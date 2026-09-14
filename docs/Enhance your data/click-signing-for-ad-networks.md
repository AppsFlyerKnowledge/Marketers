---
title: "Click signing for ad networks"
excerpt: "Learn how ad networks can sign click URLs with HMAC-SHA256 signatures to prevent click fraud and click flooding liabilities."
---
**At a glance:** Add signature validation to clicks to avoid fraud liabilities and so fraudulent clicks aren't attributed to your ad network.

## About click signing

With minimal tech, fraudsters can send clicks on behalf of an ad network and create thousands, or even millions, of fake clicks that get sent to AppsFlyer. Sometimes, the ad networks themselves aren't aware of the issue.

In order for an ad network to ensure that clicks attributed to it by AppsFlyer actually originated from the ad network, and not from a fraudster creating fake clicks, ad networks should sign their clicks with [HMAC-SHA256](https://en.wikipedia.org/wiki/HMAC) signatures.

Click signing also prevents the ad network’s traffic from being blocked due to click flooding. Meaning, that if an ad network reaches the click-blocking threshold due to an extreme level of click flooding, AppsFlyer stops recording and attributing their clicks for the rest of the day.

The signatures enable AppsFlyer to validate the clicks and make sure that the click information hasn't been manipulated by fraudsters.

- Validated clicks are recorded, and attributed to the ad network
- Invalidated clicks are rejected and:
  - Are made available in Protect360 reports for ad networks (not advertisers). [Learn more](https://support.appsflyer.com/hc/articles/4420246395793#failed-click-signatures)
  - Do not impact the conversion rate or click-blocking threshold of the ad network

## Click signature integration

### Flow

The following chart outlines the flow from initial development and basic tests to production tests, and finally, to production.

![Click_signing_integration_flow.png](https://files.readme.io/3bc0103090535c22db027fb09f72ad89d88210bba8f2b6f43d1166c2911d71cd-360017572558.png)

### Procedure

**Prerequisite:** [API V2.0 token](https://support.appsflyer.com/hc/articles/360004562377) from the admin to authorize the click signing API.

**To sign your clicks**:

1. Generate a secret key with the Generate secret key API.

Best practice: Generate and use a new secret key every 24 hours, with an expiration of 36 hours.
2. [Develop code](https://support.appsflyer.com/hc/articles/22248403360657-Click-signing-for-Ad-networks-WIP#code-example) in your servers that calls the Generate secret key API, takes the secret key and generates an HMAC-SHA256 signature. See code sample.

You can use [the other APIs](https://support.appsflyer.com/hc/articles/22248403360657-Click-signing-for-Ad-networks-WIP#click-signature-apis) as described in the table that follows.
3. The code adds the following to your click URLs:
   - An **expires** parameter that contains a Unix timestamp (in UTC) after which the ad network doesn't claim the click.
   - The HMAC-SHA256 signature.

     Example:

     ```http
     https://app.appsflyer.com/com.app.id?pid=adnetwork_int&c=my_campaign&clickid=sdkfjasksjskdfj9845weh&af_siteid=12345&expires=1597657118&signature_v2=8fnDVzZP_WRZnv3KNJaREOEfvB5p9oRc_XlKEvUo8gk
     ```

> 📘 Note
>
> Make sure any URL encoding of special characters or spaces in your link occurs before the click signature is generated. Generating the signature first results in verification failure.

## Creating a click signature

To create a click signature you must:

1. Build a JSON using the [list of attributes](https://support.appsflyer.com/hc/articles/22248403360657-Click-signing-for-Ad-networks-WIP#list-of-attributes) and [JSON rules](https://support.appsflyer.com/hc/articles/22248403360657-Click-signing-for-Ad-networks-WIP#attribute-rules) below
2. Create the signature from this JSON using HMAC56

### List of attributes

The following list of attributes is supported for click and engagement signing.

| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br>- app.appsflyer.com<br>- myapp.onelink.me<br>- click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.<br>**app-id** for single platform links or **template-id** for OneLink |
| 3 | pid | Yes |  |
| 4 | af\_prt | No |  |
| 5 | af\_siteid | Yes |  |
| 6 | clickid | Yes | A one-time unique identifier of the click |
| 7 | expires | Yes | click expiration |
| 8 | af\_engagement\_type | No |  |
| 9 | af\_click\_lookback | No |  |
| 10 | af\_viewthrough\_lookback | No |  |
| 11 | af\_reengagement\_window | No |  |
| 12 | is\_retargeting | No |  |
| 13 | af\_ip | No |  |
| 14 | advertising\_id | No |  |
| 15 | oaid | No |  |
| 16 | fire\_advertising\_id | No |  |
| 17 | idfa | No |  |
| 18 | idfv | No |  |

### Attribute and JSON rules

#### Order and appearance of attributes

- Supported parameters in the engagement URL with a value must be in the JSON
- Attributes must be listed in the JSON in the order listed in the table above

#### Empty attributes

- Attributes listed in the JSON cannot be empty values or contain only spaces

#### JSON Data structure

- The JSON data structure must be an array of attributes
  - Each attribute will be in the format `["key", "value"]`

    Example:

    `[["key-1","value-1"],["key-2","value-2"]...["key-n","value-n"]]`

#### Attribute value escaping

- The values in the JSON must be written in **lowercase strings** as defined in the [JSON standard](https://www.w3docs.com/snippets/java/how-should-i-escape-strings-in-json.html).

#### JSON spaces

- The JSON must be compacted. It should not contain any blanks, tabs, or newline characters between the values.

#### Signature algorithm

- Use HmacSHA256 with the secret key to create the signature for the JSON
- Encode the signature with Base64 **without** padding
- Add the signature to the click URL with a parameter signature\_v2

```json
//generate a signature from the click url and encode it with base64 without padding String generatedSignature = Base64.getUrlEncoder().withoutPadding().encodeToString(mac.doFinal(jsonString.getBytes()));
```

### Signature example

### Building a signature example

Example OneLink (multi-platform) click URL:

```http
https://yourbrand.onelink.me/qsWL?pid=mediasource_int&advertising_id=12345678-1234-1234-1234-123456789012
&af_ad_type=video&af_adset=MMP&clickid=sdkfjasksjskdfj9845weh&af_siteid=my_site&af_viewthrough_lookback=2h&c=my_campaign
&expires=1689695615
```

Example json object for signature (before removing blank spaces):

```json
[
	["link_domain","yourbrand.onelink.me"],
	["link_path","qswl"],
	["pid","mediasource_int"],
	["af_siteid","my_site"],
	["clickid","12345"],
	["expires","1689695615"]
]
```

Example json object for signature (after removing blank spaces)

```json
[["link_domain","yourbrand.onelink.me"],["link_path","qswl"],["pid","mediasource_int"],["template-id","qswl"],["af_siteid","my_site"],["clickid","12345"],["expires","1689695615"]]
```

Final click URL with the signature:

```http
https://yourbrand.onelink.me/qsWL?pid=mediasource_int&advertising_id=12345678-1234-1234-1234-123456789012
&af_ad_type=video&af_adset=MMP&af_siteid=my_site&af_viewthrough_lookback=2h&c=my_campaign
&expires=1689695615
&signature_v2=WIfCmfLAPSsVrBTqCqfihMeLCnbE4dIAlhHF84WsiWA
```

### Code examples

<Tabs>
<Tab title="signing-supported-params.json">

```json
[
  {"index":1, "name":"pid", "mandatory":true},
  {"index":2, "name":"af_prt", "mandatory":false},
  {"index":3, "name":"af_siteid", "mandatory":true},
  {"index":4, "name":"clickid", "mandatory":true},
  {"index":5, "name":"expires", "mandatory":true},
  {"index":6, "name":"af_engagement_type", "mandatory":false},
  {"index":7, "name":"af_click_lookback", "mandatory":false},
  {"index":8, "name":"af_viewthrough_lookback", "mandatory":false},
  {"index":9, "name":"af_reengagement_window", "mandatory":false},
  {"index":10, "name":"is_retargeting", "mandatory":false},
  {"index":11, "name":"af_ip", "mandatory":false},
  {"index":12, "name":"advertising_id", "mandatory":false},
  {"index":13, "name":"oaid", "mandatory":false},
  {"index":14, "name":"fire_advertising_id", "mandatory":false},
  {"index":15, "name":"idfa", "mandatory":false},
  {"index":16, "name":"idfv", "mandatory":false}
]
```

</Tab>
<Tab title="signature-example.go">

```go
package main

import (
	"crypto/hmac"
	"crypto/sha256"
	"encoding/base64"
	"encoding/json"
	"errors"
	"fmt"
	"io"
	"net/url"
	"os"
	"strings"
	"time"
)

type Param struct {
	Name      string
	Mandatory bool
}

func LoadSupportedParams() ([]Param, error) {
	path := "./signing-supported-params.json"
	jsonFile, _ := os.Open(path)
	defer jsonFile.Close()
	byteValue, err := io.ReadAll(jsonFile)
	if err != nil {
		return nil, errors.New("failed loading " + path)
	}
	var params []Param
	_ = json.Unmarshal(byteValue, &params)
	return params, nil
}

func computeHmac256(message, secret string) (res string, errResult error) {
	defer func() {
		if r := recover(); r != nil {
		errResult = r.(error)
		fmt.Println("failed to invoke ComputeHmac256. err: %+v", errResult)
		res = ""
		return
	}
	}()

	key := []byte(secret)
	h := hmac.New(sha256.New, key)
	h.Write([]byte(message))
	return base64.URLEncoding.WithPadding(base64.NoPadding).EncodeToString(h.Sum(nil)), nil
}

// this function accepts a click url, a ttl for the click in seconds, and the list of supported params
// the function:
// 1. adds the expiration to the click based on the provided ttl
// 2. builds a json for the signature
// 3. create an HMAC256 signature
// 4. adds the signature to the click url
func signURLV2(originalURL string, secret string, clickTtlSeconds int64, supportedParams []Param) (signedURL string, err error) {

	//add an expiration to the click
	expires := time.Now().UTC().Unix() + clickTtlSeconds
	urlWithExpired := fmt.Sprintf("%s%s%d", originalURL, "&expires=", expires)

	//parse the url
	parsedURL, err := url.Parse(urlWithExpired)
	if err != nil {
		return "", errors.New("failed parsing URL")
	}

	//build a json from the url
	jsonStr, err := buildJSONFromURLV2(parsedURL, supportedParams)
	if err != nil {
		return "", err
	}

	//create a signature
	signatureV2, err := computeHmac256(jsonStr, secret)
	if err != nil {
		fmt.Println("Failed to computeHMAC256 for url %s. err: %+v", jsonStr, err)
		return "", errors.New("fail to computeHMAC256 for url")
	}

	//add the signature to the url
	signedURL = fmt.Sprintf("%s%s%s", urlWithExpired, "&signature_v2=", signatureV2)

	return signedURL, nil

}

// this function builds a json from a given click url.
// It returns a string representation of the json ready to be signed.
func buildJSONFromURLV2(parsedURL *url.URL, supportedParams []Param) (string, error) {
	//initiate an empty json in the structure [[key-1,val-1],[key-2,val-2]...[key-n,val-n]]
	var jsonData [][2]string

	//add the url host domain to the json
	domain := parsedURL.Host
	param := [2]string{"link_domain", domain}
	jsonData = append(jsonData, param)

	//add the path (app-id or template-id) to the json
	path := parsedURL.Path
	if len(path) > 1 {
		param := [2]string{"link_path", path[1:]}
		jsonData = append(jsonData, param)
	}

	//loop over the ordered list of supported parameters and add them to the json
	for i := 0; i <len(supportedParams); i++ {name := supportedParams[i].Name val := parsedURL.Query().Get(name) if len(val) > 0 {
			param := [2]string{name, val}
			jsonData = append(jsonData, param)
		} else if supportedParams[i].Mandatory {
			return "", errors.New("missing mandatory param: " + name)
		}
	}

	//generate string representation of the json object
	jsonObj, _ := json.Marshal(jsonData)
	return strings.ToLower(string(jsonObj)), nil
}

func main() {

	supportedParams, err := LoadSupportedParams()
	if err != nil {
		fmt.Println("Error: ", err)
		os.Exit(1)
	}

	var secretKey = "tqJU4Qd/eFTEWfqW7KCG9asDO0bmZoFzv8GY3VPSPAM="
	var clickTtlSeconds int64 = 60
	var originalUrl = "https://yourbrand.onelink.me/qsWL?pid=mediasource_int&advertising_id=12345678-1234-1234-1234-123456789012&clickid=1234&af_ad_type=video&af_adset=MMP&af_siteid=my_site&af_viewthrough_lookback=2h&c=my_campaign"

	fmt.Println("Original URL: ", originalUrl)

	signedUrl, err := signURLV2(originalUrl, secretKey, clickTtlSeconds, supportedParams)
	if err != nil {
		fmt.Println("Error: ", err)
		os.Exit(1)
	} else {
		fmt.Println("Signed URL: ", signedUrl)
	}
}
```

</Tab>
</Tabs>

## Click signature APIs

AppsFlyer provides APIs that allow ad networks to manage and test the click signing process. See the list of APIs in the table below, and the sections that follow with information necessary for using the API.

#### Click signature APIs

| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br>- **disabled** (default): No click signature validation is done.<br>- **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **Report API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br>- **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br>- **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:  - Configure mode API changes to report-only.<br>  - An email alert is sent to the ad network to verify the click signing API is correctly set up.<br>- **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |

<Accordion title="Legacy versions (V1)">

These versions should not be used and are listed for reference only.

### Generate secret key method

#### Generate secret key basics

| Category | Item | Description |
| --- | --- | --- |
| Request | HTTP method | `POST` |
| Path | `https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=<ttlHours>` |
| Authorization header | - The mandatory authorization header contains a Bearer token. <br>- The admin gets the token in the dashboard as follows:  [The Admin goes to email drop-down list > API tokens to get the V2.0 token](https://support.appsflyer.com/hc/articles/360004562377) |
| Response | Results | Secret key returns in a JSON |
|  | Request limit | Maximum of 2 active secret keys at a time |

#### API request

**Method**

```http
POST https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=<ttlHours>
```

#### Parameters

| Parameter | Description |
| --- | --- |
| ttlHours | - Time to live for the secret key, in hours, from 1-1440 hours.<br>- Default is 36 hours. |

#### JSON response

| **Key** | **Description** |
| --- | --- |
| secret-key-id | An ID for the secret key |
| secret key | The secret key for the click signature |
| expiration | Epoch time in milliseconds |

#### Generate secret key curl example and response

**Curl request**

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=36' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

**JSON response**

```json
{
	"secret-key-id": "59ad6547-affc-45eb-a6c9-9805f88ee755",
	"secret-key": "zGW6Rhrmb8+vuhHtL/Kp6rW5Ci9PNsjH1J5MGO9SIeg=",
	"expiration": 1610533263
}
```

#### HTTP response codes

| Code | Message | Remarks |
| --- | --- | --- |
| 200 | OK |  |
| 401 | Not authorized | Invalid or missing authorization header |

### Revoke secret key method

#### Revoke secrete key basics

| Category | Item | Description |
| --- | --- | --- |
| Request | HTTP method | `DELETE` |
| Path | `https://hq1.appsflyer.com/api/p360-click-signing/secret/<secret-id>` |
| Authorization header | - The mandatory authorization header contains a Bearer token. <br>- The admin gets the token in the dashboard as follows:  [The Admin goes to email drop-down list > API tokens to get the V2.0 token](https://support.appsflyer.com/hc/articles/360004562377) |
| Response | Results | Empty |

#### API request

**Method**

```http
DELETE https://hq1.appsflyer.com/api/p360-click-signing/secret/<secret-id>
```

#### Parameters

| Parameter | Description |
| --- | --- |
| secret-id | The ID of the secret key to be revoked |

#### Generate secret key curl example and response

**Curl request**

```bash
curl --location --request DELETE 'https://hq1.appsflyer.com/api/p360-click-signing/secret/59ad6547-affc-45eb-a6c9-9805f88ee755' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

#### HTTP response codes

| Code | Message | Remarks |
| --- | --- | --- |
| 200 | OK |  |
| 401 | Not authorized | Invalid or missing authorization header |

### Test method

#### Test basics

| Category | Item | Description |
| --- | --- | --- |
| Request | HTTP method | `POST` |
| Path | `https://hq1.appsflyer.com/api/p360-click-signing/test` |
| Authorization header | - The mandatory authorization header contains a Bearer token. <br>- The admin gets the token in the dashboard as follows:  [The Admin goes to email drop-down list > API tokens to get the V2.0 token](https://support.appsflyer.com/hc/articles/360004562377) |
| Response | Results | Returns in a JSON |

#### API request

**Method**

```http
POST https://hq1.appsflyer.com/api/p360-click-signing/test
```

#### Parameters

| Parameter | Description |
| --- | --- |
| url | The click URL (including signature) to test |

#### JSON response

| **Key** | **Description** |
| --- | --- |
| test-status | Either Passed or Failed |
| message | Reason for the test failure. For example:<br>- Missing signature<br>- Invalid signature<br>- Expired |

#### Test curl example and response

**Curl request**

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/p360-click-signing/test' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}' \
--header 'Content-Type: application/json' \
--data-raw '{
   "url": "https://app.appsflyer.com/com.app.id?pid=adnetwork_int&c=my_campaign&clickid=sdkfjasksjskdfj9845weh&af_site_id=12345&expires=1597657118&signature=8fnDVzZP_WRZnv3KNJaREOEfvB5p9oRc_XlKEvUo8gk"
}'
```

**JSON response**

```json
{
	"test-status":"Passed / Failed",
	"message": "Invalid signature"
}
```

#### HTTP response codes

| Code | Message | Remarks |
| --- | --- | --- |
| 200 | OK |  |
| 401 | Not authorized | Invalid or missing authorization header |

### Configure mode method

#### Configure mode basics

| Category | Item | Description |
| --- | --- | --- |
| Request | HTTP method | `POST` |
| Path | `https://hq1.appsflyer.com/api/p360-click-signing/config/mode/<mode>` |
| Authorization header | - The mandatory authorization header contains a Bearer token. <br>- The admin gets the token in the dashboard as follows:  [The Admin goes to email drop-down list > API tokens to get the V2.0 token](https://support.appsflyer.com/hc/articles/360004562377) |
| Response | Results | Returns in a JSON |

#### API request

**Method**

```http
POST https://hq1.appsflyer.com/api/p360-click-signing/config/mode/<mode>
```

#### Parameters

| Parameter | Description |
| --- | --- |
| mode | Options:<br>- enabled<br>  <br>  **Note!** Only set the mode to "enabled" after you run in report-only mode for few hours and check your reports to ensure the configuration is correct and that all clicks passed signature validation.<br>- disabled<br>- report-only |

#### Configure mode curl example

**Curl request**

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/p360-click-signing/config/mode/report-only' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

#### HTTP response codes

| Code | Message | Remarks |
| --- | --- | --- |
| 200 | OK |  |
| 400 | Bad request | Invalid mode |
| 401 | Not authorized | Invalid or missing authorization header |

### Configure circuit breaker method

#### Configure circuit breaker basics

| Category | Item | Description |
| --- | --- | --- |
| Request | HTTP method | `POST` |
| Path | `https://hq1.appsflyer.com/p360-click-signing/config/circuit-breaker` |
| Authorization header | - The mandatory authorization header contains a Bearer token. <br>- The admin gets the token in the dashboard as follows:  [The Admin goes to email drop-down list > API tokens to get the V2.0 token](https://support.appsflyer.com/hc/articles/360004562377) |
| Response | Results | HTTP status |

#### API request

**Method**

```http
POST https://hq1.appsflyer.com/p360-click-signing/config/circuit-breaker
```

#### Request body JSON

| Parameter | Description |
| --- | --- |
| status | - enabled<br>- disabled |

#### Configure circuit breaker curl example and response

**Curl request**

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/p360-click-signing/config/circuit-breaker' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}' \
--data-raw '{
"status":"enabled"
}'
```

#### HTTP response codes

| Code | Message | Remarks |
| --- | --- | --- |
| 200 | OK |  |
| 400 | Bad request | Invalid status |
| 401 | Not authorized | Invalid or missing authorization header |

### Get configuration method

#### Get configuration basics

| Category | Item | Description |
| --- | --- | --- |
| Request | HTTP method | `GET` |
| Path | `https://hq1.appsflyer.com/api/p360-click-signing/config` |
| Authorization header | - The mandatory authorization header contains a Bearer token. <br>- The admin gets the token in the dashboard as follows:  [The Admin goes to email drop-down list > API tokens to get the V2.0 token](https://support.appsflyer.com/hc/articles/360004562377) |
| Response | Results | Returns in a JSON |

#### API request

**Method**

```http
GET https://hq1.appsflyer.com/api/p360-click-signing/config
```

#### JSON response

| **Key** | **Description** |
| --- | --- |
| mode | One of:<br>- enabled<br>- disabled<br>- report-only |
| circuit-breaker-config | A JSON object containing **status**, one of:<br>- enabled<br>- disabled |
| active-key-ids | A JSON array holding active keys:<br>- **secret-key-id**: Randomly-generated ID of the secret key<br>- **expiration**: Epoch time in milliseconds of the secret key |
| excluded-app-ids | A JSON array with excluded app-ids |

#### Get configuration curl example and response

**Curl request**

```bash
curl --location --request GET 'https://hq1.appsflyer.com/api/p360-click-signing/config' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

**JSON response**

```json
{
	"mode": "report-only",
	"active-key-ids": [
		{
			"secret-key-id": "59ad6547-affc-45eb-a6c9-9805f88ee755",
			"expiration": 1610533263
		}
	],
	"excluded-app-ids": [
		"app-id-1", 	"app-id-2"
	]
}
```

#### HTTP response codes

| Code | Message | Remarks |
| --- | --- | --- |
| 200 | OK |  |
| 401 | Not authorized | Invalid or missing authorization header |

### Report method

#### Report basics

| Category | Item | Description |
| --- | --- | --- |
| Request | HTTP method | `GET` |
| Path | `https://hq1.appsflyer.com/api/p360-click-signing/report` |
| Authorization header | - The mandatory authorization header contains a Bearer token. <br>- The admin gets the token in the dashboard as follows:  [The Admin goes to email drop-down list > API tokens to get the V2.0 token](https://support.appsflyer.com/hc/articles/360004562377) |
| Response | Results | Returns in a CSV |

#### API request

**Method**

```http
GET https://hq1.appsflyer.com/api/p360-click-signing/report
```

#### Parameters

| Parameter | Description |
| --- | --- |
| start-date | Start date and time for the report. Format: yyyy-mm-ddThh |
| end-date | End date and time for the report. Format: yyyy-mm-ddThh |
| The API requires either **both** start-date and end-date or **neither** of them. If start/end date are not provided, the report shows results for the past 24 hours. |

#### CSV response

| **Column** | **Description** |
| --- | --- |
| time | Date and time of the clicks. Format yyyy-mm-ddThh |
| total\_clicks | Total number of clicks during the reporting period |
| valid\_clicks | Number of valid clicks during the reporting period |
| missing\_signature | Number of clicks missing signatures during the reporting period |
| expired\_clicks | Number of expired clicks during the reporting period |
| invalid\_signature | Number of clicks with invalid signatured during the reporting period |
| no\_active\_secrets | Number of clicks rejected because there are no active secret keys in the system (usually when the system is in report-only mode) |

#### Test curl example and response

**Curl request**

```bash
curl --location --request GET 'https://hq1.appsflyer.com/api/p360-click-signing/report?start-date=2021-01-07T07&end-date=2021-01-17T12' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

**CSV response**

| **time** | **total\_clicks** | **valid\_clicks** | **missing\_signature** | **expired\_clicks** | **invalid\_signature** | **no\_active\_signatures** |
| --- | --- | --- | --- | --- | --- | --- |
| 2021-01-17T07 | 928082156 | 928082156 | 0 | 0 | 0 | 0 |
| 2021-01-17T08 | 923796132 | 923796132 | 0 | 0 | 0 | 0 |
| 2021-01-17T09 | 917541373 | 917541373 | 0 | 0 | 0 | 0 |
| 2021-01-17T10 | 909977064 | 909977064 | 0 | 0 | 0 | 0 |
| 2021-01-17T11 | 965104299 | 965104299 | 0 | 0 | 0 | 0 |
| 2021-01-17T12 | 975134824 | 975134824 | 0 | 0 | 0 | 0 |

#### HTTP response codes

| Code | Message | Remarks |
| --- | --- | --- |
| 200 | OK |  |
| 401 | Not authorized | Invalid or missing authorization header |

### Exclude app method

#### Exclude app method basics

| Category | Item | Description |
| --- | --- | --- |
| Request | HTTP method | `POST` |
| Path | `https://hq1.appsflyer.com/api/p360-click-signing/config/excluded-app/<app-id>` |
| Authorization header | - The mandatory authorization header contains a Bearer token. <br>- The admin gets the token in the dashboard as follows:  [The Admin goes to email drop-down list > API tokens to get the V2.0 token](https://support.appsflyer.com/hc/articles/360004562377) |
| Response | Results | Empty |

#### API request

**Method**

```http
POST https://hq1.appsflyer.com/api/p360-click-signing/config/excluded-app/<app-id>
```

#### Parameters

| Parameter | Description |
| --- | --- |
| app-id | Application ID to be excluded from click signing validation |

#### Exclude app curl example

**Curl request**

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/p360-click-signing/config/excluded-app/appname.com' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

#### HTTP response codes

| Code | Message | Remarks |
| --- | --- | --- |
| 200 | OK |  |
| 401 | Not authorized | Invalid or missing authorization header |

### Remove excluded app method

#### Remove excluded app method basics

| Category | Item | Description |
| --- | --- | --- |
| Request | HTTP method | `DELETE` |
| Path | `https://hq1.appsflyer.com/api/p360-click-signing/config/excluded-app/<app-id>` |
| Authorization header | - The mandatory authorization header contains a Bearer token. <br>- The admin gets the token in the dashboard as follows:  [The Admin goes to email drop-down list > API tokens to get the V2.0 token](https://support.appsflyer.com/hc/articles/360004562377) |
| Response | Results | Empty |

#### API request

**Method**

```http
DELETE https://hq1.appsflyer.com/api/p360-click-signing/config/excluded-app/<app-id>
```

#### Parameters

| Parameter | Description |
| --- | --- |
| app-id | Application ID to be removed from the list of apps excluded from click signing validation |

#### Remove excluded app curl example

**Curl request**

```bash
curl --location --request DELETE 'https://hq1.appsflyer.com/api/p360-click-signing/config/excluded-app/appname.com' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

#### HTTP response codes

| Code | Message | Remarks |
| --- | --- | --- |
| 200 | OK |  |
| 401 | Not authorized | Invalid or missing authorization header |

</Accordion>

## Code sample

```java
package sign;

import javax.crypto.Mac;
import javax.crypto.spec.SecretKeySpec;
import java.security.InvalidKeyException;
import java.security.NoSuchAlgorithmException;
import java.util.Base64;

.
.
.

String clickUrl = "https://app.appsflyer.com/com.app.id?pid=adnetwork_int&c=my_campaign&clickid=sdkfjasksjskdfj9845weh&af_site_id=12345";
String secretKey = "secret_key";
int ttlMinutes = 5;

//add expiration to the click URL
long expiration = System.currentTimeMillis() + (60000L * ttlMinutes);
clickUrl += "&expires="+expiration;

//create a SecretKey object from the given key string
SecretKeySpec signingKey = new SecretKeySpec(secretKey.getBytes(), "HmacSHA256");
Mac mac = Mac.getInstance("HmacSHA256");
mac.init(signingKey);

//generate a signature from the click url and encode it with base64 without padding
String generatedSignature =
Base64.getUrlEncoder().withoutPadding().encodeToString(mac.doFinal(clickUrl.getBytes()));

//add the signature to the click URL
String signedClickUrl = clickUrl + "&signature=" + generatedSignature;
```

## Additional information

### Troubleshooting

AppsFlyer stops click signature validation and reverts to the report-only mode when more than 90% of clicks in an hour fail signature validation.

This is to protect your business from a potential technical issue and allows you to find the cause of the anomaly:

- If you find that the signature is working as expected and the clicks are being correctly blocked, disable the circuit-breaker using the [configure circuit breaker method.](/docs/click-signing-for-ad-networks#configure-circuit-breaker-method)
- If you find that clicks are being incorrectly blocked:
  1. Make sure that you have a valid secret key by checking the click signing configuration using the [get configuration method.](/docs/click-signing-for-ad-networks#get-configuration-method)
  2. Use the [click signing report](/docs/click-signing-for-ad-networks#report-method) to get more information about the blocked clicks and investigate the sources (agency/app- iDs) and reasons for invalid clicks.
- If you find a problem with a specific app because of a non-standard integration, exclude this app from click signing validation using the [exclude app API.](/docs/click-signing-for-ad-networks#exclude-app-method)
- If you find a problem with your configuration:
  1. Continue running in report-only mode.
  2. Fix the click signing process on your side.
  3. Check the results in the [click signing report](/docs/click-signing-for-ad-networks#report-method) and re-enable click-signing validation when you see that clicks are being validated as expected.

### FAQ

<Accordion title="How can we test click signing without impacting production?">

There are two ways to test click signing:
1. Use the [test API](/docs/click-signing-for-ad-networks#test-method). This method is useful during the development phase, to test the signatures of single clicks.
2. Use report-only mode. Report-only mode verifies the signatures on the production clicks and shows you what would be blocked, but doesn't block invalid clicks. Therefore, you can test that click signing works without impacting real traffic.

</Accordion>

<Accordion title="What is the difference between an API token and a secret-key?">

**API token**: Is used to authorize and run the click signing API. There is only one per ad network. The [AppsFlyer API V2.0 token](https://support.appsflyer.com/hc/articles/360004562377) must be obtained from the admin.

**Secret key**: Is used to generate the signature. Use the [generate secret key method](/docs/click-signing-for-ad-networks#generate-secret-key-method) to create secret keys. The ad network is responsible for generating new secret keys. See the [traits section](/docs/click-signing-for-ad-networks#traits) for more information.

</Accordion>

<Accordion title="Can we apply click signing to only certain campaigns?">

No. Click signing is applied to all clicks from an ad network. You can exclude certain apps from click signing, but you can’t exclude only certain campaigns.

</Accordion>

### Traits

| Trait | Description |
| --- | --- |
| Click signature | The signature must occur on the ad network servers. |
| Secret key | - Ad networks can have a maximum of two secret keys active simultaneously.<br>- Each secret key has an expiration.<br>- Clicks signed with expired secret keys are rejected. |
| Report API | Updated statistics of click validity are aggregated on an hourly basis. |
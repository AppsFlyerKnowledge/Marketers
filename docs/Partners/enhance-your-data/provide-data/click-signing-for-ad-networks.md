---
title: "Click signing for ad networks"
excerpt: "Learn how ad networks can sign click URLs with HMAC-SHA256 signatures to prevent click fraud and click flooding liabilities."
x-zendesk:
  id: 360017831497
  url: https://support.appsflyer.com/hc/en-us/articles/360017831497-Click-signing-for-ad-networks
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Provide data
  section_id: 6551209900817
  position: 4
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-yael-sharabi, Marketers, Ad Networks, Data Management]
  labels: [Ad Network, Advertisers, Protect360, Ad Networks, Partners, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2021-02-22T09:33:52Z'
  edited_at: '2024-11-17T09:37:22Z'
---
**At a glance:** Add signature validation to clicks to avoid fraud liabilities and so fraudulent clicks aren't attributed to your ad network.

## About click signing

With minimal tech, fraudsters can send clicks on behalf of an ad network and create thousands, or even millions, of fake clicks that get sent to AppsFlyer. Sometimes, the ad networks themselves aren't aware of the issue.

In order for an ad network to ensure that clicks attributed to it by AppsFlyer actually originated from the ad network, and not from a fraudster creating fake clicks, ad networks should sign their clicks with [HMAC-SHA256](https://en.wikipedia.org/wiki/HMAC) signatures.

Click signing also prevents the ad network’s traffic from being blocked due to click flooding. Meaning, that if an ad network reaches the click-blocking threshold due to an extreme level of click flooding, AppsFlyer stops recording and attributing their clicks for the rest of the day.

The signatures enable AppsFlyer to validate the clicks and make sure that the click information hasn't been manipulated by fraudsters.

* Validated clicks are recorded, and attributed to the ad network
* Invalidated clicks are rejected and:
  * Are made available in Protect360 reports for ad networks (not advertisers). [Learn more](/docs/protect360-reports-for-ad-networks#failed-click-signatures)
  * Do not impact the conversion rate or click-blocking threshold of the ad network

## Click signature integration

### Flow

The following chart outlines the flow from initial development and basic tests to production tests, and finally, to production.

![Click_signing_integration_flow.png](https://files.readme.io/3bc0103090535c22db027fb09f72ad89d88210bba8f2b6f43d1166c2911d71cd-360017572558.png)

### Procedure

**Prerequisite:** [API V2.0 token](/docs/managing-appsflyer-tokens) from the admin to authorize the click signing API.

**To sign your clicks**:

1. Generate a secret key with the Generate secret key API.  
   Best practice: Generate and use a new secret key every 24 hours, with an expiration of 36 hours.
2. Develop code in your servers that calls the Generate secret key API, takes the secret key and generates an HMAC-SHA256 signature. See code sample.  
   You can use the other APIs as described in the table that follows.
3. The code adds the following to your click URLs:
   * An **expires** parameter that contains a Unix timestamp (in UTC) after which the ad network doesn't claim the click.
   * The HMAC-SHA256 signature.  
     Example:

     ```
     https://app.appsflyer.com/com.app.id?pid=adnetwork_int&c=my_campaign&clickid=sdkfjasksjskdfj9845weh&af_siteid=12345&expires=1597657118&signature_v2=8fnDVzZP_WRZnv3KNJaREOEfvB5p9oRc_XlKEvUo8gk
     ```

> 📘 **Note**
>
> Make sure any URL encoding of special characters or spaces in your link occurs before the click signature is generated. Generating the signature first results in verification failure.


## Creating a click signature

To create a click signature you must:

1. Build a JSON using the list of attributes and JSON rules below
2. Create the signature from this JSON using HMAC56

### List of attributes

The following list of attributes is supported for click and engagement signing.



| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br /><br />* app.appsflyer.com<br />* myapp.onelink.me<br />* click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.  <br />**app-id** for single platform links or **template-id** for OneLink |
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

* Supported parameters in the engagement URL with a value must be in the JSON
* Attributes must be listed in the JSON in the order listed in the table above

#### Empty attributes

* Attributes listed in the JSON cannot be empty values or contain only spaces

#### JSON Data structure

* The JSON data structure must be an array of attributes
  * Each attribute will be in the format ["key", "value"]  
    Example:   
    `[["key-1","value-1"],["key-2","value-2"]...["key-n","value-n"]]`

#### Attribute value escaping

* The values in the JSON must be written in **lowercase strings** as defined in the [JSON standard](https://www.w3docs.com/snippets/java/how-should-i-escape-strings-in-json.html).

#### JSON spaces

* The JSON must be compacted. It should not contain any blanks, tabs, or newline characters between the values.

#### Signature algorithm

* Use HmacSHA256 with the secret key to create the signature for the JSON
* Encode the signature with Base64 **without** padding
* Add the signature to the click URL with a parameter signature\_v2

```
//generate a signature from the click url and encode it with base64 without padding String generatedSignature = Base64.getUrlEncoder().withoutPadding().encodeToString(mac.doFinal(jsonString.getBytes()));
```

### Signature example

### Building a signature example

Example OneLink (multi-platform) click URL:

```
https://yourbrand.onelink.me/qsWL?pid=mediasource_int&advertising_id=12345678-1234-1234-1234-123456789012  
&af_ad_type=video&af_adset=MMP&clickid=sdkfjasksjskdfj9845weh&af_siteid=my_site&af_viewthrough_lookback=2h&c=my_campaign  
&expires=1689695615
```

Example json object for signature (before removing blank spaces):

```
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

```
[["link_domain","yourbrand.onelink.me"],["link_path","qswl"],["pid","mediasource_int"],["template-id","qswl"],["af_siteid","my_site"],["clickid","12345"],["expires","1689695615"]]
```

Final click URL with the signature:

```
https://yourbrand.onelink.me/qsWL?pid=mediasource_int&advertising_id=12345678-1234-1234-1234-123456789012  
&af_ad_type=video&af_adset=MMP&af_siteid=my_site&af_viewthrough_lookback=2h&c=my_campaign  
&expires=1689695615  
&signature_v2=WIfCmfLAPSsVrBTqCqfihMeLCnbE4dIAlhHF84WsiWA
```

### Code examples

### signing-supported-params.json

```
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

### signature-example.go

```
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

## Click signature APIs

AppsFlyer provides APIs that allow ad networks to manage and test the click signing process. See the list of APIs in the table below, and the sections that follow with information necessary for using the API. 

#### Click signature APIs



| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br /><br />* **disabled** (default): No click signature validation is done.<br />* **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **R****eport API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br />* **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br /><br />* **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:<br />  * Configure mode API changes to report-only.<br />  * And email alert is sent to the ad network to verify the click signing API is correctly set up.<br />* **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |



## Legacy versions

These versions should not be used and are listed for reference only

### V1 - Legacy

### Generate secret key method

#### Generate secret key basics



<table><thead><tr><th>Category</th><th>Item</th><th><span>Description</span></th></tr></thead><tbody><tr><td rowspan="3">Request</td><td>HTTP method</td><td><code>POST</code></td></tr><tr><td>Path</td><td><span>https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=&lt;ttlHours&gt;</span></td></tr><tr><td>Authorization header </td><td><ul><li>The mandatory authorization header contains a Bearer token. </li><li>The admin gets the token in the dashboard as follows:  <a href="/docs/managing-appsflyer-tokens">The Admin goes to email drop-down list &gt; API tokens to get the V2.0 token </a> </li></ul></td></tr><tr><td>Response</td><td>Results</td><td>Secret key returns in a JSON</td></tr><tr><td> </td><td>Request limit</td><td>Maximum of 2 active secret keys at a time</td></tr></tbody></table>



#### API request

**Method**

```
POST https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=<ttlHours>
```

#### Parameters



| Parameter | Description |
| --- | --- |
| ttlHours | * Time to live for the secret key, in hours, from 1-1440 hours.<br />* Default is 36 hours. |



#### JSON response



| **Key** | **Description** |
| --- | --- |
| secret-key-id | An ID for the secret key |
| secret key | The secret key for the click signature |
| expiration | Epoch time in milliseconds |



#### Generate secret key curl example and response

**Curl request**

```
curl --location --request POST 'https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=36' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

**JSON response**

```
{
	"secret-key-id": "59ad6547-affc-45eb-a6c9-9805f88ee755",
	"secret-key": "zGW6Rhrmb8+vuhHtL/Kp6rW5Ci9PNsjH1J5MGO9SIeg=",
	"expiration": 1610533263
}
```

#### HTTP response codes

#### Response codes



| Code | Message | Remarks |
| --- | --- | --- |
| 200 | OK |  |
| 401 | Not authorized | Invalid or missing authorization header |



### Revoke secret key method

#### Revoke secrete key basics



<table><thead><tr><th>Category</th><th>Item</th><th><span>Description</span></th></tr></thead><tbody><tr><td rowspan="3">Request</td><td>HTTP method</td><td><code>DELETE</code></td></tr><tr><td>Path</td><td><span>https://hq1.appsflyer.com/api/p360-click-signing/secret/&lt;secret-id&gt;</span></td></tr><tr><td>Authorization header </td><td><ul><li>The mandatory authorization header contains a Bearer token. </li><li>The admin gets the token in the dashboard as follows:  <a href="/docs/managing-appsflyer-tokens">The Admin goes to email drop-down list &gt; API tokens to get the V2.0 token </a> </li></ul></td></tr><tr><td>Response</td><td>Results</td><td>Empty</td></tr></tbody></table>



#### API request

**Method**

```
DELETE https://hq1.appsflyer.com/api/p360-click-signing/secret/<secret-id>
```

#### Parameters



| Parameter | Description |
| --- | --- |
| secret-id | The ID of the secret key to be revoked |



#### Generate secret key curl example and response

**Curl request**

```
curl --location --request DELETE 'https://hq1.appsflyer.com/api/p360-click-signing/secret/59ad6547-affc-45eb-a6c9-9805f88ee755' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

#### HTTP response codes

#### Response codes



| Code | Message | Remarks |
| --- | --- | --- |
| 200 | OK |  |
| 401 | Not authorized | Invalid or missing authorization header |



### Test method

#### Test basics



| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br /><br />* app.appsflyer.com<br />* myapp.onelink.me<br />* click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.  <br />**app-id** for single platform links or **template-id** for OneLink |
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

0

#### API request

**Method**

```
POST https://hq1.appsflyer.com/api/p360-click-signing/test
```

#### Parameters



| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br /><br />* app.appsflyer.com<br />* myapp.onelink.me<br />* click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.  <br />**app-id** for single platform links or **template-id** for OneLink |
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

1

#### JSON response



| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br /><br />* app.appsflyer.com<br />* myapp.onelink.me<br />* click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.  <br />**app-id** for single platform links or **template-id** for OneLink |
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

2

#### Test curl example and response

**Curl request**

```
curl --location --request POST 'https://hq1.appsflyer.com/api/p360-click-signing/test' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}' \
--header 'Content-Type: application/json' \
--data-raw '{
   "url": "https://app.appsflyer.com/com.app.id?pid=adnetwork_int&c=my_campaign&clickid=sdkfjasksjskdfj9845weh&af_site_id=12345&expires=1597657118&signature=8fnDVzZP_WRZnv3KNJaREOEfvB5p9oRc_XlKEvUo8gk"
}'
```

**JSON response**

```
{
	"test-status":"Passed / Failed",
	"message": "Invalid signature"
}
```

#### HTTP response codes

#### Response codes



| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br /><br />* app.appsflyer.com<br />* myapp.onelink.me<br />* click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.  <br />**app-id** for single platform links or **template-id** for OneLink |
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

3

### Configure mode method

#### Configure mode basics



| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br /><br />* app.appsflyer.com<br />* myapp.onelink.me<br />* click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.  <br />**app-id** for single platform links or **template-id** for OneLink |
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

4

#### API request

**Method**

```
POST https://hq1.appsflyer.com/api/p360-click-signing/config/mode/<mode>
```

#### Parameters



| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br /><br />* app.appsflyer.com<br />* myapp.onelink.me<br />* click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.  <br />**app-id** for single platform links or **template-id** for OneLink |
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

5

#### Configure mode curl example

**Curl request**

```
curl --location --request POST 'https://hq1.appsflyer.com/api/p360-click-signing/config/mode/report-only' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

#### HTTP response codes

#### Response codes



| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br /><br />* app.appsflyer.com<br />* myapp.onelink.me<br />* click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.  <br />**app-id** for single platform links or **template-id** for OneLink |
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

6

### Configure circuit breaker method

#### Configure circuit breaker basics



| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br /><br />* app.appsflyer.com<br />* myapp.onelink.me<br />* click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.  <br />**app-id** for single platform links or **template-id** for OneLink |
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

7

#### API request

**Method**

```
POST https://hq1.appsflyer.com/p360-click-signing/config/circuit-breaker
```

#### Request body JSON



| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br /><br />* app.appsflyer.com<br />* myapp.onelink.me<br />* click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.  <br />**app-id** for single platform links or **template-id** for OneLink |
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

8

#### Configure circuit breaker curl example and response

**Curl request**

```
curl --location --request POST 'https://hq1.appsflyer.com/api/p360-click-signing/config/circuit-breaker' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
--data-raw '{
"status":"enabled"
}'
```

#### HTTP response codes

#### Response codes



| Order | Parameter | Mandatory | Notes |
| --- | --- | --- | --- |
| 1 | link\_domain | Yes | The domain from the click URL For example:<br /><br />* app.appsflyer.com<br />* myapp.onelink.me<br />* click.mycustomdomain.com |
| 2 | link\_path | Yes | The path of the click URL not including a leading backslash.  <br />**app-id** for single platform links or **template-id** for OneLink |
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

9

### Get configuration method

#### Get configuration basics



| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br /><br />* **disabled** (default): No click signature validation is done.<br />* **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **R****eport API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br />* **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br /><br />* **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:<br />  * Configure mode API changes to report-only.<br />  * And email alert is sent to the ad network to verify the click signing API is correctly set up.<br />* **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |

0

#### API request

**Method**

```
GET https://hq1.appsflyer.com/api/p360-click-signing/config
```

#### JSON response



| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br /><br />* **disabled** (default): No click signature validation is done.<br />* **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **R****eport API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br />* **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br /><br />* **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:<br />  * Configure mode API changes to report-only.<br />  * And email alert is sent to the ad network to verify the click signing API is correctly set up.<br />* **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |

1

#### Get configuration curl example and response

**Curl request**

```
curl --location --request GET 'https://hq1.appsflyer.com/api/p360-click-signing/config' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

**JSON response**

```
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

#### Response codes



| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br /><br />* **disabled** (default): No click signature validation is done.<br />* **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **R****eport API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br />* **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br /><br />* **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:<br />  * Configure mode API changes to report-only.<br />  * And email alert is sent to the ad network to verify the click signing API is correctly set up.<br />* **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |

2

### Report method

#### Report basics



| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br /><br />* **disabled** (default): No click signature validation is done.<br />* **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **R****eport API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br />* **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br /><br />* **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:<br />  * Configure mode API changes to report-only.<br />  * And email alert is sent to the ad network to verify the click signing API is correctly set up.<br />* **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |

3

#### API request

**Method**

```
GET https://hq1.appsflyer.com/api/p360-click-signing/report
```

#### Parameters



| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br /><br />* **disabled** (default): No click signature validation is done.<br />* **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **R****eport API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br />* **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br /><br />* **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:<br />  * Configure mode API changes to report-only.<br />  * And email alert is sent to the ad network to verify the click signing API is correctly set up.<br />* **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |

4

#### CSV response



| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br /><br />* **disabled** (default): No click signature validation is done.<br />* **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **R****eport API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br />* **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br /><br />* **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:<br />  * Configure mode API changes to report-only.<br />  * And email alert is sent to the ad network to verify the click signing API is correctly set up.<br />* **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |

5

#### Test curl example and response

**Curl request**

```
curl --location --request GET 'https://hq1.appsflyer.com/api/p360-click-signing/report?start-date=2021-01-07T07&end-date=2021-01-17T12' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}' \
```

**CSV response**



| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br /><br />* **disabled** (default): No click signature validation is done.<br />* **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **R****eport API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br />* **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br /><br />* **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:<br />  * Configure mode API changes to report-only.<br />  * And email alert is sent to the ad network to verify the click signing API is correctly set up.<br />* **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |

6

#### HTTP response codes

#### Response codes



| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br /><br />* **disabled** (default): No click signature validation is done.<br />* **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **R****eport API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br />* **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br /><br />* **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:<br />  * Configure mode API changes to report-only.<br />  * And email alert is sent to the ad network to verify the click signing API is correctly set up.<br />* **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |

7

### Exclude app method

#### Exclude app method basics



| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br /><br />* **disabled** (default): No click signature validation is done.<br />* **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **R****eport API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br />* **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br /><br />* **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:<br />  * Configure mode API changes to report-only.<br />  * And email alert is sent to the ad network to verify the click signing API is correctly set up.<br />* **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |

8

#### API request

**Method**

```
POST https://hq1.appsflyer.com/api/p360-click-signing/config/excluded-app/<app-id>
```

#### Parameters



| API method | Remarks |
| --- | --- |
| [Generate secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-post) | Generate secret keys to be used in the signature. |
| [Revoke secret key](https://dev.appsflyer.com/hc/reference/click-signing-secret-delete) | Cancel compromised secret keys. |
| [Test](https://dev.appsflyer.com/hc/reference/click-signing-test-post) | Send single clicks for testing the signature. |
| [Configure mode](https://dev.appsflyer.com/hc/reference/click-signing-config-update-put) | Configure mode of click signing mode: <br /><br />* **disabled** (default): No click signature validation is done.<br />* **report-only** (testing mode): AppsFlyer validates click signatures, but doesn't block clicks with invalid signatures. The ad network can use the **R****eport API** to get statistics on successful/failing clicks. Use this to test click signing without impacting production and real traffic.<br />* **enabled:** AppsFlyer blocks clicks with invalid or missing signatures. |
| [Configure circuit breaker](https://dev.appsflyer.com/hc/reference/click-signing-config-circuit-breaker-put) | Configure the mode of the circuit breaker that protects the ad network from having too many blocked clicks:<br /><br />* **enabled** (default): If the Protect360 system detects that too many clicks are marked as invalid, then in order to protect the ad network from having potentially incorrectly blocked clicks:<br />  * Configure mode API changes to report-only.<br />  * And email alert is sent to the ad network to verify the click signing API is correctly set up.<br />* **disabled**: Protect360 continues to block all clicks marked as invalid, even when the block percentage is unusually high. |
| [Get configuration](https://dev.appsflyer.com/hc/reference/click-signing-config-get) | Get the mode and IDs of active secret keys. |
| [Report](https://dev.appsflyer.com/hc/reference/click-signing-report-get) | Get the last 3 days statistics on successful and failing clicks when the system is in **report-only** or **enabled** mode. Use this to test click signing without impacting production and real traffic. |
| [Exclude app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add) | Configure app IDs to be excluded from click signing. |
| [Remove excluded app](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-delete) | Configure app IDs to be included in click signing after being excluded. |

9

#### Exclude app curl example

**Curl request**

```
curl --location --request POST 'https://hq1.appsflyer.com/api/p360-click-signing/config/excluded-app/appname.com' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

#### HTTP response codes

#### Response codes



<table><thead><tr><th>Category</th><th>Item</th><th><span>Description</span></th></tr></thead><tbody><tr><td rowspan="3">Request</td><td>HTTP method</td><td><code>POST</code></td></tr><tr><td>Path</td><td><span>https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=&lt;ttlHours&gt;</span></td></tr><tr><td>Authorization header </td><td><ul><li>The mandatory authorization header contains a Bearer token. </li><li>The admin gets the token in the dashboard as follows:  <a href="/docs/managing-appsflyer-tokens">The Admin goes to email drop-down list &gt; API tokens to get the V2.0 token </a> </li></ul></td></tr><tr><td>Response</td><td>Results</td><td>Secret key returns in a JSON</td></tr><tr><td> </td><td>Request limit</td><td>Maximum of 2 active secret keys at a time</td></tr></tbody></table>

0

### Remove excluded app method

#### Remove excluded app method basics



<table><thead><tr><th>Category</th><th>Item</th><th><span>Description</span></th></tr></thead><tbody><tr><td rowspan="3">Request</td><td>HTTP method</td><td><code>POST</code></td></tr><tr><td>Path</td><td><span>https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=&lt;ttlHours&gt;</span></td></tr><tr><td>Authorization header </td><td><ul><li>The mandatory authorization header contains a Bearer token. </li><li>The admin gets the token in the dashboard as follows:  <a href="/docs/managing-appsflyer-tokens">The Admin goes to email drop-down list &gt; API tokens to get the V2.0 token </a> </li></ul></td></tr><tr><td>Response</td><td>Results</td><td>Secret key returns in a JSON</td></tr><tr><td> </td><td>Request limit</td><td>Maximum of 2 active secret keys at a time</td></tr></tbody></table>

1

#### API request

**Method**

```
DELETE https://hq1.appsflyer.com/api/p360-click-signing/config/excluded-app/<app-id>
```

#### Parameters



<table><thead><tr><th>Category</th><th>Item</th><th><span>Description</span></th></tr></thead><tbody><tr><td rowspan="3">Request</td><td>HTTP method</td><td><code>POST</code></td></tr><tr><td>Path</td><td><span>https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=&lt;ttlHours&gt;</span></td></tr><tr><td>Authorization header </td><td><ul><li>The mandatory authorization header contains a Bearer token. </li><li>The admin gets the token in the dashboard as follows:  <a href="/docs/managing-appsflyer-tokens">The Admin goes to email drop-down list &gt; API tokens to get the V2.0 token </a> </li></ul></td></tr><tr><td>Response</td><td>Results</td><td>Secret key returns in a JSON</td></tr><tr><td> </td><td>Request limit</td><td>Maximum of 2 active secret keys at a time</td></tr></tbody></table>

2

#### Remove excluded app curl example

**Curl request**

```
curl --location --request DELETE 'https://hq1.appsflyer.com/api/p360-click-signing/config/excluded-app/appname.com' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
```

#### HTTP response codes

#### Response codes



<table><thead><tr><th>Category</th><th>Item</th><th><span>Description</span></th></tr></thead><tbody><tr><td rowspan="3">Request</td><td>HTTP method</td><td><code>POST</code></td></tr><tr><td>Path</td><td><span>https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=&lt;ttlHours&gt;</span></td></tr><tr><td>Authorization header </td><td><ul><li>The mandatory authorization header contains a Bearer token. </li><li>The admin gets the token in the dashboard as follows:  <a href="/docs/managing-appsflyer-tokens">The Admin goes to email drop-down list &gt; API tokens to get the V2.0 token </a> </li></ul></td></tr><tr><td>Response</td><td>Results</td><td>Secret key returns in a JSON</td></tr><tr><td> </td><td>Request limit</td><td>Maximum of 2 active secret keys at a time</td></tr></tbody></table>

3

## Code sample

```
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

* If you find that the signature is working as expected and the clicks are being correctly blocked, disable the circuit-breaker using the [configure circuit breaker method.](/docs/click-signing-for-ad-networks#configure-circuit-breaker-method)
* If you find that clicks are being incorrectly blocked:
  1. Make sure that you have a valid secret key by checking the click signing configuration using the [get configuration method.](/docs/click-signing-for-ad-networks#get-configuration-method)
  2. Use the [click signing report](/docs/click-signing-for-ad-networks#report-method) to get more information about the blocked clicks and investigate the sources (agency/app- iDs) and reasons for invalid clicks.
* If you find a problem with a specific app because of a non-standard integration, exclude this app from click signing validation using the [exclude app API.](/docs/click-signing-for-ad-networks#exclude-app-method)
* If you find a problem with your configuration:
  1. Continue running in report-only mode.
  2. Fix the click signing process on your side.
  3. Check the results in the [click signing report](/docs/click-signing-for-ad-networks#report-method) and re-enable click-signing validation when you see that clicks are being validated as expected.

### FAQ



<table><thead><tr><th>Category</th><th>Item</th><th><span>Description</span></th></tr></thead><tbody><tr><td rowspan="3">Request</td><td>HTTP method</td><td><code>POST</code></td></tr><tr><td>Path</td><td><span>https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=&lt;ttlHours&gt;</span></td></tr><tr><td>Authorization header </td><td><ul><li>The mandatory authorization header contains a Bearer token. </li><li>The admin gets the token in the dashboard as follows:  <a href="/docs/managing-appsflyer-tokens">The Admin goes to email drop-down list &gt; API tokens to get the V2.0 token </a> </li></ul></td></tr><tr><td>Response</td><td>Results</td><td>Secret key returns in a JSON</td></tr><tr><td> </td><td>Request limit</td><td>Maximum of 2 active secret keys at a time</td></tr></tbody></table>

4

### Traits



<table><thead><tr><th>Category</th><th>Item</th><th><span>Description</span></th></tr></thead><tbody><tr><td rowspan="3">Request</td><td>HTTP method</td><td><code>POST</code></td></tr><tr><td>Path</td><td><span>https://hq1.appsflyer.com/api/p360-click-signing/secret?ttlHours=&lt;ttlHours&gt;</span></td></tr><tr><td>Authorization header </td><td><ul><li>The mandatory authorization header contains a Bearer token. </li><li>The admin gets the token in the dashboard as follows:  <a href="/docs/managing-appsflyer-tokens">The Admin goes to email drop-down list &gt; API tokens to get the V2.0 token </a> </li></ul></td></tr><tr><td>Response</td><td>Results</td><td>Secret key returns in a JSON</td></tr><tr><td> </td><td>Request limit</td><td>Maximum of 2 active secret keys at a time</td></tr></tbody></table>

5
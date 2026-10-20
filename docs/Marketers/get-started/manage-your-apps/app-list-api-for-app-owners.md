---
title: App list API for app owners
excerpt: Retrieve active and pending apps associated with your AppsFlyer account.
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-08-17T18:07:10Z'
  edited_at: '2026-05-05T06:57:58Z'
  id: 360011999877
  locale: en-us
  section: Manage your apps
  section_id: 6551015977105
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360011999877-App-list-API-for-app-owners
---
![mceclip0.png](https://files.readme.io/34b4b3d56ca5d7419830ba26701483f64ebb0a908e1e8e7ed65779bb89a14c67-24507752775313.png)

If you are an ad network, use the [app list for ad networks](/partners/docs/app-list-api-for-ad-networks) API.

**Further reading**: [API list for advertisers](/docs/about-advertiser-apis)

## Get app list API

The following sections include information necessary for using the API.

**Get app list basics**

<div id="get-api-list-basics" />

<Accordion title="Get API list basics">

<table><thead><tr><th>Category</th><th>Item</th><th><span>Description</span></th></tr></thead><tbody><tr><td rowspan="3">Request</td><td>HTTP method</td><td><code>GET</code></td></tr><tr><td>Path</td><td><span>https://hq1.appsflyer.com/api/mng/apps</span></td></tr><tr><td>Authorization header </td><td><ul><li>The mandatory authorization header contains a Bearer token. </li><li>An admin user gets the token in the dashboard as follows: <a href="./managing-appsflyer-tokens">The Admin goes to email drop-down list &gt; API tokens to get the V2.0 token </a></li></ul></td></tr><tr><td rowspan="3"> Response</td><td>Results</td><td>Return in a JSON</td></tr><tr><td>Request limit</td><td><ul><li>20 requests/minute</li><li>100 requests/day</li></ul></td></tr><tr><td>Record limit</td><td>1,000 records/request. If more than 1,000 records are to return, use follow-on pagination requests described in this article.</td></tr></tbody></table>

</Accordion>

<div id="api-request" />

<Accordion title="API request">

The API request consists of the method, path, mandatory capabilities parameter, and optional pagination parameters. The token is contained in the authorization header.

**Method**

```
GET https://hq1.appsflyer.com/api/mng/apps
```

Get app list mandatory parameters:

| Query parameter | Description |
| --- | --- |
|  | There are no mandatory query parameters for this API |

#### **Pagination mechanism**

A pagination mechanism, always operational, is implemented.

**Pagination principles:**

* Returns up to 1,000 records per request (page).
* Response JSONs contain the following pagination-related keys:
  * **meta.total\_items**: The number of records to be returned by all pages combined. This represents the number of apps for which you have been granted the *capabilities*being queried.
  * Pagination links (depicted in the JSON that follows) have the following keys:
    * **links.prev**: If there was a previous request: the request used to generate the previous page.
    * **links.self**: The current request: the request used to generate the current JSON (page)
    * **links.next**: The request required to get the next page. If there is no *next*key, this is the last page.

**Use one of the following pagination control methods:**

* [Best practice] Use the *links* in the JSON: If the *links.next* key exists, use it to create a request to get the next page. Continue to do so until you receive a JSON without a*links.next* key*.*
* Programmatically implement *limit* and *offset* parameters in conjunction with the *total\_items* key.

**Pagination links JSON example**

* The example that follows contains the result of the second request, consisting of two records in the data section (not displayed).
* The total number of records to return is 6.
* The **links.next** key contains the request that returns the second page—records 5 and 6.

```json
{                                                                                         
    "data": {[...]},   
    "meta": {
        "total_items": 6
    },
    "links": {
        "prev": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=2",
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=2&limit=2",
        "next": "https://hq1.appsflyer.com/api/mng/apps?offset=4&limit=2"
    }
}
```

Pagination mechanism parameters (optional):

| Query parameter | Description |
| --- | --- |
| limit | Number of records that return per call<ul><li>Maximum: 1,000</li><li>If you don't send`limit`, it is automatically set to 1,000.</li><li>Example: `limit=2`</li><li>Mandatory: No</li></ul> |
| offset | The first record to return in the call. Record numbers start with 0.<ul><li>If you don't send `offset`, it is automatically set to 0.</li><li>Example: `offset=2`</li><li>Mandatory: No</li></ul> |

</Accordion>

<div id="json-response" />

<Accordion title="JSON response">

| **Key** | **Description** |
| --- | --- |
| id | App ID, for example: `id123456789`, `com.myapp.com` |
| type | Always return `app` |
| name | App name |
| platform | iOS or Android |
| currency | App-specific currency code |
| time\_zone | App-specific timezone |
| total\_items | Number of apps housed in the account |
| links | Pagination mechanism (explained in the parameters section)<ul><li>prev: the call used to generate the previous page</li><li>self: the call used to generate the current page</li><li>next: the call used to generate the next page</li></ul> |

</Accordion>

<div id="get-app-list-curl-example-and-response" />

<Accordion title="Get app list cURL example and response">

**CURL request**

This example includes a complete call, including optional pagination parameters.

```
cURL --location --request GET 'https://hq1.appsflyer.com/api/mng/apps?limit=1000&offset=0' \
-H 'Authorization: Bearer {API V2.0 token having more than 700 characters available to the admin in the dashboard.}' \
```

**JSON response**

```json
{
    "data": [
        {
            "id": "com.appsflyer.xpend_qa1",
            "type": "app",
            "attributes": {
                "name": "com.appsflyer.xpend_qa1",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC"
            }
        },
        {
            "id": "com.abc.app",
            "type": "app",
            "attributes": {
                "name": "com.abc.app",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC",
                "enable_retargetting": true
            }
        },
        {
            "id": "com.def.app",
            "type": "app",
            "attributes": {
                "name": "com.def.app",
                "platform": "android",
                "currency": "JPY",
                "time_zone": "UTC"
            }
        }
    ],
    "meta": {
        "total_items": 6
    },
    "links": {
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=1000"
           }
}
```

</Accordion>

<div id="http-response-codes" />

<Accordion title="HTTP response codes">

| Code | Message | Remarks/troubleshooting |
| --- | --- | --- |
| 200 | OK | Valid data returned |
| 200 | OK | **Symptom**: No data returns<br /><br />**Action**: Make sure the authentication token is in the bearer header. |
| 400 | Bad request | See the message contained in the JSON |
| 401 | Unauthorized | **Message**: Authorization token is malformed<br /><br />Make sure you have the correct token; token must have 700+ characters. |
| 404 | Not found | <ul><li>Handle any network or firewall-related problems.</li><li>Make sure that AppsFlyer [IP addresses are allowlisted](/docs/appsflyer-server-ip-address-ranges-allowlisting)</li><li>Make sure you use the most recently-issued token.</li><li>No data found: No apps found.</li></ul> |
| 429 | Too many requests | Exceeded rate limitation |

</Accordion>

<div data-zendesk-anchors="h_01KQS56KS2G7TD4VHZCHVP0W9S=get-app-list-api h_01KQS56KS26TY81ACBN2XBK3W2=get-api-list-basics h_01KQS56KS27NETZ4C5RY28V804=api-request h_01KQS56KS33VFVX099T1S2928G=pagination-mechanism h_01KQS56KS3Q5EEVSSC7G1FEFXR=json-response h_01KQS56KS3EZCH1KBBQQKTXWYP=get-app-list-curl-example-and-response h_01KQS56KS3S04KDZ58J7XKQNCK=http-response-codes" />

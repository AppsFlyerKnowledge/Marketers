---
title: "App list API for app owners"
excerpt: "Retrieve active and pending apps associated with your AppsFlyer account using the App List API."
x-zendesk:
  id: 360011999877
  url: https://support.appsflyer.com/hc/en-us/articles/360011999877-App-list-API-for-app-owners
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Manage your apps
  section_id: 6551015977105
  position: 4
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Advertisers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2020-08-17T18:07:10Z'
  edited_at: '2026-05-05T06:57:58Z'
---
**At a glance:** Retrieve active and pending apps associated with your AppsFlyer account.

![mceclip0.png](https://files.readme.io/34b4b3d56ca5d7419830ba26701483f64ebb0a908e1e8e7ed65779bb89a14c67-24507752775313.png)

If you are an ad network, use the [app list for ad networks](/docs/app-list-api-for-ad-networks) API.

**Further reading**: [API list for advertisers](/docs/about-advertiser-apis)

## Get app list API

The following sections include information necessary for using the API.

### Get API list basics

| Category | Item | Description |
| --- | --- | --- |
| Request | HTTP method | `GET` |
| Path | https://hq1.appsflyer.com/api/mng/apps |
| Authorization header | - The mandatory authorization header contains a Bearer token. <br />- An admin user gets the token in the dashboard as follows: [The Admin goes to email drop-down list > API tokens to get the V2.0 token](/docs/managing-appsflyer-tokens) |
| Response | Results | Return in a JSON |
| Request limit | - 20 requests/minute<br />- 100 requests/day |
| Record limit | 1,000 records/request. If more than 1,000 records are to return, use follow-on pagination requests described in this article. |

### API request

The API request consists of the method, path, mandatory capabilities parameter, and optional pagination parameters. The token is contained in the authorization header.

**Method**

```http
GET https://hq1.appsflyer.com/api/mng/apps
```

Get app list mandatory parameters:

| Query parameter | Description |
| --- | --- |
| | There are no mandatory query parameters for this API |

#### Pagination mechanism

A pagination mechanism, always operational, is implemented.

**Pagination principles:**

- Returns up to 1,000 records per request (page).
- Response JSONs contain the following pagination-related keys:
  - **meta.total_items**: The number of records to be returned by all pages combined. This represents the number of apps for which you have been granted the _capabilities_ being queried.
  - Pagination links (depicted in the JSON that follows) have the following keys:
    - **links.prev**: If there was a previous request: the request used to generate the previous page.
    - **links.self**: The current request: the request used to generate the current JSON (page)
    - **links.next**: The request required to get the next page. If there is no _next_ key, this is the last page.

**Use one of the following pagination control methods:**

- [Best practice] Use the _links_ in the JSON: If the _links.next_ key exists, use it to create a request to get the next page. Continue to do so until you receive a JSON without a _links.next_ key.
- Programmatically implement _limit_ and _offset_ parameters in conjunction with the _total_items_ key.

**Pagination links JSON example**

- The example that follows contains the result of the second request, consisting of two records in the data section (not displayed).
- The total number of records to return is 6.
- The **links.next** key contains the request that returns the second page—records 5 and 6.

```json
{
    "data": [{...}],
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
| limit | Number of records that return per call<br />- Maximum: 1,000<br />- If you don't send `limit`, it is automatically set to 1,000.<br />- Example: `limit=2`<br />- Mandatory: No |
| offset | The first record to return in the call. Record numbers start with 0. <br />- If you don't send `offset`, it is automatically set to 0.<br />- Example: `offset=2`<br />- Mandatory: No |

### JSON response

| Key | Description |
| --- | --- |
| id | App ID, for example: `id123456789`, `com.myapp.com` |
| type | Always return `app` |
| name | App name |
| platform | iOS or Android |
| currency | App-specific currency code |
| time_zone | App-specific timezone |
| total_items | Number of apps housed in the account |
| links | Pagination mechanism (explained in the parameters section)<br />- prev: the call used to generate the previous page<br />- self: the call used to generate the current page<br />- next: the call used to generate the next page |

### Get app list cURL example and response

<Tabs>
<Tab title="cURL">

```bash
curl --location --request GET 'https://hq1.appsflyer.com/api/mng/apps?limit=1000&offset=0' \
-H 'Authorization: Bearer {API V2.0 token having more than 700 characters available to the admin in the dashboard.}'
```

</Tab>
<Tab title="Response">

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

</Tab>
</Tabs>

### HTTP response codes

| Code | Message | Remarks/troubleshooting |
| --- | --- | --- |
| 200 | OK | Valid data returned |
| 200 | OK | **Symptom**: No data returns<br />**Action**: Make sure the authentication token is in the bearer header. |
| 400 | Bad request | See the message contained in the JSON |
| 401 | Unauthorized | **Message**: Authorization token is malformed<br />Make sure you have the correct token; token must have 700+ characters. |
| 404 | Not found | - Handle any network or firewall-related problems. <br />- Make sure that AppsFlyer [IP addresses are allowlisted](/docs/appsflyer-server-ip-address-ranges-allowlisting)<br />- Make sure you use the most recently-issued token.<br />- No data found: No apps found. |
| 429 | Too many requests | Exceeded rate limitation |
---
title: "App list API for ad networks"
excerpt: "Ad networks can retrieve metadata of apps associated with their integrated partner account."
x-zendesk:
  id: 360011700857
  url: https://support.appsflyer.com/hc/en-us/articles/360011700857-App-list-API-for-ad-networks
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: APIs for ad networks
  section_id: 6551618728209
  position: 1
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Mobile Attribution, Ad Networks]
  labels: [API, Ad Networks, Partners, Developers]
  promoted: false
  comments_disabled: true
  created_at: '2020-08-06T20:11:15Z'
  edited_at: '2026-05-05T07:03:21Z'
---
## Get app list API

The following sections include information necessary for using the API.

### Get app list basics

| Category | Item | Description |
| --- | --- | --- |
| Request | HTTP method | `GET` |
| Path | https://hq1.appsflyer.com/api/mng/apps |
| Authorization header | - The mandatory authorization header contains a Bearer token. <br />- The admin gets the token in the dashboard as follows: [The Admin goes to email drop-down list > API tokens to get the V2.0 token](/docs/managing-appsflyer-tokens) |
| Response | Results | Return in JSON |
| Request limit | - 20 requests/minute<br />- 100 requests/day |
| Record limit | 1,000 records/request. If more than 1,000 records are to be returned, use follow-on pagination requests, described in this article. |

### API request

The API request consists of the method, path, mandatory capabilities parameter, and optional pagination parameters. The token is contained in the authorization header.

**Method**

```http
GET https://hq1.appsflyer.com/api/mng/apps?capabilities={capabilities}
```

#### Get app list mandatory parameters

| Query parameter | Description |
| --- | --- |
| capabilities | To get the list and number of apps to which you have permission/integration capabilities: set the capabilities parameter to one of the options listed. |

| Option | Type | Description |
| --- | --- | --- |
| `protect_360` | Report permission | Get [Protect360 raw data reports for ad networks](/docs/protect360-for-integrated-partners) |
| `cost` | Integration | App is enabled to get cost data [via InCost API](/docs/incost-api-for-ad-networks) |

**Example**: List of apps for which you have Protect360 report API permission: `capabilities=protect_360`

#### Pagination mechanism

A pagination mechanism, always operational, is implemented.

**Pagination principles:**

- Returns up to 1,000 records per request (page).
- Response JSONs contain the following pagination related keys:
  - **meta.total_items**: The number of records to be returned by all pages combined. This represents the number of apps for which you have been granted the capabilities being queried.
  - Pagination links (depicted in the JSON that follows) have the following keys:
    - **links.prev**: If there was a previous request: the request used to generate the previous page.
    - **links.self**: The current request: the request used to generate the current JSON (page)
    - **links.next**: The request required to get the next page. If there is no next key, this is the last page.

**Use one of the following pagination control methods:**

- [Best practice] Use the links in the JSON: If the links.next key exists, use it to create a request to get the next page. Continue to do so until you receive a JSON without a links.next key.
- Programmatically implement limit and offset parameters in conjunction with the total_items key.

**Pagination links JSON example**

- The example that follows contains the result of the first request, consisting of the second request containing two records in the data section (not displayed).
- The total number of records to return is 6.
- The **links.next** key contains the request that returns the next page—records 5 and 6.

```json
{
    "data": [{...}],
    "meta": {
        "total_items": 6
    },
    "links": {
        "prev": "https://hq1.appsflyer.com/api/mng/apps?capabilities=protect_360&offset=0&limit=2",
        "self": "https://hq1.appsflyer.com/api/mng/apps?capabilities=protect_360&offset=2&limit=2",
        "next": "https://hq1.appsflyer.com/api/mng/apps?capabilities=protect_360&offset=4&limit=2"
    }
}
```

#### Pagination mechanism parameters (optional)

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
| currency | App-specific currency code as set by the advertiser |
| time_zone | App-specific timezone as set by the advertiser |
| total_items | Number of apps to which the ad network has the requested capabilities option |
| links | Pagination mechanism (explained in the parameters section)<br />- prev: the call used to generate the previous page<br />- self: the call used to generate the current page<br />- next: the call used to generate the next page |

### Get app list curl example and response

<Tabs>
<Tab title="cURL">

```bash
curl --location --request GET 'https://hq1.appsflyer.com/api/mng/apps?capabilities=protect_360&limit=1000&offset=0' \
-H 'Authorization: Bearer {API V2.0 token available to the admin in the dashboard.}'
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
            "id": "com.xyz.app",
            "type": "app",
            "attributes": {
                "name": "com.xyz.app",
                "platform": "android",
                "currency": "JPY",
                "time_zone": "UTC"
            }
        }
    ],
    "meta": {
        "total_items": 3
    },
    "links": {
        "self": "https://hq1.appsflyer.com/api/mng/apps?capabilities=protect_360&offset=0&limit=1000"
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
| 400 | Bad request | - See the message contained in the JSON<br />- Empty JSON: illegal capability specified |
| 401 | Unauthorized | **Message**: Authorization token is malformed<br />Make sure you have the correct token; token must have 700+ characters. |
| 404 | Not found | - Handle any network or firewall-related problems. <br />- Make sure that AppsFlyer [IP addresses are allowlisted](/docs/appsflyer-server-ip-address-ranges-allowlisting)<br />- Make sure you use the most recently-issued token.<br />- No data found: The permission/integration (capabilities) type requested is legal, but no apps with permission were found. |
| 429 | Too many requests | Exceeded rate limitation |
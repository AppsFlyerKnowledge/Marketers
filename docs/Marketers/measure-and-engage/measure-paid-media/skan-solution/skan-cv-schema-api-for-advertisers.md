---
title: "SKAN CV schema API for advertisers"
excerpt: "View your current SKAdNetwork (SKAN) conversion value (CV) schema as configured in AppsFlyer Conversion Studio."
x-zendesk:
  id: 8610329713553
  url: https://support.appsflyer.com/hc/en-us/articles/8610329713553-SKAN-CV-schema-API-for-advertisers
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SKAN solution
  section_id: 6552135379985
  position: 11
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, SKAdNetwork (SKAN)]
  labels: [Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-08-24T12:59:10Z'
  edited_at: '2024-01-11T10:37:57Z'
---
## SKAN conversion value schema API

<Accordion title="API basics">

| Overview | View your current SKAdNetwork (SKAN) conversion value (CV) schema as configured in AppsFlyer Conversion Studio.<br /><br />**Note**:<ul><li>Historic SKAN CV schema isn't available.</li><li>You can also view your SKAN schema by downloading the CSV mapping file available in Conversion Studio.</li></ul> |
| --- | --- |
| Path | `https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>` |
| Path parameters (mandatory) | `<app_id>`: Is the app identifier as found in the AppsFlyer dashboard. Insert it exactly as it displays in the dashboard. Example: id123456789 |
| HTTP method | `GET` |
| Response content type | `text/plain` |
| Authorization | `Authorization` HTTP header containing API V2.0 token (Bearer token) is required.<br /><br />![AppsFlyerAdmin_us-en.png](https://files.readme.io/466e632ed4068c94ee10e1f72e3451e6133f7029554358d60b7433c267538bba-21590572168721.png)An admin user [gets the V2 token in the dashboard,](/docs/managing-appsflyer-tokens) from the top bar, open the account menu (email address dropdown) > **Security Center** > **AppsFlyer API and S2S tokens**. |
| Rate limitation | <ul><li>Queries return up to 50K rows</li><li>10 calls per minute</li></ul> |
| Date of last  configuration change | <ul><li>For decode mode, the date displays in the filename.</li><li>For all other modes, the date displays in the last\_config\_change column.</li></ul> |

### Request example (cURL)

```bash
curl --request \
GET 'https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>' \
--header 'Authorization: Bearer <V2_AUTH_TOKEN_HERE (700+ characters string)>'
```

</Accordion>

<Accordion title="Report name">

The API returns a CSV file with the following naming scheme:

For decode mode: `conversion_value_mapping_<date of last schema configuration change>`

For all other modes: `conversion_schema_report_custom_encode`

</Accordion>

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Ad network access | If you are an analytics partner, ask the advertiser to grant you permission. |
| Agency access | Not available |
| Account user access | The authorization token is available to an admin user in the dashboard. |

</Accordion>

<Accordion title="HTTP response codes and troubleshooting">

| HTTP | Response | Remarks |
| --- | --- | --- |
| 200 | OK | Valid data returned (CSV) |
| 400 | Bad request | Invalid request |
| 401 | Unauthorized | Authorization token is missing or invalid<br /><br />Make sure you use the token correctly |
| 401 | Too many requests | Exceeded rate limitation |
| 403 | No permission | You don't have permission to access this report. If you are an analytics partner ask the advertiser to give you permission. |
| 404 | Not found | <ul><li>Handle any network or firewall-related problems.</li><li>Make sure that AppsFlyer [IP addresses are allowlisted](/docs/appsflyer-server-ip-address-ranges-allowlisting)</li></ul> |

</Accordion>

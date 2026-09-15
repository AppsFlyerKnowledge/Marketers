---
title: "SKAN CV schema API for advertisers"
excerpt: "View your current SKAdNetwork (SKAN) conversion value (CV) schema as configured in AppsFlyer Conversion Studio."
---
## SKAN conversion value schema API

### API basics

|     |     |
| --- | --- |
| Overview | View your current SKAdNetwork (SKAN) conversion value (CV) schema as configured in AppsFlyer Conversion Studio.<br>**Note**:<br>- Historic SKAN CV schema isn't available. <br>- You can also view your SKAN schema by downloading the CSV mapping file available in Conversion Studio. |
| Path | `https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>` |
| Path parameters (mandatory) | `<app_id>`: Is the app identifier as found in the AppsFlyer dashboard. Insert it exactly as it displays in the dashboard. Example: id123456789 |
| HTTP method | `GET` |
| Response content type | `text/plain` |
| Authorization | `Authorization` HTTP header containing API V2.0 token (Bearer token) is required.<br> ![AppsFlyerAdmin_us-en.png](https://files.readme.io/466e632ed4068c94ee10e1f72e3451e6133f7029554358d60b7433c267538bba-21590572168721.png) An admin user [gets the V2 token in the dashboard,](https://support.appsflyer.com/hc/articles/360004562377) from the top bar, open the account menu (email address dropdown) > **Security Center** \> **AppsFlyer API and S2S tokens**. |
| Rate limitation | - Queries return up to 50K rows<br>- 10 calls per minute |
| Date of last  configuration change | - For decode mode, the date displays in the filename.<br>- For all other modes, the date displays in the last\_config\_change column. |

### Request example (cURL)

```shell
curl --request \
GET 'https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>' \
--header 'Authorization: Bearer <V2_AUTH_TOKEN_HERE (700+ characters string)>'
```

### Report name

The API returns a CSV file with the following naming scheme:

For decode mode: `conversion_value_mapping_<date of last schema configuration change>`

For all other modes: `conversion_schema_report_custom_encode`

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| Ad network access | If you are an analytics partner, ask the advertiser to grant you permission. |
| Agency access | Not available |
| Account user access | The authorization token is available to an admin user in the dashboard. |

### HTTP response codes and troubleshooting

| HTTP | Response | Remarks |
| --- | --- | --- |
| 200 | OK | Valid data returned (CSV) |
| 400 | Bad request | Invalid request |
| 401 | Unauthorized | Authorization token is missing or invalid<br>Make sure you use the token correctly |
| 401 | Too many requests | Exceeded rate limitation |
| 403 | No permission | You don't have permission to access this report. If you are an analytics partner ask the advertiser to give you permission. |
| 404 | Not found | - Handle any network or firewall-related problems. <br>- Make sure that AppsFlyer [IP addresses are allowlisted](https://support.appsflyer.com/hc/articles/207447093-AppsFlyer-server-IP-address-ranges-allowlisting-) |
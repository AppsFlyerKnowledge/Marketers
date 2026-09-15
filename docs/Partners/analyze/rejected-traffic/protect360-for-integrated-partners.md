---
title: "Protect360 for integrated partners"
excerpt: "Integrated partners can view fraud related to their traffic identified and blocked by the ProtectLITE and Protect360 engines, as well as the customer's manually-defined validation rules."
---
Integrated partners (ad networks and agencies) can view fraud related to their traffic identified and blocked by the ProtectLITE and Protect360 engines, as well as the customer’s manually-defined validation rules.

## Overview

AppsFlyer identifies and blocks fraud via:

- [ProtectLITE](https://support.appsflyer.com/hc/articles/360017223058): Basic fraud protection for all customers.
- [Protect360](https://support.appsflyer.com/hc/articles/218254203): Advanced fraud protection for advertisers with a premium subscription plan.

Advertisers must give:

- Ad networks [permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab) to **Access Protect360 dashboard and raw data** reports (that includes ProtectLITE), and **Access aggregate in-app events data** (for in-app event fraud).
- Agencies [permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab) to **Access Protect360 dashboard and raw data.**

With the correct permissions, integrated partners can:

- View data related to the traffic they generated.
- Download related [raw data reports](https://support.appsflyer.com/hc/articles/218254203#raw-data).

There are also [raw data reports](https://support.appsflyer.com/hc/articles/4420246395793) available to ad networks about impression capping, as well as failed click signatures, for which no advertiser permissions are required.

> 📘 Note
>
> For advertisers that work with ad networks through an agency, in order for both the ad network and agency to access data, the advertiser must integrate both the agency and ad network in AppsFlyer, and grant them both permission to access data.
>
> If only the agency is integrated and granted permissions, the ad network does not have access to the data.

### Dashboard view

**Prerequisites**: Permission from the advertiser to access ProtectLITE and Protect360.

Integrated partners can view the dashboard and charts; see the screenshot that follows.

Learn more about what data is available in the [ProtectLITE](https://support.appsflyer.com/hc/articles/360017223058#dashboard) and [Protect360](https://support.appsflyer.com/hc/articles/218254203#dashboard) dashboards.

Limitations:

- Ad networks cannot access the Anomalies dashboard.

<Image src="https://files.readme.io/234771b87c3343700d42b2cbbc283db5d65db7ea96af6bead7d55eb03d9bde01-44928678658833.jpg" alt="p360_dashboard_1.jpg" />

- Ad networks and Agencies cannot access the fraud protection studio, or the raw data level of tagged data. They can, however, see it aggregated in the Protect360 dashboard under tagged attribution and tagged in-app events. As well as identify fraud by tag type (new release etc) . To learn more about FPS see [this article](/docs/beta-fraud-protection-studio).

### Raw-data reports

**Prerequisites**: Permission from the advertiser to access ProtectLITE and Protect360.

Protect360 raw-data reports show identified and blocked fraud via ProtectLITE, Protect360, and Validation Rules.

Reports are available via:

- Export data: In AppsFlyer, from the side menu, select **Report** > **Raw Data Export**
- API: See the [ad network reporting API](#protect360-ad-network-reporting-api) section that follows.

Learn more about [Protect360 raw data reports](https://support.appsflyer.com/hc/articles/360015179337).

## Protect360 ad network reporting API

- The raw-data reports listed in this section are available to ad networks via API.
- Equivalent reports are available from the dashboard on the Export Data page.
- If the advertiser does not have a Protect360 subscription, only the Installs report is available.

**Prerequisites**

- To access advertiser data by API, the advertiser grants the ad network [permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab) to access their Protect360 dashboard and data by API. Ad networks having access to the dashboard are permitted to use the API. No action is required by the advertiser.
- For a list of apps for which you have Protect360 permissions use [get app list API.](https://support.appsflyer.com/hc/articles/360011700857)
- The admin needs to get an AppsFlyer [V2.0 authentication token](https://support.appsflyer.com/hc/articles/360004562377-Managing-API-tokens) available in the dashboard.

#### Protect360 API reports

| Report | Data freshness | Description |
| --- | --- | --- |
| Post-attribution in-app events fraud | Daily 10:00 UTC | - In-app events performed by installs identified as fraudulent.<br>- Any other in-app event judged as fraudulent irrespective of the install.<br>The report can be optionally filtered by in-app event type as described in the parameters table that follows. <br>Report topic: `fraud-post-inapps` |
| Post-attribution installs | Daily 10:00 UTC | - Installs identified as fraudulent post-attribution. <br>- The report can be optionally filtered by the detection date as described in the section that follows. <br>Report topic: detection |
| Installs | Real-time | Blocked installs with the block reason<br>Report topic: blocked_installs_report |
| In-app event | Real-time | In-app events performed by blocked users<br>Report topic: `blocked_in-app_events_report` |
| Clicks | Real-time | Clicks performed by blocked users<br>Report topic: `blocked_clicks_report` |

#### **Procedure for ad networks to get Protect360 reports by download**

**To get a report using the API:**

1. Identify the required report from the preceding list.
2. Use the relevant curl example (in the following section) to prepare your script.
3. Ensure that you replace the following placeholders:
   1. App ID
   2. From date
   3. To date
   4. Bearer token (AppsFlyer [V2.0 authentication token](https://support.appsflyer.com/hc/articles/360004562377-Managing-API-tokens))
4. Some calls have [optional parameters](/docs/protect360-for-integrated-partners#api-parameters), as described in this article.

### Curl examples

<Tabs>
<Tab title="Installs">

```bash
curl --location --request GET 'https://hq1.appsflyer.com/api/adnets-data/v1/export/blocked_installs_report/app/{app_id}?from={2020-07-10}&to={2020-07-20}&additional_fields=keyword_id,store_reinstall,deeplink_url,oaid,blocked_reason,blocked_reason_value,blocked_reason_rule,blocked_sub_reason,match_type,device_category,gp_referrer,gp_click_time,gp_install_begin,amazon_aid,keyword_match_type' \
-H 'Authorization: Bearer {V2.0 api token placeholder. Note: The token has more than 700 characters.}'
```

</Tab>
<Tab title="Post-attribution installs">

```bash
curl --location --request GET 'https://hq1.appsflyer.com/api/adnets-data/v1/export/detection/app/{app-id}?from={2020-06-10}&to={2020-07-20}&additonal-fields=fraud_reason,fraud_sub_reason,match_type,device_category,gp_referrer,gp_click_time,gp_install_begin,detection_date' \
-H 'Authorization: Bearer {V2.0 api token placeholder. Note: The token has more than 700 characters.}'
```

</Tab>
<Tab title="In-app event">

```bash
curl --location --request GET 'https://hq1.appsflyer.com/api/adnets-data/v1/export/blocked_in_app_events_report/app/?from=YYYY-MM-DD&to=YYYY-MM-DD&additional_fields=keyword_id,store_reinstall,deeplink_url,oaid,blocked_reason,blocked_reason_value,blocked_reason_rule,blocked_sub_reason,match_type,device_category,gp_referrer,gp_click_time,gp_install_begin,amazon_aid,keyword_match_type' \
-H 'Authorization: Bearer {V2.0 api token placeholder. Note: The token has more than 700 characters.}'
```

</Tab>
<Tab title="Post-attribution in-app events">

```bash
curl --location --request GET 'https://hq1.appsflyer.com/api/adnets-data/v1/export/fraud-post-inapps/app/{app-id}?from={2020-06-10}&to={2020-07-20}&additional_fields=match_type,device_category,gp_referrer,gp_click_time,gp_install_begin,fraud_reason,fraud_sub_reason,detection_date' \
-H 'Authorization: Bearer {V2.0 api token placeholder. Note: The token has more than 700 characters.}'
```

</Tab>
<Tab title="Clicks">

```bash
curl --location --request GET 'https://hq1.appsflyer.com/api/adnets-data/v1/export/blocked_clicks_report/app/{app-id}?from={2020-06-10}&to={2020-07-20}&additional_fields=keyword_id,store_reinstall,deeplink_url,oaid,blocked_reason,blocked_reason_value,blocked_reason_rule,blocked_sub_reason,gp_referrer,gp_click_time,gp_install_begin,amazon_aid,keyword_match_type' \
-H 'Authorization: Bearer {V2.0 api token placeholder. Note: The token has more than 700 characters.}'
```

</Tab>
</Tabs>

### Protect360 ad network API reference guide

### API basics

Protect360 ad network API basics:

| | |
| --- | --- |
| Path | `https://hq1.appsflyer.com/api/adnets-data/v1/export/report_topic/app/app_id` |
| Method | GET |
| Path parameters (mandatory) | - `app_id`:<br>  - The app identifier, as found in the AppsFlyer dashboard. Insert it precisely as it displays in the dashboard.<br>  - Make sure to prefix iOS apps with **id.**<br>- `report_topic`: |
| Accepted content types | `application/json` |
| Authorization | - Bearer token in the request header.<br>- <Image src="https://files.readme.io/5708713f5adc7560748b16d2df4a439163e1310fc7d32f2e5ca786d176cbc8d3-44928678665617.png" alt="AppsFlyerAdmin_us-en.png" /> Ask the admin to get the V2.0 token from the [tokens](https://support.appsflyer.com/hc/articles/360004562377-Managing-API-tokens) page. This token is about 700 characters in length. |
| Rate limitation | [Rate limitations](https://support.appsflyer.com/hc/articles/207034366) |
| Date range limitation | - Earliest date supported: 90 days before the current data<br>- 31 days out of the previous 90 days |
| Row limitations | 200K rows |
| Report characteristics | - Timezone: UTC<br>- Currency: USD |

### API parameters

Protect360 API parameters:

| Parameter | Description | Format | Mandatory |
| --- | --- | --- | --- |
| app\_id | App ID as it displays in AppsFlyer | String | Yes |
| from | Start of the date range:<br>- For installs, this is the install date.<br>- For in-app events, this is the date of the event. | YYYY-MM-DD | Yes |
| to | End of the date range:<br>- For installs, this is the install date.<br>- For in-app events, this is the date of the event. | YYYY-MM-DD | Yes |
| event\_name | [Optional for Post-attribution in-app events fraud]<br>Filter events by in-app event. Limit the report to specific events. One or more events can be included.<br>Example usage: `&event_name=af_purchase,af_login` | String | No |
| detect-from | [Optional for Post-attribution installs]<br>Start of the fraud detection date range. (Default is from.) | YYYY-MM-DD | No |
| detect-to | [Optional for Post-attribution installs]<br>End of the fraud detection date range. (Default is to.) | YYYY-MM-DD | No |

### Protect360 API HTTP return codes

Error codes and solutions:

| Status | Code | Symptom/message | Solution |
| --- | --- | --- | --- |
| OK | 200 | Empty CSV file | `addtional_fields` used more than once in the URI |
| OK | 200 | Empty CSV file | Ensure that both from and to dates have the format yyyy-mm-dd |
| OK | 200 | AppsFlyer HTML login page returns | There is no token in the Bearer token header |
| Bad request | 400 | Bad request | - Date range limitation.<br>  - The earliest date allowed is 90 days prior to the current day<br>  - Period can't exceed 60 days for installs and 90 days for in-app reports |
| Unauthorized | 401 | Unauthorized | A token was found, but it is not valid. Check that you have the current V2.0 token for your account. Ask the admin to retrieve the current token from the dashboard. |
| Not found | 404 | | - The endpoint specified is incorrect<br>- Ensure that the app ID is correct<br>- You are not authorized to access the app |

## Impression capping

If an ad network has extremely high rates of impression fraud, Protect360 blocks the ad network’s impressions for a 24-hour cycle. This means that any impressions that occur after the threshold is reached are not recorded by AppsFlyer, nor are they eligible for attribution. The blocked impressions do appear in the Protect360 dashboard and reports.

The AppsFlyer fraud protection algorithm takes into account various parameters when detecting this fraud, including volume of impressions, CVR, detected fraud rate, normal fluctuations in activity, industry and geographic benchmarks, and proprietary parameters. The algorithm is dynamic and updated on an hourly basis, to take into consideration changing trends.

> ❗️ Critical
>
> Repeatedly triggering impression flooding thresholds may result in the permanent removal of the partner integration from the AppsFlyer platform.

Impression capping thresholds:

- Apply to all ad networks equally. Meaning, there is no ad network for which extremely high rates of impression fraud would not lead to capping.
- Are at the app/ad network level. Meaning, the analysis of fraud takes into account all the ad network’s campaigns on an app, And the block affects reporting and attribution for all the ad network’s campaigns on an app (whether or not the account has Protect360).
- Are reset after a 24-hour cycle and blocks apply until the end of the cycle. Details on when the cycle starts and ends are kept private by AppsFlyer.
- Cannot be changed or stopped. Protect360 is finely tuned and accurate in its fraud detection and the algorithm can’t be manually adjusted or turned off.
- Can be avoided by stopping campaigns and publishers with anomalous activity.

### FAQ

<Accordion title="Q: What is the network threshold?">

**A**: Details of the capping mechanism are protected to prevent attempts at circumvention. That said, the threshold is only reached if there is an extreme volume of impressions fired, beyond the possibility of human behavior. Looking at the day’s impression, install volumes will give you a clear idea of whether there is a flood issue stemming from one or more publishers.

</Accordion>
<Accordion title="Q: How can a network get unblocked?">

**A**: A network can avoid the threshold by stopping campaigns and publishers with anomalous activity. Once blocked, the network needs to wait until the end of the 24-hour cycle to resume being recorded.

</Accordion>
<Accordion title="Q: Does the block affect AppsFlyer customers without Protect360?">

**A**: Yes, capping will affect regardless of whether or not a customer has Protect360. The capping mechanism protects all customers from impression abuse.

</Accordion>
<Accordion title="Q: This is not fraud. The network is working with cheap sources and sometimes their quality is low.">

**A**: Poor performance at a normal scale from non-suspicious sources does not trigger capping. The algorithm identifies performance that cannot possibly be human.

</Accordion>
<Accordion title="Q: This stops us from scaling campaigns and we don't want these impressions to be blocked.">

**A**: The AppsFlyer fraud protection algorithm protects customers from extreme and blatant instances of flooding. It doesn't impact scaling ability, as it addresses non-human generated impressions, where the vast majority of blocks only cause liabilities. If you have concerns, please contact AppsFlyer to address your issues.

</Accordion>
<Accordion title="Q: This is not fraud. Maybe AppsFlyer has issues dealing with the volume of impressions?">

**A**: We don't have any issues handling volume. We support some of the world’s largest-scale advertisers and process billions of real-time data points each day, including enormous numbers of legitimate impressions. As part of our commitment to support high-scale growth with rich and accurate data, we act in our customers’ best interests and block clear instances of impression flooding.

</Accordion>
<Accordion title="Q: What can we do if we expect a significant increase in traffic and impression volume (for example, due to new campaigns)? What can be done to avoid being blocked?">

**A**: The algorithm is dynamic and updated on an hourly basis, to take into consideration different trends. It is sophisticated enough to handle spikes and is not triggered by normal activity fluctuations, including sudden and significant increases in volume. That said, partners can use their impression data and reports to identify suspicious sources and stop those campaigns.

</Accordion>
<Accordion title="Q: How can we check for problematic traffic and improve campaign performance?">

**A**: Partners can use their impression data and reports to identify suspicious sources and stop those campaigns. Partners can also see blocked impression data in the Protect360/ProtectLITE dashboard under the dedicated columns, as long as they have received the required permission from the advertiser to view fraud data in the dashboard.

</Accordion>

### Click signing

Ad networks can add HMAC-SHA256 [signatures to their clicks](https://support.appsflyer.com/hc/articles/360017831497).

The signatures enable AppsFlyer to validate the clicks and make sure that the click information hasn't been manipulated by fraudsters.

- Validated clicks are recorded, and attributed to the ad network
- Invalidated clicks are rejected and:
  - Are aggregated in Protect360 reports made available to the ad network (not advertisers).
  - Do not impact the conversion rate of the ad network
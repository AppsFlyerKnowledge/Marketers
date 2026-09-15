---
title: "InCost API for ad networks"
excerpt: "InCost API, part of AppsFlyer ROI360, lets ad networks programmatically send advertising cost data to AppsFlyer to provide advertisers with aggregate cost data."
---
InCost API, part of AppsFlyer ROI360, lets ad networks programmatically send advertising cost data to AppsFlyer. Doing so provides advertisers with aggregate cost data and lets them understand the true impact of your network.

## About InCost API

InCost API is the optimal solution for ad networks to send cost data to AppsFlyer. Ad network partners send detailed advertising cost data to AppsFlyer using the API. AppsFlyer ingests and processes the data, and makes it available to advertisers and partners via dashboards and reports.

#### Benefits

- Help your customers understand the true impact of your network with frictionless cost reporting. Without cost data, your customers are missing a crucial piece of the measurement puzzle and can't accurately measure ROAS. As such, they may mistakenly invest in other media sources, negatively impacting your bottom line.
- Prove your ROI with a solution that guarantees accurate, complete, and real-time cost measurement.
- InCost API is quick and simple to deploy, and the impact is almost immediate. You also get complete control over how and when you send the data, including the ability to send cost data for up to 90 days back.
- InCost API supports all campaign pricing models; not just CPI (which is the only model available when sending cost by click).
- Stand out in the AppsFlyer Partner Marketplace with a “Cost” badge that indicates this is a feature you support.

## Implementing InCost API

> 📘 Prerequisites
>
> For InCost API eligibility, your ad network requires:
>
> - That 90% of campaigns contain the Campaign ID in attribution.
> - The ability to send data at least 6 times per day for increased data freshness. The specific times are up to the ad network.
> - [If the ad network updates data retroactively] The ability to send data for the last 7 days every time, for increased data completion.

**To implement InCost API and start sending cost data to AppsFlyer**:

- Follow the steps in the following table.

| Step # | Action |
| --- | --- |
| 1 | Apply for InCost:<br />1. In AppsFlyer, from the top menu, select **Help** \> **Contact our team**.<br />   <br />   The Partner assistant widget opens.<br />2. Select **Enabling cost measurement** and submit your information.<br />   <br />   Once submitted, a ticket opens and an AppsFlyer partner solution engineer will contact you. |
| 2 | Make sure campaign hierarchies (campaign ID, and optionally, adset ID and ad ID) are included on your attribution links for more than 90% of your traffic. |
| 3 | Get the AppsFlyer [API token](/docs/managing-appsflyer-tokens) from the AppsFlyer dashboard. |
| 4 | Give the API token to your developer to use in the API authorization header and ask them to follow [their instructions](https://dev.appsflyer.com/hc/reference/incost-overview) to implement the 3 API methods:<br />1. [Get app list](https://dev.appsflyer.com/hc/reference/app-list-ad-nets-api-get).<br />2. [InCost upload](https://dev.appsflyer.com/hc/reference/incost-uploader-post): Tell the developer what [fields to populate the JSON](/docs/incost-api-for-ad-networks#fields-for-incost-upload-json) with:   - Mandatory fields must be populated. Meaning, don't send empty fields. <br />   - Media source is restricted to media sources associated with (registered under) your ad network account. Get the list from your partner development manager.<br />   - Take into consideration the app [timezone](/docs/about-data-freshness-and-timezone-support#appspecific-time-zone) (as reported via the Get app permission list API) to align cost data dates with that of the app.<br />   - If there are fields that are not part of your campaign cost reporting hierarchy, don’t include them. For example, adset ID, asset name, ad ID, ad name.<br />3. [Get job status](https://dev.appsflyer.com/hc/reference/incost-jobstatus-get). |
| 5 | Test the integration:<br />1. In the ticket thread (from step 1), notify AppsFlyer that the API implementation is complete and get permissions for the following apps which can be used to test the API without using real data:<br />   - com.cost.app<br />   - id888123456<br />2. In AppsFlyer, from the side menu, select **Collaborate** \> **Partner Marketplace**, and select the partner.<br />3. Click **Set up integration**.<br />4. Select 1 of the test apps.<br />5. Open the integrated partner **Cost** tab.<br />6. Turn on the **Get Cost Data** toggle.<br />7. Click **Save Cost**.<br />8. Click **Test Connection.**<br />   <br />   The API is active. |
| 6 | In the ticket thread (from step 1), confirm with AppsFlyer that your integration is operational. |
| 7 | Make sure your advertisers enable [get cost data](/docs/set-up-an-integrated-partner#cost-tab) in the cost tab of their AppsFlyer integrated partner page. Then they'll begin to receive cost data. |

### Fields for InCost Upload JSON

| Field | Mandatory | Remarks |
| --- | --- | --- |
| date | Yes | - Spend date<br />- Format: `YYYY-MM-DD`<br />- Example:`2019-12-30` |
| app\_id | Yes | - The app ID as it appears in the AppsFlyer platform<br />- Format: String up to 250 characters<br />- Example: Android:`com.app.name`, iOS: `id123456789` |
| media\_source | Yes | - Network name (ID) displaying the ad associated with your ad network partner account in AppsFlyer<br />- Format: String 50 characters<br />- Example: `network_int` |
| af\_prt | No\* | - Required for agency attribution and cost data. <br />- Agency name as it displays on the attribution link and is associated with the agency account in AppsFlyer. <br />- Format: String 50 characters <br />- Example: `agencya`<br />- If cost data is resent for the same dates and `af_prt` is included in a subsequent API call when it was absent in the original, resulting in duplicated cost data. |
| campaign\_id | Yes | - Must be identical to the `af_c_id` param sent on the attribution link<br />- Empty string not permitted<br />- Format: String 24 characters<br />- Example: `123abc` |
| campaign\_name | Yes | - Format: String 100 characters<br />- Example: `my_campaign123` |
| adset\_id | No\* | - Required if you send `adset_name`<br />- Must be identical to the `af_adset_id` param sent on the attribution link<br />- If your cost reporting does not support `adset_id`, never send it<br />- Format: String 24 characters<br />- Example: `123A` |
| adset\_name | No | - If you send this field, you must also send `adset_id`<br />- Format: String 100 characters<br />- Example:`my_adset_name` |
| ad\_id | No\* | - Required if you send `ad_name`.<br />- This field must be identical to the `af_ad_id` param sent on the attribution link<br />- If your cost reporting does not support `adset_id`, never send it<br />- Format: String 24 characters<br />- Example:`123AB` |
| site\_id | No | - Unique ID that identifies the publisher that displays the ad.<br />- Format: String 24 characters. |
| ad\_name | No | - If you send this field, you must also send `ad_id`<br />- Format: String 100 characters<br />- Example:`Ad-name` |
| geo | No | - The country you recorded as associated with the cost<br />- Where possible, this should represent the country where the ad was displayed<br />- Format: ISO 3166 2-character country code<br />- Example:`US, CN, ZA` |
| currency | Yes | - Spend currency type<br />- Format: ISO 4217 3-character currency code<br />- Example:`USD, EUR, ZAR` |
| spend | Yes | - Spend amount using the specified currency <br />- Five digits allowed after the decimal point<br />- The value 0 (zero) is permitted<br />- Negative values are NOT permitted<br />- Don't send `,` delimiters<br />- Don't send values in quotation marks. <br />- Format: Decimal number<br />- Example values: `1` `1.2` `1234.20` |
| channel | No | - Must be identical to the `af_channel`param sent on the attribution link<br />- Format: String 20 chars<br />- Example:`my_channel` |
| keywords | No | - Format: String 100 chars<br />- Example:`abc app` |
| reported\_clicks | No | - Number of clicks reported by the network for this record.<br />- Format: Non-negative integer.<br />- Example: `150`<br />- Optional. If empty or omitted, reported as 0.<br />- Decimal or negative values are rejected (error 422: `Reported clicks can be positive integer`). |
| reported\_impressions | No | - Number of impressions reported by the network for this record.<br />- Format: Non-negative integer.<br />- Example: `1000`<br />- Optional. If empty or omitted, reported as 0.<br />- Decimal or negative values are rejected (error 422: `Reported impression can be positive integer`). |
| \* See the remarks column, as in some cases you must send this field. | | |
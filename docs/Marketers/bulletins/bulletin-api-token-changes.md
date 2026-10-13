---
title: "Bulletin: API token changes"
excerpt: "Important update regarding the deprecation of API V1 tokens and the transition to secure JWT-based API V2 tokens."
table_of_contents: false
x-zendesk:
  id: 12399683708305
  url: https://support.appsflyer.com/hc/en-us/articles/12399683708305-Bulletin-API-token-changes
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 38
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials, Agencies]
  labels: [Agencies, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2023-01-23T15:35:25Z'
  edited_at: '2023-09-21T10:43:51Z'
---
| **What's new** | To provide a more secure and reliable experience for API usage, the API V1 token, which was included in the API URLs, was deprecated in favor of the API V2 token, which is a JWT-based token that is passed in the header for bearer authorization.<br /><br />API V1 token and the APIs that use them are no longer available as of September 18, 2023. |
| --- | --- |
| **Effective date** | September 18, 2023 |
| **Prerequisites** | Only an admin can [retrieve the API V2 token](/docs/managing-appsflyer-tokens#retrieving-api-tokens) from the AppsFlyer dashboard. |
| **Who needs to update the API token?** | Both advertisers and agencies who are still using API token V1 need to update their tokens. |
| **How to find API V1 tokens** | Use the [Audit log](/docs/audit-log) to filter out any API V1 tokens still in use. You can then download the data to a CSV file:<br /><br />1. Go to the [Audit log dashboard](https://hq1.appsflyer.com/audit-reader/dashboard).<br />2. Type "API Token V1" in the search bar.<br />3. In the**Service** filter, select only **API calls**, and filter the results.<br />4. Click the Download icon from the top-right of the page.  <br />   Your CSV file is downloaded and includes your app ID, the service used, and the API call URL. |
| **Action required** | **Update the following APIs for the API V2 token:**<br /><br />1. Go to the [API token page](https://hq1.appsflyer.com/account/api-tokens).<br />2. Under API token V2.0, click the **Copy to clipboard** icon.<br />3. For each of the following APIs:<br />   * [Master API V2](https://dev.appsflyer.com/hc/reference/master_api_get)<br />   * [Aggregate Pull API V2](https://dev.appsflyer.com/hc/reference/overview-11)<br />   * [Raw Data Pull API V2](https://dev.appsflyer.com/hc/reference/overview-5)<br />   1. Replace the API V1 URL with the URL in the above documentation.<br />   2. Paste the token you copied into the Bearer authentication header.  <br />      ![token_v2_bearer.png](https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png)<br />   3. For the **OpenDSR API**, paste the token into the request bearer header:   <br />      `'Authorization': 'Bearer %AuthTokenV2%'` |
| **About the API tokens** | **Learn more about the API tokens:**<br /><br />* [Managing API tokens](/docs/managing-appsflyer-tokens)<br />  * [Master API](/docs/master-api-user-acquisition-metrics-via-api)<br />  * [Aggregate Pull API](/docs/pull-api-aggregate-data)<br />  * [Raw data](/docs/pull-api-raw-data)<br />  * [OpenDSR API](/docs/send-opendsr-api-requests#gdpr-request-format) |
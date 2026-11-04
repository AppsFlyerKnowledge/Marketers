---
title: 'Bulletin: API token changes'
metadata:
  keywords:
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2023-01-23T15:35:25Z'
  edited_at: '2023-09-21T10:43:51Z'
  id: 12399683708305
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/12399683708305-Bulletin-API-token-changes
---
| **What's new** | To provide a more secure and reliable experience for API usage, the API V1 token, which was included in the API URLs, was deprecated in favor of the API V2 token, which is a JWT-based token that is passed in the header for bearer authorization.<br /><br />API V1 token and the APIs that use them are no longer available as of September 18, 2023. |
| --- | --- |
| **Effective date** | September 18, 2023 |
| **Prerequisites** | Only an admin can <Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens#retrieve-tokens">retrieve the API V2 token</Anchor> from the AppsFlyer dashboard. |
| **Who needs to update the API token?** | Both advertisers and agencies who are still using API token V1 need to update their tokens. |
| **How to find API V1 tokens** | Use the <Anchor target="_blank" href="/marketers/docs/audit-log">Audit log</Anchor> to filter out any API V1 tokens still in use. You can then download the data to a CSV file:<ol><li>Go to the [Audit log dashboard](https://hq1.appsflyer.com/audit-reader/dashboard).</li><li>Type "API Token V1" in the search bar.</li><li>In the **Service** filter, select only **API calls**, and filter the results.</li><li>Click the Download icon from the top-right of the page.<br />Your CSV file is downloaded and includes your app ID, the service used, and the API call URL.</li></ol> |
| **Action required** | **Update the following APIs for the API V2 token:**<ol><li>Go to the <Anchor target="_blank" href="https://hq1.appsflyer.com/account/api-tokens">API token page</Anchor>.</li><li>Under API token V2.0, click the **Copy to clipboard** icon.</li><li>For each of the following APIs:<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/master_api_get">Master API V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">Aggregate Pull API V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">Raw Data Pull API V2</Anchor></li></ul><ol><li>Replace the API V1 URL with the URL in the above documentation.</li><li>Paste the token you copied into the Bearer authentication header.<br />![token_v2_bearer.png](https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png)</li><li>For the **OpenDSR API**, paste the token into the request bearer header:<br />`'Authorization': 'Bearer %AuthTokenV2%'`</li></ol></li></ol> |
| **About the API tokens** | **Learn more about the API tokens:**<ul><li><Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens">Managing API tokens</Anchor><ul><li><Anchor target="_blank" href="/marketers/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/pull-api-aggregate-data">Aggregate Pull API</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/pull-api-raw-data">Raw data</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/send-opendsr-api-requests#gdpr-request-format">OpenDSR API</Anchor></li></ul></li></ul> |
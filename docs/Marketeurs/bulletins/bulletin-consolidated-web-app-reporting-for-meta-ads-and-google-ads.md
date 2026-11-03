---
title: 'Bulletin: Consolidated Web+App reporting for Meta Ads and Google Ads'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-10-05T12:17:10Z'
  edited_at: '2025-10-23T11:50:56Z'
  id: 39686956300433
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/39686956300433-Bulletin-Consolidated-Web-App-reporting-for-Meta-Ads-and-Google-Ads
---
| Section | Details |
| --- | --- |
| **What's new** | <ul><li>Any attribution to `metaweb_int` will now be reported as `Facebook Ads`.</li><li>Any attribution to `googleads_int` will now be reported as `googleadwords_int`.</li><li>The change only impacts new attributions. Existing attribution isn't changed retroactively.</li><li>This change applies across all reporting tools — including dashboards and raw data exports.</li><li>The translation to the “official” media source (e.g., Facebook Ads, Google Adwords\_int) automatically **occurs on the back end**.</li><li>The complete web cost of Meta Web and Google Web is reported in the dashboard and Cost ETL under the main PID = `facebook_int` and `googleadwords_int`, respectively.</li></ul> |
| **General Availability date** | November 02, 2025 |
| **Why should you care?** | The consolidation provides holistic reporting of ALL your campaigns from a specific network, such as Meta or Google, including full mobile and web cost reporting. |
| **What you need to do** | <ul><li>**No change to the campaign setting process**. Continue using the original PIDs (`metaweb_int` and `googleads_int`). These ensure AppsFlyer routes postbacks correctly via the appropriate web integrations.</li><li>**In raw data tools:**<ul><li>the `original_url` field will still display the original PID used in the ad,</li><li>the attribution media source fields will reflect the updated naming.</li></ul></li><li>**To get the web cost** include the campaign ID in the attribution link to get the web cost from Meta Web and Google Web,</li></ul> |
| **Best practices** | <ul><li>Include campaign type in campaign names to simplify classification.</li><li>To enable full cost reporting for web campaigns, connect your network account under the “Cost” tab of the respective main integration (Facebook Ads, googleadwords\_int).</li></ul> |
| **Future support** | <ul><li>AppsFlyer plans to introduce a new dimension (`engagement_platform_group`) to indicate campaign type (App or Web).</li><li>Upcoming PIDs for CAPI integration will include:</li></ul><ul><li>`snapweb_int` → mapped to **snapchat\_int**</li><li>`tiktokweb_int` → mapped to **tiktokglobal\_int**</li><li>`twitterweb_int` → mapped to **Twitter**</li></ul>**<span id="h_01K6T5WZKJ2XP34V3T64TWG153"></span>Note**<br />These mappings are already active — any attributions using the above PIDs are automatically translated to the main SRN PIDs, even prior to full integration support. |
---
title: "Bulletin: Consolidated Web+App reporting for Meta Ads and Google Ads"
table_of_contents: false
x-zendesk:
  id: 39686956300433
  url: https://support.appsflyer.com/hc/en-us/articles/39686956300433-Bulletin-Consolidated-Web-App-reporting-for-Meta-Ads-and-Google-Ads
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: []
  promoted: false
  comments_disabled: false
  created_at: '2025-10-05T12:17:10Z'
  edited_at: '2025-10-23T11:50:56Z'
---
This bulletin outlines the consolidation of Web and App reporting for Meta Ads and Google Ads, providing holistic reporting of all campaigns from specific networks.

| Section | Details |
| --- | --- |
| **What's new** | - Any attribution to `metaweb_int` will now be reported as `Facebook Ads`.<br />- Any attribution to `googleads_int` will now be reported as `googleadwords_int`.<br />- The change only impacts new attributions. Existing attribution isn't changed retroactively.<br />- This change applies across all reporting tools — including dashboards and raw data exports.<br />- The translation to the “official” media source (e.g., Facebook Ads, Google Adwords\_int) automatically **occurs on the back end**.<br />- The complete web cost of Meta Web and Google Web is reported in the dashboard and Cost ETL under the main PID = `facebook_int` and `googleadwords_int`, respectively. |
| **General Availability date** | November 02, 2025 |
| **Why should you care?** | The consolidation provides holistic reporting of ALL your campaigns from a specific network, such as Meta or Google, including full mobile and web cost reporting. |
| **What you need to do** | - **No change to the campaign setting process**. Continue using the original PIDs (`metaweb_int` and `googleads_int`). These ensure AppsFlyer routes postbacks correctly via the appropriate web integrations.<br />- **In raw data tools:** <br />  - the `original_url` field will still display the original PID used in the ad,<br />  - the attribution media source fields will reflect the updated naming.<br />- **To get the web cost** include the campaign ID in the attribution link to get the web cost from Meta Web and Google Web, |
| **Best practices** | - Include campaign type in campaign names to simplify classification.<br />- To enable full cost reporting for web campaigns, connect your network account under the “Cost” tab of the respective main integration (Facebook Ads, googleadwords\_int). |
| **Future support** | - AppsFlyer plans to introduce a new dimension (`engagement_platform_group`) to indicate campaign type (App or Web).<br />- Upcoming PIDs for CAPI integration will include:<br />  <br />  <br />  - `snapweb_int` → mapped to **snapchat\_int**<br />  - `tiktokweb_int` → mapped to **tiktokglobal\_int**<br />  - `twitterweb_int` → mapped to **Twitter**<br />#### Note<br />These mappings are already active — any attributions using the above PIDs are automatically translated to the main SRN PIDs, even prior to full integration support. |
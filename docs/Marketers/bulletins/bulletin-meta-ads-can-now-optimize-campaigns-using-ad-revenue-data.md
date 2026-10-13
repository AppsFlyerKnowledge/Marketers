---
title: "Bulletin: Meta ads can now optimize campaigns using ad revenue data"
excerpt: "Meta ads now supports optimizing Android App promotion campaigns using the AdImpression ad revenue postback event."
table_of_contents: false
x-zendesk:
  id: 29376794104209
  url: https://support.appsflyer.com/hc/en-us/articles/29376794104209-Bulletin-Meta-ads-can-now-optimize-campaigns-using-ad-revenue-data
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 8
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-michael-talapov, Marketers, ROI360]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2024-10-21T09:02:43Z'
  edited_at: '2025-01-13T08:06:56Z'
---
Meta ads can now optimize your Android App promotion campaigns using the ad revenue postback event **AdImpression**.

| | |
| --- | --- |
| **What's new** | Meta ads can now optimize your Android App promotion campaigns using the ad revenue postback event **AdImpression**. |
| **Update date** | January 1, 2025 |
| **What you need to know** | - Currently, optimization via the **Adimpression** event is available for Android app promotion campaigns.<br />- When grayed out, [eligibility criteria may not be met](https://www.facebook.com/business/help/571188993373447?id=561906377587030).<br />- The Adimpression event is mapped to the af\_ad\_revenue event, which is available for plans with an [ROI360 advanced subscription](/docs/roi360-guide-cost-and-revenue-data) only. Additionally, you need the [impression-level (via SDK) ad revenue or Impression-level (via SDK) with device-level (via S2S API) integration type](/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution).<br />  - Non-ROI360 plans can send ad revenue data using other event names. |
| **What you need to do** | - For ROI360 customers, use the [impression-level (via SDK) ad revenue or Impression-level (via SDK) with device-level (via S2S API) integration type](/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution).<br />- [Map the af\_ad\_revenue event to **Adimpression**](/docs/meta-ads-in-app-event-mapping#mapping-ad-revenue-data-for-campaign-optimization). |
| **Additional resources** | See the [Meta Business Help Center](https://www.facebook.com/business/help/330074040129013) to learn more about how to maximize the value of conversions as a performance goal for app ads in Meta Ads Manager. |
---
title: "Bulletin: Unspecified engagement type"
table_of_contents: false
x-zendesk:
  id: 30795194720785
  url: https://support.appsflyer.com/hc/en-us/articles/30795194720785-Bulletin-Unspecified-engagement-type
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 6
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-moran-davida, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2024-12-09T15:17:50Z'
  edited_at: '2025-02-05T10:02:08Z'
---
| What’s new? | To standardize reporting when `engagement_type` is missing or mismatched, we are introducing `click_unspecified` or `impression_unspecified`as the default values in raw data reports and dashboards. |
| --- | --- |
| What’s the impact | **Conversions**:  <br />Starting from the effective date, the `engagement_type` will no longer be reported as empty but will default to `click_unspecified` or `impression_unspecified`, depending on the touch type (i.e., click or impression).  <br />  <br />**In-app events and sessions**:  <br />The new values will apply only to in-app events and sessions attributed to conversion events recorded after the effective date. Those attributed to conversion events recorded before the effective date will remain unaffected. |
| Effective date | December 9,2024 |
| What you should know | All information relating to EET can be found in the KB:<ul><li>[Enriched Engagement Types](/docs/about-enriched-engagement-types)</li><li>[Enriched engagement types guide for partners](/docs/enriched-engagement-types-guide-for-ad-networks)</li></ul>For immediate impact of the introduction of EET see the bulletin:<ul><li>[Enhanced engagement types visibility](/docs/bulletin-enhanced-engagement-types-visibility)</li></ul> |
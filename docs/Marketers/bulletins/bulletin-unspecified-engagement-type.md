---
title: 'Bulletin: Unspecified engagement type'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-12-09T15:17:50Z'
  edited_at: '2025-02-05T10:02:08Z'
  id: 30795194720785
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/30795194720785-Bulletin-Unspecified-engagement-type
---
| What’s new? | To standardize reporting when `engagement_type` is missing or mismatched, we are introducing `click_unspecified` or `impression_unspecified`as the default values in raw data reports and dashboards. |
| --- | --- |
| What’s the impact | **Conversions**:  <br />Starting from the effective date, the `engagement_type` will no longer be reported as empty but will default to `click_unspecified` or `impression_unspecified`, depending on the touch type (i.e., click or impression).  <br />  <br />**In-app events and sessions**:  <br />The new values will apply only to in-app events and sessions attributed to conversion events recorded after the effective date. Those attributed to conversion events recorded before the effective date will remain unaffected. |
| Effective date | December 9,2024 |
| What you should know | All information relating to EET can be found in the KB:<ul><li><Anchor target="_blank" href="/marketers/docs/about-enriched-engagement-types">Enriched Engagement Types</Anchor></li><li><Anchor target="_blank" href="/partners/docs/enriched-engagement-types-guide-for-ad-networks">Enriched engagement types guide for partners</Anchor></li></ul>For immediate impact of the introduction of EET see the bulletin:<ul><li><Anchor target="_blank" href="/marketers/docs/bulletin-enhanced-engagement-types-visibility">Enhanced engagement types visibility</Anchor></li></ul> |
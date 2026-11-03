---
title: 'Bulletin: Enhanced engagement types visibility'
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
  created_at: '2024-10-29T15:52:59Z'
  edited_at: '2026-05-04T09:16:12Z'
  id: 29614354758545
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/29614354758545-Bulletin-Enhanced-engagement-types-visibility
---
| **What’s new?** | Enriched Engagement Types (EET) will be visible to ALL accounts. |
| --- | --- |
| **What’s the impact** | <ul><li>Engagement types will be reported for all supporting networks (both click networks and SRNs).</li><li>The `engagement_type`  parameter when missing or mismatched <Anchor target="_blank" href="/marketers/id/docs/bulletin-unspecified-engagement-type">will default to `click_unspecified` or `impression_unspecified`</Anchor>.</li><li>Engaged views and engaged clicks will have <Anchor target="_blank" href="/marketers/id/docs/about-enriched-engagement-types#attribution-model-with-enriched-engagement-types-beta">the same attribution priority</Anchor> as clicks, ensuring consistency across all ad networks.</li><li>No impact on attribution and install count.</li><li>(Only for non-SRN <Anchor target="_blank" href="/marketers/id/docs/about-enriched-engagement-types#networks-that-report-engagement-types">supporting networks</Anchor>) New lookback window sliders (in the Integration tab) for engaged clicks and engaged views, with a 7-day default for existing integrations and 2-day default for new integrations.</li><li>For SRN supporting networks, the lookback window is taken from the click-through lookback window configured in the partner **Intergration** tab.</li><li>You can view the **Engagement type** dimension in the dashboards.</li><li>`engagement_type` is included in raw data reports if selected by the advertiser</li><li>Engaged views are reported with `attributed_touch_type=impression` (also applies to Google Ads and TikTok)</li><li>Starting on November 19, a shift may occur from clicks to engaged views.<ul><li>A decrease in `attributed_touch_type=click`</li><li>An increase in `attributed_touch_type=impression`</li></ul></li><li>Engaged views are measured and reported even if the **view-through** toggle is turned off. To identify those impressions as engaged views use the `engagement_type=engaged_view` metric in dashboards and raw data reports instead of relying solely on `attributed_touch_type`.</li><li>Total impressions include both engaged views and regular view. To calculate the IPM, you must **subtract engaged views from total impressions** because engaged views are a subset of impressions, and double-counting them would inflate the impression count.</li><li>Installs will always be attributed to the strongest touch type. If both view and engaged view are being reported, the install will be attributed to the engaged view (the view will not be recorded as a contributor, because it’s from the same campaign).</li></ul> |
| **Effective date** | November 2024 |
| **Supporting ad networks** | Currently, only allowed networks can report engagement types to AppsFlyer. |
| **What you should know** | All information relating to EET can be found in the KB:<ul><li><Anchor target="_blank" href="/marketers/id/docs/about-enriched-engagement-types">Enriched Engagement Types</Anchor></li><li><Anchor target="_blank" href="/partners/id/docs/enriched-engagement-types-guide-for-ad-networks">Enriched engagement types guide for partners</Anchor></li></ul> |
---
title: "Bulletin: Apple Ads adds timestamps to all attribution claims"
table_of_contents: false
x-zendesk:
  id: 50216486847249
  url: https://support.appsflyer.com/hc/en-us/articles/50216486847249-Bulletin-Apple-Ads-adds-timestamps-to-all-attribution-claims
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
  content_tags: []
  labels: [apple ads]
  promoted: false
  comments_disabled: true
  created_at: '2026-08-26T09:02:50Z'
  edited_at: '2026-08-26T15:46:17Z'
---
| Section | Details |
| --- | --- |
| What's new | As of September 1, 2026:<ul><li>Apple's AdServices API adds an engagement timestamp to all iOS attribution claims, including those that previously lacked one. AppsFlyer uses this timestamp to apply your configured lookback window and last-touch attribution rules to these claims.</li><li>For ad groups with age or gender targeting, Apple will return an attribution payload of false, and these engagements cannot be attributed to Apple Ads in AppsFlyer.</li></ul> |
| Effective date | September 1, 2026 |
| What you should know | <ul><li>For most Apple Ads campaigns, attribution accuracy improves because engagements are now evaluated against your advertiser-defined lookback window rather than the previous default windows, including engagements from non-consenting users who previously were claimed without timestamps.</li><li>Separately, ad groups with age or gender targeting will return a false attribution payload. Engagements from those ad groups are not claimed by Apple Ads and therefore cannot be attributed to them.</li></ul> |
| What you should do | No action is required. Your Apple Ads integration reflects this change automatically. If you run age or gender targeted ad groups, review your Apple Ads reporting after September 1 to understand any change in attributed conversions. |

#### See also

* [Apple Ads integration setup](/docs/apple-ads-integration-setup)

<div data-zendesk-anchors="h_01M0YZSHS593T92XC58PR1FXYY=see-also" />

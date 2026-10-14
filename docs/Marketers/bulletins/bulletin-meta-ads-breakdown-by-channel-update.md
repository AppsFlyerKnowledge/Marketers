---
title: "Bulletin: Meta ads breakdown by channel update"
x-zendesk:
  id: 49465306965393
  url: https://support.appsflyer.com/hc/en-us/articles/49465306965393-Bulletin-Meta-ads-breakdown-by-channel-update
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
  comments_disabled: true
  created_at: '2026-08-04T08:33:09Z'
  edited_at: '2026-08-04T10:27:25Z'
---
| Section | Details |
| --- | --- |
| **What's new** | Meta now requires per-ad-account opt-in for the `impression_device` breakdown, effective August 6, 2026. Because Meta's reporting API cannot return cost data broken down by both geo and channel in the same query, accounts without this opt-in will see incomplete data:<ul><li>Channel-level cost data may be missing from the default My Dashboards view</li><li>Meta's data may be missing from Cost ETL</li></ul>The same limitation also affects creative performance data broken down by channel. |
| **Effective date** | August 6, 2026 |
| **What you need to know** | Meta applies this opt-in automatically on AppsFlyer customer accounts. You do not need to take any action before August 6.<ul><li>If your cost data broken down by channel, or your creative performance data broken down by channel, is missing after August 6, the automatic opt-in has not yet applied to your account.</li></ul> |
| **What you need to do** | Take the following steps:<ol><li>After August 6, check your cost data broken down by channel (My Dashboards) and your creative performance data broken down by channel.</li><li>If you notice a gap, contact Meta directly for guidance on enabling the opt-in, or reach out to your AppsFlyer representative for help.</li><li>Once the opt-in applies to your account, your data will catch up automatically through backfill shortly after.</li><li>You can also check directly in Ads Manager whether Impression Device is already enabled for the account. See [Check Impression Device in Ads Manager](#check-impression-device-in-ads-manager) below for the steps.</li></ol> |

## Check Impression Device in Ads Manager

To check whether Impression Device is already enabled for an ad account:

1. Go to [Ads Manager](https://adsmanager.facebook.com/) and select **Settings**.

[![Ads Manager toolbar showing the Settings button](https://files.readme.io/64c9ac8d571e88bfd098b542456886cc64d6320bf3856721335a077c4f19e5b5-49469436208529.png)](https://files.readme.io/64c9ac8d571e88bfd098b542456886cc64d6320bf3856721335a077c4f19e5b5-49469436208529.png)

2. In the Create view panel, select **Delivery**.
3. Under Delivery, find **Additional Breakdowns**.
4. Under Additional Breakdowns, check whether the plus symbol next to **Impression Device** (`impression_device`) is already selected. If it is, the opt-in is active for this account.

[![Additional Breakdowns panel in Ads Manager with plus icons for Time of Day, Impression Device, and Frequency Value](https://files.readme.io/71eb7c75a3f49a82e98522fcf418acbc6ef378eeda5f093535a168aa8505ade1-49469462456081.png)](https://files.readme.io/71eb7c75a3f49a82e98522fcf418acbc6ef378eeda5f093535a168aa8505ade1-49469462456081.png)

<div data-zendesk-anchors="h_01KZ63J08GPADE2AH0KV9NNESC=check-impression-device-in-ads-manager" />

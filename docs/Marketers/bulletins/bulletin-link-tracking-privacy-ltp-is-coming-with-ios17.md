---
title: "Bulletin: Link tracking Privacy (LTP) is coming with iOS17"
excerpt: "An overview of how Apple's Link Tracking Privacy (LTP) in iOS17 affects AppsFlyer parameters, redirection, deep linking, and web-to-app flows."
x-zendesk:
  id: 18730398273553
  url: https://support.appsflyer.com/hc/en-us/articles/18730398273553-Bulletin-Link-tracking-Privacy-LTP-is-coming-with-iOS17
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 32
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, Smart Banners and Scripts]
  labels: [Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2023-09-21T08:37:39Z'
  edited_at: '2023-09-21T12:11:54Z'
---
iOS17 will detect and remove parameters identified as tracking parameters from links users share in built-in applications: Mail, Messages, and Safari's Private Browsing mode.

We performed internal testing to see how LTP affects OneLink. Our findings suggest that none of AppsFlyer parameters were removed. These are the results of our tests:

### Parameter Impact Analysis

| Parameter Status | Parameters |
| --- | --- |
| **Removed by LTP** | - `gclid` - Google ads / Analytics ID<br />- `fbclid` - Facebook advertising ID |
| **Untouched by LTP** | - UTM parameters |
| **AppsFlyer attribution parameters (Untouched)** | - `pid`<br />- `c`<br />- `Is_regtargeting`<br />- `af_channel`<br />- `af_adset`<br />- `af_ad`<br />- `af_sub1-10`<br />- `af_inactivity_window`<br />- `af_click_lookback`<br />- `af_cost_value`<br />- `af_cost_currency` |
| **AppsFlyer redirection parameters (Untouched)** | - `af_dp`<br />- `deep_link_value`<br />- `af_deep_link_sub1-10`<br />- `af_web_dp`<br />- `af_ios_url`<br />- `af_android_url`<br />- `af_xp` |

### Effective Date

The date of the public release of iOS17 (September 18, 2023)

### What this impacts

* **Redirection and Deep linking**
  Redirection and deep linking are unlikely to be impacted due to this change. The only case where deep linking may be affected is when attribution relies on GCLID or FBCLID.
* **Web-2-app**
  As LTP only applies to Safari’s private browsing mode, we expect minimal impact on attribution for web-to-app flows. However, when the user is in Safari’s private browsing mode, the GCLID and FBCLID parameters, which LTP removes, will not get mapped by the Smart script.
* **Email, SMS, and notifications**
  Apple built-in applications, such as Mail and Messages will block the relevant tracking parameters mentioned above. Therefore, using links in such campaigns may result in losing user-level data. Furthermore, some of the Email Service Provider (ESP) statistics identifiers might be blocked as part of this change, potentially impacting email campaign statistics. We advise you to contact your ESP to understand the impact fully.
---
title: "Bulletin: Link tracking Privacy (LTP) is coming with iOS17"
table_of_contents: false
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
| **What's new** | iOS17 will detect and remove parameters identified as tracking parameters from links users share in built-in applications: Mail, Messages, and Safari's Private Browsing mode.<br /><br />We performed internal testing to see how LTP affects OneLink. Our findings suggest that none of AppsFlyer parameters were removed. These are the results of our tests:<br /><br />**The following parameters are removed by LTP**<br /><br />- `gclid` - Google ads / Analytics ID<br /><br />- `fbclid` - Facebook advertising ID<br /><br />**The following parameters are untouched by LTP**<br /><br />- UTM parameters<br /><br />**AppsFlyer attribution parameters:**<br /><br />- `pid`<br /><br />- `c`<br /><br />- `Is_regtargeting`<br /><br />- `af_channel`<br /><br />- `af_adset`<br /><br />- `af_ad`<br /><br />- `af_sub1-10`<br /><br />- `af_inactivity_window`<br /><br />- `af_click_lookback`<br /><br />- `af_cost_value`<br /><br />- `af_cost_currency`<br /><br />**AppsFlyer redirection parameters**<br /><br />- `af_dp`<br /><br />- `deep_link_value`<br /><br />- `af_deep_link_sub1-10`<br /><br />- `af_web_dp`<br /><br />- `af_ios_url`<br /><br />- `af_android_url`<br /><br />- `af_xp` |
| --- | --- |
| **Effective date** | The date of the public release of iOS17 (September 18, 2023) |
| **What this impacts** | **Redirection and Deep linking**<br /><br />Redirection and deep linking are unlikely to be impacted due to this change. The only case where deep linking may be affected is when attribution relies on GCLID or FBCLID.<br /><br />**Web-2-app**<br /><br />As LTP only applies to Safari’s private browsing mode, we expect minimal impact on attribution for web-to-app flows. However, when the user is in Safari’s private browsing mode, the GCLID and FBCLID parameters, which LTP removes, will not get mapped by the Smart script.<br /><br />**Email, SMS, and notifications**<br /><br />Apple built-in applications, such as Mail and Messages will block the relevant tracking parameters mentioned above. Therefore, using links in such campaigns may result in losing user-level data. Furthermore, some of the Email Service Provider (ESP) statistics identifiers might be blocked as part of this change, potentially impacting email campaign statistics. We advise you to contact your ESP to understand the impact fully. |
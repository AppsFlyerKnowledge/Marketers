---
title: 'Bulletin: Link tracking Privacy (LTP) is coming with iOS17'
metadata:
  keywords:
    - Marketers
    - Smart Banners and Scripts
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2023-09-21T08:37:39Z'
  edited_at: '2023-09-21T12:11:54Z'
  id: 18730398273553
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/18730398273553-Bulletin-Link-tracking-Privacy-LTP-is-coming-with-iOS17
---
| **What's new** | iOS17 will detect and remove parameters identified as tracking parameters from links users share in built-in applications: Mail, Messages, and Safari's Private Browsing mode.<br /><br />We performed internal testing to see how LTP affects OneLink. Our findings suggest that none of AppsFlyer parameters were removed. These are the results of our tests:<br /><br />**<span id="h_01HAVEDAEFTDVGS1SXBD7NEJFE"></span>The following parameters are removed by LTP**<ul><li>`gclid` - Google ads / Analytics ID</li></ul><ul><li>`fbclid` - Facebook advertising ID</li></ul>**<span id="h_01HAVEDAEFN7XEPK3TNCSZRAMW"></span>The following parameters are untouched by LTP**<ul><li>UTM parameters</li></ul>**<span id="h_01HAVEDAEFMGD1SFYRJNXE9JBE"></span>AppsFlyer attribution parameters:**<ul><li>`pid`</li></ul><ul><li>`c`</li></ul><ul><li>`Is_regtargeting`</li></ul><ul><li>`af_channel`</li></ul><ul><li>`af_adset`</li></ul><ul><li>`af_ad`</li></ul><ul><li>`af_sub1-10`</li></ul><ul><li>`af_inactivity_window`</li></ul><ul><li>`af_click_lookback`</li></ul><ul><li>`af_cost_value`</li></ul><ul><li>`af_cost_currency`</li></ul>**<span id="h_01HAVEDAEFEFZ1ZCPAZ05C3AWW"></span>AppsFlyer redirection parameters**<ul><li>`af_dp`</li></ul><ul><li>`deep_link_value`</li></ul><ul><li>`af_deep_link_sub1-10`</li></ul><ul><li>`af_web_dp`</li></ul><ul><li>`af_ios_url`</li></ul><ul><li>`af_android_url`</li></ul><ul><li>`af_xp`</li></ul> |
| --- | --- |
| **Effective date** | The date of the public release of iOS17 (September 18, 2023) |
| **What this impacts** | **<span id="h_01HAVEDAEFE7K3FT7RNA0FANHV"></span>Redirection and Deep linking**<br /><br />Redirection and deep linking are unlikely to be impacted due to this change. The only case where deep linking may be affected is when attribution relies on GCLID or FBCLID.<br /><br />**<span id="h_01HAVEDAEFAB2AGW54XW52YAXJ"></span>Web-2-app**<br /><br />As LTP only applies to Safari’s private browsing mode, we expect minimal impact on attribution for web-to-app flows. However, when the user is in Safari’s private browsing mode, the GCLID and FBCLID parameters, which LTP removes, will not get mapped by the Smart script.<br /><br />**<span id="h_01HAVEDAEFTC8QRKTZCQZSC8G6"></span>Email, SMS, and notifications**<br /><br />Apple built-in applications, such as Mail and Messages will block the relevant tracking parameters mentioned above. Therefore, using links in such campaigns may result in losing user-level data. Furthermore, some of the Email Service Provider (ESP) statistics identifiers might be blocked as part of this change, potentially impacting email campaign statistics. We advise you to contact your ESP to understand the impact fully. |
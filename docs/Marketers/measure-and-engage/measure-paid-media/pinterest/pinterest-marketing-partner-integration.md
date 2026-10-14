---
title: Pinterest Marketing Partner Integration
excerpt: >-
  Enable Pinterest Marketing Partners (PMPs) to receive install data for users
  attributed to Pinterest.
metadata:
  keywords:
    - Pinterest
    - PMP
    - Advertisers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2016-12-08T16:05:33Z'
  edited_at: '2026-08-14T16:22:39Z'
  id: 217408966
  locale: en-us
  section: Pinterest
  section_id: 6551388216337
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/217408966-Pinterest-Marketing-Partner-Integration
---
Every PMP must be an official PMP and must also be approved by AppsFlyer on the back-end.

For AppsFlyer to send a postback to the PMP the af\_mp= parameter with the AppsFlyer account name as a value must be added to the attribution link.

**Example**

<Accordion title="Android">

```
https://app.appsflyer.com/com.king.candycrushsaga?pid=pinterest_int&clickid={click_id}
&af_adset={ad_group_name}&af_adset_id={ad_group_id}&af_ad={creative_name}&af_ad_id=
{creative_id}&af_siteid={publisher}&c={campaign_name}&af_c_id={campaign_id}&af_ad=
{ad_group_id}&af_ad_id={creative_id}&sha1_advertising_id={sha1_advertising_id}&tracking=
{limit_ad_tracking}&appid={app_id}&timestamp={click_timestamp}&af_mp=bidalgo
```

</Accordion>

<Accordion title="iOS">

```
https://app.appsflyer.com/id340954503?pid=pinterest_int&clickid={click_id}
&af_adset={ad_group_name}&af_adset_id={ad_group_id}&af_ad={creative_name}&af_ad_id=
{creative_id}&af_siteid={publisher}&c={campaign_name}&af_c_id={campaign_id}&af_ad=
{ad_group_id}&af_ad_id={creative_id}&sha1_advertising_id={sha1_advertising_id}&tracking=
{limit_ad_tracking}&appid={app_id}&timestamp={click_timestamp}&af_mp=bidalgo
```

</Accordion>

Supported PMP partners include:

* Bidalgo
* Bidsaas (Bidalgo)
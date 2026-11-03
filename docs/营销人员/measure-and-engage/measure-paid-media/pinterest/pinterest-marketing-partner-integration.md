---
title: Pinterest Marketing Partner Integration
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
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-12-08T16:05:33Z'
  edited_at: '2026-10-13T01:25:43Z'
  id: 217408966
  locale: zh-cn
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/zh-cn/articles/217408966
---
> **At a glance:** Enable Pinterest Marketing Partners (PMPs) to receive install data for users attributed to Pinterest.

Every PMP must be an official PMP and must also be approved by AppsFlyer on the back-end.

For AppsFlyer to send a postback to the PMP the af\_mp= parameter with the AppsFlyer account name as a value must be added to the attribution link.

> 📘 **Note**
>
> **Example**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```http
> https://app.appsflyer.com/com.king.candycrushsaga?pid=pinterest_int&clickid={click_id}
> &af_adset={ad_group_name}&af_adset_id={ad_group_id}&af_ad={creative_name}&af_ad_id=
> {creative_id}&af_siteid={publisher}&c={campaign_name}&af_c_id={campaign_id}&af_ad=
> {ad_group_id}&af_ad_id={creative_id}&sha1_advertising_id={sha1_advertising_id}&tracking=
> {limit_ad_tracking}&appid={app_id}&timestamp={click_timestamp}&af_mp=bidalgo
> ```
>
> </Tab>
>
> <Tab title="iOS">
>
> ```http
> https://app.appsflyer.com/id340954503?pid=pinterest_int&clickid={click_id}
> &af_adset={ad_group_name}&af_adset_id={ad_group_id}&af_ad={creative_name}&af_ad_id=
> {creative_id}&af_siteid={publisher}&c={campaign_name}&af_c_id={campaign_id}&af_ad=
> {ad_group_id}&af_ad_id={creative_id}&sha1_advertising_id={sha1_advertising_id}&tracking=
> {limit_ad_tracking}&appid={app_id}&timestamp={click_timestamp}&af_mp=bidalgo
> ```
>
> </Tab>
> </Tabs>
>

Supported PMP partners include:

* Bidalgo
* Bidsaas (Bidalgo)
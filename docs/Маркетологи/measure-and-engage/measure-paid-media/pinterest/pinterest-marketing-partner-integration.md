---
title: Интеграция с маркетинговыми партнерами Pinterest
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
  edited_at: '2026-08-18T00:31:54Z'
  id: 217408966
  locale: ru
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/ru/articles/217408966
---
> **At a glance:** Предоставьте маркетинговым партнерам Pinterest (PMP) возможность получать данные об установках пользователей, атрибутированных к Pinterest.

Каждый PMP должен быть официальным PMP, а также должен быть одобрен AppsFlyer на сервере.

Чтобы AppsFlyer отправил постбэк PMP, в ссылку атрибуции необходимо добавить параметр af\_mp= с именем аккаунта AppsFlyer в качестве значения.

> 📘 **Note**
>
> **Например**
>
>
> <Tabs>
> <Tab title="Android;">
>
> ```http
> http://app.appsflyer.com/com.king.candycrushsaga?pid=pinterest_int&clickid={click_id}
> &af_adset={ad_group_name}&af_adset_id={ad_group_id}&af_ad={creative_name}&af_ad_id=
> {creative_id}&af_siteid={publisher}&c={campaign_name}&af_c_id={campaign_id}&af_ad=
> {ad_group_id}&af_ad_id={creative_id}&sha1_advertising_id={sha1_advertising_id}&tracking=
> {limit_ad_tracking}&appid={app_id}&timestamp={click_timestamp}&af_mp=bidalgo
> ```
>
> </Tab>
>
> <Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">
>
> ```http
> http://app.appsflyer.com/id340954503?pid=pinterest_int&clickid={click_id}
> &af_adset={ad_group_name}&af_adset_id={ad_group_id}&af_ad={creative_name}&af_ad_id=
> {creative_id}&af_siteid={publisher}&c={campaign_name}&af_c_id={campaign_id}&af_ad=
> {ad_group_id}&af_ad_id={creative_id}&sha1_advertising_id={sha1_advertising_id}&tracking=
> {limit_ad_tracking}&appid={app_id}&timestamp={click_timestamp}&af_mp=bidalgo
> ```
>
> </Tab>
> </Tabs>
>

Поддерживаемые партнеры PMP:

* Bidalgo
* Bidsaas (Bidalgo)
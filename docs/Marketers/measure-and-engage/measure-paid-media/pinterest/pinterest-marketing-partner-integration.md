---
title: Integración de partners de marketing de Pinterest
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
  edited_at: '2026-08-22T00:30:00Z'
  id: 217408966
  locale: es
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/es/articles/217408966
---
> **At a glance:** Permite que los partners de marketing de Pinterest (PMP) reciban datos de las instalaciones de los usuarios atribuidas a Pinterest.

Cada PMP debe ser un PMP oficial y también debe ser aprobado por AppsFlyer en el backend.

Para que AppsFlyer envíe un postback al PMP, se debe agregar al enlace de atribución el parámetro af\_mp= con el nombre de la cuenta de AppsFlyer como valor.

> 📘 **Note**
>
> **Ejemplo**
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
> <Tab title="apps de iOS,">
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

Entre los partners de PMP admitidos se encuentran:

* Bidalgo
* Bidsaas (Bidalgo)
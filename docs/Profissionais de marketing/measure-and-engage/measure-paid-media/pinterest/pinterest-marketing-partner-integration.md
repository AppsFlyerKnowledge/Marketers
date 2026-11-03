---
title: Integração do parceiro de marketing do Pinterest
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
  edited_at: '2026-08-19T00:30:11Z'
  id: 217408966
  locale: pt
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/pt/articles/217408966
---
> **At a glance:** **Visão geral:** Permita que os Parceiros de Marketing do Pinterest (PMPs) recebam dados de instalação de usuários atribuídos ao Pinterest.

Cada PMP deve ser um PMP oficial e também deve ser aprovado pela AppsFlyer no back-end.

Para que a AppsFlyer envie um postback para o PMP, o parâmetro af\_mp= com o nome da conta da AppsFlyer como um valor deve ser adicionado ao link de atribuição.

> 📘 **Note**
>
> **Exemplo**
>
>
> <Tabs>
> <Tab title="Android iOS">
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
> <Tab title="Exemplo">
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

Os parceiros PMP apoiados incluem:

* Bidalgo
* Bidsaas (Bidalgo)
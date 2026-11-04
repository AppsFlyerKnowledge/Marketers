---
title: Intégration des partenaires marketing de Pinterest
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
  edited_at: '2024-08-19T14:54:30Z'
  id: 217408966
  locale: fr
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/fr/articles/217408966
---
> **En bref :** Pour autoriser les partenaires marketing de Pinterest (PMP) à recevoir les données d'installation des utilisateurs attribués à Pinterest.

Chaque PMP doit être un PMP officiel. Il doit également avoir été approuvé par AppsFlyer au niveau du back-end.

Pour que AppsFlyer envoie un postback au PMP, le paramètre *af\_mp=,* avec comme valeur le nom du compte AppsFlyer, doit être ajouté au lien d'attribution.

<div id="note" />

> 📄 **Exemple**
>
> <Tabs>
> <Tab title="Android">
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
> <Tab title="iOS">
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

Les partenaires PMP pris en charge incluent :

* Bidalgo
* Bidsaas (Bidalgo)
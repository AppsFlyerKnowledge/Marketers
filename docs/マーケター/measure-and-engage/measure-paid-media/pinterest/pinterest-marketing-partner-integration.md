---
title: Pinterest マーケティングパートナー統合
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
  edited_at: '2026-10-14T09:26:19Z'
  id: 217408966
  locale: ja
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/ja/articles/217408966
---
> **概要：** Pinterest マーケティングパートナー（PMP）が Pinterest に紐づくユーザーのインストールデータを受信できるようにします。

すべてのPMPは公式のPMPである必要があり、バックエンドのAppsFlyerによって承認されている必要があります。

AppsFlyerがPMPにポストバックを送信するには、AppsFlyerアカウント名を値とするaf\_mp=パラメーターを計測リンクに追加する必要があります。

> 📄 **例**
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

サポートされている PMP パートナーは次のとおりです。

* Bidalgo
* Bidsaas (Bidalgo)

<div data-zendesk-anchors="01JFSZQG46FGJJTK893PKSKA2W=%E4%BE%8B" />

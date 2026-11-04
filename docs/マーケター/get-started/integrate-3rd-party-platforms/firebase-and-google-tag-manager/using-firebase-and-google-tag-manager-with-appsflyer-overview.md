---
title: AppsFlyerでのFirebaseとGoogleタグマネージャーの活用｜概要
metadata:
  keywords:
    - GTM
    - Google Tag Manager
    - firebase
    - Advertisers
    - datalayer
    - data layer
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-05-13T19:42:23Z'
  edited_at: '2026-10-28T09:04:11Z'
  id: 210353513
  locale: ja
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/ja/articles/210353513
---
> **概要：** Firebase SDKで記録したイベントを、Googleタグマネージャーを使ってAppsFlyerに送信する方法を説明します。

<Image alt="gtm.png" src="https://files.readme.io/fbb4e0f83baf6f5f7f8dc83e02986ca011f5cb919b9870768da1606798211dcc-360002517245.png" width="289px" />

AppsFlyerとGoogleタグマネージャー（GTM）、Firebaseを連携すると、Firebase SDKからFirebaseに送信したアプリ内イベントを、Googleタグマネージャーを通じてSDK経由でAppsFlyerにも送信できます。同じイベントを二重に送信する処理を実装する必要がなくなります。

GTMから送信するイベントは、AppsFlyerのアプリ内イベントに合わせて作成します。イベント名、パラメータ、構造は同じです。すでにアプリにGTMを実装している場合は、簡単にAppsFlyerへのイベント送信を設定できます。

このガイドの手順に従って、イベントを送信してください。 

<div id="considerations" />

### 注意事項

* **ローデータ上のイベントソース：** GTMで生成したイベントは、ローデータレポートでソースがS2Sに設定されます。 SDKから記録されるイベントでも、このように表示されるため注意してください。
* **SKAdNetworkのコンバージョン値の更新**：このガイドの手順でGTMから生成してSDKに送信したイベントでも、通常のSDKイベントと同様に、SDKがコンバージョン値を更新します。 <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKAdNetworkの計測</Anchor>をオンにし、必要な設定を行うだけで利用できます。

<div id="note" />

> 📘 **注意**
>
> * 現在、Googleタグマネージャーとの連携では、次のパラメータをAppsFlyerに送信できません。
>   * <Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">カスタマーユーザーID</Anchor>
>   * `att`
>   * `os`次の点に注意してください。
>   * SRNにアプリ内イベントポストバックを送信する場合、`att`パラメータが必要です。
>   * Meta広告にアプリ内イベントポストバックを送信する場合、`att`と`os`の両方のパラメータが必要です。

<div id="prerequisites" />

### 前提条件

GTMからAppsFlyerにイベントを送信する前に、アプリにGTM SDKを実装する必要があります。次の準備が必要です。

1. [GTMアカウント](https://www.google.com/analytics/tag-manager/)を用意します。
2. アプリでGTMとFirebaseの連携を設定します（[Android](https://developers.google.com/tag-manager/android)と[iOS](https://developers.google.com/tag-manager/ios/)の手順を参照）。
3. まだ実施していない場合は、<Anchor target="_blank" href="/marketers/ja/docs/integrate-the-appsflyer-sdk">AppsFlyer SDKを連携</Anchor>します。

準備が整ったら、<Anchor target="_blank" href="/marketers/ja/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup">GTMの設定</Anchor>に進みます。

<div id="see-also" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/migrate-from-firebase-dynamic-links-to-appsflyer">Firebase Dynamic LinksからAppsFlyerへの移行</Anchor>

<div data-zendesk-anchors="considerations=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85 h_01HE7SKSCBH47YYFTKBWY3JVSV=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85 h_01HE7SKSCBBTTWATRZ87BYRW6G=%E6%B3%A8%E6%84%8F prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HE7SKSCB9QHA4WEERVSWMF0P=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HE7SQQG2VJW9179Q77PTZFPH=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />

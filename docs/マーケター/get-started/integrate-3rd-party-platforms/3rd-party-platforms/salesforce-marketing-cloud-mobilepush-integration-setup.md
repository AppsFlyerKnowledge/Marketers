---
title: Salesforce Marketing Cloud MobilePushとの連携設定
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-14T06:37:05Z'
  edited_at: '2026-10-28T09:03:44Z'
  id: 10590769196817
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/10590769196817
---
> **概要：** AppsFlyerの連携済みパートナーであるSalesforce Marketing Cloud MobilePushは、マーケティング、グロース、エンゲージメントの各チーム向けのユーザーエンゲージメントプラットフォームです。

<div id="overview" />

## 概要

Salesforce Marketing Cloud MobilePushでは、チャネルを横断した顧客データに基づいて、対象を絞ったプッシュメッセージを作成・送信できます。アプリの利用を促進し、ROIの向上につなげられます。 MobilePushでは、閲覧した商品から各ページの滞在時間まで、アプリ内のユーザー行動を確認できます。 MobilePushとの連携では、次のことができます。

* エンゲージメントとモバイルコマースの促進
* ユーザー理解に役立つ情報の取得
* チャネルを横断したキャンペーンの簡単な作成
* 配信対象の分類とメッセージ配信のスケジュール設定

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、このパートナーには送信されません。ポストバックの送信設定にかかわらず、この制限が適用されます。

<div id="setting-up-salesforce-marketing-cloud-mobilepush" />

## Salesforce Marketing Cloud MobilePushの設定

設定の大部分（手順1～4）はSalesforceで行います。手順5はAppsFlyerで行います。

<div id="step-1-set-up-mobilepush-sdk" />

### 手順1：MobilePush SDKの設定

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_get_started.htm&type=5">MobilePush SDKの設定を実装する</Anchor>

<div id="step-2-provision-for-push-notifications" />

### 手順2：プッシュ通知のプロビジョニング

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-provision.html">`.p12`証明書を作成する</Anchor>

<div id="step-3-enable-app-push-notifications" />

### 手順3：アプリのプッシュ通知を有効にする

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-configureforpush.html">プッシュ通知を実装する</Anchor>

<div id="step-4-set-up-app-push-notifications" />

### 手順4：アプリのプッシュ通知を設定する

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_outbound_message.htm&type=5">モバイルデバイス向けのプッシュメッセージを作成・送信する</Anchor>

<div id="note" />

> 📘 **注意**
>
> Salesforce Marketing Cloudでプッシュ通知を作成する際は、AppsFlyerが正しいPIDとキャンペーン属性を使って計測できるように、<Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_custom_keys.htm&type=5">カスタムキー</Anchor>を追加する必要があります。カスタムキーには`AF_xxxxxxxxx`を使用します。

<div id="step-5-set-up-push-notifications-in-appsflyer" />

### 手順5：AppsFlyerでプッシュ通知を設定する

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications-ios#addpushnotificationdeeplinkpath-recommended">OneLinkを使用してiOS SDKを設定する（リンク先の手順3）</Anchor>

<div id="note-1" />

> 📘 **注意**
>
> [手順4](/docs/salesforce-marketing-cloud-mobilepush-integration-setup#手順4アプリのプッシュ通知を設定する)で入力した`AF_xxxxxxxxx`カスタムキーが、`addPushNotificationDeepLinkPath`関数に入力した値と一致することを確認します。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01H9HWK3F5TQZ8YQZBHGBZACPG=%E6%A6%82%E8%A6%81 h_01H9HWK5DM87JTDVFND0KB965G=%E9%87%8D%E8%A6%81 setting-up-salesforce-marketing-cloud-mobilepush=salesforce-marketing-cloud-mobilepush%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWK3F52YGQPX4B82N40PPD=salesforce-marketing-cloud-mobilepush%E3%81%AE%E8%A8%AD%E5%AE%9A step-1-set-up-mobilepush-sdk=%E6%89%8B%E9%A0%861mobilepush-sdk%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWK3F5HCVZ0225MFRYRW5Q=%E6%89%8B%E9%A0%861mobilepush-sdk%E3%81%AE%E8%A8%AD%E5%AE%9A step-2-provision-for-push-notifications=%E6%89%8B%E9%A0%862%E3%83%97%E3%83%83%E3%82%B7%E3%83%A5%E9%80%9A%E7%9F%A5%E3%81%AE%E3%83%97%E3%83%AD%E3%83%93%E3%82%B8%E3%83%A7%E3%83%8B%E3%83%B3%E3%82%B0 h_01H9HWK3F5RNCZG340E0CT5XJC=%E6%89%8B%E9%A0%862%E3%83%97%E3%83%83%E3%82%B7%E3%83%A5%E9%80%9A%E7%9F%A5%E3%81%AE%E3%83%97%E3%83%AD%E3%83%93%E3%82%B8%E3%83%A7%E3%83%8B%E3%83%B3%E3%82%B0 step-3-enable-app-push-notifications=%E6%89%8B%E9%A0%863%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%97%E3%83%83%E3%82%B7%E3%83%A5%E9%80%9A%E7%9F%A5%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B h_01H9HWK3F5E4W8FG35V4JTFN7F=%E6%89%8B%E9%A0%863%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%97%E3%83%83%E3%82%B7%E3%83%A5%E9%80%9A%E7%9F%A5%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B step-4-set-up-app-push-notifications=%E6%89%8B%E9%A0%864%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%97%E3%83%83%E3%82%B7%E3%83%A5%E9%80%9A%E7%9F%A5%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01H9HWK3F5K8V8AVADXNNG25GY=%E6%89%8B%E9%A0%864%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%97%E3%83%83%E3%82%B7%E3%83%A5%E9%80%9A%E7%9F%A5%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01H9HWK3F5VG2GBCE93B69AADH=%E6%B3%A8%E6%84%8F step-5-set-up-push-notifications-in-appsflyer=%E6%89%8B%E9%A0%865appsflyer%E3%81%A7%E3%83%97%E3%83%83%E3%82%B7%E3%83%A5%E9%80%9A%E7%9F%A5%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01H9HWK3F5YJ71YCWHV4B02VYP=%E6%89%8B%E9%A0%865appsflyer%E3%81%A7%E3%83%97%E3%83%83%E3%82%B7%E3%83%A5%E9%80%9A%E7%9F%A5%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01H9HWK3F5T67NSPE9CVPS1KTA=%E6%B3%A8%E6%84%8F-1" />

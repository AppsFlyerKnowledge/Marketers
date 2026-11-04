---
title: TealiumとAppsFlyerの連携
metadata:
  keywords:
    - Marketers
    - TEST ID LOC
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-22T16:09:24Z'
  edited_at: '2026-10-28T09:03:57Z'
  id: 10820404821393
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/10820404821393
---
> **概要：** カスタマーデータプラットフォーム（CDP）であるTealiumは、Web、モバイル、IoT、オフラインの顧客データをつなぎます。コンバージョンデータをTealiumに自動共有する方法を説明します。

<Image alt="Tealium_icon.png" src="https://files.readme.io/e3cc1f95e8ce2de6fa83df63ff78dd4f4f76aebe1acb8e9378aa5b6aa4134364-10820461521681.png" width="276px" />

<div id="overview" />

## 概要

TealiumとAppsFlyerを連携すると、モバイルアプリを運営する企業はAppsFlyerのモバイルアトリビューションSDKを活用し、コンバージョンのアトリビューションデータをTealium AudienceStreamのプロファイルに直接送信できます。

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、このパートナーには送信されません。ポストバックの送信設定にかかわらず、この制限が適用されます。

<div id="setting-up-tealium" />

## Tealiumの設定

TealiumとAppsFlyerは、次のいずれかの方法で連携できます。

* クライアント側での連携
* サーバー側での連携

<div id="client-side-integration" />

### クライアント側での連携

iOSおよびAndroidライブラリのリモートコマンドを使って、AppsFlyer SDKのネイティブコードを実行できます。

**クライアント側でTealiumを連携するには、次の手順に従います。**

* <Anchor target="_blank" href="https://docs.tealium.com/platforms/remote-commands/integrations/appsflyer/">リモートコマンドの連携ガイド</Anchor>に従って設定します。

<div id="server-side-integration" />

### サーバー側での連携

Customer Data HubアカウントでAppsFlyer App Eventsコネクターを設定し、TealiumとAppsFlyerの間でリアルタイムにデータを送信します。

**サーバー側でTealiumを連携するには、次の手順に従います。**

* <Anchor target="_blank" href="https://docs.tealium.com/server-side-connectors/appsflyer-app-events-connector/">AppsFlyer App Eventsコネクターのガイド</Anchor>に従って設定します。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01H9HWK1ACY09ZVD7WHEQR4MR3=%E6%A6%82%E8%A6%81 h_01H9HWK1ACA6A743PDY3Q1Y0KV=%E9%87%8D%E8%A6%81 setting-up-tealium=tealium%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWK1AC27GPZPZR13SFC3GM=tealium%E3%81%AE%E8%A8%AD%E5%AE%9A clientside-integration=%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E5%81%B4%E3%81%A7%E3%81%AE%E9%80%A3%E6%90%BA h_01H9HWK1ACH6K0FDTVCHAPSKME=%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E5%81%B4%E3%81%A7%E3%81%AE%E9%80%A3%E6%90%BA serverside-integration=%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E5%81%B4%E3%81%A7%E3%81%AE%E9%80%A3%E6%90%BA h_01H9HWK1ACDZQEYVRZ7QWQ4KY3=%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E5%81%B4%E3%81%A7%E3%81%AE%E9%80%A3%E6%90%BA" />

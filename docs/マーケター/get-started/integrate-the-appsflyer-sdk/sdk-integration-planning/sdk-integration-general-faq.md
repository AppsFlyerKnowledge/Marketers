---
title: SDK実装に関する一般的なFAQ
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-01-18T11:13:24Z'
  edited_at: '2026-10-13T12:49:52Z'
  id: 207033546
  locale: ja
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ja/articles/207033546
---
> **At a glance:** AppsFlyer SDKを利用すると、アプリの広告配信やアトリビューション計測、ディープリンクの設定、モバイルアプリユーザーの行動データの収集を安全に行えます。アドネットワークや各種プラットフォームとの連携も、数週間から数か月かけることなく、わずか数分で設定して利用を開始できます。

## AppsFlyer SDKのインストールとアップデート方法

AppsFlyer SDKのインストールとアップデートの手順については、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">Dev Hub</Anchor>をご覧ください。**注意**：SDKをアップグレードするには、アプリの新しいバージョンをストアに公開する必要があります。

## AppsFlyer SDKの実装は難しいですか？

経験豊富な開発者であれば、1時間もかからずにアプリでAppsFlyerのアトリビューション計測を利用できる状態にできます。その後は、アプリごとに数分程度の作業で対応できます。

<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">Android</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">iOS</Anchor>、Unity向けのSDK実装ガイド、または<Anchor target="_blank" href="/marketers/ja/docs/other-platforms">その他のプラットフォーム</Anchor>向けのガイドをご覧ください。

## AppsFlyer SDKはアプリのダウンロード時間に影響しますか？

AppsFlyer SDKのパッケージは、アプリのパフォーマンスへの影響を*限りなくゼロに近づける*ように設計・開発されています。 どのバージョンのSDKも軽量で、通常はアプリ全体のサイズの1%未満です。そのため、**アプリ全体のダウンロード時間への影響はごくわずかです**。

* **Android SDK：** 約300KB
* **iOS SDK：** 約3.4MB

## AppsFlyer SDKはアプリのパフォーマンスに影響しますか？

AppsFlyer SDKのAPIは、主に*setter*／*getter*、またはAppsFlyerサーバーとのデータ送受信を行う高速な非同期Webサービスメソッドで構成されています。そのため、SDKのAPIがアプリのパフォーマンスに与える影響は無視できるほど小さいものです。

つまり、**AppsFlyer SDKがアプリのパフォーマンスやユーザー体験に影響することはありません**。

## アプリ外で発生したアプリ内イベントを記録できますか？

たとえば、ユーザーがWebサイト上でサブスクリプションを更新した場合など、アプリ外で発生したイベントは<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S APIを使用して送信</Anchor>できます。記録されたS2Sイベントは、ダッシュボード、ローデータ、分析機能など、プラットフォーム全体で利用できます。

<div data-zendesk-anchors="how-to-install-and-update-the-appsflyer-sdk=appsflyer-sdk%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%82%A2%E3%83%83%E3%83%97%E3%83%87%E3%83%BC%E3%83%88%E6%96%B9%E6%B3%95 h_01HSXBYM9WMD9CDX03RFHM0JY1=appsflyer-sdk%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%82%A2%E3%83%83%E3%83%97%E3%83%87%E3%83%BC%E3%83%88%E6%96%B9%E6%B3%95 is-it-hard-to-integrate-the-appsflyer-sdk=appsflyer-sdk%E3%81%AE%E5%AE%9F%E8%A3%85%E3%81%AF%E9%9B%A3%E3%81%97%E3%81%84%E3%81%A7%E3%81%99%E3%81%8B h_01HMTWQHQRGE6Z2BM1BBQY04H1=appsflyer-sdk%E3%81%AE%E5%AE%9F%E8%A3%85%E3%81%AF%E9%9B%A3%E3%81%97%E3%81%84%E3%81%A7%E3%81%99%E3%81%8B does-the-appsflyer-sdk-affect-app-download-time=appsflyer-sdk%E3%81%AF%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%80%E3%82%A6%E3%83%B3%E3%83%AD%E3%83%BC%E3%83%89%E6%99%82%E9%96%93%E3%81%AB%E5%BD%B1%E9%9F%BF%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B h_01HMTWQHQRQQ47CAJCA4Y0AASZ=appsflyer-sdk%E3%81%AF%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%80%E3%82%A6%E3%83%B3%E3%83%AD%E3%83%BC%E3%83%89%E6%99%82%E9%96%93%E3%81%AB%E5%BD%B1%E9%9F%BF%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B does-the-appsflyer-sdk-affect-app-performance=appsflyer-sdk%E3%81%AF%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%81%AB%E5%BD%B1%E9%9F%BF%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B h_01HMTWQHQRXBPQN75J0KM48AJ2=appsflyer-sdk%E3%81%AF%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%81%AB%E5%BD%B1%E9%9F%BF%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B can-i-record-inapp-events-that-occur-outside-my-app=%E3%82%A2%E3%83%97%E3%83%AA%E5%A4%96%E3%81%A7%E7%99%BA%E7%94%9F%E3%81%97%E3%81%9F%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E8%A8%98%E9%8C%B2%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01HMTWQHQSP646Y8KVZSBA01TF=%E3%82%A2%E3%83%97%E3%83%AA%E5%A4%96%E3%81%A7%E7%99%BA%E7%94%9F%E3%81%97%E3%81%9F%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E8%A8%98%E9%8C%B2%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B" />

---
title: Segmentとの連携
metadata:
  keywords:
    - Integration
    - segment IO
    - Advertisers
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
  created_at: '2016-06-30T07:54:38Z'
  edited_at: '2026-10-28T09:03:46Z'
  id: 210041606
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/210041606
---
> **概要：** Segmentの分析データをAppsFlyerに送信します。

## はじめに

Segmentでは、AppsFlyerにデータを簡単に送信できます。 Segmentのオープンソースライブラリで記録したデータは、適切な形式に変換され、AppsFlyerに送信されます。 AppsFlyerは、的確なターゲティング、広告費の最適化、ROIの向上を支援します。

## SegmentとAppsFlyerを連携する

連携方法は、<Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/">Segmentのガイド</Anchor>を参照してください。

## よくある質問

<div id="how-can-i-integrate-segment-with-appsflyer" />

<Accordion title="SegmentとAppsFlyerを連携するにはどうすればよいですか？">

次の手順でSegmentとAppsFlyerを連携します。

* AppsFlyerに接続するよう、<Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">Segment管理画面を設定</Anchor>します。
* アプリに[Segment Wrapper SDK](/docs/segment-integration#how-does-the-sdk-wrapper-work)を実装します。
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-swift-appsflyer">ネイティブiOS</Anchor>
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-kotlin-appsflyer">ネイティブAndroid</Anchor>

</Accordion>

<div id="what-sdks-do-i-need-to-add-to-my-app" />

<Accordion title="アプリにはどのSDKを追加する必要がありますか？">

Segment SDKラッパーのみを追加してください。 Segment SDKラッパーの依存関係を追加すると、アプリのビルド時にSegment SDKとAppsFlyer SDKが自動的に追加されます。

</Accordion>

<div id="how-does-the-sdk-wrapper-work" />

<Accordion title="SDKラッパーはどのように動作しますか？">

Segment SDKラッパーは、Segment SDKとAppsFlyer SDKをつなぎます。

Segment SDKラッパーからインストールやアプリ内イベントを記録するSegmentのメソッドを呼び出すと、SegmentとAppsFlyerの両方のメソッドが呼び出されます。

これにより、必要なコード量を減らし、実装の手間と時間を削減できます。

> ❗️ **警告**
>
> 警告：Segment SDKラッパーとAppsFlyer SDKのメソッドを**併用しないでください**。併用すると、エラーやデータの差異が生じることがあります。
>
> **Segment SDKラッパーのメソッドのみを使用してください。**

</Accordion>

<div id="is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk" />

<Accordion title="Segment SDKラッパーとAppsFlyer SDKで、機能に違いはありますか？">

いいえ、機能に違いはありません。 AppsFlyer SDKのすべての機能を、Segment SDKラッパーから利用できます。

</Accordion>

<div id="i-dont-see-inapp-event-data-in-the-appsflyer-dashboard" />

<Accordion title="AppsFlyer管理画面にアプリ内イベントのデータが表示されません">

* Segment SDKラッパーのtrackメソッドの実装手順に従っていることを確認してください。
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyer-Segment-Integration#adding_events">Android</Anchor>
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/blob/master/examples/SwiftPodsSample/SwiftPodsSample/ViewController.swift">iOS</Anchor>
* Segment管理画面でAppsFlyerを連携する際に、必ず<Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">Devキーを指定</Anchor>してください。

</Accordion>

<div id="install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match" />

<Accordion title="SegmentとAppsFlyerでインストールとアプリ内イベントのデータが一致しません">

Segment SDKラッパーのみを使用してください。AppsFlyer SDKと併用しないでください。詳細は、[こちら](/docs/segment-integration#how-does-the-sdk-wrapper-work)を参照してください。

SegmentとAppsFlyerのデータが一致しない原因は、[上記のよくある質問](/docs/segment-integration#i-dont-see-inapp-event-data-in-the-appsflyer-dashboard)にも記載されています。

</Accordion>

<div id="im-getting-a-validation-error-when-testing-events-in-segment" />

<Accordion title="Segmentでイベントをテストすると、検証エラーが発生します">

***Destination***ページの***Event Tester***でテストすると、***Validation Error AppsFlyer Device ID ('integrations.AppsFlyer.appsFlyerId') is required to send server to server events***というエラーが表示される場合があります。

このエラーは、SegmentとAppsFlyerの連携に問題があることを意味するものではありません。 Event Testerでは、SegmentからAppsFlyerへのサーバー間送信をテストできます。サーバー間で送信するイベントには必ずAppsFlyerIDが必要なため、このエラーが発生します。

ただし、これはサーバー間イベントにのみ関係するものです。 Segment SDK APIでイベントを記録すると、SDKからSegmentとAppsFlyerの両方にイベントが送信されます。 AppsFlyerへのAPI呼び出しには、AppsFlyer Device IDが含まれます。

</Accordion>

<div id="im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

<Accordion title="サードパーティの分析ツールを使用しています。 AppsFlyerとSegmentの両方で連携を設定する必要がありますか？">

いいえ、サードパーティの分析ツールは、Segment管理画面でのみ有効にしてください。

</Accordion>

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01JZMD855TA62KQ4AWJ5F6WSDP=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB integrating-segment-with-appsflyer=segment%E3%81%A8appsflyer%E3%82%92%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B h_01JZMD855TNEYZG1MDZY7FWV8S=segment%E3%81%A8appsflyer%E3%82%92%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B faqs=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01JZMD855TAEBDPAMEAEH66F27=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01JZMD855T2BXFR1AKRNAA7M51=how-can-i-integrate-segment-with-appsflyer h_01JZMD855TG3WEKQH21JJ1PT43=what-sdks-do-i-need-to-add-to-my-app h_01JZMD855TW07PGDA6QHFWPN67=how-does-the-sdk-wrapper-work h_01JZMD855TNZGKVY2G98FPM22Z=%E8%AD%A6%E5%91%8A h_01JZMD855T0BEENPF0BMQDBFS8=is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk h_01JZMD855TV6J44PAV1A7JCKT5=i-dont-see-inapp-event-data-in-the-appsflyer-dashboard h_01JZMD855TH07JNZBT8CN4026W=install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match h_01JZMD855TY8X2PV1HB8Y0QT6Z=im-getting-a-validation-error-when-testing-events-in-segment h_01JZMD855TCE97QW8TSBEN1DYY=im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

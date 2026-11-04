---
title: AppsFlyer iOS SDKのリリースノート
metadata:
  keywords:
    - Advertisers
    - Release Notes
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
  created_at: '2017-03-09T19:49:54Z'
  edited_at: '2026-10-28T09:11:29Z'
  id: 115001224823
  locale: ja
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ja/articles/115001224823
---
> **概要：** SDKのリリースノートでは、iOS SDKの最新の変更点を簡潔に確認できます。開発者向けの詳しい情報は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">Developer HubのiOSリリースノート</Anchor>を参照してください。

<strong>iOSとAndroidの旧バージョンのSDKは、6か月ごとの定期的なサイクルでサポートが終了します。</strong>事前に終了予定を知らせることで、チームが計画的に対応し、アプリのすべての機能を支障なく維持できるようにするためです。最新のSDKに更新すると、新機能、安定性の向上、継続的なサポートを利用できます。

<div id="important" />

> 🚧 **重要！**
>
> 円滑に移行するため、アプリの開発者はサポート終了日までに最新バージョンのSDKへ更新することを推奨します。

<div id="end-of-support-vs-deprecated" />

## サポート終了と非推奨の違い

AppsFlyerでは、サポートの範囲とデータ計測への影響を明確にするため、SDKの<strong>「非推奨」</strong>と<strong>「サポート終了」</strong>を区別しています。

* **非推奨のバージョン：** 重大な不具合など、既知の問題があるため、利用を推奨しないSDKバージョンです。 AppsFlyerへのデータ送信は引き続き可能ですが、継続利用は推奨しません。サポート対象のバージョンへの更新を強く推奨します。
* **サポート終了のバージョン：** すべてのプラットフォームで計測が完全に停止するSDKバージョンです。 AndroidとiOSのどちらでも、インストール、セッション、アプリ内イベントは計測されません。 AppsFlyerが個別に例外として指定したものを除き、これらのバージョンからのすべてのトラフィックには、ステータスコード400が返されます。SDKは通常どおりAPIリクエストを送信しようとしますが、AppsFlyerサーバーが拒否するため、データは処理されません。

<div id="ios-sdk-release-notes" />

## iOS SDKのリリースノート

以下の表では、サポート対象のiOS SDKバージョンについて、リリース日と開発者向けの主な変更点を確認できます。開発者向けの情報は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk">iOS SDK実装ガイド</Anchor>を参照してください。

| バージョン | リリース日 | 変更内容 |
| --- | --- | --- |
| 7.0.1 | 2026-07-22 | <ul><li>アプリからSDKに、ハッシュ化したユーザーのメールアドレス、電話番号、氏名、FacebookログインIDを渡し、アドネットワークのパートナーと共有できるようになりました。 SDK自体がこれらの情報を取得することはありません。情報はアプリから渡され、ハッシュ化した値のみが送信されます。元の文字列がそのまま送信されることはありません。</li><li>`setUserEmails`と`setPhoneNumber`メソッドを削除しました。これらのメソッドを使用している開発者は、`setUserEmail`と`setUserPhone`に切り替える必要があります。</li></ul> |
| 6.18.1 | 2026-05-25 | <ul><li>ネットワークエラーで失敗したPurchase Connectorの購入検証リクエストが、アプリの再起動後に完全に失われる問題を修正しました。</li></ul> |
| 6.18.0 | 2026-04-21 | <ul><li>AppTransactionの取得に対応しました。AppTransactionは、アプリストアによって暗号学的に署名された、アプリのダウンロード情報です。</li><li>不具合の修正と改善</li></ul> |
| 6.17.9 | 2026-03-10 | <ul><li>ODMデータの取得中にSDKが停止し、サーバーへのリクエストを送信できなくなる問題を修正しました。</li><li>アプリで設定したカスタマーユーザーIDが、インストールイベントで送信されない問題を修正しました。</li></ul> |
| 6.17.8 | 2025-12-03 | <ul><li>新しい購入検証API（購入の検証と記録）が、正式に利用可能になりました。</li></ul> |
| 6.17.7 | 2025-10-15 | <ul><li>GoogleのICMライブラリからのデータ取得に関する問題を修正しました。</li></ul> |
| 6.17.6 | 2025-09-21 | <ul><li>SDKがAppsFlyerにICMデータを送信しようとするとクラッシュする可能性がある、v6.17.3で発生した問題を修正しました。</li></ul> |
| 6.17.5  <br />非推奨 | 2025-09-03 | <ul><li>**このバージョンは非推奨です。使用しないでください。**</li></ul> |
| 6.17.4  <br />非推奨 | 2025-08-27 | <ul><li>**このバージョンは非推奨です。使用しないでください。**</li><li>SDKの初期化時に、まれにアプリがクラッシュする問題を修正しました。</li></ul> |
| 6.17.3  <br />非推奨 | 2025-08-21 | <ul><li>**このバージョンは非推奨です。使用しないでください。**</li><li>計測精度を向上させるため、GoogleのICMライブラリからデータを取得する処理を更新しました。</li></ul> |
| 6.17.2 | 2025-07-15 | <ul><li>`validateAndLogInAppPurchase` API（ベータ版）を更新しました。</li><li>ATT（AppTrackingTransparency）の同意を取得するアプリで、Apple Search Ads（ASA）トークンの処理を改善しました。</li></ul> |
| 6.17.1 | 2025-06-24 | <ul><li><Anchor target="_blank" href="https://support.google.com/google-ads/answer/16203286">Google Integrated Conversion</Anchor>（ICM）による計測に対応しました。</li><li>開発環境でSDKを実行すると、App Storeのログイン画面が表示される問題を修正しました。</li></ul> |
| 6.17.0 | 2025-04-23 | <ul><li>安定性とパフォーマンスの改善</li></ul> |
| 6.16.2 | 2025-03-10 | <ul><li>プラグイン向けにこのバージョンをリリースするために必要な技術的更新</li></ul> |
| 6.16.1 | 2025-02-18 | <ul><li>DMAの同意データをAppsFlyerに手動で送信するためのAPIを更新しました。</li></ul> |
| 6.16.0 | 2025-01-19 | <ul><li>Purchase Connectorを通じたサブスクリプションとアプリ内購入の報告で、AppleのStoreKit 2 APIに対応しました。この機能は、現在クローズドベータ版です。</li></ul> |
| 6.15.3 | 2024-09-23 | SDKの保守対応 |
| 6.15.2 | 2024-08-28 | <ul><li>Purchase Connectorのイベント送信に関する問題を修正しました。この修正は、Purchase Connectorのいずれの本番環境向けバージョンにも影響しません。バージョン6.15.xへの更新に関連するものです。</li></ul> |
| 6.15.1 | 2024-08-19 | <ul><li>同じ開発元のアプリがデバイスに2つ以上インストールされている場合に、再インストール検知で発生する問題を修正しました。</li></ul> |
| 6.15.0 | 2024-08-06 | <ul><li>AppsFlyerに広告収益データを送信するための`logAdRevenue` APIを追加しました。 **注意：** このバージョン以降はAdRevenue Connectorを使用せず、`logAdRevenue`メソッドに置き換える必要があります。詳しくは、[こちら](https://dev.appsflyer.com/hc/docs/ad-revenue-2)を参照してください。</li><li>Purchase Connectorに関連する内部処理を更新しました。 Purchase Connectorを使用しているアプリで、このSDKバージョンに更新する場合は、Purchase Connectorもv6.15.0に更新する必要があります。</li></ul> |
| 6.14.6 | 2024-07-24 | <ul><li>新しいセッションの開始時に、SDKが`getConversionData` API（GCD）を余分に呼び出す問題を修正しました。計測への影響はありません。</li></ul> |
| 6.14.5 | 2024-07-03 | <ul><li>手動で同意データを送信するコードを削除しても、アプリで設定した同意データがSDKから送信される問題を修正しました。</li></ul> |
| 6.14.4 | 2024-06-10 | <ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">厳格モードのSDK</Anchor>のプライバシーマニフェストを更新しました。</li></ul> |
| 6.14.3 | 2024-04-26 | <ul><li>CocoaPodsを使用するアプリで、プライバシーマニフェストの自動統合に関する問題を修正しました。</li></ul> |
| 6.14.2 | 2024-04-19 | SDKの保守対応 |
| 6.14.1 | 2024-04-18 | <ul><li>更新された購入検証の流れに対応しました。この機能は、現在クローズドベータ版です。詳しくはこちら。</li></ul> |
| 6.14.0 | 2024-04-07 | <ul><li>プライバシーマニフェストに対応しました。 <Anchor target="_blank" href="/marketers/ja/docs/implement-privacy-manifest-in-your-app">AppsFlyerのプライバシーマニフェストについて詳しくはこちら</Anchor>。</li><li>SDKにXCFrameworkの署名を追加しました。Xcode 15を使用する開発者は、SDKの配布元と正当性を検証できます。</li></ul> |
| 6.13.2 | 2024-03-26 | <ul><li>Xcode 15.3でSPMを使用するアプリをリリースできない問題を修正しました。詳しくは、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes#version-6132">開発者向けのリリースノート</Anchor>を参照してください。</li></ul> |
| 6.13.1 | 2024-03-05 | <ul><li>CMPを使った同意取得の流れ（DMA）で、GDPRの対象外のユーザーの同意データを送信する際に発生する問題を修正しました。</li></ul> |
| 6.13.0   <br />非推奨 | 2024-02-08 | <ul><li>Googleの新しいEUユーザー同意ポリシーに対応しました。</li></ul> |

<div id="unsupported-sdk-versions" />

## サポート終了のSDKバージョン

以下のSDKバージョンは、**サポート終了**となっています。これらのバージョンからAppsFlyerにデータを送信することはできず、すべてのトラフィックが拒否されます。

| バージョン | リリース日 | 変更内容 |
| --- | --- | --- |
| 6.12.3 | 2024-01-04 | <ul><li>メール配信サービス（ESP）のリンクを解決する処理で、ディープリンクのコールバックに`original_link`パラメータを追加しました。</li><li>iAd Frameworkへの参照をすべて削除しました。</li></ul> |
| 6.12.2 | 2023-08-24 | SDKの保守対応 |
| 6.12.1 | 2023-07-20 | <ul><li>SKAdNetwork 4.0で、粗いコンバージョン値（Coarse conversion value）が「None」と報告される問題を修正しました。</li><li>tvOSの実装で発生するクラッシュを修正しました。</li></ul> |
| 6.12.0 | 2023-06-28 | SDKのbitcode対応を終了しました。 |
| 6.11.2 | 2023-06-13 | `validateAndLogInAppPurchase`（購入の検証と記録に使用する従来のAPI）を呼び出しても購入イベントが記録されない、v6.11.0で発生した問題を修正しました。   <br />  <br />**重要：**`v6.11.0`または`v6.11.1`で`validateAndLogInAppPurchase` APIを使用している場合は、このバージョンに更新してください。 |
| 6.11.1 | 2023-05-24 | SDKの保守対応 |
| 6.11.0 | 2023-04-25 | <ul><li>SDKがAppsFlyerサーバーにリクエストを送信する際のURLに、新しいAppsFlyerドメイン名を使用するようになりました。</li><li>空の値やnullを渡した場合の、setHost APIの動作を変更しました。 [詳しくはこちら](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost)</li></ul> |
| 6.10.1 | 2023-04-02 | 直接ディープリンクの処理で、UDLが受け渡すデータに`link`パラメータを追加しました。 |
| 6.10.0 | 2023-02-15 | SKAdNetwork 4.0に対応しました。 <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">AppsFlyerのSKAdNetworkソリューションについて詳しくはこちら</Anchor> |
| 6.9.2  <br />サポート終了：  <br />2025-09-08 | 2023-01-31 | コンバージョンデータ取得（GCD）の内部リクエスト構造を更新しました。**注意**：レスポンスデータに変更はありません。 |
| 6.9.1  <br />サポート終了：  <br />2025-09-08 | 2022-11-28 | コンバージョンデータ取得（GCD）の内部リクエスト構造を更新しました。**注意**：レスポンスデータに変更はありません。 |
| 6.9.0  <br />サポート終了：  <br />2025-09-08 | 2022-11-06 | 広告収益の報告に使用する内部APIを更新しました。このバージョン以降は、[広告収益用の汎用コネクター（Generic Connector for AdRevenue）](https://dev.appsflyer.com/hc/docs/ad-revenue-2)のみ対応しています。<br /><br />このSDKバージョンは、AdRevenue Connector `V6.9.0`と互換性があります。 |
| 6.8.1  <br />サポート終了：  <br />2025-09-08 | 2022-08-09 | **再インストール検知**：デバイス内のストレージを利用して、アプリの再インストールを検知・報告する機能を改善しました。この機能は、AppsFlyerダッシュボードの<Anchor target="_blank" href="/marketers/ja/docs/app-settings">アプリ設定ページ</Anchor>から管理できます。 |
| 6.8.0  <br />サポート終了：  <br />2025-03-03 | 2022-07-19 | 再インストール検知には、SDK V6.8.1以降を使用してください。 |
| 6.7.0  <br />サポート終了：  <br />2025-03-03 | 2022-06-19 | iOS 15.4で導入されたAppleの更新済みAPI`updatePostbackConversionValue`を使用するよう、SKAdNetworkの実装を更新しました。<br /><br />SKAdNetworkから送信されるデータへの影響はなく、アプリのコードを変更する必要もありません。 |
| 6.6.1  <br />サポート終了：  <br />2025-03-03 | 2022-05-16 | SDKの保守対応 |
| 6.6.0  <br />サポート終了：  <br />2025-03-03 | 2022-05-01 | 既存ユーザー向けの直接ディープリンクの処理で、UDLの`didResolveDeepLink`コールバックにパラメータを追加しました。<Anchor target="_blank" href="/marketers/ja/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">詳しくはこちら</Anchor>。 |
| 6.5.4  <br />サポート終了：  <br />2025-03-03 | 2022-03-23 | SDKの保守対応 |
| 6.5.3  <br />サポート終了：  <br />2025-03-03 | 2022-03-02 | **不具合修正：** URIスキームに基づくリンクで、`didResolveDeepLink`が2回呼び出される問題を修正しました。 |
| 6.5.2  <br />サポート終了：  <br />2025-03-03 | 2022-01-26 | SDKの保守対応 |
| 6.5.1  <br />サポート終了：  <br />2025-03-03 | 2022-01-03 | SDKの保守対応 |
| 6.5.0  <br />サポート終了：  <br />2025-03-03 | 2021-12-22 | コードの構造整理と内部処理の変更。 |
| 6.4.4  <br />サポート終了：  <br />2025-03-03 | 2021-12-12 | SDKの保守対応 |
| 6.4.3  <br />サポート終了：  <br />2025-03-03 | 2021-11-30 | XCFrameworkを使用するmacOS 10.14.6での安定性に関する問題を修正しました。 |
| 6.4.2  <br />サポート終了：  <br />2025-03-03 | 2021-10-28 | SDKの保守対応 |
| 6.4.1  <br />サポート終了：  <br />2025-03-03 | 2021-10-24 | Unityアプリの安定性に関する問題を解消しました。 |
| 6.4.0  <br />サポート終了：  <br />2025-03-03 | 2021-09-12 | **APIの追加：** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor>で、SDKによるデータ共有から除外するパートナーを設定できるようになりました。<br /><br />このバージョン以降、`setSharingFilter`と<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforallpartners">`setSharingFilterForAllPartners`</Anchor>は非推奨です。 |
| 6.3.5  <br />サポート終了： 2024-08-31 | 2021-08-19 | **APIの追加**：[`setCurrentDeviceLanguage`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setcurrentdevicelanguage)<br /><br />このバージョン以降、SDKはデバイスの言語を自動的に取得しなくなります。 |
| 6.3.4  <br />サポート終了： 2024-08-31 | 2021-07-21 | <ul><li>**不具合修正：** Xcode 12.5のシミュレーターでSDKを実行する際の問題を修正しました。</li><li>軽微な修正と更新。</li></ul> |
| 6.3.2  <br />サポート終了： 2024-08-31 | 2021-06-17 | デバッグログを改善しました。 |
| 6.3.1  <br />サポート終了： 2024-08-31 | 2021-06-02 | SDKの保守対応 |
| 6.3.0  <br />サポート終了： 2024-08-31 | 2021-05-13 | <ul><li>Apple Silicon対応：M1チップを搭載したMacのシミュレーターでSDKを実行できるようになりました。</li><li>このバージョン以降、SDKはiOS `9`以降に対応しています。 iOS `8`は、サポート対象外です。</li><li>iOSの厳格モードのSDK：依存関係管理ツールCarthageに対応しました。</li><li>OneLink APIの技術的更新</li></ul> |
| 6.2.6  <br />サポート終了： 2024-08-31 | 2021-04-25 | <ul><li>不具合修正：`didFinishLaunchingWithOptions`より後にSDKを初期化すると、SKAdNetworkのルールが読み込まれない問題を修正しました。</li><li>不具合修正：`waitForATTUserAuthorization`で、ユーザーが同意していても、特定の条件でIDFAを含まない起動イベントが送信される問題を修正しました。</li><li>iOS 8のデバイスでSDKを実行できるようになりました。</li><li>不要なコードとデータの整理・削除</li></ul> |
| 6.2.5  <br />サポート終了： 2024-08-31 | 2021-04-06 | SDKのコードの構造整理、不要なコードやデータの削除。<br /><br />このバージョン以降、次の変更が適用されます。<ul><li>`setShouldCollectDeviceName`メソッドは非推奨となり、デバイス名を返さなくなります。</li><li>SDKから送信される`wifi`パラメータは、`False`に設定されます。</li></ul> |
| 6.2.4  <br />サポート終了： 2024-08-31 | 2021-03-15 | SKAdNetworkの収益計測モードと、`AF_REVENUE`パラメータを含むアプリ内イベントに関する不具合を修正しました。<br /><br />このバージョン以降、収益計測では、`AF_REVENUE`を含むすべてのイベントがコンバージョン値に反映されます。この変更以前は、`AF_PURCHASE`イベントに含まれる場合にのみ、コンバージョン値が設定されていました。<br /><br />**注意：** SKAdNetworkの収益計測を実装している場合は、このバージョンに更新する必要があります。 |
| 6.2.3  <br />サポート終了： 2024-08-31 | 2021-03-07 | SKAdNetworkの`updateConversionValue`の呼び出しに関する不具合を修正しました。 |
| 6.2.2  <br />サポート終了： 2024-08-31 | 2021-02-18 | SDKの保守対応 |
| 6.2.1  <br />サポート終了： 2024-08-31 | 2021-02-15 | <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2Sによるイベントの送信</Anchor>に対応しました。 |
| 6.2.0  <br />サポート終了： 2024-08-31 | 2021-02-07 | APIの追加：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setpartnerdata">setPartnerData</Anchor> |
| 6.1.4  <br />サポート終了： 2024-08-31 | 2021-01-12 | SDKの保守対応 |
| 6.1.3  <br />サポート終了： 2024-08-31 | 2020-12-24 | <ul><li>APIの追加：<Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor>（Movable Inkに対応）</li><li>対応機能の追加：<Anchor target="_blank" href="https://developer.apple.com/documentation/adservices">Apple AdServices Framework</Anchor></li></ul> |
| 6.1.2  <br />サポート終了： 2024-08-31 | 2020-12-03 | SDKの保守対応 |
| 6.1.1  <br />サポート終了： 2024-08-31 | 2020-11-17 | 新機能の導入：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">厳格モードのSDK</Anchor> |
| 6.1.0  <br />サポート終了： 2024-08-31 | 2020-11-09 | 対応機能の追加：<Anchor target="_blank" href="https://dev.appsflyer.com/docs/ios-unified-deep-linking">統合ディープリンクAPI（UDL）</Anchor> |
| 6.0.8  <br />サポート終了： 2024-08-31 | 2020-10-28 | 対応機能の追加：<Anchor target="_blank" href="/marketers/ja/docs/apple-app-clips-integration-guide">Apple App Clips</Anchor>のアトリビューション |
| 6.0.7  <br />サポート終了： 2024-08-31 | 2020-10-21 | SDKの保守対応 |
| 6.0.6  <br />サポート終了： 2024-08-31 | 2020-10-20 | SDKの保守対応 |
| 6.0.5  <br />サポート終了： 2024-08-31 | 2020-10-08 | SDKの保守対応 |
| 6.0.4  <br />サポート終了： 2024-08-31 | 2020-09-30 | メール配信サービス（ESP）のリンクで、複数回のリダイレクトに対応しました。 |
| 6.0.3  <br />サポート終了： 2024-08-31 | 2020-09-06 | <ul><li>API名の変更：<br />waitForAdvertisingIdentifier --> waitForATTUserAuthorization</li><li>iOS 14でも、それ以前のiOSバージョンと同様に、SDKはデフォルトでIDFAを取得します。</li></ul> |
| 6.0.2   <br />サポート終了： 2024-08-31 | 2020-08-27 | <ul><li>API名の変更：<br />deviceLoggingDisabled --> anonymizeUser</li><li>iOS 14でIDFAを取得するには、AppTrackingTransparency（ATT）の確認画面が必要です。</li><li>IDFVを使ったクロスプロモーションのアトリビューションに対応しました。</li></ul> |
| 6.0.1 ベータ版  <br />サポート終了： 2024-08-31 | 2020-08-06 | <ul><li>ユーザーのプライバシーを保護しながら広告主がキャンペーンの成果を計測できるよう、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKAdNetworkのアトリビューション</Anchor>に対応しました。</li></ul> |
| 6.0.0 ベータ版  <br />サポート終了： 2024-08-31 | 2020-08-04 | <ul><li>デバッグ機能を拡充しました。</li><li>SDKの機能とAPIに大幅な変更を加えました。[詳しくはこちら](/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes)</li></ul> |

<div id="see-also" />

> 📄 **関連記事**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/about-att-and-skan">iOS 14、ATT、SKAdNetworkのクイックスタートガイド</Anchor>

<div data-zendesk-anchors="h_01JVHFG6PN34YFWNZKX2CYHJV8=%E9%87%8D%E8%A6%81 end-of-support-vs-deprecated=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E7%B5%82%E4%BA%86%E3%81%A8%E9%9D%9E%E6%8E%A8%E5%A5%A8%E3%81%AE%E9%81%95%E3%81%84 h_01JVHEKR4MTFV0FDHMTQW00BCS=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E7%B5%82%E4%BA%86%E3%81%A8%E9%9D%9E%E6%8E%A8%E5%A5%A8%E3%81%AE%E9%81%95%E3%81%84 ios-sdk-v6=ios-sdk%E3%81%AE%E3%83%AA%E3%83%AA%E3%83%BC%E3%82%B9%E3%83%8E%E3%83%BC%E3%83%88 01H8W3DDM1BYRSPMFTA3TCY8EQ=ios-sdk%E3%81%AE%E3%83%AA%E3%83%AA%E3%83%BC%E3%82%B9%E3%83%8E%E3%83%BC%E3%83%88 unsupported-sdk-versions=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E7%B5%82%E4%BA%86%E3%81%AEsdk%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 h_01JVHGN5NVRMGN9SJ5DWEAJYN3=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E7%B5%82%E4%BA%86%E3%81%AEsdk%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 h_01HE7RE2EPQX872DKNDBJ2G2QE=%E9%96%A2%E9%80%A3%E8%A8%98%E4%BA%8B" />

---
title: AppsFlyer Android SDKリリースノート
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
  created_at: '2017-03-09T20:17:19Z'
  edited_at: '2026-10-28T09:10:53Z'
  id: 115001256006
  locale: ja
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/ja/articles/115001256006
---
> **概要：** Android SDKの最新の変更内容を、SDKリリースノートで確認できます。より詳しい技術情報については、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-release-notes">Dev HubのAndroidリリースノート</Anchor>を参照してください。

<strong>iOSおよびAndroidの旧SDKバージョンは、6か月ごとの周期で順次サポートを終了します。</strong>この周期を設けることで、終了予定を事前にお知らせし、各チームが計画的に対応して、アプリのすべての機能を支障なく維持できるようにしています。最新のSDKにアップグレードすると、新機能、安定性の向上、継続的なサポートを利用できます。

> 🚧 **重要！**
>
> 円滑に移行できるよう、アプリ開発者にはサポート終了日までに最新のSDKバージョンへ更新することを推奨します。

## サポート終了と非推奨の違い

AppsFlyerでは、サポート範囲と計測への影響を明確にするため、SDKバージョンの**非推奨**と**サポート終了**を区別しています。

* **非推奨バージョン：** 重大なバグなどの既知の問題により、使用が推奨されなくなったSDKバージョンです。引き続きAppsFlyerにデータを送信できますが、継続使用は推奨されません。サポート対象のバージョンへのアップグレードを強く推奨します。
* **サポート終了バージョン：** すべてのプラットフォームで計測が完全に停止されたSDKバージョンです。 AndroidとiOSのいずれでも、インストール、セッション、アプリ内イベントは計測されません。これらのバージョンからのすべてのトラフィックには、ステータスコード400が返されます（製品チームが特別に除外したものを除きます）。SDKは通常どおりAPI呼び出しを試みますが、AppsFlyerサーバーが拒否するため、データは処理されません。

## Android SDKのリリース情報

以下の表に、サポート対象のAndroid SDKバージョンのリリースノートを示します。リリース日と、開発者向けの主な更新内容を記載しています。開発者向けの情報は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk">Android SDK実装ガイド</Anchor>を参照してください。

| バージョン | リリース日 | 変更内容 |
| --- | --- | --- |
| 7.0.1 | 2026-07-22 | <ul><li>アプリからSDKに、ハッシュ化した顧客のメールアドレス、電話番号、氏名、FacebookログインIDを提供し、アドネットワークパートナーと共有できるようになりました。 SDK自体がこれらの情報を収集することはありません。情報はアプリから提供され、送信されるのはハッシュ化された値のみです。平文で送信されることはありません。</li><li>`setUserEmails`メソッドと`setPhoneNumber`メソッドを削除しました。これらを使用している場合は、`setUserEmail`と`setUserPhone`に切り替える必要があります。</li></ul> |
| 6.18.1 | 2026-05-25 | <ul><li>購入コネクタで、接続の問題により失敗した購入検証がキャッシュされ、再試行されない問題を修正しました。この問題により、購入データが欠落する可能性がありました。</li></ul> |
| 6.18.0 | 2026-03-17 | <ul><li>安定性の向上と不具合の修正を行いました。</li></ul> |
| 6.17.6 | 2026-03-11 | <ul><li>アプリが設定したAF\_STOREの値がSDKから送信されない問題を修正しました。</li></ul> |
| 6.17.5 | 2025-11-26 | <ul><li>安定性の向上と不具合の修正を行いました。</li><li>新しい購入検証API（購入の検証と記録）が一般提供されました。</li></ul> |
| 6.17.4 | 2025-10-15 | <ul><li>SDKとAdvanced Security Moduleの連携を更新しました。このバージョンは、Security Module v2.0.0以降と互換性があります。</li><li>Advanced Security Moduleを使用していてSDKをv6.17.4に更新する場合は、Security Moduleもv2.0.0に更新する必要があります。</li></ul> |
| 6.17.3 | 2025-08-18 | <ul><li>技術的な更新：安定性とパフォーマンスを向上させました。</li></ul> |
| 6.17.2 | 2025-08-05 | <ul><li>技術的な更新：targetSDKVersionを35に更新しました。</li></ul> |
| 6.17.1 | 2025-07-28 | <ul><li>アプリ内購入の検証に使用する`validateAndLogInAppPurchase` APIを更新しました（現在ベータ版）。</li><li>Google Play Integrity APIとの連携を追加し、Google Playを通じてデバイスの完全性を検証できるようになりました。</li></ul> |
| 6.17.0 | 2025-04-24 | <ul><li>AppSet IDの収集をサポートしました。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id">開発者向けの手順</Anchor>を参照してください。</li></ul> |
| 6.16.2 | 2025-03-02 | <ul><li>SDKの実装時にビルドエラーが発生する可能性がある問題を修正しました。</li></ul> |
| 6.16.1 | 2025-02-17 | <ul><li>DMAの同意データをAppsFlyerに手動で送信するためのAPIを更新しました。</li></ul> |
| 6.16.0 | 2024-12-17 | <ul><li>Samsungのプリロードアトリビューションをサポートしました。<Anchor target="_blank" href="/marketers/ja/docs/set-up-appsflyer-preload-referrer-attribution#samsungプリロードリファラー">詳細はこちら</Anchor>。</li><li>Privacy SandboxのアトリビューションAPIで、収益計測をサポートしました（クローズドベータ版）。</li><li>安定性の問題を解消し、セキュリティを強化するため、Dexguardをv9.8.12に更新しました。</li></ul> |
| 6.15.2 | 2024-10-10 | <ul><li>安定性の向上と不具合の修正を行いました。</li><li>Privacy Sandbox Attribution APIに関する内部更新を行いました。</li></ul> |
| 6.15.1 | 2024-08-28 | 以下のバージョンを更新しました。<ul><li>targetSDKVersion: v34</li><li>Gradle: v8.7</li><li>Java: v17</li></ul> |
| 6.15.0 | 2024-07-31 | <ul><li>広告収益データをAppsFlyerに送信する`logAdRevenue`メソッドを追加しました。**注意：** このバージョン以降、広告収益コネクタは使用せず、`logAdRevenue`メソッドに置き換える必要があります。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">詳細はこちら</Anchor></li></ul> |
| 6.14.2 | 2024-06-10 | <ul><li>Unityでビルドしたアプリで、Meta Install Referrerの取得に関する問題を修正しました。</li></ul> |
| 6.14.1 | 2024-05-29 | SDKの保守更新を行いました。 |
| 6.14.0 | 2024-04-18 | <ul><li>更新された購入検証の処理フローをサポートしました。この機能は現在クローズドベータ版です。詳細はこちら。</li><li>Huaweiリファラの連携を更新しました。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#huawei-install-referrer">詳細はこちら</Anchor>。</li></ul> |
| 6.13.1 | 2024-04-03 | SDKの保守更新を行いました。 |
| 6.13.0 | 2024-02-08 | <ul><li>Googleの新しいEU同意ポリシー（DMA）に対応しました。</li></ul> |

## サポート終了のSDKバージョン

以下のSDKバージョンは、**サポート終了**となっています。これらのバージョンからAppsFlyerにデータを送信することはできず、すべてのトラフィックが拒否されます。

| バージョン | リリース日 | 変更内容 |
| --- | --- | --- |
| 6.12.6 | 2024-01-29 | SDKの保守更新を行いました。 |
| 6.12.5 | 2023-12-18 | <ul><li>ESPのリンク解決処理で、ディープリンクのコールバックに`original_link`パラメータを追加しました。</li></ul> |
| 6.12.4 | 2023-10-25 | <ul><li>SDKの安定性を向上させるため、Dexguardをバージョン9.4.16に更新しました。</li></ul> |
| 6.12.3 | 2023-08-31 | SDKの保守更新を行いました。 |
| 6.12.2 | 2023-08-02 | <ul><li>Android 8.1.0とAndroid 11の一部のデバイスで、アプリがクラッシュする可能性がある不具合を修正しました。</li></ul> |
| 6.12.1 | 2023-06-29 | <ul><li>クロスプロモーションで、Play Storeの起動が遅れる問題を修正しました。</li><li>一部のデバイスでアプリがクラッシュする不具合を修正しました。</li></ul> |
| 6.12.0 | 2023-06-28 | <ul><li>非推奨です。バージョン6.12.1を使用してください。</li></ul> |
| 6.11.2 | 2023-06-29 | <ul><li>一部のデバイスでアプリがクラッシュする不具合を修正しました。</li></ul> |
| 6.11.1 | 2023-06-6 | <ul><li>非推奨です。バージョン6.12.1を使用してください。</li><li>SDKの初期化後にアプリがクラッシュすることがある不具合を修正しました。</li></ul> |
| 6.11.0 | 2023-05-16 | <ul><li>SDKがGoogle Playリファラを取得しようとした際に、一部のデバイスでアプリが応答しなくなることがある問題を修正しました。</li></ul> |
| 6.10.3 | 2023-04-25 | SDKの保守更新を行いました。 |
| 6.10.2 (非推奨) |  | 非推奨 |
| 6.10.1 | 2023-03-01 | <ul><li>SDKの初期化時に、Samsungデバイスでアプリが終了することがある問題を修正しました。この問題は、SDK V6.6.0以降を使用するアプリに影響していました。</li></ul> |
| 6.10.0 | 2023-02-13 | <ul><li>SDKとAppsFlyerサーバー間の通信に使用する、新しいAppsFlyerドメインを追加しました。</li><li>空の値またはnullが送信された場合のsetHost APIの動作を変更しました。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost">詳細はこちら</Anchor></li></ul> |
| 6.9.4  <br />サポート終了：  <br />2025-09-08 | 2022-12-6 | <ul><li>広告収益SDKコネクタから広告収益イベントを送信した際に、コンバージョンリスナーが呼び出される問題を修正しました。</li><li>広告収益SDKコネクタから広告収益イベントを送信した際に、アプリが応答しなくなることがある問題を修正しました。</li></ul> |
| 6.9.3  <br />サポート終了：  <br />2025-09-08 | 2022-11-28 | <ul><li>コンバージョンデータ取得（GCD）の内部リクエスト構造を更新しました。**注意**：レスポンスデータに変更はありません。</li><li>アプリでConversionListenerがnullに設定されている場合に、SDKがGCDリクエストを送信する問題を修正しました。</li></ul> |
| 6.9.2  <br />サポート終了：  <br />2025-09-08 | 2022-10-02 | <ul><li>validateAndLogInAppPurchase APIを使用した購入検証のリクエストに遅延が生じる問題を修正しました。</li></ul> |
| 6.9.1  <br />サポート終了：  <br />2025-09-08 | 2022-09-19 | SDKの保守更新を行いました。 |
| 6.9.0  <br />サポート終了：  <br />2025-09-08 | 2022-09-12 | <ul><li>Xiaomi GetApps Storeリファラをサポートしました。</li><li>広告収益のレポートに使用する内部APIを更新しました。このバージョン以降は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">汎用の広告収益SDKコネクタ</Anchor>のみがサポートされます。</li></ul> |
| 6.8.2  <br />サポート終了：  <br />2025-09-08 | 2022-08-29 | <ul><li>V6.7.0で導入されたSDKのキャッシュ機構に、キャッシュされたイベントが複数回送信される重大な問題があったため、修正しました。</li></ul> |
| 6.8.1  <br />(非推奨)  <br />サポート終了：  <br />2025-09-08 | 2022-08-24 | <ul><li>**非推奨です。** V6.8.2を使用してください。</li></ul> |
| 6.8.0  <br />(非推奨)  <br />サポート終了：  <br />2025-09-08 | 2022-07-18 | <ul><li>**非推奨です。** V6.8.2を使用してください。</li><li>SDKから<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#enablelocationcollection">`enableLocationCollection`</Anchor> APIを削除しました。引き続き、アプリから<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#loglocation">`logLocation`</Anchor> APIを使用して位置情報をSDKに直接渡すことで、ユーザーの位置情報を送信できます。</li><li>SDKの`com.google.android.gms.permission.AD_ID`権限を`AndroidManifest.xml`に追加しました。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/bulletin-the-android-sdk-adds-the-ad-id-permission">こちら</Anchor>を参照してください。</li><li>R8を使用した最適化と難読化に関する問題を修正しました。</li></ul> |
| 6.7.0  <br />(非推奨)  <br />サポート終了：  <br />2025-09-08 | 2022-06-19 | <ul><li>**非推奨です。** V6.8.2を使用してください。</li><li>SDKによるAppsFlyerサーバーへのリクエストの処理方法を変更しました。この変更により、アプリの初回起動（コンバージョン）を報告するリクエストが、アプリ内イベントやその他のリクエストより優先されます。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/bulletin-adding-a-priority-queue-to-the-android-sdk">こちら</Anchor>を参照してください。</li><li>**新しいAPI：** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisablenetworkdata">`setDisableNetworkData`</Anchor>を使用すると、携帯電話ネットワークの情報（キャリア名、通信事業者名）の収集を停止できます。</li></ul> |
| 6.6.1  <br />サポート終了：  <br />2025-03-03 | 2022-05-16 | SDKの保守更新を行いました。 |
| 6.6.0  <br />サポート終了：  <br />2025-03-03 | 2022-05-01 | <ul><li>UDLの`onDeepLinking`コールバックに、ダイレクトディープリンク（既存ユーザー向け）のパラメータを追加しました。<Anchor target="_blank" href="/marketers/ja/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">詳細はこちら</Anchor>。</li></ul> |
| 6.5.4  <br />サポート終了：  <br />2025-03-03 | 2022-03-23 | SDKの保守更新を行いました。 |
| 6.5.3  <br />サポート終了：  <br />2025-03-03 | 2022-03-09 | <ul><li>**不具合の修正：** 英語以外の文字を含むユーザー招待リンクの作成に関する問題を修正しました。</li></ul> |
| 6.5.2  <br />サポート終了：  <br />2025-03-03 | 2022-01-26 | <ul><li>UDLでのディファードディープリンクのURL解決に関する問題を修正しました。</li><li>DexGuard 9.2に更新しました。</li><li>リファクタリングと内部変更を行いました。</li></ul> |
| 6.5.1  <br />サポート終了：  <br />2025-03-03 | 2021-12-29 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution#channel-name">ストア外配信でチャネルを指定するオプション</Anchor>を使用するアプリで、UDLによるディープリンクの解決に対応しました。</li></ul> |
| 6.5.0  <br />サポート終了：  <br />2025-03-03 | 2021-12-07 | <ul><li>リファクタリングと内部変更を行いました。</li></ul> |
| 6.4.3  <br />サポート終了：  <br />2025-03-03 | 2021-11-14 | <ul><li>`V6.4.2`で発生した、`LinkGenerator`で作成したリンクからURLパラメータが欠落する不具合を修正しました。</li></ul> |
| 6.4.2  <br />サポート終了：  <br />2025-03-03 | 2021-10-24 | 以下の問題を解消しました。<ul><li>`pid`パラメータが、`LinkGenerator`で生成したカスタムURLに2回追加される問題。</li><li>余分な`/`が`af_dp`の値に追加される問題。`LinkGenerator`でカスタムURIスキームを作成した場合に発生していました。</li><li>IMEIとAndroidIDのいずれか一方のみの収集をアプリが指示しても、両方が収集される問題。</li></ul> |
| 6.4.1  <br />サポート終了：  <br />2025-03-03 | 2021-10-17 | V3.5.4より前のGradleバージョンを使用した場合のコンパイルエラーを解消しました。 |
| 6.4.0  <br />サポート終了：  <br />2025-03-03 | 2021-09-12 | **新しいAPI：** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor>を使用すると、SDKによるデータ共有の対象から除外するパートナーを設定できます。<br /><br />このバージョン以降、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilter">`setSharingFilter`</Anchor>と<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforallpartners">`setSharingFilterForAllPartners`</Anchor>は非推奨です。 |
| 6.3.2<br /><br />サポート終了： 2024-08-31 | 2021-06-06 | **新しいAPI**：[`setDisableAdvertisingIdentifiers`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) |
| 6.3.1  <br />サポート終了： 2024-08-31 | 2021-05-26 | <ul><li>**新しいAPI**：[`performOnDeepLinking`](https://dev.appsflyer.com/hc/docs/conversion-data)</li><li><Anchor target="_blank" href="/marketers/ja/docs/user-invite-attribution#手順">ユーザー招待API</Anchor>を、`start`の呼び出し前、または`stop`の呼び出し後に実行できるようになりました。</li><li>**不具合の修正**：`waitForCustomerUserId`による待機状態が、`setCustomerUserId`を呼び出しても解除されない問題を修正しました。</li></ul> |
| 6.3.0  <br />サポート終了： 2024-08-31 | 2021-04-29 | <ul><li>**不具合の修正**：アプリ内イベントの送信リクエストが失敗した際に、`onConversionDataFail`が誤って呼び出される問題を修正しました。</li><li>**不具合の修正**：不正検知に使用するモーションセンサーの指標の収集に関する問題を修正しました。</li><li>**不具合の修正**：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">UDL</Anchor>の難読化に関する修正を行いました。</li><li>OneLink APIの技術的な更新を行いました。</li></ul> |
| 6.2.3  <br />サポート終了： 2024-08-31 | 2021-03-04 | SDKの保守更新を行いました。 |
| 6.2.0  <br />サポート終了： 2024-08-31 | 2021-02-07 | <ul><li>**新しいAPI**：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setpartnerdata">`setPartnerData`</Anchor></li></ul> |
| 6.1.4  <br />サポート終了： 2024-08-31 | 2021-01-12 | <ul><li>DexGuard V9をサポートしました。</li></ul> |
| 6.1.3  <br />サポート終了： 2024-08-31 | 2020-12-24 | <ul><li>**新しいAPI**：<Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor>（Movable Inkに対応）</li></ul> |
| 6.1.1  <br />サポート終了： 2024-08-31 | 2020-12-03 | <ul><li>Samsung Galaxy Storeリファラをサポートしました。</li><li>軽微な不具合の修正とパフォーマンスの向上を行いました。</li></ul> |
| 6.1.0  <br />サポート終了： 2024-08-31 | 2020-11-09 | <ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">統合ディープリンクAPI</Anchor>をサポートしました。</li></ul> |
| 6.0.1  <br />サポート終了： 2024-08-31 | 2020-10-28 | SDKの保守更新を行いました。 |
| 6.0.0  <br />サポート終了： 2024-08-31 | 2020-10-14 | <ul><li>非推奨化やメソッド名の変更を含め、SDKの機能とAPIに大幅な変更を行いました。[詳細はこちら](/docs/appsflyer-android-sdk-release-notes#android-v600-release-notes)</li></ul> |

> 📄 **関連記事**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-sdk-version-control-policy">AppsFlyer SDKのバージョン管理ポリシー</Anchor>

<div data-zendesk-anchors="h_01JVHFG6PN34YFWNZKX2CYHJV8=%E9%87%8D%E8%A6%81 end-of-support-vs-deprecated=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E7%B5%82%E4%BA%86%E3%81%A8%E9%9D%9E%E6%8E%A8%E5%A5%A8%E3%81%AE%E9%81%95%E3%81%84 h_01JVHEKR4MTFV0FDHMTQW00BCS=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E7%B5%82%E4%BA%86%E3%81%A8%E9%9D%9E%E6%8E%A8%E5%A5%A8%E3%81%AE%E9%81%95%E3%81%84 android-sdk-v6=android-sdk%E3%81%AE%E3%83%AA%E3%83%AA%E3%83%BC%E3%82%B9%E6%83%85%E5%A0%B1 h_01H9ZPCP8RWF24WAZ6YYMA1GS0=android-sdk%E3%81%AE%E3%83%AA%E3%83%AA%E3%83%BC%E3%82%B9%E6%83%85%E5%A0%B1 deprecated-versions=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E7%B5%82%E4%BA%86%E3%81%AEsdk%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 01JHFAXXV51DHADQ7P2Q6RHFX0=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E7%B5%82%E4%BA%86%E3%81%AEsdk%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 h_01HDNZ774ME3SVT89JS7R4MSKE=%E9%96%A2%E9%80%A3%E8%A8%98%E4%BA%8B" />

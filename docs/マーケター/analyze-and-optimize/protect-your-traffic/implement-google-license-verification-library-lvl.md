---
title: Googleライセンス検証ライブラリ（LVL）の実装
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2023-07-27T14:45:46Z'
  edited_at: '2026-10-21T12:38:17Z'
  id: 17329535522961
  locale: ja
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ja/articles/17329535522961
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** Googleライセンス検証ライブラリ（Google License Verification Library：LVL）を追加すると、Google Playとのライセンス関連の通信をすべて処理し、アプリの不正利用を防止できます。

## 概要

ライセンス検証ライブラリ（LVL）は、Google Playのライセンスサービスとのライセンス関連の通信をすべて処理するライブラリです。Android SDKからダウンロードして、アプリに追加できます。

LVLは、インストールが実際のGoogle Playユーザーによるものかを検証し、Protect360のアルゴリズムによる保護をさらに強化します。これにより、Google PlayとAppsFlyerのダッシュボードに表示されるインストール数の差異を減らせます。

* LVLは、Protect360をご契約のお客様のみ利用できます。 Protect360の契約がない場合、このモジュールによるライセンス検証は行われません。
* LVL は、アプリの不正利用による収益の損失を防ぎ、利用条件の遵守を確保して、アプリへの投資を保護します。

Google Playのライセンスサービスは、ユーザーがアプリを利用するためのライセンスを持っているかどうかを判定します。 Google Playでは、アプリの購入者として記録されているユーザーを、ライセンスを持つユーザーとみなします。ライセンスはアプリごとに固有のもので、アプリの保護を強化するために利用できます。<Anchor target="_blank" href="https://developer.android.com/google/play/licensing">詳細はこちら</Anchor>

AppsFlyer SDKがお客様のアプリ側でデータを収集し、Protect360がサーバー側でライセンスを検証します。オーガニック・非オーガニックを問わず、検証に失敗した不正なインストールをブロックします。 Protect360のダッシュボードとレポートでは、「ブロック理由」に「ボット」と表示されます。

## LVLの設定

<div id="add-lvl" />

<Accordion title="設定手順">

現在、設定は手動で行います。以下の情報をAppsFlyerの担当カスタマーサクセスマネージャー（CSM）に提供してください。担当CSMが手動で登録します。

**LVLを追加する手順：**

1. gradle.propertiesファイルに、以下のプロパティを定義します。

   ```http
   appsflyerSdkVersion = "YOUR_SDK_VERSION" // e.g., 6.15.2
   ```
2. build.gradleファイルで、このプロパティを動的に参照します。

   ```http
   dependencies {
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```
3. Kotlin DSLを使用する場合：

   ```http
   dependencies {
       val appsflyerSdkVersion = "<0>" // e.g., 6.15.2
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```

   > 📘 **注意**
   >
   > dependenciesセクション内でローカル変数を定義できます。これにより、LVLとAppsFlyer SDKのバージョンを揃え、両方のモジュールで同じバージョンを使用できます。

4. アプリの「ライセンスとアプリ内課金（Licensing & in-app billing）」の情報を取得します。  
   Google Play Developer Consoleで、対象アプリを選択し、「開発ツール（Development Tools）」→「サービスとAPI（Services and APIs）」の順に進みます。

   ```http
   Base64でエンコードされたRSA公開鍵
   ```
5. 担当CSMに、以下の情報を提供してください。

* 公開鍵
* アプリID
* LVLを実装した最初のアプリバージョン
* LVL（ライセンス検証ライブラリ）の実装内容が分かるスクリーンショット

</Accordion>

<div id="test-and-troubleshoot" />

<Accordion title="設定依頼後の流れ">

設定依頼を受け付けると、Protect360チームがLVL検証を検証モード（STAGING）で設定します。この段階では、LVLの検証結果はAppsFlyer社内でのみ確認できます。数日後に、AppsFlyerがデータを確認します。

**問題がない場合：**

* LVL検証を本番モード（PRODUCTION）に切り替え、トラフィックのブロックを開始します。
* Protect360チームが担当CSMに通知します。

**問題がある場合**（インストールイベントにLVL情報が含まれていない場合など）：

* LVL検証は検証モード（STAGING）のまま継続します。
* 担当CSMがお客様に状況をお知らせし、アプリへの実装に関する問題の解決を支援します。

</Accordion>

<div id="setup-process" />

<Accordion title="テストとトラブルシューティング">

アプリのデバッグ時に、AppsFlyerへの送信データに、以下の例のようなLVL情報が含まれていることを確認してください。

```json
"lvl":{
      "ttr":,<0>,
      "signature":"<1>",
      "signedData":"<2>"
   }
```

インストール時の送信データにLVL情報が含まれていない場合は、サポート担当またはSDK担当チームと連携して確認してください。

</Accordion>

## よくある質問

<div id="what-if-an-app-is-installed-from-a-store-other-than-google-play" />

<Accordion title="Google Play以外のストアからアプリをインストールした場合はどうなりますか？">

Google Play以外のストアからのインストールは、LVLによる検証もブロックも行われません。

</Accordion>

<div id="how-much-time-does-it-take-to-get-lvl-set-up" />

<Accordion title="LVLの設定にはどのくらいの時間がかかりますか？">

必要な情報を受け取ってから、LVLの設定とデータの検証が完了するまで数営業日かかります。詳しくは、[設定手順](/docs/implement-google-license-verification-library-lvl#setup-process)をご覧ください。

</Accordion>

<div id="does-lvl-affect-app-functionality" />

<Accordion title="LVLはアプリの機能に影響しますか？">

いいえ、アプリの機能には影響しません。

</Accordion>

<div id="what-is-the-difference-between-lvl-and-gpreferrer" />

<Accordion title="LVLとGoogle Playリファラ（GP-referrer）の違いは何ですか？">

LVLによるライセンス検証と、Google Playリファラの検証アルゴリズムは、検証する内容が異なります。LVLは、アプリ自体のライセンスをアプリごとに検証します。一方、Google Playリファラは、インストールされたアプリパッケージのリファラURLを通じて、Google Playストアへの遷移元の情報を取得するために使用されます。この情報には、リファラのクリック日時、インストールの開始日時、アプリバージョンなどが含まれます。つまり、LVLはユーザーがアプリを利用するためのライセンスを持っているかを確認し、Google Playリファラはインストールに関する情報が偽造されていないかを検証します。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 01H7YJ35YKDHJ2MDZSSYKMDCJ4=%E6%A6%82%E8%A6%81 set-up-lvl=lvl%E3%81%AE%E8%A8%AD%E5%AE%9A 01H7YJ35YKDW0CB9TWRBKFBCDJ=lvl%E3%81%AE%E8%A8%AD%E5%AE%9A 01H7YJ35YK585NA5F4HZN8C74K=add-lvl 01JGK7NK10ZDD6CM6Y4631FB4Q=%E6%B3%A8%E6%84%8F 01H7YJ35YKX1CVYMRZ1W8NRH7Y=test-and-troubleshoot 01H7YJ35YKMCN2E2BDWA5DD5M3=setup-process faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7YJ35YMR8PBTTSHD77WZ4AE=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7YJ35YMRZ8KRSVND1JT6JGH=what-if-an-app-is-installed-from-a-store-other-than-google-play 01H7YJ35YM11J0EG0B8PBMSPAC=how-much-time-does-it-take-to-get-lvl-set-up 01H7YJ35YMH0NM73Y1R90JDMEA=does-lvl-affect-app-functionality 01H7YJ35YM6RHCA6QP3MK0Y9J0=what-is-the-difference-between-lvl-and-gpreferrer" />

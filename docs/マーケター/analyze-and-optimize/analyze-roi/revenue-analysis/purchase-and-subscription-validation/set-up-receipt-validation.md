---
title: レシート検証の設定
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T15:14:21Z'
  edited_at: '2026-10-28T08:49:31Z'
  id: 42137474889489
  locale: ja
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ja/articles/42137474889489
---
> **概要：** アプリストアへの照会で購入・サブスクリプションの取引を検証し、正確な収益を計測することで、広告費用対効果（ROAS）を正確に把握できます。

<div id="upgrade-to-new-receipt-validation" />

## 新しいレシート検証への移行

従来のレシート検証は、**2026年9月7日**に提供を終了します。<Anchor target="_blank" href="/marketers/ja/docs/bulletin-legacy-receipt-validation-is-deprecated">「お知らせ：従来のレシート検証の廃止」</Anchor>を参照してください。アプリで従来のレシート検証を使用している場合は、以下の設定手順に従って新しいレシート検証に移行してください。設定を始める前に、主な変更点を確認し、移行に備えてください。

<div id="h_migration_key_differences" />

<Accordion title="新しいレシート検証の変更点">

| 項目 | 従来の機能 | 新しいレシート検証 |
| --- | --- | --- |
| SDKメソッド | `validateAndLogInAppPurchase`（従来版／v1） | `validateAndLogInAppPurchase`（v2）。iOS・Androidともにメソッド名は同じですが、引数の構成が変わります。 |
| 価格と通貨の指定 | SDKの呼び出し時に指定 | ストアから自動的に取得 |
| 購入の種類 | 指定不要 | `PurchaseType`パラメータが必須（*subscription*または*one-time purchase*） |
| 収益設定 | 指定不要 | 必要（収益設定ページ） |
| `af_revenue`の値の取得元 | SDKの呼び出し時に指定した値 | ストアが返す総収益。SDKの呼び出し時に指定したカスタム値は、イベントの`custom_data`オブジェクトに格納されます。 |
| 購入イベントの区分 | すべての取引を1種類の`af_purchase`イベントで記録 | 取引の種類ごとに異なるイベントで記録：`af_purchase`、`af_ars_trial_started`、`af_ars_subscription_started`および各サンドボックス用イベント |
| StoreKit 2への対応（iOS） | 非対応 | 対応 |
| 不正の除外 | 限定的 | Android・iOSで強化 |
| SDKでの提供状況 | AppsFlyer SDK v7.0.0以降では削除 | Android v6.17.5、iOS v6.17.8、プラグインv6.17.8以降で利用可能 |
| 検証済み購入イベントの記録 | 2026年9月7日まで対応 | 継続して対応 |

</Accordion>

<div id="h_migration_what_to_plan" />

<Accordion title="移行の準備">

移行を始める前に、次の点を確認してください。

* **既存のユーザーに影響を与えず、段階的に移行できます。** AppsFlyerのダッシュボードで新しいレシート検証を有効にしても、従来のメソッドを使用するバージョンのアプリには影響しません。従来版の提供が終了する2026年9月7日までは、両方を引き続き使用できます。
* <strong>移行後は収益の値が変わる場合があります。</strong>新しいレシート検証では、ストアが返す総収益を使用します。従来のレシート検証では、SDKの呼び出し時に指定した収益の値を使用していました。 SDKの呼び出し時に総収益以外の値を指定していた場合、移行後は総収益が使われるため、ダッシュボードに表示される金額や、ポストバックでパートナーに送信される金額が変わります。純収益を使用する場合は、**ROI360ストア収益**をご利用ください。<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue">「ROI360ストア収益の設定」</Anchor>を参照してください。
* **収益額の変化をユーザー獲得パートナーに伝えてください。** `af_purchase`のポストバックで総収益以外の値を受信していたアドネットワークでは、移行後に受信する金額が変わります。
* **アプリのリリース日程を計画してください。** 2026年9月7日以降は、Android v6.17.5またはiOS v6.17.8より前のSDKで作成されたバージョンのアプリを使うユーザーについて、検証済みの`af_purchase`イベントが生成されなくなります。提供終了までに大半のユーザーへ更新版が行き渡るよう、余裕を持って新しいバージョンのアプリをリリースしてください。

</Accordion>

<div id="h_migration_upgrade_path" />

<Accordion title="ROI360ストア収益への切り替え">

両機能は同じ`validateAndLogInAppPurchase`（v2）メソッドを使用するため、ROI360ストア収益に切り替える際にSDKを変更する必要はありません。購入を自動検出するためのPurchase Connectorの追加は任意です。

詳細と設定手順は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue">「ROI360ストア収益の設定」</Anchor>を参照してください。

</Accordion>

<div id="overview" />

## 概要

<div id="note" />

> 📘 **注意**
>
> レシート検証の仕組みやAppsFlyerで有効にする方法など、詳しくは<Anchor target="_blank" href="/marketers/ja/docs/about-receipt-validation">「レシート検証について」</Anchor>を参照してください。

レシート検証を設定するには、次の手順を順番に実行します。

1. ストアの認証情報の設定（iOS・Android）
   * [iOS](#手順1iosapp-store-connectのキーの設定)：AppsFlyerにApp Store Connectのキー（アプリ内課金キー、キーID、発行者ID）を設定し、レシート検証を有効にします。
   * [Android](#手順1androidサービスアカウントのキーと権限の設定)：Google Cloudのサービスアカウントを設定し、Google Play Consoleで必要な権限を付与します。その後、サービスアカウントのJSONキーをAppsFlyerにアップロードします。
2. [validateAndLog SDK APIの実装](#手順2-sdkの実装)：開発者がAppsFlyerの`validateAndLog` SDK APIを実装できるよう準備し、テスト用のサンドボックス環境を設定します。
3. [validateAndLog SDK APIの実装テスト](#手順3-sdkの実装の確認)：iOS・Androidのサンドボックスで購入とサブスクリプションをテストし、レシート検証イベントが生成され、AppsFlyerに正しく記録されることを確認します。
4. [設定の確認・更新](#手順4設定の確認更新)：製品タイプがレシート検証に設定されていることを確認し、ストアキーとSDK連携の状態を点検します。これにより、収益を継続して正確に計測できます。
5. [validateAndLog SDK APIを実装したアプリのリリース](#手順5-validateandlog-sdk-apiを実装したアプリのリリース)：`validateAndLog` SDK APIを実装した更新版のアプリをリリースします。サンドボックスのフラグが無効で、必要なアプリ内イベントが検証ルールでブロックされていないことを確認してください。

<div id="step-1-ios-set-up-app-store-connect-keys" />

## 手順1（iOS）｜App Store Connectのキーの設定

手順1では、*App Store Connect*で次の認証情報を取得し、AppsFlyerの<strong>［収益設定］</strong>ページに入力します。

* アプリ内課金キー
* キーID
* 発行者ID

**事前準備**：

* 認証情報の設定には、App Store ConnectとAppsFlyerの両方で操作が必要です。設定中は、App Store ConnectとAppsFlyerをそれぞれ別のタブで開いておいてください。
* iOSアプリには、アプリ内購入とサブスクリプションを処理するフレームワークであるStoreKit v1またはv2が必要です。

<div id="11-create-the-app-store-connect-keys" />

<Accordion title="1.1 App Store Connectのキーの作成">

iOSの認証情報を設定するには、次の手順を実行します。

1. App Store Connectで、<strong>［ユーザとアクセス］</strong>を開きます。

   <Image align="center" alt="" src="https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png" />
2. **［ユーザとアクセス］**＞<strong>［統合］</strong>に移動し、<strong>［キー］</strong>の一覧から<strong>［アプリ内課金］</strong>を選択します。

   <Image align="center" alt="" src="https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png" />
3. ［＋］をクリックし、新しいアプリ内課金キーを生成します。

   <Image align="center" alt="" src="https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png" />
4. APIキーの名前を入力します。
5. <strong>［生成］</strong>をクリックします。
6. 作成したキーの横にある<strong>［アプリ内課金キーをダウンロード］</strong>をクリックし、キーをダウンロードします。 **注意**：キーは1回しかダウンロードできません。
7. 生成したキーの**キーID**をコピーし、AppsFlyerの購入・サブスクリプション設定の<strong>［キーID］</strong>に貼り付けます。

   <Image align="center" alt="" src="https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png" />
8. **発行者ID**をコピーします。 **注意**：ページ上部に**発行者ID**が表示されない場合は、App Store Connect APIキーを作成します。アクセスレベルは任意です。作成すると、アプリ内課金キーのページ上部に発行者IDが表示されます。

   <Image align="center" alt="" src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw" />

</Accordion>

<div id="12-set-the-app-store-connect-key" />

<Accordion title="1.2 App Store Connectのキーの設定">

1. レシート検証を有効にします。 #enable-receipt-validation
2. <strong>［App Store Connectのキー］</strong>の手順で、<strong>［アプリ内課金キー］</strong>フィールドの[<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.45%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png)<strong>［アップロード］</strong>をクリックし、p8ファイルをアップロードします。
3. <strong>［App Store Connectのキー］</strong>セクションに、App Store Connectでコピーした値を貼り付けます。

   * **キーID**
   * **発行者ID**
4. <strong>［キーを検証］</strong>をクリックし、入力したキーが正しいことを確認します。 **注意**：アプリがまだApp Storeで公開されていない場合、<strong>［キーを検証］</strong>が機能しないことがあります。
5. <strong>［保存して次へ］</strong>をクリックします。

</Accordion>

<div id="step-1-android-set-up-service-account-key-and-permissions" />

## 手順1（Android）｜サービスアカウントのキーと権限の設定

手順1では、*Google Play*と*Google Cloud*で次の認証情報を取得し、AppsFlyerの<strong>［収益設定］</strong>ページに入力します。

**事前準備**：

* アプリ内購入とサブスクリプションの収益計測を設定するには、<Anchor target="_blank" href="https://cloud.google.com/">Google Cloud Platform</Anchor>、<Anchor target="_blank" href="https://play.google.com/console/">Google Play Console</Anchor>、<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">AppsFlyerの管理画面</Anchor>で操作を行います。設定中は、3つのサービスをそれぞれ別のタブで開いておくことを推奨します。
* AppsFlyerの管理画面で設定するには、管理者権限が必要です。

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1 Google PlayデベロッパーアカウントとGoogle Cloudプロジェクトのリンク">

**前提条件**：Google Play ConsoleとGoogle Cloudプロジェクトへのアクセス権。

**Google PlayデベロッパーアカウントをGoogle Cloudプロジェクトにリンクするには、次の手順を実行します**。

1. Google Play Consoleで、Google Playデベロッパーアカウントを開きます。
2. アカウントをGoogle Cloudプロジェクトにリンクします。手順は、<Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">Googleのこちらのヘルプ</Anchor>を参照してください。
3. Google Play Developer APIを有効にします。手順は、<Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">Googleのこちらのヘルプ</Anchor>を参照してください。

   <Image align="center" alt="" src="https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png" />

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="1.2 Google Cloudでのサービスアカウントの設定">

**前提条件**：Google Cloudへのアクセス権。

**サービスアカウントを設定するには、次の手順を実行します**。

1. **サービスアカウント**を作成するか、既存のサービスアカウントを使用します。

   1. <span class="af-ol-a"></span>Google Cloudの<strong>［サービスアカウント］</strong>で、<strong>［サービスアカウントを作成］</strong>をクリックします。[![](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)
   2. サービスアカウントの詳細を入力します。[![](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)
   3. メールアドレスをコピーします。[![](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)
   4. <strong>［作成して続行］</strong>をクリックします。[![](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)
   5. <strong>［このサービスアカウントにプロジェクトへのアクセスを許可する］</strong>の手順で、**Pub/Sub**のサブスクライバーロールを選択します。[![](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)
   6. **［続行］**＞<strong>［完了］</strong>の順にクリックします。

      <Image align="center" alt="" src="https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png" />
2. サービスアカウントの秘密鍵をダウンロードします。

   1. <span class="af-ol-a"></span>Google Cloudの<strong>［サービスアカウント］</strong>で、先ほど作成したアカウントを一覧から選び、<strong>［その他の操作］</strong>アイコンをクリックします。
   2. <strong>［鍵を管理］</strong>をクリックします。[![](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)
   3. **［鍵を追加］**＞<strong>［新しい鍵を作成］</strong>をクリックします。

      <Image align="center" alt="" src="https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png" />
   4. <strong>［秘密鍵の作成］</strong>ポップアップで、<strong>［キーのタイプ］</strong>から<strong>［JSON］</strong>を選択し、<strong>［作成］</strong>をクリックします。[![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)
   5. <strong>［作成］</strong>をクリックします。秘密鍵のJSONファイルがダウンロードされます。

      <Image align="center" alt="" src="https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png" />
   6. 後でAppsFlyerにアップロードするため、JSONキーファイルを保存しておきます。 **注意**！キーは必ず保存してください。後から取得することはできません。保存しなかった場合は、キーを新たに作成し直す必要があります。

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="1.3 Google Play ConsoleでのAPIアクセス権限の設定">

**前提条件**：Google Play Consoleへのアクセス権。

**注意**：サービスアカウントの認証情報と権限の設定が反映されるまで、最大24時間かかる場合があります。そのため、後の手順でエラーが発生する場合があります。

**Google Play ConsoleでAPIのアクセス権限を設定するには**：

1. Google Play Consoleの<strong>［ユーザーと権限］</strong>で、作成したサービスアカウントを探し、<strong>［新しいユーザーを招待］</strong>をクリックします。

   <Image align="center" alt="" src="https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png" />
2. 手順1.2.1.3でサービスアカウントを設定した際にコピーした**メールアドレス**を入力します。

   <Image align="center" alt="" src="https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png" />
3. <strong>［権限］</strong>セクションの<strong>［アカウントの権限］</strong>タブで、次の両方を選択します。

   * 財務データ、注文、解約に関するアンケートの回答の閲覧。
   * 注文と定期購入の管理。[![](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)
4. <strong>［アプリの権限］</strong>タブで、<strong>［アプリを追加］</strong>をクリックし、対象のアプリを選択します。必要に応じて複数のアプリを追加します。

   <Image align="center" alt="" src="https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png" />
5. <strong>［ユーザーを招待］</strong>をクリックします。

   <Image align="center" alt="" src="https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png" />
6. 確認ポップアップで、<strong>［招待状を送信］</strong>をクリックします。

   <Image align="center" alt="" src="https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png" />

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="1.4 サービスアカウントの秘密鍵のAppsFlyerへのアップロード">

[手順1.2](#12-configure-your-service-account-in-the-google-cloud-platform)でダウンロードしたGoogleのJSONキーをアップロードし、検証します。

**前提条件**：AppsFlyerの管理者権限。

**サービスアカウントの秘密鍵をAppsFlyerにアップロードするには、次の手順を実行します**。

1. <Anchor target="_blank" href="/marketers/ja/docs/about-receipt-validation#レシート検証の有効化">レシート検証を有効にします</Anchor><Anchor target="_blank" href="/marketers/ja/docs/about-receipt-validation#レシート検証の有効化">。</Anchor>
2. <strong>［サービスアカウントのキーと権限］</strong>の手順で、<strong>［GoogleのJSONキーをアップロード］</strong>フィールドの[<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.23%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png)<strong>［アップロード］</strong>をクリックします。
3. [手順1.2](#12-configure-your-service-account-in-the-google-cloud-platform)でダウンロードしたJSONファイルをアップロードします。
4. <strong>［キーを検証］</strong>をクリックします。 **注意：**

   * サービスアカウントの認証情報と権限の設定が反映されるまで、最大24時間かかる場合があります。そのため、キーの検証や検証テストの実行時にエラーが発生する場合があります。
   * 設定を早く反映させたい場合は、Google Play Consoleで任意のアプリを開き、**［収益化］**＞**［商品］**＞<strong>［定期購入／アプリ内アイテム］</strong>に移動して、変更を加えます。例えば、商品の説明を編集して保存します。通常、この操作によってアカウントの認証情報と権限がすぐに更新されます。その後、加えた変更は元に戻せます。
5. <strong>［次へ］</strong>をクリックします。 <strong>［SDKの実装］</strong>の手順が開きます。

</Accordion>

<div id="step-2-implement-sdk" />

## 手順2｜ SDKの実装

この手順では、開発者がSDKの`validateAndLog` APIを実装できるよう準備し、テスト用のサンドボックス環境を設定します。最新の`validateAndLog` APIに対応するSDKの最小バージョンは、Androidが**6.17.5**、iOSが**6.17.8**です。

validateAndLog SDK APIを実装するには、次の手順を実行します。

1. <strong>［SDKの実装］</strong>の手順で、ダッシュボードに表示される**メッセージのひな形**をコピーします。
2. コピーしたメッセージを開発者に送信します。メッセージには、次の情報が含まれます。

   * アプリ名とアプリID
   * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">SDK実装ガイド</Anchor>へのリンク。
   * サンドボックス環境の設定手順（`sandbox = true`）。
   * テスト手順（**TestFlight**を使用）。

   このメッセージに、実装からテスト開始までに開発者が必要とする情報がすべて含まれています。
3. <strong>［次へ］</strong>をクリックします。 <strong>［SDKの実装を確認］</strong>の手順が開きます。

<div id="step-3-verify-sdk-implementation" />

## 手順3｜ SDKの実装の確認

サンドボックス環境でアプリ内購入とサブスクリプションの収益連携をテストし、SDK Connectorが正しく実装され、サーバー通知が適切に設定されてAppsFlyerに届いていることを確認します。

<div id="test-sdk-implementation" />

<Accordion title="SDKの実装テスト">

過去7日間に、アプリから有効な`validateAndLog`のデータをAppsFlyerが受信したか確認するには、次の手順を実行します。

1. <strong>［SDKの実装を確認］</strong>の手順で、<strong>［SDKの実装をテスト］</strong>をクリックします。
2. AppsFlyerが最後にデータを受信した日時など、結果を確認します。この確認で分かるのは、リクエストがAppsFlyerに届いているかどうかだけです。データの完全性や正確性までは検証されません。
3. 実装を十分に検証するには、引き続き以下のテストを行ってください。

</Accordion>

<div id="sandbox-environment-considerations" />

<Accordion title="サンドボックス環境での注意点">

サンドボックス環境では、次の点に注意してください。

* validateAndLog SDK APIがAppsFlyerに記録するイベントを生成するのは、初回購入時だけです。アプリ内購入イベントの名前は`af_purchase_sandbox_sdk`です。サブスクリプションイベントの名前は`af_ars_sandbox_sdk`**です。**
* サンドボックスイベントの収益は0です。
* Androidでは、SDKでサンドボックス環境を設定していなくても、ライセンステスターによるテストでサンドボックスイベントが生成されます。

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="アプリ内購入とサブスクリプションの収益テスト">

<Image align="center" alt="" src="https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png" />

**アプリ内購入とサブスクリプションの収益をテストするには**：

1. 開発者に、実装手順に従ってvalidateAndLog SDK APIのサンドボックス環境を設定するよう依頼します。
2. <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">Google Playのライセンステスター</Anchor>と<Anchor target="_blank" href="https://developer.apple.com/testflight/">iOSのTestFlight</Anchor>で、購入またはサブスクリプションをテストします。
3. 次のいずれかの方法で、テストイベントが表示されることを確認します。

   * <Anchor target="_blank" href="/marketers/ja/docs/testing-the-sdk-integration-for-marketers#view-live-events">ライブイベントビューアー</Anchor>でイベントを確認します。
   * <Anchor target="_blank" href="/marketers/ja/docs/activity-metrics-in-my-dashboards">マイダッシュボードのアクティビティビュー</Anchor>でイベントデータを確認します。
4. 次のテストイベントを探します。

   * 購入イベントの場合は`af_purchase_sandbox_sdk`。
   * サブスクリプションイベントの場合は`af_ars_sandbox_sdk`。
5. テストイベントに、次の情報が含まれることを確認します。

   * 収益の値が**0**であること（AppsFlyerの実際のレポートに影響を与えないため）。
   * 購入した商品の収益額が`af_sandbox_revenue`パラメータに含まれ、正しい収益が報告されていること。
   * `af_validated`パラメータが`true`であること。 `af_validated`が`false`の場合は、上記の手順2に戻り、ストアから取得したキーを検証してください。
   * `af_validation_type`パラメータが`receipt_validation`であること。

</Accordion>

<div id="step-4-verify-and-update-settings" />

## 手順4｜設定の確認・更新

ここまでの設定を保存すると、現在の設定を確認する画面が開きます。この画面で、次の設定を確認・更新できます。

1. <strong>［製品タイプ］</strong>が<strong>［レシート検証］</strong>であることを確認します。
2. <strong>［App Storeで購入を検証］</strong>がオンになっていることを確認します。
3. 次の設定を確認・更新します。

   * **App Storeのキー**の設定
   * **SDK連携**の設定

<div id="step-5-release-the-app-versions-with-the-validateandlog-sdk-api" />

## 手順5｜ validateAndLog SDK APIを実装したアプリのリリース

設定とAppsFlyer validateAndLog SDK APIの実装が完了したら、実装済みのアプリをリリースするよう開発者に依頼します。

開発者が新しいバージョンをリリースする前に、次の点を確認してください。

* <Anchor target="_blank" href="/marketers/ja/docs/about-receipt-validation#レシート検証のアプリ内購入イベントとパラメータ">アプリ内購入またはサブスクリプション</Anchor>として記録したいアプリ内イベントが、AppsFlyerで設定した検証ルールによってブロックされていないこと。
* 開発者が、すべてのサンドボックスフラグを`false`に設定していること。

<Image align="center" alt="" src="https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png" width="512px" />

validateAndLog SDK APIを実装したアプリが公開されると、<Anchor target="_blank" href="/marketers/ja/docs/about-receipt-validation#レシート検証のアプリ内購入イベントとパラメータ">アプリ内購入とサブスクリプションのイベント</Anchor>が生成され、AppsFlyerのすべてのダッシュボード、集計レポート、ローデータレポートで利用できるようになります。

イベントが生成されるのは、validateAndLog SDK APIを実装したバージョンにアプリを更新したユーザーのみです。そのため、更新版のアプリがすべてのユーザーに行き渡るまでは、アプリの収益データとストアのデータに差異が生じます。

<div data-zendesk-anchors="h_migrating-from-legacy=%E6%96%B0%E3%81%97%E3%81%84%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%B8%E3%81%AE%E7%A7%BB%E8%A1%8C upgrade-to-new-receipt-validation=%E6%96%B0%E3%81%97%E3%81%84%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%B8%E3%81%AE%E7%A7%BB%E8%A1%8C whats-new-in-receipt-validation=h_migration_key_differences prepare-the-migration=h_migration_what_to_plan switch-to-roi360-store-revenue=h_migration_upgrade_path overview=%E6%A6%82%E8%A6%81 h_01KD0RY1HMV71TGDZZX7JWM3XJ=%E6%A6%82%E8%A6%81 h_01KD0RY1HMMSR4ZDW5GF4N05P1=%E6%B3%A8%E6%84%8F step-1-ios-set-up-app-store-connect-keys=%E6%89%8B%E9%A0%861iosapp-store-connect%E3%81%AE%E3%82%AD%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD0RY1HM14KNGKADCBMHJXH6=%E6%89%8B%E9%A0%861iosapp-store-connect%E3%81%AE%E3%82%AD%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD0RY1HM08AS4RGNR1QE598K=11-create-the-app-store-connect-keys h_01KD0RY1HMPJGGHQ19D5K70JSZ=12-set-the-app-store-connect-key step-1-android-set-up-service-account-key-and-permissions=%E6%89%8B%E9%A0%861android%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AE%E3%82%AD%E3%83%BC%E3%81%A8%E6%A8%A9%E9%99%90%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD0RY1HMG9DGKGEY8XVR3K7Z=%E6%89%8B%E9%A0%861android%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AE%E3%82%AD%E3%83%BC%E3%81%A8%E6%A8%A9%E9%99%90%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD0RY1HMRK0B1Z4FKD0DD2KQ=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD0RY1HN9ER2FZ7XN93SGEN9=12-configure-your-service-account-in-the-google-cloud-platform h_01KD0RY1HN03Y7T4KCNYX9FWS0=13-set-api-access-permissions-in-google-play-console h_01KD0RY1HNS6EPAKZ4YY3MZZK9=14-upload-the-service-account-private-key-to-appsflyer step-2-implement-sdk=%E6%89%8B%E9%A0%862-sdk%E3%81%AE%E5%AE%9F%E8%A3%85 h_01KD0RY1HN63X3WM1RH19W2HZ5=%E6%89%8B%E9%A0%862-sdk%E3%81%AE%E5%AE%9F%E8%A3%85 step-3-verify-sdk-implementation=%E6%89%8B%E9%A0%863-sdk%E3%81%AE%E5%AE%9F%E8%A3%85%E3%81%AE%E7%A2%BA%E8%AA%8D h_01KD0RY1HNDMSWGDW6ZQDZ5DAM=%E6%89%8B%E9%A0%863-sdk%E3%81%AE%E5%AE%9F%E8%A3%85%E3%81%AE%E7%A2%BA%E8%AA%8D h_01KD0RY1HNC4VXSRFC1ZMKWWS6=test-sdk-implementation h_01KD0RY1HNDFF6J29AHG6S4EFM=sandbox-environment-considerations h_01KD0RY1HN5EBX3VGMH5PNHTA8=test-inapp-purchase-and-subscription-revenue step-4-verify-and-update-settings=%E6%89%8B%E9%A0%864%E8%A8%AD%E5%AE%9A%E3%81%AE%E7%A2%BA%E8%AA%8D%E6%9B%B4%E6%96%B0 h_01KD0RY1HN2HZEW9ANBPNRMXPP=%E6%89%8B%E9%A0%864%E8%A8%AD%E5%AE%9A%E3%81%AE%E7%A2%BA%E8%AA%8D%E6%9B%B4%E6%96%B0 step-5-release-the-app-versions-with-the-validateandlog-sdk-api=%E6%89%8B%E9%A0%865-validateandlog-sdk-api%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%97%E3%81%9F%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%AA%E3%83%AA%E3%83%BC%E3%82%B9 h_01KD0RY1HNECTDNNHK78F9KDPS=%E6%89%8B%E9%A0%865-validateandlog-sdk-api%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%97%E3%81%9F%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%AA%E3%83%AA%E3%83%BC%E3%82%B9" />

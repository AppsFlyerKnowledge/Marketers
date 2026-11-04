---
title: ROI360ストア収益の設定
metadata:
  keywords:
    - Premium
    - Advertisters
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-22T11:05:11Z'
  edited_at: '2026-10-28T08:49:35Z'
  id: 42158608158353
  locale: ja
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ja/articles/42158608158353
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** AppsFlyerのROI360ストア収益を設定する方法を説明します。

<div id="important" />

> 🚧 **重要**
>
> ROI360ストア収益は、ROI360の有料プランをご契約のお客様のみ利用できます。契約プランの確認やアップグレードについては、担当のカスタマーサクセスマネージャー（CSM）にお問い合わせください。

<div id="overview" />

## 概要

<div id="note" />

> 📘 **注意**
>
> ROI360の仕組みやAppsFlyerで有効にする方法など、詳しくは<Anchor target="_blank" href="/marketers/ja/docs/about-roi360-store-revenue">「ROI360ストア収益について」</Anchor>を参照してください。

ROI360ストア収益を設定するには、次の手順を順番に実行します。

1. ストアの認証情報の設定（iOS・Android）：
   * [iOS：](#手順1iosapp-store-connectのキーの設定) App Store Connectのキー（アプリ内課金キー、キーID、発行者ID）をAppsFlyerに設定します。
   * [Android](#手順1androidサービスアカウントのキーと権限の設定)：Google Cloudのサービスアカウントを設定し、Google Play Consoleで必要な権限を付与します。その後、サービスアカウントのJSONキーをAppsFlyerにアップロードします。
2. サーバー通知の設定（iOS・Android）：
   * [iOS](#手順2iosapp-storeのサーバー通知の設定)：App Storeのサーバー通知を設定し、連携を検証します。通知はAppsFlyerに直接送信するか（推奨）、自社のエンドポイントから転送します。
   * [Android](#手順2androidgoogle-playのサーバー通知の設定)：Google Playのリアルタイムデベロッパー通知（RTDN）を設定します。Google PlayからAppsFlyerに直接送信するか（推奨）、Pub/Sub経由で転送します。
3. [SDK Connectorの実装](#手順3sdk-connectorの実装)：開発者がAppsFlyer Purchase SDK Connectorを実装できるよう準備します。
4. [SDKの実装の確認](#手順4sdkの実装の確認)：両プラットフォームのサンドボックスで購入とサブスクリプションをテストし、SDKイベントとサーバー通知がAppsFlyerに正しく届き、処理されることを確認します。
5. [設定の確認・更新](#手順5設定の確認更新)：購入の検証、返金への対応、サブスクリプションの計測、ストア連携の状態を確認します。これにより、各プラットフォームの収益を継続して正確に紐づけられます。
6. [アプリのリリース](#手順6sdk-connectorを実装したアプリのリリース)：SDK Connectorを実装した更新版のアプリをリリースします。サンドボックスのフラグが無効で、必要な収益イベントが検証ルールによって許可されていることを確認してください。

<div id="step-1-ios-set-up-app-store-connect-keys" />

## 手順1（iOS）｜App Store Connectのキーの設定

手順1では、App Store Connectで次の認証情報を取得し、AppsFlyerの［収益設定］ページに入力します。

* アプリ内課金キー
* キーID
* 発行者ID

**事前準備**：

認証情報の設定には、App Store ConnectとAppsFlyerの両方で操作が必要です。設定中は、App Store ConnectとAppsFlyerをそれぞれ別のタブで開いておいてください。

<div id="11-create-the-app-store-connect-keys" />

<Accordion title="1.1 App Store Connectのキーの作成">

iOSの認証情報を設定するには、次の手順を実行します。

1. App Store Connectで、<strong>［ユーザとアクセス］</strong>を開きます。

   [![](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)
2. **［ユーザとアクセス］**＞<strong>［統合］</strong>に移動し、<strong>［キー］</strong>の一覧から<strong>［アプリ内課金］</strong>を選択します。

   [![](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)
3. ［＋］をクリックし、新しいアプリ内課金キーを生成します。

   [![](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)
4. APIキーの名前を入力します。
5. <strong>［生成］</strong>をクリックします。
6. 作成したキーの横にある<strong>［アプリ内課金キーをダウンロード］</strong>をクリックし、キーをダウンロードします。 **注意**：キーは1回しかダウンロードできません。
7. 生成したキーの**キーID**をコピーし、AppsFlyerの購入・サブスクリプション設定の<strong>［キーID］</strong>に貼り付けます。

   [![](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)
8. **発行者ID**をコピーします。 **注意**：ページ上部に**発行者ID**が表示されない場合は、App Store Connect APIキーを作成します。アクセスレベルは任意です。作成すると、アプリ内課金キーのページ上部に発行者IDが表示されます。

   [![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)

</Accordion>

<div id="12-set-the-app-store-connect-key-in-appsflyer" />

<Accordion title="1.2 AppsFlyerでのApp Store Connectのキーの設定">

1. <Anchor target="_blank" href="/marketers/ja/docs/about-roi360-store-revenue#roi360ストア収益の有効化">ROI360ストア収益を有効にします</Anchor>。
2. <strong>［App Store Connectのキー］</strong>の手順で、<strong>［アプリ内課金キー］</strong>フィールドの[<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png)<strong>［アップロード］</strong>をクリックし、p8ファイルをアップロードします。
3. <strong>［App Store Connectのキー］</strong>セクションに、App Store Connectでコピーした値を貼り付けます。

   * **キーID**

   * **発行者ID**
4. <strong>［キーを検証］</strong>をクリックし、入力したキーが正しいことを確認します。 <strong>注意：［キーを検証］</strong>は、アプリがまだApp Storeで公開されていない場合、機能しないことがあります。
5. <strong>［保存して次へ］</strong>をクリックします。

</Accordion>

<div id="step-1-android-set-up-service-account-key-and-permissions" />

## 手順1（Android）｜サービスアカウントのキーと権限の設定

手順1では、App Store Connectで次の認証情報を取得し、AppsFlyerの［収益設定］ページに入力します。

**事前準備**：

* アプリ内購入とサブスクリプションの収益計測を設定するには、<Anchor target="_blank" href="https://cloud.google.com/">Google Cloud Platform</Anchor>、<Anchor target="_blank" href="https://play.google.com/console/">Google Play Console</Anchor>、<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">AppsFlyerの管理画面</Anchor>で操作を行います。設定中は、3つのサービスをそれぞれ別のタブで開いておくことを推奨します。
* AppsFlyerの管理画面で設定するには、管理者権限が必要です。

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1｜ Google PlayデベロッパーアカウントとGoogle Cloudプロジェクトのリンク">

**前提条件**：Google Play ConsoleとGoogle Cloudプロジェクトへのアクセス権。

**Google PlayデベロッパーアカウントをGoogle Cloudプロジェクトにリンクするには、次の手順を実行します**。

1. Google Play Consoleで、Google Playデベロッパーアカウントを開きます。
2. アカウントをGoogle Cloudプロジェクトにリンクします。手順は、<Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">Googleのこちらのヘルプ</Anchor>を参照してください。
3. Google Play Developer APIを有効にします。手順は、<Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">Googleのこちらのヘルプ</Anchor>を参照してください。

   [![](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="1.2｜ Google Cloudでのサービスアカウントの設定">

**前提条件**：Google Cloudへのアクセス権。

**サービスアカウントを設定するには、次の手順を実行します**。

1. **サービスアカウント**を作成するか、既存のサービスアカウントを使用します。
   1. Google Cloudの<strong>［サービスアカウント］</strong>で、<strong>［サービスアカウントを作成］</strong>をクリックします。

      [![](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)
   2. サービスアカウントの詳細を入力します。

      [![](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)
   3. メールアドレスをコピーします。

      [![](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)
   4. <strong>［作成して続行］</strong>をクリックします。

      [![](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)
   5. <strong>［このサービスアカウントにプロジェクトへのアクセスを許可する］</strong>の手順で、**Pub/Sub**のサブスクライバーロールを選択します。

      [![](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)
   6. **［続行］**＞<strong>［完了］</strong>の順にクリックします。

      [![](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)
2. **サービスアカウントの秘密鍵**をダウンロードします。
   1. Google Cloudの<strong>［サービスアカウント］</strong>で、先ほど作成したアカウントを一覧から選び、<strong>［その他の操作］</strong>アイコンをクリックします。
   2. <strong>［鍵を管理］</strong>をクリックします。

      [![](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)
   3. **［鍵を追加］**＞<strong>［新しい鍵を作成］</strong>をクリックします。

      [![](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)
   4. <strong>［秘密鍵の作成］</strong>ポップアップで、<strong>［キーのタイプ］</strong>から<strong>［JSON］</strong>を選択し、<strong>［作成］</strong>をクリックします。

      [![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)
   5. <strong>［作成］</strong>をクリックします。秘密鍵のJSONファイルがダウンロードされます。

      [![](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)
   6. 後でAppsFlyerにアップロードするため、JSONキーファイルを保存しておきます。 **注意**！キーは必ず保存してください。後から取得することはできません。保存しなかった場合は、キーを新たに作成し直す必要があります。

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="1.3｜ Google Play ConsoleでのAPIアクセス権限の設定">

**前提条件**：Google Play Consoleへのアクセス権。

**注意**：サービスアカウントの認証情報と権限の設定が反映されるまで、24時間ほどかかる場合があります。そのため、後の手順でエラーが発生する場合があります。

**Google Play ConsoleでAPIのアクセス権限を設定するには**：

1. Google Play Consoleの<strong>［ユーザーと権限］</strong>で、作成したサービスアカウントを探し、<strong>［新しいユーザーを招待］</strong>をクリックします。

   [![](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)
2. 手順1.2.1.3でサービスアカウントを設定した際にコピーした**メールアドレス**を入力します。

   [![](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)
3. <strong>［権限］</strong>セクションの<strong>［アカウントの権限］</strong>タブで、次の両方を選択します。

   * 財務データ、注文、解約に関するアンケートの回答の閲覧。
   * 注文と定期購入の管理。[![](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)
4. <strong>［アプリの権限］</strong>タブで、<strong>［アプリを追加］</strong>をクリックし、対象のアプリを選択します。必要に応じて複数のアプリを追加します。

   [![](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)
5. <strong>［ユーザーを招待］</strong>をクリックします。

   [![](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)
6. 確認ポップアップで、<strong>［招待状を送信］</strong>をクリックします。

   [![](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="1.4｜サービスアカウントの秘密鍵のAppsFlyerへのアップロード">

[手順1.2](#12-configure-your-service-account-in-the-google-cloud-platform)でダウンロードしたGoogleのJSONキーをアップロードし、検証します。

**前提条件**：AppsFlyerの管理者権限。

**サービスアカウントの秘密鍵をAppsFlyerにアップロードするには、次の手順を実行します**。

1. <Anchor target="_blank" href="/marketers/ja/docs/about-roi360-store-revenue#roi360ストア収益の有効化">ROI360ストア収益を有効にします</Anchor>。
2. <strong>［サービスアカウントのキーと権限］</strong>の手順で、<strong>［GoogleのJSONキーをアップロード］</strong>フィールドの[<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.2%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png)**アップロードアイコン**をクリックします。
3. [手順1.2](#12-configure-your-service-account-in-the-google-cloud-platform)でダウンロードしたJSONファイルをアップロードします。
4. <strong>［キーを検証］</strong>をクリックします。**注意：**
   * サービスアカウントの認証情報と権限の設定が反映されるまで、最大24時間かかる場合があります。そのため、キーの検証や検証テストの実行時にエラーが発生する場合があります。
   * 設定を早く反映させたい場合は、Google Play Consoleで任意のアプリを開き、**［収益化］**＞**［商品］**＞<strong>［定期購入／アプリ内アイテム］</strong>に移動して、変更を加えます。例えば、商品の説明を編集して保存します。通常、この操作によってアカウントの認証情報と権限がすぐに更新されます。その後、加えた変更は元に戻せます。
5. <strong>［保存して次へ］</strong>をクリックします。

</Accordion>

<div id="step-2-ios-set-up-app-store-server-notifications" />

## 手順2（iOS）｜App Storeのサーバー通知の設定

AppsFlyerがApp Storeの通知を受信する方法を設定します。

* App Store Connectに、すでにApp Storeのサーバー通知用エンドポイント（自社のバックエンドや別のサービスなど）を設定している場合は、<strong>方法1（推奨）</strong>または**方法2**を選択します。
* App Store Connectにまだエンドポイントを設定していない場合は、**方法1**を選択します。

<div id="option-1-recommended---appsflyer-as-the-primary-endpoint" />

#### 方法1（推奨）｜通知の最初の送信先をAppsFlyerにする

App Store Connectの既存の通知URLをAppsFlyerのエンドポイントに置き換え、従来のエンドポイントをAppsFlyer側で転送先として追加します。既存のサブスクリプションの処理やワークフローは、そのまま利用できます。

この方法では、通知は次のように送信されます。

1. App Store ConnectがAppsFlyerに通知を送信します。
2. AppsFlyerがROI360の収益計測に必要な処理を行います。
3. AppsFlyerがすべての通知を既存のエンドポイントに**リアルタイムで**転送します。

この方法を使用するには、手順[2.1](#21-copy-the-appsflyer-server-notifications-endpoint)、[2.2](#22-send-notifications-directly-to-appsflyer)、[2.4](#24-test-the-server-notifications-integration)を実行します。

<div id="option-2---your-endpoint-as-the-primary-endpoint" />

#### 方法2｜通知の最初の送信先を自社のエンドポイントにする

既存のエンドポイントを最初の送信先として使い続ける場合は、自社サーバーからApp Storeのサーバー通知をAppsFlyerに転送するよう設定します。

この方法を使用するには、手順2.1と2.2を省略し、[2.3](#23--optional--forward-notifications-from-your-endpoint-to-appsflyer)と[2.4](#24-test-the-server-notifications-integration)を実行します。

<div id="note-1" />

> 📘 **注意**
>
> Appleで設定できるApp Storeのサーバー通知用エンドポイントは、アプリごとに1つです。購入やサブスクリプションに関する通知だけでなく、すべての種類の通知がそこに送信されます。 AppsFlyerは、購入とサブスクリプションの通知を使って収益を計測します。その他の通知には、Appleから再送されないよう受信確認を返しますが、通知の内容に応じた処理や操作は行いません。
>
> 購入やサブスクリプション以外の通知（同意に関する通知など）をアプリで使用する場合は、自社サーバーにも必ず届くようにしてください。
>
> * **方法1：** AppsFlyerを最初の送信先として使い、転送を有効にします（手順2.1）。 AppsFlyerは、自身が処理しない種類も含め、すべての通知をAppleから受信した内容のまま、自社のエンドポイントにリアルタイムで転送します。
> * **方法2：** 自社のエンドポイントを最初の送信先として使います。自社サーバーがすべての種類の通知を直接受信・処理し、購入とサブスクリプションの通知をAppsFlyerに転送します。

<div id="21-copy-the-appsflyer-server-notifications-endpoint" />

<Accordion title="2.1 AppsFlyerのサーバー通知用エンドポイントのコピー">

AppsFlyerのサーバー通知用エンドポイントをコピーするには、次の手順を実行します。

1. <strong>AppsFlyerで、［App Storeのサーバー通知］</strong>の手順を開き、AppsFlyerのサーバー通知用エンドポイントをコピーします。
2. 従来のApp Storeのサーバー通知用エンドポイントにAppsFlyerから通知を転送する場合は、**［通知のコピーを自社サーバーに転送］を選択します（方法1のみ）。**
3. 表示されたテキストボックスに、通知の転送先エンドポイントを入力します。

</Accordion>

<div id="22-send-notifications-directly-to-appsflyer" />

<Accordion title="2.2 通知をAppsFlyerに直接送信">

通知をAppsFlyerに直接送信するには、App Storeのサーバー通知の最初の送信先をAppsFlyerに設定します。

1. **App Store Connect**の<strong>［アプリ情報］</strong>セクションで、<strong>［App Storeサーバ通知］</strong>までスクロールし、<strong>［本番環境サーバURL］</strong>の横にある<strong>［編集］</strong>をクリックします。

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. [AppsFlyerからコピーしたサーバー通知用エンドポイント](#21-copy-the-appsflyer-server-notifications-endpoint)を貼り付け、<strong>［バージョン2の通知］</strong>を選択して、<strong>［保存］</strong>をクリックします。 **注意：** バージョン1の通知には対応していません。 App Store Connectに通知のバージョンの選択肢が表示されない場合は、すでにバージョン2を使用しています。

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. <strong>［アプリ情報］</strong>セクションで、<strong>［App Storeサーバ通知］</strong>までスクロールし、<strong>［サンドボックスサーバURL］</strong>の横にある<strong>［編集］</strong>をクリックします。

   [![](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)
4. [AppsFlyerからコピーしたサーバー通知用エンドポイント](#21-copy-the-appsflyer-server-notifications-endpoint)を貼り付け、<strong>［バージョン2の通知］</strong>を選択して、<strong>［保存］</strong>をクリックします。**注意：** バージョン1の通知には対応していません。 App Store Connectに通知のバージョンの選択肢が表示されない場合は、すでにバージョン2を使用しています。

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)

</Accordion>

<div id="23--optional--forward-notifications-from-your-endpoint-to-appsflyer" />

<Accordion title="2.3 ［任意］自社のエンドポイントからAppsFlyerに通知を転送">

App Storeのサーバー通知をAppsFlyerに直接送信せず、自社のエンドポイントを最初の送信先として使い続ける場合にのみ、この手順を実行します。

この方法は推奨される設定ではなく、バックエンド側での実装が必要です。上記の手順**2.2**でAppsFlyerを最初の送信先に設定済みの場合は、この手順を省略してください。

自社のエンドポイントからAppsFlyerにサーバー通知を転送するには、次の手順を実行します。

1. **App Store Connect**の<strong>［アプリ情報］</strong>セクションで、<strong>［App Storeサーバ通知］</strong>までスクロールし、<strong>［本番環境サーバURL］</strong>の横にある<strong>［編集］</strong>をクリックします。

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. **自社サーバーのエンドポイントURL**を貼り付けます。

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. **［バージョン2の通知］を選択します。注意：** バージョン1の通知には**対応していません**。 App Store Connectに通知のバージョンの選択肢が表示されない場合は、すでにバージョン2を使用しています。
4. <strong>［保存］</strong>をクリックします。
5. **App Store Connect**の<strong>［アプリ情報］</strong>セクションで、<strong>［App Storeサーバ通知］</strong>までスクロールし、<strong>［サンドボックスサーバURL］</strong>の横にある<strong>［編集］</strong>をクリックします。

   [![](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)
6. **自社サーバーのエンドポイントURL**を貼り付けます。

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)
7. **［バージョン2の通知］を選択します。注意：** バージョン1の通知には**対応していません**。
8. <strong>［保存］</strong>をクリックします。
9. Appleのサーバー通知をAppsFlyerの通知用エンドポイントURLに転送するよう、バックエンドを設定します。リクエストは、Appleから受信したApp Storeのデータと完全に一致する必要があります。<Anchor target="_blank" href="https://developer.apple.com/documentation/appstoreserverapi/signedpayload#discussion">Appleの形式要件</Anchor>を参照してください。

</Accordion>

<div id="24-test-the-server-notifications-integration" />

<Accordion title="2.4 サーバー通知の連携テスト">

App Storeのサーバー通知をAppsFlyerが正しく受信しているか確認する場合や、エンドポイントを設定したばかりで通知がまだ届いていない場合は、次の手順を実行します。

1. AppsFlyerで、<strong>［App Storeのサーバー通知］</strong>の手順を開きます。
2. <strong>［連携をテスト］</strong>をクリックします。 AppsFlyerがAppleにテスト通知をリクエストし、過去7日間にAppleから有効な通知を受信したか確認して、次のいずれかを表示します。

   * 有効な通知を受信したことを示す確認メッセージ。
   * 通知が見つからなかったことを示すステータスメッセージ。

   <div id="note-2" />

   > 📘 **注意**
   >
   > Appleがテストメッセージを送信するまでに、数秒かかる場合があります。


   * ステータスが無効のままの場合は、少し待ってから再試行してください。
   * テストに成功したら、または次に進む準備ができたら、<strong>［保存して次へ］</strong>をクリックします。

</Accordion>

<div id="step-2-android-set-up-google-play-server-notifications" />

## 手順2（Android）｜Google Playのサーバー通知の設定

Google Playからアプリ内購入とサブスクリプションの収益データを受信する方法として、次のいずれかを選択します。

* （推奨）Google PlayからAppsFlyerに通知を直接送信する。この方法では、自社のエンドポイントに通知のコピーを転送することはできません。この方法を選択する場合は、[「Google Playの通知をAppsFlyerに直接送信」](#21-send-google-play-notifications-directly-to-appsflyer)を参照してください。
* Google Playからまず自社に通知を送信し、その後AppsFlyerに転送する。この方法を選択する場合は、[「Google Playの通知をAppsFlyerに転送」](#22--optional--forward-google-play-notifications-to-appsflyer)を参照してください。

**前提条件**：Google Play ConsoleとAppsFlyerの管理画面へのアクセス権。

<div id="21-send-google-play-notifications-directly-to-appsflyer" />

<Accordion title="2.1 Google Playの通知をAppsFlyerに直接送信">

1. AppsFlyerで手順2<strong>［Google Playのサーバー通知の設定］</strong>を開き、<strong>［AppsFlyerのトピックでGoogleからRTDNメッセージを直接受信］</strong>を選択します。
2. AppsFlyerのトピックをクリップボードにコピーします。
3. **Google Play Console**＞<strong>［ホーム］</strong>で、対象のアプリを選択して開きます。ダッシュボードが開きます。

   [![](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)
4. **［Google Playで収益化］**＞<strong>［収益化の設定］</strong>に移動し、<strong>［Google Play Billing］</strong>セクションで、<strong>［リアルタイム通知を有効にする］</strong>にチェックが入っていることを確認します。

   [![](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)
5. <strong>［トピック名］</strong>フィールドに、コピーしたAppsFlyerのトピックアドレスを貼り付けます。

   [![](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)
6. <strong>［通知の内容］</strong>で、<strong>［定期購入、無効になった購入、すべての1回限りの購入商品］</strong>を選択します。

   [![](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)
7. <strong>［変更を保存］</strong>をクリックします。設定が反映されるまで、24時間ほどかかる場合があります。そのため、反映を待ってからテストしてください。

</Accordion>

<div id="22--optional--forward-google-play-notifications-to-appsflyer" />

<Accordion title="2.2 ［任意］Google Playの通知をAppsFlyerに転送">

**注意**：この手順は、Google PlayからAppsFlyerへ直接通知を送信する推奨方法を選択しなかった場合にのみ実行します。推奨方法に従い、Google PlayのRTDNメッセージをAppsFlyerが直接受信するトピックを作成済みの場合は、この手順を省略してください。

既存のPub/SubトピックにAppsFlyerをサブスクライバーとして追加する場合は、以下の手順に進みます。

**前提条件**：Google CloudとAppsFlyerの管理画面へのアクセス権。

**Google Playの通知をAppsFlyerに転送するには**：

1. AppsFlyerのサイドメニューから<strong>［設定］</strong>＞<strong>［収益設定］</strong>に移動します。
2. 対象のアプリを選択します。
3. <strong>［購入・サブスクリプション］</strong>タブで、<strong>［自社のRTDNトピックのメッセージをAppsFlyerに転送］</strong>を選択します。
4. エンドポイントURLをクリップボードにコピーします。
5. Google Cloudで対象のプロジェクトを開き、**Pub/Sub**を検索します。

   [![](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)
6. **Pub/Sub**の<strong>［トピック］</strong>セクションを開き、定期購入用の専用Pub/Subトピックがあることを確認します。

   [![](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)
7. **Pub/Sub**の<strong>［サブスクリプション］</strong>セクションで、<strong>［サブスクリプションを作成］</strong>をクリックします。

   [![](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)
8. **サブスクリプションID**を入力します。

   [![](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)
9. ドロップダウンから、該当する定期購入用のPub/Subトピックを選択します。

   [![](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)
10. <strong>［配信タイプ］</strong>で<strong>［プッシュ］</strong>を選択します。

    [![](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)
11. AppsFlyerでコピーした**エンドポイントURL**を貼り付けます。

    [![](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)
12. <strong>［有効期限］</strong>で<strong>［無期限］</strong>を選択します。

    [![](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)
13. <strong>［作成］</strong>をクリックします。

    [![](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)
14. <strong>［サブスクリプション］</strong>セクションに移動し、対象のトピック名をクリックします。

    [![](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)
15. トピック名をクリップボードにコピーします。

    [![](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)
16. **Google Play Console**で、**［Google Playで収益化］**＞<strong>［収益化の設定］</strong>に移動します。 <strong>［Google Play Billing］</strong>セクションの［トピック名］に、前の手順でコピーしたトピック名を貼り付けます。

    [![](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)
17. <strong>［通知の内容］</strong>で、<strong>［定期購入、無効になった購入、すべての1回限りの購入商品］</strong>を選択します。

    [![](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)
18. <strong>［変更を保存］</strong>をクリックします。設定が反映されるまで、24時間ほどかかる場合があります。そのため、反映を待ってからテストしてください。

</Accordion>

<div id="23-send-a-test-notification-from-google-play-console" />

<Accordion title="2.3 Google Play Consoleからテスト通知を送信">

Google Playのリアルタイムデベロッパー通知（RTDN）をAppsFlyerが正しく受信するか確認するため、Google Play Consoleからテスト通知を送信します。

1. <strong>［テスト通知を送信］</strong>をクリックします。 AppsFlyer用に設定したPub/Subトピックに、テスト用のRTDNメッセージが送信されます。

   <Image alt="image (33).png" src="https://files.readme.io/4d7aa79eb963373223cfde1d32db16b739119a86d8d4f0cf6ce026d42a709bf3-42170040528657.png" width="1444px" />
2. <strong>［Google Play Billing］</strong>で、［トピック名］セクションを探します。
3. 左側のメニューから<strong>［Google Playで収益化］</strong>＞<strong>［収益化の設定］</strong>に移動します。
4. Google Play Consoleを開きます。

<div id="24-confirm-notification-delivery-in-appsflyer" />

<Accordion title="2.4 AppsFlyerで通知の受信を確認">

1. テストに成功したら、または次に進む準備ができたら、<strong>［保存して次へ］</strong>をクリックします。
2. 結果：AppsFlyerに、過去7日間に通知を受信したかどうかが表示されます。
   * 受信に成功している場合は、最後に受信した通知の日時が表示されます。
   * 通知を受信していない場合は、過去7日間に通知が見つからなかったことが表示されます。
   * ステータスが表示されない場合は、Pub/Subの設定を見直し、テスト通知を再送信してください。
3. <strong>［Google Playのサーバー通知］</strong>の手順で、<strong>［連携をテスト］</strong>をクリックします。

</Accordion>

</Accordion>

<div id="step-3-implement-sdk-connector" />

## 手順3｜SDK Connectorの実装

この手順では、開発者がAppsFlyer Purchase SDK Connectorを実装できるよう準備し、テスト用のサンドボックス環境を設定します。

SDK Connectorを実装するには、次の手順を実行します。

1. <strong>［SDK Connectorの実装］</strong>の手順で、ダッシュボードに表示される**メッセージのひな形**をコピーします。
2. コピーしたメッセージを開発者に送信します。メッセージには、次の情報が含まれます。
   * アプリ名とアプリID
   * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">SDK実装ガイド</Anchor>へのリンク。
   * サンドボックス環境の設定手順（`sandbox = true`）
   * テスト手順（**TestFlight**を使用）

このメッセージに、実装からテスト開始までに開発者が必要とする情報がすべて含まれています。

<div id="note-3" />

> 📘 **注意**
>
> SDK Connectorは、取引を自動的に検出します。代わりに、`validateAndLog` SDKメソッドを実装して、取引ごとに手動で記録することもできます。ただし、このメソッドではSDK Connectorの一部の機能を利用できません。 SDK連携の2つの方法について詳しくは、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">DevHubのドキュメント</Anchor>を参照してください。

<div id="step-4-verify-sdk-implementation" />

## 手順4｜SDKの実装の確認

サンドボックス環境で購入とサブスクリプションの収益計測をテストし、SDK Connectorの実装とサーバー通知の設定が正しく、通知がAppsFlyerに届くことを確認します。

<div id="test-sdk-implementation" />

<Accordion title="SDKの実装テスト">

過去7日間に、アプリから有効な購入・サブスクリプションのイベントデータをAppsFlyerが受信したか確認するには、次の手順を実行します。

1. <strong>［SDKの実装を確認］</strong>の手順で、<strong>［SDKの実装をテスト］</strong>をクリックします。
2. AppsFlyerが最後にデータを受信した日時など、結果を確認します。

   <div id="note-4" />

   > 📘 **注意**
   >
   > このテストで分かるのは、リクエストがAppsFlyerに届いているかどうかだけです。データの完全性や正確性までは検証されません。

3. 実装を十分に検証するには、引き続き以下のテストを行ってください。

</Accordion>

<div id="sandbox-events-and-parameters" />

<Accordion title="サンドボックスのイベントとパラメータ">

* SDK Connectorがイベントを生成するのは、サンドボックスでの初回取引時のみです。
  * アプリ内購入：`af_purchase_sandbox_sdk`
  * サブスクリプション：`af_ars_sandbox_sdk`
* AppsFlyerがサーバー通知を処理するのは、元の取引のSDKイベントが記録されている場合のみです。
  * アプリ内購入のS2Sイベント：`af_purchase_sandbox_s2s`
  * サブスクリプションのS2Sイベント：`af_ars_sandbox_s2s`
* 元の取引がSDKで記録されていない場合は、 S2Sイベントは生成されません。

**iOSでの注意点**

* `af_purchase_sandbox_sdk`に`af_sandbox_revenue`が含まれる場合は、本番環境の`af_purchase`に対応します。
* 収益が含まれない場合は、本番環境の`af_purchase_free`に対応します。

**Androidでの注意点**

* **ライセンステスター**による購入では、常にサンドボックスイベントが生成されます。 SDKでサンドボックスモードが設定されていない場合も同様です。

**テストイベントに必要なパラメータ**

サンドボックスの購入イベントに、必ず次の情報が含まれるようにします。

* **収益＝0**（実際のレポートに影響を与えないため）。
* `af_sandbox_revenue`＝実際の商品価格（正しい収益を紐づけるため）。
* `af_validated`**＝true**。 `false`の場合は、前の手順に戻ってストアのキーを検証してください。
* `af_validation_type` = `receipt_validation`.

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="アプリ内購入とサブスクリプションの収益テスト">

**前提条件**：

* iOSでは、App Store Connectの［App Storeサーバ通知］で、AppsFlyerのエンドポイントが<strong>［サンドボックスサーバURL］</strong>に設定されていることを確認します。

  [![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

**アプリ内購入とサブスクリプションの収益をテストするには**：

1. 開発者に、<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-android-purchase-connector#-testing-the-integration">Android</Anchor>、<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-apple-purchase-connector#-testing-the-implementation-in-sandbox">iOS</Anchor>、<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-purchase-connector/blob/master/docs/purchaseConnectorUnity.md#testing-the-implementation-in-sandbox">Unity</Anchor>の実装手順に従い、SDK Connectorのサンドボックス環境を設定するよう依頼します。
2. <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">Google Playのライセンステスター</Anchor>で、購入またはサブスクリプションの開始をテストします。 iOSでは、<Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight</Anchor>を使用します。**注意**：サブスクリプション商品をテストできるのは、端末ごとに1回のみです。同じ端末では、同じサブスクリプション商品のテスト購入を複数回記録できません。 2回目以降の試行は記録されません。
3. <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">Google Playのライセンステスター</Anchor>と<Anchor target="_blank" href="https://developer.apple.com/testflight/">iOSのTestFlight</Anchor>で、返金、サブスクリプションの更新、または自動更新の停止のイベントをテストします。**注意**：サブスクリプション商品をテストする場合は、ストアからのサーバー通知がAppsFlyerに届くまでお待ちください。通常は、初回購入の数分後に届きます。
4. <strong>［SDK Connectorの実装を確認］</strong>の手順で、<strong>［SDKの実装をテスト］</strong>をクリックします。過去7日間にPurchase ConnectorからSDKのデータを正常に受信したかどうかが表示されます。
5. 次のいずれかの方法で、テストイベントが表示されることを確認します。

   * <Anchor target="_blank" href="/marketers/ja/docs/testing-the-sdk-integration-for-marketers#view-live-events">ライブイベントビューアー</Anchor>でイベントを確認します。

   * <Anchor target="_blank" href="/marketers/ja/docs/activity-metrics-in-my-dashboards">マイダッシュボードのアクティビティビュー</Anchor>でイベントデータを確認します。
6. AppsFlyerのアクティビティダッシュボードにイベントが表示されることを確認します。 AppsFlyerで<strong>［分析］＞［アクティビティ］</strong>を開き、<strong>［アクティビティの推移］</strong>グラフの［アプリ内イベント］タブで、テストするイベントを選択します。自動更新サブスクリプションの購入イベントの名前は`af_ars_s2s_sandbox`です。イベントには、次の情報が含まれます。
   * 収益の値が0であること（AppsFlyerの実際のレポートに影響を与えないため）。
   * 購入した商品の収益額が`af_sandbox_revenue`パラメータに含まれ、正しい収益が報告されていること。

</Accordion>

<div id="step-5-verify-and-update-settings" />

## 手順5｜設定の確認・更新

最後の手順で設定を保存すると、現在の設定を確認する画面が開きます。この画面で、次の設定を確認・更新できます。

1. <strong>［App Storeで購入を検証］</strong>のトグルがオンになっていることを確認します。
2. <strong>［購入］</strong>で、次のオプションを確認します。
   * **［購入の重複を防いでデータを正確に保つ］**：報告済みの取引の重複記録を防ぎます。
   * **［返金、キャンセル、マイナスの収益を自動計測］**：返金に関するイベントを計測し、マイナスの収益として記録します。
   * **［ファミリー共有による収益の二重計上を防ぐ］**：ファミリー共有による収益の重複を防ぎます。これらのイベントには`purchase_ownership_type=FAMILY_SHARED`が設定され、収益は0として報告されます。
3. <strong>［自動更新サブスクリプションの収益を計測・アトリビューション］</strong>のトグルがオンになっていることを確認します。
4. 次の設定の状態を確認します。
   * **App Storeのキー**の設定
   * **サーバー通知用エンドポイント**の設定
   * SDK Connectorの実装とテスト

<div id="step-6-release-the-app-versions-with-the-sdk-connector" />

## 手順6｜SDK Connectorを実装したアプリのリリース

設定とAppsFlyer Purchase SDK Connectorの実装が完了したら、実装済みのアプリをリリースするよう開発者に依頼します。

新しいバージョンをリリースする前に、次の点を確認してください。

* アプリ内購入またはサブスクリプションとして記録したいアプリ内イベントが、AppsFlyerで設定した検証ルールによってブロックされていないこと。
* 開発者が、すべてのサンドボックスフラグをfalseに設定していること。

[![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

SDK Connectorを実装したアプリが公開されると、<Anchor target="_blank" href="/marketers/ja/docs/about-roi360-store-revenue#iaprelated-events-and-parameters">アプリ内購入</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/about-roi360-store-revenue#subscriptionrelated-events-and-parameters">サブスクリプションのイベント</Anchor>が生成され、AppsFlyerのすべてのダッシュボード、集計レポート、ローデータレポート（<Anchor target="_blank" href="/marketers/ja/docs/revenue-etl-reports">収益ETL</Anchor>を含む）で利用できるようになります。

**注意：** イベントが生成されるのは、SDK Connectorを実装したバージョンにアプリを更新したユーザーのみです。そのため、更新版のアプリがすべてのユーザーに行き渡るまでは、アプリの収益データとストアのデータに差異が生じます。

<div id="switch-to-roi360-store-revenue-from-receipt-validation" />

## レシート検証からROI360ストア収益への切り替え

レシート検証の導入が完了していて、ROI360ストア収益を有効にする場合は、次の手順を実行します。

1. AppsFlyerのサイドメニューから[<Image alt="" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.54%" />](https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png)<strong>［設定］</strong>を開き、<strong>［ROI360］</strong>の<strong>［収益設定］</strong>を選択します。
2. <strong>［購入・サブスクリプション］</strong>タブを開きます。 ROI360が利用可能ですが、有効になっていないことを示すバナーが表示されます。
3. <strong>［製品の比較を表示］</strong>をクリックし、返金のアトリビューション、純収益のレポート、サブスクリプションのライフサイクル全体の計測などの利点を確認します。
4. <strong>［ROI360を有効にする］</strong>をクリックします。
5. <strong>［App Storeのサーバー通知を有効にする］</strong>の手順を実行します。詳しくは、[「App Storeのサーバー通知の設定」](#手順2iosapp-storeのサーバー通知の設定)または[「Google Playのサーバー通知の設定」](#手順2androidgoogle-playのサーバー通知の設定)を参照してください。
6. <strong>［購入・サブスクリプション］</strong>セクションで、<strong>［製品タイプ］</strong>が<strong>［ROI360］</strong>に変わったことを確認します。
7. 現在のSDKの設定で、必要なROI360ストア収益の機能を使用できるか確認します。

<div id="note-5" />

> 📘 **注意**
>
> ROI360ストア収益は、Purchase SDK ConnectorとValidate and Logの2つの連携方法に対応しています。次の機能を利用できるため、**Purchase SDK Connector**を推奨します。
>
> * 取引の自動検出
> * 既存の契約者（連携前に契約したユーザー）の収益の計測
> * サブスクリプションの価格変更への対応。価格変更後も正確に収益を報告できます。
>
> これらの機能が不要な場合は、**Validate and Log**の連携を引き続き使用できます。
>
> **SDKの連携方法の確認**
>
> アプリがPurchase SDK ConnectorとValidate and Logのどちらを使用しているか確認するには：
>
> 1. <strong>［SDK Connectorの連携］</strong>の手順を開きます。
> 2. <strong>［SDK連携をテスト］</strong>をクリックします。過去7日間にAppsFlyerがSDKのデータを最後に受信した日時と、送信元が**Purchase SDK Connector**か**Validate and Log**かが表示されます。

<div data-zendesk-anchors="h_01KSAG4Y3BP0NWYNCX3AJG47JR=%E9%87%8D%E8%A6%81 overview=%E6%A6%82%E8%A6%81 h_01KD31QE0BCW0BX9BNNDK6DJRA=%E6%A6%82%E8%A6%81 h_01KD31QE0BQAQ0CS1FJ46TV6K1=%E6%B3%A8%E6%84%8F step-1-ios-set-up-app-store-connect-keys=%E6%89%8B%E9%A0%861iosapp-store-connect%E3%81%AE%E3%82%AD%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD31QE0BE3ST0TV3KQ1M5AB0=%E6%89%8B%E9%A0%861iosapp-store-connect%E3%81%AE%E3%82%AD%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD31QE0BBYES1C2Y1MB665EF=11-create-the-app-store-connect-keys h_01KD31QE0B4G0NGRYBTS2TRZQR=12-set-the-app-store-connect-key-in-appsflyer step-1-android-set-up-service-account-key-and-permissions=%E6%89%8B%E9%A0%861android%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AE%E3%82%AD%E3%83%BC%E3%81%A8%E6%A8%A9%E9%99%90%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD31QE0BVQNJZ8PKKYKK9Q79=%E6%89%8B%E9%A0%861android%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AE%E3%82%AD%E3%83%BC%E3%81%A8%E6%A8%A9%E9%99%90%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD31QE0BP21EHP5RPBZ5PX2N=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD31QE0B5G8SDGZQ8NE07QAE=12-configure-your-service-account-in-the-google-cloud-platform h_01KD31QE0CBMGHXJTXT4JPBV70=13-set-api-access-permissions-in-google-play-console h_01KD31QE0CH5M5X9M9G68N2PPZ=14-upload-the-service-account-private-key-to-appsflyer step-2-ios-set-up-app-store-server-notifications=%E6%89%8B%E9%A0%862iosapp-store%E3%81%AE%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E9%80%9A%E7%9F%A5%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD31QE0CZAJ7SH2EECDJ11YN=%E6%89%8B%E9%A0%862iosapp-store%E3%81%AE%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E9%80%9A%E7%9F%A5%E3%81%AE%E8%A8%AD%E5%AE%9A option-1-recommended-appsflyer-as-the-primary-endpoint=%E6%96%B9%E6%B3%951%E6%8E%A8%E5%A5%A8%E9%80%9A%E7%9F%A5%E3%81%AE%E6%9C%80%E5%88%9D%E3%81%AE%E9%80%81%E4%BF%A1%E5%85%88%E3%82%92appsflyer%E3%81%AB%E3%81%99%E3%82%8B h_01KW7HDDAQEHGY33SQ2AHWVJAC=%E6%96%B9%E6%B3%951%E6%8E%A8%E5%A5%A8%E9%80%9A%E7%9F%A5%E3%81%AE%E6%9C%80%E5%88%9D%E3%81%AE%E9%80%81%E4%BF%A1%E5%85%88%E3%82%92appsflyer%E3%81%AB%E3%81%99%E3%82%8B option-2-your-endpoint-as-the-primary-endpoint=%E6%96%B9%E6%B3%952%E9%80%9A%E7%9F%A5%E3%81%AE%E6%9C%80%E5%88%9D%E3%81%AE%E9%80%81%E4%BF%A1%E5%85%88%E3%82%92%E8%87%AA%E7%A4%BE%E3%81%AE%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E3%81%AB%E3%81%99%E3%82%8B h_01KW7HDDAQK8Z279CEG7N33FKT=%E6%96%B9%E6%B3%952%E9%80%9A%E7%9F%A5%E3%81%AE%E6%9C%80%E5%88%9D%E3%81%AE%E9%80%81%E4%BF%A1%E5%85%88%E3%82%92%E8%87%AA%E7%A4%BE%E3%81%AE%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E3%81%AB%E3%81%99%E3%82%8B h_01_roi360_notification_types=%E6%B3%A8%E6%84%8F-1 h_01KD31QE0C9YFBM01GGE2PZDNR=21-copy-the-appsflyer-server-notifications-endpoint h_01KD31QE0C4MRYPMMQ31BRAYS7=22-send-notifications-directly-to-appsflyer 23-%5Boptional%5D-forward-notifications-from-your-endpoint-to-appsflyer=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0CWXTKDND5F4Q34J7G=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0C2QWHBJ8AWMEMP2SD=24-test-the-server-notifications-integration h_01KD31QE0CA26Y430AMK474NTC=%E6%B3%A8%E6%84%8F-2 step-2-android-set-up-google-play-server-notifications=%E6%89%8B%E9%A0%862androidgoogle-play%E3%81%AE%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E9%80%9A%E7%9F%A5%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD31QE0CKP0PTBQ4XCT9NDE1=%E6%89%8B%E9%A0%862androidgoogle-play%E3%81%AE%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E9%80%9A%E7%9F%A5%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KD31QE0C1RYXW6ADHMQJ3908=21-send-google-play-notifications-directly-to-appsflyer 22-%5Boptional%5D-forward-google-play-notifications-to-appsflyer=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CFVEBJV3E93Z5RDAP=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CTFNTY52F0C9D3RY2=23-send-a-test-notification-from-google-play-console h_01KD31QE0CV17JMVVB7ZPT1G8W=24-confirm-notification-delivery-in-appsflyer step-3-implement-sdk-connector=%E6%89%8B%E9%A0%863sdk-connector%E3%81%AE%E5%AE%9F%E8%A3%85 h_01KD31QE0CPK1EYVT0BSYTTZFM=%E6%89%8B%E9%A0%863sdk-connector%E3%81%AE%E5%AE%9F%E8%A3%85 h_01KD31QE0C65DQ59ZKG8V886JW=%E6%B3%A8%E6%84%8F-3 step-4-verify-sdk-implementation=%E6%89%8B%E9%A0%864sdk%E3%81%AE%E5%AE%9F%E8%A3%85%E3%81%AE%E7%A2%BA%E8%AA%8D h_01KD31QE0C9KGGFVQR6HYR5AYM=%E6%89%8B%E9%A0%864sdk%E3%81%AE%E5%AE%9F%E8%A3%85%E3%81%AE%E7%A2%BA%E8%AA%8D h_01KD31QE0C0VKWF5EBBR761C1J=test-sdk-implementation h_01KD31QE0C7RN657P9KPFV5725=%E6%B3%A8%E6%84%8F-4 h_01KD31QE0D0CR02260J5K8V8QX=sandbox-events-and-parameters h_01KD31QE0DNEBYXH4672363WYM=test-inapp-purchase-and-subscription-revenue step-5-verify-and-update-settings=%E6%89%8B%E9%A0%865%E8%A8%AD%E5%AE%9A%E3%81%AE%E7%A2%BA%E8%AA%8D%E6%9B%B4%E6%96%B0 h_01KD31QE0DQP78QG5HRSERR5S9=%E6%89%8B%E9%A0%865%E8%A8%AD%E5%AE%9A%E3%81%AE%E7%A2%BA%E8%AA%8D%E6%9B%B4%E6%96%B0 step-6-release-the-app-versions-with-the-sdk-connector=%E6%89%8B%E9%A0%866sdk-connector%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%97%E3%81%9F%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%AA%E3%83%AA%E3%83%BC%E3%82%B9 h_01KD31QE0D3HX2DEH7FQ1JR4MS=%E6%89%8B%E9%A0%866sdk-connector%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%97%E3%81%9F%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%AA%E3%83%AA%E3%83%BC%E3%82%B9 switch-to-roi360-store-revenue-from-receipt-validation=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%8B%E3%82%89roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%B8%E3%81%AE%E5%88%87%E3%82%8A%E6%9B%BF%E3%81%88 h_01KD31QE0DJNJ8T5XSZFCACMQF=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%8B%E3%82%89roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%B8%E3%81%AE%E5%88%87%E3%82%8A%E6%9B%BF%E3%81%88 h_01KD31QE0DX0VDXKHDZTWTYHHX=%E6%B3%A8%E6%84%8F-5" />

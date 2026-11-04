---
title: 受信パートナー接続 - Amplitude
metadata:
  keywords:
    - Audiences
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2022-02-23T14:27:13Z'
  edited_at: '2026-10-14T09:28:41Z'
  id: 4470658876817
  locale: ja
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ja/articles/4470658876817
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要:** AmplitudeのコホートをインポートされたオーディエンスとしてAppsFlyerに同期することで、ファーストパーティデータを活用しましょう。

<div id="about-the-amplitude-integration" />

## Amplitude連携について

**AppsFlyer Audiences-Amplitude連携**を利用すれば、Amplitudeアカウントで定義したコホートを<Anchor target="_blank" href="/marketers/ja/docs/audiences-import-audience-segments-from-internal-systems">インポートされたオーディエンス</Anchor>として直接AppsFlyerに同期することができます。AppsFlyerは、これらのオーディエンスセグメントをパートナーと接続し、キャンペーンの指標を確認し、AmplitudeとAppsFlyerのデータをリンクして、効果的に活用するための一元的な場所として機能します。

Amplitudeのコホートは、一度きりの同期または毎日や毎時間の更新が可能なスケジュール同期としてAppsFlyerと同期できます。

<div id="setting-up-the-integration" />

## 連携の設定

Amplitudeプラットフォーム内でAudiences-Amplitude連携を設定します。

<div id="define-appsflyer-data-destinations" />

### AppsFlyerデータの送信先を定義する

**Amplitudeでこれらの手順を行い、AppsFlyerデータの送信先を定義します。** **AppsFlyerオーディエンスをインポートするそれぞれのアプリに対して、個別のデータ送信先を定義する必要があります。**

1. Amplitudeの「**Data Destinations**」セクションで、「**AppsFlyer**」タイルを選択します。
2. 「**コホート デスティネーション**」で、「**AppsFlyer**」を選びます。
3. 「**AppsFlyerに接続**」ダイアログボックスに次の情報を入力してください。

   <strong>重要！</strong>Amplitudeアカウントに既に作成済みのAppsFlyer送信先がある場合、ダイアログボックスはすべての既存送信先を示すスクロール可能なリストになります。新しい送信先を作るには、このリストの最後までスクロールし、「**別の目的地を追加**」をクリックします。

   

| 項目 | 説明 |
| --- | --- |
| 名前 | 送信先の名前を入力してください。<br /><br />1つのAmplitudeプロジェクトで複数のAppsFlyer送信先を作成する場合（例：プロジェクトに複数のアプリがある場合）、後で簡単に識別できる名前を指定してください。 |
| AppsFlyer APIトークン V2.0 | **AppsFlyer APIトークンを取得するには、AppsFlyerで以下の手順に従ってください：**<ol><li>メニューの上部バーから、ユーザーメニュー（右上のメールアドレスのドロップダウン）にアクセスします。</li><li>**セキュリティセンター**を選択します。</li><li>**AppsFlyer APIトークン** セクションで、**AppsFlyer APIトークンの管理**をクリックしてください。</li><li>**V2.0** トークンをコピーしてください。</li></ol> |
| AppsFlyerアプリID | AppsFlyer管理画面に表示される、この送信先のアプリのアプリIDを入力してください。<br /><br />![amplitude_app_id_from_appsflyer_dashboard.png](https://files.readme.io/2e7da9a20f0c4b59e58f51823dd9753ecc36b77e84622821cb3cb65e4f7b2743-33375708378385.png) |
| プラットフォーム | アプリのプラットフォーム（iOSまたはAndroid）を選択してください。 |
| 識別子 | AmplitudeデータをAppsFlyerデータに接続する方法を指示するために、左側でAmplitudeユーザープロパティを選択し、右側でそれをマッピングするAppsFlyerキーを選んでください。選択するAppsFlyerキーは、次のいずれかでなければなりません。<ul><li>**iOSオーディエンスの場合:** iOS広告主ID、AmplitudeユーザーID、またはAppsFlyer顧客ユーザーID</li><li>**Androidオーディエンス向け:** Google広告主ID、AmplitudeユーザーID、またはAppsFlyer顧客ユーザーID</li></ul> |

4. 新しいAppsFlyerの宛先を保存するには、**保存** をクリックしてください。

<div id="sync-amplitude-cohorts-to-appsflyer-destinations" />

### AmplitudeコホートをAppsFlyerの宛先に同期する

**次に、Amplitude コホートをAppsFlyerの送信先に同期するために、以下の手順に従ってください:**

1. Amplitudeプラットフォームの**コホート** セクションから、AppsFlyerオーディエンスを作成するコホートを選択してください。（または、新しいコホートを作成することも可能です。）
2. 以下のリンクをクリックしてください:**コホートの詳細を表示するにはクリックしてください。**
3. **コホート定義** ページで、**同期先…** ボタンをクリックしてください。
4. AppsFlyerタイルを選択し、**次へ** をクリックしてください。

   **宛先とケイデンスの定義** ダイアログボックスが表示されます。

   [altamplitude\_define\_destination\_and\_cadence\_dialog.pngalt](https://support.appsflyer.com/hc/article_attachments/4562247577489)
5. **同期するAPIターゲットを選択** リストから、関連するAppsFlyerの宛先の名前を選んでください。
6. このコホートをAppsFlyerに一度だけ同期するか、スケジュールされた同期にするかを選択してください。（スケジュールされた同期の場合は、更新頻度を毎日または毎時に設定してください。）
7. 同期を開始するには、[**同期**] ボタンをクリックしてください。

最初の同期が正常に完了すると、このコホートの新しいオーディエンスがオーディエンス管理画面の「オーディエンス」タブに表示されます。

デフォルトでは、新しいオーディエンスの名前は、同期されたAmplitudeコホートの名前に英数字の識別子が続いたものになります。必要ならば、オーディエンス管理画面からオーディエンス名を編集できます。

[altamplitude\_imported\_audience.pngalt](https://support.appsflyer.com/hc/article_attachments/4562234292113)

<div data-zendesk-anchors="overview=amplitude%E9%80%A3%E6%90%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HNZP6HDVC5RBMKTCZY81HG4M=amplitude%E9%80%A3%E6%90%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 setting-up-the-integration=%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HNZP6HDVZH6Q1KGJE7FXSPMT=%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A define-appsflyer-data-destinations=appsflyer%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%80%81%E4%BF%A1%E5%85%88%E3%82%92%E5%AE%9A%E7%BE%A9%E3%81%99%E3%82%8B h_01HNZP6HDVV3GSEPARCY1VABX8=appsflyer%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%80%81%E4%BF%A1%E5%85%88%E3%82%92%E5%AE%9A%E7%BE%A9%E3%81%99%E3%82%8B sync-amplitude-cohorts-to-appsflyer-destinations=amplitude%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E3%82%92appsflyer%E3%81%AE%E5%AE%9B%E5%85%88%E3%81%AB%E5%90%8C%E6%9C%9F%E3%81%99%E3%82%8B h_01HNZP6HDV6EFPCM5FE5XBAS78=amplitude%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E3%82%92appsflyer%E3%81%AE%E5%AE%9B%E5%85%88%E3%81%AB%E5%90%8C%E6%9C%9F%E3%81%99%E3%82%8B" />

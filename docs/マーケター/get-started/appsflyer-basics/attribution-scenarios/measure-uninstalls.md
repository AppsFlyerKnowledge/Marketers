---
title: アンインストールの計測
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
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-14T08:03:47Z'
  edited_at: '2026-10-21T18:43:30Z'
  id: 4408933557137
  locale: ja
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ja/articles/4408933557137
---
> **At a glance:** アプリのアンインストール率を計測し、質の高いユーザーの獲得につながるメディアソース、キャンペーン、広告クリエイティブ、地域を把握できます。

<div id="overview" />

## 概要

アプリユーザーの価値を把握するには、インストール率とアンインストール率の両方を分析する必要があります。アンインストールの指標を活用することで、アプリの成果を評価し、ユーザーがいつ、なぜアプリの利用をやめるのかを把握できます。

<div id="how-does-it-work" />

### 計測の仕組み

1. <span class="af-ol-a"></span>AppsFlyerは、Firebase Cloud Messaging（FCM）とApple Push Notification Services（APNS）に日次でAPIリクエストを送信します。
2. FCMとAPNSは、画面に表示されないプッシュ通知（サイレントプッシュ通知）を送信し、対象のデバイスにアプリが引き続きインストールされているかを確認します。
3. 応答からアプリがアンインストールされたと判断できる場合（FCMとAPNS）、または過去270日間にユーザーのアクティビティが記録されていない場合（FCMのみ）、アンインストールとして記録されます。
4. AppsFlyerは、アンインストールを、そのユーザーを最初に獲得したメディアソースに紐づけます。

> 📘 **Note**
>
> **注意**
>
> アンインストールの指標は、統合ダッシュボードとユーザー獲得ビューで確認できます。

<div id="how-to-use-uninstall-data" />

## アンインストールデータの活用方法

アンインストール計測から得られる情報と、そのデータを活用してキャンペーンを最適化し、ユーザーの利用を促進する方法を、例とともに紹介します。

<div id="compare-the-quality-of-sources" />

<Accordion title="ユーザー獲得元の質の比較">

メディアソース、キャンペーン、広告クリエイティブ、地域ごとに獲得ユーザーの質を比較することで、アンインストール率の低いメディアソースを特定し、予算を重点的に配分できます。

> 📘 **Note**
>
> **例**
>
> あなたは、PlayIt Gaming Internationalでゲームアプリのマーケティングを担当しています。新しいアプリをリリースしたばかりで、2つのメディアソース（メディアソースAとメディアソースB）でキャンペーンを実施しています。
>
> ダッシュボードを確認すると、メディアソースAはインストール数が最も多い（10,390件）一方で、アンインストール率も最も高い（30%）ことが分かりました。
>
> 一方、メディアソースBはインストール数が5,949件で、アンインストール率は最も低い12%でした。
>
>
>
> この結果を踏まえ、メディアソースBにより多くの予算を配分することで、アプリを積極的に利用するユーザーの獲得を目指せます。

</Accordion>

<div id="share-uninstall-data-with-ad-networks-for-optimization" />

<Accordion title="アドネットワークへのアンインストールデータの共有による最適化">

連携先のアドネットワークにアンインストールイベントのポストバックを送信すると、ユーザー獲得キャンペーンの最適化に役立ちます。 [af\_uninstallをアドネットワークのイベントに紐づける](/docs/measure-uninstalls#アンインストールイベントの紐づけ)ことで、アンインストールイベントを送信できます。イベントの紐づけが完了すると、アプリをアンインストールしたユーザーが検出されるたびにイベントが送信されます。アドネットワークは、この情報を使って利用頻度の低いユーザーを把握し、アプリをより積極的に利用するユーザーの獲得に注力できます。

> 📘 **Note**
>
> **例**
>
> あなたは、PlayIt Gaming Internationalでゲームアプリのマーケティングを担当しています。メディアソースAは、新しいAndroidアプリのリリースにあたり連携しているアドネットワークです。メディアソースAで実施した前回のキャンペーンでは、1,000人の新規ユーザーがアプリをインストールし、その後300人がアンインストールしました。今回のキャンペーンでは、メディアソースAにアンインストールデータを共有することにしました。これにより、メディアソースAはアンインストールに関する課題に迅速に対応できます。
>
> メディアソースAは、前回のキャンペーンで得られた情報をもとに、今回のキャンペーンの広告配信から次のユーザーを除外するリストを作成します。
>
> * アプリにとっての価値が低いとすでに判明しているユーザー。
> * 自社のアプリを頻繁にアンインストールするユーザー。
>
> これにより、メディアソースAは配信対象を最適化し、該当する広告を表示する必要のないユーザーにキャンペーン予算を費やすことを防げます。

</Accordion>

<div id="exclude-uninstalls-from-retargeting-campaigns" />

<Accordion title="アンインストールしたユーザーをリターゲティングキャンペーンから除外">

GDPRやCCPAなどの規制に対応するため、アプリをアンインストールしたユーザーをリターゲティングキャンペーンから除外する必要がある場合があります。アンインストール情報を利用すると、除外リストを作成し、ユーザーのプライバシーとデータを保護するための対策を講じられます。

ユーザーを除外する方法には、次のようなものがあります。

* <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview#user-journey-report-availability">ローデータレポート：</Anchor>［**アンインストール**］レポートからアンインストールしたユーザーの一覧を取得し、手動で除外リストを作成します。
* <Anchor target="_blank" href="/marketers/ja/docs/audiences-guide">AppsFlyer Audiences：</Anchor>特定の条件（例：アプリを**アンインストールしていない**ユーザー）に基づいて対象のオーディエンスを定義し、自動的に除外します。条件を満たさないユーザーは、オーディエンスから除外されます。

> 📘 **Note**
>
> **例**
>
> あなたは、PlayIt Gaming Internationalでゲームアプリのマーケティングを担当しています。 Androidアプリのリターゲティングキャンペーンを実施しており、AppsFlyer Audiencesでリターゲティングの対象ユーザーを定義することにしました。対象ユーザーの条件は次のとおりです。
>
> * アプリをアンインストールしていないユーザー。
> * 過去30日間にアプリを起動していないユーザー。
>
> これにより、リターゲティングの対象ユーザーをより的確に絞り込めます。リターゲティングキャンペーンを実施すると、定義した対象ユーザーにのみ広告が配信されます。

</Accordion>

<div id="setting-up-uninstall-measurement" />

## アンインストール計測の設定

アンインストール計測の設定には、マーケティング担当者と開発者の連携が必要です。実装手順は、アプリの対応OSによって異なります。

マーケティング担当者と開発者が行う作業は、次のとおりです。

<Tabs>
<Tab title="Android">

| 作業 | 担当者 |
| --- | --- |
| Firebase Cloud Messaging（FCM）とAppsFlyerの連携 | マーケティング担当者 |
| AppsFlyerでのアンインストール計測の設定 | マーケティング担当者 |
| SDKの実装 | Android開発者 |
| アンインストール計測のテスト | マーケティング担当者 |
| ［任意］管理画面で、対象パートナーへの[アンインストールイベントの紐づけ](/docs/measure-uninstalls#アンインストールイベントの紐づけ)を設定 | マーケティング担当者 |

</Tab>

<Tab title="iOS">

| 作業 | 担当者 |
| --- | --- |
| P12証明書の生成 | iOS開発者 |
| AppsFlyerでのアンインストール計測の設定 | マーケティング担当者 |
| SDKの実装 | iOS開発者 |
| アンインストール計測のテスト | マーケティング担当者 |
| ［任意］管理画面で、対象パートナーへの[アンインストールイベントの紐づけ](/docs/measure-uninstalls#アンインストールイベントの紐づけ)を設定 | マーケティング担当者 |

</Tab>
</Tabs>

<div id="implementation-procedures" />

## 実装手順

実装にあたっては、モバイルアプリの開発者が、プッシュ通知に応答する仕組みをアプリに組み込む必要があります。実装手順はOSによって異なります。

<div id="connect-firebase-cloud-messaging-to-appsflyer-android" />

### Firebase Cloud MessagingとAppsFlyerの連携（Android）

Androidのアンインストール計測を利用するには、AppsFlyerでアンインストール計測を設定し、アプリにFirebase Cloud Messaging（FCM）を実装します。

<div id="http-v1" />

<Accordion title="HTTP V1">

**アンインストール計測用にFCM HTTP V1を設定するには、次の手順に従います。**

1. **プロジェクトIDの取得**：
   1. <Anchor target="_blank" href="https://console.firebase.google.com/">FCMコンソール</Anchor>にアクセスします。
   2. プロジェクトを選択します。
   3. ［**プロジェクトの概要（Project Overview）**］>［**プロジェクトの設定（Project settings）**］に移動します。
   4. プロジェクトIDをコピーします。このIDは、後の手順で使用します。
2. FCM APIの有効化：
   1. ［**Cloud Messaging**］タブに移動します。
   2. ［**Firebase Cloud Messaging API (V1)**］が［**有効（Enabled）**］になっていることを確認します。
3. **AppsFlyerに付与するアンインストール計測用ロールの作成：**
   1. ［**サービスアカウント（Service accounts）**］タブに移動します。
   2. ［**サービスアカウントの権限を管理（Manage service account permissions）**］をクリックします。   
      Google Cloud Platformが新しいブラウザタブで開きます。
   3. サイドメニューで［**ロール（Roles）**］を選択します。
   4. ［**+ロールを作成（+Create role）**］をクリックします。
   5. 次のように入力・選択します。
      * タイトル（Title）：**AppsFlyer uninstalls**と入力します。
      * ID：`af_uninstalls`と入力します。
      * ロールのリリースステージ（Role launch stage）：［**一般提供（General availability）**］を選択します。
   6. ［**権限を追加（Add permissions）**］をクリックします。
   7. <Image alt="adjusted.png" src="https://files.readme.io/c9fc0c6358ff89e1004ac1ab348a4b286d58c8a5cbe024aeb5c637136f3a67ac-33839382508049.png" width="20px" />［**フィルタ（Filter）**］で、**cloudmessaging.messages.create** 権限を選択します。
   8. ［**追加（Add）**］をクリックし、続いて［**作成（Create）**］をクリックします。
4. **AppsFlyerへのFCMアンインストール計測用ロールの付与：**
   1. サイドメニューで［**IAM**］を選択します。
   2. ［**権限（PERMISSIONS）**］->［**プリンシパル別に表示（VIEW BY PRINCIPALS）**］タブを開きます。
   3. ［**アクセス権を付与（Grant Access）**］をクリックします。
   4. ［**プリンシパルを追加（Add Principals）**］->［**新しいプリンシパル（New principals）**］に、**af-uninstalls-tracking@af-uninstalls-tracking.iam.gserviceaccount.com**と入力します。
   5. ［**ロールを割り当てる（Assign roles）**］->［**ロール（Role）**］で、作成したカスタムロール［**AppsFlyer Uninstalls**］を選択します。
   6. ［**保存（Save）**］をクリックします。   
      AppsFlyerのサービスアカウントに、AppsFlyer uninstallsロールが付与されます。

      > 📘 **Note**
      >
      > **注意**
      >
      > AppsFlyerは、画面に表示されないプッシュ通知を、アンインストールの計測またはアクティビティのないユーザーの検出にのみ使用し、その他の目的には使用しません。


</Accordion>

<div id="legacy-http" />

<Accordion title="［非推奨］従来のHTTP API">

> 🚧 **Important**
>
> **重要**
>
> 従来のHTTP APIは、Firebaseによって2023年6月20日に非推奨となり、2024年6月21日に廃止される予定です。従来のAPIを使用している場合は、[HTTP v1 APIへの切り替え](/docs/measure-uninstalls#http-v1)を強く推奨します。<Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/http-server-ref">詳細はこちら</Anchor>

Firebase Messagingを使用したアンインストール計測は、Android SDK V4.7.0以降でサポートされています。

**Firebaseのサーバーキーを取得するには、次の手順に従います。**

1. FirebaseでAndroidアプリのプロジェクトを作成します（未作成の場合）。または、**Google Developer Console**からプロジェクトを移行します（同コンソールの手順に従ってください）。詳しくは、<Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/android/client">Firebase</Anchor>のドキュメントを参照してください。
2. Firebaseの<Anchor target="_blank" href="https://console.firebase.google.com">コンソール</Anchor>を開きます。
3. Firebaseコンソールで［プロジェクトの設定（Project Settings）］に移動します。画面左側の［プロジェクトの概要（Project Overview）］の横にある歯車アイコンをクリックしてください。
4. ［Cloud Messaging］タブに、2つのサーバーキーが表示されます。
5. ［**サーバーキー（Server Key）**］をコピーします。

</Accordion>

<div id="configure-uninstall-measurement-in-appsflyer" />

### AppsFlyerでのアンインストール計測の設定

<Tabs>
<Tab title="Android">

**前提条件**：Android開発者が、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">実装手順</Anchor>に従って作業を完了している必要があります。

**AppsFlyerでアンインストール計測を設定する手順**：

1. AppsFlyerのサイドメニューで、［**設定**］>［**アプリ設定**］を選択します。
2. 必要に応じて、［**アンインストール計測**］をオンにします。
3. **［HTTP V1］を選択し、先ほど取得したプロジェクトIDを入力します。**
4. ［**接続をテスト**］をクリックします。  
   接続成功のメッセージが表示されます。

   > 📘 **Note**
   >
   > **注意**
   >
   > 接続テスト後に［**プロジェクトIDが無効か、アクセス権限がありません**］というエラーメッセージが表示された場合は、FCMの接続設定を見直してください。詳しくは、この記事の[Firebase Cloud MessagingとAppsFlyerの連携（Android）](#firebase-cloud-messagingとappsflyerの連携android)を参照してください。  
   > あわせて、権限とプロジェクトIDが正しく設定されていることを確認してください。

5. ［**設定を保存**］をクリックします。

</Tab>

<Tab title="iOS">

**前提条件**：iOS開発者が、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">実装手順</Anchor>に従って作業を完了している必要があります。

**AppsFlyerでアンインストール計測を設定するには、次の手順に従います。**

1. 開発者からP12ファイルを受け取ります。
2. AppsFlyerのサイドメニューで、［**設定**］>［**アプリ設定**］を選択します。
3. ［アンインストール］セクションまでスクロールします。
4. ［**アンインストール計測**］をオンにします。
5. アップロードアイコンをクリックし、P12ファイルを選択します。
6. ［任意］P12証明書がパスワードで保護されている場合は、パスワードを入力します。
7. ［**検証**］をクリックすると、検証のために証明書がAppsFlyerに送信されます。
8. ［**設定を保存**］をクリックします。

</Tab>
</Tabs>

<div id="testing-uninstall-measurement" />

## アンインストール計測のテスト

実装が完了したら、アプリをインストールしてからアンインストールし、アンインストールが正しく記録されるかをテストできます。アンインストール数とアンインストール率は、オーバービューダッシュボードに表示されます。

<Tabs>
<Tab title="Android">

次の状態のアプリでテストできます。

* Google Playストアで公開されているアプリ
* 保留中（Google Playストアで未公開）のアプリ
* 直接ダウンロードできるアプリ
* 他のアプリストアで公開されているアプリ

Androidアプリをテストする際は、次の点に注意してください。

* アンインストール計測は<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#uninstalls">日次</Anchor>で処理されます。アンインストールイベントは24時間以内に記録されます。ただし、その間にアプリが再インストールされた場合は、イベントは記録されません。
* <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ローデータレポート</Anchor>とAppsFlyerのダッシュボード（集計パフォーマンスレポート）に**アンインストールイベントが表示されるまで、最大48時間かかります**。

</Tab>

<Tab title="iOS">

iOSアプリをテストする際は、次の点に注意してください。

* アンインストールは、AppsFlyerのダッシュボードにすぐには表示されません。 Apple Push Notification serviceの仕組みにより、アンインストールがダッシュボードに表示されるまでには、最低9日かかります。 AppsFlyerは、アンインストールの指標を24時間ごとに更新・集計します。

  > 📘 **Note**
  >
  > **例**
  >
  > * 1日目：ユーザーがアプリをインストールします。
  > * 4日目：ユーザーがアプリをアンインストールします。
  > * 12日目：アンインストールから8日後に、Apple Push Notification Serviceがアプリの削除を通知します。
  > * 13日目：AppsFlyerのダッシュボードとローデータに、アンインストールデータが表示されます。

* テスト版のアプリでテストを行う場合は、必ずサンドボックス環境を使用してください。開発者向けの[サンドボックス環境でのアンインストール計測手順](https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#testing-uninstall-measurement)を参照してください。

</Tab>
</Tabs>

<div id="mapping-the-uninstall-event" />

## アンインストールイベントの紐づけ

 

アドネットワークにアンインストールデータを共有するには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">af\_uninstallイベント</Anchor>をパートナーのイベントに紐づける必要があります。通常のアプリ内イベントのポストバックとは異なり、アンインストールイベントはリアルタイムでは送信されません。報告されるイベント時刻は、実際にアンインストールされた時刻ではなく、AppsFlyerがアンインストールを検出した時刻です。

次の点に注意してください。

* AppsFlyerがポストバックを送信できるのは、イベントが実際に発生し、AppsFlyerに記録された場合に限られます。
* オーバービューダッシュボードやローデータレポートにアンインストールが表示されていない場合は、**af\_uninstall**イベントの紐づけを設定していても、アンインストールのポストバックはパートナーに送信されていません。

<div id="limitations" />

#### 制限事項

* アンインストールイベントは、アプリ内イベントのポストバックレポートには含まれません。
* すべてのパートナーが**af\_uninstall**イベントに対応しています。パートナーへの紐づけを設定しようとしても、パートナーの［連携］タブにこのイベントが表示されない場合は、パートナーに直接お問い合わせください。

<div id="turning-off-uninstall-measurement" />

## アンインストール計測の無効化

<Tabs>
<Tab title="Android">

Firebase/GCMのサーバーキーが設定されている場合、アプリのアンインストール計測はデフォルトで有効になります。アプリ所有者は、ダッシュボードでこの機能を無効にできます。

</Tab>

<Tab title="iOS">

P12証明書が設定され、検証済みの場合、アプリのアンインストール計測はデフォルトで有効になります。アプリ所有者は、ダッシュボードでこの機能を無効にできます。

</Tab>
</Tabs>

**注意：** アンインストールが報告されるには、アプリのインストール時点で［**アンインストール計測を有効にする**］がオンになっている必要があります。［**アンインストール計測を有効にする**］がオフの間に発生したインストールは報告されません。

<div id="to-turn-off-uninstall-measurement" />

#### **アンインストール計測を無効にする手順**：

1. AppsFlyerのサイドメニューで、［**設定**］>［**アプリ設定**］を選択します。
2. ［**アトリビューション**］>［**アンインストール計測**］に移動し、［**アンインストール計測を有効にする**］をオフにします。

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 説明 |
| --- | --- |
| CUID | アンインストールのポストバックには、CUIDは含まれません。 |

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HB8CXQ4824V2WEPYGK8YS4DC=%E6%A6%82%E8%A6%81 how-does-it-work=%E8%A8%88%E6%B8%AC%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF h_01HB8CXQ48JEJECC1HR79DXCRK=%E8%A8%88%E6%B8%AC%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF how-to-use-uninstall-data=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%B4%BB%E7%94%A8%E6%96%B9%E6%B3%95 h_01HB8CXQ48E2SRN95MH4E2H7ZH=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%B4%BB%E7%94%A8%E6%96%B9%E6%B3%95 h_01HB8CXQ48HX9RH50G45FZMZTK=compare-the-quality-of-sources h_01HB8CXQ488E22GPCEBE69VQ3M=share-uninstall-data-with-ad-networks-for-optimization h_01HB8CXQ48JTET73GH0QQBX5HF=exclude-uninstalls-from-retargeting-campaigns setting-up-uninstall-measurement=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HB8CXQ4810HTB45FAS5ZVRHF=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A implementation-procedures=%E5%AE%9F%E8%A3%85%E6%89%8B%E9%A0%86 h_01HB8CXQ489HRF72VRZ4G532GX=%E5%AE%9F%E8%A3%85%E6%89%8B%E9%A0%86 connect-firebase-cloud-messaging-to-appsflyer-android=firebase-cloud-messaging%E3%81%A8appsflyer%E3%81%AE%E9%80%A3%E6%90%BAandroid h_01HB8CXQ48ZD5Y0RKTG1W51TKW=firebase-cloud-messaging%E3%81%A8appsflyer%E3%81%AE%E9%80%A3%E6%90%BAandroid h_01HB8CXQ4865MNVG0VERSNSE3F=http-v1 h_01HB8CXQ48H079WQ6Q6G0XSQC7=legacy-http configure-uninstall-measurement-in-appsflyer=appsflyer%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HB8CXQ48CVA9B8B78W0H357C=appsflyer%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A testing-uninstall-measurement=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01HB8CXQ48SW2TT5Z85XD3XWT6=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 mapping-the-uninstall-event=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E7%B4%90%E3%81%A5%E3%81%91 h_01HB8CXQ499ABX9ZGDFB1VAE8W=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E7%B4%90%E3%81%A5%E3%81%91 limitations=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HB8CXQ49F2ARQTEV8Q032P9V=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 turning-off-uninstall-measurement=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%81%AE%E7%84%A1%E5%8A%B9%E5%8C%96 h_01HB8CXQ49Y5NCG7GK93HXHYMD=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%81%AE%E7%84%A1%E5%8A%B9%E5%8C%96 to-turn-off-uninstall-measurement=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%82%92%E7%84%A1%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B%E6%89%8B%E9%A0%86 h_01HB8CXQ49WXZS4M6CK5XG1BCX=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%82%92%E7%84%A1%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B%E6%89%8B%E9%A0%86 h_01HB8CXQ4916CJ9NDZWGWQHKSA=traits-and-limitations" />

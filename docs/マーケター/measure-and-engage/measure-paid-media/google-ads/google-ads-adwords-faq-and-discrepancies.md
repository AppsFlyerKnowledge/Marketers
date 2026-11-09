---
title: Google Ads（AdWords）｜よくある質問とデータの乖離
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T10:06:31Z'
  edited_at: '2026-10-28T09:15:25Z'
  id: 4417303339921
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/4417303339921
---
> **概要：** Google Adsに関する一般的な問題や乖離のトラブルシューティングについて説明しています。

<div id="google-ads-faq" />

## Google Adsに関するよくある質問

<div id="why-am-i-not-seeing-clicks-from-google-ads" />

<Accordion title="Google Adsからのクリック数が表示されない理由は？">

［**コスト**］タブで<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">コスト、クリック、インプレッションの取得を認証</Anchor>すると、Google Adsのクリック数とインプレッション数の集計データが取得されます。

Google Adsのクリックとインプレッションデータは、2018年8月に、まずはAndroidアプリ、次にiOSアプリで利用可能になりました。そのため、2018年以前のクリックデータを分析する際は、Google Adsのクリックデータが欠落していたり、不完全だったりする場合があります。

</Accordion>

<div id="why-am-i-not-seeing-first_open-conversions-on-google-ads" />

<Accordion title="Google Adsでfirst_openコンバージョンが表示されないのはなぜですか？">

以下のスクリーンショットのように、Google Adsでfirst\_openコンバージョンが表示されない場合：

<Image align="center" alt="AW_13.png" src="https://files.readme.io/082f79266fced9fc012cdb373321a836129205992adbe29f7509321516e8f5ab-33743114088849.png" />

Google Adsでコンバージョンをインポートする必要があります。以下の<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">コンバージョンをインポート</Anchor>する手順を実施してください。

</Accordion>

<div id="why-don-t-i-see-installs-from-google-ads" />

<Accordion title="Google Adsからのインストールが表示されないのはなぜですか？">

以下のチェックリストに沿って、インストールが表示されない原因を確認してください。

<div id="quick-fix" />

#### まず確認すること

1. **AppsFlyerでGoogle Ads連携を有効化する**  
   AppsFlyerのサイドバーから、**コラボレーション > アクティブな連携**を開き、**Google Ads**を検索し、連携がアクティブであることを確認します。
2. **Google Adsで**`first_open`**コンバージョンをインポートする**  
   Google Adsの［<Anchor target="_blank" href="https://ads.google.com/aw/conversions">コンバージョンの概要</Anchor>］ページで、`first_open`コンバージョンイベントがインポートされていることを確認します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">アプリのコンバージョンのインポート</Anchor>を参照してください。

<div id="still-not-working" />

#### 解決しない場合

1. **どのGoogle Adsアカウントがコンバージョンをインポートしているか確認する**  
   Google Adsの**MCCアカウント（マネージャーアカウント）とサブアカウント**のどちらがコンバージョンをインポートしているかを確認してください：

   * **MCC（マネージャーアカウント）を利用している場合：** MCCアカウントが、リンクされているすべてのサブアカウントを代表して`first_open`コンバージョンをインポートする必要があります。
   * **サブアカウントを利用している場合：**
     * MCCアカウントからサブアカウントへ**Link IDを共有**する必要があります。
     * サブアカウントでも、**直接**`first_open`**コンバージョンをインポートする必要があります**。

   Google AdsのMCCアカウントについては、<Anchor target="_blank" href="/marketers/ja/docs/recording-multiple-agency-mcc-google-ads-accounts#mcc">MCC</Anchor>を参照してください。
2. **削除された**`first_open`**コンバージョンを確認する**  
   ［<Anchor target="_blank" href="https://ads.google.com/aw/conversions">コンバージョンの概要</Anchor>］ページで、`first_open`コンバージョンイベントが削除されていないか確認します。削除されている場合は、**Googleサポート**へお問い合わせください。
3. **リンクIDを確認する**  
   AppsFlyerのリンクIDとGoogle AdsのリンクIDが一致していることを確認します。

</Accordion>

<div id="why-dont-i-see-inapp-events-in-the-google-ads-dashboard" />

<Accordion title="Google Ads管理画面にアプリ内イベントが表示されないのはなぜですか？">

AppsFlyerとGoogle Ads間でアプリ内イベントが正しく設定・同期されていることを確認するため、以下のチェックリストをお試しください。

<div id="quick-fix-checklist" />

#### 初期確認チェックリスト

以下の手順で、よくある問題を迅速に解消できます。

1. **AppsFlyerでイベントポストバックを確認する**（詳細な手順については、「<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended">AppsFlyerでGoogle Adsを設定する</Anchor>」を参照してください。)
   1. <span class="af-ol-a"></span>AppsFlyerで**Google Ads連携タブ**を開きます。
   2. 計測したい各アプリ内イベントについて、ポストバックが正しく設定されていることを確認します。
   3. Google Adsがイベントデータを受信できるよう、［**送信対象ユーザー**］で［*オーガニックを含むすべてのメディアソース*］を選択します。
   4. （任意）初期設定後、必要に応じてイベントごとにこの選択を変更します。
2. **テスト用のアプリ内イベントを発生させる**
   1. <span class="af-ol-a"></span>アプリを起動します。
   2. iOSアプリの場合は、アプリのトラッキングを許可し、IDFAの収集が有効になっていること を確認してください。
   3. 手動で、マッピング済みのアプリ内イベント（購入や会員登録など）を実行します。
3. **Google Adsでイベントをインポートする**
   1. <span class="af-ol-a"></span>Google Adsで <strong>［ツール］＞［コンバージョン］</strong>をクリックします。
   2. ［**コンバージョンアクションの概要**］を確認します。
   3. 対象のアプリ内イベントをインポートします。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">アプリのコンバージョンのインポート</Anchor>を参照してください。

      <div id="note" />

      > 📘 **注意**
      >
      > イベントの実行後、コンバージョンが表示されるまで最大6時間かかる場合があります。


<div id="still-not-working-1" />

#### 解決しない場合

Google Adsのパートナーイベント識別子を変更し（`CUSTOM`と表示されている場合など）、AppsFlyerでも対応するイベント名を変更した場合は、Google Adsにイベントを再インポートする必要があります。

</Accordion>

<div id="can-i-stop-google-cost-sync" />

<Accordion title="Googleのコスト同期を停止できますか？">

Googleのコスト同期を停止するには：

1. <Anchor target="_blank" href="https://myaccount.google.com/permissions">Googleアカウントの権限</Anchor>へ移動します。
2. AppsFlyer Google Costの横にある［削除］をクリックします。  
   <Image align="center" alt="remove_appsflyer_cost.png" src="https://files.readme.io/56840e708c98875c8db176c642dd324150a76aef9697fcc2756f524b2a6c0a16-33743128661137.png" />

</Accordion>

<div id="do-i-need-to-create-and-then-import-session_start" />

<Accordion title="session_startを作成してから、インポートする必要がありますか？">

これは、実施しているキャンペーンのタイプによります。リエンゲージメントキャンペーンを実施している場合は、`session_start`を作成してインポートし、エンゲージメントを測定することが推奨されます。

ユーザー獲得キャンペーンの場合、これは必須ではありません。

</Accordion>

<div id="can-i-send-uninstall-information-to-google-ads" />

<Accordion title="Google Adsにアンインストールデータを送信できますか？">

はい。  
**Googleにアンインストールイベントを送信する方法：**

1. Google Ads設定画面から、af\_uninstallイベントをカスタムイベントとしてマッピングします。
2. このコンバージョンをGoogleにインポートします。
3. Googleは、Googleのアトリビューション期間内（広告エンゲージメントから30～90日間）に受信されたイベントを承認します。アトリビューション期間終了後にGoogleが受信したイベントは、Google側では記録されません。

</Accordion>

<div id="what-google-ads-data-does-appsflyer-display" />

<Accordion title="AppsFlyerで表示されるGoogle Adsのデータは何ですか？">

キャンペーン、チャネル、広告セット、地域の各レベルでデータを確認できます。

</Accordion>

<div id="do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data" />

<Accordion title="AppsFlyerデータに基づいて、Google Adsでオーディエンスリストを作成するために、何かを設定する必要がありますか？">

いいえ。 Google APIでは、この情報はすでに設定されており、アプリ内イベント設定に基づいています。

</Accordion>

<div id="im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard" />

<Accordion title="アプリキャンペーンを実施していますが、AppsFlyerまたはGoogle Adsの管理画面にデータまたはコンバージョンイベントが表示されないのはなぜですか？">

イベントがまだインポートされていない可能性があります。イベントをインポートする方法の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">こちら</Anchor>をクリックしてください。

</Accordion>

<div id="what-do-i-do-if-there-are-multiple-accounts" />

<Accordion title="複数のアカウントを使用している場合は、どうすればよいですか？">

AppsFlyerでは、Google Adsの複数アカウントを問題なく使用できます。 AppsFlyerで使用できるリンクIDは1つです。そのため、Google AdsではリンクIDを1つのみ生成する必要があります。 これは、複数のアカウントで共有できます。詳細については、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/3030657">こちら</Anchor>をクリックしてください。

</Accordion>

<div id="what-happens-with-link-ids-created-at-mcc-level-vs-account-level" />

<Accordion title="MCCレベル、またはアカウントレベルで作成されたリンクIDは、どうなりますか？">

AppsFlyerでは、MCCレベルまたはアカウントレベルのリンクIDがサポートされています。 Google Adsの担当者と緊密に連携して、アカウントが正しく構成されていることを確認することをおすすめします。詳細については、<Anchor target="_blank" href="/marketers/ja/docs/recording-multiple-agency-mcc-google-ads-accounts">こちら</Anchor>をクリックしてください。

</Accordion>

<div id="what-is-parallel-tracking" />

<Accordion title="並行トラッキングとは何ですか？">

Google Adsの並行トラッキングは、ランディングページの読み込みを高速化し、訪問前の離脱を減らします。その結果、コンバージョンが増え、広告パフォーマンスが向上します。並行トラッキングでは、ユーザーは計測リンクを経由する前に広告から最終ページURLへ直接誘導され、クリックの計測はバックグラウンドで行われます。

並行トラッキングの詳細は、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">こちら</Anchor>を参照してください。

<div id="what-is-needed" />

#### 必要な設定は何ですか？

並行トラッキングを正しく機能させるには、最終ページURLをキャンペーンURLに含まれるURLと一致させ、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en">GoogleのValueTrackパラメータ`{lpurl}`</Anchor>に設定する必要があります。

これは以下によって行われます：

* 単一プラットフォーム向けの計測リンクを使用する場合（非推奨）
  * af\_rパラメータはURLで使用する必要があります。
* <Anchor target="_blank" href="/marketers/ja/docs/understand-onelink-short-vs-long-urls">OneLinkロングリンク</Anchor>を使用する（推奨）
  * キャンペーンURLに次のURLパラメータが含まれている
    * af\_android\_url
    * af\_ios\_url
    * af\_web\_dp
  * af\_dpは使用しないでください。
  * 最終ページURL（リダイレクト先URL）をGoogleのValueTrackパラメータに追加します。<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en#urlinsertion&zippy=%2Ctracking-template-only">詳細はこちら</Anchor>

例：

```
https://subdomain.onelink.me/template_id?pid=xxx&af_ios_url={lpurl}
&af_android_url={lpurl}&af_web_dp={lpurl}
```

注意：サポートされているすべてのパラメータについては、[こちらの記事](https://support.google.com/google-ads/answer/6305348?hl=en&sjid=12409212435602417786-AP#zippy=%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-campaign-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-ad-group-level%2Cfinal-url-tracking-template-or-custom-parameter)を参照してください。

並行トラッキングを使用したGoogle AdsのWebキャンペーンの設定方法は、こちらを参照してください。

</Accordion>

<div id="how-do-you-configure-a-campaign-with-android-or-ios-configuration" />

<Accordion title="AndroidまたはiOSの設定を使用して、キャンペーンを設定するには？">

<div id="important" />

> 🚧 **重要！**
>
> AppsFlyerでは、Google Adsで有効なすべてのアプリキャンペーンをサポートしています。
>
> GoogleはSRN（Self-Reporting Network）です。これらのネットワークにおけるアトリビューションフローの仕組みの詳細については、<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">こちら</Anchor>をクリックしてください。
>
> AppsFlyerは、Googleが提供するすべてのキャンペーン情報を提示できます。キャンペーンタイプ（検索、動画、ディスプレイ、リエンゲージメント）、および関連付く情報はGoogleによって決定されます。アプリキャンペーンの設定が推奨されています。他のキャンペーンタイプに関するガイダンスが必要な場合は、Googleの担当者にお問い合わせください。これらのキャンペーンの詳細については、<Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">こちら</Anchor>をクリックしてください。

<div id="android-configuration-for-google-ads" />

<Accordion title="Google Ads向けのAndroid設定">

Androidアトリビューションを可能にするには、アプリでGAID（Google AdsID）を取得しており、弊社のSDK経由でAppsFlyerに送信されていることを確認します。

<div id="creating-conversion-recording-installs" />

#### コンバージョン計測の設定（インストール）

コンバージョンの計測方法について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">こちら</Anchor>をクリックしてください。

<span id="inapp_events"></span>Google AdsのAndroid設定：アプリ内イベントの送信

Googleでのモバイルアプリインストールキャンペーンの成功度をさらに詳しく測定するには、AppsFlyerアカウントからGoogle Adsアカウントにアプリ内イベントを送信できます。

<div id="create-a-conversion-in-app-events" />

#### コンバージョンを作成（アプリ内イベント）

アプリコンバージョンのトラッキング方法の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">こちら</Anchor>をクリックしてください。

</Accordion>

<div id="ios-configuration-for-google-ads" />

<Accordion title="Google Ads向けのiOS設定">

<div id="google-ads---ios-configuration-app-campaigns" />

#### Google Ads - iOSの設定：アプリキャンペーン

アプリキャンペーンでは、1か所で設定するだけで、Google検索、YouTube、ディスプレイ全体にiOSアプリを宣伝できます。

一般的に、Google Adsは検索キャンペーン経由のiOSインストールをセルフアトリビューションできません。 これは、クリックがモバイルウェブ経由で発生するため、GoogleがデバイスからIDFAを取得できず、IDマッチングを実行できないためです。

一方、**アプリキャンペーンのiOS検索広告は、Google Adsで成果を計測できます**。これは、**Google検索アプリ**上に配信された広告が対象です。

<div id="creating-conversion-recording-installs-1" />

#### コンバージョン計測の設定（インストール）

コンバージョンの計測方法について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">こちら</Anchor>をクリックしてください。

<div id="google-ads---ios-configuration---sending-in-app-events" />

#### Google AdsのiOS設定：アプリ内イベントの送信

Googleでのモバイルアプリインストールキャンペーンの成功度をさらに詳しく測定するには、AppsFlyerアカウントからGoogle Adsアカウントにアプリ内イベントを送信できます。

<div id="creating-a-conversion-in-app-events" />

#### コンバージョンを作成（アプリ内イベント）

アプリコンバージョンのトラッキング方法の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">こちら</Anchor>をクリックしてください。

</Accordion>

</Accordion>

<div id="for-how-long-do-you-keep-google-ads--userlevel-data" />

<Accordion title="Google Adsのユーザーレベルデータの保持期間はどのくらいですか？">

Google Adsは、インストールから6か月後にユーザーレベルデータを削除するようアトリビューションプロバイダに要請しています。つまり、これらのユーザーがアプリをインストールしてから6か月後に行われたイベントは、オーガニック経由としてカウントされます。

過去の集計データは変わりません。

これは全てのGoogle Adsチャネルに共通しています。

</Accordion>

<div id="google-ads-discrepancies" />

## Google Adsでの乖離

Google Ads管理画面とAppsFlyer管理画面に表示される数値が異なる場合があります。

この数値の乖離を最小限に抑えるため、弊社はGoogleと緊密に連携していますが、乖離の原因については以下をご確認ください：

<div id="both-ios-and-android" />

#### iOS・Android共通の乖離

| **原因** | **Google Ads** | **AppsFlyer** |
| --- | --- | --- |
| **モデル化コンバージョンとICMコンバージョン** | Google Adsでは、Google独自のモデリングによって推定されたインストール数が表示されます。 一方で、ICM（Integrated Conversion Measurement）によるモデリングインストールは表示されません。 | AppsFlyerには、Google ICMによるモデル化インストール（確率論的モデリングに基づく成果の主張）が表示され、Google独自の内部モデリングによるインストールは表示されません。 |
| **アシストインストール（マルチタッチアトリビューション）** | Google AdsはSRNであるため、自社のアトリビューション期間内にGoogle Adsへのエンゲージメント後に発生したすべてのインストールを自社の成果として計測します。 | AppsFlyerはユーザージャーニーのラストクリックのみを成果とし、ラストクリック以前のエンゲージメントを<Anchor target="_blank" href="/marketers/ja/docs/measure-assisted-installs">アシスト</Anchor>と見なします。 |
| **インストールを記録するタイミング** | Google Adsはコンバージョンをクリック日時に紐づけます。 | AppsFlyerはコンバージョンを起動日時（アプリを開いた日時）に紐づけます。 |
| **タイムゾーン** | 地域によって異なります。 | 地域によって異なります。 |
| **アトリビューション期間** | 30日 | Googleとの連携はデフォルトで30日に設定されています（変更可能）。 |
| **ビュースルーコンバージョン** | Google Adsで特に設定されていない限り、ビュースルーコンバージョンは**全てのコンバージョン**列にのみ表示され、**コンバージョン**列には表示されません。 | AppsFlyerは合計インストール数、クリックインストール、ビュースルーインストールを表示します。 |
| **再インストール** | Google Adsは再インストールを「session\_start」コンバージョンとして表示します。 | AppsFlyerは、リターゲティングデータとして、再インストール（リアトリビューション）を計測および表示します。 |
| **アプリ内イベント** | Google Adsはアプリ内イベントをクリック日時に紐づけます。 | AppsFlyer管理画面では、アプリ内イベントはインストール日時に紐づけられます。ローデータレポートでは、AppsFlyerはアプリ内イベントをイベント発生日時に紐づけます。 |
| **検証ルール** | Googleは、検証ルールにかかわらず、AppsFlyerからすべての情報を受け取ります。 | AppsFlyerでは、検証ルールに基づいてインストール数を差し引くことがあります。 |
| **コスト - Google Adsキャンペーンチャネル** | Googleはキャンペーンの全てのチャネル（YouTube、ディスプレイ、検索）のコストをレポートします。 | AppsFlyerはキャンペーンの全てのチャネルについてGoogleからコストデータを取得しますが、iOS ACではYouTubeとディスプレイチャネルからのコンバージョンのみを計測します。その結果、AppsFlyerでの全体的なCPIはより高くなります。 |
| **SKANインストール** | Google Ads API V10以降、Google Adsダッシュボードは、インストールをdid\_win=TRUEとdid\_win=NULLで区別しません。ローデータのみで区別できます。 | Google Ads API V10以降、AppsFlyerはdid\_win=TRUEのポストバックからのインストールのみを表示します。その結果、AppsFlyer側のインストール数が少なくなる可能性があります。 |
| **first\_openイベント** | Google Adsは、DMAが正しく実装されているFirebaseからイベントを取得し、その後、DMA同意済みイベントの成果を主張します。 | Google Adsは、DMAが不適切に実装されているAppsFlyerからも同じイベントを取得し、その結果、すべてのイベントが非DMA同意としてレポートされ、Googleがそれらの成果を主張しません。<ul><li>DMAが正しく実装されているかを確認するには、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-export-page#download-report">ローデータレポートをダウンロード</Anchor>し、<Anchor target="_blank" href="/marketers/ja/docs/bulletin-dma-support-in-raw-data-reports">このお知らせ</Anchor>記事に指定された項目を確認してください。</li><li>SDKでDMAを実装する方法を学ぶには、[このAppsFlyer公式デベロッパーハブ](https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance)を参照してください。</li></ul> |
| **リターゲティングイベント** | Google Adsは、レスポンスに`ad_type=ClickToDownload`を含めて、リエンゲージメントの成果を主張する場合があります。 | AppsFlyerは、`ad_type=ClickToDownload`をリエンゲージメントではなく、UAコンバージョンイベントとしてカウントします。その結果、AppsFlyer側のリエンゲージメント数が少なくなる可能性があります。 |

<div id="notes" />

> 📘 **注意**
>
> * Google Adsではリターゲティングキャンペーンのすべてのインストールが同じ場所に表示されます。一方、AppsFlyerのオーバービューダッシュボードでは、ユーザー獲得ビューに新規インストール、リターゲティングビューにリアトリビューション、統合ビューに両方が表示されます。
> * Google Ads管理画面とAppsFlyerのデータを比較する際は、Google Ads管理画面のデータがサードパーティの分析ツール（AppsFlyer）からインポートされたものであることを確認してください。 FirebaseまたはGoogle Playからインポートされたデータは構造が異なるため、AppsFlyerのデータと完全には比較できません。 AppsFlyerからGoogle Adsの管理画面にデータをインポートする方法については、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">こちら</Anchor>をクリックしてください。
> * インストールイベント（Google Adsにおけるfirst\_open）を比較する場合は、Google Adsのコンバージョンレポートでインストールイベントまでドリルダウンして確認してください。 Google Adsでは、インストールだけでなく、購入やサブスクリプション登録など、すべてのコンバージョンが表示される場合があります。 そのため、すべてのコンバージョンイベントの中から、インストールイベントのみを選択して比較することが重要です。

<div id="see-also" />

> 📄 **関連記事**
>
> * iOS 14関連の考慮事項については、<Anchor target="_blank" href="/marketers/ja/docs/get-skan-postback-data-from-google-ads">Google Ads SKAdNetworkとAppsFlyerの相互運用性</Anchor>をご参照ください。

<div data-zendesk-anchors="google-ads-faq=google-ads%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HA1SM7D91QPG17WH752FBAFT=google-ads%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HA1SM7D9JWBEPNE0E8FE665E=why-am-i-not-seeing-clicks-from-google-ads h_01HA1SM7DAW984PPRGHXA5BYSX=why-am-i-not-seeing-first_open-conversions-on-google-ads why-don%E2%80%99t-i-see-installs-from-google-ads=why-don-t-i-see-installs-from-google-ads h_01K5DZBDMS0D2S5XYDC22WQ19H=why-don-t-i-see-installs-from-google-ads quick-fix=%E3%81%BE%E3%81%9A%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B%E3%81%93%E3%81%A8 h_01K5DZBDMSBDKAFHVVPYD6YKRK=%E3%81%BE%E3%81%9A%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B%E3%81%93%E3%81%A8 still-not-working=%E8%A7%A3%E6%B1%BA%E3%81%97%E3%81%AA%E3%81%84%E5%A0%B4%E5%90%88 h_01K5DZBDMSVTE6M2J235ST85DE=%E8%A7%A3%E6%B1%BA%E3%81%97%E3%81%AA%E3%81%84%E5%A0%B4%E5%90%88 h_01K7NT8FVC3K3861WN9VKRZ2HB=why-dont-i-see-inapp-events-in-the-google-ads-dashboard quick-fix-checklist=%E5%88%9D%E6%9C%9F%E7%A2%BA%E8%AA%8D%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 h_01K7NT8FVC1T557GPG7ZCYX33J=%E5%88%9D%E6%9C%9F%E7%A2%BA%E8%AA%8D%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 h_01K7PAH7VDS7NGW6R6HERGXK9H=%E6%B3%A8%E6%84%8F still-not-working::77f3165b=%E8%A7%A3%E6%B1%BA%E3%81%97%E3%81%AA%E3%81%84%E5%A0%B4%E5%90%88-1 h_01K7NT8FVCD4DNFKP3DS75ZKR0=%E8%A7%A3%E6%B1%BA%E3%81%97%E3%81%AA%E3%81%84%E5%A0%B4%E5%90%88-1 h_01HA1SM7DACQDVGWGKV5MZ63D6=can-i-stop-google-cost-sync h_01HA1SM7DA415FQP3MFC09AE3Y=do-i-need-to-create-and-then-import-session_start h_01HA1SM7DAEKGVPDTX77RJ9Y37=can-i-send-uninstall-information-to-google-ads h_01HA1SM7DAKKVZ82WF6RVEDHE9=what-google-ads-data-does-appsflyer-display h_01HA1SM7DANYQ0DAY54CH4HPV4=do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data h_01HA1SM7DA3XF8NBGYGZ0XTB69=im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard h_01HA1SM7DAY7JNTFSG86A1QGKC=what-do-i-do-if-there-are-multiple-accounts h_01HA1SM7DAYSVMENT91T2BE26Z=what-happens-with-link-ids-created-at-mcc-level-vs-account-level h_01HA1SM7DAK186BRZN970PKPRM=what-is-parallel-tracking additional-information=%E5%BF%85%E8%A6%81%E3%81%AA%E8%A8%AD%E5%AE%9A%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B h_01HA1SM7DAMNG8X22VNWMKBJ8R=%E5%BF%85%E8%A6%81%E3%81%AA%E8%A8%AD%E5%AE%9A%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B h_01HA1SM7DBNAS6DP8G9D8KFHPW=how-do-you-configure-a-campaign-with-android-or-ios-configuration h_01HA1SM7DB16T3RGBVGT5Z9REW=%E9%87%8D%E8%A6%81 h_01HA1SM7DBC38CY8AN3EPMMJFW=android-configuration-for-google-ads creating-conversion-recording-installs=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HA1SM7DBF9KDRNEV25KJHGHN=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB create-a-conversion-inapp-events=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E4%BD%9C%E6%88%90%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HA1SM7DBDQVNDQ5GG7X2PJ8K=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E4%BD%9C%E6%88%90%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HA1SM7DBKKQ9R8MQMQT9GRXV=ios-configuration-for-google-ads google-ads-ios-configuration-app-campaigns=google-ads---ios%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 h_01HA1SM7DBNSDFCJA5BP59MMQ2=google-ads---ios%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 creating-conversion-recording-installs::6a56eb4b=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB-1 h_01HA1SM7DBXCT0NS4W50D4ZGEK=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB-1 google-ads-ios-configuration-sending-inapp-events=google-ads%E3%81%AEios%E8%A8%AD%E5%AE%9A%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1 h_01HA1SM7DBEV9CJTAB5YHRJHYK=google-ads%E3%81%AEios%E8%A8%AD%E5%AE%9A%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1 creating-a-conversion-inapp-events=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E4%BD%9C%E6%88%90%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88-1 h_01HA1SM7DBCQYSJ3R67F0856QK=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E4%BD%9C%E6%88%90%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88-1 for-how-long-do-you-keep-google-ads%E2%80%99-userlevel-data=for-how-long-do-you-keep-google-ads--userlevel-data h_01HA1SM7DBFAAV7C4ENA34B7JP=for-how-long-do-you-keep-google-ads--userlevel-data google-ads-discrepancies=google-ads%E3%81%A7%E3%81%AE%E4%B9%96%E9%9B%A2 h_01HA1SM7DBA7KK1DXFCE2G0QTP=google-ads%E3%81%A7%E3%81%AE%E4%B9%96%E9%9B%A2 both-ios-and-android=iosandroid%E5%85%B1%E9%80%9A%E3%81%AE%E4%B9%96%E9%9B%A2 h_01HA1SM7DB18BTDKK5BK4949HX=iosandroid%E5%85%B1%E9%80%9A%E3%81%AE%E4%B9%96%E9%9B%A2 h_01HA1SM7DBSTAREA36YWRRRG82=%E6%B3%A8%E6%84%8F-1 h_01HDP2XBSEJVQ5G0MD0V5R05CM=%E9%96%A2%E9%80%A3%E8%A8%98%E4%BA%8B" />

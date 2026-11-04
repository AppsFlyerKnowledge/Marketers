---
title: はじめに — マーケティング担当者向けのオンボーディング
metadata:
  keywords:
    - SDK
    - Integration
    - Reports
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2015-01-18T11:03:01Z'
  edited_at: '2026-10-14T09:26:58Z'
  id: 207033486
  locale: ja
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/ja/articles/207033486
---
> **概要：** AppsFlyerアカウントを最大限に活用するために、さまざまな重要な設定を行いましょう。また、アプリとチームメンバーをAppsFlyerにオンボーディングするための手順やタイムライン、そして従属性について理解しましょう。

<Embed title="はじめに — マーケティング担当者向けのオンボーディング" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/gamcb25kgu" providerUrl="https://fast.wistia.com" />

<div id="introduction" />

## はじめに

この記事では、広告主（アプリ所有者）の**プロダクトマネージャーがAppsFlyerを導入するための計画・実行手順**について説明しています。各項目について、作業担当者とおおよその作業時間の目安が記載されています。

この記事の推定時間は、一般的なガイダンスとしてのみ意図されていることに注意してください。この目安は、多くのお客様との経験に基づいて示していますが、アプリ所有者、アプリ、および実装工程などは、お客様によって異なります。そのため、実際にこれらの工程にかかる時間はここに記載されている目安と異なる場合があります。

<div id="account-setup" />

## アカウント設定

**アカウント管理者**は、次の手順を完了する必要があります：

| ステップ | 時間 | 備考 |
| --- | --- | --- |
| <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">アカウントのサインアップ</Anchor> | 5分 | アカウント管理者（アドミン）は、弊社からの重要なお知らせメールを受け取ることができる、実際のAppsFlyerユーザーであることが理想的です。 |
| AppsFlyerダッシュボードを使用する<Anchor target="_blank" href="/marketers/ja/docs/user-management#creating-users">アカウントユーザーの追加</Anchor>、および権限の設定 | 1アカウントユーザーあたり1分程度 | <Anchor target="_blank" href="/marketers/ja/docs/user-management#creating-users">場合によって</Anchor>は、複数のアカウントにユーザーを追加できます。 |

**結果：** ようこそ！これで、アクティブなAppsFlyerアカウントと、それにアクセスできるアカウントユーザーができました。

<div id="tip" />

> 👍 **ヒント**
>
> AppsFlyerを初めてご利用になる方：AppsFlyerで何かできるのかをより詳しく見てみませんか？<Anchor target="_blank" href="/marketers/ja/docs/welcome-to-appsflyer#appsflyerで何ができますか">こちらの6分間の動画</Anchor>をご覧ください。

<div id="app-onboarding" />

## アプリのオンボーディング

以下の**手順1〜3**は、AppsFlyerに追加されるすべてのアプリにおいて、必須です（オプションとして記載されている場合を除く）。

このガイドを使用するか、ダッシュボードのアプリのオンボーディング画面から手順に従うことができます。オンボーディング画面では、モバイルアプリをアトリビューション用に準備するために必要な基本的な手順を案内しています。これを使用する場合は、このガイドで、特定のビジネスニーズに必要な追加のサブステップを確認することもお勧めします。

**アプリのオンボーディング画面へのアクセス：**

1. 管理画面右上の、メールアドレスのドロップダウンメニューバーをクリックします。
2. 「アプリのオンボーディング」をクリックします。

<div id="step-1-app-setup" />

## ステップ1：アプリ設定

**アカウント管理者**は、アプリごとに次の手順を完了する必要があります：

| ステップ | 時間 | 備考 |
| --- | --- | --- |
| AppsFlyerアカウントに<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">アプリを追加</Anchor> | 1分 | アプリが追加できない場合、大抵の場合、既に別のアカウントに追加されていることが原因です（他のアカウントや代理店が以前アプリを登録済の場合など）。<Anchor target="_blank" href="/marketers/ja/docs/transferring-apps-between-accounts">アプリ移管</Anchor>に関しては、担当CSMまたは hello@appsflyer.com までお問合せください。<br /><br />アプリの追加に関してその他の<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#トラブルシューティング">トラブルシューティングの手順</Anchor>を参照してください。 |
| アプリの<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#追加情報を入力しますwebアプリには該当しません">タイムゾーン、通貨</Anchor>、子ども向けかどうかを設定します | 1分 |  |
| アプリ設定：  <br /><Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>（<Anchor target="_blank" href="/marketers/ja/docs/app-settings#reattribution-window">アプリ設定</Anchor>画面） | 1分 | リアトリビューション期間は、初回インストール計測後に、**再インストールが発生しても新規インストールとして計測しない**期間のことを指します。デフォルトの期間は90日で、必要に応じて変更できます。 |
| [オプション] 既存のユーザーデバイスをAppsFlyerに移行 | 2時間 | 既にアプリに相当数のユーザーがいる場合は、二重課金を避けるためにも、<Anchor target="_blank" href="/marketers/ja/docs/migration-to-appsflyer-from-other-vendors#デバイスidの移行任意">AppsFlyerへのユーザー移行</Anchor>を検討してください。<br /><br />**注記：** アカウントアドミン<strong>（AppsFlyer CSMまたは [hello@appsflyer.com](mailto:hello@appsflyer.com)) のサポートチームまでお問合せください）</strong> |

**結果：** AppsFlyer管理画面にアプリが定義されました。

<div id="step-2-sdk--api-integration" />

## ステップ2：SDK / API実装

[ステップ1でAppsFlyerで定義されたすべてのアプリに対して、次の手順を実行します：アプリ設定](/docs/getting-started-onboarding-for-marketers#ステップ1アプリ設定)：

| ステップ | 担当者 | 時間 | 備考 |
| --- | --- | --- | --- |
| アプリで使用したい利用可能なオプションを検討し<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">SDKの機能</Anchor>を選択 | プロダクトマネージャー | 1時間単位 | <ul><li>基本的なアトリビューション以上の考慮事項：<ul><li>キャンペーンでユーザーをアプリにディープリンクする予定がありますか？</li><li>アプリで<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#アトリビューションデータとディープリンクデータの取得">アトリビューションデータへのアクセスやディープリンクデータ</Anchor>が必要ですか？</li><li>AppsFlyerデータには<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">カスタマーユーザーID（CUID）</Anchor>を含めますか？</li><li>どのように<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">iOS 14以降のデバイスに対するプライバシー設定</Anchor>を実装しますか？アンインストール、クロスプロモーションキャンペーンなどを計測する予定ですか？</li></ul></li><li>CTVアプリをお持ちですか？<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTVの概要</Anchor>を参照してください。</li></ul> |
| 計測する<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">アプリ内イベント</Anchor>を決定 | プロダクトマネージャー | 1時間単位 | ユーザーがアプリをインストールした後に行うイベントを記録することで、ユーザーの**質**をより深く理解することができます。<br /><br />[アプリ内イベントジェネレーター](https://evgen.appsflyer.com/)では、お客様の業種で<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#recommended-events-by-business-vertical">推奨される</Anchor>アプリ内イベントとパラメーターの包括的なリストを提供しています。独自のイベントとパラメータを追加できます。  <br />**コード** ボタンをクリックして、開発者向けに自動生成されたコードを表示およびコピーします。 |
| アトリビューション／ディープリンクデータの取得方法の選択 | プロダクトマネージャー | 30分 | 利用できる<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#アトリビューションデータとディープリンクデータの取得">メソッド</Anchor>を確認：<ul><li><Anchor target="_blank" href="/marketers/ja/docs/pull-api-raw-data">Pull API</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/push-api-streaming-raw-data">Push API</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">Unified Deep Linking API</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/conversion-data-payloads-and-scenarios">コンバージョンデータの取得</Anchor></li></ul> |
| 開発者への引き継ぎ | プロダクトマネージャー | 5分 | 準備して、開発者に以下の手順とタスクを記載したメールを送信してください：<ul><li>SDK / API実装</li><li>アプリ内イベントマッピング</li></ul>これらは、アプリの追加ウィザードの <Anchor target="_blank" href="https://hq1.appsflyer.com/onboarding/apps">SDK実装</Anchor> タブにあります。 |
| デベロッパーによる実装 | アプリ開発者 | 3時間 | SDK実装とアプリ内イベントマッピングの指示 / タスクが記載されたマーケターからのメールを受信します。<br /><br />AndroidとiOSの場合は、<Anchor target="_blank" href="https://dj.dev.appsflyer.com/?utm_source=dashboard&utm_medium=app-onbrd-mail-a">AppsFlyer Dev Journey</Anchor>を使用して自動的に実装するか、以下のリンクを使用して手動で実装してください。<br /><br />AppsFlyerのデベロッパー向けリソース：<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">Android</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">iOS</Anchor></li><li>Unity</li><li><Anchor target="_blank" href="/marketers/ja/docs/windows-sdk-integration-for-developers">Windows Phone</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/other-platforms">その他のプラットフォーム</Anchor></li></ul> |
| <Anchor target="_blank" href="/marketers/ja/docs/testing-the-sdk-integration-for-marketers">連携テスト</Anchor> | プロダクトマネージャー /  <br />アプリ開発者 | 1時間単位 | SDKの実装テストを行ってください。アプリをストアで公開する前と後、どちらでも実行可能です。デバッグアプリを使用することで、本番アプリのデータをクリーンに保つことができます。<br /><br />Android および iOS アプリのみ：必ず<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">テストデバイスの登録</Anchor>を行ってください。 |
| アプリの新バージョンのリリース | プロダクトマネージャー | 1時間単位 | <Anchor target="_blank" href="/marketers/ja/docs/preparing-for-the-app-store-review-nutrition-labels">App Storeの審査に向けた準備</Anchor>をしてください。 |

**結果：** これで、アプリのインストール計測、アプリ内イベント計測、その他追加の開発工数を必要としないAppsFlyer機能の準備が整いました。

<div id="step-3-attribution-setup" />

## ステップ3：アトリビューションの設定

[ステップ1でAppsFlyerで定義されたすべてのアプリに対して、次の手順を実行します：アプリ設定](/docs/getting-started-onboarding-for-marketers#ステップ1アプリ設定)：

| ステップ | 担当者 | 時間 | 備考 |
| --- | --- | --- | --- |
| AppsFlyerで計測する**有料**のメディアソースを設定 | プロダクトマネージャー /  <br />マーケティング担当者 | メディアソースごとに15分 | <Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">セルフレポーティングネットワーク</Anchor> (SRN) について：<ul><li><Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup">Meta広告</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/apple-ads-integration-setup">Apple Ads</Anchor></li><li>GMP (Doubleclick)</li></ul>SRN以外のアドネットワークの計測について：<ul><li><Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">他の連携済みパートナー</Anchor></li><li>AppsFlyer<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">計測リンク</Anchor>の構造とパラメーター</li></ul> |
| OneLinkを使用して**オウンドメディア** (モバイルWebサイト、ソーシャルメディア、ユーザー招待など) を計測 | プロダクトマネージャー | 1時間単位 | オウンドメディアのユースケースに対応する<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide#追加オプション">OneLinkベースのソリューションについて</Anchor> |
| オウンドメディアに関するデベロッパー実装 | アプリ開発者 | 0-6.5時間（導入するソリューションによって異なる） | 開発者向け：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">ディープリンクについて</Anchor> |
| アトリビューション期間の設定 | プロダクトマネージャー | メディアソースごとに2分 | 詳細：<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">クリックとビュースルールックバック期間について</Anchor> |
| [オプション] リターゲティングキャンペーンを有効にする | プロダクトマネージャー | 2分 | <Anchor target="_blank" href="/marketers/ja/docs/app-settings#reengagement-attribution">アプリ設定画面でリターゲティング計測を有効</Anchor>にします。<br /><br />詳細：<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティングガイド</Anchor> |

**結果：** アプリにトラフィックをもたらすすべてのメディアソースは、新規ユーザーやリピーターがエンゲージするたびに計測されます。

<div id="step-4-additional-setup" />

## ステップ4：追加設定

[ステップ1でAppsFlyerで定義されたすべてのアプリに対して、次の手順を実行します：](/docs/getting-started-onboarding-for-marketers#ステップ1アプリ設定)[アプリ設定](/docs/getting-started-onboarding-for-marketers#ステップ1アプリ設定)

特定の手順は、ビジネス目標を達成するために必須の場合があります。

| ステップ | 担当者 | その他のリソース |
| --- | --- | --- |
| 収益を計測してユーザー獲得キャンペーンを最適化 | プロダクトマネージャー /  <br />デベロッパー | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/legacy-receipt-validation-for-in-app-purchases">アプリ内購入の検証</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution">広告収益</Anchor></li><li>サブスクリプション</li></ul> |
| マーケティングコストデータを集約し確認する方法について確認 | プロダクトマネージャー | <Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview">ROI360 — コスト集計の概要</Anchor> |
| アプリが連携する他の<Anchor target="_blank" href="/marketers/ja/docs/3rd-party-platforms">サードパーティプラットフォーム</Anchor>の設定 | プロダクトマネージャー /  <br />デベロッパー | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/mparticle-integration-with-appsflyer">mParticle</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/segment-integration">Segment</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/mixpanel-integration-with-appsflyer">Mixpanel</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/amplitude-integration-with-appsflyer">Amplitude</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/adobe-analytics-integration-with-appsflyer">Adobe Analytics</Anchor> (Omniture)</li><li><Anchor target="_blank" href="/marketers/ja/docs/braze-formerly-appboy-integration-with-appsflyer">Braze</Anchor></li></ul> |
| 時間とコストの節約に役立つAppsFlyerプレミアム機能を確認しましょう。 | プロダクトマネージャー | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/audiences-guide">Audiences</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/pivot-table-user-metrics">ピボット表</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">Data Locker</Anchor></li></ul> |
| 不正とターゲティングミスからキャンペーンを保護 | プロダクトマネージャー | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide">Protect360—不正防止ソリューション</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/implement-validation-rules-to-prevent-fraud">検証ルール</Anchor>を使用してターゲティングミスを防止</li></ul> |
| アプリの外で発生するアプリ内イベントを計測するためにS2S APIの実装 | プロダクトマネージャー /  <br />デベロッパー | <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S REST API</Anchor> |
| メディアソースのアンインストール率を計測 | プロダクトマネージャー /  <br />デベロッパー | アンインストール計測 |
| チャネル、プラットフォーム、デバイスに渡るカスタマージャーニーの全体像を把握 | プロダクトマネージャー /  <br />デベロッパー | <Anchor target="_blank" href="/marketers/ja/docs/people-based-attribution-pba-overview">ピープルベースアトリビューション（PBA）</Anchor> |
| プライバシー規制への準拠を確認：GDPR、 CCPAなど | プロダクトマネージャー /  <br />デベロッパー | ユーザーが計測から<Anchor target="_blank" href="/marketers/ja/docs/apply-privacy-preserving-sdk-methods">オプトアウト</Anchor>できるように設定する |

<div id="enrich-your-knowledge" />

## 知識を深める

以下のポイントは、すべてのAppsFlyerユーザーにおすすめです：

| ステップ | 時間 |
| --- | --- |
| AppsFlyerのオーバービュー管理画面をよりよく理解する | 15分 |
| <Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">AppsFlyerの生涯価値（LTV）データとアクティビティデータ</Anchor>の違いを知る（アプリ内イベントの値が「オーバービュー」と「アクティビティ」管理画面で異なる理由を理解できます） | 15分 |
| AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">アトリビューションモデル</Anchor>を理解する | 30分 |
| <Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview">集計レポートツールとアナリティクス</Anchor>について | 30分 |
| <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ローデータレポート</Anchor>について | 30分 |

<div id="related" />

## 関連事項

<div id="tip-1" />

> 👍 **ヒント**
>
> ユーザー獲得（UA）は初めてですか？ユーザー獲得のための計画、実行、そして継続的に最適化をするための重要なポイントや課題などについては<Anchor target="_blank" href="https://www.appsflyer.com/resources/ecommerce/getting-started-user-acquisition-apps-complete-guide/">こちら</Anchor>を参考にしてください。

<div id="note" />

> 📘 **注**
>
> AppsFlyerの導入が初めて、そしてマーケターではありませんか？心配は不要です！
> 以下のガイドを選択して、今すぐ始めましょう：
>
> * <Anchor target="_blank" href="/partners/ja/docs/getting-started-agency-onboarding">代理店アカウント：はじめに</Anchor>
> * <Anchor target="_blank" href="/partners/ja/docs/getting-started-onboarding-guide-for-ad-networks">アドネットワーク：はじめに</Anchor>

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB 01H8BD2FJ6TQ5FP9625MNP2B3Z=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB step-1-account-setup=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E8%A8%AD%E5%AE%9A 01H8BD2FJ6E8KZW41V04SBDQPQ=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E8%A8%AD%E5%AE%9A 01H8BD2FJ6A39JB8J0PQ3EY52N=%E3%83%92%E3%83%B3%E3%83%88 app-onboarding=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%AA%E3%83%B3%E3%83%9C%E3%83%BC%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0 01H8V6FS97NTTF1VPQQDZQT973=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%AA%E3%83%B3%E3%83%9C%E3%83%BC%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0 step-2-app-setup=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971%E3%82%A2%E3%83%97%E3%83%AA%E8%A8%AD%E5%AE%9A 01H8BD2FJ61S3Z22CD01H6F39E=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971%E3%82%A2%E3%83%97%E3%83%AA%E8%A8%AD%E5%AE%9A step-3-sdk-integration=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972sdk--api%E5%AE%9F%E8%A3%85 01H8BD2FJ6CY53QXVB5QC98KTT=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972sdk--api%E5%AE%9F%E8%A3%85 step-4-attribution-setup=%E3%82%B9%E3%83%86%E3%83%83%E3%83%973%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A 01H8BD2FJ6Q8R83FV0XS5B93B3=%E3%82%B9%E3%83%86%E3%83%83%E3%83%973%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A step-5-additional-setup=%E3%82%B9%E3%83%86%E3%83%83%E3%83%974%E8%BF%BD%E5%8A%A0%E8%A8%AD%E5%AE%9A 01H8BD2FJ76WD0MRCJXZH8XABN=%E3%82%B9%E3%83%86%E3%83%83%E3%83%974%E8%BF%BD%E5%8A%A0%E8%A8%AD%E5%AE%9A enrich-your-knowledge=%E7%9F%A5%E8%AD%98%E3%82%92%E6%B7%B1%E3%82%81%E3%82%8B 01H8BD2FJ7ZV0ZYHQZ8DBTTFFK=%E7%9F%A5%E8%AD%98%E3%82%92%E6%B7%B1%E3%82%81%E3%82%8B related=%E9%96%A2%E9%80%A3%E4%BA%8B%E9%A0%85 01H8BD2FJ748GFC4VJWWYGGN1K=%E9%96%A2%E9%80%A3%E4%BA%8B%E9%A0%85 01H8BD2FJ712NGA534TCSWQGR8=%E3%83%92%E3%83%B3%E3%83%88-1 01H8BD2FJ7PRJAA1K8MESRK7VA=%E6%B3%A8" />

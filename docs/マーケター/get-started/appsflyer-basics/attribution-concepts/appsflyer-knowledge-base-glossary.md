---
title: AppsFlyerナレッジベース用語集
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Developers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2019-01-01T10:12:13Z'
  edited_at: '2026-10-28T09:07:42Z'
  id: 360000732237
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/360000732237
---
> **At a glance:** AppsFlyerで使用する用語を説明します。

 **[A](#a) · [B](#b) · [C](#c) · [D](#d) · [E](#e) · [F](#f) · [G](#g) · [I](#i) · J · [K](#k) · [L](#l) · [M](#m) · [N](#n) · [O](#o) · [P](#p) · [Q](#q) · [R](#r) · [S](#s) · [T](#t) · [U](#u) · [V](#v) · [W](#w) · [X](#X) · Y · Z** 

*\*翻訳された用語も、英語のアルファベット順に掲載しています。*

<Accordion title="A">

<div id="account-owner" />

#### アカウント所有者

**管理者**とも呼ばれます。  
AppsFlyerアカウントの主要なユーザーで、最上位の管理者としてアクセス権と操作権限を持ちます。   
［関連記事］、［関連記事］

<div id="ad" />

#### 広告

AppsFlyerでは、商品、ブランド、サービスの宣伝に使用するクリエイティブの名前を記録します。

<div id="ad-cost" />

#### 広告コスト

広告に費やした金額です。 AppsFlyerは、クリック、コストAPI、CSVファイルのアップロードを通じて広告コストを記録します。 <Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview">［関連記事］</Anchor>

<div id="ad-group" />

#### 広告グループ

類似するターゲット（商品やサービスの種類など）を持つ、1つ以上の広告をまとめたものです。各キャンペーンには、1つ以上の広告セットが含まれます。  
 *例：*Google広告では、特定の広告に関連するキーワードを整理するために使用します。

<div id="ad-hierarchy" />

#### 広告の階層

広告＞広告セット（広告グループとも呼ばれる）＞キャンペーン＞メディアソース

<div id="ad-network" />

#### アドネットワーク

マーケターの広告配信先となるアプリやWebサイトを集めたネットワークです。 パブリッシャーの広告枠を集約し、マーケターの需要と結び付けます。 <Anchor target="_blank" href="/partners/ja/docs/ad-network-onboarding">［関連記事］</Anchor>

<div id="ad-revenue" />

#### 広告収益

アプリ内広告によってアプリが得る収益です。 AppsFlyerで広告収益データを使用すると、メディアソースごとに獲得ユーザーのROIを自動で確認できます。 <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution">［関連記事］</Anchor>

<div id="ad-set" />

#### 広告セット

1つ以上の広告をまとめたものです。ターゲティング、予算、配信スケジュール、入札、掲載位置の設定に使用します。

<div id="ad-spend" />

#### 広告費

商品や施策の広告に費やした金額です。  
 *計算式：*広告による収益÷広告費＝広告費用対効果（ROAS）  
<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">［関連記事］</Anchor>、<Anchor target="_blank" href="/partners/ja/docs/cost-import-for-ad-networks">［関連記事］</Anchor>

<div id="ad-types" />

#### 広告タイプ

*種類：*音声、バナー、インタースティシャル、プレイアブル（アプリの操作体験を試せる広告）、リワード動画（視聴と引き換えにアプリ内報酬を提供する動画）、スポンサーコンテンツ、テキスト、動画<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#計測リンクのパラメータ">［関連記事］</Anchor>

<div id="ad-network-integration" />

#### アドネットワーク連携

記録とアトリビューションのため、アドネットワークをAppsFlyerのパートナーとして設定する処理です。 <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">［関連記事］</Anchor>

<div id="admin" />

#### 管理者

**アカウント所有者**とも呼ばれます。  
AppsFlyerアカウントの主要なユーザーで、最上位の管理者としてアクセス権と操作権限を持ちます。  
 ［関連記事］、［関連記事］

#### Advanced Privacy

**iOS 14.5以降の、同意していないユーザーにのみ適用されます。** Advanced Privacyでは、広告主がユーザーレベルのアトリビューションデータの提供可否を**パートナー単位**で制御できます。アプリ単位で適用されるAggregated Advanced Privacyとは異なります。特定のパートナーで有効にすると、**そのパートナー**に共有するポストバックとイベントデータが、集計・匿名化されたものになります。広告主自身は、ユーザーレベルのローデータを**利用できます**。 <Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">［関連記事］</Anchor>

<div id="advertiser" />

#### 広告主

関連用語：**マーケター**、**アプリ所有者**。  
アプリやWebサイトを所有し、コンバージョンを増やすために、さまざまなチャネルで広告・マーケティングを行う事業者です。

<div id="advertising-id" />

#### 広告ID

**Ad ID**とも呼ばれます。  
OSが定める、ユーザーがリセット可能なデバイスIDです（IDFA、GAID、OAID）。ユーザーの広告接触やアプリ利用の計測に使用します。

#### AdWords

現在のGoogle広告です。<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers">［関連記事］</Anchor>

<div id="affiliate-networks" />

#### アフィリエイトネットワーク

**パブリッシャー**とも呼ばれます。  
自社Webサイトの広告枠でマーケターのオファーを宣伝し、紹介したユーザーごとに報酬を受け取ります。パブリッシャーは、アプリへの訪問者が生んだ収益の一部、または特定のアクションを完了したアプリ訪問者1人あたりの報酬を受け取ります。 ［関連記事］

<div id="agency" />

#### 代理店

顧客のアプリマーケティングキャンペーンの運用、アトリビューション、計測を行う第三者です。顧客には、広告主、マーケター、アプリ所有者などが含まれます。<Anchor target="_blank" href="/partners/ja/docs/about-agency-accounts">［関連記事］</Anchor>

<div id="aggregate-data" />

#### 集計データ

詳細なデータをまとめて作成した、アカウント単位やアプリ単位などの上位レベルのデータです。<Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview">［関連記事］</Anchor>

#### Aggregated Advanced Privacy

**iOS 14.5以降の、同意していないユーザーにのみ適用されます。** Aggregated Advanced Privacyでは、広告主がユーザーレベルのアトリビューションデータの提供可否を**アプリ単位**で制御できます。パートナー単位で適用されるAdvanced Privacyとは異なります。有効にすると、**すべてのパートナー**に共有するポストバックとイベントデータが集計・匿名化され、広告主自身もユーザーレベルのアトリビューションデータを**利用できなくなります**。この設定は、パートナー単位のAdvanced Privacyの設定より優先されます。 <Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">［関連記事］</Anchor>

<div id="all-installs-network" />

#### すべてのインストールのポストバックを受信するアドネットワーク

自社に紐付いていないインストールも含め、すべての流入元の新規アプリインストールについてポストバックを受信するアドネットワークです。

<div id="all-launches-network" />

#### すべての起動のポストバックを受信するアドネットワーク

自社に紐付いていない起動も含め、すべての流入元の新しいアプリ起動についてポストバックを受信するアドネットワークです。

<div id="analytics-platform" />

#### 分析プラットフォーム

各種要素をまとめて提供し、ユーザーのニーズに応えるためのソリューションです。特に、データを活用する大企業などのニーズを想定して設計されています。  
 *提供する要素：*グラフなどのデータ可視化ツール、ダッシュボードの構成要素、カスタマイズ用テーマ

#### Android App Link

Androidアプリ向けのディープリンクの一種です。ユーザーのデバイスにアプリがインストールされていれば、リンクからアプリ内の特定のページや場所を直接開けます。アプリに一意に関連付けられたHTTP/HTTPSリンクで、途切れのない一体的なユーザー体験を提供するために設計されています。

ユーザーがAndroid App Linkをクリックすると、Android OSが、Webブラウザとアプリのどちらでリンクを開くかを適切に判断できます。 Android App Linksでは、Digital Asset Linksを追加して検証し、アプリのコードとWebサイトの関連ドメインの両方で設定する必要があります。 <Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">［関連記事］</Anchor>

#### Android ID

Google Play開発者サービスを搭載したAndroidデバイスの、リセットできないデバイスIDです。   
Android 10より前：GAIDを利用できない場合、このIDをアトリビューションに使用できます。   
関連する<Anchor target="_blank" href="https://www.google.com/url?q=https://developer.android.com/about/versions/10/privacy/changes&sa=D&ust=1590521123347000&usg=AFQjCNFwiLOxMlguJjQkG4NE5JkxESxEiw">プライバシー規制</Anchor>を参照してください。

#### API

**Application Program Interface**  
AppsFlyerと顧客やビジネスパートナーの間で、データをやり取りするためのルーチン、プロトコル、ツールです。  
 *例：*Push API、Pull API、Master API、Cohort API、サーバー間API

<div id="api-call" />

#### API呼び出し

リクエストを送信した際に行われる処理です。リクエストが転送・処理され、その応答が返されます。

<div id="app-id-android--ios" />

#### アプリID（Android・iOS）

ストアのアプリページのURLに含まれる、大文字と小文字を区別する一意の識別子です。

*例：*  
AndroidのアプリID＝***com.coolcompany.coolapp***などのパッケージ名

iOSのアプリID＝idと9桁または10桁のApp Store IDの組み合わせ。例：***id123456789***

<div id="app-launch" />

#### アプリ起動

アプリが開かれることです。 SDKの起動や、アプリ所有者が定めたロジックに基づいて集計します。  
 *例：*ウイルス対策アプリを1日使用したことを、1セッションと数える場合があります。 <Anchor target="_blank" href="/marketers/ja/docs/measure-sessions">［関連記事］</Anchor>

<div id="app-owner" />

#### アプリ所有者

関連用語：**広告主**、**マーケター**。  
アプリを所有し、ユーザー数を増やすために、さまざまなプラットフォームで広告・マーケティングを行う事業者です。

<div id="app-store-analytics" />

#### アプリストアの分析

アプリストア（Google Play、Apple App Storeなど）のアプリデータを収集・分析することです。

#### AppsFlyer

AppsFlyerのナレッジベース記事では、AppsFlyerが提供するプラットフォームを指します。

#### AppsFlyer ID

インストール時にAppsFlyerが生成する、アプリの一意の識別子です。 アプリを削除して再インストールすると、新しいIDが生成されます。 このIDは、AppsFlyerが記録するすべてのイベントに表示されます。

#### ARPDAU

**日次アクティブユーザーあたりの平均収益**  
1日あたりのアクティブユーザー1人が生み出す平均収益です。  
 *計算式：*総収益÷アクティブユーザー数（どちらも24時間の値）

#### ARPU

**ユーザーあたりの平均収益**  
一定期間内にユーザー1人が生み出す平均収益です。  
 *計算式：*総収益÷ユニークユーザー数

#### ARPPU

**課金ユーザーあたりの平均収益**  
一定期間内に課金ユーザー1人が生み出す平均収益です。  
 *計算式：*総収益÷課金ユーザー数

#### ASO

**アプリストア最適化**  
App Storeでアプリを見つけてもらいやすくするために使用します。

<div id="assisted-installs" />

#### アシストインストール

**マルチタッチアトリビューション**とも呼ばれます。  
インストール前の最後の計測対象の広告接触に貢献した、他のメディアソースでの広告接触です。 <Anchor target="_blank" href="/marketers/ja/docs/measure-assisted-installs">［関連記事］</Anchor>

<div id="attribution" />

#### アトリビューション

クリックやインプレッションを通じて、メディアソースに紐付けられたインストールやその他のイベントです。 <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">［関連記事］</Anchor>

<div id="attribution-link" />

#### 計測リンク

クリックの記録と、アプリのダウンロード先へのリダイレクトに必要な情報を含む、広告用のURLです。アトリビューションと分析に使用する情報が含まれます。    
*例：*ユーザーが計測リンクをクリックすると、AppsFlyerは情報を記録し、アプリのダウンロード先へリダイレクトします。

#### Audiences

ユーザーをオーディエンスのグループに分け、簡単かつ正確にターゲティングできるAppsFlyerの機能です。 <Anchor target="_blank" href="/marketers/ja/docs/audiences-guide">［関連記事］</Anchor>

</Accordion>

<Accordion title="B">

<div id="banner" />

#### バナー

広告対象のWebサイトやアプリへのリンクを含む、Webサイト上の画像広告です。 マーケターはAppsFlyerのSmart Bannersを使用して、自社のモバイルWebサイト訪問者によるアプリインストールのアトリビューションと、その質の計測を行います。 <Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">［関連記事］</Anchor>

<div id="bi-system" />

#### BIシステム

ローデータを、事業上の意思決定に役立つ情報に変換するための処理、構成、技術の総称です。

<div id="bid" />

#### 入札単価

マーケターが[CPM、CPI、CPC、CPA](#c)に基づくキャンペーンで支払う単価です。

<div id="brand-bundle" />

#### ブランドバンドル

同じブランドに関連するWebアプリとモバイルアプリのアトリビューション、アクティビティ、収益データを統合します。 <Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings">［関連記事］</Anchor>

<div id="branded-link" />

#### ブランドリンク

ブランド名や関連する用語を使用して作成した短縮URLです。 <Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain">［関連記事］</Anchor>  
*例：*ブランド名が*Great App*の場合、*promotions.greatapp.com*のようなブランドリンクを使用できます。

<div id="bundle-id" />

#### バンドルID

Appleが個々のアプリの識別に使用する一意の識別子です。 登録、変更、削除が可能です。    
*例：*バンドルIDが割り当てられていないアプリは、iTunesに提出できません。

</Accordion>

<Accordion title="C">

#### CAC

**顧客獲得コスト**  
アプリのインストールや、インストール後のアクションを実行するユーザーを獲得するためのコストです。  
 *計算式：*営業・マーケティング費用÷新規顧客数

<div id="campaign" />

#### キャンペーン

1つ以上の広告セットをまとめたものです。目的とKPI、ターゲットオーディエンス、予算とスケジュール、使用するプラットフォーム、クリエイティブと広告形式、戦略などで構成されます。<Anchor target="_blank" href="/marketers/ja/docs/measure-paid-media">［関連記事］</Anchor>。

<div id="campaign-id" />

#### キャンペーンID

メディアソース内でキャンペーンを識別する一意のIDです。

<div id="carrier" />

#### 通信事業者

Wi-Fiではなく、携帯電話回線によるデータ通信を提供する事業者です。

<div id="channel" />

#### チャネル

特にGoogle広告やMeta広告など、メディアソース内のトラフィックの区分です。  
 *例：*GoogleのYouTube、Meta広告のInstagram

<div id="churn" />

#### チャーン（顧客離脱）

**Customer attrition**、**Turnover**、**Defection**とも呼ばれます。  
マーケターは、AppsFlyerのリテンションレポートとアンインストール計測を使用して、チャーン（顧客の離脱）を推定できます。  
*計算式：*一定期間内に失ったユーザー数÷期間開始時のユーザー数

<div id="click" />

#### クリック

メディアソース内でユーザーが広告に反応し、広告対象のページやアプリ内画面にリダイレクトされることです。

<div id="click-flooding" />

#### クリック洪水

**クリックスパミング**とも呼ばれます。  
インストール直前の最後のクリックとして計測されることを狙い、アドネットワークが大量の不正なクリックを送信する行為です。

<div id="click-url" />

#### クリックURL

**計測リンク**とも呼ばれます。

<div id="client" />

#### クライアント

広告主、マーケター、アプリ所有者を指します。

#### COA

**獲得コスト**  
企業が新たな顧客、資産、商品を獲得する際の費用です。 <Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview">［関連記事］</Anchor>

<div id="cohort-analysis" />

#### コホート分析

ユーザーをグループに分けて、行動パターンを特定するための集計データです。各グループ（コホート）は通常、一定期間内の共通の特性や体験に基づいて構成されます。 <Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard">［関連記事］</Anchor>

<div id="contributor" />

#### 貢献元

**アシスト**とも呼ばれます。  
インストール前かつルックバック期間内に広告接触があったものの、インストールの計測元としては選ばれなかったメディアソースやキャンペーンです。

<div id="conversion" />

#### コンバージョン

事業にとって成果とみなす、広告に関連するアクションをユーザーが完了することです。 AppsFlyerでは、メディアソースに紐付いたインストール、再インストール、リエンゲージメントを、すべてコンバージョンとして扱います。例：ユーザーが広告をクリックした後にアプリをインストールします。このインストールが、新たなコンバージョンとなります。<Anchor target="_blank" href="/marketers/ja/docs/about-conversion-rates">［関連記事］</Anchor>

<div id="conversion-chain" />

#### コンバージョンに至る一連の流れ

広告閲覧からアプリ内アクションに至る、一連のコンバージョンイベントです。  
 *例：*広告クリック、ランディングページ訪問、Smart Bannerのクリック、アプリのインストール、会員登録、購入というユーザーの行動。

<div id="conversion-event" />

#### コンバージョンイベント

アプリユーザーが達成する、事業上重要な節目です。インストール前のクリックやインプレッション、ユーザーが実行したアプリ内イベントなどが含まれます。  
*例*：アプリのインストール、カートへの追加、購入手続きの開始、購入

<div id="conversion-rate" />

#### コンバージョン率

コンバージョンに至る一連の流れで、ある段階から次の段階へ進んだユーザーの割合です。 <Anchor target="_blank" href="/marketers/ja/docs/about-conversion-rates">［関連記事］</Anchor>

<div id="conversion-types" />

#### コンバージョンタイプ

**リターゲティングのコンバージョンタイプ**とも呼ばれます。  
リエンゲージメントとリアトリビューションを指します。

<div id="cookies-http" />

#### Cookie（HTTP）

**Web Cookie**、**Internet Cookie**、**Browser Cookie**とも呼ばれます。  
閲覧中にWebサイトから送信され、ユーザーのコンピューターに保存されるデータです。Webサイトによる訪問や行動の追跡に役立ちます。 AppsFlyerは、モバイルアプリのアトリビューションにCookieを使用しません。

#### CPA

**アクション単価**  
課金モデルの一種です。マーケターは、アプリのインストールではなく、指定したユーザーアクションに対して支払います。  
 *例：*af\_purchaseイベントに対してアドネットワークに支払います。  
 *計算式：*総費用÷アクション数

#### CPC

<strong>クリック単価。Pay per Click（PPC）</strong>とも呼ばれます。  
課金モデルの一種です。マーケターは、広告のクリックごとに支払います。マーケターとパブリッシャーで、費用負担のリスクを分け合います。  
 *例：*検索エンジン、SNS、その他のパブリッシャー上でユーザーが広告を閲覧します。  
*計算式：*総費用÷クリック数

#### CPI

**インストール単価**  
課金モデルの一種です。マーケターは、広告経由で新規ユーザーがアプリをインストールするたびに支払います。マーケターとアドネットワークの間で主に使用される課金モデルです。  
*計算式：*総費用÷新規インストール数

#### CPM

<strong>1,000回表示あたりの単価。<em>Cost per Thousand（CPT）</em></strong>とも呼ばれます。  
課金モデルの一種です。マーケターは、広告インプレッション（広告の閲覧／クリック）1,000回ごとに支払います。  
 *計算式：*あらかじめ設定した1回あたりの単価×1,000

#### CPV

**視聴単価**  
課金モデルの一種です。マーケターは、パブリッシャーのプラットフォームで動画広告を配信し、ユーザーが視聴したことに対して支払います。  
 *計算式：*広告費の合計÷インプレッション数

<div id="creative" />

#### クリエイティブ

広告を構成するコンセプト、デザイン、画像などの制作物です。 マーケターは**Smart Banners**ページで、Web開発者に依頼せずに、各バナーのクリエイティブの画像、テキスト、ボタンを設定できます。<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">［関連記事］</Anchor>

#### CRM

**顧客関係管理**  
企業と既存顧客や見込み顧客との関係ややり取りを管理するための技術です。

<div id="cross-promotion-attribution" />

#### クロスプロモーションのアトリビューション

クロスプロモーションキャンペーン経由のインストールを計測・記録する方法です。特定のアプリと、自社が所有する他のアプリを使用するキャンペーンです。

#### CSM

**カスタマーサクセスマネージャー。** 担当CSMがいない、または分からない場合は、[hello@appsflyer.com](mailto:hello@appsflyer.com)にお問い合わせください。  
**アカウントマネージャー**とも呼ばれます。

<div id="csv-file" />

#### CSVファイル

**カンマ区切り形式**のファイルです。  
顧客データや注文データなどの重要な情報を、データベースにインポートしたり、エクスポートしたりするために使用します。各行が1つのデータレコードに相当し、各レコードは1つ以上のフィールドで構成されます。

#### CTA

**クリックスルーアトリビューション**  
クリックの後に発生したインストールを、特定の広告に紐付けることです。モバイル広告キャンペーンの因果関係を計測します。

#### CTI

**クリックからインストールへの転換率**  
広告の総クリック数に対する、アプリの総インストール数の割合を示す広告指標です。 <Anchor target="_blank" href="/marketers/ja/docs/about-conversion-rates#マーケティングファネルの各段階とコンバージョン率-1">［関連記事］</Anchor>  
*計算式：*インストール数÷広告クリック数

#### CTIT

**クリックからインストールまでの時間**  
時間の分布を利用し、インストールハイジャックやクリック洪水の検知に使用します。

#### CTR

**クリック率**  
見込みユーザーへの広告表示（インプレッション）に対する、その後のクリックの割合を示す広告指標です。 <Anchor target="_blank" href="/marketers/ja/docs/about-conversion-rates#マーケティングファネルの各段階とコンバージョン率-1">［関連記事］</Anchor>  
*計算式：*広告をクリックしたユーザー数÷インプレッション数（広告閲覧数）

#### CTV

**コネクテッドTV**  
スマートテレビなど、インターネット経由のコンテンツ配信を視聴するデバイスです。通常は、ダウンロードしたCTVアプリでコンテンツを視聴します。 <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">［関連記事］</Anchor>

#### CUID

**顧客ユーザーID**  
ユーザーを一意に識別するIDです。通常、ユーザーの会員登録時にアプリ所有者が生成・設定します。 CUIDにより、アプリ所有者は複数のデバイスにまたがるユーザージャーニーを把握できます。<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">［関連記事］</Anchor>

#### CV

**コンバージョン値**  
SKAdNetworkの仕組みの中でiOSアプリに設定する、ユーザーエンゲージメントを表す値です。<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">［関連記事］</Anchor>

</Accordion>

<Accordion title="D">

#### Data Locker

ローデータをAWSのバケット（専用の保存先）に配信するAppsFlyerの機能です。マーケターはAWSバケットからローデータを取得します。 <Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">［関連記事］</Anchor>

#### DAU

**日次アクティブユーザー数**  
24時間以内に特定のアプリを起動したユニークユーザー数です。

<div id="daumau-rate" />

#### DAU/MAU率

プロダクトの利用習慣の定着度を示します。たとえば、一定の間隔でプロダクトやサービスを訪れたり、利用したりするユーザーの数を表します。

<div id="deep-linking" />

#### ディープリンク

アプリストアやWebサイトではなく、アプリ内の特定のコンテンツにユーザーを誘導するリンクです。 <Anchor target="_blank" href="/marketers/ja/docs/deep-linking-using-onelink">［関連記事］</Anchor>

<div id="deferred-deep-linking" />

#### 遅延ディープリンク

まずユーザーをアプリストアやWebサイトに誘導し、アプリをダウンロード・インストールしてもらいます。その後、リンクのアトリビューションデータを使用して、アプリ内の特定のコンテンツに誘導します。 <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">［関連記事］</Anchor>

<div id="deprecation-notice" />

#### 廃止予定の通知

指定日（提供終了日）以降、特定バージョンの機能の全部または一部や、関連するサポートを利用できなくなることを知らせる通知です。

<div id="dev-key" />

#### Devキー

SDKの設定、メッセージの暗号化、顧客アカウントやAPI呼び出し元プログラムの認証に使用する、一意の識別子および認証トークンです。 通常、同じアカウント内のアプリには同じDevキーが使用されます。

<div id="device-id" />

#### デバイスID

ユーザーがリセットできるIDFA、GAID、OAIDや、リセットできないIMEI、SSAIDなど、デバイスを一意に識別するIDです。 AppsFlyerは、デバイス単位のアトリビューションにこのIDを使用する場合があります。

<div id="direct-publisher" />

#### 直接契約のパブリッシャー

自社アプリで他のアプリを宣伝するアプリ所有者です。アドネットワークを介さずに広告を配信します。

#### DMA

**指定市場地域**。**メディア市場**とも呼ばれます。  
視聴者数の計測に使用する、人口規模で順位付けされた地理的な区分です。同じDMA内では、同じ地域のテレビ局、ラジオ局、新聞、オンラインコンテンツを利用します。

<div id="domain" />

#### ドメイン

Webサイトを訪れる際に、ブラウザに入力するWebサイトのアドレスです。例：yourwebsite.com。

#### DSP

**デマンドサイドプラットフォーム**  
デジタル広告の購入者が、複数のアドエクスチェンジやデータエクスチェンジのアカウントを1つのプラットフォームで管理するために使用します。

<div id="dual-consent" />

#### デュアル同意

iOS 14.5以降のデバイスのユーザーが、広告主アプリとパブリッシャーアプリの両方でATTに同意している状態です。

</Accordion>

<Accordion title="E">

<div id="earned" />

#### アーンドメディア

メディアソースの一種です。直接流入や検索エンジン経由でユーザーを獲得します。

#### eCPA

**実効アクション単価**  
インプレッションやクリックではなく、指定したユーザーアクションに対して支払ったと仮定した場合のCPAを示します。 [CPA](/docs/appsflyer-knowledge-base-glossary#cpa)を参照してください。  
*計算式：*総費用÷有効なアクション数＝eCPA（AppsFlyerによる分析値）

#### eCPC

**実効クリック単価**  
インプレッションやコンバージョンではなく、クリックに対して支払ったと仮定した場合のCPCを示します。 [CPC](/docs/appsflyer-knowledge-base-glossary#cpc)を参照してください。  
*計算式：*総費用÷クリック数＝eCPC（AppsFlyerによる分析値）

#### eCPI

**実効インストール単価**  
新規ユーザーがアプリを利用するまでにかかる費用を示します。優れたアプリでは、口コミなどによる自然拡散でオーガニックインストールが増えるため、CPIとは異なる値になります。 [CPI](/docs/appsflyer-knowledge-base-glossary#cpi)を参照してください。  
*計算式：*総費用÷有効なインストール数＝eCPI（AppsFlyerによる分析値）

#### eCPM

**1,000回表示あたりの実効単価**  
定義上、キャンペーンのCPMはeCPMと同じ値になります。 [CPM](/docs/appsflyer-knowledge-base-glossary#cpm)を参照してください。  
*計算式：*総費用÷総インプレッション数（1,000回単位）＝eCPM（AppsFlyerによる分析値）

<div id="engagement" />

#### エンゲージメント

ユーザーの広告接触です。  
 *例：*インプレッションやクリック

#### eRPA

**アクションあたりの実効収益**  
アクションには、アプリ起動や特定のアプリ内イベントの実行などが含まれます。 <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution">［関連記事］</Anchor>。  
 *計算式：*総収益÷対象イベントの発生回数＝eRPA（AppsFlyerによる分析値）

#### ESP

**メール配信サービスプロバイダー**  
メールマーケティングやメール一斉配信のサービスを提供する企業です。 <Anchor target="_blank" href="/marketers/ja/docs/email-service-provider-esp-integration-guide">［関連記事］</Anchor>

<div id="event" />

#### イベント

**アプリ内イベント**とも呼ばれます。  
ユーザーがアプリ内で実行する任意のアクションです。 SDKまたはサーバー間APIを通じて、AppsFlyerに報告されます。  
 *例：*サインイン、ゲームのレベルクリア、購入など。

<div id="event-counter" />

#### イベント数

実行されたアプリ内イベントの合計数です。

<div id="event-cvr" />

#### イベントCVR

**イベントコンバージョン率**  
目的のアクションを完了したユーザーの割合です。広告によってコンバージョンに至ったユーザーの数を示します。  
 *計算式：*イベントのユニーク実行数÷アトリビューション数

<div id="event-time" />

#### イベント時刻

アプリ内イベントの記録日時です。

</Accordion>

<Accordion title="F">

<div id="fraud" />

#### 不正

広告不正とは、マーケター、パブリッシャー、広告供給側のパートナーを欺き、アトリビューションに基づく報酬を不正に得ようとする行為です。  
 *例：*インプレッション、クリック、コンバージョンやデータイベントを偽装し、広告予算を不正に取得する行為。  
 *手法：*クリックスパム、クリックインジェクション、SDKスプーフィング。  

*参考情報：*<Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide#よくある質問とヒント">［関連記事］</Anchor>、<Anchor target="_blank" href="https://www.appsflyer.com/mobile-attribution-glossary">［AppsFlyerのモバイル広告不正用語集］</Anchor>

</Accordion>

<Accordion title="G">

#### GAID

**Google広告ID**  
Google PlayのAndroidユーザー向けの、ユーザーがリセット可能な一意の識別子です。 マーケターはこの識別子を使用してデータを記録し、ユーザーに合わせた広告を配信します。

#### GCD

**コンバージョンデータの取得**  
インストール時にアトリビューションデータをSDKに取得する、SDKメソッドの総称です。

<div id="geo" />

#### 国・地域

**国**とも呼ばれます。  
*例：*Overview dashboardでGEOフィルターを使用し、国別のデータを確認します。

</Accordion>

<Accordion title="I">

<div id="id-matching" />

#### IDマッチング

一意のデバイス識別子を使用するアトリビューション方法です。計測リンクから取得した識別子を、AppsFlyer SDKが取得した識別子と照合します。   
*識別子：*IDFA、GAID、OAID、Android ID、IMEI

#### IDFA

**広告主向け識別子**  
AppleのiOSユーザー向けの、ユーザーがリセット可能な一意の識別子です。マーケターはこの識別子を使用してデータを記録し、ユーザーに合わせた広告を配信します。 <Anchor target="_blank" href="/marketers/ja/docs/preparing-for-the-app-store-review-nutrition-labels">［関連記事］</Anchor>

#### IDFV

**ベンダー向け識別子**  
同一のiOSデバイス上で、同じ開発者のすべてのアプリが共有する一意の識別子です。

#### IMEI

**国際移動体装置識別番号**  
リセットできない一意のモバイルデバイス識別子です。 Android 10より前のバージョンでは、GAIDを利用できない場合、IMEIをアトリビューションに使用できます。 <Anchor target="_blank" href="https://developer.android.com/about/versions/10/privacy/changes">Android 10のプライバシーに関する変更</Anchor>

<div id="impression" />

#### インプレッション

アプリユーザーやWebサイト訪問者に広告が表示されることです。インプレッションの定義は、アドネットワークによって異なる場合があります。 <Anchor target="_blank" href="/marketers/ja/docs/about-conversion-rates#マーケティングファネルの各段階とコンバージョン率-1">［関連記事］</Anchor>

<div id="in-app-events" />

#### アプリ内イベント

アプリのインストール後にユーザーが実行する、任意のアクションです。[イベント](/docs/appsflyer-knowledge-base-glossary#イベント)を参照してください。  
 *例：*ログイン、チュートリアルの完了、購入など。

<div id="install" />

#### インストール

AppsFlyerでは、ユーザーがモバイルアプリをダウンロードしてインストールし、起動した時点でインストールを記録します。

<div id="install-hijacking" />

#### インストールハイジャック

**クリックインジェクション**、**リファラハイジャック**、**クリックハイジャック**とも呼ばれます。  
モバイルマルウェアを使い、実際のアプリインストールを自分の成果として不正に計測させるモバイル広告不正の一種です。

<div id="install-referrer" />

#### インストールリファラ

*Google Play*のリファラパラメータを使用するアトリビューション方法です。 <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#install-referrer-android-only">［関連記事］</Anchor>

<div id="integrated-partner" />

#### 連携済みパートナー

AppsFlyerと連携している、アドネットワーク、代理店、マーケティングツールです。 <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">［関連記事］</Anchor>

<div id="integrated-partner-types" />

#### 連携済みパートナーの種類

アドネットワーク、アフィリエイトネットワーク、リターゲティングネットワーク、代理店、分析プラットフォーム、直接契約のパブリッシャー、プログラマティック広告、マーケティングオートメーション、TV、不正検知、Metaのキャンペーン管理パートナー、Google Marketing Platformなどがあります。 <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#partner-types-in-the-ecosystem">［関連記事］</Anchor>

</Accordion>

<Accordion title="K">

キーワード

オンライン広告で使用する語句です。マーケターは、ユーザーが指定した語句でインターネット検索を行った際に広告を表示するため、費用を支払います。 AppsFlyerでは、Google広告、Apple Ads、オーガニック検索のキーワードデータを確認できます。 ［関連記事］

KPI

**重要業績評価指標**  
広告指標とKPIは、ターゲットオーディエンスへの施策の効果を評価するために使用します。  
 *例：*ビュースルーコンバージョン率、クリック数など。

</Accordion>

<Accordion title="L">

<div id="landing-page" />

#### ランディングページ

ユーザーが広告をクリックした後、最初に表示されるページです。

<div id="last-click-attributions" />

#### ラストクリックアトリビューション

Web分析のモデルです。売上やコンバージョンを「最後のクリック」の成果として計測します。

#### LAT

**広告トラッキングの制限**  
ユーザーの広告用デバイスIDへのアクセスを防ぐ、iOSの機能です（iOS 14まで）。有効な場合、AppsFlyerはデバイスIDを受信せず、ユーザーにはターゲティング広告が表示されません。［関連記事］

<div id="link-management" />

#### リンク管理

すべてのリンクを整理、編集、分析し、包括的に管理できる機能です。 ［関連記事］

<div id="localization" />

#### ローカライズ

アトリビューションとレポートを、特定のタイムゾーンに合わせる処理です。デフォルトでは、AppsFlyerはすべてのアプリデータをUTC（GMT）でレポートします。

<div id="lookback-window" />

#### ルックバック期間

広告接触後に発生したインストールを、その広告の成果として計測できる最長の期間です。 <Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">［関連記事］</Anchor>

<div id="loyal-user" />

#### ロイヤルユーザー

ユーザーエンゲージメントを表すKPIです。デフォルトでは、インストールしたアプリを初めて起動した後、さらに3回以上起動したユーザーを指します。 マーケターは**アプリ設定**ページで、ロイヤルユーザーの判定に使用するアプリ内イベントを選択できます。 <Anchor target="_blank" href="/marketers/ja/docs/about-a-loyal-user">［関連記事］</Anchor>

#### LTV

<strong>顧客生涯価値。Customer Lifetime Value（CLTV）</strong>とも呼ばれます。  
ユーザーがアプリを利用する期間全体での価値を示す、重要なKPIです。 <Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">［関連記事］</Anchor>

</Accordion>

<Accordion title="M">

<div id="macros" />

#### マクロ

パートナーが計測リンクやポストバックで使用するパラメータです。ポストバックに設定したマクロは、ユーザーに関連するデータに自動で置き換えられます。<Anchor target="_blank" href="/partners/ja/docs/postback-macros-for-ad-networks#アプリ内イベント専用マクロ">［関連記事］</Anchor>

<div id="marketer" />

#### マーケター

関連用語：**広告主**、**アプリ所有者**。  
アプリ所有者のもとでAppsFlyerを使用し、コンバージョンを増やすために、さまざまなチャネルでマーケティングキャンペーンを運用する担当者です。

<div id="marketing-automation" />

#### マーケティングオートメーション

モバイル向けのメール、プッシュ通知、アプリ内メッセージのキャンペーンを実行するプラットフォームなどが含まれます。連携後、AppsFlyerはこれらのキャンペーンのアトリビューションデータを提供します。

#### Master API

集計データAPIで、任意のグループ分けとKPIを指定したカスタムレポートを作成できます。 <Anchor target="_blank" href="/marketers/ja/docs/master-api-user-acquisition-metrics-via-api">［関連記事］</Anchor>

#### MAU

**月次アクティブユーザー数**  
30日間に特定のアプリを起動したユニークユーザー数です。同じユーザーは1回だけ数えます。 <Anchor target="_blank" href="/marketers/ja/docs/activity-dashboard#metric-definitions">［関連記事］</Anchor>

<div id="media-source" />

#### メディアソース

ユーザーと広告との接点を提供する媒体です。 <Anchor target="_blank" href="/marketers/ja/docs/about-media-source-types">［関連記事］</Anchor>  
*メディアソースの種類：*Self-Reporting Network（SRN）、非SRN、オウンドメディア

<div id="mediation-platform" />

#### メディエーションプラットフォーム

1つのSDK実装で複数のアドネットワークへの接続を集約するプラットフォームです。最適化アルゴリズムを使用して、アプリ開発者の広告枠に最も高いCPMで広告を配信できるアドネットワークを選びます。

<div id="meta-campaign-management-partners" />

#### Metaのキャンペーン管理 パートナー

Meta広告を専門に扱い、Metaが定めた基準を満たすマーケティングパートナーです。特定の技術を提供するパートナーと、広告買い付けを行うパートナーの2種類があります。  
 *例：*マーケターがMeta広告のキャンペーンを自動最適化できるようにするパートナー。 Metaのキャンペーン管理パートナーは、AppsFlyerと連携して、リアルタイムでポストバックを受信できます。

#### MCP

**Model Context Protocol**  
アプリケーションがLLMにコンテキストを提供する方法を標準化する、オープンなプロトコルです。 MCPは、LLMが外部システムにアクセスし、やり取りするための軽量な「橋渡し」の役割を担います。

#### MMP

**Mobile Measurement Partner**  
<Anchor target="_blank" href="https://www.appsflyer.com/glossary/mmp/">モバイル計測パートナー</Anchor>（MMP）とは、広告・マーケティングのチャネル、メディアソース、アドネットワークを横断して、アプリのキャンペーン成果の計測を支援する企業です。  
 *例：*AppsFlyer

<div id="mobile-app" />

#### モバイルアプリ

スマートフォンやタブレットなどのモバイルデバイス向けに設計されたソフトウェアです。

<div id="monetization-network" />

#### 収益化ネットワーク

収益化ネットワーク（アドネットワークとも呼ばれる）は、アプリ開発者（パブリッシャー）と広告主をつなぎます。アプリ開発者は、ユーザーに広告を表示してアプリを収益化するために利用し、広告主は、自社の商品を宣伝するために利用します。

<div id="multi-platform" />

#### 複数プラットフォーム対応

複数のプラットフォームで使用できるソリューションです。  
*例：*AppsFlyerのOneLinkは、AndroidとiOSの両方のデバイスでインストールやイベントを記録できる計測リンクです。

<div id="multi-touch-attribution" />

#### マルチタッチアトリビューション

メディアソースやキャンペーンが最後の広告接触ではないものの、インストール前かつアトリビューションの対象期間内にユーザーと接触したインストールです。

</Accordion>

<Accordion title="N">

<div id="native-ad" />

#### ネイティブ広告

掲載先のプラットフォームの形式や機能になじむ広告です。  
*例：*Webサイトの通常の記事と同じように表示される、スポンサー付きのニュース記事。

<div id="native-app" />

#### ネイティブアプリ

iOSやAndroidなど、特定のプラットフォーム向けに開発されたアプリです。

#### NOI

**ノンオーガニックインストール**  
AppsFlyerが、有料広告やオウンドメディアのマーケティング施策に紐付けて計測するモバイルアプリのインストールです。 <Anchor target="_blank" href="/marketers/ja/docs/about-organic-and-non-organic-installs">［関連記事］</Anchor>  
*例：*有料広告キャンペーン、オウンドメディアのメールキャンペーン

</Accordion>

<Accordion title="O">

#### OAID

**Open Advertiser Identifier**  
Google Play以外の一部のAndroidマーケットで使用する、ユーザーがリセット可能な一意の識別子です。IDFAやGAIDに相当します。 <Anchor target="_blank" href="/marketers/ja/docs/android-oaid-implementation-in-the-sdk">［関連記事］</Anchor>

#### OneLink™

AppsFlyer独自の、複数プラットフォーム向け計測リンクです。 1つのリンクで、見込みユーザーを適切なストアへリダイレクトしたり、既存のアプリユーザーをディープリンクで誘導したりできます。 <Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">［関連記事］</Anchor>

#### OneLink™ ID

OneLinkテンプレートに対して自動生成される一意の識別子です。 OneLink APIの使用時に必要です。 <Anchor target="_blank" href="/marketers/ja/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">［関連記事］</Anchor>

<div id="onelink-template" />

#### OneLink™テンプレート

デバイスの種類ごとに、すべての移動先を定義するテンプレートです。基本設定の完了後は、パラメータの異なるカスタムリンクを多数作成できます。各リンクは、OneLinkテンプレートで定めた移動先にユーザーを誘導します。

<div id="organic-install" />

#### オーガニックインストール

マーケターによる直接的な施策を介さずに発生した、モバイルアプリのインストールです。 AppsFlyerに広告接触の記録がないため、特定のメディアソースに紐付けることができません。 <Anchor target="_blank" href="/marketers/ja/docs/about-organic-and-non-organic-installs">［関連記事］</Anchor>

#### OTT

**Over-the-top**  
ケーブルテレビ、地上波放送、衛星放送などのプラットフォームを介さず、インターネット経由で配信するコンテンツです。 <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">［関連記事］</Anchor>

<div id="owned-media" />

#### オウンドメディア

アプリ所有者が所有・管理するメディアソースの種類です。 <Anchor target="_blank" href="/marketers/ja/docs/owned-media-attribution">［関連記事］</Anchor>  
*例：*メール、SMS、Webサイト、SNS、プッシュ通知、アプリ内通知など。

</Accordion>

<Accordion title="P">

<div id="package-id" />

#### パッケージID

[アプリID（Android・iOS）](#a)とも呼ばれます。  
ストアのアプリページのURLに表示される一意の識別子です。 形式は、対象のOSによって異なります。

<div id="paid" />

#### ペイドメディア

報酬を受け取り、Webサイトを宣伝するメディアソースの種類です。 認知、関心、行動を促すのに効果的です。   
*例：*検索広告、GoogleやYahoo!などのポータルサイトのバナー、オンラインニュース媒体のリッチメディア広告、Meta広告やSnapchatなどのSNSのネイティブ広告。

#### PBA

**People-based attribution**  
プラットフォーム、デバイス、マーケティングチャネルを横断した、ユーザー獲得とコンバージョンの流れの全体像を把握できるAppsFlyerのプレミアム機能です。特定の指標に注目したり、所在地、デバイスの種類、メディアソース、キャンペーンなどでデータを絞り込んだり、グループ化したりするために使用します。 <Anchor target="_blank" href="/marketers/ja/docs/people-based-attribution-pba-overview">［関連記事］</Anchor>

#### PID

**パートナーID**  
AppsFlyerで使用する、パートナーやメディアソースを一意に識別するIDです。

<div id="postback" />

#### ポストバック

AppsFlyerを介して、広告主からパートナー（アドネットワーク）に送信する、インストールやアプリ内イベントの通知です。パートナーがキャンペーンを最適化するのに役立ちます。

#### PPC

**クリック課金**  
主に大手検索エンジンで採用される広告モデルです。マーケターは、広告がクリックされた際にパブリッシャーへ支払います。 

<div id="probabilistic-modeling" />

#### 確率論的モデリング

オウンドメディア向けの統計的なアトリビューション方法で、機械学習を利用してキャンペーンの成果を推定します。

<div id="programmatic-advertising" />

#### プログラマティック広告

アドネットワークがさまざまなプラットフォームに接続し、仲介業者を介さずに広告枠を購入する仕組みです。

#### Protect360

自動かつ包括的な不正対策を提供する、AppsFlyerのプレミアム機能です。 <Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide">［関連記事］</Anchor>

<div id="publisher" />

#### パブリッシャー

AppsFlyerでは、アドネットワークやマーケターに広告枠を販売するメディアソース、Webサイト、アプリを指します。

#### Pull API

AppsFlyerから集計データやローデータを取得する、URLベースのAPIです。 <Anchor target="_blank" href="/marketers/ja/docs/pull-api-aggregate-data">［関連記事］</Anchor>

#### Push API

リアルタイムのアトリビューションデータを、マーケターのサーバー側のエンドポイントに配信します。<Anchor target="_blank" href="/marketers/ja/docs/push-api-streaming-raw-data">［関連記事］</Anchor>

</Accordion>

<Accordion title="Q">

<div id="qr-code" />

#### QRコード

読み取ってリンクに変換できる、2次元バーコードです。

</Accordion>

<Accordion title="R">

<div id="raw-data" />

#### ローデータ

インストール、購入、Webサイト訪問、パートナーへのポストバックなど、個々のイベントを記録した、AppsFlyerが提供するユーザーレベルのデータです。 <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">［関連記事］</Anchor>

<div id="re-attribution" />

#### リアトリビューション

過去のアプリユーザーが、同じアプリのリターゲティングキャンペーンに接触した後、アプリを再インストールすることです。 <Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">［関連記事］</Anchor>

<div id="re-attribution-window" />

#### リアトリビューション期間

インストール後、再インストールを新規インストールとして扱わない期間です。 <Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">［関連記事］</Anchor>

<div id="re-engagement" />

#### リエンゲージメント

アプリユーザーが、そのアプリのリターゲティングキャンペーンに接触した後、アプリを起動することです。 <Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">［関連記事］</Anchor>

<div id="registered-device" />

#### 登録済みデバイス

テストに使用するデバイスです。登録済みデバイスでは、AppsFlyerのリアトリビューションのルールにかかわらず、すべてのインストールが計測されます。<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">［関連記事］</Anchor>

<div id="request" />

#### リクエスト

[API呼び出し](#a)とも呼ばれます。

<div id="retargeting" />

#### リターゲティング

広告キャンペーンを通じて、現在または過去のユーザーにアプローチすることです。

<div id="retargeting-network" />

#### リターゲティングネットワーク

現在または過去のユーザーへのターゲティングを専門とするアドネットワークです。 <Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#retargeting-dashboard">［関連記事］</Anchor>

<div id="retention-report" />

#### リテンションレポート

アプリ内のユーザーセッションの状況を計測する、AppsFlyerの製品です。 ［関連記事］

<div id="revenue" />

#### 収益

アプリ内イベントや広告表示（広告収益）で報告される収益です。

<div id="revenue-attribution" />

#### 収益のアトリビューション

特定の収益イベントを、特定のキャンペーンやメディアソースに紐付けることです。 <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution">［関連記事］</Anchor>

<div id="revenue-event" />

#### 収益イベント

収益値を含めて記録されたアプリ内イベントです。   
*パラメータ：*ユーザーの収益を累積するパラメータは、af\_revenueのみです。ビジネスロジック上、実際の収益の発生を表すアプリ内イベントには、必ずこのパラメータを使用してください。

<div id="rich-media-ad" />

#### リッチメディア広告

視聴者がコンテンツを操作し、参加するよう促す高度な機能を備えた広告です。広告にユーザーを引き込む、さまざまな方法を提供します。  
 *例：*動画広告、プレイアブル広告

#### ROAS

**広告費用対効果**  
広告費1単位あたりに生まれた収益を算出して、キャンペーンの成果を計測する指標です。  
 *計算式：*収益÷広告費

#### ROI

**投資利益率**AppsFlyerのOverview dashboardと集計レポートで確認できる指標です。  
 *計算式：*（収益－コスト）÷コスト×100<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">［関連記事］</Anchor>

</Accordion>

<Accordion title="S">

#### SAN

**<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">Self-attributing Network</Anchor>。SRN**とも呼ばれます。  
大手パブリッシャーが運営し、自社のトラフィックについて、インストールやアプリ内イベントのアトリビューションを独自に計算するプラットフォームです。第三者のアトリビューション事業者の判定結果は使用しません。  
*例：*Meta広告、Google広告、X広告。 <Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">［一覧を確認］</Anchor>

#### SDK

**ソフトウェア開発キット**  
アトリビューションと分析のためにアプリに組み込むコードです。 <Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-planning">［関連記事］</Anchor>

<div id="segmentation" />

#### セグメンテーション

条件に基づいてユーザーを小さなグループに分け、それぞれに合わせた広告を提供するマーケティング手法です。

<div id="session" />

#### セッション

アプリが起動されることを前提とします。セッション数は、SDKの起動や、アプリ所有者が定めたロジックに基づいて集計します。  
 *例：*ウイルス対策アプリでは、1日の利用を1セッションと数えます。 <Anchor target="_blank" href="/marketers/ja/docs/measure-sessions">［関連記事］</Anchor>

<div id="single-platform" />

#### 単一プラットフォーム向け

AndroidやiOSなど、1つのプラットフォームのアトリビューションに使用する計測リンクです。  （複数プラットフォーム向けの計測リンクもあります。）

<div id="single-source-of-truth-ssot" />

#### Single source of truth（SSOT）

複数のデータソースから取得したiOSアトリビューションデータを統合し、アプリの成果を正確かつ包括的に把握できるAppsFlyerの仕組みです。

#### SKAdNetwork

AppleのiOSの一部であるSKAdNetworkの仕組みは、ユーザーのプライバシーを守りながらキャンペーンの成果を計測するために役立ちます。 <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">［関連記事］</Anchor>

#### SKAN

SKAdNetworkの略称です。

<div id="slug" />

#### スラッグ

[アプリID（Android・iOS）](#a)とも呼ばれます。

#### Smart Banner

モバイルWebサイトの訪問者によるアプリインストールのアトリビューションと、その質を計測できるAppsFlyerの機能です。<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">［関連記事］</Anchor>

#### SRN

**<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">Self-Reporting Network</Anchor>。SAN**とも呼ばれます。  
大手パブリッシャーが運営し、自社のトラフィックについて、インストールやアプリ内イベントのアトリビューションを独自に計算するプラットフォームです。第三者のアトリビューション事業者の判定結果は使用しません。  
 *例：*Meta広告、Google広告、X広告。 <Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">［一覧を確認］</Anchor>

#### SSP

**サプライサイドプラットフォーム**  
パブリッシャーが広告枠から得る収益を最大化するための仕組みです。広告枠の販売を自動かつ効率的に管理することで、収益の最大化を図ります。

<div id="subdomain" />

#### サブドメイン

Webサイト内の各領域を整理し、アクセスできるようにするため、メインドメイン名に追加する部分です。 1つのメインドメインに、複数のサブドメインを設定できます。例：app.yourwebsite.com

<div id="sunset-date" />

#### 提供終了日

非推奨となった特定の機能やバージョンの全部または一部が停止し、すべてのサポートが終了する日です。

</Accordion>

<Accordion title="T">

<div id="targeting" />

#### ターゲティング

特定の[オーディエンス](#a)を対象にマーケティングキャンペーンを行うことです。  
 *条件：*所在地、人口統計情報、携帯通信事業者など。

<div id="account-user" />

#### アカウントユーザー

AppsFlyerアカウントのログイン情報を持つユーザーです。管理者からアクセス権を付与されます。 ［関連記事］

<div id="touch-time" />

#### 広告接触日時

ユーザーの広告接触（クリックまたはインプレッション）が記録された日時（タイムスタンプ）です。

<div id="touch-type" />

#### 広告接触の種類

ユーザーが広告に接触した方法で、クリックまたはインプレッションを指します。

<div id="touchpoint" />

#### タッチポイント

コンバージョン（インストールや購入）に至るまでの、ユーザーとの接点です。  
*例：*クリック、インプレッション、Webサイト訪問

</Accordion>

<Accordion title="U">

#### UDID

**一意のデバイス識別子**  
個々のiOSデバイスを識別する一意のIDです。ユーザーがiCloudや設定アプリでデバイスを有効化しようとした際に、Appleのサーバーから取得されます。

<div id="uninstall-measurement" />

#### アンインストール計測

デバイスからアプリを削除したユーザーを、計測元のメディアソース別に計測することです。 <Anchor target="_blank" href="/marketers/ja/docs/measure-uninstalls">［関連記事］</Anchor>

<div id="unique-user" />

#### ユニークユーザー

ユニークユーザーの判定には、AppsFlyer IDを使用します。

<div id="universal-links" />

#### ユニバーサルリンク

ユニバーサルリンクは、Webブラウザを一度開く手順を挟まず、リンク先のコンテンツを直接表示することで、スムーズなユーザー体験を提供します。  
 ユニバーサルリンクは、WebサーバーでホストするApple App Site Association（AASA）ファイルを使用して、iOS上で動作します。 AASAファイルには、Webドメインとアプリを関連付ける情報が含まれ、そのドメインのリンクからアプリ内コンテンツをスムーズに開けるようになります。

<div id="user" />

#### ユーザー

モバイルデバイスを使用して、アプリをダウンロード、インストール、起動する人です。

<div id="user-acquisition" />

#### ユーザー獲得

新規ユーザーの獲得を目的とする広告キャンペーンです。

<div id="user-agent" />

#### ユーザーエージェント

ブラウザの種類、OS、ソフトウェアのバージョンなど、ユーザーのデバイスに関する技術情報です。 AppsFlyerは、この情報を確率論的モデリングによるアトリビューションに使用します。

<div id="user-invite-attribution" />

#### ユーザー招待のアトリビューション

同じアプリの既存ユーザーから招待を受け、アプリをインストールした新規ユーザーのアトリビューションと分析です。 <Anchor target="_blank" href="/marketers/ja/docs/user-invite-attribution">［関連記事］</Anchor>

</Accordion>

<Accordion title="V">

<div id="validation-rules" />

#### 検証ルール

ターゲティング条件の検証や独自の不正検知のためのルールです。条件に合わないインストールのアトリビューションを、アプリ所有者がブロックできます。 <Anchor target="_blank" href="/marketers/ja/docs/implement-validation-rules-to-prevent-fraud">［関連記事］</Anchor>

<div id="verticals" />

#### 業種

**Industries**とも呼ばれます。  
特定のニーズを持ち、特化したサービスへの関心が高い市場区分です。 AppsFlyerでは、マーケターの業種に応じたアプリ内イベントの報告を推奨しています。<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#recommended-events-by-business-vertical">［関連記事］</Anchor>  
*例：*ゲーム、Eコマース、旅行

<div id="video-ad" />

#### 動画広告

インターネット上での動画再生の前、途中、終了後に表示される広告です。  
 *例：*動画を埋め込んだバナー広告やインタースティシャル広告。

<div id="visitor-website" />

#### 訪問者（Webサイト）

一定期間内にWebサイトを閲覧した人です。その期間内に、同じWebサイトの異なるページを含めて複数回訪れても、1回の訪問として数えます。

#### VTA

**ビュースルーアトリビューション**  
インストールやアクションを、広告のインプレッションに紐付けることです。バナー、動画、インタースティシャル広告の閲覧が、コンバージョンにつながったことを把握するのに役立ちます。 <Anchor target="_blank" href="/marketers/ja/docs/measure-view-through-engagements">［関連記事］</Anchor>

</Accordion>

<Accordion title="W">

<div id="web-app" />

#### Webアプリ

Webブラウザ上で動作するアプリです。（ネイティブアプリは、特定のOSプラットフォーム上で動作します。）

</Accordion>

<Accordion title="X">

<div id="x-marketing-partners" />

#### Xのマーケティングパートナー

X広告からのトラフィック獲得を専門とする、AppsFlyerの連携済みパートナーです。 ［関連記事］

</Accordion>

<div data-zendesk-anchors="account-owner=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E6%89%80%E6%9C%89%E8%80%85 h_01HEN8SDX13CRX1MY8QCX8BX6W=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E6%89%80%E6%9C%89%E8%80%85 ad=%E5%BA%83%E5%91%8A h_01HEN8SDX1S487D5W08WDYXRKV=%E5%BA%83%E5%91%8A ad-cost=%E5%BA%83%E5%91%8A%E3%82%B3%E3%82%B9%E3%83%88 h_01HEN8SDX2ZPWN1RZW9NNAV96E=%E5%BA%83%E5%91%8A%E3%82%B3%E3%82%B9%E3%83%88 ad-group=%E5%BA%83%E5%91%8A%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%97 h_01HEN8SDX29BHHZ9GYRY9PEV8S=%E5%BA%83%E5%91%8A%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%97 ad-hierarchy=%E5%BA%83%E5%91%8A%E3%81%AE%E9%9A%8E%E5%B1%A4 h_01HEN8SDX2B51PP9Y0M91YATSG=%E5%BA%83%E5%91%8A%E3%81%AE%E9%9A%8E%E5%B1%A4 ad-network=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF h_01HEN8SDX2JKZ1QC4W4355G7F5=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF ad-revenue=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A h_01HEN8SDX2Q1JGRS23WVS8ACX4=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A ad-set=%E5%BA%83%E5%91%8A%E3%82%BB%E3%83%83%E3%83%88 h_01HEN8SDX2K782M8N8XFYDEJWT=%E5%BA%83%E5%91%8A%E3%82%BB%E3%83%83%E3%83%88 ad-spend=%E5%BA%83%E5%91%8A%E8%B2%BB h_01HEN8SDX2XF6S4RTPWQM0BV7D=%E5%BA%83%E5%91%8A%E8%B2%BB ad-types=%E5%BA%83%E5%91%8A%E3%82%BF%E3%82%A4%E3%83%97 h_01HEN8SDX29QWRFAHJEM79H66E=%E5%BA%83%E5%91%8A%E3%82%BF%E3%82%A4%E3%83%97 adnetwork-integration=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E9%80%A3%E6%90%BA h_01HEN8SDX2CT683CHFSSC50PWS=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E9%80%A3%E6%90%BA admin=%E7%AE%A1%E7%90%86%E8%80%85 h_01HEN8SDX20AFPW4XB8W5E13PS=%E7%AE%A1%E7%90%86%E8%80%85 h_01HEN8SDX2E8V28683JDKCRQ0Y=advanced-privacy advertiser=%E5%BA%83%E5%91%8A%E4%B8%BB h_01HEN8SDX2CS48EFE03K8S24YP=%E5%BA%83%E5%91%8A%E4%B8%BB advertising-id=%E5%BA%83%E5%91%8Aid h_01HEN8SDX2YADZ9DQYJQWVNAR6=%E5%BA%83%E5%91%8Aid h_01HEN8SDX2FSAK73W7WMR9Y1B1=adwords affiliate-networks=%E3%82%A2%E3%83%95%E3%82%A3%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%88%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF h_01HEN8SDX23X5GP45FVAYYXF8K=%E3%82%A2%E3%83%95%E3%82%A3%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%88%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF agency=%E4%BB%A3%E7%90%86%E5%BA%97 h_01HEN8SDX2GG35YXPMQECFC9MP=%E4%BB%A3%E7%90%86%E5%BA%97 aggregate-data=%E9%9B%86%E8%A8%88%E3%83%87%E3%83%BC%E3%82%BF h_01HEN8SDX2GS79MYAB2CTPZDRF=%E9%9B%86%E8%A8%88%E3%83%87%E3%83%BC%E3%82%BF aggregated-advancedprivacy=aggregated-advanced-privacy h_01HEN8SDX228V0T803NT78YTAF=aggregated-advanced-privacy allinstalls-network=%E3%81%99%E3%81%B9%E3%81%A6%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%82%92%E5%8F%97%E4%BF%A1%E3%81%99%E3%82%8B%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF h_01HEN8SDX269P5Z09NQ2QFWDAA=%E3%81%99%E3%81%B9%E3%81%A6%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%82%92%E5%8F%97%E4%BF%A1%E3%81%99%E3%82%8B%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF alllaunches-network=%E3%81%99%E3%81%B9%E3%81%A6%E3%81%AE%E8%B5%B7%E5%8B%95%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%82%92%E5%8F%97%E4%BF%A1%E3%81%99%E3%82%8B%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF h_01HEN8SDX2MBW9XXKHTSXYH9C3=%E3%81%99%E3%81%B9%E3%81%A6%E3%81%AE%E8%B5%B7%E5%8B%95%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%82%92%E5%8F%97%E4%BF%A1%E3%81%99%E3%82%8B%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF analytics-platform=%E5%88%86%E6%9E%90%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0 h_01HEN8SDX2QXNQEBPGX9XPJGPG=%E5%88%86%E6%9E%90%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0 h_01HEN8SDX2R9KGKX3F89WHEJGB=android-app-link h_01HEN8SDX202FR3ZGWTS7P8XKW=android-id h_01HEN8SDX253ZCWFE2YPD338SH=api api-call=api%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97 h_01HEN8SDX26FQJP40XTPX6K7CQ=api%E5%91%BC%E3%81%B3%E5%87%BA%E3%81%97 app-id-android-ios=%E3%82%A2%E3%83%97%E3%83%AAidandroidios h_01HEN8SDX20Q00W2EJ97ANXBZ9=%E3%82%A2%E3%83%97%E3%83%AAidandroidios app-launch=%E3%82%A2%E3%83%97%E3%83%AA%E8%B5%B7%E5%8B%95 h_01HEN8SDX22FS72WKQB9VCA149=%E3%82%A2%E3%83%97%E3%83%AA%E8%B5%B7%E5%8B%95 app-owner=%E3%82%A2%E3%83%97%E3%83%AA%E6%89%80%E6%9C%89%E8%80%85 h_01HEN8SDX26NBVDQTG6DTBK34H=%E3%82%A2%E3%83%97%E3%83%AA%E6%89%80%E6%9C%89%E8%80%85 appstore-analytics=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B9%E3%83%88%E3%82%A2%E3%81%AE%E5%88%86%E6%9E%90 h_01HEN8SDX2J6XHCR2VW4GTXA86=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B9%E3%83%88%E3%82%A2%E3%81%AE%E5%88%86%E6%9E%90 h_01HEN8SDX2RNJMDD8Y0HPTS60N=appsflyer h_01HEN8SDX2PJM4DWMX5FK9EXEA=appsflyer-id h_01HEN8SDX2HARPH83FDJ8RBCNN=arpdau h_01HEN8SDX2V2D5HTGXKHEVN9ZH=arpu h_01HEN8SDX20PZNYV7VQ68AX7AK=arppu h_01HEN8SDX3VSGWREJFF29DSQSC=aso assisted-installs=%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HEN8SDX3JDJPJHJ8983PR80Y=%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB attribution=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX34FCSPE0AJWPTHQSK=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 attribution-link=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF h_01HEN8SDX305EHK40YCHS9E5KV=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF h_01HEN8SDX38MRMC184HQPM6C84=audiences banner=%E3%83%90%E3%83%8A%E3%83%BC h_01HEN8SDX3ZNJGT3W69RM45FQA=%E3%83%90%E3%83%8A%E3%83%BC bi-system=bi%E3%82%B7%E3%82%B9%E3%83%86%E3%83%A0 h_01HEN8SDX3GFHDQ77RFGHDKM8N=bi%E3%82%B7%E3%82%B9%E3%83%86%E3%83%A0 bid=%E5%85%A5%E6%9C%AD%E5%8D%98%E4%BE%A1 h_01HEN8SDX3J5NEBQHG73K5H5GK=%E5%85%A5%E6%9C%AD%E5%8D%98%E4%BE%A1 brand-bundle=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB h_01HEN8SDX45TRA9FXD3DA2Z3ZQ=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB branded-link=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%AA%E3%83%B3%E3%82%AF h_01HEN8SDX4S7NPDB9M8KT6TCAQ=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%AA%E3%83%B3%E3%82%AF bundle-id=%E3%83%90%E3%83%B3%E3%83%89%E3%83%ABid h_01HEN8SDX41RE0ECZ08D2QRVM7=%E3%83%90%E3%83%B3%E3%83%89%E3%83%ABid h_01HEN8SDX4Y2JKY2TMBF6JDPRZ=cac campaign=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 h_01HEN8SDX49817AMNZNGZ75ZGF=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 campaign-id=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3id h_01HEN8SDX4Q7YZR2FP12Y5ZDGD=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3id carrier=%E9%80%9A%E4%BF%A1%E4%BA%8B%E6%A5%AD%E8%80%85 h_01HEN8SDX4BVYE29YRRY7991NG=%E9%80%9A%E4%BF%A1%E4%BA%8B%E6%A5%AD%E8%80%85 channel=%E3%83%81%E3%83%A3%E3%83%8D%E3%83%AB h_01HEN8SDX4XE2D4JNH4FHXWV49=%E3%83%81%E3%83%A3%E3%83%8D%E3%83%AB churn=%E3%83%81%E3%83%A3%E3%83%BC%E3%83%B3%E9%A1%A7%E5%AE%A2%E9%9B%A2%E8%84%B1 h_01HEN8SDX4K32KABGYCXYFH1E6=%E3%83%81%E3%83%A3%E3%83%BC%E3%83%B3%E9%A1%A7%E5%AE%A2%E9%9B%A2%E8%84%B1 click=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF h_01HEN8SDX4DWGPF3XZFFDBE4MF=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF click-flooding=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E6%B4%AA%E6%B0%B4 h_01HEN8SDX4JA1S2XB2GRC7WBWC=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E6%B4%AA%E6%B0%B4 click-url=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AFurl h_01HEN8SDX4M8EK5M0R436X0TCN=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AFurl client=%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88 h_01HEN8SDX431AYK22N120YGBNW=%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88 h_01HEN8SDX49SCP4PAFA9K530JJ=coa cohort-analysis=%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E5%88%86%E6%9E%90 h_01HEN8SDX42HFKR2SG5W5T80VJ=%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E5%88%86%E6%9E%90 contributor=%E8%B2%A2%E7%8C%AE%E5%85%83 h_01HEN8SDX4955H0NFN7VRFKGSH=%E8%B2%A2%E7%8C%AE%E5%85%83 conversion=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 h_01HEN8SDX4PX3EZT0KYFMFZSRV=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 conversion-chain=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%AB%E8%87%B3%E3%82%8B%E4%B8%80%E9%80%A3%E3%81%AE%E6%B5%81%E3%82%8C h_01HEN8SDX4NVR5QR15V9VQP2F9=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%AB%E8%87%B3%E3%82%8B%E4%B8%80%E9%80%A3%E3%81%AE%E6%B5%81%E3%82%8C conversion-event=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HEN8SDX4CG0Q88798ANFKJTF=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 conversion-rate=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E7%8E%87 h_01HEN8SDX4J7BADYKM6G8RPYRZ=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E7%8E%87 conversion-types=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%BF%E3%82%A4%E3%83%97 h_01HEN8SDX4PVM1AM4BJ8PVC04F=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%BF%E3%82%A4%E3%83%97 cookies-http=cookiehttp h_01HEN8SDX4R2YJ9001EHHRJFSQ=cookiehttp h_b6dda915-a18c-400e-9680-bfe6ee1b9618=cpa h_245fa59f-e321-4b19-b80a-32ab163f4127=cpc h_752531f0-7f67-434a-82a3-874c910bf441=cpi h_1204d4f6-f4d8-4f4e-bc71-8f044bd1432b=cpm h_01HEN8SDX40067S6P49GQBBFK6=cpv creative=%E3%82%AF%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96 h_01HEN8SDX4PDDMB9Y38J2KF87H=%E3%82%AF%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96 h_01HEN8SDX4PR5ZW8CYTBK4JJSJ=crm crosspromotion-attribution=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX47P20MCDFQBG7KKM8=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX4PHZRTGEJN28QK2H7=csm csv-file=csv%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB h_01HEN8SDX4AY2QMDNZW1JN3WG5=csv%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB h_01HEN8SDX4FG94VX8TF4T9ZKQV=cta h_01HEN8SDX4QCRC5HR1WWJ4ZYC3=cti h_01HEN8SDX41V4YRJKSA4PPXJT2=ctit h_01HEN8SDX4YRP2H443JN2TMMG1=ctr h_01HEN8SDX4XRGXFC2FCVR1K64B=ctv h_01HEN8SDX48RQZ74D3ASH6614T=cuid h_01HEN8SDX4W57D69HH4SNTPBVT=cv h_01HEN8SDX40DKMPC96R8MR5PE0=data-locker h_01HEN8SDX534RQXZZCBESVKAX8=dau daumau-rate=daumau%E7%8E%87 h_01HEN8SDX5XGZBETHQEWE500V7=daumau%E7%8E%87 deeplinking=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF h_01HEN8SDX5TBHA338N2VM5FRNK=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF deferred-deeplinking=%E9%81%85%E5%BB%B6%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF h_01HEN8SDX5NRG7VGF0Q06PRAXH=%E9%81%85%E5%BB%B6%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF deprecation-notice=%E5%BB%83%E6%AD%A2%E4%BA%88%E5%AE%9A%E3%81%AE%E9%80%9A%E7%9F%A5 h_01HEN8SDX51W1DQMRY1RDYME5F=%E5%BB%83%E6%AD%A2%E4%BA%88%E5%AE%9A%E3%81%AE%E9%80%9A%E7%9F%A5 dev-key=dev%E3%82%AD%E3%83%BC h_01HEN8SDX5QYS7N33ZVCCJZ4XF=dev%E3%82%AD%E3%83%BC device-id=%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9id h_01HEN8SDX5S9FNBPRDGG7WSS94=%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9id direct-publisher=%E7%9B%B4%E6%8E%A5%E5%A5%91%E7%B4%84%E3%81%AE%E3%83%91%E3%83%96%E3%83%AA%E3%83%83%E3%82%B7%E3%83%A3%E3%83%BC h_01HEN8SDX5DXH9D3GA21BE9CJ7=%E7%9B%B4%E6%8E%A5%E5%A5%91%E7%B4%84%E3%81%AE%E3%83%91%E3%83%96%E3%83%AA%E3%83%83%E3%82%B7%E3%83%A3%E3%83%BC h_01HEN8SDX52V9PEGKFTB0BRHS1=dma domain=%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 h_01HEN8SDX5DKHSYZA5H5002AVD=%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 h_01HEN8SDX5PBRPCV9TH5TD9694=dsp dual-consent=%E3%83%87%E3%83%A5%E3%82%A2%E3%83%AB%E5%90%8C%E6%84%8F h_01HEN8SDX55CKZH56BAKNEH1FY=%E3%83%87%E3%83%A5%E3%82%A2%E3%83%AB%E5%90%8C%E6%84%8F earned=%E3%82%A2%E3%83%BC%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 h_01HEN8SDX59WSESQH3KZAB07WH=%E3%82%A2%E3%83%BC%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 h_01HEN8SDX5EFS8BTBFYE9S05PK=ecpa h_01HEN8SDX55G2HG22966045JMM=ecpc h_01HEN8SDX5WBCBHFPE551ZNZ3K=ecpi h_01HEN8SDX5JHVYGHRESRAD9FMG=ecpm engagement=%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 h_01HEN8SDX5DGEVT9DX8BGE8G5Q=%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 h_01HEN8SDX5PS54X45D228MKSJN=erpa h_01HEN8SDX549Q05QGBD2EDHYM0=esp event=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HEN8SDX5RHZ1RNS8NQ8N1ED6=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 event-counter=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E6%95%B0 h_01HEN8SDX5B958HZ7JCQS2YSH7=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E6%95%B0 event-cvr=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88cvr h_01HEN8SDX5EXJFKCVATQTQVS1V=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88cvr event-time=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E6%99%82%E5%88%BB h_01HEN8SDX5D8W372DY5GW47984=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E6%99%82%E5%88%BB fraud=%E4%B8%8D%E6%AD%A3 h_01HEN8SDX54MS58C47EG8MNM4W=%E4%B8%8D%E6%AD%A3 h_01HEN8SDX5XP88TXJ5XHFHZKT4=gaid h_01HEN8SDX52X53R1B2Z3AETPHC=gcd geo=%E5%9B%BD%E5%9C%B0%E5%9F%9F h_01HEN8SDX5WQ3FGZV03C7YZBF1=%E5%9B%BD%E5%9C%B0%E5%9F%9F id-matching=id%E3%83%9E%E3%83%83%E3%83%81%E3%83%B3%E3%82%B0 h_01HEN8SDX5146H05V3TRCEC7C6=id%E3%83%9E%E3%83%83%E3%83%81%E3%83%B3%E3%82%B0 h_01HEN8SDX54A7DCJY6B9E4QH5C=idfa h_01HEN8SDX54771KFHXCHAPGZF8=idfv h_01HEN8SDX5XRAN7XJMJVHBC1V5=imei impression=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX5CZAXW025YVV0G34S=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 inapp-events=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HEN8SDX5Z6CV6AT4A4M8PJE5=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 install=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HEN8SDX5XVV3WYG56RNPRHJE=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB install-hijacking=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF h_01HEN8SDX54XEEKRA0NVZCE2FX=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF install-referrer=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9 h_01HEN8SDX51JXNARDV17VCS4RK=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9 integrated-partner=%E9%80%A3%E6%90%BA%E6%B8%88%E3%81%BF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC h_01HEN8SDX5ZTQTQW88WDN59Y7X=%E9%80%A3%E6%90%BA%E6%B8%88%E3%81%BF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC integrated-partner-types=%E9%80%A3%E6%90%BA%E6%B8%88%E3%81%BF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E7%A8%AE%E9%A1%9E h_01HEN8SDX54RXCDDH7E9G38SGE=%E9%80%A3%E6%90%BA%E6%B8%88%E3%81%BF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E7%A8%AE%E9%A1%9E landing-page=%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8 h_01HEN8SDX6VCM4H2T5M0RAEX1P=%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8 lastclick-attributions=%E3%83%A9%E3%82%B9%E3%83%88%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX68HKMZ4KHA509BAWF=%E3%83%A9%E3%82%B9%E3%83%88%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX6382B9SH0D1EE0V0F=lat link-management=%E3%83%AA%E3%83%B3%E3%82%AF%E7%AE%A1%E7%90%86 h_01HEN8SDX648ARRJ94Y17MRKA0=%E3%83%AA%E3%83%B3%E3%82%AF%E7%AE%A1%E7%90%86 localization=%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%A9%E3%82%A4%E3%82%BA h_01HEN8SDX615FPYS8F251181KE=%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%A9%E3%82%A4%E3%82%BA lookback-window=%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HEN8SDX6YCQJNFJTNFAAN3BE=%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 loyal-user=%E3%83%AD%E3%82%A4%E3%83%A4%E3%83%AB%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC h_01HEN8SDX6F3JFJ72HARJNMFZR=%E3%83%AD%E3%82%A4%E3%83%A4%E3%83%AB%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC h_01HEN8SDX63AWJM064929J05C6=ltv macros=%E3%83%9E%E3%82%AF%E3%83%AD h_01HEN8SDX66X31YR1TTND9DFCS=%E3%83%9E%E3%82%AF%E3%83%AD marketer=%E3%83%9E%E3%83%BC%E3%82%B1%E3%82%BF%E3%83%BC h_01HEN8SDX6XH8HEE8VADNY46ZQ=%E3%83%9E%E3%83%BC%E3%82%B1%E3%82%BF%E3%83%BC marketing-automation=%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%AA%E3%83%BC%E3%83%88%E3%83%A1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX6E2422J2VWXJJTYWC=%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%AA%E3%83%BC%E3%83%88%E3%83%A1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX61T183Z5HGRA1R5AM=master-api h_01HEN8SDX63DSDVBPKR9RRT9RM=mau media-source=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9 h_01HEN8SDX6BHDD2FFYGR6K1FVY=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9 mediation-network=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A8%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0 h_01HEN8SDX6KBQX4FEVHWT7EG60=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A8%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0 fmp=meta%E3%81%AE%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E7%AE%A1%E7%90%86-%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC h_01HEN8SDX6HZKMXC87QX8MCJR6=meta%E3%81%AE%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E7%AE%A1%E7%90%86-%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC mmp=mcp h_01HEN8SDX6AJDYPN0SHFFZTWED=mcp 01K07Q4NW3J45EHMS7B7P41AD5=mmp mobile-app=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA h_01HEN8SDX6SH76VX72F3ZV3JN0=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA monetization-network=%E5%8F%8E%E7%9B%8A%E5%8C%96%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF h_01HEN8SDX6A712J62ZHQV676D8=%E5%8F%8E%E7%9B%8A%E5%8C%96%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF multiplatform=%E8%A4%87%E6%95%B0%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E5%AF%BE%E5%BF%9C h_01HEN8SDX6XEW6ZR5SHBBHJBKD=%E8%A4%87%E6%95%B0%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E5%AF%BE%E5%BF%9C multitouch-attribution=%E3%83%9E%E3%83%AB%E3%83%81%E3%82%BF%E3%83%83%E3%83%81%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX6Y6GEX191MYQB3HX1=%E3%83%9E%E3%83%AB%E3%83%81%E3%82%BF%E3%83%83%E3%83%81%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 native-ad=%E3%83%8D%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E5%BA%83%E5%91%8A h_01HEN8SDX6V5WJD0VQRFRQC855=%E3%83%8D%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E5%BA%83%E5%91%8A native-app=%E3%83%8D%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E3%82%A2%E3%83%97%E3%83%AA h_01HEN8SDX65DRV75S0J6ZG0EBZ=%E3%83%8D%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E3%82%A2%E3%83%97%E3%83%AA h_01HEN8SDX6ZD002916GJNCDZD6=noi h_01HEN8SDX62YK0HCSKC9HB045Q=oaid onelink%E2%84%A2=onelink h_01HEN8SDX6A7T0G6RR499ABA8M=onelink onelink%E2%84%A2-id=onelink-id h_01HEN8SDX6XREN51ZDG2FRQVW9=onelink-id onelink%E2%84%A2-template=onelink%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88 h_01HEN8SDX65TNGHEH6DVZ8Y5RM=onelink%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88 organic-install=%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HEN8SDX6WF5NS11WTK2CPMXP=%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HEN8SDX6D90KJA2FGBX7P3J9=ott owned-media=%E3%82%AA%E3%82%A6%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 h_01HEN8SDX6CK2YY6TX7AFMD57D=%E3%82%AA%E3%82%A6%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 package-id=%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8id h_01HEN8SDX6EE40X59B2Z2HZBRT=%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8id paid=%E3%83%9A%E3%82%A4%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 h_01HEN8SDX6KN197MMBWJG94C7J=%E3%83%9A%E3%82%A4%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 h_01HEN8SDX6MS4VJFFWHJEDYXMN=pba h_01HEN8SDX6A3N1A2EGBEGE1YN5=pid postback=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HEN8SDX6ZXY44SY0Z2FGWZ4F=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HEN8SDX6EHRZ4EGT49ABF5QA=ppc probabilistic-modeling=%E7%A2%BA%E7%8E%87%E8%AB%96%E7%9A%84%E3%83%A2%E3%83%87%E3%83%AA%E3%83%B3%E3%82%B0 h_01HEN8SDX6534FRMZ4QVPAMMZK=%E7%A2%BA%E7%8E%87%E8%AB%96%E7%9A%84%E3%83%A2%E3%83%87%E3%83%AA%E3%83%B3%E3%82%B0 programmatic-advertising=%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9E%E3%83%86%E3%82%A3%E3%83%83%E3%82%AF%E5%BA%83%E5%91%8A h_01HEN8SDX62CC461QBM4NAP6BB=%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9E%E3%83%86%E3%82%A3%E3%83%83%E3%82%AF%E5%BA%83%E5%91%8A h_01HEN8SDX7FVTAQNC1H00E3HJ5=protect360 publisher=%E3%83%91%E3%83%96%E3%83%AA%E3%83%83%E3%82%B7%E3%83%A3%E3%83%BC h_01HEN8SDX72FFBA6GB3QWQWYW8=%E3%83%91%E3%83%96%E3%83%AA%E3%83%83%E3%82%B7%E3%83%A3%E3%83%BC h_01HEN8SDX720DXVKMN32TX0CWP=pull-api h_01HEN8SDX7TZCBJYAQRCDJNH4X=push-api qr-code=qr%E3%82%B3%E3%83%BC%E3%83%89 h_01HEN8SDX7Y4WWA5X6WESAD8WT=qr%E3%82%B3%E3%83%BC%E3%83%89 raw-data=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF h_01HEN8SDX7DT4SYE7038DWD8F6=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF reattribution=%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX7B1KV0MJP7J69AKBZ=%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 reattribution-window=%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93 h_01HEN8SDX7KZMED0GZ8KYSA0N8=%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93 reengagement=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 h_01HEN8SDX77FRCVX6VT62TNBYG=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88 registered-device=%E7%99%BB%E9%8C%B2%E6%B8%88%E3%81%BF%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9 h_01HEN8SDX7DCAHZAB7VC6E092K=%E7%99%BB%E9%8C%B2%E6%B8%88%E3%81%BF%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9 request=%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88 h_01HEN8SDX7Z51T0RCVQQJ48SXF=%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88 retargeting=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01HEN8SDX79FQRPHMFDBEZ8FMX=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 retargeting-network=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF h_01HEN8SDX7YQ32DJR4W90DKCR4=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF retention-report=%E3%83%AA%E3%83%86%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HEN8SDX7BDSF0JZE0KYSPSSE=%E3%83%AA%E3%83%86%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 revenue=%E5%8F%8E%E7%9B%8A h_01HEN8SDX7EYBRAQZHYW2VHYK2=%E5%8F%8E%E7%9B%8A revenue-attribution=%E5%8F%8E%E7%9B%8A%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX7FCP26JW3T1M8C0PJ=%E5%8F%8E%E7%9B%8A%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 revenue-event=%E5%8F%8E%E7%9B%8A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HEN8SDX7QYH0ZMFYWMJ8XEPX=%E5%8F%8E%E7%9B%8A%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 rich-media-ad=%E3%83%AA%E3%83%83%E3%83%81%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E5%BA%83%E5%91%8A h_01HEN8SDX7FD7Y6ES4FQT23WPE=%E3%83%AA%E3%83%83%E3%83%81%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E5%BA%83%E5%91%8A h_01HEN8SDX7CES5N0V552KGFH5W=roas h_01HEN8SDX7HM0SF48X644DS3GB=roi h_01HEN8SDX7FVGWHBSWM00723TH=san h_01HEN8SDX7TNCRH3GJ02JF88YB=sdk segmentation=%E3%82%BB%E3%82%B0%E3%83%A1%E3%83%B3%E3%83%86%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX7T1RY6Z4HAPMJYXA4=%E3%82%BB%E3%82%B0%E3%83%A1%E3%83%B3%E3%83%86%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 session=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX7NNPZ6HA562T7QGEJ=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 singleplatform=%E5%8D%98%E4%B8%80%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E5%90%91%E3%81%91 h_01HEN8SDX7NVZQTZKEXY1Y9FNZ=%E5%8D%98%E4%B8%80%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E5%90%91%E3%81%91 single-source-of-truth-ssot=single-source-of-truthssot h_01HEN8SDX7JGGCNSE6AKQSM227=single-source-of-truthssot h_01HEN8SDX7MKB1BV2WAWNDQGZM=skadnetwork h_01HEN8SDX7724Y7SXCQ8KRT0G0=skan slug=%E3%82%B9%E3%83%A9%E3%83%83%E3%82%B0 h_01HEN8SDX7SR4JH8TV6S6GRW9T=%E3%82%B9%E3%83%A9%E3%83%83%E3%82%B0 h_01HEN8SDX7T8A5Z5RHXYPM7MNS=smart-banner h_01HEN8SDX783XE97MJ3F99R956=srn h_01HEN8SDX73GSJ00WG3EXP5FMP=ssp subdomain=%E3%82%B5%E3%83%96%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 h_01HEN8SDX7BP8747RSWVWTG4E6=%E3%82%B5%E3%83%96%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 sunset-date=%E6%8F%90%E4%BE%9B%E7%B5%82%E4%BA%86%E6%97%A5 h_01HEN8SDX7V90JQ6A8NDNMXXFS=%E6%8F%90%E4%BE%9B%E7%B5%82%E4%BA%86%E6%97%A5 targeting=%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01HEN8SDX7DRVPG5GD3ADYS75G=%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 account-user=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC h_01HEN8SDX7Y9M1PYVQBQGZ4WP7=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC touch-time=%E5%BA%83%E5%91%8A%E6%8E%A5%E8%A7%A6%E6%97%A5%E6%99%82 h_01HEN8SDX727346Z5E4Q13VTXA=%E5%BA%83%E5%91%8A%E6%8E%A5%E8%A7%A6%E6%97%A5%E6%99%82 touch-type=%E5%BA%83%E5%91%8A%E6%8E%A5%E8%A7%A6%E3%81%AE%E7%A8%AE%E9%A1%9E h_01HEN8SDX77Q54AKBDX4CKGRFG=%E5%BA%83%E5%91%8A%E6%8E%A5%E8%A7%A6%E3%81%AE%E7%A8%AE%E9%A1%9E touchpoint=%E3%82%BF%E3%83%83%E3%83%81%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88 h_01HEN8SDX7Q7F3C3291KR4JNJJ=%E3%82%BF%E3%83%83%E3%83%81%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88 h_01HEN8SDX7P2CDZPDSHQSMCY6T=udid uninstall-measurement=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC h_01HEN8SDX8J66DR158FQPYET27=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC unique-user=%E3%83%A6%E3%83%8B%E3%83%BC%E3%82%AF%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC h_01HEN8SDX8E816PCQX7D4SN1X6=%E3%83%A6%E3%83%8B%E3%83%BC%E3%82%AF%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC universal-links=%E3%83%A6%E3%83%8B%E3%83%90%E3%83%BC%E3%82%B5%E3%83%AB%E3%83%AA%E3%83%B3%E3%82%AF h_01HEN8SDX8100A9JKAW8VNHFC4=%E3%83%A6%E3%83%8B%E3%83%90%E3%83%BC%E3%82%B5%E3%83%AB%E3%83%AA%E3%83%B3%E3%82%AF user=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC h_01JQ6GFZQWFNEH39SFVQMM82Z3=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC user-acquisition=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97 h_01HEN8SDX8FVQVKT3HFH0J6WQW=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97 user-agent=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%A8%E3%83%BC%E3%82%B8%E3%82%A7%E3%83%B3%E3%83%88 h_01HEN8SDX8995ZVWTMVWRM0B3S=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%A8%E3%83%BC%E3%82%B8%E3%82%A7%E3%83%B3%E3%83%88 user-invite-attribution=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%8B%9B%E5%BE%85%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEN8SDX8GYFG1CSA6S7GAX1B=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%8B%9B%E5%BE%85%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 validation-rules=%E6%A4%9C%E8%A8%BC%E3%83%AB%E3%83%BC%E3%83%AB h_01HEN8SDX8ZFG16E6TY7KWHJSG=%E6%A4%9C%E8%A8%BC%E3%83%AB%E3%83%BC%E3%83%AB verticals=%E6%A5%AD%E7%A8%AE h_01HEN8SDX8PGY44XZ80JM3GZ42=%E6%A5%AD%E7%A8%AE video-ad=%E5%8B%95%E7%94%BB%E5%BA%83%E5%91%8A h_01HEN8SDX8H82QRWR81ECK27HC=%E5%8B%95%E7%94%BB%E5%BA%83%E5%91%8A visitor-website=%E8%A8%AA%E5%95%8F%E8%80%85web%E3%82%B5%E3%82%A4%E3%83%88 h_01HEN8SDX8GW7AC0V3APY9J0MX=%E8%A8%AA%E5%95%8F%E8%80%85web%E3%82%B5%E3%82%A4%E3%83%88 h_01HEN8SDX87ACVFRN8BA517GD9=vta web-app=web%E3%82%A2%E3%83%97%E3%83%AA h_01HEN8SDX8PZS5S4VN5QGQ9MC8=web%E3%82%A2%E3%83%97%E3%83%AA x-marketing-partners=x%E3%81%AE%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC h_01HFV2G10B63FN5CHWXA0C8MDH=x%E3%81%AE%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC" />

---
title: Creative Optimization｜ガイド
metadata:
  keywords:
    - Premium
    - Marketers
    - Design team
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-09-14T13:32:13Z'
  edited_at: '2026-10-28T08:56:03Z'
  id: 18564718580625
  locale: ja
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/ja/articles/18564718580625
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** Creative Optimizationでは、すべてのキャンペーンのクリエイティブアセットデータを1つのプラットフォームに集約できます。パフォーマンスを分析して最も効果的なクリエイティブを特定し、データに基づいてより適切な判断を下せます。データはLTVベースです。つまり、選択した期間中にクリエイティブ経由で発生したコンバージョンに関する指標を示します。

<Image align="center" alt="Main image -Default view.jpg" src="https://files.readme.io/9ef8901b620d54cad031ec142f5dd408406e0a470bae8a0719826777561cd1d1-21362497825169.jpg" />

<div id="about-creative-optimization" />

## Creative Optimizationについて

**Creative Optimization**は、すべてのキャンペーンで使用するクリエイティブのパフォーマンスを1か所で計測できるツールです。これにより、すべてのメディアチャネルからすべてのクリエイティブアセットを1か所またはBIシステムに簡単に取り込み、複数のキャンペーンやチャネルなどにわたって、選択したディメンションごとにパフォーマンスを分析できます。 Creative Optimizationでは、さまざまな指標やKPIでデータを多角的に分析し、次に制作するクリエイティブの企画・選定・制作に先立って重要なインサイトを得られます。

Creative Optimizationダッシュボードでは、動画、画像、HTML、テキストのパフォーマンスを測定し、時間の経過やチャネル間でのパフォーマンスを確認できます。各クリエイティブは、強力なAIアルゴリズムによって分析・集計・マッチングされます。つまり、さまざまなキャンペーンやメディアソースで使用された同一のクリエイティブは、その命名規則や広告ID、その他のメタデータに関係なくマッチングされ、管理画面にまとめて表示されます。

<Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-overview-dashboard">Creative Optimizationオーバービューダッシュボード</Anchor>では、豊富な情報を含むさまざまなグラフと詳細な表でデータを視覚的に確認できます。キャンペーンに使用するCreative Optimizationや選定に必要な情報を把握できます。

AIを搭載した<Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-discovery-ai-dashboard">Creative Optimization Discoveryダッシュボード</Anchor>を活用すれば、推測に頼らずに効果的なクリエイティブを制作できます。すべてのクリエイティブを包括的に把握したり、個々に含まれる特定のシーンや要素のパフォーマンスを詳細に調査して、最大限のインサイトを得ることができます。

<Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-etl-reporting">Creative Optimization ETL</Anchor>は、レポートをクラウドストレージへ自動配信し、プログラムを使用してBIシステムへ効率的に取り込めるようにします。これにより、データアナリストはクリエイティブのパフォーマンス分析に必要な情報を取得できます。

Creative Optimizationでは、次のことができます：

* 効果的なクリエイティブ、シーン、要素と、そうでないものをすばやく把握
* データに基づいてクリエイティブを最適化
* クリエイティブパフォーマンスおよびROIの改善
* 最も効果的なクリエイティブを制作
* 期間・チャネル・キャンペーンを横断してクリエイティブの効果低下を把握し、データに基づいて最適化の判断を実施
* その他多数

<div id="creative-assets" />

## クリエイティブアセット

本セクションでは、当社で計測しているクリエイティブアセットに関する情報を提供します。

<div id="supported-asset-types" />

<Accordion title="対応アセットタイプ">

Creative Optimizationダッシュボードでサポートされるアセットタイプには、次のものがあります：

* 動画
* 画像
* カルーセル広告（Metaのみ）
* HTML（プレイアブル含む）
* テキスト

<div id="notes" />

> 📘 **注意**
>
> * ダッシュボード上でプレビューできるアセットは、画像、動画、テキストです。
> * 「クリエイティブの類似性」機能は、
>   カルーセル広告にはまだ対応していません。

</Accordion>

<div id="matching-creatives" />

<Accordion title="クリエイティブのマッチング">

Creative Optimizationには、命名規則やIDに関係なく、複数のチャネルやキャンペーンで同じアセットを識別するAppsFlyer独自の機能が備わっています。 AIとコンピュータービジョンのアルゴリズムにより、映像の内容、音声、ピクセルなどの特徴を照合します。その他にも：

* 同一と判定されるクリエイティブは、縦長、横長、正方形などのアスペクト比が一致している必要があります。
* 再生時間が異なる動画は、別のクリエイティブと見なされます。

</Accordion>

<div id="measuring-creatives-with-multiple-assets" />

<Accordion title="複数アセットのクリエイティブ計測">

**Creative Optimizationでは、複数のアセットを含む広告クリエイティブをどのように測定しますか？**

Meta Advantage+（ダイナミッククリエイティブ）、Googleユニバーサルアプリキャンペーン（UAC）は、複数のアセットを持つ広告クリエイティブを含むことができます。ただし、AppsFlyerはデータをアセット単位で直接取得するわけではありません。 Meta広告は**広告レベル**までのデータを提供し、Googleは**広告グループレベル**までのデータしか提供しません。このような広告クリエイティブでは、AppsFlyerはデータモデリングを使用して、パフォーマンスデータを各アセットに配分します。

<div id="example" />

> 📄 **例**
>
> Facebookに複数のアセットを持つ広告クリエイティブがあるとしましょう。 Facebookで計測されたインストール数が合計100件で、その内訳が**アセットA**は60件、**アセットB**は40件だったとします。 AppsFlyerでは、広告に50インストール紐づいているとします（AppsFlyerと<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">SRN</Anchor>の固有のアトリビューションの違いによる）。アセット単位で分析できるよう、AppsFlyerは以下のように、全体に占める各アセットの指標の比率に基づいてパフォーマンスデータ（インプレッション数、クリック数、インストール数、コスト）を配分します。
>
> **アセットAの場合：**
> 60件÷（60＋40件：Facebookで計測されたインストール数の合計）＝0.6
> 0.6×50件（AppsFlyerで計測されたインストール数）＝30件
>
> **アセットBの場合：**
> 40件÷（60＋40件：Facebookで計測されたインストール数の合計）＝0.4
> 0.4×50件（AppsFlyerで計測されたインストール数）＝20件
>
> このように、AppsFlyerでは広告クリエイティブに合計50件のインストールが紐づきますが、アセット間のインストール数の比率は維持されます。この例では、**アセットA**が**アセットB**より多くのインストールを獲得したことになります。
> 収益やROASなど、ファネル下部の指標もこの比率に基づいて計算されます。
>
> <Image align="center" alt="Creative_data_example_en-us.png" src="https://files.readme.io/ca556904829b809238b8b994fd6d762d6cb58ae993c41dd19a7de978f774e8b9-small-18564727253649.png" />

</Accordion>

<div id="using-the-dashboard" />

## ダッシュボードの使用方法

このセクションでは、メインダッシュボードの概要を説明します。フィルターの使い方、目的のクリエイティブデータを確認するために利用できる指標やディメンション、ダッシュボードビューの保存・共有方法を紹介します。

<Image align="center" alt="Filter bar and metrics -Default view.jpg" src="https://files.readme.io/b68e65ff2cdd2ad2fe0805eb1c2792904af69504d104b6f6ae8a524124272a48-21363121543185.jpg" />

<div id="filter-bar" />

<Accordion title="フィルターバー">

ダッシュボードのセットアップにおける最初のステップは、フィルターオプションを選択することです。すべてのフィルターは、Creative OptimizationのオーバービューダッシュボードとDiscoveryダッシュボードの両方に適用されます。

<Image align="center" alt="filter_bar.jpg" src="https://files.readme.io/99da48c37938e573af66cf1f46ce3273c3ca010e68070cb59b5e12cbad1981e3-18564730224913.jpg" />

**ダッシュボードのフィルターを選択するには**：

1. 以下を選択できます：
   * **アプリ**
   * **期間：** 選択した期間中にそのクリエイティブのコンバージョンデータがある場合、ダッシュボードに表示されます。すべてのデータはLTVベースです。つまり、選択した期間中にクリエイティブ経由で発生したコンバージョンに関する指標を示します。
   * [表示タイプ](#view-type)
2. ＋アイコンをクリックし、以下の絞り込み条件を追加します。
   * **ディメンションと指標**
   * **数値フィルター**では、すべての指標について以下の条件を指定できます。
     * より大きい－選択した指標の値以上のクリエイティブを表示します。
     * 未満－選択した指標の値を下回るクリエイティブを表示します。

Creative Optimizationダッシュボードでは、[標準の指標とディメンション](/docs/creative-optimization-guide#standard-metrics-and-dimensions)に加え、さまざまな[独自の指標とディメンション](#unique-metrics-and-dimensions)を利用できます。

</Accordion>

<div id="view-type" />

<Accordion title="表示タイプ">

管理画面のクリエイティブデータは、3つの異なる表示タイプで表示されます：統合、ユーザー獲得（UA）、リターゲティング：

* **統合** -新規獲得やリターゲティング広告、広告セットのすべてのクリエイティブデータを表示します。
* **ユーザー獲得**－UAの広告・広告セットに関連するクリエイティブデータのみを表示します。
* **リターゲティング** -リターゲティング広告や広告セットに紐づくクリエイティブデータのみを表示します。コストデータもこちらで入手できます。

<Image align="center" alt="View_types.jpg" src="https://files.readme.io/e73cc643581e94d6fbc6455e16615eb2e1d8b387cda626d39b17bbe714122611-18564727261585.jpg" />

</Accordion>

<div id="creative-optimization-roi360" />

<Accordion title="Creative Optimization + ROI360">

AppsFlyerのROI360の契約がある場合、Creative Optimizationダッシュボードに表示されるコストデータはROI360から取得され、ROI360はアドネットワークパートナーからのコストデータを統合して処理し、コストベースの指標を追加します。 ROI360の契約がない場合、コストデータは連携メディアパートナー独自のレポートから取得されます。最も包括的で最新のコストデータを利用するには、ROI360の契約をお勧めします。以下の表は、ROI360を使用した場合と使用しない場合のCreative Optimizationの違いを示しています。

| ROI360あり | ROI360なし |
| --- | --- |
| <ul><li><Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-cost-and-revenue-data#広告費関連ツール">ROI360経由でレポートされたデータが存在</Anchor>します。</li><li><Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-cost-and-revenue-data#広告費関連ツール">ROI360のコストレポート機能をすべて</Anchor>備えています。</li><li>クリエイティブETLにはコストデータが含まれています（ROI360 Advancedの契約が必要です）。</li></ul> | <ul><li>連携パートナーから直接レポートされるコストデータは、クリエイティブETLではなく、Creative Optimization管理画面に限定されます。</li></ul> |

詳細：<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-cost-and-revenue-data">ROI360</Anchor>

</Accordion>

<div id="standard-metrics-and-dimensions" />

<Accordion title="標準の指標とディメンション">

ダッシュボードで使用できる標準の指標・ディメンションは以下を含みます：

| 指標/ディメンション | 説明 |
| --- | --- |
| インプレッション | クリエイティブの表示回数 |
| クリック | クリエイティブを含む広告のクリック数 |
| コンバージョン | <ul><li>インストール-アプリをインストールしたユニークユーザー数</li><li>リエンゲージメント-リターゲティングキャンペーンに接触した後にアプリを開いたユニークユーザーの数</li><li>リアトリビューション-リターゲティングキャンペーンに接触した後にアプリを再インストールしたユニークユーザーの数</li></ul> |
| コスト | クリエイティブコスト |
| CTR（クリック率） | 総表示回数に対して広告がクリックされた割合（％）です。数式：クリック÷インプレッションx 100 |
| CVR（コンバージョン率） | クリックからアトリビューション（インストール、リエンゲージメント、リアトリビューション）までのジャーニーを完了したユーザーの割合(%)。計算式：コンバージョン数÷クリック数×100 |
| IPM（1,000インプレッションあたりのインストール数） | 1,000インプレッションあたりのインストール数です。ユーザーへのインプレッション（広告表示）1,000回あたりのインストール数 |
| eCPI（実効インストール単価） | eCPIはオーガニックインストールを除き、<Anchor target="_blank" href="/marketers/ja/docs/about-organic-and-non-organic-installs">非オーガニックアトリビューション</Anchor>（インストール、リエンゲージメント、リアトリビューション）1件あたりのコストを算出します。数式：利用可能な総コスト÷非オーガニックアトリビューション数 |
| CPM（インプレッション単価） | 広告インプレッション1,000回あたりのコストです。計算式：クリエイティブの総広告費÷インプレッション数）×1,000 |
| プラットフォーム | OSを指します（例： Android）。 |
| チャネル | メディアソース内でのトラフィックの分類  <br />（例： GoogleのYouTube、Meta広告のInstagramなど） |
| 地域 | 国/ロケーション |
| ID | <ul><li>クリエイティブ</li><li>広告</li><li>広告セット</li><li>キャンペーン</li></ul> |
| 代理店 | 選択した代理店が運用するクリエイティブデータを表示します。 |
| 収益（D0、D1、D3、D7、D14、D30、D60、D90） | AppsFlyerにレポートされたコホート収益 |
| ROAS（D0、D1、D3、D7、D14、D30、D60、D90） | コホート別の広告費用対効果（％）です。広告費用の単位あたりの収益を計算します。数式：収益÷コストx 100 |
| ユニークユーザー数（D0、D1、D3、D7、D14、D30、D60、D90） | インストールから指定日までにアプリを使用した、コホートユニークユーザー数 |
| リテンション（D0、D1、D3、D7、D14、D30、D60、D90） | 所定の期間サービスや製品の利用を継続したユーザーのコホート率（％）<br /><br />**注意：** データはAppsFlyerのコホートダッシュボードと一致します。 |

</Accordion>

<div id="unique-metrics-and-dimensions" />

<Accordion title="独自の指標とディメンション">

ダッシュボードでは、以下の独自の指標・ディメンションを利用できます。

| 指標/ディメンション | 説明 |
| --- | --- |
| 使用数 | 複数のチャネルを横断して、特定のクリエイティブが使用されているキャンペーン・広告セット・広告の数を表示します。 |
| [パートナー指標](/docs/creative-optimization-guide#partner-dimensions-and-metrics) | 連携パートナーから直接取得されるパフォーマンスデータ（AppsFlyerのアトリビューションデータからではない） |
| クリエイティブの類似性 | ほぼ同一の（ただし多少の違いがある）クリエイティブをグループ化し、パフォーマンスを比較することで、最も良い結果をもたらすバージョンを判断することができます。例えば、異なる向き（縦長と横長）の類似画像は一緒にグループ化され、異なる言語の類似動画も同様にグループ化されます。このディメンションは、画像と動画のみに適用されます。 |
| クリエイティブの経過日数 | キャンペーンの一部としてクリエイティブが配信されている日数を表示します。 AppsFlyerが最初のインプレッション、クリック、インストールのいずれかを受信した日時（クリエイティブの「初回検出」タイムスタンプ）から算出します。選択したディメンションによって値が異なる場合があります。たとえば、ある日にクリエイティブを1つのキャンペーンへアップロードし、別の日に別のキャンペーンへもアップロードしたとします。キャンペーンとクリエイティブの経過日数をディメンションに追加すると、最初のアップロードからの経過日数が表示されます。<br /><br />**注意：** クリエイティブダッシュボードに取り込まれる前に実行されたキャンペーンにおけるクリエイティブに関しては、AppsFlyerが最大で取り込まれる90日前までのデータを表示します。例えば、取り込まれる前にクリエイティブが90日間以上実行されていた場合、最初に表示される「クリエイティブの経過日数」は90日間であり、その後毎日累積的に増え続けることになります。 |
| クリエイティブの初回検出 | パフォーマンスデータ（通常はインプレッション）を最初に受信した日時でクリエイティブを表示します。「クリエイティブの経過日数」の計算は、このタイムスタンプがトリガーとなって始まります。 |
| 長さ | クリエイティブアセットの秒単位の長さ（動画に適用されます） |
| 解像度 | クリエイティブアセットのピクセル単位のサイズ（画像と動画に適用されます）<br /><br />**注意：** 連携されているメディアパートナーにより、ユーザーに提供された実際の解像度が表示されます。これは、最初にアップロードされた解像度とは異なる場合があります。 |
| 向き | 縦長、正方形、横長などの、クリエイティブアセットの向き |
| 月 | 月別パフォーマンスの内訳 |
| 週 | 週別パフォーマンスの内訳 |
| エンドカード | 動画広告の最後に表示されることがある広告を指し、通常はプロモーション対象アプリの基本情報が含まれます。エンドカードごとにクリエイティブをグループ化する機能により、同じエンドカードと異なる動画を比較することで最適な組み合わせを特定するなど、Creative Optimizationのためのインサイトがさらに増えます。以下のエンドカードデータでクリエイティブを見ることができます：<ul><li>エンドカード名</li><li>エンドカードID</li><li>エンドカードの長さ</li><li>エンドカードの解像度</li><li>エンドカードの向き</li><li>エンドカードの種類</li></ul>**注意：**<ul><li>エンドカードのデータは、次のパートナーで利用できます：AppLovin、IronSource、Moloco、UnityAds、Snapchat、YouAppi<ul><li>現在、一意のエンドカード名を提供しているのはironSource、Unity Ads、Snapchatのみです。その他のすべてのパートナーでは、エンドカード名はダッシュボードのクリエイティブ名と同じ名前で表示されます。</li></ul></li></ul> |

</Accordion>

<div id="custom-metrics" />

<Accordion title="カスタム指標">

カスタム指標を作成し、目的に合わせてクリエイティブのパフォーマンスを計測できます。

**カスタム指標の作成方法：**

1. ダッシュボード右上のドロップダウンメニューをクリックし、**カスタム指標**を選択します。  
   **![Custom_metric_select.jpg](https://files.readme.io/99ca0ee30d09e42ef2798188e8d95fc4cf56ee31ad055209efadc47c9df8a859-18564742772625.jpg)**
2. **フォームに以下を入力します。**
   * **名前** -ユニークな指標名を入力します。
   * **タイプ**－数値、パーセント、通貨のいずれかを選択します。
   * **説明**－説明を入力します（任意）。
   * **指標の計算式**－**＋数式を追加**をクリックして計算式を作成します。  
     * *指標*には、インプレッション、クリック、インストール、CTR、CVR、CPM、IPM、コスト、eCPI、リアトリビューション、リエンゲージメント、収益、ROAS、リテンション、ユニークユーザー数、使用数、パートナー指標が含まれます。
     * 各種*演算子、数値*、*アプリ内イベント*を組み合わせます。
     * 特定のアプリ内イベントをドロップダウンメニューから選択します。アプリ内イベントごとに個別の指標を追加し、より詳細に分析できます。たとえば、af\_purchaseの収益＋af\_loginの発生回数という計算式を設定できます。  
       <Image align="center" alt="" src="https://files.readme.io/2b8bdaa8c1fb47c7e78b59e7e24f37aa3248800c7a3ed5cc821c2e11622a93fe-30129836915729.png" width="892px" />
3. **保存**をクリックします。  
   新しいカスタム指標が作成され、フィルターバーと表の設定で、その指標の横に「カスタム」と表示されます。

**注意：**

* カスタム指標は1アカウントにつき30個まで作成できます。
* テーブル設定の「カスタム」タグにカーソルを合わせると、説明が表示されます。

カスタム指標は編集または削除することもできます。

**編集方法：**

1. **カスタム指標**フォーム上の**既存のカスタム指標を編集**ドロップダウンをクリックし、編集する指標を選択します。  
   <Image align="center" alt="" src="https://files.readme.io/b792e08152482bed11ea8ce5ea5795c3df961c257d07397b5b4d787f40a8ea2e-30129836916369.png" width="892px" />
2. 必要な変更を加え、**保存**をクリックします。  
   **注意：名前を付けて保存**をクリックすると、新しいカスタム指標として保存することもできます。

**削除するには：**

* ドロップダウンから削除したいカスタム指標を選択した後、削除アイコンをクリックします。  
  <Image align="center" alt="" src="https://files.readme.io/8370c5bfec23ef2ac15e266e98be357e496aef51fa14ca5b4c853b0b38910a10-30129810517393.png" width="546px" />

</Accordion>

<div id="partner-dimensions-and-metrics" />

<Accordion title="パートナーのディメンションと指標">

パートナー指標は、連携されたメディアパートナーから直接取得されるデータです（AppsFlyerのアトリビューションデータではありません）。指標はパートナーによって異なり、インプレッション、クリック、コンバージョン、コスト、動画再生率などが含まれます。これらの指標はフィルターで選択でき、ダッシュボードやレポート全体で表示したり、表に追加したりできます。

次の表は、すべてのCreative Optimizationパートナーと、それぞれで利用できるデータの粒度を示しています：

* ディメンション
* 指標（アドネットワークによってレポートされたもの）
* サポートされている機能とその特性

ファイルのダウンロード：<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTQLUxhNMmBPTlm1_KsfLTupNL6tgZeqAt5OFwzLJUmhSXZ7K18aX6enuV4ST1mUVarUV-KPrUnMYS6/pub?output=csv">CSV</Anchor>、<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTQLUxhNMmBPTlm1_KsfLTupNL6tgZeqAt5OFwzLJUmhSXZ7K18aX6enuV4ST1mUVarUV-KPrUnMYS6/pub?output=xlsx">XLS</Anchor>

<div id="to-set-up-partner-metrics" />

#### **パートナー指標を設定する方法：**

新しい<Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-partner-integrations">パートナー連携</Anchor>を追加すると、対応パートナーの指標が自動的にCreative Optimizationへ取り込まれます（**Unity Ads**は**例外で、以下の特別な手順が必要です**）。設定が完了すると、これらの指標は指標の横に「パートナー」と表示されます。

<Image align="center" alt="partner metrics image.jpg" src="https://files.readme.io/074948fd8e4707c1353b6f8ce387e76e04801eeef397e94a604619bc8a0ad420-18564730240145.jpg" />

**特別な手順と考慮事項：**

<div id="applovin-metrics" />

<Accordion title="AppLovinの指標">

**注意：**

* AppLovin APIの制限により、最大45日間の履歴データしか利用できません。 AppsFlyerは通常、最大90日間の履歴データを表示できますが、AppLovinの制限により、45日間のAppLovinデータしか利用できません。
* AppsFlyerのクリエイティブデータは、AppLovinの確率論的レポート（請求対象レポートではない）に準拠しています。

</Accordion>

<div id="google-ads-metrics" />

<Accordion title="Google Adsの指標">

**注意：**

* 異なる計測ロジックを用いているため、Google AdsとAppsFlyerで報告されるインストール数に違いがあります。
* GoogleとAppsFlyerでは、すべての指標に違いがあります。これは、Googleのパートナー指標がGoogleのアセットビューレポートに基づいているのに対し、AppsFlyerのデータはGoogleの広告グループビューに連動しているためです。これらのレポートではパフォーマンスデータが一致しません。たとえば、特定の広告グループに含まれるアセットのインプレッション数の合計は、その広告グループがレポートするインプレッション数の合計と一致しません。
* Creative OptimizationとGoogle AdWordsの間には違いがあります。両者のアセットビューを比較した際、以下の理由でわずかな差異が生じる場合があります。1. タイムゾーン（Creative OptimizationはUTC+0）。 2. データの更新タイミング（イベントの発生からプラットフォーム上でデータを利用できるようになるまでの時間）。

</Accordion>

<div id="meta-ads" />

<Accordion title="Meta広告の指標">

**注意：**

* 異なる計測ロジックを用いているため、Meta広告とAppsFlyerでレポートされるインストール数に違いがあります。
* MetaはiOSのインストール数をアセット単位でレポートしないため、Creative Optimizationでも利用できません。

</Accordion>

<div id="unity-ads-metrics" />

<Accordion title="Unity Adsの指標">

**Unity Adsからパートナー指標を取得する方法：**

1. Creative Optimizationダッシュボードの右上にある⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
   <Image align="center" alt="icon for creative integrations.jpg" src="https://files.readme.io/5af3cc395743cf305a9d19dca41dc53c7cbf82e18434d2eb335c9e58a4245456-21366803702033.jpg" />
2. **+新規連携**をクリックします。
3. ドロップダウンリストの**パートナー**で**Unity Ads**を選択します。  
   <Image align="center" alt="New integration - Unity Ads.jpg" src="https://files.readme.io/8a03c4b50287768cd95217af142ec551c8526b2cf5f7f7af06c04704a868093d-18564745005073.jpg" />
4. 連携に使用するUnityの**キーID**、**シークレットキー**、**組織コアID**を入力します（取得方法は<Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-partner-integrations#unity-ads">Unity連携</Anchor>の手順を参照してください）。
5. **パートナー指標**セクションで、Unityの**APIキー**と**組織ID**を入力します。これらの認証情報は、以下の手順に従って取得できます。**注意：** ROI360コストをUnity Adsと連携している場合、そこから認証情報を取得することも可能です。
   * **APIキーを取得する方法：**
     1. Unityゲーミングサービスプラットフォームにログインします。
     2. サイドメニューの**Products**をクリックし、**Grow**をクリックします。  
        <Image align="center" alt="Unity Org ID step 1.jpg" src="https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg" />
     3. **Unity Ads User Acquisition**をクリックします。  
        <Image align="center" alt="Unity Org ID step 2.jpg" src="https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg" width="312px" />
     4. **API management**を選択します。  
        <Image align="center" alt="Unity-from API mngmt, get API key w arrow.jpg" src="https://files.readme.io/c617593d5935fbe8072d9fac0146fb3257c395c8dcf173130b97cc2a4a043285-20348783332881.jpg" />
     5. APIキーをコピーします。
   * **組織IDを取得する方法：**
     1. Unity Ads管理画面サイドメニューの**Products**をクリックし、**Grow**をクリックします。  
        <Image align="center" alt="Unity Org ID step 1.jpg" src="https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg" width="583px" />
     2. **Unity Ads User Acquisition**をクリックします。
     3. <Image align="center" alt="Unity Org ID step 2.jpg" src="https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg" width="336px" />
     4. **設定**をクリックしてください。  
        <Image align="center" alt="Get Organization ID instructions 2 arrows.jpg" src="https://files.readme.io/7514d25a8c9a7a9f64e7e5b6f9008c649cb949eff7d25c49a1693f806518e07d-20348948474897.jpg" />
     5. **組織ID**をコピーします。

<div id="note" />

> 📘 **注意**
>
> 新しいパートナー連携を設定する際に、パートナー指標の認証情報を入力することをお勧めします。ただし、必須ではありません。連携を保存し、後で認証情報を追加することができます。ただし、取得されるパートナーデータは、パートナー連携の作成時点を基準とする90日分です。パートナー指標の認証情報を入力しないと、データが欠落する可能性がある点に注意してください。

</Accordion>

</Accordion>

<div id="save-and-share-views" />

<Accordion title="ビューの保存と共有">

フィルターを選択したら、フィルター設定を保存して、見たい情報にすばやく簡単にアクセスできますので、ログインするたびにディメンションやフィルターを再選択する必要はありません。保存したビューは、Creative OptimizationのオーバービューダッシュボードとDiscoveryダッシュボードの両方に適用されます。ダッシュボードビューは、プライベートまたは共有として保存できます。共有ビューは、同じアカウント内のほかのユーザーも閲覧できます。さらに、共有URLを使用してダッシュボードビューを他のユーザーと共有できます。

**注意：** ダッシュボードを保存せずに管理画面の設定を変更した場合は、現在のビューの横にオレンジ色のインジケータドットが表示されます。

<div id="save-private-dashboard-view" />

#### **プライベートダッシュボードビューの保存**

**自分だけが閲覧できるプライベートダッシュボードビューを保存するには：**

1. 現在表示されている管理画面の上部にあるドロップダウンアイコンをクリックし、メニューにプライベートアイコンが選択されていることを確認し、**+新しいプライベートダッシュボードとして保存**をクリックします。  
   <Image align="center" alt="" src="https://files.readme.io/c1ed2ac6917fa105641f054623ad87a562f4b80042379301c8736bffaa57a22e-25381406386065.png" />
2. ダッシュボード名を入力し、**保存**をクリックします。
3. メニューアイコンを使用して、ダッシュボードビューを編集および削除したり、共有設定をプライベートから共有に変更したり、ログイン時に表示されるデフォルトのビューとしてスターマークを付けたりすることができます。

<div id="save-shared-dashboard-view" />

#### **共有ダッシュボードビューの保存**

**同じアカウント内のほかのユーザーも閲覧できる共有ダッシュボードビューを保存するには：**

1. 現在表示されている管理画面の上部にあるドロップダウンアイコンをクリックし、メニューに共有アイコンが選択されていることを確認し、**+新しい共有ダッシュボードとして保存**をクリックします。  
   **![](https://files.readme.io/d4a7f206d49ddea230883ee6e119caab119164fa3bee9d0c3f02d487c9cf8a36-25381406390033.png)**
2. ダッシュボード名を入力し、**保存**をクリックします。  
   ビューが保存され、アカウント内のほかのすべてのユーザーのダッシュボードビュー一覧に表示されます。
3. メニューアイコンを使用して、ダッシュボードビューの編集・削除、共有からプライベートへの切り替え、ログイン時に表示するデフォルトビューとしてのスター設定を行えます。

<div id="share-view-url" />

#### **ビューURLの共有**

**別のアカウントユーザーと共有URLを共有するには：**

* ダッシュボード右上のアイコンをクリックしてページのURLをコピーし、共有します。  
  <Image align="center" alt="Copy_page_URL_with_cursor.jpg" src="https://files.readme.io/2d1cc2f9585850c1d9c723f959be96e953fe6cc90b6b2a31ac8c16bf4e7b4b8f-18564702245777.jpg" width="121px" />
  **注意**：プライベートダッシュボードのビューURLも共有できます。プライベートダッシュボードのURLを開くと、レポート名は「未保存レポート」と表示されます。

</Accordion>

<div id="custom-tags" />

## カスタムタグ

アップロードしたタグ、あるいはファイル名に保存されているユニーク識別子に基づいて、クリエイティブをグループ化、あるいは分析します。このセクションでは、カスタムタグを作成する方法を説明します。カスタムタグはディメンションとしてフィルターで選択し、ダッシュボード全体で表示できます。

<div id="custom-dimensions" />

<Accordion title="CSVによるカスタムタグ">

ダッシュボードにカスタムディメンションを追加できます。カスタムディメンションと、関連するタグが付いたクリエイティブは、CSVファイルを使って追加し、各キャンペーンで使用されている既存のクリエイティブと対応づけます。この機能を使って、お好きなカスタムディメンションやタグでクリエイティブを表示、整理、並べ替え、絞り込みできます。

<div id="create-and-manage-custom-dimensions" />

<Accordion title="カスタムディメンションの作成・管理">

カスタムディメンションの作成と管理のプロセスには、以下の3つの操作が必要です：

1. Creative Optimizationダッシュボードから、現在のクリエイティブを含むCSVファイルをダウンロード
2. 新規ディメンションの作成、または現在のディメンションとタグの変更を行います。 CSVファイルの各列見出しは、カスタムディメンションの名前です（例えば、「色」）。この列のすべてのクリエイティブにはカスタムディメンションのタグが付けられ、ダッシュボードではこのタグの下に表示されます。このCSVファイルを使用して、カスタムディメンションやタグを追加・変更することができます。**注意**：新しいCSVに以前作成したカスタムタグやディメンションを含める必要はありません。編集・追加するものだけを含めてください。
3. 更新したCSVファイルをCreative Optimizationダッシュボードにアップロードします。データは約30分後に利用可能になります。

このCSVファイルのダウンロードとアップロードの手順は以下の通りです：

**ダッシュボードから現在のクリエイティブのCSVファイルをダウンロードする方法：**

1. ダッシュボード右上の<Image alt="3_dots_icon.png" src="https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png" width="16px" />メニューをクリックします。  
   <Image align="center" alt="Main menu highlighted.jpg" src="https://files.readme.io/be14a3ab1a9aba6dc20816e53ad692b1697d15a185053cf523d2ae8451842350-21367268248465.jpg" />
2. **カスタムタグファイルのダウンロード**をクリックします。
3. ファイルに含めるクリエイティブを選択します（すべてのクリエイティブ、または現在ダッシュボードに表示されているもののみ。フィルターで除外されたクリエイティブは含まれません）。
4. **ダウンロード**をクリックしてください。

ファイルに必要な追加や変更を加えて保存し、ダッシュボードにアップロードします。

**CSVファイルをCreative Optimizationダッシュボードにアップロードするには：**

1. ダッシュボード右上の<Image alt="3_dots_icon.png" src="https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png" width="16px" />メニューをクリックします。
2. **カスタムタグファイルのアップロード**をクリックします。
3. アップロードするファイルを選択します。  
   CSVファイルをアップロードする前に、[特性と制限](/docs/creative-optimization-guide#traits-and-limitations)をすべて確認してください。
4. **ダッシュボードにアップロード**をクリックします。

データは約30分で利用可能になります。

</Accordion>

<div id="example-csv" />

<Accordion title="CSVの例">

ダッシュボードからダウンロードしたカスタムディメンションのCSVファイルの例を示します。各列の見出し（1行目）は、カスタムディメンションの名前です（例：「テーマ」や「バリエーション」）。ディメンションを追加したり、既存のディメンションを変更したりすることができます。タグを追加または変更することもできます（例：「3 Moves」または「DarkPalette」）。

<Image align="center" alt="Screen_Shot_2022-08-08_at_16.25.23.png" src="https://files.readme.io/33137d3c8eab51069a3863a2af193d2192cd28546442abcaf8b74073e737c63e-18564702296977.png" />

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="カスタムディメンションの特徴と制限">

* カスタムディメンションは、フィルターと表に「カスタム」タグ付きで表示されます。

<Image align="center" alt="Custom_tag.png" src="https://files.readme.io/f8003396943a406dec2b825f4a4725aeb2f0ea3b23f3c67643cc0c096321b401-18564730363025.png" width="477px" />

* Creative Optimizationダッシュボードには、最大15個のカスタムディメンションを追加できます。
* アップロードできるファイルサイズは1MBまでです。
* 既存のディメンションとタグ名は、CSVファイルを更新して再アップロードすることで変更できます。**注意：** ファイルのアップロードごとに更新または追加できるディメンションは1つだけです。
* CSVファイルで定義されたカスタムディメンションは、アカウントレベル、つまりすべてのアプリとユーザーに適用されます。
* 各クリエイティブに設定できるタグは、1ディメンションにつき1つです。たとえば、「カラー」がカスタムディメンションである場合、タグは赤などの1色のみです。
* カスタムディメンションを作成・編集する場合は、上書きや齟齬を避けるため、creative\_idを変更しないようにしてください。

</Accordion>

</Accordion>

<div id="name-convention-tags" />

<Accordion title="命名規則に基づくタグ">

カスタムタグは、クリエイティブアセットの命名規則に基づいて作成できます。これらのカスタムタグは、フィルターで選択してダッシュボード全体で表示できるディメンションとして表示されます。

これは、クリエイティブに意図的に名前を付け、名前にユニークな識別子を組み込んでいるマーケティングチームやクリエイティブチームに役立ちます。ファイル名に含まれる識別子に基づいて自動的にタグを付け、分析や最適化のためにグループ化できます。

<div id="create-and-manage-name-convention-tags" />

<Accordion title="命名規則に基づくタグの作成・編集">

**命名規則に基づくタグを作成するには：**

1. ダッシュボード右上の⋮アイコンをクリックし、**命名規則に基づくタグ**を選択します。  
   **命名規則に基づくタグの管理**ウィンドウが表示されます。  
   <Image align="center" alt="Name convention tags main window.jpg" src="https://files.readme.io/e59721daabccd23ae7735d3e8cca68194983a3c28453daf00bf0ab39ad76fa98-18564727397393.jpg" width="795px" />
2. **新しい命名規則タイプの作成**で、詳細を入力します：
   * **名前**－新しい命名規則タイプに一意の名前を付けます。
   * **区切り文字**－各部分を区切る文字です。例えば、「enUS\_bluegalaxy\_launch.mp4」というクリエイティブでは、各セクションが「\_」で区切られています。「\_」が区切り文字です。
   * **セクション数**－たとえば「enUS\_bluegalaxy\_launch.mp4」というクリエイティブ名には、「\_」で区切られた部分が3つあります。  
     **注意：** ファイルの種類はタグに含まれません。
   * **アプリ**（任意）-すべてのアプリを含めることも、特定のアプリに関連するクリエイティブにのみタグを制限することもできます。
   * **メディアソース**（任意）-すべてのメディアソースを含めることも、特定のメディアソースで実行されるクリエイティブにのみタグを制限することもできます。
3. カスタムタグの詳細を追加します：
   * **セクション番号** -作成したいタグのセクション番号を選択します。
   * **カスタムタグ名** - **＋新しいカスタムタグの作成**をクリックして名前を作成するか、既存の名前を選択します。
   * **形式**－表・ダッシュボードでのタグの表示形式を、大文字、小文字、元の表記（クリエイティブ名で使用されている表記）から選択します。  
     **＋カスタムタグを追加**をクリックすると、カスタムタグを追加できます。
4. 保存前に**プレビューファイルをダウンロード**をクリックすると、カスタムタグがクリエイティブにどのように適用されるか確認できます（任意）。これにより、作成している命名規則タイプに合致するすべてのクリエイティブのファイルがダウンロードされ、新しいタグに従ってタグ付けされます。
5. **保存**をクリックします。  
   数時間以内にタグが適用され、ダッシュボードで利用できるようになります。

**命名規則に基づくタグを編集するには：**

1. 管理画面の右上にある  ⋮ アイコンをクリックし、**命名規則に基づくタグ**を選択します。
2. **命名規則タイプの編集** ドロップダウンをクリックして選択します。
3. 必要な変更を行い、**保存**をクリックします。

**命名規則タイプを削除する方法：**

1. **命名規則タイプの編集** ドロップダウンをクリックして、削除したい命名規則タイプを選択します。
2. 選択項目の右側にカーソルを合わせると表示される<Image alt="Delete icon.jpg" src="https://files.readme.io/a4bb54fefcdd474edbb897dc334b8219c36273fd5e4f45a03e1b39091856e137-18564742905873.jpg" width="19px" />アイコンをクリックします。  
   **注意：** 関連するカスタムタグは、クリエイティブに適用されなくなります。なお、変更が反映されるまでに数時間かかる場合があります。

<div id="name-tag-traits-and-limitations" />

<Accordion title="名前タグの特徴と制限">

* 最大10種類の命名規則タイプ（および関連するカスタムタグ）を作成できます。
* CSVファイルでアップロードしたカスタムタグが、作成した命名規則に基づくタグと競合する場合、CSVのタグが優先され、そのタグだけが適用されます。

</Accordion>

</Accordion>

</Accordion>

<div id="additional-information" />

## 追加情報

<div id="h_01HA282W8WHHNDG75XZNSV2QQF" />

<Accordion title="特性と制限">

| 項目 | 備考 |
| --- | --- |
| データソース | Creative Optimizationダッシュボードのパフォーマンスデータ（パートナー指標を除く）は、AppsFlyerのアトリビューションモデルに基づきます。**注意：** 様々な広告プラットフォームやモバイル広告エコシステムのプレーヤーによって使用されるアトリビューションモデルには固有の違いがあり、それが各社間のレポートの相違を引き起こす可能性があります。 |
| 複数のアセット | 複数のアセットを含むクリエイティブでは、1つのアセットのみが表示されます（該当する場合、通常は動画となります）。 |
| データの更新頻度 | Creative OptimizationのオーバービューダッシュボードとDiscoveryダッシュボードは、毎日10:00（UTC）に1回更新されます（過去90日間のクリエイティブデータを更新）。<br /><br />タイムゾーンごとの日次更新時刻は以下のとおりです。<ul><li>ニューヨーク：午前5:00（EST）／午前6:00（EDT）</li><li>ベルリン：午前11:00（CET）／正午12:00（CEST）</li><li>上海：午後6:00（CST）</li></ul>その他の地域では、10:00（UTC）を現地のタイムゾーンに換算してください。<br /><br />**注意：** Creative Optimizationのデータは1日1回更新されますが、AppsFlyerのメインのオーバービューダッシュボードはリアルタイムで更新されるため、一時的に差異が生じる場合があります。 |
| 通貨 | Creative Optimizationにおける金銭的指標はすべてUSDです。 |

</Accordion>

<div data-zendesk-anchors="overview=creative-optimization%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H7SZ8R9ZWZ81WHV26P00YAYP=creative-optimization%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 creative-assets=%E3%82%AF%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E3%82%A2%E3%82%BB%E3%83%83%E3%83%88 01H7SZ8RA14Q5D32EY5J0WMVYA=%E3%82%AF%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E3%82%A2%E3%82%BB%E3%83%83%E3%83%88 01H7SZ8RA1C863VRG1P10CJHTR=supported-asset-types h_01HMXES26N1X3KAFRKKCC9NFXW=%E6%B3%A8%E6%84%8F 01H7SZ8RA1D9JVG1145CAXEZFX=matching-creatives 01H7SZ8RA191221K683N1Z9R69=measuring-creatives-with-multiple-assets 01H7SZ8RA1KRPFF9AW5P4QKQXH=%E4%BE%8B creative-dashboard=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95 01H7SZ8RA1JX2TCQHB5XW21EK8=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95 01H7SZ8RA1ATSBZPMFJC0T7HRG=filter-bar 01H7SZ8RA1RT91HKKD0R93T2TA=view-type h_01HJDKZWTQVTPSJXP2HWSMD8W6=creative-optimization-roi360 h_01H9JS005MCGMPJM7NYTW2HCAF=standard-metrics-and-dimensions 01H7SZ8RA222QS1AXDKT49DEK3=unique-metrics-and-dimensions 01H7SZ8RA23SCGJ435B4V32CP1=custom-metrics 01H7SZ8RA2R9N2NC6JXNZZ7C5Z=partner-dimensions-and-metrics partner-table=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E6%8C%87%E6%A8%99%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 01H7SZ8RA2VJ9466WSMN3WHR90=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E6%8C%87%E6%A8%99%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 01H8GHNPQKS7REZ9RPH0ZYEBHE=applovin-metrics 01H8GHNPQKCKMDS8AYETEDDZKH=google-ads-metrics 01H8H1GTRV7VNJDKFEF35HCNKY=meta-ads 01H7SZ8RA28T63K3NASWC92R0F=unity-ads-metrics 01H7W4JTRSJJ2R45JQVYHMYGX2=%E6%B3%A8%E6%84%8F-1 01H7SZ8RA3TPD6ED2HJZGTVRMS=save-and-share-views save-private-dashboard-view=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%99%E3%83%BC%E3%83%88%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%83%93%E3%83%A5%E3%83%BC%E3%81%AE%E4%BF%9D%E5%AD%98 h_01HYT77DSHZ6FE0MSQS83FRGW0=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%99%E3%83%BC%E3%83%88%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%83%93%E3%83%A5%E3%83%BC%E3%81%AE%E4%BF%9D%E5%AD%98 save-shared-dashboard-view=%E5%85%B1%E6%9C%89%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%83%93%E3%83%A5%E3%83%BC%E3%81%AE%E4%BF%9D%E5%AD%98 01HYT89BRYKRG44AT9MZWKZJNY=%E5%85%B1%E6%9C%89%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%83%93%E3%83%A5%E3%83%BC%E3%81%AE%E4%BF%9D%E5%AD%98 share-view-url=%E3%83%93%E3%83%A5%E3%83%BCurl%E3%81%AE%E5%85%B1%E6%9C%89 h_01HYT8GXVJV8Q6GKBDHTTJ1SM2=%E3%83%93%E3%83%A5%E3%83%BCurl%E3%81%AE%E5%85%B1%E6%9C%89 custom-tags=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%BF%E3%82%B0 h_01H9J4Z9V9SJBTE63C358FME95=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%BF%E3%82%B0 h_01H9J4R9MTMGF9F1PNZRT2QZ1W=custom-dimensions 01H7SZ8RA3GW927GJBKKR4582T=create-and-manage-custom-dimensions 01H7SZ8RA3P8VQFH268G453FKM=example-csv 01H7SZ8RA307CBMA0533M3VGWK=traits-and-limitations h_01H9J67GSXXZ20W56NDVW2XDJC=name-convention-tags h_01H9J6PCQNVAB88ZCKRT3MVJEH=create-and-manage-name-convention-tags h_01H9J6PCQN6MV2KPYNFF7SB44Q=name-tag-traits-and-limitations additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01J1VPMV85CT5ZJNN3BW4FCW0D=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1" />

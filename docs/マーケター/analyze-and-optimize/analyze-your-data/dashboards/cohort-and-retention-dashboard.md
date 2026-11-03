---
title: コホート & リテンションレポート
metadata:
  keywords:
    - Cohort
    - Cohort Report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2015-12-24T10:20:01Z'
  edited_at: '2026-10-14T09:38:55Z'
  id: 207040496
  locale: ja
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ja/articles/207040496
---
> **概要：概要：コホートとリテンションのダッシュボード（単に「コホート」とも呼ばれます）は、アプリユーザーを獲得日ごとにグループ化します。ユーザーのライフサイクル（LTV）全体にわたってパフォーマンス分析を実行します。このダッシュボードを使用することで、キャンペーン設定の違いがキャンペーン成果にどう影響するかインサイトを得ることができます。**

cohort main (2).png

## コホート & リテンションレポート

関連記事： <Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview#cohort-flavors">コホート機能の違い</Anchor>

コホートとリテンションを使用するには、1つ以上のアプリからユーザーを選択し、コンバージョン時間で分割します。収益、ROI、イベントコンバージョン率などのコホート指標が利用可能です。比較分析のために、コホートをキャンペーンまたはメディアソースなどのディメンション別に分類します。これにより、ユーザーやキャンペーンのライフサイクルについてのパターンや変化を明らかにできます。<Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">コホートのユースケース</Anchor>をご覧ください。

> 👍 **ヒント**
>
> コホートレポートについてもっと知りたいですか？クイックに重要なポイントを押さえた<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7804/play/18625/your-users-journey-with-retention-and-cohort-reports">AppsFlyerラーニングポータルコース</Anchor>をご覧ください。

## コホートを使用する

<div id="setting-up-an-analysis" />

<Accordion title="分析の設定">

1. AppsFlyerのサイドメニューから、**分析**>**リテンション**を選択します。  
   コホートダッシュボードが開きます。粒度とコンバージョン日の範囲が表示されます。  
   ![mceclip0__1_.png](https://files.readme.io/4113fd619422979d6a26004a55c009ebc48eef59d10ddc7c3e5becd2a758e6d4-32127949494417.png)
2. [コホート期間の粒度](/docs/cohort-and-retention-dashboard#cohort-periods)を選択します：
   * 時間別
   * 日数
   * 週別
   * 月
3. 計測期間（ユーザー獲得またはリターゲティングエンゲージメント）を設定します。最新の日付に関連するデータは、グラフと表では点線で表示され、[部分的なデータ](/docs/cohort-and-retention-dashboard#partial-data)が含まれる可能性があります。
4. [**コホートの編集**] をクリックします。  
   コホート設定ウィンドウが開きます。   
   <Image alt="CohortSetup.jpg" src="https://files.readme.io/f09cc190770d16a2ddf60e1f210f458114ac43d4c19fc5507fb50b0d1d2f5c77-32127949495825.jpg" width="365px" />
5. 以下を完了してください。
   * * **ユーザー獲得**
     * **リターゲティング**
     * 統合全体：ユーザー獲得計測とリターゲティング計測の両方のアプリ内イベントが含まれます。　**注：** 注：リターゲティングイベントは、ユーザー獲得イベントよりも優先されます。つまり、レポートには、is\_primary\_attribution=true となるイベントが含まれます。
   * トレンドタイプ
     * **ユーザーライフタイムパフォーマンス：**
     * **継続時間毎のKPI：**
   * データ対象のアプリは1つ以上選択可能です。**すべて**は、アカウント内の上位 100 個のアプリを意味します。　**注：** 注：代理店アカウントでは1つのアプリのみを選択できます。
   * グループ化  Media source
   * 最小コホートサイズこれにより、重要でない（小さな）コホートでレポートが乱雑になるのを防ぎます。
   * オプションのフィールド：
     * デフォルトのフィルタはありません。
6. **変更内容を保存**をクリックします。
7. コホート分析を実行する指標（KPI）を選択します。アプリ内イベントの場合、アプリ内イベントと指標を選択します。
8. データを表示するコホート期間を選択します。つまり、コンバージョン後の時間、日、週、または月を意味します。選択できるコホート期間の数は、選択したトレンドタイプによって異なります。
9. **部分的なデータ**を含めるか、**完全なデータ**（すでに終了したコホート期間のデータ）のみを表示するかを選択します。詳しくは、部分的なデータと完全なデータについての記事をご覧ください。
10. **累積**もしくは**日毎**（時間毎 / 日毎 / 週毎 / 月毎）のデータを表示するかを選択します。
    * "累積"
    * On day（当日）日毎： その日に発生した指標の値のみを表示します。つまり、コホート3には、コホート期間 3 のメトリックのみが表示されます。前の期間に何が起こったかは表示していません。
11. **ヒートマップ**を表示するかどうかを選択します。
12. データを表とグラフのどちらで表示するかを選択します。テーブルを選択した場合は、表示するデータの行数を 25、50、100、または 200 から選択できます。
13. [オプション] [保存されたコホートレポートを管理します](/docs/cohort-and-retention-dashboard#using-my-reports-save-and-select-reports)。

</Accordion>

<div id="using-my-reports-save-and-select-reports" />

<Accordion title="マイレポートの使用—レポートの保存と選択">

* マイレポートでは、現在の管理画面の設定を今後の使用のために保存できます。
* 保存されたレポートを選択すると、利用可能な最新のコホートデータが表示されます。
* 複数のレポートを保存できます。
* マイレポートにアクセスできるのは自分だけです。

| 機能 | 説明 |
| --- | --- |
| マイレポート | ![MyReports.png](https://files.readme.io/8f49c0e6dee55427bf3a64149ac48f67547967b8cd24aa8de3e34b760708f992-32127933340305.png)<br /><br />利用可能な最新のデータを表示するには、レポートを選択します。 |
| 変更を保存する | レポートを保存します。注記：注：現在選択されているレポートが上書きされます。 |
|  | <ul><li>**新しく保存**<ul><li>別のレポート名を使用してレポートを保存します</li><li>[オプション] このレポートをデフォルトのレポートにする</li></ul></li><li>名前を編集</li><li>コホートを開くとこのレポートが最初に表示されます。</li><li>**削除：**</li></ul> |

</Accordion>

<div id="export-the-cohort-to-a-csv-file" />

<Accordion title="コホートをCSVで出力">

* コホートレポートはCSVファイルに出力できます。
* [partial という接尾辞を持つ列の名前は、管理画面上のグラフや表では点線で表示される部分に相当します。](/docs/cohort-and-retention-dashboard#partial-data)

**コホートレポートをCSVファイルにエクスポートする方法：**

* コホートレポートがCSVファイルでダウンロードされます。

</Accordion>

## コホートの概念

<div id="cohort-periods" />

<Accordion title="コホート期間">

コンバージョンしたその期間は '0' (Hour 0, Day 0, Week 0, Month0）となります。コンバージョン後の次の期間は '1' (Hour 1, Day 1, Week 1, Month 1）となります。

使用可能な期間の数は、選択した期間の粒度によって異なります。

* 時間の粒度の場合：コンバージョン後の時間の最大時間数は、72時間目までです。
* 日単位の場合：コンバージョン後の最大日数は、180日目までです。
* 週の粒度の場合：コンバージョン後の最大の週数は、156周目までです。
* 月の粒度の場合：コンバージョン後の最大の月数は、36か月目までです。

**注：** 注意：AppsFlyerでは、コホート期間は特定のインストールタイムスタンプを考慮していません。代わりに、コホート時間は最も近い時間に切り捨てられ、コホートの日、週、月は暦日、週、または月に基づいています。これにより、AppsFlyerのコホートデータと、すべてのコホート期間が特定のインストールタイムスタンプによって決定される他のネットワークのコホートデータ（つまり、1時間はインストール後60分のタイムスタンプ、1日はインストールタイムスタンプから24時間後のタイムスタンプなど）と比較すると、不一致が生じる可能性があります。

</Accordion>

<div id="view-types" />

<Accordion title="表示タイプ">

コホートビューには3つのタイプがあります：

* **統合：**
  * ユーザー獲得とリターゲティングキャンペーンを組み合わせたパフォーマンス（コストと収益を含む）。
  * イベントが両方のコンバージョンタイプにアトリビューションされる場合、リターゲティングイベントのみが含まれます。つまり、レポートは実際にラストタッチがあったメディアソースを使用して生成されます。ローデータにおいては、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor> というパラメーターが付いているイベントを意味します。
* **ユーザー獲得：** ユーザー獲得： 新規インストールのパフォーマンスデータ（<Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls#attributed-to-the-first-install">特別に有効</Anchor>にしない限り、再インストールは除外されます）
* **リターゲティング：リターゲティング：リアトリビューションまたはリエンゲージメントからのパフォーマンスデータ**

[![OV.png](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)

</Accordion>

<div id="trend-types" />

<Accordion title="トレンドタイプ">

コホートのトレンドには2つのタイプがあります：

* **LTVベース**
* **計測日ベース**

#### **LTVベース**

* 表またはグラフの各列は、別のコホート期間（時間 / 日 / 週 / 月）を表します。これにより、コンバージョン後のユーザーのパフォーマンスを、コンバージョン期間から比較できます。
* データを取得するコホート期間を、粒度オプション（時間 / 日 / 週 / 月）ごとに最大値まで選択できます。

#### **計測日ベース**

* 表またはグラフの各列は、選択した日付範囲の期間のコホート期間（時間 / 日 / 週 / 月）を表します。これにより、長期にわたるキャンペーンのパフォーマンスを分析し、コンバージョン時間に対するキャンペーンKPIを表示できます。
* データを取得するために選択できるコホート期間の最大数は '5' です。
* データを表ではなくグラフとして表示することを選択した場合、グラフには 1 つのコホート期間（選択した最も低い期間）のみが表示されます。

#### 例：

この例では、同一のローデータを使用して2つのコホートトレンドタイプを生成しています。ローデータのテーブルには、A, B, C, Dというそれぞれ違うユーザに関連するアトリビューションイベントが含まれています。ユーザーは、広告に接触し、アプリをインストール、そして購入をしています。コホート0日はインストール日です。

[![CohortExample_en-us.jpg](https://files.readme.io/7542605e2bb3972dc90fb12c9d6a328ff52ec65f0694a79752380d548e72e286-32127949500817.jpg)](https://files.readme.io/7542605e2bb3972dc90fb12c9d6a328ff52ec65f0694a79752380d548e72e286-32127949500817.jpg)

</Accordion>

<div id="partial-data" />

<Accordion title="部分的なデータと完全なデータ">

コンバージョンデータ範囲内の特定日について、コンバージョン日から経過日数がコホート日よりも少ない場合、そのコホート日には部分的なデータが含まれます。つまり、部分的なデータは、コホート日が、現在の日からコンバージョン日を差し引いた日よりも少ないときに発生します。

部分的 / 完全データのコントロール設定を使用して、データの表示モードを選択します：

* [デフォルト]**部分的：**
  * アトリビューションデータは、収益データを含み、リアルタイムで継続的に更新されます。
  * コストデータは、1日6回、平均4時間毎に更新されます。
  * 部分的なデータ（表とグラフに点線で示されています）が含まれます。
* **次の項目を入力してください：** 毎日：データは毎日更新され、深夜の数分後に利用できます。「部分的なデータ」のみを含む日のデータは表示されません。

</Accordion>

<div id="list-of-dimensions-for-grouping-and-filtering" />

<Accordion title="グループ化とフィルタリングのディメンション">

| ディメンション | 備考 | グループ化 | フィルター |
| --- | --- | --- | --- |
| <span id="ad"></span>Ad |  | ✓ | ✓ |
| <span id="ad-id"></span>Ad ID |  | ✓ | ✓ |
| <span id="adset"></span>Adset |  | ✓ | ✓ |
| <span id="adset-id"></span>Adset ID |  | ✓ | ✓ |
| <span id="agency"></span>代理店 |  | ✓ | ✓ |
| <span id="apps"></span>アプリ | レポートに複数のアプリが含まれる場合に関連 | ✓ | **x** |
| <span id="attributed-touchtype"></span>アトリビューションタッチタイプ | 値：値：クリック、インプレッション、またはNA（オーガニック） | ✓ | ✓ |
| <span id="campaign"></span>Campaign |  | ✓ | ✓ |
| <span id="campaign-id"></span>Campaign ID |  | ✓ | ✓ |
| <span id="channel"></span>Channel |  | ✓ | ✓ |
| <span id="conversion-type"></span>コンバージョンタイプ | コホートタイプに依存：<ul><li>ユーザー獲得インストール</li><li>**リターゲティング**:リエンゲージメント、再帰属</li></ul> | ✓ | ✓ |
| <span id="country-geo"></span>地理 | ユーザーIPアドレスに基づく | ✓ | ✓ |
| <span id="time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year"></span>時間。以下の場合、<ul><li>日単位の粒度は日付です</li><li>時間単位の粒度はその日の時間です</li><li>週単位の粒度はその年の週です</li><li>月単位はその年の月です</li></ul> | コホートタイプに依存：<ul><li>**リターゲティング**:リターゲティング：リエンゲージメント後にアプリが初めて起動された時間。</li></ul> | ✓ | **x** |
| <span id="install-app-store"></span>Install app store | Androidの<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution">マルチストア計測</Anchor>を実装しているアプリに関連します。 このディメンションを有効にするには、CSMまでご連絡ください。 | ✓ | ✓ |
| <span id="keywords"></span>Keywords | 連携済みパートナーが提供する検索キーワード | ✓ | ✓ |
| <span id="media-source"></span>Media source |  | ✓ | ✓ |
| <span id="revenue-type"></span>収益タイプ |  | **x** | ✓ |
| <span id="site-id"></span>Site ID |  | ✓ | ✓ |
| <span id="sub-param-1"></span>Sub Param 1 |  | ✓ | ✓ |

</Accordion>

<div id="metrics-available" />

<Accordion title="利用できる指標">

| 指標 | 説明 |
| --- | --- |
| インストール | 選択した期間内のインストール数 |
| リターゲティングのコンバージョン | 選択した期間におけるリターゲティングコンバージョン（リアトリビューションとリエンゲージメント）の数 |
| アトリビューション | 選択した期間におけるインストール数、リエンゲージメント数、リアトリビューション数 |
| コスト | <ul><li>クリックまたは／およびAPI経由でAppsFlyerにレポートされたキャンペーンコスト</li><li>次の場合は使用できません：<ul><li>表示タイプ：リターゲティング</li><li>粒度：時間（Hourly）ー</li></ul></li></ul> |
| 平均eCPI | コスト ÷ アトリビューション |
| 収益 | AppsFlyerにレポートされた収益（設定に応じて、累積または日単位） |
| 収益数 | 収益イベントが発生した回数（設定に応じて、累積または日毎） |
| ARPU | ユーザー当たりの平均収益収益 ÷ ユニークユーザー数 |
| 平均収益数 | AppsFlyerにレポートされた平均収益イベント数（設定に応じて、累積または日毎） |
| セッション数（累積） | アプリが起動された回数、デバイスのフォアグラウンドに移動した回数、または開発者が設定したその他の測定回数の累積回数 |
| 平均セッション数（累積） | アプリが起動された回数、デバイスのフォアグラウンドに移動した回数、または開発者が設定したその他の測定値のユーザーあたりの平均回数（累積） |
| セッション数（日毎） | アプリが起動された回数、デバイスのフォアグラウンドに移動した回数、または開発者が設定したその他の測定回数 |
| 平均セッション数（日毎） | アプリが起動された回数、デバイスのフォアグラウンドに移動した回数、または開発者が設定したその他の測定値（ユーザーあたりの平均回数）（日毎） |
| リテンション | リテンション率：リテンション率： 当日、アプリを起動したユニークユーザー数 ÷ コンバージョン数 × 100 |
| ROI | <ul><li>投資収益率 (%)（収益 ‐ コスト）÷ コスト x 100</li><li>次の場合は使用できません：<ul><li>表示タイプ：リターゲティング</li><li>粒度：時間（Hourly）ー</li></ul></li></ul> |
| ROAS | <ul><li>広告費回収率 (ROAS) (%)収益 ÷ コスト x 100</li><li>次の場合は使用できません：<ul><li>表示タイプ：リターゲティング</li><li>粒度：時間（Hourly）ー</li></ul></li></ul> |
| アンインストール数 | <ul><li>アプリをインストールし、後でアプリをアンインストールしたアプリユーザーの数（表示タイプ：ユーザー獲得の場合のみ表示）</li><li>次の場合は使用できません：<ul><li>表示タイプ：リターゲティングまたは全体</li><li>粒度：時間（Hourly）ー</li></ul></li></ul> |
|  | <ul><li>アプリをインストールし、後でアプリをアンインストールしたアプリユーザーの平均数（表示タイプ：ユーザー獲得の場合のみ表示）</li><li>次の場合は使用できません：<ul><li>表示タイプ：リターゲティングまたは全体</li><li>粒度：時間（Hourly）ー</li></ul></li></ul> |
| IAEカウント | アプリ内イベントが実行された回数（設定に応じて累積または日毎） |
| 平均IAEカウント | アプリ内イベントが実行された平均回数（設定に応じて、累積または日毎） |
| IAE収益 | アプリ内イベントから発生した収益（設定に応じて累積または日毎） |
| IAEの平均収益 | アプリ内イベントから発生した平均収益（設定に応じて累積または日毎） |
| IAE ユニークユーザー | アプリ内イベントを実施したユニークユーザー数（設定に応じて累積または日毎） |
| IAEコンバージョン率（累積） | アプリ内イベントのコンバージョン |
| IAEコンバージョン率（日毎） | アプリ内イベントのコンバージョン |
| eCPA | アクション (イベント) あたりの有効コスト |

</Accordion>

## 追加情報

<div id="cohort-for-agencies" />

<Accordion title="代理店アカウントのコホートアクセスについて">

* 広告主は、代理店にコホートをアクセス、使用する権限付与の必要があります。
  * 代理店に許可を与えるには、広告主は：
    1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**を選択します。
    2. 代理店を選択します。
    3. [権限]タブに移動し、[**リテンションレポートとコホートレポートへのアクセス権限付与**] をオンにします。
* 代理店は、代理店によって生成されたトラフィックのデータへのアクセスに制限されています。オーガニックトラフィックや他の場所で生成された非オーガニックトラフィックに関連するデータを表示することはできません。

</Accordion>

<div id="use-cases" />

<Accordion title="使用事例">

#### 国別の収益合計

Chart（グラフ）チャート：ユーザーごとの累積収益

Screenshot 2023-07-19 at 13.54.21.png

テーブル

cohort use case 3.png

#### アプリ内イベントのコンバージョン

広告主が アプリ内イベント af\_purchase を設定しました。コホートテーブルには、コホート内のアプリユーザーのうち、購入したユーザーの割合が表示されます。例えば、10日目には、Facebook広告のメディアソースに紐づくコホートユーザーの36.27%が購入を行ったことがわかります[。](https://support.appsflyer.com/hc/article_attachments/51444176581777)

cohort use case 3.png

</Accordion>

<div id="faq" />

<Accordion title="よくある質問">

| 質問 | 回答 |
| --- | --- |
| Apple Search Ads経由の<Anchor target="_blank" href="/marketers/ja/docs/apple-ads-integration-setup#analyze-keyword-cost">キーワードコストとROI</Anchor>を表示できますか？ | はい、可能です。  <br />Apple Search Adsは、日付ごとの各キーワードのコストを、キャンペーン、広告セット、広告の内訳で提供します。**注： 注意： 国別の内訳は利用できません。** |
| 特定のメディアソースに関して、同じキャンペーン名が複数回表示されるのはなぜですか | <ul><li>同じキャンペーン名を異なるキャンペーンIDに使用した場合、同じ名前が複数回表示されます。</li><li>キャンペーンIDごとに固有名を付ける必要があります。</li><li>キャンペーン名を変更する際に、データでは最新の名前が使用されます。</li></ul> |
| オーガニックユーザーを表示することはできますか？ | オーガニックユーザーは、デフォルトでコホートレポートに含まれます。<br /><br />**コホートレポートをオーガニックユーザーに制限する方法：**<ol><li>**コホート管理画面**にて、**コホートの編集**ボタンをクリックします。</li><li>[**変更内容を保存**] をクリックします</li></ol> |
| 削除されたインストールのデータを表示できますか？ | データリテンションポリシーや GDPRによって削除されたインストールなどは、コホートダッシュボードに表示されません。<br /><br />詳細： <Anchor target="_blank" href="/marketers/ja/docs/user-level-data-retention#パートナー別のデータ保持期間">データ保持と共有に関する制限事項</Anchor> |
| 日次ビューのデータを週次または月次ビューのデータと比較できますか？ | コホートLTVが一致しないため、日単位の粒度と週単位または月単位の粒度でデータを比較するのは簡単ではありません。 |
|  |  |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| アドネットワークのコホートへのアクセス | 利用不可 |
| 代理店によるデータアクセス | 利用可能：<ul><li>1つのアプリに限定</li><li>ハイブリッドアカウントはコホートにアクセスできません</li><li>アプリごとにアプリのアクセス許可が必要です</li><li>複数アプリの選択は不可</li><li>オーガニックデータへのアクセスは利用できません。</li></ul> |
| 代理店の運用媒体の開示設定 | 2021年1月10日より利用可能 |
| アプリ固有のタイムゾーン | <ul><li>利用可能</li><li>例外：次のすべての場合、AppsFlyerはアプリ固有のタイムゾーンを無視し、UTC +0であるデフォルトのタイムゾーンを使用します。<ul><li>コホートレポートに複数のアプリのデータが含まれている場合、それぞれのアプリのタイムゾーンが異なる場合</li><li>全てのアプリのタイムゾーンは同じだが、コホートレポート期間中に少なくとも1つのアプリのタイムゾーンが変更された場合レポートの期間の決定において：<ul><li>開始日</li><li>終了日。終了日：表示期間の日数をコンバージョン日付範囲の最後の日付に加算して計算されます。例：Jan 23, 20231-180日終了日。Jan 23, 2023</li></ul></li><li>週次および月次のデータはUTCタイムゾーンで表示されます</li></ul></li></ul> |
| コスト | <ul><li>コホートでは、関連するアトリビューション（インストール、リエンゲージメント、またはリアトリビューション）が存在する場合にのみ、コストデータが含まれます。つまり、クリックやインプレッションに基づくコストが発生しても、アトリビューションがないキャンペーンでは、そのコストはコホートレポートに含まれません。この原則は、広告階層のすべての粒度に当てはまります。</li><li>AppsFlyerは、コホートレポートまたはコホートAPIに大文字を含むキーワードのコストデータをレポートしません。</li></ul> |
| App-specific currency | <ul><li>利用可能</li><li>そうでない場合は、USDで表示されます。</li></ul> |
| CSVファイルの出力 | <ul><li>最大10,000行。</li><li>ユーザー生涯パフォーマンス（LTV）レポートでのみ使用できます。トレンドタイプが計測日ベースの場合は使用できません。</li><li>CSVエクスポートの制限は1分10件、1日100件（ユーザーあたり）です。</li></ul> |
| グラフ | グラフは、コホート内のアプリ利用者数の上位5位または10位を表示（表示されるディメンションに関わらず表示）します。 |
| テーブル | テーブルには最大200行が表示されます。インストール数、リターゲティングコンバージョン数、アトリビューション数（コホートビュータイプによって異なる）、コスト、平均eCPI（インストール単価）は、選択した指標に関係なく常に表示されます。 |
| 再インストール | <ul><li>再インストール後のイベントが未アトリビューションのオーガニックイベントと見なされる場合：<ul><li>2024年5月26日現在のみ含まれている。<Anchor target="_blank" href="/marketers/ja/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">詳細を知る</Anchor></li><li>インストール時間は<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>フィールドに基づいています。</li><li>ユニークユーザーやリテンション測定にはカウントされません。</li></ul></li><li>再インストール後のイベントが最初のインストールに起因する場合、それらは常に含まれる。<Anchor target="_blank" href="/marketers/ja/docs/unique-users">詳細はこちら</Anchor></li></ul> |
| データのクエリ | データクエリの制限は1分20回、1日500回（ユーザーあたり）です。期間、グルーピング、KPIなどの変更は、新しいクエリとみなされます。 |
| オーガニックデータ | 含まれています |
| 非オーガニックデータ | 含まれています |
| データ更新頻度 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#eod">リアルタイム</Anchor></li><li>例外：<ul><li>デイリーコホート：<ul><li>コストと広告収益、アンインストールの指標は毎日更新されます。</li><li>アンインストール数値は、UTC時間1日1回計算・更新されます。</li></ul></li><li>週別および月別のコホート：<ul><li>リアルタイムデータは利用できません。データは、完了した後（週または月末のIE）にのみ表示されます。<br />ただし、一部のデータ（インストール後の時間）が完了し、他のデータがまだ開始されていないなど、一部のインストールデータが完了したデータが表示されます。</li></ul></li></ul></li></ul> |
| 過去データ | <ul><li>デイリーコホート：2年</li><li>3年</li></ul> |
| 地理 | <ul><li>利用可能</li><li>地域が不明 (N/A) の場合、地域別にグループ化しても広告収益データは表示されません。</li></ul> |
| セッションのカウント | リターゲティング表示の0日目のセッション数は、ユーザー数よりも少ない可能性があります。<br />これにはいくつかの理由があります。最も一般的なものは以下の通りです。<ul><li>リエンゲージメントセッションは、リエンゲージメントが記録される前にすでに計測されています。この場合、リターゲティングセッションは計測されません</li><li>**最小のセッション間隔**など、その他のフィルタを使用しています。この場合、リエンゲージメントは計測されていますが、セッションはフィルタリングされ表示されません。</li></ul> |
| リターゲティングと統合データ | 月次セッションデータ：2021年9月1日以降のみ利用できます |
| 広告収益 | <ul><li>時間単位の粒度でコホートを表示する場合は使用できません。</li><li>コホート管理画面とオーバービュー管理画面に表示される広告収益額に差異がある場合があります。これは、ネットワークがUTCで収益をレポートしているのに対し、アプリのタイムゾーン設定が異なる場合に発生します。</li><li>af\_ad\_revenueイベントの場合、集計の種類が次の場合 ユニークユーザー数指標は使用できません：<ul><li>"累積"</li><li>"当日" とは、2022年10月5日から 2023年2月16日までの日付を指します。</li></ul></li></ul> |
|  | <ul><li>週と月の粒度は、コホートダッシュボードでのみ使用できます。</li><li>**ユニークユーザー**と**コンバージョン率**の指標は、データに 2022年11月より前のインストールが含まれている場合は使用できません。</li><li>過去のデータは、2021年以降のもののみ利用できます。</li><li>「2」日と「7」日に制限されています。</li></ul> |
| コホート期間 | <ul><li>コンバージョンしたその期間は '0' (Hour 0, Day 0, Week 0, Month0）となります。コンバージョン後の次の期間は '1' (Hour 1, Day 1, Week 1, Month 1）となります。</li><li>注意：AppsFlyerでは、コホート期間は特定のインストールタイムスタンプを考慮していません。代わりに、コホート時間は最も近い時間に切り捨てられ、コホートの日、週、月は暦日、週、または月に基づいています。これにより、AppsFlyerのコホートデータと、すべてのコホート期間が特定のインストールタイムスタンプによって決定される他のネットワークのコホートデータ（つまり、1時間はインストール後60分のタイムスタンプ、1日はインストールタイムスタンプから24時間後のタイムスタンプなど）と比較すると、不一致が生じる可能性があります。</li></ul> |
| アプリ内イベント名 | 推奨： |
| フィルタ |  |
| 部分的なデータ |  |
| イベント |  |

</Accordion>

<div data-zendesk-anchors="cohort-dashboard=%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88--%E3%83%AA%E3%83%86%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01H7T5AGP75A36TVWSM7H81E8P=%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88--%E3%83%AA%E3%83%86%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01H7T5AGP7SGPZNK8VTDYBTY2B=%E3%83%92%E3%83%B3%E3%83%88 using-cohort=%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B 01H7T5AGP7XDKN85TR0J4V8TP3=%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B 01H7T5AGP7FDZNVM9PDBQJPMA0=setting-up-an-analysis using-my-reports%E2%80%94save-and-select-reports=using-my-reports-save-and-select-reports 01H7T5AGP8KRZ9207DCYGRGGC0=using-my-reports-save-and-select-reports 01H7T5AGP84HVD2BQ9Z8S13D5K=export-the-cohort-to-a-csv-file cohort-concepts=%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E3%81%AE%E6%A6%82%E5%BF%B5 01H8K817ZPJTRBP1KK90FVV57T=%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E3%81%AE%E6%A6%82%E5%BF%B5 01H8K817ZPZTG476KZ83F6Z460=cohort-periods h_01JJH967X8P2NF3AFBSNMBD7B4=view-types 01H8K817ZPBVTGT5R18XGQHYT2=trend-types user-lifetime-performance=ltv%E3%83%99%E3%83%BC%E3%82%B9 01H8VNMYN0149T418BXM8RGBN9=ltv%E3%83%99%E3%83%BC%E3%82%B9 kpi-by-attribution-time=%E8%A8%88%E6%B8%AC%E6%97%A5%E3%83%99%E3%83%BC%E3%82%B9 01H8VNRGMWS8SSDM5KX08EDAS2=%E8%A8%88%E6%B8%AC%E6%97%A5%E3%83%99%E3%83%BC%E3%82%B9 example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend=%E4%BE%8B 01H8K98XE9T23QGB440GHRB8E8=%E4%BE%8B 01H7T5AGP8PN12P2C4RGGQ0R95=partial-data 01H7T5AGP8XNG1CW2FPJSEEJ45=list-of-dimensions-for-grouping-and-filtering time-in-the-case-of%0A%20%20%0A%20%20daily-granularity-is-the-date%0A%20%20hourly-granularity-is-the-hour-of-the-day%0A%20%20weekly-granularity-is-the-week-of-the-year%0A%20%20monthly-granularity-is-the-month-of-the-year=time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year 01H7T5AGP708H7JGTS1RJ07H27=metrics-available information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 01H7T5AGP8J9AQ1BREYZ0JWWZ4=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 01H7T5AGP83FRX1H9WVMS485MT=cohort-for-agencies 01H7T5AGP8JF0EAX8WEFNSEKM9=use-cases revenue-sum-by-country=%E5%9B%BD%E5%88%A5%E3%81%AE%E5%8F%8E%E7%9B%8A%E5%90%88%E8%A8%88 01H7T5AGP8R6913GPXWM6DGASF=%E5%9B%BD%E5%88%A5%E3%81%AE%E5%8F%8E%E7%9B%8A%E5%90%88%E8%A8%88 inapp-event-conversion=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 01H7T5AGP80W5J1VEZ40MHGPPF=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 01H7T5AGP85T7H25863GXJCVCW=faq 01H7T5AGP90NADB7YXTFEMTSAX=traits-and-limitations" />

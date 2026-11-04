---
title: コホートAPI
metadata:
  keywords:
    - API
    - Advertisers
    - Partners
    - Developer
    - Premium
    - Gray
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2020-01-14T07:04:32Z'
  edited_at: '2026-10-14T09:34:59Z'
  id: 360004799057
  locale: ja
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ja/articles/360004799057
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** APIを使用して、コホートデータをBI、およびマーケティングオートメーションシステムに統合できます。

<div id="filtering-and-grouping-parameters" />

<div id="cohort-api" />

## コホートAPI

コホートレポートAPIは、AppsFlyerプラットフォームからコホートキャンペーンパフォーマンスデータを取得するために使用されます。これは<Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard">コホート管理画面</Anchor>と機能的に同等です。

収益、ROI、イベントコンバージョン率などのコホート指標が利用可能です。比較分析のために、コホートをキャンペーンまたはメディアソースなどのディメンション別に分類します。結果は CSV ファイルまたは JSON ファイルとして返されます。

<Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">コホートのユースケース</Anchor>をご覧ください。

1. ![](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) alt<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">AppsFlyerAdmin\_us-en.png</Anchor> APIトークンを取得します。管理者はトークンをダッシュボードで取得する必要があります。
2. 認証ヘッダーで使用するためにAPIトークンをデベロッパーに渡します。
3. 次のセクションで説明するように、APIコールを行うときに入力するパラメーターを開発者へ渡してください。パラメーターは、レポートが何に焦点を当て、どのように編成されるかを決定し、レポートの時間枠を定義します。
4. AppsFlyer公式デベロッパーハブの <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_app-id">Master APIの手順</Anchor> に従うように開発者に伝えます。

次のフィルターパラメーターを使用して、必要なデータを取得します。

| パラメーター名 | 説明 | 必須 |
| --- | --- | --- |
| <span id="bearer"></span>Bearer \ |  | はい |
| <span id="cohort-_type"></span>cohort \_type | <ul><li>「全体」は、ユーザー獲得とリターゲティングキャンペーンのパフォーマンスを組み合わせます。</li><li>リターゲティングとユーザー獲得キャンペーンの両方にイベントの成果が紐づいている場合、返されるKPIにはリターゲティングイベントのみが含まれます。つまり、is\_primary=trueとなります。</li><li>形式：文字列</li><li>例：`"cohort_type": "user_acquisition"`</li></ul> | はい |
| <span id="min_cohort_size"></span>min\_cohort\_size | <ul><li>形式：整数</li><li>1.</li><li>デフォルト1</li><li>例：`"min_cohort_size": 50`</li></ul> | いいえ |
| <span id="from"></span>開始 | LTVアトリビューション日付期間の下限。過去データのサポート範囲は、現在から730日前までです。<ul><li>形式：String yyyy-mm-dd</li><li>例： `"from": "2020-01-02"`</li></ul> | はい |
| <span id="to"></span>終了 | LTVアトリビューション日付期間の上限。<ul><li>範囲内の日数：1～31日1-180日</li><li>形式： yyyy-mm-dd</li></ul> | はい |
| <span id="granularity"></span>granularity | <ul><li>形式：yyyy-mm-dd hh:mm:ss</li><li>例：</li></ul>`"granularity": "hour", "from": "2021-12-01 14:00:00", "to": "2021-12-03 11:00:00",` | いいえ |
| <span id="partial_data"></span>partial\_data | データの歪みや誤解釈を避けるために、コホートは完全な日のデータを返します。ただし、日数未満のデータが役に立つことがあります。<br /><br />クエリに対する完全なコホート日数は、今日の日付と *to* の日付の差として計算されます。<ul><li>[デフォルト] falseの場合、完全な日数が戻ります。</li><li>trueの場合、不完全なデータを持つ日を含む 180日までの日付が返されます。</li><li>形式：ブール値</li><li>フラットフォームUI版：false</li></ul>**例：** 例：5月10日に、4月1日～30日の間にコンバージョンがあったユーザーの完全なコホート日数は、10です。<ul><li>false の場合 [デフォルト]、コホート日数0～9日が戻ります。これは、最後のコンバージョン日から今日までの日数 (10) です。</li><li>trueの場合、コホート日数1〜40が戻ります。11～40日は一部のデータのみが含まれ、データは戻りません。例えば、4月20日以降は、20日しか経過してない、等。</li></ul>**注：** 注：部分的なデータは、集計タイプが累積的な場合にのみ許可されます。 | いいえ |
| <span id="filters"></span>フィルター | 返されたデータと期間の日数を絞り込みます。 フィルタの[ディメンション一覧](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions)からフィルタを選択します。<ul><li>形式：</li><li>**特定の地域に限定する例：**`"filters": {"geo": ["US"]}`"filters":  は米国に紐づくユーザーのみが含まれます。"filters":></li><li>設定できる値：0-180。2024-02-26</li><li>デフォルトデフォルト：期間フィルタが設定されていない場合、日数は0-30、60、90、および180が返されます。  [期間フィルタの例](/docs/cohort-api#using-period-filters)</li></ul> | いいえ |
| <span id="groupings"></span>groupings | <ul><li>グループ化を使用して、列を追加したり、レポートの粒度を低くします。</li><li>[グループ化のディメンション一覧](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions)から1～7のグループ化を選択してください。</li><li>形式：</li><li>例： `"groupings": ["af_ad", "c", "af_c_id", "af_prt"]`</li></ul> | はい |
| <span id="kpis"></span>KPI | KPIはアプリの状況を確認するための指標となります。 | はい |
| <span id="preferred_currency"></span>preferred\_currency |  | いいえ |
| <span id="preferred_timezone"></span>preferred\_timezone |  | いいえ |
| <span id="aggregation_type"></span>aggregation\_type |  | はい |
| <span id="per_user"></span>per\_user |  | いいえ |


<div id="selecting-and-formatting-kpis" />

<Accordion title="KPIの選択とフォーマット">

* この表では、利用できるKPIのリストとそれに関する関数を示しています。KPIを呼び出すとそのすべての関数が返されます。
* 次のKPIは常に返されます：users、ecpi、cost
* コールごとに追加KPIを1つ選択します。
* リクエストされた各KPIについて、全ての関数が返されます。
* 形式：
  * 例A：
  * 例B：

<table><thead><tr><th> </th><th> </th><th colspan="5">関数</th></tr><tr><th rowspan="2">デフォルト/オプション </th><th rowspan="2">KPI (ディメンション名) </th><th>カウント</th><th>cvr (コンバージョン率)</th><th>レート</th><th>合計</th><th>ユニークユーザー数</th></tr><tr><th>数値</th><th>割合</th><th>割合</th><th>数値</th><th>数値</th></tr></thead><tbody><tr><td>常に</td><td>ユーザー</td><td><span>Y</span></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>常に</td><td>eCPI</td><td>-</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>常に</td><td>cost</td><td>-</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>オプション</td><td> 2024-02-26 </td><td><span>Y</span></td><td><span>Y</span></td><td>-</td><td><span>Y (3)</span></td><td><span>Y</span></td></tr><tr><td>オプション</td><td>revenue</td><td><span>Y</span></td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>オプション</td><td>ROAS</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>オプション</td><td>ROI</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>オプション</td><td>sessions</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td><span>Y(1)</span></td></tr><tr><td>オプション</td><td>uninstalls (2)</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td colspan="7"><p>(1) <em>aggregation_type=on_day</em> の場合、ユニークセッションが返されます。</p><p>(2) cohort_type=unified の場合は利用できません。 </p><p>(3) 合計とは、イベントで発生した収益の合計を意味します。</p><p> 注意イベント名では大文字と小文字が区別されます。</p></td></tr></tbody></table>


| <span id="list-of-group-by-and-filter-by-dimensions"></span><span id="formatting-kpi-functions"></span><span id="presentation-of-kpi-functions"></span>パラメータ | 範囲外の値は | 必須 |
| --- | --- | --- |
| preferred\_currency | KPIの収益通貨<ul><li>true の場合、プラットフォーム上で設定されている<Anchor target="_blank" href="/marketers/ja/docs/app-settings#localization-currency">アプリ固有の通貨</Anchor>を使用して収益値が戻ります。</li><li>[デフォルト] false の場合、結果はUSDで返されます。</li><li>形式：ブール値</li><li>フラットフォームUI版：true</li></ul> | いいえ |
| preferred\_timezone | **データ範囲のタイムゾーン**<ul><li>trueの場合、プラットフォームで設定された<Anchor target="_blank" href="/marketers/ja/docs/app-settings#localization-time-zone">アプリ固有のタイムゾーン</Anchor>を使用して表示されます。</li><li>[デフォルト] falseの場合、UTCタイムゾーンを使用して表示されます。</li><li>形式：ブール値</li><li>フラットフォームUI版：true</li></ul> | いいえ |
| aggregation\_type | <ul><li>`cumulative`</li><li>`on_day`</li></ul>`"aggregation_type": "cumulative"`<br /><br />`Format: String` | はい |
| per\_user | KPI関数をアプリユーザー数で割ります。関連するKPIのみに適用されます。<ul><li>trueの場合、KPI値はコホートのユーザー数で除算されます。</li><li>falseの場合、KPI値はユーザー数で除算されません。</li><li>形式：ブール値</li><li>tureの場合の例：総収益が$1000で、アプリユーザー数が500の場合、値は$2で返されます。</li></ul> | いいえ |

</Accordion>

<table><thead><tr><th>ディメンション名 </th><th>ディメンションAPI値</th><th>グループ化</th><th>フィルタ</th></tr></thead><tbody><tr><td>Ad</td><td>af_ad</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Ad ID</td><td>af_ad_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Campaign</td><td>c</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Campaign ID</td><td>af_c_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Channel</td><td>af_channel</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Media Source</td><td>pid</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Sub Param 1</td><td>af_sub1</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Keywords</td><td>af_keywords</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>代理店</td><td>af_prt</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>コンバージョンタイプ (1) </td><td>cohort _type</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Site ID</td><td>site_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>収益タイプ (2) </td><td>revenue_type</td><td><span>x </span></td><td><span>Y</span></td></tr><tr><td>アトリビューションタッチタイプ (3) </td><td>attributed_touch_type</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Adset</td><td>af_adset</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Adset ID</td><td>af_adset_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>国</td><td>geo</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>日付（選択したcohort_typeのコンテキストでのインストール／リアトリビューション／リエンゲージメント日） </td><td>date</td><td><span>Y</span></td><td><span>x </span></td></tr><tr><td>期間</td><td><p>ピリオド (.)</p><p><a href="./cohort-api#using-period-filters">詳細な説明</a></p></td><td><span>x</span></td><td><span>Y</span></td></tr><tr><td colspan="4"><p>注： </p><p>ディメンションのオプション：</p><ul><li>エクスポートする場合：<ul><li> </li><li> </li></ul></li></ul><p>収益タイプ\*</p><p>attributed_touch_type</p></td></tr></tbody></table>


<div id="additional-information" />

## 追加情報

<div id="using-period-filters" />

<Accordion title="期間フィルタの使用">

期間はアトリビューション後の日を指し、期間0はアトリビューション日です。例えば、ユーザーがアプリを1月1日にインストールします。これがアトリビューション日です。期間0に購入が発生した場合、この購入は1月1日に発生しました。期間0に購入が発生した場合、この購入は1月1日に発生しました。

レポートの期間範囲が1月1日から1月11日の場合、この期間にアトリビュート（インストール）されたユーザーがレポートに含まれます。その他のデータは含まれません。

* 期間の値は、0-180のうち1つまたは複数設定できます。例：0, 1, 2, 30, 180。
* 期間が指定されていない場合、デフォルト値である0、1、2…30まで、および、60、90、180 が戻ります。

<div id="example-period-filter" />

> 📄 **期間フィルタの例**
>
> * この例には、JSONクエリパラメータ、ローデータ、および結果のCSVファイルが含まれています。
> * クエリの*フィルタ期間*は、0、1、2で、選択されたKPIは*収益*です。
> * その結果、返されるデータには以下が含まれます。
>   * ユーザー、コスト、eCPIの測定は常に返されます。
>   * 収益の測定は、各期間、つまり期間 0、1、2の合計とカウントで構成されます。
>
> **クエリ**
>
> ```json
> {
>     "cohort_type": "user_acquisition",
>     "min_cohort_size": 1,
>     "preferred_timezone": false,
>     "from": "2019-12-01",
>     "to": "2020-01-01",
>     "filters": {
>         "period": [
>             0,
>             1,
>             2
>         ]
>     },
>     "aggregation_type": "cumulative",
>     "per_user": false,
>     "groupings": [
>         "pid"
>     ],
>     "kpis": [
>         "revenue"
>     ]
> }
> ```
>
> **ローデータ**
>
> **![mceclip1.png](https://files.readme.io/846aade481d3b5fa72536817533bc3edad721f1ce6015edcb48bd500461342b9-32131110606865.png)**
>
> **結果**
>
> ![mceclip0.png](https://files.readme.io/c284e5133e4e811b9416c850e399ddefb3c5bfcfcf879f469556b7a6bc0062c6-32131110607249.png)

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| アドネットワークのアクセス | いいえ |
| 代理店によるデータアクセス | いいえ |
| 代理店の運用媒体の開示設定 | いいえ：代理店が運用するメディアソースのトラフィックは常に代理店名であり、元のメディアソースではありません。 |
| アプリ固有のタイムゾーン | はい |
| アプリ固有の通貨 | はい |
| サイズ制限 | なし |
| レート制限 | <ul><li>クエリは最大 30,000 行のデータを取得します。</li></ul> |
| オーガニックデータ | 利用可能 |
| 非オーガニックデータ | 利用可能 |
| コストデータの制限 | <ul><li>コストデータは少なくとも1つのインストールが計測されているキャンペーンのデータです。</li><li>AppsFlyerは、コホートレポートまたはコホートAPIに大文字を含むキーワードのコストデータを報告しません</li><li>コストと一部のグループ化の組み合わせができません。たとえば、Meta広告には地域グループとチャネルグループのいずれかを設定できますが、両方を含めることはできません。グループ分けの正確な組み合わせは、アドネットワークにより異なります。</li></ul> |
| データ更新頻度 | データ更新頻度は、以下の [partial\_data](/docs/cohort-api#partial_data) により異なります。<ul><li>[デフォルト] falseの場合は<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#daily">毎日</Anchor>更新</li><li>trueの場合は<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">継続的（リアルタイム）</Anchor>で更新</li><li>コストとアンインストール指標は全てのインスタンスで毎日更新されます</li></ul> |
| 過去データ | デイリーコホート：2年 |
| アカウントユーザーのアクセス | 認証トークンは、管理画面でアドミンユーザーが利用できます |
| 広告収益 | af\_ad\_revenueイベントの場合、集計の種類が次の場合 ユニークユーザー数指標は使用できません：<ul><li>"累積"</li><li>"当日" とは、2022年10月5日から 2023年2月16日までの日付を指します。</li></ul> |
|  | 週単位および月単位のディメンショングループは、コホートAPIでは使用できません。 |
|  | <ul><li>注意：AppsFlyerでは、コホート期間は特定のインストールタイムスタンプを考慮していません。これにより、AppsFlyerのコホートデータと、すべてのコホート期間が特定のインストールタイムスタンプによって決定される他のネットワークのコホートデータ（つまり、1時間はインストール後60分のタイムスタンプ、1日はインストールタイムスタンプから24時間後のタイムスタンプなど）と比較すると、不一致が生じる可能性があります。</li></ul> |
| 日付 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">日付</Anchor>：日付または日付期間は生涯価値 (LTV) の日付であり、つまりユーザーが計測された日（コンバージョン日）で、アクティビティが発生した日ではありません。</li><li>現在の日付から3-5日前（2年間）</li><li>1-180日</li></ul> |
| 再インストール | <ul><li>再インストール後のイベントが未アトリビューションのオーガニックイベントと見なされる場合：<ul><li>2024年5月26日現在のみ含まれている。<Anchor target="_blank" href="/marketers/ja/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">詳細を知る</Anchor></li><li>インストール時間は<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>フィールドに基づいています。</li><li>ユニークユーザーやリテンション測定にはカウントされません。</li></ul></li><li>再インストール後のイベントが最初のインストールに起因する場合、それらは常に含まれる。<Anchor target="_blank" href="/marketers/ja/docs/unique-users">詳細はこちら</Anchor></li></ul> |
|  |  |

</Accordion>

<div data-zendesk-anchors="cohort-reporting-api=%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88api 01H7WFZR41YAQX4MFPBMJD1MBP=%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88api 01H7WFZR42XV4JY46GY11KT3CF=selecting-and-formatting-kpis 01H7WFZR43HFF65TSWG1AN0JTB=presentation-of-kpi-functions additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HMY09W324E54VPZWPJVS2KB8=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 01H7WFZR440NTXWWQ2T4P2ANWK=using-period-filters 01H7WFZR44RCXA56CXSCEZ0KXH=%E6%9C%9F%E9%96%93%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%81%AE%E4%BE%8B 01H7WFZR45VC96KYW1W9A8PBFT=traits-and-limitations" />

---
title: ROI360の広告費集計の概要
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2015-12-24T10:45:16Z'
  edited_at: '2026-10-28T08:43:27Z'
  id: 207040526
  locale: ja
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ja/articles/207040526
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 広告主がマーケティングの広告費データを集計・確認する方法を説明します。

<div id="cost-aggregation" />

## 広告費の集計

ROI360では、次のことが可能です。

* 集計済みの広告費データと、広告費に関連する顧客生涯価値（LTV）ベースの成果指標を提供します。これらは、ダッシュボードとパフォーマンスレポートで利用できます。広告費関連の指標には、投資利益率（ROI）、広告費用対効果（ROAS）、クリック数、インプレッション数、キャンペーンROI、期間ごとの平均実効インストール単価（eCPI）があります。
* モバイルアプリ、Webブラウザー、コネクテッドTV（CTV）、PC、ゲーム機など、すべてのプラットフォームの広告費をカバーします。
* インストール単価（CPI）、アクション単価（CPA）、クリック単価（CPC）、1,000回表示あたりの単価（CPM）など、メディアソースが使用するさまざまな課金モデルに対応しています。
* API、コストインポート（CSVファイルのアップロード）、<Anchor target="_blank" href="/marketers/ja/docs/view-aggregated-cost-data-for-attribution-links">アトリビューションリンク</Anchor>を通じて広告費を記録します。
* ROI360を契約している広告主の広告費データには、代理店もアクセスできます。

ROI360を契約していない広告主も、次のデータを利用できます。

* <Anchor target="_blank" href="/marketers/ja/docs/view-aggregated-cost-data-for-attribution-links">アトリビューションリンクで送信される広告費データ</Anchor>
* 連携済みSRNパートナーの<strong>［広告費］</strong>タブで設定する、Self-Reporting Network（SRN）のクリック数とインプレッション数のデータ

<div id="principles-of-cost-data-aggregation" />

## 広告費集計の基本的な仕組み

このセクションでは、キャンペーン広告費を集計する際の基本的な仕組みを説明します。

<div id="cost-aggregation-methods" />

<Accordion title="広告費の集計方法">

AppsFlyerは、1つ以上の方法でメディアソースから広告費データを取得します。メディアソースが複数の方法で広告費を送信する場合は、[広告費データの優先順位](#cost-prioritization-mechanism)に従って、AppsFlyerで使用するデータを決定します。これにより、広告費の過大計上を防ぎます。

処理後のデータは、デフォルトのUTC、または<Anchor target="_blank" href="/marketers/ja/docs/changing-app-time-zone-settings">アプリ固有のタイムゾーン</Anchor>で表示されます。

<table><thead><tr><th>広告費の集計方法</th><th>対応する課金モデル</th><th>データの詳細度</th><th>データの更新・反映</th><th>補足</th></tr></thead><tbody><tr><td> <a href="./set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api" target="_blank">API</a>\*</td><td>すべて</td><td>連携によって異なる</td><td><a href="./about-data-freshness-and-timezone-support#intraday-during-the-day" target="_blank">1日に複数回更新</a></td><td>AppsFlyerは最大7日前までのデータの再取得を試みるため、広告費の発生後にデータが変わる場合があります（対象期間はメディアソースによって異なります）。これにより、メディアソースが過去のデータに加えた変更を反映できます。</td></tr><tr><td><a href="./import-cost-data" target="_blank">コストインポート（ファイルのアップロード）</a></td><td>すべて</td><td>アップロードしたファイルによって異なる</td><td>インポートから最大4時間</td><td>報告済み広告費の取り消しと修正データの再送信は、最大90日前まで可能です。</td></tr><tr><td><a href="./view-aggregated-cost-data-for-attribution-links" target="_blank">アトリビューションリンクで送信される広告費</a></td><td>CPI</td><td>ユーザー単位</td><td><p>最短：リアルタイム</p><p>最長：リンクのクリックから最大4時間</p></td><td>変更不可</td></tr><tr><td colspan="5">\* メディアソースとAppsFlyerのAPI連携には、広告費APIまたはInCost APIのいずれか一方を使用します。両方を同時に使用することはありません。使用するAPIと取得できるデータの詳細度は、メディアソースによって異なります。</td></tr></tbody></table>

</Accordion>

<div id="cost-data-availability-and-reports" />

<Accordion title="広告費データを利用できる画面・レポート">

このセクションの最後の表に、広告費データを利用できる画面とレポートを示します。

表の補足欄に別途記載がない限り、以下の説明が適用されます。

<div id="cost-in-the-ua-view" />

#### ユーザー獲得（UA）ビューの広告費

AppsFlyerは、以下に示すメディアソースごとの照合ルールに基づいて、キャンペーン広告費をユーザー獲得（UA）に分類します。

| メディアソース | 照合ルール |
| --- | --- |
| Google広告、DV360、Facebook、TikTok、Apple Search Ads、Aura | インストール日（メディアソースが広告費を報告する日）の前後10日間に、インストール、クリック、インプレッションのいずれかが1件以上記録されている場合、広告費をUAに分類します。 |
| その他のすべてのメディアソース | メディアソースの処理当日に、インストール、クリック、インプレッションのいずれかが1件以上記録されている場合、広告費をUAに分類します。前後10日間の期間は適用されません。 |

<div id="note" />

> 📘 **注意**
>
> この条件は、表の両方の行に適用されます。照合には、メディアソース、キャンペーンID、代理店を使用します。

<div id="cost-in-the-unified-view" />

#### 統合ビューの広告費

統合ビューには、広告費の報告日（インストール日）の前後10日間にインストール、クリック、インプレッションがあるかどうかにかかわらず、選択したアプリのすべてのキャンペーンの広告費データが含まれます。

<div id="example" />

#### 例

前後10日間の期間が、広告費の表示先にどのように影響するかを以下の例で説明します。

* 前後10日間で照合するメディアソースが3月15日にキャンペーンXの広告費を報告し、3月5日～25日にキャンペーンXのクリック、インストール、インプレッションのいずれかが1件以上ある場合、3月15日の広告費はUAビューと統合ビューの両方に表示されます。
  * その期間に対象の行動がなければ、3月15日の広告費は**統合ビューにのみ**表示されます。処理当日だけで照合するメディアソースでは、前後10日間ではなく、3月15日当日に同じルールが適用されます。

<div id="cost-data-availability-and-reports-table" />

#### 広告費データを利用できる画面・レポートの一覧

| レポート形式 | ビュー／データの種類 | キャンペーン名の変更への対応 | 補足 |
| --- | --- | --- | --- |
| Overview dashboard | <ul><li>UA</li><li>統合</li></ul> | はい | リターゲティングビューには広告費は表示されません。リターゲティングの広告費は、統合ビューに表示されます。 |
| アクティビティダッシュボード | UA | はい |  |
| コホートダッシュボード | <ul><li>UA</li><li>統合</li></ul> | はい | <ul><li>リターゲティングビューには広告費は表示されません。</li><li>Google広告、DV360、Facebook、TikTok、Apple Search Ads、Auraでは、広告費の報告日（インストール日）の前後10日間にインストール、クリック、インプレッションのいずれかが1件以上記録されたキャンペーンでのみ、この統合データを利用できます。その他のメディアソースでは、広告費と同じ処理当日に対象の行動が記録されたキャンペーンのみで利用できます。</li></ul> |
| Cohort API | <ul><li>UA</li><li>統合</li></ul> | はい | Google広告、DV360、Facebook、TikTok、Apple Search Ads、Auraでは、広告費の報告日（インストール日）の前後10日間にインストール、クリック、インプレッションのいずれかが1件以上記録されたキャンペーンでのみ、この統合データを利用できます。その他のメディアソースでは、広告費と同じ処理当日に対象の行動が記録されたキャンペーンのみで利用できます。 |
| SKANダッシュボード | SKAN | いいえ | このダッシュボードには、SKAdNetwork（SKAN）のインストール数と、SKAN以外も含む**すべての**インストールの広告費データが表示されます。 |
| SKAN Aggregated Performance API | SKAN | いいえ | このAPIには、SKANのインストール数と、SKAN以外も含む**すべての**インストールの広告費データが表示されます。 |
| ピボットダッシュボード | UA | いいえ |  |
| Master API | UA | いいえ |  |
| カスタムダッシュボード | UA | いいえ |  |
| コストETL | 統合 | はい | 取得できるすべての広告費データが表示されます。 |
| 集計データPull API | UA | いいえ |  |
| Push API | クリックのローデータ（未集計） | 該当なし |  |
| ローデータPull API | クリックのローデータ（未集計） | 該当なし |  |
| Data Locker | クリックのローデータ（未集計） | 該当なし | Data Lockerのコホートレポートは広告費に対応していません。 |

<div id="note-1" />

> 📘 **注意**
>
> この表には、以下の点が適用されます。
>
> * データの詳細度は、ダッシュボードやレポートの種類によって異なる場合があります。<Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports">コストETL</Anchor>には、すべてのデータが含まれます。メディアソース、キャンペーン名、広告、広告セットなどのキャンペーン階層の詳細と、メディアソースから取得できるディメンション（地域、チャネル、サイトID、キーワードなど）が含まれます。
> * アトリビューションリンクで送信された広告費は、ローデータレポートで利用できます。
> * メディアソースがキャンペーン名の変更に対応していない場合、アトリビューションデータを持つ名前と広告費データを持つ名前の両方が表示されます。どちらのキャンペーン名のデータを見ても、それだけでは全体像を把握できません。

</Accordion>

<div id="cost-prioritization-mechanism" />

<Accordion title="広告費データの優先順位">

1つのメディアソースから、複数の方法で広告費が提供されることがあります。広告費の過大計上を防ぐため、キャンペーンごとの優先順位に従って、管理画面に表示する広告費データを決定します。優先順位は、広告費の集計方法によって決まります。優先順位が低い順に、アトリビューションリンクの広告費＞広告費API＞コストインポートとなります。

![広告費の優先順位を低い順に示す図：アトリビューションリンクの広告費、広告費API、コストインポート](https://files.readme.io/8dbea1b8561d67f77d27cad85ab109e5203930273f32d2a9b04900b810c46ec2-25433450962577.png)

この優先順位は、集計データのレポートとダッシュボードに適用されます。前述のとおり、ローデータレポートに含まれるアトリビューションリンクの広告費には影響しません。

**確認事項**：

* 優先順位はキャンペーン単位で適用されます。 1つのキャンペーンの広告費を異なる2つの方法で取得した場合、キャンペーン全体に対して優先順位の高い方のデータが採用されます。
  * ある日付について、特定のアプリとメディアソース（または代理店）の広告費が広告費APIから取得できる場合、その日のアトリビューションリンクの広告費は使用されません。
* 広告費の集計方法を変更すると、過去のデータにも影響します。過去の集計済み広告費データが変わる場合があります。
* 広告費の集計方法の変更は、代理店経由の流入にも同様に影響します。運用媒体が開示されている代理店と、非開示の代理店の両方が対象です。

<div id="example-1" />

> 📄 **例**
>
> メディアソースがアトリビューションリンクで広告費を送信しており、そのメディアソースの広告費APIを有効にすることにした場合。
>
> **結果：** AppsFlyerは、アトリビューションリンクと広告費APIの両方から広告費を集計します。広告費APIの方が優先されるため、アトリビューションリンクの広告費は使用されません。

</Accordion>

<div id="closed-beta--cost-split" />

<Accordion title="広告費の配分">

一部のメディアソースは、アプリIDを付けずにキャンペーン広告費を報告します。その場合、AppsFlyerはエンゲージメントデータとアトリビューションデータを使って、アプリIDを補完します。

広告費の報告日の**前後10日間**に記録されたキャンペーンのクリック、インプレッション、コンバージョンに基づいて、関連するアプリを照合します。

アプリIDの補完によって複数のアプリが一致した場合、以下の方法でキャンペーン広告費を配分します。

<div id="proportional-split-by-conversions" />

#### コンバージョン数に応じた配分

広告費の報告日にコンバージョン（インストール、リアトリビューション、リエンゲージメント）がある場合、各アプリのコンバージョン数の比率に応じて配分します。

**例：** 1日目の総広告費が **$100**で、キャンペーンから**iOSで60件**、**Androidで40件のインストール**が発生した場合：

* iOS：**$60**
* Android：**$40**

<div id="note-2" />

> 📘 **注意**
>
> コンバージョン数に応じた配分が適用されるのは、アトリビューションで取得できるコンバージョンデータと、メディアソースが報告する広告費データの集計単位が、完全に一致する場合のみです。一部しか一致しない場合、AppsFlyerは広告費を各アプリのコンバージョンに紐づけられないため、一致したアプリ間で均等に配分します。

<div id="equal-split-no-conversions" />

#### 均等配分（コンバージョンがない場合）

広告費の報告日にコンバージョンがない場合、一致したアプリ間で広告費を均等に配分します。

**例：** 1日目の総広告費が **$100**で、当日にインプレッションはあるもののコンバージョンがない場合：

* iOS：**$50**
* Android：**$50**

<div id="limitations" />

#### 制限事項

この機能には、以下の制限があります。

* この機能は、Google、TikTok、DV360のクロスプラットフォームキャンペーンとWeb-to-App（W2A）キャンペーンに対応しています（キャンペーンの目的がモバイル／アプリ以外のもの）。
* **Google Performance Max（PMAX）キャンペーン**：コンバージョン数に応じた配分は適用されません。 GoogleのAPIはPMAXキャンペーンの広告ID別・地域別データを報告しないため、各アプリのコンバージョン数にかかわらず、一致したアプリ間で広告費を均等に配分します。ダッシュボードでiOS、Androidなどのすべてのプラットフォームを選択した場合、キャンペーン単位の総広告費はGoogleが報告する金額と一致します。

</Accordion>

<div id="additional-information" />

## 補足情報

<div id="ad-networks-supporting-cost-api" />

<Accordion title="広告費APIに対応するメディアソースの一覧">

以下からダウンロードできる表に、広告費APIに対応するすべてのメディアソースと、それぞれで取得できるデータの詳細度を示しています。

* ディメンション
* 対応する機能とその特徴
* 指標（メディアソースの報告値）

ファイルをダウンロード：<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=csv">CSV</Anchor>、<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=xlsx">XLSX</Anchor>

</Accordion>

<div id="changing-campaign-names" />

<Accordion title="キャンペーン名の変更">

AppsFlyerは、キャンペーンIDをキーとしてキャンペーンを表示します。

表示の不整合を防ぐため、以下を確認してください。

* 各キャンペーンに一意のキャンペーンIDがあること。
* 異なるキャンペーンIDに同じキャンペーン名を使用していないこと。

<Anchor target="_blank" href="/marketers/ja/docs/campaign-name-changes">キャンペーン名の変更について詳しくはこちら</Anchor>

</Accordion>

<div id="costs-without-installs" />

<Accordion title="インストールがない広告費">

<strong>インストールがないのに広告費が表示されるのはなぜですか？</strong>メディアソースが広告費を上位階層（キャンペーン単位など）で提供し、成果情報（クリック数やインストール数）を下位階層（広告・広告セット単位など）で提供している場合に発生します。

AppsFlyerは、情報がないディメンションの広告費を、上位階層のデータで補完します。これにより、どの階層でも広告費の全体像を確認でき、データ内の不整合を最小限に抑えられます。

<div id="example-2" />

> 📄 **例**
>
> 広告主がキャンペーンを実施しているとします。広告の階層は以下のとおりです。
>
> * **メディアソース**：media\_eg
> * **キャンペーン**：campaign\_eg
> * **広告セット**：**adset\_1**、**adset\_2**
>
> 以下の表は、このメディアソースの情報を示しています。
>
> 階層：すべてのメディアソース＞media\_eg
>
>
>
> | キャンペーン | 広告費 | インストール数 |
> | --- | --- | --- |
> | campaign\_eg | $100 | 100 |
> | campaign\_yy | $200 | 1000 |
> | campaign\_zz | $300 | 2000 |
>
>
>
> campaign\_egを掘り下げると、広告セット単位の情報が表示されます。
>
> 階層：すべてのメディアソース＞media\_eg＞campaign\_eg
>
>
>
> | 広告セット | 広告費 | インストール数 |
> | --- | --- | --- |
> | なし | $100 |  |
> | adset\_1 | N/A | 30 |
> | adset\_2 | N/A | 70 |
>
>
>
> この場合、campaign\_egの広告費$100はキャンペーン単位で表示されます。この例で最下位となる広告セット階層まで掘り下げても、AppsFlyerは広告セット別に広告費を分けられません。
>
> そのため、キャンペーン単位の広告費を別の行に分けて表示します。この行の広告セットは「なし」と表示され、インストール数のフィールドは空欄になります。

</Accordion>

<div id="cost-currency-conversion" />

<Accordion title="広告費の通貨換算">

メディアソースが提供するキャンペーン広告費の通貨が、AppsFlyerでアプリに設定した通貨と異なる場合、以下の方法でアプリの通貨に換算します。

* 為替レートは、<Anchor target="_blank" href="https://openexchangerates.org/">openexchangerates.org</Anchor>から取得します。
* 最大7日前までのデータについて、為替レートを1時間ごとに更新します。
* 最後に取得した為替レートを使用して通貨を換算します。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 説明 |
| --- | --- |
| 代理店 | <ul><li>運用媒体が開示されている代理店のキャンペーンでは、広告主のダッシュボードとレポートに広告費が表示され、一元的に確認できます。[広告費データを利用できる画面・レポートについて詳しくはこちら](#cost-data-availability-and-reports)</li><li>広告主が代理店との取引を終了し、アプリ単位で代理店の権限を無効にしても、代理店側にアプリの広告費設定が残っている場合、AppsFlyerは広告費データの取得を継続します。これを防ぐには、代理店の権限を無効にする前に、AppsFlyer上の広告費連携を無効にするよう、広告主から代理店に依頼する必要があります。</li><li>一部のメディアソースでは、連携を有効にするために代理店から広告主への連絡が必要で、AppsFlyerの画面にその旨が表示されます。これらのメディアソースでは、代理店の広告費を紐づけるために必要な`af_prt`パラメータが送信データに含まれることを、代理店と広告主の双方で確認する必要があります。</li><li>X広告では、SKANのみのキャンペーン（通常のインストールがなく、SKANインストールのみのキャンペーン）の広告費データを代理店は利用できません。広告主が広告費連携を設定する必要があります。このデータを閲覧できるのは広告主のみです。</li></ul> |
| APIデータの更新・反映 | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">1日に複数回更新</Anchor>（Molocoを除く）</li><li>Mintegralのデータは、対象日の終了から約4時間後、翌日にAPI経由で利用できるようになります。例えば、1日目に発生したイベントの広告費データは、2日目の午前4時頃までに利用できるようになります。</li></ul> |
| キャンペーン名の変更 | 広告費データには、最後に報告された最新のキャンペーン名が表示されます。これは集計データのみに適用され、ローデータ自体には適用されません。 |
| タイムゾーン | メディアソースが1つのタイムゾーンにしか対応しておらず、アプリ設定のタイムゾーンと異なる場合、メディアソースのタイムゾーンを使用します。 |
| CTV・PC・ゲーム機プラットフォーム | これらのプラットフォームのアプリでは、<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">広告費データの取り込み</Anchor>機能を使用し、メール送信でデータをインポートします。<br /><br />次のプラットフォームでは、Google、Meta、TikTokからAPI経由でデータを取得することもできます。<ul><li>Steam</li><li>Native PC</li><li>Smart Cast</li><li>Tizen</li><li>Quest</li></ul> |
| クロスプラットフォーム | インプレッションやクリックが発生したプラットフォームと、アプリがインストールされたプラットフォームが異なる場合、そのクロスプラットフォームのクリックとインプレッションの広告費データは利用できません。 |
| ストア外アプリ | ストア外アプリ（Google PlayとApp Store以外のプラットフォームのアプリ）では、Mintegralの広告費データを利用できません。 |
| 地域 | Mistplayの複数国を対象とするバンドルキャンペーンでは、地域・国別の内訳を利用できません。これらのキャンペーンでは、地域はN/Aと表示されます。 |
| Smadex | ダッシュボードとコストETLレポートで、広告費とアトリビューションのデータが別々に表示される場合があります。 SmadexがサイトIDの値にインベントリIDなどの追加情報を含める場合に発生します。 |
| Apple Search Ads (ASA) | SKANのみのレポートでは、AppleがSKANポストバックにキャンペーン単位のデータを含めないため、SKANダッシュボードやPull APIでASAの広告費データを利用できません。ただし、AppsFlyerの従来の連携を使用したSSOT（single-source-of-truth）レポートでは、広告費データを利用できます。 |
| 広告費データのディメンションの文字数上限 | 以下のメディアソースでは、次のディメンションが指定された文字数を超えないようにしてください。上限を超えた場合、そのディメンションの値はレポートから除外されます。<ul><li>`app_id`：最大100文字</li><li>`publisher`：最大250文字</li><li>`partner`：最大250文字</li><li>`campaign`：最大250文字</li><li>`campaign_id`：最大250文字</li><li>`adset`：最大250文字</li><li>`adset_id`：最大250文字</li><li>`ad`：最大250文字</li><li>`ad_id`：最大250文字</li><li>`site_id`：最大250文字</li><li>`site_name`：最大250文字</li><li>`channel`：最大250文字</li><li>`ad_account`：最大250文字</li><li>`ad_account_name`：最大250文字</li></ul>これらの制限は、次のメディアソースにのみ適用されます。<ul><li>`mintegral_int`</li><li>`moloco_int`</li><li>`applovin_int`</li><li>`liftoff_int`</li><li>`aura_int`</li><li>`tiktokglobal_int`</li><li>`pinterest_int`</li><li>`vungle_int`</li><li>`iossearchads_int`</li></ul> |
| API広告費データの利用条件 | API経由の広告費データは、ROI360の利用権が有効なお客様にのみ表示されます。 ROI360が無効になると、API経由の広告費データは利用できなくなり、ダッシュボードにはCPIベースの広告費データのみが表示されます。 |
| Mintegralの広告単位のデータ | Mintegralから広告単位の広告費レポートを取得するには、各広告アカウントにアドネットワーク側の**Sub/Package × Creative dimension**の権限が必要です。 |

</Accordion>

<div data-zendesk-anchors="cost-aggregation=%E5%BA%83%E5%91%8A%E8%B2%BB%E3%81%AE%E9%9B%86%E8%A8%88 h_01HC7K2Y627P56F5JH9QT47GB2=%E5%BA%83%E5%91%8A%E8%B2%BB%E3%81%AE%E9%9B%86%E8%A8%88 principles-of-cost-data-aggregation=%E5%BA%83%E5%91%8A%E8%B2%BB%E9%9B%86%E8%A8%88%E3%81%AE%E5%9F%BA%E6%9C%AC%E7%9A%84%E3%81%AA%E4%BB%95%E7%B5%84%E3%81%BF h_01HC7K2Y62ZC932EDX00YP7DAW=%E5%BA%83%E5%91%8A%E8%B2%BB%E9%9B%86%E8%A8%88%E3%81%AE%E5%9F%BA%E6%9C%AC%E7%9A%84%E3%81%AA%E4%BB%95%E7%B5%84%E3%81%BF h_01HC7K2Y62K78M02ZN034N99T0=cost-aggregation-methods h_01HC7K2Y62YPM3A6Z0HBY58J00=cost-data-availability-and-reports cost-in-the-ua-view=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97ua%E3%83%93%E3%83%A5%E3%83%BC%E3%81%AE%E5%BA%83%E5%91%8A%E8%B2%BB h_01KGS7NM964HW175AW2CF59P5K=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97ua%E3%83%93%E3%83%A5%E3%83%BC%E3%81%AE%E5%BA%83%E5%91%8A%E8%B2%BB h_01M3VZAVTP7F3TF607B49TGZQ4=%E6%B3%A8%E6%84%8F cost-in-unified-view=%E7%B5%B1%E5%90%88%E3%83%93%E3%83%A5%E3%83%BC%E3%81%AE%E5%BA%83%E5%91%8A%E8%B2%BB h_01KGS7QG5GNKG1YVACWQKCQFZ4=%E7%B5%B1%E5%90%88%E3%83%93%E3%83%A5%E3%83%BC%E3%81%AE%E5%BA%83%E5%91%8A%E8%B2%BB example=%E4%BE%8B h_01KGS7R5SJ3NSVJAHG3BM922VS=%E4%BE%8B cost-data-availability-and-reports::865c5bcd=%E5%BA%83%E5%91%8A%E8%B2%BB%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E7%94%BB%E9%9D%A2%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E4%B8%80%E8%A6%A7 h_01HC7K2Y62ZY6HWG5TJDEPHZKH=%E5%BA%83%E5%91%8A%E8%B2%BB%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E7%94%BB%E9%9D%A2%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E4%B8%80%E8%A6%A7 h_01M3VZAVTPK4Q2X817ER2CW62D=%E6%B3%A8%E6%84%8F-1 h_01HC7K2Y62112X308A0Y7DDDRM=cost-prioritization-mechanism h_01HC7K2Y62SZKXD4W0EJGYF6RS=%E4%BE%8B-1 %5Bclosed-beta%5D-cost-split=closed-beta--cost-split h_01KHR3PQTNF5XP7J4HZEYVRK95=closed-beta--cost-split proportional-split-by-conversions=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E6%95%B0%E3%81%AB%E5%BF%9C%E3%81%98%E3%81%9F%E9%85%8D%E5%88%86 h_01KHR3PQTNMDX8AGM1C73N7SMK=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E6%95%B0%E3%81%AB%E5%BF%9C%E3%81%98%E3%81%9F%E9%85%8D%E5%88%86 h_01KZ8TMT06KNYFZ7VBX1GY07JB=%E6%B3%A8%E6%84%8F-2 equal-split-no-conversions=%E5%9D%87%E7%AD%89%E9%85%8D%E5%88%86%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%8C%E3%81%AA%E3%81%84%E5%A0%B4%E5%90%88 h_01KHR3PQTPG8GTHV64MFCM628H=%E5%9D%87%E7%AD%89%E9%85%8D%E5%88%86%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%8C%E3%81%AA%E3%81%84%E5%A0%B4%E5%90%88 limitations=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KHR3PQTPPJYKXRYKNHM4W95A=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 list-of-ad-networks=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HC7K2Y63T9GK0WW95YM39B5C=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HC7K2Y63MG10M4Z66VHY5WYW=ad-networks-supporting-cost-api h_01HE0T3TGPZFB2ZBHFGGWXY6AP=changing-campaign-names h_01HE0T3TGQGK6135KM7AYJ7S1G=costs-without-installs h_01HE0T3TGQMK285N8RV48KG8N9=%E4%BE%8B-2 h_01HE0T3TGQ7MSSB09GFNPYFKR1=cost-currency-conversion h_01HJ10FMTJKH48CEXM0G40Y9J1=traits-and-limitations" />

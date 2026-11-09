---
title: 集計レポートの概要
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2020-02-04T09:38:14Z'
  edited_at: '2026-10-14T09:30:53Z'
  id: 360005437257
  locale: ja
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ja/articles/360005437257
---
> **概要：** 集計データのレポート、ツール、APIの紹介と比較を記載しています。

<div id="aggregated-and-analytics-performance-reporting-overview" />

## 集計・分析パフォーマンスレポートの概要

AppsFlyerでは、アプリ、キャンペーン、ユーザーのパフォーマンスを評価できるよう、各種指標を揃えた集計分析ツールを提供しています。

ツール毎にデータの取得・表示方法が異なります。例えば、オーバービューではキャンペーンのLTVデータを表示しているのに対し、コホートでは時間の経過に伴うユーザーエンゲージメントのデータが表示されます。

この記事で紹介しているツールは、管理画面上から取得できるデータに関するものです。以下のツール比較表を使って、主な用途とツールの違いを理解してください。

<div id="toolapi-comparison" />

<Accordion title="レポーティング方法の比較">

次の表では、集計データを取得するためのさまざまなレポート方法とダッシュボードについて説明します。

[**データテーブルをCSVファイルとしてダウンロード**](https://docs.google.com/spreadsheets/d/e/2PACX-1vSICicxcvD0996RT59fTLDJvdGUKxqPqr47f5SMD8BmsbZtrWIoxRxJEo7tAXTBBmnIbiH097VtK6L9/pub?output=xlsx)**して、ご利用可能なレポート方法を比較対照するのに役立つさまざまな仕様と制限事項を説明する追加の項目を確認することができます。**

ダウンロード可能な CSVファイルの追加仕様項目には、次が含まれます：

* <Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support">データ更新頻度：</Anchor>イベントが発生してから、レポート方法によってデータが使用可能になるまでの期間
* <Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV / アクティビティ：</Anchor>データがLTVかアクティビティか。
* <Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティング：</Anchor>リターゲティング（リエンゲージメントCVおよびリアトリビューションCV）に紐づくデータを表示するかどうか。
* <Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls#attributed-to-the-first-install">初回インストールまでの再インストールイベント計測：</Anchor>再インストール後のイベントを初回インストールのメディアソースに紐づけることができるかどうか。
* <Anchor target="_blank" href="/partners/ja/docs/about-agency-accounts#代理店の透明性">代理店の運用媒体開示設定：</Anchor>マーケターが代理店から派生したトラフィックの元のメディアソースの詳細を確認できるかどうか。
* <Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles">タイムゾーン：</Anchor>データの表示に使用されるタイムゾーン（UTCまたはアプリ毎に設定されたもの）
* <Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls#unattributed-organic-inapps">アトリビューションされていないオーガニックアプリ内イベント：</Anchor>再インストール後にアトリビューションが付けられていないイベントを表示するかどうか
* <Anchor target="_blank" href="/marketers/ja/docs/campaign-name-changes?">キャンペーン名の変更：</Anchor>重複表示を作成せずにキャンペーン名を変更できるかどうか。

| レポートの利用機能 | 説明 |
| --- | --- |
| オーバービュー管理画面 | 選択した期間中にインストール、リエンゲージメント、またはリアトリビューションを行ったユーザーの生涯価値（LTV） |
| <Anchor target="_blank" href="/marketers/ja/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>  <br />プレミアム機能 | 選択された LTV、アクティビティ、リテンション、コホート、および Protect360 キャンペーンのパフォーマンス KPI を API別に、CSVまたは JSON形式で指定します。 |
| <Anchor target="_blank" href="/marketers/ja/docs/pull-api-aggregate-data">Pull API - 集計レポート</Anchor> | CSVファイルをインストール、リエンゲージメント、またはリアトリビューションしたユーザーの生涯価値（LTV）UA（ユーザー獲得）とリターゲティングデータは別々です。統一されたオプションはありません。 |
| <Anchor target="_blank" href="/marketers/ja/docs/aggregated-data-export-page">集計データ出力画面</Anchor> | インストール、リエンゲージメント、またはリアトリビューションしたユーザーの生涯価値（LTV）UA（ユーザー獲得）とリターゲティングデータは別々です。統合されたオプションはありません。 |
| <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN</Anchor>  <br /><Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">オーバービュー</Anchor> | iOS SKANポストバックを介してレポートされた指標と、最初のユーザー計測期間中の追加のデータポイント |
| <Anchor target="_blank" href="/marketers/ja/docs/skan-aggregated-performance-report-api">SKAN</Anchor>  <br /><Anchor target="_blank" href="/marketers/ja/docs/skan-aggregated-performance-report-api">集計データAPI</Anchor> | iOS SKANポストバックを介してレポートされた指標と、最初のユーザー計測期間中の追加のデータポイント |
| <Anchor target="_blank" href="/marketers/ja/docs/protect360-dashboard">Protect360管理画面</Anchor> | 不正なトラフィックに関する指標と分析情報。  <br />インストールのLTVベースのデータ、アプリ内イベントのアクティビティベースのデータ。 |
| <Anchor target="_blank" href="/marketers/ja/docs/activity-dashboard">アクティビティ管理画面</Anchor> | 選択した日付範囲内のアプリのアクティビティ、エンゲージメント、アプリ内指標。 |
| アプリ内イベント管理画面 | 選択した期間中にアプリをインストールしたユーザーのLTVデータに基づく、メディアソース全体のアプリ内イベントパフォーマンス指標。 |
| リテンション管理画面 | インストール後の各日の一意のユーザーエンゲージメント（セッション）指標 |
| <Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard">コホートダッシュボード</Anchor> | インストール後の各日のさまざまなコホートLTVユーザー指標。 |
| <Anchor target="_blank" href="/marketers/ja/docs/cohort-api">コホートAPI</Anchor>  <br />プレミアム機能 | インストール後の各日のさまざまなコホートLTVユーザー指標。 |
| <Anchor target="_blank" href="/marketers/ja/docs/cohort-analytics-via-data-locker">コホート Data Locker</Anchor>  <br />プレミアム機能 | インストール後の各日のさまざまなコホートLTVユーザー指標。 |
| <Anchor target="_blank" href="/marketers/ja/docs/advanced-aggregated-reports-in-data-locker">アドバンス集計レポート</Anchor>  <br />プレミアム機能 | バージョン管理された集計データレポート。LTVデータです。 |
| <Anchor target="_blank" href="/marketers/ja/docs/custom-dashboards">カスタムダッシュボード</Anchor> | LTVユーザー獲得指標を含むカスタマイズされたダッシュボード |
| <Anchor target="_blank" href="/marketers/ja/docs/pivot-table-user-metrics">ピボットレポート</Anchor>  <br />プレミアム機能 | 選択したLTV、アクティビティ、リテンション、Protect360 キャンペーンのパフォーマンス KPI をダッシュボードまたは CSV で確認できます。 |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports">コストETL</Anchor> | メディアソースごとに利用可能な最高の粒度を持つキャンペーン支出データ |
| 使用状況レポート | AppsFlyerのすべての使用量ベースの機能の組み合わせで、請求サイクルの期間中の契約義務に影響を与えます。 |
| <Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-guide">クリエイティブ最適化ダッシュボード</Anchor> | クリエイティブに関するLTVパフォーマンスデータ。つまり、指標は選択した期間中にクリエイティブから発生したコンバージョンに関するものです。 |

</Accordion>

<div id="cohort-flavors" />

<Accordion title="コホートデータの配信方法">

コホートはさまざまな配信方法で利用できます：<Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard">コホート管理画面</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/cohort-api">コホートAPI</Anchor>、Data Locker経由<Anchor target="_blank" href="/marketers/ja/docs/cohort-analytics-via-data-locker">のコホート分析。</Anchor>以下の表で、その違いについて記載しています。

| 特性 | Data Lockerでのコホート分析 | Data Lockerアドバンス集計レポート | コホート | コホートAPI |
| --- | --- | --- | --- | --- |
| 複数アプリ / 単一アプリ | 複数アプリ対応：データはアプリ毎に１つのファイルに集計されるか、アプリ毎に複数ファイルに分割 | 複数アプリ対応：データはアプリ毎に１つのファイルに集計されるか、アプリ毎に複数ファイルに分割 | 複数アプリ対応：アプリを組み合わせたパフォーマンス分析と、アプリ毎の分析を選択可能。 | 単一 |
| グループ化 | キャンペーンの全階層と全イベント約20のグループ化 | キャンペーンの全階層と全イベント約20のグループ化 | 4グループ | 7グループ |
| 利用できる指標 | 全指標 | 全指標 | 1画面毎に、1つの選択可能な指標と4つの固定指標 | 1コール毎に、1つの選択可能な指標と4つの固定指標 |
| インストールから集計可能な日数 | 365日後まで | 1095日後まで | 180日後まで | 180日後まで |
| データ取得における制限事項 | 全データセットを利用可能 | 全データセットを利用可能 | 手動での設定とダウンロードが必要 | 回数とデータサイズの制限あり |
| カスタマイズの可否 | いいえ | いいえ | はい | はい |

コホートデータ配信方法の違い

</Accordion>

<div id="user-journey-reports" />

### ユーザージャーニーレポート

記載されているレポートは、データエクスポートページもしくはPull API経由で利用できます。

これらは <Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV（顧客生涯価値）</Anchor>レポートです。したがって：

* レポートで利用可能な最も早い日付は、最初にアプリ計測が発生した日付です。
* レポートの日付範囲は、アトリビューション日に基づいています。
  * 新規獲得 / Protect360レポート：インストール日
  * リターゲティングレポート：リアトリビューション日とリエンゲージメント日

<div id="ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users" />

<Accordion title="新規獲得のLTV集計データレポート（非オーガニック・オーガニックを含む）">

<table><thead><tr><th>レポート名</th><th>グループ化</th></tr></thead><tbody><tr><td>パートナー（メディアソース）</td><td>代理店 / メディアソース / キャンペーン</td></tr><tr><td>パートナー（日別）</td><td>日付 / 代理店 / メディアソース / キャンペーン</td></tr><tr><td>デイリーアクティビティ</td><td>日付 / 代理店 / メディアソース / キャンペーン</td></tr><tr><td>Geo（国）</td><td>国 / 代理店 / メディアソース / キャンペーン</td></tr><tr><td>Geo（国）日別</td><td>日付 / 国 / 代理店 / メディアソース / キャンペーン</td></tr><tr><td>ビュースルー計測 (VTA) KPI</td><td><a href="./pull-api-aggregate-data" target="_blank">ビュースルーレポートはPull API経由で取得可能です</a></td></tr><tr><td colspan="2"> <strong>注：</strong>Meta広告が選択された<em>メディアソース</em>の場合は、追加の項目が含まれます：広告グループID、広告グループ名、広告セットID、広告セット名</td></tr></tbody></table>

CSVファイル内の日付の項目は「yyyy-mm-dd」のフォーマットになっています。CSVファイルをExcelで開くと、PC上の日付/時刻の設定を使用して日付カラムが表示されます。<Anchor target="_blank" href="https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows">エクセル</Anchor>上で適切な日付の表示方法を選択してください。

<div id="examples-of-aggregate-reports" />

#### 集計レポートのサンプル

[レポートサンプル（スプレッドシート形式）](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmzRons779Dk5QWVoPsOF8E7yJLwNPB1IF87shZr6rcMJLjszlSNIbAMVcdeQLysr8Bc4QAby5QB4u/pub?output=xlsx)

<div id="fields-in-ua-aggregate-reports" />

#### 新規獲得の集計レポートにおける項目

<table><colgroup><col/><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th rowspan="2">フィールド</th><th rowspan="2">説明</th><th colspan="5"><strong>レポート名</strong></th></tr><tr><th><strong>パートナー（メディアソース）</strong></th><th><strong>パートナー（日付別）</strong></th><th><strong>デイリー</strong></th><th><strong>Geo（国）</strong></th><th><strong>Geo（国）日別</strong></th></tr></thead><tbody><tr><td>Country</td><td>インストールを計測した国</td><td> </td><td> </td><td> </td><td>✓</td><td> ✓</td></tr><tr><td>Date</td><td>計測日</td><td> </td><td>✓</td><td> </td><td> </td><td>✓</td></tr><tr><td>Agency/PMD (af_prt)</td><td>代理店 / パートナー名</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Media Source (pid)</td><td>ユーザーを獲得したメディアソース(pid=media source)</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Campaign</td><td><p>キャンペーン名</p><p>(c= campaign name)</p></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Campaign ID</td><td>MetaキャンペーンID </td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td></tr><tr><td>Adgroup ID</td><td>Meta広告グループID or 広告ID</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td></tr><tr><td>Adgroup Name</td><td>Metaの広告グループ</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td></tr><tr><td>Adset ID</td><td>Metaの広告セットID</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td></tr><tr><td>Adset Name</td><td>Meta広告セット名</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td><td>Meta広告のみ</td></tr><tr><td>ARPU</td><td>ユーザーあたりの平均収益</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>Average eCPI</td><td>Average eCPI</td><td> </td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>Clicks</td><td>クリック数</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Conversion Rate</td><td>インストール ÷ クリック</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>CTR</td><td>クリック率（CTR）</td><td> </td><td>✓</td><td>✓</td><td> </td><td> </td></tr><tr><td>`{SDKアプリ内イベント名} (Unique Users)</td><td>イベントを実行したユニークユーザー数</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>{SDKアプリ内イベント名}  (Event counter)</td><td>イベント合計実行数</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>{SDKアプリ内イベント名}` (Sales in XXX)</td><td>イベントXXXから発生した収益額 (XXX：アプリ個別の通貨設定)</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>Impressions</td><td>インプレッション数</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>Installs</td><td>インストール数</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Loyal Users</td><td>[デフォルト設定] アプリを3回以上起動したユーザー数 / アプリ設定画面での設定に準ずる</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Loyal Users/Installs</td><td>ロイヤルユーザー率</td><td>✓</td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>ROI</td><td>投資利益率</td><td>✓</td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>Sessions</td><td><ul><li>非オーガニックユーザーのアプリ起動数</li><li>オーガニックユーザーと非オーガニックユーザーのアプリ起動数はコホートレポートにて利用可能</li></ul></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Total Cost</td><td>-</td><td>✓</td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>Total revenue</td><td>メディアソース / キャンペーンから生み出された総収益</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td colspan="7"> <strong>注記：</strong>「Meta広告のみ」と表示される列は、唯一のメディアソースとしてMeta広告を選択すると表示されます。</td></tr></tbody></table>

</Accordion>

<div id="retargeting" />

<Accordion title="リターゲティング集計データレポート">

リターゲティングレポートは、<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#retargeting-reports-and-raw-data">リターゲティング広告</Anchor>に接触しリエンゲージメントとリアトリビューションを計測したユーザーのデータで構成されます。

リターゲティングレポートでは、オーガニックユーザーと非オーガニックユーザーの区別はありません。

Pull API経由でリターゲティングレポートを取得する際は、 *&reattr=true* のパラメータをパフォーマンスレポートのURIに追加してください。

<div id="aggregate-ltv-retargeting-reports" />

#### 集計リターゲティングLTVレポート

| レポート名 | グループ化 |
| --- | --- |
| パートナー（メディアソース） | 代理店 / メディアソース / キャンペーン |
| パートナー（日別） | 日付 / 代理店 / メディアソース / キャンペーン |
| デイリーアクティビティ | 日付 / 代理店 / メディアソース / キャンペーン |
| 国別 | 国 / 代理店 / メディアソース / キャンペーン |
| 国・地域（日付別） | 日付 / 国 / 代理店 / メディアソース / キャンペーン |

<div id="aggregate-ltv-retargeting-reports-1" />

#### 集計リターゲティングLTVレポート

| フィールド | 説明 | パートナー | デイリー | パートナー（日別） | Geo（国）日別 | Geo（国） |
| --- | --- | --- | --- | --- | --- | --- |
| Date | コンバージョン日 | - | - | ✓ | ✓ | - |
| 国別 |  | - | ✓ |  | ✓ | ✓ |
| Agency/PMD (af\_prt) | 代理店 / パートナー名 | ✓ | ✓ | ✓ | ✓ | ✓ |
| Media Source (pid) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Campaign (c) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Clicks |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversions |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversion Type | Reattribution もしくは re-engagement | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversion Rate | コンバージョン数 ÷ クリック数 | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sessions |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users/Installs |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Total Cost |  | - | - | - | - | - |
| Average eCPI |  | - | - | - | - | - |
| Total Revenue |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| ROI |  | - | - | - | - | - |
| ARPU |  | ✓ | ✓ | ✓ | - | ✓ |

</Accordion>

<div id="feature-reports" />

## 機能レポート

<div id="skadnetwork" />

<Accordion title="SKAdNetwork">

<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#reporting-options">SKAdNetwork 集計レポート</Anchor>

</Accordion>

<div id="protect360-blocked-fraud" />

<Accordion title="Protect360 — ブロック済み不正">

<Image align="center" alt="" src="https://theme.zdassets.com/theme_assets/245528/ffbbc473bb0e74b9fb636ed735f69e9af6a25a18.png" />

ブロックされた不正データの集計レポートでは、<Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide">Protect360</Anchor> によってブロックされた各種イベントの詳細を確認可能です。

レポートはPull API経由で利用可能です。（データ出力画面からは取得できません。）

レポートの日付範囲はインストール日を意味します。

<div id="aggregate-protect360-reports-available-via-pull-api" />

#### Pull API経由で利用可能なProtect360の集計レポート

| レポート名 |
| --- |
| パートナー（メディアソース） |
| パートナー（日別） |
| Geo（国） |
| Geo（国）日別 |
| パートナーキャンペーンレポート |

**制限:** ブロック理由が**App Version**と**customer user idの欠落**であった場合にも、ブロック理由：**Bots** として表示されます。

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/configuring-meta-campaign-management-partners">Metaキャンペーンマネジメントパートナーの設定</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ローデータレポートの概要</Anchor>

<div data-zendesk-anchors="aggregated-and-analytics-performance-reporting%E2%80%94tools-and-reports=%E9%9B%86%E8%A8%88%E5%88%86%E6%9E%90%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E6%A6%82%E8%A6%81 01EWA9VQ2HH93525BMK6WN0P6S=%E9%9B%86%E8%A8%88%E5%88%86%E6%9E%90%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E6%A6%82%E8%A6%81 01ED4D7W8B53Q81G7PXQH8ADE2=toolapi-comparison h_01HDNYFR9KBX2KP75K1FAZC2Q7=cohort-flavors user-journey-reports=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%83%8B%E3%83%BC%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01ED4D7W8CVAQ9V2GCEX1G6KD7=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%83%8B%E3%83%BC%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HDNYFR9KBMWAFXDNNJN8VA2X=ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users examples-of-aggregate-reports=%E9%9B%86%E8%A8%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%82%B5%E3%83%B3%E3%83%97%E3%83%AB 01ED4D7W8C3ZNBYR3CMHJF3QSE=%E9%9B%86%E8%A8%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%82%B5%E3%83%B3%E3%83%97%E3%83%AB fields-in-ua-aggregate-reports=%E6%96%B0%E8%A6%8F%E7%8D%B2%E5%BE%97%E3%81%AE%E9%9B%86%E8%A8%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E9%A0%85%E7%9B%AE h_01HDNYFR9KTQ7ZF35C7E7M7AF1=%E6%96%B0%E8%A6%8F%E7%8D%B2%E5%BE%97%E3%81%AE%E9%9B%86%E8%A8%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E9%A0%85%E7%9B%AE h_01J3YNA04FEF0MHPAFF39ZJYC2=retargeting aggregate-ltv-retargeting-reports=%E9%9B%86%E8%A8%88%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0ltv%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HDNYFR9MSJWCP3JA4M1WXN1H=%E9%9B%86%E8%A8%88%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0ltv%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 aggregate-ltv-retargeting-reports::b2093953=%E9%9B%86%E8%A8%88%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0ltv%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88-1 h_01HDNYFR9MSK9VQQ0Q889Z55TN=%E9%9B%86%E8%A8%88%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0ltv%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88-1 feature-reports=%E6%A9%9F%E8%83%BD%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HDNYFR9MYXVZ5BA9FDZ6D82M=%E6%A9%9F%E8%83%BD%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01ED4D7W8CBH7Q8D31VX5313WP=skadnetwork protect360%E2%80%94blocked-fraud=protect360-blocked-fraud h_01HDNYFR9MJNKGR7XFCACVP6KT=protect360-blocked-fraud aggregate-protect360-reports-available-via-pull-api=pull-api%E7%B5%8C%E7%94%B1%E3%81%A7%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AAprotect360%E3%81%AE%E9%9B%86%E8%A8%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HDNYFR9MSZ9K8F283J0WBHCZ=pull-api%E7%B5%8C%E7%94%B1%E3%81%A7%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AAprotect360%E3%81%AE%E9%9B%86%E8%A8%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HDNYYJXVY9XHX87K06NXYQNS=%E5%8F%82%E7%85%A7" />

---
title: ［Beta機能］クロスプラットフォーム・エンドユーザーイベントレポート｜Data Locker
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2025-10-07T10:37:56Z'
  edited_at: '2026-10-14T09:24:19Z'
  id: 39748676204817
  locale: ja
  section: Cross platform reports
  section_id: 50467263168657
  url: https://support.appsflyer.com/hc/ja/articles/39748676204817
---
> **概要：** クロスプラットフォーム・エンドユーザーイベントレポートは、プラットフォームやデバイスを横断して、完全なユーザージャーニー、コンバージョン、LTV を計測します。

クロスプラットフォーム・エンドユーザーイベントレポートは、ローデータレポートであり、Customer User ID（CUID）を用いてプラットフォーム間で紐付けられた、各ユーザーのセッションおよびアプリ内イベントのイベントレベルログを提供します。各イベントにはクロスプラットフォームのアトリビューション結果が含まれており、ユーザーの完全なジャーニーを分析することが可能です。

ユーザーベースのアトリビューションフローおよび設定の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/beta-user-based-cross-platform-attribution">ユーザーベースのクロスプラットフォームアトリビューション</Anchor>を参照してください。

## レポート項目

レポートに含まれる項目を確認するには、[レポートサンプルをダウンロードしてください。](https://docs.google.com/spreadsheets/d/e/2PACX-1vRhOl-tyaJvgPd9rxGkGMNrgzHPpr7ZsMMnONOHkzdObor158gJPt7XwCBkreM4ka4OkGIyDmqCp_hh/pub?output=csv)

レポートサンプルには、すべてのレポート項目とその値が含まれています。各項目の定義については、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">項目一覧</Anchor>を参照してください。

## レポートデータの更新頻度

* 本レポートは 4時間ごとにバッチ処理が実行されます。
* 各バッチでは、直前の 4 時間にデータベースへ取り込まれたイベントが処理されます。
  * 例：8:00 AM のバッチでは、3:00 AM〜7:00 AM の間にデータベースへ取り込まれたイベントが処理されます。

* イベントは、該当する時間単位のバケットに割り当てられます。
  * 例：3:00 AM〜4:00 AM にデータベースへ取り込まれたイベントは、3:00 AM のバケットに表示されます。

> 🚧 **重要**
>
> イベントが実際に発生してからデータベースに取り込まれるまでには、通常わずかな遅延があります。本レポートでは、正確で一貫した時間単位のグルーピングを行うため、データベースへの取り込み時刻を使用しています。

### 8:00 AM バッチの例

| 日付 | レポートバージョン | レポート利用可能時刻 | レポートに含まれるイベント発生時間 | データベース取り込み時間 |
| --- | --- | --- | --- | --- |
| 2025-10-01 | 3:00 | 9:00 | 2:00-4:00 | 3:00-4:00 |
| 2025-10-01 | 4:00 | 9:00 | 3:00-5:00 | 4:00-5:00 |
| 2025-10-01 | 5:00 | 9:00 | 4:00-6:00 | 5:00-6:00 |
| 2025-10-01 | 6:00 | 9:00 | 5:00-7:00 | 6:00-7:00 |

上記例に関する補足：

* バッチ実行直前の 1 時間分のイベントは、関連する CUID を付与するための十分な時間を確保する目的で処理されません。上記例では、8:00 AM のバッチは 3:00〜7:00 に取り込まれたイベントを処理し、7:00〜8:00 に取り込まれたイベントは処理対象外となります。
* バッチ実行後、内部処理により 1 時間後にレポートが利用可能となります。上記例では、8:00 AM のバッチは 9:00 AM に利用可能です。

## レポートの購読方法

1. AppsFlyer管理画面 左メニュー **エクスポート** > **Data Locker**へ移動します。
2. **Data Locker のコンテンツページ**で **アドバンスレポート**のセクションまでスクロールします。
3. **クロスプラットフォーム・エンドユーザーイベント**を選択します。

## クラウドバケットでのレポートデータの参照方法

レポートのパスは、以下のフォルダ階層で構成されます。

```
<bucket-name>/<DataLocker connection name>/t=end_user_events_user_level_cross_platform/dt=<dt=yyyy-mm-dd>/h=<hour>/
```

### レポートのフォルダ階層

[![](https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png)](https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png)

## データ分析担当者向けの考慮事項

* 各時間バケットには、重複しないエンドユーザーイベントが含まれます。時間単位または日次で、すべてのレポートを取得してください。
* 広告収益イベントは、現時点では含まれていません。
* すべてのアプリデータは 1 つのファイルにまとめて提供されます。App IDの項目を使用してアプリ単位に分割するか、Data Locker でアプリ単位の分割設定を行ってください。統合された分割方法の使用を推奨します。
* コスト、クリック、インプレッションなどのアトリビューションよりも前のデータは、Cost ETL レポートから抽出してください。

### クエリ例

以下は、BI担当者が Data Locker 経由で抽出できる、代表的かつ実用的なデータ活用例です。各例は SQL ステートメントで示しています。

<div id="calculating-total-user-acquisitions" />

<Accordion title="ユーザー獲得数の算出">

メディアソースおよびキャンペーンごとの、新規ユニークユーザー数をカウントします。

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT customer_user_id) AS user_acquisition
	,
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-platform-activations" />

<Accordion title="プラットフォーム別アクティベーション総数の算出">

ユーザーごとに、新規でアクティブ化されたプラットフォーム、グループ、メディアソース、キャンペーンの総数を算出します。

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT CASE 
			WHEN platform_group = 'PC'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CONSOLE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CTV'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'MOBILE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Web'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Other'
				THEN customer_user_id
			ELSE NULL
			END) AS total_activations
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-revenue" />

<Accordion title="総収益の算出">

メディアソースおよびキャンペーンごとの総収益を算出します。

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,SUM(revenue_value_customer) AS total_revenue
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = ’YOUR_PRODUCT_LINE_NAME’
GROUP BY install_date
	,media_source
	,campaign_name;
```

</Accordion>

<div data-zendesk-anchors="the-report-fields=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E9%A0%85%E7%9B%AE h_01K6Z40KG9H1AC81H77XXEGK1B=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E9%A0%85%E7%9B%AE report-data-freshness=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%9B%B4%E6%96%B0%E9%A0%BB%E5%BA%A6 h_01K6Z40KG9PTRAFGXB3XJH5TJ7=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%9B%B4%E6%96%B0%E9%A0%BB%E5%BA%A6 h_01K6Z40KG9QPSMXT13N50TE7KE=%E9%87%8D%E8%A6%81 example-of-the-800-am-batch-run=800-am-%E3%83%90%E3%83%83%E3%83%81%E3%81%AE%E4%BE%8B h_01K6Z40KG9JTHGJG7YJNH9TTDT=800-am-%E3%83%90%E3%83%83%E3%83%81%E3%81%AE%E4%BE%8B how-to-subscribe-to-the-report=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E8%B3%BC%E8%AA%AD%E6%96%B9%E6%B3%95 h_01K6Z40KG9J1XWV99Z9M7AG0BY=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E8%B3%BC%E8%AA%AD%E6%96%B9%E6%B3%95 how-to-access-the-report-in-your-bucket=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%81%A7%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%82%E7%85%A7%E6%96%B9%E6%B3%95 h_01K6Z40KG9CDQ43ASM5T80AK65=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%81%A7%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%82%E7%85%A7%E6%96%B9%E6%B3%95 dl-report-folder-hierarchy=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E9%9A%8E%E5%B1%A4 h_01K6Z40KG9NSVWTRSHR71Q7PM6=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E9%9A%8E%E5%B1%A4 bi-developer-considerations=%E3%83%87%E3%83%BC%E3%82%BF%E5%88%86%E6%9E%90%E6%8B%85%E5%BD%93%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 h_01K6Z7QHDT4Q2D4JFGC28W8MND=%E3%83%87%E3%83%BC%E3%82%BF%E5%88%86%E6%9E%90%E6%8B%85%E5%BD%93%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 query-examples=%E3%82%AF%E3%82%A8%E3%83%AA%E4%BE%8B h_01K6Z40KG9E2F30Q9P5GFA9TWT=%E3%82%AF%E3%82%A8%E3%83%AA%E4%BE%8B h_01K6Z40KG9Y4MWKY6HX8A5NPXA=calculating-total-user-acquisitions h_01K6Z40KG9J9VKC3JH6XNNDA52=calculating-total-platform-activations h_01K6Z40KG9SE8068HG75H59E8Q=calculating-total-revenue" />

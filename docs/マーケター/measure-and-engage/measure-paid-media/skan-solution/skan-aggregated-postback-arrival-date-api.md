---
title: SKANポストバック到着日別集計API
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-12-21T09:03:09Z'
  edited_at: '2026-10-28T09:17:34Z'
  id: 360016646557
  locale: ja
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ja/articles/360016646557
---
> **概要：** 集計したSKAdNetworkポストバックをAPI経由で取得できます。データは、ポストバック到着日を基準に集計されます。

<div id="skan-aggregated-postback-arrival-date-api" />

## SKANポストバック到着日別集計API

このAPIは、指定したポストバック到着日の期間で、SKAdNetworkポストバックを集計して返します。

**注意**！ポストバック到着日は、SKAdNetworkダッシュボードとレポートで使用するインストール日とは異なります。

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="SKANポストバック到着日別集計APIの使用方法">

**SKANポストバック到着日別集計APIを使用する手順**：

1. APIトークンを取得します。トークンは管理者が取得する必要があります。
2. 認証ヘッダーで使用するAPIトークンを開発者に渡します。
3. 次のセクションを参照し、API呼び出し時に指定するパラメータを開発者に伝えてください。パラメータでは、レポートの対象、データのまとめ方、対象期間を指定します。
4. 開発者には、Developer Hubの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-postback-arrival-date-api-get">SKANポストバック到着日別集計API</Anchor>の手順に従うよう依頼してください。

<div id="parameters" />

#### パラメータ

| パラメータ名 | 詳細 | 必須 |
| --- | --- | --- |
| `start_date` | ポストバック到着日の対象期間は、start\_dateとend\_dateで指定します。注意！到着日は、SKAdNetworkダッシュボードとレポートで使用するインストール日とは異なります。<ul><li>YYYY-MM-DD</li><li>指定できる最も古い日付：2020-11-01。<br />例：`2020-11-05`</li></ul> | はい |
| `end_date` | <ul><li>YYYY-MM-DD</li><li>1回のレポート取得で指定できる最大日数：60日</li><li>例：`2020-11-12`</li></ul> | はい |
| `ad_network_name` | メディアソースで絞り込み | いいえ |
| `geo` | ISO 3166（alpha-2）の国コードで絞り込みます。例：`US`、`CN` | いいえ |
| `skad_redownload` | `true`または`false`で絞り込みます。 | いいえ |
| `skad_source_app_id` | ソースアプリIDで絞り込み | いいえ |
| `ad_network_campaign_id` | アドネットワークのキャンペーンIDで絞り込みます。<br /><br />**注意**：これは、SKAdNetworkが報告するキャンペーンIDではありません。 | いいえ |
| `modeled_conversion_values` | <ul><li>V2以降でのみ対応</li><li>指定できる値は`true`または`false`です。</li><li>`true`の場合、ポストバックのcount列に、モデリングで推定したCVの件数が設定されます。  [モデリングによる推定データで利用できるフィールドを確認](/docs/skan-aggregated-postback-arrival-date-api#report-structure-and-example)</li><li>`false`の場合、推定データを含めずにCVの件数を返します。レポート構成に示す、利用可能なすべてのフィールドが含まれます。</li><li>デフォルト値は`false`です。</li></ul> | いいえ |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="レポートの構成と例">

APIはCSVファイルを返します。

利用できる列と指標は、以下の表のとおりです。

例：<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRXgsWlkyvMS20HgZuOQnH1YC8QQcRhOMYIOxyj_fcgikfDfmW6wNAMHO6alPWVA1j_KZwtqowohqrK/pub?gid=0&single=true&output=csv">V1</Anchor>｜<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRMFEELm8JCAQBBAIJqAc1eE5YdN0kOcSVkOPd_Ki2ngnX61wHL4sXypVouOhto8u-JCQmdIYY_5UG6/pub?gid=219191499&single=true&output=csv">V2</Anchor>

| 列名 | ディメンションまたは計測値 | API V1トークンで利用可能 | API V2トークンで利用可能 | API V2トークンで利用可能（SKAN 4） | 推定データのみのフィルター使用時に利用可能 |
| --- | --- | --- | --- | --- | --- |
| skad\_postback\_sequence\_index | グループ化の基準 | N | N | Y | Y |
| skad\_conversion\_value | グループ化の基準 | Y | Y | Y | Y |
| skad\_coarse\_conversion\_value | グループ化の基準 | N | N | Y | Y |
| skad\_ad\_network\_id<br /><br />一部のSRNは、自社のIDをAppsFlyerに共有していません。その場合、このフィールドは空欄となり、ad\_network\_nameに値が設定されます。 | グループ化の基準 | Y | Y | Y | Y |
| ad\_network\_name<br /><br />現在、ほとんどの場合、このフィールドは空欄です。ただし、skad\_ad\_network\_idを共有していないSRNについては、値を設定します。 | グループ化の基準 | Y | Y | Y | Y |
| skad\_source\_identifier | グループ化の基準 | N | N | Y | Y |
| skad\_campaign\_id | グループ化の基準 | Y | Y | Y | Y |
| ad\_network\_campaign\_id | グループ化の基準 | Y | Y | Y | Y |
| ad\_network\_campaign\_name | グループ化の基準 | Y | Y | Y | Y |
| ad\_network\_adset\_id | グループ化の基準 | N | Y | Y | Y |
| ad\_network\_adset\_name | グループ化の基準 | N | Y | Y | Y |
| ad\_network\_ad\_id | グループ化の基準 | N | Y | Y | N |
| ad\_network\_ad\_name | グループ化の基準 | N | Y | Y | N |
| ad\_network\_creative | グループ化の基準 | N | N | Y | N |
| ad\_network\_channel | グループ化の基準 | N | N | Y | N |
| skad\_version | グループ化の基準 | Y | Y | Y | N |
| skad\_redownload | グループ化の基準 | Y | Y | Y | N |
| skad\_source\_app\_id | グループ化の基準 | Y | Y | Y | N |
| skad\_source\_domain | グループ化の基準 | N | N | Y | Y |
| skad\_fidelity\_type | グループ化の基準 | N | Y | Y | N |
| geo | グループ化の基準 | Y | Y | Y | N |
| arrival\_date | グループ化の基準 | Y | Y | Y | Y |
| count | 計測値 | Y | Y | Y | Y |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| データの更新頻度 | レポートは<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#eod">日次</Anchor>で更新されます。<br /><br />データは、<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#skan">SKAdNetwork</Anchor>の更新頻度に従って利用できるようになります。 |
| 日付範囲 | <ul><li>対応する最も古い日付：2020年11月1日</li><li>1回のクエリで指定できる最大期間：60日</li></ul> |
| レート制限 | <ul><li>1回のクエリで最大200,000行を返します。</li><li>1分あたり60回の呼び出し</li></ul> |
| SRNs | Google広告：ポストバック到着日は、Googleが報告した最終クリック時刻を基に算出します。 |
| アドネットワークのアクセス | 広告主から権限を付与されている場合、分析パートナーも利用できます。 |
| 代理店のアクセス | 利用不可 |
| アプリ固有のタイムゾーン | UTCのみ |
| アプリ固有の通貨 | 常にUSD |
| オーガニックデータ | このAPIでは利用できません。 |
| ノンオーガニックデータ | AppsFlyerが受信したSKAdNetworkポストバックを使用して算出します。 |
| 過去のデータ | 対応する最も古いコンバージョンデータ（インストールまたはリターゲティング）：2020年11月1日 |
| アカウントユーザーのアクセス | 認証トークンは、管理者ユーザーがダッシュボードで取得できます。 |

</Accordion>

<div id="see-also" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/skan-aggregated-performance-report-api">SKAN集計パフォーマンスレポートAPI</Anchor>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=skan%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E5%88%B0%E7%9D%80%E6%97%A5%E5%88%A5%E9%9B%86%E8%A8%88api h_01HDNZKFEHWET0FPX9WN136MB2=skan%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E5%88%B0%E7%9D%80%E6%97%A5%E5%88%A5%E9%9B%86%E8%A8%88api h_01HDNZKFEH76Y06091QS6Y5K1Z=using-skan-aggregated-performance-report-api parameters=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HDNZKFEHA6N6EE4RMG0HGABA=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HDNZKFEHM2D7GS3RMSRCKZY7=report-structure-and-example h_01HDNZKFEJ5P3245V1R99DGAQW=specifications-and-limitations h_01HDNZP87CWGVJ3G1BDXAR1WN0=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />

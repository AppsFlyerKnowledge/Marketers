---
title: SKAN集計パフォーマンスレポートAPI
metadata:
  keywords:
    - Advertisers
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T09:45:03Z'
  edited_at: '2026-10-28T09:17:31Z'
  id: 360014104157
  locale: ja
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ja/articles/360014104157
---
> **概要：** SKANの成果データを、追加情報とともに取得できます。 SKAdNetworkダッシュボードと同様のデータです。インストール日またはポストバック到着日で集計します。

## SKAN集計パフォーマンスレポートAPI

このAPIは、インストール日またはポストバック到着日を基準に、AppleのSKAdNetworkが報告したアトリビューション指標（実データ）と、その他の情報を返します。レポートの構成は、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKANダッシュボード</Anchor>に表示されるデータと同様です。 

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="SKAN集計パフォーマンスレポートAPIの使用方法">

**SKAN集計パフォーマンスレポートAPIを使用する手順**：

1. APIトークンを取得します。トークンは管理者が取得する必要があります。
2. 認証ヘッダーで使用するAPIトークンを開発者に渡します。
3. 次のセクションを参照し、API呼び出し時に指定するパラメータを開発者に伝えてください。パラメータでは、レポートの対象、データのまとめ方、対象期間を指定します。
4. 開発者には、Developer Hubの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-performance-report-api-get">SKAN集計パフォーマンスレポートAPI</Anchor>の手順に従うよう依頼してください。

#### パラメータ

| パラメータ名 | 形式 | 必須 |
| --- | --- | --- |
| `date_type` | `start_date`と`end_date`で指定する期間の基準となる日付の種類。<br /><br />選択肢：<ul><li>［デフォルト］`install`：AppsFlyerが、ポストバックの到着時刻と計測期間を考慮して算出したインストール日。</li><li>`arrival`：ポストバックの到着時刻。注意：オーガニックインストールの指標はN/Aになります。</li></ul>Google広告のデータ：Google広告の報告方式により、インストール日と到着日は同じになります。 | いいえ |
| `start_date` | インストール日の対象期間は、start\_dateとend\_dateで指定します。注意！インストール日は、ポストバック到着日とは異なります。<ul><li>インストール日の開始日。形式はYYYY-MM-DDです。</li><li>指定できる最も古い日付：2020-11-01。<br />例：`2020-11-05`</li></ul> | はい |
| `end_date` | <ul><li>インストール日の終了日。形式はYYYY-MM-DDです。</li><li>1回のレポート取得で指定できる最大日数：90日</li><li>例：`2020-11-12`</li></ul> | はい |
| `view_type` | 以下の種類でインストールを絞り込みます。<ul><li>`acquisition`：インストール</li><li>`retargeting`：再ダウンロード</li><li>`unified`：新規獲得と再ダウンロードの両方</li><li>［デフォルト］`unified`</li><li>コスト、クリック、インプレッションの指標は、`view_type=unified`の場合に返されます。</li></ul> | いいえ |
| `modeled_conversion_values` | <ul><li>V2以降でのみ利用可能</li><li>指定できる値は`true`または`false`です。</li><li>trueの場合、ポストバックのデコード済み指標の列には、モデリングによる推定データも含まれます。[利用できるフィールドを確認](/docs/skan-aggregated-performance-report-api#report-structure-and-example)</li><li>`false`の場合、モデリングによる推定データを含めず、元のSKANポストバックをデコードしたデータを表示します。</li><li>デフォルト値は`false`です。</li></ul> | いいえ |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="レポートの構成と例">

APIはCSVファイルを返します。

* レポートで利用できるフィールドと指標は、以下の表のとおりです。
* 一部の指標（収益、エンゲージメント、コンバージョン）は、SKANの<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">成果計測の設定</Anchor>によって異なります。
* レポートには、対象期間中にユーザーが実行したアプリ内イベントのみが含まれます。そのため、アプリ内イベントの列の数と順序は、レポートごとに変わる場合があります。データのインポート処理は、列の順序に依存しないように設計してください。
* 例：[V1](https://docs.google.com/spreadsheets/d/e/2PACX-1vSmnyUITQjRxNp6-rz8Xzscu-Rr4Kn2DW1du2VppS-QrpyQSZ0GKQ_qZdWNdNoLuwJAmgh2O-bWiuU3/pub?gid=0&single=true&output=csv)｜<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQogLd4w3xgrjQBmEiHLfcvz1e9dtWez_Rdg1OxV8bSRHRE-wxZJItfT6azLr4iZAgsW2Vxr_WVmEYo/pub?gid=0&single=true&output=csv">V2</Anchor>

#### レポートのフィールド

| フィールド名 | ディメンションまたは指標 | API V1トークンで利用可能 | API V2トークンで利用可能 | API V2トークンで利用可能（SKAN 4） | 推定データのみのフィルター使用時に利用可能 |
| --- | --- | --- | --- | --- | --- |
| 日付<br /><br />選択したdate\_typeに基づくデータです。 | ディメンション | N | Y | Y | Y |
| メディアソース（pid） | ディメンション | Y | Y | Y | Y |
| キャンペーン（c） | ディメンション | Y | Y | Y | Y |
| キャンペーンID | ディメンション | Y | Y | Y | Y |
| サイトID | ディメンション | Y | Y | Y | N |
| 広告セット | ディメンション | N | Y | Y | Y |
| 広告セットID | ディメンション | N | Y | Y | Y |
| 広告 | ディメンション | N | Y | Y | N |
| 広告ID | ディメンション | N | Y | Y | N |
| 国 | ディメンション | Y | Y | Y | N |
| AppsFlyerアトリビューションフラグ<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/single-source-of-truth-ssot-guide-for-ios-attribution">SSOT（Single Source of Truth）ガイド</Anchor>を参照してください。 | ディメンション | N | Y | Y | Y |
| ポストバックのシーケンスインデックス | ディメンション | N | N | Y | Y |
| クリエイティブ | ディメンション | N | N | Y | N |
| チャネル | ディメンション | N | N | Y | N |
| インプレッション | 指標 | Y | Y | Y | Y |
| クリック | 指標 | Y | Y | Y | Y |
| CTR | 指標 | Y | Y | Y | Y |
| インストール | 指標 | Y | Y | Y | Y |
| クリックスルーインストール（fidelity\_type = 1） | 指標 | Y | Y | Y | Y |
| ビュースルーインストール<br /><br />(fidelity\_type = 0) | 指標 | Y | Y | Y | Y |
| CVがnullの割合<br /><br />［2022年1月23日以降に利用可能］ | 指標 | N | Y | Y | Y |
| コンバージョン率 | 指標 | Y | Y | Y | Y |
| コンバージョンユーザー数 | 指標 | Y | Y | Y | Y |
| コンバージョンユーザー数÷インストール数 | 指標 | Y | Y | Y | Y |
| 総収益 | 収益指標 | Y | Y | Y | Y |
| 総コスト | 指標 | Y | Y | Y | Y |
| ROI | 収益指標 | Y | Y | Y | Y |
| ARPU | 収益指標 | Y | Y | Y | Y |
| 平均eCPI | 指標 | Y | Y | Y | Y |
| `{af_skad_revenue}`（ユニークユーザー数） | 収益指標 | Y | Y | Y | Y |
| `{af_skad_revenue}`（イベント回数） | 収益指標 | Y | Y | Y | Y |
| `{your in-app event name}`（ユニークユーザー数） | 指標 | Y | Y | Y | Y |
| `{your in-app event name}`（イベント回数） | 指標 | Y | Y | Y | Y |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| データの更新頻度 | データは、<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#skan">SKAN</Anchor>の更新頻度に従って利用できるようになります。 |
| 日付範囲 | <ul><li>期間の終了日には、UTCの当日から3日前までの日付を指定してください。たとえば、3月31日であれば3月28日を指定します。</li><li>対応する最も古い日付：2020年11月1日</li><li>1回のクエリで指定できる最大期間：90日</li></ul> |
| レート制限 | <ul><li>1回のクエリで最大250,000行を返します。</li><li>1分あたり10回の呼び出し</li></ul> |
| SRNs | <ul><li>Meta広告：データを利用できます。</li><li>Google広告：クリック時刻に基づくGoogleの方式により、インストール後最大45日までインストールが記録される場合があります。 Googleの過去45日分のデータを毎日取得することで、必要なGoogleのSKANデータを網羅できます。</li></ul> |
| アドネットワークのアクセス | 分析パートナーの場合は、広告主に権限の付与を依頼してください。 |
| 代理店のアクセス | 利用不可 |
| アプリ固有のタイムゾーン | UTCのみ |
| アプリ固有の通貨 | 常にUSD |
| オーガニックデータ | SDKがAppsFlyerに直接報告した全データから、SKANポストバックが報告したノンオーガニックデータを差し引いて算出します。 |
| ノンオーガニックデータ | AppsFlyerが受信したSKANポストバックを使用して算出します。 |
| 過去のデータ | 対応する最も古いコンバージョンデータ（インストールまたはリターゲティング）：2020年11月1日 |
| アカウントユーザーのアクセス | 認証トークンは、管理者ユーザーがダッシュボードで取得できます。 |
| 総コスト | 通常のアトリビューション（通常のOverview）にSKANキャンペーンが含まれ、その最も細かい粒度（広告、国、サイトIDなど）のデータが50,000行を超える場合、SKAN APIに総コスト指標が含まれないことがあります。 |

</Accordion>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=skan%E9%9B%86%E8%A8%88%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88api h_01HH9WHP1SDQ3TJPZ931R9KWKH=skan%E9%9B%86%E8%A8%88%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88api h_01HH9WHP1S7PWJHKAKHN434G7Y=using-skan-aggregated-performance-report-api parameters=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HH9WHP1SZQZGSZ4WEPAAFNV7=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HH9WHP1SYEHGJBBWSMS2XQP0=report-structure-and-example skadnetwork-aggregate-report-structure=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 h_01HH9WHP1STYNJK3DRESDF23DG=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 h_01HH9WHP1T4NEMW56XVYKM3KHM=specifications-and-limitations" />

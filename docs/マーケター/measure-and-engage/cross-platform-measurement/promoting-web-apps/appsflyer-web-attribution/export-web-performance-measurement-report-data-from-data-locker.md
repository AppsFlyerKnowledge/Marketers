---
title: Web Performance Measurement｜Data Locker経由でのレポートデータ出力
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T10:49:59Z'
  edited_at: '2026-10-14T09:23:14Z'
  id: 43510758321809
  locale: ja
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ja/articles/43510758321809
---
> **概要：** Data LockerからWeb Performance Measurementのデータを2種類のレポート形式で出力できます。Webサイトのパフォーマンスを目的に応じた粒度で分析できます。エンドユーザーイベントレポートはすべての訪問およびイベントの分析に、コンバージョンレポートは初回訪問、再訪問、ユーザー獲得イベントなど、コンバージョンの起点となったイベントの集計およびアトリビューション分析に利用します。

> ❗️ **Warning**
>
> **重要**Data LockerでWeb Performance Measurementのレポートを利用するには、Data Lockerの契約が必要です。

<div id="about-the-web-performance-measurement-reports" />

## Web Performance Measurementのレポートについて

Data Lockerでは、Web Performance Measurement向けに**エンドユーザーイベント**と**コンバージョン**の2種類のレポートを提供しています。それぞれ用途が異なります。

* **エンドユーザーイベント**レポートは、Webサイト上のアクティビティを分析するためのレポートです。
  * **すべてのWebイベントおよびWeb訪問**が含まれます。
  * すべての訪問は、アトリビューション済みの`SESSION`として記録されます。
  * **訪問単位**および**イベント単位**での分析に適しています。
* **コンバージョン**レポートは、コンバージョン単位で分析する場合に適しています。コンバージョンとは、マーケティング成果をいつ、どのように紐づけさせるかを決定するアトリビューションアンカー（成果紐づけの起点となるタッチポイント）です。具体的には以下が含まれます：
  * *初回訪問*（ユーザーが初めてWebサイトへアクセスした場合）
  * *再訪問*（非オーガニック広告へのエンゲージメント後にユーザーが再訪した場合）
  * *ユーザー獲得イベント*（会員登録や初回入金など、ユーザー獲得を示すカスタムイベント）
* その後に発生するすべてのユーザーイベントは、これらのコンバージョンに紐づけられ、対応するキャンペーン情報を引き継ぎます。

Data LockerのアドバンスレポートのUIでは、**エンゲージメント**と**エンドユーザーイベント（クロスプラットフォーム）が**、Web Performance Measurementのレポートとして、それぞれ個別に選択できます。本記事では、Web Performance Measurementの分析で主に使用する、**エンドユーザーイベント**と**コンバージョン**の2つのレポートについて説明します。

<div id="select-a-web-performance-measurement-report" />

## Web Performance Measurementレポートの選択

Web Performance Measurementのデータをエクスポートするには、まずData Lockerで対象のレポートを選択します。

1. AppsFlyer管理画面 左メニュー **エクスポート > Data Locker**へ移動します。
2. <strong>「アドバンスレポート」</strong>タブをクリックしてください。
3. Web Performance Measurementレポートの一覧から、**エンドユーザーイベント**または**コンバージョン**を選択します。
4. <strong>Save Configuration（設定を保存）</strong>をクリックします。

<div id="report-fields" />

## レポート項目

各レポートに含まれる項目については、以下のサンプルをダウンロードして確認できます。

* [エンドユーザーイベントレポートのサンプル](https://docs.google.com/spreadsheets/d/e/2PACX-1vQYFF0r4pMpo_voSK8QObpiRtx-diU_0a-0XVuKIVMEfh6rRPudIDXA5bgDw_lcc0qwBPcPhYtLdWwh/pub?output=csv)
* [コンバージョンイベントレポートのサンプル](https://docs.google.com/spreadsheets/d/e/2PACX-1vTMqcc6PKBATBg1DYVO8MWKrAs_wlqXxyANe3a_gu62xp3hFZV9wWT1X8c9oRekaIEwCfKZ2y9agVeV/pub?output=csv)

サンプルレポートには、利用可能なすべてのレポート項目とその値が含まれています。各項目の定義については、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">項目一覧</Anchor>を参照してください。

<div id="report-timing-and-data-freshness" />

## レポート作成タイミングとデータの更新頻度

以下では、新しいデータがいつ追加されるか、およびイベントがレポートへ反映されるタイミングについて説明します。

* **レポートの作成頻度**：新しいデータは1時間ごとに追加されます。
* **データの更新頻度：** イベントは通常、発生から2～3時間以内にレポートへ反映されます。

<div id="heres-how-each-batch-works" />

### 各バッチ処理は以下のように動作します：

* 1回のバッチ処理では、1時間30分分のイベントを**処理します。**
* このうち最初の1時間分のイベントのみが**アトリビューション対象**となります。
* 残り30分間は、アトリビューション済みイベントへCustomer User ID（CUID）を**付与するためだけに使用**されます。
* 直近30分間に発生したイベントは**まだアトリビューションされず**、次回のバッチ処理で処理されます。

[![](https://files.readme.io/1957b8b0c6b29fb44934ef7d10fd04278d541a4f2c12bb90e49fc8cb61ec7db5-44460048223761.png)](https://files.readme.io/1957b8b0c6b29fb44934ef7d10fd04278d541a4f2c12bb90e49fc8cb61ec7db5-44460048223761.png)

<div id="when-will-these-events-appear-in-the-report" />

### イベントはいつレポートへ反映されますか？

イベントは、**バッチ処理が完了した後**にレポートへ出力されます。例えば、**08:00～09:00**に発生したイベントは、10:00のバッチでアトリビューションされ、**11:00のバージョンレポート**に反映されます。

<div id="example-what-the-1000-am-batch-does" />

### 例：AM10:00のバッチ処理の内容

| **日付** | **レポート利用可能時刻** | **アトリビューション対象となるWebイベント（イベント発生時刻）** | **CUID付与のために処理されるWebイベント** |
| --- | --- | --- | --- |
| 2026-01-28 | 11:00 | 08:00 – 09:00 | 09:00 – 09:30 |
| 2026-01-28 | 12:00 | 09:00 – 10:00 | 10:00 – 10:30 |
| 2026-01-28 | 13:00 | 10:00 – 11:00 | 10:00 – 11:30 |

<div id="download-report-data-from-your-cloud-bucket" />

## クラウドバケットからのレポートダウンロード

クラウドストレージからのレポートデータへのダウンロード方法については、「<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#folder-structure">Data Lockerのフォルダ構造</Anchor>」を参照してください。

<div id="bi-developer-considerations" />

## BI開発者向けの考慮事項

<Accordion title="主な違い：Web 対モバイル">

Webアトリビューションは、識別子およびデータの取り扱いの両方において、モバイルアトリビューションとは異なります。データの正確性を高めるため、クエリでは以下のフィルターおよびベストプラクティスを適用してください。

| 項目 | モバイル | Web |
| --- | --- | --- |
| プラットフォームフィルター | `platform = 'IOS'` または `platform = 'ANDROID’` | `platform = 'WEBSITE'` |
| ユーザー識別子（値） | `appsflyer_id`（デバイスベース） | `appsflyer_id_value`（Cookieベース） |
| 識別子の種類 | デバイスによって異なる | `appsflyer_id_type`は常に`web_id` |
| ユーザー獲得イベント | Install | 初回訪問（First Visit）がデフォルトですが、ユーザー獲得イベントはカスタマイズ可能 |
| リエンゲージメント | `RE-ENGAGEMENT` | `REVISIT` |
| リアトリビューション | 対応 | 非対応（Webではユーザー獲得と再訪問のみ） |
| アプリID | App ID（例：`id123456789`） | 接頭辞のあるドメイン（例：`website-www.example.com`） |

</Accordion>

<Accordion title="どのテーブルを使用すべきか">

**エンドユーザーイベント**レポートは、ほとんどの分析用途に適しています。このレポートには、すべてのWebイベントとWeb訪問が含まれています。また、すべてのWeb訪問はアトリビューション済みの`SESSION`として記録されるため、訪問単位およびイベント単位の分析における主要なデータソースとなります。

一方、コンバージョンのテーブルは、重複したイベントレコードを含めずに、初回訪問、再訪問、およびユーザー獲得を集計したい場合に適しています。

| 利用目的 | 使用するテーブル | 理由 |
| --- | --- | --- |
| 訪問数／セッション数を集計する | `end_user_events` | 各行がセッションまたはイベントを表すため |
| 一意のコンバージョン数を集計する | `conversions` | 重複レコードを排除できるため |
| アプリ内イベントを分析する | `end_user_events` （`end_user_event_type = 'IN_APP'`） | イベント名を持つのはアプリ内イベントのみであるため |

</Accordion>

<Accordion title="クエリフィルターの適用">

ローデータを正確に分析するため、以下のフィルターを適用してください。これらを適用しない場合、重複レコードや異なるプラットフォームのデータが混在し、正確な集計結果が得られません。

* **プラットフォームでフィルターする（必須）：** Web由来のデータのみを対象とし、モバイル、PC、CTVのデータを除外するため、以下の条件を指定してください：`WHERE platform = 'WEBSITE'`
* **アトリビューションの帰属でフィルターする（必須）：** AppsFlyerでは、同じユーザーアクションが`end_user_events`に2回記録される場合があります。 これは、レポートビューによって異なるアトリビューションを付与できるためです。

  この状況は、ユーザーに以下の両方が存在する場合に発生します：

  * 元の<strong>ユーザー獲得（UA）</strong>経由の流入
  * その後の**リエンゲージメント経由**の流入

  この場合、AppsFlyerは同じイベントについて2つのレコードを書き込みます。

  * **Primary Attribution：** イベントを、最も直近のマーケティング接点へ紐づけます。これは統合ビューとリターゲティングビューで使用されます。

    `end_user_events`の重複集計を防ぐため、通常は以下の条件でPrimary Attributionのみを取得してください：

    ```sql
    WHERE platform = 'WEBSITE'
      AND is_primary_attribution = true
    ```
  * **Secondary Attribution：** イベントを元のユーザー獲得（UA）へアトリビューションします。ユーザー獲得ビューでLTVを分析する際に使用されます。

    同じイベントがPrimary AttributionとSecondary Attributionの2つのレコードとして保存されるため、フィルターを指定せずに集計すると重複カウントになります。

    以下のクエリを、BigQueryなどのBIツールでWebアトリビューションデータを分析する際のテンプレートとして利用してください。

* **コンバージョンタイプでフィルターする（任意）：** キャンペーン種別ごとに分析する場合は、以下の条件を指定します： `WHERE conversion_type = 'USER_ACQUISITION'` または `WHERE conversion_type = 'RETARGETING'`

<div id="filter-summary-table" />

#### フィルター一覧

| フィルター | SQL条件 | 利用シーン |
| --- | --- | --- |
| プラットフォーム指定 | `WHERE platform = 'WEBSITE'` | Web由来のデータのみを対象とし、他プラットフォームのデータを除外します。 |
| 統合ビュー（重複防止） | `WHERE is_primary_attribution = true AND platform = 'WEBSITE'` | 元のUAキャンペーンよりもリターゲティングキャンペーンへの成果紐づけを優先します。重複を避けた一般的なレポートに使用します。 |
| リターゲティングビューのみ | `WHERE conversion_type = 'RETARGETING' AND platform = 'WEBSITE'` | リターゲティングキャンペーンのみを分析する場合に使用します。 |
| ユーザー獲得ビューのみ | `WHERE conversion_type = 'USER_ACQUISITION' AND platform = 'WEBSITE'` | 初回訪問に紐づくイベントのみを分析するユーザー獲得レポートで使用します。 |

</Accordion>

<Accordion title="エンドユーザーの識別と集計">

Web Performance Measurementのローデータでは、エンドユーザーが以下の2つの異なる識別子で表示される場合があります。

* `customer_user_id`：お客様が設定する安定した識別子です。通常、ログイン済みユーザーに使用されます。
* `appsflyer_id_value`:CookieベースのIDで、時間の経過とともに失効する場合があります。

**ユニークユーザー**を正しく識別し、**ユーザーレベルの指標**を計算するには、必ず以下を使用してください。

```sql
COALESCE(customer_user_id, appsflyer_id_value)
```

仕組みは以下の通りです。

* `customer_user_id` が存在する場合、AppsFlyerはそれを使用します（安定した識別子であるため優先されます）。
* 存在しない場合、AppsFlyerは`appsflyer_id_value`へフォールバックします。

以下を行う場合は、必ず `COALESCE(customer_user_id, appsflyer_id_value)` を使用してください。

* ユニークユーザー数を集計する
* ユーザー単位でグループ化する
* 特定のユーザーでフィルタリングする
* ユーザー単位でテーブルを結合する
* ユーザーレベルの指標を計算する

<div id="example-count-distinct-users" />

#### 例：ユニークユーザー数を集計する

```sql
SELECT 
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users
FROM `end_user_events`
WHERE platform = 'WEBSITE'
  AND is_primary_attribution = TRUE
```

</Accordion>

<Accordion title="オーガニック vs.非オーガニックトラフィック">

`is_organic`のフィールドを使用します：

| トラフィックタイプ | フィルタ |
| --- | --- |
| オーガニック | `is_organic = true` |
| 非オーガニック | `is_organic = false` |

</Accordion>

<Accordion title="空の値の扱い">

| データ型 | 空の値 |
| --- | --- |
| 文字列 | `''`（空文字列） |
| 数値 | `NULL` |

</Accordion>

<Accordion title="クエリ例">

<Accordion title="1. メディアソース別の総訪問数（過去7日間）">

各メディアソースにアトリビューションされたWebセッション数を集計します。

```sql
SELECT media_source, COUNT(*) AS total_visits
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'SESSION'
GROUP BY media_source
ORDER BY total_visits DESC
```

</Accordion>

<Accordion title="2. キャンペーン別の初回訪問と再訪問">

```sql
SELECT campaign_name, conversion_name, COUNT(*) AS conversion_count
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name IN ('FIRST_VISIT', 'REVISIT')
GROUP BY campaign_name, conversion_name
ORDER BY conversion_count DESC
```

</Accordion>

<Accordion title="3.イベント名別の集計（アプリ内イベントのみ）">

```sql
SELECT
  event_name,
  COUNT(*) AS event_count
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'IN_APP'
GROUP BY event_name
ORDER BY event_count DESC
```

</Accordion>

<Accordion title="4.メディアソース別のユニークユーザー数">

```sql
SELECT
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
GROUP BY media_source
ORDER BY unique_users DESC
```

</Accordion>

<Accordion title="5.コンバージョン率：初回訪問から購入まで（テーブル横断の結合）">

```sql
WITH first_visits AS (
  SELECT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id,
    media_source
  FROM conversions
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND conversion_name = 'FIRST_VISIT'
),
purchases AS (
  SELECT DISTINCT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id
  FROM end_user_events
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND is_primary_attribution = true
    AND end_user_event_type = 'IN_APP'
    AND event_name = 'purchase'
)
SELECT
  fv.media_source,
  COUNT(DISTINCT fv.user_id) AS first_visit_users,
  COUNT(DISTINCT p.user_id) AS purchasers,
  SAFE_DIVIDE(COUNT(DISTINCT p.user_id), COUNT(DISTINCT fv.user_id)) AS conversion_rate
FROM first_visits fv
LEFT JOIN purchases p ON fv.user_id = p.user_id
GROUP BY fv.media_source
ORDER BY conversion_rate DESC
```

</Accordion>

<Accordion title="6.キャンペーン別の売上（過去7日間）">

```sql
SELECT
  campaign_name,
  media_source,
  SUM(revenue_usd) AS total_revenue_usd,
  COUNT(*) AS revenue_events
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND revenue_usd IS NOT NULL
  AND revenue_usd <> 0.0
GROUP BY campaign_name, media_source
ORDER BY total_revenue_usd DESC
```

</Accordion>

<Accordion title="7.日別のオーガニック／非オーガニック初回訪問">

```sql
SELECT
  DATE(event_time) AS visit_date,
  CASE WHEN is_organic = true THEN 'Organic' ELSE 'Non-Organic' END AS traffic_type,
  COUNT(*) AS first_visits
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name = 'FIRST_VISIT'
GROUP BY visit_date, traffic_type
ORDER BY visit_date, traffic_type
```

</Accordion>

<Accordion title="8. ユーザー獲得 (UA)リターゲティングの内訳">

```sql
SELECT
  conversion_type,
  conversion_name,
  COUNT(*) AS conversions
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
GROUP BY conversion_type, conversion_name
ORDER BY conversions DESC
```

</Accordion>

<Accordion title="9.クリックIDの分布（Google、Meta、TikTokなど）">

```sql
SELECT
  click_id_type,
  COUNT(*) AS events_with_click_id
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND click_id_type != ''
GROUP BY click_id_type
ORDER BY events_with_click_id DESC
```

</Accordion>

<Accordion title="10.コンバージョン日別のコホートユーザー数（モバイルのインストール日に相当）">

```sql
SELECT
  DATE(event_time__conversion) AS cohort_date,
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS cohort_users
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
GROUP BY cohort_date, media_source
ORDER BY cohort_date, cohort_users DESC
```

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

## 仕様および制限事項

以下のフィールドは**Webデータではサポートされておらず**、常に空の値となります。

| 項目 | 説明 |
| --- | --- |
| `advertising_id_type`、`hardware_id_type`など | 両方のレポート |
| `agency`、`site_id`、`ad_type` | 両方のレポート |
| `platform_group` | コンバージョン |
| `app_version__conversion` | エンドユーザーイベント |
| すべての `__assist_*` フィールド | コンバージョン |

<div id="see-also" />

## 関連情報：

* <Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">Data Lockerのアドバンスレポートについて</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">Data Locker — マーケティング担当者向け</Anchor>

<div data-zendesk-anchors="about-the-data-locker-web-attribution-reports=web-performance-measurement%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KGM4FT90X1K2V8M8GJV6EW5K=web-performance-measurement%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01_select-web-performance-measurement-report=web-performance-measurement%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%81%B8%E6%8A%9E select-a-web-performance-measurement-report=web-performance-measurement%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%81%B8%E6%8A%9E report-fields=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E9%A0%85%E7%9B%AE h_01KGM4FT90WP73N1D75WWNT2TE=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E9%A0%85%E7%9B%AE report-timing-and-data-freshness=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E4%BD%9C%E6%88%90%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0%E3%81%A8%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%9B%B4%E6%96%B0%E9%A0%BB%E5%BA%A6 h_01KGM4FT90B6W7KBS9K1FSSETD=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E4%BD%9C%E6%88%90%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0%E3%81%A8%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%9B%B4%E6%96%B0%E9%A0%BB%E5%BA%A6 here%E2%80%99s-how-each-batch-works=%E5%90%84%E3%83%90%E3%83%83%E3%83%81%E5%87%A6%E7%90%86%E3%81%AF%E4%BB%A5%E4%B8%8B%E3%81%AE%E3%82%88%E3%81%86%E3%81%AB%E5%8B%95%E4%BD%9C%E3%81%97%E3%81%BE%E3%81%99 h_01KGM4FT91MCGCBYSHE18JHQ96=%E5%90%84%E3%83%90%E3%83%83%E3%83%81%E5%87%A6%E7%90%86%E3%81%AF%E4%BB%A5%E4%B8%8B%E3%81%AE%E3%82%88%E3%81%86%E3%81%AB%E5%8B%95%E4%BD%9C%E3%81%97%E3%81%BE%E3%81%99 when-will-these-events-appear-in-the-report=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AF%E3%81%84%E3%81%A4%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E5%8F%8D%E6%98%A0%E3%81%95%E3%82%8C%E3%81%BE%E3%81%99%E3%81%8B h_01KGM4FT91XF7HCM8E8TQ56D0D=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AF%E3%81%84%E3%81%A4%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%B8%E5%8F%8D%E6%98%A0%E3%81%95%E3%82%8C%E3%81%BE%E3%81%99%E3%81%8B example-what-the-1000-am-batch-does=%E4%BE%8Bam1000%E3%81%AE%E3%83%90%E3%83%83%E3%83%81%E5%87%A6%E7%90%86%E3%81%AE%E5%86%85%E5%AE%B9 h_01KGM4FT91D90DWYGSE3SES2ZY=%E4%BE%8Bam1000%E3%81%AE%E3%83%90%E3%83%83%E3%83%81%E5%87%A6%E7%90%86%E3%81%AE%E5%86%85%E5%AE%B9 download-report-data-from-your-cloud-bucket=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%81%8B%E3%82%89%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%80%E3%82%A6%E3%83%B3%E3%83%AD%E3%83%BC%E3%83%89 h_01KGM4FT91NECKXMDW60A4B9X5=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%81%8B%E3%82%89%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%80%E3%82%A6%E3%83%B3%E3%83%AD%E3%83%BC%E3%83%89 bi-developer-considerations=bi%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 h_01KGM4FT91C2KP050ZAYW6K8FD=bi%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 filter-summary-table=%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC%E4%B8%80%E8%A6%A7 h_01KGM4FT91MSN2SN7TKNJZ54V4=%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC%E4%B8%80%E8%A6%A7 example-count-distinct-users=%E4%BE%8B%E3%83%A6%E3%83%8B%E3%83%BC%E3%82%AF%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%95%B0%E3%82%92%E9%9B%86%E8%A8%88%E3%81%99%E3%82%8B h_01KGM4FT91VDR0FWTMAPW6GM83=%E4%BE%8B%E3%83%A6%E3%83%8B%E3%83%BC%E3%82%AF%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%95%B0%E3%82%92%E9%9B%86%E8%A8%88%E3%81%99%E3%82%8B traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%8A%E3%82%88%E3%81%B3%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KGM4FT91QZR30KJAQ87AG691=%E4%BB%95%E6%A7%98%E3%81%8A%E3%82%88%E3%81%B3%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01_web-perf-see-also=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1 see-also=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />

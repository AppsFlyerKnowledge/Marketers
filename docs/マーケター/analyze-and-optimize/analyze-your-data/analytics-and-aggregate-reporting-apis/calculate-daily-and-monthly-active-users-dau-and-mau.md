---
title: 日次アクティブユーザー数（DAU）と月次アクティブユーザー数（MAU）の計算方法
metadata:
  keywords:
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2025-09-15T15:49:21Z'
  edited_at: '2026-10-14T09:24:37Z'
  id: 39071744864657
  locale: ja
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ja/articles/39071744864657
---
> **概要：** キャンペーンに関する貴重な洞察を得るために、日次アクティブユーザー数と月次アクティブユーザー数の計算方法を学びましょう

<div id="overview" />

## 概要

日次アクティブユーザー数（DAU）と月次アクティブユーザー数（MAU）は、アプリのエンゲージメントと全体的なユーザー行動を理解するための重要な指標です。これらは、ユーザーの定着率、キャンペーンのパフォーマンス、時間の経過に伴う成長傾向など、アクティブユーザーベースに関する貴重な洞察を提供します。

この記事では、ユーザー獲得とリターゲティングトラフィックを表す2つのData Locker生データテーブル（ `sessions` および `sessions_retargeting` テーブル）のクエリを使用して、DAUとMAUを計算する方法について説明します。

<div id="note" />

> 📘 **注**
>
> 2025年2月から、AppsFlyerのアクティビティダッシュボードには、デフォルトで統合（UAおよびリターゲティング）データが表示されます。生データとダッシュボードの数値の間にわずかな差があることがありますが、これは <Anchor target="_blank" href="/marketers/ja/docs/activity-metrics-in-my-dashboards#仕様と制限事項">承認されたアルゴリズムの調整</Anchor>.

<div id="querying-for-active-unique-users" />

### アクティブなユニークユーザーのクエリ

ユニークユーザー数を計算するには、以下の方法を使用します。 `advertising_id` クエリ内の主要な識別子として。もし `advertising_id` 利用できない場合は、に置き換えてください。 `appsflyer_id`.この方法は、以下の設定のアプリにのみ適用されます。 <Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls#attributed-to-the-first-install">初回インストールモード</Anchor>.

このモードを使用しないアプリには、適用をお勧めします。 `count(distinct appsflyer_id)` その代わりに。

<div id="calculate-daily-active-users-dau" />

## 日次アクティブユーザー数（DAU）の計算

以下のクエリを使用して、1日あたりの一意のユーザー数を計算します。

<div id="query-for-dau---user-acquisition-ua" />

<Accordion title="DAU用クエリ - ユーザー獲得（UA）">

指定された日のアクティブなUAユーザーを選択します。

```sql
WITH sessions_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'                      -- Replace with your app ID
		    AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'       -- Target date                 
)

SELECT COUNT(DISTINCT user_id) AS dau_ua
FROM sessions_cleaned;
```

</Accordion>

<div id="query-for-dau---retargeting" />

<Accordion title="DAU用クエリ - リターゲティング">

指定された日のアクティブなリターゲティングユーザーを選択します。

```sql
WITH sessions_retargeting_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'                      -- Replace with your app ID
		    AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'   -- Target date                 
)
SELECT COUNT(DISTINCT user_id) AS dau_retargeting
FROM sessions_retargeting_cleaned;
```

</Accordion>

<div id="query-for-dau---unified-ua-retargeting" />

<Accordion title="DAU用クエリ - ユニファイド（UA & リターゲティング）">

指定された日数のアクティブUAとリターゲティングユーザーを選択してください。

完全なアクティブユーザーカバレッジを得るには、 **union** the `sessions` and `sessions_retargeting` テーブルフィールドが揃っていることを確認してください。通常は 、IF 必要に応じて、両方のテーブルが一貫したスキーマを持つようにスキーマを正規化してください。 カラム名

```sql
WITH ua_sessions AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'                 -- Replace with your app ID
      AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'    -- Target date           
      AND is_primary_attribution = TRUE
),

retargeting_sessions AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'                  -- Same app
      AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'     -- Same date
),

all_sessions AS (
    SELECT * FROM ua_sessions
    UNION ALL
    SELECT * FROM retargeting_sessions
)

SELECT COUNT(DISTINCT user_id) AS dau_unified
FROM all_sessions;
```

</Accordion>

<div id="calculate-monthly-active-users-mau" />

## **MAU（1か月あたりのアクティブユーザー数）の算出方法**

AppsFlyerダッシュボードでは、MAUを2つの方法で表示します。

1. **過去31日間のアクティブユーザー数** - 過去31日間のユニークアクティブユーザー数。
2. **カレンダー月間MAU** – 特定の暦月内のユニークなアクティブユーザー数。

以下のクエリは、MAUの最初のタイプを計算する方法を示しています。代わりに暦月MAUを計算するには、希望の月と一致するよう日付範囲を調整するだけです。

<div id="query-for-mau---user-acquisition-ua" />

<Accordion title="MAUに関するクエリ - ユーザー獲得（UA）">

指定された月のアクティブなUAユーザーを選択します。

```sql
WITH sessions_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'  -- Replace with your app ID
			AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date 
)
SELECT COUNT(DISTINCT user_id) AS mau_ua
FROM sessions_cleaned;
```

</Accordion>

<div id="query-for-mau---retargeting" />

<Accordion title="MAUに関するクエリ - リターゲティング">

指定された月のアクティブなリターゲティングユーザーを選択します。

```sql
WITH sessions_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'  -- Replace with your app ID
			AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date 
)

SELECT COUNT(DISTINCT user_id) AS mau_retargeting
FROM sessions_cleaned;
```

</Accordion>

<div id="query-for-mau---unified-ua-retargeting" />

<Accordion title="MAUに関するクエリ - 統合（UA & リターゲティング）">

指定された月のアクティブなUAユーザーとリターゲティングユーザーを選択します。

完全なアクティブユーザーカバレッジを得るには、 **union** the `sessions` and `sessions_retargeting` テーブルフィールドが揃っていることを確認してください。通常は 、IF 必要に応じて、両方のテーブルが一貫したスキーマを持つようにスキーマを正規化してください。 カラム名

```sql
WITH ua_sessions AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'                        -- Replace with your app ID
      AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date        
      AND is_primary_attribution = TRUE
),

retargeting_sessions AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'                        -- Same app 
      AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date
),

all_sessions AS (
    SELECT * FROM ua_sessions
    UNION ALL
    SELECT * FROM retargeting_sessions
)

SELECT COUNT(DISTINCT user_id) AS mau_unified
FROM all_sessions;
```

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01K58WFCYQJE3JVR6Q4G5P1T3V=%E6%A6%82%E8%A6%81 h_01K58WFCYQSX0YTSGWBC02TCG1=%E6%B3%A8 querying-for-active-unique-users=%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%81%AA%E3%83%A6%E3%83%8B%E3%83%BC%E3%82%AF%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%82%AF%E3%82%A8%E3%83%AA h_01K58WFCYQ942VY9P70GHVG6SH=%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%81%AA%E3%83%A6%E3%83%8B%E3%83%BC%E3%82%AF%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%82%AF%E3%82%A8%E3%83%AA calculate-daily-active-users-dau=%E6%97%A5%E6%AC%A1%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%95%B0dau%E3%81%AE%E8%A8%88%E7%AE%97 h_01K58WFCYQ406CW66EEYPP5GFJ=%E6%97%A5%E6%AC%A1%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%95%B0dau%E3%81%AE%E8%A8%88%E7%AE%97 query-for-dau-%E2%80%93-user-acquisition-ua=query-for-dau---user-acquisition-ua h_01K58WFCYQVXBZN97BWHA8FC3C=query-for-dau---user-acquisition-ua query-for-dau-%E2%80%93-retargeting=query-for-dau---retargeting h_01K58WFCYQ4XNKQ9CW4D3KV2E2=query-for-dau---retargeting query-for-dau-%E2%80%93-unified-ua-retargeting=query-for-dau---unified-ua-retargeting h_01K58WFCYQ0NM0E44531YDJBCH=query-for-dau---unified-ua-retargeting calculate-monthly-active-users-mau=mau1%E3%81%8B%E6%9C%88%E3%81%82%E3%81%9F%E3%82%8A%E3%81%AE%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%95%B0%E3%81%AE%E7%AE%97%E5%87%BA%E6%96%B9%E6%B3%95 h_01K58WFCYQ251WMSNSD0EYXV69=mau1%E3%81%8B%E6%9C%88%E3%81%82%E3%81%9F%E3%82%8A%E3%81%AE%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%95%B0%E3%81%AE%E7%AE%97%E5%87%BA%E6%96%B9%E6%B3%95 query-for-mau-%E2%80%93-user-acquisition-ua=query-for-mau---user-acquisition-ua h_01K58WFCYQAV6T3S7SABSTMYKS=query-for-mau---user-acquisition-ua query-for-mau-%E2%80%93-retargeting=query-for-mau---retargeting h_01K58WFCYQ4H5CFQPPC5JQKHTJ=query-for-mau---retargeting query-for-mau-%E2%80%93-unified-ua-retargeting=query-for-mau---unified-ua-retargeting h_01K58WFCYQA1W91CHM1PN31MFG=query-for-mau---unified-ua-retargeting" />

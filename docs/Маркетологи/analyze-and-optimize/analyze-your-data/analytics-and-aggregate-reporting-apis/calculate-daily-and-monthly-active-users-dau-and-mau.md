---
title: Рассчитайте количество активных пользователей за день/месяц (DAU и MAU)
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
  edited_at: '2026-08-18T00:02:52Z'
  id: 39071744864657
  locale: ru
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ru/articles/39071744864657
---
> **Краткий обзор:** Узнайте, как рассчитывать количество активных пользователей в день и в месяц, чтобы получить важные данные о ваших кампаниях

<div id="overview" />

## Обзор

Показатели «Активные пользователи в день» (DAU) и «Активные пользователи в месяц» (MAU) -- ключевые метрики для оценки вовлечённости в приложении и общего поведения пользователей. Они предоставляют ценные сведения о вашей активной базе пользователей, такие как коэффициент удержания пользователей, эффективность кампаний и динамика роста во времени.

Эта статья поясняет, как рассчитать DAU и MAU с помощью запросов к двум таблицам необработанных данных **Premium** Data Locker, которые отражают трафик привлечения пользователей и ретаргетинга: таблицы `sessions` и `sessions_retargeting`.

<div id="note" />

> 📘 **Примечание**
>
> Начиная с февраля 2025 года, в панели «Активность» в AppsFlyer по умолчанию отображаются объединенные данные (UA и ретаргетинг). Вы можете заметить небольшую разницу между сырыми показателями и данными панели из-за <Anchor target="_blank" href="/marketers/ru/docs/activity-metrics-in-my-dashboards#спецификации-и-ограничения">утвержденных алгоритмических корректировок</Anchor>.

<div id="querying-for-active-unique-users" />

### Запрос активных уникальных пользователей

Чтобы рассчитать количество уникальных пользователей, используйте `advertising_id` в качестве основного идентификатора в вашем запросе. Если `advertising_id` недоступен, замените его на `appsflyer_id`. Этот метод применяется только к приложениям, настроенным в <Anchor target="_blank" href="/marketers/ru/docs/measure-reinstalls#attributed-to-the-first-install">режиме первичной установки</Anchor>.

Для приложений, не использующих этот режим, мы рекомендуем использовать вместо этого `count(distinct appsflyer_id)`.

<div id="calculate-daily-active-users-dau" />

## Рассчет количества ежедневных активных пользователей (DAU)

Рассчитайте общее количество уникальных пользователей в день, используя приведенные ниже запросы.

<div id="query-for-dau---user-acquisition-ua" />

<Accordion title="Запрос для DAU – Привлечение пользователей (UA)">

Выберите активных пользователей UA за указанный день.

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

<Accordion title="Запрос для DAU – Ретаргетинг">

Выберите активных пользователей ретаргетинга за указанный день.

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

<Accordion title="Запрос для DAU – Объединенные (UA и Ретаргетинг)">

Выберите активных пользователей UA и ретаргетинга за указанный день.

Чтобы получить полный охват активных пользователей, необходимо **объединить** `sessions` и таблицы `sessions_retargeting` . Убедитесь, что поля выровнены — обычно по `app_id`, `event_time`, `advertising_id` и `appsflyer_id`. При необходимости нормализуйте схему, чтобы в обеих таблицах были одинаковые названия столбцов.

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

## **Рассчет количества активных пользователей в месяц (MAU)**

Панели управления AppsFlyer представляют MAU в двух форматах:

1. **Активные пользователи за последние 31 день** – количество уникальных активных пользователей за последние 31 день.
2. **MAU за календарный месяц** – количество уникальных активных пользователей в течение конкретного календарного месяца.

Следующие запросы показывают, как рассчитать первый тип MAU. Чтобы рассчитать MAU за календарный месяц, просто измените диапазон дат, чтобы он соответствовал запрашиваемому месяцу.

<div id="query-for-mau---user-acquisition-ua" />

<Accordion title="Запрос для MAU – Привлечение пользователей (UA)">

Выберите активных пользователей UA за указанный месяц.

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

<Accordion title="Запрос для MAU – Ретаргетинг">

Выберите активных пользователей ретаргетинга за указанный месяц.

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

<Accordion title="Запрос для MAU – Объединенный (UA и Ретаргетинг)">

Выберите активных пользователей UA и ретаргетинга за указанный месяц.

Чтобы получить полный охват активных пользователей, необходимо **объединить** `sessions` и таблицы `sessions_retargeting` . Убедитесь, что поля выровнены — обычно по `app_id`, `event_time`, `advertising_id` и `appsflyer_id`. При необходимости нормализуйте схему, чтобы в обеих таблицах были одинаковые названия столбцов.

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

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01K58WFCYQJE3JVR6Q4G5P1T3V=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01K58WFCYQSX0YTSGWBC02TCG1=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 querying-for-active-unique-users=%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D1%85-%D1%83%D0%BD%D0%B8%D0%BA%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 h_01K58WFCYQ942VY9P70GHVG6SH=%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D1%85-%D1%83%D0%BD%D0%B8%D0%BA%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 calculate-daily-active-users-dau=%D1%80%D0%B0%D1%81%D1%81%D1%87%D0%B5%D1%82-%D0%BA%D0%BE%D0%BB%D0%B8%D1%87%D0%B5%D1%81%D1%82%D0%B2%D0%B0-%D0%B5%D0%B6%D0%B5%D0%B4%D0%BD%D0%B5%D0%B2%D0%BD%D1%8B%D1%85-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-dau h_01K58WFCYQ406CW66EEYPP5GFJ=%D1%80%D0%B0%D1%81%D1%81%D1%87%D0%B5%D1%82-%D0%BA%D0%BE%D0%BB%D0%B8%D1%87%D0%B5%D1%81%D1%82%D0%B2%D0%B0-%D0%B5%D0%B6%D0%B5%D0%B4%D0%BD%D0%B5%D0%B2%D0%BD%D1%8B%D1%85-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-dau query-for-dau-%E2%80%93-user-acquisition-ua=query-for-dau---user-acquisition-ua h_01K58WFCYQVXBZN97BWHA8FC3C=query-for-dau---user-acquisition-ua query-for-dau-%E2%80%93-retargeting=query-for-dau---retargeting h_01K58WFCYQ4XNKQ9CW4D3KV2E2=query-for-dau---retargeting query-for-dau-%E2%80%93-unified-ua-retargeting=query-for-dau---unified-ua-retargeting h_01K58WFCYQ0NM0E44531YDJBCH=query-for-dau---unified-ua-retargeting calculate-monthly-active-users-mau=%D1%80%D0%B0%D1%81%D1%81%D1%87%D0%B5%D1%82-%D0%BA%D0%BE%D0%BB%D0%B8%D1%87%D0%B5%D1%81%D1%82%D0%B2%D0%B0-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%B2-%D0%BC%D0%B5%D1%81%D1%8F%D1%86-mau h_01K58WFCYQ251WMSNSD0EYXV69=%D1%80%D0%B0%D1%81%D1%81%D1%87%D0%B5%D1%82-%D0%BA%D0%BE%D0%BB%D0%B8%D1%87%D0%B5%D1%81%D1%82%D0%B2%D0%B0-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%B2-%D0%BC%D0%B5%D1%81%D1%8F%D1%86-mau query-for-mau-%E2%80%93-user-acquisition-ua=query-for-mau---user-acquisition-ua h_01K58WFCYQAV6T3S7SABSTMYKS=query-for-mau---user-acquisition-ua query-for-mau-%E2%80%93-retargeting=query-for-mau---retargeting h_01K58WFCYQ4H5CFQPPC5JQKHTJ=query-for-mau---retargeting query-for-mau-%E2%80%93-unified-ua-retargeting=query-for-mau---unified-ua-retargeting h_01K58WFCYQA1W91CHM1PN31MFG=query-for-mau---unified-ua-retargeting" />

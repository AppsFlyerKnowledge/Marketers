---
title: Объедините отчеты Cost ETL и когорты
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
  created_at: '2024-08-13T11:05:26Z'
  edited_at: '2026-10-21T13:57:37Z'
  id: 27494360719505
  locale: ru
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ru/articles/27494360719505
---
> **Краткий обзор:** Комбинируйте отчеты Cost ETL и когорты через Data Locker (обычные и расширенные агрегированные), чтобы получить полную картину ваших маркетинговых кампаний с наилучшей доступной актуальностью, точностью и детализацией.

![](https://files.readme.io/46f3cd4c2cfd6ba97caafb788c92ce967d8f304abd7b620968f49095275edf1a-27497862728465.png)

## Об объединении отчетов Cost ETL и когортных отчетов

Отчеты Cost ETL и когортные отчеты через Data Locker (обычные и расширенные агрегированные) обладают своими уникальными свойствами. Например, отчеты Cost ETL включают данные о показах, кликах и затратах, а отчеты когорты — подробные данные об атрибуции, событиях в приложении и доходах.

Лучшая практика заключается в том, что после получения и загрузки в BI-систему отчетов Cost ETL и агрегированных отчетов по когортам, их следует объединить в вашей внутренней BI-системе.

В сочетании друг с другом они:

* Предоставят полную картину эффективности вашего маркетинга с максимальной актуальностью, точностью и детализацией данных.
* Позволят сопоставить внутренние данные в BI с данными, которые вы видите на дэшбордах AppsFlyer.
* Позволят рассчитать такие важные показатели, как рентабельность рекламных расходов (ROAS) и стоимость одного действия (CPA).

## Запросы для объединения отчетов

В последующих разделах представлены запросы и соображения, которые необходимо учитывать при объединении отчетов Cost ETL с другими отчетами:

* [Расширенные агрегированные отчеты по когортам](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-advanced-aggregated-cohort-report)
* [Отчеты по когортам через Data Locker](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-cohort-report)

<div id="query-to-combine-cost-etl-and-advanced-aggregated-cohort-report" />

<Accordion title="Запрос для объединения данных Cost ETL и расширенного агрегированного отчета по когортам">

**Чтобы объединить отчеты Cost ETL и когорты, ваш разработчик BI должен**:

* Используйте следующий запрос в качестве примера, адаптировав его к вашей внутренней системе бизнес-аналитики.
* **Важные замечания**:
  * Настройте запрос:
    * Настройте даты начала и окончания.
    * Настройте названия отчетов.
    * Выберите показатели и метрики в конкретной схеме Cost ETL.
  * Есть различия в актуальности данных в отчетах. Например, Cost ETL обновляется до четырех раз в день, а расширенные агрегированные отчеты по когортам обновляются много раз в день.
  * Расширенные отчеты по когортам включают пользователей, конвертированных за последние 1095 дней. Если они конвертировались до этого, они не учитываются.
  * В отчетах Cost ETL используется часовой пояс данных, указанный в AppsFlyer. Расширенные агрегированные отчеты по когортам включают отчеты по версиям (UTC) и по часовым поясам. **Рекомендация**: Объедините отчеты Cost ETL и отчеты когорты с версиями по часовым поясам.

#### Запрос

```sql
select ag.app_id,
   ag.days_post_attribution,
   ag.conversion_date,
   ag.event_date,
   ag.event_name,
   ag.media_source,
   ag.campaign,
   ag.campaign_id,
   ag.adset,
   ag.adset_id,
   ag.ad,
   ag.ad_id,
   ag.channel,
   ag.site_id,
   ag.keywords,
   ag.geo,
   ag.agency,
   ag.selected_currency as revenue_currency,
   ag.timezone as cohort_timezone,
   cst.timezone as cost_timezone,
   cst.os,     
   cst.ad_account,
   cst.currency as cost_currency,
   cst.original_currency as cost_original_currency,
   cost,
   original_cost,
   impressions as impressions,
   clicks,
   reported_impressions,
   reported_clicks,
   reported_conversions,
   ctr,
   cvr,
   ecpm,
   cpi,
   ccvr,
   cvvr,
   reported_cvr,
   install_diff,
   click_diff,
   impression_diff,
   ecpc,
   video_25p_views,
   video_50p_views,
   video_75p_views,
   video_completions,
   campaign_objective,
   cost_model,
   af_cost_model,
   bid_strategy,
   af_bid_strategy,
   bid_amount,
   original_bid_amount,
   SUM(cast(ag.revenue_selected_currency as double)) as revenue_selected_currency,
   SUM(cast(ag.revenue_usd as double)) as revenue_usd,
   SUM(cast(ag.unique_users as int)) as unique_users,
   SUM(cast(ag.first_inapps as int)) as first_inapps,
   SUM(cast(ag.event_count as int)) as event_count,
   coalesce(SUM(cast(case when ag.event_name = 'af_conversion' and ag.conversion_type = 'install' then ag.event_count end as int)),0) as installs,
   coalesce(SUM(cast(case when ag.event_name = 'af_conversion' and ag.conversion_type = 're-engagement' then ag.event_count end as int)),0) as re_engagements,
   coalesce(SUM(cast(case when ag.event_name = 'af_conversion' and ag.conversion_type = 're-attribution' then ag.event_count end as int)),0) as re_attribution
FROM {YOUR_ADVANCED_AGG_REPORT} as ag
   LEFT JOIN {YOUR_COST_ETL_REPORT} as cst
       ON ag.event_name = 'af_conversion'
           and ag.conversion_date = cst.date
           and ag.app_id = cst.app_id
           and ag.media_source = cst.media_source
           and ag.campaign = cst.campaign
           and ag.campaign_id = cst.campaign_id
           and ag.adset = cst.adset
           and ag.adset_id = cst.adset_id
           and ag.ad = cst.ad
           and ag.ad_id = cst.ad_id
           and ag.channel = cst.channel
           and ag.site_id = cst.site_id
           and ag.keywords = cst.keywords
           and ag.geo = cst.geo
           and ag.agency = cst.agency
WHERE ag.conversion_date between {start date} and {end date}
   and cst.date between {start date} and {end date}
GROUP BY ALL;
```

</Accordion>

<div id="query-to-combine-cost-etl-and-cohort-report" />

<Accordion title="Запрос для объединения отчета Cost ETL и отчета когорты">

**Чтобы объединить отчеты Cost ETL и когорты, ваш разработчик BI должен**:

* Использовать следующий запрос в качестве руководства, адаптируя его под свою внутреннюю BI-систему.
* **Важные примечания**:
  * Настройте запрос:
    * Настройте даты начала и окончания.
    * Настройте названия отчетов.
    * Выберите значения и метрики в конкретной схеме Cost ETL.
  * Есть различия в актуальности данных в отчетах. Например, Cost ETL обновляется до четырех раз в день, а когортные отчеты через Data Locker — один раз в день.
  * В отчетах Cost ETL используется часовой пояс данных, указанный в AppsFlyer. Когортные отчеты через Data Locker используют UTC.

#### Запрос

```sql
select dl.app_id,
   dl.days_post_attribution,
   dl.conversion_date,
   dl.event_date,
   dl.event_name,
   dl.media_source,
   dl.campaign,
   dl.campaign_id,
   dl.adset,
   dl.adset_id,
   dl.ad,
   dl.ad_id,
   dl.channel,
   dl.site_id,
   dl.keywords,
   dl.geo,
   dl.agency,
   dl.selected_currency as revenue_currency,
   cst.timezone as cost_timezone,
   cst.os,          
   cst.ad_account,
   cst.currency as cost_currency,
   cst.original_currency as cost_original_currency,
   cost,
   original_cost,
   impressions as impressions,
   clicks,
   reported_impressions,
   reported_clicks,
   reported_conversions,
   ctr,
   cvr,
   ecpm,
   cpi,
   ccvr,
   cvvr,
   reported_cvr,
   install_diff,
   click_diff,
   impression_diff,
   ecpc,
   video_25p_views,
   video_50p_views,
   video_75p_views,
   video_completions,
   campaign_objective,
   cost_model,
   af_cost_model,
   bid_strategy,
   af_bid_strategy,
   bid_amount,
   original_bid_amount,
   SUM(cast(dl.revenue_selected_currency as double)) as revenue_selected_currency,
   SUM(cast(dl.revenue_usd as double)) as revenue_usd,
   SUM(cast(dl.unique_users as int)) as unique_users,
   SUM(cast(dl.event_count as int)) as event_count,
   coalesce(SUM(cast(case when dl.event_name = 'af_conversion' and dl.conversion_type = 'install' then dl.event_count end as int)),0) as installs,
   coalesce(SUM(cast(case when dl.event_name = 'af_conversion' and dl.conversion_type = 're-engagement' then dl.event_count end as int)),0) as re_engagements,
   coalesce(SUM(cast(case when dl.event_name = 'af_conversion' and dl.conversion_type = 're-attribution' then dl.event_count end as int)),0) as re_attribution
FROM {YOUR_DATA_LOCKER_REPORT} as dl
   LEFT JOIN {YOUR_COST_ETL_REPORT} as cst
       ON dl.event_name = 'af_conversion'
           and dl.conversion_date = cst.date
           and dl.app_id = cst.app_id
           and dl.media_source = cst.media_source
           and dl.campaign = cst.campaign
           and dl.campaign_id = cst.campaign_id
           and dl.adset = cst.adset
           and dl.adset_id = cst.adset_id
           and dl.ad = cst.ad
           and dl.ad_id = cst.ad_id
           and dl.channel = cst.channel
           and dl.site_id = cst.site_id
           and dl.keywords = cst.keywords
           and dl.geo = cst.geo
           and dl.agency = cst.agency
WHERE dl.conversion_date between {start date} and {end date}
   and cst.date between {start date} and {end date}
GROUP BY ALL;
```

</Accordion>

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/advanced-aggregated-reports-in-data-locker">Расширенные агрегированные отчеты в Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/cohort-analytics-via-data-locker">Отчеты по когортам через Data Locker</Anchor>

<div data-zendesk-anchors="about-combining-cost-etl-and-cohort-reports=%D0%BE%D0%B1-%D0%BE%D0%B1%D1%8A%D0%B5%D0%B4%D0%B8%D0%BD%D0%B5%D0%BD%D0%B8%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2-cost-etl-%D0%B8-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D0%BD%D1%8B%D1%85-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2 h_01J55PCC5MJ3MJBESDVEFHT796=%D0%BE%D0%B1-%D0%BE%D0%B1%D1%8A%D0%B5%D0%B4%D0%B8%D0%BD%D0%B5%D0%BD%D0%B8%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2-cost-etl-%D0%B8-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D0%BD%D1%8B%D1%85-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2 queries-to-combine-reports=%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%BE%D0%B1%D1%8A%D0%B5%D0%B4%D0%B8%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2 h_01J55TR3SRXQPRBYRX6G3EJ7D9=%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%BE%D0%B1%D1%8A%D0%B5%D0%B4%D0%B8%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2 h_01J55VAQ804JWE6WT552GY98JF=query-to-combine-cost-etl-and-advanced-aggregated-cohort-report query=%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81 h_01J55W908AAPQ6YRT4P1R4CA58=%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81 h_01J55VAQ80PQX00GA9D516ST2Z=query-to-combine-cost-etl-and-cohort-report query::84619524=%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-1 h_01J55WCKZFA2JWV0MP72WVK7Y2=%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-1 h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

---
title: Combina los reportes de ETL de costos y de cohorte
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
  edited_at: '2026-08-22T00:01:01Z'
  id: 27494360719505
  locale: es
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/es/articles/27494360719505
---
> **En resumen:** Combina los reportes de cohorte y ETL de costos mediante Data Locker (agregados regulares y avanzados) para obtener una visión completa de tus campañas de marketing con la mayor actualización, precisión y granularidad disponibles.

![](https://files.readme.io/46f3cd4c2cfd6ba97caafb788c92ce967d8f304abd7b620968f49095275edf1a-27497862728465.png)

## Acerca de la combinación de reportes de costos, ETL y de cohorte

Los reportes ETL de costos y los reportes de cohortes a través de Data Locker (agregados regulares y avanzados) tienen cada uno sus propias cualidades únicas. Por ejemplo, los reportes de ETL de costos incluyen datos de impresiones, clics y costos, mientras que los reportes de cohortes incluyen datos detallados de atribución, eventos in-app e ingresos.

La mejor práctica es que, una vez que los reportes de ETL de costos y de cohorte agregados se reciban y carguen en tu sistema de BI, se combinen en tu BI interno.

Combinados, ellos:

* Proporciona una imagen completa de tu rendimiento de marketing, con la mejor actualización, precisión y granularidad disponibles.
* Haz coincidir tu BI interna con los datos que ves en los paneles de AppsFlyer.
* Te permiten calcular métricas importantes, como el retorno de la inversión publicitaria (ROAS) y el coste por acción (CPA).

## Consultas para combinar reportes

En las secciones siguientes se proporcionan las consultas y consideraciones que debes tener en cuenta al combinar los reportes de ETL de costos con:

* [Reportes de cohorte agregados avanzados](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-advanced-aggregated-cohort-report)
* [Reportes de cohorte a través de Data Locker](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-cohort-report)

<div id="query-to-combine-cost-etl-and-advanced-aggregated-cohort-report" />

<Accordion title="Consulta para combinar ETL de costos y el reporte de cohorte agregado avanzado">

Para combinar los reportes de ETL de costos y de cohorte, tu desarrollador de BI debe:

* Utilizar la siguiente consulta como guía y personalizándola para que se ajuste a tu BI interna.
* **Consideraciones importantes**:
  * Ajusta la consulta:
    * Personaliza las fechas de inicio y finalización.
    * Personaliza los nombres de tus reportes.
    * Elige las dimensiones y las métricas en tu esquema de ETL de costos específico.
  * Hay diferencias en la actualización de los reportes. Por ejemplo, el ETL de costos se actualiza hasta cuatro veces al día y los reportes de cohortes agregados avanzados se actualizan varias veces al día.
  * Los reportes de cohorte agregados avanzados incluyen los usuarios convertidos en los últimos 1095 días. Si se convirtieron antes de eso, no se tienen en cuenta.
  * Los reportes ETL de costos usan la zona horaria de los datos tal como los almacena AppsFlyer. Los reportes de cohorte agregados avanzados incluyen reportes versionados (UTC) y versionados de zona horaria. **Prácticas recomendadas**: Combina los reportes versionados de ETL de costos y de zona horaria de cohorte.

#### Query

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

<Accordion title="Consulta para combinar el reporte ETL de costos y el reporte de cohorte">

Para combinar los reportes de ETL de costos y de cohorte, tu desarrollador de BI debe:

* Utilizar la siguiente consulta como guía y personalizándola para que se ajuste a tu BI interna.
* **Consideraciones importantes**:
  * Ajusta la consulta:
    * Personaliza las fechas de inicio y finalización.
    * Personaliza los nombres de tus reportes.
    * Elige las dimensiones y las métricas en tu esquema de ETL de costos específico.
  * Hay diferencias en la actualización de los reportes. Por ejemplo, el ETL de costes se actualiza hasta cuatro veces al día y los reportes de cohortes a través de Data Locker se actualizan una vez al día.
  * Los reportes ETL de costos usan la zona horaria de los datos tal como los almacena AppsFlyer. Los reportes de cohorte a través de Data Locker utilizan UTC.

#### Query

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

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">ETL de costos</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/advanced-aggregated-reports-in-data-locker">Reportes agregados avanzados en Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/cohort-analytics-via-data-locker">Reportes de cohorte a través de Data Locker</Anchor>

<div data-zendesk-anchors="about-combining-cost-etl-and-cohort-reports=acerca-de-la-combinaci%C3%B3n-de-reportes-de-costos-etl-y-de-cohorte h_01J55PCC5MJ3MJBESDVEFHT796=acerca-de-la-combinaci%C3%B3n-de-reportes-de-costos-etl-y-de-cohorte queries-to-combine-reports=consultas-para-combinar-reportes h_01J55TR3SRXQPRBYRX6G3EJ7D9=consultas-para-combinar-reportes h_01J55VAQ804JWE6WT552GY98JF=query-to-combine-cost-etl-and-advanced-aggregated-cohort-report h_01J55W908AAPQ6YRT4P1R4CA58=query h_01J55VAQ80PQX00GA9D516ST2Z=query-to-combine-cost-etl-and-cohort-report query::84619524=query-1 h_01J55WCKZFA2JWV0MP72WVK7Y2=query-1 h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=consulta-tambi%C3%A9n" />

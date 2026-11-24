---
title: Combinar los reportes de Cost ETL y de cohortes a través de Data Locker
metadata:
  keywords:
    - Marketers
    - Analíticas de marketing
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Analíticas de marketing
  created_at: '2024-08-13T11:05:26Z'
  edited_at: '2026-08-22T00:01:01Z'
  id: 27494360719505
  locale: es
  section: AGREGACIÓN DE COSTES
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/27494360719505-Combine-Cost-ETL-and-cohort-reports-via-Data-Locker
---
> **En resumen:** Combina los reportes de cohorte y ETL de costos mediante Data Locker (agregados regulares y avanzados) para obtener una visión completa de tus campañas de marketing con la mayor actualización, precisión y granularidad disponibles.

<Image align="center" alt="" src="https://files.readme.io/46f3cd4c2cfd6ba97caafb788c92ce967d8f304abd7b620968f49095275edf1a-27497862728465.png" />

<div id="about-combining-cost-etl-and-cohort-reports" />

## Acerca de la combinación de reportes de Cost ETL y de cohortes

Los reportes de Cost ETL y los reportes de cohortes a través de Data Locker (estándar y agregados avanzados) tienen cada uno sus propias características. Por ejemplo, los reportes de Cost ETL incluyen datos de impresiones, clics y costos, mientras que los reportes de cohortes incluyen datos detallados de atribución, eventos in-app e ingresos.

Te recomendamos que, una vez que recibas los reportes de Cost ETL y de cohortes agregados y los cargues en tu sistema de BI, los combines en tu BI interno.

Al combinarlos, estos reportes:

- Ofrecen una visión completa de tu performance de marketing, con los datos más actualizados, precisos y granulares posibles.
- Hacen que tu BI interno coincida con los datos que ves en los dashboards de AppsFlyer.
- Te permiten calcular métricas importantes, como el retorno de la inversión publicitaria (ROAS) y el costo por acción (CPA).

<div id="queries-to-combine-reports" />

## Consultas para combinar reportes

En las siguientes secciones, encontrarás las consultas y los aspectos que debes tener en cuenta al combinar los reportes de Cost ETL con:

- [Reportes de cohorte agregados avanzados](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-advanced-aggregated-cohort-report)
- [Reportes de cohorte a través de Data Locker](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-cohort-report)

<div id="query-to-combine-cost-etl-and-advanced-aggregated-cohort-report" />

<Accordion title="Query to combine Cost ETL and Advanced aggregated cohort report">

Para combinar los reportes de ETL de costos y de cohorte, tu desarrollador de BI debe:

- Usar la siguiente consulta como guía y personalizarla para adaptarla a tu BI interno.
- **Consideraciones importantes**:
  - Ajusta la consulta:
    - Personaliza las fechas de inicio y de fin.
    - Personaliza los nombres de tus reportes.
    - Elige las dimensiones y métricas de tu esquema específico de Cost ETL.
  - Los reportes se actualizan con distinta frecuencia. Por ejemplo, Cost ETL se actualiza hasta cuatro veces al día y los reportes de cohortes agregados avanzados se actualizan varias veces al día.
  - Los reportes de cohortes agregados avanzados incluyen los usuarios que han convertido en los últimos 1095 días. Los usuarios que convirtieron antes no se tienen en cuenta.
  - Los reportes de Cost ETL usan la zona horaria con la que AppsFlyer almacena los datos. Los reportes de cohortes agregados avanzados incluyen reportes versionados (UTC) y reportes versionados por zona horaria. **Prácticas recomendadas**: Combina los reportes versionados de ETL de costos y de zona horaria de cohorte.

<div id="query" />

#### Consulta

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

<Accordion title="Query to combine Cost ETL and cohort report">

Para combinar los reportes de ETL de costos y de cohorte, tu desarrollador de BI debe:

- Usar la siguiente consulta como guía y personalizarla para adaptarla a tu BI interno.
- **Consideraciones importantes**:
  - Ajusta la consulta:
    - Personaliza las fechas de inicio y de fin.
    - Personaliza los nombres de tus reportes.
    - Elige las dimensiones y métricas de tu esquema específico de Cost ETL.
  - Los reportes se actualizan con distinta frecuencia. Por ejemplo, Cost ETL se actualiza hasta cuatro veces al día y los reportes de cohortes a través de Data Locker se actualizan una vez al día.
  - Los reportes de Cost ETL usan la zona horaria con la que AppsFlyer almacena los datos. Los reportes de cohortes a través de Data Locker usan UTC.

<div id="query-1" />

#### Consulta

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

<div id="see-also" />

> 📄 **Véase también**
>
> - <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">ETL de costos</Anchor>
> - <Anchor target="_blank" href="/marketers/docs/advanced-aggregated-reports-in-data-locker">Reportes agregados avanzados en Data Locker</Anchor>
> - <Anchor target="_blank" href="/marketers/docs/cohort-analytics-via-data-locker">Reportes de cohortes a través de Data Locker</Anchor>

<div data-zendesk-anchors="h_01J55PCC5MJ3MJBESDVEFHT796=about-combining-cost-etl-and-cohort-reports h_01J55TR3SRXQPRBYRX6G3EJ7D9=queries-to-combine-reports h_01J55VAQ804JWE6WT552GY98JF=query-to-combine-cost-etl-and-advanced-aggregated-cohort-report h_01J55W908AAPQ6YRT4P1R4CA58=query h_01J55VAQ80PQX00GA9D516ST2Z=query-to-combine-cost-etl-and-cohort-report query::84619524=query-1 h_01J55WCKZFA2JWV0MP72WVK7Y2=query-1 h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=see-also" />

---
title: Réunissez les ETL de coûts et les rapports de cohorte
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
  edited_at: '2024-09-09T16:49:16Z'
  id: 27494360719505
  locale: fr
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/fr/articles/27494360719505
---
> **En bref :** associez l'ETL des coûts et les rapports de cohorte via Data Locker (standard et agrégés avancés) pour obtenir des infos complètes et très précises de vos campagnes marketing.

![](https://files.readme.io/46f3cd4c2cfd6ba97caafb788c92ce967d8f304abd7b620968f49095275edf1a-27497862728465.png)

<div id="about-combining-cost-etl-and-cohort-reports" />

## A propos de l’association de l'ETL des coûts et des rapports de cohorte

Les rapports ETL des coûts et les rapports de cohorte via Data Locker (standard et agrégés avancés) ont chacun leur spécificité. Par exemple, les rapports ETL des coûts comprennent des données sur les impressions, les clics et les coûts, tandis que les rapports de cohortes offrent des données détaillées sur l'attribution, les événements in-app et les revenus.

Une fois que rapports ETL des coûts et les rapports de cohorte agrégés ont été chargés dans votre système BI, la meilleure chose à faire est de les associer dans votre système BI interne.

En les associant :

* Vous obtenez une vue d’ensemble de vos performances marketing, avec la meilleure actualisation, fiabilité et précision possible.
* Pouvez comparer votre BI interne aux données affichées dans les tableaux de bord AppsFlyer.
* Vous pouvez calculer des indicateurs importants, comme les dépenses publicitaires (ROAS) ou le coût par action (CPA).

<div id="queries-to-combine-reports" />

## Demandes à effectuer pour associer les rapports

Les sections suivantes indiquent les actions et éléments nécessaires lorsque vous souhaitez associer les rapports ETL des coûts avec :

* [Les rapports de cohorte agrégés avancés](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-advanced-aggregated-cohort-report)
* [Les rapports de cohorte via Data Locker](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-cohort-report)

<div id="query-to-combine-cost-etl-and-advanced-aggregated-cohort-report" />

<Accordion title="Marche à suivre pour associer l'ETL des coûts et le rapport de cohorte agrégé avancé">

**Pour associer l'ETL des coûts et les rapports de cohorte, votre développeur BI doit** :

* Prendre la requête suivante comme guide, et l'adapter à votre BI interne.
* **Remarques importantes** :
  * Pour adapter la requête :
    * Personnalisez les dates de début et de fin.
    * Personnalisez les noms de vos rapports.
    * Choisissez les dimensions et métriques dans votre propre ETL des coûts.
  * Il existe des différences au niveau de l’actualisation des rapports. Par exemple, l'ETL des coûts est mis à jour jusqu'à quatre fois par jour, tandis que les rapports de cohorte agrégés avancés sont mis à jour plusieurs fois par jour.
  * Les rapports de cohorte agrégés avancés incluent les utilisateurs convertis au cours des 1 095 derniers jours. S'ils ont été convertis avant, ils ne sont pas pris en compte.
  * Les rapports ETL des coûts utilisent comme fuseau horaire celui des données telles que stockées par AppsFlyer. Les rapports de cohorte agrégés avancés incluent de multiples versions des rapports selon l’UTC et le fuseau horaire. **Recommandation :** associez les rapports d'ETL des coûts et les différentes versions des rapports de cohorte par fuseau horaire.

<div id="query" />

#### Requête

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

<Accordion title="Requête pour associer l'ETL des coûts et le rapport de cohorte">

**Pour associer l'ETL des coûts et les rapports de cohorte, votre développeur BI doit** :

* Prendre la requête suivante comme guide, et l'adapter à votre BI interne.
* **Remarques importantes** :
  * Pour adapter la requête :
    * Personnalisez les dates de début et de fin.
    * Personnalisez les noms de vos rapports.
    * Choisissez les dimensions et métriques dans votre propre ETL des coûts.
  * Il existe des différences au niveau de l’actualisation des rapports. Par exemple, l'ETL des coûts est mis à jour jusqu'à 4 fois par jour, tandis que les rapports de cohorte via Data Locker sont mis à jour une fois par jour.
  * Les rapports ETL des coûts utilisent comme fuseau horaire celui des données telles que stockées par AppsFlyer. Les rapports de cohorte via Data Locker utilisent l'UTC.

<div id="query-1" />

#### Requête

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

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports">ETL des coûts</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/advanced-aggregated-reports-in-data-locker">Rapports agrégés avancés dans Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/cohort-analytics-via-data-locker">Les rapports de cohorte via Data Locker</Anchor>

<div data-zendesk-anchors="about-combining-cost-etl-and-cohort-reports=a-propos-de-lassociation-de-letl-des-co%C3%BBts-et-des-rapports-de-cohorte h_01J55PCC5MJ3MJBESDVEFHT796=a-propos-de-lassociation-de-letl-des-co%C3%BBts-et-des-rapports-de-cohorte queries-to-combine-reports=demandes-%C3%A0-effectuer-pour-associer-les-rapports h_01J55TR3SRXQPRBYRX6G3EJ7D9=demandes-%C3%A0-effectuer-pour-associer-les-rapports h_01J55VAQ804JWE6WT552GY98JF=query-to-combine-cost-etl-and-advanced-aggregated-cohort-report query=requ%C3%AAte h_01J55W908AAPQ6YRT4P1R4CA58=requ%C3%AAte h_01J55VAQ80PQX00GA9D516ST2Z=query-to-combine-cost-etl-and-cohort-report query::84619524=requ%C3%AAte-1 h_01J55WCKZFA2JWV0MP72WVK7Y2=requ%C3%AAte-1 h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=articles-connexes" />

---
title: Combine os relatórios de Cost ETL e de cohort via Data Locker
metadata:
  keywords:
    - Profissionais de marketing
    - Análise de marketing
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Análise de marketing
  created_at: '2024-08-13T11:05:26Z'
  edited_at: '2026-08-19T00:00:58Z'
  id: 27494360719505
  locale: "\n        int\n      "
  section: Cost aggregation
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/27494360719505-Combine-Cost-ETL-and-cohort-reports-via-Data-Locker
---
> **Visão geral:** Combine o Cost ETL e os relatórios de coorte através do Data Locker (agregados regulares e avançados) para obter a imagem completa das suas campanhas de marketing com a melhor atualidade, precisão e granularidade disponíveis.

<span style="font-weight: 400;"><Image align="center" alt="" src="https://files.readme.io/46f3cd4c2cfd6ba97caafb788c92ce967d8f304abd7b620968f49095275edf1a-27497862728465.png" /></span>

<span style="font-weight: 400;"><div id="about-combining-cost-etl-and-cohort-reports" /></span>

## Sobre a combinação de relatórios de Cost ETL e de cohort

Os relatórios de Cost ETL e de cohort através do Data Locker (agregados avançados e regulares) possuem qualidades distintas. Por exemplo, os relatórios de Cost ETL incluem dados de impressão, clique e custo, enquanto os relatórios de cohort incluem dados detalhados de atribuição, eventos in-app e receitas.

A prática recomendada é que, após receber e carregar os relatórios de Cost ETL e os relatórios agregados de cohort em seu sistema de BI, eles sejam combinados na sua própria ferramenta de BI.

Quando combinados, eles:

- Oferecem uma visão completa da performance das suas campanhas de marketing, com dados sempre atualizados, precisos e detalhados.
- Associam sua própria ferramenta de BI aos dados que você vê nos dashboards da AppsFlyer.
- Permitem que você calcule métricas importantes, como o ROAS e o CPA.

<span style="font-weight: 400;"><div id="queries-to-combine-reports" /></span>

## Consultas para combinar relatórios

As seções a seguir apresentam as consultas e os aspectos que você deve considerar ao combinar os relatórios de Cost ETL com:

- [Relatórios avançados agregados de coortes](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-advanced-aggregated-cohort-report)
- [Relatórios de coortes via Data Locker](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-cohort-report)

<span style="font-weight: 400;"><div id="query-to-combine-cost-etl-and-advanced-aggregated-cohort-report" /></span>

<Accordion title="Query to combine Cost ETL and Advanced aggregated cohort report">

**Para combinar o ETL de custos e os relatórios de coorte, o programador de BI deve**:

- Usar a consulta abaixo como um guia, personalizando-a para se adequar à sua própria ferramenta de BI.
- **Considerações importantes**:
  - Ajustando a consulta:
    - Personalize as datas de início e fim.
    - Personalize os nomes dos seus relatórios.
    - Selecione as dimensões e métricas no seu esquema específico de Cost ETL.
  - Existem diferenças na atualização dos relatórios. Por exemplo, o Cost ETL é atualizado até quatro vezes por dia e os relatórios agregados avançados de cohort são atualizados várias vezes ao dia.
  - Os relatórios agregados avançados de cohort incluem usuários convertidos nos últimos 1095 dias. Se eles se converteram antes disso, não são considerados.
  - Os relatórios de Cost ETL usam o fuso horário dos dados conforme eles são armazenados pela AppsFlyer. Os relatórios avançados agregados de cohort incluem relatórios versionados em UTC e relatórios versionados por fuso horário. **Prática recomendada**: Combinar ETL de custos e relatórios com versões de fuso horário de coorte.

<span style="font-weight: 400;"><div id="query" /></span>

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
   coalesce(SUM(cast(case when ag.event_name = 'af_conversion' and ag.conversion_type = 're-attribution' then ag.event_count end as int)),0) as re_attribution FROM {YOUR_ADVANCED_AGG_REPORT} as ag
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
```

</Accordion>

<span style="font-weight: 400;"><div id="query-to-combine-cost-etl-and-cohort-report" /></span>

<Accordion title="Query to combine Cost ETL and cohort report">

**Para combinar o ETL de custos e os relatórios de coorte, o programador de BI deve**:

- Usar a consulta abaixo como um guia, personalizando-a para se adequar à sua própria ferramenta de BI.
- **Considerações importantes**:
  - Ajustando a consulta:
    - Personalize as datas de início e fim.
    - Personalize os nomes dos seus relatórios.
    - Selecione as dimensões e métricas no seu esquema específico de Cost ETL.
  - Existem diferenças na atualização dos relatórios. Por exemplo, o Cost ETL é atualizado até quatro vezes por dia e os relatórios de cohort via Data Locker são atualizados uma vez por dia.
  - Os relatórios de Cost ETL usam o fuso horário dos dados conforme eles são armazenados pela AppsFlyer. Os relatórios de cohort via Data Locker utilizam UTC.

<span style="font-weight: 400;"><div id="query-1" /></span>

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
   coalesce(SUM(cast(case when dl.event_name = 'af_conversion' and dl.conversion_type = 're-attribution' then dl.event_count end as int)),0) as re_attribution FROM {YOUR_DATA_LOCKER_REPORT} as dl
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
           and dl.agency = cst.agency WHERE dl.conversion_date between {start date} and {end date}
   and cst.date between {start date} and {end date} GROUP BY ALL;
```

</Accordion>

<span style="font-weight: 400;"><div id="see-also" /></span>

> 📄 **Consulte também**
>
> - <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports">ETL de custos</Anchor>
> - <Anchor target="_blank" href="/marketers/docs/advanced-aggregated-reports-in-data-locker">Relatórios agregados avançados no Data Locker</Anchor>
> - <Anchor target="_blank" href="/marketers/docs/cohort-analytics-via-data-locker">Relatórios de cohort via Data Locker</Anchor>

<span style="font-weight: 400;"><div data-zendesk-anchors="h_01J55PCC5MJ3MJBESDVEFHT796=about-combining-cost-etl-and-cohort-reports h_01J55TR3SRXQPRBYRX6G3EJ7D9=queries-to-combine-reports h_01J55VAQ804JWE6WT552GY98JF=query-to-combine-cost-etl-and-advanced-aggregated-cohort-report h_01J55W908AAPQ6YRT4P1R4CA58=query h_01J55VAQ80PQX00GA9D516ST2Z=query-to-combine-cost-etl-and-cohort-report query::84619524=query-1 h_01J55WCKZFA2JWV0MP72WVK7Y2=query-1 h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=see-also" /></span>

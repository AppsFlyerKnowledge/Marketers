---
title: 通过Data Locker合并Cost ETL和群组报告
metadata:
  keywords:
    - 营销人员
    - 市场分析
x-zendesk:
  category: 营销人员
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - 营销人员
    - 市场分析
  created_at: '2024-08-13T11:05:26Z'
  edited_at: '2026-08-13T16:01:09Z'
  id: 27494360719505
  locale: zh-cn
  section: 成本数据汇总
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/27494360719505-Combine-Cost-ETL-and-cohort-reports-via-Data-Locker
---
> \*\*概览：\*\*您可以通过 Data Locker 合并 Cost ETL 和群组报告（常规及高级汇总），以最佳可用的时效性、准确性和颗粒度，全面了解您的营销广告活动。

<Image align="center" alt="" src="https://files.readme.io/46f3cd4c2cfd6ba97caafb788c92ce967d8f304abd7b620968f49095275edf1a-27497862728465.png" />

<div id="about-combining-cost-etl-and-cohort-reports" />

## Cost ETL与群组报告的合并方式简介

Cost ETL报告以及Data Locker中的群组报告（常规及高级汇总均适用）分别具有其各自专属的特点。 Cost ETL reports and cohort reports via Data Locker (regular and advanced aggregated) each have their own unique qualities. For example, Cost ETL reports include impression, click, and cost data, while cohort reports include detailed attribution, in-app event, and revenue data.

为了充分利用这两种报告，建议您在内部BI系统接收到Cost ETL和汇总群组报告并完成入库后合并这两个报告。

合并后的报告具有以下优势：

- 可提供时效性最强、准确性最高、颗粒度最细的数据，帮助您全面了解营销效果。
- 将贵司的内部BI与AppsFlyer面板数据对齐。
- 有助于重要指标的计算，如广告支出回报率（ROAS）以及平均用户行为成本（CPA）。

<div id="queries-to-combine-reports" />

## 用于合并报告的查询语句

将Cost ETL报告与下列报告合并时，需要考量特定的查询语句和注意事项，详见以下各章节说明。

- [高级汇总群组报告](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-advanced-aggregated-cohort-report)
- [通过Data Locker获取的群组报告](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-cohort-report)

<div id="query-to-combine-cost-etl-and-advanced-aggregated-cohort-report" />

<Accordion title="Query to combine Cost ETL and Advanced aggregated cohort report">

**合并Cost ETL与群组报告时，您的BI开发人员需要完成以下操作**：

- 您可以参考以下查询语句，并根据您内部BI的实际情况做相应的调整。
- **重要事项**：
  - 调整查询语句：
    - 调整报告的起始日期和截止日期。
    - 调整您的报告名称。
    - 从特定的Cost ETL数据结构中选择所需的维度和指标。
  - 不同报告的时效性有所差异。 There are differences in the reports' freshness. For example, Cost ETL updates up to four times a day and Advanced aggregated cohort reports update multiple times a day.
  - Advanced aggregated cohort reports include users converted in the past 1,095 days. If they converted before that, they aren't taken into account. 更早之前转化的用户会被忽略。
  - Cost ETL reports use the timezone of the data as it's stored by AppsFlyer. Cohort reports via Data Locker use UTC. 高级汇总群组报告则包含UTC时区的数据版本和本地时区的数据版本。**最佳实践**：合并 Cost ETL 和群组时区版本化报告。

<div id="query" />

#### 查询

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

**合并Cost ETL与群组报告时，您的BI开发人员需要完成以下操作**：

- 您可以参考以下查询语句，并根据您内部BI的实际情况做相应的调整。
- **重要事项**：
  - 调整查询语句：
    - 调整报告的起始日期和截止日期。
    - 调整您的报告名称。
    - 从特定的Cost ETL数据结构中选择所需的维度和指标。
  - 不同报告的时效性有所差异。 There are differences in the reports' freshness. For example, Cost ETL updates up to four times a day and cohort reports via Data Locker update once per day.
  - Cost ETL reports use the timezone of the data as it's stored by AppsFlyer. Cohort reports via Data Locker use UTC. 而Data Locker中的群组报告则按UTC时间呈现。

<div id="query-1" />

#### 查询

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

> 📄 **另请参阅**
>
> - <Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL</Anchor>
> - <Anchor target="_blank" href="/marketers/zh/docs/advanced-aggregated-reports-in-data-locker">Data Locker中的高级汇总报告</Anchor>
> - <Anchor target="_blank" href="/marketers/zh/docs/cohort-analytics-via-data-locker">Data Locker中的群组报告</Anchor>

<div data-zendesk-anchors="h_01J55PCC5MJ3MJBESDVEFHT796=about-combining-cost-etl-and-cohort-reports h_01J55TR3SRXQPRBYRX6G3EJ7D9=queries-to-combine-reports h_01J55VAQ804JWE6WT552GY98JF=query-to-combine-cost-etl-and-advanced-aggregated-cohort-report h_01J55W908AAPQ6YRT4P1R4CA58=query h_01J55VAQ80PQX00GA9D516ST2Z=query-to-combine-cost-etl-and-cohort-report query::84619524=query-1 h_01J55WCKZFA2JWV0MP72WVK7Y2=query-1 h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=see-also" />

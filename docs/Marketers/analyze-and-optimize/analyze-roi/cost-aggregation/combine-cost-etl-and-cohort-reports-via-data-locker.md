---
title: Combine Cost ETL and cohort reports via Data Locker
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
  edited_at: '2026-08-13T16:01:09Z'
  id: 27494360719505
  locale: en-us
  section: Cost aggregation
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/27494360719505-Combine-Cost-ETL-and-cohort-reports-via-Data-Locker
---
> **At a glance:** Combine Cost ETL and cohort reports via Data Locker (regular and advanced aggregated) to get the full picture of your marketing campaigns with the best available freshness, accuracy, and granularity.

<Image align="center" alt="" src="https://files.readme.io/46f3cd4c2cfd6ba97caafb788c92ce967d8f304abd7b620968f49095275edf1a-27497862728465.png" />

<div id="about-combining-cost-etl-and-cohort-reports" />

## About combining Cost ETL and cohort reports

Cost ETL reports and cohort reports via Data Locker (regular and advanced aggregated) each have their own unique qualities. For example, Cost ETL reports include impression, click, and cost data, while cohort reports include detailed attribution, in-app event, and revenue data.

The best practice is that once the Cost ETL and aggregated cohort reports are received and loaded into your BI system, they should be combined in your internal BI.

Combined, they:

* Provide the full picture of your marketing performance, with the best available freshness, accuracy, and granularity.
* Match your internal BI to the data you see in AppsFlyer dashboards.
* Allow you to calculate important metrics, like return on ad spend (ROAS) and cost per action (CPA).

<div id="queries-to-combine-reports" />

## Queries to combine reports

The sections that follow provide the queries and considerations you need to take into account when combining Cost ETL reports with:

* [Advanced aggregated cohort reports](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-advanced-aggregated-cohort-report)
* [Cohort reports via Data Locker](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-cohort-report)

<div id="query-to-combine-cost-etl-and-advanced-aggregated-cohort-report" />

<Accordion title="Query to combine Cost ETL and Advanced aggregated cohort report">

**To combine the Cost ETL and cohort reports, your BI developer should**:

* Use the following query as a guide, customizing it to fit your internal BI.
* **Important considerations**:
  * Adjust the query:
    * Customize the start dates and end dates.
    * Customize your report names.
    * Choose the dimensions and metrics in your specific Cost ETL schema.
  * There are differences in the reports' freshness. For example, Cost ETL updates up to four times a day and Advanced aggregated cohort reports update multiple times a day.
  * Advanced aggregated cohort reports include users converted in the past 1,095 days. If they converted before that, they aren't taken into account.
  * Cost ETL reports use the timezone of the data as it's stored by AppsFlyer. Advanced aggregated cohort reports include versioned (UTC) and versioned timezone reports. **Best practice**: Combine Cost ETL and cohort timezone versioned reports.

<div id="query" />

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

<Accordion title="Query to combine Cost ETL and cohort report">

**To combine the Cost ETL and cohort reports, your BI developer should**:

* Use the following query as a guide, customizing it to fit your internal BI.
* **Important considerations**:
  * Adjust the query:
    * Customize the start dates and end dates.
    * Customize your report names.
    * Choose the dimensions and metrics in your specific Cost ETL schema.
  * There are differences in the reports' freshness. For example, Cost ETL updates up to four times a day and cohort reports via Data Locker update once per day.
  * Cost ETL reports use the timezone of the data as it's stored by AppsFlyer. Cohort reports via Data Locker use UTC.

<div id="query-1" />

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

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/advanced-aggregated-reports-in-data-locker">Advanced aggregated reports in Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/cohort-analytics-via-data-locker">Cohort reports via Data Locker</Anchor>

<div data-zendesk-anchors="h_01J55PCC5MJ3MJBESDVEFHT796=about-combining-cost-etl-and-cohort-reports h_01J55TR3SRXQPRBYRX6G3EJ7D9=queries-to-combine-reports h_01J55VAQ804JWE6WT552GY98JF=query-to-combine-cost-etl-and-advanced-aggregated-cohort-report h_01J55W908AAPQ6YRT4P1R4CA58=query h_01J55VAQ80PQX00GA9D516ST2Z=query-to-combine-cost-etl-and-cohort-report query::84619524=query-1 h_01J55WCKZFA2JWV0MP72WVK7Y2=query-1 h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=see-also" />

---
title: Cost ETL 리포트와 코호트 리포트 결합
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
  edited_at: '2026-10-14T10:39:23Z'
  id: 27494360719505
  locale: ko
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ko/articles/27494360719505
---
> **요약:** 데이터 락커(정기 및 고급 집계)를 통해 Cost ETL 리포트와 코호트 리포트를 결합하여 최고의 최신성, 정확성, 세분화로 마케팅 캠페인의 전체 상황을 파악할 수 있습니다.

![](https://files.readme.io/46f3cd4c2cfd6ba97caafb788c92ce967d8f304abd7b620968f49095275edf1a-27497862728465.png)

<div id="about-combining-cost-etl-and-cohort-reports" />

## Cost ETL 리포트와 코호트 리포트의 결합 정보

데이터 락커를 통해 생성된 Cost ETL 리포트와 코호트 리포트(일반 및 고급 집계)는 각각 고유한 특성을 가지고 있습니다. 예를 들어, Cost ETL 리포트에는 노출, 클릭 및 비용 데이터가 포함되는 반면, 코호트 리포트에는 자세한 어트리뷰션, 인앱 이벤트 및 수익 데이터가 포함됩니다.

가장 좋은 방법은 Cost ETL 리프트와 집계된 코호트 리포트가 수신되어 BI 시스템에 로드되면 내부 BI에 결합하도록 하는 것입니다.

두 리포트를 결합하면 다음과 같은 이점이 있습니다.

* 최고의 최신성, 정확성, 세분화와 함께, 마케팅 성과를 전체적으로 보여줍니다.
* 내부 BI를 앱스플라이어 대시보드에 표시되는 데이터와 일치시킵니다.
* 광고 지출 대비 수익률(ROAS) 및 전환당 비용(CPA)과 같은 중요한 지표를 계산할 수 있습니다.

<div id="queries-to-combine-reports" />

## 리포트를 결합하는 쿼리

이후에 이어지는 섹션에서는 Cost ETL 리포트를 다음과 결합할 때의 쿼리와 고려 사항을 제시합니다.

* [고급 집계 코호트 리포트](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-advanced-aggregated-cohort-report)
* [데이터 락커를 통한 코호트 리포트](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-cohort-report)

<div id="query-to-combine-cost-etl-and-advanced-aggregated-cohort-report" />

<Accordion title="Cost ETL 리포트와 고급 집계 코호트 리포트를 결합하는 쿼리">

**Cost ETL 리포트와 코호트 리포트를 결합하려면 BI 개발자는 다음을 수행해야 합니다.**

* 다음 쿼리를 가이드로 삼아 내부 BI에 맞게 사용자 지정합니다.
* **중요 고려 사항**:
  * 쿼리 조정:
    * 시작 날짜와 종료 날짜를 사용자 지정합니다.
    * 리포트 이름을 사용자 지정합니다.
    * 특정 Cost ETL 스키마에서 측정항목과 지표를 선택합니다.
  * 리포트의 최신성에 차이가 있습니다. 예를 들어, Cost ETL은 하루에 최대 4회 업데이트되고 고급 집계 코호트 리포트는 하루에 여러 번 업데이트됩니다.
  * 고급 집계 코호트 리포트에는 지난 1,095일 동안 전환된 사용자가 포함됩니다. 그 이전에 전환한 경우는 고려 대상이 아닙니다.
  * Cost ETL 리포트에서는 앱스플라이어에 저장된 데이터의 시간대를 사용합니다. 고급 집계 코호트 리포트에는 버전이 지정된 (UTC) 리포트와 버전이 지정된 시간대 리포트가 포함됩니다. **모범 사례**: Cost ETL 리포트와 코호트 시간대 버전 지정 리포트를 결합합니다.

<div id="query" />

#### 쿼리

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

<Accordion title="Cost ETL 리포트와 코호트 리포트를 결합하는 쿼리">

**Cost ETL 리포트와 코호트 리포트를 결합하려면 BI 개발자는 다음을 수행해야 합니다.**

* 다음 쿼리를 가이드로 삼아 내부 BI에 맞게 사용자 지정합니다.
* **중요 고려 사항**:
  * 쿼리 조정:
    * 시작 날짜와 종료 날짜를 사용자 지정합니다.
    * 리포트 이름을 사용자 지정합니다.
    * 특정 Cost ETL 스키마에서 측정항목과 지표를 선택합니다.
  * 리포트의 최신성에 차이가 있습니다. 예를 들어, Cost ETL은 하루에 최대 4번 업데이트되고 데이터 락커를 통한 코호트 리포트는 하루에 한 번 업데이트됩니다.
  * Cost ETL 리포트에서는 앱스플라이어에 저장된 데이터의 시간대를 사용합니다. 데이터 락커를 통한 코호트 리포트는 UTC를 사용합니다.

<div id="query-1" />

#### 쿼리

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

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/advanced-aggregated-reports-in-data-locker">데이터 락커의 고급 집계 리포트</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/cohort-analytics-via-data-locker">데이터 락커를 통한 코호트 리포트</Anchor>

<div data-zendesk-anchors="about-combining-cost-etl-and-cohort-reports=cost-etl-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%99%80-%EC%BD%94%ED%98%B8%ED%8A%B8-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EA%B2%B0%ED%95%A9-%EC%A0%95%EB%B3%B4 h_01J55PCC5MJ3MJBESDVEFHT796=cost-etl-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%99%80-%EC%BD%94%ED%98%B8%ED%8A%B8-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EA%B2%B0%ED%95%A9-%EC%A0%95%EB%B3%B4 queries-to-combine-reports=%EB%A6%AC%ED%8F%AC%ED%8A%B8%EB%A5%BC-%EA%B2%B0%ED%95%A9%ED%95%98%EB%8A%94-%EC%BF%BC%EB%A6%AC h_01J55TR3SRXQPRBYRX6G3EJ7D9=%EB%A6%AC%ED%8F%AC%ED%8A%B8%EB%A5%BC-%EA%B2%B0%ED%95%A9%ED%95%98%EB%8A%94-%EC%BF%BC%EB%A6%AC h_01J55VAQ804JWE6WT552GY98JF=query-to-combine-cost-etl-and-advanced-aggregated-cohort-report query=%EC%BF%BC%EB%A6%AC h_01J55W908AAPQ6YRT4P1R4CA58=%EC%BF%BC%EB%A6%AC h_01J55VAQ80PQX00GA9D516ST2Z=query-to-combine-cost-etl-and-cohort-report query::84619524=%EC%BF%BC%EB%A6%AC-1 h_01J55WCKZFA2JWV0MP72WVK7Y2=%EC%BF%BC%EB%A6%AC-1 h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />

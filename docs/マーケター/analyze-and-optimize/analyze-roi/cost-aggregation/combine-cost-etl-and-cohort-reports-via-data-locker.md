---
title: Data Locker経由のコストETLレポートとコホートレポートの結合
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
  edited_at: '2026-10-28T08:43:16Z'
  id: 27494360719505
  locale: ja
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ja/articles/27494360719505
---
> **概要：** コストETLと、Data Locker経由のコホートレポート（通常版・詳細集計版）を結合し、可能な限り最新かつ正確で詳細なデータを使って、マーケティングキャンペーンの全体像を把握します。

![](https://files.readme.io/46f3cd4c2cfd6ba97caafb788c92ce967d8f304abd7b620968f49095275edf1a-27497862728465.png)

## コストETLレポートとコホートレポートの結合について

コストETLレポートと、Data Locker経由のコホートレポート（通常版・詳細集計版）には、それぞれ異なる特徴があります。例えば、コストETLレポートにはインプレッション、クリック、広告費のデータが含まれ、コホートレポートにはアトリビューション、アプリ内イベント、収益の詳細なデータが含まれます。

コストETLレポートと集計コホートレポートを受信してBIシステムに読み込んだ後、社内のBIシステム上で両者を結合することを推奨します。

レポートを結合すると、次のことが可能になります。

* 可能な限り最新かつ正確で詳細なデータを使って、マーケティング成果の全体像を把握できます。
* 社内のBIシステムとAppsFlyerのダッシュボードで、表示するデータを揃えられます。
* 広告費用対効果（ROAS）やアクション単価（CPA）など、重要な指標を計算できます。

## レポート結合用のクエリ

以下では、コストETLレポートを次のレポートと結合するためのクエリと、考慮すべき事項を説明します。

* [詳細集計コホートレポート](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-advanced-aggregated-cohort-report)
* [Data Locker経由のコホートレポート](/docs/combine-cost-etl-and-cohort-reports-via-data-locker#query-to-combine-cost-etl-and-cohort-report)

<div id="query-to-combine-cost-etl-and-advanced-aggregated-cohort-report" />

<Accordion title="コストETLレポートと詳細集計コホートレポートを結合するクエリ">

**コストETLレポートとコホートレポートを結合するには、BIシステム開発者が以下の作業を行います**。

* 以下のクエリを参考に、社内のBIシステムに合わせて調整します。
* **重要な確認事項**：
  * クエリ内の以下の項目を調整してください。
    * 開始日と終了日を変更します。
    * レポート名を変更します。
    * 使用するコストETLスキーマに含まれるディメンションと指標を選択します。
  * レポートによって更新頻度が異なります。例えば、コストETLは1日最大4回、詳細集計コホートレポートは1日に複数回更新されます。
  * 詳細集計コホートレポートには、過去1,095日間にコンバージョンしたユーザーが含まれます。それ以前にコンバージョンしたユーザーは、集計対象に含まれません。
  * コストETLレポートでは、AppsFlyerにデータが保存されているタイムゾーンを使用します。詳細集計コホートレポートには、UTCでバージョン管理されるレポートと、指定したタイムゾーンでバージョン管理されるレポートがあります。**推奨事項**：コストETLレポートと、指定したタイムゾーンでバージョン管理されるコホートレポートを結合してください。

#### クエリ

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

<Accordion title="コストETLレポートとコホートレポートを結合するクエリ">

**コストETLレポートとコホートレポートを結合するには、BIシステム開発者が以下の作業を行います**。

* 以下のクエリを参考に、社内のBIシステムに合わせて調整します。
* **重要な確認事項**：
  * クエリ内の以下の項目を調整してください。
    * 開始日と終了日を変更します。
    * レポート名を変更します。
    * 使用するコストETLスキーマに含まれるディメンションと指標を選択します。
  * レポートによって更新頻度が異なります。例えば、コストETLは1日最大4回、Data Locker経由のコホートレポートは1日1回更新されます。
  * コストETLレポートでは、AppsFlyerにデータが保存されているタイムゾーンを使用します。 Data Locker経由のコホートレポートでは、UTCを使用します。

#### クエリ

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

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports">コストETL</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/advanced-aggregated-reports-in-data-locker">Data Lockerの詳細集計レポート</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/cohort-analytics-via-data-locker">Data Locker経由のコホートレポート</Anchor>

<div data-zendesk-anchors="about-combining-cost-etl-and-cohort-reports=%E3%82%B3%E3%82%B9%E3%83%88etl%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A8%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E7%B5%90%E5%90%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01J55PCC5MJ3MJBESDVEFHT796=%E3%82%B3%E3%82%B9%E3%83%88etl%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A8%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E7%B5%90%E5%90%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 queries-to-combine-reports=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E7%B5%90%E5%90%88%E7%94%A8%E3%81%AE%E3%82%AF%E3%82%A8%E3%83%AA h_01J55TR3SRXQPRBYRX6G3EJ7D9=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E7%B5%90%E5%90%88%E7%94%A8%E3%81%AE%E3%82%AF%E3%82%A8%E3%83%AA h_01J55VAQ804JWE6WT552GY98JF=query-to-combine-cost-etl-and-advanced-aggregated-cohort-report query=%E3%82%AF%E3%82%A8%E3%83%AA h_01J55W908AAPQ6YRT4P1R4CA58=%E3%82%AF%E3%82%A8%E3%83%AA h_01J55VAQ80PQX00GA9D516ST2Z=query-to-combine-cost-etl-and-cohort-report query::84619524=%E3%82%AF%E3%82%A8%E3%83%AA-1 h_01J55WCKZFA2JWV0MP72WVK7Y2=%E3%82%AF%E3%82%A8%E3%83%AA-1 h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />

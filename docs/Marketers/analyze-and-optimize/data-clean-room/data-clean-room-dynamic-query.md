---
title: Data Clean Room—Dynamic Query
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2023-09-20T10:05:34Z'
  edited_at: '2024-12-11T09:29:24Z'
  id: 18704719821329
  locale: en-us
  section: Data Clean Room
  section_id: 4591191779217
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/18704719821329-Data-Clean-Room-Dynamic-Query
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Run custom DCR queries in real time on your attribution data in the AppsFlyer system, your custom sources, or a combination. Preview the results of your queries or download the full results.

## Overview

### Why use Dynamic Query?

Dynamic Query gives you the ability to run ad hoc, custom queries on your DCR data in real time to answer your specific marketing questions quickly and efficiently.

* Incorporating the power and flexibility of SQL, it allows you to perform advanced research and complex calculations that can't be accomplished in any other way. With Dynamic Query, you can bring your business logic to data that would otherwise be inaccessible.
* In addition, Dynamic Query makes it possible to obtain efficient answers to one-time or occasional questions without the need to set up reports. (Of course, <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-reports">traditional DCR reports</Anchor> are still the right solution for ongoing data retrieval and ingestion.)

Dynamic Query is available to **all DCR customers,** giving you the ability to run queries and preview the results without using credits from your DCR package. You'll only be charged credits if you decide to download the full results. In this way, you can be sure you've set up your queries correctly and that you'll get the answers you need before you incur any charges.

### Query language and dialect

Dynamic Query utilizes SQL **(Spark SQL dialect)** and supports:

* <Anchor target="_blank" href="https://spark.apache.org/docs/3.2.1/sql-ref-syntax-qry-select.html">SELECT statements</Anchor>
* <Anchor target="_blank" href="https://spark.apache.org/docs/3.2.1/api/sql/">Standard SQL functions</Anchor>
* User-defined functions (UDFs), upon customer request
  * If you require a non-standard SQL function, contact your CSM or [hello@appsflyer.com](mailto:hello@appsflyer.com,) and we'll make every effort to add it.

### Available sources

Dynamic Query allows you to perform custom queries on the following data sources:

* Your attribution data in the AppsFlyer system
  * [Learn more](#querying-attribution-data) about attribution data tables and how to query them
* <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-sources">Custom sources</Anchor> you've set up in the DCR

You can query these sources individually, or [combine 2 or more](#combining-sources) using **JOIN** or **UNION** statements. This flexibility makes Dynamic Query useful in a variety of scenarios, for example:

* Querying only attribution data to [obtain cross-app insights](#obtain-crossapp-insights), [explore data integrity](#explore-data-integrity), or [calculate custom attribution metrics](#calculate-custom-attribution-metrics)
* Querying your custom sources in combination with attribution data to [enrich your data](#enrich-your-custom-data-with-attribution-insights) with attribution insights

Based on the types of sources used in a query, [rules are applied](#preserving-privacy) to ensure the strict preservation of user privacy.

> 📘 **Note**
>
> Currently, Dynamic Query does not query attribution data or return results from Meta (Facebook, Instagram, etc.) To query this data, set up <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-reports">DCR reports</Anchor>.

### Preserving privacy

To ensure that Dynamic Query maintains strict compliance with DCR privacy standards, the following requirements apply to all queries:

1. Any query utilizing **attribution data** must include a **GROUP BY** statement so that results are aggregated.
2. **UNION** statements **cannot** be used to combine custom sources with attribution data.
3. Grouping by the following fields is **not permitted:**
   * **Attribution data fields:**
     * appsflyer\_id
     * idfa
     * idfv
     * advertising\_id
     * android\_id
     * customer\_user\_id
     * ip
   * **Custom source fields** that are joined to any of the above attribution data fields.
4. The following functions are **not permitted** when run on **non-aggregated attribution data.** They **are permitted** when run on **aggregated attribution data** or **custom source data:**
   * collect\_list
   * collect\_set
   * last
   * last\_value
   * first
   * first\_value
   * max
   * min

To learn more about the *do*s and *don't*s of constructing queries, see samples and explanations of [valid](#sample-queries) and [invalid](#invalid-queries) queries.

### Accessing Dynamic Query

1. In AppsFlyer, from the side menu, select **Collaborate** > **Data Clean Room**.
2. From the top menu, select the **Dynamic Query** tab.

## Reference

### Query reference

The following tabs provide additional information about constructing queries in the Dynamic Query environment.

<div id="combining-sources" />

<Accordion title="Combining sources: JOIN and UNION">

**JOIN** statements combine sources by matching a common field:

* Can be used to combine any sources: attribution data tables and/or custom sources
* Can be used to combine an unlimited number of sources
* **Typically used to enrich custom source data with attribution data**

**UNION** statements append tables with matching schema (containing the same columns and datatypes):

* **Can** be used to combine attribution data tables ***or*** custom sources; **cannot** be used to combine attribution data tables ***with*** custom sources
* Can be used to combine an unlimited number of sources
* **Typically used to perform queries on** [**multiple attribution data tables**](#querying-attribution-data)

</Accordion>

<div id="querying-attribution-data" />

<Accordion title="Querying attribution data tables">

Attribution data in the AppsFlyer system exists in 8 different tables:

* Each table includes different types of attribution events.
* The timeframe for which query data is available varies by table.
  * When constructing your query in the Dynamic Query console, hover over the name of a table in the selection panel to see the precise data availability dates for that table.
* The tables within each of the groups below have matching schema, meaning you can use **UNION** statements to easily query multiple tables at once.

**Group 1: App installs and retargeting events**

| Table name | Description | Data availability dates |
| --- | --- | --- |
| installs | A user downloads, installs, and launches a mobile app | Prior 180 days  <br />(not including current day) |
| re\_installs | A user installs an app, then uninstalls and re-installs it during the re-attribution window | Prior 180 days  <br />(not including current day) |
| re\_engagements | An inactive user of a specific app engages with a retargeting campaign for the app and subsequently launches it | Prior 180 days  <br />(not including current day) |
| re\_attribution | A former user of a specific app (who had uninstalled it) engages with a retargeting campaign for the app and subsequently reinstalls it | Prior 180 days  <br />(not including current day) |
| organic\_installs | Install not attributed to a specific media source | Prior 180 days  <br />(not including current day) |

**Group 2: In-app events**

| Table name | Description | Data availability dates |
| --- | --- | --- |
| in\_app\_events | Post-install events set up for measurement in the app SDK | Prior day + current day |
| in\_app\_organic\_installs | In-app events following an organic install | Prior day + current day |

**Group 3: Impressions**

| Table name | Description | Data availability dates |
| --- | --- | --- |
| impressions | An ad is viewed by an app user or website visitor<ul><li>Data available for non-SRN ad networks only</li></ul> | Prior 5 days + current day |

</Accordion>

### Sample queries

These queries demonstrate just a few possibilities of what you can do with Dynamic Query. You can use them simply to get your ideas flowing, or you can use them as a starting point for your own queries.

**To use the sample queries as a basis for your queries:**

1. Copy and paste: Copy the SQL samples of your choice and paste them into a worksheet in the **Dynamic Query** tab.
2. Replace parameters: Modify the SQL code by replacing the parameters with the specific sources and fields you want to query.
3. Execute: Click the **Run** button to execute a query and preview the results.  
   * Running a query and previewing the results does not consume credits.
   * Credits from your DCR package are consumed only if you download the full results.

<div id="obtain-crossapp-insights" />

<Accordion title="Obtain cross-app insights">

This query retrieves information about the 3 apps with the most re-installs from Snapchat during the past 3 days.

```sql
SELECT app_id, COUNT(*) AS reinstall_count
FROM re_installs
WHERE media_source = 'snapchat_int' AND dt BETWEEN DATE_SUB(current_date(), 3) AND current_date()
GROUP BY app_id
ORDER BY reinstall_count DESC
LIMIT 3;
```

</Accordion>

<div id="explore-data-integrity" />

<Accordion title="Explore data integrity">

To help you assess data integrity, this query calculates the rate of null IDFA values for the 10 media sources with the highest number of installs during the past 7 days.

```sql
SELECT media_source, COUNT(*) AS total_installs, ROUND((SUM(CASE WHEN idfa IS NULL THEN 1 ELSE 0 END) / COUNT(*)) * 100, 2) AS null_idfa_rate
FROM installs
WHERE dt BETWEEN DATE_SUB(current_date(), 3) AND current_date()
GROUP BY media_source
ORDER BY total_installs DESC
LIMIT 10;
```

</Accordion>

<div id="calculate-custom-attribution-metrics" />

<Accordion title="Calculate custom attribution metrics">

By calculating the geometric mean of the time difference (in seconds) between install time and attributed touch time for each media source and campaign, the resulting data provides insight into the efficiency of various media sources as regards user conversions and attribution timelines.

```sql
SELECT media_source,campaign,geo_mean(GREATEST(1, unix_timestamp(install_time, "yyyy-MM-dd HH:mm:ss") - unix_timestamp(attributed_touch_time, "yyyy-MM-dd HH:mm:ss.SSS")))
FROM installs
GROUP BY 1,2
```

</Accordion>

<div id="enrich-your-custom-data-with-attribution-insights" />

<Accordion title="Enrich your custom data with attribution insights">

This query utilizes attribution data to group a score from Custom Source C (c.score) by media source, allowing you to use your custom metric to evaluate the relative performance of various media sources.

```sql
SELECT media_source, sum(c.score)
FROM client_input c JOIN install i on i.appsflyer_id = c.appsflyer_id
GROUP BY media_source;
```

</Accordion>

<div id="complex-attribution-and-firstparty-data-join" />

<Accordion title="Complex attribution and first-party data join">

This query utilizes a more intricate data-join process, allowing for advanced insight generation. First, it retrieves and unifies data from 2 distinct attribution tables ("install" and "installRetarget"). Next, it combines this data with 2 first-party custom sources to provide insights about various conversion types, including an aggregated custom performance metric (score) and maximum age for each.

```sql
SELECT conversion_type, SUM(sum_score), MAX(max_age)
FROM (SELECT media_source, conversion_type, SUM(score) as sum_score, MAX(age) as max_age
FROM (SELECT * from install union all select * FROM installRetarget) af
JOIN client_input c on c.appsflyer_id = af.appsflyer_id
JOIN client_age ca on ca.appsflyer_id = c.appsflyer_id
GROUP BY media_source, conversion_type)
GROUP BY conversion_type
```

</Accordion>

### Invalid queries

These queries illustrate some of the rules that Dynamic Query uses to ensure compliance with user privacy requirements. Use them to better understand the *do*s and *don't*s of constructing queries for the DCR.

<div id="no-group-by-statement" />

<Accordion title="No GROUP BY statement">

Each of the following queries is invalid because it utilizes attribution data but doesn't include a **GROUP BY** statement:

```sql
SELECT *
FROM install;
```

-----------------------------------------------------

```sql
SELECT media_source, appId
FROM client_input c
JOIN install af on af.appsflyer_id = c.appsflyer_id;
```

</Accordion>

<div id="grouped-by-nonpermitted-attribution-data-field" />

<Accordion title="Grouped by non-permitted attribution data field">

The following query is invalid because it groups by a non-permitted attribution data field (appsflyer\_id):

```sql
SELECT appsflyer_id, count(*)
FROM install
GROUP BY appsflyer_id
```

-----------------------------------------------------

The following query is invalid because it groups by a non-permitted attribution data field (appsflyer\_id). This is not permitted even when the field is within a function:

```sql
SELECT substr(appsflyer_id, 0, 5), count(*)
FROM install
GROUP BY substr(appsflyer_id, 0, 5)
```

-----------------------------------------------------

The following query is invalid because it groups by a non-permitted attribution data field (appsflyer\_id). This is not permitted even when the field is within an index:

```sql
SELECT appsflyer_id, count(*)
FROM install
GROUP BY 1
```

</Accordion>

<div id="grouped-by-nonpermitted-custom-data-field" />

<Accordion title="Grouped by custom source field joined to non-permitted attribution data field">

The following query is invalid because it groups by a custom source field (my\_id) that is joined to a non-permitted attribution data field (appsflyer\_id); therefore, the same grouping restriction applies to my\_id.

```sql
SELECT my_id, count(*)
FROM installs
JOIN my_source on my_source.my_id = installs.appsflyer_id
GROUP BY my_id
```

</Accordion>

<div id="restricted-function" />

<Accordion title="Restricted function">

The following query is **invalid** because it attempts to run the collect\_list function on **non-aggregated** attribution data:

```sql
SELECT App_id, collect_list(appsflyer_id)
FROM install
GROUP BY app_id
```

-----------------------------------------------------

Compare with the following **valid** query, which runs the collect\_list function on **aggregated** attribution data:

```sql
SELECT app_id, collect_list(campaign)
FROM (select app_id, campaign
  FROM Install
  GROUP BY 1, 2)
GROUP BY app_id
```

-----------------------------------------------------

Compare with the following **valid** query, which runs the collect\_list function on **custom source data:**

```sql
SELECT app_id, collect_list(c.score)
FROM client_input c
GROUP BY app_id
```

</Accordion>

<div data-zendesk-anchors="h_01HAS0VY179VDWWV6N5YY2578E=overview h_01HF9G8TXGTAJDFZFVT8WS3QJE=why-use-dynamic-query query-language-and-syntax=query-language-and-dialect h_01HF3KZXC2VHNG92YX25K9HX7Q=query-language-and-dialect h_01HASGQZ5ATBPQ0HF28ETAGPMJ=available-sources h_01HF45KMZNF95SC0K6DE7P4K1R=note 01HF3EJEN2KSRR56F9XF0VSPQF=preserving-privacy accessing-the-dynamic-query=accessing-dynamic-query h_01J3FBVTVW2NCNESK3SYR0G9Q8=accessing-dynamic-query h_01HAS0X3NDFM136YMYSAG88JD7=reference h_01HFKFTBD7BCVP8PT0FDNGVHXS=query-reference h_01HFM169F3W9FDZZ3A4SG7WW58=combining-sources h_01HFM169F3WECT4M32H1CVCMKS=querying-attribution-data h_01HF3TDC0A8N9ZXGJHY4MZE3Y6=sample-queries h_01HF40PRZV7DBMYQRS6YJK2RM4=obtain-crossapp-insights h_01HF40PRZVFHY7B0R1G5S5PRTG=explore-data-integrity h_01HF40PRZVB5N2B14VEYW2CB3N=calculate-custom-attribution-metrics h_01HF40PRZVDXPZBDT25B9JK2EE=enrich-your-custom-data-with-attribution-insights h_01HF40PRZVM2HGQMX9TCK8WF7Y=complex-attribution-and-firstparty-data-join h_01HF3V03EFAVYR6M4WX0BHSVDK=invalid-queries h_01HF40PRZVZWTSK4BJ6BQ1D7S0=no-group-by-statement h_01HF40PRZVY13XM4RVETNK7E6K=grouped-by-nonpermitted-attribution-data-field h_01HF40PRZVJ9G4BAXKGW5VZMJX=grouped-by-nonpermitted-custom-data-field h_01HF42A4B20727TQGPPMP20629=restricted-function" />

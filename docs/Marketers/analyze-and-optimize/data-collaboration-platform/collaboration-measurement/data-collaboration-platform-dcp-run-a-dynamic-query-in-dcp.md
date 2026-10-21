---
title: Data Collaboration Platform (DCP) - Run a dynamic query in DCP
deprecated: false
hidden: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-10-15T11:14:42Z'
  edited_at: '2026-10-18T06:49:15Z'
  id: 51953788887569
  locale: en-us
  section: Collaboration measurement
  section_id: 38034865098641
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/51953788887569-Data-Collaboration-Platform-DCP-Run-a-dynamic-query-in-DCP
---
**At a glance:** Dynamic Query lets you run your own SQL queries directly on your Data Collaboration Platform (DCP) data. Query your own data, your own AF attribution data, or data shared inside a collaboration, to answer specific questions without setting up a report.

## About Dynamic Query

Dynamic Query gives you the ability to run ad hoc, custom queries on your DCP data in real time to answer your specific collaboration questions quickly and efficiently.

* Let a collaborator better segment your data before they create an audience.
* Build your own campaign measurement logic with Dynamic Query.

Dynamic Query works differently depending on whether you are querying your own data or data shared in a collaboration.

## Before you start

Before you can run any query, <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">configure your cloud bucket destination</Anchor>. This step is required, because every query runs against your own cloud bucket and writes results directly to your storage. AppsFlyer does not store your query results, so your data stays within your own cloud environment.

## Run a query on your own data

The following sections cover how to access and query data you own. The Sources panel here only lists sources you own, you cannot add a collaborator's source in this view. To query data shared with you in a collaboration instead, see [Run a query with collaboration data](#).

### Access Dynamic Query

1. In AppsFlyer, go to the side menu > **Collaborate** > **Data Clean Room**.
2. Select the **Dynamic Query** tab.

### Write your query on your own data

1. Browse the source's fields in the Sources panel. Click a field to preview its distinct values.

   > 📘 **Note**
   >
   > This helps your filters match real data before you write the query. For more information, see <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-create-and-manage-sources">Data Collaboration Platform (DCP) - Create and manage sources</Anchor>.

2. Write your query freely, at raw level or aggregated, your choice. Every source here belongs to you, so there's no permission check and no GROUP BY requirement.

   > 📘 **Note**
   >
   > If you are also an AppsFlyer client, you can query your AF attribution data this way too, but results are aggregated only, even though it is your own data.


## Run a query with collaboration data

The following sections cover how to access and query data shared with you in a collaboration. To query only data you own instead, see [Run a query on your own data](#).

### Access Dynamic Query in a collaboration

1. In AppsFlyer, go to the side menu > **Collaborate** > **Data Clean Room**.
2. Select the **Collaborations** tab, then select the relevant collaboration.
3. Select the **Dynamic Query** tab.

When you query data shared in a collaboration, Dynamic Query can access every source <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-create-a-collaboration#step-4-associate-sources-optional">added to that collaboration</Anchor>.

### Write your query with collaboration data

1. Browse the source's fields in the Sources panel. Click a field to preview its distinct values.

   > 📘 **Note**
   >
   > This helps your filters match real data before you write the query. For more information, see <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-create-and-manage-sources">Data Collaboration Platform (DCP) - Create and manage sources</Anchor>.

2. <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-sharing-permissions">Check the source's permission type</Anchor> to determine whether your query needs a join. There are two permission types:

   

| Permission type | Join required? | Result level |
| --- | --- | --- |
| Intersected | Yes, you must join to your own source | Aggregated only |
| All Data | No, you can query it freely | Aggregated only |

3. Write your query with a GROUP BY clause or an aggregate function, such as `COUNT(*)`.

   > 🚧 **Important**
   >
   > A source you do not own always returns aggregated results, no matter which permission type it is shared under. Raw-level results stay available only for sources you own.


## Explore sample queries

The following examples show how each permission type works in practice.

<div id="h_01M56WAZ8WGKHMG3BJYXNYHJT4" />

<Accordion title="Find brand collaboration candidates">

This query uses the All Data permission to find the top brands in a collaboration by client count and revenue over the last 60 days.

```sql
SELECT
    t.brand_name,
    COUNT(DISTINCT t.hashed_email) AS total_clients,
    COUNT(*) AS total_purchases,
    SUM(t.revenue) AS total_revenue
FROM <collaborator_transactions_table> t
WHERE t.event_time BETWEEN DATE_SUB(current_date(), 60) AND current_date()
GROUP BY t.brand_name
ORDER BY total_revenue DESC
LIMIT 20;
```

</Accordion>

<div id="h_01M56WAZ8WWJ78CQCK17FXWCWF" />

<Accordion title="Build a loyalty club retargeting segment">

This query uses the Intersected permission. It joins your own loyalty club data to a collaborator's purchase data, by country, over the last 30 days.

```sql
SELECT
    t.country,
    COUNT(DISTINCT l.hashed_email) AS loyalty_members,
    COUNT(*) AS total_purchases,
    SUM(t.revenue) AS total_revenue
FROM <collaborator_transactions_table> t
JOIN <my_loyalty_club_table> l ON l.hashed_email = t.hashed_email  -- required join satisfies intersection permission
WHERE t.event_time BETWEEN DATE_SUB(current_date(), 30) AND current_date()
    AND t.brand_name = '<collaborator_brand_name>'
GROUP BY t.country
ORDER BY total_revenue DESC
LIMIT 20;
```

</Accordion>

<div id="h_01M56WAZ8W6KN04JZN06T75A9A" />

<Accordion title="Discover audiences before a user acquisition (UA) campaign">

This query uses the All Data permission to segment a collaborator's transactions by country and category, so you can discover high-value audiences before you create one for user acquisition.

```sql
SELECT
    t.country,
    t.category,
    COUNT(DISTINCT t.hashed_email) AS total_buyers,
    COUNT(*)                       AS total_purchases,
    SUM(t.revenue)                 AS total_revenue,
    AVG(t.revenue)                 AS avg_order_value
FROM <collaborator_transactions_table> t
WHERE t.event_time BETWEEN DATE_SUB(current_date(), 30) AND current_date()
GROUP BY t.country, t.category
ORDER BY total_buyers DESC
LIMIT 20;
```

</Accordion>

## View and download query results

The following sections cover how to run your query and manage its results.

<div id="h_01M56WAZ8WXC0X46H2P3AY3GFX" />

<Accordion title="Dynamic Query run modes">

Every query runs in one of two modes:

* **Sample data** (default) runs on a small subset of your data, so you can refine your query before running it on the full dataset.
* **All data** runs against the complete source. Only this mode has a **Download** button.

> 📘 **Note**
>
> Don't confuse the **All data** run mode with the **All Data** permission type. Permission types control what a collaborator can access. Run modes control how much of your own query you execute.

</Accordion>

<div id="h_01M56WAZ8W2E7P4S60T0WJ4NNF" />

<Accordion title="Query history">

Your query and its results stay in place as you move between tabs and worksheets. You can open multiple worksheets to work on different queries at once.

Select **All runs** to see your query history, including status and duration for each run, run in either Sample data or All data mode.

</Accordion>

<div id="h_01M56WAZ8WCVEVWRQK68736H02" />

<Accordion title="Result limits and downloads">

Results display in pages of 100 rows, up to 10 pages (1,000 rows total). To see everything, download the results. Your total result count always shows, even if it is larger than what is displayed. This count caps at 10 million, so if your actual result count is 20 million, the displayed count still shows 10 million.

You can download up to 1 million rows directly. If your results are larger, Dynamic Query redirects you to your <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">cloud bucket</Anchor> instead. Your cloud bucket holds up to 10 million rows. If you need more, contact your Customer Success Manager (CSM) to expand this limit.

</Accordion>

## Privacy and query restrictions

Dynamic Query applies privacy protections at multiple levels:

* Non-owned sources always return aggregated results, see [Run a query with collaboration data](#).
* Key-type identifier fields, such as AppsFlyer ID, Android ID, and IDFA (Identifier for Advertisers), always return as hashed values in query results.
* Distinct values are not available for fields categorized as Keys, such as AppsFlyer ID or Android ID, when browsing the Sources panel.

## Traits and limitations

| Trait | Description |
| --- | --- |
| Result display limit | 1,000 rows (100 rows per page, up to 10 pages) |
| Download limit | 1 million rows direct, 10 million rows through your cloud bucket, contact your CSM to expand |
| Cloud bucket setup | Required before you can run any query, not just before downloading |
| Run modes | Sample data (default, no download) and All data (full source, download available) |

## See also

* <Anchor target="_blank" href="/marketers/docs/data-clean-room-dynamic-query">Data Clean Room Dynamic Query</Anchor>
* <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-guide">Data Collaboration Platform (DCP) guide</Anchor>
* <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-sharing-permissions">Data Collaboration Platform (DCP) sharing permissions</Anchor>
* <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-create-a-collaboration#step-4-associate-sources-optional">Data Collaboration Platform (DCP) - Create a collaboration</Anchor>
* <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary">Raw data field dictionary</Anchor>

<div data-zendesk-anchors="h_01M56WAZ8VZKYM6TP7AYGKQA52=about-dynamic-query h_01M56WAZ8VQ4D6NHCNJ463ZJE4=before-you-start h_01M56WAZ8VPZPM8P1H0DNVTTA6=run-a-query-on-your-own-data h_01M56WAZ8VQ4NNZEYAX4ZAZCFZ=access-dynamic-query h_01M56WAZ8VPG7QEAPSSBG11N11=write-your-query-on-your-own-data h_01M56WAZ8VDWA030BB53YP1TR2=note h_01M56WAZ8VBVRQV8B7J0TA21ZM=note-1 h_01M56WAZ8V82DRQ92ZPC3KFZYJ=run-a-query-with-collaboration-data h_01M56WAZ8VK33RR50SWQYV7KE0=access-dynamic-query-in-a-collaboration h_01M56WAZ8WXRM23PDCTA11APA2=write-your-query-with-collaboration-data h_01M56WAZ8WM0ZHFDKTT7AZ1CG8=note-2 h_01M56WAZ8W01XKEQDYVZCQ23ZZ=important h_01M56WAZ8W348ZTS79F23MAP3C=explore-sample-queries h_01M56WAZ8WZ23RCK7TYQC2FPZD=view-and-download-query-results h_01M56WAZ8WK936BRP4F7VHG954=note-3 h_01M56WAZ8W471Z9B14ZJ3V41VC=privacy-and-query-restrictions h_01M56WAZ8WCVFPD8JMHQ39HMEJ=traits-and-limitations h_01M56WAZ8WBY66ZBNHSNGFAJKD=see-also" />

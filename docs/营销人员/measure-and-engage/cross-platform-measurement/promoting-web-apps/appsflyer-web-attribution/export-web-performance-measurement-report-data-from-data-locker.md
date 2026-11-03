---
title: 从Data Locker导出网页端效果衡量报表数据
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T10:49:59Z'
  edited_at: '2026-10-14T10:00:23Z'
  id: 43510758321809
  locale: zh-cn
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/zh-cn/articles/43510758321809
---
> **概览：** 您可以从Data Locker导出两类网页端效果衡量报表，并根据分析需求选择合适的颗粒度来分析网站表现。使用「终端用户事件」报表分析所有访问和事件，使用「转化」报表统计独立转化锚点（首次访问、再次访问和用户获取事件）并进行归因。

> 🚧 **重要提示！**
>
> 您需要订阅Data Locker，才能访问其中的网页端效果衡量报表。

## 关于网页端效果衡量报表

Data Locker为网页端效果衡量提供两类报表：**终端用户事件**和**转化**，分别适用于不同的分析需求。

* **网页端终端用户事件**报表是分析网站活跃数据的主要数据来源：
  * 包含**所有网页端事件和访问**
  * 将每次访问记录为已归因的`SESSION`
  * 适用于**访问层级**和**事件层级**报表
* **转化**报表最适合用于转化层级分析。每次转化都是一个归因锚点，用于确定何时进行归因，以及如何分配营销贡献。其中包括：
  * *首次访问*（用户首次访问您的网站）；
  * *再次访问*（用户与非自然广告互动后再次访问您的网站）；以及
  * *用户获取事件*（注册或首次存款等表示已获取用户的自定义事件）。
* 系统之后会将所有用户事件关联到这些转化，并为事件沿用相应的广告系列详情。

## 报表字段

如需了解报表中包含哪些字段，请下载各报表的示例文件：

* [终端用户事件报表示例](https://docs.google.com/spreadsheets/d/e/2PACX-1vQYFF0r4pMpo_voSK8QObpiRtx-diU_0a-0XVuKIVMEfh6rRPudIDXA5bgDw_lcc0qwBPcPhYtLdWwh/pub?output=csv)
* [转化事件报表示例](https://docs.google.com/spreadsheets/d/e/2PACX-1vTMqcc6PKBATBg1DYVO8MWKrAs_wlqXxyANe3a_gu62xp3hFZV9wWT1X8c9oRekaIEwCfKZ2y9agVeV/pub?output=csv)

示例报表包含所有报表字段及对应值。有关字段定义，请参阅<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">字段字典</Anchor>。

## 报表更新时间和数据时效性

以下信息说明新数据何时写入报表，以及近期事件何时可在报表中查看。

* **报表更新频率**：每小时写入一次新数据。
* **数据时效性**：事件发生后通常会在2至3小时内显示在报表中。

### 每批数据的处理方式如下：

* 每批数据会**处理**1.5小时窗口内发生的事件。
* 在该窗口内，只有前1小时发生的事件会进行**归因**。
* 剩余30分钟的数据**仅用于**为已归因事件补充Customer User ID（CUID）。
* 最近30分钟内发生的事件**暂未归因**，将在下一批数据中处理。

[![](https://files.readme.io/1957b8b0c6b29fb44934ef7d10fd04278d541a4f2c12bb90e49fc8cb61ec7db5-44460048223761.png)](https://files.readme.io/1957b8b0c6b29fb44934ef7d10fd04278d541a4f2c12bb90e49fc8cb61ec7db5-44460048223761.png)

### 这些事件何时会显示在报表中？

事件会在**处理完成后**写入报表。例如，**08:00–09:00**发生的事件会在10:00批次中完成归因，并显示在**11:00发布的报表版本**中。

### 示例：10:00批次的处理内容

| **日期** | **报表可用时间** | **完成归因的网页端事件（事件时间）** | **为此前事件补充CUID而处理的网页端事件** |
| --- | --- | --- | --- |
| 2026-01-28 | 11:00 | 08:00–09:00 | 09:00–09:30 |
| 2026-01-28 | 12:00 | 09:00–10:00 | 10:00–10:30 |
| 2026-01-28 | 13:00 | 10:00–11:00 | 10:00–11:30 |

## 如何访问云存储桶中的报表数据

有关如何访问云存储桶中报表数据的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers#folder-structure">Data Locker文件夹结构</Anchor>。

## BI开发者注意事项

<div id="key-differences-web-vs-mobile" />

<Accordion title="主要区别：网页端与移动端">

网页端归因与移动端归因使用的标识符和数据逻辑均不同。为提高数据准确性，请在查询中应用以下筛选条件并遵循相关最佳实践。

| 对比项 | 移动端 | 网页端 |
| --- | --- | --- |
| 平台筛选条件 | `platform = 'IOS'`或`platform = 'ANDROID’` | `platform = 'WEBSITE'` |
| 用户标识符（值） | `appsflyer_id`（基于设备） | `appsflyer_id_value`（基于Cookie） |
| 标识符类型 | 根据设备而异 | `appsflyer_id_type`始终为`web_id` |
| 用户获取事件 | 激活 | 默认为首次访问，但可以自定义用户获取事件 |
| 再互动 | `RE-ENGAGEMENT` | `REVISIT` |
| 再归因 | 支持 | 不支持——网页端仅包含用户获取和再次访问 |
| 应用ID | 应用ID（例如`id123456789`） | 包含前缀的域名（例如`website-www.example.com`） |

</Accordion>

<div id="which-table-to-query" />

<Accordion title="应查询哪个数据表？">

**终端用户事件**报表适用于大多数分析场景。该报表包含网站上的所有事件和访问。该报表还会将每次网页端访问记录为已归因的`SESSION`，是生成访问层级和事件层级报表的主要数据来源。

如果需要统计独立转化，同时避免出现重复的事件记录，**转化**表主要适用于统计首次访问、再次访问和用户获取。

| 用例 | 数据表 | 适用原因 |
| --- | --- | --- |
| 统计访问次数/会话数 | `end_user_events` | 每行代表一次会话或一个事件 |
| 统计独立转化 | `conversions` | 避免重复 |
| 分析应用内事件 | `end_user_events`与`end_user_event_type = 'IN_APP'`结合使用 | 只有应用内事件包含事件名称 |

</Accordion>

<div id="implement-query-filters" />

<Accordion title="应用查询筛选条件">

为确保原始数据查询结果准确，请应用以下筛选条件。如未应用，查询结果中将出现重复记录，且不同平台的指标会混在一起。

* **按平台筛选（必需）：** 添加`WHERE platform = 'WEBSITE'`，仅查询源自网页端的数据，并排除移动端、PC端或CTV环境中的记录。
* **按归因贡献筛选（必需）：** 同一用户操作可能在`end_user_events`中出现两次，因为AppsFlyer可能会根据报表视图为该操作分配两种不同的归因贡献。

  用户存在以下两个来源时，就可能出现这种情况：

  * 最初的<strong>用户获取（UA）</strong>来源；以及后续的
  * **再互动**来源。

  在这种情况下，AppsFlyer可能会为同一事件写入两条记录：

  * **主要归因贡献：** 将事件归因到最近一次相关的营销互动。用于统一视图和再营销视图。

    为避免重复统计，查询`end_user_events`时应默认仅使用主要归因记录：

    ```sql
    WHERE platform = 'WEBSITE'
      AND is_primary_attribution = true
    ```
  * **次要归因贡献：** 将事件归因到最初的UA来源。用于在用户获取视图中追踪生命周期价值（LTV）。

    由于同一用户操作可能存储为两条记录（一条采用主要归因贡献，另一条采用次要归因贡献），统计事件时如不添加筛选条件，可能会重复计算该操作。

    您可以将以下查询用作模板，通过BigQuery或其他BI工具分析网页端归因数据。

* **按转化类型筛选（可选）：** 添加`WHERE conversion_type = 'USER_ACQUISITION'`或`WHERE conversion_type = 'RETARGETING'`，根据广告系列类型筛选归因数据。

#### 筛选条件汇总表

| 筛选要求 | SQL逻辑 | 应用场景 |
| --- | --- | --- |
| 平台限定条件 | `WHERE platform = 'WEBSITE'` | 仅保留源自网页端的数据，排除其他平台的记录。 |
| 统一视图（避免重复） | `WHERE is_primary_attribution = true AND platform = 'WEBSITE'` | 再营销广告系列的归因优先级高于最初的UA广告系列。适用于常规报表，可避免重复统计。 |
| 仅限再营销视图 | `WHERE conversion_type = 'RETARGETING' AND platform = 'WEBSITE'` | 仅在单独分析再营销广告系列表现时使用。 |
| 仅限用户获取视图 | `WHERE conversion_type = 'USER_ACQUISITION' AND platform = 'WEBSITE'` | 仅用于以用户获取为重点的视图，其中事件必须关联到首次访问。 |

</Accordion>

<div id="identifying-and-counting-end-users" />

<Accordion title="识别并统计终端用户">

在网页端效果衡量原始数据中，同一终端用户可能使用两种不同的标识符出现：

* `customer_user_id`：由您设置的稳定标识符（通常用于已登录用户）。
* `appsflyer_id_value`：基于Cookie的ID，可能会随时间推移而失效。

为正确识别**独立用户**并计算**用户层级指标**，请始终使用：

```sql
COALESCE(customer_user_id, appsflyer_id_value)
```

具体逻辑如下：

* 如果`customer_user_id`存在，AppsFlyer会优先使用该标识符，因为该标识符更稳定。
* 如果不存在，AppsFlyer会回退使用`appsflyer_id_value`。

如需执行以下操作，请使用`COALESCE(customer_user_id, appsflyer_id_value)`：

* 统计独立用户数
* 按用户分组
* 筛选特定用户
* 按用户关联数据表
* 计算任何用户层级指标

#### 示例：统计独立用户数

```sql
SELECT 
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users
FROM `end_user_events`
WHERE platform = 'WEBSITE'
  AND is_primary_attribution = TRUE
```

</Accordion>

<div id="organic-vs-nonorganic-traffic" />

<Accordion title="自然流量与非自然流量">

使用`is_organic`字段：

| 流量类型 | 筛选条件 |
| --- | --- |
| 自然 | `is_organic = true` |
| 非自然 | `is_organic = false` |

</Accordion>

<div id="handling-empty-values" />

<Accordion title="处理空值">

| 数据类型 | 空值 |
| --- | --- |
| 字符串 | `''`（空字符串） |
| 数值 | `NULL` |

</Accordion>

<div id="query-examples" />

<Accordion title="查询示例">

<div id="1-total-visits-by-media-source-7-days" />

<Accordion title="1按媒体渠道统计访问总次数（7天）">

统计归因到各媒体渠道的网页端会话数。

```sql
SELECT media_source, COUNT(*) AS total_visits
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'SESSION'
GROUP BY media_source
ORDER BY total_visits DESC
```

</Accordion>

<div id="2-first-visits-and-revisits-by-campaign" />

<Accordion title="2按广告系列统计首次访问和再次访问">

```sql
SELECT campaign_name, conversion_name, COUNT(*) AS conversion_count
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name IN ('FIRST_VISIT', 'REVISIT')
GROUP BY campaign_name, conversion_name
ORDER BY conversion_count DESC
```

</Accordion>

<div id="3-count-distinct-event-names-inapp-events-only" />

<Accordion title="3统计不同事件名称的数量（仅限应用内事件）">

```sql
SELECT
  event_name,
  COUNT(*) AS event_count
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'IN_APP'
GROUP BY event_name
ORDER BY event_count DESC
```

</Accordion>

<div id="4-count-distinct-users-by-media-source" />

<Accordion title="4按媒体渠道统计独立用户数">

```sql
SELECT
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
GROUP BY media_source
ORDER BY unique_users DESC
```

</Accordion>

<div id="5-conversion-rate-first-visit-to-purchase-crosstable-join" />

<Accordion title="5转化率——首次访问至购买（跨表关联）">

```sql
WITH first_visits AS (
  SELECT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id,
    media_source
  FROM conversions
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND conversion_name = 'FIRST_VISIT'
),
purchases AS (
  SELECT DISTINCT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id
  FROM end_user_events
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND is_primary_attribution = true
    AND end_user_event_type = 'IN_APP'
    AND event_name = 'purchase'
)
SELECT
  fv.media_source,
  COUNT(DISTINCT fv.user_id) AS first_visit_users,
  COUNT(DISTINCT p.user_id) AS purchasers,
  SAFE_DIVIDE(COUNT(DISTINCT p.user_id), COUNT(DISTINCT fv.user_id)) AS conversion_rate
FROM first_visits fv
LEFT JOIN purchases p ON fv.user_id = p.user_id
GROUP BY fv.media_source
ORDER BY conversion_rate DESC
```

</Accordion>

<div id="6-revenue-by-campaign-last-7-days" />

<Accordion title="6按广告系列统计收入（过去7天）">

```sql
SELECT
  campaign_name,
  media_source,
  SUM(revenue_usd) AS total_revenue_usd,
  COUNT(*) AS revenue_events
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND revenue_usd IS NOT NULL
  AND revenue_usd <> 0.0
GROUP BY campaign_name, media_source
ORDER BY total_revenue_usd DESC
```

</Accordion>

<div id="7-organic-vs-nonorganic-first-visits-by-day" />

<Accordion title="7按天统计自然和非自然首次访问">

```sql
SELECT
  DATE(event_time) AS visit_date,
  CASE WHEN is_organic = true THEN 'Organic' ELSE 'Non-Organic' END AS traffic_type,
  COUNT(*) AS first_visits
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name = 'FIRST_VISIT'
GROUP BY visit_date, traffic_type
ORDER BY visit_date, traffic_type
```

</Accordion>

<div id="8-user-acquisition-vs-retargeting-breakdown" />

<Accordion title="8用户获取与再营销细分">

```sql
SELECT
  conversion_type,
  conversion_name,
  COUNT(*) AS conversions
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
GROUP BY conversion_type, conversion_name
ORDER BY conversions DESC
```

</Accordion>

<div id="9-click-id-distribution-google-meta-tiktok-etc" />

<Accordion title="9点击ID分布（Google、Meta、TikTok等）">

```sql
SELECT
  click_id_type,
  COUNT(*) AS events_with_click_id
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND click_id_type != ''
GROUP BY click_id_type
ORDER BY events_with_click_id DESC
```

</Accordion>

<div id="10-cohort-users-by-conversion-date-equivalent-to-mobile-install-date" />

<Accordion title="10按转化日期划分用户群组（相当于移动端激活日期）">

```sql
SELECT
  DATE(event_time__conversion) AS cohort_date,
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS cohort_users
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
GROUP BY cohort_date, media_source
ORDER BY cohort_date, cohort_users DESC
```

</Accordion>

</Accordion>

## 特性和限制

以下字段**不支持网页端数据**，因此始终为空：

| 字段 | 备注 |
| --- | --- |
| `advertising_id_type`、`hardware_id_type`等 | 两者 |
| `agency`、`site_id`、`ad_type` | 两者 |
| `platform_group` | conversions |
| `app_version__conversion` | end\_user\_events |
| 所有`__assist_*`字段 | conversions |

<div data-zendesk-anchors="h_01KJYKY2RFJKMR2M3VB6R5XKYK=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA about-the-data-locker-web-attribution-reports=%E5%85%B3%E4%BA%8E%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F%E6%8A%A5%E8%A1%A8 h_01KGM4FT90X1K2V8M8GJV6EW5K=%E5%85%B3%E4%BA%8E%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F%E6%8A%A5%E8%A1%A8 report-fields=%E6%8A%A5%E8%A1%A8%E5%AD%97%E6%AE%B5 h_01KGM4FT90WP73N1D75WWNT2TE=%E6%8A%A5%E8%A1%A8%E5%AD%97%E6%AE%B5 report-timing-and-data-freshness=%E6%8A%A5%E8%A1%A8%E6%9B%B4%E6%96%B0%E6%97%B6%E9%97%B4%E5%92%8C%E6%95%B0%E6%8D%AE%E6%97%B6%E6%95%88%E6%80%A7 h_01KGM4FT90B6W7KBS9K1FSSETD=%E6%8A%A5%E8%A1%A8%E6%9B%B4%E6%96%B0%E6%97%B6%E9%97%B4%E5%92%8C%E6%95%B0%E6%8D%AE%E6%97%B6%E6%95%88%E6%80%A7 here%E2%80%99s-how-each-batch-works=%E6%AF%8F%E6%89%B9%E6%95%B0%E6%8D%AE%E7%9A%84%E5%A4%84%E7%90%86%E6%96%B9%E5%BC%8F%E5%A6%82%E4%B8%8B h_01KGM4FT91MCGCBYSHE18JHQ96=%E6%AF%8F%E6%89%B9%E6%95%B0%E6%8D%AE%E7%9A%84%E5%A4%84%E7%90%86%E6%96%B9%E5%BC%8F%E5%A6%82%E4%B8%8B when-will-these-events-appear-in-the-report=%E8%BF%99%E4%BA%9B%E4%BA%8B%E4%BB%B6%E4%BD%95%E6%97%B6%E4%BC%9A%E6%98%BE%E7%A4%BA%E5%9C%A8%E6%8A%A5%E8%A1%A8%E4%B8%AD h_01KGM4FT91XF7HCM8E8TQ56D0D=%E8%BF%99%E4%BA%9B%E4%BA%8B%E4%BB%B6%E4%BD%95%E6%97%B6%E4%BC%9A%E6%98%BE%E7%A4%BA%E5%9C%A8%E6%8A%A5%E8%A1%A8%E4%B8%AD example-what-the-1000-am-batch-does=%E7%A4%BA%E4%BE%8B1000%E6%89%B9%E6%AC%A1%E7%9A%84%E5%A4%84%E7%90%86%E5%86%85%E5%AE%B9 h_01KGM4FT91D90DWYGSE3SES2ZY=%E7%A4%BA%E4%BE%8B1000%E6%89%B9%E6%AC%A1%E7%9A%84%E5%A4%84%E7%90%86%E5%86%85%E5%AE%B9 how-to-access-report-data-in-your-cloud-bucket=%E5%A6%82%E4%BD%95%E8%AE%BF%E9%97%AE%E4%BA%91%E5%AD%98%E5%82%A8%E6%A1%B6%E4%B8%AD%E7%9A%84%E6%8A%A5%E8%A1%A8%E6%95%B0%E6%8D%AE h_01KGM4FT91NECKXMDW60A4B9X5=%E5%A6%82%E4%BD%95%E8%AE%BF%E9%97%AE%E4%BA%91%E5%AD%98%E5%82%A8%E6%A1%B6%E4%B8%AD%E7%9A%84%E6%8A%A5%E8%A1%A8%E6%95%B0%E6%8D%AE bi-developer-considerations=bi%E5%BC%80%E5%8F%91%E8%80%85%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01KGM4FT91C2KP050ZAYW6K8FD=bi%E5%BC%80%E5%8F%91%E8%80%85%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01KGM4FT91VNYYB998QBR6SDCC=key-differences-web-vs-mobile h_01KGM4FT91DEJT1GSA24MDMENV=which-table-to-query h_01KGM4FT91CTGZVST46MYYVJXV=implement-query-filters filter-summary-table=%E7%AD%9B%E9%80%89%E6%9D%A1%E4%BB%B6%E6%B1%87%E6%80%BB%E8%A1%A8 h_01KGM4FT91MSN2SN7TKNJZ54V4=%E7%AD%9B%E9%80%89%E6%9D%A1%E4%BB%B6%E6%B1%87%E6%80%BB%E8%A1%A8 h_01KGM4FT91BXMPKWXWSHH1X1W2=identifying-and-counting-end-users example-count-distinct-users=%E7%A4%BA%E4%BE%8B%E7%BB%9F%E8%AE%A1%E7%8B%AC%E7%AB%8B%E7%94%A8%E6%88%B7%E6%95%B0 h_01KGM4FT91VDR0FWTMAPW6GM83=%E7%A4%BA%E4%BE%8B%E7%BB%9F%E8%AE%A1%E7%8B%AC%E7%AB%8B%E7%94%A8%E6%88%B7%E6%95%B0 h_01KGM4FT91M2ZJ58PFZDE2W26J=organic-vs-nonorganic-traffic h_01KGM4FT91KYHDHYMK2FNE15CN=handling-empty-values h_01KGM9GZMRDVQKM3BQWX9E44E2=query-examples h_01KGM9GZMR7E8NQY9QN1Z0EEX8=1-total-visits-by-media-source-7-days h_01KGM9GZMRQ89CSXVJ4T4995FR=2-first-visits-and-revisits-by-campaign h_01KGM9GZMR90V0V4HBNM46RM1X=3-count-distinct-event-names-inapp-events-only h_01KGM9GZMRZBGNJYF7Y4N912HV=4-count-distinct-users-by-media-source h_01KGM9GZMR5SKN6PHD0NSK0JT0=5-conversion-rate-first-visit-to-purchase-crosstable-join h_01KGM9GZMRK2HTDSRHP5RJ059E=6-revenue-by-campaign-last-7-days h_01KGM9GZMRPVQX2WENF6MXPT1D=7-organic-vs-nonorganic-first-visits-by-day h_01KGM9GZMRER33GK5BYS3G66XJ=8-user-acquisition-vs-retargeting-breakdown h_01KGM9GZMRKNSG5JFE26XJZ2A6=9-click-id-distribution-google-meta-tiktok-etc h_01KGM9GZMRMJNSX8WV0WG01FCZ=10-cohort-users-by-conversion-date-equivalent-to-mobile-install-date traits-and-limitations=%E7%89%B9%E6%80%A7%E5%92%8C%E9%99%90%E5%88%B6 h_01KGM4FT91QZR30KJAQ87AG691=%E7%89%B9%E6%80%A7%E5%92%8C%E9%99%90%E5%88%B6" />

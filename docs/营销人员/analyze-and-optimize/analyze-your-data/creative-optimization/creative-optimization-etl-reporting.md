---
title: 素材优化的ETL数据上报
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-10-10T14:33:17Z'
  edited_at: '2026-10-14T09:59:48Z'
  id: 19253873174801
  locale: zh-cn
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/zh-cn/articles/19253873174801
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：概要：** 您可以使用Data Locker持续将素材优化数据自动拉取到云存储工具中，以程序化方式高效完成数据入库。/strong>

## 素材优化的ETL工具简介

素材优化数据的提取、转换、加载（Creative Optimization ETL）工具能让您的数据分析专员获得所有必要信息，帮助其完成素材效果分析。该工具可自动将<Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-guide">素材优化</Anchor>数据传输到云存储平台，以便您通过程序化的方式将数据入库到您的BI系统。

该工具提供素材资产层级的完整数据，包括所有投放KPI、浅层及深层漏斗KPI、归因数据以及素材资产数据。

Creative Optimization ETL使用<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">Data Locker</Anchor>将您的素材优化数据发送到云存储平台。我们提供多种存储方案供您选择，包括AppsFlyer的AWS存储桶或您在AWS、GCS、Yandex、BigQuery、Snowflake等各种平台上的自有存储桶。Data Locker支持多宿端数据传输，也就是说您可以将数据同时传输到多个宿端，或分宿端传输不同的数据，并根据您的实际需求调整数据的传输方式。如需使用Creative Optimization ETL，需购买**素材优化高阶付费套餐**。

<div id="get-started" />

## 启用方式

本节介绍如何为创意优化报告设置 Data Locker。

<div id="set-up-data-locker" />

<Accordion title="设置Data Locker">

**前期准备**：

通过您的 AppsFlyer 客户成功经理订阅创意优化高级计划。订阅后，您可以设置数据储物柜。

**请按以下步骤设置Data Locker：**

1. 1. 按<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers#set-up-data-locker">此文档</Anchor>中的说明完成相关操作。
2. 2. 设置Data Locker时，在Data Locker配置页面的**报告类型**部分中选择Creative（素材）。

![数据存储 - 选择创意优化.jpg](https://files.readme.io/d69a0f361c585dbb7c2d9fe0f47bc87d79712a954a3fb347de7b32b6e73fbb90-51911142204305.jpg)

</Accordion>

<div id="edit-data-locker-configuration" />

<Accordion title="修改Data Locker配置">

本章节说明了现有Data Locker配置的修改方式，您可以按照这部分内容在Data Locker中添加素材优化报告的数据。

**请按以下方式在Data Locker中添加素材优化数据：**

1. 从AppsFlyer后台左侧的菜单栏中选择**导出 > Data Locker**。
2. 在数据存储配置页面，选择 **选择报告**，选择 **创意优化**。

![数据存储 - 选择创意优化.jpg](https://files.readme.io/d69a0f361c585dbb7c2d9fe0f47bc87d79712a954a3fb347de7b32b6e73fbb90-51911142204305.jpg)

</Accordion>

## 其他相关信息

<div id="data-freshness" />

<Accordion title="数据时效性">

配置完毕后，素材优化报告会以每天一次的频率传输到Data Locker，每份报告提供最近30天的数据，它将在 UTC + 12 每天播放。也就是说，每天更新的当地时间取决于您所在的地理位置，您可以根据“0 UTC + 10 + 当地时区”来计算更新的当地时间。

**示例：**  
纽约 0 UTC + 12 - 5 = 7:00  
Berlin        0 UTC + 12 + 1 = 13:00  
上海 0 UTC + 12 + 8 = 20:00

</Accordion>

<div id="available-data" />

<Accordion title="可用数据">

Data Locker中的可用素材数据如下：

| 字段 | 类型 |
| --- | --- |
| date | 字符串 |
| asset\_link | 字符串 |
| creative | 字符串 |
| media\_source | 字符串 |
| campaign | 字符串 |
| campaign\_id | 字符串 |
| ad | 字符串 |
| ad\_id | 字符串 |
| adset | 字符串 |
| adset\_id | 字符串 |
| app\_name | 字符串 |
| app\_id | 字符串 |
| creative\_first\_seen | 字符串 |
| 素材使用时长 | 字符串 |
| creative\_type | 字符串 |
| 时长 | 字符串 |
| end\_card\_type | 字符串 |
| geo | 字符串 |
| platform | 字符串 |
| 画面方向 | 字符串 |
| 分辨率 | 字符串 |
| impressions | 字符串 |
| clicks | 字符串 |
| installs | 字符串 |
| ctr | 字符串 |
| cvr | 字符串 |
| ipm | 字符串 |
| cost | 字符串 |
| ecpi | 字符串 |
| reattributions | 字符串 |
| reengagements | 字符串 |
| CPM | 字符串 |
| roas\_d1 | 字符串 |
| roas\_d7 | 字符串 |
| roas\_d14 | 字符串 |
| roas\_d30 | 字符串 |
| roas\_d60 | 字符串 |
| roas\_d90 | 字符串 |
| retention\_d1 | 字符串 |
| retention\_d7 | 字符串 |
| retention\_d14 | 字符串 |
| retention\_d30 | 字符串 |
| retention\_d60 | 字符串 |
| retention\_d90 | 字符串 |
| revenue\_d1 | 字符串 |
| revenue\_d14 | 字符串 |
| revenue\_d30 | 字符串 |
| revenue\_d60 | 字符串 |
| revenue\_d7 | 字符串 |
| Revenue\_d90 | 字符串 |
| partner\_cpm | 字符串 |
| partner\_ctr | 字符串 |
| partner\_cvr | 字符串 |
| partner\_clicks | 字符串 |
| partner\_cost | 字符串 |
| partner\_ipm | 字符串 |
| partner\_impressions | 字符串 |
| partner\_installs | 字符串 |
| partner\_ecpi | 字符串 |

查看<Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-guide#standard-metrics-and-dimensions">标准指标</Anchor>和素材优化<Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-guide#unique-metrics-and-dimensions">专用指标</Anchor>的定义。

> 📘 **注意**
>
> * 当广告没有可用的预览时，**资产链接** 和 **创意** 列将不会被填充。
> * 下列数据不可用：
>   * Custom dimension
>   * 自定义指标
>   * 应用内事件
>   * AI数据（元素及场景）
>   * 再营销数据

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 成本数据 | 需要 ROI360 订阅才能将成本数据包含在创意优化 ETL 报告中。 |

</Accordion>

<div data-zendesk-anchors="about-creative-etl=%E7%B4%A0%E6%9D%90%E4%BC%98%E5%8C%96%E7%9A%84etl%E5%B7%A5%E5%85%B7%E7%AE%80%E4%BB%8B h_01HCF5ZDDGTN52MZ9DX2MDKJV7=%E7%B4%A0%E6%9D%90%E4%BC%98%E5%8C%96%E7%9A%84etl%E5%B7%A5%E5%85%B7%E7%AE%80%E4%BB%8B get-started=%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HCF65RS2NKHEDHFE9TN78ES8=%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HCFF8BWHGFX5KEZWKVDYXKKA=set-up-data-locker h_01HCFF8BWJCQHNN17N8G555FP9=edit-data-locker-configuration data=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HCF8C8S392WJMYYHV6ECMNCW=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HCFC87EDDD3X0ZXNCAQAHTZB=data-freshness h_01HCFBYBBMNZ52TH4M3G3YB3YM=available-data h_01HF44ZFSHJ8MX9ZNBF7SWB5JN=%E6%B3%A8%E6%84%8F 01JH2M65K4MC96MZE4CVRPMS8B=traits-and-limitations" />

---
title: 数据协作平台（DCP） - 协作衡量 - 概览
metadata:
  keywords:
    - Marketers
    - Retail Media Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Retail Media Measurement
  created_at: '2025-01-27T08:21:27Z'
  edited_at: '2026-10-14T10:08:07Z'
  id: 32143318560017
  locale: zh-cn
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/zh-cn/articles/32143318560017
---
> **概要：** 介绍协作归因的基本概念和设置流程，帮助您使用协作衡量功能。

## 站内与站外广告系列归因

DCP对站内和站外广告采取不同的的衡量方式。站内广告是协作者自身平台上投放的广告，站外广告则是在第三方平台上，如Facebook、Google Ads以及其他SRN上投放的广告由于DCP无法直接访问第三方平台的用户交互数据，其归因流程和数据结构与站内广告不同，因此需要采用专门的解决方案。除非特别说明，本文中的信息同时适用于这两种类型的广告。

<div id="the-three-data-sources-of-measurement" />

## 三类衡量数据来源

DCP的归因模型通过将转化事件与用户交互事件进行匹配，从而完成归因。此流程依赖以下三类关键数据源：转化数据、用户交互数据和广告映射数据。在归因流程，每种数据都起着关键作用。

<div id="conversions" />

<Accordion title="转化">

转化数据包含与用户行为有关的详细信息，例如购买行为及相关的库存单位（SKU）或快速消费品（CPG）。每条转化记录代表一次独立的转化事件，记录了如SKU、用户ID以及事件时间等详细信息。

**转化参数示例**

| **字段** | **参数值** |
| --- | --- |
| `app_id` | FoodDelivery |
| `user_id` | 5abe2ddccca43000af58f0b |
| `event_time` | 2024-08-21T16:06:32.393Z |
| `event_name` | 记录负收入 |
| `sku` | 8711327623057 |
| `sku_revenue` | 6.94 |
| `sku_quantity` | 1 |

AppsFlyer可通过将AppsFlyer SDK对接到您的应用中，或借助协作者提供的自定义数据源，获取应用内转化数据。网页端和线下门店的转化事件也可以通过自定义数据源接入。

</Accordion>

<div id="engagements" />

<Accordion title="交互">

交互数据来源包含用户与广告交互的详细信息，例如点击或展示。每条记录代表一次互交互事件，包括广告ID、媒体来源以及触达类型（例如点击或展示）等。

**交互参数示例**

| **字段** | **参数值** |
| --- | --- |
| `appsflyer_id` | 1727548724223 |
| `media_source` | google |
| `campaign` | grc\_web\_ftu\_seq |
| `attributed_touch_time` | 2024-09-28T17:05:34 |
| `attributed_touch_type` | 展示（impression）： |
| `event_name` | start\_game |

要访问交互数据，在[站内广告](#站内与站外广告系列归因)中，您可以使用 AppsFlyer SDK 设置新的应用内事件，并在参数中包含`event_value`归因数据，或通过自定义数据源共享互动数据。

而在[站外广告中，互动数据由第三方平台提供](#站内与站外广告系列归因)，不通过应用内事件或自定义数据源传递。

</Accordion>

<div id="campaign-mapping" />

<Accordion title="广告系列映射">

借助广告系列映射数据源，我们能够确定触发转化的具体交互事件。广告系列映射将SKU或CPG与广告系列ID进行配对，将转化事件与交互事件关联起来。借助这种映射，DCP可以将包含特定SKU的转化事件与包含相应广告系列ID的交互事件进行匹配，从而完成归因。

**广告系列映射参数示例**

| **字段** | **参数值** |
| --- | --- |
| `collaborator_name` | fashion\_site |
| `collaborator_id` | 10079 |
| `campaign_id` | 49fd77a2-8b64-4c9d... |
| `campaign_name` | off\_season\_25\_1 |
| `conversion_targets` | 8711327621978, 8711327622289, 8711327623057 |

广告系列映射信息就是AppsFlyer接收的一种自定义数据源接。

</Accordion>

<div id="the-dcp-measurement-process" />

## **DCP归因流程**

DCP的归因流程通过将转化事件中的SKU与投放该SKU的交互事件进行匹配，来实现转化与交互的关联归因。该流程使用协作数据、交互数据和广告系列映射数据这三类数据源来完成匹配。

以下是详细步骤：

1. DCP将广告系列映射数据与转化数据中的SKU进行匹配，以识别转化是由哪一广告触发。无法匹配的转化将被标记为自然流量（Organic）。
2. DCP将已匹配的转化事件与具有相同用户ID和广告系列ID的互动事件关联，生成包含广告系列与转化信息的归因记录。
3. 若某条归因记录包含多个SKU，DCP会将其拆分为多条记录，每条记录对应一个SKU。
4. DCP会过滤掉广告系列中未被定义为转化目标的SKU。
5. 归因逻辑说明：
   * 当多个交互事件与同一次转化相关联时，DCP会根据AppsFlyer的优先级规则，采用末次触达归因（Last-Touch Attribution）方式进行归因。如需更多信息，请参考<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#各种归因方式的优先级归因瀑布流">各种归因方式的优先级（归因瀑布流）</Anchor>。
   * 当同一个交互事件对应多个转化事件时，只有第一个转化事件会归因于该交互，其余的转化将保持未归因状态。
6. DCP 会对已归因的转化事件进行汇总以生成洞察报告，包括总转化量等。

### 四步完成归因设置

归因设置可分为四个主要步骤，我们在每一步都为您准备了对应的文档指南：

1. 明确您适用的协作场景
2. <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement">准备归因流程所需的数据源</Anchor>
3. <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-configure-collaboration-measurement">配置DCP以获取数据并进行归因</Anchor>
4. <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-view-measurement-dashboard">在数据面板或报告中使用归因数据</Anchor>
5. <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-view-measurement-reports">在数据面板或报告中使用归因数据</Anchor>

<div data-zendesk-anchors="onsite-and-offsite-campaign-measurement=%E7%AB%99%E5%86%85%E4%B8%8E%E7%AB%99%E5%A4%96%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E5%BD%92%E5%9B%A0 h_01JJKDD2YB8PPQ5EG7SSEQNV58=%E7%AB%99%E5%86%85%E4%B8%8E%E7%AB%99%E5%A4%96%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E5%BD%92%E5%9B%A0 the-three-data-sources-of-measurement=%E4%B8%89%E7%B1%BB%E8%A1%A1%E9%87%8F%E6%95%B0%E6%8D%AE%E6%9D%A5%E6%BA%90 h_01JJKDD2YBAGN14GY06HNBES4X=%E4%B8%89%E7%B1%BB%E8%A1%A1%E9%87%8F%E6%95%B0%E6%8D%AE%E6%9D%A5%E6%BA%90 h_01JJKDD2YB757FKYAAMDSKREWT=conversions h_01JJKDD2YBGP02RRRFX2Q0XAK7=engagements h_01JJKDD2YBXHY4XA5TPN4T9CH4=campaign-mapping the-dcp-measurement-process=dcp%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B h_01JJKDD2YBGEGZBF7K6F0TXJW7=dcp%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B set-up-measurement-in-four-steps=%E5%9B%9B%E6%AD%A5%E5%AE%8C%E6%88%90%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE h_01JJKDD2YBZ0F489P50SGE6TQF=%E5%9B%9B%E6%AD%A5%E5%AE%8C%E6%88%90%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE" />

---
title: 再营销事件的双重归因
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2020-12-13T07:35:18Z'
  edited_at: '2026-10-14T10:07:09Z'
  id: 360016371077
  locale: zh-cn
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/zh-cn/articles/360016371077
---
> **概要：** 概要：为了评估再营销广告在再互动窗口期间的投放效果，AppsFlyer会对相关的应用内事件和session（应用打开）进行双重归因，即同时归因到拉新渠道和再营销渠道。

![](https://files.readme.io/fce514999471aa7bfced06fa0e1c7d6fa7363a8d30119bd20d0b5d7e56eb1f7d-9479192551825.png)

<div id="overview" />

## 速览

* **再互动（沉睡用户唤醒）：**
* **再归因（流失用户召回）：**

以上图为例，用户激活应用并完成了一个应用内事件，这两个转化归因到green\_network（标为绿色）。之后，该用户与blue\_network（标为蓝色）上的再营销广告互动，并完成了两个事件。这两个事件的归因逻辑如下：

* blue\_network是促成再互动的主要来源。
* green\_network作为初始拉新渠道，是再互动的次要来源。

下表列出了再互动窗口前、中、后各场景中应用内事件的归因方式，以便您更清晰地了解其中的归因逻辑。表格中的说明部分列出了用于标识双重归因事件的原始数据字段：

* is\_primary\_attribution
* 请使用以下任意字段了解归因数据的背景信息：
  * 【推荐】**conversion\_type**：可能出现的参数值为install（激活）或re-engagement（再互动）
  * is\_retargeting：如果该参数值为true，则表示相关数据与再营销广告有关

<div id="attribution-relative-to-the-re-engagement-window" />

#### 与再互动窗口相关的归因

| 媒体渠道 | 再互动窗口前 | 再互动窗口期内 | 再互动窗口期后 |
| --- | --- | --- | --- |
| 用户获取 | 主要<br /><br />is\_primary\_attributionTrue<br /><br />conversion\_type: install<br /><br />is\_retargetingFalse | 此外，<br /><br />is\_primary\_attribution否<br /><br />conversion\_type: re-engagement<br /><br />is\_retargetingFalse | 主要<br /><br />is\_primary\_attributionTrue<br /><br />conversion\_type: install<br /><br />is\_retargetingFalse |
| 再营销 | 不适用 | 主要<br /><br />is\_primary\_attributionTrue<br /><br />conversion\_type: re-engagement<br /><br />is\_retargetingTrue | 不适用 |

<div id="support-for-dashboard-view-types" />

## 适用的面板视图类型

部分面板和群组报告提供多种视图选项，包括统一、用户获取和再营销。这些视图类型所使用的归因逻辑与原始数据相同。

![](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)

<div id="data-filtering-by-view-type-using-the-conversion_type-field" />

#### 可使用conversion\_type字段按视图类型筛选数据

<table><thead><tr><th>视图类型</th><th>conversion_type</th><th>is_primary</th><th>归因</th></tr></thead><tbody><tr><td rowspan="2">用户获取</td><td>install</td><td>对或错</td><td>归因到拉新渠道的激活</td></tr><tr><td>re-engagement</td><td>否</td><td>归因到拉新渠道的再营销事件</td></tr><tr><td>再营销</td><td>re-engagement或re-attribution</td><td>True</td><td>归因到再营销渠道的再营销事件</td></tr><tr><td>统一</td><td>install或re-engagement</td><td>True</td><td>归因到末次触达渠道的所有事件</td></tr></tbody></table>

<div id="how-do-i-identify-double-attributed-retargeting-events-in-user-acquisition-in-app-reports" />

## 如何在用户获取的应用内事件报告中识别双重归因的再营销事件？

在**UA应用内事件报告**中可根据以下条件识别双重归因的事件：

* is\_primary\_attribution字段可用于识别主要和次要渠道，该参数的值为false时，即表示相关转化是由再营销广告促成的，因此UA渠道为次要渠道。
* is\_retargeting字段的值总是为false。

在再互动窗口期内，再营销应用内事件报告中相应字段的填充方式如下：

* is\_primary\_attribution字段的值总是为true。
* is\_retargeting字段的值总是为true。
* 对于在再互动窗口期之外发生的事件，不会有任何记录。

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01J8FJW0TE4DV5BFHGARS4ERT6=%E9%80%9F%E8%A7%88 attribution-relative-to-the-reengagement-window=%E4%B8%8E%E5%86%8D%E4%BA%92%E5%8A%A8%E7%AA%97%E5%8F%A3%E7%9B%B8%E5%85%B3%E7%9A%84%E5%BD%92%E5%9B%A0 h_01J8FJW0TEJH716NXMM2RDN4J1=%E4%B8%8E%E5%86%8D%E4%BA%92%E5%8A%A8%E7%AA%97%E5%8F%A3%E7%9B%B8%E5%85%B3%E7%9A%84%E5%BD%92%E5%9B%A0 support-for-dashboard-view-types=%E9%80%82%E7%94%A8%E7%9A%84%E9%9D%A2%E6%9D%BF%E8%A7%86%E5%9B%BE%E7%B1%BB%E5%9E%8B h_01J8FJW0TEDFGFPPYZEAREKY4Q=%E9%80%82%E7%94%A8%E7%9A%84%E9%9D%A2%E6%9D%BF%E8%A7%86%E5%9B%BE%E7%B1%BB%E5%9E%8B data-filtering-by-view-type-using-the-conversion_type-field=%E5%8F%AF%E4%BD%BF%E7%94%A8conversion_type%E5%AD%97%E6%AE%B5%E6%8C%89%E8%A7%86%E5%9B%BE%E7%B1%BB%E5%9E%8B%E7%AD%9B%E9%80%89%E6%95%B0%E6%8D%AE h_01J8FJW0TETSV5X6D7NJ4EQHGC=%E5%8F%AF%E4%BD%BF%E7%94%A8conversion_type%E5%AD%97%E6%AE%B5%E6%8C%89%E8%A7%86%E5%9B%BE%E7%B1%BB%E5%9E%8B%E7%AD%9B%E9%80%89%E6%95%B0%E6%8D%AE how-do-i-identify-doubleattributed-retargeting-events-in-user-acquisition-inapp-reports=%E5%A6%82%E4%BD%95%E5%9C%A8%E7%94%A8%E6%88%B7%E8%8E%B7%E5%8F%96%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E6%8A%A5%E5%91%8A%E4%B8%AD%E8%AF%86%E5%88%AB%E5%8F%8C%E9%87%8D%E5%BD%92%E5%9B%A0%E7%9A%84%E5%86%8D%E8%90%A5%E9%94%80%E4%BA%8B%E4%BB%B6 h_01J8FJW0TED4T9JN89PCRA3M9R=%E5%A6%82%E4%BD%95%E5%9C%A8%E7%94%A8%E6%88%B7%E8%8E%B7%E5%8F%96%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E6%8A%A5%E5%91%8A%E4%B8%AD%E8%AF%86%E5%88%AB%E5%8F%8C%E9%87%8D%E5%BD%92%E5%9B%A0%E7%9A%84%E5%86%8D%E8%90%A5%E9%94%80%E4%BA%8B%E4%BB%B6" />

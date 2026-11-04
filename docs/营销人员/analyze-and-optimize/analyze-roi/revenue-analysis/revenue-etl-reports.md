---
title: 详情请见Data Locker中的Revenue ETL报告。
metadata:
  keywords:
    - Marketers
    - revenue
    - etl
    - revenueetl
    - revenue etl
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2023-06-25T16:57:02Z'
  edited_at: '2026-10-14T10:15:17Z'
  id: 16464765619985
  locale: zh-cn
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/zh-cn/articles/16464765619985
---
> **概要：**

<div id="revenue-etl" />

## 收入 ETL

**请注意**：

| 报告 | 对接类型 | 说明 | 数据时效性 |
| --- | --- | --- | --- |
| [旧版广告收入【单一版本报告】](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level) | <ul><li>通过SDK上报的展示级别数据。</li><li>通过S2S API上报设备级别数据</li><li>由SDK上报的展示级别数据与由S2S API上报的设备级别数据相结合</li></ul> |  |  |
| [广告收入【版本化报告】](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level) | <ul><li>通过SDK上报的展示级别数据。</li><li>通过S2S API上报设备级别数据</li><li>由SDK上报的展示级别数据与由S2S API上报的设备级别数据相结合</li></ul> |  | <ul><li>一天更新多次， <Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#data-freshness">详情请见此处说明。</Anchor></li></ul> |
| [广告收入【SDK展示层级】](/docs/revenue-etl-reports#impression-level-report) | <ul><li>通过SDK上报的展示级别数据。</li><li>由SDK上报的展示级别数据与由S2S API上报的设备级别数据相结合</li></ul> |  | 每小时更新一次<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#data-freshness">详情请见此处说明。</Anchor> |
|  | IAP和订阅收入的对接流程 |  | 每小时更新一次 |
|  | IAP和订阅收入的对接流程 |  | 每8小时更新一次 |

<div id="reports" />

## 报告

<div id="ad-revenue-single-version-report-device-level" />

<Accordion title="旧版广告收入【单一版本报告】">

**请注意：**

<div id="download-the-report-data-sample" />

#### Data Sources。

* **SDK**：
* S2S

广告收入平台的对接方式


2. <span id="data-flow-2"></span><span id="data-flow-1"></span><span id="data-flow"></span><span id="the-report-data-flow"></span>AppsFlyer的ROI360广告收入报告功能会完成下列数据处理工作：

   1. <span class="af-ol-a"></span>数据规范化
   2. 将收入归因到带来激活的渠道，并进行数据扩充。
   3. 生成广告收入事件
   4. 将事件汇总到设备级别

   **请注意：**
3. 数据传输


| <span id="when-is-the-report-data-available"></span>对接类型 |  |  |  |
| --- | --- | --- | --- |
| SDK |  | 20:00 | 00:00 — 24:00 |
| SDK + S2S |  | 17:00 | 00:00 — 24:00 |


1. <span id="how-to-subscribe-to-the-report"></span><span id="how-to-subscribe-to-the-report-2"></span><span id="how-to-subscribe-to-the-report::67646c99"></span>从AppsFlyer后台的侧边栏中选择**报告 > Data Locker**。

**请注意：**


<span id="how-to-access-the-report-in-dl"></span>构成报告路径的文件夹结构如下：

格式：`<bucket-name>/t=attributed_ad_revenue/dt=<dt=yyyy-mm-dd>/h=23/`

<div id="report-folder-hierarchy" />

#### 报告文件夹的层次结构

```
bucket
|
└── t=attributed_ad_revenue
    |
    ├── dt=2023-06-02
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        |
    |        ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        │
    |        └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |
    ├── dt=2023-06-01
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |
    ├── dt=2023-05-31
    |   |
    .   . 
    .   .
```

**说明：**

* **dt**：报告中的事件发生的日期。
* **t**：报告类型。

</Accordion>

<div id="ad-revenue-versioned-report-device-level" />

<Accordion title="广告收入【版本化报告】">

**请注意：**

#### Data Sources。

* **SDK**：
* S2S

广告收入平台的对接方式


2. AppsFlyer的ROI360广告收入报告功能会完成下列数据处理工作：

   1. <span class="af-ol-a"></span>数据规范化
   2. 将收入归因到带来激活的渠道，并进行数据扩充。
   3. 生成广告收入事件
   4. 将事件汇总到设备级别

   **请注意：**
3. 数据传输


| <span id="when-are-the-report-versions-available"></span>对接类型 |  |  |  |
| --- | --- | --- | --- |
| SDK |  | 03:00-04:00 | 00:00 — 03:00 |
| SDK |  | 07:00-08:00 | 00:00 — 07:00 |
| SDK |  | 11:00-12:00 | 00:00 — 11:00 |
| SDK |  | 15:00-16:00 | 00:00 — 15:00 |
| SDK |  | 21 | 6257(1) |
| SDK |  | 23:00-24:00 | 00:00 — 23:00 |
| SDK |  | 04:00-05:00 | 00:00 — 24:00 |
| S2S |  | 12:00-13:00 | 00:00 — 24:00 |
| S2S |  | 18:00-19:00 | 00:00 — 24:00 |
| S2S |  | 00:00-01:00 | 00:00 — 24:00 |
| S2S |  | 13:00-14:00 | 00:00 — 24:00 |
| S2S |  | 06:00-07:00 | 00:00 — 24:00 |
| S2S |  | 08:00-09:00 | 00:00 — 24:00 |
| S2S |  | 10:00-11:00 | 00:00 — 24:00 |
| SDK + S2S |  |  |  |

**请注意：**


1. <span id="report-folder-hierarchy-1"></span><span id="how-to-access-the-report-in-your-bucket-1"></span><span id="how-to-subscribe-to-the-report-1"></span><span id="how-to-subscribe-to-the-report::cae4aa15"></span>从AppsFlyer后台的侧边栏中选择**报告 > Data Locker**。

**请注意：**


<span id="how-to-access-the-report-in-your-bucket-2"></span><span id="how-to-access-the-report-in-your-bucket"></span>构成报告路径的文件夹结构如下：

`<bucket-name>/t=attributed_ad_revenue_v2/dt=<dt=yyyy-mm-dd>/version=<9999999>/`

<div id="transactionlevel-stores-revenue-report" />

<div id="report-folder-hierarchy-2" />

#### 报告文件夹的层次结构

```
bucket
|
└── t=attributed_ad_revenue_v2
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

* **说明：**
  * **t：** 报告类型
  * **dt**：报告中的事件发生的日期。
  * version

</Accordion>

<div id="impression-level-report" />

<Accordion title="广告收入【SDK展示层级】">

<div id="when-is-the-report-data-available-1" />

<div id="data-source" />

#### 数据来源

广告收入平台的对接方式


2. AppsFlyer的ROI360广告收入报告功能会完成下列数据处理工作：
   1. <span class="af-ol-a"></span>数据规范化
   2. 将收入归因到带来激活的渠道，并进行数据扩充。
3. 数据传输


| 对接类型 |  |  |
| --- | --- | --- |
| SDK |  |  |


1. 从AppsFlyer后台的侧边栏中选择**报告 > Data Locker**。
3. **广告收入【SDK展示层级】**


<span id="how-to-access-the-report-in-your-bucket-3"></span><span id="how-to-access-the-report-in-aws-the-bucket"></span>构成报告路径的文件夹结构如下：

`<bucket-name>/t=attributed_adrevenue_sdk_impression_level/dt=<dt=yyyy-mm-dd>/h=<hh>`

#### 报告文件夹的层次结构

```
bucket
|
└── t=attributed_adrevenue_sdk_impression_level/
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**说明：**

* **t：** 报告类型
* **dt**：报告中的事件发生的日期。
* H

</Accordion>

<div id="data-flow-3" />

#### Data Sources。



|  |  |
| --- | --- |
|  |  |


1. <span id="data-flow-4"></span><span id="how-to-subscribe-to-the-report-3"></span><span id="when-is-the-report-data-available-2"></span><span id="data-flow::bde19643"></span>从AppsFlyer后台的侧边栏中选择**报告 > Data Locker**。


<span id="how-to-access-the-report-in-your-bucket-4"></span><span id="how-to-access-the-report-in-your-bucket::b136ba80"></span>构成报告路径的文件夹结构如下：

`<bucket-name>/t=stores_rawdata/dt=<dt=yyyy-mm-dd>/h=<hh>`

<div id="devicelevel-stores-revenue-report" />

<div id="report-folder-hierarchy-3" />

#### 报告文件夹的层次结构

```
bucket
|
└── t=stores_rawdata
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**说明：**

* **t**：报告类型。
* **dt**：报告中的事件发生的日期。
* H


<div id="download-the-report-data-sample::8cbba4e3" />

#### Data Sources。



|  |  |  |
| --- | --- | --- |
|  | <span id="when-are-the-report-versions-available-1"></span><span id="the-report-data-processing-flow"></span>04:00 - 05:00 | 00:00 — 04:00 |
|  | 12:00 - 13:00 | 00:00 — 12:00 |
|  | 20:00 - 21:00 | 00:00 — 20:00 |
|  | 05:00 - 06:00 | 00:00 — 24:00 |


1. <span id="how-to-subscribe-to-the-report-4"></span><span id="how-to-subscribe-to-the-report::a624afde"></span>从AppsFlyer后台的侧边栏中选择**报告 > Data Locker**。


<span id="how-to-access-the-report-in-the-aws-bucket"></span>构成报告路径的文件夹结构如下：

`<bucket-name>/t=stores_devicedata/dt=<dt=yyyy-mm-dd>/version=<999999999>`

<div id="report-folder-hierarchy-4" />

#### 报告文件夹的层次结构

```
bucket
|
└── t=stores_devicedata
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

**说明：**

* **t**：报告类型。
* **dt**：报告中的事件发生的日期。
* **version**：

<div data-zendesk-anchors="revenue-etl=%E6%94%B6%E5%85%A5-etl h_01HMBTDD8TASZ2NEBXP7CZ3Q81=%E6%94%B6%E5%85%A5-etl reports=%E6%8A%A5%E5%91%8A h_01HME0BBF2M47M2AV437RYQ070=%E6%8A%A5%E5%91%8A h_01HETBAQVVYW14END06HBPBQSN=ad-revenue-single-version-report-device-level h_01HETBAQVVZB87JNT0JVYSP80D=download-the-report-data-sample the-report-data-sources=data-sources h_01HETBAQVVSKVDM4J90A0WGFJW=data-sources data-flow=the-report-data-flow data-flow::c7ffb834=the-report-data-flow h_01HETBAQVV97R7G6F67RM6K62K=the-report-data-flow h_01HMTZ9VQ5PS8G9JTQ2YXF1G7X=the-report-data-flow h_01HMTZ9VQ5J837PGG99S8ARAGV=the-report-data-flow h_01HETBAQVVKDAWW2S98TG6682S=when-is-the-report-data-available h_01HETBAQVVFSDRW778VQSSE107=how-to-subscribe-to-the-report h_01HETBAQVV15T92VXRHG2CP2KJ=how-to-access-the-report-in-dl the-report-folder-hierarchy-in-aws=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84 h_01HETBAQVVA750VTE1ABSM2M47=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84 h_01HETBAQVVCB2SYMW9876HPE7N=ad-revenue-versioned-report-device-level data-sources=data-sources-1 h_01HMTZ9VQ5WE6D7E5NEBYH71SZ=data-sources-1 h_01HETBAQVVP1M40KHB66AW545S=when-are-the-report-versions-available h_01HMTZ9VQ5BBFNNE7Z8EP084CF=how-to-subscribe-to-the-report::cae4aa15 h_01HMTZ9VQ5FGBC56AP4R49P4BX=how-to-access-the-report-in-your-bucket report-folder-hierarchy=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84-1 h_01HMTZ9VQ5HCKP7T3JQ2RHZV50=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84-1 h_01HETBAQVVR90NJC522WNAG190=impression-level-report the-source-of-the-report-data=%E6%95%B0%E6%8D%AE%E6%9D%A5%E6%BA%90 h_01HETBAQVV3KBEW4VV4RY9VRA2=%E6%95%B0%E6%8D%AE%E6%9D%A5%E6%BA%90 when-is-the-report-data-available::272621c9=%E6%95%B0%E6%8D%AE%E6%9D%A5%E6%BA%90 h_01HMTZ9VQ5YQKBQ779YWBWESDZ=%E6%95%B0%E6%8D%AE%E6%9D%A5%E6%BA%90 h_01HMTZ9VQ5ZST1M7JYKFC3DA62=how-to-subscribe-to-the-report::67646c99 h_01HETBAQVVHE80MH3SM3GX21V1=how-to-access-the-report-in-aws-the-bucket report-folder-hierarchy::26ec73c6=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84-2 h_01HMTZ9VQ5FFSA1XF7YSATM6WH=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84-2 data-sources::68e71455=data-sources-2 h_01HMTZ9VQ5SWTWTSNW5M9KJ1XN=data-sources-2 when-is-the-report-data-available::87d17fc2=data-flow::bde19643 how-to-subscribe-to-the-report::6569d202=data-flow::bde19643 h_01HMTZ9VQ6XVHDHBKV86F3Q9DJ=data-flow::bde19643 h_01HMTZ9VQ64AJQM861M6ENHVWC=data-flow::bde19643 h_01HMTZ9VQ60HMM6TXAPYSZG5CT=data-flow::bde19643 h_01HMTZ9VQ67ZEX3KM6CV32SNBD=how-to-access-the-report-in-your-bucket::b136ba80 report-folder-hierarchy::805d4d8=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84-3 h_01HMTZ9VQ68VRJRHXSNAE38A0E=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84-3 h_01HETBAQVV9PSDJNS76SNX522C=download-the-report-data-sample::8cbba4e3 the-report-data-sources::af31e5d1=data-sources-3 h_01HETBAQVWE2R75D034VCYMTR1=data-sources-3 when-are-the-report-versions-available::2f1bc55f=the-report-data-processing-flow h_01HETBAQVWZRBE84NV403BCZ9F=the-report-data-processing-flow h_01HETBAQVWQFCKHMT6PJNPXX7D=the-report-data-processing-flow h_01HETBAQVW54MD9Q09RNC673PE=how-to-subscribe-to-the-report::a624afde h_01HETBAQVWYDR81WS9Q9G20ZND=how-to-access-the-report-in-the-aws-bucket the-report-folder-hierarchy-in-aws::45c0d598=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84-4 h_01HETBAQVWXHK6DXFA90GJQWPV=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84-4" />

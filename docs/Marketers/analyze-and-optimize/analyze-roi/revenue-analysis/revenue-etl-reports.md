---
title: Revenue ETL reports
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
  edited_at: '2026-05-14T15:39:31Z'
  id: 16464765619985
  locale: en-us
  section: Revenue analysis
  section_id: 6551069075089
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/16464765619985-Revenue-ETL-reports
---
> **At a glance:** Learn about ROI360 revenue reports, their sources, how they are generated, when they are available, and how you can access them. Learn more about the fields and structure of the reports by downloading the data sample.

## Revenue ETL

With ROI360 Revenue ETL, your revenue data is sent via Data Locker to cloud storage for loading into your BI systems.

The following table shows the available revenue reports. **Note**: With the exception of the Legacy ad revenue [single version] reports, all reports require an ROI360 Advanced package subscription.

| Report | Integration type | Description | Data freshness |
| --- | --- | --- | --- |
| [Legacy ad revenue [single version]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level):<ul><li>Attributed ad revenue [single version x+1]</li><li>Organic ad revenue [single version x+1]</li><li>Retargeting ad revenue [single version x+1]</li></ul> | <ul><li>Impression-level (via SDK)</li><li>Device-level (via S2S API)</li><li>Impression-level (via SDK) with device-level (via S2S API)</li></ul> | <ul><li>Contains ad revenue data.</li><li>Single version (no further data updates).</li><li>If there are both API and SDK integrations, reports contain only API data.</li></ul> | <ul><li>Daily (Available on Day x+1) <Anchor target="_blank" href="/marketers/docs/roi360-guide-ad-revenue-attribution#data-freshness">Learn more</Anchor></li></ul> |
| [Ad revenue [versioned]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level):<ul><li>Attributed ad revenue [versioned]</li><li>Organic ad revenue [versioned]</li><li>Retargeting ad revenue [versioned]</li></ul> | <ul><li>Impression-level (via SDK)</li><li>Device-level (via S2S API)</li><li>Impression-level (via SDK) with device-level (via S2S API)</li></ul> | <ul><li>Contains the most up-to-date ad revenue data.</li><li><Anchor target="_blank" href="/marketers/docs/data-locker-for-marketers#version-folders">Versioned</Anchor></li></ul> | <ul><li>Intraday. <Anchor target="_blank" href="/marketers/docs/roi360-guide-ad-revenue-attribution#data-freshness">Learn more</Anchor></li><li>Data updates from 4 hours to 14 days after the ad impression.</li></ul> |
| [Ad revenue [SDK impression level]](/docs/revenue-etl-reports#impression-level-report) | <ul><li>Impression-level (via SDK)</li><li>Impression-level (via SDK) with device-level (via S2S API)</li></ul> | <ul><li>Contains ad revenue SDK data.</li><li>Provides maximum data freshness and granularity.</li></ul> | Hourly. <Anchor target="_blank" href="/marketers/docs/roi360-guide-ad-revenue-attribution#data-freshness">Learn more</Anchor> |
| [Transaction-level stores revenue](/docs/revenue-etl-reports#transactionlevel-stores-revenue-report) | ROI360 IAP and subscription revenue integration | <ul><li>Contains ROI360 validated in-app purchase and subscription raw data at the transaction level.</li><li>Provides maximum data freshness and data granularity.</li><li>Includes unique ROI360 monetization-related data and net revenue.</li></ul> | Hourly |
| [Device-level stores revenue [versioned]](/docs/revenue-etl-reports#devicelevel-stores-revenue-report) | ROI360 IAP and subscription revenue integration | <ul><li>Contains ROI360 validated in-app purchase and subscription raw data at the device level.</li><li>Includes unique ROI360 net revenue data.</li></ul> | Every 8 hours |

## Reports

Details about the different reports—how they work, how to subscribe to them, and how to access them—can be found in the sections that follow.

<div id="ad-revenue-single-version-report-device-level" />

<Accordion title="[Legacy] Ad revenue (single version)">

The report shows a single version of ad revenue data of one day aggregated to the device level. The report is available on day X+1 (X is the day of the revenue event occurrence).

**Note:** Separate reports provide the organic and retargeting revenue data. These reports are identical in structure and availability.

<span id="download-the-report-data-sample"></span>[Download the Ad revenue single version report data sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vSuZYSPuAWIG-MappxQDIT3sl8UmN6MLKP2SKsbREekVAvKSHuUAUAtUE6JapanANJbKsTzCOID8z7G/pub?output=xlsx).

#### Data sources

Depending on your ad revenue partner integration type, the report data can originate from either:

* **SDK**: Impression-level data payloads sent by the ROI360 Ad Revenue SDK connector.
* **S2S:** Device-level reports pulled by an API request from partners (mediation or monetization networks).

To learn how to set the integration type, see: Connect to ad revenue integrated partners.

#### Data flow

1. **Data ingestion:** The report can originate from the ad revenue SDK connector or S2S API request (see the section above).
2. **Data processing**: AppsFlyer ROI360 Ad Revenue performs the following:

   1. Data normalization,
   2. Attribution to the install source and data enrichment,
   3. Ad revenue events generation,
   4. Events are aggregated to the device level.

   **Note:** A report can have more than one device-level aggregation for the same device. This may happen because device-level aggregation is based on monetization-related dimensions such as monetization network, placement, and ad type. For example, if the app display ads in two different placements, revenue events from each placement are aggregated separately on the device level.
3. **Data delivery**: The device-level data is written to the single report version.

#### When is the report data available?

| Integration type | Version Day (X = revenue event occurrence day) | Version available at | The version includes revenue events occurring between |
| --- | --- | --- | --- |
| SDK | Day X+1 | 20:00 | 00:00 — 24:00 |
| SDK + S2S | Day X+1 | 17:00 | 00:00 — 24:00 |

#### How to subscribe to the report?

1. In AppsFlyer, from the side menu, select **Report** > **Data Locker**.
2. In the **Data Locker content** pane scroll down to the **ROI360 RevenueETL** tile.
3. Select **Attributed revenue [single version].**

**Note:** You can also select the same report for retargeting and organic  (Retargeting/Organic ad revenue [single version]).

#### How to access the report in your bucket?

The path to the report consists of the following folder hierarchy:

With the following format: `<bucket-name>/t=attributed_ad_revenue/dt=<dt=yyyy-mm-dd>/h=23/`

#### Report folder hierarchy

An example of the attributed ad revenue single version report folder hierarchy in the advertiser bucket:

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

**Legend:**

* **dt**: Date when the revenue events included in the report occurred.
* **t:** report type
* **h:** single version creation hour

</Accordion>

<div id="ad-revenue-versioned-report-device-level" />

<Accordion title="Ad revenue (versioned)">

The report shows multiple versions of revenue data of a single date. For example, the revenue occurring on June 21 is reported on June 21, June 22, June 23, June 24, June 28, and July 5.

The purpose of collecting multiple versions of the same day is to capture revenue calculation variations that arise from time-dependent conditions. For example impressions that had revenue value in real-time, may have a different value a day later.

**Note:** Separate reports provide the organic and retargeting revenue data. These reports are identical in structure and availability.

[Download the Ad revenue versioned report data sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vQek1x3rYnYQq3jctSz5hnWG_Nk_LQk2ixMTQFVMb8K6w-UmeNKvKOif3-nudAyIqp9tyuoq9R-FhVz/pub?output=csv).

#### Data sources

Depending on your partner integration type, the report data can originate from either:

* **SDK**: Impression-level data payloads sent by the ROI360 Ad Revenue SDK connector.
* **S2S:** Device-level reports pulled by an API request from partners (mediation or monetization networks).
* **S2S + SDK:** Payloads originating from both SDK and S2S.

To learn how to set the integration type, see: Connect to ad revenue integrated partners.

#### Data flow

1. **Data ingestion:** The report can either originate from the SDK or S2S API request (see the section above).
2. **Data processing:** AppsFlyer ROI360 Ad Revenue performs the following:

   1. Data normalization,
   2. Attribution to the install source and data enrichment,
   3. Ad revenue events generation,
   4. Events are aggregated to the device level.

   **Note:** A report can have more than one device-level aggregation for the same device. This may happen because device-level aggregation is based on monetization-related dimensions such as monetization network, placement, and ad type. For example, if the app display ads in two different placements, revenue events from each placement are aggregated separately on the device level.
3. **Data delivery**: Device-level data is written to multiple report versions according to a predetermined schedule (specified below).

#### When are the report versions available?

The table provided below outlines the generation schedules for both the S2S and SDK versions. Customers who benefit from ROI360 Ad Revenue Freshness to Accuracy will receive both versions, ensuring optimal accuracy and up-to-date information.

**Note:** Some S2S-originated versions may not be created. If the data from the partner(s) did not change since the last pull, a new version will NOT be generated.

| Integration type | Version Day (X = revenue event occurrence day) | Version available at | The version includes revenue events occurring between |
| --- | --- | --- | --- |
| SDK | Day X | 03:00-04:00 | 00:00 — 24:00 |
| SDK | Day X | 07:00-08:00 | 00:00 — 07:00 |
| SDK | Day X | 11:00-12:00 | 00:00 — 11:00 |
| SDK | Day X | 15:00-16:00 | 00:00 — 15:00 |
| SDK | Day X | 19:00-20:00 | 00:00 — 19:00 |
| SDK | Day X | 23:00-24:00 | 00:00 — 23:00 |
| SDK | Day X+1 | 04:00-05:00 | 00:00 — 24:00 |
| S2S | Day X+1 | 10:00-11:00 | 00:00 — 24:00 |
| S2S | Day X+1 | 16:00-17:00 | 00:00 — 24:00 |
| S2S | Day X+2 | 00:00-01:00 | 00:00 — 24:00 |
| S2S | Day X+2 | 13:00-14:00 | 00:00 — 24:00 |
| S2S | Day X+3 | 06:00-07:00 | 00:00 — 24:00 |
| S2S | Day X+7 | 08:00-09:00 | 00:00 — 24:00 |
| S2S | Day X+14 | 11:00-12:00 | 00:00 — 24:00 |
| SDK + S2S | All SDK and S2S versions above |  |  |

#### How to subscribe to the report?

1. In AppsFlyer, from the side menu, select **Report**
   > **Data Locker**.
2. In the **Data Locker content** pane scroll down to the **ROI360 RevenueETL** tile.
3. Select **Attributed Ad revenue [versioned].**

**Note:** You can also select the same report for retargeting and organic  (Retargeting/Organic ad revenue [versioned]).

#### How to access the report in your bucket?

The path to the report consists of the following folder hierarchy:

`<bucket-name>/t=attributed_ad_revenue_v2/dt=<dt=yyyy-mm-dd>/version=<9999999>/`

#### Report folder hierarchy

An example of a report tree in the advertiser bucket:

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

* **Legend:**
  * **t:** Report type
  * **dt**: Date when the revenue events included in the report occurred.
  * **version:** The version’s name is the epoch timestamp of the version creation date and time, e.g., **version=1685588879**.
* The origin of the version, whether S2S or SDK, can be learned from the version creation time. The first SDK versions originate from the SDK. The others are S2S.

| Integration type | Version Day (X = revenue event occurrence day) | Version available at | The version includes revenue events occurring between |
| --- | --- | --- | --- |
| SDK | Day X | 03:00-04:00 | 00:00 — 24:00 |
| SDK | Day X | 07:00-08:00 | 00:00 — 07:00 |
| SDK | Day X | 11:00-12:00 | 00:00 — 11:00 |
| SDK | Day X | 15:00-16:00 | 00:00 — 15:00 |
| SDK | Day X | 19:00-20:00 | 00:00 — 19:00 |
| SDK | Day X | 23:00-24:00 | 00:00 — 23:00 |
| SDK | Day X+1 | 04:00-05:00 | 00:00 — 24:00 |
| S2S | Day X+1 | 10:00-11:00 | 00:00 — 24:00 |
| S2S | Day X+1 | 16:00-17:00 | 00:00 — 24:00 |
| S2S | Day X+2 | 00:00-01:00 | 00:00 — 24:00 |
| S2S | Day X+2 | 13:00-14:00 | 00:00 — 24:00 |
| S2S | Day X+3 | 06:00-07:00 | 00:00 — 24:00 |
| S2S | Day X+7 | 08:00-09:00 | 00:00 — 24:00 |
| S2S | Day X+14 | 11:00-12:00 | 00:00 — 24:00 |

</Accordion>

<div id="impression-level-report" />

<Accordion title="Ad revenue (SDK impression level)">

The report shows impression-level data divided into folders by occurrence hour. Each folder **only contains impressions that occurred during that hour**.

[Download the Ad revenue impression level report data sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5zVxFGaCMNZMbCCYPae6f7MmbtelxrqXb-A5DBENuyTFCN4deRfICvbL0_dNeYVipojmAeUdrGbKI/pub?output=csv)

#### Data source

The report data originates from impression-level data sent by the ROI360 Ad Revenue SDK connector and requires an SDK-type integration.

To learn how to set the integration type, see: Connect to ad revenue integrated partners.

#### Data flow

1. **Data ingestion:** The report data originates from impression-level data sent by the ROI360 Ad Revenue SDK connector and requires an SDK-type integration.
2. **Data processing**: AppsFlyer ROI360 Ad Revenue performs the following:
   1. Data normalization,
   2. Attribution to the install source and data enrichment,
   3. Impression-level ad revenue event generation.
3. **Data delivery**: Impression events are written to files divided by folders according to occurrence hour. Each folder only contains impressions that occurred during that hour.

#### When is the report data available?

| Integration type | Version Day (X = revenue event occurrence day) | Version available at |
| --- | --- | --- |
| SDK | Day X | At the end of every reported hour |

#### How to subscribe to the report?

1. In AppsFlyer, from the side menu, select **Report** > **Data Locker**.
2. In the **Data Locker content** pane scroll down to the **ROI360 RevenueETL** tile.
3. Select **Ad revenue [SDK impression level].**

#### How to access the report in your bucket?

The path to the report consists of the following folder hierarchy:

`<bucket-name>/t=attributed_adrevenue_sdk_impression_level/dt=<dt=yyyy-mm-dd>/h=<hh>`

#### Report folder hierarchy

An example of a report tree in the advertiser bucket:

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

**Legend:**

* **t:** Report type
* **dt**: Date when the revenue events included in the report occurred.
* **h**: Hourly folder containing the CSV file with impressions that occurred during that specific hour.

</Accordion>

<div id="transactionlevel-stores-revenue-report" />

<Accordion title="Transaction-level stores revenue">

This report presents raw in-day data at the transaction level, divided into hourly folders containing only the transactions relevant for that hour.

[Download the transaction-level stores report data sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGlRSg_Xrp2EsqK2uaisjhlqeSuZsypqKqSSRGX3AQBwBLlNdG_5LOOKCM9f9gCcLguMQgQwT--Dz7/pub?output=csv)

#### Data sources

The report data originates from transactions collected via the ROI360 SDK Purchase connector and server-to-server stores notifications.

#### Data flow

1. The report data originates from transactions collected via the ROI360 SDK Purchase connector payloads or from S2S stores notifications.
2. AppsFlyer ROI360 VIAP/Subscriptions processes the data, attributes it, and creates transaction-level events and values.
3. The transaction-level events are written to the report divided into hourly folders.

#### When is the report data available?

| Version Day (X = revenue event occurrence day) | Version available at |
| --- | --- |
| Day X | At the end of every reported hour |

#### How to subscribe to the report?

1. In AppsFlyer, from the side menu, select **Report** > **Data Locker**.
2. In the **Data Locker content** pane scroll down to the **ROI360 RevenueETL** tile.
3. Select **Transaction-Level Stores Revenue report.**

#### How to access the report in your bucket?

The path to the report consists of the following folder hierarchy:

`<bucket-name>/t=stores_rawdata/dt=<dt=yyyy-mm-dd>/h=<hh>`

#### Report folder hierarchy

An example of a report tree in the advertiser bucket:

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

**Legend:**

* **t:** report type
* **dt**: Date when the revenue events included in the report occurred.
* **h**: Hourly folder containing the CSV file with transactions that occurred during that specific hour.

</Accordion>

<div id="devicelevel-stores-revenue-report" />

<Accordion title="Device-level stores revenue (versioned)">

The device-level store revenue report specifies in-app purchase and auto-renewable subscription events captured by ROI360 products. These events include unique ROI360 monetization-related dimensions. Customer-issued in-app events are not included in this report.

<span id="download-the-report-data-sample::8cbba4e3"></span>[Download the device-level stores revenue report data sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vSpomvcf2axYeSFcCh0kEx3ShYYRGVfF9WYZXG1UYBkeymeVfh8mcypAOpq2drqE3zhdmbcmrMtahsl/pub?output=csv)

#### Data sources

The report data originates from transactions collected via:

1. The ROI360 SDK Purchase connector.
2. The stores (for example, The App Store and Google Play store) via server-to-server notifications.

#### Data flow

1. The report data originates from transactions collected via the ROI360 SDK Purchase connector payloads or from S2S stores notifications.
2. AppsFlyer ROI360 VIAP/Subscriptions processes the data, attributes it, and creates in-app events.
3. The in-app events are aggregated to the device level and written to a report version every four hours.

#### When are the report versions available?

| Version Day (X = revenue event occurrence day) | Version available at | The version includes revenue events occurring between |
| --- | --- | --- |
| Day X | 04:00 - 05:00 | 00:00 — 04:00 |
| Day X | 12:00 - 13:00 | 00:00 — 12:00 |
| Day X | 20:00 - 21:00 | 00:00 — 20:00 |
| Day X+1 | 05:00 - 06:00 | 00:00 — 24:00 |

#### How to subscribe to the report?

1. In AppsFlyer, from the side menu, select **Report** > **Data Locker**.
2. In the **Data Locker content** pane scroll down to the **ROI360 RevenueETL** tile.
3. Select **Device-Level Stores Revenue report [versioned]**.

#### How to access the report in your bucket?

The path to the report consists of the following folder hierarchy:

`<bucket-name>/t=stores_devicedata/dt=<dt=yyyy-mm-dd>/version=<999999999>`

#### Report folder hierarchy

An example of a report tree in the advertiser bucket:

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

**Legend:**

* **t:** report type
* **dt**: Date when the revenue events included in the report occurred.
* **version**: The version’s name is the epoch timestamp of the version creation date and time, e.g., **version=1685588879**.

</Accordion>

<div data-zendesk-anchors="h_01HMBTDD8TASZ2NEBXP7CZ3Q81=revenue-etl h_01HME0BBF2M47M2AV437RYQ070=reports h_01HETBAQVVYW14END06HBPBQSN=ad-revenue-single-version-report-device-level h_01HETBAQVVZB87JNT0JVYSP80D=download-the-report-data-sample the-report-data-sources=data-sources h_01HETBAQVVSKVDM4J90A0WGFJW=data-sources the-report-data-flow=data-flow h_01HETBAQVV97R7G6F67RM6K62K=data-flow h_01HETBAQVVKDAWW2S98TG6682S=when-is-the-report-data-available h_01HETBAQVVFSDRW778VQSSE107=how-to-subscribe-to-the-report how-to-access-the-report-in-dl=how-to-access-the-report-in-your-bucket h_01HETBAQVV15T92VXRHG2CP2KJ=how-to-access-the-report-in-your-bucket the-report-folder-hierarchy-in-aws=report-folder-hierarchy h_01HETBAQVVA750VTE1ABSM2M47=report-folder-hierarchy h_01HETBAQVVCB2SYMW9876HPE7N=ad-revenue-versioned-report-device-level data-sources=data-sources-1 h_01HMTZ9VQ5WE6D7E5NEBYH71SZ=data-sources-1 data-flow=data-flow-1 h_01HMTZ9VQ5PS8G9JTQ2YXF1G7X=data-flow-1 h_01HETBAQVVP1M40KHB66AW545S=when-are-the-report-versions-available how-to-subscribe-to-the-report::cae4aa15=how-to-subscribe-to-the-report-1 h_01HMTZ9VQ5BBFNNE7Z8EP084CF=how-to-subscribe-to-the-report-1 how-to-access-the-report-in-your-bucket=how-to-access-the-report-in-your-bucket-2 h_01HMTZ9VQ5FGBC56AP4R49P4BX=how-to-access-the-report-in-your-bucket-2 report-folder-hierarchy=report-folder-hierarchy-2 h_01HMTZ9VQ5HCKP7T3JQ2RHZV50=report-folder-hierarchy-2 h_01HETBAQVVR90NJC522WNAG190=impression-level-report the-source-of-the-report-data=data-source h_01HETBAQVV3KBEW4VV4RY9VRA2=data-source data-flow::c7ffb834=data-flow-2 h_01HMTZ9VQ5J837PGG99S8ARAGV=data-flow-2 when-is-the-report-data-available::272621c9=when-is-the-report-data-available-1 h_01HMTZ9VQ5YQKBQ779YWBWESDZ=when-is-the-report-data-available-1 how-to-subscribe-to-the-report::67646c99=how-to-subscribe-to-the-report-2 h_01HMTZ9VQ5ZST1M7JYKFC3DA62=how-to-subscribe-to-the-report-2 how-to-access-the-report-in-aws-the-bucket=how-to-access-the-report-in-your-bucket-3 h_01HETBAQVVHE80MH3SM3GX21V1=how-to-access-the-report-in-your-bucket-3 report-folder-hierarchy::26ec73c6=report-folder-hierarchy-2 h_01HMTZ9VQ5FFSA1XF7YSATM6WH=report-folder-hierarchy-2 h_01HETBAQVWZKYBAG5E71KVB9PM=transactionlevel-stores-revenue-report data-sources::68e71455=data-sources-3 h_01HMTZ9VQ5SWTWTSNW5M9KJ1XN=data-sources-3 data-flow::bde19643=data-flow-4 h_01HMTZ9VQ6XVHDHBKV86F3Q9DJ=data-flow-4 when-is-the-report-data-available::87d17fc2=when-is-the-report-data-available-2 h_01HMTZ9VQ64AJQM861M6ENHVWC=when-is-the-report-data-available-2 how-to-subscribe-to-the-report::6569d202=how-to-subscribe-to-the-report-3 h_01HMTZ9VQ60HMM6TXAPYSZG5CT=how-to-subscribe-to-the-report-3 how-to-access-the-report-in-your-bucket::b136ba80=how-to-access-the-report-in-your-bucket-4 h_01HMTZ9VQ67ZEX3KM6CV32SNBD=how-to-access-the-report-in-your-bucket-4 report-folder-hierarchy::805d4d8=report-folder-hierarchy-3 h_01HMTZ9VQ68VRJRHXSNAE38A0E=report-folder-hierarchy-3 h_01HETBAQVVWAFEMK8ENWN7DYEY=devicelevel-stores-revenue-report h_01HETBAQVV9PSDJNS76SNX522C=download-the-report-data-sample::8cbba4e3 the-report-data-sources::af31e5d1=data-sources-3 h_01HETBAQVWE2R75D034VCYMTR1=data-sources-3 the-report-data-processing-flow=data-flow-4 h_01HETBAQVWZRBE84NV403BCZ9F=data-flow-4 when-are-the-report-versions-available::2f1bc55f=when-are-the-report-versions-available-1 h_01HETBAQVWQFCKHMT6PJNPXX7D=when-are-the-report-versions-available-1 how-to-subscribe-to-the-report::a624afde=how-to-subscribe-to-the-report-4 h_01HETBAQVW54MD9Q09RNC673PE=how-to-subscribe-to-the-report-4 how-to-access-the-report-in-the-aws-bucket=how-to-access-the-report-in-your-bucket-4 h_01HETBAQVWYDR81WS9Q9G20ZND=how-to-access-the-report-in-your-bucket-4 the-report-folder-hierarchy-in-aws::45c0d598=report-folder-hierarchy-4 h_01HETBAQVWXHK6DXFA90GJQWPV=report-folder-hierarchy-4" />

---
title: "Revenue ETL reports"
excerpt: "Learn about ROI360 revenue reports, their sources, how they are generated, when they are available, and how you can access them."
---
With ROI360 Revenue ETL, your revenue data is sent via Data Locker to cloud storage for loading into your BI systems.

> 📘 Note
>
> With the exception of the Legacy ad revenue [single version] reports, all reports require an ROI360 Advanced package subscription.

| Report | Integration type | Description | Data freshness |
| --- | --- | --- | --- |
| [Legacy ad revenue [single version]](https://support.appsflyer.com/hc/articles/16464765619985#ad-revenue-single-version-report-device-level):<br>- Attributed ad revenue [single version x+1]<br>- Organic ad revenue [single version x+1]<br>- Retargeting ad revenue [single version x+1] | - Impression-level (via SDK)<br>- Device-level (via S2S API)<br>- Impression-level (via SDK) with device-level (via S2S API) | - Contains ad revenue data.<br>- Single version (no further data updates).<br>- If there are both API and SDK integrations, reports contain only API data. | - Daily (Available on Day x+1) [Learn more](https://support.appsflyer.com/hc/articles/217490046#data-freshness) |
| [Ad revenue [versioned]](https://support.appsflyer.com/hc/articles/16464765619985#ad-revenue-single-version-report-device-level):<br>- Attributed ad revenue [versioned]<br>- Organic ad revenue [versioned]<br>- Retargeting ad revenue [versioned] | - Impression-level (via SDK)<br>- Device-level (via S2S API)<br>- Impression-level (via SDK) with device-level (via S2S API) | - Contains the most up-to-date ad revenue data.<br>- [Versioned](/docs/data-locker-for-marketers#version-folders) | - Intraday. [Learn more](https://support.appsflyer.com/hc/articles/217490046#data-freshness)<br>- Data updates from 4 hours to 14 days after the ad impression. |
| [Ad revenue [SDK impression level]](https://support.appsflyer.com/hc/articles/16464765619985#impression-level-report) | - Impression-level (via SDK)<br>- Impression-level (via SDK) with device-level (via S2S API) | - Contains ad revenue SDK data.<br>- Provides maximum data freshness and granularity. | Hourly. [Learn more](https://support.appsflyer.com/hc/articles/217490046#data-freshness) |
| [Transaction-level stores revenue](https://support.appsflyer.com/hc/articles/16464765619985#transactionlevel-stores-revenue-report) | ROI360 IAP and subscription revenue integration | - Contains ROI360 validated in-app purchase and subscription raw data at the transaction level.<br>- Provides maximum data freshness and data granularity.<br>- Includes unique ROI360 monetization-related data and net revenue. | Hourly |
| [Device-level stores revenue [versioned]](https://support.appsflyer.com/hc/articles/16464765619985#devicelevel-stores-revenue-report) | ROI360 IAP and subscription revenue integration | - Contains ROI360 validated in-app purchase and subscription raw data at the device level.<br>- Includes unique ROI360 net revenue data. | Every 8 hours |

## Reports

Details about the different reports—how they work, how to subscribe to them, and how to access them—can be found in the sections that follow.

### [Legacy] Ad revenue (single version)

The report shows a single version of ad revenue data of one day aggregated to the device level. The report is available on day X+1 (X is the day of the revenue event occurrence).

> 📘 Note
>
> Separate reports provide the organic and retargeting revenue data. These reports are identical in structure and availability.

[Download the Ad revenue single version report data sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vSuZYSPuAWIG-MappxQDIT3sl8UmN6MLKP2SKsbREekVAvKSHuUAUAtUE6JapanANJbKsTzCOID8z7G/pub?output=xlsx).

#### Data sources

Depending on your ad revenue partner integration type, the report data can originate from either:

- **SDK**: Impression-level data payloads sent by the ROI360 Ad Revenue SDK connector.
- **S2S:** Device-level reports pulled by an API request from partners (mediation or monetization networks).

To learn how to set the integration type, see: Connect to ad revenue integrated partners.

#### Data flow

1. **Data ingestion:** The report can originate from the ad revenue SDK connector or S2S API request (see the section above).
2. **Data processing**: AppsFlyer ROI360 Ad Revenue performs the following:
   1. Data normalization,
   2. Attribution to the install source and data enrichment,
   3. Ad revenue events generation,
   4. Events are aggregated to the device level.

> 📘 Note
>
> A report can have more than one device-level aggregation for the same device. This may happen because device-level aggregation is based on monetization-related dimensions such as monetization network, placement, and ad type. For example, if the app display ads in two different placements, revenue events from each placement are aggregated separately on the device level.

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

> 📘 Note
>
> You can also select the same report for retargeting and organic (Retargeting/Organic ad revenue [single version]).

#### How to access the report in your bucket?

The path to the report consists of the following folder hierarchy:

With the following format: `<bucket-name>/t=attributed_ad_revenue/dt=<dt=yyyy-mm-dd>/h=23/`

#### Report folder hierarchy

An example of the attributed ad revenue single version report folder hierarchy in the advertiser bucket:

```auto
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

- **dt**: Date when the revenue events included in the report occurred.
- **t:** report type
- **h:** single version creation hour

### Ad revenue (versioned)

The report shows multiple versions of revenue data of a single date. For example, the revenue occurring on June 21 is reported on June 21, June 22, June 23, June 24, June 28, and July 5.

The purpose of collecting multiple versions of the same day is to capture revenue calculation variations that arise from time-dependent conditions. For example impressions that had revenue value in real-time, may have a different value a day later.

> 📘 Note
>
> Separate reports provide the organic and retargeting revenue data. These reports are identical in structure and availability.

[Download the Ad revenue versioned report data sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vQek1x3rYnYQq3jctSz5hnWG_Nk_LQk2ixMTQFVMb8K6w-UmeNKvKOif3-nudAyIqp9tyuoq9R-FhVz/pub?output=csv).

#### Data sources

Depending on your partner integration type, the report data can originate from either:

- **SDK**: Impression-level data payloads sent by the ROI360 Ad Revenue SDK connector.
- **S2S:** Device-level reports pulled by an API request from partners (mediation or monetization networks).
- **S2S + SDK:** Payloads originating from both SDK and S2S.

To learn how to set the integration type, see: Connect to ad revenue integrated partners.

#### Data flow

1. **Data ingestion:** The report can either originate from the SDK or S2S API request (see the section above).
2. **Data processing:** AppsFlyer ROI360 Ad Revenue performs the following:
   1. Data normalization,
   2. Attribution to the install source and data enrichment,
   3. Ad revenue events generation,
   4. Events are aggregated to the device level.

> 📘 Note
>
> A report can have more than one device-level aggregation for the same device. This may happen because device-level aggregation is based on monetization-related dimensions such as monetization network, placement, and ad type. For example, if the app display ads in two different placements, revenue events from each placement are aggregated separately on the device level.

3. **Data delivery**: Device-level data is written to multiple report versions according to a predetermined schedule (specified below).

#### When are the report versions available?

The table provided below outlines the generation schedules for both the S2S and SDK versions. Customers who benefit from ROI360 Ad Revenue Freshness to Accuracy will receive both versions, ensuring optimal accuracy and up-to-date information.

> 📘 Note
>
> Some S2S-originated versions may not be created. If the data from the partner(s) did not change since the last pull, a new version will NOT be generated.

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
| SDK + S2S | All SDK and S2S versions above | | |

#### How to subscribe to the report?

1. In AppsFlyer, from the side menu, select **Report** > **Data Locker**.
2. In the **Data Locker content** pane scroll down to the **ROI360 RevenueETL** tile.
3. Select **Attributed Ad revenue [versioned].**

> 📘 Note
>
> You can also select the same report for retargeting and organic (Retargeting/Organic ad revenue [versioned]).

#### How to access the report in your bucket?

The path to the report consists of the following folder hierarchy:

`<bucket-name>/t=attributed_ad_revenue_v2/dt=<dt=yyyy-mm-dd>/version=<9999999>/`

#### Report folder hierarchy

An example of a report tree in the advertiser bucket:

```auto
Autobucket
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

- **Legend:**
  - **t:** Report type
  - **dt**: Date when the revenue events included in the report occurred.
  - **version**: The version’s name is the epoch timestamp of the version creation date and time, e.g., **version=1685588879**.
- The origin of the version, whether S2S or SDK, can be learned from the version creation time. The first SDK versions originate from the SDK. The others are S2S.

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

### Ad revenue (SDK impression level)

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

```auto
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

- **t:** Report type
- **dt**: Date when the revenue events included in the report occurred.
- **h**: Hourly folder containing the CSV file with impressions that occurred during that specific hour.

### Transaction-level stores revenue

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

```auto
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

- **t:** report type
- **dt**: Date when the revenue events included in the report occurred.
- **h**: Hourly folder containing the CSV file with transactions that occurred during that specific hour.

### Device-level stores revenue (versioned)

The device-level store revenue report specifies in-app purchase and auto-renewable subscription events captured by ROI360 products. These events include unique ROI360 monetization-related dimensions. Customer-issued in-app events are not included in this report.

[Download the device-level stores revenue report data sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vSpomvcf2axYeSFcCh0kEx3ShYYRGVfF9WYZXG1UYBkeymeVfh8mcypAOpq2drqE3zhdmbcmrMtahsl/pub?output=csv)

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

```auto
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

- **t:** report type
- **dt**: Date when the revenue events included in the report occurred.
- **version**: The version’s name is the epoch timestamp of the version creation date and time, e.g., **version=1685588879**.
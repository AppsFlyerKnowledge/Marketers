---
title: "ROI360 guide - ad revenue attribution"
excerpt: "Learn how to attribute ad revenue to complete your LTV performance view and determine ROI by matching user lifetime value to media spend campaigns."
---
Attribute ad revenue to complete the LTV (lifetime value) performance view.

![Attributes_ad_revenue.png](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)

## Ad revenue attribution

- Ads display in the app on banners, offer walls, interstitials, etc., and create ad revenue.
- Ad revenue, combined with in-app purchases and subscription revenue, provides you with the complete LTV picture of the user. By matching user LTV to the media spend campaign, you can determine ROI and analyze it on the platform.

**Attributed ad revenue data**:

- Is acquired from the mediation platforms or ad monetization networks via server APIs or by embedded reporting SDK in the app (including iOS 14).
- Is attributed to the media source that originally brought the user, for example:
  - User sees an ad from Network A and downloads your app.
  - Ad displays inside the app.
  - Ad revenue is attributed to Network A (responsible for user acquisition), regardless of who published the ad.
- Reporting granularity depends on the monetization network integration and ad revenue attribution type.

### Integration types for ad revenue attribution

Data accuracy and freshness depend on the ad revenue attribution integration type, as shown in the following table.

> 📘 Note
>
> SDK integration types require developer assistance to implement. S2S integration types require you to have the correct network credentials.

| Ad revenue attribution integration type | Description |
| --- | --- |
| [Aggregate level](/docs/roi360-guide-ad-revenue-attribution#h_01JYRKB8Q3D3W0FM75VH78XQTS) via S2S API | - AppsFlyer receives daily revenue, broken down by geo.<br />- The effective revenue per action (eRPA) is derived by dividing the revenue by the number of instances of a trigger event.<br />- The trigger events are either app open or specific in-app events set in the app.<br />- If you're using a mediation platform, make sure to disable ad revenue integrations for monetization partners mediated via the platform before enabling the ad revenue integration with the platform. Failure to do so results in duplicate data.<br />- Data is not available in raw data reports and cannot be shared with ad networks via postbacks or UA signals. |
| [Device-level](/docs/roi360-guide-ad-revenue-attribution#01ECF1PZ36R9W7A0X4WBR95JDS) via S2S API | - The mediation platform or monetization network reports the revenue by user at the device level. Not all networks support device-level granularity.<br />- This revenue is attributed to the media source that brought the user. Meaning AppsFlyer ad revenue attribution adheres to the attribution rules found in the platform, including retargeting attribution rules.<br />- If you're using a mediation platform, make sure to disable ad revenue integrations for monetization partners mediated via the platform before enabling the ad revenue integration with the platform. Failure to do so results in duplicate data.<br />- Device-level via S2S API includes 100% of ad revenue and offers the highest data accuracy among ad revenue integration types.<br />- Data is available in raw data reports and can be shared with ad networks only via [UA signals.](/docs/share-ad-revenue-data-with-partners)<br />- For Android: Make sure developers have enabled the collection of AppSet\_id, since some mediations may provide only this identifier. See developer instructions for [Collecting AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id). |
| Impression-level via SDK | - Impression-level refers to how AppsFlyer receives the data. Data may end up being reported at other levels of granularity (such as the device level).<br />- The mediation platform or monetization network reports the revenue by user at the impression level. Not all networks support impression-level granularity.<br />- This revenue is attributed to the media source that brought the user. Meaning AppsFlyer ad revenue attribution adheres to the attribution rules found in the platform, including retargeting attribution rules.<br />- If you're using a mediation platform, make sure to disable ad revenue integrations for monetization partners mediated via the platform before enabling the ad revenue integration with the platform. Failure to do so results in duplicate data.<br />- Impression-level via SDK has the best data freshness of all ad revenue integration types.<br />- Supports SKAN (SKAdNetwork).<br />- Impression-level via SDK is the integration type that must be used when you use a mediation platform that isn't included in the list of AppsFlyer integrated partners. In the Ad revenue SDK, for mediation\_network, the developer would need to choose customMediation.<br />- Data can be shared with ad networks only via [postbacks](/docs/share-ad-revenue-data-with-partners). |
| Impression-level (via SDK) with device-level (via S2S API) | - Allows impression-level data that arrives via SDK to be attributed and reported on Day X, and to be replaced by device-level data that arrives via API on Day 1 and onward. **Note**: For Android, data reported via SDK from unknown devices (without available device IDs) isn't replaced by data that arrives via API.<br />- Enables data freshness to accuracy. Meaning, you get the benefit of data freshness for Day X with the data accuracy for Days X+1 and on.<br />- Supports SKAN.<br />- Data can be shared with ad networks via both [postbacks and UA signals](/docs/share-ad-revenue-data-with-partners).<br />- For Android: Make sure developers have enabled the collection of AppSet\_id, since some mediations may provide only this identifier. See developer instructions for [Collecting AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id). |

## Implementation

The following sections describe the available types of ad revenue attribution, as well as the workflows and steps required for implementation and maintenance.

### Connect to ad revenue integrated partners

**Before you begin**:

- Request that the ad revenue integrated partner provide you with API credentials.

**To enable ad revenue integration with the ad revenue network**:

1. In AppsFlyer, from the side menu, select **Settings** > **Revenue Settings** > **Ad revenue**.
2. In Ad revenue integration, click **New ad revenue integration**.
3. Select an ad revenue partner and click **Next**.
   ![ad revenue 3.6(2).png](https://files.readme.io/8ccba7d0909c15e92507bc55c7bf2bf003e1a9431fb6bd1d32a0f41959f7a904-47792643579153.png)

   > 📘 Note
   >
   > If your mediation solution does not appear in the list of supported partners, select **Custom mediation** and integrate it via the [AppsFlyer ad revenue SDK API](https://dev.appsflyer.com/hc/docs/gs-ad-revenue).

4. Select the type of ad revenue data you want to receive. **Note**: Not all ad networks provide all the options listed below.
   - Attributed revenue. Meaning revenue based on the user acquisition source. Attributed revenue reports can be either:
     - [Aggregate level](/docs/roi360-guide-ad-revenue-attribution#h_01JYRKB8Q3D3W0FM75VH78XQTS) via S2S API.
       - Select the event on which to base the ad revenue. For example, if you choose the event af\_app\_opened, the total ad revenue is divided among all app-opened events, giving you the ad revenue per app open.
     - Device-level via S2S API.
       - **For Android:** Make sure that developers enable the collection of `app_set_id`, because some mediations may provide only this identifier. See developer instructions for [Collecting AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).
       - **Note**: If you're enabling the device-level ad revenue API for a mediation platform, you must disable the ad revenue integrations for the monetization networks it mediates. Failure to do so results in duplicate data.
     - Impression-level via SDK.
       - Tell your app developers to integrate the [AppsFlyer ad revenue SDK API](https://dev.appsflyer.com/hc/docs/gs-ad-revenue).
     - **Recommended:** Impression-level (via SDK) with device-level (via S2S API).
       - Tell your app developers to integrate the [AppsFlyer ad revenue SDK API](https://dev.appsflyer.com/hc/docs/gs-ad-revenue).
       - **For Android:** Make sure that developers enable the collection of `app_set_id`, because some mediations may provide only this identifier. See developer instructions for [Collecting AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).
       - **Note**: If you're using a mediation platform, make sure to disable ad revenue integrations for monetization partners mediated through the platform before enabling the ad revenue integration with the platform. Failure to do so results in duplicate data.
5. Complete the API credentials or login as required by the integrated partner. This is not relevant for SDK integrations.
6. Click **Save**.
7. Click **Test Connection**.
   - If a success message displays, you have completed the procedure.
   - If any other message displays, see the table [Ad revenue integration status and testing](/docs/roi360-guide-ad-revenue-attribution#01ECF1PZ32Z4C20NADJ2SF3EPC) and follow the recommended corrective action, then repeat the procedure.
8. AppsFlyer collects data from the partner multiple times per day. For more information, see [Data Freshness](/docs/roi360-guide-ad-revenue-attribution#01H8V10BKK6N5XJ6GHKC201E3Y).
9. [Optional] QA and compare the ad revenue data you see in AppsFlyer to the ad revenue data you see in your mediation partner and UA partner dashboards. [Learn more](/docs/compare-roi360-ad-revenue-data-with-partner-data)
10. [Optional] Share ad revenue data to your UA partners via [UA signals and ad revenue event postbacks](/docs/share-ad-revenue-data-with-partners).

> 📘 Note
>
> If you change from one integration type to another, the change takes effect at 12 AM UTC the following day.

### View, edit, and delete ad revenue integrated partners

![delete_edit_adi.png](https://files.readme.io/2d2153ec3248061dab4072e1d981e237f553e32824a68e392ae239778b307610-47792653636113.png)

**To view, edit, or delete ad revenue network integrations**:

1. In AppsFlyer, from the side menu, select **Settings** > **Revenue Settings** > **Ad revenue** and select your app.

A list of all your partner integrations displays, along with information about the product and integration type, integration status, and the ad revenue event names.
2. Hover over the integration and click **Edit** or **Delete** as needed.

### Deduplicate cross-referenced ad revenue

When an app uses two [mediation platforms](/docs/appsflyer-knowledge-base-glossary#mediation-network) with API integration types (aggregate-level or device-level), both associated with the same [monetization network](/docs/appsflyer-knowledge-base-glossary#monetization-network), partial duplication of ad revenue data may occur. In such cases, each mediation platform reports all the ad revenue generated by its associated monetization network, regardless of whether that revenue was generated while being mediated by only one of the platforms.

**To help avoid partial duplication of revenue data when two mediation platforms cross-reference each other**:

- If available, use impression-level integrations via SDK. Impression-level data reported this way isn't deduplicated. The SDK reports each impression once, so there's no overlap to remove.
- For integrations **via API**, deduplicate the ad revenue:
  1. In AppsFlyer, from the side menu, select **Settings** > **Revenue Settings** > **Ad revenue**.
  2. In **General Settings**, check the box **Deduplicate ad revenue when two mediation partners cross-reference each other**. **Note**: Don't check the box if the 2 mediation platforms mediate different ad formats. For example, when platform 1 shows Banner and Interstitial, and platform 2 shows AppOpen and Native ads.

  > 📘 Note
  >
  > The setting is always ignored for:
  > - **Impression-level (SDK) integrations** — all partners.
  > - **Device-level (API) integrations** - for AppLovin MAX or ironSource (Unity LevelPlay)
  >
  > These don't contain duplicated data in the first place, so there's nothing to deduplicate.

![dedup.png](https://files.readme.io/a739bc7e3557913bf6a67afa74a71dd72673d5b4e4d6bbe1d3ef872e46609422-47792653637265.png)

### Aggregate granularity using app open or in-app events

Aggregate granularity for ad revenue works as follows:

- The integrated network reports total daily revenue, broken down by geo.
- AppsFlyer derives the effective revenue per action (eRPA) by dividing the ad revenue with the number of instances of a trigger event.
- AppsFlyer creates a \_monetized event that includes the total eRPA for each attributed device. For example, ad\_matched\_monetized.
- Using eRPA, revenue is attributed to media sources.
- You can use one of the following event types:
  - **Unique monetization in-app event** requires modifications to the app.
  - **af\_app\_opened** event, which is available by default.
- Don't report ad revenue amounts in in-app events in parallel to an ad revenue integration. Doing so causes ad revenue to be duplicated in the dashboard because AppsFlyer gets the revenue data from the monetization network through integration.

#### Aggregate ad revenue using events

| Event method | How implemented | Considerations |
| --- | --- | --- |
| Unique monetization in-app event | - An in-app event is set at the time of ad display<br />- This provides a distinct count of user actions, which enables superior eRPA calculations<br />- This can be further refined by having a different in-app event for each monetization network. Doing so enables you to break the revenue down by monetization network<br /> <br /> See the table that follows for a full discussion. | - Requires the developer to modify the app<br />- Revenue can be broken down by monetization network in the Dashboard |
| af\_app\_opened event | - The af\_app\_opened event is sent by the Appsflyer SDK by default<br />- It is triggered by each user session | - No app modification required<br />- Quick to implement<br />- eRPA values are significantly distorted unless you show only one ad per session<br />- No breakdown of revenue by monetization network<br />- The event pertains to all users who open the app, and you have no indication of the user's willingness to watch ads |

#### Comparison of in-app event methods

| Method | Pros | Cons | Considerations |
| --- | --- | --- | --- |
| Use the same event for all networks. For example, ad\_watched. This automatically generates the ad\_watched\_monetized event containing the monetization details | Simplest to implement | No quality information, like the number of clicks and ad revenue per network | - Best suited if the main goal is to find sources/campaigns that get users with the greatest tendency to click on ads.<br />- It is not suited to comparing the performance of monetization networks. |
| **(Best practice)** Each network is allocated a unique event for ad watching. Example: ad\_watch\_admob,<br />ad\_watch\_vungle. | Full visibility and ability to compare the monetizing networks in the dashboard in addition to the raw data. | Ad revenue isn't accumulated under a single event. The number of events is equivalent to the number of networks | Enables comparison of monetizing networks in the dashboard. Ad revenue is separated by network using an in-app event per network. |

### Ad revenue integration status and testing

The operational status of ad revenue integration is available as follows:

- [Cost and ad revenue integration status dashboard](/docs/dashboard-cost-and-ad-revenue-status): Centralized list of partners for whom ad revenue integration is enabled for one or more apps in your account.
- **Test Connection button:** Available when you add or edit an ad revenue integration. Use it to check whether the integration is operational.

To verify that the integration is operational:

1. Click **Test Connection**.
2. A success message displays — **API key verified** (for API-based integrations) or **Authentication was successful** (for SDK integrations). If any other message appears, follow the corrective action guidance in the table below.

| Status | Meaning | Remarks/action required |
| --- | --- | --- |
| API key verified | The connection is live and can pull data. AppsFlyer collects data multiple times per day. For more information, see [Data Freshness](/docs/roi360-guide-ad-revenue-attribution#01H8V10BKK6N5XJ6GHKC201E3Y). | None |
| Authentication was successful | Valid ad revenue events were received from the SDK. | None |
| Invalid credentials | One or more of the provided credentials are incorrect. | Get the correct credentials from the ad revenue partner |
| Missing configuration details | One or more of the credential fields is incomplete | Retrieve the credentials in the ad revenue partner's dashboard or reach out to the partner and request the credentials. |
| No events found | No valid ad revenue events were received from the SDK recently. | Confirm the SDK integration is complete and that test events are being sent. You can verify event delivery in real time using the [Live Events viewer](/docs/testing-the-sdk-integration-for-marketers#view-live-events). |

> 📘 Note
>
> For SDK integrations, you can also verify that ad revenue events are recorded in real time using the [Live Events viewer](/docs/testing-the-sdk-integration-for-marketers#view-live-events). Note that it only displays events sent from registered test devices.

## Ad revenue data

Ad revenue data is available via AppsFlyer dashboards and raw data reports.

### Ad revenue aggregate data

Ad revenue shows the quality of users from different sources over time. As users continue to open the app and engage with ads, their LTV increases.

> 📘 Note
>
> There may be discrepancies between the ad revenue data in different dashboards and reports.

Ad revenue attribution is available as follows:

- LTV-based:
  - Dashboards being: Overview, events
  - LTV reports
  - Cohort dashboard and reports
  - Master API
- Activity-based:
  - Dashboard: Activity
  - Ad revenue raw data

#### Overview dashboard - aggregated performance report

In the Overview dashboard:

- Values, including revenue, are LTV. See [LTV vs. activity data](/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports).
- The **Revenue** column includes all revenue, including ad revenue and in-app purchases.
- Drill down into the advertising hierarchy (media source, campaign, ad set, geo) to view the **monetized** events in the report.

#### Events dashboard

In the Activity dashboard:

- Values, including revenue, are activity date-based. See [LTV vs. activity data](/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports).
- The **Average Actions per User** indicates users' tendency to engage with the ads presented in the app.

#### Examples

Three users install an app on December 31, 2017. They are attributed as follows:

- User A: Network A
- User B: Network B
- User C: Organic

The app is integrated with five different monetization platforms. Each platform uses a unique in-app event using the AppsFlyer SDK as follows:

- Meta Audience Network: fb\_ad\_view
- Chartboost: chartboost\_ad\_view
- Admob: admob\_ad\_view
- Applovin: applovin\_ad\_view
- IronSource: is\_ad\_view

After the install for a period of four days, the users are shown ads as follows:

| User | UA network | fb\_<br />ad\_view | chartboost\_<br />ad\_view | admob\_<br />ad\_view | applovin\_<br />ad\_view | is\_ad\_view | Total |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | Network A<br />2017-12-31 | 2018-01-01<br />$1 | 2018-01-02<br />$1 | 2018-01-03<br />$1 | 2018-01-04<br />$1 | | $4 |
| B | Network B<br />2017-12-31 | 2018-01-02<br />$1 | | 2018-01-04<br />$1 | | | $2 |
| C | Organic<br />2017-12-31 | 2018-01-01<br />$1 | | | | 2018-01-02<br />$1 | $2 |

Looking at the data, we can now summarize the revenue collected per user, per day (and per in-app event):

| User | 2018-01-01 | 2018-01-02 | 2018-01-03 | 2018-01-04 | Total LTV |
| --- | --- | --- | --- | --- | --- |
| A | $1 | $1 | $1 | $1 | $4 |
| B | | $1 | | $1 | $2 |
| C | $1 | $1 | | | $2 |
| Total | $2 | $3 | $1 | $2 | $8 |

**Understanding the Reports:**

As mentioned, ad revenue is tied to user LTV. Therefore, the time period you select in the Dashboard represents the cohort of installs for which the revenue is aggregated up until the current time and day. Let's examine a report with two different date selections:

Aggregate Report: Dates Selected: 2017-12-31-2018-01-05

| Network | LTV Revenue |
| --- | --- |
| Organic | $2 |
| Network A | $4 |
| Network B | $2 |
| Network C | $2 |

In this case, the cohort consists of users who installed the app between 2017-12-31 and the current day, 2018-01-05. All revenue generated by those users is tied back to the source of acquisition and reflected in the user's LTV.

### Ad revenue raw data

![PremiumFeature.jpg](https://files.readme.io/674e5d0c9efde9d12008bd705b3ba95f04e133fec3f39d4278612675123d4de4-360007173877.jpg)

Ad revenue raw data reports contain data from monetization networks with device-level or impression-level integration with AppsFlyer.

**Principles of ad revenue raw data**

- Data is aggregated by the number of unique impressions per user. Unique impressions are derived from the combination of the ad monetization network, ad unit, and placement.
- Impression-level raw data is:
  - Aggregated to the device-level and available in device-level reports.
  - Available as impression-level reports in Data Locker.

| Report | Export<br />data page | Pull API | Data Locker |
| --- | --- | --- | --- |
| Attributed ad revenue (non-organic) | **✓** | **✓** | **✓
*** |
| Organic ad revenue | **✓** | **✓** | **✓
*** |
| Retargeting ad revenue | **✓** | **✓** | **✓
*** |
| Impression-level raw data\*\* | **-** | **-** | **✓** |
| \* Versioned report is also available, updated multiple times per day. Non-versioned Data Locker reports are daily. For more information, see [Data Freshness](/docs/roi360-guide-ad-revenue-attribution#01H8V10BKK6N5XJ6GHKC201E3Y).<br />\*\* This refers to reports with impression-level in the name, not to impression-level ad revenue integration. ||||

**Data characteristics and fields**

The fields in ad revenue reports are populated:

- By the ad revenue event itself, and listed in the table that follows. These fields are divided into:
  - **Specific:** Fields specific to ad revenue. For example, impressions and placement. **Note**! The fields populated differ by monetization partner, as shown in the Fields by network table in this section.
  - **Context:** Fields having a similar meaning in other raw data reports. For example, event name, event value, and currency.
- As a result of attributing the event to the media source that brought the user. Meaning these fields are copied from the conversion event that brought the user. For example, media source and a campaign. These fields are not listed in the table that follows.

#### Fields populated by ad revenue

| api\_name | Field name | Field type | Description |
| --- | --- | --- | --- |
| event\_time | Event time | Context | The date the revenue is attributed to |
| event\_name | Event name | Context | Set to af\_ad\_revenue |
| event\_revenue | Event Revenue Currency | Context | - Amount of revenue using event revenue currency<br />- A zero value indicates impressions without revenue |
| event\_revenue\_currency | Event Currency | Context | Event revenue currency |
| event\_revenue\_XXX | Event Revenue XXX | Context | - In the export page: Revenue converted to the app-specific currency<br />- In Data Locker, always USD<br />- In Pull API, according to the currency of the Pull. |
| country | Country | Context | Install the country of the install conversion |
| ad\_unit | Ad unit | Specific | The value of this field is specific to the ad network. For server-to-server (S2S) integrations:<br />- **MAX:** Use the ad unit ID (for example, f53328a3c).<br />- **IronSource:** Use the ad unit type, such as banner, rewarded\_video, or interstitial.<br />For other networks, refer to the relevant partner integration guide or contact your network representative to confirm the required format. |
| segment | Segment | Specific | Ad placement name |
| monetization\_network | Monetization Network | Specific | Network is sending the ad |
| impressions | Impressions | Specific | Number of times that the user saw the ad |
| mediation\_network | Mediation Network | Specific | Mediation platform reporting the event to AppsFlyer |
| customer\_user\_id | Customer User ID | Context | Populated if available from the advertiser:<br />- For impression-level (SDK) integrations: Collected via `setCustomerUserId()` in the AppsFlyer SDK.<br />- For device-level (API) integrations: Collected from the mediation API (user ID or publisher user ID set via the mediation SDK).<br />- Not supported by Odeeo and Appodeal. |

#### Fields by network

| Display name | Admob | ironSource (LevelPlay) | AppLovin MAX | Appodeal | Fyber |
| --- | --- | --- | --- | --- | --- |
| Ad unit | **✓** | **✓** | **✓** | **✓** | **✓** |
| Segment | - | (1) | - | - | - |
| Placement | - | **✓** | **✓** | **✓** | **✓** |
| Monetization Network | **✓** | **✓** | - | **✓** | - |
| Impressions | **-** | - | **✓** | **✓** | - |
| Mediation Network | **-** | **✓** | **✓** | **✓** | - |
| (1) The advertiser needs to configure this in ironSource ||||||

[Ad revenue raw data sample report](https://docs.google.com/spreadsheets/d/e/2PACX-1vRm_1tevWFdzdj6JgdxYawLBtYAJj-ubDeY4g1QfbdSkd2-Adi18oemPMdd7m7cM2e3fzm7VH0w6lhD/pub?output=xlsx)

### Data freshness

Data freshness depends on the integration type and the reporting method.

For **S2S API integrations**, the earliest that data becomes available is:

- Dashboards and raw data reports (via Data Locker) starting at Day X+1, 12 PM UTC, approximately 4 times per day, every 6 hours. And days 2, 3, 7, and 14, once per day.

For **impression-level SDK integrations**, the earliest that data becomes available is:

- Dashboards (Activity and Cohort metrics): Continuous (15–60 minutes after event occurrence)
- Dashboards (LTV metrics) and raw data reports (via Data Locker), best-case scenario, starting at Day X from 5 AM UTC, updated approximately 6 times per day, every 4 hours.
- Impression level raw data reports (via Data Locker) at Day X from 1 AM UTC, updated hourly.

For **impression-level (via SDK) with device-level (via S2S API)**, you get data freshness for Day X with the data accuracy for Days X+1, as follows:

- For impression-level data that arrives via SDK:
  - Dashboards (Activity and Cohort metrics): Continuous (15–60 minutes after event occurrence)
  - Dashboards (LTV metrics) and raw data reports (via Data Locker), best-case scenario, starting at Day X from 5 AM UTC, updated approximately 6 times per day, every 4 hours.
  - Impression level raw data reports (via Data Locker) at Day X from 1 AM UTC, updated hourly.
- For device-level data that arrives via S2S API:
  - Dashboards and raw data reports (via Data Locker) starting at Day X+1, 12 PM UTC, approximately 4 times per day, every 6 hours. And days 2, 3, 7, and 14, once per day.

For **Raw Data Export and Pull API**, regardless of integration type or ROI360 package (Advanced or Standard), data for a given day becomes available the following day, at 6 PM UTC on Day X+1. Data is not updated after this time for these tools.

> 📘 Note
>
> Intra-day data availability in dashboards requires an ROI360 Advanced subscription.

#### Ad revenue Data Locker reports

| Name | Freshness | Report Sections |
| --- | --- | --- |
| _**Daily Ad Revenue (aggregated at device-level)**_ | The ad revenue for a particular day (day X) is reported on the following day (X+1), at 5 PM UTC.<br />For instance, Ad revenue from May 1st will be reported on May 2nd. | The report includes the Attributed, Organic, and Retargeting Ad Revenue sections. |
| _**Versioned Daily Ad Revenue Report (aggregated at device-level)**_ | The daily report consists of:<br />- In-day versions are created every 4 hours during the day of revenue (day X). In-day data is collected via the SDK API.<br />- Full-day versions created on days 1, 2, 3, 7, and 14, based on data originating from S2S API reports.<br />In other words, the version set of a daily report includes the following versions:<br />- 00:00 — 04:00 on day X.<br />- 00:00 — 08:00 on day X [SDK API]<br />- 00:00 — 12:00 on day X [SDK API]<br />- 00:00 — 24:00 on day X [ SDK API]<br />- 00:00 — 24:00 on day x+1 [S2S]<br />- 00:00 — 24:00 on day x+2 [S2S]<br />- 00:00 — 24:00 on day x+3 [S2S]<br />- 00:00 — 24:00 on day x+7 [S2S]<br />- 00:00 until 24:00 on day x+14 [S2S] | Each report version includes the Attributed, Organic, and Retargeting Ad Revenue sections. |
| _**Impression-level Ad Revenue report (impression-level)**_ | The impression-level ad revenue records are written to a separate file every hour. | |

**See also:**

- [Revenue ETL reports](/docs/revenue-etl-reports)

## Additional information

### Migrating from aggregate to device-level granularity

Keep the following in mind when migrating from aggregate to device-level granularity:

- Migrating does not impact historical ad revenue data. This data remains unchanged.
- Ad revenue data is pulled multiple times a day, starting at 03:00 UTC, using the granularity options selected then.
- Device-level granularity does not require you to define in-app events (like you do for aggregate-level reporting). You can continue sending these events, but they don't impact the device-level granularity reporting in AppsFlyer.

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| Limitations | Ad revenue events are not available to:<br />- Push API<br />- Retargeting dashboard<br />Device-level granularity limitations:<br />- The af\_ad\_revenue event is not available for cohorts in Pivot and Master API.<br />- The event is available in Cohort analytics.<br />- [Discrepancies can occur when implementing Meta ads **in-app** bid revenue.](/docs/applovin-max-ad-revenue-configuration#best-practice)<br />Counting unique users that trigger an af\_ad\_revenue event is not supported in AppsFlyer dashboards. |
| Device IDs supported | The following device IDs are supported for ad revenue attribution:<br />- AppsFlyer ID<br />- IDFA<br />- IDFV<br />- GAID<br />- AppSet ID\*<br />- Android ID<br />- IMEI<br />\* AppSet ID is supported for Applovin MAX and IronSource LevelPlay mediations only. See developer instructions for [Collecting AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id). |
| Ad network access | Can't access Cohort reports |
| Agency access | Agencies:<br />- Can't access the ad revenue configurations.<br />- Can see all the dashboards and data relevant to them. |
| Agency transparency | Not supported |
| Time zone | Ad revenue displays in AppsFlyer dashboards and reports in the UTC timezone only. Meaning, if data is reported at 2 PM UTC+2, in AppsFlyer, it displays as 2 PM UTC. processed daily.<br />This is because AppsFlyer needs to normalize the data collected from multiple sources and partners, most of which report their data in UTC. |
| Currency | In AppsFlyer:<br />- Dashboard displays the advertiser's app-specific currency.<br />- Raw data reports display the original currency and also convert it to the advertiser's app-specific currency. |
| Data type | Both organic and non-organic data are supported |
| Data freshness | [Ad revenue](/docs/roi360-guide-ad-revenue-attribution#01H8V10BKK6N5XJ6GHKC201E3Y) |
| Historical/retroactive data | - Data is pulled and available from the day of the integration. This means that historical data is not available before the integration date (day 0).<br />- Ad revenue data received via the S2S API for a specific day is updated on days 1, 2, 3, 7, and 14.<br />- Ad revenue data in the Overview, Cohort, and Activity dashboards, as well as data via the Master API and Cohort API, is updated retroactively; via raw data export and Pull API, it's not. If you have the advanced revenue package, data is also updated in Data Locker. |
| Account user access | Supported |
| SKAN | Supported by impression-level ad revenue SDK API. |
| Geo/country | In the Cohort dashboard, when geo is unknown (N/A), the N/A data doesn't display when aggregating by geo. |
| In-app event postbacks | - Postbacks to partners can be for "this partner only" or "all media sources, including organic." [Learn more](/docs/in-app-event-postback-configuration#options-for-sending-postbacks)<br />- Ad revenue event postbacks to ad networks only work with Impression-level via SDK and Impression-level (via SDK) with device-level (via S2S API) integrations. |
| CTV, PC, and console apps | - Android and iOS apps are supported.<br />- The Windows platform (UWP) is supported by Vungle.<br />- All other platforms aren't supported. |
| Customer User ID (CUID) | Supported for both SDK and device-level integrations. |
| Event count in dashboards | Event count is expected to be higher for intra-day (today's) data compared to historical periods. Historical data is aggregated into unique ad revenue impressions (same device × network × ad unit × placement), resulting in a lower event count. |

### List of ad revenue integrated partners

| Partner | Integration type available | | |
| --- | --- | --- | --- |
| | Aggregate level | Device level | Impression level |
| Admost | - | **✓** | **✓** |
| [AppLovin](/docs/applovin-campaign-configuration#ad-revenue-tab) | **✓** | - | - |
| [AppLovin Max](/docs/applovin-max-ad-revenue-configuration) | - | **✓** | **✓** |
| [Appodeal](/docs/appodeal-campaign-configuration) | - | **✓** | **✓** |
| [Bytedance Ads (China traffic)](/docs/bytedance-ads-china-campaign-configuration) | **✓** | - | - |
| Pangle (TikTok for Business) | **✓** | - | - |
| [Chartboost](/docs/chartboost-campaign-configuration#ad-revenue-tab) | **✓** | - | **✓** |
| Custom Mediation | - | - | **✓** |
| Google Ad Manager | **✓** | - | - |
| [Meta ads](/docs/meta-ads-integration-setup) | **✓** | - | - |
| [Fyber](/docs/fyber-campaign-configuration#ad-revenue-tab) | **✓** | **✓** | **✓** |
| [Google Admob](/docs/google-admob-ad-revenue-attribution-configuration) | **✓** | - | **✓** |
| Inmobi | **✓** | - | - |
| [ironSource](/docs/ironsource-campaign-configuration#ad-revenue-tab) (LevelPlay) | **✓** | **✓** | **✓** |
| Mintegral | **✓** | - | - |
| Odeeo | - | **✓** | - |
| Tapjoy | - | **✓** | - |
| Topon | **✓** | **✓** | **✓** |
| Topon Pte | - | - | **✓** |
| Tradplus | - | **✓** | **✓** |
| [Unity Ads](/docs/unity-ads-campaign-configuration) | **✓** | - | - |
| Unity Ads Mediation | - | - | **✓** |
| Voodoo | **✓** | - | - |
| [Vungle](/docs/vungle-campaign-configuration) | **✓** | - | - |
| Yandex | - | - | **✓** |
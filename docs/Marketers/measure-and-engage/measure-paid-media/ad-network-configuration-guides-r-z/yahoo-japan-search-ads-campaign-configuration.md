---
title: "Yahoo Japan Search Ads campaign configuration"
excerpt: "Learn how to configure the Yahoo Japan Search Ads integration with AppsFlyer for Android apps, including mapping in-app events and setting up agency permissions."
---
Yahoo Japan Search Ads is a self-reporting network (SRN) partner that combines advertising and analytics. 

On December 15, 2021, the legacy integration with Yahoo Japan Search Ads, _yahoojapansearch_int,_ was replaced with a new integration, _yjsearch_int_. Learn how to [start working with the new API](#integrating-with-the-new-api).

## Yahoo Japan Search Ads integration principles

AppsFlyer integration with Yahoo Japan Search Ads is relevant only to Android apps.

The integration leverages a link ID for conversion measurement and is based on pre-defined conversion events on Yahoo Japan Search Ads. You can map in-app events like subscriptions and purchases to these events. This enables conversion measurement and reporting between AppsFlyer and Yahoo Japan Search Ads.

### Comparing the legacy and new integration

Yahoo Japan Search Ads API feature support:

| Feature | Legacy (yahoojapansearch\_int) | New<br>(yjsearch\_int) |
| --- | --- | --- |
| Install conversion (click-through only) | Yes | Yes |
| In-app conversion | No | Yes |

### Integrating with the new API

**To enable the integration with the new API:**

1. In Yahoo Japan Search Ads Ads dashboard, [generate a link ID](https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102). You must select AppsFlyer as your MMP.
2. In AppsFlyer, [configure the integration with Yahoo Japan Search Ads](https://support.appsflyer.com/hc/articles/4412602890641#yahoo-japan-search-ads%E2%80%94integration-tab-sections).
3. [Map the in-app events](https://support.appsflyer.com/hc/articles/4412602890641#2) you want to measure, and [create new conversion analytics on the Campaign Management Tool](https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D) in Yahoo Japan Search Ads.

### Data sharing between AppsFlyer and Yahoo Japan Search Ads

Send postbacks to Yahoo Japan Search Ads relating to conversions and in-app events. In-app events are mapped to pre-defined conversion events used by Yahoo Japan Search Ads to optimize and update performance reports. You perform the mapping as part of the integration settings.

Consider the following mapping table in the context of AppsFlyer in-app events (your app) and Yahoo Japan Search Ads pre-defined event mapping.

| AppsFlyer in-app event | Yahoo Japan Search Ads app event type |
| --- | --- |
| af\_purchase | in\_app\_purchase |
| af\_app\_opened | session\_start |
| af\_search | view\_search\_results |
| af\_content\_view | view\_item |
| af\_list\_view | view\_item\_list |
| af\_add\_to\_cart | add\_to\_cart |
| af\_travel\_booking | ecommerce\_purchase |
| Any in-app event | If you have additional events, map them to the event custom. |

**Data provided to AppsFlyer by Yahoo Japan Search Ads**

When Yahoo Japan Search Ads claims a conversion, they provide us with the media source parameters listed in the table. These parameters populate analytics and raw data reports. The table that follows contains the mapping between Yahoo Japan Search Ads and AppsFlyer parameters.

#### Yahoo Japan Search Ads-AppsFlyer media source mapping

| Yahoo Japan Search Ads | AppsFlyer |
| --- | --- |
| timestamp | attributed\_touch\_time |
| campaign\_tracking\_id | campaign\_id |
| ad\_group\_tracking\_id | adset\_id |
| ad\_tracking\_id | ad\_id |
| keyword | keywords |
| match\_type | keyword\_match\_type |
| account\_id | network\_account\_id |

## Integration procedures

You can integrate with Yahoo Japan Search Ads using a single entity - directly as an advertiser or via an agency.

Complete the sections as follows:

- [Complete once—mandatory] [Advertiser Yahoo Japan Search Ads integration](https://support.appsflyer.com/hc/articles/4412602890641#yahoo-japan-search-ads%E2%80%94integration-tab-sections).
- [Optional per agency] [Agency integration](https://support.appsflyer.com/hc/articles/4412602890641#agency-integration).

### Yahoo Japan Search Ads—integration tab sections

| Step | Section | Description |
| --- | --- | --- |
| 1 | Activate partner | **Prerequisites:**<br>Get the Yahoo Japan Search Ads [link ID](https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102).<br>**To activate the Yahoo Japan Search Ads App Attribution integration:**<br>1. In AppsFlyer, from the side menu, select **Collaborate** \> **Partner Marketplace**.<br>2. Search for **Yahoo! Search Ads (Yahoo! JAPAN Sponsored Search) - New API**, and select it.<br>3. Verify that **yjsearch\_int** displays in the URL. If this is not the case, you have selected the wrong integrated partner. <br>4. In the **Integration** tab, turn on **Activate partner**.<br>   <br>   **Note:** The toggle must be on[(activated)](https://support.appsflyer.com/hc/articles/360000844778)for as long as you work with the partner.<br>5. In the Link ID field, paste the link ID mentioned in the prerequisites.<br>6. [Optional] Changes to default settings for install [click-through lookback](https://support.appsflyer.com/hc/articles/208338403) window. Yahoo Japan Search Ads default is 7 days. To minimize discrepancies [best practice], align with the Yahoo Japan Search Ads default.<br>7. Click **Save integration**.<br>8. In **Yahoo Japan Search Ads**, set the new conversion settings as "app\_first\_open". Learn more about the configuration in Yahoo Japan Search Ads. |
| 2 | Map AppsFlyer in-app events to Yahoo Japan Search Ads events | **To map the Yahoo Japan Search Ads pre-defined events to AppsFlyer in-app events:**<br><br>1. In AppsFlyer, from the side menu, select **Collaborate** > **Active integrations**.<br>2. Select **Yahoo! Search Ads (Yahoo! JAPAN Sponsored Search) - New API**.<br>3. Turn on **In-app events postback.**<br>4. Click **Add event** to add an app event to the list.<br>5. Complete the parameters required.<br>6. Click **Save integration.**<br>7. In **Yahoo Japan Search Ads**, set the new conversion settings to match the configured in-app events. Learn more about the configuration in Yahoo Japan Search Ads.<br><br>**Parameter Details:**<br>- **SDK event name:** The name of the event, as received by AppsFlyer from either the SDK integrated in your app, or from server-to-server events.<br>- **Partner event identifier:** The Yahoo Japan Search Ads pre-defined events. Suggested default mapping configurations are listed in the table in the previous section.<br>- **Sending option:** Select the sending option for the event:<br>  - **This partner only:** for events coming only from users attributed to Yahoo Japan Search Ads. <br>  - **All media sources, including organic:** Have your entire user base available to be reported to Yahoo Japan Search Ads.<br>- **Send revenue:**<br>  - **No values & no revenue:** Sends only the event itself without the event value.<br>  - **Values & no revenue:** Sends all the parameters excluding the revenue value.<br>  - **Values & revenue**: Sends all the event parameters, including the revenue value (if exists in the event).<br><br>Remarks:<br>- Event names are case-sensitive. To avoid discrepancies, make sure you use the correct event name for all media sources and app versions. |

### Agency integration

Agencies are able to run campaigns with Yahoo Japan Search Ads on your behalf.

#### Agency setup

| Procedure performed by | Procedure |
| --- | --- |
| Advertiser | 1. Verify that you have completed [advertiser Yahoo Japan Search Ads integration](https://support.appsflyer.com/hc/articles/4412602890641#yahoo-japan-search-ads%E2%80%94integration-tab-sections).<br>2. In AppsFlyer, from the side menu, select **Collaborate** > **Active integrations**.<br>3. Select an agency.<br>4. Go to the **Permissions tab**, and turn on **Agency permissions**. |
| Agency | 1. In AppsFlyer, go to **Configuration** \> **Active Integrations**.<br>2. Select **Yahoo! Search Ads (Yahoo! JAPAN Sponsored Search) - New API.**<br>3. Go to the **Integration tab**.<br>4. Verify that **Activate Partner** is **On.** If this is not the case, the advertiser must complete [Advertiser Yahoo Japan Search Ads integration.](https://support.appsflyer.com/hc/articles/4412602890641#yahoo-japan-search-ads%E2%80%94integration-tab-sections)<br>5. Verify that the remaining settings, like lookback windows and in-app event mapping, are correct. If necessary, ask the advertiser to make changes. <br>6. Enter your **Yahoo Japan Search Ads customer ID**. The ID is available in the [Campaign Management tool](https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=36745&o=default#:~:text=How%20to%20check%20Account%20ID). Note that only one customer ID can be connected. <br>7. Click **Save**. |

## Subsidiary procedures

### Get the app link ID

**To get the Campaign Manager link ID,** [see Yahoo Japan Search Ads documentation.](https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102)

### Create a new Yahoo Japan Search Ads pre-defined event

**To create a new pre-defined event,** refer to [Yahoo Japan Search Ads instructions](https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D).

### Yahoo Japan Search Ads discrepancies

See the following table to learn about discrepancies and how to minimize them.

**Differences in attribution models**

| Cause | Description | AppsFlyer tip |
| --- | --- | --- |
| Incorrect in-app event mapping | Mapping between AppsFlyer and Yahoo Japan Search Ads isn't correct. | - Verify the link ID, <br>- Verify AppsFlyer in-app events are correctly mapped to Yahoo Japan Search Ads events. |
---
title: "Yahoo Japan Search Ads campaign configuration"
excerpt: "Yahoo Japan Search Ads, a self-reporting network (SRN) partner that combines advertising and analytics."
x-zendesk:
  id: 4412602890641
  url: https://support.appsflyer.com/hc/en-us/articles/4412602890641-Yahoo-Japan-Search-Ads-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  position: 25
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Advertisers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2021-12-02T10:07:00Z'
  edited_at: '2026-09-15T10:48:52Z'
---
* On December 15, 2021, the legacy integration with Yahoo Japan Search Ads, *yahoojapansearch\_int,* was replaced with a new integration, *yjsearch\_int*. Learn how to [start working with the new API](/docs/yahoo-japan-search-ads-campaign-configuration#integrating-with-the-new-api).

![](https://cdn.appsflyer.com/marketplace/static/logo/yjsearch.png)

## Yahoo Japan Search Ads integration principles

AppsFlyer integration with Yahoo Japan Search Ads is relevant only to Android apps. 

The integration leverages a link ID for conversion measurement and is based on pre-defined conversion events on Yahoo Japan Search Ads. You can map in-app events like subscriptions and purchases to these events. This enables conversion measurement and reporting between AppsFlyer and Yahoo Japan Search Ads.

### Comparing the legacy and new integration

Yahoo Japan Search Ads API feature support:

| Feature | Legacy (yahoojapansearch\_int) | New<br /><br />(yjsearch\_int) |
| --- | --- | --- |
| Install conversion (click-through only) | Yes | Yes |
| In-app conversion | No | Yes |

### Integrating with the new API

**To enable the integration with the new API:**

1. In Yahoo Japan Search Ads Ads dashboard, [generate a link ID](https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102). You must select AppsFlyer as your MMP.
2. In AppsFlyer, [configure the integration with Yahoo Japan Search Ads](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads%E2%80%94integration-tab-sections).
3. [Map the in-app events](/docs/yahoo-japan-search-ads-campaign-configuration#2) you want to measure, and [create new conversion analytics on the Campaign Management Tool](https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D) in Yahoo Japan Search Ads.

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

* [Complete once—mandatory] [Advertiser Yahoo Japan Search Ads integration](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads%E2%80%94integration-tab-sections).
* [Optional per agency] [Agency integration](/docs/yahoo-japan-search-ads-campaign-configuration#agency-integration).

### Yahoo Japan Search Ads—integration tab sections

<table><thead><tr><th>Step</th><th>Section</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>Activate partner</td><td><p><strong>Prerequisites:</strong></p><p>Get the Yahoo Japan Search Ads <a href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&amp;aid=44102">link ID</a>.</p><p><strong>To activate the Yahoo Japan Search Ads App Attribution integration: </strong></p><ol><li>In AppsFlyer, from the side menu, select <strong>Collaborate</strong> &gt; <strong>Partner Integrations</strong> &gt; <strong>Partner Marketplace</strong>.</li><li>Search for <strong>Yahoo! Search Ads (Yahoo! JAPAN Sponsored Search) - New API</strong>, and select it.</li><li>Verify that <strong>yjsearch_int </strong>displays in the URL. If this is not the case, you have selected the wrong integrated partner. </li><li>In the <strong>Integration</strong> tab, turn on <strong>Activate partner</strong>.<br/><strong>Note:</strong><span><strong> </strong></span><span><span>The toggle must be on</span><span> </span></span><a href="./partner-activation-deactivation"><span><span>(activated)</span></span></a><span><span> </span><span>for as long as you work with the partner.</span></span></li><li>In the Link ID field, paste the link ID mentioned in the prerequisites.</li><li>[Optional] Changes to default settings for install <a href="./set-up-lookback-windows">click-through lookback</a> window. Yahoo Japan Search Ads default is 7 days. To minimize discrepancies [best practice], align with the Yahoo Japan Search Ads default.</li><li>Click <strong>Save integration</strong>.</li><li>In <strong>Yahoo Japan Search Ads</strong>, set the new conversion settings as "app_first_open". Learn more about the configuration in Yahoo Japan Search Ads.</li></ol></td></tr><tr><td>2</td><td>Map AppsFlyer in-app events to Yahoo Japan Search Ads events</td><td><p><strong>To map the Yahoo Japan Search Ads pre-defined events to AppsFlyer in-app events:</strong></p><ol><li>In AppsFlyer, from the side menu, select <strong>Collaborate</strong> &gt; <strong>Partner Integrations</strong> &gt; <strong>Active integrations</strong>.</li><li>Select <strong>Yahoo! Search Ads (Yahoo! JAPAN Sponsored Search) - New API</strong>.</li><li>Turn on <strong>In-app events postback.</strong></li><li>Click <strong>Add event</strong> to add an app event to the list.</li><li>Complete the parameters required. </li><li>Click <strong>Save integration.</strong></li><li>In <strong>Yahoo Japan Search Ads</strong>, set the new conversion settings to match the configured in-app events. Learn more about the configuration in Yahoo Japan Search Ads.</li></ol><figure><table><thead><tr><th>Parameter name</th><th>Description</th></tr></thead><tbody><tr><td>SDK event name</td><td>The name of the event, as received by AppsFlyer from either the SDK integrated in your app, or from server-to-server events.</td></tr><tr><td>Partner event identifier</td><td>The Yahoo Japan Search Ads pre-defined events. Suggested default mapping configurations are listed in the table in the previous section.</td></tr><tr><td>Sending option</td><td><p>Select the sending option for the event:</p><ul><li><strong>This partner only: </strong>for events coming only from users attributed to Yahoo Japan Search Ads. </li><li><strong>All media sources, including organic:</strong> Have your entire user base available to be reported to Yahoo Japan Search Ads.</li></ul></td></tr><tr><td>Send revenue</td><td><ul><li><strong>No values &amp; no revenue:</strong> Sends only the event itself without the event value.</li><li><strong>Values &amp; no revenue:</strong> Sends all the parameters excluding the revenue value.</li><li><strong>Values &amp; revenue</strong>: Sends all the event parameters, including the revenue value (if exists in the event).</li></ul></td></tr></tbody></table></figure><p>Remarks: </p><ul><li>Event names are case-sensitive. To avoid discrepancies, make sure you use the correct event name for all media sources and app versions.</li></ul></td></tr></tbody></table>

### Agency integration

Agencies are able to run campaigns with Yahoo Japan Search Ads on your behalf.

#### Agency setup

| Procedure performed by | Procedure |
| --- | --- |
| Advertiser | 1. Verify that you have completed [advertiser Yahoo Japan Search Ads integration](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads%E2%80%94integration-tab-sections).<br />2. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active integrations**.<br />3. Select an agency.<br />4. Go to the **Permissions tab**, and turn on **Agency permissions**. |
| Agency | 1. In AppsFlyer, go to **Collaborate** > **Partner Integrations** > **Active Integrations**.<br />2. Select **Yahoo! Search Ads (Yahoo! JAPAN Sponsored Search) - New API.**<br />3. Go to the **Integration tab**.<br />4. Verify that **Activate Partner** is **On.** If this is not the case, the advertiser must complete [Advertiser Yahoo Japan Search Ads integration.](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads%E2%80%94integration-tab-sections)<br />5. Verify that the remaining settings, like lookback windows and in-app event mapping, are correct. If necessary, ask the advertiser to make changes.<br />6. Enter your **Yahoo Japan Search Ads customer ID**. The ID is available in the [Campaign Management tool](https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=36745&o=default#:~:text=How%20to%20check%20Account%20ID). Note that only one customer ID can be connected.<br />7. Click **Save**. |

## Subsidiary procedures

### Get the app link ID

**To get the Campaign Manager link ID,** [see Yahoo Japan Search Ads documentation.](https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102)

### Create a new Yahoo Japan Search Ads pre-defined event

**To create a new pre-defined event,**refer to [Yahoo Japan Search Ads instructions](https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D).

### Yahoo Japan Search Ads discrepancies

See the following table to learn about discrepancies and how to minimize them.

**Differences in attribution models**

| Cause | Description | AppsFlyer tip |
| --- | --- | --- |
| Incorrect in-app event mapping | Mapping between AppsFlyer and Yahoo Japan Search Ads isn't correct. | * Verify the link ID,<br />* Verify AppsFlyer in-app events are correctly mapped to Yahoo Japan Search Ads events. |
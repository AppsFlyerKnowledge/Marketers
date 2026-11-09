---
title: Yahoo Japan Search Ads campaign configuration
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-12-02T10:07:00Z'
  edited_at: '2026-10-13T01:15:16Z'
  id: 4412602890641
  locale: ko
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ko/articles/4412602890641
---
> **At a glance:** Yahoo Japan Search Ads, a self-reporting network (SRN) partner that combines advertising and analytics.

* On December 15, 2021, the legacy integration with Yahoo Japan Search Ads, *yahoojapansearch\_int,* was replaced with a new integration, *yjsearch\_int*. Learn how to [start working with the new API](/docs/yahoo-japan-search-ads-campaign-configuration#integrating-with-the-new-api).

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yjsearch.png" width="121px" />

## Yahoo Japan Search Ads integration principles

AppsFlyer integration with Yahoo Japan Search Ads is relevant only to Android apps. 

The integration leverages a link ID for conversion measurement and is based on pre-defined conversion events on Yahoo Japan Search Ads. You can map in-app events like subscriptions and purchases to these events. This enables conversion measurement and reporting between AppsFlyer and Yahoo Japan Search Ads.

<div id="comparing-the-legacy-and-new-integration" />

<Accordion title="Comparing the legacy and new integration">

Yahoo Japan Search Ads API feature support:

| Feature | Legacy (yahoojapansearch\_int) | New<br /><br />(yjsearch\_int) |
| --- | --- | --- |
| Install conversion (click-through only) | Yes | Yes |
| In-app conversion | No | Yes |

</Accordion>

<div id="integrating-with-the-new-api" />

<Accordion title="Integrating with the new API">

**To enable the integration with the new API:**

1. In Yahoo Japan Search Ads Ads dashboard, <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">generate a link ID</Anchor>. You must select AppsFlyer as your MMP.
2. In AppsFlyer, [configure the integration with Yahoo Japan Search Ads](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).
3. [Map the in-app events](/docs/yahoo-japan-search-ads-campaign-configuration#2) you want to measure, and <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D">create new conversion analytics on the Campaign Management Tool</Anchor> in Yahoo Japan Search Ads.

</Accordion>

<div id="data-sharing-between-appsflyer-and-yahoo-japan-search-ads" />

<Accordion title="Data sharing between AppsFlyer and Yahoo Japan Search Ads">

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

</Accordion>

## Integration procedures

You can integrate with Yahoo Japan Search Ads using a single entity - directly as an advertiser or via an agency.  
Complete the sections as follows:

* [Complete once—mandatory] [Advertiser Yahoo Japan Search Ads integration](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).
* [Optional per agency] [Agency integration](/docs/yahoo-japan-search-ads-campaign-configuration#agency-integration).

<div id="yahoo-japan-search-ads-integration-tab-sections" />

<Accordion title="Yahoo Japan Search Ads—integration tab sections">

<table><thead><tr><th>Step</th><th>Section</th><th>Description</th></tr></thead><tbody><tr><td><span id="1"></span>1</td><td>Activate partner</td><td><p><strong>Prerequisites:</strong></p><p>Get the Yahoo Japan Search Ads <a href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&amp;aid=44102" target="_blank">link ID</a>.</p><p><strong>To activate the Yahoo Japan Search Ads App Attribution integration:</strong> </p><ol><li>In AppsFlyer, from the side menu, select <strong>Collaborate</strong> &gt; <strong>Partner Integrations</strong> &gt; <strong>Partner Marketplace</strong>.</li><li>Search for <strong>Yahoo! Search Ads (Yahoo! JAPAN Sponsored Search) - New API</strong>, and select it.</li><li>Verify that <strong>yjsearch_int</strong> displays in the URL. If this is not the case, you have selected the wrong integrated partner. </li><li>In the <strong>Integration</strong> tab, turn on <strong>Activate partner</strong>.<br/><strong>Note:</strong><span> </span><span><span>The toggle must be on</span><span> </span></span><a href="./partner-activation-deactivation" target="_blank"><span><span>(activated)</span></span></a><span><span> </span><span>for as long as you work with the partner.</span></span></li><li>In the Link ID field, paste the link ID mentioned in the prerequisites.</li><li>[Optional] Changes to default settings for install <a href="./set-up-lookback-windows" target="_blank">click-through lookback</a> window. Yahoo Japan Search Ads default is 7 days. To minimize discrepancies [best practice], align with the Yahoo Japan Search Ads default.</li><li>Click <strong>Save integration</strong>.</li><li>In <strong>Yahoo Japan Search Ads</strong>, set the new conversion settings as "app_first_open". Learn more about the configuration in Yahoo Japan Search Ads.</li></ol></td></tr><tr><td><span id="2"></span>2</td><td>Map AppsFlyer in-app events to Yahoo Japan Search Ads events</td><td><p><strong>To map the Yahoo Japan Search Ads pre-defined events to AppsFlyer in-app events:</strong></p><ol><li>In AppsFlyer, from the side menu, select <strong>Collaborate</strong> &gt; <strong>Partner Integrations</strong> &gt; <strong>Active integrations</strong>.</li><li>Select <strong>Yahoo! Search Ads (Yahoo! JAPAN Sponsored Search) - New API</strong>.</li><li>Turn on <strong>In-app events postback.</strong></li><li>Click <strong>Add event</strong> to add an app event to the list.</li><li>Complete the parameters required. </li><li>Click <strong>Save integration.</strong></li><li>In <strong>Yahoo Japan Search Ads</strong>, set the new conversion settings to match the configured in-app events. Learn more about the configuration in Yahoo Japan Search Ads.</li></ol><figure><table><thead><tr><th>Parameter name</th><th>Description</th></tr></thead><tbody><tr><td><span id="sdk-event-name"></span>SDK event name</td><td>The name of the event, as received by AppsFlyer from either the SDK integrated in your app, or from server-to-server events.</td></tr><tr><td><span id="partner-event-identifier"></span>Partner event identifier</td><td>The Yahoo Japan Search Ads pre-defined events. Suggested default mapping configurations are listed in the table in the previous section.</td></tr><tr><td><span id="sending-option"></span>Sending option</td><td><p>Select the sending option for the event:</p><ul><li><strong>This partner only:</strong> for events coming only from users attributed to Yahoo Japan Search Ads. </li><li><strong>All media sources, including organic:</strong> Have your entire user base available to be reported to Yahoo Japan Search Ads.</li></ul></td></tr><tr><td><span id="send-revenue"></span>Send revenue</td><td><ul><li><strong>No values &amp; no revenue:</strong> Sends only the event itself without the event value.</li><li><strong>Values &amp; no revenue:</strong> Sends all the parameters excluding the revenue value.</li><li><strong>Values &amp; revenue</strong>: Sends all the event parameters, including the revenue value (if exists in the event).</li></ul></td></tr></tbody></table></figure><p>Remarks: </p><ul><li>Event names are case-sensitive. To avoid discrepancies, make sure you use the correct event name for all media sources and app versions.</li></ul></td></tr></tbody></table>

</Accordion>

<div id="agency-integration" />

<Accordion title="Agency integration">

Agencies are able to run campaigns with Yahoo Japan Search Ads on your behalf.

#### Agency setup

| Procedure performed by | Procedure |
| --- | --- |
| Advertiser | <ol><li>Verify that you have completed [advertiser Yahoo Japan Search Ads integration](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).</li><li>In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active integrations**.</li><li>Select an agency.</li><li>Go to the **Permissions tab**, and turn on **Agency permissions**.</li></ol> |
| Agency | <ol><li>In AppsFlyer, go to **Collaborate** > **Partner Integrations** > **Active Integrations**.</li><li>Select **Yahoo! Search Ads (Yahoo! JAPAN Sponsored Search) - New API.**</li><li>Go to the **Integration tab**.</li><li>Verify that **Activate Partner** is **On.** If this is not the case, the advertiser must complete [Advertiser Yahoo Japan Search Ads integration.](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections)</li><li>Verify that the remaining settings, like lookback windows and in-app event mapping, are correct. If necessary, ask the advertiser to make changes.</li><li>Enter your **Yahoo Japan Search Ads customer ID**. The ID is available in the <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=36745&o=default#:~:text=How%20to%20check%20Account%20ID">Campaign Management tool</Anchor>. Note that only one customer ID can be connected.</li><li>Click **Save**.</li></ol> |

</Accordion>

## Subsidiary procedures

<div id="get-the-app-link-id" />

<Accordion title="Get the app link ID">

**To get the Campaign Manager link ID,** <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">see Yahoo Japan Search Ads documentation.</Anchor>

</Accordion>

<div id="create-a-new-yahoo-japan-search-ads-predefined-event" />

<Accordion title="Create a new Yahoo Japan Search Ads pre-defined event">

**To create a new pre-defined event,** refer to <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D">Yahoo Japan Search Ads instructions</Anchor>.

</Accordion>

<div id="yahoo-japan-search-ads-discrepancies" />

<Accordion title="Yahoo Japan Search Ads discrepancies">

See the following table to learn about discrepancies and how to minimize them.

**Differences in attribution models**

| Cause | Description | AppsFlyer tip |
| --- | --- | --- |
| Incorrect in-app event mapping | Mapping between AppsFlyer and Yahoo Japan Search Ads isn't correct. | <ul><li>Verify the link ID,</li><li>Verify AppsFlyer in-app events are correctly mapped to Yahoo Japan Search Ads events.</li></ul> |

</Accordion>

<div data-zendesk-anchors="h_01HH1RS8ZJSWTCDY5QBN3E041D=yahoo-japan-search-ads-integration-principles h_01HH1RS8ZJATXC84X8C74B95C8=comparing-the-legacy-and-new-integration h_01HH1RS8ZJWESR21H0BE7S3HV5=integrating-with-the-new-api h_01HH1RS8ZJM3EHGMKJF409QPTX=data-sharing-between-appsflyer-and-yahoo-japan-search-ads yahoo-japan-search-adsappsflyer-media-source-mapping=yahoo-japan-search-ads-appsflyer-media-source-mapping h_01HH1RS8ZM0ZEPJ7ZJYY286J2F=yahoo-japan-search-ads-appsflyer-media-source-mapping h_01HH1RS8ZMAFNAGWAZDWX5PJT4=integration-procedures yahoo-japan-search-ads%E2%80%94integration-tab-sections=yahoo-japan-search-ads-integration-tab-sections h_01HH1RS8ZMS287YR3K9CW7HN37=yahoo-japan-search-ads-integration-tab-sections h_01HH1RS8ZMGTJQB3ANAJB8MY52=agency-integration h_01HH1RS8ZMCBT0NJ5Z23ZAK6TV=agency-setup h_01HH1RS8ZMKHBA000CEX6KHQJK=subsidiary-procedures h_01HH1RS8ZMWPS69ASK452QAXAK=get-the-app-link-id h_01HH1RS8ZMXVXH745DP5Q8SZ3D=create-a-new-yahoo-japan-search-ads-predefined-event h_01HH1RS8ZM5SXTQDPJ5E9YEKPS=yahoo-japan-search-ads-discrepancies" />

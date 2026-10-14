---
title: "Petal Ads Global (formerly HUAWEI Ads global) campaign configuration"
excerpt: "Petal Ads Global, an AppsFlyer integrated partner, is a paid presentation service, which provided by Huawei for pan-ecosystem partners. It aims to help partners set up a communication bridge with Huawei device users so they can provide valuable information and quality services for users. Petal Ads Global provides slots for displaying mainstream ads such as native ads, rewarded video ads, banner ads, and interstitial ads to more than 570 million Huawei device users around the world."
x-zendesk:
  id: 360010605858
  url: https://support.appsflyer.com/hc/en-us/articles/360010605858-Petal-Ads-Global-formerly-HUAWEI-Ads-global-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  position: 21
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Agencies]
  labels: [integrated partner, Advertisers, Agencies, huawei, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2020-06-28T08:40:00Z'
  edited_at: '2026-09-09T12:36:05Z'
---
![huaweiadsglobal.png](https://files.readme.io/12f1351923768c1afc1ba0f16b267388a8c9b1ae7fc2d6d36b5d1d01381f1bbc-14151449726353.png)

## Petal Ads Global introduction

Petal Ads Global is integrated into several third-party apps and Huawei apps such as HUAWEI Browser, HUAWEI Video, HUAWEI Assistant, HUAWEI Reader, and HUAWEI Music, which are sub publishers of Petal Ads Global display network. Besides, AppGallery standard ad placements and App Gallery Search Ads support AppsFlyer attribution too.

## Setting up Petal Ads Global

Petal Ads Global requires to use **OAID** for attribution. Refer to [**our Android OAID Implementation in the SDK guide**](/docs/android-oaid-implementation-in-the-sdk) for fetching OAID on HUAWEI devices. In addition, Petal Ads Global highly recommends **HUAWEI App Gallery referrer attribution** for the apps in the store, to enable the huawei referrer attribution, please upgrade the Android SDK to 6.14.0 above.

| Traffic source | Channel value | Attribution methods | Note |
| --- | --- | --- | --- |
| Display Ads | huaweiadsglobal | ID-Matching (OAID or GAID), Probabilistic Modeling, Huawei Referrer | Click [here](/docs/android-oaid-implementation-in-the-sdk) to check OAID implementation guide in the Android SDK. Huawei referrer attribution requires Android SDK 6.14.0 |
| App Gallery | huaweiappgalleryglobal | ID-Matching (OAID or GAID), Huawei Referrer | Huawei referrer attribution requires Android SDK 6.14.0 |
| Petal Search | empty value | ID-Matching (OAID or GAID), Probabilistic Modeling | Click [here](/docs/android-oaid-implementation-in-the-sdk) to check OAID implementation guide in the Android SDK |

### Setting up the Petal Ads Global integration

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

<Accordion title="Integration tab">

The **Integration Tab** is divided into different sections:

#### Activate partner

To enable the configuration, [activate the partner](/docs/partner-activation-deactivation#activate-a-partner-integration).

This toggle must be turned on for as long as you work with the partner.

#### General settings

**Enable view-through attribution**

To attribute view-through installs from Petal Ads Global, turn this toggle on. The view-through lookback window slider is available in the **Attribution link** tab.

#### Default postbacks

Send automatic postbacks to Petal Ads Global following user installs from users attributed to Petal Ads Global only. Learn more about [default postbacks](/docs/set-up-an-integrated-partner#default-postbacks).

#### In-app events settings

Configure in-app event postbacks that are sent to Petal Ads Global.

**To configure in-app event postbacks:**

1. Turn on **In-app event postbacks**.
2. Set the [**In-app events postback window**](/docs/in-app-event-postback-configuration#in-app-event-postback-window).
3. To add an SDK Event to the list, click **Add event**.
4. Select the following parameters for each event:

| Parameter name | Description |
| --- | --- |
| **SDK event name** | The name of the event, as received by AppsFlyer either from the SDK or from server-to-server events.  <br />**Tip**: If you don't see the event you want in the list, activate this event on a device with a non-organic installation and recheck. |
| **Partner event identifier** | Enter the unique name or ID of each event as defined on Petal Ads Global. Select the most suitable pre-defined event out of 68 options for your SDK event, for example:<br /><br />* `browse` (browsing)<br />* `collection` (adding to favorites)<br />* `addToCart` (adding to shopping cart)<br />* `preOrder` (order placement)<br />* `register` (registration)<br />* `retain` (next-day retention)<br />* `paid` (payment occurred)<br />* `custom` (custom-type event) |
| **Sending option** | The postbacks can be sent only for the events performed by users attributed to Petal Ads Global. |
| **Send event data** | <ul><li>**No values & no revenue:** Send only the event itself without the event value.</li><li>**Values & no revenue:** Send all the parameters excluding the revenue value.</li><li>**Values & revenue**: Send all the event parameters, including the revenue value (if exists in the event).</li></ul> |

5. Click **Save Integration**.

</Accordion>

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[More about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).  
When generating the attribution link, select parameters from the list below and map them to the Petal Ads Global parameters name detailed in the table.

**Attribution link parameters**

| Parameter | Parameter name | Petal Ads Global macro | Description |
| --- | --- | --- | --- |
| Campaign | c  <br />af\_c\_id | \_\_CID\_\_ | Add it to compare different campaigns running with Petal Ads Global. |
| Adset | af\_adset  <br />af\_adset\_id | \_\_ADSETID\_\_ | Use to differentiate adsets. |
| Ad | af\_ad  <br />af\_ad\_id | \_\_ADID\_\_ | Use to differentiate between creatives within the adset. |
| Site and subsite ID | af\_siteid  <br />af\_subsiteid | \_\_SITEID\_\_ | Use to attribute installs to specific publishers.<br /><br />**Good practice!** If there are multiple publishers,<ul><li>Limit the number of site IDs in use.</li><li>Use the subsite ID parameter to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitation.</li></ul> |
| Channel | af\_channel | \_\_CHANNEL\_\_ | Use to differentiate the ad placements.<br /><br />huaweiadsglobal<br /><br />huaweiappgalleryglobal<br /><br />If blank value, then huawei search ads. |
| Subscriber parameters | af\_sub1, af\_sub2, af\_sub3, af\_sub4, and af\_sub5 |  | Use to insert additional useful values.<ul><li>Parameters are parsed and included in the raw data report.</li><li>Use them to perform data aggregation or filtering.</li></ul> |
| Ad type | af\_ad\_type | \_\_APP\_STATUS\_\_ | used to distinguish whether the app activated before.<ul><li>if the campaign is used to targeting the users who installed but never open, the parameter will be</li></ul>af\_ad\_type=installed<ul><li>if the campaign is used to targeting the users who never install the App, the parameter will be</li></ul>af\_ad\_type=notinstalled |

</Accordion>

<Accordion title="Cost tab">

Cost data is not supported by this partner.

</Accordion>

<Accordion title="Ad revenue tab">

Ad revenue data is not supported by this partner.

</Accordion>

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Petal Ads Global. Note that even if attribution is disabled for Petal Ads Global, the permissions tab is active and you can grant control to Petal Ads Global.

[Learn how to give permissions to Petal Ads Global.](/docs/set-up-an-integrated-partner#permissions-tab)

</Accordion>

## Configuring campaigns on Petal Ads Global

**To configure AppsFlyer attribution on Petal Ads Global, please click** [**here**](https://developer.huawei.com/consumer/en/doc/distribution/promotion/appsflyer-0000001122291488) **to learn more from Huawei Support Center.**

1. Obtain the impression and click tracking URLs in AppsFlyer.
2. Associate AppsFlyer in Petal Ads Global.
3. Set the data postback in AppsFlyer.
4. Create a conversion in Petal Ads Global.
5. Test the conversion in Petal Ads Global.
6. Create an ad task in Petal Ads Global.
7. [View the conversion data](https://developer.huawei.com/consumer/en/doc/distribution/promotion/tracking-shu-0000001139892541) in Petal Ads Global.

## Data discrepancies

**Note：** On the Petal Ads Global dashboard, the conversion data(eg. Install/Activations) has 2 data sources, the one is AppsFlyer the other one is HMS. When you want to compare the data, such as install, between AppsFlyer and Petal Ads Global dashboard, please select the 'Activations’ instead of 'Activations(HMS)' on the Huawei dashboard.

[![](https://files.readme.io/fd2878d20c78ebc87d8536225882c8613396178b920c570677edc668dabb810e-360015414918.png)](https://files.readme.io/fd2878d20c78ebc87d8536225882c8613396178b920c570677edc668dabb810e-360015414918.png)

#### Data reporting on Petal Ads Global and FAQs of data discrepancy

| Metric | Data source | FAQ | Description |
| --- | --- | --- | --- |
| Impressions | Huawei | Huawei impressions < AF impressions | AppsFlyer records all the impressions that Huawei sends to AF, while Petal Ads Global would do some data processing before displaying the impressions on the Petal Ads Global dashboard. |
| Clicks | Huawei | Huawei clicks < AF clicks | AppsFlyer records all the clicks that Huawei sends to AF, while Petal Ads Global would do some data processing before displaying the clicks on Petal Ads Global. |
| Downloads | Huawei | n/a | AF does not have this metric. |
| Activations | Activations are from AppsFlyer; Activations HMS is from Huawei | Huawei Activations > AF installs | Huawei’s activations are AF's installs. The data discrepancy results from different data reporting logics. <br /><br />For example, a user downloaded the app from AppGallery on Dec 24th, and first-opened the app on Dec 25th. In this case, AF will record the install on Dec 25th, while Petal Ads Global will record this activation on Dec 24th. |
| Day2 retention and other in-app events | For non-HMS ones, the data sources are AppsFlyer. | Huawei > AF | The data discrepancy results from different data reporting logics. <br /><br />Following the example above, the user registered in the app on Dec 26th, AF overview dashboard will display the registration data on Dec 25th, same as the install date. While Petal Ads Global promotion dashboard will display the registration on Dec 24th, the same as the download date. |
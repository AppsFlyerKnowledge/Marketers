---
title: Baidu mDSP Ads (Baiyi) campaign configuration
excerpt: >-
  Baidu mDSP Ads (Baiyi), an AppsFlyer ad network integrated partner, is an
  advertising solutions provider and part of Baidu, the dominant search engine
  in China with over 70% market share.
metadata:
  keywords:
    - Advertisers
    - Baidu mDSP
    - Baiyi
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-08-24T07:22:04Z'
  edited_at: '2026-09-15T11:04:35Z'
  id: 115004330446
  locale: en-us
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115004330446-Baidu-mDSP-Ads-Baiyi-campaign-configuration
---
## Setting up Baidu mDSO Ads (Baiyi)

1. In AppsFlyer, from the side menu, select**Collaborate> Partner Integrations** > **Partner Marketplace**.
2. Search for the partner and select it. You’re directed to the integration setup page.

The Baidu mDSP Ads (Baiyi) configuration window includes 2 active tabs: Integration and Attribution link. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partner

On the **first visit**, you must toggle ON the ***Activate Partner*** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

Default Postbacks

AppsFlyer can send automatic postbacks to Baidu mDSP Ads (Baiyi) following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

![baidu-mdsp-default-postbacks.png](https://files.readme.io/fdde731527468b9837efa2230c5416f3393024b8c4eec8b44339086a2f31b984-360002069005.png)

### In-app events settings

In this section, you can map your AppsFlyer events with Baidu mDSP Ads (Baiyi) via postbacks.

![baidu-mdsp-in-app-events.png](https://files.readme.io/fa515fac11e82be11bb55bb9b198ac63681ecdb713f0f6537f4ca7bf0c60e5b1-360002069085.png)

1. Toggle In-App Event Postbacks to ON.
2. Click **Add Event** to add an SDK Event to the list.
3. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Baidu mDSP Ads (Baiyi) 's side.  <br />Obtain the corresponding Event ID from Baidu mDSP Ads (Baiyi) and set in the text field. |
| **Send Revenue** | **When unchecked** - AppsFlyer sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - AppsFlyer sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Baidu mDSP Ads (Baiyi) for attributing Baidu mDSP Ads (Baiyi)'s campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Baidu mDSP Ads (Baiyi).  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Baidu mDSP Ads (Baiyi) campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Baidu mDSP Ads (Baiyi).  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about[**AppsFlyer Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window can be attributed to Baidu mDSP Ads (Baiyi).

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

![baidu-mdsp-click-through.png](https://files.readme.io/19f6616cc1e62ec8888a72625ce936acdb6e8e63e4a4cd4273cdc99fd2297a93-360002075089.png)

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Baidu mDSP Ads (Baiyi) to be activated when leads click on a corresponding ad.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost integration is not available for Baidu mDSP Ads (Baiyi).

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue integration is not available for Baidu mDSP Ads (Baiyi).

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions configuration is not available for Baidu mDSP Ads (Baiyi).

</Accordion>

## Create conversion rule at Baidu mDSP ads

Log in to Baidu mDSP Ads at http://baiyi.baidu.com/ and go to **Tool** >> **Apps**:

![mDSP_4.png](https://files.readme.io/90f99229f6bffe9b9edbf0469f9b4e66ca9c5c55184eb542e250ef6a9bd76aee-115014006086.png)

Click **Create New App**.

![mDSP_5.png](https://files.readme.io/c034e3238fbd6021fefc44ff8b1cf8b4d39c3f9043b02074c3bdccce2747ac48-115014006106.png)

Enter all the relevant information in the fields.

Add the AppsFlyer **Attribution Link in the box of Feedback URL**:

![mDSP_6.png](https://files.readme.io/6692275131ee49b62febcb558457f7f1a1fbd167f3d3f61d976e1cb248a61388-115014006906.png)

***NOTE***: For iOS Apps, add the app by entering the **Appid**. For Android Apps, add the app in two ways:  
1. Connecting with the App that you have uploaded to Baidu Developer Platform ([http://app.baidu.com/](http://app.baidu.com/)), or  
2. Entering the APK download page, or upload the APK there.

Then click submit button at the end of the page.

**2. Create App Promotion Ads at Baidu mDSP Ads**.

Click **Campaign Management** >> **Create New Campaign**:

![mDSP_7.png](https://files.readme.io/aab8866a1969e403247c97018aae1d65d456ce4e261412035ef91a1862f509b9-115014006926.png)

In section **2. Set Up Ad Unit** >> Process to **Objectives**, choose App Install >> Complete other related information and submit the Ad campaign for verification:

![mDSP_8.png](https://files.readme.io/da064e6811b4c749a20757d711186dc705070629887cdf2e7b514cc17274af75-115014006946.png)

<div data-zendesk-anchors="h_01HKW6TN4YBTMR1ZDH77D7SK7N=setting-up-baidu-mdso-ads-baiyi h_01HKW6TN4YM927W1VAKNWFQ0SJ=integration-tab h_01HKW6TN4Y4EXABZTJ2VE4QRTK=activate-partner inapp-events-settings=in-app-events-settings h_01HKW6TN4YYDKNGCSJB4MARK52=in-app-events-settings h_01HKW6TN4Y2D2K419172AZJXR6=attribution-link-tab h_01HKW6TN4YQTMGSMPGR01FR658=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW6TN4Y9ZP7SXMTD0XGNPGV=click-through-attribution h_01HKW6TN4Y5A1PT6RCVCFYRG9Q=click-attribution-link h_01HKW6TN4Z02V726B7379TMBC0=cost-tab h_01HKW6TN4Z01YZWHMGF5N1KC50=ad-revenue-tab h_01HKW6TN4Z3KCEFDW9YA2A2BZV=permissions-tab h_01HKW6TN4ZWEA7683C8MFAT4AY=create-conversion-rule-at-baidu-mdsp-ads" />

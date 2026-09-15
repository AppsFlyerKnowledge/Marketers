---
title: "ByteDance Ads China—campaign configuration"
excerpt: "Learn how to configure mobile attribution, view-through tracking, cost API, and ad revenue integration for ByteDance Ads China (Ocean Engine) in AppsFlyer."
---
**At a glance:** ByteDance Ads China (Ocean Engine), an AppsFlyer integrated partner, is an Internet technology company operating several machine learning-enabled content platforms.

> 📘 **Note**
>
> #### Note
>
> If you want to promote your Android Apps with ByteDance Ads China, you are required to send your OAID to AppsFlyer SDK according to the instructions in the [AppsFlyer SDK Integration - Android](/docs/sdk-integration-overview). Google Play service is blocked in China, OAID is the most popular Android Device ID for ad attribution.


In addition to click-based mobile attribution, ByteDance Ads China also offers view-through attribution, which you can record with AppsFlyer.

To configure your campaigns with ByteDance Ads China, follow the steps below.

## Setting up ByteDance Ads China

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

Tip

> 📘 **Note**
>
> * The [General Settings](/docs/set-up-an-integrated-partner#d-general%20settings) step in the Integration tab is **mandatory** for all partners.
> * All the rest of the steps are either descriptive or **optional**.


## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partners

On the **first visit** here, you must toggle ON the ***Activate Partner*** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, click [here](/docs/partner-activation-deactivation).

General Settings

**Enable View-Through attribution**

[![](https://support.appsflyer.com/hc/article_attachments/50612201111697)](https://support.appsflyer.com/hc/article_attachments/50612201111697)

Toggle this to **ON** if you want to attribute view-through installs from ByteDance Ads China. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

AppsFlyer can send automatic postbacks to ByteDance Ads China following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

![bytedance-default-postbacks.png](https://files.readme.io/5f3cb637fb9ff652533fcfd9c02ea8dc1768e0e1c1686a180ea18c0d2e09309f-50612201121425.png)

### In-app events settings

In this section, you can map your AppsFlyer events with ByteDance Ads China via postbacks.

1. Turn In-App Event Postbacks on.
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner.
3. Click **Add Event** to add an SDK Event to the list.
4. Complete the following parameters:



| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.  <br />**Tip**: Don't see the event you are looking for?<br /><br />* Make sure to activate the event on a device with a non-organic installation and recheck.<br />* Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br /><br />* **Text field:** Get the corresponding event ID from the partner.<br />* **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br />* **As is**: Send the events as they are, without mapping the event name. |
| **for users from** | Select the sending option for the event:<br /><br />* **This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner.<br />* **All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, the user who performed it came from any media source. |
| **including** | Select which event data to share with the partner in the postback:<br /><br />* **No values & no revenue**: Send just the event itself without any parameters (values or revenue).<br />* **Values & no revenue**: Send all the parameters **excluding** the revenue value.<br />* **Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event). |



## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters)**.**

**To generate an attribution link,**follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

### Click attribution link

Once you have generated the attribution link, complete the campaign setup process on the ByteDance Ads China site.

**1. Create Conversion Tracking in Ocean Engine.**

Log in to Ocean Engine ([https://ad.oceanengine.com/](https://ad.oceanengine.com/)) > **Library** > **Conversion Tracking**.

![OE_dashboard_1.png](https://files.readme.io/fda140ac7e3023033880b04ed500a675ae78187e4eb694ee200922b729ab119f-50612185108497.png)

Click on **Tracking application** and create a **New Application Transformation**.

![OE_dashboard_2.png](https://files.readme.io/dbf0c13c23d21d08c195a4ab747e5de0986cb01f5ebde98f6c701ce731480958-50612185109009.png)

Click the **API** method.

![OE_dashboard3.png](https://files.readme.io/70e7f6ca01c532fafb8f2ab7d31d6de51494f11749329c1c1333d1da6f28f284-50612185110417.png)

In the Monitoring link part, enter AppsFlyer click attribution link and/or impression attribution link.

![dashboard4.png](https://files.readme.io/d36ec92a03062fc7ee169bb1ff3863722343577f3ee2b12779065b3e52731348-50612201124369.png)

**2. Finish the Attribution Test Following the Instructions on the Website**.

**3. Create an Ad Campaign with the Newly Created Conversion**.

Go to **New Ad** >> **Set Budget and Bid** select the conversion you created for this app.

## Cost tab

AppsFlyer gets cost details by API. Note that AppsFlyer doesn't support the ad-level cost data for ByteDance, except for campaigns running on the v1.0 ByteDance system.

### API dimensions supported



| Geo | Media source | Campaign | Adset | Ad | Other |
| --- | --- | --- | --- | --- | --- |
| Yes | - | Yes | Yes | No<br /><br />(Ads are only supported for v1.0 ByteDance campaigns) | - |



**To enable ByteDance Ads China cost API**:

1. In the integrated partner Cost tab, enable ***Get****Cost****Data***.
2. Log in to ByteDance Ads China.
3. Click ***Save****Cost***.
   * You have successfully completed the procedure. API is active. AppsFlyer collects data from the partner 6 times a day, on average once every four hours.
   * The cost tab shows the status of your cost integration and the last time AppsFlyer managed to pull matching cost data.

## Ad revenue tab

This section is relevant if you are acting as a publisher, displaying ads of the partner to your users. As such, you would certainly like to measure the engagement of your users acquired from different sources, to find the most profitable sources for you.

**To enable the ad revenue API**:

* Follow [these integration instructions](/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners).

## Permissions tab

In this tab, you can select the permissions to grant ByteDance Ads China, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for ByteDance Ads China, the permissions tab is active and you can grant control to ByteDance Ads China.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -*only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*****a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).
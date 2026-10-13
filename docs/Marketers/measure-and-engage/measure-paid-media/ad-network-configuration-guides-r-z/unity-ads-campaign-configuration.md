---
title: "Unity Ads campaign configuration"
excerpt: "Configure Unity Ads campaigns in AppsFlyer to measure mobile attribution, cost, ad revenue, and view-through attribution for iOS and Android."
---
**At a glance:** Unity Ads, an AppsFlyer ad network integrated partner, is a video ad network for iOS and Android. In addition to click-based mobile attribution, Unity Ads offers cost, ad revenue, and view-through attribution, which can be recorded in AppsFlyer.

To configure your campaigns with Unity Ads, follow the steps below.

## Setting up Unity Ads

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

## Integration tab

### Activate partners

On the first visit, you will need to turn on the **Activate partner** toggle to setup the integration. The toggle must remain on for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### General settings

**Sending Device ID (Advertising ID) to Unity**

At the top of the Integration tab, there's a note saying that Unity Ads requires sending them the device ID for every install—this is done automatically, no need to do anything on your end.

[![Unity_msc_new_2.png](https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png)](https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png)

**Unity Ads Game ID**

Unity Ads requires connecting with AppsFlyer via a unique game ID. If you don't know yours, you can obtain it directly from Unity Ads or you can find it, after uploading the game, under **Apps** > **Campaigns**, as shown in the screenshot below.

[![](https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png)](https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png)

The Unity Ads Platform maps one app to a single Unity Ads Game ID, per account level (advertisers and agencies will have different Game IDs for the same app). Multiple accounts on the Unity Ads Platform can't run the same app with different Game IDs.

**Enable View-Through attribution**

Turn on this option to attribute view-through installs from Unity Ads. The view-through lookback slider is available on the attribution link tab (described below).

![Unity_ads_msc_new_3.png](https://files.readme.io/fab459ace7e8f1354d3bbfbca8ddefcd11376b7426a8e361abfab1b42b623880-360001875405.png)

### Default postbacks

![Screen_Shot_2022-07-28_at_13.07.25.png](https://files.readme.io/a571ddc49e490373b34144e34626a18c6c18908cec3345cd7ac70c49aa855c05-7975491293329.png)

Send automatic postbacks to Unity Ads following user installs. Use this section to define the source of the users that allow sending these postbacks:

* **This partner only**: for events coming only from users attributed to Unity Ads.
* **All media sources including organic**: to have your entire user base available to be reported to Unity Ads.

> 📘 **Note**
>
> As an all-installs network, Unity Ads prefers to receive postbacks for all new installs of your app from any source, and they recommended selecting **All media sources including organic** to send all install postbacks to Unity Ads.


### In-app events settings

Map AppsFlyer events with the partner via postbacks. If postback sending is enabled, this includes rejected in-app events (events blocked by Protect360 or events found to be non-compliant with target validation rules).

[![](https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png)](https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png)

#### To configure in-app event postbacks

1. Enter the **game\_id**. Make sure the game\_id is correct and is the same as used for install attribution.
2. Turn on **In-app event postbacks**.
3. Set the **In-app event postback window**, if required (read more about[in-app event postback window configuration](/docs/in-app-event-postback-configuration#inapp-event-postback-window)).
4. Click **Add event** to add an SDK or server-to-server event to the list.
5. Complete the following parameters:



| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.  <br />**Tip**: Don't see the event you are looking for?<br /><br />* Make sure to activate the event on a device with a non-organic installation and recheck.<br />* Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br /><br />* **Text field:** Get the corresponding event ID from the partner.<br />* **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br />* **As is**: Send the events as they are, without name mapping. |
| **for users from** | Select the sending option for the event:<br /><br />* **This partner only**: send postbacks only when this event is attributed to this partner.<br />* **All media sources, including organic**: send postbacks for events attributed to any partner, as well as organic events. According to Unity Ads, this option is recommended. |
| **including** | * **No data (default)**: send only the event itself without the event value.<br />* **Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event). According to Unity Ads, this option is recommended.<br />* **Values without revenue**: send all the parameters **excluding** the revenue value. |


> 📘 **Important!**
>
> Select the correct SDK/server-to-server event and the corresponding partner event identifier. Do not duplicate events (do not pass the same events under different SDK/server-to-server event names).

> 📘 **Note**
>
> You can send [ad revenue postbacks](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks) to Unity Ads so they can optimize campaigns using ad revenue data:
>
> * **Event name:** af\_ad\_revenue
> * **Mapped to:** ad\_revenue


## Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[More about attribution link structure and parameters](/docs/about-link-structure-and-parameters)**.**

**To generate an attribution link,**follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

**Notes:**

* When the target audience of an Android app includes children, Unity sends zeroed-out advertising IDs.

## Cost tab

Cost on the attribution link isn't supported. AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. 

**Note**:

* Cost data requires an ROI360 subscription.
* Cost data from Unity Ads can be received only for downloads coming from Google Play or Apple App Store. For Android, cost data for third-party Android app stores isn't supported.
* Agency cost isn't supported via cost by click or API. Advertisers can send agency cost data via [Ad Spend Ingestion](/docs/import-cost-data).

**To enable the cost API**:

* Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).   
  **Note**: For Unity cost integrations, all apps with the same Service account key ID must contain the same Organization core ID and Service account secret key. Otherwise, pulling cost data is affected. Make sure to select the **Organization core ID**.

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

## Ad revenue tab

This section is relevant if you are acting as a publisher, displaying ads of the partner to your users. As such, you would certainly like to measure the engagement of your users acquired from different sources, to find the most profitable sources for you.

**To enable the ad revenue API**:

* Follow [these integration instructions](/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners).

## Permissions tab

In this tab, you can select the permissions to grant Unity Ads to perform certain actions. Note that even if attribution is disabled for Unity Ads, the permissions tab is active and you can grant Unity Ads permissions.  
Learn more about [the permissions you can grant](/docs/set-up-an-integrated-partner#permissions-tab).
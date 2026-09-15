---
title: "The Trade Desk campaign configuration"
excerpt: "Learn how to set up and integrate The Trade Desk (TTD) with AppsFlyer to measure click-based and view-through mobile attribution, CTV campaigns, and retargeting."
---
**At a glance:** The Trade Desk, an AppsFlyer ad network integrated partner, uses its enhanced mobile advertising solution to cultivate strategic, scalable, and smart campaigns to meet the needs of cross-device users. The Trade Desk offers click-based mobile attribution, view-through mobile attribution, and click-based retargeting, all of which can be recorded through AppsFlyer.

## Setting up The Trade Desk (TTD)

Follow these steps to enable AppsFlyer campaign measurement.

### Step 1: Define conversion events in TTD

1. On the left menu of your TTD advertiser page, click **DATA**.
2. From the top menu, click **Add App Data**.
3. Enter the following fields on the **Create App Data** page:
   * **App Name:** Enter the name of the app.
   * **Operating System:** Select either **Android** or **iOS**.   
     **Note:** TTD supports CTV under both the Android and iOS options.
   * **Tracking Vendor:** Select **AppsFlyer**.
   * **Events:** Click **ADD EVENT** to add conversion events and enter the fields:
     * **EVENT NAME**: Enter the event name.  
       **Note:** Make sure the name is written precisely as in AppsFlyer, including capitalization, spaces, and symbols.
     * [Optional] **DESCRIPTION**: Add a description.
     * [Optional] **USAGE OF COLLECTED DATA**: Select **Attribution**. This option includes both attribution and retargeting.
     * To add more events, click **ADD EVENT** and repeat the process.
   * **Conversion Credit Source**: Select which source to attribute conversions, either AppsFlyer or The Trade Desk.   
     **Note:**
     * For measuring cross-device and TTD buy, select **The Trade Desk**.   
       For a holistic view of measurement not just in TTD, select **AppsFlyer**.
     * Never change this selection during a campaign.
     * Make sure to select the correct source before clicking **CREATE APP DATA**. You can't change your conversion credit source during a campaign.
4. Click **CREATE APP DATA**.

### Step 2: Define conversion events in AppsFlyer

For AppsFlyer to define conversion events and enable you to send event postbacks to TTD, you must first [integrate TTD with AppsFlyer](/docs/the-trade-desk-campaign-configuration#integrating-ttd-with-appsflyer) and set up the following configurations:

* Integration settings (including the configuration of event postbacks)
* Attribution link
* Permissions

### Step 3: Map defined conversion events from AppsFlyer

1. From the TTD left menu, click **CAMPAIGNS**.
2. Scroll down to **Campaigns** and select a campaign from the list.
3. Click **Edit Reporting & Attribution**.
4. Click **ADD CONVERSION DATA SOURCE**.
5. Under **CONVERSION DATA SOURCE**, select or type **AppsFlyer**. AppsFlyer events are now mapped to TTD events.
6. **CROSS-DEVICE CONCEPT**:
   * If you chose in [Step 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) (Conversion Credit Source) to have conversions attributed by TTD, select here **Household** to see conversions in all available channels (such as mobile in-app and CTV).
   * If you chose AppsFlyer in [Step 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd), select here **None**.
7. Click **SAVE**.

### Step 4: Add click and impression trackers to campaign creatives

In this step, you'll add the click and impression trackers that were created in AppsFlyer to each of the creatives in TTD.

1. Under **CAMPAIGNS** in the TTD left menu, click the **CREATIVES** from the top tab.
2. Select a creative from the list of creatives associated with the current campaign.
3. Scroll down to **Tracking**.
4. Copy the view-through [attribution link](/docs/the-trade-desk-campaign-configuration#h_01HH2DHQWY7X522JKKC4A45BHN) from AppsFlyer, and paste it to the 1x1 Pixel Impression Tracking URL field.
5. Copy the click-through attribution link from AppsFlyer, and paste it to the click-Through URL field.
6. Click **SAVE CHANGES**.
7. Repeat this step for each of the creatives associated with the campaign.

> 📘 **Note**
>
> If you've chosen for conversions to be attributed by TTD (in [Step 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd)), you can edit the attribution windows:
>
> 1. From the menu of icons on the right of any TTD page, click the cogwheel to open the **Advertiser Preferences**.
> 2. Scroll down to **Attribution Windows** and click the edit button on the right.
> 3. From the **Manage Attribution Windows** page, edit the attribution windows:
>    * **De-duplication Windows:** The number of conversions you can see in a certain period of time.
>    * **Campaign Attribution Windows:** The period of time from ad exposure to the conversion.
> 4. Click **SAVE**.


## Integrating TTD with AppsFlyer

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

TTD configuration window includes three active tabs: Integration, Attribution link, and Permissions. Click the items below to read about the tabs setup.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

### Integration tab

#### Activate partner

On your first visit, you'll need to turn on the **Activate partner** toggle to set up the integration. The toggle must remain on for as long as you work with TTD.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

#### Advanced Privacy

For iOS apps, the [Enable Advance Privacy](/docs/apply-aggregated-advanced-privacy-framework) toggle appears. When turned on, it limits the sharing of user identifiers with the partner. Note that when the [Aggregated Advanced Privacy](/docs/apply-aggregated-advanced-privacy-framework) toggle is on in the App Settings, **Enable Advanced Privacy** is turned on and locked by default. 

#### General settings

**Tracker and advertiser ID**

The Trade Desk connects with AppsFlyer via a unique network ID. If you don't already have the Tracker\_ID and the advertiserid, you must obtain them from The Trade Desk to continue with the integration.

![TTD_General_Settings_.png](https://files.readme.io/f7f2b66556f2713ff56a3bd2fcfe6fe8fe8d346a9b322904f93670ee55cf94c3-50612291000849.png)

**Enable View-Trough attribution**

Turn on **Enable View-Through attribution** to attribute view-through installs from The Trade Desk. The view-through lookback slider is available on the attribution link tab (described below).

#### Default postbacks

![default_postbacks_en-us.png](https://files.readme.io/b291c9fd4ac858723f3071bf271a041403639d49bfb1984030fc7c7306c40c16-50612291002385.png)

Send automatic postbacks to The Trade Desk following user installs and re-engagements. Use this section to define the source of the users that allow sending these postbacks:

* **This partner only**: for events coming only from users attributed to The Trade Desk.
* **All media sources including organic**: to have your entire user base available to be reported to The Trade Desks.

> 📘 **Note**
>
> As an all-installs network, The Trade Desk prefers to receive postbacks for all new installs of your app from any source, and they recommend selecting **All media sources including organic** to send all install postbacks to The Trade Desk.


#### In-app events settings

Map AppsFlyer events with TTD via postbacks. If postback sending is enabled, this includes rejected in-app events (events blocked by Protect360 or events found to be non-compliant with target validation rules).

![the_trade_desk_in_app_event_settings_en-us.png](https://files.readme.io/a72231e1f7d21eeb6ffd0b8e0ce056872ec7ef4670470a86e93eb7094ff9cea8-50612307447185.png)

**To configure in-app event postbacks:**

1. Enter the **advertiserid** and **Tracker\_ID**.
2. Enable **In-app event postbacks**.
3. Set the **In-app event postback window**, if required (read more about[in-app event postback window configuration](/docs/in-app-event-postback-configuration#inapp-event-postback-window)).
4. If available, select whether to send events automatically or manually. Learn more about [sending all events as they are](/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped).
5. Click **Add event** to add an SDK or server-to-server event to the list.
6. Complete the parameters required.
7. [Optional] Click![conditional-iae-postbacks-icon.png](https://files.readme.io/8b8da8198a5180447eacaab4a3dd101d82149a8d7aa926e3b896847a18eb76f9-50612291007377.png) to set conditions for sending certain in-app events to TTD.  
   Learn more about [conditional in-app event postbacks](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks).



| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.  <br />**Tip**: Don't see the event you are looking for?<br /><br />* Make sure to activate the event on a device with a non-organic installation and recheck.<br />* Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **for users from** | Select the sending option for the event:<br /><br />* **This partner only**: send postbacks only when this event is attributed to this partner.<br />* **All media sources including organic**: send postbacks for events attributed to any partner, as well as organic events. |
| **including** | * **No data (default)**: send only the event itself without the event value.<br />* **Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event).<br />* **Values without revenue**: send all the parameters **excluding** the revenue value. |



### Attribution link tab

Generate and save attribution links and send them to TTD for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or [OneLink](/docs/onelink-guide).

#### Attribution link parameters

Adding parameters to the attribution link enables you to perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here. When saving the attribution link, all the parameters configured in this tab are saved.

Select which parameters you want to add to the attribution link.

![ttd_attribution_link_parameters_en-us.png](https://files.readme.io/2658797286fd7d922c68a9c2f1705166672066d4179d72cf4fe0039ac3ede212-50612291012625.png)

#### Default parameters



| Name | Description | Parameter |
| --- | --- | --- |
| Site ID | Set your site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations. | af\_siteid |
| Campaign Name | Add your campaign name to compare different campaigns running with TTD. | c |
| Campaign ID | Add your campaign ID. | af\_c\_id |
| Adset ID | Add your adset ID to compare the performance of all your ads per adset. | af\_adset |
| Ad ID | Add your ad ID. | af\_ad\_id |



You can add more parameters for the attribution link. Learn more about [setting up the attribution link](/docs/set-up-an-integrated-partner#attribution-link-tab) and about attribution link [structure and parameters](/docs/about-link-structure-and-parameters).

#### Parameters for measuring CTV

You can have CTV traffic measured with AppsFlyer by adding the following parameters and values:



| Parameter | Value | Comments |
| --- | --- | --- |
| redirect | false |  |
| af\_xplatform\_vt\_lookback | 1h-72h | Any value between 1-72 hours can be entered |



#### Click-through attribution

![click-through_attribution_ttd_en-us.png](https://files.readme.io/9d8c4aed6aa5d8b3cba5b4e32a5245f4bd8b6d9cf50e8cc800dce66842487355-50612291014673.png)

Use the slider to set the maximum time from click to install. Only installs (first launches) that take place within the lookback window are attributed.

Lookback window range: 1-23 hours or 1-30 days.

Attribution link parameter: af\_click\_lookback

Learn more about the [click lookback window](/docs/set-up-lookback-windows).

**Click-through attribution link:** Contains all the parameters you included in the attribution link setup. You can copy the link and send it to the partner to be activated when your leads click a corresponding ad.

#### View-through attribution

![view-through_attribution_ttd_en-us.png](https://files.readme.io/7435384719e46f0534149ef41612db6ee54c930bab8e8eadc1fd86ae84d5d777-50612307451921.png)

Use the slider to set the maximum time from impression to install. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to the partner, providing there was no other relevant ad click.

Lookback window range: 1-24 hours.

Attribution link parameter: af\_viewthrough\_lookback

Learn more about [view-through attribution](/docs/set-up-lookback-windows).

**View-through attribution link:** Contains all the parameters you included in the attribution link setup. You can copy the link and send it to the partner to be activated when your leads click a corresponding ad.

### Cost tab

Cost integration is not available for The Trade Desk.

### Ad revenue tab

Ad revenue is not available for The Trade Desk.

### Permissions tab

In this tab, you can select the permissions to grant The Trade Desk, whether they act as an ad network, agency, or even both. Note that even if attribution is disabled for The Trade Desk, the permissions tab can be active and you can grant control to The Trade Desk.

![](https://support.appsflyer.com/hc/article_attachments/50612307452817)

Use these toggles to give the ad network permissions to handle its own configuration for your app:

#### **Ad network permissions**

* **Allow to configure integration:** Allow TTD to set up the integration tab, except for in-app event postbacks
* **Allow to configure in-app event postbacks:** Allow TTD to setup in-app event postback mapping to itself, on the integration tab
* **Allow access to your retention report:** Only for TTD's own retention data
* **Allow access to your aggregate loyal user data:** Only for TTD's own loyal user data
* **Allow access to your aggregate in-app events data:** Only for TTD's own in-app events data
* **Allow access to your aggregate revenue data:** Only for the revenue data attributed to TTD
* **Allow access to your Protect360 dashboard:** Only for TTD's own Protect360 data, and providing you have this feature enabled

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).
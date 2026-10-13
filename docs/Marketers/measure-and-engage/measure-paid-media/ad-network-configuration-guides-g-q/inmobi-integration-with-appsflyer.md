---
title: "InMobi integration with AppsFlyer"
excerpt: "Learn how to set up the InMobi integration with AppsFlyer to record click-based mobile attribution, cost, retargeting, and view-through attribution."
---
**At a glance:** InMobi, an AppsFlyer integrated ad network partner, enables consumers to discover new products and services through contextual and curated recommendations on mobile devices. In addition to click-based mobile attribution, Inmobi also offers cost, retargeting and view-through attribution, which you can record with AppsFlyer.

![inmobi_icon.png](https://files.readme.io/cbe0e88492041fc8e1781b397b67a3c8c3a09591974f2cf4fa145a18ca9e6a8d-10602685724817.png)

## Setting up Inmobi

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

Inmobi's configuration window includes 4 active tabs: **Integration, Attribution link, Cost**, and **Permissions**. Click on the following items to read about the tab setup.

> 📘 **Tip**
>
> * The [General Settings](/docs/set-up-an-integrated-partner#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**


## Integration tab

### Activate partners

On the **first visit** here, you will need to toggle ON the **Activate Partner** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

> 📘 **Note**
>
> As an ALL-Installs network, Inmobi prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to InMobi.


### General settings

**gpm\_ID**

Inmobi connects with AppsFlyer via a unique network ID. If you don't already have the Network ID, you must obtain it from Inmobi to continue with the integration.

![Inmobi_msc_new_3.png](https://files.readme.io/9c2efaed833211582a33b3a2bbd7d07336bc78d6e2d4e3a7645b5ca14be2fd73-360001865845.png)

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Inmobi. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Inmobi following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to InMobi.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to InMobi.

### In-app events settings

In this section you can map your AppsFlyer events with InMobi via postbacks.

1. Set the Inmobi gpm\_id again here.
2. Toggle In-App Event Postbacks to ON.
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner.  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner.
4. Click **Add Event** to add an SDK Event to the list.
5. Fill in the following parameters:



| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event, as defined on InMobi's side.  <br />Obtain the corresponding Event ID from InMobi and set in the text field. |
| **Send Revenue** | **When unchecked** - Send all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - Send all the parameters including the revenue value (if it exists in the event). |



## Attribution link tab

In this tab, you can create the attribution links you want to send to Inmobi for attributing Inmobi's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links. [![](https://files.readme.io/1f198f652bc960ea8d20c58d4bf704b8aff1361d105d9ed72c52c070eb88d2ce-360002187398.png)](https://files.readme.io/1f198f652bc960ea8d20c58d4bf704b8aff1361d105d9ed72c52c070eb88d2ce-360002187398.png)

[![](https://files.readme.io/03371cdc64826e77cee3bd0adb90280aa59ebddd34ec85d8946ae9646ce86ce8-360001866409.png)](https://files.readme.io/03371cdc64826e77cee3bd0adb90280aa59ebddd34ec85d8946ae9646ce86ce8-360001866409.png)

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with InMobi.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific InMobi campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Inmobi.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

[![](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about[**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters)**.**

### Retargeting settings

When enabled, AppsFlyer recognizes a link as a [retargeting](/docs/retargeting-attribution-guide) attribution link, rather than a user acquisition link, by adding the `&is_retargeting=true` to the click recording link. Note that retargeting is currently only supported for click-through and not view-through attribution.  
**Attribution link parameter:** is\_retargeting.

The following setup below is displayed when retargeting is enabled.

![msc_new_7.png](https://files.readme.io/b90bbd6e3bea9dd862808343896b005071b7d9e564d31039c188c3ebf8e81077-360002254489.png)

1. Standard Link vs. OneLink

Select **standard attribution link** option if:

* You don't need to deep link with the URL or
* Plan to use only [URI schemes](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings) for deep linking

select **Use OneLink** for:

* Using a single link for both Android and iOS apps or
* Deep linking using Universal or app links

Note that selecting OneLink changes the click recording link from app specific to a [OneLink URL](/docs/onelink-guide).

2. Deep Link URL

Use this field if the link is meant to deep link users to any specific activity within your app.  
**Attribution link parameter:** af\_dp  
You can find more information about AppsFlyer's [deep linking solution in this guide.](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink)

3. Re-engagement Window

Set the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source. You can set the value in days (1-90), hours (up to 23), or even lifetime.

**Attribution link parameter:** af\_reengagement\_window

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Inmobi.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

[![](https://files.readme.io/930deba7817e7ede9504624111c3190dcd01a1f6dfb626463a844fcaa2d66930-360002254509.png)](https://files.readme.io/930deba7817e7ede9504624111c3190dcd01a1f6dfb626463a844fcaa2d66930-360002254509.png)

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Inmobi to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Inmobi, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the [view-through attribution here](/docs/set-up-lookback-windows).

[![](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to InMobi to be activated when a corresponding ad is watched, usually for 1 second or more.

## Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

## Ad revenue tab

Ad Revenue data is not supported by this partner.

## Permissions tab

Select which [permissions to grant](/docs/set-up-an-integrated-partner#permissions-tab) InMobi to access your data and perform various actions.

> 📘 **Note**
>
> When the integration is [deactivated](/docs/partner-activation-deactivation) while the Permissions toggle is still turned on, permissions remain granted.
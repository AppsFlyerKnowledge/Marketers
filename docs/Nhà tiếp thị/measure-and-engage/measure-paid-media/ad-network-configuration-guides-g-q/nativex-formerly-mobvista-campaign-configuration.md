---
title: Nativex (formerly Mobvista) campaign configuration
metadata:
  keywords:
    - mobvista
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
  created_at: '2016-03-28T09:15:13Z'
  edited_at: '2026-08-13T08:31:46Z'
  id: 208209476
  locale: en-us
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/208209476-Nativex-formerly-Mobvista-campaign-configuration
---
> **At a glance:** Nativex, an AppsFlyer integrated partner, is a mobile marketing platform providing user acquisition, analytics, and monetization solutions to worldwide mobile developers and brands. In addition to click-based mobile attribution, Nativex also offers cost and view-through attribution, which you can record with AppsFlyer.

![nativex.png](https://files.readme.io/840450215d38dc171452049ce1e9ce8c5f289e489fcb985a8d7ecb745fd11ede-49783409596049.png)

## Setting up Nativex

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

Nativex's configuration window includes 4 active tabs: Integration, Attribution link, Cost, and Permissions. Click on the items below to read about the tabs setup.

> 👍 **Tip**
>
> * The <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#d-general-settings">General Settings</Anchor> step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partners

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable the set up of the Integration tab parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, please click <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">here</Anchor>.

### General Settings

**Mobvista\_campuuid**

Nativex connects with AppsFlyer via a unique network ID. If you don't already have the Network ID, you must obtain it from Nativex to continue with the integration.

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Nativex. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Nativex following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Nativex.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Nativex.

### In-app events settings

In this section you can map your AppsFlyer events with Nativex via postbacks.

1. Set the Nativex network ID again here
2. Toggle In-App Event Postbacks to ON
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Nativex's side.  <br />Obtain the corresponding Event ID from Nativex and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Nativex for attributing Nativex's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to perform thorough drill-down analyses later. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Nativex.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Nativex campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Nativex.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise limiting the number of used site IDs and using the sub site ID parameter to avoid <Anchor target="_blank" href="/marketers/vi/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">**AppsFlyer Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Nativex.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Nativex to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Nativex, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">view-through attribution here</Anchor>.

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Nativex to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Nativex automatically sends encrypted CPI cost data on the attribution link for all installs.

For the full list of partners supporting cost data, click <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#additional-information">here</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue data is not supported by this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Nativex, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for Nativex, the permissions tab is active and you can grant control to Nativex.

### Ad network permissions

Use these toggles to give Nativex permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit Nativex to set up the Integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit Nativex to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to Nativex's own retention data
* ***Allow access to your Protect360 dashboard*** - only to Nativex's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

* ***Main toggle*** - Set to On to reveal the agency permissions options
* ***Allow access to your retention report*** - only to the agency's own retention data
* ***Allow access to aggregate organic data***
* ***Allow to configure in-app event postbacks*** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab

Learn more about granting <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#cấp-quyền-cho-đại-lý">agency permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-mobvista=setting-up-nativex h_01HKW7VFYJ6CZP5JD29YAS3AAH=setting-up-nativex h_01HKW7VFYJ02HSZ963PX5H38ZS=tip h_01HKW7VFYJXNP3AP7FZPFBRHA7=integration-tab h_01HKW7VFYJB9F9M8KGEA52ZQGD=activate-partners h_01HKW7VFYJDAT6G9VSC5H50Y9K=general-settings h_01HKW7VFYJVW66881ZHG2Q1B31=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW7VFYJA1919WZ0XPY8SP98=in-app-events-settings h_01HKW7VFYJKD1BHDDAG8VKFTYB=attribution-link-tab h_01HKW7VFYJFGKPDDBT09T3BXAN=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKW7VFYJMYJ508P8E3B5WNN2=click-through-attribution h_01HKW7VFYJ6N5JMZTDBAKX02A4=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HKW7VFYK0YRYZXMPFRJNQJKP=view-through-attribution-lookback-window h_01HKW7VFYKD6S2NZ280VXRQT1F=impressions-attribution-link h_01HKW7VFYKDN59CAGE3JC11G7D=cost-tab h_01HKW7VFYK3AGC81SBA00C43AD=ad-revenue-tab h_01HKW7VFYKS66EAP51QECZPFQH=permissions-tab h_01HKW7VFYKRE972AJAM499H241=ad-network-permissions h_01HKW7VFYK1T10MR5AJ436C2NS=agency-permissions" />

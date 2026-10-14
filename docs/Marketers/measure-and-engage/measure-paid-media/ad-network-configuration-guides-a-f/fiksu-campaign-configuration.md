---
title: "Fiksu campaign configuration"
excerpt: "Fiksu, an AppsFlyer ad network integrated partner, lets performance-driven marketers target and engage specific audiences that are most likely to spend time and money in their app. In addition to click-based mobile attribution, Fiksu also offers view-through attribution, which you can record with AppsFlyer."
x-zendesk:
  id: 207033936
  url: https://support.appsflyer.com/hc/en-us/articles/207033936-Fiksu-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  position: 24
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Campaign, SDK, Media Source Configuration, Configure, Fiksu, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2015-03-08T13:07:42Z'
  edited_at: '2026-09-09T13:11:43Z'
---
## Setting up Fiksu

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partners

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

> 📘 **Note**
>
> As an ALL-Installs network, Fiksu prefers to receive postbacks for all new installs of your app from ANY source, including organic. It is recommended to select **Events attributed to any partner** to send all install postbacks to Fiksu.

### General settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Fiksu. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Fiksu following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Fiksu.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Fiksu.

### In-app events settings

In this section you can map your AppsFlyer events with Fiksu via postbacks.

1. Toggle In-App Event Postbacks to ON
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Fiksu's side.  <br />Obtain the corresponding Event ID from Fiksu and set it in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Fiksu for attributing Fiksu's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Fiksu.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Fiksu campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Fiksu.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about[**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Fiksu.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Fiksu to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Fiksu, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the [view-through attribution here](/docs/set-up-lookback-windows).

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Fiksu to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost integration is not available for Fiksu.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue data is not supported by this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Fiksu, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for Fiksu, the permissions tab is active and you can grant control to Fiksu.

### Ad network permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -*only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

* ***Main toggle*** - Set to On to reveal the agency permissions options
* ***Allow access to your retention report*** - only to the agency's own retention data
* ***Allow access to aggregate organic data***
* ***Allow to configure in-app event postbacks*** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab

Learn more about granting [agency permissions](/docs/set-up-an-integrated-partner#agency-permissions).

</Accordion>

<div data-zendesk-anchors="h_01HKWB9WVVQ64QR9YX3MH7VGEQ=setting-up-fiksu h_01HKWB9WVVB2KTKYH4H71KYSPH=integration-tab h_01HKWB9WVWEM3JV591Y10JKSJX=activate-partners h_01HKWB9WVWFXCANSKQ6BHSP7AC=note h_01HKWB9WVWZW406F39Q1Q05PPF=general-settings h_01HKWB9WVW2JJV6GXS6PAW8Z5D=default-postbacks inapp-events-settings=in-app-events-settings h_01HKWB9WVWRWKH9YBPBA0KJXXW=in-app-events-settings h_01HKWB9WVWSN05C4QGGZJ1E07E=attribution-link-tab h_01HKWB9WVW907GFS5DD4Y8BA22=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HKWB9WVW55W199VX5NBVVKFK=click-through-attribution h_01HKWB9WVWK0HNABYVH9MVFYB6=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HKWB9WVWKNPP1Y4FET06W02S=view-through-attribution-lookback-window h_01HKWB9WVW0DE7Z290K91HVN92=impressions-attribution-link h_01HKWB9WVXWCA9FQAS7E6V3JR8=cost-tab h_01HKWB9WVX2TETG4366S0YQAB9=ad-revenue-tab h_01HKWB9WVX4697WV73434RGZ9R=permissions-tab h_01HKWB9WVXNCKD1E5Y9AG54B08=ad-network-permissions h_01HKWB9WVXSFDH3309H2ST85NS=agency-permissions" />

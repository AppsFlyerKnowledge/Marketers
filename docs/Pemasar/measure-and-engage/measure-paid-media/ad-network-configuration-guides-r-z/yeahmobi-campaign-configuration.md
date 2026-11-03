---
title: Yeahmobi campaign configuration
metadata:
  keywords:
    - yeah-mobi
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
  created_at: '2016-03-28T10:00:25Z'
  edited_at: '2026-09-09T13:37:14Z'
  id: 209731663
  locale: en-us
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/209731663-Yeahmobi-campaign-configuration
---
> **At a glance:** Yeahmobi, an AppsFlyer ad network integrated partner, is a video ad network for iOS and Android. In addition to click-based mobile attribution, Yeahmobi provides cost data, which can be recorded with AppsFlyer.

To configure your campaigns with Yeahmobi, follow the steps below.

## Setting up Yeahmobi

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partners

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle **must** be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/id/docs/partner-activation-deactivation">here</Anchor>.

### Default Postbacks

Send automatic postbacks to Yeahmobi following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Yeahmobi.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Yeahmobi.

### In-app events settings

In this section, you can map your AppsFlyer events with Yeahmobi via postbacks.

1. Turn on In-App Event Postbacks.
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner.  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner.
3. Click **Add Event** to add an SDK Event to the list.
4. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server-to-server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on the Yeahmobi side.  <br />Obtain the corresponding Event ID from Yeahmobi and set it in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Yeahmobi for attributing Yeahmobi campaigns, ad sets, or even single ads. Note that AppsFlyer **doesn't** save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Yeahmobi.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Yeahmobi campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Yeahmobi.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/id/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Yeahmobi.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Yeahmobi to be activated when leads click on a corresponding ad.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Yeahmobi automatically sends CPI cost data on the attribution link for all installs.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue data is not supported by this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant to the partner, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for the partner, the permissions tab is active and you can grant control to the partner.

### Ad network permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

* ***Main toggle*** - Set to On to reveal the agency permissions options
* ***Allow to configure in-app event postbacks*** - permit the agency to set in-app event postbacks mapping to itself on the integration tab
* ***Allow access to aggregate organic data***
* ***Allow access to your retention report*** - only to the agency's own retention data

Learn more about granting <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#hak-akses-agensi">agency permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HK290F4KYKPR30MW5EH7XSTG=setting-up-yeahmobi h_01HK290F4KJ4JB72D32RPWBA26=integration-tab h_01HK290F4KQVRHB6VB089A9VFH=activate-partners h_01HK290F4KVZPHFD23EKC88BNJ=default-postbacks inapp-events-settings=in-app-events-settings h_01HK290F4KAK84A1M36VNTFM84=in-app-events-settings h_01HK290F4KKVB38XP7VP5KSR7V=attribution-link-tab h_01HK290F4KV3CNJXW6DP7PSTFQ=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HK290F4M10V9K1AWF8M8JXD1=click-through-attribution h_01HK290F4MV18FSH7GEPBPJESC=click-attribution-link h_01HK290F4MY2F9SX963Q1GGFTV=cost-tab h_01HK290F4MHPH43P52J5ZV9ZC3=ad-revenue-tab h_01HK290F4MZ8MKZVEZPAY8ZBEV=permissions-tab h_01HK290F4MEXVTJJGAB2BAEGM5=ad-network-permissions h_01HK290F4MHH62HP0KRBN9FK9W=agency-permissions" />

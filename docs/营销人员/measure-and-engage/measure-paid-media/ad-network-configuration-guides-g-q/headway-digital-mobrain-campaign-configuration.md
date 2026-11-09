---
title: Headway Digital (Mobrain) campaign configuration
metadata:
  keywords:
    - headway
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
  created_at: '2016-04-04T14:59:03Z'
  edited_at: '2026-10-13T01:08:45Z'
  id: 209803183
  locale: zh-cn
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/zh-cn/articles/209803183
---
> **At a glance:** Headway Digital, an AppsFlyer integrated ad network partner, provides data-focused marketing solutions that drive execution and powerful brand insight on mobile. In addition to click-based mobile attribution, they offer cost, retargeting, and view-through attribution, which you can record with AppsFlyer.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobrain.png?v=1" width="213px" />

## Setting up Headway Digital (Mobrain)

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partner

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable the set up of the Integration tab parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, please click <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">here</Anchor>.

### General settings

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Mobrain. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Mobrain following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Mobrain.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Mobrain.

### In-app events settings

In this section you can map your AppsFlyer events with Mobrain via postbacks.

1. Toggle In-App Event Postbacks to ON
2. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
3. Click **Add Event** to add an SDK Event to the list
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Mobrain's side.  <br />Obtain the corresponding Event ID from Mobrain and set in the text field. |
| **Send Revenue** | **When unchecked** - Send all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - send all the parameters, including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Mobrain for attributing Mobrain's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to perform thorough drill-down analyses later. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Mobrain.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Mobrain campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Mobrain.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/zh/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">**AppsFlyer Attribution Link Structure and Parameters**</Anchor>.

### Retargeting settings

When enabled, AppsFlyer recognizes a link as a <Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">retargeting</Anchor> attribution link, instead of a user acquisition link, by adding the `&is_retargeting=true` to the click recording link. Note that retargeting is currently only supported for click-through and not view-through attribution.  
**Attribution link parameter:** is\_retargeting.

The following setup is displayed when retargeting is enabled.

1. Standard Link vs. OneLink

Select ***standard attribution link*** option if:

* You don't need to deep link with the URL or
* Plan to use only <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">URI schemes</Anchor> for deep linking

select ***Use OneLink*** for:

* Using a single link for both Android and iOS apps or
* Deep linking using Universal or app links

Note that selecting OneLink changes the click recording link from app specific to a <Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink URL</Anchor>.

2. Deep Link URL

Use this field if the link is meant to deep link users to any specific activity within your app.  
**Attribution link parameter:** af\_dp  
You can find more information about AppsFlyer's <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">deep linking solution in this guide.</Anchor>

3. Re-engagement Window

Set the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source. You can set the value in days (1-90), hours (up to 23), or even lifetime.

**Attribution link parameter:** af\_reengagement\_window

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Mobrain.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Mobrain to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Mobrain, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the <Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">view-through attribution here</Anchor>.

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Mobrain to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Mobrain automatically sends CPI cost data on the attribution link for all installs.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue data is not supported by Mobrain.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Mobrain, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for Mobrain, the permissions tab is active and you can grant control to Mobrain.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

### Agency permissions

Use these toggles to give the agency permissions to handle its own configuration for your app:

* ***Main toggle*** - Set to On to reveal the agency permissions options
* ***Allow to configure in-app event postbacks*** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to aggregate organic data***
* ***Allow access to your retention report*** - only to the agency's own retention data

Learn more about granting <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#代理权限">agency permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKA1AEYTDZ5H5J33Z9FW10QW=setting-up-headway-digital-mobrain h_01HKA1AEYV5A1J168WK2D6FTVP=integration-tab h_01HKA1AEYVAM34GGG30SKTGK3X=activate-partner h_01HKA1AEYVQEEJZQBVXG29T999=general-settings h_01HKA1AEYVPH65388RM6SCPH8H=default-postbacks inapp-events-settings=in-app-events-settings h_01HKA1AEYVYSNGNKR738X9QCKB=in-app-events-settings h_01HKA1AEYV3C0VN31RM44N2Q93=attribution-link-tab h_01HKA1AEYV50HE549X8FGZ48DJ=attribution-link-parameters h_01HKA1AEYVDJSSQGSCYRK75J35=retargeting-settings clickthrough-attribution=click-through-attribution h_01HKA1AEYV721RG0D13GQDTAFH=click-through-attribution h_01HKA1AEYVBZH3W5M8GWDGM8NS=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HKA1AEYV0X18DS118ZRW9XXH=view-through-attribution-lookback-window h_01HKA1AEYV0KM6GCZESTM7DGD5=impressions-attribution-link h_01HKA1AEYVWANYAXHW5Z8N3KEK=cost-tab h_01HKA1AEYW6HCFKSSF9MZZ3BJ9=ad-revenue-tab h_01HKA1AEYWHD46RKKV3R13FXJE=permissions-tab h_01HKA1AEYWXZT0S754P18VY9R2=ad-network-permissions h_01HKA1AEYWJDXRM0QVBQQ7J58T=agency-permissions" />

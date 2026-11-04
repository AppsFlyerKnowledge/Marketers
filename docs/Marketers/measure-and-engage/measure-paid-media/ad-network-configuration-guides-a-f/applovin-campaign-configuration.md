---
title: AppLovin campaign configuration
metadata:
  keywords:
    - Applovin
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
  created_at: '2016-03-06T12:20:32Z'
  edited_at: '2026-09-09T13:01:06Z'
  id: 208335613
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/208335613-AppLovin-campaign-configuration
---
> **At a glance:** AppLovin, an AppsFlyer integrated partner, is a well-known ad network for mobile app traffic. In addition to click-based mobile attribution, AppLovin also offers cost, ad revenue, and view-through attribution, which you can record with AppsFlyer.

<div id="setting-up-applovin" />

## Setting up AppLovin

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

<div id="activate-partner" />

### Activate partner

On the **first visit** here, you will need to toggle ON the **Activate Partner** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

<div id="note" />

> 📘 **Note**
>
> As an ALL-Installs network, AppLovin prefers to receive postbacks for all new installs of your app from ANY source, including organic. It is recommended to select *Events attributed to any partner* to send all install postbacks to AppLovin.

<div id="general-settings" />

### General settings

**Share organic/non-organic indication**

When this toggle is turned on, if an install postback is sent for all media sources including organic, then AppLovin will receive an indication whether an install was organic or non-organic.

**SDK Key**

AppLovin connects with AppsFlyer via a unique sdk\_key. If you don't already have the sdk\_key, you must obtain it from AppLovin to continue with the integration.

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from AppLovin. The view-through lookback slider is available on the attribution link tab (described below).

<div id="default-postbacks" />

### Default postbacks

Send automatic postbacks to AppLovin following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to AppLovin.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to AppLovin.

<div id="in-app-events-settings" />

### In-app events settings

In this section you can map which of your AppsFlyer events to send to AppLovin via postbacks.

1. Set the AppLovin sdk\_key again here.
2. Toggle In-App Event Postbacks to ON.
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on AppLovin's side.  <br />Obtain the corresponding Event name from AppLovin and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard. 

<div id="applovin-billable-cost" />

> 🚧 **Applovin billable cost**
>
> As of August 1, 2024, Applovin bills all their customers based on probabilistic installs. Prior to this date, some customers were billed based on SKAN installs. <Anchor target="_blank" href="https://support.applovin.com/hc/en-us/articles/28531589437965-iOS-Billing-Method">See Applovin for additional information</Anchor>
>
> The AppsFlyer cost integration with AppLovin accurately reflects this billable cost. Meaning the cost in AppsFlyer properly matches the cost on the AppLovin platform.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

* Applovin provides ad revenue mediation with aggregate data.
* About <Anchor target="_blank" href="/marketers/docs/roi360-guide-ad-revenue-attribution">ad revenue attribution</Anchor> (ad monetization)

**To enable the ad revenue API**:

* Follow <Anchor target="_blank" href="/marketers/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">these integration instructions</Anchor>.

<div id="note-1" />

> 📘 **Note**
>
> * Applovin sends ad revenue that it generated itself.
> * Ad revenue from mediation partners such as ironSource and Unity may be displayed on the Applovin dashboard, but is not sent to AppsFlyer. Enable other mediation partners in AppsFlyer's dashboard to send ad revenue data directly to AppsFlyer.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant AppLovin. Note that even if attribution is disabled for AppLovin, the permissions tab is active and you can grant control to AppLovin.

<div id="ad-network-permissions" />

### Ad network permissions

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* **Allow to configure integration** - permit the partner to setup the integration tab (except in-app event postbacks)
* **Allow to configure in-app event postbacks** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* **Allow access to your retention report** - only to the partner's own retention data
* **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data
* **Allow access to your aggregate in-app events data** - only to the partner's own in-app events data
* **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner
* **Allow access to your Protect360 dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKW93TKBNYVC05MA5GB37JVH=setting-up-applovin h_01HKW93TKCPCFYD6HV2XH1QTHS=integration-tab h_01HKW93TKCG5JCQK52QJ65483M=activate-partner h_01HKW93TKC2XGTZ7WAQ2E2AGPD=note h_01HKW93TKCZCK6GB7M4VV5C1NB=general-settings h_01HKW93TKCCRB21JAFDA2GWH6F=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW93TKCVWKTM9C8J220Q41E=in-app-events-settings h_01HKW93TKCCXVQMBCGW02J7JK4=attribution-link-tab h_01HKW93TKCXMG7BHMEWRFSCM6N=cost-tab h_01J43V7Z67C98TG7CE2QQGVVWE=applovin-billable-cost h_01HKW93TKDDWXA2C7456E8Q8GG=ad-revenue-tab h_01HKW93TKD8Z0QQADBJWMBP962=note-1 h_01HKW93TKDBCXNA68YVMQVBVP0=permissions-tab h_01HKW93TKD21RF42KMNA9J9WXF=ad-network-permissions" />

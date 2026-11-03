---
title: Chartboost campaign configuration
metadata:
  keywords:
    - Chartboost
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
  created_at: '2016-03-28T08:01:01Z'
  edited_at: '2026-10-01T00:25:34Z'
  id: 209731553
  locale: ja
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ja/articles/209731553
---
> **At a glance:** Chartboost, an AppsFlyer ad network integrated partner, is one of the largest mobile games-only ad platforms to increase revenue. In addition to click-based mobile attribution, Chartboost also offers cost, ad revenue, and view-through attribution, which you can record with AppsFlyer.

> 📘 **Note**
>
> Integrating the Chartboost SDK is only necessary if you act as a Chartboost publisher and wish to attribute ad revenue. Otherwise, the AppsFlyer SDK is all that is required. For more information, see this article's [ad revenue section](/docs/chartboost-campaign-configuration#ad-revenue-tab).

## Setting up Chartboost

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

The ***Integration Tab*** is divided into different sections as described below.

### Activate partners

The <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation#activate-a-partner-integration">partner must be activated</Anchor> by switching on the ***Activate partner*** toggle on the first visit, to enable its setup.

### General settings

**Chartboost App ID and Signature**

Chartboost requires connecting with AppsFlyer via a unique app ID and a signature. If you do not know yours, you can obtain it directly from Chartboost.

**Enable View-Through attribution**

Toggle ON if you want to attribute view-through installs from Chartboost. The view-through lookback slider is available in the ***Attribution link*** tab.

### Default postbacks

Send automatic postbacks to Chartboost following installs and rejected installs. Use this section to define the **source of the users** for the postbacks.

Select ***This partner only*** for installs coming only from users attributed to Chartboost.  
Select ***All sources, including organi*c** to have your entire user base available to be reported to Chartboost.

Rejected installs can be sent for **This partner only**.

#### Launch postbacks

As of July 1, 2020, we no longer send launch postbacks to Chartboost. If your integration was set up before this date, there may be changes to your configurations. The following table explains possible changes and your actions, where applicable:

| Your configuration | Will be updated to | Your next actions |
| --- | --- | --- |
| Send to Chartboost **all launches** (from all media sources, including organic) | Send to Chartboost:<ul><li>**all installs** (from all media sources, including organic)</li><li>**all** `af_app_opened` **events** (from all media sources, including organic)</li></ul> | No further actions required. This update has no actual impact on the configuration. |

### In-app events settings

In this section, you can configure in-app event postbacks that are sent to Chartboost.

**To configure in-app event postbacks:**

1. Activate ***In-app event postback***.
2. Choose whether to report selected events to the partner, or all of them.
   * Note: If you choose to report all events, the *af\_app\_opened* event is not reported.
3. If you choose to manually select events, click ***Add event*** to add an SDK Event to the list.

| Parameter name | Description |
| --- | --- |
| **SDK event name** *(required for manual selection only)* | The name of the event, as received by AppsFlyer either from the SDK, or from server-to-server events.  <br />**Tip**: If you don't see the event you want in the list, activate this event on a device with a non-organic installation and recheck. |
| **Sending option** | Select the sending option for the event:  <br />**This partner only** for events coming **only** from users attributed to Chartboost.  <br />**All sources, including organic** to have your entire user base available to be reported to the partner |
| **Send event data** | <ul><li>**No values & no revenue:** sends only the event itself without the event value.</li><li>**Values & no revenue:** sends all the parameters excluding the revenue value.</li><li>**Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event).</li></ul> |

4. Click ***Save***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Chartboost for attributing Chartboost campaigns, ad sets, or single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Chartboost.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Chartboost campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Chartboost.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid <Anchor target="_blank" href="/marketers/ja/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">**AppsFlyer Attribution Link Structure and Parameters**</Anchor>.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Chartboost.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Chartboost to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to Chartboost, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the <Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">view-through attribution here</Anchor>.

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to Chartboost to be activated when a corresponding ad is watched.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

This section is relevant if you are acting as a publisher, displaying ads of the partner to your users. As such, you would certainly like to measure the engagement of your users acquired from different sources, to find the most profitable sources for you.

**To enable the ad revenue API**:

* Follow <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">these integration instructions</Anchor>.

> 🚧 **Important!**
>
> As a Chartboost publisher, there are two additional requirements besides AppsFlyer configuration:
>
> 1. [Integrate Chartboost SDK](https://answers.chartboost.com/en-us/child_article/ios) - this is only required if you act as a publisher. **If you only use Chartboost to advertise your app, AppsFlyer SDK is all you need to integrate**.
> 2. [Enable Chartboost S2S](https://answers.chartboost.com/en-us/child_article/s2s-setup) - this step is required to allow AppsFlyer to query Chartboost for ad revenue data. **This should not be confused with** <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">**AppsFlyer S2S**</Anchor> **which is your way of sending in-app events to AppsFlyer using a dedicated API.**

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Chartboost, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for Chartboost, the permissions tab is active and you can grant control to Chartboost.

Use these toggles to give the ad network permissions to handle its own configuration for your app: Ad Network Permissions

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

## Discrepancies between Chartboost and AppsFlyer

Sometimes there are discrepancies between the Chartboost dashboard and AppsFlyer dashboard.

Advertisers should be aware of the following reasons:

| Cause | Chartboost | AppsFlyer |
| --- | --- | --- |
| **Attribution Window** | Chartboost attribution window is 21 days | AppsFlyer lookback window is 7 days<br /><br />**\*\* This is the main cause of discrepancies between AppsFlyer and Chartboost** |
| **Multi-Channel Source Attribution** | Chartboost attribution works as specified above regardless of other sources. | AppsFlyer uses the last click attribution (For more information about AppsFlyer attribution, click <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">here</Anchor>) |

> 📘 **Note**
>
> While Chartboost shows all installs of a retargeting campaign in the same place, on the AppsFlyer dashboard, installs are divided between the Overview page (new installs) and the Retargeting page (re-attribution and re-engagements).

<div data-zendesk-anchors="h_01HFRFDP5V8Q9F0KTEX8X917ZX=note h_01HFRFDP5V0CTXQ0B0JXYD0TKS=setting-up-chartboost h_01HFRFDP5V7BEPGG4226CYWCS7=integration-tab h_01HFRFDP5V26M3RV5986P768A7=activate-partners h_01HFRFDP5VPBY1W81DRVVWJ54D=general-settings h_01HFRFDP5V2GAJQ81NYKDGF16K=default-postbacks h_01HFRFDP5VGFJ8K0J9GA0EX3K1=launch-postbacks inapp-events-settings=in-app-events-settings h_01HFRFDP5V3Z41EEASQD7ZPJRD=in-app-events-settings h_01HFRFDP5VKTGQFHMMXTD6KQTY=attribution-link-tab h_01HFRFDP5VA3DQSH3TRYJC47JZ=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HFRFDP5VQFQHH6ZZ6DWXSJ9C=click-through-attribution h_01HFRFDP5WAJ5Y0K27DY21NZ91=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HFRFDP5WTKE6WJ3CVS16PDF9=view-through-attribution-lookback-window h_01HFRFDP5WSM97SFDS8YC64X31=impressions-attribution-link h_01HFRFDP5W0K5A3E229PS25N9P=cost-tab h_01HFRFDP5WAB1F5YBA9BW3QYPM=ad-revenue-tab h_01HFRFDP5WMREFM3Q0DXJYTHCD=important h_01HFRFDP5WHAKN44VT9Y90P6BJ=permissions-tab h_01HFRFDP5WHWZARGXQ5ZTRC8BD=discrepancies-between-chartboost-and-appsflyer h_01HFRFDP5WN483XJN4PDV2KCR0=note-1" />

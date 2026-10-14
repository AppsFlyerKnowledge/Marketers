---
title: "MoPub Acquire campaign configuration"
excerpt: "MoPub Acquire (formerly Crossinstall, an X Ads company), is an AppsFlyer integrated partner. MoPub Acquire is a mobile-only demand-side platform specializing in playable ads at scale. In addition to click-based mobile attribution, MoPub Acquire also offers cost and view-through attribution, which you can record with AppsFlyer."
x-zendesk:
  id: 211187263
  url: https://support.appsflyer.com/hc/en-us/articles/211187263-MoPub-Acquire-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  position: 15
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [CrossInstall, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-06-20T11:27:42Z'
  edited_at: '2026-09-09T12:38:54Z'
---
![MoPub Acquire, a Twitter Company](https://cdn.appsflyer.com/marketplace/static/logo/crossinstall.png)

## Setting up MoPub Acquire

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

The Integration tab is divided into different sections as described below.

### Activate partner

**To enable the integration of this partner**, turn on **Activate partner**.  
The toggle must be on for as long as you work with the partner. Learn more about [partner activation](/docs/partner-activation-deactivation#activate-a-partner-integration).

**Enable View-Through attribution**

Turn this on if you want to attribute view-through installs from MoPub Acquire. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to MoPub Acquire following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to MoPub Acquire.

### In-app events settings

In this section, you can map your AppsFlyer events with MoPub Acquire via postbacks.

**To configure in-app events postback:**

1. Turn **In-app event postback** on.
2. Set the **In-app event postback window** (read more about[in-app event postback window configuration](/docs/in-app-event-postback-configuration#in-app-event-postback-window)).
3. Click **Add event** to add an SDK event to the list.
4. Complete the parameters required:

| Parameter name | Description |
| --- | --- |
| SDK event name | The name of the event, as received by AppsFlyer either from the SDK integrated with your app or from server-to-server events.  <br />**Tip**: Don't see the event you are looking for? Type in its SDK Event Name, click **Create custom**, and map normally. Read more about [custom event mapping](/docs/in-app-event-postback-configuration#custom-events). |
| Sending option | Select the sending option for the event:<ul><li>**Only events attributed to this partner** for events coming **only** from users attributed to this partner.</li><li>**Events attributed to any partner or organic** to have your entire user base available to be reported to the partner.</li></ul> |
| Send revenue | <ul><li>**No values & no revenue:** sends only the event itself without the event value.</li><li>**Values & no revenue:** sends all the parameters excluding the revenue value.</li><li>**Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event).</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to MoPub Acquire for attributing MoPub Acquire's campaigns, ad sets, or even single ads.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with MoPub Acquire.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific MoPub Acquire campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns MoPub Acquire.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about [**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters).

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to MoPub Acquire.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to MoPub Acquire to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to MoPub Acquire, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days.

**Attribution link parameter:** af\_viewthrough\_lookback

More details about the [view-through attribution here](/docs/set-up-lookback-windows).

### Impressions attribution link

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to MoPub Acquire to be activated when a corresponding ad is watched.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant MoPub Acquire. Note that even if attribution is disabled for MoPub Acquire, the permissions tab is active and you can grant control to MoPub Acquire. [Learn what permission can you give to MoPub Acquire](/docs/set-up-an-integrated-partner#permissions-tab).

</Accordion>

<div data-zendesk-anchors="h_01HFP4C4JDPYDGM3RBSQCNHC3T=setting-up-mopub-acquire h_01HFP4C4JDRMK87B48F4MV5B91=integration-tab h_01HFP4C4JD5A9RZP6HBBM2WFHZ=activate-partner h_01HFP4C4JDAK0N210GAH978CM0=default-postbacks inapp-events-settings=in-app-events-settings h_01HFP4C4JDEW2YBFCFR0MN6G91=in-app-events-settings h_01HFP4C4JDWBC03HBEZ13HP3NS=attribution-link-tab h_01HFP4C4JDWAWKMT1CSPQSCNMZ=attribution-link-parameters clickthrough-attribution=click-through-attribution h_01HFP4C4JDW2DRVVHXJ8ZAT9W5=click-through-attribution h_01HFP4C4JDTXJYH4S1EZ4HYJWG=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HFP4C4JDDWH23CVQMJNH2V70=view-through-attribution-lookback-window h_01HFP4C4JDYXBYAP5AYBN54A4B=impressions-attribution-link h_01HFP4C4JDP8NDDRHGXM0Y7XM7=cost-tab h_01HFP4C4JDBWCER854NDKTYRW8=ad-revenue-tab h_01HFP4C4JDRYYPW6W2PNA8J8P3=permissions-tab" />

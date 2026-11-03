---
title: DataLift campaign configuration
metadata:
  keywords:
    - Datalift Retargeting
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
  created_at: '2016-11-09T14:57:24Z'
  edited_at: '2026-10-13T01:07:55Z'
  id: 217752383
  locale: ko
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ko/articles/217752383
---
> **At a glance:** DataLift, an AppsFlyer ad network integrated partner, enables app marketers to programmatically access all major mobile ad inventory worldwide and control their campaigns through a single proprietary technology platform, providing advanced data integration and extended targeting and audience management capabilities. In addition to click-based mobile attribution, DataLift also offers retargeting, which you can record with AppsFlyer.

## Setting up DataLift

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

DataLift's configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partner

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation, click <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">here</Anchor>.

### General settings

### Default postbacks

Send automatic postbacks to DataLift following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to DataLift.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Datalift Retargeting.

### In-app events settings

In this section you can map your AppsFlyer events with DataLift via postbacks.

1. Enter the API\_KEY
2. Toggle In-App Event Postbacks to ON
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Datalift Retargeting's side.  <br />Obtain the corresponding Event ID from DataLift and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

In this tab, you can create the attribution links you want to send to Datalift Retargeting for attributing DataLift's campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with DataLift.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific DataLift campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Datalift Retargeting.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the subsite ID parameter, to avoid <Anchor target="_blank" href="/marketers/ko/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">**AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Retargeting settings

When enabled, AppsFlyer recognizes a link as a <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">retargeting</Anchor> attribution link, instead of a user acquisition link, by adding the `&is_retargeting=true` to the click recording link. Note that retargeting is currently only supported for click-through and not view-through attribution.  
**Attribution link parameter:** is\_retargeting.

The following setup below is displayed when retargeting is enabled.

1. Standard Link vs. OneLink

Select ***standard attribution link*** option if:

* You don't need to deep link with the URL or
* Plan to use only <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">URI schemes</Anchor> for deep linking

select ***Use OneLink*** for:

* Using a single link for both Android and iOS apps or
* Deep linking using Universal or app links

Note that selecting OneLink changes the click recording link from app specific to a <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">OneLink URL</Anchor>.

2. Deep Link URL

Use this field if the link is meant to deep link users to any specific activity within your app.  
**Attribution link parameter:** af\_dp  
You can find more information about AppsFlyer <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">deep linking solution in this guide.</Anchor>

3. Re-engagement Window

Set the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source. You can set the value in days (1-90), hours (up to 23), or even lifetime.

**Attribution link parameter:** af\_reengagement\_window

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to DataLift.

**Attribution link parameter:** af\_click\_lookback

More details about the <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">click lookback window here</Anchor>.

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to DataLift to be activated when leads click on a corresponding ad.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported by Datalift.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant DataLift, whether the partner acts as an ad network, agency, or both. Note that even if attribution is disabled for DataLift, the permissions tab is active and you can grant control to DataLift.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

Ad Network Permissions

* ***Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HKWB7DF793NT8G97RCFA873J=setting-up-datalift h_01HKWB7DF76EHWS5YRMEXTKQDA=integration-tab h_01HKWB7DF704T3BZ16JM5CHYTS=activate-partner h_01HKWB7DF7R0F7J1X6K5BSBEKC=general-settings h_01HKWB7DF70BY7JAG9NXVQ1DPC=default-postbacks inapp-events-settings=in-app-events-settings h_01HKWB7DF7ZE4HKCAHTPNJMPXS=in-app-events-settings h_01HKWB7DF7YNXFFGVWPDDJZTK8=attribution-link-tab h_01HKWB7DF759S8AKVV5RZWQZYG=attribution-link-parameters h_01HKWB7DF7B9BCYGGSXNAC0V4R=retargeting-settings clickthrough-attribution=click-through-attribution h_01HKWB7DF7NGNM5T8SD27PDC1D=click-through-attribution h_01HKWB7DF7D0WN8M0W7RQT7PJC=click-attribution-link h_01HKWB7DF8J8C5PGD257HTK9WD=cost-tab h_01HKWB7DF8X11EE3GTT4E62724=ad-revenue-tab h_01HKWB7DF8309PMXRHWK5HY83E=permissions-tab" />

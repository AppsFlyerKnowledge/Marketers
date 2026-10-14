---
title: "Hotstar campaign configuration"
excerpt: "Hotstar, an AppsFlyer integrated partner, is a major ad-supported streaming service in India."
x-zendesk:
  id: 360004428658
  url: https://support.appsflyer.com/hc/en-us/articles/360004428658-Hotstar-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  position: 2
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Campaign, configuration, integrated partner, Advertisers, hotstar, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2019-12-19T09:52:42Z'
  edited_at: '2026-09-09T13:40:16Z'
---
![](https://cdn.appsflyer.com/marketplace/static/logo/hotstar.png)

## Hotstar integration in AppsFlyer

**Prerequisite:** An account with the partner. If you don't have
an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to
   **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the
   **Activate partner** toggle.   
   **Note:** The toggle
   **must stay on (active) as long as you work with the partner**.
   [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn
   more about
   [partner integrations.](/docs/set-up-an-integrated-partner)

<Accordion title="Integration tab">

Connect to Hotstar by activating and setting parameters in the integration tab.

**To configure the integration**:

1. Enable **Activate partner.**
2. **Under** **General settings** **enable/disable** **View-through attribution:**
   * [Default] **Enable**: Activate to attribute view-through installs to Hotstar. The length of the lookback window is configured in the Attribution link tab.
   * **Disable**: View-through installs from the partner are not attributed.
3. **Default postbacks**: Send postbacks to Hotstar after the user installs the app. Only users attributed to Hotstar are reported.
4. **In-app events settings**: To send postbacks, map your in-app event IDs to Hotstar's in-app IDs. Configure the parameters as follows:
   * Enable **In-app events postbacks**.
   * Sending option: **Only events attributed to this partner** can be sent to Hotstar.
   * Click **Add event** to add an SDK event to the list. Complete the parameters as described in the following table.

| Setting name | Description |
| --- | --- |
| SDK event name | Event name received by AppsFlyer from:<ul><li>SDK integrated into the app</li><li>Server-to-server events</li></ul>**Tip:** If a needed event isn't in the list, perform a non-organic installation on a device, then check again. |
| Partner event identifier | Unique event name or ID as defined by Hotstar. Get from Hotstar event ID corresponding to your SDK event and insert it in the text field. |
| Send revenue | [Default] **Not enabled:** Send all the in-app parameters to Hotstar, except for the revenue parameter (`af_revenue`).<br /><br />**Enabled**: Send all the in-app parameters including, when available, the revenue amount. |

</Accordion>

<Accordion title="Attribution link tab">

Generate click and impression attribution links to be used by Hotstar. The following table explains the difference between click link and impression link, as well as the relevance of lookback windows.

| Attribution link type | Link activation | Lookback window |
| --- | --- | --- |
| Click | A lead clicks on an ad served by Hotstar | The **click-through** lookback window is the **maximum time from click to install**.<br /><br />Hotstar gets an attribution if a lead clicks and installs an app before the lookback window expires.<br /><br />**Parameter name**: `af_click_lookback`  <br />**Default value**: 7 days  <br />**Range:** 1-23 hours or 1-30 days |
| Impression | A lead views an ad (for at least 1 second) served by Hotstar | The **view-through** lookback window is the **maximum time from impression to install**.<br /><br />Hotstar gets an attribution if a lead views (impression) an app and then installs before the lookback window expires. This applies if there are no other relevant ad clicks.<br /><br />**Parameter name**: `af_viewthrough_lookback`  <br />**Default value**: 1 day  <br />**Range:** 1-23 hours or 1-7 days |

Learn more about[link structure and parameters](/docs/about-link-structure-and-parameters).

**Typical link parameters:**

| Parameter | Parameter name | Description |
| --- | --- | --- |
| Campaign | c | Name of the campaign |
| Ad set | af\_adset | Name of the ad set. Use to differentiate between ad sets within a campaign |
| Ad name | af\_ad | Name of the specific ad. Use to differentiate between creatives within an ad set |
| Site ID | af\_siteid  <br />af\_sub\_siteid | Publisher ID used to attribute installs to specific publishers.<br /><br />**Good practice!** If there are many publishers,<ul><li>Limit the number of site IDs in use.</li><li>Use the subsite ID parameter to avoid [exceeding the site ID limit](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit).</li></ul> |
| Subscriber parameters | af\_sub1 up to af\_sub5 | Use to insert values:<ul><li>Parameters are parsed and included in the raw data report.</li><li>Use them to perform data aggregation or filtering.</li></ul> |

**To generate the attribution links**:

1. Select a name from the **Parameter name** drop-down list, then set the parameter value.
2. To add more parameters, click **Add parameter** and repeat the previous step.
3. Set the duration of the click-through lookback window.
4. Set the duration of the view-through lookback window.
5. Copy the click and impression attribution links to use in your Hotstar campaigns.  
   **Note**: AppsFlyer does not save partner links.

</Accordion>

<Accordion title="Cost tab">

Cost attribution is not available for this partner.

</Accordion>

<Accordion title="Ad revenue tab">

Ad revenue attribution is not available for this partner.

</Accordion>

<Accordion title="Permissions tab">

You can give Hotstar permission to view information or configure changes in the integration. The type of permission varies according to the business relationship (ad network/ad agency) you have with Hotstar.

**Note**: It is possible to give Hotstar permissions even if there is no active integration with them.

#### Ad network permissions

**To enable ad network permissions**:

1. Enable **Ad network permissions**.
2. Give Hotstar team members access to one or more of the following:
   * **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks)
   * **Allow to configure in-app event postbacks** - permit the partner to map in-app event postbacks to itself on the integration tab
   * **Allow access to your retention report** - only to the partner's own retention data
   * **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data
   * **Allow access to your aggregate in-app events data** - only to the partner's own in-app events data
   * **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner
   * **Allow spend ingestion** - is at the app level.
   * **Allow access to your Protect360 dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser.

</Accordion>

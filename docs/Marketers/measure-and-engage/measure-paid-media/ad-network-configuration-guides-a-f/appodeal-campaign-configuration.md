---
title: "Appodeal campaign configuration"
excerpt: "Appodeal, an AppsFlyer integrated partner, provides app owners with click attribution and an all-in-one ad monetization solution. Ad revenue is reported with user-level granularity."
x-zendesk:
  id: 360004404977
  url: https://support.appsflyer.com/hc/en-us/articles/360004404977-Appodeal-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  position: 11
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [ad revenue, cost, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2019-12-17T19:36:02Z'
  edited_at: '2026-06-16T09:48:54Z'
---
## Setting up Appodeal integration

![](https://cdn.appsflyer.com/marketplace/static/logo/appodeal.png)

AppsFlyer integration with Appodeal supports click attribution and [user-level ad revenue attribution.](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data)

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below:

### Integration

Configure this section if Appodeal provides ad network advertising services.

**To enable the integration**:

1. Enable **Activate Partner.**
2. Click **Save Integration**.

### Attribution link

Generate click attribution links (for use by Appodeal) via this tab. [More about link structure and parameters](/docs/about-link-structure-and-parameters)**.**

**To generate an attribution link**:

1. Select a parameter from the Parameter name drop-down list and set a value.
2. Click **Add parameter** and repeat the above step to add more parameters.
3. Set the duration of the **click-through lookback window.**
4. Copy the click-attribution link and send it to the ad network.  
   Note: AppsFlyer does not save links.

**Attribution link and lookback window**



| Attribution link type | Link activation | Lookback window |
| --- | --- | --- |
| Click | A user clicks on an ad served by the ad network | **The Click-through lookback** window is preset; it is the **maximum allowed time from click to install**.<br /><br />Example: An install (first launch) made after the click—but before the expiry of the lookback window—is attributed to Appodeal.<br /><br />**Parameter name**: `af_click_lookback`  <br />**Default value**: 7 days  <br />**Range:** 1-23 hours or 1-30 days |



**Typical link parameters**



| Parameter | Parameter name | Description |
| --- | --- | --- |
| Campaign | c | Name of the campaign |
| Adset | af\_adset | Use to differentiate add sets. |
| Ad name | af\_ad | Use to differentiate between creatives within the add set. |
| Site ID | af\_siteid  <br />af\_subsiteid | Use to attribute installs to specific publishers.<br /><br />**Good practice!** If there are multiple publishers,<br /><br />* Limit the number of site IDs in use<br />* Use the subsite ID parameter to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitation |
| Subscriber parameters | af\_sub1, af\_sub2, af\_sub3, af\_sub4, and af\_sub5 | Use to insert values.<br /><br />* Parameters are parsed and included in the raw data report.<br />* Use them to perform data aggregation or filtering |



### Cost

Appodeal sends CPI cost data via the attribution link.

### Ad revenue

* Appodeal provides ad revenue mediation with [user-level granularity](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data)
* Learn more about [AppsFlyer ad revenue attribution](/docs/roi360-guide-ad-revenue-attribution)

**To enable the ad revenue API**:

* Follow [these integration instructions](/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners).

### Permissions

No permissions need to be set for Appodeal.
---
title: Appodeal campaign configuration
metadata:
  keywords:
    - ad revenue
    - cost
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
  created_at: '2019-12-17T19:36:02Z'
  edited_at: '2026-06-16T09:48:54Z'
  id: 360004404977
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360004404977-Appodeal-campaign-configuration
---
> **At a glance:** Appodeal, an AppsFlyer integrated partner, provides app owners with click attribution and an all-in-one ad monetization solution. Ad revenue is reported with user-level granularity.

## Setting up Appodeal integration

![](https://cdn.appsflyer.com/marketplace/static/logo/appodeal.png)

AppsFlyer integration with Appodeal supports click attribution and <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">user-level ad revenue attribution.</Anchor>

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below:

<div id="integration" />

<Accordion title="Integration">

Configure this section if Appodeal provides ad network advertising services.

**To enable the integration**:

1. Enable **Activate Partner.**
2. Click **Save Integration**.

</Accordion>

<div id="attribution-link" />

<Accordion title="Attribution link">

Generate click attribution links (for use by Appodeal) via this tab. <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">More about link structure and parameters</Anchor>.

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
| Site ID | af\_siteid  <br />af\_subsiteid | Use to attribute installs to specific publishers.<br /><br />**Good practice!** If there are multiple publishers,<ul><li>Limit the number of site IDs in use</li><li>Use the subsite ID parameter to avoid <Anchor target="_blank" href="/marketers/vi/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceeding the site ID</Anchor> limitation</li></ul> |
| Subscriber parameters | af\_sub1, af\_sub2, af\_sub3, af\_sub4, and af\_sub5 | Use to insert values.<ul><li>Parameters are parsed and included in the raw data report.</li><li>Use them to perform data aggregation or filtering</li></ul> |

</Accordion>

<div id="cost" />

<Accordion title="Cost">

Appodeal sends CPI cost data via the attribution link.

</Accordion>

<div id="ad-revenue" />

<Accordion title="Ad revenue">

* Appodeal provides ad revenue mediation with <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">user-level granularity</Anchor>
* Learn more about <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution">AppsFlyer ad revenue attribution</Anchor>

**To enable the ad revenue API**:

* Follow <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">these integration instructions</Anchor>.

</Accordion>

<div id="permissions" />

<Accordion title="Permissions">

No permissions need to be set for Appodeal.

</Accordion>

<div data-zendesk-anchors="h_01HKW9BK4ZAR4Q22Z9WBVFPPT7=setting-up-appodeal-integration h_01HKW9BK4ZDFDX9X7P2HW4QR1P=integration h_01HKW9BK4ZM4JMQKT4Y8ZC050V=attribution-link h_01HKW9BK4ZV8DWSZQ55332NQWY=cost h_01HKW9BK4ZS3GYMZ6E9T64PPGC=ad-revenue h_01HKW9BK4ZJ1F1Z099NJHRZRNE=permissions" />

---
title: "Appodeal campaign configuration"
excerpt: "Learn how to set up AppsFlyer integration with Appodeal for click attribution and user-level ad revenue attribution."
---
Appodeal, an AppsFlyer integrated partner, provides app owners with click attribution and an all-in-one ad monetization solution. Ad revenue is reported with user-level granularity.

## Setting up Appodeal integration

AppsFlyer integration with Appodeal supports click attribution and [user-level ad revenue attribution.](https://support.appsflyer.com/hc/articles/217490046#ad-revenue-raw-data)

> 📘 Prerequisite
>
> An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 🚧 Important
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below:

### Integration

Configure this section if Appodeal provides ad network advertising services.

**To enable the integration**:

1. Enable **Activate Partner.**
2. Click **Save Integration**.

### Attribution link

Generate click attribution links (for use by Appodeal) via this tab. [More about link structure and parameters](https://support.appsflyer.com/hc/articles/207447163) **.**

**To generate an attribution link**:

1. Select a parameter from the Parameter name drop-down list and set a value.
2. Click **Add parameter** and repeat the above step to add more parameters.
3. Set the duration of the **click-through lookback window.**
4. Copy the click-attribution link and send it to the ad network.

> 📘 Note
>
> AppsFlyer does not save links.

**Attribution link and lookback window**

| Attribution link type | Link activation | Lookback window |
| --- | --- | --- |
| Click | A user clicks on an ad served by the ad network | **The Click-through lookback** window is preset; it is the **maximum allowed time from click to install**.<br>Example: An install (first launch) made after the click—but before the expiry of the lookback window—is attributed to Appodeal.<br>**Parameter name**: `af_click_lookback `<br>**Default value**: 7 days<br>**Range:** 1-23 hours or 1-30 days |

**Typical link parameters**

| Parameter | Parameter name | Description |
| --- | --- | --- |
| Campaign | c | Name of the campaign |
| Adset | af\_adset | Use to differentiate add sets. |
| Ad name | af\_ad | Use to differentiate between creatives within the add set. |
| Site ID | af\_siteid<br>af\_subsiteid | Use to attribute installs to specific publishers.<br>**Good practice!** If there are multiple publishers,<br>- Limit the number of site IDs in use<br>- Use the subsite ID parameter to avoid [exceeding the site ID](https://support.appsflyer.com/hc/articles/115005099063-What-are-the-Exceeded-Media-Sources-#exceeded_siteid_limit) limitation |
| Subscriber parameters | af\_sub1, af\_sub2, af\_sub3, af\_sub4, and af\_sub5 | Use to insert values.<br>- Parameters are parsed and included in the raw data report. <br>- Use them to perform data aggregation or filtering |

### Cost

Appodeal sends CPI cost data via the attribution link.

### Ad revenue

* Appodeal provides ad revenue mediation with [user-level granularity](https://support.appsflyer.com/hc/articles/217490046#ad-revenue-raw-data)
* Learn more about [AppsFlyer ad revenue attribution](https://support.appsflyer.com/hc/articles/217490046-Ad-Revenue-Attribution)

**To enable the ad revenue API**:

* Follow [these integration instructions](https://support.appsflyer.com/hc/articles/217490046-Ad-revenue-attribution-guide#connect-to-ad-revenue-integrated-partners).

### Permissions

No permissions need to be set for Appodeal.
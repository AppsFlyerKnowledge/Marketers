---
title: Vungle campaign configuration
excerpt: >-
  Vungle, an AppsFlyer ad network integrated partner, offers an in-app video
  advertising platform for performance marketers. In addition to click-based
  mobile attribution, Vungle offers cost and view-through attribution, which can
  be recorded with AppsFlyer.
metadata:
  keywords:
    - Vungle
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2016-03-03T08:53:29Z'
  edited_at: '2026-09-08T07:18:37Z'
  id: 207990186
  locale: en-us
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207990186-Vungle-campaign-configuration
---
![](https://cdn.appsflyer.com/marketplace/static/logo/vungle.png?v=1)

## Setting up Vungle

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

> 📘 **Tip**
>
> * The [General Settings](/docs/set-up-an-integrated-partner#d-general-settings) step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration tab is divided into different sections as described below.

### Activate partners

Connect to Vungle by activating and setting parameters in the integration tab. Vungle must supply its unique network ID, ***app\_id***; this is necessary in order to connect with AppsFlyer.

> 📘 **Note**
>
> As an all-installs network, Vungle prefers to receive postbacks for all new installs of your app from any source, and they recommend selecting **All media sources, including organic** to send all install postbacks to Vungle.

**To configure the integration**:

1. Enable ***Activate partner***. See more information about [partner activation](/docs/partner-activation-deactivation).
2. **Under *General settings* enable/disable *View-through attribution*:**
   * [Default] **Enable**: Activate to attribute view-through installs to Vungle. The length of the lookback window is configured in the Attribution link tab.
   * **Disable**: View-through installs from the partner are not attributed.
3. ***Default postbacks***: Send postbacks to Vungle after user installs and re-engagements. Use this section to define users who are the source of these postbacks. Under ***Sending Option***,

   * Select **Only events attributed to this partner** for events attributed to Vungle users.
   * Select **Events attributed to any partner or organic** to make your entire user available for reporting to Vungle.
4. ***I**n-app events settings***: To send postbacks to Vungle, map in-app event IDs to Vungle’s. Configure the parameters as follows:
   * Enter the Vungle app\_id.
   * Enable ***In-app events postbacks***.
   * Select a ***Sending Option***.
   * Click ***Add event*** to add an SDK event to the list. Complete the parameters as described in the following table.

| Parameter Name | Description |
| --- | --- |
| **SDK event name** | Event name received by AppsFlyer from:<ul><li>SDK integrated in the app</li><li>Server-to-server events</li></ul>**Tip:** If a needed event isn’t on the list, perform a non-organic installation on a device, then check again. |
| **Partner event identifier** | Unique event name or ID as defined by Vungle.<br /><br />Get from Vungleevent ID corresponding to your SDK event and insert it in the text field. |
| **Send revenue** | [Default] **Not enabled:** sends all the in-app parameters to Vungle, except for the revenue parameter (`af_revenue`).<br /><br />**Enabled**: sends all the in-app parameters including, when available, the revenue amount. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).  

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

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

This section is relevant if you are acting as a publisher, displaying ads of the partner to your users. As such, you would certainly like to measure the engagement of your users acquired from different sources, to find the most profitable sources for you.

**To enable the ad revenue API**:

* Follow [these integration instructions](/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners).

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

You can give Vungle permission to view information or configure changes in the integration. The type of permission varies according to the business relationship (ad network/ad agency) you have with Vungle.

**Note**: It is possible to give Vungle permissions even if there is no active integration with them.

### Ad network permissions

**To enable ad-network permissions:**

1. Enable ***Ad network permissions***.
2. Give Vungle team members access to one or more of the following:

| **Allow to configure integration** | Set up the integration tab (except in-app event postbacks). |
| --- | --- |
| Allow to configure in-app event postbacks | Set up in-app event postbacks that are mapped to Integration tab. |
| Allow access to your retention report | Partner’s retention data |
| Allow access to your aggregate loyal users data | Partner’s loyal-user data |
| Allow access to your aggregate in-app events data | Partner’s in-app events data |
| Allow access to your aggregate revenue data | Revenue data attributed to the partner. |
| Allow spend ingestion |  |
| Allow access to your Protect360 dashboard | [If enabled] Partner’s Protect360 data |

Learn more about giving [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

### Agency permissions

You can allow Vungle to configure your app as an agency.

**To enable agency permissions:**

1. Enable ***Agency*** **permissions**.
2. Give Vungle agency access to one or more of the following:

| **Allow access to your Protect360 dashboard** | [If enabled for your account] Agency’s Protect360 data |
| --- | --- |
| **Allow access to your retention and cohort reports** | Agency’s retention and cohort data |
| **Allow access to aggregate organic data** | Agency’s aggregate organic data |
| **Allow to configure in-app event postbacks** | Set up in-app event postbacks that are mapped to the integration tab. |

Learn more about granting [agency permissions](/docs/set-up-an-integrated-partner#agency-permissions).

</Accordion>

<div data-zendesk-anchors="h_01HJZVD66Q6ZBPGEASQTAQNH3G=setting-up-vungle h_01HJZVD66QE7BTR3F5QKJZFPMD=tip h_01HJZVD66QDTZAG9GD153SM2AG=integration-tab h_01HJZVD66QG7FHRCEAT7WX7E1R=activate-partners h_01HJZVD66Q9HB72WQM5Y4S60FN=note h_01HJZVD66Q5HGF9GWKHB87GK2Y=attribution-link-tab h_01HJZVD66R0XX4DB12R25Y3PXM=cost-tab h_01HJZVD66SNVAHYSSFN2RMWHZX=ad-revenue-tab h_01HJZVD66SJT203JAYDQQ29ZEC=permissions-tab h_01HJZVD66S4680GJ0A9SFSGY4Z=ad-network-permissions h_01HJZVD66SC6KK9KWHR6WQYGR3=agency-permissions" />

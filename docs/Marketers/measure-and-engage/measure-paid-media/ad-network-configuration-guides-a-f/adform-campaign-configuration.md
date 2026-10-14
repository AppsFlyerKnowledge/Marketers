---
title: Adform campaign configuration
excerpt: >-
  Adform, an AppsFlyer ad network integrated partner, provides open and
  transparent technologies that connect advertisers and agencies with publishers
  to enable digital advertising across all devices. In addition to click-based
  mobile attribution, Adform also offers view-through attribution, which you can
  record with AppsFlyer.
metadata:
  keywords:
    - adform
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2016-05-01T07:23:12Z'
  edited_at: '2026-06-16T12:03:12Z'
  id: 208641516
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/208641516-Adform-campaign-configuration
---
## Setting up Adform

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

Adform configuration window includes 2 active tabs: **Integration** and **Attribution link**. Click on the items below to read about the tab setup.

> 📘 **Tip**
>
> * The [General Settings](/docs/set-up-an-integrated-partner#d-general-settings) step in the Integration tab is **mandatory** for all partners
> * All the rest of the steps are either descriptive or **optional**

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

> 📘 **Note**
>
> As an ALL-Installs network, Adform prefers to receive postbacks for all new installs of your app from ANY source, including organic. It is recommended to select **Events attributed to any partner** to send all install postbacks to Adform.

### General settings

**Client Tracking ID**

Adform connects with AppsFlyer via a unique Client Tracking ID. If you don't already have it, you must obtain it from Adform to continue with the integration.

![adform_msc_new_2.png](https://files.readme.io/d3d72b295a6d3bdc7f097128a6399bd4cd60309118750b4e2217a2b01ca5362a-360002140925.png)

**Enable View-Through attribution**

Toggle this to ON if you want to attribute view-through installs from Adform. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

Send automatic postbacks to Adform following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Adform.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Adform.

### In-app events settings

In this section you can map your AppsFlyer events with Adform via postbacks.

1. Enter the Client\_Tracking\_ID and password again.
2. Toggle In-App Event Postbacks to ON
3. Select the Sending Option for all SDK defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Adform's side.  <br />Obtain the corresponding Event ID from Adform and set in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).

[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

There are no permissions to be granted Adform.

</Accordion>

<div data-zendesk-anchors="h_01HJR630HMJCK05KSJ1P57KJD1=setting-up-adform h_01HJR630HMXT2T93RH2DZ709Z6=tip h_01HJR630HMT23996KHW0Z2Z9BT=integration-tab h_01HJR630HM3QQVARD5YN3WG6D4=activate-partner h_01HJR630HMR742Z6N1HWFGDM4Z=note h_01HJR630HMYXE1R9WBDBBV5K39=general-settings h_01HJR630HMHMC5WP2F4CYP8GG0=default-postbacks inapp-events-settings=in-app-events-settings h_01HJR630HM4XGH1DYSHYH7EPQ4=in-app-events-settings h_01HJR630HM00A090TQNW6Z11RY=attribution-link-tab h_01HJR630HMP3AE90YEWNVHN19Q=cost-tab h_01HJR630HMSE5DFR6Y4T3TP34C=ad-revenue-tab h_01HJR630HMF4ZJFNX6RAGT8PJA=permissions-tab" />

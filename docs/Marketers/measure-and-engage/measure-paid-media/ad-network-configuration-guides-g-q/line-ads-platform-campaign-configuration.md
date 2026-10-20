---
title: LINE Ads Platform campaign configuration
excerpt: >-
  LINE Ads Platform, an AppsFlyer integrated partner combines a bidding and
  customized targeting system. In addition to click-based mobile attribution,
  LINE Ads Platform also offers retargeting attribution, which you can record
  with AppsFlyer.
metadata:
  keywords:
    - Advertisers
    - LINE Ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-10T15:26:17Z'
  edited_at: '2026-09-09T13:00:38Z'
  id: 213050543
  locale: en-us
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/213050543-LINE-Ads-Platform-campaign-configuration
---
![](https://cdn.appsflyer.com/marketplace/static/logo/lap.png)

## Setting up LINE Ads platform

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

The Integration Tab is divided into different sections as described below.

> 📘 **Note**
>
> As an ALL-Installs network, LINE prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to LINE. This can only be performed by the account owner.

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### General settings

**Account ID and App ID**

LINE Ads Platform connects with AppsFlyer via a unique account and app ID, LINE\_Ad\_account\_id, and LINE\_Ad\_app\_ID.  
**To connect your LINE Ads account to AppsFlyer:**

* Enter your unique **LINE\_Ad\_account\_id** and your **LINE\_Ad\_app\_ID**.   
  See [Line Line Ads documentation on creating a business ID](https://lineforbusiness.com/th-en/service/line-ads/manual#Tracking:~:text=Tracking%20app%20conversions).

#### Connect multiple accounts and apps

You can connect multiple Line Ads accounts and apps to AppsFlyer by manually adding an account ID or app ID parameter to an attribution link, after its creation.

> 📘 **Note**
>
> Parameters existing in both the attribution link and under the **General settings** lead to conflicts. To avoid this, see the **Parameter priority logic** described below before adding parameters to the attribution link.

**Parameter priority logic**

* When both parameter types, account ID and app ID (line\_ad\_account\_id, line\_ad\_app\_id), are included in the attribution link, any corresponding ID set in the General settings gets overridden.
* When one of the parameter types is missing from the attribution link but has been set in the General settings, the value set in the general settings will be included for the connection.
* When both parameter types, account ID and app ID, are missing from the General settings and attribution links, the integration may not function as intended.

**To connect multiple account ID and app ID parameters:**

1. Set up one or more [attribution links](/docs/about-link-structure-and-parameters).
2. Add to each attribution link an account ID and app ID parameter, using lower-case letters. See the highlighted part in the example below.

> 📘 **Example**
>
> An example attribution link with an account ID and app ID parameters:
>
> ```
> https://app.appsflyer.com/id123456789?pid=example_int;...line_ad_account_id=A123456789123&line_ad_app_id=1234567891234&...;redirect=false
> ```

### Default postbacks

Send automatic postbacks to LINE Ads Platform following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to LINE Ads Platform.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to LINE Ads Platform.

### In-app events settings

In this section you can map your AppsFlyer events with LINE Ads Platform via postbacks.

1. Enter the LINE\_Ad\_app\_ID and LINE\_Ad\_account\_id again.
2. Toggle In-App Event Postbacks to ON.
3. Select the Sending Option for all SDK-defined events.  
   **- Only events attributed to this partner** for events coming **only** from users attributed to this partner  
   **- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. From the dropdown list select an ***SDK Event Name***.
5. From the ***Partner Event Identifier***dropdown list, select the corresponding option.
6. Click ***Add Event***to add additional Event Names.
7. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated with your app or from server to server events.  <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on LINE Ads Platform's side.  <br />Obtain the corresponding Event ID from LINE Ads Platform and set it in the text field. |
| **Send Revenue** | **When unchecked** - Send all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.  <br />**When checked** - Send all the parameters including the revenue value (if it exists in the event). |

### Custom in-app events mapping

AppsFlyer allows you to map any custom in-app event to send to LINE, by using the CUSTOM Partner Event Identifier option.

The event name and the event value (including the event parameters) configured in the SDK are forwarded to LINE, as is.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

[Follow these instructions](https://lineforbusiness.com/th-en/service/line-ads/manual) to activate the attribution link in LINE Ads Platform.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported by this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported by this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

No permission configurations are available for LINE Ads Platform.

</Accordion>

<div data-zendesk-anchors="h_01HKW2TJ83EZSV30XH3CM0HHB7=setting-up-line-ads-platform h_01HKW2TJ83RG7W6F2PZMAY7BXZ=integration-tab h_01HKW2TJ83VEK727ZH9FPH6TPJ=note h_01HKW2TJ83VPWD1GK99S4MY3ZB=activate-partner h_01HKW2TJ83PFS3TCPHKZ9HY5PE=general-settings h_01JAA89AWAQ4JZS3522EVZZN8D=connect-multiple-accounts-and-apps 01JB6YF9SFD2TWTZGR0RPVEBTC=note-1 01JAT9SYW9C06P185S9TWKAFM0=example h_01HKW2TJ838FFTAR7NQC9WX295=default-postbacks inapp-events-settings=in-app-events-settings h_01HKW2TJ833VC6SGSRNJSZ53WR=in-app-events-settings custom-inapp-events-mapping=custom-in-app-events-mapping h_01HKW2TJ83GQ7SFKV6YPM49QP1=custom-in-app-events-mapping h_01HKW2TJ83JPB6DSW8Z5PCY1SC=attribution-link-tab h_01HKW2TJ839R8NS3PFHCAJGXTZ=cost-tab h_01HKW2TJ835JT0WD3GN4H3XHT5=ad-revenue-tab h_01HKW2TJ83MPGHKGEMDQQYGGJ1=permissions-tab" />

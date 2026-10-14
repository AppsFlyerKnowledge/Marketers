---
title: "MoEngage campaign configuration"
excerpt: "MoEngage, a third-party customer engagement platform integrated with AppsFlyer, is an agentic customer engagement platform built for the mobile-first world."
x-zendesk:
  id: 115003139643
  url: https://support.appsflyer.com/hc/en-us/articles/115003139643-MoEngage-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 21
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [MoEngage, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2017-06-25T07:50:18Z'
  edited_at: '2026-07-07T09:25:09Z'
---
> 📘 **Important!**
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up MoEngage

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

Learn more about [setting the partner page header.](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page)

<div id="integration-tab" />

<Accordion title="Integration tab">

The **Integration** tab is divided into different sections, as described below.

### Activate partner

On your first visit, turn **Activate Partner** on to set up the integration. The toggle must be on for as long as you work with the partner. Learn more about [partner activation](/docs/partner-activation-deactivation).

### General settings

MoEngage connects with AppsFlyer via a unique App ID, App Key, and the Data Center of MoEngage. If you don't already have the App ID and App Key, you must obtain the first to continue with the integration:

* **APP\_ID:** Enter the app ID. To obtain it, log in to your MoEngage account from the left menu, and go to **Settings** > **App Settings**.
* **MoEngage Data Center:** Specify the MoEngage data center that you have signed up with. Learn more about [Data Centers in MoEngage](https://help.moengage.com/hc/en-us/articles/360057030512-Data-Centers-in-MoEngage).
* **APP\_KEY:** Enter the app API key. To obtain it, log in to your MoEngage account, and go to **Settings** > **Analytics**.

![moengage_general_settings_en-us.png](https://files.readme.io/0180fb4ad22857320200b1f53a01c72c87fc6cc4a3f4aabcd585b2cfb0f7596a-8179576817809.png)

### Default postbacks

AppsFlyer can send automatic postbacks to MoEngage following user installs. Select one of the following options:

* **Off**: Don't send any install postbacks.
* **All media sources, including organic**: Send postbacks for events attributed to any partner and for organic events.

![web_mo_engage_default_postbacks_en-us.png](https://files.readme.io/9be309d681904a015fc0295b2ee463411f5c8fbaf450145b132e8ab37bda7665-17028057319697.png)

> 📘 **Note**
>
> As an all-installs network, MoEngage prefers to receive postbacks for all new installs of your app from any source, including organic. MoEngage recommends selecting **All media sources, including organic**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

**Attribution link** isn't supported in the integration with this partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

**Cost data** isn't supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

**Ad revenue** isn't supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

**Permissions** isn't supported in the integration with this partner.

</Accordion>

<div data-zendesk-anchors="h_01H9HWJPMX1TXBZY6C94HQ7J85=important h_01H9HWJPMXN58VV9SQQPY4T5HZ=setting-up-moengage h_01H9HWJPMX946NS52DTPAZWVEK=integration-tab h_01H9HWJPMX46NV79HHGRRD6D56=activate-partner h_01H9HWJPMXPZ5QV9D08CJMHMHS=general-settings h_01H9HWJPMX0TZ496PP8EY3H336=default-postbacks h_01H9HWJPMX4CHJ9MADEQBSDMGY=note h_01H9HWJPMXJVWPK67W5X88GYHZ=attribution-link-tab h_01H9HWJPMXQ07XNN8Y79P5DCAN=cost-tab h_01H9HWJPMX8MC1GSD2VD3QQ82Y=ad-revenue-tab h_01H9HWJPMXKYXVCH3HRA2FCPSQ=permissions-tab" />

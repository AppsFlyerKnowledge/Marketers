---
title: Spotify campaign configuration
metadata:
  keywords:
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
  created_at: '2020-11-05T07:36:01Z'
  edited_at: '2026-06-16T10:01:47Z'
  id: 360015074677
  locale: en-us
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360015074677-Spotify-campaign-configuration
---
> **At a glance:** Spotify, an AppsFlyer ad network integrated partner, uses its enhanced mobile advertising solution to cultivate strategic, scalable, and smart campaigns to meet the needs of mobile users. In Spotify, clicks are generated when a user clicks on a CTA button while watching or hearing an ad.

<Image alt="Spotify_Full_Logo_RGB_Black.png" src="https://files.readme.io/e3908e19ec71c506c2ff135652cea6529f128743d8284c02c1a481f24485b3a6-small-37818004235409.png" width="53.91%" />

<div id="setting-up-spotify" />

## Setting up Spotify

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

Learn more about the <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">partner configuration window header</Anchor>.

Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation#activate-a-partner-integration">partner activation rules</Anchor>.

<div id="important" />

> 🚧 **Important**
>
> * The <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#d-general-settings">general settings</Anchor> step in the Integration tab is **mandatory** for all partners.
> * All the rest of the steps are either descriptive or **optional.**

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration tab is divided into different sections as described below.

<div id="general-settings" />

### General settings

**Enable view-through attribution**

If you want to attribute view-through installs from Spotify, enable this toggle. To set the view-through lookback window, go to the attribution link tab (described below).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Spotify has a server-to-server integration with AppsFlyer, so attribution links are not used for campaign measurement. When you select your app as the conversion measurement source during Spotify campaign setup, the AppsFlyer integration will automatically be activated, and Spotify will send AppsFlyer impression and click data with the necessary identifiers for attribution.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost integration is not available for Spotify.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue is not available for Spotify.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Spotify, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Spotify, the permissions tab is active and you can grant control to Spotify.

After you enable granting permissions to Spotify, you can add team members to grant them access to the data according to the selected permissions.  
Permissions can be granted only to Spotify employees who have an ad network team member account on AppsFlyer.  
**To grant permissions to ad network team members:**

1. Click **Add team member.**
2. Enter the ad network team member's email.
3. Click **Add**.

<div id="important-1" />

> 🚧 **Important!**
>
> * When you give Spotify permissions to configure the integration and to change in-app event postbacks, you allow them to potentially access all attribution events, including organic and non-organic traffic from all media sources.
> * Changes that Spotify makes override the current configuration, even if set by the advertiser.

The following are the permissions types that advertisers can grant Spotify:

* **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks).
* **Allow to configure in-app event postbacks** - permit the partner to set up in-app event postbacks mapping to itself on the integration tab.
* **Allow access to your retention report** - only to the partner's own retention data.
* **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data.
* **Allow access to your aggregate in-app events data** - only to the partner's own in-app events data.
* **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner.
* **Allow access to your Protect360 dashboard & raw data via API** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser.

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJS1DB7YV8T6RNXH1JRNTGDN=setting-up-spotify h_01HJS1DB7YKBY0Q7GY7QT9DHKZ=important h_01HJS1DB7YQKM7DRR0MJGHX95G=integration-tab h_01HJS1DB7YEQZ7JQ0T2NWFBQBM=general-settings h_01HJS1DB7YHN0PCMFWQ9SZKE27=attribution-link-tab h_01HJS1DB7ZVSQCYJZENWJ9G77H=cost-tab h_01HJS1DB7Z03PTQSQB0JVJEFY0=ad-revenue-tab h_01HJS1DB7Z6CBDQFVNC75X2Z6Z=permissions-tab h_01HJS1DB7ZPZET71JAZ8E4CZ7S=important-1" />

---
title: "Spotify campaign configuration"
excerpt: "Spotify, an AppsFlyer ad network integrated partner, uses its enhanced mobile advertising solution to cultivate strategic, scalable, and smart campaigns to meet the needs of mobile users. In Spotify, clicks are generated when a user clicks on a CTA button while watching or hearing an ad."
x-zendesk:
  id: 360015074677
  url: https://support.appsflyer.com/hc/en-us/articles/360015074677-Spotify-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  position: 8
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2020-11-05T07:36:01Z'
  edited_at: '2026-06-16T10:01:47Z'
---
![Spotify_Full_Logo_RGB_Black.png](https://files.readme.io/e3908e19ec71c506c2ff135652cea6529f128743d8284c02c1a481f24485b3a6-small-37818004235409.png)

## Setting up Spotify

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below.

Learn more about the [partner configuration window header](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

Learn more about [partner activation rules](/docs/partner-activation-deactivation#activating-a-partner).

> ❗️ Important
>
> - The [general settings](/docs/set-up-an-integrated-partner#d-general%20settings) step in the Integration tab is **mandatory** for all partners.
> - All the rest of the steps are either descriptive or **optional.**

## Integration tab

The Integration tab is divided into different sections as described below.

### General settings

**Enable view-through attribution**

If you want to attribute view-through installs from Spotify, enable this toggle. To set the view-through lookback window, go to the attribution link tab (described below).

## Attribution link tab

Spotify has a server-to-server integration with AppsFlyer, so attribution links are not used for campaign measurement. When you select your app as the conversion measurement source during Spotify campaign setup, the AppsFlyer integration will automatically be activated, and Spotify will send AppsFlyer impression and click data with the necessary identifiers for attribution.

## Cost tab

Cost integration is not available for Spotify.

## Ad revenue tab

Ad revenue is not available for Spotify.

## Permissions tab

In this tab, you can select the permissions to grant Spotify, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for Spotify, the permissions tab is active and you can grant control to Spotify.

After you enable granting permissions to Spotify, you can add team members to grant them access to the data according to the selected permissions.

Permissions can be granted only to Spotify employees who have an ad network team member account on AppsFlyer.

**To grant permissions to ad network team members:**

1. Click **Add team member.**
2. Enter the ad network team member's email.
3. Click **Add**.

> ❗️ Important!
>
> - When you give Spotify permissions to configure the integration and to change in-app event postbacks, you allow them to potentially access all attribution events, including organic and non-organic traffic from all media sources.
> - Changes that Spotify makes override the current configuration, even if set by the advertiser.

The following are the permissions types that advertisers can grant Spotify:

- **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks).
- **Allow to configure in-app event postbacks** - permit the partner to set up in-app event postbacks mapping to itself on the integration tab.
- **Allow access to your retention report** - only to the partner's own retention data.
- **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data.
- **Allow access to your aggregate in-app events data** - only to the partner's own in-app events data.
- **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner.
- **Allow access to your Protect360 dashboard & raw data via API** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser.

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).
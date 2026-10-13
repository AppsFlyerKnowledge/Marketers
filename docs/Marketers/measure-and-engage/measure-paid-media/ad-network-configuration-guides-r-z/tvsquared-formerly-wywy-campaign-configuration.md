---
title: "TVSquared (formerly Wywy) campaign configuration"
excerpt: "Learn how to configure the TVSquared (formerly Wywy) integration in AppsFlyer to measure and optimize your campaigns."
x-zendesk:
  id: 213836263
  url: https://support.appsflyer.com/hc/en-us/articles/213836263-TVSquared-formerly-Wywy-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  position: 15
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Advertisers, TV Squareed, Wywy, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-09-06T08:58:47Z'
  edited_at: '2026-06-16T09:45:39Z'
---
At a glance: TVSquared (formerly Wywy), an AppsFlyer ad network integrated partner, enables the entire digital organization - marketers, product managers, and data scientists - to run the business based on data. TVSquared creates an integrated view of consumers across devices, providing tools to optimize the user experience in real-time.

## Setting up TVSquared

> 📘 Prerequisite
>
> An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

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

> 📘 Note
>
> For TVSquared you need to complete the Integration tab. The remaining tabs are not applicable to TVSquared.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

1. Enable _**Activate Partner**_.

The Integrations parameters display.

For more details about partner activation please click [here](/docs/partner-activation-deactivation).
2. Complete the General Setting fields:
   - _**SITEID**_: Fill in the SITEID you obtained from TVSquared.
   - _**COLLECTORID**_: Fill in the COLLECTORID obtained from TVSquared.
3. **Default Postbacks**: AppsFlyer sends postbacks to TVSquared after the user installs/re-engagement. Select the Sending Option for which the partner will get postbacks:
   - **Events attributed to any partner or organic**:All installs, irrespective of source, are reported to TVSquared
   - **Off**
4. Complete in-app events settings fields:

- _**SITEID**_: Fill in the SITEID you obtained from TVSquared.
- _**COLLECTORID**_: Fill in the COLLECTORID obtained from TVSquared.
- **customerid:** (optional) You can leave this field blank.
- (optional) Enable _**In-App Events Postback**_: Map your in-app events with TVSquared using postbacks. Configure the parameters as follows:
  - Click Add Event to add an SDK event to the list and complete the parameters.
- Click **Save integration.**

#### Note

According to both Meta ads and X Ads terms and conditions, AppsFlyer can't share user-level data with any 3rd party. Therefore, all Meta ads and X Ads installs are sent to TVSquared as organic.

For details on sharing data with 3rd parties, click [here](/docs/user-level-data-retention).

## Attribution link tab

Attribution Links are not available for TVSquared.

## Cost tab

Cost data is not supported in the integration with this partner.

## Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

## Permissions tab

Permissions are not available for TVSquared.
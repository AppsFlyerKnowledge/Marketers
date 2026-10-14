---
title: "TVSquared (formerly Wywy) campaign configuration"
excerpt: "TVSquared (formerly WyWy), an AppsFlyer ad network integrated partner, enables the entire digital organization - marketers, product managers, and data scientists - to run the business based on data. TVSquared creates an integrated view of consumers across devices, providing tools to optimize the user experience in real-time."
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
## Setting up TVSquared

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

**Note:** For TVSquared you need to complete the Integration tab. The remaining tabs are not applicable to TVSquared.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

1. Enable ***Activate Partner***.  
   The Integrations parameters display.  
   For more details about partner activation please click [here](/docs/partner-activation-deactivation).
2. Complete the General Setting fields:
   * ***SITEID***: Fill in the SITEID you obtained from TVSquared.
   * ***COLLECTORID***: Fill in the COLLECTORID obtained from TVSquared.
3. **Default Postbacks**: AppsFlyer sends postbacks to TVSquared after the user installs/re-engagement. Select the Sending Option for which the partner will get postbacks:
   * **Events attributed to any partner or organic**:All installs, irrespective of source, are reported to TVSquared
   * **Off**
4. Complete in-app events settings fields:

* ***SITEID***: Fill in the SITEID you obtained from TVSquared.
* ***COLLECTORID***: Fill in the COLLECTORID obtained from TVSquared.
* **customerid:** (optional) You can leave this field blank.
* (optional) Enable ***In-App Events Postback***: Map your in-app events with TVSquared using postbacks. Configure the parameters as follows:
  * Click Add Event to add an SDK event to the list and complete the parameters.
* Click **Save integration.**

> 📘 **Note**
>
> According to both Meta ads and X Ads terms and conditions, AppsFlyer can't share user-level data with any 3rd party. Therefore, all Meta ads and X Ads installs are sent to TVSquared as organic.
>
> For details on sharing data with 3rd parties, click [here](/docs/user-level-data-retention).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for TVSquared.

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

Permissions are not available for TVSquared.

</Accordion>

<div data-zendesk-anchors="h_01HF9R4JZ504QNYCQQ8TFDM6FV=setting-up-tvsquared h_01HF9R4JZ5VXT1P5T3RVRXN522=integration-tab h_01HF9R4JZ55HMSRD3TNFF05PKZ=activate-partner h_01HF9R4JZ5KWKPCN3ESQ9K27S7=note h_01HF9R4JZ596NM643Z662BGY0M=attribution-link-tab h_01HF9R4JZ50XY445ABGAPDY962=cost-tab h_01HF9R4JZ5BA74FKFRKY4FPTAS=ad-revenue-tab h_01HF9R4JZ5BV6C6H6V6W53BXXK=permissions-tab" />

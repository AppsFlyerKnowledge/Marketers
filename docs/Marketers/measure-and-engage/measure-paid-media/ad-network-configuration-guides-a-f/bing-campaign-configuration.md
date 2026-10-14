---
title: "Bing campaign configuration"
excerpt: "Bing, an AppsFlyer ad network integrated partner, is one of the world's leading search engines. You can manage user acquisition campaigns through Bing and attribute them with AppsFlyer."
x-zendesk:
  id: 360000985718
  url: https://support.appsflyer.com/hc/en-us/articles/360000985718-Bing-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  position: 16
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Advertisers, Bing, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2019-02-17T11:13:20Z'
  edited_at: '2026-06-16T09:37:37Z'
---
> 📘 **Note**
>
> Microsoft requires attribution providers to delete its user-level data 13 months after the install. This means that the events performed by these users 13 months after they install the app are counted as organic. Past aggregate data remains the same.

## Set up Bing

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

See [partner configuration window.](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page)

<div id="integration-tab" />

<Accordion title="Integration tab">

#### Activate partner

On the **first visit**, you must toggle ON the ***Activate Partner*** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

#### Default postbacks

Send automatic postbacks to Bing following user installs.

> 📘 **Note**
>
> The option **Only events attributed to this partner** is the only option with Bing and is selected by default.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide).  
[Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost integration is not available for this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue is not available for this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

See [permissions tab](/docs/set-up-an-integrated-partner#permissions-tab).

</Accordion>

<div data-zendesk-anchors="h_01HKWAVZG5GZD6DRZBCDF8KWG5=note h_01HKWAVZG51TVD1Y2M4R46CN9H=set-up-bing h_01HKWAVZG5QRGYT2996ARR93M6=integration-tab h_01HKWAVZG5N42ETTX9K01YGN56=activate-partner h_01HKWAVZG5CAMFVGQBDFDZKWMT=default-postbacks h_01HKWAVZG5DTQJ9HCP5N0BQP5F=note-1 h_01HKWAVZG6KK6V3ARGTFQBBGCX=attribution-link-tab h_01HKWAVZG67HCXB8QCMS4F3SZC=cost-tab h_01HKWAVZG60ECM8Q41Y3HTGXZ5=ad-revenue-tab h_01HKWAVZG6N8WC79DBW2N09A70=permissions-tab" />

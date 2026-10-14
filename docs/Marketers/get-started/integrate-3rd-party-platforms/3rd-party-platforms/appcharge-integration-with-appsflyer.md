---
title: "Appcharge integration with AppsFlyer"
excerpt: "Appcharge, an integrated AppsFlyer partner, is a gaming commerce technology provider that specializes in processing payments outside traditional app store ecosystems. Through its integration with AppsFlyer, Appcharge can automatically send web store purchase and refund data to AppsFlyer, enabling a more complete view of return on ad spend (ROAS) and lifetime value (LTV)."
x-zendesk:
  id: 36292113943825
  url: https://support.appsflyer.com/hc/en-us/articles/36292113943825-Appcharge-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 1
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2025-06-17T13:21:47Z'
  edited_at: '2026-07-07T09:58:17Z'
---
## About Appcharge

[Appcharge](https://appcharge.com/) an integrated AppsFlyer partner, is a direct-to-consumer (D2C) platform built for mobile gaming publishers. The integration helps publishers monitor purchases from their web store, a critical revenue channel outside traditional app stores. By sending purchase and refund data directly to AppsFlyer, Appcharge enables accurate return on ad spend (ROAS) calculations based on net revenue, unlocking better insights into campaign performance and player lifetime value (LTV).

The Appcharge integration helps you:

* Attribute and measure e-commerce performance
* Ensure that the LTV is being reported from web store purchases
* Attribute web store purchases to marketing campaigns
* Maintain consistency with your mobile campaign data

This guide walks you through setting up the Appcharge integration.

## Set up the integration

**Prerequisites:**

* You have an active Appcharge account. If not, then please contact the partner (Appcharge) and open an account with them before setting up the integration.
* Your AppsFlyer account includes the necessary permissions to configure partner integrations.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle. Keep it on as long as you work with the partner.
5. Complete the configuration using the **Integration** tab, as described below.

**To edit an existing integration:**

In AppsFlyer, go to **Collaborate > Partner Integrations > Active integrations** tab, search for the partner, and make your changes.

<Accordion title="Integration tab">

#### Activate partner

On your first visit, you'll need to turn on the
**Activate partner** toggle to set up the integration.
The toggle must remain on for as long as you work with Appcharge.
Learn
more about
[partner activation](/docs/partner-activation-deactivation).

#### Advanced Privacy

For iOS apps, the
[Advance Privacy](/docs/apply-aggregated-advanced-privacy-framework)
toggle appears. When turned on, it limits the sharing of user
identifiers
with the partner. Note that when the
[Aggregated Advanced Privacy](/docs/apply-aggregated-advanced-privacy-framework) toggle
is turned on in the App Settings,
**Advanced Privacy (for iOS 14.5+ and later)** is
turned on and locked by default.

#### Default postbacks

AppsFlyer sends default postbacks to Appcharge following user
installs.
Use this section to
[define these postbacks](/docs/set-up-an-integrated-partner#default-postbacks).

* **Off:** Install postbacks aren't sent to Appcharge.  
  **Note:** Appcharge's integration with AppsFlyer
  doesn't
  require sending install postbacks. Therefore, it's recommended
  to set it to Off.
* **All media sources, including organic:** Install
  postbacks are sent for events attributed to any partner and
  for
  organic events.

![default_postbacks.png](https://files.readme.io/390cbd75195ddcfa3f17cd9d569befda9f8b9b0f7040b53f420bb6fa1bc668d0-36292113918225.png)

#### In-app event postbacks

In this section, you can map your AppsFlyer events with your
partners
via postbacks.

![xsolla-af-login-3.jpg](https://files.readme.io/290c39c3503ac884196024851d58e70e6aff8ead5d9e32013e64964624bb8670-36292139269521.jpg)

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK
   or server-to-server event
   to the list.
3. Complete the following parameters:
4. Click **Save Integration**.

</Accordion>

<Accordion title="Attribution link tab">

Attribution links aren't available for Appcharge.

</Accordion>

<Accordion title="Cost tab">

Cost data isn't supported in the integration with Appcharge.

</Accordion>

<Accordion title="Ad revenue tab">

Ad revenue data isn't supported in the integration with Appcharge.

</Accordion>

<Accordion title="Permissions tab">

Permissions aren't available for Appcharge.

</Accordion>

## Identify Appcharge events in AppsFlyer

Appcharge sends AppsFlyer two kinds of mobile in-app events:

* `ac_af_purchase` - When a user successfully completes a purchase
* `ac_af_refund` - When a refund is completed

<Accordion title="Traits and limitations">

PC / Console support - the AppsFlyer integration with Appcharge does not support PC / Console Apps.

</Accordion>

Learn more about [partner integrations](/docs/set-up-an-integrated-partner).
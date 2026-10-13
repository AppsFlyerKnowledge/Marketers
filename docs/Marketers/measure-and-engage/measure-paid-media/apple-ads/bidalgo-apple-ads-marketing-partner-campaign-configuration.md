---
title: "Bidalgo Apple Ads marketing partner—campaign configuration"
excerpt: "Optimize Apple Ads campaigns by using Bidalgo. When configured, AppsFlyer sends postbacks to Bidalgo."
x-zendesk:
  id: 360001340429
  url: https://support.appsflyer.com/hc/en-us/articles/360001340429-Bidalgo-Apple-Ads-marketing-partner-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Apple Ads
  section_id: 6551310453393
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: [Apple Search Ads, Advertisers, Bidalgo, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2018-07-26T10:33:54Z'
  edited_at: '2026-09-15T10:41:33Z'
---
## Enabling sending postbacks to Bidalgo (Apple Ads marketing partner)

> 📘 **Note**
>
> If the advertiser or the agency disables attribution for Apple Ads, attribution for this app, including postback sending to Apple Ads Marketing partners, stops.

Both advertisers and agencies can enable attribution for Apple Ads.

* **Advertisers:** follow the instructions below on how to enable attribution for Apple Ads.
* **Agencies:** [follow these instructions](/docs/apple-ads-integration-setup#agency-setup) to enable attribution for Apple Ads.

### Configuring Bidalgo

**To set up a Bidalgo:**

1. If required, activate **Apple Ads integration:**
   1. In AppsFlyer, from the side menu, select **Collaboration** > **Partner Integrations > Partner Marketplace** tab.
   2. Search for and select the partner. You're directed to the partner configuration page.
   3. From the **Integration** tab, turn on **Activate partner**.
   4. Click **Save Integration**.
2. **In your Apple Ads dashboard**: Get the Apple Ads Campaign Group ID parameter related to Bidalgo. Use the screenshot that follows as a guide to locating the ID.

   ![ASACGroupID.png](https://files.readme.io/4c1dd5feabd59b66c1af687b72128e2490d71670a49e106f98e103357a5a5619-21589966333713.png)
3. **In AppsFlyer, configure Bidalgo:**
   1. In AppsFlyer, from the side menu, select **Collaboration** > **Active Integrations.**
   2. Search for Bidalgo - Apple Ads Marketing Partner.  
      The list of marketing partners displays.
   3. Select Bidalgo - Apple Ads Marketing Partner.
   4. Turn on **Activate Partner**.
   5. Enter Bidalgo's **Apple Ads Campaign ID** that you retrieved in the earlier step. Enter the digits (numbers) only.
   6. Click **Save**.

### Default postbacks

Installs and re-engagements are sent automatically when the partner is activated.

### Configuring in-app events postbacks

**To configure in-app events postback:**

1. Turn on **In-app events postback**.
2. Click **Add Event** to add an SDK Event to the list.
3. Complete the following parameters:

   

| Parameter Name | Description |
| --- | --- |
| SDK Event Name | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server-to-server events. **Tip:** If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| Send Revenue | Select one of the following: No values and no revenue, Values and no revenue, or Values and revenue. |

4. Click **Save Integration**.
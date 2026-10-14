---
title: "SplitMetrics Acquire (formerly SearchAdsHQ) setup"
excerpt: "Optimize Apple Ads campaigns by using SplitMetrics Acquire. When configured, AppsFlyer sends postbacks to SplitMetrics Acquire."
x-zendesk:
  id: 360002249257
  url: https://support.appsflyer.com/hc/en-us/articles/360002249257-SplitMetrics-Acquire-formerly-SearchAdsHQ-setup
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Apple Ads
  section_id: 6551310453393
  position: 4
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: [Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2019-08-15T08:21:04Z'
  edited_at: '2026-09-15T10:52:56Z'
---
## Enabling Apple Ads attribution

Both advertisers and agencies can enable Attribution for Apple Ads.

> 📘 **Note**
>
> If the advertiser or the agency disables attribution for Apple Ads, attribution for this app, including postback sending to Apple Ads Marketing Partners stops.

* **Advertisers**: follow the instructions below on how to enable attribution for Apple Ads.
* **Agencies**: [follow these instructions](/docs/apple-ads-integration-setup#agency-setup) to enable attribution for Apple Ads.

## Setting up SplitMetrics Acquire on AppsFlyer

### Getting required information from SplitMetrics Acquire

Before you start configuring SplitMetrics Acquire on AppsFlyer, obtain your **client\_id** and your **Apple Ads campaign group ID**.

* For client\_id, go to your SplitMetrics Acquire dashboard, click **Integrations** > **AppsFlyer**. In the popup that opens, copy the ID.
* For Apple  Ads Campaign Group ID: **In your Apple Ads dashboard,** get the Apple Ads Campaign Group ID parameter related to SplitMetrics Acquire. Use the screenshot that follows as a guide to locating the ID.  ![ASACGroupID.png](https://files.readme.io/a4b2aba5e7d4e0257b455b1dc44b1030a288a4c3892c0da905cdf361496041e5-360017400378.png)

### Setting up campaigns on AppsFlyer

**To set up a SplitMetrics Acquire:**

1. **In AppsFlyer, configure SplitMetrics Acquire:**
   1. In AppsFlyer, from the side menu, select **Collaboration** > **Partner Integrations** > **Active Integrations.**
   2. Search for SplitMetrics Acquire.  
      The list of marketing partners displays.
   3. Select SplitMetrics Acquire.
   4. Turn on **Activate Partner**.
   5. Enter the client ID in the **client\_id** field.
   6. Enter SplitMetrics Acquire's **Apple Ads Campaign ID** that you retrieved in the earlier step. Enter the digits (numbers) only.
   7. Click **Save**.
2. If you want to record attributions for Apple Ads, also turn on the **Apple Ads integration:**
   1. In AppsFlyer, from the side menu, select **Collaboration** > **Partner Integrations** > **Partner Marketplace**.
   2. Search for and select the partner. You're directed to the partner configuration page.
   3. From the **Integration** tab, turn on **Activate partner**.
   4. Click **Save Integration**.

#### Configuring in-app event postbacks

**To configure postback that should be sent to SplitMetrics Acquire upon in-app events:**

1. Enter the client\_id.
2. Turn on **In-app events postback**.
3. Click **Add Event** to add an SDK Event to the list.
4. Complete the following parameters:

   

| Parameter Name | Description |
| --- | --- |
| SDK Event Name | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server-to-server events. **Tip:** If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| Send Revenue | Select one of the following: No values and no revenue, Values & no revenue, or Values & revenue. |

5. Click **Save Integration**.

<div data-zendesk-anchors="enabling-apple-search-ads-attribution=enabling-apple-ads-attribution h_01HBB5JWBAZMD5BHPGQYHYQY0Q=enabling-apple-ads-attribution h_01HBB5JWBA612TQV90K56H319J=note setting-up-searchadshq-on-appsflyer=setting-up-splitmetrics-acquire-on-appsflyer h_01HBB5JWBA6QPV3ZN0FCBK0BHR=setting-up-splitmetrics-acquire-on-appsflyer getting-required-information-from-searchadshq=getting-required-information-from-splitmetrics-acquire h_01HBB5JWBA6CGAAQAA9DZ4XMNS=getting-required-information-from-splitmetrics-acquire h_01HBB5JWBAMHKBAMQD4TTQSZ0H=setting-up-campaigns-on-appsflyer configuring-inapp-event-postbacks=configuring-in-app-event-postbacks h_01HBB5JWBBHMKT3Z9JKEQJAZZ7=configuring-in-app-event-postbacks" />

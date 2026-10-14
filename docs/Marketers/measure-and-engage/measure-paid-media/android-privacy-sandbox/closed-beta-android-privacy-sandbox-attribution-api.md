---
title: "[Closed beta] Android privacy sandbox - Attribution API"
excerpt: "A privacy-preserving mechanism designed to measure the effectiveness of ad campaigns without relying on user identifiers. Managed on-device, with last-touch attribution. No user data is exchanged between ad networks, which preserves user privacy."
x-zendesk:
  id: 25471654983825
  url: https://support.appsflyer.com/hc/en-us/articles/25471654983825--Closed-beta-Android-privacy-sandbox-Attribution-API
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Android privacy sandbox
  section_id: 25467093087761
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roi-tamir, Marketers, Mobile Attribution, Ad Networks]
  labels: [Advertisers, Ad Networks, Marketers, Loc In Prog, Android Privacy Sandbox, Closed beta]
  promoted: false
  comments_disabled: true
  created_at: '2024-05-29T10:14:59Z'
  edited_at: '2026-08-19T10:31:42Z'
---
[![53090 Android Privacy Sandbox image for KB (1).png](https://files.readme.io/6d9489a792351c33ed0c5f9669fe8bf998c04c8ab665c016aea4c859cec65fe2-26337856151441.png)](https://files.readme.io/6d9489a792351c33ed0c5f9669fe8bf998c04c8ab665c016aea4c859cec65fe2-26337856151441.png)

## Introduction

**Definitions**

* Ad tech - Ad tech in the context of the Android Sandbox Attribution API includes mobile measurement partners (MMPs), advertisers, and ad networks, all working together to measure the performance of ad campaigns while maintaining user privacy.
* Sources - ad clicks or views.
* Triggers - conversions such as installs or post-install events.
* post-install attribution exclusivity window - The post-install attribution exclusivity window in the Sandbox Attribution API is a period during which only the installing ad network can attribute post-install events, ensuring that other networks cannot claim attribution for those events within this time frame.

## About Android privacy sandbox attribution API

### How the Attribution API works

Setup for Ad techs to use the attribution API:

1. Complete the [enrollment process](https://developers.google.com/privacy-sandbox/relevance/setup/android).
2. [Register attribution sources](https://developers.google.com/privacy-sandbox/relevance/attribution-reporting/android#register-attribution-source) such as ad clicks or views.
3. [Register triggers](https://developers.google.com/privacy-sandbox/relevance/attribution-reporting/android#register-trigger) including user conversions on the advertiser app.

The Attribution Reporting API matches triggers to attribution sources and attribution conversions and sends one or more triggers off-device through event-level and aggregatable reports to the ad techs.

The source contains all the data and information about the ad network, including information about the click or view and campaign details. Multiple sources can be stored on the device.

The trigger holds measurement data and data on the install and post-install conversion. Multiple triggers can happen from different ad networks or MMPs.

An ad tech must register both attribution sources and triggers to receive postbacks from the API.

**Note: that the same ad tech must register both the attribution sources and the triggers to receive postback from the API.**

## AppsFlyer Sandbox attribution solution

<Accordion title="Principles and flows">

[![53090 Android Privacy Sandbox image for KB (1).png](https://files.readme.io/f10d82d0bb685cf8b329c3b3be14ad546531588b876938b41e3b9650b1080cac-26552356197649.png)](https://files.readme.io/f10d82d0bb685cf8b329c3b3be14ad546531588b876938b41e3b9650b1080cac-26552356197649.png)

To overcome the functional and structural limitations of the Sandbox attribution infrastructure, the AppsFlyer Sandbox attribution solution takes into consideration the characteristics in the table that follows

| Characteristic | Description |
| --- | --- |
| Data integration | <ul><li>AppsFlyer integrates with multiple ad networks and provides Sandbox attribution results.</li><li>Advertisers don't need to integrate with each ad network individually —a complex and tedious task.</li></ul> |
| Data enrichment | <ul><li>Enriches Sandbox attribution data with other data points to provide complete ROI analysis. For example, the campaign name provided by the ad network, and so on.</li><li>Data points include impressions, clicks, cost, and more.</li></ul> |
| Data delivery | Enriched Sandbox attribution data is available using the following:<ul><li>[Sandbox Overview dashboard](/docs/special-access-android-privacy-sandbox-attribution-api-dashboard-by-appsflyer-cl)</li></ul> |
| Seamless integration | <ul><li>No coding is required. The app requires<ul><li>AppsFlyer [V6.13.1 SDK](/docs/sdk-integration-overview) or above for installs.</li><li>[V6.16.0 SDK](/docs/sdk-integration-overview) or above for [revenue](/docs/special-access-android-privacy-sandbox-attribution-api-dashboard-by-appsflyer-cl#table-metrics).</li><li>[V6.16.1 SDK](/docs/sdk-integration-overview) or above for predefined in-app event measurement.</li></ul></li><li>Includes support for expected changes by Google in the Sandbox attribution infrastructure.</li></ul> |
| Agility | Advertisers can change measurement configurations as needed in the dashboard |

</Accordion>

## Additional Privacy Sandbox attribution information

<Accordion title="Reporting options">

Sandbox attribution reports don't contain user-level identifiers.

| Report name | Type | Enriched by AppsFlyer | Delivery method | Premium feature |
| --- | --- | --- | --- | --- |
| Sandbox overview dashboard | Aggregated | Yes | Dashboard | No |

<Accordion title="Sandbox attribution solution implementation checklist">

| No | Action | Description | Responsibility |
| --- | --- | --- | --- |
| 1 | Prepare the app | Migrate the app to AppsFlyer [V6.13.1 SDK](/docs/sdk-integration-overview) or above.<br />Note: SDK [V6.16.0](/docs/sdk-integration-overview) or above is needed for [revenue](/docs/special-access-android-privacy-sandbox-attribution-api-dashboard-by-appsflyer-cl#table-metrics), and [V6.16.1 SDK](/docs/sdk-integration-overview) or above for predefined in-app event measurement.<ul><li>No change to app logic or to app code is required.</li><li>The AppsFlyer Sandbox attribution solution relies on in-app events to register the triggers. Send in-app events in the usual manner. No Sandbox attribution solution-specific testing is required.</li><li>Submit the app to the Google Play Store</li><li>No Sandbox attribution registration or process is required in the app store.</li></ul> | Developer |
| 2 | Partner integration | Ad network partners must integrate with AppsFlyer using Sandbox attribution integration. See here a list of Sandbox attribution integrated partners.<br /><br />Decide if you want to allow partners to redirect the triggers to the ad network partner. See more details [here](/docs/closed-beta-android-privacy-sandbox-attribution-api#redirecting-triggers-to-ad-networks). | Marketer |

</Accordion>

<Accordion title="Troubleshooting guide">

| Symptom | Description |
| --- | --- |
| The dashboard doesn't contain any installs | <ol><li>Verify that your SDK version is [V6.13.1](/docs/sdk-integration-overview) or above.<br />Note: SDK [V6.16.0](/docs/sdk-integration-overview) or above is needed for [revenue](/docs/special-access-android-privacy-sandbox-attribution-api-dashboard-by-appsflyer-cl#table-metrics), and [V6.16.1 SDK](/docs/sdk-integration-overview) or above for predefined in-app event measurement.</li></ol><ul><li>To do so, go to Integration > SDK Information > Users by SDK version.</li></ul><ol><li>If you use SDK plugins, verify that you implement a version that supports AppsFlyer Sandbox attribution.</li><li>Verify that your ad network partners are integrated with the AppsFlyer Sandbox attribution solution.</li></ol> |

</Accordion>

<Accordion title="Timing from app install until dashboard and reports update">

Sandbox aggregatable reports received on a given day are processed at the end of the next day—UTC starting at 00:01. The data is available 8 hours later. In other words, it takes around 32-56 hours to process the data, with an average delay of 44 hours.  
**For example,** a report received on Monday is processed and ready on Wednesday. The dashboard will be updated by Wednesday 08:00 UTC.

</Accordion>

<Accordion title="Traits and limitations">

| Traits | Remarks |
| --- | --- |
| Agencies | Agencies can indicate that they brought the user by implementing [Sandbox attribution agency recognition](/docs/getting-started-agency-onboarding#sandbox-attribution-agency-campaigns) |
| Agency transparency | N/A |
| Timezone | UTC |
| Currency | N/A |
| Organic data | N/A |
| Non-organic data | Based on Sandbox attribution reports |
| Data freshness | Daily |
| Historical data | Depends on the time the ad network is integrated with AppsFlyer. Earliest date is August 19th, 2024 |
| User access | Account users must have the [necessary permissions](/docs/user-management) |

</Accordion>

<div id="redirecting-triggers-to-ad-networks" />

<Accordion title="Redirecting triggers to ad networks">

Within the Privacy Sandbox, each individual ad network has the capability to view the last-touch attribution flow within its network. This means that an ad network can attribute conversions (such as app installs) to the last ad interaction that occurred within their network.  
However, this capability is different when comparing it to the broader attribution provided by AppsFlyer within Sandbox:  
AppsFlyer can encompass multiple ad networks and provide a holistic view across different networks and declare which network was the last touch before the conversion.

Example Scenario: A user sees and clicks on an ad from Unity Ads on Day 1, then clicks on an ad from TikTok on Day 2, and finally installs the app on Day 3.

Ad network's last-touch attribution: Unity Ads and TikTok can each see if their ad was the last touch before the conversion within their own network. Both Tiktok and Unity will receive winning reports for their own ads under Sandbox attribution.  

AppsFlyer last touch attribution: AppsFlyer can view the entire user journey across both Unity Ads and TikTok, identifying that the user interacted with both ads before converting. AppsFlyer can attribute the conversion to TikTok as it was the last touch.  
If you want to allow the ad network to view the last touch attribution flow within its network you will need to provide written consent to your AppsFlyer rep so we can then redirect those triggers to the ad network. Please reach out to your AppsFlyer rep for more details.  
In the future, we will add such a capability within the AppsFlyer platform to avoid the need for manual written consent.

</Accordion>

<Accordion title="Comparing Sandbox attribution results to AppsFlyer attribution results">

It is not possible to properly compare the Sandbox results to AppsFlyer attribution results for the following reasons:

1. There are fewer ad networks currently integrated with Sandbox attribution compared to AppsFlyer. Therefore, in the case of multi-touch and cross-network attribution flows, the results can differ. For example,  
   Day 1: User clicks on an ad run by Unity  
   Day 2: User clicks on an ad run by TikTok  
   Day 3: User installs App  
   In the regular AppsFlyer flow, TikTok - being the last touch point, will win the attribution. However, with Sandbox, assuming TikTok is still not integrated with Sandbox, Unity Ads will win the attribution.
2. Sandbox attribution results can also contain "noise". Which is the addition of random data to user-related information to protect individual privacy. This technique is used to obscure specific details about user actions, making it more difficult to measure or identify individual users while still allowing for the aggregation and analysis of overall trends and patterns.

</Accordion>

</Accordion>

> 📘 **See also**
>
> * [Closed Beta] Android privacy sandbox - Integrated partners list
> * [[Closed Beta] Attribution API dashboard by AppsFlyer](/docs/special-access-android-privacy-sandbox-attribution-api-dashboard-by-appsflyer-cl)
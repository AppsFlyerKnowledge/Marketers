---
title: "Google Ads (AdWords)—FAQ and discrepancies"
excerpt: "Troubleshoot common issues, missing installs, in-app event sync, and data discrepancies between Google Ads and AppsFlyer."
---
Troubleshoot common issues and discrepancies relating to Google Ads.

## Google Ads FAQ

### Why am I not seeing clicks from Google Ads?

Aggregate clicks and impressions data from Google Ads is collected once you have [authenticated cost, clicks and impressions](/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory) collection in the **Cost** tab.

Clicks and impressions data from Google Ads was made available during August 2018, first for Android apps and later on for iOS apps. Therefore, when analyzing clicks data from 2018 and before, Google Ads clicks data may be missing or incomplete.

### Why am I not seeing first_open conversions on Google Ads

If you are not seeing first_open conversions on Google Ads as shown in the screenshot below:

![AW_13.png](https://files.readme.io/082f79266fced9fc012cdb373321a836129205992adbe29f7509321516e8f5ab-33743114088849.png)

it means that you need to import conversions in Google Ads. Follow the instruction on [importing conversions](/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory).

### Why don’t I see installs from Google Ads?

Follow this checklist to troubleshoot missing installs:

#### Quick fix

1. **Activate Google Ads in AppsFlyer**

In AppsFlyer, from the sidebar, open **Collaborate > Active integrations**, search for **Google Ads**, and confirm the integration is active.
2. **Import the** `first_open` **conversion in Google Ads**

In Google Ads, go to the [Conversions summary](https://ads.google.com/aw/conversions) page and make sure that the `first_open` conversion event is imported. For more information, see [Import your app conversions](/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory).

#### Still not working?

1. **Check which Google Ads account imports conversions**

Determine whether the **Google Ads MCC account or sub-account** is responsible for importing conversions:

   - **If using an MCC (manager account):** The MCC should import the `first_open` conversion on behalf of all linked sub-accounts.
   - **If using a sub-account:**     - The MCC must **share the Link ID** with the sub-account.
     - The sub-account must **also import the** `first_open` **conversion** directly.

For more information about Google Ads MCC accounts, see: [MCC](/docs/recording-multiple-agency-mcc-google-ads-accounts#mcc).

2. **Check for removed** `first_open` **conversions**

In the [Conversions summary](https://ads.google.com/aw/conversions) page, check if the `first_open` conversion event was removed. If removed, contact **Google support** for assistance.
3. **Confirm the Link ID**

Ensure the Link ID in AppsFlyer matches the Link ID in Google Ads.

### Why don't I see in-app events in the Google Ads dashboard?

Use this checklist to ensure your in-app events are correctly set up and synced between AppsFlyer and Google Ads.

#### Quick fix checklist

Follow these steps to quickly resolve the most common issues:

1. **Verify event postbacks in AppsFlyer** (for step-by-step instructions, see [Set up Google Ads on AppsFlyer.](/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended))   1. Go to the **Google Ads integration tab** in AppsFlyer.
2. Ensure postbacks are configured correctly for each in-app event you want to measure.
3. Under **For users from**, select _All media sources, including organic,_ to ensure Google Ads receives event data.
4. (Optional) After initial setup, adjust this selection for specific events if needed.
2. **Trigger a test in-app event**   1. Launch your app.
2. For iOS apps, ensure IDFA collection is enabled by allowing the app to track.
3. Perform the mapped in-app events manually (for example, purchase or signup).
3. **Import events in Google Ads**   1. In Google Ads, click **Tools Conversions**.
2. Check the **Conversion Action Summary**.
3. Import the relevant in-app events. For more information, see [Import your app conversions](/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory).

> 📘 Note
>
> Conversions can take up to 6 hours to appear after performing the event.

#### Still not working?

If you’ve modified the Partner Event identifier in Google Ads (for example, if it’s labeled as `CUSTOM`) and changed the corresponding event name in AppsFlyer, you’ll need to re-import the events into Google Ads.

### Can I stop Google cost sync?

To stop cost sync with Google:

1. Go to your [Google account permissions](https://myaccount.google.com/permissions).
2. Click on Remove next to AppsFlyer Google Cost.

![remove_appsflyer_cost.png](https://files.readme.io/56840e708c98875c8db176c642dd324150a76aef9697fcc2756f524b2a6c0a16-33743128661137.png)

### Do I need to create and then import session_start?

This depends on the type of campaign you are running. If you are running a re-engagement campaign then it is recommended to create and import `session_start` to measure engagements.

For a user acquisition campaign, this is not mandatory.

### Can I send uninstall information to Google Ads?

Yes.

**To start sending uninstall events to Google:**

1. Map the af_uninstall event as a Custom event in Google Ads setup window.
2. Import that conversion in Google.
3. Google acknowledges events if received within Google's attribution window (started with ad engagement and lasting 30-90 days). Events received by Google after the window ends are not recorded in Google.

### What Google Ads data does AppsFlyer display?

You can view data at the following levels: campaign, channel, adset, and geo.

### Do I need to configure anything to create audience lists in Google Ads based on AppsFlyer data?

No. In the Google API, this information is already set and is based on your In-App Event configuration.

### I'm running an app campaign, why can't I see data or conversion events in the AppsFlyer or Google Ads dashboard?

It is very likely that you have not yet imported events. For details about how to import events, click [here](/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory).

### What do I do if there are multiple accounts?

There is no problem using multiple accounts with Google Ads with AppsFlyer. AppsFlyer only works with one Link ID. Therefore, only one Link ID must be generated in Google Ads and this can be shared between multiple accounts. For more information, click [here](https://support.google.com/google-ads/answer/3030657).

### What happens with link IDs created at MCC level vs. account level

Link IDs at MCC or account level are supported by AppsFlyer. We recommend working closely with your Google Ads representative to ensure your account is structured correctly. For more information, click [here](/docs/recording-multiple-agency-mcc-google-ads-accounts).

### What is parallel tracking?

Google Ads' Parallel tracking enables your landing page to load faster, reducing the issue of lost visits. As a result, conversions are increased and ad performance is improved. With Parallel Tracking, users are sent to the final URL, directly from your ad, before sending them to the attribution links, while click measurement takes place in the background.

For a full explanation of Parallel Tracking, click [here](https://support.google.com/google-ads/answer/7544674?hl=en).

#### What is needed?

In order for parallel tracking to work as intended, the final URL must match what is in the campaign URL and be put in [Google's `{lpurl}` ValueTrack parameter.](https://support.google.com/google-ads/answer/6305348?hl=en)

This is done by:

- Using a single platform attribution link (not recommended)
  - af_r parameter must be used in the URL
- Using a [OneLink long link](/docs/understand-onelink-short-vs-long-urls) (recommended)
  - Having the following URL parameters included in the campaign URL
    - af_android_url
    - af_ios_url
    - af_web_dp
  - af_dp should not be used
  - adding your final URL (destination URL) to Google's ValueTrack parameter. [Learn more](https://support.google.com/google-ads/answer/6305348?hl=en#urlinsertion&zippy=%2Ctracking-template-only)

For example,

```auto
https://subdomain.onelink.me/template_id?pid=xxx&af_ios_url={lpurl}&af_android_url={lpurl}&af_web_dp={lpurl}
```

Note: To see all supported parameters refer to this [article](https://support.google.com/google-ads/answer/6305348?hl=en&sjid=12409212435602417786-AP#zippy=%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-campaign-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-ad-group-level%2Cfinal-url-tracking-template-or-custom-parameter).

Click here to see how to configure Google ad web campaigns with parallel tracking.

### How do you configure a campaign with Android or iOS configuration

> 🚧 Important!
>
> AppsFlyer supports all app campaigns enabled by Google Ads.

Google is an SRN (Self Reporting Network). For more information about how the attribution flow works for these networks, click [here](/docs/self-reporting-networks-srns).

AppsFlyer can present any campaign information that is provided by Google. The campaign type (Search, Video, Display, and Re-engagement) and associated information is determined by Google. It is recommended to configure App campaigns. For guidance on other campaign types, you should contact your Google representative. For details of these campaigns, click [here](https://developers.google.com/app-conversion-tracking/api/request-response-specs).

#### Android configuration for Google Ads

To support Android attribution, make sure that your app supports GAID (Google Advertising ID) collection, and that it is passed to AppsFlyer through our SDK.

#### Creating conversion recording (installs)

For details of how to create conversion recording, click [here](/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory).

Google Ads - Android Configuration - Sending In-App Events

If you want to further measure the success of your Mobile App Install campaigns in Google, you can send in-app events to your Google Ads account from your AppsFlyer account.

#### Create a conversion (in-app events)

For details of how to measure your app conversions, click [here](/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory).

#### iOS configuration for Google Ads

#### Google Ads - iOS configuration: app campaigns

App campaigns allow you to promote your iOS app across Google Search, YouTube and Display in a single place of configuration.

Generally, Google Ads itself can't self-attribute iOS installs from search campaigns as the clicks come from mobile web sources, preventing Google from pulling the IDFA from the devices, and from performing ID matching.

In contrast, **iOS search on App Campaigns can be attributed by Google Ads**, for ads that are served on the **Google Search App.**

#### creating conversion recording (installs)

For details of how to create conversion recording, click [here](/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory).

#### Google Ads - iOS configuration - sending in-app events

If you want to further measure the success of your Mobile App Install campaigns in Google, you can send in-app events to your Google Ads account from your AppsFlyer account.

#### Creating a conversion (in-app events)

For details of how to measure your app conversions, click [here](/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory).

### For how long do you keep Google Ads’ user-level data?

Google Ads requires attribution providers to delete its user-level data 6 months after the install. This means that the events performed by these users 6 months after they install the app are counted as organic.

Past aggregate data remains the same.

This is relevant for all Google Ads channels.

## Google Ads discrepancies

Sometimes there are discrepancies between the Google Ads dashboard and the AppsFlyer dashboard.

While we work closely with Google Ads to minimize these discrepancies, advertisers should be aware of the following reasons:

#### Both iOS and Android

| Cause | Google Ads | AppsFlyer |
| --- | --- | --- |
| **Modelled conversions and ICM conversions** | Google Ads shows modelled installs generated by Google’s internal modelling, and does not show ICM-based modelled installs. | AppsFlyer shows modelled installs generated by Google ICM (probabilistic claims), and does not show Google’s internally modelled installs. |
| **Assisted installs (aka Multi-touch attribution)** | Google Ads, as an SRN, attributes all installs following engagements with Google Ads, within their attribution window. | AppsFlyer attributes the last click in a user's journey and treats engagements before it as [assists](/docs/measure-assisted-installs). |
| **Install record time** | Google Ads attributes the conversion to the Click time. | AppsFlyer attributes the conversion to the launch time (app open). |
| **Time zones** | Varies - based on location | Varies - based on location. |
| **Attribution window** | 30 Days | Google integration is set for 30 days by default (can be modified). |
| **View-through conversions** | VT conversions only show in the **All conversions** column and not in the **Conversions** column, unless set otherwise in Google Ads. | AppsFlyer shows total installs number, click installs and VT installs. |
| **Reinstalls** | Google Ads show reinstalls as a session_start conversion. | AppsFlyer attributes and displays re-installs (AKA re-attributions) as part of its retargeting data. |
| **In-app events** | Google Ads attributes the in-app event to the Click time. | In the AppsFlyer dashboard in-app events are attributed according to the install time. In Raw Data Reports, AppsFlyer attributes in-app events according to the time of the event. |
| **Validation rules** | Google receives all information from AppsFlyer regardless of validation rules. | AppsFlyer might deduct a number of installs based on their validation rules. |
| **Cost - Google Ads campaign channels** | Google reports cost for all channels of a given campaign - YouTube, display, and search. | AppsFlyer gets cost data from Google for all channels of a campaign, but only attributes conversions from YouTube and display channels in iOS AC. As a result, the overall CPI in AppsFlyer is higher. |
| **SKAN installs** | From Google Ads API V10+, the Google Ads dashboard doesn't differentiate between installs with did_win=TRUE and did_win=NULL. The differentiation is only in raw data. | From Google Ads API V10+, AppsFlyer only displays installs from postbacks with the did_win=TRUE. As a result, the installs number in AppsFlyer may be lower. |
| **first_open events** | Google Ads get events from Firebase where DMA is implemented correctly and subsequently DMA consented events are claimed. | Google Ads get the same events also from AppsFlyer where DMA is implemented incorrectly causing all events to be reported as non DMA consented and Google not to claim them. <br/>- To check if DMA is implemented correctly [download the raw data report](/docs/raw-data-export-page#download-report) and focus on the fields specified in [this bulletin](/docs/bulletin-dma-support-in-raw-data-reports).<br/>- See [the Dev Hub](https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance) to learn how to implement DMA in the SDK |
| **Retargeting events** | Google Ads can claim a re-engagement with `ad_type=ClickToDownload` in the response. | AppsFlyer counts `ad_type=ClickToDownload` as a UA conversion event rather than as a re-engagement. As a result, the re-engagement number in AppsFlyer may be lower. |

#### Notes

- While Google Ads shows all installs of a retargeting campaign in the same place, in the AppsFlyer Overview dashboard, the UA view displays new installs, the retargeting view displays re-attributions, and the unified view displays both.
- When comparing data from Google Ads dashboard and AppsFlyer, make sure that the data in the Google Ads dashboard is data that is imported from 3rd party analytics (AppsFlyer). Data imported from Firebase or Google Play is structured differently and is not fully comparable with AppsFlyer data. To learn how to import data from AppsFlyer to Google Ads dashboard, click [here](/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory).
- To compare install events (first_open in Google Ads), make sure that you drill down to install events in the conversion report in Google Ads. Google Ads might show all conversions (e.g. installs, purchases, subscriptions) which is why it is important to select only those install events out of all conversion events.

<Cards>
  <Card title="Google Ads SKAdNetwork interoperability with AppsFlyer" href="/docs/get-skan-postback-data-from-google-ads">
    For iOS 14-related considerations, see Google Ads SKAdNetwork interoperability with AppsFlyer.
  </Card>
</Cards>
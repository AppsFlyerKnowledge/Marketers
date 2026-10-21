---
title: Google Ads (AdWords)—FAQ and discrepancies
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T10:06:31Z'
  edited_at: '2026-03-16T16:54:16Z'
  id: 4417303339921
  locale: en-us
  section: Google Ads
  section_id: 6551205645457
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4417303339921-Google-Ads-AdWords-FAQ-and-discrepancies
---
**At a glance:** Troubleshoot common issues and discrepancies relating to Google Ads.

## Google Ads FAQ

<div id="why-am-i-not-seeing-clicks-from-google-ads" />

<Accordion title="Why am I not seeing clicks from Google Ads?">

Aggregate clicks and impressions data from Google Ads is collected once you have <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">authenticated cost, clicks and impressions</Anchor> collection in the **Cost** tab.

Clicks and impressions data from Google Ads was made available during August 2018, first for Android apps and later on for iOS apps. Therefore, when analyzing clicks data from 2018 and before, Google Ads clicks data may be missing or incomplete.

</Accordion>

<div id="why-am-i-not-seeing-first_open-conversions-on-google-ads" />

<Accordion title="Why am I not seeing first_open conversions on Google Ads">

If you are not seeing first\_open conversions on Google Ads as shown in the screenshot below:

![AW_13.png](https://files.readme.io/082f79266fced9fc012cdb373321a836129205992adbe29f7509321516e8f5ab-33743114088849.png)

it means that you need to import conversions in Google Ads. Follow the instruction on <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">importing conversions</Anchor>.

</Accordion>

<div id="why-don-t-i-see-installs-from-google-ads" />

<Accordion title="Why don’t I see installs from Google Ads?">

Follow this checklist to troubleshoot missing installs:

#### Quick fix

1. **Activate Google Ads in AppsFlyer**  
   In AppsFlyer, from the sidebar, open **Collaborate > Active integrations**, search for **Google Ads**, and confirm the integration is active.
2. **Import the** `first_open` **conversion in Google Ads**  
   In Google Ads, go to the <Anchor target="_blank" href="https://ads.google.com/aw/conversions">Conversions summary</Anchor> page and make sure that the `first_open` conversion event is imported. For more information, see <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">Import your app conversions</Anchor>.

#### Still not working?

1. **Check which Google Ads account imports conversions**  
   Determine whether the **Google Ads MCC account or sub-account** is responsible for importing conversions:

   * **If using an MCC (manager account):** The MCC should import the `first_open` conversion on behalf of all linked sub-accounts.
   * **If using a sub-account:**
     * The MCC must **share the Link ID** with the sub-account.
     * The sub-account must **also import the** `first_open` **conversion** directly.

   For more information about Google Ads MCC accounts, see: <Anchor target="_blank" href="/marketers/docs/recording-multiple-agency-mcc-google-ads-accounts#mcc">MCC</Anchor>.
2. **Check for removed** `first_open` **conversions**  
   In the <Anchor target="_blank" href="https://ads.google.com/aw/conversions">Conversions summary</Anchor> page, check if the `first_open` conversion event was removed. If removed, contact **Google support** for assistance.
3. **Confirm the Link ID**  
   Ensure the Link ID in AppsFlyer matches the Link ID in Google Ads.

</Accordion>

<div id="why-dont-i-see-inapp-events-in-the-google-ads-dashboard" />

<Accordion title="Why don't I see in-app events in the Google Ads dashboard?">

Use this checklist to ensure your in-app events are correctly set up and synced between AppsFlyer and Google Ads.

#### Quick fix checklist

Follow these steps to quickly resolve the most common issues:

1. **Verify event postbacks in AppsFlyer** (for step-by-step instructions, see <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended">Set up Google Ads on AppsFlyer.</Anchor>)
   1. Go to the **Google Ads integration tab** in AppsFlyer.
   2. Ensure postbacks are configured correctly for each in-app event you want to measure.
   3. Under **For users from**, select *All media sources, including organic,* to ensure Google Ads receives event data.
   4. (Optional) After initial setup, adjust this selection for specific events if needed.
2. **Trigger a test in-app event**
   1. Launch your app.
   2. For iOS apps, ensure IDFA collection is enabled by allowing the app to track.
   3. Perform the mapped in-app events manually (for example, purchase or signup).
3. **Import events in Google Ads**
   1. In Google Ads, click **Tools Conversions**.
   2. Check the **Conversion Action Summary**.
   3. Import the relevant in-app events. For more information, see <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">Import your app conversions</Anchor>.

      > 📘 **Note**
      >
      > Conversions can take up to 6 hours to appear after performing the event.


#### Still not working?

If you’ve modified the Partner Event identifier in Google Ads (for example, if it’s labeled as `CUSTOM`) and changed the corresponding event name in AppsFlyer, you’ll need to re-import the events into Google Ads.

</Accordion>

<div id="can-i-stop-google-cost-sync" />

<Accordion title="Can I stop Google cost sync?">

To stop cost sync with Google:

1. Go to your <Anchor target="_blank" href="https://myaccount.google.com/permissions">Google account permissions</Anchor>.
2. Click on Remove next to AppsFlyer Google Cost.  
   ![remove_appsflyer_cost.png](https://files.readme.io/56840e708c98875c8db176c642dd324150a76aef9697fcc2756f524b2a6c0a16-33743128661137.png)

</Accordion>

<div id="do-i-need-to-create-and-then-import-session_start" />

<Accordion title="Do I need to create and then import session_start?">

This depends on the type of campaign you are running. If you are running a re-engagement campaign then it is recommended to create and import `session_start` to measure engagements.

For a user acquisition campaign, this is not mandatory.

</Accordion>

<div id="can-i-send-uninstall-information-to-google-ads" />

<Accordion title="Can I send uninstall information to Google Ads?">

Yes.  
**To start sending uninstall events to Google:**

1. Map the af\_uninstall event as a Custom event in Google Ads setup window.
2. Import that conversion in Google.
3. Google acknowledges events if received within Google's attribution window (started with ad engagement and lasting 30-90 days). Events received by Google after the window ends are not recorded in Google.

</Accordion>

<div id="what-google-ads-data-does-appsflyer-display" />

<Accordion title="What Google Ads data does AppsFlyer display?">

You can view data at the following levels: campaign, channel, adset, and geo.

</Accordion>

<div id="do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data" />

<Accordion title="Do I need to configure anything to create audience lists in Google Ads based on AppsFlyer data?">

No. In the Google API, this information is already set and is based on your In-App Event configuration.

</Accordion>

<div id="im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard" />

<Accordion title="I'm running an app campaign, why can't I see data or conversion events in the AppsFlyer or Google Ads dashboard?">

It is very likely that you have not yet imported events. For details about how to import events, click <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">here</Anchor>.

</Accordion>

<div id="what-do-i-do-if-there-are-multiple-accounts" />

<Accordion title="What do I do if there are multiple accounts?">

There is no problem using multiple accounts with Google Ads with AppsFlyer. AppsFlyer only works with one Link ID. Therefore, only one Link ID must be generated in Google Ads and this can be shared between multiple accounts. For more information, click <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3030657">here</Anchor>.

</Accordion>

<div id="what-happens-with-link-ids-created-at-mcc-level-vs-account-level" />

<Accordion title="What happens with link IDs created at MCC level vs. account level">

Link IDs at MCC or account level are supported by AppsFlyer. We recommend working closely with your Google Ads representative to ensure your account is structured correctly. For more information, click <Anchor target="_blank" href="/marketers/docs/recording-multiple-agency-mcc-google-ads-accounts">here</Anchor>.

</Accordion>

<div id="what-is-parallel-tracking" />

<Accordion title="What is parallel tracking?">

Google Ads' Parallel tracking enables your landing page to load faster, reducing the issue of lost visits. As a result, conversions are increased and ad performance is improved. With Parallel Tracking, users are sent to the final URL, directly from your ad, before sending them to the attribution links, while click measurement takes place in the background.

For a full explanation of Parallel Tracking, click <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">here</Anchor>.

#### What is needed?

In order for parallel tracking to work as intended, the final URL must match what is in the campaign URL and be put in [Google's `{lpurl}` ValueTrack parameter.](https://support.google.com/google-ads/answer/6305348?hl=en)

This is done by:

* Using a single platform attribution link (not recommended)
  * af\_r parameter must be used in the URL
* Using a <Anchor target="_blank" href="/marketers/docs/understand-onelink-short-vs-long-urls">OneLink long link</Anchor> (recommended)
  * Having the following URL parameters included in the campaign URL
    * af\_android\_url
    * af\_ios\_url
    * af\_web\_dp
  * af\_dp should not be used
  * adding your final URL (destination URL) to Google's ValueTrack parameter. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en#urlinsertion&zippy=%2Ctracking-template-only">Learn more</Anchor>

For example,

```
https://subdomain.onelink.me/template_id?pid=xxx&af_ios_url={lpurl}
&af_android_url={lpurl}&af_web_dp={lpurl}
```

Note: To see all supported parameters refer to this [article](https://support.google.com/google-ads/answer/6305348?hl=en&sjid=12409212435602417786-AP#zippy=%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-campaign-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-ad-group-level%2Cfinal-url-tracking-template-or-custom-parameter).

Click here to see how to configure Google ad web campaigns with parallel tracking.

</Accordion>

<div id="how-do-you-configure-a-campaign-with-android-or-ios-configuration" />

<Accordion title="How do you configure a campaign with Android or iOS configuration">

> 🚧 **Important!**
>
> AppsFlyer supports all app campaigns enabled by Google Ads.
>
> Google is an SRN (Self Reporting Network). For more information about how the attribution flow works for these networks, click <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns">here</Anchor>.
>
> AppsFlyer can present any campaign information that is provided by Google. The campaign type (Search, Video, Display, and Re-engagement) and associated information is determined by Google. It is recommended to configure App campaigns. For guidance on other campaign types, you should contact your Google representative. For details of these campaigns, click <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">here</Anchor>.

<div id="android-configuration-for-google-ads" />

<Accordion title="Android configuration for Google Ads">

To support Android attribution, make sure that your app supports GAID (Google Advertising ID) collection, and that it is passed to AppsFlyer through our SDK.

#### Creating conversion recording (installs)

For details of how to create conversion recording, click <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">here</Anchor>.

<span id="inapp_events"></span>Google Ads - Android Configuration - Sending In-App Events

If you want to further measure the success of your Mobile App Install campaigns in Google, you can send in-app events to your Google Ads account from your AppsFlyer account.

#### Create a conversion (in-app events)

For details of how to measure your app conversions, click <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">here</Anchor>.

</Accordion>

<div id="ios-configuration-for-google-ads" />

<Accordion title="iOS configuration for Google Ads">

#### Google Ads - iOS configuration: app campaigns

App campaigns allow you to promote your iOS app across Google Search, YouTube and Display in a single place of configuration.

Generally, Google Ads itself can't self-attribute iOS installs from search campaigns as the clicks come from mobile web sources, preventing Google from pulling the IDFA from the devices, and from performing ID matching.

In contrast, **iOS search on App Campaigns can be attributed by Google Ads**, for ads that are served on the **Google Search App.**

#### creating conversion recording (installs)

For details of how to create conversion recording, click <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">here</Anchor>.

#### Google Ads - iOS configuration - sending in-app events

If you want to further measure the success of your Mobile App Install campaigns in Google, you can send in-app events to your Google Ads account from your AppsFlyer account.

#### Creating a conversion (in-app events)

For details of how to measure your app conversions, click <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">here</Anchor>.

</Accordion>

</Accordion>

<div id="for-how-long-do-you-keep-google-ads--userlevel-data" />

<Accordion title="For how long do you keep Google Ads’ user-level data?">

Google Ads requires attribution providers to delete its user-level data 6 months after the install. This means that the events performed by these users 6 months after they install the app are counted as organic.

Past aggregate data remains the same.

This is relevant for all Google Ads channels.

</Accordion>

## Google Ads discrepancies

Sometimes there are discrepancies between the Google Ads dashboard and the AppsFlyer dashboard.

While we work closely with Google Ads to minimize these discrepancies, advertisers should be aware of the following reasons:

#### Both iOS and Android

| **Cause** | **Google Ads** | **AppsFlyer** |
| --- | --- | --- |
| **Modelled conversions and ICM conversions** | Google Ads shows modelled installs generated by Google’s internal modelling, and does not show ICM-based modelled installs. | AppsFlyer shows modelled installs generated by Google ICM (probabilistic claims), and does not show Google’s internally modelled installs. |
| **Assisted installs (aka Multi-touch attribution)** | Google Ads, as an SRN, attributes all installs following engagements with Google Ads, within their attribution window. | AppsFlyer attributes the last click in a user's journey and treats engagements before it as <Anchor target="_blank" href="/marketers/docs/measure-assisted-installs">assists</Anchor>. |
| **Install record time** | Google Ads attributes the conversion to the Click time. | AppsFlyer attributes the conversion to the launch time (app open). |
| **Time zones** | Varies - based on location | Varies - based on location. |
| **Attribution window** | 30 Days | Google integration is set for 30 days by default (can be modified). |
| **View-through conversions** | VT conversions only show in the **All conversions** column and not in the **Conversions** column, unless set otherwise in Google Ads. | AppsFlyer shows total installs number, click installs and VT installs. |
| **Reinstalls** | Google Ads show reinstalls as a session\_start conversion. | AppsFlyer attributes and displays re-installs (AKA re-attributions) as part of its retargeting data. |
| **In-app events** | Google Ads attributes the in-app event to the Click time. | In the AppsFlyer dashboard in-app events are attributed according to the install time. In Raw Data Reports, AppsFlyer attributes in-app events according to the time of the event. |
| **Validation rules** | Google receives all information from AppsFlyer regardless of validation rules. | AppsFlyer might deduct a number of installs based on their validation rules. |
| **Cost - Google Ads campaign channels** | Google reports cost for all channels of a given campaign - YouTube, display, and search. | AppsFlyer gets cost data from Google for all channels of a campaign, but only attributes conversions from YouTube and display channels in iOS AC. As a result, the overall CPI in AppsFlyer is higher. |
| **SKAN installs** | From Google Ads API V10+, the Google Ads dashboard doesn't differentiate between installs with did\_win=TRUE and did\_win=NULL. The differentiation is only in raw data. | From Google Ads API V10+, AppsFlyer only displays installs from postbacks with the did\_win=TRUE. As a result, the installs number in AppsFlyer may be lower. |
| **first\_open events** | Google Ads get events from Firebase where DMA is implemented correctly and subsequently DMA consented events are claimed. | Google Ads get the same events also from AppsFlyer where DMA is implemented incorrectly causing all events to be reported as non DMA consented and Google not to claim them.<ul><li>To check if DMA is implemented correctly <Anchor target="_blank" href="/marketers/docs/raw-data-export-page#download-report">download the raw data report</Anchor>  and focus on the fields specified in <Anchor target="_blank" href="/marketers/docs/bulletin-dma-support-in-raw-data-reports">this bulletin</Anchor>.</li><li>See [the Dev Hub](https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance) to learn how to implement DMA in the SDK</li></ul> |
| **Retargeting events** | Google Ads can claim a re-engagement with `ad_type=ClickToDownload` in the response. | AppsFlyer counts `ad_type=ClickToDownload`  as a UA conversion event rather than as a re-engagement. As a result, the re-engagement number in AppsFlyer may be lower. |

> 📘 **Notes**
>
> * While Google Ads shows all installs of a retargeting campaign in the same place, in the AppsFlyer Overview dashboard, the UA view displays new installs, the retargeting view displays re-attributions, and the unified view displays both.
> * When comparing data from Google Ads dashboard and AppsFlyer, make sure that the data in the Google Ads dashboard is data that is imported from 3rd party analytics (AppsFlyer). Data imported from Firebase or Google Play is structured differently and is not fully comparable with AppsFlyer data. To learn how to import data from AppsFlyer to Google Ads dashboard, click <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">here</Anchor>.
> * To compare install events (first\_open in Google Ads), make sure that you drill down to install events in the conversion report in Google Ads. Google Ads might show all conversions (e.g. installs, purchases, subscriptions) which is why it is important to select only those install events out of all conversion events.

> 📄 **See also**
>
> * For iOS 14-related considerations, see <Anchor target="_blank" href="/marketers/docs/get-skan-postback-data-from-google-ads">Google Ads SKAdNetwork interoperability with AppsFlyer</Anchor>.

<div data-zendesk-anchors="h_01HA1SM7D91QPG17WH752FBAFT=google-ads-faq h_01HA1SM7D9JWBEPNE0E8FE665E=why-am-i-not-seeing-clicks-from-google-ads h_01HA1SM7DAW984PPRGHXA5BYSX=why-am-i-not-seeing-first_open-conversions-on-google-ads why-don%E2%80%99t-i-see-installs-from-google-ads=why-don-t-i-see-installs-from-google-ads h_01K5DZBDMS0D2S5XYDC22WQ19H=why-don-t-i-see-installs-from-google-ads h_01K5DZBDMSBDKAFHVVPYD6YKRK=quick-fix h_01K5DZBDMSVTE6M2J235ST85DE=still-not-working h_01K7NT8FVC3K3861WN9VKRZ2HB=why-dont-i-see-inapp-events-in-the-google-ads-dashboard h_01K7NT8FVC1T557GPG7ZCYX33J=quick-fix-checklist h_01K7PAH7VDS7NGW6R6HERGXK9H=note still-not-working::77f3165b=still-not-working-1 h_01K7NT8FVCD4DNFKP3DS75ZKR0=still-not-working-1 h_01HA1SM7DACQDVGWGKV5MZ63D6=can-i-stop-google-cost-sync h_01HA1SM7DA415FQP3MFC09AE3Y=do-i-need-to-create-and-then-import-session_start h_01HA1SM7DAEKGVPDTX77RJ9Y37=can-i-send-uninstall-information-to-google-ads h_01HA1SM7DAKKVZ82WF6RVEDHE9=what-google-ads-data-does-appsflyer-display h_01HA1SM7DANYQ0DAY54CH4HPV4=do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data h_01HA1SM7DA3XF8NBGYGZ0XTB69=im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard h_01HA1SM7DAY7JNTFSG86A1QGKC=what-do-i-do-if-there-are-multiple-accounts h_01HA1SM7DAYSVMENT91T2BE26Z=what-happens-with-link-ids-created-at-mcc-level-vs-account-level h_01HA1SM7DAK186BRZN970PKPRM=what-is-parallel-tracking additional-information=what-is-needed h_01HA1SM7DAMNG8X22VNWMKBJ8R=what-is-needed h_01HA1SM7DBNAS6DP8G9D8KFHPW=how-do-you-configure-a-campaign-with-android-or-ios-configuration h_01HA1SM7DB16T3RGBVGT5Z9REW=important h_01HA1SM7DBC38CY8AN3EPMMJFW=android-configuration-for-google-ads h_01HA1SM7DBF9KDRNEV25KJHGHN=creating-conversion-recording-installs create-a-conversion-inapp-events=create-a-conversion-in-app-events h_01HA1SM7DBDQVNDQ5GG7X2PJ8K=create-a-conversion-in-app-events h_01HA1SM7DBKKQ9R8MQMQT9GRXV=ios-configuration-for-google-ads google-ads-ios-configuration-app-campaigns=google-ads---ios-configuration-app-campaigns h_01HA1SM7DBNSDFCJA5BP59MMQ2=google-ads---ios-configuration-app-campaigns creating-conversion-recording-installs::6a56eb4b=creating-conversion-recording-installs-1 h_01HA1SM7DBXCT0NS4W50D4ZGEK=creating-conversion-recording-installs-1 google-ads-ios-configuration-sending-inapp-events=google-ads---ios-configuration---sending-in-app-events h_01HA1SM7DBEV9CJTAB5YHRJHYK=google-ads---ios-configuration---sending-in-app-events creating-a-conversion-inapp-events=creating-a-conversion-in-app-events h_01HA1SM7DBCQYSJ3R67F0856QK=creating-a-conversion-in-app-events for-how-long-do-you-keep-google-ads%E2%80%99-userlevel-data=for-how-long-do-you-keep-google-ads--userlevel-data h_01HA1SM7DBFAAV7C4ENA34B7JP=for-how-long-do-you-keep-google-ads--userlevel-data h_01HA1SM7DBA7KK1DXFCE2G0QTP=google-ads-discrepancies h_01HA1SM7DB18BTDKK5BK4949HX=both-ios-and-android h_01HA1SM7DBSTAREA36YWRRRG82=notes h_01HDP2XBSEJVQ5G0MD0V5R05CM=see-also" />

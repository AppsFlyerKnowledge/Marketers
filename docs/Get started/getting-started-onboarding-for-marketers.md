---
title: "Getting started—Onboarding for marketers"
excerpt: "Get everything set up to make the most of your AppsFlyer account by understanding the steps, timelines, and dependencies for onboarding your apps and team."
---
At a glance: Get everything set up to make the most of your AppsFlyer account. Understand the steps, timelines, and dependencies for getting your apps and your team on board.

<Embed title="Onboarding for Marketers" typeOfEmbed="youtube" url="https://www.youtube.com/embed/b3ca4a830666b3d68c95f2c658792c7472e806cb7b739f6d4f2ee5deeb58e4b6" />

## Introduction

This document helps marketer (app owner) product managers **plan and execute their onboarding with AppsFlyer**. For every item, the owner and approximate implementation time are provided.

> 📘 General guidance
>
> Note that the time estimates in this article are intended as general guidance only. They are based on our experience working with many new customers, but we recognize that every app owner, app, and implementation is different. Your actual time requirements may vary.

## Account setup

The **account admin** should complete the following steps:

| Step | Time | Comments |
| --- | --- | --- |
| [Sign up](https://www.appsflyer.com/get-started/) with AppsFlyer | 5 mins | Ideally, an account admin is a real AppsFlyer user who can receive important messages when needed. |
| [Add account users](https://support.appsflyer.com/hc/articles/4409128270481#creating-users) who will use the AppsFlyer dashboard, and set their permissions | 1 min per account user | [In some cases](https://support.appsflyer.com/hc/articles/4409128270481#creating-users), users can be added to multiple accounts. |

**Result:** Welcome! You now have an active AppsFlyer account and account users who can access it.

> 👍 Tip
>
> New to AppsFlyer and wondering what it can do for you? [Watch this 6-minute video](/docs/welcome-to-appsflyer#what-can-you-do-with-appsflyer).

## App onboarding

The following **steps 1-3 are mandatory for every app** added to AppsFlyer (except where stated as optional).

You can follow the steps using this guide or via the app onboarding page. The App onboarding page guides you through the basic steps required to get your app ready for attribution. If you prefer to use it, we recommend also checking this guide for additional steps you may need for your specific business needs.

**To open the app onboarding page:**

1. In the menu bar, click the user menu (email address dropdown)
2. Select App onboarding

## Step 1: App setup

The **account admin** should complete the following steps for each of your apps:

| Step | Time | Comments |
| --- | --- | --- |
| [Add your app](https://support.appsflyer.com/hc/articles/207377436-Adding-a-New-App-to-the-AppsFlyer-Dashboard) to the AppsFlyer account | 1 min | If adding an app fails, it's often because it was previously defined in a different account (typically an ad agency that your marketers work with). Contact your CSM or hello@appsflyer.com to [transfer the app to your account](/docs/transferring-apps-between-accounts). <br>See additional [troubleshooting steps](https://support.appsflyer.com/hc/articles/207377436-Adding-a-New-App-to-the-AppsFlyer-Dashboard#troubleshooting) for adding apps. |
| Set the app [time zone, currency](https://support.appsflyer.com/hc/articles/207377436#enter-additional-information-not-applicable-to-web-apps), and whether it's directed toward children | 1 min |  |
| Set the app's<br>[re-attribution window](https://support.appsflyer.com/hc/articles/115002587066-Re-Attribution-Window) (on the [App settings](https://support.appsflyer.com/hc/articles/211719806-App-settings-#reattribution-window) page) | 1 min | The re-attribution window is the period, starting from the date of the first install, during which **re-installs from the same device are not attributed** as new installs. The default value is 90 days, which you can customize as needed. |
| [Optional] Migrate existing user devices into AppsFlyer | 2 hours | If your app already has a substantial user base, consider [migrating them into AppsFlyer](https://support.appsflyer.com/hc/articles/360001923697#device-migration%E2%80%94optional) to avoid double charges.<br>**Note:** With the assistance of your AppsFlyer CSM or the support team at [hello@appsflyer.com](mailto:hello@appsflyer.com)). |

**Result:** Your apps are now defined in the AppsFlyer dashboard.

## Step 2: SDK / API integration

Complete the following steps for every app defined in AppsFlyer in [Step 1: App setup](https://support.appsflyer.com/hc/articles/207033486#step-2-app-setup):

| Step | Owner | Time | Comments |
| --- | --- | --- | --- |
| Consider the available options and select the [SDK functionalities](https://support.appsflyer.com/hc/articles/207032126) you want your app to use | Product manager | 1 hour | - Some considerations beyond basic attribution:<br>  - Will your campaigns deep link users into the app?<br>  - Will the app need to [access attribution or deep-linking data](https://support.appsflyer.com/hc/articles/207032066#accessing-attribution-and-deep-linking-data)?<br>  - Should AppsFlyer data contain your [Customer User ID](https://support.appsflyer.com/hc/articles/207032066#integrate-unique-identifiers-from-your-bi-system-with-appsflyer) for reference?<br>  - How will you implement [privacy settings for iOS 14+](https://support.appsflyer.com/hc/articles/207032066#configure-app-tracking-transparency-att-support) devices? Will you measure uninstalls, run cross-promotion campaigns, and more?<br>- Do you have a CTV app? See our [CTV overview](https://support.appsflyer.com/hc/articles/4404083608849). |
| Select which [in-app events](https://support.appsflyer.com/hc/articles/115005544169) to record | Product manager | 1 hour | Recording the post-installation events your users perform in the app helps you better understand the **quality** of your users.<br>Visit the [In-app event generator](https://evgen.appsflyer.com/) to use our comprehensive list of [recommended in-app events](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-guide#recommended-events-by-business-vertical) and parameters for your vertical. You can add your own events and parameters.<br>Click the **Code** button to view and copy the automatically generated code for your developers (and make them happy). |
| Select methods for retrieving attribution /deep-linking data | Product manager | 30 mins | Learn more about the available [methods](https://support.appsflyer.com/hc/articles/207032066#accessing-attribution-and-deep-linking-data):<br>- [Pull API](https://support.appsflyer.com/hc/articles/360007530258-Using-Pull-API-raw-data)<br>- [Push API](https://support.appsflyer.com/hc/articles/207034356)<br>- [Unified deep linking API](https://support.appsflyer.com/hc/articles/207032246)<br>- [Get conversion data](https://support.appsflyer.com/hc/articles/360000726098) |
| Developer hand off | Product manager | 5 mins | Prepare and send an email to your developer with instructions and tasks for: <br>- SDK / API integration<br>- In-app event mapping<br>  <br>  These can be found in the [Integrate the SDK](https://hq1.appsflyer.com/onboarding/apps) tab of the add an app wizard. |
| Implementation by developer | App developer | 3 hours | Receive the email from the marketer with instructions and tasks for SDK integration and in-app event mapping.<br>Implement them automatically for Android and iOS using the [AppsFlyer Dev Journey](https://dj.dev.appsflyer.com/?utm_source=dashboard&utm_medium=app-onbrd-mail-a) or manually using the links below.<br>AppsFlyer resources for your developers:<br>- [Android](https://dev.appsflyer.com/hc/docs/install-android-sdk)<br>- [iOS](https://dev.appsflyer.com/hc/docs/install-ios-sdk)<br>- [Unity](https://support.appsflyer.com/hc/articles/360007314277)<br>- [Windows phone](https://support.appsflyer.com/hc/articles/207032026-Windows-Phone-SDK-Download-Integration-Guide)<br>- [Other platforms](https://support.appsflyer.com/hc/sections/6551244207121-Other-platforms) |
| [Integration testing](https://support.appsflyer.com/hc/articles/360001559405) | Product manager/<br>App developer | 1 hour | You can test your SDK integration before or after your app is live in the app store. You can use debug apps to keep your app data clean.<br>For Android and iOS apps only: Be sure to [register your test devices](https://support.appsflyer.com/hc/articles/207031996-Registering-test-devices-). |
| Release new app version | Product manager | 1 hour | [Prepare for iOS App Store review](/docs/preparing-for-the-app-store-review-nutrition-labels). |

**Result:** Your apps are ready for install attribution, in-app event measurement, and other AppsFlyer functionalities that won’t require additional dev resources.

## Step 3: Attribution setup

Complete the following steps for every app defined in AppsFlyer in [Step 1: App setup](https://support.appsflyer.com/hc/articles/207033486#step-2-app-setup):

| Step | Owner | Time | Comments |
| --- | --- | --- | --- |
| Set up **paid** media sources for attribution in AppsFlyer | Product manager/<br>Marketer | 15 mins per media source | Learn about attributing [Self Reporting Networks](https://support.appsflyer.com/hc/articles/360001546905-About-self-reporting-networks-SRNs-) (SRNs), specifically:<br>- [Google Ads](https://support.appsflyer.com/hc/articles/115002504686-Google-Ads-AdWords-guide)<br>- [Meta ads](https://support.appsflyer.com/hc/articles/207033826-Facebook-Ads-setup-guide)<br>- [Apple Search Ads](https://support.appsflyer.com/hc/articles/213747963-Apple-Search-Ads-guide)<br>- [GMP](https://support.appsflyer.com/hc/articles/4410481172625) (Doubleclick)<br>Learn about attributing non-SRN ad networks:<br>- [Other integrated partners](https://support.appsflyer.com/hc/articles/4410395957521)<br>- AppsFlyer [attribution link](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters) structure and parameters |
| Use OneLink to attribute **owned** media sources: mobile websites, social media, user invites, and more | Product manager | 1 hour | Learn about [OneLink-based solutions](https://support.appsflyer.com/hc/articles/115005248543-OneLink-overview#additional-options) for your owned-media use cases |
| Owned media developer implementation | App developer | 0-6.5 hours (depending on the implemented solutions) | For developers: [Getting started with Deep linking](https://dev.appsflyer.com/hc/docs/getting-started-1) |
| Set up attribution windows | Product manager | 2 mins per media source | Learn more: [Click and view-through lookback windows explained](https://support.appsflyer.com/hc/articles/208338403-Lookback-windows-explained) |
| [Optional] Enable retargeting campaigns | Product manager | 2 mins | [Activate Retargeting on the App Settings](https://support.appsflyer.com/hc/articles/211719806-App-settings-#reengagement-attribution) page.<br>Learn more: [Retargeting guide](https://support.appsflyer.com/hc/articles/207033786-Retargeting-Attribution-Guide) |

**Result:** All media sources bringing traffic into your apps are attributed whenever new or returning users engage with them.

## Step 4: Additional setup

Complete the following steps for every app defined in AppsFlyer in [Step 1: App setup.](https://support.appsflyer.com/hc/articles/207033486#step-2-app-setup)

Certain steps may be mandatory to meet your business goals.

| Step | Owner | Additional resources |
| --- | --- | --- |
| Optimize user acquisition campaigns by recording revenue | Product manager/<br>Developers | - [In-app purchase validations](https://support.appsflyer.com/hc/articles/207032106)<br>- [Ad monetization](https://support.appsflyer.com/hc/articles/217490046)<br>- [User subscriptions](https://support.appsflyer.com/hc/articles/360001279189) |
| Learn about methods to aggregate and view marketing cost data | Product manager | [ROI360—cost aggregation overview](/docs/roi360-cost-aggregation-overview) |
| Set up other [3rd-party platforms](https://support.appsflyer.com/hc/sections/6551199962257-3rd-party-platforms) your app works with | Product manager/<br>Developers | - [mParticle](https://support.appsflyer.com/hc/articles/209787323-AppsFlyer-and-mParticle-Integration)<br>- [Segment](https://support.appsflyer.com/hc/articles/210041606-Segment-Integration)<br>- [Mixpanel](https://support.appsflyer.com/hc/articles/207447103-Mixpanel)<br>- [Amplitude](https://support.appsflyer.com/hc/articles/211200306-AppsFlyer-Amplitude-Integration)<br>- [Adobe Analytics](https://support.appsflyer.com/hc/articles/115003326706-AppsFlyer-Integration-with-Adobe-Analytics) (Omniture)<br>- [Braze](https://support.appsflyer.com/hc/articles/115001603343-AppsFlyer-Braze-Formerly-Appboy-Integration) |
| Check out these AppsFlyer premium features that can save you time and money. | Product manager | - [Audiences](https://support.appsflyer.com/hc/articles/115002689186-Audiences)<br>- [Pivot table](https://support.appsflyer.com/hc/articles/115001421846-AppsFlyer-Pivot-)<br>- [Data Locker](https://support.appsflyer.com/hc/articles/360000877538) |
| Protect your campaigns from fraud and mistargeting | Product manager | - [Protect360—Anti-fraud solution](https://support.appsflyer.com/hc/articles/218254203-Protect360-Overview-)<br>- Use [Validation rules](https://support.appsflyer.com/hc/articles/115004703926-Validation-Rules-for-app-owners) to ensure campaigns are not mistargeted |
| Implement Server-to-Server API for in-app events reported outside the app | Product manager/<br>Developers | [S2S REST API](https://support.appsflyer.com/hc/articles/207034486-Server-to-Server-Events-API) |
| Measure uninstall rates for your media sources | Product manager/<br>Developers | [Uninstall measurement](https://support.appsflyer.com/hc/articles/210289286-Uninstall-Measurement) |
| Gain a unified view of customer journeys across channels, platforms, and devices | Product manager/<br>Developers | [People-Based Attribution (PBA)](https://support.appsflyer.com/hc/articles/360002274017-People-Based-Attribution-PBA-getting-started) |
| Ensure compliance with privacy regulations: [GDPR,](https://support.appsflyer.com/hc/articles/360000811585-GDPR) [CCPA](https://support.appsflyer.com/hc/articles/360000811585-GDPR), etc. | Product manager/<br>Developers | Allowing users to [opt-out](https://support.appsflyer.com/hc/articles/360001422989-Opt-Out-Scenarios) of attribution. |

## Enrich your knowledge

Recommended for all AppsFlyer users:

| Step | Time |
| --- | --- |
| Get to know the [AppsFlyer overview dashboard](https://support.appsflyer.com/hc/articles/360014697157-Overview-dashboard-V2) | 15 mins |
| Explore the difference between [Lifetime Value (LTV) data and activity](https://support.appsflyer.com/hc/articles/115005600889-LTV-vs-Activity) data in AppsFlyer (solving the mystery of why the in-app events summary differs between the Overview and Activity dashboards) | 15 mins |
| Understand the AppsFlyer [attribution model](https://support.appsflyer.com/hc/articles/207447053-What-is-AppsFlyer-s-Attribution-Model-) | 30 mins |
| Learn about [aggregate reporting tools and analytics](https://support.appsflyer.com/hc/articles/360005437257) | 30 mins |
| Learn about [raw data reporting](/docs/raw-data-reporting-overview) | 30 mins |

## Related

> 👍 Tip
>
> New to UA (user acquisition)? Learn [all about](https://www.appsflyer.com/resources/ecommerce/getting-started-user-acquisition-apps-complete-guide/) the biggest challenges and critical elements of planning, executing, and continuously optimizing your user acquisition efforts.

> 📘 Note
>
> New to AppsFlyer but not a marketer? No worries!
>
> Choose the guide for you below and get started:
>
> - [Getting started for agencies](https://support.appsflyer.com/hc/articles/360002381617)
> - [Getting started for ad networks](https://support.appsflyer.com/hc/articles/360001300998)
---
title: Getting started—Onboarding for marketers
excerpt: >-
  Get everything set up to make the most of your AppsFlyer account. Understand
  the steps, timelines, and dependencies for getting your apps and your team on
  board.
metadata:
  keywords:
    - SDK
    - Integration
    - Reports
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2015-01-18T11:03:01Z'
  edited_at: '2025-03-25T11:21:10Z'
  id: 207033486
  locale: en-us
  section: Marketer onboarding
  section_id: 6550866490129
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207033486-Getting-started-Onboarding-for-marketers
---
<Embed title="Getting started—Onboarding for marketers" typeOfEmbed="iframe" url="https://fast.wistia.net/embed/iframe/gamcb25kgu" height="417px" />

## Introduction

This document helps marketer (app owner) product managers**plan and execute their onboarding with AppsFlyer**. For every item, the owner and approximate implementation time are provided.

Note that the time estimates in this article are intended as general guidance only. They are based on our experience working with many new customers, but we recognize that every app owner, app, and implementation is different. Your actual time requirements may vary.

## Account setup

The **account admin** should complete the following steps:

| Step | Time | Comments |
| --- | --- | --- |
| [Sign up](https://www.appsflyer.com/get-started/) with AppsFlyer | 5 mins | Ideally, an account admin is a real AppsFlyer user who can receive important messages when needed. |
| [Add account users](/docs/user-management#creating-users) who will use the AppsFlyer dashboard, and set their permissions | 1 min per account user | [In some cases](/docs/user-management#creating-users), users can be added to multiple accounts. |

**Result:** Welcome! You now have an active AppsFlyer account and account users who can access it.

> 📘 **Tip**
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
| [Add your app](/docs/adding-an-app-to-appsflyer) to the AppsFlyer account | 1 min | If adding an app fails, it's often because it was previously defined in a different account (typically an ad agency that your marketers work with). Contact your CSM or hello@appsflyer.com to [transfer the app to your account](/docs/transferring-apps-between-accounts).<br /><br />See additional [troubleshooting steps](/docs/adding-an-app-to-appsflyer#troubleshooting) for adding apps. |
| Set the app [time zone, currency](/docs/adding-an-app-to-appsflyer#enter-additional-information-not-applicable-to-web-apps), and whether it's directed toward children | 1 min |  |
| Set the app's  <br />[re-attribution window](/docs/set-up-re-attribution-window) (on the [App settings](/docs/app-settings#reattribution-window) page) | 1 min | The re-attribution window is the period, starting from the date of the first install, during which **re-installs from the same device are not attributed** as new installs. The default value is 90 days, which you can customize as needed. |
| [Optional] Migrate existing user devices into AppsFlyer | 2 hours | If your app already has a substantial user base, consider [migrating them into AppsFlyer](/docs/migration-to-appsflyer-from-other-vendors#device-migrationoptional) to avoid double charges.<br /><br />**Note:** With the assistance of your AppsFlyer CSM or the support team at [hello@appsflyer.com](mailto:hello@appsflyer.com)). |

**Result:** Your apps are now defined in the AppsFlyer dashboard.

## Step 2: SDK / API integration

Complete the following steps for every app defined in AppsFlyer in [Step 1: App setup](/docs/getting-started-onboarding-for-marketers#step-1-app-setup):

| Step | Owner | Time | Comments |
| --- | --- | --- | --- |
| Consider the available options and select the [SDK functionalities](/docs/sdk-integration-overview) you want your app to use | Product manager | 1 hour | <ul><li>Some considerations beyond basic attribution:<ul><li>Will your campaigns deep link users into the app?</li><li>Will the app need to [access attribution or deep-linking data](/docs/basic-sdk-integration-guide#accessing-attribution-and-deep-linking-data)?</li><li>Should AppsFlyer data contain your [Customer User ID](/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer) for reference?</li><li>How will you implement [privacy settings for iOS 14+](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support) devices? Will you measure uninstalls, run cross-promotion campaigns, and more?</li></ul></li><li>Do you have a CTV app? See our [CTV overview](/docs/ctv-pc-and-console-platform-attribution-concepts).</li></ul> |
| Select which [in-app events](/docs/in-app-events-overview) to record | Product manager | 1 hour | Recording the post-installation events your users perform in the app helps you better understand the **quality** of your users.<br /><br />Visit the [In-app event generator](https://evgen.appsflyer.com/) to use our comprehensive list of [recommended in-app events](/docs/in-app-events-overview#recommended-events-by-business-vertical) and parameters for your vertical. You can add your own events and parameters.  <br />Click the **Code** button to view and copy the automatically generated code for your developers (and make them happy). |
| Select methods for retrieving attribution /deep-linking data | Product manager | 30 mins | Learn more about the available [methods](/docs/basic-sdk-integration-guide#accessing-attribution-and-deep-linking-data):<ul><li>[Pull API](/docs/pull-api-raw-data)</li><li>[Push API](/docs/push-api-streaming-raw-data)</li><li>[Unified deep linking API](/docs/create-a-onelink-template)</li><li>[Get conversion data](/docs/conversion-data-payloads-and-scenarios)</li></ul> |
| Developer hand off | Product manager | 5 mins | Prepare and send an email to your developer with instructions and tasks for:<ul><li>SDK / API integration</li><li>In-app event mapping</li></ul>These can be found in the [Integrate the SDK](https://hq1.appsflyer.com/onboarding/apps) tab of the add an app wizard. |
| Implementation by developer | App developer | 3 hours | Receive the email from the marketer with instructions and tasks for SDK integration and in-app event mapping.<br /><br />Implement them automatically for Android and iOS using the [AppsFlyer Dev Journey](https://dj.dev.appsflyer.com/?utm_source=dashboard&utm_medium=app-onbrd-mail-a) or manually using the links below.<br /><br />AppsFlyer resources for your developers:<ul><li>[Android](https://dev.appsflyer.com/hc/docs/install-android-sdk)</li><li>[iOS](https://dev.appsflyer.com/hc/docs/install-ios-sdk)</li><li>Unity</li><li>[Windows phone](/docs/windows-sdk-integration-for-developers)</li><li>[Other platforms](/docs/other-platforms)</li></ul> |
| [Integration testing](/docs/testing-the-sdk-integration-for-marketers) | Product manager/  <br />App developer | 1 hour | You can test your SDK integration before or after your app is live in the app store. You can use debug apps to keep your app data clean.<br /><br />For Android and iOS apps only: Be sure to [register your test devices](/docs/registering-test-devices). |
| Release new app version | Product manager | 1 hour | [Prepare for iOS App Store review](/docs/preparing-for-the-app-store-review-nutrition-labels). |

**Result:** Your apps are ready for install attribution, in-app event measurement, and other AppsFlyer functionalities that won’t require additional dev resources.

## Step 3: Attribution setup

Complete the following steps for every app defined in AppsFlyer in [Step 1: App setup](/docs/getting-started-onboarding-for-marketers#step-1-app-setup):

| Step | Owner | Time | Comments |
| --- | --- | --- | --- |
| Set up **paid** media sources for attribution in AppsFlyer | Product manager/  <br />Marketer | 15 mins per media source | Learn about attributing [Self Reporting Networks](/docs/self-reporting-networks-srns) (SRNs), specifically:<ul><li>[Google Ads](/docs/google-ads-adwords-integration-setup-for-advertisers)</li><li>[Meta ads](/docs/meta-ads-integration-setup)</li><li>[Apple Search Ads](/docs/apple-ads-integration-setup)</li><li>GMP (Doubleclick)</li></ul>Learn about attributing non-SRN ad networks:<ul><li>[Other integrated partners](/docs/set-up-an-integrated-partner)</li><li>AppsFlyer [attribution link](/docs/about-link-structure-and-parameters) structure and parameters</li></ul> |
| Use OneLink to attribute **owned** media sources: mobile websites, social media, user invites, and more | Product manager | 1 hour | Learn about [OneLink-based solutions](/docs/onelink-guide#additional-options) for your owned-media use cases |
| Owned media developer implementation | App developer | 0-6.5 hours (depending on the implemented solutions) | For developers: [Getting started with Deep linking](https://dev.appsflyer.com/hc/docs/getting-started-1) |
| Set up attribution windows | Product manager | 2 mins per media source | Learn more: [Click and view-through lookback windows explained](/docs/set-up-lookback-windows) |
| [Optional] Enable retargeting campaigns | Product manager | 2 mins | [Activate Retargeting on the App Settings](/docs/app-settings#reengagement-attribution) page.<br /><br />Learn more: [Retargeting guide](/docs/retargeting-attribution-guide) |

**Result:** All media sources bringing traffic into your apps are attributed whenever new or returning users engage with them.

## Step 4: Additional setup

Complete the following steps for every app defined in AppsFlyer in [Step 1: App setup.](/docs/getting-started-onboarding-for-marketers#step-1-app-setup)

Certain steps may be mandatory to meet your business goals.

| Step | Owner | Additional resources |
| --- | --- | --- |
| Optimize user acquisition campaigns by recording revenue | Product manager/  <br />Developers | <ul><li>[In-app purchase validations](/docs/legacy-receipt-validation-for-in-app-purchases)</li><li>[Ad monetization](/docs/roi360-guide-ad-revenue-attribution)</li><li>User subscriptions</li></ul> |
| Learn about methods to aggregate and view marketing cost data | Product manager | [ROI360—cost aggregation overview](/docs/roi360-cost-aggregation-overview) |
| Set up other [3rd-party platforms](/docs/3rd-party-platforms) your app works with | Product manager/  <br />Developers | <ul><li>[mParticle](/docs/mparticle-integration-with-appsflyer)</li><li>[Segment](/docs/segment-integration)</li><li>[Mixpanel](/docs/mixpanel-integration-with-appsflyer)</li><li>[Amplitude](/docs/amplitude-integration-with-appsflyer)</li><li>[Adobe Analytics](/docs/adobe-analytics-integration-with-appsflyer) (Omniture)</li><li>[Braze](/docs/braze-formerly-appboy-integration-with-appsflyer)</li></ul> |
| Check out these AppsFlyer premium features that can save you time and money. | Product manager | <ul><li>[Audiences](/docs/audiences-guide)</li><li>[Pivot table](/docs/pivot-table-user-metrics)</li><li>[Data Locker](/docs/data-locker-for-marketers)</li></ul> |
| Protect your campaigns from fraud and mistargeting | Product manager | <ul><li>[Protect360—Anti-fraud solution](/docs/protect360-anti-fraud-guide)</li><li>Use [Validation rules](/docs/implement-validation-rules-to-prevent-fraud) to ensure campaigns are not mistargeted</li></ul> |
| Implement Server-to-Server API for in-app events reported outside the app | Product manager/  <br />Developers | [S2S REST API](/docs/server-to-server-events-api-for-mobile-s2s-mobile) |
| Measure uninstall rates for your media sources | Product manager/  <br />Developers | Uninstall measurement |
| Gain a unified view of customer journeys across channels, platforms, and devices | Product manager/  <br />Developers | [People-Based Attribution (PBA)](/docs/people-based-attribution-pba-overview) |
| Ensure compliance with privacy regulations: GDPR, CCPA, etc. | Product manager/  <br />Developers | Allowing users to [opt-out](/docs/apply-privacy-preserving-sdk-methods) of attribution. |

## Enrich your knowledge

Recommended for all AppsFlyer users:

| Step | Time |
| --- | --- |
| Get to know the AppsFlyer overview dashboard | 15 mins |
| Explore the difference between [Lifetime Value (LTV) data and activity](/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports) data in AppsFlyer (solving the mystery of why the in-app events summary differs between the Overview and Activity dashboards) | 15 mins |
| Understand the AppsFlyer [attribution model](/docs/appsflyer-attribution-model) | 30 mins |
| Learn about [aggregate reporting tools and analytics](/docs/aggregated-and-analytics-reporting-overview) | 30 mins |
| Learn about [raw data reporting](/docs/raw-data-reporting-overview) | 30 mins |

## Related

> 📘 **Tip**
>
> New to UA (user acquisition)? Learn [all about](https://www.appsflyer.com/resources/ecommerce/getting-started-user-acquisition-apps-complete-guide/) the biggest challenges and critical elements of planning, executing, and continuously optimizing your user acquisition efforts.

> 📘 **Note**
>
> New to AppsFlyer but not a marketer? No worries!
> Choose the guide for you below and get started:
>
> * [Getting started for agencies](/partners/docs/getting-started-agency-onboarding)
> * [Getting started for ad networks](/partners/docs/getting-started-onboarding-guide-for-ad-networks)

<div data-zendesk-anchors="01H8BD2FJ6TQ5FP9625MNP2B3Z=introduction step-1-account-setup=account-setup 01H8BD2FJ6E8KZW41V04SBDQPQ=account-setup 01H8BD2FJ6A39JB8J0PQ3EY52N=tip 01H8V6FS97NTTF1VPQQDZQT973=app-onboarding step-2-app-setup=step-1-app-setup 01H8BD2FJ61S3Z22CD01H6F39E=step-1-app-setup step-3-sdk-integration=step-2-sdk--api-integration 01H8BD2FJ6CY53QXVB5QC98KTT=step-2-sdk--api-integration step-4-attribution-setup=step-3-attribution-setup 01H8BD2FJ6Q8R83FV0XS5B93B3=step-3-attribution-setup step-5-additional-setup=step-4-additional-setup 01H8BD2FJ76WD0MRCJXZH8XABN=step-4-additional-setup 01H8BD2FJ7ZV0ZYHQZ8DBTTFFK=enrich-your-knowledge 01H8BD2FJ748GFC4VJWWYGGN1K=related 01H8BD2FJ712NGA534TCSWQGR8=tip-1 01H8BD2FJ7PRJAA1K8MESRK7VA=note" />

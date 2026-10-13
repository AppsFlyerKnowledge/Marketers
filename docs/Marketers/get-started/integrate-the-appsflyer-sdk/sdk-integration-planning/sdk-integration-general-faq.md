---
title: "SDK integration general FAQ"
excerpt: "Find answers to common questions about integrating, updating, and measuring performance with the AppsFlyer SDK."
x-zendesk:
  id: 207033546
  url: https://support.appsflyer.com/hc/en-us/articles/207033546-SDK-integration-general-FAQ
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SDK integration planning
  section_id: 6551182964369
  position: 6
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Advertisers, Developers, Marketers, Loc In Prog, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2015-01-18T11:13:24Z'
  edited_at: '2026-08-13T12:52:29Z'
---
The AppsFlyer SDK lets you safely advertise your app, attribute, deep-link, and collect behavioral information of your mobile users. You can set up and start working with any ad network and/or platform in a manner of minutes—not weeks or months!

## How to install and update the AppsFlyer SDK?

To learn how to install and update the AppsFlyer SDK, please see [the Dev Hub](https://dev.appsflyer.com/hc/docs/sdk-installation).

> 📘 Note
>
> Upgrading the SDK involves releasing a new version of your app to the stores.

## Is it hard to integrate the AppsFlyer SDK?

In less than an hour, an experienced developer can ready apps for attribution with AppsFlyer. Then, they only need a few minutes per app.

Check out the AppsFlyer SDK integration guides for [Android](/docs/sdk-integration-overview), [iOS](/docs/sdk-integration-overview), Unity, or these [other platforms](/docs/other-platforms).

## Does the AppsFlyer SDK affect app download time?

AppsFlyer SDK packages are designed and coded for a *close-to-zero* effect on app performance. All the SDK versions are lightweight and usually take up less than 1% of an app's size. In other words, **the effect on overall app download time is marginal**.

* **Android SDK:** ~300KB
* **iOS SDK:** ~3.4MB

## Does the AppsFlyer SDK affect app performance?

AppsFlyer SDK APIs are primarily *setter*/*getter* or fast asynchronous web service methods that send/receive data from AppsFlyer servers. This means SDK APIs have a negligible effect on app performance.

In other words, **the AppsFlyer SDK has no effect on app performance or user experience**.

## Can I record in-app events that occur outside my app?

You can use the [S2S API to report events](/docs/server-to-server-events-api-for-mobile-s2s-mobile) that take place outside the app; for example, a user renews their subscription using your web interface. S2S events, once recorded, are available across the platform, including dashboards, raw data, and analytics.
---
title: "SDK integration general FAQ"
excerpt: "Find answers to common questions about integrating, updating, and measuring performance with the AppsFlyer SDK."
---
The AppsFlyer SDK lets you safely advertise your app, attribute, deep-link, and collect behavioral information of your mobile users. You can set up and start working with any ad network and/or platform in a manner of minutes—not weeks or months!

## How to install and update the AppsFlyer SDK?

To learn how to install and update the AppsFlyer SDK, please see [the Dev Hub](https://dev.appsflyer.com/hc/docs/sdk-installation).

> 📘 Note
>
> Upgrading the SDK involves releasing a new version of your app to the stores.

## Is it hard to integrate the AppsFlyer SDK?

In less than an hour, an experienced developer can ready apps for attribution with AppsFlyer. Then, they only need a few minutes per app.

Check out the AppsFlyer SDK integration guides for [Android](https://support.appsflyer.com/hc/articles/207032126), [iOS](https://support.appsflyer.com/hc/articles/207032126), [Unity,](https://support.appsflyer.com/hc/articles/360007314277) or these [other platforms](https://support.appsflyer.com/hc/sections/6551244207121-Other-platforms).

## Does the AppsFlyer SDK affect app download time?

AppsFlyer SDK packages are designed and coded for a *close-to-zero* effect on app performance. All the SDK versions are lightweight and usually take up less than 1% of an app's size. In other words, **the effect on overall app download time is marginal**.

* **Android SDK:** ~300KB
* **iOS SDK:** ~3.4MB

## Does the AppsFlyer SDK affect app performance?

AppsFlyer SDK APIs are primarily *setter*/*getter* or fast asynchronous web service methods that send/receive data from AppsFlyer servers. This means SDK APIs have a negligible effect on app performance.

In other words, **the AppsFlyer SDK has no effect on app performance or user experience**.

## Can I record in-app events that occur outside my app?

You can use the [S2S API to report events](https://support.appsflyer.com/hc/articles/207034486-Server-to-server-events-API-for-mobile-S2S-mobile-) that take place outside the app; for example, a user renews their subscription using your web interface. S2S events, once recorded, are available across the platform, including dashboards, raw data, and analytics.
---
title: "Segment integration"
excerpt: "Learn how to integrate Segment with AppsFlyer to route your analytics data and optimize your mobile attribution."
---
At a glance: Send your Segment analytics data to AppsFlyer.

## Introduction

Segment makes it easy to send your data to AppsFlyer. Once you have recorded your data through Segment's open source libraries, the data is translated and routed to AppsFlyer in the appropriate format. AppsFlyer helps marketers to pinpoint targeting, optimize ad spend, and boost ROI.

## Integrating Segment with AppsFlyer

Follow [this guide from Segment](https://segment.com/docs/destinations/appsflyer/) to learn how to integrate Segment with AppsFlyer.

## FAQs

<Accordion title="How can I integrate Segment with AppsFlyer?">

To integrate Segment with AppsFlyer, follow these steps:

- [Configure your Segment dashboard](https://segment.com/docs/destinations/appsflyer/#getting-started) to connect to AppsFlyer
- Implement [the Segment Wrapper SDK](https://support.appsflyer.com/hc/articles/210041606#how-does-the-sdk-wrapper-work) in your app:

  - [Native iOS](https://github.com/segment-integrations/analytics-swift-appsflyer)
  - [Native Android](https://github.com/segment-integrations/analytics-kotlin-appsflyer)

</Accordion>

<Accordion title="What SDKs do I need to add to my app?">

You only need to add the Segment SDK wrapper. When you add the Segment SDK wrapper dependency, the app build process automatically adds Segment SDK and the AppsFlyer SDK to your app.

</Accordion>

<Accordion title="How does the SDK wrapper work?">

The Segment SDK wrapper connects Segment SDK and the AppsFlyer SDK.

When you use the Segment SDK wrapper to call Segment's methods for recording installs and in-app events, the SDK wrapper calls both Segment's and AppsFlyer methods.

This saves you time and effort and requires less coding.

> 🚧 Warning
>
> **DO NOT USE** methods from both the Segment SDK wrapper and the AppsFlyer SDK. Doing so could lead to errors and data discrepancies.
>
> **Use only methods from the Segment SDK wrapper.**

</Accordion>

<Accordion title="Is there any difference in functionality between the Segment SDK wrapper and the AppsFlyer SDK?">

No, there is no change in functionality. All functions in the AppsFlyer SDK are available in the Segment SDK wrapper.

</Accordion>

<Accordion title="I don't see in-app event data in the AppsFlyer dashboard">

- Make sure to follow the instructions for implementing the track method in Segment SDK wrapper:
  - [Android](https://github.com/AppsFlyerSDK/AppsFlyer-Segment-Integration#adding_events)
  - [iOS](https://github.com/AppsFlyerSDK/segment-appsflyer-ios/blob/master/examples/SwiftPodsSample/SwiftPodsSample/ViewController.swift)
- Make sure to [specify your dev key](https://segment.com/docs/destinations/appsflyer/#getting-started) when integrating AppsFlyer in Segment's dashboard.

</Accordion>

<Accordion title="Install and in-app events data in Segment and AppsFlyer doesn't match">

Make sure that to only use the Segment SDK Wrapper Do not combine the Segment SDK Wrapper with AppsFlyer SDK. See [here](https://support.appsflyer.com/hc/articles/210041606#how-does-the-sdk-wrapper-work) for more info.

[The FAQ above](https://support.appsflyer.com/hc/articles/210041606#i-dont-see-inapp-event-data-in-the-appsflyer-dashboard) also specifies reasons why data might not align between Segment and AppsFlyer.

</Accordion>

<Accordion title="I'm getting a validation error when testing events in Segment">

When you test events using the _**Event Tester**_ in the _**Destination**_ page, you might get an error: _**Validation Error AppsFlyer Device ID ('integrations.AppsFlyer.appsFlyerId') is required to send server to server events**_.

This error doesn't mean that there is an issue with the integration between Segment and AppsFlyer. The Event Tester allows you to test sending server-to-server from Segment to AppsFlyer. Any event that is sent using server-to-server requires the AppsFlyerID which is why the event tester throws the error.

However, this is only relevant for server-to-server events. When you use Segment SDK API to record events, events are sent from the SDK to both Segment and AppsFlyer. For the AppsFlyer API call, the AppsFlyer Device ID is included.

</Accordion>

<Accordion title="I'm using a third-party analytics tool. Should I integrate it with both AppsFlyer and Segment?">

No, you should only use the Segment dashboard to enable the 3rd party analytics tools.

</Accordion>
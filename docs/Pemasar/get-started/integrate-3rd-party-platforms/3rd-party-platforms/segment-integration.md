---
title: Segment integration
metadata:
  keywords:
    - Integration
    - segment IO
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-30T07:54:38Z'
  edited_at: '2025-07-08T07:14:01Z'
  id: 210041606
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/210041606-Segment-integration
---
> **At a glance:** Send your Segment analytics data to AppsFlyer.

## Introduction

Segment makes it easy to send your data to AppsFlyer. Once you have recorded your data through Segment's open source libraries, the data is translated and routed to AppsFlyer in the appropriate format. AppsFlyer helps marketers to pinpoint targeting, optimize ad spend, and boost ROI.

## Integrating Segment with AppsFlyer

Follow <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/">this guide from Segment</Anchor> to learn how to integrate Segment with AppsFlyer.

## FAQs

<div id="how-can-i-integrate-segment-with-appsflyer" />

<Accordion title="How can I integrate Segment with AppsFlyer?">

To integrate Segment with AppsFlyer, follow these steps:

* <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">Configure your Segment dashboard</Anchor> to connect to AppsFlyer
* Implement [the Segment Wrapper SDK](/docs/segment-integration#how-does-the-sdk-wrapper-work) in your app:
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-swift-appsflyer">Native iOS</Anchor>
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-kotlin-appsflyer">Native Android</Anchor>

</Accordion>

<div id="what-sdks-do-i-need-to-add-to-my-app" />

<Accordion title="What SDKs do I need to add to my app?">

You only need to add the Segment SDK wrapper. When you add the Segment SDK wrapper dependency, the app build process automatically adds Segment SDK and the AppsFlyer SDK to your app.

</Accordion>

<div id="how-does-the-sdk-wrapper-work" />

<Accordion title="How does the SDK wrapper work?">

The Segment SDK wrapper connects Segment SDK and the AppsFlyer SDK.

When you use the Segment SDK wrapper to call Segment's methods for recording installs and in-app events, the SDK wrapper calls both Segment's and AppsFlyer methods.

This saves you time and effort and requires less coding.

> ❗️ **Warning**
>
> Warning - **DO NOT USE** methods from both the Segment SDK wrapper and the AppsFlyer SDK. Doing so could lead to errors and data discrepancies.
>
> **Use only methods from the Segment SDK wrapper.**

</Accordion>

<div id="is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk" />

<Accordion title="Is there any difference in functionality between the Segment SDK wrapper and the AppsFlyer SDK?">

No, there is no change in functionality. All functions in the AppsFlyer SDK are available in the Segment SDK wrapper.

</Accordion>

<div id="i-dont-see-inapp-event-data-in-the-appsflyer-dashboard" />

<Accordion title="I don't see in-app event data in the AppsFlyer dashboard">

* Make sure to follow the instructions for implementing the track method in Segment SDK wrapper:
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyer-Segment-Integration#adding_events">Android</Anchor>
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/blob/master/examples/SwiftPodsSample/SwiftPodsSample/ViewController.swift">iOS</Anchor>
* Make sure to <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">specify your dev key</Anchor> when integrating AppsFlyer in Segment's dashboard.

</Accordion>

<div id="install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match" />

<Accordion title="Install and in-app events data in Segment and AppsFlyer doesn't match">

Make sure that to only use the Segment SDK Wrapper Do not combine the Segment SDK Wrapper with AppsFlyer SDK. See [here](/docs/segment-integration#how-does-the-sdk-wrapper-work) for more info.

[The FAQ above](/docs/segment-integration#i-dont-see-inapp-event-data-in-the-appsflyer-dashboard) also specifies reasons why data might not align between Segment and AppsFlyer.

</Accordion>

<div id="im-getting-a-validation-error-when-testing-events-in-segment" />

<Accordion title="I'm getting a validation error when testing events in Segment">

When you test events using the ***Event Tester*** in the ***Destination*** page, you might get an error: ***Validation Error AppsFlyer Device ID ('integrations.AppsFlyer.appsFlyerId') is required to send server to server events***.

This error doesn't mean that there is an issue with the integration between Segment and AppsFlyer. The Event Tester allows you to test sending server-to-server from Segment to AppsFlyer. Any event that is sent using server-to-server requires the AppsFlyerID which is why the event tester throws the error.

However, this is only relevant for server-to-server events. When you use Segment SDK API to record events, events are sent from the SDK to both Segment and AppsFlyer. For the AppsFlyer API call, the AppsFlyer Device ID is included.

</Accordion>

<div id="im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

<Accordion title="I'm using a third-party analytics tool. Should I integrate it with both AppsFlyer and Segment?">

No, you should only use the Segment dashboard to enable the 3rd party analytics tools.

</Accordion>

<div data-zendesk-anchors="h_01JZMD855TA62KQ4AWJ5F6WSDP=introduction h_01JZMD855TNEYZG1MDZY7FWV8S=integrating-segment-with-appsflyer h_01JZMD855TAEBDPAMEAEH66F27=faqs h_01JZMD855T2BXFR1AKRNAA7M51=how-can-i-integrate-segment-with-appsflyer h_01JZMD855TG3WEKQH21JJ1PT43=what-sdks-do-i-need-to-add-to-my-app h_01JZMD855TW07PGDA6QHFWPN67=how-does-the-sdk-wrapper-work h_01JZMD855TNZGKVY2G98FPM22Z=warning h_01JZMD855T0BEENPF0BMQDBFS8=is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk h_01JZMD855TV6J44PAV1A7JCKT5=i-dont-see-inapp-event-data-in-the-appsflyer-dashboard h_01JZMD855TH07JNZBT8CN4026W=install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match h_01JZMD855TY8X2PV1HB8Y0QT6Z=im-getting-a-validation-error-when-testing-events-in-segment h_01JZMD855TCE97QW8TSBEN1DYY=im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

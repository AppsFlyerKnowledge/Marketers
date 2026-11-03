---
title: Measuring push notification re-engagement campaigns
metadata:
  keywords:
    - Re-Engagement
    - push
    - notifications
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2016-01-18T10:03:11Z'
  edited_at: '2026-11-01T13:32:51Z'
  id: 207364076
  locale: en-us
  section: Owned media attribution
  section_id: 6551214397585
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207364076-Measuring-push-notification-re-engagement-campaigns
---
> **At a glance:** Measure push notification campaigns on both iOS and Android.

## Overview

AppsFlyer supports the measurement of push notification campaigns from all push providers, as well as campaigns implemented directly on top of Firebase Cloud Messaging or Apple Push Notification Services (APNS).

There are 2 possible ways to implement the integration:

* By utilizing OneLink links (recommended).
* By sending a JSON object with an `af` key in the push notification's payload.

The conversions display in the Overview dashboard, in the retargeting or unified views.

## How does it work?

Once you've completed the steps in this article, your app will work as follows:

1. You trigger a push notification that contains a OneLink link **or** an `af` key in its payload.
2. The app user receives the push notification and clicks on it.
3. The app loads and the AppsFlyer SDK starts.
4. The SDK processes the payload of the push notification that opened the app.
5. The SDK extracts and sends the attribution data to AppsFlyer.

In the OneLink scenario, if the OneLink is configured to route the user to a specific location in the app, the deep link flow is triggered.

## Prerequisites

Before continuing, make sure that your app has <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide">the AppsFlyer SDK integrated</Anchor> **and** can receive push notifications.

## Steps

To set up push notification measurement, the following steps must be completed:

1. [Create a push notification](/docs/measuring-push-notification-re-engagement-campaigns#1-creating-the-push-notification) that contains a custom data key with the OneLink link **or** an `af` key with a JSON object as its value.
2. [Configure the SDK to resolve the custom key](/docs/measuring-push-notification-re-engagement-campaigns#2-configuring-the-sdk) (done by the app developer).
3. [Test the integration](/docs/measuring-push-notification-re-engagement-campaigns#3-testing-the-integration) by triggering a push notification.
4. [View push notification campaigns performance](/docs/measuring-push-notification-re-engagement-campaigns#4-viewing-push-notification-campaigns-in-the-dashboard) in the dashboard.

<Accordion title="1. Creating the push notification">

First, create a push notification that contains attribution data using one of the following methods.

> 📘 **Note**
>
> In the following demonstration, we're using Firebase as the push provider. The instructions should be applicable to any push provider, with minor differences (if any). Consult the respective push provider's documentation.

<Tabs>
<Tab title="Using OneLink (recommended)">

#### **Using OneLink (recommended)**

This is the recommended method of integrating AppsFlyer with push notifications.

1. Create a <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">OneLink link and set it up for retargeting.</Anchor>  
    **Note**: OneLink short and long URLs are both supported.
2. In the push notification custom data, add the OneLink that contains the attribution data you want to send to AppsFlyer.

> 📘 **Note**
>
> **Firebase example**
>
> In Firebase:
>
>  ![appsflyer-push-custom-data-firebase.png](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)

</Tab>

<Tab title="Using JSON">

<div id="using-json-legacy" />

#### **Using JSON**

> 📘 **Note**
>
> The following documents the JSON-based method of integrating AppsFlyer with push notifications, and is available for backward-compatibility purposes. If you're setting up a new app, use the [recommended OneLink-based solution](/docs/measuring-push-notification-re-engagement-campaigns#using-onelink-recommended).

In the push notification's custom data, add a custom key called `af` that contains the attribution data you want to send to AppsFlyer in JSON format. The following attribution parameters are required:

* `pid`
* `is_retargeting`
* `c`

> 📘 **Note**
>
> **Firebase example**
>
> In Firebase:
>
>  ![appsflyer-push-custom-data-firebase-json.png](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)

</Tab>
</Tabs>

</Accordion>

<Accordion title="2. Configuring the SDK">

This task requires changes to the app code. Follow the instructions on how to configure the SDK:

* When implementing the recommended OneLink-based solution:
  1. let the app developer know what's the name of the custom key you added to the notification. In this example, it's `af_push_link`.
  2. Send them <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-using-onelink-recommended">these instructions</Anchor>.
* When implementing the legacy JSON-based solution, send your developers <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-legacy">these instructions</Anchor>.

</Accordion>

<Accordion title="3. Testing the integration">

To test that push notification measurement is integrated correctly, simply trigger a push notification in the campaign you set up in Step 1.

If everything is configured properly, the SDK will:

1. Listen to push notifications.
2. Process the attribution data embedded in the push notification and send it to AppsFlyer.
3. Proceed with the regular deep linking flow, if push notification measurement is implemented using OneLink.

</Accordion>

<Accordion title="4. Viewing push notification campaigns in the dashboard">

You can see data originating from push notifications in the <Anchor target="_blank" href="/marketers/docs/retargeting-attribution-guide#retargeting-dashboard">Retargeting dashboard</Anchor>.

**Note**: AppsFlyer deduplicates push notification data. Meaning, if identical payloads are received more than once, only one is counted.

</Accordion>

<div data-zendesk-anchors="h_01J5XFSEG9DR31DP73KTAGQPFW=overview h_01J5XFSEG967HXNT3GFSC2AQYE=how-does-it-work h_01J5XFSEG91SER3JKB3RKK6B6G=prerequisites h_01J5XFSEG9W3RTP62NW7SV4D0F=steps h_01J5XFSEG9W73JYPHH9VRZSTZ8=using-onelink-recommended h_01J5XFSEG9V46T6XSG31J4AVET=using-json-legacy" />

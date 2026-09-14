---
title: "Salesforce Marketing Cloud MobilePush integration setup"
excerpt: "Learn how to integrate Salesforce Marketing Cloud MobilePush with AppsFlyer to drive engagement, gain user insights, and attribute push notification campaigns."
---
Salesforce Marketing Cloud MobilePush, an AppsFlyer integrated partner, is a user engagement platform for marketing, growth, and engagement teams.

## Overview

Salesforce Marketing Cloud MobilePush allows you to create and send targeted push messages based on cross-channel consumer data. This helps encourage app usage and deliver increased ROI. With MobilePush, you can view how users navigate through your app, from the products they view to the time spent on each page. Integrating MobilePush allows you to:

- Drive engagement and mCommerce
- Gain valuable user insight
- Easily build cross-channel campaigns
- Segment and schedule messages

> ❗️ Important!
>
> [Some media sources](https://support.appsflyer.com/hc/articles/360006868017-Raw-data-content-restriction-media-source-or-user-identifiers#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Salesforce Marketing Cloud MobilePush

Most of the setup is done in Salesforce (steps 1-4). Step 5 is done in AppsFlyer.

### Step 1: Set up MobilePush SDK

- [Implement the MobilePush SDK setup](https://help.salesforce.com/s/articleView?id=sf.mc_mp_get_started.htm&type=5)

### Step 2: Provision for push notifications

- [Create a `.p12` certificate](https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-provision.html)

### Step 3: Enable app push notifications

- [Implement push notifications](https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-configureforpush.html)

### Step 4: Set up app push notifications

- [Create and send push messages to mobile devices](https://help.salesforce.com/s/articleView?id=sf.mc_mp_outbound_message.htm&type=5)

> 📘 Note
>
> When creating a push notification on Salesforce marketing cloud, a [custom key](https://help.salesforce.com/s/articleView?id=sf.mc_mp_custom_keys.htm&type=5) needs to be added so that AppsFlyer can properly attribute with the correct PID and campaign attributes. Use `AF_xxxxxxxxx` as the custom key.

### Step 5: Set up push notifications in AppsFlyer

- [Configure the iOS SDK using OneLink (step 3 in this link)](https://dev.appsflyer.com/hc/docs/push-notifications-ios#addpushnotificationdeeplinkpath-recommended)

> 📘 Note
>
> Make sure the `AF_xxxxxxxxx` custom key you entered in [step 4](https://support.appsflyer.com/hc/articles/10590769196817#step-4-set-up-app-push-notifications) has the same value as the one entered in the `addPushNotificationDeepLinkPath` function.
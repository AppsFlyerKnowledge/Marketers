---
title: Salesforce Marketing Cloud MobilePush integration setup
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-14T06:37:05Z'
  edited_at: '2023-09-10T07:54:37Z'
  id: 10590769196817
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/10590769196817-Salesforce-Marketing-Cloud-MobilePush-integration-setup
---
> **At a glance:** Salesforce Marketing Cloud MobilePush, an AppsFlyer integrated partner, is a user engagement platform for marketing, growth, and engagement teams.

<div id="overview" />

## Overview

Salesforce Marketing Cloud MobilePush allows you to create and send targeted push messages based on cross-channel consumer data. This helps encourage app usage and deliver increased ROI. With MobilePush, you can view how users navigate through your app, from the products they view to the time spent on each page. Integrating MobilePush allows you to:

* Drive engagement and mCommerce
* Gain valuable user insight
* Easily build cross-channel campaigns
* Segment and schedule messages

<div id="important" />

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions#media-source-restrictions">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

<div id="setting-up-salesforce-marketing-cloud-mobilepush" />

## Setting up Salesforce Marketing Cloud MobilePush

Most of the setup is done in Salesforce (steps 1-4). Step 5 is done in AppsFlyer.

<div id="step-1-set-up-mobilepush-sdk" />

### Step 1: Set up MobilePush SDK

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_get_started.htm&type=5">Implement the MobilePush SDK setup</Anchor>

<div id="step-2-provision-for-push-notifications" />

### Step 2: Provision for push notifications

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-provision.html">Create a `.p12` certificate</Anchor>

<div id="step-3-enable-app-push-notifications" />

### Step 3: Enable app push notifications

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-configureforpush.html">Implement push notifications</Anchor>

<div id="step-4-set-up-app-push-notifications" />

### Step 4: Set up app push notifications

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_outbound_message.htm&type=5">Create and send push messages to mobile devices</Anchor>

<div id="note" />

> 📘 **Note**
>
> When creating a push notification on Salesforce marketing cloud, a <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_custom_keys.htm&type=5">custom key</Anchor> needs to be added so that AppsFlyer can properly attribute with the correct PID and campaign attributes. Use `AF_xxxxxxxxx` as the custom key.

<div id="step-5-set-up-push-notifications-in-appsflyer" />

### Step 5: Set up push notifications in AppsFlyer

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications-ios#addpushnotificationdeeplinkpath-recommended">Configure the iOS SDK using OneLink (step 3 in this link)</Anchor>

<div id="note-1" />

> 📘 **Note**
>
> Make sure the `AF_xxxxxxxxx` custom key you entered in [step 4](/docs/salesforce-marketing-cloud-mobilepush-integration-setup#step-4-set-up-app-push-notifications) has the same value as the one entered in the `addPushNotificationDeepLinkPath` function.

<div data-zendesk-anchors="h_01H9HWK3F5TQZ8YQZBHGBZACPG=overview h_01H9HWK5DM87JTDVFND0KB965G=important h_01H9HWK3F52YGQPX4B82N40PPD=setting-up-salesforce-marketing-cloud-mobilepush h_01H9HWK3F5HCVZ0225MFRYRW5Q=step-1-set-up-mobilepush-sdk h_01H9HWK3F5RNCZG340E0CT5XJC=step-2-provision-for-push-notifications h_01H9HWK3F5E4W8FG35V4JTFN7F=step-3-enable-app-push-notifications h_01H9HWK3F5K8V8AVADXNNG25GY=step-4-set-up-app-push-notifications h_01H9HWK3F5VG2GBCE93B69AADH=note h_01H9HWK3F5YJ71YCWHV4B02VYP=step-5-set-up-push-notifications-in-appsflyer h_01H9HWK3F5T67NSPE9CVPS1KTA=note-1" />

---
title: Texting desktop users a link to your mobile app
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2019-11-21T09:13:52Z'
  edited_at: '2026-05-05T06:54:49Z'
  id: 360003799658
  locale: en-us
  section: Owned media attribution
  section_id: 6551214397585
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360003799658-Texting-desktop-users-a-link-to-your-mobile-app
---
> **At a glance:** Convert desktop users to mobile app users using SMS vendors and OneLink.

![text-me-the-app-web-form.png](https://files.readme.io/d28b843ab7528138b4d85b147b8d613efde740d354238227b0f123030fa3a1de-360004940018.png)

<div id="introduction" />

## Introduction

If your brand has both a web app and a mobile app, desktop web users might decide at some point that they want to install the mobile app.

To help them do so and for better user experience, you can text them a direct link to the app. This is the quickest way to help them install the app.

This way, they don't have to open the app store on their mobile, find your app, and install it. When you save users time and effort, they are more likely to convert and install your mobile app.

<div id="note" />

> 📘 **Note**
>
> We offer another solution for <Anchor target="_blank" href="/marketers/docs/qr-to-app-conversion">desktop-to-web conversion</Anchor> that simply requires you to post a QR code (generated from your OneLink) to your desktop site.

<div id="requirements" />

## Requirements

To text desktop users a link to your mobile app, you need the following:

1. An SMS provider account like Twilio, AWS SNS, or bandwidth.com.
2. A backend environment where you can handle the logic for texting links to users.
3. A multi-platform custom link such as <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>.

<div id="setting-up" />

## Setting up

The following section is a high-level overview of the requirements discussed earlier.

<div id="sms-provider-account-to-text-a-link-to-the-app" />

### SMS provider account to text a link to the app

Create an account with any SMS provider. Then, you can send links to your mobile app to a large number of users at any given time.

See the list that follows for some popular providers that support a variety of programming languages and have comprehensive APIs for various use cases:

* <Anchor target="_blank" href="https://www.twilio.com/docs/sms/send-messages">Twilio</Anchor>
* <Anchor target="_blank" href="https://dev.bandwidth.com/messaging/about.html">bandwidth</Anchor>
* <Anchor target="_blank" href="https://docs.aws.amazon.com/sns/latest/dg/sns-mobile-phone-number-as-subscriber.html">AWS SNS</Anchor>
* <Anchor target="_blank" href="https://www.braze.com/docs/user_guide/message_building_by_channel/sms/create/">Braze</Anchor>
* <Anchor target="_blank" href="https://www.airship.com/platform/channels/sms/">Airship</Anchor>
* [Swrve](https://docs.swrve.com/user-documentation/campaigns/campaign-channels/intro-to-sms/)
* <Anchor target="_blank" href="https://help.mixpanel.com/hc/en-us/articles/115004730066-Send-SMS-Messages-From-Mixpanel">Mixpanel</Anchor>

<div id="a-backend-environment-to-communicate-with-the-sms-provider" />

### A backend environment to communicate with the SMS provider

SMS providers require authentication tokens to use their services. In addition, user phone numbers are sensitive data. Due to these aspects, the best thing to do is to handle everything from your backend.

<div id="a-multi-platform-custom-link" />

### A multi-platform custom link

A multi-platform custom link redirects the user to the correct app store or destination according to the device they have. This way you can send the same link to any user no matter what device they have.

<div id="texting-the-app-to-users" />

## Texting the app to users

This section describes the flow of texting users a link to the app. It also explains how to follow up on the number of users that install the app from the link.

<div id="create-a-multi-platform-onelink" />

### Create a multi-platform OneLink

Create a multi-platform OneLink to put in the SMS. When you create the link, you have the option to define the media source and campaign. We suggest that you set the media source and campaign as follows:

* media source: website
* campaign: text-me-the-app

When sending OneLink in SMS, it's best to use the short link version of the OneLink.

To learn how to create the link, see <Anchor target="_blank" href="/marketers/docs/onelink-guide">here</Anchor>.

<div id="set-up-an-sms-topic-in-your-sms-provider-account" />

### Set up an SMS topic in your SMS provider account

In this step, you create an SMS topic or message that contains the OneLink to the app. This SMS is sent when users fill out and submit a form with their phone number. When users submit the form, your backend receives the request and communicates with the SMS provider API to send the link.

<div id="set-up-a-web-form-to-collect-phone-numbers" />

### Set up a web form to collect phone numbers

On your website, at pages of your choice, set up a call-to-action to prompt users to install your app. The call-to-action should open a web form through which users can submit their phone numbers.

<div id="apply-logic-in-your-backend" />

### Apply logic in your backend

On submitting the form, the website should send a request to your backend. The backend receives the phone number and sends a request to the SMS provider to text a link to the app to the user's phone.

Refer to your SMS provider API and documentation to learn how to create the logic in your backend.

<div id="how-attribution-works-when-sending-a-link-to-the-app" />

## How Attribution works when sending a link to the app

 There's no way to include the advertising ID when texting desktop users a link to the app. Therefore, AppsFlyer resorts to <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#probabilistic-modeling">attribution using Probabilistic modeling</Anchor>.

AppsFlyer <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows#probabilistic-modeling-lookback-window">limits the lookback window</Anchor> for Probabilistic modeling clicks to maintain accuracy. The limits are:

* iOS: up to 24 hours
* Android (Google Play): up to one hour
* Android (out-of-store): up to 24 hours

Encourage your users to install as close as possible to the click so that AppsFlyer can accurately attribute the install to the texted link. You can do so by offering coupons, discounts, or game credits.

<div id="people-based-attribution" />

## People-based attribution

There are more ways, other than texting a link to the app, in which users convert from web to app. It's not always clear where these users come from and what media sources and campaigns contribute to their conversion.

To get more insights into how many web users convert to mobile apps users, and what media sources and campaigns are involved in the process, use People-based attribution.

People-based attribution (PBA) puts together data from both web and mobile app campaigns. The consolidated data helps you analyze user journeys across platforms and user transition from web to mobile apps.

To learn more, see <Anchor target="_blank" href="/marketers/docs/people-based-attribution-pba-overview">here</Anchor>.

<div data-zendesk-anchors="h_01KQS4E94MVN7NEEDR7ESA17K9=introduction h_01KQS4E94MSP2PQ0RVAHS2JY8R=note h_01KQS4E94MVYA0EZ7Y0FCMZEBC=requirements h_01KQS4E94MF2BZZ5AXP67R7YRW=setting-up h_01KQS4E94MYPEBKN80CNHCV1DG=sms-provider-account-to-text-a-link-to-the-app h_01KQS4E94MW7DWRGPNX8D98W46=a-backend-environment-to-communicate-with-the-sms-provider a-multiplatform-custom-link=a-multi-platform-custom-link h_01KQS4E94MP2Q29S7892GGT0QM=a-multi-platform-custom-link h_01KQS4E94MGBCX0TM5AGHXPX0Z=texting-the-app-to-users create-a-multiplatform-onelink=create-a-multi-platform-onelink h_01KQS4E94MQSWQ9S0CHNJG8B77=create-a-multi-platform-onelink h_01KQS4E94MG7KGB8HQVT11717J=set-up-an-sms-topic-in-your-sms-provider-account h_01KQS4E94MNPRC5AJ9EJD4GPG3=set-up-a-web-form-to-collect-phone-numbers h_01KQS4E94MA810B0QRSMDQ0FQM=apply-logic-in-your-backend h_01KQS4E94MC8C19RCCPV52G7N1=how-attribution-works-when-sending-a-link-to-the-app peoplebased-attribution=people-based-attribution h_01KQS4E94MJ0C6Q82H67R22S2W=people-based-attribution" />

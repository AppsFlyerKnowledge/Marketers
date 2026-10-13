---
title: "Texting desktop users a link to your mobile app"
excerpt: "Convert desktop users to mobile app users using SMS vendors and OneLink."
x-zendesk:
  id: 360003799658
  url: https://support.appsflyer.com/hc/en-us/articles/360003799658-Texting-desktop-users-a-link-to-your-mobile-app
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Owned media attribution
  section_id: 6551214397585
  position: 3
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, QR-to-App]
  labels: [Advertisers, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2019-11-21T09:13:52Z'
  edited_at: '2026-05-05T06:54:49Z'
---
![text-me-the-app-web-form.png](https://files.readme.io/d28b843ab7528138b4d85b147b8d613efde740d354238227b0f123030fa3a1de-360004940018.png)

## Introduction

If your brand has both a web app and a mobile app, desktop web users might decide at some point that they want to install the mobile app.

To help them do so and for better user experience, you can text them a direct link to the app. This is the quickest way to help them install the app.

This way, they don't have to open the app store on their mobile, find your app, and install it. When you save users time and effort, they are more likely to convert and install your mobile app.

> 📘 Note
>
> We offer another solution for desktop-to-web conversion that simply requires you to post a QR code (generated from your OneLink) to your desktop site.

## Requirements

To text desktop users a link to your mobile app, you need the following:

1. An SMS provider account like Twilio, AWS SNS, or bandwidth.com.
2. A backend environment where you can handle the logic for texting links to users.
3. A multi-platform custom link such as [OneLink](/docs/onelink-guide).

## Setting up

The following section is a high-level overview of the requirements discussed earlier.

### SMS provider account to text a link to the app

Create an account with any SMS provider. Then, you can send links to your mobile app to a large number of users at any given time.

See the list that follows for some popular providers that support a variety of programming languages and have comprehensive APIs for various use cases:

- [Twilio](https://www.twilio.com/docs/sms/send-messages)
- [bandwidth](https://dev.bandwidth.com/messaging/about.html)
- [AWS SNS](https://docs.aws.amazon.com/sns/latest/dg/sns-mobile-phone-number-as-subscriber.html)
- [Braze](https://www.braze.com/docs/user_guide/message_building_by_channel/sms/create/)
- [Airship](https://www.airship.com/platform/channels/sms/)
- [Swrve](https://docs.swrve.com/user-documentation/campaigns/campaign-channels/intro-to-sms/)
- [Mixpanel](https://help.mixpanel.com/hc/en-us/articles/115004730066-Send-SMS-Messages-From-Mixpanel)

### A backend environment to communicate with the SMS provider

SMS providers require authentication tokens to use their services. In addition, user phone numbers are sensitive data. Due to these aspects, the best thing to do is to handle everything from your backend.

### A multi-platform custom link

A multi-platform custom link redirects the user to the correct app store or destination according to the device they have. This way you can send the same link to any user no matter what device they have.

## Texting the app to users

This section describes the flow of texting users a link to the app. It also explains how to follow up on the number of users that install the app from the link.

### Create a multi-platform OneLink

Create a multi-platform OneLink to put in the SMS. When you create the link, you have the option to define the media source and campaign. We suggest that you set the media source and campaign as follows:

- media source: website
- campaign: text-me-the-app

When sending OneLink in SMS, it's best to use the short link version of the OneLink.

To learn how to create the link, see [here](/docs/onelink-guide).

### Set up an SMS topic in your SMS provider account

In this step, you create an SMS topic or message that contains the OneLink to the app. This SMS is sent when users fill out and submit a form with their phone number. When users submit the form, your backend receives the request and communicates with the SMS provider API to send the link.

### Set up a web form to collect phone numbers

On your website, at pages of your choice, set up a call-to-action to prompt users to install your app. The call-to-action should open a web form through which users can submit their phone numbers.

### Apply logic in your backend

On submitting the form, the website should send a request to your backend. The backend receives the phone number and sends a request to the SMS provider to text a link to the app to the user's phone.

Refer to your SMS provider API and documentation to learn how to create the logic in your backend.

## How Attribution works when sending a link to the app

There's no way to include the advertising ID when texting desktop users a link to the app. Therefore, AppsFlyer resorts to [attribution using Probabilistic modeling](/docs/appsflyer-attribution-model#probabilistic-modeling).

AppsFlyer [limits the lookback window](/docs/set-up-lookback-windows#probabilistic-modeling-lookback-window) for Probabilistic modeling clicks to maintain accuracy. The limits are:

- iOS: up to 24 hours
- Android (Google Play): up to one hour
- Android (out-of-store): up to 24 hours

Encourage your users to install as close as possible to the click so that AppsFlyer can accurately attribute the install to the texted link. You can do so by offering coupons, discounts, or game credits.

## People-based attribution

There are more ways, other than texting a link to the app, in which users convert from web to app. It's not always clear where these users come from and what media sources and campaigns contribute to their conversion.

To get more insights into how many web users convert to mobile apps users, and what media sources and campaigns are involved in the process, use People-based attribution.

People-based attribution (PBA) puts together data from both web and mobile app campaigns. The consolidated data helps you analyze user journeys across platforms and user transition from web to mobile apps.

To learn more, see [here](/docs/people-based-attribution-pba-overview).
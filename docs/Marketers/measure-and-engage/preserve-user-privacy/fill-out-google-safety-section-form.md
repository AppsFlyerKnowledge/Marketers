---
title: "Fill out Google safety section form"
excerpt: "This guide provides information to assist you in answering the Google Play Data safety section questionnaire in relation to what AppsFlyer processes on your behalf."
x-zendesk:
  id: 4417197430289
  url: https://support.appsflyer.com/hc/en-us/articles/4417197430289-Fill-out-Google-safety-section-form
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Preserve user privacy
  section_id: 6551440878097
  position: 4
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Google Play, Marketers, Loc Published]
  promoted: false
  comments_disabled: false
  created_at: '2022-01-19T15:00:21Z'
  edited_at: '2025-06-03T07:48:01Z'
---
As of April 2022, app developers are required to complete the Google Play Data safety section form and publish a link to a privacy policy, even if they don’t collect any of the data types specified by Google. This page is intended to provide information to assist you in answering the Google Safety Section Questionnaire, only in relation to what AppsFlyer processes on behalf of customers.

Customers should work closely with legal and other professional advisors to determine exactly how Google policies apply to them and should adapt their responses in line with their specific configurations and uses.

> 📘 Disclaimer
>
> The information contained in this article is intended to assist in answering the Google Safety Section Questionnaire in relation **only** to what AppsFlyer processes on behalf of customers.
>
> It is provided for information and convenience purposes only. Customers should work closely with legal and other professional advisors to determine exactly how Google policies apply to them and should adapt their responses in line with their specific configurations and uses.

## Introduction

As of April 2022, app developers will be required to provide information related to their privacy practices through the Google dedicated safety section. Specifically, app developers will need to provide details on the data they collect, how it is handled and shared, including through their use of any third-party SDKs.

The information provided by each app will be displayed in the Google store listing helping end-users better understand an app’s privacy practices.

## Audience

All app developers will be required to complete the safety section questionnaire and publish a link to a privacy policy even if they do not collect any of the data types specified by Google.

## Google safety form (questionnaire)

Google has published a form (questionnaire) that app developers will be required to complete. The questionnaire includes the following sections:

- Data collection and security
- Data types
- Data usage and handling

App developers will need to first assess their data collection and handling practices before responding to the questionnaire.

With respect to the use of AppsFlyer, app developers are reminded that they have full control over how they implement and configure AppsFlyer, including the data collected and how it is used. Therefore, each app developer may have different answers to the questionnaire based on their data practices and use of AppsFlyer.

App developers must respond to the questionnaire in accordance with their specific use cases, configurations, and partner integrations.

### Data collection and security

In this section, you will be asked a few general yes/no questions:

1. Does your app collect or share any of the required data types?
2. Is all of the user data collected by your app encrypted in transit?
3. Do you provide a way for users to request that their data be deleted?

With respect to your use of AppsFlyer, AppsFlyer encrypts all data in transit that is transmitted through the SDK. AppsFlyer also provides customers with the ability to delete specific end-user data through its OpenGDPR framework. For the data types collected, see the table in the Data types section.

### Data types

In this section, you will be asked to select the data types collected and respond to the following:

1. If the data is shared
2. Is the data processed ephemerally
3. Is the data required or can end-users opt-out
4. The purpose

The following table assumes AppsFlyer software default configurations. App developers are responsible for ensuring that they adapt accordingly in line with their specific configurations and uses.

“Collected” means data transmitted off of the device by any means (for example, webview, or SDK).  An exception is if end-to-end encryption is used making the data unreadable to anyone.

| Data type | AppsFlyer default data collection | Notes |
| --- | --- | --- |
| Location Info<br />- Approximate Location<br />- Precise Location | See notes -> | Precise Location: No<br />Approximate Location: Yes, the IP address is received and mapped to a region/city level. |
| Personal Info<br />- Name<br />- Email Address<br />- Personal identifiers (account ID, number, or name)<br />- Address<br />- Phone Number<br />- Race and ethnicity<br />- Political or religious beliefs<br />- Sexual orientation or gender identity<br />- Other personal info | See notes -> | Personal info should not be collected, and AppsFlyer restricts the collection of such personal data like name and address. However, if app developers have configured to transmit hashed emails or hashed phone numbers or they have configured a customer user account ID (CUID) they will need to respond accordingly. |
| Financial Info<br />- Credit card, debit card, or bank account number<br />- Purchase history<br />- Credit info<br />- Other financial info | No<br />Optional<br />No<br />No | Financial information such as credit cards and credit information should not be collected.<br />If you are measuring in-app purchases (purchase history) you should respond **Yes** |
| Health and Fitness<br />- Health information<br />- Fitness information | No | Should not be collected |
| Messages<br />- Emails<br />- SMS or MMS messages<br />- Other in-app messages | No | Should not be collected |
| Photos or Videos<br />- Photos<br />- Videos | No | Should not be collected |
| Audio Files<br />- Voice or sound recordings<br />- Music files<br />- Other audio files | No | Should not be collected |
| Calendar<br />- Calendar events | No | Should not be collected |
| App activity<br />- Pageviews and taps in-app<br />- In-app search history<br />- Installed apps<br />- Other user-generated content<br />- Other actions | See notes -> | AppsFlyer by default measures app launches which may be deemed page views or other actions.<br />Furthermore, if you configure your app to measure specific in-app events you should respond Yes in accordance with your configurations. |
| Web browsing | No | Should not be collected |
| App info and performance<br />- Crash logs<br />- Diagnostics<br />- Other app performance data | No<br />Yes<br />Yes | Launch time or battery levels may be received for fraud detection purposes |
| Device or other identifiers<br />- Device or other identifiers (for example, IMEI, MAC, and Ad ID) | See notes -> | The AppsFlyer Android SDK, by default collect the Google Advertiser Identifier (GAID). <br />You can disable the collection of the Advertising ID in the SDK by [revoking AD_ID permission](https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission) and by calling [setDisableAdvertisingIdentifiers](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib). |

“Shared” means the transfer of data to a third party (whether off or on the device).

Exceptions include the following:

- Transfers to service providers that process the data on your behalf and per your instructions
- Transfers required for legal purposes (for example, in response to a government request)
- End-user action or based on a prominent in-app disclosure and consent
- Anonymous data

It is important to note that while AppsFlyer acts solely as a service provider on your behalf and per your instructions if you are sharing data with third-party networks (for example, through postbacks, SRN’s, and audiences ) this would be deemed sharing.  Therefore, each app developer will need to assess his configurations and partner integrations and respond accordingly.

## Ephemeral processing

Ephemeral processing refers to data processed in memory, only for the period of time needed to process a specific action in real-time and for no other purpose. Given the nature of the AppsFlyer services, the data processed by AppsFlyer on your behalf is not processed ephemerally.

## User choice

In general, the data collected is required to perform the services. With that said, app developers have the ability to subject any data collection to opt-in or opt-out controls.

## Purpose

Google has provided a list of purposes from which app developers must choose as detailed in the table that follows. You must identify the relevant purpose.

| Purpose | Notes |
| --- | --- |
| App functionality | Select if you use the data to enable any features in the app |
| Analytics | Yes |
| Developer communications | Select if you use the data to send any notifications to users |
| Advertising and marketing | Select if you share the data type with a third party for the purpose of displaying third-party ads or if used to promote products or send push notifications |
| Fraud, prevention, security, and compliance | Yes |
| Personalization | Select if you use the data for any type of product personalization |
| Account management | Select if you use the data for the setup and management of user accounts |

<Cards>
  <Card title="Preparing for Google Play's new safety section" href="https://android-developers.googleblog.com/2021/07/new-google-play-safety-section.html" icon="fa-solid fa-sack-dollar">
    Read the official Android developers blog post about the safety section.
  </Card>
  <Card title="Provide information for Google Play's Data safety section" href="https://support.google.com/googleplay/android-developer/answer/10787469" icon="fa-solid fa-sack-dollar">
    Review Google's developer support guide on completing the form.
  </Card>
</Cards>
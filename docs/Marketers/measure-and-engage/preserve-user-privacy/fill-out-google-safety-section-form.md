---
title: Fill out Google safety section form
metadata:
  keywords:
    - Google Play
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-19T15:00:21Z'
  edited_at: '2025-06-03T07:48:01Z'
  id: 4417197430289
  locale: en-us
  section: Preserve user privacy
  section_id: 6551440878097
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4417197430289-Fill-out-Google-safety-section-form
---
> **At a glance**: As of April 2022, app developers are required to complete the Google Play Data safety section form and publish a link to a privacy policy, even if they don’t collect any of the data types specified by Google. This page is intended to provide information to assist you in answering the Google Safety Section Questionnaire, only in relation to what AppsFlyer processes on behalf of customers.

Customers should work closely with legal and other professional advisors to determine exactly how Google policies apply to them and should adapt their responses in line with their specific configurations and uses.

#### **Disclaimer**

The information contained in this article is intended to assist in answering the Google Safety Section Questionnaire in relation **only** to what AppsFlyer processes on behalf of customers.

It is provided for information and convenience purposes only. Customers should work closely with legal and other professional advisors to determine exactly how Google policies apply to them and should adapt their responses in line with their specific configurations and uses.

## Introduction

As of April 2022, app developers will be required to provide information related to their privacy practices through the Google dedicated safety section. Specifically, app developers will need to provide details on the data they collect, how it is handled and shared, including through their use of any third-party SDKs.

The information provided by each app will be displayed in the Google store listing helping end-users better understand an app’s privacy practices.

## Audience

All app developers will be required to complete the safety section questionnaire and publish a link to a privacy policy even if they do not collect any of the data types specified by Google.

## Google safety form (questionnaire)

Google has published a form (questionnaire) that app developers will be required to complete. The questionnaire includes the following sections:

* Data collection and security
* Data types
* Data usage and handling

App developers will need to first assess their data collection and handling practices before responding to the questionnaire.

With respect to the use of AppsFlyer, app developers are reminded that they have full control over how they implement and configure AppsFlyer, including the data collected and how it is used. Therefore, each app developer may have different answers to the questionnaire based on their data practices and use of AppsFlyer.

App developers must respond to the questionnaire in accordance with their specific use cases, configurations, and partner integrations.

### Data collection and security

In this section, you will be asked a few general yes/no questions:

1. Does your app collect or share any of the required data types?
2. Is all of the user data collected by your app encrypted in transit?
3. Do you provide a way for users to request that their data be deleted?

With respect to your use of AppsFlyer, AppsFlyer encrypts all data in transit that is transmitted through the SDK. AppsFlyer also provides customers with the ability to delete specific end-user data through its OpenGDPR framework. For the data types collected, see the table in the [Data types](/docs/fill-out-google-safety-section-form#data-types) section.

### Data types

In this section, you will be asked to select the data types collected and respond to the following:

1. If the data is shared
2. Is the data processed ephemerally
3. Is the data required or can end-users opt-out
4. The purpose

The following table assumes AppsFlyer software default configurations. App developers are responsible for ensuring that they adapt accordingly in line with their specific configurations and uses.

“Collected” means data transmitted off of the device by any means (for example, webview, or SDK).  An exception is if end-to-end encryption is used making the data unreadable to anyone.

| Data type | AppsFlyer default data collection | Notes |
| --- | --- | --- |
| Location Info<ul><li>Approximate Location</li><li>Precise Location</li></ul> | See notes -> | Precise Location: No<br /><br />Approximate Location: Yes, the IP address is received and mapped to a region/city level. |
| Personal Info<ul><li>Name</li><li>Email Address</li><li>Personal identifiers (account ID, number, or name)</li><li>Address</li><li>Phone Number</li><li>Race and ethnicity</li><li>Political or religious beliefs</li><li>Sexual orientation or gender identity</li><li>Other personal info</li></ul> | See notes -> | Personal info should not be collected, and AppsFlyer restricts the collection of such personal data like name and address. However, if app developers have configured to transmit hashed emails or hashed phone numbers or they have configured a customer user account ID (CUID) they will need to respond accordingly. |
| Financial Info<ul><li>Credit card, debit card, or bank account number</li><li>Purchase history</li><li>Credit info</li><li>Other financial info</li></ul> | No  <br />  <br />Optional<br /><br />No  <br />No | Financial information such as credit cards and credit information should not be collected.<br /><br />If you are measuring in-app purchases (purchase history) you should respond **Yes** |
| Health and Fitness<ul><li>Health information</li><li>Fitness information</li></ul> | No | Should not be collected |
| Messages<ul><li>Emails</li><li>SMS or MMS messages</li><li>Other in-app messages</li></ul> | No | Should not be collected |
| Photos or Videos<ul><li>Photos</li><li>Videos</li></ul> | No | Should not be collected |
| Audio Files<ul><li>Voice or sound recordings</li><li>Music files</li><li>Other audio files</li></ul> | No | Should not be collected |
| Calendar<ul><li>Calendar events</li></ul> | No | Should not be collected |
| App activity<ul><li>Pageviews and taps in-app</li><li>In-app search history</li><li>Installed apps</li><li>Other user-generated content</li><li>Other actions</li></ul> | See notes -> | AppsFlyer by default measures app launches which may be deemed page views or other actions.<br /><br />Furthermore, if you configure your app to measure specific in-app events you should respond Yes in accordance with your configurations. |
| Web browsing | No | Should not be collected |
| App info and performance<ul><li>Crash logs</li><li>Diagnostics</li><li>Other app performance data</li></ul> | No<br /><br />Yes<br /><br />Yes | Launch time or battery levels may be received for fraud detection purposes |
| Device or other identifiers<ul><li>Device or other identifiers (for example, IMEI, MAC, and Ad ID)</li></ul> | See notes -> | The AppsFlyer Android SDK, by default collect the Google Advertiser Identifier (GAID).   <br />You can disable the collection of the Advertising ID in the SDK by [revoking AD\_ID permission](https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission) and by calling [setDisableAdvertisingIdentifiers](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib). |

“Shared” means the transfer of data to a third party (whether off or on the device).

Exceptions include the following:

* Transfers to service providers that process the data on your behalf and per your instructions
* Transfers required for legal purposes (for example, in response to a government request)
* End-user action or based on a prominent in-app disclosure and consent
* Anonymous data

It is important to note that while AppsFlyer acts solely as a service provider on your behalf and per your instructions if you are sharing data with third-party networks (for example, through postbacks, SRN’s, and audiences ) this would be deemed sharing.  Therefore, each app developer will need to assess his configurations and partner integrations and respond accordingly.

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

> 📄 **See also**
>
> To learn more about preparing for the Google Play safety section and how to complete the required form, read these articles:
>
> * <Anchor target="_blank" href="https://android-developers.googleblog.com/2021/07/new-google-play-safety-section.html">Preparing for Google Play's new safety section</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/10787469">Provide information for Google Play's Data safety section</Anchor>

<div data-zendesk-anchors="h_01HDP3NTTKH3X3585J3DM6MCDC=disclaimer h_01HDP3NTTK1BDTZTHNWRM3411D=introduction h_01HDP3NTTKQE2N0HZDNGK2ZQPC=audience h_01HDP3NTTKK6DJSF49326V3BEG=google-safety-form-questionnaire h_01HDP3NTTK89K8YPT6C7S9QM3W=data-collection-and-security h_01HDP3NTTK9DYZTQ2B64QMKGX8=data-types h_01HDP3NTTKT7C0TGVCZJ4GR9BF=ephemeral-processing h_01HDP3NTTK4CT8MJ1S84MAG8VD=user-choice h_01HDP3NTTKD3MND388MWCC6PAT=purpose h_01HDP3RBENN69F150ESQMSVP3Q=see-also" />

---
title: About device identifiers
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2021-10-12T14:16:09Z'
  edited_at: '2026-04-19T11:43:45Z'
  id: 4408847686161
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4408847686161-About-device-identifiers
---
> **At a glance:** Understand the device identifiers supported in the AppsFlyer SDK.

## Overview

The AppsFlyer SDK provides a framework for customers to configure which device identifiers their app uses for <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#attribution">attribution</Anchor> and analytics.

The customer can configure the SDK to retrieve advertising identifiers such as GAID, IDFA, and IDFV, based on their app's needs, applicable platform policies, and user consent. (for example, third-party Android app stores or apps marketed in China).

## Android device identifiers

The SDK supports the following device identifiers for Android platforms:

#### Apps published on Google Play

| Device identifier | Purpose |
| --- | --- |
| <span id="gaid"></span>GAID | A **user-resettable** identifier for Google Play Android users.<br /><br />Starting with SDK V4.8.0, AppsFlyer automatically collects this device identifier. |

#### Apps published in third-party app stores

| Device identifier | Purpose |
| --- | --- |
| <span id="amazon-advertising-id"></span>Amazon Advertising ID | A **user-resettable**, unique identifier used by Amazon Fire TV. <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts">See CTV overview</Anchor> |
| <span id="oaid"></span>OAID | A **user-resettable** identifier used by some out-of-store Android markets.  For more information, see the <Anchor target="_blank" href="/marketers/docs/android-oaid-implementation-in-the-sdk">Guide to implementing OAID</Anchor>. |
| <span id="android-id"></span>Android ID | A unique, **non-resettable** mobile-device identifier used in third-party app stores. The SDK does not automatically collect the Android ID. However, if there is a need to collect these identifiers, your developer can implement collection.<br /><br />**Note:** Android ID cannot be used in conjunction with GAID. |

## Apple device identifiers

The SDK supports the following device identifiers for iOS platforms:

| Device identifier | Purpose |
| --- | --- |
| <span id="idfa"></span>IDFA | A unique **user-resettable** identifier for Apple iOS or tvOS (Apple TV) users. Since the release of iOS 14.5, IDFA is available only if the user consents via the <Anchor target="_blank" href="/marketers/docs/about-att-and-skan#att-principles">ATT prompt</Anchor>. |
| <span id="idfv"></span>IDFV | A device identifier shared by all the apps from the **same vendor** on the device. Once the first app is installed, the ID is assigned to it, and other apps from the same vendor are assigned the same IDFV. Apps from other vendors are assigned a different IDFV.<br /><br />In addition, when all the apps from a specific vendor are removed, the IDFV for that vendor is deleted, and upon a new installation, a new IDFV will be assigned. |

## CTV , PC, and console app device identifiers

The SDK supports the following device identifiers for CTV, PC, and console platforms:

| Platform | Device ID |
| --- | --- |
| Android TV | advertising\_id |
| tvOS (Apple TV) | idfa |
| Amazon Fire TV | amazon\_fire\_id |
| Chromecast | advertising\_id |
| Roku | rida |
| Vizio | vida |
| Samsung | tifa |
| LG | LG Ads=lg\_adid |
| Xbox | custom |
| Vidaa | vidaaid |
| Steam | steamid |
| Meta Quest (Oculus) | custom |
| Epic Games | epicid |
| PlayStation | psid |
| Native PC | custom |
| Google Play Games on PC | See [Android identifiers](/docs/about-device-identifiers#android-device-identifiers) |

<div data-zendesk-anchors="h_01H9YXEYC3PA271B3G3Y3GM9PS=overview h_01H9YXEYC3D95A6G70EGNR8ENK=android-device-identifiers h_01H9YXEYC3RG2XCVVW8MJ5VZSC=apps-published-on-google-play apps-published-in-thirdparty-app-stores=apps-published-in-third-party-app-stores h_01H9YXEYC3JA3DPN6P43J1ZXR9=apps-published-in-third-party-app-stores h_01H9YXEYC3733B1A85TEF35EAY=apple-device-identifiers ctv-device-identifiers=ctv--pc-and-console-app-device-identifiers h_01H9YXEYC3DFPWVXA5Y3XANQ3P=ctv--pc-and-console-app-device-identifiers" />

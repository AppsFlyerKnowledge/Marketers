---
title: "About device identifiers"
excerpt: "Understand the device identifiers supported in the AppsFlyer SDK for attribution and analytics across Android, Apple, CTV, PC, and console platforms."
---
> 👍 At a glance
>
> Understand the device identifiers supported in the AppsFlyer SDK.

## Overview

The AppsFlyer SDK provides a framework for customers to configure which device identifiers their app uses for [attribution](/docs/basic-sdk-integration-guide#attribution) and analytics.

The customer can configure the SDK to retrieve advertising identifiers such as GAID, IDFA, and IDFV, based on their app's needs, applicable platform policies, and user consent. (for example, third-party Android app stores or apps marketed in China).

## Android device identifiers

The SDK supports the following device identifiers for Android platforms:

#### Apps published on Google Play

| Device identifier | Purpose |
| --- | --- |
| GAID | A **user-resettable** identifier for Google Play Android users.<br />Starting with SDK V4.8.0, AppsFlyer automatically collects this device identifier. |

#### Apps published in third-party app stores

| Device identifier | Purpose |
| --- | --- |
| Amazon Advertising ID | A **user-resettable**, unique identifier used by Amazon Fire TV. [See CTV overview](/docs/ctv-pc-and-console-platform-attribution-concepts) |
| OAID | A **user-resettable** identifier used by some out-of-store Android markets.  For more information, see the [Guide to implementing OAID](/docs/android-oaid-implementation-in-the-sdk). |
| Android ID | A unique, **non-resettable** mobile-device identifier used in third-party app stores. The SDK does not automatically collect the Android ID. However, if there is a need to collect these identifiers, your developer can implement collection.<br />**Note:** Android ID cannot be used in conjunction with GAID. |

## Apple device identifiers

The SDK supports the following device identifiers for iOS platforms:

| Device identifier | Purpose |
| --- | --- |
| IDFA | A unique **user-resettable** identifier for Apple iOS or tvOS (Apple TV) users. Since the release of iOS 14.5, IDFA is available only if the user consents via the [ATT prompt](/docs/about-att-and-skan#att-principles). |
| IDFV | A device identifier shared by all the apps from the **same vendor** on the device. Once the first app is installed, the ID is assigned to it, and other apps from the same vendor are assigned the same IDFV. Apps from other vendors are assigned a different IDFV.<br />In addition, when all the apps from a specific vendor are removed, the IDFV for that vendor is deleted, and upon a new installation, a new IDFV will be assigned. |

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
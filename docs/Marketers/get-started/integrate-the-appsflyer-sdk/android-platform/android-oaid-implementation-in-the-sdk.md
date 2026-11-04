---
title: Android OAID implementation in the SDK
metadata:
  keywords:
    - China
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2020-02-27T20:21:05Z'
  edited_at: '2023-11-27T15:49:37Z'
  id: 360006278797
  locale: en-us
  section: Android platform
  section_id: 6551190827921
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360006278797-Android-OAID-implementation-in-the-SDK
---
> **At a glance:** Collect the Android OAID to attribute installs from third-party Android app stores.

<div id="about-oaid" />

## About OAID

The Open Anonymous Device Identifier (OAID) is a user-resettable unique identifier for Android devices. It was introduced by the Mobile Security Alliance (MSA), China Information and Communication Research Institute, and device manufacturers, as a privacy-preserving alternative to non-resettable device identifiers like IMEI.

The OAID is usually used for ad measurement and install attribution on devices where Google Play Services aren't available (meaning where Google Advertising ID does not exist).

<span id="supported-devices"></span>The OAID is readable on all devices using an SDK provided by the MSA, or on Huawei devices using the Huawei Mobile Service (HMS) Core SDK.

<div id="integration" />

## Integration

The integration of OAID consists of 3 steps:

1. Integrating an SDK to generate and provide the OAID (either the MSA SDK or Huawei HMS SDK).
2. Integrating the AppsFlyer OAID plugin module.
3. Integrating the AppsFlyer SDK.

**Note**:

* For apps that are intended to be used in China, the MSA SDK must be used.
* For apps that are intended to be used globally on Huawei devices, the Huawei HMS library should be used.

<div id="msa-sdk" />

<Accordion title="MSA SDK">

**To integrate and use the MSA SDK**:

1. Follow the instructions on the [MSA website](http://www.msa-alliance.cn/col.jsp?id=120) to register your app.
   * Registering allows you to download the SDK.
   * As part of the registration process, you receive a certificate file that needs to be added into the app.
2. Tell your developers to follow their <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#msa-sdk-integration">integration instructions</Anchor>.

</Accordion>

<div id="huawei-hms-sdk" />

<Accordion title="Huawei HMS SDK">

**To integrate and use the Huawei HMS SDK**:

* Tell your developers to follow their <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#huawei-hms-sdk-integration">integration instructions</Anchor>.

</Accordion>

<div id="additional-information" />

## Additional information

<div id="opting-out-of-oaid-collection" />

<Accordion title="Opting out of OAID collection">

Once the OAID integration is complete, the SDK attempts to collect OAID automatically. If you want to prevent the collection of OAID for certain users, tell the developer to use of the following:

<Tabs>
<Tab title="Android">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid">setCollectOAID(false) API</Anchor> or <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>

<Tab title="Unity">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectoaid">setCollectOAID(false) API</Anchor> or <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>
</Tabs>

<div id="setting-oaid-manually" />

<Accordion title="Setting OAID manually">

If your app already collects OAID, you can skip the AppsFlyer OAID plugin integration and simply set the OAID value into the AppsFlyer SDK manually, using the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#setting-oaid-manually">setOaidData API</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="h_01HG8PXBZS1SN3SY3AAH1EKMNP=about-oaid h_01HG8PXBZS26P9X1TQ7J4WQNF5=integration h_01HG8PXBZSM0QYQE4C9S1FBFB1=msa-sdk h_01HG8PXBZS3HP9X1AZ7HQ8C34Y=huawei-hms-sdk h_01HG8PXBZSW5HNTTDRQ7DFFF4D=additional-information h_01HG8PXBZS8Z3MTQWFN5R6FFA8=opting-out-of-oaid-collection h_01HG8PXBZSYNS8R1PCW4YXHFBA=setting-oaid-manually" />

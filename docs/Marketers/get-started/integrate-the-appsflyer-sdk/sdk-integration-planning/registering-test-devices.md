---
title: Registering test devices
metadata:
  keywords:
    - whitelisting
    - Testing
    - device
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-03-10T08:19:35Z'
  edited_at: '2026-08-28T10:04:49Z'
  id: 207031996
  locale: en-us
  section: SDK integration planning
  section_id: 6551182964369
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207031996-Registering-test-devices
---
> **At a glance:** When performing attribution tests, register your test device to make sure each install is recorded as a new install. A registered test device prevents installs from being recorded as reinstalls.

<div id="why-register-a-test-device" />

## Why register a test device

When performing attribution tests, the re-attribution window limits install attributions to one per 90-day window. Therefore, if you repeatedly use the same device to test install attributions, nothing is recorded. Registering a device as a test device prevents repeated installs on the registered device from being recorded as reinstalls.

<div id="methods-for-registering-a-test-device" />

## Methods for registering a test device

Registering a test device includes selecting the device's operating system (Android, iOS, or Windows), and adding the device identifier.

You can use one of the following methods to register:

* [Download and install the My Device ID by AppsFlyer app:](#register-a-device-using-the-appsflyer-device-id-app-admin-only) Once you install the app on the test device, you can automatically register the device and share device ID details to your AppsFlyer account. The device will be automatically listed on the **Test devices** page.

<div id="note" />

> 📘 **Note**
>
> * In iOS 14+ test devices you can use this registration method only when AppTransparency Tracking (ATT) was implemented on your app and you want to run tests as a consenting user. When this is not the case use the manual method.
> * If your AppsFlyer account has two-factor authentication (2FA) enabled, you cannot register test devices using the app, because the app does not support 2FA authentication. In this case, use the manual method to register test devices.

* [Manually add the test device:](#register-a-device-manually) Any account user can directly register a test device by adding the device identifier to the **Test devices** page.

Keep in mind the following:

* Registered test devices are available to all apps that belong to the account.
* Ad networks need to ask an advertiser to add devices; agencies can add their own devices.

<Accordion title="Supported device identifiers">

Device identifiers include the following:

* **Android:** AID (GAID or OAID), IMEI, Android ID

<div id="note-1" />

> 📘 **Note**
>
> When registering a test device, you should add IMEI or Android ID device identifiers only if your app collects and uses these identifiers.

* **iOS:** IDFA, IDFV
* **Windows Phone:** Windows advertising ID

</Accordion>

<div id="managing-test-device-registration" />

## Managing test device registration

<Accordion title="Register a device using the AppsFlyer device ID app">

**To download the AppsFlyer device ID app:**

1. Download and install the app using the QR code (Google Play store) or one of the provided links:

   <div id="android" />

   <Accordion title="Android">

   [<Image alt="kb_qr_code.png" src="https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png" width="50%" />](https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png)

   **Links:** [Google Play](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid&hl=en) and [Out-of-market store](https://apkpure.com/my-device-id-by-appsflyer/com.appsflyer.android.deviceid)

   </Accordion>

   <div id="ios" />

   <Accordion title="iOS">

   [<Image alt="kb_qr_code.png" src="https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png" width="50%" />](https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png)

   </Accordion>

   <div id="windows" />

   <Accordion title="Windows">

   [<Image alt="" src="https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png" width="50.91%" />](https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png)

   </Accordion>

2. On an iOS 14.5+ device, if you want to allow IDFA collection, tap **Allow** when the ATT prompt displays. [<Image alt="" src="https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png" width="50%" />](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)
3. On the Android/iOS/Windows screen, tap **Register** to register the device:

   <div id="android::db8cc168" />

   <Accordion title="Android">

   [<Image alt="" src="https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png" width="50%" />](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)

   </Accordion>

   <div id="ios::80f176b3" />

   <Accordion title="iOS">

   [<Image alt="" src="https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png" width="50%" />](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)

   </Accordion>

   <div id="windows::6c6af14b" />

   <Accordion title="Windows">

   [<Image alt="" src="https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg" width="50%" />](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)

   </Accordion>

4. Enter your AppsFlyer login credentials. The device is now registered.
5. Tap **Share** details to share Device ID information.

</Accordion>

<Accordion title="Register a device manually">

Account users can manually register a device:

1. In AppsFlyer, from the side menu, select **Settings** -> **Test Devices**.
2. Select **Test devices**.
3. Click **+ Add device**.

   [<Image alt="" src="https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png" width="50%" />](https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png)
4. Complete the following:
   * **Name (only use English letters):** Enter a unique identifying name for the device.
   * **OS:** Select an operating system.
   * **Device ID type:** Select a device identifier.
   * **Device ID:** Provide the device ID according to the operating system:

     <div id="ios::41efa11e" />

     <Accordion title="iOS">

     How to obtain the IDFA or IDFV identifiers:

     * **IDFA:** To obtain the IDFA install the AppsFlyer device ID app on your test device. To learn how see: [Add a device](#register-a-device-manually) using the AppsFlyer device ID app (admin only) above.
     * **IDFV:** To obtain the IDFV get your developer to install the IDFV test tool app on your test device. Once installed and launched the tool app will display the IDFV. **Note:** The test tool can be installed only after the developer performed preliminary steps in X-Code.

     To learn when to use IDFA or IDFV see [Registering an iOS test device](#registering-an-ios-test-device).

     </Accordion>

     <div id="android::7db075c7" />

     <Accordion title="Android">

     Obtain the identifiers by using the AppsFlyer Device ID app or by dialing the codes into the device:

     | Identifier | Retrieval method | Google Play | Other |
     | --- | --- | --- | --- |
     | AID (GAID or OAID) | Use the [AppsFlyer Device ID app](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid) | Mandatory |  |
     | IMEI | *#06#* | Not applicable | Make sure that the developer used <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">setCollectImei</Anchor> to collect the ID. |
     | Android ID | *#*#8255#*#* (may not work on newer devices) | Not applicable | Make sure that the developer used <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">setCollectAndroidID</Anchor> to collect the ID. |

     </Accordion>

5. Click **Save**. The device displays in the list of registered devices. **Note**: Although the device displays in the list of registered devices immediately, it may take a few minutes to register in the system and function as intended.

<div id="note-2" />

> 📘 **Note**
>
> **Adding more than one identifier**
>
> There can be cases in which you want to add more than one identifier to your test device, for example, you want both IDFA and IDFV on the same device.
>
> **To add an additional identifier:**
>
> 1. Click **Add device**.
> 2. Use the same name for the test device, and add the 2nd identifier.
> 3. Click **Save**.

</Accordion>

<Accordion title="Unregister a device">

A maximum of 200 devices can be registered per account.

**To delete a device from the list:**

1. In AppsFlyer, in the upper-right click on your email address.
2. Select **Test devices**.
3. Click the delete icon to remove devices.

</Accordion>

<div id="registering-an-ios-test-device" />

## Registering an iOS test device

The flow chart below illustrates the potential courses of action when registering your iOS test devices.

[![](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)

Select among the following options when registering your iOS test device:

<Accordion title="Register your test device with IDFA">

<div id="when-to-use-idfa-for-test-device-registration" />

#### **When to use IDFA for test device registration?**

You can register with IDFA if AppTransparency Tracking (ATT) was implemented on your app and you want to run tests as a consenting user. When launching the tested app for the first time, make sure to click **Allow** in the ATT prompt.

<div id="how-to-register-your-test-device-with-an-idfa" />

#### **How to register your test device with an IDFA?**

To register with IDFA, register a device using the AppsFlyer device ID app.

</Accordion>

<Accordion title="Register your test device with IDFV">

<div id="when-to-use-idfv-for-test-device-registration" />

#### **When to use IDFV for test device registration?**

When IDFA is not accessible, IDFV is your only option. In the following scenarios you **must use IDFV**:

* **ATT was implemented** but you want to run tests as a non-consenting user. When launching the app for the first time, make sure to click **Don't Allow** in the ATT prompt.
* **ATT was not implemented** at all.

<div id="how-to-register-your-device-with-idfv" />

#### **How to register your device with IDFV**

1. Before you can register the test device with an IDFV, your developer has to install the IDFV test tool app on your test device. For developer instructions you can refer your developer to <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-the-idfv-test-tool-app">this article</Anchor>.
2. After your developer installed the IDFV test tool app, launch it and copy the IDFV displayed.
3. [Register the test device manually](#register-a-device-manually) using the IDFV.

<div id="note-3" />

> 📘 **Note**
>
> **What are the reasons for installing the IDFV test tool app?**
>
> * The IDFV test tool is used to extract the IDFV you need to register the test device.
> * When you don’t have another app owned by your developer account installed on your test device. In this case iOS assigns a new vendor ID every time you reinstall the app. Since test involves in many cases reinstalling the app, each reinstall triggers iOS to reset the IDFV. **The utility app by pretending to belong to the vendor, prevents iOS from creating a new IDFV every time the app is reinstalled on the test device.**

</Accordion>

<Accordion title="Testing with a non-registered device">

Use this option only if you cannot register a test device with either IDFA or IDFV. In this instance, probabilistic modeling is used for attribution. Each install is recorded as a new install on the test device. This method can help with registering repeated test installs for the same device if at least one of the following happens:

* The AppsFlyer iOS SDK is v6.8.0 or below.
* Reinstall detection is disabled for the app (not recommended for live apps).
* The test attribution link contains `is_retargeting="true"`. In this case, installs are recorded as re-attributions and are available in the retargeting dashboard and retargeting raw data reports.
* For iOS only: To prevent Protect360 from flagging clicks as fraudulent, add the query parameter `pid="ios_testing"` to your test attribution link.

</Accordion>

<div data-zendesk-anchors="why-register-a-testing-device=why-register-a-test-device 01H7W9EA7RQDB69QS339XFHAFZ=why-register-a-test-device methods-for-registering-a-testing-device=methods-for-registering-a-test-device 01H7W9EA7RRRJBFSXW3KY53R9K=methods-for-registering-a-test-device managing-testingdevice-registration=managing-test-device-registration 01H7W9EA7R7SJVVQCST3WA6YBM=managing-test-device-registration 01JHJKN5Z3562N4W2H543XPC7E=android 01JHJKN5Z54T180C7G462C26Z4=ios 01JHJKN5Z51FABEGCFVTK0MPYR=windows 01JHJKTNRHHSZSC44WDWA9J2PD=android::db8cc168 01JHJKTNRJJBBA6WAC44PD33V7=ios::80f176b3 01JHJKTNRK9DY99SZ759ZGRP23=windows::6c6af14b 01JHJKDZK8084GMZ9QAZPHVBHQ=ios::41efa11e 01JHJKDZK9MTNXANVEHCM18EBM=android::7db075c7 registering-an-ios-testing-device=registering-an-ios-test-device h_01H6S2AKDH181MBDFGPBP1BQPV=registering-an-ios-test-device when-to-use-idfa-for-testing-device-registration=when-to-use-idfa-for-test-device-registration 01H7W9EA7SRD5V5134H2BRZ2AF=when-to-use-idfa-for-test-device-registration how-to-register-your-testing-device-with-an-idfa=how-to-register-your-test-device-with-an-idfa 01H7W9EA7SBBCAP3Y24FFCCGJW=how-to-register-your-test-device-with-an-idfa when-to-use-idfv-for-testing-device-registration=when-to-use-idfv-for-test-device-registration 01H7W9EA7S3103TSHSH4XHTP1R=when-to-use-idfv-for-test-device-registration 01H7W9EA7SGTDQCRVJKKRH0EVT=how-to-register-your-device-with-idfv" />

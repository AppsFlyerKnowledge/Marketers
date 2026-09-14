---
title: "Registering test devices"
excerpt: "Register your test device to ensure each install is recorded as a new install during attribution testing, preventing repeated installs from being flagged as reinstalls."
---
When performing attribution tests, register your test device to make sure each install is recorded as a new install. A registered test device prevents installs from being recorded as reinstalls.

## Why register a test device

When performing attribution tests, the re-attribution window limits install attributions to one per 90-day window. Therefore, if you repeatedly use the same device to test install attributions, nothing is recorded. Registering a device as a test device prevents repeated installs on the registered device from being recorded as reinstalls.

## Methods for registering a test device

Registering a test device includes selecting the device's operating system (Android, iOS, or Windows), and adding the device identifier.

You can use one of the following methods to register:

- [Download and install the My Device ID by AppsFlyer app:](/docs/registering-test-devices#register-a-device-using-the-appsflyer-device-id-app-admin-only) Once you install the app on the test device, you can automatically register the device and share device ID details to your AppsFlyer account. The device will be automatically listed on the **Test devices** page.

- In iOS 14+ test devices you can use this registration method only when AppTransparency Tracking (ATT) was implemented on your app and you want to run tests as a consenting user. When this is not the case use the manual method.
- If your AppsFlyer account has two-factor authentication (2FA) enabled, you cannot register test devices using the app, because the app does not support 2FA authentication. In this case, use the manual method to register test devices.

- [Manually add the test device:](/docs/registering-test-devices#register-a-device-manually) Any account user can directly register a test device by adding the device identifier to the **Test devices** page.

Keep in mind the following:

- Registered test devices are available to all apps that belong to the account.
- Ad networks need to ask an advertiser to add devices; agencies can add their own devices.

### Supported device identifiers

Device identifiers include the following:

- **Android:** AID (GAID or OAID), IMEI, Android ID

When registering a test device, you should add IMEI or Android ID device identifiers only if your app collects and uses these identifiers.

- **iOS:** IDFA, IDFV
- **Windows Phone:** Windows advertising ID

## Managing test device registration

### Register a device using the AppsFlyer device ID app

**To download the AppsFlyer device ID app:**

1. Download and install the app using the QR code (Google Play store) or one of the provided links:

<Tabs>
<Tab title="Android">

![Android QR Code](https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png)

**Links:** [Google Play](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid&hl=en) and [Out-of-market store](https://apkpure.com/my-device-id-by-appsflyer/com.appsflyer.android.deviceid)

</Tab>
<Tab title="iOS">

![iOS QR Code](https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png)

</Tab>
<Tab title="Windows">

</Tab>
</Tabs>

2. On an iOS 14.5+ device, if you want to allow IDFA collection, tap **Allow** when the ATT prompt displays.
3. On the Android/iOS/Windows screen, tap **Register** to register the device:

<Tabs>
<Tab title="Android">

</Tab>
<Tab title="iOS">

</Tab>
<Tab title="Windows">

</Tab>
</Tabs>

4. Enter your AppsFlyer login credentials. The device is now registered.
5. Tap **Share** details to share Device ID information.

### Register a device manually

Account users can manually register a device:

1. In AppsFlyer, from the side menu, select **Settings** -> **Test Devices**.
2. Select **Test devices**.
3. Click **+ Add device**.
4. Complete the following:
   - **Name (only use English letters):** Enter a unique identifying name for the device.
   - **OS:** Select an operating system.
   - **Device ID type:** Select a device identifier.
   - **Device ID:** Provide the device ID according to the operating system:

     <Tabs>
     <Tab title="iOS">

     How to obtain the IDFA or IDFV identifiers:

     - **IDFA:** To obtain the IDFA install the AppsFlyer device ID app on your test device. To learn how see: [Add a device](/docs/registering-test-devices#register-a-device-manually) using the AppsFlyer device ID app (admin only) above.
     - **IDFV:** To obtain the IDFV get your developer to install the IDFV test tool app on your test device. Once installed and launched the tool app will display the IDFV. 
     
     > 📘 Note
     >
     > The test tool can be installed only after the developer performed preliminary steps in X-Code.

     To learn when to use IDFA or IDFV see [Registering an iOS test device](/docs/registering-test-devices#registering-an-ios-testing-device).

     </Tab>
     <Tab title="Android">

     Obtain the identifiers by using the AppsFlyer Device ID app or by dialing the codes into the device:

     | Identifier | Retrieval method | Google Play | Other |
     | --- | --- | --- | --- |
     | AID (GAID or OAID) | Use the [AppsFlyer Device ID app](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid) | Mandatory |  |
     | IMEI | \*#06#\* | Not applicable | Make sure that the developer used [setCollectImei](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei) to collect the ID. |
     | Android ID | \*#\*#8255#\*#\* (may not work on newer devices) | Not applicable | Make sure that the developer used [setCollectAndroidID](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid) to collect the ID. |

     </Tab>
     </Tabs>

5. Click **Save**. The device displays in the list of registered devices. 

> 📘 Note
>
     > Although the device displays in the list of registered devices immediately, it may take a few minutes to register in the system and function as intended.

**Adding more than one identifier**

There can be cases in which you want to add more than one identifier to your test device, for example, you want both IDFA and IDFV on the same device.

**To add an additional identifier:**

1. Click **Add device**.
2. Use the same name for the test device, and add the 2nd identifier.
3. Click **Save**.

### Unregister a device

A maximum of 200 devices can be registered per account.

**To delete a device from the list:**

1. In AppsFlyer, in the upper-right click on your email address.
2. Select **Test devices**.
3. Click the delete icon to remove devices.

## Registering an iOS test device

The flow chart below illustrates the potential courses of action when registering your iOS test devices.

Select among the following options when registering your iOS test device:

<Tabs>
<Tab title="Register with IDFA">

#### **When to use IDFA for test device registration?**

You can register with IDFA if AppTransparency Tracking (ATT) was implemented on your app and you want to run tests as a consenting user. When launching the tested app for the first time, make sure to click **Allow** in the ATT prompt.

#### **How to register your test device with an IDFA?**

To register with IDFA, register a device using the AppsFlyer device ID app.

</Tab>
<Tab title="Register with IDFV">

#### **When to use IDFV for test device registration?**

When IDFA is not accessible, IDFV is your only option. In the following scenarios you **must use IDFV**:

- **ATT was implemented** but you want to run tests as a non-consenting user. When launching the app for the first time, make sure to click **Don't Allow** in the ATT prompt.
- **ATT was not implemented** at all.

#### **How to register your device with IDFV**

1. Before you can register the test device with an IDFV, your developer has to install the IDFV test tool app on your test device. For developer instructions you can refer your developer to [this article](https://dev.appsflyer.com/hc/docs/install-the-idfv-test-tool-app).
2. After your developer installed the IDFV test tool app, launch it and copy the IDFV displayed.
3. [Register the test device manually](/docs/registering-test-devices#register-a-device-manually) using the IDFV.

**What are the reasons for installing the IDFV test tool app?**

- The IDFV test tool is used to extract the IDFV you need to register the test device.
- When you don’t have another app owned by your developer account installed on your test device. In this case iOS assigns a new vendor ID every time you reinstall the app. Since test involves in many cases reinstalling the app, each reinstall triggers iOS to reset the IDFV. **The utility app by pretending to belong to the vendor, prevents iOS from creating a new IDFV every time the app is reinstalled on the test device.**

</Tab>
<Tab title="Testing with a non-registered device">

Use this option only if you cannot register a test device with either IDFA or IDFV. In this instance, probabilistic modeling is used for attribution. Each install is recorded as a new install on the test device. This method can help with registering repeated test installs for the same device if at least one of the following happens:

- The AppsFlyer iOS SDK is v6.8.0 or below.
- Reinstall detection is disabled for the app (not recommended for live apps).
- The test attribution link contains `is_retargeting="true"`. In this case, installs are recorded as re-attributions and are available in the retargeting dashboard and retargeting raw data reports.
- For iOS only: To prevent Protect360 from flagging clicks as fraudulent, add the query parameter `pid="ios_testing"` to your test attribution link.

</Tab>
</Tabs>
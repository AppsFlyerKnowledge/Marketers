---
title: "Testing Windows SDK integration"
excerpt: "Learn how to test your Windows app integration with AppsFlyer, including non-organic installs, in-app events, and deep linking."
---
**At a glance:** Test your Windows app integration with AppsFlyer.

* Currently, there is no way of testing with Windows Referrer other than to upload the app to the Windows App Store.
* When testing with Windows Referrer, you must be familiar with the following restrictions:
  * You must be logged in to the store.
  * You must not have the Windows 10 Anniversary Update on your device.
  * Your device must never have had the app (Windows' referrer is lifetime - even if you are allowlisted or have waited over 90 days, you will not receive referrer attribution).

## Test SDK integration

1. It is required to test the SDK Integration on a registered test device. To register your test device, follow the steps [here](/docs/registering-test-devices).
2. Open the AppsFlyer dashboard and chose the app you are testing.
3. Select SDK Integration Tests from the Navigation Menu.
4. You are presented with three options to test:

* Non-organic Install
* In-app events
* Deep linking

[![](https://files.readme.io/7b2af46dc66530db91c31466b08121673f067ea9188d5bbf7e5f4a4137cbc6e4-115011326025.png)](https://files.readme.io/7b2af46dc66530db91c31466b08121673f067ea9188d5bbf7e5f4a4137cbc6e4-115011326025.png)

## Testing non-organic install

1. Select one of your registered devices from the dropdown list
2. Select where you are installing the app from (Windows Store or Other)
3. Scan the generated QR code with your registered test device and follow the instructions on your device.
4. Wait until the non-organic install is registered on the Integration Test page, indicating the test was successful. This can take up to two minutes. If the app did not register a non-organic install by this time, see the troubleshooting guide displayed on the Integration Test page.

## Testing in-app events

1. Select one of your registered test devices from the dropdown menu and click Next.
2. Open your app and start generating in-app events.
3. You will see a log of these events as they are registered in real-time.

## Testing deep linking

1. OneLink must be defined for your app to test Deep Linking. See [OneLink guide](/docs/create-a-onelink-template)
2. Select one of your registered test devices from the drop-down menu and click Next.
3. Scan the QR code with your registered test device and follow the instructions on your device.
4. Wait until the Deep Link is registered successfully on the Integration Test page.
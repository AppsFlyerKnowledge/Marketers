---
title: "Testing tvOS integration before publishing"
excerpt: "Learn how to simulate non-organic installs on your AppleTV device using the tvOS Test App to verify attribution before publishing your app."
---
**At a glance:** Simulate a non-organic install from your AppleTV device using the tvOS Test App.

## Overview

AppleTV does not contain a browser. Therefore, you cannot test clicks or installs on the device for an **unpublished** app. (For **published** apps, you can [test using attribution links](/docs/testing-the-sdk-integration-for-marketers#testing-using-attribution-links)).

To test attribution on unpublished apps, you can use the **tvOS Test App.**

### How does the tvOS Test App work?

The tvOS Test App allows you to simulate an attribution link click from within your AppleTV device, so you can then install it and receive a non-organic attribution.

**To test attribution using the tvOS Test App:**

1. Download the project from [here](https://github.com/AppsFlyerSDK/AppsFlyerFramework).
2. From XCode, build the project to your AppleTV testing device.

   The following window displays:

   ![](https://support.appsflyer.com/hc/en-us/article_attachments/205289963/tvos_test_1.png)
3. [Register](/docs/registering-test-devices) your AppleTV device as a test device using the **IDFA** displayed at the bottom of the app screen.
4. In the Test App, enter your AppID as it appears on your app’s dashboard.

   Make sure that the app you are testing is **not installed** on the device. To get a non-organic attribution, you must simulate a real scenario where the attribution link is clicked before the app is opened on **first** **launch**.
5. Click the **Click Simulation** button and wait for a response.

   If everything is valid, the following message is displayed:

   ![](https://support.appsflyer.com/hc/en-us/article_attachments/205275743/tvos_test_2.png)
6. **Install** your integrated app on your device.

   A non-organic attribution is shown on your dashboard under the **AppsFlyer\_Test** media source if your integration is correct.

   ![](https://support.appsflyer.com/hc/en-us/article_attachments/205275823/tvos_test_3.png)
---
title: Testing tvOS integration before publishing
metadata:
  keywords:
    - Testing
    - tvos
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2016-07-12T09:49:14Z'
  edited_at: '2026-10-01T00:15:03Z'
  id: 211758923
  locale: ja
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ja/articles/211758923
---
> **At a glance:** Simulate a non-organic install from your AppleTV device using the tvOS Test App.

## Overview

AppleTV does not contain a browser. Therefore, you cannot test clicks or installs on the device for an **unpublished** app. (For **published** apps, you can <Anchor target="_blank" href="/marketers/ja/docs/testing-the-sdk-integration-for-marketers#アトリビューションリンクを使ったテスト">test using attribution links</Anchor>).

To test attribution on unpublished apps, you can use the **tvOS Test App.**

### How does the tvOS Test App work?

The tvOS Test App allows you to simulate an attribution link click from within your AppleTV device, so you can then install it and receive a non-organic attribution.

**To test attribution using the tvOS Test App:**

1. Download the project from <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyerFramework">here</Anchor>.
2. From XCode, build the project to your AppleTV testing device.

   The following window displays:

   <Image align="center" alt="" src="https://files.readme.io/7ed3c5e8165e6d27c9d87db8b026c0898536b145def6bfedd0dc5f78c7804669-205289963.png" />
3. <Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">Register</Anchor> your AppleTV device as a test device using the **IDFA** displayed at the bottom of the app screen.
4. In the Test App, enter your AppID as it appears on your app’s dashboard.

   Make sure that the app you are testing is **not installed** on the device. To get a non-organic attribution, you must simulate a real scenario where the attribution link is clicked before the app is opened on **first** **launch**.
5. Click the **Click Simulation** button and wait for a response.

   If everything is valid, the following message is displayed:

   <Image align="center" alt="" src="https://files.readme.io/27b8b5acfe9691d3704ae36b04e28ecaa643e1b68eb5e0a6f8be70f657b2c0d3-205275743.png" />
6. **Install** your integrated app on your device.

   A non-organic attribution is shown on your dashboard under the **AppsFlyer\_Test** media source if your integration is correct.

   <Image align="center" alt="" src="https://files.readme.io/4c6ab66ebd13556bd764d4e93adbb639be208b8955dd1fe1d3dd60ecd5c01a3b-205275823.png" />
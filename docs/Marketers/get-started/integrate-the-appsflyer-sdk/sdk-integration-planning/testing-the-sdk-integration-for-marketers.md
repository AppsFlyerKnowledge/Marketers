---
title: "Testing the SDK integration for marketers"
excerpt: "Test your Android or iOS app integration with AppsFlyer."
x-zendesk:
  id: 360001559405
  url: https://support.appsflyer.com/hc/en-us/articles/360001559405-Testing-the-SDK-integration-for-marketers
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SDK integration planning
  section_id: 6551182964369
  position: 4
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Testing, SDK, Advertisers, Debug, Debugging, redirects test, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2018-11-12T14:15:08Z'
  edited_at: '2026-08-13T12:49:29Z'
---
## Overview

After the SDK integration is complete you can verify that the SDK is communicating successfully with AppsFlyer servers. Marketers can choose between two testing methods:

* Testing using the **SDK Integration Test** page that enables you to:
  * ![](https://files.readme.io/16b90e430d7beea0eaa1530130d094d590c0a202f6c6ad298a88aac9508fee7a-31828933593745.png) [View events in real-time](#view-live-events) as they occur in your tested app.
  * [Test non-organic install](#h_01HYX9R15931HJEA06SY3K47W5)
  * [Test deep links (retargeting)](#h_01HYX9R159DDNJW53AWTWT4C2Z)
* [Test using attribution links.](#testing-using-attribution-links)

Developers can perform integration testing in their development environment. See the [Dev Hub's Integration testing articles](https://dev.appsflyer.com/hc/docs/integration-testing).

CTV apps can also be tested, see [Testing CTV](#testing-ctv).

## Testing using the SDK Integration Tests page

Use the **SDK Integration Tests** page to view real-time live events, such as installs, ad revenue, and in-app events, as they occur in your app. You can also test non-organic installs, in-app events, and deep linking (retargeting), and locate any integration issues in your project. The live event viewer replaces the legacy in-app event testing tool.

The SDK integration test page works only in apps where the SDK collects a device ID.

* **iOS:** Make sure the user has granted App Tracking Transparency (ATT) permissions so that the IDFA can be collected. You can test non-ATT apps using the procedure specified here.
* **Android:** Although the device ID (GAID) is typically collected automatically, we recommend verifying that the SDK collects it.

### **Prepare a test device**

1. Prepare a device (Android or iOS) that does not have the app installed. If needed, uninstall the app from the device.
2. [Register the device as a test device.](/docs/registering-test-devices)

### Perform the integration tests

The **SDK Integration Tests** page provides the following three tests:

<Accordion title="View live events">

The Live Event Viewer is a testing tool that displays real-time data sent from the SDK to AppsFlyer, including install, ad revenue, and store revenue events, and other in-app events. For each event captured, you can see the event log and details.

The Live Events Viewer also supports in-app events and sessions created from a test device, sent to your server, and ingested into AppsFlyer through the S2S API. Make sure the S2S events include the device identifier (IDFA for iOS, GAID for Android) of the registered test device.

**To view events in the Live Event Viewer:**

1. In AppsFlyer, from the side menu, select **Settings** > **SDK Integration Tests**.

   [![](https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png)](https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png)
2. Click **Live Events.**

   [![](https://files.readme.io/6ec1edba14e51bb27babf80d2d6f4873dbaa5113752217b4fb13399f7a1c61f1-31828925849489.png)](https://files.readme.io/6ec1edba14e51bb27babf80d2d6f4873dbaa5113752217b4fb13399f7a1c61f1-31828925849489.png)
3. In the **App** list, select the app that you want to test.
4. In the **Test device** list, select the device you want to use for testing your app. If you don’t have a test device, you can register one by clicking on the **Add a test device** link.
5. Click **Continue** to begin recording your app events.
6. Launch the app and interact with it to generate sessions and in-app events.

   [![](https://files.readme.io/72b8822197dc626c1b28a9f8d43bb3c1a91f99e600ae0d8d1f74829bc62dcce6-31828933607313.png)](https://files.readme.io/72b8822197dc626c1b28a9f8d43bb3c1a91f99e600ae0d8d1f74829bc62dcce6-31828933607313.png)
7. Click an event item to view the event details on the right panel.
8. If you want to stop recording the events click **Stop**. Click **Start** again when you want to continue.

</Accordion>

<Accordion title="Test non-organic installs">

**To test non-organic installs:**

1. In AppsFlyer, from the side menu, select **Settings** > **SDK Integration Tests**.

   [![](https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png)](https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png)
2. Click **Non-Organic Installs** test.

   [![](https://files.readme.io/34440ab6d328e2d519f759f3c2a1b17dbcbee55af32b47bdbd52bb9f537c6735-31828933612177.png)](https://files.readme.io/34440ab6d328e2d519f759f3c2a1b17dbcbee55af32b47bdbd52bb9f537c6735-31828933612177.png)
3. In the **App** list, select the app that you want to test.
4. In the **Test device** list, select the device you want to use for testing your app. If you don’t have a test device, you can register one by clicking on the **Add a test device** link.
5. If the tested app is installed on your test device remove it.
6. Select the **I removed the app from the tested device** checkbox.
7. Click **Continue** and follow the wizard steps.

**If the app does not record a non-organic install, possible reasons might be:**

* IDFA is available but the test device was not [registered with this identifier on the Test devices page](/docs/registering-test-devices#registering-an-ios-test-device).
* You have more than 1 of your apps, besides the test app, installed on the test device but the test device was not [registered with IDFV on the Test devices page](/docs/registering-test-devices#registering-an-ios-test-device).
* An organic install was recorded.
* The test was performed on a version of the app that does not include the SDK.

For integration errors, contact your developer.

</Accordion>

<Accordion title="Test deep links (retargeting)">

**Before you begin:**

* Launch the test app at least 3 times.
* To test deep linking (retargeting), OneLink must be defined for your app. For more information, see the [OneLink Setup guide](/docs/create-a-onelink-template).
* Verify that [retargeting](/docs/app-settings#reengagement-attribution) is turned on.

**To test deep links:**

1. In AppsFlyer, from the side menu, select **Settings** > **SDK Integration Tests**.

   [![Keyboard Maestro Engine 2024-10-06 10.00.47.png](https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png)](https://files.readme.io/4a4941c82e49eb4f71f7f391e88d9e771432aee95232d54b0fa77d25eb91f944-31828925857169.png)
2. Click **Retargeting**.

   [![](https://files.readme.io/7c5eb6870e8d4c25a817f6c2895163b699e0a4972a6cc675b94396c386288d72-31828925858961.png)](https://files.readme.io/7c5eb6870e8d4c25a817f6c2895163b699e0a4972a6cc675b94396c386288d72-31828925858961.png)
3. In the **App** list, select the app that you want to test.
4. In the **Test device** list, select the device you want to use for testing your app. If you don’t have a test device, you can register one by clicking on the **Add a test device** link.
5. Click **Continue** and follow the wizard steps.

</Accordion>

## Testing using attribution links

The following section describes the procedures you should follow to test installs with attribution links. You can perform these tests even if the app is still pending (meaning, not listed in the Google Play Store or Apple App Store).

<Accordion title="Test install attribution">

Testing installs allows you to verify that the AppsFlyer SDK is attributing installs correctly to various media sources.

**To test install attribution:**

1. Copy the following link (Android or iOS), and make these changes:

   1. **app\_id** value: Add your app ID in AppsFlyer.
   2. **pid** parameter: Specify the name of the media source to which the install is attributed.
   3. **c** parameter: Specify the name of the campaign.
   4. If you are testing an app available via a third-party Android store, add the [af\_r parameter](/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links) to the attribution link.
   5. Replace the GAID, IDFA, or IDFV with your specific device identifier.

   <Accordion title="Android">

   ```
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&advertising_id=<GAID>
   ```

   </Accordion>

   <Accordion title="iOS">

   IDFA

   ```
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfa=<IDFA>
   ```

   IDFV

   ```
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfv=<IDFV>
   ```

   </Accordion>

   The following are examples of attribution links with specific values:

   <Accordion title="Android">

   ```

   ```

   ```
   https://app.appsflyer.com/com.my.app?pid=Test&c=Test&advertising_id=12345f9*-eba*-421*-876*-7654ac67876*
   ```

   </Accordion>

   <Accordion title="iOS">

   ```

   ```

   ```
   https://app.appsflyer.com/id123456789?pid=Test&c=Test&idfa=1A2B****-9128-4***-123*-04E***654321
   ```

   </Accordion>

If you're testing an iOS app without registering a test device your test click can be flagged as fraudulent by Protect 360.

To prevent this event from being detected as fraud, add the following query parameter to your link: pid=ios\_testing

1. Copy your updated link, send it to the test device, and then click the link.

In iOS, use iMessage or email to send the link to the device. Don't paste the link in the iOS Notes app and click the link. This action can cause the link to break.

1. Do one of the following:

   * If the app is live, proceed to install it.
   * If the app is pending, the following message displays: "*The app you are looking for is not available in the market yet.*" This is the expected result. Since the app is not live, the attribution link doesn't lead to any app store. However, the attribution link is still valid for attribution purposes and you should install the app as follows:
     * **For Android:** From an APK file (or Android Studio for developers)
     * **For iOS:** From TestFlight (or Xcode for developers)

   You should see an install that is attributed to the test campaign under the media source called **Test**. Allow up to 30 minutes for the install to appear in the app's dashboard.

   [![Test_Install_Attribution_Link](https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png)](https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png)

The following describes alternative ways to verify your test results:

* If you have access to raw-data reports, download the Installs raw data report. This report takes several minutes to download. **To download the report:**
  1. In AppsFlyer, from the side menu,select **Report** > **Raw Data Export.**
  2. From the **User acquisition (non-organic)** list, click **Installs**, and then download the report.
* If you have access to the debug logs, you can use the Get the conversion data API to retrieve the attribution results for a specific install.

</Accordion>

<Accordion title="Test in-app events attribution">

Testing in-app events allows you to verify that revenue associated with an event is displayed and that in-app events are attributed to the media source that generates the install.

**To test attribution of in-app events:**

1. Launch the app, and then generate a few in-app events.
2. Open the app's Activity dashboard, and check that the events are there.  
   You should see the events, their revenue (if revenue is associated with them), and the media source to which they are associated. Allow up to 60-70 minutes for the events to appear in the dashboard.

**Tip!** Consider downloading the [in-app events raw data report](/docs/raw-data-reporting-overview) to verify that events are attributed correctly. This report takes several minutes to download.

**To download the report:**

1. In AppsFlyer, from the side menu, select **Report** > **Raw Data Export.**
2. In the **Raw Data Reports** section, download the in-app events raw data report.

</Accordion>

<Accordion title="Test OneLink">

OneLink allows you to set a single attribution link for both Android and iOS. OneLink recognizes the user's device and redirects them to the relevant app store.

In addition, OneLink enables deep linking. Deep linking allows you to open the app in a specific app activity while serving customized content.

For more information, see our guide on [testing OneLink URLs](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing).

</Accordion>

## Testing retargeting using attribution links

The following sections describe the procedures you should follow to test retargeting attribution.

<Accordion title="About retargeting tests">

Retargeting attribution occurs when a user engages with a retargeting campaign by clicking on a retargeting attribution link. This results in a re-attribution or a re-engagement event. For more information, see the [Retargeting attribution guide](/docs/retargeting-attribution-guide).

Retargeting tests include the following :

* [**For re-attribution:**](/docs/testing-the-sdk-integration-for-marketers#test-reattribution) Uninstalling and reinstalling the app. Then, verifying in the dashboard that an install was recorded.
* [**For re-engagement:**](/docs/testing-the-sdk-integration-for-marketers#test-reengagement) Clicking a retargeting attribution link or a deep link, and then verifying that a re-engagement is attributed to the correct media source.

</Accordion>

<Accordion title="Prerequisites to run retargeting tests">

Before running retargeting tests, the following setup is required:

* Retargeting must be activated for the app you are testing.
* Create an app-specific link or retrieve a OneLink custom link. These links must include the retargeting parameter.

**To set up retargeting tests:**

1. Enable retargeting in the app's settings.

   In the app's dashboard, click **App Settings** and turn on **Enable retargeting attribution**.

   ![Set_Reattribution_window](https://files.readme.io/1fe0c8c4add90c75237b0c5c97b6ff26d8f08ff95bd952912ef746fdec2e9f3d-31828933628561.png)
2. Do one of the following:
   * Create an app-specific attribution link. Make sure to include the retargeting parameter, `is_retargeting=true`, and the advertising ID. To view the GAID, IDFA, or IDFV, follow the  [Registering a test device](/docs/registering-test-devices) instructions.    
     The following is an example of an attribution link that includes an Android-specific parameter as the device identifier (GAID). For more information about adding other device identifier parameters, such as IDFA or IDFV, see [Attribution link structure and parameters](/docs/about-link-structure-and-parameters#ios-specific-parameters).

     ```
     https://app.appsflyer.com/<app_id>?pid=Test&c=Test&is_retargeting=true&advertising_id=<GAID>
     ```
   * Retrieve the [custom link's long URL](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link) from a [OneLink template](/docs/create-a-onelink-template#create-a-onelink-template). Make sure to activate [Retargeting campaign](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings). The following image shows an example of a custom long URL: ![Testing_LongLink_en-us.png](https://files.readme.io/19c706b0cc11b83a5cb08d51b3418654c6fa1e597ee7ff9e631db21c33c00b82-31828933632401.png)

You can now proceed to test re-attribution and re-engagement.

</Accordion>

<Accordion title="Test re-attribution">

**Before you begin:**

* Follow the [instructions](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) for setting up retargeting tests.
* Make sure your test device is **not** registered.

**To test re-attribution:**

1. Uninstall the app from the device. If you just installed the app, wait for a few minutes.
2. Copy the [attribution link](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) you created previously, either the app-specific attribution link or custom long link from the OneLink template, send it to the test device, and then click the link.

In iOS, use iMessage or email to send the link to the device. Don't paste the link in the iOS Notes app and click the link. This action may cause the link to break.

1. Do one of the following:
   * If the app is live, proceed to install it.
   * If the app is pending, install it as follows:
     * **For Android**: Install from Android Studio or an APK file.
     * **For iOS:** Install from TestFlight.
2. Open the app's dashboard, and in the **View type** box, select **Retargeting**.
3. In the **Attribution type** box, select **Re-attributions**.

   You should see the install attributed to the media source and campaign. Allow up to 30 minutes for the retargeted install to appear in the dashboard.

   [![Testing_SDK_Reattribution](https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png)](https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png)

The following describes alternative ways to verify your test results:

* If you have access to raw-data reports, download the Conversions raw-data report. This report takes several minutes to download. **To download the report:**
  1. In AppsFlyer, from the side menu,select **Report** > **Raw Data Export.**
  2. From the **Retargeting** list, click **Conversions (re-engagements & re-attributions)**, and then download the report.
* If you have access to the debug logs, you can use the SDK integration test API to retrieve the attribution results for a specific install.

</Accordion>

<Accordion title="Test re-engagement">

**Before you begin:**

* Follow the [instructions](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) for setting up retargeting tests.
* For testing purposes, set the minimum time between conversions to **None**. This allows all of the re-engagement conversions to be recorded and attributed during testing. ![Testing_Reattribution_window](https://files.readme.io/ec8c7c923093dbed0e99aa5ef57d0239217ead5a9db41f42fe4af8a70eb04551-4406211661841.png)
* Make sure the app is installed on your test device and has been launched several times. If you just installed the app, wait for a few minutes.

**To test re-engagement (direct deep linking):**

Make sure that your app is configured for [deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking), and then follow [this procedure](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing) for testing.

**To test re-engagement (indirect deep linking):**

1. Copy the [attribution link](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) you created previously, either the app-specific attribution link or custom long link from the OneLink template.
2. Send the link to your test device, and then click the link.
3. To open the app, do one of the following:

   * In the app store, click **Open**.
   * Launch the app from your device.

   In the dashboard, you should see a re-engagement attributed to the media source and campaign. Allow up to 30 minutes for the re-engagement to appear.

   [![Testing_SDK_Re-engagement](https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png)](https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png)

**Tip!** Consider downloading the conversions raw data report to verify that the re-engagement was attributed to the correct media source. This report takes several minutes to download.

**To download the report:**

1. In AppsFlyer, from the side menu,select **Report** > **Raw Data Export.**
2. In the **Retargeting** section, download the **Conversions (re-engagements & re-attributions)** report.

</Accordion>

## Testing organic installs

We recommend that you start by testing an organic install.

**To test an organic install:**

1. Install the app on a [registered test device](/docs/registering-test-devices).
2. Launch the app.

The app's dashboard displays a new organic install. Allow up to 30 minutes for the install to appear.

[![](https://files.readme.io/49c242957324516ba93d6c5ebfa338ec19b05820bcf619d8c39d6f7e4ada9bae-31828925882001.png)](https://files.readme.io/49c242957324516ba93d6c5ebfa338ec19b05820bcf619d8c39d6f7e4ada9bae-31828925882001.png)

## Testing CTV

Special test cases include the following:

* **Android TV:** The SDK is compatible with Android-based smart TVs. A marketer or any team member can test these TV apps by following the procedures in this article.
* **Apple TV (tvOS):** The SDK is compatible with Apple TVs (tvOS). A marketer or any team member can test these TV apps by following the procedures in this article.
* **Unpublished tvOS apps:** Requires a marketer and developer to work together (see [Testing tvOS integration before publishing](/docs/testing-tvos-integration-before-publishing)).
* **Amazon Fire TV:** A marketer can [test the integration](/docs/testing-the-sdk-integration-for-marketers#testing-from-the-dashboard) using the Android SDK testing method in the AppsFlyer dashboard. (Learn more about [Amazon Fire TV attribution](/docs/setting-up-amazon-fire-tv-ad-attribution)).
* **PBA web events:** Requires a marketer and developer to work together (see [Testing PBA web SDK integration](/docs/test-pba-web-sdk-integration)).

See also

* Ad network integration testing Ad network integration testing

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Testing links | When using a registered test device, remove the `af_inactivity_window` parameter from the testing link. Otherwise, the install may be incorrectly attributed as *Organic* instead of being attributed to the test link. |

<div data-zendesk-anchors="01H88X11QS2VYFXJGC95TXC6PN=overview h_01HYX9R159XMZKMH1MBMBH9K9J=testing-using-the-sdk-integration-tests-page h_01J9GTS4S2RXJAMYGG6XJ5HFRZ=prepare-a-test-device h_01J9GTW7RAGZXE7GK5BWGBA7N5=perform-the-integration-tests 01H88X11QT0WDRW5GZDCR7MZ3D=testing-using-attribution-links 01H88X11QTQ94BAJGEE1V11F6X=testing-retargeting-using-attribution-links h_01HYX9R1594DD9BEZ6PMV9PJM8=testing-organic-installs Testing%20CTV=testing-ctv 01H88X11QT72F71N49G65BAEAE=testing-ctv h_01J6S6HS0H0M6GQ81WGZ3XT0P9=traits-and-limitations" />

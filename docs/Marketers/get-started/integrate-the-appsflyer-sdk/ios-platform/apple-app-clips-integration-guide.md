---
title: Apple App Clips integration guide
metadata:
  keywords:
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
  created_at: '2020-10-09T00:42:10Z'
  edited_at: '2024-08-05T15:24:14Z'
  id: 360014262358
  locale: en-us
  section: iOS platform
  section_id: 6551263106577
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360014262358-Apple-App-Clips-integration-guide
---
> **At a glance:** App Clips lets users with iOS 14 or later quickly access and experience your app. AppsFlyer enables App Clip attribution, and redirects users who can't use App Clips (for example, Android users) as needed.

![app_clip_flow_3.png](https://files.readme.io/1a5ec7a6b8a061955742d8e79ba78fa0262c0609e1e801decc92300d6c24a774-360012832058.png)

## App Clip integration

* App Clips provide iOS 14 users with quick, convenient access to an app experience, without the need to download the full app.
* App Clips are installed and launched from an invocation (for example, a QR code or NFC tag). **Note**: Safari Smart App Banners and links in Messages are not supported.
* The AppsFlyer SDK is required for App Clip attribution of clicks, installs, in-app events, and App Clip-to-full app installs.
* Independent of the SDK, OneLink redirects users as needed:
  * Users without the app installed:
    * With iOS 14 or later are sent to the App Clip.
    * With iOS 13 or earlier, or Android, are redirected based on your settings in OneLink (to the app store, etc).
  * Users with the app installed are sent to the app based on the Universal Link or App Link setup in OneLink.

### Considerations

* App Clips can be up to 10 MB in size. The AppsFlyer SDK is ~1.5 MB.
* No advertising identifiers available.
* App Clips are deleted by the OS automatically after a 30-day period of inactivity.

> 📄 **Example**
>
> Mark is the marketer of a coffee shop chain. He enlists his iOS developer to create an App Clip that lets customers conveniently skip the line and order in seconds. They simply identify themselves using <Anchor target="_blank" href="https://developer.apple.com/sign-in-with-apple/">Apple Sign-in</Anchor>, order coffee, and pay using <Anchor target="_blank" href="https://developer.apple.com/apple-pay/">Apple Pay</Anchor>. The developer adds the AppsFlyer SDK and makes sure it works in both the app and the app clip.
>
> Mark creates a OneLink and posts the QR code in the coffee shop, along with the tagline "Skip the line!".
>
> Customers scan the QR code and:
>
> * If they have a device with iOS 14 or later, the App Clip opens—with the correct coffee shop branch, and a discount coupon populated.
> * If they already have the full app installed, the app opens in the order coffee page.
> * If they do not have the app and have a device with iOS 13 or earlier, or Android, the app store page for the coffee shop app opens.
>
> Mark uses the AppsFlyer dashboard and reports to see how many clicks and installs the App Clip receives - and how many users proceed to eventually download the full app.

## Metrics and reporting

App Clips analytic and raw data are available in the platform based on the user activity described in the following table.

| User action | AppsFlyer event | Overview dashboard and analytic tools | Raw data |
| --- | --- | --- | --- |
| Invocation (example: QR code) | No event | No event | No event |
| Clicks App Card and App Clip opens | Click and install attributed to the invocation source | <ul><li>Clicks</li><li>Installs</li></ul> | <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor> |
| Uses App Clip | <ul><li>[Optional] Developer sends in-app event</li><li>After the first App Clip launch, follow-up launches are counted as sessions.</li></ul> | <ul><li>In-app event</li><li>Session</li></ul> | <ul><li>In-app event sent by the developer</li><li><Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor></li></ul> |
| Downloads and launches full app | In-app event | In-app event name= af\_app\_clip\_to\_full\_app | <ul><li>In-app event name= af\_app\_clip\_to\_full\_app</li><li><Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |
| Ongoing use of full app | [Optional] Developer sends in-app event | In-app event | <ul><li>In-app event sent by the developer</li><li><Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |

**Cohort dashboard**

View App Clip performance in the <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard#trend-type%E2%80%94user-lifetime-performance">Cohort dashboard</Anchor>, where you can:

* See how long it takes users to go from the App Clip to the full app install.
* Use the in-app conversion metric to compare the performance of different invocation campaigns.

## App Clip implementation

The following procedure detail what you and the iOS developer need to do to develop and integrate App Clips.

#### Scope of work

| **Who's involved**<ul><li>**Advertiser**:<ul><li>Configures Apple App Clips in OneLink templates.</li><li>Puts the OneLink links in the Apple App Store Connect portal.</li><li>Views metrics in AppsFlyer dashboard and reports.</li></ul></li><li>**iOS developer**:<ul><li>Creates the App Clip</li><li>Integrates the AppsFlyer SDK in the App Clip.</li></ul></li></ul> |
| --- |
| **Prerequisites**<ul><li>An AppsFlyer account with at least one app.</li><li>A OneLink template with Universal Links, and OneLink link set up to direct your full app users.<br />**Recommendation**: The template and link invocation you use for the App Clip sends all users without your full app to the App Clip. Therefore, consider having a separate template and custom link for cases in which you want to send those users to the App Store, instead of the App Clip.</li></ul> |

<div id="develop-app-clip" />

<Accordion title="Develop App Clip">

For complete instructions on how developers create an App Clip for your app, see the Apple <Anchor target="_blank" href="https://developer.apple.com/app-clips/">App Clip guide for developers</Anchor>.

For a simplified sample app that demonstrates the usage of App Clips and its integration with a full application, see the <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips/">AppsFlyer App Clip guide</Anchor>.

</Accordion>

<div id="integrate-sdk" />

<Accordion title="Integrate SDK">

* The SDK is required for AppsFlyer attribution of clicks, installs, in-app events, and App Clip-to-full app installs.
* OneLink redirects users independently of SDK integration.

**To install the SDK and configure the full app SDK**:

Send the following links to your iOS developer and tell them to follow the instructions for:

* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-sdk-integration">SDK integration in the App Clip</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-to-full-app-install">Configuring App Clip-to-full app install attribution</Anchor>
* [Optional] <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events">Set up in-app events</Anchor>, if you don't yet have in-app events being measured for your full app, or want to use different in-app events for the App Clip.

</Accordion>

<div id="configure-onelink" />

<Accordion title="Configure OneLink">

**Prerequisites**:

* <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#create-a-onelink-template">OneLink template</Anchor> for your full app with iOS Universal Links configured.
* <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link">OneLink link</Anchor>.
* **Recommendation**: The template and link invocation you use for the App Clip sends all users without your full app to the App Clip. Therefore, consider having a separate template and custom link for cases in which you want to send those users to the App Store, instead of the App Clip.

**To configure the OneLink template for your App Clip**:

1. In the AppsFlyer dashboard, go to **Engage** > **OneLink Management**.
2. Select the **OneLink template** you use to direct users to your full app.
3. Make sure the OneLink template has Universal Links configured. (See <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">instructions</Anchor> for adding Universal Links.)
4. Click **Save**.  
   The AASA file is updated to support the App Clip.
5. In the AppsFlyer dashboard, go to **Engage** > **OneLink Management**.
6. Select the **OneLink custom link** based on the template you configured in steps 1-4 that you use to direct users to your App Clip.
7. Make sure you have a media source (pid) specified.  
   The media source needs to be specified in the URL (for example: **pid=chartboost\_int**) or contained inside the link.

**To verify App Clips is enabled on AppsFlyer OneLink:**

1. Create a URL to get your association file. The URL is created by taking the domain of your OneLink template and adding `/.well-known/apple-app-site-association`.   
   For example: `coffee.onelink.me/.well-known/apple-app-site-association`.
2. Go to the URL of your association file.  
   The apple-app-site-association file is automatically downloaded.
3. Open the apple-app-site-association file with a text editor (for example, Notepad).
4. Make sure the file contains the word "**appclips**". and that the bundle ID ends with "**.Clip**". For example:  

   ```java
   "appclips": {
       "apps": [
         "ABCD1234.id.your.app.Clip",
         ...
       ]
   ...
   }
   ```

   If it does, then you have successfully set up App Clips on the AppsFlyer side, and the App Clip is implemented on any OneLink template with the same subdomain.

</Accordion>

<div id="configure-app-store-connect" />

<Accordion title="Configure App Store Connect">

**Prerequisites**: Completion of [OneLink template configuration for App Clips](/docs/apple-app-clips-integration-guide#configure-onelink)

**To configure your App Clip to work with OneLink**:

1. In your app page in App Store Connect, go to **Build** > **Domain Status**.
2. Make sure your OneLink domain displays under **Build domains** and that **Cache status** and **Debug status** are both “validated”.
3. In the AppsFlyer dashboard, go to **Engage** > **OneLink Management**.
4. Hover over the **Actions** icon of the link you want to use and click **Get URL**.
5. Record the short URL (or the prefix of the long URL).
6. In your app page in App Store Connect, go to **App Clip** > **Edit Advanced Experiences** > **+Add** > **Next**.
7. In **App Clip Experience URL**, paste the OneLink custom URL you recorded in step 5.  
   **Note**: You can append query parameters after the main custom URL, but you cannot change the path.
8. Click **Next**.  
   Your App Clip is now configured to work with OneLink. Further instructions regarding App Store Connect settings are available in the <Anchor target="_blank" href="https://developer.apple.com/documentation/app_clips/configuring_your_app_clip_s_launch_experience">Apple developer guide</Anchor>.

</Accordion>

<div id="testing" />

<Accordion title="Testing">

**Prerequisites**: A <Anchor target="_blank" href="/marketers/docs/registering-test-devices">registered test device</Anchor> with iOS 14 without your full app installed.

**To test your OneLink/App Clip integration:**

1. In the AppsFlyer dashboard, go to **Engage** > **OneLink Management**.
2. Hover over the **Actions** icon of the link you want to test and click **Get URL**.
3. Scan the QR code with your device.  
   The App Clip Card displays on your device, indicating that your OneLink/App Clip integration is properly set up.

</Accordion>

## Traits and limitations

<div id="traits-and-limitations::26141033" />

<Accordion title="Traits and limitations">

| Trait/Limitation | Description |
| --- | --- |
| Invocation methods | <ul><li>QR codes and NFC tags are supported.</li><li>Safari Smart App Banners and links in Messages are not supported.</li></ul> |
| SKAdNetwork | SKAdNetwork functionality isn’t available. Therefore, App Clip installs display in the SKAdNetwork dashboard as organic. |
| OneLink | Only one advanced App Clip experience is allowed per OneLink custom link. This means you cannot add additional paths to the OneLink in App Store Connect. |
| Protect360 | Protect360 does not support App Clips. |

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/guides/ios-14-app-clips/">Attribution solution for Apple App Clips by AppsFlyer</Anchor>

<div data-zendesk-anchors="h_01HDNZQTCBXY0Y3QYCBNVH7EAW=app-clip-integration h_01HDNZQTCBPJWY6H2M452QH644=considerations h_01HDNZQTCB7NB682YTSMNCJSDP=example h_01HDNZQTCBNG3TYRAA7GVPF39P=metrics-and-reporting h_01HDNZQTCBJK7SB96G8A4DHR34=app-clip-implementation h_01HDNZQTCB1AKW9QFRRM9VVN4D=scope-of-work h_01HDNZQTCBN04J3GA8H64V70YY=develop-app-clip h_01HDNZQTCBHHENFYJK7MFJTZ14=integrate-sdk h_01HDNZQTCBN9QV4MZAAWMV164Y=configure-onelink h_01HDNZQTCC6F8TTM2FRQK6DB2E=configure-app-store-connect h_01HDNZQTCCN2BX9NZ4027ZCEFB=testing h_01HDNZQTCCMW2YNK1G34EBM7DM=traits-and-limitations h_01HDNZQTCCV0S78NRK00PK4S0J=traits-and-limitations::26141033 h_01HDNZS83EKJNZGG1QEVS9RMCA=see-also" />

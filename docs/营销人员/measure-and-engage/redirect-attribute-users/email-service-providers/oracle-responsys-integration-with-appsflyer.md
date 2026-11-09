---
title: Oracle Responsys integration with AppsFlyer
metadata:
  keywords:
    - Oracle Responsys
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-11-20T09:26:13Z'
  edited_at: '2026-10-13T01:36:58Z'
  id: 360003798297
  locale: zh-cn
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/zh-cn/articles/360003798297
---
> **At a glance:** Oracle Responsys, an email delivery and analytics platform, embeds AppsFlyer OneLink within emails. Email recipients who click the link are deep linked into your app.

<Image align="center" alt="oracle-responsys-af-logo.png" src="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png" />

ESPs (Email Service Providers) can be excellent sources for segmented user traffic.

One of the challenges with ESPs is performing correct attribution and deep linking. ESPs wrap the deep linking URL with their own ESP's click recording domain. This procedure often breaks the functionality of iOS Universal Links and Android App Links.

However, deep linking and click recording are still possible with ESPs that support Universal Links and App Links on top of their click recording domain. In addition, you can set up your own click domain to act as the click recording domain.

## Prerequisites

* Configure your app to support <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">deep linking with OneLink</Anchor>.
* Verify your SDK version (both Android and iOS)

<Tabs>
<Tab title="iOS">

* AppsFlyer iOS SDK version 4.9.0 (or above)

</Tab>

<Tab title="Android">

* AppsFlyer Android SDK version 4.9.0 (or above)

</Tab>
</Tabs>

## Setting up Oracle Responsys click domain

Follow this section to set up your click domain (click recording domain) in Oracle Responsys.

### Step 1: Set up a click domain in Oracle Responsys

To set up a click domain, follow Oracle Responsys official guide on how to <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCEA/LinkTable_Main.htm?cshid=LinkTable_Main">create click domains</Anchor>. Oracle Responsys uses Link Tables to help record clicks for a specific campaign

**Note**, in Link tables, you can define **IOS link URL** to be the same as the Link URL:

<Image align="center" alt="Oracle-responsys-link-tracking-table.png" src="https://files.readme.io/c151c58af73cf460ba4275a9159e45c15807f311fa8d8b4b1531b0cdf7e3bc4e-49839256667665.png" />

Once you set click domains in Link Tables, Responsys uses these domains to wrap OneLinks that you include in email campaigns. This way, Responsys can record clicks in their system while preserving OneLink and deep linking functionality.

### Step 2: Give Responsys an AASA (iOS) and an Asset Links file (Android)

<div id="aasa-for-ios" />

<Accordion title="AASA for iOS">

For Responsys to support iOS Universal Links, they need an AASA file. See the following instructions.

When you set up OneLink with Universal Links, you already have an AASA associated with the OneLink. To obtain the AASA:

1. Go to OneLink configuration and find a OneLink that is configured with Universal Links.
2. Add **/.well-known/apple-app-site-association** to the end of the OneLink URL.
3. Paste the OneLink in the browser address bar and hit enter. For example: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**. When you do so, the AASA file is downloaded to your computer. You can open it using any simple text editor.
4. Send this AASA file to Responsys. For more information and to learn more about the contents of this file, see page 11 of <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/pdf/ios-universal-links-dev-guide.pdf">Oracle's guide</Anchor>.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Asset Links for Android">

When you set up OneLink with App Links, you already have an Asset Links file associated with the OneLink. To obtain the Asset Links file. To obtain the Asset Links file:

1. Go to OneLink configuration and find a OneLink that is configured with App Links.
2. Add **/.well-known/assetlinks.json** to the end of the OneLink URL.
3. Paste the OneLink in the browser address bar and hit enter. For example:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. When you do so, the Asset Links file is downloaded to your computer. You can open it using any simple text editor.
4. Send this Asset Links file to Responsys. For more information and to learn more about the contents of this file, see <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/android/app-links/">this guide</Anchor>.

</Accordion>

## Setting up your app

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Step 1 for Android: Setting up your app to support App Links">

#### Adding the click domain to the activity in the Android manifest

In the Android manifest, add the click domain host and any prefix in the activity tag of the activity you want to deep link into.

```html Markup
<activity android:name=".DeepLinkActivity">
    <intent-filter  android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" />
           <category android:name="android.intent.category.BROWSABLE" />
           <data android:scheme="https"
               android:host="click.example.com"
               android:pathPrefix="/campaign" />
     </intent-filter>
</activity>
```

#### Setting up the app to resolve click domains

The SDK needs to resolve the OneLink behind the click domain to get the campaign details. The details are returned in the `onAppOpenAttribution` method.

To resolve click domains:

1. Make sure that your SDK version is at least 4.9.0.
2. List the click domains in the SDK API `setResolveDeepLinkURLs`. This API needs to be called before SDK initialization. For more information please refer to SDK documentation <Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">here</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

   * **Important!** If you are using Movable Ink (MI) in conjunction with Oracle, you need to get the MI CNAME and internal domains from your MI account manager and add them to `setResolveDeepLinkURLs`, in addition to the click link for Oracle. For example:

     ```java
     AppsFlyerLib.getInstance().setResolveDeepLinkURLs("oracle-click.example.com", "mi.example.com", "example.micpn.com");
     ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Step 1 for iOS: Setting up your app to support Universal Links">

This section discusses how to set up your app to support Universal Links.

#### Associating click domains in Xcode

1. In Xcode, click on your project.
2. Click on ***Capabilities***. ![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Turn ***Associated Domains*** on.
4. Click the + sign and add your click domain. For example, applinks:click.example.com.

</Accordion>

### Step 2: Setting up the app to resolve click domains

The SDK needs to resolve the OneLink behind the click domain to get the campaign details. The details are returned in the `onAppOpenAttribution` method.

To resolve click domains:

1. Make sure that your SDK version is at least 4.9.0.
2. List the click domains in the SDK property `resolveDeepLinkURLs`. This property needs to be set before SDK initialization. For more information please refer to SDK documentation <Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">here</Anchor>.  

   <Tabs>
   <Tab title="Objective-C">

   ```objectivec
   [AppsFlyerTracker sharedTracker].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerTracker.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

   * **Important!** If you are using Movable Ink (MI) in conjunction with Oracle, you need to get the MI CNAME and internal domains from your MI account manager and add them to `setResolveDeepLinkURLs`, in addition to the click link for Oracle. Domain examples:
     * Oracle domain: oracle-click.example.com
     * MI CNAME domain: mi.example.com
     * MI internal domain: example.micpn.com
3. Add the following code so that the SDK can resolve the click recording domain:  

   <Tabs>
   <Tab title="Objective-C">

   Add this code in AppDelegate.m

   ```objectivec
   - (NSDictionary *)allHTTPHeaderFieldsForResolveDeepLinkURL:(NSURL *)URL {
       if ([URL.host  isEqual: @"click.example.com"]) {
           return [NSDictionary dictionary];
       }
       else {
           return nil;
       }
   }
   ```

   </Tab>

   <Tab title="Swift">

   Add this code in AppDelgate.swift

   ```swift
   func allHTTPHeaderFields(forResolveDeepLinkURL URL: URL!) -> [String : String]! {
       if (URL.host == "click.example.com") {
           /// Change User-Agent
           return [:]
       } else {
           return nil;
       }
   }
   ```

   </Tab>
   </Tabs>

## Sending your first email

1. Create a OneLink URL in the Link Management page (or manually).
2. When creating the OneLink URL make sure to URL encode all parameter values.
3. The following parameters are highly recommended to use:
   * pid (media source) - Use a media source that signifies this usage such as Email.
   * c (campaign) - The name of the campaign you want to measure.
   * af\_dp - The deep link URI scheme you want to deep link your users into.
   * af\_web\_dp - Where to redirect users clicking the link on a desktop.
   * af\_ios\_url - Where to redirect users that don't have the app clicking the link on an iOS device.
   * af\_android\_url - Where to redirect users that don't have the app click the link on an Android device.
4. Place the OneLink URL in the email that you create in Responsys. Example:

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

   At this stage, Responsys wraps the above link with the click domain that you set in the previous steps. Any click on the click domain redirects to the OneLink attribution link. If the app is installed on the user's device, the click domain deep links into the app.

> 📘 **Note**
>
> **Example**
>
> URL parameters are not URL encoded in this example, just for the sake of readability:
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

### Testing your links

After following all the required steps mentioned above, creating the appropriate OneLink URL, and placing it in an email, send yourself a test email.

What should you expect?

If you have the app installed, the app should be invoked. If the relevant AppsFlyer SDK deep linking APIs are implemented you should be deep linked into the relevant content.  
In addition, a click should appear in both the AppsFlyer dashboard, attributed to the provided media source and campaign, and also in Responsys data.

<div data-zendesk-anchors="h_01HDNSK7GR33AN2M4GP956S1FD=prerequisites h_01HDNSK7GR84QSRTS86GH556WK=setting-up-oracle-responsys-click-domain h_01HDNSK7GRHYJZSMYCMT9RVEBW=step-1-set-up-a-click-domain-in-oracle-responsys h_01HDNSK7GRW57NNXMN1SWFTTFZ=step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android h_01HDNSK7GR77N60SFVBD57S9GQ=aasa-for-ios h_01HDNSK7GR6ADJCPG63ZVP19NJ=asset-links-for-android h_01HDNSK7GRN751HAPPQ3HVRMDG=setting-up-your-app h_01HDNSK7GRHCK378A8XKMK7ZZF=step-1-for-android-setting-up-your-app-to-support-app-links h_01HDNSK7GRQNQGWXAEGHSTHADH=adding-the-click-domain-to-the-activity-in-the-android-manifest h_01HDNSK7GRP9ND0MHC3ZHD7G8H=setting-up-the-app-to-resolve-click-domains h_01HDNSK7GRJ682QYAMPB4PSGRZ=step-1-for-ios-setting-up-your-app-to-support-universal-links h_01HDNSK7GSRENM232MQ25EB3J3=associating-click-domains-in-xcode h_01HDNSK7GSP08G2EQSNVR5G45B=step-2-setting-up-the-app-to-resolve-click-domains h_01HDNSK7GSA9VAMTRFCX8SZGSC=sending-your-first-email h_01HDNSK7GSTAJXAP6KGKE9TD8T=testing-your-links" />

---
title: Iterable integration with AppsFlyer
metadata:
  keywords:
    - OneLink
    - Advertisers
    - ESP
    - Developers
    - Iterable
    - Deep Likning
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2019-09-16T13:14:19Z'
  edited_at: '2026-08-14T16:22:46Z'
  id: 360002522337
  locale: en-us
  section: Email service providers
  section_id: 6551247620881
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360002522337-Iterable-integration-with-AppsFlyer
---
Integrate OneLink-based attribution links with Iterable system to [deep link from emails](/docs/email-service-provider-esp-integration-guide). The integration utilizes Iterable’s support for Universal Links on top of branded click recording domains.

![iterable-af-logo.png](https://files.readme.io/e339ea75a54e53711f3c577c7f82339151af13e6c086cc1435cbb57cf1fae3f0-49839295443089.png)

## Introduction

ESPs (Email Service Providers) can be excellent sources for segmented user traffic.

One of the problems with ESPs is recording clicks while keeping deep linking functionality intact. ESPs wrap deep linking URLs with their own ESP's click recording domain. This procedure sometimes breaks the iOS Universal Links process.

With Iterable, which supports Universal Links on top of their click recording domain, deep linking and click recording can still be performed.

## Prerequisites

<Accordion title="iOS">

* AppsFlyer iOS SDK version 4.9.0

</Accordion>

<Accordion title="Android">

* AppsFlyer Android SDK version 4.9.0

Iterable doesn’t support Android App Links. However, [URI Scheme deep linking is still supported](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page). No special actions are required on Iterable side to support deep linking in Android.

</Accordion>

## Setting up Iterable

### Step 1: Setting up link branding in Iterable

Create a dedicated click recording domain and set a subdomain (for example, [click.example.com](http://click.example.com)). This can be done by purchasing a designated domain or using your own domain.

For more information on setting a click recording domain with Iterable, see [here](https://support.iterable.com/hc/en-us/articles/115002651226-Setting-up-mail-domains).

### Step 2: Uploading your SSL certificate to Iterable

Your click recording domain must include your domain’s SSL certificate. The SSL certificate should be installed in your Iterable account. Instructions on installing your SSL certificates can be found [here](https://support.iterable.com/hc/en-us/articles/115000427446-How-to-Set-up-HTTPS-for-Links-for-Click-Tracking).

### Step 2: Give Iterable an AASA (iOS) and an Asset Links file (Android)

<div id="aasa-for-ios" />

<Accordion title="AASA for iOS">

For Iterable to support iOS Universal Links, they need an AASA file. See the following instructions.

When you set up OneLink with Universal Links, you already have an AASA associated with the OneLink. To obtain the AASA:

1. Go to ***OneLink templates*** and find a OneLink that is configured with Universal Links.
2. Add **/.well-known/apple-app-site-association** to the end of the OneLink URL.
3. Paste the OneLink in the browser address bar and hit enter. For example: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**. When you do so, the AASA file is downloaded to your computer. You can open it using any simple text editor.
4. Define link re-write rules. For more information see [here](https://support.iterable.com/hc/en-us/articles/360035496511).
5. Send this AASA file to Iterable. For more information and to learn more about the contents of this file, see [Iterable's guide](https://support.iterable.com/hc/en-us/articles/360035496511-iOS-Universal-Lin).

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Asset Links for Android">

When you set up OneLink with App Links, you already have an Asset Links file associated with the OneLink. To obtain the Asset Links file:

1. Go to ***OneLink templates*** and find a OneLink that is configured with App Links.
2. Add **/.well-known/assetlinks.json** to the end of the OneLink URL.
3. Paste the OneLink in browser address bar and hit enter. For example:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. When you do so, the Asset Links file is downloaded to your computer. You can open it using any simple text editor.
4. Send this Asset Links file to Iterable. For more information and to learn more about the contents of this file, see [Iterable's guide](https://support.iterable.com/hc/en-us/articles/360035127392).

</Accordion>

## Setting up your app

See the following to set up your apps to support App and Universal links.

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Step 1 for Android: Setting up your app to support App Links">

#### Step 1: Adding the click domain to the activity in the Android manifest

In the Android manifest, add the click domain host and any prefix in the activity tag of the activity you want to deep link into.

```xml
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

#### Step 2: Setting up the app to resolve click domains

The SDK needs to resolve the OneLink behind the click domain to get the campaign details. The details are returned in the `onAppOpenAttribution` method.

To resolve click domains:

1. Make sure that your SDK version is at least 4.9.0.
2. List the click domains in the SDK API `setResolveDeepLinkURLs`. This API needs to be called before SDK initialization. For more information, see the SDK documentation [here](/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls).  

   ```
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Step 1 for iOS: Setting up your app to support Universal Links">

This section discusses how to set up your app to support Universal Links.

#### Step 1: Associating click domains in Xcode

1. In Xcode, click on your project.
2. Click on ***Capabilities***.
   ![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Turn ***Associated Domains*** on.
4. Click the + sign and add your click domain. For example, applinks:click.example.com.

</Accordion>

See the following to set up configure the SDK to resolve deep links.

<div id="step-2-for-android-resolve-deep-links" />

<Accordion title="Step 2 for Android: resolve deep links">

The SDK needs to resolve the OneLink behind the click domain to get the campaign details. The details are returned in the `onAppOpenAttribution` method.

To resolve click domains:

1. Make sure that your SDK version is at least 4.9.0.
2. List the click domains in the SDK property `resolveDeepLinkURLs`. This property needs to be set before SDK initialization. For more information, see the SDK documentation [here](/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls).  

   ```
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("clickdomain.com", "myclickdomain.com", "anotherclickdomain.com");
   ```

</Accordion>

<div id="step-2-for-ios-resolve-deep-links" />

<Accordion title="Step 2 for iOS: resolve deep links">

The SDK needs to resolve the OneLink behind the click domain to get the campaign details. The details are returned in the `onAppOpenAttribution` method.

To resolve click domains:

1. Make sure that your SDK version is at least 4.9.0.
2. List the click domains in the SDK property `resolveDeepLinkURLs`. This property needs to be set before SDK initialization. For more information, see the SDK documentation [here](/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls).  

   <Accordion title="Objective-C">

   ```
   [AppsFlyerLib shared].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Accordion>

   <Accordion title="Swift">

   ```
   AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Accordion>

3. Add the following code so that the SDK can resolve the click recording domain:  

   <Accordion title="Objective-C">

   Add this code in AppDelgate.m

   ```
   - (NSDictionary *) allHTTPHeaderFieldsForResolveDeepLinkURL:(NSURL *) URL {
       if ([URL.host  isEqual: @"click.example.com"]) {
           return [NSDictionary dictionary];
       }
       else {
           return nil;
       }
   }
   ```

   </Accordion>

   <Accordion title="Swift">

   Add this code in AppDelgate.swift

   ```
   func allHTTPHeaderFields(forResolveDeepLinkURL URL: URL!) -> [String : String]! {
       if (URL.host == "click.example.com") {
           /// Change User-Agent
           return [:]
       } else {
           return nil;
       }
   }
   ```

   </Accordion>

</Accordion>

## Sending your first email

1. [Create a OneLink URL](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink) on the Link Management page (or manually).
2. When creating the OneLink URL make sure to URL encode all parameter values.
3. The following parameters are highly recommended to use:
   * pid (media source) - Use a media source that signifies this usage such as Email.
   * c (campaign) - The name of the campaign you want to measure.
   * af\_dp - The deep link URI scheme you want to deep link your users into.
   * af\_web\_dp - Where to redirect users clicking the link on desktop.
   * af\_ios\_url - Where to redirect users that don’t have the app clicking the link on an iOS device.
   * af\_android\_url - Where to redirect users that don’t have the app clicking the link on an Android device.
4. Place the OneLink URL in the email that you create in Iterable. Example:

   ```html
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

   At this stage, Iterable wraps the above link with the click domain that you set in the previous steps. Any click on the click domain redirects to the OneLink attribution link. If the app is installed on the user's device, the click domain deep links into the app.

**Example**

URL parameters are not URL encoded in this example, just for the sake of readability:

```
https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
```

### Testing your links

After following all the required steps mentioned above, creating the appropriate OneLink URL, and placing it in an email, send yourself a test email.

What should you expect?

If you have the app installed, the app should be invoked. If the relevant AppsFlyer SDK deep linking APIs are implemented you should be deep linked into the relevant content.  
In addition, a click should appear in both the AppsFlyer dashboard, attributed to the provided media source and campaign, and also in Iterable data.

<div data-zendesk-anchors="h_01HV6PJQRMT8037JMVMMXDPWGN=introduction h_01HV6PJQRM5N1K6CY0NSSFXT3X=prerequisites h_01HV6PJQRMX18FRB3NMZH6NCH0=setting-up-iterable h_01HV6PJQRMMYV3A5ZSEGTT7993=step-1-setting-up-link-branding-in-iterable h_01HV6PJQRMYDDWK9AKGN258TTM=step-2-uploading-your-ssl-certificate-to-iterable h_01HV6PJQRMFJ23627KS83D4C6A=step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android h_01HV6PJQRMNSYK8N7QEE00KSPE=aasa-for-ios h_01HV6PJQRMSMZCVJ5XRXZ3SWEH=asset-links-for-android h_01HV6PJQRMJHDF94JSAT8N8SP9=setting-up-your-app h_01HV6PJQRM5S772CTH219MGY44=step-1-for-android-setting-up-your-app-to-support-app-links h_01HV6PJQRM2V31JAJ52Q3FHQWH=step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest step-2%20setting-up-the-app-to-resolve-click-domains=step-2-setting-up-the-app-to-resolve-click-domains h_01HV6PJQRMCRFM90QSP5SS72SE=step-2-setting-up-the-app-to-resolve-click-domains h_01HV6PJQRMVJB6J6GV41DCYAVQ=step-1-for-ios-setting-up-your-app-to-support-universal-links h_01HV6PJQRNRW8Y97JWHP0MSXZF=step-1-associating-click-domains-in-xcode h_01HV6PJQRNHFH8XGMCEWVGSPA5=step-2-for-android-resolve-deep-links h_01HV6PJQRN4NYPWS2XQQSJAM5R=step-2-for-ios-resolve-deep-links h_01HV6PJQRN2H29D8HKXHBYE1NB=sending-your-first-email h_01HV6PJQRNET2J17ZGGZE0K0Q6=testing-your-links" />

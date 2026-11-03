---
title: EmailLabs integration with AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2022-01-31T14:00:18Z'
  edited_at: '2026-08-14T16:22:42Z'
  id: 4419148952721
  locale: en-us
  section: Email service providers
  section_id: 6551247620881
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4419148952721-EmailLabs-integration-with-AppsFlyer
---
> **At a glance:** EmailLabs, an email delivery and analytics platform, embeds AppsFlyer OneLink within emails. When email recipients click on the link, they are deep-linked into your app.

![emaillabs-af-logo.png](https://files.readme.io/467ee1fbcea8a36dff40172b1dbc97780a7e6cafd958ecb5b520a612c3308231-49839289267857.png)

## Introduction

ESPs (Email Service Providers) can be excellent sources for segmented user traffic.

One of the challenges when using ESPs is recording clicks while persevering deep linking functionality. ESPs wrap the deep linking URL with their own click recording domain. This action often breaks iOS Universal Links.

However, with ESPs that support Universal Links on top of their click recording domain, deep linking and click recording can still be performed successfully.

## SDK version prerequisites

<Tabs>
<Tab title="iOS">

* AppsFlyer iOS SDK version 6.0.4

</Tab>

<Tab title="Android">

* AppsFlyer Android SDK version 6.0.0

</Tab>
</Tabs>

## Step 1: Integration setup in EmailLabs

**To set up the integration in EmailLabs:**

1. Set up your domain according to <Anchor target="_blank" href="https://docs.emaillabs.io/get_started/getting-started/">this article</Anchor>
2. Set up your click recording domain according to <Anchor target="_blank" href="http://docs.emaillabs.io/user-panel/smtp-applications/whitelabel-2/">this article</Anchor> and the screenshot below.  
   ![whitelabel-section-2.png](https://files.readme.io/a5b992868a0abd94b2f24097ead760a98e6529e4f83ecfaf713d681800de4631-49839273475217.png)
3. Enable link tracking according to <Anchor target="_blank" href="http://docs.emaillabs.io/user-panel/smtp-applications/link-tracking/">this article</Anchor> and the screenshot below.  
   ![link-tracking-section-3.png](https://files.readme.io/3c1d0f13d3fcc2b49754cf4beb653592b9fffc27ad27775cf56986f78f9ea53b-49839289275153.png)
4. Contact EmailLabs support at [bok@emaillabs.pl](mailto:bok@emaillabs.pl) and request to enable SSL.
5. In EmailLabs, go to **Panel** > **SMTP** **Accounts** > **Settings** > **Deep** **Links**, and check the Activated box. For iOS apps, enter the <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/General/Conceptual/DevPedia-CocoaCore/AppID.html">Apple Application ID</Anchor> in the respective field.  
   ![deeplinking-section-5.png](https://files.readme.io/15a5b45a58c1a130de6bfe2c3e9e3b379537b4fc549c1c3fcce41ef54b8653e9-49839289277073.png)

### Step 2: Configuring your AppsFlyer SDK

> 📘 **Note**
>
> If you haven’t already done so, make sure you have configured your app to support <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">deep linking with OneLink</Anchor>.

After configuring your click recording domain to support Universal Links as described previously, you need to set up your app to deep-link and resolve that Universal Link.

1. Associate the click recording domain in Xcode:  
   ![configure-xcode-deeplinking-domain.png](https://files.readme.io/923d9bca2fbe448d848b6596c1087bf625ec0a0d5958ff5f28c3fc818275461a-49839289277969.png)
2. Provide the click recording domain to the SDK API `setResolveDeepLinkURLs`. This API needs to be called before SDK initialization. For more information please refer to SDK documentation <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">here</Anchor>.  

   ```objectivec
   [[AppsFlyerLib shared] resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```
3. When the app is invoked due to a click on the Universal Link, the AppsFlyer SDK resolves the deep link and extracts the underlying OneLink. All deep link parameters are then propagated into the onAppOpenAttribution API for deep link logic execution.

## Step 3: Send emails with OneLink through EmailLabs

1. Create a OneLink URL on the Link Management page (or manually). You must URL-encode parameter values.
2. [Best practice] Use the following parameters:
   * *pid* (media source): Use a media source that signifies this usage such as EmailLabs.
   * *c* (campaign): Campaign name
   * *af\_dp*: The deep link URI scheme you want to deep-link your users into.
   * *af\_web\_dp:* Where to redirect users clicking the link on desktop.
   * *af\_ios\_url*: Where to redirect users that don’t have the app clicking the link on an iOS device.
   * *af\_android\_url:* Where to redirect users that don’t have the app click the link on an Android device.
3. Insert the OneLink URL in the email.  
   Example:

   ```html
   <a href="links.example.com data-msys-sublink="appsflyer">Link to your app!</a>
   ```
4. If the email is part of a retargeting campaign, add the parameter is\_retargeting=true.  
   This indicates that the attribution link is from a retargeting campaign. <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">Learn more about retargeting</Anchor>.
5. EmailLabs wraps the link with the defined click domain so that a click on the click domain redirects to the OneLink attribution link.

> 📘 **Note**
>
> **Example**
>
> The URL parameters in the example that follows aren't encoded to enable ease of reading.
>
> ```http
> https://example.onelink.me/abcd?pid=emaillabs&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

## Step 4: Test your links

**To test the integration:**

1. Set up EmailLabs.
2. Create a OneLink URL.
3. Insert the URL in an email.
4. Send a test email to yourself.

**Expected result:**

* If you have the app installed, it should launch and you will be deep-linked into the defined app page.
* A click reflects in:
  * The AppsFlyer dashboard, attributed to the media source and campaign.
  * EmailLabs data.
---
title: Implement Google License Verification Library (LVL)
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2023-07-27T14:45:46Z'
  edited_at: '2025-08-06T08:14:01Z'
  id: 17329535522961
  locale: en-us
  section: Protect your traffic
  section_id: 6551015912465
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/17329535522961-Implement-Google-License-Verification-Library-LVL
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Protect your apps against unauthorized use by adding the Google License Verification Library (LVL) to handle all license-related communication with Google Play.

## Overview

The License Verification Library (LVL) is a library you can add to your apps (downloadable from the Android SDK) that handles all of the licensing-related communication with the Google Play licensing service.

LVL  adds another layer of protection on top of Protect360 algorithms by verifying that installs are coming from real Google Play users. This helps reduce discrepancies between the number of installs visible on Google Play and the AppsFlyer dashboard.

* LVL is available only for Protect360 clients. Without the P360 package, the module does not validate licenses.
* LVL prevents revenue loss from unauthorized app usage, ensuring compliance and protecting your investment.

The Google Play Licensing service determines whether the user is licensed to use an app or not. Google Play considers users to be licensed if they are recorded purchasers of the app. The license is unique per app and can be used for enhanced protection. <Anchor target="_blank" href="https://developer.android.com/google/play/licensing">Learn more</Anchor>

The AppsFlyer SDK collects the data from the customer side, and Protect360 performs the server-side license verification, blocking fraudulent installs that fail verification for both organic and non-organic installs. The “Block reason” you will see in the Protect360 dashboard and reports will be “Bots”.

## Set up LVL

<div id="add-lvl" />

<Accordion title="Set up process">

Currently, this is a manual process where you'll need to pass the below information to your AppsFlyer CSM so they can add it manually.

**To add the LVL:**

1. Define a property in the gradle.properties file called:

   ```http
   appsflyerSdkVersion = "YOUR_SDK_VERSION" // e.g., 6.15.2
   ```
2. Reference the property dynamically in your build.gradle file:

   ```http
   dependencies {
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```
3. For Kotlin DSL Users:

   ```http
   dependencies {
       val appsflyerSdkVersion = "<YOUR_SDK_VERSION>" // e.g., 6.15.2
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```

   > 📘 **Note**
   >
   > You can define a local variable under the dependencies section. This will align the LVL and AppsFlyer SDK versions to be the same ensuring that both modules have the same versions.

4. Get the app’s Licensing & in-app billing:  
   From the Google Play Developer Console (Select the app -> Development Tools -> Services and APIs).

   ```http
   Base64-encoded RSA public key
   ```
5. Please provide your CSM with the following information:

* Public key
* app-id
* Minimum app-version the LVL is integrated in
* A screenshot of their LVL (Liveness Verification Library) implementation

</Accordion>

<div id="test-and-troubleshoot" />

<Accordion title="Next steps">

Once we get your request, the Protect360 team will configure LVL verification in STAGING mode. At this stage, the system will only report the results of LVL verification internally for AppsFlyer. A couple of days later, we will check our data.

**If everything looks good:**

* We will set the LVL verification to PRODUCTION mode and it will start blocking traffic.
* The Protect360 team will notify the CSM.

**If something isn't right** (like if we don't see LVL information on the install events):

* We will leave the LVL verification in STAGING mode.
* Your CSM will notify you and help you troubleshoot the implementation in the app.

</Accordion>

<div id="setup-process" />

<Accordion title="Test and troubleshoot">

When debugging the app, you should be able to see LVL information on the payload that is sent to AppsFlyer, like the example below:

```json
"lvl":{
      "ttr":,<ttr>,
      "signature":"<signature>",
      "signedData":"<signedData>"
   }
```

Work with your support/SDK team in case there is no LVL information on the install message.

</Accordion>

## FAQ

<div id="what-if-an-app-is-installed-from-a-store-other-than-google-play" />

<Accordion title="What if an app is installed from a store other than Google Play?">

LVL validation will not verify and not block installs coming from stores other than Google Play.

</Accordion>

<div id="how-much-time-does-it-take-to-get-lvl-set-up" />

<Accordion title="How much time does it take to get LVL set up?">

Once we get the information, it takes a few business days to set up LVL and verify the data. See details about the [setup process](/docs/implement-google-license-verification-library-lvl#setup-process).

</Accordion>

<div id="does-lvl-affect-app-functionality" />

<Accordion title="Does LVL affect app functionality?">

No, app functionality is not affected.

</Accordion>

<div id="what-is-the-difference-between-lvl-and-gpreferrer" />

<Accordion title="What is the difference between LVL and GP-referrer?">

The license verification using LVL, differs from GP-referrer verification algorithms as the LVL handles license verification for the app itself (license per app), while the GP-referrer is used to get the install's redirection source to the Google Play store with the installed package's referrer URL (the timestamps of when a referrer click happened, when the installation began, the app version, etc.). In short, while LVL is used for checking that the user is licensed to use the app, the GP-referrer is used for verifying that the install details were not forged.

</Accordion>

<div data-zendesk-anchors="01H7YJ35YKDHJ2MDZSSYKMDCJ4=overview 01H7YJ35YKDW0CB9TWRBKFBCDJ=set-up-lvl 01H7YJ35YK585NA5F4HZN8C74K=add-lvl 01JGK7NK10ZDD6CM6Y4631FB4Q=note 01H7YJ35YKX1CVYMRZ1W8NRH7Y=test-and-troubleshoot 01H7YJ35YKMCN2E2BDWA5DD5M3=setup-process 01H7YJ35YMR8PBTTSHD77WZ4AE=faq 01H7YJ35YMRZ8KRSVND1JT6JGH=what-if-an-app-is-installed-from-a-store-other-than-google-play 01H7YJ35YM11J0EG0B8PBMSPAC=how-much-time-does-it-take-to-get-lvl-set-up 01H7YJ35YMH0NM73Y1R90JDMEA=does-lvl-affect-app-functionality 01H7YJ35YM6RHCA6QP3MK0Y9J0=what-is-the-difference-between-lvl-and-gpreferrer" />

---
title: "Implement Google License Verification Library (LVL)"
excerpt: "Protect your Android apps against unauthorized use by integrating the Google License Verification Library to verify installs from real Google Play users."
x-zendesk:
  id: 17329535522961
  url: https://support.appsflyer.com/hc/en-us/articles/17329535522961-Implement-Google-License-Verification-Library-LVL
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Protect your traffic
  section_id: 6551015912465
  position: 10
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-roy-yanai, Marketers, Protect360]
  labels: [Premium, Premium Feature, Marketers, Localize, Loc Published]
  promoted: false
  comments_disabled: false
  created_at: '2023-07-27T14:45:46Z'
  edited_at: '2025-08-06T08:14:01Z'
---
The License Verification Library (LVL) is a library you can add to your apps (downloadable from the Android SDK) that handles all of the licensing-related communication with the Google Play licensing service.

LVL adds another layer of protection on top of Protect360 algorithms by verifying that installs are coming from real Google Play users. This helps reduce discrepancies between the number of installs visible on Google Play and the AppsFlyer dashboard.

> 📘 Protect360 Requirement
>
> LVL is available only for Protect360 clients. Without the P360 package, the module does not validate licenses.

- LVL prevents revenue loss from unauthorized app usage, ensuring compliance and protecting your investment.

The Google Play Licensing service determines whether the user is licensed to use an app or not. Google Play considers users to be licensed if they are recorded purchasers of the app. The license is unique per app and can be used for enhanced protection. [Learn more](https://developer.android.com/google/play/licensing)

The AppsFlyer SDK collects the data from the customer side, and Protect360 performs the server-side license verification, blocking fraudulent installs that fail verification for both organic and non-organic installs. The “Block reason” you will see in the Protect360 dashboard and reports will be “Bots”.

## Set up LVL

### Set up process

Currently, this is a manual process where you'll need to pass the below information to your AppsFlyer CSM so they can add it manually.

**To add the LVL:**

1. Define a property in the `gradle.properties` file called:

```http
appsflyerSdkVersion = "YOUR_SDK_VERSION" // e.g., 6.15.2
```

2. Reference the property dynamically in your `build.gradle` file:

<Tabs>
<Tab title="Groovy">

```http
dependencies {
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
}
```

</Tab>
<Tab title="Kotlin DSL">

```http
dependencies {
       val appsflyerSdkVersion = "<YOUR_SDK_VERSION>" // e.g., 6.15.2
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
}
```

</Tab>
</Tabs>

> 👍 Tip
>
> You can define a local variable under the dependencies section. This will align the LVL and AppsFlyer SDK versions to be the same ensuring that both modules have the same versions.

4. Get the app’s Licensing & in-app billing:

From the Google Play Developer Console (Select the app -> Development Tools -> Services and APIs).

```auto
AutoBase64-encoded RSA public key
```

5. Please provide your CSM with the following information:

- Public key
- app-id
- Minimum app-version the LVL is integrated in
- A screenshot of their LVL (Liveness Verification Library) implementation

### Next steps

Once we get your request, the Protect360 team will configure LVL verification in STAGING mode. At this stage, the system will only report the results of LVL verification internally for AppsFlyer. A couple of days later, we will check our data.

**If everything looks good:**

- We will set the LVL verification to PRODUCTION mode and it will start blocking traffic.
- The Protect360 team will notify the CSM.

**If something isn't right** (like if we don't see LVL information on the install events):

- We will leave the LVL verification in STAGING mode.
- Your CSM will notify you and help you troubleshoot the implementation in the app.

### Test and troubleshoot

When debugging the app, you should be able to see LVL information on the payload that is sent to AppsFlyer, like the example below:

```json
"lvl":{
      "ttr":<ttr>,
      "signature":"<signature>",
      "signedData":"<signedData>"
   }
```

Work with your support/SDK team in case there is no LVL information on the install message.

## FAQ

<Accordion title="What if an app is installed from a store other than Google Play?">

LVL validation will not verify and not block installs coming from stores other than Google Play.

</Accordion>

<Accordion title="How much time does it take to get LVL set up?">

Once we get the information, it takes a few business days to set up LVL and verify the data. See details about the [setup process](#setup-process).

</Accordion>

<Accordion title="Does LVL affect app functionality?">

No, app functionality is not affected.

</Accordion>

<Accordion title="What is the difference between LVL and GP-referrer?">

The license verification using LVL, differs from GP-referrer verification algorithms as the LVL handles license verification for the app itself (license per app), while the GP-referrer is used to get the install's redirection source to the Google Play store with the installed package's referrer URL (the timestamps of when a referrer click happened, when the installation began, the app version, etc.). In short, while LVL is used for checking that the user is licensed to use the app, the GP-referrer is used for verifying that the install details were not forged.

</Accordion>
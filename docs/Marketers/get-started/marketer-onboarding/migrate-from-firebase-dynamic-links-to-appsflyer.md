---
title: "Migrate from Firebase Dynamic Links to AppsFlyer"
excerpt: "Migrate from Firebase Dynamic Links to AppsFlyer OneLink using our step-by-step guide to prevent disruptions to user journeys."
---
Google’s [Firebase Dynamic Links](https://firebase.google.com/docs/dynamic-links) will be deprecated on August 25, 2025. Effective on this date, all links served by Firebase Dynamic Links (both hosted on custom domains and page.link subdomains) will stop working, and new link creation will be disabled. If you use Firebase Dynamic Links, it's essential to take proactive steps as soon as possible to migrate your links elsewhere to prevent disruptions to user journeys from your campaigns.

AppsFlyer OneLink enables you to easily create links with attribution, redirection, and deep linking capabilities on owned or paid media, regardless of device, operating system, channel, or platform. Partner with AppsFlyer to create personalized, contextual user journeys that drive users to your app for maximum conversion and revenue. Follow the instructions below to get started migrating your Firebase Dynamic Links to AppsFlyer.

## Migrate from Firebase to AppsFlyer

This section describes how to migrate your Firebase dynamic links over to AppsFlyer OneLink.

**To migrate to AppsFlyer:**

**Prerequisites**

Before you begin, you'll need your:

- Dynamic Links from Firebase
- App developer

### Step 1. Create an AppsFlyer account

- [Create an AppsFlyer account](https://www.appsflyer.com/get-started/).
- [Add account users with appropriate permissions](https://support.appsflyer.com/hc/articles/4409128270481--Beta-User-management).

### Step 2. Add your app

- [Add your app](https://support.appsflyer.com/hc/articles/207377436) in AppsFlyer.
- [Optional] Change the default 90-day [re-attribution window](https://support.appsflyer.com/hc/articles/115002587066) to align with your definition of active users.

![add](https://files.readme.io/7f7bab2277d0f45434618d28714c727ccbb9e414192b765dd22551bcbd5b0a37-16950840602769.png)

### Step 3. Create a OneLink template (app developer collaboration)

**You and your app developer are both needed for this step.**

A OneLink template is required for creating links and end-user experiences. It forms the basis of the redirection logic for all OneLink links you create for your various marketing campaigns.

- [Create a OneLink template](https://support.appsflyer.com/hc/articles/207032246-OneLink-templates#procedures) - You must either be an AppsFlyer admin user or have [permissions to add/edit OneLink templates](https://support.appsflyer.com/hc/articles/4409128270481)

### Step 4. Set up the AppsFlyer SDK (app developer task)

**Your app developer is needed for this step.**

The AppsFlyer SDK integrated into the app is the link between the app and the AppsFlyer platform. It provides:

- Deep linking - The SDK enables unified deep linking (UDL) implementation
- Attribution - The SDK reports app installs, app opens, in-app events, and so on.

Integrate AppsFlyer SDK in your app using the steps below.

#### AppsFlyer SDK integration steps

1. Integrate the AppsFlyer SDK into the app.

See the guides for Android and iOS [SDK integration](/docs/sdk-integration-overview).
2. Map in-app events you want to be recorded, using the AppsFlyer schemes.

This can be done via [SDK](https://support.appsflyer.com/hc/articles/115005544169) or [S2S](https://support.appsflyer.com/hc/articles/207034486).
3. Handle Firebase's SDK.

You can switch exclusively to AppsFlyer, or run both SDKs simultaneously for a few weeks. View a breakdown of these options in the table below.

| Option | What happens after<br>updated app version release | Impact |
| --- | --- | --- |
| Remove Firebase's SDK (recommended) | Only AppsFlyer records new installs and updating users.<br>Firebase still shows events performed by users, until the users update their app too. | - Fast transition<br> - No double attribution<br> - Allows you to see if you have any lingering app versions with the Firebase SDK still on them |
| Keep Firebase's SDK for a transition period | AppsFlyer and Firebase attribute new installs and report events. At a later date, remove the Firebase SDK. | - Data validation is possible. Meaning, you can compare data from AppsFlyer and Firebase<br> - Double attribution, which may cause double charges with ad networks<br> - Higher workload |

4. After all other tasks in the scope of work are completed, update the app version with AppsFlyer SDK to the market. New users are attributed by AppsFlyer.

> 📘 Note
>
> - Make sure to update the app for iOS, Google Play, and any relevant Android out-of-store markets.
> - Your Android app may exist on unofficial APK sites, even if you don't know it (search the web for your app's package name to find out). APK sites take some time to update to the latest version, so they may bring organic users, which install old versions without AppsFlyer SDK.
> - App update rollouts in the app stores can take a couple of days to fully complete. Users installing during this phase may still get the previous version.

### Step 5. Understand parameter mapping (app developer task)

**Your app developer is needed for this step.**

Understand how Firebase Dynamic Links parameters map to AppsFlyer's corresponding parameters.

Correct mapping and understanding of the corresponding parameters will ensure your links get the same results.

The table below lists all of Firebase's parameters and the corresponding AppsFlyer parameters.

Use this table as a reference for all the parameters you currently use when you migrate to AppsFlyer.

> 📘 Note
>
> If a Firebase parameter isn't listed, it is because AppsFlyer covers this in the OneLink template setup without you needing to put a parameter in your links.

| Grouping | Firebase | AppsFlyer | Description |
| --- | --- | --- | --- |
| Mobile parameters | link | - af\_dp<br>- deep\_link\_value | - **af\_dp** - URI scheme used as a fallback method to launch iOS and Android apps.<br>- **deep\_link\_value** - Value name for the specific in-app content that users will be directed to. |
| Android parameters | afl | af\_android\_url | Allows redirection of Android users to a customized web page (the domain must be in the [redirect allowlist](https://support.appsflyer.com/hc/articles/25068636064529)) |
| iOS parameters | ifl | af\_ios\_url | Allows redirection of iOS users to a customized web page (the domain must be in the [redirect allowlist](https://support.appsflyer.com/hc/articles/25068636064529)) |
| | efr | af\_force\_deeplink | Used to force an iOS app to open using the af\_dp URI scheme. Without this, the app won't open using the URI scheme |
| Other platform URL | ofl | af\_web\_dp | Allows redirection of desktop users to a customized web page |
| Social tags | st | af\_og\_title | Used to customize the title of shared content on Social media |
| | sd | af\_og\_description | Used to customize the description of shared content on social media |
| | si | af\_og\_image | Used to customize the image of shared content on social media |
| Analytic parameters | utm\_source | pid | Media Source |
| | utm\_medium | af\_channel | Identifies the media source channels where your ads are distributed |
| | utm\_campaign | c | Campaign name |
| | utm\_term | af\_keywords | Keywords list for text-targeted campaigns |
| | utm\_content | af\_adset | Collection of ads associated with a campaign |

### Step 6. Create OneLink links with mapped parameters

Using your mapped parameters, you can create OneLink links from your OneLink template.

Links can be created [in bulk](https://support.appsflyer.com/hc/articles/14511403892369-Bulk-Links) via CSV file, programmatically with the [OneLink API](https://support.appsflyer.com/hc/articles/360001250345), individually using the [AppsFlyer dashboard](https://support.appsflyer.com/hc/articles/115005248543), in the [SDK](https://support.appsflyer.com/hc/articles/115004480866), or as manually constructed [long links](https://support.appsflyer.com/hc/articles/360017132597-OneLink-long-URLs).

Use the following table to determine which method best works for your use.

| Firebase | AppsFlyer | Use it if | Notes |
| --- | --- | --- | --- |
| Firebase console | [OneLink Management page](https://support.appsflyer.com/hc/articles/115005248543-Set-up-OneLink-Complete-guide) | You would like to create OneLink links one by one. In this way, you can utilize the full OneLink features and possibilities | |
| Dynamic Link Builder API | [SDK](/docs/user-invite-attribution) | You would like to create in-app programmatically generated links for uses such as user invites and referrals | - Requires iOS or Android developer |
| Firebase REST API | [OneLink API](https://support.appsflyer.com/hc/articles/360001250345-Use-the-OneLink-API-for-custom-integrations) | You would like to create links programmatically outside the mobile app | - Requires a developer<br>- Not available on the free plan |
| Manual link construction | [Long links](/docs/understand-onelink-short-vs-long-urls) | You would like to manually construct the link with its query parameters. Use if you don't require short links For example if the link will be behind a button or a banner | |
| | [Bulk Links](https://support.appsflyer.com/hc/articles/14511403892369-Perform-bulk-actions-on-OneLink-links-via-CSV) | You would like to migrate all your Firebase dynamic links in bulk to AppsFlyer.<br>This is recommended to quickly move over all your links without any errors | - Requires a pre-step of [mapping the link parameter keys and values according to the corresponding Firebase parameters](https://support.appsflyer.com/hc/articles/16282289097105#map-parameters)<br>- Not available on the free plan. |
| | [Smart Banner](/docs/smart-banners-mobile-web-to-app-for-marketers) | you would like to create banners on mobile websites that deep link to your app | |
| | [Smart Script](/docs/set-up-smart-script-to-convert-web-visitors) | If you would like to construct a long link dynamically in a web page for a web-to-app experience | |

#### See also

<Cards>
  <Card title="Branded Domains" href="https://support.appsflyer.com/hc/articles/360002329137-Branded-Domains">
    Learn how to set up and use branded domains with AppsFlyer.
  </Card>
  <Card title="Using Firebase and Google Tag Manager with AppsFlyer" href="https://support.appsflyer.com/hc/articles/210353513">
    An overview of integrating Firebase and Google Tag Manager with AppsFlyer.
  </Card>
</Cards>
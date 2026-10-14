---
title: Adding an app to AppsFlyer
excerpt: >-
  Learn how to add your app to AppsFlyer so you can get attribution data on
  installs and in-app events, and analyze the data using the different tools on
  AppsFlyer.
metadata:
  keywords:
    - Add App
    - adding an app
    - Advertisers
    - could not add app
    - security reasons
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2016-01-20T08:57:00Z'
  edited_at: '2026-08-03T09:05:58Z'
  id: 207377436
  locale: en-us
  section: Manage your apps
  section_id: 6551015977105
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207377436-Adding-an-app-to-AppsFlyer
---
## Overview

If you haven't yet added an app to your dashboard, the app onboarding page will display when you log into AppsFlyer. App onboarding guides you through all the steps to add your app and also get it ready for attribution.

### Entering the wizard for adding an app

You can enter the wizard for adding apps from the platform or you can add your app via the app onboarding page (for Android and iOS apps only).

**To enter the wizard from the app onboarding page:**

* In the **Add your app** step, click **Add app** and follow the instructions for adding an app.

> 📘 **Note**
>
> If the onboarding page isn't already open, from the top menu bar > email address dropdown, click **App onboarding**.

![onboarding page.png](https://files.readme.io/8903839c25f12df28e1c4b488699670e2dadca83af9ddfebfc0cf4eacd2ce744-33198275479953.png)

**To enter the Add an app wizard from the platform:**

* From the top menu bar > **My Apps,** click **+ Add app**
* From the AppsFlyer Homepage, click **+ Add app**
* From the top bar, open the account menu (email address dropdown) >**App onboarding**, click **+ Onboard another app**

![add an app (1).png](https://files.readme.io/894b7b76c1da76e2308b110266cbffeb579c551033ce302ade182c1d63fd9384-33198275483793.png)

## Adding an app

After you've [entered the Add an app wizard](#entering-the-wizard-for-adding-an-app), follow these steps:

1. [Enter the app details](#enter-app-details).
2. [Enter additional information](#enter-additional-information-not-applicable-to-web-apps).
3. Click **Add my app**.
4. Copy the Dev key, to be used in the [SDK integration](/docs/getting-started-onboarding-for-marketers#step-2-sdk--api-integration) (you can retrieve it later from the [App Settings](/docs/app-settings#general-app-settings) page).
5. Click **Done** or **+ Add another app** to add more apps. Repeat the process for adding more apps.

> 📘 **Note**
>
> * Only admins and [account users with the necessary permissions](/docs/user-management) are able to add apps.
> * As you follow the steps for adding an app (below), the available options will vary depending on the previous options you've selected.

After registering the app, it will appear on the dashboard. To have installs and in-app events recorded and attributed to the correct media sources, you'll need to:

* Integrate the SDK
* Connect the app to partners in the Partner Marketplace

See [all the steps](/docs/getting-started-onboarding-for-marketers) for completing the onboarding process.

### Enter app details

Select the app platform and enter the required details, as listed below:

<div id="android-androidtv-fire" />

<Accordion title="Android, AndroidTV, Fire">

Use this option for the following platforms:

* Android (mobile)
* AndroidTV
* Amazon Fire
* Amazon Fire TV
* Kindle

| Google Play status | When to use it | Required details |
| --- | --- | --- |
| <span id="in-store"></span>In store | Your app is currently available in the Google Play store | **Google Play URL** (copied from Google Play)<ul><li>**Example:** https://play.google.com/store/apps/details?id=com.appsflyer.adNetworkTest&hl=en&gl=GB</li><li>**Important!**<ul><li>If your app is **not** listed in the US Google Play store:<ul><li>The URL must include the country code of any store in which it is listed, as shown in the example above: **&gl=`{country_code}.** If you do not include the country code, you will receive an error when trying to add the app.</li><li>The language code is optional: **&hl={language_code}`**</li></ul></li><li>If your store **is** listed in the US Google Play store, both the country and language codes are optional.</li></ul></li></ul> |
| <span id="pending-approval-not-published"></span>Pending approval/not published | Your app is not yet published or is pending approval from Google Play | **Android package name**<ul><li>**Example:** com.appsflyer.adNetworkTest</li><li>**Note:** Package name is case sensitive</li><li>**Format:**<ul><li>At least two segments (one or more dots)</li><li>Each segment must start with a letter</li><li>All characters must be alphanumeric or underscore (a-z, A-Z, 0-9, or \_)</li><li>Maximum length of 100 characters</li></ul></li></ul>For more information, see [Android developer documentation](https://developer.android.com/studio/build/application-id) |
| <span id="third-party-store-out-of-store"></span>3rd-party store/out-of-store | Your app is in an Android app store other than Google Play, and/or it can be downloaded from a location other than an app store | <ul><li>**Android package name:** For detailed requirements, see previous row.</li><li>**App URL:** (copied from the 3rd-party app store or out-of-store location)</li><li>**Channel name: (optional)** a unique name you set in the AndroidManifest.xml of the individual APK prepared for that store/location, e.g. my\_apk. The name must be:<ul><li>case-sensitive</li><li>identical to the name you entered in [the **Channel name** field when you added the app](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app).</li></ul></li></ul>```<br />&lt;application><br />...<br /><br />...<br />&lt;/application><br />```<br /><br />Note<br /><br /><br />**<span id="h_01KRB930DZ2NRYBZSERSG7WB3A"></span>Note**<br />Using the channel parameter for multi-store attribution is not recommended. For a simpler and more standardized implementation, use the af\_store parameter instead.<br /><br /><br /><br /><br />**<span id="01H815FE641Q6N5JY5846QE59Y"></span>Important!**<br />If your app is available from more than one source (in other words, any combination of Google Play, 3rd-party stores, or out-of-store locations), it is vital to consider the options for [setting up multi-store Android attribution](/docs/set-up-multi-store-android-attribution). |

</Accordion>

<div id="ios-tvos-macos" />

<Accordion title="ioS, tvOS, MacOS">

Use this option for the following platforms:

* iOS
* tvOS
* MacOS

| App Store status | When to use it | Required details |
| --- | --- | --- |
| <span id="in-store::f93cfa22"></span>In store | Your app is currently available in the App Store | **App Store URL** (copied from the App Store)<ul><li>**Example:** https://apps.apple.com/us/app/partner-integrations/id1543229303</li><li>**Notes:**<ul><li>Be sure that the URL includes the 2-letter country code of the store (for example, **us** in the URL above)</li><li>An app added to the App Store prior to June 14, 2019, may contain itunes.apple.com in its URL (instead of apps.apple.com).</li></ul></li></ul> |
| <span id="pending-approvalnot-published"></span>Pending approval/not published | Your app is not yet published or is pending approval from the App Store | **Country** of the App Store to which the app has been submitted<br /><br />**App ID** assigned by the App Store, without the prefix id<ul><li>**Example:** 1543229303</li><li>**Format:** 9 or 10 numeric characters, 0-9</li></ul> |

</Accordion>

<div id="windows-xbox" />

<Accordion title="Windows">

Use this option for the following platforms:

* Windows Phone
* Windows (desktop)

| Microsoft Store status | When to use it | Required details |
| --- | --- | --- |
| In store | Your app is currently available in the Microsoft Store | **Microsoft Store URL** (copied from the Microsoft Store)<ul><li>**Example:** https://www.microsoft.com/en-us/p/wordament/9wzdncrfhwfg</li><li>**Note:** The URL above is an example for a Windows Phone app. URL format varies for Windows desktop apps.</li></ul>**App ID:** Maximum length of 150 characters. |
| Pending approval/not published | Your app is not yet published or is pending approval from the store | **App ID** assigned by the Microsoft Store<ul><li>**Maximum length:** 150 characters</li><li>**Example:** 9wzdncrfhwfg</li><li>**Note:** App ID is case sensitive</li></ul> |

</Accordion>

<div id="web-pba" />

<Accordion title="Web (PBA)">

> 📘 **Note**
>
> A web app is where you define a website to include in a brand bundle for our People-Based Attribution (PBA) feature.
>
> * This option is available only to customers who have subscribed to PBA.
> * [Learn more](/docs/people-based-attribution-pba-overview) about PBA and attributing web visits, web events, and website-assisted installs to obtain a unified view of customer journeys across channels, platforms, and devices.

**Full URL:** The full URL of the website for which you want to measure traffic. This is the website on which you have implemented (or will implement) the [PBA Web SDK](/docs/onboarding-guide-to-people-based-attribution#2).

[![URL_diagram](https://files.readme.io/45c6e433af693fd8c293380192a8e60f26c82588195bab61bafbc9839baf5c7b-33198323426961.png)](https://files.readme.io/45c6e433af693fd8c293380192a8e60f26c82588195bab61bafbc9839baf5c7b-33198323426961.png)

Include –

* scheme
* subdomain [optional]
* domain name
* top-level domain
* path [optional] – the address of a specific directory or page on your website

**App name:** The name you have chosen for your app

* Maximum length: 100 characters
* XSS tags not permitted

> 📘 **Important!**
>
> Once you create a web app, you are not able to edit its properties (URL and app name) without deleting it and re-creating it, **which means you also must** [**delete the brand bundle**](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) **of which it is a part.**

**Next steps:**

* Add your newly-created web app to a [PBA brand bundle](/docs/pba-brand-bundles-and-settings) to see it on the PBA dashboard.
  * Make sure all the mobile apps you want to include in the brand bundle have been added to your account before creating the bundle.
* [Integrate the PBA Web SDK](/docs/pba-web-sdk-integration-guide) to the website specified in the web app to get the measurement data flowing.

</Accordion>

<div id="web" />

<Accordion title="Web">

Use the Web platform to create a new Web app and measure website visits and conversions using Web Performance Measurement.

#### **Before you begin**

* Legacy People-Based Attribution (PBA) web apps appear under “**Web (PBA)”** marked as Legacy.
* If you are migrating from a legacy PBA Web app, you can use your existing PBA Web Dev Key.

#### **To add a Web app**

1. Go to **My Apps** > **Add app**.
2. Select **Website**.
3. Enter the following:

**App name**: The name you have chosen for your Web app.

* **Length:** 1-100 characters
* **Allowed characters:** Letters (any language), numbers, spaces (not at start or end), and special characters: . - \_ :
* **Blocked characters:** ; \`{ }\` $ < > \` \

**Example:** My Online Store, Corporate Website 2024, E-Commerce\_Production

**Primary domain (Full URL)**: The primary domain of your website. This is set during web app creation and cannot be changed afterward.

* **Format:** Valid domain name only (no protocol, path, or port)
* **Length:** Maximum 500 characters
* **Processing:** AppsFlyer automatically
  * Removes http:// or https://
  * Removes trailing slashes
  * converts the domain to lowercase
* **Immutability:** Cannot be edited after app creation

**Important:** To change the primary domain, you must delete and recreate the web app, which results in loss of historical data continuity.

**Examples:**

* https://shop.example.com/checkout → Stored as shop.example.com → App ID: website-shop.example.com
* example.com/ → Stored as example.com → App ID: [website-example.com](http://website-example.com)

**App ID**: The unique ID AppsFlyer creates for the Web app, based on the primary domain.

* Generated automatically using the format: website-`<primary_domain>`
* Example: website-shop.example.com

**Web SDK ID**: The identifier used by the Web SDK for attribution (previously named web\_dev\_key).

Two options during app creation:

**Option 1: Generate new (default)**

* Automatically creates a new Web SDK ID
* Format: website-`{yourdomain.com}`
* Example: website-shop.example.com
* **Use case:** New web attribution implementations

**Option 2: Reuse existing PBA dev key**

* Select from dropdown of existing PBA (People-Based Attribution) web app dev keys
* Enables seamless migration without changing website code
* **Use case:** Migrating from legacy PBA to the new web attribution solution

**Note:** Reusing the PBA Dev Key allows you to migrate from PBA to the new Web app **without making any changes to your website implementation.**

Each PBA dev key can only be assigned to **ONE** web app. Once a PBA dev key is used for a web app, it is no longer available for other web apps.

* **Length:** 1-550 characters
* **Immutability:** Cannot be changed after app creation
* **PBA migration:** Only dev keys from your account's PBA web apps appear in the dropdown

**Currency**: The currency used for the app’s reporting.

* Standard ISO 4217 currency code (e.g., USD, EUR, GBP, ILS)
* Selected from dropdown
* Required field

**Time zone**: The time zone used for the app’s reporting.

* IANA time zone format (e.g., America/New\_York, Europe/London, Asia/Tokyo)
* Selected from dropdown
* Required field

4. Click **Create app**.

**Limitations**

* The **primary domain cannot be changed** after the app is created.
* The primary domain is automatically added to **Excluded Domains** as type **PRIMARY**.

Each legacy **Web Dev Key can be reused for only one** new Web app.

> 📘 **Note**
>
> For full information on Web attribution settings [see here](/docs/configure-web-performance-measurement-settings).

</Accordion>

<div id="roku" />

<Accordion title="Roku">

**App name:** Channel name copied from the [Roku Developer Dashboard](https://developer.roku.com/developer).

* **Example:** My Roku channel
* **Format:**
  * Maximum length of 100 characters
  * XSS tags not permitted

**Channel ID:** Numeric ID assigned to the channel by Roku.

* **Format:**
  * Numeric characters (0-9)
  * Maximum length: 50 characters
* **How do I find it?**
  * From the [Roku Developer Dashboard](https://developer.roku.com/developer), click on the name of the channel you are adding to AppsFlyer. This opens the Roku Preview & Publish page for the channel.
  * The number at the end of the URL page is the Channel ID:

    ![](https://files.readme.io/89f6513eee03558a9dc8e465fe67953780074477fc0fe20675b721d8116671af-33198275490577.png)

</Accordion>

<div id="amazon-vega-os" />

<Accordion title="Amazon Vega OS">

**App name:** The name you have chosen for your app.

**App ID:** The ID of the app. Found using reverse DNS notation:  `<tld>`.`<company_name>`.`<app_name>`  
Must contain a minimum of 2 segments. Each segment must start with a letter followed by characters from: `A-Z` `a-z` `0-9.``-`  

Example: com.company.my\_app

For more information, see the “id” field in the [Amazon Vega OS documentation](https://developer.amazon.com/docs/vega/0.21/manifest-package.html#fields).

</Accordion>

<div id="vizio-smartcast" />

<Accordion title="Vizio SmartCast">

**App name:** The name you have chosen for your app.

**App ID:** The ID of the app, as recognized by Vizio. Starts with `vizio.`, followed by 2-10 characters from: `A-Z` `a-z` `0-9.``-`. If you need to confirm the app ID, check with your Vizio representative.

</Accordion>

<div id="samsung-tizen" />

<Accordion title="Samsung Tizen">

**App name:** The name you have chosen for your app.

**App ID:** The Bundle ID assigned to your app by Samsung. Starts with the letter `G`, followed by 8-15 digits. To get the App ID:

1. Sign in to the Samsung TV Seller Office Using [this link](https://developer.samsung.com/tv-seller-office/guides/overview.html).

   1. Enter your developer URL
2. Your Bundle ID is automatically generated and displayed. This can be used to access the app store URL.
3. For any issues, open an issue board ticket in the seller office.

Note: To access your unique app store web page, add the bundle ID to the URL "[https://www.samsung.com/us/appstore/app/](https://www.samsung.com/us/appstore/app/)".

For example, if your bundle ID is "G15147002586", the URL of your page will be "[https://www.samsung.com/us/appstore/app/G15147002586/](https://www.samsung.com/us/appstore/app/G15147002586/) ". The developer URL, bundle ID, and app store ID are then displayed in the metadata on that page.

![](https://files.readme.io/ee4b192abab24e064013a4a034bda38fb3ed49497ae333e327e1b78dd05d5349-33198275491729.png)

</Accordion>

<div id="lg-webos" />

<Accordion title="LG WebOS">

**App name:** The name you have chosen for your app.

**App ID:** The LG WebOS app ID.

* **Format:**
  * Maximum length of 50 characters
  * Characters from `A-Z` `a-z._` in bundle-like format. Must start with letters.
* **Example:** com.my-company.app

If you need to confirm the app ID, check with your LB WebOS representative.

</Accordion>

<div id="playstation" />

<Accordion title="PlayStation">

**App name:** The name you have chosen for your app.

**App ID:** The PlayStation concept ID, a unique identifier assigned to a game or other content concepts. It appears as a 5-9 digit number in the PlayStation store URL. You can find it at the end of the app store URL of your app:

![playstation_app_id_url.png](https://files.readme.io/df92705244e55e7adc44a88076556609983ec3dff89c03df77e19f0f1a061bbb-33198323434513.png)

</Accordion>

<div id="vidaa" />

<Accordion title="Vidaa">

**App name:** The name you have chosen for your app.

**App ID:** The Vidaa app ID. Maximum length of 50 characters.

</Accordion>

<div id="steam" />

<Accordion title="Steam">

**App name:** The name you have chosen for your app.

**App ID:** The Steam app ID. This is the 5-8 digit number that appears in the Steam store URL:

![steam_store_app_url.png](https://files.readme.io/4976c0323eab0c08b61d4a1a7a75ebf7ea9fcd819176ff574421f0de4d8c614c-33198275497617.png)

</Accordion>

<div id="meta-quest" />

<Accordion title="Meta Quest (Oculus)">

**App name:** The name you have chosen for your app.

**App ID:** The Meta Quest app ID, as it appears at the end of the Meta app store URL from which the app is downloaded. Includes 3-50 characters from: `A-Z` `a-z0-9._-`.

![](https://files.readme.io/1938b3f89b866ebdd3452367d7410c423ce57372544a801ca3d1b409f3bff541-33198323442449.png)

</Accordion>

<div id="nintendo-switch" />

<Accordion title="Nintendo Switch">

**App name:** The name you have chosen for your app.

**App ID:** The Nintendo Switch app ID, as it appears at the end of the URL of the store from which the app is downloaded. Includes 14 digits.

* **Example:** 70010000012345

</Accordion>

<div id="xbox" />

<Accordion title="Xbox">

**App name:** The name you have chosen for your app.

**App ID:** The Xbox app ID, as it appears at the end of the Xbox store URL from which the app is downloaded. Includes 12 letters and digits only (`A-Z` `a-z0-9`).

![](https://files.readme.io/c33ffcb35d4488b9340cfa8b475097eab7b79bfeaf94e8cf8ce6478dda07d341-33198275505041.png)

**Note:** App ID is case-sensitive.

</Accordion>

<div id="epic-games" />

<Accordion title="Epic Games">

**App name:** The name you have chosen for your app.

**App ID:** The Epic Games app ID, as it appears in the store from which the app is downloaded. Includes 3-50 characters from: `A-Z` `a-z0-9._-`.

![](https://files.readme.io/81d1f043c8a7ef5e367a62d564f8c6241c6057445363b21286e3f72ad4210cf6-33198275508497.png)

</Accordion>

<div id="native-pc" />

<Accordion title="Native PC">

**App name:** The name you have chosen for your app.

**App ID:** The Native PC app ID. Includes 3-50 characters from: `A-Z` `a-z0-9._-`.

</Accordion>

### Enter additional information (not applicable to web apps):

![](https://files.readme.io/561aea51bbfaa733721040706cac2b9520e35cfe71027fa34d08ed7890baf00c-33198323448081.png)

#### **Select currency**

Select the currency in which this app's data will be displayed in the dashboard. Revenue and spend events are converted to this currency using the exchange rate in effect at the event time. [Learn more](/docs/app-settings#localization-currency) about an app's currency setting and its impact.

> 📘 **Important!**
>
> Use care in selecting the currency you want to use for the app. You won't be able to change it once cost and revenue have been recorded.

#### **Select timezone**

Align the timezone you select here with the timezone you set with other attribution partners (such as Meta ads and Google Ads). This ensures the closest match between the data reported in the AppsFlyer dashboard and the data you receive from these partners.

> 📘 **Note**
>
> * Once the timezone is set, it remains locked and can't be changed until the following day.
> * [Learn more](/docs/changing-app-time-zone-settings) about app timezone setting and its impact.

#### **Define app audience**

Select **Yes** or **No** to indicate whether or not your app is directed toward children or a mixed audience (both children and adults).  
If you've selected **Yes:**

1. Open and read the [guide](https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf) about implementing compliance with child-directed apps.
2. Select the box to confirm you've read the guide and will implement the controls it specifies.

> 📘 **Note**
>
> * Two weeks after adding the app, you'll get a notification asking you to confirm you've implemented privacy controls for your child-directed apps. After confirming, you'll get a confirmation message. You can always access the confirmation message from the Notification center or see the confirmation details in the [Audit log](/docs/audit-log).
> * See [frequently asked questions about child-directed apps](/docs/child-directed-apps-faq).

#### Manage your apps in bulk via API

Account admins can [manage multiple apps in bulk](https://dev.appsflyer.com/hc/reference/app-management-v2-overview) using a dedicated API that supports the main features of the UI. This includes adding and deleting apps, and updating the app settings. The API also incorporates the same error verification mechanisms.

> 📘 **Note**
>
> At this stage, adding apps and updating the app settings via API is possible for mobile apps only. Deleting apps is possible for all platforms.

### Add a debug or testing app

If your developer creates a **debug**, **sandbox**, or **testing app**, you must add the app to the dashboard. Once your developer starts testing with the app, data displays in the app’s dashboard.

> 📘 **Note**
>
> For iOS apps that haven’t been published to the App Store and don’t yet have a valid App Store ID, you can still proceed with SDK testing by adding the app using a **dummy iOS App Store ID**. This enables SDK integration and testing without needing a real App Store listing.

For developer instructions on how to create a debug app and add it to the dashboard, see:

* [Android instructions](https://dev.appsflyer.com/hc/docs/testing-android#creating-an-android-debug-app)
* [iOS instructions](https://dev.appsflyer.com/hc/docs/testing-ios#creating-an-ios-debug-app)

## About pending apps

Working with an app in pending status can be useful when you are debugging it to test the AppsFlyer SDK.

The status of the app as pending on the dashboard has no effect on data collection and measurement. Whether an app is pending or live on an app store, if users install and interact with it, install and in-app event data is recorded on the dashboard just the same.

Once your pending app goes live, AppsFlyer will detect and automatically update its status, so you don't need to add it again. [Learn more](/docs/why-is-my-app-still-pending) about pending apps and the optional procedure for manually refreshing status.

## Troubleshooting

Find solutions for some common issues:

<div id="app-wasnt-added" />

<Accordion title="App wasn't added">

If this error occurs, contact your CSM or send an email to [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<div id="app-not-in-the-store" />

<Accordion title="App not in the store">

Confirm that you have copied the store URL correctly, using the appropriate app name/ID.

</Accordion>

<div id="cant-access-marketplace" />

<Accordion title="Can't access marketplace">

This error sometimes occurs when adding an Android app from a non-US store. Follow these steps to resolve it:

1. Add the app with a status of **Pending approval/not published**, as described above.
2. Go to the AppsFlyer **App settings** page.
3. Change the **App store country** to the correct country (for example, Japan).

</Accordion>

<div id="something-went-wrong" />

<Accordion title="Something went wrong. Please try again.">

One possible reason for this error is trying to add an Android app without a country code (for apps **not** listed in the US Google Play Store). See full details for resolving this issue [above](/docs/adding-an-app-to-appsflyer#in-store).

</Accordion>

<div id="my-ios-app" />

<Accordion title="My iOS app was removed from the App Store. Why am I still seeing installs?">

This happens because users can reinstall an app via the operating system if it previously existed on their device. Even if the app is no longer available in the App Store, users can still install it, and these installs will be counted in AppsFlyer.

</Accordion>

## Other information

<div id="product-line" />

<Accordion title="Product Line">

You can add or remove apps from a Product Line. For more information on Product Lines and what they offer, [see here](/docs/product-line-group-apps-for-cross-platform-attribution).

</Accordion>

<div data-zendesk-anchors="01H8Y09SSKZS2RHM35JT16ESKM=overview 01H8Y0K9EHWH05DB5K02ASJG11=entering-the-wizard-for-adding-an-app 01H8F2TENNWXADKVZFHY9SE8JC=note 01H8ECFB7V0DCNE0ZKPZ2GCVMP=adding-an-app 01H81661SR41SQFZZ0AW6K2EDM=note-1 01H815FE64VZZS9WGJSC8VY74D=enter-app-details 01H815FE64CXEHWTV40NVYQHGJ=android-androidtv-fire 01H815FE64X0SPA71TBQ9T4ZVB=ios-tvos-macos 01H815FE64ZZA2N1XQFBRXVF41=windows-xbox 01H815FE64XZKDJW1CX5R1JE1T=web-pba 01H815FE646GWA7KJ83KTGHH05=note-2 01H815FE65R1Z06TJR0DNC8PFY=important h_01KGEPG8V7ZZ6V2EYYPES0QM77=web h_01KGPM33BA6AJSX32CTN808AXM=before-you-begin h_01KGPM3GTYJJ0ARD3R1XHVAQ8F=to-add-a-web-app h_01KGPM5TTNSECSWEAQY5VH7DTY=note-3 01H815FE65X37H40AN99EZJ940=roku h_01KDJP1G4QZHAKH13M5D3CD793=amazon-vega-os 01H815FE654W6D4FCANR1DET8A=vizio-smartcast 01H815FE65J6T610QQXWJS0CJS=samsung-tizen 01H815FE65CRW81AD1006KHGV4=lg-webos 01H815FE65ESQZ56C8B4HG9P8M=playstation 01H815FE65483DV8MD4STH3QTR=vidaa 01H815FE655PZS1H9YW95X1R53=steam 01H815FE655XP075WYRVVFKD4F=meta-quest 01H815FE65XJEVHNT45SHGWJS4=nintendo-switch 01H815FE6598PD87PNBE7MFEQ8=xbox 01H815FE658WJCB1ZCPGAD4GGS=epic-games 01H815FE652P3HCWY2PEDJJARM=native-pc 01H815FE65AWE8VKV9FYJ7N8MV=enter-additional-information-not-applicable-to-web-apps h_01HHCFD94K6PGQRED6Z6KXKRQF=select-currency 01H815FE65X7BCFKH1EEFA91GQ=important-1 h_01HHCFDE25S92GZ9TPGQW4PXHV=select-timezone h_01HMNSSBP2EFXCVW290MKW1EFV=note-4 h_01HHCFDRNFDERZZV3TT8BVXMB4=define-app-audience h_01H9MYF17VNBETQ0HS745EJ85H=note-5 h_01HR3Z81NXCAZKK26HWCN5VD9D=manage-your-apps-in-bulk-via-api h_01HR3ZJW7YD4B8WV0NW9MX6EVP=note-6 add-debug-or-testing-app=add-a-debug-or-testing-app h_01K2F8JX66F614HF8D5MWQ26P7=add-a-debug-or-testing-app ios-dummy-app-id-note=note-7 h_01K2F8JX662XEY0A47DZG6DHWQ=note-7 01H815FE65MYPABC3DTVEMA8E9=about-pending-apps 01H815FE655HS8EA4R00D0VCYD=troubleshooting 01H815FE65V2GYP0Q612512DE0=app-wasnt-added 01H815FE65A0HPTVVCT42QQA6M=app-not-in-the-store 01H815FE65EN3PBSH5BKRGNNXD=cant-access-marketplace 01H815FE65FR4ATDA4CVX2FW9N=something-went-wrong h_01JNK9HB2ZWQ78XK9B33QWHV49=my-ios-app h_01K7KSRWCB1Y89T21JFJR42VAJ=other-information h_01K7KSPDSSG8CRCQB5V545Y12Z=product-line" />

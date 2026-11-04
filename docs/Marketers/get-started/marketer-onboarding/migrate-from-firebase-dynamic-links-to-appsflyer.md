---
title: Migrate from Firebase Dynamic Links to AppsFlyer
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-06-19T09:27:37Z'
  edited_at: '2026-08-19T09:29:28Z'
  id: 16282289097105
  locale: en-us
  section: Marketer onboarding
  section_id: 6550866490129
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/16282289097105-Migrate-from-Firebase-Dynamic-Links-to-AppsFlyer
---
> **At a glance:** Migrate from Firebase Dynamic Links to AppsFlyer OneLink using our step-by-step guide.

<div id="" />

## ![53375 Firebase migration KB image.png](https://files.readme.io/b5340a5b30c160bca2b420052fd60b23f4bfe0de6d2868f91ad4342bee36c7df-30063560499345.png)

<div id="about-the-migration" />

## About the migration

Google’s <Anchor target="_blank" href="https://firebase.google.com/docs/dynamic-links">Firebase Dynamic Links</Anchor> will be deprecated on August 25, 2025. Effective on this date, all links served by Firebase Dynamic Links (both hosted on custom domains and page.link subdomains) will stop working, and new link creation will be disabled. If you use Firebase Dynamic Links, it's essential to take proactive steps as soon as possible to migrate your links elsewhere to prevent disruptions to user journeys from your campaigns.

AppsFlyer OneLink enables you to easily create links with attribution, redirection, and deep linking capabilities on owned or paid media, regardless of device, operating system, channel, or platform. Partner with AppsFlyer to create personalized, contextual user journeys that drive users to your app for maximum conversion and revenue. Follow the instructions below to get started migrating your Firebase Dynamic Links to AppsFlyer.

<div id="migrate-from-firebase-to-appsflyer" />

## Migrate from Firebase to AppsFlyer

This section describes how to migrate your Firebase dynamic links over to AppsFlyer OneLink.

**To migrate to AppsFlyer:**

**Prerequisites**

Before you begin, you'll need your:

* Dynamic Links from Firebase
* App developer

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="Step 1. Create an AppsFlyer account">

* <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Create an AppsFlyer account</Anchor>.
* <Anchor target="_blank" href="/marketers/docs/user-management">Add account users with appropriate permissions</Anchor>.

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="Step 2. Add your app">

* <Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer">Add your app</Anchor> in AppsFlyer.
* [Optional] Change the default 90-day <Anchor target="_blank" href="/marketers/docs/set-up-re-attribution-window">re-attribution window</Anchor> to align with your definition of active users.

![add](https://files.readme.io/7f7bab2277d0f45434618d28714c727ccbb9e414192b765dd22551bcbd5b0a37-16950840602769.png)

</Accordion>

<div id="step-3-create-a-onelink-template" />

<Accordion title="Step 3. Create a OneLink template (app developer collaboration)">

**You and your app developer are both needed for this step**.

A OneLink template is required for creating links and end-user experiences. It forms the basis of the redirection logic for all OneLink links you create for your various marketing campaigns.

* <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#create-a-onelink-template">Create a OneLink template</Anchor>
  * You must either be an AppsFlyer admin user or have <Anchor target="_blank" href="/marketers/docs/user-management">permissions to add/edit OneLink templates</Anchor>

</Accordion>

<div id="step-4-set-up-the-appsflyer-sdk" />

<Accordion title="Step 4. Set up the AppsFlyer SDK (app developer task)">

**Your app developer is needed for this step**.

The AppsFlyer SDK integrated into the app is the link between the app and the AppsFlyer platform. It provides:

* Deep linking -  The SDK enables unified deep linking (UDL) implementation
* Attribution - The SDK reports app installs, app opens, in-app events, and so on.

Integrate AppsFlyer SDK in your app using the steps below.

<div id="appsflyer-sdk-integration-steps" />

#### AppsFlyer SDK integration steps

1. Integrate the AppsFlyer SDK into the app.  
   See the guides for Android and iOS <Anchor target="_blank" href="/marketers/docs/sdk-integration-overview">SDK integration</Anchor>.
2. Map in-app events you want to be recorded, using the AppsFlyer schemes.  
   This can be done via <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">SDK</Anchor> or <Anchor target="_blank" href="/marketers/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Handle Firebase's SDK.  
   You can switch exclusively to AppsFlyer, or run both SDKs simultaneously for a few weeks. View a breakdown of these options in the table below.

| Option | What happens after  <br />updated app version release | Impact |
| --- | --- | --- |
| Remove Firebase's SDK (recommended) | Only AppsFlyer records new installs and updating users.  <br />Firebase still shows events performed by users, until the users update their app too. | <ul><li>Fast transition</li><li>No double attribution</li><li>Allows you to see if you have any lingering app versions with the Firebase SDK still on them</li></ul> |
| Keep Firebase's SDK for a transition period | AppsFlyer and Firebase attribute new installs and report events. At a later date, remove the Firebase SDK. | <ul><li>Data validation is possible. Meaning, you can compare data from AppsFlyer and Firebase</li><li>Double attribution, which may cause double charges with ad networks</li><li>Higher workload</li></ul> |

4. After all other tasks in the scope of work are completed, update the app version with AppsFlyer SDK to the market. New users are attributed by AppsFlyer.   
   **Note**:
   * Make sure to update the app for iOS, Google Play, and any relevant Android out-of-store markets.
   * Your Android app may exist on unofficial APK sites, even if you don't know it (search the web for your app's package name to find out). APK sites take some time to update to the latest version, so they may bring organic users, which install old versions without AppsFlyer SDK.
   * App update rollouts in the app stores can take a couple of days to fully complete. Users installing during this phase may still get the previous version.

</Accordion>

<div id="step-5-understand-parameter-mapping" />

<Accordion title="Step 5. Understand parameter mapping (app developer task)">

**Your app developer is needed for this step**.

Understand how Firebase Dynamic Links parameters map to AppsFlyer's corresponding parameters.

Correct mapping and understanding of the corresponding parameters will ensure your links get the same results.

The table below lists all of Firebase's parameters and the corresponding AppsFlyer parameters.

Use this table as a reference for all the parameters you currently use when you migrate to AppsFlyer.

<div id="note" />

> 📘 **Note**
>
> If a Firebase parameter isn't listed, it is because AppsFlyer covers this in the OneLink template setup without you needing to put a parameter in your links.

<table><thead><tr><th>Grouping</th><th>Firebase</th><th>AppsFlyer</th><th>Description</th></tr></thead><tbody><tr><td>Mobile parameters</td><td>link</td><td><ul><li>af_dp</li><li>deep_link_value</li></ul></td><td><ul><li><strong>af_dp</strong> - URI scheme used as a fallback method to launch iOS and Android apps.</li><li><strong>deep_link_value</strong> - Value name for the specific in-app content that users will be directed to.</li></ul></td></tr><tr><td><br/>Android parameters</td><td>afl</td><td>af_android_url</td><td>Allows redirection of Android users to a customized web page (the domain must be in the <a href="./set-up-your-domain-redirect-allowlist" target="_blank">redirect allowlist</a>)</td></tr><tr><td rowspan="2">iOS parameters<br/><br/> </td><td>ifl</td><td>af_ios_url</td><td>Allows redirection of iOS users to a customized web page (the domain must be in the <a href="./set-up-your-domain-redirect-allowlist" target="_blank">redirect allowlist</a>)</td></tr><tr><td>efr</td><td>af_force_deeplink</td><td>Used to force an iOS app to open using the af_dp URI scheme. Without this, the app won't open using the URI scheme</td></tr><tr><td>Other platform URL</td><td>ofl</td><td>af_web_dp</td><td>Allows redirection of desktop users to a customized web page</td></tr><tr><td rowspan="3"><br/>Social tags<br/><br/> </td><td>st</td><td>af_og_title</td><td>Used to customize the title of shared content on Social media</td></tr><tr><td>sd</td><td>af_og_description</td><td>Used to customize the description of shared content on social media</td></tr><tr><td>si</td><td>af_og_image</td><td>Used to customize the image of shared content on social media</td></tr><tr><td rowspan="5"><p>Analytic parameters <br/><br/><br/><br/> </p></td><td>utm_source</td><td>pid</td><td>Media Source</td></tr><tr><td>utm_medium</td><td>af_channel</td><td>Identifies the media source channels where your ads are distributed</td></tr><tr><td>utm_campaign</td><td>c</td><td>Campaign name</td></tr><tr><td>utm_term</td><td>af_keywords</td><td>Keywords list for text-targeted campaigns</td></tr><tr><td>utm_content</td><td>af_adset</td><td>Collection of ads associated with a campaign</td></tr></tbody></table>

</Accordion>

<div id="step-6-create-onelink-links-with-mapped-parameters" />

<Accordion title="Step 6. Create OneLink links with mapped parameters">

Using your mapped parameters, you can create OneLink links from your OneLink template.

Links can be created <Anchor target="_blank" href="/marketers/docs/perform-onelink-bulk-actions-via-csv">in bulk</Anchor> via CSV file, programmatically with the <Anchor target="_blank" href="/marketers/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor>, individually using the <Anchor target="_blank" href="/marketers/docs/onelink-guide">AppsFlyer dashboard</Anchor>, in the <Anchor target="_blank" href="/marketers/docs/user-invite-attribution">SDK</Anchor>, or as manually constructed <Anchor target="_blank" href="/marketers/docs/understand-onelink-short-vs-long-urls">long links</Anchor>.

Use the following table to determine which method best works for your use.

| Firebase | AppsFlyer | Use it if | Notes |
| --- | --- | --- | --- |
| Firebase console | <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink Management page</Anchor> | You would like to create OneLink links one by one. In this way, you can utilize the full OneLink features and possibilities |  |
| Dynamic Link Builder API | <Anchor target="_blank" href="/marketers/docs/user-invite-attribution">SDK</Anchor> | You would like to create in-app programmatically generated links for uses such as user invites and referrals | <ul><li>Requires iOS or Android developer</li></ul> |
| Firebase REST API | <Anchor target="_blank" href="/marketers/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> | You would like to create links programmatically outside the mobile app | <ul><li>Requires a developer</li><li>Not available on the free plan</li></ul> |
| Manual link construction | <Anchor target="_blank" href="/marketers/docs/understand-onelink-short-vs-long-urls">Long links</Anchor> | You would like to manually construct the link with its query parameters. Use if you don't require short links For example if the link will be behind a button or a banner |  |
|  | <Anchor target="_blank" href="/marketers/docs/perform-onelink-bulk-actions-via-csv">Bulk Links</Anchor> | You would like to migrate all your Firebase dynamic links in bulk to AppsFlyer.<br /><br />This is recommended to quickly move over all your links without any errors | <ul><li>Requires a pre-step of [mapping the link parameter keys and values according to the corresponding Firebase parameters](/docs/migrate-from-firebase-dynamic-links-to-appsflyer#map-parameters)</li><li>Not available on the free plan.</li></ul> |
|  | <Anchor target="_blank" href="/marketers/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner</Anchor> | you would like to create banners on mobile websites that deep link to your app |  |
|  | <Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors">Smart Script</Anchor> | If you would like to construct a long link dynamically in a web page for a web-to-app experience |  |

</Accordion>

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/brand-onelink-with-your-domain">Branded Domains</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/using-firebase-and-google-tag-manager-with-appsflyer-overview">Using Firebase and Google Tag Manager with AppsFlyer—Overview</Anchor>

<div data-zendesk-anchors="overview=about-the-migration h_01J7ZPPQ340PNQ70FZAQY4GBZ1=about-the-migration 01H8K961JHRXNQHBVN930XW70Q=about-the-migration how-to-migrate-from-firebase-to-appsflyer=migrate-from-firebase-to-appsflyer 01H8K961JHCK0Z4GTTHCAKF98E=migrate-from-firebase-to-appsflyer h_01J5QWWGWGDBEF8RY3DZ5XAN3G=step-1-create-an-appsflyer-account h_01J5QWWGWGN17673GYFZWPNKQR=step-2-add-your-app h_01J5QWWGWGKJPRCG9N93B8KBYW=step-3-create-a-onelink-template h_01J5QWWGWGCQFHBQ9EC0QTPF4S=step-4-set-up-the-appsflyer-sdk h_01J5QXST2K890DV7QS6S9K3A01=appsflyer-sdk-integration-steps h_01J5QWWGWGPRF5DRMMQ14BJCFA=step-5-understand-parameter-mapping 01H8K961JHBXVKXM0XQYY605EQ=note h_01J5QWWGWG3ST19WDRZXN8FK8Q=step-6-create-onelink-links-with-mapped-parameters h_01HE7SZPKKQETH260G45V0D0HN=see-also" />

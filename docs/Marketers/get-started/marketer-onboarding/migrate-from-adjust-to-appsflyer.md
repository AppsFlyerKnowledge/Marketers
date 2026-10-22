---
title: Migrate from Adjust to AppsFlyer
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
  created_at: '2024-12-02T10:01:48Z'
  edited_at: '2024-12-05T10:13:18Z'
  id: 30563700129297
  locale: en-us
  section: Marketer onboarding
  section_id: 6550866490129
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/30563700129297-Migrate-from-Adjust-to-AppsFlyer
---
> **At a glance:** Plan your migration from Adjust to AppsFlyer. Understand how to avoid double charges, data duplication, and data loss during the migration period.

<Image alt="" src="https://files.readme.io/cc012894dd05255c0b7fa448b1c95d925d556ddb43dc461086bb71e9279da90d-30633481029137.png" width="1765px" />

## About migrating to AppsFlyer

Migrating from Adjust to AppsFlyer provides a smooth transition to a reliable and comprehensive platform for attribution and marketing analytics. AppsFlyer offers secure and unbiased solutions alongside a suite of advanced tools designed to help brands navigate changes in the industry. With global customer support and a focus on continuous product improvement, AppsFlyer aims to equip businesses with the tools and insights needed to grow and adapt.

#### Compare measurement between AppsFlyer and Adjust

When considering migration, you might want to compare AppsFlyer and Adjust attribution measurements across the same media sources and campaigns. However, not all media sources support measurement with more than one MMP. Those that do may have certain limitations and challenges to prevent attribution discrepancies. See more about <Anchor target="_blank" href="/marketers/docs/measuring-attribution-with-multiple-mmps">Measuring attribution with multiple MMPs</Anchor>.

## Tasks

[![](https://files.readme.io/7deffffc032dce24c30b5b73ae09c083a227ac6f4ec13be224bb7f7fb5b7042f-30642410251793.png)](https://files.readme.io/7deffffc032dce24c30b5b73ae09c083a227ac6f4ec13be224bb7f7fb5b7042f-30642410251793.png) The following table describes the main steps needed for migration. To see a precise breakdown of the general tasks, as well as to record your progress, download <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQqbJIkE7kD87uSm7MH7zfkPN1VLuBaeotTEHAID2pYFVWM_LuQIA2AE2-8fVnXH-DrbXUQCs2iaiDe/pub?output=xlsx">this spreadsheet</Anchor>.

You can work on these tasks simultaneously, meaning the marketers, developers, and data engineers can, for the most part, work on their assigned tasks concurrently. Note that we recommend you:

* Complete all of the tasks before releasing your updated app with the AppsFlyer SDK.
* Pause existing marketing campaigns before performing the device ID migration.

<table><thead><tr><th>Step</th><th>Who's involved</th><th>Estimated time</th><th>Remarks</th></tr></thead><tbody><tr><td>1. Create an AppsFlyer account</td><td>Marketer/AppsFlyer dashboard user</td><td>2 hours</td><td> </td></tr><tr><td>2. Add the app in AppsFlyer</td><td>Marketer/AppsFlyer dashboard user</td><td>2 hours</td><td> </td></tr><tr><td>3. Integrate the SDK</td><td>App developers</td><td>1 day + 1 week of testing and iterating</td><td><ul><li><strong>Recommended</strong>: Integrate the AppsFlyer SDK in a pre-production app for testing.</li><li>Production app must be updated in app stores after all other tasks are completed.</li></ul></td></tr><tr><td>4. Migrate devices (optional)</td><td>Data engineer</td><td>1-2 weeks</td><td rowspan="2"><ul><li>Consider pausing existing campaigns before migration, and resuming them after app version is updated. </li><li>Consider repeating device migration on the final migration date to ensure complete coverage. </li></ul></td></tr><tr><td>5. Migrate campaigns</td><td>Marketer/UA manager</td><td>1-3 days for each media source</td></tr><tr><td>6. Set up data reporting</td><td>Data engineer</td><td>3-6 weeks</td><td> </td></tr></tbody></table>

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="Step 1. Create an AppsFlyer account">

**To create an AppsFlyer account**:

1. <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Create an AppsFlyer account</Anchor>.
2. <Anchor target="_blank" href="/marketers/docs/user-management">Add account users with appropriate permissions</Anchor>.

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="Step 2. Add your app">

**To add your app in AppsFlyer**:

1. <Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer">Add your app</Anchor> in AppsFlyer.
2. [Optional] Change the default 90-day <Anchor target="_blank" href="/marketers/docs/set-up-re-attribution-window">re-attribution window</Anchor> to align with your definition of active users.
3. As part of the app onboarding wizard in AppsFlyer, prepare and send an email to your developer with instructions and tasks for SDK integration and in-app event mapping.

</Accordion>

<div id="step-3-integrate-the-sdk" />

<Accordion title="Step 3. Integrate the SDK">

The AppsFlyer SDK integrated into the app is the link between the app and the AppsFlyer platform. It reports app installs, app opens, in-app events, and so on.

**To integrate the AppsFlyer SDK**:

1. Receive the email from the marketer with instructions and tasks for SDK integration and in-app event mapping.
2. Follow those email instructions and use the <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?sourceos=android&utm_source=kb&utm_medium=sdk-int-wizard-orvw">AppsFlyer SDK integration wizard</Anchor> to integrate the AppsFlyer SDK into the app.
   * The wizard takes the developer from installation to successful testing of the integration. It also guides the developer in defining in-app events and successfully testing their transmission to AppsFlyer. <Anchor target="_blank" href="/marketers/docs/for-ios-and-android-the-sdk-integration-wizard">Learn more about the SDK integration wizard</Anchor>
   * See additional developer guides for <Anchor target="_blank" href="/marketers/docs/sdk-integration-overview">Android</Anchor> and <Anchor target="_blank" href="/marketers/docs/sdk-integration-overview">iOS</Anchor> SDK integration.
   * Map in-app events you want to be recorded, using the AppsFlyer schemes.  
     This can be done via <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">SDK</Anchor> or <Anchor target="_blank" href="/marketers/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Remove the Adjust SDK.  
   You can do this immediately and switch exclusively to AppsFlyer, or run both SDKs simultaneously for a while. View a breakdown of these options in the table below.

| Option | What happens after  <br />updated app version release | Impact |
| --- | --- | --- |
| Remove the Adjust SDK (recommended) | Only AppsFlyer records new installs and updating users.  <br />Adjust still shows events performed by users, until the users update their app too. | <ul><li>Fast transition.</li><li>No double attribution.</li></ul> |
| Keep the Adjust SDK for a transition period | AppsFlyer and Adjust attribute new installs and report events. At a later date, remove the Adjust SDK. | <ul><li>Data validation is possible. Meaning, you can compare data from AppsFlyer and Adjust.</li><li>Double attribution, which may cause double charges with ad networks. See example below.</li><li>Higher workload.</li></ul> |

4. After all other tasks in this migration article are completed, release the app version with the AppsFlyer SDK to the market. New users are attributed by AppsFlyer.   
   **Note**:
   * Make sure to update the app for iOS, Google Play, and any relevant Android out-of-store markets.
   * Your Android app may exist in unofficial APK sites, even if you don't know it (search the web for your app's package name to find out). APK sites take some time to update to the latest version, so they may bring organic users, which install old versions without AppsFlyer SDK.
   * App update rollouts in the app stores can take a couple of days to fully complete. Users installing during this phase may still get the previous version.

</Accordion>

<div id="step-4-migrate-devices-optional" />

<Accordion title="Step 4. Migrate devices — optional">

Device migration is the process of uploading a list of your existing user device IDs (IDFA, IDFV, GAID) into AppsFlyer. (If you don't have all the device IDs needed, you can contact your CSM to help guide you through the migration process using CUID.) You should perform this process before releasing the new app version, which will include the AppsFlyer SDK. There are two options when migrating devices, [attributed](/docs/migrate-from-adjust-to-appsflyer#attributed-migration) or [non-attributed migration](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration).

Device migration solves data issues associated with existing app users who downloaded the app, and were attributed by Adjust. For example, SRN double charges, which occur when users originally attributed to an SRN under Adjust, and who are still within the lookback window, are claimed by the SRN again under AppsFlyer.

> 📄 **Example**
>
> * A new user clicks on an ad on the Facebook app and installs your app on June 15.
> * On June 24 the user updates the app to the version with the AppsFlyer SDK, and launches. For AppsFlyer, this is a new user, that needs to be attributed in real time.
> * AppsFlyer queries Meta ads with the user device ID. Because the user is still within the Meta ads 28-day lookback window, Meta ads self-attributes the user. This causes a double charge to the app owner for the same user.

Once you migrate devices, data reflects in AppsFlyer as follows:

* **Installs** **data:** Similar to <Anchor target="_blank" href="/marketers/docs/set-up-re-attribution-window#reinstall">re-installs</Anchor>, migrated devices have no install data. Migrated device installs are not displayed in AppsFlyer.
* **In-app events and sessions data:** Recorded and displayed as organic for [non-attributed device migration method](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration), or attributed to the media source and campaign, if using the [attributed method](/docs/migrate-from-adjust-to-appsflyer#attributed-migration).
* **Retargeting:** Re-attributions and re-engagements are displayed normally.
* **Activity data:** Displayed normally.
* **Retention and cohort data:** Migrated devices have no install record. As such, they aren't associated with any cohort, and can't be shown in the cohort and retention reports.

> 📘 **Note**
>
> If the app is not opened within 180 days from the migration date, all of the migrated device data is deleted. Consequently, if the app is opened after the 180-day period, a new install will be recorded.

**To migrate devices:**

1. Decide which user population to migrate. You can migrate all existing users (which may prevent you from getting accurate re-attribution data from AppsFlyer), or users that only recently installed your app (which may lead to double charges of somewhat older users).  
   **We recommend migrating users who are active during your current re-attribution window period.** For example, if your app has a 90-day re-attribution window, migrate those users who have at least one session during the previous 90 days.
2. [Optional] Tell the marketer/UA manager to pause existing marketing campaigns (from SRNs, non-SRN ad networks, owned media, etc.) until after the device migration.  
   If you decide not to pause campaigns, migrate any remaining device IDs from the other vendor as soon as the updated app version with the AppsFlyer SDK is released to app stores.
3. Prepare a CSV file based on the user population selected, using either the [attributed](/docs/migrate-from-adjust-to-appsflyer#attributed-migration) or [non-attributed](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration) migration structure. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">See sample CSV</Anchor>
4. Send your AppsFlyer CSM the CSV.  
   Your CSM will migrate the device IDs to AppsFlyer.

</Accordion>

<div id="step-5-migrate-campaigns" />

<Accordion title="Step 5. Migrate campaigns">

Switch existing marketing campaigns to AppsFlyer to enable AppsFlyer attribution, and avoid duplicate charges and the loss of attribution data.

**Note**: You can choose to only migrate a few marketing campaigns at a time. In this case, you can segment the ones you want to migrate by media source (for example, ad network or agency), geo, or campaign.

The following sections explain what is needed to enable AppsFlyer measurement for different types of media sources: SRNs, non-SRN ad networks, owned media, and SKAN.

#### SRNs

SRNs reply to Mobile Measurement Partners (MMPs) when queried about engagements of specific devices. If AppsFlyer and Adjust query the same SRN about the same device install, you may incur double charges.

**To migrate SRN campaigns**:

* Activate and configure relevant <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns#srns-integrated-with-appsflyer">SRNs</Anchor> in AppsFlyer.

> 📘 **Note**
>
> * SRNs can run multiple MMPs (except Meta ads and Twitter).
> * Meta ads cannot de-duplicate in-app events.

#### Non-SRN ad networks

Ad network attribution links record the engagements of users and are subsequently used to attribute the engagements that become actual installs.

**To migrate non-SRN ad network campaigns**:

1. <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">Activate</Anchor> the relevant ad networks in AppsFlyer.
2. <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">Generate AppsFlyer attribution links</Anchor> for each ad network.
3. Switch the existing links in each of your campaigns with the AppsFlyer attribution links.

#### Owned media

Owned media refers to attribution links you use in:

* Content sharing
* Web-to-app
* Email
* SMS
* Social media posts
* Blogs
* Internet communities (Quora, etc.)
* and more...

For these campaigns, AppsFlyer uses <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink links</Anchor>. OneLink links redirect users based on their device to the correct app store, directly into the app, or to a web URL/landing page.

**To change your Adjust links into AppsFlyer OneLink links**:

* Contact your CSM, who will assist you with transforming your owned media links to into OneLink links according to the channels and tools you currently use.

#### SKAN

For SKAdNetwork (SKAN) attribution, you can only have one SDK update the conversion value. Otherwise, SKAN data is rendered meaningless. Therefore, make sure that after migration, only the AppsFlyer SDK updates the SKAN conversion value.

<Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">Learn about setting up the SKAN conversion value in AppsFlyer.</Anchor>

</Accordion>

<div id="step-6-set-up-data-reporting" />

<Accordion title="Step 6. Set up data reporting">

You can get <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-apis">raw</Anchor> and <Anchor target="_blank" href="/marketers/docs/analytics-and-aggregate-reporting-apis">aggregate</Anchor> report data from AppsFlyer using a number of methods. Familiarize yourself with the methods and set up the ones that are relevant to you.

Reporting methods include:

* Dashboards
* Export reports
* Push API
* Pull API
* Data Locker

Before migration, your systems store your attribution data from Adjust according to the reporting structures, fields, and parameters you have set up with them. For AppsFlyer to correctly report data, you must adapt and map your current report structures to AppsFlyer report structure, fields, and parameters.

**To adapt/map your report structures:**

* Contact your AppsFlyer CSM for help in quickly adapting/migrating your report data structures from Adjust to AppsFlyer.

</Accordion>

## Additional information

<div id="attributed-migration" />

<Accordion title="Attributed migration">

Devices migrated to AppsFlyer with this method have their in-app events, and sessions recorded and displayed according to the media source reported by the previous attribution vendor, and according to the ad networks' data retention policies.

#### Attributed device migration CSV structure

| Column  <br />name | Description | Mand-atory | Examples |
| --- | --- | --- | --- |
| app\_id | App ID as it appears in AppsFlyer dashboard | Yes | <ul><li>Android: com.great.app1</li><li>iOS: id123456789</li></ul> |
| platform | Device platform: ios or android | Yes | <ul><li>ios</li><li>android</li></ul> |
| device\_id | <ul><li>Android: gaid or android\_id</li><li>iOS: IDFV (recommended, if available) or IDFA</li><li>Do not duplicate the same combination of device ID and app ID in multiple rows. If duplication occurs, the last occurrence in the file is used.</li></ul> | Yes | <ul><li>**gaid** (lower case): 9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**android\_id** (lower case): f35aea8908254891</li><li>**IDFV** (upper case): A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA** (upper case): 9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android: advertiserId (also supports amazon\_aid)j, android\_id</li><li>iOS:idfa or idfv</li><li>Currently, other identifiers, OAID, IMEI are not supported.<br />Use non-attributed migration for Android users, which are not from Google Play.</li></ul> | Yes | <ul><li>advertiserId</li><li>android\_id</li><li>idfa</li><li>idfv</li></ul> |
| install\_time | The original app install time with the <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor> UTC format:  <br />**yyyy-mm-ddTHH:MM:SS.SSS** | No | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>Either:<ul><li>AppsFlyer partner ID</li><li>Custom media source (cannot be a partner ID).</li></ul></li><li>To get the list of partner IDs as required by AppsFlyer:<ul><li><Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">Enable all relevant integrated partners.</Anchor></li><li>Run the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">Get active integrations API</Anchor> for a list of all active integrations.</li><li>Use the **media\_source\_name** from the API as the **media\_source** value in the CSV.</li><li>Exceptions:<ul><li>For Apple Search Ads use **Apple Search Ads**.</li><li>For Twitter, use **twitter**.</li></ul></li></ul></li><li>Format: Values are case-sensitive</li></ul> | Yes | Non-organic: facebook\_int, googleadwords\_int<br /><br />Organic: organic |
| integrated\_partner | <ul><li>Indicates whether the media source is an integrated partner or not. Meaning organic or custom media source.</li><li>Format: Values are case sensitive</li></ul> | Yes | <ul><li>yes</li><li>no (if media\_source is custom)</li></ul> |
| campaign | For more granular attribution details, supply the original campaign name.<br /><br />Format: String | No |  |
| campaign\_id | For more granular attribution details, supply the original campaign id.<br /><br />Format: String no spaces permitted | No |  |

**CSV file rules:**

* CSV file can contain user devices from multiple apps.
* Do not duplicate the same combination of device ID and app ID in multiple rows. If duplication occurs, the last occurrence in the file is used.
* All column headers must be included: app\_id, platform, device\_id, id\_type, install\_time, media\_source, integrated\_partner, campaign, campaign\_id. **Note**: The order of the fields is important and must be maintained.
* You can add both IDFV and IDFA for the same device, but they must be in separate rows. All fields in the separate rows should be the same, except device\_id.
* Each row must contain exactly 9 fields separated by commas.
* Leave non-mandatory fields empty (blank).
* Files can contain up to 5 million rows.
* If you have multiple files, give each file a unique name.
* Encode data using UTF-8.
* [Optional] Compress files using ZIP or GZIP.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=0&single=true&output=csv">See sample CSV</Anchor>

</Accordion>

<div id="nonattributed-migration" />

<Accordion title="Non-attributed migration">

Devices migrated to AppsFlyer with this method are recorded (but do not display) as organic users. Their in-app events and sessions are also recorded and displayed as organic.

#### Non-attributed device migration CSV file structure

| Option | Columns | When to use | Example |
| --- | --- | --- | --- |
| 1 | App ID + IDFA/GAID/IDFV | <ul><li>If all your Android users have GAID identifiers.</li><li>iOS only users</li></ul> | [![device_migration_file_option_1.png](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png)](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png) |
| 2 | App ID + Device ID + Device ID type | <ul><li>If some of your Android users have only IMEI or Android ID, but not GAID (out-of-store markets, Android versions below 4.4.2).</li><li>Android ID needs to have a hexadecimal format.</li></ul>**Note**:<ul><li>Use the exact strings for the **ID type** column: advertiserId (also supports amazon\_aid), idfa, idfv, android\_id, imei.</li><li>If you use android\_id or imei, and later AppsFlyer receives a better identifier, a new attribution may be recorded.</li></ul> | [![device_migration_file_option_2.png](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png)](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png) |

**CSV file rules:**

* CSV file can contain user devices from multiple apps.
* Each row contains a single device ID per app.
* Depending on the file structure option you choose, file columns must be as follows (and in the order listed):
  * Option 1: app\_id,device\_id
  * Option 2: app\_id,device\_id,id\_type
* App IDs in lowercase.
* Android identifiers in lowercase.
* IDFA/IDFV in uppercase.
* Up to 25 million rows permitted.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">See sample CSV</Anchor>

</Accordion>

<div data-zendesk-anchors="overview=about-migrating-to-appsflyer 01H8EDSTP8N4GZJQ5J609C3DHM=about-migrating-to-appsflyer h_01HQJ10ZFJR43KBYMD9A07CJ99=compare-measurement-between-appsflyer-and-adjust 01H8EDSTP8YGDZBPEY1976JP8C=tasks 01JE3EC4C847ZEK769Y9G237KG=step-1-create-an-appsflyer-account 01JE3EC4C9V83D0V46EJK49JZ2=step-2-add-your-app 01JE3EC4CAKY4FQBPPZSJFP5V5=step-3-integrate-the-sdk step-4-migrate-devices%E2%80%94optional=step-4-migrate-devices-optional 01JE3EC4CPT4KAER27C8C0DHH7=step-4-migrate-devices-optional 01H8EDSTP93QJA4XZB6TDWWH1V=example 01JA2CAMW3HCHC4B9FX7517FJ6=note 01JE3EJ5DVXF1VT28ZCGR7SMF3=step-5-migrate-campaigns 01JE3EXVNRMA2MFVPSJZ2RMR09=srns 01H8EDSTP9ZGMHSM44BWGF1FJN=note-1 nonsrn-ad-networks=non-srn-ad-networks 01JE3EXVNTWK4ZJS55WXHFKSMX=non-srn-ad-networks 01JE3EXVNTS4FVXN370G1CR8Z9=owned-media 01JE3EXVP4TSMGSZD4B460RSQA=skan 01JE3F6VXDG9MDCVWN81RSHXVG=step-6-set-up-data-reporting 01JE3E5VHV2WCFWABC9FYQW3VG=additional-information 01JE3FG6K95QT60C36R88WGDG4=attributed-migration 01H8EDSTP9HABKEZJXMB84CDDE=attributed-device-migration-csv-structure 01JE3FG6MKNJMTHSR5B2ZMQP1K=nonattributed-migration nonattributed-device-migration-csv-file-structure=non-attributed-device-migration-csv-file-structure 01H8EDSTP9AFDMQS6BPQJY19ZH=non-attributed-device-migration-csv-file-structure" />

---
title: Migration to AppsFlyer from other vendors
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2019-07-01T13:11:37Z'
  edited_at: '2026-06-16T12:04:07Z'
  id: 360001923697
  locale: en-us
  section: Marketer onboarding
  section_id: 6550866490129
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360001923697-Migration-to-AppsFlyer-from-other-vendors
---
> **At a glance:** Plan your migration to AppsFlyer from another attribution vendor. Understand how to avoid double charges, data duplication, and data loss during the migration period.

![migration flow](https://files.readme.io/31d67493ae3ae6912b4da3163ebb731a8d58494c3007ef1d08cb7332226d9e81-360017326677.png)

## About migrating to AppsFlyer from other vendors

Migrating to AppsFlyer from another vendor includes the following main tasks:

* [SDK integration](/docs/migration-to-appsflyer-from-other-vendors#sdk-integration)
* [Device migration](/docs/migration-to-appsflyer-from-other-vendors#device-migrationoptional)
* [Campaign migration](/docs/migration-to-appsflyer-from-other-vendors#campaign-migration)
* [Data report setup](/docs/migration-to-appsflyer-from-other-vendors#data-report-setup)

You can work on these tasks simultaneously. However, we recommend that you:

* Complete all of the tasks before releasing your updated app with the AppsFlyer SDK.
* Pause existing marketing campaigns before performing the device ID migration.

### Compare measurement between AppsFlyer and other MMPs

When considering migrating to AppsFlyer from another MMP, advertisers might want to compare both MMP attribution measurements across the same media sources and campaigns. However, not all media sources support measurement with more than one MMP. Those that do, may come with certain limitations and challenges to prevent attribution discrepancies. See more about <Anchor target="_blank" href="/marketers/docs/measuring-attribution-with-multiple-mmps">Measuring attribution with multiple MMPs</Anchor>.

## Tasks

The following table describes the scope of work required for each task. To see a precise breakdown of the general tasks, as well as to record your progress, download <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQqbJIkE7kD87uSm7MH7zfkPN1VLuBaeotTEHAID2pYFVWM_LuQIA2AE2-8fVnXH-DrbXUQCs2iaiDe/pub?output=xlsx">this spreadsheet</Anchor>

#### Scope of work

<table><thead><tr><th>Task</th><th>Action required</th><th>Who's involved</th><th>Estimated time</th><th>Remarks</th></tr></thead><tbody><tr><td>Prerequisites</td><td><ol><li><a href="https://www.appsflyer.com/get-started" target="_blank">Create an AppsFlyer account</a>.</li><li><a href="./adding-an-app-to-appsflyer" target="_blank">Add the app</a> in AppsFlyer.</li><li>[Optional] Change the default 90-day <a href="./set-up-re-attribution-window" target="_blank">re-attribution window</a> to align <span>with your definition of active users.</span></li></ol></td><td>Marketer/AppsFlyer dashboard user</td><td>2 hours</td><td> </td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#sdk-integration">SDK integration</a></td><td><ul><li>Integrate AppsFlyer SDK in your app.</li><li>Map S2S or SDK in-app events.</li><li>Update app version in app stores.</li></ul></td><td>App developers</td><td>1-2 weeks</td><td><ul><li><strong>Recommended</strong>: Integrate the AppsFlyer SDK in a pre-production app for testing.</li><li>Production app must be updated in app stores after all other tasks are completed.</li></ul></td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#device-migrationoptional">Device migration</a> [optional]</td><td>Migrate device IDs to avoid double attribution of your existing users.</td><td>Data engineer</td><td>1-2 weeks</td><td rowspan="2"><ul><li>Consider pausing existing campaigns before migration, and resuming them after app version is updated.</li><li>Consider repeating device migration on the final migration date to ensure complete coverage. </li></ul></td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#campaign-migration">Campaign migration</a></td><td><ul><li>Integrate your ad networks in AppsFlyer</li><li>Migrate existing campaigns from:<ul><li>SRNs</li><li>Non-SRN ad networks</li><li>Owned media</li></ul></li></ul></td><td>Marketer/UA manager</td><td>1-3 weeks</td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#data-report-setup">Data report setup</a></td><td><ul><li>Adapt/map your current report structures to AppsFlyer structures.</li><li>Prepare to receive AppsFlyer reports.</li></ul></td><td>Data engineer</td><td>2-4 weeks</td><td> </td></tr></tbody></table>

### SDK integration

<div id="sdk-integration::c763138b" />

<Accordion title="SDK integration">

The AppsFlyer SDK integrated into the app is the link between the app and the AppsFlyer platform. It reports app installs, app opens, in-app events, and so on.

**To integrate the AppsFlyer SDK**:

1. Integrate the AppsFlyer SDK into the app.  
   See the guides for <Anchor target="_blank" href="/marketers/docs/sdk-integration-overview">Android</Anchor> and <Anchor target="_blank" href="/marketers/docs/sdk-integration-overview">iOS</Anchor> SDK integration.
2. Map in-app events you want to be recorded, using the AppsFlyer schemes.  
   This can be done via <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">SDK</Anchor> or <Anchor target="_blank" href="/marketers/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Remove the competing attribution vendor's SDK.  
   You can do this immediately and switch exclusively to AppsFlyer, or run both SDKs simultaneously for a few weeks. View a breakdown of these options in the table below.

| Option | What happens after  <br />updated app version release | Impact |
| --- | --- | --- |
| Remove competitor's SDK (recommended) | Only AppsFlyer records new installs and updating users.  <br />Competitor still shows events performed by users, until the users update their app too. | <ul><li>Fast transition.</li><li>No double attribution.</li></ul> |
| Keep competitor's SDK for a transition period | AppsFlyer and competitor attribute new installs and report events. At a later date, remove the competitor's SDK. | <ul><li>Data validation is possible. Meaning, you can compare data from AppsFlyer and the other vendor.</li><li>Double attribution, which may cause double charges with ad networks. See example below.</li><li>Higher workload.</li></ul> |

4. After all other tasks in the scope of work are completed, update the app version with AppsFlyer SDK to the market. New users are attributed by AppsFlyer.   
   **Note**:
   * Make sure to update the app for iOS, Google Play, and any relevant Android out-of-store markets.
   * Your Android app may exist in unofficial APK sites, even if you don't know it (search the web for your app's package name to find out). APK sites take some time to update to the latest version, so they may bring organic users, which install old versions without AppsFlyer SDK.
   * App update rollouts in the app stores can take a couple of days to fully complete. Users installing during this phase may still get the previous version.

</Accordion>

### Device migration—optional

<div id="about-device-migration" />

<Accordion title="About device migration">

Device migration is the process of uploading a list of your existing user device IDs (IDFA, IDFV, GAID, CUID) into AppsFlyer. You should perform this process before releasing the new app version, which will include the AppsFlyer SDK. There are two options when migrating devices, [attributed](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) or [non-attributed migration](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration).

Device migration solves data issues associated with existing app users who downloaded the app, and were attributed by your previous vendor. For example, SRN double charges, which occur when users originally attributed to an SRN under your prior vendor, and who are still within the lookback window, are claimed by the SRN again under AppsFlyer.

> 📄 **Example**
>
> * A new user clicks on an ad on the Facebook app and installs your app on June 15.
> * On June 24 the user updates the app to the version with the AppsFlyer SDK, and launches. For AppsFlyer, this is a new user, that needs to be attributed in real time.
> * AppsFlyer queries Meta ads with the user device ID. Because the user is still within the Meta ads 28-day lookback window, Meta ads self-attributes the user. This causes a double charge to the app owner for the same user.

Once you migrate devices, data reflects in AppsFlyer as follows:

* **Installs** **data:** Similar to <Anchor target="_blank" href="/marketers/docs/set-up-re-attribution-window#reinstall">re-installs</Anchor>, migrated devices have no install data. Migrated device installs are not displayed in AppsFlyer.
* **In-app events and sessions data:** Recorded and displayed as organic for [non-attributed device migration method](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration), or attributed to the media source and campaign, if using the [attributed method](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration).
* **Retargeting:** Re-attributions and re-engagements are displayed normally.
* **Activity data:** Displayed normally.
* **Retention and cohort data:** Migrated devices have no install record. As such, they aren't associated with any cohort, and can't be shown in the Retention and Cohort reports.

> 📘 **Note**
>
> If the app is not opened within 180 days from the migration date, all of the migrated device data is deleted. Consequently, if the app is opened after the 180 days period, a new install will be recorded.

</Accordion>

<div id="how-to-migrate-devices" />

<Accordion title="How to migrate devices">

**To migrate devices:**

1. Decide which user population to migrate. You can migrate all existing users (which may prevent you from getting accurate re-attribution data from AppsFlyer), or users that only recently installed your app (which may lead to double charges of somewhat older users).  
   **We recommend migrating users who are active during your current re-attribution window period.** For example, if your app has a 90-day re-attribution window, migrate those users who have at least one session during the previous 90 days.
2. [Optional] Tell the marketer/UA manager to pause existing marketing campaigns (from SRNs, non-SRN ad networks, owned media, etc.) until after the device migration.  
   If you decide not to pause campaigns, migrate any remaining device IDs from the other vendor as soon as the updated app version with the AppsFlyer SDK is released to app stores.
3. Prepare a CSV file based on the user population selected, using either the [attributed](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) or [non-attributed](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration) migration structure. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">See sample CSV</Anchor>
4. Send your AppsFlyer CSM the CSV.  
   Your CSM will migrate the device IDs to AppsFlyer.

</Accordion>

<div id="attributed-migration" />

<Accordion title="Attributed migration">

Devices migrated to AppsFlyer with this method have their in-app events, and sessions recorded and displayed according to the media source reported by the previous attribution vendor, and according to the ad networks' data retention policies.

#### Attributed device migration CSV structure

| Column  <br />name | Description | Mand-atory | Examples |
| --- | --- | --- | --- |
| app\_id | App ID as it appears in AppsFlyer dashboard | Yes | <ul><li>Android: com.great.app1</li><li>iOS: id123456789</li></ul> |
| platform | Device platform: ios or android | Yes | <ul><li>ios</li><li>android</li></ul> |
| device\_id | <ul><li>Android: gaid, android\_id,</li><li>iOS: IDFV (recommended, if available) or IDFA</li><li>Do not duplicate the same combination of device ID and app ID in multiple rows. If duplication occurs, the last occurrence in the file is used.</li></ul> | Yes | <ul><li>**gaid** (lower case): 9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**android\_id** (lower case): f35aea8908254891</li><li>**IDFV** (upper case): A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA** (upper case): 9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android:<ul><li>advertiserId</li><li>android\_id</li><li>amazon\_aid</li></ul></li><li>iOS:<ul><li>idfa</li><li>idfv</li></ul></li><li>Currently, other identifiers, OAID, IMEI are not supported.<br />Use non-attributed migration for Android users, which are not from Google Play.</li></ul>**Note**<br />`android_id` is not collected by the AppsFlyer SDK by default. If you use `android_id` as your identifier, make sure to <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">collect it in your SDK integration</Anchor>. | Yes | <ul><li>advertiserId</li><li>android\_id</li><li>idfa</li><li>idfv</li><li>amazon\_aid (lower case): df07c7dc-cea7-4a89-b328-810ff5acb15d</li></ul> |
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
| 1 | App ID + IDFA/GAID | <ul><li>If all your Android users have GAID identifiers.</li><li>iOS only users</li></ul> | [![device_migration_file_option_1.png](https://files.readme.io/e4902c1fd33dc348d636f0c9a571bddad966c37aa1f8fad19cf6160c8c1b7dfb-360003138317.png)](https://files.readme.io/e4902c1fd33dc348d636f0c9a571bddad966c37aa1f8fad19cf6160c8c1b7dfb-360003138317.png) |
| 2 | App ID + Device ID + Device ID type | <ul><li>If some of your Android users have only IMEI or Android ID, but not GAID (out-of-store markets, Android versions below 4.4.2).</li><li>Android ID needs to have a hexadecimal format.</li></ul>**Note**:<ul><li>Use the exact strings for the **ID type** column: advertiserId (also supports amazon\_aid), idfa, idfv, android\_id, imei.</li><li>If you use android\_id or imei, and later AppsFlyer receives a better identifier, a new attribution may be recorded.</li><li>`android_id` and `imei` are not collected by the AppsFlyer SDK by default. If you use either of these identifiers, make sure to <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">collect them in your SDK integration</Anchor>.</li></ul> | [![device_migration_file_option_2.png](https://files.readme.io/a85463bc7fd8f08e9c5e20d09b3b39f951547f18402c225ef3d952b18923b648-360003224698.png)](https://files.readme.io/a85463bc7fd8f08e9c5e20d09b3b39f951547f18402c225ef3d952b18923b648-360003224698.png) |

**CSV file rules:**

* CSV file can contain user devices from multiple apps.
* Each row contains a single device ID per app.
* Depending on the file structure option you choose, file columns must be as follows (and in the order listed):
  * Option 1: app\_id,device\_id
  * Option 2: app\_id,device\_id,id\_type
* App IDs in lowercase
* Android identifiers in lowercase
* IDFA/IDFV in uppercase
* Up to 25 million rows permitted

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">See sample CSV</Anchor>

</Accordion>

### Campaign migration

Switch existing marketing campaigns to AppsFlyer to enable AppsFlyer attribution, and avoid duplicate charges and the loss of attribution data.

**Note**: You can choose to only migrate a few marketing campaigns at a time. In this case, you can segment the ones you want to migrate by media source (for example, ad network or agency), geo, or campaign.

<div id="srns" />

<Accordion title="SRNs">

SRNs reply to Mobile Measurement Partners (MMPs) when queried about engagements of specific devices. If two MMPs, for example, AppsFlyer and a competing attribution vendor, query the same SRN about the same device install, you may incur double charges.

**To migrate SRN campaigns**:

* Activate and configure relevant <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns#srns-integrated-with-appsflyer">SRNs</Anchor> in AppsFlyer.

> 📘 **Note**
>
> * SRNs can run multiple MMPs (except Meta ads and Twitter).
> * Meta ads cannot de-duplicate in-app events.

</Accordion>

<div id="nonsrn-ad-networks" />

<Accordion title="Non-SRN ad networks">

Ad network attribution links record the engagements of users and are subsequently used to attribute the engagements that become actual installs.

**To migrate non-SRN ad network campaigns**:

1. <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">Activate</Anchor> the relevant ad networks in AppsFlyer.
2. <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">Generate AppsFlyer attribution links</Anchor> for each ad network.
3. Switch the existing links in each of your campaigns with the AppsFlyer attribution links.

</Accordion>

<div id="owned-media" />

<Accordion title="Owned media">

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

**To change your current owned media links into AppsFlyer OneLink links**:

* Contact your CSM, who will assist you with transforming your owned media links to into OneLink links according to the channels and tools you currently use.

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

For SKAdNetwork (SKAN) attribution, you can only have one SDK update the conversion value. Otherwise, SKAN data is rendered meaningless. Therefore, make sure that after migration, only the AppsFlyer SDK updates the SKAN conversion value.

<Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">Learn about setting up the SKAN conversion value in AppsFlyer.</Anchor>

</Accordion>

### Data report setup

<div id="adapt-and-map-report-structures" />

<Accordion title="Adapt and map report structures">

Before migration, your systems store your attribution data from your current vendor according to the reporting structures, fields, and parameters you have set up with them. For AppsFlyer to correctly report data, you must adapt and map your current report structures to AppsFlyer report structure, fields, and parameters.

**To adapt/map your report structures:**

* Contact your AppsFlyer CSM for help in quickly adapting/migrating your report data structures from Adjust, Branch/Tune, or Kochava to AppsFlyer.

</Accordion>

<div id="prepare-report-methods" />

<Accordion title="Prepare report methods">

You can get <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-apis">raw</Anchor> and <Anchor target="_blank" href="/marketers/docs/analytics-and-aggregate-reporting-apis">aggregate</Anchor> report data from AppsFlyer using a number of methods. Familiarize yourself with the methods and set up the ones that are relevant to you.

Reporting methods include:

* Dashboards
* Export reports
* Push API
* Pull API
* Data Locker

</Accordion>

<div data-zendesk-anchors="overview=about-migrating-to-appsflyer-from-other-vendors 01H8EDSTP8N4GZJQ5J609C3DHM=about-migrating-to-appsflyer-from-other-vendors h_01HQJ10ZFJR43KBYMD9A07CJ99=compare-measurement-between-appsflyer-and-other-mmps 01H8EDSTP8YGDZBPEY1976JP8C=tasks 01H8EDSTP8HGCVHYX49GQQEHBB=scope-of-work h_01F0RDXJ4F34DDKRFV5G6WZQX0=sdk-integration 01H8EDSTP97C85X2E9EKBSVFQJ=sdk-integration::c763138b device-migration%E2%80%94optional=device-migrationoptional h_01F0RDXVSQ13R9Q2KT7PK1KSCQ=device-migrationoptional 01H8EDSTP9NDF6611MVEMWQSMZ=about-device-migration 01H8EDSTP93QJA4XZB6TDWWH1V=example 01JA2CAMW3HCHC4B9FX7517FJ6=note 01H8EDSTP9M2MDMGZ8QBQGPM6S=how-to-migrate-devices h_01F0RPWKQ4B0T1TXRGPVTYPPFB=attributed-migration 01H8EDSTP9HABKEZJXMB84CDDE=attributed-device-migration-csv-structure h_01KV852C6CGBHSB6EFY122DRQY=note-1 h_01F0RPX3SJ391M8SPNNN50DDA8=nonattributed-migration nonattributed-device-migration-csv-file-structure=non-attributed-device-migration-csv-file-structure 01H8EDSTP9AFDMQS6BPQJY19ZH=non-attributed-device-migration-csv-file-structure h_01F0RDY9WPSBZVP3B7XN3ZEJKK=campaign-migration 01H8EDSTP94KSE1J4J5B7HX96Z=srns 01H8EDSTP9ZGMHSM44BWGF1FJN=note-1 01H8EDSTP981XVWVM2NE0A45RM=nonsrn-ad-networks 01H8EDSTP9XNJA80Z5XR7WR9QN=owned-media 01H8EDSTP9Q8JAPNXSQWSHSK32=skan h_01F0RDYKYHAEZ65GZBZ3MWTB5Z=data-report-setup 01H8EDSTP91E934EDXTPXW2ARJ=adapt-and-map-report-structures 01H8EDSTPAF8H5ESHDVK42M0RB=prepare-report-methods" />

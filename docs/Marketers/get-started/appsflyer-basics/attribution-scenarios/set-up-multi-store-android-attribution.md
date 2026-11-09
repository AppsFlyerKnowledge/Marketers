---
title: Set up multi-store Android attribution
metadata:
  keywords:
    - Android
    - Google
    - Google Play
    - Add App
    - amazon
    - Advertisers
    - Agencies
    - baidu
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-12-24T10:48:17Z'
  edited_at: '2025-10-21T08:51:45Z'
  id: 207447023
  locale: en-us
  section: Attribution scenarios
  section_id: 6551328497041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207447023-Set-up-multi-store-Android-attribution
---
> **At a glance:** Attribute your apps in multiple Android stores and view the data in a single app dashboard or in an app dashboard per store.

<div id="multi-store-android-attribution" />

## Multi-store Android attribution

AppsFlyer attributes apps, irrespective of the app store. Meaning Google Play store and third-party Android app stores like Amazon, Opera, GetJar, Baidu, and Huawei. (AKA out-of-market stores or alternate Android app stores.) App owners, who market the app via multiple stores, can choose between a **single** **dashboard** having the data of all stores together or a **dashboard per store.**

<div id="note" />

> 📘 **Note**
>
> * AppsFlyer Android attribution supports all device identifier types including GAID and <Anchor target="_blank" href="/marketers/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor>
> * For apps marketed in China, see <Anchor target="_blank" href="/marketers/docs/measure-attribution-in-the-chinese-domestic-market">Attributing Android apps in the Chinese domestic market</Anchor>

<Image align="center" alt="DashboardType_us-en-new.jpg" src="https://files.readme.io/10fdd08c4e57f799756f46922b5f8dc45c67f7550f9105e65076652f459c98f7-9545756936593.jpg" />

<div id="single-dashboard-vs-dashboard-per-store" />

### Single dashboard vs. dashboard per store

* **Single dashboard:** One dashboard that combines data from all stores, including Google Play Store
* **Dashboard per store:** Multiple dashboards—each store has its own dashboard. This means you have as many dashboards as stores providing the app.

<table><thead><tr><th> </th><th>Single dashboard<br/>[Best practice]</th><th> Dashboard per store</th></tr></thead><tbody><tr><td><span id="android-package-name"></span>Android package name</td><td colspan="2">Use the same (identical) package name irrespective of the option selected. </td></tr><tr><td><span id="channel-name"></span>Channel name</td><td>Nothing to set</td><td><ul><li><span>When adding the App in the AppsFlyer dashboard using the <strong>Android Out-of-Store APK</strong> option, set the channel.</span></li><li><span>The channel identifies the store.</span></li><li>The combination of Android package name and channel uniquely identifies each AppsFlyer dashboard.</li><li>Example: The Android package name is com.abc.def and the channel is xyzdevicestore. The unique dashboard identifier is com.abc.def-xyzdevicestore.</li><li>If the APK has a channel setting but there is no app with this setting, traffic is attributed to the default app, being the app with a blank channel setting being Google Play Store. </li></ul></td></tr><tr><td><span id="populating-the-install_app_store-field"></span>Populating the install_app_store field</td><td><ul><li>Uniquely identifies the store providing the app by download.</li><li>In the case of Google Play Store, this is blank.</li><li>The store name is set in the <a href="./set-up-multi-store-android-attribution#single-dashboard-apk-preparation">manifest/APK</a>.</li></ul></td><td>N/A</td></tr><tr><td><span id="onelink-template"></span><a href="./create-a-onelink-template#create-a-onelink-template" target="_blank">OneLink template</a></td><td>When working with OneLink this method is recommended. </td><td>N/A </td></tr><tr><td><span id="measurementattribution-links"></span>Measurement/Attribution links </td><td><ul><li>Links are the same irrespective of the store.</li><li>To redirect to the correct store, use <a href="./set-up-multi-store-android-attribution#single-dashboard-attribution-links">af_r</a> to set the redirect URL</li></ul></td><td><ul><li>A unique link is required for each store.</li><li>Create these using the <strong>Active integrations</strong> page.</li><li>The app ID is the channel name appended to the android package name. Ex: com.abc.def-def_store.<br/>Hence the attribution links will be different.</li></ul></td></tr><tr><td><span id="reporting-options-available-having-install_app_store-field"></span>Reporting options available having install_app_store field</td><td>Raw data reports always contain this field. For Overview and Cohort, reach out to your CSM asking them to add the necessary feature. </td><td>N/A </td></tr><tr><td><span id="considerations"></span>Considerations</td><td><ul><li>Attribution accuracy: Re-installs from different stores don't result in inflated install numbers.</li><li><span>Organic installs will reflect organic installs of APKs from all stores under one dashboard.</span></li><li><span>Reporting options, broken down per store,  are limited to Overview, Cohort, and raw data at present.</span></li></ul></td><td><ul><li>Attribution accuracy: Re-installs are counted, which results in less accurate attribution.</li><li><span>View organic and non-organic installs and in-app event data per store (channel) on separate app dashboards in AppsFlyer.</span></li><li><span>Use Cohort to display combined reports of all stores together</span></li><li><p>Activate a partner (<a href="./partner-activation-deactivation" target="_blank">Activate partner</a> is turned on) in each third-party store app where the partner is running an active campaign. This helps prevent attribution discrepancies, especially when working with self-reporting networks (SRNs).<br/> </p></li></ul></td></tr></tbody></table>

<div id="set-up-tasks" />

## Set-up tasks

The workflow that follows lists the activities required to set up the desired option. The tasks are divided between the marketer and developer.

For the Dashboard-per-store option repeat the tasks for each store.

<div id="before-you-begin" />

### **Before you begin**

* Decide on the naming convention for the channel and install\_app\_store parameters.
* Use the naming table that follows to map the channels and stores.
* The table is used by the developer to prepare the APKs.

<table><thead><tr><th>Parameter</th><th>Instruction</th><th>Single dashboard<br/>[Best practice]</th><th>Dashboard per store</th></tr></thead><tbody><tr><td>Android package name</td><td>The identical package name for all dashboard options</td><td colspan="2">If the app is already in Google Play Store use the existing package name. Example: comb.abc.def</td></tr><tr><td>Channel name</td><td>A unique value for each store.</td><td>Not set. Leave blank. </td><td><p>Unique for each store. Set the value in the individual APK prepared for the store and when adding the app in AppsFlyer. </p><p>Don't set a channel for the Google Play Store APK. </p></td></tr><tr><td>Install app store AF_STORE</td><td>A unique value identifying the store</td><td><span>Unique for each store. Set in the APK through the manifest. Each store has its own APK. </span></td><td> Not set</td></tr></tbody></table>

<div id="tasks" />

### Tasks

| Step | Responsibility | Single dashboard | Dashboard per store |
| --- | --- | --- | --- |
| 1 | Developer | [APK preparation](/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation) | [APK preparation](/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation) |
| 2 | Marketer | No action required. The assumption is that the app is already active in AppsFlyer. | [Add the app](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app) in AppsFlyer. |
| 3 | Marketer | [Prepare attribution links](/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links) | Prepare attribution links with the app ID combined with the channel name. |
| 4 | Developer and marketer | [Testing](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) | [Testing](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) |

<div id="procedures" />

## Procedures

<div id="single-dashboard-apk-preparation" />

<Accordion title="Single dashboard—APK preparation">

The Android package name determines which dashboard will contain the attribution data. In the single dashboard method, all stores have identical Android package names. There is no concept of a channel parameter here.

The identification of the download store is by way of the AF\_STORE parameter set in the SDK, as described in this section.  The AF\_STORE parameter isn't case-sensitive. For example, ABC, abc, Abc.

**To prepare the APK:**

1. Create a copy of the App build. **Note**: Don't change the Android package name.
2. To identify the individual store use one of the following methods:
   * **Manifest method:** Add the following within the `<application>` tag of the AndroidManifest.xml to identify the store. Set the AF\_STORE parameter to the app store name.

     ```xml
     <application>
        ...
        <meta-data android:name="AF_STORE" android:value="EnterStoreNameHere"/>
        ...
     </application>
     ```

     **--OR--**
   * **API method:** Prepare a separate APK for each alternative app store. Call the setOutOfStore API to set the AF\_STORE value. Set a unique value for each store.

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("EnterStoreNameHere")
     ```

The value set here appears in AppsFlyer raw data install\_app\_store field. This field is available in:

* Overview dashboard
* Cohort dashboard
* <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Raw data reports</Anchor> (Raw data reports are an AppsFlyer premium feature)

</Accordion>

<div id="single-dashboard-attribution-links" />

<Accordion title="Single dashboard—attribution links">

Whether you create your attribution link <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">for use by an advertising network</Anchor> or <Anchor target="_blank" href="/marketers/docs/onelink-onboarding-guide#about-onelink">for your own media</Anchor>, follow these steps to make sure that all your attribution link engagements appear on a single dashboard.

1. In your attribution link, set the **Out-of-store URL** parameter. This populates the `af_r` macro on the attribution link to redirect users to the correct app store landing page. For example, `&af_r=https://www.destinationurl.com`

   <div id="note-1" />

   > 📘 **Note**
   >
   > The default redirect **Out-of-store app URL** is set in the <Anchor target="_blank" href="/marketers/docs/app-settings">App Settings</Anchor> page. If this has been set up, there's no need to update the attribution link because attribution links created for the app will be auto-populated with this URL. <Anchor target="_blank" href="/marketers/docs/app-settings#outofstore-app-url">Learn more</Anchor>

2. Add `af_r` redirection to the <Anchor target="_blank" href="/marketers/docs/set-up-your-domain-redirect-allowlist">redirection allowlist</Anchor>.
3. Populate the `af_r` macro with the store landing page URL.
4. Set additional <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-parameters">attribution link parameters</Anchor>.
5. Out-of-store media sources **make use of ID matching for attribution** and the AppsFlyer <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#probabilistic-modeling">Probabilistic modeling</Anchor> serves as a fallback method.
6. Add one or more user ID placeholders to the link URL:
   * `android_id`
   * `advertising_id`
   * `oaid`
7. Copy the attribution link and give it to the ad network partner.

</Accordion>

<div id="dashboard-per-store-apk-preparation" />

<Accordion title="Dashboard per store—APK preparation">

The Android package name combined with the channel parameter set in the manifest determines which store dashboard will contain the attribution data.

**To prepare a separate APK/manifest for each store:**

* Add the following within the `<application>` tag of the AndroidManifest.xml to identify the store. Set CHANNEL parameter to the app store name.

  ```xml
  <application>
       ...
       <meta-data android:name="CHANNEL" android:value="EnterStoreNameHere"/>
       ...
  </application>
  ```

  **Note:** Parameters are case-sensitive. For the channel name you must use upper or lower-case letters only (a-z or A-Z). No other characters, such as hyphen (-) or underscore (\_), are permitted.

</Accordion>

<div id="dashboard-per-store-adding-the-app" />

<Accordion title="Dashboard per store—adding the app">

Add a dashboard (app) identified by the combination of the Android package name and channel set in the APK/manifest. Example: Android package name is com.myapp and the channel name is abcstore then the unique dashboard name is com.myapp—abcstore.

**To add a dashboard per store in AppsFlyer**:

1. In AppsFlyer, from the side menu, select **Settings** > **My apps**, and click **Add app**.
2. Select **Android > In 3rd-party store.**
3. Complete:
   * **Android package name:** The package name is exactly as it displays in the app package.
   * **Channel name:** Unique identifier (store name) to differentiate between dashboards having the same package name. Verify that you use the same value in the APK prepared for the store.  
     **Note:** For the channel name you must use upper or lower-case letters only (a-z or A-Z). No other characters, such as hyphen (-) or underscore (\_), are permitted.
   * **App URL:**
     * Contains the default URL download address that populates the af\_r macro in attribution links. Enter the URL where the APK is hosted or its landing page URL.
     * You can change this per attribution link when you create them.
4. Click **Next**.
5. Follow the instructions in the interface to complete adding the app.

</Accordion>

<div id="testing-both-dashboard-options" />

<Accordion title="Testing—both dashboard options">

<div id="non-organic-installs" />

#### **Non-organic installs**

**To test non-organic installs:**

1. Use an Android device that does not have your app installed or <Anchor target="_blank" href="/marketers/docs/registering-test-devices">register the device</Anchor>.
2. Generate a test attribution link using a <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink link</Anchor>. Use test as the Media source name ("&pid=test").
3. Add an advertising ID being GAID, OAID, or Android ID to the click URL.

   ```http
   https://app.appsflyer.com/com.greatapp?pid=test
   &af_r=https://www.destinationurl.com&advertising_id=b5a3-78d9b5-0f12345-xxxx
   ```

   Send the attribution link to yourself via email and click on it. **Once redirected, do not install from the store**. Instead, install the updated beta version app with AppsFlyer attribution SDK embedded and launch it.

| Single dashboard | Dashboard per store |
| --- | --- |
| <ol><li>Check your app installation raw-data report on the Export Data page.</li><li>You should see one install conversion with the test media source. Under the column titled **Install App Store,** you should see the name of the store as it appears on the manifest.xml file.</li><li>You can also see the param "af\_installstore": "STORE\_NAME" in the install logs.</li></ol> | <ol><li>Go to the necessary app per store dashboard.</li><li>Check the app's installs raw-data report under the Export Data page or look at the overview page of the app.</li><li>You should see one installation conversion with the “test” media source.</li></ol> |

<div id="organic-installs" />

#### **Organic installs**

**To test organic installs:**

1. Use an Android device that does not have your app installed or that is <Anchor target="_blank" href="/marketers/docs/registering-test-devices">registered</Anchor>.
2. Install the updated beta version app with AppsFlyer attribution SDK embedded and launch it.
3. Check the results:

<div id="expected-results" />

#### Expected results

| Single dashboard | Dashboard per store |
| --- | --- |
| Check the overview page for a new organic install (under the “organic” media source). At present, with the single app method, there is no indication as to the origin of organic installs. | <ol><li>Go to the dashboard and overview page of the app that is specific to the tested store.</li><li>You should see one installation conversion under “organic” media source.</li></ol> |

</Accordion>

<div id="additional-features" />

## Additional features

<div id="driving-users-to-the-amazon-app-store-from-facebook" />

<Accordion title="Driving users from Facebook to the Amazon app store">

1. Configure a URL link to the app in your Meta app settings, under the **Android** section.
2. Log in to Meta as the app admin, go to <Anchor target="_blank" href="https://developers.facebook.com/apps/">https://developers.facebook.com/apps/</Anchor>, and choose the app.
3. Go to settings and find your Android settings, or if you have not already configured Android, add the platform.
4. Fill out the required details, including the Amazon app store URL specific to your app.  

   <Image align="center" alt="outofstore_1.png" src="https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png" />
5. In the AppsFlyer dashboard, under Active Integrations, select Meta ads, and enter the same Facebook App ID you use when recording Meta In-Store Mobile App Install Ads with AppsFlyer.

</Accordion>

<div id="getting-the-data-appsflyer-reports" />

<Accordion title="Getting the data - Additional AppsFlyer reports">

In addition to the Overview dashboard, you can use the following reporting methods in AppsFlyer.

* Cohort:
  * Combine multiple dashboards (apps) in a single report
  * View the performance of each dashboard by breaking it down by install\_app\_store
* Pull API (for single app method): <Anchor target="_blank" href="/marketers/docs/pull-api-aggregate-data">Pull API</Anchor> installs raw data does not contain the **Install App Store** by default. To include the column add the following to the Pull API call: `&additional_fields=install_app_store`
* Custom dashboard (for multiple apps method): If you use the multi-dashboard approach, use the <Anchor target="_blank" href="/marketers/docs/custom-dashboards">custom dashboard</Anchor> to combine performance data from several apps in one place.

</Accordion>

<div id="referrer-implementation-thirdparty-android-app-stores" />

<Accordion title="Referrer implementation—third-party Android app stores">

Third-party stores referrer attribution is supported in the SDK as follows:

* **The Samsung store referrer**: Out of the box support.
* **The Huawei store referrer**: A dependency should be added by your developer, for instructions, see [the Dev Hub](https://dev.appsflyer.com/hc/docs/install-android-sdk#huawei-install-referrer).
* **The Xiaomi GetApps store referrer**: A dependency should be added by your developer, for instructions,  see [the Dev Hub](https://dev.appsflyer.com/hc/docs/install-android-sdk#xiaomi-getapps-store-referrer).

Third-party Android stores having referrer attribution integrations with AppsFlyer

| Third-party app store | Starting from | SDK version |
| --- | --- | --- |
| <span id="huawei-app-store"></span>Huawei App Store | July 2020 | 6.14.0 + |
| <span id="samsung-galaxy-store"></span>Samsung Galaxy Store | December 2020 | 6.1.1 + |
| <span id="xiaomi-getapps-store"></span>Xiaomi GetApps Store | September 2022 | 6.9.0 + |

</Accordion>

<div id="3rd-party-raw-data" />

<Accordion title="Third party store referrer in raw data reports">

Attribution by third-party store referrer is reflected in raw data reports as follows:

* Match type: the name of the third-party store attributed. For example, `huawei_referrer`.
* Contributor: If the user engaged with multiple app stores before installing the app, AppsFlyer considers these engagements as contributors. The install is awarded to the last-click engagement. Example:
  * A user clicks on an ad served by Google and is redirected to the Play Store. The user doesn't download the app.
  * The user clicks on another ad and is redirected to the Samsung Galaxy store. The user downloads and installs the app.
  * Attribution is awarded to the ad network causing the user to be redirected to the Samsung Galaxy store; Google is recognized as a contributor.

</Accordion>

<div id="troubleshooting" />

## Troubleshooting

<div id="installs-attributed-to-the-default-app" />

### Installs attributed to the default app

If you create an app APK with a channel setting but don't create a dashboard for it in the AppsFlyer account: Installs are attributed to the default app, usually the Google Play Store app in your account. If there is no default app no data is recorded for the app.

<div id="traits-and-limitations" />

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| OneLink redirection to multiple app stores | Multiple app stores can be set on the <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#create-a-onelink-template">OneLink template</Anchor> if the app package name is the same for all app stores and you implement the single dashboard option. |
| Install app store | This parameter isn't available for agencies or ad networks. |
| OneLink redirection to a third-party store | If your Android app is available exclusively through a third-party store, [you must set its Google Play status to Published out of store when adding the app](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app). Choosing any other status will prevent redirection to the third-party store and will result in an error message. |
| Ad revenue | `af_ad_revenue` values cannot be grouped by `install_app_store` values. |

<div data-zendesk-anchors="multistore-android-attribution=multi-store-android-attribution h_01HJ369QB8PDKG7QQRV840KRAY=multi-store-android-attribution h_01HJ369QB876GZKQCGJZQDXDRF=note h_01HJ369QB8SRN61ABBZ51TKFX2=single-dashboard-vs-dashboard-per-store reporting-options-available-having%C2%A0install_app_store-field=reporting-options-available-having-install_app_store-field setup-tasks=set-up-tasks h_01HJ369QB8NPE8FAHR42D2YN0K=set-up-tasks h_01JD2DEXW74MFE44FM3S0JCK5Q=before-you-begin h_01JD2DFF2K0APZ98JV1X09ZB33=tasks h_01HJ369QB990HH38TRQESQVFWN=procedures single-dashboard%E2%80%94apk-preparation=single-dashboard-apk-preparation h_01HJ369QB9V3W9R3EB6SJSNBED=single-dashboard-apk-preparation single-dashboard%E2%80%94attribution-links=single-dashboard-attribution-links h_01HJ369QB9H3J6E892X4V15AYJ=single-dashboard-attribution-links h_01K5EJP59771926PMZBRC0C2AB=note-1 dashboard-per-store%E2%80%94apk-preparation=dashboard-per-store-apk-preparation h_01HJ369QB9SP4DHZM5JB0RKEWG=dashboard-per-store-apk-preparation dashboard-per-store%E2%80%94adding-the-app=dashboard-per-store-adding-the-app h_01HJ369QB9X58DVBTWVWD0GCAV=dashboard-per-store-adding-the-app testing%E2%80%94both-dashboard-options=testing-both-dashboard-options h_01HJ369QB97FN9BJKD9WRW99YG=testing-both-dashboard-options nonorganic-installs=non-organic-installs h_01HJ369QB93A3ZZFAF0JAEXFRR=non-organic-installs h_01HJ369QB9SA05Y8VES8DD1FY4=organic-installs h_01HJ369QBAJADS4SMSDPKK9RHW=expected-results h_01HJ369QBAQ49ACSG3VEGSH7D4=additional-features h_01HJ369QBA1XVMZD4G019T2S9W=driving-users-to-the-amazon-app-store-from-facebook h_01HJ369QBA2WDAZNNPRRWA3MRT=getting-the-data-appsflyer-reports referrer-implementation%E2%80%94thirdparty-android-app-stores=referrer-implementation-thirdparty-android-app-stores h_01HJ369QBA4D0SG9MQE6MXB0DH=referrer-implementation-thirdparty-android-app-stores 01JBKT1E0YA06EKW27VR1DH861=3rd-party-raw-data 01JBKV47A5YJXKYHWA7H8NQAAF=troubleshooting h_01HJ369QBANRCTCFKTGK8BTQEC=installs-attributed-to-the-default-app h_01HJ369QBAJA87QJNTYNWYX82N=traits-and-limitations" />

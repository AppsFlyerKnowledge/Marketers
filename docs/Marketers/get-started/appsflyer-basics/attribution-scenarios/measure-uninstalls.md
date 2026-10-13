---
title: "Measure uninstalls"
excerpt: "Learn how to measure and analyze your app's uninstall rate to determine which media sources, campaigns, and creatives bring the highest quality users."
x-zendesk:
  id: 4408933557137
  url: https://support.appsflyer.com/hc/en-us/articles/4408933557137-Measure-uninstalls
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Attribution scenarios
  section_id: 6551328497041
  position: 4
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-alina-koifman, Marketers, Mobile Attribution]
  labels: [Advertisers, Developers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2021-10-14T08:03:47Z'
  edited_at: '2026-08-14T15:06:29Z'
---
Measure the uninstall rate for your app and determine which sources (media sources, campaigns, ad creatives, and geo) bring quality users.

## Overview

To understand the value of your app users, you must analyze both install and uninstall rates. The uninstall metric can help you measure your app's performance, and understand when and why users leave your app.

### How does it work?

1. AppsFlyer sends a daily API request to Firebase Cloud Messaging (FCM) and Apple Push Notification Services (APNS).
2. FCM and APNS then send a silent push notification to verify if an app is still installed on a given device.
3. An uninstall is recorded if the response indicates that the app was uninstalled (FCM and APNS) or no user activity was recorded for the past 270 days (FCM only).
4. AppsFlyer attributes the uninstall to the media source that originally brought the user.

> 📘 Note
>
> Uninstall metrics are available in the Unified dashboard and the user acquisition view.

## How to use uninstall data

The following are some examples of what you can learn from measuring uninstalls, and how you can use the data to optimize campaigns and user engagement.

### Compare the quality of sources

By comparing the quality of users acquired from different sources (media sources, campaigns, ad creatives, and geo), you can determine the media sources with the lowest uninstall rates, and reallocate funds to them.

**Example**

You are a marketer of gaming apps for PlayIt Gaming International. You have just launched a new app and you are running campaigns on two different media sources (Media source A, and Media source B).

When you check the dashboard you see that although Media source A has the highest number of installs (10,390), it also has the highest uninstall rate (30%).

Media source B, on the other hand, has 5,949 installs and the lowest uninstall rate (12%).

![Uninstall rates.png](https://files.readme.io/36fb732bfe3a63729b1aa0913f2fe3f24df6a7c86adde9f5c2b95424d840dec4-33839423253137.png)

Based on these insights, you could reallocate more of your budget to Media source B and try to acquire more engaged users.

### Share uninstall data with ad networks for optimization

Sending uninstall event postbacks to the ad networks you work with is useful for optimizing user acquisition campaigns. You can send the uninstall event by [mapping af_uninstall to your ad network](/docs/measure-uninstalls#mapping-the-uninstall-event). Once the mapping is complete, an event is sent each time a user is identified as having uninstalled the app. Ad networks can use this information to determine which users are less engaged and focus on getting more engaged users.

**Example**

You are a marketer of gaming apps for PlayIt Gaming International. Media source A is an ad network that you are working with on the launch of your new Android app. In the previous campaign you ran with Media source A, 1,000 new users installed your app, and subsequently, 300 users uninstalled the app. For the new campaign, you want Media source A to receive uninstall data. This will allow Media source A to quickly address uninstall challenges.

Based on insights from the previous campaign, Media source A creates a campaign exclusion list that excludes specific types of users from ads running in your new campaign:

- Users who have already proven that they are of lower value for your app.
- Users who regularly uninstall your apps.

This allows Media source A to optimize audience targeting to make sure that your campaign budget is not wasted on users who don't need to see certain campaign ads.

### Exclude uninstalls from retargeting campaigns

In some cases, to comply with regulations like GDPR and CCPA, you might need to exclude users that uninstalled your app from retargeting campaigns. Uninstall information allows you to create exclusion lists and apply privacy measures to protect your customers’ privacy and data.

Methods to exclude users include the following:

- [Raw-data reports:](/docs/raw-data-reporting-overview#user-journey-report-availability) A manual method in which you retrieve a list of uninstalled users from the **Uninstalls** report and create an exclusion list.
- [AppsFlyer Audiences:](/docs/audiences-guide) An automatic method in which you define a target audience based on specific criteria (for example, users who **haven't** uninstalled your app). Users that don't meet the criteria are excluded from the audience.

**Example**

You are a marketer of gaming apps for PlayIt Gaming International. You are running a retargeting campaign for one of your Android apps and you decide to use AppsFlyer Audiences to define a retargeting audience. The criteria for your audience is as follows:

- Users that haven't uninstalled the app.
- Users that haven't launched the app in the last 30 days.

This allows you to create a more exact retargeting audience. When your retargeting campaign runs, ads will only be served to users defined in your retargeting audience.

## Setting up uninstall measurement

The process of setting up the uninstall metric requires that the marketer and the developer work together. Implementation instructions depend on the operating system your app runs on.

The flow for the marketer and the developer is as follows:

<Tabs>
<Tab title="Android">

| Task | Owner |
| --- | --- |
| [Connect Firebase Cloud Messaging (FCM) to AppsFlyer](/docs/measure-uninstalls#connect-firebase-cloud-messaging-to-appsflyer-android) | Marketer |
| [Configure uninstall measurement in AppsFlyer](/docs/measure-uninstalls#configure-uninstall-measurement-in-appsflyer) | Marketer |
| [Integrate with the SDK](https://dev.appsflyer.com/hc/docs/uninstall-measurement) | Android developer |
| [Test uninstall measurement](/docs/measure-uninstalls#testing-uninstall-measurement) | Marketer |
| [Optional] [Map the uninstall event](/docs/measure-uninstalls#mapping-the-uninstall-event) to relevant partners in the dashboard | Marketer |

</Tab>
<Tab title="iOS">

| Task | Owner |
| --- | --- |
| [Generate P12 certificate](https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#creating-a-p12-certificate) | iOS developer |
| [Configure uninstall measurement in AppsFlyer](/docs/measure-uninstalls#configure-uninstall-measurement-in-appsflyer) | Marketer |
| [Integrate with the SDK](https://dev.appsflyer.com/hc/docs/uninstall-measurement) | iOS developer |
| [Test uninstall measurement](/docs/measure-uninstalls#testing-uninstall-measurement) | Marketer |
| [Optional] [Map the uninstall event](/docs/measure-uninstalls#mapping-the-uninstall-event) to relevant partners in the dashboard | Marketer |

</Tab>
</Tabs>

## Implementation procedures

Implementation requires your mobile developer to integrate a mechanism that responds to push notifications into your app. Implementation instructions vary according to the operating system.

### Connect Firebase Cloud Messaging to AppsFlyer (Android)

Android uninstall measurement is available by configuring uninstall measurement in AppsFlyer and adopting Firebase Cloud Messaging (FCM) into your app.

<Tabs>
<Tab title="HTTP V1">

**To configure FCM HTTP V1 for uninstalls:**

1. **To get the Project ID**:
   1. Go to the [FCM console.](https://console.firebase.google.com/)
   2. Select a project.
   3. Go to **Project Overview** > **Project settings.**
      ![UninstallFirebase.png](https://files.readme.io/15e74e10daa2f1f1d872f0c8fea274c9819c52c4655baa903728257dd6337e80-33839423254289.png)
   4. Copy the Project ID. You will need it at a later stage in the process.
2. **To enable the FCM API**:
   1. Go to the **Cloud Messaging tab**.
   2. Make sure that **Firebase Cloud Messaging API (V1)** is set to **Enabled**
3. **To assign AppsFlyer the uninstall role:**
   1. Go to the **Service accounts** tab.
   2. Click **Manage service account permissions**.
      
      A new browser tab opens in Google Cloud Platform.
   3. In the side menu, select **Roles**.
   4. Click **+Create role.**
   5. Complete as follows:
      - Title: Enter **AppsFlyer uninstalls**.
      - ID: Enter `af_uninstalls`.
      - Role launch stage: Select **General availability**.
   6. Click **Add permissions.**
   7. In ![adjusted.png](https://files.readme.io/c9fc0c6358ff89e1004ac1ab348a4b286d58c8a5cbe024aeb5c637136f3a67ac-33839382508049.png)**Filter**, Select the **cloudmessaging.messages.create** permission.
      ![Cloud Messaging permission filter](https://files.readme.io/255f5cf42ba1b07cae905ec0acbe6459303c3bd5b03f2d36e1ac3f9606fbb229-33839382512145.png)
   8. Click **Add** and then click **Create**.
4. **To assign AppsFlyer the FCM uninstall role:**
   1. In the side menu, select **IAM**.
   2. Open the **PERMISSIONS** -> **VIEW BY PRINCIPALS** tab.
   3. Click **Grant Access.**
   4. In **Add Principals** -> **New principals**, enter **af-uninstalls-tracking@af-uninstalls-tracking.iam.gserviceaccount.com**
   5. In **Assign roles** -> **Role** select the custom you created - **AppsFlyer Uninstalls**.
   6. Click **Save**.

      The AppsFlyer service account has been assigned the role of AppsFlyer uninstalls.

      > 📘 Note
      >
      > AppsFlyer uses silent push notifications solely to measure uninstalls or identify inactive users and does not use them for any other purposes.

</Tab>
<Tab title="[Deprecated] Legacy HTTP">

> ❗️ Important!
>
> HTTP legacy API were deprecated by Firebase on June 20, 2023, and will be removed on June 21st, 2024. If you are using the legacy API, we strongly recommend that you [use the HTTP v1 API](/docs/measure-uninstalls#http-v1). [Learn more](https://firebase.google.com/docs/cloud-messaging/http-server-ref)

Uninstall measurement using Firebase Messaging is supported by Android SDK V4.7.0+.

**To obtain the Firebase server key:**

1. Create a Firebase Android Application project (if you have not already done so), or migrate your project from **Google Developer Console** (follow the instructions there). For more information, go to [Firebase](https://firebase.google.com/docs/cloud-messaging/android/client).
2. Open the Firebase [Console](https://console.firebase.google.com/).
3. In the Firebase Console, navigate to the Project Settings (click on the cogwheel next to Project Overview on the left pane of the page).
![firebase_cloud_messaging_server_key.png](https://files.readme.io/4e31c02a1bea013c823b0148ba1704d4492f66d04e23f0e13e00a9c0c22d286c-33839382513041.png)
4. In the Cloud Messaging tab, you see two Server Keys.
5. Copy the **Server Key**.

</Tab>
</Tabs>

### Configure uninstall measurement in AppsFlyer

<Tabs>
<Tab title="Android">

**Prerequisite**: Android developer must complete their [integration instructions](https://dev.appsflyer.com/hc/docs/uninstall-measurement).

**To configure uninstall measurement in AppsFlyer**:

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings**.
2. If necessary, turn on **Uninstall measurement**.
3. Select **HTTP V1, and enter the project ID you prepared earlier.**
![UninstallHTTPV1.png](https://files.readme.io/80d13e47ea7ae1585d2ecc0e2f7210572e47dba936557c8e96314e49b0d738d8-33839423258641.png)
4. Click **Test connection**.

The success message displays.

> 📘 Note
>
> If you get the **Project ID is invalid or access permissions are missing** error message, after testing your connection, review your connection settings in FCM. For more information, see [Connect Firebase Cloud Messaging to AppsFlyer (Android)](/docs/measure-uninstalls#connect-firebase-cloud-messaging-to-appsflyer-android) in this article, and make sure that permissions/project ID are set correctly.

5. Click **Save settings**.

</Tab>
<Tab title="iOS">

**Prerequisite**: iOS developer must complete their [integration instructions](https://dev.appsflyer.com/hc/docs/uninstall-measurement).

**To configure uninstall measurement in AppsFlyer:**

1. Get the P12 file from your developer.
2. In AppsFlyer, from the side menu, select **Settings** > **App Settings**.
3. Scroll down to the Uninstall section.
4. Turn on **Uninstall measurement**.
![Uninstall_iOS_p2.png](https://files.readme.io/3f9de3ebe6099886fa9bc210bd6e491ba91e8ff2c890c980f66c4d48398a597c-33839423260561.png)
5. Click the upload icon, and select the P12 file.
6. [Optional] If the P12 certificate is password-protected, enter the password.
7. Click **Validate** to send the certificate to AppsFlyer for verification.
8. Click **Save Settings**.

</Tab>
</Tabs>

## Testing uninstall measurement

Once the implementation procedures are complete, you can install and then uninstall the app to test that uninstalls are recorded correctly. Uninstalls and uninstall rates are displayed on the Overview dashboard.

<Tabs>
<Tab title="Android">

You can perform this test on apps that are:

- In the Google Play Store
- Pending (not listed in the Google Play Store)
- Available through direct download
- In alternative app stores

Keep in mind the following when testing Android apps:

- Uninstall measurement is processed [daily](/docs/about-data-freshness-and-timezone-support#uninstalls). An uninstall event is registered within 24 hours, but if the app is reinstalled during this time, an event isn't recorded.
- **Uninstall events take up to 48 hours to display** in [raw-data reports](/docs/raw-data-reporting-overview) and in the AppsFlyer dashboard (Aggregated Performance Report).

</Tab>
<Tab title="iOS">

Keep in mind the following when testing iOS apps:

- Uninstalls do not immediately appear in the AppsFlyer dashboard. Due to the Apple Push Notification service, the time it takes uninstalls to appear on the dashboard is a minimum of 9 days. AppsFlyer updates and aggregates metrics for uninstalls every 24 hours.

  **Example**
  - Day 1: A user installs your app.
  - Day 4: A user uninstalls your app.
  - Day 12: Apple Push Notification Service reports app removal 8 days after the uninstall.
  - Day 13: Uninstall data appears in the AppsFlyer dashboard and raw data.

- If you are performing tests on a test version of the app, make sure you are using the sandbox environment. See developer instructions for the [uninstall sandbox procedure](https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#testing-uninstall-measurement).

</Tab>
</Tabs>

## Mapping the uninstall event

![Uninstall_event_postback.png](https://files.readme.io/9c3c7f3fd330720d4f6f41fdf509c5af00d042291c1350ab83a1951464ac8e8f-33839423261713.png)

To share uninstall data with an ad network requires mapping the [af_uninstall event](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration) to a partner. Unlike postbacks for regular in-app events, the uninstall event is not sent in real-time. The event time that is reported represents the time that AppsFlyer determined the app was uninstalled, and not the actual uninstall itself.

Keep in mind the following:

- AppsFlyer can only send the postback if the event actually occurs and is recorded by AppsFlyer.
- If you don't see uninstalls in the dashboard Overview page or in the raw-data report, this means that uninstall postbacks were not sent to the partner, even if the **af_uninstall** event was mapped.

#### Limitations

- Uninstall events are not included in in-app event postback reports.
- All partners support the **af_uninstall** event. If you want to map it to a partner but the event is not available in the partner's Integration tab, contact the partner directly for support.

## Turning off uninstall measurement

<Tabs>
<Tab title="Android">

If a Firebase/GCM Server Key is provided, app uninstall measurement is enabled by default. App owners can disable this feature via the dashboard.

</Tab>
<Tab title="iOS">

If a P12 certificate is provided and validated, app uninstall measurement is enabled by default. App owners can disable this feature via the dashboard.

</Tab>
</Tabs>

> 📘 Note
>
> For an uninstall to be reported, **Enable uninstall measurement** must be on at the time the app is installed. Installs occurring when **Enable uninstall measurement** is off aren't reported.

#### **To turn off uninstall measurement**:

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings**.
2. Go to **Attribution** > **Uninstall measurement** and turn off **Enable uninstall measurement.**

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| CUID | CUID isn't sent in uninstall postbacks. |
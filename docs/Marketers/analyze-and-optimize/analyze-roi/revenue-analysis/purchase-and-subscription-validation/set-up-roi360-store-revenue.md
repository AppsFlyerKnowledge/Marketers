---
title: "Set up ROI360 store revenue"
excerpt: "Learn how to configure the AppsFlyer ROI360 store revenue solution, including store credentials, server notifications, and SDK connector implementation."
x-zendesk:
  id: 42158608158353
  url: https://support.appsflyer.com/hc/en-us/articles/42158608158353-Set-up-ROI360-store-revenue
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Purchase and subscription validation
  section_id: 42227328788241
  position: 4
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-michael-talapov, Marketers, ROI360]
  labels: [Premium, Advertisters]
  promoted: false
  comments_disabled: false
  created_at: '2025-12-22T11:05:11Z'
  edited_at: '2026-07-01T17:06:19Z'
---
**At a glance:** Set up the AppsFlyer ROI360 store revenue solution.

> 📘 **Important!**
>
> ROI360 store revenue is available only to customers on the ROI360 premium plan. To check your plan or upgrade, contact your Customer Success Manager (CSM).


## Overview

> 📘 **Note**
>
> For more information about ROI360, including how it works and how to enable it in AppsFlyer, see [About ROI360 Store revenue](/docs/about-roi360-store-revenue).


To set up ROI360 Store Revenue, complete the following steps in order:

1. Set up store credentials (iOS and Android):
   * [iOS**:**](#step-1-ios-set-up-app-store-connect-keys) Configure App Store Connect keys (In-App Purchase key, Key ID, and Issuer ID) in AppsFlyer.
   * [Android](#step-1-android-set-up-service-account-key-and-permissions)**:** Configure a Google Cloud service account, set the required permissions in Google Play Console, and upload the service account JSON key to AppsFlyer.
2. Configure server notifications (iOS and Android):
   * [iOS](#step-2-ios-set-up-app-store-server-notifications)**:** Set up App Store Server Notifications, either by sending notifications directly to AppsFlyer (recommended) or by forwarding them from your own endpoint, and validate the integration.
   * [Android](#step-2-android-set-up-google-play-server-notifications)**:** Set up Google Play real-time developer notifications (RTDN), either by allowing Google Play to send notifications directly to AppsFlyer (recommended) or by forwarding them via Pub/Sub.
3. [Implement the SDK Connector](#step-3-implement-sdk-connector): Prepare developers to integrate the AppsFlyer Purchase SDK Connector.
4. [Verify SDK implementation](#step-4-verify-sdk-implementation): Test sandbox in-app purchases and subscriptions on both platforms to confirm that SDK events and server notifications are correctly received and processed by AppsFlyer.
5. [Verify and update settings](#step-5-verify-and-update-settings): Review and confirm the statuses of purchase validation, refund handling, subscription measurement, and store integration to ensure accurate, ongoing revenue attribution across platforms.
6. [Release app versions](#step-6-release-the-app-versions-with-the-sdk-connector): Release updated app versions with the SDK Connector integrated, ensuring sandbox flags are disabled and validation rules allow the required revenue events.

## Step 1 (iOS): Set up App Store Connect Keys

In step 1, obtain the following credentials from App Store Connect and input them in the Revenue Settings page within the AppsFlyer platform.t

* In-App Purchase key
* Key ID
* Issuer ID

**Before you start**:

Setting the credentials involves steps performed in both App Store Connect and AppsFlyer. During setup, keep both the App Store Connect and AppsFlyer tabs open.

### 1.1 Create the App Store Connect keys

To set iOS credentials,follow these step:

1. In the App Store Connect, go to **Users and Access**

   [![](https://files.readme.io/915adbb054060c95ccdf784ecb5690e7f417e5851eda5a652727947698a03c3d-42158608027793.png)](https://files.readme.io/915adbb054060c95ccdf784ecb5690e7f417e5851eda5a652727947698a03c3d-42158608027793.png)
2. Go to **Users and Access**> **Integrations**, and from the **Keys**list, select **In-App Purchase**.

   [![](https://files.readme.io/a24c642acd6d2470cd0b7e575e9ecb36c40eaef9d5fa9e8337a758e2b404ba14-42158637491729.png)](https://files.readme.io/a24c642acd6d2470cd0b7e575e9ecb36c40eaef9d5fa9e8337a758e2b404ba14-42158637491729.png)
3. Click **+** to generate a new In-App Purchase key.

   [![](https://files.readme.io/2ac7ba9197d1d3f134539eba3f315f497ccd8664a25ed6144606199c125dbba6-42158608030609.png)](https://files.readme.io/2ac7ba9197d1d3f134539eba3f315f497ccd8664a25ed6144606199c125dbba6-42158608030609.png)
4. Enter a name for your API key.
5. Click **Generate**.
6. Click **Download In-App Purchase Key**next to the key you just generated to download it. **Note**: You can only download the key once.
7. Copy the **Key ID** of the key you just generated and paste it into the AppsFlyer purchases & subscriptions setting for **Key ID**.

   [![](https://files.readme.io/7a7be640b7b338aba367c37f4eeb01911cba88564f72b88749c19d8e5c31d47c-42158608031633.png)](https://files.readme.io/7a7be640b7b338aba367c37f4eeb01911cba88564f72b88749c19d8e5c31d47c-42158608031633.png)
8. Copy the **Issuer ID**. **Note**: If the **Issuer ID** is not displayed at the top of the page, create an App Store Connect API key (with any access level). After that, the Issuer ID will appear at the top of the page for the In-App Purchase key.

   [![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)

### 1.2 Set the App Store Connect key in AppsFlyer

1. [Enable ROI360 Store revenue](/docs/about-roi360-store-revenue#enable-roi360-store-revenue).
2. Under the **App Store Connect keys** step, click [![](https://files.readme.io/83e35630c777ef41478e3743591733723e340c2cb885fab2072ca51b3ce95b47-42158637499665.png)](https://files.readme.io/83e35630c777ef41478e3743591733723e340c2cb885fab2072ca51b3ce95b47-42158637499665.png) **Upload** in the **In-App Purchase key**field to upload the p8 file.
3. In the section titled **App Store Connect keys**, paste the values you copied from App Store Connect.

   * **Key ID**

   * **Issuer ID**
4. Click **Validate keys** to ensure the keys you entered are correct. **Note: The Validate key** may not work if your app has not yet been published in the App Store.
5. click **Save and next**

## Step 1 (Android): Set up service account key and permissions

In step 1, you can obtain the following credentials from App Store Connect and input them in the Revenue Settings page within the AppsFlyer platform.

**Before you start**:

* Setting up in-app purchase and subscription revenue measurement involves steps performed in the [Google Cloud Platform](https://cloud.google.com/), [Google Play Console](https://play.google.com/console/), and the [AppsFlyer UI](https://hq1.appsflyer.com/auth/login). We recommend keeping tabs on all three places open throughout the setup.
* Setting up in the AppsFlyer UI requires admin permissions.

### 1.1. Link your Google Play Developer Account to your Google Cloud Project

**Prerequisites**: Access to Google Play Console and Google Cloud Project.

**To link your Google Play Developer Account to your Google Cloud Project, follow these steps**:

1. In the Google Play Console, go to your Google Play Developer Account.
2. Link the account to your Google Cloud project. For instructions, see this [Google help topic](https://developers.google.com/android-publisher/getting_started#linking).
3. Enable the Google Play Developer API. For instructions, see [this Google help topic](https://developers.google.com/android-publisher/getting_started#enable).

   [![](https://files.readme.io/f30f2ed9081b4ad0a5455e5592838cb70a47c49767b69eaaaa73011a60bc4b8d-42158637503633.png)](https://files.readme.io/f30f2ed9081b4ad0a5455e5592838cb70a47c49767b69eaaaa73011a60bc4b8d-42158637503633.png)

### 1.2. Configure your Service Account in the Google Cloud Platform

**Prerequisites**: Access to Google Cloud Platform.

**To configure your service account, follow these steps**:

1. Create or locate the **Service Account**:
   1. Go to the **Service accounts** section in the Google Cloud Platform and click **Create Service Account**.

      [![](https://files.readme.io/639ded7c1b878913c33b350d9931620b8c1e6d3eda826a35c44141a22a562488-42158637505169.png)](https://files.readme.io/639ded7c1b878913c33b350d9931620b8c1e6d3eda826a35c44141a22a562488-42158637505169.png)
   2. Complete the service account details.

      [![](https://files.readme.io/7f5cf6b02e8d33bab5fece9170c30be03dea5d27309d716f9017bc9ec418ca6b-42158637508113.png)](https://files.readme.io/7f5cf6b02e8d33bab5fece9170c30be03dea5d27309d716f9017bc9ec418ca6b-42158637508113.png)
   3. Copy the email address.

      [![](https://files.readme.io/6a1c5e9fe99c89418b6039cd23285e85c41211e154e5000d72347bbf9a26f963-42158608046993.png)](https://files.readme.io/6a1c5e9fe99c89418b6039cd23285e85c41211e154e5000d72347bbf9a26f963-42158608046993.png)
   4. Click **Create and continue**.

      [![](https://files.readme.io/118bdf5197362d8df8f8c14b59b1c377fb6badc17d152c7ffb8b62037079ec07-42158608050833.png)](https://files.readme.io/118bdf5197362d8df8f8c14b59b1c377fb6badc17d152c7ffb8b62037079ec07-42158608050833.png)
   5. In the **Grant this service account access to the project**step, select the **Pub/sub** subscriber role.

      [![](https://files.readme.io/c015aafa83ec986d4ed9de867774ef7a277e34f6b90086580691d884aff28646-42158637513617.png)](https://files.readme.io/c015aafa83ec986d4ed9de867774ef7a277e34f6b90086580691d884aff28646-42158637513617.png)
   6. Click **Continue**> **Done**.

      [![](https://files.readme.io/e6618c1f51dff42982380b1f7ac994c31edaa9862b7ec3343b3c8e5d0207bc71-42158637515537.png)](https://files.readme.io/e6618c1f51dff42982380b1f7ac994c31edaa9862b7ec3343b3c8e5d0207bc71-42158637515537.png)
2. Download the **Service Account Private Key**:
   1. In the Google Cloud Platform, go to the **Service accounts** section, find the account you want (the one you just created) from the list, and click the **More actions** icon.
   2. Click **Manage keys**.

      [![](https://files.readme.io/9c2e3e6e1e069325c4a47a0e1e638805cfb9235f6c3fca6a32b29e530074b6cf-42158637519889.png)](https://files.readme.io/9c2e3e6e1e069325c4a47a0e1e638805cfb9235f6c3fca6a32b29e530074b6cf-42158637519889.png)
   3. Click **Add key** > **Create new key**.

      [![](https://files.readme.io/beb1e5a984ca5335f51ffa44d2532ddbfa1147ee2a5a88a543de640c7248f7bd-42158637522321.png)](https://files.readme.io/beb1e5a984ca5335f51ffa44d2532ddbfa1147ee2a5a88a543de640c7248f7bd-42158637522321.png)
   4. In the **Create private key** popup, under **Key type**, select **JSON**, and click **Create**.

      [![](https://files.readme.io/a3b7c0468b9ba1984a18340519ca59a40b12ee52066a2faae6c5b21931f8828b-42158608067089.png)](https://files.readme.io/a3b7c0468b9ba1984a18340519ca59a40b12ee52066a2faae6c5b21931f8828b-42158608067089.png)
   5. Click **Create**. The private key JSON file is downloaded.

      [![](https://files.readme.io/1a577ef4d159c73ff76a6a79a45a7909a3f9ee422abc5990482b3b45e308d666-42158637525649.png)](https://files.readme.io/1a577ef4d159c73ff76a6a79a45a7909a3f9ee422abc5990482b3b45e308d666-42158637525649.png)
   6. Save the JSON key file, which will be uploaded to AppsFlyer later. **Note**! You must save the key; it can't be retrieved later. If you don't save it, you will have to create an entirely new key

### 1.3. Set API access permissions in Google Play Console

**Prerequisites**: Access to Google Play Console.

**Note**: It can take time (sometimes even 24 hours) after setting service account credentials and permissions to be able to use them. This may cause you to receive errors in later steps.

**To set API access permissions in Google Play Console**:

1. In the Google Play Console, go to **Users and permissions**, find the service account you created, and click **Invite new users**.

   [![](https://files.readme.io/eab4eb0b7357f890d7c86fe4095c031d82de7ba2ab6ddb32a472a521310fdaab-42158637526929.png)](https://files.readme.io/eab4eb0b7357f890d7c86fe4095c031d82de7ba2ab6ddb32a472a521310fdaab-42158637526929.png)
2. Enter the **Email address** that you copied when you configured your service account in step 1.2.1.3.

   [![](https://files.readme.io/fbac8546bf697a6efa183217fad16a965752bc2f2c9b0b9051b178c2eac15e40-42158608078609.png)](https://files.readme.io/fbac8546bf697a6efa183217fad16a965752bc2f2c9b0b9051b178c2eac15e40-42158608078609.png)
3. In the **Permissions** section, go to the **Account permissions** tab, and select both:

   * View financial data, orders, and cancellation survey responses.
   * Manage orders and subscriptions.[![](https://files.readme.io/41c44a10091b60e7ad356d864dd26bf313c8ed9ebfc91a4599be71a510c9f26b-42158637529105.png)](https://files.readme.io/41c44a10091b60e7ad356d864dd26bf313c8ed9ebfc91a4599be71a510c9f26b-42158637529105.png)
4. On the **App permissions** tab, click **Add app,**then select your app. Add multiple apps if needed.

   [![](https://files.readme.io/51457fad5fab7516d5e8d89867796795fbb4b938f723bcaf62b86b33ef3ce096-42158637538961.png)](https://files.readme.io/51457fad5fab7516d5e8d89867796795fbb4b938f723bcaf62b86b33ef3ce096-42158637538961.png)
5. Click **Invite user.**

   [![](https://files.readme.io/1fe2f95c7f0c06fded8cd14628e37b535d52447ef9261e1c02b8ade1139a1546-42158637541137.png)](https://files.readme.io/1fe2f95c7f0c06fded8cd14628e37b535d52447ef9261e1c02b8ade1139a1546-42158637541137.png)
6. In the confirmation popup, click **Send invite**.

   [![](https://files.readme.io/7e643e577d3134dcf352eeeafc26cacbcb8dcee718892f2ca14132fa593c1015-42158608083729.png)](https://files.readme.io/7e643e577d3134dcf352eeeafc26cacbcb8dcee718892f2ca14132fa593c1015-42158608083729.png)

### 1.4. Upload the Service Account Private Key to AppsFlyer

Upload and validate the Google JSON key you downloaded in [step 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).

**Prerequisites**: Admin access to AppsFlyer.

**To upload the Service Account Private Key to AppsFlyer, follow these steps**:

1. [Enable ROI360 Store revenue](/docs/about-roi360-store-revenue#enable-roi360-store-revenue).
2. Under the **Service Account Key and Permissions** step, in the **Upload Google JSON key**field, click [![](https://files.readme.io/83e35630c777ef41478e3743591733723e340c2cb885fab2072ca51b3ce95b47-42158637499665.png)](https://files.readme.io/83e35630c777ef41478e3743591733723e340c2cb885fab2072ca51b3ce95b47-42158637499665.png)  **(Upload icon).**
3. Upload the JSON file you downloaded in [step 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).
4. Click **Validate Key.****Note:**
   * After setting service account credentials and permissions, it can take up to 24 hours to be able to use them. This may cause you to receive errors when trying to validate the key or perform a validation test.
   * To work around the 24-hour wait time, in the Google Play Console, navigate to any application, then go to **Monetize** > **Products** > **Subscriptions/In-app products**, and make a change. For example, edit the description of your product and save it. This should instantly update the account credentials and permissions. You can then undo the changes.
5. Click **Save and Next**.

## Step 2 (iOS): Set up App Store server notifications

Set how App Store notifications are received in AppsFlyer.

* If you already have an App Store server notifications endpoint configured in App Store Connect (for example, your own backend or another service), choose between **Option 1 (recommended)** or **Option 2**.
* If you have not yet configured an endpoint in App Store Connect, choose **Option 1**.

#### Option 1 (Recommended) - AppsFlyer as the primary endpoint

Replace the existing App Store Connect notification URL with the AppsFlyer endpoint, and add your previous endpoint in AppsFlyer as a forwarding destination. Your current subscription logic and workflows remain unchanged and continue to function as expected.

The notification flow for this option is as follows:

1. App Store Connect sends notifications to AppsFlyer
2. AppsFlyer processes them for ROI360
3. AppsFlyer forwards all notifications to your existing endpoint **in real time**

To use this option, complete steps [2.1](#21-copy-the-appsflyer-server-notifications-endpoint), [2.2](#22-send-notifications-directly-to-appsflyer), and [2.4](#24-test-the-server-notifications-integration).

#### Option 2 - Your endpoint as the primary endpoint

If you prefer to keep your existing endpoint as the primary destination, configure your server to forward App Store server notifications to AppsFlyer.

To use this option, skip steps 2.1, 2.2 and complete steps [2.3](#23-[optional]-forward-notifications-from-your-endpoint-to-appsflyer) and [2.4](#24-test-the-server-notifications-integration)

> 📘 **Note**
>
> Apple supports only one App Store server notification endpoint per app, and sends all notification types to it, not only purchase and subscription notifications. AppsFlyer uses the purchase and subscription notifications to measure revenue. It acknowledges any other type back to Apple, so Apple stops retrying, but does not process or act on it.
>
> If your app relies on notification types beyond purchases and subscriptions (for example, consent notifications), make sure those notifications reach your own server:
>
> * **Option 1:** Keep AppsFlyer as the primary endpoint and enable forwarding (step 2.1). AppsFlyer forwards a copy of all notifications to your endpoint in real time, unchanged from how Apple sent them, including the types AppsFlyer does not process.
> * **Option 2:** Keep your own endpoint as the primary destination, so your server receives and handles all notification types directly, and forward purchase and subscription notifications to AppsFlyer.


### 2.1 Copy the AppsFlyer server notifications endpoint

To copy the AppsFlyer server notifications endpoint, follow these steps:

1. **In AppsFlyer,**inthe **App Store server notifications** step, copy the AppsFlyer server notifications endpoint.
2. If you previously had another App Store server notifications endpoint and want AppsFlyer to forward notifications to it, select **Forward a copy of notifications to your server (relevant for option 1 only).**
3. Enter your notification forwarding endpoint in the displayed text box.

### 2.2 Send notifications directly to AppsFlyer

To send notifications directly to AppsFlyer, set up AppsFlyer as the primary App Store server notifications endpoint.

1. In **App Store Connect**, in the **App Information** section, scroll to **App Store Server Notifications**, and next to **Production Server URL**, click **Edit**.

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. Paste [the AppsFlyer server notifications endpoint copied from AppsFlyer](#21-copy-the-appsflyer-server-notifications-endpoint), select **Version 2 Notifications**, and click **Save**. **Note:** Version 1 notifications are no longer supported. If the notification-version selector does not appear in Apple Store Connect, it means you are already using Version 2.

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. In the **App Information** section, scroll to **App Store Server Notifications**, and next to **Sandbox Server URL**, click **Edit**.

   [![](https://files.readme.io/fffd184969c2b29d8dfbb7acdcc53482e47ca7da506b44ab5aa65f3328ca21bb-42158608093969.png)](https://files.readme.io/fffd184969c2b29d8dfbb7acdcc53482e47ca7da506b44ab5aa65f3328ca21bb-42158608093969.png)
4. Paste [the AppsFlyer server notifications endpoint copied from AppsFlyer](#21-copy-the-appsflyer-server-notifications-endpoint), select **Version 2 Notifications**, and click **Save**. **Note:** Version 1 notifications are no longer supported. If the notification-version selector does not appear in Apple Store Connect, it means you are already using Version 2.

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)

### 2.3 [Optional] Forward notifications from your endpoint to AppsFlyer

Use this step only if you want to keep your endpoint as the primary destination for App Store server notifications, instead of sending notifications directly to AppsFlyer.

This option is not the recommended setup and requires backend implementation. If you already configured AppsFlyer as the primary endpoint in step **2.2** above, skip this step.

To forward server notifications from your endpoint to AppsFlyer, follow these steps:

1. In **App Store Connect**, in the **App Information** section, scroll to **App Store Server Notifications**, and next to **Production Server URL**, click **Edit**.

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. Paste **your server endpoint URL**.

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. Select **Version 2 Notifications. Note:** Version 1 notifications are **no longer supported**. If the notification-version selector does not appear in Apple Store Connect, it means you are already using Version 2.
4. Click **Save**.
5. In **App Store Connect**, in the **App Information** section, scroll to **App Store Server Notifications**, and next to **Sandbox Server URL**, click **Edit**.

   [![](https://files.readme.io/fffd184969c2b29d8dfbb7acdcc53482e47ca7da506b44ab5aa65f3328ca21bb-42158608093969.png)](https://files.readme.io/fffd184969c2b29d8dfbb7acdcc53482e47ca7da506b44ab5aa65f3328ca21bb-42158608093969.png)
6. Paste **your server endpoint URL**.

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)
7. Select **Version 2 Notifications. Note:** Version 1 notifications are **no longer supported**.
8. Click **Save**.
9. Configure your backend to forward Apple server notifications to the AppsFlyer notification endpoint URL. The requests must match the App Store payload exactly as received from Apple, see[Apple format requirements](https://developer.apple.com/documentation/appstoreserverapi/signedpayload#discussion).

### 2.4 Test the server notifications integration

To confirm that AppsFlyer is receiving App Store server notifications correctly, or if you recently configured the endpoint and no server notifications have arrived yet:

1. In AppsFlyer, go to the **App Store server notifications** step.
2. Click **Test integration**. AppsFlyer sends a test notification request to Apple and checks whether any valid notifications were received from Apple in the past 7 days, and displays one of the following:

   * A confirmation of whether valid notifications were received.
   * A status message indicating that no notifications were found.

   CALLSTART::Note::

   #### Note

   Apple may take a few seconds to send the test message.

   CALLEND::

   * If the status remains invalid, wait a few moments and try again.
   * After the test succeeds, or when you are ready to continue, click **Save and next**.

## Step 2 (Android): Set up Google Play server notifications

To receive in-app purchase and subscription revenue data from Google Play, select between the following options:

* (Recommended) Google Play sends the notifications directly to AppsFlyer. With this option, no notification copies can be forwarded to your endpoint. If you'd like to select this option, you can see [Send Google Play notifications directly to AppsFlyer](#21-send-google-play-notifications-directly-to-appsflyer).
* Google Play sends the notifications to you first, which are then forwarded to AppsFlyer. If you choose this option, see [Forward Google Play notifications to AppsFlyer.](#22-[optional]-forward-google-play-notifications-to-appsflyer)

**Prerequisites**: Access to Google Play Console and AppsFlyer UI.

### 2.1 Send Google Play notifications directly to AppsFlyer

1. In AppsFlyer, on step 2**, Set up Google Play server notifications**, select **Allow AppsFlyer topic to get RTDN messages directly from Google**.
2. Copy the AppsFlyer topic to the clipboard.
3. In **Google Play Console** > **Home**, select to view your app. The dashboard opens.

   [![](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)
4. Go to **Monetize with Play** > **Monetization setup**, and in the **Google Play Billing** section, make sure **Enable real-time notification** is checked.

   [![](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)
5. In the **Topic name** field, paste the AppsFlyer topic address you copied.

   [![](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)
6. For **Notification content**, select **Subscriptions, voided purchases, and all one-time products**.

   [![](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)
7. Click **Save Changes**. It can take time (sometimes even 24 hours) for this to take effect. Therefore, wait before testing.

### 2.2 [Optional] Forward Google Play notifications to AppsFlyer

**Note**: This step is only for when you didn’t choose the recommended method to receive in-app purchase and subscription revenue data from Google Play by sending notifications directly to AppsFlyer. If you completed the steps for the recommended method to create a topic where AppsFlyer directly receives the RTDN notifications from Google Play, skip this step.

If you want to set AppsFlyer as a subscriber to your existing PUB/SUB topic, continue with the instructions below.

**Prerequisites**: Access to Google Cloud Platform and AppsFlyer UI.

**To forward Google Play notifications to AppsFlyer**:

1. In AppsFlyer, from the side menu, go to **Settings** > **Revenue Settings**,
2. Select your app,
3. In the **Purchases & subscriptions**tab, select **Forward your RTDN topic messages to AppsFlyer**.
4. Copy the endpoint URL to the clipboard.
5. In Google Cloud Platform, under your project, search for **Pub/Sub**.

   [![](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)
6. In **Pub/Sub** go to the **Topics** section, and verify you have a dedicated pub/sub topic for subscriptions.

   [![](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)
7. In **Pub/Sub,** go to the **Subscriptions** section, and click **Create Subscriptions**.

   [![](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)
8. Enter the **Subscription ID**.

   [![](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)
9. Select the relevant subscription pub/sub topic from the dropdown.

   [![](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)
10. For **Delivery type**, select **Push**.

    [![](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)
11. Paste the **Endpoint URL** that you copied from AppsFlyer.

    [![](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)
12. Under **Expiration period**, select **Never expire**.

    [![](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)
13. Click **Create**.

    [![](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)
14. Go to the **Subscriptions** section and click into the Topic name you want.

    [![](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)
15. Copy the topic name to the clipboard.

    [![](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)
16. In **Google Play Console**, go to **Monetize with Play** > **Monetization setup.** and in the **Google Play Billing** section, paste the topic name that you copied in the previous step in the Topic name field.

    [![](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)
17. For **Notification content**, select **Subscriptions, voided purchases, and all one-time products**.

    [![](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)
18. Click **Save changes**. It can take time (sometimes even 24 hours) for this to take effect. Therefore, wait before testing.

### 2.3 Send a test notification from Google Play Console

To verify that Google Play real-time developer notifications (RTDN) are correctly received by AppsFlyer, send a test notification from Google Play Console:

1. Click **Send test notification**. This sends a test RTDN message to the Pub/Sub topic configured for AppsFlyer.

   ![image (33).png](https://files.readme.io/4d7aa79eb963373223cfde1d32db16b739119a86d8d4f0cf6ce026d42a709bf3-42170040528657.png)
2. Under **Google Play Billing**, locate the Topic name section.
3. In the left menu, navigate to **Monetise with Play** → **Monetisation setup**.
4. Go to the Google Play Console.

### 2.4 Confirm notification delivery in AppsFlyer

1. When the test succeeds, or when you're ready to proceed, click **Save and next**.
2. Result: AppsFlyer displays whether any notifications were received in the last 7 days.
   * If successful, the interface shows the date and time of the most recent notification.
   * If none were received, the interface indicates that no notifications were found in the last 7 days.
   * If no status appears, review your Pub/Sub configuration and resend the test notification.
3. In the **Google Play Server Notifications** step, click **Test integration**.

## Step 3: Implement SDK Connector

In this step, you’ll prepare your developers to integrate the AppsFlyer Purchase SDK Connector and configure the sandbox environment for testing.

To implement the SDK connector, follow these steps:

1. In the **Implement SDK Connector** step, copy the **pre-written message** displayed in the dashboard.
2. Send it to your developers. It includes:
   * The app name and App ID
   * A link to [the SDK integration guide](https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation).
   * Instructions to configure the sandbox environment (`sandbox = true`)
   * Testing steps (using **TestFlight**)

This message provides all the information your developers need to complete the integration and begin testing.

> 📘 **Note**
>
> The connector uses automatic transaction detection. As an alternative, you can implement the `validateAndLog` SDK method to manually log each transaction. This method does not support all features available with the connector. For details on both SDK integration options, see [the DevHub documentation](https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation).


## Step 4: Verify SDK implementation

Test the in-app purchase and subscription revenue integration in a sandbox environment to confirm that the SDK connector is correctly integrated and that server notifications are properly configured and received by AppsFlyer.

### Test SDK implementation

To check whether AppsFlyer has received valid purchase and subscription event payloads from your app in the last 7 days, perform these steps:

1. In the **Verify SDK implementation** step, click **Test SDK implementation**.
2. Review the results, including the timestamp of the most recent payload received by AppsFlyer.

   CALLSTART::Note::

   #### Note

   This test only confirms that requests are reaching AppsFlyer and does not verify the completeness or correctness of the data.

   CALLEND::
3. To fully validate the implementation, continue with the testing steps below.

### Sandbox events and parameters

* The SDK connector generates events only for the initial sandbox transaction:
  * In-app purchase: `af_purchase_sandbox_sdk`
  * Subscription: `af_ars_sandbox_sdk`
* AppsFlyer processes server notifications only if the SDK event for the original transaction was recorded.
  * In-app purchase S2S: `af_purchase_sandbox_s2s`
  * Subscription S2S: `af_ars_sandbox_s2s`
* If the SDK never records the original transaction. no S2S event is created.

**iOS considerations**

* If `af_purchase_sandbox_sdk` includes `af_sandbox_revenue`, it maps to a production `af_purchase`.
* If no revenue is present, it maps to a production `af_purchase_free`.

**Android considerations**

* Purchases by **License Testers** always generate sandbox events. even if sandbox mode isn’t configured in the SDK.

**Required parameters for test events**

Ensure that every sandbox purchase event includes:

* **Revenue = 0** (to avoid affecting real reports).
* `af_sandbox_revenue` = actual product price (so the correct revenue is attributed).
* `af_validated` **= true**. If `false` go back and verify the store key.
* `af_validation_type` **=** `receipt_validation`.

### Test in-app purchase and subscription revenue

**Prerequisites**:

* For iOS, make sure that under App Store Server Notifications in App Store connect, the AppsFlyer endpoint is configured as your **Sandbox Server URL**.

  [![](https://files.readme.io/1d967de84fb2e506879e444cf04957556fc17b039a1b719467327afd18916fa6-42158637600785.png)](https://files.readme.io/1d967de84fb2e506879e444cf04957556fc17b039a1b719467327afd18916fa6-42158637600785.png)

**To test in-app purchase and subscription revenue**:

1. Tell your developers to follow their [Android](https://github.com/AppsFlyerSDK/appsflyer-android-purchase-connector#-testing-the-integration), [iOS](https://github.com/AppsFlyerSDK/appsflyer-apple-purchase-connector#-testing-the-implementation-in-sandbox), and [Unity](https://github.com/AppsFlyerSDK/appsflyer-unity-purchase-connector/blob/master/docs/purchaseConnectorUnity.md#testing-the-implementation-in-sandbox) instructions to configure the sandbox environment in the SDK Connector.
2. Make test purchases or start a subscription using [License Tester in Google Play](https://support.google.com/googleplay/android-developer/answer/6062777?hl=en). For iOS, use [TestFlight](https://developer.apple.com/testflight/). **Note**: A subscription product can be tested only once per device. In practice, a device cannot register multiple test purchases of the same subscription. Additional attempts will not be recorded.
3. Make a test refund, subscription renewal, or subscription cancellation event using [License Tester in Google Play](https://support.google.com/googleplay/android-developer/answer/6062777?hl=en) and [TestFlight in iOS](https://developer.apple.com/testflight/). **Note**: If you're testing a subscription product, allow time for AppsFlyer to receive a server notification from the store, which typically occurs within a few minutes after the initial purchase is made.
4. Under the **Verify SDK connector implementation** step, click **Test SDK implementation.** It indicates whether any SDK payloads were successfully received from Purchase Connector in the past 7 days.
5. View that the test events are displayed in one of the following ways:

   * View the event in the [Live event viewer](/docs/testing-the-sdk-integration-for-marketers#view-live-events).

   * View the event data in [My Dashboards - Activity View](/docs/activity-metrics-in-my-dashboards).
6. Verify that the event appears in the AppsFlyer Activity dashboard. In AppsFlyer, go to **Analyze > Activity**, and in the **Activity trend** chart, open the In-app events tab and select the event to test. An auto-renewable subscription purchase is called `af_ars_s2s_sandbox`. The event includes:
   * A revenue value of 0 (so as not to skew real AppsFlyer reports).
   * An `af_sandbox_revenue` parameter that includes the revenue value of the purchased product, ensuring the correct revenue is reported.

## Step 5: Verify and update settings

After you have completed configuring the settings above and saved the last step, you are redirected to the active configuration view, where you can verify or update the following settings:

1. Make sure that the **Verify purchases with the App Store** toggle is turned on**.**
2. Check the following options under **Purchases**:
   * **Prevent duplicate purchases for clean data**: Avoids recording transactions that have already been reported.
   * **Automatically measure refunds, cancellations, and negative revenue**: Measures refund-related events and logs them as negative revenue.
   * **Avoid double-counting revenue from Family Sharing**: Prevents duplicate revenue from Family Sharing. These events are marked with `purchase_ownership_type=FAMILY_SHARED` and report zero revenue.
3. Make sure that the **Measure and attribute revenue for auto-renewing subscriptions** toggle is turned on:
4. The status of the following settings:
   * The **App Store key** setup
   * The **Server notification endpoint**setup
   * Implement & test SDK Connector

## Step 6: Release the app versions with the SDK connector

With everything from the previous steps configured and the AppsFlyer purchase SDK connector integrated into your app, tell your developer to release the app version with the SDK connector integrated.

However, before the developer releases the new app version, make sure that:

* The in-app events you want to capture as an in-app purchase or subscription aren't blocked by one of the Validation Rules you have configured in AppsFlyer.
* Your developer should have any sandbox flags marked as false.

[![](https://files.readme.io/1d967de84fb2e506879e444cf04957556fc17b039a1b719467327afd18916fa6-42158637600785.png)](https://files.readme.io/1d967de84fb2e506879e444cf04957556fc17b039a1b719467327afd18916fa6-42158637600785.png)

Once the app with the SDK connector is released, [in-app purchase](/docs/about-roi360-store-revenue#iaprelated-events-and-parameters) and [subscription events](/docs/about-roi360-store-revenue#subscriptionrelated-events-and-parameters) will be generated and made available across all AppsFlyer dashboards, as well as in aggregated and raw data reports, including [Revenue ETL](/docs/revenue-etl-reports).

**Note:** Events will only be generated for users who have updated to a version of the app that includes the SDK connector. As a result, a discrepancy is expected between the revenue data from the app and the store data until the updated app version is fully adopted.

## Switch to ROI360 Store revenue (from Receipt validation)

If you completed onboarding for Receipt Validation but want to activate the ROI360 Store revenue product, perform the following:

1. In AppsFlyer, from the side menu, open [![](https://files.readme.io/e759a4435ce6a34eaa31454483b3c75fffc2830c8bc575d66d9fd8e7acc76a97-42158637603601.png)](https://files.readme.io/e759a4435ce6a34eaa31454483b3c75fffc2830c8bc575d66d9fd8e7acc76a97-42158637603601.png) **Settings** and under **ROI360** select **Revenue Settings**.
2. Open the **Purchases & subscriptions** tab. A banner appears stating that ROI360 is available but not active.
3. Click **View product comparison** to understand the benefits, including refund attribution, net revenue reporting, and full subscription lifecycle measurement.
4. Click **Activate ROI360.**
5. Perform the **Enable App Store Server Notification** step. For more information, see [Set up App Store server notifications](#step-2-ios-set-up-app-store-server-notifications) or [Set up Google Play server notifications](#step-2-android-set-up-google-play-server-notifications).
6. In the **Purchases & subscriptions** section, verify that the **Product type** is now set to **ROI360**.
7. Review your current SDK setup to ensure it can support the ROI360 Store revenue functionality you need.

> 📘 **Note**
>
> ROI360 Store revenue supports two integration methods: Purchase SDK connector and Validate and Log. Of the two, we recommend using the **Purchase SDK Connector** to benefit from:
>
> * Automatic transaction detection
> * Measurement of revenue from existing subscribers (users subscribed before integration)
> * Support for subscription price changes, ensuring accurate revenue reporting when pricing updates occur.
>
> If you don’t need these capabilities, you can continue using the **Validate and Log** integration instead.
>
> **How to check your SDK integration method**
>
> To confirm whether your app uses the Purchase SDK connector or Validate and Log:
>
> 1. Go to the **Integrate SDK Connector** step.
> 2. Click **Test SDK integration**. You’ll see when the most recent SDK payload was received by AppsFlyer within the past 7 days, and whether it originated from either the **Purchase SDK Connector** or **Validate and Log**.
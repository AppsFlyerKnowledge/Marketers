---
title: "Set up receipt validation"
excerpt: "Learn how to set up receipt validation to measure revenue from in-app purchases and subscriptions, and verify it with the App Store and Google Play."
---
**At a glance:** Receipt validation measures revenue from in-app purchases and subscriptions, and verifies it with the app stores, ensuring accurate Return on Ad Spend (ROAS) results.

## Upgrade to new Receipt validation

The legacy Receipt validation will be shut down on **September 7, 2026**, see [Bulletin: Legacy Receipt validation is deprecated](/docs/bulletin-legacy-receipt-validation-is-deprecated). If your app uses the legacy Receipt validation, migrate to the new one by performing the setup steps below. Before you start, review the key differences and prepare the migration.

### What's new in Receipt validation



| Area | Legacy | New Receipt validation |
| --- | --- | --- |
| SDK method | `validateAndLogInAppPurchase` (legacy/v1) | `validateAndLogInAppPurchase` (v2), same name and new signature on iOS and Android |
| Price and currency input | Passed in the SDK call | Auto-extracted from the store |
| Purchase type | Not required | Mandatory `PurchaseType` parameter (*subscription* or *one-time purchase*) |
| Revenue settings configuration | Not required | Required (Revenue settings page) |
| `af_revenue` value source | Value passed in the SDK call | Gross value returned by the store; any custom value passed in the SDK call lands in the event's `custom_data` object |
| Purchase event granularity | Single `af_purchase` event for all transaction types | Distinct events per transaction type: `af_purchase`, `af_ars_trial_started`, `af_ars_subscription_started`, and sandbox variants |
| StoreKit 2 support (iOS) | Not supported | Supported |
| Fraud filtering | Limited | Improved on Android and iOS |
| SDK availability | Removed from AppsFlyer SDK v7.0.0+ | Available from Android v6.17.5, iOS v6.17.8, and plugins v6.17.8 onward |
| Validated purchase event recording | Supported until September 7, 2026 | Ongoing |



### Prepare the migration

Before starting the migration, review the following considerations:

* **Migrate gradually without disrupting existing users.** Enabling the new Receipt validation in the AppsFlyer dashboard does not affect app versions still using the legacy method. Both continue to work until the legacy sunset on September 7, 2026.
* **Expect revenue changes after migration.** The new Receipt validation uses the gross value returned by the store, whereas the legacy Receipt validation used the revenue value passed in the SDK call. If the SDK call passed a non-gross value, dashboards and partner postbacks, now reflecting gross values, will show a different number after migration. For net revenue, use **ROI360 Store Revenue** instead, see [Set up ROI360 store revenue](/docs/set-up-roi360-store-revenue).
* **Inform your UA partners about the revenue change.** Ad networks that used to ingest non-gross revenue from the `af_purchase` postback will see different values after migration.
* **Plan your app release timeline.** After September 7, 2026, users on app versions built with SDK versions earlier than Android v6.17.5 or iOS v6.17.8 will stop generating validated `af_purchase` events. Ship your new app version with enough lead time to reach the majority of your user base before the sunset.

### Switch to ROI360 Store Revenue

Switching to ROI360 Store Revenue does not require an SDK change, since both products use the same `validateAndLogInAppPurchase` (v2) method. Adding the Purchase Connector for automatic purchase detection is optional.

For more information and setup instructions, see [Set up ROI360 store revenue](/docs/set-up-roi360-store-revenue).

## Overview

> 📘 **Note**
>
> For more information about Receipt validation, including how it works and how to enable it in AppsFlyer, see [About Receipt validation](/docs/about-receipt-validation).


To set up Receipt validation, complete the following steps in order:

1. Set up store credentials (iOS and Android)
   * [iOS](#step-1-ios-set-up-app-store-connect-keys)**:** Configure App Store Connect keys (In-App Purchase key, Key ID, and Issuer ID) in AppsFlyer to enable Receipt validation.
   * [Android](#step-1-android-set-up-service-account-key-and-permissions)**:** Configure a Google Cloud service account, set the required permissions in Google Play Console, and upload the service account JSON key to AppsFlyer.
2. [Implement the validateAndLog SDK API](#step-2-implement-sdk): Prepare developers to integrate the AppsFlyer `validateAndLog` SDK API and configure the sandbox environment for testing.
3. [Test validateAndLog SDK API implementation](#step-3-verify-sdk-implementation): Perform sandbox test purchases and subscriptions on iOS and Android to verify that Receipt validation events are generated and correctly recorded by AppsFlyer.
4. [Verify and update settings](#step-4-verify-and-update-settings): Confirm that the product type is set to Receipt validation and review store key and SDK integration statuses to ensure accurate, ongoing revenue measurement.
5. [Release the app versions with the validateAndLog SDK API](#step-5-release-the-app-versions-with-the-validateandlog-sdk-api): Release updated app versions with the `validateAndLog` SDK API integrated, ensuring sandbox flags are disabled and required in-app events are not blocked by validation rules.

## Step 1 (iOS) Set up App Store Connect keys

In step 1, obtain the following credentials from *App Store Connect* and enter them on the **Revenue Settings** page in the AppsFlyer platform.

* In-App Purchase key
* Key ID
* Issuer ID

**Before you start**:

* Setting the credentials involves steps performed in both App Store Connect and AppsFlyer. During setup, keep both the App Store Connect and AppsFlyer tabs open.
* Your iOS app requires StoreKit v1or v2, which provides the framework for handling in-app purchases and subscriptions.

### 1.1 Create the App Store Connect keys

To set iOS credentials, follow these steps:

1. In App Store Connect, go to **Users and Access**.

   [![](https://files.readme.io/e47db4ee7ea526c9d0154614a1685d4553257e203de86144a9ba34616c5a9f9d-42144939159313.png)](https://files.readme.io/e47db4ee7ea526c9d0154614a1685d4553257e203de86144a9ba34616c5a9f9d-42144939159313.png)
2. Go to **Users and Access**> **Integrations**, and from the **Keys**list, select **In-App Purchase**.

   [![](https://files.readme.io/f29bb10190a7dff35bddf0b1736202b439a9238925187eaef4247565f00f8805-42144939163025.png)](https://files.readme.io/f29bb10190a7dff35bddf0b1736202b439a9238925187eaef4247565f00f8805-42144939163025.png)
3. Click **+** to generate a new In-App Purchase key.

   [![](https://files.readme.io/0495e6793159e14fb1b27169665493cd0b8950228ebb859e3442f1024be58222-42144939165073.png)](https://files.readme.io/0495e6793159e14fb1b27169665493cd0b8950228ebb859e3442f1024be58222-42144939165073.png)
4. Enter a name for your API key.
5. Click **Generate**.
6. Click **Download In-App Purchase Key**next to the key you just generated to download it. **Note**: You can only download the key once.
7. Copy the **Key ID** of the key you just generated and paste it into the AppsFlyer purchases & subscriptions setting for **Key ID**.

   [![](https://files.readme.io/50532c20938f84526077f747300a874af51b691fac803368a9d2327aa64a6c48-42144939166097.png)](https://files.readme.io/50532c20938f84526077f747300a874af51b691fac803368a9d2327aa64a6c48-42144939166097.png)
8. Copy the **Issuer ID**. **Note**: If the **Issuer ID** is not displayed at the top of the page, create an App Store Connect API key (with any access level). After that, the Issuer ID appears at the top of the page for the In-App Purchase key.

   [![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)

### 1.2 Set the App Store Connect key

1. Enable Receipt validation. #enable-receipt-validation
2. Under the **App Store Connect keys** step, click [![](https://files.readme.io/962b88087a7109e6131124969c8571df8574e8a6839f4498c176d7c161906c40-42138428770705.png)](https://files.readme.io/962b88087a7109e6131124969c8571df8574e8a6839f4498c176d7c161906c40-42138428770705.png)  **Upload** in the **In-App Purchase key**field to upload the p8 file.
3. In the section titled **App Store Connect keys**, paste the values you copied from App Store Connect.

   * **Key ID**
   * **Issuer ID**
4. Click **Validate keys** to ensure the keys you entered are correct. **Note**: The **Validate keys** action may not work if your app has not yet been published in the App Store.
5. Click **Save and Next**.

## Step 1 (Android). Set up service account key and permissions

In step 1, obtain the following credentials from *Google Play* and *Google Cloud* and enter them on the **Revenue Settings** page in the AppsFlyer platform.

**Before you start**:

* Setting up in-app purchase and subscription revenue measurement involves steps performed in the [Google Cloud Platform](https://cloud.google.com/), [Google Play Console,](https://play.google.com/console/) and the [AppsFlyer UI](https://hq1.appsflyer.com/auth/login). We recommend keeping tabs on all three places open throughout the setup.
* Setup in the AppsFlyer UI requires admin permissions.

### 1.1 Link your Google Play Developer account to your Google Cloud project

**Prerequisites**: Access to Google Play Console and a Google Cloud project.

**To link your Google Play Developer account to your Google Cloud project, follow these steps**:

1. In the Google Play Console, go to your Google Play Developer account.
2. Link the account to your Google Cloud project. For instructions, see this [Google help topic](https://developers.google.com/android-publisher/getting_started#linking).
3. Enable the Google Play Developer API. For instructions, see [this Google help topic](https://developers.google.com/android-publisher/getting_started#enable).

   [![](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)

### 1.2 Configure your service account in the Google Cloud platform

**Prerequisites**: Access to Google Cloud platform.

**To configure your service account, follow these steps**:

1. Create or locate the **service account**:

   1. Go to the **Service Accounts** section in the Google Cloud platform and click **CREATE SERVICE ACCOUNT**.[![](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)
   2. Complete the service account details.[![](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)
   3. Copy the email address.[![](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)
   4. Click **Create and continue**.[![](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)
   5. In the **Grant this service account access to the project**step, select the **Pub/Sub** subscriber role.[![](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)
   6. Click **Continue**> **Done**.

      [![](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)
2. Download the service account private key:

   1. In the Google Cloud platform, go to the **Service accounts** section, find the account you want (the one you just created) in the list, and click the **More actions** icon.
   2. Click **Manage keys**.[![](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)
   3. Click **Add key** > **Create new key**.

      [![](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)
   4. In the **Create private key** popup, under **Key type**, select **JSON**, and click **Create**.[![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)
   5. Click **Create**. The private key JSON file is downloaded.

      [![](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)
   6. Save the JSON key file, which you will upload to AppsFlyer later. **Note**! You must save the key. it can't be retrieved later. If you don't save it, you must create an entirely new key.

### 1.3 Set API access permissions in Google Play Console

**Prerequisites**: Access to Google Play Console.

**Note**: It can take time (sometimes up to 24 hours) after setting service account credentials and permissions to be able to use them. This may cause you to receive errors in later steps.

**To set API access permissions in Google Play Console**:

1. In the Google Play Console, go to **Users and permissions**, find the service account you created, and click **Invite new users**.

   [![](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)
2. Enter the **Email address** that you copied when you configured your service account in step 1.2.1.3.

   [![](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)
3. In the **Permissions** section, go to the **Account permissions** tab, and select both:

   * View financial data, orders, and cancellation survey responses.
   * Manage orders and subscriptions.[![](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)
4. On the **App permissions** tab, click **Add app,**then select your app. Add multiple apps if needed.

   [![](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)
5. Click **Invite user**.

   [![](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)
6. In the confirmation popup, click **Send invite**.

   [![](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)

### 1.4 Upload the service account private key to AppsFlyer

Upload and validate the Google JSON key you downloaded in [step 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).

**Prerequisites**: Admin access to AppsFlyer.

**To upload the service account private key to AppsFlyer, follow these steps**:

1. [Activate Receipt validation](/docs/about-receipt-validation#enable-receipt-validation)[.](/docs/about-receipt-validation#enable-receipt-validation)
2. Under the **Service Account Key and Permissions** step, in the **Upload Google JSON key**field, click [![](https://files.readme.io/962b88087a7109e6131124969c8571df8574e8a6839f4498c176d7c161906c40-42138428770705.png)](https://files.readme.io/962b88087a7109e6131124969c8571df8574e8a6839f4498c176d7c161906c40-42138428770705.png)  **Upload**.
3. Upload the JSON file you downloaded in [step 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).
4. Click **Validate key**.**Note:**

   * After setting service account credentials and permissions, it can take up to 24 hours to be able to use them. This may cause you to receive errors when trying to validate the key or perform a validation test.
   * To work around the 24-hour wait time, in the Google Play Console, navigate to any application, then go to **Monetize** > **Products** > **Subscriptions/In-app products**, and make a change. For example, edit the description of your product and save it. This usually updates the account credentials and permissions immediately. You can then undo the changes.
5. Click **Next**. The **SDK implementation** step is opened.

## Step 2. Implement SDK

In this step, you prepare your developers to integrate the SDK `validateAndLog` API, and set up a sandbox environment for testing. The minimum SDK versions that support the latest `validateAndLog` API are **6.17.5** for Android and **6.17.8** for iOS.

To implement the validateAndLog SDK API, follow these steps:

1. In the **SDK implementation** step, copy the **pre-written message** displayed in the dashboard.
2. Send it to your developers. it includes:

   * The app name and App ID
   * A link to [the SDK integration guide](https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation).
   * Instructions to configure the sandbox environment (`sandbox = true`).
   * Testing steps (using **TestFlight**).

   This message provides all the information your developers need to complete the integration and begin testing.
3. Click **Next**. The **Verify SDK implementation** step is opened.

## Step 3. Verify SDK implementation

Test the in-app purchase and subscription revenue integration in a sandbox environment to confirm that the SDK connector is correctly integrated and that server notifications are properly configured and received by AppsFlyer.

### Test SDK implementation

To check whether AppsFlyer has received valid `validateAndLog` payloads from your app in the last 7 days, perform these steps:

1. In the **Verify SDK implementation** step, click **Test SDK implementation**.
2. Review the results, including the timestamp of the most recent payload received by AppsFlyer. Note that this check only confirms that requests are reaching AppsFlyer and does not verify data completeness or correctness.
3. To fully validate the implementation, continue with the testing steps below.

### Sandbox environment considerations

In a sandbox environment:

* Only initial purchase events cause the validateAndLog SDK API to produce an event that is recorded by AppsFlyer. An in-app purchase event is called `af_purchase_sandbox_sdk`. A subscription event is called `af_ars_sandbox_sdk`**.**
* Sandbox events have a revenue of 0.
* For Android, tests performed by License Testers result in sandbox events even if the sandbox environment in the SDK isn't configured.

### Test in-app purchase and subscription revenue

[![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

**To test in-app purchase and subscription revenue**:

1. Tell your developers to follow their instructions to configure the sandbox environment for the validateAndLog SDK API.
2. Make a test purchase or subscription with [License Tester in Google Play](https://support.google.com/googleplay/android-developer/answer/6062777?hl=en) and [TestFlight in iOS](https://developer.apple.com/testflight/).
3. View that the test events are displayed in one of the following ways:

   * View the event in the [Live event viewer.](/docs/testing-the-sdk-integration-for-marketers#view-live-events)
   * View the event data in [My Dashboards - Activity View](/docs/activity-metrics-in-my-dashboards).
4. Look for the following test events:

   * The `af_purchase_sandbox_sdk` for a purchase event.
   * The `af_ars_sandbox_sdk` for a subscription event.
5. Make sure that the test events include the following:

   * A revenue value of **0** (so as not to skew real AppsFlyer reports).
   * An `af_sandbox_revenue` parameter that includes the revenue value of the product purchased, ensuring the correct revenue is reported.
   * An `af_validated` parameter is `true`. If `af_validated` is `false` - get back to step 2 above and validate the key provided from the store
   * An `af_validation_type` parameter is `receipt_validation`.

## Step 4. Verify and update settings

After you have completed configuring the settings above and saved the above steps, you are redirected to the active configuration view, where you can verify or update the following settings:

1. Verify that the **Product type** is **Receipt validation**
2. Make sure that **Verify purchases with the App Store** is turned on**.**
3. Verify or update the following settings:

   * The **App Store key** setup
   * The **SDK integration**setup

## Step 5. Release the app versions with the validateAndLog SDK API

With everything from the previous steps configured and the AppsFlyer validateAndLog SDK API integrated into your app, tell your developers to release the app version with the validateAndLog SDK API integrated.

Before the developers release the new app version, make sure that:

* The in-app events you want to capture as an [in-app purchase or subscription](/docs/about-receipt-validation#inapp-purchase-events-and-parameters-for-receipt-validation) aren't blocked by any of the validation rules you have configured in AppsFlyer.
* Your developers have all sandbox flags set to `false`.

[![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

Once the app with the validateAndLog SDK API is released, [in-app purchase and subscription events](/docs/about-receipt-validation#inapp-purchase-events-and-parameters-for-receipt-validation) are generated and made available across all AppsFlyer dashboards, as well as in aggregated and raw data reports.

Events are only generated for users who have updated to a version of the app that includes the validateAndLog SDK API. As a result, a discrepancy between the revenue data from the app and the store data is expected until the updated app version is fully adopted.
---
title: "Set up ROI360 store revenue"
excerpt: "Learn how to configure the AppsFlyer ROI360 store revenue solution, including store credentials, server notifications, and SDK connector implementation."
---
At a glance: Set up the AppsFlyer ROI360 store revenue solution.

> ❗️ Important!
>
> ROI360 store revenue is available only to customers on the ROI360 premium plan. To check your plan or upgrade, contact your Customer Success Manager (CSM).

## Overview

> 📘 Note
>
> For more information about ROI360, including how it works and how to enable it in AppsFlyer, see [About ROI360 Store revenue](https://support.appsflyer.com/hc/articles/42138855425297--WIP-About-ROI360-store-revenue).

To set up ROI360 Store Revenue, complete the following steps in order:

1. Set up store credentials (iOS and Android):
   - [iOS :](/docs/set-up-roi360-store-revenue#step-1-ios-set-up-app-store-connect-keys) Configure App Store Connect keys (In-App Purchase key, Key ID, and Issuer ID) in AppsFlyer.
   - [Android](/docs/set-up-roi360-store-revenue#step-1-android-set-up-service-account-key-and-permissions) : Configure a Google Cloud service account, set the required permissions in Google Play Console, and upload the service account JSON key to AppsFlyer.
2. Configure server notifications (iOS and Android):
   - [iOS](/docs/set-up-roi360-store-revenue#step-2-ios-set-up-app-store-server-notifications) : Set up App Store Server Notifications, either by sending notifications directly to AppsFlyer (recommended) or by forwarding them from your own endpoint, and validate the integration.
   - [Android](/docs/set-up-roi360-store-revenue#step-2-android-set-up-google-play-server-notifications) : Set up Google Play real-time developer notifications (RTDN), either by allowing Google Play to send notifications directly to AppsFlyer (recommended) or by forwarding them via Pub/Sub.
3. [Implement the SDK Connector](/docs/set-up-roi360-store-revenue#step-3-implement-sdk-connector): Prepare developers to integrate the AppsFlyer Purchase SDK Connector.
4. [Verify SDK implementation](/docs/set-up-roi360-store-revenue#step-4-verify-sdk-implementation): Test sandbox in-app purchases and subscriptions on both platforms to confirm that SDK events and server notifications are correctly received and processed by AppsFlyer.
5. [Verify and update settings](/docs/set-up-roi360-store-revenue#step-5-verify-and-update-settings): Review and confirm the statuses of purchase validation, refund handling, subscription measurement, and store integration to ensure accurate, ongoing revenue attribution across platforms.
6. [Release app versions](/docs/set-up-roi360-store-revenue#step-6-release-the-app-versions-with-the-sdk-connector): Release updated app versions with the SDK Connector integrated, ensuring sandbox flags are disabled and validation rules allow the required revenue events.

## Step 1 (iOS): Set up App Store Connect Keys

In step 1, obtain the following credentials from App Store Connect and input them in the Revenue Settings page within the AppsFlyer platform.

- In-App Purchase key
- Key ID
- Issuer ID

**Before you start**:

Setting the credentials involves steps performed in both App Store Connect and AppsFlyer. During setup, keep both the App Store Connect and AppsFlyer tabs open.

### 1.1 Create the App Store Connect keys

To set iOS credentials, follow these steps:

1. In the App Store Connect, go to **Users and Access**
2. Go to **Users and Access** > **Integrations**, and from the **Keys** list, select **In-App Purchase**.
3. Click **+** to generate a new In-App Purchase key.
4. Enter a name for your API key.
5. Click **Generate**.
6. Click **Download In-App Purchase Key** next to the key you just generated to download it. **Note**: You can only download the key once.
7. Copy the **Key ID** of the key you just generated and paste it into the AppsFlyer purchases & subscriptions setting for **Key ID**.
8. Copy the **Issuer ID**. **Note**: If the **Issuer ID** is not displayed at the top of the page, create an App Store Connect API key (with any access level). After that, the Issuer ID will appear at the top of the page for the In-App Purchase key.

### 1.2 Set the App Store Connect key in AppsFlyer

1. [Enable ROI360 Store revenue](https://support.appsflyer.com/hc/articles/42138855425297--WIP-About-ROI360-Store-revenue#enable-roi360-store-revenue).
2. Under the **App Store Connect keys** step, click Upload in the **In-App Purchase key** field to upload the p8 file.
3. In the section titled **App Store Connect keys**, paste the values you copied from App Store Connect.
   - **Key ID**
   - **Issuer ID**
4. Click **Validate keys** to ensure the keys you entered are correct. **Note**: The Validate key may not work if your app has not yet been published in the App Store.
5. Click **Save and next**

## Step 1 (Android): Set up service account key and permissions

In step 1, you can obtain the following credentials from App Store Connect and input them in the Revenue Settings page within the AppsFlyer platform.

**Before you start**:

- Setting up in-app purchase and subscription revenue measurement involves steps performed in the [Google Cloud Platform](https://cloud.google.com/), [Google Play Console](https://play.google.com/console/), and the [AppsFlyer UI](https://hq1.appsflyer.com/auth/login). We recommend keeping tabs on all three places open throughout the setup.
- Setting up in the AppsFlyer UI requires admin permissions.

### 1.1. Link your Google Play Developer Account to your Google Cloud Project

**Prerequisites**: Access to Google Play Console and Google Cloud Project.

**To link your Google Play Developer Account to your Google Cloud Project, follow these steps**:

1. In the Google Play Console, go to your Google Play Developer Account.
2. Link the account to your Google Cloud project. For instructions, see this [Google help topic](https://developers.google.com/android-publisher/getting_started#linking).
3. Enable the Google Play Developer API. For instructions, see [this Google help topic](https://developers.google.com/android-publisher/getting_started#enable).

### 1.2. Configure your Service Account in the Google Cloud Platform

**Prerequisites**: Access to Google Cloud Platform.

**To configure your service account, follow these steps**:

1. Create or locate the **Service Account**:
   1. Go to the **Service accounts** section in the Google Cloud Platform and click **Create Service Account**.
   2. Complete the service account details.
   3. Copy the email address.
   4. Click **Create and continue**.
   5. In the **Grant this service account access to the project** step, select the **Pub/sub** subscriber role.
   6. Click **Continue** > **Done**.
2. Download the **Service Account Private Key**:
   1. In the Google Cloud Platform, go to the **Service accounts** section, find the account you want (the one you just created) from the list, and click the **More actions** icon.
   2. Click **Manage keys**.
   3. Click **Add key** > **Create new key**.
   4. In the **Create private key** popup, under **Key type**, select **JSON**, and click **Create**.
   5. Click **Create**. The private key JSON file is downloaded.
   6. Save the JSON key file, which will be uploaded to AppsFlyer later. **Note**: You must save the key; it can't be retrieved later. If you don't save it, you will have to create an entirely new key.

### 1.3. Set API access permissions in Google Play Console

**Prerequisites**: Access to Google Play Console.

> 📘 Note
>
> It can take time (sometimes even 24 hours) after setting service account credentials and permissions to be able to use them. This may cause you to receive errors in later steps.

**To set API access permissions in Google Play Console**:

1. In the Google Play Console, go to **Users and permissions**, find the service account you created, and click **Invite new users**.
2. Enter the **Email address** that you copied when you configured your service account in step 1.2.1.3.
3. In the **Permissions** section, go to the **Account permissions** tab, and select both:
   - View financial data, orders, and cancellation survey responses.
   - Manage orders and subscriptions.
4. On the **App permissions** tab, click **Add app,** then select your app. Add multiple apps if needed.
5. Click **Invite user.**
6. In the confirmation popup, click **Send invite**.

### 1.4. Upload the Service Account Private Key to AppsFlyer

Upload and validate the Google JSON key you downloaded in [step 1.2](/docs/set-up-roi360-store-revenue#12-configure-your-service-account-in-the-google-cloud-platform).

**Prerequisites**: Admin access to AppsFlyer.

**To upload the Service Account Private Key to AppsFlyer, follow these steps**:

1. [Enable ROI360 Store revenue](https://support.appsflyer.com/hc/articles/42138855425297--WIP-About-ROI360-Store-revenue#enable-roi360-store-revenue).
2. Under the **Service Account Key and Permissions** step, in the **Upload Google JSON key** field, click the upload icon.
3. Upload the JSON file you downloaded in [step 1.2](/docs/set-up-roi360-store-revenue#12-configure-your-service-account-in-the-google-cloud-platform).
4. Click **Validate Key.** 

> 📘 Note
>
> - After setting service account credentials and permissions, it can take up to 24 hours to be able to use them. This may cause you to receive errors when trying to validate the key or perform a validation test.
> - To work around the 24-hour wait time, in the Google Play Console, navigate to any application, then go to **Monetize** > **Products** > **Subscriptions/In-app products**, and make a change. For example, edit the description of your product and save it. This should instantly update the account credentials and permissions. You can then undo the changes.

5. Click **Save and Next**.

## Step 2 (iOS): Set up App Store server notifications

Set how App Store notifications are received in AppsFlyer.

- If you already have an App Store server notifications endpoint configured in App Store Connect (for example, your own backend or another service), choose between **Option 1 (recommended)** or **Option 2**.
- If you have not yet configured an endpoint in App Store Connect, choose **Option 1**.

#### Option 1 (Recommended) - AppsFlyer as the primary endpoint

Replace the existing App Store Connect notification URL with the AppsFlyer endpoint, and add your previous endpoint in AppsFlyer as a forwarding destination. Your current subscription logic and workflows remain unchanged and continue to function as expected.

The notification flow for this option is as follows:

1. App Store Connect sends notifications to AppsFlyer
2. AppsFlyer processes them for ROI360
3. AppsFlyer forwards all notifications to your existing endpoint **in real time**

To use this option, complete steps [2.1](/docs/set-up-roi360-store-revenue#21-copy-the-appsflyer-server-notifications-endpoint), [2.2](/docs/set-up-roi360-store-revenue#22-send-notifications-directly-to-appsflyer), and [2.4](/docs/set-up-roi360-store-revenue#24-test-the-server-notifications-integration).

#### Option 2 - Your endpoint as the primary endpoint

If you prefer to keep your existing endpoint as the primary destination, configure your server to forward App Store server notifications to AppsFlyer.

To use this option, skip steps 2.1, 2.2 and complete steps [2.3](/docs/set-up-roi360-store-revenue#23-[optional]-forward-notifications-from-your-endpoint-to-appsflyer) and [2.4](/docs/set-up-roi360-store-revenue#24-test-the-server-notifications-integration)

> 📘 Note
>
> Apple supports only one App Store server notification endpoint per app, and sends all notification types to it, not only purchase and subscription notifications. AppsFlyer uses the purchase and subscription notifications to measure revenue. It acknowledges any other type back to Apple, so Apple stops retrying, but does not process or act on it.
>
> If your app relies on notification types beyond purchases and subscriptions (for example, consent notifications), make sure those notifications reach your own server:
>
> - **Option 1:** Keep AppsFlyer as the primary endpoint and enable forwarding (step 2.1). AppsFlyer forwards a copy of all notifications to your endpoint in real time, unchanged from how Apple sent them, including the types AppsFlyer does not process.
> - **Option 2:** Keep your own endpoint as the primary destination, so your server receives and handles all notification types directly, and forward purchase and subscription notifications to AppsFlyer.

### 2.1 Copy the AppsFlyer server notifications endpoint

To copy the AppsFlyer server notifications endpoint, follow these steps:

1. **In AppsFlyer,** in the **App Store server notifications** step, copy the AppsFlyer server notifications endpoint.
2. If you previously had another App Store server notifications endpoint and want AppsFlyer to forward notifications to it, select **Forward a copy of notifications to your server (relevant for option 1 only).**
3. Enter your notification forwarding endpoint in the displayed text box.

### 2.2 Send notifications directly to AppsFlyer

To send notifications directly to AppsFlyer, set up AppsFlyer as the primary App Store server notifications endpoint.

1. In **App Store Connect**, in the **App Information** section, scroll to **App Store Server Notifications**, and next to **Production Server URL**, click **Edit**.
2. Paste [the AppsFlyer server notifications endpoint copied from AppsFlyer](/docs/set-up-roi360-store-revenue#21-copy-the-appsflyer-server-notifications-endpoint), select **Version 2 Notifications**, and click **Save**. **Note:** Version 1 notifications are no longer supported. If the notification-version selector does not appear in Apple Store Connect, it means you are already using Version 2.
3. In the **App Information** section, scroll to **App Store Server Notifications**, and next to **Sandbox Server URL**, click **Edit**.
4. Paste [the AppsFlyer server notifications endpoint copied from AppsFlyer](/docs/set-up-roi360-store-revenue#21-copy-the-appsflyer-server-notifications-endpoint), select **Version 2 Notifications**, and click **Save**. **Note:** Version 1 notifications are no longer supported. If the notification-version selector does not appear in Apple Store Connect, it means you are already using Version 2.

### 2.3 [Optional] Forward notifications from your endpoint to AppsFlyer

Use this step only if you want to keep your endpoint as the primary destination for App Store server notifications, instead of sending notifications directly to AppsFlyer.

This option is not the recommended setup and requires backend implementation. If you already configured AppsFlyer as the primary endpoint in step **2.2** above, skip this step.

To forward server notifications from your endpoint to AppsFlyer, follow these steps:

1. In **App Store Connect**, in the **App Information** section, scroll to **App Store Server Notifications**, and next to **Production Server URL**, click **Edit**.
2. Paste **your server endpoint URL**.
3. Select **Version 2 Notifications. Note:** Version 1 notifications are **no longer supported**. If the notification-version selector does not appear in Apple Store Connect, it means you are already using Version 2.
4. Click **Save**.
5. In **App Store Connect**, in the **App Information** section, scroll to **App Store Server Notifications**, and next to **Sandbox Server URL**, click **Edit**.
6. Paste **your server endpoint URL**.
7. Select **Version 2 Notifications. Note:** Version 1 notifications are **no longer supported**.
8. Click **Save**.
9. Configure your backend to forward Apple server notifications to the AppsFlyer notification endpoint URL. The requests must match the App Store payload exactly as received from Apple, see [Apple format requirements](https://developer.apple.com/documentation/appstoreserverapi/signedpayload#discussion).

### 2.4 Test the server notifications integration

To confirm that AppsFlyer is receiving App Store server notifications correctly, or if you recently configured the endpoint and no server notifications have arrived yet:

1. In AppsFlyer, go to the **App Store server notifications** step.
2. Click **Test integration**. AppsFlyer sends a test notification request to Apple and checks whether any valid notifications were received from Apple in the past 7 days, and displays one of the following:
   - A confirmation of whether valid notifications were received.
   - A status message indicating that no notifications were found.

> 📘 Note
>
> Apple may take a few seconds to send the test message.
>
> - If the status remains invalid, wait a few moments and try again.
> - After the test succeeds, or when you are ready to continue, click **Save and next**.

## Step 2 (Android): Set up Google Play server notifications

To receive in-app purchase and subscription revenue data from Google Play, select between the following options:

- (Recommended) Google Play sends the notifications directly to AppsFlyer. With this option, no notification copies can be forwarded to your endpoint. If you'd like to select this option, you can see [Send Google Play notifications directly to AppsFlyer](/docs/set-up-roi360-store-revenue#21-send-google-play-notifications-directly-to-appsflyer).
- Google Play sends the notifications to you first, which are then forwarded to AppsFlyer. If you choose this option, see [Forward Google Play notifications to AppsFlyer.](/docs/set-up-roi360-store-revenue#22-[optional]-forward-google-play-notifications-to-appsflyer)

**Prerequisites**: Access to Google Play Console and AppsFlyer UI.

### 2.1 Send Google Play notifications directly to AppsFlyer

1. In AppsFlyer, on step 2, **Set up Google Play server notifications**, select **Allow AppsFlyer topic to get RTDN messages directly from Google**.
2. Copy the AppsFlyer topic to the clipboard.
3. In **Google Play Console** > **Home**, select to view your app. The dashboard opens.
4. Go to **Monetize with Play** > **Monetization setup**, and in the **Google Play Billing** section, make sure **Enable real-time notification** is checked.
5. In the **Topic name** field, paste the AppsFlyer topic address you copied.
6. For **Notification content**, select **Subscriptions, voided purchases, and all one-time products**.
7. Click **Save Changes**. It can take time (sometimes even 24 hours) for this to take effect. Therefore, wait before testing.

### 2.2 [Optional] Forward Google Play notifications to AppsFlyer

> 📘 Note
>
> This step is only for when you didn’t choose the recommended method to receive in-app purchase and subscription revenue data from Google Play by sending notifications directly to AppsFlyer. If you completed the steps for the recommended method to create a topic where AppsFlyer directly receives the RTDN notifications from Google Play, skip this step.

If you want to set AppsFlyer as a subscriber to your existing PUB/SUB topic, continue with the instructions below.

**Prerequisites**: Access to Google Cloud Platform and AppsFlyer UI.

**To forward Google Play notifications to AppsFlyer**:

1. In AppsFlyer, from the side menu, go to **Settings** > **Revenue Settings**,
2. Select your app,
3. In the **Purchases & subscriptions** tab, select **Forward your RTDN topic messages to AppsFlyer**.
4. Copy the endpoint URL to the clipboard.
5. In Google Cloud Platform, under your project, search for **Pub/Sub**.
6. In **Pub/Sub** go to the **Topics** section, and verify you have a dedicated pub/sub topic for subscriptions.
7. In **Pub/Sub,** go to the **Subscriptions** section, and click **Create Subscriptions**.
8. Enter the **Subscription ID**.
9. Select the relevant subscription pub/sub topic from the dropdown.
10. For **Delivery type**, select **Push**.
11. Paste the **Endpoint URL** that you copied from AppsFlyer.
12. Under **Expiration period**, select **Never expire**.
13. Click **Create**.
14. Go to the **Subscriptions** section and click into the Topic name you want.
15. Copy the topic name to the clipboard.
16. In **Google Play Console**, go to **Monetize with Play** > **Monetization setup.** and in the **Google Play Billing** section, paste the topic name that you copied in the previous step in the Topic name field.
17. For **Notification content**, select **Subscriptions, voided purchases, and all one-time products**.
18. Click **Save changes**. It can take time (sometimes even 24 hours) for this to take effect. Therefore, wait before testing.

### 2.3 Send a test notification from Google Play Console

To verify that Google Play real-time developer notifications (RTDN) are correctly received by AppsFlyer, send a test notification from Google Play Console:

1. Click **Send test notification**. This sends a test RTDN message to the Pub/Sub topic configured for AppsFlyer.
<Image src="https://files.readme.io/4d7aa79eb963373223cfde1d32db16b739119a86d8d4f0cf6ce026d42a709bf3-42170040528657.png" alt="Send test notification" />
2. Under **Google Play Billing**, locate the Topic name section.
3. In the left menu, navigate to **Monetise with Play** → **Monetisation setup**.
4. Go to the Google Play Console.

### 2.4 Confirm notification delivery in AppsFlyer

1. When the test succeeds, or when you're ready to proceed, click **Save and next**.
2. Result: AppsFlyer displays whether any notifications were received in the last 7 days.
   - If successful, the interface shows the date and time of the most recent notification.
   - If none were received, the interface indicates that no notifications were found in the last 7 days.
   - If no status appears, review your Pub/Sub configuration and resend the test notification.
3. In the **Google Play Server Notifications** step, click **Test integration**.

## Step 3: Implement SDK Connector

In this step, you’ll prepare your developers to integrate the AppsFlyer Purchase SDK Connector and configure the sandbox environment for testing.

To implement the SDK connector, follow these steps:

1. In the **Implement SDK Connector** step, copy the **pre-written message** displayed in the dashboard.
2. Send it to your developers. It includes:
   - The app name and App ID
   - A link to [the SDK integration guide](https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation).
   - Instructions to configure the sandbox environment (`sandbox = true`)
   - Testing steps (using **TestFlight**)

This message provides all the information your developers need to complete the integration and begin testing.

> 📘 Note
>
> The connector uses automatic transaction detection. As an alternative, you can implement the `validateAndLog` SDK method to manually log each transaction. This method does not support all features available with the connector. For details on both SDK integration options, see [the DevHub documentation](https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation).

## Step 4: Verify SDK implementation

Test the in-app purchase and subscription revenue integration in a sandbox environment to confirm that the SDK connector is correctly integrated and that server notifications are properly configured and received by AppsFlyer.

### Test SDK implementation

To check whether AppsFlyer has received valid purchase and subscription event payloads from your app in the last 7 days, perform these steps:

1. In the **Verify SDK implementation** step, click **Test SDK implementation**.
2. Review the results, including the timestamp of the most recent payload received by AppsFlyer.

> 📘 Note
>
> This test only confirms that requests are reaching AppsFlyer and does not verify the completeness or correctness of the data.

3. To fully validate the implementation, continue with the testing steps below.

### Sandbox events and parameters

- The SDK connector generates events only for the initial sandbox transaction:
  - In-app purchase: `af_purchase_sandbox_sdk`
  - Subscription: `af_ars_sandbox_sdk`
- AppsFlyer processes server notifications only if the SDK event for the original transaction was recorded.
  - In-app purchase S2S: `af_purchase_sandbox_s2s`
  - Subscription S2S: `af_ars_sandbox_s2s`
- If the SDK never records the original transaction, no S2S event is created.

**iOS considerations**

- If `af_purchase_sandbox_sdk` includes `af_sandbox_revenue`, it maps to a production `af_purchase`.
- If no revenue is present, it maps to a production `af_purchase_free`.

**Android considerations**

- Purchases by **License Testers** always generate sandbox events, even if sandbox mode isn’t configured in the SDK.

**Required parameters for test events**

Ensure that every sandbox purchase event includes:

- **Revenue = 0** (to avoid affecting real reports).
- `af_sandbox_revenue` = actual product price (so the correct revenue is attributed).
- `af_validated` **= true**. If `false` go back and verify the store key.
- `af_validation_type` **=** `receipt_validation`.

### Test in-app purchase and subscription revenue

**Prerequisites**:

- For iOS, make sure that under App Store Server Notifications in App Store connect, the AppsFlyer endpoint is configured as your **Sandbox Server URL**.

**To test in-app purchase and subscription revenue**:

1. Tell your developers to follow their [Android](https://github.com/AppsFlyerSDK/appsflyer-android-purchase-connector#-testing-the-integration), [iOS](https://github.com/AppsFlyerSDK/appsflyer-apple-purchase-connector#-testing-the-implementation-in-sandbox), and [Unity](https://github.com/AppsFlyerSDK/appsflyer-unity-purchase-connector/blob/master/docs/purchaseConnectorUnity.md#testing-the-implementation-in-sandbox) instructions to configure the sandbox environment in the SDK Connector.
2. Make test purchases or start a subscription using [License Tester in Google Play](https://support.google.com/googleplay/android-developer/answer/6062777?hl=en). For iOS, use [TestFlight](https://developer.apple.com/testflight/). **Note**: A subscription product can be tested only once per device. In practice, a device cannot register multiple test purchases of the same subscription. Additional attempts will not be recorded.
3. Make a test refund, subscription renewal, or subscription cancellation event using [License Tester in Google Play](https://support.google.com/googleplay/android-developer/answer/6062777?hl=en) and [TestFlight in iOS](https://developer.apple.com/testflight/). **Note**: If you're testing a subscription product, allow time for AppsFlyer to receive a server notification from the store, which typically occurs within a few minutes after the initial purchase is made.
4. Under the **Verify SDK connector implementation** step, click **Test SDK implementation.** It indicates whether any SDK payloads were successfully received from Purchase Connector in the past 7 days.
5. View that the test events are displayed in one of the following ways:
   - View the event in the [Live event viewer](/docs/testing-the-sdk-integration-for-marketers#view-live-events).
   - View the event data in [My Dashboards - Activity View](/docs/activity-metrics-in-my-dashboards).
6. Verify that the event appears in the AppsFlyer Activity dashboard. In AppsFlyer, go to **Analyze > Activity**, and in the **Activity trend** chart, open the In-app events tab and select the event to test. An auto-renewable subscription purchase is called `af_ars_s2s_sandbox`. The event includes:
   - A revenue value of 0 (so as not to skew real AppsFlyer reports).
   - An `af_sandbox_revenue` parameter that includes the revenue value of the purchased product, ensuring the correct revenue is reported.

## Step 5: Verify and update settings

After you have completed configuring the settings above and saved the last step, you are redirected to the active configuration view, where you can verify or update the following settings:

1. Make sure that the **Verify purchases with the App Store** toggle is turned on.
2. Check the following options under **Purchases**:
   - **Prevent duplicate purchases for clean data**: Avoids recording transactions that have already been reported.
   - **Automatically measure refunds, cancellations, and negative revenue**: Measures refund-related events and logs them as negative revenue.
   - **Avoid double-counting revenue from Family Sharing**: Prevents duplicate revenue from Family Sharing. These events are marked with `purchase_ownership_type=FAMILY_SHARED` and report zero revenue.
3. Make sure that the **Measure and attribute revenue for auto-renewing subscriptions** toggle is turned on:
4. The status of the following settings:
   - The **App Store key** setup
   - The **Server notification endpoint** setup
   - Implement & test SDK Connector

## Step 6: Release the app versions with the SDK connector

With everything from the previous steps configured and the AppsFlyer purchase SDK connector integrated into your app, tell your developer to release the app version with the SDK connector integrated.

However, before the developer releases the new app version, make sure that:

- The in-app events you want to capture as an in-app purchase or subscription aren't blocked by one of the Validation Rules you have configured in AppsFlyer.
- Your developer should have any sandbox flags marked as false.

Once the app with the SDK connector is released, [in-app purchase](https://support.appsflyer.com/hc/articles/42138855425297--WIP-About-ROI360-store-revenue#iaprelated-events-and-parameters) and [subscription events](https://support.appsflyer.com/hc/articles/42138855425297--WIP-About-ROI360-store-revenue#subscriptionrelated-events-and-parameters) will be generated and made available across all AppsFlyer dashboards, as well as in aggregated and raw data reports, including [Revenue ETL](https://support.appsflyer.com/hc/articles/16464765619985-ROI360-Revenue-ETL-Data-Locker-reports).

**Note:** Events will only be generated for users who have updated to a version of the app that includes the SDK connector. As a result, a discrepancy is expected between the revenue data from the app and the store data until the updated app version is fully adopted.

## Switch to ROI360 Store revenue (from Receipt validation)

If you completed onboarding for Receipt Validation but want to activate the ROI360 Store revenue product, perform the following:

1. In AppsFlyer, from the side menu, open **Settings** and under **ROI360** select **Revenue Settings**.
2. Open the **Purchases & subscriptions** tab. A banner appears stating that ROI360 is available but not active.
3. Click **View product comparison** to understand the benefits, including refund attribution, net revenue reporting, and full subscription lifecycle measurement.
4. Click **Activate ROI360.**
5. Perform the **Enable App Store Server Notification** step. For more information, see [Set up App Store server notifications](/docs/set-up-roi360-store-revenue#step-2-ios-set-up-app-store-server-notifications) or [Set up Google Play server notifications](/docs/set-up-roi360-store-revenue#step-2-android-set-up-google-play-server-notifications).
6. In the **Purchases & subscriptions** section, verify that the **Product type** is now set to **ROI360**.
7. Review your current SDK setup to ensure it can support the ROI360 Store revenue functionality you need.

> 📘 Note
>
> ROI360 Store revenue supports two integration methods: Purchase SDK connector and Validate and Log. Of the two, we recommend using the **Purchase SDK Connector** to benefit from:
>
> - Automatic transaction detection
> - Measurement of revenue from existing subscribers (users subscribed before integration)
> - Support for subscription price changes, ensuring accurate revenue reporting when pricing updates occur.
>
> If you don’t need these capabilities, you can continue using the **Validate and Log** integration instead.

**How to check your SDK integration method**

To confirm whether your app uses the Purchase SDK connector or Validate and Log:

1. Go to the **Integrate SDK Connector** step.
2. Click **Test SDK integration**. You’ll see when the most recent SDK payload was received by AppsFlyer within the past 7 days, and whether it originated from either the **Purchase SDK Connector** or **Validate and Log**.
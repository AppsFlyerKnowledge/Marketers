---
title: "Bulletin: Update App Store credentials for iOS ROI360 receipt validation"
excerpt: "Learn how to update your App Store credentials in AppsFlyer to transition your ROI360 iOS validation flow to Apple's new in-app purchase validation APIs."
---
| **What's new** | AppsFlyer will transition the ROI360 iOS validation flow to Apple's new in-app purchase validation APIs, as the current API is deprecated by Apple.  <br />To ensure your iOS revenue data continues to be validated accurately and in real-time, you’ll need to update your App Store credentials in the AppsFlyer platform.  <br />If your app still uses Apple Server Notifications Version 1, you’ll also be required to switch to Version 2 notifications before updating credentials. |
| --- | --- |
| **Update date** | 02/04/2025 |
| **What you need to know** | This change affects apps using ROI360 for iOS in-app purchase and subscription revenue validation.  <br />By upgrading to the new iOS validation flow, you’ll benefit from:<br /><br />* Enhanced real-time validation with the Apple Store using new Apple endpoints.<br />* No changes to in-app event structure or parameters.<br />* Updated validation result responses in the AppsFlyer Purchase SDK Connector, including a new `store_status` code for failed validations.<br />* No changes to your SDK implementation are required.<br /><br />**Note:** StoreKit 2-based receipt validation is only supported with the new App Store credentials. Make sure to complete the update if your app uses StoreKit 2 to ensure continued validation.<br /><br />Apple may sunset the old API at any time, so we strongly recommend updating your credentials to stay ahead of any potential disruptions. |
| **What you need to do** | To complete the setup:<br /><br />1. Generate In-App Purchase Key from App Store Connect.<br />2. Upload the new key in the Revenue Settings section of the AppsFlyer platform.<br /><br />If your app is using Apple Server Notifications Version 1, you must switch to Version 2 before updating your credentials. You’ll see a message in the Revenue Settings page if this applies to your app as prerequisite.<br /><br />Follow the detailed instructions below:<br /><br />* [Update the App Store credentials for ROI360 iOS receipt validation](#get-ios-credentials)<br />* [Set up Version 2 of Apple Server Notifications](#send-app-store-notifications-directly-to-appsflyer) |



### Set up version 2 of Apple Server Notifications

If your app previously used Apple Server Notifications Version 1, you must switch to Version 2 in App Store Connect before updating your validation credentials. (If this applies to your app, you’ll see a message on the **Revenue settings** page.)

**To set up version 2 of Apple Server Notifications:**

1. In **App Store Connect**, in the **App Information** section, scroll to **App Store Server Notifications.**

   ![image (24).png](https://files.readme.io/8e9c92cdf87303b58a6b604640b4f7adb3cf56c03e57df053e9d486b89345547-33812520143505.png)
2. For **Production Server URL**, click **Edit**.
3. Do not change the URL in the **Production Server URL** box.

   ![image (25).png](https://files.readme.io/fc7737793f2e7982e3e92d30dec45d7def98ef8ec6c3186ebbdf32a78f217a3d-33812683240977.png)
4. Under **Notification Version**, select **Version 2 Notifications**.
5. Click **Save**.
6. Under the **App Store Server Notifications** section, click **Edit** for the **Sandbox Server URL**.
7. Repeat the steps 3-5.

### Update the App Store credentials for ROI360 receipt validation

The required credentials for the iOS In-App Purchase API integration are:

* In-App Purchase  key
* Key ID
* Issuer ID

**Before you start**:

* Updating the keys involves steps performed in both App Store Connect and AppsFlyer. During setup, keep both the App Store Connect and AppsFlyer tabs open.
* You need admin permissions to set up keys in AppsFlyer.

**To update iOS credentials**:

1. In the App Store Connect, go to **Users and Access** ![](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)
2. Go to **Users and Access** > **Integrations**, and from the **Keys** list, select **In-App Purchase**.  
   ![](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)
3. Click **+** to generate a new In-App Purchase key.  
   ![](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)
4. Enter a name for your API key.
5. Click **Generate**.
6. Click **Download In-App Purchase Key** next to the key you just generated to download it. **Note**: You can only download the key once.
7. In **AppsFlyer**, from the side menu, select **Settings** > **Revenue Settings**.
8. Select your app from the list.
9. In the **Purchases & subscriptions** tab, click **Update keys**. ![](https://files.readme.io/edcb9ef1c24f58b911792e924ca69173c487261e2ef35cf1a21270251c50e586-33405937635601.png)
10. Under **New keys**, in the **In-App Purchase key** field, click the **Upload icon** ( ![upload-2.png](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png)) to upload the p8 file.
11. In App Store Connect, copy the **Key ID** of the key you just generated and paste it into the AppsFlyer purchases & subscriptions setting for **Key ID**. ![](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)
12. In App Store Connect, copy the **Issuer ID** and paste it into the AppsFlyer purchases & subscriptions setting for **Issuer ID**. **Note**: If the **Issuer ID** is not displayed at the top of the page, create an App Store Connect API key (with any access level). After that, the Issuer ID will appear at the top of the page for the In-App Purchase key. 

    ![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)
13. In the AppsFlyer purchases and subscriptions settings, click **Validate keys** to ensure the keys you entered are correct.
14. Click **Update keys**. Once the keys are updated, your app will be fully transitioned to Apple’s new iOS validation flow.
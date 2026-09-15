---
title: "Set up your ESP integration with AppsFlyer"
excerpt: "Set up an ESP integration with AppsFlyer to enable seamless and secure deep linking in your email campaigns for better user engagement and conversion rates."
---
![ESP final main KB image.png](https://files.readme.io/f14a193bb8d303adb93c01b33dcafba9053359fd92a187378cd324544a94dc88-27434531852049.png)

## About the AppsFlyer ESP integration

Marketers often use email service providers (ESPs) to send large-scale email campaigns. And while this should be a simple process, delivering predictable user journeys, this is often not the case. The reason lies in how the typical ESP handles its analytics, which tends to break deep links and negatively affect the mobile user experience. As a result, users are sometimes routed to mobile websites instead of your app, making conversions less likely.

AppsFlyer addresses this issue with an ESP integration solution, which enables AppsFlyer to serve as an intermediary between the ESP server and your domain name. Its role as a proxy enables the provision of association files (AASA / asset links) which facilitates deep linking. Additionally, the AppsFlyer solution sends measurement data back to your ESP, enabling you to monitor your email analytics effectively.

Set up an ESP integration with AppsFlyer for smooth and secure deep-linking experiences in your email campaigns, for optimal mobile user engagement and conversion rates.

> 📘 Premium Feature
>
> The AppsFlyer ESP integration solution is a premium feature. If you’d like to learn more about it or get started, get in touch with us at [hello@appsflyer.com](mailto:hello@appsflyer.com).

## Set up the integration

This section describes how to set up your ESP integration with AppsFlyer.

### Prerequisites

Before you begin setting up your ESP integration with AppsFlyer, you'll need to have an account with a supported ESP\*. The following items will be required from them:

- A new **click-tracking domain** (described in Step 1.)
- The **ESP endpoint**: The endpoint is provided to you by the ESP so you can route your clicks to its servers. Example of the ESP endpoint structure: esp.endpoint.com.
- **Specific ESP integration requirements:**
  - **Emarsys** - Ask your Emarsys customer success manager to enable HTTP redirection.
  - **Blueshift** - Ask your Blueshift customer success manager to change the HTTP response code for clicks to 302 (from the default 307).

**To set up the integration, follow these steps:**

### Step 1. Create a click-tracking domain in your ESP platform (IT / system admin task)

The click-tracking domain (CTD) is the domain component of the URL that appears in email messages.

It consists of a subdomain and your main domain, such as mail.yourbrand.com. Different ESPs may refer to this as link branding, tracker domain, click domain, link rewriting, click tracking, or white labeling.

**Creating a new CTD is mandatory**, even if you are already using an existing one. This ensures that there is no impact on the traffic of current live email campaigns.

> 📘 Notes
>
> - The SSL certificate will be handled by AppsFlyer (in step 3.).
> - At this stage, email links will likely not be secured, meaning the URL prefix will be HTTP instead of HTTPS. This will be resolved in Step 5.

### Step 2. Use a OneLink template for your email campaign

Create a [OneLink template](https://support.appsflyer.com/hc/articles/207032246#procedures) and configure Universal Links/App Links under "When app is installed". This template will be used later to create OneLink links for your email campaigns.

\*If you already have an existing OneLink template configured that enables Universal Links/App Links, you can use it.

### Step 3. Set your ESP integration in AppsFlyer

Now it's time to set your ESP integration in AppsFlyer. Please note that this step and the following one ("Step 4. Configure your app") can be set up at the same time.

**To set your ESP integration in AppsFlyer:**

1. In **AppsFlyer**, from the side menu, select **Engage** > **ESP integration**.

![From Engage click ESP integration.png](https://files.readme.io/7b731446ce6158d5033020b63be5f386105e7899a8c1b291aa3cb13662a59ee5-27063684942481.png)

2. Select your ESP.

![select ESP.png](https://files.readme.io/526fed3aaf1e6fdbf2404243619159984e298752fdf5913fd3a65cc5a2ed9e1d-27086632495761.png)

3. Select the OneLink template you want to use for email campaigns, then click **Next**.

![select OneLink template.png](https://files.readme.io/4f96b999740be8596a424ce9108a8f702bda2a7ed025ec1869c553393432d87d-27086632499729.png)

4. Make sure you have an active account with the selected ESP.

You will need the following from your ESP:
- The click-tracking domain you created in step 1.
- ESP endpoint

Click **Next**.

5. Enter your click tracking domain and ESP endpoint, then click **Validate connection**. This validates that the click-tracking domain points to the endpoint you entered.

![enter your ctd and esp endpoint.png](https://files.readme.io/d068b7de020bed7ba979b25e0fe866c40a118b00bbfde06a36a4c097485ac885-27086632503441.png)

When done, click **Next**.

6. **Route link traffic to AppsFlyer:**

a. **Copy and send the customized pre-fabricated instructions in AppsFlyer to your IT or domain administrator.** They will need to reroute your email campaign traffic from the ESP servers to the AppsFlyer servers by updating your DNS CNAME records with the new domain provided by AppsFlyer.

As a result, every time a link is clicked, the click will be redirected to AppsFlyer, which in turn will redirect it to the ESP endpoint.

![click to Af to ESP image.png](https://files.readme.io/8a53fa7e8e2574246ea6b1344cfec0ac2d8f319bb181f6956ecb6db5b05cd0c5-26982377140369.png)

b. After copying and sending the instructions, click **Done**.

Your ESP integration has been created.

> 📘 Important
>
> - Your ESP integration status is pending and will only start working after the CNAME record is mapped.
> - It can take up to 24 hours after mapping for a new integration to start working and become active.

### Step 4. Configure your app (developer task)

Have your developer make the following configurations to your app:

- [Configure your app to support associated domains](/docs/set-up-your-esp-integration-with-appsflyer#h_01J3W8XR5QS227XNCD453RWYZ9)
- [Configure your app to support deep linking](/docs/set-up-your-esp-integration-with-appsflyer#h_01J3W8Y7FMSWPG7MFF6FMSXFM3)
- [Configure your app to handle Weblinks and Application links](/docs/set-up-your-esp-integration-with-appsflyer#h_01J3W8ZMHSXQGJPQEVR62Q28X9)

#### **Configure your app to support associated domains**

AppsFlyer hosts app association files for your app to enable [Universal Links (iOS)](https://support.appsflyer.com/hc/articles/360000732237#universal-links) or [App Links (Android)](https://support.appsflyer.com/hc/articles/360000732237#android-app-link).

**To configure your app to access the files:**

**For iOS**

**Prerequisite:** SDK from [v6.12.3](/docs/appsflyer-ios-sdk-release-notes)

Configure your app to enable Universal Linking from the email message to your app.

Learn more about configuring [Universal links](https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links).

> 📘 Note
>
> The click domain should be added to the current domains already defined in the associated domains.

**For Android**

**Prerequisite:** SDK from [v6.12.5](https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk)

Configure your app to enable Android App Linking from the email message to your app. Learn more about configuring Android [App Links](https://support.appsflyer.com/hc/articles/360000732237#universal-links).

> 📘 Note
>
> The click domain should be added to the current domains already defined in the Android Manifest.

#### **Configure your app to support deep linking**

When a click on an App Link or Universal Link occurs, the app should open.

**To enable the app to extract the OneLink behind the click recording domain and resolve the deep link:**

1. Provide the click recording domain to the SDK API `resolveDeepLinkURLs`. This API must be called before SDK initialization.

- For iOS please follow these [instructions](https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup).
- For Android please follow these [instructions](https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup#flow-description).

2. Use the [Unified DeepLinking API](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl) to get the deep link parameters and handle the deep link data.

#### **Configure your app to handle Weblinks and Application Links**

The provided code aims to regulate the functionality of wrapped links within an email campaign, specifically addressing two types: Weblinks intended to open a website, and links designed to open the app through a universal link or App link.

For more developer information please see the following guides:

- [iOS Deep Linking ESP 2.0](https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup)
- [Android Deep Linking ESP 2.0](https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup)

### Step 5. Ensure SSL click-tracking is turned on in your ESP platform

Perform an email test to verify the link status.

If CTD links are identified as HTTP, contact the ESP team to enable SSL click-tracking.

This will ensure that all HTTP links are automatically converted to HTTPS.

You can use the following sample message text when contacting your ESP:

```
Hi Team,

Could you please enable SSL click tracking for CTD XXX? It is currently set to HTTP instead of HTTPS.

We appreciate your assistance with this update.
```

### Step 6. Customize the OneLink link for your email campaign in AppsFlyer

**To create and customize the OneLink link for your campaign:**

1. In AppsFlyer, create an “Email-to-app” OneLink link on the OneLink management page (or manually) within the OneLink template you created earlier. This is the link you’ll use in your email campaign that will attribute and redirect users per your specifications. Learn how to create a [OneLink link](https://support.appsflyer.com/hc/articles/208874366#create-a-onelink-link).

![email-to-app.png](https://files.readme.io/4e30986e039ed4cc13b9963ef3d1bb7b933061176bed812dced45a7240023d54-27082280943761.png)

> 👍 Best practice
>
> Use the same campaign name in both the ESP email campaign and in the AppsFlyer OneLink links used in that campaign.

### Step 7. Test the integration in your ESP platform

**To test the integration with the OneLink link you created:**

Insert the OneLink URL in a test email you create and send to yourself using the ESP email editor.

- From your mobile device, open the email and click the link. If you have the app installed, the app will open and you'll be deep-linked to the relevant content. In addition, a mobile click should appear in the AppsFlyer dashboard, attributed to the provided media source and campaign, as well as in your ESP analytics dashboard.
- Click on a web link and verify that it redirects to the correct destination.

Once the test is successful, you're all set.

### Step 8. Use the link confidently in your email campaigns

Well done! You're now ready to use links in your email campaigns. Afterwards, you can view the campaign results in your ESP or AppsFlyer dashboards.

\*ESPs supported by this integration include: Blueshift, Braze, CleverTap, Customer.io, Emarsys, Expert Sender, Klaviyo, MailExpress, MailGun, Moengage, RDStation, Reteno, Sailthru, Sendgrid, Sparkpost, and more. See the full [list](https://support.appsflyer.com/hc/articles/360004556077).

## FAQ

<Accordion title="Do I need to create an SSL certificate at any point?">

No, AppsFlyer creates the SSL certificate for you.

</Accordion>

<Accordion title="If I have the AppsFlyer ESP integration and SDK implemented for basic OneLink deep linking, do I need to add both the OneLink domain and the ESP click tracking domain to iOS Associated Domains?">

- Yes. When configuring ESP and OneLink universal/App Links for deep linking, you must register both the domains in your app’s Associated Domains entitlement:
  - **The OneLink domain** – required for standard deep linking with AppsFlyer.
  - **The ESP click tracking domain** – required to ensure that email links powered by your ESP (e.g., Braze, Emarsys) are recognized and properly deep-linked.
- **Who hosts the AASA file for the click tracking domain?**

In this setup, AppsFlyer hosts the AASA file for the click tracking domain used in ESP email links. You only need to add that domain to your app’s associated domains, and you don't need to manage the AASA hosting yourself.

</Accordion>
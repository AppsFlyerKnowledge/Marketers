---
title: Adobe ESP integration with AppsFlyer
deprecated: false
hidden: false
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-23T06:43:55Z'
  edited_at: '2026-09-23T10:35:28Z'
  id: 51170889016977
  locale: en-us
  section: Email service providers
  section_id: 6551247620881
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/51170889016977-Adobe-ESP-integration-with-AppsFlyer
---
> **At a glance:** Set up an Adobe ESP integration with AppsFlyer to enable seamless and secure deep linking in your email campaigns for better user engagement and conversion rates.

<Image alt="adobe_appsflyer_banner_updated.png" src="https://files.readme.io/95ae69b9b07c2972e03213509fac02516f7ffb300688deb72db5c9aa744e67cf-51180732192401.png" width="1855px" />

## About the Adobe ESP integration

Marketers often use email service providers (ESPs) to send large-scale email campaigns. And while this should be a simple process, delivering predictable user journeys, this is often not the case. The reason lies in how the typical ESP handles its analytics, which tends to break deep links and negatively affect the mobile user experience. As a result, users are sometimes routed to mobile websites instead of your app, making conversions less likely.

AppsFlyer addresses this issue with an ESP integration solution, which enables AppsFlyer to serve as an intermediary between the ESP server and your domain name. Its role as a proxy enables the provision of association files (AASA / asset links) which facilitates deep linking. Additionally, the AppsFlyer solution sends measurement data back to your ESP, enabling you to monitor your email analytics effectively.

Set up an Adobe ESP integration with AppsFlyer for smooth and secure deep-linking experiences in your email campaigns, for optimal mobile user engagement and conversion rates.

The AppsFlyer ESP integration solution is a premium feature. If you'd like to learn more about it or get started, get in touch with us at [hello@appsflyer.com](mailto:hello@appsflyer.com).

## Set up the integration

<span id="h_01J3JHFXRP57VS9D22FEWS2JZW"></span>This section describes how to set up your Adobe ESP integration with AppsFlyer.

### Prerequisites

Before you begin setting up your Adobe ESP integration with AppsFlyer, you'll need to have an account with Adobe. The following items will be required from them:

* A new **click-tracking domain** (described in [Step 1.](/docs/adobe-esp-integration-with-appsflyer#af-accordion-1))
* The **ESP endpoint**: The endpoint is provided to you by the ESP so you can route your clicks to its servers. Example of the ESP endpoint structure: esp.endpoint.com.

**To set up the integration, follow these steps:**

<Accordion title="Step 1. Create a click-tracking domain in your ESP platform (IT / system admin task)">

The click-tracking domain (CTD) is the domain component of the URL that appears in email messages.   
It consists of a subdomain and your main domain, such as mail.yourbrand.com. Different ESPs may refer to this as link branding, tracker domain, click domain, link rewriting, click tracking, or white labeling.

**Creating a new CTD is mandatory**, even if you are already using an existing one. This ensures that there is no impact on the traffic of current live email campaigns.

> 📘 **Notes**
>
> * The SSL certificate will be handled by AppsFlyer (in step 3.).
> * At this stage, email links will likely not be secured, meaning the URL prefix will be HTTP instead of HTTPS. This will be resolved in [Step 5.](#h_01JMYDQGPF3B9GNH0RY27JW3E4)).

</Accordion>

<Accordion title="Step 2. Use a OneLink template for your email campaign">

Create a <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#create-a-onelink-template">OneLink template</Anchor> and configure Universal Links/App Links under "When app is installed". This template will be used later to create OneLink links for your email campaigns.

*If you already have an existing OneLink template configured that enables Universal Links/App Links, you can use it.

</Accordion>

<Accordion title="Step 3. Set your ESP integration in AppsFlyer">

Now it's time to set your ESP integration in AppsFlyer. Please note that this step and the following one ("[Step 4. Configure your app](#h_01J3W0Z1613XPYM75GH65R793W)") can be set up at the same time.

**To set your ESP integration in AppsFlyer:**

1. In **AppsFlyer**, from the side menu, select **Engage** > **ESP integration**.

<Image alt="Selecting ESP integration from the Engage menu" src="https://files.readme.io/e4ab3ceaa61ca94b2cc0ed826ee2dd56dfaf58aafd6a73a81d99ec54541d6d8a-51170889009809.png" width="196px" />

2. Select your ESP (Adobe).

<Image alt="Selecting your ESP from the list" src="https://files.readme.io/12a5ab3adf7a01928a09273fc9921483cc90f88a42ccc73742be70aa3a527b64-51170903613201.png" width="482px" />

3. Select the OneLink template you want to use for email campaigns, then click **Next**.

![Selecting a OneLink template for the ESP integration](https://files.readme.io/cd614aa582712f07b0817524bfb2495a96a5bc7f048d47152e749d406da1aa49-51170889012113.png)

4. Make sure you have an active account with the selected ESP.

You will need the following from your ESP:

* The click-tracking domain you created in step 1.
* ESP endpoint

Click **Next**.

5. Enter your click tracking domain and ESP endpoint, then click **Validate connection**. This validates that the click-tracking domain points to the endpoint you entered.

![Entering the click-tracking domain and ESP endpoint](https://files.readme.io/a27e5e380d4ff31aba901a9bb0fc3178d8bcb3fba6627ca06cef89e977afc2e2-51170903614737.png)

When done, click **Next**.

6. **Route link traffic to AppsFlyer:**

a. **Copy and send the customized pre-fabricated instructions in AppsFlyer to your IT or domain administrator.** They will need to reroute your email campaign traffic from the ESP servers to the AppsFlyer servers by updating your DNS CNAME records with the new domain provided by AppsFlyer.

As a result, every time a link is clicked, the click will be redirected to AppsFlyer, which in turn will redirect it to the ESP endpoint.

<Image alt="Diagram of a click being redirected from the ESP to AppsFlyer" src="https://files.readme.io/f718fd8397bcf73a3f02ddc977680c0d14dd8747509b38e20564c48386590080-51170903615761.png" width="374px" />

b. After copying and sending the instructions, click **Done**.

Your ESP integration has been created.

**Please note that:**

* Your ESP integration status is pending and will only start working after the CNAME record is mapped.
* It can take up to 24 hours after mapping for a new integration to start working and become active.

</Accordion>

<Accordion title="Step 4. Set up an unsubscribe link">

**When using an Adobe unsubscribe link, do the following:**

1. Create *web.`<your domain>`* and CNAME it to the exact Adobe domain that you used to create the click-tracking domain in Step 1. For example: *click.mydomain* → *yourdomain.cname.campaign.adobe.com*.
2. Perform Step 3 for this domain as well - treat this domain as a CTD, and you can use the same OneLink template you used when creating the CTD in Step 1.

It means that under AppsFlyer Adobe integration UI, you will have 2 CTDs.

**Note:** This setup is required because two domains are involved in the unsubscribe link process.

For the **unsubscribe link,** there is no need to perform additional steps beyond what is mentioned here.

</Accordion>

<Accordion title="Step 5. Configure your app (developer task)">

Have your developer make the following configurations to your app:

* [Configure your app to support associated domains](#configure-your-app-to-support-associated-domains)
* [Configure your app to support deep linking](#configure-your-app-to-support-deep-linking)
* [Configure your app to handle Weblinks and Application links](#configure-your-app-to-handle-weblinks-and-application-links)

#### **Configure your app to support associated domains**

AppsFlyer hosts app association files for your app to enable <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-knowledge-base-glossary#universal-links">Universal Links (iOS)</Anchor> or <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-knowledge-base-glossary#lien-dapp-android">App Links (Android)</Anchor>.

**To configure your app to access the files:**

**For iOS**  
**Prerequisite:** SDK from <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-ios-sdk-release-notes">v6.12.3</Anchor>  
Configure your app to enable Universal Linking from the email message to your app.  
Learn more about configuring <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">Universal links</Anchor>.  
**Note:** The click domain should be added to the current domains already defined in the associated domains.

**For Android**  
**Prerequisite:** SDK from <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk">v6.12.5</Anchor>  
Configure your app to enable Android App Linking from the email message to your app. Learn more about configuring Android <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-knowledge-base-glossary#lien-dapp-android">App Links</Anchor>.  
**Note:** The click domain should be added to the current domains already defined in the Android Manifest.

<div id="h_01J3WS4QWMRT8KSW6J3QHXM9TQ" />

#### **Configure your app to support deep linking**

When a click on an App Link or Universal Link occurs, the app should open.

**To enable the app to extract the OneLink behind the click recording domain and resolve the deep link:**

1. Provide the click recording domain to the SDK API resolveDeepLinkURLs. This API must be called before SDK initialization.

* For IOS please follow these <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">instructions</Anchor>.
* For Android please follow the follow these <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup#flow-description">instructions</Anchor>.

2. Use the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Unified DeepLinking API</Anchor> to get the deep link parameters and handle the deep link data.

<div id="h_01J3WS4QWMSKZ33APWFR8CG5TZ" />

#### **Configure your app to handle Weblinks and Application Links**

The provided code aims to regulate the functionality of wrapped links within an email campaign, specifically addressing two types: Weblinks intended to open a website, and links designed to open the app through a universal link or App link.  
For more developer information please see the following guides:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">iOS Deep Linking ESP 2.0</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup">Android Deep Linking ESP 2.0</Anchor>

</Accordion>

<Accordion title="Step 6. Ensure SSL click-tracking is turned on in your ESP platform">

Perform an email test to verify the link status.   
If CTD links are identified as HTTP, contact the ESP team to enable SSL click-tracking.   
This will ensure that all HTTP links are automatically converted to HTTPS.

You can use the following sample message text when contacting your ESP:

Hi Team,  
Could you please enable SSL click tracking for CTD XXX? It is currently set to HTTP instead of HTTPS.   
We appreciate your assistance with this update.

</Accordion>

<Accordion title="Step 7. Customize the OneLink link for your email campaign in AppsFlyer">

**To create and customize the OneLink link for your campaign:**

1. In AppsFlyer, create an "Email-to-app" OneLink link on the OneLink management page (or manually) within the OneLink template you created earlier. This is the link you'll use in your email campaign that will attribute and redirect users per your specifications. Learn how to create a <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink">OneLink link</Anchor>.

<Image alt="Creating an Email-to-app OneLink link in AppsFlyer" src="https://files.readme.io/5e2e4e38f9490132687370347fa7432f383977ae3ae251fd3a897365eb2843a0-51170903616145.png" width="652px" />

**Best practice:** Use the same campaign name in both the ESP email campaign and in the AppsFlyer OneLink links used in that campaign.

</Accordion>

<Accordion title="Step 8. Test the integration in your ESP platform">

**To test the integration with the OneLink link you created:**

Insert the OneLink URL in a test email you create and send to yourself using the ESP email editor.

* From your mobile device, open the email and click the link. If you have the app installed, the app will open and you'll be deep-linked to the relevant content. In addition, a mobile click should appear in the AppsFlyer dashboard, attributed to the provided media source and campaign, as well as in your ESP analytics dashboard.
* Click on a web link and verify that it redirects to the correct destination.

Once the test is successful, you're all set.

</Accordion>

<Accordion title="Step 9. Use the link confidently in your email campaigns">

Well done! You're now ready to use links in your email campaigns. Afterwards, you can view the campaign results in your ESP or AppsFlyer dashboards.

</Accordion>

## FAQ

<Accordion title="Do I need to create an SSL certificate at any point?">

No, AppsFlyer creates the SSL certificate for you.

</Accordion>

<Accordion title="If I have the AppsFlyer ESP integration and SDK implemented for basic OneLink deep linking, do I need to add both the OneLink domain and the ESP click tracking domain to iOS Associated Domains?">

* Yes. When configuring ESP and OneLink universal/App Links for deep linking, you must register both the domains in your app's Associated Domains entitlement:
  * **The OneLink domain** – required for standard deep linking with AppsFlyer.
  * **The ESP click tracking domain** – required to ensure that email links powered by your ESP (e.g., Braze, Emarsys) are recognized and properly deep-linked.
* **Who hosts the AASA file for the click tracking domain?**  
  In this setup, AppsFlyer hosts the AASA file for the click tracking domain used in ESP email links. You only need to add that domain to your app's associated domains, and you don't need to manage the AASA hosting yourself.

</Accordion>

<div data-zendesk-anchors="overview=about-the-adobe-esp-integration h_01J3JHJCCASM6E5QYJB5VHQ8HK=about-the-adobe-esp-integration set-up-your-esp-integration-with-appsflyer=set-up-the-integration h_01J3JHFRGA6BTMWSK7EEEVGS6T=set-up-the-integration h_01J3JJ74GYF5AJT9R2P2CXDXE1=prerequisites h_01JMYJG3CTGE9Y3SBFAECV326G=notes h_01J3W8XR5QS227XNCD453RWYZ9=configure-your-app-to-support-associated-domains h_01J3W8Y7FMSWPG7MFF6FMSXFM3=configure-your-app-to-support-deep-linking h_01J3W8ZMHSXQGJPQEVR62Q28X9=configure-your-app-to-handle-weblinks-and-application-links h_01K3R6V0K31816PVY95X5WZC4C=faq" />

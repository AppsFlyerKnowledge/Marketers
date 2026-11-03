---
title: Salesforce Marketing Cloud (SFMC) integration with AppsFlyer
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-01T14:53:41Z'
  edited_at: '2026-10-22T09:41:15Z'
  id: 50431751712529
  locale: en-us
  section: Email service providers
  section_id: 6551247620881
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/50431751712529-Salesforce-Marketing-Cloud-SFMC-integration-with-AppsFlyer
---
> **At a glance:** Integrate AppsFlyer with Salesforce Marketing Cloud (SFMC) to deep link users from email campaigns to in-app content. Sync in-app event data into SFMC to build audiences and trigger journeys based on real app behavior.

## About the integration

SFMC lets you re-engage existing users through email campaigns by deep linking them to specific in-app content, such as a promotion or a personalized offer.

There are two integration options:

* **Standard SFMC email deep linking**: create your campaign OneLink links in AppsFlyer, then add them to your emails.
* **Advanced SFMC app exchange integration**: create campaign OneLink links directly inside Salesforce, and automatically import in-app event data so you can build re-engagement audiences. This is a premium feature.

## Comparison: Standard vs. Advanced

| Capability | Standard SFMC email deep linking | Advanced SFMC app exchange integration |
| --- | --- | --- |
| Deferred deep links | Yes | Yes |
| Direct deep links | Yes | Yes |
| Deep link measurement | Yes | Yes |
| Link creation | In AppsFlyer | In the dedicated Salesforce app |
| SFMC postbacks (in-app event sync) | No | Yes |

## Prerequisites

<Tabs>
<Tab title="iOS">

* AppsFlyer iOS SDK version 4.9.0+
* For iOS Universal Links, do the following in your SFMC environment: Purchase and implement a <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_sender_authentication_package.htm&type=5">Sender Authentication Package</Anchor> (SAP), and purchase an SSL Certificate (SSL Configuration) and submit an SSL Request Form. Reach out to your Salesforce account representative or submit a deliverability support case via Salesforce Help to get both.

</Tab>

<Tab title="Android">

* AppsFlyer Android SDK version 4.9.0+
* SFMC doesn't support Android App Links, so <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">URI Scheme</Anchor> deep linking is used instead. No special action is needed to support deep linking in Android apps from SFMC.

</Tab>
</Tabs>

## Set up Standard SFMC email deep linking

**To set up the integration:**

<Accordion title="Step 1: Set your click-recording domain in SFMC">

To set a click-recording domain, follow SFMC official guides for:

* <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_implement_ios_universal_link.htm&type=5">Implementing iOS Universal Link</Anchor>
* <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_dns_record_maintenance.htm&type=5">DNS Record Maintenance</Anchor>

</Accordion>

<Accordion title="Step 2: Upload your SSL certificate to SFMC">

In order for iOS Universal Links to work properly, your click-recording domain must include your domain's SSL certificate that should be installed in your SFMC account. Instructions on setting your SSL certificates can be found in the <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_ssl_certificates.htm&type=5">SFMC official guide</Anchor>.

</Accordion>

<Accordion title="Step 3: Set deep linking in SFMC">

To enable deep linking from SFMC emails:

1. Log in to your SFMC account, and go to the **Email Studio** view
2. Click on the **Admin** tab
3. In the side menu, click on **deep linking**. In this view, you can configure new deep link integration with your app, or modify existing ones.

   <Image alt="[ALT TEXT NEEDED: describe the SFMC deep linking configuration screen]" src="https://files.readme.io/4b7e68abb76163329ab5d487425c4dfe3ee903bb3360893c9b59f40f73486858-50431735587345.png" width="3348px" />
4. To create a new configuration, click the **Create** button and enter your AppID. The AppID value is a combination of your Apple developer team ID and the Bundle ID. Both of these values can be retrieved from your Apple Developer account.

   > 📄 **Example**
   >
   > Given the Team ID prefix *5UABCDFGH* and the Bundle ID *com.your.app*, the following value should be entered:  
   > 5UABCDFGH.com.your.app
   >
   > <Image alt="[ALT TEXT NEEDED: describe the SFMC deep linking configuration screen shown here]" src="https://files.readme.io/4f5500c6f538b2b8e00db0bae1bcac240fc49b30419f4f4a8b07fb0bd3cf8f4a-50431735587985.png" width="1234px" />

5. Your set up of universal links and deep linking is completed once SFMC sets up the Apple App Site Association (AASA) file. This process may take a few hours. You can see your generated file using the following URL:

   ```
   https://<click_recording_link_domain>/apple-app-site-association
   ```

</Accordion>

<Accordion title="Step 4: Configure your AppsFlyer SDK">

> 📘 **Note**
>
> If you haven't already done so, make sure to configure your app to support <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">deep linking with OneLink</Anchor>.

After configuring your click-recording domain to support Universal Links as described previously, you need to set up your app to deep link and resolve the Universal Link.

1. Associate the click-recording domain in Xcode:

   <Image alt="[ALT TEXT NEEDED: describe the Xcode associated domains screen]" src="https://files.readme.io/02bee3d75c32d494d80719b2718ddf4648440bcb3ebcb2132799e44e38852629-50431735589009.png" width="1135px" />
2. Provide the click-recording domain to the SDK API `setResolveDeepLinkURLs`. This API needs to be called before SDK initialization. For more information, see the SDK documentation on <Anchor target="_blank" href="/marketers/id/docs/sdk-integration-overview">resolving deep link URLs</Anchor>.

   ```swift
   AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   * **Important!** If you are using Movable Ink (MI) in conjunction with Salesforce, you need to get the MI CNAME and internal domains from your MI account manager and add them to `setResolveDeepLinkURLs`, in addition to the click link for Salesforce. For example:

     ```swift
     AppsFlyerLib.shared().resolveDeepLinkURLs = ["salesforce-click.example.com", "mi.example.com", "example.micpn.com"]
     ```
3. When the app is invoked due to a click on the Universal Link, the AppsFlyer SDK resolves the deep link and extracts the underlying OneLink. All deep link parameters are then propagated into the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onappopenattribution">onAppOpenAttribution API</Anchor> for deep link logic execution.

</Accordion>

## Send emails with Standard SFMC email deep linking

**To send emails with Standard SFMC email deep linking:**

1. Create a <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink link</Anchor>, either manually or from the OneLink links page in the AppsFlyer dashboard.
2. URL-encode all parameter values when you create the OneLink. These parameters are highly recommended:

| Parameter | Description | Notes |
| --- | --- | --- |
| pid | Media source | Representative media source |
| c | Campaign name | The campaign that will be attributed |
| af\_dp | Deep-link URL | Deep-link redirect for users |
| af\_web\_dp | Desktop redirect | Redirect for desktop users |
| af\_ios\_url |  | Redirect for iOS users who don't have the app installed |
| af\_android\_url |  | Redirect for Android users who don't have the app installed |

3. Copy the link into the email you create in Salesforce Email Studio. Salesforce Marketing Cloud wraps the link with your click-recording domain, so any click on that domain redirects to your OneLink attribution link.

**Example** (URL parameters shown unencoded, for readability):

```
https://example.onelink.me/ABcd?pid=Email&c=Spring_Newsletter&af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
```

## Set up the Advanced SFMC app exchange integration

**To set up the advanced SFMC app exchange integration:**

<Accordion title="Step 1: Install the OneLink app from the SFMC AppExchange">

1. Ask your CSM, or email hello@appsflyer.com, to enable the app install on the SFMC AppExchange.
2. In Salesforce, go to the AppExchange link your CSM shares once the app is enabled.
3. Click **Install**.
4. Grant permissions: ask your Salesforce Marketing Cloud admin to grant access to the app for individual users or Business Units. You may need a hard refresh to see the new permissions.
5. Give users access to the AppsFlyer OneLink app: go to **Apps > Installed Packages**, select the **ACCESS** tab, select the users who should be able to use OneLink, and click **Save**. Again, a hard refresh may be needed.

</Accordion>

<Accordion title="Step 2: Complete the basic setup">

Complete the steps in the "[Set up Standard SFMC email deep linking](#set-up-standard-sfmc-email-deep-linking)" above.

</Accordion>

<Accordion title="Step 3: Create OneLink links in Salesforce using the AppsFlyer OneLink app">

Create a separate attribution link for each campaign.

<Image alt="[ALT TEXT NEEDED: currently the filename SFMC-AF-app1-en_us.png; describe the OneLink app screen shown]" src="https://files.readme.io/21d7961d03e822dd2a4ccb426dc7b5c85c3700f81a9530bc8950a67e3f1d6237-50431735591185.png" width="684px" />

**To create a OneLink link:**

1. In **Salesforce**, open the **AppsFlyer** OneLink app.
2. Click **Add OneLink**.
3. Enter a name in the **Link name** field. Consider:
   * Choose an easily identifiable name.
   * The link name will be used when applying OneLinks to email campaigns.
4. In the **Base URL** field, enter the long-version OneLink URL copied from the **AppsFlyer OneLink custom links** page.
   * Use a long-version URL to make sure the app analyzes and sets link parameters.
   * Learn how to <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">copy an existing link URL</Anchor> or <Anchor target="_blank" href="/marketers/id/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">create a new OneLink link</Anchor>.
5. [Optional] To add more parameters, click **Add parameter**. See the <Anchor target="_blank" href="/marketers/id/docs/about-link-structure-and-parameters#parameter-link-atribusi">list of recommended parameters</Anchor>.
6. [Optional] To set an internal SalesForce marketing cloud macro, click the icon located to the right of a parameter.
   * It is recommended to set a **Subscriber key** for each **OneLink** parameter.
   * This lets you connect attributed email conversions back to your Salesforce data.
7. Click **Generate link**.

</Accordion>

<Accordion title="Step 4: Send emails containing custom attribution links">

1. In **Salesforce Email Studio**, create a new template or email.
2. Click the **Edit** icon, the **Content** tab, then select **Blocks**.
3. Scroll down to find **AppsFlyer Button CB** or **AppsFlyer Image CB**.

   <Image alt="[ALT TEXT NEEDED: currently the filename sf_email_edit_onelink_new.PNG; describe the Content Blocks panel shown]" src="https://files.readme.io/565a80933451dbdb1606b20f8d71964019a36f14ffd0b0ba295649a96b056cf0-50431751706641.png" width="396px" />
4. Drag the image/button into the body of the email.
5. Click the image/button to edit.
6. In the **Title** field, name the image/button.
7. Select a **OneLink link**.

   <Image alt="[ALT TEXT NEEDED: describe the OneLink link selector shown]" src="https://files.readme.io/1d22268b5ced4d753cb6812decdccd960e92d9d8156213f76fc67db98b52c9c7-50431751707665.png" width="415px" />
8. Save the email and send it.

> 📄 **Example**
>
> For readability purposes, the URL parameters are not URL encoded:
>
> ```
> https://example.onelink.me/ABcd?pid=Email&c=Spring_Newsletter&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

</Accordion>

<Accordion title="Step 5: Test your links">

**To test your attribution links:**

1. Create the appropriate OneLink URL.
2. Place it in an email.
3. Send the email to yourself.
4. Click the link.

* If you have the app installed on your device, the app should be invoked.
* If the relevant AppsFlyer SDK deep linking APIs are implemented you are deep linked into the relevant content.
* A click should appear in both the AppsFlyer dashboard, attributed to the provided media source and campaign.
* A click appears in Salesforce data.

</Accordion>

## Dynamic Emails

If you need to generate links dynamically to represent dynamic content per user, use the OneLink API.

To do this, use an Automation Studio script activity in SFMC's Journey Builder that calls the OneLink API before the send, writes the generated deep link into a field on the send Data Extension for each contact, then have the email pull that field with a simple AMPscript lookup.

## Advanced SFMC in-app events data sync

This feature lets AppsFlyer automatically send in-app event data from your app to Salesforce Marketing Cloud, where it's stored in a dedicated Data Extension. Use this data to build audiences, trigger journeys, and personalize campaigns based on real app behavior, such as purchases, registrations, or level completions.

This is a premium feature, available as part of the Advanced SFMC app exchange integration.

### How it works

When a user performs an in-app event (for example, completing a purchase), AppsFlyer sends a postback to the SFMC connector. The connector writes the event data into a Data Extension in your SFMC account, where each row represents one event for one contact. From there, use SFMC's Journey Builder or Automation Studio to trigger follow-up communications based on that event.

**To set up the advanced data sync:**

<Accordion title="Step 1: Enable postback sending in AppsFlyer">

1. In AppsFlyer, go to **Collaborate > Active Integrations** and search for Salesforce Marketing Cloud.
2. Select the app you want to configure and click **Set up integration**.
3. In the **Integration** tab, make sure the **Activate partner** toggle is on.
4. Scroll to **In-app event postbacks** and turn the toggle on.
5. Click **Add event** and map the AppsFlyer events you want to send to SFMC. For each event, select it from your app's event list and set the sending condition: **This partner only** (sends only events attributed to SFMC traffic) or **All media sources, including organic** (recommended for audience building, since it sends every occurrence of the event regardless of attribution).
6. Click **Save integration**.

> 📘 **Note**
>
> Only events already received by AppsFlyer from your SDK or S2S integration appear in the event list. If an event is missing, check your SDK implementation first.

</Accordion>

<Accordion title="Step 2: Verify the Data Extension in SFMC">

After the first postback is sent, AppsFlyer automatically creates a Data Extension in your SFMC account, named Installs-`{mid} or Events-{mid}`. To verify:

1. In SFMC, go to **Email Studio > Data Extensions**.
2. Search for your app's Data Extension.
3. Confirm rows are populating with event data. Each row should include the contact identifier, event name, event timestamp, and event parameters.

If the Data Extension wasn't created automatically, confirm the SFMC connector app is correctly installed and that your SFMC admin has granted it the necessary data write permissions.

</Accordion>

<Accordion title="Step 3: Use event data in Journey Builder">

1. In SFMC, open Journey Builder and create or edit a journey.
2. Set the entry source to **Data Extension** and select the AppsFlyer Data Extension for your app.
3. Configure the entry criteria, for example, contacts whose event\_name equals af\_purchase.
4. Build the journey steps you need (send email, wait, branch by event value, and so on).
5. Activate the journey.

> 👍 **Tip**
>
> Use the af\_sub1 parameter in your OneLinks to pass the SFMC subscriber key as a user identifier. This lets postbacks match back to the correct contact record in Salesforce, enabling contact-level personalization rather than campaign-level attribution only.

</Accordion>

### Postback data fields

The SFMC connector creates two Data Extensions in your account: one for installs, one for in-app events. All fields exist in the schema, but some aren't currently populated. Fields marked "not written" are part of the schema but will always be empty.

<Accordion title="Data fields">

**Install Data Extension fields (49 fields)**

| Field | Written | Notes |
| --- | --- | --- |
| Touch Type | Yes |  |
| Touch Time | Yes |  |
| Event Name | Yes |  |
| Event Source | Yes |  |
| Media Source | Yes |  |
| Channel | Yes |  |
| Campaign | Yes |  |
| Campaign ID | Yes |  |
| Sub Param 1 to 5 | Yes | Map to af\_sub1 through af\_sub5 on the OneLink |
| Region | Yes |  |
| Country Code | Yes |  |
| State | Yes |  |
| City | Yes |  |
| Postal Code | Yes |  |
| DMA | Yes |  |
| IP | Yes |  |
| AF ID | Yes | AppsFlyer's unique device identifier |
| IDFV | Yes |  |
| Device Type | Yes |  |
| Device Cat | Yes |  |
| Platform | Yes |  |
| OS Version | Yes |  |
| App Version | Yes |  |
| SDK Version | Yes |  |
| App ID | Yes |  |
| App Name | Yes |  |
| Is Retargeting | Yes |  |
| Match Type | Yes |  |
| User Agent | Yes |  |
| Install Time | Yes |  |
| Event Time | Yes |  |
| Deep Link Value | Yes |  |
| deep\_link\_sub1 to sub10 | No | Exists in the schema, not written |
| IDFA | No | Exists in the schema, not written (iOS device identifier) |
| Advertiser ID | No | Exists in the schema, not written (Android GAID) |

**In-app event Data Extension fields**

All install fields above, plus:

| Field | Written | Notes |
| --- | --- | --- |
| Is Primary Attribution | No | Exists in the schema, not written |
| Reengagement Window | No | Exists in the schema, not written |
| Event Value | No | Exists in the schema, not written |
| Event Revenue Currency | No | Exists in the schema, not written |
| Event Revenue USD | No | Exists in the schema, not written |

</Accordion>

### Troubleshooting

* **No data in the Data Extension**: Check that the Activate partner toggle and the in-app event postbacks toggle are both on, and that the events you need are mapped. Also confirm the SFMC app has data write permissions in your SFMC account.
* **Events appearing but no matching contacts**: Make sure you're passing af\_sub1=%%\_subscriberkey%% in your OneLinks, so postbacks can match to SFMC contacts.
* **Data Extension not created**: Contact your CSM or AppsFlyer support to confirm the connector is correctly provisioned for your account.

<div data-zendesk-anchors="h_01M1EKQ4FWJDKEECDASNHC226Z=about-the-integration h_01M1EKQ4FWVTQ3R02AE6QREKKK=comparison-standard-vs-advanced h_01M1EKQ4FW9XVMFC7FXD8551C1=prerequisites h_01M1EKQ4FW115929RS4BR442QF=set-up-standard-sfmc-email-deep-linking h_01HE7RCE5NE25563AAGBH0EPZC=example h_01HE7RCE5N1WQA3XEN9W1QY29K=note h_01M1EKQ4FW5Q23VEPA4YJK9MQF=send-emails-with-standard-sfmc-email-deep-linking h_01M1EKQ4FW91474YRH5GZ0K805=set-up-the-advanced-sfmc-app-exchange-integration h_01HA51F56HX6VQDYNAQAADKBHJ=example-1 h_01M1EKQ4FW48QWSZ9W5J80AZVZ=dynamic-emails h_01M1EKQ4FW4N9ZGBDGYZ6VAKWN=advanced-sfmc-in-app-events-data-sync h_01M1EKQ4FWVP1A3J89BGQBV8A8=how-it-works h_01M1EKQ4FWZZS3D4T5QW7HNQ9W=postback-data-fields h_01M1EKQ4FW366GDCCXJS7TDEQS=troubleshooting" />

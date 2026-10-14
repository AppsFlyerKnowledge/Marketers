---
title: "PBA Web SDK integration guide"
excerpt: "Integrate AppsFlyer into websites using the Web SDK to record and measure visits, events, conversions, and revenue."
x-zendesk:
  id: 360001610038
  url: https://support.appsflyer.com/hc/en-us/articles/360001610038-PBA-Web-SDK-integration-guide
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  position: 7
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-gil-or, Marketers, Cross-Platform Measurement]
  labels: [Developers, Marketers, Loc In Prog, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2019-05-17T09:05:30Z'
  edited_at: '2026-08-14T16:22:54Z'
---
![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)

## Web SDK user and integration guide

* The Web SDK JavaScript tag:
  * is part of the People-Based Attribution (PBA) solution for analyzing user journeys across multiple platforms.
  * reports user visits and actions on your website to the AppsFlyer platform.
  * is a website plug-in module that needs no programming. It is agnostic to the website visitor's operating system and browser.
  * Size: 40-60Kb.
* Implement the Web SDK alongside the AppsFlyer mobile SDK to record and map user activity across your mobile app and web environments.
* Events occurring outside of the website can be recorded using [Web server-to-server events API](/docs/web-server-to-server-events-api-for-pba-web-s2s) (Web S2S)

## Selecting a code snippet

Choose the snippet that matches your integration type and security requirements. Two options are available:

* [Standard Web SDK](#standard-web-sdk): The standard integration.
* [Advanced SDK Verification](#advanced-sdk-verification): An enhanced integration that adds supply-chain protection for the Web SDK. Use this to add an extra layer of security against CDN compromise, DNS hijacking, and man-in-the-middle attacks.

**Important!**

If you are transitioning from the Standard Web SDK to Advanced SDK Verification, replace your existing snippet with the new one. Do not add the new snippet on top of the existing one.

### Standard Web SDK

Use this snippet to deploy the standard Web SDK integration. Paste it near the top of the `` tag on all pages where you want to load the SDK.

<div id="standard-without-smart-banners" />

<Accordion title="Without Smart Banners">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
</script>
```

</Accordion>

<div id="standard-with-smart-banners" />

<Accordion title="With Smart Banners">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba,banners&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
  AF('banners', 'showBanner');
</script>
```

</Accordion>

### Advanced SDK Verification

Advanced SDK Verification adds supply-chain protection for the Web SDK. It ensures that the code running in your users' browsers is exactly what AppsFlyer published. The SDK source code itself is identical to the standard integration; only the delivery and verification mechanisms differ.

The Advanced SDK Verification:

* Adds an extra layer of security against CDN compromise, DNS hijacking, and man-in-the-middle attacks.
* Adds approximately 250ms to the SDK loading time.

Advanced SDK Verification is optional. The standard integration remains fully supported and is the market standard for third-party analytics pixels. Advanced SDK Verification provides an additional layer of protection beyond that standard.

If your website enforces a Content Security Policy (CSP) using a nonce, see [Content Security Policy (CSP)](#content-security-policy-csp) in the Manage privacy section for the nonce-extended variant of this snippet.

<div id="advanced-verification-without-smart-banners" />

<Accordion title="Without Smart Banners">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="advanced-verification-with-smart-banners" />

<Accordion title="With Smart Banners">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

## Integrating the Web SDK into the website

<div id="installation-and-integration" />

<Accordion title="Installation and integration">

#### Considerations and actions required

| Integration checklist |
| --- |
| To ensure that visits and events are recorded, the Web SDK must be installed on all pages of the website. |
| Place the snippet code [that you selected above](#selecting-a-code-snippet) so that it loads as early as possible in the page scope. Do so by placing the code near the top of the head tag. |
| If you are integrating the SDK using Google Tag Manager (GTM):<ul><li>Ensure that the SDK loads once per page load.</li><li>Set the SDK to load as soon as the page loads using [GTM prioritization.](https://support.google.com/tagmanager/answer/2772421?hl=en)</li></ul> |
| You can implement the Web SDK **with** or **without** Smart Banners. Follow the relevant instructions in the sections that follow. |
| Integration mandatory requirements<ul><li>Visit recording</li><li>Event recording</li><li>Setting the [Customer User ID](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid) (CUID) : If you don't have a CUID, reach out to your CSM to discuss alternatives.</li></ul>Validate the integration using the [test tool](/docs/test-pba-web-sdk-integration) |

**Before you start**:

* Verify with the marketer that they have created the [brand bundle.](/docs/pba-brand-bundles-and-settings)
* For additional guidance see the [PBA onboarding guide](/docs/onboarding-guide-to-people-based-attribution).
* Consider: If you already have the standalone Smart Banners web SDK, remove it and replace it with the Web SDK for both Smart Banners and People-based Attribution; do not simply add the standalone Web SDK for PBA.

**Do the following:**

* Get the Web SDK Web Dev Key. **Note!** This is not the same key used by mobile apps.
  * **To get the Web Dev Key:**
    1. In AppsFlyer, from the top menu, select the **My Apps**tab.
    2. Click **View brand bundles.**
    3. Copy the required **Web Dev Key. (WEB\_DEV\_KEY)**
* If you implement Smart Banners, get the Smart Banner key.
  * **To get the Smart Banner Key:**
    1. In AppsFlyer, from the side menu, go to **Engage** > **Web to App** > **Smart Banners.**
    2. Copy the required **Smart Banner Key**.
* Permissions to add scripts to head tags on the website.
* If you use Google Tag Manager, it must be integrated into the website.

**Proceed to integrate web SDK by using one of the following options.**

<Accordion title="Native">

#### JavaScript code snippet

Integrate the web SDK using one of the following methods.

#### **To install the Web SDK without Smart Banners:**

1. Repeat the procedure that follows on all pages on your website.
2. In the code snippet, that follows, replace the `WEB_DEV_KEY` using the key specified in the prerequisites.
3. Paste the code snippet [you selected above](#selecting-a-code-snippet) into the head tag of your website. Paste it near the top of the head tag.

#### **To implement the Web SDK with Smart Banners:**

1. Repeat the procedure below on all pages of your website.
2. In the code snippet [that you selected above](#selecting-a-code-snippet), replace the `WEB_DEV_KEY` and `YOUR_BANNER_KEY`using the keys specified in the prerequisites.
3. Paste this code snippet into the website's head tag. Paste it near the top of the head tag.

</Accordion>

<Accordion title="Google Tag Manager">

**To implement the web SDK with Google Tag Manager (GTM):**

1. [Go to Google Tag Manager.](https://developers.google.com/tag-manager/quickstart)
2. Create a new tag for AppsFlyer web SDK.

   ![Create a new tag for the AppsFlyer Web SDK in Google Tag Manager](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)
3. Select **Custom HTML** tag type.
4. Give the tag a meaningful name.
5. Do one of the following:
   * If you are integrating the web SDK **without** Smart Banners:
     1. Paste the code snippet [that you selected above](#selecting-a-code-snippet) into the **Tag Configuration** window.
     2. In the code snippet, replace `WEB_DEV_KEY` using the key mentioned in the prerequisites.
   * If you are integrating the web SDK **with** Smart Banners:
     1. Paste the code snippet [that you selected above](#selecting-a-code-snippet) into the **Tag Configuration** window.
     2. In the code snippet, replace the `WEB_DEV_KEY` and `YOUR_BANNER_KEY`using the keys mentioned in the prerequisites.
6. Click **Save**.
7. Do one of the following:
   * **To add the trigger to all pages:**
     1. Click **Add Trigger**.

        ![gtm-af-tag-sdk-trigger.png](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)
     2. Select **All Pages**.
     3. Click **Save.**
     4. Enter a tag name and click **Save**.  
        You have completed the procedure.
   * **To add the trigger to specific pages:**
     1. Click **Save Tag**.
     2. In the GTM main window, select **Triggers.** Click **New**.
     3. Click the pen icon.
     4. Choose the **Page View** trigger type.  
        ![PBAselectTrigger_us-en.jpg](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)
     5. Select **Some Page Views.**
     6. Set the page and trigger conditions as needed.
     7. Click **Save.**
     8. Associate the trigger to the AppsFlyer Web SDK tag. To do so:
        1. In the GTM main window, select Tags.
        2. Select the tag you created earlier.
        3. In the triggering panel, click on the pen.
        4. Select the page view trigger you created earlier.

           ![Select the page view trigger created earlier in Google Tag Manager](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)
        5. Click **Save**.

</Accordion>

<Accordion title="Adobe Launch Tag Manager">

1. [Create a property in Adobe Experience Cloud](/docs/pba-web-sdk-integration-guide#create-a-property-in-adobe-experience-cloud)
2. [Add the Web SDK to the Adobe Launch property](/docs/pba-web-sdk-integration-guide#add-the-web-sdk-to-the-adobe-launch-property)
3. [Add the Adobe Launch tag to the website](/docs/pba-web-sdk-integration-guide#add-the-adobe-launch-tag-to-the-website)
4. [Publish the Adobe Launch environment](/docs/pba-web-sdk-integration-guide#publish-the-adobe-launch-environment)

<div id="create-a-property-in-adobe-experience-cloud" />

<Accordion title="Create a property in Adobe Experience Cloud">

![adobe_create_property.png](https://files.readme.io/1f97d619d5fdfe47b1dd1a2e17c0169e939c32bcda62580ba259d6e86f61d6c2-20260884824209.png)

1. Go to **Adobe Experience Cloud** >**Launch**.
2. Under **Adobe Experience Cloud Launch**, click **Go to Launch**.
3. Click **New Property**.
4. Name the property.
5. Under **Platform**, select **Web**.
6. Enter your website domain.
7. Click **Save**.

</Accordion>

<div id="add-the-web-sdk-to-the-adobe-launch-property" />

<Accordion title="Add the Web SDK to the Adobe Launch property">

![web_property_rules.png](https://files.readme.io/5f592f3ce1f5b319c8f6f96a6235618d884a4faccb1387b1f22c1fd2ce662d15-360006168098.png)

1. On the **My web property** page, select the **Rules** tab.
2. Name the rule. Recommended to use, **Load web SDK**.
3. In the **IF** section, under **EVENTS**, click **+Add**.
   * Under **Event Type**, select **Core - DOM Ready**
   * Click **Keep Changes**.
4. In the **THEN** section, under **Actions**, click **+Add**.
   * Under **Action Type** > **Custom Code**.
   * Select **JavaScript** > **Open Editor** and paste the Web SDK snippet **without the &lt;script> tags**.
   * Click **Keep Changes** to close the code editor.
5. Click **Save**.

</Accordion>

<div id="add-the-adobe-launch-tag-to-the-website" />

<Accordion title="Add the Adobe Launch tag to the website">

![adobe_tag.png](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)

1. On the **My web property** page, select the **Environments** tab.
2. Find the row with the environment you want to publish (development or production).
   * Under the **INSTALL** header, click the box icon on the relevant row; this is usually a production environment.
   * See the section about publishing the **Adobe Launch** environment.
3. In the **Web Install Instructions** dialog box:
   * Copy the script code snippet.
   * Close the dialog box.
4. Paste the code snippet into the  tag of the website.

</Accordion>

<div id="publish-the-adobe-launch-environment" />

<Accordion title="Publish the Adobe Launch environment">

![adobe_publishing_env.png](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)

1. On the **My web property** page, go to the **Publishing** tab.
2. Under the **Development** section, click **Add New Library.**
   * Name the library and choose an environment.
   * Under **RESOURCE CHANGES**, click **Add a Resource.**
   * Click **Rules** > **Load web SDK** > **Latest** > **Select & Create a New Revision**.
   * Click **Save**.
3. Under the **Development** section:
   * Next to the newly created library, click the Action menu (3 dots) > select **Build for Development**.
   * Click the action menu again > select **Submit for Approval**.
4. Under the **Submitted** section:
   * Click the action menu > select **Build for Staging**.
   * Click the action menu again > select **Approve for Publishing**.
5. Under the **Approved** section:
   * Click the action menu > select **Build & Publish to Production.**
   * The process is now complete.

</Accordion>

When the website loads on a mobile device, the active creative displays in the banner. To display the banner on specific pages or according to user actions, see [Adobe Launch rules](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html).

</Accordion>

</Accordion>

<div id="ensure-that-the-sdk-is-working" />

<Accordion title="Ensure that the SDK is working">

Once installed verify that the AppsFlyer web SDK is called by the visitor's browser and that messages are sending. This is done by examining the message network connection reported in the browser.

**To ensure that the SDK loads and is working:**

1. Go to the website.
2. Open the browser developer tools.

   ![WebSDK_us-en.jpg](https://files.readme.io/5550f0ee8c1a5852a983e6482cb0489696b669ffe5fade49d2308ee32f57201b-360009548497.jpg)
3. Go to the (A) **Network** tab.
4. Refresh the page.
5. Filter by (B) **wa.appsflyer**.
6. Select the (C) **events** message.
7. In the headers tab, (D) ensure that:
   * **Request URL** is wa.appsflyer.com/events.
   * site\_id query parameter= `WEB_DEV_KEY`.
   * (E)**status code is 200**.
8. Verify that the value of site\_id is equal to the value of `WEB_DEV_KEY` in the brand bundle settings:
   1. In AppsFlyer, from the side menu, select **Settings** > **Brand Bundles.**
   2. Click **Web dev key,** doing so copies the key.
   3. Paste the key in any location (new browser tab, notepad ) to display the key.
   4. Verify that the site\_id and `WEB_DEV_KEY` match.
9. Ensure that the SDK loads only once. Multiple SDK loading can cause the SDK to stop functioning.

</Accordion>

<div id="sending-events-optinoptout" />

<Accordion title="Sending events opt-in/opt-out">

![5578-VistiorPrivacyOptIn_us-en.png](https://files.readme.io/cd6cbcaeb7f831f4efe74a9a6c6b20d5095602e7edf4dd38becd90864e73c2fb-360010263157.png)

The Web SDK sends visitor event data to AppsFlyer. You can control, stop, or start event sending as described in this section.

Consider:

* **SDK initial state setting**: Determines if the SDK sends events on initially loading the web page or if the SDK must wait until you give an explicit command to begin sending events. The setting is contained within the web snippet.
* **Explicit control:** Use to stop or start sending events. For example, if you implement data opt-in/opt-out banners (aka cookie consent banners), integrate the explicit commands into your banner controls to start and stop sending events. The explicit control has priority over the SDK initial state setting, and uses persistent first-party cookies having the following characteristics:
  * Set on the website domain.
  * Expire after a period set by the Web SDK or as determined by the browser. After cookie expiration, the Web SDK reverts to the initial state setting.
  * The Web SDK cookie doesn't interfere with and is always subject to, the browser-specific cookie settings.

#### SDK initial state setting

| Setting | Snippet required |
| --- | --- |
| [Default] Send events | Make the following change to the Web SDK snippet. If necessary, add the measurementStatus parameter:<br /><br />Set measurementStatus=true<br /><br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:true}` |
| Don't send events | Make the following change to the Web SDK snippet. If necessary add the measurementStatus parameter:<br /><br />Set measurementStatus=false  <br />  <br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:false}` |

#### Explicit control

| Option | Command |
| --- | --- |
| Start sending events (opt-in) | `window.AF_SDK.PLUGINS.PBA.enableMeasurement()` |
| Stop sending events (opt-out) | `window.AF_SDK.PLUGINS.PBA.disableMeasurement()` |

</Accordion>

<div id="implement-a-content-security-policy-csp-policy" />

<Accordion title="Implement a Content Security Policy (CSP) policy">

If your website requires strict security or data privacy protocols, use the following mechanisms to configure how the Web SDK interacts with your environment and your data.

#### Content Security Policy (CSP)

If your website requires JavaScript to be secured by a CSP, the Web SDK supports two approaches depending on your CSP configuration.

* **CSP using self**: Add `https://websdk.appsflyersdk.com` to your `script-src` allowlist. This works for both the Standard Web SDK and the Advanced SDK Verification.
* **CSP using nonce**: If your policy uses `script-src 'nonce-...'`, you can use [the nonce-extended variant of Advanced SDK Verification](#advanced-sdk-verification-with-csp-nonce-snippets). This forwards the nonce to all three script tags required by the verification process. Replace `{{CSP_NONCE}}` with your server-generated, per-request nonce value.

The table below shows which CSP policies are compatible with the nonce-extended variant.

| Policy | Works | Notes |
| --- | --- | --- |
| `script-src 'self'` | No | External CDN origin not allowed; inline script also blocked. |
| `script-src 'self' https://websdk.appsflyersdk.com` | Partial | Allows loader and SDK, but inline setup script still blocked. |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | Yes | Nonce covers inline script and loader; SDK tag gets nonce forwarded by the loader. |
| `script-src 'nonce-...' 'strict-dynamic'` | Yes (recommended) | Nonce covers inline script and loader; `strict-dynamic` propagates trust to the dynamically injected SDK tag. No CDN origin needed in the allowlist. |

CSP policy compatibility

#### Advanced SDK Verification with CSP nonce snippets

<div id="nonce-without-smart-banners" />

<Accordion title="Without Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="nonce-with-smart-banners" />

<Accordion title="With Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

</Accordion>

<div id="discard-query-params" />

<Accordion title="Discard query params">

If your query params contain data that you don't want AppsFlyer to record, you can instruct the AppsFlyer platform to discard some or all query params. By doing so they aren't available in raw data or reports.

You can implement the methods described in relation to urls, referrers, and header\_referer.

#### Query discard options

| Method | Description |
| --- | --- |
| Discard all query params | Append `af_url=true` to the url |
| Discard specified query params | By setting a query param mask you specify which params are discarded.  Set the discard mask using `af_url_mask=param` where param is the parameter name.<br /><br />Example:<br /><br />**Url with mask:**<br /><br />`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`<br /><br />**Url after discarding:**<br /><br />`param1=value1&af_url_mask=param2;param3` |

</Accordion>

## Principles of event recording

<div id="conversion-and-standard-events" />

<Accordion title="Conversion and standard events">

* User events are recorded by the SDK, which sends the event to the AppsFlyer platform.
* Using the [conversion events](/docs/pba-brand-bundles-and-settings#web-event-settings) list, set by the marketer, AppsFlyer splits the events into standard and conversion events.
* Conversion event data is available in PBA dashboards.
* Conversion and standard event data are available in [raw data reports.](/docs/pba-raw-data-reports)

### Conversion events

* Conversion events provide insights into your marketing and business efforts. Conversion events include purchases, downloads, signups, and subscriptions.
* PBA attributes conversion events to the media source that drove the user to visit the website.
* By identifying the attributed media source, you can measure and differentiate the quality of users brought by different media sources.
* Conversion events are used to record revenue and calculate ROI.
* Use them to compare the budget of ads for specific media sources against the revenue generated from the users that come from these media sources.

### Standard events

* Standard events are used to validate the user journey and funnels that lead to conversions.
* Use them to measure user activity and highlight media sources that bring engaged users.
* Record user activity to mark users for re-engagement campaigns.

### Recording events

Trigger the web SDK to record events when certain conditions are met, for example, when a landing page loads or when users interact with website elements. See [examples of recording events](#recording-events::f1e16eae).

</Accordion>

<div id="identifying-users-using-customer-user-id-cuid" />

<Accordion title="Identifying users using customer user ID (CUID)">

* Web users are identified in AppsFlyer by using the unique CUID you allocate them. Typically the CUID is managed by your backend servers.
* Use the same CUID value you use in the mobile environment. Doing so enables you to have a holistic view of user activity across multiple platforms. The function in the mobile SDK is setCustomerUserId function ([iOS](/docs/customer-user-id-field-cuid#setting-the-cuid), [Android, Unity](/docs/customer-user-id-field-cuid#setting-the-cuid)).
* To set the CUID in the web SDK:
  * Set the CUID at the earliest point that you have access to it. Most times this means you need to wait for the user to identify via login or sign up.
  * Fire the JavaScript call to setCustomerUserId() as shown in the example that follows.   
    Note! Send the CUID as a string even if it is a number. Do so enclosing it in quotation marks.
* If you implement web S2S, consider that you may need to notify PBA when you [associate](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method) a CUID with a web visitor id in your backend.
* CUIDs must not contain [directly identifiable personal information](/docs/customer-user-id-field-cuid#cuid-and-privacy) such as a phone number or email address.

**Example: set the CUID**

```
// Associate all current user web events to distinct ID 663274 
AF('pba', 'setCustomerUserId' , '663274')
```

</Accordion>

<div id="web-sdk-event-parameters" />

<Accordion title="Web SDK event parameters">

| Parameter name | Mandatory | Description |
| --- | --- | --- |
| eventType | Yes | Event type<br /><br />Format: String<br /><br />Always populate this parameter with EVENT.<br /><br />Example: eventType: "EVENT" |
| eventName | Yes | Event name<br /><br />Format: String<br /><br />Example: Purchase, Subscription |
| ~~eventCategory~~ | No | This parameter is deprecated and will be removed from the system at a date to be announced. Use the eventValue parameter instead. |
| ~~eventLabel~~ | No | This parameter is deprecated and will be removed from the system at a date to be announced. Use the eventValue parameter instead. |
| eventRevenue | No | Revenue assigned to a conversion event<br /><br />Format: Float |
| eventRevenueCurrency | No | Revenue currency<ul><li>3 character [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) currency code</li><li>Default: USD</li></ul>Format: String |
| eventValue | No | Map of event parameters describing the event. Use this parameter to send rich in-app events like product SKU, line item price.<br /><br />Format: JSON<br /><br />**Example:** To send SKU ABC123, having blue color and a unit price of $3.99<br /><br />`{"sku": "ABC123", “color": "blue", "unit_price":3.99,"currency": "USD"}`<br /><br />**Limitation:** 1000 characters. Do not exceed this it will be truncated. |

</Accordion>

<div id="recording-event-scenarios" />

<Accordion title="Recording event scenarios">

Example event

```
// purchase event of shoes with associated revenue
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

The events that you send depend on the nature of your web app. For example, an online store app requires a set of events that differ from that of a news outlet. See the scenarios that follow to get a sense of the events you should and send and when.

#### Online store

Suppose you are managing an online store. Some standard events that you might want to record would be:

* Search: standard event
* Add to cart: standard event
* Remove from cart: standard event
* Purchase: conversion event

News outlet

Suppose you are managing a new outlet. Some events that you might want to record would be:

* Signup: conversion event
* Purchase subscription: conversion event

</Accordion>

<div id="ensuring-that-events-are-sent" />

<Accordion title="Ensuring that events are sent">

This part is intended for web developers.

[Test PBA web SDK integration:](/docs/test-pba-web-sdk-integration) view test events in real-time.

**To ensure that events are sent to AppsFlye**r:

1. Open the website.
2. Open the browser developer tools.
   * [How to open the developer tools in Chrome](https://developers.google.com/web/tools/chrome-devtools/open#console)
   * [How to open the developer tools in Safari](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/Web_Inspector_Tutorial/EnableWebInspector/EnableWebInspector.html)
3. Switch to the Network tab.
4. Trigger the event.
5. Filter by message.

   ![pba_af_event.png](https://files.readme.io/394f43890d1aaf09114054a3bca1a003178526e768a5da0b554dbc8d63ef1eb4-360003502238.png)
6. Look for a network request that starts with destination wa.appsflyer.com (see screenshot below).
7. Ensure that:
   1. The status code is 200.
   2. The Request Payload aligns with the parameters in the event.

</Accordion>

## Examples

<div id="recording-events::f1e16eae" />

<Accordion title="Recording events">

The code provided is for illustrative purposes only. Don't use this code as-is.

* Assumptions: The Web SDK is already loaded by the page by the time the event is sent.
* The example scenarios contain the code for recording events when:
  * a landing page loads.
  * users interact with the website.

<Accordion title="Native event recording">

**Recording events when a landing page loads**

* You have a subscription page for newsletters and want to record subscriptions.
* You can also set up a thank you page and redirect users to it after they subscribe.

```html
<html>
    <head>
        {/* Assume that the server returns a response with details about the newly subscribed user */}
        {/* Alternatively, you can extract data from localStorage or cookies,
            in case data was set in either of them during the subscription process */}
        <script>window.onload = function(){
            AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion', eventValue: {'label' : 'newspaper'}, eventName: 'subscription',}); } </script> </head> <body> <h1>Thank You for Subscribing to Our Newsletter</h1> </body> </html>
```

* The preceding code contains a basic HTML page. The web page needs to load the Web SDK in order for you to send events.
* Once the page loads, after the user is redirected to it, the window loading method calls the AF() method to send the subscription event to AppsFlyer.

**Recording events when users interact with the website**

* You have an eCommerce website and want to record checkout events.
* When the user clicks on the checkout button, the Web SDK sends an event to AppsFlyer.

```html
<html>
<head>
    {/* Assume that data about products in the shopping cart
    is stored in localStorage */}
    <script>
        window.onload = function () {
            document.getElementById('checkout').addEventListener('click', function () {
                AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
            });
        }
    </script>
</head>
<body>
    <h1>Shopping Cart</h1>
    <h2>Shirt</h2>
    <p>
        <ul>
            <li>Color: Blue</li>
            <li>Quantity: 2</li>
            <li>Price: $20</li>
        </ul>
    </p>
    <h2>Pants</h2>
    <p>
        <ul>
            <li>Color: Black</li>
            <li>Quantity: 3</li>
            <li>Price: $15</li>
        </ul>
    </p>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

The preceding code above shows a basic HTML page. The web page needs to load the Web SDK in order for you to send events.

* Once the page loads, it binds a click listener to the **Checkout** button.
* When the user clicks the **Checkout** button the callback function:
  * fetches data from localStorage.
  * calls the AF() method and passes data to it.
* The AF() method sends the event to AppsFlyer.

</Accordion>

<Accordion title="Tag Manager event recording">

**Recording events when a landing page loads**

* You have a subscription page for newsletters and want to record successful subscriptions.
* You set up a thank you page to which users are redirected after successfully subscribing.

1. Set up a thank you page

   ```html
   <html>
   <head>
       <script>
            // Google Tag Manager loads the Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           }) (window,document,'script','dataLayer','GTM-XXXX');
       </script>
        <script>
           // Assume that the server returns a response with details about the newly subscribed user
           function getResponseFromServer() {
               return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
           }
           //Alternatively, you can extract data from localStorage or cookies,
           //in case data was set in either of them during the subscription process
           localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
       </script>
   </head>
   <body>
       <h1>Thank You for Subscribing to Our Newsletter</h1>
   </body>
   </html>
   ```

   The preceding code loads GTM which in turn loads the Web SDK. Thereafter Two other actions take place in the script. One is a function that gets a response from the server with user details. The other sets data to local storage. GTM has access to both function and localStorage. You can call the function and access localStorage using GTM.
2. Add a new tag for attributing subscriptions after the thank you page loads

   ![Add a new tag for attributing subscriptions in Google Tag Manager](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
3. Give the tag a distinct name and select the **Custom HTML** tag type option.
4. Put the following code in the **Custom HTML**.

   ```html
   <script> 
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'}); </script>
   ```

   ![gtm_tag_after_subscribe.png](https://files.readme.io/6cf080f94a97a7f38c50899a93d154320995e91f60963c075a5dd03b3a080408-360003515298.png)
5. Expand the **Advanced Settings** control, and then the **Tag Sequencing** control below the text area and make sure it is set up to fire the conversion after the tag was executed.

   ![Tag Sequencing settings in Google Tag Manager](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. To fire the conversion tag set a trigger. In the example, the trigger is fired on loading the Thank you page.

   ![Trigger set to fire on the Thank You page load](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

**Recording events when users interact with the website**

* You have an eCommerce website and want to record checkout events.
* After the user clicks on the checkout button, the Web SDK sends an event to AppsFlyer.

1. Setup a checkout page

   ```html
   <html>
   <head>
       <script>
           // Google Tag Manager loads the Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           }) (window,document,'script','dataLayer','GTM-XXXX');
       </script>
   </head>
   <body>
       <h1>Shopping Cart</h1>
       <h2>Shirt</h2>
       <p>
           <ul>
               <li>Color: Blue</li>
               <li>Quantity: 2</li>
               <li>Price: $20</li>
           </ul>
       </p>
       <h2>Pants</h2>
       <p>
           <ul>
               <li>Color: Black</li>
               <li>Quantity: 3</li>
               <li>Price: $15</li>
           </ul>
       </p>
       <button id='checkout'>Checkout</button>
   </body>
   </html>
   ```

   The preceding code loads the Web SDK using GTM The rest is simply HTML that mimics a shopping cart page. Notice the **Checkout** button that has the ID checkout. It is required when setting GTM to handle a click on that button.
2. In GTM, click on **Variables**, click on **Configure** and check **Click Element** in the list of **Built-In Variables.**  

   ![gtm-create-variable.png](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)
3. Create a new variable, give it a meaningful name, and choose the type of **All Elements.**  

   ![gtm-checkout-all-elements.png](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png)
4. In the trigger configuration, choose **Some Clicks**, choose **Click Element** that **matches CSS Selector** of #checkout.  

   ![gtm-checkout-click-elememt.png](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)
5. Create a new tag for the checkout action, choose type Custom HTML, and set the trigger to the checkout trigger.

   ```html
   <script>
    AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'}); </script>
   ```

   ![gtm-checkout-tag.png](https://files.readme.io/8d3f99dcd3c3ff8df9e6fc13076b798237b86f8cbc5bbd26f349fa9948edb0d6-360003431857.png)

</Accordion>

* Make sure the web SDK functions tag is loaded before the event is fired.
* Don't send special characters in event values, like currency symbols in revenue value.
* Value strings should be shorter than 50 characters.

</Accordion>

<div id="setting-customer-user-id-after-signup" />

<Accordion title="Setting customer user ID after signup">

The code provided in these examples is for reference only. Do not use this code as-is. If you are not sure how to use this code, consult your web developer. 

Assumption: The Web SDK is loaded by the page before the event is sent; don't load the SDK again.

User scenario:

* A user signs up to your website.
* The website code gathers the user details and sends it to your server.
* The server generates a unique CUID for the user.
* In the thank you page after signup, you query the server for the new CUID.
* Using the server response, you set AppsFlyer CUID using the Web SDK setCustomerUserId() method.

<Accordion title="Native">

Set up a signup page:

```html
<html>
<head>
    {/* The Web SDK script loads first */}
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        };
    // This function stores the user email sent to the server after the user reaches the thank you page
    // The response from the server is a unique CUID that should be set using the web SDK setCustomerUserId method
        function storeUserEmail (){
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Sign Up</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Name</label>
            <input type="text" name="name" id="name"></div>
        <br />
        <div> <label>Email</label>
            <input type="email" name="email" id="email"></div>
        <br />
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

The preceding code above is a simple signup form. When the form is submitted, the email is stored in localStorage. When the user reaches the thank you page, the user email address is sent to the server to generate the unique CUID for the email address.

Set up a thank you page for users who sign up:

```html
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        // Using the fetch API to send the user email to the server
        // and get the unique user id in return	
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                   res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }  </script> 
     </head> 
     <body> 
        <h1>Thank You for Signing Up!</h1> 
     </body> 
</html>
```

The code makes use of the fetch API. It sends the server the email address entered by the user. Assuming that the server creates a user with a unique CUID upon signup, sending the email address to the server is for the purpose of receiving a unique CUID. The server responds with a unique CUID and this unique CUID is the value that is passed with the setCustomerUserId method.

</Accordion>

<Accordion title="Google Tag Manager">

1. Set up a signup page:

   ```html
   <html>
   <head>
       <script>
            // Google Tag Manager loads the Web SDK
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({
                   'gtm.start':
                       new Date().getTime(), event: 'gtm.js'
               }); var f = d.getElementsByTagName(s)[0],
                   j = d.createElement(s), dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true; j.src =
                       'https://www.googletagmanager.com/gtm.js?id=' + i + dl; f.parentNode.insertBefore(j, f);
           }) (window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');

       // This function stores the user email to be sent to the server after the user reaches the thank you page
       // the response from the server is a unique CUID that should be used in the web SDK setCustomerUserId method
           function storeUserEmail (){
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
   </head>
   <body>
       <h1>Sign Up</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Name</label>
               <input type="text" name="name" id="name"></div>
           <br />
           <div> <label>Email</label>
               <input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
   </body>
   </html>
   ```

   The code above is a simple signup form. When the form is submitted, the email address is stored in localStorage. When the user reaches the thank you page, the user email address is sent to the server to get the unique CUID for that email.
2. Set up a thank you page for users who sign up:

   ```
   (t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
   t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
   o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
   p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
       </script>
       <script>
           // using the fetch api to send the user email to the server
           // and get the unique user id in return 
           window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
                  res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
           } </script> 
       </head>
       <body> 
               <h1>Thank You for Signing Up!</h1> 
        </body> 
    </html>
   ```

   The preceding code is a thank you page having a GTM trigger that sends the server the email address provided by the user in the signup form.  
   Assuming that on signup, the server creates a user with a unique CUID.  
   Sending the email to the server is for the purpose of receiving a unique CUID.  
   The server responds with a unique CUID which is sent using the setCustomerUserId() method.  
   Continue this procedure to create the trigger and tab.
3. Add a new tag, for attributing subscriptions, after the thank you page loads.
   ![Add a new tag for attributing subscriptions in Google Tag Manager](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. Give the tag a distinct name and select the “Custom HTML” tag type option
   ![GoogleTag.jpg](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

   ```html
   <script>
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
            res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
   </script>
   ```
5. Expand the **Advanced Settings** control and then the **Tag Sequencing** control below the text area and make sure it is set up to fire the conversion after the tag was executed

   ![Tag Sequencing settings in Google Tag Manager](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. Set a trigger for the conversion tag to indicate when the conversion tag should be fired (in the below example it is fired on “Thank you” page load)

   ![Trigger set to fire on the Thank You page load](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Accordion>

The setCustomerUserId function can be sent at any stage in the user flow, for example, after user login and signup. AppsFlyer uses the most recent CUID sent to update the current observed user for past or future touchpoints and events.

Use the same CUID value as you do in the setCustomerUserd function in the mobile app (see mobile setCustomerUserId for: [iOS](/docs/customer-user-id-field-cuid#setting-the-cuid), [Android,](/docs/customer-user-id-field-cuid#setting-the-cuid) Unity)

</Accordion>

## Addtional information

<div id="web-sdk-cookies" />

<Accordion title="Web SDK cookies">

The cookies listed in the table that follows are set or used by Web SDK on your website.

In the table the following abbreviations are used:

* AMP: Accelerated Mobile Pages
* CDN: Content Delivery Network
* 3PC: Third-party Cookies

| Cookie name | Domain | Lifespan | When used | Details |
| --- | --- | --- | --- | --- |
| afUserid | Your website domain | 395 days | non-AMP | Identify a user in the context of web load and navigation events |
| AF\_SYNC | Your website domain | 1 week | non-AMP | <ul><li>Flag indicating that a final user identifier is set</li><li>This is used to reduce site load times</li></ul> |
| af\_id | appsflyer.com | 395 days | non-AMP when 3PC permitted | Identify a user in the context of app launch and navigation events |
| af\_id | onelink.me | 395 days | non-AMP when 3PC permitted | Link banner engagements, onelink engagements, or both to app launch events. |
| amp-afUserid | AMP CDN or your website domain | 1 year | For pages service by AMP |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | Your website domain | 395 days | Stores the PBA consent state. Prevents SDK operation until user consent is granted. Not set by default—used only when [consent gating](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) configured. | non-AMP |

</Accordion>

<div id="release-notes" />

<Accordion title="Web SDK release notes">

| Date | Version | Notes |
| --- | --- | --- |
| 2021-07-01 | 1.0 | [Discard query params](/docs/pba-web-sdk-integration-guide#discard-query-params) |
| 2021-06-01 | 1.0 | [Implement a Content Security Policy (CSP)](/docs/pba-web-sdk-integration-guide#implement-a-content-security-policy-csp-policy) |
| 2020-08-31 | 1.0 | [Added opt-in and opt-out functionality](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) |
| 2020-04-16 | 1.0 | The customerUserId() function replaces the IDENTIFY event for sending the unique CUID |
| 2020-07-30 | 1.0 | <ul><li>Explicit start/stop control to send events</li><li>Changing the default initial state</li></ul> |

</Accordion>

<div id="deprecations" />

<Accordion title="Deprecations">

* A deprecation notice provides a heads up of our intention to stop supporting a feature or method. The feature or method continues to work until its sunset date.
* Regard deprecation notices as an opportunity to make changes to your code.

| Deprecation date | Sunset date | Details |
| --- | --- | --- |
| 2020-04-16 | To be announced | **Deprecated method:** Sending the customer user ID (CUID) in the event parameter customUserId with the eventType set to "IDENTIFY"<br /><br />**Current method:** Send the CUID using the setCustomerUserId() function. |

</Accordion>

<div data-zendesk-anchors="h_01HFKCMH8HAW5DN4K9H1A5Q2NJ=web-sdk-user-and-integration-guide step-2-select-a-code-snippet=selecting-a-code-snippet h_01KP11XJV8RDV378GMFF0DVZ8V=selecting-a-code-snippet standard=standard-web-sdk h_01KP11XJV8MN64YV17D1M0T5B9=standard-web-sdk h_01KP3CJBZWK17M58W9M2EP8VC3=standard-without-smart-banners h_01KP3CJBZWKW1K9P9V1XGYM5ED=standard-with-smart-banners h_01KP11XJV8ZGF4SDXJH6FKX18E=advanced-sdk-verification h_01KP3CJBZWP7HDJ0GE2DF3TTE3=advanced-verification-without-smart-banners h_01KP3CJBZWJWS9H0XVHQFF758B=advanced-verification-with-smart-banners h_01HFKCMH8HCDNGFJEN32BNA9F2=integrating-the-web-sdk-into-the-website h_01HFKCMH8HVTJX37PD22ZFV0AY=installation-and-integration h_01HFKCMH8H0JBGD2GWY127428R=considerations-and-actions-required h_01HFKCMH8HC064MHGH8D66QCYK=javascript-code-snippet h_01HFKCMH8HST7G880G44WXXXB6=to-install-the-web-sdk-without-smart-banners h_01HFKCMH8HX4SQP6YCBHJH4AX5=to-implement-the-web-sdk-with-smart-banners h_01HFKCMH8JMMPMHFR4399QPRJV=create-a-property-in-adobe-experience-cloud h_01HFKCMH8J8WVHP7RZ2ENHGY9V=add-the-web-sdk-to-the-adobe-launch-property h_01HFKCMH8J2MAXJ3YVHJ2AJHWQ=add-the-adobe-launch-tag-to-the-website h_01HFKCMH8JWE1Q2749N54MAYRT=publish-the-adobe-launch-environment h_01HFKCMH8JFQQG0BEQ5CATGQ2P=ensure-that-the-sdk-is-working h_01HFKCMH8JCHH5WB5XRC8029DE=sending-events-optinoptout h_01HFKCMH8JSJR95Y9KNANABBKR=sdk-initial-state-setting h_01HFKCMH8JG2C43P8QZ0SKZCBB=explicit-control h_01HFKCMH8J9XDX87ES4F5WW4GJ=implement-a-content-security-policy-csp-policy h_01KGJCGCQ0QB7NK6YNZT5XJVJY=content-security-policy-csp h_01KP11XJV88YB2NSBZJTX9K7ZQ=advanced-sdk-verification-with-csp-nonce-snippets h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners h_01HFKCMH8JG40DT9NHXG6TPMJ1=discard-query-params h_01HFKCMH8JYSV81BEY5XQRZ24Y=query-discard-options h_01HFKCMH8JZCKH1JPTGBVJ3QP4=principles-of-event-recording h_01HFKCMH8JEDEDC48AH5A2797D=conversion-and-standard-events h_01HFKCMH8JYYB7HG2W8XQ7RFPD=conversion-events h_01HFKCMH8JQHSJF3T8SF4ZES7W=standard-events h_01HFKCMH8J79VD5BX96ANAYAFQ=recording-events h_01HFKCMH8JPJZQ81TYZX5PDF91=identifying-users-using-customer-user-id-cuid h_01HFKCMH8JYPNHJGYVRK1SZFYB=web-sdk-event-parameters h_01HFKCMH8J35YT2448PX8ZRM5P=recording-event-scenarios h_01HFKCMH8JQS3CTE6NTZY4G8ZR=online-store h_01HFKCMH8J1EDH3XM5V4ECYCPS=ensuring-that-events-are-sent h_01HFKCMH8J4KQSZ489TMDEN426=examples h_01HFKCMH8JAK25DZ1BZDFS4THD=recording-events::f1e16eae h_01HFKCMH8J4XNY5B9MKAS81T6Z=setting-customer-user-id-after-signup h_01HFKCMH8KJDZ0A15RMQ8BDMDH=addtional-information h_01HFKCMH8KV3QD9CPBSVWM3EVE=web-sdk-cookies h_01HFKCMH8KGJTE7BMK4VSQJF33=release-notes h_01HFKCMH8KP1SHA21JZA5PTZXG=deprecations" />

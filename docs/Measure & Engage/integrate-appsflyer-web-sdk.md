---
title: "Integrate AppsFlyer Web SDK"
excerpt: "Install the AppsFlyer Web SDK on your website to report user visits and events, and set a persistent customer user ID to unify journeys across platforms."
---
The Web SDK lets you record how visitors interact with your website and sends this information to AppsFlyer. It is a 40–60 KB plug-in module that reports user visits and actions on your website to the AppsFlyer platform.

### Integrate the SDK manually

Follow the steps below to complete your Web SDK integration from installation through validation and privacy controls.

1. [Obtain your keys.](#1-obtain-your-keys) Obtain the Web SDK ID (also known as Web Dev Key).
2. [Select a code snippet.](#2-select-a-code-snippet) Choose the snippet that matches your integration type and security requirements.
3. [Deploy the Web SDK.](#3-deploy-the-snippet) Deploy the SDK using a native snippet, Google Tag Manager, or Adobe Launch Tag Manager.
4. [Make sure the SDK is working.](#4-make-sure-the-sdk-is-working) Validate that the SDK sends requests by checking network calls in the browser developer tools.
5. [Set and record events.](#5-set-and-record-events) Define and send custom events on page load or user interaction using native JavaScript or Google Tag Manager.
6. [Set the customer user ID.](#6-set-customer-user-id) Set a persistent CUID to unify web activity with other platforms.
7. [Manage privacy.](#7-manage-privacy) Control measurement opt-in or opt-out, and configure security and data filtering (Content Security Policy and query-parameter discarding).
8. [Web SDK cookies reference.](#web-sdk-cookies-reference) Review the cookies the Web SDK sets or uses, including purpose, lifespan, and scope.

## 1. Obtain your keys

**Obtain the Web SDK ID (also known as Web Dev Key):**

1. In AppsFlyer, from the top menu, open **App Settings**.
2. From the app selector at the top of the page, select your web app (your website domain with the "website-" prefix).
3. Under **SDK authentication**, copy the **Web SDK ID**.

**Obtain the Smart Banner key (if needed):**

1. In AppsFlyer, from the side menu, open **Engage** > **Web to App** > **Smart Banners**.
2. Copy the required Smart Banner Key.

## 2. Select a code snippet

Choose the snippet that matches your integration type and security requirements. Two options are available:

- [Standard Web SDK](#standard-web-sdk): The standard integration.
- [Advanced SDK Verification](#advanced-sdk-verification): An enhanced integration that adds supply-chain protection for the Web SDK. Use this to add an extra layer of security against CDN compromise, DNS hijacking, and man-in-the-middle attacks.

If you are transitioning from the Standard Web SDK to Advanced SDK Verification, replace your existing snippet with the new one. Do not add the new snippet on top of the existing one.

### Standard Web SDK

Use this snippet to deploy the standard Web SDK integration. Paste it near the top of the `<head>` tag on all pages where you want to load the SDK.

<Tabs>
<Tab title="Without Smart Banners">

```javascript
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  // Replace WEB_DEV_KEY with your Web SDK ID
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
</script>
```

</Tab>
<Tab title="With Smart Banners">

```javascript
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  // Replace WEB_DEV_KEY with your Web SDK ID
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba,banners&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
  AF('banners', 'showBanner');
</script>
```

</Tab>
</Tabs>

### Advanced SDK Verification

Advanced SDK Verification adds supply-chain protection for the Web SDK. It makes sure that the code running in your users' browsers is exactly what AppsFlyer published. The SDK source code itself is identical to the standard integration; only the delivery and verification mechanisms differ.

The Advanced SDK Verification:

- Adds an extra layer of security against CDN compromise, DNS hijacking, and man-in-the-middle attacks.
- Adds approximately 250ms to the SDK loading time.

Advanced SDK Verification is optional. The standard integration remains fully supported and is the market standard for third-party analytics pixels. Advanced SDK Verification provides an additional layer of protection beyond that standard.

If your website enforces a Content Security Policy (CSP) using a nonce, see [Content Security Policy (CSP)](#content-security-policy-csp) in the Manage privacy section for the nonce-extended variant of this snippet.

<Tabs>
<Tab title="Without Smart Banners">

```javascript
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
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

</Tab>
<Tab title="With Smart Banners">

```javascript
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
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

</Tab>
</Tabs>

## 3. Deploy the snippet

Deploy the snippet you selected in Step 2 using one of the following methods. Make sure the SDK loads once per page load.

<Tabs>
<Tab title="Option A: Add directly to your website">

Repeat this on all pages:

1. In the snippet from Step 2, replace `WEB_DEV_KEY` with your Web SDK ID (and `YOUR_BANNER_KEY` if applicable).
2. Paste the snippet near the top of the website's `<head>` tag.

</Tab>
<Tab title="Option B: Deploy via Google Tag Manager (GTM)">

Make sure the SDK loads once per page load and set it to load as soon as the page loads using GTM prioritization.

1. Open Google Tag Manager.
2. Create a new tag for the AppsFlyer Web SDK.
3. Select the **Custom HTML** tag type.
4. Give the tag a meaningful name.
5. Paste the snippet from Step 2 into **Tag Configuration**.
6. Click **Save**.
7. Add a trigger:
   - For all pages:
     1. Click **Add Trigger**.
     2. Select **All Pages**.
     3. Click **Save**.
     4. Enter a tag name, then click **Save**.
   - For specific pages:
     1. Click **Save Tag**.
     2. In the GTM main window, select **Triggers**. Click **New**.
     3. Click the pen icon.
     4. Choose the **Page View** trigger type.
     5. Select **Some Page Views**.
     6. Set the page and trigger conditions as needed.
     7. Click **Save**.
     8. Associate the trigger to the AppsFlyer Web SDK tag:
        1. In the **GTM** main window, select **Tags**.
        2. Select the tag you created earlier.
        3. In the triggering panel, click the pen icon.
        4. Select the page view trigger you created earlier.
        5. Click **Save**.

> 🚧 GTM Custom Templates
>
> GTM Custom Templates are not supported for Advanced SDK Verification, because their sandboxed environment does not allow setting the integrity attribute required for verification. Use the **Custom HTML** tag type instead.

</Tab>
<Tab title="Option C: Deploy via Adobe Launch Tag Manager">

#### Create a property in Adobe Experience Cloud

1. Open Adobe Experience Cloud > Launch.
2. Under Adobe Experience Cloud Launch, click **Go to Launch**.
3. Click **New Property**.
4. Name the property.
5. Under **Platform**, select **Web**.
6. Enter your website domain.
7. Click **Save**.

#### Add the snippet to the Adobe Launch property

1. On the **My web property** page, select the **Rules** tab.
2. Name the rule. Recommended: Load web SDK.
3. In the **IF** section, under **Events**, click **Add**.
   - Under **Event Type**, select **Core – DOM Ready**.
   - Click **Keep Changes**.
4. In the **THEN** section, under **Actions**, click **Add**.
   - Under **Action Type**, select **Custom Code**.
   - Select **JavaScript** > **Open Editor**, and paste the snippet from Step 2 (without any wrapper lines).
   - Click **Keep Changes** to close the code editor.
5. Click **Save**.

#### Add the Adobe Launch tag to the website

1. On the **My web property** page, select the **Environments** tab.
2. Find the row with the environment you want to publish (development or production).
3. Under the **Install** column, click the box icon on the relevant row.
4. In the **Web Install Instructions** dialog, copy the script code snippet and close the dialog.
5. Paste the code snippet into the website head section.

#### Publish the Adobe Launch environment

1. On the **My web property** page, go to the **Publishing** tab.
2. Under the **Development** section, click **Add New Library**.
   - Name the library and choose an environment.
   - Under **RESOURCE CHANGES**, click **Add a Resource**.
   - Click **Rules** > **Load web SDK** > **Latest** > **Select & Create a New Revision**.
   - Click **Save**.
3. Under the **Development** section:
   - Next to the newly created library, click the Action menu (3 dots) > select **Build for Development**.
   - Click the action menu again > select **Submit for Approval**.
4. Under the **Submitted** section:
   - Click the action menu > select **Build for Staging**.
   - Click the action menu again > select **Approve for Publishing**.
5. Under the **Approved** section:
   - Click the action menu > select **Build & Publish to Production**.

</Tab>
</Tabs>

## 4. Make sure the SDK is working

After installation, verify that the SDK sends requests by checking network requests in your browser's developer tools.

<Image src="https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png" alt="DevTools screenshot" />

**To make sure the SDK is working, follow these steps:**

1. Open the website.
2. Open the browser developer tools.
3. Go to the (A) **Network** tab.
4. Refresh the page.
5. Filter by (B) `appsflyer`. Two requests may appear:
   - **SDK loader** — Request URL starts with `https://websdk.appsflyersdk.com`. This confirms the SDK script loaded correctly.
   - **Event data** — Request URL starts with `https://wa.appsflyer.com/events`. This confirms the SDK is sending event data to AppsFlyer.
6. Select the (C) **events** message (the `wa.appsflyer.com` call).
7. Under Headers, (D) make sure:
   - Request URL starts with `https://wa.appsflyer.com/events?site-id=`.
   - `site_id` query parameter = `WEB_DEV_KEY`.
   - Status code is 200.
8. Verify `site_id` matches the `WEB_DEV_KEY` in AppsFlyer > top menu > **My Apps**.
9. Verify that the SDK loads only once. Multiple SDK loading can cause the SDK to stop functioning.

For a real-time, visual way to confirm your Web SDK installation and validate that your events fire correctly, use the Web SDK Test page.

## 5. Set and record events

After initializing the Web SDK, you can move from measuring basic visits to capturing specific user actions. This section guides you through defining and recording custom events, like purchases or sign-ups, using either **native JavaScript** or **Google Tag Manager**.

### Set events

Events are the fundamental building blocks of web measurement, representing specific user actions that hold value for your business. To record these interactions, you must define the logic and parameters for each event, making sure that the correct event parameters, such as revenue and custom metadata, are passed to the AppsFlyer platform.

**Example event (purchase event with associated revenue)**

```javascript
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name", "af_customer_event_id": "evt-abc-001"}});
```

#### Web SDK event parameters table

| Parameter name | Mandatory | Description |
| --- | --- | --- |
| `eventType` | Yes | Event type. Format: String. Always populate this parameter with `EVENT`. Example: `eventType: "EVENT"` |
| `eventName` | Yes | Event name. Format: String. Example: Purchase, Subscription |
| `eventRevenue` | No | Revenue assigned to a conversion event. Format: Float |
| `eventRevenueCurrency` | No | Revenue currency. 3 character ISO 4217 currency code. Default: USD. Format: String |
| `eventValue` | No | Map of event parameters describing the event. Use this parameter to send rich in-app events like product SKU and line item price. Format: JSON. Example: `{"sku": "ABC123", "color": "blue", "unit_price": 3.99, "currency": "USD"}` Limitation: 3000 characters (truncated if exceeded). |

### Record events on page load

This is the standard approach for conversions that end with a redirect, like a **Thank You** or confirmation page.

You can implement this trigger either by adding a window loading method to your **native JavaScript** or by configuring a page view trigger within **Google Tag Manager**.

The following code examples are for illustrative purposes. **Do not use this code as-is**; adapt it to your site's specific structure.

<Tabs>
<Tab title="Example: Record event via AF Web SDK">

This approach is ideal for recording conversions that occur via redirects, such as a Thank You page for a newsletter subscription.

**Use Case:** A user completes a newsletter signup and is redirected to a confirmation page. You want to record the subscription event as soon as that page is visible.

**Native page load example:**

```javascript
window.onload = function(){
  AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion'}, eventName: 'subscription'});
}
```

**How it works:**

1. The page loads the necessary content.
2. Once the window is fully loaded (`window.onload`), the script automatically calls the `AF()` method.
3. The **subscription** event, along with its associated metadata (category and label), is sent directly to AppsFlyer.

</Tab>
<Tab title="Example: Record event via GTM">

This approach is used to record successful conversions, such as a newsletter subscription, by firing a tag when a "Thank You" page loads.

#### 1. Set up a Thank You page

The following HTML structure loads GTM, which in turn loads the Web SDK. It also demonstrates how data can be made available to GTM via functions or `localStorage`.

```javascript
<html>
<head>
    <script>
        // Google Tag Manager loads the Web SDK
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-XXXX');
    </script>
    <script>
        function getResponseFromServer() {
            return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
        }
        localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
    </script>
</head>
<body>
    <h1>Thank You for Subscribing to Our Newsletter</h1>
</body>
</html>
```

#### 2. Configure the GTM tag

1. Create a new tag in GTM and select the **Custom HTML** tag type.
2. Provide a distinct name (for example, "AF Subscription Event").
3. Paste the following script into the HTML text area:

```javascript
AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'});
```

4. Expand **Advanced Settings** > **Tag Sequencing**. Make sure it is configured to fire after the main Web SDK initialization tag.
5. Set a trigger for this tag to fire on the **Page View** of your "Thank You" page.

</Tab>
</Tabs>

### Record events on user interaction

Use this to measure actions without a page reload (button clicks, downloads, add-to-cart).

These interactions are typically handled by binding a click listener to a **native HTML element** or by using **Google Tag Manager** variables to identify and measure specific element IDs or CSS selectors.

The following code examples are for illustrative purposes. **Do not use this code as-is**; adapt it to your site's specific structure.

<Tabs>
<Tab title="Example: Record event via AF Web SDK">

Use this method to measure specific actions users take on a page, such as clicking a **Checkout** or **Download** button.

**Use Case:** You operate an ecommerce site and want to capture a **checkout** event the moment a user clicks the **Checkout** button in their shopping cart.

**Native user interaction example:**

```javascript
<html>
<head>
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
    <button id='checkout'>Checkout</button>
</body>
</html>
```

**How it works:**

1. When the page loads, the script attaches a **click** event listener to the element with the ID `checkout`.
2. When the user clicks the button, the callback function is triggered.
3. The function can fetch relevant data (for example, from `localStorage`) and pass it into the `AF()` method.
4. The SDK then transmits the **checkout** event to the AppsFlyer platform.

</Tab>
<Tab title="Example: Record event via GTM">

This method captures specific actions, such as clicking a **Checkout** button, using GTM's built-in variables and triggers.

#### 1. Set up a checkout page

```javascript
<html>
<head>
    <script>
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-XXXX');
    </script>
</head>
<body>
    <h1>Shopping Cart</h1>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

#### 2. Configure GTM variables and triggers

1. In GTM, click **Variables** > **Configure** and enable **Click Element** in the Built-In Variables list.
2. Create a new User-Defined Variable (Type: **All Elements**).
3. Create a new **Trigger**:
   - Trigger Type: **Click - All Elements**.
   - This trigger fires on: **Some Clicks**.
   - Condition: **Click Element** matches CSS Selector `#checkout`.

#### 3. Create the interaction tag

1. Create a new **Custom HTML** tag for the checkout action.
2. Paste the interaction script:

```javascript
<script>
     AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
</script>
```

3. Assign the "Checkout Click" trigger you created in the previous step.

</Tab>
</Tabs>

### Event implementation best practices

To make sure data accuracy and successful transmission, keep the following technical requirements in mind:

- **Load order:** Make sure the Web SDK functions tag is fully loaded in the page scope before any event calls are made.
- **Data formatting:** Do not include special characters in event values. For example, use numeric values for revenue rather than including currency symbols (use `10.50` instead of `$10.50`).
- **String limits:** Keep your `eventValue` strings concise; values longer than 3000 characters will be truncated.
- **Event deduplication:** We recommend sending `af_customer_event_id` in `eventValue`, with a unique value per event. This matters most when you send the same event through both the Web SDK and the server-to-server (S2S) API. AppsFlyer forwards this value to the ad network, which uses it to deduplicate the server-side event it receives from AppsFlyer against the same event it received from its own pixel.
- **Revenue placement:** Populate `eventRevenue` only on events where money actually moved, such as a purchase or a confirmed subscription. For events that carry a monetary value but aren't realized revenue (e.g., add to cart, initiated checkout, or content view), use af_price and af_currency in eventValue instead. Sending `eventRevenue` on both the checkout and the purchase double-counts revenue in every report.
- **Event naming:** Don't add platform suffixes such as `_web` to event names. Platform is already a dimension in the dashboard and in raw data. Use the same event names as in your mobile app to keep cross-platform reporting unified.

## 6. Set customer user ID

After the implementation of event measurement, set a persistent identity to link web activity with other platforms (mobile, PC, CTV) using `setCustomerUserId` to get a unified view of the user journey across platforms.

**Key rules**

- **Consistency:** Use the same CUID value as your mobile app implementations (see mobile `setCustomerUserId` for: [iOS](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk), [Android](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#setting-the-customer-user-id), [Unity](https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id)).
- **Timing:** You can send CUID at any stage (for example, after login or signup). Set the CUID as early as possible, once you have access to it. Most of the time, this means you need to wait for the user to identify via login or sign-up.
- **Syntax:** Send the value as a string (enclosed in quotation marks). **Example:**`AF('pba', 'setCustomerUserId', '663274')`
- **Privacy:** Do not include personally identifiable information (PII) such as email addresses or phone numbers.

<Tabs>
<Tab title="Example: Setting CUID after signup (native)">

The code provided in these examples is for reference only. Do not use this code as-is. If you are not sure how to use this code, consult your web developer.

Assumption: The Web SDK is loaded on the page before the event is sent; do not load it again.

User scenario:
- A user signs up to your website.
- The website code gathers the user's details and sends them to your server.
- The server generates a unique CUID for the user.
- On the thank-you page after signup, you query the server for the new CUID.
- Using the server response, you set the AppsFlyer CUID using the Web SDK `setCustomerUserId()` method.

#### A sign-up form example

The code below is a simple signup form. When the form is submitted, the email address is stored in `localStorage`. When the user reaches the thank-you page, the user's email address is sent to the server to get the unique CUID for that email.

```javascript
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
        function storeUserEmail() {
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Sign Up</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Name</label><input type="text" name="name" id="name"></div>
        <br/>
        <div><label>Email</label><input type="email" name="email" id="email"></div>
        <br/>
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

#### A thank-you page example

The code uses the Fetch API. It sends the server the email address entered by the user. Assuming the server creates a user with a unique CUID upon signup, sending the email address to the server returns a unique CUID. The server responds with a unique CUID, and this unique CUID is the value that is passed with the `setCustomerUserId` method.

```javascript
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
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }
    </script>
</head>
<body>
    <h1>Thank You for Signing Up!</h1>
</body>
</html>
```

</Tab>
<Tab title="Example: Setting CUID after signup (Google Tag Manager)">

1. Set up a signup page.

The code example below is a simple signup form. When the form is submitted, the email address is stored in `localStorage`. When the user reaches the thank-you page, the user's email address is sent to the server to get the unique CUID for that email.

```javascript
<html>
<head>
       <script>
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({ 'gtm.start': new Date().getTime(), event: 'gtm.js' });
               var f = d.getElementsByTagName(s)[0], j = d.createElement(s),
                   dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true;
               j.src = 'https://www.googletagmanager.com/gtm.js?id=' + i + dl;
               f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');
           function storeUserEmail() {
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
</head>
<body>
       <h1>Sign Up</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Name</label><input type="text" name="name" id="name"></div>
           <br />
           <div><label>Email</label><input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
</body>
</html>
```

2. Set up a thank-you page for users who sign up. The code below is a thank-you page with a GTM trigger that sends the server the email address provided by the user in the signup form. Assuming that on signup the server creates a user with a unique CUID, sending the email to the server returns a unique CUID. The server responds with a unique CUID, which is sent using the `setCustomerUserId()` method.

```javascript
<script>
       window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
               res.text().then(function (id) {
                   console.log(id);
                   AF('pba', 'setCustomerUserId', id);
               });
           });
       }
</script>
```

3. Add a new tag for attributing subscriptions after the thank-you page loads.
<Image src="https://files.readme.io/bfe322d5e9e813f9164ca007897beb03775ee6d5a6343ae87c614bf12bf64ea6-43485615744657.png" alt="Adding a new GTM tag for the CUID conversion event" />

4. Give the tag a distinct name and select the **Custom HTML** tag type option.
<Image src="https://files.readme.io/f7561119a7835026724ef67014324b12e4511098e0a5211e10502f6e5c5f7252-43485615746065.jpg" alt="Naming the tag and selecting the Custom HTML tag type in GTM" />

```javascript
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

5. Expand **Advanced Settings** and then **Tag Sequencing** below the text area, and make sure it is set up to fire the conversion after the tag is executed.
<Image src="https://files.readme.io/0aa688b205b1cad7792f8ad18d32f3c83cb2378ece46c9c3f3efe755a42c5c3a-43485611324049.png" alt="Configuring GTM Tag Sequencing for the conversion tag" />

6. Set a trigger for the conversion tag to indicate when the conversion tag should be fired (in the example below, it is fired on "Thank you" page load).
<Image src="https://files.readme.io/68667653631227d0df81a340818b25b9f7ee670843fb2e1976ec9f972da67127-43485611327633.png" alt="Setting the GTM trigger to fire the conversion tag on Thank You page load" />

</Tab>
</Tabs>

## 7. Manage privacy

Following the implementation of event measurement, you may need to apply specific security and privacy constraints to comply with organizational or regional standards.

### Opt in or opt out of sending events

You can control measurement in two ways:

#### SDK initial state setting (in the snippet)

Determines whether the SDK sends events when the web page first loads or waits until you explicitly tell it to start sending events. This setting is defined in the web snippet.

- Send events: `{pba: {webAppId: "...", measurementStatus:true}}`
- Do not send events: `{pba: {webAppId: "...", measurementStatus:false}}`

If measurementStatus is empty or NULL, AppsFlyer regards it as if measurementStatus:true.

#### Explicit control

Explicit control takes priority over the initial state setting and uses persistent first-party cookies:

- Set on the website domain.
- Expire after a period set by the Web SDK or by the browser.
- Always subject to browser cookie settings.

**Commands**

- Start sending events (opt-in): `window.AF_SDK.PLUGINS.PBA.enableMeasurement()`
- Stop sending events (opt-out): `window.AF_SDK.PLUGINS.PBA.disableMeasurement()`

### Secure and filter data

If your website requires strict security or data privacy protocols, use the following mechanisms to configure how the Web SDK interacts with your environment and your data.

#### Content Security Policy (CSP)

If your website requires JavaScript to be secured by a CSP, the Web SDK supports two approaches depending on your CSP configuration and the snippet you selected in Step 2.

- **CSP using self**: Add `https://websdk.appsflyersdk.com` to your `script-src` allowlist. This works for both the Standard Web SDK and Advanced SDK Verification.
- **CSP using nonce**: If your policy uses `script-src 'nonce-...'`, use the nonce-extended variant of Advanced SDK Verification below. This forwards the nonce to all three script tags that the verification process requires. Replace `{{CSP_NONCE}}` with your server-generated, per-request nonce value.

##### CSP policy compatibility

| Policy | Works | Notes |
| --- | --- | --- |
| `script-src 'self'` | No | External CDN origin not allowed; inline script also blocked. |
| `script-src 'self' https://websdk.appsflyersdk.com` | Partial | Allows loader and SDK, but inline setup script still blocked. |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | Yes | Nonce covers inline script and loader; SDK tag gets nonce forwarded by the loader. |
| `script-src 'nonce-...' 'strict-dynamic'` | Yes (recommended) | Nonce covers inline script and loader; `strict-dynamic` propagates trust to the dynamically injected SDK tag. No CDN origin needed in the allowlist. |

#### Advanced SDK Verification with CSP nonce snippets

<Tabs>
<Tab title="Without Smart Banners">

```javascript
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
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

</Tab>
<Tab title="With Smart Banners">

```javascript
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
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

</Tab>
</Tabs>

#### Discard query parameters

If your URL query parameters contain sensitive information, instruct AppsFlyer to discard them (URLs, referrers, and `header_referer`).

- Discard **all** query parameters: append `af_url=true`
- Discard **specific** parameters: use `af_url_mask=param` (separate multiple params with `;`)

Example:
- Original: `param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`
- Result: `param1=value1&af_url_mask=param2;param3`

## Web SDK cookies reference

The Web SDK sets or uses the following cookies:

| Cookie name | Domain | Lifespan | When used | Details |
| --- | --- | --- | --- | --- |
| afUserid | Your website domain | 395 days | Non-Accelerated Mobile Pages | Identifies a user in the context of web page load and navigation events. |
| AF_SYNC | Your website domain | 1 week | Non-Accelerated Mobile Pages | Indicates that a final user identifier is set. Used to reduce site load times. |
| af_id | [appsflyer.com](http://appsflyer.com/) | 395 days | Non-Accelerated Mobile Pages when third-party cookies are permitted | Identifies a user in the context of app launch and navigation events. |
| af_id | [onelink.me](http://onelink.me/) | 395 days | Non-Accelerated Mobile Pages when third-party cookies are permitted | Links link banner engagements, OneLink engagements, or both, to app launch events. |
| amp-afUserid | AMP CDN or your website domain | 1 year | Accelerated Mobile Pages |  |
| AF_DEFAULT_MEASUREMENT_STATUS | Your website domain | 395 days | Non-Accelerated Mobile Pages | Stores the consent state. Prevents the SDK from operating until the user grants consent. Not set by default. Used only when [consent gating](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) is configured. |
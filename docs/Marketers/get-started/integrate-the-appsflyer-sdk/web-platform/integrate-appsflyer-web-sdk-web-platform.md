---
title: Integrate AppsFlyer Web SDK
hidden: false
deprecated: false
x-zendesk:
  id: 50896216552337
  url: https://support.appsflyer.com/hc/en-us/articles/50896216552337-Integrate-AppsFlyer-Web-SDK
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Web platform
  section_id: 50896333547281
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: []
  labels: []
  promoted: false
  comments_disabled: false
  created_at: '2026-09-15T09:07:44Z'
  edited_at: '2026-09-15T09:07:44Z'
---
**At a glance:** Install the AppsFlyer Web SDK (also known as the pixel) on your website to report user visits and events to AppsFlyer, and set a persistent customer user ID (CUID) to unify journeys across platforms.

## Overview

The Web SDK lets you record how visitors interact with your website and sends this information to AppsFlyer. It is a 40–60 KB plug-in module that reports user visits and actions on your website to the AppsFlyer platform.

### Integrate the SDK manually

 Follow the steps below to complete your Web SDK integration from installation through validation and privacy controls.

1. [Obtain your keys.](#step-1-obtain-your-keys) Obtain the Web SDK ID (also known as Web Dev Key).
2. [Select a code snippet.](#step-2-select-a-code-snippet) Choose the snippet that matches your integration type and security requirements.
3. [Deploy the Web SDK.](#step-3-deploy-the-snippet) Deploy the SDK using a native snippet, Google Tag Manager, or Adobe Launch Tag Manager.
4. [Make sure the SDK is working.](#2-make-sure-the-sdk-is-working) Validate that the SDK sends requests by checking network calls in the browser developer tools.
5. [Set and record events.](#3-set-and-record-events) Define and send custom events on page load or user interaction using native JavaScript or Google Tag Manager.
6. [Set the customer user ID.](#4-set-customer-user-id) Set a persistent CUID to unify web activity with other platforms.
7. [Manage privacy.](#5-manage-privacy) Control measurement opt-in or opt-out, and configure security and data filtering (Content Security Policy and query-parameter discarding).
8. [Web SDK cookies reference.](#web-sdk-cookies-reference) Review the cookies the Web SDK sets or uses, including purpose, lifespan, and scope.

#### Integrate the SDK with an AI coding agent

Instead of manually integrating the Web SDK (see steps below), use
an
AI coding tool (Cursor, Claude Code, Codex, Copilot) to implement
the
entire integration for you. Copy the prompt, replace the two placeholders,
and paste it into your AI coding tool.

This approach streamlines and covers all the steps below, but you
still
need to make sure the SDK works correctly and review your privacy
configuration
afterward.

Before copying the prompt, replace:

* `<WEB_SDK_ID>`: In AppsFlyer, go to
  **App Settings**, select your web app (your website
  domain with the "website-" prefix), and copy the
  **Web SDK ID** from **SDK authentication**.
* `<PRODUCTION_URL>`: Your live site URL, used
  for
  post-deploy verification.

The AI tool builds an event plan from your codebase and waits for
your
approval
before implementing it. Review the plan, confirm that revenue and
currency
values appear only on realized-revenue events, and verify the results
using
the post-deploy verification steps in the prompt.

<Accordion title="AI implementation prompt">

```
# **AppsFlyer Web SDK - AI implementation prompt**

Copy the prompt below into an AI coding tool that can edit your project (Cursor, Claude Code, Codex, Copilot). Before copying, replace two placeholders:

  - <WEB_SDK_ID> - in AppsFlyer, go to My Apps, select your web app (your domain with the website- prefix), and copy the Web SDK ID (also called Web Dev Key) from SDK authentication.
  - <PRODUCTION_URL> - your live site URL, used for post-deploy verification.

Implement the AppsFlyer Web SDK (web attribution pixel) on this website, including the events that matter for my marketing measurement.

My Web SDK ID: <WEB_SDK_ID>

My production URL: <PRODUCTION_URL>

## Step 0 - Config gate

If the Web SDK ID above is missing or still a placeholder, reply ONLY with a short request for it (in AppsFlyer: My Apps > the "website-" prefixed app > SDK authentication > Web SDK ID) and stop. Do not write any code until it is provided. If the production URL is missing, request it in the same reply - it is required for post-deploy verification.

Work with minimal diffs: infer file paths from the repo, change only what this integration requires, and preserve the project's existing patterns.

## Step 1 - Analyze the site first

Before writing any code, review the codebase and build the event plan yourself - do not ask me to list the events:

1. Identify the framework (plain HTML, React, Next.js, Vue, etc.) and where the document <head> is controlled.

2. Discover the conversion actions from the code. Look in, in order of reliability:

   - Existing analytics calls: gtag()/GA4 events, Segment analytics.track(), fbq('track'), dataLayer.push (including ecommerce objects) - these tell you both the actions and where the values (amount, currency, order ID) already live.

   - Commerce logic: checkout/cart modules, order-confirmation and thank-you pages/routes, payment-success callbacks.

   - Auth logic: signup and login flows, and where the internal user ID becomes available in client code.

   - Forms and CTAs: lead forms, subscription/trial starts, downloads.

   - Non-commerce / tool products: if the site has no purchase, cart, checkout, signup, or login flows, do not invent commerce or auth events. Identify the real product actions (e.g. generate, copy, export, download, share, template select, parameter edit) and map those to custom descriptive event names instead.

3. Map each discovered action to the AppsFlyer standard name:

   - completed order / "Order Completed" / purchase_success -> af_purchase (with eventRevenue)

   - signup / register / account created -> af_complete_registration

   - login / signin -> af_login

   - add to cart / "Product Added" -> af_add_to_cart (af_price, no eventRevenue)

   - begin checkout / "Checkout Started" -> af_initiated_checkout (af_price, no eventRevenue)

   - product or content view -> af_content_view

   - subscription started -> af_subscribe; free trial started -> af_start_trial

   - search -> af_search

   Anything with no standard equivalent keeps a descriptive custom name.

4. For each event, identify in the code the exact source of: the amount actually charged (for af_purchase), currency, order/transaction ID, and the user ID. Reuse the same data sources the existing analytics reads from.

5. Check for an existing consent management platform (CMP) such as OneTrust or Didomi. Also flag any homegrown consent toggle or privacy preference stored by the site, and ask me how it should gate measurement rather than deciding for me.

Note: existing analytics are discovery input only - implement AppsFlyer events as direct AF() calls, not relayed through Segment/GA4 with their names.

Then show me the proposed event plan as a table (AppsFlyer event name, trigger + file, revenue/af_price source, dedup ID source) and wait for my approval before implementing. Flag any event where you could not locate the value source instead of guessing.

## Step 2 - Install the SDK snippet

Add this snippet near the top of the <head> on every page, with my Web SDK ID:

<script>

!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){

(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},

t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,

o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),

p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "<WEB_SDK_ID>"}})

</script>

Hard rules:

- Use the snippet verbatim. Do NOT rewrite it as a custom component or wrapper module. Wrapped SDKs can send custom events while the automatic visit (the SDK's LOAD event) never fires - the site then shows zero visits and nothing can be attributed.

- The SDK must load exactly ONCE per page load. In React/Next.js, guard against re-renders and double-mounting (e.g. load it in the root HTML/document template, not inside a component that re-mounts). Multiple loads can stop the SDK from working.

- If the site already loads the AppsFlyer SDK via a tag manager (GTM), do NOT add it in code as well - one loader, not two. Tell me if you find an existing AppsFlyer tag.

- Do NOT implement a page-view or visit event manually. The SDK records visits automatically on load; a hand-rolled "page_view" event will never count as a visit.

- The config key is webAppId (not appId).

- If the site enforces a strict Content Security Policy with nonces, add the nonce to the inline snippet tag AND make sure the policy includes 'strict-dynamic' - the snippet injects the SDK script dynamically, and without 'strict-dynamic' a nonce-only policy blocks it.

## Step 3 - Implement events

Event call format:

AF('pba', 'event', {

  eventType: 'EVENT',            // always the literal string 'EVENT'

  eventName: 'af_purchase',

  eventRevenue: 49.99,           // top level - only on realized revenue

  eventRevenueCurrency: 'USD',   // top level - 3-letter ISO code, defaults to USD if omitted

  eventValue: {                  // JSON metadata, max 1000 characters

    "af_order_id": "TXN-12345",

    "af_customer_event_id": "evt-abc-001"

  }

});

Event rules - follow these exactly:

1. Use AppsFlyer standard event names so cross-platform reporting and funnels align: af_purchase, af_complete_registration, af_login, af_add_to_cart, af_initiated_checkout, af_content_view, af_subscribe. If a mobile app exists, use the SAME event names as the mobile SDK. Never add platform suffixes like "_web".

   Exception - distinct purchase lines: if the site clearly sells distinct product tiers or categories that need separate dashboard breakdowns (e.g. two subscription products), propose split names in the event plan (af_purchase_<tier>) instead of one generic event, and note why. Segmentation via eventValue alone does not show in standard dashboard views. Never send BOTH a tier-level and a generic event for the same purchase - that duplicates data.

2. Revenue goes ONLY in the top-level eventRevenue field, and ONLY on events where money actually moved (completed purchase, completed subscription, confirmed booking). Values inside eventValue (af_revenue, revenue, price, amount, total) are NEVER counted as revenue - putting revenue there is the #1 implementation mistake and results in $0 revenue on every purchase.

3. Always send eventRevenueCurrency with eventRevenue when the currency is not USD - otherwise every amount is recorded as USD.

4. Send the actual single-transaction amount as a plain number: no currency symbols, no cents-as-units, no cart-total-plus-item duplication, no lifetime value.

5. For monetary values that are NOT realized revenue (add-to-cart value, checkout-started value, browsed price): do NOT set eventRevenue. Put the amount in "af_price" and the currency in "af_currency" inside eventValue. Sending eventRevenue on both af_initiated_checkout and af_purchase double-counts revenue.

6. On purchases, include "af_order_id" (the transaction ID) inside eventValue. If the codebase has no real transaction ID at that point, say so in the event plan instead of substituting a placeholder.

7. Include a unique "af_customer_event_id" inside eventValue on every conversion event. The same event name must never fire twice with the same ID - generate it per action and guard against SPA re-renders firing the handler twice. This also deduplicates against any server-side (S2S) stream sending the same conversions.

8. One event per user action. Do not emit two names for the same action, and do not relay the same action through both AppsFlyer and a forwarding layer with different names.

9. For multi-item carts, add an "af_order_info" array inside eventValue - one object per item with keys: sku, revenue (per-unit price), qty, content_name, content_type, content_category, brand. On a purchase, top-level eventRevenue still carries the order total.

10. Events must fire after the SDK snippet has loaded on the page. For conversions that end on a confirmation/thank-you page, fire the event on that page's load; for in-page actions (button clicks in an SPA), fire from the action handler.

11. Sparse payloads - omit irrelevant fields:

    - Do NOT include eventRevenue or eventRevenueCurrency unless money actually moved on that event. Never send eventRevenue: 0 or a default currency "just in case."

    - Do NOT include eventCategory, eventLabel, or any GA/Segment-style fields. They are not part of the AppsFlyer Web SDK event API.

    - Inside eventValue, omit keys whose values are empty string, null, undefined, or false (unless falsehood itself is meaningful for that property).

    - If a parameter is not relevant for a specific event, do not put it in the payload at all. Prefer a minimal object with only the fields that apply.

    - Empty revenue/currency columns in AppsFlyer reports do not mean the client should send zeros or defaults - leave those fields absent.

## Step 4 - Set the Customer User ID (CUID)

Immediately after a user logs in or signs up (and on page loads where the user is already authenticated), call:

AF('pba', 'setCustomerUserId', '<the user's internal ID, as a string>');

Rules:

- Use the SAME identifier the mobile apps pass to setCustomerUserId, if mobile apps exist - this is what stitches one user's journey across web and mobile.

- Use an opaque internal ID. Never an email address, phone number, or other PII.

- Call it as early as possible - events fired before it will not carry the CUID.

- setCustomerUserId by itself does not create a reportable event. Also fire af_complete_registration on signup and af_login on login, after the CUID is set, so those events carry it.

## Step 5 - Consent (only if a CMP exists)

If the site has a consent management platform:

- Initialize the SDK with measurement off: {pba: {webAppId: "<WEB_SDK_ID>", measurementStatus: false}}

- On consent granted: window.AF_SDK.PLUGINS.PBA.enableMeasurement()

- On consent revoked: window.AF_SDK.PLUGINS.PBA.disableMeasurement()

Notes:

- These plugin methods only exist once the SDK script has finished loading, unlike AF(), which is a queueing stub available immediately. Handle that ordering.

- If measurement starts off, no visit is recorded until consent is granted. Call that trade-off out explicitly before implementing it.

If there is no CMP, use the plain snippet (measurement defaults to on).

## Step 6 - Verify

### 6a. Local verification (during implementation)

Run the project, drive a browser (Playwright/Puppeteer, or a browser tool if you have one), and capture BOTH the request payload and the HTTP response status of every call to appsflyer domains. Assert:

- The SDK loader request returns 200 and fires exactly once per page load (navigate between pages and re-render components to prove no double load).

- A request fires on page load with eventType "LOAD" and a populated afWebUserId, and its response is 2xx - this is the visit; without it nothing will attribute.

- Each implemented conversion produces exactly one event request, each returning 2xx, with eventRevenue and eventRevenueCurrency at the top level on purchases, and af_customer_event_id present and unique.

- After a simulated login, subsequent requests carry the customer user ID.

A captured request is NOT proof of success. An event whose response is 4xx was rejected and will never appear in reporting. Report the status code for every event you fire, and never describe an event as verified without one.

If you cannot run a browser, verify statically: the snippet has a single insertion point that cannot mount twice; every event handler fires exactly once per action; revenue and currency are top-level fields; setCustomerUserId is reachable on every authenticated entry path. Say plainly that no response status could be observed.

### 6b. Post-deploy verification on the real domain (mandatory)

Local runs prove the code path, not the production page. Build pipelines and asset processors can strip, defer, or relocate inline scripts, so checking the source file is not enough. After deployment:

- Fetch the production URL and confirm the snippet is present in the SERVED HTML.

- Load the production page in a browser and repeat every assertion from 6a against it.

- Confirm the af_id query parameter on the outgoing requests carries the Web SDK ID exactly - a wrong or truncated ID means events are sent under an ID that does not exist in my account and they will silently go nowhere.

- Use a dedicated QA customer user ID (for example qa_<yyyymmdd>_01) so the run is isolatable in raw data later.

If I have not deployed yet, tell me 6b is still outstanding and give me the exact commands and assertions to run once I do.

### 6c. QA record

Produce a table of the verification run so the rows can be matched in AppsFlyer raw data afterwards, with one line per event: UTC timestamp, event name, CUID, af_order_id, af_customer_event_id, HTTP status. State the UTC start and end time of the whole run, and the UTC time of the deployment if you know it.

## Step 7 - Reading the data back

Include in the report an explicit guide to confirming the events in AppsFlyer, because visits and conversions are different record types and are easy to confuse:

- Visits are recorded automatically and appear in event-level data as SESSION rows with an EMPTY event name and zero revenue - that is the schema, not a fault. First visits and revisits appear in conversion-level data (FIRST_VISIT / REVISIT), not as named events. A sessions-scoped export can never contain in-app events, no matter how correct the implementation is.

- The implemented conversions appear as separate rows with the event name populated (af_purchase, af_login, and so on), with revenue on purchase rows only.

- Any data pulled for a time window BEFORE the deployment cannot contain the new events. Give me the deployment UTC time and tell me to query only after it. Point out that attribution-time fields can be much older than the event time and refer to a prior visit, not to this run.

- State the expected reporting latency, and warn me not to read an empty report inside that window as a failure.

- Tell me the exact filter to use to find the QA run from 6c (time window plus QA CUID), and what a healthy result looks like.

- If events return 2xx but still do not appear after the latency window, say clearly that this is an account-side issue (event not enabled for the web app, reporting scope, or data access) rather than a code defect, and list what I should check in the AppsFlyer UI.

## Output

When done, give me:

- A table of every event implemented: name, trigger location (file), revenue handling, dedup ID.

- Where the snippet was installed and how single-load is guaranteed.

- Where setCustomerUserId is called.

- The QA record table from 6c, and a clear split of what you verified yourself (with response statuses) versus what remains as a manual QA checklist for me (page to open, action to take, request and status to expect).

- The Step 7 guide to reading the data back.

- Anything you could not implement or need from me (e.g. where the user ID lives, which purchase amount field is the final charged total, any value source you refused to guess).

Do not implement anything beyond the AppsFlyer Web SDK integration described here.
```

</Accordion>

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

* [Standard Web SDK](#standard): The standard integration.
* [Advanced SDK Verification](#advanced-sdk-verification): An enhanced integration that adds supply-chain protection for the Web SDK. Use this to add an extra layer of security against CDN compromise, DNS hijacking, and man-in-the-middle attacks.

If you are transitioning from the Standard Web SDK to Advanced SDK Verification, replace your existing snippet with the new one. Do not add the new snippet on top of the existing one.

### Standard Web SDK

Use this snippet to deploy the standard Web SDK integration. Paste it near the top of the `` tag on all pages where you want to load the SDK.

<Accordion title="Without Smart Banners">

```
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

</Accordion>

<Accordion title="With Smart Banners">

```
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

</Accordion>

### Advanced SDK Verification

Advanced SDK Verification adds supply-chain protection for the Web SDK. It makes sure that the code running in your users' browsers is exactly what AppsFlyer published. The SDK source code itself is identical to the standard integration; only the delivery and verification mechanisms differ.

The Advanced SDK Verification:

* Adds an extra layer of security against CDN compromise, DNS hijacking, and man-in-the-middle attacks.
* Adds approximately 250ms to the SDK loading time.

Advanced SDK Verification is optional. The standard integration remains fully supported and is the market standard for third-party analytics pixels. Advanced SDK Verification provides an additional layer of protection beyond that standard.

If your website enforces a Content Security Policy (CSP) using a nonce, see [Content Security Policy (CSP)](#content-security-policy-csp) in the Manage privacy section for the nonce-extended variant of this snippet.

<Accordion title="Without Smart Banners">

```
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

</Accordion>

<Accordion title="With Smart Banners">

```
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

</Accordion>

## 3. Deploy the snippet

Deploy the snippet you selected in Step 2 using one of the following methods. Make sure the SDK loads once per page load.

<Accordion title="Option A: Add directly to your website">

Repeat this on all pages:

1. In the snippet from Step 2, replace `WEB_DEV_KEY` with your Web SDK ID (and `YOUR_BANNER_KEY` if applicable).
2. Paste the snippet near the top of the website's `` tag.

</Accordion>

<Accordion title="Option B: Deploy via Google Tag Manager (GTM)">

Make sure the SDK loads once per page load and set it to load as soon as the page loads using GTM prioritization.

1. Open Google Tag Manager.
2. Create a new tag for the AppsFlyer Web SDK.
3. Select the **Custom HTML** tag type.
4. Give the tag a meaningful name.
5. Paste the snippet from Step 2 into **Tag Configuration**.
6. Click **Save**.
7. Add a trigger:
   * For all pages:
     1. Click **Add Trigger**.
     2. Select **All Pages**.
     3. Click **Save**.
     4. Enter a tag name, then click **Save**.
   * For specific pages:
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

GTM Custom Templates are not supported for Advanced SDK Verification, because their sandboxed environment does not allow setting the integrity attribute required for verification. Use the **Custom HTML** tag type instead.

</Accordion>

<Accordion title="Option C: Deploy via Adobe Launch Tag Manager">

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
   * Under **Event Type**, select **Core – DOM Ready**.
   * Click **Keep Changes**.
4. In the **THEN** section, under **Actions**, click **Add**.
   * Under **Action Type**, select **Custom Code**.
   * Select **JavaScript** > **Open Editor**, and paste the snippet from Step 2 (without any wrapper lines).
   * Click **Keep Changes** to close the code editor.
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
   * Name the library and choose an environment.
   * Under **RESOURCE CHANGES**, click **Add a Resource**.
   * Click **Rules** > **Load web SDK** > **Latest** > **Select & Create a New Revision**.
   * Click **Save**.
3. Under the **Development** section:
   * Next to the newly created library, click the Action menu (3 dots) > select **Build for Development**.
   * Click the action menu again > select **Submit for Approval**.
4. Under the **Submitted** section:
   * Click the action menu > select **Build for Staging**.
   * Click the action menu again > select **Approve for Publishing**.
5. Under the **Approved** section:
   * Click the action menu > select **Build & Publish to Production**.

</Accordion>

## 4. Make sure the SDK is working

After installation, verify that the SDK sends requests by checking network requests in your browser's developer tools.

[![DevTools screenshot](https://files.readme.io/7af40a6fee8bbcd59d204c5bbac888587d97e1ae76278919391e2809fe91b9ff-50896206357009.png)](https://files.readme.io/7af40a6fee8bbcd59d204c5bbac888587d97e1ae76278919391e2809fe91b9ff-50896206357009.png)

**To make sure the SDK is working, follow these steps:**

1. Open the website.
2. Open the browser developer tools.
3. Go to the (A) **Network** tab.
4. Refresh the page.
5. Filter by (B) `appsflyer`. Two requests may appear:
   * **SDK loader** — Request URL starts with `https://websdk.appsflyersdk.com`. This confirms the SDK script loaded correctly.
   * **Event data** — Request URL starts with `https://wa.appsflyer.com/events`. This confirms the SDK is sending event data to AppsFlyer.
6. Select the (C) **events** message (the `wa.appsflyer.com` call).
7. Under Headers, (D) make sure:
   * Request URL starts with `https://wa.appsflyer.com/events?site-id=`.
   * `site_id` query parameter = `WEB_DEV_KEY`.
   * Status code is 200.
8. Verify `site_id` matches the `WEB_DEV_KEY` in AppsFlyer > top menu > **My Apps**.
9. Verify that the SDK loads only once. Multiple SDK loading can cause the SDK to stop functioning.

For a real-time, visual way to confirm your Web SDK installation and validate that your events fire correctly, use the Web SDK Test page.

## 5. Set and record events

After initializing the Web SDK, you can move from measuring basic visits to capturing specific user actions. This section guides you through defining and recording custom events, like purchases or sign-ups, using either **native JavaScript** or **Google Tag Manager**.

<Accordion title="Set events">

Events are the fundamental building blocks of web measurement, representing specific user actions that hold value for your business. To record these interactions, you must define the logic and parameters for each event, making sure that the correct event parameters, such as revenue and custom metadata, are passed to the AppsFlyer platform.

**Example event (purchase event with associated revenue)**

```
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name", "af_customer_event_id": "evt-abc-001"}});
```

<Accordion title="Web SDK event parameters table">

| Parameter name | Mandatory | Description |
| --- | --- | --- |
| `eventType` | Yes | Event type. Format: String. Always populate this parameter with `EVENT`. Example: `eventType: "EVENT"` |
| `eventName` | Yes | Event name. Format: String. Example: Purchase, Subscription |
| `eventRevenue` | No | Revenue assigned to a conversion event. Format: Float |
| `eventRevenueCurrency` | No | Revenue currency. 3 character ISO 4217 currency code. Default: USD. Format: String |
| `eventValue` | No | Map of event parameters describing the event. Use this parameter to send rich in-app events like product SKU and line item price. Format: JSON. Example: `{"sku": "ABC123", "color": "blue", "unit_price": 3.99, "currency": "USD"}` Limitation: 3000 characters (truncated if exceeded). |

</Accordion>

</Accordion>

<Accordion title="Record events on page load">

This is the standard approach for conversions that end with a redirect, like a **Thank You** or confirmation page.

You can implement this trigger either by adding a window loading method to your **native JavaScript** or by configuring a page view trigger within **Google Tag Manager**.

The following code examples are for illustrative purposes. **Do not use this code as-is**; adapt it to your site's specific structure.

<Accordion title="Example: Record event via AF Web SDK">

This approach is ideal for recording conversions that occur via redirects, such as a Thank You page for a newsletter subscription.

**Use Case:** A user completes a newsletter signup and is redirected to a confirmation page. You want to record the subscription event as soon as that page is visible.

**Native page load example:**

```
window.onload = function(){
  AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion'}, eventName: 'subscription'});
}
```

**How it works:**

1. The page loads the necessary content.
2. Once the window is fully loaded (`window.onload`), the script automatically calls the `AF()` method.
3. The **subscription** event, along with its associated metadata (category and label), is sent directly to AppsFlyer.

</Accordion>

<Accordion title="Example: Record event via GTM">

This approach is used to record successful conversions, such as a newsletter subscription, by firing a tag when a "Thank You" page loads.

#### 1. Set up a Thank You page

The following HTML structure loads GTM, which in turn loads the Web SDK. It also demonstrates how data can be made available to GTM via functions or `localStorage`.

```
<html>
<head>
    <script>
        // Google Tag Manager loads the Web SDK
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        }) (window,document,'script','dataLayer','GTM-XXXX');
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

   ```
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'});
   ```
4. Expand **Advanced Settings** > **Tag Sequencing**. Make sure it is configured to fire after the main Web SDK initialization tag.
5. Set a trigger for this tag to fire on the **Page View** of your "Thank You" page.

</Accordion>

</Accordion>

<Accordion title="Record events on user interaction">

Use this to measure actions without a page reload (button clicks, downloads, add-to-cart).

These interactions are typically handled by binding a click listener to a **native HTML element** or by using **Google Tag Manager** variables to identify and measure specific element IDs or CSS selectors.

The following code examples are for illustrative purposes. **Do not use this code as-is**; adapt it to your site's specific structure.

<Accordion title="Example: Record event via AF Web SDK">

Use this method to measure specific actions users take on a page, such as clicking a **Checkout** or **Download** button.

**Use Case:** You operate an ecommerce site and want to capture a **checkout** event the moment a user clicks the **Checkout** button in their shopping cart.

**Native user interaction example:**

```
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

</Accordion>

<Accordion title="Example: Record event via GTM">

This method captures specific actions, such as clicking a **Checkout** button, using GTM's built-in variables and triggers.

#### 1. Set up a checkout page

```
<html>
<head>
    <script>
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        }) (window,document,'script','dataLayer','GTM-XXXX');
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
   * Trigger Type: **Click - All Elements**.
   * This trigger fires on: **Some Clicks**.
   * Condition: **Click Element** matches CSS Selector `#checkout`.

#### 3. Create the interaction tag

1. Create a new **Custom HTML** tag for the checkout action.
2. Paste the interaction script:

   ```
   <script>
     AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
   </script>
   ```
3. Assign the "Checkout Click" trigger you created in the previous step.

</Accordion>

</Accordion>

<Accordion title="Event implementation best practices">

To make sure data accuracy and successful transmission, keep the following technical requirements in mind:

* **Load order:** Make sure the Web SDK functions tag is fully loaded in the page scope before any event calls are made.
* **Data formatting:** Do not include special characters in event values. For example, use numeric values for revenue rather than including currency symbols (use `10.50` instead of `$10.50`).
* **String limits:** Keep your `eventValue` strings concise; values longer than 3000 characters will be truncated.
* **Event deduplication:** We recommend sending `af_customer_event_id` in `eventValue`, with a unique value per event. This matters most when you send the same event through both the Web SDK and the server-to-server (S2S) API. AppsFlyer forwards this value to the ad network, which uses it to deduplicate the server-side event it receives from AppsFlyer against the same event it received from its own pixel.
* **Revenue placement:** Populate `eventRevenue` only on events where money actually moved, such as a purchase or a confirmed subscription. For events that carry a monetary value but aren't realized revenue (e.g., add to cart, initiated checkout, or content view), use af\_price and af\_currency in eventValue instead. Sending `eventRevenue` on both the checkout and the purchase double-counts revenue in every report.
* **Event naming:** Don't add platform suffixes such as `_web` to event names. Platform is already a dimension in the dashboard and in raw data. Use the same event names as in your mobile app to keep cross-platform reporting unified.

</Accordion>

## 6. Set customer user ID

After the implementation of event measurement, set a persistent identity to link web activity with other platforms (mobile, PC, CTV) using `setCustomerUserId` to get a unified view of the user journey across platforms.

**Key rules**

* **Consistency:** Use the same CUID value as your mobile app implementations (see mobile `setCustomerUserId` for: [iOS](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk), [Android](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#setting-the-customer-user-id), [Unity](https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id)).
* **Timing:** You can send CUID at any stage (for example, after login or signup). Set the CUID as early as possible, once you have access to it. Most of the time, this means you need to wait for the user to identify via login or sign-up.
* **Syntax:** Send the value as a string (enclosed in quotation marks). **Example:** `AF('pba', 'setCustomerUserId', '663274')`
* **Privacy:** Do not include personally identifiable information (PII) such as email addresses or phone numbers.

<Accordion title="Example: Setting CUID after signup (native)">

The code provided in these examples is for reference only. Do not use this code as-is. If you are not sure how to use this code, consult your web developer.

Assumption: The Web SDK is loaded on the page before the event is sent; do not load it again.

User scenario:

* A user signs up to your website.
* The website code gathers the user's details and sends them to your server.
* The server generates a unique CUID for the user.
* On the thank-you page after signup, you query the server for the new CUID.
* Using the server response, you set the AppsFlyer CUID using the Web SDK `setCustomerUserId()` method.

#### A sign-up form example

The code below is a simple signup form. When the form is submitted, the email address is stored in `localStorage`. When the user reaches the thank-you page, the user's email address is sent to the server to get the unique CUID for that email.

```
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

```
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

</Accordion>

<Accordion title="Example: Setting CUID after signup (Google Tag Manager)">

1. Set up a signup page.

   The code example below is a simple signup form. When the form is submitted, the email address is stored in `localStorage`. When the user reaches the thank-you page, the user's email address is sent to the server to get the unique CUID for that email.

   ```
   <html>
   <head>
       <script>
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({ 'gtm.start': new Date().getTime(), event: 'gtm.js' });
               var f = d.getElementsByTagName(s)[0], j = d.createElement(s),
                   dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true;
               j.src = 'https://www.googletagmanager.com/gtm.js?id=' + i + dl;
               f.parentNode.insertBefore(j, f);
           }) (window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');
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

   ```
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

   [![Adding a new GTM tag for the CUID conversion event](https://files.readme.io/a8c40e8045dc824c96ca0704471b42465ffacd75b37a926f7ec3a7253095a7c4-50896206358417.png)](https://files.readme.io/a8c40e8045dc824c96ca0704471b42465ffacd75b37a926f7ec3a7253095a7c4-50896206358417.png)
4. Give the tag a distinct name and select the **Custom HTML** tag type option.

   [![Naming the tag and selecting the Custom HTML tag type in GTM](https://files.readme.io/fddcd6db6025b5e50b69c2071134f7d587bb277d57f7a284d579b5655a16e738-50896216533393.jpg)](https://files.readme.io/fddcd6db6025b5e50b69c2071134f7d587bb277d57f7a284d579b5655a16e738-50896216533393.jpg)

   ```
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

   [![Configuring GTM Tag Sequencing for the conversion tag](https://files.readme.io/88fccc39b7c2851729f51296a103c24cbf1a6e948891d28d0c1a12bd3edd1a1c-50896216536209.png)](https://files.readme.io/88fccc39b7c2851729f51296a103c24cbf1a6e948891d28d0c1a12bd3edd1a1c-50896216536209.png)
6. Set a trigger for the conversion tag to indicate when the conversion tag should be fired (in the example below, it is fired on "Thank you" page load).

   [![Setting the GTM trigger to fire the conversion tag on Thank You page load](https://files.readme.io/8e3a166c9dcb95066eb4fe3937c2a339a4874cff3870add68f3c3eecfbfd867e-50896206361233.png)](https://files.readme.io/8e3a166c9dcb95066eb4fe3937c2a339a4874cff3870add68f3c3eecfbfd867e-50896206361233.png)

</Accordion>

## 7. Manage privacy

Following the implementation of event measurement, you may need to apply specific security and privacy constraints to comply with organizational or regional standards.

<Accordion title="Opt in or opt out of sending events">

You can control measurement in two ways:

#### SDK initial state setting (in the snippet)

Determines whether the SDK sends events when the web page first loads or waits until you explicitly tell it to start sending events. This setting is defined in the web snippet.

* Send events: `{pba: {webAppId: "...", measurementStatus:true}}`
* Do not send events: `{pba: {webAppId: "...", measurementStatus:false}}`

If measurementStatus is empty or NULL, AppsFlyer regards it as if measurementStatus:true.

#### Explicit control

Explicit control takes priority over the initial state setting and uses persistent first-party cookies:

* Set on the website domain.
* Expire after a period set by the Web SDK or by the browser.
* Always subject to browser cookie settings.

**Commands**

* Start sending events (opt-in): `window.AF_SDK.PLUGINS.PBA.enableMeasurement()`
* Stop sending events (opt-out): `window.AF_SDK.PLUGINS.PBA.disableMeasurement()`

</Accordion>

<Accordion title="Secure and filter data">

If your website requires strict security or data privacy protocols, use the following mechanisms to configure how the Web SDK interacts with your environment and your data.

#### Content Security Policy (CSP)

If your website requires JavaScript to be secured by a CSP, the Web SDK supports two approaches depending on your CSP configuration and the snippet you selected in Step 2.

* **CSP using self**: Add `https://websdk.appsflyersdk.com` to your `script-src` allowlist. This works for both the Standard Web SDK and Advanced SDK Verification.
* **CSP using nonce**: If your policy uses `script-src 'nonce-...'`, use the nonce-extended variant of Advanced SDK Verification below. This forwards the nonce to all three script tags that the verification process requires. Replace `{{CSP_NONCE}}` with your server-generated, per-request nonce value.

The table below shows which CSP policies are compatible with the nonce-extended variant.

| Policy | Works | Notes |
| --- | --- | --- |
| `script-src 'self'` | No | External CDN origin not allowed; inline script also blocked. |
| `script-src 'self' https://websdk.appsflyersdk.com` | Partial | Allows loader and SDK, but inline setup script still blocked. |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | Yes | Nonce covers inline script and loader; SDK tag gets nonce forwarded by the loader. |
| `script-src 'nonce-...' 'strict-dynamic'` | Yes (recommended) | Nonce covers inline script and loader; `strict-dynamic` propagates trust to the dynamically injected SDK tag. No CDN origin needed in the allowlist. |

CSP policy compatibility

#### Advanced SDK Verification with CSP nonce snippets

<Accordion title="Without Smart Banners">

```
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

</Accordion>

<Accordion title="With Smart Banners">

```
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

</Accordion>

#### Discard query parameters

If your URL query parameters contain sensitive information, instruct AppsFlyer to discard them (URLs, referrers, and `header_referer`).

* Discard **all** query parameters: append `af_url=true`
* Discard **specific** parameters: use `af_url_mask=param` (separate multiple params with `;`)

Example:

* Original: `param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`
* Result: `param1=value1&af_url_mask=param2;param3`

</Accordion>

## Web SDK cookies reference

The Web SDK sets or uses the following cookies:

| Cookie name | Domain | Lifespan | When used | Details |
| --- | --- | --- | --- | --- |
| afUserid | Your website domain | 395 days | Non-Accelerated Mobile Pages | Identifies a user in the context of web page load and navigation events. |
| AF\_SYNC | Your website domain | 1 week | Non-Accelerated Mobile Pages | Indicates that a final user identifier is set. Used to reduce site load times. |
| af\_id | [appsflyer.com](http://appsflyer.com/) | 395 days | Non-Accelerated Mobile Pages when third-party cookies are permitted | Identifies a user in the context of app launch and navigation events. |
| af\_id | [onelink.me](http://onelink.me/) | 395 days | Non-Accelerated Mobile Pages when third-party cookies are permitted | Links link banner engagements, OneLink engagements, or both, to app launch events. |
| amp-afUserid | AMP CDN or your website domain | 1 year | Accelerated Mobile Pages |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | Your website domain | 395 days | Non-Accelerated Mobile Pages | Stores the consent state. Prevents the SDK from operating until the user grants consent. Not set by default. Used only when [consent gating](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) is configured. |
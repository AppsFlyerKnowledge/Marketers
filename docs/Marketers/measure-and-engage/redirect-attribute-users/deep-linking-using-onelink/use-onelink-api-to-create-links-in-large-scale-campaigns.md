---
title: "Use OneLink API to create links in large-scale campaigns"
excerpt: "Learn how to programmatically generate personalized short links at scale to take users from owned media directly into your mobile app."
---
**At a glance:** OneLink API lets you programmatically generate personalized short links at scale, taking users from any owned media—such as SMS, email, web, or QR—directly into your mobile app. Use it to create seamless cross-channel journeys, deepen engagement, and improve conversion.

## About OneLink API

OneLink API is a premium feature that lets you turn any owned channel into a direct path into your mobile app. By generating personalized short links programmatically, you can deliver customized user journeys at scale, deepen engagement, and drive higher conversions across SMS, email, websites, social posts, and more. With OneLink API, you can:

* [Create](https://dev.appsflyer.com/hc/reference/onelink-v2-create-link), [get](https://dev.appsflyer.com/hc/reference/get-onelink-v2-link), [update](https://dev.appsflyer.com/hc/reference/update-onelink-v2-link), and [delete](https://dev.appsflyer.com/hc/reference/delete-onelink-v2-link) short links programmatically.
* Add attribution parameters dynamically for more granular measurement (e.g., media source, campaign, asset…).  
  **Note:** The media source (pid) parameter is mandatory.
* Add personalized redirection and deep linking parameters that enable you to direct users to customized in-app or in-web content, such as a product page, coupon, or promotion.
* Generate large volumes of short links and [QR codes](https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-qr) automatically.
* Customize TTL (Time To Live) and renewal behavior per use case. [Learn more](/docs/bulletin-onelink-short-url-ttls-automatically-extend)
* Enforce strict parameter validation to ensure predictable redirection behavior and reliable measurement.
* [Retrieve quota usage](https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-quota) for consumption management.

> 📘 **Note**
>
> #### Example
>
> A global travel app generates millions of contextual short links daily across CRM, email, and QR experiences. Using OneLink API v2.0, their automation platform builds per-user deep links that respect locale, loyalty tier, and specific in-app destinations — while maintaining governance and consistent measurement across all markets.


## Get started

**To get started using OneLink API, follow the steps below:**

**Prerequisite:** An AppsFlyer account. To access OneLink API, contact your CSM or write to hello@appsflyer.com.

**To set up OneLink API:**

1. Generate the [OneLink API token](/docs/managing-appsflyer-tokens#token-types) (Admin permissions needed).
2. [Create a OneLink template](/docs/create-a-onelink-template#procedures).
3. Copy the Template ID.   
   [![](https://support.appsflyer.com/hc/article_attachments/360019487418)](https://support.appsflyer.com/hc/article_attachments/360019487418)
4. Share the template ID and API token with the developer and have them follow these [instructions](https://dev.appsflyer.com/hc/reference/onelinkapi_v2_overview).

## **Dashboard**

The OneLink API dashboard provides a view of your daily, monthly, and three-month API usage. This helps you monitor your consumption against the monthly quota limit. 

**To view the OneLink API dashboard**: 

In AppsFlyer, from the side menu, select **Engage** > **OneLink API**.

## Use cases

The following use cases highlight common ways to use OneLink API to create seamless, contextual journeys into your app.

### Cross-platform journeys (CTV, desktop, web-to-app)

Generate short-lived or per-session links that help users move seamlessly across devices. Common examples include QR codes on TV spots or “scan to continue” flows on desktop that take users directly to the correct in-app step.

**Value:** Seamless continuity and improved conversion across devices.

### CRM-powered channels (SMS, email, WhatsApp)

Create per-user, personalized short links at send-time for high-intent messages such as price-drop alerts, waitlists, win-backs, bill reminders, or magic sign-in flows.

**Value:** Personalization at scale with consistent attribution.

### Offline and QR-based engagement

Produce scannable links for in-store materials, receipts, packaging, or event signage. You can update destination settings without reprinting physical assets.

**Value:** Dynamic routing and offline attribution without reprinting physical assets.

### Referral and advocate sharing

Enable shareable short links for influencer, creator, or customer referral programs with customizable parameters and attribution-ready routing.

**Value:** Scalable measurement and accurate attribution for referrals.

## **Traits and limitations**

This section lists some of the key OneLink API traits and limitations. See a [complete and detailed list](https://dev.appsflyer.com/hc/reference/onelinkapi_v2_overview).



| Trait | Remarks |
| --- | --- |
| API quota limit | * The limit for using the OneLink API to create, edit, or delete OneLink links is 7.5 million requests per month (UTC timezone), per account.<br />* POST, PUT, and DELETE requests count towards this limit. GET requests and GET QR requests do not count toward the quota.<br />* All requests made after exceeding this quota are not served; the API call receives status code 429 with the message "Monthly quota exceeded".<br />* You can check how much of the quota is used/remaining by either:  <br />  • Visiting the OneLink API page in the AppsFlyer platform to view usage history from the past 4 months, or  <br />  • Using the GET quota API to retrieve your current quota status.  <br />  You can also use the [GET quota API](https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-quota) to trigger internal alerts when your usage nears your defined threshold. |
| Link visibility | * Links created via the API do not appear in the list of OneLink custom links in the AppsFlyer dashboard.<br /><br />  **Best practice:** Save API-created links to a local table, so you can access the links for any future purpose. |


> 📘 **Note**
>
> #### Note
>
> A new version of OneLink API (v2.0) was released in December 2025. The previous version (v1.0) is deprecated and will continue to work until June 2026, after which it won’t be maintained. New integrations should use OneLink API v2.0. For migration guidance, see the Dev Hub [migration guide](https://dev.appsflyer.com/hc/reference/migrate_to_onelink_api_v2).
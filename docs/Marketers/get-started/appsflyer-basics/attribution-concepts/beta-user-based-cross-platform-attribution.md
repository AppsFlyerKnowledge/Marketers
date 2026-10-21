---
title: '[Beta] User-based cross-platform attribution'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Cross-Platform Measurement
    - pm-gil-bouchnik
  created_at: '2025-09-16T13:58:09Z'
  edited_at: '2026-08-12T11:16:09Z'
  id: 39104189339793
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/39104189339793--Beta-User-based-cross-platform-attribution
---
> **At a glance:** Learn what cross-platform user-based attribution is, how it operates, and how to set it in AppsFlyer.

## What is user-based attribution?

User-based attribution is a cross-platform model that relies on a persistent <Anchor target="_blank" href="/marketers/docs/customer-user-id-field-cuid">Customer User ID (CUID)</Anchor> to link conversion events across platforms. Using the CUID, the model attributes all activity to the media source that drove the user’s first conversion or re-engagement event.

> 📘 **Note**
>
> If you want to use cross-platform re-engagement, make sure to continue reading this article, as it covers the foundational attribution model. You can then read cross-platform re-engagement for user-based attribution for specific guidance.

### A cross-platform user journey example

For example, a user clicks a Google web ad, signs up, and completes a purchase on a desktop browser. Later, the same user clicks an Instagram mobile ad, installs the mobile app, and makes another in-app purchase. A week later, the user installs the brand’s CTV app, signs in using the same CUID, and starts a paid subscription there as well.

Because the CUID consistently identifies the user across platforms, and the Google web campaign was the first non-organic launch event associated with that CUID, all subsequent activity - including the mobile app purchase and the CTV subscription - is attributed to the Google campaign.

### User-based vs. device-based attribution

This model addresses a key limitation of **device-based attribution:** treating each device as a separate user and fragmenting the user journey across platforms. By contrast, **user-centric attribution** links events across devices using a persistent CUID, enabling consistent measurement, accurate campaign crediting, and a true understanding of lifetime value across the entire product line.

The following user journey example illustrates the difference between device-centric and user-centric attribution:

[![user-journey.png](https://files.readme.io/892efd3cdcaa15848baefdd50e65dcdc9448d423e4b6787c067dcbdd5c801dd0-39104359761169.png)](https://files.readme.io/892efd3cdcaa15848baefdd50e65dcdc9448d423e4b6787c067dcbdd5c801dd0-39104359761169.png)

A user clicks a Meta ad on the web, is redirected to the advertiser's website, signs up, and creates an account. Later, the same user installs the advertiser's iOS app, logs in, and makes a $50 purchase. A few days later, the user sees a YouTube ad, installs the advertiser's PC app, logs in again, and makes a $100 purchase.

Device-based attribution credits $0 to Meta Ads, while user-based attribution credits $150. The table below shows how this journey would be attributed under each model:

| Purchase in-app event | **Device-Centric Attribution** | **User-Centric Attribution (CUID)** |
| --- | --- | --- |
| **iOS app purchase** ($50) | Attributed to **Organic** (no prior ad click performed on the device) | Attributed to **Meta** (from initial web ad) |
| **PC app purchase** ($100) | Attributed to **YouTube** (based on recent device-level interaction) | Attributed to **Meta** (same user identified via CUID) |
| **Total purchases** ($150) | **$50 to Organic**, **$100 to YouTube** (split across campaigns) | **$150 total** attributed to Meta (single unified source) |

### What makes an event a candidate for cross-platform attribution?

An event is considered a **candidate for cross-platform attribution** if it meets **all** of the following conditions:

* **CUID is present:** The event must include a valid <Anchor target="_blank" href="/marketers/docs/customer-user-id-field-cuid">Customer User ID (CUID)</Anchor> — a persistent, advertiser-provided identifier (e.g., login ID or hashed email) that uniquely identifies a user across devices and platforms.
  * If an event is missing a CUID but shares the same `appsflyer_id`, AppsFlyer can backfill the CUID within a short processing window — up to 4 hours before the first event that arrived with a CUID. For more information, see [The CUID enrichment processing window](#the-cuid-enrichment-processing-window) below.
  * Events that arrive without a CUID and can’t be enriched through the CUID enrichment process are still included in cross-platform attribution. In these cases, attribution is determined using their device-level (classic) attribution method.
* **Belongs to a product line:** The app generating the event must be part of a **product line** – a grouping of related apps (e.g., iOS, Android, CTV) under the same brand, for which attribution is scoped and configured collectively. For more information, see <Anchor target="_blank" href="/marketers/docs/product-line-group-apps-for-cross-platform-attribution#about-product-line">Group apps for cross-platform attribution</Anchor>.
* **Within the inactivity restoration window:** The event must fall within the **inactivity window** – a configurable period (e.g., 7 to 390 days) during which a CUID is still considered active and eligible for attribution within a given product line. If the CUID has not been seen within this window, its previous attribution mapping is discarded.
* **Device-level attribution fields are present:** The event must already contain valid **device-level attribution parameters** (e.g., media source, campaign ID) derived from AppsFlyer’s classic device-based attribution model.

### How is the attribution source determined?

This model attributes all events for a given user (CUID) to the **original media source** that drove the user’s first conversion.

The attributed original media source is determined using the following logic:

* For each in-app event with a CUID in a product line, AppsFlyer identifies the **earliest** launch event for that CUID (i.e., a launch event with a valid media source).
* The media source attributed to that launch event by classic device-centric attribution is considered the attribution source for the in-app event.
* This media source is used as the **user acquisition cross-platform attribution source** for all subsequent events associated with that CUID and product line.
* If an in-app event lacks a CUID, AppsFlyer attempts to backfill it during the 1–4 hour [enrichment processing window](#the-cuid-enrichment-processing-window).
* If an event without a CUID arrives outside the defined CUID [enrichment window](#the-cuid-enrichment-processing-window), it will still be included in cross-platform attribution. These events are attributed using their device-level (classic) attribution method.

> 📘 **Note**
>
> AppsFlyer only matches identical CUIDs **within the same product line**. We do not attempt to match, infer, or share CUIDs across different product lines or customers. This ensures a strict privacy-first approach, keeping each customer’s data siloed and independent.

#### The CUID enrichment processing window

The CUID enrichment processing window is the period (1–4 hours) during which AppsFlyer processes newly arrived in-app events to backfill missing customer user IDs (CUIDs). This enables cross-platform attribution even if some in-app events arrive without a CUID.

**How does CUID enrichment work**

* Every 1–4 hours, AppsFlyer runs a processing job.
* If an event arrives without a CUID but shares the same `appsflyer_id` as another event with a CUID, AppsFlyer backfills the missing CUID.
* This stitching applies only to events received during the processing window.

**CUID enrichment Example**

* **8:01**: A *first app open* event is recorded with `appsflyer_id = XYZ`.
* **9:00**: A *sign-up* event is recorded with `cuid = 123` and `appsflyer_id = XYZ`.
* **12:00**: The 4-hour processing window ends. AppsFlyer retroactively stitches `cuid = 123` to the *first app open* event.
* **12:30**: A *purchase* event with `appsflyer_id = XYZ`  is recorded but has
* no CUID. Because the event arrives after the window closes, AppsFlyer does not stitch `cuid = 123` to it.

**CUID enrichment Limitations**

* Events without a CUID arriving **outside the 1–4 hour processing window** are attributed using classic AppsFlyer attribution and added to the cross-platform attribution method results.
* CUID stitching is **not applied retroactively** beyond the processing window.

> 👍 **Tip**
>
> To maximize cross-platform matching, always include a CUID in every in-app event sent.

## Set up cross-platform attribution

To set up cross-platform attribution, you need to apply a few settings in AppsFlyer and implement specific SDK functions in your app code.

* **In AppsFlyer**, assign your apps to a product line, opt in to cross-platform attribution, and specify the inactivity restoration window. For more information, see <Anchor target="_blank" href="/marketers/docs/product-line-group-apps-for-cross-platform-attribution#how-to-set-up-a-product-line">Set up a product line</Anchor>.
* **In your app**, set the AppsFlyer SDK to send events with CUIDs. For developer instructions, see [Set Customer User ID](https://dev.appsflyer.com/hc/docs/set-customer-user-id).

## View cross-platform attribution results

* **Report:** To view cross-platform attribution results, see the <Anchor target="_blank" href="/marketers/docs/end-user-events-cross-platform-report-in-data-locker">Data Locker End-user events cross-platform report</Anchor>.
* **My Dashboards:** Available via the "Cross Platform" template. For more information about selecting a dashboard template, see <Anchor target="_blank" href="/marketers/docs/my-dashboards#create-dashboard">Create a custom dashboard</Anchor>.

## Frequently Asked Questions (FAQs)

<Accordion title="Why are cross-platform attribution results different from classic AppsFlyer attribution results?">

There are a few reasons that can explain the differences.

#### Different attribution logic

* **Cross-platform attribution is user-based.** It links activity using the CUID and attributes all subsequent user activity to the user's campaign cohort within the product line.
* **Classic AppsFlyer attribution is device-centric** (one AppsFlyer ID per device). This means the same real-world user on multiple devices or platforms can be counted as separate users and credited to different touchpoints.

**Impact:** Even if overall revenue is similar, revenue by media source or campaign can shift significantly.

#### Different attribution date

* In classic cohort and LTV results, the attribution date reflects the date of the user's first app launch, or, for web, the initial user acquisition date.
* In the cross-platform UA view, the attribution date represents the user's first acquisition date across platforms. When cross-platform re-engagement is enabled, the attribution date reflects the most recent non-organic app launch.

As a result, some metrics in cross-platform attribution can be attributed to earlier dates compared to classic attribution.

</Accordion>

<div data-zendesk-anchors="what-is-userbased-attribution=what-is-user-based-attribution h_01K59D3JXN9P5ZN40WX957CHKC=what-is-user-based-attribution a-crossplatform-user-journey-example=a-cross-platform-user-journey-example h_01K59D3JXN4WJ3HN0AXN58N877=a-cross-platform-user-journey-example userbased-vs-devicebased-attribution=user-based-vs-device-based-attribution h_01K59D3JXN3EXS90N2AX7DXV3B=user-based-vs-device-based-attribution what-makes-an-event-a-candidate-for-crossplatform-attribution=what-makes-an-event-a-candidate-for-cross-platform-attribution h_01K59D3JXNNYZHYFAPRH50E4Z4=what-makes-an-event-a-candidate-for-cross-platform-attribution h_01K59D3JXNGNZYAYPG13SZ98V1=how-is-the-attribution-source-determined h_01K59D3JXN5CYVB6F84DTRBZS9=the-cuid-enrichment-processing-window set-up-crossplatform-attribution=set-up-cross-platform-attribution h_01K59D3JXNH84WMZ6PQ4BVF44B=set-up-cross-platform-attribution view-crossplatform-attribution-results=view-cross-platform-attribution-results h_01K59D3JXNGGG4AKEXM9Q9KA6A=view-cross-platform-attribution-results h_01KNSGZXB1EFD78QSA8B28XCN9=frequently-asked-questions-faqs h_01KNSG79PE8RFRSHYWGTGWN4VV=different-attribution-logic h_01KNSG79PEBXX0H14B9SQZ0W83=different-attribution-date" />

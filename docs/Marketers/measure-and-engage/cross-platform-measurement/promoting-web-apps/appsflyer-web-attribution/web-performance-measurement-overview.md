---
title: Web Performance Measurement - Overview
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T15:07:53Z'
  edited_at: '2026-09-17T11:40:46Z'
  id: 43521734577809
  locale: en-us
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/43521734577809-Web-Performance-Measurement-Overview
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**At a glance:** Web Performance Measurement enables you to identify which media sources and campaigns drive users to your website and measure how those visits influence downstream actions over time. It enables you to capture and attribute user interactions end-to-end, supporting both user acquisition (first-time visitors) and re-engagement, from the initial visit through lifetime value measurement.

## About Web Performance Measurement

Web attribution is the process of identifying which media sources and campaigns drive users to visit a website and influence their subsequent actions.

A web visit represents both a browsing activity and an ad engagement that occurred immediately before the visit. Unlike mobile attribution, where clicks and installs must be matched, a web visit carries marketing source data in the destination URL and header, making the initial match immediate.

The purpose of this article is to outline the end-to-end Web Performance Measurement process, explaining how user interactions are captured, identified, and measured from the initial website visit through to lifetime value. This process enables the engine to support both user acquisition, for identifying and attributing first-time visitors, and retargeting or re-engagement, for measuring the impact of campaigns specifically aimed at returning users.

#### If you use People-Based Attribution (PBA)

If you currently use <Anchor target="_blank" href="/marketers/docs/people-based-attribution-pba">People-Based Attribution (PBA)</Anchor>, consider switching to Web Performance Measurement for more granular attribution and additional signals.

### The Web Performance Measurement flow

The Web Performance Measurement flow follows a structured sequence of steps that transforms raw site visits into actionable marketing insights.

1. [Data collection](#1-data-collection): The system captures user interaction data through either the Web SDK (Pixel) or a Server-to-Server (S2S) API.
2. [Visit recording](#2-visit-recording)[:](/docs/web-performance-measurement-overview#2-visit-recording) Captures the user’s arrival on the website and logs a visit event, even when the traffic source is not yet known.
3. [Media source resolution](#3-media-source-resolution): Identifies the media source by parsing URL parameters in a defined priority order.
4. [The 30-minute identity delay](#4-the-30minute-identity-delay): Delays attribution decision for 30 minutes to allow for identity resolution via user login.
5. [Stitching and identity resolution](#5-stitching-and-identity-resolution): Links the current session to a persistent Customer User ID (CUID) or a browser cookie.
6. [User acquisition event](#6-user-acquisition-ua-event): Records the acquisition-defining event (for example, `first_visit` or a custom acquisition event) within the UA lookback window.
7. [Pre-acquisition period](#7-preacquisition-period): Attributes intermediate events that occur between the first visit and the UA event.
8. [Re-engagement and re-acquisition](#8-reengagement-and-reacquisition): Attributes returning users (revisits) based on inactivity windows and determine whether the return is a re-engagement or re-acquisition.
9. [LTV measurement](#9-ltv-measurement): Attributes ongoing events and revenue to measure the user’s lifetime value, governed by the Attribution Window.

## The Web Performance Measurement process - step by step

The following sections explain each step in detail.

<div id="1-data-collection" />

<Accordion title="1. Data collection">

Once the user arrives at the landing page, AppsFlyer must capture that interaction through an integrated listener.

* **Web SDK (Pixel)**: A client-side snippet <Anchor target="_blank" href="/marketers/docs/integrate-appsflyer-web-sdk">implemented directly on the website or via Google Tag Manager (GTM)</Anchor>.
* **Server-to-Server (S2S) API**: A robust server-side integration that helps bypass browser measurement prevention and ad blockers while allowing you to enrich data before it reaches AppsFlyer. The S2S integration can be done directly from a customer server or via Google Tag Manager Server Side.

</Accordion>

<div id="2-visit-recording" />

<Accordion title="2. Visit recording">

After the session data is collected, the system determines whether to create a first visit record. This record serves as a preprocessing layer that captures raw user activity before the actual media source resolution and attribution. Not every session is recorded as a visit.

AppsFlyer records a visit when someone lands on your site under a new session or with recognizable source parameters, and ignores visits from excluded domains. These visit recording rules prevent double-counting of sessions.

For more information, see <Anchor target="_blank" href="/marketers/docs/about-traffic-source-resolution#step-1-visit-recording">Visit recording</Anchor>.

</Accordion>

<div id="3-media-source-resolution" />

<Accordion title="3. Media source resolution">

After the data is collected and the visit is recorded, the engine evaluates it in a defined priority order. This waterfall supports both AppsFlyer-specific and market-standard parameters, so customers **don’t need to change their existing attribution links during migration**. The first matching signal in the waterfall is used to determine the visit origin.

* **PID**: The system first checks for proprietary AppsFlyer parameters.
* **UTM parameters**: If no PID exists, it looks for standard tags like `utm_source`.
* **Click IDs**: It then searches for network-specific IDs such as Google Click ID (`gclid`) or TikTok Click ID (`ttclid`).
* **Referrer**: As a final fallback, it identifies the URL the user was on immediately before arriving.

For more information, see <Anchor target="_blank" href="/marketers/docs/about-traffic-source-resolution#step-2-media-source-resolution">Media source resolution</Anchor>.

</Accordion>

<div id="4-the-30minute-identity-delay" />

<Accordion title="4. The 30-minute identity delay">

Because most users log in within 30 minutes of a visit, AppsFlyer intentionally delays attribution decisions by that same amount of time. This delay prevents "Organic" misclassification by allowing the system to capture the CUID and correctly link returning users with expired cookies to their original source.

</Accordion>

<div id="5-stitching-and-identity-resolution" />

<Accordion title="5. Stitching and identity resolution">

With the source identified and the 30-minute delay complete, the system moves to "stitching" the user's fragmented sessions into a single journey.

* **CUID Stitching**: If a Customer User ID (e.g. a hashed email) is captured, the engine links the session to the user's cross-device history.
* **Cookie fallback**: If no CUID is available, the system falls back to browser cookies, though they are less stable and device-specific.

</Accordion>

<div id="6-user-acquisition-ua-event" />

<Accordion title="6. User acquisition event">

Once the user's identity is resolved, the engine looks for the specific action that defines them as acquired. The industry standard is the`first_visit`, but this often represents a weak signal—a user might click an ad accidentally or bounce immediately. By setting a custom acquisition event, such as registration or purchase, you ensure that long-term value (LTV) is attributed to the marketing source that drove a meaningful action, not just a curiosity click.

When a user acquisition event occurs, the attribution engine searches backwards for a period equal to the **Lookback window (user acquisition)** to find a non-organic visit to attribute to. This setting defines the maximum time allowed between a user's visit and the completion of the UA event (Default: 30 days). If no non-organic touchpoint is found within this lookback period, the UA event is considered organic and not attributed. You can set the custom event Lookback window duration when you add your web app to AppsFlyer, see <Anchor target="_blank" href="/marketers/docs/configure-web-performance-measurement-settings#lookback-window-user-acquisition">Lookback window (user acquisition)</Anchor>.

Depending on the business model, different events can be defined as the user acquisition trigger, for example

* **Registration completed event (e.g., a banking app)**. The acquisition event is triggered only when the sign-up flow is successfully completed.
* **First order event (e.g., a food delivery app)**. Browsing or adding items does not count; the event fires only after a successful transaction.
* **Subscription-activated event (e.g., a streaming or SaaS app)**. The acquisition event is recorded when the subscription is confirmed, not on trial start or app install.

For more information about setting a user acquisition event, see <Anchor target="_blank" href="/marketers/docs/configure-web-performance-measurement-settings#user-acquisition-settings">User acquisition settings</Anchor>.

</Accordion>

<div id="7-preacquisition-period" />

<Accordion title="7. Pre-acquisition period">

After the system resolves the user’s identity but before they’re acquired, there can be a gap in the journey called the pre-acquisition period. This is relevant only if you define a custom user acquisition (UA) event instead of using the default `first_visit`. In this period, users can take meaningful actions, such as adding items to cart, browsing products, or engaging with content, before they complete the event that officially acquires them, such as registration or a first purchase.

AppsFlyer collects and attributes these pre-acquisition events to the marketing source and flags them in reporting as pre-acquisition. The key difference between pre-acquisition and post-acquisition attribution is the attribution window. During the pre-acquisition period, the attribution window is shorter and matches the UA event lookback window, because these events occur before the UA event that defines the user as acquired. After the custom UA event is triggered and the user is acquired, the attribution window extends to measure lifetime value (LTV), giving long-term credit to the marketing source that acquired the user.

</Accordion>

<div id="8-reengagement-and-reacquisition" />

<Accordion title="8. Re-engagement and re-acquisition">

Once a user is acquired, they may return to the site later. A re-engagement (revisit) attribution is triggered when a returning user clicks an ad and visits your site.

While *re-engagement* focuses on existing users, a return can also be classified as a *re-acquisition* if the user has been inactive for an extended period. To be eligible for re-acquisition, the user must first cross the **Inactivity Window** (default: 90 days), which defines the period of inactivity required to consider them "churned." Once this window has passed, if the user returns, the engine records a new user acquisition event rather than a standard revisit.

For more information, see <Anchor target="_blank" href="/marketers/docs/configure-web-performance-measurement-settings#re-engagement-settings">Re-engagement settings</Anchor> and <Anchor target="_blank" href="/marketers/docs/configure-web-performance-measurement-settings#re-acquisition-settings">Re-acquisition settings</Anchor>

</Accordion>

<div id="9-ltv-measurement" />

<Accordion title="9. LTV measurement">

Whether the user was brought in by an initial acquisition campaign or a subsequent retargeting effort, the final goal is to measure their total value over time. Once a user is successfully attributed to a source, the system measures their ongoing activity to calculate Lifetime Value (LTV).

This measurement is governed by the **Attribution Window**, which is set to "Forever" by default. This ensures that every subsequent action—such as repeat purchases or subscription renewals—is credited back to the original marketing source that drove the user to the site. By capturing this long-term data, you can move beyond simple conversion counts and determine the true Return on Ad Spend (ROAS) for your campaigns.

For more information about setting the **Attribution window**, see the <Anchor target="_blank" href="/marketers/docs/configure-web-performance-measurement-settings#attribution-window">Attribution window</Anchor>.

</Accordion>

<div data-zendesk-anchors="about-web-attribution=about-web-performance-measurement h_01KGMK4P46QE2HQHADD25TPCQF=about-web-performance-measurement if-you-use-peoplebased-attribution-pba=if-you-use-people-based-attribution-pba h_01KH0P7BB9KF19S8XRH49DKMZA=if-you-use-people-based-attribution-pba the-appsflyer-web-attribution-flow=the-web-performance-measurement-flow h_01KGMK4P4614EEQ28V5FV32CY5=the-web-performance-measurement-flow the-appsflyer-web-attribution-process-step-by-step=the-web-performance-measurement-process---step-by-step h_01KGMK4P46HTB82K2PH9V0E33B=the-web-performance-measurement-process---step-by-step h_01KGMK4P46VJ0NF1FKFRS8V6J2=1-data-collection h_01KGMK4P46GWBP56NJM2ENARTR=2-visit-recording h_01KGMK4P46ZKS856R5C5KEQDBK=3-media-source-resolution h_01KGMK4P465777YN9MQ1JYZ7HT=4-the-30minute-identity-delay h_01KGMK4P46GFBZTMHDVW2MD3K1=5-stitching-and-identity-resolution h_01KGMK4P46MBT49ECD7RFHDY3X=6-user-acquisition-ua-event h_01KGMK4P46XYPVFV67F000EM6C=7-preacquisition-period h_01KGMK4P472B4TFGVR4VBH4REH=8-reengagement-and-reacquisition h_01KGMK4P47E9TPX0S26TTPW4CB=9-ltv-measurement" />

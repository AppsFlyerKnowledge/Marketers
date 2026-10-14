---
title: "Server-to-Server (S2S) API for Web Performance Measurement"
excerpt: "The S2S API for Web Performance Measurement lets you send web visits and events to AppsFlyer directly from your server, bypassing browser limitations like ad blockers and cookie restrictions. Use it alongside the Web SDK or on its own to get more complete, higher-quality attribution data."
x-zendesk:
  id: 45670116601617
  url: https://support.appsflyer.com/hc/en-us/articles/45670116601617-Server-to-Server-S2S-API-for-Web-Performance-Measurement
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  position: 8
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, Web Attribution]
  labels: [Web Attribution, Web Attribution SDK, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2026-04-12T15:09:07Z'
  edited_at: '2026-10-04T12:54:37Z'
---
## About the S2S API for web attribution

AppsFlyer supports two ways to send web data for attribution: the Web SDK (client-side) and the S2S API (server-to-server, or S2S). You can use either method independently or combine them depending on your setup and needs.

The Web SDK runs in the browser. The S2S API lets you send the same data from your own backend instead. Here's why that matters: privacy-focused browsers and ad blockers, including Safari ITP, Firefox ETP, and Brave, can block or limit client-side measurement. Industry estimates put browser-level blocking at 25–40% of web users. Because S2S calls originate from your server and never pass through the browser, they're not affected by these restrictions at all.

### How it works

1. A user visits your website or triggers an event in the browser.
2. Your server receives the event.
3. Your server sends the event directly to the AppsFlyer server for attribution.

### Why use S2S

Here's what using the S2S API means for you, broken down by benefit:

* **Measure server-side events:** Some conversions never touch the browser at all, for example, subscription renewals processed on the backend or events originating in a CRM system. S2S is the only way to get these into AppsFlyer and tie them back to the right campaign.
* **Increased measurement coverage:** S2S calls come from your server, not the browser, so ad blockers, Safari ITP cookie limits, and other browser-level restrictions don't apply. You can capture visits and conversions that client-side measurement alone would miss.
* **Data enrichment from the backend:** With S2S, your server can add extra data to events before sending them, including Customer User IDs, hashed email or phone numbers, CRM attributes, subscription status, or any internal identifiers. This improves identity resolution and strengthens signal quality.
* **Security:** Dev keys, user identifiers, and any added data stay on your server and are sent over a secure connection, giving you full control over what leaves your infrastructure.

## API specification

Base URL: `https://events.appsflyer.com`

### Authentication

All requests must include a valid S2S API token and the correct content type in the request headers.

| Header | Type | Description |
| --- | --- | --- |
| `Authorization` | API token | Your S2S API token is included in the Header in the following format:<br /><br />`Authorization: Bearer {s2s-token}` |
| `Content-Type` | string | Must be `application/json`. Required on all requests. |

> 📘 **Note**
>
> To create an S2S API token, see the instructions in [Managing AppsFlyer tokens](/docs/managing-appsflyer-tokens#manage-your-tokens).

### Measure an event

`POST /v2.0/s2s/inapps/app/web/{appId}`

Measures a web event (for example, a purchase, sign-up, or custom action) for a given app.

<Accordion title="Path parameter">

| Parameter | Required | Description |
| --- | --- | --- |
| `appId` | Required | The `unified_app_id` as defined in AppsFlyer. For example: `website-www.example.com` |

</Accordion>

<Accordion title="Request body">

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `user_id` | object | Required | User identifier. Must contain at least one of `customer_user_id` or `appsflyer_id`. |
| `event_name` | string | Required | Event name. 1–64 characters. Cannot contain `@ = + -`. Example: `af_purchase` |
| `event_revenue` | number (double) | Optional | Revenue amount for purchase or monetization events. |
| `event_revenue_currency` | string (ISO-4217) | Optional | Currency code for the revenue value. For example, `USD` or `EUR`. |
| `event_value` | object | Optional | Free-form event parameters. Supports a `custom_parameters` sub-object. |
| `event_url` | string | Optional | Page URL where the event occurred. Valid HTTP URL, max 4,096 characters. |
| `timestamp` | integer (int64) | Optional | Unix time in ms (UTC). If omitted, AppsFlyer uses the receive time. Late acceptance window: events must arrive no later than 00:30 on the next calendar day in the app's timezone. |
| `ip` | string | Optional | Device IP address (IPv4 or IPv6). Max 46 characters. |
| `user_agent` | string | Optional | Full user agent string from the browser. Max 1,024 characters. |
| `http_referrer` | string | Optional | Referrer URL of the current page. |
| `af_customer_event_id` | string | Optional | Your own unique ID for the event, which you use to deduplicate conversions on ad network platforms. AppsFlyer forwards it to the network as the event ID.<br /><br />Send it when either applies:<ul><li>You run a network pixel on your site, alongside AppsFlyer measurement.</li><li>You send the same event through both the Web SDK and this API.</li></ul>When you send it, also send the same value in the network's own pixel event (for example, `eventID` in `fbq()`), so the network counts the conversion once instead of twice.<br /><br />If you omit it, AppsFlyer generates its own ID, and the network can't match your pixel events.<br /><br />**Limits:** Max 256 characters. Matching is exact and case-sensitive. |
| `email_hashed` | string | Optional | SHA256 of normalized (lowercase, trimmed) email. Must be a 64-character hex string. |
| `phone_number_hashed` | string | Optional | SHA256 of phone number. Must be a 64-character hex string. |
| `phone_number_e164_hashed` | string | Optional | SHA256 of E.164 phone number (for example, `+14155552671`). Must be a 64-character hex string. |
| `first_name_hashed` | string | Optional | SHA256 of normalized first name. Must be a 64-character hex string. |
| `last_name_hashed` | string | Optional | SHA256 of normalized last name. Must be a 64-character hex string. |

</Accordion>

<Accordion title="Example request">

```json
{"user_id":{"customer_user_id":"15667737-366d-4994-ac8b-653fe6b2be4a"},"event_name":"af_purchase","event_revenue":49.99,"event_revenue_currency":"USD","af_customer_event_id": "550e8400-e29b-41d4-a716-446655440000","event_value":{"af_content_id":"SKU-001","af_quantity":2,"custom_parameters":{"promo_code":"SUMMER10"}},"event_url":"https://example.com/checkout/success","timestamp":1712000000000,"ip":"35.244.183.10","user_agent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) ...","email_hashed":"a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2"}
```

</Accordion>

<Accordion title="Responses">

| Status | Description |
| --- | --- |
| 202 Accepted | Request accepted. Returns status, message, and optional `messageId`. |
| 400 Bad Request | Invalid or missing fields. |
| 401 Unauthorized | App does not exist, or authentication failed. |
| 403 Forbidden | App traffic is blocked. |
| 415 Unsupported Media Type | `Content-Type` must be `application/json`. |

</Accordion>

### Measure a visit

`POST /v2.0/s2s/visits/app/web/{appId}`

Measures a page visit for a given web app. This endpoint shares all base fields with the event endpoint, with two key differences: `event_url` is required, and the event name and revenue fields do not apply.

<Accordion title="Path parameter">

| Parameter | Required | Description |
| --- | --- | --- |
| `appId` | Required | The `unified_app_id` as defined in AppsFlyer. For example: `website-www.example.com` |

</Accordion>

<Accordion title="Request body">

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `user_id` | object | Required | User identifier. Must contain at least one of `customer_user_id` or `appsflyer_id`. |
| `event_url` | string | Required | The URL of the visited page. Valid HTTP URL, max 4,096 characters. |
| `timestamp` | integer (int64) | Optional | Unix time in ms (UTC). If omitted, AppsFlyer uses the receive time. Late acceptance window: visits must arrive no later than 00:30 on the next calendar day in the app's timezone. |
| `ip` | string | Optional | Device IP address (IPv4 or IPv6). Max 46 characters. |
| `user_agent` | string | Optional | Full user agent string from the browser. Max 1,024 characters. |
| `http_referrer` | string | Optional | Referrer URL of the current page. |
| `event_value` | object | Optional | Free-form event parameters, including a `custom_parameters` sub-object. |
| `customer_dedup_id` | string | Optional | Customer-provided deduplication identifier. |
| `email_hashed` | string | Optional | SHA256 of normalized email. Must be a 64-character hex string. |
| `phone_number_hashed` | string | Optional | SHA256 of phone number. Must be a 64-character hex string. |
| `phone_number_e164_hashed` | string | Optional | SHA256 of E.164 phone number. Must be a 64-character hex string. |
| `first_name_hashed` | string | Optional | SHA256 of normalized first name. Must be a 64-character hex string. |
| `last_name_hashed` | string | Optional | SHA256 of normalized last name. Must be a 64-character hex string. |

</Accordion>

<Accordion title="Example request">

```json
{"user_id":{"appsflyer_id":"1234567890abcdef","customer_user_id":"15667737-366d-4994-ac8b-653fe6b2be4a"},"event_url":"https://example.com/products/sneakers","timestamp":1712000000000,"ip":"35.244.183.10","user_agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) ...","http_referrer":"https://www.google.com/","email_hashed":"a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2"}
```

</Accordion>

<Accordion title="Responses">

| Status | Description |
| --- | --- |
| 202 Accepted | Request accepted. Returns status, message, and optional `messageId`. |
| 400 Bad Request | Invalid or missing fields. |
| 401 Unauthorized | App does not exist, or authentication failed. |
| 403 Forbidden | App traffic is blocked. |
| 415 Unsupported Media Type | `Content-Type` must be `application/json`. |

</Accordion>

## Set up a fully server-side integration

If you're running the Web SDK alongside S2S, use [Extracting the Web SDK afUserID](#extracting-the-web-sdk-afuserid) instead. This section is only for integrations without an SDK.

If you're not running the Web SDK on your site at all, you're responsible for everything it would normally handle: assigning the user cookie, sending the right identifiers, and keeping every event payload complete. Done right, this setup gives you the full benefits described in [Why use S2S](#why-use-s2s), but it depends on getting these details right.

<Accordion title="Send visits, not just events">

A visit carries the attribution parameters that every subsequent event relies on, and the system expects a visit before any user event. If you send an event before a visit, the system classifies it as organic.

</Accordion>

<Accordion title="Assign a first-party cookie via HTTP">

Because there's no Web SDK to set the `afUserId` cookie for you, you need to assign and manage it yourself, as an HTTP cookie set in the `Set-Cookie` response header, not a client-side cookie written in JavaScript.

Here's why that matters: a client-side cookie (set via `document.cookie`) expires quickly, as fast as 7 days on Safari, or 24 hours on domains under ITP. Once it expires, the identifier resets, and a returning visitor looks new. A cookie your server sets isn't subject to that cap and can persist up to the browser maximum (Chrome allows up to 400 days). It can also be marked `HttpOnly`, so page scripts and ad blockers can't read or strip it, and it doesn't rely on any script running on the page at all.

To set and read it:

1. On the first request from a visitor with no cookie, generate a stable, unique ID on your server (for example, a UUID).
2. Return it in a first-party cookie:

   ```
   Set-Cookie: af_web_id=<generated-id>; Max-Age=34128000; Path=/; Secure; HttpOnly; SameSite=Lax
   ```
3. On every later request, read the value from the incoming Cookie header and reuse it. Don't regenerate it.
4. Send that value to AppsFlyer on every call as `appsflyer_id` part of the request's `user_id` object.

You can name the cookie whatever you like; AppsFlyer reads the value you send, not the cookie's name. Just make sure you set it from your own first-party domain.

</Accordion>

<Accordion title="Send the right identifiers on each call">

Every call needs a `user_id` object with at least one of `appsflyer_id` (the cookie value) or `customer_user_id` (your internal user ID). Sending both, when you have them, improves identity resolution.

Here's what to keep in mind: visits are mostly anonymous, so always send the cookie value. For on-site events, add the `customer_user_id` once the user is identified, and keep sending the cookie alongside it. For events that don't originate in the browser, the `customer_user_id` alone is enough, as long as AppsFlyer already knows that user from an earlier identified session.

</Accordion>

## Things to consider

<Accordion title="User identification">

The `user_id` object is required on every request. At least one of the following identifiers must be provided.

| Field | Type | Description |
| --- | --- | --- |
| `customer_user_id` | string (1–64 characters) | Your internal user identifier, as set in your system. |
| `appsflyer_id` | string (min 1 character) | AppsFlyer internal identifier for the web user. If you use the AppsFlyer Web SDK, the `appsflyer_id` value is retrieved from the Web SDK cookie. Extract it from `afUserId`. See [Extracting the Web SDK afUserId](#extracting-the-web-sdk-afuserid) |

</Accordion>

<Accordion title="Late acceptance windows">

Events and visits must be received no later than 00:30 on the next calendar day in the app's timezone. Late events fall back to the server receive time.

</Accordion>

<Accordion title="Hashed PII fields">

All personal data fields must be SHA256-hashed before sending. Normalize text (lowercase, trimmed) before hashing. Each hash must be exactly 64 hexadecimal characters (case-insensitive).

* Pattern for all hashed fields: `^[a-fA-F0-9]{64}$`
* Phone numbers using the `phone_number_e164_hashed` field must conform to E.164 format (for example, `+14155552671`) before hashing.

</Accordion>

<Accordion title="Extracting the Web SDK afUserID">

* The `afUserId` parameter is a unique identifier set by the Web SDK when a user first visits your site.
* If you need `afUserId`, use one of the methods that follow.

<span id="h_01HKW2YAW5FK04C3AWCXGP1XAW"></span>**Get afUserId from the HTTP cookie header**

* The `afUserId` is sent by the visitor's browser on calls to your site.
* Extract it from the HTTP cookie header if needed.

<span id="h_01HKW2YAW5CT2WZ229KJD2FWYK"></span>**Viewing afUserId in the visitor's browser**

* View the `afUserId` in the visitor's browser for troubleshooting and debugging.
* For it to be available, the visitor needs to have first visited a page having the Web SDK at least once.
* The cookie containing `afUserId` is a first-party cookie in relation to your domain.
* The following procedure was prepared using Chrome 81. There may be differences across browsers and operating systems.

**To get the afUserId from the visitor's browser:**

1. In your browser, go to your website.
2. Right-click, select ***Inspect***. The browser's inspect element window opens.
3. Go to the (A) ***Application*** tab.
4. In the side menu, (B) expand Cookies.
5. Select your website. If it does not display, refresh the browser.
6. In the (C) ***filter*** field, enter `afUserId`. The value of afUserID displays.

</Accordion>

## Send events via Segment (CDP)

**You can use Segment to route events to your S2S API.** (Segment is a Customer Data Platform, a tool used for collecting customer events and sending them to configured destinations.)

The Web SDK and Segment are two separate, parallel paths into AppsFlyer, not one feeding the other: the Web SDK keeps sending visits, which carry the attribution parameters, and Segment sends events for properties that don't have the SDK. Neither path knows about the other; AppsFlyer is where they meet, joining a visit to its events using the identifier you send on both.

Web SDK - sends visits

Segment - sends events

S2S API

Joined by
`appsflyer_id`
or
`customer_user_id`

AppsFlyer - visit + event, joined

The Web SDK and Segment are two parallel paths into AppsFlyer, joined by a shared identifier.

> 📘 **Note**
>
> This covers **web** events sent over S2S from a Segment custom destination. For Segment's mobile SDK wrapper, which connects app installs and in-app events to the AppsFlyer mobile SDK, see [Segment integration](/docs/segment-integration) instead; that's a different integration for a different platform.

<Accordion title="Set up the destination in Segment">

AppsFlyer doesn't have a pre-built Segment destination for the S2S API yet, so you'll need to set this up as a custom destination in Segment that sends each event to the S2S endpoint. There are two ways to do this, depending on how much control you need over the data format.

#### Option 1: Webhooks (Actions) destination

This is the recommended starting point. It requires no code, and all setup happens in Segment's user interface.

To set it up:

1. In Segment, add the Webhooks destination from the destination catalog.
2. Connect it to the source that collects the events you want to send.
3. For each event type, create a mapping that defines the AppsFlyer URL, sets the method to POST, adds the required headers, and builds the JSON payload from the event's fields.

#### Option 2: Destination Function

Use this option only if the Webhooks mapping can't produce the payload format AppsFlyer needs. A Destination Function is a small JavaScript function that runs inside Segment, receives each event, and sends it to the AppsFlyer endpoint using fetch.

Use this option when:

* The payload needs a nested structure, for example, wrapping `user_id` inside a `user` object, that the Webhooks mapping user interface can't build.
* The event data needs to be transformed before sending, such as converting a timestamp to a different format.

</Accordion>

<Accordion title="The AppsFlyer endpoint">

Whichever setup you use, point it at this endpoint:

```
POST https://events.appsflyer.com/v2.0/s2s/inapps/app/web/website-{your_domain}

Authorization: Bearer {s2s-token}
Content-Type: application/json
```

Get your S2S API key from the AppsFlyer token management page (see [Authentication](#authentication)). In the path, use the web app ID (for example, `website-www.your_domain`), not the **Web SDK ID** UUID on the app settings page.

</Accordion>

<Accordion title="Payload per event">

Build the JSON body for each mapped event with these fields:

```json
{
  "user_id": {
    "customer_user_id": "<your internal user ID>",
    "appsflyer_id": "<afUserId cookie value, when available>"
  },
  "event_name": "signup",
  "event_url": "<page URL where the event happened>",
  "ip": "<end-user IP>",
  "user_agent": "<end-user user agent>",
  "af_customer_event_id": "<Segment messageId>"
}
```

</Accordion>

<Accordion title="Two Rules that make attribution work">

1. Keep the Web SDK running on the marketing site: it records the visits, and Segment carries the events. As explained in the introduction to this section, a user needs a visit before an event or the event gets attributed as organic. If you want a fully server-side setup instead, with no Web SDK at all, follow [Set up a fully server-side integration](#set-up-a-fully-server-side-integration).
2. Every call also needs the right identifiers: send the same `appsflyer_id` or `customer_user_id` combination described in [Send the right identifiers on each call](#af-accordion-11).

</Accordion>

<Accordion title="Verify the setup">

Once the destination and payload are in place, roll out in three steps:

1. Map one or two events in Segment (the sign-up event is a good first candidate) and send a test event from the mapping tester.
2. Verify they arrive correctly in the raw report and match up with the marketing-site visit.
3. Once confirmed, expand the mapping to the remaining events.

</Accordion>

<Accordion title="Suggested rollout">

Once the destination and payload are in place, roll out in three steps:

1. Map one or two events in Segment (the sign-up event is a good first candidate) and send a test event from the mapping tester.
2. Verify they arrive correctly in the raw report and match up with the marketing-site visit.
3. Once confirmed, expand the mapping to the remaining events.

</Accordion>

<div data-zendesk-anchors="h_01KP13TF66KEZ7F1TGAA7RGQ6G=about-the-s2s-api-for-web-attribution h_01KP13TF66W8V5A40YT2XYWQ5K=how-it-works h_01KP13TF671CF85KMYXFZE6W9D=why-use-s2s h_01KP13TF67N1FVEAD1C7RV25TY=api-specification h_01KP13TF67MHPEQ5J3H69RTQH5=authentication h_01KT98N5SBW812PVXP165FCWR3=note h_01KP13TF67QQC3F1YP9RZRNMTK=measure-an-event h_01KP13TF68HMD8GSR6GSY95WYF=measure-a-visit h_01KZS2SFULLSVR01=set-up-a-fully-server-side-integration h_01KP13TF68F2T3P7P56A5EG2HW=things-to-consider h_01M2T6JS6CPED929FVJS4P4CEG=send-events-via-segment-cdp h_01M2T6JS6CJ75PG72RSRYTCV9N=note-1 h_01M2T6JS6C08V4WZCC9EP724ZG=option-1-webhooks-actions-destination h_01M2T6JS6CZVH4PVH6MK7X5VTZ=option-2-destination-function" />

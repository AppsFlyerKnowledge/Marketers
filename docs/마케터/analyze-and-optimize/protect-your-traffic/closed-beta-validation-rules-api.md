---
title: '[Closed beta] Validation Rules API'
metadata:
  keywords:
    - Marketers
    - Closed beta
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2026-07-02T09:03:27Z'
  edited_at: '2026-10-13T00:18:58Z'
  id: 48341412127249
  locale: ko
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ko/articles/48341412127249
---
<span class="af-tag af-tag--closed-beta">Closed beta</span>

> **At a glance:** Automate the creation and management of Validation Rules at scale. The Validation Rules API lets technical teams programmatically create, update, patch, and delete rules, going beyond the UI's value limits and cutting out manual rule management overhead.

> 📘 **Note**
>
> The Validation Rules API is available to Protect360 customers. It's currently in closed beta, and access is limited and enabled per account. Contact your Customer Success Manager (CSM) to request access.

## About the Validation Rules API

Until now, Validation Rules could only be managed through the AppsFlyer UI. This created two limitations:

* A cap of approximately 17,000 values per rule. Not enough for enterprise-scale blocklists.
* Every update required manual UI work. This is time-consuming and operationally expensive for teams making frequent changes.

The Validation Rules API removes both constraints. It gives technical teams full programmatic control over their rules, supports up to 300,000 values per rule with large rules, and enables automation of high-frequency updates without touching the UI.

Rules created via the API are flagged as API-managed and appear as read-only in the AppsFlyer UI. Existing UI-created rules aren't affected. UI-managed and API-managed rules coexist in the same account.

<Accordion title="Is this for you?">

The Validation Rules API is built for specific use cases. It's not meant to replace the UI for every customer. Consider the API if:

* You manage a blocklist or allowlist that exceeds, or is approaching, the ~17,000 value UI limit.
* Your team wants to integrate rule management into your own systems, scripts, or automation pipelines.
* Your fraud or traffic-blocking logic changes frequently, and manual UI updates have become a bottleneck.

If you manage a small number of rules that rarely change, the Validation Rules UI remains the simplest way to manage them.

</Accordion>

<Accordion title="Access and eligibility">

The Validation Rules API is available to Protect360 customers. It's currently in closed beta, and access is enabled per account.

* Requires a Protect360 subscription.
* Controlled by a feature flag. Contact your Customer Success Manager (CSM) to request access and activation.
* Large rules (up to 300,000 values) require additional special enablement beyond standard API access. Contact your CSM to activate them.

</Accordion>

## How it works

<Accordion title="Authenticate">

The API uses Bearer token (JWT) authentication.

1. In your AppsFlyer account, go to **Security Center** > **API tokens**.
2. Generate a token.
3. Include the token in the **Authorization** header of your API requests.

> 📘 **Note**
>
> API access must be enabled per account before a token will work. Contact your CSM to activate it.

</Accordion>

<Accordion title="What you can do">

| Action | Description |
| --- | --- |
| List rules | Retrieve all active rules (enabled and disabled) for your account. |
| Create a rule | Create a new rule programmatically. |
| Retrieve a rule | Get full rule details, including all conditions. |
| Update a rule | Overwrite an existing rule with a new configuration. |
| Enable / disable a rule | Toggle a rule on or off without deleting it. |
| Delete a rule | Remove a rule permanently. |
| Patch a rule | Add, remove, or replace values for a single dimension without rewriting the full rule. |

The patch endpoint is especially useful for high-frequency updates. You update only what changed, not the entire rule. This works well for workflows like daily fraud-source blocklist updates.

</Accordion>

## Scope and supported configurations

The Validation Rules API currently supports a defined subset of what's available in the UI rule builder.

* Applies to install events only. In-app events aren't supported in this version.
* Supported dimensions:
  * Traffic source (Population): Site ID, Media Source, Agency, Campaign, Campaign ID, Ad Set ID, and Ad ID
  * Conditions: Geo, Platform
* Supported operators: Is in list, Is not in list.
* Logic between dimensions: AND only. OR isn't supported.
* Rule types: Match (block matching traffic) or Do not match (block traffic that doesn't match).
* Source types: All traffic, all non-organic traffic, or non-organic traffic from a specific agency.
* Supported blocking actions:
  * Block attribution and correct to the last valid media source.
  * Block attribution and mark installs as invalid. These won't appear in the Protect360 dashboard.

<Accordion title="Rule size and limits">

|  | Standard rule | Large rule |
| --- | --- | --- |
| Total values across all conditions | Up to 17,000 | Up to 300,000 |
| Requires special enablement | Yes | Yes |
| Max rules per account | 100 | Up to 5 |

Additional limits:

* Max 2,000 app IDs per rule.
* 2MB per API call. Requests that exceed this (roughly 50,000 values) must be split across multiple calls.
* 300,000 values per large rule, across all dimensions combined, regardless of operation type (create, update, or patch).

Exceeding any limit returns an error identifying which limit was breached.

</Accordion>

<Accordion title="Accessing blocked traffic data">

Traffic blocked by API-managed rules is reported identically to traffic blocked by UI-created rules.

| Report | Location |
| --- | --- |
| Raw Data Export | Protect360 & Validation Rules > Installs |
| Data Locker | Protect360 reports > blocked\_installs report |
| Pull API | Raw data export |

</Accordion>

<Accordion title="Technical documentation">

For full technical details, including endpoint references, request and response schemas, and error codes, see the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/updaterule">Validation Rules API reference</Anchor>.

</Accordion>

<Accordion title="Traits and limitations">

| Trait | Description |
| --- | --- |
| Event support | Install events only. In-app events aren't supported in this version. |
| Logic | Only AND logic is supported between dimensions. OR isn't supported. |
| UI interaction | Rules created via the API appear as read-only in the UI. Edit them using the API. |
| Call size | 2MB per API call (approximately 50,000 values). Larger updates must be split across multiple calls. |

</Accordion>

## FAQ

<Accordion title="Who can use the Validation Rules API?">

The Validation Rules API is available to Protect360 customers. It's currently in closed beta, and access is enabled per account. Contact your CSM to request access.

</Accordion>

<Accordion title="Do API-managed rules appear in the UI?">

Yes. Rules created via the API are visible in the AppsFlyer UI, but they're flagged as API-managed and appear as read-only.

</Accordion>

<Accordion title="Can I manage some rules via the API and others via the UI?">

Yes. API-managed and UI-created rules coexist in the same account. API-managed rules appear as read-only in the UI. UI-created rules aren't accessible via the API.

</Accordion>

<Accordion title="Can I edit an API-managed rule in the UI?">

No, the rule appears as read-only. You must use the API to update it instead.

</Accordion>

<Accordion title="What's the difference between Update and Patch?">

Update overwrites the full rule. Patch updates a single dimension only, adding, removing, or replacing values without rewriting the entire rule. Use Patch for frequent, targeted updates.

</Accordion>

<Accordion title="What happens if I exceed a limit?">

The API returns an error identifying which limit was breached. Split large updates across multiple API calls to stay within the 2MB per call limit.

</Accordion>

<Accordion title="How many rules can I have?">

Up to 100 standard rules per account and up to 5 large rules per account. Both standard and large rules require special enablement. Contact your CSM to activate them.

</Accordion>

<Accordion title="Is OR logic supported?">

No. Only AND logic is supported between dimensions.

</Accordion>

<Accordion title="What event types are supported?">

Install events only. In-app events aren't supported in this version.

</Accordion>

> 📄 **See also**
>
> * Implement validation rules to prevent fraud

<div data-zendesk-anchors="h_01KWH1NW583T8SPZFF5REMQC6V=note h_01KWH1NW58A3YK7FKR1C4WBRF3=about-the-validation-rules-api h_01KWH1NW58P5AB47847E99YG6G=how-it-works h_01KWH1NW594YT5S9FT8VWX77SG=note-1 h_01KWH1NW594XM03VQKNJPY37B7=scope-and-supported-configurations h_01KWH1NW59J9QHP37KMMK18JBG=faq h_01KWH1NW59G3WG3KHVRGY9TMV4=see-also" />

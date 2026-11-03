---
title: '[Closed beta] Implementing Series of Events Rule for advanced fraud prevention'
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
  created_at: '2024-07-10T09:41:19Z'
  edited_at: '2026-09-28T07:49:15Z'
  id: 26596474431761
  locale: en-us
  section: Protect your traffic
  section_id: 6551015912465
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/26596474431761--Closed-beta-Implementing-Series-of-Events-Rule-for-advanced-fraud-prevention
---
<span class="af-tag af-tag--closed-beta">Closed beta</span>

> **At a glance:** Series of events in validation rules allows advertisers to define an event sequence a real user should go through. Any deviation from your defined order, or from the timing between events, is detected and blocked.

## Intro

Advertisers can define an event sequence a real user should go through in your app. AppsFlyer evaluates this sequence using an evaluation window that starts the day the rule is saved: it grows daily up to 30 days, then becomes a rolling 30-day window that shifts forward every day. Events fired before the rule was created are never evaluated.

If the sequence breaks, either in order or in timing, the user is considered fake and:

* Any in-app events, as well as sessions, after the break are blocked immediately.
* The install is blocked in post-attribution, if it falls within the post-attribution window (7 days)
* The associated in-app events inside the evaluation window are blocked as part of the post-attribution process
* Other in-app events that meet the rule's conditions elsewhere in the app are not affected

Note: editing the rule in any way, including app selection, conditions, traffic source, event sequence, or enabling/disabling, resets the evaluation window back to day 0.

## Who is this for?

This feature is only suitable for:

* **SDK events** - Apps that will create rules with only SDK events.
* **Non-repeating events** - Apps that have an event sequence in which events will not happen more than once in the sequence. If the same event occurs more than once in the sequence (for example, Event C is sent twice), it's treated as a violation and the associated events are blocked.
* **NOI traffic** - This feature is only available for NOI traffic

## How to set up a series of event rule

Follow these instructions to set up a Series of events rule:

1. Go to **Settings > Validation Rules**
2. Click **+ New rule**
3. Name the rule
4. Select the **Post attribution** tab
5. Select the app you want to set the rule for  
   Note: you can only select one app for each rule
6. Define the traffic source for the rule to run on
7. Choose the conditions. Currently, the options are:
   1. Geo
   2. Device model
8. Your unique identifier is set automatically based on the app you selected - **IDFA** for iOS, or **Advertiser ID** for Android. You can change this to **Customer User ID** instead, for either platform.
9. Define the sequence of events - add at least 2 events, in the order a real user should complete them
10. Optionally, set a minimum time gap between each event pair. If you don't set one, a 1-second minimum applies by default
11. Review the **Rule outcome** section to confirm the evaluation window state and the minimum total sequence time
12. Click **Save**

> 🚧 **Important!**
>
> Don't select all your app's events. Only select the events where there usually could be fraud

## Accessing data

When a Series of Events rule blocks an install or in-app event, the details are recorded in your raw data reports. Go to **Raw Data > Protect360 & Validation Rules** to find blocked events, and use the fields below to identify which ones were blocked by this rule.

| Report | Key fields |
| --- | --- |
| Post-attribution installs | <ul><li>Fraud reason = validation bots</li><li>Fraud sub reason = validation rules pa</li><li>Blocked reason value = rule name</li></ul> |
| Post-attribution in-app events | <ul><li>fraud\_reason = validation bots</li><li>fraud\_sub\_reason = validation rules pa</li></ul> |
| Blocked in-app events | <ul><li>Blocked Reason = validation bots</li><li>Blocked sub reason = validation rules pa</li><li>Blocked Reason Value = rule name</li></ul> |

## Examples

Below are examples of different series of events and if they would be considered fraudulent or not.

<Accordion title="Example 1">

**Defined rule**

User should perform events in this order:

* Event A
* Event B
* Event C

**Actually performed**

The user does the events in this order:

* Day 0: Install occurred
* Day 1: Event A sent
* Day 2: Event B sent
* Day 3: Event C sent

**Result:**

Not fraud. The user performed the series of events in the defined sequence.

</Accordion>

<Accordion title="Example 2">

**Defined rule**

User should perform events in this order:

* Event A
* Event B
* Event C

**Actually performed**

The user does the events in this order:

* Day 0: Install occurred
* Day 1: Event A sent
* Day 2: Event C sent
* Day 3: Event B sent

**Result:**

Fraud. The user performed Event C before Event B which is out of the defined sequence. As a result:

* Event A will be blocked in post-attribution
* Event B will be blocked in real-time
* Event C will be blocked in real-time or post-attribution as this event broke the sequence
* All following events will be blocked in real-time

</Accordion>

<Accordion title="Example 3">

**Defined rule**  
 User should perform events in this order:

* Event A
* Event B (minimum time to previous event: 1 hour)
* Event C (minimum time to previous event: 2 hours)

**Actually performed**  
 The user does the events in this order:

* Day 0: Install occurred
* Day 0: Event A sent
* Day 0: Event B sent 10 minutes after Event A
* Day 0: Event C sent 2 hours after Event B

**Result:**  
 Fraud. The user performed all events in the correct order, but the gap between Event A and Event B was only 10 minutes, which is less than the configured minimum of 1 hour. The timing constraint was violated, regardless of the correct sequence order. As a result:

* Event A will be blocked in post-attribution
* Event B will be blocked in real-time as it violated the minimum time constraint
* Event C will be blocked in real-time as it followed a violated sequence
* All following events will be blocked in real-time

</Accordion>

<Accordion title="Example 4">

**Defined rule**  
 User should perform events in this order:

* Event A
* Event B
* Event C

**Actually performed**  
 The user does the events in this order:

* Day 0: Install occurred
* Day 1: Event A sent
* Day 2: Event B sent
* No Event C sent

**Result:**  
 Not fraud. The user completed Events A and B in the correct order but never fired Event C. Incomplete sequences are not flagged as violations. No events are blocked. The rule continues to evaluate future events within the 30-day evaluation window.

</Accordion>

<Accordion title="Example 5">

**Defined rule**

The user was identified by the <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">Customer User ID (CUID)</Anchor>.

The user should perform events in this order:

* Event A
* Event B
* Event C

**Actually performed**

The user does the events in this order:

* Day 0: Install occurred
* Day 1: Event A sent
* Day 1: Uninstall occurred
* Day 1: Install occurred
* Day 2: Event B sent
* Day 3: Event C sent

**Result:**

Not fraud. Since the user was identified by the <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">Customer User ID (CUID)</Anchor> and the events were performed in order.

</Accordion>

<Accordion title="Example 6">

**Defined rule**

The user should perform events in this order:

* Event A
* Event B
* Event C

**Actually performed**

The user was identified by the Advertiser ID

The user does the events in this order:

* Day 0: Install occurred
* Day 1: Event A sent
* Day 1: Uninstall occurred
* Day 1: Install occurred
* Day 2: Event B sent
* Day 3: Event C sent

**Result:**

Not fraud. Since the user was identified by the Advertiser ID and the events were performed in order.

</Accordion>

<Accordion title="Example 7">

**Defined rule**  
 User should perform events in this order:

* Event A
* Event B
* Event C

Rule created on January 1.

**Actually performed:**

* January 1 (Day 0): Rule created. Evaluation window starts. Events fired before this date are ignored.
* January 15 (Day 14): Event A sent. Window is growing, now evaluating the last 14 days.
* January 30 (Day 29): Event B sent. Window is growing, now evaluating the last 29 days.
* January 31 (Day 30): Window reaches 30 days and becomes a rolling 30-day window, shifting forward every day.
* February 20: Event C sent. The rolling window now looks back 30 days to January 21. Event A (fired January 15) falls outside the window and is no longer evaluated.

**Result:**  
 Not fraud. By February 20, the rolling window looks back to January 21, placing Event A (January 15) outside the evaluation window. Only Events B and C are evaluated - both in the correct order, no violation flagged.

</Accordion>

<Accordion title="Example 8">

**Defined rule**

The user should perform events in this order:

* Event A
* Event B
* Event C

**Actually performed**

The user does the events in this order:

* Day 0: Install occurred
* Day 1: Event A sent
* Day 2: Event B sent
* Day 3: Event B sent
* Day4: Event C sent

**Result:**

Fraud. Since the same Event (Event B) happened twice, we presume fraud, as you cannot have the same event twice in a sequenc.

</Accordion>

<Accordion title="Example 9">

**Defined rule**  
 The user was identified by Customer User ID (CUID).  
 User should perform events in this order:

* Event A
* Event B
* Event C

**Actually performed**  
 The user fires events across two devices using the same CUID:

* Day 0: Install occurred on Device 1
* Day 0: Install occurred on Device 2
* Day 1: Event A sent from Device 1
* Day 2: Event B sent from Device 2
* Day 3: Event C sent from Device 1

**Result:**  
 Not fraud. Since the user was identified by CUID, the sequence evaluation spans all AppsFlyer IDs associated with the same CUID and rule id. Events A, B, and C were performed in the correct order regardless of which device fired them.

</Accordion>

<Accordion title="Traits and limitations">

* Up to 100 events can be defined in each rule.
* At 80 events, a warning is shown. At 100 events, the limit is reached and the rule must be split to add more.
* The minimum time that can be set between consecutive events is 1 second. If no timing is configured for a pair, the 1 second default applies automatically.
* The maximum configurable time gap between events is 30 days, aligned with the evaluation window.
* The evaluation window starts at day 0 (rule creation date) and grows daily up to 30 days, after which it becomes a rolling 30-day window shifting forward every day. Events fired before the rule creation date are never evaluated.
* Any edit to a rule resets the evaluation window back to day 0.
* Up to 10 active rules can be set per account.
* Series of events rules can only be used for non-organic traffic.
* Only SDK traffic is supported. S2S traffic is out of scope for Phase 1.
* Incomplete sequences are not flagged as violations.
* The same event cannot appear twice within a single sequence.
* Only AND logic is supported between conditions. OR logic is not supported.

</Accordion>

## FAQ

<Accordion title="What happens after a reinstall?">

If the reinstall resets events the user already completed, it's treated as a violation. If the user resumes from where they left off, no violation is flagged.

</Accordion>

<div data-zendesk-anchors="h_01J2DZP5DWZ0V52PA0RGQ4PNHN=intro h_01J2E0CYHW4TBK6TQHMHYEVGEM=who-is-this-for h_01J2E0MZYM7GZ2N6Z0NDRQQPTF=how-to-set-up-a-series-of-event-rule h_01J2ED6016XRPDVJBJ0X388THJ=important h_01KWSHAXG3K8PQV334JHGC8A0G=accessing-data h_01J2E0XXG85150ZBSSFVF98W83=examples h_01KWSHAXG4PFT77C0FWCXTF3AH=faq" />

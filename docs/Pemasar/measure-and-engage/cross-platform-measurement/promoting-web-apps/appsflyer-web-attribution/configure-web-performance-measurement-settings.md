---
title: Configure Web Performance Measurement settings
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
  created_at: '2026-02-05T08:47:53Z'
  edited_at: '2026-08-03T08:33:38Z'
  id: 43541863890961
  locale: en-us
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/43541863890961-Configure-Web-Performance-Measurement-settings
---
> **At a glance:** Configure your web attribution settings to control how AppsFlyer attributes website visits, conversions, and user activity to marketing campaigns. Settings include attribution windows, user acquisition events, re-engagement rules, and domain exclusions.

## Overview

Web attribution settings define how AppsFlyer measures and attributes user activity on your website. These settings determine:

* Which events qualify as user acquisition.
* How long to attribute subsequent events to marketing sources.
* When to consider users as returning (re-engagement) or reacquired.
* Which domains to exclude from attribution.

### Who should configure these settings

Marketing teams and growth managers typically configure these settings based on business objectives. Technical teams may be involved for SDK integration and domain configuration.

### Accessing web attribution settings

To access your web app's attribution settings:

1. In AppsFlyer, go to **My Apps**
2. Select your web app from the list
3. Navigate to **App Settings** > **Attribution**

## Quick reference

| Setting | Default | Options | Editable | What it controls |
| --- | --- | --- | --- | --- |
| App name | User input | 1–100 chars | Yes | Display name in AppsFlyer |
| Full URL (primary domain) | User input | 1–500 chars | No | App identifier and primary excluded domain |
| Web SDK ID | Auto-generated | 1–550 chars | No | SDK identifier for event collection |
| Currency | User-selected | ISO codes | Yes | Revenue and ROI reporting |
| Time zone | User-selected | IANA zones | Limited | Reporting timestamps |
| User acquisition event | First visit | Event name | Yes | When a user is considered acquired |
| Lookback window (UA) | 30 days | 1 hour–90 days | Yes | How far back to find a UA touchpoint |
| Re-engagement window | 30 days | 1 hour–90 days | Yes | How long retargeting gets credit |
| Inactivity window (re-engagement) | Disabled | 0–30 days | Yes | Minimum inactivity for retargeting |
| Attribution window | Lifetime | Preset options | Yes | How long events are attributed to UA |
| Inactivity window (re-acquisition) | 90 days | 1–180 days | Yes | When users are considered churned |
| Re-acquisition event | Visit | Event name | Yes | What brings churned users back |
| Excluded domains | Primary only | Up to 100 | Yes | Domains ignored for attribution |

**Constraint:**  
The re-engagement inactivity window must be **shorter than or equal to** the re-acquisition inactivity window. Otherwise, users could be reacquired before qualifying for retargeting.

## **Basic settings**

The basic settings for the web app are:

* App name
* Full URL
* Web SDK ID
* Currency
* Time zone

For more information see <Anchor target="_blank" href="/marketers/id/docs/adding-an-app-to-appsflyer#web">Adding an app to AppsFlyer</Anchor>.

## User acquisition settings

User acquisition (UA) settings determine how AppsFlyer identifies when a user is first acquired and how to attribute that acquisition to marketing sources.

<div id="user-acquisition-event" />

<Accordion title="User acquisition event">

The event that triggers user acquisition. This is an important business action that defines when you consider a user truly "acquired."

#### Why customize

The default **first visit** often represents a weak signal of user value. A user might click an ad accidentally or bounce immediately. By customizing this setting, you ensure that long-term value (LTV) is attributed to the marketing source that drove a meaningful action, not just a curiosity click.

**Default:** first visit (user is acquired on their first website visit)

#### Common alternatives by industry

| **Industry** | **Recommended UA Event** |
| --- | --- |
| Banking/Finance | registration or first\_time\_deposit |
| E-commerce | sign\_up or first\_purchase |
| Food Delivery | first\_order |
| SaaS/Subscription | subscription\_start |
| Gaming | sign\_up ortutorial\_complete or first\_purchase |

#### How it works

If set to **first visit**:

* Users are acquired immediately on their first website visit.
* Attribution begins from the first visit.

If set to **a custom event** (e.g., sign\_up):

* Users enter a **"pre-acquisition period"** from first visit until they perform the event.
* During pre-acquisition, events are attributed to the last non-organic touchpoint within the lookback window (last-touch attribution).
* Once the custom UA event occurs, a **User Acquisition conversion** is created and long-term attribution begins.

#### Example scenario (UA event = sign\_up):

* **Day 0:** User visits from Facebook ad → Pre-acquisition period begins
* **Day 2:** User visits from Google ad → Credit switches to Google (last touch)
* **Day 3:** User signs up → User acquisition attributed to Google ad

**Day 10:** User makes purchase → Purchase attributed to Google for LTV measurement

</Accordion>

<div id="lookback-window-user-acquisition" />

<Accordion title="Lookback window (user acquisition)">

How far back in time AppsFlyer looks to find the marketing touchpoint that drove user acquisition.

This window controls how long AppsFlyer "remembers" a marketing touchpoint. If a user visits from an ad but doesn't complete the UA event until later, this setting determines whether the ad still gets credit.

**Default:** 30 days

**Range:** 1 hour to 90 days

#### How it works

When a user performs the UA event (e.g., sign\_up), AppsFlyer looks back within this window to find the most recent non-organic touchpoint and attributes the acquisition to that marketing source.

#### Example 1 (30-day lookback):

* **Day 0:** User clicks Facebook ad and visits website
* **Day 25:** User returns directly and completes sign\_up event
* **Result:** User acquisition attributed to Facebook (within 30-day lookback window)

#### Example 2 (window expired):

* **Day 0:** User clicks Facebook ad and visits website
* **Day 40:** User returns directly and completes sign\_up event

**Result:** User acquisition marked as organic (outside 30-day lookback window)

</Accordion>

## Re-engagement settings

Re-engagement settings control how AppsFlyer attributes activity when acquired users return to your website through retargeting campaigns.

<div id="reengagement-window-item" />

<Accordion title="Re-engagement window">

How long after a re-engagement conversion AppsFlyer continues to attribute events to that marketing touchpoint.

This setting determines how long retargeting campaigns get credit for user activity. It balances giving credit to retargeting efforts while still attributing long-term LTV back to the original acquisition source.

**Default:** 30 days

**Range:** 1 hour to 90 days

#### How it works

When an acquired user returns via a non-organic source (e.g., retargeting ad) and meets re-engagement criteria, a **retargeting conversion** is created. Events within this window receive **dual attribution**:

1. **Primary attribution** → Retargeting campaign
   * Purpose: Credit the retargeting campaign
2. **Secondary attribution** → Original UA source
   * Purpose: Support UA view that measures full user lifetime value (LTV) back to original acquisition

#### Example (within window):

* **Day 0:** User acquired via Facebook ad
* **Day 50:** User clicks email retargeting campaign and returns (retargeting conversion created)
* **Day 60:** User makes $100 purchase (10 days after retargeting)
* **Result - Dual attribution:**
  * **Primary (Retargeting view):** Email campaign gets credit for $100 purchase
  * **Secondary (UA view):** Facebook ad also tracked for $100 in user's LTV
* **Reports:**
  * Unified view: Shows purchase attributed to Email
  * Retargeting view: Shows purchase attributed to Email
  * UA view: Shows purchase attributed to Facebook

</Accordion>

<div id="inactivity-window-for-reengagement" />

<Accordion title="Inactivity window for re-engagement">

The minimum period of user inactivity required before a non-organic touchpoint can create a re-engagement (retargeting) conversion.

Prevent crediting retargeting campaigns when users are already actively engaged with your website. This optimizes retargeting budget by ensuring campaigns target truly inactive users.

**Default:** Disabled

**Range:** 0 (disabled) to 30 days

#### How it works

**When disabled:**

* Every non-organic touchpoint from an acquired user creates a retargeting conversion

**When enabled (e.g., 7 days):**

* Only creates retargeting conversion if user has been inactive for at least 7 days
* If user was active recently, visit attributed to original UA source instead

**Constraint:**

* Cannot exceed Inactivity Window (Re-acquisition)

#### Example (7-day inactivity window):

* **Day 0:** User acquired via Facebook ad
* **Day 3:** User visits organically
* **Day 5:** User clicks retargeting ad → **No retargeting conversion** (only 2 days inactive)
* **Day 15:** User clicks retargeting ad → **Retargeting conversion created** (12 days inactive)

</Accordion>

## Re-acquisition settings

Re-acquisition settings determine when inactive users are considered "churned" and how to bring them back as reacquired users.

<div id="inactivity-window-reacquisition" />

<Accordion title="Inactivity window (re-acquisition)">

The period of complete inactivity after which a user is marked as "churned." Churned users can be reacquired, generating a new user acquisition conversion.

This setting defines your business's churn threshold. It determines when a user is considered "lost" and eligible to be reacquired, allowing win-back campaigns to get credit for bringing back churned users.

**Default:** 90 days

**Range:** 1 to 180 days

#### How it works

**When user is marked as churned:**

* User no longer attributed to original UA source for new events
* User enters a "pre-acquisition" state (waiting to be reacquired)
* Attribution windows from original acquisition no longer apply

**When churned user returns:**

* If user performs the re-acquisition event → New UA conversion created
* Win-back campaign gets credit as the new acquisition source
* User is treated as a completely new acquisition from a reporting perspective

#### Example (90-day window):

* **Day 0:** User acquired via Google ad
* **Day 50:** Last activity
* **Day 140:** User churned (90 days inactive)
* **Day 145:** User clicks email win-back campaign

**Day 146:** User performs re-acquisition event → **New UA conversion** attributed to email campaign

</Accordion>

<div id="reacquisition-event" />

<Accordion title="Re-acquisition event">

The event that triggers re-acquisition for churned users. Only churned users can be reacquired.

Many user acquisition events are one-time actions (e.g., sign\_up, first\_purchase) that cannot happen twice. This setting allows you to define a repeatable event that signals a churned user has returned.

**Default:** visit (Churned users are **immediately reacquired** on their first return visit)

**Common alternatives:** sign\_in or purchase

#### How it works

**If set to a custom event (e.g.,** **sign\_in**):

* Churned users must perform the specific event to be reacquired
* User can visit multiple times before reacquisition occurs
* More stringent definition of "true" reacquisition.

#### Example (re-acquisition event = sign\_in):

* User churned after 90 days inactivity
* User clicks email win-back campaign and visits → Not yet reacquired
* A day later, the user signs in → Reacquisition conversion created, attributed to email campaign

</Accordion>

## Attribution window

<div id="time-period" />

<Accordion title="Time period">

The maximum time period after the user acquisition during which AppsFlyer attributes events to that conversion.

**Default:** Forever

**Available options:** None, 1 day, 7 days, 30 days, 60 days, 90 days, 180 days, 365 days, Forever (limited by data retention)

</Accordion>

## Excluded domains

Domains to exclude from attribution. This prevents AppsFlyer from attributing visits or events when users navigate between specified domains and your website.

**Purpose:**

1. **Prevents self-attribution:** Exclude your own domains
2. **Excludes third-party flows:** Exclude payment gateways, authentication providers

<div id="domain-types" />

<Accordion title="Domain types">

#### PRIMARY (required, automatic)

* Your main website domain (set during app creation)
* Automatically added and cannot be removed
* Exactly one primary domain per web app
* **Automatic subdomain exclusion:** Primary domain automatically excludes all its subdomains
  * Example: example.com automatically excludes shop.example.com, blog.example.com, etc.
* **Impact of exclusion:** No self-attribution

#### INTERNAL (optional)

* Your brand's other domains not covered by primary domain
* Add up to 99 additional domains
* Example: Different top-level domains like example.co.uk, example.in
* **Impact of exclusion:** No self-attribution

#### EXTERNAL (optional)

There are two types of external domain exclusions:

#### External (listed by you)

* Domains used by your website directly, but not part of your brand
* These include payment gateways, payment processing sites, authentication providers
* Add up to 99 additional domains
* Examples: auth0.com, okta.com, facebook.com, google.com
* **Impact of exclusion:** Visits are disregarded

#### External (listed by AppsFlyer)

* Domains automatically excluded by AppsFlyer:

  **Payment providers**

  * PayPal (payment checkout)
  * Stripe (payment checkout)
  * Adyen (payment checkout)
  * Klarna (payment checkout)
  * Braintree (payment gateway)
  * Square (payment checkout)
  * Paddle (payment checkout)
  * Mollie (payment checkout)
  * Alipay (payment checkout)
  * Razorpay (payment checkout)
  * Paytm (payment checkout)
  * PayU (payment checkout)
  * Mercado Pago (payment checkout)
  * Yandex Pay (payment checkout)
  * Naver Pay (payment checkout)

  **OAuth and SSO sign-in**

  * Google Sign-In (Google account login)
  * Apple ID (Apple account login)
  * Microsoft (Microsoft 365 / Entra account login)
  * Microsoft Live (Outlook/Live account login)
  * Facebook Login (Facebook's sign-in domain only)
  * Yandex Login (Yandex account login)
  * Kakao Login (Kakao account login)
  * Naver Login (Naver account login)
  * LINE Login (LINE account login)
  * Weixin Login (WeChat's OAuth sign-in)
  * VK Login (VK account login)
  * Daum Login (Daum account login)
* The list of automatic domains cannot be edited
* **Impact of exclusion:** Visits are disregarded

</Accordion>

<div id="adding-excluded-domains" />

<Accordion title="Adding excluded domains">

**To add domains:**

1. Go to your web app settings → Attribution
2. Navigate to the Excluded Domains section
3. Click **Add domain**
4. Enter the domain name (e.g., custom-gateway.com)
5. Select domain type: Internal or External
6. Click **Save**

**Important notes:**

* Exclusions take effect within **1 hour**
* Changes apply **prospectively only** (do not affect historical data)
* Common payment providers and OAuth/SSO sign-in domains are automatically excluded. See the full list under [External (listed by AppsFlyer)](#external-listed-by-appsflyer) (no need to add these manually)

</Accordion>

<div id="requirements-and-validation" />

<Accordion title="Requirements and validation">

#### Domain format:

* Domain name only (no protocols, paths, or ports)
* Maximum 500 characters per domain
* Protocols (https://) automatically stripped, converted to lowercase

#### Examples:

* example.com ✅
* shop.example.com ✅ (but unnecessary if example.com is primary domain)
* https://example.com → example.com ✅ (protocol stripped)
* example.com/path ❌ (paths not allowed)
* example.com:8080 ❌ (ports not allowed)

#### Limits:

* Maximum 100 domains total (including 1 PRIMARY)

</Accordion>

## Migrating from People-Based Attribution (PBA)

<div id="key-differences" />

<Accordion title="Key differences">

| **Aspect** | **PBA (Legacy)** | **New Web Performance Measurement** |
| --- | --- | --- |
| **Configuration level** | Brand bundle level | Web app level |
| **Custom UA event** | Not available | Fully customizable |
| **Time windows** | Limited control | Full control (1h - lifetime) |

</Accordion>

<div id="migration-steps" />

<Accordion title="Migration steps">

1. Create new web app
   1. Go to My Apps → Add App → Select Website
2. Choose Web SDK ID   
   Reuse existing PBA dev key (recommended) to avoid code changes in your website.
3. Configure settings   
   Map PBA settings to new web attribution settings
4. Add excluded domains   
   Map PBA (Brand Bundle) excluded domains to new web attribution settings

**Note:** Each PBA dev key can only be assigned to ONE new web app.

</Accordion>

<div data-zendesk-anchors="h_01KGPFHN8MKTPX5VYDEV30M9A7=overview h_01KGPFK1RNA7ZTJRACJ6M97EAB=who-should-configure-these-settings h_01KGPFM0DJDMVDXZC2B6G6DVX5=accessing-web-attribution-settings h_01KGPFT1W65R724WCNDPBHY3F6=quick-reference h_01KGPGJG092S1TEDB1T9JNBASE=basic-settings h_01KGPGE592EK59XXVKTTFDGX16=user-acquisition-settings h_01KGPGRTEFA0PJ3DB7MR4W85EB=user-acquisition-event h_01KGPHMJWF6Z1VV0KH301TYAS5=why-customize h_01KGPHMSEDGJ2E6NSB1ZCR5CCW=common-alternatives-by-industry h_01KGPHN5M5GBBMPBYRMYHB9F0E=how-it-works example-scenario-ua-event-sign_up=example-scenario-ua-event--sign_up h_01KGPHQES3SF5AKBNYD8CY3RG8=example-scenario-ua-event--sign_up h_01KGPGRTEFYRAZD7Z9NYDKV907=lookback-window-user-acquisition how-it-works::69b3417c=how-it-works-1 h_01KGPHX2JNAWZ8VJZ25CRWP1ER=how-it-works-1 example-1-30day-lookback=example-1-30-day-lookback h_01KGPHX8JMG7FMRS1MYFYS6JRV=example-1-30-day-lookback h_01KGPHXT83JHJ6J0APVN7NRJ3E=example-2-window-expired reengagement-settings=re-engagement-settings h_01KGPJ1ZMXXJJNCBB52CHY95Z2=re-engagement-settings reengagement-window%C2%A0item=reengagement-window-item h_01KGPJ58N3712E1NZ4E6JVGAY2=reengagement-window-item how-it-works::dafb60ec=how-it-works-2 h_01KGPJFG3X578XCP5X353RRVR1=how-it-works-2 h_01KGPJG6WSYX2R0VVQYXXWZSMA=example-within-window h_01KGPJ58N3QH9RKXTVZXCZ1WGW=inactivity-window-for-reengagement how-it-works::4a4cf0f=how-it-works-3 h_01KGPJK3H2JF7PV1ATQB3TE9AX=how-it-works-3 example-7day-inactivity-window=example-7-day-inactivity-window h_01KGPJKDMY4FRAJSMHE19GGJCA=example-7-day-inactivity-window reacquisition-settings=re-acquisition-settings h_01KGPJMJDX83SBA77A7BSRZ87V=re-acquisition-settings h_01KGPJPC0QXYFD6Q09XF7T3XA9=inactivity-window-reacquisition how-it-works::9c91010b=how-it-works-4 h_01KGPJV8EJR94H1P7GZXMP8HSR=how-it-works-4 example-90day-window=example-90-day-window h_01KGPJVHCNBZHD9ZXW288CGG9H=example-90-day-window h_01KGPJPC0QY2726Z583AQ7G5W2=reacquisition-event how-it-works::587eebec=how-it-works-5 h_01KGPJY5PA9907PXBRC2QHNJ6T=how-it-works-5 example-reacquisition-event-sign_in=example-re-acquisition-event--sign_in h_01KGPJYWG31QJ1G5A09QC00AMY=example-re-acquisition-event--sign_in h_01KGPK8H7P5AT59S0GQ9ZK0F01=attribution-window h_01KGPK1CSV5XGKHX3XVS37QFKS=time-period h_01KGPKA56KQRJKRS54HBR50NJN=excluded-domains h_01KGPKCY1EBCMYDDYS6SZEK1ZR=domain-types h_01KGPKJQ7M82KW5VE9ESYNNFEQ=primary-required-automatic h_01KGPKJV9B2BHDR64JD24VHH1X=internal-optional h_01KGPKJZQYZESHHH3D0NA2WC9F=external-optional h_01KGPKK4THXQ88AXT58GZ2MHHE=external-listed-by-you h_01KGPKK96ZAZSKVPBX60FC888X=external-listed-by-appsflyer h_01KGPKCY1ETKF1NQ2BP6Z3JH4T=adding-excluded-domains h_01KGPKCY1EE01631ZEYGC6FEJH=requirements-and-validation h_01KGPKKXRA59A4RDY4QE1M0Q66=domain-format h_01KGPKM213203KA8CEBHZ9KJP3=examples h_01KGPKM8AMQ5BA88ZCSTRJ2JV7=limits migrating-from-peoplebased-attribution-pba=migrating-from-people-based-attribution-pba h_01KGPKPGSF3VSBTQJR6JN80BF4=migrating-from-people-based-attribution-pba h_01KGPKQPWC1GYYGYYD6PCDWX29=key-differences h_01KGPKQPWD00B08Z76ZYGRP4AT=migration-steps" />

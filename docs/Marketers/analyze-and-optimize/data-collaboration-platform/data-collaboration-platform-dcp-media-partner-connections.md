---
title: Data Collaboration Platform (DCP) media partner connections
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2026-04-12T14:19:36Z'
  edited_at: '2026-05-24T13:27:09Z'
  id: 45669216166417
  locale: en-us
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/45669216166417-Data-Collaboration-Platform-DCP-media-partner-connections
---
<div id="at-a-glance" />

## At a glance

Connect your audiences to media partners so you can activate your tailored campaigns and achieve maximum results.

<div id="about-partner-connections" />

## About partner connections

<Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-guide">Data Collaboration Platform (DCP)</Anchor> partner connections enable you to securely connect your DCP audiences to supported media partners, so you can activate tailored campaigns on their platforms. Once a partner is connected to an audience, DCP delivers the audience based on the configured refresh and activation flow, using the latest available source data and <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-create-and-manage-sources#sharing-permissions">permissions</Anchor>.

<div id="note" />

> 📘 **Note**
>
> * The audience is delivered for activation as a list of user identifiers. Each delivery represents a full audience snapshot at the time of export.
> * Audience refreshes are not continuous or in real-time. Instead, they are triggered according to the defined policy, which is cadence-based and checks whether the source data has been updated. Each refresh generates and sends the audience list to the selected destinations.

<div id="supported-partner-connections" />

## Supported partner connections

This section lists the media partner connections supported by DCP, along with each partner’s setup requirements, permissions, supported campaign types, and any additional requirements or limitations.

<div id="google-ads" />

<Accordion title="Google Ads">

**Media partner platform:**  
Google Ads

**Media partner name in DCP:**  
Google Ads

**Media partner’s connection setup and account permissions requirements:**

* Active Google account.
* User access: Standard or Admin access to the Google Ads account
* Customer Match: Must be enabled and approved
* Partner authorization: Account approved to work with the partner (via Google rep)
* Partner link: Backend connection created by Google

**How it works:**

A Standard/Admin user must enable the integration during setup.   
After that, the DCP uploads audiences automatically via the Partner Link.

**Official resources:**  
<Anchor target="_blank" href="https://support.google.com/google-ads/answer/10589050">Google Ads Customer Match help</Anchor>

**Supported campaign types:**

* **Search**  
  Use Customer Match lists in Observation or Targeting mode to adjust bids or refine targeting for search queries.
* **Display**  
  Target or exclude audiences directly across the Google Display Network using Customer Match lists.
* **Video (YouTube)**  
  Use audiences for targeting ads on YouTube (in-stream, in-feed, Shorts).
* **Shopping**  
  Apply audiences in Observation mode to optimize bids for users on Shopping campaigns.
* **Performance Max (PMax)**  
  Use Customer Match lists as audience signals to guide Google’s automation (not strict targeting).
* **Demand Gen**  
  Use Customer Match lists for direct audience targeting across YouTube, Discover, and Gmail.
* **App Campaigns**   
  App Campaigns for installs (ACi) use uploaded audiences only as optimization signals, while re-engagement campaigns (ACe) support deterministic targeting and are the primary method for audience activation.

<div id="app-campaigns-aci--ace-guidelines" />

#### App campaigns (ACi & ACe) guidelines

Google App campaigns (formerly known as Universal App Campaign - UAC) behave differently from other campaign types when using Customer Match audiences:

**App Campaigns for Installs (ACi)**

Designed for acquiring new users at scale.  
Customer Match audiences **cannot be used for direct targeting.**  
Uploaded audiences are used **only as signals** to improve Google’s machine learning and optimization.  
Activation is **fully automated by Google AI**, with no control over audience inclusion/exclusion.  
Requires sufficient account history (e.g., conversion data and spend) to be eligible.

**App Campaigns for Engagement (ACe)**

Designed for **re-engaging existing users.**  
Customer Match audiences support **deterministic targeting.**  
Advertisers can:

* Retarget specific user segments (e.g., churned users, purchasers)
* Run lifecycle campaigns (upsell, cross-sell, retention)

Audience lists from DCP are used as primary targeting criteria, similar to other platforms.

<div id="notes" />

> 📘 **Notes**
>
> * Use ACi when your goal is scale and user acquisition (audiences = signals only).
> * Use ACe when your goal is re-engagement and precise audience targeting (audiences = direct targeting).

**Connection expiration:**

* Connections are generally persistent and don't expire automatically
* Re-authentication may be required if OAuth tokens are revoked, account permissions change, password/security settings are updated, or Google partner authorization changes

**Audience freshness:**

* Customer Match memberships expire after 540 days unless refreshed
* Recommended operational validation: every 60–90 days
* Recommended audience refresh: daily for performance/lifecycle campaigns; minimum every 7 days
* Critical audiences must not remain stale for more than 7 days

**Additional requirements/limitations:**

* Customer Match lists require a minimum of 1,000 active, matched users before they can be used to serve ads.
* EU Consent (DMA): You must add that for users in the European Economic Area (EEA), passing explicit, granted consent signals (ad\_user\_data and ad\_personalization) is strictly required to use Customer Match. If consent is denied or missing, the user will not be processed.

</Accordion>

<div id="dv360" />

<Accordion title="DV360">

**Media partner platform:**  
Google DV360 (Display & Video 360)

**Media partner name in DCP:**  
DV360

**Media partner’s connection setup and account permissions requirements:**

* Active DV360 account
* User access: Partner-level or Advertiser-level access with sufficient permissions
* Audience ingestion enabled: Account must allow 1st-party audience uploads
* Partner authorization: Account approved to work with the partner (via Google rep)
* Partner link: Backend connection created by Google

**How it works:**

The appropriate DV360 access permissions are needed to enable the integration during setup.  
After that, the DCP uploads audiences automatically via the Partner Link.

**Official resources:**  
<Anchor target="_blank" href="https://support.google.com/displayvideo/answer/9134175?hl=en">Display & Video 360 audience help</Anchor>

**Supported campaign types:**

* **Display** – Used for direct audience targeting and exclusions
* **Video (YouTube & Programmatic Video)** – Used for direct audience targeting across YouTube and video inventory
* **Audio** – Used for targeting on digital audio inventory
* **Native** – Used for audience targeting across native placements
* **Connected TV (CTV)** – Used for targeting on streaming and TV inventory
* **App campaigns:** DV360 supports app install and re-engagement strategies, but in a programmatic, line-item-based model. It does not replicate Google Ads App Campaigns, and Customer Match audiences are used directly for targeting/exclusion rather than as core optimization signals or deterministic app-user targeting.

**Connection expiration:**

* Connection remains active unless revoked or permissions change (mirrors Google Ads behavior)
* Audience memberships follow Google Customer Match policies, including the 540-day expiration window

**Audience freshness:**

* Recommended operational validation: every 60–90 days
* Recommended audience refresh: daily preferred; maximum 7 days between refreshes for active campaigns

**Additional requirements / limitations:**

* Customer Match lists require a minimum of 1,000 active, matched users before they can be used to serve ads.
* EU Consent (DMA): You must add that for users in the European Economic Area (EEA), passing explicit, granted consent signals (ad\_user\_data and ad\_personalization) is strictly required to use Customer Match. If consent is denied or missing, the user will not be processed.

</Accordion>

<div id="meta-ads" />

<Accordion title="Meta Ads">

**Media partner platform:**  
Meta Ads Manager (Facebook / Instagram)

**Media partner name in DCP:**  
Meta Ads

**Media partner’s connection setup and account permissions requirements:**

* Valid personal Meta (Facebook) account
* Business Manager created and linked to your personal account
* At least one Facebook Page
* Ad Account owned by or shared with the Business Manager
* **User access:**
  * Admin access to Business Manager
  * Admin or Advertiser access to the Ad Account

You must be the ad account owner or have Admin/Advertiser permissions on an ad account connected to a Business Manager. These permissions are required to manage ads and audiences and are essential for DCP integrations.

**Important requirements:**

* The Meta user used to connect the DCP must:
  * Accept Meta Ads Terms & Conditions
  * Accept Custom Audiences Terms of Service

The same user authenticating the DCP connection must have accepted these terms, otherwise the connection will fail.

**How it works:**

You need the required permissions during setup to connect the DCP.  

After setup is complete:

* The DCP can upload and refresh audiences automatically.

**Official resources:**  
<Anchor target="_blank" href="https://www.facebook.com/business/help/1143109949216644/">Meta Business help</Anchor>

**Supported campaign types:**

Custom audiences created in the DCP can be activated across the following Meta campaign types:

* **Awareness (Brand Awareness / Reach)** – Used for broad audience targeting
* **Traffic** – Used to drive users to a destination (e.g., website or app)
* **Engagement** – Used for optimizing interactions (e.g., post engagement, video views)
* **Leads** – Used for lead generation campaigns
* **App Promotion** – Used for app installs and re-engagement
* **Sales (Conversions)** – Used for driving purchases or other conversion events

DCP audiences (Custom Audiences) can be used for direct targeting across all Meta campaign types, supporting full-funnel use cases from awareness to conversion.

**Connection expiration:**

* Connections are generally long-lived but may break due to: password resets, MFA/security changes, revoked permissions, Business Manager ownership changes, or Meta policy reviews

**Audience freshness:**

* Recommended operational validation: every 60–90 days
* Recommended audience refresh: daily for conversion/lifecycle campaigns; every 3–7 days acceptable for awareness campaigns

</Accordion>

<div id="tiktok" />

<Accordion title="TikTok">

**Media partner platform:**  
TikTok Ads Manager

**Media partner name in DCP:**  
TikTok

**Media partner’s connection setup and account permissions requirements:**

TikTok Ads Manager account.  
Approved and active advertiser account.  
Admin access to the advertiser.  

Active TikTok Ads account (Ads Manager)

* **Ad Account access:**
  * Admin or Operator access to the TikTok Ads account
* **Audience permissions:**
  * Ability to create and manage Custom Audiences
* **Partner authorization:**
* The partner (DCP) must be granted access via TikTok Business Center or Ads Manager

**How it works:**

An Admin or Standard user is required during setup to authorize and connect the DCP.  

After setup is complete:

* The DCP can upload and refresh audiences automatically
* Audience activation happens directly within TikTok Ads using those uploaded audiences

**Official resources:**  
<Anchor target="_blank" href="https://ads.tiktok.com/help/article/invite-partners-into-tiktok-business-center?lang=en">TikTok Business Center partner access help</Anchor>

**Supported campaign types:**

Custom Audiences created in the DCP can be activated across the following TikTok campaign types:

* **Reach** – Used for maximizing audience exposure
* **Traffic** – Used to drive users to a website or landing page
* **Video Views** – Used to maximize video engagement
* **Lead Generation** – Used to collect leads directly on TikTok
* **App Promotion** – Used for app installs and re-engagement
* **Conversions (Website Conversions)** – Used to drive actions such as purchases or sign-ups

DCP audiences (Custom Audiences) can be used for direct targeting across all TikTok campaign types, supporting full-funnel use cases from awareness to conversion.

**Connection expiration:**

* OAuth/business authorization may expire or be revoked due to permission or admin changes

**Audience freshness:**

* Recommended token and permission validation: quarterly
* Recommended audience refresh: daily preferred; maximum 7 days for active audiences

**Additional requirements / limitations:**

* Minimum Audience Size: A Custom Audience requires a strict minimum of 1,000 total matched users before it can be applied to an ad group

</Accordion>

<div id="pinterest" />

<Accordion title="Pinterest">

**Media partner platform:**  
Pinterest Ads Manager

**Media partner name in DCP:**  
Pinterest

**Media partner’s connection setup and account permissions requirements:**

* Active Pinterest Business account  
  Ads Manager account linked to the business
* **User access:**
  * Admin or Analyst (with audience permissions) access to the ad account
* **Audience permissions:**
  * Ability to create and manage Customer Lists (audiences)
* **Partner access:**
  * The partner (DCP) must be granted access to the ad account via Business Manager

**How it works:**

An Admin or (or sufficient) user is required during setup to connect the DCP and grant permissions.  

After setup is complete:

* The DCP can upload and refresh audiences automatically

**Official resources:**  
<Anchor target="_blank" href="https://help.pinterest.com/en/business/article/audience-targeting">Pinterest audience targeting help</Anchor>

**Supported campaign types:**

Customer List audiences created in the DCP can be activated across the following Pinterest campaign types:

* **Awareness** – Used to maximize reach and brand visibility
* **Consideration (Traffic / Engagement / Video Views)** – Used to drive clicks, engagement, or video views
* **Conversions** – Used to drive actions such as purchases, sign-ups, or other conversion events
* **Catalog Sales (Shopping ads)** – Used to promote products from a catalog and drive purchases

DCP audiences (Customer Lists) can be used for direct targeting across all Pinterest campaign types, supporting full-funnel use cases from awareness to conversion, including shopping/catalog campaigns.

**Connection expiration:**

* OAuth tokens and partner permissions may expire or be revoked depending on business/account changes

**Audience freshness:**

* Recommended operational reconnect validation: every 60–90 days
* Recommended audience refresh: every 1–7 days, depending on campaign type

</Accordion>

<div id="the-trade-desk" />

<Accordion title="The Trade Desk">

**Media partner platform:**  
The Trade Desk (TTD)

**Media partner name in DCP:**  
The Trade Desk

**Media partner’s connection setup and account permissions requirements:**

* Active The Trade Desk (TTD) account
* **User access:**
  * Admin or Trader-level access to the account
* **Audience permissions:**
  * Ability to create and manage first-party audiences (data segments)
* **Data sharing enabled:**
  * Account must allow data onboarding / audience ingestion from external partners (such as DCPs)
* **Partner authorization:**
  * The partner (DCP) must be approved and linked as a data provider in TTD
* **API credentials (required)** Required for API-based audience upload and activation:
  * Generate from the “First Party Data Credentials” section in TTD (or request them from your TTD account admin):
    * Advertiser ID
    * Advertiser Secret Key

**How it works:**

An Admin or Trader user is required during setup to:

* Enable the integration
* Generate API credentials
* Approve partner data sharing

After setup is complete:

* The DCP uploads audiences via API credentials + partner configuration
* Audiences are available as first-party data segments in TTD

**Official resources:**  
<Anchor target="_blank" href="https://www.thetradedesk.com/">The Trade Desk platform</Anchor>

**Supported campaign types:**

First-party audiences created in the DCP can be activated across the following TTD campaign types:

* **Display** – Used for direct audience targeting across web and in-app inventory
* **Video (Online Video & CTV)** – Used for targeting on programmatic video and connected TV inventory
* **Audio** – Used for targeting on digital audio/streaming platforms
* **Native** – Used for audience targeting across native ad formats

DCP audiences in The Trade Desk are used for direct targeting across all campaign types, including Display, Video (CTV & OLV), Audio, and Native, enabling deterministic audience activation across channels.

**Connection expiration:**

* API credentials are typically long-lived until manually rotated or revoked
* Recommended credential rotation: every 6–12 months per security policy

**Audience freshness:**

* Recommended audience refresh: daily or weekly, depending on activation use case and segment volatility

</Accordion>

<div id="create-a-partner-connection" />

## Create a partner connection

You can set up partner connections as part of the audience-builder flow or separately.

<div id="setup-as-part-of-the-audiencebuilder-flow" />

<Accordion title="Setup as part of the audience-builder flow">

<span id="h_01HZHF5BWHBE7W8VNM3QFB7K58"></span>**To create a media partner connection as part of the audience-builder flow:**

Follow the instructions detailed <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-build-and-activate-audiences#step-3-connect-and-export">here</Anchor>.

</Accordion>

<div id="separate-setup" />

<Accordion title="Separate setup">

<span id="h_01HZHF5BWH7P8HCWS9SG1JQ2BT"></span>**To create a connection outside the audience-builder flow:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Data Clean Room**.
2. From the top-right menu, click **Manage connections**.
3. Click **New connection**. If you already have existing cloud connections in your account, you'll see them all under **Partner**.
4. From the **New media partner connection** dialog, select the relevant media partner.

   <Image align="center" alt="New media partner connection.png" src="https://files.readme.io/1c50a570d4eb495c3d77ee8e572b14a577e39adad65e41fe20eb3b014cce8989-46196842129425.png" width="91.09%" />
5. Enter a connection name.
6. Log in to the media partner account with your credentials, and follow their instructions to enable AppsFlyer access.
7. Click **Select account ID** and select the relevant account for this connection.
8. Click **Save**. The new connection is added to the list of partners.

</Accordion>

<div data-zendesk-anchors="h_01KNS1JFT1R7K6MCWJRGA2EAAY=at-a-glance h_01KNS1JFT1C788JKA9ZH657TE0=about-partner-connections h_01KP0WCJVS71MZ5XEXRHRWXX2Q=note media-partner-connections=supported-partner-connections h_01KNS1JFT1CT1AC1C6PAZAM779=supported-partner-connections h_01KNS1JFT1RE8MA525AJ99D9DS=google-ads app-campaigns-aci-ace-guidelines=app-campaigns-aci--ace-guidelines h_01KQC3Y84E1GT5VJB463N42SFT=app-campaigns-aci--ace-guidelines h_01KQC759QZPWJ7MWGPK7TJ06HW=notes h_01KNS1JFT1VESJCKHV4S11EKST=dv360 h_01KNS1JFT1P3ZR6EG6YR0M1F98=meta-ads h_01KNS1JFT1GTXJ4PMV5QKSDEX9=tiktok h_01KNS1JFT18VRXFHBYPRTS2MS6=pinterest h_01KNS1JFT2GJMKYNGR6ZRMWN25=the-trade-desk h_01KP115WC2QNT7MAS73HZSHQJT=create-a-partner-connection h_01KP11SX0VMYNRCY9C7GKQPYGB=setup-as-part-of-the-audiencebuilder-flow h_01KP11SX0VCAQM5MEGV3RKG086=separate-setup" />

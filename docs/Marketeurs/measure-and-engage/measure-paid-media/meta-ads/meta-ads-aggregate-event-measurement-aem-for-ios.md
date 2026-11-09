---
title: Meta Ads—Aggregate Event Measurement (AEM) for iOS
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-10-09T16:40:55Z'
  edited_at: '2026-10-26T09:47:12Z'
  id: 19228737402129
  locale: en-us
  section: Meta ads
  section_id: 6551109855761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/19228737402129-Meta-Ads-Aggregate-Event-Measurement-AEM-for-iOS
---
> **At a glance:** Learn about the Aggregated Event Measurement (AEM) solution for optimizing iOS conversions and in-app events and for attributing iOS re-engagements on Meta Ads.

## Overview

AppsFlyer supports the <Anchor target="_blank" href="https://www.facebook.com/business/help/721422165168355">Meta Ads Aggregated Event Measurement (AEM)</Anchor> solution. This solution enables measuring web and app events for iOS 14+ devices using the following attribution methods:

* [App AEM for re-engagement](#app-aem-for-re-engagement)
* [App AEM for app promotion](#app-aem-for-app-promotion)

As part of the AEM solution, Meta accepts conversion and in-app postbacks from the advertiser, provided that the events qualify for AEM. To check the AEM eligibility of your events, see the following:

* [Check if your app events are eligible for AEM](#check-if-your-app-events-are-eligible-for-aem)

## App AEM for re-engagement

Using AEM, Meta Ads provides deep-link re-engagement attribution for iOS users when the Advertiser ID is unavailable.

### Attribution flow

Meta Ads appends attribution data to the deep link along with the AEM `campaign_ids` identifier. AppsFlyer receives and processes the campaign parameters shown in the deep link URL, then:

* Makes aggregate reporting data available to Meta Ads
* Performs attribution based on the deep link information appended by Meta Ads
* Includes attribution data from the deep link in raw data and aggregated data reports

### Attribution data parameters

The following attribution data parameters, as shared by Meta Ads, are included in the reports:

* `ad_id`
* `adgroup_id`
* `campaign_id`
* `campaign_group_id`
* `account_id`

> 📘 **Note**
>
> To leverage AEM for remarketing, the AppsFlyer SDK retrieves the `campaign_ids` string on deep link open. By default, the SDK shares deep links from all domains. If you have customized your integration, make sure it is configured to share deep links from all domains, including the Meta domain, and not only from the AppsFlyer domain.

### FAQs on deep link re-engagement attribution

<div id="what-must-the-advertiser-do-to-enable-this-attribution" />

<Accordion title="What must the advertiser do to enable this attribution?">

**No action is needed** from the advertiser to receive these parameters for attribution.

However, to measure deep link re-engagement attribution, the **Re-engagement attribution toggle** **must be turned on**.

**Note:** According to Meta Ads' terms and conditions about AEM, enabling re-engagement attribution measurement means postbacks to Meta Ads might include partial IP addresses as part of the attribution data.

</Accordion>

<div id="what-about-agencies-and-meta-campaign-management-partners" />

<Accordion title="What about agencies and Meta campaign management partners?">

At this stage, attribution for agencies and Meta campaign management partners is not supported. This means all traffic is attributed to Meta Ads. This is temporary and will change soon.

</Accordion>

<div id="are-there-any-restrictions-on-data-from-this-attribution" />

<Accordion title="Are there any restrictions on data from this attribution?">

Data coming from deep link attributions isn't subject to reporting restrictions. This means all data appears in both aggregated and user-level raw reports.

</Accordion>

## App AEM for app promotion

### AEM eligibility

When an app is eligible for AEM on Meta Ads, **Aggregated Event Measurement** is selected by default during Ad Set creation. This means both AEM and SKAdNetwork (SKAN) can be used simultaneously for the campaign. If **Apple SKAdNetwork** is selected instead, only SKAN will apply to the campaign. This means AppsFlyer has limited ability to measure app activity on Meta Ads.

<Image align="center" alt="aem_meta_ads_platform.png" src="https://files.readme.io/9ce9735024294967545fee9e9fc44cc49834ffcb5b3496febd50f8466c1bd397-46192072798737.png" width="563px" />

> 📘 **Note**
>
> If you have issues with AEM eligibility, see [Check if your app events are eligible for AEM](#check-if-your-app-events-are-eligible-for-aem).

### AEM data sharing

**Advanced data sharing** enables you to make all qualifying conversion events available to Meta ads for measurement, including events from users for whom an Advertiser ID is unavailable.

* When turned off, Advanced data sharing is limited to conversion events for users with an available Advertiser ID. Events from users without an Advertiser ID are not shared or attributed.
* When enabled, Advanced data sharing makes conversion events available to Meta ads for all users, including those without an Advertiser ID. AppsFlyer attributes these events. The data made available might include additional device-related information that does not involve the device ID. To learn more, see <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-integration-setup#advanced_data_sharing">Advanced data sharing</Anchor>.

<Image align="center" alt="aem" src="https://files.readme.io/77e44d893994581dbe1a058fb5bebbf9b5e8bf167abe6e9d35ea8aa809ceca4b-46192056604305.png" />

> 📘 **Note**
>
> * All events include installs, app opens, and in-app events.
> * Before enabling **Advanced data sharing**, make sure that making this data available to Meta ads, including any use of your data by third parties, complies with any platform policies or regulations to which you are subject. Data made available might include IP addresses, anon\_ids (if available), vendor\_id, and user agents.
> * For in-app events sent via server-to-server (S2S), Meta Ads requires both the **IP address** and the **Identifier for Vendors (IDFV)** to be included in the event payload. Without these identifiers, the event won't be eligible for Meta Ads attribution in AEM.
> * Meta AEM for app promotion might also include non-deterministic view-through claims. To support non-deterministic view-through attribution via Meta AEM, make sure the app-level Enable view-through attribution via campaign measurement modeling toggle is turned on. For details, see <Anchor target="_blank" href="/marketers/fr/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">View-through attribution via probabilistic modeling</Anchor>.

## Check if your app events are eligible for AEM

You can visit Meta Events Manager to check if your app events are eligible for AEM. Once your app event is eligible, you can see the results of your selected AEM campaigns in Ads Manager. To learn how to check if your app events are eligible for AEM, see <Anchor target="_blank" href="https://www.facebook.com/business/help/716239976391518?id=1877298665783613">Meta documentation</Anchor>.

## Enable AEM: summary

Use the table below as a quick checklist to enable Meta Ads AEM in AppsFlyer.

| **Solution** | **Toggle** | **Toggle location** | **Impact** |
| --- | --- | --- | --- |
| **AEM remarketing (re-engagements)** | Re-engagement attribution | Partner integration (Meta Ads) | Enables AEM for remarketing (re-engagement attribution). |
| **AEM app promotion (installs)** | Advanced data sharing | Partner integration (Meta Ads) | Enables AEM for app promotion, including making events from users when an Advertiser ID is not available, making them measurable via Meta, and accepting non-deterministic claims (when applicable). |
| **AEM app promotion (installs)** | Enable view-through attribution via probabilistic modeling | App Settings | Enables view-through attribution for non-deterministic claims. |

## Troubleshooting

<div id="troubleshooting-ineligible-events-in-meta-aem" />

<Accordion title="Troubleshooting ineligible events in Meta AEM">

If Meta Ads flags your app events as ineligible, showing errors like **“Missing opt-out events”** or other AEM-related messages, it’s typically due to missing or misconfigured data. Use the checklist below to diagnose and fix common issues.

> 🚧 **Important!**
>
> After you complete the steps below, allow time for changes to take effect. Meta Ads might take up to **2–3 days** to reflect AEM eligibility.

<div id="step-1-advanced-data-sharing-is-enabled" />

<Accordion title="Step 1: Advanced data sharing is enabled">

1. Go to **Collaborate** > **Active Integrations** > **Meta Ads**.
2. Make sure that **Advanced data sharing** is turned on.

</Accordion>

<div id="step-2-ip-masking-is-disabled" />

<Accordion title="Step 2: IP masking is disabled">

Events with masked IPs aren’t eligible for AEM.

* Go to **App Settings**.
* Make sure **IP masking** is turned off.

</Accordion>

<div id="step-3-servertoserver-s2s-events-include-required-parameters" />

<Accordion title="Step 3: Server-to-Server (S2S) events include required parameters">

Every S2S event must include:

* **IP address**
* **IDFV** (Identifier for Vendors)

</Accordion>

<div id="step-4-review-att-consent-rate" />

<Accordion title="Step 4: Review App Tracking Transparency (ATT) consent rate">

Meta accepts a limited volume of events with missing or zeroed-out Identifier for Advertisers (IDFA) values. If your app exceeds this threshold, you might see the following error: "**Advertiser Tracking Enabled parameter volume out of range."**

</Accordion>

<div id="step-5-postback-mapping-configuration" />

<Accordion title="Step 5: Postback mapping configuration">

Make sure event postbacks are mapped to **Send all (including organic)**.

</Accordion>

<div id="step-6-check-reengagement-settings-if-relevant" />

<Accordion title="Step 6: Check re-engagement settings (if relevant)">

For re-engagement campaigns:

* Enable **Re-engagement attribution** in both **App Settings** and the **Meta Active integration page**.

</Accordion>

#### Still not working?

If specific events remain ineligible:

1. Go to Meta's Event Manager and follow the on-screen guidance.
2. Select the affected app event.
3. Set **MMP traffic** as the preferred connection method.

#### Need help?

If the issue persists:

* Submit a support ticket
* Include a screenshot from Meta Ads showing the ineligible events

</Accordion>

<div id="i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible" />

<Accordion title="I don't receive AEM data in dashboards and reports, although my campaigns are AEM-eligible">

Here is Meta's reply: "We are rolling out this update in collaboration with your MMP over the next several months, and some advertisers may not have access until rollout is complete."

</Accordion>

<div id="why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement" />

<Accordion title="Why can't I see AEM-attributed installs in raw reports even after signing the AMM agreement?">

When AAP is enabled, installs attributed via Meta's Aggregated Event Measurement (AEM) are excluded from raw data reports. This applies even if the AMM agreement is signed.

</Accordion>

> 📘 **Note**
>
> When **Advanced data sharing** is on, Meta can claim and attribute installs through Aggregated Event Measurement (AEM) even when no opt-in data is available, including when no IDFA is ever collected. However, AEM results might improve as more IDFA signals become available, so we recommend sending as many opt-in events as possible.

<div data-zendesk-anchors="h_01HCAM4CEVRCG13CA32B0GM9QS=overview app-aem-for-reengagement=app-aem-for-re-engagement 01H88ZM20H99W37M0H6XXQVMQA=app-aem-for-re-engagement 01H7YJVNMV7QSZJWKZZA9042K6=attribution-flow 01H7YJVNMVPPCD08Z2R0V5GCMY=attribution-data-parameters h_attribution_deeplink_note=note faqs-on-deep-link-reengagement-attribution=faqs-on-deep-link-re-engagement-attribution 01H7YJVNMV4ZKMWKD06RC6GKFW=faqs-on-deep-link-re-engagement-attribution 01H7YJVNMVSGMNJ3K84MCENXYG=what-must-the-advertiser-do-to-enable-this-attribution 01H7YJVNMVP7ZRCKXDRRH7GZBY=what-about-agencies-and-meta-campaign-management-partners are-there-any-restrictions-on-data-from-this%20attribution=are-there-any-restrictions-on-data-from-this-attribution 01H7YJVNMVQF0B0DV2NQYQVYHK=are-there-any-restrictions-on-data-from-this-attribution 01H88ZM20HQFMG962AZGYA98FR=app-aem-for-app-promotion 01H7YJVNMVPB054VFS60KH9N7W=aem-eligibility h_01HR886Q0KPM99FCQXD6RDPSBK=note-1 01H88ZM20HK2HY32M4BKZ4N0B9=aem-data-sharing 01H7YK9CHHNARCD7M2VZRMEW6S=note-2 check-eligibility=check-if-your-app-events-are-eligible-for-aem 01JBHQSHF8NA4SGVJ3WYPRN9B3=check-if-your-app-events-are-eligible-for-aem enable-aem-toggles-summary=enable-aem-summary h_01KJ28ETP9GK6TBTJK8SBZ5PFW=enable-aem-summary faqs-and-troubleshooting=troubleshooting 01H7YK9CHHZN78CBHFTQ7E9RKQ=troubleshooting h_01K720W9MYXFTYG18368SKHGGC=troubleshooting-ineligible-events-in-meta-aem h_01K720W9MYDKK5Q2J1M8VT9JFP=important h_01K722GQSB92J5KFFYQNP5WR29=step-1-advanced-data-sharing-is-enabled h_01K722GQSBV3GY2ZNN29ENG7Q2=step-2-ip-masking-is-disabled h_01K722GQSBVTSC09EPPCZQ6WN3=step-3-servertoserver-s2s-events-include-required-parameters h_01K722GQSBSX06A56ZX8RJ6YKT=step-4-review-att-consent-rate h_01K722GQSB26TN65JVJD6R7BAV=step-5-postback-mapping-configuration h_01K722GQSBTD4J9TZHBRGYS1XV=step-6-check-reengagement-settings-if-relevant h_01K722GQSB8CXSSCVZPA3R3CJX=still-not-working h_01K722GQSBBB8KS8JNRBJZ4WWT=need-help 01JCX7SKJ76KGW9SN7RCFA18E6=i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible why-can%27t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement h_01K4ADBT26D2KD5MH568542XSV=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement h_01M5VSB77G1VDKA6SJC81XNNFX=note-3" />

---
title: "Meta Ads—Aggregate Event Measurement (AEM) for iOS"
excerpt: "Learn about the AEM solution for optimizing iOS conversions and in-app events and for attributing iOS re-engagements on Meta Ads."
x-zendesk:
  id: 19228737402129
  url: https://support.appsflyer.com/hc/en-us/articles/19228737402129-Meta-Ads-Aggregate-Event-Measurement-AEM-for-iOS
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Meta ads
  section_id: 6551109855761
  position: 7
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution, Agencies]
  labels: [Agencies, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2023-10-09T16:40:55Z'
  edited_at: '2026-05-25T14:38:28Z'
---
AppsFlyer supports the [Meta Ads Aggregated Event Measurement (AEM)](https://www.facebook.com/business/help/721422165168355) solution. This solution enables measuring web and app events for iOS 14+ devices using the following attribution methods:

- [App AEM for re-engagement](/docs/meta-ads-aggregate-event-measurement-aem-for-ios#app-aem-for-reengagement)
- [App AEM for app promotion](/docs/meta-ads-aggregate-event-measurement-aem-for-ios#app-aem-for-app-promotion)

As part of the AEM solution, Meta accepts conversion and in-app postbacks from the advertiser, provided that the events qualify for AEM. To check the AEM eligibility of your events, see the following:

- [Check if your app events are eligible for AEM](/docs/meta-ads-aggregate-event-measurement-aem-for-ios#check-eligibility)

## App AEM for re-engagement

Using AEM, Meta Ads provides deep-link re-engagement attribution for iOS users where the Advertiser ID is not available.

### Attribution flow

Meta Ads appends attribution data to the deep link along with the AEM `campaign_ids` identifier. AppsFlyer receives and processes the campaign parameters showing on the deep link URL, then:

- Makes aggregate reporting data available to Meta Ads
- Performs attribution based on the deep link information appended by Meta Ads
- Includes attribution data from the deep link in raw data and aggregated data reports

### Attribution data parameters

The following attribution data parameters, as shared by Meta Ads, are included in the reports:

- `ad_id`
- `adgroup_id`
- `campaign_id`
- `campaign_group_id`
- `account_id`

> 📘 Note
>
> To leverage AEM for re-marketing, the AppsFlyer SDK retrieves the `campaign_ids` string on deep link open. By default, the SDK shares deep links from all domains. If you have customized your integration, make sure it is configured to share deep links from all domains, including the Meta domain, and not only from the AppsFlyer domain.

### FAQs on deep link re-engagement attribution

#### What must the advertiser do to enable this attribution?

**No action is needed** from the advertiser to receive these parameters for attribution.

However, for the deep link re-engagement attribution to be measured, the **Re-engagement attribution toggle** **must be turned on**.

> 📘 Note
>
> According to Meta Ads' terms and conditions regarding AEM, enabling re-engagement attribution measurement means postbacks to Meta Ads may include partial IP addresses as part of the attribution data.

#### What about agencies and Meta campaign management partners?

At this stage, attribution for agencies and Meta campaign management partners is not supported. This means all traffic is attributed to Meta Ads. This is temporary and will change soon.

#### Are there any restrictions on data from this attribution?

Data coming from deep link attributions isn't subject to reporting restrictions. This means all data appears both in aggregated and user-level raw data reports.

## App AEM for app promotion

### AEM eligibility

When an app is eligible for AEM on Meta Ads, during the Ad Set creation process **Aggregated Event Measurement** is selected by default. This means both AEM and SKAN can be used simultaneously for the campaign. If **Apple's SKAdNetwork** is selected instead, only SKAN will be applicable for the campaign. This means AppsFlyer has limited ability to measure the app activity on Meta Ads.

![aem_meta_ads_platform.png](https://files.readme.io/9ce9735024294967545fee9e9fc44cc49834ffcb5b3496febd50f8466c1bd397-46192072798737.png)

> 📘 Note
>
> If you have issues with AEM eligibility, see the [check if your app events are eligible for AEM](/docs/meta-ads-aggregate-event-measurement-aem-for-ios#check-eligibility).

### AEM data sharing

**Advanced data sharing** enables you to make all qualifying conversion events available to Meta ads for measurement, including events from users for whom an Advertiser ID is unavailable.

- When turned off, Advanced data sharing is limited to conversion events for users whose Advertiser ID is available. Events from users without an Advertiser ID are not shared or attributed.
- When turned on, Advanced data sharing enables conversion events to be made available to Meta ads for all users, including those where an Advertiser ID is not available. AppsFlyer attributes these events. The data made available may include additional device-related information that does not involve the device ID. To learn more, see [Advanced data sharing](/docs/meta-ads-integration-setup#advanced_data_sharing).

![aem](https://files.readme.io/77e44d893994581dbe1a058fb5bebbf9b5e8bf167abe6e9d35ea8aa809ceca4b-46192056604305.png)

> 📘 Note
>
> - All events include installs, app opens, and in-app events.
> - Before enabling **Advanced data sharing**, make sure that making this data available to Meta ads, including any use of your data by third parties, complies with any platform policies and/or regulations to which you are subject. Data made available may include IP addresses, anon\_ids (if available), vendor\_id, and user agents.
> - For in-app events sent via server-to-server (S2S), Meta Ads requires both the **IP address** and the **Identifier for Vendors (IDFV)** to be included in the event payload. Without these identifiers, the event won't be eligible for Meta Ads attribution in AEM.
> - Meta AEM for app promotion may also include nondeterministic view-through claims. To support nondeterministic view-through attribution via Meta AEM, make sure the app-level Enable view-through attribution via campaign measurement modeling toggle is turned on. For details, see [View-through attribution via probabilistic modeling](/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling).

## Check if your app events are eligible for AEM

You can visit Meta Events Manager to check if your app events are eligible for AEM. Once your app event is eligible, you can see the results of your selected AEM campaigns in Ads Manager. To learn how to check if your app events are eligible for AEM, see [Meta documentation](https://www.facebook.com/business/help/716239976391518?id=1877298665783613).

## How to enable AEM - summary

Use the table below as a quick checklist to enable Meta Ads AEM in AppsFlyer.

| **Solution** | **Toggle** | **Toggle location** | **Impact** |
| --- | --- | --- | --- |
| **AEM remarketing (re-engagements)** | Re-engagement attribution | Partner integration (Meta Ads) | Enables AEM for remarketing (re-engagement attribution). |
| **AEM app promotion (installs)** | Advanced data sharing | Partner integration (Meta Ads) | Enables AEM for app promotion, including making events from users where an Advertiser ID is not available, measurable via Meta, and accepting non-deterministic claims (when applicable). |
| **AEM app promotion (installs)** | Enable view-through attribution via probabilistic modeling | App Settings | Enables view-through attribution for non-deterministic claims. |

## Troubleshooting

### Troubleshooting ineligible events in Meta AEM

If Meta Ads flags your app events as ineligible—showing errors like **“Missing opt-out events”** or other AEM-related messages—it’s typically due to missing or misconfigured data. Use the checklist below to diagnose and fix common issues.

> ❗️ Important!
>
> After you complete the steps below, allow time for changes to take effect. After changes are applied, Meta Ads may take up to **2–3 days** to reflect AEM eligibility.

#### Step 1: Advanced Data Sharing is enabled

1. Go to **Collaborate** \> **Active Integrations** \> **Meta Ads**.
2. Make sure that **Advanced Data Sharing** is turned on.

#### Step 2: IP masking is disabled

Events with masked IPs aren’t eligible for AEM.

- Go to **App Settings**.
- Ensure **IP masking** is turned off.

#### Step 3: Server-to-Server (S2S) events include required parameters

Every S2S event must include:

- **IP address**
- **IDFV** (Identifier for Vendors)

#### Step 4: Review ATT consent rate

Meta accepts a limited volume of events with missing or zeroed-out IDFAs. If your app exceeds this threshold, you may see this error: **Advertiser Tracking Enabled parameter volume out of range.**

#### Step 5: Postback mapping configuration

Ensure event postbacks are mapped to **Send all (including organic)**.

#### Step 6: Check re-engagement settings (if relevant)

For re-engagement campaigns:

- Enable **Re-engagement Attribution** in both **App Settings** and the **Meta Active integration page**.

#### Still not working?

If specific events remain ineligible:

1. Go to Meta's Event Manager and follow the on-screen guidance.
2. Select the affected app event.
3. Set **MMP traffic** as the preferred connection method.

#### Need help?

If the issue persists:

- Submit a support ticket
- Include a screenshot from Meta Ads showing the ineligible event(s)

### I don't receive AEM data in dashboards and reports, although my campaigns are AEM-eligible

Here is Meta's reply: "We are rolling out this update in collaboration with your MMP over the next several months and some advertisers may not have access until rollout is complete."

### Why can't I see AEM-attributed installs in raw reports even after signing the AMM agreement?

When AAP is enabled, installs attributed via Meta's Aggregate Event Measurement (AEM) are excluded from raw data reports. This applies even if the AMM agreement is signed.
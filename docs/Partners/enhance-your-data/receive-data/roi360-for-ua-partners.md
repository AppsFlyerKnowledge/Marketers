---
title: "ROI360 for UA partners"
excerpt: "AppsFlyer provides UA partners with complete and accurate ad, in-app purchases, and auto-renewable subscription data via reports and postbacks to optimize UA campaigns."
x-zendesk:
  id: 17735150011921
  url: https://support.appsflyer.com/hc/en-us/articles/17735150011921-ROI360-for-UA-partners
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Receive data
  section_id: 6551235995281
  position: 5
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Mobile Attribution, Ad Networks]
  labels: [Ad Networks, Partners]
  promoted: false
  comments_disabled: false
  created_at: '2023-08-12T17:09:08Z'
  edited_at: '2024-10-27T14:32:39Z'
---
AppsFlyer receives revenue information from both its partners and the app stores (Apple App Store and Google Play Store). Once received, the data undergoes a series of steps including validation, normalization, attribution, and enrichment with additional properties and dimensions.  AppsFlyer can send the information to the UA partner. Following this process, AppsFlyer transmits the enriched and attributed data to the UA partner. The UA partner can then utilize this information to optimize their user acquisition campaigns and enhance the service they offer to advertisers.

### What revenue types are reported to the partners?

Apps create two revenue types:

- **Ad revenue:** Ad revenue is generated whenever an ad is displayed in the app, like in banners, interstitial ads, and other formats. It can be calculated regardless of the campaign method by which an advertiser is billed.
- **In-app purchase and auto-renewal subscription:** Store revenue is generated whenever an in-app purchase or subscription-related transaction is performed.

### How does AppsFlyer provide revenue signals to UA partners?

AppsFlyer provides partners with information on in-app ads, in-app purchases, and subscription revenue through the following means:

- **Ad Revenue UA Signals report**: The report lists ad revenue events aggregated to the device level. The report is available daily in Data Locker and contains the data of the previous day.
- **Ad Revenue postbacks**: Every time an ad impression occurs on a client device a postback is sent from AppsFlyer to the partner containing the details of the ad revenue event.
- **Store Revenue postbacks**: Every time a purchase or subscription event occurs a postback is sent from AppsFlyer to the partner containing the details of the revenue event.

## Set up ROI360 for partners

What actions do partners need to take to receive the UA signals report and the ad revenue and store revenue postbacks?

### How to subscribe to the ROI360 UA Signals report

To enable the partner to get the report via Data Locker:

- The partner has to perform the following steps in Data Locker:
1. [Set up Data Locker](/docs/data-locker-for-partners#set-up-data-locker) in the partner account including the connection to the cloud service provider, and the reports’ format and contents.
2. [Enable the ROI360 UA Signals report](/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report).
- The advertiser has to [grant the partner permission for the report](/docs/roi360-guide-ad-revenue-attribution#permission-to-get-ad-revenue-data).

### How to receive ROI360 postbacks from AppsFlyer

To receive postbacks from AppsFlyer, partners must initiate a conversation with the AppsFlyer partner integration team. Subsequently, the team will configure the ROI in-app revenue postback values within the AppsFlyer platform.

To contact AppsFlyer partner support, open the **Help** menu in your dashboard and select **Contact our team**.

![alt](https://files.readme.io/02d80a38dfb950e01127ba8afa33dca1a8bbef9fe137fe11743afaad966244c8-17770060481809.gif)

## ROI360 UA Signals Report for UA Networks

The report provides complete and accurate day x+1 CSV/parquet revenue records to the UA partner's S3 bucket on a daily basis. Each record is an aggregation of ad revenue events on the device level.

The UA Signals report does not provide real-time data as ad revenue postbacks do. However, it is both more accurate and complete. This is because the value of an impression can change over time. This is especially true when the impression-level revenue data is for an ad impression that was sold through standard CPM bidding rather than real-time bidding.

### What are the report data sources?

Depending on the advertiser integration type, the report data can originate from either:

1. [AdRevenue SDK](/docs/integrate-the-roi360-ad-revenue-sdk-api) integrations: customers can share impression-level revenue data loaded by the partner to client devices, and then reported to AppsFlyer in near real-time.
2. S2S API-based device-level integrations: customers can configure their partner credentials within the AppsFlyer UI under integrated partners and allow ROI360 ad revenue to collect device-level ad revenue data on their behalf.
3. A combination of the two (Freshness to Accuracy). 

> 📘 Note
>
> The transfer of data from the advertiser to AppsFlyer is contingent upon advertiser permissions and whether the advertiser is a ROI360 advanced customer.

### What data processing is performed on the report data?

AppsFlyer ROI360 Ad Revenue performs the following:

1. Data normalization
2. Attribution to the install media source and data enrichment
3. Ad revenue events generation
4. Events are aggregated to the device level

### How is the report data delivered?

Device-level data is written daily to the report in Data Locker

### What is the report data freshness?

Data is written daily to the h=23 folder of your Data Locker bucket at 21:00 [UTC time](/docs/about-data-freshness-and-timezone-support#daily).

### What are the report fields?

| **Field** | **Remarks** |
| --- | --- |
| Version | Unix timestamp in second. Example: 1661315124 |
| app\_id | App ID in the AppsFlyer platform |
| install\_time | • Timestamp of install: YYYY-MM-DD HH:MM:SSExample: 2020-08-16 11:22:33 • For iOS 14+ devices and non-consenting users, or if the advertiser has Advanced Privacy on, install time is rounded to the nearest hour. |
| campaign, campaign\_id, adset\_name, adset\_id, ad\_name, ad\_name, ad\_id, site\_id | Only populated if UA is attributed to the partner receiving the data. |
| idfa, idfv, advertising\_id | • The same device ID, like IDFA, IDFV, or advertiser\_id could display in multiple rows if there are more than one ad revenue monetization events. • For iOS 14+ devices and non-consenting users, or if the advertiser has Advanced Privacy on, this does not display. |
| platform | Device platform: iOS, Android, or Windows Mobile |
| country | Country code using [ISO 3166 (alpha-2)](https://www.iso.org/iso-3166-country-codes.html) Example: US, CN |
| original\_url | • For iOS 14+ devices and non-consenting users, or if the advertiser has Advanced Privacy on, this does not display. • Only populated if UA is attributed to the partner receiving the data. |
| mediation\_network | The mediation network associated with the impression or impressions. [See list of possible networks](/docs/roi360-guide-ad-revenue-attribution#[closed-beta]-ua-signals-for-ad-networks) |
| ad\_unit | Coming Q3 2023: The monetization ad\_unit associated with the impression or impressions |
| placement | Coming Q3 2023: The monetization placement associated with the impression or impressions |

### Download the report data sample

[Click to download the report](https://docs.google.com/spreadsheets/d/e/2PACX-1vSiPD52sbLAcl3mGbAFAiqsCZuSpUamrWP8n9BDyvI11DyNlckiKj-Peuo_fbSuIu-XnUxZqwAMEojT/pub?output=csv)

## In-app ad revenue (IAA) postbacks

IAA postbacks are the second ingestion approach that AppsFlyer uses to send revenue information to partners. Their main advantage over the Ad Revenue UA signals report is their freshness, as postbacks offer near real-time IAA revenue data sharing. This is in contrast to the X+1  freshness (one day after the event occurrence date) offered through the ad revenue UA signals report.

However, real-time freshness is less accurate compared to X+1:

- Real-time IAA postbacks data is ±5% less accurate on average than the UA signals report X+1 data.
- Real-time IAA postbacks data is ±7% less complete on average than the UA signals report X+1 data.

### What are the IAA postback data sources?

The data for the IAA postback originates from Impression-level data that partners load onto client devices. This data is then shared with AppsFlyer through the ROI360 Ad Revenue SDK, which is installed on the device by the advertiser. The SDK API allows the app developer to report an impression event including certain parameters like the ILRD, the currency, the mediation platform, and the monetization source.

Data transfer from the advertiser client devices to AppsFlyer is subject to advertiser permissions and whether an advertiser is a ROI360 advanced customer.

### What processing is performed on the IAA postback data?

AppsFlyer ROI360 performs the following steps for each impression-level data received:

1. Data normalization.
2. Attribution to the install media source and data enrichment.
3. Generation of an **af\_ad\_revenue** event.

### How is the postback data delivered?

The event is sent to the partner through an existing postback configuration between the partner and AppsFlyer as an additional parameter.

## In-app purchase (IAP) postbacks

ROI360 in-app purchase postbacks deliver multiple layers of reporting accuracy by first validating each transaction, deduplicating it, and then deducting store commission and sales tax.

### What are the IAP postback data sources?

The data for the IAP postback originates from:

1. Transaction-level data read by the ROI360 Purchase SDK whenever an in-app purchase or auto-renewable subscription event occurs on the device.
2. Any incoming **App Store and Google Play (RTDN) server notifications** are also processed by the AppsFlyer purchase and subscription revenue business logic:

   - Notifications regarding transactions previously reported via the SDK are validated and processed.
   - Notifications regarding unknown transactions are not reported into AppsFlyer

> 📘 Note
>
> The transfer of data from the advertiser to AppsFlyer is contingent upon advertiser permissions and whether the advertiser is a ROI360 advanced customer.

### What data processing is performed on the IAP postback data?

AppsFlyer ROI360 performs the following steps for each transaction-level data received:

1. AppsFlyer **validates the purchase or subscription with the relevant store** to ensure it's not fraudulent.
   - Upon successful validation, AppsFlyer logs the purchase or subscription.
   - If receipt validation fails, the event displays in the blocked in-app events raw data report (available to Protect360 subscribers).
2. AppsFlyer ensures that transactions are not duplicated, including those related to family sharing on iOS.
3. AppsFlyer calculates net revenue data taking into account store commission and taxes ( **True Revenue**).
4. AppsFlyer generates an internal purchase or lifecycle event for the validated and processed transaction.

### How is the postback delivered?

The IAP event is sent to the partner through an existing postbacks integration between the partner and AppsFlyer.

### What are the IAP events?

ROI360 customers may share the following revenue-bearing event names:

| **Event name** | **Description** |
| --- | --- |
| af\_purchase | Recorded when a user makes a purchase |
| af\_purchase\_refund | Recorded when a purchase is refunded |
| af\_ars\_trial\_converted | Recorded when a fully priced renewal starts, following a trial period |
| af\_ars\_subscription\_started | Recorded when a discounted or a fully priced subscription starts |
| af\_ars\_subscription\_resumed | Recorded when a fully priced subscription is resumed following a churned or refunded subscription |
| af\_ars\_subscription\_refunded | Recorded when a subscriber is issued a refund |
| af\_ars\_subscription\_renewed | Recorded when an auto-renewal subscription takes place |
| af\_ars\_subscription\_xgraded | Recorded when a subscriber upgrades, downgrades, or cross-grades to a different product |
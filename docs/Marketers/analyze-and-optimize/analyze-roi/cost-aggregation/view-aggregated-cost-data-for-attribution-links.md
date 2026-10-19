---
title: View aggregated cost data for attribution links
excerpt: >-
  Viewing aggregated cost data for each ad click as reported by ad networks on
  the attribution link.
metadata:
  keywords:
    - eCPI
    - clicks
    - ROI
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2020-05-20T10:50:58Z'
  edited_at: '2025-04-05T11:07:35Z'
  id: 360008981698
  locale: en-us
  section: Cost aggregation
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360008981698-View-aggregated-cost-data-for-attribution-links
---
## Basic cost reporting

Cost data is reported to AppsFlyer by:

* Ad networks: each time a user clicks on an ad. Viewing campaign cost in AppsFlyer helps advertisers measure ROI and make appropriate budgetary decisions.
  * Cost is reported on the [attribution link](/docs/about-link-structure-and-parameters) using the cost-per-install (CPI) model.
  * When sending the attribution link to the ad network, ensure the ad network [adds the cost reporting parameters](/appsflyer-partners/docs/cost-reporting-on-the-attribution-link-for-ad-networks).
* [Advanced options for cost aggregation](/docs/roi360-cost-aggregation-overview), including by API and Cost Import (CSV file upload).

  * Cost aggregation methods support cost models used by the partner in addition to CPI, including, CPA, CPC, and CPM.

<div id="viewing-ad-cost-by-click" />

<Accordion title="Viewing ad cost reported on the attribution link">

Cost data reported on attribution links is aggregated and available for viewing in real-time (maximum up to 2 hours after the link is clicked) in the AppsFlyer dashboards, performance reports, and raw data reports.

In the ***Overview dashboard,**Aggregated Performance Report* contains cost, clicks, impressions, ROI, and average eCPI data.

[![CostReporting.jpg](https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg)](https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg)

The performance and raw data reports are also available for [download](/docs/raw-data-reporting-overview).

</Accordion>

<div id="ad-networks-providing-cost-by-click-data" />

<Accordion title="Ad networks providing cost data on the attribution link">

For ad networks that report cost on the attribution link, the dimensions supported are those contained on the link.

**Ad networks that report cost on the attribution link include:**

* AdAction
* Aura from Unity
* Blind Ferret
* Chartboost
* Cross Install
* Digital Turbine
* Fyber
* HangMyAds
* ironSource
* Criteo DSP (Manage)
* Mintegral
* TikTok for Business
* Vungle
* [See full list of ad networks that support cost on the attribution link](https://docs.google.com/spreadsheets/d/e/2PACX-1vTMPZ9anfZoFBelK2bsBUoHG9n4YE3WxpXOayDF_wI8vyYClM6_6yXelFCZ3khwhd9Z_5Louxd4VVgx/pub?gid=0&single=true&output=csv)

</Accordion>

<div id="limitations" />

<Accordion title="Limitations">

Cost on the attribution link limitations:

* Cost is only reported using the cost-per-install model (CPI). Other models, including CPA, CPC, and CPM are not supported.
* [Self-reporting networks](/docs/self-reporting-networks-srns) (SRN) do not report cost on the attribution link.
* Cost data on the attribution link data is immutable. Therefore, once it's logged in AppsFlyer, it cannot be changed, even if there are data-reporting errors.

</Accordion>

<div data-zendesk-anchors="h_01HX954Y5X7ZP2VMB5W2XAMCR0=basic-cost-reporting h_01HX954Y5XTRRQV4JHA5XX1AQ0=viewing-ad-cost-by-click h_01HX954Y5XV8M2R2VDAV34641R=ad-networks-providing-cost-by-click-data h_01HX954Y5X84BM7F8TGQRDPBTS=limitations" />

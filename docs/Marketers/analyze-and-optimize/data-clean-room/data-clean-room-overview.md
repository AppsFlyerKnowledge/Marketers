---
title: Data Clean Room—Overview
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-03-08T14:47:36Z'
  edited_at: '2024-09-04T08:33:29Z'
  id: 4626852381713
  locale: en-us
  section: Data Clean Room
  section_id: 4591191779217
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4626852381713-Data-Clean-Room-Overview
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**![privacy_cloud_logo.png](https://files.readme.io/5862beb63a4b22f68fc230f89c3faa260a15ab40e1defa70c59604d5a81e759d-5583061038225.png)**

**At a glance:** Enrich your user-level data by matching it with AppsFlyer user-level attribution data to create aggregated reports and obtain insights that leverage the value of the combined data.

## Introduction

Throughout its history, the mobile marketing ecosystem has utilized user-level data to obtain insights and optimize advertising campaigns:

1. Media sources provided user-level data to attribution measurement providers (such as AppsFlyer), who used it to provide attribution, then passed it along to advertisers.
2. Advertisers matched this user-level data to their own user-level data (from BI or CRM systems, for example), then analyzed and grouped it as necessary to obtain the aggregate insights they needed to optimize their campaigns.

With the advent of the user-privacy era, access to user-level data from media sources has been significantly restricted:

1. Media sources provide user-level data to attribution measurement providers (such as AppsFlyer), who use it to provide attribution; **however, they are now blocked from passing this user-level data to advertisers.**
2. This leaves advertisers unable to match user-level attribution data to their own user-level data as they could in the past – making it impossible for them to obtain the insights they need.

This is precisely the "data blind spot" that the AppsFlyer Data Clean Room (DCR) steps in to correct.

### How does it work?

Instead of passing user-level attribution data to the advertiser so that the ***advertiser*** can match it with its user-level data, the ***DCR takes on the job of matching*** user-level attribution data with the advertiser's user-level data – essentially shifting this responsibility to AppsFlyer. Then the DCR analyzes and groups this data, then passes it along to the advertiser in aggregated form – allowing the advertiser to obtain the aggregate insights they need **while maintaining user privacy.**

### How does the DCR obtain data?

The DCR currently uses 2 different types of data:

* **Custom data source:** user-level data uploaded to cloud storage for use by the DCR. This data originates from the advertiser's internal systems (such as BI or CRM systems).
* **Attribution data:** User-level data provided by the media sources to AppsFlyer for attribution

### What does the DCR do with the data?

The DCR works according to standard database principles. In other words, it matches data from different tables (or **"sources"**) into a single data set. This single data set is then used to create **reports** that use the combined data:

* In order to match the data from different data sources and combine them into a single set, each source must share at least one field that identifies a unique app user **("identifier")** in common with another source.
* By using identifiers to match your user-level data with user-level attribution data, the DCR creates a combined user-level data set.
* Then, in order to provide insights while maintaining user privacy, DCR processes this data to create **aggregated reports,** grouped according to characteristics **("dimensions")** that you define.

## DCR terminology

The following are some frequently used DCR terms:

* **Connector:** Your (advertiser-owned) AWS or GCS bucket in which DCR data is stored. A connector can include folders for your data source flowing into the DCR and/or destinations for reports flowing out. You can use a single connector or multiple connectors for data flowing in and out of the DCR.
* **Sources:**
  * **Advertiser data source:** Your first-party data file that comes into the DCR (intended for matching and enrichment with AppsFlyer attribution data). New versions of source files can be uploaded for processing as often as every 6 hours. When you set up a source in the AppsFlyer DCR platform, you define its **structure** and **location:**
    * **Source structure:** A list of data fields in the source and the category you assign to each for how it will be used in reports (identifier, dimension, or metric).
    * **Source location:** The cloud service folder from which AppsFlyer obtains the source file each time you update it. This folder lives inside a bucket ("connector").
  * **Attribution data:** User-level attribution data from your AppsFlyer account (used for matching and enrichment of advertiser data in the DCR)
* **Report:** A data file coming out of the DCR after processing. Reports are created each time new versions of the related source files are uploaded. When you set up a report in the AppsFlyer DCR platform, you define its **structure** and **destination:**
  * **Report structure:** Specification of advertiser data sources and attribution data to be used in creating the report, the identifiers by which they will be joined, the metrics to be included, and the dimensions by which the report will be grouped.
  * **Report destination:** The cloud service folder to which AppsFlyer sends the report each time it is processed. This folder lives inside a bucket ("connector").

## Working with the DCR (setup workflow)

The AppsFlyer Data Clean Room (DCR) is very flexible in terms of the types of data you choose to upload, the reports you receive, and the timing and frequency of processing. For this reason, it involves a relatively significant planning and setup process – likely involving the collaboration of several people within your organization.

Follow these steps to set up the DCR to meet your organization's needs:

1. Consider the reports you want to receive from the DCR. These reports are the result of enriching your advertiser data sources with AppsFlyer attribution data. Determine the first-party data sources you need to upload into the DCR in order to create these reports.
2. <Anchor target="_blank" href="/marketers/docs/data-clean-room-setting-up-cloud-services">Create the basic cloud storage structure</Anchor> to support those data sources and reports.
3. Define the queries that will pull the data and produce the data source files; produce prototypes of the data source files.
4. Develop the automations that will pull the data, create the source subfolders, and upload the data sources and <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-sources#_success-files">\_SUCCESS files</Anchor> on a regular basis.
5. Set up your <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-sources">sources</Anchor> in the AppsFlyer DCR platform.
6. Set up your <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-reports">reports</Anchor> in the AppsFlyer DCR platform.
7. Develop the automations that will ingest the reports after they are delivered by the DCR to your cloud storage.

<div data-zendesk-anchors="h_01HE7SDH5PWCW6YG00GC12W4BS=introduction h_01HE7SDH5PW64CHNJVJJ30V5ZY=how-does-it-work h_01HE7SDH5P82HCEN52ZBPMQV16=how-does-the-dcr-obtain-data h_01HE7SDH5PWDQ61389TT7V83F8=what-does-the-dcr-do-with-the-data h_01HE7SDH5P3QSG874XASXNH1YS=dcr-terminology h_01HE7SDH5P0S9542P2CB22KKVT=working-with-the-dcr-setup-workflow" />

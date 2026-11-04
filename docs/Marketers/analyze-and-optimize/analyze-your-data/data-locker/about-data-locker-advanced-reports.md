---
title: About Data Locker Advanced Reports
metadata:
  keywords:
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2026-04-04T10:49:27Z'
  edited_at: '2026-09-03T15:20:32Z'
  id: 45424430660497
  locale: en-us
  section: Data Locker
  section_id: 6550945728657
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/45424430660497-About-Data-Locker-Advanced-Reports
---
> **At a glance:** Advanced Reports deliver consolidated, typed, and consistently named event-level data across mobile, web, and connected TV (CTV) platforms in a single report, so you can spend less time preparing data and more time using it.

<Embed title="About Data Locker Advanced Reports" typeOfEmbed="youtube" url="https://www.youtube.com/embed/0Myz1hxZJH0" providerUrl="https://www.youtube.com" />

<div id="about-advanced-reports" />

## About Advanced Reports

The sections below cover how Advanced Reports consolidate data by product, arrive ready to use with no extra preparation, and let you control exactly what each report returns.

<div id="consolidated-data-by-data-product" />

### Consolidated data by data product

Advanced Reports organize event-level raw data around data products.

* Each report covers one full data product, so there are no fragmented files to stitch together.
* Data from mobile, web, and CTV lives in a single file with a shared schema.

<div id="data-that-is-ready-to-use" />

### Data that is ready to use

Legacy reports returned all fields as plain strings with inconsistent naming, requiring teams to cast types, rename fields, and reconcile schemas before analysis could proceed. Advanced Reports ship with the foundational preparation already done:

* **Typed fields:** integers, booleans, timestamps, and enums, instead of plain strings.
* **Unified schema:** consistent, validated structure across all data products.
* **Self-explanatory field names:** consistently named and self-explanatory across all reports, making data easier to work with directly in BI (business intelligence) tools, analyst workflows, and AI-powered applications.

<div id="precise-control-over-what-you-receive" />

### Precise control over what you receive

Advanced Reports let you tailor each report to your exact needs without any post-processing:

* **Schema customization:** add or remove fields to match your downstream requirements.
* **Report-level filters:** scope data to a specific platform, conversion type, country, or event.
* **Pre-built templates:** start instantly with field and filter configurations designed for common use cases.

<div id="advanced-reports-vs-legacy-reports" />

## Advanced Reports vs. legacy reports

The table below highlights the key differences between Advanced Reports and legacy reports.

|  | Legacy reports | Advanced Reports |
| --- | --- | --- |
| **Data structure** | Fragmented across multiple reports | Consolidated, one report covers the full data product |
| **Field types** | All fields delivered as plain strings | Typed fields: integers, booleans, timestamps, enums |
| **Field names** | Inconsistent naming across reports; not optimized for readability | **Self-explanatory**, consistent names across all reports |
| **Schema** | Inconsistent; varied structure across reports | Unified, validated schema across all data products |
| **Platform coverage** | Separate reports per platform with different schemas | Mobile, web, and CTV consolidated in a single report with a shared schema |
| **Filters** | Basic filter selection | Report-level multi-select filters per several dimensions, plus pre-built templates for common use cases |
| **AI and BI readiness** | Required type casting, schema alignment, field normalization, field renaming | Typed, validated, and consistently named, with **Self-explanatory** field names that are easy to interpret by both humans and AI-powered applications |

<div id="available-reports" />

## Available reports

Each report corresponds to a data product, a curated, structured dataset representing a specific domain of your marketing data, such as conversions, engagements, or user events. The following reports are available today.

<Accordion title="Engagements">

The Engagements report consolidates mobile click and impression data across user acquisition and retargeting activities. It gives you a unified view of user interactions with your ads, supporting in-depth analysis of top-of-funnel performance, creative and channel evaluation, and cost and reach optimization at the engagement level.

* **Platforms:** Mobile
* **Data freshness:** 1–3 hours
* **Report Fields:** [Download the report sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vQcBDMTizVe22HrquKhPhPyprLa8k9_GptkfMNOl7-ai2dtiBp_D8gXTcgdUHlZpndAZjUqEzY-eqeR/pub?output=csv)

</Accordion>

<Accordion title="Conversions">

The Conversions report provides a complete view of all app installations, including organic and non-organic sources across mobile, web, and CTV. By centralizing conversion data, you can perform comprehensive growth analysis using a single, streamlined dataset and precisely measure and optimize marketing performance.

* **Platforms:** Mobile, Web, CTV
* **Data freshness:** 1–3 hours
* **Report Fields:** [Download the report sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmF8gMIBuWzS3aw7M8TSzuxS3MYNC0m1RZzPAND-1jP3MjDcRUZmvggoaZRDAKb5uI1R77sufCLQeU/pub?output=csv)

</Accordion>

<Accordion title="End-user events">

The End-user events report captures detailed in-app event data, including sessions, purchases, registrations, and level completions, across mobile, web, and CTV platforms. Each event is enriched with full attribution context, enabling you to analyze user behavior, retention, and lifetime value with complete attribution traceability.

* **Platforms:** Mobile, Web, CTV
* **Data freshness:** 1–3 hours
* **Report Fields:** [Download the report sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vRm4xYgov7i-xClroQR0eS5vtQvtOavmo-V9zWiGmZMOIyBmIl0swmfj34tYgVinIC7uZp0dyPXD8wI/pub?output=csv)

</Accordion>

<Accordion title="End user events cross-platform">

The End user events cross-platform report extends the end-user events report to support cross-platform use cases. See the <Anchor target="_blank" href="/marketers/docs/end-user-events-cross-platform-report-in-data-locker">End-user events cross-platform report</Anchor> for more information.

* **Platforms:** Mobile, Web, CTV

</Accordion>

<Accordion title="Conversions cross-platform">

The cross-platform conversions-with-assists report shows the complete user journey behind each cross-platform conversion, including the full assisting engagement chain, not just the last touchpoint. See the <Anchor target="_blank" href="/marketers/docs/conversions-cross-paltform-report">Conversions cross-platform report</Anchor> for more information.

* **Data freshness:** 4 hours
* **Report Fields:** [Download the report sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vRTFg6HXtHNYwegAjMysjybPbRk4IO8uflwvbGvR_xb11BcCrCWQ7i3xZD_Y2iiYSsx_MjTPN0E_Bmk/pub?gid=670907846&single=true&output=csv)

</Accordion>

<div id="report-templates" />

## Report templates

Templates are pre-configured report presets designed for common use cases. Each template is associated with a specific data product and comes pre-loaded with the fields and filters most relevant to that report's common use cases. Selecting a template automatically loads the correct fields and filters. You can edit the pre-filled report name before saving.

Once saved, a template-based report is fully independent. Changes to the template do not affect reports that have already been saved from it.

The following pre-defined templates are available:

| Template name | Report | Description |
| --- | --- | --- |
| **Web Conversions** | Conversions | Attribution anchors for web, including first visits, revisits, and user-acquisition events. All downstream user events inherit campaign details from these conversions. |
| **Web Events** | End-user events | All web events and sessions. Use this as your primary report for visit-level and event-level analysis. |

<div id="report-level-filters" />

## Report-level filters

Report-level filters let you scope a report to a specific subset of data, for example, a particular platform, conversion type, or country.

The set of available filters depends on the data product. The table below shows which filters are supported for each report. Additional filters will follow over time.

| Report | Available filters |
| --- | --- |
| **Conversions** | Conversion type, Country, Platform group, Platform, Media source, and App |
| **Engagements** | Campaign type, Engagement type, Country, Media source, and App |
| **End-user events** | Event name, Platform group, Conversion type, Country, Is primary attribution, Media source, and App |
| **Cross-platform end-user events** | Event name, Platform group, Conversion type, Country, Is primary attribution, Media source, and App |

<div data-zendesk-anchors="h_01KNC1RP0RM102X8A8XQK7GKAZ=about-advanced-reports h_01KNC1RP0RK5CGNQ9ZT7PB3EA5=consolidated-data-by-data-product data-thats-ready-to-use=data-that-is-ready-to-use h_01KNC1RP0RZC1Z2EAZGW701789=data-that-is-ready-to-use h_01KNC1RP0RQYQJXYQTQ2GBR26F=precise-control-over-what-you-receive h_01KNC1RP0RNJV2FY8EH6T609FP=advanced-reports-vs-legacy-reports report-types=available-reports h_01KNC1RP0RVMSSTVM8ZADT72RB=available-reports h_01KNC1RP0R4Y6YFCNWGWZK4ETF=report-templates h_01KNC1RP0RRC4498475BQXWT03=report-level-filters" />

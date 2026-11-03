---
title: Recreating classic reports in advanced reports
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
  created_at: '2026-06-15T08:16:54Z'
  edited_at: '2026-06-23T11:05:18Z'
  id: 47741416390161
  locale: en-us
  section: Data Locker
  section_id: 6550945728657
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/47741416390161-Recreating-classic-reports-in-advanced-reports
---
> **At a glance:** If you're migrating from classic Data Locker raw reports, use this guide to find the exact filter selections that reproduce each classic report in <Anchor target="_blank" href="/marketers/id/docs/about-data-locker-advanced-reports">Advanced Reports</Anchor>.

## Overview

Classic Data Locker delivered the user journey as many separate report topics. Advanced Reports consolidates all of that into one report per data product, which you scope down using report-level filters.

The three Advanced Reports and the classic topics they replace are:

* The **Engagements** **advanced report** replaces the classic clicks and impressions topics.
* The **Conversions** **advanced report** replaces the classic installs, retargeting conversions, and CTV installs topics.
* The **End-user events** **advanced report** replaces the classic in-app events, sessions, CTV in-app events, CTV sessions, and uninstalls topics.

To recreate a specific classic report, apply the report-level filters described in the sections below. For the full list of available filters per report, see <Anchor target="_blank" href="/marketers/id/docs/about-data-locker-advanced-reports#report-level-filters">Report-level filters</Anchor>.

## Recreate classic reports in the Engagements advanced report

In the Engagements Advanced Report, set the **Campaign type** filter to match the classic report's category (for example, User acquisition or Retargeting), and the **Engagement type** filter to match its event type (for example, Clicks or Impressions).

| Classic report | Campaign type filter | Engagement type filter |
| --- | --- | --- |
| User acquisition – Clicks | User acquisition | `Click` + `Engaged click` |
| User acquisition – Impressions | User acquisition | `View` + `Engaged view` |
| Retargeting – Clicks | Retargeting | `Click` + `Engaged click` |
| Retargeting – Impressions | Retargeting | `View` + `Engaged view` |

## Recreate classic reports in the Conversions advanced report

In the Conversions Advanced Report, set the **Conversion type** filter to match the classic report's category (for example, User acquisition or Retargeting), and the **Platform group** filter to match its platform (for example, Mobile or CTV).

| Classic report | Conversion type filter | Platform group filter | Comments |
| --- | --- | --- | --- |
| User acquisition – Installs | User acquisition | Mobile | <ul><li>The `conversion_name` field value is `INSTALL`.</li><li>Covers organic and non-organic installs.</li></ul> |
| Retargeting – Conversions | Retargeting | Mobile | <ul><li>The `conversion_name` field value is `RE-ENGAGEMENT` or `RE-ATTRIBUTION`.</li><li>Covers non-organic only.</li></ul> |
| CTV – Installs | User acquisition | CTV | <ul><li>The `conversion_name` field value is `INSTALL`.</li><li>Covers organic and non-organic installs.</li></ul> |

## Recreate classic reports in the End-user events advanced report

In the End-user events Advanced Report, set the **Conversion type** filter to match the classic report's category (for example, User acquisition or Retargeting), and the **Platform group** filter to match its platform (for example, Mobile or CTV).

| Classic report | End user event type filter | Conversion type filter | Platform group filter | Comments |
| --- | --- | --- | --- | --- |
| User acquisition – In-app events | `In-app` | User acquisition | Mobile | <ul><li>Covers organic and non-organic in-app events.</li></ul> |
| Retargeting – In-app events | `In-app` | Retargeting | Mobile | <ul><li>Covers non-organic only.</li><li>Set **Is primary attribution** to `True` to deduplicate retargeting events published more than once.</li></ul> |
| User acquisition – Sessions | `Session` | User acquisition | Mobile | <ul><li>Covers organic and non-organic sessions.</li></ul> |
| Retargeting – Sessions | `Session` | Retargeting | Mobile | <ul><li>Covers non-organic only.</li></ul> |
| CTV – In-app events | `In-app` | any value | CTV |  |
| CTV – Sessions | `Session` | any value | CTV |  |

## Traits and limitations

| Trait | Description |
| --- | --- |
| Reports not reproducible | Cross-platform engagements, reinstalls, and organic reinstalls are not reproducible using Advanced Reports. |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/id/docs/about-data-locker-advanced-reports">About Data Locker Advanced Reports</Anchor>

<div data-zendesk-anchors="about-recreating-classic-reports=overview h_01KV55PGFSSE3GWZ9ZW0TXSVNB=overview reproduce-classic-reports-in-the-engagements-advanced-report=recreate-classic-reports-in-the-engagements-advanced-report h_01KV55PGFSBHV59ZA7KFVQVM1S=recreate-classic-reports-in-the-engagements-advanced-report reproduce-classic-reports-in-the-conversions-advanced-report=recreate-classic-reports-in-the-conversions-advanced-report h_01KV55PGFSK35M9XC7EHVDX53X=recreate-classic-reports-in-the-conversions-advanced-report reproduce-classic-reports-in-the-end-user-events-advanced-report=recreate-classic-reports-in-the-end-user-events-advanced-report h_01KV55PGFSCD4AQQWRBY0MHJGK=recreate-classic-reports-in-the-end-user-events-advanced-report h_01KV55PGFSF8QVSBAWA3XN7A8W=traits-and-limitations h_01KV8SEHV9KVY6R5HQA6K2M2JZ=see-also" />

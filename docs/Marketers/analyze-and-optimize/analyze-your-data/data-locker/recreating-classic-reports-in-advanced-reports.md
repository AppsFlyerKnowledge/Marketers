---
title: "Recreating classic reports in advanced reports"
excerpt: "Learn how to migrate from classic Data Locker raw reports to Advanced Reports by applying the exact filter selections that reproduce each classic report."
---
> 📘 At a glance
>
> If you're migrating from classic Data Locker raw reports, use this guide to find the exact filter selections that reproduce each classic report in [Advanced Reports](/docs/about-data-locker-advanced-reports).

## Overview

Classic Data Locker delivered the user journey as many separate report topics. Advanced Reports consolidates all of that into one report per data product, which you scope down using report-level filters.

The three Advanced Reports and the classic topics they replace are:

- The **Engagements** **advanced report** replaces the classic clicks and impressions topics.
- The **Conversions** **advanced report** replaces the classic installs, retargeting conversions, and CTV installs topics.
- The **End-user events** **advanced report** replaces the classic in-app events, sessions, CTV in-app events, CTV sessions, and uninstalls topics.

To recreate a specific classic report, apply the report-level filters described in the sections below. For the full list of available filters per report, see [Report-level filters](/docs/about-data-locker-advanced-reports#report-level-filters).

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
| User acquisition – Installs | User acquisition | Mobile | - The `conversion_name` field value is `INSTALL`. <br /> - Covers organic and non-organic installs. |
| Retargeting – Conversions | Retargeting | Mobile | - The `conversion_name` field value is `RE-ENGAGEMENT` or `RE-ATTRIBUTION`. <br /> - Covers non-organic only. |
| CTV – Installs | User acquisition | CTV | - The `conversion_name` field value is `INSTALL`. <br /> - Covers organic and non-organic installs. |

## Recreate classic reports in the End-user events advanced report

In the End-user events Advanced Report, set the **Conversion type** filter to match the classic report's category (for example, User acquisition or Retargeting), and the **Platform group** filter to match its platform (for example, Mobile or CTV).

| Classic report | End user event type filter | Conversion type filter | Platform group filter | Comments |
| --- | --- | --- | --- | --- |
| User acquisition – In-app events | `In-app` | User acquisition | Mobile | - Covers organic and non-organic in-app events. |
| Retargeting – In-app events | `In-app` | Retargeting | Mobile | - Covers non-organic only. <br /> - Set **Is primary attribution** to `True` to deduplicate retargeting events published more than once. |
| User acquisition – Sessions | `Session` | User acquisition | Mobile | - Covers organic and non-organic sessions. |
| Retargeting – Sessions | `Session` | Retargeting | Mobile | - Covers non-organic only. |
| CTV – In-app events | `In-app` | any value | CTV |  |
| CTV – Sessions | `Session` | any value | CTV |  |

## Traits and limitations

| Trait | Description |
| --- | --- |
| Reports not reproducible | Cross-platform engagements, reinstalls, and organic reinstalls are not reproducible using Advanced Reports. |

<Cards>
  <Card title="About Data Locker Advanced Reports" href="/docs/about-data-locker-advanced-reports" icon="fa-solid fa-box-archive">
    Learn more about the features and capabilities of Advanced Reports in Data Locker.
  </Card>
</Cards>
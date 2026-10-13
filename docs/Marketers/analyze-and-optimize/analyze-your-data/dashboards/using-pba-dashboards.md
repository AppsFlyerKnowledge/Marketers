---
title: "Using PBA dashboards"
excerpt: "Get the most out of our PBA dashboard features."
x-zendesk:
  id: 360007630318
  url: https://support.appsflyer.com/hc/en-us/articles/360007630318-Using-PBA-dashboards
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Dashboards
  section_id: 6550925337873
  position: 15
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, Cross-Platform Measurement]
  labels: [pba, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2020-04-21T04:53:54Z'
  edited_at: '2024-02-01T14:21:50Z'
---
![AppsFlyer-People-Based-Attribution_us-en.png](https://files.readme.io/d2178dfedb2f67420e66626adbd72dd96ba9edc39fcb0be08648b01656fd2d4b-360010094118.png)

## PBA dashboards

The following sections relate to the [Website Attribution](/docs/pba-website-attribution-dashboard) and [Web-Assisted Installs](/docs/pba-web-assisted-installs) dashboards.

## Settings

### Filtering options

Refine PBA dashboard results by using the (A) date picker, (B) main filters, and (C) additional filters to fit the analysis to your needs.

#### Filter panel in PBA dashboards

![PBAHeader_us-en.png](https://files.readme.io/aaa4040b69082c8507c604b530086404080d542b614fd20fcb0d5302221d7586-360019762657.png)

**Key**:

(1) Date picker

(2) Default filters

(3) Additional filters: Click **+** to select an additional filter.

**Principles**

- The filter panel design is common to all PBA dashboards.
- The filters available per dashboard differ as indicated in the table that follows.
- Filters with context: Some filters, as indicated in the table, require that they be associated with a context. For example, in the Web-Assisted Installs dashboard, the geo filter requires a context of either the web media source or the mobile media source. You can set a geo filter for each by setting two geo filters; one for each context.

#### Available filter dimensions per dashboard

| Filter | Description/values | Website Attribution | Web-Assisted Installs | Conversion<br />Paths |
| --- | --- | --- | --- | --- |
| Date picker | The date one of the following PBA conversion events occurred: <br />- App install<br />- Web conversion<br />- Mobile conversion | Y | Y | Y |
| Geo | List of countries/territories | Y | Y (1) | Y (2) |
| Install type | Organic, smart banner, custom link, paid | -- | Y | -- |
| Media channel | Ad, direct, email, referral, organic search, social | Y | Y | Y (2) |
| Mobile platform | Android, iOS | -- | Y | -- |
| Media source | Media source to which the event is attributed | Y | Y(1) | Y (2) |
| Media type | Includes paid, [owned](/docs/owned-media-attribution), earned | Y | Y | Y (2) |
| Conversion events | Show paths that lead to the conversion event for the conversion path | Y | -- | Y |
| Path length (steps) | Number of steps in the current conversion path view: Media source, media channel, media type | -- | -- | Y |
| Path duration (days) | Duration of the conversion starting with the first touchpoint | -- | -- | Y |
| **(1)** In the web-assisted installs dashboard, you associate the filter with the web media source or the mobile media source. You can set multiple instances of the filter. Example case |

### Grouping options

Group by options are available on the **Web-Assisted Installs** and **Website Attribution** dashboards.

Dashboard data is grouped by, for example, media source, device, or country. When a group is selected, a data column is added to the results table. The order in which groups are chosen affects how the data is shown.

- Default group: **Media source/Campaign**
- In the drop-down, select 1 or more of the options.

#### Example

**Scenario:** The same targeting campaign is run in both Net\_A and Net\_B.

**Goal:** Look at which media source is more successful.

**How?** Group by _media source_, then look at a campaign that is directed towards the same target audience _._

| Group | Description | Web-Assisted Installs | Website Attribution |
| --- | --- | --- | --- |
| Device type | Includes smartphone, tablet, desktop, TV, and other (unrecognized devices) | Y | Y |
| Environment | - Use to differentiate between web and mobile KPIs<br />- Website Attribution dashboard: Combines operating system and platform. For example, Android/Web, iOS/Web, Windows/Web, Linux/Web <br />- Web-Assisted Installs: iOS, Android, Windows | Y | N |
| Geo | - View traffic and engagement trends by country<br />- Results can directly impact investment decisions per country | Y | Y |
| Media source/campaign | **Media source**<br />Media source attributed to a conversion<br />- To view in-depth campaign data click down through the campaign hierarchy: campaign > ad set > ad<br />- Available hierarchy levels differ between the various media sources<br />**Campaign names**<br />- Available campaign names based on URL parameters.<br />- Campaign names aren't available in all cases. | Y | Y |
| Media channel | Ad, direct, email, referral, organic search, social | N | Y |
| Media type | Includes paid, [owned](/docs/owned-media-attribution), earned | N | Y |
| Platform |  | N | Y |

### Other settings

| Setting | Description |
| --- | --- |
| Brand bundle | PBA dashboards have brand-bundle level data. Bundles consist of a website, 1 Android app, and 1 iOS app.<br />- You can select bundles if your [permissions](/docs/pba-brand-bundles-and-settings#faq) let you view/edit the apps that form the bundle.<br />- Use the selector to switch between bundles.<br />- [Create and edit bundles.](/docs/pba-brand-bundles-and-settings) |
| PBA settings | - Set conversion events<br />- Change bundle settings |

## Additional information

### Traits and limitations

> 📘 Data Freshness
>
> PBA dashboards and reports are updated [daily](/docs/about-data-freshness-and-timezone-support#eod) per the UTC time zone.

- Daily processing includes events received during the previous day.
- Data finalization:
  - In the case of Web-Assisted Installs, Website Attribution PBA identifies additional related events during the first 7 days after the conversion. This can change the media source identified as being ultimately responsible for driving the conversion.
  - In the related raw-data reports, the _final\_data_ field is false during the initial 7-day period.

PBA dashboards don't support local currency and data will be shown in USD.
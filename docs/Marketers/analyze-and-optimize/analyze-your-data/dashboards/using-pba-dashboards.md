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

<div id="filtering-options" />

<Accordion title="Filtering options">

Refine PBA dashboard results by using the (A) date picker, (B) main filters, and (C) additional filters to fit the analysis to your needs.

#### Filter panel in PBA dashboards

[![PBAHeader_us-en.png](https://files.readme.io/aaa4040b69082c8507c604b530086404080d542b614fd20fcb0d5302221d7586-360019762657.png)](https://files.readme.io/aaa4040b69082c8507c604b530086404080d542b614fd20fcb0d5302221d7586-360019762657.png)

**Key**:

(1) Date picker

(2) Default filters

(3) Additional filters: Click **+** to select an additional filter.

**Principles**

* The filter panel design is common to all PBA dashboards.
* The filters available per dashboard differ as indicated in the table that follows.
* Filters with context: Some filters, as indicated in the table, require that they be associated with a context. For example, in the Web-Assisted Installs dashboard, the geo filter requires a context of either the web media source or the mobile media source. You can set a geo filter for each by setting two geo filters; one for each context.

#### Available filter dimensions per dashboard

<table><tbody><tr><th>Filter</th><th>Description/values</th><th>Website Attribution </th><th>Web-Assisted Installs</th><th>Conversion<br/>Paths</th></tr><tr><td>Date picker</td><td><p>The date one of the following PBA conversion events occurred: </p><ul><li>App install</li><li>Web conversion</li><li>Mobile conversion</li></ul></td><td><p>Y</p></td><td><p>Y</p></td><td><p>Y</p></td></tr><tr><td>Geo </td><td><p>List of countries/territories </p></td><td>Y</td><td><span>Y (1)</span></td><td><p><span>Y (2)</span></p></td></tr><tr><td>Install type</td><td>Organic, smart banner, custom link, paid</td><td>--</td><td><span>Y</span></td><td><span>--</span></td></tr><tr><td>Media channel</td><td>Ad, direct, email, referral, organic search, social</td><td>Y</td><td><span>Y</span></td><td><span>Y (2)</span></td></tr><tr><td>Mobile platform</td><td>Android, iOS</td><td>--</td><td><span>Y</span></td><td><span>--</span></td></tr><tr><td>Media source </td><td><p>Media source to which the event is attributed<span></span></p></td><td><p>Y</p></td><td><span>Y(1)</span></td><td><span> <font>Y (2)</font> </span></td></tr><tr><td><p>Media type</p></td><td><p>Includes paid, <a href="./owned-media-attribution">owned</a>, earned</p></td><td><p>Y</p></td><td>Y</td><td>Y (2)</td></tr><tr><td><p>Conversion events</p></td><td><p>Show paths that lead to the conversion event for the conversion path</p></td><td><p>Y</p></td><td><p>--</p></td><td><p><span>Y</span></p></td></tr><tr><td><p>Path length (steps) </p></td><td><p>Number of steps in the current conversion path view: Media source, media channel, media type</p></td><td><p>--</p></td><td><p>--</p></td><td><p>Y</p></td></tr><tr><td><p>Path duration (days)</p></td><td>Duration of the conversion starting with the first touchpoint</td><td>--</td><td>--</td><td>Y</td></tr><tr><td colspan="5"><p><strong>(1) </strong>In the web-assisted installs dashboard, you associate the filter with the web media source or the mobile media source. You can set multiple instances of the filter. Example case</p></td></tr></tbody></table>

</Accordion>

<div id="grouping-options" />

<Accordion title="Grouping options">

Group by options are available on the **Web-Assisted Installs** and **Website Attribution** dashboards.

Dashboard data is grouped by, for example, media source, device, or country. When a group is selected, a data column is added to the results table. The order in which groups are chosen affects how the data is shown.

* Default group: **Media source/Campaign**
* In the drop-down, select 1 or more of the options.

> 📘 **Example**
>
> **Scenario:** The same targeting campaign is run in both Net\_A and Net\_B.
>
> **Goal:** Look at which media source is more successful.
>
> **How?** Group by *media source*, then look at a campaign that is directed towards the same target audience*.*

| Group | Description | Web-Assisted Installs | Website Attribution |
| --- | --- | --- | --- |
| Device type | Includes smartphone, tablet, desktop, TV, and other (unrecognized devices) | Y | Y |
| Environment | <ul><li>Use to differentiate between web and mobile KPIs</li><li>Website Attribution dashboard: Combines operating system and platform. For example, Android/Web, iOS/Web, Windows/Web, Linux/Web</li><li>Web-Assisted Installs: iOS, Android, Windows</li></ul> | Y | N |
| Geo | <ul><li>View traffic and engagement trends by country</li><li>Results can directly impact investment decisions per country</li></ul> | Y | Y |
| Media source/campaign | **Media source**<br /><br />Media source attributed to a conversion<ul><li>To view in-depth campaign data click down through the campaign hierarchy: campaign > ad set > ad</li><li>Available hierarchy levels differ between the various media sources</li></ul>**Campaign names**<ul><li>Available campaign names based on URL parameters.</li><li>Campaign names aren't available in all cases.</li></ul> | Y | Y |
| Media channel | Ad, direct, email, referral, organic search, social | N | Y |
| Media type | Includes paid, [owned](/docs/owned-media-attribution), earned | N | Y |
| Platform |  | N | Y |

</Accordion>

<div id="other-settings" />

<Accordion title="Other settings">

| Setting | Description |
| --- | --- |
| Brand bundle | PBA dashboards have brand-bundle level data. Bundles consist of a website, 1 Android app, and 1 iOS app.<ul><li>You can select bundles if your [permissions](/docs/pba-brand-bundles-and-settings#faq) let you view/edit the apps that form the bundle.</li><li>Use the selector to switch between bundles.</li><li>[Create and edit bundles.](/docs/pba-brand-bundles-and-settings)</li></ul> |
| PBA settings | <ul><li>Set conversion events</li><li>Change bundle settings</li></ul> |

</Accordion>

## Additional information

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

PBA dashboards and reports are updated [daily](/docs/about-data-freshness-and-timezone-support#eod) per the UTC time zone.

* Daily processing includes events received during the previous day.
* Data finalization:
  * In the case of Web-Assisted Installs, Website Attribution PBA identifies additional related events during the first 7 days after the conversion. This can change the media source identified as being ultimately responsible for driving the conversion.
  * In the related raw-data reports, the *final\_data*field is false during the initial 7-day period.

PBA dashboards don't support local currency and data will be shown in USD.

</Accordion>

<div data-zendesk-anchors="h_01HNJGN4BYRH14QXS4SWQAHR8D=pba-dashboards h_01HNJGN4BYF8NFYYWHG30RHEJH=settings h_01HNJGN4BYSHM9PFYQQ86ZR84X=filtering-options h_01HNJGN4BYVYY2MKK5G3RCS07W=filter-panel-in-pba-dashboards filters-and-date-picker=available-filter-dimensions-per-dashboard h_01HNJGN4BZ2KZAK120ZGT3B23W=available-filter-dimensions-per-dashboard h_01HNJGN4BZV94W8W2GBXCZF563=grouping-options 01EDDQYQ8RWQZZTEZY9AVT1M64=example 01EDDQYQ8R5JPZE30ETV70FJVN=other-settings h_01HNJGN4BZ9BMV7BQRQCKGYSSP=additional-information h_01HNJGN4BZFMG73SPZ1J4Z7TT5=traits-and-limitations" />

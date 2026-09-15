---
title: "Resolve retargeting double attribution"
excerpt: "Learn how AppsFlyer attributes in-app events and sessions to both user acquisition and retargeting media sources during a re-engagement window."
---
**At a glance:** To evaluate performance during the retargeting campaign's re-engagement window, in-app events and sessions are double-attributed to the user acquisition (UA) and retargeting media sources.

![](https://support.appsflyer.com/hc/article_attachments/9479192551825)

## Overview

Double attribution in retargeting campaigns means that in-app events are attributed to both the media source motivating the original install and the media source motivating the re-engagement or re-attribution event.

The application of double attributions is different between re-engagements and re-attributions:

* **Re-engagements:** Double attribution is applied on all re-engagements.
* **Re-attributions:** Double attribution is applied on apps that are in first-install mode. For apps not in first install mode, double attribution is not applied. (First install mode means that all in-app events generated from reinstalls are attributed to the original install. For more information about the first-install mode, see [Attributed to the first install](/docs/measure-reinstalls#attributed-to-the-first-install)). We recommend contacting AppsFlyer to migrate your existing apps to the first-install mode.

In the preceding figure, the UA event is attributed to the green\_network. One event is generated. In contrast, after the user engages with a retargeting ad served by blue\_network two events are generated. The events credit:

* blue\_network as the primary source motivating the re-engagement.
* green\_network as the secondary source that motivated the original install.

To clarify further, the table that follows contains a scenario of how in-app events are attributed before, during, and after a re-engagement window. The notation in the table refers to the raw data fields used to identify double-attributed events:

* is\_primary\_attribution: If true, the media source is the primary media source
* context: use one of the following fields:
  * [Best practice] **conversion\_type**: install or re-engagement.
  * is\_retargeting: if true, the data relates to the retargeting campaign.

#### Attribution relative to the re-engagement window



| Media source | Before re-engagement | During re-engagement | After re-engagement |
| --- | --- | --- | --- |
| User acquisition | Primary<br /><br />is\_primary\_attribution: True<br /><br />conversion\_type: install<br /><br />(is\_retargeting: False) | Secondary<br /><br />is\_primary\_attribution: False<br /><br />conversion\_type: re-engagement<br /><br />(is\_retargeting: False) | Primary<br /><br />is\_primary\_attribution: True<br /><br />conversion\_type: install<br /><br />(is\_retargeting: False) |
| Retargeting | N/A | Primary<br /><br />is\_primary\_attribution: True<br /><br />conversion\_type: re-engagement<br /><br />(is\_retargeting: True) | N/A |



## Support for dashboard view types

Some dashboards and cohort reports contain multiple view options being unified, user acquisition, and retargeting. These view types employ similar logic to that employed in raw data.

![](https://support.appsflyer.com/hc/article_attachments/9479237101329)

#### Data filtering by view type using the conversion\_type field



<table><thead><tr><th>View type</th><th>conversion_type</th><th>is_primary</th><th>Attribution</th></tr></thead><tbody><tr><td rowspan="2">User acquisition</td><td>install</td><td>True or False</td><td>UA events attributed to the UA media source</td></tr><tr><td>re-engagement</td><td>False</td><td>Retargeting events attributed to the UA media source.</td></tr><tr><td>Retargeting</td><td>re-engagement or re-attribution</td><td>True</td><td>Retargeting events attributed to the retargeting media source</td></tr><tr><td>Unified</td><td>install or re-engagement</td><td>True</td><td>All events attributed to the last touch media source</td></tr></tbody></table>



## How do I identify double-attributed retargeting events in user acquisition in-app reports?

In **UA in-app event reports** events recorded as a result of double attribution are identified as follows:

* The is\_primary\_attribution field identifies primary and secondary media sources; when false, it means that the attribution is the result of a retargeting campaign and the UA media source is secondary.
* The is\_retargeting field is always false.

The corresponding record in retargeting in-app event reports during the re-engagement window is populated as follows:

* The is\_primary\_attribution field is always true.
* The is\_retargeting field is always true.
* To clarify, there is no record whatsoever if the event does not happen during a re-engagement window.
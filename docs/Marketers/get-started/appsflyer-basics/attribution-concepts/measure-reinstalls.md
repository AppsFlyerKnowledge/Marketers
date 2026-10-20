---
title: Measure reinstalls
excerpt: >-
  A reinstall occurs when a user installs an app, uninstalls it, and then
  reinstalls it. Reinstalls result in one of the following attribution types:
  non-organic reinstall, organic reinstall, or re-attribution (retargeting).
  Reinstalls help avoid multiple charges for users that uninstall and install
  again.
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2022-10-27T07:37:21Z'
  edited_at: '2026-05-20T07:33:11Z'
  id: 10164066030737
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/10164066030737-Measure-reinstalls
---
## What is a reinstall

A reinstall occurs when an app user deletes an app and then reinstalls the app during the [re-attribution window.](/docs/set-up-re-attribution-window#re-attribution-window)

The reinstall can come from a retargeting campaign (re-attribution), an organic source, or a non-organic source.

Reinstalls that come from an organic source, or a non-organic source, and are in the [re-attribution window](/docs/set-up-re-attribution-window#re-attribution-window), are referred to as reinstalls.

Reinstalls that come from retargeting campaigns are referred to as re-attributions.

They differ in how the reinstall and in-app events are attributed.

If an install occurs outside of the [re-attribution window](/docs/set-up-re-attribution-window#re-attribution-window), the reinstall is called a [new install](/docs/set-up-re-attribution-window#new-install). A new install is attributed to the media source (or organic if no engagement is recorded) and a new re-attribution window commences.

The table below shows what AppsFlyer would call different reinstalls

| Reinstall source | Is the re-attribution window valid? | Did the user interact with a retargeting campaign before reinstalling? | Did the user interact with a UA campaign before reinstalling? | What is it called |
| --- | --- | --- | --- | --- |
| From a retargeting campaign | Yes | Yes | No | Re-attribution |
| From an organic or non-organic source | Yes | No | Yes or No | Reinstall |
| From an organic or non-organic source | No | No | Yes or No | New install |

## Why are reinstalls important

As well as being a good indication that users are coming back to your app and that your campaigns are working, proper reinstall attribution is important to help avoid multiple charges for users that uninstall and install again within the [re-attribution window.](/docs/set-up-re-attribution-window#re-attribution-window)

Likewise, attributing in-app events from reinstalls to the original media source (first install) provides advertisers with a better picture of how users are engaged. It also shows how effective UA campaigns and Retargeting ads are. For more information see [in-app events](#post-reinstall-in-app-events) below.

## Reinstall flow and outcome

<div id="reinstall" />

<Accordion title="Reinstall">

After the first app install, the user uninstalls, then reinstalls during the [re-attribution window](/docs/set-up-re-attribution-window#re-attribution-window). A reinstall can either come from organic or a UA campaign (see [examples](/docs/measure-reinstalls#examples)).

The following happens:

* The install is NOT attributed - it doesn't appear on the dashboard, nor on the data
* Partners can receive reinstall postbacks only if they support this capability and have been granted explicit permissions by AppsFlyer. Advertisers can choose to send reinstall postbacks to this partner only or to all media sources, including organic, in the partner’s **Active Integration** page as part of the *install* postbacks section.
* See [in-app events](/docs/measure-reinstalls#post-reinstall-in-app-events) for information on how in-app events are attributed

</Accordion>

<div id="reattribution" />

<Accordion title="Re-attribution">

After the first app install, the user uninstalls, then engages with a retargeting campaign and reinstalls during the [re-attribution window](/docs/set-up-re-attribution-window#re-attribution-window).

The following happens:

* The install is attributed to the retargeting media source in the retargeting and unified view of the Overview dashboard
  * The user acquisition view doesn't contain re-attributions
* All following in-app events are attributed to the retargeting media source (see [in-app events](/docs/measure-reinstalls#post-reinstall-in-app-events) for more information)
* An install postback is sent to the retargeting media source

For more Retargeting Attribution information, click [here](/docs/retargeting-attribution-guide).

</Accordion>

## Post reinstall in-app events

In-app events performed by a user after a reinstall are either attributed organic, attributed non-organic, or unattributed organic, depending on the **Post Reinstall Events attribution** state (see flow chart below). An example of an in-app event is a user who reinstalls an app and then makes an in-app purchase.

[![](https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg)](https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg)

<div id="postreinstall-events-attribution-state" />

<Accordion title="Post-reinstall events attribution state">

<table><thead><tr><th>Post Reinstall Events Attribution state</th><th>After a Reinstall</th><th>After a Re-attribution</th></tr></thead><tbody><tr><td><strong>Attributed as organic in-apps</strong></td><td>unattributed organic</td><td>Retargeting</td></tr><tr><td><strong>Attributed to the first install</strong><span>(1)</span></td><td>first install media source</td><td>Retargeting <span>(2)</span></td></tr><tr><td colspan="3"><p><span>(1) See limitations below</span></p><p><span>(2) In the primary source field. The first install media source will be listed in the secondary source field (y<span>ou will only see this in the raw data).</span></span></p></td></tr></tbody></table>

</Accordion>

<div id="unattributed-organic-inapps" />

<Accordion title="Unattributed organic in-apps">

Reinstall

* All in-app events are counted as organic or disregarded completely [depending on the reporting method](/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison).
* In-app events will be reported with the conversion\_type and campaign\_type as "unknown".
* The date used to aggregate data depends on the event:
  * For most SDK-originated in-app events, the date of the app download is used to aggregate data; not the date of the reinstall.
  * For ad revenue events (af\_ad\_revenue) sent by the SDK connector, the date of the reinstall is used to aggregate data.

Re-attribution

* All in-app events are attributed to the retargeting media source

</Accordion>

<div id="attributed-to-the-first-install" />

<Accordion title="Attributed to the first install (first install mode)">

> 📘 **Note**
>
> The first-install mode automatically applies to apps added to AppsFlyer on or after July 31, 2024. For apps added before this date, we recommend contacting AppsFlyer to migrate your existing apps to the first-install mode.

The first install mode provides advertisers with a better picture of user engagement. It shows how effective UA campaigns and Retargeting ads are by attributing in-app events to the original source rather than organic.

* **Reinstall in first install mode:** All in-app events generated from reinstalls are attributed to the original install (1). The install time of the attributed in-app event will be the time of the first install, not the time of the reinstall. For example, if there was an install on March 1st and then a reinstall on March 5th, and if the 'Post Reinstall Events Attribution' option is enabled, any purchase made after the reinstall will be attributed to the install time of March 1st.
* **Re-attribution in first install mode:** All in-app events are attributed to the retargeting ad in the primary source and the original install in the secondary source. (2)

(1) See the [limitations below.](/docs/measure-reinstalls#limitations)

(2) You will only see this in the raw data.

> 📘 **Note**
>
> Organic KPI data in the dashboard may show a lower value with **Post Reinstall Events Attribution** set to **Attributed to the first install** as some of those numbers may now be attributed to a non-organic media source.

#### Examples for first-install mode attribution.

**Example 1**

A user installs the app (day 0), makes a purchase for $10, and then uninstalls the app.

The next day (day 1), the user reinstalls the app and makes a purchase of $5.

![Reinstall_1.jpg](https://files.readme.io/7e8eccb3a6873b42a1d8503c0f027386728adb2eecbe457451d2e37c0a7b6774-10225445609873.jpg)

Since the user already made a purchase before reinstalling, there will not be an additional unique user count.

| Media source | users | Af\_purchase:<br /><br />Unique users<br /><br />Day 0 | Af\_purchase:<br /><br />Unique users<br /><br />Day 1 (cumulative) | Revenue<br /><br />Day 0 | Revenue<br /><br />Day 1 (cumulative) |
| --- | --- | --- | --- | --- | --- |
| Media\_source\_A | 1 | 1 | 1 | $10 | $15 |

We will see an increase in revenue under the same `device_identifier`.

| Appsflyer\_id | Device identifier | Media source | Event name | Event date |
| --- | --- | --- | --- | --- |
| 111 | XXX | media\_source\_A | install | day 0 |
| 111 | XXX | media\_source\_A | af\_purchase | day 0 |
| 222 | XXX | organic | reinstall | day 1 |
| 222 | XXX | media\_source\_A | af\_purchase | day 1 |

**Example 2**

A user installs the app (day 0), makes a purchase, and then uninstalls the app.

The next day (day 1), the user reinstalls the app from a UA campaign and makes a purchase.

| Media source | Event name | Event date | Reinstall attribution | In-app event attribution |
| --- | --- | --- | --- | --- |
| media\_source\_A | install | day 0 | media\_source\_A |  |
| media\_source\_A | af\_purchase | day 0 |  | media\_source\_A |
| media\_source\_B | reinstall | day 1 | media\_source\_B |  |
| media\_source\_B | af\_purchase | day 1 |  | media\_source\_A |

</Accordion>

<div id="confirm-inapps-are-attributed-to-the-original-install" />

<Accordion title="Confirm in-apps are attributed to the original install">

You can verify in your raw data report that your post-reinstall in-app events are in a first-install mode by following these steps:

* Check the `install_time` field on the in-app event. If it reflects the time of the original install (not the reinstall), the event is attributed to the first install.
* Verify the `device_id` (GAID or IDFA). It remains the same across installs and reinstalls, so you can use it to reference the event to the original install.
* Note that the `appsflyer_id` of the in-app event differs from the original install value. AppsFlyer generates a new AppsFlyer ID after each reinstall.

</Accordion>

<div id="limitations" />

<Accordion title="Limitations">

* Only users who have consented to share their device identifier (such as IDFA or GAID) with the app for both the install and reinstall will have their in-app events attributed to the original install
  * Device identifiers in the first install and the reinstall must match
* The reinstall must occur within the [re-attribution window](/docs/retargeting-attribution-guide#reengagement-rules-and-windows) of the last recorded install.
* Each install and reinstall will still have its own unique `appsflyer_id`
* The dashboards do not differentiate between an in-app event following install or re-install
  * It is possible to see this through the raw data
* Reinstalls are not measured by the AppsFlyer Windows SDK.

</Accordion>

## How does the data appear in the AppsFlyer dashboards

<table><thead><tr><th colspan="2"> </th><th>Reinstall non-organic</th><th>Reinstall organic </th><th>Re-attribution</th></tr></thead><tbody><tr><td colspan="2">The Reinstall itself</td><td>Not seen</td><td>Not seen</td><td>Retargeting media source\*</td></tr><tr><td rowspan="2">In-app event attributions going forward</td><td>Post Reinstall Events set to <strong>Attributed as organic in-apps</strong></td><td>Unattributed organic</td><td>Unattributed organic</td><td>Retargeting media source</td></tr><tr><td>Post Reinstall Events set to <strong>Attributed to the first install</strong></td><td>First media source</td><td>First media source</td><td>Retargeting campaign</td></tr><tr><td colspan="5">\*Only in the overview dashboard.</td></tr></tbody></table>

## Reinstalls raw data reports

> 📘 **Prerequisites**
>
> Requires enabling. Reach out to your CSM to discuss this.

* [Reinstall example report as a CSV file](https://docs.google.com/spreadsheets/d/e/2PACX-1vQtlerXtCVImurv-JyuG7JMPvLN6p2w79pmbMNBx6WBnLwnYq5bUqXiUuoy2l_UTzEjIr8UkDdclRxf/pub?output=csv)

#### How the install and in-app events are attributed

<table><thead><tr><th colspan="2"> </th><th>Reinstall non-organic</th><th>Reinstall organic </th><th>Re-attribution</th><th>Install non-organic</th><th>Install organic</th></tr></thead><tbody><tr><td colspan="2">Attributed to </td><td>UA campaign</td><td>Organic</td><td>Retargeting campaign</td><td>UA campaign</td><td>Organic</td></tr><tr><td rowspan="2">Event attribution going forward</td><td>Post Reinstall Events set to <strong>Attributed as organic in-apps</strong></td><td>Organic</td><td>Organic</td><td>Retargeting campaign</td><td>UA campaign</td><td>Organic</td></tr><tr><td>Post Reinstall Events set to <strong>Attributed to the first install</strong></td><td>First install</td><td>First install</td><td>Retargeting campaign</td><td>UA campaign</td><td>Organic</td></tr></tbody></table>

### Availability of reinstall reports

* Reinstall raw data reports are available using the delivery tools detailed in the table that follows.
* The reports have the same structure and are populated in a similar manner to install reports in that:
  * **Media source** fields are populated using the media source that brought the reinstall or organic.
  * **Install time**: Interpret as reinstall time, meaning the time of the first app open after the reinstall
  * **Event name:***Reinstall*

| Report delivery method | Non-organic reinstall | Organic reinstall |
| --- | --- | --- |
| [Export data](/docs/raw-data-reporting-overview) | **✓** | **✓** |
| [Pull API](/docs/pull-api-aggregate-data) | **✓** | **✓** |
| [Data Locker](/docs/data-locker-for-marketers) | **✓** | **✓** |
| Push API | **✓** | **✓** |

<div data-zendesk-anchors="01H7SZVZPGHBQ7VM8TMWRD3CE4=what-is-a-reinstall 01H7SZVZPG6T2AW9B3EMT29AQQ=why-are-reinstalls-important 01H7SZVZPGVQCNCQ7TCZMYM33T=reinstall-flow-and-outcome 01H7SZVZPGCDP3GRK1BWZ04MR6=reinstall 01H7SZVZPG8WNTK30YXNZ44VTS=reattribution inapp-events=post-reinstall-in-app-events 01H7SZVZPGBYRWZGAZRT36EFGH=post-reinstall-in-app-events h_01K47GSZ90CKBGPCZFGQBD1PMK=postreinstall-events-attribution-state 01H7SZVZPH4AE1PZK8V5JG6C6X=unattributed-organic-inapps 01H7SZVZPH7KPM7T42GHZ7N69S=attributed-to-the-first-install h_01KHJV7J6H5KKMZVZN8XPW4CEZ=note 01H7SZVZPH5YGSMPGW7NPKXJAF=note-1 with-attributed-to-the-first-install-enabled=examples-for-first-install-mode-attribution 01H7SZVZPHH3DS9J4VRD70VTX6=examples-for-first-install-mode-attribution h_01K47KBXE2NXXQFMS4RPJ0RA4T=confirm-inapps-are-attributed-to-the-original-install 01H7SZVZPH8MSBQ92XWFK0HWGQ=limitations 01H7SZVZPHHQS4NHEDATD7ZP9V=how-does-the-data-appear-in-the-appsflyer-dashboards 01H7SZVZPHPWN8REBQ5CWVFNJT=reinstalls-raw-data-reports 01H7SZVZPHCVDPDDYD6HHNFMMK=prerequisites how-the-install-and-inapp-events-are-attributed=how-the-install-and-in-app-events-are-attributed 01H7SZVZPHQT8XS3ZBA4W682GB=how-the-install-and-in-app-events-are-attributed 01H7SZVZPH6NY7FMG9YHDBB95R=availability-of-reinstall-reports" />

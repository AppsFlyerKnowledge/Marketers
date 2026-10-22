---
title: Changing app time-zone settings
metadata:
  keywords:
    - Time Zone
    - Existing Apps
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2017-01-12T15:33:00Z'
  edited_at: '2025-09-17T10:16:51Z'
  id: 115000306786
  locale: en-us
  section: Manage your apps
  section_id: 6551015977105
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115000306786-Changing-app-time-zone-settings
---
> **At a glance:** Set or change an app-specific time zone in order to view the app's data more closely aligned with your time zone or that of your advertising partners. Understand the effect of time zone changes on the reporting of data within the AppsFlyer platform.

## Why change the time zone?

The default time zone for new apps is UTC (UTC +0). If the app time zone is changed, this affects how data appears in the platform.

* **Scenario:** You work in a time zone that is not UTC. However, you want app data aligned to your time zone or to the time zone you selected with other partners like Meta ads and Google.
* **Goal:** Simplify data comparisons between AppsFlyer and other networks.
* **Solution:** Align the time zone in the AppsFlyer platform with the other service providers you use. Accurate Daylight savings time is supported by default (not configurable).

**Agencies and ad networks**:

* Agencies: view data using the time zone set by the app owner. Agencies can't set the time zone.
* Ad networks: view data using UTC at all times irrespective of the timezone set by the advertiser.

## Changing the time zone

An admin user can make timezone changes. Changes can be made once every 48 hours. The change timezone settings are unavailable within 48 hours of a previous change.

**To change the app time zone:**

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings.**
2. In **Localization > Time Zone**, select **UTC**.
3. Click **Save settings**, then wait 48 hours.
4. Go to **Settings** > **App settings**.
5. In **Localization** > **Time Zone** > select a time zone (per city/country).
6. Click **Save settings**.  
   Change takes effect at the beginning of the next day at 00:00 UTC.

> 📄 **Example**
>
> * October 24 at 22:00, the timezone is changed (meaning steps 1-6 above are completed).
> * October 25 at 00:00 UTC, the change takes effect.

After changing the time-zone:

* The time zone used in the presentation of data depends on the reporting period and method as detailed in the tables that follow.
* Aggregate reports will have some anomalies on the day and the day following the time zone change.
  * Cost data is duplicated on the day and the day following the change.

#### Aggregate data

<table><thead><tr><th rowspan="2">Reporting method </th><th colspan="3">Report date range</th></tr><tr><th>Starts and ends <span>before</span> the change </th><th>Starts and ends <span>after</span> the change </th><th>Starts before and ends after the change</th></tr></thead><tbody><tr><td>My Dashboards</td><td><p>Not supported. Data is available only in UTC when the dashboard’s timezone is changed.</p></td><td>Current time zone</td><td>Data is presented only for dates after the change.</td></tr><tr><td>Overview dashboard</td><td>Previous time zone</td><td>Current time zone</td><td><p>Split:</p><ul><li>Before the change: UTC</li><li>After the change: current time zone</li></ul></td></tr><tr><td>Events and custom dashboards</td><td>UTC</td><td>Current time zone</td><td><p>Split:</p><ul><li>Before the change: UTC</li><li>After the change: current time zone</li></ul></td></tr><tr><td>Activity dashboard</td><td>Previous time zone</td><td>Current time zone</td><td>UTC</td></tr><tr><td>Cohort, Retention, Pivot</td><td>UTC</td><td>Current time zone (1)</td><td>UTC</td></tr><tr><td>Master API</td><td colspan="3"><ul><li>Default: UTC</li><li>Option: <a href="./pull-api-aggregate-data" target="_blank">Select the time zone when you pull data</a> </li></ul></td></tr><tr><td colspan="4">Notes:<br/>(1) All apps must use the same app-specific time zone for a given reporting period. If not, then the time zone reverts to UTC.</td></tr></tbody></table>

#### Raw data reports

<table><thead><tr><th rowspan="2">Reporting method </th><th colspan="3">Report date range</th></tr><tr><th>Starts and ends <span>before</span> the change </th><th>Starts and ends <span>after</span> the change </th><th>Starts before and ends after the change</th></tr></thead><tbody><tr><td>Export page raw data</td><td>Current time zone</td><td>Current time zone</td><td>Current time zone</td></tr><tr><td>Push API</td><td colspan="3">Separate fields for UTC and the app-specific time zone calculated using the selected time zone at the time of the event.</td></tr><tr><td>Pull API</td><td colspan="3"><ul><li>Default: UTC</li><li>Option: <a href="./pull-api-aggregate-data" target="_blank">Select the time zone when you pull the data</a></li></ul></td></tr><tr><td>Data Locker</td><td colspan="3">No impact—date fields are in UTC</td></tr></tbody></table>

<div data-zendesk-anchors="h_01HJR69P6Z44SZA5A684H82PNV=why-change-the-time-zone h_01HJR69P6ZWJQ47FQY2HATAAE3=changing-the-time-zone h_01HJR69P6Z6B0Q6E6996WXVZ0N=example h_01HJR69P6ZY8JJBCBSDZKN75N6=aggregate-data h_01HJR69P6ZDXXK8ZTKK3E774VJ=raw-data-reports" />

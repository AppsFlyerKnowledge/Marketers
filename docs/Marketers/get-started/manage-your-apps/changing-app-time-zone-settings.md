---
title: "Changing app time-zone settings"
excerpt: "Learn how to set or change an app-specific time zone in AppsFlyer to align your data reporting with your local time zone or advertising partners."
---
**At a glance:** Set or change an app-specific time zone in order to view the app's data more closely aligned with your time zone or that of your advertising partners. Understand the effect of time zone changes on the reporting of data within the AppsFlyer platform.

## Why change the time zone?

The default time zone for new apps is UTC (UTC +0). If the app time zone is changed, this affects how data appears in the platform.

- **Scenario:** You work in a time zone that is not UTC. However, you want app data aligned to your time zone or to the time zone you selected with other partners like Meta ads and Google.
- **Goal:** Simplify data comparisons between AppsFlyer and other networks.
- **Solution:** Align the time zone in the AppsFlyer platform with the other service providers you use. Accurate Daylight savings time is supported by default (not configurable).

**Agencies and ad networks**:

- Agencies: view data using the time zone set by the app owner. Agencies can't set the time zone.
- Ad networks: view data using UTC at all times irrespective of the timezone set by the advertiser.

## Changing the time zone

An admin user can make timezone changes. Changes can be made once every 48 hours. The change timezone settings are unavailable within 48 hours of a previous change.

**To change the app time zone:**

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings.**
2. In **Localization > Time Zone**, select **UTC**.
3. Click **Save settings**, then wait 48 hours.
4. Go to **Settings** > **App settings**.
5. In **Localization** > **Time Zone** > select a time zone (per city/country).
6. Click **Save settings**.

Change takes effect at the beginning of the next day at 00:00 UTC.

#### Example

- October 24 at 22:00, the timezone is changed (meaning steps 1-6 above are completed).
- October 25 at 00:00 UTC, the change takes effect.

After changing the time-zone:

- The time zone used in the presentation of data depends on the reporting period and method as detailed in the tables that follow.
- Aggregate reports will have some anomalies on the day and the day following the time zone change.
  - Cost data is duplicated on the day and the day following the change.

#### Aggregate data

| Reporting method | Starts and ends before the change | Starts and ends after the change | Starts before and ends after the change |
| --- | --- | --- | --- |
| My Dashboards | Not supported. Data is available only in UTC when the dashboard’s timezone is changed. | Current time zone | Data is presented only for dates after the change. |
| Overview dashboard | Previous time zone | Current time zone | Split:<br>- Before the change: UTC<br>- After the change: current time zone |
| Events and custom dashboards | UTC | Current time zone | Split:<br>- Before the change: UTC<br>- After the change: current time zone |
| Activity dashboard | Previous time zone | Current time zone | UTC |
| Cohort, Retention, Pivot | UTC | Current time zone (1) | UTC |
| Master API | - Default: UTC<br>- Option: [Select the time zone when you pull data](https://support.appsflyer.com/hc/articles/207034346) | | |

> 📘 Notes
>
> (1) All apps must use the same app-specific time zone for a given reporting period. If not, then the time zone reverts to UTC.

#### Raw data reports

| Reporting method | Starts and ends before the change | Starts and ends after the change | Starts before and ends after the change |
| --- | --- | --- | --- |
| Export page raw data | Current time zone | Current time zone | Current time zone |
| Push API | Separate fields for UTC and the app-specific time zone calculated using the selected time zone at the time of the event. | | |
| Pull API | - Default: UTC<br>- Option: [Select the time zone when you pull the data](https://support.appsflyer.com/hc/articles/207034346) | | |
| Data Locker | No impact—date fields are in UTC | | |
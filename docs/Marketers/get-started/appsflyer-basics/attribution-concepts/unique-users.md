---
title: "Unique users"
excerpt: "Learn how unique users are counted and used in metrics across AppsFlyer dashboards and reports."
---
At a glance: Learn how unique users are counted and used in metrics in AppsFlyer dashboards and reports.

## About unique users

A unique user is a term that refers to an attributed device whose presence is counted only once, regardless of how many actions a user performs on the device.

It's a calculation used in a wide variety of marketing metrics, including:

- Installs: The number of unique users who downloaded and installed the app.
- Retention rate: On-day percentage of unique users with a session.
- Event unique users: Number of unique users (attributions) who perform the event.
- Daily active users (DAU): Number of unique users (counted only once) who open the app at least once during the day.
- And many more.

The calculation of unique users is based on the device ID (like IDFA or GAID). If no device ID is available (like for iOS SKAN), the AppsFlyer ID is used instead. This ensures that a user is counted once since the device ID or AppsFlyer ID is the same for all the actions, no matter how many sessions or actions they perform.

## Use cases

Although the unique user calculation is usually straightforward, questions sometimes arise around certain user behaviors or actions. The following use cases explain how unique users are counted in some of those more complicated instances.

### Install and reinstall

The install and reinstall have the same device ID/AppsFlyer ID. Therefore, only 1 unique user is counted. Both in-app events are attributed to the same unique user as the first install.

> 📘 Note
>
> - If a reinstall doesn't include a device ID/AppsFlyer ID, it can't be connected to the first install, and is considered as “unattributed organic.” Post-reinstall events after unattributed organic reinstalls aren't included in the unique user count.
> - There may be other reasons for events being unattributed organic. In these cases, as well, the events aren't included in the unique user count.

### Install and re-attribution

The install and re-attribution have the same device ID (AppsFlyer ID is the same). However, in this case, AppsFlyer also takes into account the parameter `is_retargeting=true` so the event after the re-attribution is counted as an additional unique user. Therefore, 2 unique users are counted.

- In the Overview dashboard, the UA view displays 1 unique user since retargeting re-attributions aren't shown in the UA view. Same for UA reports.
- In the Overview dashboard, the retargeting view, displays 1 unique user since UA installs aren't shown in the retargeting view. Same for retargeting reports.
- In the Overview dashboard, the unified view, displays 2 unique users, 1 connected to the first install and the 2nd connected to the re-attribution. Same for unified reports.

### Install and re-engagement

The install and re-engagement have the same device ID/AppsFlyer ID. However, in this case (just like for re-attributions), AppsFlyer also takes into account the parameter `is_retargeting=true` so the event after the re-engagement is counted as an additional unique user. Therefore, 2 unique users are counted.

- In the Overview dashboard, the UA view displays 1 unique user since retargeting re-engagements aren't shown in the UA view. Same for UA reports.
- In the Overview dashboard, the retargeting view, displays 1 unique user since UA installs aren't shown in the retargeting view. Same for retargeting reports.
- In the Overview dashboard, the unified view, displays 2 unique users, 1 connected to the first install and the 2nd connected to the re-engagement. Same for unified reports.

### Unattributed in-app events

When an in-app event is unattributed, meaning it's following a reinstall but for whatever reason isn't linked to the first install, it's not included in the unique user count at all. This can occur when there isn't a device ID available for the reinstall, but **there could be other reasons as well**. [Learn more](https://support.appsflyer.com/hc/articles/10164066030737-Reinstalls#unattributed-organic-inapps)

## Traits and limitations

| Trait | Details |
| --- | --- |
| Ad revenue events<br>(af\_ad revenue) | - Unique user count is supported for ad revenue events for:<br>  - Cohort on-day metrics<br>  - Activity metrics<br>  - SKAN metrics<br>- Unique user count isn't supported for ad revenue events for:<br>  - Cohort cumulative metrics<br>  - LTV metrics via Classic attribution method. <br><br>**Note**: To clarify, this means that when looking at a dashboard with SSOT view, unique user metric for ad revenue events is available for SKAN data, but not Classic attribution data. |
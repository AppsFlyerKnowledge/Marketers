---
title: Unique users
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
  created_at: '2024-08-11T09:52:33Z'
  edited_at: '2026-10-13T00:25:06Z'
  id: 27435981457553
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/27435981457553
---
> **At a glance:** Learn how unique users are counted and used in metrics in AppsFlyer dashboards and reports.

## About unique users

A unique user is a term that refers to an attributed device whose presence is counted only once, regardless of how many actions a user performs on the device.

It's a calculation used in a wide variety of marketing metrics, including:

* Installs: The number of unique users who downloaded and installed the app.
* Retention rate: On-day percentage of unique users with a session.
* Event unique users: Number of unique users (attributions) who perform the event.
* Daily active users (DAU): Number of unique users (counted only once) who open the app at least once during the day.
* And many more.

The calculation of unique users is based on the device ID (like IDFA or GAID). If no device ID is available (like for iOS SKAN), the AppsFlyer ID is used instead. This ensures that a user is counted once since the device ID or AppsFlyer ID is the same for all the actions, no matter how many sessions or actions they perform.

## Use cases

Although the unique user calculation is usually straightforward, questions sometimes arise around certain user behaviors or actions. The following use cases explain how unique users are counted in some of those more complicated instances.

<div id="install-and-reinstall" />

<Accordion title="Install and reinstall">

![](https://files.readme.io/8b9f3c442f98c056069b4449c7e5115cbea828a64ace3a98e0090fb0d8d1d8d6-27455116159889.png)

The install and reinstall have the same device ID/AppsFlyer ID. Therefore, only 1 unique user is counted. Both in-app events are attributed to the same unique user as the first install.

**Note**:

* If a reinstall doesn't include a device ID/AppsFlyer ID, it can't be connected to the first install, and is considered as “unattributed organic.” Post-reinstall events after unattributed organic reinstalls aren't included in the unique user count.
* There may be other reasons for events being unattributed organic. In these cases, as well, the events aren't included in the unique user count.

</Accordion>

<div id="install-and-reattribution" />

<Accordion title="Install and re-attribution">

![](https://files.readme.io/40420c5ea201ba7cf13d03e5968d20c2fffaa31b74c47ae36cd917cccbaae353-27453973190289.png)

The install and re-attribution have the same device ID (AppsFlyer ID is the same). However, in this case, AppsFlyer also takes into account the parameter `is_retargeting=true` so the event after the re-attribution is counted as an additional unique user. Therefore, 2 unique users are counted.

* In the Overview dashboard, the UA view displays 1 unique user since retargeting re-attributions aren't shown in the UA view. Same for UA reports.
* In the Overview dashboard, the retargeting view, displays 1 unique user since UA installs aren't shown in the retargeting view. Same for retargeting reports.
* In the Overview dashboard, the unified view, displays 2 unique users, 1 connected to the first install and the 2nd connected to the re-attribution. Same for unified reports.

</Accordion>

<div id="install-and-reengagement" />

<Accordion title="Install and re-engagement">

![](https://files.readme.io/17b2bcd5365defb92e330ef8ce9cbcaf462912477704eca25439ade81f01e424-51165279253393.png)

The install and re-engagement have the same device ID/AppsFlyer ID. However, in this case (just like for re-attributions), AppsFlyer also takes into account the parameter `is_retargeting=true` so the event after the re-engagement is counted as an additional unique user. Therefore, 2 unique users are counted.

* In the Overview dashboard, the UA view displays 1 unique user since retargeting re-engagements aren't shown in the UA view. Same for UA reports.
* In the Overview dashboard, the retargeting view, displays 1 unique user since UA installs aren't shown in the retargeting view. Same for retargeting reports.
* In the Overview dashboard, the unified view, displays 2 unique users, 1 connected to the first install and the 2nd connected to the re-engagement. Same for unified reports.

</Accordion>

<div id="unattributed-inapp-events" />

<Accordion title="Unattributed in-app events">

![](https://files.readme.io/94bf078bcf4ba26a1dc4ca323a1b4a7543cfb4e3fc8b780d0d29713c4266aa95-27455116170001.png)

When an in-app event is unattributed, meaning it's following a reinstall but for whatever reason isn't linked to the first install, it's not included in the unique user count at all. This can occur when there isn't a device ID available for the reinstall, but **there could be other reasons as well**. <Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls#unattributed-organic-inapps">Learn more</Anchor>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Details |
| --- | --- |
| Ad revenue events<br /><br />(af\_ad revenue) | <ul><li>Unique user count is supported for ad revenue events for:<ul><li>Cohort on-day metrics</li><li>Activity metrics</li><li>SKAN metrics</li></ul></li><li>Unique user count isn't supported for ad revenue events for:<ul><li>Cohort cumulative metrics</li><li>LTV metrics via Classic attribution method. **Note**: To clarify, this means that when looking at a dashboard with SSOT view, unique user metric for ad revenue events is available for SKAN data, but not Classic attribution data.</li></ul></li></ul> |

</Accordion>

<div data-zendesk-anchors="overview=about-unique-users 01H7Z1003GTTMRY072BXWDFNP0=about-unique-users h_01J52T4MT63JVJEQ050E2BXMVQ=use-cases h_01J52T9B4ZZH1TBW98YM5MY675=install-and-reinstall h_01J52T9B4ZYWQAGS3QHG99G3AS=install-and-reattribution h_01J531V2AKW8QP33B6K8QFH72R=install-and-reengagement h_01J52WPCZEBFP4RR0Y4ZC5TABK=unattributed-inapp-events h_01J52ZHXKYDG77PE70QZV63KY3=traits-and-limitations" />

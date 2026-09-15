---
title: "Bulletin: First install attribution for post-reinstall in-app events"
excerpt: "Learn about the enhancement that attributes post-reinstall in-app events and sessions to the original media source instead of labeling them organic unattributed."
---
This enhancement attributes all [in-app events](https://support.appsflyer.com/hc/articles/10164066030737-Reinstalls#inapp-events) and sessions following a re-engagements or a [re-attribution](https://support.appsflyer.com/hc/articles/10164066030737-Reinstalls#reattribution) to the original media source that drove it (’first install’) rather than labeling them ‘organic unattributed.’

<Image src="https://files.readme.io/42a96ec533d217ee4dadad71592023d1fd0c977557308638f3553660a95fc7b5-25827620446353.png" alt="First install attribution flow diagram" />

### Effective date
July 31, 2024. The first-install mode automatically applies only to apps added to AppsFlyer on or after the effective date. For apps added before July 31, 2024, we recommend contacting AppsFlyer to migrate your existing apps to the first-install mode.

### Prerequisites
None

### Required actions
None

### What must I know?

> 📘 Important
>
> Only users who have consented to share their device identifier (such as IDFA or GAID) with the app for both the install and reinstall will have their in-app events attributed to the original install. Otherwise, they will be labeled as ‘organic unattributed.’

### What's the impact?
- For apps added to AppsFlyer **after July 31, 2024**: No impact
- For apps added **before July 31, 2024**, we recommend contacting AppsFlyer to migrate your existing apps to first-install mode. After the migration, the following may occur:
  - A potential increase in the number of in-app events and sessions attributed to the first install following a reinstall, along with a corresponding decrease in the attributions classified as 'organic' for such events.
  - A potential increase in the MAU (Monthly Active Users) count for media sources attributed originally and a decrease in the MAU count for organic sources.
  - On the day when the app switches to first-install mode, the session count doubles. As a result, the day 1 retention rate for the cohort is unusually high.
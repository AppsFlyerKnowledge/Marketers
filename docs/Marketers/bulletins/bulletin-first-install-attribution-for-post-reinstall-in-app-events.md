---
title: "Bulletin: First install attribution for post-reinstall in-app events"
table_of_contents: false
x-zendesk:
  id: 25676426941457
  url: https://support.appsflyer.com/hc/en-us/articles/25676426941457-Bulletin-First-install-attribution-for-post-reinstall-in-app-events
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 19
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-moran-davida, Marketers, Mobile Attribution]
  labels: [Marketers, Loc Published]
  promoted: false
  comments_disabled: false
  created_at: '2024-06-05T15:04:01Z'
  edited_at: '2025-04-30T14:37:51Z'
---
| **What's new** | This enhancement attributes all [in-app events](/docs/measure-reinstalls#post-reinstall-in-app-events) and sessions following a re-engagements or a [re-attribution](/docs/measure-reinstalls#reattribution) to the original media source that drove it (’first install’) rather than labeling them ‘organic unattributed.’<br /><br />![Screenshot 2024-06-11 at 8.44.30.png](https://files.readme.io/42a96ec533d217ee4dadad71592023d1fd0c977557308638f3553660a95fc7b5-25827620446353.png) |
| --- | --- |
| **Effective date** | July 31, 2024. The first-install mode automatically applies only to apps added to AppsFlyer on or after the effective date. For apps added before July 31, 2024, we recommend contacting AppsFlyer to migrate your existing apps to the first-install mode. |
| **Prerequisites** | None |
| **Required actions** | None |
| **What must I know?** | Only users who have consented to share their device identifier (such as IDFA or GAID) with the app for both the install and reinstall will have their in-app events attributed to the original install. Otherwise, they will be labeled as ‘organic unattributed.’ |
| **What's the impact?** | <ul><li>For apps added to AppsFlyer **after July 31, 2024**: No impact</li><li>For apps added **before July 31, 2024**, we recommend contacting AppsFlyer to migrate your existing apps to first-install mode. After the migration, the following may occur:<ul><li>A potential increase in the number of in-app events and sessions attributed to the first install following a reinstall, along with a corresponding decrease in the attributions classified as 'organic' for such events.</li><li>A potential increase in the MAU (Monthly Active Users) count for media sources attributed originally and a decrease in the MAU count for organic sources.</li><li>On the day when the app switches to first-install mode, the session count doubles. As a result, the day 1 retention rate for the cohort is unusually high.</li></ul></li></ul> |
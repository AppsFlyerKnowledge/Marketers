---
title: 'Bulletin: Digital Turbine migration to unified AppsFlyer integration'
hidden: false
deprecated: false
table_of_contents: false
x-zendesk:
  id: 50419778565521
  url: https://support.appsflyer.com/hc/en-us/articles/50419778565521-Bulletin-Digital-Turbine-migration-to-unified-AppsFlyer-integration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 0
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: []
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2026-09-01T10:27:56Z'
  edited_at: '2026-09-30T09:03:00Z'
---
| **Section** | **Details** |
| --- | --- |
| **What's New** | Digital Turbine (DT) is migrating advertisers from the legacy PID `digitalturbine_int` to the new unified PID `onedigitalturbine_int`, as part of DT's move to its Ads platform migration.<br /><br />The unified integration gives you access to DT's machine learning capabilities and first-party device signals. |
| **Effective Date** | October 1, 2026 |
| **What you need to know** | **New media source**<br /><br />* The new media source is `onedigitalturbine_int`.<br /><br />**Campaign reporting dimensions**<br /><br />* Reporting shifts from Campaign/Campaign ID to Adset/Adset ID.<br />* This affects cohort and LTV reporting.<br /><br />**Reporting during the transition**<br /><br />* Select both media sources (`digitalturbine_int` and `onedigitalturbine_int`) when reviewing reports during the transition period.<br />* Review any custom dashboards, BI integrations, or saved reports that reference the legacy PID, since they won't automatically pick up the new PID. |
| **What you need to do** | 1. Generate new attribution links using the [DT&lt;>AppsFlyer Integration Guide](https://docs.digitalturbine.com/measurement/mmp-guides/appsflyer), and send them to your DT Account Manager.<br />2. DT will migrate your campaigns to the new links. You don't need to recreate them manually.<br />3. Keep your legacy integration active until your lookback window expires, so in-flight conversions still attribute correctly. On the day you transition, switch cost reporting to DT's Unified Reporting API only. Do this as soon as `onedigitalturbine_int`  is live, and avoid running both at once to prevent double-counting spend.<br /><br />**Reporting API and cost data**<br /><br />* Transition from the legacy Reporting API to DT's Unified Reporting API to avoid duplicate data.<br />* InCost is configured at the account level.<br />* The app-level Cost tab is being phased out for migrated networks.<br />* Account-level API authentication is required under the `onedigitalturbine_int` partner setup.<br />* No Client ID or Secret is needed for cost data. AppsFlyer receives it directly from DT. What's changed is the setup flow: Cost integration used to be enabled per app, and now it's configured once at the account level for multiple apps.<br /><br />**Migration deadline**<br /><br />* The **deadline is October 1, 2026**. Generate your new links as soon as possible.<br />* DT will monitor delivery and cost data after the migration.<br />* If you run into issues, contact AppsFlyer Support or your CSM, or reach out to your DT account manager. |
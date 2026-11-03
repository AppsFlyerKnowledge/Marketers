---
title: 'Bulletin: Digital Turbine migration to unified AppsFlyer integration'
deprecated: false
hidden: false
metadata:
  keywords:
    - Marketers
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-01T10:27:56Z'
  edited_at: '2026-10-13T02:06:41Z'
  id: 50419778565521
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/50419778565521
---
| **Section** | **Details** |
| --- | --- |
| **What's New** | Digital Turbine (DT) is migrating advertisers from the legacy PID `digitalturbine_int` to the new unified PID `onedigitalturbine_int`, as part of DT's move to its Ads platform migration.<br /><br />The unified integration gives you access to DT's machine learning capabilities and first-party device signals. |
| **Effective Date** | October 1, 2026 |
| **What you need to know** | **New media source**<ul><li>The new media source is `onedigitalturbine_int`.</li></ul>**Campaign reporting dimensions**<ul><li>Reporting shifts from Campaign/Campaign ID to Adset/Adset ID.</li><li>This affects cohort and LTV reporting.</li></ul>**Reporting during the transition**<ul><li>Select both media sources (`digitalturbine_int` and `onedigitalturbine_int`) when reviewing reports during the transition period.</li><li>Review any custom dashboards, BI integrations, or saved reports that reference the legacy PID, since they won't automatically pick up the new PID.</li></ul> |
| **What you need to do** | <ol><li>Generate new attribution links using the <Anchor target="_blank" href="https://docs.digitalturbine.com/measurement/mmp-guides/appsflyer">DT&lt;>AppsFlyer Integration Guide</Anchor>, and send them to your DT Account Manager.</li><li>DT will migrate your campaigns to the new links. You don't need to recreate them manually.</li><li>Keep your legacy integration active until your lookback window expires, so in-flight conversions still attribute correctly. On the day you transition, switch cost reporting to DT's Unified Reporting API only. Do this as soon as `onedigitalturbine_int`  is live, and avoid running both at once to prevent double-counting spend.</li></ol>**Reporting API and cost data**<ul><li>Transition from the legacy Reporting API to DT's Unified Reporting API to avoid duplicate data.</li><li>InCost is configured at the account level.</li><li>The app-level Cost tab is being phased out for migrated networks.</li><li>Account-level API authentication is required under the `onedigitalturbine_int` partner setup.</li><li>No Client ID or Secret is needed for cost data. AppsFlyer receives it directly from DT. What's changed is the setup flow: Cost integration used to be enabled per app, and now it's configured once at the account level for multiple apps.</li></ul>**Migration deadline**<ul><li>The **deadline is October 1, 2026**. Generate your new links as soon as possible.</li><li>DT will monitor delivery and cost data after the migration.</li><li>If you run into issues, contact AppsFlyer Support or your CSM, or reach out to your DT account manager.</li></ul> |
---
title: '[Bulletin] Agency data is now transparent'
metadata:
  keywords:
    - Marketers
    - Platform essentials
    - Agencies
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2025-01-23T11:20:37Z'
  edited_at: '2025-02-10T09:52:44Z'
  id: 32048747169553
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/32048747169553--Bulletin-Agency-data-is-now-transparent
---
| **What's new** | All agencies are now transparent. This change enhances your ability to analyze and optimize your marketing investments with greater granularity. |
| --- | --- |
| **Update date** | March 12, 2025 |
| **What you need to know** | **Before the change**: For non-transparent agencies, the media source field showed the agency name, instead of the specific ad network.<br /><br />**After the change**:<ul><li>All agency-managed campaign data will be fully visible to you down to the media source level, regardless of previous transparency settings. Meaning, the media source field will show the specific ad network, instead of the agency name. You will still be able to group data by agency.</li><li>Dashboards: Historical agency data will also be transparent.</li><li>Reports: Data of reports received before the change will not be updated. For example, reports written to Data Locker prior to the update will include non-transparent agency data, but reports written after the update, will show transparent agency data.</li><li>Protect360 validation rules defined for "non-transparent agencies,”  will be reclassified as simply for "Agencies". The rules will continue to operate seamlessly within the updated transparent agency framework, with all other defined settings.</li><li>If you are working with cost data reported before the change, you may see the aggregated cost split into multiple lines: one under the previous agency name (before the change) and another under the media source directly (after the change). In this case, you should replace the cost data from before the change with the data after the change.</li></ul> |
| **What you need to do** | If you have internal workflows that rely on the current "agency name" presented as the media source for non-transparent agencies, review these workflows and consider updating them to accommodate this change.<br /><br />For example, in dashboards, group data by either media source or agency. And in reports, use the `media_source` or `af_prt` fields, as needed. |
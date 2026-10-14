---
title: 'Bulletin: Push API Update: Changes to “Message Fields” Selection Behavior'
metadata:
  keywords:
    - Marketers
    - Raw Reports
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2025-12-10T11:38:33Z'
  edited_at: '2025-12-10T11:41:45Z'
  id: 41785747996689
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/41785747996689-Bulletin-Push-API-Update-Changes-to-Message-Fields-Selection-Behavior
---
| Section | Details |
| --- | --- |
| **What's new** | The behavior of the Push API configuration setting `selected_fields = "ALL FIELDS"`   changes. This setting will no longer act as a future-proof selector. It will only apply to the message fields that exist at the moment the configuration is saved. Any new fields added later will not be included automatically.<br /><br />This change increases schema transparency, gives customers better control of their data pipelines, and prevents unplanned field expansion. |
| **Effective date** | December 30, 2025 |
| **What you need to know** | <ul><li>The Push API setting can be applied in the following ways:<ul><li>[Update push API configuration REST API](https://dev.appsflyer.com/hc/reference/put_app-app-id):<ul><li>Set the `select_fields` property to ALL Fields</li></ul></li><li>[In AppsFlyer, under Export-> API Access -> Push API or Push API (SKAN)](/docs/push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint):<ul><li>Select the **Select All** field.</li></ul></li></ul></li><li>When calling the [Get Push API configuration REST API](https://dev.appsflyer.com/hc/reference/get_app-app-id) when `selected_fields = "ALL FIELDS"` is set, the call will return the explicit list of selected fields instead of the generic “all”.</li></ul> |
| **What you need to do** | <ul><li>Most customers do not need to take action.</li><li>No changes to field names or semantics.</li><li>Customers  must manually update their selection in AppsFlyer or via the REST API to receive newly added fields.</li><li>Customers using “ALL FIELDS” should periodically review their configuration to ensure new fields are included as needed.</li></ul> |
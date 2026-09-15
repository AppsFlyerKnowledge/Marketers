---
title: "Bulletin: Push API Update: Changes to “Message Fields” Selection Behavior"
excerpt: "Important update regarding changes to the AppsFlyer Push API configuration setting for selecting all fields, effective December 30, 2025."
table_of_contents: false
---
The behavior of the Push API configuration setting `selected_fields = "ALL FIELDS"` changes. This setting will no longer act as a future-proof selector. It will only apply to the message fields that exist at the moment the configuration is saved. Any new fields added later will not be included automatically. This change increases schema transparency, gives customers better control of their data pipelines, and prevents unplanned field expansion.

| Section | Details |
| --- | --- |
| **What's new** | The behavior of the Push API configuration setting `selected_fields = "ALL FIELDS"` changes. This setting will no longer act as a future-proof selector. It will only apply to the message fields that exist at the moment the configuration is saved. Any new fields added later will not be included automatically. <br />This change increases schema transparency, gives customers better control of their data pipelines, and prevents unplanned field expansion. |
| **Effective date** | December 30, 2025 |
| **What you need to know** | - The Push API setting can be applied in the following ways:<br />  - [Update push API configuration REST API](https://dev.appsflyer.com/hc/reference/put_app-app-id): <br />    - Set the `select_fields` property to ALL Fields<br />  - [In AppsFlyer, under Export-> API Access -> Push API or Push API (SKAN)](/docs/push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint):<br />    - Select the **Select All** field.<br />- When calling the [Get Push API configuration REST API](https://dev.appsflyer.com/hc/reference/get_app-app-id) when `selected_fields = "ALL FIELDS"` is set, the call will return the explicit list of selected fields instead of the generic “all”. |
| **What you need to do** | - Most customers do not need to take action. <br />- No changes to field names or semantics.<br />- Customers must manually update their selection in AppsFlyer or via the REST API to receive newly added fields. <br />- Customers using “ALL FIELDS” should periodically review their configuration to ensure new fields are included as needed. |
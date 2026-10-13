---
title: "Bulletin: [Closed Beta] Protect360 Pre-released detection (Billing API)"
table_of_contents: false
x-zendesk:
  id: 27286254350481
  url: https://support.appsflyer.com/hc/en-us/articles/27286254350481-Bulletin-Closed-Beta-Protect360-Pre-released-detection-Billing-API
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 64
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-yanai, Marketers, Protect360]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2024-08-05T16:11:54Z'
  edited_at: '2026-05-04T09:19:39Z'
---
| **What's new** | Protect360 has added the ability to reflect the detection of logics which are not yet in production. The data of this additional detection is deducted from your package (to Appsflyer). This is becasue it reflects non-legitimate conversions which should not be consumed in the package. |
| --- | --- |
| **Released date [Beta]** | July, 2024 |
| **What you need to know** | * The pre-release detection data will be available in **Account Management** **->** **Usage report** **->** **Conversion source** **->** **Pre-released detection**<br />* The pre-release detection is aggregated and divided by Non-organic conversions and Organic conversions.<br />* The pre-release detection will be updated daily. However, the final calculations will be provided on the 10th of the following month.<br />* The pre-released detection is not reflected to partners (as this detection is not yet in production) and therefore is not applicable for reconciliation processes with partners<br />* Pre-released detection numbers are available since July 1st, 2024 |
| **Implications** | Pre-released detections can be found in your Usage report. This pre-release detection reduced your cost, crediting detected fraud back to your package plan.<br /><br />Pre-released detections reflect additional conversions to deduct from the Appsflyer package. |
| **Additional information** | Below are screenshots showing the usage report with the pre-release filter and data visual.<br /><br />#### Usage report - showing where to find the filter.<br /><br />![Usage_protect1.jpg](https://files.readme.io/efdbb5f45e800a762c7c1acca6798845b70c81ce79330123fef90a1909b51b61-27361610892561.jpg)<br /><br />#### Billable report - filtered to show only deduction due to Protect360 pre-released detection (Therefore in minus).<br /><br />![Usage_protect2.jpg](https://files.readme.io/0f5a8caef0d223878f8aee8bcc409313ec69cdef517f91cc0fe68ab8dc0abe16-27361550181905.jpg)<br /><br />#### Pie chart reflecting the total billable conversions breakdown after the deduction of the pre-released detection.<br /><br />![Usage_protect3.jpg](https://files.readme.io/4c327a495a21a16f7b03e6aaa216e79601b8ab31c29a9e1abf48381d345e6bc4-27361610894225.jpg) |
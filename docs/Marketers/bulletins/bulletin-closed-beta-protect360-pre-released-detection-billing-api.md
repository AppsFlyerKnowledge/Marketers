---
title: "Bulletin: Protect360 Pre-released Detection (Billing API)"
excerpt: "Learn about the Protect360 pre-released detection feature in the billing API, which credits detected fraud back to your package plan."
---
## What's new

Protect360 has added the ability to reflect the detection of logics which are not yet in production. The data of this additional detection is deducted from your package (to Appsflyer). This is becasue it reflects non-legitimate conversions which should not be consumed in the package.

## Released date [Beta]

July, 2024

## What you need to know

* The pre-release detection data will be available in **Account Management** **->** **Usage report** **->** **Conversion source** **->** **Pre-released detection**
* The pre-release detection is aggregated and divided by Non-organic conversions and Organic conversions.
* The pre-release detection will be updated daily. However, the final calculations will be provided on the 10th of the following month.
* The pre-released detection is not reflected to partners (as this detection is not yet in production) and therefore is not applicable for reconciliation processes with partners
* Pre-released detection numbers are available since July 1st, 2024

## Implications

Pre-released detections can be found in your Usage report. This pre-release detection reduced your cost, crediting detected fraud back to your package plan.
Pre-released detections reflect additional conversions to deduct from the Appsflyer package.

## Additional information

Below are screenshots showing the usage report with the pre-release filter and data visual.

### Usage report - showing where to find the filter.

<Image src="https://files.readme.io/efdbb5f45e800a762c7c1acca6798845b70c81ce79330123fef90a1909b51b61-27361610892561.jpg" alt="Usage_protect1.jpg" />

### Billable report - filtered to show only deduction due to Protect360 pre-released detection (Therefore in minus).

<Image src="https://files.readme.io/0f5a8caef0d223878f8aee8bcc409313ec69cdef517f91cc0fe68ab8dc0abe16-27361550181905.jpg" alt="Usage_protect2.jpg" />

### Pie chart reflecting the total billable conversions breakdown after the deduction of the pre-released detection.

<Image src="https://files.readme.io/4c327a495a21a16f7b03e6aaa216e79601b8ab31c29a9e1abf48381d345e6bc4-27361610894225.jpg" alt="Usage_protect3.jpg" />
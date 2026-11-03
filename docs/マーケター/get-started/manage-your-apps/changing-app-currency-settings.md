---
title: Changing app currency settings
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2025-12-24T08:22:42Z'
  edited_at: '2026-10-01T00:17:44Z'
  id: 42223406543249
  locale: ja
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ja/articles/42223406543249
---
> **At a glance:** Easily manage your app’s currency settings to align your revenue reporting with your business needs. This article clarifies how currency changes impact your historical and future data, helps you understand who can make changes, and outlines the required approval steps.

## **About changing app currency settings**

By default, your AppsFlyer dashboards display data using your selected local currency. You can easily switch to USD view at any time without changing the actual currency settings of your app.

If you're viewing data from multiple apps with different local currencies, the dashboard defaults to USD automatically.

## **Who can change the app currency?**

Currency changes depend on your app's existing data:

* **Apps without revenue or cost:** You can change the currency directly.
* **Apps with revenue or cost:** Only an **AppsFlyer admin** can perform the change.  
  To request a currency change:

1. Contact your AppsFlyer representative or submit a support ticket.
2. Provide your app details.
3. Attach written approval acknowledging the impact on reporting.

## **How currency changes impact your data**

Changing your app currency impacts revenue data display and accuracy:

<div id="future-data" />

<Accordion title="Future data">

Once the currency changes, all future events with the af\_revenue parameter use the new currency. Reports after the change will reflect this, but reports spanning the change date may show mixed currencies.

</Accordion>

<div id="historical-data-accuracy" />

<Accordion title="Historical data accuracy">

Historical data remains, but becomes inaccurate:

* Revenue events before the change remain in the old currency.
* Revenue events after the change use the new currency.
* This mixture causes inaccuracies in metrics like LTV and ROAS.

The impact varies:

* **Extensive revenue history:** Significant discrepancies.
* **Minimal revenue history:** Lesser impact.

</Accordion>

### **Example**

<div id="reporting-impacts" />

<Accordion title="Reporting impacts">

If you change your app currency on **October 1**, here's how revenue reporting methods are affected:

| **Reporting method** | **Before Oct 1** | **Spanning Oct 1** | **After Oct 1** |
| --- | --- | --- | --- |
| **LTV & Cohort (D0–180)** | Mixed currencies (inaccurate) | Mixed currencies (inaccurate) | Accurate |
| **Activity** | Shows previous currency | Mixed currencies (inaccurate) | Accurate |
| **SSOT** | Accurate up to 7 days before the change | Mixed currencies (inaccurate) | Accurate |

</Accordion>

> 🚧 **Important!**
>
> * Currency changes are **permanent**.
> * Historical data **cannot be converted or restored**.
> * Confirm all implications with your AppsFlyer account manager before making changes.

<div data-zendesk-anchors="h_01KD7Q6FR8VKG3HGXDJC6YB5J3=about-changing-app-currency-settings h_01KD7Q6FR96NRV4SBRQ8YEW12X=who-can-change-the-app-currency h_01KD7Q6FRB9TCV2N0KT2N4599A=how-currency-changes-impact-your-data h_01KD7QJQ4FF197R69RAD5Q6KKT=future-data h_01KD7QM57R8TJY5T10R36EB1P9=historical-data-accuracy h_01KD7QW856FFEQ779153KNCYW6=example h_01KD7QG6CB2KFGXE6D4M46B65H=reporting-impacts h_01KD7QS7EYS21KX0Q9WB7ETV99=important" />

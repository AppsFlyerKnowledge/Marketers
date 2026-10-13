---
title: "Changing app currency settings"
excerpt: "Learn how changing your app's currency settings impacts historical and future revenue reporting, who can make these changes, and the required approval steps."
x-zendesk:
  id: 42223406543249
  url: https://support.appsflyer.com/hc/en-us/articles/42223406543249-Changing-app-currency-settings
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Manage your apps
  section_id: 6551015977105
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2025-12-24T08:22:42Z'
  edited_at: '2025-12-25T00:01:08Z'
---
**At a glance:** Easily manage your app’s currency settings to align your revenue reporting with your business needs. This article clarifies how currency changes impact your historical and future data, helps you understand who can make changes, and outlines the required approval steps.

## **About changing app currency settings**

By default, your AppsFlyer dashboards display data using your selected local currency. You can easily switch to USD view at any time without changing the actual currency settings of your app.

If you're viewing data from multiple apps with different local currencies, the dashboard defaults to USD automatically.

## **Who can change the app currency?**

Currency changes depend on your app's existing data:

- **Apps without revenue or cost:** You can change the currency directly.
- **Apps with revenue or cost:** Only an **AppsFlyer admin** can perform the change.

To request a currency change:

1. Contact your AppsFlyer representative or submit a support ticket.
2. Provide your app details.
3. Attach written approval acknowledging the impact on reporting.

## **How currency changes impact your data**

Changing your app currency impacts revenue data display and accuracy:

### Future data

Once the currency changes, all future events with the af\_revenue parameter use the new currency. Reports after the change will reflect this, but reports spanning the change date may show mixed currencies.

### Historical data accuracy

Historical data remains, but becomes inaccurate:

- Revenue events before the change remain in the old currency.
- Revenue events after the change use the new currency.
- This mixture causes inaccuracies in metrics like LTV and ROAS.

The impact varies:

- **Extensive revenue history:** Significant discrepancies.
- **Minimal revenue history:** Lesser impact.

### **Example**

### Reporting impacts

If you change your app currency on **October 1**, here's how revenue reporting methods are affected:

| **Reporting method** | **Before Oct 1** | **Spanning Oct 1** | **After Oct 1** |
| --- | --- | --- | --- |
| **LTV & Cohort (D0–180)** | Mixed currencies (inaccurate) | Mixed currencies (inaccurate) | Accurate |
| **Activity** | Shows previous currency | Mixed currencies (inaccurate) | Accurate |
| **SSOT** | Accurate up to 7 days before the change | Mixed currencies (inaccurate) | Accurate |

> ❗️ Important!
>
> - Currency changes are **permanent**.
> - Historical data **cannot be converted or restored**.
> - Confirm all implications with your AppsFlyer account manager before making changes.
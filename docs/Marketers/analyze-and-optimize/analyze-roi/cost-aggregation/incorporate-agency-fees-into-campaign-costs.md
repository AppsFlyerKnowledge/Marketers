---
title: "Incorporate agency fees into campaign costs"
excerpt: "Agency fee rules are part of the AppsFlyer ROI360 premium feature that enables advertisers to add the percentage fees agencies charge for traffic so they can see the total campaign cost."
x-zendesk:
  id: 4402103019665
  url: https://support.appsflyer.com/hc/en-us/articles/4402103019665-Incorporate-agency-fees-into-campaign-costs
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Cost aggregation
  section_id: 6551029483281
  position: 8
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-maytav-avnat, Marketers, Agencies, ROI360]
  labels: [Advertisers, Agencies, Premium, Xpend, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-06-03T13:53:23Z'
  edited_at: '2025-08-07T17:10:38Z'
---
## Overview

Agency fee rules are defined by the advertiser (with AppsFlyer account admin privileges) in the rule builder using customized conditions that add fee percentages to the cost of agency campaigns for specific apps and/or media sources.

ROI360 uses the agency fee rule to calculate the total ad cost with the fee, based on the ad network API and attribution link cost. The calculation applies at every granularity level (campaign, adset, etc.). The results are displayed in your dashboards, reports, and Cost ETL; not in the agency or ad network dashboards and reports. **Note**: Cost ETL reports have additional [fields for agency fees](/docs/set-up-and-use-roi360-cost-etl-reports#file-fields).

Agency rules help advertisers:

* Understand the real cost of their ad campaigns
* Save time and manual effort to report on cost data
* Manage agency performance
* Accurately analyze historical cost data

## Procedures

See the sections that follow for instructions for the view, add, edit, and delete rules. All procedures require AppsFlyer admin privileges.

### View rule list

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/90ad4b15e0e27f2043e3e6dc1dfaf0581add5e5df2122f95b235728fb140fa5c-4408750662545.png) To view all the agency fee rules created in your account**:

1. In AppsFlyer, from the side menu, select **Settings** > **Cost Control.**  
   The Cost Control screen displays the list of agency rules. Rules are categorized into the following possible statuses:
   * **Active:** The rule start date is today or earlier, and the rules have calculated fee data at least once.
   * **Inactive:** The rule end date is in the past (meaning before today).
   * **Scheduled:** There is data waiting to be processed. After creating a rule or editing the date/price, the rule is scheduled until it is processed and then it moves to Active or Inactive.
   * **Failed:** The rule is failing to calculate for technical reasons.
2. Filter the rules in the list using the filter options: Partner, App, and Media source.

### Add rule

The rule builder user interface is designed for interactive rule building. **Tip!** Familiarize and experiment with the rule builder before reviewing this article in detail.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/90ad4b15e0e27f2043e3e6dc1dfaf0581add5e5df2122f95b235728fb140fa5c-4408750662545.png) To add a new rule**:

1. In AppsFlyer, from the side menu, select **Settings** > **Cost Control.**
2. Click **+** **Add Agency fees rule**.  
   The Agency fees rule screen displays.
3. Select a partner (agency).
4. Choose one or more Apps or select **All apps**. If you select **All apps**, the rule applies to all your apps, including apps added to your account in the future.
5. Select one or more media sources or check All media sources. If you check All media sources, the rule applies to all media sources, including those added in the future.
   * If the agency you work with is non-transparent, the **All media sources** option is selected by default, and you cannot select a specific media source.
   * If your selected app is not transparent, the media source drop-down remains disabled, unless, the app selected in the drop-down contains Meta ads or X Ads, as these are always transparent.
6. Enter a start date.
7. [Optional] Enter an end date.
8. Enter the agency fee percentage fee. This can be a number between 100 and -100 (to reflect agency discounts or refunds).
9. Click **Create rule**.

> 📘 **Note**
>
> The following errors can prevent your rule from being created:
>
> * A mandatory field is not populated. To resolve, ensure that all the mandatory fields are populated.
> * The rule logic conflicts with an existing rule. To resolve, change the app, or media source.


### Edit, duplicate, or delete a rule

**Considerations:**

When you edit or delete a rule, previously calculated data (up to 90 days in the past) gets overwritten:

* For an edited rule, the total cost reflects the updated agency percentage fee.
* For a deleted rule, the agency fee is removed from the total cost.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/90ad4b15e0e27f2043e3e6dc1dfaf0581add5e5df2122f95b235728fb140fa5c-4408750662545.png) To edit, duplicate, or delete a rule**:

1. In the [rule list](/docs/incorporate-agency-fees-into-campaign-costs#view-rule-list), hover over the rule you want to edit, duplicate, or delete.
2. Click **Menu** ⋮ on the right side.
3. Select the action you want to perform.

> 📘 **Note**
>
> The agency and start date of a rule cannot be edited after the rule is created. If you need to change them, delete your old configuration, and create a new rule.


## Traits and limitations



| Trait | Remarks |
| --- | --- |
| Agencies and ad networks | Agencies and ad networks cannot view rules, or see the total ad cost data that results from agency fee rules in their dashboards and reports. |
| Data freshness | [Intraday](/docs/about-data-freshness-and-timezone-support#intraday-during-the-day). Initial calculations can take up to 5 hours to display. |
| Historical data | Rules can be created and impact data up to 90 days in the past. |
| Rule processing frequency | New agency fee rules are processed every **4 hours**. This means that a rule may take up to **4 hours** to apply. |



Traits and limitations
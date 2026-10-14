---
title: "Custom dimensions"
excerpt: "Define your own dimensions and use them to group and view data in the Overview dashboard."
x-zendesk:
  id: 15920604187921
  url: https://support.appsflyer.com/hc/en-us/articles/15920604187921-Custom-dimensions
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Dashboards
  section_id: 6550925337873
  position: 8
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-nohar-avigal, Marketers, Marketing Analytics]
  labels: [dashboard, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2023-06-06T09:28:20Z'
  edited_at: '2025-01-01T11:17:18Z'
---
![](https://fast.wistia.com/embed/medias/tvcdofnwjo/swatch)

## Overview

Custom dimensions let you use existing dimensions to create your own dimensions for data analytics relevant to your business purposes. These dimensions can be used in all widgets in the Overview dashboard to group data and help you gain deeper insights and make data-driven decisions that align with your business objectives.

The custom dimensions you create are at the account level, meaning different apps in the same AppsFlyer account can use the same custom dimensions.

### Benefits

* Tailored insights: Define and collect data specific to your business needs. By capturing additional information beyond the standard dimensions, you can gain deeper insights and a more comprehensive understanding of your data.
* Segmented analysis: Group and analyze your data based on specific relevant attributes or characteristics to get a more detailed view of user behavior, customer segments, or product performance.
* Enhanced reporting: Create custom dashboards and reports that align with your unique reporting requirements.
* Improved decision-making: By capturing custom dimensions that align with your business goals, you can make more informed decisions. Custom dimensions provide the necessary context to evaluate the impact of different variables and factors on your key performance indicators (KPIs), helping you identify trends, patterns, and opportunities for optimization.

### Example use cases

| Example use case | Description |
| --- | --- |
| Campaign intent | <ul><li>Based on your campaign names.</li><li>Select value names to differentiate your different campaign goals. For example: label a brand awareness as "brd" and a user acquisition campaign as "new" or "ua."</li><li>Include the value names in your campaign names. For example: "US\_Facebook\_BRD" or "UK\_Google\_new".</li><li>AppsFlyer parses the campaign name and groups data based on your labels.</li></ul> |
| Regions | <ul><li>Based on geos.</li><li>Group several geos/countries into regions. For example: Group USA, Canada, and Mexico into "North America," or use different geos to create groupings for Europe, APAC, etc.</li><li>AppsFlyer groups data based on your region values (North America, Europe, APAC, and so on).</li></ul> |
| Owned vs paid media | <ul><li>Based on media sources.</li><li>Group different media sources into "owned" and "paid." For example: Group SMS and Facebook post into the value "owned," and Facebook and Google into the value "paid."</li><li>AppsFlyer groups data from these media sources into the values "owned" and "paid," respectively.</li></ul> |
| Cities | <ul><li>Based on your campaign names.</li><li>Values include the cities you have specific campaigns for in your campaign names. For example: "US\_Facebook\_NY" for New York and "US\_Google\_SF" for San Francisco.</li><li>AppsFlyer parses the campaign name and groups data based on the cities.</li></ul> |
| UA manager | <ul><li>Based on media sources.</li><li>Group different media sources according to specific team members. For example: Group Google and Facebook campaigns into the value "Kevin" and TikTok and Instagram campaigns into the value "Natasha."</li><li>AppsFlyer groups data from these media sources into the values "Kevin" and "Natasha," respectively.</li></ul> |

## Procedures

<Accordion title="Create a custom dimension">

**To create a custom dimension**:

1. In the Overview dashboard, either:
   * Click the **Menu icon (⋮)** > **Custom dimensions**.  
     [![](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)
   * In any chart or table, in the **Show to**p or **Group by** dropdown menu, click **+ Create custom dimension**.
2. If this is your first time creating a custom dimension, click **+ New dimension**.  
   The **Create** tab opens.
3. Enter a name and description for your dimension. Choose name and description that will help you identify this custom dimension in dashboard grouping options.
4. Define the possible dimension values. There can be up to 10 values per dimension. For each value:
   1. Enter a value name.
      * Example: For a custom dimension called "campaign intent," values can be "branding" and "ua." See more example use cases.
   2. Define the rules for when the value name should be used. There can be up to 10 rules per value.
      * Each rule includes the existing dimension the value is based on, operators, and operator values.
      * Example: If campaign name includes "brd" or "brnd," the value name will be "branding." See more example use cases.
      * The following table shows the different components used in defining a dimension.

<table><thead><tr><th>Value name</th><th>Dimension (to base the value on)</th><th>Operator</th><th>Operator value</th></tr></thead><tbody><tr><td rowspan="3">You decide the possible value names for your custom dimension.</td><td>Media source</td><td rowspan="2">Select: <ul><li>Is</li><li>Contains</li><li>Starts with</li><li>Ends with</li></ul></td><td><ul><li>String</li><li>Dropdown selection (if operator is "is")</li></ul></td></tr><tr><td>Campaign name</td><td>String</td></tr><tr><td>Geo</td><td>Is </td><td>Dropdown selection</td></tr></tbody></table>

5. Click **Save**.

</Accordion>

<Accordion title="Delete or edit a custom dimension">

**To delete or edit a custom dimension**:

1. In the Overview dashboard, either:
   * Click the **Menu icon** > **Custom dimension**.  
     [![](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)
   * In any chart or table, in the **Show to**p or **Group by** dropdown menu, click **+ Create custom dimension**.
2. Click the **Edit** tab.
3. Select or search for a custom dimension.
4. To delete the dimension, click the **Delete** icon next to your selected dimension.
5. To edit the dimension, make any changes you want to your custom dimension settings, and click **Save**.

</Accordion>

<Accordion title="View custom dimension data">

Custom dimensions can be used to group and view data in all widgets in the Overview dashboard.

**To view custom dimension data**:

1. In the Overview dashboard, go to any chart or dashboard widget.
2. In the **Show top** or **Group by** dropdown menu, look under Custom dimensions for the custom dimension you want to use.  
   [![](https://files.readme.io/e34bcb2ca34546347b391f0ad921319f296a21c41c3783e59a7d808b44d0b6a9-17082706166929.png)](https://files.readme.io/e34bcb2ca34546347b391f0ad921319f296a21c41c3783e59a7d808b44d0b6a9-17082706166929.png)
3. The chart or table data is displayed in a grouping using your custom dimension

</Accordion>

<Accordion title="Specifications and limitations">

| Spec | Remarks |
| --- | --- |
| Custom dimensions | Up to 10 custom dimensions can be created. |
| Advertiser | Can't view or edit custom dimensions made by agencies. |
| Agencies | <ul><li>Can create and edit their own custom dimensions and view them in their dashboard.</li><li>Can't edit or view custom dimensions made by the advertiser.</li></ul> |
| Ad networks | Can't view, create, or edit custom dimensions. |
| SKAN metrics | When SSOT is off and data is grouped by a custom dimension, SKAN metrics don't display. |
| SSOT | When SSOT is on and data is grouped by a custom dimension based on geo, data doesn't display. |
| Permissions | Any team member can create new dimensions and edit existing dimensions, even if they were created by another team member. |
| Case sensitivity | No. Upper case and lowercase are treated the same. |
| Dimension values | <ul><li>There can be up to 10 custom dimension values.</li><li>When matching data to custom dimension values, priority is given to higher-ranked dimension values. Example:<ul><li>For Paid vs. owned media dimension, you set Value 1 to be paid media if media source is Facebook, and Value 2 to be owned media if media source is Facebook.</li><li>Facebook can be grouped into either paid or owned media based on your settings, but AppsFlyer gives priority to the Value 1 setting (paid).</li></ul></li></ul> |
| Operators | The operator "does not contain" isn't available yet. |
| Dimension rules | You can have up to 10 rules for a dimension value. These are connected with "or." The connector "and" isn't available yet. |

</Accordion>

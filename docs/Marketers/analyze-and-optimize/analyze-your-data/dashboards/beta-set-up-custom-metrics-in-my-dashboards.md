---
title: "[Beta] Set up custom metrics in My Dashboards"
excerpt: "Define your own metrics and use them to view data in My Dashboards."
x-zendesk:
  id: 31400289569169
  url: https://support.appsflyer.com/hc/en-us/articles/31400289569169--Beta-Set-up-custom-metrics-in-My-Dashboards
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Dashboards
  section_id: 6550925337873
  position: 3
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-maya-kahane, Marketers, Marketing Analytics]
  labels: [Marketers, Beta feature]
  promoted: false
  comments_disabled: true
  created_at: '2025-01-01T09:21:05Z'
  edited_at: '2026-08-19T10:32:26Z'
---
## About custom metrics

Custom metrics let you tailor data analysis to your unique business needs by defining calculations based on existing data. They provide more control and flexibility than standard metrics, enabling you to combine multiple metrics, create projections, and customize KPIs.

For example, instead of generic metrics like "Revenue" or "Clicks," you can create formulas for your unique uses cases, such as:

* Revenue D60 Prediction = Revenue D1 * 3
* Click-to-purchase rate = Clicks / af\_purchase [unique users]

Custom metrics are compatible with all widget types in My Dashboards, including tables, charts, and KPIs. Whether you're a marketer tracking campaign ROI, a product manager monitoring engagement, or an analyst forecasting performance, custom metrics enhance your ability to analyze trends, identify opportunities, and make data-driven decisions for your unique business needs—all directly from your dashboard.

**Note**: The custom metrics you create are at the account level, meaning different apps in the same AppsFlyer account can use the same custom metrics.

## Procedures

<div id="create-a-custom-metric" />

<Accordion title="Create a custom metric">

**To create a custom metric**:

1. In your dashboard, either:
   * Click **+ Create new** > **Custom metrics**.
   * In any chart or table, in the **Metrics** dropdown menu, click **+ Create custom metric**.
2. Name your metric. At the top of the custom metric editor, input a descriptive name for your metric (for example, "IPM").
3. Choose a **Metric type**. Select whether the metric is numeric, a percentage, or monetary (currency).
4. Define your metric formula. Either:
   * Get started quickly: Use suggested formulas (displayed in the left-side menu of the custom metric editor). Then use the editor to edit the template to fit your specific needs, such as selecting different in-app events or modifying multipliers or other parameters. For example, for the template `Retention rate D2 / Retention rate D7`, you can replace D2 and D7 with different events or time periods.
   * Use the interactive editor: Add metrics and operators (using the buttons), and numbers (using your keyboard) to define your formula.
5. Preview the formula in the fx formula field.
6. [Optional] If you created the custom metric from within the general dashboard, click **Save and add to chart**.  
   A new chart is created that includes your custom metric.
7. Click **Save**.
   * If you created the custom metric from within a widget, it's automatically added to the chart or table.
   * If you created the custom metric in the general dashboard, you can now add it to any widgets you want.

</Accordion>

<div id="edit-a-custom-metric" />

<Accordion title="Edit a custom metric">

You can edit a custom metric either from the dashboard or from within a specific widget. **Note**! Any changes you make to a custom metric are account-level, meaning the changes affect the metric for all users and dashboards.

**To edit a custom metric from the dashboard**:

1. In your dashboard, click **+ Create new** > **Custom metrics**.
2. In the custom metric editor's left-side menu, under My custom metrics, find the metric you want to edit and click the **Edit** icon.
3. Make any changes you want to the custom metric formula.
4. Click **Save**.

**To edit a custom metric from a widget**:

1. In any chart or table, in the **Metrics** dropdown menu, find the metric you want to edit and click the **Edit** icon.
2. In the custom metric editor's left-side menu, under My custom metrics, find the metric you want to edit and click the **Edit** icon.
3. Make any changes you want to the custom metric formula.
4. Click **Save**.

</Accordion>

<div id="delete-a-custom-metric" />

<Accordion title="Delete a custom metric">

You can delete a custom metric either from the dashboard or from within a specific widget. **Note**! Any deletions to a custom metric are account-level, meaning the metric is removed for all users and dashboards.

**To delete a custom metric from the dashboard**:

1. In your dashboard, click **+ Create new** > **Custom metrics**.
2. In the custom metric editor's left-side menu, under My custom metrics, find the metric you want to delete and click the **Delete** icon.

**To delete a custom metric from a widget**:

* In any chart or table, in the **Metrics** dropdown menu, find the metric you want to delete and click the **Delete** icon.

</Accordion>

## Additional information

<div id="best-practices" />

<Accordion title="Best practices">

* **Start simple**: Begin with basic metrics and progressively add complexity as needed and as you become more familiar with formula development.
* **Align with goals**: Ensure each metric ties back to a specific business objective or question.
* **Document your formulas**: Keep a reference of your custom formulas for easy updates or debugging.
* **Review periodically**: Regularly assess your metrics to ensure they remain relevant.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Account-level accessibility | All account members can create, view, edit, and delete any custom metric. This includes metrics created by other users. |
| Custom metrics | <ul><li>Custom metrics have a cap of 100 custom metrics per account.</li><li>Custom metrics are currently supported only with daily time breakdown. Weekly and monthly breakdowns are not supported.</li></ul> |
| Formula complexity | Maximum 5 metrics per custom metric formula. |
| Nesting restriction | Custom metrics can't be used as components in other custom metric formulas. |

</Accordion>

<div data-zendesk-anchors="h_01H8XWQHPERAEDQVD275TFVC5B=about-custom-metrics h_01H8XWQHPESY4DDDJSTR0JDHNB=procedures h_01H8XWQHPEDYVDQQV3P8EDARAY=create-a-custom-metric h_01H8XWQHPE22WZ46RTNCYKX96F=edit-a-custom-metric h_01H8XWQHPED4PFPJP2044FT1H8=delete-a-custom-metric 01JGGT56V05BJRCV9Q572JJR3W=additional-information 01JGK1XAVB3M5KDA59A9ZASM2K=best-practices h_01H8XWQHPF7WZ7B5Q7T9CHADRK=traits-and-limitations" />

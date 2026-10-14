---
title: "[Closed beta] Use AI Predictive Audiences to reach high-intent users"
excerpt: "Predictive Audiences uses AI to create an audience of users most likely to take a key action, such as purchasing, so you can reach high-intent users, reduce wasted spend, and maximize campaign impact."
x-zendesk:
  id: 45762246838801
  url: https://support.appsflyer.com/hc/en-us/articles/45762246838801--Closed-beta-Use-AI-Predictive-Audiences-to-reach-high-intent-users
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Audiences
  section_id: 6551336428945
  position: 2
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-neama-benhabib, Marketers, Audience Segmentation]
  labels: [Premium, Beta, Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2026-04-15T09:20:36Z'
  edited_at: '2026-04-27T10:30:56Z'
---
<Embed title="[Closed beta] Use AI Predictive Audiences to reach high-intent users" typeOfEmbed="youtube" url="https://www.youtube.com/embed/LuEJrfARo5g" providerUrl="https://www.youtube.com" />

## About Predictive Audiences

Predictive Audiences, part of AppsFlyer [Audiences](/docs/audiences-guide), helps you create AI-powered audiences of users most likely to take a key action. Use it to predict who is most likely to purchase within the next 7 days, so you can focus your campaigns on high-intent users and improve campaign efficiency.

You can adjust the likelihood range to create a narrower audience of higher-intent users or a broader audience with greater reach, then connect the audience to your partners for activation. Once created, the audience refreshes daily and is automatically and continuously sent to your connected partners.

## Create a predictive audience

### Prerequisites

To get started using Predictive Audiences, follow the steps below:

* **Prerequisite:** An AppsFlyer [Audiences](/docs/audiences-guide) subscription. Predictive Audiences is currently in beta and is enabled per account. To gain access, contact your CSM.

<Accordion title="Step 1: Define the goal">

In this step, you define what you want Predictive Audiences to predict by selecting the app, target event, and prediction goal for the audience.

**To define the goal:**

1. Access Audiences by clicking **Engage > Audiences** in the AppsFlyer side menu.
2. In **Audiences**, click **New predictive audience**.
3. Enter an audience name.

   [![Define goal (values entered).png](https://files.readme.io/9dd260c4552be231e2f313db451d92501b6090664e6f7010c660357f9af71efb-45796747476497.png)](https://files.readme.io/9dd260c4552be231e2f313db451d92501b6090664e6f7010c660357f9af71efb-45796747476497.png)
4. Select an app.
5. Select a target event.
6. Select a prediction goal (**Likely to purchase**).
7. Click **Continue**.

</Accordion>

<Accordion title="Step 2: Set the probability range">

In this step, you set the probability range to balance precision and reach. Higher minimum thresholds create smaller, higher-intent audiences, while lower minimum thresholds expand reach while maintaining high performance.

You can select a suggested preset or drag the chart markers to customize the range. As you adjust it, the estimated audience size updates in real time, helping you understand the trade-off between scale and conversion likelihood.

**To set the probability range:**

1. Choose a preset (**High intent**, **Balanced**, or **Maximum reach**) to set a default range. We recommend selecting **Balanced**.

**Or**

2. To customize the range, drag the minimum and maximum markers on the graph.

   ![Set probability range Correct version.png](https://files.readme.io/8dd9b6368d86e5641e99e7fe66e137b1137adf8fdf7760d597826f7c2d5be745-45796825322385.png)

   The **Estimated audience size** updates in real time based on your selections.

#### Compare audiences (optional):

Compare Audiences is an optional feature that lets you compare your predictive audience with one or more existing audiences. It allows you to compare performance across key indicators (KPIs), such as return on ad spend (ROAS) and conversion rate. You can select any audience to compare; however, performance data is currently available only for campaigns connected to Facebook, TikTok, Google, or Snap.

</Accordion>

<Accordion title="Step 3: Connect to partners">

In this step, you connect the predictive audience to your partners so it can be activated and uploaded upon creation.

**To connect to partners and activate the audience:**

1. Select existing partner connections or add a new connection.

   [![Connect to partners.png](https://files.readme.io/3fd67bfe6d3fd760ad1569c8e0b360432f7874d152804cbef9a4925189837e0c-45796884976401.png)](https://files.readme.io/3fd67bfe6d3fd760ad1569c8e0b360432f7874d152804cbef9a4925189837e0c-45796884976401.png)
2. Review your selections in the **Summary** on the right.
3. Click **Connect and finish**.

Your first predictive audience will be ready within 24 hours and automatically activated with your partners.

After creation, your new predictive audience will appear in the **Audiences** table.

</Accordion>

## Traits and limitations

| Trait | Description |
| --- | --- |
| Availability | Beta feature enabled per account and requires explicit opt-in. Available currently for ecommerce apps only. |
| Prediction window | Predicts the likelihood of purchase within 7 days. |
| One app per audience | Multi-app predictive audiences aren’t supported. |
| Eligibility-based selection & data limitations | Only eligible apps and events with a minimum amount of data will appear in selection drop-downs (e.g., 1000 active users in the last 30 days). |
| Data protection | Your audience data may be processed to support AI-powered Audiences capabilities. Your account data is never shared and is used only to improve internal models and predictions. |
| Daily refresh | The audience is refreshed and uploaded to partners daily. |
---
title: "Understand Incrementality for remarketing experiment alerts"
excerpt: "Understand alerts and get them resolved, to ensure accurate experiment results."
x-zendesk:
  id: 13479545385489
  url: https://support.appsflyer.com/hc/en-us/articles/13479545385489-Understand-Incrementality-for-remarketing-experiment-alerts
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Incrementality for remarketing
  section_id: 6551378485649
  position: 2
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-niv-klein, Marketers, Incrementality]
  labels: [Premium Feature, Marketers, Incrementality]
  promoted: false
  comments_disabled: true
  created_at: '2023-03-05T12:31:35Z'
  edited_at: '2025-07-06T10:54:14Z'
---
<Image src="https://files.readme.io/3981e4a4bd66206d9b5986cc1b573f67e1ab836042a1f73518f48a1ea17b6568-35266706078481.jpg" alt="Incrementality experiment alerts dashboard interface" />

## About experiment alerts

Once you've [set up an Incrementality experiment](/docs/run-an-incrementality-for-remarketing-experiment), you may come across alerts on the Incrementality dashboard. These alerts are designed to help you identify issues that can compromise the integrity and accuracy of your experiment results. They provide specific information about problems and suggest actions that can be taken to address them, to ensure accurate experiment results. This article provides a comprehensive overview of the different types of alerts, as well as the recommended actions for getting the issues resolved.

## Alert types

Experiment alerts fall into the following categories:

### Experiment setup

#### Audience deletion or control group removal

Experiments whose connected audiences have been deleted or whose split audience control group has been removed. In both these scenarios, a 404 error will appear when visiting the experiment page.

**To resolve this and restore the experiment results:**

If the **audience was deleted** - Please contact your CSM who will have it restored manually.

If the **control group was removed** - Please split the audience again and set the control group to the exact same percentage as it was before removal.

#### More suitable campaign? (SRNs only)

This alert is relevant to Self Reporting Networks (SRNs) only. This alert appears when a campaign is connected to an experiment but data indicates that there's a campaign that may be better suited for targeting the audience.

A "more suitable campaign" is a campaign, currently active during the experiment time frame, that targets the test group in a more substantial way than the configured campaign (and doesn't target the control group).

**Actions to take:** Check if the right campaign is linked.

> 📘 Note
>
> It's also a good idea to make sure the audience is not included as part of the targeting configuration of other campaigns.

#### No impressions (Non-SRNs only)

When Incrementality experiments are done on campaigns run on non-SRN ad networks, AppsFlyer requires user impressions in order to most accurately calculate the incremental impact of those campaigns. Without impressions, the results will simply not display on the experiment page.

This alert describes a situation in which for some reason we're not receiving impressions data for the connected campaign.

**Actions to take:** Check that you are receiving impressions from the media partner and that the tested campaign is working and delivering ads.

### Experiment background environment

#### Background campaign (one or multiple)

This alert appears when there are unrelated, very large campaigns that have a much bigger impact on the audience than the configured campaign in the experiment.

How can this happen?

It's not unusual for unrelated campaigns to exist in the background, but if those campaigns have a bigger budget or operate more intensely, they can overshadow the configured campaign—and subsequently affect the results of the experiment.

**Actions to take:**

* Increase the impact of your campaign by raising the budget.
* Check whether the tested audience overlaps with the audience targeted by the background campaign (can be checked with the Audiences partner overlap feature).
* Check whether the tested audience overlaps with the unrelated background campaign.
* Tighten the tested audience segmentation.
* If actions were taken to minimize the impact of background campaigns, set the experiment start date to after these changes were made.

> 📘 Note
>
> It is best practice to minimize the targeting of the tested audience with other campaigns.

### Linked campaign performance

#### Audience overlap

The connected campaign is targeting overlapping audiences. This means that the linked campaign's targeting configuration contains more than one audience.

Additionally, the multiple audiences in the tested campaign configuration overlap. This will result in targeting outside of the tested audience, including targeting the control group of the tested audience.

**Actions to take:**

Update the campaign's targeting to include the tested audience only and remove any additional audiences.

#### Control group is targeted

This warning indicates that the configured campaign is targeting the control group although it's only supposed to target the test group.

**How can this happen?**

* The experiment was linked to the wrong campaign.
* The campaign on the media partner side was configured to target users outside of the audience (learn about [audience expansion features](/docs/run-an-incrementality-for-remarketing-experiment#check-for-audience-expansion-features) in Facebook and Google).
* Network not enforcing the targeting configuration.

**Actions to take:**

Please check the common scenarios listed above, and contact your CSM if unsure. In certain cases, depending on the significance of the exposure to the campaign by the control group users, there isn't a fix for this, and a new Incrementality experiment should be created.

If the breach is relatively small, it's enough to make sure the control group targeting has stopped. Track the warning in the experiment’s UI and check to see if the alert still appears after a few days.

#### Detailed targeting toggle is enabled

Detailed targeting is a feature on certain ad networks that lets you fine-tune who sees your ads. This alert will appear if the campaign’s detailed targeting toggle is enabled. When enabled it will allow the campaign to target outside of the configured audience.

**Actions to take:** Verify that the detailed targeting toggle is off on the partner-side campaign configuration.

#### Low activity

The campaign is not delivering ads or is delivering very few ads to the targeted audience.

**Actions to take:** Investigate the problem on the media partner side to understand why the campaign isn't delivering ads.

#### Multiple audiences connected

The campaign’s targeting configuration includes multiple audiences. This may lead to targeting outside the tested audience, or the control group, ultimately impacting the test results.

**Actions to take:**

A best practice for Incrementality testing is that the tested campaign should target only one audience.

#### Out-of-audience targeting

The tested campaign is also targeting users outside of the targeted audience test group. Part of the campaign's cost is being spent delivering ads to those unrelated to the tested audience users, and who are not taken into consideration in the Incrementality test.

Therefore, when spending money on unrelated users, metrics that involve the cost of the campaign such as iROAS \& CPiA will be biased. They will take into account the entire campaign cost, including the cost it took to present ads to users outside of the audience, but it will not count their conversions.

**How can this happen?**

* The experiment was linked to the wrong campaign.
* The campaign on the media partner side was configured to target users outside of the audience (learn about [audience expansion features](/docs/run-an-incrementality-for-remarketing-experiment#check-for-audience-expansion-features) in Facebook and Google).
* Network not enforcing the targeting configuration.

**Actions to take:**

Make sure the campaign's targeting configuration contains only the tested audience and that the campaign's configuration doesn't allow the campaign to target outside of the audience.
---
title: "Data collaboration platform (DCP) - Determine your collaboration measurement use case"
excerpt: "Identify your collaboration scenario, making sure you know what data to provide, who is responsible for it, and in what format to submit it."
x-zendesk:
  id: 32964487756561
  url: https://support.appsflyer.com/hc/en-us/articles/32964487756561-Data-collaboration-platform-DCP-Determine-your-collaboration-measurement-use-case
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Collaboration measurement
  section_id: 38034865098641
  position: 1
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-yael-sharabi, Marketers, Data Management]
  labels: [Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2025-02-25T15:52:06Z'
  edited_at: '2026-05-04T09:20:22Z'
---
## Overview

DCP supports a variety of on-site and off-site use cases. Each use case requires a different setup, specifying which collaborator is responsible for preparing each data source and the format in which the data should be configured.

This article aims to help Commerce Media Networks (CMNs) and advertisers (brands) identify which use case applies to them. Once the appropriate use case is determined, the collaboration owner can assign the necessary preparation and configuration tasks to the relevant collaborators (For more information about task assignment, see: [Assign configuration task](/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configuration-task-assignment).)

This is where the use case decision tree comes into play. It serves as a structured guide to help you specify your use case and receive the corresponding preparation instructions.

## How does the decision tree help?

Depending on the setup, one collaborator may need to prepare and configure the conversions and campaigns tasks, while the other may be responsible for preparing the engagements or media partners tasks. The decision tree helps the collaboration owner determine which collaborator should be assigned each task and provides links to the corresponding instructions.

### Which decision tree do I need: On-site or Off-site?

You can use two decision trees: one for on-site campaigns and the other for off-site use campaigns. To determine which decision tree is appropriate, consider where the **ad is served** and where the **conversion occurs**.

* Use the [off-site campaign decision tree](#the-off-site-campaign-decision-tree) if the ad is displayed on an external advertising platform (for example, Facebook, Google) outside of your owned and operated properties.
* Use the [on-site campaign decision tree](#the-on-site-campaign-decision-tree) if the ad is served within your ecosystem and the conversion takes place on your platform.

## The on-site campaign decision tree

In the on-site campaign scenario, the conversion takes place on a platform owned and operated by the CMN or the advertiser. This leads to the initial question in the on-site decision tree: On which platform does the conversion take place — the CMN’s or the advertiser’s?

Answer the initial question by choosing the correct answer, and continue to expand the branches that correspond to your specific conditions.

#### **On which platform does the conversion take place?**

<Accordion title="The conversions take place on the CMN platform">

<Accordion title="The CMN platform is an app">

If the CMN platform is an app, follow the instructions below for each data type:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Campaigns | CMN | <ul><li>[Campaign source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Conversions | CMN | <ul><li>[Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li><li>[Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Engagements | CMN | <ul><li>[Engagement source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme)</li><li>[Engagement in-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events)</li></ul> | <ul><li>[Engagements task configuration](/docs/set-up-the-engagements-task)</li></ul> |
| Lookback windows | CMN/Advertiser | Not relevant | <ul><li>[Lookback windows task configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

**OR**

<Accordion title="The CMN platform is a website">

If the CMN platform is a website, follow the instructions below for each data type:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Campaigns | CMN | <ul><li>[Campaign source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Conversions | CMN | <ul><li>[Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Engagements | CMN | <ul><li>[Engagement source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme)</li></ul> | <ul><li>[Engagements task configuration](/docs/set-up-the-engagements-task)</li></ul> |
| Lookback windows | CMN/Advertiser | Not relevant | <ul><li>[Lookback windows task configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

</Accordion>

**OR**

<Accordion title="The conversions take place on the advertiser platform">

<Accordion title="The advertiser platform is an app">

If the advertiser platform is an app, follow the instructions below for each data type:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Campaigns | Advertiser | <ul><li>[Campaign source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Conversions | Advertiser | <ul><li>[Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li><li>[Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Engagements | CMN | <ul><li>[Engagement source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme)</li><li>[Engagement in-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events)</li></ul> | <ul><li>[Engagements task configuration](/docs/set-up-the-engagements-task)</li></ul> |
| Lookback windows | CMN/Advertiser | Not relevant | <ul><li>[Lookback windows task configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

**OR**

<Accordion title="The advertiser platform is a website">

If the advertiser platform is a website, follow the instructions below for each data type:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Campaigns | Advertiser | <ul><li>[Campaign source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Conversions | Advertiser | <ul><li>[Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Engagements | CMN | <ul><li>[Engagement source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme)</li></ul> | <ul><li>[Engagements task configuration](/docs/set-up-the-engagements-task)</li></ul> |
| Lookback windows | CMN/Advertiser | Not relevant | <ul><li>[Lookback windows task configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

</Accordion>

## The off-site campaign decision tree

In the off-site campaign scenario, the ad is displayed on an external advertising platform such as Facebook or Google. This leads to the initial question in the off-site decision tree: Which account on the external advertising platform is used to display the ad—the CMN’s or the advertiser’s?

Answer the initial question by choosing the correct answer, and continue to expand the branches that correspond to your specific conditions.

#### **Which account on the external platform displays the ad?**

<Accordion title="The CMN external-platform account displays the ad">

<Accordion title="The conversions take place on the CMN platform">

<Accordion title="The CMN platform is an app">

If the CMN platform is an app, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | CMN | <ul><li>[Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li><li>[Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Campaigns | CMN | <ul><li>[Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Media partners | CMN | Not relevant | <ul><li>[Media partners task configuration](/docs/set-up-the-media-partners-task)</li></ul> |
| Lookback windows | CMN/Advertiser | Not relavant | <ul><li>[Loookback windows configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

**OR**

<Accordion title="The CMN platform is a website">

If the CMN platform is a website, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | CMN | <ul><li>[Conversion source (custom)](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Campaigns | CMN | <ul><li>[Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Media partners | CMN | Not relevant | <ul><li>[Media partners task configuration](/docs/set-up-the-media-partners-task)</li></ul> |
| Lookback windows | CMN/Advertiser | Not relevant | <ul><li>[Loookback windows configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

</Accordion>

**OR**

<Accordion title="The conversions take place on the advertiser platform">

<Accordion title="The advertiser platform is an app">

If the advertiser platform is an app, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | Advertiser | <ul><li>[Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li><li>[Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Campaigns | Advertiser | <ul><li>[Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Media partners | CMN | Not relevant | <ul><li>[Media partners task configuration](/docs/set-up-the-media-partners-task)</li></ul> |
| Lookback windows | CMN/Advertiser | Not relavant | <ul><li>[Loookback windows configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

**OR**

<Accordion title="The advertiser platform is a website">

If the advertiser platform is a website, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | Advertiser | <ul><li>[Conversion source (custom)](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Campaigns | Advertiser | <ul><li>[Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Media partners | CMN | Not relevant | <ul><li>[Media partners task configuration](/docs/set-up-the-media-partners-task)</li></ul> |
| Lookback windows | CMN/Advertiser | Not relavant | <ul><li>[Loookback windows configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

</Accordion>

</Accordion>

**OR**

<Accordion title="The Advertiser external-platform account displays the ad">

<Accordion title="The conversions take place on the CMN platform">

<Accordion title="The CMN platform is an app">

If the CMN platform is an app, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | CMN | <ul><li>[Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li><li>[Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Campaigns | CMN | <ul><li>[Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Media partners | Advertiser | Not relevant | <ul><li>[Media partners task configuration](/docs/set-up-the-media-partners-task)</li></ul> |
| Lookback windows | CMN/Advertiser | Not relavant | <ul><li>[Loookback windows configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

**OR**

<Accordion title="The CMN platform is a website">

If the CMN platform is a website, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | CMN | <ul><li>[Conversion source (custom)](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Campaigns | CMN | <ul><li>[Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Media partners | Advertiser | Not relevant | <ul><li>[Media partners task configuration](/docs/set-up-the-media-partners-task)</li></ul> |
| Lookback windows | CMN | Not relavant | <ul><li>[Loookback windows configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

</Accordion>

**OR**

<Accordion title="The conversions take place on the advertiser platform">

<Accordion title="The advertiser platform is an app">

If the advertiser platform is an app, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | Advertiser | <ul><li>[Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li><li>[Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Campaigns | Advertiser | <ul><li>[Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Media partners | Advertiser | Not relevant | <ul><li>[Media partners task configuration](/docs/set-up-the-media-partners-task)</li></ul> |
| Lookback windows | CMN | Not relavant | <ul><li>[Loookback windows configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

**OR**

<Accordion title="The advertiser platform is a website">

If the advertiser platform is a website, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | Advertiser | <ul><li>[Conversion source (custom)](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)</li></ul> | <ul><li>[On-site Conversions task configuration](/docs/set-up-the-conversions-task#set-up-on-site-campaign-conversions)</li></ul> |
| Campaigns | Advertiser | <ul><li>[Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source)</li></ul> | <ul><li>[Campaigns task configuration](/docs/set-up-the-campaigns-task)</li></ul> |
| Media partners | Advertiser | Not relevant | <ul><li>[Media partners task configuration](/docs/set-up-the-media-partners-task)</li></ul> |
| Lookback windows | CMN | Not relavant | <ul><li>[Loookback windows configuration](/docs/set-up-the-lookback-windows-task)</li></ul> |

</Accordion>

</Accordion>

</Accordion>

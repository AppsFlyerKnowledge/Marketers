---
title: "Data collaboration platform (DCP) - Determine your collaboration measurement use case"
excerpt: "Identify your collaboration scenario to determine what data to provide, who is responsible for it, and in what format to submit it."
---
**At a glance:** Identify your collaboration scenario, making sure you know what data to provide, who is responsible for it, and in what format to submit it.

## Overview

DCP supports a variety of on-site and off-site use cases. Each use case requires a different setup, specifying which collaborator is responsible for preparing each data source and the format in which the data should be configured.

This article aims to help Commerce Media Networks (CMNs) and advertisers (brands) identify which use case applies to them. Once the appropriate use case is determined, the collaboration owner can assign the necessary preparation and configuration tasks to the relevant collaborators (For more information about task assignment, see: [Assign configuration task](/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configuration-task-assignment).)

This is where the use case decision tree comes into play. It serves as a structured guide to help you specify your use case and receive the corresponding preparation instructions.

## How does the decision tree help?

Depending on the setup, one collaborator may need to prepare and configure the conversions and campaigns tasks, while the other may be responsible for preparing the engagements or media partners tasks. The decision tree helps the collaboration owner determine which collaborator should be assigned each task and provides links to the corresponding instructions.

### Which decision tree do I need: On-site or Off-site?

You can use two decision trees: one for on-site campaigns and the other for off-site use campaigns. To determine which decision tree is appropriate, consider where the **ad is served** and where the **conversion occurs**.

* Use the [off-site campaign decision tree](#the-off-site-campaign-decision-tree) if the ad is displayed on an external advertising platform (for example, Facebook, Google) outside of your owned and operated properties.
* Use the [on-site campaign decision tree](#the-on-site-campaign-decision-tree) if the ad is served within your ecosystem and the conversion takes place on your platform.

## The on-site campaign decision tree

In the on-site campaign scenario, the conversion takes place on a platform owned and operated by the CMN or the advertiser. This leads to the initial question in the on-site decision tree: On which platform does the conversion take place — the CMN’s or the advertiser’s?

Answer the initial question by choosing the correct answer, and continue to expand the branches that correspond to your specific conditions.

#### **On which platform does the conversion take place?**

<Tabs>
<Tab title="The conversions take place on the CMN platform">

##### The CMN platform is an app

If the CMN platform is an app, follow the instructions below for each data type:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Campaigns | CMN | - [Campaign source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Conversions | CMN | - [Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)<br>- [Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Engagements | CMN | - [Engagement source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme)<br>- [Engagement in-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events) | - [Engagements task configuration](https://support.appsflyer.com/hc/articles/38188042548113-Set-Engagements-task) |
| Lookback windows | CMN/Advertiser | Not relevant | - [Lookback windows task configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

##### The CMN platform is a website

If the CMN platform is a website, follow the instructions below for each data type:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Campaigns | CMN | - [Campaign source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Conversions | CMN | - [Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Engagements | CMN | - [Engagement source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme) | - [Engagements task configuration](https://support.appsflyer.com/hc/articles/38188042548113-Set-Engagements-task) |
| Lookback windows | CMN/Advertiser | Not relevant | - [Lookback windows task configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

</Tab>
<Tab title="The conversions take place on the advertiser platform">

##### The advertiser platform is an app

If the advertiser platform is an app, follow the instructions below for each data type:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Campaigns | Advertiser | - [Campaign source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Conversions | Advertiser | - [Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)<br>- [Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Engagements | CMN | - [Engagement source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme)<br>- [Engagement in-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events) | - [Engagements task configuration](https://support.appsflyer.com/hc/articles/38188042548113-Set-Engagements-task) |
| Lookback windows | CMN/Advertiser | Not relevant | - [Lookback windows task configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

##### The advertiser platform is a website

If the advertiser platform is a website, follow the instructions below for each data type:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Campaigns | Advertiser | - [Campaign source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Conversions | Advertiser | - [Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Engagements | CMN | - [Engagement source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme) | - [Engagements task configuration](https://support.appsflyer.com/hc/articles/38188042548113-Set-Engagements-task) |
| Lookback windows | CMN/Advertiser | Not relevant | - [Lookback windows task configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

</Tab>
</Tabs>

## The off-site campaign decision tree

In the off-site campaign scenario, the ad is displayed on an external advertising platform such as Facebook or Google. This leads to the initial question in the off-site decision tree: Which account on the external advertising platform is used to display the ad—the CMN’s or the advertiser’s?

Answer the initial question by choosing the correct answer, and continue to expand the branches that correspond to your specific conditions.

#### **Which account on the external platform displays the ad?**

<Tabs>
<Tab title="The CMN external-platform account displays the ad">

##### The conversions take place on the CMN platform

###### The CMN platform is an app

If the CMN platform is an app, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | CMN | - [Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)<br>- [Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Campaigns | CMN | - [Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Media partners | CMN | Not relevant | - [Media partners task configuration](https://support.appsflyer.com/hc/articles/38191067035153-Set-Media-partners-task) |
| Lookback windows | CMN/Advertiser | Not relevant | - [Lookback windows configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

###### The CMN platform is a website

If the CMN platform is a website, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | CMN | - [Conversion source (custom)](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Campaigns | CMN | - [Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Media partners | CMN | Not relevant | - [Media partners task configuration](https://support.appsflyer.com/hc/articles/38191067035153-Set-Media-partners-task) |
| Lookback windows | CMN/Advertiser | Not relevant | - [Lookback windows configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

##### The conversions take place on the advertiser platform

###### The advertiser platform is an app

If the advertiser platform is an app, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | Advertiser | - [Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)<br>- [Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Campaigns | Advertiser | - [Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Media partners | CMN | Not relevant | - [Media partners task configuration](https://support.appsflyer.com/hc/articles/38191067035153-Set-Media-partners-task) |
| Lookback windows | CMN/Advertiser | Not relevant | - [Lookback windows configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

###### The advertiser platform is a website

If the advertiser platform is a website, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | Advertiser | - [Conversion source (custom)](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Campaigns | Advertiser | - [Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Media partners | CMN | Not relevant | - [Media partners task configuration](https://support.appsflyer.com/hc/articles/38191067035153-Set-Media-partners-task) |
| Lookback windows | CMN/Advertiser | Not relevant | - [Lookback windows configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

</Tab>
<Tab title="The Advertiser external-platform account displays the ad">

##### The conversions take place on the CMN platform

###### The CMN platform is an app

If the CMN platform is an app, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | CMN | - [Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)<br>- [Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Campaigns | CMN | - [Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Media partners | Advertiser | Not relevant | - [Media partners task configuration](https://support.appsflyer.com/hc/articles/38191067035153-Set-Media-partners-task) |
| Lookback windows | CMN/Advertiser | Not relevant | - [Lookback windows configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

###### The CMN platform is a website

If the CMN platform is a website, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | CMN | - [Conversion source (custom)](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Campaigns | CMN | - [Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Media partners | Advertiser | Not relevant | - [Media partners task configuration](https://support.appsflyer.com/hc/articles/38191067035153-Set-Media-partners-task) |
| Lookback windows | CMN | Not relevant | - [Lookback windows configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

##### The conversions take place on the advertiser platform

###### The advertiser platform is an app

If the advertiser platform is an app, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | Advertiser | - [Conversion source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme)<br>- [Conversion In-app event](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Campaigns | Advertiser | - [Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Media partners | Advertiser | Not relevant | - [Media partners task configuration](https://support.appsflyer.com/hc/articles/38191067035153-Set-Media-partners-task) |
| Lookback windows | CMN | Not relevant | - [Lookback windows configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

###### The advertiser platform is a website

If the advertiser platform is a website, follow the instructions below for each task:

| Task | Prepared and configured by | Learn how to prepare | Learn how to configure |
| --- | --- | --- | --- |
| Conversions | Advertiser | - [Conversion source (custom)](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme) | - [On-site Conversions task configuration](https://support.appsflyer.com/hc/articles/38187770114449-Set-the-Conversions-task#set-up-onsite-campaign-conversions) |
| Campaigns | Advertiser | - [Campaign mapping source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source) | - [Campaigns task configuration](https://support.appsflyer.com/hc/articles/38190881693969-Set-Campaigns-task) |
| Media partners | Advertiser | Not relevant | - [Media partners task configuration](https://support.appsflyer.com/hc/articles/38191067035153-Set-Media-partners-task) |
| Lookback windows | CMN | Not relevant | - [Lookback windows configuration](https://support.appsflyer.com/hc/articles/38191154658193-Set-Lookback-windows-task) |

</Tab>
</Tabs>
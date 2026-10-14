---
title: >-
  Data collaboration platform (DCP) - Determine your collaboration measurement
  use case
excerpt: >-
  Identify your collaboration scenario, making sure you know what data to
  provide, who is responsible for it, and in what format to submit it.
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2025-02-25T15:52:06Z'
  edited_at: '2026-05-04T09:20:22Z'
  id: 32964487756561
  locale: en-us
  section: Collaboration measurement
  section_id: 38034865098641
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/32964487756561-Data-collaboration-platform-DCP-Determine-your-collaboration-measurement-use-case
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

<div id="the-conversions-take-place-on-the-cmn-platform" />

<Accordion title="The conversions take place on the CMN platform">

<div id="the-cmn-platform-is-an-app" />

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

<div id="the-cmn-platform-is-a-website" />

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

<div id="the-conversions-take-place-on-the-advertiser-platform" />

<Accordion title="The conversions take place on the advertiser platform">

<div id="the-advertiser-platform-is-an-app" />

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

<div id="the-advertiser-platform-is-a-website" />

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

<div id="the-cmn-external-platform-account" />

<Accordion title="The CMN external-platform account displays the ad">

<div id="the-conversions-take-place-on-the-cmn-platform::e7b94fc0" />

<Accordion title="The conversions take place on the CMN platform">

<div id="the-cmn-platform-is-an-app::76ead17" />

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

<div id="the-cmn-platform-is-a-website::5144f168" />

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

<div id="the-conversions-take-place-on-the-advertiser-platform::aa9e89bf" />

<Accordion title="The conversions take place on the advertiser platform">

<div id="the-advertiser-platform-is-an-app::d36436f5" />

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

<div id="the-advertiser-platform-is-a-website::b70163fb" />

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

<div id="the-advertisers-external-platform-account" />

<Accordion title="The Advertiser external-platform account displays the ad">

<div id="the-conversions-take-place-on-the-cmn-platform::7b0781d3" />

<Accordion title="The conversions take place on the CMN platform">

<div id="the-cmn-platform-is-an-app::413a6003" />

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

<div id="the-cmn-platform-is-a-website::95667666" />

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

<div id="the-conversions-take-place-on-the-advertiser-platform::51470bc6" />

<Accordion title="The conversions take place on the advertiser platform">

<div id="h_01K3BAV1SP7RWP7K9TM7Y6MJVX" />

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

<div id="the-advertiser-platform-is-a-website::8cb255ef" />

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

<div data-zendesk-anchors="h_01JSKXR18RP691PT3Y5JGAJKF8=overview h_01K3JR6NJ906S2HZC7YRWWFT2P=how-does-the-decision-tree-help which-decision-tree-do-i-need-onsite-or-offsite=which-decision-tree-do-i-need-on-site-or-off-site h_01K3JR7AZFWJMTBZGAKYS4BFJS=which-decision-tree-do-i-need-on-site-or-off-site the-onsite-use-case-decision-tree=the-on-site-campaign-decision-tree h_01JSKXR18R4A4WFPTQVB1DVV5Y=the-on-site-campaign-decision-tree h_01JSM17ZMGCF1FWQPM7T04C0MM=on-which-platform-does-the-conversion-take-place h_01JSKXR18RTDSJ6W40D5JVFSS5=the-conversions-take-place-on-the-cmn-platform h_01JSKXR18R9A9MCZ7TPJHXWMBC=the-cmn-platform-is-an-app h_01JSKXR18RWSJTR5AKDBRGP0QS=the-cmn-platform-is-a-website h_01JSKXR18R083C5FY5FTESJDAZ=the-conversions-take-place-on-the-advertiser-platform h_01JSKXR18RH3SCQJRJA7QBVS6Y=the-advertiser-platform-is-an-app h_01JSKXR18R3N816VYJ4910VYGA=the-advertiser-platform-is-a-website the-offsite-use-case-decision-tree=the-off-site-campaign-decision-tree h_01JSKXR18R38YJZ2S410J4EH43=the-off-site-campaign-decision-tree h_01JSM18A2R9015RWB05BE0YK7Q=which-account-on-the-external-platform-displays-the-ad h_01JSKXR18R4EKMWCYKFTBAEPH9=the-cmn-external-platform-account h_01JSKXR18RCKD3E841EQ2RC03B=the-conversions-take-place-on-the-cmn-platform::e7b94fc0 h_01JSKXR18R5115TP1BYE07TJ7V=the-cmn-platform-is-an-app::76ead17 h_01JSKXR18RCBGH6F8SNSRN2CJG=the-cmn-platform-is-a-website::5144f168 h_01JSKXR18RGQX77NM72G4WAC08=the-conversions-take-place-on-the-advertiser-platform::aa9e89bf h_01JSKXR18R61CTQ0VMRKD184VE=the-advertiser-platform-is-an-app::d36436f5 h_01JSKXR18RSQC7MCYZ5JE2VP3B=the-advertiser-platform-is-a-website::b70163fb h_01JSKXR18SYFX87XBSBNPJXAFA=the-advertisers-external-platform-account h_01JSKXR18S6TQMNW6PD65G67AQ=the-conversions-take-place-on-the-cmn-platform::7b0781d3 h_01JSKXR18SCDQXAN5NFQ1W17K2=the-cmn-platform-is-an-app::413a6003 h_01JSKXR18SDCDQX4SJ24ADZA18=the-cmn-platform-is-a-website::95667666 h_01JSKXR18S123PXD3FN2N11GCN=the-conversions-take-place-on-the-advertiser-platform::51470bc6 h_01JSKXR18STJV3GGW83123W7XC=the-advertiser-platform-is-a-website::8cb255ef" />

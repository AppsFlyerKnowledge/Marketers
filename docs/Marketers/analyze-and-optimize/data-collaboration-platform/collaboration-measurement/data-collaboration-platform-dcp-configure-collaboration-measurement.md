---
title: Data Collaboration Platform (DCP) - Configure collaboration measurement
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2025-01-27T09:58:46Z'
  edited_at: '2026-03-05T00:01:07Z'
  id: 32147174933905
  locale: en-us
  section: Collaboration measurement
  section_id: 38034865098641
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/32147174933905-Data-Collaboration-Platform-DCP-Configure-collaboration-measurement
---
> **At a glance:** Learn how to configure DCP to perform SKU-level attribution based on the conversion, engagement, and campaign mapping data.

<div id="overview" />

## Overview

After <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement">preparing the conversion, engagement, and campaign-mapping</Anchor> data, you can configure DCP to use them for measurement and attribution:

1. [**Define campaign type**](#select-campaign-type-on-site-off-site-or-both) – Choose on-site, off-site, or combined. This determines how DCP processes your data and sets the required configuration tasks.
2. [**Assign tasks**](#assign-configuration-task) – The owner assigns each configuration task to the collaborator with access to the relevant data.
3. [**Configure tasks**](#configure-on-site-and-off-site-campaign-measurement) – Collaborators configure conversions, engagements, and campaign mapping. This includes setting up on-site and off-site campaigns so all data is connected, mapped, and ready for attribution.
4. <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-run-and-manage-measurement">**Run and manage measurements**</Anchor> - Run measurements live or historical, duplicate them, re-run them, or change their scope.

<div id="start-the-measurement-setup" />

## Start the measurement setup

To start the measurement setup, follow these steps:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Data Clean Room**.
2. On the **Data Collaboration Platform** page, select the collaboration you want to set.
3. In the Collaboration page, perform **one** of the following steps:
   * If this is the first measurement set up in your collaboration, click **Set up measurement.** The **Create measurement** page is displayed.
   * If you already have a measurement set in your collaboration, click the plus sign in the measurement selection panel. The **Create measurement** page is displayed.

[![start-measurement.png](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)

<div id="select-campaign-type-on-site-off-site-or-both" />

## Select campaign type: on-site, off-site, or both

Because on-site and off-site campaign types differ by where the conversion occurs and how attribution is handled, the collaboration owner must specify the campaign type before configuring collaboration measurement. For more information, see: <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaign-measurement">On-site vs. Off-site campaign measurement</Anchor>.

To select the campaign type, follow these steps:

1. [Start the measurement setup](#start-the-measurement-setup).
2. On the **Create Measurement** page, choose  <Image alt="on-site icon.png" src="https://files.readme.io/c9ff0bb1e2c31527ee38a9403a6180e3ecd4c3ad105935fb59ed14c2474f6039-32148924980113.png" width="3.27%" /> **On-site, <Image alt="off-site icon.png" src="https://files.readme.io/6de5841985237de221c74d427ad06f719572000aafe8077c7cef64e53ee8caf5-32156666763921.png" width="3.3%" /> Off-site**, or both. Continue to **one** of the following:
   * [Configure on-site campaign](#configure-on-site-and-off-site-campaign-measurement),
   * [Configure off-site campaign](#configure-offsite-campaign-measurement),
   * [Configure a combined on-site and off-site campaign](#configure-combined-onsite-and-offsite-campaign-measurement).

<div id="assign-configuration-task" />

## Assign configuration task

The Measurement settings page includes five key tasks: conversion, engagement, campaign mapping,  media partners, and lookback window configuration.

The DCP account owner can assign tasks to collaborators to ensure data privacy and reflect the split in responsibilities. For example, one collaborator may handle engagement data while the other handles conversions. Collaborators only have access to the tasks assigned.

<div id="assign-a-configuration-task-to-a-collaborator" />

<Accordion title="Assign a configuration task to a collaborator">

To assign any of the above tasks, follow the steps below:

1. [Open measurement settings](#start-the-measurement-setup).
2. In each of the four tasks above, from the **Assignee** list, select the collaborator who will handle the task.
   * **Conversions task:** Assign to the collaborator whose platform hosts conversions.
   * **Campaigns task:** Assign to the collaborator whose platform hosts conversions.
   * **Engagements task:** Assign to the collaborator where user engagement occurs.
   * **Media partners task:** Assign to the collaborator whose media partner account is used for off-site campaigns
   * **Lookback windows task** – Automatically assigned to the collaboration owner. You may optionally assign the other collaborator.

</Accordion>

<div id="remove-the-configuration-task-assignment-from-a-collaborator" />

<Accordion title="Remove the configuration task assignment from a collaborator">

In some cases, it may be necessary to revoke a configuration task assignment from a collaborator. When the collaboration owner removes an assignment, the following occurs:

* The collaborator immediately loses access to the unassigned task.
* Any configuration previously provided by the collaborator for that task is discarded.
* The collaboration measurement is stopped.

To remove a configuration task assignment, follow the steps below:

1. Go to collaboration measurement, see Open measurement settings.
2. In the relevant configuration step, from the **Assignee** list, remove the assigned collaborator.

</Accordion>

<div id="configure-on-site-and-off-site-campaign-measurement" />

## Configure on-site and off-site campaign measurement

Configure the campaign measurement setup in Measurement settings. Use the steps below based on whether your measurement is on-site, off-site, or a combined on-site and off-site setup.

<div id="configure-onsite-campaign-measurement::4f9b35af" />

<Accordion title="Configure on-site campaign measurement">

To set up an <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-campaigns">on-site campaign</Anchor>, follow these steps:

1. [Start the measurement setup](#start-the-measurement-setup).
2. <Anchor target="_blank" href="/marketers/docs/set-up-the-campaigns-task">Set up the campaigns task</Anchor>
3. <Anchor target="_blank" href="/marketers/docs/set-up-the-conversions-task">Set up the conversions task</Anchor>
4. <Anchor target="_blank" href="/marketers/docs/set-up-the-engagements-task">Set up the engagements task</Anchor>
5. <Anchor target="_blank" href="/marketers/docs/set-up-the-lookback-windows-task">Set up the lookback windows task</Anchor>

</Accordion>

<div id="configure-offsite-campaign-measurement" />

<Accordion title="Configure off-site campaign measurement">

To set up an <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaigns">off-site campaign</Anchor>, follow these steps:

1. [Start the measurement setup](#start-the-measurement-setup).
2. <Anchor target="_blank" href="/marketers/docs/set-up-the-campaigns-task">Set up the campaigns task</Anchor>
3. <Anchor target="_blank" href="/marketers/docs/set-up-the-conversions-task">Set up the conversions task</Anchor>
4. <Anchor target="_blank" href="/marketers/docs/set-up-the-media-partners-task">Set up the media partners task</Anchor>
5. <Anchor target="_blank" href="/marketers/docs/set-up-the-lookback-windows-task">Set up the lookback windows task</Anchor>

</Accordion>

<div id="configure-combined-onsite-and-offsite-campaign-measurement" />

<Accordion title="Configure combined on-site and off-site campaign measurement">

To set up a <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaigns">combined on-site and off-site campaign</Anchor>, follow these steps:

1. [Start the measurement setup](#start-the-measurement-setup).
2. <Anchor target="_blank" href="/marketers/docs/set-up-the-campaigns-task">Set up the campaigns task</Anchor>
3. <Anchor target="_blank" href="/marketers/docs/set-up-the-conversions-task">Set up the conversions task</Anchor>
4. <Anchor target="_blank" href="/marketers/docs/set-up-the-engagements-task">Set up the engagements task</Anchor>
5. <Anchor target="_blank" href="/marketers/docs/set-up-the-media-partners-task">Set up the media partners task</Anchor>
6. <Anchor target="_blank" href="/marketers/docs/set-up-the-lookback-windows-task">Set up the lookback windows task</Anchor>

</Accordion>

<div data-zendesk-anchors="h_01K3EHANCCZ703MMMM5PTEF68B=overview open-measurement-settings=start-the-measurement-setup h_01JJKK3CQ8F9Q7VM7MM9AFKNN5=start-the-measurement-setup select-campaign-type-onsite-offsite-or-both=select-campaign-type-on-site-off-site-or-both h_01K3EHANCCW8PQ8NWC6ZHWCMGT=select-campaign-type-on-site-off-site-or-both h_01K3EHANCCW97TV88ECVMQKF2N=assign-configuration-task h_01K3EHANCD71R47V88DR61CTMV=assign-a-configuration-task-to-a-collaborator h_01K3EHANCDF1HMTV8X35Q1RHTS=remove-the-configuration-task-assignment-from-a-collaborator configure-onsite-campaign-measurement=configure-on-site-and-off-site-campaign-measurement h_01K3EHANCD936QN2MKFY5QSDBZ=configure-on-site-and-off-site-campaign-measurement h_01KJWCMN3XRTS3361N08RT1SD6=configure-onsite-campaign-measurement::4f9b35af h_01KJWCMN3XRXW6A71P5678AHH1=configure-offsite-campaign-measurement h_01KJWCMN3XKD8YJVPQEZ53K819=configure-combined-onsite-and-offsite-campaign-measurement" />

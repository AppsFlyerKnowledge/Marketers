---
title: Set up the Engagements task
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
  created_at: '2025-08-18T10:19:20Z'
  edited_at: '2026-05-27T09:33:55Z'
  id: 38188042548113
  locale: en-us
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/38188042548113-Set-up-the-Engagements-task
---
> **At a glance:** Learn how to configure engagement events for on-site and combined campaigns (on-site and off-site campaigns).

<Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#engagements">Engagement events</Anchor> capture user interactions—such as ad views or clicks—that occur before a conversion. They are configured only for on-site campaigns, either alone or combined with off-site campaigns. (For off-site campaigns, engagement data is provided directly by external partners such as Meta or Google. This article explains how to configure engagements by campaign type.

## Prerequisites

Before the Engagements task can be set up, the collaboration owner needs to assign it to the collaborator who owns the platform where the engagement events are generated. For more information, see Assign configuration tasks

## Set up engagements for on-site or combined campaigns

In the context of on-site and combined campaigns, all engagement events originate from the collaborator’s owned properties—such as their app, website, or in-store systems. These engagement events are typically collected using the AppsFlyer SDK or submitted via custom data sources and are attributed solely to on-site user activity.

<div id="1-prepare-engagement-data" />

<Accordion title="1. Prepare engagement data">

Before you set up the custom engagement source in DCP, you can provide engagement data in one of two ways:

* **Custom source file:** Create an engagement source file and upload it to your cloud service. For more information, see <Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Prepare custom source files for engagements</Anchor>.
* **AppsFlyer SDK:** Integrate the AppsFlyer SDK into your app to automatically send in-app engagement events to DCP. For more information, see <Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events">Prepare in-app events for engagements</Anchor>.

</Accordion>

<div id="2-open-engagement-settings" />

<Accordion title="2. Open engagement settings">

The **Measurement settings** page is where you configure, as part of the collaboration measurement setup, how engagements are collected and attributed.

To open the **Measurement settings** page, follow these steps:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Data Clean Room**.
2. On the **Data Collaboration Platform** page, select the collaboration you want to set.
3. At the bottom of the collaboration page, click **Set up measurement.**
   * If the link is grayed out, set up the collaboration's <Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-create-and-manage-sources">data sources</Anchor> and <Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiences</Anchor>.
4. On the **Measurement Setting** page, click the **Engagements** pane to open the **Engagements** dialog.

   > 📘 **Note**
   >
   > * If the **Engagements** dialog is locked, it means that the Engagements task has been assigned to your collaborator and that you cannot view its content. If you are the collaboration owner, you can unlock it by reassigning the task to yourself. However, any previous settings will be deleted, and the task will be reset.
   > * If the **Engagements** pane is grayed out, ask the collaboration owner to assign you the Engagements task.


</Accordion>

<div id="3-set-data-provision-method" />

<Accordion title="3. Set data provision method">

Engagement data is provided to DCP either via in-app events, custom source, or both:

* **In-app events** — The origin of the engagement event data is the AppsFlyer SDK integrated into your mobile app. The SDK sends engagement events in real time from your app whenever the user performs a defined action.
* **Custom source** — The origin of the engagement events is a custom source file stored in your cloud.

To set up the engagement provision method in DCP, follow these steps:

1. In the **Engagements** dialog, select the engagement provisioning type: in-app events, custom source file, or both.
2. Depending on your provisioning method, enter the following details:
   * **In-app events:**
     1. Select the app that sends the in-app events containing the engagement data.
     2. In the **Select ad engagement event** list, select which of the in-app events sent by the AppsFlyer SDK is the engagement event.
     3. In the **Select advertised item (SKU)** list, select the parameter in the in-app event that contains the SKU value.
   * **Custom source:**
     1. Click + **New engagement source**.
     2. In the **New engagement source** dialog, enter the engagement source's name in the **Source name** field according to the <Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-create-and-manage-sources#requirements-and-guidelines">requirements and guidelines</Anchor>.
3. Click **Next**.

</Accordion>

<div id="4-set-source-location" />

<Accordion title="4. Set source location">

If a custom source is used to provide engagement events to DCP, set the details that enable DCP to access it in your cloud service.

1. In the **Set source location** step, select the connection from which the source is accessed.
   * If your account does not have connections defined, the **New connection** dialog will open, prompting you to create one.
   * If you have existing connections but want to use a new one, open the **Select connection** list and select **+ New connection.**
2. Set the source access details according to your cloud service:
   * <Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-locations-in-bigquery">BigQuery</Anchor>
   * <Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-locations-in-snowflake">Snowflake</Anchor>
   * <Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-locations-in-cloud-storage-buckets">Amazon S3 and GCS</Anchor>
   * <Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-location-as-local-files">Local file system</Anchor>
3. Select how new data should be handled. For more information, see: <Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Set source sync method</Anchor>.
4. Click **Next**.

</Accordion>

<div id="5-map-engagement-source-fields" />

<Accordion title="5. Map engagement source fields">

If a custom source is used to provide engagement events to DCP, map your custom engagement source fields to their corresponding DCP fields.

> 📘 **Note**
>
> The **DCP conversion events database** stores all the conversion events of the current collaboration under a unitary scheme, including conversion events originating from **in-app events** or **off-site campaigns** (if you’re running a combined on-site off-site campaign).

**Load engagement source fields**

If the engagement source fields are not already loaded, you might have to load them manually to have them mapped to DCP fields.

To load engagement source fields, follow these steps:

1. In the **Map source fields** step, click **Load fields from source**.
2. For information about how to manually load fields, see: <Anchor target="_blank" href="/marketers/vi/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-load-your-source-fields">Load your source fields</Anchor>.

**Auto-map engagement fields**

When engagement source fields are loaded, DCP automatically maps them to their corresponding DCP fields. Auto mapping can take up to 10 seconds. A banner displays the mapping result, showing how many fields were mapped and listing any source columns that could not be matched.

To re-trigger auto mapping, click **Update mapping**.

**Map engagement fields**

If the engagement source fields are loaded, you can map them to the DCP fields.

To map the engagement custom source fields, follow these steps

1. If you are setting a combined **On-site and Off-site campaign**, in the **Map source fields** step, expand the **Data for on-site attribution;** else, skip to the step below.
2. Map all required fields under **Required**.
3. (Optional) Expand **Optional enrichment data** to map additional fields.
4. Click **Save**. The **`{source name}` source created** message is displayed.[<Image alt="" src="https://files.readme.io/670c7ca42d066bf2d874785108d84318387e393512973d2fff5056ab3f5a45cd-38381396764817.png" width="40.62%" />](https://files.readme.io/670c7ca42d066bf2d874785108d84318387e393512973d2fff5056ab3f5a45cd-38381396764817.png)

</Accordion>

<div data-zendesk-anchors="h_01K3EFVGA56P7FB605JY1BQ34M=prerequisites set-up-engagements-for-onsite-or-combined-campaigns=set-up-engagements-for-on-site-or-combined-campaigns h_01K3EFVGA6GT10BXJYE9SFM9TE=set-up-engagements-for-on-site-or-combined-campaigns h_01K3EFVGA6NM4YKZ8MEEYXX58B=1-prepare-engagement-data h_01K3EFVGA65CFME4H3ZC89X471=2-open-engagement-settings h_01K3EFVGA618KT7PGSVQXF6JSV=note h_01K3EFVGA6BKGAS5GZR3GW2N2M=3-set-data-provision-method h_01K3EFVGA64CQTKZ8C227042PY=4-set-source-location h_01K3EFVGA6J7PX1QE8TRA42QEY=5-map-engagement-source-fields h_01K3EFVGA6E3WH7FEYCW09P74V=note-1" />

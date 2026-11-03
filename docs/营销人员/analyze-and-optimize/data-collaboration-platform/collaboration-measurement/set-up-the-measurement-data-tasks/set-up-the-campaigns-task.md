---
title: Set up the Campaigns task
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
  created_at: '2025-08-18T11:31:27Z'
  edited_at: '2026-10-13T00:14:57Z'
  id: 38190881693969
  locale: zh-cn
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/zh-cn/articles/38190881693969
---
> **At a glance:** Learn how to configure the campaign source for on-site, off-site and combined campaigns (on-site and off-site campaigns).

<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#campaign-mapping">The campaign source</Anchor> connects on-site conversion events to their respective off-site, on-site, and combined campaigns, enabling accurate attribution and performance reporting. Unlike other tasks in DCP (such as conversions or engagements), the **Campaigns task is identical for both on-site and off-site campaigns**. This means you follow the same configuration process regardless of the campaign type.

## Prerequisites

Before the Campaigns task can be set up, the collaboration owner needs to assign it to the collaborator who owns the platform where the conversion events are generated. For more information, see Assign configuration tasks

## Set up the Campaigns task

The campaigns source links internal conversion events to campaign-level identifiers (for example, campaign ID) in the context of on-site, off-site, or combined campaigns. The campaign information you set in this task is submitted via a custom data source to DCP.

<div id="1-prepare-campaign-data" />

<Accordion title="1. Prepare campaign data">

Before you set up the campaign source in DCP, prepare the campaign’s custom source and upload it to your cloud service. For details about the mapping schema and how to load the campaign source to your cloud environment, see <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source">Prepare campaign source</Anchor>.

To set up the campaign source in DCP:

1. Go to the **collaboration measurement** page.
2. Click **Campaigns**.
3. On the **Campaigns** dialog, click **+ New campaign source**.
4. In the **New campaign source** dialog, enter a name in the **Source name** field according to <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#要求和指南">requirements and guidelines</Anchor>.
5. Click **Next**.

</Accordion>

<div id="2-open-campaigns-settings" />

<Accordion title="2. Open campaigns settings">

The **Measurement settings** page is where you configure how campaigns are collected, attributed, and connected to media partner data as part of your collaboration setup.

To open the **Measurement settings** page, follow these steps:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Data Clean Room**.
2. On the **Data Collaboration Platform** page, select the collaboration you want to set.
3. At the bottom of the collaboration page, click **Set up measurement.**
   * If the link is disabled, set up the collaboration's <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources">data sources</Anchor> and <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiences</Anchor>.
4. On the **Measurement Setting** page, click the **Campaigns** pane to open the **Campaigns** dialog.

   > 📘 **Note**
   >
   > * If the **Campaigns** dialog is locked, it means that the **Campaigns** task is assigned to your collaborator, and you cannot view its content. If you are the collaboration owner, you can unlock by reassigning the task to yourself. However, any previous settings will be deleted, and the task will be reset.
   > * If the **Campaigns** pane is grayed out, ask the collaboration owner to assign you the Campaigns task.


</Accordion>

<div id="3-set-campaign-data-provision-method" />

<Accordion title="3. Set campaign data provision method">

Campaign data is provided to DCP in a custom source file stored in your cloud.

To set up the conversion provision method in DCP, follow these steps:

1. In the **Campaigns** dialog, click + **New campaign source**.
2. In the **New conversion source** dialog, in the **Source name** step, set the campaign source's name in the **Source name** field according to the <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#要求和指南">requirements and guidelines</Anchor>.
3. Click **Next**.

</Accordion>

<div id="4-set-source-location" />

<Accordion title="4. Set source location">

Set the location of the campaign's source in your cloud service.

1. In the **Set source location step**, select the connection from which the source is accessed.
   * If your account does not have connections defined, the **New connection** dialog will open, prompting you to create one.
   * If you have existing connections but want to use a new one, open the **Select connection** list and select **+ New connection**.
2. Set the access details according to your cloud service:
   * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#bigquery-数据源位置">BigQuery</Anchor>
   * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#snowflake-数据源位置">Snowflake</Anchor>
   * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#云存储桶的数据源位置">Amazon S3 and GCS</Anchor>
   * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-location-as-local-files">Local file system</Anchor>
3. Select how new data should be handled. For more information, see: <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Set source sync method</Anchor>.
4. Click **Next**.

</Accordion>

<div id="5-map-campaign-fields" />

<Accordion title="5. Map campaign fields">

If a custom source is used to provide conversion events to DCP, map your on-site custom conversion source fields to their corresponding DCP fields.

**Load campaign source fields**

If the campaign source fields are not already loaded, you might have to load them manually to have them mapped to DCP fields.

To load conversion source fields, follow these steps:

1. In the **Map source fields** step, click **Load fields from source**.
2. For information about how to manually load fields, see: <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-load-your-source-fields">Load your source fields</Anchor>.

**Auto-map campaign fields**

When campaign source fields are loaded, DCP automatically maps them to their corresponding DCP fields. Auto mapping can take up to 10 seconds. A banner displays the mapping result, showing how many fields were mapped and listing any source columns that could not be matched.

To re-trigger auto mapping, click **Update mapping**.

**Map campaign fields**

If the conversion source fields are loaded, you can map them to the DCP fields.

To map the campaigns' custom source fields, follow these steps:

1. Map the fields under **Source fields** to their corresponding fields under **DCP fields**.
   * For a list of fields and descriptions, see The campaigns scheme.
2. Click **Save**. The **campaign\_mapping source created** message is displayed.

</Accordion>

<div id="5-align-collaborator-name" />

<Accordion title="6. Align collaborator name">

The final step after completing the Campaigns task is to align the collaborator’s name. This is required because each DCP account has only one campaign source. Since the account owner can maintain multiple collaborations with different collaborators, DCP needs to know which collaborator is active in the current collaboration.

To align the collaborator name:

* In the **Campaigns** dialog, under **Align collaborator names**, select the collaborator of the current collaboration.

</Accordion>

<div data-zendesk-anchors="h_01K3BEVMGMPENVYY18EB0ANQCP=prerequisites h_01K3BEVMGM6EEP6DY54HDDVKTR=set-up-the-campaigns-task h_01K3BEVMGMC9C09FJTRVMS2J32=1-prepare-campaign-data h_01K3BEVMGMT28RXKBN31EBAFYJ=2-open-campaigns-settings h_01K3BEVMGMGV8GVGKZFDCSC0DF=note h_01K3BEVMGM2D9TA52F9F36Z31W=3-set-campaign-data-provision-method h_01K3BEVMGM67JV6VT6TBXTYACC=4-set-source-location h_01K3BEVMGNNFYFF939RHB8Z8E1=5-map-campaign-fields h_01K3BEVMGN4MAV9B0HP2TK5XCC=5-align-collaborator-name" />

---
title: "Set up the Campaigns task"
excerpt: "Learn how to configure the campaign source for on-site, off-site, and combined campaigns in the Data Collaboration Platform."
---
At a glance: Learn how to configure the campaign source for on-site, off-site and combined campaigns (on-site and off-site campaigns).

[The campaign source](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#campaign-mapping) connects on-site conversion events to their respective [off-site, on-site, and combined campaigns](https://support.appsflyer.com/hc/articles/38354928391313-Set-up-collaboration-measurement#select-campaign-type-onsite-offsite-or-both), enabling accurate attribution and performance reporting. Unlike other tasks in DCP (such as conversions or engagements), the **Campaigns task is identical for both on-site and off-site campaigns**. This means you follow the same configuration process regardless of the campaign type.

## Prerequisites

Before the Campaigns task can be set up, the collaboration owner needs to assign it to the collaborator who owns the platform where the conversion events are generated. For more information, see [Assign configuration tasks](https://support.appsflyer.com/hc/articles/38354928391313-Set-up-campaign-measurement@assign-configuration-tasks)

## Set up the Campaigns task

The campaigns source links internal conversion events to campaign-level identifiers (for example, campaign ID) in the context of on-site, off-site, or combined campaigns. The campaign information you set in this task is submitted via a custom data source to DCP.

### 1. Prepare campaign data

Before you set up the campaign source in DCP, prepare the campaign’s custom source and upload it to your cloud service. For details about the mapping schema and how to load the campaign source to your cloud environment, see [Prepare campaign source](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-campaign-mapping-source).

To set up the campaign source in DCP:

1. Go to the **collaboration measurement** page.
2. Click **Campaigns**.
3. On the **Campaigns** dialog, click **+ New campaign source**.
4. In the **New campaign source** dialog, enter a name in the **Source name** field according to [requirements and guidelines](/docs/data-collaboration-platform-dcp-create-and-manage-sources#requirements-and-guidelines).
5. Click **Next**.

### 2. Open campaigns settings

The **Measurement settings** page is where you configure how campaigns are collected, attributed, and connected to media partner data as part of your collaboration setup.

To open the **Measurement settings** page, follow these steps:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Data Clean Room**.
2. On the **Data Collaboration Platform** page, select the collaboration you want to set.
3. At the bottom of the collaboration page, click **Set up measurement.**
   - If the link is disabled, set up the collaboration's [data sources](/docs/data-collaboration-platform-dcp-create-and-manage-sources) and [audiences](/docs/data-collaboration-platform-dcp-build-and-activate-audiences).
4. On the **Measurement Setting** page, click the **Campaigns** pane to open the **Campaigns** dialog.

> 📘 Note
>
> - If the **Campaigns** dialog is locked, it means that the **Campaigns** task is assigned to your collaborator, and you cannot view its content. If you are the collaboration owner, you can unlock by [reassigning the task](https://support.appsflyer.com/hc/articles/38354928391313-Set-up-collaboration-measurement#assign-configuration-task) to yourself. However, any previous settings will be deleted, and the task will be reset.
> - If the **Campaigns** pane is grayed out, ask the collaboration owner to assign you the Campaigns task.

### 3. Set campaign data provision method

Campaign data is provided to DCP in a custom source file stored in your cloud.

To set up the conversion provision method in DCP, follow these steps:

1. In the **Campaigns** dialog, click + **New campaign source**.
2. In the **New conversion source** dialog, in the **Source name** step, set the campaign source's name in the **Source name** field according to the [requirements and guidelines](/docs/data-collaboration-platform-dcp-create-and-manage-sources#requirements-and-guidelines).
3. Click **Next**.

### 4. Set source location

Set the location of the campaign's source in your cloud service.

1. In the **Set source location step**, select the connection from which the source is accessed.
   - If your account does not have connections defined, the **New connection** dialog will open, prompting you to create one.
   - If you have existing connections but want to use a new one, open the **Select connection** list and select **+ New connection**.
2. Set the access details according to your cloud service:
   - [BigQuery](/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-locations-in-bigquery)
   - [Snowflake](/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-locations-in-snowflake)
   - [Amazon S3 and GCS](/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-locations-in-cloud-storage-buckets)
   - [Local file system](/docs/data-collaboration-platform-dcp-create-and-manage-sources#local-file-system)
3. Select how new data should be handled. For more information, see: [Set source sync method](/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method).
4. Click **Next**.

### 5. Map campaign fields

If a custom source is used to provide conversion events to DCP, map your on-site custom conversion source fields to their corresponding DCP fields.

**Load campaign source fields**

If the campaign source fields are not already loaded, you might have to load them manually to have them mapped to DCP fields.

To load conversion source fields, follow these steps:

1. In the **Map source fields** step, click **Load fields from source**.
2. For information about how to manually load fields, see: [Load your source fields](/docs/data-collaboration-platform-dcp-create-and-manage-sources#load-the-source-fields).

**Auto-map campaign fields**

When campaign source fields are loaded, DCP automatically maps them to their corresponding DCP fields. Auto mapping can take up to 10 seconds. A banner displays the mapping result, showing how many fields were mapped and listing any source columns that could not be matched.

To re-trigger auto mapping, click **Update mapping**.

**Map campaign fields**

If the conversion source fields are loaded, you can map them to the DCP fields.

To map the campaigns' custom source fields, follow these steps:

1. Map the fields under **Source fields** to their corresponding fields under **DCP fields**.
   - For a list of fields and descriptions, see [The campaigns scheme](https://support.appsflyer.com/hc/articles/article_number).
2. Click **Save**. The **campaign_mapping source created** message is displayed.

### 6. Align collaborator name

The final step after completing the Campaigns task is to align the collaborator’s name. This is required because each DCP account has only one campaign source. Since the account owner can maintain multiple collaborations with different collaborators, DCP needs to know which collaborator is active in the current collaboration.

To align the collaborator name:

- In the **Campaigns** dialog, under **Align collaborator names**, select the collaborator of the current collaboration.
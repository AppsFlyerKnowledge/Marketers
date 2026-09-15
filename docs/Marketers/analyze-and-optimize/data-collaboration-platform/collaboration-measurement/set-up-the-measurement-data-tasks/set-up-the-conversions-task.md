---
title: "Set up the Conversions task"
excerpt: "Learn how to configure conversion events for on-site and off-site campaigns in AppsFlyer's Data Collaboration Platform."
---
**At a glance:** :AAG: Learn how to configure conversion events for on-site and off-site campaigns.

[Conversion events](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#conversions) capture valuable post-engagement actions—such as purchases—across various campaign setups. While the structure and content of each conversion event remain consistent, the way conversions are measured, attributed, and shared varies depending on whether it’s an [on-site](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-campaigns), [off-site](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns), or [on-site and off-site](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns) campaign. This article explains how to set the Conversion task for each campaign type.

## Prerequisites

Before the Conversions task can be set up, the collaboration owner needs to assign it to the collaborator who owns the platform where the conversion events are generated. For more information, see Assign configuration tasks

## Set up on-site campaign conversions

In the context of on-site campaigns, all conversion events originate from the collaborator’s owned properties—such as their app, website, or in-store systems. These conversion events are typically collected using the AppsFlyer SDK or submitted via custom data sources and attributed solely to on-site user engagements.

To set up on-site conversions, follow these steps:

1. [Prepare conversion data](#prepare-conversion-data)
2. [Open conversion settings](#open-conversion-settings)
3. [Set data provision method](#set-conversion-data-provision-method)
4. [Set source location](#set-conversion-source-location)
5. [Map on-site conversion source fields](#map-onsite-conversion-source-fields)

## Set up off-site campaign conversions

In the context of on-site campaigns, conversion events occur within the collaborator’s properties, such as their app, website, or in-store systems, but attribution is based on engagements that took place on external platforms, such as Meta or Google.

To set up off-site conversions, follow these steps:

1. [Prepare conversion data](#prepare-conversion-data)
2. [Open conversion settings](#open-conversion-settings)
3. [Set data provision method](#set-conversion-data-provision-method)
4. [Set source location](#set-conversion-source-location)
5. [Map off-site conversion source fields](#map-offsite-conversion-source-fields)

## Set up on-site and off-site conversions

In combined on-site and off-site campaign setups, conversions from the collaborator’s properties may be attributed to engagements from either on-site or off-site sources.

To set up on-site and off-site conversions, follow these steps:

1. [Prepare conversion data](#prepare-conversion-data)
2. [Open conversion settings](#open-conversion-settings)
3. [Set data provision method](#set-conversion-data-provision-method)
4. [Set source location](#set-conversion-source-location)
5. [Map on-site conversion source fields](#map-onsite-conversion-source-fields)
6. [Map off-site conversion source fields](#map-offsite-conversion-source-fields)

## Configuration activities

### Prepare conversion data

Before you set up the custom conversion source in DCP, you can provide conversion data in one of two ways:

* **Custom source file:** Create a conversion source file and upload it to your cloud service. For more information, see [Prepare custom source files for conversions](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme).
* **AppsFlyer SDK:** Integrate the AppsFlyer SDK into your app to automatically send in-app conversion events to DCP. For more information, see [Prepare in-app events for conversions.](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events)

### Open conversion settings

The **Measurement settings** page is where you configure how conversions and engagements are collected, attributed, and shared with media partners as part of your off-site collaboration setup.

To open the **measurement settings** page, follow these steps:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Data Clean Room**.
2. On the **Data Collaboration Platform** page, select the collaboration you want to set.
3. At the bottom of the collaboration page, click **Set up measurement.**(If the link is disabled, set up the collaboration's [data sources](/docs/data-collaboration-platform-dcp-create-and-manage-sources) and [audiences](/docs/data-collaboration-platform-dcp-build-and-activate-audiences).)
4. On the **Measurement Settings** page, click the **Conversions** pane to open the **Conversions** dialog.

   CALLSTART::Note::

   #### Note

   * If the **Conversion** dialog is locked, it means that the **Conversion** task has been assigned to your collaborator and that you cannot view its content. If you are the collaboration owner, you can unlock it by reassigning the task to yourself. However, any previous settings will be deleted, and the task will be reset.
   * If the **Conversion** pane is grayed out, ask the collaboration owner to assign you the Conversion task.CALLEND::

### Set conversion data provision method

Conversion data is provided to DCP either via in-app events, custom source, or both:

* **In-app events** — The origin of the conversion event data is the AppsFlyer SDK integrated into your mobile app. The SDK sends conversion events in real time from your app whenever the user performs a converting activity.
* **Custom source**— The origin of the conversion events is a custom source file stored in your cloud.

To set up the conversion provision method in DCP, follow these steps:

1. In the **Conversions** dialog, select the conversion provisioning type: in-app events, custom source file, or both.
2. Depending on your provisioning method, enter the following details:
   * **In-app events:**
     1. Select the app that sends the in-app events containing the conversion data.
     2. In the **Select conversion event** list, select which of the in-app events sent by the AppsFlyer SDK is the conversion event.
     3. In the **Advertised item (SKU)**field, choose the parameter that contains the conversion event SKUs.
   * **Custom source:**
     1. Click on + **New conversion source**.
     2. In the **New conversion source** dialog, enter the conversion source's name in the **Source name** field according to the [requirements and guidelines](/docs/data-collaboration-platform-dcp-create-and-manage-sources#requirements-and-guidelines).
3. Click **Next**.

### Set conversion source location

If a custom source is used to provide conversion events, enable DCP to access them by following these steps:

1. In the **Set source location** step, select the connection from which the source is accessed.
   * If your account does not have connections defined, the **New connection** dialog will open, prompting you to create one.
   * If you have existing connections but want to use a new one, open the **Select connection** list and select **+ New connection.**
2. Set the source access details according to your cloud service:
   * [BigQuery](/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-locations-in-bigquery)
   * [Snowflake](/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-locations-in-snowflake)
   * [Amazon S3 and GCS](/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-locations-in-cloud-storage-buckets)
   * [Local file system](/docs/data-collaboration-platform-dcp-create-and-manage-sources#local-file-system)
3. Select how new data should be handled. For more information, see: [Set source sync method](/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method).
4. Click **Next**.

### Map on-site conversion source fields

If a custom source is used to provide conversion events to DCP, map your on-site custom conversion source fields to their corresponding DCP fields.

> 📘 **Note**
>
> The **DCP conversion events database** stores all the conversion events of the current collaboration under a unitary scheme, including conversion events originating from **in-app events** or **off-site campaigns** (if you’re running a combined on-site off-site campaign).


**Load conversion source fields**

If the conversion source fields are not already loaded, you might have to load them manually to have them mapped to DCP fields.

To load conversion source fields, follow these steps:

1. In the **Map source fields** step, click **Load fields from source**.
2. For information about how to manually load fields, see: [Load your source fields](/docs/data-collaboration-platform-dcp-create-and-manage-sources#load-the-source-fields).

**Auto-map conversion fields**

When conversion source fields are loaded, DCP automatically maps them to their corresponding DCP fields. Auto mapping can take up to 10 seconds. A banner displays the mapping result, showing how many fields were mapped and listing any source columns that could not be matched.

To re-trigger auto mapping, click **Update mapping**.

**Map conversion fields**

If the conversion source fields are loaded, you can map them to the DCP fields.

To map the conversion custom source fields, follow these steps

1. If you are setting a **combined** **on-site and off-site campaign**, expand **Data for on-site attribution;** otherwise**,** skip to the step below.
2. Map all required fields under **Required**.
3. (Optional) Expand **Optional enrichment data** to map additional fields.

   CALLSTART::Note::

   #### Note

   If the campaign is combined withan Off-site campaign, and you map a field (for example, Event ID) that's already mapped in an off-site channel, you'll be prompted with an **Override field?** message. Click **Yes, continue** to confirm and apply the mapping across channels.

   CALLEND::
4. Click **Save**. The **`{source name}` source created** message is displayed.[![](https://support.appsflyer.com/hc/article_attachments/38345272613265)](https://support.appsflyer.com/hc/article_attachments/38345272613265)

### Map off-site conversion source fields

If a custom source is used to provide conversion events from off-site campaigns, map your off-site custom conversion source fields to their corresponding DCP fields.

> 📘 **Note**
>
> The **DCP conversion events database** stores all the conversion events of the current collaboration under a unitary scheme, including conversion events originating from **in-app events** or **on-site campaigns** (if you’re running a combined on-site off-site campaign).


**Load conversion source fields**

If the conversion source fields are not already loaded, you might have to load them manually to have them mapped to DCP fields.

To load conversion source fields, follow these steps:

1. In the **Map source fields** step, click **Load fields from source**.
2. For information about how to manually load fields, see: [Load your source fields](/docs/data-collaboration-platform-dcp-create-and-manage-sources#load-the-source-fields).

**Auto-map conversion fields**

When conversion source fields are loaded, DCP automatically maps them to their corresponding DCP fields. Auto mapping can take up to 10 seconds. A banner displays the mapping result, showing how many fields were mapped and listing any source columns that could not be matched.

To re-trigger auto mapping, click **Update mapping**.

**Map conversion fields**

If the conversion source fields are loaded, you can map them to the DCP fields. When you share conversion data with external platforms like Meta or Google, AppsFlyer sends only the fields required for each partner to match conversions against their own campaign engagement events.

The fields shown here depend on the conversion source types you selected during setup:

1. If you are setting a **combined** **on-site and off-site campaign**, expand **Data for off-site attribution;** otherwise**,** skip to the step below.
2. Turn on **Meta Ads** or **Google Ads,** depending on your data sources:

   CALLSTART::Note::

   #### Note

   When you share conversion data with external platforms like Meta or Google, AppsFlyer sends only the fields required for each partner to match conversions against their own campaign engagement events.

   CALLEND::

   **Meta Ads field mapping**

   Map the fields under **Source fields** to their corresponding fields under **DCP fields**. The DCP fields listed here reflect the required parameters for Meta Ads.

   * Map all six required fields under **Required**.
   * Expand **Optional enrichment data** to map additional fields (for example, First name, IDFA, and email).

   **Google Ads field mapping**

   Map the fields under **Source fields** to their corresponding fields under **DCP fields**. The DCP fields listed here reflect the required parameters for Google Ads.

   * Map all five required fields under **Required**.
   * Map at least one identifier under **At least one is required**.
   * Expand **Optional enrichment data** to map recommended fields like revenue, client user agent, or hashed identifiers.CALLSTART::Note::

   #### Note

   If the campaign is combined withan Off-site campaign, and you map a field (for example, Event ID) that's already mapped in an off-site channel, you'll be prompted with an **Override field?** message. Click **Yes, continue** to confirm and apply the mapping across channels.

   CALLEND::
3. Click **Save** to complete the source setup.
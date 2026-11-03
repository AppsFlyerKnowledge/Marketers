---
title: Set up the Conversions task
metadata:
  keywords:
    - Marketers
    - Retail Media Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Retail Media Measurement
  created_at: '2025-08-18T10:13:32Z'
  edited_at: '2026-10-13T00:15:05Z'
  id: 38187770114449
  locale: zh-cn
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/zh-cn/articles/38187770114449
---
> **At a glance:** :AAG: Learn how to configure conversion events for on-site and off-site campaigns.

<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#conversions">Conversion events</Anchor> capture valuable post-engagement actions—such as purchases—across various campaign setups. While the structure and content of each conversion event remain consistent, the way conversions are measured, attributed, and shared varies depending on whether it’s an <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-campaigns">on-site</Anchor>, <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">off-site</Anchor>, or <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">on-site and off-site</Anchor> campaign. This article explains how to set the Conversion task for each campaign type.

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

<div id="prepare-conversion-data" />

<Accordion title="Prepare conversion data">

Before you set up the custom conversion source in DCP, you can provide conversion data in one of two ways:

* **Custom source file:** Create a conversion source file and upload it to your cloud service. For more information, see <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Prepare custom source files for conversions</Anchor>.
* **AppsFlyer SDK:** Integrate the AppsFlyer SDK into your app to automatically send in-app conversion events to DCP. For more information, see <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Prepare in-app events for conversions.</Anchor>

</Accordion>

<div id="open-conversion-settings" />

<Accordion title="Open conversion settings">

The **Measurement settings** page is where you configure how conversions and engagements are collected, attributed, and shared with media partners as part of your off-site collaboration setup.

To open the **measurement settings** page, follow these steps:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Data Clean Room**.
2. On the **Data Collaboration Platform** page, select the collaboration you want to set.
3. At the bottom of the collaboration page, click **Set up measurement.** (If the link is disabled, set up the collaboration's <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources">data sources</Anchor> and <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiences</Anchor>.)
4. On the **Measurement Settings** page, click the **Conversions** pane to open the **Conversions** dialog.

   > 📘 **Note**
   >
   > * If the **Conversion** dialog is locked, it means that the **Conversion** task has been assigned to your collaborator and that you cannot view its content. If you are the collaboration owner, you can unlock it by reassigning the task to yourself. However, any previous settings will be deleted, and the task will be reset.
   > * If the **Conversion** pane is grayed out, ask the collaboration owner to assign you the Conversion task.


</Accordion>

<div id="set-conversion-data-provision-method" />

<Accordion title="Set conversion data provision method">

Conversion data is provided to DCP either via in-app events, custom source, or both:

* **In-app events** — The origin of the conversion event data is the AppsFlyer SDK integrated into your mobile app. The SDK sends conversion events in real time from your app whenever the user performs a converting activity.
* **Custom source** — The origin of the conversion events is a custom source file stored in your cloud.

To set up the conversion provision method in DCP, follow these steps:

1. In the **Conversions** dialog, select the conversion provisioning type: in-app events, custom source file, or both.
2. Depending on your provisioning method, enter the following details:
   * **In-app events:**
     1. Select the app that sends the in-app events containing the conversion data.
     2. In the **Select conversion event** list, select which of the in-app events sent by the AppsFlyer SDK is the conversion event.
     3. In the **Advertised item (SKU)** field, choose the parameter that contains the conversion event SKUs.
   * **Custom source:**
     1. Click on + **New conversion source**.
     2. In the **New conversion source** dialog, enter the conversion source's name in the **Source name** field according to the <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#要求和指南">requirements and guidelines</Anchor>.
3. Click **Next**.

</Accordion>

<div id="set-conversion-source-location" />

<Accordion title="Set conversion source location">

If a custom source is used to provide conversion events, enable DCP to access them by following these steps:

1. In the **Set source location** step, select the connection from which the source is accessed.
   * If your account does not have connections defined, the **New connection** dialog will open, prompting you to create one.
   * If you have existing connections but want to use a new one, open the **Select connection** list and select **+ New connection.**
2. Set the source access details according to your cloud service:
   * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#bigquery-数据源位置">BigQuery</Anchor>
   * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#snowflake-数据源位置">Snowflake</Anchor>
   * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#云存储桶的数据源位置">Amazon S3 and GCS</Anchor>
   * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#本地文件的数据源位置">Local file system</Anchor>
3. Select how new data should be handled. For more information, see: <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Set source sync method</Anchor>.
4. Click **Next**.

</Accordion>

<div id="map-onsite-conversion-source-fields" />

<Accordion title="Map on-site conversion source fields">

If a custom source is used to provide conversion events to DCP, map your on-site custom conversion source fields to their corresponding DCP fields.

> 📘 **Note**
>
> The **DCP conversion events database** stores all the conversion events of the current collaboration under a unitary scheme, including conversion events originating from **in-app events** or **off-site campaigns** (if you’re running a combined on-site off-site campaign).

**Load conversion source fields**

If the conversion source fields are not already loaded, you might have to load them manually to have them mapped to DCP fields.

To load conversion source fields, follow these steps:

1. In the **Map source fields** step, click **Load fields from source**.
2. For information about how to manually load fields, see: <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-加载您的数据源字段">Load your source fields</Anchor>.

**Auto-map conversion fields**

When conversion source fields are loaded, DCP automatically maps them to their corresponding DCP fields. Auto mapping can take up to 10 seconds. A banner displays the mapping result, showing how many fields were mapped and listing any source columns that could not be matched.

To re-trigger auto mapping, click **Update mapping**.

**Map conversion fields**

If the conversion source fields are loaded, you can map them to the DCP fields.

To map the conversion custom source fields, follow these steps

1. If you are setting a **combined** **on-site and off-site campaign**, expand **Data for on-site attribution;** otherwise, skip to the step below.
2. Map all required fields under **Required**.
3. (Optional) Expand **Optional enrichment data** to map additional fields.

   > 📘 **Note**
   >
   > If the campaign is combined with an Off-site campaign, and you map a field (for example, Event ID) that's already mapped in an off-site channel, you'll be prompted with an **Override field?** message. Click **Yes, continue** to confirm and apply the mapping across channels.

4. Click **Save**. The **`{source name}` source created** message is displayed.[<Image alt="" src="https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png" width="40.33%" />](https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png)

</Accordion>

<div id="map-offsite-conversion-source-fields" />

<Accordion title="Map off-site conversion source fields">

If a custom source is used to provide conversion events from off-site campaigns, map your off-site custom conversion source fields to their corresponding DCP fields.

> 📘 **Note**
>
> The **DCP conversion events database** stores all the conversion events of the current collaboration under a unitary scheme, including conversion events originating from **in-app events** or **on-site campaigns** (if you’re running a combined on-site off-site campaign).

**Load conversion source fields**

If the conversion source fields are not already loaded, you might have to load them manually to have them mapped to DCP fields.

To load conversion source fields, follow these steps:

1. In the **Map source fields** step, click **Load fields from source**.
2. For information about how to manually load fields, see: <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-加载您的数据源字段">Load your source fields</Anchor>.

**Auto-map conversion fields**

When conversion source fields are loaded, DCP automatically maps them to their corresponding DCP fields. Auto mapping can take up to 10 seconds. A banner displays the mapping result, showing how many fields were mapped and listing any source columns that could not be matched.

To re-trigger auto mapping, click **Update mapping**.

**Map conversion fields**

If the conversion source fields are loaded, you can map them to the DCP fields. When you share conversion data with external platforms like Meta or Google, AppsFlyer sends only the fields required for each partner to match conversions against their own campaign engagement events.

The fields shown here depend on the conversion source types you selected during setup:

1. If you are setting a **combined** **on-site and off-site campaign**, expand **Data for off-site attribution;** otherwise, skip to the step below.
2. Turn on **Meta Ads** or **Google Ads,** depending on your data sources:

   > 📘 **Note**
   >
   > When you share conversion data with external platforms like Meta or Google, AppsFlyer sends only the fields required for each partner to match conversions against their own campaign engagement events.


   **Meta Ads field mapping**

   Map the fields under **Source fields** to their corresponding fields under **DCP fields**. The DCP fields listed here reflect the required parameters for Meta Ads.

   * Map all six required fields under **Required**.
   * Expand **Optional enrichment data** to map additional fields (for example, First name, IDFA, and email).

   **Google Ads field mapping**

   Map the fields under **Source fields** to their corresponding fields under **DCP fields**. The DCP fields listed here reflect the required parameters for Google Ads.

   * Map all five required fields under **Required**.
   * Map at least one identifier under **At least one is required**.
   * Expand **Optional enrichment data** to map recommended fields like revenue, client user agent, or hashed identifiers.

   > 📘 **Note**
   >
   > If the campaign is combined with an Off-site campaign, and you map a field (for example, Event ID) that's already mapped in an off-site channel, you'll be prompted with an **Override field?** message. Click **Yes, continue** to confirm and apply the mapping across channels.

3. Click **Save** to complete the source setup.

</Accordion>

<div data-zendesk-anchors="h_01K38T7G97M4403CPYYVG4F0SG=prerequisites set-up-onsite-campaign-conversions=set-up-on-site-campaign-conversions h_01K38T7G970AVGNTPN6JN7E5SC=set-up-on-site-campaign-conversions set-up-offsite-campaign-conversions=set-up-off-site-campaign-conversions h_01K38T7G97KP9NHFPPFG3F4992=set-up-off-site-campaign-conversions set-up-onsite-and-offsite-conversions=set-up-on-site-and-off-site-conversions h_01K38T7G97ZXZZQ48ZRY4A019F=set-up-on-site-and-off-site-conversions h_01K38T7G975KF5036EZTNA4NYJ=configuration-activities h_01K38T7G974NCK1XE35KG4CF79=prepare-conversion-data h_01K38T7G97156TM1AJD7HTNZ2K=open-conversion-settings h_01K38T7G97VGR60QBE1YP565XQ=note h_01K38T7G975CFGND94MK9B4PZS=set-conversion-data-provision-method h_01K38T7G979CKD39QCFV7ZESY5=set-conversion-source-location h_01K38T7G97XNE4AS4YE64QWK80=map-onsite-conversion-source-fields h_01K38T7G9738EZBAM1XVMASGK0=note-3 h_01K38T7G97HV111FQ6CQCQMXHH=note-5 h_01K38T7G976GHY5W6YDHJD1DY7=map-offsite-conversion-source-fields h_01K38T7G97WFBS0HHX1ASR2F5W=note-3 h_01K38T7G97MZF6RYY3YRG2EVPQ=note-4 h_01K38T7G976MJZWGDYMK6EB76A=note-5" />

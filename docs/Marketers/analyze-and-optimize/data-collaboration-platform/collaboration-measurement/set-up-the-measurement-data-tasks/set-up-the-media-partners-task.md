---
title: Set up the Media partners task
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2025-08-18T11:36:01Z'
  edited_at: '2025-08-26T00:01:05Z'
  id: 38191067035153
  locale: en-us
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/38191067035153-Set-up-the-Media-partners-task
---
**At a glance:** Learn how to configure media partners for off-site campaigns.

Before you can share eligible conversions with your <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaigns">off-site campaign</Anchor> media partners and receive aggregated performance data in response, you must first connect DCP to the media account that activates the campaign. This connection tells AppsFlyer how to send the conversion data to the media partner.

## Prerequisites

Before the Media partners task can be set up, the collaboration owner needs to assign it to the collaborator who owns the third-party account (e.g, Facebook or Google). For more information, see Assign configuration tasks

<div id="create-a-media-partner-connection" />

<Accordion title="Create a media partner connection">

> 📘 **Note**
>
> The **Media Partners** task appears on the **Measurement settings** page only when you set up an <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaigns">off-site campaign</Anchor> that uses a custom source as the provisioning method. For more information, see: <Anchor target="_blank" href="/marketers/docs/set-up-the-conversions-task#set-conversion-data-provision-method">Set conversion data provision method</Anchor>

To select or create a media partner connection, follow these steps:

1. On the **Measurement settings** page, click the **Media partners** task.

   > 📘 **Note**
   >
   > * If the **Media partners** dialog is locked, it means that the **Media partners** task has been assigned to your collaborator and that you cannot view its content. If you are the collaboration owner, you can unlock it and reassign the task to yourself. However, any previous settings will be deleted, and the task will be reset.
   > * If the **Media partners** pane is grayed out, ask the collaboration owner to assign you the Conversion task.

2. In the Media partners dialog, click **+ Connect media partner**.
3. In the **Connect media partner** dialog, create or select a media partner connection to the media account that activates the campaign:
   * **If an existing connection is available, select it:**
     * In the **Select connection** dropdown, choose an existing connection.
   * **If no connections exist, create one:**
     1. Click **+ New connection**.
     2. In the **New media partner connection** window, select a media partner such as **Meta Ads** or **Google Ads**.
     3. In the **Connection name** field, enter a name for the new connection.
     4. Click **Login to [Media Partner]** and complete the authentication in the media partner login window.
     5. Click **Save** after the authentication is completed. After it is saved, the new connection is auto-selected in the **Select connection** dropdown of the **Connect media partner** dialog.

</Accordion>

<div id="set-the-google-ads-conversion-action-id-parameter" />

<Accordion title="Set the Google Ads Conversion action ID parameter">

If your media partner is Google Ads, provide DCP with the Conversion action ID parameter. The Conversion action ID is obtained from your Google Ads account and included in the conversion data sent to Google Ads. The Conversion Actio**n** must be of type `UPLOAD_CLICKS`.

To learn more about Google Ads’ Conversion action, see the <Anchor target="_blank" href="https://support.google.com/google-ads/answer/12216226?hl=en">Google Ads documentation</Anchor>.

To set the Google Ads Conversion Action ID, follow these steps:

1. From the **Select connection** drop-down box, select a Google Ads connection.
2. In the **Connect media partner** dialog, populate **at least one** of the following fields with the Google Ads conversion action ID. **Note:** You can use the same ID across multiple web or mobile assets, and you may leave some assets unassigned. However, assets without a Conversion Action ID will not be attributed.

   * **Web conversion action:** The conversion action ID used for conversion events created on the collaborator website. This must be a **Conversion Action** of type `UPLOAD_CLICKS`.
   * **App conversion action (per app):** The conversion action ID used for conversion events created on the collaborator app. Enter the corresponding Conversion Action ID, also of type `UPLOAD_CLICKS`.

   > 📘 **Note**
   >
   > These Conversion Actions should be kept **exclusive to DCP measurement** and should not be used for other traffic.

3. Click **Done** to return to the main dialog.
4. Confirm the connection is listed, then click **Save**.
5. On the **Measurement settings** page, verify the media partner shows a green check mark and status as **Connected**.

</Accordion>

<div id="set-the-meta-ads-meta-pixel-and-dataset-id-parameters" />

<Accordion title="Set the Meta Ads Meta Pixel and Dataset ID parameters">

If your media partner is Meta Ads, provide DCP with the Meta Pixel and Dataset ID parameters. The Meta Pixel and Dataset ID are obtained from your Meta Ads account and included in the conversion data sent to Meta Ads.

See the Meta Ads documentation about <Anchor target="_blank" href="https://www.facebook.com/business/help/952192354843755?id=1205376682832142">Meta Pixel</Anchor> and <Anchor target="_blank" href="https://www.facebook.com/business/help/5818684664831465?id=490360542427371">Dataset ID</Anchor>.

To set the Google Ads Conversion Action ID, follow these steps:

1. From the **Select connection** drop-down box, select a Meta Ads connection.
2. In the **Connect media partner** dialog, populate **at least one** of the following fields with the Meta or Pixel IDs. **Note:** You may leave some assets unassigned. However, assets without a Conversion Action ID will not be attributed.

   * **Meta Pixel:** The ID used for conversion events created on the collaborator website.
   * **Dataset ID (per app):** The ID used for conversion events created on the collaborator app.

   > ❗️ **Warning**
   >
   > The Dataset and Meta Pixel must meet the following conditions:
   >
   > * Created specifically for DCP.
   > * Must **not receive any conversions directly** from the client.
   > * Meta Pixel and Dataset ID are interchangeable.


   > 📘 **Note**
   >
   > The **system user** whose credentials are shared with DCP must:
   >
   > * Have **access** to the Dataset.
   > * Be granted **ads\_read** permission.

3. Click **Done** to return to the main dialog.
4. Confirm the connection is listed, then click **Save**.
5. On the **Measurement settings** page, verify the media partner shows a green check mark and status as **Connected**.

</Accordion>

<div data-zendesk-anchors="h_01K3G4VZX9X67EG0AA7GASSR51=prerequisites h_01K3G4VZX9QBCX8NGQJ6GV02CS=create-a-media-partner-connection h_01K3G4VZX90X7GFX0S274EP5Y4=note h_01K3G4VZX9GX7JRZ7ZJPSG50VS=note-1 h_01K3G4VZX9S8V2DVCNGNBHEFAD=set-the-google-ads-conversion-action-id-parameter h_01K3G4VZX93P0K0B0R4DR1JMB3=note-2 h_01K3G4VZX9WC21793Q33431PCB=set-the-meta-ads-meta-pixel-and-dataset-id-parameters h_01K3G4VZX9KADAF2XXFEWVXG81=warning h_01K3G4VZXAQBHPPE91WM7R2REH=note-3" />

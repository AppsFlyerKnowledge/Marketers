---
title: "Set up the Media partners task"
excerpt: "Learn how to configure and connect media partners like Google Ads and Meta Ads for off-site campaigns in DCP."
x-zendesk:
  id: 38191067035153
  url: https://support.appsflyer.com/hc/en-us/articles/38191067035153-Set-up-the-Media-partners-task
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Set up the measurement data tasks
  section_id: 38035061674769
  position: 3
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-yael-sharabi, Marketers, Data Management]
  labels: []
  promoted: false
  comments_disabled: false
  created_at: '2025-08-18T11:36:01Z'
  edited_at: '2025-08-26T00:01:05Z'
---
At a glance: Learn how to configure media partners for off-site campaigns.

Before you can share eligible conversions with your [off-site campaign](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns) media partners and receive aggregated performance data in response, you must first connect DCP to the media account that activates the campaign. This connection tells AppsFlyer how to send the conversion data to the media partner.

## Prerequisites

Before the Media partners task can be set up, the collaboration owner needs to assign it to the collaborator who owns the third-party account (e.g, Facebook or Google). For more information, see Assign configuration tasks

## Create a media partner connection

> 📘 Note
>
> The **Media Partners** task appears on the **Measurement settings** page only when you set up an [off-site campaign](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns) that uses a custom source as the provisioning method. For more information, see: [Set conversion data provision method](/docs/set-up-the-conversions-task#set-conversion-data-provision-method)

To select or create a media partner connection, follow these steps:

1. On the **Measurement settings** page, click the **Media partners** task.

> 📘 Note
>
> - If the **Media partners** dialog is locked, it means that the **Media partners** task has been assigned to your collaborator and that you cannot view its content. If you are the collaboration owner, you can unlock it and reassign the task to yourself. However, any previous settings will be deleted, and the task will be reset.
> - If the **Media partners** pane is grayed out, ask the collaboration owner to assign you the Conversion task.

2. In the Media partners dialog, click **\+ Connect media partner**.
3. In the **Connect media partner** dialog, create or select a media partner connection to the media account that activates the campaign:
   - **If an existing connection is available, select it:**      - In the **Select connection** dropdown, choose an existing connection.
   - **If no connections exist, create one:**     1. Click **\+ New connection**.
     2. In the **New media partner connection** window, select a media partner such as **Meta Ads** or **Google Ads**.
     3. In the **Connection name** field, enter a name for the new connection.
     4. Click **Login to [Media Partner]** and complete the authentication in the media partner login window.
     5. Click **Save** after the authentication is completed. After it is saved, the new connection is auto-selected in the **Select connection** dropdown of the **Connect media partner** dialog.

## Set the Google Ads Conversion action ID parameter

If your media partner is Google Ads, provide DCP with the Conversion action ID parameter. The Conversion action ID is obtained from your Google Ads account and included in the conversion data sent to Google Ads. TheConversion Actio **n** must be of type `UPLOAD_CLICKS`.

To learn more about Google Ads’ Conversion action, see the [Google Ads documentation](https://support.google.com/google-ads/answer/12216226?hl=en).

To set the Google Ads Conversion Action ID, follow these steps:

1. From the **Select connection** drop-down box, select a Google Ads connection.
2. In the **Connect media partner** dialog, populate **at least one** of the following fields with the Google Ads conversion action ID. **Note:** You can use the same ID across multiple web or mobile assets, and you may leave some assets unassigned. However, assets without a Conversion Action ID will not be attributed.

   - **Web conversion action:** The conversion action ID used for conversion events created on the collaborator website. This must be a **Conversion Action** of type `UPLOAD_CLICKS`.
   - **App conversion action (per app):** The conversion action ID used for conversion events created on the collaborator app. Enter the corresponding Conversion Action ID, also of type `UPLOAD_CLICKS`.

> 📘 Note
>
> These Conversion Actions should be kept **exclusive to DCP measurement** and should not be used for other traffic.

3. Click **Done** to return to the main dialog.
4. Confirm the connection is listed, then click **Save**.
5. On the **Measurement settings** page, verify the media partner shows a green check mark and status as **Connected**.

## Set the Meta Ads Meta Pixel and Dataset ID parameters

If your media partner is Meta Ads, provide DCP with the Meta Pixel and Dataset ID parameters. The Meta Pixel and Dataset ID are obtained from your Meta Ads account and included in the conversion data sent to Meta Ads.

See the Meta Ads documentation about [Meta Pixel](https://www.facebook.com/business/help/952192354843755?id=1205376682832142) and [Dataset ID](https://www.facebook.com/business/help/5818684664831465?id=490360542427371).

To set the Google Ads Conversion Action ID, follow these steps:

1. From the **Select connection** drop-down box, select a Meta Ads connection.
2. In the **Connect media partner** dialog, populate **at least one** of the following fields with the Meta or Pixel IDs. **Note:** You may leave some assets unassigned. However, assets without a Conversion Action ID will not be attributed.

   - **Meta Pixel:** The ID used for conversion events created on the collaborator website.
   - **Dataset ID (per app):** The ID used for conversion events created on the collaborator app.

> 🚧 Warning
>
> The Dataset and Meta Pixel must meet the following conditions:
>
>    - Created specifically for DCP.
>    - Must **not receive any conversions directly** from the client.
>    - Meta Pixel and Dataset ID are interchangeable.

> 📘 Note
>
> The **system user** whose credentials are shared with DCP must:
>
>    - Have **access** to the Dataset.
>    - Be granted **ads\_read** permission.

3. Click **Done** to return to the main dialog.
4. Confirm the connection is listed, then click **Save**.
5. On the **Measurement settings** page, verify the media partner shows a green check mark and status as **Connected**.
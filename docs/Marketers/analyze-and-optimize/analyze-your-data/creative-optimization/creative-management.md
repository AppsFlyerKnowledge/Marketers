---
title: Creative Management
excerpt: >-
  Creative Management helps you centralize, review, and launch creatives faster.
  Use it to sync creatives from your creative storage, understand creative
  activity status across media sources, easily find relevant creatives, and
  upload them directly to supported media source campaigns.
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2025-09-17T12:01:55Z'
  edited_at: '2026-10-07T11:34:33Z'
  id: 39137008313105
  locale: en-us
  section: Creative Optimization
  section_id: 4419063475217
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/39137008313105-Creative-Management
---
## About Creative Management

Creative Management is a centralized hub for managing creative assets across their lifecycle, from storage sync to media source upload.

Use Creative Management to:

* Sync creatives from creative storage.
* Easily search and review creatives in a centralized gallery.
* Understand creative activity status across media sources.
* Prioritize creatives with AI-driven pre-launch scoring.
* Upload creatives directly to campaigns across media sources.
* Review upload outcomes and see which creatives were uploaded successfully or failed.

Built for scale, Creative Management helps marketing and creative teams reduce manual work, optimize time-to-launch, and boost campaign performance.

## Get started

**Prerequisites**

An AppsFlyer account with a [Creative Optimization](/docs/creative-optimization-guide) subscription. To sign up for Creative Management, contact your CSM or write to [hello@appsflyer.com](mailto:hello@appsflyer.com). A free trial may also be available.

**To get started using Creative Management, follow the steps below:**

<div id="sync-creatives-from-the-creative-storage" />

<Accordion title="Sync creatives from creative storage">

Creative Management can sync creatives from connected storage. Once the connection is saved, Creative Management pulls creatives from the connected storage and keeps the library up to date as new creatives are added.

Creative Management currently supports Google Drive and Dropbox. Each source has a different connection flow.

**Supported storage connections include:**

* [Google Drive](#connect-google-drive)
* [Dropbox](#connect-dropbox)

#### Connect Google Drive

**To connect a Google Drive folder:**

1. In AppsFlyer, go to **Optimize > Creative Management**.

**![Click Creative Management New.png](https://files.readme.io/c4ae98a4409b0766c9bd41e2f153d67c3d6168d31af82dadd1f43f345678878e-40988213459217.png)**

2. Click **Creative connections**.

![click Creative connection.png](https://files.readme.io/a1ba600e90389351dc119bb00a358d14909eb92a3fc0b8391e3efa7650992ae2-small-48939135740689.png)

3. Click **Add connections**.
4. Select **Google Drive**.
5. In Google Drive, give AppsFlyer access to the folder that contains your creatives by sharing the folder with viewer permissions for the AppsFlyer service account: `creative-google-account-drive@creative-prod.iam.gserviceaccount.com`.
   * Creative Management syncs creatives from the selected folders and their subfolders.
6. Return to Creative Management and enter the folder URL.
7. Select the relevant app. This step is optional, but we recommend it because it helps organize and match creatives correctly.
8. Click **Add URL**.
9. Repeat the previous two steps to connect multiple folders at once.

![image (49).png](https://files.readme.io/c29dab5dc76470b5e99e8efd8accaec7bfd1c6878f3bcfe8d58d7b650063065b-48939152741393.png)

10. Click **Connect**.

#### Connect Dropbox

Before connecting Dropbox, make sure you're logged in to Dropbox with the account that has access to the relevant creative folders.

**To connect Dropbox folders:**

1. In AppsFlyer, go to **Optimize > Creative Management**.
2. Click **Creative connections**.
3. Click **Add connections**.
4. Select **Dropbox**.
5. In the Dropbox login popup, connect to the relevant Dropbox account.
6. In the connection modal, click **Choose folders**, then select the folders you want to connect.
   * Creative Management syncs creatives from the selected folders and their subfolders.

![click Choose folders.png](https://files.readme.io/13d62001deedecfb95a202aa54d36a1d7948d36aa76ac2a93b056be54d2ffe01-48939135745937.png)

7. Select the relevant app for each folder. This step is optional, but we recommend it because it helps organize and match creatives correctly.
8. Click **Connect**.

After the connection is created, Creative Management starts pulling and processing the creatives. Once processing is complete, the creatives appear in the gallery with metadata such as creative type, sync date, launch date, status, and available versions.

</Accordion>

<div id="browse-and-select-creatives" />

<Accordion title="Browse and select creatives">

The Creative Management gallery is where you review, search, filter, and select creatives.

Each creative card represents one creative. A creative may include multiple versions, such as different resolutions or formats. From the card, you can quickly understand whether the creative is new, active, or inactive across media sources, and view high-level metadata such as when it was first launched and when it was synced to Creative Management. Each new creative is automatically analyzed and scored to help you choose the best ones before launch. Scores range from C (less likely to succeed) to A (ready to scale), helping you prioritize top-performing creatives with confidence.

![image (52).png](https://files.readme.io/a295ed00e01564b04bd32a7ce515cf41012a62324a8fcd350d1b4b9113e0cacb-small-48939135746577.png)

#### Filter creatives

Use the search bar and filters to find the relevant creatives by:

* **Search bar**: Search for creatives by ID or name.
* **App**: Focus on creatives related to a specific app.
* **Media source**: Find creatives that are active or were active on a specific network.
* **Creative type**: Filter by image, video, or HTML.
* **Creative status**: Filter by New, Active, or Inactive creatives.
* **Creative score**: Focus on new creatives with a specific AI score.
* **Sync date**: Find creatives added to Creative Management during a specific period.
* **Launch date**: Find creatives first launched during a specific period.
* **Resolution**: Find creatives with a specific available version.

By default, creatives are sorted by sync date, so recently added creatives appear first. You can also sort by launch date or creative name.

</Accordion>

<div id="upload-creatives-to-media-sources" />

<Accordion title="Upload creatives to media sources">

When you're ready to launch creatives, select one or more creatives from the gallery and click **Upload to media source**.

Creative Management currently supports uploads only for app promotion campaigns. The upload setup changes based on the selected media source because each network has different requirements and destination structures.

For all supported media sources, you can upload creatives to multiple destinations at once.

**Supported media sources include:**

* [Google Ads](#google-ads)
* [Meta Ads](#meta-ads)
* [TikTok Ads](#tiktok-ads)
* [Mintegral](#mintegral)
* [Unity Ads](#unity-ads)
* [AppLovin](#applovin)

#### Google Ads

For Google Ads, you can upload creatives to existing app promotion ad groups.

1. Select creatives from the gallery.
2. Click **Upload to media source**.
3. Choose Google Ads.
4. Select the required destination details: Google account and ad groups.
   * You can use the campaign filter to narrow the search for specific ad groups.
   * You don't need to add the YouTube channel.
5. If the upload action includes videos, select whether the videos uploaded are made for kids.
6. Select the creatives from the **All creatives** section and assign them to the ad groups.
7. If a creative has multiple versions, select the relevant ones you want to upload.
8. Review the setup and any validation messages.
9. Click **Upload to Google Ads**.

![click Upload to Google Ads.png](https://files.readme.io/5280a1a396584e6874d8a2c24882fb9be4b25747d322fab607944da57a8fcdc9-48939152742545.png)

> 📘 **Note**
>
> Before uploading a large batch for the first time, we recommend testing with a single creative to confirm it appears correctly in the selected media source.

#### Meta Ads

For Meta, you can create ads inside existing ad sets.

1. Select creatives from the gallery.
2. Click **Upload to media source**.
3. Choose Meta Ads.
4. Select the required destination details: Meta ad account and ad sets.
   * You can use the campaign filter to narrow the search for ad groups.
5. Create as many new ads as needed.
   * If you selected multiple ad sets, each ad is created in each ad set.
6. Select the creatives from the **All creatives** section and assign them to the ads.
7. If a creative has multiple versions, select the relevant ones you want to upload.

![Meta Ads.png](https://files.readme.io/56c387af74f4904921770abdee23e0d27a92e8f26c40d2d4fa46a4c42a4e2bb0-48939152743441.png)

8. Review the setup and any validation messages.
9. Click **Next**.
10. Set up ad-level fields: Facebook Page, Instagram profile, primary text, headline, CTA, launch status, and whether to allow Meta enhancements for your creatives.
    * By default, this setup applies to all new ads created. You can edit specific ads by choosing them from the **Customize a specific ad** dropdown.
11. Click **Create ads in Meta**.

![image (55).png](https://files.readme.io/95125f551e731428a8d18a7ba1162246a867cdff4e0d34aee3950e08446c5eeb-48939152744209.png)

#### TikTok Ads

For TikTok Ads, you can upload creatives to existing app promotion ads.

1. Select creatives from the gallery.
2. Click **Upload to media source**.
3. Choose TikTok.
4. Select the required destination details: TikTok ad account and ads.
   * You can use the campaign and ad group filters to narrow the search for specific ads.
   * You don't need to add the YouTube channel.
5. Select the creatives from the **All creatives** section and assign them to the ads.
6. If a creative has multiple versions, select the relevant ones you want to upload.
7. Review the setup and any validation messages.
8. Click **Upload to TikTok**.

#### Unity Ads

> 📘 **Note**
>
> For Unity Ads, you can currently upload creatives only to Unity's creative library. Direct upload to campaigns will be added soon.

1. Select creatives from the gallery.
2. Click **Upload to media source**.
3. Choose **Unity Ads**.
4. Select the app you want the creatives to be associated with, and the language of the creatives (optional).
5. If a creative has multiple versions, select the relevant ones you want to upload.
6. Click **Upload to Unity Ads**.

#### Mintegral

> 📘 **Note**
>
> For Mintegral, you can currently upload creatives only to Mintegral's creative library. Direct upload to campaigns will be added soon.

1. Select creatives from the gallery.
2. Click **Upload to media source**.
3. Choose **Mintegral**.
4. Select the Mintegral account you want the creatives to be associated with.
5. If a creative has multiple versions, select the relevant ones you want to upload.
6. Click **Upload to Mintegral**.

#### AppLovin

> 📘 **Note**
>
> Access to AppLovin's campaign management API is available to select advertisers. To request access or learn more about eligibility, please reach out to your AppLovin representative.

For AppLovin, you can upload creatives to existing creative sets or create new creative sets.

1. Select creatives from the gallery.
2. Click **Upload to media source**.
3. Choose AppLovin.
4. Choose whether to create new creative sets or upload to existing ones.

**To create a new creative set:**

1. Select the AppLovin account.
2. Select the campaigns you want the creative set to be created in.
3. Enter a creative set name.
4. Select the launch status.
5. Click **Add**. You can create as many creative sets as needed.
6. Select the creatives from the **All creatives** section and assign them to the creative sets.
7. If a creative has multiple versions, select the relevant ones you want to upload.
8. Review the setup and any validation messages.
9. Click **Upload to AppLovin**.

**To upload to an existing creative set:**

1. Select the AppLovin account.
2. Select the creative sets you want to upload to.
   * You can use the campaign filter to narrow the search for specific creative sets.
3. Select the creatives from the **All creatives** section and assign them to the creative sets.
4. If a creative has multiple versions, select the relevant ones you want to upload.
5. Review the setup and any validation messages.
6. Click **Upload to AppLovin**.

</Accordion>

<div id="review-upload-results" />

<Accordion title="Review upload results">

After you start an upload, the upload window closes automatically, and Creative Management continues the upload process in the background while you keep working.

To review upload results, click **Upload history** from the Creative Management gallery.

Upload history shows previous upload jobs and their results, including:

* Media source and destination.
* Upload status: Success, Partial success, or Failed.
* Number of creatives uploaded out of the total selected.
* Time the upload finished.
* Details for creatives that failed.

If an upload finishes with partial success or failure, Creative Management shows an indication on Upload history so you can review the issue later. In the details view, failed creatives appear with a failure reason.

</Accordion>

<div id="creative-activity-status" />

<Accordion title="Creative activity status">

Creative status helps you understand where a creative is used across your connected media sources.

In the gallery, each creative can show whether it is:

* **New**: The creative hasn't been launched yet.
* **Active**: The creative is currently running.
* **Inactive**: The creative was active before, but isn't currently running.

Creative Management also helps you understand where your active creatives are currently running. Click a creative card to open the right panel, where you can see exactly which campaigns and ad groups the creative is active in.

Use status information to answer questions such as:

* Which new creatives should I upload next?
* Which creatives are active on one media source and can be tested on another?
* Which creatives were tested before and may be worth relaunching?
* Which creatives are active in a test campaign and should be uploaded to more campaigns?

</Accordion>

## Traits and limitations

| Trait | Description |
| --- | --- |
| Campaign scope | Creative Management currently supports app promotion campaigns only. |
| Supported storage sources | Repository sync is currently supported for Google Drive and Dropbox. |
| Upload destinations vary by network | Supported upload destinations and required fields vary by media source. |
| Upload method varies by network | Upload method varies by network.  <br />Google Ads, Meta Ads, and TikTok support upload directly into campaigns (as ads or creative sets); Unity Ads and Mintegral currently support upload to the network's creative library only. |
| Asset requirements | Creative file formats, dimensions, duration, and size must meet each network's requirements. |
| Upload history scope | Upload history reflects the upload result, not the creative's ongoing delivery or moderation status. |

> 📘 **See also**
>
> * [Creative Optimization guide](/docs/creative-optimization-guide)

<div data-zendesk-anchors="h_01KXDN2V1R9SRPFSRGZZ4ZA62S=sync-creatives-from-the-creative-storage h_01KXDN2V1RGCDYJ074FV4KJY8T=connect-google-drive h_01KXDN2V1R75971RE5ECTDM8TM=connect-dropbox h_01KXDN2V1RAA882M55HK9152D6=browse-and-select-creatives h_01KXDN2V1RHJJZC67ZM84TNT0Y=filter-creatives h_01KXDN2V1R8CXZ4XGTX656XRWF=upload-creatives-to-media-sources h_01KXDN2V1RE8748NWSCJP824PD=google-ads h_01KXDN2V1R31MABH1A3G0T9B84=note h_01KXDN2V1RG25RR7BXYAFVEAT7=meta-ads h_01KXDN2V1RBANB482286YP1QSY=tiktok-ads h_01KXDN2V1R52Y91AZNVGPPWW44=unity-ads h_01KXDN2V1RF9TZ25DFYQ91RVRC=note-1 h_01KXDN2V1REED32CRW83W7MMC9=mintegral h_01KXDN2V1SVWASV4KGJJ2VC162=note-2 h_01KXDN2V1RSFB2GHDPN95S90EJ=applovin h_01M1H2RMVW2CYMV7KBBSHJ9686=note-3 h_01KXDN2V1S8NZP8F4QN51NS3XP=review-upload-results h_01KXDN2V1SC0PHRY810NJG6QY3=creative-activity-status h_01KXDN2V1SDNR1Z5FTKEJNDZF3=see-also" />

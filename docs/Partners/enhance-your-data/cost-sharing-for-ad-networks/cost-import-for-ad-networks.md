---
title: "Cost Import for ad networks"
excerpt: "Learn how ad networks can report campaign costs directly to AppsFlyer via CSV files using email or file upload."
x-zendesk:
  id: 360002868097
  url: https://support.appsflyer.com/hc/en-us/articles/360002868097-Cost-Import-for-ad-networks
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Cost sharing for ad networks
  section_id: 6551141756177
  position: 1
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-maytav-avnat, ROI360, Ad Networks]
  labels: [Ad Networks, Partners, Gray, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2019-10-20T06:03:13Z'
  edited_at: '2025-09-10T14:33:39Z'
---
**At a glance:** Learn how ad networks can report the advertiser's campaign costs directly to AppsFlyer via CSV files.

## Cost Import for ad networks

![AdspendIngestion.jpg](https://files.readme.io/e870005c5f20531a2d06cc78b47a82a8a1f730f2c04728f5d0a5674c1c70129a-24507313816337.jpg)

#### Overview

- Prepare a CSV file containing the ad spend details as follows:
  - Date of spend
  - App ID (multiple apps allowed per file if the apps belong to the same owner)
  - Media source (one per file allowed)
  - Campaign name
  - Spend amount
  - [Optional] Geo
  - [Optional] Currency (default USD)
- Submit the file to AppsFlyer by email/file upload using the ad network account in AppsFlyer.

> 📘 Important
>
> Before you submit files for the first time, the advertiser must grant you, the ad network, Cost Import permission. This needs to be done once for each app and is a very brief process.
>
> Once a file is uploaded, it can't be reverted.

- Monitor and check that no errors were found in the file.

### Submitting ad spend files for ad networks

- Use either the upload or email method to ingest ad spend files.
- 👍 Best practice
  
  Initially, use the upload method as it is easier to resolve CSV formatting issues.
- Ad Networks cannot import agency cost data; only advertisers can.

<Tabs>
<Tab title="Submission by file upload">

**To submit Cost Import files by upload:**

1. [For each app that you work with you need to do this once] [Ask the advertiser to grant you Cost Import permission](/docs/import-cost-data#cost-import-permissions-for-ad-networks).
2. [Prepare the CSV file using this format and schema](/docs/import-cost-data#prepare-csv-file-with-cost-data).
3. Click here to [log in to your AppsFlyer ad network account.](https://hq1.appsflyer.com/auth/login)
4. [Upload and ingest the file](/docs/import-cost-data#upload-file).
5. In the AppsFlyer dashboard, monitor the ingestion:
   - [Status](/docs/import-cost-data#cost-import-dashboard)
   - [Matched rows](/docs/import-cost-data#matched-rows)
   - [Cost Import actions](/docs/import-cost-data#cost-import-dashboard)
6. Additional procedures:
   - [Overwrite previous ingestion](/docs/import-cost-data#cost-import-dashboard)
   - [Revert (cancel)](/docs/import-cost-data#cost-import-dashboard)

</Tab>
<Tab title="Submission by email">

**To submit Cost Imports files by email:**

1. [For each app that you work with you need to do this once] [Ask the advertiser to grant you Cost Import permission](/docs/import-cost-data#cost-import-permissions-for-ad-networks).
2. [Prepare the CSV file using this format and schema](/docs/import-cost-data#prepare-csv-file-with-cost-data).
3. If you don't have an Cost Import token (you'll need it when you email the file):
   - Click here to [log in to your AppsFlyer ad network account](https://hq1.appsflyer.com/auth/login).
   - [Get an Ad Spend token.](/docs/import-cost-data#token-for-email-import) Note: The same token is used for all advertisers.
4. Submit file by [Email](/docs/import-cost-data#email-file)
5. AppsFlyer emails a status report; it notes if the ingest was successful or if issues were found. 

> 📘 Note
>
> If the status mail was not received see [the Cost import dashboard](/docs/import-cost-data#cost-import-dashboard).

6. In the AppsFlyer dashboard monitor the ingestion:
   - [Status](/docs/import-cost-data#cost-import-dashboard)
   - [Matched rows](/docs/import-cost-data#matched-rows)
   - [Cost Import actions](/docs/import-cost-data#cost-import-dashboard)
7. Additional procedures:
   - [Overwrite previous ingestion](/docs/import-cost-data#cost-import-dashboard)
   - [Revert (cancel)](/docs/import-cost-data#cost-import-dashboard)

</Tab>
</Tabs>
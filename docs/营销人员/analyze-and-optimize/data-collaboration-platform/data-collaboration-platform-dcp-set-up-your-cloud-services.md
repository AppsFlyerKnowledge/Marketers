---
title: Data Collaboration Platform (DCP) - Set up your cloud services
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2024-04-28T14:01:34Z'
  edited_at: '2026-10-13T00:17:44Z'
  id: 24604528827921
  locale: zh-cn
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/zh-cn/articles/24604528827921
---
> **At a glance:** Set up your cloud services so you can connect your source data to DCP and export audiences to your cloud storage buckets.

## About cloud service setup

DCP uses two types of connections to move data between your cloud services and the platform:

* **Source connections:** Enables you to connect your first-party data to DCP for collaboration and audience creation.
* **Cloud storage connections:** Enables you to export your audiences to your cloud storage buckets after each audience update.

Setting up a connection is a two-step process:

* **Step 1:** Use your cloud service's interface to prepare it for use with DCP.
* **Step 2:** Connect it to DCP in the AppsFlyer platform. See <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-add-connections">Data Collaboration Platform (DCP) - Add connections</Anchor>.

The table below shows which services are supported for each connection type:

| Cloud service | Source (inbound) | Cloud storage (outbound) |
| --- | --- | --- |
| Amazon S3 | ✓ | ✓ |
| Google Cloud Storage (GCS) | ✓ | ✓ |
| BigQuery | ✓ | - |
| Snowflake | ✓ | - |
| Salesforce Cloud/CRM | ✓ | - |

For Amazon S3 and GCS, the same bucket setup and permissions apply for both source and cloud storage connections, so no separate setup is needed for each direction. Creating a source connection automatically creates a matching cloud storage connection (and vice versa), and deleting one deletes the other, since it's really one underlying connection that's shared across both tabs.

## Set up your cloud services

Select your cloud service below for setup instructions.

<div id="amazon-s3" />

<Accordion title="Amazon S3">

Use the following instructions to prepare an Amazon S3 bucket for use with DCP.

> 📘 **Note**
>
> The following procedure must be performed by your AWS admin.

**To create a bucket:**

1. Log in to the AWS console.
2. Go to the S3 service.
3. Create the bucket:
   1. Click **Create bucket**.
   2. Complete the **Bucket name**, starting with `af-dcr-`

       and followed by your text, according to the [DCR naming requirements](#dcr-naming-requirements).
   3. Click **Create bucket**.

**To grant AppsFlyer bucket permissions:**

1. Select the bucket you created.
2. Go to the **Permissions** tab.
3. In the **Bucket policy** section, click **Edit**. The **Edit bucket policy** window opens.
4. Paste the following code snippet into the window:

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "AF-DCR-DL",
         "Effect": "Allow",
         "Principal": {
           "AWS": [
             "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",
             "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
           ]
         },
         "Action": [
           "s3:GetObject",
           "s3:ListBucket",
           "s3:DeleteObject",
           "s3:PutObject"
         ],
         "Resource": [
           "arn:aws:s3:::af-dcr-mybucket",
           "arn:aws:s3:::af-dcr-mybucket/*"
         ]
       }
     ]
   }
   ```
5. In the snippet, replace `af-dcr-mybucket` (in the two lines in which it appears) with the name of the bucket you created.
6. Click **Save changes**.

> 🚧 **Important!**
>
> When replacing the bucket name in the snippet, do not overwrite `/*` in the second line in which the bucket name appears.

</Accordion>

<div id="google-cloud-storage-gcs" />

<Accordion title="Google Cloud Storage (GCS)">

Use the following instructions to prepare a GCS bucket for use with DCP.

> 📘 **Note**
>
> The following procedure must be performed by your Google Cloud admin.

**To create a bucket:**

1. Log in to your GCS console.
2. Go to the Cloud Storage Browser page.
3. Create the bucket:
   1. Click **Create bucket**.
   2. Enter your bucket information on the **Create a bucket** page. Include the bucket name, starting with `af-dcr-`

       and followed by your text, according to the [DCR naming requirements](#dcr-naming-requirements).
   3. Click **Continue**.
   4. Click **Create**.

**To grant AppsFlyer bucket permissions:**

1. Select the bucket you created.
2. Go to the **Permissions** tab.
3. In the **Permissions** section, click **+ Add**. The **Add members** window opens.
4. In the **New members** box, enter the following accounts:
   * `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   * `af-data-delivery@af-raw-data.iam.gserviceaccount.com`
5. From the **Role** list, select **Cloud storage** > **Storage Admin**.
6. Click **Save**.

</Accordion>

<div id="bigquery" />

<Accordion title="BigQuery">

BigQuery supports source connections only. Use the following instructions to create a dataset and grant AppsFlyer permissions.

> 📘 **Note**
>
> The following procedure must be performed by your Google Cloud admin.

**To create a dataset:**

1. Log in to your Google Cloud console.
2. Go to the BigQuery page.
3. In a new or existing Google Cloud project, create a dataset for the exclusive use of DCP:
   1. In the left-side panel, click the three-dot menu icon (**View actions**) to the right of the project ID.
   2. Select **Create dataset**.
   3. In the right-side panel that opens, enter the name of the dataset and select other options as required.
      * You can use any name: letters, numbers, and underscores only.
        * **Recommended:** Use a name that indicates the dataset is being used for a source connection.
      * Do not use the **Enable table expiration** option, as DCP will be unable to read your data after the tables expire.
   4. Click **Create dataset**.

**To grant AppsFlyer permissions to the dataset:**

1. In the left-side panel, click the three-dot menu icon (**View actions**) to the right of the dataset you created.
2. Select **Share**.
3. In the right-side panel that opens, click **Add principal**.
4. In the **Add principals** section, enter the following account in the **New principals** field:
   * `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
5. In the **Assign roles** section, select **BigQuery** > **BigQuery Data Viewer**.
6. Click **Save**.
7. Click **Close** to close the right-side panel.

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Snowflake supports source connections only. Use the following instructions to create a private share for use by DCP.

> 📘 **Note**
>
> The following procedure must be performed by a Snowflake **Accountadmin**.

**To create a private share:**

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Log in to the Snowflake account</Anchor> that contains the data you want to share with DCP.
2. Switch your role to **Account admin**.
3. From the left-side panel, select **Private Sharing**.
4. On the page that opens, select the **Shared By Your Account** tab.
5. Click **Share**. From the list that opens, select **Create a Direct Share**.
6. Select the tables and/or views you want to share with DCP, then click **Done**.
7. Change the **Secure Share Identifier** and add an optional description as needed.
8. In the **Add accounts in your region by name** field, enter the AppsFlyer Snowflake account for your region:

| Region | AppsFlyer account |
| --- | --- |
| EU West (eu-west-1) | QL63117 |
| US East - N. Virginia (us-east-1) | MWB70410 |
| US East - Ohio (us-east-2) | BM15378 |

9. Click **Create Share**.

</Accordion>

<div id="salesforce-cloudcrm" />

<Accordion title="Salesforce Cloud/CRM">

Salesforce Cloud/CRM supports source connections only. See <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-integration-with-salesforce-data-cloud">DCP - Integration with Salesforce Data Cloud</Anchor> for setup instructions.

</Accordion>

## Traits and limitations

| Trait | Description |
| --- | --- |
| Supported cloud services | Amazon S3 and GCS support both source and cloud storage connections. BigQuery, Snowflake, and Salesforce Cloud/CRM support source connections only. |
| Bucket use | S3 and GCS buckets must be for the exclusive use of DCP. No other service can write data to the bucket. |
| <span id="dcr-naming-requirements"></span>DCR naming requirements | The following naming requirements apply to all DCR data entities, including buckets, folders, and files:<ul><li>**Maximum length:** 200 characters</li><li>**Valid characters:** letters (A-Z, a-z), numbers (0-9), hyphens (-)</li><li>**Invalid characters:** spaces, and all other symbols or special characters</li><li>Numbers and hyphens cannot be the first character of a name</li><li>**Special-purpose characters only:**<ul><li>Equal signs (=): only in <Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version">date and version folder names</Anchor></li><li>Underscores {"(_):"} only in <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#file-format">multi-part GZIP file names</Anchor> or <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#_success-files">{"_SUCCESS"} files</Anchor></li><li>Dots (.): only directly before filename extensions (.csv, .gzip)</li></ul></li></ul> |
| Bucket naming | Bucket names must begin with `af-dcr-` followed by your text. Example: `af-dcr-example-bucket`.<br /><br />[PENDING R&D: confirm whether af-datalocker- prefix should still be listed as an allowed alternative, or removed] |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-add-connections">DCP - Add connections</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-build-and-activate-audiences">DCP - Build and activate audiences</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources">DCP - Create and manage sources</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-guide">Data Collaboration Platform (DCP) guide</Anchor>

<div data-zendesk-anchors="h_01KY1VRHDTX2W1YC4QX1N093GF=about-cloud-service-setup h_01KY1VRHDT63WWBPNNN3QC9N49=set-up-your-cloud-services h_01KY1VRHDT2GRP2MMYTKFNRN3P=amazon-s3 h_01KY1VRHDTYMG39CRENZC971RS=note h_01KY1VRHDVV1ZHTVV5SXGXRZ59=important h_01KY1VRHDVS3S0F22T0EQ5MCKY=google-cloud-storage-gcs h_01KY1VRHDVX4KYCT627NN92TCT=note-2 h_01KY1VRHDVR3CZAZK0PGXDBWRC=bigquery h_01KY1VRHDV8Q3TRG7TBM5TRDYM=note-2 h_01KY1VRHDVSE9WJSDFXYV7W2R3=snowflake h_01KY1VRHDVDDK9B8Y7DKA5GA75=note-3 h_01KY1VRHDV9PJQMAGBY52G9RS8=salesforce-cloudcrm h_01KY1VRHDVT3PYP5QVKNKQ803G=traits-and-limitations h_01KY1VRHDVEWNCDKZYCGWD1SRM=see-also" />

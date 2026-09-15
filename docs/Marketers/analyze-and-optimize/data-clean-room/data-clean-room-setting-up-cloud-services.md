---
title: "Data Clean Room—Setting up cloud services"
excerpt: "Set up data warehouses and cloud storage buckets to share data with the Data Clean Room and receive reports."
---
Preparing to use the Data Clean Room (DCR) involves setting up:

- The cloud services/locations from which the DCR reads first-party data from your systems (custom data sources). These locations are used to create **inbound connections.**
- The cloud services/locations to which the DCR delivers reports after processing. These locations are used to create **outbound connections.**

Creating an inbound or outbound connection is a 2-step process:

- **Step #1 –** Use the interfaces of your selected cloud services to prepare them for use with the DCR (this article).
- **Step #2 –** Use the AppsFlyer platform to connect them to the DCR. (See [Data Clean Room—Working with connections](/docs/data-clean-room-working-with-connections)).

> 📘 Note
>
> See [Data Clean Room—Working with sources](/docs/data-clean-room-working-with-sources#source-format) for complete information about data source requirements:
>
> - Data format *(for all data sources)*
> - Table columns *(for data sources in data warehouses)*
> - File name and format *(for data sources in cloud storage buckets)*

### Supported cloud services

Two types of cloud services are supported for inbound and outbound connections to the DCR:

- **Data warehouses:** BigQuery and Snowflake
- **Cloud storage buckets:** Amazon S3 (AWS) and GCS

You can use one or any combination of these services for inbound and outbound connections.

> 🚧 Important!
>
> - If you will be using multiple custom data sources for a single report, they must be located in cloud storage buckets.
> - It's very common to use the same cloud storage bucket on Amazon S3 or GCS for both inbound and outbound connections. Be sure to follow the [special instructions for that setup](/docs/data-clean-room-setting-up-cloud-services#setting-up-cloud-services-inbound-outbound).

## Setting up cloud services for inbound connections

Prepare your selected cloud services for use with DCR inbound connections according to the instructions in the following tabs.

<Tabs>
<Tab title="BigQuery">

> 📘 Note
>
> The following procedure must be performed by your Google Cloud admin.

**To create a dataset and grant the DCR permissions:**

1. Log in to your Google Cloud console.
2. Go to the BigQuery page.
3. In a new or existing Google Cloud project, create a dataset for the exclusive use of the DCR:
   1. In the **left-side** panel, click the **View actions** button ![BQ_view_actions_button.png](https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png) to the right of the project ID.
   2. Select **Create dataset.**
      ![BQ_create_dataset.png](https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png)
   3. In the **right-side** panel that opens, enter the name of the dataset and select other options as you require.
      - You can use any name that suits you – using letters, numbers, and underscores (\_) only.
        - **Recommended:** Use a name that indicates the dataset is being used for an inbound connection.
      - It is strongly recommended **NOT** to use the **Enable table expiration** option since the DCR would be unable to read the sources after the tables expire.
   4. Click the ![BQ_create_dataset_button.png](https://files.readme.io/242c16aaa7e7f1f96b3392452260fa1c1987a8ebfd276c36630a028baa245b16-13879858133137.png) button.
4. Grant the DCR permissions to the dataset:
   1. In the **left-side** panel, click the **View actions** button ![BQ_view_actions_button.png](https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png) to the right of the dataset you created.
   2. Select **Share.**
   3. In the **right-side** panel that opens, click the ![BQ_add_principal_button.png](https://files.readme.io/77179cb4b9c81faa7cdc13397920699186df15fd1722247ccd8cbecb0cc43bce-13879857984017.png) button.
   4. In the **Add principals** section, enter the following account in the **New principals** field:
      `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. In the **Assign roles** section, select **BigQuery > BigQuery Data Viewer.**
      ![BQ_data_viewer.png](https://files.readme.io/beec60ee830957ff265f8046875d1b8fa006a2c0cb60427ac969d7d45efa8b5b-14964740088721.png)
   6. Click **Save.**
   7. Click **CLOSE** to close the right-side panel.

</Tab>

<Tab title="Snowflake">

> 📘 Note
>
> The following procedure must be performed by a Snowflake **Accountadmin.**

**To create a private share for use by the DCR:**

1. [Log in to the Snowflake account](https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface) that contains the data you want to share with the DCR.
2. Switch your role to **Accountadmin.**
3. From the left-side panel, select **Private Sharing.**
4. In the page that opens, select the **Shared By Your Account** tab.
   ![snowflake_private_sharing.png](https://files.readme.io/e99ddd6acf3a3714ea1818fc1d28489b0ea458abac3519d6e4fe67ab643de5bb-13879858362257.png)
5. Click the **Share** button. From the list that opens, select **Create a Direct Share.**
   ![snowflake_create_direct_share.png](https://files.readme.io/0a33cddd326d03a13da19a1e1b4d75a7f6a9c5479dad2fdcad52f111bc5b4e14-13879858320913.png)
6. Select the tables and/or views that you want to share with the DCR, then click **Done.**
7. According to your needs, change the **Secure Share Identifier** and add an optional description.
8. In the field **Add accounts in your region by name**, enter one of the following AppsFlyer Snowflake accounts, according to your Snowflake account region:

| Region | AppsFlyer account |
| --- | --- |
| EU West (eu-west-1) | QL63117 |
| US East - N. Virginia (us-east-1) | MWB70410 |
| US East - Ohio (us-east-2) | BM15378 |

9. Click the **Create Share** button.

</Tab>

<Tab title="Amazon S3">

> 📘 Note
>
> The following procedure must be performed by your AWS admin.

**To create a bucket and grant AppsFlyer permissions:**

1. Log in to the AWS console.
2. Go to the S3 service.
3. Create the bucket:
   1. Click **Create bucket.**
   2. Complete the **Bucket name**, starting with `af-dcr-` or `af-datalocker-` and followed by your text (according to the DCR naming requirements below).
   3. Click **Create bucket.**
4. Grant AppsFlyer bucket permissions:
   1. Select the bucket you created.
   2. Go to the **Permissions** tab.
   3. In the **Bucket policy** section, click **Edit.** The **Edit bucket policy** window opens.
   4. Paste the following code snippet into the window.

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

   5. In the snippet, replace *`af-dcr-mybucket`* (in the 2 lines in which it appears) with the name of the bucket you created.

> 🚧 Caution!
>
> When replacing the bucket name in the snippet, be sure not to overwrite `/*` in the second line in which the bucket name appears.

   6. Click **Save changes.**

</Tab>

<Tab title="GCS">

> 📘 Note
>
> The following procedure must be performed by your Google Cloud admin.

**To create a bucket and grant AppsFlyer permissions:**

1. Log in to your GCS console.
2. Go to the Cloud Storage Browser page.
3. Create the bucket:
   1. Click **Create bucket.**
   2. Enter your bucket information on the **Create a bucket** page. Include the bucket name, starting with `af-dcr-` or `af-datalocker-` and followed by your text (according to the DCR naming requirements below).
   3. Click **Continue.**
   4. Click **Create.**
4. Grant AppsFlyer bucket permissions:
   1. Select the bucket you created.
   2. Go to the **Permissions** tab.
   3. In the **Permissions** section, click **+ Add.** The **Add members** window opens.
   4. In the **New members** box, enter the following account:
      `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. From the **Role** list, select **Cloud storage** > **Storage Admin.**
      ![dcr_gcs_permissions.png](https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png)
   6. Click **Save.**

</Tab>
</Tabs>

### Cloud storage bucket requirements

The following requirements are relevant to buckets on both cloud services:

- **Use:** The bucket must be for the exclusive use of AppsFlyer Data Clean Room. In other words, no other service can write data to the bucket.
- **Permissions:** AppsFlyer DCR service must be given bucket permissions. See instructions for granting these permissions in the tabs for each cloud service above.
- **Name:** The bucket name must begin with `af-dcr-` or `af-datalocker-` - Example: `af-dcr-example-bucket`
- **DCR naming requirements:** The following naming requirements apply to all DCR data entities (buckets, folders, and files):
  - Maximum length: 200 characters
  - Valid characters:
    - letters `(A-Z, a-z)`
    - numbers `(0-9)`, *cannot be the first character of a name*
    - hyphens `(-)`, *cannot be the first character of a name*
    - Invalid characters:
      - spaces
      - all other symbols or special characters
    - Characters used for special purposes only:
      - equal signs `(=)`, *only where required in* [date and version folder names](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version)
      - underscores `(_)`, *only where used to identify the parts of* [multi-part GZIP files](/docs/data-clean-room-working-with-sources#file-format) *or for naming* [\_SUCCESS files](/docs/data-clean-room-working-with-sources#_success-files)
      - dots `(.)`, *only directly before filename extensions* `(.csv, .gzip)`

## Setting up cloud services for outbound connections

The DCR delivers reports to your selected cloud services using [AppsFlyer Data Locker](/docs/data-locker-for-marketers).

> 📘 Note
>
> Receiving DCR reports does not require a premium subscription to Data Locker. If you are interested in receiving other AppsFlyer reports via Data Locker, contact your CSM or send an email to [hello@appsflyer.com](mailto:hello@appsflyer.com).

Your DCR reports can be delivered to one or more locations on your cloud services (whether or not you use the same services for inbound connections). Prepare them for use with outbound connections according to the instructions in the following tabs.

<Tabs>
<Tab title="BigQuery">

> 📘 Note
>
> The following procedure must be performed by your Google Cloud admin.

**To create a dataset and grant Data Locker permissions:**

1. Log in to your Google Cloud console.
2. Go to the BigQuery page.
3. In a new or existing Google Cloud project, create a dataset for the exclusive use of Data Locker:
   1. In the **left-side** panel, click the **View actions** button ![BQ_view_actions_button.png](https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png) to the right of the project ID.
   2. Select **Create dataset.**
      ![BQ_create_dataset.png](https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png)
   3. In the **right-side** panel that opens, enter the name of the dataset and select other options as you require.
      - You can use any name that suits you – using letters, numbers, and underscores (\_) only.
        - **Recommended:** Use a name that indicates the dataset is being used for an outbound connection.
      - It is strongly recommended **NOT** to use the **Enable table expiration** option since Data Locker would be unable to write reports to the dataset after the tables expire.
   4. Click the ![BQ_create_dataset_button.png](https://files.readme.io/242c16aaa7e7f1f96b3392452260fa1c1987a8ebfd276c36630a028baa245b16-13879858133137.png) button.
4. Grant Data Locker permissions to the dataset:
   1. In the **left-side** panel, click the **View actions** button ![BQ_view_actions_button.png](https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png) to the right of the dataset you created.
   2. Select **Share.**
   3. In the **right-side** panel that opens, click the ![BQ_add_principal_button.png](https://files.readme.io/77179cb4b9c81faa7cdc13397920699186df15fd1722247ccd8cbecb0cc43bce-13879857984017.png) button.
   4. In the **Add principals** section, enter the following account in the **New principals** field:
      `datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com`
   5. In the **Assign roles** section, select **BigQuery > BigQuery Data Editor.**
      ![BQ_data_editor.png](https://files.readme.io/cc26288d02f10805c971167d42d77efc9c7702f7fe231724b66eddd9b1b0e252-13879852726929.png)
   6. Click **Save.**
   7. Click **CLOSE** to close the right-side panel.

</Tab>

<Tab title="Snowflake">

The procedure for preparing Snowflake for outbound connections is completed in combination with the [procedure for creating the outbound connection](/docs/data-clean-room-working-with-connections#snowflake-outbound) itself.

</Tab>

<Tab title="Amazon S3">

Follow the instructions for creating an [Amazon S3 bucket for inbound connections](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound) (with no changes to that procedure).

</Tab>

<Tab title="GCS">

Follow the instructions for creating a [GCS bucket for inbound connections](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound). In step #4 of that procedure, enter the following account in the **New members** box:

`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

</Tab>
</Tabs>

## Setting up the same cloud storage bucket for both inbound and outbound connections

As previously mentioned, it's common to use the same bucket on Amazon S3 or GCS for both inbound and outbound connections.

The instructions for this setup vary only slightly from the [instructions for inbound connections](/docs/data-clean-room-setting-up-cloud-services#setting-up-cloud-services-inbound). They do differ, however, depending on whether you are:

- creating a new bucket for use with DCR inbound and outbound connections; ***or***
- modifying a bucket previously used only for Data Locker to one now used for both inbound and outbound DCR connections

Instructions for both of these scenarios are included in the tabs below:

<Tabs>
<Tab title="Amazon S3">

### Creating a new bucket for inbound/outbound connections

Follow the instructions for creating an [Amazon S3 bucket for inbound connections](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound) (with no changes to that procedure).

### Modifying an existing bucket previously used only for Data Locker

Modifying an existing bucket that you used previously only for Data Locker requires changing bucket permissions (to allow access by both DCR and Data Locker).

**To modify bucket permissions:**

1. Log in to the AWS console.
2. Go to the S3 service.
3. Select the bucket used previously only for Data Locker.
4. Go to the **Permissions** tab.
5. In the **Bucket policy** section, click **Edit.** The **Edit bucket policy** window opens.
6. **Replace the contents** of the window with following code snippet:

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

   - In the snippet, replace *`af-dcr-mybucket`* (in the 2 lines in which it appears) with the name of the bucket you created.

> 🚧 Caution!
>
> When replacing the bucket name in the snippet, be sure not to overwrite `/*` in the second line in which the bucket name appears.

7. Click **Save changes.**

</Tab>

<Tab title="GCS">

### Creating a new bucket for inbound/outbound connections

Follow the instructions for creating a [GCS bucket for inbound connections](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound). Modify step #4 of that procedure to enter the following **2 accounts** in the **New members** box:

`appsflyer-dcr@dcr-report.iam.gserviceaccount.com`

`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

### Modifying an existing bucket previously used only for Data Locker

Modifying an existing bucket that you used previously only for Data Locker requires changing bucket permissions (to allow access by both DCR and Data Locker).

**To modify bucket permissions:**

1. Log in to your GCS console.
2. Go to the Cloud Storage Browser page.
3. Select the bucket used previously only for Data Locker.
4. Go to the **Permissions** tab.
5. In the Permissions section, click **+ Add.** The **Add members** window opens.
6. In the **New members** box, enter the following account:
   `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
7. From the **Role** list, select **Cloud storage** > **Storage Admin.**
   ![dcr_gcs_permissions.png](https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png)
8. Click **Save.**

</Tab>
</Tabs>
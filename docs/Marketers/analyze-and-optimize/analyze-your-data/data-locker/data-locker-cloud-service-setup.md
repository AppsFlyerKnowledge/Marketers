---
title: "Data Locker—cloud service setup"
excerpt: "Set up your cloud service to receive data from Data Locker: GCS, AWS, BigQuery, or Snowflake."
---
Data Locker enables you to stream data to your selected and owned storage solution, whether it is a bucket or a data warehouse. Set up your cloud service using one of the following procedures.

## Bucket cloud storage

<Tabs>
<Tab title="GCS storage">

Before you begin, note the following:

- The procedure in this section needs to be performed by your Google Cloud admin.
- You can delete files from Data Locker 25 or more hours after they were written. Don't delete them before.

**Information for the GCS admin**

Data Locker is the AppsFlyer solution for streaming data to storage.

**Requirements**

- Create a GCS bucket for the exclusive use of Data Locker. Exclusive means no other service writes data to the bucket.
- Suggested bucket name: `af-datalocker`.
- Grant Data Locker permissions using the procedure that follows.

**To grant Data Locker permissions:**

In this procedure, substitute `data-locker-example` with the name of the bucket you previously created for Data Locker.

1. Log in to your GCS console.
2. Go to **Storage** > **Storage browser**.

![mceclip0.png](https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png)

3. Select the bucket you previously created, for example, `data-locker-example`.
4. Go to the **Permissions** tab.
5. Click **+Add**.

The Add members window opens.
6. Complete as follows:
1. **New members**, paste the snippet that follows.

      ```auto
      Autoaf-data-delivery@af-raw-data.iam.gserviceaccount.com
      ```

2. **Select a role**: **Cloud storage** > **Storage Object Admin**.

      ![mceclip0.png](https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png)
7. Click **Save**.

</Tab>

<Tab title="AWS storage">

Before you begin, note the following:

- The procedure in this section needs to be performed by your AWS admin.
- You can delete files from Data Locker 25 or more hours after they were written. Don't delete them before.

**Information for the AWS Admin**

Data Locker is the AppsFlyer solution for streaming data to storage.

**Requirements**

- Create an AWS bucket named af-datalocker-mybucket. The prefix af-datalocker- is mandatory. The suffix is free text.
- We suggest af-datalocker-yyyy-mm-dd-hh-mm-free-text. Where yyyy-mm-dd-hh-mm is the current date and time, and you add any other text you want as depicted in the figure that follows.

**User interface in AWS console**

![MyBucket.jpg](https://files.readme.io/b8a16d185279200026388e146cfb3eb03ae3c7737ac26da3aa0d116a0cf9c078-4403551836305.jpg)

After creating the bucket, grant AppsFlyer permissions using the procedure that follows.

**To create a bucket and grant AppsFlyer permissions:**

1. Log in to the AWS console.
2. Go to the S3 service.
3. **To create the bucket**:   1. Click **Create bucket**.
2. Complete the **Bucket name** as follows: Start with `af-datalocker-` and then add any other text as described previously.
3. Specify one of the [supported AWS](/docs/data-locker-cloud-service-setup#h_01J2DSZ4NVVMTTNSXP2Z9DAS0Q) regions.
4. Click **Create bucket.**
4. **To grant AppsFlyer permissions:**   1. Select the bucket.
2. Go to the **Permissions** tab.
3. In the **Bucket policy** section, click **Edit**.

      The Bucket policy window opens.
4. Paste the following snippet into the window.

      ```auto
      Auto{
        "Version": "2012-10-17",
        "Statement": [\
          {\
            "Sid": "AF_DataLocker_Direct",\
            "Effect": "Allow",\
            "Principal": {\
              "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"\
            },\
            "Action": [\
              "s3:GetObject",\
              "s3:ListBucket",\
              "s3:DeleteObject",\
              "s3:PutObject"\
            ],\
            "Resource": [\
              "arn:aws:s3:::af-datalocker-my-bucket",\
              "arn:aws:s3:::af-datalocker-my-bucket/*"\
            ]\
          }\
        ]
      }
      ```
5. In the snippet, replace `af-datalocker-my-bucket` with the bucket name you created.
6. [Optional] Add support for KMS-encrypted buckets. To do so, in the **Key Policy** section, choose **Switch to policy view** and paste the following snippet in the **Statement array.**

```auto
Auto{
         "Sid": "Allow use of the key",
         "Effect": "Allow",
         "Principal": {
             "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
         },
         "Action": "kms:GenerateDataKey*",
         "Resource": "*"
     }
```

7. Click **Save changes**.
8. Complete the [Setup Data Locker procedure.](/docs/data-locker-for-marketers#set-data-locker-report-settings)

#### **Supported AWS regions**

Data Locker supports the following AWS regions:

- Asia Pacific (Tokyo): `ap-northeast-1`
- Asia Pacific (Seoul): `ap-northeast-2`
- Asia Pacific (Mumbai): `ap-south-1`
- Asia Pacific (Singapore): `ap-southeast-1`
- Asia Pacific (Sydney): `ap-southeast-2`
- Canada (Central): `ca-central-1`
- EU (Frankfurt): `eu-central-1`
- EU (Ireland): `eu-west-1`
- EU (London): `eu-west-2`
- South America (São Paulo): `sa-east-1`
- US East (N. Virginia): `us-east-1`
- US East (Ohio): `us-east-2`
- US West (N. California): `us-west-1`
- US West (Oregon): `us-west-2`

</Tab>

<Tab title="Azure storage">

Before you begin, note the following:

- The procedure in this section needs to be performed by your Azure Cloud admin.
- You can delete files from Data Locker 25 or more hours after they were written. Don't delete them before.

**Information for the Azure admin**

Data Locker is the AppsFlyer solution for streaming data to your storage account.

**To define a storage account for Data Locker:**

01. In your Azure portal, go to [Azure storage accounts.](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts) and click ![predict_dashboard_plus_symbol.png](https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png)**Create** to create a storage account to retrieve your AppsFlyer data.
02. In the **Basic** tab **> Project details,** select from the dropdowns:
    1. A **Subscription.**
    2. A **Resource Group.**

       Optional: If no resource group exists, click **Create new** to create a resource group.
03. Under **Instance details:**
    1. Enter a **Storage account name.**
    2. Select a **Region** from the dropdown.
04. Click **Next: Advanced >**
05. Under the  **Security** tab, select **Enable Hierarchical namespace.**
06. Click **Review > Create.**
07. After deployment finishes, return to your [Azure storage accounts](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts) and select the newly created account.
08. Go to **Access keys** and copy your **Storage account name** and one of your **keys**.
09. Go to **Storage browser > Blob containers** and click ![predict_dashboard_plus_symbol.png](https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png)**Add container.**
    1. Enter a **Name** for the new container.
    2. Click **Create.**
10. Once enabled, in AppsFlyer, go to [**Data Locker**](https://hq1.appsflyer.com/datalocker/overview) **> ![predict_dashboard_plus_symbol.png](https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png) New connection.**
11. In the new connection:
    1. Name your connection.
    2. Choose **Azure Blob**.
    3. Enter your Azure **Container name** in the **Bucket Name** field (the one you made in step 9).
    4. Enter your copied **Storage account name** from step 8.
    5. Enter your copied **Key** from step 8.
    6. Click **Test connection**.
    7. **Save.**

</Tab>

<Tab title="Yandex Cloud storage">

Before you begin, note the following:

- The procedure in this section needs to be performed by your Yandex Cloud admin.
- You can delete files from Data Locker 25 or more hours after they were written. Don't delete them before.

**Information for the Yandex admin**

Data Locker is the AppsFlyer solution for streaming data to storage.

**To create a bucket and grant Data Locker permissions:**

1. In your [Yandex Cloud console](https://console.cloud.yandex.com/), go to the **Service Accounts** tab and click **Create service account**.
2. Name the service account, for example, `af-datalocker`.
3. Create a static access key for the service account. In the service account:
1. Click **Create a new key**.
2. Select **Create static access key**.
3. Save the **Key ID** and **Secret Key**.
4. Give your new service account **storage.editor** permissions.
1. In your bucket settings, go to **Access Bindings** and click **Assign bindings**.
2. For your new service account, add the **storage.editor** role and click **Save**.
5. Contact your AppsFlyer CSM to enable Yandex in Data Locker.
6. Once enabled, use the key ID and secret key during [Data Locker setup](/docs/data-locker-for-marketers#set-up-data-locker).

</Tab>
</Tabs>

## Data warehouse cloud storage

### BigQuery

The procedure in this section needs to be performed by your BigQuery admin.

**Information for the BigQuery Admin**

Data Locker is the AppsFlyer solution for streaming data to storage.

**Requirements**

- Create a BigQuery dataset

**To create a BigQuery dataset:**

1. In BigQuery, create a project or use an existing project.
2. In the project, click **CREATE DATASET**. ![GCSCreateDataSEt_1_.png](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)
3. Give the dataset a suitable ID.

> 📘 Note
>
> Make sure that the target project or dataset is linked to an active billing account. Without a billing account, Data Locker cannot create or write to tables in the BigQuery destination, and the connection setup process may fail.

4. Grant AppsFlyer access to the dataset. [See Big Query instructions](https://cloud.google.com/bigquery/docs/control-access-to-resources-iam#grant_access_to_a_resource)
   - For **Add principal**, use the following AppsFlyer user: [datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com](mailto:datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com)
   - For **Assign roles**, select BigQuery Data Editor.
5. Complete the remaining settings as required.

### Snowflake

Connect Data Locker to your Snowflake account. By doing so, data is sent to Snowflake and continues to be available in your selected cloud storage.

**Considerations for BI developers**

- The data freshness rate is the same as that of the data provided in a bucket.
- The table and column structure of the data is equivalent to that of data available directly from a Data Locker bucket.
- As rows are added to the Snowflake share, the `_ingestion_time` column is populated in the system’s local timezone (not UTC). To ensure row uniqueness and to prevent ingestion of the same row more than once:
1. Save the `max_ingestion_time` per table ingested.
2. Each time you run your ingestion process, ingest only those rows where `_ingestion_time > max_ingestion_time`

Complete the following procedures to connect Snowflake to Data Locker.

#### **Snowflake connector procedures**

**To get your Snowflake account ID and region**:

1. In Snowflake, [log in to your Snowflake account](https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface).
2. In the menu bar, select your name.

Your account ID and region display.

![Snowflake account details](https://files.readme.io/6f508a5c2c6cd5dd84dd2639c73e62ff819e0a06ea3323d7a999a6b4fc717009-40394499797393.png)

**To connect Data Locker to Snowflake**:

1. In AppsFlyer, go to **Reports** > **Data Locker**.
2. Select Snowflake.
3. Enter the Snowflake region and account locator using the information you previously received from Snowflake.
4. Click **Save**.

**To** **create a database from a share in Snowflake**:

1. In Snowflake, [log in to your Snowflake account](https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface).
2. Switch role to **Accountadmin**. See [Create a database from a share.](https://docs.snowflake.com/en/user-guide/data-share-consumers.html#creating-a-database-from-a-share)
3. Select **Shares**.
4. Select the AppsFlyer share, for example, APPSFLYER_ACC_XXX_DATA_LOCKER.
5. Click **Create Database from Secure Share and complete the required details**. 

> 📘 Note
>
> You must load the data from the shared database into your tables, because data in the shared database is only available for a limited period (currently 14 days).

6. In your database, the imported tables are displayed. Table names and structures are equivalent to those in Data Locker buckets.

## Traits and limitations

| Trait | Description |
| --- | --- |
| AppsFlyer cloud connection | Reports cannot be stored uncompressed |
| BigQuery dataset location change | If you change the dataset location in BigQuery, you need to re-save your connection in AppsFlyer. Since no configuration changes are required in the AppsFlyer connection settings, the **Save** button is disabled. To enable the button, make a temporary change, save the connection, then revert the change and save the connection again. |
| Supported Snowflake regions | **AWS-supported regions:**<br />- us-east-1<br />- us-east-2<br />- us-west-2<br />- eu-west-1<br />- eu-west-2<br />- eu-west-3<br />- eu-central-1<br />- eu-north-1<br />- ca-central-1<br />- sa-east-1<br />- ap-south-1<br />- ap-southeast-1<br />- ap-southeast-2<br />- ap-northeast-1<br />- ap-northeast-2<br />- ap-northeast-3<br />**Azure-supported regions:**<br />- australia-east<br />- east-us-2<br />- central-us<br />- southcentral-us<br />- west-europe<br />- west-us-2<br />**GCP-supported regions:**<br />- Limited support. Contact AppsFlyer support to verify availability for your region. |
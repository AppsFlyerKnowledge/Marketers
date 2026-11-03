---
title: Data Clean Room—Working with connections
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2023-03-20T13:18:17Z'
  edited_at: '2024-09-04T08:35:26Z'
  id: 13886278812817
  locale: en-us
  section: Data Clean Room
  section_id: 4591191779217
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/13886278812817-Data-Clean-Room-Working-with-connections
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Connect your cloud services to the Data Clean Room in order to upload data and receive reports.

## Overview

Once you have set up your cloud services for use with the Data Clean Room (DCR), the next step is to connect them to the DCR.

* The connections from which the DCR reads first-party data from your systems are called **inbound connections.** You use these connections when setting up your custom data sources.
* The connections through which the DCR delivers reports after processing are called **outbound connections.** You use these connections when setting up your reports.

## Creating inbound connections

You can choose to create inbound connections either:

* Before using them to create sources; ***or***
* As part of the source creation process.

Either way, the process is the same, and you can use the created connections in exactly the same way. The only difference is the timing and the way you initiate the process.

**To create a new inbound connection outside the source creation process:**

1. From the top of the main DCR page in AppsFlyer, click the **Manage connections** button:

   [![dcr_manage_connections_button.png](https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png)](https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png)

   * If you have existing inbound connections in your account, you'll see the **Manage connections** dialog. From there, click the ![dcr_new_connection_button.png](https://files.readme.io/ea74c7dd6653a544216addddc5fda2a15126a6a26ba2e3ea0a954c58f4fe479e-13916096900753.png) button to open the **New connection** dialog.
   * If you are creating your account's first inbound connection, the **New connection** dialog will open automatically.
2. Continue with the instructions in the [Complete the connection](#complete-the-connection) section, below.

**To create a new inbound connection as part of the source creation process:**

1. Create the connection while you are <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-sources#2-specify-the-source-location">specifying the source location</Anchor>.
   * If there are no connections defined in your account, the **New connection** dialog will open, prompting you to create one.
   * If you have existing connections but want to use a new one, click the ![dcr_new_connection_button.png](https://files.readme.io/ea74c7dd6653a544216addddc5fda2a15126a6a26ba2e3ea0a954c58f4fe479e-13916096900753.png) button to open the **New connection** dialog.
2. Continue with the instructions in the [Complete the connection](#complete-the-connection) section below.

#### Complete the connection

From the **New connection** dialog, select the cloud service you are connecting to the DCR, then continue with the instructions from the relevant tab below.

<Image alt="dcr_create_inbound_connection.png" src="https://files.readme.io/b30606026761528f4a0d3efcc1a3207e8b9c99ca8202f76b2d698a86efaa21ee-13913809617297.png" width="457px" />

<div id="bigquery-inbound" />

<Accordion title="BigQuery">

In the **New connection** dialog, enter the BigQuery **project ID** for the project that contains your custom data source.

* You can get this information from the Big Query page of your Google Cloud Console.

  <Image alt="BQ_project_ID.png" src="https://files.readme.io/de295dfc0224ff90f041b1aeaf2996828ec1920a715ba668b46a2f50489fd15b-13910856739857.png" width="457px" />

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

In the **New connection** dialog, enter the **Snowflake account ID** and **region** for the account that contains your custom data source. You can get this information by clicking on the account name at the bottom-left menu of your Snowflake console:

* **ACCOUNTADMIN** > **Account** > hover over the relevant account > **Copy account identifier**. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/admin-account-identifier#finding-the-organization-and-account-name-for-an-account">See here Snowflake documentation</Anchor>.

![ui-snowsight-account-identifier.png](https://files.readme.io/9995c3fd523548de93bafc7c575203e7d38be3b6be2a5e876d7a0a8495ca04c9-24698313004433.png)

</Accordion>

<div id="s3-gcs-inbound" />

<Accordion title="Amazon S3 and GCS">

In the **New connection** dialog, enter the name of the <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services#cloud-storage-buckets--amazon-s3-and-gcs">bucket you created</Anchor> for the exclusive use of the DCR.

</Accordion>

## Creating outbound connections

The DCR delivers reports to your selected cloud services using <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>. Because reports are delivered via Data Locker, outbound DCR connections are actually Data Locker connections. You can choose to create these connections either:

* Before using them to create reports (starting from the Data Locker page in AppsFlyer); ***or***
* As part of the report creation process (starting from the DCR page in AppsFlyer).

Either way, the process is largely the same, and you can use the created connections in exactly the same way.

> 📘 **Note**
>
> Receiving DCR reports does not require a premium subscription to Data Locker. If you are interested in receiving other AppsFlyer reports via Data Locker, contact your CSM or send an email to [hello@appsflyer.com](mailto:hello@appsflyer.com).

**To create a new outbound connection outside the report creation process:**

1. From the AppsFlyer left-side navigation menu, select **Report > Data Locker.**  
   * If you have existing Data Locker connections in your account, you'll be taken to the main Data Locker page. From there, click the ![dcr_dl_new_connection_button.png](https://files.readme.io/8261a480674822371c6e585f995a496a6b5682dd935351375db200bbb1272689-13919327056657.png) button in the upper-right corner to open the **New connection** dialog.
   * If you are creating your account's first Data Locker connection, you'll see Data Locker's **Get started** page. Click the ![dcr_dl_get_started_button.png](https://files.readme.io/3176ed5c35cba0939dd36de8c1136d15dc8ce27ee2891894ef65dba92fc7e91a-13919329616657.png) button to open the **New connection** dialog.
2. Continue with the instructions in the [Complete the connection](#complete-the-connection-1) section below.

**To create a new outbound connection as part of the report creation process:**

1. Create the connection while you are <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-creating-attribution-data-reports#set-the-report-destination-and-save-the-report">setting the report destination</Anchor>.
   * If there are no connections defined in your account:
     * A new tab will open in your browser (showing the AppsFlyer Data Locker page)
     * A **New connection** dialog will open.
   * If you have existing connections but want to use a new one, click the ![dcr_new_connection_data_locker_button.png](https://files.readme.io/16bf3f34eb9f055bd1935a19620279c83947f6fd6a238b7199366c0497a43ed0-21414410403345.png) button:
     * A new tab will open in your browser (showing the AppsFlyer Data Locker page)
     * A **New connection** dialog will open.
2. Continue with the instructions in the [Complete the connection](#complete-the-connection-1) section, below.
3. After creating the connection, return to the DCR tab in your browser and select the newly created connection from the list of Data Locker connections.

#### Complete the connection

> 🚧 **Important!**
>
> The **AppsFlyer AWS Bucket** option should not be used for DCR reports.

From the **New connection** dialog, select the cloud service you are connecting to, then continue with the instructions from the relevant tab below.

[![dcr_dl_new_connection_dialog.png](https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png)](https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png)

<div id="bigquery-outbound" />

<Accordion title="BigQuery">

1. In the **New connection** dialog, enter a name for the connection; then select the **BigQuery** option.
2. Enter the **Project ID** and **Dataset name** for the BigQuery project that contains the <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services#bigquery-outbound">dataset you created</Anchor> for Data Locker.  
   * You can get this information from the Big Query page of your Google Cloud Console.

     <Image alt="BQ_project_ID_dataset_name.png" src="https://files.readme.io/c784b0369c51a6e123279fdc5b2fa1fba255ae371d436e9247cb5e4685387983-13928683779089.png" width="457px" />
3. Click the ![dcr_dl_test_connection_button.png](https://files.readme.io/8c789303491a4524515216aca06dc4b3435b5b0baa3aaa8726ff73cce968c5bc-13928683412241.png) button to ensure that Data Locker is connected to the dataset.
4. Click **Save** to create the connection.

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

The procedure for connecting Snowflake to Data Locker is a 2-step process:

* **[Step #1](/docs/data-clean-room-working-with-connections#step-1) –** In AppsFlyer, create the initial connection.
  * This gives your Snowflake account the ability to access an AppsFlyer Snowflake share.
* **[Step #2](/docs/data-clean-room-working-with-connections#step-2) –** In your Snowflake account, create a database from the share.
  * This creates a database in your account that references the tables in the AppsFlyer share.

**Note:** The following procedure must be performed by a Snowflake **Accountadmin.**

<span id="step-1"></span>**Step #1 (create the initial connection) –**

1. In the **New connection** dialog, enter a name for the connection; then select the **Snowflake** option.
2. Enter your Snowflake account region and account ID.
   * You can get this information by clicking on the account name at the bottom-left corner of your Snowflake console, then hovering over the account name in the popup. **Important!** Look for the ID labeled **Locator.** This is **NOT** the same ID as the one used to create inbound Snowflake connections.  

     <Image alt="snowflake_account_locator.png" src="https://files.readme.io/23495b3209129f48ed1ca3442a1e96fac791d46df6f87050ac036893a050e427-13930022354961.png" width="536px" />
3. Click the ![dcr_dl_test_connection_button.png](https://files.readme.io/8c789303491a4524515216aca06dc4b3435b5b0baa3aaa8726ff73cce968c5bc-13928683412241.png) button to ensure that Data Locker is connected to your Snowflake account.
4. Click **Save** to create the connection.

<span id="step-2"></span>**Step #2 (create a database from share)** –

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Log in to your Snowflake account</Anchor>.
2. Switch your role to **Accountadmin.**
3. From the left-side panel, select **Private Sharing.**
4. In the page that opens, select the **Shared With You** tab.
5. From the share whose name begins with **APPSFLYER**, click the **Get data** ![snowflake_get_data_button.png](https://files.readme.io/fbda3603d504f08980bd5329aad49e5e0c562e1de556ffb0e04ad4a1abbac89c-13930725492497.png) button.
6. [Optional] In the **Get Data** dialog, change the default database name according to your needs and select the roles in addition to Accountadmin that can access the database.
7. Click **Get Data** to create the database.

</Accordion>

<div id="s3-gcs-outbound" />

<Accordion title="Amazon S3 and GCS">

1. In the Data Locker **New connection** dialog, enter a name for the connection; then select either the **Amazon S3** or **GCS** option.
2. Enter the name of the <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services#cloud-storage-buckets--amazon-s3-and-gcs">bucket you created</Anchor> for the exclusive use of DCR.

</Accordion>

<div data-zendesk-anchors="h_01HKA1AS2QGDTPW85WA07K35M0=overview h_01HKA1AS2QRRBJAYNKSWWZXE3N=creating-inbound-connections complete-the-connection-inbound=complete-the-connection h_01HKA1AS2Q06F07RDD8W384RE2=complete-the-connection h_01HKA1AS2QXP5H2HBJ911F3TPZ=bigquery-inbound h_01HKA1AS2QCPC6515FZ45E8Q67=snowflake-inbound h_01HKA1AS2QQZWFMRQD0T0FNQM5=s3-gcs-inbound h_01HKA1AS2QAV9DJWZQ2703TS0Z=creating-outbound-connections h_01HKA1AS2Q76NP9FY7S4H0QP4D=note complete-the-connection-outbound=complete-the-connection-1 h_01HKA1AS2RKTWNY2ZR7VYAJC90=complete-the-connection-1 h_01HKA1AS2R7RFWKM2W89QSEH3V=important h_01HKA1AS2RJXZPCBKE7ST0SA63=bigquery-outbound h_01HKA1AS2R7TV495V39N35CWAR=snowflake-outbound h_01HKA1AS2RBTK8NZF09BYWDX2G=s3-gcs-outbound" />

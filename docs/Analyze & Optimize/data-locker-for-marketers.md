---
title: "Data Locker for marketers"
excerpt: "Data Locker sends your report data to cloud storage for loading into your BI systems, supporting destinations like AWS, GCS, Azure, BigQuery, and Snowflake."
---
Data Locker sends your report data to cloud storage for loading into your BI systems. You can select between different storage destinations: An AppsFlyer-owned bucket in AWS, or storage owned by you in AWS, GCS, Yandex, BigQuery, and Snowflake. Data Locker supports [multiple destinations](https://support.appsflyer.com/hc/articles/360000877538#multipleconnections-principles-more-than-one-destination). That means you can send all data to multiple destinations, segregate data by destination, or a combination of both.

## Overview

<Image src="https://files.readme.io/820fee89515ccdcdfac2043bcb9fde722ddc8ec852a140ec250378c581d9c375-32966274469649.png" alt="Data Locker for Advertisers" />

In Data Locker select your apps, media sources, events, and reports to include in the data AppsFlyer delivers to your selected cloud storage options. Then, load data programmatically from the storage into your systems.

### Data Locker—features

| Feature | Description |
| --- | --- |
| [Storage options (cloud)](https://support.appsflyer.com/hc/articles/360000877538#storage-options) | Data Locker can send your data to any of the following cloud service providers:<br>- Storage owned by AppsFlyer on AWS<br>- [Storage owned by you](https://support.appsflyer.com/hc/articles/360017603577)on:  - AWS<br>  - GCS<br>  - Azure Blob<br>  - [Beta] Yandex<br>  - BigQuery<br>  - Snowflake<br>You can set more than 1 destination in Data Locker. This means that you can send all or some of your data to [multiple destinations](https://support.appsflyer.com/hc/articles/360000877538#multipleconnections-principles-more-than-one-destination).<br>**Examples**<br>- Segregate data by report type. Send raw data to GCS and aggregate data to Snowflake.<br>- Segregate data by app and send the data per app group to different buckets. |
| Multi-app | Send data of 1, more, or all apps in your account. When you add apps to the account, they can be automatically included. |
| Availability window | 14 days |
| [Data segregation](https://support.appsflyer.com/hc/articles/360000877538#app-segregation) | Available data segregation options (relevant for bucket cloud storage):<br>- [Default] **Unified:** Data of all apps combined. The row-level app ID field is used to identify the app in data files.<br>- **Segregated by app:** Data of each app is in a separate folder. The folder name consists of the app ID. |
| Data format options | - For bucket cloud storage:<br>  - CSV<br>  - Parquet<br>  - [Adobe](https://support.appsflyer.com/hc/articles/13856826626321)<br>- Data warehouse |
| Data freshness | Freshness depends on the report type <br>- **Hourly:** Data generated continuously; for example, installs and in-app event data are written within hours of the event arriving in AppsFlyer.<br>- **Daily:** Reports like uninstalls, are generated daily and are ready on the following day.<br>- **Versioned:** If the same report is generated multiple times for the same time period a versioning mechanism is in place. |

### Reports available via Data Locker

[Reports available via Data Locker](https://support.appsflyer.com/hc/articles/4410643856657)

## Set Data Locker report settings

To configure Data Locker, follow these steps to connect your cloud service, define export settings, and customize report content:

### 1\. Set up your cloud service

You can connect your Data Locker to one or more cloud service providers. See the following for instructions on how to configure them to work with Data Locker:

- [AWS](https://support.appsflyer.com/hc/articles/360017603577#aws-storage) bucket
- [GCS](https://support.appsflyer.com/hc/articles/360017603577#gcs-storage) bucket
- [Azure](https://support.appsflyer.com/hc/articles/360017603577#%5Bbeta%5D-azure-storage) Blob
- [Beta] [Yandex](https://support.appsflyer.com/hc/articles/360017603577#yandex) bucket
- [BigQuery](https://support.appsflyer.com/hc/articles/360017603577#bigquery) data warehouse
- [Snowflake](https://support.appsflyer.com/hc/articles/360017603577#snowflake) data warehouse

> 📘 Note
>
> If you don't have a Data Locker subscription and you access Cohorts analytics or SKAN data, you must still complete a marketer-owned cloud storage service procedure.

### 2\. Add a connection to your cloud service

After configuring your cloud service account to work with Data Locker (see "Set up your cloud service" above), create a connection in Data Locker using the credentials from your account. You can create up to two connections.

> 📘 Note
>
> By default, each account can open up to **2 Data Locker connections**. If you need additional connections, contact your Customer Success Manager (CSM).

To create a connection for your cloud provider perform the following steps:

1. In AppsFlyer, from the sidebar, go to **Exports** > **Data Locker**.
2. On the right-hand side, click **New connection.**
3. In **Connection name** enter the name for your connection. Use only lowercase letters, digits, and hyphens.
4. Click the icon of the cloud service to which you want to connect.
5. Depending on the service you selected, enter the following connection information.

<Tabs>
<Tab title="AWS">

Before setting the AWS connection, create an AWS bucket. To learn, how see [here](https://support.appsflyer.com/hc/articles/360017603577#aws-storage).

To set the connection:

1. Enter your AWS S3 bucket name. `af-` prefix is mandatory, and should be entered manually.
2. Click **Test connection**.
3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
4. Select whether to **Make this connection compatible with Adobe Experience Platform**. If selected, click **Save** and continue to [select global-level filters](/docs/data-locker-for-marketers#select-global-level-filters).
5. Click **Save**.

</Tab>

<Tab title="GCS">

Before setting the GCS connection, create a bucket on GCS. To learn how see [here](/docs/data-locker-cloud-service-setup#gcs-storage).

To set the connection:

1. Enter your **GCS bucket name**.
2. Click **Test connection**.
3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
4. Select whether to **Make this connection compatible with Adobe Experience Platform**. If selected, click **Save** and continue to [select global-level filters](/docs/data-locker-for-marketers#select-global-level-filters).
5. Click **Save**.

</Tab>

<Tab title="Azure">

Before setting the Azure connection, open a storage account in Azure. To learn how, see [here](/docs/data-locker-cloud-service-setup#[beta]-azure-storage).

To set the connection:

1. Enter your **Connection name**, **Storage account name**, and **Key**.
2. Verify that an error message indicating that the bucket path is invalid isn't displayed.
3. Select whether to **Make this connection compatible with Adobe Experience Platform**. If selected, click **Save** and continue to [select global-level filters](/docs/data-locker-for-marketers#select-global-level-filters).
4. Click **Save**.

</Tab>

<Tab title="Yandex">

Before setting the AWS connection, create a service account in Yandex. To learn how, see [here](/docs/data-locker-cloud-service-setup#yandex).

To set the connection:

1. Enter your **Bucket name**, **Access key**, and **Secret key**.
2. Verify that an error message indicating that the bucket path is invalid isn't displayed.
3. Select whether to **Make this connection compatible with Adobe Experience Platform**. If selected, click **Save** and continue to [select global-level filters](/docs/data-locker-for-marketers#select-global-level-filters).
4. Click **Save**.

</Tab>

<Tab title="BigQuery">

Before setting the BigQuery connection, create a dataset in BigQuery. To learn how, see [here](/docs/data-locker-cloud-service-setup#bigquery).

To set the connection:

1. Enter your BigQuery project ID and dataset name.
2. Click **Test connection**.
3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
4. Click **Save** and continue to [select global-level filters](/docs/data-locker-for-marketers#select-global-level-filters).

</Tab>

<Tab title="Snowflake">

Before setting the Snowflake connection, open an account in Snowflake. To learn how, see [here](/docs/data-locker-cloud-service-setup#snowflake).

To set the connection:

1. Enter your Snowflake region and account ID.
2. Click **Test connection**.
3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
4. Click **Save** and continue to [select global-level filters](/docs/data-locker-for-marketers#select-global-level-filters).

</Tab>
</Tabs>

6. Click **Save.** The **Report output settings section** is displayed.

> 📘 Note
>
> You can [use the audit log](/docs/data-locker-for-marketers#track-connection-changes-in-the-audit-log) to confirm whether a connection was created, updated, or deleted, and who made the change.

### 3\. Set the report output settings

After setting the connection with the cloud service, you can continue to set the general settings of your Data Locker reporting outputs. **If your cloud service is BigQuery or Snowflake, you can skip this step**.

1. Under the **Report output settings** section, select the folder structure ( [data segregation](https://support.appsflyer.com/hc/articles/360000877538#app-segregation)):
   - **Unified (** default **):** The report files include records from all the apps.
   - **Segregated by app:** Each report file is dedicated to one app.
2. Select the reports file format: Parquet (default) or CSV.
3. Select the report's file compression type:
   - Snappy (only available for Parquet files)
   - GZIP
4. Select the maximum row number you want in your file: Either 10k, 25k, 50k, 100k, 200k, or 500k. More rows in the file mean fewer files but a larger file size.

> 📘 Note
>
> Under **Expected path**, view the path patterns for your reports. Note: The real path may be different than what is displayed.

### 4\. Select global-level filters

The global-level filters allow you to **filter your reports by apps, geo, or media sources**. These filters apply to most of the reports in your Data Locker account, but you can also set them at the report level (see [7-select-the-reportlevel-filters](/docs/data-locker-for-marketers#select-the-report-level-filters) below). If the same filter is applied on both levels, the report-level filter takes precedence.

To apply a filter, perform the following:

1. In the **Reports** section, click the filter and select the items to include in the report. For example, click <Image src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" alt="Apps filter" /> the **Apps** filter and select the apps to include in the reports.
2. Then click the Enter (\&\#x23CE;) button.

### 5\. Select the report group

Select the reports that you want to get in your cloud service. The reports are listed in groups. Clicking on the report group name expands or collapses the groups.

- To select a report, click <Image src="https://files.readme.io/3f59bcc54434374270c0099394a740cc650a3b4a1be0f3f34d298be1ebcad40c-34623601355409.png" alt="Expand" /> to expand the report group. For each report in the group, the following information is presented:
  - **Report Name:** The title of the report.
  - **Dataset Name:** The name of the dataset that contains the report's records.
  - **Data Freshness:** How often the report is updated with new records (e.g., hourly, daily, or versioned).
  - **Fields:** the number of fields (or columns) that you selected for the report compared to the total number of fields available for selection.

### 6\. Customize or duplicate the report

After selecting one or more reports from a report group, you can choose to either **customize the original report** or **create a separate customized copy** by duplicating it. This allows you to tailor the report’s fields and filters to your specific needs without affecting the original version.

**Option A: Customize the original report**

1. Click the <Image src="https://files.readme.io/35f4653b944cd5dc81c6de76f8dcacd9c3413ea49915ba2b5865a244ede3c4b6-35437232722833.png" alt="Customize" />**Customize** button next to the report name.
2. The report editor will open, allowing you to select fields and apply filters.
3. Changes will be saved to the original report configuration.

*Note: This modifies how the report is delivered to your cloud storage.*

**Option B: Duplicate the report**

- Click <Image src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" alt="Options" /> next to the report name.
- Select <Image src="https://files.readme.io/d8fbf09b3a8e3839f80a0a4fec90e0360dc1c2a4a066bf58438364c0d8a15c65-35439088509073.png" alt="Duplicate" />**Duplicate** from the dropdown menu.
- A copy of the report will be created, named with the prefix `copy_of_`.
- The duplicated report opens in edit mode for further customization.

*Tip: Duplicating is ideal for creating variations of a report for different use cases.*

After choosing whether to customize or duplicate, proceed to configure the report fields as described in the next step.

### 7\. Select the report fields

Once you’ve chosen to customize or duplicate a report, the next step is to define which data fields should be included. Each report provides a complete set of available fields, and you can customize your selection to include only what’s relevant for your analysis or integration. By default, all fields are selected, but you can refine the report by manually choosing specific ones.

To select the fields to include in the report:

1. In the selected report dialog, under the **Fields** tab, hover over any field to view its description.

<Image src="https://files.readme.io/293d227464e3907982e0c82187915ee1b16386a4111e83ebd8db065ade64a48b-34623601367697.png" alt="Fields selection" />

2. Check the fields you want to include in the report, or uncheck the fields you wish to exclude from the report.
3. Click **Apply** to save your settings.

**Copy field selection from another report**

You can copy the field selection from another report as a starting point and then continue to select or deselect fields to fine-tune the report.

1. In the **Fields** tab, deselect any random field.
2. Click **Pull schema from report**.
3. Select the report you want to copy the field selection from.
4. Continue to select or deselect fields.
5. To restore the report's original field selection, click <Image src="https://files.readme.io/dda26e3d18c52049cf92d7862a87ce7a46e6a00c349afd70dfe6d1809e00b89e-34623601369361.png" alt="Refresh" />**Refresh**.

### 8\. Select the report-level filters

The report-level filters enable you to **filter a single report by apps, media sources, or other dimensions**. You can also set filters that apply to all the reports in your account; see [select global-level filters](/docs/data-locker-for-marketers#select-global-level-filters). By default, the report-level filters are set to the global-level filter settings, but you can update them to custom settings that apply only to the selected report.

To select the filters to apply to a specified report:

1. Hover on the specific report that you want to customize.
2. Click <Image src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" alt="Options" />  to open the actions menu, and select <Image src="https://files.readme.io/c27f864253e6749f883047b4529ad292153500db5aebd452568a6aa04407472e-34623601366033.png" alt="Edit report" />**Edit report**.
3. Open the **Filters** tab. The filters are set to the global-level filter settings.
4. Click the filter and select the items to include in the report. For example, click <Image src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" alt="Apps filter" /> the **Apps** filter and select the apps to include in the reports.
5. Click the Enter (\&\#x23CE;) button. Your selection overrides the global-level settings.
6. (Optional) For the **Inapps** report, you can set the **In-app event** filter. Enter their names exactly to select them.
7. Click **Apply** to save your settings.

### 9\. Remove legacy fields

Legacy fields are those that were previously included in the report schema but are now excluded. We recommend removing these fields to ensure your report contains only relevant information. Before making any changes, make sure that your workflows and integrations do not depend on them.

**To remove specific legacy fields**

1. Open the **Legacy fields** tab.
2. Turn on: **Include legacy fields in the report**.
3. Deselect the fields you want to exclude.
4. Click **Apply**.
5. Save the connection settings.

**To remove all legacy fields:**

1. Open the legacy fields tab.
2. Turn off: **Include legacy fields in the report**.

> 📘 Note
>
> If you want to include legacy fields in the report but can't because the legacy fields list is grayed out and locked, contact your Customer Success Manager.

#### Non-empty legacy fields

Most legacy fields are empty or `null`. However, a few of them contain values but are still considered legacy because either:

- They appear in the report under a different name (renamed).
- They were excluded from the report schema (deprecated).

[Download the non-empty legacy fields list (CSV).](https://docs.google.com/spreadsheets/d/e/2PACX-1vRzJr2IgKTHKq_6IFX-PFFv6_89ixtlbGZ9RNH134TniGlWa_M-85D1L2E7LhzQrDjictnSnNNnN2mm/pub?output=csv)

### 10\. Save the connection

Click **Save,** and the first data dump will be written to your cloud service within 3 hours. Subsequent data update schedules are specific to each report.

> ❗️ Important!
>
> Any changes to Data Locker settings take up to 3 hours to take effect.

## Set user permissions

Both **admins** and **team members**, with the correct permissions, can access Data Locker.

- **Admins** can access the Data Locker page, create and manage all connections, add editors, and assign owners to existing connections.
- **Team members** can access the Data Locker page, edit existing connections that they own, or create new connections. They **cannot** manage ownership (set the owner and editors), even if they are the account owners.

### Manage Data Locker access and ownership (Admins)

#### Give Data Locker access

- To provide a team member permission to access Data Locker, assign them a role with Data Locker set to **Manage**.

#### Manage ownership and editors

To transfer ownership or add a team member as an editor on an existing connection:

1. Click the three-dot options menu <Image src="https://files.readme.io/9d3faf1888da216d8fba433a95952d8f749d2abc236c0888a1c8a9d68d35273e-32966274479633.png" alt="Options" /> within the connection.
2. Select **Manage ownership**.
3. Change the connection owner or add an editor.

#### Review filters after changing ownership

If you change the owner of a Data Locker connection to a user with data access restrictions (for example, limited by app, media source, agency, or country), existing [global-level](/docs/data-locker-for-marketers#select-global-level-filters) or [report-level filters](/docs/data-locker-for-marketers#7-select-the-reportlevel-filters) may be reset to match the new owner’s permissions.

After transferring ownership, review the filters and confirm the connection reflects the intended data scope.

For more information about data access restrictions, see [User management > Data access](/docs/user-management#data-access).

> 📘 Note
>
> In AF AWS connections, there is no **Manage ownership** option even for Admins, since only Admins can edit, delete, or create new AF AWS connections. This precaution is taken to prevent the exposure of the bucket credentials.

## Data storage architecture

### Overview

The structure of your data in storage depends on whether the data is sent to cloud storage or a data warehouse. The folder structure described here applies to storage (buckets). For data warehouse storage, consider that the reference to folders applies to views.

Data is written to your selected storage option. In the case of cloud storage, the storage is owned by AppsFlyer on AWS or owned by you on AWS, GCS, or Yandex. You can switch storage options at any time or send some or all of your data to multiple storage options.

Data in the cloud bucket storage is organized in a hierarchical folder structure, according to report type, date, and time. The following figure contains an example of this structure:

<Image src="https://files.readme.io/23dc197712aaf638706edf8323fdbc539f871ee34095b8f47a5a1824fe23f9f6-32966274471697.png" alt="Folder Overview" />

Data of a given report is contained in the hour (h) folders associated with that report:

- The number of hour folders depends on the report data freshness (hourly, daily or versioned).
- Data is provided in Snappy or GZIP compressed files, or uncompressed files, having Parquet or CSV format.
- Data files consist of columns (fields).
- The schema (field) structure of the [user journey reports](/docs/data-locker-advertiser-reports#user-journey) is identical to each other and depends on the fields selected by you. Other reports each have their own explicit fields, AKA schemaless reports. See [Data Locker marketer reports](/docs/data-locker-advertiser-reports#user-journey) for the reports available and links to the report specifications.

### Folder structure

| Folder | Description |
| --- | --- |
| Subscription ID | <Image src="https://files.readme.io/0cda5728e48dab772878cad13ed3b81168f152e1bf01604ac45b700af804dd16-32966264039185.png" alt="Data Locker Folders" /><br>- The top-level folder in the bucket depends on the storage owner and provider. In general, the top-level folder is your Subscription ID but in some cases, for example, if you use Cyberduck the ID is set in the bookmark and doesn't display in the folder structure.<br>- The _data-locker-hourly_ folder contains the report topics. Folders above this level depend on bucket ownership and cloud service provider.<br>**Examples of folder structure based on bucket owner and cloud provider**<br>- **AppsFlyer bucket**: `<af-ext-reports>/<unique_identifier>/<data-locker-hourly>`<br>- **Your AWS bucket**: _`<af-datalocker-your bucket prefix>/<generated-home-folder><subscription-id>_`<br>- **Your GCS bucket:** `<your bucket name>/<generated-home-folder>/<subscription-id>` |
| Topic (t) | Report type relates to the subject matter of the report. |
| Date (dt) | This is the related data date. In the case of raw data, it means the date the event occurred. In the case of aggregated data, the reporting date itself. |
| Time (h or version) | Date folders are divided into **hourly (h)** or **version** folders depending on the report type. <br>#### **Hourly folders**<br>The h folders relate to the time the data was received by AppsFlyer. For example, install events received between 14:00-15:00 UTC are written to the h=14 file. Note! There is a delay, of about 1-3 hours, between the time the data arrives in AppsFlyer until the h folder is written to Data Locker. For example, the h=14 folder is written 1 hour later at 15:00 UTC. <br>**Hourly folder characteristics**:<br>- There are 24 h folders numbered 0–23. For example, h=0, h=1, and so on.<br>- A late folder, h=late, contains events of the preceding day arriving after midnight. Meaning events arriving during 00:00–02:00 UTC of the following day. For example, if a user installs an app on Monday 08:00 UTC and the event arrives on Tuesday 01:00 UTC, the event is written to Monday's late folder.<br>- Data arriving after 02:00 UTC is written to the folder of the actual arrival date and time.<br>- Ensure that data in the h=late folder is consumed. It isn't contained in any other folder.<br>- \_temporary folder **:** In some cases, we generate a temporary folder within an h folder. Disregard temporary folders and subfolders. Example: /t=impressions/dt=2021-04-11/h=18/ **\_temporary**.<br>**Daily reports**<br>- Raw data reports having a daily data freshness are stored in the h=23 folder. The uninstall report is usually in the h=2 folder but can be in any folder.<br>- Cohort and Incrementality reports are stored directly in the dt folder.<br>- Versioned reports adhere to a different convention described in this section. <br>**Hourly report considerations for apps that don't use UTC time.**<br>To make sure that you get all the data for a given calendar day you must consume the folders according to the day defined by the app timezone as detailed: <br>- **Eastern hemisphere timezone**: To get all the data of a given calendar date you must consume folders according to UTC time and date. Example: Your app timezone is UTC+10 (Sydney, Australia). To get all the hourly data related to Tuesday (Sydney) you must consume the following folders: Monday h=14–23 and late, Tuesday h=0–13 and 14-15 Why must you consume Tuesday h=14-15? Some data can arrive late. So the h=14–15 folders can contain late-arriving events. You must filter event\_time to align with the app calendar day relative to UTC.<br>- **Western hemisphere timezone:** To get all the data of a given calendar date you must consume folders according to UTC time and date. Example: Your app timezone is UTC- 7 (Los Angeles). To get all the hourly data related to Tuesday (Los Angeles) you must consume the following folders: Tuesday h=7–23 and late, Wednesday h=0–6 and 7-8. Why must you consume Wednesday h=7-8? Some data can arrive late. So the h=7–8 folders can contain late-arriving events. You must filter event\_time to align with the app calendar day relative to UTC.<br>#### **Version folders**<br>Some reports have a versioned option. This means that the most updated data for a given day is provided multiple times. Because data can continue to update due to late-arriving data or more accurate data the same report has multiple versions where the most recent version is the most accurate. <br>The reports for a given day are contained in the versions folder of that day. Each version is contained in a separate folder whose name is set using an Epoch timestamp that uniquely identifies the report. <br>Your data import processes must consider that data can be written retroactively. For example, on January 14, data can be written to the Jan 1 folder. If the bucket is owned by you, consider using cloud service notification to trigger your import process ( [AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/NotificationHowTo.html) \| [GCS](https://cloud.google.com/storage/docs/pubsub-notifications)) |

### App segregation

For bucket cloud storage, data is provided in unified data files containing the data of all apps selected or segregated into folders by app. The segregation is within the h folder as described in the table that follows.

| Segregation type | Description |
| --- | --- |
| [Default] Unified | Data for all apps are provided in unified data files. When consuming the data, use the row-level app\_id field to distinguish between apps.<br>**Example of data files are in the h=2 folder**<br><Image src="https://files.readme.io/45200b797b4e5e38982f2f795695517cbde9bce2658114ceb6a05edba6612213-32966274476049.png" alt="Unified by App" /><br>The data file naming convention is unique\_id.gz.<br>- Your data loading process must:<br>  - Load data after the \_SUCCESS flag is set.<br>  - Load all files in the folder having a _.gz_ extension. Don't build your import process using part numbering logic. |
| Segregated by app | The folder contains subfolders per app. Data files for a given app are contained within the app folder. In the figure that follows, the h=19 folder contains app folders. Each app folder contains the associated data files. Note! The data files don't contain the app\_id you must determine the app\_id using the folder. <br><Image src="https://files.readme.io/90639507da82f7dafacfa5bfb67fa96a8277747cd0eee226d74498bf5ff16869-32966264040977.png" alt="Segregated by App" /><br>In each app folder the naming convention is unique\_id.gz: <br>- Your data loading process must:<br>  - Load data after the \_SUCCESS flag is set.<br>  - Load all files in the folder having a _.gz_ extension. Don't build your import process using part numbering logic.<br>Limitation: This option is not available for Peopled-Based Attribution reports. |

### Data files

Data files depend on segregation type.

| Content | Details |
| --- | --- |
| Completion flag | The last file (completion) flag is set when all the data for a given h folder has been written. <br>- Don't read data in a folder before verifying that the \_SUCCESS flag exists.<br>- The \_SUCCESS flag is set even in cases where there is no data to write to a given folder and the folder is empty.<br>- Note! In the segregation by app option, the flag is set in the h folder and not the individual app folders. See the figures in the previous section. |
| File types | - Data is provided in Snappy or GZIP compressed files, or uncompressed files, having Parquet or CSV format.<br>- After unzipping, the data files are in Parquet or CSV format according to your settings. |
| Column sequence (CSV files) | In the case of CSV files, the sequence of fields in reports is always the same. When we add new fields these are added to the right of the existing fields. <br>In this regard: <br>- The column structure of user journey reports is identical. This means you can have similar data-loading procedures for different report types. You select the fields contained in the reports. The field meaning is detailed in the [raw data dictionary](https://support.appsflyer.com/hc/articles/208387843-Raw-data-field-dictionary-V5-).<br>- Reports having an FF notation in the report availability section don't adhere to the common column structure. |
| Field population considerations | **Blank or empty fields:** Some fields are populated with _null_ or are empty. This means that in the context of a given report there is no data to report. Typically _null_ means this field is not populated in the context of a given report and app type. Blank "" means the field is relevant in its context but no data was found to populate it with. <br>In the case of the restricted media source, the content of restricted fields is set to null. <br>Overall regard null and blank as one and the same thing; there is no data available. <br>**Time zone and currency**<br>App-specific time zone and currency settings have no effect on data written to Data Locker. The following apply: <br>- **Time zone**: Date and hour data are in UTC.<br>- **Currency**: The field event\_revenue\_usd is in USD.<br>**Values with commas**: These commas are contained between double quotes \`"\`, for example, `"iPhone6,1"`. |

### Storage options

> 🚧 Caution!
>
> If you are using the marketer-owned storage option:
>
> - Verify that you comply with data privacy regulations like GDPR and ad network/SRN data retention policies.
> - Don't use the marketer-owned storage solution to send data to third parties.

- Data is written to a storage owner of your choice as follows:
  - AppsFlyer storage
  - Customer storage—AWS, GCS, Azure, Yandex, BigQuery, and Snowflake
- You can change the storage selection at any time.
- If you change the storage, the following happens:
  - We start writing to the newly selected storage within one hour.
  - We continue writing to the existing storage during a transition period of 7 days. The transition period expiry time displays in the user interface. Use the transition period to update your data loading processes. You can restart the transition period or revert to the AppsFlyer bucket if needed.
  - **Changing storage**: You can migrate from one storage option to another by using the multi-storage option and sending data to multiple destinations simultaneously. Once you have completed the migration and testing, delete the storage option you no longer need.

|  | AppsFlyer-owned storage (AWS) | Marketer-owned storage (GCS, AWS, Azure, Yandex, BigQuery, Snowflake) |
| --- | --- | --- |
| Bucket name | Set by AppsFlyer | - [GCS](https://support.appsflyer.com/hc/articles/360017603577#gcs-storage): No restriction<br>- [AWS](https://support.appsflyer.com/hc/articles/360017603577#aws-storage): Set by you. Must have the prefix af-.<br>Example: `af-datalocker-your-bucket-name` |
| Storage ownership | AppsFlyer | Marketer |
| Storage platform | AWS | AWS, GCS, Azure, Yandex, BigQuery, Snowflake |
| Credentials to access data by you | Available in the Data Locker user interface to your AppsFlyer account admins | Not known to AppsFlyer. Use credentials provided by the cloud provider. |
| Data retention | Data is deleted after 14 days | Marketer responsibility |
| Data deletion requests | AppsFlyer responsibility | Marketer responsibility |
| Security | AppsFlyer controls the storage. The customer has read access. | The marketer controls the storage.<br>- **AWS**: AppsFlyer requires GetObject, ListBucket, DeleteObject, PutObject permission to the bucket. The bucket should be dedicated to AppsFlyer use. Don't use it for other purposes.<br>- **GCS**: See [GCS configuration article](https://support.appsflyer.com/hc/articles/360017603577). |
| Storage capacity | Managed by AppsFlyer | Managed by the marketer |
| Access control using VPC endpoints with bucket policies | Not Applicable | [Optional] In AWS, if you implement VPC endpoint security at the bucket level, you must allowlist AppsFlyer servers. |

#### **Notice to security officers in the case of customer-controlled storage**

Consider:

- The bucket or destination is for the sole use of AppsFlyer. There should be no other entity writing to a given destination.
- You can delete data in the destination 25 hours after we write the data.
- Data written to the destination is a copy of data already in our servers. The data continues to be in our servers in accordance with our retention policy.
- For technical reasons, we sometimes delete and rewrite the data. For this reason, we need delete and list permissions. Neither permissions are a security risk for you. In the case of list, we are the sole entity writing to the bucket. In the case of delete, we are able to regenerate the data.
- For additional information, you can contact our security team via [hello@appsflyer.com](mailto:hello@appsflyer.com) or your CSM.

### Multiple-connections principles (more than one destination)

In Data Locker you can send some or all of your data to 2 destinations (defined in the connection settings). For example, you can send App A data to AWS, and App B data to GCS.

Each connection consists of a complete set of Data Locker settings, including a destination. Connection settings are independent of one another.

In managing your connections, consider:

- In Data Locker settings, connections are shown in tabs. Each connection has its own settings tab from which you can manage the connection. The icon of each tab represents the storage type.
- To see connection details, duplicate a connection, or delete a connection, click \&#x22EE; (options).

## Additional information

### Track connection changes in the audit log

You can view Data Locker connection changes in the Audit log, available from the Security center in the AppsFlyer dashboard. Use the audit log to confirm whether a change was made, when it occurred, and who made it. This can help resolve issues like missing data or unexpected connection changes without needing to contact support.

The following connection lifecycle events are tracked:

- New connection created
- Connection updated
- Connection disabled
- Connection deleted

**To access the audit log:**

1. In the top navigation bar, open <Image src="https://files.readme.io/b7020f3b633fb66e0e2d4988c7903426509b1fa871693cee602a39b8eb9d69d1-34955489919889.png" alt="Account menu" />  the account menu.
2. Select **Security center**.
3. In the **Audit log** section, click **View audit** log.
4. Filter by Service: **Datalocker** to view related entries.

For more information see: [Audit log.](https://support.appsflyer.com/hc/articles/360007971697)

### Traits and Limitations

| **Trait** | Remarks |
| --- | --- |
| Ad networks | Not for use by ad networks |
| Agencies | Not for use by agencies |
| App-specific time zone | Not Applicable. Data Locker folders are divided into hours using UTC. The actual events contain times in UTC. Convert the times to any other time zone as needed. Irrespective of your app time-zone the delay from event occurrence until it is recorded in Data Locker remains the same. |
| App-specific currency | Not supported |
| Size limitations | Not applicable |
| Data freshness | Data is updated according to the specific report data freshness detailed in [this article](https://support.appsflyer.com/hc/articles/4410643856657#raw-data-reports). |
| Historical data | Not supported. If you need historical data, some reports, but not all, are available via Pull API. |
| Restricted data | Fields in some reports are restricted due to privacy limitations. [Learn more](https://support.appsflyer.com/hc/articles/360006868017) |
| User access | Only [account users with required permissions](https://support.appsflyer.com/hc/articles/4409128270481) can configure Data Locker. |
| Single app/multiple app | Multi-app support. Data Locker is at the account level |
| Maximum connections | By default, each account can open up to **2 Data Locker connections**. To request additional connections, **contact your CSM**. |

### Troubleshooting

- **Symptom**: Unable to retrieve data using AWS CLI
- **Error message**: An error occurred (AccessDenied) when calling the ListObjectsV2 operation: Access Denied
- **Cause**: The AWS credentials being used are not the correct credentials for the AppsFlyer bucket. This can be caused by having multiple or invalid credentials on your machine.
- **Solution**:  1. Use a different method, like [Cyberduck](https://support.appsflyer.com/hc/articles/360000877538-Data-Locker-V2-0-high-volume-multi-app-raw-data-delivery#cyberduck) to access the bucket, meaning not the CLI. Do this to verify that the credentials you are using are working. If you are able to connect using Cyberduck, this indicates an issue with the credentials cache.
2. [Refresh the AWS credentials cache](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-role.html).

     **Screenshot from AWS** <Image src="https://files.readme.io/e6608b196c39cb71e0a02e0eabe95378f24659a1578a16fd381bfd0053ca309e-32966264043537.png" alt="AWS Access Denied" />

## AWS data retrieval

Use your preferred AWS data retrieval tool, AWS CLI, or one of the tools described in the sections that follow. Note! The exact instructions are suitable for AppsFlyer owned buckets. Adjust the instructions as needed if you are connecting to your bucket.

### AWS CLI

**Before you begin**:

- Install the AWS CLI on your computer.
- In AppsFlyer, go to Data Locker, and retrieve the information contained in the credentials panel.

**To use AWS CLI**:

1. Open the terminal. To do so in Windows, \<Windows\>+\<R\>, click **OK**.

The command line window opens.
2. Enter **aws configure.**
3. Enter the AWS Access Key as it appears in the credentials panel.
4. Enter your AWS Secret Key as it appears in the credentials panel.
5. Enter **eu-west-1.**
6. Press Enter (None).

Use the CLI commands that follow as needed.

In the following commands, the value of \{home-folder\} can be found

**To list folders in your bucket:**

```auto
Autoaws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/
```

### Listing files and folders

There are three types of folders in your Data Locker bucket:

- Report Type `t=`
- Date `dt=`
- Hour `h=`

To list all the reports of a specific report type:

```auto
Autoaws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/
```

To list all the reports of a specific report type for a specific day:

```auto
Autoaws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17
```

To list all the reports of a specific report, in a specific hour of a specific day:

```auto
Autoaws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17/h=23
```

To download files for a specific date:

```auto
aws s3 cp s3://af-ext-reports/<home-folder>/data-locker-hourly/t=installs/dt=2020-08-01/h=9/part-00000.gz ~/Downloads/
```

### Cyberduck

**Before you begin**:

- Install the Cyberduck client.
- In AppsFlyer, go to Data Locker and retrieve the information contained in the credentials panel.

**To configure Cyberduck**:

1. In Cyberduck, click Action.
2. Select **New Bookmark**. The window opens.
3. In the first field (marked [1] in the screenshot below) select **Amazon S3.** <Image src="https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png" alt="Cyberduck configuration" />
4. Complete the fields as follows:
   - **Nickname:** Free text
   - **Server:** s3.amazonaws.com
   - **Access Key ID:** Copy the AWS Access Key as it appears in the credentials panel in AppsFlyer
   - **Secret Access Key:** Copy the Bucket Secret key as it appears in the credentials panel in AppsFlyer.
   - **Path**: \{Bucket Name\}/\{Home Folder\} For example: **af-ext-reports/1234-abc-ffffffff**
5. Close the window. To do so, click the X in the upper-right corner of the window.
6. Select the connection.

The data directories are displayed.

### Amazon S3 browser

**Before you begin**:

- Install the Amazon S3 Browser.
- In AppsFlyer, go to Data Locker and retrieve the information contained in the credentials panel.

**To configure the Amazon S3 Browser**:

1. In the S3 browser, Click **Accounts** \> **Add** **New Account**.

The Add New Account window opens. <Image src="https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png" alt="S3 Browser Account" />
2. Complete the fields as follows:
   - **Account Name**: free text.
   - **Access Key ID**: copy the AWS Access Key as it appears in the credentials panel.
   - **Secret Access Key**: copy the Bucket Secret key as it appears in the credentials panel.
   - Select **Encrypt Access Keys** with a password and enter a password. Make a note of this password.
   - Select **Use secure transfer.**
3. Click **Save changes**.
4. Click **Buckets** \> **Add External Bucket**.

The Add External Bucket window opens.

<Image src="https://files.readme.io/88dd43f62dbd68d0295b52a7f7b9b09449bd915e6a6d52703c24a50583e05a6e-32966264054929.png" alt="Add External Bucket" />
5. Enter the **Bucket name.** The Bucket name has the following format: \{Bucket Name\}/\{Home Folder\}. The values needed for bucket name and home folder appear in the credentials window.
6. Click **Add External bucket.** The bucket is created and displays in the left panel of the window.

You can now access the Data Locker files.

#### See also

<Cards>
  <Card title="Reports available via Data Locker" href="https://support.appsflyer.com/hc/articles/4410643856657">
    View the list of reports available for export via Data Locker.
  </Card>
  <Card title="Selecting the right raw data delivery tool" href="https://support.appsflyer.com/hc/articles/209680773#reporting-tools%E2%80%94characteristics-and-features">
    Compare raw data delivery tools and choose the best fit for your needs.
  </Card>
</Cards>
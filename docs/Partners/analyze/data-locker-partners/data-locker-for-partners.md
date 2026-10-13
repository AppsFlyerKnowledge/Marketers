---
title: "Data Locker for partners"
excerpt: "Data Locker for partners (ad networks and agencies) delivers app data to the partner's storage in AWS, GCS, or BigQuery."
x-zendesk:
  id: 360020818517
  url: https://support.appsflyer.com/hc/en-us/articles/360020818517-Data-Locker-for-partners
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Data Locker
  section_id: 6551591547409
  position: 0
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-rona-einat, Data Locker, Agencies, Ad Networks]
  labels: [Agencies, Ad Networks, Partners]
  promoted: false
  comments_disabled: true
  created_at: '2021-05-28T15:37:04Z'
  edited_at: '2025-06-05T13:56:06Z'
---
![6133DataLockerForPartners.png](https://files.readme.io/f6cad12250fe07cf2b0a12b64eeaa597c83527b4b4e09aea11cc2a52ab53339b-4637680455313.png)

## Data Locker for partners

Data Locker for partners delivers app data to cloud storage. Advertisers set permissions that allow AppsFlyer to share selected data with a given partner.

### Data Locker features

| Feature | Description |
| --- | --- |
| Storage options (cloud) | Storage (bucket) owned by you on:<br />- AWS <br />- GCS<br />- Yandex<br />- BigQuery<br />[About storage options](/docs/data-locker-for-marketers#storage-options) |
| Multi app support | Supports data of apps that are integrated with you. The advertiser must give permission per report for you to get the data. |
| Data format options | - For bucket cloud storage:<br />  - CSV<br />  - Parquet<br />  - Adobe<br />- Data warehouse |
| Data freshness | Freshness depends per report type:<br />- **Hourly:** Data generated continuously<br />- **Daily:** Some reports are prepared on a daily basis and are ready on the following day |

### Reports available for partners

The reports available and the permissions required to get the reports differ per partner type. However, the Data Locker mechanism, storage options, and settings required are the same irrespective of the partner type. See the articles per partner type as follows:

- [Ad networks](/docs/data-locker-reports-available-for-ad-networks)
- [Agencies](/docs/data-locker-reports-for-agencies)
- [Marketing partners](/docs/data-locker-reports-for-api-partners)

## Data storage architecture

### Overview

Data is written to your selected storage option. You can switch from one option to another at any time. The change occurs within hours.

Data in the cloud bucket storage is organized in a hierarchical folder structure, according to report type, date, and time. The following figure contains an example of this structure:

![DLFolderOVerview.png](https://files.readme.io/78f360ec1df72253e5b2cd725f3eecf4e17548a7f06b544a94a75a2c319d77a0-18107910420369.png)

Data of a given report is contained in the hour (h) folders associated with that report.

- The number of hour folders depends on if the report streams hourly or daily.
- Data is provided in Snappy or GZIP compressed files, or uncompressed files, having Parquet or CSV format.
- Data files consist of columns (fields).
- The column structure is defined per report type.

### Folder structure

| Folder | Description |
| --- | --- |
| data-locker-hourly | ![DLHourly.png](https://files.readme.io/c257b82d22622d97808a6c23603ac4eee9f2ab091bcb68a33637ac4fb749fdff-18107874510353.png)<br />- The top-level folder in the bucket depends on the storage provider.<br />- The _data-locker-hourly_ folder contains the report topics. <br />**Examples of folder structure based on bucket owner and cloud provider**:<br />- **Your AWS bucket**: _\<af-datalocker-your bucket prefix>\/\<generated-home-folder>\<subscription-id>_<br />- **Your GCS bucket:** \<your bucket name>\/\<generated-home-folder>\/\<subscription-id> |
| t (topic) | Report type relates to the subject matter of the report. |
| dt (date) | This is the related data date. In most cases, this means the date the event occurred. |
| h (hour) | The h folders relate to the time AppsFlyer received the data. For example, install events received between 14:00-15:00 UTC are streamed to the h=14 file. Note! There is a lag, of about 6 hours, between the time the data arrives in AppsFlyer until the h folder is streamed to Data Locker. For example, the h=14 folder is streamed six hours later at 23:00 UTC. <br />**Folder characteristics**:<br />- There are 24 h folders numbered 0-23. For example, h=0, h=1, and so on. <br />- In addition, a late folder contains events from the preceding day arriving after midnight (in other words, events that arrive between 00:00–02:00 UTC of the following day). For example, if a user installs an app on Monday at 08:00 and the event arrives on Tuesday at 01:00, the event is recorded in Monday's late folder. <br />- Data arriving after 02:00 is recorded in the folder of the actual arrival date and time. <br />- You must use the data in the late folder. It isn't contained in any other folder. <br />- \_temporary folder **:** In some cases, we generate a temporary folder within an h folder. Disregard temporary folders and subfolders. Example: /t=impressions/dt=2021-04-11/h=18/\_temporary. |
| Unified data | Data for all apps is provided in unified data files. When you load the data, use the row-level app\_id field to distinguish between apps.<br />**Example of data files are in the h=2 folder**<br />![UnifiedByApp.png](https://files.readme.io/dbc39c2ce99c1ff607fd553b9c9034e55728c102f31fd18a501cc00910267b28-18107874522513.png)<br />- In your data loading process ensure that:<br />  - You begin to consume data only after the \_SUCCESS flag is set.<br />  - You load all files having a _.gz extension._ |
| Completion flag | The last file (completion) flag is set when all of the data for a given h folder has been written. <br />- Don't read data in a folder before verifying that the \_SUCCESS flag exists.<br />  <br />- The \_SUCCESS flag is set even in cases where no data is written to the folder. Meaning the folder is empty. |
| Zipping | Files are zipped using gz. After unzipping:<br />- The files have no extension.<br />- Each file has a header row containing the column (field) names. |
| Column sequence | The sequence of fields in reports is always the same. New fields are added to the right of existing fields. <br />Column (field) definitions are defined per report. Check the relevant report article for the description. |
| Field population considerations | **Blank or empty fields**: Some fields are populated with _null_ or are empty. This means that in the context of a given report there is no data to report. Typically _null_ means this field is not populated in the context of a given report and app type. Blank "" means the field is relevant in its context but no data was found to populate it with. <br />**Time zone and currency**:<br />App-specific time zone and currency settings are disregarded for data provided by Data Locker. As such: <br />- **Time zone**: Date and hour data are in UTC<br />- **Currency**: The field event\_revenue\_usd is in USD<br />**Values with commas**: These comas are contained between double quotes `"`, for example, `"iPhone6,1"`. |

### Data files

Data files depend on segregation type.

| Content | Details |
| --- | --- |
| Completion flag | The last file (completion) flag is set when all the data for a given h folder has been written. <br />- Don't read data in a folder before verifying that the \_SUCCESS flag exists.<br />  <br />- The \_SUCCESS flag is set even in cases where there is no data to write to a given folder and the folder is empty. <br />  <br />- Note! In the segregation by app option, the flag is set in the h folder and not the individual app folders. See the figures in the previous section. |
| File types | - Data is provided in Snappy or GZIP compressed files, or uncompressed files, having Parquet or CSV format.<br />- After unzipping, the data files are in Parquet or CSV format according to your settings. |
| Column sequence (CSV files) | In the case of CSV files, the sequence of fields in reports is always the same. When we add new fields these are added to the right of the existing fields. <br />In this regard: <br />- The column structure of user journey reports is identical. This means you can have similar data loading procedures for different report types. You select the fields contained in the reports. The field meaning is detailed in the [raw data dictionary](/docs/raw-data-field-dictionary). <br />- Reports having an FF notation in the report availability section don't adhere to the common column structure. |
| Field population considerations | **Blank or empty fields:** Some fields are populated with _null_ or are empty. This means that in the context of a given report there is no data to report. Typically _null_ means this field is not populated in the context of a given report and app type. Blank "" means the field is relevant in its context but no data was found to populate it with. <br />In the case of the restricted media source, the content of restricted fields is set to null. <br />Overall regard null and blank as one and the same thing; there is no data available. <br />**Time zone and currency**<br />App-specific time zone and currency settings have no effect on data written to Data Locker. The following apply: <br />- **Time zone**: Date and hour data are in UTC.<br />- **Currency**: The field event\_revenue\_usd is in USD.<br />**Values with commas**: These commas are contained between double quotes `"`, for example, `"iPhone6,1"`. |

### Storage options

- Data is written to a storage owner of your choice as follows: AWS, GCS, and BigQuery.
- You can change the storage selection at any time.
- If you change the storage, the following happens:
  - We start writing to the newly selected storage within one hour.
  - We continue writing to the existing storage during a transition period of 7 days. The transition period expiry time displays in the user interface. Use the transition period to update your data loading processes.
  - **Changing buckets**: If you change storage, data is sent to both for a transition period of 7 days, allowing you to align your data consumption process.

|  | Partner-owned storage (GCS, AWS, BigQuery) |
| --- | --- |
| Bucket name | - GCS: No restriction<br />- AWS: Set by you. Must have the prefix af-.<br />Example: `af-datalocker-your-bucket-name` |
| Storage owner | Partner |
| Storage platform | AWS, GCS, Yandex, BigQuery |
| Credentials to access data by you | Not known to AppsFlyer. Use credentials provided by the storage provider. |
| Data retention | Controlled by you |
| Security | You control the storage. <br />- **AWS**: AppsFlyer requires GetObject, ListBucket, DeleteObject, PutObject permission to the bucket. The bucket should be dedicated to AppsFlyer use. Don't use it for other purposes.<br />- [GCS](/docs/data-locker-cloud-service-setup#gcs-storage) |

#### **Notice to security officers**

> 📘 Notice to security officers
>
> Consider:
> - The bucket or destination is for the sole use of AppsFlyer. There should be no other entity writing to the bucket.
> - You can delete data in the bucket 25 hours after we write the data.
> - Data we write to the destination is a copy of data already in our servers. The data continues to be in our servers in accordance with our retention policy.
> - For technical reasons, we sometimes need to delete and rewrite the data. For this reason, we require delete and list permissions. Neither list nor delete are a security risk for you. In the case of list, we are the sole entity writing to the bucket. In the case of delete, we can regenerate the data.

### Multiple-connection principles (more than one destination)

In Data Locker you can send some or all of your data to more than one destination (defined in the connection settings). For example, you can send App A data to AWS, and App B data to GCS.

Each connection consists of a complete set of Data Locker settings, including a destination. Connection settings are independent of one another.

In managing your connections, consider:

- In Data Locker settings, connections are shown in tabs. Each connection has its own settings tab from which you can manage the connection. The default tab is “Data Locker.”
- To create a new connection:
1. Click **Add connection**.
2. Provide a name for the connection and choose the storage type.
3. Click **Save**.

     Once saved, the connection displays next to the default “Data Locker” tab. The icon of each tab represents the storage type.
- To see connection details, duplicate a connection, or delete a connection, click ⋮ (options).

## Procedures

### Set up Data Locker

Use this procedure to set up Data Locker. Changes to settings take effect within 3 hours.

**Prerequisite:**

Complete one or more of the following storage procedures:

- [AWS](/docs/data-locker-cloud-service-setup#aws-storage) bucket
- [GCS](/docs/data-locker-cloud-service-setup#gcs-storage) bucket
- [Beta] [Yandex](/docs/data-locker-cloud-service-setup#yandex) bucket
- [BigQuery](/docs/data-locker-cloud-service-setup#bigquery) data warehouse

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/771bf2946e0e5bde4126a710540eda14172a849d58185b9c5dbd240481c2efe2-18107874528145.png) To set up Data Locker:**

1. Log in to your [AppsFlyer partner dashboard.](https://hq1.appsflyer.com/auth/login)
2. Go to:
   - **Advertisers**: In AppsFlyer, from the sidebar, open **Export** > **Data Locker**.
   - **Marketing partners**: Click the **account menu** \> **Data Locker**.
3. Follow the [Data Locker setup instructions](/docs/data-locker-for-marketers#set-up-data-locker) steps 3-16.

## Additional information

### Traits and Limitations

| **Trait** | Remarks |
| --- | --- |
| App-specific time zone | Not Applicable |
| App-specific currency | Not supported |
| Size limitations | Not applicable |
| Data freshness | Data is updated according to the specific report data freshness detailed in this article. |
| Historical data | Not supported |
| Team member access | Team members cannot set up Data Locker. |

### Troubleshooting

[Use this troubleshooting guide](/docs/data-locker-for-marketers#troubleshooting) **.**
---
title: Data Clean Room—Working with sources
metadata:
  keywords:
    - Advertisers
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
  created_at: '2022-03-27T10:58:23Z'
  edited_at: '2026-08-14T16:22:51Z'
  id: 5041487011601
  locale: en-us
  section: Data Clean Room
  section_id: 4591191779217
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/5041487011601-Data-Clean-Room-Working-with-sources
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Set up the custom data sources you share with the Data Clean Room (DCR) for matching with attribution data and creating DCR reports.

## Introduction

Many DCR reports are designed to match your **attribution data** with data from your **custom data sources.** This article contains everything you need to know about working with your custom data sources, including how to:

* [Format the data source](/docs/data-clean-room-working-with-sources#source-requirements)
* [Create the source](/docs/data-clean-room-working-with-sources#creating-a-source) within the DCR
  * [Name the source](/docs/data-clean-room-working-with-sources#1-name-the-source)
  * [Specify the location](/docs/data-clean-room-working-with-sources#2-specify-the-source-location) from which the DCR will retrieve the data source
  * [Define the structure](/docs/data-clean-room-working-with-sources#3-define-the-source-structure) of the source (labeling fields as metrics, dimensions, and identifiers)
  * [Save the source](/docs/data-clean-room-working-with-sources#4-save-the-source)
* [Update source data](/docs/data-clean-room-working-with-sources#updating-sources-to-trigger-report-processing) on a regular basis to trigger report processing
* [Work with existing sources](/docs/data-clean-room-working-with-sources#working-with-existing-sources)

> 🚧 **Important**
>
> **Before you begin**
>
> Before you create custom data sources, you should first:
>
> * [Required] <Anchor target="_blank" href="/marketers/id/docs/data-clean-room-setting-up-cloud-services">Set up the cloud services</Anchor> from which the DCR will retrieve the data. Two types of cloud services are supported:
>   * **Data warehouses:** BigQuery and Snowflake
>   * **Cloud storage buckets:** Amazon S3 (AWS) and GCS
> * [Optional] <Anchor target="_blank" href="/marketers/id/docs/data-clean-room-working-with-connections#creating-inbound-connections">Create inbound connections</Anchor> in the AppsFlyer platform to connect these cloud services to the DCR.
>   * If these connections were not set up previously, you will be prompted to set them up during source creation.

## Source requirements

Sources must meet these requirements in order to prevent errors in source creation and report processing.

<div id="data-format" />

<Accordion title="Data format (relevant to all data sources)">

Data within sources must meet these requirements:

* **Date and time:**
  * **Format:** yyyy-MMM-dd hh:mm:ss (*for example*, `2023-APR-18 15:30:35`)
  * **Time zone:** UTC
* **Numbers:** maximum 2 digits following the decimal point
* **String length:** maximum of 256 characters
* **Character limitations:**
  * **For field names (column headers):** no spaces or special characters
  * **All other data:** no limitations (all characters are valid)

</Accordion>

<div id="table-columns" />

<Accordion title="Table columns (relevant only to data sources in data warehouses)">

In addition to data shared for processing, source tables in BigQuery or Snowflake must include 2 additional columns – one for **date** and one for **version:**

* **Date:**
  * **Column header:** `dt`
  * **Column type:** date
  * **Data format:** yyyy-mm-dd (*for example*, `2023-04-18`)
  * **Additional:** BigQuery tables must be <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/partitioned-tables">partitioned</Anchor> by this column
* **Version:**
  * **Column header:** `v`
  * **Column type:** string
  * **Data format:** number (for example, `1`, `2`, `3`, `10`)
  * **Important!** A new version of a report is triggered each time the DCR detects a new value in this column. To ensure the completeness of your report, be sure to populate the source table with a complete set of data whenever the column value is changed.

</Accordion>

<div id="file-format" />

<Accordion title="File name and format (relevant only to data sources in cloud storage buckets)">

Data source files stored in Amazon S3 or GCS must meet these file name and format requirements:

* File name must comply with <Anchor target="_blank" href="/marketers/id/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR naming requirements</Anchor>
* CSV or GZIP format
  * The file underlying GZIP compression must be a CSV file.
* Number of data source files per [data folder](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version):
  * **CSV:** Maximum of 1
  * **GZIP:** Maximum of 1 single-part file. Multi-part GZIP files are supported when named as follows: `filename_part01.gz`, `filename_part02.gz`, etc.

</Accordion>

## Creating a source

The process of creating a source consists of **all the steps described below.** They are separated into tabs simply for ease of reading.

**Follow these steps to create a source:**

<div id="1-name-the-source" />

<Accordion title="#1: Name the source">

1. Go to the **Sources** tab of the **Data Clean Room.**
2. Click the **+ New source** button.  
   The **New source** page opens.
3. Enter the name of the source in the upper-left corner.
   * This can be any unique name that will help you identify the source in the DCR platform. For cloud integrations, the name doesn't need to match the file name.
   * **Important!** Ensure that the source name is different from all other sources in your account or you won't be able to [save the source](/docs/data-clean-room-working-with-sources#4-save-the-source).
   * Source name requirements:
     * Length: 2-80 characters
     * Valid characters:
       * letters `(A-Z, a-z)`
       * numbers `(0-9)`, *cannot be the first character of a name;*
     * Invalid characters:
       * spaces
       * all other symbols or special characters

</Accordion>

<div id="2-specify-the-source-location" />

<Accordion title="#2: Specify the source location">

**To specify the data source location:**

1. Select the <Anchor target="_blank" href="/marketers/id/docs/data-clean-room-setting-up-cloud-services#overview">connection</Anchor> in which the source will be (or has been) created.
   * If there are no connections defined in your account, the **New connection** dialog will open, prompting you to create one. Follow <Anchor target="_blank" href="/marketers/id/docs/data-clean-room-working-with-connections#complete-the-connection">these instructions</Anchor> to create it.
   * If you have existing connections but want to use a new one, click the ![dcr_new_connection_button.png](https://files.readme.io/0a6766bcb5deef0b2264b372592b82485cc59b11e454cdcbd4a1718de4df951d-14989643499153.png) button to open the **New connection** dialog. Follow <Anchor target="_blank" href="/marketers/id/docs/data-clean-room-working-with-connections#complete-the-connection">these instructions</Anchor> to create it.
2. Continue with the relevant instructions below based on where the data for your source is located.

#### Source locations in BigQuery

**To complete specifying the data source location for BigQuery sources:**

1. Select the dataset in which the source table is located.
2. Select the table in which the source data is located.

The lists from which you make these selections contain the available datasets and tables, respectively, in the BigQuery project you specified when creating the connection.

#### Source locations in Snowflake

**To complete specifying the source location for Snowflake sources:**

1. Select the share containing the source data.
2. Select the schema in which the source table is located.
3. Select the table in which the source data is located.

The lists from which you make these selections contain the shares, schemas, and tables, respectively, in the Snowflake account you specified when creating the connection.

#### Source locations in cloud storage buckets

Source locations in Amazon S3 or GCS consist of the cloud storage bucket specified by the connection and the underlying folder path from which the DCR reads the source file each time it is updated.

Once you have specified the connection, AppsFlyer can automatically generate the required underlying folder path as part of the source creation process.

* Allowing AppsFlyer to generate the folders makes the process easy. However, you can choose to manually create them instead, according to the instructions <Anchor target="_blank" href="/marketers/id/docs/data-clean-room-setting-up-cloud-services">detailed here</Anchor>.

- or -

* You can upload a prototype version of the source file directly from its connection.
  * If you select this option, there's one additional choice to make:
    * Allow AppsFlyer to automatically create the source folder structure; or
    * Create the source folder structure manually

If AppsFlyer generates the folders, the only additional information required is the name you want to give the **source folder.** (This is the top-level folder in which you update the source each time your want to use it for running a new report version.) You can also indicate whether you want the source folder to be created underneath a parent folder – often named **input.**

**To complete specifying a source location in a cloud storage bucket, enter the source folder name.**

* By default, the displayed source folder name:
  * Is based on the [name you gave the source](/docs/data-clean-room-working-with-sources#1-name-the-source). You can change the folder name to meet your needs, so long as it complies with the <Anchor target="_blank" href="/marketers/id/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR naming requirements</Anchor>.
  * Indicates that it will be generated within a parent folder named **input.** This folder serves as the parent folder for all sources you upload to the DCR.
    * The **input** folder is not required, and you can remove it or name it something different, so long as it complies with the <Anchor target="_blank" href="/marketers/id/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR naming requirements</Anchor>.
    * Although this folder is not required, having an **input** folder (or an equivalent folder of a different name) is considered best practice. It is even more highly recommended when you are using the same cloud storage bucket both for uploading data files (input) and receiving reports (output).

> 🚧 **Important**
>
> If you manually created the folder path, make sure the connection and path you enter in the **Source location** section match the path you manually created.

</Accordion>

<div id="3-define-the-source-structure" />

<Accordion title="#3: Define the source structure">

For all sources that you share with the DCR for processing, AppsFlyer needs to know how each data field should be used in order to create reports. Defining the source structure consists of:

* [Loading the source fields](/docs/data-clean-room-working-with-sources#loading-source-fields)
* [Categorizing each field](/docs/data-clean-room-working-with-sources#categorize-fields) (column) as one of the following types:
  * **Identifier:** Field that identifies a unique app user (examples might include CUID, AppsFlyer ID, etc.)
    * The primary purpose of identifiers in the context of the DCR is to join data sources so that corresponding user-level data can be matched.
  * **Dimension:** An attribute by which you categorize app users (examples might include geo, install date, campaign, etc.)
  * **Metric:** Numeric data you have collected with respect to an app user (examples might include revenue, number of app opens, LTV, etc.)
    * A data field identified as a metric can contain **only numeric values.**

#### Loading source fields

Load source fields using the relevant instructions below:

**Data warehouse sources**

To load fields from a data source located in a data warehouse (BigQuery or Snowflake), click the ![dcr_load_fields_from_source.png](https://files.readme.io/667761e044a45e9a63bf904ada0ba07917014b5b446379213742510278b5a2dd-14986195290897.png) button.

> 🚧 **Important**
>
> If the selected source table does not include the required [date and version columns](/docs/data-clean-room-working-with-sources#table-columns), you will receive an error.

**Cloud storage bucket sources**

To load fields from a data source located in a cloud storage bucket (Amazon S3 or GCS), you must upload a prototype source file.

For purposes of defining the source structure:

* You can upload a prototype version of the data source from a local file.
  * If you select this option, AppsFlyer always creates the source folder path automatically.

- or -

* You can upload a prototype version of the source file directly from its connection.
  * If you select this option, there's one additional choice to make:
    * Allow AppsFlyer to automatically create the source folder structure; or
    * Create the source folder structure manually

**To upload your prototype source file, follow the instructions in the relevant tab below:**

<Tabs>
<Tab title="Local file">

1. In the **Source structure** section, click the <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" /> button.
2. In the window that opens, select **Upload a local file.**
3. Specify the CSV or GZIP file you want to upload, then click OK.

</Tab>

<Tab title="Connection (automatic creation)">

**To load the file from its connection and allow AppsFlyer to create the source folder structure:**

1. In the **Source structure** section, click the <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" /> button.
2. In the window that opens, select **Load from connection.**
3. Click the **Generate folders** link.
   * AppsFlyer automatically creates the required folder structure and source folder (on the connection you specified, with the source folder name you specified).
4. After the source folder structure has been created, a confirmation message is displayed, including a link to the source folder. Click the provided link to upload your prototype file to the source folder.
5. Once the file has finished uploading, click **OK.**

</Tab>

<Tab title="Connection (manual creation)">

**To upload the source file from a structure you created manually:**

1. In the **Source structure** section, click the <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" /> button.
2. In the window that opens, select **Load from connection.**
3. **DO NOT** click **Generate folders.** Instead, upload the file directly to the source folder you created for it.
4. Once the file has finished uploading, click **OK.**

</Tab>
</Tabs>

#### Categorize fields

After you load the fields, AppsFlyer analyzes the file, and a list of all data fields (columns) is displayed in the **Available fields** list.

**To categorize the fields:**

1. Select one or more fields in the **Available fields** list on the left and use the buttons in the middle of the screen to categorize them as [identifiers, dimensions, or metrics](/docs/data-clean-room-working-with-sources#3-define-the-source-structure).
   * Once you categorize a field, it is displayed in the relevant category list on the right side of the screen.
   * You can use the search bar to search for fields in the lists.
   * To remove a field from a category it's been assigned to, select it in the relevant category list and use the **Remove** button to return it to the **Available fields** list.
2. Repeat this process until you have categorized each field you want to include in DCR reports.
   * There is no requirement to categorize every field in the **Available fields** list. However, a field must be categorized in order to use it later in a report.
3. If you edit the source before [saving the source](/docs/data-clean-room-working-with-sources#4-save-the-source) and want to use fields from the edited source data, click the **Reload fields** link at the bottom of the **Available fields** list.
   * Note that reloading the source will overwrite the field names in the Available fields list. Any fields that you previously categorized will remain in the **Identifiers, Dimensions,** or **Metrics** lists.
   * If a previously categorized field is not found in the reloaded source data, it will still display in the relevant category list, but it will be marked with an error icon.

> 📘 **Note**
>
> If you decide to use additional fields from this source after saving it, you can do so by [editing the source structure](/docs/data-clean-room-working-with-sources#editing-the-source-structure).

</Accordion>

<div id="4-save-the-source" />

<Accordion title="#4: Save the source">

**To save the source:**

1. [Optional] Click <Image alt="DCR_test_source.png" src="https://files.readme.io/c8d2bb2e7062d062a2ed7ddb84472c5acd02fc93b178b2299515b2374a3ad3e3-11240865384849.png" width="43px" /> to check for errors in the format or validity of the source fields.
2. Click **Save** to save the source.

   The source is created and a confirmation message is displayed.

   * If you uploaded the source from a local file, saving the source triggers the automatic creation of the folder structure, and the displayed confirmation message includes a link to the source folder.

   The new source is displayed in the list of all existing sources in the **Sources** tab of the Data Clean Room.

</Accordion>

## Updating sources to trigger report processing

Each time you want AppsFlyer to process a data source file and run a report based on it, you upload a new version of the file to the source folder, within a series of nested subfolders indicating the date and version number (plus one extra subfolder to let AppsFlyer know where the data is).

AppsFlyer continually scans for new versions of source files for the **current date and 2 days prior.** A new version of a report is triggered each time new versions of the source files are found (including [\_SUCCESS files](/docs/data-clean-room-working-with-sources#_success-files), as further detailed below).

<div id="nested-subfolders-for-each-date-and-version" />

<Accordion title="Nested subfolders for each date and version">

The structure of nested subfolders is as follows:

* Within the source folder --> 1 subfolder for each date ("date folder")
  * **Format:** `dt=yyyy-mm-dd/`
  * **Example:** `dt=2022-12-15/`
* Within each date folder --> 1 subfolder for each version on that date ("version folder")
  * **Format:** `v=n/`
  * **Example:** `v=1/`
  * **Note:** The version folder is required even if you only upload the file one time per day.
* Within each version folder --> 1 subfolder to indicate the location of the data ("data folder")
  * **Format:** `data/`
  * The data folder is the location to which the source file is uploaded.

In most cases, you use API calls or other available programmatic means to create the date/version/data folders automatically each time the data source file is uploaded. For additional information, see the API reference for your cloud service: <Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html">AWS</Anchor>, <Anchor target="_blank" href="https://cloud.google.com/storage/docs/reference/libraries">GCS</Anchor>.

</Accordion>

<div id="_success-files" />

<Accordion title="_SUCCESS files">

Once the upload of a source file to the data folder is complete, an empty file named `_SUCCESS` should be uploaded to the **version** folder. This alerts AppsFlyer that a new file is available to be processed. In most cases, you use an API script to automatically generate and upload this file.

**Important!** The `_SUCCESS` file must be uploaded to the **version** folder, outside the data folder.

The filename for the \_SUCCESS file:

* Must be in ALL CAPS
* Must be preceded by an underscore `(_)`
* Should not have a file extension

For multi-part GZIP files:

* Only one `_SUCCESS` file should be uploaded for all file parts.
* The `_SUCCESS` file should be uploaded only after all file part uploads are complete.

</Accordion>

<div id="example-after-uploading-files" />

<Accordion title="Example (after uploading files)">

After uploading source files on 2 days (and programmatically creating date/version/data folders and `_SUCCESS` files), your bucket/folder structure might look something like this:

<Image align="center" alt="dcr_file_structure_after_uploads.png" src="https://files.readme.io/f6e753cdf8389c0b99cad9cbf1a06261473ef87ce6f840a21ab8d9ccea20aed4-11420299723665.png" />

</Accordion>

## Working with existing sources

There are several ways in which you might want to work with existing sources. You initiate these processes from the **Sources** tab of the Data Clean Room:

* [Editing the source name](/docs/data-clean-room-working-with-sources#editing-the-source-name)
* [Editing the source structure](/docs/data-clean-room-working-with-sources#editing-the-source-structure)
* [Deleting a source](/docs/data-clean-room-working-with-sources#deleting-a-source) (if it's not being used for a report)

<div id="editing-the-source-name" />

<Accordion title="Editing the source name">

To edit the source name:

1. Go to the **Sources** tab of the **Data Clean Room.**
2. In the list of sources, hover over the row of the source you want to edit.
3. Click the edit button ![edit_button.png](https://files.readme.io/aeb81045ac5e49107cfb1e6cb0b49d5184ea1d70a20e3c58f684bc44f6e25c66-5366594803473.png) that displays on the right side of the row.
4. On the **Edit source** page, edit the name of the source.
5. Click the **Save** button to save the source with the new name or **Cancel** to undo your changes.

</Accordion>

<div id="editing-the-source-structure" />

<Accordion title="Editing the source structure">

To edit the source structure:

1. Go to the **Sources** tab of the **Data Clean Room.**
2. In the list of sources, hover over the row of the source you want to edit.
3. Click the edit button ![edit_button.png](https://files.readme.io/aeb81045ac5e49107cfb1e6cb0b49d5184ea1d70a20e3c58f684bc44f6e25c66-5366594803473.png) that displays on the right side of the row.
4. On the **Edit source** page, the fields that were previously categorized as [identifiers, dimensions, or metrics](/docs/data-clean-room-working-with-sources#3-define-the-source-structure) will display in the relevant category lists on the right side of the screen.
5. You can move a previously categorized field to a different category without reloading fields from the source file. To do this:
   1. First, select it in the relevant category list and use the **Remove** button to return it to the **Available fields** list.
   2. Next, select it in the **Available fields** list and use the buttons in the middle of the screen to categorize it as an identifier, dimension, or metric.
6. To work with fields in the source file that have not yet been categorized, they must be reloaded from the source location or from a local file. Make this selection by clicking the **Reload fields** link at the bottom of the **Available fields** list.
7. AppsFlyer analyzes the file, and a list of all previously uncategorized data fields (columns) is displayed in the **Available fields** list.
   * Fields that were previously categorized as identifiers, dimensions, or metrics will still display in the relevant category lists on the right side of the screen.
   * If a previously categorized field is not found in the reloaded source file, it will still display in the relevant category list, but it will be marked with an error icon.
8. Select one or more fields in the **Available fields** list on the left and use the buttons in the middle of the screen to categorize them as identifiers, dimensions, or metrics.
9. Once you have made all necessary changes, click the **Save** button to save the source with the updated structure or **Cancel** to undo your changes.

> 🚧 **Important**
>
> Don't forget to make corresponding changes reflecting the new source structure in any reports for which this source is used:
>
> * Fields that were removed, uncategorized, or changed from their previous categories are automatically removed from any reports in which they are used.
> * Newly added or categorized fields are not automatically included in existing reports until you edit report definitions to include them.

</Accordion>

<div id="deleting-a-source" />

<Accordion title="Deleting a source">

1. Go to the **Sources** tab of the **Data Clean Room.**
2. In the list of sources, hover over the row of the source you want to delete.
3. Click the delete button ![delete_button.png](https://files.readme.io/dbdbc085f6b7b5c2143c14494d1694fad5a3902ed57f8b34ded2144260164716-5367408938513.png) that displays on the right side of the row.
4. In the dialog, confirm that you want to delete the source.
   * You cannot delete a source that is being used by a report. If this is the case, a message will list the reports in which the source is being used. In order to delete the source, you can either:
     * Delete the reports in which it is being used; or
     * Remove the source fields from the definitions of the reports in which they are used.

</Accordion>

## Reference

<div id="manually-creating-a-folder-structure" />

<Accordion title="Manually creating a storage bucket folder structure (relevant only if you choose to do so)">

In general, it's easiest to allow AppsFlyer to automatically generate the required folder structure as part of the source creation process. However, if you wish to create these folders manually, you can do so as follows.

#### Create a DCR key folder

To ensure maximum security, the folder directly beneath the bucket (the "DCR key folder") must be named with the 8-character, alphanumeric **DCR key** assigned to your account (for example, `01bcc5fb`). *Note that this is different from any other password or key associated with your AppsFlyer account.*

The DCR key folder is generally created manually using the interface of your selected cloud service.

**To get your account's DCR key, click the DCR key button at the top of the main DCR page.**

<Image align="center" alt="dcr_key_button.png" src="https://files.readme.io/8d02c129ce45b19b28523419e43ec8227a9179e3bafb2b84c0a523b247061c19-16571022734353.png" />

After creating the DCR key folder, your bucket/folder structure would look something like this:

<Image align="center" alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png" />

#### Top-level input folder

Though it is not required, best practice is to create a top-level input folder directly beneath the DCR key folder. This folder will be dedicated to files you upload to the DCR.

The top-level input folder is generally created manually using the interface of your selected cloud service.

* This practice is even more highly recommended when you are using the same bucket both for uploading data files (input) and receiving reports (output).
* You can name this folder anything you want, so long as it complies with the <Anchor target="_blank" href="/marketers/id/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR naming requirements</Anchor>. For ease of identification, it is usually named `input/`.

After creating the top-level input folder, your bucket/folder structure might look something like this:

<Image align="center" alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png" />

#### Second-level folder for each data source

You can regularly upload different data source files to the DCR for processing. Each of these data sources must be assigned a separate folder ("data source folders").

So, for example, if you plan to upload 2 files to the DCR for processing every day: *BI-data.csv* and *CRM-data.gzip*, you would assign each of these data sources a folder. You could choose to call these folders `BI-data/` and `CRM-data/`.

The data source folders are generally created manually using the interface of your selected cloud service.

After creating 2 data source folders, your bucket/folder structure might look something like this:

<Image align="center" alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png" />

Under each data source folder, [nested subfolders by date and version](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version) must be created each time the source is updated.

</Accordion>

<div data-zendesk-anchors="h_01HPKB2ERNRQG73AFA0X7XEDEF=introduction source-format=source-requirements h_01HPKB2ERPANE0CAXFP9RG5YEH=source-requirements h_01HPKB2ERPQ787V0PAABP7Q2YY=data-format h_01HPKB2ERPJ5PVQ2QM5XCYZE0D=table-columns h_01HPKB2ERPWZFZN2DSCHWNXKXX=file-format h_01HPKB2ERPX2T413N3T93YBBZB=creating-a-source h_01HPKB2ERPQMT0NKTE5NN40KG4=1-name-the-source h_01HPKB2ERQWDMYBEPDZY17T9PG=2-specify-the-source-location h_01HPKB2ERQ28JQ2CK16RYZ38G6=source-locations-in-bigquery h_01HPKB2ERQWFGF8MN8ZYAXWC87=source-locations-in-snowflake h_01HPKB2ERQZT3Y6GNZ2WWWM0M7=source-locations-in-cloud-storage-buckets h_01HPKB2ERQ40VTVZA5DGNR907G=3-define-the-source-structure h_01HPKB2ERQTJPGG68FSEBHVVJA=loading-source-fields h_01HPKB2ERSYCFE1EYTCK550VTK=categorize-fields h_01HPKB2ERS55YGWY3RMRPR02Y4=4-save-the-source uploading-source-files-to-trigger-report-processing=updating-sources-to-trigger-report-processing h_01HPKB2ERSCPAPB6WE3354ECW9=updating-sources-to-trigger-report-processing h_01HPKB2ERSEVBTS3DR2TB6Y1AQ=nested-subfolders-for-each-date-and-version h_01HPKB2ERSJ9KNDK6CEBRQB65C=_success-files h_01HPKB2ERSJKGVE61T6J9HXTCK=example-after-uploading-files h_01HPKB2ERS5PK2P2XTC4ZMPCMC=working-with-existing-sources h_01HPKB2ERTC48MGS0BM5SDR6XV=editing-the-source-name h_01HPKB2ERTS6DEQX0KP0EQTGSP=editing-the-source-structure h_01HPKB2ERVGJYJ9KW1RGX24CGV=deleting-a-source h_01HPKB2ERV1KK3J8YX918GCF3M=reference h_01HPKB2ERVZ88MJ35JC66YDPAB=manually-creating-a-folder-structure creating-a-dcr-key-folder=create-a-dcr-key-folder h_01HPKB2ERV7MQJ9CK44T92GK2G=create-a-dcr-key-folder toplevel-input-folder=top-level-input-folder h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=top-level-input-folder secondlevel-folder-for-each-data-source=second-level-folder-for-each-data-source h_01HPKB2ERVVFMP81RE8ATZ6SZ8=second-level-folder-for-each-data-source" />

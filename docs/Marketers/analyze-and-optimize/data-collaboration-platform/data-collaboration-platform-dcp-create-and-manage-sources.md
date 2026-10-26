---
title: Data Collaboration Platform (DCP) - Create and manage sources
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
  created_at: '2024-05-02T13:56:27Z'
  edited_at: '2026-09-22T08:22:34Z'
  id: 24740010687249
  locale: en-us
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/24740010687249-Data-Collaboration-Platform-DCP-Create-and-manage-sources
---
> **At a glance:** Create and manage sources to securely share your first-party data with other collaborators.

## About DCP sources

In the Data Collaboration Platform (DCP), a source is a dataset, typically uploaded to AppsFlyer from your cloud storage. These sources form the foundation of any collaboration, supplying the data that your collaborators can use for audience creation and activation. This article contains everything you need to know about creating and managing your sources, including:

* [Source data requirements](#source-data-requirements)
* [Creating sources](#create-a-source)
* [Managing your sources](#manage-your-sources)

## Source data requirements

It's recommended to <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion">prepare your source data</Anchor> to maximize match rates between collaborator datasets and optimize collaboration outcomes. In addition, all sources **must meet the following requirements**.

<Accordion title="Data format (relevant to all sources)">

Data within sources must meet these requirements:

* **Date** (only): yyyy-mm-dd (for example, `2023-04-18`)
* **Date and time:**
  * **Format:** yyyy-MMM-dd hh:mm:ss (*for example*, `2023-APR-18 15:30:35`)
  * **Time zone:** UTC
* **Numbers:** maximum 2 digits following the decimal point
* **String length:** maximum of 256 characters
* **Character limitations:**
  * **For field names (column headers):** no spaces or special characters
  * **All other data:** no limitations (all characters are valid)

</Accordion>

<Accordion title="Table columns (relevant only to sources in data warehouses)">

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

<Accordion title="File name and format (relevant only to sources in cloud storage buckets)">

Source files stored in Amazon S3 or GCS must meet these file name and format requirements:

* File name must comply with <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR naming requirements</Anchor>
* CSV or GZIP format
  * The file underlying GZIP compression must be a CSV file.
* Number of data source files per <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-add-connections#snowflake-outbound">data folder</Anchor>:
  * **CSV:** Maximum of 1
  * **GZIP:** Maximum of 1 single-part file. Multi-part GZIP files are supported when named as follows: `filename_part01.csv.gz`, `filename_part02.csv.gz`, etc.

</Accordion>

## Create a source

**Prerequisite:** Before creating your source, <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">set up the cloud services</Anchor> that AppsFlyer DCP will use to retrieve your source data. If these connections aren't set up, you'll be prompted to do so during source creation.

**To create a source in DCP, follow the steps below:**

<Accordion title="Step 1: Access DCP Sources">

1. In AppsFlyer, from the side menu, select **Collaborate** > **Data Clean Room**.

   <Image alt="Click Data Clean Room.png" src="https://files.readme.io/b65f88e8dd771c33345049ae35a512e75dfd820c40c169a2b536c433df141e8e-43750175599889.png" width="644px" />
2. Click **+ New source** (on the main page or in the **Sources** tab).

   <Image alt="sources empty state cropped.png" src="https://files.readme.io/629d8c7c68bfbce7c2307306128b0d0cc430886dc2a58200cb635bc0044d2bd7-33193030142609.png" width="482px" />
3. Proceed with the **New source** walkthrough steps:

</Accordion>

<Accordion title="Step 2: Set source name">

Enter the source name. This can be any unique name that will help you identify the source. You can also add an optional description about the source to help easily identify what it contains (e.g., "All purchases from 2025").

#### Requirements and guidelines

* Make sure the **source name** is unique among all other sources in your account. Otherwise, you won't be able to save the source.
* For cloud integrations, the name doesn't need to match the file name.
* Source name requirements:
  * Length: 2-80 characters
  * Valid characters:
    * letters `(A-Z, a-z)`
    * numbers `(0-9)`, *cannot be the first character of a name;*
    * Underscore `"_"`
  * Invalid characters:
    * spaces
    * all other symbols or special characters

</Accordion>

<Accordion title="Step 3: Set source location">

**To specify the source location:**

1. Select the <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#overview">connection</Anchor> in which the source will be (or has been) created.
   * If there are no connections defined in your account, the **New connection** dialog will open, prompting you to create one. Follow <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-add-connections">these instructions</Anchor> to create it.
   * If you have existing connections but want to use a new one, click **+ New connection** and follow <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-connections">these instructions</Anchor> to create it.
2. Continue with the relevant instructions below, based on where the data for your source is located.

**Note:** For best performance when there’s a large amount of data, a subset of your data may be stored separately. This data will be updated whenever the source is updated and deleted when the source is deleted.

#### Source locations in BigQuery

**To complete specifying the source location for BigQuery sources:**

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

Source locations in Amazon S3 or GCS consist of the cloud storage bucket specified by the connection and the underlying folder path from which the DCR reads the source file each time it is updated.

Once you have specified the connection, AppsFlyer can automatically generate the required underlying folder path as part of the source creation process.

* Allowing AppsFlyer to generate the folders makes the process easy. However, you can choose to manually create them instead, according to the instructions <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">detailed here</Anchor>.

If AppsFlyer generates the folders, the only additional information required is the name you want to give the **source folder.** (This is the top-level folder in which you update the source each time your want to use it for running a new report version.) You can also indicate whether you want the source folder to be created underneath a parent folder – often named **input.**

**To complete specifying a source location in a cloud storage bucket, enter the source folder name.**

* By default, the displayed source folder name:
  * Is based on the [name you gave the source](#h_01K1ZHNZEQWRP7ZBK7XJP5F9HA). You can change the folder name to meet your needs, so long as it complies with the <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR naming requirements</Anchor>.
  * Indicates that it will be generated within a parent folder named **input.** This folder serves as the parent folder for all sources you upload to the DCR.
    * The **input** folder is not required, and you can remove it or name it something different, so long as it complies with the <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR naming requirements</Anchor>.
    * Although this folder is not required, having an **input** folder (or an equivalent folder of a different name) is considered best practice. It is even more highly recommended when you are using the same cloud storage bucket both for uploading data files (input) and receiving reports (output).

> 🚧 **Important!**
>
> If you manually created the folder path, make sure the connection and path you enter in the **Source location** section match the path you manually created.


#### Source location as local files

You can also upload source data using a local file. However, **It’s strongly recommended to set a cloud service as your source location** (crucial for larger data sets and automatic updates). A local file is primarily used for testing purposes and getting familiar with the platform functionalities.

**To upload source data using a local file:**

When selecting your source location, click on **Local file system** and **Next**, which adds the option to upload local files from your device.

<Image alt="Select Local file system.png" src="https://files.readme.io/08f4797196c915b73a543c7152b5090913287c61b12fefe893d3893ca76fc4d5-33193021989393.png" width="731px" />

> 📘 **Note**
>
> * Supported file types: .CSV and .GZ files (max size 5 GB).
> * Data uploaded from a local file will be saved for 180 days.
> * Updates must be performed manually.

</Accordion>

<Accordion title="Step 4. Set source update method">

When setting up a source in the Data Collaboration Platform (DCP), you must choose how you'd like updates to that source to be handled. DCP supports two sync methods: **Snapshot** and **Append**. Each method suits different use cases and data flows:

* **Snapshot** - This method uploads the full dataset each time the source is updated, completely replacing the old dataset each time with the new one. Choose this method only if your file uploads always contain the complete and up-to-date dataset.
* **Append** - This method uploads only new or changed data, not the full dataset. Old datasets are not removed or updated. It is ideal for recurring uploads like daily or weekly reports. Benefits include smaller uploads (may drive lower cloud storage costs), faster data upload performance, easier record management, and more.

<Image alt="Delta Generate folders.png" src="https://files.readme.io/105f55ff555565e97b82ecf86d58cfd2cf2a0340f83d6261fd3bd1c084b13889-38096875288977.png" width="637px" />

> 🚧 **Important!**
>
> Please determine which method is best before selecting. Once an option is selected and **Generate folders** is clicked, a file path along with instructions for handling data uploads is created within your selected cloud service. To prevent folder duplications and errors, you can **change the sync method only once** after the initial selection.


#### Snapshot upload requirements

Use this method to upload a complete, self-contained file that fully replaces the prior dataset each time the source is updated.

<span id="h_01K2A7MAWT05K506384QHYA0FN"></span>**Supported cloud services**

* Amazon S3
* Google Cloud Storage (GCS)
* BigQuery
* Snowflake

**<span id="h_01K2A7MAWTCYF3VAWJRRRJFNN5"></span>Follow these guidelines for the Snapshot update method:**

1. **Source folder path**

   When you register a cloud‑storage source in DCP, a root path (e.g. `input/my_source_folder/`) is defined for that source. Each time you refresh the dataset, you upload a **full snapshot**—a file that contains all current rows—to this folder. This guarantees that DCP always processes the most up‑to‑date and complete view of the data.
2. <span id="h_01K2A7MAWTPJ621MGBBG40N8H4"></span>**Uploading full snapshot files**

| Guideline | Why it matters | How to comply |
| --- | --- | --- |
| **Complete dataset** | DCP must replace the prior state in full | Generate an export that includes every record, not just changes |
| **Date-partitioned folder (**`dt=`) | Enables date‑range filtering & retention management | Place each snapshot under `dt=YYYY‑MM‑DD/` |
| **Version sub‑folder (**`v=`) | Allows multiple snapshots on the same day | First upload under `v=1/`; retries use `v=2/`, `v=3/`, etc. |
| `data/` **sub-folder** | Organizes your files | Store Parquet / CSV / Avro files in this folder |
| `_SUCCESS` **marker** | Signals DCP ingestion to begin | Upload an empty file named `_SUCCESS` inside the `v=` folder after all data files land |
| **Supported file type and size** |  | <ul><li>Supported file types: .csv or .gz</li><li>Maximum file size: 5 GB</li></ul> |

> 🚧 **Important!**
>
> The full snapshot file (BI-data.csv in the screenshot below) must be placed under:
>
> ```
> /v=1/data/
> ```
>
> Then, once the data file is uploaded, place an empty `_SUCCESS` file in:
>
> ```
> /v=1/
> ```

**Folder anatomy:**

```
s3://af-dcr-xyz/abcd9876/input/source_name1/dt=2025-mm-dd/v=1/data/
└ bucket ┘ └ tenant ┘ └ingestion┘ └source┘└snapshot date┘└ver┘└files┘
```

| Segment | Description | Purpose |
| --- | --- | --- |
| `af-dcr-xyz` | S3 / GCS bucket | Top‑level container for all DCP data |
| `abcd9876/` | Tenant / workspace ID | Keeps each customer’s data isolated |
| `input/` | Ingestion area | Where raw uploads land before processing |
| `source_name1/` | Source name | Logical dataset registered in DCP |
| `dt=2025-mm-dd/` | Snapshot date | Represents the dataset’s full state on that day |
| `v=1/` | Version (optional) | Supports retries or additional snapshots |
| `data/` | Files | Parquet / CSV / Avro snapshot files |

<span id="h_01K2A7MAWTYFHBANCV9F2NKNCV"></span>**Example of a two-day snapshot structure:**

```
source_name1/
  dt=2025-08-10/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
  dt=2025-08-11/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
```

Example of how folder structure should look after uploading a complete snapshot of the source files for 2 days (and programmatically creating date/version/data folders and \_SUCCESS files), your bucket/folder structure might look something like this:

[<Image alt="Snapshot example bucket.png" src="https://files.readme.io/a96762b43bbcae3d1265aa407e725ba885e27c3a83433d017aa30d7afaf31e37-38096860329233.png" width="219px" />](https://files.readme.io/a96762b43bbcae3d1265aa407e725ba885e27c3a83433d017aa30d7afaf31e37-38096860329233.png)


#### Append upload requirements

Use this method to upload only the data that changed or was added since the previous upload.

Why use Append?

* **Efficiency** – smaller uploads
* **Data integrity** – preserves full change history for time‑series analysis
* **Privacy compliance** – simplifies record deletion & consent management

**Supported cloud services:** AWS S3 and Google Cloud Storage (GCS)  
**Note:** BigQuery and Snowflake are not supported or the Append method and must use the Snapshot method.

**Follow these guidelines for the Append update method:**

<span id="h_01K2A7MAWT8E6AX95VG86APXBB"></span>1. **Source folder setup**

| Step | Description |
| --- | --- |
| **Create / assign bucket** | Use an existing S3 / GCS bucket or let AppsFlyer provision one for you |
| **Define root path** | A tenant‑scoped path (e.g. `s3://af‑dcr‑xyz/abcd1234/`) is configured as the input directory |
| **Security** | Grant the service user write permission only on this path |

<span id="h_01K2A7MAWT86J2S65D99BC66PQ"></span>2. **Uploading append (delta) files**

| Guideline | Why it matters | How to comply |
| --- | --- | --- |
| **Upload cadence** | Keeps transfer cost & ops overhead low | Upload daily, or bundle 7-day folders and upload weekly |
| **One folder per day** | Enables date filtering & avoids scanning large batches | Place each day's delta in `dt=YYYY‑MM‑DD/` |
| **Unique file names** | Prevents accidental overwrites | Give files unique names modeled like this:`events_2025‑08‑04.parquet` `events_2025‑08‑05.parquet` |
| **Required columns** | Enables tracking of changes | The file must include:<ul><li>A date column to associate records with a reporting timeframe.<ul><li>A version column to track data revisions.</li></ul></li></ul>**Note:** Files missing these columns will result in a loading error in DCP. |

<span id="h_01K2A7MAWTV3FY1GZSXQFNX4JS"></span>**Folder anatomy:**

```
s3://af-dcr-xyz/abcd1234/input/source_name/dt=2025-08-10/
└ bucket ┘ └ tenant ┘ └ ingestion ┘ └ source ┘ └ day partition ┘
```

| Segment | Purpose |
| --- | --- |
| `af-dcr-xyz` | Customer’s S3/GCS bucket |
| `abcd1234/` | Tenant or workspace ID |
| `input/` | Raw uploads awaiting ingestion |
| `source_name/` | Logical DCP source (e.g., CRM\_Events) |
| `dt=2025-08-10/` | Daily partition folder |

<span id="h_01K2A7MAWTRSYFTTDKG4G0TPZR"></span>**Example weekly delta folder structure:**

```
source_name/
  dt=2025-08-04/
  dt=2025-08-05/
  dt=2025-08-06/
  dt=2025-08-07/
  dt=2025-08-08/
  dt=2025-08-09/
  dt=2025-08-10/
```

<span id="h_01K2A7MAWT5NDJQAYD16NRZSAQ"></span>**Rule‑of‑thumb cheat‑sheet:**

| Requirement | Why | Example |
| --- | --- | --- |
| **Weekly batch (optional)** | Fewer pushes, same granularity | Upload one batch containing seven sibling `dt=` folders |
| **Day partitions** | Speeds up queries & UI filters | `s3://your‑bucket/source/ dt=2025‑08‑04/ ... dt=2025‑08‑10/` |

**Key takeaway:** Even when uploading weekly, always organize data into day-specific `dt=YYYY‑MM‑DD` folders.

</Accordion>

<Accordion title="Step 5: Map source fields">

Map source fields to DCP fields, test it, and save the configured data:

1. [Load your source fields](#1-load-your-source-fields)
2. [Configure the source fields](#2-configure-the-source-fields)
3. [Verify EU user inclusion](#3-verify-eu-user-inclusion)
4. [Test the source data](#4-test-the-source-data)
5. [Save the source](#5-save-the-source)

#### 1. Load your  source fields

Source fields load automatically. In case manual loading is needed, follow the instructions below according to the source location:

**Data warehouse sources**

To load fields from a source located in a data warehouse (BigQuery or Snowflake), click **Load fields from source**.

> 🚧 **Important!**
>
> If the selected source table does not include the required [date and version columns](#h_01HPKB2ERPJ5PVQ2QM5XCYZE0D), you will receive an error.

**Cloud storage bucket sources**

To load fields from a source located in a cloud storage bucket (Amazon S3 or GCS), you must upload a prototype source file.

For purposes of mapping the source fields to DCP fields:

* You can upload a prototype version of the source from a local file.
  * If you select this option, AppsFlyer always creates the source folder path automatically.

                                                                - or -

* You can upload a prototype version of the source file directly from the connected cloud bucket.
  * If you select this option, there's one additional choice to make:
    * Allow AppsFlyer to automatically generate the cloud folder for the source file, or
    * [Create the cloud folder for the source file manually](#h_01HPKB2ERVZ88MJ35JC66YDPAB)

**To upload your prototype source file, follow the instructions in the relevant tab below:**

<Tabs>
<Tab title="Local file">

1. In the **Map source fields** section, click **Load fields from source**.
2. In the window that opens, select **Upload a local file.**
3. Specify the CSV or GZIP file you want to upload, then click OK.

</Tab>

<Tab title="Connection (automatic creation)">

**To load the file from the connected cloud bucket and allow AppsFlyer to generate the cloud folder for the source file:**

1. In the **Map source fields** section, click **Load fields from source**.
2. In the window that opens, select **Load from cloud bucket.**
3. Click the **Generate folders** link.
   * AppsFlyer automatically generates the required folder structure and cloud source folder (on the connection you specified, with the source folder name you specified).
4. After the source folder structure has been created, a confirmation message is displayed, including a link to the source folder. Click the provided link to upload your prototype file to the source folder.
5. Once the file has finished uploading, click **OK.**

</Tab>

<Tab title="Connection (manual creation)">

**To upload the source file from a structure you created manually:**

1. In the **Map source fields** section, click **Load fields from source**.
2. In the window that opens, select **Load from cloud bucket.**
3. **DO NOT** click **Generate folders.** Instead, upload the file directly to [the source folder you created for it](#h_01HPKB2ERVZ88MJ35JC66YDPAB).
4. Once the file has finished uploading, click **OK.**

</Tab>
</Tabs>

#### 2. Configure the source fields

After loading the source fields, each source field (column) is presented with a DCP field. Review each source field and map it to the appropriate DCP field from the drop-down list beside it. Consider the following:

> 📘 **Note**
>
> * When both parties share their source data, **at least one field must be set as an identifier** to enable user-level data to match across the corresponding sources. An identifier is a field that uniquely identifies an app user (for example, CUID, AppsFlyer ID, or hashed email).
> * Although configuring each of the uploaded source fields (columns) isn't mandatory, it is important for categorization, effective data interpretation, aiding audience creation, suggesting insights, and effectively facilitating validations.

#### AI-assisted field type detection

DCP can suggest a DCP field for each source column using AI, based on the column name.

**To turn on AI-assisted detection:**

1. In the **Map source fields** section, look for the banner: "Want help mapping the fields quickly? **Activate DCP AI Assistant**." Click **Activate DCP AI Assistant**.
2. Once your fields are loaded, click **Auto detect field types**. DCP evaluates each column name and suggests a DCP field for it.
3. Review each suggestion before saving. You can accept a suggestion as is, or change the mapping manually, the same way you'd edit any other field.

Each field lands in one of these states:

* **Mapped:** AI found a single confident match. Review it and accept, or change it manually.
* **Couldn't map:** AI couldn't determine a field. Map it manually, or leave it unmapped.

#### Limitations

* **Column limit:** AI detection supports up to 100 columns per source. Sources with more columns display a "limit exceeded" message.
* **Field name length:** column names over 100 characters aren't supported for AI detection.

> 🚧 **Important!**
>
> As with manually added fields, if an AI-suggested mapping uses a [List of... type](#important-5), the source file must be uploaded or connected as Parquet. CSV and GZIP files don't support array-typed columns.

**To remove a field:**

* Hover over the right side of the field you want to remove and click the dustbin icon that appears when hovering.

**To add fields manually:**

This option allows you to include a field in the audience that isn't currently present in the data source.

1. Click **+ New field**. An empty field is added.
2. Enter the name of the field and select its type.

<Image alt="NewField.png" src="https://files.readme.io/8dfb70dcac2cc9a2257c6e092bc2185de74a3804bd608878eaaadf09cd903331-43749881081745.png" width="760px" />

**Field types include:**

* [**Identifier**](#identifier-vs-list-of-identifiers)
  * Android ID
  * AppsFlyer ID
  * CUID
  * Email
  * Hashed email
  * Hashed email (no dots)
  * IDFA
  * IP address
  * ID5 Id
  * MediaMath Id
  * Mobile Ad Id
  * Phone number
  * Hashed phone (no plus)
  * Platform ID
  * SHA256 hashed ID
  * SHA256 phone number
  * ZIP+5 code
  * ZIP+4 code
  * LUID
  * Person ID
* [**List of identifiers**](#identifier-vs-list-of-identifiers)
  * Hashed emails (no dots)
  * Hashed phones (no plus)
  * Hashed emails
  * Hashed phones
  * Emails
  * Phones
  * ID5 Ids
  * MediaMath Ids
  * Mobile Ad Ids
  * IDFAs
  * Android IDs
  * IP addresses
* Booolean
* Date and Time
  * Date time
  * Date
* DMA
  * Ad personalization enabled
  * Ad user data enabled
  * EU DMA Applies
* Number
  * Double
  * List of Numbers
  * Long
  * Number
* Text
  * Text
  * App Id
  * List of Text

#### **Identifier vs. List of identifiers:**

Identifier types hold a single value per row (for example, one email or one CUID per row). List of identifiers types hold an array of values per row (for example, a single row can contain multiple hashed emails or device IDs) — use this when a source needs to match on more than one identifier per record.

> 🚧 **Important!**
>
> If a source includes any field mapped to a **List of...** type (List of identifiers, List of Numbers, or List of Text), the source file must be uploaded or connected as Parquet. CSV and GZ files don't support array-typed columns, so list fields may not be ingested correctly from those formats.

#### Reload source fields

If the configuration of one of your data files has changed, you can update the source file to reflect the changes.

> 📘 **Note**
>
> Reloading the source resets the column names in the source to match the updated file names. This will overwrite any of the field names in the list and their type.

**To reload updated fields from a file:**

1. Click **Reload fields**.
2. Select the file location.
   * For a local file: Upload the file.
   * For a file from your cloud service: Click **Load from cloud bucket** and follow the instructions.
3. Click **OK**. The updated files are now displayed.

#### 3. Verify EU user inclusion

* Select **Yes** or **No** to the question: **Does your source include European users, to which EU DMA regulations apply?**

Learn more about privacy regulations for the EU Digital Markets Act.

#### 4. Test the source data

* [Optional] Click **Test** to check for errors in the format or validity of the source fields.

#### 5. Save the source

* Click **Save** to save the source.

After confirming, the new source is added under the **Sources** tab.

> 📘 **Note**
>
> If you uploaded the source from a local file, saving the source triggers the automatic creation of the folder structure, and the displayed confirmation message includes a link to the source folder.

</Accordion>

## Manage your sources

The sources you've created are displayed in the **Sources** tab. From here, you can edit the source name and structure, share it with a collaborator, and delete it—provided it's not already being used in an audience.

<Accordion title="Edit a source">

1. Go to the **Sources** tab of the **Data Clean Room**.
2. In the list of sources, hover over the source you want to edit, and click the edit icon ![edit_button.png](https://files.readme.io/987296a8252ca09524a826bcd3e06995b17e5ca646672958d803572cecabbf10-24740010658449.png) at the end of the row.
3. On the **Edit source** page, edit the relevant fields, as detailed below.
4. Click **Save.**

#### Edit the source name

When editing the source name, make sure to [follow these naming requirements](#requirements-and-guidelines).

#### Edit the source location

1. From the **Edit source** page > **Source location**, select a different data connection.
2. Select the relevant location details.
3. [Optional] [Test the source](#4-test-the-source-data).
4. Click **Save.**

#### Edit the field mapping

1. Go to the field mapping, and make the necessary changes: Change the field or update its mapped DCP field.
2. Click **Save**.

> 🚧 **Important!**
>
> Don't forget to make corresponding changes reflecting the new source structure in any reports for which this source is used:
>
> * Fields that were removed, unmapped, or changed from their previous mapping are automatically removed from any reports in which they are used.
> * Newly added or mapped fields are not automatically included in existing reports until you edit report definitions to include them.

</Accordion>

<Accordion title="Delete a source">

You can delete any source except when it's being used in an audience. If this is the case, a notification will specify the audiences using that source. To enable the deletion of the source, you must first delete the audience linked to it. As for sources shared with you, they can only be deleted by the source owner.

1. Go to the **Sources** tab of the **Data Clean Room.**
2. In the list of sources, hover over the row of the source you want to delete.
3. Click the delete icon ![delete_button.png](https://files.readme.io/10fbd4d4f09ddb56823a2824629f8bb9362b34c95038b3d9e747ffcde7b30381-24740010666129.png) showing on the right side of the row.
4. In the dialog, click **Delete** to confirm.

</Accordion>

## Sharing permissions

Granting permissions to your collaborators to view and use your source data is done when <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-create-a-collaboration">creating collaborations</Anchor>. Learn more about <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-sharing-permissions">sharing permissions</Anchor>.

## Additional information

This section provides some additional references and useful information.

<Accordion title="Manually create a storage bucket folder structure (Optional)">

In general, it's easiest to allow AppsFlyer to automatically generate the required folder structure as part of the source creation process. However, if you wish to create these folders manually, you can do so as follows.

#### Create a DCR key folder

To ensure maximum security, the folder directly beneath the bucket (the "DCR key folder") must be named with the 8-character, alphanumeric **DCR key** assigned to your account (for example, `01bcc5fb`). *Note that this is different from any other password or key associated with your AppsFlyer account.*

The DCR key folder is generally created manually using the interface of your selected cloud service.

**To get your account's DCR key:**

* Click the 3-dot (actions) menu on the upper right and select **DCR key**.

[<Image alt="DCR key.png" src="https://files.readme.io/b892831ad68cffb5b8084949d759f402780536c7176aa27733c867aff6560684-43750165616657.png" width="1141px" />](https://files.readme.io/3a15c67e4683e9d6c748cfb3fe7d95be9fa44e47d82a7615abadb90575f1fce1-24740007159825.png)

After creating the DCR key folder, your bucket/folder structure would look something like this:

<Image alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/ba5902f70e75dc6fa1a6970f28397607c42bd433add4be311f4b498a3960ce05-24740007165841.png" width="308px" />

#### Top-level input folder

Though it is not required, best practice is to create a top-level input folder directly beneath the DCR key folder. This folder will be dedicated to files you upload to the DCR.

The top-level input folder is generally created manually using the interface of your selected cloud service.

* This practice is even more highly recommended when you are using the same bucket both for uploading data files (input) and receiving reports (output).
* You can name this folder anything you want, so long as it complies with the <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR naming requirements</Anchor>. For ease of identification, it is usually named `input/`.

After creating the top-level input folder, your bucket/folder structure might look something like this:

<Image alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/2d0fef29b00e9ac8bb9ee5fa281a9a502d0395c72d8879370271e1e4a1af9c95-24740010678801.png" width="308px" />

#### Second-level folder for each data source

You can regularly upload different data source files to the DCR for processing. Each of these data sources must be assigned a separate folder ("data source folders").

So, for example, if you plan to upload 2 files to the DCR for processing every day: *BI-data.csv* and *CRM-data.gzip*, you would assign each of these data sources a folder. You could choose to call these folders `BI-data/` and `CRM-data/`.

The data source folders are generally created manually using the interface of your selected cloud service.

After creating 2 data source folders, your bucket/folder structure might look something like this:

<Image alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/c9feab81da8507ce96c61bd19b70a53bb6e4914cbab67fbcd0de8b578b04f29a-24740007171473.png" width="307px" />

Under each data source folder, [nested subfolders by date and version](#nested-subfolders-for-each-date-and-version) must be created each time the source is updated.

</Accordion>

## Privacy regulations

This section outlines important information about current privacy regulations.

<Accordion title="Understanding Google's EU user consent policy and its implications">

As part of Google’s enforcement of the Digital Markets Act (DMA) Google updated its EU user consent policy as of March 6, 2024. As a Google App Attribution Partner, AppsFlyer made the necessary changes to support their policy requirements, while ensuring that advertisers maximize the value from their Google Ads marketing channels.

> 📘 **Note**
>
> * Google’s enforcement of the Digital Markets Act (DMA) applies to all platforms.
> * Read more about this:
>   * <Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">Insights and resources about the Digital Marketers Act</Anchor>
>   * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">Google’s FAQ</Anchor>

#### Adding consent fields

When setting up a source intended for audience activation on Google and confirming **Yes** to the question **Does your source involve European users subject to EU DMA regulations?** ensure that the additional consent fields in the table below are included in the source file. This enables AppsFlyer to transfer the necessary information to Google during the activation process.

**Additional consent fields and their response values:**

<table><thead><tr><th>Field name</th><th>Response value</th><th>Field explained</th></tr></thead><tbody><tr><td><span id="eea"></span><code>eea</code></td><td>true/false</td><td>Is the user located in the EEA (European Economic Area), to which the DMA applies?</td></tr><tr><td><span id="ad_personalization"></span><code>ad_personalization</code></td><td>\*true/false</td><td>Did the user give Google consent to use their data for personalized advertising?</td></tr><tr><td><span id="ad_user_data"></span><code>ad_user_data</code></td><td>\*true/false</td><td>Did the user give consent to send their user data to Google? </td></tr><tr><td colspan="3"><span id="when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them"></span>\* When “<strong>true</strong>”, AppsFlyer includes the user identifiers you've sent for users who gave consent.<br/>   When “<strong>false</strong>”: AppsFlyer doesn't include them, as they weren't sent to AppsFlyer.</td></tr></tbody></table>

#### Potential impact on the audience size

The actual and estimated audience size sent to Google may vary based on the number of users granting or denying consent.

</Accordion>

<div data-zendesk-anchors="introduction=about-dcp-sources h_01HPKB2ERNRQG73AFA0X7XEDEF=about-dcp-sources source-format=source-data-requirements h_01HPKB2ERPANE0CAXFP9RG5YEH=source-data-requirements creating-a-source=create-a-source h_01HPKB2ERPX2T413N3T93YBBZB=create-a-source h_01K1ZHNZEQ3NSN3V7NQ34G8VC8=requirements-and-guidelines 01HX49VY7D8KG5DCB82BP69BXV=source-locations-in-bigquery 01HX49VY7DXH5YN8FF0NFAJBC2=source-locations-in-snowflake 01HX49VY7D3CSF4SQ79Q7CZKWX=source-locations-in-cloud-storage-buckets 01HX49VY7D307DT5VTMGHPF3WA=important local-file-system=source-location-as-local-files h_01HX4SKEGE9NVCA6VYSR77S2DK=source-location-as-local-files h_01K1FW3AW2AW4TPDS0ZGPQCMX3=source-location-as-local-files h_01HX4T0H6SFQJEWFETKFD1CY6S=note h_01K29ETW94GQM9YYF5A4Y6DKB6=important-1 overwrite-method-specifications=snapshot-upload-requirements h_01K1G33RX95KP9TJ4002DDJBCE=snapshot-upload-requirements h_01K2A7MAWS5KR16QV0Y8AE39GW=snapshot-upload-requirements h_01K2CC62XGAVTD5JH5DYXP0947=important-2 data-title=append-upload-requirements append-delta-upload-requirements=append-upload-requirements h_01K2A7MAWT7CRHY1TV5J41MM0D=append-upload-requirements h_01K2C6QNJSAH9D3M48T02JHQ3R=append-upload-requirements load-the-source-fields=1-load-your-source-fields h_01HPKB2ERQTJPGG68FSEBHVVJA=1-load-your-source-fields h_01HPKB2ERRZNPYVVD8GHD7PBPE=important-3 configure-the-source-fields=2-configure-the-source-fields h_01HX64YHGHMK352E3RXHBFV0B5=2-configure-the-source-fields 01HX6HVZ6DK2WH71JVB0J9WPBF=note-1 h_01K5AI0D3TFIELDTYPEDETECT=ai-assisted-field-type-detection h_01K5AI0D3TLIMITATIONS=limitations h_01K5AI0D3TIMPORTANT=important-4 h_01KYSMJKRA2E13PH2QS671BSKG=identifier-vs-list-of-identifiers h_01KYSJNEWS5QY5Q13Z11TNJHX1=important-5 h_01HX6TDNEMJFQM5FA95Y3C1QHD=reload-source-fields h_01HX6WF7YC014Z7ZX359RB5ZRZ=note-2 verify-eu-user-inclusion=3-verify-eu-user-inclusion 01HZKZ2T33TYCQ8J59YGDYN7DK=3-verify-eu-user-inclusion test-the-source-data=4-test-the-source-data h_01HX6WGD421PCWEWTN5YJ7V42H=4-test-the-source-data save-the-source=5-save-the-source h_01HYX92EXSJNM5B2PDXEAEBNFS=5-save-the-source h_01HYXC06K3ZWQE867NKBT95RFH=note-3 working-with-existing-sources=manage-your-sources h_01HPKB2ERS5PK2P2XTC4ZMPCMC=manage-your-sources 01J1SMACQHFEVAR8ZC6W8T0BAV=edit-the-source-name h_01J1SM789AFJBSD0NG826P98Q4=edit-the-source-location edit-the-source-structure=edit-the-field-mapping h_01J1SNB66WQMBV1GQE4PDQ0NW4=edit-the-field-mapping h_01HPKB2ERTYP6BFAESN3MHZSQG=important-6 permissions=sharing-permissions h_01HZHBDPZ8FFQCB9DZ2Q8XSC2R=sharing-permissions reference=additional-information h_01HPKB2ERV1KK3J8YX918GCF3M=additional-information creating-a-dcr-key-folder=create-a-dcr-key-folder h_01HPKB2ERV7MQJ9CK44T92GK2G=create-a-dcr-key-folder toplevel-input-folder=top-level-input-folder h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=top-level-input-folder secondlevel-folder-for-each-data-source=second-level-folder-for-each-data-source h_01HPKB2ERVVFMP81RE8ATZ6SZ8=second-level-folder-for-each-data-source privacy-regulations-eu-digital-markets-act=privacy-regulations h_01HZHBF0NZDTXAA3MY1A0BPE5E=privacy-regulations h_01HZM4EFRJD483NARKDPPPPXCY=note-4 h_01HZHBF0NZSDGDYG2ZWNW4KQYD=adding-consent-fields -when-%E2%80%9Ctrue%E2%80%9D-appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google%C2%A0-when-%E2%80%9Cfalse%E2%80%9D-appsflyer-abstains-from-sending-them=when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them h_01HZHBF0NZJBSXNBDFZH4YKNSH=potential-impact-on-the-audience-size" />

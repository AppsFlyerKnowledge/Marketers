---
title: Data Collaboration Platform (DCP) - Add connections
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-04-28T13:26:59Z'
  edited_at: '2026-07-27T13:03:23Z'
  id: 24603890457617
  locale: en-us
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/24603890457617-Data-Collaboration-Platform-DCP-Add-connections
---
> **At a glance:** Set up DCP connections to connect your data sources, enrich your data, and export audiences to cloud storage and media partners.

## About DCP connections

Connections determine how DCP ingests your data and exports your audiences. After <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">setting up your cloud services</Anchor>, connect them to DCP using the **Manage connections** modal. The following connection types are available:

* [**Source connections**](#create-source-connections): for ingesting your first-party data into DCP from cloud storage or a data warehouse.
* [**Cloud storage connections**](#create-cloud-storage-connections): for exporting your audiences to your Amazon S3 or Google Cloud Storage (GCS) buckets.
* [**Media partner connections**](#create-media-partner-connections): for sending your audiences to advertising platforms for activation.
* [**Data & Identity connections**](#create-data-identity-connections): for unifying fragmented user data to improve match rates and expand partner-side audiences.

DCP supports different cloud services for different connection directions. Use the table below to see which services you can use for each connection type:

| Cloud service | Source (inbound) | Cloud storage export (outbound) |
| --- | --- | --- |
| Amazon S3 | ✓ | ✓ |
| Google Cloud Storage (GCS) | ✓ | ✓ |
| BigQuery | ✓ | - |
| Snowflake | ✓ | - |
| Salesforce Cloud/CRM | ✓ | - |

For Amazon S3 and Google Cloud Storage, a single connection serves as both a source (inbound) and a cloud storage export (outbound) destination. Creating a source connection to S3 or GCS automatically creates a matching cloud storage (export) connection, and vice versa.

<div id="create-source-connections" />

<Accordion title="Create source connections">

Create source connections to bring first-party data into DCP.

**To create a source connection:**

1. In AppsFlyer, go to **Collaborate** > **Data Clean Room**.
2. Click **Manage connections** in the top-right corner.
3. Go to the **Source** tab and click **+ New connection**.  
   <Image align="center" alt="2026-07-27_13-30-46.png" src="https://files.readme.io/dec879432c0b9d6ba4eeec2c175dfce145c99652ccabb02d37f3434627f9310f-49189748198289.png" width="529px" />
4. Continue with the [Cloud service connections for source data instructions](#cloud-service-connections-for-source-data) below.

You can also create a source connection directly when setting up a source. See <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-create-and-manage-sources">Create and manage sources</Anchor> for instructions.

> 📘 **Note**
>
> Creating an incoming Source connection to Amazon S3 or GCS automatically creates a matching outgoing Cloud storage connection (and vice versa). Deleting Amazon S3 or GCS connection also automatically deletes the other. Since it's really one underlying connection, removing it from either tab removes it everywhere it's used.

#### Cloud service connections for source data

Source connections are for connecting your data sources securely to DCP. From the **New connection** dialog, select your cloud service and complete the details for your provider:

**BigQuery:** In the **New connection** dialog, enter the BigQuery **project ID** for the project that contains your source data. You can find this on the BigQuery page of your Google Cloud Console.

**Snowflake:** In the **New connection** dialog, enter the **Snowflake account ID** and **region** for the account that contains your source data. To find this, click the account name at the bottom-left of your Snowflake console:

**ACCOUNTADMIN** > **Account** > hover over the relevant account > **Copy account identifier**. See the <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/admin-account-identifier#finding-the-organization-and-account-name-for-an-account">Snowflake documentation</Anchor> for details.

> 🚧 **Important!**
>
> Look for the ID labeled **Locator**. This is **not** the same ID used to create outbound Snowflake connections.

**Amazon S3 and GCS:** In the **New connection** dialog, enter the name of the <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#cloud-storage-buckets-inbound">bucket you created</Anchor> for the exclusive use of the AppsFlyer Data Clean Room (DCR).

**Salesforce Cloud/CRM:** See <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-integration-with-salesforce-data-cloud">how to set up a Salesforce connection</Anchor>.

#### Local file connection

Local file system connections let you upload data files directly from your computer into DCP. This option is typically used for testing only and isn't recommended for ongoing or large-scale data ingestion.

<div id="set-up-a-local-file-connection" />

<Accordion title="Set up a local file connection">

A local file connection is used to test the platform using a sample file. It lets you get familiar with DCP functionality before starting to share data. Keep in mind that it isn't recommended for sharing data, has a data retention limit of 14 days, and doesn't support automation processes.

A local file connection can be <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-location-as-local-files">set up during source creation</Anchor>.

</Accordion>

</Accordion>

<div id="create-cloud-storage-connections" />

<Accordion title="Create cloud storage connections">

Cloud storage connections let you automatically export your DCP audiences to your Amazon S3 or Google Cloud Storage (GCS) bucket after each audience update.

**To create a cloud storage connection:**

1. In AppsFlyer, go to **Collaborate** > **Data Clean Room**.
2. Click **Manage connections** in the top-right corner.
3. Go to the **Cloud storage** tab and click **+ New connection**.  
   <Image align="center" alt="2026-07-27_13-30-34.png" src="https://files.readme.io/1da10127617317d0ff466433c89712d78c104b6a943b4b669e1d7180d22df958-49189843742609.png" width="533px" />
4. The **New cloud storage connection** modal opens.
5. In the **New cloud storage connection** modal, select your cloud provider: **Google Cloud Storage** or **Amazon Simple Storage**.
6. Enter your bucket name:
   * **GCS:** Enter the GCS bucket name in the format `gs://my-bucket`.
   * **S3:** Enter the S3 bucket name.
7. Click **Test connection** to verify that DCP can connect to your bucket.
8. Click **Save**. The new connection appears under **Your cloud storage connections** in the **Cloud storage** tab.

You can also create a cloud storage connection directly from the audience builder. See <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-build-and-activate-audiences">Build and activate audiences</Anchor> for instructions.

<div id="understand-export-path" />

<Accordion title="Understand the export path">

Each time an audience is exported, DCP writes it to your bucket using a fixed, predictable path:

```
<bucket>/dcp-output/audiences/<collaboration-id>/t=<audience_name>_<id>/dt=<YYYY-MM-DD>/v=<version>/<file>.csv
```

**Example folder contents for one delivery:**

```
s3://af-dcr-example-bucket/dcp-output/audiences/8f3a1c02-44b1-4e9a-9c7d-2b6e1a0f5d3e/t=example_audience_6148a3/dt=2026-07-18/v=1/
  ├── part-00000-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv
  ├── part-00001-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv
  └── _SUCCESS
```

| Path segment | What it means |
| --- | --- |
| &lt;bucket> | Your connected S3 or GCS bucket. |
| dcp-output/audiences/ | Fixed folder that DCP creates automatically for all audience exports. |
| &lt;collaboration-id> | The unique ID of the collaboration this audience belongs to. You can find it in the collaboration's URL in DCP. |
| t=&lt;audience\_name>\_&lt;id> | The audience name (spaces and special characters replaced with underscores), plus a unique ID. This ensures a deleted-and-recreated audience with the same name never overwrites or collides with older files. |
| dt=&lt;YYYY-MM-DD> | The delivery date. |
| v=&lt;version> | A version number for this audience's exports. It increases with each new delivery. |
| part-NNNNN-&lt;job-id>-c000.csv | One of the output files for this delivery — see File format and splitting below. |
| \_SUCCESS | An empty marker file written once the export finishes writing all part files. |

> 📘 **Note**
>
> This folder structure is created and managed automatically. Don't rename or restructure it manually — any automated process reading these files should be built to follow this path pattern, and should wait for \_SUCCESS to appear before processing the part files, to avoid reading a partial delivery.

**File format and splitting**

* Audiences are always exported as CSV files, uncompressed, with two columns: `value` (the identifier) and `taxonomy` (the identifier type).
* Larger audiences may be delivered as multiple files rather than a single file, numbered `part-00000`, `part-00001`, and so on. By default, each file contains up to approximately 500,000 rows.
* A single file can contain a mix of identifier types in the same rows — filter using the `taxonomy` column for the identifiers you need. Common taxonomy values include `customer_id`, `mobile_ad_id`, `hashed_email`, and `hashed_phone_number_without_plus_sha256`.

**Example:**

```
value,taxonomy
6f1a2b3c4d5e6f7a8b9c0d1e2f3a4b5c,customer_id
1a2b3c4d-5e6f-4a7b-8c9d-0e1f2a3b4c5d,mobile_ad_id
b7e2c9a1f4d6e8b0a2c4d6e8f0a1b3c5d7e9f1a3b5c7d9e0f2a4b6c8d0e2f4a6,hashed_email
c1d3e5f7a9b1c3d5e7f9a1b3c5d7e9f1a3b5c7d9e1f3a5b7c9d1e3f5a7b9c1d3,hashed_phone_number_without_plus_sha256
```

</Accordion>

</Accordion>

<div id="create-media-partner-connections" />

<Accordion title="Create media partner connections">

Outbound media partner connections let you securely connect your DCP audiences to supported media partners, so you can activate tailored campaigns on their platforms. Media partners are the main destination for audience activation. Learn how to <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-media-partner-connections">set up specific media partner connections</Anchor>.

**To create a media partner connection:**

1. In AppsFlyer, go to **Collaborate** > **Data Clean Room**.
2. Click **Manage connections** in the top-right corner.
3. Go to the **Media partners** tab and click **+ New connection**. If you already have existing connections, you'll see them listed under **Media partners**.
4. From the **New media partner connection** dialog, select the relevant media partner.
5. Enter a connection name.
6. Log in to the media partner account with your credentials and follow their instructions to enable AppsFlyer access.
7. Click **Select account ID** and select the relevant account for this connection.
8. Click **Save**. The new connection is added to the list of partners.

You can also create a media partner connection directly from the audience builder. See <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-build-and-activate-audiences">Build and activate audiences</Anchor> for instructions.

</Accordion>

<div id="create-data-identity-connections" />

<Accordion title="Create Data & Identity connections">

Data & Identity connections unify fragmented user data to improve match rates with activation partners. This enables larger partner-side audiences and more impact from your campaigns.

#### ID5

<Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-enrich-sources-with-id5">Enrich your first-party data with ID5 identifiers</Anchor> to unify fragmented user data, improve match rates with activation partners, and increase partner-side audience size.

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">DCP - Set up your cloud services</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-build-and-activate-audiences">DCP - Build and activate audiences</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-media-partner-connections">DCP - Media partner connections</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-enrich-sources-with-id5">DCP - Enrich sources with ID5</Anchor>
> * <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-guide">Data Collaboration Platform (DCP) guide</Anchor>

</Accordion>

<div data-zendesk-anchors="h_01KXX80P91T92MH8KEGHVG3QP1=about-dcp-connections h_01KXX80P913HRREW60M6S316PP=create-source-connections h_01KY4HCGBBCD5FZD9RYNNVDYRC=note source-cloud-service-connections=cloud-service-connections-for-source-data h_01KXX80P914VFMH1T6FQF9KC31=important h_01KXX80P91EFCGH3MYV729TGTH=local-file-connection h_01KXX80P91HG17YTWE15ZWTBZ8=set-up-a-local-file-connection h_01KXX80P91F8TG9FR1XQ7QVNCY=create-cloud-storage-connections h_01KYEP2MX3KQ3BAP7VRSGYTFBB=understand-export-path h_01KYEP2MX3SHFCECTSTHV9RMS4=note-1 h_01KXX80P91BMB45ETZQSKWJWZB=create-media-partner-connections h_01KXX80P91PS35EG5P5YJB9EHC=create-data-identity-connections h_01KXX80P92BXD3B7ZVT1FC5HCF=id5 h_01KXX80P92WMPPRGD7321TBS7Y=see-also" />

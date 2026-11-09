---
title: Data Collaboration Platform (DCP) - Build and activate audiences
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
  created_at: '2024-04-25T12:55:13Z'
  edited_at: '2026-07-28T11:30:35Z'
  id: 24522739719057
  locale: en-us
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/24522739719057-Data-Collaboration-Platform-DCP-Build-and-activate-audiences
---
> **At a glance:** Build high-value audiences in DCP collaborations using shared data and activate them on media partner sites or cloud services for maximum campaign impact.

## About DCP audiences

Build audiences in a DCP collaboration by combining datasets to create enriched audience segments and reach specific consumer groups. Audiences can be based on one collaborator's data or on intersecting users across both collaborators' datasets, based on the permissions defined by the data source owner. After an audience is built, it can be sent to media partners for activation or to a cloud storage bucket.

## Build an audience

The following tools are available for building your audiences:

* [Visual audience builder](/docs/data-collaboration-platform-dcp-build-and-activate-audiences#visual-audience-builder) - The visual audience builder is a user-friendly tool that allows non-technical users to create audience segments without needing SQL skills. It allows for advanced audience segmentation using a graphical interface.
* [SQL audience builder](#sql-audience-builder) (requires SQL expertise) - An SQL query that allows querying the data without restrictions. Requires SQL expertise.

#### Key features

| Visual audience builder | SQL audience builder |
| --- | --- |
| <span id="supports-using-one-source-from-each-collaborating-party"></span>Supports using either one source from each collaborating party or multiple sources from one collaborator | Supports multiple sources from both parties |
| <span id="supports-using-overlapping-data-only"></span>For one source for each collaborator, supports using overlapping data only | Supports querying all the data |
| <span id="supports-retrieving-values-within-the-selected-attribute-range"></span>Supports retrieving values within the selected attribute range. | Supports querying values beyond the attribute range |

Learn how to <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion">prepare source data</Anchor> to maximize match rates between collaborator datasets.

<div id="visual-audience-builder" />

<Accordion title="Visual audience builder">

**Follow the steps below to build your audiences using the Visual Audience Builder:**

> 📘 **Note**
>
> Make sure you have the Build audiences <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-sharing-permissions">permission</Anchor> to create an audience.

1. In AppsFlyer, from the side menu, select **Collaborate** > **Data Clean Room**.

   <Image align="center" alt="Click Data Clean Room.png" src="https://files.readme.io/2c1d9c18f9b28619e3e24cd4743ae0b98c7f04924baa2b915ec6323452a75088-42800679689105.png" width="245px" />
2. From the **Collaborations** tab, click the relevant collaboration.

   <Image align="center" alt="Click the relevant collaboration.png" src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. In the collaboration, click **New audience** > **Visual audience builder**.  
   **Note:** At least one source must be associated before you can build an audience.

   <Image align="center" alt="New Aud Visual audience builder.png" src="https://files.readme.io/31458edec870140b9c4eb0805aef0175ca5f3c698b6faa380f979398046eb58b-32455804445201.png" width="355px" />
4. Proceed with the **Audience builder** walkthrough steps below:

#### Step 1: Details and sources

The audience can be created using data from a single collaborator or by merging one source from each collaborator to enable a combined data source.

<Image align="center" alt="New aud.png" src="https://files.readme.io/c110dcda7524ddcb4ce255ac5eb1f33ffec61103219e35f54f1d5687135cf915-35683488156433.png" />

1. **Audience name:** Name the audience collaboration.
2. **Select sources:** Select a source from the dropdown list:
   * For a one-sided collaboration: select either your own source or your collaborator's source.
   * For a two-sided collaboration: select one of your own sources and one of your collaborator's sources.

     > 📘 **Note**
     >
     > * When both sources share intersecting users, the right pane shows a summary of the source intersection, providing an estimated count of users common to both sources.
     > * Transactional data sources will not be available in the source dropdown. See [Working with transactional data sources](#working-with-transactional-data-sources) below.

3. **Data combination method:** Select which data you want to build the audience from:
   * **Intersecting users** - Includes only users that appear in both sources (yours and your collaborator's).
   * **Users from my source only** - Includes only users unique to your source. Excludes all users appearing in your collaborator's source.
   * **Users from the collaborator's source only** - Includes only users unique to your collaborator's associated source. Excludes all users appearing in your source.  

     **Note:** All three options will only be available if the source permissions have "**Build Audiences**" > "**Can use all data** - **Universal dataset**" enabled. <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-create-and-manage-sources#sharing-permissions">Learn more about source permissions</Anchor>  

     <Image align="center" alt="can use all data permision enabled w arrow.png" src="https://files.readme.io/6f386c2383c75bf42da6cfdc4d662be0fdf7d623588480825e4a70f453d1f94c-46848627186065.png" width="1556px" />
4. Click **Next**.

#### Step 2: Define the audience

After the data sources are selected, this step involves choosing which attributes and values to include in your audience.

1. Click **Select column** to see the list of attributes from the sources.
2. Select an attribute, operator, and attribute value.
   * **Numerical and date attributes** can be filtered with the operators:  
     Equals, Not equals, Greater than, Lower than, Greater than or equals,  
     Lower than or equals, Between, Last "X" days (can also include the current day)
   * **Text attributes** can be filtered with the operators:  
     Equals or Non-equals

     > 📘 **Note**
     >
     > * If an attribute isn't selected, all the attributes are included by default.
     > * Once attribute values are selected, the audience size is adjusted.

3. [Optional] Click **+ Condition** to add another attribute, and select its values.  
   Repeat as needed.
4. Click **Next**.
5. Continue with the next step [Send the audience](#send-an-audience-for-activation) to activate the audience.

<Image align="center" alt="Definetheaudience.png" src="https://files.readme.io/70c93dbb737563f7b62e8a8ba111e7d5e7e1a0fa2697a2be69d5caa579bbf3dc-34588602544017.png" width="75.57%" />

#### Summary (Right-side preview pane)

The Summary panel updates in real time as you define your audience. It provides an **estimated range of unique users** that can be activated, based on the identifiers available in the selected data sources and their overlap.  
Because audience activation depends on which identifiers media partners use at runtime, the audience size is shown as a range rather than a single number.

**Source rows vs. unique users**

Source data may contain multiple rows per user.  
For example, the same person may appear several times due to:

* Multiple events
* Multiple devices
* Multiple identifiers (e.g., CUID, email, phone)

  Audience size estimates in DCP are always based on unique users, not raw rows.

**Identifiers and estimated user range**

A single source can include more than one identifier for the same user (for example, both a CUID and a hashed email) because different media partners support different identifiers, and DCP can't predict which identifier will be used during activation.

DCP estimates the audience size as a minimum-maximum range:

* **Minimum:** assumes the strongest possible overlap between identifiers
* **Maximum:** assumes identifiers represent different users

The actual activated audience will fall somewhere within this range, depending on partner capabilities and identifier matching.

**Understanding the Summary panel:**

**Total users**  
Shows the maximum number of unique users available across all selected sources before overlap is applied.

**Source contribution**  
Displays the number of unique users each source contributes and where they overlap with other sources.

**Estimated data pool**  
Represents the estimated number of unique users shared across sources, expressed as:

* A user range
* A percentage of your source contribution

This pool determines the maximum audience that can be jointly activated.

**Estimated audience size**  
The Estimated audience size reflects the expected range of unique users that match your audience definition and can be activated. The range:

* Accounts for identifier duplication
* Accounts for cross-source overlap (if applicable)
* Adjusts dynamically as filters, sources, or rules change

<Image align="center" alt="image (20).png" src="https://files.readme.io/0ba94f26978e2d3f984bd0c8c2fa8e60159420f5765cff358cdd80d6f05e271c-43432443225489.png" />

> 📘 **Note**
>
> The activated audience on the media partner side may be smaller than the audience you send due to differing match rates by media partners.

#### Working with transactional data sources

Transactional data sources, such as purchases, orders, or events that contain multiple records per user, can't be used directly in the visual audience builder. This is because using transactional data without aggregation can result in incorrect audience counts, inflated audience sizes, and unexpected segmentation results.

To use transactional data for audience creation, you must first aggregate it into a user-level dataset using the Data View tool. **To aggregate:**

1. Open the <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-create-customized-data-views">**Data View**</Anchor> tool and create a Data View from the transactional source.
2. Apply aggregation functions (such as Count, Sum, or Average) to produce one row per user.
3. Associate the aggregated Data View with the collaboration.
4. Use the aggregated Data View as your source in the Audience Builder.

<Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-create-customized-data-views#transactional-data-sources">Learn how to aggregate transactional data using a Data View</Anchor>

</Accordion>

<div id="sql-audience-builder" />

<Accordion title="SQL audience builder">

**Follow the steps below to build your audience using the SQL audience builder:**

> 📘 **Note**
>
> Make sure you have the <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">Build audiences</Anchor> permission to create an audience.

1. In AppsFlyer, from the side menu, select **Collaborate** > **Data Clean Room**.

   <Image align="center" alt="Click Data Clean Room.png" src="https://files.readme.io/2c1d9c18f9b28619e3e24cd4743ae0b98c7f04924baa2b915ec6323452a75088-42800679689105.png" width="40.57%" />
2. From the **Collaborations** tab, click the relevant collaboration.

   <Image align="center" alt="Click the relevant collaboration.png" src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. In the collaboration, click **New audience** > **SQL audience builder**.

   <Image align="center" alt="New Aud SQL audience builder.png" src="https://files.readme.io/e955bdd8a90a92dff5bb695cd64621860e79413f42ac8a8efaefc3cb80d061a5-32455799682193.png" width="355px" />
4. Proceed with the **Audience builder** walkthrough steps:

#### Set details

Name the audience, and click **Next**.

#### Build query

1. Click the editor to open the [SQL builder](#sql-audience-builder).
2. Write your SQL query to build your audience. You can use joined or one-sided sources.

> 📘 **Note**
>
> If your query includes a transactional data source, it must include aggregation logic, such as COUNT, SUM, AVG, MIN, or MAX, to reduce the data to one row per user before it can be used for audience creation. Queries that use transactional data without aggregation aren't supported. See [supported and unsupported query patterns](#transactional-data-in-sql-queries) below.

3. Click **Test** and review the query results (audience sample) shown beneath the query statement.
4. Click **Continue** and then **Next** to proceed with the next step of the **Audience builder** walkthrough, or **Save as draft** and resume later.
5. Continue to [Send the audience](#send-an-audience-for-activation).

#### The SQL audience builder

Use the SQL builder to query the data and create an audience. The following table outlines the sections in the builder:

| Section | Description |
| --- | --- |
| <span id="left-pane"></span>Left pane | Presents all available sources for creating your audience. This may include your sources and those shared with you. You'll only be able to view sources to which you have the <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">**Build audience**</Anchor> permission.<br /><br />Selecting a source expands it to reveal corresponding columns. |
| <span id="topmiddle-section-text-editor"></span>Top-middle section (query editor) | The query editor for writing your SQL statements. |
| <span id="bottommiddle-section-context-panel"></span>Bottom-middle section (context panel) | This section dynamically shows details based on the selected object from the left pane:<ul><li>**When selecting a source:** Shows the column names ("Field name") and their corresponding types ("Type").</li><li>**When a column is selected:** Shows the column values ("Distinct values") and the row count for each value ("Count").</li><li>**Following query execution:** Shows a sample of the query results.<br />**Note:** As a privacy measure, the results table doesn't display hashed values, such as emails and IDs. These values are shown as "Restricted".</li></ul> |
| <span id="right-pane"></span>Right pane | This section dynamically shows details based on the selected object:<ul><li>**When selecting a source:** Shows the permissions granted for the source.</li><li>**While writing the SQL query:**<ul><li>Shows the query validity status on the top right of the page. This may include any of the following statuses:</li><li>**Ready to run:** No issues found. You can test the query and proceed to the next step.</li><li>**Syntax error:** An error in syntax was detected along with guidance on resolving it.</li><li>**Permission error:** Indicates a lack of required permissions, with a tooltip detailing which <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-create-and-manage-sources#view-permissions-for-collaborator%E2%80%99s-source">access rights are provided for the source</Anchor>.</li><li>Shows a **Test** button on the top right of the page. Once you've completed writing your query, you must test it to confirm the accuracy of the intended audience.<br />Click **Test** to test your query and examine the results.</li></ul></li></ul> |

#### Transactional data in SQL queries

When working with transactional data sources in the SQL Builder, the following query patterns apply.

**Supported query patterns**

| Pattern | Description |
| --- | --- |
| <span id="single-transactional-source-with-aggregation"></span>Single transactional source with aggregation | A query that aggregates a transactional source into one row per user. For example, aggregating purchase records to produce a total purchase count per user. |
| <span id="transactional-source-joined-to-a-profileuserlevel-source"></span>Transactional source joined to a profile/user-level source | Allowed when the transactional side is aggregated before the join. For example, aggregating purchase history by user, then joining the result to a customer profile dataset. |
| <span id="aggregated-transactional-output-in-downstream-joins"></span>Aggregated transactional output in downstream joins | Once aggregated to the user level, the output can be used in further joins and audience-building workflows, and is treated similarly to a profile-level dataset. |

**Unsupported query patterns**

| Pattern | Description |
| --- | --- |
| <span id="transactional-source-joined-directly-to-another-transactional-source"></span>Transactional source joined directly to another transactional source | Direct joins between two transactional datasets, such as purchases joined to orders, aren't supported. These joins are blocked before execution because they can multiply records, produce incorrect audience results, and create transactional expansion. |
| <span id="nonaggregated-transactional-query"></span>Non-aggregated transactional query | Queries that use transactional records directly, without aggregation, aren't supported. |

</Accordion>

## Send an audience for activation

After an audience is built, activate it where it can drive results. Select a destination, such as media partners for campaign targeting or a cloud storage bucket for downstream use, and DCP refreshes and delivers the audience daily based on the latest source data and <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-create-and-manage-sources#sharing-permissions">permissions</Anchor>.

* [**Connect an audience to media partners**](#connect-an-audience-to-media-partners) - Media partner platforms include Meta Ads, Google Ads, and many more. Connect your audience to media partners when you want to run paid campaigns, remarketing, or look-alike expansion.
* [**Export an audience to cloud storage**](#export-to-cloud-storage) - Connect your audience to cloud storage when you need the file in BI models, CDPs, or internal enrichment pipelines.

> 📘 **Note**
>
> * The audience is sent for activation as a list of user IDs. This list is continually refreshed and sent to the selected destinations daily.
> * With every update to the source data, the audience is automatically refreshed and sent to the selected destinations.

<div id="connect-an-audience-to-media-partners" />

<Accordion title="Connect an audience to media partners">

Send the audience for activation directly in your preferred media partner platforms, such as Meta Ads and <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10010286?hl=en">Google Ads</Anchor>. The system forwards a CSV of user IDs, hashed automatically if the partner requires it.

> 📘 **Note**
>
> * When you build an audience using your collaborator's source data, the activation options you see depend on the <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-sharing-permissions">permissions</Anchor> granted by your collaborator. Only the activation partners they allowed for that source will be available to you during activation.
> * If your collaborator didn't grant you permissions to publish or export audiences, you can still submit an activation request. In this case, your activation request is sent to your collaborator for activation on their side.

**To connect the audience to media partners:**

1. Within the audience builder, turn on **Connect audiences to media partners**.  

   <Image align="center" alt="Connect audience to media partners.png" src="https://files.readme.io/d1e6558183eed8f239f1d61efd81cd71db7a2c7f6acfdef7e1c029dea51af172-37184169230097.png" />
2. Click **+ Partner connection**.
3. If no partner connections were established, create a new partner connection:
   1. Click **+ Add connections**.
   2. Select the relevant media partner (Meta Ads, Google Ads, Pinterest, TikTok, DV360, or The Trade Desk).
   3. Enter a name for the connection.
   4. Click **Login with [partner name]**. You'll be directed to the partner login page. Choose the account to receive the audience. Then, you'll be directed back to the dialog window.
   5. Click **Select account ID** and select the relevant account ID.
   6. Click **Save**.
4. Click **Save & send**.

<Image align="center" alt="image (21).png" src="https://files.readme.io/bb7785936d3e79e18adffe31ca8121b5c0a65392508ef0aea76c7dc75e9ce9eb-43432561109777.png" />

</Accordion>

<div id="export-to-cloud-storage" />

<Accordion title="Export to cloud storage">

Send the audience directly to your cloud storage bucket. With every audience update, DCP automatically exports the latest version to your selected destination. You can also download the audience as a CSV file at any time.

> 📘 **Note**
>
> Before exporting, make sure your cloud storage bucket is set up and connected to DCP. See <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">Set up your cloud services</Anchor> and <Anchor target="_blank" href="/marketers/id/docs/data-collaboration-platform-dcp-add-connections">Add connections</Anchor> for instructions.

**To export the audience to cloud storage:**

1. Within the audience builder, turn on **Export to cloud storage**.
2. From the **Cloud storage connections** dropdown, select an existing connection.
   * If you don't have a connection yet, click **+ New cloud connection**. The connection dialog opens directly on this page, without leaving DCP. Complete the setup and click **Save**. The new connection is selected automatically.
3. Click **Save & send**.

</Accordion>

## Manage audiences

View and manage audiences associated with a collaboration.

<div id="access-audience-management" />

<Accordion title="Access audience management">

**To view and manage audiences associated with a collaboration:**

1. In DCP, go to the **Collaborations** tab and click the relevant collaboration.
2. Click the **Audiences** section.  
   <Image align="center" alt="Audiences section new UI.png" src="https://files.readme.io/8f8170d6848da0158c7db76938bdb4fa64cb3a9702218fe549e6b6e859d64140-small-43777994824977.png" width="2836px" />

**What you can do from this page:**

* **Search for an audience:** Search by either the source name or the audience name.
* **Sort audiences:** Sort audiences by clicking on any of the column headings.
* **View audience details:** See details such as the collaborator's name, statistics on overlapping users, [audience status](#view-audience-statuses), and activation location.
* **More actions:** Clicking the 3-dot menu icon of an audience card opens additional available actions:
  * [**Edit:**](#edit-the-audience-activation-destination) Modify the audience activation destination.
  * **Duplicate:** Create a new, independent copy of the audience.
    * The new audience's sources and data combination method carry over locked (can't be changed); filters and activation destinations carry over pre-filled but are fully editable.
    * Duplicate is disabled for SQL audience builder audiences and for audiences with an "Invalid" status.
  * **View history:** See all instances of the audience activation, with details such as the connection and activation status.
  * [**Delete:**](#delete-an-audience) Delete the audience.
  * **Pause audience:** Prevents the audience from being updated and re-activated when the data source is modified.

</Accordion>

<div id="edit-the-audience-activation-destination" />

<Accordion title="Edit the audience activation destination">

While building an audience, you can save it as a draft and then return to it and edit the activation destination (depending on your permissions).

**To edit the audience activation destination:**

1. From the **Collaborations** tab, click the relevant collaboration.
2. Click the **Audiences** section and locate the relevant audience.
3. Click the 3-dot menu icon that appears when hovering on the audience > **Edit**.
4. Under **Connect and export** (at the bottom of the audience page), turn on the relevant toggle:

   * [Connect to media partners](#connect-an-audience-to-media-partners)
   * [Export to cloud storage](#export-to-cloud-storage)

</Accordion>

<div id="delete-an-audience" />

<Accordion title="Delete an audience">

You can delete an audience created in your account. Doing so removes it permanently from your account.

**To delete an audience:**

1. From the **Collaborations** tab, click the relevant collaboration.
2. Click the **Audiences** section and locate the relevant audience.
3. Click the 3-dot menu icon that appears when hovering on the audience > **Delete**.
4. Confirm deletion.

</Accordion>

<div id="view-audience-statuses" />

<Accordion title="View audience statuses">

You can view the **Last upload status** of audiences associated with a collaboration.

<Image align="center" alt="image (26).png" src="https://files.readme.io/5659a3e30aac91226ecf8d1cf08618b698f063d1412522f2c231459fdfc7fb03-43541066537105.png" width="860px" />

There are various statuses an audience can have:

* **Active:** The audience was successfully sent to the destination platform(s) and is available for use in campaigns.
* **Draft:** The audience was saved as a draft (it was never connected, exported, or delivered).
* **Invalid:** Indicates that a source or data view used for the audience has expired, been deleted, removed from the collaboration, or no longer has valid permissions.
* **Pending delivery:** The audience was sent to the collaborator for activation, and it's pending activation.
* **Paused:** The audience has been manually paused and won't be sent when new data becomes available.
* **Suspended:** The collaboration and its associated audiences have been suspended.

You can also view the **Upload history** status of an audience.

**To view the upload history:**

Click the dropdown next to the specific audience and select **View history**.

<Image align="center" alt="View history doctored .png" src="https://files.readme.io/7840f05fd8f6a98445c29e5a59813776378d842dd54fab4e3f66111c34dd89dd-36573637043089.png" />

**Upload history statuses include:**

* **Processing:** The audience is currently being prepared.
* **Success:** The audience was successfully sent to all connections.
* **Partial failure:** The audience could not be sent to one or more connections.
* **Failure:** There was an issue processing the audience (e.g., due to mismatched data, platform restrictions, or platform errors).
* **N/A:** The audience is in draft or pending status. Upload history status is not applicable.

</Accordion>

<div data-zendesk-anchors="overview=about-dcp-audiences h_01HWG1P909NHBXC5VF23BDVVPH=about-dcp-audiences key-features=build-an-audience h_01HWG5B2MEJH7M8E9BWA3FQFQ2=build-an-audience 01KFDX0R4BYSTE1V5G7ATQ6FZS=key-features h_01HWG62BA9X4VRRDXAEKA07FTJ=visual-audience-builder h_01HZMBFKV40PHFN1B8PVVCMWQQ=note step-1-join-sources=step-1-details-and-sources h_01HWFRRGP99KKGBSQ6QB10RD26=step-1-details-and-sources h_01KT94AC4N81MBE0DAT7TX2QA7=note-1 step-2-build-audiences=step-2-define-the-audience h_01HWFRRPFTCFGEHY1AW8G4VMY4=step-2-define-the-audience h_01JSEPSRF3FFJJ4S20GJJPJVWF=note-2 summary-rightside-preview-pane=summary-right-side-preview-pane h_01KBMPR7BHCTTVE8DR1TCRYAHJ=summary-right-side-preview-pane h_01KBMPK2HXMZ6YNQMJTST9BD8Y=note-3 h_transactional-data-visual-builder=working-with-transactional-data-sources h_01HWG62BAAD46MTK385756T4AQ=sql-audience-builder h_01HZM8X9RZ1A9CKWYNM61QW515=note-4 step-1-set-details=set-details h_01HWG9VX0QB3GFZDARAT5QKHV0=set-details step-2-build-query=build-query h_01HWG9Y6B9X3T1FFM9ZR8TVBVC=build-query h_01KT6SCS53699DZXE4EF92WC44=note-5 h_01HZM9P2GNCPGJDEA51HCV1Y99=the-sql-audience-builder h_transactional-data-sql-patterns=transactional-data-in-sql-queries send-audience-for-activation=send-an-audience-for-activation h_01HZMCHKMVXRWK7RXZ7NN65JQX=send-an-audience-for-activation h_01HZMCRJBBXFEV6JXEHGFXZDZW=note-6 h_01KFG12R13ADFBY4XBDRGE956V=connect-an-audience-to-media-partners h_01HZMDXEEABQRQE8XMZNE86SRF=note-7 h_01KFG12R13R9B6ATHTBTKAVAMX=export-to-cloud-storage h_01KY2FJV90NYBVTQBN6K63K9DS=note-8 h_01HZPWTG23YQ5Y1GAPXT65DK07=manage-audiences h_01KFBA379S9ZZAKN7FC7X2S297=access-audience-management h_01KFB4HVDZZ0MA4Q69DXKH4YY7=edit-the-audience-activation-destination h_01KFB4HVDZJ08STDXGA7ZP8MM3=delete-an-audience h_01KFB4HVDZFCJNYG6VVWTWVAQ8=view-audience-statuses" />

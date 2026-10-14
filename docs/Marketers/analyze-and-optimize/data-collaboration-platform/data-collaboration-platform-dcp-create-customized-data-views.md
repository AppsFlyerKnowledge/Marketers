---
title: Data Collaboration Platform (DCP) - Create customized data views
excerpt: >-
  Create customized subsets of your existing source data with no SQL or
  technical expertise needed. Data views let you modify, refine, and summarize
  the data, so you can share only what's relevant with collaborators.
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2024-11-22T12:57:55Z'
  edited_at: '2026-06-18T14:18:48Z'
  id: 30296051098897
  locale: en-us
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/30296051098897-Data-Collaboration-Platform-DCP-Create-customized-data-views
---
## About data views

**Data views** let you create customized subsets of your existing data sources that you can share in collaborations, without changing the original dataset. They let you perform functions that modify, refine, and summarize the data so you can share only what's relevant, keeping the data you share clear and focused, and all other data private and secure. Designed for non-technical users, no SQL knowledge, data expert, or data engineer is required.

### Data view functions

With the data view builder, you can shape your data by applying the following key functions:

* **Filter** your dataset to focus on relevant information by applying conditions such as time range, category, or custom parameters.
* **Calculated fields enable** you to:
  * **Transform** the structure, format, or values in your data to generate new columns and extract insights from existing fields.
  * **Aggregate** records to create meaningful summaries using functions like Sum, Average, Count, Min, and Max.
* **Select fields** to include only the columns you need in your data view, keeping your output clean and purposeful.

## The data view builder

**![New data view - Default.png](https://files.readme.io/b34b61b2fbc092884270ce0daab9a86deae6b423775bcc648ee0eba6f319e8e5-41945719130897.png)**

## Create a data view

To get started creating a data view, follow the steps below:

**Prerequisites**

An AppsFlyer [account](https://www.appsflyer.com/sign-up/) with DCP access.

<div id="set-the-data-view-general-details" />

<Accordion title="Step 1. Set the data view general details">

1. In AppsFlyer, from the side menu, select **Collaborate** > **Data Clean Room**.

   ![Click Data Clean Room.png](https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png)
2. From the main **Sources** tab (at the top), hover over the specific source you want to create the data view from, and click  ![ellipsis.png](https://files.readme.io/d3e33f1864edb1d9d2f8e18c9c7887454018a67e9f7fed054e7134231dba60a2-30296671836433.png)  (the Menu icon) at the end of the row.
3. Select **Create a data view**. You're directed to the **New data view** page.

   ![Create a data view w arrow.png](https://files.readme.io/f9fbcacabb560da996e1dc009e6cd2c5b78d3ccd42e89e2a3c37e71882577e18-41945719135889.png)
4. Set the following fields:
   * **Data view name:** Enter a name for the data view. This can be any unique name that will help you identify it. See the [naming requirements and guidelines](#naming-requirements-and-guidelines) below.
   * **Description:** Enter a description (optional). This appears as a tooltip when hovering over the data view name under the **Sources** tab. It's recommended to highlight the primary objectives and data manipulations performed.

#### Naming requirements and guidelines

* Make sure the name is unique among all other sources and sub-sources in your account. Otherwise, you won't be able to save it.
* For cloud integrations, the name doesn't need to match the file name.
* Name requirements:
  * Length: 2-80 characters
  * Valid characters:
    * letters (A-Z, a-z)
    * numbers (0-9), *cannot be the first character of a name;*
  * Invalid characters:
    * Spaces
    * Underscore
    * all other symbols or special characters

</Accordion>

<div id="h_01K4SDE8H7R9YZYXMRVXV5GZSV" />

<Accordion title="Step 2. Filter your data (optional)">

You can apply filters to narrow down the data by using selected attributes, helping you focus on specific and relevant information.

**To apply filters:**

1. Under **Filters**, click **Filter data**.
2. Click **Select column** and select the relevant column from the dropdown menu.
3. Select anoperator.
4. Enter a value.
5. [Optional] Click **+ Condition** to add a condition to the filter.

> 📘 **Note**
>
> * You can add as many conditions as needed, using the AND and OR operations.
> * Multiple conditions are processed according to the standard logical order, with priority given to AND operations over OR.
> * When using functions or filters on date-type fields (columns), make sure that the date values conform to the supported date format specific to the selected function. Any discrepancies may lead to suboptimal choices among the provided options.

</Accordion>

<div id="transform-aggregate-and-filter-data" />

<Accordion title="Step 3. Create calculated fields (optional)">

Calculated fields enable you to use functions to add new fields, change data format and values, or combine records using logic, calculations, or aggregation.

**To create a calculated field:**

1. Under **Calculated fields**, click **+ New field**.
2. Enter a **New field name**.
3. Click **Set function**, and select a function from the [list of functions](#zd-list-of-functions-and-use-case-examples). The relevant fields for entering the required information are automatically added.
4. For **Aggregation** fields:  The **Group by** section will automatically open and you can select the field that defines how the aggregated data will be grouped.
5. [Optional] Click **+ New field** to add more **Transformation** or **Aggregation** fields. You can add as many as needed.

#### **Group by**

Group your data into meaningful categories when applying an aggregation. When you add an aggregation function, the Group by section opens automatically and lets you select the field(s) that determines how the data is grouped. For example, you can group results by country, user ID, or product line to calculate totals or counts for each group.

![Group by.png](https://files.readme.io/40fc355847acf7269c6fcd2b505ed182b407d4c668f717612b53c5fd88506443-41967849623057.png)  

**To select the fields to group by:**  
Click  **+Field** to add fields.  
**Note:** The first fields selected are the identifiers selected in the original source.

Once created, the new field is:

* Included in the **Calculated fields** section.
* Included in the list of fields available for use in all functions and filters.
* Included in the list of fields under the [Select fields](#select-fields) section.

<div id="zd-list-of-functions-and-use-case-examples" />

#### List of functions and use case examples

#### **Transformation functions**

* **IF:** A conditional statement that executes different actions based on whether a specified condition is true or false.
* **CONCAT:** The concatenation of two strings
* **CONST:** Returns the parameter of the CONCAT function
* **LEAST:** Returns the lowest of two values
* **GREATEST:** Returns the highest of two values

#### **Example: Transformation**

You want to indicate products purchased from the collaborator while masking purchases from other brands you're working with.

#### **Aggregate functions**

* **COUNT:** Returns the number of rows.
* **SUM:** Returns the sum of all values
* **AVG:** Returns the average of all values
* **MIN:** Returns the minimum values of two numbers
* **MAX:** Returns the Maximum values of two numbers

#### **Example: Aggregation**

You want to count the total number of purchases per user and sum the total price they paid.

#### Example: Aggregation with a condition

You want data on the latest purchases made by users located in Germany and who purchased P&G products.

</Accordion>

<div id="select-fields" />

<Accordion title="Step 4. Select fields (optional)">

The data view structure includes fields from the original data source and any custom data fields created within the data view builder. From here, you can remove fields or rearrange their order (Note that you'll need to retain at least one identifier field in the data view).

> 📘 **Note**
>
> * Adjusting the field type can only be done from the original source, not from the data view.
> * If you created a new field that is using an aggregation function, the fields available in the selection will only be the ones that are in the **Group by** of the function.
> * Removing a field from the selected fields will not affect the aggregation function results.

<div id="adjust-field-types" />

<Accordion title="Adjust field types">

Review each field and select the appropriate data type from the dropdown list beside it to change it.

</Accordion>

<div id="remove-fields" />

<Accordion title="Remove fields">

You can remove any of the fields. If there are multiple identifier fields, you can remove all except one. A data view must contain at least one identifier field.

**To remove a field:**

1. Hover over the right side of the field you want to remove.
2. Click the dustbin icon that appears. The field now appears in the **Removed** section, with a **Restore** button that allows you to bring back the removed field.
3. Click [Save](#save-your-data-view).

</Accordion>

<div id="restoring-temporarily-removed-fields" />

<Accordion title="Restoring temporarily removed fields">

When a field is removed from the list, it is placed under the **Removed** section. You can restore the field at any point as long as the field is part of the original source.

</Accordion>

</Accordion>

<div id="save-your-data-view" />

<Accordion title="Step 5. Review and save your data view">

**Side panel**

The side panel on the right side of the page presents two sets of data, one from the original source and one from the data view created from it. Each set includes the table name and description, the number of fields, and the number of rows, along with a sample table containing five rows of data. When functions and filters are applied to the data view, the side panel reflects these changes, enabling you to verify the data while modifying it, and compare it with the original version.

![Data view - side panel.png](https://files.readme.io/c1dae932618bf2ded68a30853474ce9d6107fdb09541a5d12ac3ddcf4def0101-41945719138577.png)

You can save the data view at any stage. Once saved, it is added under the original data source in the list of sources, and you can [edit, share, or delete it](#manage-data-views).

**To save the data view:**

Click **Save** at the bottom of the page.

</Accordion>

<div id="h_01JVSEG13462Z4XXD1NE8GW1HE" />

<Accordion title="Step 6. Share your data view in a collaboration (optional)">

You can [associate your data view with a collaboration](You%20can%20share%20(associate)%20your%20data%20view%20in%20a%20collaboration,%20enabling%20a%20brand%20collaborator%20to%20view%20and%20perform%20actions%20with%20it%20(based%20on%20the%20permissions%20you%20set).), enabling brand collaborators to view and perform actions with it (based on the permissions you set).  
**Note:** To associate a data view with a collaboration, you must either be the creator of the collaboration or be invited to it.

> 📘 **Note**
>
> If you created this Data View to aggregate a transactional source for audience creation, make sure to associate it with the relevant collaboration. The aggregated Data View must be associated with the collaboration before it becomes available as a source in the Audience Builder. [Learn how to associate sources with a collaboration](/docs/data-collaboration-platform-dcp-create-a-collaboration).

</Accordion>

## Use cases

This section outlines some common use cases for data views.

<div id="common-use-cases" />

<Accordion title="Common use cases">

Data views are useful when you need to tailor and control access to data for different audiences or business purposes. Here are a few common scenarios:

* **Brand-specific reporting**  
  If you're working with multiple brands using a single data source, you can create separate data views for each brand, showing only the data relevant to them. This keeps the data clean, focused, and compliant with privacy or competitive boundaries.
* **Internal collaboration**  
  Share tailored views with different teams, such as marketing, product, or sales, so each team sees only the fields and records that are meaningful to their work. This avoids confusion and ensures that each team is working with the right subset of data.
* **Client data sharing**  
  When sharing reports or insights with clients or external partners, data views let you exclude sensitive or irrelevant information while still providing full visibility into the data that matters to them.
* **Category or region filtering**  
  You can build views filtered by country, product line, or other dimensions, making it easier to focus on specific market segments or business units without cluttering reports with unrelated data.
* **Data summarization**  
  Apply aggregation to summarize key metrics, such as total purchases by region or user activity over time, so your collaborators see high-level insights instead of raw data.
* **Transactional data preparation**  
  If your source contains transactional data , such as purchases, orders, or events with multiple records per user, use a data view to aggregate it into a user-level dataset before sharing it for audience creation. This prevents inflated audience sizes and ensures accurate segmentation results. See [Using transactional data sources](#h_transactional-data-sources) below.

</Accordion>

<div id="transactional-data-sources" />

<Accordion title="Transactional data sources">

Transactional data refers to sources that contain multiple records per user (for example, purchases, orders, or events). If you're working with a transactional data source, you must aggregate it into a user-level dataset before it can be used for audience creation in the Audience Builder.

> 📘 **Note**
>
> When you open a transactional data source directly, or are redirected here from the Audience Builder, a banner is displayed confirming that aggregation is required. The aggregated Data View must also be associated with the relevant collaboration before it becomes available as a source in the Audience Builder.

**Why aggregation is required**

Transactional datasets can contain multiple records per user. Using them directly in audience creation can result in incorrect audience counts, inflated audience sizes, and unexpected segmentation results. Aggregating the data produces one row per user, making it suitable for audience workflows.

**To prepare transactional data for use in the Audience Builder, follow these steps:**

1. Create a Data View from the transactional source (see [Create a data view](#create-a-data-view) above).
2. Apply aggregation functions, such as Count, Sum, Average, Min, or Max, to produce one row per user.
3. Apply filters if needed to refine the dataset.
4. Associate the aggregated Data View with the collaboration (see [Step 6](#h_01JVSEG13462Z4XXD1NE8GW1HE) above).
5. Use the aggregated Data View as the source in the Audience Builder.

[Learn how to build audiences](/docs/data-collaboration-platform-dcp-build-and-activate-audiences)

</Accordion>

## Manage data views

The data views appear in the **Sources** tab, under the original source. You can edit the functions, filters, and fields, delete data views, or share them with collaborators.

<div id="edit-details" />

<Accordion title="Edit a data view">

You can modify the data view description or the labels used in the description.

1. In AppsFlyer, from the side menu, select **Collaborate** > **Data Clean Room**.
2. From the **Sources** tab, click the source name. The associated data views are shown.
3. Hover over the data view to modify, and click [![edit-subdomain.png](https://files.readme.io/0bb6f6e4caf3a363cb85ca96016485ee4dd378ed1af461f0c5295d83509db515-30296682398481.png)](/docs/data-collaboration-platform-dcp-create-customized-data-views#share-a-data-view) (the Edit icon) at the end of the row.
4. Edit the description or the labels applied.

</Accordion>

<div id="delete-a-data-view" />

<Accordion title="Delete a data view">

**To delete a data view:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Data Clean Room**.
2. From the **Sources** tab, click the source name. The associated data views are shown.
3. Hover over the data view to modify, and click **Delete source** at the end of the row.

A data view can also be deleted from a collaboration.

**Note:**    
When you delete a data view:

* Collaborators lose access to the data views shared with them (associated) through a collaboration.
* Audiences based on the data view can no longer be used.

</Accordion>

<div id="share-a-data-view" />

<Accordion title="Share a data view">

Share your data view with the collaborator and grant them the necessary permissions.

1. In the Data Collaboration Platform, go to the **Collaborations** tab > specific collaboration.
2. In the collaboration dashboard, click the action menu on the upper right > **Associated sources**.

   ![Associate source new UI.png](https://files.readme.io/3730b39bb5754260b74632591dffe3fcf54e6c73ff114ba0a8853f277e1e709a-43751907286161.png)
3. Select your data view (source) from the dropdown menu to associate it with the collaboration.  

   ![select data view.png](https://files.readme.io/f1681e5a4096459cbc570531494a8a7be8e4f835d95e4435217b0e8e15715772-43751923329937.png)  
   Then click **Save**.
4. **Optional:** Set custom data permissions on the data view source.

   You can set custom permissions (that is different than the general data permissions policy). **To set custom data permissions on your data view source:**

   From the 3-dot menu next to the data view source, click **Edit permissions**.  

   ![Edit permissions new.png](https://files.readme.io/58c785d7fdda52aa159153676d5875e718ceae2f31f987706b79509eb8251151-43752564819985.png)
5. Set the permissions according to your preferences ([learn about permissions](/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source)), then click **Save**.

> 📘 **Note**
>
> You can only associate data views created from your sources.

</Accordion>

<div data-zendesk-anchors="overview=about-data-views 01JD9Z4WKKDWS2EQND0SY7EADZ=about-data-views 01JD9Z4WKMTZ18E13E6V3KZYB3=data-view-functions 01JD9Z4WKNREMCMB9PNSVVQ024=the-data-view-builder set-a-data-view=create-a-data-view 01JD9Z4WKRD4V4A07WT5YG42RZ=create-a-data-view 01JD9Z4WKWQJJE9Q8EMQY8NCMD=set-the-data-view-general-details naming-requirements=naming-requirements-and-guidelines 01JD9Z4WKX3BGN7V9V1V1YBYWT=naming-requirements-and-guidelines 01JDEVRX2EV64YQN2JE901CEK8=note 01JD9Z4WM1EQVKS9B4EHMTHW41=transform-aggregate-and-filter-data h_01KC69N1HAVXE2NVB6DZRJG91N=group-by list-of-functions-and-use-case-examples=zd-list-of-functions-and-use-case-examples 01JD9Z4WMDV8B7P8W5E13J7HNJ=zd-list-of-functions-and-use-case-examples h_01JDA45VWKH2ZKVBTK87VFVKTB=transformation-functions h_01JDA4611HFFEA17352NSNCJYX=example-transformation h_01JDA467NV99FDAXJCXYSD5PBF=aggregate-functions h_01JDA46DWD6G3S4S5FM48KWQXA=example-aggregation 01JDETVS9XQ9XCNEFVCSC8GAJR=example-aggregation-with-a-condition 01JD9Z4WMJ9XFBXPJAM6RNRP96=select-fields 01JD9Z4WMJJGXG9XXSW6Q6S5KE=note-1 01JD9Z4WMKA2J94AYW9VXKKVKQ=adjust-field-types 01JD9Z4WMM4QQDP749R7H93Z67=remove-fields 01JD9Z4WMNHXCP4Q66C1TN67Y4=restoring-temporarily-removed-fields 01JD9Z4WMQGY8DCEWMPGX8FC2Y=save-your-data-view h_transactional_share_note=note-2 h_01JVSHYGNEFEKP713NNYSSZPS2=use-cases h_01JVSHX282XSCWMN2JRZJ593KN=common-use-cases h_01KT964QX4EW74REN13T1TBKGN=transactional-data-sources h_transactional_banner_note=note-3 01JD9Z4WMRFS0S408ZJ2YKBZF3=manage-data-views 01JD9Z4WMT7GG4JV91JE5KAJ4X=edit-details 01JD9Z4WMZGV916XJ77V3NR1HK=delete-a-data-view 01JD9Z4WN3VX56JDWK937D1WXH=share-a-data-view 01JDA2A87RG8V8RZW4EB1B2K56=note-4" />

---
title: Audiences - Import audience segments from internal systems
metadata:
  keywords:
    - Developers
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-09-15T10:45:43Z'
  edited_at: '2026-10-05T06:46:48Z'
  id: 360013291857
  locale: en-us
  section: Audiences
  section_id: 6551336428945
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360013291857-Audiences-Import-audience-segments-from-internal-systems
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Import predefined audience segments from your internal systems (such as BI and CRM) to AppsFlyer Audiences, allowing you to use Audiences to connect and maintain these segments with your advertising partners.

## Why import audiences?

In certain circumstances, you may have predefined audience segments in your internal systems. Importing these audiences (as lists of device and/or user identifiers) to AppsFlyer allows you to use Audiences as your central point for connecting and maintaining all of your audience segments with your advertising partners. Additionally, it enables you to take full advantage of other Audiences features, such as identifier matching/data enrichment and connected campaign metrics.

Consider the following examples:

> 📄 **Examples**
>
> **Promotional remarketing** You want to target promotional offers to users during the month of their birthdays.
>
> Here's how to do it with Audiences:
>
> 1. Use your internal CRM to generate a list of users along with their birthdays.
> 2. Segment the list according to birthday month, and export it as individual lists of advertising IDs.
> 3. Import the lists to AppsFlyer as audiences and connect them to the partners with which you want to run the promotional campaigns.
> 4. Set up campaigns with the relevant partners to target the audiences accordingly.
>
> **Acquiring additional users** Your app development studio acquires another studio. The studio you acquired has the device IDs of users who previously installed their apps, and you want to target these users to install your existing apps.
>
> Here's how to do it with Audiences:
>
> 1. Obtain the list of device IDs from the studio you acquired, and import it to AppsFlyer as an audience.
> 2. Connect the audience to the partners with which you want to run campaigns.
> 3. Set up campaigns with the relevant partners to target these users accordingly.

## Audiences import V2.0

This article describes concepts and procedures related to the new Audiences import feature V2.0 (with options for importing by CSV and API).

## Imported audience types

When you import an audience, you designate it as one of two types, which determines how AppsFlyer treats the uploaded audience, both in terms of processing and uploading it to partners. **The designation is made when an audience is first imported and can't be changed later.**

**A standard imported audience:**

* Undergoes identifier matching and data enrichment—a process in which Audiences matches imported identifiers with existing identifiers in the Audiences database (for the same user on the same app) in order to enrich audience data uploaded to partners.
* Is uploaded to partners subject to your account's user identifier policy.
* Must be imported using the V2.0 import feature described in this article.

**An "As-is" imported audience:**

* Doesn't undergo identifier matching and data enrichment.
* Is uploaded to partners without reference to your account's user identifier policy (meaning all imported identifiers are uploaded to partners).
* Can be imported using the V2.0 import feature (described in this article).

> 🚧 **Important!**
>
> * All audiences existing as of November 23, 2021, **are designated as-is audiences and cannot be changed to standard audiences.** You can continue to update these audiences as necessary using either the V2.0 import feature (described in this article).
> * You can have up to 500 active imported audiences at any one time.
> * Only an admin can designate a new imported audience as an as-is audience.
> * When importing an audience with CUID as the identifier, the CUID association must have been received by AppsFlyer on the install (not just on post-install events) for complete association with the relevant devices and successful enrichment with device identifiers (i.e., GAID, IDFA). <Anchor target="_blank" href="/marketers/id/docs/customer-user-id-field-cuid#mengatur-cuid">Learn more</Anchor>

## Audience import procedures

Import an audience either by uploading a CSV file or using the Import Audience API.

<div id="import-a-csv-file" />

<Accordion title="Import a CSV file">

Prepare a CSV file, with the following specifications:

**Format**

* One column for each user identifier being uploaded
* A header row with the name of the identifier in each column (all lowercase)
* No blank rows
* Maximum number of rows: 1 million
* If you prepare the file using Excel, save it as a **CSV (Comma delimited) (\*.csv)** file, as shown in the fol following image:

<Image align="center" alt="CSV.jpg" src="https://files.readme.io/863505596fd525ff0750f05db70413e9aaee51beb208bd0fbc8ab718ad4e4576-32897281151633.jpg" width="339px" />

#### identifier hash

> 📘 **Note**
>
> This CSV format is for importing audience segments. If you're importing user attribute data instead, see <Anchor target="_blank" href="/marketers/id/docs/audiences-create-better-audiences-with-user-attribute-data">Create better audiences with user attribute data</Anchor>, which uses a different CSV format with no header row.

**Columns and identifiers**

* Data is ingested using the header row to identify the data in each column, therefore:
  * There is no requirement that columns appear in a specific order.
  * There is no requirement to include columns for identifiers not being uploaded.
  * You can import as many identifiers as you want in a single CSV file so long as each row includes the required identifiers, as further detailed below.
* Available identifiers:
  * app\_id
  * idfv
  * idfa
  * gaid
  * oaid
  * imei
  * cuid
  * emails
  * phone
  * phone\_e164
  * braze\_id
  * amplitude\_id  

    **Note:** Additional identifiers such as emails and phone must either be in the encrypted sha256 format or left blank.
* Required identifiers:
  * For Android audiences: **app\_id** + one of: **gaid** OR **oaid** OR **imei** OR **cuid** OR **braze\_id** OR **amplitude\_id**
  * For iOS audiences: **app\_id** + one of: **idfv** OR **cuid** OR **braze\_id** OR **amplitude\_id**
* In compliance with Google's enforcement of the <Anchor target="_blank" href="/marketers/id/docs/audiences-user-identifier-policy#eu-digital-markets-act">Digital Markets Act (DMA)</Anchor> on March 6, 2024, when importing an “as is” audience, two additional AppsFlyer consent columns will need to be added. These are:

| AppsFlyer consent columns | Google field | Values | Field explained |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true/false | Did the user give Google consent to use their data for personalized advertising? |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true/false | Did the user give consent to send their user data to Google? |

If the consent fields are not filled in with values, they will be sent to Google as “Unspecified”, and will not likely be included in the audience on Google's side. Filling in these fields ensures maximum inclusion of users from the <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">European Economic Area (EEA)</Anchor> in your Google audiences.

**Example CSV files:**

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/4413851475729">new-import-android-example.csv</Anchor>  
<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/4413840980497">new-import-ios-example.csv</Anchor>

<span id="01ECF4ZD0RB90HZC6ZFNTKMDSG"></span>**To create and import a new audience using a CSV file:**

1. In the AppsFlyer left-side panel, go to **Engage** > **Audiences**.
2. Click **New audience**.
3. Select **Import audience**.  
   The **Import audience** window opens.
4. Enter a unique **Audience name**.  
   **Note:** Audience names can't include special characters (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)
5. Select the audience platform: **Android** or **iOS.**
6. Indicate whether this audience is a [**standard** audience or **as-is** audience](/docs/audiences-import-audience-segments-from-internal-systems#imported-audience-types).
7. For a standard audience, leave the box unchecked.
8. For an as-is audience, check the box. (**Note:** This option is available only to admins.)
9. Click **Save audience and proceed.**  
   The **Import** tab is displayed.
10. In the **Import using CSV** section, keep the default of **Add new devices/users** (since this is a new audience).
11. Select the CSV file to upload.  
    Wait for the confirmation message **Uploaded successfully.**
12. Click **Next.**  
    The **Connect** tab is displayed.
13. **(Optional)** Follow the instructions for <Anchor target="_blank" href="/marketers/id/docs/audiences-guide#connect-an-audience-to-media-partners">connecting an audience to partners</Anchor>.
14. Click **Done.**

Your audience is now visible in the Audiences dashboard, and it has been imported and connected to partners. Note, however, that the newly-imported audience list is not yet available for upload to partners since imported audiences are processed with a <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#eod">data freshness of daily</Anchor>.

**To update an existing audience using a CSV file:**

1. In the AppsFlyer left-side panel, go to **Engage** > **Audiences**.
2. Click on the name of the audience you want to update.  
   The **Edit audience** screen opens, with the **Define** tab displayed.
3. If you want to edit the audience name, you can do so here. Otherwise, select the **Import** tab to upload the new CSV file.
4. In the **Import using CSV** section, choose what to do with the uploaded list:
5. **Add new devices/users:** Add device/user identifiers to the existing audience
6. **Remove devices/users from existing audience:** Remove device/user identifiers in the uploaded list from the audience
7. **Overwrite existing audience with new devices/users:** Replace the entire audience with the uploaded list
8. Select the CSV file to upload.  
   Wait for the confirmation message **Uploaded successfully.**
9. Click **Next.**  
   The **Connect** tab is displayed.
10. Make changes to <Anchor target="_blank" href="/marketers/id/docs/audiences-guide#connect-an-audience-to-media-partners">partner connections</Anchor> for this audience if required.
11. Click **Done.**

Your audience has been updated using the CSV file. Note, however, that the revised audience list is not yet uploaded to partners since imported audiences are processed with a <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#eod">data freshness of daily</Anchor>.

### Error messages

| Message | Cause | What to Do |
| --- | --- | --- |
| There's a problem with the device list | One or multiple issues with the device list | Please check that the CSV file:<ul><li>is populated with devices and GAID/IDFA identifiers in the correct format</li><li>contains the required identifiers</li><li>contains a header row, with the headers in the correct format</li><li>has no blank rows</li><li>app\_id is populated with the correct app you use for Audiences</li></ul> |
| Seems like your device list is empty. Add some device IDs to it and try again | The CSV file is empty | Make sure that the CSV contains at least one device ID. |
| We couldn’t understand one or more of your device IDs. | <ul><li>The CSV format is incorrect</li><li>The file you uploaded is not a CSV file</li><li>The CSV file was edited and saved by a program other than a valid CSV editor (i.e. Microsoft Excel)</li><li>One or more device IDs is in the wrong format</li></ul> | <ul><li>Make sure that the CSV is in the required format.</li><li>Make sure that all device IDs are in the correct format.</li><li>If you used Excel, save the file as a CSV file described above.</li></ul> |
| Cannot use import v1 while applying user account policy on audience. | You have uploaded a CSV file for a [standard audience](/docs/audiences-import-audience-segments-from-internal-systems#imported-audience-types) using the V1.0 import structure. Standard audiences must be uploaded using a CSV in the V2.0 structure. | Edit the CSV file you are uploading to use the format, columns, and identifiers described above. |
| We just had a temporary connection problem and couldn’t upload your file. You can try again now. | Possible network error | Try uploading the CSV file again. |

</Accordion>

<div id="use-the-import-audience-api" />

<Accordion title="Use the Import Audience API">

The Import Audience API is used to either add or remove devices from an audience.

**To import a new audience using the API:**

1. In the AppsFlyer left-side panel, go to **Engage** > **Audiences**.
2. Click **New audience.**
3. Select **Import audience**.  
   The **Import audience** window opens.
4. Enter a unique **Audience Name.**  
   **Note:** Audience names can't include special characters (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)
5. Select the audience platform: **Android** or **iOS.**
6. Indicate whether this audience is a [**standard** audience or **as-is** audience](/docs/audiences-import-audience-segments-from-internal-systems#imported-audience-types).
   * For a **standard audience**, leave the box unchecked.
   * For an **as-is audience**, check the box (please note, this option is only available to admins). <Anchor target="_blank" href="/marketers/id/docs/audiences-user-identifier-policy#importing-audiences">Two additional consent fields</Anchor> are required when importing an "as is" audience in compliance with Google's enforcement of the Digital Markets Act (DMA) on March 6, 2024. Filling in these fields ensures maximum inclusion of users from the <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">European Economic Area (EEA)</Anchor> in your Google audiences.
7. Click **Save**.  
   The Import page is displayed.
8. In the **Import using API** section, keep the default of **Add new devices/users** (since this is a new audience).
9. Copy the API request URL from the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/audience-import-post">Import a new audience API</Anchor> page (the API token is already included).
10. Then copy and paste the API request body.
11. Click **Done**.  
    The **Connect** tab is displayed.
12. **(Optional)** Follow the instructions for <Anchor target="_blank" href="/marketers/id/docs/audiences-guide#connect-an-audience-to-media-partners">connecting an audience to partners</Anchor>.
13. Click **Done.**
14. Prepare the API request including the user/device identifiers, and POST it to AppsFlyer.

**To update an existing audience using the API:**

1. In the AppsFlyer left-side panel, go to **Engage** > **Audiences**.
2. Click on the name of the audience you want to update.  
   The **Edit audience** screen opens, with the **Define** tab displayed.
3. If you want to edit the audience name, you can do so here. Otherwise, select the **Import** tab.
4. In the **Import using API** section, choose what to do with the uploaded list:
5. **Add new devices/users:** Add device/user identifiers to the existing audience.
6. **Remove devices/users from existing audience:** Remove device/user identifiers from the existing audience.
7. Copy the **API request URL** from the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/audience-import-post">Import a new audience API</Anchor> page(the API token is already included). **Note:** Changing this option changes the endpoint path in the code to be copied. Be sure to use the correct endpoint for the action you are taking (in this and future API requests).
8. Then copy the **API request body.**
9. Click **Next.**  
   The **Connect** tab is displayed.
10. Make changes to <Anchor target="_blank" href="/marketers/id/docs/audiences-guide#connect-an-audience-to-media-partners">partner connections</Anchor> for this audience if required.
11. Click **Done.**
12. Prepare the API request including the user/device identifiers, and POST it to AppsFlyer.

**Note:** When importing via API, it will take 24 hours for the audience to update.

### Response codes

| Code | Message | Description |
| --- | --- | --- |
| 200 | The request was successful | Audience successfully imported |
| 400 | Invalid audience platform, this audience is already configured for Android/iOS. To use a different platform, please create a new audience in the UI | The platform specified in the request body doesn't match the platform specified when creating the audience |
| 400 | X or more of your rows do not contain an app id. You must attach an app id to each row. | Each row must contain an **app\_id**<ul><li>**Note:** app\_id is not required for an [as-is audience](/docs/audiences-import-audience-segments-from-internal-systems#imported-audience-types) that is imported using the V1.0 legacy import feature.</li></ul> |
| 400 | X or more of your rows does not contain a valid unique identifier | All or some rows do not contain at least one of the following identifiers in a valid format:<ul><li>For Android audiences: **gaid** OR **oaid** OR **imei** OR **cuid** OR **braze\_id** OR **amplitude\_id**</li><li>For iOS audiences: **idfv** OR **cuid** OR **braze\_id** OR **amplitude\_id**</li></ul> |
| 400 | Cannot process more than Y devices per request (n devices counted in this request) | The request body contains a list of more than 10,000 device IDs |
| 400 | Device list cannot be empty | The request body contains an empty list of devices<br /><br />You must provide at least one device ID per request |
| 400 | We couldn’t understand one or more of your device IDs | All or some device IDs are not in a valid format |
| 400 | X or more of devices to remove contain more than one identifier per device | A remove request was sent with more than one identifier per device |
| 403 | Forbidden | Unauthorized request: Incorrect or missing import key |
| 429 | Too many requests | Requests are limited to 350 per minute |
| 500 | Could not parse request | Invalid request body format (not the expected JSON structure or not a JSON)<br /><br />See the sample request above |

**API limitations**

* You can only add devices to one audience per request.
* You can only remove devices from one audience per request.
* You can send up to 10,000 device IDs per request.
* You can send up to 350 requests per minute.

</Accordion>

<div id="imported-audience-management-api" />

<Accordion title="Imported Audience Management API">

The <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-2">Imported Audience Management API</Anchor> allows advertisers to create and configure imported audiences, connect imported audiences to partners, upload imported audiences to partners, and more.

</Accordion>

<div data-zendesk-anchors="h_01HA4M61P4H5AVXQFA5ETABA67=why-import-audiences 01ECF4ZD0QQ5JJNH624D0E9WRF=examples h_01HA4M61P41RSJMKSJ2V9WJH8W=audiences-import-v20 h_01HA4M61P4TEBNF264RNFC57YP=imported-audience-types h_01HA4M61P4NVDJ393HA4V75PQV=important h_01HA4M61P4EEYGJNZ3N2D0KXS5=audience-import-procedures 01ECF4ZD0RHJAQ31NKFCX8QEWW=import-a-csv-file h_01HA4M61P4BJZKN97ZTT8TKRBK=identifier-hash h_01M45CYAAKF4MV0S3Z89NW6PQS=note confirmation-messages=error-messages h_01HA4M61P57TMZRK4XX7ARK896=error-messages h_01HA4M61P5XZR7C20Y5D3XX4K9=use-the-import-audience-api h_01HA4M61P5YGX4QP2PDSVW7D3G=response-codes h_01HA4M61P6CE4RBCVTA3KE15VN=imported-audience-management-api" />

---
title: "Import cost data"
excerpt: "Learn how to use Cost Import to upload or email CSV files containing campaign cost data to AppsFlyer ROI360."
x-zendesk:
  id: 360002516838
  url: https://support.appsflyer.com/hc/en-us/articles/360002516838-Import-cost-data
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Cost aggregation
  section_id: 6551029483281
  position: 4
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-maytav-avnat, Marketers, Agencies, ROI360, Ad Networks]
  labels: [Ad Network, Agency, Advertisers, Agencies, Premium, Premium Feature, Xpend, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2019-09-15T15:53:44Z'
  edited_at: '2026-08-05T10:36:56Z'
---
Cost Import, part of AppsFlyer ROI360, allows advertisers to get full and accurate coverage of their marketing cost by importing CSV files via upload or email.

## Overview

Use Cost Import to:

- Get campaign costs of any marketing activity (mobile campaigns, influencer campaigns, CTV, and more) to AppsFlyer. This is particularly important for media sources that don't report cost via API or on the attribution link.
- Retroactively overwrite and correct existing cost data.

Cost is reported via CSV files uploaded or emailed to AppsFlyer. Once AppsFlyer receives the file, the data is processed and becomes available in dashboards and reports within a few hours. This gives you a complete picture of your campaign costs and ROI.

> 📘 Note
>
> - Ad networks can import cost files for their customers if the relevant permissions are provided.
> - Agencies can't upload data. They can prepare their files and send them to the advertiser for upload.

## Procedures

To use Cost Import and send cost data to AppsFlyer, you need to:

1. [Prepare the CSV file](/docs/import-cost-data#prepare-csv-file-with-cost-data) with the cost data to send.
2. Send the file to AppsFlyer via either:
   - [Uploading](/docs/import-cost-data#email-file) it in the AppsFlyer UI.
   - [Email](/docs/import-cost-data#email-file). **Note**: For apps on CTV, PC, and console platforms, use only this method.

See the sections that follow for detailed instructions.

### Prepare CSV file with cost data

Advertisers, ad networks, and agencies can prepare the Cost Import CSV file. [See sample file](https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv)

**To prepare the CSV file**:

- Follow the file schema, format, and rules detailed in the following tables.

You can optionally include the ad network's reported clicks and reported impressions alongside your cost data. **Note**: If you use Excel or Google Sheets to create the file, follow the [Excel and Google Sheets formatting instructions](/docs/import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file).

#### CSV schema

| Column name <br />(case sensitive) | Format/remark | Example | Mandatory |
| --- | --- | --- | --- |
| date | - The date the cost occurred<br />- Format: String<br />  <br />  (Best practice):  - YYYY-MM-DD<br />  - YYYY/MM/DD<br />  - MM-DD-YYYY<br />  - MM/DD/YYYY<br />- Future dates not permitted<br />- **Best practice**: Use the same timezone as the one defined for your app in AppsFlyer.<br />- **Note**: Are you using Excel/Google sheets to prepare the file? [Read this](/docs/import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file). | - 2019-05-30<br />- 2019/05/30<br />- 5-30-2019<br />- 5/30/2019<br />- 05-30-2019<br />- 05/30/2019 | **✓** |
| app-id | - Format: String<br />- App ID as it appears in AppsFlyer.<br />- Multiple app IDs are allowed in a single file.<br />- All app IDs need to belong to the same advertiser account. | - com.app.name <br />- id12356789 | **✓** |
| media-source | - Format: String<br />- Media source name **exactly** as it appears in AppsFlyer. **Note:** Include the \_int suffix if relevant.<br />- Only one media source per file permitted. Multiple apps for the same media source are permitted. | network\_x\_int | **✓** |
| campaign | - Format: String<br />- Campaign name. If the campaign name appears in the ad network, the name in this file should match it (case sensitive).<br />- Don't use the same campaign name for multiple apps. | campaign\_a | **✓**<br />**Note**: If attribution data exists with both name and ID, the CSV must contain both to match. |
| spend | - Monetary cost<br />- Five digits allowed after the decimal point<br />- The value 0 (zero) is permitted<br />- **Note**:   - 1000 comma separators aren’t allowed, for example: "2,874.12".<br />  - Are you using Excel/Google sheets to prepare the file? [Read this](/docs/import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file). | 2874.12345 | **✓** |
| reported-clicks | - Format: Integer<br />- The number of clicks reported by the ad network.<br />- Whole numbers only. No decimals, comma separators, currency symbols, or scientific notation.<br />- The value must be 0 or greater. The value 0 is permitted. | 1200 | No |
| reported-impressions | - Format: Integer<br />- The number of impressions reported by the ad network.<br />- Whole numbers only. No decimals, comma separators, currency symbols, or scientific notation.<br />- The value must be 0 or greater. The value 0 is permitted. | 45000 | No |
| geo | - Format: String<br />- Two-letter country code compliant with [ISO 3166](https://www.iso.org/iso-3166-country-codes.html). **Note**: Make sure that you send 2 characters with no blanks.<br />- For the United Kingdom use UK,not GB. | US, CN, AU | No |
| currency | - Format: String<br />- Three-letter currency code compliant with [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html). **Note**: Make sure that you send three characters with no leading or trailing blanks.<br />- One currency code per app in the file allowed. Different apps can have different currency codes. | USD, GBP, EUR, JPY | No.<br />Will default to USD if left empty. |
| campaign-id | Format: String | abc1234def | No.<br />**Note**: If attribution data exists with both name and ID, the CSV must contain both to match. |
| adset | Format: String | my\_adset\_1 | |
| adset-id | Format: String | id5678ghi | |
| ad | Format: String | my\_ad\_name | |
| ad-id | Format: String | id91011jkl | |
| site-id | - Format: String <br />- Unique ID that identifies the publisher that displays the ad. [Learn more](/docs/about-link-structure-and-parameters#site-id-parameter) | id1213mno | No |
| channel | Format: String | video | No |
| keywords | Format: String | - better<br />- better you app<br />- better you online | No |
| agency | - Format: String<br />- The agency name. The value in the `af_prt` parameter.<br />- Only one agency can be included in a file, and only campaigns managed by that agency can be included in the file.<br />- The agency name is mandatory per row. No blank cells are allowed in the agency column.<br />- The agency must have permission to all the apps included in the file.<br />- Only advertisers can upload the file. Agencies can't upload data. They can prepare their files and send them to the advertiser to upload.<br />- If cost data is re-sent for the same dates and the agency name (`af_prt`) is included in a subsequent submission when it was absent in the original, this results in duplicated cost data. | AgencyName | No |

> 📘 Note
>
> Names with non-English characters must be encoded using UTF-8.

#### CSV format and rules

| Rule | Requirement |
| --- | --- |
| Prohibited characters | Fields in string format can't have `=`, `+`, `-`, or `@` as the first character. For example, `@example_campaign` or `=123` are prohibited. |
| App owner | One advertiser (app owner) per file permitted. Multiple apps from the same advertiser account are permitted. |
| Filename extension | CSV Example: abc123.csv |
| File structure | - **Format**: Files have a CSV format meaning that each column is separated by a comma.<br />- **Header row**: The first row is a header row that matches the schema<br />- **Data rows**: Contain the mandatory columns. **Note**: Make sure that there are no trailing blanks in your data. For example, [USD] (a blank follows the **D** should be changed to [USD].<br />- **Blank rows**: Not permitted<br />- **Duplicate rows** having the same key: Not permitted. The key is derived from using the mandatory fields.<br />- **Blank cells:** Empty values are not allowed in the file. If you do not want to upload certain fields, they should not be in the file. |
| Advertising hierarchy | Cost must be recorded at the campaign level with other dimensions in the advertising hierarchy being optional.<br />Any partial data that is uploaded at a lower hierarchy will override all data from the campaign level down.<br />**For example:** If you import a file with campaign cost for adset 1, and separately import another file for adset 2 of the same campaign, the total cost of the campaign will be replaced and show only adset 2 data. For total campaign cost, the file you import needs to include adset 1 and adset 2. |

### Upload file

Advertisers and ad networks can upload Cost Import CSV files.

**Prerequisites**: Ad networks require [Cost Import permission from the advertiser](/docs/import-cost-data#cost-import-permissions-for-ad-networks).

**To upload the CSV file via the AppsFlyer UI**:

1. In AppsFlyer, from the side menu, select **Settings** > **Cost Import.**

The Cost Import page displays.
2. Click **+ Import cost file**

The Import cost window opens.
3. Drag the CSV file to the **Import cost file** window.

Processing file message displays.
4. If an error message displays during upload, rectify the error and repeat the relevant steps.
5. The **Cost Import: file summary** window opens.
6. Do one of the following:
   - Abort the upload, click **Cancel import**.
   - Complete the import process, click **Import file.**

     The message, All set! displays.
   - If an error message displays, follow the [error message instructions](/docs/import-cost-data#error-messages-and-solutions).
7. Click **Import another file** or **Done**.

### Email file

Advertisers and ad networks can email Cost Import CSV files.

**Prerequisites**:

- **Advertisers**: 
  - Sender email must be for a registered AppsFlyer user.
- **Ad networks**:
  - Sender email must be for a registered AppsFlyer user.
  - [Cost Import permission from the advertiser](/docs/import-cost-data#cost-import-permissions-for-ad-networks).

**To send the CSV file by email**:

1. Get the [token for email import](/docs/import-cost-data#token-for-email-import).
   1. In AppsFlyer, from the side menu, select **Settings** > **Cost Import.**
   2. In the upper right-hand of the page, click **Token for email import.**
   3. Copy and save the token.
2. Compose the email with the following fields:
   - **To**: `adspend-upload@appsflyer.com`
   - **CC:** **Users who should get a copy of the automatic feedback**
   - **Subject**: Paste the token for email import in the subject field.
   - **Attachment**: CSV file with the data.
3. Send the email.
   - Once the file is received and processed, a status email summarizes the details, issues, or errors found during processing. The email is sent to all parties on the submission email and to the advertiser admin. Where errors are identified, follow the [error message instructions](/docs/import-cost-data#error-messages-and-solutions).
   - You can view the status of files submitted on the [Cost Import dashboard](/docs/import-cost-data#error-messages-and-solutions)

## Dashboard

The Cost Import dashboard lets you upload files and view details of previously uploaded files.

### Cost Import dashboard

To view the Cost Import dashboard, in AppsFlyer, from the side menu, select **Settings** > **Cost Import**.

Details about the information available for previously imported files are described in the following table.

| Column name | Description |
| --- | --- |
| CSV file name | The name of the cost files imported to AppsFlyer. |
| Upload date | Date file was imported. |
| Media source | Media source included in the file. |
| Date range | First and last dates in the file in which ad spend occurred. |
| Matched rows (%) | The percentage of rows in the file where cost was matched to attribution. [Learn more](/docs/import-cost-data#matched-rows) . |
| Status | The status of the imported file:<br />- **Success**: Action completed successfully. Cost is recorded and available in AppsFlyer dashboards and reports.<br />- **Validation error**: AppsFlyer system problem. Wait 10 minutes and try again. If it fails again, contact AppsFlyer support.<br />- **No permissions**: The token is not approved for this app. - Advertisers: Make sure the app ID is correct.<br />  - Ad networks: Confirm with the advertiser that they've given you Cost Import permission.<br />- **Reverted**: Action completed successfully. File was overwritten/replaced by other data. |
| Action | - At the file level: If you have app permissions to all the apps contained in the file, you can:<br />  - **Download CSV file**: This a copy of the imported CSV file.<br />  - **Download unmatched report** for all apps in the file. See the Matched rows section of this table to learn more.<br />- At the app level: If you click a specific file, information about all Cost Imports for the app displays, from that specific file, as well as other files. If you have app permission for the app you can:<br />  - **Download app data.**<br />  - **Download unmatched report** for the app<br />  - **Revert**(cancel) the Cost Import for the selected app. |

### Matched rows

Row matching is the process where the cost reported by import is matched with attribution data recorded in AppsFlyer. This is done using all dimension names (not IDs) available, such as media source, campaign, adset, ad, etc. If they all match, the rows are designated as is-matching=TRUE.

Cost is recorded and available in AppsFlyer dashboards and reports regardless of matched status.

The percentage of matched rows displays on the Cost Import dashboard. If unmatched rows are unexpected or the number of matched rows (%) is higher than expected:

- Download the Unmatched report to investigate the cause. The Unmatched report contains a column "is-matched" which can have a value of TRUE (matched) or FALSE (unmatched) rows.
- If necessary, cancel the import by reverting it.
- See the Action section of this table for details.

## Additional information

### Using Excel or Google Sheets to prepare CSV file

When using Excel or Google Sheets to prepare the CSV file, the date and spend columns need to be formatted correctly before you save the file as a CSV file. After you save the CSV file, verify that the content is formatted correctly. Use the following guidelines to:

- Format the date cells.
- Format the spend cells.
- Verify the content format.

#### Format date cells

**To format date cells in Excel with the format YYYY-MM-DD**:

1. Select the cells to be formatted.
2. Right-click and then select **Format cells**.

The format cells window opens.

<Image src="https://files.readme.io/43d0f370f299d73b8ce93fec1c912cb7525d0071db779a64a58f5917df2a5531-360004042458.png" alt="Format date cells in Excel" />

3. Select **Custom**.
4. In the Type field, enter **YYYY-MM-DD**
5. Click **OK**.

The date is formatted.

#### Formatting spend cells

Excel usually formats value cells with a comma to separate the thousands, as shown in the following image. This format isn't suitable for Cost Import files.

<Image src="https://files.readme.io/d54e21ddd937dfe25a33bb96193761a5a724c22a35a55bb7d71eb03a6433d7ed-360003949177.png" alt="Excel thousands separator example" />

**To format spend cells without a 1000 comma separator**:

1. Select the cells to be formatted.
2. Right-click and then select **Format cells**.

The format cells window opens.
3. Select **Number**.

<Image src="https://files.readme.io/d2bfeec87d24739e9d1cea8467d7ce23b56aa9414a96202379f6e774991bf387-360004075458.png" alt="Format cells as number in Excel" />

4. Clear **Use 1000 separator (,).**
5. (Optional) Set the number of **Decimal places**. The default is 2. The maximum permitted is 5.
6. Click **OK**.

The cells are formatted correctly.

#### Verify content format

**To verify the content format**:

1. Use an editor to view the file.
   - Windows: Notepad, Notepad++
   - macOS: TextEdit
2. Pay special attention to the following:
   - **Blank spaces:** Make sure that there are no leading or trailing blank spaces before or after the commas that separate the fields. In Excel, use the @trim command to remove blank spaces.
   - **Date:** Make sure that the date cells have the format YYYY-MM-DD.
   - **Spend:** Make sure there are no commas in the spend cells.
   - **Delimiters**: Must be commas. If they are semi-colons:     - This may occur when your computer's regional settings are set to a language/region that's not English, especially German.
     - The solution differs depending on your computer operating system (macOS or Windows).
     - To resolve this issue, search for the latest guidance from [Microsoft](https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010) or other forums. Use the following search terms: Operating system (macOS or Windows) Excel change delimiter for CSV files.

The following image contains a screenshot of the [sample CSV file](https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv) displayed in an editor.

<Image src="https://files.readme.io/1398c5e9bad7a46b697e3b21030e64d656162e33a4a63f39475c64993bbe7a72-360003996197.png" alt="Sample CSV file in text editor" />

### Token for email import

The token for email import is used to verify that the email sender is authorized to submit the Cost Import file.

Advertiser and ad network tokens are different:

- Advertiser token:  - The same token is valid for all apps in the account.
  - Any account user can get the token.
- Ad network token:  - The same token is used for all advertisers.

Advertisers and ad networks shouldn't share their tokens with each other!

### Cost Import permissions for ad networks

Ad networks require advertiser permission per app to access Cost Import.

**To grant an ad network Cost Import permission:**

1. In AppsFlyer, the **advertiser** needs to go to the side menu and select **Collaborate** > **Active Integrations.**

The Integrated Partner page displays.
2. Select the integrated partner.
3. Go to the **Permissions** tab.
4. Enable **Ad Network Permissions** if it is not already so.
5. (optional) Add account users.
6. Enable **Use Cost Import.**
7. Click **Save permissions**.

## Troubleshooting, traits, and limitations

### Error messages and solutions

The following table lists all possible Cost Import error messages and corresponding solutions.

| Error message | Description | Solution |
| --- | --- | --- |
| None of the app IDs provided in the file exist in AppsFlyer. Please verify the correctness of app IDs. | App ID does not exist in the account. | Change app ID and resubmit. |
| Line [line name] has the wrong number of columns. Expected [number] columns, received [number] columns. | All columns in the file must have a value. | Change the values populated in the file based on the headers you defined. |
| Missing 'media-source' in file header. | - File header is missing media- source.<br />- The column name needs to be exactly as it is in the scheme. | Add media-source as a header name. |
| The file can contain only one media source. Multiple media sources encountered in the file: [number of media sources]. | The file contains more than one media source. Hidden empty lines or malformed rows in the CSV can also trigger this error, even if they aren't visible in Excel. | Open the file in a text editor, such as Notepad++, and remove any empty lines or malformed rows. Save the file and upload it again. If the file contains more than one media source, split it into one file per media source. |
| The value provided [value] for [field] is not a valid value for this column. | Data format in the column is incorrect. For example, the date is dd-mm-yy instead of yyyy-mm-dd. | Correct the format and resubmit. |
| Multiple currencies identified for the app. Please use a single currency for each app in the file. Encountered currencies: %number of currencies%. | Only one currency can be used for an app. | Use one currency in the upload and resubmit. |
| The following columns in the file header are not supported: [file headers] | File header does not match the scheme. Meaning, the column name needs to be exactly as it is in the scheme. | Remove the unsupported columns and resubmit. |
| Missing required columns in file header: [file headers] | File header is missing a mandatory column. | Add the missing column and its values and resubmit. |
| The app contains a future date: [date] | Future dates are not allowed. | Correct the date to today's date or earlier, and resubmit. |
| The file is empty. There is no data to process. | The file is empty. | Populate data in the file and resubmit. |
| The following two rows conflict due to identical dimensions. Please provide a single row of spend per set of dimensions. [conflicting rows] | There is more than one row with the same key (mandatory) fields. | Remove the duplicate rows and resubmit. |
| The file can contain data only from a single advertiser account. Different advertisers encountered in file: [advertiser names] | For partners, an upload cannot be for more than one advertiser. | Split the upload into one file per advertiser. |
| The app [app ID] doesn't exist in the account. Please verify the app ID. | App ID does not exist. | Correct the app ID and resubmit. |
| Geo (country) code was not found for app [app ID]. Use an ISO 3166 2-letter code | Geo does not exist. | Correct the geo and resubmit. |
| Currency code was not found for app [app ID]. Use an ISO 4217 3-letter code. | Currency does not exist | Change the currency to a valid currency and resubmit. |
| There were validation errors for one or more apps in the file. Please review the file information for more details. | There is more than one error in the file. | Download the file and review for errors. |
| There was an internal error processing the file, please try uploading it again. | - Backend issue processing the file.<br />- Typically a temporary issue. | Wait 1 hour and upload again. |

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| Ad networks | Supported.<br />Exceptions:<br />- Meta Ads<br />- X Ads<br />- ASA |
| Agencies | - Agencies can't upload data. They can prepare their files and send them to the advertiser to upload.<br />- The CSV files must contain an Agency column with the agency name (the agency name is the value in the af\_prt parameter). [See CSV schema](/docs/import-cost-data#ad-spend-csv-schema) |
| Agency transparency | Not supported |
| App-specific timezone | Supported |
| App-specific currency | Supported. Campaign costs are converted to the app-specific currency. |
| Campaign name | The same campaign name can't be used for multiple apps, or the cost of one app will apply to both. |
| Field names | If field names in the campaign hierarchy do not match the field names as they appear in the attribution data, they will be counted separately. <br />For example, if the campaign names do not match, then even though the campaign IDs are the same, they will be counted as different campaigns. |
| File size | When uploading a CSV Cost Import file the size limit is:<br />- Via AppsFlyer dashboard: 2 MB<br />- Via email: 5 MB per file |
| Organic data | Supported |
| Non-organic data | Supported |
| Data freshness | [Ad spend](/docs/about-data-freshness-and-timezone-support#intraday-during-the-day) |
| Historical data | Supported. Cost reported can be reverted, and corrected data submitted, for up to 90 days. |
| Retargeting | Not supported. |
| Account user access | Not available for users with geo or media source restrictions. |

#### See also

<Cards>
  <Card title="Attribution link structure and parameters" href="/docs/about-link-structure-and-parameters" icon="fa-solid fa-link">
    Learn about the parameters and structure used in AppsFlyer attribution links.
  </Card>
</Cards>
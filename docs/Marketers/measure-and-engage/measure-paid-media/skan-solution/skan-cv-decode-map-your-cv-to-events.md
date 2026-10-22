---
title: SKAN CV decode (map your CV to events)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-26T20:31:40Z'
  edited_at: '2025-04-11T00:01:03Z'
  id: 360014696297
  locale: en-us
  section: SKAN solution
  section_id: 6552135379985
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360014696297-SKAN-CV-decode-map-your-CV-to-events
---
> **At a glance:** AppsFlyer decodes and transforms the conversion value set by you into events. The events are used to populate the SKAN dashboard, raw data, and postbacks to partners.

![SKAdNetwork_-_Custom__1_.png](https://files.readme.io/74f0d3836ee6a73f6746afa2d6d6a468c09cba696561c5a2075149ca360b78bf-34255690318097.png)

## Decode SKAN conversion value

Advertisers use conversion value decode as an alternative to using options available in <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">Conversion Studio</Anchor>. If you use Decode, it means you are responsible for setting <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/4097267-updatepostbackconversionvalue">updatePostbackConversionValue</Anchor> according to your app logic.

Apart from setting the conversion value (CV) in the app, the remainder of the flow, features, and reporting options are the same as those described in the <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide">SKAN solution guide</Anchor>. This means that at the expiry of the activity window (controlled by you), iOS sends the postback to the ad network, which forwards it to AppsFlyer. AppsFlyer decodes the CV according to your mapping into events processed just like decoded CVs set by the SDK.

## Custom conversion value—Decode

Implementing custom CV decode requires uploading a CSV file containing your CV mapping to the AppsFlyer platform.

**Decode mapping principles**

* Provide decode mapping for fine conversion values (1-63), and coarse conversion values (low, medium, and high) for windows 1-3. It's not mandatory to map the entire range of values. For example, you can map values 1, 2, 10, and 43.
* CV 0 is always mapped to install. You can't set it.
* The mapping table is uploaded to AppsFlyer in a CSV file. You can upload an updated mapping table as needed.
* Upon receiving a postback from iOS, the CV is decoded into events, as illustrated in the examples.
* The install time is derived using the postback arrival time.
* Events have the same time as the install time.
* To best understand how to prepare the schema, review the mapping scenarios that follow.
* <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#custom-events">Custom in-app events</Anchor> names are allowed.
  * Meaning you send new event names, even if they haven't ever been sent by the SDK.
  * You can map the in-app events to ad network in-app events.
  * This is also true for Meta ads integration, subject to Meta-specific rules detailed in the next section.

<div id="decode-mapping-scenario-rules" />

<Accordion title="Decode mapping scenario rules">

Consider:

* Fine conversion value range: 1-63
* Coarse conversion value range: Low, medium, and high
* A given conversion value maps to one or more in-app events specified by you. In-app events have optional parameters.
* For the examples: Assume that the install date is Feb 1 at 08:00.
* The table that follows is an example decode mapping table. Its structure is similar to that of the CSV file required. Following the table are the events generated as a result of the decoding process.
* An install event is always generated, irrespective of your mapping.
* Revenue measurement:
  * Revenue is in USD.
  * A given conversion value has a revenue range bounded by  min\_revenue and max\_revenue.
  * In aggregated reports and dashboards, revenue is calculated as the average of the range. Example: min\_revenue=4 and max\_revenue=10. The calculated revenue is 7.
  * Raw data reports include the calculated revenue (skad\_revenue), min\_revenue, and max\_revenue.

#### **Meta-specific rules**

If you integrate with Meta ads, adhere to the following rules:

* Min and max revenue values for a given conversion value must be different. Meaning not equal.
* Values mustn't overlap and must be in consecutive order as illustrated for conversion\_value 1-2 and 62 in the table that follows.
* event\_counter: Meta ads doesn't consider this value. [Best practice] Populate it with a value of 1.

### Example: Decode mapping

| conversion\_  <br />value | event\_  <br />name | event\_  <br />value | min\_revenue<br /><br />(not -inclusive) | max\_revenue (inclusive) | event\_  <br />counter | hours\_from\_  <br />install |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | af\_purchase | `{abc}` | 0 | 3 | 1 | 24 |
| 2 | af\_purchase | `{def}` | 3 | 10 | 3 | 36 |
| 21 | event\_a |  |  |  | 1 | 24 |
| 21 | event\_b |  |  |  | 3 | 24 |
| 21 | event\_c | `{xyz}` |  |  | 2 | 24 |
| 21 | event\_d |  |  |  | 1 | 24 |
| 21 | event\_e |  |  |  | 1 | 24 |
| 21 | event\_f |  |  |  | 1 | 24 |
| 21 | event\_g |  |  |  | 1 | 24 |
| 62 | af\_purchase | \{fgh) | 10 | 17 | 2 | 72 |
| 62 | event\_a | `{klm}` |  |  | 3 | 72 |

### Example A: Fine conversion value 1

| event\_name | skad\_revenue | min\_ revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 1.5 | 0 | 3 | `{abc}` |

### Example B: Fine conversion value 2

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 6.5 | 3 | 10 | `{def}` |
| af\_purchase | 6.5 | 3 | 10 | `{def}` |
| af\_purchase | 6.5 | 3 | 10 | `{def}` |

### Example C: Fine conversion value 21

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| event\_a |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_c |  |  |  | `{xyz}` |
| event\_c |  |  |  | `{xyz}` |
| event\_d |  |  |  |  |
| event\_e |  |  |  |  |
| event\_f |  |  |  |  |
| event\_g |  |  |  |  |

### Example D: Fine conversion value 62

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 13.5 | 10 | 17 | `{fgh}` |
| af\_purchase | 13.5 | 10 | 17 | `{fgh}` |
| event\_a |  |  |  | `{klm}` |
| event\_a |  |  |  | `{klm}` |
| event\_a |  |  |  | `{klm}` |

</Accordion>

<div id="ssot-support-for-decode-mode" />

<Accordion title="SSOT support for Decode mode">

#### Overview

Decode mode customers can now access SSOT (Single Source of Truth) attribution, bringing deduplication benefits previously available only to encode mode users. This improves non-organic performance measurement without requiring encode mode implementation.

#### Key Benefits

* Retrieve a real-time indication via an API on whether an install is attributed (non-organic) or not (organic) by AppsFlyer.
* Reflect the SSOT attribution signal when updating conversion values.
* Use SSOT-compatible decode schemas by uploading updated schema files with a special SSOT flag.
* Access SSOT dashboards and DataLocker reports.
* Deduplicate non-organic installs across networks.
* Enable more accurate attribution and reporting.
* Reduce development and QA complexity.

#### How to Enable SSOT for Decode Mode

1. **Extract the AppsFlyer ID -** <Anchor target="_blank" href="/marketers/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id">Retrieve the AppsFlyer ID from the SDK at install time</Anchor>.
2. **Query the SSOT API -** Use the AppsFlyer ID and App ID to check if the install was attributed by AppsFlyer.
   * API returns:  
     `"is-non-organic-install": true/false`
3. **Apply the attribution signal -** Use this signal to adjust your CV logic. For example, reflect attribution by adding an `af_attribution_flag` event to the relevant CV entries.
4. **Upload updated schema file -** [Use your existing decode schema](/docs/skan-cv-decode-map-your-cv-to-events#decode-mapping-scenario-rules). For CVs affected by SSOT attribution, add the `af_attribution_flag` event to indicate deduplication.
5. **Access reports**  
   SSOT dashboards and DataLocker files now include decode mode data.

#### FAQ

**Q: When should I query the API to get the SSOT attribution flag?**  
**A:**

* Query the API immediately after installation.
* Re-query every 10 seconds (up to 5 times) to account for attribution delay.
* Alternatively, query once at least 25 seconds after install to ensure accuracy.

</Accordion>

<div id="zd-decode-csv-file-specification" />

<Accordion title="Decode csv file specification">

Conversion values are mapped to one or more in-app events.

**File rules**

* Format: CSV file
* Maximum number of rows: 640 + header row; total 641.
* The header row  must include all the column names exactly as they display here. Best practice: Use the example file attached as a template. See sample decode CSV files for <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=0&single=true&output=csv">SKAN 3</Anchor> and <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=1187444449&single=true&output=csv">SKAN 4</Anchor>.
* Don't use the following characters as the first character in a column: `=`, `+`, `-`, and `@` (edited).

### Decode csv file specification

| Column | Mandatory value | Content | Details |
| --- | --- | --- | --- |
| conversion\_value | Yes, for:<ul><li>SKAN 3 and below</li><li>SKAN 4 where postback\_sequence\_index is 0</li></ul> | Integer value 1–63 | The same fine conversion value can be listed more than once. See the examples for further explanation. |
| coarse\_conversion\_value | Relevant only for SKAN 4 | String:<ul><li>low</li><li>medium</li><li>high</li></ul> | The same coarse conversion value can be listed more than once. |
| event\_name | Yes | String | In-app event. It does not have to be an event that already exists in AppsFlyer.<br /><br />Note! In-app event names are case-sensitive.<br /><br />[Best practice]: Event name for revenue af\_skad\_revenue. |
| event\_value | No | String | String set by the developer containing data to be decoded by the advertiser in their systems. Typically this is in the format of a JSON. |
| min\_revenue | No | Integer or  floating | Use the min\_revenue and max\_revenue to set a revenue range in USD.<ul><li>If you don't want to associate revenue with a conversion value, set min\_revenue and max\_revenue to blank.</li><li>The value set in min\_revenue is not inclusive. Meaning greater than 0. Similar to 0.0001</li><li>The value set in max\_value is inclusive.</li><li>Example: If min\_revenue is 0 and max\_revenue is 4, this means the range is 0.0001-4</li><li>max\_revenue must be greater than min\_revenue</li></ul>**Note!** If you generate the file using Excel, before saving, change the column format to comma and not currency to avoid Excel embedding a $ symbol in the CSV file. |
| max\_revenue | No |  | If you populate min\_revenue: max\_revenue must have a value greater than 0.<br /><br />See min\_revenue for the explanation. |
| event\_revenue\_usd | No |  | Deprecated starting June 7, 2021. Use min\_revenue and max\_revenue |
| event\_counter | Yes | Integer | <ul><li>Number of times the event is duplicated on decoding. Typically it represents the number of times the user performed a given action.</li><li>Minimum value 1.</li></ul>Example: If the user performed a given event 5 times, then 5 events are generated.<br /><br />Considerations: If you send revenue, the total USD amount reported is multiplied by the value in event\_counter. Meaning if min\_revenue = 0, max\_revenue = 3, and event\_counter = 4 the total revenue reported 1.5 X 4 = 6.<br /><br />See the examples. |
| hours\_from\_install | Yes | Integer | <ul><li>Hours elapsed since the install</li><li>Minimum value: 1</li><li>Maximum value: 1512 (63 days)</li><li>The value for all rows of a given conversion\_value must be identical. Meaning different values for different conversion values is permitted.</li></ul>AppsFlyer uses this to derive and set the install date as follows:<ul><li>If the postbacks are SKAN V4, the install date formula is: Install date = postback arrival time - [accumulated window length] - [average postback delay].<ul><li>Postback 1: install date = postback arrival time - 48h - 36h</li></ul></li><li>If the postbacks are SKAN V3, the install date formula is: Install date = postback arrival time - 36 hours - [average last-active range].<ul><li>The default [average last-active range] is 12 hours.</li><li>For a conversion value of 0, the average last-active range is set to 0.</li></ul></li></ul> |
| postback\_sequence\_index | Yes, but only relevant for SKAN 4 | Integer:<ul><li>0</li><li>1</li><li>2</li></ul> | For fine value, only the value of 0 can be received. |

</Accordion>

<div id="upload-conversion-value-schema-file" />

<Accordion title="Upload conversion value schema file">

**Before you begin**:

* Prepare the conversion value schema CSV file.
* If you integrate with Meta ads and measure revenue, verify that your schema complies with [rules relating to Meta.](/docs/skan-cv-decode-map-your-cv-to-events#meta-specific-rules) If you don't, Meta ads can't interpret the schema.

**To enable SKAN measurement using decode measurement:**

1. In AppsFlyer, go to **Settings** > **SKAN Conversion Studio.**
2. Click options (⋮), select **Upload decode mapping file**.
3. If you haven't yet upgraded to SKAN 4, choose to upload a file for SKAN 4 or pre SKAN 4. Once you upgrade to SKAN 4, the choice for other versions is unavailable.
4. Do one of the following:
   * **Click Drag & drop file.**
   * **Upload updated mapping file.**
5. Follow the instructions in the user interface to upload the file.
6. Turn on **SKAN measurement.**
7. Click **Save changes.**   
   Note: For the next 48-72 hours, data in the dashboard is ambiguous. Meaning due to iOS timer issues, we can't be sure if the decode mapping matches the encode mapping used by you.
8. Ensure that you have mapped your in-app events to those used by partners so that they can consume postbacks correctly.

</Accordion>

## Troubleshooting the CSV upload errors file

<div id="upload-error-messages" />

<Accordion title="Upload error messages">

One or more values in the file don't match the required format: The file format was changed starting June 7, 2021. Verify that your file format matches the example in this article.

</Accordion>

<div id="using-excel-to-format-the-event_revenue_usd-column" />

<Accordion title="Using Excel to format the event_revenue_usd column">

When using Excel/Google sheets to create a CSV file, the event\_revenue\_usd column must be formatted correctly before saving the file as a CSV file.

After saving the CSV file, verify that the content is formatted correctly. **Note**: Don't use Excel to do the verification; rather, use an [editor](/docs/skan-cv-decode-map-your-cv-to-events#visual-inspection-of-the-csv-file-without-excel).

#### Formatting event\_revenue\_usd cells in Excel

Excel usually formats value cells with a comma to separate the thousands, as shown in the figure. This format is not suitable for upload CSV files. You must also remove the $ symbol.

![mceclip0.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

You can correct this by formatting the cells in Excel.

**To format the spend amounts without a 1000 comma or $ symbol:**

1. Select the cells to be formatted.
2. Right-click, select **Format cells**.  
   The format cells window opens.
3. Select **Number**.  

   <Image alt="Formatnumbers.png" src="https://files.readme.io/4c1b61d1eae9149e818d4cc9793128fbdaafed5daed9acf6cbc503571475cc0e-34255643022481.png" width="381px" />

1. Clear **Use 1000 separator (,).**
2. (Optional) Set the number of **Decimal places**. The default is 2. The maximum permitted is 5.
3. Click **OK**.  
   The cells are formatted correctly.

</Accordion>

<div id="visual-inspection-of-the-csv-file-without-excel" />

<Accordion title="Visual inspection of the CSV file without Excel">

To examine the content of the CSV file, use an editor to view the file.

* Windows: Notepad, Notepad++
* macOS: TextEdit

The following contains a screenshot of the <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?output=csv">example CSV file</Anchor> displayed in an editor.

**Editor view**

![SKCustomeEditor.png](https://files.readme.io/d8677e9967a70db32e8d04c4ee835bd477b18c1cb464a9cd0e593f72ce3f3c15-34255690323217.png)

Using an editor, examine the CSV file. Pay special attention to the following:

* **Blank spaces:** Ensure that there are no leading or trailing blank spaces before or after the commas that separate the fields. In Excel, use the @trim command to remove blank spaces.
* **event\_revenue\_usd:** Ensure that there is neither a comma nor a $ symbol in the event\_revenue\_usd column.  

  ![mceclip1.png](https://files.readme.io/160d89f313b98a83ad6b214de8fd02a290fb1c26563b6dd3c6f0a8a7a93ef3d1-34255690324881.png)

</Accordion>

<div id="csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

<Accordion title="CSV files generated by Excel don't have commas as delimiters">

If Excel creates CSV file with a semi-colon ";" or other characters as a delimiter but not a comma:

* This occurs when your computer's regional settings are set to a language/region that is not English.
* This issue is particularly prevalent when German is selected in the regional settings.
* The solution differs depending on your computer operating system (macOS or Windows).
* To resolve this issue, search for the latest guidance from <Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor> or other forums to revolve. Use the following search terms: *Operating system (macOS or Windows) Excel change delimiter for CSV files.*

</Accordion>

<div data-zendesk-anchors="h_01HAMKKCKJEGCDPN5P8J6X0E8E=decode-skan-conversion-value custom-conversion-value%E2%80%94decode=custom-conversion-valuedecode h_01HAMKKCKJ5K6J6NNPF394ZK61=custom-conversion-valuedecode h_01HAMKKCKJT7MA03SHT4X3MH4W=decode-mapping-scenario-rules facebookspecific-rules=meta-specific-rules h_01HAMKKCKJDCEKCNZFSF0V6KH8=meta-specific-rules h_01HAMKKCKJ5B7W8FGK01QCKN7Y=example-decode-mapping example-b-conversion-value-1=example-a-fine-conversion-value-1 h_01HAMKKCKJ1ZRH00A7Q4HZ4BBK=example-a-fine-conversion-value-1 example-b-conversion-value-2=example-b-fine-conversion-value-2 h_01HAMKKCKJZBASWWM1VD0VXWBX=example-b-fine-conversion-value-2 example-c-conversion-value-21=example-c-fine-conversion-value-21 h_01HAMKKCKJ4YHMQENKNVPMV4KC=example-c-fine-conversion-value-21 example-d-conversion-value-62=example-d-fine-conversion-value-62 h_01HAMKKCKJP7V7D26MGM1WVDTE=example-d-fine-conversion-value-62 h_01JQX7MY9QRH71M4S6W9CKCQ5Z=ssot-support-for-decode-mode h_01JQX7NZD3KBYTBJMS2VEMK1MT=overview h_01JQX7PPSRCZXNTH890PP5TD1Q=key-benefits h_01JQX7QKV73WT10Q8QG0DKSB4S=how-to-enable-ssot-for-decode-mode h_01JQX8JC023CMFSD1T6N60YHR8=faq decode-csv-file-specification=zd-decode-csv-file-specification h_01HAMKKCKKJFRTXYJNWZNGF97V=zd-decode-csv-file-specification decode-csv-file-specification::d6a1f3f1=decode-csv-file-specification h_01HAMKKCKK7G7VP6SDEHBH6383=decode-csv-file-specification h_01HAMKKCKKN7WDP6F5E4W91HQJ=upload-conversion-value-schema-file h_01HAMKKCKK0QQ8AS8FZ83MZ8FH=troubleshooting-the-csv-upload-errors-file h_01HAMKKCKK3B2T9VSTYCVE0017=upload-error-messages h_01HAMKKCKKFJAE4B88QV00HYPW=using-excel-to-format-the-event_revenue_usd-column h_01HAMKKCKKKVYCWCQCAEMSBMF7=formatting-event_revenue_usd-cells-in-excel h_01HAMKKCKK39C9SP7K86ER3HZK=visual-inspection-of-the-csv-file-without-excel h_01HAMKKCKK9GEBC64JE4DSDAMQ=csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

---
title: Data Clean Room—Creating In-app event reports
metadata:
  keywords:
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
  created_at: '2022-09-22T12:03:40Z'
  edited_at: '2024-07-22T12:05:41Z'
  id: 9312610473233
  locale: en-us
  section: Data Clean Room
  section_id: 4591191779217
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/9312610473233-Data-Clean-Room-Creating-In-app-event-reports
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Create In-app event reports to focus on user activity occurring after an app has been installed. Extract specific event parameters from your in-app event raw data, optionally match the data with custom sources, then process and present it in aggregated form.

<div id="creating-an-in-app-event-report" />

## Creating an In-app event report

**To create an In-app event report, follow the steps detailed in the tabs below.**

**Note:** These steps are divided into tabs for ease of reading. All steps must be completed in order to create the report. *(Certain steps, as indicated, are not relevant for reports that don't use custom sources.)*

<div id="perform-preliminary-steps" />

<Accordion title="Perform preliminary steps">

1. Go to the **Reports** tab of the **DCR.**
2. Click the **+ New report** button.
3. Select **In-app events** as the type of source data, then click **Next** in the bottom right corner of the screen.
4. Enter a name for the report.
   * This can be any name that will help you identify the report in the DCR platform.
   * **Important!** Ensure that the report name is different from all other reports in your account or you will not be able to [save the report](/docs/data-clean-room-creating-in-app-event-reports#configure-report-settings-and-save-the-report).
   * Report name requirements:
     * Length: 2-80 characters
     * Valid characters:
       * letters **(A-Z, a-z)**
       * numbers **(0-9)**, *cannot be the first character of a name*
       * a hyphen (-), *cannot be the first character of a name*
     * Invalid characters:
       * spaces
       * all other symbols or special characters

</Accordion>

<div id="select-sources" />

<Accordion title="Select sources">

Specify the source data to be used for the report:

<div id="in-app-event-sources" />

#### **In-app event sources**

* **Apps:** Select one or more of the apps in your AppsFlyer account.
* **Timeframe:** Select the number of days of historical data you want the DCR to search for in-app events (from 1 to 30 days).
* **Events:** Select one or more in-app events to include in the report.
  * The available events include all in-app events **from the selected apps** that have been configured to report data to AppsFlyer via the SDK or the server-to-server API (S2S).
* **Source types:** Select one or more types of in-app event data:

| Installs | In-app events related to install attributions<ul><li>An install is recorded when a user downloads, installs, and launches a mobile app.</li></ul> |
| --- | --- |
| Re-engagements | In-app events related to re-engagements<ul><li>A re-engagement is recorded when an inactive user of a specific app engages with a retargeting campaign for the app and subsequently launches it.</li></ul> |
| Reattributions | In-app events related to re-attributions<ul><li>A re-attribution is recorded when a former user of a specific app (who had uninstalled it) engages with a retargeting campaign for the app and subsequently reinstalls it.</li></ul> |

<div id="data-sources" />

#### **Data sources**

1. [Optional] Add more sources to use in the report. When choosing whether to more sources, note the significant difference between reports that **do** and **do not** use custom sources.
   * A report that **doesn't** use custom sources extracts specific event parameters and values from the in-app event raw data.
   * A report that **does** use custom sources extracts specific event parameters and values from the in-app event raw data, then matches this data with user-level data from your custom sources (such as data from your BI or CRM systems).
2. Complete the next steps based on whether or not your report uses custom sources:
   * If your report **doesn't** use custom sources, skip to **[Select dimensions](/docs/data-clean-room-creating-in-app-event-reports#select-dimensions),** then continue with the steps in all remaining tabs.
   * If your report **does** use custom sources, continue with the steps in the [**Join sources**](#join-sources-only-for-reports-containing-custom-sources) tab (immediately following) and all remaining tabs.

</Accordion>

The following step is relevant **only for reports that use custom sources.**

<div id="join-sources-only-for-reports-containing-custom-sources" />

<Accordion title="Join sources (only for reports containing custom sources)">

In order to match data among sources, each of the **custom** sources used in the report must include an <Anchor target="_blank" href="/marketers/docs/data-clean-room-setting-up-cloud-services">identifier</Anchor> mapped to a **key identifier** in the in-app event data.

* In-app event reports include **all** selected events matching the key identifier during the selected timeframe.

<div id="what-is-a-key-identifier" />

#### **What is a key identifier?**

You can map to either of these in-app event data identifiers as **key identifiers:**

* **AppsFlyer ID (af\_id):** A unique app identifier generated by AppsFlyer at installation –
  * This ID appears in all events recorded by AppsFlyer.
  * A new AppsFlyer ID is generated if an app is deleted and then reinstalled.
* **Customer User ID (CUID):** A unique user identifier usually generated and set by the app owner at the time of user registration.
  * Using CUID to map data requires that your app is configured to <Anchor target="_blank" href="/marketers/docs/customer-user-id-field-cuid">send the CUID to AppsFlyer</Anchor> via the SDK or the server-to-server API (S2S).

<div id="important" />

> 🚧 **Important!**
>
> Not all media sources permit matching using CUID. It is highly recommended to use AppsFlyer ID.

<div id="mapping-schemes-directindirect" />

#### **Mapping schemes (direct/indirect)**

If the report includes more than one custom source, only one of them needs to be mapped **directly** to an in-app event key identifier. Other custom sources can be mapped either **directly or indirectly,** as illustrated in the following example:

<div id="example" />

> 📄 **Example**
>
> ![dcr_mapping_identifiers_in-app events.png](https://files.readme.io/73d0e929663bda4e6f142c64d0228fdf1eeec3b02ef1560f6f03f2a089d00664-9969546429713.png)
>
> In the scenario shown above:
>
> * Custom source #1 identifier **AF** is mapped directly to the in-app event key identifier **af\_id.**
> * Custom source #2 is mapped indirectly: **user\_code** --> **AF** --> **af\_id.**
> * Custom source #3 is mapped indirectly (through a longer chain): **user\_id** --> **user\_code** --> **AF** --> **af\_id.**
> * Custom source #4 identifier **ID** is mapped directly to the in-app event key identifier **af\_id.**
>   * Note that it could have been mapped indirectly instead (through custom source #3 identifier **user\_id**), but either option works fine.
>
> ✓ This mapping scheme works to match data among all the sources since each custom source is mapped either directly or indirectly to the in-app event key identifier **af\_id.**

</Accordion>

The remaining tabs are relevant for **all in-app event reports,** whether or not they include custom sources.

<div id="select-dimensions" />

<Accordion title="Select dimensions">

Recall that user-level data cannot be reported by the DCR. Instead, it provides you with the decision-making insights you need by aggregating (or grouping) the data by the dimensions you choose.

A dimension is generally an attribute by which you categorize app users (for example, geo, install date, campaign, etc.)

<div id="extracting-dimensions-from-event_value" />

#### **Extracting dimensions from event\_value**

When in-app events are reported to AppsFlyer via the SDK or the S2S API, much of the raw data is contained in a single field called **event\_value.** This structured data field includes all of the specific in-app event parameters that have been configured for the events that your apps send to AppsFlyer.

One of the major advantages of In-app event reports is that they allow you to extract specific parameters and their values from the **event\_value** field for the events you choose.

**To extract dimensions from the event\_value field for use in DCR reports:**

1. In the **Dimensions from sources** list, click the <Image alt="extract_dimension_button.png" src="https://files.readme.io/c238da4a1d2a15fe2249070747fa6247db63ab4129b1c72804b84550675214f3-10754426767761.png" width="123px" /> button.

   The **Extract field from event\_value** window opens.
2. In the **Report field** box, enter the name of the extracted dimension as you would like it to appear in your report.
3. From the **Event\_value parameter** list, select the in-app event parameter that should be mapped by default to the report field (dimension) you defined in step 2.
   * The available parameters include those that have been configured in the **selected in-app events** **in the selected apps**.
4. It may be that the default mapping differs by app and/or event. If this is the case:
   1. Click the **Add exception** button
   2. Select the app and event for which the report field should be mapped differently.
   3. Select the in-app event parameter that should be mapped to the report field for this combination of app/event.
   4. Follow these steps for as many exceptions as you want to set up.
5. When you are finished setting up the mapping for the extracted dimension, click **Save and add another** to extract another dimension from the event\_value field or **Save** to return to the main screen.

**To edit extracted dimensions:**

1. In either the **Dimensions from sources** or the **Report dimensions** list, hover over the name of the dimension you want to edit.
2. Click the <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> button that displays to the right of the dimension.
3. Select **Edit extracted field.**
4. Make changes to the **Report field** name and/or parameter mapping as necessary.
5. Click **Save** to save your changes.

**To delete extracted dimensions:**

1. In either the **Dimensions from sources** or the **Report dimensions** list, hover over the name of the dimension you want to delete.
2. Click the <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> button that displays to the right of the dimension.
3. Select **Delete field.**
   * **Caution!** If you delete an extracted field from the **Report dimensions** list, it will delete the definition of the extracted field. If you wish to remove the field from the report while preserving its definition, select the field and use the **Remove** button instead.

<div id="selecting-report-dimensions" />

#### **Selecting report dimensions**

In-app event report dimensions can include:

* Dimensions you've extracted from event\_value
* [Default in-app event dimensions](/docs/data-clean-room-creating-in-app-event-reports#default-inapp-event-dimensions)
* Any field in the report's custom sources that has been <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-sources#3-define-the-source-structure">categorized as a dimension</Anchor> (if applicable)

**To select the dimensions to include in your report:**

1. Select one or more dimensions in the **Dimensions from sources** list on the left and use the **Add** button in the middle of the screen to add them to the list of **Report dimensions.**
   * You can use the search bar to search for dimensions in the lists.
2. To remove a dimension, select it from the **Report dimensions** list and use the **Remove** button to return it to the **Dimensions from sources** list.
3. Repeat this process until you have added each dimension you want to include in the report.

**Note:** By default, all reports are grouped by the in-app event dimension **media\_source.** If you do not wish to use this dimension in your report, you can remove it from the **Report dimensions** list.

<div id="optional-customizing-dimension-display-names" />

#### **[Optional] Customizing dimension display names**

By default, dimension names are displayed in your report exactly as they are named in the in-app event data or your custom sources. If you wish, you can customize dimension names for your report.

**To customize dimension display names:**

1. In the **Report dimensions** list, hover over the name of the dimension whose display name you want to edit.
2. Click the edit button ![edit_button.png](https://files.readme.io/f4ef4722724c776ce4034ab07492a4ac80825f6f15350911c1cbb51ac4843092-10754262613649.png) that displays to the right of the dimension.
3. Change the name to the dimension display name to be used in your report (up to 50 characters).
4. Click **OK** to save the display name, or **X** to cancel it.

**Note:** If you want to change the name of an **extracted dimension**, use the steps for editing extracted dimensions (above).

<div id="preserving-privacy-while-grouping-by-dimension-regrouping" />

#### **Preserving privacy while grouping by dimension (regrouping)**

Depending on the size of your data set, the number of dimensions you choose, and other factors, it's possible that a report would include one or more groups containing too few users to allow reporting. If the data were reported this way, it would violate restrictions against providing user-level data.

However, instead of removing or hiding the data from the report completely, the DCR uses a **regrouping mechanism** to provide as much detail as possible while maintaining user privacy.

<div id="regrouping-example" />

> 📄 **Regrouping example**
>
> Assume you have set up a report according to the following dimensions (in order):
>
> * **In-app event dimensions:**
>   * media source
>   * campaign
>   * adset\_name
>   * ad\_id
> * **Custom source dimensions:**
>   * user\_type
>
> **Before regrouping**
>
> After initial analysis of the data, the DCR determines that the data would break down as follows:
>
>
>
> | media  <br />source | campaign | adset  <br />name | ad  <br />id | user  <br />type | rev  <br />D0 | rev  <br />D7 | count | reportable? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | media\_source | UA\_100 | green | kjh867 | buyer | 1 | 4 | 120 | ✓ |
> | media\_source | UA\_101 | green | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | media\_source | UA\_200 | green | lkh123 | beg | 6 | 7 | x | **X** |
> | media\_source | UA\_200 | green | ilk945 | beg | 3 | 21 | x | **X** |
> | media\_source | UA\_200 | green | plm654 | beg | 8 | 17 | x | **X** |
>
>
>
> As it stands, the final 3 rows are not reportable because there are too few users in each. (This media source requires a minimum of **y** users in order to be reportable. Here, we have only **x**.)
>
> According to the regrouping logic, the DCR first "eliminates" the last-listed in-app event dimension (in this case, **ad\_id**). It then analyzes the data again to see which rows are reportable.
>
> **After regrouping**
>
> After applying the regrouping logic, the report appears as follows:
>
>
>
> | media  <br />source | campaign | adset  <br />name | ad  <br />id | user  <br />type | rev  <br />D0 | rev  <br />D7 | count | reportable? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | media\_source | UA\_100 | green | kjh867 | buyer | 1 | 4 | 120 | ✓ |
> | media\_source | UA\_101 | green | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | media\_source | UA\_200 | green | RESTRICTED | beg | 17 | 45 | y (x+x+x) | ✓ |
>
>
>
> **Results:**
>
> * The last row now combines the data that had previously been on 3 rows. Now, the combined row has a user count equal to **y** and can be reported.
> * The dimension that was eliminated is now reported as RESTRICTED.
> * Had there still been unreportable rows (fewer than **y** users), the DCR would continue to analyze the data on an iterative basis, eliminating one dimension after another until it either:
>   * can report all rows; or
>   * runs out of in-app event dimensions to eliminate
>
> **Note:** By default, the DCR applies regrouping only to **[default in-app event dimensions](/docs/data-clean-room-creating-in-app-event-reports#default-inapp-event-dimensions)** (not to extracted in-app event dimensions or custom source dimensions). If data grouped by a default in-app event dimension would result in a row containing fewer than **y** users, the data in that row will be reported as RESTRICTED.
>
> * *See below for an advanced option you can use to apply regrouping to custom source dimensions as well.*

<div id="optional-managing-dimension-priority" />

#### **[Optional] Managing dimension priority**

By default, in-app event dimensions are eliminated in reverse order from the order in which they appear in the **Report dimensions** list. However, you can modify the default sequence and/or apply regrouping to selected custom source dimensions (if applicable) in order to preserve the dimensions most important to you.

**To change the order in which dimensions are eliminated:**

1. Click the **Manage dimension priority** button.
2. Select a dimension and drag it to the desired position in the list (or use the arrow buttons on the right to move it).
   * The dimension labeled as **Highest priority** (at the top of the list) means it's the last to be eliminated if regrouping is required.
3. [Optional] To apply regrouping to custom source dimensions (for reports using custom sources):
   1. Click **Use advanced options to refine regrouping**
   2. Select custom source dimensions to which you'd like to apply regrouping.
   3. The selected dimensions are added to the **Manage dimension priority** list.
      * By default, these dimensions are added to the bottom of the list, as **Lowest priority** for regrouping. However, you can reorder them just like in-app event dimensions as described above.
4. Click **OK** to save your changes.
   * The **Report dimensions** list on the main screen remains in its original order, but the revised order has been saved. (Click again on the **Manage dimension priority** button if you wish to review or edit your selection.)

</Accordion>

<div id="select-metrics" />

<Accordion title="Select metrics">

Metrics are the numeric data you have collected with respect to an app user (examples might include revenue, number of app opens, LTV, etc.) and can be any numeric data field from your sources that you have categorized as a metric.

<div id="extracting-metrics-from-event_value" />

#### **Extracting metrics from event\_value**

Just as you can for [report dimensions](/docs/data-clean-room-creating-in-app-event-reports#select-dimensions), you can extract in-app event parameters from the **event\_value** field for use as metrics in your reports.

**To extract dimensions from the event\_value field for use in DCR reports:**

1. In the **Metrics from sources** list, click the <Image alt="extract_metric_button.png" src="https://files.readme.io/93ca5970968816d452331df4ce5ff4cfb678cbb24f65eb99fe01bd3bb3016959-10755235273233.png" width="102px" /> button.

   The **Extract field from event\_value** window opens.
2. In the **Report field** box, enter the name of the extracted metric as you would like it to appear in your report.
3. From the **Event\_value parameter** list, select the in-app event parameter that should be mapped by default to the report field (metric) you defined in step 2.
   * The available parameters include those that have been configured in the **selected in-app events** **in the selected apps**.
4. It may be that the default mapping differs by app and/or event. If this is the case:
   1. Click the **Add exception** button
   2. Select the app and event for which the report field should be mapped differently.
   3. Select the in-app event parameter that should be mapped to the report field for this combination of app/event.
   4. Follow these steps for as many exceptions as you want to set up.
5. When you are finished setting up the mapping for the extracted metric, click **Save and add another** to extract another metric from the event\_value field or **Save** to return to the main screen.

**To edit extracted metrics:**

1. In either the **Metrics from sources** or the **Report metrics** list, hover over the name of the metric you want to edit.
2. Click the <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> button that displays to the right of the metric.
3. Select **Edit extracted field.**
4. Make changes to the **Report field** name and/or parameter mapping as necessary.
5. Click **Save** to save your changes.

**To delete extracted metrics:**

1. In either the **Metrics from sources** or the **Report metrics** list, hover over the name of the metric you want to delete.
2. Click the <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> button that displays to the right of the metric.
3. Select **Delete field.**
   * **Caution!** If you delete an extracted field from the **Report metrics** list, it will delete the definition of the extracted field. If you wish to remove the field from the report while preserving its definition, select the field and use the **Remove** button instead.

<div id="select-report-metrics" />

#### **Select report metrics**

**To select the metrics to include in your report:**

1. Select one or more metrics in the **Metrics from sources** list on the left and use the **Add** button in the middle of the screen to add them to the list of **Report metrics.**
   * You can use the search bar to search for metrics in the lists.
2. For each metric in the **Report metrics** list, select whether you want the data reported as either:
   * a sum of numeric values; or
   * a count of distinct values
3. To remove a metric, select it from the **Report metrics** list and use the **Remove** button to return it to the **Metrics from sources** list.
4. Repeat this process until you have added each metric you want to include in the report.

<div id="optional-customizing-metric-display-names" />

#### **[Optional] Customizing metric display names**

By default, metric names are displayed in your report exactly as they are named in the in-app event data or your custom sources. If you wish, you can customize metric names for your report.

**To customize metric display names:**

1. In the **Report metrics** list, hover over the name of the metric whose display name you want to edit.
2. Click the edit button ![edit_button.png](https://files.readme.io/f4ef4722724c776ce4034ab07492a4ac80825f6f15350911c1cbb51ac4843092-10754262613649.png) that displays to the right of the metric.
3. Change the name to the metric display name to be used in your report (up to 50 characters).
4. Click **OK** to save the display name, or **X** to cancel it.

**Note:** If you want to change the name of an **extracted metric**, use the steps for editing extracted metrics (above).

<div id="optional-select-identifiers-to-count" />

#### **[Optional] Select identifiers to count**

By default, each row of the report ends with a column containing a count of the distinct AppsFlyer IDs grouped in that row's data.

**If you wish to add columns for the distinct counts of other identifiers from your sources, do so as follows:**

1. Select one or more identifiers in the **Identifiers from sources** list on the left and use the **Add** button in the middle of the screen to add them to the list of **Distinct count identifiers**.
   * You can use the search bar to search for identifiers in the lists.
2. To remove an identifier, select it from the **Distinct count identifiers** list and use the **Remove** button to return it to the **Identifiers from sources** list.
3. Repeat this process until you have added each identifier you want counted in the report.

</Accordion>

<div id="configure-report-settings-and-save-the-report" />

<Accordion title="Configure report settings and save the report">

<div id="schedule-only-for-reports-without-custom-sources" />

#### **Schedule (only for reports without custom sources)**

Reports without custom sources are run according to the schedule you define.

**To define the report schedule:**

1. Select whether to run the report daily or on one or more days each week.
2. Select the time at which to run the report (timezone is UTC).

<div id="important-1" />

> 🚧 **Important!**
>
> Scheduling options are disabled for reports that use custom sources. This type of report runs whenever new versions of all of the <Anchor target="_blank" href="/marketers/docs/data-clean-room-creating-attribution-data-reports#custom-sources">custom sources it uses</Anchor> are detected:
>
> * For sources located in **data warehouses** (BigQuery and Snowflake), the DCR recognizes that a new version of a source has been created when it detects a new value in <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-sources#table-columns">the `v` column of the source table</Anchor>.
>   * **Important!** To ensure the completeness of your report, be sure to populate the source table with a complete set of data whenever the column value is changed.
> * For sources located in **cloud storage buckets** (Amazon S3 and GCS), the DCR recognizes that a new version of a source has been created when it detects that a <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-sources#updating-sources-to-trigger-report-processing">new version of a source file has been uploaded</Anchor> along with its accompanying \_SUCCESS file.
>
> AppsFlyer continually scans for new versions of sources for the **current date and 2 days prior.**

<div id="report-destination" />

#### **Report destination**

The DCR delivers reports to your selected cloud services using <Anchor target="_blank" href="/marketers/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>. Therefore, specifying the report destination involves selecting or creating a Data Locker connection.

* **Note:** Receiving DCR reports does not require a premium subscription to Data Locker. If you are interested in receiving other AppsFlyer reports via Data Locker, contact your CSM or send an email to [hello@appsflyer.com](mailto:hello@appsflyer.com).

**To set the report destination and save the report:**

1. Select from the list of Data Locker connections available in your AppsFlyer account.
   * If there are no connections defined in your account:
     * A new tab will open in your browser (showing the AppsFlyer Data Locker page)
     * A **New connection** dialog will open. Follow <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-connections#complete-the-connection-1">these instructions</Anchor> to create the connection.
   * If you have existing connections but want to use a new one, click the ![dcr_new_connection_data_locker_button.png](https://files.readme.io/21fda59ab30e85ab4ba8b4b5920c901e8bcdedadad393a2205bb34e839f9c8db-16684568466961.png) button:
     * A new tab will open in your browser (showing the AppsFlyer Data Locker page)
     * A **New connection** dialog will open. Follow <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-connections#complete-the-connection-1">these instructions</Anchor> to create the connection.
   * After creating the connection, return to the DCR tab in your browser and select the newly created connection from the list of Data Locker connections.
2. Click **Save** to save the report.
3. The new report is now displayed in the **Reports** tab of the **Data Clean Room.**

</Accordion>

<div id="reference" />

## Reference

<div id="default-inapp-event-dimensions" />

<Accordion title="Default in-app event dimensions">

In addition to dimensions extracted from **event\_value** and dimensions from your custom sources (if applicable), the following in-app event dimensions can be used to group reports:

* media\_source *([included as a report dimension by default](#selecting-report-dimensions))*
* ad
* ad\_id
* ad\_type
* adset\_id
* adset\_name
* app\_id
* app\_version
* attributed\_touch\_type
* brand
* campaign
* campaign\_id
* channel
* city
* conversion\_type
* country
* device\_type
* dma
* engagement\_type
* event\_name
* event\_revenue\_currency
* geo\_region
* is\_attributed
* keywords
* match\_type
* model
* partner
* platform
* site\_id

</Accordion>

<div id="default-inapp-event-metrics" />

<Accordion title="Default in-app event metrics">

In addition to metrics extracted from **event\_value** and metrics from your custom sources (if applicable), the following in-app event metrics can be included in reports:

* event\_revenue
* event\_revenue\_u\_s\_d

</Accordion>

<div data-zendesk-anchors="creating-an-inapp-event-report=creating-an-in-app-event-report h_01HA9W7NP4CR9CVXY9CXENYSPF=creating-an-in-app-event-report h_01HA9W7NP4B55Y2SB6ADKE06JV=perform-preliminary-steps h_01HA9W7NP4A7YK5JFYNFXFY6ZJ=select-sources inapp-event-sources=in-app-event-sources h_01HA9W7NP4G0S2TQT9W2RK1QBA=in-app-event-sources custom-sources=data-sources h_01HA9W7NP46D57Q7H8611K4KBB=data-sources h_01HA9W7NP4K2055TXTE98HWTAW=join-sources-only-for-reports-containing-custom-sources h_01HA9W7NP4WTBJ83MY73JQ2ESH=what-is-a-key-identifier h_01HA9W7NP5N8W4X8H1WRN1183Z=important h_01HA9W7NP51HWA36BBP1JC3HMW=mapping-schemes-directindirect h_01HA9W7NP5V1SV5PGF277G5P6T=example h_01HA9W7NP56M09TF9CB7FCBPBR=select-dimensions h_01HA9W7NP5BV7GJXMEMS57HNJ9=extracting-dimensions-from-event_value h_01HA9W7NP5S6EWDE38Q6T42QEB=selecting-report-dimensions %5Boptional%5D-customizing-dimension-display-names=optional-customizing-dimension-display-names h_01HA9W7NP5YC8E3B05GV7J1Z5V=optional-customizing-dimension-display-names h_01HA9W7NP5XJGK4CXNHK02NYT4=preserving-privacy-while-grouping-by-dimension-regrouping h_01HA9W7NP596RGHA1BES64GSK1=regrouping-example %5Boptional%5D-managing-dimension-priority=optional-managing-dimension-priority h_01HA9W7NP5781HV31T5DAYSMMT=optional-managing-dimension-priority h_01HA9W7NP6WCSRSH157P78QEQF=select-metrics h_01HA9W7NP6JEXE67A935BJ93AQ=extracting-metrics-from-event_value h_01HA9W7NP6EF23ZDGZHDKVTS7V=select-report-metrics %5Boptional%5D-customizing-metric-display-names=optional-customizing-metric-display-names h_01HA9W7NP6X584YAXT030A6BEY=optional-customizing-metric-display-names %5Boptional%5D-select-identifiers-to-count=optional-select-identifiers-to-count h_01HA9W7NP6YETQ1ND0K8XZTZZ0=optional-select-identifiers-to-count h_01HA9W7NP6ZH3KRN7YNWCPFZC9=configure-report-settings-and-save-the-report h_01HA9W7NP62DCR2SWD8X4M61R7=schedule-only-for-reports-without-custom-sources h_01HA9W7NP6XQE1MN0J08FE89V4=important-1 h_01HA9W7NP6BQYAF3RMZSW747HH=report-destination h_01HA9W7NP6BS0TE332GNPTW9M1=reference h_01HA9W7NP606HF0MSPQ4S09YRS=default-inapp-event-dimensions h_01HA9W7NP6A1N25KQ947J3EJW3=default-inapp-event-metrics" />

---
title: Pull API raw data
metadata:
  keywords:
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2020-04-14T18:24:00Z'
  edited_at: '2026-03-12T12:19:12Z'
  id: 360007530258
  locale: en-us
  section: Data delivery tools
  section_id: 6550995484561
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360007530258-Pull-API-raw-data
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Use this API to get raw data reports in CSV files.

[![PullAPIRaw_us-en.png](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)

## Pull API raw data

* Pull API lets you get raw data reports for in CSV files. <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview">Learn more about raw data reports</Anchor>
* Filter by options available: Media source, date range, in-app event name, and geo.
* Additional capabilities in Pull API are:
  * Select currency
  * Select timezone

#### Raw data reports available via Pull API

<table><thead><tr><th>Report</th><th>Description</th><th>Refresh rate</th></tr></thead><tbody><tr><td colspan="3"><h4><strong><span id="raw-data-reports-nonorganic"></span>Raw data reports (non-organic)</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-report-v5" target="_blank">Installs</a></td><td>Records non-organic installs. The record is generated when a user opens the app for the first time.<br/> </td><td>Real-time</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-report-v5" target="_blank">In-app events</a></td><td>Records the events performed by users.<br/> </td><td>Real-time</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-uninstall-events-report-v5" target="_blank">Uninstalls</a></td><td>Records when a user uninstalls the app.<br/> </td><td>Daily</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-v5" target="_blank">Reinstalls</a><br/> </td><td>Records users who after uninstalling the app, engage with a UA media source and reinstall the app during the re-attribution window.</td><td>Real-time</td></tr><tr><td colspan="3"><h4><strong><span id="raw-data-reports-organic"></span>Raw data reports (organic)</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-installs-report-v5" target="_blank">Organic Installs</a><br/> </td><td>Records when the app is opened by a user for the first time.<br/> </td><td>Continuous</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-in-app-events-report-v5" target="_blank">Organic in-app events</a><br/> </td><td>Records details about events performed by users.<br/> </td><td>Continuous</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-uninstall-events-report-v5" target="_blank">Organic uninstalls</a><br/> </td><td>Records users uninstalling the app.<br/> </td><td>Daily</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-organic-v5" target="_blank">Organic reinstalls</a><br/> </td><td>Records users uninstalling the app and then installing it again.</td><td>Daily<br/> </td></tr><tr><td colspan="3"><h4><strong><span id="retargeting"></span>Retargeting</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-retarget-v5">Conversions</a></td><td>Record of a user opening the app after engaging with a retargeting campaign.</td><td>Real-time</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-retarget-v5">In-app events</a></td><td>In-app events performed by the user during the re-engagement window.</td><td>Real-time</td></tr><tr><td colspan="3"><h4><strong><span id="ad-revenue-raw-data"></span>Ad revenue raw data</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5" target="_blank">Attributed ad revenue</a><br/> </td><td>Records ad revenue for users attributed to a media source.</td><td>Daily</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-organic-raw-v5" target="_blank">Organic ad revenue</a></td><td>Records ad revenue for users not attributed to a media source.</td><td>Daily</td></tr><tr><td colspan="3"><h4><strong><span id="protect360-fraud"></span>Protect360 fraud</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-installs-report-v5" target="_blank">Installs</a></td><td>Records installs identified as fraudulent and therefore not attributed to any media source.</td><td>Real-time</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-detection-v5" target="_blank">Post-attribution installs</a></td><td>Records in-app events from fraudulent installs and therefore not attributed at all.</td><td>Daily</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-in-app-events-report-v5" target="_blank">In-app events</a></td><td>Records in-app events identified as fraudulent by Protect360.</td><td>Real-time</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-fraud-post-inapps-v5" target="_blank">Post-attribution in-app events</a></td><td>Records in-app events for installs identified as fraudulent after being attributed to a media source or judged fraudulent without regard to the install itself.</td><td>Daily</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-clicks-report-v5" target="_blank">Clicks</a></td><td>Records clicks performed by users blocked by Protect360.</td><td>Real-time</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-install-postbacks-v5" target="_blank">Blocked install postbacks</a></td><td>Records copies of postbacks sent to a media source resulting in a blocked install.</td><td>Real-time</td></tr><tr><td colspan="3"><strong>Postbacks</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5" target="_blank">Install postbacks</a></td><td>Records install events generated when a user opens the app for the first time.</td><td>Daily</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-postbacks-v5" target="_blank">In-app event postbacks</a></td><td>Records in-app event postbacks sent to the media source.</td><td>Daily</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-in-app-events-postbacks-v5" target="_blank">Retargeting in-app event postbacks</a></td><td>Records in-app events users performed during the re-engagement window.</td><td>Real-time</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-install-postbacks-v5" target="_blank">Retargeting conversions postbacks</a></td><td>Records in-app events users performed during the re-engagement window.</td><td>Real-time</td></tr></tbody></table>

<div id="using-pull-api-raw-data" />

<Accordion title="Using Pull API raw data">

**To use Pull API raw data**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/ff3f7349af66b7b80d311953567eef821eec56d46146fa9ad7c43d73dd2f8af5-33379479626641.png)<Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens#reaching-the-tokens-page">Get the API token</Anchor>. An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the parameters to input when they make the API call, as described in the sections that follow. The parameters determine what the report focuses on, how it's organized, and provide a reporting timeframe.
4. Tell your developer to follow their <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">Pull API raw data instructions</Anchor> in the developer hub.

#### Parameters

| Parameter | Description |
| --- | --- |
| from | <ul><li>The date range consists of `from`and `to` parameters. The dates relate to the activity date.</li><li>Format: `yyyy-mm-dd`, `yyyy-mm-dd hh:mm`, or `yyyy-mm-dd hh:mm:ss` **Note**: The space needs to be encoded as shown here `from=2020-04-01%2001:00:00` - In general, browsers will encode the space.</li><li>Example: 2010-01-01 or 2010-01-01 20:15 (Hours and minutes parameters available for raw data reports).</li></ul> |
| to | End date. As for `from` |
| media\_source | `media_source`: To limit (filter) the call to a specific media source.<br /><br />Set both the `media_source` and `category` parameters as follows:<ul><li>For Meta ads, set category and media source to *facebook*</li><li>For X Ads, set category and media source to *twitter*</li><li>For all other media sources, set category to *standard* and media source to the name of the media source.</li></ul><ul><li>Examples<ul><li>`media_source=facebook&category=facebook`</li><li>`media_source=abc_example&category=standard`</li></ul></li></ul> |
| maximum\_rows | Maximum number of rows returned by a single API call.<ul><li>[Default] if no value is sent, up to 200K rows</li><li>200000: Up to 200K rows return</li><li>1000000: Up to 1M rows return</li><li>Example: `maximum_rows=1000000` enables up to 1M rows.</li></ul> |
| event\_name | Filter in-app events by specified events. Select multiple events by using a comma-separated list.<br /><br />**Example**: `event_name=af_purchase,ftd` |
| reattr | Set retargeting attribution data.<ul><li>[Default] If false, user acquisition data (UA) campaigns returns.</li><li>If true, retargeting attribution data returns.</li><li>**Example**:`reattr=true`</li></ul> |
| additional\_fields | To get additional fields in addition to the default fields.<br /><br />**Example**: `additional_fields=device_download_time,deeplink_url` |
| currency | Currency of the revenue and cost<ul><li>[Default] If the parameter is not sent, data returns as USD. Meaning, do nothing and results return in USD.</li><li>If you send, `currency=preferred`the <Anchor target="_blank" href="/marketers/docs/app-settings#localization-time-zone">app-specific</Anchor> currency is used. Meaning the currency set in the app settings.</li></ul>**Example**: If the app-specific currency is EUR, by sending `currency=preferred`the values return in EUR. |
| timezone | [Default] Data returns using UTC.<ul><li>To get data in the <Anchor target="_blank" href="/marketers/docs/app-settings#localization-time-zone">app-specific</Anchor> timezone, add `timezone` as shown in this section to the call:</li></ul><ul><li>`timezone=[Numerical value]`</li><li>Example: For time zone UTC+10:00 use`timezone=+10:00` **Note**: The `+`,`-`, and `:` need to be encoded. Example: +10:00 encodes to `%2B10%3A00`</li></ul> |
| geo | Filter the data by country code.<br /><br />Limitation: You can set only one country code filter per API call.<br /><br />Example: `geo=ZA` |
| from\_install time | <ul><li>The date range consists of `from`and `to` parameters. The dates relate to the activity date.</li><li>Format: `yyyy-mm-dd`</li><li>Example: 2010-01-01</li></ul> |
| to\_install\_time | End date. As for `from_install time` |
| agency | To limit (filter) the call to a specific agency. |

</Accordion>

<div id="protect360-fields" />

<Accordion title="Protect360 fields">

<Anchor target="_blank" href="/marketers/docs/protect360-raw-data-reports#postattribution-reports">See the Protect360 raw data guide</Anchor>

</Accordion>

<div id="time-frame-fields" />

<Accordion title="Time frame fields">

If the API results exceed the maximum, split the report using hours and minutes. Apply the following:

* **from**/**to:** **yyyy-mm-dd hh:mm**
* **from:**
  * Date only = from the beginning (00:00) of the chosen date
  * Date and time = from and including 00:00
* Parameter **to:**
  * Date only = up to the end (24:00) of the chosen day
  * Date and time = up to, but not including, the shown time

**Example:** An app owner has 1300K daily installs from all sources. To overcome the 1M row limit, the app owner splits the day into two 12-hour URI calls. See the following table for options.

<table><thead><tr><th>API call</th><th>From </th><th>To </th></tr></thead><tbody><tr><td><strong>First API call</strong> </td><td><p><strong>from</strong>=yyyy-mm-dd</p><p><strong>Example:</strong></p><ul><li><strong>from</strong>=<code>2019-12-29</code></li><li>Begins on this date at the beginning of the day at 00:00</li></ul></td><td><p><strong>to</strong>=yyyy-mm-dd 12:00</p><p><strong>Example:</strong></p><ul><li><strong>to</strong>=<code>2019-12-29 12:00</code></li><li>Continues up to 11:59:59, not 12:00 </li></ul></td></tr><tr><td><p><strong>Option A: Second API call</strong> </p><p><strong>Example:</strong> </p><p><code><kbd><strong>&amp;from=2019-12-29 12:00&amp;to=2019-12-29</strong></kbd></code></p><ul><li>Starts noon 29 Dec 2019</li><li>Ends midnight 29 Dec 2019</li></ul></td><td><p><strong>from</strong>=yyyy-mm-dd 12:00</p><p><strong>Example:</strong></p><ul><li><strong>from</strong>=<code>2019-12-29 12:00</code></li><li>Starts from and includes 12:00</li></ul></td><td><p><strong>to</strong>=yyyy-mm-dd</p><p><strong>Example:</strong></p><ul><li><strong>to</strong>=<code>2019-12-29</code></li><li>Ends at midnight</li></ul></td></tr><tr><td><strong>Option B: Second API call</strong></td><td><p><strong>from</strong>=yyyy-mm-dd 12:00</p><p><strong>Example:</strong></p><ul><li><strong>from</strong>=<code>2019-12-29 12:00</code></li><li>Starts from and includes 12:00</li></ul></td><td><p><strong>to</strong>=yyyy-mm-dd+1 00:00</p><p><strong>+1</strong> = next day at 00:00</p><p><strong>Example:</strong></p><ul><li><strong>to=</strong><code><strong>2019-12-30 00:00</strong></code></li><li>Meaning before any time has elapsed on 30 Dec.</li></ul></td></tr><tr><td colspan="3"><strong>Note:</strong> Use option A or B as they have the same results. </td></tr></tbody></table>

</Accordion>

<div id="additional-fields" />

<Accordion title="Additional fields">

Additional report fields are not added to the default list of fields so that new fields don't impact your existing import and ingestion processes. Use the `additional_fields` parameter to get non-default fields.

* List a field only once.
* See the <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary">list of available fields</Anchor>.
* Example: `additional_fields=device_download_time,deeplink_url`

</Accordion>

<div id="default-fields" />

<Accordion title="Default fields">

| Default Pull API fields |
| --- |
| Attributed Touch Type |
| Attributed Touch Time |
| Install Time |
| Event Time |
| Event Name |
| Event Value |
| Event Revenue |
| Event Revenue Currency |
| Event Revenue USD |
| Event Source |
| Is Receipt Validated |
| Partner |
| Media Source |
| Channel |
| Keywords |
| Campaign |
| Campaign ID |
| Adset |
| Adset ID |
| Ad |
| Ad ID |
| Ad Type |
| Site ID |
| Sub Site ID |
| Sub Param 1 |
| Sub Param 2 |
| Sub Param 3 |
| Sub Param 4 |
| Sub Param 5 |
| Cost Model |
| Cost Value |
| Cost Currency |
| Contributor 1 Partner |
| Contributor 1 Media Source |
| Contributor 1 Campaign |
| Contributor 1 Touch Type |
| Contributor 1 Touch Time |
| Contributor 2 Partner |
| Contributor 2 Media Source |
| Contributor 2 Campaign |
| Contributor 2 Touch Type |
| Contributor 2 Touch Time |
| Contributor 3 Partner |
| Contributor 3 Media Source |
| Contributor 3 Campaign |
| Contributor 3 Touch Type |
| Contributor 3 Touch Time |
| Region |
| Country Code |
| State |
| City |
| Postal Code |
| DMA |
| IP |
| WIFI |
| Operator |
| Carrier |
| Language |
| AppsFlyer ID |
| Advertising ID |
| IDFA |
| Android ID |
| Customer User ID |
| IMEI |
| IDFV |
| Platform |
| Device Type |
| OS Version |
| App Version |
| SDK Version |
| App ID |
| App Name |
| Bundle ID |
| Is Retargeting |
| Retargeting Conversion Type |
| Attribution Lookback |
| Reengagement Window |
| Is Primary Attribution |
| User Agent |
| HTTP Referrer |
| Original URL |

</Accordion>

## Additional information

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Comments |
| --- | --- |
| API token type required | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/ff3f7349af66b7b80d311953567eef821eec56d46146fa9ad7c43d73dd2f8af5-33379479626641.png)<Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens">V2.0 token</Anchor> |
| Ad network access | No |
| Agency access | Yes |
| Agency transparency | Yes. However, note that if you use both the agency filter and media source filters, the media source filters don't apply for non-transparent agencies. This means that for non-transparent agencies, all data is included; not just data from the filtered media sources. |
| App-specific currency | Yes |
| App-specific timezone | Yes |
| Data freshness | <ul><li>Equivalent to the availability of the data in the overview dashboard.</li><li>Reports updated with a lag of a few hours:<ul><li>Organic in-app events</li></ul></li><li>Reports updated Daily:<ul><li>Uninstalls</li><li>Post-attribution in-app events</li><li>Ad revenue</li></ul></li></ul> |
| Historical data | Yes.  According to <Anchor target="_blank" href="/marketers/docs/user-level-data-retention">retention</Anchor> and <Anchor target="_blank" href="/marketers/docs/report-generation-quotas-rate-limitations">rate limitation</Anchor> policies. |
| Non-organic data | Yes |
| Organic data | Yes |
| Rate limitation | API limitations for <Anchor target="_blank" href="/marketers/docs/report-generation-quotas-rate-limitations">raw data</Anchor>. |
| Size limitations | <ul><li>API calls return a max. of 200K/1M rows.</li><li>If a report has exactly 200K/1M rows, then assume rows are missing.</li><li>Use the maximum\_rows parameter to select the maximum number of rows.</li><li>Make multiple API calls, using from/to parameters that include the time of day.</li></ul> |
| Install\_date from and install\_date\_to | Install date range must be earlier than the activity date range. |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Troubleshooting">

| Symptom/message | Solution |
| --- | --- |
| The report doesn't contain the data expected according to the selected time range or there is a discrepancy between the raw data report and aggregated data report. | Verify that you have set the `timezone`parameter. If you don't, data is sent using UTC and not your app time zone. |

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Selecting the right data delivery tool/reporting API</Anchor>

<div data-zendesk-anchors="h_01HE7S6WDVJD2XFW498P8FPY7W=pull-api-raw-data aggregate-performance-reports-available-via-pull-api=raw-data-reports-available-via-pull-api h_01HE7S6WDV59VTP6Z4X790QDRD=raw-data-reports-available-via-pull-api h_01KEVCHC25BDNS9F1GEPBDAW39=raw-data-reports-nonorganic h_01KEVCHJ8TRRM9BYW6C544PNFR=raw-data-reports-organic h_01KEVCHSNGPX2RW917QX4N03A2=retargeting h_01KEVCHYMHGC6VTVSERH611Q8X=ad-revenue-raw-data h_01KEVCJ3GWBZG8SWHZKTRJ6YAX=protect360-fraud h_01HE7S6WDVYJ5MAK04VWB4MF6A=using-pull-api-raw-data h_01HE7S6WDVF8T4719HWDJH8JN1=parameters h_01HE7S6WDVGSS0F116ZB6QVG1N=protect360-fields h_01HE7S6WDVP47A3Q8J7NPH54T5=time-frame-fields h_01HE7S6WDWZ8FR6GRJ40B4CJAV=additional-fields h_01HE7S6WDWMXYF0RHYPF058A9K=default-fields h_01HE7S6WDW9V8XC3CJ0F96EHN0=additional-information h_01HE7S6WDWV87YVJMN76STX7A1=traits-and-limitations h_01HE7S6WDWMZPPTR41VHJQ8MWC=troubleshooting h_01HE7S8S8QCSKRA62A2HVK2MYJ=see-also" />

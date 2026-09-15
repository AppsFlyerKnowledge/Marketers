---
title: "Pull API raw data"
excerpt: "Use the Pull API to retrieve raw data reports in CSV format, with options to filter by media source, date range, in-app event name, and geo."
---
At a glance: Use this API to get raw data reports in CSV files.

![PullAPIRaw_us-en.png](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)

## Pull API raw data

- Pull API lets you get raw data reports for in CSV files. [Learn more about raw data reports](https://support.appsflyer.com/hc/articles/209680773)
- Filter by options available: Media source, date range, in-app event name, and geo.
- Additional capabilities in Pull API are:
  - Select currency
  - Select timezone

#### Raw data reports available via Pull API

| Report | Description | Refresh rate |
| --- | --- | --- |
| **Raw data reports (non-organic)** | | |
| [Installs](https://dev.appsflyer.com/hc/reference/get_app-id-installs-report-v5) | Records non-organic installs. The record is generated when a user opens the app for the first time. | Real-time |
| [In-app events](https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-report-v5) | Records the events performed by users. | Real-time |
| [Uninstalls](https://dev.appsflyer.com/hc/reference/get_app-id-uninstall-events-report-v5) | Records when a user uninstalls the app. | Daily |
| [Reinstalls](https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-v5) | Records users who after uninstalling the app, engage with a UA media source and reinstall the app during the re-attribution window. | Real-time |
| **Raw data reports (organic)** | | |
| [Organic Installs](https://dev.appsflyer.com/hc/reference/get_app-id-organic-installs-report-v5) | Records when the app is opened by a user for the first time. | Continuous |
| [Organic in-app events](https://dev.appsflyer.com/hc/reference/get_app-id-organic-in-app-events-report-v5) | Records details about events performed by users. | Continuous |
| [Organic uninstalls](https://dev.appsflyer.com/hc/reference/get_app-id-organic-uninstall-events-report-v5) | Records users uninstalling the app. | Daily |
| [Organic reinstalls](https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-organic-v5) | Records users uninstalling the app and then installing it again. | Daily |
| **Retargeting** | | |
| [Conversions](https://dev.appsflyer.com/hc/reference/get_app-id-installs-retarget-v5) | Record of a user opening the app after engaging with a retargeting campaign. | Real-time |
| [In-app events](https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-retarget-v5) | In-app events performed by the user during the re-engagement window. | Real-time |
| **Ad revenue raw data** | | |
| [Attributed ad revenue](https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5) | Records ad revenue for users attributed to a media source. | Daily |
| [Organic ad revenue](https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-organic-raw-v5) | Records ad revenue for users not attributed to a media source. | Daily |
| **Protect360 fraud** | | |
| [Installs](https://dev.appsflyer.com/hc/reference/get_app-id-blocked-installs-report-v5) | Records installs identified as fraudulent and therefore not attributed to any media source. | Real-time |
| [Post-attribution installs](https://dev.appsflyer.com/hc/reference/get_app-id-detection-v5) | Records in-app events from fraudulent installs and therefore not attributed at all. | Daily |
| [In-app events](https://dev.appsflyer.com/hc/reference/get_app-id-blocked-in-app-events-report-v5) | Records in-app events identified as fraudulent by Protect360. | Real-time |
| [Post-attribution in-app events](https://dev.appsflyer.com/hc/reference/get_app-id-fraud-post-inapps-v5) | Records in-app events for installs identified as fraudulent after being attributed to a media source or judged fraudulent without regard to the install itself. | Daily |
| [Clicks](https://dev.appsflyer.com/hc/reference/get_app-id-blocked-clicks-report-v5) | Records clicks performed by users blocked by Protect360. | Real-time |
| [Blocked install postbacks](https://dev.appsflyer.com/hc/reference/get_app-id-blocked-install-postbacks-v5) | Records copies of postbacks sent to a media source resulting in a blocked install. | Real-time |
| **Postbacks** | | |
| [Install postbacks](https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5) | Records install events generated when a user opens the app for the first time. | Daily |
| [In-app event postbacks](https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-postbacks-v5) | Records in-app event postbacks sent to the media source. | Daily |
| [Retargeting in-app event postbacks](https://dev.appsflyer.com/hc/reference/get_app-id-retarget-in-app-events-postbacks-v5) | Records in-app events users performed during the re-engagement window. | Real-time |
| [Retargeting conversions postbacks](https://dev.appsflyer.com/hc/reference/get_app-id-retarget-install-postbacks-v5) | Records in-app events users performed during the re-engagement window. | Real-time |

### Using Pull API raw data

**To use Pull API raw data**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/ff3f7349af66b7b80d311953567eef821eec56d46146fa9ad7c43d73dd2f8af5-33379479626641.png)[Get the API token](/docs/managing-appsflyer-tokens#reaching-the-tokens-page). An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the parameters to input when they make the API call, as described in the sections that follow. The parameters determine what the report focuses on, how it\'s organized, and provide a reporting timeframe.
4. Tell your developer to follow their [Pull API raw data instructions](https://dev.appsflyer.com/hc/reference/overview-5) in the developer hub.

#### Parameters

| Parameter | Description |
| --- | --- |
| from | - The date range consists of `from` and `to` parameters. The dates relate to the activity date.<br/>- Format: `yyyy-mm-dd`, `yyyy-mm-dd hh:mm`, or `yyyy-mm-dd hh:mm:ss` **Note**: The space needs to be encoded as shown here `from=2020-04-01%2001:00:00` - In general, browsers will encode the space.<br/>- Example: 2010-01-01 or 2010-01-01 20:15 (Hours and minutes parameters available for raw data reports). |
| to | End date. As for `from` |
| media\_source | `media_source`: To limit (filter) the call to a specific media source.<br/>Set both the `media_source` and `category` parameters as follows:<br/>- For Meta ads, set category and media source to _facebook_<br/>- For X Ads, set category and media source to _twitter_<br/>- For all other media sources, set category to _standard_ and media source to the name of the media source.<br/>- Examples<br/>  - `media_source=facebook&category=facebook`<br/>  - `media_source=abc_example&category=standard` |
| maximum\_rows | Maximum number of rows returned by a single API call.<br/>- [Default] if no value is sent, up to 200K rows<br/>- 200000: Up to 200K rows return<br/>- 1000000: Up to 1M rows return<br/>- Example: `maximum_rows=1000000` enables up to 1M rows. |
| event\_name | Filter in-app events by specified events. Select multiple events by using a comma-separated list.<br/>**Example**: `event_name=af_purchase,ftd` |
| reattr | Set retargeting attribution data.<br/>- [Default] If false, user acquisition data (UA) campaigns returns.<br/>- If true, retargeting attribution data returns.<br/>- **Example**: `reattr=true` |
| additional\_fields | To get additional fields in addition to the default fields.<br/>**Example**: `additional_fields=device_download_time,deeplink_url` |
| currency | Currency of the revenue and cost<br/>- [Default] If the parameter is not sent, data returns as USD. Meaning, do nothing and results return in USD.<br/>- If you send, `currency=preferred` the [app-specific](https://support.appsflyer.com/hc/articles/211719806-App-settings-#localization-time-zone) currency is used. Meaning the currency set in the app settings.<br/>**Example**: If the app-specific currency is EUR, by sending `currency=preferred` the values return in EUR. |
| timezone | [Default] Data returns using UTC.<br/>- To get data in the [app-specific](https://support.appsflyer.com/hc/articles/211719806-App-settings-#localization-time-zone) timezone, add `timezone` as shown in this section to the call:<br/>- `timezone=[Numerical value]`<br/>- Example: For time zone UTC+10:00 use `timezone=+10:00` **Note**: The `+`, `-`, and `:` need to be encoded. Example: +10:00 encodes to `%2B10%3A00` |
| geo | Filter the data by country code.<br/>Limitation: You can set only one country code filter per API call.<br/>Example: `geo=ZA` |
| from\_install time | - The date range consists of `from` and `to` parameters. The dates relate to the activity date.<br/>- Format: `yyyy-mm-dd`<br/>- Example: 2010-01-01 |
| to\_install\_time | End date. As for `from_install time` |
| agency | To limit (filter) the call to a specific agency. |

### Protect360 fields

[See the Protect360 raw data guide](https://support.appsflyer.com/hc/articles/360015179337#postattribution-reports)

### Time frame fields

If the API results exceed the maximum, split the report using hours and minutes. Apply the following:

- **from** / **to**: **yyyy-mm-dd hh:mm**
- **from**:
  - Date only = from the beginning (00:00) of the chosen date
  - Date and time = from and including 00:00
- Parameter **to**:
  - Date only = up to the end (24:00) of the chosen day
  - Date and time = up to, but not including, the shown time

**Example:** An app owner has 1300K daily installs from all sources. To overcome the 1M row limit, the app owner splits the day into two 12-hour URI calls. See the following table for options.

| API call | From | To |
| --- | --- | --- |
| **First API call** | **from** =yyyy-mm-dd<br/>**Example:**<br/>- **from** =`2019-12-29`<br/>- Begins on this date at the beginning of the day at 00:00 | **to** =yyyy-mm-dd 12:00<br/>**Example:**<br/>- **to** =`2019-12-29 12:00`<br/>- Continues up to 11:59:59, not 12:00 |
| **Option A: Second API call**<br/>**Example:**<br/>`&from=2019-12-29 12:00&to=2019-12-29`<br/>- Starts noon 29 Dec 2019<br/>- Ends midnight 29 Dec 2019 | **from** =yyyy-mm-dd 12:00<br/>**Example:**<br/>- **from** =`2019-12-29 12:00`<br/>- Starts from and includes 12:00 | **to** =yyyy-mm-dd<br/>**Example:**<br/>- **to** =`2019-12-29`<br/>- Ends at midnight |
| **Option B: Second API call** | **from** =yyyy-mm-dd 12:00<br/>**Example:**<br/>- **from** =`2019-12-29 12:00`<br/>- Starts from and includes 12:00 | **to** =yyyy-mm-dd+1 00:00<br/>**+1** = next day at 00:00<br/>**Example:**<br/>- **to=**`2019-12-30 00:00`<br/>- Meaning before any time has elapsed on 30 Dec. |
| **Note:** Use option A or B as they have the same results. | | |

### Additional fields

Additional report fields are not added to the default list of fields so that new fields don\'t impact your existing import and ingestion processes. Use the `additional_fields` parameter to get non-default fields.

- List a field only once.
- See the [list of available fields](https://support.appsflyer.com/hc/articles/208387843).
- Example: `additional_fields=device_download_time,deeplink_url`

### Default fields

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

## Additional information

### Traits and limitations

| Trait | Comments |
| --- | --- |
| API token type required | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/ff3f7349af66b7b80d311953567eef821eec56d46146fa9ad7c43d73dd2f8af5-33379479626641.png)[V2.0 token](https://support.appsflyer.com/hc/articles/360004562377-Managing-API-tokens) |
| Ad network access | No |
| Agency access | Yes |
| Agency transparency | Yes. However, note that if you use both the agency filter and media source filters, the media source filters don\'t apply for non-transparent agencies. This means that for non-transparent agencies, all data is included; not just data from the filtered media sources. |
| App-specific currency | Yes |
| App-specific timezone | Yes |
| Data freshness | - Equivalent to the availability of the data in the overview dashboard.<br/>- Reports updated with a lag of a few hours:<br/><br/><br/>- Organic in-app events<br/>- Reports updated Daily:<br/>- Uninstalls<br/>- Post-attribution in-app events<br/>- Ad revenue |
| Historical data | Yes. According to [retention](https://support.appsflyer.com/hc/articles/360006091197) and [rate limitation](https://support.appsflyer.com/hc/articles/207034366) policies. |
| Non-organic data | Yes |
| Organic data | Yes |
| Rate limitation | API limitations for [raw data](https://support.appsflyer.com/hc/articles/207034366). |
| Size limitations | - API calls return a max. of 200K/1M rows.<br/>- If a report has exactly 200K/1M rows, then assume rows are missing.<br/>- Use the maximum\_rows parameter to select the maximum number of rows.<br/>- Make multiple API calls, using from/to parameters that include the time of day. |
| Install\_date from and install\_date\_to | Install date range must be earlier than the activity date range. |

### Troubleshooting

| Symptom/message | Solution |
| --- | --- |
| The report doesn\'t contain the data expected according to the selected time range or there is a discrepancy between the raw data report and aggregated data report. | Verify that you have set the `timezone` parameter. If you don\'t, data is sent using UTC and not your app time zone. |

<Cards>
  <Card title="Selecting the right data delivery tool/reporting API" href="https://support.appsflyer.com/hc/articles/209680773-raw%20data-reporting-overview#reporting-tools%E2%80%94characteristics-and-features">
    Learn how to choose the best reporting tool or API for your data delivery needs.
  </Card>
</Cards>
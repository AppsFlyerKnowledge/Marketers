---
title: "Master API—user acquisition metrics via API"
excerpt: "Get selected LTV, activity, retention, cohort, and Protect360 campaign performance KPIs by API, in CSV or JSON format."
---
At a glance: Get selected LTV, activity, retention, cohort, and Protect360 campaign performance KPIs by API, in CSV or JSON format. Select 1 or more apps.

## Master API—user acquisition metrics via API

Master API:

- Lets you get selected LTV, activity, retention, cohort, and Protect360 campaign performance KPIs. The KPIs available are the equivalent KPIs of those found in the Overview, Activity, Retention, Cohort, and Protect360 dashboards.
- Is calculated daily. The updated data is available to you within 24-48 hours, depending on your app-specific timezone.
- Is the infrastructure upon which the AppsFlyer [pivot table](https://support.appsflyer.com/hc/articles/115001421846-AppsFlyer-Pivot-) is built.

To use Master API, you define the data that you want to view (similar to the implementation of the [Pull API](https://support.appsflyer.com/hc/articles/207034346-Pull-APIs-Pulling-AppsFlyer-Reports-by-APIs)). The result returns as a CSV or JSON file.

**To use Master API**:

1. Get the [API token](https://support.appsflyer.com/hc/articles/360004562377). An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the parameters to input when they make the API call, as described in the sections that follow. The parameters determine what the report focuses on, how it's organized, and provide a reporting timeframe.
4. Tell your developer to follow their [Master API instructions](https://dev.appsflyer.com/hc/reference/overview-9) in the developer hub.
5. ### API parameters

| Parameter | Value | Mandatory |
| --- | --- | --- |
| app\_id | - App identifier, as found in AppsFlyer.<br>   - Insert the app ID exactly as found in AppsFlyer<br>   - Prefix iOS apps with **id**<br>   - Use **all app IDs** to query for all your apps | Yes |
| from | Lower-bound of the LTV attribution date range.<br>   - Format: String yyyy-mm-dd<br>   - Example: `from: 2020-01-02` | Yes |
| to | Upper-bound of the LTV attribution date range<br>   - Number of the days in the range: 1-31 days<br>   - For a single day: `from` and `to` values are identical. <br>   - Format: yyyy-mm-dd<br>   - Example: `from: 2021-01-01, to: 2021-01-31` is 31 days. | Yes |
| [Groupings](https://support.appsflyer.com/hc/articles/213223166#groupings) | Group by parameters, separated by a comma. See the Groupings table for the list available <br>Example: `groupings=pid,geo` | Yes |
| [KPIs](https://support.appsflyer.com/hc/articles/213223166#kpis) | List of KPIs to include, each separated by a comma. See the KPI table that follows for a list of KPIs.<br>Example: `kpis=installs,clicks, impressions,sessions,retention_day_7` | Yes |
| [Filters](https://support.appsflyer.com/hc/articles/213223166#filters-optional) | Data can be filtered using one or more filter options. | No |
| [Currency](https://support.appsflyer.com/hc/articles/213223166#localization) | To return data using the app-specific currency set currency=preferred | No |
| [Timezone](https://support.appsflyer.com/hc/articles/213223166#localization) | To return data using the app-specific timezone set timezone=preferred.  See [localization rules](https://support.appsflyer.com/hc/articles/213223166#localization) | No |
| Format | By default, the response data is received in CSV file format. If you prefer to get the data in JSON format, select `format=json`. | No |

### Groupings

These dimensions are used for collecting the data into groups to allow easier and more accurate examination of the information. You can find descriptions of these fields [here](https://support.appsflyer.com/hc/articles/208387843).

| Group by<br>API name | Group by display name | LTV KPIs | Retention KPIs | Activity KPIs | Protect360 | Cohort |
| --- | --- | --- | --- | --- | --- | --- |
| app\_id | App ID | Yes | Yes | Yes | Yes | Yes |
| pid | Media source | Yes | Yes | Yes | Yes | Yes |
| af\_prt | Agency | Yes | Yes | Yes | Yes | No |
| c | Campaign | Yes | Yes | Yes | Yes | Yes |
| af\_adset | Adset | Yes | Yes | Yes | No | No |
| af\_ad | Ad | Yes | Yes | Yes | No | No |
| af\_channel | Channel | Yes | Yes | Yes | Yes | No |
| af\_siteid | Publisher ID | Yes | Yes | Yes | Yes | Yes |
| af\_keywords | Keywords | Yes | Yes | Yes | No | No |
| is\_primary | Is primary attribution | Yes | No | Yes | Yes | No |
| af\_c\_id | Campaign ID | Yes | No | Yes | Yes | No |
| af\_adset\_id | Adset ID | Yes | No | Yes | No | No |
| af\_ad\_id | Ad ID | Yes | No | Yes | No | No |
| install\_time | Install Time | Yes | Yes | Yes\* | Yes | Yes |
| attributed\_touch\_type | Touch Type | Yes | Yes | Yes | Yes | No |
| geo | Geo | Yes | Yes | Yes | Yes | Yes |
| \* In the context of Activity KPIs, regard install time as event time. |

### KPIs

KPIs are the metrics used for gaining insights into the behavior of your app. The KPIs are grouped by type in the sections that follow.

#### LTV

Lifetime Value - Aggregate Events segmented by install day up and until today

| KPI API name | Description |
| --- | --- |
| impressions | Number of impressions within the selected time frame |
| clicks | Number of clicks within the selected time frame |
| installs | Number of installs within the selected time frame |
| cr | Conversion Rate |
| sessions | Number of sessions created by the users who installed within the selected time frame |
| loyal\_users | Number of loyal users who installed within the selected time frame |
| loyal\_users\_rate | Loyal users/installs |
| cost | Total cost in the selected time frame. [See limitations](https://support.appsflyer.com/hc/articles/213223166#limitations). |
| revenue | Lifetime revenue generated by the users who installed in the selected time frame |
| roi | Return on Investment over a certain time frame |
| arpu\_ltv | Average revenue per user, for the users who installed in the selected time frame |
| average\_ecpi | Effective Cost per Installation (eCPI) over a certain time frame. Available only if cost and installs are included in the call. |
| uninstalls | Uninstalling users, who installed in the selected time frame |
| uninstalls\_rate | Uninstallation rate |
| event\_counter\_[event\_name] | Number of event occurrences |
| unique\_users\_[event\_name] | Number of unique users who performed the event |
| sales\_in\_usd\_[event\_name] | Revenue reported as part of the reported events |

#### Retention

Retention is a measure of how many existing users are active in your app.

> 📘 Note
>
> - The maximum retention day number is 30 days post-install, where day 0 is the install day. This means that value [x] cannot exceed 30.
> - If you request retention_day_1, before the data for that day is available then the metric that returns relates to users installing on the previous day. For example, on Jan 2, you request retention_day_1 for users who installed on Jan 1. Because the metric isn't yet available, the metric that returns relates to users who installed on Dec 31.

| KPI | Description |
| --- | --- |
| retention\_day\_[x] | Number of retained users at day X |
| retention\_rate\_day\_[x] | Number of retained users at day X out of installing users |

#### Activity

App activity occurring during a selected date range. **Note**: Activity KPIs include unified data (UA and retargeting together).

| KPI | Description |
| --- | --- |
| activity\_average\_dau | Average daily active users (DAU) within the selected time frame |
| activity\_average\_mau | Average monthly active users within the selected time frame (one MAU day represents the unique users in the preceding 30 days) |
| activity\_average\_dau\_mau\_rate | Average DAU/MAU rate |
| activity\_average\_arpdau | Average revenue per daily active user - the average revenue of a given day out of all unique users |
| activity\_sessions | Number of sessions performed within the selected time frame |
| activity\_revenue | Revenue reported within the selected time frame |
| activity\_event\_counter\_[event\_name] | Number of events generated by users within the selected time frame |
| activity\_sales\_in\_usd\_[event\_name] | Revenue reported as part of the reported events within the selected time frame |
| activity\_average\_unique\_users\_[event\_name] | Average unique users performing a given event within the selected time frame |

#### Cohort

AppsFlyer Cohorts provide advertisers with the ability to view and compare different metrics for multiple cohorts over different time frames.

> 📘 Note
>
> - **Rounding errors:** Cohort per user KPIs are calculated using four decimal places. This means that if the calculated value per user is < 0.0001 then this shows as 0. For example, the number of users is 100,000, and total revenue is $9. The revenue per user is 9/100000=0.00009. As 0.00009<0.0001 the value shown will be 0.
> - **Cohort days**: The maximum cohort day number is 90 days post-install where day 0 is the install day. The cohort day value [x] must be in the range of 1-90. **Note**: cohort_day_0 isn't supported in Mater API, even though it's supported in the Cohort dashboard.
> - **Master API vs. Cohort API and** [**Cohort dashboard:**](https://support.appsflyer.com/hc/articles/207040496-Cohort-dashboard) Results may differ due to different handling of reinstalls and timing issues.

**Sessions**

| KPI | Description |
| --- | --- |
| cohort\_day\_[x]\_total\_sessions\_per\_user | Cohort Day x - Cumulative sessions per user up to day x (including day x) |
| cohort\_day\_[x]\_sessions\_per\_user | Cohort Day x - Sessions on day x only from the cohort |
| cohort\_[x]\_days\_total\_sessions\_per\_user | Replaces specifying KPIs Cohort\_day\_1\_total\_sessions\_per\_user to Cohort\_day\_x\_total\_sessions\_per\_user on the URL.<br>For example: cohort\_3\_days\_total\_sessions\_per\_user on the URL produces 3 report columns:<br>Cohort\_day\_1\_total\_sessions\_per\_user+ Cohort\_day\_2\_total\_sessions\_per\_user+Cohort\_day\_3\_total\_sessions\_per\_user |

**Revenue**

| KPI | Description |
| --- | --- |
| cohort\_day\_[x]\_total\_revenue\_per\_user | Cohort Day x - Cumulative revenue per user up to day x (including day x) |
| cohort\_day\_[x]\_revenue\_per\_user | Cohort Day x - ARPU received on day x only from the cohort |
| cohort\_[x]\_days\_total\_revenue\_per\_user | Replaces specifying KPIs Cohort\_day\_1\_total\_revenue\_per\_user to Cohort\_day\_x\_total\_revenue\_per\_user.<br>For example: cohort\_3\_days\_total\_revenue\_per\_user on the URL produces 3 report columns:<br>Cohort\_day\_1\_total\_revenue\_per\_user+ Cohort\_day\_2\_total\_revenue\_per\_user+Cohort\_day\_3\_total\_revenue\_per\_user |
| cohort\_day\_[x]\_total\_event\_[eventname]\_revenue\_per\_user | Cohort Day x accumulative revenue per user according to specific in-app event |
| cohort\_day\_[x]\_event\_[eventname]\_revenue\_per\_user | Cohort Day x revenue per user according to specific in-app event |

**Events**

| KPI | Description |
| --- | --- |
| cohort\_day\_[x]\_total\_event\_[eventname]\_per\_user | Cohort Day x - Cumulative events per user up to day x (including day x) |
| cohort\_day\_[x]\_event\_[eventname]\_per\_user | Cohort Day x - Events received on day x only from the cohort |
| cohort\_[x]\_days\_total\_event\_[eventname]\_per\_user | Replaces specifying KPIs events to Cohort\_day\_x\_total\_events\_per\_user.<br>For example: cohort\_3\_days\_total\_events\_per\_user on the URL produces 3 report columns:<br>Cohort\_day\_1\_total\_events\_per\_user+ Cohort\_day\_2\_total\_events\_per\_user+Cohort\_day\_3\_total\_events\_per\_user |

#### Protect360

**Protect360 KPIs**

| Description | KPI |
| --- | --- |
| **Installs** |  |
| Total | protect360\_total\_installs |
| Blocked | blocked\_installs |
| Blocked % | blocked\_installs\_rate |
| Post-attribution | post\_attribution\_installs |
| Post-attribution % | post\_attribution\_installs\_rate |
| Total fraudulent installs | total\_fraudulent\_installs |
| Fraudulent installs % | fraudulent\_installs\_rate |
| **Fake installs** |  |
| Real-time block | real\_time\_fake\_installs |
| Post-attribution fraud | post\_attribution\_fake\_installs |
| **Hijacked installs** |  |
| Real-time block | real\_time\_hijacked\_installs |
| Post-attribution fraud | post\_attribution\_installs\_hijacked\_installs |
| **Validation rules** |  |
| Blocked installs | validation\_rules\_blocked\_installs |
| Blocked attribution | validation\_rules\_blocked\_attribution |
| **Fake installs block breakdown** |  |
| Blocked site ID blacklist | blocked\_installs\_siteid\_blacklist |
| Post-attribution site ID blacklist | post\_attribution\_installs\_siteid\_blacklist |
| Blocked bots | blocked\_installs\_bots |
| Post-attribution bots | post\_attribution\_installs\_bots |
| Blocked behavioral anomalies | blocked\_installs\_behavioral\_anomalies |
| Post-attribution behavioral anomalies | post\_attribution\_installs\_behavioral\_anomalies |
| Blocked install validation | blocked\_installs\_install\_validation |
| **Hijacked installs block breakdown** |  |
| Blocked install hijacking | blocked\_installs\_install\_hijacking |
| Post-attribution install hijacking | post\_attribution\_installs\_installs\_hijacking |
| Blocked CTIT anomalies | blocked\_installs\_ctit\_anomalies |
| Post-attribution CTIT anomalies | post\_attribution\_installs\_ctit\_anomalies |
| Blocked click flooding | blocked\_installs\_click\_flood |
| Post-attribution click flooding | post\_attribution\_installs\_click\_flood |
| **Clicks** |  |
| Total | protect360\_total\_clicks |
| Blocked | blocked\_clicks |
| % | blocked\_clicks\_rate |
| **In-App Events** |  |
| Total | protect360\_total\_in\_apps |
| Blocked | blocked\_in-app-events |
| % | blocked\_in-app-events\_rate |
| Device farm indicators - new devices |  |
| Installs | install\_fraud\_new\_devices\_total |
| Installs % | install\_fraud\_new\_devices\_total\_installs\_rate |
| Loyal user % | install\_fraud\_new\_devices\_total\_loyal\_user\_rate |
| **Device farm indicators - LAT devices** |  |
| Installs | install\_fraud\_lat\_devices\_total |
| Installs % | install\_fraud\_lat\_devices\_total\_installs\_rate |
| Loyal user % | install\_fraud\_lat\_devices\_total\_loyal\_user\_rate |
| **Click flooding indicators** |  |
| Conversion rate | conversion\_rate |
| **Click flooding indicators - CTIT** |  |
| Over 60 minutes | click\_flood\_over\_1\_hour\_rate |
| Over 5 hours | click\_flood\_over\_5\_hours\_rate |

#### Calculated KPIs

In addition, to the KPIs described previously, you can add calculated KPIs to your master API reports. This enables you to have your own calculated reports included in your Master API reports.

You can insert any number of built-in KPI objects in the calculated KPI formulas. Each calculation KPI object includes a key and a value. The key is the name you give the KPI and the value is the KPI formula.

Standard arithmetic operators are supported: addition (+) encoded as %2b, subtraction (-), multiplication (\*), division (/) encoded as %2f.

Calculated KPI field keys **must** start with "calculated\_kpi\_", followed by any valid string, such as, "calculated\_kpi\_purchaserate".

#### Example

<Tabs>
<Tab title="First three days combined retention">

```auto
Autokpis=installs,loyal_users_rate&calculated_kpi_3days_retention=
retention_day_1%2Bretention_day_2%2Bretention_day_3
```

</Tab>
<Tab title="Average revenue per impression">

```auto
Autokpis=installs&calculated_kpi_rev_per_impression=revenue%2Fimpression
```

</Tab>
<Tab title="Cohort day 7 ROI">

```auto
Autokpis=installs,roi,arpu_ltv,cost,revenue&calculated_kpi_roi_day_7=
(cohort_day_7_total_revenue_per_user-average_ecpi)%2Faverage_ecpi
```

</Tab>
</Tabs>

### Filters (optional)

| Parameter | Description | Example | Mandatory? |
| --- | --- | --- | --- |
| pid | - Used for selecting the rows, in which the specified media source/s are displayed.<br>   - Comma-separated multiple selection is supported. | pid=organic,applovin\_int | No |
| c | - Used for filtering by campaign name.<br>   - Comma-separated multiple selection is supported. | c=my\_sample\_campaign | No |
| af\_prt | - Used for filtering by agency name.<br>   - Comma-separated multiple selection is supported. | af\_prt=moburst | No |
| af\_channel | - Used for filtering by channel name.<br>   - Comma-separated multiple selection is supported. | af\_channel=Instagram | No |
| af\_siteid | - Used for filtering by publisher ID.<br>   - Comma-separated multiple selection is supported. | af\_siteid=12345678 | No |
| geo | - Used for filtering by country.<br>   - Comma-separated multiple selection is supported. | geo=US,DE | No |

### Localization

Local currency and app-specific timezone are set on the [app settings page](/docs/app-settings). Master API data can extract the data using either the system's default currency and timezone or using the app-specific timezone and currency.

The following applies:

   - Using the app-specific timezone/currency is supported only if all apps have the same timezone/currency. Otherwise, UTC and USD are used. Timezone and currency are separate. Meaning that if the currency of all apps is the same but the timezones aren't, then you can use the app-specific currency but not the app-specific timezone.
   - If the preferred timezone was changed in the dashboard within the requested time range, the generated report contains values starting from the most recent timezone change.

Use the following parameters to select the app-specific setting. **Note**: If you don't use the preferred parameters, you get the default settings, which are USD for currency and UTC for timezone.

| Parameter | Description | Example | Mandatory? |
| --- | --- | --- | --- |
| currency | Monetary values are in the app-specific currency | currency=preferred | No |
| timezone | Timezone used is according to the app-specific timezone | timezone=preferred | No |

## Additional information

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| Cost data | - Availability of different cost dimensions meaning adset, ad, geo, channel, and site ID is [ad network dependent](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api). <br>- To get eCPI: If the cost data is available, include both installs and cost in the call. <br>- In general, all sources, including owned media, which use AppsFlyer links and have the cost parameter on the links, fully support cost data, regardless of the requested dimensions. Self-reporting networks, with their own API, usually support cost data with only some of the available dimensions. For example, [Meta ads](https://support.appsflyer.com/hc/articles/4410472805649#what-are-the-limitations-of-facebook-cost-data-in-master-api) doesn’t support grouping by Geo and Channel in the same call. Grouping by either of them separately is supported.<br>- Campaigns that have cost data, but no installs data in the recent past (approx. 7 days), are not available via Master API. |
| Groupings | Specific groupings are only available for LTV KPIs, Activity, or Retention KPIs. The API returns N/A when the data for a specific KPI is not available. For example, requesting retention\_rate\_day\_7 grouped by af\_channel returns N/A. |
| Dimensions | For cohort data, if an agency is involved in the attribution, the returned media source is the agency name |
| Maximum rows per report | 200K |
| Event names | Master API currently doesn't support event names that include a forward-slash `/` . To overcome this limitation, avoid the user of `/` in event names. |
| Processing time | Selecting more than one app increases the processing time and the response may take longer. |
| Date range | Timeframe granularity is daily. |
| Agencies | Master API not available |
| Ad networks | Master API not available |
| Historical data | - LTV data: 25 months (2 years + 1 month)<br>- Cohort data (daily cohort): 2 years<br>- Activity data: 3 years |
| Retargeting | - Not supported.<br>- Exception: Activity KPIs for traffic from after February 1, 2025 include unified data (UA and retargeting together). |
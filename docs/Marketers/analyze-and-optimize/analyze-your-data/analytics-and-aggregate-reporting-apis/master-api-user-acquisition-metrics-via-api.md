---
title: Master API—user acquisition metrics via API
metadata:
  keywords:
    - Master API
    - Customizable
    - Aggregated Data
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-09-27T15:10:38Z'
  edited_at: '2026-03-18T09:00:26Z'
  id: 213223166
  locale: en-us
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/213223166-Master-API-user-acquisition-metrics-via-API
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Get selected LTV, activity, retention, cohort, and Protect360 campaign performance KPIs by API, in CSV or JSON format. Select 1 or more apps.

<div id="master-apiuser-acquisition-metrics-via-api" />

## Master API—user acquisition metrics via API

Master API:

* Lets you get selected LTV, activity, retention, cohort, and Protect360 campaign performance KPIs. The KPIs available are the equivalent KPIs of those found in the Overview, Activity, Retention, Cohort, and Protect360 dashboards.
* Is calculated daily. The updated data is available to you within 24-48 hours, depending on your app-specific timezone.
* Is the infrastructure upon which the AppsFlyer <Anchor target="_blank" href="/marketers/docs/pivot-table-user-metrics">pivot table</Anchor> is built.

To use Master API, you define the data that you want to view (similar to the implementation of the <Anchor target="_blank" href="/marketers/docs/pull-api-aggregate-data">Pull API</Anchor>). The result returns as a CSV or JSON file.

**To use Master API**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/11471b4014e8a4805ff15397166298cd02b4df7707bacb62c936f1513dbe34a5-16574754168721.png) Get the <Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens">API token</Anchor>. An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the parameters to input when they make the API call, as described in the sections that follow. The parameters determine what the report focuses on, how it's organized, and provide a reporting timeframe.
4. Tell your developer to follow their <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-9">Master API instructions</Anchor> in the developer hub.
5.
   <div id="api-parameters" />

   <Accordion title="API parameters">

   | Parameter | Value | Mandatory |
   | --- | --- | --- |
   | app\_id | * App identifier, as found in AppsFlyer.<br />* Insert the app ID exactly as found in AppsFlyer<br />* Prefix iOS apps with **id**<br />* Use **all app IDs** to query for all your apps | Yes |
   | from | Lower-bound of the LTV attribution date range.<br /><br />* Format: String yyyy-mm-dd<br />* Example: `from: 2020-01-02` | Yes |
   | to | Upper-bound of the LTV attribution date range<br /><br />* Number of the days in the range: 1-31 days<br />* For a single day: `from` and `to` values are identical.<br />* Format: yyyy-mm-dd<br />* Example: `from: 2021-01-01, to: 2021-01-31` is 31 days. | Yes |
   | [Groupings](/docs/master-api-user-acquisition-metrics-via-api#groupings) | Group by parameters, separated by a comma. See the Groupings table for the list available <br /><br />Example: `groupings=pid,geo` | Yes |
   | [KPIs](/docs/master-api-user-acquisition-metrics-via-api#kpis) | List of KPIs to include, each separated by a comma. See the KPI table that follows for a list of KPIs.<br /><br />Example: `kpis=installs,clicks, impressions,sessions,retention_day_7` | Yes |
   | [Filters](/docs/master-api-user-acquisition-metrics-via-api#filters-optional) | Data can be filtered using one or more filter options. | No |
   | [Currency](/docs/master-api-user-acquisition-metrics-via-api#localization) | To return data using the app-specific currency set currency=preferred | No |
   | [Timezone](/docs/master-api-user-acquisition-metrics-via-api#localization) | To return data using the app-specific timezone set timezone=preferred.  See [localization rules](/docs/master-api-user-acquisition-metrics-via-api#localization) | No |
   | Format | By default, the response data is received in CSV file format. If you prefer to get the data in JSON format, select `format=json`. | No |

   </Accordion>

   <div id="groupings" />

   <Accordion title="Groupings">

   These dimensions are used for collecting the data into groups to allow easier and more accurate examination of the information. You can find descriptions of these fields <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary">here</Anchor>.

   <table><thead><tr><th>Group by<br/>API name</th><th>Group by display name</th><th>LTV KPIs</th><th>Retention KPIs</th><th>Activity KPIs</th><th>Protect360</th><th>Cohort</th></tr></thead><tbody><tr><td>app_id</td><td>App ID</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td>pid</td><td>Media source</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td>af_prt</td><td>Agency</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td></tr><tr><td>c</td><td>Campaign</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td>af_adset</td><td>Adset</td><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td></tr><tr><td>af_ad</td><td>Ad</td><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td></tr><tr><td>af_channel</td><td>Channel</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td></tr><tr><td>af_siteid</td><td>Publisher ID</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td>af_keywords</td><td>Keywords</td><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td></tr><tr><td>is_primary</td><td>Is primary attribution</td><td>Yes</td><td>No</td><td>Yes</td><td>Yes</td><td>No</td></tr><tr><td>af_c_id</td><td>Campaign ID</td><td>Yes</td><td>No</td><td>Yes</td><td>Yes</td><td>No</td></tr><tr><td>af_adset_id</td><td>Adset ID</td><td>Yes</td><td>No</td><td>Yes</td><td>No</td><td>No</td></tr><tr><td>af_ad_id</td><td>Ad ID</td><td>Yes</td><td>No</td><td>Yes</td><td>No</td><td>No</td></tr><tr><td>install_time</td><td>Install Time</td><td>Yes</td><td>Yes</td><td>Yes\*</td><td>Yes</td><td>Yes</td></tr><tr><td>attributed_touch_type</td><td>Touch Type</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td></tr><tr><td>geo</td><td>Geo</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td colspan="7">\* In the context of Activity KPIs, regard install time as event time. </td></tr></tbody></table>

   </Accordion>

   <div id="kpis" />

   <Accordion title="KPIs">

   KPIs are the metrics used for gaining insights into the behavior of your app. The KPIs are grouped by type in the sections that follow.

   <div id="ltv" />

   <Accordion title="LTV">

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
   | cost | Total cost in the selected time frame. [See limitations](/docs/master-api-user-acquisition-metrics-via-api#limitations). |
   | revenue | Lifetime revenue generated by the users who installed in the selected time frame |
   | roi | Return on Investment over a certain time frame |
   | arpu\_ltv | Average revenue per user, for the users who installed in the selected time frame |
   | average\_ecpi | Effective Cost per Installation (eCPI) over a certain time frame. Available only if cost and installs are included in the call. |
   | uninstalls | Uninstalling users, who installed in the selected time frame |
   | uninstalls\_rate | Uninstallation rate |
   | event\_counter\_[event\_name] | Number of event occurrences |
   | unique\_users\_[event\_name] | Number of unique users who performed the event |
   | sales\_in\_usd\_[event\_name] | Revenue reported as part of the reported events |

   </Accordion>

   <div id="retention" />

   <Accordion title="Retention">

   Retention is a measure of how many existing users are active in your app.

   **Note:**

   * The maximum retention day number is 30 days post-install, where day 0 is the install day. This means that value [x] cannot exceed 30.
   * If you request retention\_day\_1, before the data for that day is available then the metric that returns relates to users installing on the previous day. For example, on Jan 2, you request retention\_day\_1 for users who installed on Jan 1. Because the metric isn't yet available, the metric that returns relates to users who installed on Dec 31.

   | KPI | Description |
   | --- | --- |
   | retention\_day\_[x] | Number of retained users at day X |
   | retention\_rate\_day\_[x] | Number of retained users at day X out of installing users |

   </Accordion>

   <div id="activity" />

   <Accordion title="Activity">

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

   </Accordion>

   <div id="cohort" />

   <Accordion title="Cohort">

   AppsFlyer Cohorts provide advertisers with the ability to view and compare different metrics for multiple cohorts over different time frames.

   **Note:**

   * **Rounding errors:** Cohort per user KPIs are calculated using four decimal places. This means that if the calculated value per user is &lt; 0.0001 then this shows as 0. For example, the number of users is 100,000, and total revenue is $9. The revenue per user is 9/100000=0.00009. As 0.00009&lt;0.0001 the value shown will be 0.
   * **Cohort days**: The maximum cohort day number is 90 days post-install where day 0 is the install day. The cohort day value [x] must be in the range of 1-90.  **Note**: cohort\_day\_0 isn't supported in Mater API, even though it's supported in the Cohort dashboard.
   * **Master API vs. Cohort API and** <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard">**Cohort dashboard:**</Anchor> Results may differ due to different handling of reinstalls and timing issues.

   **Sessions**

   | KPI | Description |
   | --- | --- |
   | cohort\_day\_[x]\_total\_sessions\_per\_user | Cohort Day x - Cumulative sessions per user up to day x (including day x) |
   | cohort\_day\_[x]\_sessions\_per\_user | Cohort Day x - Sessions on day x only from the cohort |
   | cohort\_[x]\_days\_total\_sessions\_per\_user | Replaces specifying KPIs Cohort\_day\_1\_total\_sessions\_per\_user to Cohort\_day\_x\_total\_sessions\_per\_user on the URL.<br /><br />For example: cohort\_3\_days\_total\_sessions\_per\_user on the URL produces 3 report columns:  <br />Cohort\_day\_1\_total\_sessions\_per\_user+ Cohort\_day\_2\_total\_sessions\_per\_user+Cohort\_day\_3\_total\_sessions\_per\_user |

   **Revenue**

   | KPI | Description |
   | --- | --- |
   | cohort\_day\_[x]\_total\_revenue\_per\_user | Cohort Day x - Cumulative revenue per user up to day x (including day x) |
   | cohort\_day\_[x]\_revenue\_per\_user | Cohort Day x - ARPU received on day x only from the cohort |
   | cohort\_[x]\_days\_total\_revenue\_per\_user | Replaces specifying KPIs Cohort\_day\_1\_total\_revenue\_per\_user to Cohort\_day\_x\_total\_revenue\_per\_user.<br /><br />For example: cohort\_3\_days\_total\_revenue\_per\_user on the URL produces 3 report columns:  <br />Cohort\_day\_1\_total\_revenue\_per\_user+ Cohort\_day\_2\_total\_revenue\_per\_user+Cohort\_day\_3\_total\_revenue\_per\_user |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_revenue\_per\_user | Cohort Day x accumulative revenue per user according to specific in-app event |
   | cohort\_day\_[x]\_event\_[eventname]\_revenue\_per\_user | Cohort Day x revenue per user according to specific in-app event |

   **Events**

   | KPI | Description |
   | --- | --- |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_per\_user | Cohort Day x - Cumulative events per user up to day x (including day x) |
   | cohort\_day\_[x]\_event\_[eventname]\_per\_user | Cohort Day x - Events received on day x only from the cohort |
   | cohort\_[x]\_days\_total\_event\_[eventname]\_per\_user | Replaces specifying KPIs events to Cohort\_day\_x\_total\_events\_per\_user.<br /><br />For example: cohort\_3\_days\_total\_events\_per\_user on the URL produces 3 report columns:  <br />Cohort\_day\_1\_total\_events\_per\_user+ Cohort\_day\_2\_total\_events\_per\_user+Cohort\_day\_3\_total\_events\_per\_user |

   </Accordion>

   <div id="protect360" />

   <Accordion title="Protect360">

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

   </Accordion>

   <div id="calculated-kpis" />

   #### Calculated KPIs

   In addition, to the KPIs described previously, you can add calculated KPIs to your master API reports. This enables you to have your own calculated reports included in your Master API reports.

   You can insert any number of built-in KPI objects in the calculated KPI formulas. Each calculation KPI object includes a key and a value. The key is the name you give the KPI and the value is the KPI formula.

   Standard arithmetic operators are supported: addition (+) encoded as %2b, subtraction (-), multiplication (*), division (/) encoded as %2f.

   Calculated KPI field keys **must** start with "calculated\_kpi\_", followed by any valid string, such as, "calculated\_kpi\_purchaserate".

   <div id="example" />

   > 📄 **Example**
   >
   > **First three days combined retention**
   >
   > ```http
   > kpis=installs,loyal_users_rate&calculated_kpi_3days_retention=
   > retention_day_1%2Bretention_day_2%2Bretention_day_3
   > ```
   >
   > **Average revenue per impression**
   >
   > ```http
   > kpis=installs&calculated_kpi_rev_per_impression=revenue%2Fimpression
   > ```
   >
   > **Cohort day 7 ROI**
   >
   > ```http
   > kpis=installs,roi,arpu_ltv,cost,revenue&calculated_kpi_roi_day_7=
   > (cohort_day_7_total_revenue_per_user-average_ecpi)%2Faverage_ecpi
   > ```

   </Accordion>

   <div id="filters-optional" />

   <Accordion title="Filters (optional)">

   | Parameter | Description | Example | Mandatory? |
   | --- | --- | --- | --- |
   | pid | * Used for selecting the rows, in which the specified media source/s are displayed.<br />* Comma-separated multiple selection is supported. | pid=organic,applovin\_int | No |
   | c | * Used for filtering by campaign name.<br />* Comma-separated multiple selection is supported. | c=my\_sample\_campaign | No |
   | af\_prt | * Used for filtering by agency name.<br />* Comma-separated multiple selection is supported. | af\_prt=moburst | No |
   | af\_channel | * Used for filtering by channel name.<br />* Comma-separated multiple selection is supported. | af\_channel=Instagram | No |
   | af\_siteid | * Used for filtering by publisher ID.<br />* Comma-separated multiple selection is supported. | af\_siteid=12345678 | No |
   | geo | * Used for filtering by country.<br />* Comma-separated multiple selection is supported. | geo=US,DE | No |

   </Accordion>

   <div id="localization" />

   <Accordion title="Localization">

   Local currency and app-specific timezone are set on the <Anchor target="_blank" href="/marketers/docs/app-settings">app settings page</Anchor>. Master API data can extract the data using either the system's default currency and timezone or using the app-specific timezone and currency.

   The following applies:

   * Using the app-specific timezone/currency is supported only if all apps have the same timezone/currency. Otherwise, UTC and USD are used. Timezone and currency are separate. Meaning that if the currency of all apps is the same but the timezones aren't, then you can use the app-specific currency but not the app-specific timezone.
   * If the preferred timezone was changed in the dashboard within the requested time range, the generated report contains values starting from the most recent timezone change.

   Use the following parameters to select the app-specific setting. **Note**: If you don't use the preferred parameters, you get the default settings, which are USD for currency and UTC for timezone.

   | Parameter | Description | Example | Mandatory? |
   | --- | --- | --- | --- |
   | currency | Monetary values are in the app-specific currency | currency=preferred | No |
   | timezone | Timezone used is according to the app-specific timezone | timezone=preferred | No |

   </Accordion>

<div id="additional-information" />

## Additional information

<div id="limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Cost data | <ul><li>Availability of different cost dimensions meaning adset, ad, geo, channel, and site ID is <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network dependent</Anchor>.</li><li>To get eCPI: If the cost data is available, include both installs and cost in the call.</li><li>In general, all sources, including owned media, which use AppsFlyer links and have the cost parameter on the links, fully support cost data, regardless of the requested dimensions. Self-reporting networks, with their own API, usually support cost data with only some of the available dimensions. For example, <Anchor target="_blank" href="/marketers/docs/meta-ads-faq#what-are-the-limitations-of-facebook-cost-data-in-master-api">Meta ads</Anchor> doesn’t support grouping by Geo and Channel in the same call. Grouping by either of them separately is supported.</li><li>Campaigns that have cost data, but no installs data in the recent past (approx. 7 days), are not available via Master API.</li></ul> |
| Groupings | Specific groupings are only available for LTV KPIs, Activity, or Retention KPIs. The API returns N/A when the data for a specific KPI is not available. For example, requesting retention\_rate\_day\_7 grouped by af\_channel returns N/A. |
| Dimensions | For cohort data, if an agency is involved in the attribution, the returned media source is the agency name |
| Maximum rows per report | 200K |
| Event names | Master API currently doesn't support event names that include a forward-slash `/` . To overcome this limitation, avoid the user of `/` in event names. |
| Processing time | Selecting more than one app increases the processing time and the response may take longer. |
| Date range | Timeframe granularity is daily. |
| Agencies | Master API not available |
| Ad networks | Master API not available |
| Historical data | <ul><li>LTV data: 25 months (2 years + 1 month)</li><li>Cohort data (daily cohort): 2 years</li><li>Activity data: 3 years</li></ul> |
| Retargeting | <ul><li>Not supported.</li><li>Exception: Activity KPIs for traffic from after February 1, 2025 include unified data (UA and retargeting together).</li></ul> |

</Accordion>

<div data-zendesk-anchors="master-api%E2%80%94user-acquisition-metrics-via-api=master-apiuser-acquisition-metrics-via-api h_01JJVMXKACJ2V4YZFGYXVB8FQF=master-apiuser-acquisition-metrics-via-api h_01JJVMXKACZDXPQG4271HFYWCE=api-parameters h_01JJVMXKAEXMKQQRT0RT6N8P74=groupings h_01JJVMXKAEHM0871GBQHZENRXA=kpis h_01JK2ZEH32Y92Y553540XDYZFA=ltv h_01JK2ZEH32A08EEDZEWFSX3ZFS=retention h_01JK2ZEH3219694E4PFPZ8ZXZF=activity h_01JK2ZEH32NCWZWKTDS0J6DFS2=cohort h_01JK2ZEH32Q7B6RCQYXNHM8KGK=protect360 h_01JJVMXKAFW1TEE35GK9B20TRP=calculated-kpis h_01JJVMXKAFZDPNXKAZCBQ27DBD=example h_01JJVMXKAFWA4D47MH7VSXKN14=filters-optional h_01JJVMXKAFSBXJ9EJJ16BF8H7Q=localization h_01JJVMXKAFFW2G3N7188DHYCB8=additional-information h_01JJVMXKAF25YX092NE9DV9862=limitations" />

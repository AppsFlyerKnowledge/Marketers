---
title: "Pull API aggregate data"
excerpt: "Learn how to use the AppsFlyer Pull API to retrieve aggregate user acquisition and retargeting reports in CSV format."
---
Use this Pull API to get your AppsFlyer aggregate reports in CSV files.

![PullAPIAverage_us-en.png](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)

#### Looking for Pull API raw data?

Learn all about it [here](https://support.appsflyer.com/hc/articles/360007530258).

## Pull API aggregate data

- Pull API lets you get aggregate data reports for user acquisition (UA) and retargeting in CSV files.
- [Data freshness rates](https://support.appsflyer.com/hc/articles/360000310629-Data-freshness-and-time-zone-support#data-freshness-rates-and-timezone-support) are the same as the equivalent report on the Export Data page and Overview dashboard page. Consider that cost can update with a delay of several hours, depending on the partner providing the cost data.
- Filter by options available: Media source and date range.
- Additional capabilities in Pull API are:
  - Add attribution touch type
  - Select timezone

#### Aggregate performance reports available via Pull API

| Category | UA | Retargeting\* |
| --- | --- | --- |
| Partners (media source) | **✓** | **✓** |
| Partners by date | **✓** | **✓** |
| Daily | **✓** | **✓** |
| Geo | **✓** | **✓** |
| Geo by date report | **✓** | **✓** |
| \* For retargeting reports, add the `&reattr=true` to the URI. | | |

### Using Pull API aggregate data

**To use Pull API aggregate data**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/5dd980a707877c2ab26826170f7f1313bffba1fed8ab3eacb59954770c302932-19754884868369.png) Get the API token. An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the [parameters](https://support.appsflyer.com/hc/articles/207034346#parameters) to input when they make the API call, as described in the section that follow. The parameters determine what the report focuses on, how it's organized, and provide a reporting timeframe.
4. Tell your developer to follow their [Pull API aggregate data instructions](https://dev.appsflyer.com/hc/reference/overview-11) in the developer hub.

### Parameters

| Parameter | Description |
| --- | --- |
| app\_id | Application ID |
| from | - The date range consists of a `from`and `to` parameter. The range is the LTV (install) date range.<br>- Format: `yyyy-mm-dd`, <br>- Example: 2010-01-01 |
| to | End date. As for `from` |
| media\_source | Use to limit (filter) to a specific media source.<br>- Example:`media_source=facebook` |
| attribution\_touch\_type | Set this parameter as shown in the example to get [view-through attribution](https://support.appsflyer.com/hc/articles/207034346) (VTA) KPIs. <br>Example: `attribution_touch_type=impression`<br>Some VTA KPIs, like clicks, impressions, and cost APIs, don't have values associated with them and display the value N/A instead. |
| currency | Currency of revenue and cost.<br>Aggregate Pull API reports always use the app-specific currency. |
| reattr | Get retargeting conversions data.<br>- [Default] If false, user acquisition data (UA) campaigns returns.<br>- If true, retargeting conversion returns.<br>- **Example**:`reattr=true` |
| timezone | [Default] Data returns using UTC.<br>- Template URIs are populated with the timezone parameter set to the app-specific time zone. <br>- [Default] If the parameter is not sent, data returns using UTC.<br>- If you send`timezone=[Joda-Time]`, data returns using the app-specific time zone.<br>Notes about selecting timezones<br>- Joda-Time time zone format takes into account daylight saving time.<br>- The Joda-Time value must be identical to the value in the app settings page. For example, if the timezone setting is Paris, the timezone value in the Pull API URL should be `timezone=Europe%2fParis`.<br>- Pulling data in the selected time zone is only available from the date when the time zone setting was made. Any data prior to the date of the change uses UTC as the timezone. |

### Traits and limitations

| Trait | Comments |
| --- | --- |
| API token type required | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/5dd980a707877c2ab26826170f7f1313bffba1fed8ab3eacb59954770c302932-19754884868369.png)[V2.0 token](https://support.appsflyer.com/hc/articles/360004562377-Managing-API-tokens) |
| Ad network access | N |
| Agency access | Y |
| Agency transparency | Y |
| App-specific currency | Y |
| App-specific timezone | Y |
| Cost | Cost data is for UA campaigns only; not for retargeting or inactive campaigns (campaigns without any installs). |
| Data freshness | [Continuous](https://support.appsflyer.com/hc/articles/360000310629-Data-freshness-and-time-zone-support#continuous-aka-realtime) |
| Historical data | Aggregated LTV data is available for up to 25 months (2 years + 1 month) |
| Non-organic data | Y |
| Organic data | Y |
| Rate limitations | [Limitation](https://support.appsflyer.com/hc/articles/207034366) |
| Size limitations | - Pull API for **raw data** supports up to 1M rows. Pull API for **aggregated data** can aggregate up to 1M rows of raw data.<br>- API calls return a max. of 200K rows.<br> - If a report has exactly 200K rows, then assume rows are missing.<br> - Make multiple API calls, using from/to parameters that include the time of day. |
| Campaign name changes | Pull API reports don't support campaign name changes |

<Cards>
  <Card title="Descriptions and examples of aggregate reports" href="https://support.appsflyer.com/hc/articles/360005437257">
    View detailed descriptions and examples of the aggregate reports available.
  </Card>
  <Card title="Selecting the right data delivery tool for aggregated data" href="https://support.appsflyer.com/hc/articles/360005437257">
    Compare and choose the best tool for delivering your aggregated data.
  </Card>
</Cards>
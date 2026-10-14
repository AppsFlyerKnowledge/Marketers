---
title: "Pull API aggregate data"
excerpt: "Use this Pull API to get your AppsFlyer aggregate reports in CSV files."
x-zendesk:
  id: 207034346
  url: https://support.appsflyer.com/hc/en-us/articles/207034346-Pull-API-aggregate-data
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Data delivery tools
  section_id: 6550995484561
  position: 8
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-rona-einat, Marketers, Raw Reports]
  labels: [Performance, raw data, Pull API, Reports, API, Parameters, API Policy, Advertisers, facebook rawdata, facebook raw data, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2013-04-24T15:08:25Z'
  edited_at: '2026-03-18T09:04:12Z'
---
[![PullAPIAverage_us-en.png](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)

> 📘 **Looking for Pull API raw data?**
>
> Learn all about it [here](/docs/pull-api-raw-data).

## Pull API aggregate data

* Pull API lets you get aggregate data reports for user acquisition (UA) and retargeting in CSV files.
* [Data freshness rates](/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support) are the same as the equivalent report on the Export Data page and Overview dashboard page. Consider that cost can update with a delay of several hours, depending on the partner providing the cost data.
* Filter by options available: Media source and date range.
* Additional capabilities in Pull API are:
  * Add attribution touch type
  * Select timezone

#### Aggregate performance reports available via Pull API

<table><thead><tr><th>Category</th><th> UA</th><th>Retargeting\*</th></tr></thead><tbody><tr><td>Partners (media source)</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Partners by date</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Daily</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Geo</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Geo by date report</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td colspan="3">\* For retargeting reports, add the <code>&amp;reattr=true</code> to the URI. </td></tr></tbody></table>

<Accordion title="Using Pull API aggregate data">

**To use Pull API aggregate data**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/5dd980a707877c2ab26826170f7f1313bffba1fed8ab3eacb59954770c302932-19754884868369.png) Get the API token. An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the [parameters](/docs/pull-api-aggregate-data#parameters) to input when they make the API call, as described in the section that follow. The parameters determine what the report focuses on, how it's organized, and provide a reporting timeframe.
4. Tell your developer to follow their [Pull API aggregate data instructions](https://dev.appsflyer.com/hc/reference/overview-11) in the developer hub.

</Accordion>

<div id="parameters" />

<Accordion title="Parameters">

| Parameter | Description |
| --- | --- |
| app\_id | Application ID |
| from | <ul><li>The date range consists of a `from`and `to` parameter. The range is the LTV (install) date range.</li><li>Format: `yyyy-mm-dd`,</li><li>Example: 2010-01-01</li></ul> |
| to | End date. As for `from` |
| media\_source | Use to limit (filter) to a specific media source.<ul><li>Example:`media_source=facebook`</li></ul> |
| attribution\_touch\_type | Set this parameter as shown in the example to get [view-through attribution](/docs/pull-api-aggregate-data) (VTA) KPIs.<br /><br />Example: `attribution_touch_type=impression`<br /><br />Some VTA KPIs, like clicks, impressions, and cost APIs, don't have values associated with them and display the value N/A instead. |
| currency | Currency of revenue and cost.<br /><br />Aggregate Pull API reports always use the app-specific currency. |
| reattr | Get retargeting conversions data.<ul><li>[Default] If false, user acquisition data (UA) campaigns returns.</li><li>If true, retargeting conversion returns.</li><li>**Example**:`reattr=true`</li></ul> |
| timezone | [Default] Data returns using UTC.<ul><li>Template URIs are populated with the timezone parameter set to the app-specific time zone.</li><li>[Default] If the parameter is not sent, data returns using UTC.</li><li>If you send`timezone=[Joda-Time]`, data returns using the app-specific time zone.</li></ul>Notes about selecting timezones<ul><li>Joda-Time time zone format takes into account daylight saving time.</li><li>The Joda-Time value must be identical to the value in the app settings page. For example, if the timezone setting is Paris, the timezone value in the Pull API URL should be `timezone=Europe%2fParis`.</li><li>Pulling data in the selected time zone is only available from the date when the time zone setting was made. Any data prior to the date of the change uses UTC as the timezone.</li></ul> |

</Accordion>

<Accordion title="Traits and limitations">

| Trait | Comments |
| --- | --- |
| API token type required | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/5dd980a707877c2ab26826170f7f1313bffba1fed8ab3eacb59954770c302932-19754884868369.png)[V2.0 token](/docs/managing-appsflyer-tokens) |
| Ad network access | N |
| Agency access | Y |
| Agency transparency | Y |
| App-specific currency | Y |
| App-specific timezone | Y |
| Cost | Cost data is for UA campaigns only; not for retargeting or inactive campaigns (campaigns without any installs). |
| Data freshness | [Continuous](/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime) |
| Historical data | Aggregated LTV data is available for up to 25 months (2 years + 1 month) |
| Non-organic data | Y |
| Organic data | Y |
| Rate limitations | [Limitation](/docs/report-generation-quotas-rate-limitations) |
| Size limitations | <ul><li>Pull API for **raw data** supports up to 1M rows. Pull API for **aggregated data** can aggregate up to 1M rows of raw data.</li><li>API calls return a max. of 200K rows.<ul><li>If a report has exactly 200K rows, then assume rows are missing.</li><li>Make multiple API calls, using from/to parameters that include the time of day.</li></ul></li></ul> |
| Campaign name changes | Pull API reports don't support campaign name changes |

</Accordion>

> 📘 **See also**
>
> * [Descriptions and examples of aggregate reports](/docs/aggregated-and-analytics-reporting-overview)
> * [Selecting the right data delivery tool for aggregated data](/docs/aggregated-and-analytics-reporting-overview)
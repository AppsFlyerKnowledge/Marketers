---
title: "Measure exceeded dimensions and cardinality limits"
excerpt: "Learn why some aggregate data dimensions display as exceeded in AppsFlyer and how to prevent reaching cardinality limits."
---
**At a glance:** Why some aggregate data dimensions display as *exceeded*and how to prevent reaching cardinality limits.

## What are exceeded dimensions?

AppsFlyer collects your install and event data and aggregates it. Data is aggregated using unique values populating a given dimension. The number of unique values in a dimension is called cardinality. Most analytics and aggregated reporting tools have cardinality limits per dimension. When the number of unique values in a dimension exceeds the cardinality limit, the remaining data is grouped in an *exceeded* group. And when the number of unique values in the media source dimension exceeds the cardinality limit, the remaining media source data **as well as all dimensions based on the remaining media sources** are grouped in *exceeded* groups.

The examples that follow illustrate cardinality and how it affects your reports.

> 📘 **Example**
>
> **Example A: Campaign ID cardinality limit**
>
> The Campaign ID cardinality limit is 3000. If the number of campaign IDs reported on a given day exceeds 3000, then any remaining campaign IDs are grouped together in the Exceeded\_CampaignID\_Limit.
>
> **Example B: Events cardinality limit**
>
> * Assume that the Events cardinality limit is 3.
> * On a given day, 7 unique events are reported: A, B, C, D, E, F, and G. In other words, Events cardinality is 7.
> * In aggregated reports, events A, B, C are listed separately. Events D, E, F, and G are grouped in the Exceeded\_Events\_Limit.


Exceeded dimensions and cardinality limits affect aggregate data as follows:

* Overview dashboard
* Aggregate data export and Pull API reports
* Master API reports
* Click and impression data in Activity and Custom dashboards
* Protect360 dashboard

Raw data isn't affected by cardinality limits.

If a large part of your data is grouped in *exceeded* groupings, that data isn't broken down. This can lead to imprecise results in analytics reports. If needed, use raw data to build groupings without cardinality limits.

The table that follows lists the cardinality limits per day, per app.



<table><tbody><tr><th>Dimension</th><th>Exceeded group name</th><th>Limit type per...</th><th>Cardinality limit per day </th><th>Cardinality for Protect360 per day</th></tr><tr><td>Ad</td><td>Exceeded_Ad_Limit</td><td>Media source</td><td>1000</td><td>-</td></tr><tr><td>Ad ID</td><td>Exceeded_AdID_Limit</td><td>Media source</td><td>1000</td><td>-</td></tr><tr><td>Ad set</td><td>Exceeded_AdSet_Limit</td><td>Media source</td><td>1000</td><td>-</td></tr><tr><td>Adset ID</td><td>Exceeded_AdSetID_Limit</td><td>Media source</td><td>1000</td><td>-</td></tr><tr><td>Campaign</td><td>Exceeded_Campaign_Limit</td><td>Media source</td><td>3000</td><td><ul><li>Installs/in-app events: 3000</li><li>Impressions/clicks: 100 </li></ul></td></tr><tr><td>Campaign ID</td><td>Exceeded_CampaignID_Limit</td><td>Media source</td><td>3000</td><td><ul><li>Installs/in-app events: 3000</li><li>Impressions/clicks: 100 </li></ul></td></tr><tr><td>Channel</td><td>Exceeded_Channels_Limit</td><td>Media source</td><td>20</td><td>20</td></tr><tr><td>Site ID</td><td>Exceeded_SiteID_Limit</td><td>Media source</td><td>1000**</td><td><ul><li>Installs/in-app events/impressions/clicks: 1000**</li></ul></td></tr><tr><td>Events</td><td>Exceeded_Events_Limit</td><td>App </td><td>300</td><td>Installs/in-app events: 300</td></tr><tr><td>Keywords</td><td>Exceeded_Keywords_Limit</td><td>Media source</td><td>1000</td><td>-</td></tr><tr><td>Media source names*</td><td>Exceeded_MediaSource_Limit</td><td>App</td><td>1000</td><td><ul><li>Installs/in-app events: 1000</li><li>Impressions/clicks: 100 </li></ul></td></tr><tr><td colspan="5"><p>* If <span>the number of unique values in the media source dimension exceeds the cardinality limit, the remaining media source data </span><strong>as well as all dimensions based on the remaining media sources</strong><span> are grouped in </span><em>exceeded</em><span> groups.</span></p><p><span>** See <a href="/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">Exceeded_SiteID_Limit</a> for more details and limits.</span></p></td></tr></tbody></table>



## Cardinality limits per dimension

### Exceeded\_AdSet\_Limit and Exceeded\_Ad\_Limit

* Up to 1000 unique adset names and 1000 unique ad names per media source are available.
  * On a given day, ad set information from the 1001st ad set and above is grouped in the **Exceeded\_AdSet\_Limit** source. The same applies to the **Exceeded\_Ad\_Limit** source.

> 📘 **Tip**
>
> "Divide and Conquer" again. Define a small number of general ad set names (ideally up to 50), and assign all previous ad set names as single ads. You could also use the **af\_sub** parameters on AppsFlyer attribution links. This enables you to:
> 1. Prevent seeing **Exceeded\_AdSet\_Limit** or **Exceeded\_Ad\_Limit.**2. Efficiently optimize according to significant ad sets and ad traffic.
> 3. Perform deep analysis based on the ad set and ad names in the raw data.


### Exceeded\_AdSetID\_Limit and Exceeded\_AdID\_Limit

* Up to 1000 unique ad set IDs and 1000 unique ad IDs per media source are available.
  * On a given day, ad set ID information from the 1001st ad set ID and above is grouped in the **Exceeded\_AdSetID\_Limit** source. The same applies to the **Exceeded\_AdID\_Limit** source.

### Exceeded\_Campaign\_Limit

**[![](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)**

* Up to 3000 unique campaign names per day are available.
  * On a day campaign information from the 3001st campaign and above is grouped in the **Exceeded\_Campaign\_Limit** source.

> 📘 **Tip**
>
> Define a small number of general campaign names (ideally up to 300), and assign all previous campaign names as ad sets. On AppsFlyer attribution links the parameter is **af\_adset**. This enables you to:
> 1. Prevent seeing **Exceeded\_Campaign\_Limit**.2. Efficiently optimize according to significant adset traffic.
> 3. Perform deep analysis based on the campaigns and ad set names in the raw data.


### Exceeded\_CampaignID\_Limit

* Up to 3000 unique campaign IDs per day are available.
  * During a single day, all campaign information from the 3001st campaign ID and above is attributed to the **Exceeded\_CampaignID\_Limit** source.

### Exceeded\_Channels\_Limit

* Up to 20 unique channel names per day per media source are available. For Protect360, the limit is 1000.
  * On a day, all channel information from the 21st channel and above is attributed to the **Exceeded\_Channel\_Limit** source.

### Exceeded\_Events\_Limit

* Up to 300 unique event names per day are available.
  * On a day, all event information from the 301st event and above is attributed to the event name called **Exceeded\_Events\_Limit**.

> 📘 **Tip**
>
> To stop seeing **Exceeded\_Events\_Limit**, consider using:
>
> * [Rich in-app events](/docs/in-app-events-overview). Instead of reporting on hundreds of different events define a small number of general event names (ideally up to 20). Use dynamic event values to differentiate between these events. This lets you optimize according to value parameters, and perform analysis based on the event values, which are available via the [in-app events raw data report.](/docs/raw-data-reporting-overview)
> * [Validation Rules](/docs/implement-validation-rules-to-prevent-fraud) to remove unneeded in-app events from the AppsFlyer platform.

> 📘 **Example**
>
> Your app com.greatapp sends a purchase in-app event for every color of socks it sells, for example, buy\_red\_socks, buy\_blue\_socks, buy\_white\_socks, etc. To avoid this inflation of different events narrow them all down to a single event, buy\_socks, and insert the color as an [event parameter](/docs/in-app-events-overview).


### Exceeded\_Keywords\_Limit

* Up to 1000 unique keywords per day per media source are available.
  * On a day, keyword information from the 1001st keyword and above is grouped in the **Exceeded\_Keywords\_Limit** source.

### Exceeded\_MediaSource\_Limit

* Up to 1000 unique media source names per day are available.
  * On a day,  campaign information from the 1001st media source name and above is grouped in the **Exceeded\_MediasSource\_Limit**source.

### Exceeded\_SiteID\_Limit

Site ID (per clicks, impressions, installs, and in-app events) has 2 thresholds, 1000 and 5000.

* Generally, up to 1000 unique site IDs per day per media source are available.
  * On a day, site ID information from the 1001st site ID and above per media source is grouped into a single site ID titled **Exceeded\_SiteID\_Limit.** Therefore, if you do see the site ID **Exceeded\_SiteID\_Limit**, it means there are too many used site IDs per the media source in question, and trying to optimize the source's traffic according to site IDs becomes less accurate and less effective.
* From August 19, 2024, if there are more than 5000 site IDs per day per media source, only 10 site IDs display. All other site IDs are grouped into a single site ID titled **Exceeded\_SiteID\_Limit**.

> 📘 **Tip**
>
> "Divide and Conquer". Instead of using thousands of site IDs per media source, which distorts your aggregate data, use a second parameter on your attribution links called **af\_sub\_siteid.** Define a small number of general site IDs (ideally up to 50), and assign all previous site IDs as sub-site IDs under these general site IDs. This enables you to:
> 1. Prevent seeing **Exceeded\_SiteID\_Limit**2. Efficiently optimize according to significant site IDs traffic
> 3. Perform deep analysis based on the site IDs and sub-site IDs in the raw data

> 📘 **Note**
>
> In the Retention Report, you do not see an Exceeded\_SiteID\_Limit but not all the Site IDs are shown. Site IDs are shown randomly but it is a UI limitation to show all (when they have exceeded the limit). To work around this issue, retrieve retention data from the master API.


## How to avoid getting exceeded sources?

### The long-term solution

Most advertisers won't encounter **Exceeded** sources as they don't normally define 3000 campaigns manually.

If you do encounter **Exceeded** sources it's probably because one or more media sources is using dynamic values for names of campaigns, site IDs, ad sets, or ads. Dynamic in-app events within the app code may cause the **Exceeded\_Events\_Limit** source data to appear.

> 📘 **Tip**
>
> Use only static values for names of in-app events, campaigns, site IDs, ad sets, and ads to avoid getting **Exceeded** sources.
>
> Also please check specific tips per any **Exceeded** source above.


### The short-term solution

The long-term solution may take you a few days to a few weeks to fully implement.

But what if you want to look at your data right now?

As explained, an **Exceeded** source occurs when AppsFlyer receives the N+1 click (or event) source during a single day. It is possible that the more prominent media sources you use arrive later in the day, and therefore are combined with an **Exceeded** source's data. Here's a simple trick to minimize the effect of any **Exceeded** source you see:

> 📘 **Tip**
>
> Forget today and look only at data from yesterday and beforehand. Every day an aggregation process recalculates the last day's data and in retrospect assigns only the smallest (not most late) sources, to any **Exceeded** source. This ensures that the distortion caused by the overflow of clicks is minimal!
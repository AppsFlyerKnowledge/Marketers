---
title: "Advanced filter and group by options in events and activity dashboards"
excerpt: "Learn how to use advanced filter and group by options in AppsFlyer events and activity dashboards to view precise and relevant data for your apps."
---
By filtering and grouping the information in the dashboard using the advanced options, you can view the most precise and relevant data for your apps.

## Advanced filter by and group by options in dashboards

- **Filter by**: Media Source, Geo
- **Group by**: Media Source/Campaign, Site ID, Geo
- **Drill-down**: ad set and ad level data

## Filter by options

AppsFlyer offers you a number of filtering options to let you refine your search and view the information most relevant to you.

For each filter (Media Source, Geo, and Campaign) you can select several options to be filtered at the same time. An X appears next to each selection.

In the field, you are prompted as to how many filters you have selected.

Use the date selector to refine your search to specific dates. You can select your own custom date range or use one of the preset date range buttons.

Select the Media Source for which you want to view the data.

Use the **Geo** dropdown to select a specific geo region and view app activities for that region.

## Group by options

The grouping options allow you to further categorize the results of your filters. Under the **Group By** filter, click the dropdown to view your grouping options:

- **Media Source / Campaign**
  - Used for comparison of acquisition sources. For example, if the same targeting is used for Google and Meta ads so you can view which source is more successful when a campaign is directed towards the same target audience. In addition, by clicking on the name of the campaign, you can drill-down to ad set and then to ad level to view in-depth campaign data. This is only available to those media sources providing the information.
- **Site ID**
  - Based on AppsFlyer **af\_siteid** parameter which represents the publisher that drove the install. You can see which publisher brings you the highest quality users. You can then easily identify which Site IDs have a low conversion rate. This indicates the quality and legitimacy of the traffic.
- **Geo**
  - Allows you to see the best traffic by country. This has a direct impact on how much you are willing to invest per country.
- **Channel**
  - Allows you to view the data per channel. For example, viewing Meta channels (Meta ads, Instagram, Audience Network or Messenger) and Google channels (Search, UAC, mGDN, etc...).
- **Agency**
  - Allows you to view data per agency. If there is no agency data, the Agency column in the table shows _**Unknown**_.

By default, **Media Source / Campaign** is displayed.

When you select **Site ID**, the data displayed is based on your filter selections for Site ID.

> 📘 Note
>
> Site\_id data is available as of 16 May 2016 and onwards.

You are further presented with a breakdown of the data based on Site ID.

When you select the **Geo** option you are presented with a breakdown of the data by country.

## Advanced filtering

For the advanced filtering options click the advanced filter icon.

The filter options expand:

> 📘 Note
>
> Once you select a Campaign/Channel but no Media Source, a warning notification is displayed indicating that you must select a media source first.

When the results are shown, the Advance Filter icon changes color from blue to green.

## Example user story

Mr. A. Flyer wants to examine the campaigns he is running for his app for a particular date range, in this story - the last 7 days.

At the top level, they can view all campaigns grouped by Media Source.

He then wants to refine his search to view the data for the different countries that his campaigns are active in.

To do so, grouping the information by Geo allows him to view the statistics for all the countries.

From viewing this information he wants to focus on a particular country. Having grouped his campaigns by geo and media source, he can then filter the data by Geo.

Mr. A. Flyer can then filter by Site ID allowing him to hone his search to view how a specific Site ID is performing and the quality of the traffic driven from that site.
---
title: Advanced filter and group by options in events and activity dashboards
metadata:
  keywords:
    - advance filters
    - Site ID
    - Advertisers
    - Agencies
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
  created_at: '2016-08-08T14:04:48Z'
  edited_at: '2022-05-18T07:54:06Z'
  id: 211490886
  locale: vi
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/vi/articles/211490886
---
> **At a glance**: Use advanced filter and group by options in events and activity dashboards.

## Advanced filter by and group by options in dashboards

* **Filter by**: Media Source, Geo
* **Group by**: Media Source/Campaign, Site ID, Geo
* **Drill-down**: ad set and ad level data

By filtering and grouping the information in the dashboard using the advanced options, you can view the most precise and relevant data for your apps.

## Filter by options

AppsFlyer offers you a number of filtering options to let you refine your search and view the information most relevant to you.

For each filter (Media Source, Geo, and Campaign) you can select several options to be filtered at the same time. An X appears next to each selection.

<Image align="center" alt="" src="https://files.readme.io/ec865c2e963879815dd25e4c3f3870c4539d22a470c099c256d7e33ea9a0df59-208034063.png" />

In the field, you are prompted as to how many filters you have selected.

<Image align="center" alt="" src="https://files.readme.io/aabcbc881f0f18ae64a4b29af903dafaa27abd31dcaf17d97a0f8e89de30f416-208032403.png" />

Use the date selector to refine your search to specific dates. You can select your own custom date range or use one of the preset date range buttons.

<Image align="center" alt="" src="https://files.readme.io/a80d29a742e80686701669de77e63392239d4694e8c8646e7aae0fd22e11e5de-206060926.png" />

Select the Media Source for which you want to view the data.

<Image align="center" alt="" src="https://files.readme.io/362d109b0b6f1d54b6393b577b34137df3d3b45017aa6dac488caed898468b85-206119563.png" />

Use the **Geo** dropdown to select a specific geo region and view app activities for that region.

<Image align="center" alt="" src="https://support.appsflyer.com/hc/en-us/article_attachments/203515273/DB4.png" />

## Group by options

The grouping options allow you to further categorize the results of your filters. Under the **Group By** filter, click the dropdown to view your grouping options:

* **Media Source / Campaign**

* Used for comparison of acquisition sources. For example, if the same targeting is used for Google and Facebook so you can view which source is more successful when a campaign is directed towards the same target audience. In addition, by clicking on the name of the campaign, you can drill-down to ad set and then to ad level to view in-depth campaign data. This is only available to those media sources providing the information.

<Image align="center" alt="" src="https://files.readme.io/d9437c102866d0966682477e15c1ba61e95898fc40e96f7f5bea1db36c5eb863-207209326.png" />

* **Site ID**

* Based on AppsFlyer **af\_siteid** parameter which represents the publisher that drove the install. You can see which publisher brings you the highest quality users. You can then easily identify which Site IDs have a low conversion rate. This indicates the quality and legitimacy of the traffic.

* **Geo**

* Allows you to see the best traffic by country. This has a direct impact on how much you are willing to invest per country.

* **Channel**

* Allows you to view the data per channel. For example, viewing Facebook channels (Facebook, Instagram, Audience Network or Messenger) and Google channels (Search, UAC, mGDN, etc...).

* **Agency**  
  * Allows you to view data per agency. If there is no agency data, the Agency column in the table shows ***Unknown***.

By default, **Media Source / Campaign** is displayed.

<Image align="center" alt="" src="https://files.readme.io/07b4a1ef6dbfe48d5011157e0799a117d383da0eaea409417a70b715dd5eb09a-115001055266.png" />

When you select **Site ID**, the data displayed is based on your filter selections for Site ID.

> 📘 **Note**
>
> Site\_id data is available as of 16 May 2016 and onwards.

<Image align="center" alt="" src="https://files.readme.io/7f1dcfa333e63c16a44be5ce04a7ecbe7bf1f656a2edb6bb719cb55ea4dd50b1-206156066.png" />

You are further presented with a breakdown of the data based on Site ID.

<Image align="center" alt="" src="https://files.readme.io/bc331dd1c8a611741a75a5a176a7b1a4b72edf08219dfe2a611d14bea3440231-206122143.png" />

When you select the **Geo** option you are presented with a breakdown of the data by country.

<Image align="center" alt="" src="https://files.readme.io/5eb0847fddd0592b2d130df2b97349da7afd0a5f2e03cc7bfdbf2da6becde67d-206064206.png" />

## Advanced filtering

For the advanced filtering options click ![](https://files.readme.io/278e2ad18a60859c446a7a5a6cbc708c012b2200d01c1886c17a662816d1ff27-206127343.png).

The filter options expand:

<Image align="center" alt="" src="https://files.readme.io/3f10672f949e1fc18347632912ff04977d1733ccd25d0fa8a7d4b57ee9bb53ae-211309586.png" />

> 📘 **Note**
>
> Once you select a Campaign/Channel but no Media Source, a warning notification is displayed indicating that you must select a media source first.

<Image align="center" alt="" src="https://files.readme.io/d082084e0be1ec0e47525d55b07518249a5ff6d3ded9bf13dbd7ff7f56d6cc5c-206066866.png" />

When the results are shown, the Advance Filter icon changes color from blue to green ![](https://files.readme.io/5d9e7c2aa155bd2ffeed093f13afab52fd7ce3c4de1a5387ec7be7b692066cb1-206128223.png)

## Example user story

Mr. A. Flyer wants to examine the campaigns he is running for his app for a particular date range, in this story - the last 7 days.

At the top level, they can view all campaigns grouped by Media Source.

<Image align="center" alt="" src="https://files.readme.io/e46dec817d252776dcc6ab29a72ce4cdfdfeaed48e2f7c2783908a932494418e-206163486.png" />

He then wants to refine his search to view the data for the different countries that his campaigns are active in.

To do so, grouping the information by Geo allows him to view the statistics for all the countries.

From viewing this information he wants to focus on a particular country. Having grouped his campaigns by geo and media source, he can then filter the data by Geo.

<Image align="center" alt="" src="https://files.readme.io/36af4e06c37648c7777df302e26b9d350f572132abbd367394cda39c944bf9ce-206114886.png" />

Mr. A. Flyer can then filter by Site ID allowing him to hone his search to view how a specific Site ID is performing and the quality of the traffic driven from that site.

<Image align="center" alt="" src="https://files.readme.io/6b1f87913bd8e873d28c6ce681a5de9d462a44638c7a6adea5b5988d4ec2908e-211309606.png" />
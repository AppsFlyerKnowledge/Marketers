---
title: Creative Optimization guide
excerpt: >-
  Creative Optimization enables you to pull all creative asset data from all
  your campaigns into a single platform, so you can analyze their performance,
  discover which creatives work best, and make better data-driven decisions.
  Data is LTV, meaning the metrics are for conversions that occurred from
  creatives during the selected date range.
metadata:
  keywords:
    - Premium
    - Marketers
    - Design team
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2023-09-14T13:32:13Z'
  edited_at: '2026-09-23T08:06:40Z'
  id: 18564718580625
  locale: en-us
  section: Creative Optimization
  section_id: 4419063475217
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/18564718580625-Creative-Optimization-guide
---
[![Main image -Default view.jpg](https://files.readme.io/9ef8901b620d54cad031ec142f5dd408406e0a470bae8a0719826777561cd1d1-21362497825169.jpg)](https://files.readme.io/9ef8901b620d54cad031ec142f5dd408406e0a470bae8a0719826777561cd1d1-21362497825169.jpg)

## About Creative Optimization

**Creative Optimization** is your one-stop shop for measuring the performance of creatives used in all of your campaigns. It enables you to effortlessly pull all your creative assets from all media channels into one platform, or your BI system, and analyze their performance by selected dimensions, across multiple campaigns, channels, and much more. Creative Optimization enables you to slice and dice by different metrics and KPIs to gain critical insights before planning, selecting, and producing your next batch of creatives.

The Creative Optimization dashboards let you measure the performance of videos, images, HTML, and text, and see how well they’re doing over time and across channels. Each creative is analyzed, aggregated, and matched using powerful AI algorithms. This means that the same creatives used for different campaigns and media sources are identified and displayed as one in the dashboards regardless of their naming convention, ad ID, or any other metadata.

Use the [Creative Optimization Overview dashboard](/docs/creative-optimization-overview-dashboard) to see your data laid out visually in a variety of information-packed graphs and a detailed table, which gives you all the information needed to optimize and select the best creatives for your campaigns.

With the AI-powered [Creative Optimization Discovery dashboard](/docs/creative-optimization-discovery-ai-dashboard), take the guesswork out of producing winning creatives. Gain a comprehensive view of all your creatives or dive deep into the performance of individual scenes and elements for maximum data-driven insights.

[Creative Optimization ETL](/docs/creative-optimization-etl-reporting) equips your data analysts with all the information needed for creative performance analysis by streaming reports automatically to cloud storage for efficient, programmatic loading into your BI systems.

With Creative Optimization, you can:

* Quickly learn which creatives, scenes, and elements work and which don't
* Optimize your creatives based on data
* Increase creative performance and ROI
* Produce the most successful creatives
* Identify declining effectiveness of creatives across time/channels/campaigns and make informed decisions for optimization
* And more

## Creative assets

This section provides information about the creative assets we measure.

<div id="supported-asset-types" />

<Accordion title="Supported asset types">

Asset types supported by the Creative Optimization dashboard include:

* Videos
* Images
* Carousel ads (Meta only)
* HTML (including Playable)
* Text

> 📘 **Notes**
>
> * Assets that can be previewed in the dashboard include images, videos, and text.
> * The “Creative similarity” feature is not yet available for
>   carousel ads.

</Accordion>

<div id="matching-creatives" />

<Accordion title="Matching creatives">

Creative Optimization has the unique ability to identify which assets are the same, across multiple channels and campaigns, regardless of naming conventions or IDs. This is done by AI and computer vision algorithms that match properties such as visual context, sound, and pixels. Additionally:

* The matched creatives must have the same aspect ratio, such as portrait, landscape, or square.
* Videos with different durations are considered different creatives.

</Accordion>

<div id="measuring-creatives-with-multiple-assets" />

<Accordion title="Measuring creatives with multiple assets">

**How does Creative Optimization measure an ad creative with multiple assets?**

Meta Advantage+ (dynamic creatives), and Google Universal App Campaigns (UAC) can include ad creatives with multiple assets. However, AppsFlyer doesn't break down the data on the asset level. Meta ads provides data up to the **ad level** and Google provides data only up to the **ad group level**. For these types of ad creatives, AppsFlyer uses data modeling to divide performance data across the assets.

> 📘 **Example**
>
> Suppose there is an ad creative on Facebook with multiple assets. Facebook attributes it with 100 installs total, broken down to assets as follows: **asset A** has 60 installs and **asset B** has 40 installs, as measured by Facebook. In AppsFlyer, let’s say the ad is attributed with 50 installs (due to inherent attribution differences between AppsFlyer and [SRNs](/docs/self-reporting-networks-srns)). To enable asset-level analysis, AppsFlyer distributes the performance data (impressions, clicks, installs, and cost) based on the asset metrics ratio from the total as illustrated below.
>
> So, **for asset A there are:**
> 60 installs divided by 60+40 (total installs attributed by Facebook) = 0.6
> Then we multiply 0.6 by 50 (number of AppsFlyer attributed installs) = 30 installs
>
> **For asset B there are:**
> 40 installs divided by 60+40 (total installs attributed by Facebook) = 0.4
> Then we multiply 0.4 by 50 (number of AppsFlyer attributed installs) = 20 installs.
>
> So the ad creative is attributed with a total of 50 installs by AppsFlyer but the volume of installs per asset is kept which means that **asset A** generated more installs than **asset B**, in our example.
> Down funnel metrics, such as Revenue and ROAS, are calculated based on this ratio as well.
>
> ![Creative_data_example_en-us.png](https://files.readme.io/ca556904829b809238b8b994fd6d762d6cb58ae993c41dd19a7de978f774e8b9-small-18564727253649.png)

</Accordion>

## Using the dashboard

This section provides a comprehensive overview of the main dashboard: How to use filters, the various metrics and dimensions available to get the creative data you're looking for, and how to save and share dashboard views.

[![Filter bar and metrics -Default view.jpg](https://files.readme.io/b68e65ff2cdd2ad2fe0805eb1c2792904af69504d104b6f6ae8a524124272a48-21363121543185.jpg)](https://files.readme.io/b68e65ff2cdd2ad2fe0805eb1c2792904af69504d104b6f6ae8a524124272a48-21363121543185.jpg)

<div id="filter-bar" />

<Accordion title="Filter bar">

The first step in setting up your dashboards is selecting your filtering options. All filters are applied to both the Creative Optimization Overview and Discovery dashboards.

[![filter_bar.jpg](https://files.readme.io/99da48c37938e573af66cf1f46ce3273c3ca010e68070cb59b5e12cbad1981e3-18564730224913.jpg)](https://files.readme.io/99da48c37938e573af66cf1f46ce3273c3ca010e68070cb59b5e12cbad1981e3-18564730224913.jpg)

**To select dashboard filters**:

1. Select your:
   * **App**
   * **Date range:** A creative is displayed in the dashboard when there is conversion data for the creative during the selected date range. All data is LTV, meaning the metrics are for conversions that occurred from creatives during the selected date range.
   * [View type](#view-type)
2. Click the **+** icon to add any of the following filtering options including:
   * **Dimensions and metrics**
   * **Numeric filters**, which are available for all metrics with the following options:
     * Greater than **-** displays creatives with values higher than or equal to the chosen metric
     * Less than **-** displays creatives with values below the chosen metric

In addition to [standard metrics and dimensions](/docs/creative-optimization-guide#standard-metrics-and-dimensions), the Creative Optimization dashboard offers various [unique metrics and dimensions.](#unique-metrics-and-dimensions)

</Accordion>

<div id="view-type" />

<Accordion title="View type">

Creative data in the dashboards is presented in 3 separate view types: Unified, User Acquisition (UA), and Retargeting:

* **Unified** - Displays all creative data from both UA and retargeting ads/adsets.
* **User Acquisition** - Displays creative data associated with UA ads/adsets only.
* **Retargeting** - Displays creative data associated with retargeting ads/adsets only. Cost data is available here as well.

[![View_types.jpg](https://files.readme.io/e73cc643581e94d6fbc6455e16615eb2e1d8b387cda626d39b17bbe714122611-18564727261585.jpg)](https://files.readme.io/e73cc643581e94d6fbc6455e16615eb2e1d8b387cda626d39b17bbe714122611-18564727261585.jpg)

</Accordion>

<div id="creative-optimization-roi360" />

<Accordion title="Creative Optimization + ROI360">

With an AppsFlyer ROI360 subscription, cost data displayed in the Creative Optimization dashboards comes from ROI360, which consolidates and processes cost data from your ad network partners, and adds additional cost-based metrics. Without this subscription, cost data comes from your integrated media partners’ own reporting. We recommend an ROI360 subscription to access the most comprehensive and current cost data. The table below explains the Creative Optimization differences with and without ROI360.

| With ROI360 | Without ROI360 |
| --- | --- |
| <ul><li>[Has data as reported via any ROI360 method](/docs/roi360-guide-cost-and-revenue-data#cost-tools).</li><li>[Has all the ROI360 cost-reporting capabilities](/docs/roi360-guide-cost-and-revenue-data#cost-tools).</li><li>Creative ETL includes cost data (requires an ROI360 Advanced subscription).</li></ul> | <ul><li>Cost data, as reported directly by your integrated partners, is limited to Creative Optimization dashboards, not Creative ETL.</li></ul> |

Learn more about [ROI360](/docs/roi360-guide-cost-and-revenue-data).

</Accordion>

<div id="standard-metrics-and-dimensions" />

<Accordion title="Standard metrics and dimensions">

Standard metrics/dimensions available in the dashboards include:

| Metric/dimension | Description |
| --- | --- |
| Impressions | Number of creative views |
| Clicks | Number of clicks on ads with the creative |
| Conversions | <ul><li>Installs - Number of unique users who install the app</li><li>Re-engagements - Number of unique users who open the app after interacting with a retargeting campaign</li><li>Re-attributions - Number of unique users who reinstall the app after interacting with a retargeting campaign</li></ul> |
| Cost | Creative cost |
| CTR (Click through rate) | Rate (%) of users who have clicked an ad in relation to the number of total views. Formula: Clicks/impressions *100 |
| CVR (Conversion rate) | Rate (%) of users completing the journey from click to attribution (installs, re-engagements, and re-attributions). Formula: Conversions / Clicks *100 |
| IPM (Installs per mille) | Installs per mille. Number of installs per every 1000 user impressions (ad views) |
| eCPI (Effective cost per install) | eCPI excludes organic installs and calculates the cost per [non-organic attributions](/docs/about-organic-and-non-organic-installs) (installs, re-engagements, and re-attributions). Formula: Total available cost / all non-organic attributions. |
| CPM (Cost per mille) | Cost of 1000 ad impressions. Formula: Total creative spend / number of impressions) * 1,000 |
| Platform | Refers to the OS (i.e. Android) |
| Channel | Segmentation of traffic within media sources  <br />(i.e. YouTube for Google, Instagram for Meta ads etc.) |
| Geo | Country/location |
| IDs | <ul><li>Creative</li><li>Ad</li><li>Adset</li><li>Campaign</li></ul> |
| Agency | Displays creative data from selected agencies |
| Revenue (D0, D1, D3, D7, D14, D30, D60, D90) | Cohorted revenue reported to AppsFlyer |
| ROAS (D0, D1, D3, D7, D14, D30, D60, D90) | Cohorted Return On Ad Spend (%). Calculates the revenue generated per unit of ad spend. Formula: Revenue / Cost * 100 |
| Unique users (D0, D1, D3, D7, D14, D30, D60, D90) | Cohorted unique users that engaged with your app up to, and including, the specified day from the install |
| Retention (D0, D1, D3, D7, D14, D30, D60, D90) | Cohorted rate (%) of users who continue to use your service or product over a predetermined period<br /><br />**Note:** The data is aligned with the AppsFlyer Cohort dashboard. |

</Accordion>

<div id="unique-metrics-and-dimensions" />

<Accordion title="Unique metrics and dimensions">

Unique metrics/dimensions available in the dashboards include:

| Metric/dimension | Description |
| --- | --- |
| Appearances | Displays the number of campaigns/adsets/ads a specific creative is displayed in, across the different channels |
| [Partner metrics](/docs/creative-optimization-guide#partner-dimensions-and-metrics) | Performance data that comes directly from integrated partners (not from AppsFlyer attribution data) |
| Creative similarity | Groups creatives that are almost identical (but with slight differences) and lets you compare their performance so you can determine the most successful version. For example, similar images with different orientations (portrait vs. landscape) would be grouped together, as would similar videos in different languages. This dimension is only applicable to images and videos. |
| Creative age | Displays the number of days a creative has run as part of campaigns. The age is calculated from the first impression, click, or install received by AppsFlyer (the creative "First seen" timestamp) and can vary by the dimensions selected. For example, if a creative was uploaded to a campaign one day, and then also uploaded to another campaign on a different day, and both campaigns and creative age dimensions are added to the filter, the age will be that of the first upload.<br /><br />**Note:** For creatives in campaigns that began running before being ingested into the Creative dashboard, AppsFlyer displays their data which includes up to 90 days before the ingestion. For example, if a creative was running for 90+ days before ingestion, the “creative age” that will display is 90 at first but then will continue to grow cumulatively each day. |
| Creative first seen | Displays creatives by when performance data (usually an impression) was first received. The "Creative age" calculation is triggered from this time stamp. |
| Duration | Length of time in seconds of a creative asset (applicable to videos) |
| Resolution | Size of a creative asset in pixels (applicable to images and videos)<br /><br />**Note:** We display the actual resolution that was served to users by your integrated media partners. This may be a different resolution than what was originally uploaded to them. |
| Orientation | Orientation of a creative asset such as portrait, square, or landscape |
| Month | Breakdown of performance by month |
| Week | Breakdown of performance by week |
| End cards | This refers to an ad that may display at the end of video ads, and which usually contains basic information about the promoted app. The ability to group creatives by end cards gives additional insights for the optimization of creatives, such as comparing the same end card with different videos to identify the best combination. You can view creatives by the following end card data:<ul><li>End card name</li><li>End card ID</li><li>End card duration</li><li>End card resolution</li><li>End card orientation</li><li>End card type</li></ul>**Notes:**<ul><li>End card data is available for the following partners: AppLovin, IronSource, Moloco, UnityAds, Snapchat, and YouAppi.<ul><li>Currently, only ironSource, Unity Ads, and Snapchat provide the unique end card names. For all other partners, the end card names will appear identical to the creative names in the dashboards.</li></ul></li></ul> |

</Accordion>

<div id="custom-metrics" />

<Accordion title="Custom metrics">

Create custom metrics to measure the performance of your creatives exactly how you like.

**To create a custom metric:**

1. Click the dropdown menu on the upper right of the dashboard, and select **Custom metrics.**  
   **![Custom_metric_select.jpg](https://files.readme.io/99ca0ee30d09e42ef2798188e8d95fc4cf56ee31ad055209efadc47c9df8a859-18564742772625.jpg)**
2. **Fill out the form:**
   * **Name** - Enter a unique metric name
   * **Type** - Select either a Numeric, Percentage, or Currency type
   * **Description** - Enter a description (optional)
   * **Metric formula** - Create a formula by clicking **+ Add formula**.   
     * *Metrics* include impressions, clicks, installs, CTR, CVR, CPM, IPM, Cost, eCPI, Reattributions, Reengagements, Revenue, ROAS, Retention, Unique users, Appearances, partner metrics
     * Combine with various *Operators, Numbers,* and/or *In-app events*
     * Specific in-app events are selected from the dropdown menu. For each in-app event, you can add any metrics per the event separately to get highly specific insights, for example, af\_purchase revenue + af\_login count.  
       ![](https://files.readme.io/2b8bdaa8c1fb47c7e78b59e7e24f37aa3248800c7a3ed5cc821c2e11622a93fe-30129836915729.png)
3. Click **Save**.  
   Your new custom metric is created and will display in the filter bar and table settings with "Custom" next to it.

**Notes:**

* You can create up to 30 custom metrics per account.
* You can hover over the "Custom" tag in the table settings to see the description.

Custom metrics can also be edited or deleted.

**To edit:**

1. Click the **Edit existing custom metric** dropdown (on the **Custom metrics** form) and select the one you wish to edit.  
   ![](https://files.readme.io/b792e08152482bed11ea8ce5ea5795c3df961c257d07397b5b4d787f40a8ea2e-30129836916369.png)
2. Make any changes you wish, then click **Save**.  
   **Note:** You can also click **Save as**to save it as a new custom metric.

**To delete:**

* After selecting the custom metric you wish to delete from the dropdown, click the delete icon.  
  ![](https://files.readme.io/8370c5bfec23ef2ac15e266e98be357e496aef51fa14ca5b4c853b0b38910a10-30129810517393.png)

</Accordion>

<div id="partner-dimensions-and-metrics" />

<Accordion title="Partner dimensions and metrics">

Partner metrics is performance data that comes directly from integrated media partners (and not from AppsFlyer attribution data). Metrics vary by partner and can include impressions, clicks, conversions, cost, and video play % metrics. The metrics can be selected in the filters, viewed throughout the dashboard and reports, and added to the table.

The following table lists all Creative optimization partners, with the data granularity available for each:

* Dimensions
* Metrics (as reported by the ad networks)
* Supported features and their characteristics

Download file: [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vTQLUxhNMmBPTlm1_KsfLTupNL6tgZeqAt5OFwzLJUmhSXZ7K18aX6enuV4ST1mUVarUV-KPrUnMYS6/pub?output=csv), [XLS](https://docs.google.com/spreadsheets/d/e/2PACX-1vTQLUxhNMmBPTlm1_KsfLTupNL6tgZeqAt5OFwzLJUmhSXZ7K18aX6enuV4ST1mUVarUV-KPrUnMYS6/pub?output=xlsx)

#### **To set up partner metrics:**

Add a new [partner integration](/docs/creative-optimization-partner-integrations) and metrics for supported partners will automatically be pulled into Creative Optimization (**Unity Ads** **is an exception and has special instructions below**). Once set up, these metrics are indicated with "Partner" alongside the metric.

![partner metrics image.jpg](https://files.readme.io/074948fd8e4707c1353b6f8ce387e76e04801eeef397e94a604619bc8a0ad420-18564730240145.jpg)

**Special instructions and considerations:**

<div id="applovin-metrics" />

<Accordion title="AppLovin metrics">

**Note:**

* Due to a restriction on the AppLovin API, only up to 45 days of historical data is available. AppsFlyer is typically able to display up to 90 days of historical data, however, because of the AppLovin restriction, only 45 days of AppLovin data is available.
* AppsFlyer Creative data is aligned with the AppLovin probabilistic report (not the billable report).

</Accordion>

<div id="google-ads-metrics" />

<Accordion title="Google Ads metrics">

**Note:**

* There will be differences in the number of installs reported by Google Ads and AppsFlyer due to different attribution logic.
* There will be differences between Google and AppsFlyer for all metrics. This is due to the fact that Google partner metrics are based on the Google asset view report while AppsFlyer data is aligned to the Google ad group view. These reports are not aligned with each other in terms of performance, for example, the total number of asset impressions under a specific ad group won't be equal to the total impressions that the ad group reports.
* There are differences between the Creative product and Google AdWords platform; when comparing the asset view between the Google platform and AppsFlyer there may be slight differences due to: 1. Time zones (Creative is UTC+0). 2. Data freshness rate (the difference between event occurrence and data availability in the platform).

</Accordion>

<div id="meta-ads" />

<Accordion title="Meta Ads metrics">

**Note:**

* There will be differences in the number of installs reported by Meta Ads and AppsFlyer due to different attribution logic.
* Meta doesn't report installs on the asset level for iOS, so it's not available in Creative.

</Accordion>

<div id="unity-ads-metrics" />

<Accordion title="Unity Ads metrics">

**To get partner metrics from Unity Ads:**

1. From the Creative Optimization dashboard, click the  **⋮** icon on the upper right to get to **Creative integrations**.  
   ![icon for creative integrations.jpg](https://files.readme.io/5af3cc395743cf305a9d19dca41dc53c7cbf82e18434d2eb335c9e58a4245456-21366803702033.jpg)
2. Click **+ New integration**.
3. Select **Unity Ads** in the **Partner** dropdown list.  
   ![New integration - Unity Ads.jpg](https://files.readme.io/8a03c4b50287768cd95217af142ec551c8526b2cf5f7f7af06c04704a868093d-18564745005073.jpg)
4. Enter the Unity **Key ID**, **Secret Key**, and **Organization Core ID** for the integration (see [Unity integration](/docs/creative-optimization-partner-integrations#unity-ads) instructions for how to get these).
5. In the **Partner metrics** section, enter the Unity **API Key** and the **Organization ID**. You can retrieve these credentials by following the below instructions. **Note:** If you have a ROI360 Cost integration with Unity Ads, you can take the credentials from there as well.
   * **To get the API key:**
     1. Log in to your Unity Gaming Services platform.
     2. Click **Products** in the side menu, then click **Grow**.  
        ![Unity Org ID step 1.jpg](https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg)
     3. Click **Unity Ads User Acquisition**.  
        ![Unity Org ID step 2.jpg](https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg)
     4. Click **API management**.  
        ![Unity-from API mngmt, get API key w arrow.jpg](https://files.readme.io/c617593d5935fbe8072d9fac0146fb3257c395c8dcf173130b97cc2a4a043285-20348783332881.jpg)
     5. Copy the API key.
   * **To get the Organization ID:**
     1. Within Unity Ads, click **Products** on the side menu, then click **Grow**.  
        ![Unity Org ID step 1.jpg](https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg)
     2. Click **Unity Ads User Acquisition**.
     3. ![Unity Org ID step 2.jpg](https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg)
     4. Click **Settings**.  
        ![Get Organization ID instructions 2 arrows.jpg](https://files.readme.io/7514d25a8c9a7a9f64e7e5b6f9008c649cb949eff7d25c49a1693f806518e07d-20348948474897.jpg)
     5. Copy the **Organization ID**.

> 📘 **Note**
>
> We recommend entering the partner metrics credentials when setting up a new partner integration. However, it's not mandatory. You can save the integration and add the credentials at a later time. But please note that we pull 90 days of partner data from the time the partner integration is created, so not entering the partner metric credentials may result in missing data.

</Accordion>

</Accordion>

<div id="save-and-share-views" />

<Accordion title="Save and share views">

After selecting your filters, you can save your selections for quick and easy access to the info you want to see in the dashboards so there's no need to reselect the filters each time you log in. The saved view applies to both the Creative Optimization Overview and Discovery dashboards. You can save a dashboard view as private or shared. Shared views are visible to other account users. Additionally, you can share dashboard views with others via the share URL.

**Note**: An orange indicator dot appears next to the current view if you've made changes to the dashboard settings without saving the view.

#### **Save private dashboard view**

**To save a private dashboard view (only visible to you):**

1. At the top of the dashboard that's currently showing, click the dropdown icon, make sure the menu has the private icon selected, and then click **+ Save as new private dashboard.**  
   ![](https://files.readme.io/c1ed2ac6917fa105641f054623ad87a562f4b80042379301c8736bffaa57a22e-25381406386065.png)
2. Enter a dashboard name and click **Save**.
3. Use the menu icons to edit and delete dashboard views, change the share settings from private to shared, or star a view, marking it as the default view to display upon login.

#### **Save shared dashboard view**

**To save a shared dashboard view (visible to other account users):**

1. At the top of the dashboard that's currently showing, click the dropdown icon, make sure the menu has the shared icon selected, and then click **+ Save as new shared dashboard.**  
   **![](https://files.readme.io/d4a7f206d49ddea230883ee6e119caab119164fa3bee9d0c3f02d487c9cf8a36-25381406390033.png)**
2. Enter a dashboard name and click **Save**.  
   The view is saved and appears in the list of dashboard views for all other account users.
3. Use the menu icons to edit and delete dashboard views, change the share settings from shared to private, or star a view, marking it as the default view to display upon login.

#### **Share view URL**

**To share a view URL with another account user:**

* Click the icon on the upper right of the dashboard to copy the page URL, then share it.  
  ![Copy_page_URL_with_cursor.jpg](https://files.readme.io/2d1cc2f9585850c1d9c723f959be96e953fe6cc90b6b2a31ac8c16bf4e7b4b8f-18564702245777.jpg)  
  **Note**: View URLs can be shared even for private dashboards. When the private dashboard URL is opened, the report name that displays is "Unsaved Report".

</Accordion>

## Custom tags

Group and analyze your creatives based on tags that you upload or by the unique identifiers that are stored in file names. This section describes the different ways of creating custom tags, which appear as dimensions you can select in the filters and view throughout the dashboards.

<div id="custom-dimensions" />

<Accordion title="Custom tags via CSV">

You can add custom dimensions to the dashboard. These custom dimensions and the associated tagged creatives are added via CSV file and aligned with the current creatives used in the various campaigns. Use this feature to view, organize, sort, and filter creatives by any custom dimensions and tags you wish.

<div id="create-and-manage-custom-dimensions" />

<Accordion title="Create and manage custom dimensions">

The process of creating and managing custom dimensions includes the following 3 actions:

1. Downloading a CSV file from the Creative Optimization dashboard which contains the current creatives.
2. Creating new dimensions or changing current dimensions and tags. Each column heading in the CSV file is the name of the custom dimension (For example: “Color”). All creatives in this column will be tagged with the custom dimension and will be displayed under this tag in the dashboard. You can add or change any of the custom dimensions or tags via the CSV file. **Note**: The new CSV doesn't need to include previously created custom tags and dimensions; only ones that you want to edit or add.
3. Uploading the updated CSV file into the Creative Optimization dashboard. The data will be available after around 30 minutes.

The procedures for downloading and uploading the CSV file are described below:

**To download a CSV file with current creatives from the dashboard:**

1. Click the![3_dots_icon.png](https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png) menu on the top-right corner of the dashboard.  
   ![Main menu highlighted.jpg](https://files.readme.io/be14a3ab1a9aba6dc20816e53ad692b1697d15a185053cf523d2ae8451842350-21367268248465.jpg)
2. Click **Download custom tags file**.
3. Select which creatives you want to include in the file (all creatives or only the creatives that are currently displayed on the dashboard - excluding creatives that are filtered out).
4. Click **Download**.

Make the desired additions or changes to the file, then save it, and upload it back into the dashboard.

**To upload the CSV file to the Creative Optimization dashboard:**

1. Click the![3_dots_icon.png](https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png) menu on the top-right corner of the dashboard.
2. Click **Upload custom tags file**.
3. Select a file to upload.  
   Make sure you are aware of all of the different [traits and limitations](/docs/creative-optimization-guide#traits-and-limitations) when uploading a CSV file.
4. Click **Upload to dashboard**.

The data will be available in about 30 minutes.

</Accordion>

<div id="example-csv" />

<Accordion title="Example CSV">

Here's an example of a custom dimensions CSV file (that you download from the dashboard). Each column heading (in row 1) is the name of a custom dimension (for example: “Theme” or "Variant"). You can add additional dimensions or change the existing ones. You can also add or change the tags (for example: “3 Moves" or "DarkPalette").

[![Screen_Shot_2022-08-08_at_16.25.23.png](https://files.readme.io/33137d3c8eab51069a3863a2af193d2192cd28546442abcaf8b74073e737c63e-18564702296977.png)](https://files.readme.io/33137d3c8eab51069a3863a2af193d2192cd28546442abcaf8b74073e737c63e-18564702296977.png)

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Custom dimension traits and limitations">

* Custom dimensions appear with a “Custom” tag in the filters and table.

![Custom_tag.png](https://files.readme.io/f8003396943a406dec2b825f4a4725aeb2f0ea3b23f3c67643cc0c096321b401-18564730363025.png)

* You can add up to 15 custom dimensions to the Creative Optimization dashboard.
* The upload file size is limited to 1 MB.
* Existing dimensions and tag names can be changed by updating the CSV file and re-uploading it. **Note**: You can update or add only one dimension per file upload.
* Custom dimensions defined in the CSV file apply on the account level, meaning to all apps and users.
* Each creative can have one tag per dimension. For example, if "Color" is the custom dimension, the tag can only be one color, such as red.
* When creating or editing the custom dimensions, make sure not to change the creative\_id to avoid overwrites and discrepancies.

</Accordion>

</Accordion>

<div id="name-convention-tags" />

<Accordion title="Name convention tags">

You can create custom tags based on your creative asset naming conventions. These custom tags will appear as dimensions you can select in the filters and view throughout the dashboard.

This is useful for marketing and creative teams whose creatives are named intentionally, with unique identifiers built into the names. These creatives can automatically be tagged by the built-in identifiers, and grouped for analysis and optimization purposes.

<div id="create-and-manage-name-convention-tags" />

<Accordion title="Create and edit name convention tags">

**To create name convention tags:**

1. Click the  **⋮**  icon on the upper right of the dashboard, and select **Name convention tags**.  
   The **Manage name convention tags** window appears.  
   ![Name convention tags main window.jpg](https://files.readme.io/e59721daabccd23ae7735d3e8cca68194983a3c28453daf00bf0ab39ad76fa98-18564727397393.jpg)
2. Under **Create new name convention type**, enter the details:
   * **Name** - Give the new name convention type a unique name.
   * **Separator** - The character that separates each section. For example, in a creative called “enUS\_bluegalaxy\_launch.mp4”, each section is separated by “\_”. “\_” is the separator.
   * **Number of sections** - For example, in a creative called “enUS\_bluegalaxy\_launch.mp4”, there are 3 sections separated by a “\_”.  
     **Note:** The file type is not included in the tags.
   * **App** (optional) - You can include all apps, or limit tags to creatives associated with certain apps only.
   * **Media source** (optional) - You can include all media sources, or limit tags to creatives that ran on certain media sources only.
3. Add the custom tag details:
   * **Section number** - Select the section number of the tag you'd like to create.
   * **Custom tag name** - Create a name by clicking **+ Create new custom tag**, or select an existing name.
   * **Format** - Select how the tags should appear throughout the table/dashboard: in uppercase, lowercase, or the original (how it originally appears in the creative name).  
     You can add additional custom tags by clicking **+ Add custom tag**.
4. Before you save, you can preview how your custom tags will be applied to your creatives by clicking **Download preview file** (optional). This will download a file with all creatives that match the name convention type you're creating, with all of them tagged according to the new tags.
5. Click **Save**.  
   The tags will be applied and available in the dashboard within a few hours.

**To edit name convention tags:**

1. Click the  **⋮**  icon on the upper right of the dashboard, and select **Name convention tags**.
2. Click the **Edit name convention type** dropdown to make your selection.
3. Make the required changes, and click **Save**.

**To delete a name convention type:**

1. Click the **Edit name convention type** dropdown and select the one you want to delete.
2. Click the  ![Delete icon.jpg](https://files.readme.io/a4bb54fefcdd474edbb897dc334b8219c36273fd5e4f45a03e1b39091856e137-18564742905873.jpg)  icon which appears when you hover to the right of your selection.  
   **Note:** The associated custom tags will no longer apply to your creatives. It may take a few hours for the change to take effect.

<div id="name-tag-traits-and-limitations" />

<Accordion title="Name tag traits and limitations">

* You can create up to 10 different name convention types (and the associated custom tags).
* If custom tags that have been uploaded via CSV file conflict with the name convention tags you've created, the uploaded CSV tags will take precedence and only those tags will apply.

</Accordion>

</Accordion>

</Accordion>

## Additional information

<div id="h_01HA282W8WHHNDG75XZNSV2QQF" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Data source | The source of performance data in the Creative Optimization dashboards (aside from Partner metrics) comes from the AppsFlyer attribution model. **Note**: There are inherent differences in the attribution models used by the various advertising platforms and players in the mobile advertising ecosystem, which can explain reporting discrepancies between them. |
| Multiple assets | For creatives that include multiple assets, only one asset is displayed (usually the video when applicable). |
| Data freshness | The Creative Optimization Overview and Discovery dashboards update once daily at 10:00 UTC (refreshing creative data from the last 90 days).<br /><br />Depending on your time zone, the daily update occurs at:<ul><li>New York: 5:00 AM EST / 6:00 AM EDT</li><li>Berlin: 11:00 AM CET / 12:00 PM CEST</li><li>Shanghai: 6:00 PM CST</li></ul>For other locations, convert 10:00 UTC to your local time zone.<br /><br />**Note:** Data in Creative Optimization updates once a day, whereas the main AppsFlyer Overview dashboard updates in real time, which may cause temporary discrepancies. |
| Currency | All monetary metrics in Creative Optimization are in USD. |

</Accordion>

<div data-zendesk-anchors="overview=about-creative-optimization 01H7SZ8R9ZWZ81WHV26P00YAYP=about-creative-optimization 01H7SZ8RA14Q5D32EY5J0WMVYA=creative-assets 01H7SZ8RA1C863VRG1P10CJHTR=supported-asset-types h_01HMXES26N1X3KAFRKKCC9NFXW=notes 01H7SZ8RA1D9JVG1145CAXEZFX=matching-creatives 01H7SZ8RA191221K683N1Z9R69=measuring-creatives-with-multiple-assets 01H7SZ8RA1KRPFF9AW5P4QKQXH=example creative-dashboard=using-the-dashboard 01H7SZ8RA1JX2TCQHB5XW21EK8=using-the-dashboard 01H7SZ8RA1ATSBZPMFJC0T7HRG=filter-bar 01H7SZ8RA1RT91HKKD0R93T2TA=view-type h_01HJDKZWTQVTPSJXP2HWSMD8W6=creative-optimization-roi360 h_01H9JS005MCGMPJM7NYTW2HCAF=standard-metrics-and-dimensions 01H7SZ8RA222QS1AXDKT49DEK3=unique-metrics-and-dimensions 01H7SZ8RA23SCGJ435B4V32CP1=custom-metrics 01H7SZ8RA2R9N2NC6JXNZZ7C5Z=partner-dimensions-and-metrics partner-table=to-set-up-partner-metrics 01H7SZ8RA2VJ9466WSMN3WHR90=to-set-up-partner-metrics 01H8GHNPQKS7REZ9RPH0ZYEBHE=applovin-metrics 01H8GHNPQKCKMDS8AYETEDDZKH=google-ads-metrics 01H8H1GTRV7VNJDKFEF35HCNKY=meta-ads 01H7SZ8RA28T63K3NASWC92R0F=unity-ads-metrics 01H7W4JTRSJJ2R45JQVYHMYGX2=note 01H7SZ8RA3TPD6ED2HJZGTVRMS=save-and-share-views h_01HYT77DSHZ6FE0MSQS83FRGW0=save-private-dashboard-view 01HYT89BRYKRG44AT9MZWKZJNY=save-shared-dashboard-view h_01HYT8GXVJV8Q6GKBDHTTJ1SM2=share-view-url h_01H9J4Z9V9SJBTE63C358FME95=custom-tags h_01H9J4R9MTMGF9F1PNZRT2QZ1W=custom-dimensions 01H7SZ8RA3GW927GJBKKR4582T=create-and-manage-custom-dimensions 01H7SZ8RA3P8VQFH268G453FKM=example-csv 01H7SZ8RA307CBMA0533M3VGWK=traits-and-limitations h_01H9J67GSXXZ20W56NDVW2XDJC=name-convention-tags h_01H9J6PCQNVAB88ZCKRT3MVJEH=create-and-manage-name-convention-tags h_01H9J6PCQN6MV2KPYNFF7SB44Q=name-tag-traits-and-limitations h_01J1VPMV85CT5ZJNN3BW4FCW0D=additional-information" />

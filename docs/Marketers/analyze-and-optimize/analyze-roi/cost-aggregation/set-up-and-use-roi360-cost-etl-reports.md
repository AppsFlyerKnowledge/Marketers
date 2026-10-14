---
title: Set up and use ROI360 cost ETL reports
excerpt: >-
  Cost ETL, part of AppsFlyer ROI360, provides advertisers with campaign cost
  data having the best granularity available per media source. Data, updated up
  to 4 times daily, is delivered to your cloud service ready for loading into
  advertiser BI systems.
metadata:
  keywords:
    - Campaign
    - eCPI
    - clicks
    - Impressions
    - ROI
    - cost
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2020-05-17T15:36:41Z'
  edited_at: '2026-08-13T15:58:03Z'
  id: 360008849238
  locale: en-us
  section: Cost aggregation
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360008849238-Set-up-and-use-ROI360-cost-ETL-reports
---
[![5896_CostETL_graphic__2_.png](https://files.readme.io/3c9b8721fa4aba170c1ed7b7b365b4a5fe1cd74080469b3020d395352cede674-11178721788817.png)](https://files.readme.io/3c9b8721fa4aba170c1ed7b7b365b4a5fe1cd74080469b3020d395352cede674-11178721788817.png)

Cost ETL, part of AppsFlyer ROI360, provides advertisers with campaign cost data with the best granularity available per media source. Up to four times daily, the data is updated and delivered to your Data Locker cloud service, ready for loading into advertiser BI systems.

Advertisers can effortlessly route reports to multiple cloud destinations at once. This empowers teams when transitioning from one cloud service to another, as data is accessible in multiple services simultaneously.

Cost ETL reports include cost data tied to AppsFlyer attribution, including attribution metrics such as installs, re-attributions, and re-engagements.

## Four types of cost ETL reports

AppsFlyer offers four types of cost ETL reports to support different analysis needs.

* **Summary report:** (default) High-level cost data aggregated by media source. Recommended for analyzing cost and performance metrics at a broad level.
* **Geo report:** (optional) Cost data broken down by country (2-letter codes), such as US, CA, or FR. Recommended for geo-level performance and cost analysis.
* **Channel report:** (optional) Cost data segmented by channel (e.g., YouTube, Shopping). Best for channel-level performance and cost analysis.  
  [View sample file](https://docs.google.com/spreadsheets/d/e/2PACX-1vRqyHRTiLq8KUtELHqdaF6yVTfNE22X5UmUqXX89oOK5ZpS6lksXD0401G8MFmsaEzg2Csvf-d3y08Z/pub?single=true&output=csv)
* **All Cost Report**: a comprehensive view of mobile and non-mobile cost data, sourced directly from ad networks, with no attribution data. Currently covers Google Ads, Meta Ads, and TikTok.  
  [View sample file](https://docs.google.com/spreadsheets/d/e/2PACX-1vSdjA_4tdWBxxbI_ZM7mcZzCKhrWxQ-0m1DPIig-gMTpnDyLBDE_RGJ5zskNFpbsg/pub?gid=559626950&single=true&output=csv)

  > 📘 **Note**
  >
  > To start receiving Google Ads and Meta Ads in the All Cost report, please contact your AppsFlyer representative.


### Cost ETL report types overview table

<table><thead><tr><th> </th><th>Summary</th><th>Geo</th><th>Channel</th><th><strong>All Cost Report</strong></th></tr></thead><tbody><tr><td><strong>How to get the report</strong></td><td>Enable Cost ETL. The Summary report is selected by default.</td><td>Enable Cost ETL and select the Geo report.</td><td>Enable Cost ETL and select the Channel report.</td><td>Enable Cost ETL and select the <strong>Geo</strong> report. (All Cost report doesn't have a specific selector in cost ETL page)</td></tr><tr><td><strong>Where to find the report</strong></td><td>Depends on the cloud connector service you choose. It can be a folder (Summary) or a dedicated table.</td><td>Depends on the cloud connector service you choose. It can be a folder (Geo) or a dedicated table.</td><td>Depends on the cloud connector service you choose. It can be a folder (Channel) or a dedicated table.</td><td>Depends on the cloud connector service you choose. It can be a folder (All Cost) or a dedicated table.</td></tr><tr><td><strong>Cost type coverage</strong></td><td><p>Mobile cost: No limitation.<br/>CTV and web cost: Limited to:<br/> </p><ol><li>Campaigns with at least one conversion</li><li>Cost source is InCost API, Cost Import, or CPI</li></ol></td><td>Same as Summary.</td><td>Same as Summary.</td><td>Mobile, Web, CTV, PC, and Console cost from Google Ada, Meta Ads and TikTok.</td></tr><tr><td><strong>Media source coverage</strong></td><td>No limitation</td><td>No limitation</td><td>No limitation</td><td><ul><li><strong>TikTok:</strong> Data is automatically added.</li><li><strong>Google and Meta:</strong> Contact your CSM to enable.</li></ul></td></tr><tr><td><strong>Schema granularity</strong></td><td>Based on customer configuration in Cost ETL settings.</td><td><p>Based on customer configuration in Cost ETL settings.</p><p><br/>For Meta, the channel dimension has no values.</p></td><td><p>Based on customer configuration in Cost ETL settings.</p><p><br/>For Meta, the geo dimension has no value.</p></td><td><p>Based on customer configuration in Cost ETL settings.</p><p>For Meta, the Channel dimension is not supported.<br/><strong>Platform:</strong> A new dimension from the ad network indicating where the campaign runs (e.g., mobile, desktop, tablet).</p></td></tr><tr><td><strong>Attribution data</strong></td><td>Supported</td><td>Supported</td><td>Supported</td><td><p>Not supported.</p><p><br/>Attribution metrics values are displayed as zero (0), if they are configured by the customer to be part of the Cost ETL schema.</p></td></tr><tr><td><strong>App ID</strong></td><td>If the ad network does not support App ID granularity, the App ID is extracted from the attribution data.</td><td>Same as Summary.</td><td>Same as Summary.</td><td><p>Extracted from the ad network.</p><p><br/>If the App ID is not reported, the value will be unknown.</p></td></tr><tr><td><strong>Cost source</strong></td><td>API integration (Cost + InCost), Cost Import, CPI</td><td>Same as Summary.</td><td>Same as Summary.</td><td>API integration only.</td></tr><tr><td><strong>CNC</strong></td><td>Supported</td><td>Supported</td><td>Supported</td><td>Not supported.</td></tr><tr><td><strong>Agency data</strong></td><td>Supported</td><td>Supported</td><td>Supported</td><td><ul><li><strong>Facebook and Meta: </strong>Not supported.</li><li><strong>TikTok:</strong> Supported only for campaigns with App ID in AppsFlyer.</li></ul></td></tr><tr><td><strong>Agency fee</strong></td><td>Supported</td><td>Supported</td><td>Supported</td><td>Not supported. Value is always 0.</td></tr><tr><td><strong>Freshness</strong></td><td colspan="4">Data is collected from the ad network 6 times per day.<br/>Reports can be delivered up to 4 times per day (based on customer configuration).</td></tr></tbody></table>

## Report details

<div id="data-freshness" />

<Accordion title="Data freshness">

Campaign cost data is written:

* To your cloud service or bucket for viewing, transferring, and loading cost data into your systems.
* For all apps you choose to include in Cost ETL, per day, per version.
* Up to 4 times per day (data freshness: [intraday)](/docs/about-data-freshness-and-timezone-support#intraday-during-the-day).
* For the current day and the previous 6 days (referred to as 7 days in this article), as well as days 14, 29, and 88. Take this into consideration in your data loading process.
  * Example: For the date October 14, 2024, the file contains data for October 14 (the current day), October 13 (1 day back), October 12 (2 days back), October 11 (3 days back), October 10 (4 days back), October 9 (5 days back), October 8 (6 days back), September 30 (14 days back), September 15 (29 days back), and July 18 (88 days back).
  * The retroactive data allows for updates and corrections in the cost data reporting.
* For cost matched with an attribution, click, or impression.  
  **Note**:
  * Data for the last 7 days is pulled anew from the media sources. Data for days 14, 29, and 88 is re-processed.
  * Only cost data is updated retroactively; not attribution data.

</Accordion>

<div id="directory-and-filename-structure" />

<Accordion title="Directory and filename structure">

Data written to the cloud service or bucket has the directory and file structure described:

* When Cost ETL completes writing to a directory, a flag is set by creating a *success* file. This is always the most recent timestamp in the directory.
* The number of folders/files is as follows:
  * Summary: Up to 4 version folders per day.
    * Each version folder contains parquet files with 7 days of data.
  * Geo or Channel report: Each report contains up to 4 version folders per day.
    * Each version folder contains parquet files containing data with numbering starting from 1.
  * All cost: Based on the geo dimension, contains up to 4 files per day.

#### Data Locker connection directory structure

`<client-bucket>/<DL-generated-partition>/<connection-name>/t=<report-name>/dt=<YYYY-MM-DD>/v=<1/2/3/4>/<parquet file number>`

| **Variable** | **Content** |
| --- | --- |
| client-bucket | Name of the bucket as configured in the cloud service |
| DL-generated-partition | Generated partition, unique per customer |
| connection-name | Connection name as defined during Data Locker setup |
| t | The name of the specific report. Either:<ul><li>cost\_etl\_summary</li><li>cost\_etl\_geo</li><li>cost\_etl\_channel</li><li>cost\_etl\_all\_cost\_geo</li></ul> |
| dt | <ul><li>The report date, meaning the date the report was sent.</li><li>YYYY-MM-DD</li></ul> |
| v | <ul><li>The chronological version of the report per day (up to 4 possible daily reports)</li><li>Integer between 1-4</li></ul> |
| Parquet file number | <ul><li>Numbered starting from 00000</li><li>Example: `part-<number>`</li></ul> |

#### Cost ETL connection directory structure

`<advertiser bucket name>/cost_etl/version/dt=<yyyy-mm-dd>/b=<n>/<dimension>/<file name/<parquet file number>`

| **Variable** | **Content** |
| --- | --- |
| advertiser\_bucket\_name | As defined in the Cost ETL configuration: af-xpend-cost-etl--[your bucket name suffix] |
| cost\_etl | Always cost\_etl |
| version | Cost ETL version |
| date | Cost date<br /><br />Format: yyyy-mm-dd |
| batch | Number 1-4 |
| dimension | Data dimension:<ul><li>geo</li><li>channel</li></ul> |
| file\_name | <ul><li>summary</li><li>all-cost</li></ul> |
| Parquet file number | <ul><li>Numbered starting from 00000</li><li>Example: `part-<number>`</li></ul> |

**Example:** For the first data pull of June 23, 2020, the directory and file name structure is as follows: `/bucket-name/cost_etl/v1/dt=2020-06-23/b=1/geo/part-00001`

</Accordion>

<div id="file-fields" />

<Accordion title="File fields">

#### Fields/Dimensions

| **Field** | **Remarks** | **Always populated** | **Format** | **Included in summary file** |
| --- | --- | --- | --- | --- |
| ad | Component of the advertising hierarchy | No | String | - |
| ad\_account | <ul><li>Ad account from which cost data was pulled</li><li>Relevant for networks where connection is done using oAuth (logging in with your credentials), for example in Google or Meta ads</li></ul> | No | String | - |
| ad\_id | Component of the advertising hierarchy | No | String | - |
| adset | Component of the advertising hierarchy | No | String | - |
| adset\_id | Component of the advertising hierarchy | No | String | - |
| af\_bid\_strategy | Bid strategy mapped and normalized by AppsFlyer. Component of campaign properties. [Learn more](/docs/campaign-properties-in-cost-etl-reports) | No | String | - |
| af\_cost\_model | Cost model mapped and normalized by AppsFlyer. Component of campaign properties. [Learn more](/docs/campaign-properties-in-cost-etl-reports) | No | String | - |
| agency | Agency responsible for placing the ad | No | String | - |
| app\_id | App id in the AppsFlyer platform | Yes | String | **✓** |
| bid\_amount | Component of campaign properties. [Learn more](/docs/campaign-properties-in-cost-etl-reports) | No | Integer | - |
| bid\_strategy | Component of campaign properties. [Learn more](/docs/campaign-properties-in-cost-etl-reports) | No | String | - |
| campaign | Component of the advertising hierarchy | No | String | - |
| campaign\_id | Component of the advertising hierarchy | No | String | - |
| campaign\_objective | Component of campaign properties. [Learn more](/docs/campaign-properties-in-cost-etl-reports) | No | String | - |
| channel | Dimension in the advertising hierarchy | No | String | - |
| cost\_model | Component of campaign properties. [Learn more](/docs/campaign-properties-in-cost-etl-reports) | No | String | - |
| currency | Currency of advertiser spend as defined for the app in AppsFlyer | Yes | 3 character string compliant with ISO-4217 | **✓** |
| date | Date cost incurred reported by the media source | Yes | String yyyy-mm-dd | **✓** |
| geo | Dimension in the advertising hierarchy | No | 2 character string compliant with ISO 3166 | **✓** |
| keyword\_id | ID of the ASA keyword terms | Yes | String | - |
| keyword\_term | Word(s) used by the user for online search | Yes | String | - |
| media\_source | Media source responsible for display the ad | Yes | String | **✓** |
| original\_bid\_amount | Component of campaign properties. [Learn more](/docs/campaign-properties-in-cost-etl-reports) | No | Integer | - |
| original\_currency | Currency of cost as reported by the network before any conversions | No | 3 character string compliant with ISO-4217 | - |
| os | Operating system of the device. Possible values:<ul><li>android</li><li>windowsphone</li><li>ios</li></ul> | Yes | String | **-** |
| platform | The platform used for running the campaign (mobile, tablet, desktop, and CTV) | All cost report only | String | - |
| site\_id | Publisher ID | No | String | - |
| timezone | <ul><li>Timezone of the data as it is stored in AppsFlyer</li><li>Sometimes networks report data in a different time zone compared to what is defined in AppsFlyer. This data point helps explain cost discrepancies between AppsFlyer and networks</li></ul> | Yes | String | - |

#### Metrics

| **Field** | **Remarks** | **Always populated** | **Format** | **Included in summary file** |
| --- | --- | --- | --- | --- |
| ccvr | <ul><li>Cost per conversion</li><li>Formula: Cost / (installs + re-attributions + re-engagements)</li></ul> |  | Integer | - |
| clicks | <ul><li>Counted by AppsFlyer.</li><li>Includes both UA and retargeting.</li><li>[Engaged clicks](/docs/about-enriched-engagement-types#engaged_click) are subtracted from the total number of clicks.</li></ul> |  | Integer | **✓** |
| clicks\_discrepancy | <ul><li>Difference between those counted by ad network and AppsFlyer</li><li>Disregard this metric if:<ul><li>There isn't a match between cost and attribution.</li><li>The ad network doesn't support [reported clicks.](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api)</li></ul></li></ul> |  | Integer | - |
| cost | Amount of spend (including agency fees where relevant) |  | Value | **✓** |
| cost\_without\_fees | Cost minus the agency fee. Counted by AppsFlyer | Yes | Integer | **-** |
| cpi | <ul><li>Counted by AppsFlyer</li><li>Formula: Cost / installs</li></ul> |  | Integer | - |
| ctr | <ul><li>Click-through rate. Counted by AppsFlyer</li><li>Formula: Click / impressions</li></ul> | No | Integer | - |
| cvr | <ul><li>Conversion rate. Counted by AppsFlyer</li><li>Formula: Install / clicks</li></ul> |  | Integer | - |
| cvvr | <ul><li>Completed video view rate. Counted by AppsFlyer</li><li>Formula: Video completions / impressions</li></ul> |  | Integer | - |
| ecpc | <ul><li>Counted by AppsFlyer</li><li>Formula: Cost / clicks</li></ul> |  | Integer | - |
| ecpm | <ul><li>Counted by AppsFlyer</li><li>Formula: (Cost / impressions) * 1000</li></ul> |  | Integer | - |
| fees | Fees an agency charges in addition to the usual ad cost. Counted by AppsFlyer | Yes | Integer | **-** |
| impressions | <ul><li>Counted by AppsFlyer.</li><li>Includes both UA and retargeting.</li><li>[Engaged views](/docs/about-enriched-engagement-types#engaged_view)  are subtracted from the total number of impressions.</li></ul> | Yes.<br /><br />If no value is available for a particular metric, it is populated with 0. | Integer | **✓** |
| impressions\_discrepancy | <ul><li>Difference between those counted by ad network and AppsFlyer</li><li>Disregard this metric if:<ul><li>There isn't a match between cost and attribution.</li><li>The ad network doesn't support [reported impressions.](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api)</li></ul></li></ul> |  | Integer | - |
| installs | Counted by AppsFlyer |  | Integer | **✓** |
| installs\_discrepancy | <ul><li>Difference between those counted by ad network and AppsFlyer</li><li>Disregard this metric if:<ul><li>There isn't a match between cost and attribution.</li><li>The ad network doesn't support [reported conversions.](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api)</li></ul></li></ul> |  | Integer | - |
| original\_cost | Cost as reported by the network, in the currency reported by the network before any currency conversion (with agency fees calculated by AppsFlyer added where relevant) |  | Value | - |
| original\_cost\_without\_fees | Original cost as reported by the ad network, without agency fees | Yes | Integer | **-** |
| re\_attributions | Counted by AppsFlyer |  | Integer | **✓** |
| re\_engagements | Counted by AppsFlyer |  | Integer | **✓** |
| reported\_clicks | Counted by the Media source |  | Integer | **✓** |
| reported\_conversions | Counted by the Media source |  | Integer |  |
| reported\_cvr | <ul><li>Reported conversion rate</li><li>Formula: Reported conversions / reported clicks</li></ul> |  | Integer | - |
| reported\_impressions | Counted by the Media source |  | Integer | **✓** |
| video\_25p\_views | Video played 25%. Reported by  ad network |  | Integer | - |
| video\_50p\_views | Video played 50%. Reported by  ad network |  | Integer | - |
| video\_75p\_views | Video played 75%. Reported by  ad network |  | Integer | - |
| video\_completions | Reported by  ad network |  | Integer | - |

</Accordion>

## Procedures

<div id="set-up-cost-etl" />

<Accordion title="Set up Cost ETL">

This configuration procedure must be performed by an admin user.

**Before you start**:

Cost ETL setup requires:

* A cloud service set up with permission for AppsFlyer to write data to it. This means you need to set up either 1 or more of the following cloud services:
  * [AWS](/docs/data-locker-cloud-service-setup#aws-storage) bucket
  * [GCS](/docs/data-locker-cloud-service-setup#gcs-storage) bucket
  * [Beta] [Azure](/docs/data-locker-cloud-service-setup#beta--azure-storage) Blob
  * [Beta] [Yandex](/docs/data-locker-cloud-service-setup#yandex) bucket
  * [BigQuery](/docs/data-locker-cloud-service-setup#bigquery) data warehouse
  * [Snowflake](/docs/data-locker-cloud-service-setup#snowflake) warehouse
* AppsFlyer admin privileges and access to the AppsFlyer UI to complete Cost ETL setup.

[**![AppsFlyerAdmin_us-en.png](https://files.readme.io/4256ee1b617bf6f8fe1597e3a0d194b2d20b85b4cb8be41e0c9dee9396710605-4404934404753.png)**](https://files.readme.io/4256ee1b617bf6f8fe1597e3a0d194b2d20b85b4cb8be41e0c9dee9396710605-4404934404753.png) **To set up Cost ETL:**

1. In AppsFlyer, from the side menu, go to **Export** > **Cost ETL**.
2. Select or set up a **Data connection**:
   * If you already have data connections set up, in the **Connection** dropdown, select the ones you want for Cost ETL.  
     [![](https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png)](https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png)
   * If you don't have a data connection yet, click **+ New connection in Data Locker** and create a connection there:  
     [![](https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png)](https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png)
     1. Name your connection.  
        [![](https://files.readme.io/734060321cf14a4ebbce66fe2abc71ff299218f7c52cb64dc5b8e71c42d3632d-31233921530001.png)](https://files.readme.io/734060321cf14a4ebbce66fe2abc71ff299218f7c52cb64dc5b8e71c42d3632d-31233921530001.png)
     2. **Select a cloud service data destination**. Do one of the following:
        * Select **S3**.  
          [![](https://files.readme.io/1a78090f00407d44a5b74f3cb3b94e3a28064bc9b991b1cecf506fa0b9053842-31233961351441.png)](https://files.readme.io/1a78090f00407d44a5b74f3cb3b94e3a28064bc9b991b1cecf506fa0b9053842-31233961351441.png)
          1. Enter your AWS S3 bucket name. `af-` prefix is mandatory, and should be entered manually.
          2. Click **Test connection**.
          3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          4. Select whether to **Make this connection compatible with Adobe Experience Platform**.
          5. Click **Save**.
          6. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
        * Select **GCS**.  
          [![](https://files.readme.io/6da526f43131887270136e9fcfa9434ad88c2ce8cebdb896c07dac4a0652d683-31233921536913.png)](https://files.readme.io/6da526f43131887270136e9fcfa9434ad88c2ce8cebdb896c07dac4a0652d683-31233921536913.png)
          1. Enter your **GCS bucket name**.
          2. Click **Test connection**.
          3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          4. Select whether to **Make this connection compatible with Adobe Experience Platform**.
          5. Click **Save**.
          6. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
        * [Beta] Select **Azure**.  
          [![](https://files.readme.io/cd718eeebc5965d24a2d38457d4fa22c5691d6a186464187bea12199fb96671b-31233921550481.png)](https://files.readme.io/cd718eeebc5965d24a2d38457d4fa22c5691d6a186464187bea12199fb96671b-31233921550481.png)
          1. Enter your **Connection name**, **Storage account name**, and **Key**.
          2. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          3. Select whether to **Make this connection compatible with Adobe Experience Platform**.
          4. Click **Save**.
          5. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
        * [Beta] Select **Yandex**.  
          [![](https://files.readme.io/230e0d9c0b56b4c9f85da8c97f1ab91818c16ecfbabbf81ecb35f12d41716888-31233961360273.png)](https://files.readme.io/230e0d9c0b56b4c9f85da8c97f1ab91818c16ecfbabbf81ecb35f12d41716888-31233961360273.png)
          1. Enter your **Bucket name**, **Access key**, and **Secret key**.
          2. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          3. Select whether to **Make this connection compatible with Adobe Experience Platform**.
          4. Click **Save**.
          5. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
        * Select **BigQuery**.  
          [![](https://files.readme.io/6989fa8c869c08440da757b3ebb385754a4f23dbe4e2d38c50837448c08ab03b-31233921555857.png)](https://files.readme.io/6989fa8c869c08440da757b3ebb385754a4f23dbe4e2d38c50837448c08ab03b-31233921555857.png)
          1. Enter your BigQuery project ID and dataset name.
          2. Click **Test connection**.
          3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          4. Click **Save**.
          5. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
        * Select **Snowflake**.  
          [![](https://files.readme.io/b0e5f5ece797f46006d6e29a6afd01bc120b035590bd2ee87a54daa8c36bb0ed-31233961363985.png)](https://files.readme.io/b0e5f5ece797f46006d6e29a6afd01bc120b035590bd2ee87a54daa8c36bb0ed-31233961363985.png)
          1. Enter your Snowflake region and account ID.
          2. Click **Test connection**.
          3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          4. Click **Save**.
          5. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
3. Click **Next**.  
   [![](https://files.readme.io/4237ca8e7e70e0c04e924b61839d47d88e42075b4c257fcdf5e78870712d3582-31233921563153.png)](https://files.readme.io/4237ca8e7e70e0c04e924b61839d47d88e42075b4c257fcdf5e78870712d3582-31233921563153.png)
4. Set the report **Version schedule (UTC)**:  
   [![](https://files.readme.io/427b18043c0ab53ea559d53094efb6f04ad7505659c08ba7345b3a647f78d64d-31233961369105.png)](https://files.readme.io/427b18043c0ab53ea559d53094efb6f04ad7505659c08ba7345b3a647f78d64d-31233961369105.png)
   1. Select how many reports to receive every day (1, 2, 3, or 4).
   2. Select what time to receive the reports. [Learn more](/docs/set-up-and-use-roi360-cost-etl-reports#report-schedule)
   3. Click **Next**.
5. Set up the report details:
   1. Select 1 or more apps to include in reports. Select **Add all future apps** to automatically include apps you add in the future.  
      [![](https://files.readme.io/a5d453f40a7c5318f6a4c6cdfc5cf4d645c540c4b684362a796cda41d3c058c6-31233961373585.png)](https://files.readme.io/a5d453f40a7c5318f6a4c6cdfc5cf4d645c540c4b684362a796cda41d3c058c6-31233961373585.png)
   2. Select the reports that best fit your analysis needs. See descriptions in the [Report Types](#report-types) section.
      * The **Summary report** is selected by default.
      * To receive an All cost report, the **Geo report** must be selected.  
        [![](https://files.readme.io/3662c55c71f3390ac651c9269eac519f846b53ad675dab224b62fb09f81d4578-31233921571345.png)](https://files.readme.io/3662c55c71f3390ac651c9269eac519f846b53ad675dab224b62fb09f81d4578-31233921571345.png)
   3. Select dimensions to be included in the reports. **Note**: If you chose to receive the Geo report, the geo dimension is included by default. If you chose to receive the Channel report, the channel dimension is included by default.   
      [![](https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png)](https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png)
   4. Select the metrics to be included in the reports.   
      [![](https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg)](https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg)
6. Click **Apply**.

</Accordion>

<div id="edit-or-change-connection" />

<Accordion title="Edit or change connection">

You can edit or change connections to get data sent to different (or additional) places.

**Note**: After switching to an existing connection, you will not be able to revert to your previous Cost ETL connection.

#### Edit connection

**To edit connection details**:

1. In AppsFlyer, from the side menu, go to **Export** > **Cost ETL**.
2. In the **Data connection** section, either:
   * For Data Locker connections, in the **Connection** dropdown, hover over the connection you want to edit. The connection details display. Click **Edit in Data Locker**.  
     [![](https://files.readme.io/95c76d3bfc4a4db4bb9b4e67e4460680e0039e91dd930903515771e52c00ac7a-31233961377937.png)](https://files.readme.io/95c76d3bfc4a4db4bb9b4e67e4460680e0039e91dd930903515771e52c00ac7a-31233961377937.png)
   * For Cost ETL connections, click the **Connection details** dropdown. The connection details display.  
     [![](https://files.readme.io/67a1fb2ce45a49fc75d12eba4d1c3e67875b83883b0fc05307c080c6050be0f2-31233961380369.png)](https://files.readme.io/67a1fb2ce45a49fc75d12eba4d1c3e67875b83883b0fc05307c080c6050be0f2-31233961380369.png)
3. Follow the on-screen instructions to edit your connection details.
4. Click **Save changes** or **Apply** as prompted.

#### Change Data Locker connection

**To change from one Data Locker connection to another**:

1. In AppsFlyer, from the side menu, go to **Export** > **Cost ETL**.
2. In the **Data connection** section, either:
   * If you already have the Data Locker connections you want set up, in the **Connection** dropdown, select the ones you want for Cost ETL.  
     [![](https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png)](https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png)
   * If you don't have the Data Locker connection you want set up yet, click **+ New connection in Data Locker** and create a connection there. Then go back to the Cost ETL settings and select it from the **Connection** dropdown.  
     [![](https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png)](https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png)
3. Click **Save changes**.

#### Change from Cost ETL to Data Locker connection

**Before you begin**:

* Consider that after switching to a Data Locker connection, you can't switch back to your previous Cost ETL connection.
* Note that when switching to a Data Locker connection, the folder path structure changes to the following format without impacting the report data:

  `<client-bucket>/<DL-generated-partition>/<connection-name>/t=<report-name>/dt=<YYYY-MM-DD>/v=<1/2/3/4>/`

**To change from a deprecated Cost ETL connection to a Data Locker connection**:

1. In AppsFlyer, from the side menu, go to **Export** > **Cost ETL**.
2. In the **Data connection** section, click **Data Locker connections**.  
   [![](https://files.readme.io/2608d88368579c9fd3aa7648905484a56a7f0d989a96582cee51303409ce427c-31233961382289.png)](https://files.readme.io/2608d88368579c9fd3aa7648905484a56a7f0d989a96582cee51303409ce427c-31233961382289.png)
3. Do one of the following to set up the Data Locker connection:
   * If you already have the data connections you want set up, in the **Connection** dropdown, select the ones you want for Cost ETL.  
     [![](https://files.readme.io/da486f6399e92c49923527da3348f4535691768cebd7a776ec84f7a2a739c204-31233961385617.png)](https://files.readme.io/da486f6399e92c49923527da3348f4535691768cebd7a776ec84f7a2a739c204-31233961385617.png)
   * If you don't have the data connection you want set up yet, click **+ New connection in Data Locker** and create a connection there. Then go back to the Cost ETL settings and select it from the **Connection** dropdown.  
     [![](https://files.readme.io/0d48f83f30954f5f68efecf7e6c4cf2b39b295e0b893711bd2e2756406c42461-31233921587985.png)](https://files.readme.io/0d48f83f30954f5f68efecf7e6c4cf2b39b295e0b893711bd2e2756406c42461-31233921587985.png)
4. Click **Save changes**.

</Accordion>

<div id="aws-object-ownership" />

<Accordion title="Change AWS object ownership">

In AWS, by default, when AppsFlyer writes objects to your bucket, the object owner is AppsFlyer. Depending on your data loading process, you might have to change the default ownership to you—the bucket owner.

**To change the ownership of objects in your bucket**:

1. Sign in to the AWS Management Console and open the Amazon S3 console at [https://console.aws.amazon.com/s3/](https://console.aws.amazon.com/s3/).
2. In the **Buckets** list, choose the name of the bucket that you want to enable S3 Object Ownership for.
3. Go to the **Permissions** tab.
4. Under **Object Ownership,** click **Edit**.
5. Select **Bucket owner preferred.**
6. Click **Save**.

</Accordion>

## Best practices

<div id="report-schedule" />

<Accordion title="Report schedule">

The report schedule settings allow you to get the freshest data right when you need it.

When choosing your report schedule:

* Select the time to get the report as close as possible to the time you start processing data in your BI system.
* If you have any any ad networks that provide yesterday's data later than others, set an additional report at the time when that ad network data is ready.

</Accordion>

<div id="override-data" />

<Accordion title="Override data">

When pulling and analyzing your data, it is recommended to pull data for a specific date and batch, or override all previous data for the days that the current batch provides. Otherwise, you may see the same data repeated.

For example, batch 1 on February 20 contains data for Feb 14-20. But, batches written on February 19 also contained data for Feb 14 to Feb 19. Override the data of the previous days received on February 19 with the data received in the most recent February 20 batch.

</Accordion>

<div id="geo-versus-channel" />

<Accordion title="Geo versus channel">

Not all networks provide data for all dimensions together. Geo and channel data in Meta ads are the most common examples. This is why two separate data sets are provided. The geo data set is guaranteed to have geo data and the channel data set is guaranteed to have channel data.

In many cases and for many media sources, the data in the geo and channel sets will be identical. As such, consume one of the data sets (geo or channel), according to what best suits your needs.

If the integration agreement with a given media source doesn't include channel, so that channel is blank, we treat that data as if it contains the channel.

</Accordion>

<div id="aggregate-data" />

<Accordion title="Aggregate data">

Cost ETL provides flexible and granular data as deep as can be extracted from the ad network. To extract actionable insight from such potentially huge amounts of data, it is recommended to aggregate the data in a way that best suits your business needs. For example, if you need to understand cost data at the campaign and country-level, use those dimensions.

</Accordion>

<div id="standardization-across-networks" />

<Accordion title="Standardization across networks">

Not all networks provide data with the same granularity. For example, Meta ads doesn't provide site ID cost data, while X Ads doesn't provide geo cost data. Be aware of such cases as you aggregate Cost ETL data, and make sure you look at similar data as you compare networks.

</Accordion>

<div id="compare-data" />

<Accordion title="Compare data">

Cost ETL provides information regarding all your cost data. Some campaigns provided in Cost ETL do not appear in some AppsFlyer dashboards, for example, data of inactive campaigns, meaning campaigns without any recorded installs. To compare the data, find a specific campaign ID in the overview dashboard and compare it to its cost data in Cost ETL. [Learn more about cost data availability](/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports)

</Accordion>

<div id="combine-geo-report-and-all-cost-report" />

<Accordion title="Combine Geo report and All Cost report">

To get complete cost data tied with attribution for Google, Meta, TikTok (mobile and non-mobile), and other media sources (mobile only), use the following query:

```sql
with etl as (
    select *
    from etl
    where media_source = 'Facebook Ads'
      and date = '2025-07-16'
),

allcost as (
    select *
    from allcost
    where media_source = 'Facebook Ads'
      and date = '2025-07-16'
),

main as (
    select
        case when etl.date is null then 'all cost' else 'cost etl' end as report,
        coalesce(etl.date, allcost.date) as date,
        coalesce(etl.app_id, allcost.app_id) as app_id,
        etl.os,
        allcost.platform,
        coalesce(etl.media_source, allcost.media_source) as media_source,
        coalesce(etl.agency, allcost.agency) as agency,
        coalesce(etl.campaign_id, allcost.campaign_id) as campaign_id,
        coalesce(etl.campaign, allcost.campaign) as campaign,
        coalesce(etl.adset_id, allcost.adset_id) as adset_id,
        coalesce(etl.adset, allcost.adset) as adset,
        coalesce(etl.ad_id, allcost.ad_id) as ad_id,
        coalesce(etl.ad, allcost.ad) as ad,
        coalesce(etl.geo, allcost.geo) as geo,
        coalesce(etl.channel, allcost.channel) as channel,
        coalesce(etl.site_id, allcost.site_id) as site_id,
        coalesce(etl.ad_account, allcost.ad_account) as ad_account,
        coalesce(etl.keyword_id, allcost.keyword_id) as keyword_id,
        coalesce(etl.keywords, allcost.keywords) as keywords,
        coalesce(etl.campaign_objective, allcost.campaign_objective) as campaign_objective,
        coalesce(etl.af_cost_model, allcost.af_cost_model) as af_cost_model,
        coalesce(etl.bid_strategy, allcost.bid_strategy) as bid_strategy,
        coalesce(etl.af_bid_strategy, allcost.af_bid_strategy) as af_bid_strategy,
        coalesce(etl.currency, allcost.currency) as currency,
        coalesce(etl.cost, allcost.cost) as cost,
        coalesce(etl.impressions, allcost.impressions) as impressions,
        coalesce(etl.clicks, allcost.clicks) as clicks,
        coalesce(etl.installs, allcost.installs) as installs,
        coalesce(etl.re_attributions, allcost.re_attributions) as re_attributions,
        coalesce(etl.re_engagements, allcost.re_engagements) as re_engagements,
        coalesce(etl.original_cost, allcost.original_cost) as original_cost,
        coalesce(etl.reported_impressions, allcost.reported_impressions) as reported_impressions,
        coalesce(etl.reported_clicks, allcost.reported_clicks) as reported_clicks,
        coalesce(etl.reported_conversions, allcost.reported_conversions) as reported_conversions,
        coalesce(etl.ctr, allcost.ctr) as ctr,
        coalesce(etl.cvr, allcost.cvr) as cvr,
        coalesce(etl.ecpm, allcost.ecpm) as ecpm,
        coalesce(etl.cpi, allcost.cpi) as cpi,
        coalesce(etl.ccvr, allcost.ccvr) as ccvr,
        coalesce(etl.cvvr, allcost.cvvr) as cvvr,
        coalesce(etl.reported_cvr, allcost.reported_cvr) as reported_cvr,
        coalesce(etl.install_diff, allcost.install_diff) as install_diff,
        coalesce(etl.click_diff, allcost.click_diff) as click_diff,
        coalesce(etl.impression_diff, allcost.impression_diff) as impression_diff,
        coalesce(etl.ecpc, allcost.ecpc) as ecpc,
        coalesce(etl.video_25p_views, allcost.video_25p_views) as video_25p_views,
        coalesce(etl.video_50p_views, allcost.video_50p_views) as video_50p_views,
        coalesce(etl.video_75p_views, allcost.video_75p_views) as video_75p_views,
        coalesce(etl.video_completions, allcost.video_completions) as video_completions
    from etl
    full join allcost
        on etl.date = allcost.date
        and etl.app_id = allcost.app_id
        and etl.media_source = allcost.media_source
        and etl.campaign_id = allcost.campaign_id
        and etl.adset_id = allcost.adset_id
        and etl.ad_id = allcost.ad_id
        and etl.channel = allcost.channel
        and etl.geo = allcost.geo
        and etl.agency = allcost.agency
        and etl.site_id = allcost.site_id
        and etl.keyword_id = allcost.keyword_id
),

dedup as (
    select *,
           row_number() over (
               partition by date, media_source, agency, campaign_id, adset_id, ad_id, geo, channel, site_id, keyword_id
               order by report desc, cost desc
           ) as rank_for_dedup
    from main
)

select *
from dedup
where rank_for_dedup = 1;
```

</Accordion>

<div id="combine-cost-etl-and-cohort-reports" />

<Accordion title="Combine Cost ETL and cohort reports">

Consider combining Cost ETL reports with Aggregated advanced cohort reports (or regular Cohort reports via Data Locker) in your BI system. Together, they give the fullest picture of marketing performance with fresh and accurate data, including clicks, impressions, cost, revenue, in-app events, etc.). And you can use this combined data to get ROAS, CPA, etc. [Learn more](/docs/combine-cost-etl-and-cohort-reports-via-data-locker)

</Accordion>

## Additional information

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Timezone | If the timezone is changed, cost data is duplicated on the day and the day following the change. [Learn more](/docs/changing-app-time-zone-settings) |
| Data freshness | <ul><li>[Intraday](/docs/about-data-freshness-and-timezone-support#intraday-during-the-day). During Cost ETL setup, you set the report schedule, meaning when you want the reports to arrive.</li><li>Data usually arrives within one hour of the time you select. So if you select that a report should arrive by 6 AM, it arrives between 5-6 AM.</li></ul>**Note**: Once the cost data arrives to your bucket, further data transfer to your BI systems can vary greatly, depending on the report and parquet file size, which can be anywhere from a few KBs to many GBs. |
| All cost report | <ul><li>Doesn't include cost data for Google Performance Max campaigns.</li><li>Doesn't support Campaign name changes</li></ul> |
| SKAN campaign cost data | <ul><li>Cost ETL provides cost data for SKAN campaigns only if the campaign has at least one classic conversion.</li><li>For campaigns with SKAN-only conversions, cost data is available only if:<ul><li>The related ad network is Twitter (X) or Meta, or</li><li>The integration with the related ad network is marked as Inactive campaign (Column M= "Yes" in [this list](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api)).</li></ul></li></ul> |
| CTV and PC apps support | PC and CTV apps are not supported in Cost ETL reporting. |
| Google Web and Meta Web cost availability | To include cost data from [Google Web (`pid=googleads_int`](/docs/google-ads-adwords-create-web-based-campaigns#create-a-google-ads-integration-in-appsflyer)) and [Meta Web (`pid=metaweb_int`)](/docs/meta-ads-create-web-based-campaigns#how-to-create-a-meta-web-ads-campaign) in the All Cost report, you must create a cost connection in the Cost tab of your [Google Ads (`pid=googleadwords_int`)](/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory) and [Meta Ads (`pid=facebook_int`)](/docs/meta-ads-integration-setup#cost-clicks-and-impressions) active integrations. Without these connections Google and Meta Web cost data won’t appear in the report. |

</Accordion>

<div data-zendesk-anchors="h_01K4WKGHP4S2B23R0Z57NFESPE=four-types-of-cost-etl-reports h_01JZJVXY0BA25QM9PK4YRT8DZ6=note cost-etl-report-comparison-table=cost-etl-report-types-overview-table h_01K4WN2VMPZYA6273EDW7CSJZ9=cost-etl-report-types-overview-table h_01JYXKJFYG6FKM8S6C8GYHPK6T=report-details h_01JYXKJFYGE8SHR071RNXW5V97=data-freshness h_01HA29GW8PWN30BCQCK29V0FTA=directory-and-filename-structure h_01JD4P98XF9S47EDHP38VXW1XS=data-locker-connection-directory-structure h_01JKWMF6V57C35F1A0BVH18CY1=cost-etl-connection-directory-structure h_01HA29GW8P0B1JJTGYDW863D7Z=file-fields h_01HA29GW8PQATB4K5VJP1HD4NW=fieldsdimensions h_01HA29GW8PZTS7XDWGYWXFZPYG=metrics 01JCZDRERADNNX04RT752793PG=procedures 01JCZP8A5W67W66N886KHNRR4A=set-up-cost-etl 01JCZME67YK848NM0RJTM1J5ZG=edit-or-change-connection h_01JCZMGC8J41Y7H4JGZDVWYDJS=edit-connection change-data-locker-connections=change-data-locker-connection h_01JCZNQF3QE7P8PBQPKXZK1SA2=change-data-locker-connection h_01JKWMF6V70W9FA90SSKJ77R2Z=change-from-cost-etl-to-data-locker-connection h_01HA29GW8Q6D630E8SDVSFYVG7=aws-object-ownership h_01HA29GW8QKPQXE4GHECAC5R5X=best-practices h_01J0NRD227RQR50CMNW60SF7SK=report-schedule h_01HA29GW8QHX8AMK4T7E85H7RS=override-data h_01HA29GW8QT5FNNYSWHCT99D68=geo-versus-channel h_01HA29GW8QA3FP46EMZVYDEZF3=aggregate-data h_01HA29GW8QPW0NXEMF1WGJMKSF=standardization-across-networks h_01HA29GW8Q3FNS0W7SKTG7S9R1=compare-data h_01K4WNM1ZFSMFZEV3V2HQ5PYQE=combine-geo-report-and-all-cost-report h_01J582E5JNR5DJ9T8HKDG2XSRR=combine-cost-etl-and-cohort-reports h_01HA286GA6WPYVNN7KCXK7DGFM=additional-information h_01HA282W8WHHNDG75XZNSV2QQF=traits-and-limitations" />

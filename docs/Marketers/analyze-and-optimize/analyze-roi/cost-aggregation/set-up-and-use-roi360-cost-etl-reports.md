---
title: "Set up and use ROI360 cost ETL reports"
excerpt: "Learn how to configure and use AppsFlyer ROI360 Cost ETL reports to deliver granular campaign cost data directly to your cloud service."
---
**At a glance:** Cost ETL, part of AppsFlyer ROI360, provides advertisers with campaign cost data having the best granularity available per media source. Data, updated up to 4 times daily, is delivered to your cloud service ready for loading into advertiser BI systems.

[![5896_CostETL_graphic__2_.png](https://files.readme.io/3c9b8721fa4aba170c1ed7b7b365b4a5fe1cd74080469b3020d395352cede674-11178721788817.png)](https://support.appsflyer.com/hc/article_attachments/11178721788817)

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

  CALLSTART::Note::

  #### Note

  To start receiving Google Ads and Meta Ads in the All Cost report, please contact your AppsFlyer representative.

  CALLEND::

### Cost ETL report types overview table

|  | Summary | Geo | Channel | **All Cost Report** |
| --- | --- | --- | --- | --- |
| **How to get the report** | Enable Cost ETL. The Summary report is selected by default. | Enable Cost ETL and select the Geo report. | Enable Cost ETL and select the Channel report. | Enable Cost ETL and select the **Geo** report. (All Cost report doesn't have a specific selector in cost ETL page) |
| **Where to find the report** | Depends on the cloud connector service you choose. It can be a folder (Summary) or a dedicated table. | Depends on the cloud connector service you choose. It can be a folder (Geo) or a dedicated table. | Depends on the cloud connector service you choose. It can be a folder (Channel) or a dedicated table. | Depends on the cloud connector service you choose. It can be a folder (All Cost) or a dedicated table. |
| **Cost type coverage** | Mobile cost: No limitation. CTV and web cost: Limited to:   1. Campaigns with at least one conversion 2. Cost source is InCost API, Cost Import, or CPI | Same as Summary. | Same as Summary. | Mobile, Web, CTV, PC, and Console cost from Google Ada, Meta Ads and TikTok. |
| **Media source coverage** | No limitation | No limitation | No limitation | * **TikTok:** Data is automatically added. * **Google and Meta:** Contact your CSM to enable. |
| **Schema granularity** | Based on customer configuration in Cost ETL settings. | Based on customer configuration in Cost ETL settings.  For Meta, the channel dimension has no values. | Based on customer configuration in Cost ETL settings.  For Meta, the geo dimension has no value. | Based on customer configuration in Cost ETL settings.  For Meta, the Channel dimension is not supported. **Platform:** A new dimension from the ad network indicating where the campaign runs (e.g., mobile, desktop, tablet). |
| **Attribution data** | Supported | Supported | Supported | Not supported.  Attribution metrics values are displayed as zero (0), if they are configured by the customer to be part of the Cost ETL schema. |
| **App ID** | If the ad network does not support App ID granularity, the App ID is extracted from the attribution data. | Same as Summary. | Same as Summary. | Extracted from the ad network.  If the App ID is not reported, the value will be unknown. |
| **Cost source** | API integration (Cost + InCost), Cost Import, CPI | Same as Summary. | Same as Summary. | API integration only. |
| **CNC** | Supported | Supported | Supported | Not supported. |
| **Agency data** | Supported | Supported | Supported | * **Facebook and Meta:** Not supported. * **TikTok:** Supported only for campaigns with App ID in AppsFlyer. |
| **Agency fee** | Supported | Supported | Supported | Not supported. Value is always 0. |
| **Freshness** | Data is collected from the ad network 6 times per day. Reports can be delivered up to 4 times per day (based on customer configuration). | | | |

## Report details

### Data freshness

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

### Directory and filename structure

Data written to the cloud service or bucket has the directory and file structure described:

* When Cost ETL completes writing to a directory, a flag is set by creating a *success* file. This is always the most recent timestamp in the directory.
* The number of folders/files is as follows:
  * Summary: Up to 4 version folders per day.
    * Each version folder contains parquet files with 7 days of data.
  * Geo or Channel report: Each report contains up to 4 version folders per day.
    * Each version folder contains parquet files containing data with numbering starting from 1.
  * All cost: Based on the geo dimension, contains up to 4 files per day.

#### Data Locker connection directory structure

`/<DL-generated-partition>//t=/dt=<YYYY-MM-DD>/v=<1/2/3/4>/`

| **Variable** | **Content** |
| --- | --- |
| client-bucket | Name of the bucket as configured in the cloud service |
| DL-generated-partition | Generated partition, unique per customer |
| connection-name | Connection name as defined during Data Locker setup |
| t | The name of the specific report. Either:<br /><br />* cost\_etl\_summary<br />* cost\_etl\_geo<br />* cost\_etl\_channel<br />* cost\_etl\_all\_cost\_geo |
| dt | * The report date, meaning the date the report was sent.<br />* YYYY-MM-DD |
| v | * The chronological version of the report per day (up to 4 possible daily reports)<br />* Integer between 1-4 |
| Parquet file number | * Numbered starting from 00000<br />* Example: `part-` |

#### Cost ETL connection directory structure

`/cost_etl/version/dt=/b=//`

| **Variable** | **Content** |
| --- | --- |
| advertiser\_bucket\_name | As defined in the Cost ETL configuration: af-xpend-cost-etl--[your bucket name suffix] |
| cost\_etl | Always cost\_etl |
| version | Cost ETL version |
| date | Cost date<br /><br />Format: yyyy-mm-dd |
| batch | Number 1-4 |
| dimension | Data dimension:<br /><br />* geo<br />* channel |
| file\_name | * summary<br />* all-cost |
| Parquet file number | * Numbered starting from 00000<br />* Example: `part-` |

**Example:** For the first data pull of June 23, 2020, the directory and file name structure is as follows: `/bucket-name/cost_etl/v1/dt=2020-06-23/b=1/geo/part-00001`

### File fields

#### Fields/Dimensions

| **Field** | **Remarks** | **Always populated** | **Format** | **Included in summary file** |
| --- | --- | --- | --- | --- |
| ad | Component of the advertising hierarchy | No | String | - |
| ad\_account | * Ad account from which cost data was pulled<br />* Relevant for networks where connection is done using oAuth (logging in with your credentials), for example in Google or Meta ads | No | String | - |
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
| os | Operating system of the device. Possible values:<br /><br />* android<br />* windowsphone<br />* ios | Yes | String | **-** |
| platform | The platform used for running the campaign (mobile, tablet, desktop, and CTV) | All cost report only | String | - |
| site\_id | Publisher ID | No | String | - |
| timezone | * Timezone of the data as it is stored in AppsFlyer<br />* Sometimes networks report data in a different time zone compared to what is defined in AppsFlyer. This data point helps explain cost discrepancies between AppsFlyer and networks | Yes | String | - |

#### Metrics

| **Field** | **Remarks** | **Always populated** | **Format** | **Included in summary file** |
| --- | --- | --- | --- | --- |
| ccvr | * Cost per conversion<br />* Formula: Cost / (installs + re-attributions + re-engagements) |  | Integer | - |
| clicks | * Counted by AppsFlyer.<br />* Includes both UA and retargeting.<br />* [Engaged clicks](/docs/about-enriched-engagement-types#engaged_click) are subtracted from the total number of clicks. |  | Integer | **✓** |
| clicks\_discrepancy | * Difference between those counted by ad network and AppsFlyer<br />* Disregard this metric if:<br />  * There isn't a match between cost and attribution.<br />  * The ad network doesn't support [reported clicks.](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) |  | Integer | - |
| cost | Amount of spend (including agency fees where relevant) |  | Value | **✓** |
| cost\_without\_fees | Cost minus the agency fee. Counted by AppsFlyer | Yes | Integer | **-** |
| cpi | * Counted by AppsFlyer<br />* Formula: Cost / installs |  | Integer | - |
| ctr | * Click-through rate. Counted by AppsFlyer<br />* Formula: Click / impressions | No | Integer | - |
| cvr | * Conversion rate. Counted by AppsFlyer<br />* Formula: Install / clicks |  | Integer | - |
| cvvr | * Completed video view rate. Counted by AppsFlyer<br />* Formula: Video completions / impressions |  | Integer | - |
| ecpc | * Counted by AppsFlyer<br />* Formula: Cost / clicks |  | Integer | - |
| ecpm | * Counted by AppsFlyer<br />* Formula: (Cost / impressions) * 1000 |  | Integer | - |
| fees | Fees an agency charges in addition to the usual ad cost. Counted by AppsFlyer | Yes | Integer | **-** |
| impressions | * Counted by AppsFlyer.<br />* Includes both UA and retargeting.<br />* [Engaged views](/docs/about-enriched-engagement-types#engaged_view)  are subtracted from the total number of impressions. | Yes.<br /><br />If no value is available for a particular metric, it is populated with 0. | Integer | **✓** |
| impressions\_discrepancy | * Difference between those counted by ad network and AppsFlyer<br />* Disregard this metric if:<br />  * There isn't a match between cost and attribution.<br />  * The ad network doesn't support [reported impressions.](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) |  | Integer | - |
| installs | Counted by AppsFlyer |  | Integer | **✓** |
| installs\_discrepancy | * Difference between those counted by ad network and AppsFlyer<br />* Disregard this metric if:<br />  * There isn't a match between cost and attribution.<br />  * The ad network doesn't support [reported conversions.](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) |  | Integer | - |
| original\_cost | Cost as reported by the network, in the currency reported by the network before any currency conversion (with agency fees calculated by AppsFlyer added where relevant) |  | Value | - |
| original\_cost\_without\_fees | Original cost as reported by the ad network, without agency fees | Yes | Integer | **-** |
| re\_attributions | Counted by AppsFlyer |  | Integer | **✓** |
| re\_engagements | Counted by AppsFlyer |  | Integer | **✓** |
| reported\_clicks | Counted by the Media source |  | Integer | **✓** |
| reported\_conversions | Counted by the Media source |  | Integer |  |
| reported\_cvr | * Reported conversion rate<br />* Formula: Reported conversions / reported clicks |  | Integer | - |
| reported\_impressions | Counted by the Media source |  | Integer | **✓** |
| video\_25p\_views | Video played 25%. Reported by  ad network |  | Integer | - |
| video\_50p\_views | Video played 50%. Reported by  ad network |  | Integer | - |
| video\_75p\_views | Video played 75%. Reported by  ad network |  | Integer | - |
| video\_completions | Reported by  ad network |  | Integer | - |

## Procedures

### Set up Cost ETL

This configuration procedure must be performed by an admin user.

**Before you start**:

Cost ETL setup requires:

* A cloud service set up with permission for AppsFlyer to write data to it. This means you need to set up either 1 or more of the following cloud services:
  * [AWS](/docs/data-locker-cloud-service-setup#aws-storage) bucket
  * [GCS](/docs/data-locker-cloud-service-setup#gcs-storage) bucket
  * [Beta] [Azure](/docs/data-locker-cloud-service-setup#%5Bbeta%5D-azure-storage) Blob
  * [Beta] [Yandex](/docs/data-locker-cloud-service-setup#yandex) bucket
  * [BigQuery](/docs/data-locker-cloud-service-setup#bigquery) data warehouse
  * [Snowflake](/docs/data-locker-cloud-service-setup#snowflake) warehouse
* AppsFlyer admin privileges and access to the AppsFlyer UI to complete Cost ETL setup.

[**![AppsFlyerAdmin_us-en.png](https://support.appsflyer.com/hc/article_attachments/4404934404753)**](https://support.appsflyer.com/hc/article_attachments/4404934404753) **To set up Cost ETL:**

1. In AppsFlyer, from the side menu, go to **Export** > **Cost ETL**.
2. Select or set up a **Data connection**:
   * If you already have data connections set up, in the **Connection** dropdown, select the ones you want for Cost ETL.  
     [![](https://support.appsflyer.com/hc/article_attachments/31233921523601)](https://support.appsflyer.com/hc/article_attachments/31233921523601)
   * If you don't have a data connection yet, click **+ New connection in Data Locker** and create a connection there:  
     [![](https://support.appsflyer.com/hc/article_attachments/31233961342865)](https://support.appsflyer.com/hc/article_attachments/31233961342865)
     1. Name your connection.  
        [![](https://support.appsflyer.com/hc/article_attachments/31233921530001)](https://support.appsflyer.com/hc/article_attachments/31233921530001)
     2. **Select a cloud service data destination**. Do one of the following:
        * Select **S3**.  
          [![](https://support.appsflyer.com/hc/article_attachments/31233961351441)](https://support.appsflyer.com/hc/article_attachments/31233961351441)
          1. Enter your AWS S3 bucket name. `af-` prefix is mandatory, and should be entered manually.
          2. Click **Test connection**.
          3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          4. Select whether to **Make this connection compatible with Adobe Experience Platform**.
          5. Click **Save**.
          6. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
        * Select **GCS**.  
          [![](https://support.appsflyer.com/hc/article_attachments/31233921536913)](https://support.appsflyer.com/hc/article_attachments/31233921536913)
          1. Enter your **GCS bucket name**.
          2. Click **Test connection**.
          3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          4. Select whether to **Make this connection compatible with Adobe Experience Platform**.
          5. Click **Save**.
          6. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
        * [Beta] Select **Azure**.  
          [![](https://support.appsflyer.com/hc/article_attachments/31233921550481)](https://support.appsflyer.com/hc/article_attachments/31233921550481)
          1. Enter your **Connection name**, **Storage account name**, and **Key**.
          2. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          3. Select whether to **Make this connection compatible with Adobe Experience Platform**.
          4. Click **Save**.
          5. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
        * [Beta] Select **Yandex**.  
          [![](https://support.appsflyer.com/hc/article_attachments/31233961360273)](https://support.appsflyer.com/hc/article_attachments/31233961360273)
          1. Enter your **Bucket name**, **Access key**, and **Secret key**.
          2. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          3. Select whether to **Make this connection compatible with Adobe Experience Platform**.
          4. Click **Save**.
          5. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
        * Select **BigQuery**.  
          [![](https://support.appsflyer.com/hc/article_attachments/31233921555857)](https://support.appsflyer.com/hc/article_attachments/31233921555857)
          1. Enter your BigQuery project ID and dataset name.
          2. Click **Test connection**.
          3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          4. Click **Save**.
          5. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
        * Select **Snowflake**.  
          [![](https://support.appsflyer.com/hc/article_attachments/31233961363985)](https://support.appsflyer.com/hc/article_attachments/31233961363985)
          1. Enter your Snowflake region and account ID.
          2. Click **Test connection**.
          3. Verify that an error message indicating that the bucket path is invalid isn't displayed.
          4. Click **Save**.
          5. In the Cost ETL setup, in the **Connection** dropdown, select the cloud service you created.
3. Click **Next**.  
   [![](https://support.appsflyer.com/hc/article_attachments/31233921563153)](https://support.appsflyer.com/hc/article_attachments/31233921563153)
4. Set the report **Version schedule (UTC)**:  
   [![](https://support.appsflyer.com/hc/article_attachments/31233961369105)](https://support.appsflyer.com/hc/article_attachments/31233961369105)
   1. Select how many reports to receive every day (1, 2, 3, or 4).
   2. Select what time to receive the reports. [Learn more](/docs/set-up-and-use-roi360-cost-etl-reports#report-schedule)
   3. Click **Next**.
5. Set up the report details:
   1. Select 1 or more apps to include in reports. Select **Add all future apps** to automatically include apps you add in the future.  
      [![](https://support.appsflyer.com/hc/article_attachments/31233961373585)](https://support.appsflyer.com/hc/article_attachments/31233961373585)
   2. Select the reports that best fit your analysis needs. See descriptions in the [Report Types](#report-types) section.
      * The **Summary report** is selected by default.
      * To receive an All cost report, the **Geo report** must be selected.  
        [![](https://support.appsflyer.com/hc/article_attachments/31233921571345)](https://support.appsflyer.com/hc/article_attachments/31233921571345)
   3. Select dimensions to be included in the reports. **Note**: If you chose to receive the Geo report, the geo dimension is included by default. If you chose to receive the Channel report, the channel dimension is included by default.   
      [![](https://support.appsflyer.com/hc/article_attachments/4476081988241)](https://support.appsflyer.com/hc/article_attachments/4476081988241)
   4. Select the metrics to be included in the reports.   
      [![](https://support.appsflyer.com/hc/article_attachments/360019263038)](https://support.appsflyer.com/hc/article_attachments/360019263038)
6. Click **Apply**.

### Edit or change connection

You can edit or change connections to get data sent to different (or additional) places.

**Note**: After switching to an existing connection, you will not be able to revert to your previous Cost ETL connection.

#### Edit connection

**To edit connection details**:

1. In AppsFlyer, from the side menu, go to **Export** > **Cost ETL**.
2. In the **Data connection** section, either:
   * For Data Locker connections, in the **Connection** dropdown, hover over the connection you want to edit. The connection details display. Click **Edit in Data Locker**.  
     [![](https://support.appsflyer.com/hc/article_attachments/31233961377937)](https://support.appsflyer.com/hc/article_attachments/31233961377937)
   * For Cost ETL connections, click the **Connection details** dropdown. The connection details display.  
     [![](https://support.appsflyer.com/hc/article_attachments/31233961380369)](https://support.appsflyer.com/hc/article_attachments/31233961380369)
3. Follow the on-screen instructions to edit your connection details.
4. Click **Save changes** or **Apply** as prompted.

#### Change Data Locker connection

**To change from one Data Locker connection to another**:

1. In AppsFlyer, from the side menu, go to **Export** > **Cost ETL**.
2. In the **Data connection** section, either:
   * If you already have the Data Locker connections you want set up, in the **Connection** dropdown, select the ones you want for Cost ETL.  
     [![](https://support.appsflyer.com/hc/article_attachments/31233921523601)](https://support.appsflyer.com/hc/article_attachments/31233921523601)
   * If you don't have the Data Locker connection you want set up yet, click **+ New connection in Data Locker** and create a connection there. Then go back to the Cost ETL settings and select it from the **Connection** dropdown.  
     [![](https://support.appsflyer.com/hc/article_attachments/31233961342865)](https://support.appsflyer.com/hc/article_attachments/31233961342865)
3. Click **Save changes**.

#### Change from Cost ETL to Data Locker connection

**Before you begin**:

* Consider that after switching to a Data Locker connection, you can't switch back to your previous Cost ETL connection.
* Note that when switching to a Data Locker connection, the folder path structure changes to the following format without impacting the report data:

  `/<DL-generated-partition>//t=/dt=<YYYY-MM-DD>/v=<1/2/3/4>/`

**To change from a deprecated Cost ETL connection to a Data Locker connection**:

1. In AppsFlyer, from the side menu, go to **Export** > **Cost ETL**.
2. In the **Data connection** section, click **Data Locker connections**.  
   [![](https://support.appsflyer.com/hc/article_attachments/31233961382289)](https://support.appsflyer.com/hc/article_attachments/31233961382289)
3. Do one of the following to set up the Data Locker connection:
   * If you already have the data connections you want set up, in the **Connection** dropdown, select the ones you want for Cost ETL.  
     [![](https://support.appsflyer.com/hc/article_attachments/31233961385617)](https://support.appsflyer.com/hc/article_attachments/31233961385617)
   * If you don't have the data connection you want set up yet, click **+ New connection in Data Locker** and create a connection there. Then go back to the Cost ETL settings and select it from the **Connection** dropdown.  
     [![](https://support.appsflyer.com/hc/article_attachments/31233921587985)](https://support.appsflyer.com/hc/article_attachments/31233921587985)
4. Click **Save changes**.

### Change AWS object ownership

In AWS, by default, when AppsFlyer writes objects to your bucket, the object owner is AppsFlyer. Depending on your data loading process, you might have to change the default ownership to you—the bucket owner.

**To change the ownership of objects in your bucket**:

1. Sign in to the AWS Management Console and open the Amazon S3 console at [https://console.aws.amazon.com/s3/](https://console.aws.amazon.com/s3/).
2. In the **Buckets** list, choose the name of the bucket that you want to enable S3 Object Ownership for.
3. Go to the **Permissions** tab.
4. Under **Object Ownership,**click **Edit**.
5. Select **Bucket owner preferred.**
6. Click **Save**.

## Best practices

### Report schedule

The report schedule settings allow you to get the freshest data right when you need it.

When choosing your report schedule:

* Select the time to get the report as close as possible to the time you start processing data in your BI system.
* If you have any any ad networks that provide yesterday's data later than others, set an additional report at the time when that ad network data is ready.

### Override data

When pulling and analyzing your data, it is recommended to pull data for a specific date and batch, or override all previous data for the days that the current batch provides. Otherwise, you may see the same data repeated.

For example, batch 1 on February 20 contains data for Feb 14-20. But, batches written on February 19 also contained data for Feb 14 to Feb 19. Override the data of the previous days received on February 19 with the data received in the most recent February 20 batch.

### Geo versus channel

Not all networks provide data for all dimensions together. Geo and channel data in Meta ads are the most common examples. This is why two separate data sets are provided. The geo data set is guaranteed to have geo data and the channel data set is guaranteed to have channel data.

In many cases and for many media sources, the data in the geo and channel sets will be identical. As such, consume one of the data sets (geo or channel), according to what best suits your needs.

If the integration agreement with a given media source doesn't include channel, so that channel is blank, we treat that data as if it contains the channel.

### Aggregate data

Cost ETL provides flexible and granular data as deep as can be extracted from the ad network. To extract actionable insight from such potentially huge amounts of data, it is recommended to aggregate the data in a way that best suits your business needs. For example, if you need to understand cost data at the campaign and country-level, use those dimensions.

### Standardization across networks

Not all networks provide data with the same granularity. For example, Meta ads doesn't provide site ID cost data, while X Ads doesn't provide geo cost data. Be aware of such cases as you aggregate Cost ETL data, and make sure you look at similar data as you compare networks.

### Compare data

Cost ETL provides information regarding all your cost data. Some campaigns provided in Cost ETL do not appear in some AppsFlyer dashboards, for example, data of inactive campaigns, meaning campaigns without any recorded installs. To compare the data, find a specific campaign ID in the overview dashboard and compare it to its cost data in Cost ETL. [Learn more about cost data availability](/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports)

### Combine Geo report and All Cost report

To get complete cost data tied with attribution for Google, Meta, TikTok (mobile and non-mobile), and other media sources (mobile only), use the following query:

```
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

### Combine Cost ETL and cohort reports

Consider combining Cost ETL reports with Aggregated advanced cohort reports (or regular Cohort reports via Data Locker) in your BI system. Together, they give the fullest picture of marketing performance with fresh and accurate data, including clicks, impressions, cost, revenue, in-app events, etc.). And you can use this combined data to get ROAS, CPA, etc. [Learn more](/docs/combine-cost-etl-and-cohort-reports-via-data-locker)

## Additional information

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| Timezone | If the timezone is changed, cost data is duplicated on the day and the day following the change. [Learn more](/docs/changing-app-time-zone-settings) |
| Data freshness | * [Intraday](/docs/about-data-freshness-and-timezone-support#intraday-during-the-day). During Cost ETL setup, you set the report schedule, meaning when you want the reports to arrive.<br />* Data usually arrives within one hour of the time you select. So if you select that a report should arrive by 6 AM, it arrives between 5-6 AM.<br /><br />**Note**: Once the cost data arrives to your bucket, further data transfer to your BI systems can vary greatly, depending on the report and parquet file size, which can be anywhere from a few KBs to many GBs. |
| All cost report | * Doesn't include cost data for Google Performance Max campaigns.<br />* Doesn't support Campaign name changes |
| SKAN campaign cost data | * Cost ETL provides cost data for SKAN campaigns only if the campaign has at least one classic conversion.<br />* For campaigns with SKAN-only conversions, cost data is available only if:<br />  * The related ad network is Twitter (X) or Meta, or<br />  * The integration with the related ad network is marked as Inactive campaign (Column M= "Yes" in [this list](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api)). |
| CTV and PC apps support | PC and CTV apps are not supported in Cost ETL reporting. |
| Google Web and Meta Web cost availability | To include cost data from [Google Web (`pid=googleads_int`](/docs/google-ads-adwords-create-web-based-campaigns#create-a-google-ad-for-web-integration-in-appsflyer)) and [Meta Web (`pid=metaweb_int`)](/docs/meta-ads-create-web-based-campaigns#how-to-create-a-meta-ads-campaign) in the All Cost report, you must create a cost connection in the Cost tab of your [Google Ads (`pid=googleadwords_int`)](/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory) and [Meta Ads (`pid=facebook_int`)](/docs/meta-ads-integration-setup#cost-clicks-and-impressions) active integrations. Without these connections Google and Meta Web cost data won’t appear in the report. |
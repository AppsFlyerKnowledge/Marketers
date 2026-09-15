---
title: "Ad revenue signals for UA ad networks"
excerpt: "Ad networks responsible for user acquisition can receive ad revenue data via Data Locker to optimize their customers' UA campaigns and improve ROAS."
---
**At a glance:** Ad networks responsible for user acquisition can receive data regarding ad revenue and use it to optimize their customers' UA campaigns.

Ad networks can receive reports via Data Locker with valuable ad revenue information regarding users. These users may have been acquired from campaigns served through them, or they may be from a different media source.

Ad networks can then ingest this data to campaign-targeting and optimization algorithms, and use it to improve ROAS campaigns based on a complete view of UA-generated revenue.

## Set the Ad Revenue report in Data Locker

The following activities need to be completed to access the Ad Revenue report in Data Locker:

- Ad networks have to [onboard to Data Locker for Partners](/docs/data-locker-for-partners#set-up-data-locker).
- Ad networks have to [configure the report output settings](/docs/ad-revenue-signals-for-ua-ad-networks#configure-the-report-output-settings) and [enable the Ad revenue report](/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report).
- Advertisers have to permit ad networks to view the report. [See advertiser instructions](https://support.appsflyer.com/hc/articles/24100803679761-ROI360-Sharing-ad-revenue-data-with-UA-partners#ua-signals-for-ad-networks)

### Configure the report output settings

To configure the report output setting, follow the steps below:

1. In AppsFlyer, go to **Report** > **Data Locker.**
2. In the **Report output settings** area turn on **Send reports**.
3. Set the report file output properties.
   - The report format (Parqet/CSV).
   - The report compression method (Snappy/GZIPO/Uncompressed).
   - The maximum number of rows in a file.
4. Review the expected path of the report file outputs. The path is set according to your connection settings. To learn how to set up the connection see [Set up Data Locker](/docs/data-locker-for-partners#set-up-data-locker).

### Enable the Ad revenue report

1. In the **Data Locker content** section select the **Ad revenue [daily]** report type.
2. Click **Save connection**.
3. Make sure that the advertiser permitted the Ad network to view the report.
4. For instruction, see [Permit ad networks to get ad revenue data.](https://support.appsflyer.com/hc/articles/217490046-Ad-revenue-attribution-guide#permission-to-get-ad-revenue-data)

## Report specification

### Report structure and format

- Format: Data arrives in CSV format to the UA partner's S3 bucket.
- Level: Contains device-level dimensions and metrics.
- Data enrichment: Includes ad revenue data from mediation partners, and adds attribution data relevant to the UA ad network (that is cleaned of all dimensions irrelevant to the UA ad network).
- Data freshness: [Daily, meaning data for Day 0 arrives on Day 1](https://support.appsflyer.com/hc/articles/360000310629-Data-freshness-and-time-zone-support#ad-revenue). Data is written daily at 17:00 [UTC time](https://support.appsflyer.com/hc/articles/360000310629-Data-freshness-and-time-zone-support#daily) to the h=23 of your Data Locker bucket.
- Apps included: A single report contains the data of all apps for which advertisers have granted permission.
- The reports include data about all conversion types: Installs, re-attributions, re-engagements, and reinstalls.
- Currency: In USD. Event revenue is calculated to USD on the day the event occurred.
- [See sample report](https://docs.google.com/spreadsheets/d/e/2PACX-1vSoV1U_pMUoTFhIpyYQmUI1zQWArY19c8gMmsfpRiAaGXVZEG4WqgSC26u5-fv32j8ZQN4uxtNgVkYs/pub?output=csv)

### Report fields

| **Field** | **Remarks** |
| --- | --- |
| Version | Unix timestamp in second. Example: 1661315124 |
| app\_id | App ID in the AppsFlyer platform |
| install\_time | - Timestamp of install: YYYY-MM-DD HH:MM:SS<br><br>Example: 2020-08-16 11:22:33<br>- For iOS 14+ devices and non-consenting users, or if the advertiser has Advanced Privacy on, install time is rounded to the nearest hour. |
| campaign, campaign\_id, adset\_name, adset\_id, ad\_name, ad\_name, ad\_id, site\_id | Only populated if UA is attributed to the partner receiving the data. |
| idfa, idfv, advertising\_id | - The same device ID, like IDFA, IDFV, or advertiser\_id could display in multiple rows if there are more than one ad revenue monetization events.<br>- For iOS 14+ devices and non-consenting users, or if the advertiser has Advanced Privacy on, this does not display. |
| platform | Device platform: iOS, Android, or Windows Mobile |
| country | Country code using [ISO 3166 (alpha-2)](https://www.iso.org/iso-3166-country-codes.html) Example: US, CN |
| original\_url | - For iOS 14+ devices and non-consenting users, or if the advertiser has Advanced Privacy on, this does not display.<br>- Only populated if UA is attributed to the partner receiving the data. |
| ad\_unit |  |
| placement |  |
| mediation\_network |  |
| engagement\_type |  |

Metrics:

| **Field** | **Remarks** |
| --- | --- |
| impressions | Number of times the user saw the ad |
| revenue\_usd | Daily revenue (in USD) generated for the device ID. **Note**: When the revenue amount is small, it's represented in scientific notation. For example: 8.00E-05 |
---
title: "PBA raw data reports"
excerpt: "PBA raw data reports are available via Data Locker."
x-zendesk:
  id: 360001917778
  url: https://support.appsflyer.com/hc/en-us/articles/360001917778-PBA-raw-data-reports
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  position: 13
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, Cross-Platform Measurement]
  labels: [Data Locker, People Based Attribution, Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2019-07-01T07:53:57Z'
  edited_at: '2025-08-01T11:01:02Z'
---
## PBA raw data reports

Use PBA raw data reports to analyze user journeys and actions.

### Report descriptions

PBA raw data report topics



| Raw data report topic | Description |
| --- | --- |
| [Website visits](#website-visits-and-website-events) | * Visits to the website.<br />* Measure user exposure and engagement with web traffic campaigns. |
| [Website events](/docs/pba-website-attribution-dashboard) | * Contain the actions performed by website visitors like subscribe or purchase.<br />* Events are attributed to the last non-direct web visit occurring in the previous 30 days.<br />* Attribution parameters associated with the event can include media source, media channel, campaign, and so on.<br />* Use these parameters to optimize your marketing efforts.<br />* Analyze user behavior per media source.<br />* The values for these fields are determined through the attributed visit using [PBA media source attribution rules.](/docs/pba-media-source-attribution-rules)<br />* The intent is to associate events with a specific website visit and not a specific page view.<br />* Use this to find out which sources and campaigns drive users and what actions the users perform. |



## Raw-data report fields

### Website visits and website events

#### Sample reports

* Website events: [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=1096347999&single=true&output=csv)
* Website visits: [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=432734495&single=true&output=csv)

Raw data fields are populated in part from data originating in the mobile app user attribution link and app install event.

[Download field list as CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmRBeUQS-xeiv069vIgnfBoJW8Wfl1ojv0rAK-pcOlAzNveG1lqvExVdhWfgCKIpJxczWksUiHjSa3/pub?gid=0&single=true&output=csv)

#### Field list website visits and website events report



| Field name | Description | Format | Example |
| --- | --- | --- | --- |
| advertising\_id | Advertising ID (GAID) | String | 7fzzz3fa-8bad-46c9-bb03-fffffffffffffffffffffffff |
| af\_web\_id | Cookie ID sent from the web SDK | String | 68972980-58f9-4ca6-8743-c0d633364b6d |
| amazon\_aid | Amazon Fire TV advertising ID | String | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| android\_id | Android device ID | String | 68999980-58f9-4ca6-8743-c0d633364b6d |
| app\_id | The most recent app ID installed | String | id123456789 |
| app\_name | The most recent app name | String | My App |
| app\_version | The most recent app version | String | 6.32 |
| appsflyer\_id | AppsFlyer (install) ID | String | 1594825729709-5655157112349378588 |
| attributed\_touch\_time | On web visits, the timestamp of the web visit On web events, the timestamp of the attributed web visit | yyyy-mm-dd hh:mm:ss | 9/17/2020 0:09:25 |
| attributed\_touch\_type | The type of touchpoint. Currently, always set to website visit. | String | web visit |
| bundle\_id | PBA bundle ID | String | 048db9bf-97r7-4m2f-919b-607b7kk806d0 |
| campaign | Attributed to the website visit | String | Summer Campaign |
| campaign\_id | Attributed to the website visit | String | 12343425 |
| city | Resolved using the IP address | String | Spring Valley |
| country\_code | Resolved using the IP address | String | US |
| customer\_user\_id | Customer User Identifier (CUID) | String | 5a8771ecbb986ABC |
| device\_type | The type of device | String | Desktop |
| dma | Resolved using the IP address | String | 501 |
| event\_name | In the website visit report: Always website visit. In the website event report: eventName sent by the web SDK. | String | purchase |
| event\_revenue | Event revenue amount in purchase currency | String | 199.99 |
| event\_revenue\_currency | 3 digit currency code of the event\_revenue | String | USD, ZAR, EUR |
| event\_revenue\_usd | event\_revenue converted to USD | String | 57.46 |
| event\_source | Either web SDK or Server-to-server | String | web SDK, S2S |
| event\_time | Website visits: time of visit Website event: time of event | yyyy-mm-dd hh:mm:ss | 9/17/2020 0:09:25 |
| event\_type | The following: Standard event, conversion event, website visit | String | conversion event |
| event\_url | URL of the webpage where event occurred (Equals Original URL in website visits) | String | http://www.brandpit.com/checkout |
| event\_value | Website events: Event value details contained in a JSON. Website visits: Always null | JSON | `{"sku": "ABC123", “color": "blue", "unit_price":3.99,"currency": "USD"}` |
| idfa | Advertising identifier | String | A56B9887-FEBA-458C-BEFC-C891F9DF7681 |
| idfv | Advertising identifier | String | EBC2F523-B1E5-4484-A4C8-ADC32DC7C23D |
| imei | Device identifier | String | 3532211234 |
| install\_time | The most recent app install time | yyyy-mm-dd hh:mm:ss | 9/17/2020 0:09:25 |
| ip | Visitor IP address | String | 24.7.104.115 |
| language | Reported by user agent | String | English |
| media\_channel | Attribtued to the website visit | String | Ad |
| media\_source | Attribtued to the website visit | String | googleadwords\_int |
| media\_type | Attribtued to the website visit | String | Paid |
| oaid | Advertising identifier | String | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| original\_url | URL address redirecting the user to the website on the attributed website visit | String | https://www.brandpitt.com/signin?utm\_source=Googleg&utm\_term=shoes&utm\_campaign=cool&c=summer⁡\_siteid=publisher⁡\_sub1=helloworld |
| platform | The platform | String | macOS |
| postal\_code | Resolved using the IP address | String | 10977 |
| query\_params | Query params on the redirecting URL (after the ?) Example: https://www.brandpitt.com/signin?utm\_source=Google&utm\_term=shoes&utm\_campaign=cool&c=summer⁡\_siteid=publisher⁡\_sub1=helloworld⁡\_keyword=shoes If URL has no query params, the value will be null | JSON | `{"c":"summer",af_siteid":"publisher",af_sub1":helloworld",af_keywords":"shoes","utm_source":"Google","utm_campaign":"cool","utm_term":"shoes"}` |
| referrer | HTTP document referrer of the attributed website visit | String | https://www.google.com/ |
| region | Resolved using the IP address | String | NA |
| state | Resolved using the IP address | String | NY |



### Field release notes



| Date | Report | Change |
| --- | --- | --- |
| 2020-11-18 | Website events<br /><br />Website visits | The report names and structure are changed:<br /><br />* Web touchpoints replaced by **Website visits**<br />* Web events replaced by **Website events** |
| 2020-10-04 | Web-to-app | Fields added:<br /><br />* mobile\_campaign\_id<br />* web\_campaign\_id |



### Procedures

### Setting up PBA reports in Data Locker

* PBA reports are written Daily to the Data Locker in h=23 folder for events occurring on a given day.
* Data can't be written retroactively.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/23a82846b437ddc93e848a70648a9c217777d43162c5ac6a5ff3fd9c586578c1-21591689590161.png) To enable PBA reports an account admin must set up Data Locker:**

1. In AppsFlyer, from the side menu, select **Report** > **Data Locker**.
2. Select all the reports in the People-Based Attribution section.
3. Click **Save configuration**.

**To download reports, see** [**accessing Data Locker reports**](/docs/data-locker-for-marketers)**.**

**Data Locker** PBA raw data reports are made available in the h=23 folder.

Example: t=website\_events/dt=2020-11-26/h=23

### Combining PBA and mobile data

The data reflects the users most likely to engage with both your mobile app and website.

Combine mobile app and website data.

**Solution:**

* Combine reports using [customer user ID](/docs/customer-user-id-field-cuid) (CUID)
  * Use the same CUID for both mobile and [web](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid) and combine reports using CUID as the key.
  * Then, combine reports using the CUID field
* PBA cross-platform user identification:
  * PBA can determine that a web and a mobile user are the same person.
  * If so, then web reports with PBA include a mobile advertising ID: Android advertising ID, iOS IDFA, OAID, or Amazon advertising ID, as well as `appsflyer_id` and `app_name`.
  * Then, combine mobile and web reports based on mobile advertising ID.

#### **Use cases for PBA and mobile**

Combine mobile and web data to see user activity across platforms and devices. The combined data lets you:

* Follow the user journey across your brand's digital properties
* Analyze user behavior in each platform
* Consider which platform shows more user engagement
* See which platform produces more conversions
* Measure your efforts at switching users from web to mobile

### Application note - downloading and combining Data Locker files

PBA raw data is available in Data Locker. For a given report, the data is contained in the h=23 folder of report type and consists of multiple compressed files.

Use this procedure to:

* Copy the files from Data Locker using Cyber-Duck or any other tool for copying S3 files.
* Combine the files into a single CSV file using [Q.](http://harelba.github.io/q/)

**Copying PBA data from Data Locker**

**Before you begin**:

* [Install and set up Cyber-Duck.](/docs/data-locker-for-marketers#cyberduck)

**To copy data using Cyber Duck:**

1. Open Cyberduck  
   The list of data types available displays.

   ![Duck_us-en.jpg](https://files.readme.io/b8e93ad9423605b3247531d276b9c2d45abd4ea044dde29ee177f4d71b738e9d-360008254377.jpg)
2. **Double-click** on a PBA report type and choose from web\_events, web\_to\_app, or web\_touch\_points.  
   The list of report dates available displays.
3. **Right-click** on a given date.
4. Select **Download to a specific location and complete the location.**  
   The files download.
5. Repeat the above steps to copy data from other report types. Each report type and date must be stored in a different directory on your computer.

**Creating a combined CSV file:**

**Before you begin:**

Install [Q](http://harelba.github.io/q/) on your computer.

**To combine the data in a CSV file using Q**:

1. Using the command line/maс terminal, go to the directory containing the data.
2. Use the command that follows to combine the compressed files into a single file having the name pbadata.csv.  
   Note: The symbol ~ represents the path/home folder where the Q command is located on your computer. You may need to include the full path to invoke the command.

   ```
   ~q "SELECT * from part*.gz" -d , -H -z -O >pbadata.csv
   ```
3. Open the file using Excel or any other tool
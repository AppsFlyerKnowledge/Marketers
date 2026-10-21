---
title: Protect360 anti-fraud guide
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - p360
    - p 360
    - 360protect
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2016-12-06T07:47:17Z'
  edited_at: '2025-09-17T10:12:30Z'
  id: 218254203
  locale: en-us
  section: Protect your traffic
  section_id: 6551015912465
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/218254203-Protect360-anti-fraud-guide
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**At a glance:** Attribution fraud drains marketing budgets, pollutes marketing performance data, and can turn successful campaigns into losing ones. **Protect360 provides app owners with real-time fraud protection and post-attribution detection.**

![p360intro2.jpg](https://files.readme.io/c8476382eeff62164ca93b9bf2f3c4cdbe0609d4160047eac36a44d5f333ffdb-360014803578.jpg)

## Protect360 overview

* Protects against attribution fraud. It consists of dynamic tools that detect fraud and block fraudulent attribution.
* Uses AppsFlyer scale, machine learning, and behavioral analysis to provide cover against known and new forms of click/install fraud including bots and behavioral anomalies.
* Guards marketers from fraud at the device, publisher, and media source levels.
* Uses a layered approach of real-time fraud blocking and post-attribution fraud identification
* Does not impact the app user experience. In case of fraud attempts involving real users, app installs complete normally, and only attribution recording is affected.

<div id="realtime-blocking" />

<Accordion title="Real-time blocking">

* In real-time, before attribution, the install is identified as coming from a fraudulent media source and is blocked from attribution.
* Subsequent in-app events from the same user are blocked.
* Blocked installs and in-app events are reported in the Protect360 dashboard and blocked fraud reports.
  * Blocked installs and in-app events: Are not included in AppsFlyer attribution and dashboards because they were never attributed.
* Blocked install postbacks are sent to media sources, with the blocking reason, enabling them to optimize.

<Anchor target="_blank" href="/marketers/docs/protect360-raw-data-reports">About blocked events</Anchor>

</Accordion>

<div id="postattribution-detection" />

<Accordion title="Post-attribution detection">

* Fraud identified after attribution is referred to as post-attribution fraud. Post-attribution fraud can be identified on the day of the install, and up to 7 days after (8 days total).
* Once attributed, an install can't be erased. For this reason, post-attribution fraud is handled differently to that of real-time fraud.
* Fraudulent installs and in-app events identified in retrospect must be treated as real fraud and not charged for.

Once a source, like an ad network or site ID, is identified as fraudulent:

* Future clicks from the source are blocked.
* Past installs:
  * From the start of the current calendar month until the present, are labeled as post-attribution fraud, but **not erased from data**. As of January 2020, advertiser invoices are credited for the attribution fees of these installs.
  * From before the start of the current month, are not changed.
* In-app events occurring:

  * **Up until** the install labeling: labeled as fraud.
  * **After** the install labeling: labeled as fraud.

  Note: For user acquisition (UA) reinstalls identified as fraudulent, Protect360 corrects the attribution by reassigning the install to an Organic source. Consequently, any subsequent in-app events from these reinstalls are attributed to Organic and will appear in the Organic in-app events reports.

Examples of post-attribution fraud:

* Seemingly regular installs followed by fraudulent signals within in-app events
* A new form of fraud found
* Installs which turn out to be fraudulent only after anomaly detection algorithms collect enough statistical data about the installs of any publisher

</Accordion>

<div id="common-fraud-issues-and-solutions" />

<Accordion title="Common fraud issues and solutions">

When AppsFlyer identifies fraud, **the attribution** **event** associated with the fraud is blocked. This eliminates fraudster gains and motivation. **Note**: The app install itself takes place and is not blocked. This means the app user can use the app and generate revenue for the advertiser.

Blocked fraud clicks, installs, and in-app events are found in <Anchor target="_blank" href="/marketers/docs/protect360-raw-data-reports">Protect360 fraud raw data reports</Anchor>.

The following table describes some fraud types and how Protect360 handles them.

| Fraud type | Description | AppsFlyer solution |
| --- | --- | --- |
| <span id="device-id-reset-fraud"></span>**Device ID reset fraud** | Device ID is constantly reset by the fraudster on the same physical device, so as to generate a large number of installs. | AppsFlyer identifies abnormal rates of new devices and consequently denylists sources delivering them. |
| <span id="install-hijacking"></span>**Install hijacking** | Fraudsters plant malware on mobile devices that alerts when a download of an app takes place. Instantly a click is sent to AppsFlyer claiming credit for the install. | Blocks attributed clicks with a very quick CTIT (<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-to-install-time-ctit/">Click To Install Time</Anchor>) and based on Google Play Server-Side API. |
| <span id="click-hijacking"></span><Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-hijacking/">**Click hijacking**</Anchor> | Malware identifies an install attribution link click and instantly sends another click that credits them if it is attributed. | Blocks attributed clicks occurring very fast after other clicks for the same app on the same device. |
| <span id="click-flooding"></span><Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-flooding/">**Click flooding**</Anchor> | Mobile fraud where large numbers of fraudulent clicks are sent, with the purpose of delivering the last-click prior to installs. | Blocks attributed clicks from site IDs with a low conversion rate and long CTIT. |
| <span id="behavioral-anomalies"></span>**Behavioral anomalies** | Mobile fraud where the fraudster generates an inconsistent and abnormal post-install activity. | Our unique scale allows us to track and understand behavioral engagement patterns on multiple levels - such as by app, region, media source, and publisher. Non-human behavioral patterns are identified in near real-time and blocked at the source. |
| <span id="ip-denylists"></span>**IP denylists** | Fraudsters usually operate from <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-farms/">click farms</Anchor>, which may be identified by their IP addresses for long periods of time. | <ul><li>IP addresses suspected of fraud are denylisted on a daily basis based on up to date data received from third party global provider <Anchor target="_blank" href="http://www.digitalelement.com/">Digital Element</Anchor>.</li><li>IP denylist protection is enabled for all apps.</li></ul> |
| <span id="sdk-authentication"></span>**SDK authentication** | Fraudsters send fake SDK messages to simulate valuable user actions. | <ul><li>A proprietary hashing protocol is used to encrypt messages between SDKs and web services, preventing fraudsters from mimicking the messages.</li><li>SDK authentication protection is enabled for all apps.</li></ul> |
| <span id="store-validations"></span>**Store validations** | Fraudsters send fake SDK messages to simulate installs or in-app purchases so they can claim high CPA fees. <Anchor target="_blank" href="/marketers/docs/implement-apple-app-store-itunes-install-validation">Apple store validations</Anchor>. | Enables <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/install-validation/">install validation</Anchor> on iTunes and in-app purchase validation for both iTunes and Google Play, of any install or in-app purchase that has taken place to prevent attribution of fraudulent activities. |

**Note**: The exact time values cited above, are withheld to protect our clients.

Additional blocking reasons are explained in the <Anchor target="_blank" href="/marketers/docs/protect360-raw-data-reports">raw data article</Anchor>.

</Accordion>

The table below outlines the various types of fraudulent installs and in-app events, and what happens when the Protect360 engine blocks them in real-time, or detects them post-attribution.

<table><thead><tr><th>Fraud type</th><th>Detection time</th><th>What happens to install</th><th>What happens to in-app event</th></tr></thead><tbody><tr><td rowspan="2"><span>Fake install</span></td><td><span>Real-time</span></td><td><span>Blocked in real-time</span></td><td><span>Blocked in real-time</span></td></tr><tr><td><span>Post-attribution</span></td><td><span>Marked in the Post-Attribution Installs report</span></td><td><ul><li><span>In-app events that occurred before fraud detection, will be marked in the Post-Attribution In-App Events report.</span></li><li><span>After detection: blocked in real-time</span></li></ul></td></tr><tr><td rowspan="2"><span>Install attribution hijacking</span></td><td><span>Real-time</span></td><td><ul><li><span>Blocked in real-time</span></li><li><span>Attribution is corrected to the last valid source</span></li></ul></td><td><ul><li><span>Is not shown in raw reports and is only visible on the dashboard</span></li><li><span>Attributed to the same valid source as the install</span></li></ul></td></tr><tr><td><span>Post-attribution</span></td><td><span>Marked in the Post-Attribution Installs report</span></td><td><ul><li><span>In-app events that occurred before fraud detection, will be marked in the Post-Attribution In-App Events report.</span></li><li><p>After fraud detection: marked in the Post-Attribution In-App Events report up to 30 days from the install.\*</p><p>\*In-app events are corrected to the last valid media source for 30 days from the install. Events occurring after 30 days are not corrected.</p></li></ul></td></tr><tr><td rowspan="2"><span>Fraudulent in-app event</span></td><td><span>Real-time</span></td><td>-</td><td><span>Blocked in real-time</span></td></tr><tr><td><span>Post-attribution</span></td><td>-</td><td><span>Marked in the Post-Attribution In-App Events report</span></td></tr></tbody></table>

Protect360 fraud detection and outcomes

## Using Protect360

<div id="dashboard" />

<Accordion title="Dashboard">

The <Anchor target="_blank" href="/marketers/docs/protect360-dashboard">Protect360 dashboard</Anchor> displays aggregate fraud data and provides insights relating to fraudulent traffic.

Dashboard views:

**Installs**: <Anchor target="_blank" href="/marketers/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV-based</Anchor> insights about fraudulent installs, blocked in real-time, and identified post-attribution. You can drill down to further examine the fraud events by using the filtering and grouping options.

**In-app events**: <Anchor target="_blank" href="/marketers/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Activity-based</Anchor> insights about fraudulent in-app events, blocked in real-time, and identified post-attribution. You can drill down to further examine the fraud events by using the filtering and grouping options.

</Accordion>

<div id="raw-data" />

<Accordion title="Raw data">

<Anchor target="_blank" href="/marketers/docs/protect360-raw-data-reports">Raw data</Anchor> about fraud is available via Pull API, Export Data, and <Anchor target="_blank" href="/marketers/docs/data-locker-for-marketers">Data Locker (a premium feature)</Anchor>.

Raw data reports are divided as follows:

* Blocked reports: Installs, clicks, and in-app events of users whose attribution was blocked and not attributed to any media source at all.
* Post-attribution reports:
  * Installs attributed to a media source, but later found to be fraudulent.
  * In-app events:
    * of installs identified as fraud after being attributed to a media source.
    * judged to be fraudulent without regard to the install itself.

* Advertisers use these reports to reconcile ad network accounts, for optimization, and to adjust attribution dashboards for post-attribution fraud.

</Accordion>

<div id="validation-rules" />

<Accordion title="Validation rules">

<Anchor target="_blank" href="/marketers/docs/implement-validation-rules-to-prevent-fraud">Validation Rules</Anchor> enable app owners to set conditions to block certain installs, block attribution (and ensure that installs are attributed to the most recent valid media source), or block in-app events.

</Accordion>

<div id="fraud-reconciliation-with-ad-networks" />

<Accordion title="Fraud reconciliation with ad networks">

With Protect360, advertisers get raw data regarding fraudulent installs and in-app events that ad networks may not have recorded as fraud.

If you discover that an ad network has been sending you traffic from suspicious sources, notify the ad network and ask them to stop sending you traffic from those suspicious sources. Use the raw data installs report column called **Attributed Touch Time** to verify that no more installs are received from the source after your request to stop it.

You can also use Protect360 data to reconcile with ad networks and receive full or partial refunds for past traffic from suspicious sources.

**To reconcile CPI-based campaigns using Protect360:**

* At the start of each month contact the account manager in each ad network where fraud occurred.
* Collect the relevant fraudulent installs raw data from the Blocked installs and [post-attribution installs](/docs/protect360-anti-fraud-guide#postattribution-detection) reports.
* Share the fraud raw data with the network for reconciliation and optimization of their traffic.
* It's possible to create a raw data report which includes just the valid installs, but excludes post-attribution fraudulent installs. To do this, you need to download the monthly ***Attributed UA installs*** report and exclude all entries from the ***Post-attribution installs*** report.

**To reconcile CPA/CPE-based campaigns using Protect360:**

* At the start of each month contact the account manager in each ad network where fraud occurred.
* Collect the relevant fraudulent in-app events raw data from the Blocked in-app events and [Post-attribution](/docs/protect360-anti-fraud-guide#postattribution-detection) In-app events reports.
* Share the fraud raw-data with the network for reconciliation and optimization of their traffic.
* It's possible to create a raw data report which includes just the valid IAEs, but excludes post-attribution fraudulent events. To do this, you need to download the monthly ***Attributed UA in-app events*** report and exclude all entries from the ***Post-attribution in-app events*** report.

</Accordion>

## Traits and limitations

<div id="traits-and-limitations::a07033c3" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Advertiser access | All account users. |
| Ad network access | <ul><li>Protect360 dashboard and raw data access require <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#ad-network-permissions">advertiser permission.</Anchor></li><li>Advertiser must have the ad network as an integrated partner.</li></ul> |
| Agency access | Protect360 dashboard and raw data access require <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#ad-network-permissions">advertiser permission.</Anchor> |
| Agency transparency | Transparent agency: Can see specific media sources<br /><br />Non-transparent agency: Cannot see specific media sources |
| App-specific time zone | <ul><li>App-specific time zone is used in the dashboard, provided all apps are set to the same time zone.</li><li>If apps are not set to the same time zone, then the dashboard defaults to UTC.</li></ul> |
| Data freshness | <ul><li>Protect360 dashboard: Updated <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#eod">Daily</Anchor>.<br />The most recent update time displays below the date range filter in the Dashboard.</li><li>Reports:<ul><li>Blocked installs and in-app events: Update continuously in near real-time.</li><li>Post-attribution: <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#eod">Daily</Anchor> using UTC.</li></ul></li></ul> |
| Re-installs | Fraud data for re-installs is only available in raw data. Therefore, there may be discrepancies between the overall numbers in the dashboard and raw data reports. |
| Retargeting | <ul><li>For installs identified as fraud, the attributed touch-type breakdown between installs, re-attributions, and re-engagements is displayed.</li><li>For in-app events:<ul><li>The in-app event (CPA) dashboard displays fraudulent events from UA installs, but not from retargeting.</li><li>Fraudulent events from re-attributions that are identified in real-time, can be viewed in raw data reports. Fraudulent events from re-engagements can't be identified.</li><li>Fraudulent events from retargeting can't be identified post-attribution.</li></ul></li></ul> |
| Limitations | <ul><li>Tables limited to maximum 20,000 rows.</li><li>If you query for a larger data set, some media sources might be excluded. To overcome this limitation, we recommend the following:<ul><li>Query for a smaller dataset - smaller date range, specific apps, and specific media sources</li><li>Export Protect360 <Anchor target="_blank" href="/marketers/docs/protect360-raw-data-reports">raw data reports</Anchor></li><li>Export Protect360 Aggregated Advanced Detection Reports <Anchor target="_blank" href="/marketers/docs/pull-api-aggregate-data">through Pull API</Anchor></li></ul></li></ul> |

Traits and limitations

</Accordion>

## FAQ and tips

<div id="faq" />

<Accordion title="FAQ">

| **Does Protect360 work against fraud coming from custom attribution links?**<br /><br />Definitely! Protect360 detects and blocks fraud coming from custom attribution links, in addition to ad networks. That means you are also protected if you have campaigns of owned media, such as with influencers, email and SMS campaigns, website banners and landing pages, viral posts on social media, Push notifications, or even QR codes. |
| --- |
| **What's new in Protect360 V2 compared with V1?**<ol><li>There are 3 main changes in the P360 V2.0:<br />Post-Attribution fraud - wherever we present blocked installs, we also show Post-Attribution fraud installs. Post-Attribution is also available as a raw data report.</li><li>Anomaly Insights - A new section called “Anomaly Insights” was added, in which advertisers can analyze anomalies via visualization tools. It's replacing the 2 charts on the old “Advanced Detection” tab.</li><li>Centralization of all the fraud data - the “advanced detection” tab was removed and instead we present all the information in 1 tab.</li></ol> |
| **Why isn't the post-attribution raw data available in the Export Data page?**<br /><br />Post-attribution reports are on the account level per media source, in order to make the reconciliation process easier. The **Export Data** page is on the single app level, and still contains the Blocked fraud data on the app level for backward compatibility. |
| **Does post-attribution data update retroactively?**<ul><li>**Installs** - install data on the overview page and all other reports outside Protect360 dashboard does not update retroactively.</li><li>**In-app events** - once the post-attribution protection layer identifies an install as fake, following in-app events coming from this install are being blocked. Previous in-app events do not update retroactively.</li></ul> |
| **Why does the data look different when selecting specific/different networks in Anomaly insights?**<br /><br />When you look at CTIT anomalies and select AF\_Baseline as a benchmark, you may see Network A's anomalies. Then, if, for example, you select Network A as a benchmark, you will see other networks' anomalies, but not Network A.<br /><br />This outcome is actually what you should expect. When the trusted AppsFlyer baseline is used, networks with abnormal rates of CTIT display. When the anomalous network is used as the baseline, its installs aren't included as anomalies anymore, but installs from other networks may be considered anomalous relative to it. |
| **Is abnormal organic traffic actually fraudulent?**<br /><br />It's possible that abnormal spikes in organic traffic are actually fraudulent. In general, if you see organic traffic in AppsFlyer, which you have reasons to believe is actually fraudulent, it could be one of the 3 following cases:<ul><li>**Failed attribution fraud:** Fraudster's clicks failed to receive attribution, e.g., click flooding with the last click taking place beyond the click lookback window.</li><li>**Non-attribution fraud:** User performs fraud, that is not related to attribution, e.g. using fraud to collect items in strategy games.</li><li>**SDK integration issues:** Check that your in-app events are sent correctly, i.e. at the right time in the flow and with correct event parameter values.</li></ul> |

FAQ

</Accordion>

<div id="benchmarks-and-tips" />

<Accordion title="Benchmarks and tips">

| **Detecting new devices fraud**<br /><br />Fraudsters may mask their devices by frequently resetting the main IDs of their devices, i.e. IDFA for iOS and GAID for Android.<br /><br />Fortunately, AppsFlyer identifies over 98% of mobile devices globally.<br /><br />Therefore, a high percentage of unknown new devices is a strong indication of fraud by click farms, unless intentionally targeting new devices.<br /><br />**Detecting new devices:**<ol><li>In Protect360 go to the ***Identified fraud breakdown*** table.</li><li>Scroll right to the ***Device farm indicators - new devices*** columns.</li><li>Click on the ***Installs %*** column name to sort the table in descending order of new device ratio.</li><li>New device fraud indicators:</li></ol><ul><li>Sources with a high percentage of **new** devices. **Note**: As the number of installs rises, lower percentages can also be considered as fraud (since the overall amount is large).<ul><li>When the source loyal user ratio is compared with the overall loyal user ratio, a relatively low percentage is a strong indication of fraud.</li></ul></li></ul>**Note**: Campaigns of <Anchor target="_blank" href="/marketers/docs/appsflyer-factory-preinstall-using-manifest-android">pre-installed apps</Anchor> usually have extremely high rates of new devices, as these may be among the very first apps that users launch when activating their new devices. Therefore, for pre-installed apps, new device fraud is unlikely, even with high new devices rates. |
| --- |
| **Detecting LAT fraud**<br /><br />LAT (Limited Ad Tracking) users select to opt-out of exposing their device ID, IDFA or GAID, to advertisers. Approximately 15% of iOS users and 10% of Android users take this choice.<br /><br />Similar to the new device ranking, LAT users may be legitimate users. However, a high percentage of them could indicate fraudulent activity.<br /><br />**Detecting LAT:**<ol><li>In Protect360 go to the ***Identified fraud breakdown*** table.</li><li>Scroll right to the ***Device farm indicators - LAT devices*** columns.</li><li>Click on the ***Installs %*** column name to sort the table in descending order of LAT device ratio.</li><li>LAT devices fraud indicators:</li></ol><ul><li>Sources with a high percentage of **LAT** devices. **Note**: As the number of installs rises, lower percentages can also be considered as fraud (since the overall amount is large).</li><li>When the source loyal user ratio is compared with the overall loyal user ratio, a relatively low percentage is a strong indication of fraud.</li></ul> |
| **Detecting click flooding fraud**<ol><li>Using click flooding, fraudsters send millions of clicks with real device IDs, hoping to register as the last click for real users. Sources with this type of fraud have **very low conversion rates, but high-quality users**, since these are real users.</li></ol>**Detecting click flooding:**<ol><li>In Protect360 go to the ***Identified fraud breakdown*** table.</li><li>Scroll right to the ***Click flooding indicators*** columns.</li><li>Click on the ***Conversion rate*** column name to sort the table in ascending order of conversion rate.</li><li>Click flooding fraud benchmarks:</li></ol><ul><li>Normal ***Conversion Rates*** are between 0.5% to 35%.<br />Suspect sources whose conversion rates are abnormally low, or that **have 25% or less of the average conversion rate** of the app. You can find this KPI in the Aggregated performance report table in the dashboard overview page.</li><li>For borderline sources, compare the ***Assists %*** with the average assists ratio. You can see the normal assists ratio in the assists widget, in the dashboard overview page.<br />Sources whose assists ratio is **50% higher than the average** assists ratio of the app are considered suspicious.<br />Note that the more sources are used by an app, the higher are its Contribution rates.</li></ul> |
| **Detecting click flooding with CTIT indicators**<br /><br />Another indication of click flooding is the **even distribution of CTIT**.<br />Usually, around 70% of normal installs take place within 1 hour of the ad engagement.<br />With click flooding, there's no connection between the fake engagement and the actual install. This leads to much more than 30% of fraud installs, which have longer than a 1 hour CTIT.<br /><br />**Detecting click flooding CTIT indications:**<ol><li>In Protect360 go to the ***Identified fraud breakdown*** table.</li><li>Scroll right to the ***Click flooding indicators*** ***- CTIT*** columns.</li><li>Click flooding CTIT benchmarks:</li></ol><ul><li>Normally, ***Over 60 minutes*** values should be around 30%. Suspect sources who have more than 50% with this metric.</li><li>Normally, ***Over 5 hours*** values should be around 20%. Suspect sources who have more than 40% with this metric.</li></ul>Use the ***Anomaly insights*** <Anchor target="_blank" href="/marketers/docs/protect360-dashboard#anomalies-dashboard">page</Anchor> to investigate sources with suspicious CTIT. |

Benchmarks and tips

</Accordion>

<div id="advanced-antifraud-tips" />

<Accordion title="Advanced anti-fraud tips">

| **Number of installs**<br /><br />Filtering by the number of installs per checked source is important for detecting the biggest fraud sources. Additionally, a lower number of installs may not be mathematically significant. Note:<br /><br />**Note**: Sources with less than 30 installs, or even 50, are not significant enough to draw conclusions from. Expand the date range or other search criteria to get more significant results. |
| --- |
| **Change loyal user definition**<br /><br />The default definition for Loyal users is 3 or more launches of the app. It is an important KPI for user engagement, but unfortunately, many fraudsters know it and use it to fake high rates of loyal users, thus avoiding suspicion. Avoid being conned by creating and selecting a better, more elaborate loyal user definition.<br /><br />Analyze your app user quality KPIs such as register, tutorial completion, purchase, multiple sessions. Within the app code send a new **loyal user** in-app event if a user performs ALL the list of KPIs.<br /><br />After the first non-organic **loyal user** event is sent, go to **App Settings** and select it to indicate loyal users for your app. Expect general loyal user rates to slightly drop and then drastically drop for fraudulent sources. |

Advanced anti-fraud tips

</Accordion>

> 👍 **Tip**
>
> Want to understand more about protection from fraud? Check out this short, informative <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7809/play/18635/mobile-app-fraud-and-protect360">course on the AppsFlyer Learning Portal</Anchor>.

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/protect360-raw-data-reports">Raw data</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/marketers-guide-mobile-ad-fraud/">Introductory guide for marketers to mobile ad fraud</Anchor>

<div data-zendesk-anchors="h_01HE7RSPPQ4T5J3W038EZRCTCE=protect360-overview h_01HE7RSPPQ5BH7HBK0R8SY1T16=realtime-blocking h_01HE7RSPPRW4CQ3GB9ZEYAA6YN=postattribution-detection h_01HE7RSPPRYMQKJH46JET2ZZ0T=common-fraud-issues-and-solutions h_01HE7RSPPR8Y8J1VJJXXDCAZE6=using-protect360 h_01HE7RSPPR04G3SCSYHSWJKQDG=dashboard h_01HE7RSPPRS6PSTZCR5RT4A5ND=raw-data h_01HE7RSPPR8C9MHRAGJXYD2VVZ=validation-rules h_01HE7RSPPR1PQ2R6NJPRQGS1K1=fraud-reconciliation-with-ad-networks h_01HE7RSPPRV797PS12NFQHX1X5=traits-and-limitations h_01HE7RSPPRWRKR1Y25PZV2RMVV=traits-and-limitations::a07033c3 h_01HE7RSPPSV2TT8SMK8JZXFKMC=faq-and-tips h_01HE7RSPPS01J796008HDS1CRW=faq h_01HE7RSPPS018W98JWZGED54W8=benchmarks-and-tips h_01HE7RSPPSEDZWRH929DBSWEWM=advanced-antifraud-tips h_01HE7RSPPSY161MSQVQW7M767F=tip h_01HE7RX6167Q5QP5JNZDSXCCK5=see-also" />

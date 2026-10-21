---
title: Protect360 raw data reports
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - Raw Data
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-09T13:03:45Z'
  edited_at: '2026-03-28T14:03:09Z'
  id: 360015179337
  locale: en-us
  section: Protect your traffic
  section_id: 6551015912465
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360015179337-Protect360-raw-data-reports
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**At a glance:** Raw data reports describe installs and in-app events blocked by the Protect360 engine, as well as from manually added Validation Rules.

## About Protect360 raw data reports

Raw data reports:

* Display data about:
  * Clicks, installs, and in-app events identified as fraudulent by the Protect360 engine.
  * Installs and in-app events identified via Validation Rules.
* Include the block reason for each click, install, or in-app event.
* Are used by advertisers to reconcile ad network accounts, for optimization, and to adjust attribution dashboards for post-attribution fraud.
* May have <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions">some fields are restricted or not available</Anchor> if <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">AppsFlyer Aggregated Advanced Privacy (AAP)</Anchor>.
* Report types and their availability by download, API, and Data Locker (S3 bucket) are described in the sections that follow.
* Historical raw data report retention is up to 90 days, depending on the reporting tool and origin of the raw data.

> 📘 **Note**
>
> Due to raw data restrictions related to privacy, the raw reports may show fields with empty values. An example of this is the contributor fields.

<div id="report-types" />

<Accordion title="Report types">

#### Protect360 raw-data report types

| Report | Description |
| --- | --- |
| <span id="installs"></span>Installs | Reports include:<ul><li>**Fake installs**: Installs identified as fraudulent by the Protect360 engine. These do not appear in any AppsFlyer dashboard or raw data, except for the Protect360 dashboard and raw data.</li><li>**Hijacked installs**: Real user installs where attribution is stolen, but Protect360 [corrects the attribution](/docs/protect360-raw-data-reports#hijacked-installs-attribution-correction).</li><li>**Validation Rules**: That either blocked the install or blocked the attribution (Protect360 [corrects the attribution](/docs/protect360-raw-data-reports#hijacked-installs-attribution-correction)).</li></ul> |
| <span id="postattribution-installs"></span>Post-attribution installs | Reports include installs attributed to a media source, but later found to be fraudulent. Protect360 [corrects the attribution](/docs/protect360-raw-data-reports#hijacked-installs-attribution-correction). |
| <span id="blocked-inapp-events"></span>Blocked in-app events | Reports include in-app events from:<ul><li>**Fake installs**: IAEs are blocked.</li><li>**In-app events**: Identified as fraudulent independent of the original installs.</li><li>**Validation Rules**:<ul><li>IAEs from a rule that blocked the install or blocked attribution.</li><li>IAEs from a rule that blocked the in-app event.</li></ul></li></ul> |
| <span id="postattribution-inapp-events"></span>Post-attribution in-app events | Reports include in-app events:<ul><li>Identified post-attribution.</li><li>Of installs attributed to a media source, but later found to be fraudulent.</li></ul> |
| <span id="clicks"></span>Clicks | Reports include blocked clicks with the block reasons. |
| <span id="blocked-install-postbacks"></span>Blocked install postbacks | Reports include copies of the rejection postbacks sent to media sources bringing blocked installs. |

</Accordion>

<div id="postattribution-reports" />

<Accordion title="Post-attribution reports">

* Post-attribution raw data fraud reports have the same structure as the blocked fraud reports.
* The current month (by install date) post-attribution report continues to be updated until the seventh day of the following month (detection date).
* Post attribution raw data reports are limited to advertisers. Agencies need <Anchor target="_blank" href="/partners/docs/protect360-for-integrated-partners">permissions</Anchor> enabled to access.
* Reports contain post-attribution fraud events identified by Protect360 and include all media sources in a single report. **Note**: If no post attribution fraud events are identified for the selected date range, the report returns empty,
* Post-attribution raw data fraud reports are available as follows:
  * Dashboard user interface: limited to one media source during one calendar month.
  * Pull API: contains all media sources. (Limitation: Available to app owners only.)

#### **Using post-attribution reports**

* Select any combination of install/IAE and detect date ranges as needed.
* Take into consideration that Protect360 performs post-attribution detection during the calendar month of the install and up to the seventh day of the following month. This means, for example, that for installs in November, Protect360 checks for fraud up to December 7.
* The best practice for using this Pull API is as follows:
  * Assume you pull the report on a daily basis.
  * Set the install date range to 60 days looking back from the current day.
  * Set the detect-from/detect-to range to the day before the current day.  
    This means you will get the list of post-attribution frauds detected yesterday. If you didn't pull the report for a few days, adjust the detect date range, and pull the report.

> 📄 **Example**
>
> **Example A**: During December (install date) 15 installs are attributed to example\_media. On January 3 (detection date), Protect360 identifies example\_media as a fraudster. As a result, the 15 installs attributed to example\_media are listed as fraudulent in the post-attribution fraud report for further action by the app owner.
>
> **Example B**: During December, 15 installs are attributed to example\_media. On January 9, Protect360 identifies example\_media as a fraudster. In this case, no action is taken by Protect360 because the fraudster was identified after the month close on January 7.

</Accordion>

<div id="raw-data-availability-by-tool-type" />

<Accordion title="Raw data availability by tool type">

#### Protect360 raw-data availability by tool type

<table><thead><tr><th>Report</th><th>Data freshness</th><th>Pull API</th><th>Export Data page</th><th>Data Locker</th></tr></thead><tbody><tr><td>Installs</td><td>Real-time</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Blocked in-app events</td><td>Real-time</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Clicks</td><td>Real-time</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Blocked install postbacks</td><td>Real-time</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Post-attribution installs</td><td>Daily 15:00 UTC</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Post-attribution in-app events</td><td>Daily 20:00 UTC</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="5"><p>\* Limitations to report via Data Locker:</p><ul><li>Agency transparency not supported. Meaning that agency-driven traffic does not contain the name of the media source sending the install.</li><li>The report has a unique set of fields relative to other Data Locker reports. This list can't be changed.</li><li>Retargeting data is not available in the Installs report; only in the Post-attribution installs report. </li></ul></td></tr></tbody></table>

</Accordion>

## Getting raw data reports

Raw data reports are available by download, Pull API, and Data Locker (S3 bucket). You can also <Anchor target="_blank" href="/partners/docs/protect360-for-integrated-partners">give partners access to reports</Anchor>.

<div id="download" />

<Accordion title="Download">

**To download:**

1. In the Protect360 dashboard, go to **Raw data reports** > **Blocked** or **Post-attribution.**
   * For post-attribution reports, select the media source and month.
2. Select the **Protect360 & Validation Rules** report to download.

**OR**

1. In the AppsFlyer dashboard, go to **Export Data**.
2. Select the **Protect360 & Validation Rules** report to download.

**Note**: Reports downloaded from the Export Data page contain all media sources.

</Accordion>

<div id="pull-api" />

<Accordion title="Pull API">

**To download raw data reports available by Pull API:**

**Before you begin:**

You need a Pull API token. Get the token from an <Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens">admin user</Anchor>.

1. Go to **Report > API Access.** The <Anchor target="_blank" href="/marketers/docs/pull-api-raw-data">Pull API</Anchor> page opens.
2. In the Protect360 fraud reports section, select the necessary Pull API call.
3. Populate the parameters as required. The table that follows lists the parameters.
4. Pull the report.

#### Pull API raw data report parameters

| Parameter | Description | Format | Mandatory |
| --- | --- | --- | --- |
| app\_id | App ID as it appears in AppsFlyer | String | Yes |
| api\_token | Retrieve the key from the Dashboard. Go to **Report** > **API Access.** Only an admin user can retrieve the API token. | String | Yes |
| from | Start of the date range:<ul><li>For installs, this is the install date.</li><li>For in-app events, this is the date of the event.</li></ul> | YYYY-MM-DD | Yes |
| to | End of the date range:<ul><li>For installs, this is the install date.</li><li>For in-app events, this is the date of the event.</li></ul> | YYYY-MM-DD | Yes |
| event\_name | [Optional for Post-attribution in-app events fraud]<br /><br />Filter events by in-app event. Limit the report to specific events.  One or more events can be included.<br /><br />Example usage: `&event_name=af_purchase,af_login` | String | No |
| additional\_fields=rejected\_reason\_value | [Optional for Post-attribution in-app events fraud]<br /><br />**<Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor>** displays the valid contributor (media source) for hijacked installs/in-app events. Populated with either <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#attribution::2a6fd501">**contributor[1-3]**</Anchor> or **organic**. | String | No |
| detect-from | [Optional for Post-attribution installs]<br /><br />Start of the fraud detect date range. (Default is from.) (Used in Post-attribution install fraud.) (Used in Post-attribution install fraud.) | YYYY-MM-DD | No |
| detect-to | [Optional for Post-attribution installs]<br /><br />End of the fraud detection date range. (Default is to.) | YYYY-MM-DD | No |

</Accordion>

<div id="data-locker" />

<Accordion title="Data Locker">

Data Locker writes raw-data to an AWS S3 bucket.

<Anchor target="_blank" href="/marketers/docs/data-locker-advertiser-reports#protect360">See list of available Protect360 reports</Anchor>. 

<Anchor target="_blank" href="/marketers/docs/data-locker-for-marketers#aws-cli">See Data Locker configuration instructions</Anchor>.

</Accordion>

## Protect360 report structure

Protect360 reports have the same general structure as user acquisition reports fields.

In addition to the regular <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary">raw data report fields</Anchor>, Protect360 reports also have retargeting and blocked reason fields, as follows:

### Blocked reasons

<div id="click-level-blocked-reasons" />

<Accordion title="Click level blocked reasons">

At the click level, clicks are blocked, and the attribution process ignores them.

| Blocked reason | Description |
| --- | --- |
| ip\_blacklist | Based on a dynamically created list (<Anchor target="_blank" href="/marketers/docs/protect360-anti-fraud-guide#ip-denylists">details</Anchor>) |
| click\_capping | Extremely high rates of click fraud are detected from that ad network. <Anchor target="_blank" href="/partners/docs/protect360-for-integrated-partners#impression-capping">Learn more</Anchor> |
| click\_signing | Signature on the click is not validated. <Anchor target="_blank" href="/partners/docs/click-signing-for-ad-networks">Learn more</Anchor> |
| input\_validation | Invalid media source name |

</Accordion>

<div id="install-level-blocked-reasons" />

<Accordion title="Install level blocked reasons">

At the install level, we identify enough info at the time of install to determine either:

* A fake install, meaning the user installing the app is not a real person. In this case, the attribution is completely blocked.
* Attribution hijacking, where the user is real but the engagement is falsified. In this case, the fraudulent engagement is blocked and attribution is re-assigned to the first valid contributing ad network.

The following tables list possible install level blocked reasons:

#### Install level: Fake install block sub reasons

| Blocked reason | Blocked sub reason | Description |
| --- | --- | --- |
| bots | fake\_device\_parameters | Non-human behavior detected in device-related parameters during the app installation process |
| bots | fake\_install\_parameters | Non-human behavior detected in install-related parameters during the app installation process |
| bots | bayesian\_network | Bayesian network identification of fraudulent patterns |
| bots | user activity anomalies | Identifies abnormal or suspicious user behavior within the app using behavioral anomaly detection models. These models:<ul><li>Analyze user activity on an individual level</li><li>Surface deviations from expected patterns</li><li>Detect behavior clustering that diverges from legitimate user profiles</li><li>This detection helps flag bot activity that mimics real users but performs in-app actions in atypical ways.</li></ul> |
| bots | store validation | Validates that each install originates from an authentic and expected source. This mechanism:<ul><li>Verifies the integrity of the acquisition channel</li><li>Detects spoofed or manipulated install signals</li><li>Rejects installs that don’t align with genuine distribution pathways</li><li>By ensuring legitimacy at the install level, this method helps block bots attempting to fake organic or paid installs.</li></ul> |
| bots | App-interaction anomalies | Flags non-in-app-based events on post-install app interactions. Helps identify suspicious behavior in the transition from install to launches. |
| validation\_bots | invalid\_device\_parameters | Specific device fields expectation mismatch - defined by the customer |
| validation\_bots | validation\_rules | Rules where the outcome is blocked installs based on manually defined validation rule |
| bots | ai\_layer | AI models are utilized to analyze vast amounts of data points, enhancing detection capabilities for identifying fraudulent device and installation activities. |

#### Install level: Attribution hijacking block sub reasons

| Blocked reason | Blocked sub reason | Description |
| --- | --- | --- |
| ctit\_anomalies | short\_ctit | Install blocked due to short CTIT: Protect360 defined |
| install\_hijacking | referrer\_hijack | Blocked hijacking attempt based on GooglePlay API and AppsFlyer SDK parameters |
| install\_hijacking | integration\_temporarily\_blocked | Install blocked because the partner (pid) has extremely high fraud rates and significant anomalies in all their traffic |
| validation\_hijacking | short\_ctit | Install blocked due to short CTIT: Customer defined |
| validation\_hijacking | empty\_site\_id | Install blocked due to unpopulated site ID. Rule implementation is phased |
| validation\_hijacking | validation\_rules | Rules where the outcome is blocked attribution based on manually defined validation rule |

</Accordion>

<div id="cluster-level-blocked-reasons" />

<Accordion title="Cluster level blocked reasons">

When a pattern of fraud is detected, the fraud source is denylisted. Installs from this denylisted source are blocked either because of:

* A fake install, meaning the user installing the app is not a real person. In this case, the attribution is completely blocked.
* Attribution hijacking, where the user is real but the engagement is falsified. In this case, the fraudulent engagement is blocked and attribution is re-assigned to the first valid contributing ad-network.

The following tables list possible cluster level blocked reasons:

#### Cluster level: Fake install block reasons

| Blocked reason | Blocked sub reason | Description |
| --- | --- | --- |
| bots | timestamp\_anomalies | Anomalies related to attribution flow click times and other timestamps collected from the device |
| bots, site\_blacklist | device\_emulators | Installs generated on a large scale by automatic scripts working in virtual environments |
| site\_blacklist | device\_farms | High rates of unknown (new) devices |
| behavioral\_anomalies | behavioral\_anomalies | Suspicious in-app behavior compared to common app user behavior pattern |

#### Cluster level: Attribution hijacking block reasons

| Blocked reason | Blocked sub reason | Description |
| --- | --- | --- |
| ctit\_anomalies, install\_hijacking | ctit\_anomalies | Abnormal CTIT pattern per app standards |
| click\_flood | click\_flood | Abnormally high click volume across long CTIT distribution |
| install\_hijacking | click\_clusters | Clicks generated by a device-level malware |
| Re-engagement Hijacking | Re-engagement Click Clusters | Detects fraudulent attempts to hijack re-engagement attribution. These manipulations aim to steal credit from legitimate retargeting networks or even from users who didn’t see any retargeting ad at all.<br />Once detected, attribution is corrected and reassigned to:<ul><li>The valid retargeting network</li><li>The original user acquisition (UA) provider</li><li>Organic, if the user installed the app without being exposed to any valid retargeting ad</li></ul> |

</Accordion>

<div id="inapp-level-blocked-reasons" />

<Accordion title="In-app level blocked reasons">

In-app events can be blocked for the following reasons:

* The initial install was identified as fake.
* Because of a defined validation rule.
* Because our algorithm detects fraud.

The following table lists possible in-app level blocked reasons.

#### In-app level block reasons

| Blocked reason | Blocked sub reason | Description |
| --- | --- | --- |
| Inherits from install | Inherits from install | Initial install identified as fake based on [install](/docs/protect360-raw-data-reports#install-level-blocked-reasons) or [denylisted](/docs/protect360-raw-data-reports#cluster-level-blocked-reasons) level reason |
| inapps\_bots | fake\_device\_parameters | AppsFlyer algorithm detects fraud |
| in\_app\_store\_validation | - | <Anchor target="_blank" href="/marketers/docs/legacy-receipt-validation-for-in-app-purchases">Receipt validation</Anchor> for in-app purchase fails. |
| validation\_inapps | validation\_rules | Based on manually defined validation rule |

</Accordion>

### Retargeting

Protect360 raw data includes fraudulent installs and sessions from retargeting campaigns (known as re-attributions and re-engagements, respectively). Data displays using the <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#event">event name</Anchor> and <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#attribution::e9c68f6c">retargeting conversion type</Anchor> fields. They are marked as either an:

* Install (applies to event name, but not retargeting conversion type)
* Re-attribution
* Re-engagement
* Reinstall

Protect360 retargeting raw data is available for real-time blocks and fraud identified post attribution as follows:

<table><thead><tr><th>Report </th><th>Export data</th><th>Pull API</th><th>Data Locker</th></tr></thead><tbody><tr><td>Installs</td><td><span>✓\*</span></td><td><span>✓\*</span></td><td>-</td></tr><tr><td>Post-attribution installs</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="4"><span>\* Re-engagement data not available</span><br/> </td></tr></tbody></table>

### Hijacked installs attribution correction

For hijacked installs, AppsFlyer blocks attribution to the fraudulent network and instead attributes the last legitimate contributor source.

For hijacked installs use the <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor> field to identify the valid contributor (media source), meaning the contributor that should have originally received attribution.

* The **rejected\_reason\_value** is populated with either <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary#attribution::2a6fd501">**contributor[1-3]**</Anchor> or **organic**. Check the **contributor[1-3]** **media source/partner** fields to view the contributor details and reconcile.
* If the contributor fields are not displayed in your report, they are available to be added from the **Export data** page.

**Note**: When hijacked installs are blocked in real-time, the correct attributions display in AppsFlyer dashboards and reports (not just Protect360). When hijacked installs are identified post-attribution, the correct attributions are displayed only in Protect360 raw data.

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remark |
| --- | --- |
| Inapps reports | The inapps reports don't include the contributor field. The contributor fields are available in the installs report only. |
| Empty values | Due to raw data restrictions related to privacy, the raw reports may show fields with empty values. An example of this is the contributor fields. |

</Accordion>

<div data-zendesk-anchors="h_01HE7S55TCE60A34T6RCNTCQK8=about-protect360-raw-data-reports h_01J91EP40Q69KXXF2SR66AM2FQ=note h_01HE7S55TC4G31R9EANMKCZ7V5=report-types protect360-rawdata-report-types=protect360-raw-data-report-types h_01HE7S55TCKQYTXPV6J54SHM0D=protect360-raw-data-report-types h_01HE7S55TC4F5S243BSGN74RDK=postattribution-reports using-postattribution-reports=using-post-attribution-reports h_01HE7S55TC7KCF75KFXHCE3K2K=using-post-attribution-reports h_01HE7S55TCR8BKZ0PQ5B14X3X4=example h_01HE7S55TC95YC1BJJ0ZERCQ14=raw-data-availability-by-tool-type protect360-rawdata-availability-by-tool-type=protect360-raw-data-availability-by-tool-type h_01HE7S55TCH4CES29C5J3QXQK4=protect360-raw-data-availability-by-tool-type h_01HE7S55TC3MRT6E9QV0J0X6FC=getting-raw-data-reports h_01HE7S55TCBVFQ1DH06G53BNEN=download h_01HE7S55TCMT81J4SWBFQFYV2C=pull-api h_01HE7S55TCRRD95D0QPCXBRF8T=pull-api-raw-data-report-parameters h_01HE7S55TCMAY86J1HKYB0APZ6=data-locker h_01HE7S55TCS91ZC9V3K0VDSVXK=protect360-report-structure h_01HE7S55TC1ZEDD5ABD21FCPY2=blocked-reasons h_01HE7S55TDMDSVQCVSV5YS3CZN=click-level-blocked-reasons h_01HE7S55TD754T07FWHFK5P71K=install-level-blocked-reasons install-level-fake-install-block-reasons=install-level-fake-install-block-sub-reasons h_01HE7S55TDHTE5P47N1CCREGZX=install-level-fake-install-block-sub-reasons install-level-attribution-hijacking-block-reasons=install-level-attribution-hijacking-block-sub-reasons h_01HE7S55TDFA6WGAHE80ECV8CA=install-level-attribution-hijacking-block-sub-reasons h_01HE7S55TDCHG0CVJA3JRSAW3G=cluster-level-blocked-reasons h_01HE7S55TDBES0BY0FF3WKSSVG=cluster-level-fake-install-block-reasons h_01HE7S55TD3M45TH4PY2W805W7=cluster-level-attribution-hijacking-block-reasons h_01HE7S55TDGB05PEZX8KS3J3QJ=inapp-level-blocked-reasons inapp-level-block-reasons=in-app-level-block-reasons h_01HE7S55TD661EHCV50S9BW5MS=in-app-level-block-reasons h_01HE7S55TDSYDC8BWZ8D8DF9JE=retargeting h_01HE7S55TD8SDCQJCCYQC0MNES=hijacked-installs-attribution-correction h_01J91E55BXQ4E01A9R3EB33WYF=traits-and-limitations" />

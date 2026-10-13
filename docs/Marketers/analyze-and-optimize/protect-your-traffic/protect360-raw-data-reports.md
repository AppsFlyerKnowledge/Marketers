---
title: "Protect360 raw data reports"
excerpt: "Raw data reports describe installs and in-app events blocked by the Protect360 engine, as well as from manually added Validation Rules."
x-zendesk:
  id: 360015179337
  url: https://support.appsflyer.com/hc/en-us/articles/360015179337-Protect360-raw-data-reports
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Protect your traffic
  section_id: 6551015912465
  position: 8
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 27439133508369
  content_tags: [pm-roy-yanai, Marketers, Protect360]
  labels: [Advertisers, Protect360, protect, protect 360, '360', Raw Data, Premium, Marketers, Localize]
  promoted: false
  comments_disabled: true
  created_at: '2020-11-09T13:03:45Z'
  edited_at: '2026-03-28T14:03:09Z'
---
## About Protect360 raw data reports

Raw data reports:

- Display data about:
  - Clicks, installs, and in-app events identified as fraudulent by the Protect360 engine.
  - Installs and in-app events identified via Validation Rules.
- Include the block reason for each click, install, or in-app event.
- Are used by advertisers to reconcile ad network accounts, for optimization, and to adjust attribution dashboards for post-attribution fraud.
- May have [some fields are restricted or not available](/docs/about-raw-data-identifier-restrictions) if [AppsFlyer Aggregated Advanced Privacy (AAP)](/docs/apply-aggregated-advanced-privacy-framework).
- Report types and their availability by download, API, and Data Locker (S3 bucket) are described in the sections that follow.
- Historical raw data report retention is up to 90 days, depending on the reporting tool and origin of the raw data.

> 📘 Note
>
> Due to raw data restrictions related to privacy, the raw reports may show fields with empty values. An example of this is the contributor fields.

### Report types

#### Protect360 raw-data report types

| Report | Description |
| --- | --- |
| Installs | Reports include: <br />- **Fake installs**: Installs identified as fraudulent by the Protect360 engine. These do not appear in any AppsFlyer dashboard or raw data, except for the Protect360 dashboard and raw data.<br />- **Hijacked installs**: Real user installs where attribution is stolen, but Protect360 [corrects the attribution](/docs/protect360-raw-data-reports#hijacked-installs-attribution-correction).<br />- **Validation Rules**: That either blocked the install or blocked the attribution (Protect360 [corrects the attribution](/docs/protect360-raw-data-reports#hijacked-installs-attribution-correction)). |
| Post-attribution installs | Reports include installs attributed to a media source, but later found to be fraudulent. Protect360 [corrects the attribution](/docs/protect360-raw-data-reports#hijacked-installs-attribution-correction). |
| Blocked in-app events | Reports include in-app events from:<br />- **Fake installs**: IAEs are blocked.<br />- **In-app events**: Identified as fraudulent independent of the original installs.<br />- **Validation Rules**:  - IAEs from a rule that blocked the install or blocked attribution.<br />  - IAEs from a rule that blocked the in-app event. |
| Post-attribution in-app events | Reports include in-app events:<br />- Identified post-attribution.<br />- Of installs attributed to a media source, but later found to be fraudulent. |
| Clicks | Reports include blocked clicks with the block reasons. |
| Blocked install postbacks | Reports include copies of the rejection postbacks sent to media sources bringing blocked installs. |

### Post-attribution reports

- Post-attribution raw data fraud reports have the same structure as the blocked fraud reports.
- The current month (by install date) post-attribution report continues to be updated until the seventh day of the following month (detection date).
- Post attribution raw data reports are limited to advertisers. Agencies need [permissions](/docs/protect360-for-integrated-partners) enabled to access.
- Reports contain post-attribution fraud events identified by Protect360 and include all media sources in a single report. **Note**: If no post attribution fraud events are identified for the selected date range, the report returns empty,
- Post-attribution raw data fraud reports are available as follows:
  - Dashboard user interface: limited to one media source during one calendar month.
  - Pull API: contains all media sources. (Limitation: Available to app owners only.)

#### **Using post-attribution reports**

- Select any combination of install/IAE and detect date ranges as needed.
- Take into consideration that Protect360 performs post-attribution detection during the calendar month of the install and up to the seventh day of the following month. This means, for example, that for installs in November, Protect360 checks for fraud up to December 7.
- The best practice for using this Pull API is as follows:
  - Assume you pull the report on a daily basis.
  - Set the install date range to 60 days looking back from the current day.
  - Set the detect-from/detect-to range to the day before the current day.

    This means you will get the list of post-attribution frauds detected yesterday. If you didn't pull the report for a few days, adjust the detect date range, and pull the report.

#### Example

**Example A**: During December (install date) 15 installs are attributed to example\_media. On January 3 (detection date), Protect360 identifies example\_media as a fraudster. As a result, the 15 installs attributed to example\_media are listed as fraudulent in the post-attribution fraud report for further action by the app owner.

**Example B**: During December, 15 installs are attributed to example\_media. On January 9, Protect360 identifies example\_media as a fraudster. In this case, no action is taken by Protect360 because the fraudster was identified after the month close on January 7.

### Raw data availability by tool type

#### Protect360 raw-data availability by tool type

| Report | Data freshness | Pull API | Export Data page | Data Locker |
| --- | --- | --- | --- | --- |
| Installs | Real-time | **✓** | **✓** | **✓\*** |
| Blocked in-app events | Real-time | **✓** | **✓** | **✓** |
| Clicks | Real-time | **✓** | **✓** | **✓** |
| Blocked install postbacks | Real-time | - | **✓** | - |
| Post-attribution installs | Daily 15:00 UTC | **✓** | **✓** | **✓\*** |
| Post-attribution in-app events | Daily 20:00 UTC | **✓** | **✓** | - |
| \* Limitations to report via Data Locker:<br />- Agency transparency not supported. Meaning that agency-driven traffic does not contain the name of the media source sending the install.<br />- The report has a unique set of fields relative to other Data Locker reports. This list can't be changed.<br />- Retargeting data is not available in the Installs report; only in the Post-attribution installs report. |

## Getting raw data reports

Raw data reports are available by download, Pull API, and Data Locker (S3 bucket). You can also [give partners access to reports](/docs/protect360-for-integrated-partners).

<Tabs>
<Tab title="Download">

**To download:**

1. In the Protect360 dashboard, go to **Raw data reports** > **Blocked** or **Post-attribution.**
   - For post-attribution reports, select the media source and month.
2. Select the **Protect360 & Validation Rules** report to download.

**OR**

1. In the AppsFlyer dashboard, go to **Export Data**.
2. Select the **Protect360 & Validation Rules** report to download.

> 📘 Note
>
> Reports downloaded from the Export Data page contain all media sources.

</Tab>
<Tab title="Pull API">

**To download raw data reports available by Pull API:**

**Before you begin:**

You need a Pull API token. Get the token from an [admin user](/docs/managing-appsflyer-tokens).

1. Go to **Report > API Access.** The [Pull API](/docs/pull-api-raw-data) page opens.
2. In the Protect360 fraud reports section, select the necessary Pull API call.
3. Populate the parameters as required. The table that follows lists the parameters.
4. Pull the report.

#### Pull API raw data report parameters

| Parameter | Description | Format | Mandatory |
| --- | --- | --- | --- |
| app\_id | App ID as it appears in AppsFlyer | String | Yes |
| api\_token | Retrieve the key from the Dashboard. Go to **Report** \> **API Access.** Only an admin user can retrieve the API token. | String | Yes |
| from | Start of the date range:<br />- For installs, this is the install date.<br />- For in-app events, this is the date of the event. | YYYY-MM-DD | Yes |
| to | End of the date range:<br />- For installs, this is the install date.<br />- For in-app events, this is the date of the event. | YYYY-MM-DD | Yes |
| event\_name | [Optional for Post-attribution in-app events fraud]<br />Filter events by in-app event. Limit the report to specific events.  One or more events can be included.<br />Example usage: `&event_name=af_purchase,af_login` | String | No |
| additional\_fields=rejected\_reason\_value | [Optional for Post-attribution in-app events fraud]<br />**[rejected\_reason\_value](/docs/raw-data-field-dictionary#protect360)** displays the valid contributor (media source) for hijacked installs/in-app events. Populated with either [**contributor[1-3]**](/docs/raw-data-field-dictionary#attribution::2a6fd501) or **organic**. | String | No |
| detect-from | [Optional for Post-attribution installs]<br />Start of the fraud detect date range. (Default is from.) (Used in Post-attribution install fraud.) (Used in Post-attribution install fraud.) | YYYY-MM-DD | No |
| detect-to | [Optional for Post-attribution installs]<br />End of the fraud detection date range. (Default is to.) | YYYY-MM-DD | No |

</Tab>
<Tab title="Data Locker">

Data Locker writes raw-data to an AWS S3 bucket.

[See list of available Protect360 reports](/docs/data-locker-advertiser-reports#protect360).

[See Data Locker configuration instructions](/docs/data-locker-for-marketers#aws-cli).

</Tab>
</Tabs>

## Protect360 report structure

Protect360 reports have the same general structure as user acquisition reports fields.

In addition to the regular [raw data report fields](/docs/raw-data-field-dictionary), Protect360 reports also have retargeting and blocked reason fields, as follows:

### Blocked reasons

#### Click level blocked reasons

At the click level, clicks are blocked, and the attribution process ignores them.

| Blocked reason | Description |
| --- | --- |
| ip\_blacklist | Based on a dynamically created list ( [details](/docs/protect360-anti-fraud-guide#ip-denylists)) |
| click\_capping | Extremely high rates of click fraud are detected from that ad network. [Learn more](/docs/protect360-for-integrated-partners#impression-and-click-capping) |
| click\_signing | Signature on the click is not validated. [Learn more](/docs/click-signing-for-ad-networks) |
| input\_validation | Invalid media source name |

#### Install level blocked reasons

At the install level, we identify enough info at the time of install to determine either:

- A fake install, meaning the user installing the app is not a real person. In this case, the attribution is completely blocked.
- Attribution hijacking, where the user is real but the engagement is falsified. In this case, the fraudulent engagement is blocked and attribution is re-assigned to the first valid contributing ad network.

The following tables list possible install level blocked reasons:

#### Install level: Fake install block sub reasons

| Blocked reason | Blocked sub reason | Description |
| --- | --- | --- |
| bots | fake\_device\_parameters | Non-human behavior detected in device-related parameters during the app installation process |
| bots | fake\_install\_parameters | Non-human behavior detected in install-related parameters during the app installation process |
| bots | bayesian\_network | Bayesian network identification of fraudulent patterns |
| bots | user activity anomalies | Identifies abnormal or suspicious user behavior within the app using behavioral anomaly detection models. These models:<br />- Analyze user activity on an individual level<br />- Surface deviations from expected patterns<br />- Detect behavior clustering that diverges from legitimate user profiles<br />- This detection helps flag bot activity that mimics real users but performs in-app actions in atypical ways. |
| bots | store validation | Validates that each install originates from an authentic and expected source. This mechanism:<br />- Verifies the integrity of the acquisition channel<br />- Detects spoofed or manipulated install signals<br />- Rejects installs that don’t align with genuine distribution pathways<br />- By ensuring legitimacy at the install level, this method helps block bots attempting to fake organic or paid installs. |
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

#### Cluster level blocked reasons

When a pattern of fraud is detected, the fraud source is denylisted. Installs from this denylisted source are blocked either because of:

- A fake install, meaning the user installing the app is not a real person. In this case, the attribution is completely blocked.
- Attribution hijacking, where the user is real but the engagement is falsified. In this case, the fraudulent engagement is blocked and attribution is re-assigned to the first valid contributing ad-network.

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
| Re-engagement Hijacking | Re-engagement Click Clusters | Detects fraudulent attempts to hijack re-engagement attribution. These manipulations aim to steal credit from legitimate retargeting networks or even from users who didn’t see any retargeting ad at all.<br />Once detected, attribution is corrected and reassigned to: <br />- The valid retargeting network<br />- The original user acquisition (UA) provider<br />- Organic, if the user installed the app without being exposed to any valid retargeting ad |

#### In-app level blocked reasons

In-app events can be blocked for the following reasons:

- The initial install was identified as fake.
- Because of a defined validation rule.
- Because our algorithm detects fraud.

The following table lists possible in-app level blocked reasons.

#### In-app level block reasons

| Blocked reason | Blocked sub reason | Description |
| --- | --- | --- |
| Inherits from install | Inherits from install | Initial install identified as fake based on [install](/docs/protect360-raw-data-reports#install-level-blocked-reasons) or [denylisted](/docs/protect360-raw-data-reports#cluster-level-blocked-reasons) level reason |
| inapps\_bots | fake\_device\_parameters | AppsFlyer algorithm detects fraud |
| in\_app\_store\_validation | - | [Receipt validation](/docs/legacy-receipt-validation-for-in-app-purchases) for in-app purchase fails. |
| validation\_inapps | validation\_rules | Based on manually defined validation rule |

### Retargeting

Protect360 raw data includes fraudulent installs and sessions from retargeting campaigns (known as re-attributions and re-engagements, respectively). Data displays using the [event name](/docs/raw-data-field-dictionary#event) and [retargeting conversion type](/docs/raw-data-field-dictionary#attribution::e9c68f6c) fields. They are marked as either an:

- Install (applies to event name, but not retargeting conversion type)
- Re-attribution
- Re-engagement
- Reinstall

Protect360 retargeting raw data is available for real-time blocks and fraud identified post attribution as follows:

| Report | Export data | Pull API | Data Locker |
| --- | --- | --- | --- |
| Installs | **✓\*** | **✓\*** | - |
| Post-attribution installs | **✓** | **✓** | **✓** |
| \* Re-engagement data not available |

### Hijacked installs attribution correction

For hijacked installs, AppsFlyer blocks attribution to the fraudulent network and instead attributes the last legitimate contributor source.

For hijacked installs use the [rejected\_reason\_value](/docs/raw-data-field-dictionary#protect360) field to identify the valid contributor (media source), meaning the contributor that should have originally received attribution.

- The **rejected\_reason\_value** is populated with either [**contributor[1-3]**](/docs/raw-data-field-dictionary#attribution::2a6fd501) or **organic**. Check the **contributor[1-3]** **media source/partner** fields to view the contributor details and reconcile.
- If the contributor fields are not displayed in your report, they are available to be added from the **Export data** page.

> 📘 Note
>
> When hijacked installs are blocked in real-time, the correct attributions display in AppsFlyer dashboards and reports (not just Protect360). When hijacked installs are identified post-attribution, the correct attributions are displayed only in Protect360 raw data.

### Traits and limitations

| Trait | Remark |
| --- | --- |
| Inapps reports | The inapps reports don't include the contributor field. The contributor fields are available in the installs report only. |
| Empty values | Due to raw data restrictions related to privacy, the raw reports may show fields with empty values. An example of this is the contributor fields. |
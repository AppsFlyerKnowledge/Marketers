---
title: "SKAN raw data reports"
x-zendesk:
  id: 360014261518
  url: https://support.appsflyer.com/hc/en-us/articles/360014261518-SKAN-raw-data-reports
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SKAN solution
  section_id: 6552135379985
  position: 5
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, SKAdNetwork (SKAN)]
  labels: [Advertisers, Premium Feature, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2020-10-08T20:54:55Z'
  edited_at: '2024-12-05T17:23:46Z'
---
**At a glance:** SKAN raw data reports contain row-level data generated after translating and decoding postbacks received by AppsFlyer from iOS, as well as raw SKAN postbacks. Data is available via [Data Locker](/docs/data-locker-for-marketers) and [Push API](/docs/push-api-streaming-raw-data). If your subscription plan includes raw data, there is no need for a Data Locker subscription.

## SKAN raw data reports

Principles:

- **Data is provided by:**
  - **Data Locker**
    > 📘 Note
    >
    > Available to accounts having a raw data subscription. Meaning, there is no need for a Data Locker subscription. If you aren't currently using Data Locker, an admin user must configure Data Locker and enable the SKAN reports. To do so, go to **Reports** > **Data Locker**. Select the SKAN reports.
    - **Data freshness rate**: Daily. Data is contained in the h=23 folder of the date the postback is received by AppsFlyer.
  - **Push API**
    - Data freshness: See [Push API for SKAN data](/docs/push-api-streaming-raw-data).
- **Install date**: Is derived from the postback arrival time by AppsFlyer as follows:
  - If the postbacks are SKAN V4, the install date formula is: Install date = postback arrival time - [accumulated window length] - [average postback delay].
    - Postback 1: install date = postback arrival time - 48h - 36h
    - Postback 2: install date = postback arrival time - 168h - 84h
    - Postback 3: install date = postback arrival time - 840h - 84h
  - If the postbacks are SKAN V3, the install date formula is: Install date = postback arrival time - 36 hours - [average last-active range]. 
    - The default [average last-active range] is 12 hours.
    - For a conversion value of 0, the average last-active range is set to 0.
  - Google estimates the install time on its own and AppsFlyer uses that install time.
    > 📘 Note
    >
    > It can take up to 45 days for Google to report installs. [Learn more](/docs/get-skan-postback-data-from-google-ads#get-skan-postback-data-from-google-ads)

Report types available are:

- **Device postback**: 1 device postback per install or redownload received from the iOS device.
- **SKAN raw data**:
  - AppsFlyer decodes and translates the device postback into raw data records.
  - Each postback generates an install or redownload record and in-app event records.
  - The number of in-app event records depends on the conversion value (CV) as follows:
    - CV = 0, blank, or null: No in-app records are generated.
    - CV range:
      - 1-63: For SKAN 3, and SKAN 4 window 1 fine value, this is the number of in-app records, depending on your measurement settings.
      - Low, medium, or high: For SKAN 4 coarse values, this is the number of in-app records, depending on your measurement settings.

**Why are some fields empty?** This occurs for any of the following reasons:

- Non-mandatory enrichment fields like campaign_name, ad_network_campaign_id, ip that the ad network did not provide.
- Apple withheld the data due to Apple threshold policies. Fields like source_app_id, skad_campaign_id, skad_conversion_value.

## SKAN raw data report format and content

### Raw data report types

| Report type | Report name | Description |
| --- | --- | --- |
| Postback | Postbacks | Postbacks sent by iOS to the ad network. The postback, after enrichment by the ad network, is forwarded to AppsFlyer. [Download postbacks example](https://docs.google.com/spreadsheets/d/e/2PACX-1vRfFFmj1YV1c73Wbar2VOiKWml6VmsyFvQuydXTPUOO4zXVKmwtw6nup9vKNtNwou2z8IqNpcF4yP6c/pub?gid=1225544365&single=true&output=csv) (CSV).<br />Note: Postbacks aren't included when did_win=false.<br />**Topic name in Data Locker**: skad_postbacks |
| Postback | Postbacks copy (direct from Apple) | Postbacks sent directly by iOS to AppsFlyer.<br />Available starting iOS 15+ and requires the advertiser to configure the app to [send the winning postback](/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15) to AppsFlyer. [Download postbacks copy example](https://docs.google.com/spreadsheets/d/e/2PACX-1vSu0c3gYoIHe2k6_M3cngSFzc-txQvEN38X7Ig7qhXYPg8uBUzyyPqlSwDMugvZS_tUrFjtY8AGYKrh/pub?gid=1225544365&single=true&output=csv) (CSV).<br />Note: This topic contains only winning postbacks. <br />**Topic name in Data Locker**: skad_postbacks_copy |
| Decoded event | Installs | **First-time app installs**<br />SKAN reported _redownload=false_. Meaning, this is the first time the user, represented by the Apple ID, downloaded the app.<br />[Download installs example](https://docs.google.com/spreadsheets/d/e/2PACX-1vS4rNJAio8Ub2cffUEiYhzdavVfXaJAD6OpjhRBjVpGQsAlibOWCkZpfLl29n1OCDBZ2eToO4_gOvbl/pub?gid=1472391837&single=true&output=csv) (CSV).<br />**Topic name in Data Locker**: skad_installs |
| Decoded event | Redownloads | **App installs that are not first-time installs**<br />SKAN reported _redownload=true_. Meaning, this is not the first time the user, represented by the Apple ID, downloaded the app. This report has the same structure as installs.<br />**Topic name in Data Locker**: skad_redownloads |
| Decoded event | In-app events | **In-app events**<br /><br />Starting July 21, 2021, there are changes to how we provide in-app event raw data as detailed in the tables.<br /><br />The number of in-app event records depends on your measurement settings.<br /><br />[Download in-app events example](https://docs.google.com/spreadsheets/d/e/2PACX-1vRwhxOmZwTkOr9uNFN0d4Rk2jFpipONoB8KzIZI5Tw12IvoLirj07QUdI9RJoL9rZYFSN1PvT-W6vP0/pub?gid=1454741057&single=true&output=csv) (CSV).<br /><br />**Topic name in Data Locker**: skad_inapps |

Valid for iOS postbacks received starting July 21, 2021:

| Measurement type | Description |
| --- | --- |
| Revenue | - Revenue of a given user. If revenue > 0, a record containing the skad_revenue and event_name fields.<br />- The fields min_revenue and max_revenue are populated with your custom conversion range values. |
| In-app conversion and funnel events | - A record for each unique conversion event performed. The event_name field is populated accordingly. If no events are performed, there is no record.<br />- Conversion events have min_event_counter = 0 and max_event_counter = 1. |
| In-app engagement | To determine the number of times a user performed a given in-app event use the formula `[round up (min_event_counter + max_event_counter) / 2]` |

Valid for iOS postbacks received until July 20, 2021:

| Measurement type | Number of records | Description |
| --- | --- | --- |
| Revenue | 0-1 | If revenue > 0, a record containing the skad_revenue and event_name fields. |
| Conversion | 0-6 | A record for each unique conversion event performed. The event_name field is populated accordingly. If no events are performed, there is no record. |
| Engagement | 0-63 | The number of records represents the number of times the user performed the engagement event. If the user does not engage, there are no engagement records. |
| Custom | 0-unlimited | According to your custom conversion schema. |
| Decoded event | SRN advertising dimensions | - Report contains Meta ads events with campaign, adset, and ad granularity. Each row in the report can be either an install or in-app event.<br />- Adset and ad granularity isn't included in SKAN postbacks from Meta ads. This data is unique to this report, and doesn't display in the SKAN dashboard, Performance API, and other SKAN Data Locker reports.<br />- Report is schemaless. Data Locker field selection options don’t apply.<br />- Best practice: Don't combine or compare data from this report with other SKAN reports, as there may be discrepancies between this report, which uses data decoded by the SRN, and other reports, which use data decoded by AppsFlyer. These discrepancies can be due to time zone differences, SRN schema differences, or incorrectly mapped in-app events-to-CV in the SRN integration.<br />- [Download SRN advertising dimensions example](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZjIpqZJxHY9WpIdf9OeDCVQYzM_fLmrpB1oAt3S-MbJTKueOJODwwl6Pz3M0SCAbCFIdMlshOayrw/pub?output=xlsx) (CSV).<br />**Topic name in Data Locker**: skad_srn_advertising_dimensions |

### Raw data field format types

#### Field formats

| Format name | Description |
| --- | --- |
| String [n] | The maximum length of the string. We don't usually enforce field length limitations on receipt of the data, but data may be truncated thereafter. |
| Time string | String having the format, `yyyy-mm-dd hh:mm:ss`. For example, `2019-09-17 00:09:25` |
| Enum [n] | Enum fields can only contain specific values. For example, Cost currency has 3 characters and can contain only currency codes as specified. |
| Timestamp | 10-digit UNIX timestamp. Example:<br />August 4, 2020, 07:25 UTC translates to `"timestamp": "1596525944"` |
| Boolean | The value of the field can be either `TRUE` or `FALSE` |
| Integer | Integer |
| Float | Real floating number that can have a decimal point and values after the decimal point. |

### Fields available in postback and postback copy reports

| Field name | Source or iOS SKAN starting version | Description | Format | Available in postbacks copy |
| --- | --- | --- | --- | --- |
| ad_network_campaign_id | Ad network | Campaign ID reported by the ad network to AppsFlyer | String | No |
| ad_network_campaign<br />_name | Ad network | Campaign name reported by the ad network to AppsFlyer. | String | No |
| ad_network_timestamp | Ad network | Time the ad network received the postback.<br />In the case of Google Ads, the time is derived from the last-click time reported by Google. | Timestamp | No |
| app_id | AppsFlyer | App ID (advertiser app) with prefix ID. | String | Yes |
| city | AppsFlyer | Starting August 30, 2021, always null | String | No |
| country_code | Ad network |  | String | No |
| dma |  | Starting August 30, 2021, always null | String | No |
| postal_code |  | Starting August 30, 2021, always null | String | No |
| region | AppsFlyer | According to the country_code reported | String | No |
| skad_ad_network_id | 1.0 | Some SRNs don't share their ID, and the field is left blank. For example, X Ads. | String | Yes |
| skad_attribution_signature | 1.0 |  | String | Yes |
| skad_campaign_id | 1.0 | Campaign ID used to publish the ad. Range 0-100 | String | Yes |
| skad_conversion_value | 2.0 | Conversion value reported by iOS. Range 0-63.<br />If null, iOS didn't populate the field\*\* | Integer | Yes |
| skad_redownload | 2.0 | If true, app was redownloaded | Boolean | Yes |
| skad_source_app_id | 2.0 | Site ID. The app publishing the ad. This field is identical to source_app_id.<br />Field population depends on privacy thresholds\*\* | String | Yes |
| skad_transaction_id | 1.0 |  | String | Yes |
| skad_version | 2.0 |  | String | Yes |
| timestamp | Ad network | Time that AppsFlyer received the SKAN postback. | Timestring | Yes |
| ad_network_name | Ad network | Ad network name reported by the ad network to AppsFlyer. <br />- If this field is blank, the ad network didn't (couldn't) populate it.<br />- You can resolve the ad network name using skad_ad_network_id. Use this [table](/docs/skan-integrated-partners-list#apple-skadnetwork-ids-of-ad-networks) to do so. | String | No |
| ip |  | IP address in the HTTP message of the iOS device sending the postback.<br />This field is populated if the ad network provides us with the address.<br />Note! The SDK isn't involved in getting the address. | String | No |
| skad_app_id | 1.0 |  | String | No |
| source_app_id | AppsFlyer | Site ID. The app publishing the ad. This field is identical to skad_source_app_id | String | No |
| ad_network_adset_id | Ad network |  | String | No |
| ad_network_adset_name | Ad network |  | String | No |
| ad_network_ad_name | Ad network |  | String | No |
| ad_network_ad_id | Ad network |  | String | No |
| did_win | 3.0 (iOS 14.6) | Used to distinguish between campaigns [contributing or attributed](https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes) with the install. <br />- If true, the campaign is attributed for bringing the install.<br />- If false, the campaign is recognized as contributing to the install, but it isn't included in any SKAN dashboards or reports.<br />- If null, iOS didn't populate the field due to a [legacy iOS or SKAdNetwork version](https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes). | Boolean | Yes |
| fidelity_type | 2.2 (iOS 14.5) | Differentiate between [ad presentation](https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions) options that affect attribution. Indicated using the values 0 and1 as follows: <br />- View-though ads (0)<br />- StoreKit-rendered ads (1)<br />Disregard the field value if the SKAN version is before 2.2 | Integer | Yes |
| ad_network_source_app_id | Ad network | Publisher app ID reported by the ad network. Use to help reconcile cost; reported by the ad network. The publisher app gives the basis for this data. | String | No |
| ad_network_channel | Ad network |  | String | No |
| af_prt | Ad network |  | String | No |
| skad_postback_sequence_index | 4.0 (iOS 16.2) | - Value represents the SKAN window, either `0`, `1`, or `2`.<br />- For SKAN 3 the value is `0` | Integer | Yes |
| skad_coarse_conversion_value | 4.0 (iOS 16.2) | - Value can be `low`, `medium`, or `high`.<br />- For SKAN 3 the value is `null`. | String | Yes |
| skad_source_identifier | 4.0 (iOS 16.2) | - Value can be up to 4 digits.<br />- For SKAN 3 the value is `null`. | String | Yes |
| skad_source_domain | 4.0 (iOS 16.2) | - Value represents the source of attributable web ads.<br />- For SKAN 3 the value is `null`. | String | Yes |
| ad_network_creative | Ad network | - Value is based on data enrichment received from the ad network.<br />- For SKAN 3 the value is `null`. | String | No |
| \*\* Apple determines if the field is populated using a privacy-threshold mechanism | | | | |

### Fields available in decoded event reports

| Field name | Source | Description | Format | Included in SRN advertising dimensions report |
| --- | --- | --- | --- | --- |
| ad_network_campaign_id | Ad network | Campaign ID reported by the ad network to AppsFlyer | String | Yes |
| ad_network_campaign<br />_name | Ad network | Campaign name reported by the ad network to AppsFlyer | String | Yes |
| ad_network_timestamp | Ad network | Time the postback was received by the ad network<br />In the case of Google Ads, this field isn't populated. | Timestamp<br />(time string for SRN advertising dimensions report) | Yes |
| app_id | iOS | The app ID (advertiser app) | String | Yes |
| city |  | Starting August 30, 2021, always null | String | No |
| country_code | Ad network |  | String | No |
| dma |  | Starting August 30, 2021, always null | String | No |
| event_name | AppsFlyer | In-app event name as configured in AppsFlyer.<br />For the SRN 
___report, this is the in-app event name as configured in Meta ads. | String | Yes |
| event_uuid | AppsFlyer | A unique random identifier enabling partners to identify duplicate postbacks | String | No |
| install_date | iOS | Estimated by AppsFlyer based on the postback arrival time. | Time string | No |
| install_type | iOS | New installs | String | No |
| ip | iOS | The IP address in the HTTP message of the iOS device sending the postback.<br />This field is populated if the ad network provides us with the address.<br />Note! The SDK isn't involved in getting the address. | String | No |
| media_source | iOS | Ad network attributed using AppsFlyer network names | String | Yes |
| postal_code |  | Starting August 30, 2021, always null | String | No |
| region | AppsFlyer | Determined according to the country_code | String | No |
| skad_ad_network_id | iOS | ID of the ad network to whom the postback was sent | String | No |
| skad_ambiguous_event (deprecated with SKAN 4+) | AppsFlyer | If true, the iOS postback was received during the first 72-hours after an advertiser changed the SKAN settings in the dashboard. Due to the various timers employed by SKAN, AppsFlyer can't map the event accurately.<br />- Not available in SKAN 4 and onwards | Boolean | No |
| skad_attribution_signature | iOS |  | String | No |
| skad_campaign_id | iOS | Campaign ID used to publish the ad. Range 0-100 | Integer | No |
| skad_conversion_value | iOS | Conversion value reported by iOS. Range 0-63.<br />If null, iOS didn't populate the field\*\* | Integer | No |
| skad_mode | AppsFlyer | The conversion measurement mode used to decode the iOS postback. Options:<br />- custom_decode<br />- revenue<br />- events<br />- skan4<br />- custom_encode<br />- engagement | String | No |
| skad_redownload | iOS | If true, the app was redownloaded | Boolean | No |
| skad_revenue | iOS | Event revenue amount in USD. | Float | No |
| skad_source_app_id | iOS | Site ID - the app publishing the ad.<br />Field population depends on privacy thresholds\*\* | String | No |
| skad_transaction_id | iOS | - | String | No |
| skad_version | iOS | - | String | No |
| timestamp | iOS | Time that AppsFlyer received the SKAN postback.<br />For Google Ads and Meta ads, this is the time AppsFlyer gets the data from the Google and Meta ads API, respectively. | Timestamp<br />(time string for SRN advertising dimensions report) | Yes |
| event_value | S2S | Default value: null<br />Contains a string set by apps implementing custom decode.<br />Advertisers consume this in their systems. AppsFlyer doesn't make use of it. | String (JSON) | No |
| ad_network_adset_id | Ad network |  | String | Yes |
| ad_network_adset_name | Ad network |  | String | Yes |
| ad_network_ad_name | Ad network |  | String | Yes |
| ad_network_ad_id | Ad network |  | String | Yes |
| skad_did_win (1) | 3.0 (iOS 14.6) | Used to distinguish between campaigns [contributing or attributed](https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes) with the install. <br />- If true, the campaign is attributed for bringing the install.<br />- If false, the campaign is recognized as contributing to the install, but it isn't included in any SKAN dashboards or reports.<br />- If null, iOS didn't populate the field due to a [legacy iOS or SKAdNetwork version](https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes). | Boolean | No |
| skad_fidelity_type (1) | 2.2 (iOS 14.5) | Differentiate between [ad presentation](https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions) options that affect attribution. Indicated using the values 0 and1 as follows: <br />- View-though ads (0)<br />- StoreKit-rendered ads (1)<br />Disregard the field value if the SKAN version is before 2.2 | Integer | Yes |
| ad_network_source_app_id (1) | Ad network | Publisher app ID reported by the ad network. Use to help reconcile cost; reported by the ad network. The basis for this data is provided by the publisher app. | String | No |
| ad_network_channel (1) | Ad network |  | String | No |
| af_prt (1) | Ad network |  | String | No |
| min_revenue | AppsFlyer | See note (4) | Real number | No |
| max_revenue | AppsFlyer | See note (4) | Real number | No |
| event_revenue | AppsFlyer | Formula: [sum of values for the specific event in USD]/[The number of events that happened on a specific day] | Float | Yes |
| min_event_counter | AppsFlyer | Use to calculate the number of times a user performs an event. See note (3) | Integer | No |
| max_event_counter | AppsFlyer | See note (3) | Integer | No |
| min_time_post_install | AppsFlyer | See note (5) | Integer | No |
| max_time_post_install | AppsFlyer | See note (5) | Integer | No |
| af_attribution_flag | AppsFlyer | When the Single Source of Truth (SSOT) mechanism is on: If true, the install was attributed by both AppsFlyer and SKAN. If false, the install wasn't attributed by AppsFlyer. If the skad_conversion_value is null, the flag is either true or false (based on [modeling](/docs/skan-modeled-data#null-conversion-values)). | Boolean | No |
| measurement_window | AppsFlyer | Duration of the activity window. Default 24h. | Integer | No |
| interval | AppsFlyer | Activity window intervals. | Integer | No |
| user_agent | AppsFlyer | Device user agent | String | No |
| skad_postback_sequence_index | 4.0 (iOS 16.2) | - Value represents the SKAN window, either `0`, `1`, or `2`.<br />- For SKAN 3 the value is `0` | Integer | Yes |
| skad_coarse_conversion_value | 4.0 (iOS 16.2) | - Value can be `low`, `medium`, or `high`.<br />- For SKAN 3 the value is `null`. | String | Yes |
| skad_source_identifier | 4.0 (iOS 16.2) | - Value can be up to 4 digits.<br />- For SKAN 3 the value is `null`. | String | Yes |
| skad_source_domain | 4.0 (iOS 16.2) | - Value represents the source of attributable web ads.<br />- For SKAN 3 the value is `null`. | String | Yes |
| ad_network_creative | Ad network | - Value is based on data enrichment received from the ad network.<br />- For SKAN 3 the value is `null`. | String | No |
| \*\* Apple determines if the field is populated using a privacy threshold mechanism<br />(1) Starting June 2, 2021, the field is added to reports but won't necessarily be populated.<br />(3) To determine the number of times a user performs a given in-app event use the formula: `[round up (min_event_counter + max_event_counter) / 2]` . Note! You must round up the nearest integer.<br />Example:<br />A. If min = 0 and max = 1 the average is 0.5; rounding up returns a result of 1.<br />B. If min = 5 and max = 10, the average is 7.5; rounding up returns a result of 8.<br />(4) Revenue is always provided in the field `skad_revenue`. If you use SKAN 4 or [Custom mode](/docs/skan-conversion-studio), the bucket range associated with the event and used to calculate skad_revenue is described by min_revenue and max_revenue.<br />(5)<br />- In Custom conversion: AppsFlyer calculates install time as the postback arrival time - 36h - average (min_time_post_install + max_time_post_install). However, if CV=0 then average (min_time_post_install + max_time_post_install) is regarded as 0. <br />- In Decode conversion: The min_time_post_install is one hour less than that set in max_time_post_install which is equal to [hours_from_install](/docs/skan-cv-decode-map-your-cv-to-events#decode-csv-file-specification) set by you in your Decode conversion mapping. | | | | |

## Additional information

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| Ad network access | Ad networks are provided with postbacks |
| Agency access | Not available |
| Agency transparency | N/A |
| Timezone | UTC |
| Currency | USD |
| Organic data | Based on SDK event data. For example, organic install metrics are calculated as follows: Data of all installs reported by the SDK less non-organic installs reported by SKAN. |
| Non-organic data | Based on SKAN postbacks |
| Data freshness | Daily. SKAN timing means that iOS reports on an install 24-48 hours after the window closes. |
| Historical data | Limited to the Data Locker availability window. |
| Account user access | Available. According to account permissions |

<Cards>
  <Card title="Available SKAN reports (SKAN solution guide)" href="/docs/skadnetwork-skan-solution-guide#reporting-options" icon="fa-solid fa-lock">
    Learn more about the reporting options available for SKAN.
  </Card>
</Cards>
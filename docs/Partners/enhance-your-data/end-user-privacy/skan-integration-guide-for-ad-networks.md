---
title: "SKAN integration guide for ad networks"
excerpt: "Integrate with AppsFlyer SKAdNetwork (SKAN) to optimize campaigns and ensure proper attribution for the traffic your ad network generates."
---
At a glance: Ad networks integrate with AppsFlyer SKAdNetworks (SKAN), enabling them to optimize campaigns and to be attributed to the traffic they generate.

## AppsFlyer offering for ad networks

**Learn more about the AppsFlyer SKAN solution for advertisers:**

[SKAN solution guide |](https://support.appsflyer.com/hc/articles/360011420698-SKANNetwork-Solution-guide-iOS-14-) [SKAN dashboard](https://support.appsflyer.com/hc/articles/360011307357)

- **Be attributed for campaign conversions:**  - Integration with AppsFlyer ensures that the ad network is attributed for all installs, in-app events, and revenue resulting from campaigns run on advertisers' behalf.
  - Without integration in place, installs, in-app events, and revenue are attributed as organic and not to the ad network.
- **Campaign optimization:**  - The conversion value in the postback is encoded.
  - AppsFlyer enables ad networks to translate the conversion value of each postback, ensuring ad networks can optimize their campaigns based on the decoded value per app.
- **No need for direct integration with each advertiser—** SKAN postbacks are sent only to the ad network and advertisers can consume the data using any of the following:  - Individual integration with each ad network. A solution that is not scalable, neither for ad networks nor for advertisers.
  - A single integration with AppsFlyer. Scalable for both the advertiser and the ad network.
- **Increase your prominence in AppsFlyer:**  - Ad networks having SKAN integration are certified and identified as such in the AppsFlyer dashboard.
  - This assures advertisers that they are working with ad networks that can be measured deterministically via this attribution model.

## SKAN data flow

<Image src="https://files.readme.io/dff0fb00721802f59d199ae6a69f9ea7484bc0ef038c669904aa1a7c2b97dfc8-12574373654161.png" alt="5754_Postback_flow_for_SKAD__1_.png" />

The full SKAN postback flow is as follows:

1. **iOS** sends the SKAN postback to the attributed ad network.
2. **The ad network**does one of the following:   - **Enrich and forward:** Enrich the SKAN postback with the ad network campaign ID/source identifier, campaign name, and the iOS device IP address.
   - **Redirect:** The network requests the iOS device to redirect the postback and campaign data it adds, back to AppsFlyer.
3. **AppsFlyer** validates and decodes the postback. Then, it sends the decoded and enriched postback to the ad network (in parallel to sharing it with the advertiser).

## Main integration parts

SKAN integration between AppsFlyer and ad networks consists of the following main parts as described in this article:

- Ad networks send SKAN data to AppsFlyer
- Ad networks receive enriched and decoded data from AppsFlyer via postbacks

## Send data to AppsFlyer

After the ad network receives the SKAN postback from the device, the ad network forwards it to AppsFlyer using one of the following methods:

- Enrich and forward (POST)
- Redirect (HTTP 307 redirect method)

Upon receipt of a SKAN postback, AppsFlyer performs the following:

- Postback validation: Ensure that it is unique.
- Conversion value decode: Generate attribution install/in-app event records.
- Send decoded postbacks to the ad network.
- Make attribution data available to advertisers via dashboards and reports.

### Enrich and forward

Using this method, ad networks forward each postback received from the device to AppsFlyer.

**The ad network:**

- Receives the postback from the iOS device.
- [Mandatory] Enriches the postback with:
  - Ad network campaign ID and campaign name.
  - The timestamp of the postback sent from the iOS device.
- [Optional] Enriches the postback with:
  - IP address received from the device, required mainly for geo resolution purposes.
  - Adset ID and name
  - Ad ID and name
  - Ad network name
  - Country code
  - Source app ID
  - Creative
  - Channel
- Sends the postback to AppsFlyer
- **Note!** Before sending the postback to AppsFlyer, validate the Apple [attribution signature](https://developer.apple.com/documentation/storekit/SKAdnetwork/verifying_an_install-validation_postback) using the content of the outgoing postback to ensure that you didn't inadvertently corrupt the data.

#### SKAN enriched postback protocol

| | |
| --- | --- |
| Endpoint | `https://skadpostbacks.appsflyer.com/api/postbacks` |
| HTTP method | POST |
| Accepted content types | `application/json` |
| Return codes | 200 OK: Postback received has a valid format. <br>400: Bad request: Malformed JSON, empty, JSON, missing mandatory fields. |

#### SKAN enriched postback JSON parameters

| Parameter | Format | Description | Source |
| --- | --- | --- | --- |
| version | String | SKAdNetwork version<br>Example: `"version":"2.0"` | SKAN postback |
| ad-network-id | String | Ad network ID<br>Example: `"ad-network-id":" abc123defg.SKAdnetwork"` | SKAN postback |
| ad-network-name | String | - Name of the ad network<br>- Example: `ad_network_name=your_network` | Ad network |
| ad-network-country-code | String | - The user location (geo) as derived by the ad network.<br>- Populate using [ISO 3166 (alpha-2)](https://www.iso.org/iso-3166-country-codes.html) codes.<br>- Example: CN, ZA<br>- Ad networks often derive geo according to a given campaign's target region. <br>- AppsFlyer uses the country code to populate geo-related fields in reports and dashboards. | Ad network |
| campaign-id | Integer | - Only for SKAN 3 and below<br>- SKAdNetwork campaign ID<br>- Example: `"campaign-id":23` | SKAN postback |
| transaction-id | String | SKAdNetwork postback transaction ID | SKAN postback |
| app-id | Integer | - Target app ID as it appears in AppsFlyer. Always has the prefix id.<br>- Example:`app_id=id123456789` | SKAN postback |
| attribution-signature | String | Attribution signature | SKAN postback |
| redownload | Boolean | When redownload = true, it means the user downloaded the app from the app store again. | SKAN postback |
| source-app-id | Integer | - Source App ID (publisher)<br>- For SKAN 4, available only in the first postback, for tier 3. See [Apple documentation](https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows) | SKAN postback |
| conversion-value | Integer | AppsFlyer SDK sets the conversion value according to advertiser settings.<br>**Notes**!<br>- iOS due to iOS privacy-preserving thresholds may not populate the parameter in the postback and the value will be null.<br>- Null and 0 have different meanings:<br> - Null: iOS withheld the conversion value<br> - 0: The user installed the app but didn't perform any measured actions. | SKAN postback |
| ad-network-campaign-id | String | To enable a common language between ad networks, advertisers, and AppsFlyer, you must provide your campaign-id. | Ad network |
| ad-network-campaign-name | String | Ad network campaign name associated with the ad network campaign ID. This name displays in dashboards and reports. | Ad network |
| ad-network-adset-id | String | Ad network adset ID | Ad network |
| ad-network-adset-name | String | Ad network adset name | Ad network |
| ad-network-ad-name | String | Ad network ad name | Ad network |
| ad-network-ad-id | String | Ad network ad ID | Ad network |
| ip | String | - The IP address of the device sending the postback.<br>- iPv4 and IPv6 addresses supported.<br>- Example: `"ip":"198.51.100.1"` | Ad network |
| timestamp | String | - Time the ad network received the SKAN postback. A 10-digit epoch UNIX timestamp. [Optional] 13-digit epoch timestamp permitted.<br>- Example: August 4, 2020, 07:25 UTC translates to `"timestamp": "1596525944"` | Ad network |
| fidelity-type | Integer | - Differentiate between [ad presentation](https://developer.apple.com/documentation/storekit/SKAdnetwork/receiving_ad_attributions) options that affect attribution. Indicated using the values 0 and1 as follows: <br> - View-though ads (0)<br> - Storekit-rendered ads (1)<br>- Mandatory field starting SKAN V2.2 | SKAN postback (V2.2+) |
| did-win | Boolean | - Used to distinguish between campaigns [contributing or attributed](https://developer.apple.com/documentation/storekit/SKAdnetwork/SKAdnetwork_release_notes/SKAdnetwork_version_3_0_release_notes) with the install. <br>- If true, the campaign is attributed for bringing the install.<br>- If false, the campaign is recognized as contributing to the install | SKAN postback (V3.0+) |
| ad-network-source-app-id | String | Populate with the _publisher ID_ that you associate with the app publishing the ad. This is usually the ID you allocated to the publisher, and not the ID generated by Apple. | Ad network |
| postback-sequence-index | Integer | - Only for SKAN 4+<br>- Value represents the sequence number (SKAN window), either`0`,`1`, or`2`. | SKAN 4.0 postback (iOS 16.2) |
| coarse-conversion-value | String | - Only for SKAN 4+<br>- Value can be`low`,`medium`, or`high`.<br>- For the first postback, only available for tier 1. For the second and third postbacks, available for tiers 1-3. See [Apple documentation](https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows) | SKAN 4.0 postback (iOS 16.2) |
| source-identifier | String | - Only for SKAN 4+<br>- Replaces `campaign-id`<br>- Value can be up to 4 digits.<br>- For the first postback, up to 4 digits are available for tiers 2-3 and 2 digits are available for tiers 0-1. For the second and third postbacks, 2 digits are available for tiers 1-3. For tier 0, there isn't a postback. See [Apple documentation](https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows) | SKAN 4.0 postback (iOS 16.2) |
| source-domain | String | - Only for SKAN 4+<br>- Value represents the source of attributable web ads. Example: `example.com`<br>- Available in web ads only, in the first postback, for tier 3. See [Apple documentation](https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows) | SKAN 4.0 postback (iOS 16.2) |
| creative | String | - Only relevant for SKAN 4+<br>- Available when you use additional digits in the source\_identifier for additional campaign granularity. | Ad network |
| channel | String | - Only relevant for SKAN 4+<br>- Available when you use additional digits in the source\_identifier for additional campaign granularity. | Ad network |

#### **Curl example—enriched SKAN 3 postback**

```bash
curl --location --request POST 'https://skadpostbacks.appsflyer.com/api/postbacks?app_id=id888707074' \
  --header 'Content-type: application/json' \
  --data-raw '{
      "version":"3.0",
      "app-id": 888707086, 
      "ip": "192.0.2.0",
      "ad-network-campaign-name": "skadnetwork_abc_campaign",
      "source-app-id": 888707074,
      "ad-network-id": "abcabcabc.skadnetwork",
      "transaction-id": "68eb3d91-15f5-44ee-9267-25c7655c20b6",
      "redownload": false,
      "attribution-signature": "MDYCGQCsQ4y8d4BlYU9b8Qb9BPWPi+ixk/OiRysCGQDZZ8fpJnuqs9my8iSQVbJO/oU1AXUROYU=",
      "timestamp": "1596525944",
      "ad-network-campaign-id": "222222",
      "conversion-value": 63,
      "campaign-id": 99
  }'
```

#### **Curl example—enriched SKAN 4 postback with fine conversion values**

```bash
curl --location --request POST 'https://skadpostbacks.appsflyer.com/api/postbacks?app_id=id888707074' \
  --header 'Content-type: application/json' \
  --data-raw '{
      "version": "4.0",
      "ad-network-id": "example123.skadnetwork",
      "ad-network-campaign-name": "skadnetwork_abc_campaign",
      "ad-network-campaign-id": "222222",
      "source-identifier": "5239",
      "app-id": 525463029, 
      "transaction-id": "6aafb7a5-0170-41b5-bbe4-fe71dedf1e30",
      "redownload": false,
      "source-app-id": 1234567891,
      "fidelity-type": 1,
      "did-win": true,
      "conversion-value": 63,
      "postback-sequence-index": 0,
      "attribution-signature": "MEUCIGRmSMrqedNu6uaHyhVcifs118R5z/AB6cvRaKrRRHWRAiEAv96ne3dKQ5kJpbsfk4eYiePmrZUU6sQmo+7zfP/1Bxo="
  }'
```

#### **Curl example—enriched SKAN 4 postback with coarse conversion values**

```bash
curl --location --request POST 'https://skadpostbacks.appsflyer.com/api/postbacks?app_id=id888707074' \
  --header 'Content-type: application/json' \
  --data-raw '{
      "version": "4.0",
      "ad-network-id": "example123.skadnetwork",
      "ad-network-campaign-name": "skadnetwork_abc_campaign",
      "ad-network-campaign-id": "222222",
      "source-identifier": "39",
      "app-id": 525463029, 
      "transaction-id": "6aafb7a5-0170-41b5-bbe4-fe71dedf1e31",
      "redownload": false,
      "source-app-id": 1234567891,
      "fidelity-type": 1,
      "did-win": true,
      "coarse-conversion-value": "high",
      "postback-sequence-index": 0,
      "attribution-signature": "MEUCIQD4rX6eh38qEhuUKHdap345UbmlzA7KEZ1bhWZuYM8MJwIgMnyiiZe6heabDkGwOaKBYrUXQhKtF3P/ERHqkR/XpuA="
  }'
```

### Redirect

<Image src="https://files.readme.io/17d4a668cde784a2f823e702e04fc75a2bbbdb483e44d9d10edfad03d865bbb7-360012352758.png" alt="Redirect_us-en__2_.png" />

Using this method, the ad network responds to the device with an HTTP redirect command (307), requesting the device to send the postback directly to AppsFlyer.

The redirect method has the following advantages:

- **Increased advertiser trust:** The MMP acts on behalf of an advertiser. By providing AppsFlyer access to the postback firsthand, advertisers are confident that postbacks are not manipulated in transit.
- **No processing required by the ad network:** Ad networks respond with the redirect command (to the device), thus eliminating the need to process postbacks. In comparison, the enrich and forward method requires that ad networks consume the postback, enrich it with additional parameters, and finally forward it to AppsFlyer.

#### **Implementation**

1. Configure your server to respond with an HTTP 307 response redirecting the postback to [_https://skadredirect.appsflyer.com/api/redirects_](https://skadredirect.appsflyer.com/api/redirects)
2. Append query params that contain campaign details using the query params listed in the table that follows. Regard the sending of your campaign details as mandatory. Campaign details enable us to enrich SKAN data with cost and other campaign data and enable advertisers to effectively optimize campaigns.

**Example redirect URL**

```
https://skadredirect.appsflyer.com/api/redirects?
  &ad-network-campaign-id=243232&ad-network-campaign-name=yarg_campaign_name
  &ad-network-adset-name=dsdsa&creative=examplecreative&channel=channelexample
```

#### Query params for campaign details (not mandatory)

| Query param | Description |
| --- | --- |
| ad-network-name | - Name of the ad network<br>- Example:`ad_network_name=your_network` |
| ad-network-campaign-id | Campaign ID |
| ad-network-campaign-name | Campaign name |
| ad-network-adset-id | Ad set ID |
| ad-network-adset-name | Ad set name |
| ad-network-ad-id | Ad ID |
| ad-network-ad-name | Ad name |
| ad-network-country-code | - The user location (geo) derived by the ad network.<br>- Populate using [ISO 3166 (alpha-2)](https://www.iso.org/iso-3166-country-codes.html) codes.<br>- Example: CN, ZA<br>- Ad networks often derive geo according to a given campaign's target region. <br>- AppsFlyer uses the country code to populate geo-related fields in reports and dashboards. |
| ad-network-source-app-id | Populate with the _publisher ID_ that you associate with the app publishing the ad. This is usually the ID you allocated to the publisher, and not the ID generated by Apple. |
| ip | - The IP address of the device sending the postback.<br>- iPv4 and IPv6 addresses supported.<br>- Example:`"ip":"198.51.100.1"` |
| timestamp | - Time the ad network received the SKAN postback. A 10-digit epoch UNIX timestamp. [Optional] 13-digit epoch timestamp permitted.<br>- Example: August 4, 2020, 07:25 UTC translates to`"timestamp": "1596525944"` |
| creative | - Only relevant for SKAN 4+<br>- Available when you use additional digits in the source\_identifier for additional campaign granularity. |
| channel | - Only relevant for SKAN 4+<br>- Available when you use additional digits in the source\_identifier for additional campaign granularity. |

## Receive data from AppsFlyer

Prior to receiving your first postback, take into consideration the following:

- Ad networks must define the postback end-point and template (reach out to your AppsFlyer Partner Development Manager using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif), to ensure this is in place).
- AppsFlyer sends SKAN postbacks using the same mechanism as with the existing postbacks sent to you.

### Principles

- For each postback sent from the ad network to AppsFlyer, AppsFlyer sends:
  - One install postback. Redownloads are signaled by the redownload parameter.
  - Zero to several in-app event postbacks. The exact number depends on the translation of the conversion value. See [simulated postbacks.](https://support.appsflyer.com/hc/articles/360011502657#simulated-postbacks)
- When you consume postbacks, the same install or event can be attributed by more than one AppsFlyer attribution solution. Use the _attribution\_source_ parameter to differentiate between postback types.

### Postback macros available to ad network partners

| Postback macro (name) | Description | Format and example | Relevant to in-app events only |
| --- | --- | --- | --- |
| site\_id | The app publishing the ad (source app ID) | String: 876534 | |
| install\_time | Estimated by AppsFlyer based on the _updateConversion_ window. Provided as a 10-digit UNIX epoch timestamp or as a human-readable timestamp | - String: 1596119460 <br>- Translates to July 30, 2020, 14:31 UTC. | |
| skadnetwork\_ad\_network\_time | Time the postback was received by the ad network from the iOS device. Reported by the ad network. Provided as a 10-digit UNIX epoch timestamp or as a human-readable timestamp | - String: 1596119460 <br>- Translates to July 30, 2020, 14:31 UTC | |
| skadnetwork\_received\_time | Time AppsFlyer received the postback from the ad network. Provided as a 10-digit UNIX epoch timestamp or as a human-readable timestamp | - String: 1596119460 <br>- Translates to July 30, 2020, 14:31 UTC | |
| event\_name | Event name <br>- af\_skadnetwork\_revenue<br>- af\_login<br>- af\_skadnetwork\_revenue<br>- or as set by the advertiser | String: af\_skadnetwork\_revenue, abc123 | Yes |
| revenue | Revenue amount using the specified currency code | Number: 5, 20, 0.4 | Yes |
| currency | Currency code being the app-specific currency set by the advertiser | String: EUR, USD, ZAR | Yes |
| attribution\_source | The source of the attribution data:<br>SKAdNetwork: SKAdNetwork | String: SKAdNetwork | |
| app\_id | App ID (advertiser app) | String: ID123456790 | |
| country | Install geo (country) determined by the ad network | String: US, UK, ZA | |
| campaign | Campaign name populated using a _d-network-campaign-name_ sent in the postback from the ad network | String: UA\_US\_23+ | |
| campaign\_id | Ad network Campaign ID populated using _ad network-campaign-id_ sent in the postback from the ad network. **Note**: For SKAN 4, this value is always null. | String: 3456745 | |
| redownload | Possible values: true, false<br>When redownload = true, it means the user downloaded the app from the app store again | Boolean: true, false | |
| skadnetwork\_ambiguous\_event<br>(deprecated with SKAN 4+) | Events received during the first 72-hours after an advertiser changes the SKAN settings in the dashboard. Due to the various timers employed by SKAN AppsFlyer can't map the event accurately.<br>- Not available in SKAN 4 and onwards | Boolean: true, false | |
| skadnetwork\_campaign\_id | SKAN campaign ID as provided by the original SKAN postback | 56, 23 | |
| af\_skadnetwork\_nonce | A unique random identifier enabling partners to identify duplicate postbacks | | |
| event\_id | Name/ID of the corresponding event in the ad network platform | | Yes |
| transaction\_id | SKAN postback transaction ID<br>**Note**: The advertiser must explicitly allow us to share the transaction\_id with you. Ask the advertiser to do so in the [**Integration**](https://support.appsflyer.com/hc/articles/4410395957521#integration-tab) tab. | | |
| ad\_network\_adset\_id | Added to the iOS postback by the ad network | String | |
| ad\_network\_adset\_name | Added to the iOS postback by the ad network | String | |
| ad\_network\_ad\_name | Added to the iOS postback by the ad network | String | |
| ad\_network\_ad\_id | Added to the iOS postback by the ad network | String | |
| SKAN\_min\_event\_counter | See note (1) | Integer | Yes |
| SKAN\_max\_event\_counter | See note (1) | Integer | Yes |
| SKAN\_min\_time\_post-install | See note (2) | Integer | Yes |
| SKAN\_max\_time\_post-install | See note (2) | Integer | Yes |
| SKAN\_min\_event\_revenue | See note (3) | Real number | Yes |
| SKAN\_max\_event\_revenue | See note (3) | Real number | Yes |
| fidelity-type | Differentiate between [ad presentation](https://developer.apple.com/documentation/storekit/SKAdnetwork/receiving_ad_attributions) options that affect attribution. Indicated using the values 0 and1 as follows: <br>- View-though ads (0)<br>- Storekit-rendered ads (1) | Integer | |
| skad\_af\_attribution\_flag | Used to indicate if the user was attributed by AppsFlyer using the [Single Source of Truth mechanism](https://support.appsflyer.com/hc/articles/4410634145425#attribution-flag-field). | Boolean | |
| skad\_postback\_sequence\_index | - Value represents the SKAN window, either`0`,`1`, or`2`.<br>- For SKAN 3 the value is`0` | Integer | |
| skad\_coarse\_conversion\_value | - Value can be`low`,`medium`, or`high`.<br>- For SKAN 3 the value is`null`. | String | |
| skad\_source\_identifier | - Value can be up to 4 digits.<br>- For SKAN 3 the value is`null`. | String | |
| skad\_source\_domain | - Value represents the source of attributable web ads.<br>- For SKAN 3 the value is`null`. | String | |
| ad\_network\_creative | - Value is based on data enrichment received from the ad network.<br>- For SKAN 3 the value is `null`. | String | |
| ad\_network\_channel | - Only relevant for SKAN 4+<br>- Available when you use additional digits in the source\_identifier for additional campaign granularity. | String | |
| Notes:<br>1. **Event occurrences**: The number of event occurrences is calculated using the following formula:<br> <br> `[round up (SKAN_min_event_counter+SKAN_max_event_counter) / 2]`<br> <br> Note! The value must be rounded up to the nearest integer.<br>- Example:<br> - A. If min=0 and max=1 the number of events is 1.<br> - B. If min=0 and max =10 the number of events is 5.<br>- **Determine install time**: For advertisers implementing custom conversion, AppsFlyer calculates install time as the postback arrival time - 48h - average (min\_time\_post\_install + max\_time\_post\_install). Ad networks don't need to make use of these macros. <br>- **Determine revenue**: AppsFlyer uses these values to determine the revenue of an event by calculating the average of min and max. Ad networks don't need to make use of these macros. | | | | |

### SKAN postback examples

**Example of an install SKAN postback sent by AppsFlyer**

```
http://YourCompanyDomain.com/event?site_id=(publisher-id)&install_time=(timestamp)
  &skan_ad_network_time=(timestamp)
  &skan_af_received_time=(timestamp)
  &attribution_source=skadnetwork
  &app_id=(id123456789)&country=(ZA)&campaign=(campaign-name)
  &campaign_id=(campaign-id)&SKAN_ambiguous_event=(boolean)
&redownload=(boolean)
&af_SKAN_nonce=(uuid)
```

**Example of an in-app SKAN postback sent by AppsFlyer**

```
http://YourCompanyDomain.com/event?site_id=(publisher-id)&install_time=(timestamp)
  &skan_ad_network_time=(timestamp)
  &skan_af_received_time=(timestamp)&revenue=(value)
  &currency=(code)&event_name=(event-name)&attribution_source=skadnetwork
  &app_id=(id123456789)&country=(ZA)&campaign=(campaign-name)
  &campaign_id=(campaign-id)&SKAN_ambiguous_event=(boolean)
&redownload=(boolean)
&af_SKAN_nonce=(uuid)
```

## Integration testing

To validate the integration with AppsFlyer, use either or both of the following methods.

- Real SKAN postbacks: based on actual SKAN traffic received by the network
- Simulated postbacks: based on AppsFlyer test apps

**To receive real SKAN postbacks from iOS devices, the ad network completes the following:**

- [Register with Apple](https://developer.apple.com/documentation/storekit/SKAdnetwork/registering_an_ad_network)
- [Sign ads with a SKAdNetwork signature](https://developer.apple.com/documentation/storekit/skadnetwork/generating_the_signature_to_validate_storekit-rendered_ads).
- Publisher app: [Add the network ID to the info.plist file](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app) and [call the loadProduct](https://developer.apple.com/documentation/storekit/SKAdnetwork/generating_the_signature_to_validate_an_installation) function upon ad impression.
- Advertised app: Use the most recent AppsFlyer [iOS SDK.](https://support.appsflyer.com/hc/articles/207032126) Versions prior to V6.0.3 aren't supported.

**To receive simulated postbacks:**

- Contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif) and request integration with simulation apps.
- Specify IDs of the apps from the list in the [following section](https://support.appsflyer.com/hc/articles/360011502657#simulated-postbacks).

### Real environment

Using this method, the ad network sends AppsFlyer actual SKAN postbacks from live apps.

#### Testing integration

| Responsibility | Action |
| --- | --- |
| Ad network | Notify AppsFlyer via your partner development manager (or use the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif)) as to your SKAN network ID, provided by Apple. |
| Ad network and AppsFlyer | Agree on a mutual customer (having integrated the most recent AppsFlyer SDK) to use for postback integration verification. |
| Ad network | Send app SKAN postbacks to AppsFlyer, using one of the methods described in this article. |
| AppsFlyer | Send decoded postbacks to the ad network in accordance with the conversion value mapping set by the advertiser. |

#### Test criteria

| Responsibility | Action |
| --- | --- |
| Ad network | Notify AppsFlyer as to the quantity of SKAN postbacks sent during a specified period for the agreed mutual customer. |
| AppsFlyer | Verify the count of postbacks received versus the count sent by the ad network. |
| AppsFlyer | Share with the ad network the count of postbacks sent to the network for a given app broken down by type:<br>- Install/redownload postbacks<br>- In-app postbacks.<br>Note: If you use the same endpoint for probabilistic postbacks, ensure that you filter using _attribution\_source=skadnetwork_ to distinguish SKAN Network postbacks from other postbacks. |

### Simulated postbacks

- Using this method, the ad network sends AppsFlyer preprepared postbacks to AppsFlyer test apps, as detailed in the table below. AppsFlyer replies with decoded postbacks to the ad network.
- Each test app has a different conversion value mapping, as detailed in the table.

| App ID | Conversion mode | Instructions |
| --- | --- | --- |
| id888707085 | Revenue, in $1 units<br>Expected results: | 1. In the **Integration** tab, enable **in-app events postbacks**. <br>2. Select event name _af\_SKAN\_revenue_ and map to your event identifier.<br>3. Save configuration.<br>4. In a postback, send conversion value = 7.<br>5. AppsFlyer responds with:<br> - Install postback<br> - af\_SKAN\_revenue postback with value of $7 |
| id888707086 | Conversion, including the in-app events:<br>- af\_level\_complete<br>- af\_login<br>- af\_SKAN\_revenue<br>- af\_register<br>- af\_subscription<br>- af\_custom\_event | 1. In the **Integration** tab, enable **in-app events postbacks**. <br>2. Select each of the in-app events listed and map it to your event identifier. <br>3. Save configuration.<br>4. In a postback, send conversion value = 63.<br>5. AppsFlyer responds with:<br> - Install postback<br> - af\_level\_complete postback<br> - af\_login postback<br> - af\_SKAN\_revenue postback<br> - af\_register postback<br> - af\_subscription postback<br> - af\_custom\_event postback |
| id888707087 | Engagement, measured using af\_skad\_revenue event | 1. In the **Integration** tab, enable **in-app events postbacks**. <br>2. Map the event name _af\_skad\_revenue_ and to your event identifier.<br>3. **Save** configuration.<br>4. In a postback, send conversion value = 3.<br>5. AppsFlyer responds with:<br> - Install postback<br> - 3 postbacks of af\_skad\_revenue event |

#### Integration steps

| Responsibility | Action |
| --- | --- |
| Ad network | Configure your SKAN network ID (provided by Apple) and SKAN postback template on the [postback management platform](https://support.appsflyer.com/hc/articles/360018512658). For queries and assistance, contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif). |
| Ad network | 1. [Activate the test apps](https://support.appsflyer.com/hc/articles/360020713538).<br>2. For each app complete the instructions column in the previous table. <br>3. Send simulated postbacks, using the test apps listed in the preceding table. Considerations when sending simulated postbacks:<br> - Set the app\_id and conversion value as listed in the preceding table. <br> - Since Ad networks can't generate Apple compatible signatures, the simulated postbacks don't have to include the signature fields. AppsFlyer will not verify them for simulated postbacks.<br> - Ad networks send the postback using either the POST or REDIRECT approach. |
| AppsFlyer | Responds with the decoded postbacks to the endpoint designated by the ad network during integration |

#### Test criteria

| Responsibility | Action |
| --- | --- |
| AppsFlyer | Process the postback and sends postbacks to the ad network. |
| Ad network | - Ad network receives and decodes the translated postbacks.<br>- In-app postbacks sent by AppsFlyer match the expected flows. For example, conversion value 3 for app ID888707087, the ad network receives 3 postbacks of _af\_SKAN\_revenue_ event. |

## Clarifications

Clarifications relating to mandatory fields, enrichment, certification, and more.

### FAQ

<Accordion title="Are the enrichment fields mandatory?">

For the present, we will process the postback even if it is missing one or more of the following enrichment parameters. Consider that the information is required for the following reasons: 
- **Ad network campaign ID**: If we have cost integration with you then this is reported using your campaign ID. 
- **Ad network campaign name**: Many advertisers relate to the campaign name and not the campaign number. 
- **IP address**: Required for geo resolution. 
- **Timestamp**: Assists us to attribute the install to the correct date.

</Accordion>

<Accordion title="Can we send either our campaign ID, or our campaign name, but not both?">

See the previous answer. Consider populating both ID and name with the same value.

</Accordion>

<Accordion title="We are using Enrich and Forward. Can we add key-value pairs that are not in the AppsFlyer specification?">

Yes, you can. We will process the postback and disregard the extra information provided that the attribution signature is valid.

</Accordion>

<Accordion title="Are the SKAN postback templates distinct from the existing postback templates?">

Yes. The flow and structure differ.

</Accordion>

<Accordion title="Will we receive a SKAN postback and a probabilistic/deterministic modeling postback related to the same install, meaning duplicate reporting of the same install?">

Yes. For each case, we record an install attributed to you, irrespective of method, we will send you a postback.
Use _attribution\_source_ to differentiate SKAN postbacks.

</Accordion>

<Accordion title="Are we required to process the postback from AppsFlyer?">

No. Consider, that best practice is to optimize campaigns according to user-quality reported via the postback.

</Accordion>

<Accordion title="Are we expected to call AppsFlyer attribution links or is it sufficient to send the postback with the SKAN payload and enriched data?">

It is sufficient to send us the SKAN payload and enriched data.

</Accordion>

<Accordion title="What is required for us to be certified in the AppsFlyer dashboard as a SKAN integrated partner?">

- Complete integration using one of the methods listed in this article
- Send us postbacks of apps using AppsFlyer as their attribution partner

</Accordion>

<Accordion title="How does the limit of 100 SKAN campaign IDs impact me?">

The 1-100 limit relates to the way you sign and number your campaigns in Apple. It means that at any time, you can have 100 simultaneous unique campaigns. We allow you to enrich the postback with your actual campaign name and ID. Meaning you map the SKAN campaign ID to your actual campaign IDs in use at the time the postback is received. Doing so means that the 100 ID limit does not restrict the number of campaigns that you measure in AppsFlyer provided of course that you don't have more than 100 simultaneous campaigns for a given app.

</Accordion>
---
title: Apply Aggregated Advanced Privacy framework
excerpt: >-
  Advertisers use the Aggregated Advanced Privacy (AAP) framework to control
  which attribution data is made available to partners and ad networks via the
  AppsFlyer platform.
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2021-03-15T11:32:31Z'
  edited_at: '2026-06-11T10:21:55Z'
  id: 360018515798
  locale: en-us
  section: Preserve user privacy
  section_id: 6551440878097
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360018515798-Apply-Aggregated-Advanced-Privacy-framework
---
## Aggregated Advanced Privacy (AAP) framework

The AppsFlyer Aggregated Advanced Privacy (AAP) framework prevents tracking across apps and websites owned by different companies, and the ability to uniquely identify a user or device. AAP utilizes the Apple App Tracking Transparency privacy levels as a minimum benchmark for its privacy-preserving thresholds.

The framework enables advertisers to control the availability of user-level attribution data via the AppsFlyer platform.

When AAP is on, user-level attribution data for users running iOS 14.5+ who have not granted ATT consent will not be available to advertisers or partners. **Note**: Even when AAP is off, user-level data cannot be used to uniquely identify a device.

AAP has no impact on the availability of aggregated attribution data and analytics reports to advertisers and partners.

### AAP-impacted features

If AAP is on, the raw data is affected, and some fields are restricted or unavailable. This affects data provided by the following tools:

* Data Locker
* Raw data Pull API
* Push API
* Dashboard export page
* Postbacks to networks
* [Get conversion data (GCD) API](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking) in the context of the client-side user-level data API.

Data availability is affected when AAP is on as follows:

* **Attribution data and fraud (Protect360):** [Some attribution fields are restricted or not available.](/docs/about-raw-data-identifier-restrictions)
* **Click, impression, and blocked clicks (fraud) data:** [User and device-related identifiers](/docs/about-raw-data-identifier-restrictions#identifier-restriction) aren't available.
* **Deferred deep linking**: If you implement deferred deep linking in paid media, use the [unified deep linking API (UDL).](https://dev.appsflyer.com/hc/docs/unifieddeeplink) The legacy API, which uses GCD, can't be used in the context of non-consenting users. In the case of owned media, deferred deep linking for owned media is supported via GCD and the most recent deferred deep linking API.

## Data availability principles in Aggregated Advanced Privacy

When AAP applies to a given user's data, data availability depends on that user's ATT status and the media source bringing the user.

**Definitions:**

* **User-level attribution data:** Data records containing device-level identifiers tied to attribution at the user level
* **Limited attribution data for advertisers:**
  * Available: Device-level identifiers. (IDFA is available if user consent is given.)
  * Unavailable: Attribution parameters received via publisher attribution link (for example, `pid` and `c`). [List of fields restricted and unavailable to advertisers](/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields) AKA restricted media source.
* **Limited attribution data for partners:**
  * Available: Aggregated campaign details.
  * Unavailable: User-level data that can help identify the user such as AppsFlyer ID, Custom data, Customer user ID (CUID), Click ID, IDFA, IDFV, User-agent, and IP address.

The terms defined are used in the figure and sections that follow to describe the data available to advertisers and partners.

![Advanced Privacy Framework - Advertisers (4).png](https://files.readme.io/0291fe2eea5f6efc41f2338824a0017be3e265f502e0d3999d52ac87b1ee7719-35847850634897.png)

Advanced Privacy behaves differently when served on the web and the af\_media\_type=web or af\_media\_type=app parameter must be used. See [here](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns) for more information.

### Paid and owned media data availability

<div id="paid-media" />

<Accordion title="Paid media">

Paid media includes mobile ad networks with integrations in the AppsFlyer platform with whom advertisers run campaigns.

#### Paid media data availability by ATT status

<table><thead><tr><th rowspan="2">Media type</th><th colspan="2">ATT status</th><th colspan="2">Data available to:</th></tr><tr><th>Publisher app</th><th>Advertiser app</th><th>Advertiser</th><th>Ad network</th></tr></thead><tbody><tr><td rowspan="4">App</td><td>Authorized</td><td>Authorized</td><td>User-level attribution data</td><td>User-level attribution data</td></tr><tr><td>Not authorized</td><td>Authorized</td><td>Limited attribution data for advertisers </td><td>Limited attribution data for partners</td></tr><tr><td>Authorized</td><td>Not authorized</td><td>Limited attribution data for advertisers </td><td>Limited attribution data for partners</td></tr><tr><td>Not authorized</td><td>Not authorized</td><td>Limited attribution data for advertisers </td><td>Limited attribution data for partners</td></tr><tr><td> </td><td colspan="4"> </td></tr><tr><td rowspan="2"><p>Web</p></td><td>N/A</td><td>Authorized</td><td>User-level attribution data</td><td>User-level attribution data</td></tr><tr><td>N/A</td><td>Not authorized</td><td>Limited attribution data for advertisers </td><td>Limited attribution data for partners</td></tr></tbody></table>

</Accordion>

<div id="owned-media" />

<Accordion title="Owned media">

The Apple AppTrackingTransparency framework applies only to data collected from different companies. Therefore, owned media user-level attribution data is available to advertisers irrespective of the user ATT consent status.

Owned media includes digital marketing campaigns used by advertisers to reach customers. This includes email campaigns, cross-promotions, push notifications, and so on. In AppsFlyer, campaigns using ad networks aren't regarded as owned media.

</Accordion>

## Controlling Advanced Aggregated Privacy

<div id="aap-central-switch" />

<Accordion title="Aggregated Advanced Privacy (AAP)—app-level toggle">

The AAP is an app-level toggle that controls the Advanced Privacy settings for all partners of the selected app. The AAP toggle is located on the **App Settings** page. When the AAP toggle is on, the **Advanced Privacy** toggles for all partners of the selected app are automatically turned on and can't be modified. When off, advertisers can go to each partner integration individually and turn on **Advanced Privacy**.

![AAPcontrol.png](https://files.readme.io/ddc8140ada9278eab447ecdfa4d88c56e07a0ed54b10b71de1cc2352f9590d40-35847850639121.png)

#### AAP enabled

* Aggregated attribution is available. This includes, for example, Overview dashboards and reporting tools such as Cohort and the Master API.
* [Advanced Privacy partner toggles](#partner-advanced-privacy-switch) are turned on and cannot be modified. Note! They are locked in position.
* The data customers may make available to advertisers and partners is limited to aggregated data only, as defined in the [previous section](/docs/apply-aggregated-advanced-privacy-framework#data-availability-principles-in-aggregated-advanced-privacy).

#### AAP disabled

* User-level attribution data is available for advertisers.
* The Advanced Privacy setting per partner can be set individually.

*Before turning AAP off, consider if by doing so you will make user-level attribution data available to third parties and how they will use the data. You should work closely with your legal and other professional advisors in relation to how Apple defines tracking. Nothing stated here is legal advice. It is provided for your information and convenience.*

**To set the Aggregated Advanced Privacy setting**:

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings**.
2. Turn **Aggregated Advanced Privacy** on or off as required.
3. Click **Save**.

</Accordion>

<div id="partner-advanced-privacy-switch" />

<Accordion title="Advanced Privacy (AP)—partner-level toggle">

If AAP is disabled, advertisers can set the Advanced Privacy setting for each ad network individually.

![APControl.png](https://files.readme.io/8e5a005cbadb5665cf255d39d6fa425298510f719b166c2013a2dfe57d4e982b-35847865312657.png)

**To turn off a partner's Advanced Privacy:**

1. Verify that the central toggle for AAP is off, in the **App Settings** page.
2. From the side menu, select **Collaborate** > **Active Integrations**.
3. Select the ad network.
4. In the **Integration** tab, toggle off **Advanced Privacy.**

**Changing the AAP setting and the impact on the partner's Advanced Privacy setting**

As previously stated, the AAP setting overrides the Advanced Privacy (AP) setting at the partner level. However, if you later turn off AAP (the central toggle), individual partner-level Advanced Privacy settings revert to their prior status. Meaning as follows:

* In the past, you turned AAP off and set some partner AP settings to off.
* Later you turned AAP on. Remember, when AAP is on, it overrides the partner setting and all partners are regarded as being on.
* Now you turn AAP off again. Meaning the individual partner settings apply. So for some partners, the setting is already off.

</Accordion>

## Advanced Aggregated Privacy implications for your partners

<div id="ad-networks" />

<Accordion title="Ad networks">

#### **Postbacks to ad network partners**

[AAP affects ad networks](/docs/advanced-privacy-guide-postback-macros-for-ad-networks) in relation to data shared with them and is aligned with the AAP principles that apply to advertisers in the context of an ad network. Data shared with ad networks is via postbacks which differ between the attributed ad network and the unattributed ad network.

Data sharing rules described apply to a given ad network if either of the following toggles is on:

* AAP: App-level toggle
* AP: Partner-level toggle

#### **Postbacks for attributed ad networks**

In the case of the attributed network the postback type used to share data depends on the user consent status as follows:

* **Consenting users:** Regular postback containing user-level attribution data including identifiers.
* **Non-consenting users:** Advanced Privacy (AP) postback containing limited attribution data. It contains campaign details and no identifiers.
  * **Prerequisite:** For an ad network to get AP postbacks they must have AP integration with AppsFlyer. Without integration, no postback is sent for non-consenting users.
  * **Exception:** For installs attributed to Apple Ads, when an ad network that doesn't support Advanced Privacy sets the install postbacks to **All media sources, including organic**, Apple Ads still sends install postbacks to the ad network regardless of the Advanced Privacy state on the advertiser's side.

The various user consent scenarios and postback types used are illustrated in the figure that follows.

![AAP - Attributed ad networks.png](https://files.readme.io/d776c77115beb4c6b6ada1850077f186aa2feb809a8b69af8cf0ec760cd02b39-35847865314961.png)

Advanced Privacy behaves differently when served on the web and the af\_media\_type=web or af\_media\_type=app parameter must be used. See [here](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns) for more information.

#### **Postbacks for unattributed partners**

Unattributed postbacks are sent to a network when the sending option in the integrated partner's integration tab is set to *all media sources, including organic*and that partner is not attributed to the event as illustrated in the figure that follows.

![InAppEventAll.png](https://files.readme.io/e24037f75b2b82797031eb13d5e063b8c2006812491e69674ff066ac830919f7-35847850644881.png)

The various user consent scenarios and postback type used are illustrated in the flowchart that follows.

![AAP - Unattributed ad networks.png](https://files.readme.io/bb8a5d192e2120f8df90b9be044c0b4abf48c2250f5128fbbce76c60c89718cc-35847850645649.png)

Advanced Privacy behaves differently when served on the web and the af\_media\_type=web or af\_media\_type=app parameter must be used. See [here](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns) for more information.

</Accordion>

<div id="analytics-partners" />

<Accordion title="Analytics partners">

AAP affects analytics partners in relation to data shared with them and is aligned with the AAP principles that apply to advertisers in the context of the analytics partner.  Data shared with the partner is via postbacks.

Data sharing rules described, apply to a given partner if either of the following toggles is on:

* AAP: App-level toggle
* AP: Partner-level toggle

Postbacks containing user-level attribution data including user identifiers are sent for consenting users. No postback is sent in the case of non-consenting users.

The various user consent scenarios and postback type used are illustrated in the figure that follows.

![AAP - Analytics partner.png](https://files.readme.io/4bb77720f9e0be093e325f989987f5b5ba2dba5aa26e2f32df5f1bd5b99161eb-35847865320593.png)

Advanced Privacy behaves differently when served on the web and the af\_media\_type=web or af\_media\_type=app parameter must be used. See [here](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns) for more information.

</Accordion>

<div id="agencies" />

<Accordion title="Agencies">

**Data availability**: The impact of AAP on agencies is similar to that of advertisers. If raw data is available to the agency for a given app and AAP applies to a given user's data, the data is available according to the rules of [limited attribution data for advertisers](/docs/apply-aggregated-advanced-privacy-framework#data-availability-principles-in-aggregated-advanced-privacy).

**Agency changing an ad network's Advanced Privacy setting:**

* If AAP is off, the Advanced Privacy setting of each integrated partner can be set.
* By default, only advertisers can change the Advanced Privacy setting; however, the advertiser can explicitly give the agency permission to set the Advanced Privacy setting of ad networks enabled by the agency.

**Grant an agency permission to set Advanced Privacy**

![agency_advanced_privacy.png](https://files.readme.io/ac4a1aae41e9e39b9759006db84ea14df7495d0a14c02df7dbfb8dd93a2d2c23-35847865322129.png)

**To allow an agency to set Advanced Privacy**:

1. From the side menu, select **Collaborate** > **Active Integrations**.
2. Select the agency.
3. In the **Permissions** tab, turn on **Change the** **Advanced Privacy setting.**
4. Click **Save.**

</Accordion>

> 📘 **See also**
>
> * [Advanced Privacy guide & postback macros for ad networks](/docs/advanced-privacy-guide-postback-macros-for-ad-networks)

<div data-zendesk-anchors="aggregated-advanced-privacy-framework=aggregated-advanced-privacy-aap-framework h_01HDPDE0H3SYFWBHK59HBV2P6N=aggregated-advanced-privacy-aap-framework aapimpacted-features=aap-impacted-features h_01HDPDE0H339BPACN235V70MWW=aap-impacted-features h_01HDPDE0H3QBE60DVBZ1MWNB9N=data-availability-principles-in-aggregated-advanced-privacy h_01HDPDE0H326EXNCQHPVJWXK3H=paid-and-owned-media-data-availability h_01HDPDE0H3TBDSXCNW5Q3E1Q7P=paid-media h_01HDPDE0H3SACYAV19WQD9TCQ3=paid-media-data-availability-by-att-status h_01HDPDE0H4M4XPE1C54K284BGW=owned-media controlling-aap=controlling-advanced-aggregated-privacy h_01HDPDE0H4VQC2DWAV68Q9VDVQ=controlling-advanced-aggregated-privacy h_01HDPDE0H4BHG114REGTWCDBP9=aap-central-switch h_01HDPDE0H4SC810EBK7ZGQ02K0=aap-enabled h_01HKHPGQ1R6HZEXSRTX7ATVWE9=aap-disabled h_01HDPDE0H4FRDXWRCYAWTPZZWE=partner-advanced-privacy-switch 01HKHPEBBFGQ5ZX4J6G50GEN64=advanced-aggregated-privacy-implications-for-your-partners h_01HDPDE0H4PDJ4TC02TED0DB8P=ad-networks h_01HDPDE0H47ENYTWRVFPX0VTZC=postbacks-to-ad-network-partners h_01HDPDE0H4B01YG577QZCG7TA7=postbacks-for-attributed-ad-networks h_01HDPDE0H63ZMV255SN7EKDRMV=postbacks-for-unattributed-partners h_01HDPDE0H67T1XFTEB2N0NN6YN=analytics-partners h_01HDPDE0H6AM91W49W2G2Z94DM=agencies h_01HDPDMX05ZZCAMW4TTWF4M4YN=see-also" />

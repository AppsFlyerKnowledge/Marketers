---
title: About ATT and SKAN
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
  created_at: '2020-08-11T09:19:23Z'
  edited_at: '2026-06-11T08:40:04Z'
  id: 360011890298
  locale: en-us
  section: Attribution scenarios
  section_id: 6551328497041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360011890298-About-ATT-and-SKAN
---
**At a glance**: Starting iOS 14.5, Apple requires that you implement and comply with the terms of [AppTrackingTransparency](https://developer.apple.com/documentation/apptrackingtransparency) (ATT). ATT means that *if your app collects data about end-users and shares it with other companies for purposes of tracking across apps and websites,* you must use the ATT consent prompt and get user consent in both the publisher and advertiser app. If you don't track, there is no need to display the prompt.

![iOS14-consent-pre-ATT-enforcement-6522_Cover-image_917x480.jpg](https://files.readme.io/622b57cf6b6b7ad9472b3d072f44d9b451e82fec6b0c918427e39e9e6700602e-360019478118.jpg)

## Attribution measurement in an ATT environment

AppsFlyer provides you with multiple attribution methods giving you a complete range of attribution solutions. The [ATT](/docs/about-att-and-skan#att-principles) consent requirement impacts attribution in the context of paid app-to-app campaigns. As such, advertisers need to use a mix of attribution and reporting solutions.

In the case of paid app-to-app campaigns, [SKAN](/docs/about-att-and-skan#skan-solution-principles) provides deterministic attribution results. Other campaign types like owned media, web-to-app and Apple Ads use AppsFlyer traditional attribution tools. The traditional tools provide long-term LTV measurement, whereas SKAN measures user performance during a short post-install post.

In summary, to obtain a complete picture, use both SKAN and AppsFlyer traditional solutions because they complement one another.

This article provides advertisers with an introduction to SKAN and ATT. It is intended for advertisers familiar with the AppsFlyer platform.

<div id="skan-solution-principles" />

<Accordion title="SKAN Solution principles">

AppsFlyer provides aggregated iOS attribution results using SKAN postbacks from iOS. These postbacks are sent by iOS to ad networks who then forward them to AppsFlyer. The postbacks contain anonymized attribution records enriched with a conversion value (CV) set by the advertiser. The CV is a measure of user quality during an initial post-install window.

The AppsFlyer [SKAN Solution](/docs/skadnetwork-skan-solution-guide) provides advertisers with:

* SKAN data in dashboards and reports derived by aggregating postbacks from all ad networks enriched with other data points like cost.
* The ability to control, via the AppsFlyer Conversion Studio, what the CV measures without the need to make changes to the app code. The CV can be used to measure revenue, engagements, or conversion events.

**SKAN limitations**

* **Campaigns:** Doesn't support cross-promotion campaigns and mobile web-assisted installs.
* **Measurement period:** The effective measurement period is limited to a few days.

**SKAN flow**

![SKAN_flow_-_Affinity_diagram_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. Advertiser sets SKAN measurement settings in the AppsFlyer Conversion Studio.
2. The user opens the app for the first time.
3. During each window, AppsFlyer sets the CV based on user actions and the defined CV schema.
4. After the window closes, iOS sends the postback to the ad network and a postback copy to AppsFlyer. The postback arrives with some delay:
   * For SKAN 4 measurement window 1: 24-48 hours
   * For SKAN 4 measurement windows 2-3: 24-144 hours
   * For SKAN 3: 24-48 hours after the most recent increase in the CV value.
5. Postback copies sent directly from the iOS device to AppsFlyer are forwarded to the advertiser's defined endpoint. See [send SKAN postback copies to AppsFlyer.](/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15)
6. Ad network forwards enriched postback to AppsFlyer or SRN communicates postback data by API.
7. AppsFlyer validates and decodes the CV. Decoded data is recorded and attributed before being made available in AppsFlyer via dashboards, reports, and APIs.

</Accordion>

<div id="att-principles" />

<Accordion title="ATT principles">

The ATT prompt provides advertisers with a way to get explicit user consent allowing the advertisers to collect and share their data. Starting iOS 14.5 IDFA is available only if the user consent via the prompt.

Both publisher and advertiser apps display the prompt. If the user provides consent in both apps, it means that the user agrees to be *tracked,* and advertisers are permitted by Apple to track the user between apps owned by different companies.

**Setting ATT**

ATT is set to one of the values listed in the table that follows. Initially, iOS sets ATT to not determined or restricted.

Consider that use of the consent prompt to convert a user from *not determined* to *authorized* is optional. But, if you don't display the prompt, you can't get *authorization.*

| ATT value | Consent  <br />(IDFA available) | Remarks |
| --- | --- | --- |
| Restricted | No | <ul><li>Determined by Apple based on user age and other criteria. Can't be changed by the device user.</li><li>The prompt can't be displayed to these users.</li></ul> |
| Not determined (until iOS 14.4) | Yes | Default value |
| Not determined<br /><br />(starting iOS 14.5) | No | Default value |
| Denied | No | Occurs if any of the following are true:<ul><li>Set after displaying the prompt</li><li>The user turned off *Allow Apps to Request to Track* (master switch at the device level)</li><li>Before installing iOS 14 on the device, LAT was on</li></ul> |
| Authorized | Yes | Set after displaying the prompt |

**ATT implications**

With ATT in place, IDFA is available only when users grant consent. As a result, advertisers benefit from using both aggregated attribution methods and user-level reporting where consent is given. [AppsFlyer attribution models](/docs/appsflyer-attribution-model).

Attribution-related data for an app comes from a number of sources. The identifier available and used by each differ. Most data displays using the traditional attribution tools. However, for installs attributed using SKAN, reporting is via the SKAN dashboard.

</Accordion>

<div id="which-dashboard-has-the-install" />

<Accordion title="Which dashboard has the install?">

In iOS 14 an install can be attributed to both the traditional and SKAN dashboards. In addition, depending on the media source context it can be attributed as organic in one dashboard and as non-organic in the other.

</Accordion>

## iOS attribution and privacy: important knowledge

#### iOS attribution, SKAN, and privacy articles and links

| Area | Article | Special interest: FAQ, discrepancies, comparisons |
| --- | --- | --- |
| SKAN | [SKAN raw data fields](/docs/skan-raw-data-reports) | Additional raw data SKAN fields supporting did\_win and SKAN 3.0 |
| SKAN | [SKAN solution](/docs/skadnetwork-skan-solution-guide) | <ul><li>[Timing from app install to dashboard update](/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update)</li><li>[Organic metrics in the context of SKAN](/docs/skadnetwork-skan-solution-guide#organic-metrics-in-the-context-of-skadnetwork)</li><li>[AppsFlyer attribution versus SKAN attribution](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#appsflyer-attribution-vs-skan-attribution)</li><li>[FAQ SKAN discrepancies](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#faq-skan-discrepancies)</li></ul> |
| SKAN | [SKAN partner interoperability](/docs/skan-interoperation) (article section) | [SKAN integrated partners list](/docs/skan-integrated-partners-list) |
| SKAN | [Meta ads and AppsFlyer SKAN integration](/docs/skadnetwork-skan-interoperation-with-meta-ads) | <ul><li>[Troubleshooting and discrepancies](/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq)</li><li>[Measurement and timing differences](/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook)</li></ul> |
| SKAN | [Snapchat and AppsFlyer SKAN interoperation](/docs/skan-interoperation-with-snapchat) | [Discrepancies guide](/docs/skan-interoperation-with-snapchat#discrepancies-guide) |
| Privacy | [Aggregated Advanced Privacy (AAP)](/docs/apply-aggregated-advanced-privacy-framework) | <ul><li>[AAP impacted features](/docs/apply-aggregated-advanced-privacy-framework#aap-impacted-features)</li></ul> |
| Privacy | [Restricted media sources](/docs/about-raw-data-identifier-restrictions) | [Restricted raw data fields](/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields) |
| iOS 14 | [Nutrition labels—prepare for the App Store review](/docs/preparing-for-the-app-store-review-nutrition-labels) |  |
| iOS 14 | [Configuring ATT in the app](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support) (SDK guidance developers) |  |
| iOS 14 | [About self-reporting networks (SRNs) like Google, Meta ads, and so on](/docs/self-reporting-networks-srns) | [Where are SRN installs reported?](/docs/self-reporting-networks-srns#ios-145-srn-attribution) |
| Billing | [Billing for iOS apps](https://content.appsflyer.com/ios-14-hub/billing/) |  |

<div id="ios-14-impact-on-attribution-and-measurement" />

<Accordion title="IDFA availability impact on attribution and measurement">

#### **Metrics**

Consider that where an IDFA is not available, the following metrics may be affected:

| Metrics | Increase | Decrease | Remarks |
| --- | --- | --- | --- |
| Non-organic vs. organic | Organic | Non-organic |  |
| Reinstalls vs. installs | Installs | Reinstalls |  |
| Retargeting | Organic installs and in-app events | Re-engagements, Re-attributions |  |
| Apple Ads | -- | -- | Unchanged. Attribution works correctly regardless of IDFA availability. |

#### **Deep linking**

Deferred deep linking using the [legacy method of onConversionDataSuccess](https://dev.appsflyer.com/hc/docs/dl_android_gcd_legacy) may not work when an IDFA is not available, since it requires attribution data that may be restricted by privacy settings.

We recommend using [unified deep linking (UDL)](https://dev.appsflyer.com/hc/docs/dl_android_overview). UDL conforms to the iOS 14.5+ privacy standards and only returns parameters relevant to deep linking and deferred deep linking: `deep_link_value` and `deep_link_sub1`. Attribution parameters such as `media_source`, `campaign`, and `af_sub1-5` return null and can’t be used for deep linking purposes.

</Accordion>

## FAQ—iOS attribution and ATT

<div id="what-happens-to-an-app-using-an-sdk-version-before-v6" />

<Accordion title="What happens to an app using an SDK version before V6+?">

For apps using an SDK version earlier than V6.0:

* SKAdNetwork and Apple Ads won't work.
* If you submit the app to the App Store, expect it to be rejected.

For apps using an SDK earlier than V6.10: SKAN 4 won't work.

</Accordion>

<div id="is-it-mandatory-to-display-the-att-prompt" />

<Accordion title="Is it mandatory to display the ATT prompt?">

No. You only need to ask for ATT consent if you want to *track* a user, collect IDFA, or both.

</Accordion>

## FAQ—SKAN

<div id="how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4" />

<Accordion title="How do I know when I’ll receive postbacks and if they’ll be SKAN 3 or SKAN 4?">

The type of SKAN postback you receive is determined by a variety of factors, including what mode you use in Conversion Studio, what ad network you use, and what iOS version your users have.

These factors impact:

* Postback version: Either SKAN 3 or SKAN 4. [Learn more](/docs/skadnetwork-skan-solution-guide#principles-and-flow)
* Window 1 (AW): For SKAN 4, this is 48 hours. For SKAN 3, this is based on the activity window. Note: If Conversion Studio isn’t SKAN 4, but the ad network signature is, the window is either based on the activity window or 48 hours, whichever is lower.
* Postback delay: Hours after install when the SKAN postback arrives. This is dependent on when the window closes. [Learn more](/docs/skadnetwork-skan-solution-guide?query=skan%20faq#timing-from-app-install-until-dashboard-and-reports-update)
* Rolling timer: For SKAN 3, the activity window can be extended up to 63 days; the postback only arrives after the window closes.

The following flowchart explains this in further detail.

![SKAN_4_matrix_-_Page_8__1_.png](https://files.readme.io/0dbd4cae34d9f9fed80dbe835485789dab75d46dbb38de055f454d01efb97350-13756140934545.png)

</Accordion>

<div id="in-skan-am-i-limited-to-100-campaign-ids-per-ad-network" />

<Accordion title="In SKAN, am I limited to a certain number of source identifiers/campaign IDs per ad network?">

Yes. Previously the limit was 100 campaign IDs. However, from SKAN 4, campaign IDs are called hierarchical source identifiers, and the limit is 10,000. The source identifier is a 4-digit integer.

Ad networks map the SKAN source identifier to their campaign ID.

</Accordion>

<div id="what-is-the-use-case-for-skan-raw-data" />

<Accordion title="What is the use case for SKAN raw data?">

* Use raw data to aggregate dimensions that aren't available via aggregated APIs.
* Easily adjust existing raw data import processes to consume SKAN raw data.

</Accordion>

<div id="why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio" />

<Accordion title="Why don't the conversion values I receive match my configuration in AppsFlyer Conversion Studio?">

Usually, this is because of another SDK in your app that has the ability to set conversion values, and that conflicts with your AppsFlyer SDK and the conversion values you have configured in AppsFlyer. Make sure you don't have another SDK that sets conversion values integrated into your app.

</Accordion>

<div id="why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports" />

<Accordion title="Why doesn’t the aggregate data in my SKAN dashboard match the raw data numbers in my SKAN Data Locker reports?">

Often, this discrepancy is due to looking at Data Locker reports in the wrong place. Data from Google can take up to 13 days to be received. And in raw data reports, data is written on the day it’s received, not cumulatively. Therefore, to get correct metrics for installs relating to a specific date, you need to look at all reports 13 days after that date, as well.

Example: In the June 12 report, it displays 100 installs from Google that occurred on June 11. In the June 24 report, it says 100 MORE installs occurred on June 11. You’ll need to look at all reports for the past 13 days (from June 12-June 24) and aggregate based on the install time or ad network timestamp to get an accurate reading of the 200 total installs that occurred on June 11.

</Accordion>

> 📘 **See also**
>
> * [AppsFlyer getting started step-by-step](/docs/getting-started-onboarding-for-marketers#step-3-attribution-setup)

<div data-zendesk-anchors="h_01HE0C8YXSXSX003X0671Z97KZ=attribution-measurement-in-an-att-environment h_01HE0C8YXSCA8M57F1RG4CJ7HK=skan-solution-principles h_01HE0C8YXSSCTQJAPDE27FB1H8=att-principles h_01HE0C8YXS0BFA2M16D1Q2PQYW=which-dashboard-has-the-install ios-14-important-knowledge=ios-attribution-and-privacy-important-knowledge h_01HE0C8YXS3BH109DF1Y1KNK5P=ios-attribution-and-privacy-important-knowledge ios-14-and-skan-articles-and-links=ios-attribution-skan-and-privacy-articles-and-links h_01HE0C8YXSPZKBWXC51Z2636R0=ios-attribution-skan-and-privacy-articles-and-links h_01HE0C8YXSTCVA8YYR4BQVHVXS=ios-14-impact-on-attribution-and-measurement h_01HE0C8YXSJMYN81FKPCA8ATK7=metrics h_01HE0C8YXS6ADG1SQCMVP0W69B=deep-linking faq%E2%80%94ios-14=faqios-attribution-and-att h_01HE0C8YXSV9VSK1NPG9RCTQW1=faqios-attribution-and-att h_01HE0C8YXS1FFYQJ8YZXP9W9ZV=what-happens-to-an-app-using-an-sdk-version-before-v6 h_01HE0C8YXSKA0325YJSXV81ZB9=is-it-mandatory-to-display-the-att-prompt faq%E2%80%94skan=faqskan h_01HE0C8YXSQKH8ER1Q5VS6Z0NM=faqskan how-do-i-know-when-i%E2%80%99ll-receive-postbacks-and-if-they%E2%80%99ll-be-skan-3-or-skan-4=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXS44YXAN2DV2ZR03GE=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXSCWM892QH0N7YQ8HP=in-skan-am-i-limited-to-100-campaign-ids-per-ad-network h_01HE0C8YXSSWHV45M6P7SQGCRD=what-is-the-use-case-for-skan-raw-data h_01HE0C8YXS8GJKFC23S1R9TWW0=why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio why-doesn%E2%80%99t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE0C8YXS1VW1T50ARJE0MP62=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE7SNR02VQDKG55QP06ECNAR=see-also" />

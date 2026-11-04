---
title: Meta ads FAQ
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-09T10:04:49Z'
  edited_at: '2026-05-06T12:58:42Z'
  id: 4410472805649
  locale: en-us
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/en-us/articles/4410472805649-Meta-ads-FAQ
---
> **At a glance:** Find answers to frequently asked questions about using Meta ads in AppsFlyer.

<div id="meta-ads-faq" />

## Meta ads FAQ

<div id="i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard" />

<Accordion title="I don't see Meta ads campaign clicks in AppsFlyer's dashboard">

By default, Meta ads sends only the conversion and engagement data. However, you can easily also start getting <Anchor target="_blank" href="/marketers/docs/meta-ads-integration-setup#cost-clicks-and-impressions">clicks, impressions, and cost data for your Meta ads campaigns</Anchor>.

</Accordion>

<div id="can-appsflyer-show-the-campaign-level-and-ad-groups" />

<Accordion title="Can AppsFlyer show the campaign level and ad groups?">

Yes. In fact, AppsFlyer shows you also the single ad level, so you have 3 levels of drill down with Meta ads, campaigns >> ad groups >> ads.

</Accordion>

<div id="is-facebook-data-shown-in-realtime" />

<Accordion title="Is Meta ads data shown in real-time?">

Yes, all installs and subsequent in-app events are shown in real-time. However, the clicks, impressions, and cost data AppsFlyer gets in an aggregated form from Meta ads arrives periodically every few hours.

</Accordion>

<div id="when-can-i-see-a-new-campaigns-data-on-appsflyer" />

<Accordion title="When can I see a new campaign's data on AppsFlyer?">

To see data from new ads, ad sets and campaigns on Meta ads they must generate at least one install.

For example, a new ad has generated 100 clicks with no installs, and is not shown on the AppsFlyer dashboard and data. Another ad only has 1 click and 1 install, but is displayed on AppsFlyer.

</Accordion>

<div id="how-can-i-get-more-installs-from-facebook" />

<Accordion title="How can I get more installs from Meta ads?">

If you have activated retargeting for Meta ads you can get up to 100% more installs in your user acquisition campaigns, for free!  
How? Read <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns#what-is-srn-mistargeting">here</Anchor>.

</Accordion>

<div id="how-can-i-get-device-level" />

<Accordion title="How can I get device-level Android install data using the Google Play and Meta Install Referrers?">

<div id="google-play-install-referrer-api" />

#### Google Play Install Referrer API

The Google Play Install Referrer API allows advertisers to retrieve attribution data such as campaign information from installs that originated from the Google Play Store. This API must be <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">integrated into your app</Anchor> and works by passing referrer data when the app is first opened after installation. Attribution fields will be available in AppsFlyer raw data reports with the match type `gp_referrer` once the required decryption key is submitted.

<div id="meta-install-referrer" />

#### Meta Install Referrer

The Meta install referrer provides additional campaign metadata stored locally on the device. This is accessible via the [AppsFlyer SDK](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer). It complements the Google Play Install Referrer by enabling richer data, including both click and impression data, and potentially spans multiple sessions. Attribution via Meta install referrer uses match types like `fb_referrer` (Facebook) and `ig_referrer` (Instagram).

<div id="campaign-attribution-fields" />

#### Campaign Attribution Fields

* Ad ID
* Ad name
* Adset ID
* Adset name
* Campaign ID
* Campaign name
* Account ID
* Channel

<div id="sdk-and-setup-notes" />

#### SDK and Setup Notes

* AppsFlyer SDK version 5.4.0+ is required for the Google Play referrer data.
* Meta referrer support depends on correct SDK configuration. See <Anchor target="_blank" href="/marketers/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">this bulletin</Anchor> for implementation details.

<div id="submitting-the-decryption-key" />

#### Submitting the Decryption Key

Both referrer types require a decryption key from your Meta developer account. You only need to provide this key once per app. The steps include:

1. Log into your Meta developer portal.
2. Navigate to **My Apps** and select the relevant app.
3. Go to **Settings > Basic** and locate the "Install Referrer decryption key."
4. In AppsFlyer, navigate to **Collaborate > Active Integrations > Meta ads**.
5. Paste the key into the **Install Referrer Decryption Key** field and save.

</Accordion>

<div id="do-you-make-facebook-raw-data-available-to-agencies" />

<Accordion title="Do you make Meta ads raw data available to agencies?">

No. We are not allowed to provide Meta ads raw data to agencies, this is because agencies are regarded as third parties in terms of Meta terms of services.

</Accordion>

<div id="i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports" />

<Accordion title="I don't see Meta ads raw data in the installation and in-app events reports">

By default, Meta Ads does not allow the distribution of device-level data with unrestricted attribution information. However, if you accept the Meta Advanced Mobile Measurement (AMM) Terms, you will be able to access device-level attribution data for Meta ads without restriction. See <Anchor target="_blank" href="/marketers/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data">Enable Meta ads device-level data.</Anchor>

</Accordion>

<div id="any-specific-columns-for-facebook-in-appsflyers-performance-reports" />

<Accordion title="Any specific columns for Meta ads in AppsFlyer's performance reports?">

Yes. The performance reports have static column structures in any combination of selected media sources, which present information down to the campaign level.  
However, when you download performance reports ONLY for Meta ads, AppsFlyer adds 4 columns to them, which present information down to the single ad level! The added columns are Adset Name, Adset ID, Adgroup (i.e. single ad) Name and Adgroup ID.

[![](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)

</Accordion>

<div id="can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer" />

<Accordion title="Can I work with Meta campaign management partners and measure performance with AppsFlyer?">

Yes. AppsFlyer is integrated with dozens of Meta campaign management partners. These partners can be set up for attribution on the Active Integrations page in the dashboard.

For details about setting up attribution with Meta campaign management partners, click <Anchor target="_blank" href="/marketers/docs/configuring-meta-campaign-management-partners">here</Anchor>.

</Accordion>

<div id="what-should-i-do-when-i-receive-the-following-warning" />

<Accordion title="What should I do when I receive the following warning?">

[![](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)

* Verify the Facebook App ID and check if you have any geo or age restrictions on their Facebook App ID.
* If attribution is already working, this indicates that app is already publicly available in the Meta Developer Portal and you can safely ignore this error message.

</Accordion>

<div id="what-happens-with-different-lookback-windows-than-on-facebook" />

<Accordion title="What happens with different lookback windows than on Meta ads?">

7-day click and 1-day view are the maximum and default lookback windows for Meta ads.

Configuring shorter windows on AppsFlyer decreases Meta ad attribution on AppsFlyer. Conversely, configuring longer windows on AppsFlyer results in more attribution on AppsFlyer’s side than on Meta’s.

Therefore, to minimize discrepancies, the recommendation is to configure the Meta ads lookback windows in AppsFlyer to 7 day clicks and 1 day views.

</Accordion>

<div id="what-are-the-facebook-api-parameters" />

<Accordion title="What are the Meta API parameters?">

In some AppsFlyer APIs, Meta parameters have different names than displayed on the dashboard, for backward compatibility reasons. Consult the table below:

| Conversion data | AppsFlyer raw data | Meta |
| --- | --- | --- |
| campaign | campaign | campaign\_group\_name |
| campaign\_id | Campaign ID | campaign\_group\_id |
| adgroup | Ad | adgroup\_name |
| adgroup\_id | Ad ID | adgroup\_id |
| adset | Adset | campaign\_name |
| adset\_id | Adset ID | campaign\_id |
| agency | Partner | N/A |
| is\_fb | Media Source | is\_fb |
| af\_channel | Channel | publisher\_platform |
| af\_siteid | Site ID | publisher\_platform when `publisher_platform` value is not equal to `facebook` else `null`. |

</Accordion>

<div id="how-long-do-you-keep-facebook-s-userlevel-data" />

<Accordion title="How long do you keep Meta ads user-level data?">

Meta ads requires attribution providers to delete its user-level data 6 months after the install. This means that the events performed by these users 6 months after they install the app are counted as organic.  
Past aggregate data remains the same.  
This is relevant for all Meta ads channels (Facebook app, Instagram, Messenger, and AudienceNetwork).

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-meta-ads" />

<Accordion title="Are iOS Universal Links and Android App Links supported in Meta Ads?">

iOS Universal Links and Android App Links are supported and can be used in Meta ads. For more information, see the <Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">Meta help center</Anchor>.

* For Static ads (non-catalog) iOS Universal Links and Android App Links are only supported in campaigns where **App** is selected as a destination.
* For Dynamic ads, iOS Universal Links, Android App Links, and URI schemes can be used as outlined [here](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads).

**Note:** iOS Universal Links and Android App Links are only supported in paid ads.

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content" />

<Accordion title="Are iOS Universal links and Android App Links supported in Meta’s Non-paid content?">

iOS Universal Links and Android App Links are only supported in paid ads. In non-paid social apps content, it may be necessary to set up a Social app landing page or URI scheme to redirect or deep link users.

</Accordion>

<div id="aem-attribution-is-not-working" />

<Accordion title="AEM attribution is not working">

If the **Advanced Data Sharing** toggle is turned on and you’re not receiving attribution with Meta, check if the shared events meet Meta's eligibility criteria. See [Meta documentation](https://www.facebook.com/business/help/716239976391518?id=1877298665783613).

</Accordion>

<div id="can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads" />

<Accordion title="Can OneLink links be used for app opening and deep linking in dynamic product ads?">

Yes. OneLink links with App Links, Universal Links, or URI schemes configured are supported in dynamic product ads. You can use OneLink links in your data feed for catalogs used in dynamic ads under the **applink.ios\_url** and **applink.android\_url** fields.

</Accordion>

<div id="conversion-events-are-not-sent-to-meta-ads" />

<Accordion title="Conversion events are not sent to Meta Ads">

You might be on a Zero package which doesn't include attribution.

</Accordion>

<div id="can-i-use-get" />

<Accordion title="Can I use Get Conversion Data (GCD) to retrieve conversion data from Meta?">

**Yes.** You can continue to use **GCD** to retrieve conversion data from Meta, depending on your app setup and AMM agreement status:

* **If the Facebook SDK is integrated into your app:**

  As explained in <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns#deferred-deep-linking">the Deferred deep linking (DDL) documentation</Anchor>, you can retrieve the DDL data and use it via GCD.
* **If the Facebook SDK isn’t integrated into your app:**

  You can still retrieve **campaign, ad set, and ad names** via GCD—provided that <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions#meta-ads">Advanced Mobile Measurement (AMM) is signed</Anchor>. In this case, you can use these values to apply your own **custom deep-linking logic**.

<div id="note" />

> 📘 **Note**
>
> Meta’s data-sharing policies can affect the level of detail available through GCD. Ensure that AMM is signed to maximize available campaign-level data.

</Accordion>

<div id="meta-ads-cost-faq" />

## Meta ads cost FAQ

<div id="getting-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="Getting Meta ads cost data in the AppsFlyer dashboard">

AppsFlyer gets spend data (including clicks and impressions) from Meta ads campaigns if one or more installs occurred during the previous 7 days.

If a Meta ads campaign engages with multiple platforms (Android, iOS, desktop, etc.) the cost in the Dashboard is platform-specific and is calculated by Meta ads.

<Anchor target="_blank" href="/marketers/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Getting Meta ads cost including clicks and impressions</Anchor>.

</Accordion>

<div id="facebook-cost-example" />

<Accordion title="Meta ads cost example">

An advertiser runs campaigns using Meta ads. In AppsFlyer the advertiser sees the following:

![mceclip2.png](https://files.readme.io/a1aa5847db5c0b873b34b1d4de43ade7d4109608371e05a84342122e56d0ce08-4411031032081.png)

The cost information is provided by Meta ads to AppsFlyer. The number of **installs** is calculated by AppsFlyer using AppsFlyer attribution rules. As a result, the eCPI calculated by Meta ads and AppsFlyer usually differs.

</Accordion>

<div id="i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="I can't see old Meta ads cost data in the AppsFlyer dashboard">

Upon performing the first Meta ads admin login described above AppsFlyer receives Meta ads cost data up to 7 days retroactively for existing campaigns. Cost data from beforehand isn't available.

In subsequent syncs, AppsFlyer also receives data from the last 7 days. This means that cost, clicks, and impressions data is collected for all campaigns, which have at least 1 conversion during the last 7 days.

</Accordion>

<div id="can-i-stop-cost-data-sync" />

<Accordion title="Can I stop cost data sync?">

To stop cost data sync with Meta ads, <Anchor target="_blank" href="https://www.facebook.com/help/405094243235242">remove AppsFlyer from your Business Integration in your Meta ads account</Anchor>.

</Accordion>

<div id="cost-data-was-fine-for-a-few-months-but-it-stopped-displaying" />

<Accordion title="Cost data was fine for a few months, but it stopped displaying">

Meta ads may reset this permission to get the cost data every few months. If you notice the cost data stopped appearing on the dashboard please repeat the Meta ads admin login steps again.

If the Meta ads admin user changes their Meta ads password the login steps must be repeated as well.

</Accordion>

<div id="i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer" />

<Accordion title="I clicked on my Facebook ad 5 minutes ago. Why don't I see the click in AppsFlyer?">

AppsFlyer gets aggregated clicks, impressions, and cost data from Meta ads periodically every few hours. Therefore, it may take a few hours before these actions are displayed on AppsFlyer's dashboard.

</Accordion>

<div id="can-i-get-raw-data-on-clicks-and-impressions-from-facebook" />

<Accordion title="Can I get raw data on clicks and impressions from Meta ads?">

As AppsFlyer gets only aggregated click and impression data from Meta ads, the entire set of raw clicks and impressions is not available. The only raw clicks and impressions available in raw reports are those that resulted in installs.

</Accordion>

<div id="are-there-limitations-of-facebook-cost-data-by-geo" />

<Accordion title="Are there limitations of Meta ads cost data by geo?">

If you filter by Geo on AppsFlyer's dashboard, you can see the summary and breakdown of the Meta ads cost data.

This data is available only for "Mobile App Install Campaigns" on Meta ads.

In addition, cost by Geo data is only available for single platform campaigns. This means campaigns that have an Android-targeted ad set, and an iOS-targeted ad set, can't have Geo-specific cost data. **To get the full cost data, dedicate a campaign to each platform**.

</Accordion>

<div id="what-are-the-limitations-of-facebook-cost-data-in-master-api" />

<Accordion title="What are the limitations of Meta ads cost data in Master API?">

Meta ads doesn’t support grouping of cost data by Geo and Channel simultaneously in <Anchor target="_blank" href="/marketers/docs/master-api-user-acquisition-metrics-via-api">Master API reports</Anchor>.

To create a report with complete cost data, group it by only one of these dimensions.

</Accordion>

<div id="the-total-cost-doesnt-match" />

<Accordion title="Why doesn't the total cost shown in Meta and AppsFlyer match?">

There are differences between Meta ads and AppsFlyer attribution models. These differences may lead to discrepancies with Meta ads cost data:

* **Meta ads cross-device attribution:** this might sometimes cause issues where a campaign for one platform (iOS/Android) shows an install with its cost for another platform.
* **Meta ads non-mobile campaigns:** in these campaigns, like the Meta ads link click campaigns, desktop users may eventually install mobile apps. For these cross-device campaigns, AppsFlyer does not show cost. However, if the link click was performed by the same device that installed the app, cost data is received.  
  For example, a Facebook user clicks on an ad leading to the advertiser's landing page on a desktop computer. A week later the same Facebook user installs the advertiser's iOS app on an iPhone device. While the install is attributed and displayed on AppsFlyer's dashboard, the cost of this cross-platform install is not.
* **Campaigns with 0 results in the last 7 days** - AppsFlyer syncs the cost only for campaigns that had installs/conversions in the past 7 days. If Meta ads cost was just set, campaigns which were inactive for more than 7 days beforehand will not show cost.
* **Deleted and archived ads**: Cost for deleted and archived ads isn't reported by Meta to AppsFlyer, but this cost is reflected in the Meta dashboard. This can cause a discrepancy between Meta and AppsFlter reports when comparing data at the campaign level.

</Accordion>

<div id="why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical" />

<Accordion title="Why is the AppsFlyer calculation for eCPI different from the cost calculated by Meta ads, while the total cost is identical?">

The Cost Per Install is calculated by dividing the total cost with the number of installs. Since <Anchor target="_blank" href="/marketers/docs/meta-ads-discrepancies">AppsFlyer counts installs differently from Meta ads</Anchor> the eCPI will usually differ between the two.

</Accordion>

<div id="why-doesnt-cost-data-include-data-from-all-campaigns" />

<Accordion title="Why doesn't cost data include data from all campaigns?">

When the user performing the Meta ads login (described above) doesn't have access to some of the running campaigns, the result is campaigns that are displayed on AppsFlyer's dashboard but lack some of the cost, clicks, and impression data.

**Note:** Although several Meta ads users may have permission to run campaigns in the Meta Business Manager, only one is required to perform the Meta ads login.

</Accordion>

<div id="is-facebook-cost-data-displayed-for-retargeting-campaigns" />

<Accordion title="Is Meta ads cost data displayed for retargeting campaigns?">

Cost and ROI data for retargeting campaigns can be found in the **unified** view of <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard">Cohort reports</Anchor>.

</Accordion>

<div id="why-does-the-facebook-cost-configuration-window-close-before-login" />

<Accordion title="Why does the Meta ads cost configuration window close before login?">

If you're signed in to Meta ads on the same browser that you're performing the configuration, the window automatically connects to Meta ads using those credentials. If access has already been granted to AppsFlyer, then there's nothing to do and so the window closes.

</Accordion>

<div id="why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store" />

<Accordion title="Why is there a discrepancy in cost data for apps in the Amazon app store?">

Contrary to AppsFlyer's data, Meta ads doesn't distinguish between cost data from Android apps as opposed to Amazon apps—which are Android-based. Therefore, the cost data of Amazon users may be attributed to campaigns targeting other Android users instead of the original Amazon campaigns.

</Accordion>

<div id="how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked" />

<Accordion title="How to connect cost data of a new Meta ad account while my old account is linked?">

If you want to switch to a new ad account but your Meta ads cost is already linked via AppsFlyer with your old ad account, you need to disconnect the ad account via Meta ads and then connect the new ad account in AppsFlyer.

1. On Meta ads, go to **Settings** > **Business Integration**.
2. On the **Active** tab, remove the AppsFlyer integration.  

   [![](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)
3. Go to AppsFlyer dashboard and connect the cost with the new ad account.

</Accordion>

<div id="facebook-sdk-faq" />

## Facebook SDK FAQ

<div id="who-needs-facebooks-sdk" />

<Accordion title="Who needs the Facebook SDK?">

Your app may already have the Facebook SDK integrated into it, before the AppsFlyer SDK. Even if not, you may wonder whether you really need Facebook SDK in addition to AppsFlyer SDK. And if you do, can the two co-exist without duplicate reporting?

Your app does not require the Facebook SDK for the following:

* **User acquisition**: Generally, the AppsFlyer SDK takes care of all mobile user acquisition attribution purposes of your Meta ads users, including engagements, installs, sessions, and post-install events.
* **Deep linking**: To open the app when the link is clicked and deep link users to a specific page or activity in the app, you can use OneLink, without the Facebook SDK. You can use iOS Universal Links, Android App Links, and URI schemes to do this. For more information, see the<Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595"> Meta help center</Anchor>.  

  **Note:**   
  For Static ads (non-catalog) iOS Universal Links and Android App Links are only supported in campaigns where **App** is selected as a destination.  
  For example, if you set up an awareness campaign in Meta - as this campaign does not allow **App** to be selected as a destination, iOS Universal Links and Android App Links are not supported.  

  For Dynamic ads, iOS Universal Links, Android App Links, and URI schemes can be used as outlined [here](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads).  

  Meta ads scrapes the OneLink URL, and uses it to create a Meta ads App Link that opens the app, and deep links the user.

Your app requires the Facebook SDK in addition to the AppsFlyer SDK for the following:

* **Deferred deep linking**:  
  Meta Ads DDL values aren’t available in Conversion data. Clients must coordinate with Meta, and typically the Facebook SDK is required to access this data.
* **Dynamic Product Ads campaigns data**: You can only get data for Dynamic Product Ads from the Facebook SDK.
* **Other Meta ads features**: You may need Facebook SDK for reasons unrelated to attribution such as authentication, ad monetization, social sharing, user invites, etc.

<div id="note-1" />

> 📘 **Note**
>
> The above information and recommendations regarding deep linking and deferred deep linking are based on thorough testing we conducted using the Meta ads available demo/preview tools, which uses a different mechanism than live ads.

</Accordion>

<div id="avoiding-duplicates-with-facebook-sdk" />

<Accordion title="Avoiding duplicates with Facebook SDK">

If you have <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#faq_593792547454717">both the AppsFlyer and Facebook SDKs in your app</Anchor>, installs and in-app events are reported via the Facebook SDK, and then via postbacks to Meta ads servers through AppsFlyer. How can you avoid this duplicate reporting?

* **For installs**, Meta de-duplicates installs. This means there's **no duplication** and each install is counted only once.
* **For In-app events**, Meta ads doesn't de-duplicate in-app events, potentially leading to double counting and inaccurate reporting of in-app events. To avoid such duplication in Meta ads, consider either of the following:
  * Don't configure events in the Facebook SDK
  * For Android, disable the <Anchor target="_blank" href="/marketers/docs/meta-ads-in-app-event-mapping">Meta ads in-app events mapping</Anchor> from AppsFlyer.  
    Note that to enable SKAN attribution for iOS 14.5+, you'll need to <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-interoperation-with-meta-ads#in-app-event-mapping">map in-app events to Meta ads</Anchor>.

</Accordion>

<div id="meta-ads-attribution-faq" />

## Meta ads attribution FAQ

<div id="attributing-agencies-with-facebook" />

<Accordion title="Attributing agencies with Meta ads">

Agencies and Meta campaign management partners can run and attribute Meta ads campaigns on behalf of advertisers on AppsFlyer, or even alongside the advertisers' own Meta ads campaigns. In order for the agency campaigns to be attributed to the agency, the campaign name MUST begin with the agency's name.

Note that for iOS 14 users, only **one** agency can run campaigns for a specific ad account. See more about <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-interoperation-with-meta-ads#skan-interoperability-appsflyer---meta-ads">Meta ads and AppsFlyer SKAdNetwork interoperability</Anchor>.

For more details about agencies and Meta ads install attribution please <Anchor target="_blank" href="/partners/docs/about-agency-accounts#srn-configurations">go here</Anchor>.

In addition, **agencies can't alter Meta ads lookback windows and retargeting control**. Rather, they need to ask the advertiser to perform these changes if they're needed.

Besides, agencies can't modify any in-app event postbacks sent to Meta ads. The reason for that is a Meta ads requirement to receive information about all installs, including those that are not attributed to it (and therefore may not be brought by the agency).

The image below shows all settings that need to be configured by the advertiser for the agency to be able to manage its Meta ads campaigns:

[![advertiser-vs-agency-facebook-int-new.png](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)

</Accordion>

<div id="attribution-for-facebook-for-outofstore-android-apps" />

<Accordion title="Attribution for Meta ads for out-of-store Android apps">

Meta ads doesn't allow creating mobile apps install campaigns for Android apps that are in out-of-store markets, for example, Baidu.

However, you can advertise and record installs for out-of-store apps on Meta ads following these instructions:

1. The developer has to prepare a separate APK for each out-of-store market you use to advertise your app on. More <Anchor target="_blank" href="/marketers/docs/set-up-multi-store-android-attribution">details here</Anchor>.
2. Create a **Traffic** or **Conversions** campaign on Meta ads, with mobile attribution enabled, which sends leads to a landing page.
3. The landing page should include a **Download App** button, which directly links to the out-of-store market where the APK exists.
4. The lead clicks on the button and is redirected to the out-of-store market. After completing the installation AppsFlyer attributes the user to Meta ads, via its MMP API.

<div id="note-2" />

> 📘 **Note**
>
> The same solution applies to apps in Google Play and the App store, which <Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">require a landing page</Anchor> prior to the redirection to the market.

For specific instructions on attribution for apps in Amazon, click <Anchor target="_blank" href="/marketers/docs/set-up-multi-store-android-attribution#driving-users-to-the-amazon-app-store-from-facebook">here</Anchor>.

</Accordion>

<div id="what-is-facebook-android-and-ios-crossattribution" />

<Accordion title="What is a Meta ads Android and iOS cross-attribution?">

Meta ads identifies users based on their Meta ads account. Some users have both iOS and Android devices associated with the same Meta ads account.

If such a user clicks or views an ad for your app on their Android device, but install the app on their iOS device, Meta ads considers themselves as having generated the install. As a result, an Android Campaign name appears on your iOS dashboard.

<div id="example" />

> 📄 **Example**
>
> Andrew Josef is busy on his Android device. While using it, he clicks on an Android Meta campaign ad for an app called **Bubbles**. He does not download the app.
>
> One day later, Andrew Josef decides to download the **Bubbles** app organically on his iOS device and launches it.
>
> In this situation, AppsFlyer attribution takes the Android Meta ads campaign from Meta ads and presents it in the iOS Dashboard where Andrew Josef downloaded and launched it from.

</Accordion>

<div id="what-are-facebook-ads-channels" />

<Accordion title="What are Meta ads channels?">

With Meta ads you can see data broken down not only by campaigns, ad sets and ads, but also by Meta ads channels (called Placements):

* **Facebook** - users from the Facebook app
* **Instagram** - users from the Instagram app
* **Messenger** - users from the Facebook Messenger app
* **AudienceNetwork** - users from other apps that belong to or are affiliated with Meta ads
* **Threads** - users from the Threads app
* **WhatsApp** - users from the WhatsApp app

Use this data to compare the quality of users that you get from the different channels.

![Facebook_channels.png](https://files.readme.io/f6b51baf3056f42ee32ac9709b1e4b3661580ce6148acfa36fc2bad102e7bfd8-4411036713745.png)

</Accordion>

<div data-zendesk-anchors="facebook-ads-faq=meta-ads-faq h_01HD1JTW2EP1MY3DD9136E9CHC=meta-ads-faq h_01HD1JTW2EN36V9SHH11283Y3A=i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard h_01HD1JTW2EJE0K034KSV8B3WZQ=can-appsflyer-show-the-campaign-level-and-ad-groups h_01HD1JTW2EFKCJMNBXBK2C55DN=is-facebook-data-shown-in-realtime h_01HD1JTW2E4SVC1Z9C3K6XJB2G=when-can-i-see-a-new-campaigns-data-on-appsflyer h_01HD1JTW2ECWSXFKQC1YBP1592=how-can-i-get-more-installs-from-facebook h_01K8B4YFDKKYP25V6NR12CE9RF=how-can-i-get-device-level h_google_play_referrer=google-play-install-referrer-api h_meta_install_referrer=meta-install-referrer h_attribution_fields=campaign-attribution-fields h_sdk_requirements=sdk-and-setup-notes sdk-requirements=sdk-and-setup-notes h_decryption=submitting-the-decryption-key decryption-key=submitting-the-decryption-key h_01HD1JTW2ED762B3K1QS6QC38M=do-you-make-facebook-raw-data-available-to-agencies h_01HD1JTW2EWQGK4QA9W8DFZTMH=i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports h_01HD1JTW2EYSBJ38WNS1HP5MCE=any-specific-columns-for-facebook-in-appsflyers-performance-reports h_01HD1JTW2ETTXQAP7ZSTMVGA8K=can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer h_01HD1JTW2EPY8W5Z84PBWSM86G=what-should-i-do-when-i-receive-the-following-warning h_01HD1JTW2ED2DNPTXAFYJTTGV3=what-happens-with-different-lookback-windows-than-on-facebook h_01HD1JTW2EXF1R0MA91ZSW7QG4=what-are-the-facebook-api-parameters how-long-do-you-keep-facebook%E2%80%99s-userlevel-data=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EPDNSY30J45JB443A=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EN8THFCRNZ0EBQ2M3=are-ios-universal-links-and-android-app-links-supported-in-meta-ads h_01JJVVX9NCSTVQKG2ENTGDRDK9=are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content 01H7YJVNMVBRVTT9HH7KM8P33B=aem-attribution-is-not-working h_01HD1JTW2ETG739TWQVTKPCM2R=can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads h_01JTG2474VHWAD8EK8ASPWZY0W=conversion-events-are-not-sent-to-meta-ads h_01K8B4AKSHSMP18MM0GAAZEQMF=can-i-use-get h_01K8B4AKSH7E8TBEG024NAV1A5=note facebook-ads-cost-faq=meta-ads-cost-faq h_01HD1JTW2EEVD1PDPFW15K45CE=meta-ads-cost-faq h_01HD1JTW2EE0WQ90J431Z8NQ8Q=getting-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2ESVMMPK32W34PA54T=facebook-cost-example h_01HD1JTW2EVFXAET26WK2KSHTV=i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2EJQHKVJF4XHWGVASJ=can-i-stop-cost-data-sync h_01HD1JTW2EYJTA2TRY7EE75KXA=cost-data-was-fine-for-a-few-months-but-it-stopped-displaying h_01HD1JTW2EYXZW2QCMQH5CRFSK=i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer h_01HD1JTW2EYE2ZDNVRT5BCRXZJ=can-i-get-raw-data-on-clicks-and-impressions-from-facebook h_01HD1JTW2EG11RRBYHJ5BMJM5M=are-there-limitations-of-facebook-cost-data-by-geo h_01HD1JTW2E3RMV2TMPNZZ86HG5=what-are-the-limitations-of-facebook-cost-data-in-master-api h_01HD1JTW2EKVSAQ3706NC8JV9M=the-total-cost-doesnt-match h_01HD1JTW2EMJQJHBBB9SRJ6MZN=why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical h_01HD1JTW2E2S79FC9VAHA12X93=why-doesnt-cost-data-include-data-from-all-campaigns h_01HD1JTW2ET6Y2EHG29AQS09NA=is-facebook-cost-data-displayed-for-retargeting-campaigns h_01HD1JTW2EXTS1GDZHN8PAMV8C=why-does-the-facebook-cost-configuration-window-close-before-login h_01HD1JTW2FC0NJK00HZ76SFH30=why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store how-to-connect-cost-data-of%C2%A0a-new-facebook-ad-account-while-my-old-account-is-linked=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked h_01HD1JTW2F401DA2NHBSPTKATB=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked facebook-ads-sdk-faq=facebook-sdk-faq h_01HD1JTW2FPRCVGBF7CG7ZMKXF=facebook-sdk-faq h_01HD1JTW2F03XQSEVTFBW8JCX3=who-needs-facebooks-sdk h_01HD1JTW2FB09HM2CC83GMT901=note-1 h_01HD1JTW2FNNHPZQARZNCCP7ER=avoiding-duplicates-with-facebook-sdk facebook-ads-attribution-faq=meta-ads-attribution-faq h_01HD1JTW2F2JV2BMDS40HFG6K0=meta-ads-attribution-faq h_01HD1JTW2FK1ZTPTA8B8A4N64Z=attributing-agencies-with-facebook h_01HD1JTW2F63AT1NGBY96Y6CCE=attribution-for-facebook-for-outofstore-android-apps h_01HD1JTW2FMKYDHNSM7G182EY0=note-2 h_01HD1JTW2F8JT69CSN04GCZ91V=what-is-facebook-android-and-ios-crossattribution h_01HD1JTW2F5PY7A8T5NMHBZ87B=example h_01HD1JTW2FX3QWC9BKWQ65E5B8=what-are-facebook-ads-channels" />

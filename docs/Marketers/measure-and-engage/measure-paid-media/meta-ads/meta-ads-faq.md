---
title: "Meta ads FAQ"
excerpt: "Find answers to frequently asked questions about using Meta ads, cost data, SDK integration, and attribution in AppsFlyer."
x-zendesk:
  id: 4410472805649
  url: https://support.appsflyer.com/hc/en-us/articles/4410472805649-Meta-ads-FAQ
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Meta ads
  section_id: 6551109855761
  position: 5
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution, Agencies]
  labels: [Facebook, Advertisers, Agencies, facebook, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-11-09T10:04:49Z'
  edited_at: '2026-05-06T12:58:42Z'
---
**At a glance:** Find answers to frequently asked questions about using Meta ads in AppsFlyer.

## Meta ads FAQ

#### I don't see Meta ads campaign clicks in AppsFlyer's dashboard

By default, Meta ads sends only the conversion and engagement data. However, you can easily also start getting [clicks, impressions, and cost data for your Meta ads campaigns](/docs/meta-ads-integration-setup#cost-clicks-and-impressions).

#### Can AppsFlyer show the campaign level and ad groups?

Yes. In fact, AppsFlyer shows you also the single ad level, so you have 3 levels of drill down with Meta ads, campaigns >> ad groups >> ads.

#### Is Meta ads data shown in real-time?

Yes, all installs and subsequent in-app events are shown in real-time. However, the clicks, impressions, and cost data AppsFlyer gets in an aggregated form from Meta ads arrives periodically every few hours.

#### When can I see a new campaign's data on AppsFlyer?

To see data from new ads, ad sets and campaigns on Meta ads they must generate at least one install.

For example, a new ad has generated 100 clicks with no installs, and is not shown on the AppsFlyer dashboard and data. Another ad only has 1 click and 1 install, but is displayed on AppsFlyer.

#### How can I get more installs from Meta ads?

If you have activated retargeting for Meta ads you can get up to 100% more installs in your user acquisition campaigns, for free!  
How? Read [here](/docs/self-reporting-networks-srns#what-is-srn-mistargeting).

#### How can I get device-level Android install data using the Google Play and Meta Install Referrers?

#### Google Play Install Referrer API

The Google Play Install Referrer API allows advertisers to retrieve attribution data such as campaign information from installs that originated from the Google Play Store. This API must be [integrated into your app](/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play) and works by passing referrer data when the app is first opened after installation. Attribution fields will be available in AppsFlyer raw data reports with the match type `gp_referrer` once the required decryption key is submitted.

#### Meta Install Referrer

The Meta install referrer provides additional campaign metadata stored locally on the device. This is accessible via the [AppsFlyer SDK](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer). It complements the Google Play Install Referrer by enabling richer data, including both click and impression data, and potentially spans multiple sessions. Attribution via Meta install referrer uses match types like `fb_referrer` (Facebook) and `ig_referrer` (Instagram).

#### Campaign Attribution Fields

* Ad ID
* Ad name
* Adset ID
* Adset name
* Campaign ID
* Campaign name
* Account ID
* Channel

#### SDK and Setup Notes

* AppsFlyer SDK version 5.4.0+ is required for the Google Play referrer data.
* Meta referrer support depends on correct SDK configuration. See [this bulletin](/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe) for implementation details.

#### Submitting the Decryption Key

Both referrer types require a decryption key from your Meta developer account. You only need to provide this key once per app. The steps include:

1. Log into your Meta developer portal.
2. Navigate to **My Apps** and select the relevant app.
3. Go to **Settings > Basic** and locate the "Install Referrer decryption key."
4. In AppsFlyer, navigate to **Collaborate > Active Integrations > Meta ads**.
5. Paste the key into the **Install Referrer Decryption Key** field and save.

#### Do you make Meta ads raw data available to agencies?

No. We are not allowed to provide Meta ads raw data to agencies, this is because agencies are regarded as third parties in terms of Meta terms of services.

#### I don't see Meta ads raw data in the installation and in-app events reports

By default, Meta Ads does not allow the distribution of device-level data with unrestricted attribution information. However, if you accept the Meta Advanced Mobile Measurement (AMM) Terms, you will be able to access device-level attribution data for Meta ads without restriction. See [Enable Meta ads device-level data.](/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data)

#### Any specific columns for Meta ads in AppsFlyer's performance reports?

Yes. The performance reports have static column structures in any combination of selected media sources, which present information down to the campaign level.  
However, when you download performance reports ONLY for Meta ads, AppsFlyer adds 4 columns to them, which present information down to the single ad level! The added columns are Adset Name, Adset ID, Adgroup (i.e. single ad) Name and Adgroup ID.

[![](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)

#### Can I work with Meta campaign management partners and measure performance with AppsFlyer?

Yes. AppsFlyer is integrated with dozens of Meta campaign management partners. These partners can be set up for attribution on the Active Integrations page in the dashboard.

For details about setting up attribution with Meta campaign management partners, click [here](/docs/configuring-meta-campaign-management-partners).

#### What should I do when I receive the following warning?

[![](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)

* Verify the Facebook App ID and check if you have any geo or age restrictions on their Facebook App ID.
* If attribution is already working, this indicates that app is already publicly available in the Meta Developer Portal and you can safely ignore this error message.

#### What happens with different lookback windows than on Meta ads?

7-day click and 1-day view are the maximum and default lookback windows for Meta ads.

Configuring shorter windows on AppsFlyer decreases Meta ad attribution on AppsFlyer. Conversely, configuring longer windows on AppsFlyer results in more attribution on AppsFlyer’s side than on Meta’s.

Therefore, to minimize discrepancies, the recommendation is to configure the Meta ads lookback windows in AppsFlyer to 7 day clicks and 1 day views.

#### What are the Meta API parameters?

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



#### How long do you keep Meta ads user-level data?

Meta ads requires attribution providers to delete its user-level data 6 months after the install. This means that the events performed by these users 6 months after they install the app are counted as organic.  
Past aggregate data remains the same.  
This is relevant for all Meta ads channels (Facebook app, Instagram, Messenger, and AudienceNetwork).

#### Are iOS Universal Links and Android App Links supported in Meta Ads?

iOS Universal Links and Android App Links are supported and can be used in Meta ads. For more information, see the[Meta help center](https://www.facebook.com/business/help/1627795160837067?id=1858550721111595).

* For Static ads (non-catalog) iOS Universal Links and Android App Links are only supported in campaigns where **App** is selected as a destination.
* For Dynamic ads, iOS Universal Links, Android App Links, and URI schemes can be used as outlined [here](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads).

**Note:** iOS Universal Links and Android App Links are only supported in paid ads.

#### Are iOS Universal links and Android App Links supported in Meta’s Non-paid content?

iOS Universal Links and Android App Links are only supported in paid ads. In non-paid social apps content, it may be necessary to set up a Social app landing page or URI scheme to redirect or deep link users.

#### AEM attribution is not working

If the **Advanced Data Sharing** toggle is turned on and you’re not receiving attribution with Meta, check if the shared events meet Meta's eligibility criteria. See [Meta documentation](https://www.facebook.com/business/help/716239976391518?id=1877298665783613).

#### Can OneLink links be used for app opening and deep linking in dynamic product ads?

Yes. OneLink links with App Links, Universal Links, or URI schemes configured are supported in dynamic product ads. You can use OneLink links in your data feed for catalogs used in dynamic ads under the **applink.ios\_url** and **applink.android\_url** fields**.**

#### Conversion events are not sent to Meta Ads

You might be on a Zero package which doesn't include attribution.

#### Can I use Get Conversion Data (GCD) to retrieve conversion data from Meta?

**Yes.** You can continue to use **GCD** to retrieve conversion data from Meta, depending on your app setup and AMM agreement status:

* **If the Facebook SDK is integrated into your app:**

  As explained in [the Deferred deep linking (DDL) documentation](/docs/self-reporting-networks-srns#deferred-deep-linking), you can retrieve the DDL data and use it via GCD.
* **If the Facebook SDK isn’t integrated into your app:**

  You can still retrieve **campaign, ad set, and ad names** via GCD—provided that [Advanced Mobile Measurement (AMM) is signed](/docs/about-raw-data-identifier-restrictions#meta-ads). In this case, you can use these values to apply your own **custom deep-linking logic**.

> 📘 **Note**
>
> Meta’s data-sharing policies can affect the level of detail available through GCD. Ensure that AMM is signed to maximize available campaign-level data.


## Meta ads cost FAQ

#### Getting Meta ads cost data in the AppsFlyer dashboard

AppsFlyer gets spend data (including clicks and impressions) from Meta ads campaigns if one or more installs occurred during the previous 7 days.

If a Meta ads campaign engages with multiple platforms (Android, iOS, desktop, etc.) the cost in the Dashboard is platform-specific and is calculated by Meta ads.

[Getting Meta ads cost including clicks and impressions](/docs/meta-ads-integration-setup#cost-clicks-and-impressions).

#### Meta ads cost example

An advertiser runs campaigns using Meta ads. In AppsFlyer the advertiser sees the following:

![mceclip2.png](https://files.readme.io/a1aa5847db5c0b873b34b1d4de43ade7d4109608371e05a84342122e56d0ce08-4411031032081.png)

The cost information is provided by Meta ads to AppsFlyer. The number of **installs** is calculated by AppsFlyer using AppsFlyer attribution rules. As a result, the eCPI calculated by Meta ads and AppsFlyer usually differs.

#### I can't see old Meta ads cost data in the AppsFlyer dashboard

Upon performing the first Meta ads admin login described above AppsFlyer receives Meta ads cost data up to 7 days retroactively for existing campaigns. Cost data from beforehand isn't available.

In subsequent syncs, AppsFlyer also receives data from the last 7 days. This means that cost, clicks, and impressions data is collected for all campaigns, which have at least 1 conversion during the last 7 days.

#### Can I stop cost data sync?

To stop cost data sync with Meta ads, [remove AppsFlyer from your Business Integration in your Meta ads account](https://www.facebook.com/help/405094243235242).

#### Cost data was fine for a few months, but it stopped displaying

Meta ads may reset this permission to get the cost data every few months. If you notice the cost data stopped appearing on the dashboard please repeat the Meta ads admin login steps again.

If the Meta ads admin user changes their Meta ads password the login steps must be repeated as well.

#### I clicked on my Facebook ad 5 minutes ago. Why don't I see the click in AppsFlyer?

AppsFlyer gets aggregated clicks, impressions, and cost data from Meta ads periodically every few hours. Therefore, it may take a few hours before these actions are displayed on AppsFlyer's dashboard.

#### Can I get raw data on clicks and impressions from Meta ads?

As AppsFlyer gets only aggregated click and impression data from Meta ads, the entire set of raw clicks and impressions is not available. The only raw clicks and impressions available in raw reports are those that resulted in installs.

#### Are there limitations of Meta ads cost data by geo?

If you filter by Geo on AppsFlyer's dashboard, you can see the summary and breakdown of the Meta ads cost data.

This data is available only for "Mobile App Install Campaigns" on Meta ads.

In addition, cost by Geo data is only available for single platform campaigns. This means campaigns that have an Android-targeted ad set, and an iOS-targeted ad set, can't have Geo-specific cost data. **To get the full cost data, dedicate a campaign to each platform**.

#### What are the limitations of Meta ads cost data in Master API?

Meta ads doesn’t support grouping of cost data by Geo and Channel simultaneously in [Master API reports](/docs/master-api-user-acquisition-metrics-via-api).

To create a report with complete cost data, group it by only one of these dimensions.

#### Why doesn't the total cost shown in Meta and AppsFlyer match?

There are differences between Meta ads and AppsFlyer attribution models. These differences may lead to discrepancies with Meta ads cost data:

* **Meta ads cross-device attribution:** this might sometimes cause issues where a campaign for one platform (iOS/Android) shows an install with its cost for another platform.
* **Meta ads non-mobile campaigns:** in these campaigns, like the Meta ads link click campaigns, desktop users may eventually install mobile apps. For these cross-device campaigns, AppsFlyer does not show cost. However, if the link click was performed by the same device that installed the app, cost data is received.  
  For example, a Facebook user clicks on an ad leading to the advertiser's landing page on a desktop computer. A week later the same Facebook user installs the advertiser's iOS app on an iPhone device. While the install is attributed and displayed on AppsFlyer's dashboard, the cost of this cross-platform install is not.
* **Campaigns with 0 results in the last 7 days** - AppsFlyer syncs the cost only for campaigns that had installs/conversions in the past 7 days. If Meta ads cost was just set, campaigns which were inactive for more than 7 days beforehand will not show cost.
* **Deleted and archived ads**: Cost for deleted and archived ads isn't reported by Meta to AppsFlyer, but this cost is reflected in the Meta dashboard. This can cause a discrepancy between Meta and AppsFlter reports when comparing data at the campaign level.

#### Why is the AppsFlyer calculation for eCPI different from the cost calculated by Meta ads, while the total cost is identical?

The Cost Per Install is calculated by dividing the total cost with the number of installs. Since [AppsFlyer counts installs differently from Meta ads](/docs/meta-ads-discrepancies) the eCPI will usually differ between the two.

#### Why doesn't cost data include data from all campaigns?

When the user performing the Meta ads login (described above) doesn't have access to some of the running campaigns, the result is campaigns that are displayed on AppsFlyer's dashboard but lack some of the cost, clicks, and impression data.

**Note:** Although several Meta ads users may have permission to run campaigns in the Meta Business Manager, only one is required to perform the Meta ads login.

#### Is Meta ads cost data displayed for retargeting campaigns?

Cost and ROI data for retargeting campaigns can be found in the **unified** view of [Cohort reports](/docs/cohort-and-retention-dashboard).

#### Why does the Meta ads cost configuration window close before login?

If you're signed in to Meta ads on the same browser that you're performing the configuration, the window automatically connects to Meta ads using those credentials. If access has already been granted to AppsFlyer, then there's nothing to do and so the window closes.

#### Why is there a discrepancy in cost data for apps in the Amazon app store?

Contrary to AppsFlyer's data, Meta ads doesn't distinguish between cost data from Android apps as opposed to Amazon apps—which are Android-based. Therefore, the cost data of Amazon users may be attributed to campaigns targeting other Android users instead of the original Amazon campaigns.

#### How to connect cost data of a new Meta ad account while my old account is linked?

If you want to switch to a new ad account but your Meta ads cost is already linked via AppsFlyer with your old ad account, you need to disconnect the ad account via Meta ads and then connect the new ad account in AppsFlyer.

1. On Meta ads, go to **Settings** > **Business Integration**.
2. On the **Active** tab, remove the AppsFlyer integration.  
     
   [![](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)
3. Go to AppsFlyer dashboard and connect the cost with the new ad account.

## Facebook SDK FAQ

#### Who needs the Facebook SDK?

Your app may already have the Facebook SDK integrated into it, before the AppsFlyer SDK. Even if not, you may wonder whether you really need Facebook SDK in addition to AppsFlyer SDK. And if you do, can the two co-exist without duplicate reporting?

Your app does not require the Facebook SDK for the following:

* **User acquisition**: Generally, the AppsFlyer SDK takes care of all mobile user acquisition attribution purposes of your Meta ads users, including engagements, installs, sessions, and post-install events.
* **Deep linking**: To open the app when the link is clicked and deep link users to a specific page or activity in the app, you can use OneLink, without the Facebook SDK. You can use iOS Universal Links, Android App Links, and URI schemes to do this. For more information, see the [Meta help center](https://www.facebook.com/business/help/1627795160837067?id=1858550721111595).  
    
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

> 📘 **Note**
>
> The above information and recommendations regarding deep linking and deferred deep linking are based on thorough testing we conducted using the Meta ads available demo/preview tools, which uses a different mechanism than live ads.


#### Avoiding duplicates with Facebook SDK

If you have [both the AppsFlyer and Facebook SDKs in your app](https://developers.facebook.com/docs/app-events/faq#faq_593792547454717), installs and in-app events are reported via the Facebook SDK, and then via postbacks to Meta ads servers through AppsFlyer. How can you avoid this duplicate reporting?

* **For installs**, Meta de-duplicates installs. This means there's **no duplication** and each install is counted only once.
* **For In-app events**, Meta ads doesn't de-duplicate in-app events, potentially leading to double counting and inaccurate reporting of in-app events. To avoid such duplication in Meta ads, consider either of the following:
  * Don't configure events in the Facebook SDK
  * For Android, disable the [Meta ads in-app events mapping](/docs/meta-ads-in-app-event-mapping) from AppsFlyer.  
    Note that to enable SKAN attribution for iOS 14.5+, you'll need to [map in-app events to Meta ads](/docs/skadnetwork-skan-interoperation-with-meta-ads#in-app-event-mapping).

## Meta ads attribution FAQ

#### Attributing agencies with Meta ads

Agencies and Meta campaign management partners can run and attribute Meta ads campaigns on behalf of advertisers on AppsFlyer, or even alongside the advertisers' own Meta ads campaigns. In order for the agency campaigns to be attributed to the agency, the campaign name MUST begin with the agency's name.

Note that for iOS 14 users, only **one** agency can run campaigns for a specific ad account. See more about [Meta ads and AppsFlyer SKAdNetwork interoperability](/docs/skadnetwork-skan-interoperation-with-meta-ads#skan-interoperability-appsflyer-facebook).

For more details about agencies and Meta ads install attribution please [go here](/docs/about-agency-accounts#srn-configurations).

In addition, **agencies can't alter Meta ads lookback windows and retargeting control**. Rather, they need to ask the advertiser to perform these changes if they're needed.

Besides, agencies can't modify any in-app event postbacks sent to Meta ads. The reason for that is a Meta ads requirement to receive information about all installs, including those that are not attributed to it (and therefore may not be brought by the agency).

The image below shows all settings that need to be configured by the advertiser for the agency to be able to manage its Meta ads campaigns:

[![advertiser-vs-agency-facebook-int-new.png](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)

#### Attribution for Meta ads for out-of-store Android apps

Meta ads doesn't allow creating mobile apps install campaigns for Android apps that are in out-of-store markets, for example, Baidu.

However, you can advertise and record installs for out-of-store apps on Meta ads following these instructions:

1. The developer has to prepare a separate APK for each out-of-store market you use to advertise your app on. More [details here](/docs/set-up-multi-store-android-attribution).
2. Create a **Traffic** or **Conversions** campaign on Meta ads, with mobile attribution enabled, which sends leads to a landing page.
3. The landing page should include a **Download App** button, which directly links to the out-of-store market where the APK exists.
4. The lead clicks on the button and is redirected to the out-of-store market. After completing the installation AppsFlyer attributes the user to Meta ads, via its MMP API.

> 📘 **Note**
>
> The same solution applies to apps in Google Play and the App store, which [require a landing page](/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id) prior to the redirection to the market.


For specific instructions on attribution for apps in Amazon, click [here](/docs/set-up-multi-store-android-attribution#driving-users-to-the-amazon-app-store-from-facebook).

#### What is a Meta ads Android and iOS cross-attribution?

Meta ads identifies users based on their Meta ads account. Some users have both iOS and Android devices associated with the same Meta ads account.

If such a user clicks or views an ad for your app on their Android device, but install the app on their iOS device, Meta ads considers themselves as having generated the install. As a result, an Android Campaign name appears on your iOS dashboard.

> 📘 **Example**
>
> Andrew Josef is busy on his Android device. While using it, he clicks on an Android Meta campaign ad for an app called **Bubbles**. He does not download the app.
>
> One day later, Andrew Josef decides to download the **Bubbles** app organically on his iOS device and launches it.
>
> In this situation, AppsFlyer attribution takes the Android Meta ads campaign from Meta ads and presents it in the iOS Dashboard where Andrew Josef downloaded and launched it from.


#### What are Meta ads channels?

With Meta ads you can see data broken down not only by campaigns, ad sets and ads, but also by Meta ads channels (called Placements):

* **Facebook** - users from the Facebook app
* **Instagram** - users from the Instagram app
* **Messenger** - users from the Facebook Messenger app
* **AudienceNetwork** - users from other apps that belong to or are affiliated with Meta ads
* **Threads** - users from the Threads app
* **WhatsApp** - users from the WhatsApp app

Use this data to compare the quality of users that you get from the different channels.

![Facebook_channels.png](https://files.readme.io/f6b51baf3056f42ee32ac9709b1e4b3661580ce6148acfa36fc2bad102e7bfd8-4411036713745.png)
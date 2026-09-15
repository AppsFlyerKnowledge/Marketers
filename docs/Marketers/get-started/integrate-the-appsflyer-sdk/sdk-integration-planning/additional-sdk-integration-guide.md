---
title: "Additional SDK integration guide"
excerpt: "Explore additional AppsFlyer SDK functionalities such as uninstall measurement, user invite attribution, push notifications, and privacy settings."
---
Consider the additional SDK functionalities that are available and work with your developer to implement APIs such as uninstall measurement, user invite attribution, push notifications, and privacy settings.

## Additional attribution methods

Consider these additional attribution methods if you plan to measure TV, uninstalls, or pre-installed apps.

**All platforms**

CTV attribution

Attribute [mobile users to CTV ads](https://support.appsflyer.com/hc/articles/4404083608849-Connected-TV-CTV-gaming-platforms-and-over-the-top-OTT-attribution-overview) aired in specific locations and at specific times.

Measure uninstalls

Measure the uninstall rate of users coming from different sources. Uninstall measurement can help you to analyze and optimize your campaigns according to this significant KPI.

[Learn how to set up uninstall measurement](https://support.appsflyer.com/hc/articles/4408933557137).

**Android only**

Pre-installed apps

In [pre-install campaigns](https://support.appsflyer.com/hc/articles/207032166), app owners contract with device manufacturers (OEMs) to pre-install their apps.

With AppsFlyer, you can easily attribute installs of pre-installed apps. When users launch your app for the first time, AppsFlyer attributes the install to the preload partner as a media source.

## Sessions

Measure user engagement with your app by counting the number of user sessions during a given period.

**All platforms**

Custom time between sessions

By default, at least 5 seconds must pass between two app launches to count as two separate sessions. Learn more about [counting sessions](https://support.appsflyer.com/hc/articles/360000520785-How-does-AppsFlyer-Count-Sessions-#session-reporting-by-the-app-sdk).

> 🚧 Warning
>
> Setting a high value to the custom time between launches can impair APIs that rely on session data, such as deep linking.

**Android only**

Background sessions for utility apps

You can [manually report user sessions](https://support.appsflyer.com/hc/articles/360000520785-How-does-AppsFlyer-Count-Sessions-#session-reporting-by-the-app-sdk). This can be useful for utility apps that run in the background.

## Owned media

Use OneLink to attribute your owned media sources such as websites, social media, and user invites.

**All platforms**

Resolve wrapped deep link URLs

Some 3rd party services, such as [email service providers](https://support.appsflyer.com/hc/articles/360004556077-Email-service-providers-ESPs-explained), wrap links in emails with their own click recording domains. Some even allow you to set your own click recording domains. If OneLink is wrapped in such domains, it might limit its functionality.

To overcome this issue, your developer needs to configure the app using these APIs:

<Tabs>
<Tab title="Android Native">

See [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setresolvedeeplinkurls) in the Android SDK reference

</Tab>
<Tab title="iOS Native">

See [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#resolvedeeplinkurls) in the iOS SDK reference

</Tab>
<Tab title="Unity">

See [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/api#setresolvedeeplinkurls) in the Unity SDK reference

</Tab>
</Tabs>

Record push notifications

AppsFlyer supports the measurement of push notification campaigns from all vendors, including Google Cloud Messaging and Apple push notification services.

[Learn more about push notification measurement](https://support.appsflyer.com/hc/articles/207364076-Measuring-Push-Notification-Re-Engagement-Campaigns).

User invite attribution

Allowing your existing users to invite their friends and contacts as new users to your app can be a key growth factor for your app. With AppsFlyer, you can attribute and record installs that originate from user invites within your app.

[Learn more about user invite attribution](https://support.appsflyer.com/hc/articles/115004480866).

Cross-promotion attribution

Cross-promoting apps can be a major growth factor in driving additional installs for your apps. AppsFlyer enables you to attribute and record installs originating from a cross-promotion from the app the user currently has, to another one of your apps.

[Learn more about cross-promotion attribution](https://support.appsflyer.com/hc/articles/115004481946-Cross-Promotion-Attribution).

Attribute app sessions initiated from owned websites (domains)

App owners that use App Links or Universal Links for deep linking (without OneLink), can configure the SDK to attribute sessions initiated via the domain associated with their app ([Android](https://developer.android.com/studio/write/app-link-indexing#associatesite)/[iOS](https://developer.apple.com/documentation/xcode/supporting-associated-domains?preferredLanguage=occ)).

For example:

- A user searches Google and clicks on your domain, **[www.example.com](https://www.example.com)**.
- If the user doesn’t have the app installed, they are directed to the website ([www.example.com](https://www.example.com)).
- If the user has the app installed on their device, they are deep linked into the app associated with [www.example.com](https://www.example.com). The session is attributed to the media source (`pid` parameter) configured in the SDK.

Developer documentation is available as follows:

- [Android SDK reference](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl)
- [iOS SDK reference](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl)

> 👍 Tip!
>
> [OneLink Smart Script](https://support.appsflyer.com/hc/articles/360001237818-Mobile-web-to-app-attribution-solutions#attribution-solutions) can help app owners convert website visitors to app users.

## User privacy

Review regulations like GDPR and CCPA and your business requirements, and consider which opt-in and opt-out policies to implement.

**All platforms**

Opt-out policy

In some instances, you might need to instruct your developer to set the AppsFlyer SDK to stop or limit data collection, (for example, to comply with GDPR and CCPA regulations). There are different methods to preserve the privacy of users on the SDK. For more information about the various methods, see [Privacy preserving methods in the SDK](https://support.appsflyer.com/hc/articles/360001422989-Privacy-preserving-methods-in-the-SDK) article.

Exclude partners from getting data

In some cases, advertisers may want to stop sharing user-level data with ad networks/partners for specific users. Reasons for this include:

- Privacy policies such as CCPA or GDPR
- User opt-out mechanisms
- Competition with some partners (ad networks, third parties)

Data sharing with partners is controlled via the `setSharingFilterForPartners` method:

<Tabs>
<Tab title="Android native">

See [`setSharingFilterForPartners`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners) in the Android SDK reference

</Tab>
<Tab title="iOS native">

See [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners) in the iOS SDK reference

</Tab>
<Tab title="Unity">

See [`setSharingFilterForPartners`](https://dev.appsflyer.com/hc/docs/api#setsharingfilterforpartners) in the Unity SDK reference

</Tab>
<Tab title="React Native">

See [`setSharingFilterForPartners`](https://dev.appsflyer.com/hc/docs/rn_api#setsharingfilterforpartners) in the React Native SDK reference

</Tab>
</Tabs>

Send consent for DMA compliance

As part of the EU [Digital Marketer Act](https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en) (DMA) legislation, big tech companies must get consent from European end users before using personal data from third-party services for advertising.

To comply with the legislation, Google requires AppsFlyer customers to include specific consent fields when sending events originating from EU end-users to Google. The AppsFlyer SDK (Android - v6.13.0+, iOS - v6.13.1+) can send the necessary consent data with each event to meet this requirement.

The SDK offers two alternative methods for gathering consent data:

- **Through a Consent Management Platform (CMP):** If the app uses a CMP that complies with the [Transparency and Consent Framework (TCF) v2.2 protocol](https://iabeurope.eu/tcf-supporting-resources/), the SDK can automatically retrieve the consent details.

OR

- **Through a dedicated SDK API**: Developers can pass Google's required consent data directly to the SDK using a specific API designed for this purpose.

To implement user consent data collection for DMA compliance see our Dev Hub guides:

<Tabs>
<Tab title="Android Native">

[Send consent for DMA compliance](https://dev.appsflyer.com/hc/docs/android-send-consent-for-dma-compliance)

</Tab>
<Tab title="iOS Native">

[Send consent for DMA compliance](https://dev.appsflyer.com/hc/docs/ios-send-consent-for-dma-compliance)

</Tab>
</Tabs>

**iOS only**

Strict-mode SDK

Use the strict-mode SDK to completely remove IDFA collection functionality and AdSupport framework dependencies (for example, when developing [apps for children](https://developer.apple.com/app-store/review/guidelines/#kids-category)).

If you market apps for children, your developer needs to install the [strict-mode SDK](https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk) instead of the regular SDK. **Note:** IDFV remains available.

Disable ad frameworks

To disable the AdSupport and iAd frameworks, the SDK provides the following setters:

<Tabs>
<Tab title="iOS native">

- [`disableCollectASA`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disablecollectasa) to opt out of Apple Search Ads attributions.
- [`disableAdvertisingIdentifier`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) to not collect Apple `advertisingIdentifier`

</Tab>
<Tab title="Unity">

- [`setDisableCollectIAd`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectiad) to opt out of Apple Search Ads attributions.
- [`setDisableCollectAppleAdSupport`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectappleadsupport) to not collect Apple `advertisingIdentifier`

</Tab>
</Tabs>
---
title: "Send SKAN and AdAttributionKit postback copies directly to AppsFlyer (iOS 15+)"
excerpt: "Starting iOS 15, configure your app to send postback copies to AppsFlyer in addition to sending them to ad networks. Doing so enables AppsFlyer to validate the conversion value (CV) and verify postback integrity. Configure AppsFlyer Push API to forward postback copies to an additional selected endpoint."
x-zendesk:
  id: 4402320969617
  url: https://support.appsflyer.com/hc/en-us/articles/4402320969617-Send-SKAN-and-AdAttributionKit-postback-copies-directly-to-AppsFlyer-iOS-15
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SKAN solution
  section_id: 6552135379985
  position: 6
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, SKAdNetwork (SKAN)]
  labels: [Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-06-08T12:09:25Z'
  edited_at: '2025-12-31T09:07:08Z'
---
> 📘 **Note**
>
> Throughout this article, references to **SKAN** include both **SKAdNetwork** and the latest **AdAttributionKit (AAK)** framework.

## Why send postback copies to AppsFlyer?

* Get all postbacks in one place: Postbacks contain information critical to advertisers—specifically, the CV used to measure user quality. The CV, in postbacks, is neither encrypted nor part of the postback signature. As a result, the CV as reported by the ad network can't be validated and is open to manipulation. AppsFlyer will forward the postback copies using Push API to endpoints defined by you.
  * Mandatory for Apple Ads: forwarding postbacks is required for AA SKAN reporting (iOS 15+).
* View redownload metrics; some ad networks don't share redownload data with AppsFlyer. The postback copy helps complete the picture.
* View publisher app data
* View touch-type engagement

**Note!** AppsFlyer must still receive ad network postbacks as they contain additional data provided by the ad network (for example, campaign name).

## Configure your app to send postback copies to AppsFlyer

According to Apple's documentation, you can set a single SKAN postback endpoint.

**To register the AppsFlyer endpoint:**

1. Ask your iOS developer to [add AppsFlyer](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#sending-skan-postback-copies-to-appsflyer) as a SKAN and AdAttributionKit postback endpoint in the next app version.
2. Submit the iOS app.
3. Postbacks will be sent to AppsFlyer as the new version becomes published (not from TestFlight).
4. You can see the received postbacks in the [postbacks copy report](/docs/skan-raw-data-reports).

> 📘 **Important!**
>
> Apps that don't have SKAN traffic will see the following message even after completing setup: 'Your app isn’t set up to send iOS postback copies (iOS 15+) to AppsFlyer. This is required to assure the integrity of your SKAN measurement.'

## Common misconceptions

> 📘 **Don't believe everything you hear!**
>
> Are these statements true or false?
>
> ![TrueOrFalse.png](https://files.readme.io/77212d5a12ce2af35b0a4c87ca9e58213b4f9fd88c775007793e7abb5aaa3f04-35682597298577.png)
>
> * Advertisers no longer depend on ad networks to get postbacks.
>   * **False.** The advertiser still depends on the ad network to decode significant pieces of data. For example, only the ad network can map the SKAN campaign ID to the campaign name.
> * As soon as I've set an additional endpoint, copies of all postbacks are sent there.
>   * **False.** The additional endpoint feature is only available for devices running iOS 15+. Postback copies aren't sent from devices running earlier versions.

## Traits and limitations

After an app has been configured to send postback copies to AppsFlyer, it may take a couple of days for it to show on the dashboard.

> 📘 **See also**
>
> * [Apple developer](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_an_advertised_app?changes=latest_minor#see-also)
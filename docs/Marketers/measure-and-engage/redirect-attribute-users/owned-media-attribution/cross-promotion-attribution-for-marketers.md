---
title: "Cross-promotion attribution for marketers"
excerpt: "Attribute installs from cross-promotion campaigns that promote your apps on other apps you own."
x-zendesk:
  id: 115004481946
  url: https://support.appsflyer.com/hc/en-us/articles/115004481946-Cross-promotion-attribution-for-marketers
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Owned media attribution
  section_id: 6551214397585
  position: 7
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-asaf-mashiah, Marketers, OneLink]
  labels: [tracking, Advertisers, Cross Promotion, cross-promotion, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2017-08-30T13:26:03Z'
  edited_at: '2024-09-22T10:59:57Z'
---
![CrossPromo_userJourney](https://files.readme.io/4ecc5b536021355247c51f1a19b23d71623da9f9578387622d6c6f0a57d4801b-4404615401489.png)

## About cross-promotion

Cross-promotion campaigns are one of the best ways to promote your existing apps or guide your users to new apps launched by your company. These types of campaigns can result in higher conversion and retention rates compared with most other sources of traffic. Since cross-promotion is advertising on owned media, you can use [device ID matching](/docs/cross-promotion-attribution-for-marketers#attributing-cross-promotion) to deterministically attribute new installs. Cross-promotion attribution is available for all accounts, regardless of your AppsFlyer plan.

The following image shows the promoted app's dashboard with a breakdown of metrics for campaigns running on owned media (**af\_cross\_promotion**) and other media sources. You can see that the number of installs and conversion rate for the cross-promotion campaign are much higher than those for the other media sources.

[![CrossPromo_mediaSource](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)

### How does cross-promotion work?

1. The user is served a cross-promotion ad on an existing app your company owns. The ad is promoting another app also owned by your company. The ad creative can be a banner, video, or any clickable object.
2. [optional] The [SDK records and sends](/docs/cross-promotion-attribution-for-developers) a cross-promotion impression to AppsFlyer.
3. The user clicks on the ad.
4. The SDK records the click and redirects the user to the promoted app's page on the app store. The click recorded by the SDK already includes the device advertising ID.
5. Once the promoted app is installed and launched, the [AppsFlyer dashboard](/docs/cross-promotion-attribution-for-marketers#promoted-app-dashboard) shows the newly acquired user under the media source **af\_cross\_promotion**.
   * To change the media source value, your developer needs to add a custom parameter called `pid` with the value you want. **Note**: For Android, this only works for SDK V6.4.2+.
   * The app driving the install, the source app, appears as a **Site ID** of this media source.
6. The SDK generates an in-app event automatically.  
   The event name for Android is `af_cross_promotion` and for iOS it's `af_cross_promotion_clicked`.

## Attributing cross-promotion

AppsFlyer allows you to use device ID matching as the attribution method for recording and attributing installs that originate from your cross-promotion campaigns. You can attribute both impressions and clicks, enabling you to calculate the [click-through rate](/docs/about-conversion-rates#marketing-funnel-stages-and-conversion-rates-1) or installs/impressions ratio.

The device identifier used for matching depends on the following:

* The user's device and OS version
* The version of the AppsFlyer SDK in the source app

| Device ID matching for cross-promotion | Device/OS version | SDK version | Notes |
| --- | --- | --- | --- |
| IDFA | iOS 9 – 14.4 | V5.0.0+ |  |
| IDFV | iOS 14.5+ | V6.0.2+ | IDFV is collected automatically; no further action is required by the developer. |
| GAID | Android devices with Google Play services |  |  |
| OAID, Android ID, IMEI, Fire ID | Android devices without Google Play services |  |  |

## Setting up cross-promotion

The process of setting up the cross-promotion attribution requires that the marketer and the developer work together to implement additional code in the AppsFlyer SDK.

The flow for the marketer and the developer is as follows:

| Step | Role | Task | Details |
| --- | --- | --- | --- |
| 1 | Marketer | Decide on the existing apps in which to run the cross-promotion campaign. | The source app attributed with the install will appear as the **Site ID** in the promoted app’s dashboard. |
| 2 | Marketer | Determine if you want to add [additional parameters](/docs/about-link-structure-and-parameters) such as lookback window, ad set name, and subscriber parameters. Send these additional parameter names and values to the developer. |  |
| 3 | Developer | Implement the code in the SDK. | Developer documentation is [here](/docs/cross-promotion-attribution-for-developers). |
| 4 | Marketer | In the [promoted app's dashboard](/docs/cross-promotion-attribution-for-marketers#promoted-app-dashboard), view the traffic coming from the cross-promotion campaign and optimize your campaigns accordingly. |  |
| 5 [Optional] | Marketer | Create a [custom dashboard](/docs/cross-promotion-attribution-for-marketers#custom-dashboard) to compare cross-promotion traffic and share data with account users. |  |

## Viewing cross-promotion data

### Promoted app dashboard

The promoted app's dashboard enables you to determine which source apps send the best traffic to the promoted app.

**To compare traffic from source apps:**

1. Go to **Overview**.
2. Select the **af\_cross\_promotion** media source (or your custom media source).
3. Group by **Site ID** to view the list of source apps.[![CrossPromo_SiteID](https://files.readme.io/e057085e90a4a8e56e6769a0af332785488d7757cb5430418e8db6b3cfa67210-4404613179025.png)](https://files.readme.io/e057085e90a4a8e56e6769a0af332785488d7757cb5430418e8db6b3cfa67210-4404613179025.png)

#### Analysis

Viewing the installs, clicks, impressions, and conversion rate data from several existing apps all serving ads for the same promoted app enables you to perform affinity analysis. The source apps (Site IDs) with the best conversion rates have the best affinity with the promoted app, and their users are most likely to install it. Based on these insights, you can optimize your cross-promotion campaigns accordingly.

> 📘 **Example**
>
> You are a marketer of gaming apps for PlayIt Gaming International. You have a number of successful apps, including Bowling (com.playit.bowling) and Golfing (com.playit.golfing). You have just launched a new app called Billiards. You decide to run cross-promotion tests to see how many users actually click on the Billiards ad in one of the existing apps. The campaign runs well on Bowling, with a conversion rate of 7.92%, so you decide to advertise on Golfing as well.
>
> When you check the dashboard you see that the conversion rate for Golfing,18.22%, is much higher than the rate for Bowling, which allows you to determine that there is a greater affinity between Golfing and the promoted app, BIlliards.
>
> [![CrossPromo_conversionRate](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)
>
> Based on these insights, you could optimize your campaign as follows:
>
> * Run a full-scale cross-promotion campaign on Golfing.
> * Start to [attribute impressions](/docs/measure-view-through-engagements#view-through-attribution-flow) in addition to clicks. Since you initially set up your campaign to measure only clicks, installs from users that see the ad without clicking and then install later are counted as organic installs instead of non-organic. This means you don't yet have a complete picture of the campaign performance for each source app.

### Custom dashboard

The promoted app's dashboard is great for getting a picture of which source apps are driving the best traffic. But what about if you want to evaluate the performance of a single existing app being used to promote multiple apps? This is where a custom dashboard can do exactly what you need.

A [custom dashboard](/docs/custom-dashboards) allows you to view information from several promoted apps in one place, including cross-promotion traffic. In addition, a custom dashboard is a quick and easy way to share data with account users.

> 📘 **Example**
>
> You are a marketer for eCommerce Apps, Ltd., and you have a highly successful app called Shoes. You are now launching 3 new apps, Accessories, Jackets and Coats, and Sport Shoes. You decide to run a cross-promotion campaign in the Shoe app to see which of your new apps it does the best job of promoting.
>
> You divide your user base into 3 segments. Each time a user launches the Shoe app, 1 out of 3 possible ads is displayed: 1 for Accessories, 1 for Jackets and Coats, and 1 for Sport Shoes.
>
> To view metrics for all 3 promoted apps in one place, you create a custom dashboard. In the following image, you can see that Sport Shoes has a 20.23% conversion rate, meaning that Shoes has a much greater affinity with Sport Shoes than with the other 2 apps it is promoting.
>
> ![CrossPromo_customWidget](https://files.readme.io/9363a68994956bc19115f6f9babb9acb0c7d4fe75478683b2a45720987486956-4404613319953.png)

<div data-zendesk-anchors="about-crosspromotion=about-cross-promotion h_01HE7RXZ2CZCYENE4K40W5YSHF=about-cross-promotion how-does-crosspromotion-work=how-does-cross-promotion-work h_01HE7RXZ2CE5EQV42Y4B9SK4FN=how-does-cross-promotion-work attributing-crosspromotion=attributing-cross-promotion h_01HE7RXZ2CWB2GZ8HV6447RVV1=attributing-cross-promotion setting-up-crosspromotion=setting-up-cross-promotion h_01HE7RXZ2C9JGFYV8K8FECFFJN=setting-up-cross-promotion viewing-crosspromotion-data=viewing-cross-promotion-data h_01HE7RXZ2CE9NWMQ1PT3G98QVN=viewing-cross-promotion-data h_01HE7RXZ2CQG9M35Y2FJNPZWDA=promoted-app-dashboard h_01HE7RXZ2CVQD8H0J6EVRJM5T7=analysis h_01HE7RXZ2CW1P0QNA8FFXP5KBS=example h_01HE7RXZ2C7N3DKNPF898WM4AD=custom-dashboard h_01HE7RXZ2C51KJMP795QYS26YK=example-1" />

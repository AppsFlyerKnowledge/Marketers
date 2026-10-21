---
title: CTV, PC, and console platform attribution concepts
metadata:
  keywords:
    - Attribution
    - Advertisers
    - Developers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2021-07-15T11:30:45Z'
  edited_at: '2026-10-14T12:13:28Z'
  id: 4404083608849
  locale: en-us
  section: Overview
  section_id: 15323084579345
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4404083608849-CTV-PC-and-console-platform-attribution-concepts
---
> **At a glance:** Learn about how attribution works for CTV, PC, and console platforms to allow AppsFlyer to receive attribution and event data for your campaigns on these cross-platform devices.

<Image alt="Diagram of AppsFlyer's cross-platform attribution solution for CTV, PC, and console" src="https://files.readme.io/7fc57fd80ad86bb173bcf81581b9fe8b4625ed2a044d302a6d72194560019e81-4410336840977.png" width="471px" />

## The AppsFlyer cross-platform solution

In today's digital landscape, growth professionals face the challenge of reaching consumers across multiple devices and platforms. Traditional measurement approaches fall short in capturing the full scope of user journeys that span platforms. Cross-platform measurement is essential to understanding the impact of marketing activities and making informed decisions.

AppsFlyer offers an extensive cross-platform solution that complements conventional mobile attribution tools. It helps growth professionals accurately measure and attribute marketing efforts when users interact across multiple platforms and devices. This solution focuses on CTV, PC, and console platforms.

Advertisers can promote an app on the same or different platforms as the ad displays. For example, an advertiser can display an ad for a Steam app on the Steam platform. They can also display an ad for a Steam app on the desktop web, for example, via Google Ads. <span id="tv-screens"></span>CTV campaigns specifically entail ads delivered on TV screens and TV-like displays.

Whatever their marketing strategy, advertisers integrate with AppsFlyer to receive attribution data and performance measurements about sources (non-organic or organic) and campaigns driving CTV, PC, and console platform app installs and post-install events. Marketers use these insights to calculate user lifetime value (LTV) and measure and optimize marketing activities. <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model">Learn more about AppsFlyer attribution</Anchor>

### Supported platforms

<table><thead><tr><th rowspan="2">Platform</th><th colspan="2">AppsFlyer integration method</th></tr><tr><th>S2S</th><th>SDK</th></tr></thead><tbody><tr><td>Android TV</td><td><span>-</span></td><td><span><strong>✓</strong></span></td></tr><tr><td>tvOS (Apple TV)</td><td><span>-</span></td><td><span><strong>✓</strong></span></td></tr><tr><td>MacOS</td><td><span>-</span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Amazon Fire TV</td><td><span>-</span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Chromecast</td><td><span>-</span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Roku</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Vizio</td><td><span><strong>✓</strong></span></td><td><span>-</span></td></tr><tr><td>Samsung</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>LG</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>PlayStation</td><td><span><strong>✓</strong></span></td><td><span>-</span></td></tr><tr><td>Vidaa</td><td><span><strong>✓</strong></span></td><td><span>-</span></td></tr><tr><td>Steam</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Native PC</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Meta Quest (Oculus)</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Epic Games</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Nintendo Switch</td><td><span><strong>✓</strong></span></td><td><span>-</span></td></tr><tr><td>Xbox</td><td><span><strong>✓</strong></span></td><td><span>-</span></td></tr></tbody></table>

### Integrate with ad networks that support specified CTV, PC, and Console platforms

Integrate with ad networks that display ads on CTV, PC, and console platforms in <Anchor target="_blank" href="/marketers/docs/partner-integrations">Partner Integrations</Anchor>.

## Cross-platform attribution flows

When marketing apps on CTV, PC, and console platforms, there are several flows—from ad display (impression or click) to AppsFlyer attribution—that apply to all platforms:

* Direct attribution link
* Cross-platform OneLink link
* SRN (self-reporting network, also known as SAN, self-attributing network)
* Cross-platform landing page

Each app, advertiser, and platform can have 1 or more of these flows implemented at the same time. The sections that follow explain the different flow types and when each is used.

<Accordion title="Direct attribution link">

Direct attribution links are AppsFlyer links that support redirection and attribution for a single destination app on a single platform at a time. They're typically utilized for:

* Same platform to same platform advertising. Meaning the platform displaying the ad and the platform supporting the app are identical. For example, an advertiser can display an ad for a Samsung TV app on a Samsung TV. Both probabilistic modeling and deterministic matching are supported (deterministic matching is performed when <Anchor target="_blank" href="/marketers/docs/about-device-identifiers#ctv--pc-and-console-app-device-identifiers">a supported ID</Anchor> is provided in the link).
* Any platform to any platform advertising, with the destination/platform predetermined. For example, a desktop web landing page displays an ad with one or more buttons, each redirecting to a specific platform store/marketplace. Attribution is performed by probabilistic modeling.

 The attribution flow is illustrated in the diagram that follows.

![CTV attribution flow - Direct attribution link flow](https://files.readme.io/2af32b096faa381843040314c9c183056256d03a7e2e6095e72a59bb7211727f-19374976446225.png)

Because direct attribution links point to an app on a specific, predetermined platform and lead to a single destination, they always include the app ID and platform information in the URL.

Sample direct attribution link: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/1234561?&af_media_source=game_media_source&af_campaign=campaign_yellow&af_campaign_id=1234&af_ad=game_ad_name&af_adset=game_adset_name&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F1176160%2FSpace_Wars%2F`

<Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-direct-attribution-links#attribution-link">Learn how to set up direct attribution links</Anchor>.

</Accordion>

<Accordion title="Cross-platform OneLink link">

Cross-platform OneLink links support routing and attribution when the ad platform and the destination platform differ. The user sees an ad for a mobile app on one platform, then continues the journey on another.

Examples:

* CTV-to-mobile. The user sees the mobile-app ad on a Roku device. They then install or open the Android or iOS app.
* Desktop-web-to-console. The user sees the game ad on desktop web. They then continue on a PC or console platform, such as PlayStation, Xbox, or Steam.

Cross-platform OneLink links only support the probabilistic modeling attribution method (based on IP address). For this reason, multiple installs by multiple users can be attributed to the same impression. The attribution flow is illustrated in the diagram that follows.

All possible app destinations/platforms are configured in the OneLink template. To that end, cross-platform OneLink links don't contain a specific app ID or specific platform information in the URL. Instead, the URL includes the template ID, which contains all the possible app destinations/platforms that are configured.

Sample cross-platform OneLink link:

```
https://impressions.onelink.me/ch/AG7A?pid=game_media_source&c=game_landing_page&af_ad=game_ad_name&af_adset=game_adset_name&af_xplatform=true
```

<Anchor target="_blank" href="/marketers/docs/set-up-cross-platform-links-for-multi-device-campaigns">Learn how to set up cross-platform OneLink links</Anchor>

</Accordion>

<Accordion title="SRN">

With direct attribution links and cross-platform OneLink links, AppsFlyer attribute installs via data contained in the URL. In contrast, self-reporting networks (SRNs), sometimes also known as Self-attributing networks (SANs), self-attribute using the device ID when notified of an install by AppsFlyer.

Attribution to SRNs is via deterministic matching. When an advertiser integrates an SRN, attribution works as illustrated in the diagram that follows.

![CTV attribution flow - SRN attribution flow](https://files.readme.io/ba0d84643aefd6a20e95c8aca9424affea8169c95ccc428ddf3d35bb8787a67c-19374961372945.png)

Currently, SRN attribution only works for same platform to same platform advertising. Meaning, when the touchpoint (click or impression) occurs on the same platform as the install. For example, if a Roku CTV install is checked with Roku Endemic Media (the SRN for Roku) and an impression is found to have occurred on a Roku device. If the impression happened on a different platform, such as mobile, it is not considered for attribution.

In the future, SRN attribution may become available for any platform to any platform ads, allowing for more comprehensive cross-platform attribution.

</Accordion>

<Accordion title="Cross-platform landing page">

Cross-platform landing pages are designed to support common cross-platform user journeys and marketing flows. They are most-commonly used for gaming apps. The landing pages run the AppsFlyer Smart Script to perform web-to-app attribution. This means they attribute installs on any platform (such as CTV, PC, console, and mobile platforms) to ads displayed on web.

The Smart Script in a cross-platform landing page uses the incoming link (the link on the web ad) to do two things that ensure the original media source and web ad are attributed with the install:

* Create a cross-platform OneLink link that sends an impression to AppsFlyer. This lets AppsFlyer log an impression that can later be used to attribute user installs. Impressions are sent when the landing page opens. Even if users leave the landing page without clicking any buttons, and then download and install the app on their own, the impression is still attributed.
* Create direct attribution links for each app/platform. When users click these links, they are directed to the correct platform/app store. And when they subsequently download and install the app, the install is attributed to the click.

The landing page supports both probabilistic modeling and deterministic matching (when an ID is provided in the link) attribution methods. With probabilistic modeling, it's possible that multiple installs by multiple users can be attributed to the same impression. The attribution flow is illustrated in the diagram that follows.

![CTV attribution flow - Landing page attribution flow](https://files.readme.io/28e4d14d14532332027e5d429ac3f95c8d4d451d94125e399cfb9ad04727b278-19374961376529.png)

For example:

1. You have a gaming app that can be downloaded and played on desktop, mobile, Epic, or Steam platforms.
2. You advertise on the web.
3. A user sees the ad on the web, whether from paid search results or social media promotions.
4. The users click on the ad and is redirected to a landing page, that has separate download buttons for each platform: desktop, mobile, Epic, and Steam.
5. The landing page runs the AppsFlyer Smart Script that:
6. Captures essential data points from the incoming link (the link that brought the user from web to the landing page), like query or UTM params, or default values, that identify the media source, campaign, ad, and more.
7. Uses the above data points to generate an impression and send it to AppsFlyer.
8. Generates outgoing links for each of the platform download buttons.
9. The user clicks one of the download buttons, is taken to the platform app store, downloads and opens the app.
10. The install/first app open is matched to the impression and attributed to the media source that showed the original ad on the web.

Additional information:

* <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">See sample cross-platform landing page</Anchor>
* <Anchor target="_blank" href="/marketers/docs/cross-platform-landing-pages-with-smart-script">Learn how to set up cross-platform landing pages with Smart Script</Anchor>

</Accordion>

## Data availability

CTV, PC, and console platform data includes install data, as well as in-app event data that gives advertisers insights regarding the lifetime value (LTV) of non-organic and organic users, based on subscription, in-app purchases, and ad monetization. LTV metrics are calculated from the attribution date until the present.

Data is available as follows:

* Aggregate data via the Overview dashboard.
* Raw data via:
  * <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-data-via-data-locker">Data Locker</Anchor>
  * <Anchor target="_blank" href="/marketers/docs/raw-data-export-page">Export</Anchor>
  * <Anchor target="_blank" href="/marketers/docs/pull-api-raw-data">Pull API</Anchor>
* **Impressions from cross-platform campaigns** (for example, CTV-to-mobile) don't display in app-level dashboards. A single CTV impression can lead to multiple mobile conversions, making it impossible to split impressions accurately across apps. To access total impression counts, use the <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-data-via-data-locker">Cross-platform engagements report via Data Locker</Anchor>.

> 📘 **Note**
>
> For platforms with Android and iOS operating systems, the availability of <Anchor target="_blank" href="/marketers/docs/aggregated-and-analytics-reporting-overview">aggregate</Anchor> and <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview">raw data reports</Anchor> is the same as for mobile apps.

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Re-attribution window | For CTV, PC, and console platforms, the re-attribution window is based on a defined period of inactivity (default 90 days). |
| Post-reinstall events | Attributed to the first install. <Anchor target="_blank" href="/marketers/docs/measure-reinstalls#attributed-to-the-first-install">Learn more</Anchor> |
| Retargeting | <ul><li>Re-attribution: Supported for all platforms.</li><li>Re-engagement: Supported in any platform that isn't Android, iOS, Windows Phone, or website. In practice, this means CTV, PC, and Console apps.</li></ul> |
| Attribution method | <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#attribution-methods">See CTV, PC, and console platform attribution methods</Anchor> |
| Currency | USD or as defined in AppsFlyer app settings |
| Timezone | UTC |
| Cost data | For apps on these platforms, import cost data via <Anchor target="_blank" href="/marketers/docs/import-cost-data">Cost Import</Anchor> using the upload-by-email method.<br /><br />You can also pull data via API for Google, Meta, or TikTok for the following platforms:<ul><li>Steam</li><li>Native PC</li><li>Smart Cast</li><li>Windows Phone</li><li>Tizen</li><li>Quest</li></ul> |
| Data freshness | In My Dashboards, the Installs, re-engagements, and re-attributions metrics for CTV, PC, and console platforms are served from our AI-ready data pipeline (migrated between July 21 and August 10, 2026). This means these metrics for these platforms now show up with a delay instead of continuously. See <Anchor target="_blank" href="/marketers/docs/my-dashboards#traits-and-limitations">My Dashboards traits and limitations</Anchor> for details. |

</Accordion>

<div data-zendesk-anchors="about-ctv-attribution=the-appsflyer-cross-platform-solution 01H7ZRK7PCNZG54ZQ0804HMR38=the-appsflyer-cross-platform-solution list-of-supported-ctv-and-gaming-device-types=supported-platforms 01H7ZRK7PCP1KWRX1A5K81F4KR=supported-platforms list-of-specified-platforms=integrate-with-ad-networks-that-support-specified-ctv-pc-and-console-platforms h_01JMA8F9F6M2MZFNRXFQWJF8B8=integrate-with-ad-networks-that-support-specified-ctv-pc-and-console-platforms crossplatform-attribution=cross-platform-attribution-flows 01H8EHHJNBA8NKMX2C8RSV7P31=cross-platform-attribution-flows h_01H9G52NKMQG9QD9S3N537BM7N=data-availability h_01M2MN6SN9SW7RGGK5R1MFW91B=note" />

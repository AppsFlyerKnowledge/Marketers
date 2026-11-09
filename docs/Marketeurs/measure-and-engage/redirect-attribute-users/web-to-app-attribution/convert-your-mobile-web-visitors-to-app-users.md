---
title: Convert your mobile web visitors to app users
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2019-03-19T08:54:10Z'
  edited_at: '2026-09-07T10:17:00Z'
  id: 360001237818
  locale: en-us
  section: Web-to-app attribution
  section_id: 6551240476177
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360001237818-Convert-your-mobile-web-visitors-to-app-users
---
> **At a glance:** Use your mobile website to convert mobile web visitors into new mobile app users.

## Mobile web-to-app attribution solutions

<Image align="center" alt="Web_to_app_.png" src="https://files.readme.io/deb9ba0dfd18671666e9f06dc27440759844ea365988f80e05ce7ac2817a7299-46646996021777.png" />

### Benefits of web-to-app campaigns

Using web-to-app campaigns helps you:

* Convert mobile web visitors into app users. [See also web-assisted installs.](/docs/convert-your-mobile-web-visitors-to-app-users#web-assisted-installs)
* Use web or landing pages to increase your users’ understanding of your product/service before they download the app.
* Find your best- and least- converting web/landing pages.
* Build more specific offerings to retarget your mobile web users, who are also your app users.
* Seamlessly deep link users from the site to a specific page in the app.

### Attribution solutions

<Embed title="Convert your mobile web visitors to app users" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/kv67fa3rvn" providerUrl="https://fast.wistia.com" />

For mobile web-to-app users, since there are two clicks (the first that directs to the web page and the second that directs from the web page to the app store), attribution and deep linking are problematic. Users who eventually download the app may be wrongfully attributed, or attributed as organic, even if the first click comes from an ad network, Google click, or owned media source. 

AppsFlyer provides the following solutions for accurate web-to-app attribution:

<Anchor target="_blank" href="/marketers/fr/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor>:

* Add the Smart Banner web SDK to your website, and then create dynamic banners on the AppsFlyer dashboard.
* When a user clicks a URL and is directed to your mobile website, a Smart Banner pops up with a CTA to download the app from the app store.
* The Smart Banner URL is populated based on the parameters/UTMs in the incoming link, and is used for attribution.

<Anchor target="_blank" href="/marketers/fr/docs/onelink-smart-script-overview">OneLink Smart Script</Anchor>:

* Runs a script on your mobile website.
* When a user clicks a URL and is directed to your mobile website, they land on a page with buttons urging them to download your app.
* The script on the web page dynamically generates the outgoing URLs on these buttons based on the incoming URL, which is used for attribution.
* Replaces the previous mobile landing page attribution <Anchor target="_blank" href="/marketers/fr/docs/deprecated-mobile-landing-page-attribution-script">script</Anchor>. If you are still using the previous script, you should migrate.

Both solutions bridge the gap between the incoming campaign URLs to your website, and the outgoing OneLink URL created for correct attribution and deep linking of the mobile website users.

The following table compares the two solutions so that you can choose and implement the one most suitable for your needs. **Note**: You can implement both solutions and use them in tandem.

#### Smart Banner vs OneLink Smart Script

| Characteristic | Smart Banners | OneLink Smart Script |
| --- | --- | --- |
| Media sources supported | All media sources supported:<ul><li>Incoming links with pid or UTM params (including SRNs)</li><li>Organic visitors</li></ul> | All media sources supported:<ul><li>Incoming links (including SRNs)</li><li>Organic visitors</li></ul> |
| Change attribution link parameters | Fast change in AppsFlyer dashboard/wizard access. | Requires developer implementation in the script, but is totally flexible. |
| Desktop users | Not supported | Supported |
| Marketer setup | Uses wizard to set up Smart Banners. | Decides parameters and values to be set on the incoming and outgoing URLs (default values are supplied). |
| Developer setup | <ul><li>Integrates web SDK.</li><li>Alternatively, can be <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-marketers">implemented by the marketer</Anchor>.</li></ul> | <ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator">Implements the script</Anchor> that creates the outgoing URL.</li><li>Alternatively, can be implemented by the marketer via a <Anchor target="_blank" href="/marketers/fr/docs/set-up-smart-script-to-convert-web-visitors#configurer-smart-script-onelink">tag manager</Anchor>.</li></ul> |
| Ongoing campaign setup | For click ad networks, set up web campaign-to-app link. | Follow the instructions per media source type. |
| Availability | Available with a paid subscription plan. | Available with a paid subscription plan. |

**Note:** Smart Banners and OneLink Smart Script are available only with eligible paid <Anchor target="_blank" href="/marketers/fr/docs/account-management-plans-payments-and-billing#appsflyer-plans">subscription plans</Anchor>. Feature access depends on your AppsFlyer plan.

### Web-assisted installs

Web-Assisted Installs occur when users download your app, but not necessarily because of a specific campaign. Before they download your app, they visited your website for whatever reason, perhaps days or weeks earlier. Use <Anchor target="_blank" href="/marketers/fr/docs/people-based-attribution-pba-overview">PBA</Anchor> Web-Assisted Installs to see a general breakdown of these *assist* touchpoints that eventually lead to the app install.  

#### Web-to-app solutions vs. Web-Assisted Installs

| Characteristic | Mobile web-to-app solutions | Web-Assisted Installs (PBA) |
| --- | --- | --- |
| Purpose | Gives you tools to run campaigns designed to directly convert web visitors into app users, while attributing the media source responsible for the web visit. | See a breakdown of installs preceded by web visits. |
| Flows | Direct flow from web to app download. | Direct, deferred, or disjointed flows. Installs can be predated by a web visit (up to 30 days). |
| User devices | Same device | Same or cross-device |

| Trait | Remarks |
| --- | --- |
| SDK version |  |
| Match type | `preload_rfr` |
| Overview dashboard | Engagements count as clicks in aggregate reports and dashboards. They are aggregated at the preload partner (media source) and campaign levels. |
| Raw data reports | <ul><li>Engagements are available in the clicks reports only via Data Locker.</li><li>In the install reports, the preload events are NOT found in the original URL due to Samsung’s privacy restrictions.</li><li>They can be identified in the `af_engagement_type` parameter as `preload`.</li></ul> |

<div data-zendesk-anchors="mobile-webtoapp-attribution-solutions=mobile-web-to-app-attribution-solutions h_01KFAFC9DFAES0JGPVCQQV3GAR=mobile-web-to-app-attribution-solutions benefits-of-webtoapp-campaigns=benefits-of-web-to-app-campaigns h_01KFAFC9DFJ7QWJ6JN60NKVPZ3=benefits-of-web-to-app-campaigns h_01KFAFC9DFH4JH6DE4KZE424Q3=attribution-solutions h_01KFAFC9DFGCYRS1C5SVX1ZSCC=smart-banner-vs-onelink-smart-script webassisted-installs=web-assisted-installs h_01KFAFC9DG4MCVQ5YRGVRQ6K5P=web-assisted-installs webtoapp-solutions-vs-webassisted-installs=web-to-app-solutions-vs-web-assisted-installs h_01KFAFC9DG4YJ55BYQH9TQ2YPQ=web-to-app-solutions-vs-web-assisted-installs" />

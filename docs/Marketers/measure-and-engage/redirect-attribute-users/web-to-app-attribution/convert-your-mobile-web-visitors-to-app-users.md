---
title: "Convert your mobile web visitors to app users"
excerpt: "Learn how to use your mobile website to convert mobile web visitors into new mobile app users with AppsFlyer's web-to-app attribution solutions."
---
**At a glance:** Use your mobile website to convert mobile web visitors into new mobile app users.

## Mobile web-to-app attribution solutions

![Web_to_app_.png](https://files.readme.io/deb9ba0dfd18671666e9f06dc27440759844ea365988f80e05ce7ac2817a7299-46646996021777.png)

### Benefits of web-to-app campaigns

Using web-to-app campaigns helps you:

* Convert mobile web visitors into app users. [See also web-assisted installs.](/docs/convert-your-mobile-web-visitors-to-app-users#webassisted-installs)
* Use web or landing pages to increase your users’ understanding of your product/service before they download the app.
* Find your best- and least- converting web/landing pages.
* Build more specific offerings to retarget your mobile web users, who are also your app users.
* Seamlessly deep link users from the site to a specific page in the app.

### Attribution solutions

![](https://fast.wistia.com/embed/medias/kv67fa3rvn/swatch)

For mobile web-to-app users, since there are two clicks (the first that directs to the web page and the second that directs from the web page to the app store), attribution and deep linking are problematic. Users who eventually download the app may be wrongfully attributed, or attributed as organic, even if the first click comes from an ad network, Google click, or owned media source. 

AppsFlyer provides the following solutions for accurate web-to-app attribution:

[Smart Banners](/docs/smart-banners-mobile-web-to-app-for-marketers):

* Add the Smart Banner web SDK to your website, and then create dynamic banners on the AppsFlyer dashboard.
* When a user clicks a URL and is directed to your mobile website, a Smart Banner pops up with a CTA to download the app from the app store.
* The Smart Banner URL is populated based on the parameters/UTMs in the incoming link, and is used for attribution.

[OneLink Smart Script](/docs/onelink-smart-script-overview):

* Runs a script on your mobile website.
* When a user clicks a URL and is directed to your mobile website, they land on a page with buttons urging them to download your app.
* The script on the web page dynamically generates the outgoing URLs on these buttons based on the incoming URL, which is used for attribution.
* Replaces the previous mobile landing page attribution [script](/docs/deprecated-mobile-landing-page-attribution-script). If you are still using the previous script, you should migrate.

Both solutions bridge the gap between the incoming campaign URLs to your website, and the outgoing OneLink URL created for correct attribution and deep linking of the mobile website users.

The following table compares the two solutions so that you can choose and implement the one most suitable for your needs. **Note**: You can implement both solutions and use them in tandem.

#### Smart Banner vs OneLink Smart Script



| Characteristic | Smart Banners | OneLink Smart Script |
| --- | --- | --- |
| Media sources supported | All media sources supported:<br /><br />* Incoming links with pid or UTM params (including SRNs)<br />* Organic visitors | All media sources supported:<br /><br />* Incoming links (including SRNs)<br />* Organic visitors |
| Change attribution link parameters | Fast change in AppsFlyer dashboard/wizard access. | Requires developer implementation in the script, but is totally flexible. |
| Desktop users | Not supported | Supported |
| Marketer setup | Uses wizard to set up Smart Banners. | Decides parameters and values to be set on the incoming and outgoing URLs (default values are supplied). |
| Developer setup | * Integrates web SDK.<br />* Alternatively, can be [implemented by the marketer](/docs/smart-banners-website-code-implementation-for-marketers). | * [Implements the script](https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator) that creates the outgoing URL.<br />* Alternatively, can be implemented by the marketer via a [tag manager](/docs/set-up-smart-script-to-convert-web-visitors#set-up-onelink-smart-script). |
| Ongoing campaign setup | For click ad networks, set up web campaign-to-app link. | Follow the instructions per media source type. |
| Availability | Available with a paid subscription plan. | Available with a paid subscription plan. |



**Note:** Smart Banners and OneLink Smart Script are available only with eligible paid [subscription plans](/docs/account-management-plans-payments-and-billing#appsflyer-plans). Feature access depends on your AppsFlyer plan.

### Web-assisted installs

Web-Assisted Installs occur when users download your app, but not necessarily because of a specific campaign. Before they download your app, they visited your website for whatever reason, perhaps days or weeks earlier. Use [PBA](/docs/people-based-attribution-pba-overview) Web-Assisted Installs to see a general breakdown of these *assist* touchpoints that eventually lead to the app install.  

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
| Raw data reports | * Engagements are available in the clicks reports only via Data Locker.<br />* In the install reports, the preload events are NOT found in the original URL due to Samsung’s privacy restrictions.<br />* They can be identified in the `af_engagement_type` parameter as `preload`. |
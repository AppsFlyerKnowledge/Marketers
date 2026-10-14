---
title: "Smart Banners and Smart Script security and performance"
excerpt: "Discover how AppsFlyer proactively addresses your security concerns regarding Smart Banners and Smart Script."
x-zendesk:
  id: 22082177372561
  url: https://support.appsflyer.com/hc/en-us/articles/22082177372561-Smart-Banners-and-Smart-Script-security-and-performance
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Web-to-app attribution
  section_id: 6551240476177
  position: 4
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, Smart Banners and Scripts]
  labels: [Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2024-01-30T14:54:37Z'
  edited_at: '2026-05-31T11:57:28Z'
---
In this Q&A, we discuss common queries about smart banners and smart script integration, focusing on their impact on security and site speed.

## Smart banners API security

<Accordion title="What data does the smart banner capture when someone clicks or views it?">

| Data | Remarks |
| --- | --- |
| Client IP | The IP is used to calculate location (Country, region and state) |
| Event time |  |
| User Agent |  |
| Website Page | The URL from which the call to the web SDK originated |
| HTTP protocol | HTTP/HTTPS |
| Headers | Host, Content-type, Origin, Content-length, Encoding |
| OneLink parameters |  |
| Banner parameters | Banner configuration settings:<ul><li>[Dismissal behavior](/docs/smart-banners-mobile-web-to-app-for-marketers#dismissal-behaviour)</li><li>[Incoming parameters](/docs/smart-banners-mobile-web-to-app-for-marketers#param-table)</li><li>UTM parameters</li><li>AppsFlyer parameters</li><li>default parameters</li><li>other parameters</li></ul> |

</Accordion>

<Accordion title="What API calls are needed to show a smart banner?">

* An API to fetch the SDK from a CDN located at `https://websdk.appsflyersdk.com`.
* An API to generate the link behind the CTA located at `banner.appsflyer.com`. This API is triggered by the [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner) SDK method.
* An API to fetch the the banner creative from a CDN located at `creatives-cdn-appsflyer.com`.

</Accordion>

<Accordion title="Do these API calls include an identifier?">

Yes. The client's unique web key acts as an identifier in API calls, enabling the retrieval of necessary data for banner display and the generation of the OneLink URL for the banner CTA.

</Accordion>

<Accordion title="Is it possible for a malicious entity to change the URL or alter the APIs web key?">

No. It's not possible to access and modify the code dictating the web key used in the banner's API call. This means that malicious entities cannot manipulate the banner calculation and the OneLink URL generated for the banner CTA.

</Accordion>

## Smart banners script hosting security

<Accordion title="Can clients host a copy of the Smart Banner script on their server?">

Clients cannot host Smart Banners script on their servers. However they can use [Smart Script](/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script) for OneLink URL generation and implement their own banner creatives.

Using Smart Script along with your own banners lets you design custom creatives and further map and customize your generated links, eliminating the need to implement the banner SDK on your website and perform external API calls.

</Accordion>

<Accordion title="Can clients host their own code and still use banners?">

Clients can develop their own banners, including the design, development, and integration on the site, and utilize [Smart Script](/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script) to generate the links for their banner's call-to-action (CTA).

</Accordion>

<Accordion title="Can Smart Banners be supported without embedding their code snippet on the page?">

* Clients have the option to use tag managers to invoke the Smart Banner APIs, as an alternative to directly integrating the code snippet. To learn more about tag managers see [here.](/docs/smart-banners-website-code-implementation-for-marketers#website-code-implementation)
* Running the script in an iFrame is not supported.

</Accordion>

<Accordion title="How does AppsFlyer protect your banners from post-save tampering">

When editing and saving a banner creative in AppsFlyer creative editor - an attacker could try and intercept the request, take over it, and inject harmful JavaScript code.

We implement multiple measures to ensure Smart Banners are secure from potential attacks and prevent unauthorized edits by users outside of their own account.

* Our Security team runs tests and checks to make sure all our services (including Smart Banners) are are protected and free from vulnerabilities.
* We conduct regular independent and unbiased penetration tests to ensure AppsFlyer's safety and security.
* Internally, we validate HTML and Script tags and sanitize any malicious scripts.

</Accordion>

<Accordion title="Do Smart Banners use cookies?">

By default, Smart Banners do not use cookies. However, we provide an optional configuration to use first-party cookies for customers who prefer increased persistence (for example, to address storage volatility in Safari on iOS 26).

The website owner must explicitly [enable this option](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#set-storage-mode-optional). If enabled, the website owner is also responsible for updating their cookie consent management and privacy disclosures as required by applicable regulations.

</Accordion>

## Smart Banners Performance

<Accordion title="Does the Smart Banner web SDK impact website load speed?">

While adding any additional code to a website might potentially affect loading times, most of the smart banner's work is done server-side, asynchronously, and without blocking the page from loading.

Furthermore, we employ CDNs to expedite the loading of pages and banners.

</Accordion>

<Accordion title="Can you share some metrics regarding banner speed performance?">

Banner loading speed varies and depends on several factors including:

* Internet speed
* Connectivity and connection type
* Site performance and more.

These factors, when added to the minimal response time from AppsFlyer servers to browsers, contribute to the calculation of banner load times.

Since the above variables are not related to AppsFlyer, we cannot specify exact time frames for the complete end-to-end process.

</Accordion>

<Accordion title="How can I actively minimize the banner loading time?">

Banner loading time is impacted by the Largest Contentful Paint (LCP), which primarily concerns the banner image. To improve LCP loading performance, you can::

* Choose a smaller banner template.
* Reduce the image sizes of the logo and background images
  * Consider substituting the background image with a solid color to cut down on asset loading times.
  * Use a CDN to host your banner images for faster loading times.

* Choose the same font weight throughout your banner.

</Accordion>

## Smart Script Security and Performance

<Accordion title="Does Smart Script use cookies?">

No, we do not use cookies in our Smart Script solution.

</Accordion>

<Accordion title="Does Smart Script make any external calls to generate links?">

No, the script is executed locally on the client's website, so it doesn't rely on external calls, making it very secure to use.

</Accordion>

<Accordion title="Is there a download time associated with Smart Script?">

You can embed the script directly on your website, ensuring no download time. The script loads quickly because it doesn't require any server calls.

</Accordion>

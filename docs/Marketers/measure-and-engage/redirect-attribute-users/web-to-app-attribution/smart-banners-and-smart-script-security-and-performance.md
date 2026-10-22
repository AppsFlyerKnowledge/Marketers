---
title: Smart Banners and Smart Script security and performance
metadata:
  keywords:
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-01-30T14:54:37Z'
  edited_at: '2026-05-31T11:57:28Z'
  id: 22082177372561
  locale: en-us
  section: Web-to-app attribution
  section_id: 6551240476177
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/22082177372561-Smart-Banners-and-Smart-Script-security-and-performance
---
> **At a glance:** Discover how AppsFlyer proactively addresses your security concerns regarding Smart Banners and Smart Script.

In this Q&A, we discuss common queries about smart banners and smart script integration, focusing on their impact on security and site speed.

## Smart banners API security

<div id="what-data-does-the-smart-banner-capture-when-someone-clicks-or-views-it" />

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
| Banner parameters | Banner configuration settings:<ul><li><Anchor target="_blank" href="/marketers/docs/smart-banners-mobile-web-to-app-for-marketers#dismissal-behaviour">Dismissal behavior</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/smart-banners-mobile-web-to-app-for-marketers#param-table">Incoming parameters</Anchor></li><li>UTM parameters</li><li>AppsFlyer parameters</li><li>default parameters</li><li>other parameters</li></ul> |

</Accordion>

<div id="what-api-calls-are-needed-to-show-a-smart-banner" />

<Accordion title="What API calls are needed to show a smart banner?">

* An API to fetch the SDK from a CDN located at `https://websdk.appsflyersdk.com`.
* An API to generate the link behind the CTA located at `banner.appsflyer.com`. This API is triggered by the [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner) SDK method.
* An API to fetch the the banner creative from a CDN located at `creatives-cdn-appsflyer.com`.

</Accordion>

<div id="do-these-api-calls-include-an-identifier" />

<Accordion title="Do these API calls include an identifier?">

Yes. The client's unique web key acts as an identifier in API calls, enabling the retrieval of necessary data for banner display and the generation of the OneLink URL for the banner CTA.

</Accordion>

<div id="is-it-possible-for-a-malicious-entity-to-change-the-url-or-alter-the-apis-web-key" />

<Accordion title="Is it possible for a malicious entity to change the URL or alter the APIs web key?">

No. It's not possible to access and modify the code dictating the web key used in the banner's API call. This means that malicious entities cannot manipulate the banner calculation and the OneLink URL generated for the banner CTA.

</Accordion>

## Smart banners script hosting security

<div id="can-clients-host-a-copy-of-the-smart-banner-script-on-their-server" />

<Accordion title="Can clients host a copy of the Smart Banner script on their server?">

Clients cannot host Smart Banners script on their servers. However they can use <Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script">Smart Script</Anchor> for OneLink URL generation and implement their own banner creatives.

Using Smart Script along with your own banners lets you design custom creatives and further map and customize your generated links, eliminating the need to implement the banner SDK on your website and perform external API calls.

</Accordion>

<div id="can-clients-host-their-own-code-and-still-use-banners" />

<Accordion title="Can clients host their own code and still use banners?">

Clients can develop their own banners, including the design, development, and integration on the site, and utilize <Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script">Smart Script</Anchor> to generate the links for their banner's call-to-action (CTA).

</Accordion>

<div id="can-smart-banners-be-supported-without-embedding-their-code-snippet-on-the-page" />

<Accordion title="Can Smart Banners be supported without embedding their code snippet on the page?">

* Clients have the option to use tag managers to invoke the Smart Banner APIs, as an alternative to directly integrating the code snippet. To learn more about tag managers see <Anchor target="_blank" href="/marketers/docs/smart-banners-website-code-implementation-for-marketers#website-code-implementation">here.</Anchor>
* Running the script in an iFrame is not supported.

</Accordion>

<div id="how-does-appsflyer-protect-your-banners-from-postsave-tampering" />

<Accordion title="How does AppsFlyer protect your banners from post-save tampering">

When editing and saving a banner creative in AppsFlyer creative editor - an attacker could try and intercept the request, take over it, and inject harmful JavaScript code.

We implement multiple measures to ensure Smart Banners are secure from potential attacks and prevent unauthorized edits by users outside of their own account.

* Our Security team runs tests and checks to make sure all our services (including Smart Banners) are are protected and free from vulnerabilities.
* We conduct regular independent and unbiased penetration tests to ensure AppsFlyer's safety and security.
* Internally, we validate HTML and Script tags and sanitize any malicious scripts.

</Accordion>

<div id="do-smart-banners-use-cookies" />

<Accordion title="Do Smart Banners use cookies?">

By default, Smart Banners do not use cookies. However, we provide an optional configuration to use first-party cookies for customers who prefer increased persistence (for example, to address storage volatility in Safari on iOS 26).

The website owner must explicitly <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#set-storage-mode-optional">enable this option</Anchor>. If enabled, the website owner is also responsible for updating their cookie consent management and privacy disclosures as required by applicable regulations.

</Accordion>

## Smart Banners Performance

<div id="does-the-smart-banner-web-sdk-impact-website-load-speed" />

<Accordion title="Does the Smart Banner web SDK impact website load speed?">

While adding any additional code to a website might potentially affect loading times, most of the smart banner's work is done server-side, asynchronously, and without blocking the page from loading.

Furthermore, we employ CDNs to expedite the loading of pages and banners.

</Accordion>

<div id="can-you-share-some-metrics-regarding-banner-speed-performance" />

<Accordion title="Can you share some metrics regarding banner speed performance?">

Banner loading speed varies and depends on several factors including:

* Internet speed
* Connectivity and connection type
* Site performance and more.

These factors, when added to the minimal response time from AppsFlyer servers to browsers, contribute to the calculation of banner load times.

Since the above variables are not related to AppsFlyer, we cannot specify exact time frames for the complete end-to-end process.

</Accordion>

<div id="how-can-i-actively-improve-the-banner-loading-time" />

<Accordion title="How can I actively minimize the banner loading time?">

Banner loading time is impacted by the Largest Contentful Paint (LCP), which primarily concerns the banner image. To improve LCP loading performance, you can::

* Choose a smaller banner template.
* Reduce the image sizes of the logo and background images
  * Consider substituting the background image with a solid color to cut down on asset loading times.
  * Use a CDN to host your banner images for faster loading times.

* Choose the same font weight throughout your banner.

</Accordion>

## Smart Script Security and Performance

<div id="does-smart-script-use-cookies" />

<Accordion title="Does Smart Script use cookies?">

No, we do not use cookies in our Smart Script solution.

</Accordion>

<div id="does-smart-script-make-any-external-calls-to-generate-links" />

<Accordion title="Does Smart Script make any external calls to generate links?">

No, the script is executed locally on the client's website, so it doesn't rely on external calls, making it very secure to use.

</Accordion>

<div id="is-there-a-download-time-associated-with-smart-script" />

<Accordion title="Is there a download time associated with Smart Script?">

You can embed the script directly on your website, ensuring no download time. The script loads quickly because it doesn't require any server calls.

</Accordion>

<div data-zendesk-anchors="h_01HNDDT0XHK5Y5NYTQMSXYSCZ4=smart-banners-api-security h_01HNDDT0XHY7BZNXA2CRT1W46F=what-data-does-the-smart-banner-capture-when-someone-clicks-or-views-it h_01HNDDT0XJGFJE3XBAXTE0C2K5=what-api-calls-are-needed-to-show-a-smart-banner h_01HNDDT0XJVX8KXSZC10GTJMCS=do-these-api-calls-include-an-identifier h_01HNDDT0XJ7MGPFSZKJ7YRZ2HJ=is-it-possible-for-a-malicious-entity-to-change-the-url-or-alter-the-apis-web-key h_01HNDDT0XJSS77BFVVT2QQV5HP=smart-banners-script-hosting-security h_01HNDDT0XJYW3Y0MQZWW1C1ETJ=can-clients-host-a-copy-of-the-smart-banner-script-on-their-server h_01HNDDT0XJG1SKBMA14KBGKZGD=can-clients-host-their-own-code-and-still-use-banners h_01HNDDT0XJDEGBK5WTBJ52ZVST=can-smart-banners-be-supported-without-embedding-their-code-snippet-on-the-page h_01HNDDT0XJC7FT514HEGN68T68=how-does-appsflyer-protect-your-banners-from-postsave-tampering h_01HNDDT0XJR4BQPN20FNGJPARY=do-smart-banners-use-cookies smart-banner-performance=smart-banners-performance h_01HNDDT0XJNJXY52BZJS9T1G72=smart-banners-performance h_01HNDDT0XJ456B4DG38BMMP98W=does-the-smart-banner-web-sdk-impact-website-load-speed h_01HNDDT0XJSEXVNRT8H27EMCNS=can-you-share-some-metrics-regarding-banner-speed-performance h_01HNDDT0XJK99RH6MAJFGQ7FPX=how-can-i-actively-improve-the-banner-loading-time h_01HNDDT0XJSGVRA6SB2YYYAE0P=smart-script-security-and-performance h_01HNDDT0XJW9B4GJ3J4RMJDG6V=does-smart-script-use-cookies h_01HNDDT0XJNZXGPZN2NDHQ34KF=does-smart-script-make-any-external-calls-to-generate-links h_01HNDDT0XJXV12C5P1CD32FZW3=is-there-a-download-time-associated-with-smart-script" />

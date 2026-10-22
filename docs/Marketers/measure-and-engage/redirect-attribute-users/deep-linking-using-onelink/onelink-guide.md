---
title: OneLink guide
metadata:
  keywords:
    - Marketers
    - start
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-10-19T08:53:16Z'
  edited_at: '2026-05-13T07:18:11Z'
  id: 115005248543
  locale: en-us
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/en-us/articles/115005248543-OneLink-guide
---
> **At a glance:** Create links with attribution, redirection, and deep linking capabilities that convert owned or paid media users into app users, regardless of device, operating system, channel, or platform. These links help you provide the best experience for your users, no matter which of your owned media sources they convert from: websites, banners, social media posts, emails, texts, and more.

## Introduction video

<Embed title="OneLink guide" typeOfEmbed="youtube" url="https://www.youtube.com/embed/golT4p9D8MA" providerUrl="https://www.youtube.com" />

## Benefits

The AppsFlyer customer experience and deep linking suite powered by OneLink allows you to create links to measure mobile marketing campaigns across every major channel. The links you create allow you to:

* Interact with your customers across many different online and offline touchpoints.
* Increase conversions by providing users from any touchpoint with the best contextual experiences, from click to app install.
* Get accurate attribution and measurements regarding your campaign results.
* Send new users without your app to the correct app store or web URL, regardless of device, operating system, channel, or platform.
* Send existing users with your app installed directly into the app (using App Links, Universal Links, and URI schemes).
* Deep link users to specific in-app pages or experiences.

OneLink features are available through <Anchor target="_blank" href="/marketers/docs/account-management-plans-payments-and-billing#appsflyer-plans">AppsFlyer subscription plans</Anchor>. To keep your OneLink experiences running smoothly, make sure your plan stays active.

## Experiences

The AppsFlyer customer experience and deep linking suite powered by OneLink allows you to create links that provide the optimal experience for your users, no matter where they come from. The customer experiences you can configure include:

* **Social-to-app**: Engage your users on social media and send them from social media feeds to your app.
* **App-to-app**: Lead users to your app from within other apps.
* <Anchor target="_blank" href="/marketers/docs/convert-your-mobile-web-visitors-to-app-users">**Web-to-app**</Anchor>: Convert your mobile website visitors into new mobile app users using Smart Banners and Smart Script.
* <Anchor target="_blank" href="/marketers/docs/qr-to-app-conversion">**QR-to-app**</Anchor>: Use QR codes to drive app installs by having users scan a QR code at key points during their offline customer experience. You can also put QR codes on your desktop site, or on TV and CTV ads to route users to your app.
* **Email-to-app**: Use email service providers (ESPs) to engage users via email and send them from their inbox to your app.
* **Text-to-app**: Create links for your SMS and messaging campaigns and engage users via text messages.
* **Referral-to-app**: Create user invite links that allow users and influencers to invite others to your app or share specific in-app content, for example, an article.
* **Custom**: No matter where your users come from, whether via desktop or mobile, online or offline, owned or paid media, use OneLink to easily send your users to the right place.

## Setting up OneLink

Providing the desired customer experience from link to app install for your users using the AppsFlyer UI requires:

* Two different roles within an organization (marketers and developers) working together.
* <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template">Creating a OneLink template</Anchor> that represents the routing logic at the core of all your links, to redirect:
  * New users without your app installed to the correct app store or web URL.
  * Existing users with your app installed into the app via Android App Links, iOS Universal Links, and URI scheme.

    * If these are not defined, users will default to the same settings as new users without your app installed (web URL or app store).

    **Note**: A OneLink template is not a clickable link for your end-users; it is the foundation for generating many custom links. Based on the template, you can create many OneLink custom links for the users to click on. It is rare to need more than one or two OneLink templates in the lifetime of an app (outside of testing).
* <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Creating a OneLink link</Anchor>. This is the clickable link or scannable QR code displayed in your ads. During link setup, you define the desired customer experience and add any desired parameters.

The following table describes the details of the marketer and developer tasks and provides links to their resources.

| Task | Details | Resources |
| --- | --- | --- |
| Create OneLink template | <ul><li>Marketer/product manager sets up the template in AppsFlyer.</li><li>Android developer configures app-opening methods for existing users (Android App Links and URI scheme).</li><li>iOS developer configures app-opening methods for existing users (iOS Universal Links and URI scheme).</li></ul> | <ul><li>AppsFlyer dashboard</li><li><Anchor target="_blank" href="/marketers/docs/create-a-onelink-template">Marketer instructions</Anchor></li><li>Developer instructions for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">Android</Anchor> and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup">iOS</Anchor></li></ul> |
| Create OneLink link | <ul><li>Marketer/product manager sets up the link in AppsFlyer, including selecting the desired customer experience and adding any desired attribution or deep linking parameters.</li><li>Android and iOS developers implement UDL method for deep linking (if deep linking is required).</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Marketer instructions</Anchor></li><li>Developer instructions for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_unified_deep_linking">Android</Anchor> and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_unified_deep_linking">iOS</Anchor></li><li>Sample apps (Github)</li></ul> |

## Additional options

After completing some or all of the setup in the UI, consider implementing the additional features described below.

* <Anchor target="_blank" href="/marketers/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> and <Anchor target="_blank" href="/marketers/docs/perform-onelink-bulk-actions-via-csv">bulk link creation</Anchor>: Scale and run multiple campaigns at once, and create thousands of OneLink links quickly and easily, saving you time and effort, and letting you focus on your campaign and marketing efforts instead.
* <Anchor target="_blank" href="/marketers/docs/export-onelink-urls">Export OneLink URLs</Anchor>: Download all OneLink URLs created in the AppsFlyer user interface (OneLink URLs created via SDK, OneLink API, or bulk upload aren't included).
* <Anchor target="_blank" href="/marketers/docs/measuring-push-notification-re-engagement-campaigns">Measure push notification re-engagement campaigns</Anchor>: Use push notifications with OneLink to measure mobile user re-engagements.
* <Anchor target="_blank" href="/marketers/docs/cross-promotion-attribution-for-marketers">Cross-promotion attribution</Anchor>: Your existing app users are excellent candidates for installing your other new apps. Learn how to use SDK methods to easily create and measure cross-promotion campaigns.
* <Anchor target="_blank" href="/marketers/docs/understand-onelink-short-vs-long-urls">Long URLs</Anchor>: Add parameters to your OneLink custom links or generate a large number of OneLink custom links by applying your own simple formulas in a spreadsheet.
* <Anchor target="_blank" href="/marketers/docs/redirect-app-users-to-a-website">App-to-web redirection</Anchor>: Redirect users from your app to a website or social media page.

## Troubleshooting and FAQ

Quickly find solutions for testing and debugging OneLink custom link redirection/behavior issues with our <Anchor target="_blank" href="/marketers/docs/onelink-troubleshooting-and-faq">OneLink troubleshooting guide</Anchor>.

## Limitations

* OneLink is not supported by the Meta mobile app install objective, where only Meta App Links are accepted.
* If your paid subscription plan lapses, certain OneLink links and features will no longer be available. This may affect ESP and branded domain links, disable SDK and API link creation and requests (unless separately purchased), and revoke access to web-to-app and bulk link creation.

<div data-zendesk-anchors="h_01HGE1D5JZ4Y603BD55W2P7DPW=introduction-video h_01HGE1D5JZJGY8BZX8ZTSXQ635=benefits h_01HGE1D5JZV65E9YWG424HYRNW=experiences setup=setting-up-onelink h_01HGE1D5K0RKHHV9SVH4VREMXQ=setting-up-onelink h_01HGE1D5K2VCKYJY3Y8MKYVT2V=additional-options h_01HGE1D5K24FG3F8G54DYTK599=troubleshooting-and-faq h_01HGE1D5K2M0VMJPMP4EJ0QGPY=limitations" />

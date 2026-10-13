---
title: "OneLink guide"
excerpt: "Create links with attribution, redirection, and deep linking capabilities that convert owned or paid media users into app users, regardless of device, operating system, channel, or platform. These links help you provide the best experience for your users, no matter which of your owned media sources they convert from: websites, banners, social media posts, emails, texts, and more."
x-zendesk:
  id: 115005248543
  url: https://support.appsflyer.com/hc/en-us/articles/115005248543-OneLink-guide
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Deep linking using OneLink
  section_id: 6551203111057
  position: 2
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, Smart Banners and Scripts]
  labels: [Marketers, start]
  promoted: false
  comments_disabled: true
  created_at: '2017-10-19T08:53:16Z'
  edited_at: '2026-05-13T07:18:11Z'
---
## Introduction video

<Embed title="Customer experience and deep linking suite overview" typeOfEmbed="youtube" url="https://www.youtube.com/embed/golT4p9D8MA" />

## Benefits

The AppsFlyer customer experience and deep linking suite powered by OneLink allows you to create links to measure mobile marketing campaigns across every major channel. The links you create allow you to:

- Interact with your customers across many different online and offline touchpoints.
- Increase conversions by providing users from any touchpoint with the best contextual experiences, from click to app install.
- Get accurate attribution and measurements regarding your campaign results.
- Send new users without your app to the correct app store or web URL, regardless of device, operating system, channel, or platform.
- Send existing users with your app installed directly into the app (using App Links, Universal Links, and URI schemes).
- Deep link users to specific in-app pages or experiences.

OneLink features are available through [AppsFlyer subscription plans](/docs/account-management-plans-payments-and-billing#appsflyer-plans). To keep your OneLink experiences running smoothly, make sure your plan stays active.

## Experiences

The AppsFlyer customer experience and deep linking suite powered by OneLink allows you to create links that provide the optimal experience for your users, no matter where they come from. The customer experiences you can configure include:

- **Social-to-app**: Engage your users on social media and send them from social media feeds to your app.
- **App-to-app**: Lead users to your app from within other apps.
- [**Web-to-app**](/docs/convert-your-mobile-web-visitors-to-app-users): Convert your mobile website visitors into new mobile app users using Smart Banners and Smart Script.
- [**QR-to-app**](/docs/qr-to-app-conversion): Use QR codes to drive app installs by having users scan a QR code at key points during their offline customer experience. You can also put QR codes on your desktop site, or on TV and CTV ads to route users to your app.
- **Email-to-app**: Use email service providers (ESPs) to engage users via email and send them from their inbox to your app.
- **Text-to-app**: Create links for your SMS and messaging campaigns and engage users via text messages.
- **Referral-to-app**: Create user invite links that allow users and influencers to invite others to your app or share specific in-app content, for example, an article.
- **Custom**: No matter where your users come from, whether via desktop or mobile, online or offline, owned or paid media, use OneLink to easily send your users to the right place.

## Setting up OneLink

Providing the desired customer experience from link to app install for your users using the AppsFlyer UI requires:

- Two different roles within an organization (marketers and developers) working together.
- [Creating a OneLink template](/docs/create-a-onelink-template)that represents the routing logic at the core of all your links, to redirect:
  - New users without your app installed to the correct app store or web URL.
  - Existing users with your app installed into the app via Android App Links, iOS Universal Links, and URI scheme.
    - If these are not defined, users will default to the same settings as new users without your app installed (web URL or app store).

> 📘 Note
>
> A OneLink template is not a clickable link for your end-users; it is the foundation for generating many custom links. Based on the template, you can create many OneLink custom links for the users to click on. It is rare to need more than one or two OneLink templates in the lifetime of an app (outside of testing).

- [Creating a OneLink link](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink). This is the clickable link or scannable QR code displayed in your ads. During link setup, you define the desired customer experience and add any desired parameters.

The following table describes the details of the marketer and developer tasks and provides links to their resources.

| Task | Details | Resources |
| --- | --- | --- |
| Create OneLink template | - Marketer/product manager sets up the template in AppsFlyer.<br />- Android developer configures app-opening methods for existing users (Android App Links and URI scheme).<br />- iOS developer configures app-opening methods for existing users (iOS Universal Links and URI scheme). | - AppsFlyer dashboard<br />- [Marketer instructions](/docs/create-a-onelink-template)<br />- Developer instructions for [Android](https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods) and [iOS](https://dev.appsflyer.com/hc/docs/dl_ios_init_setup) |
| Create OneLink link | - Marketer/product manager sets up the link in AppsFlyer, including selecting the desired customer experience and adding any desired attribution or deep linking parameters.<br />- Android and iOS developers implement UDL method for deep linking (if deep linking is required). | - [Marketer instructions](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink)<br />- Developer instructions for [Android](https://dev.appsflyer.com/hc/docs/dl_android_unified_deep_linking) and [iOS](https://dev.appsflyer.com/hc/docs/dl_ios_unified_deep_linking)<br />- Sample apps (Github) |

## Additional options

After completing some or all of the setup in the UI, consider implementing the additional features described below.

- [OneLink API](/docs/use-onelink-api-to-create-links-in-large-scale-campaigns) and [bulk link creation](/docs/perform-onelink-bulk-actions-via-csv): Scale and run multiple campaigns at once, and create thousands of OneLink links quickly and easily, saving you time and effort, and letting you focus on your campaign and marketing efforts instead.
- [Export OneLink URLs](/docs/export-onelink-urls): Download all OneLink URLs created in the AppsFlyer user interface (OneLink URLs created via SDK, OneLink API, or bulk upload aren't included).
- [Measure push notification re-engagement campaigns](/docs/measuring-push-notification-re-engagement-campaigns): Use push notifications with OneLink to measure mobile user re-engagements.
- [Cross-promotion attribution](/docs/cross-promotion-attribution-for-marketers): Your existing app users are excellent candidates for installing your other new apps. Learn how to use SDK methods to easily create and measure cross-promotion campaigns.
- [Long URL](/docs/understand-onelink-short-vs-long-urls) s: Add parameters to your OneLink custom links or generate a large number of OneLink custom links by applying your own simple formulas in a spreadsheet.
- [App-to-web redirection](/docs/redirect-app-users-to-a-website): Redirect users from your app to a website or social media page.

## Troubleshooting and FAQ

Quickly find solutions for testing and debugging OneLink custom link redirection/behavior issues with our [OneLink troubleshooting guide](/docs/onelink-troubleshooting-and-faq).

## Limitations

- OneLink is not supported by the Meta mobile app install objective, where only Meta App Links are accepted.
- If your paid subscription plan lapses, certain OneLink links and features will no longer be available. This may affect ESP and branded domain links, disable SDK and API link creation and requests (unless separately purchased), and revoke access to web-to-app and bulk link creation.
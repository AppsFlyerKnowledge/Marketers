---
title: OneLink onboarding guide
metadata:
  keywords:
    - Marketers
    - set up
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-08-21T11:48:39Z'
  edited_at: '2026-05-13T07:07:16Z'
  id: 27699299657617
  locale: en-us
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/27699299657617-OneLink-onboarding-guide
---
> **At a glance**: Use OneLink for powerful, customized user redirection, deep linking, and attribution from your campaigns, regardless of user device, operating system, channel, or platform, for maximum conversion.

<div id="" />

## ![53010_Onelink.jpg](https://files.readme.io/c0d24ab87126bf765a89a25077b07d8678159cdb6f1b68eddc14a4cd2759b12a-30192941047185.jpg)

<div id="about-onelink" />

## About OneLink

AppsFlyer <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor> enables you to create links for your campaigns with attribution, redirection, and deep linking capabilities that convert owned media users into app users and engage existing users with smooth contextual journeys regardless of device, operating system, channel, or platform. Use OneLink to create personalized, contextual user journeys that drive users to your app to achieve the highest possible conversion rates and revenue. The personalized experiences you can create include:

* **Social-to-app**: Engage your users on social media and send them from social media feeds to your app.
* **App-to-app**: Lead users to your app from within other apps.
* <Anchor target="_blank" href="/marketers/docs/convert-your-mobile-web-visitors-to-app-users">**Web-to-app**</Anchor>: Convert your mobile website visitors into new mobile app users using Smart Banners and Smart Script. **Includes paid features**
* **QR-to-app**: Use QR codes to drive app installs by having users scan a QR code at key points during their offline customer experience. You can also put QR codes on your desktop site, or on TV and CTV ads to route users to your app.
* **Email-to-app**: Use email service providers (ESPs) to engage users via email and send them from their inbox to your app. **Includes paid features**
* **Text-to-app**: Create links for your SMS and messaging campaigns and engage users via text messages.
* **Referral-to-app**: Create user invite links that allow users and influencers to invite others to your app or share specific in-app content, for example, an article. **Includes paid features**
* **Custom**: Create a custom experience with a myriad of options for maximum customization. No matter where your users come from, whether via desktop or mobile, online or offline, owned or paid media, use OneLink to easily direct them to the right place.

**Note:** While basic OneLink setup is available on the free plans, most features require a paid AppsFlyer <Anchor target="_blank" href="/marketers/docs/account-management-plans-payments-and-billing#appsflyer-plans">subscription plan</Anchor>. 

<div id="onelink-onboarding" />

## OneLink onboarding

**To get started using OneLink, follow the steps below:**

<span id="h_01J5WC8Z4J352AHSDTRCEP2W9H"></span>**Prerequisites**

* An AppsFlyer <Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">account</Anchor> with at least one of your apps added.
* Most features require a paid AppsFlyer <Anchor target="_blank" href="/marketers/docs/account-management-plans-payments-and-billing#appsflyer-plans">subscription plan</Anchor>. For help, contact [hello@appsflyer.com](mailto:hello@appslfyer.com)
* To set up OneLink, you must be an AppsFlyer Admin user or have <Anchor target="_blank" href="/marketers/docs/user-management">permissions</Anchor> to add/edit OneLink templates.
* The <Anchor target="_blank" href="/marketers/docs/integrate-the-appsflyer-sdk">AppsFlyer SDK</Anchor> should be installed in your mobile apps for attribution of installs, in-app events, and deep linking.
  * If the SDK is not yet installed in your apps, it's still possible to create a working redirection link, but without attribution.

| Task | Purpose | Actions required | Who's involved |
| --- | --- | --- | --- |
| 1. Create a OneLink template | A OneLink template is the required base of redirection logic for the links you'll create. | <ul><li>Marketer/product manager: Set up a <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template">OneLink template</Anchor> in AppsFlyer.</li><li>Android developer: Configure app-opening methods for existing users (Android App Links and URI scheme).</li><li>iOS developer: Configure app-opening methods for existing users (iOS Universal Links and URI scheme).</li></ul><Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">Developer instructions</Anchor> | Marketer and developer |
| 2. Create a OneLink link | Create a OneLink link from your newly created template, for use in your campaign. | <ul><li>Marketer/product manager: Set up a <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link">OneLink link</Anchor> in AppsFlyer, including selecting the customer experience and adding any attribution and deep linking parameters.</li><li>Android and iOS developers: Set up <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep linking</Anchor> (if deep linking is required).</li></ul> | Marketer and developer |
| 3. Set up your domain redirect allowlist | For security, links you create in AppsFlyer will only redirect users to web URLs whose domains are in your allowlist. | Update the <Anchor target="_blank" href="/marketers/docs/set-up-your-domain-redirect-allowlist">domain redirect allowlist</Anchor> with all domains you want to redirect users to. | Marketer |
| 4. Test your new link | Test that your link successfully redirects:<ul><li>New users without your app installed</li><li>Existing users with your app installed</li></ul> | You can <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">test</Anchor> your newly created link. | Marketer |
| 5. Use the link confidently in your campaign, then measure the results |  | <ol><li>Add the new link to your campaign and serve it to your audience.</li><li>See the results of your campaign in the AppsFlyer Overview dashboard (filter by your campaign).</li></ol>Congratulations! You're all done onboarding to OneLink. | Marketer, data analyst |
| **Optional features** |  | Now that you're all set up, you can explore and discover additional OneLink features such as:<ul><li>Web-to-app: Transform web users into app users and measure web-to-app funnels.</li><li><Anchor target="_blank" href="/marketers/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> and <Anchor target="_blank" href="/marketers/docs/perform-onelink-bulk-actions-via-csv">bulk link creation</Anchor>: Scale and run multiple campaigns at once and create thousands of OneLink links quickly and easily.<br />*OneLink API requires an Enterprise subscription.</li><li><Anchor target="_blank" href="/marketers/docs/export-onelink-urls">Export OneLink URLs</Anchor>: Download your OneLink URLs created in AppsFlyer.</li><li><Anchor target="_blank" href="/marketers/docs/user-invite-attribution">User invite attribution</Anchor> - Create engagement by integrating user invite links created directly from the app.</li><li><Anchor target="_blank" href="/marketers/docs/cross-promotion-attribution-for-marketers">Cross-promotion attribution</Anchor>: Your existing app users are excellent candidates for installing your other new apps. Learn how to use SDK methods to create and measure cross-promotion campaigns.</li><li><Anchor target="_blank" href="/marketers/docs/understand-onelink-short-vs-long-urls">Long URLs</Anchor>: Add parameters to your OneLink custom links or generate a large number of OneLink custom links by applying your own simple formulas in a spreadsheet.</li></ul>**Note:** Most features require a paid AppsFlyer <Anchor target="_blank" href="/marketers/docs/account-management-plans-payments-and-billing#appsflyer-plans">subscription plan</Anchor>. | Marketer and developer |

If you need any help getting started with OneLink, reach out to your salesperson, or write to [hello@appsflyer.com](mailto:hello@appsflyer.com)

<div id="traits-and-limitations" />

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Owned media attribution in iPad Safari | When users click owned media links on an iPad using the Safari browser, the browser may report a **Macintosh-like user agent** instead of an iPad device model. As a result, AppsFlyer identifies the click as originating from a Mac device, while the app install is identified as originating from an iPad. Because probabilistic attribution relies on matching device characteristics between the click and the install, this mismatch prevents attribution and can result in unattributed installs or deferred deep linking failures. This limitation applies only to owned media traffic on iPad devices using Safari. |

<div data-zendesk-anchors="overview=about-onelink h_01J2G7RMHSPPXCWJ60W9HZASXX=about-onelink h_01HKHGX9JJQQCKF9SDZRSCM1XJ=about-onelink xyz-onboarding=onelink-onboarding h_01J2RJFH0B4R815CWDQNEB2C1P=onelink-onboarding h_01KFAG3N0X0W0RCJXK00KX038E=traits-and-limitations" />

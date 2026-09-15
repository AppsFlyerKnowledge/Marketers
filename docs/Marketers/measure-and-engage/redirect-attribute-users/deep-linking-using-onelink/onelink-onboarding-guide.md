---
title: "OneLink onboarding guide"
excerpt: "Use OneLink for powerful, customized user redirection, deep linking, and attribution from your campaigns across all devices and platforms."
---
At a glance: Use OneLink for powerful, customized user redirection, deep linking, and attribution from your campaigns, regardless of user device, operating system, channel, or platform, for maximum conversion.

![53010_Onelink.jpg](https://files.readme.io/c0d24ab87126bf765a89a25077b07d8678159cdb6f1b68eddc14a4cd2759b12a-30192941047185.jpg)

## About OneLink

AppsFlyer [OneLink](https://support.appsflyer.com/hc/articles/115005248543) enables you to create links for your campaigns with attribution, redirection, and deep linking capabilities that convert owned media users into app users and engage existing users with smooth contextual journeys regardless of device, operating system, channel, or platform. Use OneLink to create personalized, contextual user journeys that drive users to your app to achieve the highest possible conversion rates and revenue. The personalized experiences you can create include:

- **Social-to-app**: Engage your users on social media and send them from social media feeds to your app.
- **App-to-app**: Lead users to your app from within other apps.
- [**Web-to-app**](https://support.appsflyer.com/hc/articles/360001237818): Convert your mobile website visitors into new mobile app users using Smart Banners and Smart Script. **Includes paid features**
- **QR-to-app**: Use QR codes to drive app installs by having users scan a QR code at key points during their offline customer experience. You can also put QR codes on your desktop site, or on TV and CTV ads to route users to your app.
- **Email-to-app**: Use email service providers (ESPs) to engage users via email and send them from their inbox to your app. **Includes paid features**
- **Text-to-app**: Create links for your SMS and messaging campaigns and engage users via text messages.
- **Referral-to-app**: Create user invite links that allow users and influencers to invite others to your app or share specific in-app content, for example, an article. **Includes paid features**
- **Custom**: Create a custom experience with a myriad of options for maximum customization. No matter where your users come from, whether via desktop or mobile, online or offline, owned or paid media, use OneLink to easily direct them to the right place.

> 📘 Note
>
> While basic OneLink setup is available on the free plans, most features require a paid AppsFlyer [subscription plan](/docs/account-management-plans-payments-and-billing#appsflyer-plans).

## OneLink onboarding

**To get started using OneLink, follow the steps below:**

**Prerequisites**

- An AppsFlyer [account](https://www.appsflyer.com/sign-up/) with at least one of your apps added.
- Most features require a paid AppsFlyer [subscription plan](/docs/account-management-plans-payments-and-billing#appsflyer-plans). For help, contact [hello@appsflyer.com](mailto:hello@appslfyer.com)
- To set up OneLink, you must be an AppsFlyer Admin user or have [permissions](https://support.appsflyer.com/hc/articles/4409128270481) to add/edit OneLink templates.
- The [AppsFlyer SDK](https://support.appsflyer.com/hc/sections/6551164458257-Integrate-the-AppsFlyer-SDK) should be installed in your mobile apps for attribution of installs, in-app events, and deep linking.
  - If the SDK is not yet installed in your apps, it's still possible to create a working redirection link, but without attribution.

| Task | Purpose | Actions required | Who's involved |
| --- | --- | --- | --- |
| 1\. Create a OneLink template | A OneLink template is the required base of redirection logic for the links you'll create. | - Marketer/product manager: Set up a [OneLink template](https://support.appsflyer.com/hc/articles/207032246-OneLink-templates) in AppsFlyer.<br>- Android developer: Configure app-opening methods for existing users (Android App Links and URI scheme). <br>- iOS developer: Configure app-opening methods for existing users (iOS Universal Links and URI scheme). <br>[Developer instructions](https://support.appsflyer.com/hc/articles/207032246-OneLink-templates#add-redirection-logic-for-existing-app-users) | Marketer and developer |
| 2\. Create a OneLink link | Create a OneLink link from your newly created template, for use in your campaign. | - Marketer/product manager: Set up a [OneLink link](https://support.appsflyer.com/hc/articles/208874366-OneLink-links-and-experiences#create-a-onelink-link) in AppsFlyer, including selecting the customer experience and adding any attribution and deep linking parameters.<br>- Android and iOS developers: Set up [deep linking](https://support.appsflyer.com/hc/articles/208874366-OneLink-links-and-experiences#deep-linking-and-deferred-deep-linking)(if deep linking is required). | Marketer and developer |
| 3\. Set up your domain redirect allowlist | For security, links you create in AppsFlyer will only redirect users to web URLs whose domains are in your allowlist. | Update the [domain redirect allowlist](/docs/set-up-your-domain-redirect-allowlist) with all domains you want to redirect users to. | Marketer |
| 4\. Test your new link | Test that your link successfully redirects:<br>- New users without your app installed<br>- Existing users with your app installed | You can [test](https://support.appsflyer.com/hc/articles/208874366-OneLink-links-and-experiences#testing) your newly created link. | Marketer |
| 5\. Use the link confidently in your campaign, then measure the results | | 1. Add the new link to your campaign and serve it to your audience.<br>2. See the results of your campaign in the AppsFlyer [Overview dashboard](https://support.appsflyer.com/hc/articles/360014697157) (filter by your campaign).<br>Congratulations! You're all done onboarding to OneLink. | Marketer, data analyst |
| **Optional features** | | Now that you're all set up, you can explore and discover additional OneLink features such as: <br>- Web-to-app: Transform web users into app users and measure web-to-app funnels.<br>- [OneLink API](https://support.appsflyer.com/hc/articles/360001250345) and [bulk link creation](https://support.appsflyer.com/hc/articles/14511403892369): Scale and run multiple campaigns at once and create thousands of OneLink links quickly and easily.<br> <br> *OneLink API requires an Enterprise subscription.<br>- [Export OneLink URLs](https://support.appsflyer.com/hc/articles/4416027813905): Download your OneLink URLs created in AppsFlyer.<br>- [User invite attribution](/docs/user-invite-attribution) - Create engagement by integrating user invite links created directly from the app.<br>- [Cross-promotion attribution](https://support.appsflyer.com/hc/articles/115004481946-Cross-promotion-attribution): Your existing app users are excellent candidates for installing your other new apps. Learn how to use SDK methods to create and measure cross-promotion campaigns.<br>- [Long URLs](https://support.appsflyer.com/hc/articles/360017132597): Add parameters to your OneLink custom links or generate a large number of OneLink custom links by applying your own simple formulas in a spreadsheet.<br>**Note:** Most features require a paid AppsFlyer [subscription plan](/docs/account-management-plans-payments-and-billing#appsflyer-plans). | Marketer and developer |

If you need any help getting started with OneLink, reach out to your salesperson, or write to [hello@appsflyer.com](mailto:hello@appsflyer.com)

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Owned media attribution in iPad Safari | When users click owned media links on an iPad using the Safari browser, the browser may report a **Macintosh-like user agent** instead of an iPad device model. As a result, AppsFlyer identifies the click as originating from a Mac device, while the app install is identified as originating from an iPad. Because probabilistic attribution relies on matching device characteristics between the click and the install, this mismatch prevents attribution and can result in unattributed installs or deferred deep linking failures. This limitation applies only to owned media traffic on iPad devices using Safari. |
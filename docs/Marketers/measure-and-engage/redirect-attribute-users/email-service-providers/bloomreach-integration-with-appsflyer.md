---
title: "Bloomreach integration with AppsFlyer"
excerpt: "Set up an integration with Bloomreach to enable seamless deep linking from email campaigns, measure traffic in both Bloomreach and AppsFlyer, and create user experiences that drive conversion."
x-zendesk:
  id: 45235709425553
  url: https://support.appsflyer.com/hc/en-us/articles/45235709425553-Bloomreach-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Email service providers
  section_id: 6551247620881
  position: 3
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, OneLink]
  labels: [marketers]
  promoted: false
  comments_disabled: false
  created_at: '2026-03-29T13:30:32Z'
  edited_at: '2026-03-31T11:39:52Z'
---
![Bloomreach + AppsFlyer.png](https://files.readme.io/842523ac61d5f702a451b361d435e794f8dedad0f54eecffdf27f596c2cab262-45298084947473.png)

## About the integration

Bloomreach is an email marketing automation platform and email service provider (ESP) that helps brands create personalized experiences across channels.

The integration between AppsFlyer and Bloomreach enables smooth deep linking from email campaigns, supports accurate traffic measurement in both Bloomreach and AppsFlyer, and helps create seamless user experiences that drive conversion.

## Set up the integration

Setting up the integration requires actions in both AppsFlyer and Bloomreach. To set up the integration, follow the steps below:

<Accordion title="Step 1: In AppsFlyer, create and configure OneLink">

First, set up OneLink in AppsFlyer and confirm that the required hosting and domain settings are in place.

#### When your app is installed

Define the redirection behavior for users who already have your app installed.

**To define redirection behavior:**

1. [Create a OneLink template](/docs/create-a-onelink-template#create-a-onelink-template) and configure Universal Links/App Links. This template will be used later to create OneLink links for your email campaigns.
2. If you already have an existing OneLink template configured that enables Universal Links/App Links, you can use it.

#### Hosting and SSL

* OneLink links are SSL-secured and hosted by AppsFlyer.
* The AASA file and App Link files are also hosted by AppsFlyer.

See [additional information and instructions.](/docs/set-up-your-esp-integration-with-appsflyer#configure-your-app-to-support-deep-linking)

#### App domain definition

Example: For iOS, define the associated domain as follows:

```
applinks:<your-onelink-subdomain>.onelink.me
```

See [additional information and instructions.](https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links)

</Accordion>

<Accordion title="Step 2: In Bloomreach, define a Universal Link domain">

Next, define a Universal Link domain in Bloomreach so links can support deep linking while still being measured.

Domains defined in Bloomreach are not wrapped in a CDN click-tracking link when they are used in an email campaign, which enables deep linking.

An additional parameter is automatically appended to the original Universal Link to enable measurement through the Bloomreach web and mobile SDKs.

See [additional information and instructions.](https://documentation.bloomreach.com/engagement/docs/universal-link)

![2026-03-31_09-28-18.png](https://files.readme.io/4058ab59e2622f26327d9a4a62fa8afdc5965210acba9d9c5bb7a62d53a05503-45298084948753.png)

> 📘 **Example**
>
> Below is an example of an unwrapped Universal Link with Bloomreach tracking parameters appended:
>
> ```
> https://engmntqa.onelink.me/LtRd?pid=ESP_Bloomreach&c=esp-campaign&is_retargeting=true&utm_source=bloomreach&utm_medium=email&utm_campaign=Test-severla-link-yossi-26-10&xnpe_cmp=.eJwzPNrmPEXT6ZZjVKC-flJ-SqV-SWJSTqp-CYRdpF-SQrxItHEslJuSWaafmMWTsWTZufIm9r61XAs2AABFBChI.jF6UMukHXiw5lw
> ```

</Accordion>

<Accordion title="Step 3: In Bloomreach, implement mobile and web SDKs">

Finally, implement the relevant Bloomreach SDKs to ensure click measurement works correctly across mobile apps and the web.

#### iOS

Implement the Bloomreach [mobile SDK](https://documentation.bloomreach.com/engagement/docs/mobile-sdks) for iOS and ensure that Universal Link measurement is properly configured. The Bloomreach SDK supports measurement of Universal Links to capture user interactions initiated through email campaigns.

See additional information and instructions about [Universal Links](https://documentation.bloomreach.com/engagement/docs/ios-sdk-universal-links#track-universal-links) and [mobile SDKs.](https://documentation.bloomreach.com/engagement/docs/mobile-sdks)

#### Android

Implement the Bloomreach [mobile SDK](https://documentation.bloomreach.com/engagement/docs/mobile-sdks) for Android and configure App Links similarly to iOS Universal Links to ensure click attribution and measurement consistency.

See additional information and instructions about [Android App Links](https://documentation.bloomreach.com/engagement/docs/android-sdk-app-links#track-android-app-links) and [mobile SDKs.](https://documentation.bloomreach.com/engagement/docs/mobile-sdks)

#### Web

Implement the Bloomreach [JavaScript web SDK](https://Mobile%20SDKs) to ensure that clicks for Universal Links are measured on your website as well. Click measurement for Universal Links on your website will work with no additional configuration required.

See [additional information and instructions.](https://documentation.bloomreach.com/engagement/docs/js-sdk)

</Accordion>

<Accordion title="Step 4: Test the integration">

After you complete the setup, send a test email to validate the integration and confirm that deep linking and click measurement work as expected.

1. **Insert the OneLink link into a test email and send it to yourself.**

   Using your ESP email editor, add the OneLink link to a test email and send it to yourself. Ensure that the domain configured in Step 2 is used and that the link is not wrapped.
2. **Validate the link structure.**

   Open the test email and confirm that the OneLink is not wrapped by Bloomreach. In addition, verify that the `xnpe_cmp` parameter is appended to the link.
3. **Verify click measurement and OneLink behavior.**

   On your mobile device, open the email and click the link. Confirm that:

   * If the app is installed, it opens and deep links to the expected in-app content.
   * The click appears in the Bloomreach analytics dashboard.

Once all validations are complete, the integration setup is complete.

> 📘 **Note**
>
> If clicks do not appear in the Bloomreach platform, contact the Bloomreach Support team.

</Accordion>

> 📘 **Important notes**
>
> * AppsFlyer hosts and secures all relevant OneLink and association files, including AASA and App Link files.
> * Bloomreach SDKs for iOS, Android, and JavaScript must be implemented correctly for link measurement to work.
> * Universal Links and App Links should remain unwrapped, with Bloomreach parameters appended automatically.
> * This integration enables accurate email-to-app and email-to-web click attribution, as well as cross-channel engagement measurement.
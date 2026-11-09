---
title: Bloomreach integration with AppsFlyer
metadata:
  keywords:
    - marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2026-03-29T13:30:32Z'
  edited_at: '2026-10-01T00:35:29Z'
  id: 45235709425553
  locale: ja
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ja/articles/45235709425553
---
> **At a glance:** Set up an integration with Bloomreach to enable seamless deep linking from email campaigns, measure traffic in both Bloomreach and AppsFlyer, and create user experiences that drive conversion.

<Image align="center" alt="Bloomreach + AppsFlyer.png" src="https://files.readme.io/842523ac61d5f702a451b361d435e794f8dedad0f54eecffdf27f596c2cab262-45298084947473.png" width="645px" />

## About the integration

Bloomreach is an email marketing automation platform and email service provider (ESP) that helps brands create personalized experiences across channels.

The integration between AppsFlyer and Bloomreach enables smooth deep linking from email campaigns, supports accurate traffic measurement in both Bloomreach and AppsFlyer, and helps create seamless user experiences that drive conversion.

## Set up the integration

Setting up the integration requires actions in both AppsFlyer and Bloomreach. To set up the integration, follow the steps below:

<div id="step-1-in-appsflyer-create-and-configure-onelink" />

<Accordion title="Step 1: In AppsFlyer, create and configure OneLink">

First, set up OneLink in AppsFlyer and confirm that the required hosting and domain settings are in place.

#### When your app is installed

Define the redirection behavior for users who already have your app installed.

**To define redirection behavior:**

1. <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">Create a OneLink template</Anchor> and configure Universal Links/App Links. This template will be used later to create OneLink links for your email campaigns.
2. If you already have an existing OneLink template configured that enables Universal Links/App Links, you can use it.

#### Hosting and SSL

* OneLink links are SSL-secured and hosted by AppsFlyer.
* The AASA file and App Link files are also hosted by AppsFlyer.

See <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer#ディープリンクをサポートするようにアプリを設定します">additional information and instructions.</Anchor>

#### App domain definition

Example: For iOS, define the associated domain as follows:

```text
applinks:<your-onelink-subdomain>.onelink.me
```

See <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">additional information and instructions.</Anchor>

</Accordion>

<div id="step-2-in-bloomreach-define-a-universal-link-domain" />

<Accordion title="Step 2: In Bloomreach, define a Universal Link domain">

Next, define a Universal Link domain in Bloomreach so links can support deep linking while still being measured.

Domains defined in Bloomreach are not wrapped in a CDN click-tracking link when they are used in an email campaign, which enables deep linking.

An additional parameter is automatically appended to the original Universal Link to enable measurement through the Bloomreach web and mobile SDKs.

See <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/universal-link">additional information and instructions.</Anchor>

<Image align="center" alt="2026-03-31_09-28-18.png" src="https://files.readme.io/4058ab59e2622f26327d9a4a62fa8afdc5965210acba9d9c5bb7a62d53a05503-45298084948753.png" width="73.36%" />

> 📄 **Example**
>
> Below is an example of an unwrapped Universal Link with Bloomreach tracking parameters appended:
>
> ```text
> https://engmntqa.onelink.me/LtRd?pid=ESP_Bloomreach&c=esp-campaign&is_retargeting=true&utm_source=bloomreach&utm_medium=email&utm_campaign=Test-severla-link-yossi-26-10&xnpe_cmp=.eJwzPNrmPEXT6ZZjVKC-flJ-SqV-SWJSTqp-CYRdpF-SQrxItHEslJuSWaafmMWTsWTZufIm9r61XAs2AABFBChI.jF6UMukHXiw5lw
> ```

</Accordion>

<div id="step-3-in-bloomreach-implement-mobile-and-web-sdks" />

<Accordion title="Step 3: In Bloomreach, implement mobile and web SDKs">

Finally, implement the relevant Bloomreach SDKs to ensure click measurement works correctly across mobile apps and the web.

#### iOS

Implement the Bloomreach <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">mobile SDK</Anchor> for iOS and ensure that Universal Link measurement is properly configured. The Bloomreach SDK supports measurement of Universal Links to capture user interactions initiated through email campaigns.

See additional information and instructions about <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/ios-sdk-universal-links#track-universal-links">Universal Links</Anchor> and <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">mobile SDKs.</Anchor>

#### Android

Implement the Bloomreach <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">mobile SDK</Anchor> for Android and configure App Links similarly to iOS Universal Links to ensure click attribution and measurement consistency.

See additional information and instructions about <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/android-sdk-app-links#track-android-app-links">Android App Links</Anchor> and <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">mobile SDKs.</Anchor>

#### Web

Implement the Bloomreach <Anchor target="_blank" href="https://Mobile%20SDKs">JavaScript web SDK</Anchor> to ensure that clicks for Universal Links are measured on your website as well. Click measurement for Universal Links on your website will work with no additional configuration required.

See <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/js-sdk">additional information and instructions.</Anchor>

</Accordion>

<div id="step-4-test-the-integration-by-sending-a-test-email" />

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

<div data-zendesk-anchors="h_01KMWVJR5AQRY8YRAD6ZV6H1VV=about-the-integration h_01KMWVJR5ACS7Q1GKP1GGGBRYK=set-up-the-integration h_01KMWVJR5ABTK766X4G0B9J92E=step-1-in-appsflyer-create-and-configure-onelink h_01KMWVJR5AY8WRV4Y6GTWHDE5D=when-your-app-is-installed h_01KMWVJR5A40099PC91YW2QR1D=hosting-and-ssl h_01KMWVJR5A7JV0FHC5W1EP9502=app-domain-definition h_01KMWVJR5A57Y1ZPAYBC5321DX=step-2-in-bloomreach-define-a-universal-link-domain h_01KMWVJR5BER86B8YV3H60PGF6=example h_01KMWVJR5B6K6EG49VJM7JSEK2=step-3-in-bloomreach-implement-mobile-and-web-sdks h_01KMWVJR5B3505FSJSXRC9NQ4A=ios h_01KMWVJR5BE703X877C40DZ5MX=android h_01KMWVJR5BVTXS8W2WGTYEGP0D=web h_01KMWVJR5BPA0N2YTK2983DHMT=step-4-test-the-integration-by-sending-a-test-email h_01KMWVJR5B6PHSEK7NA5W8ZGNF=note h_01KN1TCDE27DNPJJ8HRHZ4FPA0=important-notes" />

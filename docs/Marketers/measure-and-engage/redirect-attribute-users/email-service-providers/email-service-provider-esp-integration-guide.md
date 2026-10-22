---
title: Email service provider (ESP) integration guide
metadata:
  keywords:
    - Email
    - Advertisers
    - Developers
    - Premium
    - Email service providers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-12-31T10:43:24Z'
  edited_at: '2026-09-23T11:00:22Z'
  id: 360004556077
  locale: en-us
  section: Email service providers
  section_id: 6551247620881
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360004556077-Email-service-provider-ESP-integration-guide
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**At a glance:** Create email campaigns with integrated ESPs using OneLink branded links and deep linking for seamless user experiences that drive conversion (for those using iOS Universal Links or Android App Links).

## About ESP integration

Email marketing is a simple, powerful, and effective way of engaging with customers and potential customers. Many marketers rely on email service providers (ESPs) to send large-scale email campaigns to their users. And while this should be a straightforward and simple process, delivering the perfect mobile user journey you envision, this is usually not the case.

**What's the challenge?**

The issues arise as a result of how the typical ESP handles its analytics, which tends to break deep links and negatively affect the mobile user experience. Deep linking refers to sending users directly to a specific location inside your app, which is a crucial functionality in effecting conversion. Providing a smooth deep-linking experience in email campaigns sent by ESPs is a real challenge as ESPs "wrap" the deep links for measurement purposes, which breaks the app-domain association required for iOS Universal links and Android App Links. This unfortunately results in:

* Routing users to mobile websites instead of deep linking them into the app
* Using the URI scheme deep-linking method which is less secure and provides a poor user experience

<Image alt="53242 KB.png" src="https://files.readme.io/53db119f60e3fe2dfaf58b8a87e14595eeb9dde375bf87f7617f36a463ee0ced-30227717940753.png" width="688px" />

**What's the solution?**

To avoid these issues and provide mobile users with the best experience, click on your ESP in the section below and follow the specific integration instructions. Some ESPs are supported by an AppsFlyer integration solution that enables AppsFlyer to serve as an intermediary between the ESP server and your domain name. Its role as a proxy enables the provision of association files (AASA / asset links) which facilitates deep linking.

The AppsFlyer ESP integration solution is a premium feature. If you'd like to learn more about it or get started, contact us at [hello@appsflyer.com](mailto:hello@appsflyer.com).

## Supported ESPs

ESP email campaigns for mobile app users can cause attribution and deep linking issues. To avoid these issues, click on your ESP in the section below and follow the AppsFlyer ESP integration instructions in the link.

| Supported ESP list | Uses AppsFlyer integration method |
| --- | --- |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Acoustic logo" src="https://files.readme.io/b3dac2e0a4f326da76584ed95ee2cd61683edff054c67110c56b95a361444acb-38086051586577.svg" width="86px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/adobe-esp-integration-with-appsflyer"><Image alt="Adobe logo" src="https://files.readme.io/62926ce91dac3216426360869fc3d3adfe7a73e009cca47ecabb4a41b973b457-51177578838545.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="AWS SES logo" src="https://files.readme.io/371a43248e0c88469a5a4599c501da148745c3b12d080f114dbb385ef9a7f899-46799108961937.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Blueshift logo" src="https://files.readme.io/038b29f54fdb4e20775d7c1af0e6543a78351abdfad8b8d7d029a1fdd5b5de7b-32377991388945.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Braze logo" src="https://files.readme.io/41e9614c7a35cd18f1d17d5958d6a7243e53a1af0a3e56935342b90103d7be20-32378022189969.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="CleverTap logo" src="https://files.readme.io/f3190c5c82b380e93d70bbccccf279f78decf6a223bcab3ca62958356202e1a1-32378022192657.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Customer.io logo" src="https://files.readme.io/e893909294e6397226b10dbad55f06644cf7a9e6db0a3020280495a9d17fc53c-32378022194833.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Emarsys logo" src="https://files.readme.io/449120ed88bb0540b758530ca5d8884e2e8210485859b17eb272d61e218566a1-32378022206737.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="ExpertSender logo" src="https://files.readme.io/25141c53c10b3f2eed600567b04849dda88f6b379bb71ae00bcc2e85fa0171e7-32377991413393.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Insider logo" src="https://files.readme.io/544b4f408b64e99e037cfca238c578185db66d87d85f7d329e39d62b253ba618-36655909659153.svg" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Klaviyo logo" src="https://files.readme.io/4144e48e7c072ec2034671752a02398e98bb023cda647f37986e953772d97f89-41351882139409.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="MailExpress logo" src="https://files.readme.io/7a196f7d2825ea7dbb14a7deda4af907c5056957b63e93c53a7550bd8394a5c4-32377991435921.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Mailgun logo" src="https://files.readme.io/4a19bb320d3abf176ca3bb2384f4de5a06d8e2f1925df2fc6e082372b711b19a-32377991438865.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Mindbox logo" src="https://files.readme.io/5fdc6f90d39879c994298762de429528719f9be0f08e78ac25f1d2a6240d20f2-50865749335057.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Moengage logo" src="https://files.readme.io/d2316501fe1f428d4337a4924a59e93545b50171d173b3371bdd4dd180805509-32377991440913.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Ongage logo" src="https://files.readme.io/d3dd0839abd7ee6fbcf065a815d71a20885b0a09beabd37452c47d0396ee1d6e-32378022240273.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="ESP logo (name unconfirmed)" src="https://files.readme.io/25e13e60d862c3694e698ecd66d1a26e5d8e1a1849c5ded15ad308e1c8d99b6e-44854095773457.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="RD Station logo" src="https://files.readme.io/91a24e7341c87484a4c06d077a1ee7fd7a04b3817b63ced27cec944421ca58aa-32378022248977.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Reteno logo" src="https://files.readme.io/4e1d8fab29601c1d3c2015a7253258a9c152cd987ee6c5f0125c6f6e79a370a1-32377991454609.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Sailthru logo" src="https://files.readme.io/61b721936f4f9cc64ee9551a213865eca2bea188599311f79d92d945204a713b-32378022253841.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="SendGrid logo" src="https://files.readme.io/f4c3217e956db7e922a6150597d596c2c4848e5aa0a43b2347824aacbeb2caa3-32378022256785.png" height="40px" /></Anchor> | Yes |
| <Anchor target="_blank" href="/marketers/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="SparkPost logo" src="https://files.readme.io/bec55e3c96bb80b736777e110d05df9009e015ef2c1cdd8b3d8088880264f593-32377991460369.png" height="40px" /></Anchor> | Yes |

## Other ESPs

Here's a list of other ESPs that, while not supported by the AppsFlyer ESP integration, have their own methods for handling the attribution and deep linking issues discussed above. To implement their methods, find your ESP in the section below and follow their integration instructions in the links provided.

| ESP list | Uses AppsFlyer integration method |
| --- | --- |
| Bloomreach | No. Uses their own redirection method. Learn how to <Anchor target="_blank" href="/marketers/docs/bloomreach-integration-with-appsflyer">integrate with Bloomreach.</Anchor> |
| EmailLabs | No. Uses their own redirection method. Learn how to <Anchor target="_blank" href="/marketers/docs/emaillabs-integration-with-appsflyer">integrate with EmailLabs</Anchor>. |
| Iterable | No. Uses their own redirection method. Learn how to <Anchor target="_blank" href="/marketers/docs/iterable-integration-with-appsflyer">integrate with Iterable.</Anchor> |
| Oracle | No. Uses their own redirection method. Learn how to <Anchor target="_blank" href="/marketers/docs/oracle-responsys-integration-with-appsflyer">integrate with Oracle.</Anchor> |
| Salesforce | No. Uses their own redirection method. Learn how to <Anchor target="_blank" href="/marketers/docs/salesforce-marketing-cloud-sfmc-integration-with-appsflyer">integrate with Salesforce</Anchor>. |

<div data-zendesk-anchors="overview=about-esp-integration h_01J3JHJCCASM6E5QYJB5VHQ8HK=about-esp-integration supported-email-service-providers=supported-esps h_01H92VH355BQ13SP72VNJEKW1E=supported-esps h_01K06J2Z9QRW4VPVBP6QT81W8Y=other-esps" />

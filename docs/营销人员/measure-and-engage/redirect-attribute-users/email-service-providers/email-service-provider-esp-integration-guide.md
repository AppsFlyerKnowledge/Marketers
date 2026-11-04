---
title: ESP（邮件营销服务商）对接
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
  edited_at: '2026-10-14T10:00:10Z'
  id: 360004556077
  locale: zh-cn
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/zh-cn/articles/360004556077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 使用OneLink品牌链接与深度链接，通过对接的电子邮件服务商（ESP）创建邮件营销活动，为用户打造顺畅衔接的体验旅程，从而有效提升转化率。

<div id="about-esp-integration" />

## 关于ESP对接

电子邮件营销是一种简单、高效、极具影响力的营销方式，可用于与现有客户及潜在客户建立联系。许多营销人员依赖ESP批量发送营销邮件。而虽然这一流程看似十分简洁明了，但要打造出理想的移动端用户体验往往并非易事。

**有哪些挑战?**

广告主面临的许多问题根源在于大多数ESP（电子邮件服务提供商）在处理分析数据时，往往会导致深度链接无法跳转，从而影响移动端用户体验。深度链接指可以将用户直接引导至应用内指定页面的链接，如使用得当，深度链接可显著提高转化率。但在通过ESP发送的邮件营销活动中，要实现顺畅的深度链接体验并非易事。这是因为ESP通常会对深度链接进行“包装”，以便进行数据追踪。这种包装会破坏iOS的通用链接（Universal Links）和Android App Links所需的关联域名。由此可能导致：

* 用户跳转至移动网页，而非直接跳转至应用内目标页面
* 广告主不得不使用安全性低、用户体验差的URI scheme链接。

<Image alt="53242 KB.png" src="https://files.readme.io/53db119f60e3fe2dfaf58b8a87e14595eeb9dde375bf87f7617f36a463ee0ced-30227717940753.png" width="688px" />

**如何解决？**

为确保移动端用户获得理想体验，建议您在下方查看各类ESP的对接说明进行配置。部分ESP已支持AppsFlyer的对接方案，允许广告主借助AppsFlyer将ESP服务器与域名进行关联。通过代理机制，AppsFlyer可为您的域名提供必要的关联文件（如AASA或Asset Links），从而实现稳定可靠的深度链接跳转体验。

<div id="other-esps" />

<div id="supported-esps" />

## 支持的ESP

向移动应用用户发送的ESP邮件广告可能会出现归因和深度链接问题。为了避免这些问题，请点击以下ESP，并按照链接中的具体说明进行操作。

| 支持的ESP | 是否支持AppsFlyer beta测试版对接 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="acoustic logo.svg" src="https://files.readme.io/b3dac2e0a4f326da76584ed95ee2cd61683edff054c67110c56b95a361444acb-38086051586577.svg" width="211px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB blueshift.png" src="https://files.readme.io/038b29f54fdb4e20775d7c1af0e6543a78351abdfad8b8d7d029a1fdd5b5de7b-32377991388945.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB braze.png" src="https://files.readme.io/41e9614c7a35cd18f1d17d5958d6a7243e53a1af0a3e56935342b90103d7be20-32378022189969.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB CleverTap.png" src="https://files.readme.io/f3190c5c82b380e93d70bbccccf279f78decf6a223bcab3ca62958356202e1a1-32378022192657.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB customer.io.png" src="https://files.readme.io/e893909294e6397226b10dbad55f06644cf7a9e6db0a3020280495a9d17fc53c-32378022194833.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/emaillabs-integration-with-appsflyer"><Image alt="53798 KB EmailLabs (1).png" src="https://files.readme.io/ed7d3195cd15a43dcdee30fbb7984308dc47bf43df76c5413ef03f51d23566ee-51911130280977.png" width="343px" /></Anchor> | 不支持。仅支持自有跳转方式 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB emarsys.png" src="https://files.readme.io/449120ed88bb0540b758530ca5d8884e2e8210485859b17eb272d61e218566a1-32378022206737.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB expertsender.png" src="https://files.readme.io/25141c53c10b3f2eed600567b04849dda88f6b379bb71ae00bcc2e85fa0171e7-32377991413393.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Insider (1).svg" src="https://files.readme.io/544b4f408b64e99e037cfca238c578185db66d87d85f7d329e39d62b253ba618-36655909659153.svg" width="145px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/iterable-integration-with-appsflyer"><Image alt="53798 KB ITERABLE (1).png" src="https://files.readme.io/f4a1f2647bedbba13d247432620794355b42e69ddef6a88998484dc381f4a07a-51911130286993.png" width="343px" /></Anchor> | 不支持。仅支持自有跳转方式 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB klaviyo.png" src="https://files.readme.io/9228e85d708ca912bd06ccaba32b6e0bf681573a11ecef276252dd13f283be9d-51911130289169.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB MailExpress (2).png" src="https://files.readme.io/7a196f7d2825ea7dbb14a7deda4af907c5056957b63e93c53a7550bd8394a5c4-32377991435921.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB Mailgun.png" src="https://files.readme.io/4a19bb320d3abf176ca3bb2384f4de5a06d8e2f1925df2fc6e082372b711b19a-32377991438865.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB moengage.png" src="https://files.readme.io/d2316501fe1f428d4337a4924a59e93545b50171d173b3371bdd4dd180805509-32377991440913.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB ongage.png" src="https://files.readme.io/d3dd0839abd7ee6fbcf065a815d71a20885b0a09beabd37452c47d0396ee1d6e-32378022240273.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/oracle-responsys-integration-with-appsflyer"><Image alt="53798 KB ORACLE (1).png" src="https://files.readme.io/358270bfbce36b0c323c6a8057246f7a56eb9563061e76d87efc7e7e6736fee7-51911130290321.png" width="343px" /></Anchor> | 不支持。仅支持自有跳转方式 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB RD STATION.png" src="https://files.readme.io/91a24e7341c87484a4c06d077a1ee7fd7a04b3817b63ced27cec944421ca58aa-32378022248977.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB Reteno.png" src="https://files.readme.io/4e1d8fab29601c1d3c2015a7253258a9c152cd987ee6c5f0125c6f6e79a370a1-32377991454609.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB SAILTHRU.png" src="https://files.readme.io/61b721936f4f9cc64ee9551a213865eca2bea188599311f79d92d945204a713b-32378022253841.png" width="343px" /></Anchor> | 是 |
| <Image alt="salesforce.png" src="https://files.readme.io/4f92bf21312489f04f86d876ac1ec06a19d6241bb2ed451e8beb30113a19d48c-51911130291473.png" width="147px" /> | 不支持。仅支持自有跳转方式 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB sendgrid.png" src="https://files.readme.io/f4c3217e956db7e922a6150597d596c2c4848e5aa0a43b2347824aacbeb2caa3-32378022256785.png" width="343px" /></Anchor> | 是 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB SPARKPOST.png" src="https://files.readme.io/bec55e3c96bb80b736777e110d05df9009e015ef2c1cdd8b3d8088880264f593-32377991460369.png" width="343px" /></Anchor> | 是 |

<div data-zendesk-anchors="overview=%E5%85%B3%E4%BA%8Eesp%E5%AF%B9%E6%8E%A5 h_01J3JHJCCASM6E5QYJB5VHQ8HK=%E5%85%B3%E4%BA%8Eesp%E5%AF%B9%E6%8E%A5 supported-email-service-providers=%E6%94%AF%E6%8C%81%E7%9A%84esp h_01H92VH355BQ13SP72VNJEKW1E=%E6%94%AF%E6%8C%81%E7%9A%84esp" />

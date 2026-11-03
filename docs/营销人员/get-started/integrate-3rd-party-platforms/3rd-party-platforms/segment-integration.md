---
title: Segment对接
metadata:
  keywords:
    - Integration
    - segment IO
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-30T07:54:38Z'
  edited_at: '2026-10-14T10:14:10Z'
  id: 210041606
  locale: zh-cn
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/zh-cn/articles/210041606
---
> **概要：** 本文为您介绍了将Segment分析数据发送至AppsFlyer的方法。

## 简介

Segment可将您的数据传送到AppsFlyer。通过Segment的开源库采集数据后，数据会被转换为相应格式并传输至AppsFlyer。借助AppsFlyer，营销人员能够更精准地锁定目标受众、优化广告支出并提升ROI。

## Segment与AppsFlyer的对接

请参考<Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/">Segment的指南</Anchor>，了解如何将Segment与AppsFlyer的对接。

## 常见问题解答

<div id="how-can-i-integrate-segment-with-appsflyer" />

<Accordion title="如何将Segment与AppsFlyer对接？">

请按照以下步骤操作：

* 在Segment面板中<Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">配置连接至AppsFlyer</Anchor>。
* 在您的应用中对接[Segment Wrapper SDK](/docs/segment-integration#how-does-the-sdk-wrapper-work)：
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-swift-appsflyer">iOS自有应用</Anchor>
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-kotlin-appsflyer">Android自有应用</Anchor>

</Accordion>

<div id="what-sdks-do-i-need-to-add-to-my-app" />

<Accordion title="我需要将哪些SDK添加到我的应用中？">

您只需添加Segment SDK Wrapper。添加完成后，应用会在构建过程中自动添加Segment SDK和AppsFlyer SDK。

</Accordion>

<div id="how-does-the-sdk-wrapper-work" />

<Accordion title="SDK Wrapper的工作原理是什么？">

Segment SDK Wrapper连接了Segment SDK与AppsFlyer SDK。

当您使用Segment SDK Wrapper来调用Segment提供的接口以记录激活和应用内事件时，SDK Wrapper会同时调用Segment和AppsFlyer的接口。

这样能够节省开发时间和人力，减少额外的编码工作。

> ❗️ **重要提示**
>
> 请勿同时调用Segment SDK Wrapper和AppsFlyer SDK的接口。否则可能会导致错误和数据不一致。
>
> **只需使用Segment SDK Wrapper提供的端口即可。**

</Accordion>

<div id="is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk" />

<Accordion title="Segment SDK Wrapper和AppsFlyer SDK在功能上有区别吗？">

没有区别。Segment SDK Wrapper中包含了AppsFlyer SDK的全部功能。

</Accordion>

<div id="i-dont-see-inapp-event-data-in-the-appsflyer-dashboard" />

<Accordion title="为什么我在AppsFlyer面板中看不到应用内事件数据？">

* 请确保按照说明正确部署Segment SDK Wrapper中的track接口：
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyer-Segment-Integration#adding_events">安卓</Anchor>
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/blob/master/examples/SwiftPodsSample/SwiftPodsSample/ViewController.swift">iOS</Anchor>
* 在Segment面板中对接AppsFlyer时，请务必填写您的<Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">开发者密钥</Anchor>（dev key）。

</Accordion>

<div id="install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match" />

<Accordion title="为什么Segment和AppsFlyer中的激活或应用内事件数据不一致？">

请确保仅使用Segment SDK Wrapper，不要同时使用AppsFlyer SDK。点击[此处](/docs/segment-integration#how-does-the-sdk-wrapper-work)了解更多信息。

此外，也可参见上述[常见问题解答](/docs/segment-integration#i-dont-see-inapp-event-data-in-the-appsflyer-dashboard)了解其他原因。

</Accordion>

<div id="im-getting-a-validation-error-when-testing-events-in-segment" />

<Accordion title="在Segment中测试事件时出现验证错误怎么办？">

当您在***Destination***页面使用***Event Tester***测试事件时，可能会看到如下错误信息：***Validation Error AppsFlyer Device ID ('integrations.AppsFlyer.appsFlyerId') is required to send server to server events***.

这并不代表Segment与AppsFlyer的对接存在问题。Event Tester测试的是从Segment到AppsFlyer的S2S回传事件，此类事件必须包含AppsFlyerID，因此才会报错。

但这种情况仅适用于S2S事件。当您使用Segment SDK API来记录事件时，事件会通过SDK同时发送到Segment和AppsFlyer。在发送给AppsFlyer的API调用中，系统会自动包含AppsFlyer设备ID。

</Accordion>

<div id="im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

<Accordion title="我在使用第三方分析工具，是否需要分别对接到AppsFlyer和Segment？">

不需要。您只需在Segment面板中启用相应的第三方分析工具即可。

</Accordion>

<div data-zendesk-anchors="introduction=%E7%AE%80%E4%BB%8B h_01JZMD855TA62KQ4AWJ5F6WSDP=%E7%AE%80%E4%BB%8B integrating-segment-with-appsflyer=segment%E4%B8%8Eappsflyer%E7%9A%84%E5%AF%B9%E6%8E%A5 h_01JZMD855TNEYZG1MDZY7FWV8S=segment%E4%B8%8Eappsflyer%E7%9A%84%E5%AF%B9%E6%8E%A5 faqs=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01JZMD855TAEBDPAMEAEH66F27=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01JZMD855T2BXFR1AKRNAA7M51=how-can-i-integrate-segment-with-appsflyer h_01JZMD855TG3WEKQH21JJ1PT43=what-sdks-do-i-need-to-add-to-my-app h_01JZMD855TW07PGDA6QHFWPN67=how-does-the-sdk-wrapper-work h_01JZMD855TNZGKVY2G98FPM22Z=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01JZMD855T0BEENPF0BMQDBFS8=is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk h_01JZMD855TV6J44PAV1A7JCKT5=i-dont-see-inapp-event-data-in-the-appsflyer-dashboard h_01JZMD855TH07JNZBT8CN4026W=install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match h_01JZMD855TY8X2PV1HB8Y0QT6Z=im-getting-a-validation-error-when-testing-events-in-segment h_01JZMD855TCE97QW8TSBEN1DYY=im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

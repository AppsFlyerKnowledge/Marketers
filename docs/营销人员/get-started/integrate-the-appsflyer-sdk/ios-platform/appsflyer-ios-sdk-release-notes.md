---
title: AppsFlyer iOS SDK版本说明
metadata:
  keywords:
    - Advertisers
    - Release Notes
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-03-09T19:49:54Z'
  edited_at: '2026-10-14T10:12:08Z'
  id: 115001224823
  locale: zh-cn
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/zh-cn/articles/115001224823
---
> **概要：** 本文将为您简要介绍iOS SDK的近期更新。对于开发人员，如果需要更全面的信息，请查看<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">Dev Hub中的安卓版本说明</Anchor>。

<strong>AppsFlyer将按照原计划，在六个月的周期内，逐步停止对iOS和Android旧版SDK的支持。</strong>此机制旨在为广告主预留充足时间，以便开发团队提前规划和升级，确保应用功能不受影响。请及时升级到最新版SDK，体验最新功能、更高稳定性和持续的技术支持。

<div id="important" />

> 🚧 **重要提示！**
>
> 为了确保平稳过渡，建议应用开发者在停止支持日期前完成SDK升级。

<div id="end-of-support-vs-deprecated" />

## 停止支持与弃用的区别

为了更清晰地区分SDK的支持状态及其对数据衡量的影响，AppsFlyer将旧版SDK分为以下两类：

* **弃用版本**由于存在已知问题（如严重Bug），官方不再推荐使用的SDK版本。这些版本仍然可以向AppsFlyer发送数据，但不鼓励开发者继续使用，我们强烈建议您升级到受支持的版本。
* **停止支持版本：** 不再进行任何数据衡量的SDK版本。在iOS和Android平台上，激活、应用打开和应用内事件都将无法被记录。来自这类版本的请求（除非被AppsFlyer特别豁免）将收到400错误码，表示虽然SDK会继续尝试发送请求，但AppsFlye 服务器将拒绝处理，数据也不会被接收或存储。

<div id="ios-sdk-release-notes" />

## iOS SDK版本说明

下表列出了当前受支持的iOS SDK版本、发布时间以及对其他重要信息。如需了解其他信息，请参见<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk">iOS SDK对接指南</Anchor>。

| 版本 | 发布日期 | 说明 |
| --- | --- | --- |
| 6.17.7 | 2025-10-15 | <ul><li>修复了从Google ICM库获取数据的问题</li></ul> |
| 6.17.6 | 2025-09-21 | <ul><li>修复了在v6.17.3中出现的问题，该问题可能导致SDK在尝试将ICM数据发送到AppsFlyer时崩溃。</li></ul> |
| 6.17.5  <br />弃用的区别 | 2025-09-03 | <ul><li>**该版本已弃用，请勿使用。**</li></ul> |
| 6.17.4  <br />弃用的区别 | 2025-08-27 | <ul><li>**该版本已弃用，请勿使用。**</li><li>修复了在极少数情况下，SDK初始化时应用程序崩溃的问题。</li></ul> |
| 6.17.3  <br />弃用的区别 | 2025-08-21 | <ul><li>**该版本已弃用，请勿使用。**</li><li>更新了从Google的ICM库获取数据的逻辑，以提高准确性。</li></ul> |
| 6.17.2 | 2025-07-15 | <ul><li>更新了`validateAndLogInAppPurchase`API（测试版）</li><li>优化了Apple Search Ads (ASA) 令牌的处理方式，适用于已获取ATT（AppTrackingTransparency）授权的应用</li></ul> |
| 6.17.1 | 2025-06-24 | <ul><li>新增对<Anchor target="_blank" href="https://support.google.com/google-ads/answer/16203286">Google ICM</Anchor>（对接转化衡量）的支持。</li><li>修复了在开发环境中运行SDK时可能弹出App Store登录窗口的问题</li></ul> |
| 6.17.0 | 2025-04-23 | <ul><li>提升了稳定性和性能</li></ul> |
| 6.16.2 | 2025-03-10 | <ul><li>进行了必要的技术更新，以支持在插件中发布该版本</li></ul> |
| 6.16.1 | 2025-02-18 | <ul><li>更新了API，支持将DMA同意数据手动发送到AppsFlyer。</li></ul> |
| 6.16.0 | 2025-01-19 | <ul><li>新增通过Purchase Connector上报苹果StoreKit 2 API的订阅和应用内购买数据。该功能目前处于Beta测试阶段。</li></ul> |
| 6.15.3 | 2024-09-23 | SDK维护 |
| 6.15.2 | 2024-08-28 | <ul><li>修复了Purchase Connector中的事件传输问题。此次修复不会影响Purchase Connector的任何生产版本（Production Version），且与Purchase Connector更新到6.15.x版本有关。</li></ul> |
| 6.15.1 | 2024-08-19 | <ul><li>修复了设备中同时安装同一厂商的多个应用时发生的重装激活检测问题。</li></ul> |
| 6.15.0 | 2024-08-06 | <ul><li>添加了`logAdRevenue` API，用于向AppsFlyer发送广告收入数据。 **请注意：** 从这个版本开始，请务必弃用AdRevenue Connector，并以`logAdRevenue`方法替代。详情请见[此处](https://dev.appsflyer.com/hc/docs/ad-revenue-2)说明。</li><li>与Purchase Connector有关的内部更新。使用Purchase Connector的应用以及更新到此版本SDK的应用都必须将其Purchase Connector更新到v6.15.0。</li></ul> |
| 6.14.6 | 2024-07-24 | <ul><li>修复了新session开启时SDK对`getConversionData`API（GCD）进行不必要调用的问题；该问题不影响数据监测。</li></ul> |
| 6.14.5 | 2024-07-03 | <ul><li>问题修复：SDK在发送手动授权的代码已移除的情况下，仍发送用户在应用中设置的手动授权数据。</li></ul> |
| 6.14.4 | 2024-06-10 | <ul><li>更新了<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">严格模式SDK</Anchor>的隐私清单（Privacy Manifest）。</li></ul> |
| 6.14.3 | 2024-04-26 | <ul><li>修复了使用Cocoapods自动化合并应用隐私清单（Privacy Manifest）的功能。</li></ul> |
| 6.14.2 | 2024-04-19 | SDK维护 |
| 6.14.1 | 2024-04-18 | <ul><li>更新后支持最新的购买验证（Purchase Validation）链路。该功能目前处于Beta测试阶段。了解详情</li></ul> |
| 6.14.0 | 2024-04-07 | <ul><li>更新后支持隐私清单（Privacy Manifest）如需进一步了解AppsFlyer的隐私清单（Privacy Manifest），请参考<Anchor target="_blank" href="/marketers/zh/docs/implement-privacy-manifest-in-your-app">此文档</Anchor>。</li><li>在SDK中添加了XCFramework签名，允许开发人员使用Xcode 15验证SDK的来源（origin）及真实性（authenticity）。</li></ul> |
| 6.13.2 | 2024-03-26 | <ul><li>对于Xcode 15.3中使用SPM的应用，修复了导致其发布失败的问题。详情请见<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes#version-6132">开发人员的版本说明</Anchor>。</li></ul> |
| 6.13.1 | 2024-03-05 | <ul><li>修复了CMP授权流程（DMA）中发送非GDPR用户授权数据的问题</li></ul> |
| 6.13.0   <br />弃用的区别 | 2024-02-08 | <ul><li>更新后支持Google最新的欧洲用户意见征集政策</li></ul> |
| 6.12.3 | 2024-01-04 | <ul><li>在ESP（邮件营销服务商）解析流程的深度链接回调中添加了新的`original_link`参数。</li><li>移除了所有提及iAd Framework的内容</li></ul> |
| 6.12.2 | 2023-08-24 | SDK维护 |
| 6.12.1 | 2023-07-20 | <ul><li>修复了SKAdNetwork 4.0中导致粗粒度转化值上报为“None”的问题。</li><li>修复了tvOS接入过程中的系统崩溃问题。</li></ul> |
| 6.12.0 | 2023-06-28 | 从SDK中移除了对bitcode的支持。 |
| 6.11.2 | 2023-06-13 | 修复了v6.11.0中的一个问题：调用`validateAndLogInAppPurchase`（用于购买认证和日志记录的历史API）后不记录购买事件。   <br />  <br /><strong>重要提示！</strong>如果您在使用`v6.11.0`或`v6.11.1`的同时使用`validateAndLogInAppPurchase`API，请务必更新到这个版本。 |
| 6.11.1 | 2023-05-24 | SDK维护 |
| 6.11.0 | 2023-04-25 | <ul><li>SDK在URL中使用新的AppsFlyer域名向AppsFlyer服务器发送请求。</li><li>更改了发送空值或null值时setHost API的行为。 [了解详情](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost)</li></ul> |
| 6.10.1 | 2023-04-02 | 在直接深度链接场景的UDL有效信息（payload）中添加了`link`参数 |
| 6.10.0 | 2023-02-15 | 支持SKAdNetwork 4.0。<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">进一步了解AppsFlyer的SKAN解决方案</Anchor> |

<div id="unsupported-sdk-versions" />

## 不再支持的SDK版本

以下SDK版本已进入“停止支持”状态。这些版本将无法再向AppsFlyer发送任何数据，来自这些版本的所有请求都会被拒绝处理。

| 版本 | 发布日期 | 说明 |
| --- | --- | --- |
| 6.9.2  <br />停止支持：  <br />2025-09-08 | 2023-01-31 | 更新了Get Conversion Data（GCD）的内部请求结构。**请注意**：响应数据保持不变。 |
| 6.9.1  <br />停止支持：  <br />2025-09-08 | 2022-11-28 | 更新了Get Conversion Data（GCD）的内部请求结构。**请注意**：响应数据保持不变。 |
| 6.9.0  <br />停止支持：  <br />2025-09-08 | 2022-11-06 | 更新了内部的广告收入（AdRevenue）上报API。从该版本开始仅支持[通用的广告收入（AdRevenue）连接器（Connector）](https://dev.appsflyer.com/hc/docs/ad-revenue-2)。<br /><br />该版SDK兼容AdRevenue Connector `V6.9.0`。 |
| 6.8.1  <br />停止支持：  <br />2025-09-08 | 2022-08-09 | **重装激活识别**：对于使用本机存储的应用，优化了识别及上报其重装激活的能力。您可以在AppsFlyer面板的<Anchor target="_blank" href="/marketers/zh/docs/app-settings">应用配置</Anchor>中调整该功能。 |
| 6.8.0  <br />停止支持：  <br />2025-03-03 | 2022-07-19 | 如需使用重装激活识别（Reinstall Detection）功能，请更新到SDK V6.8.1+ |
| 6.7.0  <br />停止支持：  <br />2025-03-03 | 2022-06-19 | 更新了SKAdNetwork的启用方式，使用iOS 15.4中新引入的Apple API `updatePostbackConversionValue`<br /><br />这对SKAdNetwork发送的数据没有影响，且无需对应用代码做任何修改 |
| 6.6.1  <br />停止支持：  <br />2025-03-03 | 2022-05-16 | SDK维护 |
| 6.6.0  <br />停止支持：  <br />2025-03-03 | 2022-05-01 | 在UDL的`didResolveDeepLink`回调中添加了参数，用于直接深度链接（Direct Deep Linking）流程（针对现有用户）。详情请见<Anchor target="_blank" href="/marketers/zh/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">此文档</Anchor>。 |
| 6.5.4  <br />停止支持：  <br />2025-03-03 | 2022-03-23 | SDK维护 |
| 6.5.3  <br />停止支持：  <br />2025-03-03 | 2022-03-02 | **修复漏洞：** 修复了基于URI scheme的链接中重复调用`didResolveDeepLink`的问题 |
| 6.5.2  <br />停止支持：  <br />2025-03-03 | 2022-01-26 | SDK维护 |
| 6.5.1  <br />停止支持：  <br />2025-03-03 | 2022-01-03 | SDK维护 |
| 6.5.0  <br />停止支持：  <br />2025-03-03 | 2021-12-12 | 代码重构及内部更新。 |
| 6.4.4  <br />停止支持：  <br />2025-03-03 | 2021-12-12 | SDK维护 |
| 6.4.3  <br />停止支持：  <br />2025-03-03 | 2021-11-30 | 通过xcframework修复了MacOS 10.14.6的稳定性问题 |
| 6.4.2  <br />停止支持：  <br />2025-03-03 | 2021-10-28 | SDK维护 |
| 6.4.1  <br />停止支持：  <br />2025-03-03 | 2021-10-24 | 解决了Unity应用中的稳定性问题 |
| 6.4.0  <br />停止支持：  <br />2025-03-03 | 2021-09-12 | **新增API：** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor>，若您不想让SDK向某些渠道发送数据，可使用该API配置相关需求。<br /><br />从该版本开始弃用`setSharingFilter`<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforallpartners">setSharingFilter和`setSharingFilterForAllPartners`setSharingFilterForAllPartners。</Anchor> |
| 6.3.5  <br />停止支持：2024-08-31 | 2021-08-19 | **新增API**：[`setCurrentDeviceLanguage`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setcurrentdevicelanguage)<br /><br />从该版本开始，SDK不再自动收集语言信息 |
| 6.3.4  <br />停止支持：2024-08-31 | 2021-07-21 | <ul><li>**修复漏洞：** 修复了在XCode 12.5 Simulators上运行SDK时出现的问题</li><li>轻微问题修复及更新</li></ul> |
| 6.3.2  <br />停止支持：2024-08-31 | 2021-06-17 | 优化了联调日志 |
| 6.3.1  <br />停止支持：2024-08-31 | 2021-06-02 | SDK维护 |
| 6.3.0  <br />停止支持：2024-08-31 | 2021-05-13 | <ul><li>更新后支持Apple Silicon：该SDK可在搭载M1芯片组的Mac设备模拟器上运行</li><li>从该版SDK开始支持iOS `9`+，不再支持iOS `8`</li><li>iOS Strict-mode SDK（严格模式）：更新后支持Carthage依赖管理器</li><li>完成了OneLink API的技术更新</li></ul> |
| 6.2.6  <br />停止支持：2024-08-31 | 2021-04-25 | <ul><li>修复漏洞：SDK在之后初始化时，SKAN规则加载失败`didFinishLaunchingWithOptions`</li><li>修复漏洞：`waitForATTUserAuthorization`边缘场景导致SDK发送应用打开事件时不含IDFA（即使用户已授权）</li><li>支持SDK在iOS 8设备中运行</li><li>清理并移除了未使用的代码和数据</li></ul> |
| 6.2.5  <br />停止支持：2024-08-31 | 2021-04-06 | 对SDK中未使用的数据进行了重构、清理和移除<br /><br />从该版本开始：<ul><li>弃用了`setShouldCollectDeviceName`方法，不再返回设备名称</li><li>SDK发送的`wifi`参数值设为`False`</li></ul> |
| 6.2.4  <br />停止支持：2024-08-31 | 2021-03-15 | 修复了SKAdNetwork收入衡量模式以及含`AF_REVENUE`参数的应用内事件中出现的问题<br /><br />从该版本开始，进行收入衡量时：任何包含参数`AF_REVENUE`的事件都会影响转化值。在此之前，必须在`AF_PURCHASE`事件框架中设置转化值。<br /><br />**请注意：** 您必须将SDK更新到此版本后才能使用SKAdNetwork收入衡量。 |
| 6.2.3  <br />停止支持：2024-08-31 | 2021-03-07 | 修复了SKAdNetwork的调用相关问题`updateConversionValue` |
| 6.2.2  <br />停止支持：2024-08-31 | 2021-02-18 | SDK维护 |
| 6.2.1  <br />停止支持：2024-08-31 | 2021-02-15 | 更新后支持<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S事件上报</Anchor> |
| 6.2.0  <br />停止支持：2024-08-31 | 2021-02-07 | 新增API：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setpartnerdata">setPartnerData</Anchor> |
| 6.1.4  <br />停止支持：2024-08-31 | 2021-01-12 | SDK维护 |
| 6.1.3  <br />停止支持：2024-08-31 | 2020-12-24 | <ul><li>新增API：<Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor>（支持Movable Ink）</li><li>更新后支持<Anchor target="_blank" href="https://developer.apple.com/documentation/adservices">Apple AdServices Framework</Anchor></li></ul> |
| 6.1.2  <br />停止支持：2024-08-31 | 2020-12-03 | SDK维护 |
| 6.1.1  <br />停止支持：2024-08-31 | 2020-11-17 | 引入<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">Strict mode SDK（严格模式）</Anchor> |
| 6.1.0  <br />停止支持：2024-08-31 | 2020-11-09 | 更新后支持<Anchor target="_blank" href="https://dev.appsflyer.com/docs/ios-unified-deep-linking">Unified deep linking API</Anchor> |
| 6.0.8  <br />停止支持：2024-08-31 | 2020-10-28 | 更新后支持<Anchor target="_blank" href="/marketers/zh/docs/apple-app-clips-integration-guide">Apple App Clips</Anchor>归因 |
| 6.0.7  <br />停止支持：2024-08-31 | 2020-10-21 | SDK维护 |
| 6.0.6  <br />停止支持：2024-08-31 | 2020-10-20 | SDK维护 |
| 6.0.5  <br />停止支持：2024-08-31 | 2020-10-08 | SDK维护 |
| 6.0.4  <br />停止支持：2024-08-31 | 2020-09-30 | 更新支持以ESP为起点的多重跳转 |
| 6.0.3  <br />停止支持：2024-08-31 | 2020-09-06 | <ul><li>API名称变更：<br />waitForAdvertisingIdentifier --> waitForATTUserAuthorization</li><li>SDK在iOS 14中默认收集IDFA（与在先前版本iOS中的行为一致）</li></ul> |
| 6.0.2   <br />停止支持：2024-08-31 | 2020-08-27 | <ul><li>API名称变更：<br />deviceLoggingDisabled --> anonymizeUser</li><li>在iOS 14中，需要用户在AppTrackingTransparency（ATT）弹窗中授权后才能收集IDFA</li><li>更新后支持IDFV交叉推广归因</li></ul> |
| 6.0.1 beta  <br />停止支持：2024-08-31 | 2020-08-06 | <ul><li>更新后支持<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">SKAdNetwork归因</Anchor>，帮助广告主在保护用户隐私的前提下衡量投放效果</li></ul> |
| 6.0.0 beta  <br />停止支持：2024-08-31 | 2020-08-04 | <ul><li>扩展了联调功能</li><li>对SDK功能性和API做了重大调整。[了解详情](/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes)</li></ul> |

<div id="see-also" />

> 📄 **另请参见**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/about-att-and-skan">iOS 14、ATT及SKAN的快速入门指南</Anchor>

<div data-zendesk-anchors="h_01JVHFG6PN34YFWNZKX2CYHJV8=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA end-of-support-vs-deprecated=%E5%81%9C%E6%AD%A2%E6%94%AF%E6%8C%81%E4%B8%8E%E5%BC%83%E7%94%A8%E7%9A%84%E5%8C%BA%E5%88%AB h_01JVHEKR4MTFV0FDHMTQW00BCS=%E5%81%9C%E6%AD%A2%E6%94%AF%E6%8C%81%E4%B8%8E%E5%BC%83%E7%94%A8%E7%9A%84%E5%8C%BA%E5%88%AB ios-sdk-v6=ios-sdk%E7%89%88%E6%9C%AC%E8%AF%B4%E6%98%8E 01H8W3DDM1BYRSPMFTA3TCY8EQ=ios-sdk%E7%89%88%E6%9C%AC%E8%AF%B4%E6%98%8E unsupported-sdk-versions=%E4%B8%8D%E5%86%8D%E6%94%AF%E6%8C%81%E7%9A%84sdk%E7%89%88%E6%9C%AC h_01JVHGN5NVRMGN9SJ5DWEAJYN3=%E4%B8%8D%E5%86%8D%E6%94%AF%E6%8C%81%E7%9A%84sdk%E7%89%88%E6%9C%AC h_01HE7RE2EPQX872DKNDBJ2G2QE=%E5%8F%A6%E8%AF%B7%E5%8F%82%E8%A7%81" />

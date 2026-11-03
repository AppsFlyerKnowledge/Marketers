---
title: AppsFlyer安卓SDK版本说明
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
  created_at: '2017-03-09T20:17:19Z'
  edited_at: '2026-10-14T10:04:43Z'
  id: 115001256006
  locale: zh-cn
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/zh-cn/articles/115001256006
---
> **概要：** 本文列出了安卓SDK的近期更新信息，便于您快速查看各版本的大致情况。如果开发人员需要更全面的信息，请查看<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-release-notes">Dev Hub中的安卓版本说明</Anchor>。

<strong>AppsFlyer将按照原计划，在六个月的周期内，逐步停止对iOS和Android旧版SDK的支持。</strong>此机制旨在为广告主预留充足时间，以便开发团队提前规划和升级，确保应用功能不受影响。请及时升级到最新版SDK，体验最新功能、更高稳定性和持续的技术支持。

> 🚧 **重要提示！**
>
> 为了确保平稳过渡，建议应用开发者在停止支持日期前完成SDK升级。

## 停止支持与弃用的区别

为了更清晰地区分SDK的支持状态及其对数据衡量的影响，AppsFlyer将旧版SDK分为以下两类：

* **已弃用的版本**由于存在已知问题（如严重Bug），官方不再推荐使用的SDK版本。这些版本仍然可以向AppsFlyer发送数据，但不鼓励开发者继续使用，我们强烈建议您升级到受支持的版本。
* **停止支持版本：** 不再进行任何数据衡量的SDK版本。在iOS和Android平台上，激活、应用打开和应用内事件都将无法被记录。来自这类版本的请求（除非被产品团队特别豁免）将收到400错误码，表示虽然SDK会继续尝试发送请求，但AppsFlye 服务器将拒绝处理，数据也不会被接收或存储。

## Android SDK版本说明

下表列出了当前受支持的安卓SDK版本、发布时间以及对其他重要信息。如需了解其他信息，请参见<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk">安卓SDK对接指南</Anchor>。

| 版本 | 发布日期 | 说明 |
| --- | --- | --- |
| 6.17.5 | 2025-11-26 | <ul><li>改善了稳定性并修复相关问题</li></ul> |
| 6.17.4 | 2025-10-15 | <ul><li>更新了SDK与高级安全模块之间的对接。该版本兼容Security Module v2.0.0及以上版本。</li><li>如果您正在使用高级安全模块，并希望将SDK升级至v6.17.4，请务必同时将Security Module升级至v2.0.0。</li></ul> |
| 6.17.3 | 2025-08-18 | <ul><li>技术更新：提升了稳定性和性能</li></ul> |
| 6.17.2 | 2025-08-05 | <ul><li>技术更新：更新为targetSDKVersion 35</li></ul> |
| 6.17.1 | 2025-07-28 | <ul><li>对用于应用内购买验证的`validateAndLogInAppPurchase`API进行了更新（当前为测试版）</li><li>新增对Google Play Integrity API的对接，可通过Google Play进行设备完整性验证</li></ul> |
| 6.17.0 | 2025-04-24 | <ul><li>新增对AppSet ID数据采集的支持。详见<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id">开发者说明文档</Anchor></li></ul> |
| 6.16.2 | 2025-03-02 | <ul><li>修复了对接SDK时可能导致构建错误的问题。</li></ul> |
| 6.16.1 | 2025-02-17 | <ul><li>更新了API，支持将DMA同意数据手动发送到AppsFlyer。</li></ul> |
| 6.16.0 | 2024-12-17 | <ul><li>增加了对三星预装归因的支持。详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-appsflyer-preload-referrer-attribution#特点与局限性">此文档</Anchor>。</li><li>在Privacy Sandbox attribution API（用于隐私沙盒归因）中增加了对收入衡量的支持（封闭Beta测试中）。</li><li>Dexguard已更新到v9.8.12，解决了稳定性问题并强化数据安。</li></ul> |
| 6.15.2 | 2024-10-10 | <ul><li>改善了稳定性并修复相关问题</li><li>与Privacy Sandbox Attribution API相关的内部更新</li></ul> |
| 6.15.1 | 2024-08-28 | 版本升级：<ul><li>targetSDKVersion：v34</li><li>Gradle：v8.7</li><li>Java：v17</li></ul> |
| 6.15.0 | 2024-07-31 | <ul><li>添加了`logAdRevenue`方法，用于向AppsFlyer发送广告收入数据。**请注意：** 从这个版本开始，请务必弃用AdRevenue Connector，并以`logAdRevenue`方法替代。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">详情请见此处说明。</Anchor></li></ul> |
| 6.14.2 | 2024-06-10 | <ul><li>针对使用Unity搭建的应用，修复了在抓取Meta Install Referrer时发生的问题。</li></ul> |
| 6.14.1 | 2024-05-29 | SDK维护 |
| 6.14.0 | 2024-04-18 | <ul><li>更新后支持最新的购买验证（Purchase Validation）链路。该功能目前处于Beta测试阶段。了解详情</li><li>更新了华为Referrer对接。详情请见<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#huawei-install-referrer">此文档</Anchor>。</li></ul> |
| 6.13.1 | 2024-04-03 | SDK维护 |
| 6.13.0 | 2024-02-08 | <ul><li>更新后支持Google最新的欧洲用户意见征集政策（DMA）</li></ul> |
| 6.12.6 | 2024-01-29 | SDK维护 |
| 6.12.5 | 2023-12-18 | <ul><li>在ESP解析流程的深度链接回调中添加了`original_link`参数。</li></ul> |
| 6.12.4 | 2023-10-25 | <ul><li>将Dexguard更新到9.4.16版本，以改善SDK稳定性。</li></ul> |
| 6.12.3 | 2023-08-31 | SDK维护 |
| 6.12.2 | 2023-08-02 | <ul><li>修复了在Android 8.1.0和Android 11中导致部分设备上应用崩溃的问题。</li></ul> |
| 6.12.1 | 2023-06-29 | <ul><li>修复了跨平台推广场景中Play Store打开延迟的问题。</li><li>修复了在部分设备中导致应用崩溃的问题。</li></ul> |
| 6.12.0 | 2023-06-28 | <ul><li>已弃用——请使用6.12.1.版本。</li></ul> |
| 6.11.2 | 2023-06-29 | <ul><li>修复了在部分设备中导致应用崩溃的问题。</li></ul> |
| 6.11.1 | 2023-06-6 | <ul><li>已弃用——请使用6.12.1.版本。</li><li>修复了部分情况下SDK初始化后应用闪退的问题。</li></ul> |
| 6.11.0 | 2023-05-16 | <ul><li>修复了SKD试图获取Google Play Referrer时在部分设备上导致应用卡死的问题</li></ul> |
| 6.10.3 | 2023-04-25 | SDK维护 |
| 6.10.2【已弃用】 |  | 已弃用 |
| 6.10.1 | 2023-03-01 | <ul><li>修复了SDK在三星设备中初始化时导致应用关闭的问题。该问题的影响范围为接入了SDK V6.6.0及以上版本的应用。</li></ul> |
| 6.10.0 | 2023-02-13 | <ul><li>新增AppsFlyer域名，用于SDK和AppsFlyer服务器之间的数据传输。</li><li>更改了发送空值或null值时的setHost API<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost">详情请见此处说明。</Anchor></li></ul> |

## 不再支持的SDK版本

以下SDK版本已进入**停止支持**状态。这些版本将无法再向AppsFlyer发送任何数据，来自这些版本的所有请求都会被拒绝处理。

| 版本 | 发布日期 | 说明 |
| --- | --- | --- |
| 6.9.4  <br />停止支持：  <br />2025-09-08 | 2022-12-6 | <ul><li>修复了从广告收入SDK连接器侧发送广告收入事件时触发转化监听器调用的问题。</li><li>修复了从广告收入SDK连接器侧发送广告收入事件时出现应用卡死的问题。</li></ul> |
| 6.9.3  <br />停止支持：  <br />2025-09-08 | 2022-11-28 | <ul><li>更新了Get Conversion Data（GCD）的内部请求结构。**请注意**：响应数据保持不变。</li><li>修复了应用将ConversionListener设为null时SDK触发GCD请求的问题。</li></ul> |
| 6.9.2  <br />停止支持：  <br />2025-09-08 | 2022-10-02 | <ul><li>修复了使用validateAndLogInAppPurchase API请求购买验证时的延迟问题。</li></ul> |
| 6.9.1  <br />停止支持：  <br />2025-09-08 | 2022-09-19 | SDK维护 |
| 6.9.0  <br />停止支持：  <br />2025-09-08 | 2022-09-12 | <ul><li>更新后支持Xiaomi GetApps Store Referrer。</li><li>更新了内部的广告收入上报API。从该版本开始仅支持<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">通用广告收入SDK接口</Anchor>。</li></ul> |
| 6.8.2  <br />停止支持：  <br />2025-09-08 | 2022-08-29 | <ul><li>修复V6.7.0版SDK的缓存机制中出现的重大漏洞，该漏洞会致使缓存的事件被重复发送。</li></ul> |
| 6.8.1  <br />（已弃用）  <br />停止支持：  <br />2025-09-08 | 2022-08-24 | <ul><li><strong>已弃用。</strong>请使用V6.8.2。</li></ul> |
| 6.8.0  <br />（已弃用）  <br />停止支持：  <br />2025-09-08 | 2022-07-18 | <ul><li><strong>已弃用。</strong>请使用V6.8.2。</li><li>从SDK中移除了<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#enablelocationcollection">`enableLocationCollection`</Anchor> API。应用可以通过<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#loglocation">`logLocation`</Anchor> API直接将用户的位置数据传递给SDK，从而上报该信息。</li><li>将`com.google.android.gms.permission.AD_ID`权限添加到SDK的`AndroidManifest.xml`中。详情请见<Anchor target="_blank" href="/marketers/zh/docs/bulletin-the-android-sdk-adds-the-ad-id-permission">此文档</Anchor>。</li><li>修复了使用R8时的优化和混淆问题。</li></ul> |
| 6.7.0  <br />（已弃用）  <br />停止支持：  <br />2025-09-08 | 2022-06-19 | <ul><li><strong>已弃用。</strong>请使用V6.8.2。</li><li>更新了SDK对于发送到AppsFlyer服务器的请求的处理方式。更新后，上报首次应用打开（转化）的请求会比应用内事件和其他请求的优先级更高。详情请见<Anchor target="_blank" href="/marketers/zh/docs/bulletin-adding-a-priority-queue-to-the-android-sdk">此文档</Anchor>。</li><li>**新增API：** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisablenetworkdata">`setDisableNetworkData`</Anchor>，用于关闭对蜂窝网络信息（网络和设备运营商的名称）的收集。</li></ul> |
| 6.6.1  <br />停止支持：  <br />2025-03-03 | 2022-05-16 | SDK维护 |
| 6.6.0  <br />停止支持：  <br />2025-03-03 | 2022-05-01 | <ul><li>在UDL的`onDeepLinking`回调中添加了参数，用于直接深度链接（Direct Deep Linking）流程（针对现有用户）。详情请见<Anchor target="_blank" href="/marketers/zh/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">此文档</Anchor>。</li></ul> |
| 6.5.4  <br />停止支持：  <br />2025-03-03 | 2022-03-23 | SDK维护 |
| 6.5.3  <br />停止支持：  <br />2025-03-03 | 2022-03-09 | <ul><li>**修复漏洞：** 修复了创建带有非英语字符的用户邀请链接时出现的问题。</li></ul> |
| 6.5.2  <br />停止支持：  <br />2025-03-03 | 2022-01-26 | <ul><li>修复了解析UDL延迟深度链接的URL时出现的问题。</li><li>升级到DexGuard 9.2</li><li>代码重构及内部更新。</li></ul> |
| 6.5.1  <br />停止支持：  <br />2025-03-03 | 2021-12-29 | <ul><li>针对使用<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution#channel-name">带Channel选项的第三方应用商店</Anchor>的应用，通过UDL实现深度链接解决方案。</li></ul> |
| 6.5.0  <br />停止支持：  <br />2025-03-03 | 2021-12-07 | <ul><li>代码重构及内部更新。</li></ul> |
| 6.4.3  <br />停止支持：  <br />2025-03-03 | 2021-11-14 | <ul><li>修复了`V6.4.2`中`LinkGenerator`导致创建链接时发生URL参数缺失的问题。</li></ul> |
| 6.4.2  <br />停止支持：  <br />2025-03-03 | 2021-10-24 | 修复了以下问题：<ul><li>由`LinkGenerator`生成的自定义URL中出现重复的`pid`参数。</li><li>使用`LinkGenerator`创建自定义URI scheme时`af_dp`值中出现冗余的“`/`”。</li><li>应用仅触发IMEI或AndroidID的收集时，SDK会同时收集这两种ID。</li></ul> |
| 6.4.1  <br />停止支持：  <br />2025-03-03 | 2021-10-17 | 修复了使用V3.5.4以前的Gradle版本时发生的编译错误。 |
| 6.4.0  <br />停止支持：  <br />2025-03-03 | 2021-09-12 | **新增API：** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor>，若您不想让SDK向某些渠道发送数据，可使用该API配置相关需求。<br /><br />从该版本开始弃用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilter">`setSharingFilter`</Anchor>和<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforallpartners">`setSharingFilterForAllPartners`</Anchor>。 |
| 6.3.2<br /><br />停止支持：2024-08-31 | 2021-06-06 | **新增API：** [`setDisableAdvertisingIdentifiers`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) |
| 6.3.1  <br />停止支持：2024-08-31 | 2021-05-26 | <ul><li>**新增API：** [`performOnDeepLinking`](https://dev.appsflyer.com/hc/docs/conversion-data)</li><li>更新后可在调用`start`前/`stop`后触发<Anchor target="_blank" href="/marketers/zh/docs/user-invite-attribution#设置流程">User Invite API</Anchor>。</li><li>**修复漏洞**：修复了调用`setCustomerUserId`后仍不释出`waitForCustomerUserId`的问题。</li></ul> |
| 6.3.0  <br />停止支持：2024-08-31 | 2021-04-29 | <ul><li>**修复漏洞**：应用内事件发送请求失败时误调用`onConversionDataFail`</li><li>**修复漏洞**：动态感应指标的收集（用于识别作弊行为）</li><li>**修复漏洞**：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">UDL</Anchor>的混淆相关问题修复</li><li>完成了OneLink API的技术更新</li></ul> |
| 6.2.3  <br />停止支持：2024-08-31 | 2021-03-04 | SDK维护 |
| 6.2.0  <br />停止支持：2024-08-31 | 2021-02-07 | <ul><li>**新增API：** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setpartnerdata">`setPartnerData`</Anchor></li></ul> |
| 6.1.4  <br />停止支持：2024-08-31 | 2021-01-12 | <ul><li>更新后支持DexGuard V9</li></ul> |
| 6.1.3  <br />停止支持：2024-08-31 | 2020-12-24 | <ul><li>**新增API**：<Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor>（支持Movable Ink）</li></ul> |
| 6.1.1  <br />停止支持：2024-08-31 | 2020-12-03 | <ul><li>更新后支持三星Galaxy Store Referrer</li><li>轻微漏洞修正及性能优化。</li></ul> |
| 6.1.0  <br />停止支持：2024-08-31 | 2020-11-09 | <ul><li>更新后支持<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">Unified deep linking API</Anchor></li></ul> |
| 6.0.1  <br />停止支持：2024-08-31 | 2020-10-28 | SDK维护 |
| 6.0.0  <br />停止支持：2024-08-31 | 2020-10-14 | <ul><li>对SDK功能性和API做出了重大调整，包括方法弃用和方法名称变更。[详情请见此处说明。](/docs/appsflyer-android-sdk-release-notes#android-v600-release-notes)</li></ul> |

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-sdk-version-control-policy">AppsFlyer SDK版本管理政策</Anchor>

<div data-zendesk-anchors="h_01JVHFG6PN34YFWNZKX2CYHJV8=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA end-of-support-vs-deprecated=%E5%81%9C%E6%AD%A2%E6%94%AF%E6%8C%81%E4%B8%8E%E5%BC%83%E7%94%A8%E7%9A%84%E5%8C%BA%E5%88%AB h_01JVHEKR4MTFV0FDHMTQW00BCS=%E5%81%9C%E6%AD%A2%E6%94%AF%E6%8C%81%E4%B8%8E%E5%BC%83%E7%94%A8%E7%9A%84%E5%8C%BA%E5%88%AB android-sdk-v6=android-sdk%E7%89%88%E6%9C%AC%E8%AF%B4%E6%98%8E h_01H9ZPCP8RWF24WAZ6YYMA1GS0=android-sdk%E7%89%88%E6%9C%AC%E8%AF%B4%E6%98%8E deprecated-versions=%E4%B8%8D%E5%86%8D%E6%94%AF%E6%8C%81%E7%9A%84sdk%E7%89%88%E6%9C%AC 01JHFAXXV51DHADQ7P2Q6RHFX0=%E4%B8%8D%E5%86%8D%E6%94%AF%E6%8C%81%E7%9A%84sdk%E7%89%88%E6%9C%AC h_01HDNZ774ME3SVT89JS7R4MSKE=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

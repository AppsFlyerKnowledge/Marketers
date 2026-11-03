---
title: SDK对接概览
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Integration
    - Advertisers
    - firetv
    - fire tv
    - Advertiser
    - Developer
    - appuid
    - anonymous
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2012-12-26T14:34:58Z'
  edited_at: '2026-10-14T09:59:41Z'
  id: 207032126
  locale: zh-cn
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/zh-cn/articles/207032126
---
> **概要：概要**：本文介绍了AppsFlyer SDK已上线的功能，并解释了安卓和iOS应用分别应适配哪些API。

## SDK简介

本视频将为您介绍SDK对接的总体情况。

<Embed title="SDK对接概览" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/4iybquc6q3" providerUrl="https://fast.wistia.com" />

SDK用于记录应用激活和事件，也就是说，您可以使用SDK记录激活、应用打开（session）和应用内事件。应用内事件是指应用内购或游戏通关等用户行为，您可以通过这些事件来衡量ROI和用户质量。

本文介绍了SDK V6+的对接流程，帮助广告主（应用所有者）侧的产品经理规划如何在其安卓或iOS应用中接入AppsFlyer SDK。

如需了解其他相关主题，您可以参阅以下文档：

<Tabs>
<Tab title="安卓原生">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">开发人员专用的SDK安装文档</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-android-sdk-release-notes">发布说明</Anchor>
* 开发人员专用的SDK参考文档
* <Anchor target="_blank" href="/marketers/zh/docs/fill-out-google-safety-section-form">Google Play中的Data Safety（数据安全）板块</Anchor>

</Tab>

<Tab title="iOS原生">

* <Anchor target="_blank" href="/marketers/zh/docs/updating-to-ios-sdk-v6-and-plugins">升级到iOS SDK V6</Anchor>。虽然iOS SDK V5.4.4在iOS 14环境中是完全可用的，但是，我们强烈建议您采用SDK V6.X版本以确保兼容iOS14的重要变化和未来更新。
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">开发人员专用的SDK安装文档</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes">发布说明</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference">开发人员专用的SDK参考文档</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/preparing-for-the-app-store-review-nutrition-labels">如何应对App Store的审核——Nutrition Label（隐私标签）</Anchor>

</Tab>

<Tab title="Unity">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">开发人员专用的SDK安装文档</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api">开发人员专用的SDK参考文档</Anchor>

</Tab>

<Tab title="React Native">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">开发人员专用的SDK安装文档</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api">开发人员专用的SDK参考文档</Anchor>

</Tab>
</Tabs>

## SDK兼容性

AppsFlyer SDK与下列平台兼容：

<Tabs>
<Tab title="Android">

* 从Android V4.0起
* 非移动端安卓平台，如智能电视（包括亚马逊Fire TV等）的相关信息<Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts">详情请见CTV简介。</Anchor>
* 安卓<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution">第三方应用商店</Anchor>，如亚马逊和百度

</Tab>

<Tab title="iOS">

* iOS 8（iPhone、iPod、iPad）
* tvOS 9+（Apple TV）
* 支持Apple <Anchor target="_blank" href="https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1">IPv6 DNS64/NAT64</Anchor> 网络

该SDK支持<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">多种归因方式</Anchor>。归因方式的选取视以下因素而定：

* 用户设备上安装的iOS版本
* 应用中安装的iOS SDK版本

<table><thead><tr><th><span>适用的归因方式</span></th><th><span>iOS版本</span></th><th><span>适用的iOS SDK版本</span></th><th><span>说明</span></th></tr></thead><tbody><tr><td rowspan="2"><span>概率模型</span></td><td><p><span>8 – 14.4</span></p></td><td>5.0.0+</td><td> </td></tr><tr><td><p><span>14.5+</span></p></td><td><span> 6.0.3+</span></td><td><span>概率模型仅限自有媒体、交叉推广和授权的网页到端的授权匹配。</span></td></tr><tr><td rowspan="2"> <span>ID匹配</span><br/><span><br/></span> </td><td><span>8 - 13</span></td><td>5.0.0+</td><td><span>用户可选择不启用Limit Ad Tracking（限制广告跟踪，简称LAT)设置</span></td></tr><tr><td><span>14.5+</span></td><td><span>6.0.3+</span></td><td><p>须符合App Tracking Transparency（应用追踪透明度，简称 ATT框架）并获得用户同意。详情请见<a href="./basic-sdk-integration-guide#configure-app-tracking-transparency-att-support" target="_blank">符合ATT框架的iOS SDK配置</a>。</p></td></tr><tr><td rowspan="2"><p><a href="./skadnetwork-skan-solution-guide" target="_blank"><span>SKAdNetwork</span></a></p></td><td><p><span>11.3 - 13</span></p></td><td rowspan="2"><p><span>6.2.3</span><br/><span><br/></span></p></td><td><p>SKAdNetwork（简称SKAN）解决方案<span>仅限按照</span><a href="https://developer.apple.com/documentation/storekit/skadnetwork" target="_blank">SKAN</a><span>的要求进行激活归因，因此没有转化值。</span></p></td></tr><tr><td><p><span>14+</span></p></td><td><ul><li>无论ATT如何设置，SKAN在iOS和SDK层级都是默认可用的。</li><li>市场人员需要在AppsFlyer的面板中启用SKAN。</li></ul></td></tr></tbody></table>

请注意SDK V6.0.8 或未来以上版本会支持<Anchor target="_blank" href="/marketers/zh/docs/apple-app-clips-integration-guide">Apple App Clips 归因</Anchor>。有关苹果轻App的详情请参阅我们的<Anchor target="_blank" href="/marketers/zh/docs/apple-app-clips-integration-guide">博文</Anchor>。

</Tab>
</Tabs>

## SDK对接

SDK的安装和对接需要产品经理和移动端开发人员合作完成。在接入SDK**之前**，请先全面了解该流程中所涉及的工作，并明确您的应用需要用到哪些功能。

### SDK规划清单

为便于您上手，我们准备了一个<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx">任务清单</Anchor>来帮助您跑通整个规划流程，并针对每一项工作都提供了市场人员和开发人员的专用指南。

### SDK对接工作

基础的SDK对接包括以下几项工作。预计用时一栏仅作参考。

| 基础SDK对接工作 | 预计用时 |
| --- | --- |
| 获取<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#在相关应用中添加dev-key">AppsFlyer dev key</Anchor>并将链接、安装和对接指南一并发送给您的开发人员。 | 15分钟 |
| 请根据<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#归因">归因考量因素</Anchor>确定您需要收集的设备标识符。 | 30分钟 |
| 确定您想要衡量的<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#记录应用内事件">应用内事件</Anchor>，并将事件名称和事件参数发送给开发人员。 | 1小时 |
| 确定您要使用的<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#onelink深度链接">深度链接方式</Anchor>。 | 30分钟 |
| 确定<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#拉取归因和深度链接数据">拉取归因数据</Anchor>的方式。 | 30分钟 |
| 基础对接完成后，任何具有AppsFlyer面板权限的账户用户都能进行<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#测试sdk对接">基础测试</Anchor>。<br /><br />开发人员可以利用<Anchor target="_blank" href="/marketers/zh/docs/testing-the-sdk-integration-for-marketers#testing-in-the-development-environment">开发环境</Anchor>中的调试日志。 | 1小时 |

您可以与移动端开发人员合作，在SDK中另外接入以下API：

| 其他SDK对接工作 | 预计用时 |
| --- | --- |
| 确定您的应用是否需要<Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#其他归因方式">其他归因</Anchor>设置（如第三方应用商店的卸载衡量或激活归因）。 | 30分钟 |
| 确定<Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#应用打开sessions">用户session上报机制</Anchor>。 | 30分钟 |
| 确定<Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#自有媒体">自有媒体</Anchor>的归因方式。 | 1小时 |
| 管理<Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#用户隐私">用户隐私</Anchor>政策，确保您的应用符合相关隐私条例（如GDPR和CCPA） | 1小时 |

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC和主机平台简介</Anchor>

<div data-zendesk-anchors="about-the-sdk=sdk%E7%AE%80%E4%BB%8B h_01H9FHRVKE6BHGW05G6YMKF737=sdk%E7%AE%80%E4%BB%8B sdk-compatibility=sdk%E5%85%BC%E5%AE%B9%E6%80%A7 h_01H9FHRVKEQ837Q0GFECNPPAN2=sdk%E5%85%BC%E5%AE%B9%E6%80%A7 sdk-integration=sdk%E5%AF%B9%E6%8E%A5 h_01H9FHRVKEN0MMGTSD362FTWPS=sdk%E5%AF%B9%E6%8E%A5 sdk-planning-checklist=sdk%E8%A7%84%E5%88%92%E6%B8%85%E5%8D%95 h_01H9FHRVKE468M1RTMF7VTYV1R=sdk%E8%A7%84%E5%88%92%E6%B8%85%E5%8D%95 sdk-integration-tasks=sdk%E5%AF%B9%E6%8E%A5%E5%B7%A5%E4%BD%9C h_01H9FHRVKERHXY19R97EN86EGP=sdk%E5%AF%B9%E6%8E%A5%E5%B7%A5%E4%BD%9C h_01H9FHRVKE88CXGH8G7E26ZXT2=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

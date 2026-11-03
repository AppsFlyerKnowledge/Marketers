---
title: SDK对接补充指南
metadata:
  keywords:
    - iOS
    - Android
    - Integration
    - Advertisers
    - firetv
    - Advertiser
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2021-10-10T11:54:14Z'
  edited_at: '2026-10-14T10:15:07Z'
  id: 4408735106193
  locale: zh-cn
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/zh-cn/articles/4408735106193
---
> **概要：** 除了基础功能外，您还可以使用其他的SDK功能，并与开发人员合作部署卸载衡量、用户邀请归因、推送通知和隐私设置等API。

## 其他归因方式

如果您需要衡量电视推广、应用卸载或预装推广，可以考虑另外再使用以下各种归因方式。

**所有平台**

<div id="tv-attribution" />

<Accordion title="CTV归因">

将移动用户归因到在特定地点和特定时段投放的<Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts">CTV广告</Anchor>。

</Accordion>

<div id="measure-uninstalls" />

<Accordion title="卸载衡量">

衡量各渠道的用户卸载率。卸载是一项非常重要的KPI，衡量卸载可以帮助您分析并优化您的广告投放。

<Anchor target="_blank" href="/marketers/zh/docs/measure-uninstalls">卸载衡量配置指南</Anchor>。

</Accordion>

**仅适用于安卓**

<div id="preinstalled-apps" />

<Accordion title="预装应用的归因">

在<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-factory-preinstall-using-manifest-android">预安装广告</Anchor>场景中，广告主与设备生产商（OEM）协议将其应用预安装到设备中。

您能通过AppsFlyer轻松实现预装应用激活的归因。用户首次打开您的应用时，AppsFlyer会将该次激活归因到预安装合作伙伴，将其作为一个媒体渠道。

</Accordion>

## 应用打开（Sessions）

通过计算指定时段内的用户session次数来衡量用户与应用的互动情况。

**所有平台**

<div id="custom-time-between-sessions" />

<Accordion title="设定两个session之间的间隔时长">

默认2个session之间必须至少间隔5秒，才能分别将其计为单独的session。详情请见<Anchor target="_blank" href="/marketers/zh/docs/measure-sessions#session-reporting-by-the-app-sdk">session计算方式</Anchor>。

如果两个session之间的间隔时间设置得**较高**，**可能会严重影响依赖session数据的API**，如深度链接。

</Accordion>

**仅适用于安卓**

<div id="background-sessions-for-utility-apps" />

<Accordion title="工具类应用的后台session">

您可以<Anchor target="_blank" href="/marketers/zh/docs/measure-sessions#session-reporting-by-the-app-sdk">手动上报用户session</Anchor>。这种方式适用于一般在后台运行的工具类应用。

</Accordion>

## 自有媒体

通过OneLink对网站、社交媒体、用户邀请等自有媒体进行归因。

**所有平台**

<div id="resolve-wrapped-deep-link-urls" />

<Accordion title="解析有嵌套的深度链接URL">

<Anchor target="_blank" href="/marketers/zh/docs/email-service-provider-esp-integration-guide">电子邮件服务商</Anchor>等第三方服务商会使用自己的域名将链接嵌套在邮件中，用于记录点击，有些还能让广告主设置这类域名。如果OneLink被嵌套在此类域名中，其功能可能会受到限制。

要解决这个问题，您的开发人员需要使用以下API来配置相关应用：

<Tabs>
<Tab title="安卓原生">

请参考安卓SDK对接说明中的[`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setresolvedeeplinkurls)

</Tab>

<Tab title="iOS原生">

请参考iOS SDK对接说明中的[`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#resolvedeeplinkurls)

</Tab>

<Tab title="Unity">

请参考Unity SDK对接说明中的[`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/api#setresolvedeeplinkurls)

</Tab>
</Tabs>

</Accordion>

<div id="record-push-notifications" />

<Accordion title="记录推送通知">

AppsFlyer能够衡量通过各种平台投放的推送通知广告，包括Google Cloud Messaging或Apple推送通知服务。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/measuring-push-notification-re-engagement-campaigns">推送通知衡量</Anchor>。

</Accordion>

<div id="user-invite-attribution" />

<Accordion title="用户邀请归因">

允许您现有的用户邀请朋友或联系人成为您应用的新用户，这可以成为应用的一个关键增长因素。您可以通过AppsFlyer对用户邀请带来的激活进行归因和记录。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/user-invite-attribution">用户邀请归因</Anchor>。

</Accordion>

<div id="crosspromotion-attribution" />

<Accordion title="交叉推广归因">

交叉推广能大幅提升应用拉新力度。您可以在用户的现有应用上交叉推广您的其他应用，并通过AppsFlyer来对这类激活进行归因和记录。  

详情请见<Anchor target="_blank" href="/marketers/zh/docs/cross-promotion-attribution-for-marketers">交叉推广归因</Anchor>。

</Accordion>

<div id="attribute-app-sessions-initiated-from-owned-websites-domains" />

<Accordion title="对来自自有网站（域）的session进行归因">

如果广告主通过App Link或Universal Link实现深度链接（不使用OneLink），可以让SDK通过与其应用相关联的域（<Anchor target="_blank" href="https://developer.android.com/studio/write/app-link-indexing#associatesite">Android</Anchor>/<Anchor target="_blank" href="https://developer.apple.com/documentation/xcode/supporting-associated-domains?preferredLanguage=occ">iOS</Anchor>）来对session进行归因。

例如:

* 一个用户通过Google搜索并点击了您的网站<strong>www.example.com</strong>：
* 如果用户未安装相关应用，他们会跳转到关联网站（[www.example.com](https://www.example.com)）。
* 如果用户已安装相关应用，他们会通过深度链接打开该应用（即与[www.example.com](https://www.example.com)相关联的应用）。而这个session就会归因给SDK中所配置的媒体渠道（`pid`参数）。

另请参考以下开发者文档：

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">安卓SDK对接说明</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">iOS SDK对接说明</Anchor>

**提示**您可以使用<Anchor target="_blank" href="/marketers/zh/docs/convert-your-mobile-web-visitors-to-app-users#attribution-solutions">OneLink Smart Script</Anchor>将网页端用户导流到移动端。

</Accordion>

## 用户隐私

请结合GDPR和CCPA等隐私条例以及您的业务需求，综合考虑用户授权政策的选择和执行。

**所有平台**

<div id="optout-policy" />

<Accordion title="用户拒绝授权">

在某些情况下，您可能需要让开发人员关闭AppsFlyer SDK或限制数据收集（如在GDPR和CCPA合规场景下）。您可以使用多种不同方式通过SDK配置来保护用户隐私。如需进一步了解这些方式，请参考<Anchor target="_blank" href="/marketers/zh/docs/apply-privacy-preserving-sdk-methods">保护用户隐私的SDK配置</Anchor>说明。

</Accordion>

<div id="exclude-partners-from-getting-data" />

<Accordion title="停止与合作渠道共享数据">

在某些情况下，广告主可能希望停止与广告平台/合作渠道共享特定用户的用户级别数据。其原因包括：

* CCPA或GDPR等隐私政策的合规问题
* 用户拒绝授权
* 与某些渠道（广告平台、第三方）存在竞争关系

您可以通过`setSharingFilterForPartners`方法来控制渠道的数据共享：

<Tabs>
<Tab title="安卓原生">

请参考安卓SDK对接说明中的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor>

</Tab>

<Tab title="iOS原生">

请参考iOS SDK对接说明中的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">`resolveDeepLinkURLs`</Anchor>

</Tab>

<Tab title="Unity">

请参考Unity SDK对接说明中的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor>

</Tab>

<Tab title="React Native">

请参考React Native SDK对接说明中的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor>

</Tab>
</Tabs>

</Accordion>

<div id="send-consent-for-dma-compliance" />

<Accordion title="用于DMA合规的授权数据发送">

根据欧盟[《数字营销法案》](https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en) (DMA) 的规定，对于欧洲境内的终端用户，大型科技公司必须先获得其授权同意，然后才能将这些用户来自第三方服务平台的个人数据用于广告营销。

为了遵守该法律的规定，Google要求AppsFlyer的客户向Google发送来自欧盟终端用户的事件时，在其中添加特定的用户授权字段。AppsFlyer SDK（v6.13.0+）可在每个事件中发送必要的授权数据，以符合此项的要求。

AppsFlyer SDK提供两种不同的授权数据收集方式，供广告主选用：

* **通过同意管理平台（Consent Management Platform，简称CMP）收集：** 如果相关应用使用的CMP支持[透明度和同意框架（Transparency and Consent Framework，简称TCF） v2.2](https://iabeurope.eu/tcf-supporting-resources/)，该SDK可以自动获取授权信息。

  或
* **通过专用的SDK API收集**：开发人员可以通过专用API将Google所需的授权数据直接传递给SDK。

如需收集用户授权数据以实现DMA合规，请参考我们的开发者指南：

<Tabs>
<Tab title="安卓原生">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-send-consent-for-dma-compliance">用于DMA合规的授权数据发送</Anchor>

</Tab>

<Tab title="iOS原生">

[用于DMA合规的授权数据发送](https://dev.appsflyer.com/hc/docs/ios-send-consent-for-dma-compliance)

</Tab>
</Tabs>

</Accordion>

**仅适用于iOS**

<div id="strictmode-sdk" />

<Accordion title="Strict-mode（严格模式）SDK">

使用strict-mode（严格模式）SDK可以彻底禁用IDFA收集功能，并且完全不依赖AdSupport框架（适用于面向儿童的应用等）。

如果您需要推广面向儿童的应用，您的开发人员需要安装<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">strict-mode SDK</Anchor>，而不能使用常规的SDK。**请注意：** 注意： IDFV仍然可用。

</Accordion>

<div id="disable-ad-frameworks" />

<Accordion title="禁用广告框架">

AppsFlyer SDK提供以下setter，用于禁用AdSupport和iAd框架：

<Tabs>
<Tab title="iOS原生">

* [`disableCollectASA`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disablecollectasa)用于停止ASA归因。
* [`disableAdvertisingIdentifier`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier)用于停止收集Apple `advertisingIdentifier`

</Tab>

<Tab title="Unity">

* [`setDisableCollectIAd`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectiad)用于停止ASA归因。
* [`setDisableCollectAppleAdSupport`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectappleadsupport)用于停止收集Apple `advertisingIdentifier`

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="additional-attribution-methods=%E5%85%B6%E4%BB%96%E5%BD%92%E5%9B%A0%E6%96%B9%E5%BC%8F 01H8W01DRHQHJKNMJA24PR5S2T=%E5%85%B6%E4%BB%96%E5%BD%92%E5%9B%A0%E6%96%B9%E5%BC%8F 01H8W01DRHXR0BRCB9RECH7KS1=tv-attribution 01H8W01DRHMZN2P0FKADM0NQ96=measure-uninstalls 01H8W01DRH2HM3N06YAGRZ030F=preinstalled-apps sessions=%E5%BA%94%E7%94%A8%E6%89%93%E5%BC%80sessions 01H8W01DRHD3EZBQT0ZKDMM1QB=%E5%BA%94%E7%94%A8%E6%89%93%E5%BC%80sessions 01H8W01DRH2SR3NBQSMSQ6QR6K=custom-time-between-sessions 01H8W01DRH4NGYYABE274DJ1A5=background-sessions-for-utility-apps owned-media=%E8%87%AA%E6%9C%89%E5%AA%92%E4%BD%93 01H8W01DRHV8H3QFJX5QKABK5E=%E8%87%AA%E6%9C%89%E5%AA%92%E4%BD%93 01H8W01DRHJS8MM3ZQX2RX4JJG=resolve-wrapped-deep-link-urls 01H8W01DRHHDEEXP8GDFX9134R=record-push-notifications 01H8W01DRHZDB82AB63JKE1B6V=user-invite-attribution 01H8W01DRHVR8JHZCJ6SW8TAA6=crosspromotion-attribution 01H8W01DRHXSYWCS6RW2ZVDKXT=attribute-app-sessions-initiated-from-owned-websites-domains user-privacy=%E7%94%A8%E6%88%B7%E9%9A%90%E7%A7%81 01H8W01DRHJFB71DVJ64QWJME4=%E7%94%A8%E6%88%B7%E9%9A%90%E7%A7%81 01H8W01DRHD7FDERJZFJP9GG0T=optout-policy 01H8W01DRHYNYYFTF82XZ21J3P=exclude-partners-from-getting-data h_01HP25PQZCSQPCMTAZ5PFA0ZFS=send-consent-for-dma-compliance 01H8W01DRJD0XRX4VX03T3YEKX=strictmode-sdk 01H8W01DRJKJFFMBMJ4KNTXPXE=disable-ad-frameworks" />

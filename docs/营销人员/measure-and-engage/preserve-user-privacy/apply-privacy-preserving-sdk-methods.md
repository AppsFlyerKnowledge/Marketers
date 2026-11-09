---
title: 保护用户隐私的SDK配置
metadata:
  keywords:
    - Advertisers
    - coppa
    - opt-out
    - opt out
    - consent management
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
  created_at: '2018-08-20T11:14:36Z'
  edited_at: '2026-10-14T10:07:26Z'
  id: 360001422989
  locale: zh-cn
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001422989
---
> **概要：** 您可以通过多种AppsFlyer SDK设置方式来保护您用户的隐私。

<div id="note" />

> 📘 **注意**
>
> 本文意图仅在于帮助应用开发人员了解可用的技术手段，用以调控应用所有者、广告平台和社交平台之间的用户数据共享。**本文所提供的信息既不包含也不构成对COPPA、GDPR或任何具体隐私保护条例的合规性指导。**

AppsFlyer SDK为应用所有者提供多种保护用户隐私和控制数据收集的方法。本文对这些方法进行了逐一探讨，同时说明了各种方法对用户数据的影响，并阐释了如何在不阻断归因的情况下保护用户隐私。

考量并决定您要使用的方案，将AppsFlyer开发者资源中心(Dev Hub)中的部署说明文档发送给您的开发人员。

下面我们来分别探讨各个配置方法。

<div id="use-start-and-stop-methods" />

## 使用start和stop方法

只有在调用`start`方法后，SDK才会向AppsFlyer发送激活和应用内事件。SDK不会上报任何在`start`调用之前发生的事件。同样，如果后续通过调用`start`方法撤销了之前的`stop`，则此后将不再发送任何事件。

<div id="impact-on-attribution" />

### 对归因的影响

出现以下情况时**不**发生归因：

* `start`方法未调用。
* 调用`stop`方法撤销了先前的start。

<div id="common-use-cases" />

### 常见使用场景

| 使用场景 | 描述 |
| --- | --- |
| 用户在启动应用时授权或拒绝授权 | 在用户首次启动应用时同意共享数据，则调用`start` 。  <br />如果用户拒绝共享数据，则不调用  <br />`start`。 |
| 分session授权 | 每次应用打开时请求授权，并根据用户的授权决定选择性调用`start`startstart。 |
| 一次性拒绝授权（用户同意共享数据后又决定拒绝共享） | 调用`stop`，让SDK不再发送后续事件。 |

<div id="developer-reference" />

### 开发者参考资料

请查看以下开发者参考资料和文档，了解start和stop方法的使用方式：

<Tabs>
<Tab title="Android">

[使用start方法仅发送激活信息](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#use-start-to-share-only-the-install-event)

</Tab>

<Tab title="iOS">

[使用start方法仅发送激活信息](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#use-start-to-share-only-the-install-event)

</Tab>
</Tabs>

<div id="prevent-sharing-data-with-networks" />

## 防止与平台共享数据

与广告平台或自归因平台（SRN）对接时，您可以选择是否与其共享用户级别的信息。您还可以**根据终端用户的偏好**，在SDK中使用`setSharingFilterForPartners`方法进一步细化相关应用与所有或部分渠道的数据共享。

使用此方法时，AppsFlyer会在所有适用的数据传输工具中停止与您指定的平台共享用户数据，包括回传、API、原始数据报告等。

<div id="impact-on-attribution-1" />

### 对归因的影响

* 如果您选择不与某个广告平台（非SRN）共享数据，则AppsFlyer会对**来自该广告平台**的激活进行归因，但不会以任何方式通知该平台。
* 如果您选择**不**与某个**SRN**共享数据，则来自该SRN的激活不会被归因，其数据也不会与您的对接渠道共享。

  <div id="note-1" />

  > 📘 **注意**
  >
  > 当某个SRN被排除在您的数据共享范围之外时，AppsFlyer无法将互动数据归因到该SRN。


<div id="developer-reference-1" />

### 开发者参考资料

请查看以下开发者参考资料和文档，了解如何防止与第三方平台共享数据：

<Tabs>
<Tab title="Android">

[防止与第三方共享数据](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#prevent-sharing-data-with-third-parties)

</Tab>

<Tab title="iOS">

[防止与第三方共享数据](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#prevent-sharing-data-with-third-parties)

</Tab>
</Tabs>

<div id="anonymize-user-information" />

## 用户信息匿名化

您可以在配置SDK时使用`anonymizeUser`方法，让AppsFlyer删除所有用户身份识别信息。这种情况下，SDK向AppsFlyer发送激活和应用内事件后，所有的身份识别信息会被删除或进行哈希加密处理：

* **删除**：个人身份标识符（GAID、IDFA、IDFV以及CUID）
* **哈希加密：** AppsFlyer ID和IP地址

下图展示了经匿名化处理（删除或哈希加密）后的原始数据样例。

<Image align="center" alt="" src="https://files.readme.io/5cae15ee0e38c84b2f9876d0dca2145543e83e624933ca138017da5206e7a834-35847868223633.png" />

<div id="impact-on-attribution-2" />

### 对归因的影响

如果您在`start`之前调用了`anonymizeUser`，则不会发生任何归因。所有应用内事件都记录为自然事件或不做记录，具体取决于您使用的面板

<div id="note-2" />

> 👍 **提示**
>
> 如需对激活进行归因，请务必先确认SDK已经将相关激活发送到AppsFlyer，然后再调用`anonymizeUser`。该流程可确保激活后发生的所有应用内事件在发送到AppsFlyer时都不带有标识符信息，也因此不会被归因。

<div id="developer-reference-2" />

### 开发者参考资料

请查看以下开发者参考资料和文档，了解用户信息匿名化方式：

<Tabs>
<Tab title="Android">

[用户信息匿名化](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#anonymize-user-information)

</Tab>

<Tab title="iOS">

[用户信息匿名化](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#anonymize-user-information)

</Tab>
</Tabs>

<div id="remove-specific-device-identifiers" />

## 删除特定的设备标识符

您可以让SDK不收集且不向AppsFlyer发送特定的设备标识符。与`anonymizeUser`方法不同，使用该方式时您可以保留您需要的标识符。

您可以使用以下方法通过SDK API禁用特定标识符：

<div id="android-identifiers" />

### 安卓标识符

| 方法 | 禁用标识符 |
| --- | --- |
| `setdisableadvertisingIdentifiers` | <ul><li>GAID-Google Advertising ID</li><li>Open Anonymous Device Identifier（OAID）</li><li>Amazon Advertising ID（AAID）</li></ul> |
| [`setcollectoaid`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid) | Open Anonymous Device Identifier（OAID） |

<div id="ios-identifiers" />

### iOS标识符

| 方法 | 禁用标识符 |
| --- | --- |
| `disableAdvertisingIdentifier` | IDFA（iOS 13及以下版本） |
| `disableIDFVCollection` | IDFV |

<div id="developer-reference-3" />

### 开发者参考资料

请查看以下开发者参考资料和文档，了解如何移除特定的设备标识符：

<Tabs>
<Tab title="Android">

[禁用ID](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#disable-ids)

</Tab>

<Tab title="iOS">

[禁用ID](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#disable-ids)

</Tab>
</Tabs>

<div id="note-3" />

> 📘 **对AppsFlyer的数据隐私有疑问？**
>
> [AppsFlyer数据处理声明](https://www.appsflyer.com/legal/processing-customer-data/)中界定了您与AppsFlyer之间的隐私关系。如果您对此声明有任何疑问，或需要联系我们的数据保护负责人，请发邮件至[dpo@appsflyer.com](mailto:dpo@appsflyer.com)。

<div data-zendesk-anchors="h_01HKD1N2C8G348DPPG41HMC15J=%E6%B3%A8%E6%84%8F use-start-and-stop-methods=%E4%BD%BF%E7%94%A8start%E5%92%8Cstop%E6%96%B9%E6%B3%95 h_01HKD1N2C8V0SP1NG8W2EJPRQZ=%E4%BD%BF%E7%94%A8start%E5%92%8Cstop%E6%96%B9%E6%B3%95 impact-on-attribution=%E5%AF%B9%E5%BD%92%E5%9B%A0%E7%9A%84%E5%BD%B1%E5%93%8D h_01HKD1N2C80QAJSNE83SD45DJA=%E5%AF%B9%E5%BD%92%E5%9B%A0%E7%9A%84%E5%BD%B1%E5%93%8D common-use-cases=%E5%B8%B8%E8%A7%81%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF h_01HKD1N2C8YHWYARRAGX1TD6DM=%E5%B8%B8%E8%A7%81%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF developer-reference=%E5%BC%80%E5%8F%91%E8%80%85%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99 h_01HKM6VNJFCW77F2268XXDF65Q=%E5%BC%80%E5%8F%91%E8%80%85%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99 prevent-sharing-data-with-networks=%E9%98%B2%E6%AD%A2%E4%B8%8E%E5%B9%B3%E5%8F%B0%E5%85%B1%E4%BA%AB%E6%95%B0%E6%8D%AE h_01HKD1N2C8ASV10XWY33R972MC=%E9%98%B2%E6%AD%A2%E4%B8%8E%E5%B9%B3%E5%8F%B0%E5%85%B1%E4%BA%AB%E6%95%B0%E6%8D%AE impact-on-attribution::aa0a9f9e=%E5%AF%B9%E5%BD%92%E5%9B%A0%E7%9A%84%E5%BD%B1%E5%93%8D-1 h_01HKD1N2C8RA34M4TSWYCW3A9F=%E5%AF%B9%E5%BD%92%E5%9B%A0%E7%9A%84%E5%BD%B1%E5%93%8D-1 h_01HKD1N2C809Y9HE99WGXZYE39=%E6%B3%A8%E6%84%8F-1 developer-reference::f2007ab7=%E5%BC%80%E5%8F%91%E8%80%85%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99-1 h_01HKM6VNJFP8C7KCFSV1046H0B=%E5%BC%80%E5%8F%91%E8%80%85%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99-1 anonymize-user-information=%E7%94%A8%E6%88%B7%E4%BF%A1%E6%81%AF%E5%8C%BF%E5%90%8D%E5%8C%96 h_01HKD1N2C8CWSWK0VSXZ39MQ3D=%E7%94%A8%E6%88%B7%E4%BF%A1%E6%81%AF%E5%8C%BF%E5%90%8D%E5%8C%96 impact-on-attribution::601baa93=%E5%AF%B9%E5%BD%92%E5%9B%A0%E7%9A%84%E5%BD%B1%E5%93%8D-2 h_01HKD1N2C8BFVCKD3BQS4HE75P=%E5%AF%B9%E5%BD%92%E5%9B%A0%E7%9A%84%E5%BD%B1%E5%93%8D-2 h_01HKD1N2C80WW9JVBBFS5QDY7T=%E6%8F%90%E7%A4%BA developer-reference::e4cacf1f=%E5%BC%80%E5%8F%91%E8%80%85%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99-2 h_01HKM6VNJF7XPZ9ME61JG4KM9Z=%E5%BC%80%E5%8F%91%E8%80%85%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99-2 remove-specific-device-identifiers=%E5%88%A0%E9%99%A4%E7%89%B9%E5%AE%9A%E7%9A%84%E8%AE%BE%E5%A4%87%E6%A0%87%E8%AF%86%E7%AC%A6 h_01HKD1N2C8S3Y73AZ9J7JFDKQE=%E5%88%A0%E9%99%A4%E7%89%B9%E5%AE%9A%E7%9A%84%E8%AE%BE%E5%A4%87%E6%A0%87%E8%AF%86%E7%AC%A6 android-identifiers=%E5%AE%89%E5%8D%93%E6%A0%87%E8%AF%86%E7%AC%A6 h_01HKD1N2C8HZ61XHMBC0JNTK7S=%E5%AE%89%E5%8D%93%E6%A0%87%E8%AF%86%E7%AC%A6 ios-identifiers=ios%E6%A0%87%E8%AF%86%E7%AC%A6 h_01HKD1N2C8AHK4EYANG6N6ST06=ios%E6%A0%87%E8%AF%86%E7%AC%A6 developer-reference::4e0971d1=%E5%BC%80%E5%8F%91%E8%80%85%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99-3 h_01HKM6VNJFV0YJWV8KT23VTKKH=%E5%BC%80%E5%8F%91%E8%80%85%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99-3 h_01HKD1N2C8ZZX549W0KP3V16YQ=%E5%AF%B9appsflyer%E7%9A%84%E6%95%B0%E6%8D%AE%E9%9A%90%E7%A7%81%E6%9C%89%E7%96%91%E9%97%AE" />

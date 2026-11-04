---
title: 隐私清单（Privacy Manifest）
metadata:
  keywords:
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
  created_at: '2024-01-15T10:17:30Z'
  edited_at: '2026-10-14T10:13:53Z'
  id: 21677433322641
  locale: zh-cn
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/zh-cn/articles/21677433322641
---
> **概要：** Apple在2023年的全球开发者大会（WWDC23）上发布了最新的隐私清单（Privacy Manifest）政策。Privacy Manifest推出后，应用开发者可以更清晰地阐明其应用的隐私保护措施。AppsFlyer已针对AppsFlyer SDK创建了隐私清单，详情请见下文说明。

<div id="background" />

## 背景

隐私清单（Privacy Manifest）上线后，应用开发者可以记录其通过相关应用独立收集或通过第三方（如该应用中安装的第三方SDK）收集的数据类别。有了这些信息，应用开发者就能通过面向用户的隐私标签（Nutrition Labels）等方式，更准确地传达其应用中的隐私保护措施。

很多情况下，应用开发者并不了解第三方SDK所收集的数据或具体某个SDK使用数据的目的。第三方SDK能通过隐私清单（Privacy Manifest）便捷地向相关应用开发者传达此信息，帮助开发者创建准确的隐私标签（Nutrition Labels）。

<div id="what-are-nutrition-labels" />

### 什么是隐私标签（Nutrition Labels）？

隐私标签（Nutrition Labels）以简洁明了、便于理解的呈现方式展示具体应用所采取的隐私保护措施。这样，终端用户就能更清晰地了解相关应用所收集的数据及其用途。如需进一步了解隐私标签，请参考<Anchor target="_blank" href="/marketers/zh/docs/preparing-for-the-app-store-review-nutrition-labels">此文档</Anchor>。

<div id="what-is-in-the-appsflyer-privacy-manifest" />

## AppsFlyer隐私清单的内容

<div id="important" />

> 🚧 **重要提示！**
>
> 除了AppsFlyer SDK之外，您还需要明确您自己的数据收集情况、必须声明使用原因的API（Required Reasons API）、以及您的应用及其他SDK对数据的使用情况，并通过隐私标签（Nutrition Labels）传达这些信息。

AppsFlyer SDK 6.14.0中带有AppsFlyer隐私清单，其中包含以下信息；

* [数据使用情况](#数据使用情况)
* [Required Reason API（必须声明使用原因的API）](#必须声明使用原因的apirequired-reason-apis)
* [跟踪域名](#跟踪域名tracking-domains)

<div id="data-usage" />

### 数据使用情况

Apple要求应用开发者和SDK开发者记录其收集的数据类别，以及相关应用或第三方SDK收集此类数据的原因。

应用开发者可以使用Xcode创建一个隐私报告，在其中总结有关其数据收集的信息。

下表列出了AppsFlyer SDK收集的数据类型，这些信息也包含在我们的隐私清单中。

<div id="note" />

> 📘 **注意**
>
> 下表所列的信息以AppsFlyer软件的默认配置为前提。应用开发者有责任自行调整其隐私清单的内容，确保其中的信息符合其对AppsFlyer SDK的实际配置和使用场景。

| 特点 | NSPrivacyCollectedDataType | NSPrivacyCollectedDataTypeLinked | NSPrivacyCollectedDataTypeTracking | NSPrivacyCollectedDataTypePurposes |
| --- | --- | --- | --- | --- |
| 设备ID（Device ID，即IDFA和IDFV） | NSPrivacyCollectedDataTypeDeviceID | 是 | 是 | NSPrivacyCollectedDataTypePurposeThirdPartyAdvertising |
| 产品交互（Product Interaction，即应用打开） | NSPrivacyCollectedDataTypeProductInteraction | 否 | 否 | NSPrivacyCollectedDataTypePurposeAnalytics |

<div id="required-reason-apis" />

### 必须声明使用原因的API（Required Reason APIs）

Apple要求开发方对于指定的一系列API声明其使用原因。使用这些API的应用和SDK必须在隐私清单（Privacy Manifest）的Required Reson API部分中提供详细信息。Apple根据<Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api?language=objc">一系列主题</Anchor>（topics），将这些API按照功能特点及传输信息分为多种类型。6.14.0版本的AppsFlyer SDK中包含下列API：

* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">File Timestamp API（文件时间戳）</Anchor>
* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">User defaults API（用户默认设置）</Anchor>

在说明Required Reason API的用途时，应用开发者需要指出相关API的类别并阐明使用该API的具体原因。下表列出了AppsFlyer使用的API及其用途。

<div id="sdk-version-6140-and-above" />

<Accordion title="6.14.0及以上版本的SDK">

| API 类别 | API类别类型 | 使用原因 | 注意事项 |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">File Timestamp API（文件时间戳）</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | 该SDK使用<Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor>和<Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> API判断相关应用的安装日期以及更新日期。 |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">User defaults API（用户默认设置）</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | SDK会储存其运行所必须的数据，比如持续记录应用打开次数。 |

</Accordion>

<div id="sdk-versions-6130-and-earlier" />

<Accordion title="6.13.x及更早版本的SDK">

| API类别 | API类别类型 | 使用原因 | 注意事项 |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">File Timestamp API（文件时间戳）</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | 该SDK使用<Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor>和<Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> API判断相关应用的安装日期以及更新日期。 |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278394">System boot time APIs（系统启动时间）</Anchor> | NSPrivacyAccessedAPICategorySystemBootTime | 35F9.1 | 监测SDK性能（执行请求的耗时等） |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">User defaults API（用户默认设置）</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | SDK会储存其运行所必须的数据，比如持续记录应用打开次数。 |

以下代码片段中包含了上述必须声明的使用原因（Required Reasons），您可以直接将其复制粘贴到您的PrivacyInfo.xcprivacy文件中。

```xml
<key>NSPrivacyAccessedAPITypes</key>
<array>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>CA92.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryUserDefaults</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>C617.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryFileTimestamp</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>35F9.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategorySystemBootTime</string>
    </dict>
</array>
```

</Accordion>

<div id="tracking-domains" />

### 跟踪域名（Tracking Domains）

相关应用或第三方SDK中使用的任何跟踪域名（Tracking Domain）都必须在记录在隐私清单中。如果用户未通过应用跟踪透明度框架（即ATT弹窗 ）授权，同意数据跟踪（即opt-out），则iOS操作系统会拦截从用户设备传输到该域名的所有流量。AppsFlyer SDK在执行任何服务器请求之前都会先确认用户的ATT授权状态，然后再根据用户的授权状态执行该请求。

<div id="faq" />

## 常见问题解答

<div id="do-i-have-to-update-my-appsflyer-sdk" />

<Accordion title="AppsFlyer是否提供支持Privacy Manifest的SDK？">

是的，6.14.0及以上版本的SDK都全面支持Privacy Manifest。

</Accordion>

<div id="do-i-have-to-report-my-own-data-collection" />

<Accordion title="应用开发者是否必须上报自己的数据收集情况？">

是的，除了AppsFlyer及其他SDK之外，您还需要明确您自己的数据收集及使用情况、并通过隐私标签（Nutrition Labels）传达这些信息，其中必须涵盖您对AppsFlyer SDK的默认配置所做的任何更改（如应用内事件的衡量设置）。

</Accordion>

<div data-zendesk-anchors="background=%E8%83%8C%E6%99%AF h_01HCY4D9EKHYB5B3YNWRCB53F4=%E8%83%8C%E6%99%AF what-are-nutrition-labels=%E4%BB%80%E4%B9%88%E6%98%AF%E9%9A%90%E7%A7%81%E6%A0%87%E7%AD%BEnutrition-labels h_01HCY4ZASEAR69RT3YMHMSE4NP=%E4%BB%80%E4%B9%88%E6%98%AF%E9%9A%90%E7%A7%81%E6%A0%87%E7%AD%BEnutrition-labels what-to-consider-when-getting-your-app-ready-to-ios17=appsflyer%E9%9A%90%E7%A7%81%E6%B8%85%E5%8D%95%E7%9A%84%E5%86%85%E5%AE%B9 h_01HCY4D9EKTKB50BSZD7RBMMYB=appsflyer%E9%9A%90%E7%A7%81%E6%B8%85%E5%8D%95%E7%9A%84%E5%86%85%E5%AE%B9 h_01HQ5C9WGW669HBWSG4WQMJTGP=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA data-usage=%E6%95%B0%E6%8D%AE%E4%BD%BF%E7%94%A8%E6%83%85%E5%86%B5 h_01HQ03P71BG159MCE3VQY4GTMH=%E6%95%B0%E6%8D%AE%E4%BD%BF%E7%94%A8%E6%83%85%E5%86%B5 h_01HT9QHRQSKDQ8GR17N7X5QB8N=%E6%B3%A8%E6%84%8F required-reason-apis=%E5%BF%85%E9%A1%BB%E5%A3%B0%E6%98%8E%E4%BD%BF%E7%94%A8%E5%8E%9F%E5%9B%A0%E7%9A%84apirequired-reason-apis h_01HQ03NV880VHFTXQDE8R6ZRZH=%E5%BF%85%E9%A1%BB%E5%A3%B0%E6%98%8E%E4%BD%BF%E7%94%A8%E5%8E%9F%E5%9B%A0%E7%9A%84apirequired-reason-apis h_01HSZSWW6Y91BTY1GNXMMVJCEQ=sdk-version-6140-and-above h_01HT9QVD9KZVN7RXWP03XCH8JZ=sdk-versions-6130-and-earlier required-reasons-api=%E8%B7%9F%E8%B8%AA%E5%9F%9F%E5%90%8Dtracking-domains h_01HQ03NV88SJPYKBM66S7X6GP8=%E8%B7%9F%E8%B8%AA%E5%9F%9F%E5%90%8Dtracking-domains faq=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01HQQXSN96D4QTTYHG8CBE8695=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HCY5XRA96XAYYGB4XCZ8EXXG=do-i-have-to-update-my-appsflyer-sdk h_01HDDQV25KC9XWF7CJ7QBH4XW2=do-i-have-to-report-my-own-data-collection" />

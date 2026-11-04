---
title: 直接向AppsFlyer发送SKAN回传备份（iOS 15+适用）
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-08T12:09:25Z'
  edited_at: '2026-10-14T10:10:04Z'
  id: 4402320969617
  locale: zh-cn
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/zh-cn/articles/4402320969617
---
> **概要：** 从iOS 15开始，除了向广告平台发送回传数据外，您还可以通过应用内的配置额外向AppsFlyer发送回传备份。这样，AppsFlyer就能验证转化值（CV）并核实渠道回传数据的真实性。**配置完成后，您可以对AppsFlyer的Push API进行相应配置，从而向多个指定端点转发回传备份。**

<div id="why-send-postback-copies-to-appsflyer" />

## 向AppsFlyer发送回传备份的优势

* 一站式获取所有回传回传包含对广告主至关重要的信息—特别是用于评估用户质量的转化值 (CV)。由于回传数据中的CV值既没有加密也不构成回传签名，因此广告平台上报的CV值无法得到验证，并且有可能被篡改。AppsFlyer可以通过Push API将回传数据转发到您指定的端点，从而实现数据的验证和核实。
* 为您呈现Redownload（重新下载）指标。部分广告平台不会将Redownload数据共享给AppsFlyer，但这一缺口可以通过回传备份来填补。
* 查看流量侧应用的数据。
* 查看触点类型/广告互动信息。

**请注意**AppsFlyer仍需接收广告平台的回传数据，因为其中包含广告平台所提供的其他数据（如广告系列名称）。

<div id="configure-your-app-to-send-postback-copies-to-appsflyer" />

## 向AppsFlyer发送回传备份的应用配置方法

您只能设置一个SKAN回传端点（该信息来自Apple文档）。

**请按以下步骤注册AppsFlyer端点：**

1. 让您的iOS开发人员在下一个应用版本中将<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#sending-skan-postback-copies-to-appsflyer">AppsFlyer</Anchor>设置为SKAN回传端点。
2. 提交该iOS应用。
3. 新版应用上架后（非TestFlight），SKAN回传将会发送到AppsFlyer。
4. 您可以在<Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports">回传备份报告</Anchor>中查看回传内容。

<div id="important" />

> 🚧 **重要提示！**
>
> 即使完成了相关配置，如果应用当前没有SKAN流量，您仍会看到以下提示：您的应用尚未完成将iOS回传备份（iOS 15及以上）发送至AppsFlyer的设置。请务必确认您的SKAN衡量数据完整、准确且有效。”

<div id="common-misconceptions" />

## 常见误区

<div id="dont-believe-everything-you-hear" />

> 📘 **警惕“伪科普”的误导！**
>
> 您能判断以下说法的正误吗？
>
> ![TrueOrFalse.png](https://files.readme.io/77212d5a12ce2af35b0a4c87ca9e58213b4f9fd88c775007793e7abb5aaa3f04-35682597298577.png)
>
> * 广告主不再需要通过广告平台来获得回传数据。
>   * **False。** 广告主仍需依赖广告平台来解析部分关键数据。例如，只有广告平台能够将SKAN中的campaign ID与对应的广告系列名称进行映射。
> * 只要我额外设置了一个端点，就能将所有回传备份发送到这个新添加的端点。
>   * **False。** 额外的端点功能仅适用于运行iOS 15+的设备。使用旧版本的设备不会发送回传备份。

<div id="traits-and-limitations" />

## 特点与局限性

完成向AppsFlyer发送回传备份的应用配置后，相关数据反映到面板上可能需要几天的时间。

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_an_advertised_app?changes=latest_minor#see-also">Apple开发者文档</Anchor>

<div data-zendesk-anchors="why-send-postback-copies-to-appsflyer=%E5%90%91appsflyer%E5%8F%91%E9%80%81%E5%9B%9E%E4%BC%A0%E5%A4%87%E4%BB%BD%E7%9A%84%E4%BC%98%E5%8A%BF h_01HE7SV29Y7DNSKAAR91MJX986=%E5%90%91appsflyer%E5%8F%91%E9%80%81%E5%9B%9E%E4%BC%A0%E5%A4%87%E4%BB%BD%E7%9A%84%E4%BC%98%E5%8A%BF configure-your-app-to-send-postback-copies-to-appsflyer=%E5%90%91appsflyer%E5%8F%91%E9%80%81%E5%9B%9E%E4%BC%A0%E5%A4%87%E4%BB%BD%E7%9A%84%E5%BA%94%E7%94%A8%E9%85%8D%E7%BD%AE%E6%96%B9%E6%B3%95 h_01HE7SV29YDFA5Z0X4WS87YK0Y=%E5%90%91appsflyer%E5%8F%91%E9%80%81%E5%9B%9E%E4%BC%A0%E5%A4%87%E4%BB%BD%E7%9A%84%E5%BA%94%E7%94%A8%E9%85%8D%E7%BD%AE%E6%96%B9%E6%B3%95 h_01HH9WCVH4C37ZGMRZRB7EQT6B=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA common-misconceptions=%E5%B8%B8%E8%A7%81%E8%AF%AF%E5%8C%BA h_01HE7SV29YC855TGCXTCT4KHRN=%E5%B8%B8%E8%A7%81%E8%AF%AF%E5%8C%BA h_01HE7SV29YMMTPH6EKYF3GQYEN=%E8%AD%A6%E6%83%95%E4%BC%AA%E7%A7%91%E6%99%AE%E7%9A%84%E8%AF%AF%E5%AF%BC traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HHH74CC5X0T5M1F86XWMNH9V=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HE7SX466CMCC03K99H68ZRBN=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

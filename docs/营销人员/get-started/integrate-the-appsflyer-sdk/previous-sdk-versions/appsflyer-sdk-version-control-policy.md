---
title: AppsFlyer SDK版本管理政策
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Advertisers
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
  created_at: '2021-11-30T10:43:19Z'
  edited_at: '2026-10-14T10:08:31Z'
  id: 4412316953105
  locale: zh-cn
  section: Previous SDK versions
  section_id: 6551300280977
  url: https://support.appsflyer.com/hc/zh-cn/articles/4412316953105
---
> **概要：** 本文介绍了AppsFlyer SDK的版本管理政策以及目前给予维护的SDK版本。

## 版本管理说明

AppsFlyer历年来发布了多个版本的SDK。每个版本的SDK调用的API版本都有所不同。为了界定每个API在各版本SDK中的使用时长，我们制定了版本管理政策。

## 版本管理的意义

实行版本管理是为了：

* 提前知会广告主其现行SDK版本中的API下线事宜。由于新版本的采纳（即相关应用的用户升级到新版本）需要一定的时间，因此广告主必须提前了解相关信息。
* 增强稳定性（向下兼容范围为2.5年），避免广告主在使用非常陈旧的SDK时出现意外的问题。
* 帮助广告主利用新版SDK支持的新功能。

## SDK版本的生命周期

每个版本的API至少可运行2.5年。每当有新的主要或次要SDK版本上线时，AppsFlyer会为此前的次要版本（包括其各版补丁）设定下线日期。

<strong>AppsFlyer将按照原计划，在六个月的周期内，逐步停止对iOS和Android旧版SDK的支持。</strong>此机制旨在为广告主预留充足时间，以便开发团队提前规划和升级，确保应用功能不受影响。请及时升级到最新版SDK，体验最新功能、更高稳定性和持续的技术支持。

> 🚧 **重要提示！**
>
> 为了确保平稳过渡，建议应用开发者在停止支持日期前完成SDK升级。

## 停止支持与弃用的区别

为了更清晰地区分SDK的支持状态及其对数据衡量的影响，AppsFlyer将旧版SDK分为以下两类：

* **已弃用的版本**由于存在已知问题（如严重Bug），官方不再推荐使用的SDK版本。这些版本仍然可以向AppsFlyer发送数据，但不鼓励开发者继续使用，我们强烈建议您升级到受支持的版本。
* **停止支持版本：** 不再进行任何数据衡量的SDK版本。在iOS和Android平台上，激活、应用打开和应用内事件都将无法被记录。来自这类版本的请求（除非被AppsFlyer特别豁免）将收到400错误码，表示虽然SDK会继续尝试发送请求，但AppsFlye 服务器将拒绝处理，数据也不会被接收或存储。

## 当SDK版本达到其支持结束日期时会发生什么？

一旦SDK的版本达到其支持结束日期，AppsFlyer服务器将不再测量安装、会话和应用内事件。发送到这些端点的事件会直接被拦截。

鉴于应用更新后的采纳周期，**强烈建议**您的开发人员在下线日期之前预留出充分的时间，提前完成SDK升级。

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-android-sdk-release-notes">AppsFlyer安卓SDK版本说明</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-ios-sdk-release-notes">AppsFlyer iOS SDK版本说明</Anchor>

<div data-zendesk-anchors="about-versioning=%E7%89%88%E6%9C%AC%E7%AE%A1%E7%90%86%E8%AF%B4%E6%98%8E h_01HE7RHYC4YGZWF9EKK96RPMAN=%E7%89%88%E6%9C%AC%E7%AE%A1%E7%90%86%E8%AF%B4%E6%98%8E why-do-we-need-version-control=%E7%89%88%E6%9C%AC%E7%AE%A1%E7%90%86%E7%9A%84%E6%84%8F%E4%B9%89 h_01HE7RHYC4QSVTA4ZCHTKYQSAT=%E7%89%88%E6%9C%AC%E7%AE%A1%E7%90%86%E7%9A%84%E6%84%8F%E4%B9%89 sdk-version-lifecycles=sdk%E7%89%88%E6%9C%AC%E7%9A%84%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F h_01HE7RHYC41QN657ZTEQ0P45GD=sdk%E7%89%88%E6%9C%AC%E7%9A%84%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F h_01JVHFG6PN34YFWNZKX2CYHJV8=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA end-of-support-vs-deprecated=%E5%81%9C%E6%AD%A2%E6%94%AF%E6%8C%81%E4%B8%8E%E5%BC%83%E7%94%A8%E7%9A%84%E5%8C%BA%E5%88%AB h_01JVHEKR4MTFV0FDHMTQW00BCS=%E5%81%9C%E6%AD%A2%E6%94%AF%E6%8C%81%E4%B8%8E%E5%BC%83%E7%94%A8%E7%9A%84%E5%8C%BA%E5%88%AB what-happens-when-an-sdk-version-is-sunset=%E5%BD%93sdk%E7%89%88%E6%9C%AC%E8%BE%BE%E5%88%B0%E5%85%B6%E6%94%AF%E6%8C%81%E7%BB%93%E6%9D%9F%E6%97%A5%E6%9C%9F%E6%97%B6%E4%BC%9A%E5%8F%91%E7%94%9F%E4%BB%80%E4%B9%88 h_01HE7RHYC4EVSNA2F4DQ1594DH=%E5%BD%93sdk%E7%89%88%E6%9C%AC%E8%BE%BE%E5%88%B0%E5%85%B6%E6%94%AF%E6%8C%81%E7%BB%93%E6%9D%9F%E6%97%A5%E6%9C%9F%E6%97%B6%E4%BC%9A%E5%8F%91%E7%94%9F%E4%BB%80%E4%B9%88 h_01HE7RPQBD858TQSF27NFGGP43=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

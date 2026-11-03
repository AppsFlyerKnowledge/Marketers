---
title: 在拉新投放中排除老用户
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2020-05-03T10:11:31Z'
  edited_at: '2026-10-14T10:06:20Z'
  id: 360007949158
  locale: zh-cn
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/zh-cn/articles/360007949158
---
> **概要：** 概要：将现有用户排除在拉新（UA）广告的投放范围之外有助于提升新用户的获取效率，在预算不变的情况下得到更多激活，从而改善ROAS。

## 问题与结果

如果您的应用从多个渠道获取流量，这些渠道有可能会将拉新广告投放给您的现有用户。

这会从以下几个方面影响到您的投放效果：

* 重复买量——为之前已经获得的流量重复支付展示/点击费用。
* 扭曲转化率——弱化拉新投放的效果。由于向现有用户展示广告，因此拉低了新增激活数量。
* 潜在用户流失——本来可能会激活应用的潜在用户由于没有看到广告而不发生转化。

详情请见此处说明。

## 解决方案

这里列出的解决方案概括说明了如何与广告平台同步用户信息，以将现有用户排除在拉新投放之外。

### 手动更新

通过AppsFlyer收集用户层级别的原始激活数据，并基于此信息创建设备ID列表。然后将该列表发送给广告平台，用于在投放中排除相关用户。

您可以通过以下几种方法将这些原始数据添加到您的BI系统：

* 下载原始数据报告
* 定期调用原始数据Pull API来拉取数据
* 使用Push API实时收集数据
* 通过SDK获取转化数据

> 📘 **注意**
>
> 在您与广告平台手动同步最新的设备ID列表期间，拉新广告有可能会被投放到最近刚刚激活应用的用户。

### 受众共享（Audiences）

**受众共享**功能非常适用于禁投名单的维护：

* 省时省力——广告平台侧和广告主侧都不需要任何开发或维护。
* 简单易用——完成简短的初始设置后即可开始上传人群包。
* 快捷高效——每24个小时自动向广告平台发送用户分组。

<div data-zendesk-anchors="issues-and-consequences=%E9%97%AE%E9%A2%98%E4%B8%8E%E7%BB%93%E6%9E%9C solutions=%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88 manual-update=%E6%89%8B%E5%8A%A8%E6%9B%B4%E6%96%B0 audiences=%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%ABaudiences" />

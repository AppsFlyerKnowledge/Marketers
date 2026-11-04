---
title: 更改应用时区设置
metadata:
  keywords:
    - Time Zone
    - Existing Apps
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2017-01-12T15:33:00Z'
  edited_at: '2026-10-23T12:43:24Z'
  id: 115000306786
  locale: zh-cn
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/zh-cn/articles/115000306786
---
> **内容概要：** 为应用设置或更改专属时区，可以让应用数据的展示时间更符合您所在的时区，或与广告渠道使用的时区保持一致。本文将介绍更改时区对 AppsFlyer 平台数据报表的影响。

<div id="why-change-the-time-zone" />

## 为什么要更改时区？

新应用默认使用 UTC 时区（UTC+0）。更改应用时区后，AppsFlyer 平台中数据的展示方式也会随之变化。

* **适用场景：** 您所在的时区不是 UTC，但希望应用数据按照您所在的时区展示，或与 Meta 广告、Google 等其他合作渠道所使用的时区保持一致。
* **目的：** 简化 AppsFlyer 与其他广告渠道之间的数据对比。
* **解决方法：** 将 AppsFlyer 平台中的应用时区调整为与其他服务提供商一致。平台默认支持夏令时的自动调整，无需单独配置。

代理和广告渠道的数据时区规则：

* **代理：** 按应用所有者设置的时区查看数据，无法自行更改时区。
* **广告渠道：** 始终使用 UTC 时区查看数据，不受广告主设置的应用时区影响。

<div id="changing-the-time-zone" />

## 如何更改时区？

只有管理员可以更改应用时区，且两次更改之间必须至少间隔 48 小时。在上一次更改后的 48 小时内，时区设置不可修改。

**更改应用时区的步骤：**

1. 在 AppsFlyer 左侧菜单中，依次进入 **设置** > **应用设置**。
2. 在 **本地化 > 时区** 中，选择 **UTC**。
3. 点击 **保存设置**，然后等待 48 小时。
4. 再次进入 **设置** > **应用设置**。
5. 在 **本地化** > **时区** > 中，选择所需时区对应的城市或国家/地区。
6. 点击 **保存设置**。  
   更改将在下一个 UTC 时间 00:00 生效。

<div id="example" />

> 📄 **示例**
>
> * 10 月 24 日 22:00，完成上述第 1–6 步。
> * 10 月 25 日 00:00（UTC），新时区设置生效。

更改时区后的影响

* 数据展示所使用的时区取决于报表类型和报表时间范围，具体规则见下文。
* 更改时区当天及次日，汇总报表中的数据可能出现异常。
  * 成本数据会在更改时区当天及次日重复计算。

<div id="aggregate-data" />

#### 汇总数据报表

<table><thead><tr><th rowspan="2">报表类型 </th><th colspan="3">报告日期范围</th></tr><tr><th>在更改<span>之前</span>开始和结束 </th><th>在更改<span>之后</span>开始和结束 </th><th>在时区更改之前开始，更改之后结束</th></tr></thead><tbody><tr><td>My Dashboards</td><td><p>不支持更改面板时区后的跨时区数据展示。更改面板时区后，数据仅以 UTC 时区提供。</p></td><td>当前时区</td><td>仅展示更改之后日期的数据。</td></tr><tr><td>概览面板</td><td>更改前的时区</td><td>当前时区</td><td><p>拆分为两种时区：</p><ul><li>更改前：UTC</li><li>更改后：当前时区</li></ul></td></tr><tr><td>事件和自定义面板</td><td>UTC</td><td>当前时区</td><td><p>拆分为两种时区：</p><ul><li>更改前：UTC</li><li>更改后：当前时区</li></ul></td></tr><tr><td>活动面板</td><td>更改前的时区</td><td>当前时区</td><td>UTC</td></tr><tr><td>群组、留存和数据透视表</td><td>UTC</td><td>当前时区 (1)</td><td>UTC</td></tr><tr><td>Master API</td><td colspan="3"><ul><li>默认：UTC</li><li>可选：<a href="./pull-api-aggregate-data" target="_blank">提取数据时选择时区</a> </li></ul></td></tr><tr><td colspan="4">注意：<br/>（1）在同一个报表时间范围内，所有应用必须使用相同的应用时区。否则，系统会将时区恢复为 UTC。</td></tr></tbody></table>

<div id="raw-data-reports" />

#### 原始数据报表

<table><thead><tr><th rowspan="2">报表类型 </th><th colspan="3">报告日期范围</th></tr><tr><th>在更改<span>之前</span>开始和结束 </th><th>在更改<span>之后</span>开始和结束 </th><th>在时区更改之前开始，更改之后结束</th></tr></thead><tbody><tr><td>导出页面中的原始数据</td><td>当前时区</td><td>当前时区</td><td>当前时区</td></tr><tr><td>Push API</td><td colspan="3">分别提供 UTC 时间字段和应用时区时间字段。应用时区时间根据事件发生时所选的时区计算。</td></tr><tr><td>Pull API</td><td colspan="3"><ul><li>默认：UTC</li><li>可选：<a href="./pull-api-aggregate-data" target="_blank">提取数据时选择时区</a> </li></ul></td></tr><tr><td>Data Locker</td><td colspan="3">不受时区变更影响，日期字段始终使用 UTC。</td></tr></tbody></table>

<div data-zendesk-anchors="why-change-the-time-zone=%E4%B8%BA%E4%BB%80%E4%B9%88%E8%A6%81%E6%9B%B4%E6%94%B9%E6%97%B6%E5%8C%BA h_01HJR69P6Z44SZA5A684H82PNV=%E4%B8%BA%E4%BB%80%E4%B9%88%E8%A6%81%E6%9B%B4%E6%94%B9%E6%97%B6%E5%8C%BA changing-the-time-zone=%E5%A6%82%E4%BD%95%E6%9B%B4%E6%94%B9%E6%97%B6%E5%8C%BA h_01HJR69P6ZWJQ47FQY2HATAAE3=%E5%A6%82%E4%BD%95%E6%9B%B4%E6%94%B9%E6%97%B6%E5%8C%BA h_01HJR69P6Z6B0Q6E6996WXVZ0N=%E7%A4%BA%E4%BE%8B aggregate-data=%E6%B1%87%E6%80%BB%E6%95%B0%E6%8D%AE%E6%8A%A5%E8%A1%A8 h_01HJR69P6ZY8JJBCBSDZKN75N6=%E6%B1%87%E6%80%BB%E6%95%B0%E6%8D%AE%E6%8A%A5%E8%A1%A8 raw-data-reports=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E8%A1%A8 h_01HJR69P6ZDXXK8ZTKK3E774VJ=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E8%A1%A8" />

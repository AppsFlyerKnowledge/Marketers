---
title: '[Beta] 基于用户的跨平台归因'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Cross-Platform Measurement
    - pm-gil-bouchnik
  created_at: '2025-09-16T13:58:09Z'
  edited_at: '2026-10-14T10:01:29Z'
  id: 39104189339793
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/39104189339793
---
> **概要：** 了解什么是基于用户的跨平台归因，它是如何运作的，以及如何在 AppsFlyer 中设置它。

## 什么是基于用户的归因？

基于用户的归因是一种跨平台模型，依赖于持久的 <Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">客户用户 ID (CUID)</Anchor> 来链接跨平台的转化事件。使用 CUID，该模型将所有活动归因于驱动用户首次转化事件的原始媒体来源。

### 跨平台用户旅程示例

例如，用户点击 Google 网页广告，注册并在桌面浏览器上完成购买。后来，同一用户点击 Instagram 移动广告，安装移动应用，并进行另一次应用内购买。一周后，用户安装品牌的 CTV 应用，使用相同的 CUID 登录，并在此处开始付费订阅。

因为 CUID 一致地识别跨平台的用户，而 Google 网页活动是与该 CUID 相关的第一个非有机启动事件，所以所有后续活动 - 包括移动应用购买和 CTV 订阅 - 都归因于 Google 活动。

### 基于用户的归因与基于设备的归因

该模型解决了 **基于设备的归因** 的一个关键限制，该模型将每个设备视为单独的用户，并在平台之间碎片化用户旅程。相比之下，**以用户为中心的归因** 使用持久的 CUID 链接跨设备事件，使得一致的测量、准确的活动归因和对整个产品线的生命周期价值的真实理解成为可能。

以下用户旅程示例说明了以设备为中心的归因与以用户为中心的归因之间的区别：

[<Image alt="user-journey.png" src="https://files.readme.io/892efd3cdcaa15848baefdd50e65dcdc9448d423e4b6787c067dcbdd5c801dd0-39104359761169.png" width="2048px" />](https://files.readme.io/892efd3cdcaa15848baefdd50e65dcdc9448d423e4b6787c067dcbdd5c801dd0-39104359761169.png)

用户在网页上点击 Meta 广告，被重定向到广告主的网站，注册并创建账户。后来，同一用户安装广告主的 iOS 应用，登录并进行 50 美元的购买。几天后，用户看到 YouTube 广告，安装广告主的 PC 应用，再次登录，并进行 100 美元的购买。

基于设备的归因将 0 美元归因于 Meta 广告，而基于用户的归因将 150 美元归因于此。下表显示了在每个模型下如何归因此旅程：

| 应用内购买事件 | **设备中心归因** | **用户中心归因 (CUID)** |
| --- | --- | --- |
| **iOS 应用购买** ($50) | 归因于 **自然流量** (设备上未执行过广告点击) | 归因于 **Meta** (来自初始网页广告) |
| 应用内购买 | 归因于 **YouTube** (基于最近的设备级交互) | 归因于 **Meta** (通过 CUID 识别的同一用户) |
| **总购买额** ($150) | **$50 归因于自然流量**, **$100 归因于 YouTube** (在多个活动中分配) | **$150 总计** 归因于 Meta (单一统一来源) |

### 什么使事件成为跨平台归因的候选？

如果事件满足 **所有** 以下条件，则该事件被视为 **跨平台归因的候选**：

* **CUID 存在：** 事件必须包含有效的 <Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">客户用户 ID (CUID)</Anchor> — 一个持久的、广告商提供的标识符 (例如，登录 ID 或哈希电子邮件)，可以在设备和平台之间唯一标识用户。
  * 如果事件缺少 CUID，但共享相同的 `appsflyer_id`，AppsFlyer 可以在短处理窗口内填补 CUID — 最长可达在第一个到达的 CUID 事件之前的 4 小时。有关更多信息，请参见下面的 [CUID 丰富处理窗口](#cuid-丰富处理窗口)。
  * 没有 CUID 的事件且无法通过 CUID 丰富过程进行丰富的事件仍然包含在跨平台归因中。在这些情况下，归因是通过其设备级（经典）归因方法确定的。
* **属于产品线：** 生成事件的应用必须是 **产品线** 的一部分 — 一组相关应用（例如，iOS、Android、CTV）在同一品牌下，归因范围和配置是集体的。有关更多信息，请参见 <Anchor target="_blank" href="/marketers/zh/docs/product-line-group-apps-for-cross-platform-attribution#产品线简介">跨平台归因的组应用程序</Anchor>。
* **在非活动恢复窗口内：** 事件必须在 **非活动窗口** 内发生——这是一个可配置的时间段（例如，7到390天），在此期间，CUID 仍被视为活跃并有资格在特定产品线内进行归因。如果在此窗口内未见到 CUID，则其先前的归因映射将被丢弃。
* **设备级归因字段存在：** 事件必须已经包含有效的 **设备级归因参数**（例如，媒体来源、活动 ID），这些参数源自 AppsFlyer 的经典基于设备的归因模型。

### 如何确定归因来源？

该模型将给定用户（CUID）的所有事件归因于驱动用户首次转化的 **原始媒体来源**。

归因的原始媒体来源是使用以下逻辑确定的：

* 对于产品线中具有 CUID 的每个应用内事件，AppsFlyer 确定该 CUID 的 **最早** 启动事件（即具有有效媒体来源的启动事件）。
* 经典设备中心归因所归因的媒体来源被视为该应用内事件的归因来源。
* 该媒体来源被用作与该 CUID 和产品线相关的所有后续事件的 **用户获取跨平台归因来源**。
* 如果应用内事件缺少 CUID，AppsFlyer 会在 1-4 小时的 [丰富处理窗口](#cuid-丰富处理窗口) 内尝试填补它。
* 如果没有 CUID 的事件在定义的 CUID [丰富窗口](#cuid-丰富处理窗口) 之外到达，它仍将包含在跨平台归因中。这些事件使用其设备级（经典）归因方法进行归因。

> 📘 **注意**
>
> AppsFlyer 仅在 **同一产品线内** 匹配相同的 CUID。我们不尝试在不同的产品线或客户之间匹配、推断或共享 CUID。这确保了严格的隐私优先方法，使每个客户的数据保持孤立和独立。

#### CUID 丰富处理窗口

CUID 丰富处理窗口是一个时间段（1-4 小时），在此期间，AppsFlyer 处理新到达的应用内事件，以填补缺失的客户用户 ID（CUID）。这使得跨平台归因成为可能，即使某些应用内事件在没有CUID的情况下到达。

**CUID丰富化是如何工作的**

* 每1-4小时，AppsFlyer会运行一个处理作业。
* 如果一个事件在没有CUID的情况下到达，但与另一个有CUID的事件共享相同的`appsflyer_id`，AppsFlyer会补充缺失的CUID。
* 这种拼接仅适用于在处理窗口期间接收到的事件。

**CUID丰富化示例**

* 02一个*首次打开应用*事件被记录，带有`appsflyer_id = XYZ`。
* 02一个*注册*事件被记录，带有`cuid = 123`和`appsflyer_id = XYZ`。
* 024小时的处理窗口结束。AppsFlyer追溯性地将`cuid = 123`拼接到*首次打开应用*事件。
* 02一个*购买*事件被记录，带有`appsflyer_id = XYZ`但没有CUID。因为事件在窗口关闭后到达，AppsFlyer不会将`cuid = 123`拼接到它。

**CUID丰富化的限制**

* 在**1-4小时处理窗口外**到达的没有CUID的事件，使用经典的AppsFlyer归因进行归因，并添加到跨平台归因方法的结果中。
* CUID拼接在处理窗口之外**不适用追溯**。

> 👍 **提示**
>
> 为了最大化跨平台匹配，始终在每个发送的应用内事件中包含CUID。

## 跨平台归因的设置方式

要设置跨平台归因，您需要在AppsFlyer中应用一些设置，并在您的应用代码中实现特定的SDK功能。

* **在AppsFlyer中**，将您的应用分配到一个产品线，选择加入跨平台归因，并指定不活动恢复窗口。有关更多信息，请参见<Anchor target="_blank" href="/marketers/zh/docs/product-line-group-apps-for-cross-platform-attribution#如何设置产品线">设置产品线</Anchor>。
* **在您的应用中**，设置AppsFlyer SDK以发送带有CUID的事件。有关开发者说明，请参见[设置客户用户 ID](https://dev.appsflyer.com/hc/docs/set-customer-user-id)。

## 查看跨平台归因结果

* 要查看跨平台归因结果，请参见<Anchor target="_blank" href="/marketers/zh/docs/end-user-events-cross-platform-report-in-data-locker">数据锁定终端用户事件跨平台报告</Anchor>。
* （规划中）在我的仪表板中提供了一种新的归因方法

<div data-zendesk-anchors="what-is-userbased-attribution=%E4%BB%80%E4%B9%88%E6%98%AF%E5%9F%BA%E4%BA%8E%E7%94%A8%E6%88%B7%E7%9A%84%E5%BD%92%E5%9B%A0 h_01K59D3JXN9P5ZN40WX957CHKC=%E4%BB%80%E4%B9%88%E6%98%AF%E5%9F%BA%E4%BA%8E%E7%94%A8%E6%88%B7%E7%9A%84%E5%BD%92%E5%9B%A0 a-crossplatform-user-journey-example=%E8%B7%A8%E5%B9%B3%E5%8F%B0%E7%94%A8%E6%88%B7%E6%97%85%E7%A8%8B%E7%A4%BA%E4%BE%8B h_01K59D3JXN4WJ3HN0AXN58N877=%E8%B7%A8%E5%B9%B3%E5%8F%B0%E7%94%A8%E6%88%B7%E6%97%85%E7%A8%8B%E7%A4%BA%E4%BE%8B userbased-vs-devicebased-attribution=%E5%9F%BA%E4%BA%8E%E7%94%A8%E6%88%B7%E7%9A%84%E5%BD%92%E5%9B%A0%E4%B8%8E%E5%9F%BA%E4%BA%8E%E8%AE%BE%E5%A4%87%E7%9A%84%E5%BD%92%E5%9B%A0 h_01K59D3JXN3EXS90N2AX7DXV3B=%E5%9F%BA%E4%BA%8E%E7%94%A8%E6%88%B7%E7%9A%84%E5%BD%92%E5%9B%A0%E4%B8%8E%E5%9F%BA%E4%BA%8E%E8%AE%BE%E5%A4%87%E7%9A%84%E5%BD%92%E5%9B%A0 what-makes-an-event-a-candidate-for-crossplatform-attribution=%E4%BB%80%E4%B9%88%E4%BD%BF%E4%BA%8B%E4%BB%B6%E6%88%90%E4%B8%BA%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0%E7%9A%84%E5%80%99%E9%80%89 h_01K59D3JXNNYZHYFAPRH50E4Z4=%E4%BB%80%E4%B9%88%E4%BD%BF%E4%BA%8B%E4%BB%B6%E6%88%90%E4%B8%BA%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0%E7%9A%84%E5%80%99%E9%80%89 how-is-the-attribution-source-determined=%E5%A6%82%E4%BD%95%E7%A1%AE%E5%AE%9A%E5%BD%92%E5%9B%A0%E6%9D%A5%E6%BA%90 h_01K59D3JXNGNZYAYPG13SZ98V1=%E5%A6%82%E4%BD%95%E7%A1%AE%E5%AE%9A%E5%BD%92%E5%9B%A0%E6%9D%A5%E6%BA%90 h_01K59D3JXNG9KDQ11QPNK3Z0EW=%E6%B3%A8%E6%84%8F the-cuid-enrichment-processing-window=cuid-%E4%B8%B0%E5%AF%8C%E5%A4%84%E7%90%86%E7%AA%97%E5%8F%A3 h_01K59D3JXN5CYVB6F84DTRBZS9=cuid-%E4%B8%B0%E5%AF%8C%E5%A4%84%E7%90%86%E7%AA%97%E5%8F%A3 h_01K6ZF1RRQ47HAFZNP4RK083W9=%E6%8F%90%E7%A4%BA set-up-crossplatform-attribution=%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01K59D3JXNH84WMZ6PQ4BVF44B=%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F view-crossplatform-attribution-results=%E6%9F%A5%E7%9C%8B%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0%E7%BB%93%E6%9E%9C h_01K59D3JXNGGG4AKEXM9Q9KA6A=%E6%9F%A5%E7%9C%8B%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0%E7%BB%93%E6%9E%9C" />

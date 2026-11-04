---
title: AppsFlyer与应用商店之间的归因差异
metadata:
  keywords:
    - Google Play
    - AppsFlyer
    - iTunes
    - installs
    - Discrepancies
    - App Stre
    - Compare
    - Account
    - Advertisers
    - app store
    - appstore
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T12:52:53Z'
  edited_at: '2026-10-14T10:15:12Z'
  id: 207040726
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/207040726
---
> **概要：**

<div id="note" />

<div id="attribution-discrepancies" />

## 归因差异

移动归因生态系统中所有参与者使用的归因模型存在固有差异。这同样适用于 AppsFlyer 和主要应用商店、iTunes 应用商店和 Google Play。 **请注意**：

AF\_vs\_app\_stores.png


| <span id="why-appsflyer-attributes-less"></span>原因 |  | AppsFlyer |  |
| --- | --- | --- | --- |
| **对安装的定义** | 一旦用户下载并安装应用程序，应用程序商店就会记录安装，无论用户是否稍后启动应用程序。 | 从未启动的用户不会计入AppsFlyer，即使他们下载并安装（通过应用商店定义）。 |  |
| **安装记录日期** | 应用商店将下载日期记录为安装日期 | AppsFlyer 将首次启动的日期记录为安装日期 | 在 AppsFlyer 的控制面板上使用较长的时间作为您查询的日期范围, 以最大限度地减少这种差异。 |
| **时区** |  |  |  |
| Android 用户卸载并在定义的重新归因**窗口中**重新安装 | 有时, Google Play 为同一用户显示两个唯一安装, 而不考虑第一次安装所需的时间。另外的时候显示唯一的用户, 因此与 AppsFlyer 差异较小。 |  | 您可以<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">将重新归因窗口设置</Anchor>为1到24个月。 |
| iOS 用户卸载并在定义的再归因窗口之外的重新安装 |  |  | 您可以<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">将重新归因窗口设置</Anchor>为1到24个月。 |


| <span id="why-appsflyer-attributes-more"></span>原因 |  | AppsFlyer |  |
| --- | --- | --- | --- |
|  |  |  | <ul><li>当大多数用户完成应用程序升级时, 此峰值通常会在几天后下降。</li></ul> |
| **设备 ID 重置和限制广告跟踪 (LAT) 欺诈** |  |  | AppsFlyer 的 <Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide">Protect360 反欺诈解决方案</Anchor>可以很容易地检测到你的应用是否有这些类型的欺诈。 |
|  |  |  | 如果你在<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution">店外的 Android 市场</Anchor>上做广告, 请查阅文档以进行正确的设置。 |
|  | 有时, Google Play 为同一用户显示两个唯一安装, 而不考虑第一次安装所需的时间。另外的时候显示唯一的用户, 因此与 AppsFlyer 差异较小。 |  | 您可以<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">将重新归因窗口设置</Anchor>为1到24个月。 |

<div data-zendesk-anchors="attribution-discrepancies=%E5%BD%92%E5%9B%A0%E5%B7%AE%E5%BC%82 h_01HNWP7A6GQC5ZX6WKBW411DVG=%E5%BD%92%E5%9B%A0%E5%B7%AE%E5%BC%82 h_01HNWP7A6GZJS246548Q5AFPZR=%E5%BD%92%E5%9B%A0%E5%B7%AE%E5%BC%82 h_01HNWP7A6G85PR1R66Q3KCRPNW=why-appsflyer-attributes-less h_01HNWP7A6GVVWMV6HECXQFTJT6=why-appsflyer-attributes-more" />

---
title: Snapchat — 高级 SRN 对接设置
metadata:
  keywords:
    - configuration
    - snapchat measurement partner
    - snapchat
    - measurement
    - snapchat measurement analytics
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-13T12:28:59Z'
  edited_at: '2026-10-21T08:29:08Z'
  id: 211011983
  locale: zh-cn
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/zh-cn/articles/211011983
---
> **At a glance:** 本文介绍如何设置 AppsFlyer 与 Snapchat 的对接，以进行归因衡量。 Snapchat 属于高级 SRN（自归因渠道，Self-Reporting Network）。

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/snapchat.png?v=1" width="52px" />

<div id="overview" />

## 概述

通过高级 SRN 对接，所有获得<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent">双重授权</Anchor>的流量都会按照常规 SRN 流量进行归因和报告。对于未获得用户授权的流量，AppsFlyer 可以根据 Snapchat 提供的点击和展示数据，采用<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#高级srn的归因原理">其他归因方式</Anchor>进行归因和衡量，同时遵守相关隐私限制。

<div id="set-up-snapchat-integration" />

## 设置 Snapchat 对接

**前提条件：** 您需要拥有 Snapchat 账户。如果尚未注册，请先联系 Snapchat 开通账户，再进行对接设置。

**设置新的对接：**

1. 在 AppsFlyer 中，前往**协作（Collaborate）> 渠道对接（Partner Integrations）> Marketplace** 标签页。  
   （**如需编辑现有对接：** 请前往**协作（Collaborate）> 渠道对接（Partner Integrations）> 已启用的对接（Active integrations）** 标签页。）
2. 选择相应的 App。
3. 搜索 Snapchat，然后点击**Integrate**（对接）。
4. 在**Integration**（对接）标签页中，开启<strong>启用渠道（Activate partner）</strong>开关。  
   **注意：** 只要您仍在使用 Snapchat，**该开关就必须保持开启状态**。详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">启用和停用渠道</Anchor>。
5. 根据下文各标签页的说明，完成相关配置。详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">渠道对接</Anchor>。

<Accordion title="Integration（对接）标签页">

此对接支持点击归因、展示归因、成本数据和受众数据。

<div id="activate-partner" />

#### 启用渠道

首次进入此页面时，您必须开启**启用渠道（Activate Partner）**，才能进行后续设置。  
有关详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">启用和停用渠道</Anchor>。

**启用归因**

开启**启用渠道（Activate Partner）**，以允许 AppsFlyer 对 Snapchat 流量进行归因。

<Image align="center" alt="mceclip0.png" src="https://files.readme.io/cf4e73fec951e4e9d2c1919ca20adff88fc0d49d7fea9b033ab9c39194ce2702-360003259638.png" />

<div id="general-settings" />

#### 常规设置

**Snap App ID**

1. 登录 Snap Business Manager，进入 Apps，复制 Snap App ID（有关如何生成 Snap App ID 的说明，请参阅 Snapchat 的<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/a/snap-app-id">官方指南</Anchor>）。
2. 将该 ID 粘贴到 AppsFlyer 中的 Snap App ID 字段。

<Image align="center" alt="snapchat-app-id.png" src="https://files.readme.io/2e5f53240893e2a80ba36065f67f4504f69e1167d96ef35bd7a4ab874d5a7bb9-360008280878.png" />

**如果 App 由代理推广，请注意以下事项**：

* 只有广告主可以添加 Snap App ID。
* 如果代理与您在 Snapchat 广告平台上隶属于同一组织，请仅使用一个 Snap App ID。
* 如果代理与您在 Snapchat 广告平台上隶属于不同组织，请向代理索取该 App 对应的 Snap App ID，并将其填写到此字段中。此字段支持填写多个 ID。每输入一个 ID 后，请按 Enter 键。

<div id="advanced-privacy" />

#### 高级隐私（Advanced Privacy）

**Advanced Privacy**（AP，高级隐私）开关用于控制 AppsFlyer 向 Snapchat 发送哪些事件。在 Snapchat 端，此设置也称为**Advanced Conversions**（高级转化）。

* **关闭 Advanced Privacy**：AppsFlyer 会向 Snapchat 发送所有安装、再互动和应用内事件，用于归因，包括未提供 IDFA（广告主标识符，Identifier for Advertisers）的用户所产生的相关事件。  
  **重要提示：** 如需使用 Snapchat 的<Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/unified-attribution?language=en_US">统一归因解决方案</Anchor>，必须关闭 Advanced Privacy 开关。
* **开启 Advanced Privacy**：AppsFlyer 仅向 Snapchat 发送已提供 IDFA 的用户所产生的安装、再互动和应用内事件。

> 📘 **Note**
>
> 即使获得广告主授权，代理也无法开启 Advanced Privacy。该设置仅限广告主使用。

<div id="advanced-matching-data-sharing" />

#### 高级匹配数据共享（Advanced Matching data sharing）

开启**Advanced Matching 数据共享**后，如果发送给 AppsFlyer 的事件信息中包含哈希处理后的邮箱、电话号码、名字或姓氏等高级匹配字段，这些字段就会共享给 Snapchat。详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/advanced-matching-data-sharing">高级匹配数据共享</Anchor>。

<div id="install-attribution" />

#### 激活归因

您可以针对仅浏览、点击或与广告互动的用户，分别设置不同的归因窗口，以归因其新增激活（首次打开）。请注意，只有在回溯窗口内发生的激活才会归因给 Snapchat。

**注意：** 不支持重装激活的归因（即设备上非首次安装产生的激活）。

1. 将**点击型激活回溯窗口**设置为 1-23 小时或 1-30 天。**注意：** Snapchat 建议将点击型激活回溯窗口设置为 7 天，以便与其平台对齐。

> 📘 **Note**
>
> 设置点击型回溯窗口后，系统会同步确定互动观看和互动点击的回溯窗口。

2. 【可选】开启**浏览型激活归因**，并设置回溯窗口：
   * **浏览型激活回溯窗口**可设置为 1-24 小时。**注意：** Snapchat 建议将浏览型激活回溯窗口设置为 1 天，以便与其平台对齐。

<div id="re-engagement-attribution" />

#### 再互动归因

您可以针对仅浏览、点击或与广告互动的现有用户，分别设置不同的归因窗口，以归因其再互动。请注意，只有在回溯窗口内发生的再互动才会归因给 Snapchat。

1. 将**再互动点击型回溯窗口**设置为 1-23 小时或 1-30 天。**注意：** Snapchat 建议将再互动点击型回溯窗口设置为 7 天，以便与其平台对齐。

> 📘 **Note**
>
> 设置再互动点击型回溯窗口后，系统会同步确定再互动的互动观看和互动点击回溯窗口。

2. 【可选】开启**再互动浏览型归因**，并设置回溯窗口：
   * **再互动浏览型回溯窗口**可设置为 1-24 小时。**注意：** Snapchat 建议将再互动浏览型回溯窗口设置为 1 天，以便与其平台对齐。
3. 将**再互动窗口**设置为 1-23 小时、1-90 天或**整个生命周期**。

<div id="ignore-active-users-for-retargeting" />

#### 再营销时忽略活跃用户

设置一个窗口期，用来忽略在该期间内打开过您应用的用户所产生的<Anchor target="_blank" href="/marketers/zh/docs/set-retargeting-inactivity-window#不活跃时长">再互动和再归因</Anchor>。也就是说，这些用户在窗口期内的行为不会被记录到 AppsFlyer 中。

> 📘 **Note**
>
> 对于在设定窗口期内处于**沉睡**状态的用户，其再互动和再归因转化**仍会被记录**。

1. 开启**再营销时忽略活跃用户**。
2. 设置不活跃窗口。

<div id="in-app-event-postbacks" />

#### 应用内事件回传

通过回传，将 AppsFlyer 事件映射给渠道。开启回传后，被拦截的应用内事件（包括被 Protect360 拦截的事件，或未通过目标验证规则的事件）也会一并发送。

<Image align="center" alt="mceclip0.png" src="https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png" />

**配置应用内事件回传：**

1. 设置**渠道 ID**（如有需要）。
2. 开启**应用内事件回传**。
3. 如有需要，设置**应用内事件回传窗口**（详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">应用内事件回传窗口配置</Anchor>）。
4. 如有相关选项，选择自动或手动发送事件。详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">按原样发送所有事件</Anchor>。
5. 点击**添加事件**，将 SDK 事件或服务器对服务器（S2S）事件添加到列表中。
6. 填写所需参数。
7. 【可选】点击 <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> 为向渠道发送特定应用内事件设置条件。  
   详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">带条件的应用内事件回传</Anchor>。

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer 事件** | 事件名称，即 AppsFlyer 从集成在您应用中的 SDK 或服务器对服务器事件中接收到的事件名称。<br />**提示**：找不到您要的事件？<ul><li>请先在非自然激活的设备上完成该事件，再重新检查。</li><li>直接在**AppsFlyer 事件**字段中输入事件名称，然后点击**创建自定义事件**。详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">自定义事件映射</Anchor>。</li></ul> |
| **映射到的渠道事件** | 渠道侧为每个事件定义的专属名称或 ID。可选的映射方式包括：<ul><li>**文本字段：** 从渠道处获取对应的事件 ID。</li><li>**下拉菜单：** 选择最合适的 AppsFlyer 预定义事件。</li><li>**按原样**：不做名称映射，直接发送事件。</li></ul> |
| **事件来源** | 选择回传的发送范围：<ul><li>**仅该渠道**：仅当事件归因给该渠道时才发送回传。</li><li>**所有媒体渠道（含自然量）**：无论事件归因给哪个渠道，或属于自然量，都发送回传。</li></ul> |
| **回传内容** | <ul><li>**无数据（默认）**：只发送事件本身，不带事件值。</li><li>**值和收入**：发送所有事件参数，**含**收入值（如有）。</li><li>**仅发送值**：发送**除**收入外的所有参数。</li></ul> |

</Accordion>

<Accordion title="归因链接标签页">

Snapchat 不支持归因链接。

> 📘 **Note**
>
> 与 Facebook、Apple Ads、Google Ads 等其他 SRN 一样，Snapchat 不使用外部归因链接，因此此标签页不适用。

</Accordion>

<Accordion title="成本标签页">

成本对接可提供以下汇总数据：

* 广告系列、广告组、广告及渠道入口维度的成本数据。详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">广告平台成本对接表</Anchor>，其中列出了各渠道支持的维度、指标和功能。  
  **注意：** 成本数据需要订阅<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>。
* 点击和展示数据。

**启用 Cost API**：

* 请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">对接说明</Anchor>操作。

<div id="cost-data-sync-status" />

<Accordion title="成本数据同步状态">

您可以在成本（及广告收入）对接状态面板，或各广告平台单独的面板中，<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">查看 Cost API 状态</Anchor>，以及 AppsFlyer 上一次成功拉取匹配成本数据的时间。

</Accordion>

<div id="stop-snapchat-cost-sync" />

<Accordion title="关闭 Snapchat 成本同步">

**如需停止获取 Snapchat 成本数据，并删除已连接的 Snapchat 账户：**

* <Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">在操作列中，将鼠标悬停在该账户上，点击**删除连接**</Anchor>。  
  删除后，AppsFlyer 将停止获取成本数据。但不会影响历史数据。

</Accordion>

> 📘 **Note**
>
> * 请确保您在 Snapchat 中设置的广告系列仅针对 iOS 或仅针对安卓，不要同时覆盖两个平台。如果一个广告系列同时投放给两个平台，AppsFlyer 将无法按应用拆分成本，导致成本数据无法显示。
> * 为避免成本数据出现差异，请确保应用设置和您的 Snapchat 广告账户使用相同的时区。
> * 设置好 Snapchat 的成本数据后，请勿更改任何在投广告系列、广告组或单条广告的名称，否则可能导致成本数据严重偏差或缺失。

</Accordion>

<Accordion title="广告收入标签页">

此渠道的对接不支持广告收入。

</Accordion>

<Accordion title="权限标签页">

选择需要向 Snapchat 开放的<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">权限</Anchor>，以便其访问您的数据并执行相应操作。

> 📘 **Note**
>
> 即使对接已停用，只要权限开关仍处于开启状态，相应权限就会继续保留。

</Accordion>

<div id="web-to-app-measuring-app-activity-for-non-app-campaigns" />

## Web-to-App：衡量非 App 推广活动带来的 App 内活动

通过与 Snapchat 的对接，AppsFlyer 可以全面衡量归因给 Snapchat 的非 App 推广活动所带来的 App 内活动，例如激活、再互动和应用内事件。

举例来说，即使广告落地页是网页，也可以衡量由此产生的 App 激活，从而实现对 Web-to-App（W2A）用户路径的衡量。要启用此类衡量，请在 Snapchat Ads Manager 中开启<Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/app-id-tracking">Snap App ID Tracking</Anchor> 开关。

按照上述方式配置后，您就能有效衡量 Snapchat 非 App 推广活动带来的 App 内活动，更好地了解用户行为。

<div id="deep-linking-with-snapchat" />

## 使用 Snapchat 深度链接

Snapchat 深度链接的原理是：在 Snapchat 平台原生深度链接的基础上，加入 AppsFlyer 参数。

实现 Snapchat 深度链接的方法：

1. 确认已为 Snapchat 的再营销启用[**深度链接**](/docs/snapchat-advanced-srn-integration-setup#在-snap-平台上设置深度链接)。
2. 确认 AppsFlyer 中的<Anchor target="_blank" href="/marketers/zh/docs/app-settings#reengagement-attribution">再互动归因</Anchor>开关已开启。
3. 在应用的深度链接 URI scheme 中，**至少**添加以下参数：
   * **PID** — 此处的媒体渠道固定为**snapchat\_int**。这样一来，相关数据才会显示在 AppsFlyer 数据面板的**Snapchat\_int** 渠道下。
   * **C —** 对应的广告系列名称。
   * **is\_retargeting=true —** 该字段用于将广告系列标记为再营销广告系列。由于 URI 中带有该字段，现有用户与该广告系列的互动会被标记为再互动。从而确保相关用户数据出现在再营销数据面板中。

> 📘 **Note**
>
> **URI 示例**
>
> client://home?pid=snapchat\_int&amp;c=TEST&amp;is\_retargeting=true

<div id="set-up-deep-links-on-the-snap-platform" />

### 在 Snap 平台上设置深度链接

1. 进入**Drive traffic to app** 推广类型。
2. 添加深度链接 URI：  
     
   <Image align="center" alt="" src="https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png" />

<div id="deferred-deep-linking-with-snapchat" />

### 使用 Snapchat 延迟深度链接

AppsFlyer 提供多种延迟深度链接方案：

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">**UDL（统一深度链接）**</Anchor>：如果广告设置了深度链接，Snapchat 的点击数据中会带有 <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#deep_link_value">deep\_link\_value</Anchor> 字段，该字段受 UDL 方案支持。
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">**GCD（Get Conversions Data）API**</Anchor>：这是在 SDK 层面实时获取 Snapchat 用户转化数据的推荐方式。 GCD API 返回的数据中包含 <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_dp">`af_dp`</Anchor> 参数，该参数即为实际的深度链接目标（即用户在 App 内的跳转位置）。
* **使用转化数据参数：** 您也可以使用广告系列名称、广告组名称等其他字段（这些字段会作为 Snapchat 激活归因数据的一部分返回），自行编写逻辑，将用户引导到相应内容。

<div id="set-up-snapchat-for-agencies" />

## 为代理设置 Snapchat

代理可以代表广告主启用 Snapchat 对接，并开始为其推广活动获取归因数据。但在使用该对接时，代理存在一定限制。

<div id="agency-limitations" />

### 代理的限制

* 只有在广告主一方启用了 Snapchat 对接后，代理才能访问该对接。
* 代理对接页面中显示的归因参数继承自广告主的对接，且仅为**只读**状态。也就是说，代理可以看到广告主配置的归因回溯窗口，但无法自行修改。
* 对于归因后产生的事件，如果广告主授权，代理可以配置应用内事件回传。
* 即使获得授权，代理也无法开启 Advanced Privacy（见上文<strong>高级隐私（Advanced Privacy）</strong>部分）。

**设置代理侧的 Snapchat 对接：**

1. 在 AppsFlyer 中，前往**配置**下的**Partner Marketplace**。
2. 找到并选择**Snapchat**。
3. 输入代理的**Snapchat Account ID**。此 ID 用于识别代理流量，并将其与广告主流量区分开来。最多可输入 50 个不同的 Snapchat 账户 ID。此后这些账户产生的所有归因数据都会显示在代理的数据面板中。
4. 点击**保存对接**。

<Image align="center" alt="snapchat-agency-integration.png" src="https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png" />

> 🚧 **Important**
>
> 广告主和代理之间不应共享 Snapchat 账户 ID。如果共享了账户 ID，广告主一方的所有激活都会被自动归因到代理的数据面板中。

<div id="raw-data-restrictions" />

## 原始数据限制

* 自 2023 年 3 月 1 日起，原始数据报告不再包含 Snapchat 的卸载数据。
* 自 2023 年 9 月 12 日起，Snapchat 开始限制广告主在设备级别可见的浏览型归因数据。这会影响原始数据报告、Push API 消息、Pull API 报告、数据导出页面以及 Data Locker 等用户级别数据来源，仅填充以下字段：
  * Media source（即 snapchat\_int）
  * Channel
  * Attributed touch type（显示为 impression）
  * Attributed touch time（仅上报日期，格式为 dd/mm/yyyy）
  * 广告系列名称和 ID（自 2025 年 12 月 15 日起）
  * 广告组名称和 ID（自 2025 年 12 月 15 日起）
* 自 2026 年 10 月 6 日起，`snapchat_int` 的浏览型归因数据在部分情况下会在原始数据中受到限制。相关限制逻辑由 Snapchat 管理。

<div id="snapchat-data-retention" />

## Snapchat 数据保留期限

Snapchat 要求归因服务商在用户激活 App 满 12 个月后删除其设备级别数据。也就是说，这些用户在激活满 12 个月后产生的事件会被记为自然量。

历史汇总数据不受影响。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%BF%B0 01H8F1RWVPTHBDGF3830DY7G7M=%E6%A6%82%E8%BF%B0 setting-up-snapchat-integration=%E8%AE%BE%E7%BD%AE-snapchat-%E5%AF%B9%E6%8E%A5 01H7WQ47ECTZHPKMG5Z5ZPAND5=%E8%AE%BE%E7%BD%AE-snapchat-%E5%AF%B9%E6%8E%A5 activate-partner=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 01H7WQ47ECZB5GNCQ0XH68N1DK=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 general-settings=%E5%B8%B8%E8%A7%84%E8%AE%BE%E7%BD%AE 01H7WQ47ECQSQPP63H398NTQ6M=%E5%B8%B8%E8%A7%84%E8%AE%BE%E7%BD%AE h_01_advanced-privacy=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81advanced-privacy advanced-privacy=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81advanced-privacy h_01_advanced-matching-data-sharing=%E9%AB%98%E7%BA%A7%E5%8C%B9%E9%85%8D%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%ABadvanced-matching-data-sharing advanced-matching-data-sharing=%E9%AB%98%E7%BA%A7%E5%8C%B9%E9%85%8D%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%ABadvanced-matching-data-sharing install-attribution=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 01H8VVCC8GK8VFPBEPAMVHCAWM=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 reengagement-attribution=%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 01H8VVCC8HHG5290PYF0BT29QA=%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 ignore-active-users-for-retargeting=%E5%86%8D%E8%90%A5%E9%94%80%E6%97%B6%E5%BF%BD%E7%95%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7 h_01HNWSTJZPFQVQ5C8M0JA1J0T5=%E5%86%8D%E8%90%A5%E9%94%80%E6%97%B6%E5%BF%BD%E7%95%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7 inapp-event-postback-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H8VVCC8HHZRFQ2T1X478YZMP=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H7WQ47ED1HYEBHFJDHTB6HJH=cost-data-sync-status 01H7WQ47ED3P53B269W93Z341E=stop-snapchat-cost-sync web-to-app-measuring-app-activity-for-nonapp-campaigns=web-to-app%E8%A1%A1%E9%87%8F%E9%9D%9E-app-%E6%8E%A8%E5%B9%BF%E6%B4%BB%E5%8A%A8%E5%B8%A6%E6%9D%A5%E7%9A%84-app-%E5%86%85%E6%B4%BB%E5%8A%A8 h_01JJMAS0W9WMEPJCQWD9BXAEZ2=web-to-app%E8%A1%A1%E9%87%8F%E9%9D%9E-app-%E6%8E%A8%E5%B9%BF%E6%B4%BB%E5%8A%A8%E5%B8%A6%E6%9D%A5%E7%9A%84-app-%E5%86%85%E6%B4%BB%E5%8A%A8 deep-linking-with-snapchat=%E4%BD%BF%E7%94%A8-snapchat-%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 01H7WQ47EDC973V7CPE38QAQE7=%E4%BD%BF%E7%94%A8-snapchat-%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 how-to-set-up-deep-links-on-snap-platform=%E5%9C%A8-snap-%E5%B9%B3%E5%8F%B0%E4%B8%8A%E8%AE%BE%E7%BD%AE%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 01H7WQ47EDJAX2DW7A2JJ4XVJN=%E5%9C%A8-snap-%E5%B9%B3%E5%8F%B0%E4%B8%8A%E8%AE%BE%E7%BD%AE%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 deferred-deep-linking-with-snapchat=%E4%BD%BF%E7%94%A8-snapchat-%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 01H7WQ47EDS3MYRN9A9ZPHXG9Z=%E4%BD%BF%E7%94%A8-snapchat-%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 setting-up-snapchat-for-agencies=%E4%B8%BA%E4%BB%A3%E7%90%86%E8%AE%BE%E7%BD%AE-snapchat 01H7WQ47EDARK9SSP47V5MGX18=%E4%B8%BA%E4%BB%A3%E7%90%86%E8%AE%BE%E7%BD%AE-snapchat agency-limitations=%E4%BB%A3%E7%90%86%E7%9A%84%E9%99%90%E5%88%B6 h_01HHVGS94CB9XC0T63VFDZ18JS=%E4%BB%A3%E7%90%86%E7%9A%84%E9%99%90%E5%88%B6 raw-data-restrictions=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E9%99%90%E5%88%B6 h_01HA3XZPWSKVRX7VTRXT1WQ1EZ=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E9%99%90%E5%88%B6 keeping-snapchat-data=snapchat-%E6%95%B0%E6%8D%AE%E4%BF%9D%E7%95%99%E6%9C%9F%E9%99%90 01H7WQ47ED9STKS1CVW5EXYX0Z=snapchat-%E6%95%B0%E6%8D%AE%E4%BF%9D%E7%95%99%E6%9C%9F%E9%99%90" />

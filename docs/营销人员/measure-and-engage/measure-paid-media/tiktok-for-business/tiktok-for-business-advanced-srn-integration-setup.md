---
title: TikTok for Business高级SRN对接设置
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-06-09T16:49:57Z'
  edited_at: '2026-10-14T10:14:21Z'
  id: 6722785184913
  locale: zh-cn
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/zh-cn/articles/6722785184913
---
> **概要：** TikTok for Business（tiktokglobal\_int）是一个高级自归因平台（<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">SRN</Anchor>），能让广告主在AppsFlyer中根据用户点击和浏览数据进行移动端归因。这些流量包括TikTok应用和非移动端带来的应用激活。

<div id="note" />

> 📘 **注意**
>
> * 2023年1月30日，我们上线了新的**TikTok for Business高级SRN**对接`tiktokglobal_int`，**TikTok for Business的历史对接**`bytedanceglobal_int`将逐步下线，到2024年3月20日正式停用。此次变更的过渡事宜将由TikTok负责处理，他们会通知所有相关客户，引导其删除历史对接。<strong>为了避免出现数据丢失问题，请确保新对接和历史对接在过渡期间都处于启用状态。</strong>详情请见相关的<Anchor target="_blank" href="/marketers/zh/docs/bulletin-tiktok-for-business-advanced-srn">公告文档</Anchor>。
> * AppsFlyer可衡量TikTok[非应用广告系列](#网页到应用衡量非应用广告带来的应用流量)（non-app campaign)带来的应用流量。

<Image alt="TTFB_logo__4C_stacked_black_1.png" src="https://files.readme.io/f876dca1810a33266ad93de7822354d3a9aeb41a1e064a1f85f7120f713e699d-23689976309905.png" width="218px" />

<div id="overview" />

## 速览

高级SRN对接意味着所有包含广告ID的流量都会被归因并上报为常规SRN流量。在广告ID不可用的情况下，AppsFlyer会根据TikTok的点击和展示来衡量归因。

<div id="set-up-tiktok-for-business" />

## TikTok for Business对接设置说明

**前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer面板的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式**：从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索并选择**TikTok for Business**。
3. 点击**设置对接**，界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">（启用）</Anchor>状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

配置窗口包括以下选项卡：渠道对接、归因链接、成本、广告收入和授权。TikTok for Business对接页面中的**归因链接**选项卡不可用，其他选项卡为可选配置。

<div id="note-1" />

> 📘 **注意**
>
> * 部分设置区分iOS和安卓设备。
> * 设置广告系列名称时，不能以空格开头或结尾，否则会导致面板和报告的数据之间产生差异。详情请见<Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=9535">TikTok投放设置指南</Anchor>。
> * 使用<Anchor target="_blank" href="https://www.tiktok.com/business/en/blog/introducing-tiktok-search-ads-toggle">TikTok Search Ads Toggle</Anchor>投放的搜索广告也包含在总体的TikTok归因中。 AppsFlyer不接收具体搜索关键字词的数据。

<div id="integration-tab" />

<Accordion title="对接选项卡">

**对接**选项卡中包含多个板块，下文做了详细说明。

<div id="activate-partner" />

#### 启用渠道

在配置对接之前，必须先打开**启用该渠道**开关。有关<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation#渠道对接的启用方式">启用和停用合作伙伴</Anchor>的更多信息，请参阅对接。

<div id="advanced-matching-data-sharing" />

<div id="note-2" />

<div id="advanced-data-sharing" />

#### 高级隐私保护

仅适用于iOS应用：通过回传和<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">报告</Anchor>与共享渠道数据时，您对这些数据的控制范围取决于<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">**高级隐私模式**（用于iOS14.5+）</Anchor>的启用状态：

| 高级隐私保护：启用 | 高级隐私保护：停用 |
| --- | --- |
| 仅发送归因到该渠道的事件回传 | 根据您指定的配置发送回传：<ul><li>**所有媒体渠道，包括自然流量**</li><li>**仅该合作渠道**</li></ul> |
| 根据<Anchor target="_blank" href="/partners/zh/docs/advanced-privacy-guide-postback-macros-for-ad-networks">高级隐私模板</Anchor>发送回传 |  |
| <Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">汇总和匿名数据</Anchor>由客户提供给合作伙伴，这意味着不包含用户级数据（设备ID）。 |  |

> 📘 **注意**
>
> * 启用对接（`tiktokglobal_int`）时，**高级隐私保护**开关默认处于打开状态。
> * 从历史对接（`bytedanceglobal_int`）迁移到新对接（`tiktokglobal_int`）时**高级隐私保护**开关默认打开，与迁移前的启用状态无关。

<div id="note-3" />

<div id="general-settings" />

#### 通用设置

**TikTok App ID**

TikTok App ID是在TikTok Ads Manager（TikTok广告管理平台）中生成的专属代号，TikTok通过该代号来确认广告主对其应用的所有权。虽然TikTok App ID不是必填项，但仍建议您为所有应用都输入该ID。这有助于您更好地掌握您在TikTok for Business中的数据并解锁其他产品。

**应用ID的添加方式：**

1. 【可选】输入您的TikTok App ID（请在TikTok Ads后台查看）。
2. 【可选】如需添加多个应用ID：
   1. 输入第一个应用ID，然后按回车键。
   2. 输入下一个TikTok App ID。

> 📘 **注意**
>
> * 配置TikTok App ID不影响您在AppsFlyer中的数据。
> * 迁移到新对接（`tiktokglobal_int`）时，系统会自动使用历史对接（`bytedanceglobal_int`）中的值来填充对应字段。
> * <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001070">详情请见iOS 14中与TikTok App ID相关的注意事项。</Anchor>

<div id="note-4" />

<div id="default-postbacks" />

#### 默认回传

配置**激活**回传的发送方式。**被拦截的激活**和**再互动**仅回传到TikTok for Business。

* **仅该合作渠道**（默认）：仅回传归因到该渠道的事件，也就是说完成这些事件的用户来自该渠道。
* **所有媒体渠道，包括自然流量**：回传归因到任何渠道以及自然量的事件，也就是说完成这些事件的用户来自各个渠道。TikTok for Business建议将默认设置改为**所有媒体渠道，包括自然流量**，以便更有效地进行优化。

> 📘 **注意**
>
> * 仅适用于iOS应用：仅适用于iOS应用：通过回传和<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">报告</Anchor>与共享渠道数据时，您对这些数据的控制范围取决于**高级隐私模式（用于iOS14.5+）**[的启用状态](#高级隐私保护)：
> * 从历史对接（`bytedanceglobal_int`）迁移到新对接（`tiktokglobal_int`）时激活回传默认设置为**仅限该合作渠道**，不受迁移前的设置影响。

<div id="note-6" />

<div id="note-5" />

<div id="install-attribution" />

#### 激活归因

您可以为不同的广告交互类型设置不同的归因窗口，分别针对仅浏览广告、点击广告或与广告交互的用户所完成的新增激活（首次打开）进行归因。请注意，仅在相关回溯窗口内发生的激活才会被归因到TikTok for Business。

1. 设置**点击型激活回溯窗口**，可用的时长范围为1-23小时或1-30天。**注意：** TikTok for Business建议将点击回溯窗口设置为7天，与其平台上的窗口期对齐。

   > 📘 **注意**
   >
   > 对点击回溯窗口的设置也会应用于深度点击和深度浏览的回溯窗口。

2. 【可选】打开**浏览型激活归因**的开关并设置回溯窗口：
   * **浏览型激活回溯窗口**的可用时长范围为1-24小时。**请注意：** TikTok for Business建议将浏览型激活回溯窗口设置为1天，与其平台上的窗口期对齐。

> 📘 **注意**
>
> * TikTok for Business为了保护用户隐私，使用了高级数据隐私保护措施。从2021年10月23日起，TikTok for Business开始限制设备层级的浏览型归因数据对广告主的可见性。这会影响原始数据报告、Push API消息、Pull API报告、数据导出页面和Data Locker等用户级别的数据传输工具，其中填充的数据仅限以下字段：
> * * Media source（媒体渠道，显示为“bytedanceglobal\_int”）
>   * 渠道
>   * Attributed touch type（广告互动类型，显示为“impression”）
>   * Attributed touch time（广告互动时间，该字段仅上报日期，格式为“dd/mm/yyyy”）
>   * Campaign（广告系列，显示为“restricted”）
>     广告系列上报为“restricted”（受限）这表示该数据在GCD中不可用。汇总数据报告中仍会显示浏览型转化。
> * 从历史对接（`bytedanceglobal_int`）迁移到新对接（`tiktokglobal_int`）时，回溯窗口（点击型和浏览型）自动设为**默认值**，不受迁移前的设置影响。您后续可以更新这些设置。

<div id="note-7" />

<div id="reinstall-attribution" />

#### 重装激活归因

重装激活归因功能可帮助您衡量在再归因窗口期内重装激活应用的用户，并将其归因到符合条件的TikTok点击和展示。

该开关打开时，重装激活会被记录为TikTok广告系列中的新增转化，并与您现有的激活归因设置保持一致。有关重装激活的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls">衡量重装激活</Anchor>

* 如需启用重装激活归因，请在**对接**选项卡中打开**重装激活归因**开关。

> 📘 **注意**
>
> * 无需为重装激活设置单独的回溯窗口。重装激活归因的点击和浏览状态以及回溯窗口与您的激活归因设置相同。
> * 启用后，符合条件的重装激活回传会发送到TikTok。

<div id="warning" />

<div id="note-8" />

<div id="re-engagement-attribution" />

#### 再次互动归因

设置不同的归因窗口，以归因于浏览、点击或参与广告的现有用户的再次参与。请注意，仅在相关回溯窗口内发生的再互动才会被归因到TikTok for Business。

1. 设置**点击型激活回溯窗口**，可用的时长范围为1-23小时或1-30天。注意：**TikTok for Business建议将点击型再互动回溯窗口设置为7天，与其平台上的窗口期对齐。**

   > 📘 **注意**
   >
   > 对再互动点击回溯窗口的设置也会应用于再互动深度点击和深度浏览的回溯窗口。

2. 【可选】**再互动的浏览型归因**开关，并设置回溯窗口：
   * 设置**再互动的浏览回溯窗口**，可用的时长范围为1-24小时。**请注意：** TikTok for Business建议将再互动的浏览回溯窗口设置为1天，与其平台上的窗口期对齐。
3. 设置**再互动窗口**，可用的时长范围为1-23小时、1-90天或用户的整个**生命周期**。

> 🚧 **注意事项！**
>
> 从历史对接（`bytedanceglobal_int`）迁移到新对接（`tiktokglobal_int`）时**再互动**开关**默认关闭**，与迁移前的启用状态无关。如果您的历史对接中包含<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销广告</Anchor>，`为了确保过渡前后的连贯一致，请务必在新对接中打开再互动开关。`

进一步了解再互动归因的<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide#reengagement-rules-and-windows">规则和窗口期</Anchor>。

<div id="note-9" />

<div id="ignore-active-users-for-retargeting" />

#### 再营销广告中忽略活跃用户

打开这个开关并设置其窗口期后，AppsFlyer就会<Anchor target="_blank" href="/marketers/zh/docs/set-retargeting-inactivity-window#不活跃时长">忽略在此期间打开相关应用的用户所完成的再互动和再归因</Anchor>。也就是说，这些用户在该窗口期内的行为不会被记录到AppsFlyer中。

> 📘 **注意**
>
> 在此期间处于**沉睡**状态的用户所完成的再互动和再归因**会得到记录**。

1. 打开**在再营销广告中忽略活跃用户**的开关。
2. 设置不活跃窗口。

<div id="in-app-event-postbacks" />

#### 应用内事件回传

将回传中的应用内事件映射到TikTok for Business平台中的对应事件：

1. 打开**应用内事件回传**开关。
2. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。下表列出了必须配置的字段：

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。<br />**提示**：如果下拉菜单中没有您要查看的事件：<ul><li>请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。</li><li>在**AppsFlyer事件**中输入该事件的名称，然后点击**创建自定义事件**。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">自定义事件映射</Anchor>。</li></ul> |
| **渠道映射事件** | 渠道侧为每个事件定义的专属名称或ID。映射配置包括以下几种：<ul><li>**下拉菜单：** 选择最合适的预定义 TikTok 事件。</li><li>**按原样**：如果您从下拉菜单中选择自定义，AppsFlyer 将按原样发送事件，而不将其映射到任何 TikTok 预定义事件。请注意，TikTok 不使用自定义事件进行优化，而仅用于报告目的，而不是用于优化，因此 TikTok 不推荐此设置。要了解有关 TikTok 标准和自定义事件的更多信息，请参阅 TikTok 文档</li></ul> |
| **事件来源** | 选择事件回传的范围：<ul><li>**仅该合作渠道**（默认）：仅回传归因到该渠道的事件。</li><li>**所有媒体渠道，包括自然流量**：回传所有带量渠道的事件，以及自然量。 TikTok for Business建议广告主选择**所有媒体渠道，包括自然流量**，以便更有效地进行优化。</li></ul> |
| **回传内容** | <ul><li>**不发送值与收入**（默认）：仅发送事件本身，不带任何事件值。</li><li>**仅发送值**：发送**除**收入以外的所有参数。</li><li>**发送值与收入**：发送所有事件参数，**包括**收入（若有）。TikTok for Business建议广告主使用**值和收入**这一选项，这样他们才能提供更有效的投放优化服务。</li></ul> |

3. 【可选】点击**添加条件**<Image alt="onditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />图标，<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">设置事件的回传条件</Anchor>。
4. 点击**保存对接**。
5. 【可选】您可以在保存对接后留在配置页面，将其他应用也对接到该渠道：
   1. 点击页面左上角渠道名称下方的应用名称，打开应用列表。
   2. 在下拉菜单中选择一个其他应用。
   3. 为选定应用完成对接设置。

<div id="note-11" />

<div id="note-10" />

> 📘 **注意**
>
> * 仅适用于iOS应用：仅适用于iOS应用：通过回传和<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">报告</Anchor>与共享渠道数据时，您对这些数据的控制范围取决于**高级隐私模式（用于iOS14.5+）**[的启用状态](#高级隐私保护)：
> * 迁移到新对接（`tiktokglobal_int`）时，系统会自动使用历史对接（`bytedanceglobal_int`）中的设置来配置所有的回传事件。
>   * 如果某事件在TikTok for Business的历史对接中映射到**Pay**，则在迁移到新对接时该事件的名称会自动更改为**Purchase**。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

在<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">SRN</Anchor>和高级SRN对接中，归因链接不可用。

SRN依靠自己的平台完成归因，而高级SRN的归因则结合了广告平台的互动数据与AppsFlyer的数据，并根据您在[渠道对接选项卡](#integration-tab)中的归因设置得出归因结果。

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="成本选项卡（用于成本、点击和展示数据）">

该对接可针对成本、点击和展示提供广告系列、广告组、广告和国家/地区维度的汇总数据。详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">广告平台成本对接表</Anchor>，其中详细说明了适用维度、指标和功能。

**注意：** 对接中默认包含点击和展示数据，但您**需要购买**<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview?query=xpend">**ROI360**</Anchor>**产品**才能获取成本数据。

**请按以下步骤启用TikTok for Business的API对接，以获取成本、点击和展示数据**：

1. 进入**成本**选项卡，然后打开**获取成本数据**开关。
2. 点击**登入TikTok Ads**。
3. 界面会打开TikTok登录窗口，通过该窗口登入您的TikTok账户，并确认所需权限。
4. TikTok界面中显示操作成功的消息后，即可关闭该窗口。您的TikTok账户信息就会出现在**绑定账户**列表下。
5. 向下滚动到**广告主账户ID**部分 >**Advertiser ID**：输入TikTok广告主账户ID，然后点击**添加**。

   > 📘 **注意**
   >
   > * 请按以下方式从您的TikTok for Business账户中获取**广告主ID**：进入**Users** > **Members**，然后您就会在Advertiser account（广告主账户）部分下看到该ID信息。
   > * 请确保您添加的**广告主ID**是第2步中相关**TikTok账户**下的ID，因为AppsFlyer会从这个账户收集数据。
   > * 至少需要添加一个**广告主ID**，最多可以添加30个。

6. 点击**保存成本**。

<div id="for-roi360-subscribers" />

#### ROI360客户的专享配置

* 在`bytedanceglobal_int`历史对接和`tiktokglobal_int`新对接中都启用了Cost API的广告主和代理可能会看到重复的成本数据。如需避免此问题，请进入`bytedanceglobal_int`对接页面 > **成本选项卡**，然后关闭成本数据开关。  
  但启用新的成本对接时，新对接会自动收集过渡日前5天的成本数据。也就是说，新对接会重复显示这5天的成本数据。**举例来说**，假设您在1月15日停用了历史成本对接，并在同一天启用了新的成本对接，您就会在新对接中看到1月10日到14日之间的成本数据出现重复。
* 详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">广告平台成本对接表</Anchor>，其中详细说明了适用维度、指标和功能。
* 您可以在成本（及广告收入）对接状态面板或单独的广告平台面板中查看AppsFlyer最近一次拉取成本数据的时间以及<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">成本API状态</Anchor>。
* 进一步了解<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Cost API的启用方式</Anchor>。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

如需向TikTok发送广告收入数据，用于UA优化，请配置<Anchor target="_blank" href="/marketers/zh/docs/share-ad-revenue-data-with-partners">广告收入回传或UA信号</Anchor>（signal）。

要从 Pangle 获取广告收入数据，请使用 Pangle（广告收入）合作伙伴集成。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

您可以在这个板块中选择需要向TikTok for Business开放的数据权限，以便其提供各种功能。

请注意，即使相关对接已<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">停用</Anchor>，只要TikTok For Business对接中的广告平台权限开关处于打开状态，相关**权限就仍向TikTok For Business开放**。

进一步了解与<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">授权</Anchor>相关的信息。

</Accordion>

<div id="deep-linking-with-tiktok-for-business" />

## 在TikTok for Business中使用深度链接

<Anchor target="_blank" href="https://ads.tiktok.com/help/article/understanding-deeplinks-and-deferred-deeplinks?lang=en">TikTok支持在多种投放目标中使用深度链接和延迟深度链接</Anchor>。您可以在创建广告系列、广告组或广告时，在广告层级进行配置。您可以创建深度链接将用户引导到应用内的具体页面，这样您就能根据用户与TikTok广告的交互方式，有针对性地向其展示定制化内容。

<div id="access-tiktok-conversion-data-via-appsflyers-gcd-api-for-deep-linking" />

### 在深度链接场景中使用AppsFlyer的GCD API获取TikTok转化数据

AppsFlyer针对延迟深度链接提供多种解决方案：

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">**Unified Deep Linking (UDL)**</Anchor> TikTok点击中包含一个<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#deep_link_value">deep\_link\_value</Anchor>（深度链接）字段，UDL解决方案支持该字段。
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">**GCD（Get Conversions Data，获取转化数据）API**</Anchor>：这是用于实时获取TikTok用户转化数据的推荐方式，可直接从SDK层级抓取数据。GCD API返回的数据中包含参数，该参数用于传递实际的深度链接终点（即应用调起后用户进入的具体页面）。
* **转化数据参数的使用方式如下：** 您可以创建自定义逻辑，使用其他参数将相关用户引导到指定的页面，这些参数包括广告系列名称、广告组名称以及该API返回的TikTok激活归因数据中的其他字段。

<div id="web-to-app-measure-app-activity-for-non-app-campaigns" />

## 网页到应用衡量非应用广告带来的应用流量

AppsFlyer与TikTok的集成使得对应用活动的全面测量成为可能——例如安装、重新参与和应用内事件——这些都是归因于TikTok for Business的非应用活动。

例如，即使广告目标是网页着陆页，应用安装也可以被测量，从而能够测量Web到应用（W2A）用户旅程。   
  
通过在 TikTok 广告管理器中按照以下步骤操作，您可以有效地衡量来自 TikTok 非应用程序活动的应用程序活动，并获得有关用户行为的宝贵见解。您还可以查看 <Anchor target="_blank" href="https://ads.tiktok.com/help/article/how-to-measure-app-activity-for-non-app-promotion-campaigns?lang=en">TikTok 文档</Anchor>。

1. 前往 TikTok 广告活动页面，然后选择编辑广告。
2. 向下滚动到**Tracking**>**App events**，选择相关应用。
3. 点击**保存**。
4. 这些步骤适用于您活动中的所有相关广告。

<div id="set-up-tiktok-for-business-for-agencies" />

## 代理的TikTok for Business对接设置

帮助广告主代为投放的代理商可以启用TikTok for Business的对接，并对其投放的广告进行归因。但是代理商在使用该对接时有一定的局限性。

<div id="send-complex-in-app-events-to-tiktok" />

<div id="important" />

<div id="agency-limitations" />

### 代理限制

* 广告主侧必须先启用TikTok for Business，然后代理才能访问其对接。
* 从2024年1月1日开始，显示在代理对接页面上的归因参数是从广告主对接中以**仅查看**模式继承而来的。也就是说代理可以查看广告主配置的归因回溯窗口，但无法自行配置。
* 但代理无法启用高级隐私保护设置（即使获得许可） — 只有广告主可以设置该功能。
* 代理可以在<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#configure-inapp-event-postbacks::8743ba60">广告主授权</Anchor>后配置应用内事件回传。
* 映射应用内事件回传时，建议您确保您的代理和贵司营销人员所做的映射配置完全一致。

**代理的TikTok for Business对接设置方式如下：**

1. 从AppsFlyer后台菜单栏的**配置**下方点击进入**Partner Marketplace**平台，
2. 搜索并选择**TikTok for Business**。
3. 输入**TikTok App ID**。
4. 输入您代理的**TikTok账户ID**。这是为了识别代理流量，并将其与广告主的流量区分开来。
5. 点击**保存对接**。

   <Image alt="tiktok.png" src="https://files.readme.io/b13ee9cd005b97c37019154a0caa10e03b846e7405777d9fc0e3db11bfb233b4-33379202036369.png" width="60.92%" />

> ❗️ **重要提示**
>
> 广告主和代理之间切勿共享TikTok for Business账户ID，否则所有的广告主侧激活全部都会被自动记录到代理面板中。

<div id="smart-plus-campaigns-reporting" />

## Smart Plus广告系列报告

Smart Plus 是 TikTok 推出的一种新型广告系列，能让广告主在同一个广告单元中测试多个素材，通过自动化素材测试优化投放效果。

<Anchor target="_blank" href="https://ads.tiktok.com/help/article/about-smart-plus-campaign?lang=en">了解有关 Smart Plus 营销活动的更多信息</Anchor>

<div id="how-smart-plus-campaigns-are-structured" />

### Smart Plus 广告系列的结构

不同于标准的TikTok广告系列，智能增强广告系列包括三个级别（广告系列、广告组和广告），它增加了第四层——**创意**。

1. 广告系列
2. 广告组
3. Ad
4. 素材

<div id="note-12" />

<div id="how-smart-plus-data-is-reported-in-appsflyer" />

### 如何在AppsFlyer中报告Smart Plus数据

AppsFlyer将TikTok Smart Plus广告系列数据映射如下：

| TikTok级别 | 等同于AppsFlyer | 说明 |
| --- | --- | --- |
| 广告系列 | 广告系列 | 直接映射 |
| 广告组 | 广告组 | 直接映射 |
| Ad | — | 未在AppsFlyer中映射 |
| 素材 | Ad | 映射到AppsFlyer广告层级 |

> 📘 **注意**
>
> AppsFlyer的Smart Plus广告系列映射结构与TikTok Ads Manager不同。在TikTok Ads Manager中，报告仅显示到广告层级，没有专门的素材细分。但AppsFlyer会将TikTok的素材数据直接映射到广告层级。因此，在比较 AppsFlyer 和 TikTok 的投放数据时，您可能会看到数据差异。

## 问题排查

### 我的TikTok应用状态为“待验证”。

如果在AppsFlyer的应用级别或TikTok合作伙伴级别启用了汇总层级的高级隐私保护（AAP），则仅发送归因到广告平台的激活和应用内事件回传。因此，TikTok 可能无法从有机来源接收所需的回调，导致“待验证”状态。

#### 推荐的解决方案

1. 您可以暂时关闭AppsFlyer中的AAP设置，仅允许TikTok接收自然回传用于验证目的。（禁用 AAP 可以使用户级数据对广告商和合作伙伴可用。详情请见：AAP关闭时
   1. <span class="af-ol-a"></span>转到 <Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework#aap-central-switch">应用级设置</Anchor> 并禁用 AAP。
   2. 导航到 [TikTok 的合作伙伴集成配置](#高级隐私保护) 并在那里也禁用 AAP。
2. 在[回调部分](#默认回传)中，将回调方法设置为：所有媒体渠道，包括自然流量：
3. 等待TikTok至少接收一个安装或应用内事件回调。一旦收到，您的应用程序应在TikTok仪表板上自动更新为“已验证”。
4. 验证后，您可以根据您的隐私偏好[重新启用AAP设置](#高级隐私保护)。

> 📄 **相关文档**
>
> * 用于国内流量的<Anchor target="_blank" href="/marketers/zh/docs/bytedance-ads-china-campaign-configuration">ByteDance Ads（巨量引擎）</Anchor> （bytedance\_int）
> * <Anchor target="_blank" href="/marketers/zh/docs/skan-interoperation-with-tiktok-for-business">TikTok for Business与AppsFlyer的SKAN互通性</Anchor>

<div data-zendesk-anchors="01H8VVCC8GW5AZ3M475XFZY9JW=%E6%B3%A8%E6%84%8F overview=%E9%80%9F%E8%A7%88 01H8VVCC8G3ZXZJMHSMJ67GMG4=%E9%80%9F%E8%A7%88 setting-up-tiktok-for-business%C2%A0integration=tiktok-for-business%E5%AF%B9%E6%8E%A5%E8%AE%BE%E7%BD%AE%E8%AF%B4%E6%98%8E 01H8VVCC8GPY4SEFGK30Q1BJZ6=tiktok-for-business%E5%AF%B9%E6%8E%A5%E8%AE%BE%E7%BD%AE%E8%AF%B4%E6%98%8E 01H8VVCC8G6P25R0N5A7S3NGY7=%E6%B3%A8%E6%84%8F-1 01H8VVCC8GY6WTH0404RH2AR9F=integration-tab activate-partner::e4f2f638=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 01H8VVCC8G0KR4AA2HD9S8QBKD=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 advanced-privacy=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 01H8VVCC8G0Z6ZHC10KVY9CGGQ=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 01H8VVCC8GC57YTDWA9EB2VP87=%E6%B3%A8%E6%84%8F-2 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE 01H8VVCC8GSDPSNN0AJPVZPR8P=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE 01H8VVCC8G2JB115XW49HJQFHA=%E6%B3%A8%E6%84%8F-3 default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 01H8VVCC8GW677RN6R6CV35KGG=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 01H8VVCC8G6M8D3WQ2CM10ZNZX=%E6%B3%A8%E6%84%8F-10 install-attribution=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 01H8VVCC8GK8VFPBEPAMVHCAWM=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 01JE5ZMSXK5Q9KWKY8C6ZXEGD9=%E6%B3%A8%E6%84%8F-5 01H8VVCC8G3YFDZVV9X9709F9M=%E6%B3%A8%E6%84%8F-6 reinstall-attribution=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 h_01K6D37PG96P2MG99BETK25GYA=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 h_01K6D43X96RNY6H2RJEYW4KPCY=%E6%B3%A8%E6%84%8F-7 reengagement-attribution=%E5%86%8D%E6%AC%A1%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 01H8VVCC8HHG5290PYF0BT29QA=%E5%86%8D%E6%AC%A1%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 h_01JJM8MPX2HMWBZSSAAC4YCZ3Q=%E6%B3%A8%E6%84%8F-8 01H8VVDWH85M34K7Z75BAT7BQW=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 ignore-active-users-for-retargeting=%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E4%B8%AD%E5%BF%BD%E7%95%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7 h_01HNWSTJZPFQVQ5C8M0JA1J0T5=%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E4%B8%AD%E5%BF%BD%E7%95%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7 h_01HMXNJVHK9C3FT8E04RE0TH99=%E6%B3%A8%E6%84%8F-9 inapp-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H8VVCC8HHZRFQ2T1X478YZMP=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H8VVCC8HDMTY1P2SG31HD61K=%E6%B3%A8%E6%84%8F-10 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions 01H8VVCC8HFJF62TC7DNXRH22A=%E6%B3%A8%E6%84%8F-11 for-xpend-subscribers=roi360%E5%AE%A2%E6%88%B7%E7%9A%84%E4%B8%93%E4%BA%AB%E9%85%8D%E7%BD%AE 01H8VVCC8HWDC9A03FRY5BC87Y=roi360%E5%AE%A2%E6%88%B7%E7%9A%84%E4%B8%93%E4%BA%AB%E9%85%8D%E7%BD%AE 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab 01H8VVCC8HAG0XVWE2T9PRDHTK=permissions-tab deep-linking-with-tiktok-for-business=%E5%9C%A8tiktok-for-business%E4%B8%AD%E4%BD%BF%E7%94%A8%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01JJM8MPX2X37WVR86S7786S06=%E5%9C%A8tiktok-for-business%E4%B8%AD%E4%BD%BF%E7%94%A8%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 accessing-tiktok-conversion-data-via-appsflyers-gcd-api-for-deep-linking=%E5%9C%A8%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%9C%BA%E6%99%AF%E4%B8%AD%E4%BD%BF%E7%94%A8appsflyer%E7%9A%84gcd-api%E8%8E%B7%E5%8F%96tiktok%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE h_01HVQR1TC5WVRDS24R9ZKD2HW2=%E5%9C%A8%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%9C%BA%E6%99%AF%E4%B8%AD%E4%BD%BF%E7%94%A8appsflyer%E7%9A%84gcd-api%E8%8E%B7%E5%8F%96tiktok%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE measuring-app-activity-for-nonapp-campaigns=%E7%BD%91%E9%A1%B5%E5%88%B0%E5%BA%94%E7%94%A8%E8%A1%A1%E9%87%8F%E9%9D%9E%E5%BA%94%E7%94%A8%E5%B9%BF%E5%91%8A%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%BA%94%E7%94%A8%E6%B5%81%E9%87%8F h_01J7MYAMBQ8M0JN005FSXQDZNS=%E7%BD%91%E9%A1%B5%E5%88%B0%E5%BA%94%E7%94%A8%E8%A1%A1%E9%87%8F%E9%9D%9E%E5%BA%94%E7%94%A8%E5%B9%BF%E5%91%8A%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%BA%94%E7%94%A8%E6%B5%81%E9%87%8F setting-up-tiktok-for-business-for-agencies=%E4%BB%A3%E7%90%86%E7%9A%84tiktok-for-business%E5%AF%B9%E6%8E%A5%E8%AE%BE%E7%BD%AE 01H8VVCC8HVNNQ9PJS4ZQCVDNS=%E4%BB%A3%E7%90%86%E7%9A%84tiktok-for-business%E5%AF%B9%E6%8E%A5%E8%AE%BE%E7%BD%AE agency-limitations=%E4%BB%A3%E7%90%86%E9%99%90%E5%88%B6 h_01HHVGS94CB9XC0T63VFDZ18JS=%E4%BB%A3%E7%90%86%E9%99%90%E5%88%B6 01H8VVCC8HWJ2WQ83E0CZMEHH1=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA smart-campaigns=smart-plus%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E6%8A%A5%E5%91%8A smart-plus-campaigns-reporting=smart-plus%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E6%8A%A5%E5%91%8A h_01K9AGYS6XCDS3193ZAK7Z208F=smart-plus%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E6%8A%A5%E5%91%8A how-smart-plus-campaigns-are-structured=smart-plus-%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E7%9A%84%E7%BB%93%E6%9E%84 h_01K9AGYS6XSXJ9DD6XYDHVYMYK=smart-plus-%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E7%9A%84%E7%BB%93%E6%9E%84 how-smart-plus-data-is-reported-in-appsflyer=%E5%A6%82%E4%BD%95%E5%9C%A8appsflyer%E4%B8%AD%E6%8A%A5%E5%91%8Asmart-plus%E6%95%B0%E6%8D%AE h_01K9AGYS6XYT763ST1H1T4SXT8=%E5%A6%82%E4%BD%95%E5%9C%A8appsflyer%E4%B8%AD%E6%8A%A5%E5%91%8Asmart-plus%E6%95%B0%E6%8D%AE h_01K9AGYS6X12RC8245TY1RGVNX=%E6%B3%A8%E6%84%8F-12 troubleshooting=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 h_01JQBGSDV84TBJGXGBSFWN6C4D=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 my-app-status-on-tiktok-is-%E2%80%98pending-verification%E2%80%99=%E6%88%91%E7%9A%84tiktok%E5%BA%94%E7%94%A8%E7%8A%B6%E6%80%81%E4%B8%BA%E5%BE%85%E9%AA%8C%E8%AF%81 h_01JQBGSKBY6C3289G3NY3WN74K=%E6%88%91%E7%9A%84tiktok%E5%BA%94%E7%94%A8%E7%8A%B6%E6%80%81%E4%B8%BA%E5%BE%85%E9%AA%8C%E8%AF%81 recommended-resolution=%E6%8E%A8%E8%8D%90%E7%9A%84%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88 h_01JQBGWA8ASV6MBA5FKGD56DKZ=%E6%8E%A8%E8%8D%90%E7%9A%84%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88 h_01HE7RY8K7HV2CTZ2S537YRCNQ=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

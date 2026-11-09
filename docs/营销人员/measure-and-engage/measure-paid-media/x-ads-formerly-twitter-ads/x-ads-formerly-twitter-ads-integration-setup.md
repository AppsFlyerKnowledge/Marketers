---
title: X Ads（原Twitter广告）对接设置
metadata:
  keywords:
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
  created_at: '2021-11-09T09:33:40Z'
  edited_at: '2026-10-14T10:02:01Z'
  id: 4410472471825
  locale: zh-cn
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410472471825
---
> **概要：** 本文介绍了如何将X Ads账户与AppsFlyer进行对接，以便在AppsFlyer面板中查看X Ads的归因数据。

<div id="overview" />

## 概览

X Ads是一个高级自归因平台（SRN），AppsFlyer可通过该平台对所有用户的转化事件进行归因，包括缺少广告标识符（ID）的用户。

<div id="x-ads-attribution-flow-in-appsflyer" />

### X-Ads归因流程在AppsFlyer中

**X Ads的归因流程如下：**

1. AppsFlyer通过S2S对接从X Ads接收所有广告交互数据，并按照以下方式进行归因：
   * 如果激活事件和交互事件中都包含移动广告主ID（MAID），AppsFlyer会使用确定性ID匹配进行归因。
   * 如果激活事件或交互事件中缺少MAID，AppsFlyer则会使用概率归因模型（PMOD）进行归因。
2. 无论激活是否被归因为X Ads，AppsFlyer都会通过对接将所有激活回传给X Ads。
3. 当用户拒绝App Tracking Transparency（ATT）授权且高级隐私（AP）处于启用状态时，发送给X Ads的回传中某些字段将受到限制。受限字段包括：

   * X Ads交互ID
   * 哈希设备ID
   * IP address（IP地址）
   * User Agent（用户代理）

   <Image align="center" alt="_- visual selection.png" src="https://files.readme.io/8c17755d275e732f88cf93e8e7e33df891911dd640d2dbfc2637313a9d59d43e-small-36433399199249.png" />

<div id="connecting-your-x-ads-account-to-appsflyer" />

## 将X Ads账户对接到AppsFlyer

<div id="h_01HDJVBAEZATGM580CNC7BCVTN" />

<div id="note" />

> 📘 **注意事项**
>
> 在开始之前，请请确保您已在X Ads账户中<Anchor target="_blank" href="https://business.X%20Ads.com/en/help/account-setup/billing-basics.html">添加支付方式</Anchor>，否则无法在AppsFlyer后台激活渠道对接。

1. 在<Anchor target="_blank" href="https://business.x.com/en/advertising">X Ads</Anchor>中登陆X Ads 账户。  
   如果界面没有自动跳转到Ads页面，请点击屏幕左上角的Ads按钮。
2. 当界面提示您选择**Simple (NEW)**（简易）或**Advanced**（高级）投放选项时，请选择**Advanced**。
3. **在Campaign objective（投放目标）下选择App Installs（应用激活）或App re-engagements（应用再互动），然后点击Next（下一步）。**

   <Image align="center" alt="X-Ads-campaign-objective.png" src="https://files.readme.io/44e5aca3895fc5aefa22f91542b9c23f9798b246ac8086e97a3994244fc2c5a8-36433415100561.png" />
4. 选择您的应用，然后点击<strong>mobile measurement partner（移动衡量合作伙伴）</strong>链接。
5. 在<strong>Conversion tracking（转化跟踪）</strong>页中点击**Go to AppsFlyer（前往AppsFlyer）**。

   <Image align="center" alt="X-Ads-mmp-selection.png" src="https://files.readme.io/718bc93d2fcf606a8c165aed70364659ba23b74891b22775c5522ee9e4c7901a-36433422307345.png" />
6. 界面会提示您即将离开X Ads并进入AppsFlyer网站。点击**Go to AppsFlyer**并登录到您的面板。
7. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
8. 搜索并选择**X Ads**。
9. 在**对接**选项卡中，接受X Ads的移动应用转化记录（MACT）条款与条件，然后点击**保存对接**。
10. 打开**启用该渠道**开关，然后点击**通过X Ads登录**。
11. 点击**Authorize app**（授权应用），授权AppsFlyer使用您的X Ads账户。
12. 再次打开**启用该渠道**开关，界面会显示**对接**选项卡的设置，然后启用归因。  
    **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开（即启用）状态。详情请见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">渠道激活</Anchor>。
13. 选择您的X Ads账户将其激活，然后点击**保存并关闭**。

<div id="x-ads-attribution-setup" />

## X Ads归因设置

请点击<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">此处</Anchor>查看渠道配置页的标头（Header）示例。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

下文说明了**对接选项卡**中所包含的各个部分。您必须先<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">激活渠道</Anchor>才能看到该渠道对接选项卡中的具体内容。

<div id="ad-account-connected" />

### 广告账户已连接

请选择要启用归因的账户。

<Image align="center" alt="X-Ads_msc_new_4.png" src="https://files.readme.io/8b8ecdfd79bc87d4a65766ce67e48a06524d825e04d5e642eb5e9741069a2f6c-36433422308241.png" />

**请注意：** 您可以在AppsFlyer中连接最多200个广告账户。为了避免达到此限制并确保所有活跃账户的持续归因，我们建议删除任何不再使用的广告账户。

<div id="advanced-privacy" />

### 高级隐私保护

仅适用于iOS应用：**高级隐私(AP)** 开关允许您控制通过回传与X Ads共享的用户数据等级。此设置符合iOS 14.5及以上版本的隐私要求。  
当高级隐私开关开启时：

* 将基于
* X Ads提供的高级隐私模板<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">发送回传。仅共享</Anchor><Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">汇总和匿名</Anchor>数据；不包含任何设备级标识符。

<div id="note-1" />

> 📘 **注意**
>
> * 启用X Ads对接时，高级隐私保护开关**默认**处于打开状态。
> * 根据X Ads的说明，保持高级隐私**开启**状态可能会导致活动事件的回传量

<div id="click-through-attribution" />

### 偏低<strong>，从而限制在X Ads平台上的效果优化能力。点击型归因</strong>

您可以使用滑块来设置**点击型回溯窗口期**，只有发生在归因窗口期内的安装（首次启动）才有可能会被归因给Twitter。

您可以将这个值自定义为1-23小时或1-30天。建议您将点击型回溯窗口设置为14天，与X Ads的归因窗口保持一致。

<Image align="center" alt="X-Ads_msc_new_6.png" src="https://files.readme.io/359f6145751f45d38c151572f1ba0c525d232d16ffaee6b68453da0bc1826a69-36433422308369.png" />

<div id="view-through-attribution-lookback-window" />

### 浏览型归因窗口

您可以使用滑块来设置**浏览型回溯窗口期**，在广告展示之后，在没有其他相关点击的情况下，只有发生在归因窗口期内的激活（首次启动）才有可能会被归因给X Ads。

您可以将这个值自定义为1-23小时或1-7天。 建议将浏览型回溯窗口设置为1天，与X Ads的归因窗口保持一致。

<Image align="center" alt="X-Ads_msc_new_7.png" src="https://files.readme.io/15c9d815b05c03dfdf8578ed5af297c411991ab74accc5539fc1dbca178c3336-36433422308497.png" />

<div id="reinstall-settings" />

### 重装激活设置

打开**重装激活归因**开关，以启用重装激活归因。

重装激活归因的回溯窗口期沿用激活归因中的设置，因此这里无需再配置。

<div id="re-engagement-settings" />

### 再互动设置

对于X Ads上的再营销活动，AppsFlyer仅支持<strong>再互动（Re-engagement）</strong>表现衡量。再互动指的是用户在互动发生时已激活应用，并通过再营销广告再次产生互动。

<div id="important" />

> 🚧 **重要提示！**
>
> 请确保您已在应用设置页面启用了再营销功能。如需了解详情，请点击<Anchor target="_blank" href="/marketers/zh/docs/app-settings#reengagement-attribution">此处</Anchor>。

X Ads的再营销归因仅支持再互动转化。

如需对X Ads启用再互动归因，请在对接选项卡中打开**再互动归因**开关。

<div id="re-engagement-click-through-lookback-window" />

#### 点击型再互动回溯窗口

请设置**点击型再互动回溯窗口**，界定用户从点击广告到再互动转化之间的最长时限，仅在该窗口期中发生的再互动转化才会被归因到相关的再营销广告。您可以在1-23小时或1-30天的范围内自行调整该窗口期。

<Image align="center" alt="X-Ads-reengagement-activate.png" src="https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png" />

<div id="re-engagement-view-through-lookback-window" />

#### 浏览型再互动回溯窗口

如需启用再营销广告的展示归因，请打开**浏览型再互动归因**开关。

请设置**浏览型再互动回溯窗口**，界定用户从浏览广告到再互动转化之间的最长时限，仅在该窗口期中发生的再互动转化才会被归因到相关的再营销广告。您可以在1-23小时或1-7天的范围内自行调整该窗口期。

<Image align="center" alt="X-Ads-reengagement-view-through.png" src="https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png" />

<div id="re-engagement-window" />

#### 再互动窗口期

请设置**再互动窗口期**。仅在该窗口期内发生的应用内事件才会被归因到相关的再营销渠道。这个值可以设置为数天（1-90天）、数小时（至多23小时）甚至是终生：

<Image align="center" alt="X-Ads-reengagement-window.png" src="https://files.readme.io/5bc42bd967929a88fd38f8bdd9cc36046a6f0381d1883ab1f26f5c680185a74c-36433415113105.png" width="628px" />

<div id="ignore-active-users-for-retargeting" />

#### 再营销广告中忽略活跃用户

设置不活跃窗口期后，可忽略在此期间的活跃用户，避免将其行为记录为再营销转化。详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-retargeting-inactivity-window">再营销中的不活跃窗口</Anchor>说明。

<div id="in-app-event-postback-settings" />

### 应用内事件回传设置

这部分选项用于设置AppsFlyer事件与渠道之间的映射与回传。

<Image align="center" alt="In-app_event_postbacks_en-us.png" src="https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png" />

**请按以下步骤配置应用内事件回传：**

1. 设置**渠道ID** （如有需要）。
2. 启用**应用内事件回传**。
3. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。
4. 根据下表配置必要参数。  

| 参数 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。<br />**提示**：如果下拉菜单中没有您要查看的事件：<ul><li>请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。</li><li>在**AppsFlyer事件**中输入该事件的名称，然后点击**创建自定义事件**。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">自定义事件映射</Anchor>。</li></ul> |
| **渠道映射事件** | 渠道侧为每个事件定义的专属名称或ID。从下拉菜单中选择最贴合您业务需求的AppsFlyer预定义事件。 |
| **事件来源** | 选择事件回传的范围：<br /><br /><br /><br />**注意事项**<br />为了确保X Ads能接收到归因给代理的回传，您必须选择**所有媒体渠道，包括自然流量**。否则X Ads无法接收到这些回传。<ul><li>**仅该合作渠道**：仅回传归因到该渠道的事件。</li><li>**所有媒体渠道，包括自然流量**：回传归因到任何渠道以及自然量的事件。</li></ul> |
| **回传内容** | <ul><li>**无数据（默认）**：仅发送事件本身，不带事件值</li><li>**值和收入** ：发送所有事件参数，**包括**收入（若有）。</li><li>**仅发送值：** 发送**除**收入以外的所有参数。</li></ul> |

5. 【可选】点击<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />设置应用内事件的发送条件。  
   详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">带有条件设置的应用内事件回传</Anchor>。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

X Ads不使用归因链接进行归因。

<div id="note-2" />

> 📘 **注意**
>
> 该选项卡对<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">自归因平台</Anchor>（即SRN，包括Meta ads、Apple Search Ads、Adwords、X ads等）不可用，因为SRN不使用外部归因链接。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

成本对接可提供下列汇总数据：

* 广告系列、广告组、广告、流量入口和国家/地区维度的成本数据。详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">广告平台成本对接表</Anchor>，其中详细说明了适用维度、指标和功能。  
  **请注意：** 您需要购买<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>才能获得成本数据。
* 点击、展示数据以及扩充数据（关键词、广告系列名称以及广告组）。

**Cost API的启用方式如下**：

* 请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">对接指南</Anchor>进行操作。

您可以在成本（及广告收入）对接状态面板或单独的广告平台面板中查看AppsFlyer最近一次拉取成本数据的时间以及<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">成本API状态</Anchor>。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

X Ads的对接不支持广告收入数据。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

在此选项卡中, 您可以为X Ads开放各类权限, 无论是将该合作伙伴设为广告平台、代理, 还是广告平台兼代理。请注意，即使禁用X Ads的归因，授权选项卡仍处于有效状态，仍然可以对X Ads进行授权。

您可以使用权限开关向广告平台授权，让其处理与自己相关的配置：

<div id="ad-network-permissions" />

### 广告平台权限

* **允许配置对接**——允许该渠道设置对接选项卡（应用内事件回传除外）
* **允许配置应用内事件回传**——允许该渠道在对接选项卡中设置应用内事件回传，将事件映射到其平台。
* **允许访问留存报告**——仅限该渠道的留存数据
* **允许访问汇总忠实用户数据**——仅限该渠道的忠实用户数据
* **允许访问汇总应用内事件数据**——仅限该渠道的应用内事件数据
* **允许访问汇总收入数据**——仅限归因给该渠道的收入数据
* **允许访问Protect360面板**——仅访问该渠道的Protect360数据（需广告主事先开通该功能）

详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">广告平台权限</Anchor>。

<div id="agency-permissions" />

### 代理权限

详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#代理权限">代理授权指南</Anchor>。

</Accordion>

<div id="x-ads-features" />

## X-Ads功能

<div id="mobile-app-promotion-on-x-ads" />

<Accordion title="在X Ads上推广移动应用">

X Ads移动应用推广是一种在X Ads上推广应用的方法。该产品能让广告主使用优质的卡片式设计素材来推广他们的移动应用，从而提升新增激活、应用互动以及深度链接转化。用户可以直接从Twitter的时间线（Timeline）中下载并使用广告主推广的应用，操作十分便捷。

</Accordion>

<div id="webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only" />

<Accordion title="网页到应用测量非应用活动的应用活动（仅限Android）">

AppsFlyer与X Ads的集成使得可以测量应用活动——包括安装、重新参与和应用内事件——对于**非应用活动**在Android上。

例如，即使广告目标是**网页着陆页**，应用安装和其他安装后的活动仍然可以被测量，从而使得Web到应用（W2A）用户旅程的测量成为可能。

要测量来自X非应用活动的应用活动并获得有关用户行为的有价值见解，请在X Ads管理器中按照以下步骤操作：

1. 前往X Ads管理器中的活动创建表单。
2. 在<strong>交付</strong>部分，开启<strong>应用转化</strong>测量，以启用跟踪由该活动产生的安装和应用内转化。在<Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">X Ads文档</Anchor>中查看更多详细信息（在<em>"测量非应用目标上的应用转化"</em>下）。

<div id="important-1" />

> 🚧 **重要提示！**
>
> 此功能目前**仅在Android上受支持**。

</Accordion>

<div id="twitter-ads-and-appsflyer-skan-interoperation" />

<Accordion title="Twitter Ads与AppsFlyer之间的SKAN互通性">

Twitter Ads会通过一个专用的API发送SKAN回传数据。您可以在<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN面板</Anchor>中查看来自Twitter Ads的SKAN数据。

Twitter Ads会在SKAN回传中添加以下字段：

* Campaign name
* 广告系列 ID
* 即广告组的名称
* Adset ID

</Accordion>

<div id="twitter-user-privacy" />

<Accordion title="X Ads用户隐私">

X Ads广告主和用户可以控制他们如何与广告主和商业伙伴共享信息：

* 从**2021年7月31日&lt;1>开始，未注册X Ads高级移动测量（AMM）程序的广告主将不再收到X Ads MACT用户级数据。因此，**所有X Ads数据将在AppsFlyer的原始数据工具中受到限制**。<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions#x-ads-formerly-twitter">了解有关X Ads数据限制的更多信息。</Anchor>**
* 如果广告主在AMM程序中，并且用户已确认隐私通知，**将不适用原始数据限制**。
* 无论AMM状态如何，如果用户在欧盟并同意与商业伙伴共享数据，**将不适用原始数据限制**。
* 如果用户在欧盟并且**未**同意与商业伙伴共享数据，**将适用原始数据限制**。
* AppsFlyer中的汇总归因数据不受Twitter政策的影响，因此会显示准确的归因数据。

通过AMM计划，广告主可以通过授予X Ads进行审计的权利来获得更完整的用户级数据。此审计确保X Ads数据仅用于测量目的，符合行业标准和数据保护法律。

<Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">在常见问题部分了解更多关于AMM计划的信息</Anchor>。有关详细指导，请联系您的X Ads客户经理。

</Accordion>

<div id="advanced-srn-parameter-names" />

## 高级SRN参数名称

在X Ads的高级SRN集成中，以下字段**替换**其在AppsFlyer仪表板、汇总报告和事件级原始数据中的旧版对应项。

| **AppsFlyer**  <br />**数据列** | **历史SRN对接** | 高级SRN对接 |
| --- | --- | --- |
| **PID** | Twitter | Twitter |
| **广告活动名称** | 广告活动名称 | Campaign name |
| **广告系列 ID** | 广告系列 ID  <br />(base36: different X's dashboard, e.g. 21I3V9) | 广告系列 ID  <br />(base10: same as X's dashboard, e.g. 123456789) |
| **广告组名称** | Line Item ID  <br />(base36: different X's dashboard, e.g. 21I3V9) | Line Item Name |
| **Adset ID** | Line Item ID  <br />(base36: different X's dashboard, e.g. 21I3V9) | Line Item ID  <br />(base10: same as X's dashboard, e.g. 123456789) |
| **Ad Name** | Tweet ID | Ad Name  <br />（如可用） |
| **Ad ID** | Tweet ID | Tweet ID |
| **匹配类型** | srn | 如: id\_matching、probabilistic |

<div id="traits-and-limitations" />

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 不支持前滚归因 | Twitter Ads不支持前贴片广告的MMP归因。 |
| 广告名称 "未命名" | 广告名称在X（前身为Twitter）广告数据模型中不是强制字段，因此可能会缺失。当广告名称在X Ads管理器中未定义时，AppsFlyer将其显示为 **'未命名。'** |
| 成本 | X Ads中，如果投放的广告系列只有SKAN激活而没有常规激活，则其成本数据对代理不可用。成本对接必须由广告主设置，且相关数据仅限广告主可以查看。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01JV7CGQNZNEM3P98K6KSYKB0D=%E6%A6%82%E8%A7%88 xads-attribution-flow-in-appsflyer=x-ads%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B%E5%9C%A8appsflyer%E4%B8%AD h_01JZG83EKX39SF8355EW62C462=x-ads%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B%E5%9C%A8appsflyer%E4%B8%AD connecting-your-X-Ads-ads-account-to-appsflyer=%E5%B0%86x-ads%E8%B4%A6%E6%88%B7%E5%AF%B9%E6%8E%A5%E5%88%B0appsflyer h_01HDJVCRYQESA17XZ83GS81YZ3=%E5%B0%86x-ads%E8%B4%A6%E6%88%B7%E5%AF%B9%E6%8E%A5%E5%88%B0appsflyer h_01JV7D6AWYQ981HY6C130B021B=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 X-Ads-ads-attribution-setup=x-ads%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE h_01HDJVBAEZ5W3JH1BN7WXJ08P6=x-ads%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab ad-account-connected=%E5%B9%BF%E5%91%8A%E8%B4%A6%E6%88%B7%E5%B7%B2%E8%BF%9E%E6%8E%A5 h_01HDJVBAEZD89BSGHQTPR84HSC=%E5%B9%BF%E5%91%8A%E8%B4%A6%E6%88%B7%E5%B7%B2%E8%BF%9E%E6%8E%A5 xads_advanced_privacy_toggle=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 advanced-privacy=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 h_01JV7HVQJ2GTP74G6JYB300E71=%E6%B3%A8%E6%84%8F clickthrough-attribution=%E5%81%8F%E4%BD%8E%E4%BB%8E%E8%80%8C%E9%99%90%E5%88%B6%E5%9C%A8x-ads%E5%B9%B3%E5%8F%B0%E4%B8%8A%E7%9A%84%E6%95%88%E6%9E%9C%E4%BC%98%E5%8C%96%E8%83%BD%E5%8A%9B%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01HDJVBAEZFJWQ6FD4Q4GSPD76=%E5%81%8F%E4%BD%8E%E4%BB%8E%E8%80%8C%E9%99%90%E5%88%B6%E5%9C%A8x-ads%E5%B9%B3%E5%8F%B0%E4%B8%8A%E7%9A%84%E6%95%88%E6%9E%9C%E4%BC%98%E5%8C%96%E8%83%BD%E5%8A%9B%E7%82%B9%E5%87%BB%E5%9E%8B%E5%BD%92%E5%9B%A0 viewthrough-attribution-lookback-window=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3 h_01HDJVBAEZ2H91WBHNSMRQYQ7H=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3 reinstall-settings=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E8%AE%BE%E7%BD%AE h_01HDJVBAF0XRWRZJQSS4STH7YN=%E9%87%8D%E8%A3%85%E6%BF%80%E6%B4%BB%E8%AE%BE%E7%BD%AE reengagement-settings=%E5%86%8D%E4%BA%92%E5%8A%A8%E8%AE%BE%E7%BD%AE h_01HDJVBAEZZR1W06YH4XJSBKHV=%E5%86%8D%E4%BA%92%E5%8A%A8%E8%AE%BE%E7%BD%AE h_01JV9YQ7ZHRDD2NA5ENQXJQ31V=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA reengagement-clickthrough-lookback-window=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%86%8D%E4%BA%92%E5%8A%A8%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01HDJVBAEZ59ERYD2WQQYK6T37=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%86%8D%E4%BA%92%E5%8A%A8%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 reengagement-viewthrough-lookback-window=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%86%8D%E4%BA%92%E5%8A%A8%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01HDJVBAEZSCK7430NJ8AMQYVY=%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%86%8D%E4%BA%92%E5%8A%A8%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 reengagement-window=%E5%86%8D%E4%BA%92%E5%8A%A8%E7%AA%97%E5%8F%A3%E6%9C%9F h_01HDJVBAEZCMWY5X47FEEFXTBX=%E5%86%8D%E4%BA%92%E5%8A%A8%E7%AA%97%E5%8F%A3%E6%9C%9F ignore-active-users=%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E4%B8%AD%E5%BF%BD%E7%95%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7 h_01JVC3PWDR9KHEFBQF5NWHCQJN=%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E4%B8%AD%E5%BF%BD%E7%95%A5%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7 inapp-event-postback-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0%E8%AE%BE%E7%BD%AE h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0%E8%AE%BE%E7%BD%AE h_01HDJVBAEZATGM580CNC7BCVTN=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=%E6%B3%A8%E6%84%8F-1 h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab ad-network-permissions=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90 h_01HDJVBAF0BMSCKF6J9NJ019YJ=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90 agency-permissions=%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90 h_01HDJVBAF0W3ZE7J93CRE8EBRP=%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90 x-ad-features=x-ads%E5%8A%9F%E8%83%BD h_01JZWQA6DXRZ17SRVT4HM2MQSH=x-ads%E5%8A%9F%E8%83%BD h_01JZWQA6DX3BRNG8B5CJGA57AM=mobile-app-promotion-on-x-ads h_01JZWQA6DX7W9102P5S6KWJ1WB=webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only h_01JZWQA6DX8AX5XG3W4A6XB53S=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 h_01H9QR6TH74PKBGM5RC4M118GE=twitter-ads-and-appsflyer-skan-interoperation h_01H9QR6TH74R50K00H7FYN61KC=twitter-user-privacy x-ads-data-differences=%E9%AB%98%E7%BA%A7srn%E5%8F%82%E6%95%B0%E5%90%8D%E7%A7%B0 advanced-srn-parameter-names=%E9%AB%98%E7%BA%A7srn%E5%8F%82%E6%95%B0%E5%90%8D%E7%A7%B0 traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01JYGPBHHNQARG3GRMQJA95JKD=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />

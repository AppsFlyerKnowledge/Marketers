---
title: ironSource投放配置
metadata:
  keywords:
    - Supersonic
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-06T10:47:23Z'
  edited_at: '2026-10-14T10:07:10Z'
  id: 208005096
  locale: zh-cn
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/zh-cn/articles/208005096
---
> **概要**：ironSource是AppsFlyer的对接渠道之一，该平台所提供的各种工具可帮助应用开发人员、设备生产商、移动运营商和广告主开展变现、促活、分析和拓展工作。除了点击型移动归因外，ironSource还支持成本、广告收入、再营销和浏览型归因，您可以通过AppsFlyer记录相关的数据。

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ironsource.png?v=1" width="213px" />

> 📘 **注意事项**
>
> 由于ironSource支持所有类型的激活归因，因此该平台更希望广告主向其发送所有渠道（包括自然流量）的激活回传。请在对接配置的“事件来源”一栏选择“**所有媒体渠道，包括自然流量**”。

**前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系相关渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式如下：** 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**。界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">（启用）</Anchor>状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

ironSource的配置窗口中有以下5个选项卡：渠道对接、归因链接、成本、广告收入和授权。下文分小节介绍了各部分的配置信息。

如需进一步了合作伙伴配置页面中各选项卡的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">此文档</Anchor>。

> 👍 **建议**
>
> * 对接页面中的<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#d-general-settings">通用设置</Anchor>是广告主**必须**为所有合作渠道都配置的内容。
> * 其余步骤都是描述性的或是**可选的**

<div id="integration-tab" />

<Accordion title="对接选项卡">

### 启用渠道

请在首次访问该页面时打开**启用该渠道**开关，然后就可以设置对接了。在您与该渠道合作期间，请确保该开关总是处于打开状态。  
有关渠道激活的详细说明请参见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。

#### 高级隐私保护

启用<strong>高级隐私保护（iOS 14.5+）</strong>后，您可以<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#b-advanced-privacy">自行调整</Anchor>在回传和报告中与ironSource分享哪些信息。请注意：该功能仅适用于iOS应用。

### 交易ID

仅适用于iOS应用。打开**共享SKAN交易ID**开关就表示您允许AppsFlyer与ironSource<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">共享SKAdNetwork回传的交易ID</Anchor>。共享此ID后，ironSource就可以解析您的SKAdNetwork转化值。

> 📘 **注意事项**
>
> 如需启用ironSource与AppsFlyer的SKAN互通设置，请联系您的ironSource客户经理，让ironSource<Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/general/universal-skan-reporting/#step-1">向MMP发送SKAN数据</Anchor>。

### 通用设置

**Advertiser ID**

ironSource通过专属的Advertiser ID（由6位数字组成）和密码与AppsFlyer对接。如果您还不知道您的Advertiser ID和密码，请先在ironSource后台查看这些信息，然后才能继续完成对接。如果您已经有这些信息，请将ID和密码复制粘贴到相应的字段中。

### 激活和再互动归因

这两个开关打开后，即使用户只**浏览**而**未点击**您的广告，AppsFlyer也可以将相关的新增激活和重装激活归因到ironSource。详情请见<Anchor target="_blank" href="/marketers/zh/docs/measure-view-through-engagements">浏览型归因</Anchor>。

**如需对新增激活进行归因：**

1. 打开**浏览型激活归因**开关。
2. 在**归因链接选项卡**中配置[浏览](/docs/ironsource-campaign-configuration#attribution-link-tab)回溯窗口的时长。

**如需对现有用户的新增再互动进行归因：**

1. 打开**浏览型再互动归因**开关。
2. 在**归因链接选项卡**中配置[浏览](/docs/ironsource-campaign-configuration#attribution-link-tab)回溯窗口的时长。

### 默认回传

用户完成激活和再互动后自动向ironSource发送回传。您可以在这个板块中设置可用回传的**事件来源**。

若选择**仅该合作渠道**，则仅回传由ironSource带来的用户所完成的事件。  
若选择**所有媒体渠道，包括自然流量**：将所有用户的相关事件数据都上报给ironSource。

> 📘 **注意事项**
>
> 请注意：由于ironSource支持所有类型的激活归因，因此该平台更希望广告主向其发送所有渠道（包括自然流量）的激活回传。请在对接配置的“事件来源”一栏选择**所有媒体渠道，包括自然流量**。

### 应用内事件回传

将回传中的应用内事件映射到ironSource平台中的对应事件：

1. 打开**应用内事件回传**开关。
2. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。下表列出了必须配置的字段：  

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。<br />**提示**：如果下拉菜单中没有您要查看的事件：<ul><li>请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。</li><li>在**AppsFlyer事件**中输入该事件的名称，然后点击**创建自定义事件**。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">自定义事件映射</Anchor>。</li></ul> |
| **渠道映射事件** | 渠道侧为每个事件定义的专属名称或ID。映射配置包括以下几种：<ul><li>**文本字段：** 从渠道处获取相应的事件ID。</li><li>**下拉菜单：** 选择最合适的AppsFlyer预定义事件。</li><li>**按原样**：按原样发送事件，不进行名称映射。</li></ul> |
| **事件来源** | 选择事件回传的范围：<ul><li>**仅该合作渠道**：仅回传归因到该渠道的事件。</li><li>**所有媒体渠道，包括自然流量**：回传所有带量渠道以及自然量的事件。</li></ul> |
| **回传内容** | <ul><li>**不发送值与收入（默认）**：仅发送事件本身，不带任何事件值。</li><li>**发送值与收入**：发送所有事件参数，**包括**收入（若有）。</li><li>**仅发送值：** 发送**除**收入以外的所有参数。</li></ul> |

3. 【可选】点击**添加条件**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />图标，<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">设置事件的回传条件</Anchor>。
4. 点击**保存对接**。
5. 【可选】您可以在保存对接后留在配置页面，将其他应用也对接到该渠道：
   1. 点击页面左上角渠道名称下方的应用名称，打开应用列表。
   2. 在下拉菜单中选择一个其他应用。
   3. 为选定应用完成对接设置。

> 📘 **注意事项**
>
> * 仅适用于iOS应用：通过回传和<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">报告</Anchor>与渠道共享数据时，您对这些数据的控制范围取决于<strong>高级隐私模式（用于iOS14.5+）</strong>的<Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-advanced-srn-integration-setup#高级隐私保护">启用状态</Anchor>：
> * 您可以向ironSource发送<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">广告收入回传</Anchor>，以便ironSource侧根据相关的广告收入数据优化投放：
>   * **AppsFlyer事件名称：** af\_ad\_revenue
>   * **渠道映射事件名称：** adRevenue

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

生成并保存归因链接，然后将其发送到该渠道，使得相关流量可以被归因到具体的广告系列、广告组或单个广告，UA和再营销广告都在归因范围内。归因可以通过单平台链接或<Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink</Anchor>链接来实现。  
详情请见<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">归因链接结构和参数</Anchor>说明。

请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">相关说明</Anchor>**生成归因链接**。  
详情请见ironSource对点击和浏览的定义。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

AppsFlyer通过API获取成本信息。详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">广告平台成本对接表</Anchor>，其中详细说明了适用维度、指标和功能。**注意**：您需要购买ROI360才能获得成本数据。

**Cost API的启用方式如下**：

* <Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">请按照对接指南进行操作</Anchor>

您可以在成本（及广告收入）对接状态面板或单独的广告平台面板中查看AppsFlyer最近一次拉取成本数据的时间以及<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">成本API状态</Anchor>。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

如果您在应用中展示来自Unity LevelPlay（前身为ironSource）或ironSource聚合平台的广告，则需要配置这部分内容。

对于广告收入数据，我们支持下列颗粒度和发送方式：

* 通过S2S API上报的汇总数据
* 通过S2S API上报设备级别数据
* 通过SDK上报的展示级别数据。
* 由SDK上报的展示级别数据与由S2S API上报的设备级别数据相结合

详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution">广告收入归因</Anchor>。

**如需启用广告收入对接**：

* 请按照<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">对接指南</Anchor>进行操作。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

您可以在这个选项卡中为ironSource开放各种权限。请注意：即使您停用了ironSource归因，仍可以使用授权选项卡向ironSource开放各类权限。

您可以使用权限开关向广告平台授权，让其处理与自己相关的配置：

### 广告平台权限

* **允许配置对接**——允许该渠道设置对接选项卡（应用内事件回传除外）
* **允许配置应用内事件回传**——允许该渠道在对接选项卡中设置应用内事件回传，将事件映射到其平台。
* **允许访问留存报告**——仅限该渠道的留存数据
* **允许访问汇总忠实用户数据**——仅限该渠道的忠实用户数据
* **开放汇总应用内事件数据的访问权限**——仅限该渠道带来的应用内事件
* **允许访问汇总收入数据**——仅限归因给该渠道的收入数据
* **允许访问Protect360面板**——仅访问该渠道的Protect360数据（需广告主事先开通该功能）

如需进一步了解广告平台权限的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">此文档</Anchor>。

### 代理权限

您可以使用权限开关向代理商授权，让其处理与自己相关的配置：

* **主开关**——打开后可看到所有的代理权限选项
* **访问留存报告**——打开后代理可访问自己的留存数据
* **允许访问汇总的自然数据**
* **配置应用内事件回传**——打开后代理可在“渠道对接”选项卡中设置AppsFlyer事件在自己平台中的回传映射。

了解更多关于<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#代理权限">代理权限</Anchor>的详情。

</Accordion>

</Accordion>

<div data-zendesk-anchors="h_01HKW1E1KBG121H7YJBW2SZS6E=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01HCFHXQQ8FRF8D22A85PDN1B1=%E5%BB%BA%E8%AE%AE h_01HCFHXQQ8XYCKWPVTMK8HF165=integration-tab activate-partners=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01HCFHXQQ8HCXPEWR4CWY55M2H=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 advanced-privacy=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 h_01HCFHXQQ8ABQYRSBGC7Z1F1SV=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 transaction-id=%E4%BA%A4%E6%98%93id h_01HCFHXQQ8Q3BX7GSGD5MH4QT8=%E4%BA%A4%E6%98%93id h_01HCFHXQQ8D26KT5E6YEQ50DA4=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9-1 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01HCFHXQQ8J0ZC9FGCNTPMKHK6=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE install-and-reengagement-attribution=%E6%BF%80%E6%B4%BB%E5%92%8C%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 h_01HCFHXQQ8V2E8982XRSY4G50F=%E6%BF%80%E6%B4%BB%E5%92%8C%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0 default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HCFHXQQ8Q27JXG2V7G4XZX43=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HCFHXQQ8XZ6H3733GPR3ZFYE=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9-2 inapp-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01HCFHXQQ891GH196XFRXY8MYS=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01HCFHXQQ8VF25W10CWQHTEAYW=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9-3 h_01HCFHXQQ8AYNTCH9GHZJG594E=attribution-link-tab h_01HCFHXQQ87EBRW9NBY58XYFGP=cost-tab h_01HCFHXQQ8XZ8XQFH3XRFVHRZV=ad-revenue-tab h_01HCFHXQQ891P7ET9Q4BSQWJXT=permissions-tab ad-network-permissions=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90 h_01HCFHXQQ86VNX9WRFEZECYV7R=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90 agency-permissions=%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90 h_01HCFHXQQ936CQ1FVHCRC58H4C=%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90" />

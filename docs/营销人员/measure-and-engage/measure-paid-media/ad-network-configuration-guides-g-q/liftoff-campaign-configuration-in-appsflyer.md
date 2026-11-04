---
title: 如何在AppsFlyer配置Liftoff的广告系列
metadata:
  keywords:
    - liftoff
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
  created_at: '2016-03-28T09:38:23Z'
  edited_at: '2026-10-14T10:04:56Z'
  id: 209731633
  locale: zh-cn
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/zh-cn/articles/209731633
---
> **概要：** Liftoff是AppsFlyer的已对接合作伙伴，是品牌和应用开发人员合作最多的渠道之一。Liftoff支持点击归因和展示归因，以及基于点击和展示的再营销归因，广告主可以在AppsFlyer后台直接查看这些数据。

![](https://cdn.appsflyer.com/marketplace/static/logo/liftoff.png)

<div id="important" />

> 🚧 **重要提示！**
>
> 部分渠道限制第三方的数据共享。对于通过这些渠道获得的用户设备级别数据，AppsFlyer无法将其分享给第三方平台或服务商。这种情况下，由这些渠道带来的激活全部都会上报为自然量。
>
> 详情请见<Anchor target="_blank" href="/marketers/zh/docs/user-level-data-retention">此文档</Anchor>，其中列出了所有限制第三方数据共享的媒体渠道。

<div id="setting-up-liftoff" />

## 设置Liftoff

**前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系相关渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式如下：** 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**。界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">（启用）</Anchor>状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

下文说明了对接选项卡中所包含各部分内容。

<div id="activate-partners" />

### 启用渠道

请在首次访问时开启 <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation#渠道对接的启用方式">**激活合作伙伴**</Anchor> 开关以激活该合作伙伴，激活之后可对渠道进行归因配置。

<div id="general-settings" />

### 通用设置

**启用浏览型归因**

如果要启用Liftoff的展示归因，请激活这里。可在 [**归因链接**](/docs/liftoff-campaign-configuration-in-appsflyer#attribution-link-tab)选项卡中配置展示归因窗口期。

<div id="default-postbacks" />

### 默认回传

在用户安装、安装被拒、再互动之后，AppsFlyer可以自动回传这些事件至Liftoff。您可以在这个板块中设置可用回传的**事件来源**。

选择 **仅此伙伴**只会回传归因给Liftoff渠道的用户事件。   
选择<strong>所有渠道（包括自然渠道）</strong>会将所有用户的数据回传给Liftoff。

<div id="note" />

> 📘 **注意**
>
> 作为“全安装”网络，Liftoff希望获取所有渠道（包括自然渠道）新增安装的数据回传。建议选择 **所有渠道包括自然渠道** 以便将所有安装的数据回传给Liftoff。

**请按以下步骤配置应用内事件回传：**

1. 激活**应用内事件回传**
2. 选择回传**所选事件**或是**全部事件**给该合作伙伴。
   * 请注意：注意：如果选择回传所有事件，则不会回传 af\_app\_opened 事件。
3. 如果选择手动选择事件，请单击**添加事件**以将SDK事件添加到列表中。
4. 填写以下数据： 

| 参数名称 | 说明 |
| --- | --- |
| **SDK事件名称** （仅在手动选择时需要） | AppsFlyer从SDK或服务器收到的事件名称。   <br />**提示**：提示 ：如果没有在列表中看到所需的事件，请在任意非自然安装设备上激活此事件，然后重新检查。 |
| **发送选项** | 选择事件回传的范围：  <br />选择 仅此伙伴只会回传归因给Liftoff渠道的用户事件。   <br />**所有渠道包括自然渠道**可以回传全部用户信息给该合作伙伴 |
| **发送事件数据** | <ul><li>**不发送值与收入：** 仅发送事件本身，不发送事件值。</li><li>**含事件值不含收入值：** 发送除收入值以外的所有参数。</li><li>**含事件值和收入值** ：发送所有事件参数，包括收入值（如果事件中存在）。</li></ul> |

5. 点击**保存**。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

生成并保存归因链接，然后将其发送到该渠道，使得相关流量可以被归因到具体的广告系列、广告组或单个广告，UA和再营销广告都在归因范围内。归因可以通过单平台链接或<Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink</Anchor>链接来实现。  
详情请见<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">归因链接结构和参数</Anchor>。  

请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">相关说明</Anchor>**生成归因链接**。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

AppsFlyer通过API获取成本信息。详情请见广告平台成本对接表，其中详细说明了适用维度、指标和功能。**请注意**：您需要购买ROI360才能获得成本数据。

**成本API的启用方式如下**：

* 请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">对接指南</Anchor>进行操作。

<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">您可以在成本（及广告收入）对接状态面板或单独的广告平台面板中查看AppsFlyer最近一次获取匹配成本数据的时间以及</Anchor> API状态。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

该合作伙伴不支持广告收入数据。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

在该选项卡中，您可以选择要授予该渠道的权限。请注意，即使禁用 Liftoff的归因，授权选项卡仍处于有效状态，仍然可以对 Liftoff进行授权。

<div id="ad-network-permissions" />

### 广告平台权限

在该选项卡中，您可以选择要授予该渠道的权限。请注意，即使禁用 Liftoff的归因，授权选项卡仍处于有效状态，仍然可以对 Liftoff进行授权。

您可以使用权限开关向广告平台授权，让其处理与自己相关的配置：

* **允许配置对接**——允许该渠道设置对接选项卡（应用内事件回传除外）
* **允许配置应用内事件回传**——允许该渠道在对接选项卡中设置应用内事件回传，将事件映射到其平台。
* **允许访问留存报告**——仅限该渠道的留存数据
* **允许访问汇总忠实用户数据**——仅限该渠道的忠实用户数据
* **开放汇总应用内事件数据的访问权限**——仅限该渠道带来的应用内事件
* **允许访问汇总收入数据**——仅限归因给该渠道的收入数据
* **允许访问Protect360面板**——仅访问该渠道的Protect360数据（需广告主事先开通该功能）

如需进一步了解广告平台权限的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">此文档</Anchor>。

<div id="agency-permissions" />

### 代理权限

如果Liftoff是您的代理，则可以在这里授予他们配置该应用的权限：

* 主开关 设置为 ON ：   
  * 显示代理权限选项
  * 使代理能够获得应用的安装归因警告警告：开关为OFF时发生的代理安装不会归因给该代理 ，也不会显示在代理的控制面板和数据上（ 更多详细信息/strong> ）。

* **允许访问Protect360面板**
* **允许访问您的留存报告和群组报告** - 仅限于由该代理带来的用户留存和群组信息。
* **允许访问汇总的自然数据**
* **配置应用内事件回传**——打开后代理可在“渠道对接”选项卡中设置AppsFlyer事件在自己平台中的回传映射。
  * **事件共享权限** -在此处选择您的首选选项:  
    **仅限此渠道：** 仅发送来自该代理的流量所产生的事件。  
    **所有媒体渠道，包括自然量：** 发送来自所有流量来源的事件，包括其他媒体渠道、代理和自然量。
  * **允许发送事件收入** 允许代理商发送事件，包括其货币价值
  * 确保选择要授权给该代理的具体事件。单击 **添加事件** 然后从下拉列表中选择事件。对要添加的每个事件执行此操作。

如需进一步了解代理合作的相关事宜，请参考<Anchor target="_blank" href="/partners/zh/docs/about-agency-accounts">此文档</Anchor>。

</Accordion>


3. <span id="set-up-skadnetwork-integration-with-liftoff"></span>使用场景示例:

<div id="product-feed-retargeting-with-liftoff" />

## 使用Liftoff再营销广告Feed

为了正确归因产品事件，Liftoff需要接收与每个事件相关的产品ID。例如，用户购买或添加到购物车中的具体产品的商品ID。

这些ID需要与您在产品Feed中传给Liftoff的特有ID相匹配。对于标准的模式，Liftoff支持通过AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure#预定义事件参数">af\_content\_id</Anchor>参数分享该数据。

如果您使用的是非标准事件数据，请与您的Liftoff 账户经理联系，以了解是否可以进行对接。

<div data-zendesk-anchors="h_01HGFR9QYBQ3BK3TM364SJDKWZ=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA setting-up-liftoff=%E8%AE%BE%E7%BD%AEliftoff h_01HGFR9QYBPY2XR4KMWMJKHHMQ=%E8%AE%BE%E7%BD%AEliftoff h_01HGFR9QYBJG0WD6X203X8MYFV=integration-tab activate-partners=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01HGFR9QYBXAQQKPRW1KKF6989=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01HGFR9QYBPCYCJRY20S1TCF6R=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HGFR9QYB8JHTAAB591QQ1P6J=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HGFR9QYBW8DFZK63EZ3V5622=%E6%B3%A8%E6%84%8F h_01HGFR9QYB42YK8FJD308YWXC7=attribution-link-tab h_01HGFR9QYBJ20T4F0W5486B4NW=cost-tab h_01HGFR9QYBV9ZCGJ1D6BD1T9JG=ad-revenue-tab h_01HGFR9QYB9DA5XYXPEARZSCHF=permissions-tab ad-network-permissions=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90 h_01HGFR9QYB0VCPG7YCX64BBKY9=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E6%9D%83%E9%99%90 agency-permissions=%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90 h_01HGFR9QYBR3W0JXY7MHQ8PZT7=%E4%BB%A3%E7%90%86%E6%9D%83%E9%99%90 h_01HGFR9QYBG4830DKGMGV716B7=set-up-skadnetwork-integration-with-liftoff product-feed-retargeting-with-liftoff=%E4%BD%BF%E7%94%A8liftoff%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8Afeed h_01HGFR9QYB302DVBYXMK0XY4ED=%E4%BD%BF%E7%94%A8liftoff%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8Afeed" />

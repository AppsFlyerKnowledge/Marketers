---
title: Pinterest — 设置网页端应用对接
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
  created_at: '2026-06-14T13:07:07Z'
  edited_at: '2026-10-23T12:41:15Z'
  id: 47721580892433
  locale: zh-cn
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/zh-cn/articles/47721580892433
---
**概览：** 为您的网站应用设置 Pinterest 对接，将网页转化事件发送到 Pinterest，用于广告活动优化和报告。

<div id="set-up-integration" />

## **设置对接**

**前期准备：**

* 已注册 Pinterest 账户
* 已在 AppsFlyer 中完成设置的网站应用。<Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer#web">了解更多</Anchor>
* 用于网页归因的 AppsFlyer <Anchor target="_blank" href="/marketers/zh/docs/integrate-appsflyer-web-sdk">Web SDK</Anchor> 或 <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-s2s-api-for-web-performance-measurement">Server-to-Server (S2S) API</Anchor>

**请按照以下方式启用或修改该对接：**

1. **激活对接：** 在 AppsFlyer 中，从侧边菜单选择 **协作** > **渠道对接** > **Marketplace** 选项卡。  
   **编辑对接：** 在 AppsFlyer 中，从侧边菜单选择 **协作** > **渠道对接** > **激活对接** 选项卡。
2. 从上方下拉菜单中选择您的网站应用。
3. 搜索 Pinterest，然后点击**对接**（对接）。
4. 在 **对接** 选项卡中，打开 **启用渠道** 开关。  
   **请注意：** 只要您与 Pinterest 合作，就必须始终保持此开关处于<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">（已激活）</Anchor>状态。
5. 按照以下说明，在 **对接** 选项卡中完成配置。

<div id="integration-tab" />

## **对接选项卡**

<div id="activate-partner" />

### **激活合作伙伴**

在 **首次访问** 时，请打开 **启用渠道** 开关，以启用对接选项卡参数的设置。在与 Pinterest 合作期间，请确保此开关处于打开状态。

了解更多有关 <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">启用渠道</Anchor>的信息。

<div id="in-app-event-settings" />

### **应用内事件设置**

如需将应用内事件回传发送到 Pinterest，请提供以下 Pinterest 凭据。这些凭据会包含在发送到 Pinterest 的事件回传中。

* **广告账户 ID** - 您的 Pinterest 广告账户的唯一标识符。
* **访问令牌** - 在 Pinterest 中生成的访问令牌。

您可以在 Pinterest 广告管理工具 UI 中找到您的广告账户 ID 和访问令牌（请参阅 <Anchor target="_blank" href="https://developers.pinterest.com/docs/api-features/tracking-conversions/#getting-your-access-token-and-ad-account-id">Pinterest 文档</Anchor>）。如果您需要帮助，请联系 Pinterest 支持团队。

**设置 Pinterest 凭据：**

1. 在 AppsFlyer 中，在 Pinterest **活跃对接**页面 > **对接**选项卡中，向下滚动至**应用内事件设置**。
2. 在相应字段中输入广告账户 ID 和访问令牌值。

<div id="in-app-event-postbacks" />

### **应用内事件回传**

在本部分中，您可以通过回传将 AppsFlyer Web 事件映射到 Pinterest 事件。

1. 在 Pinterest 对接设置中，向下滚动到**应用内事件回传**。
2. 打开**应用内事件回传**开关。
3. 设置应用内事件回传窗口。
4. 选择事件的回传设置和映射。

| **参数名称** | **描述** |
| --- | --- |
| **AppsFlyer 事件名称** | Web 事件名称，即 AppsFlyer 通过您网站中集成的 Web SDK 或通过服务器到服务器事件接收的事件名称。<br /><br />**注意：** 如果您没有在列表中看到所需事件，请确保该事件已激活，然后重新检查。 |
| **渠道事件名称** | 要映射到的 Pinterest 事件，从 Pinterest 的预定义事件列表中选择。有关 Pinterest 事件名称，请参阅 <Anchor target="_blank" href="https://developers.pinterest.com/docs/api-features/track-conversion-events/#understand-conversion-events">Pinterest 文档</Anchor>。 |
| **事件来源** | **仅该合作伙伴：** 仅来自归因给 Pinterest 的用户的事件。<br /><br />**所有媒体渠道，包括自然流量：** 可将您的全部用户群报告给该合作伙伴。 |
| **包含数据** | 选择是否在回传中向合作伙伴发送事件收入或参数值。 AppsFlyer 可以发送丰富的网页事件的所有参数（不包括收入参数，即 **af\_revenue** 中包含的参数），也可以发送所有参数（包括收入值，如有）。 |

> 📘 **Note**
>
> 如果您的网站同时运行 Pinterest Tag，请将相同的事件 ID 同时发送到 AppsFlyer 和 ChatGPT Ads，以便 AppsFlyer 对事件进行去重：
>
> * 发送到 AppsFlyer 的事件载荷中需包含 af\_customer\_event\_id：对于 Web SDK，可将其包含在 eventValue 中；对于 S2S（服务器到服务器）API，可将其包含在 event\_value 中。
> * 在对应的 Tag 事件中发送相同的值。
>
> AppsFlyer 会将此值作为事件 ID 转发给 Pinterest。随后，Pinterest 会使用该 ID，将从 AppsFlyer 接收的服务端事件与 Tag 事件去重，因此 AppsFlyer 只会统计一次转化。
>
> 如果您未发送 af\_customer\_event\_id，AppsFlyer 会自动生成一个事件 ID。此 ID 不会与您的 Tag 事件匹配。
>
> 如需了解更多信息，请参阅《对接 AppsFlyer Web SDK》。

5. 点击 **添加事件**，将事件添加到列表中。

<div data-zendesk-anchors="set-up-pinterest=%E8%AE%BE%E7%BD%AE%E5%AF%B9%E6%8E%A5 h_01KV339A5ZGK96JNCNR78PDMNH=%E8%AE%BE%E7%BD%AE%E5%AF%B9%E6%8E%A5 integration-tab=%E5%AF%B9%E6%8E%A5%E9%80%89%E9%A1%B9%E5%8D%A1 h_01KV339A67N4436STPW1VJR585=%E5%AF%B9%E6%8E%A5%E9%80%89%E9%A1%B9%E5%8D%A1 activate-partner=%E6%BF%80%E6%B4%BB%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4 h_01KV339A67H0DSSJ3P84PXGQ2F=%E6%BF%80%E6%B4%BB%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4 inapp-event-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01KV339A68YZBZZ73T8XTBE6BR=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE inapp-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01KV339A6BN0CWYX7GCJ19RN0J=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0" />

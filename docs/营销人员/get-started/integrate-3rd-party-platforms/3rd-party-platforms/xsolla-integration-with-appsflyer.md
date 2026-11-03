---
title: 将Xsolla与AppsFlyer对接
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2024-03-25T06:20:28Z'
  edited_at: '2026-10-14T10:09:43Z'
  id: 23593013687185
  locale: zh-cn
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/zh-cn/articles/23593013687185
---
> **概要：** Xsolla是AppsFlyer的对接合作伙伴，专注于游戏电商技术，尤其擅长处理非传统应用商店平台的支付流程。通过与AppsFlyer的对接，Xsolla可将Web Shop中的购买与收入数据自动回传至AppsFlyer，呈现完整ROAS和LTV数据，包括在Xsolla Web Shop中完成的交易。

> 🚧 **重要提示！**
>
> <Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions#媒体渠道数据限制">部分渠道</Anchor>限制第三方的数据共享。 这时，我们不会向渠道发送受限事件的回传，不论您是否在回传配置部分选择了该事件。

## 对接类型

您可采取两种方式与Xsolla对接：

* [技术合作伙伴对接](#设置技术合作伙伴对接)：通过此方式，Xsolla可将Web Shop中的购买与收入数据作为移动端应用内事件发送至AppsFlyer，从而在标准应用商店购买之外，进一步提升移动端广告活动的ROAS和LTV表现。
* [PBA Web SDK对接](#设置pba-web-sdk对接)；通过此方式，Xsolla可将Web Shop中的购买与收入作为网页事件发送至AppsFlyer，对网页端广告活动效果进行衡量，并将游戏用户直接引导至Web Shop。

**前期准备：**

* 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。
* 为确保对接正常运行，请将Customer User ID（CUID）与AppsFlyer共享，并确保CUID与提供给Xsolla的用户ID一致。只有完成这一步骤，用户才能成功登录Xsolla的Web Shop，其数据才能被准确归因并同步到AppsFlyer中。

## 设置技术合作伙伴对接

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式**：从AppsFlyer面板左侧的菜单栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**，界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">（启用）</Anchor>状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

此时您仅可使用配置窗口中的**对接**选项卡。

如需进一步了合作伙伴配置页面中各选项卡的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">此文档</Anchor>。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

#### 启用渠道

请在首次访问该页面时打开**启用该渠道**开关，然后就可以设置对接了。在您与Xsolla合作期间，请确保该开关总是处于打开状态。详情请见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">渠道启用说明</Anchor>。

#### 高级隐私保护

iOS应用的面板中会显示<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">高级隐私</Anchor>开关，此开关打开时可限制渠道共享用户标识符。请注意：如果您在应用配置中打开了<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">汇总层级的高级隐私</Anchor>开关，AppsFlyer会默认开启并锁定**高级隐私（适用于iOS 14.5及以上版本）**。

#### 默认回传

用户激活应用后，AppsFlyer会向Xsolla发送默认回传。详情请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#default-postbacks">回传设置说明</Anchor>。

* **关闭**：不向Xsolla发送激活回传。  
  **请注意：** Xsolla与AppsFlyer的对接时不要求发送激活回调。因此，建议您将其设置为关闭。
* **所有媒体渠道，包括自然流量：** 发送来自所有渠道以及自然流量的激活回传。

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

#### 应用内事件回传

这部分选项用于设置AppsFlyer事件与渠道之间的映射与回传。

![xsolla-af-login-3.jpg](https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg)

1. 打开**应用内事件回传**开关。
2. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。
3. 请配置以下参数：

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。<br /><br />**请注意：**<ul><li>对于Xsolla，请务必添加af\_login事件，或其他能代表用户登录移动应用的事件（如上方截图所示）。</li><li>建议您不要发送过于频繁的事件，并避免在此类事件中包含CUID（例如af\_app\_opened），否则可能会导致对接无法正常运行。</li></ul> |
| **渠道映射事件** | 请输入向Xsolla发送的事件名称。Xsolla在事件命名方面没有限制，你可以在此字段中使用任意名称。 |
| **事件来源** | 选择**所有媒体渠道，包括自然流量**：发送来自所有渠道以及自然流量的激活回传。 |
| **回传内容** | <ul><li>**不发送值与收入：** 仅发送不带任何参数的事件本身（即没有值或收入）。</li><li>**仅发送值：** 发送**除**收入以外的所有参数。</li><li>**发送值与收入**：发送所有事件参数，**包括**收入（若有）。</li></ul>请注意： Xsolla与AppsFlyer的对接并不要求发送值或收入，因此上述任意选项均可使用。 |

4. 点击**保存对接** 。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

Xsolla不支持归因链接。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

Xsolla的渠道对接不支持成本数据。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

Xsolla的渠道对接不支持广告收入数据。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

权限设置不适用于Xsolla。

</Accordion>

## 设置PBA Web SDK对接

对接后，您可以在PBA面板中查看LTV（数据与相关洞察，分析应用表现。

**如需设置对接：**

1. **在AppsFlyer后台：** <Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer?query=adding%20an%20app">添加Xsolla应用</Anchor>。将平台选择为<Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer#web-pba">Web（PBA）</Anchor>，并填写以下信息：
   * 将你的Web Shop域名用作Web app URL，例如：如果你的Web Shop域名是[www.webshop.com](https://www.webshop.com)，则该URL即为你的Web app URL。
   * 应用名称可设置为任意值。
2. **在AppsFlyer后台进行如下操作：** <Anchor target="_blank" href="/marketers/zh/docs/pba-brand-bundles-and-settings#add-brand-bundle">添加Xsolla套件</Anchor>，详细信息如下：
   1. 1. 套件名称可设置为任意名称。
      2. 选择你在上一步创建的网页应用。
3. **在Xsolla中进行如下操作：** 将AppsFlyer与您的Xsolla Publisher账户连接：
   1. 在<Anchor target="_blank" href="https://publisher.xsolla.com/">Publisher账户</Anchor>中打开您的项目。
   2. 选择您的站点并单击**配置**。
   3. 在**站点设置**选项卡中，转到**应用程序**部分。
   4. 在**AppsFlyer**模块中，点击**连接**。  
      [![xsolla-connect.jpg](https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg)](https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg)
   5. 在**AppsFlyer Dev Key**字段中，输入 AppsFlyer 网络开发者密钥。请参见下文了解如何[在 AppsFlyer 中获取密钥](/docs/xsolla-integration-with-appsflyer#在appsflyer中查找网络开发者密钥)。
   6. 点击**连接**。

#### 在AppsFlyer中查找网络开发者密钥

1. 在**我的应用**页面，点击**查看品牌套件**。
2. 点击Xsolla套件上的复制图标。

![xsolla-brand-bundle2.jpg](https://files.readme.io/9cb6a9e872e482f7e426aea7e615afb1f91017c569e7cd67286cdb946d9d2445-26923253273361.jpg)

## 在AppsFlyer中识别Xsolla的事件

### 技术合作伙伴 (S2S) 对接方式：

Xsolla会向AppsFlyer发送2类应用内事件：

* **xsolla-billing-payment** - 代表用户完成了一项购买
* **xsolla-billing-refund** - 代表用户发起了购买退款

这两个事件都会作为应用内事件出现在AppsFlyer中。

### Web SDK对接方式：

Xsolla会根据具体广告主的业务活动，向AppsFlyer发送多个网页事件。其中最重要的事件是名为 "PURCHASE" 的事件，该事件包含收入信息。  
Xsolla的网页事件将展示在PBA的网页归因数据中，并可在DataLocker的“网页事件”原始数据报告中查看。

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

PC / 主机端 - 目前，AppsFlyer与Xsolla的对接不支持PC或主机端应用。

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="https://developers.xsolla.com/solutions/web-shop/analytics/appsflyer/">Xsolla提供的说明文档</Anchor>

<div data-zendesk-anchors="h_01HST42K52VQDWCWGP7TQVFB2X=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA integration-types=%E5%AF%B9%E6%8E%A5%E7%B1%BB%E5%9E%8B h_01J3DB8MCNQKKKCV1M39KN7Q0H=%E5%AF%B9%E6%8E%A5%E7%B1%BB%E5%9E%8B setting-up-xsolla=%E8%AE%BE%E7%BD%AE%E6%8A%80%E6%9C%AF%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4%E5%AF%B9%E6%8E%A5 h_01HST42K52JKQ70F7Y5PHDZAZ5=%E8%AE%BE%E7%BD%AE%E6%8A%80%E6%9C%AF%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4%E5%AF%B9%E6%8E%A5 h_01HST42K52YZMTE3C2TBTK865M=integration-tab activate-partner=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01HST42K52RCTSGRNRCJ1C70NP=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 advanced-privacy=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 h_01HST42K52BBJ6JS5KM0WCN6CF=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HST47F5BXWV5W8BNHS9M2MTN=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01H9FKEAV3GG6X17X3NCCSWJAS=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01HST42K53GSMD91ACXY9DMP7S=attribution-link-tab h_01HST42K53D0PPXTM7MHBQ8P04=cost-tab h_01HST42K53YS8N6G2V0279F5GA=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab setting-up-the-pba-web-sdk-integration=%E8%AE%BE%E7%BD%AEpba-web-sdk%E5%AF%B9%E6%8E%A5 h_01J3DEZZHDPSRZRXDV6FD4HY6Q=%E8%AE%BE%E7%BD%AEpba-web-sdk%E5%AF%B9%E6%8E%A5 finding-the-web-dev-key-in-appsflyer=%E5%9C%A8appsflyer%E4%B8%AD%E6%9F%A5%E6%89%BE%E7%BD%91%E7%BB%9C%E5%BC%80%E5%8F%91%E8%80%85%E5%AF%86%E9%92%A5 h_01J3F247QEAFGRW7CEP941KZE9=%E5%9C%A8appsflyer%E4%B8%AD%E6%9F%A5%E6%89%BE%E7%BD%91%E7%BB%9C%E5%BC%80%E5%8F%91%E8%80%85%E5%AF%86%E9%92%A5 identifying-xsollas-events-in-appsflyer=%E5%9C%A8appsflyer%E4%B8%AD%E8%AF%86%E5%88%ABxsolla%E7%9A%84%E4%BA%8B%E4%BB%B6 h_01JMHXRGB60RVZ399FNHS18ZHZ=%E5%9C%A8appsflyer%E4%B8%AD%E8%AF%86%E5%88%ABxsolla%E7%9A%84%E4%BA%8B%E4%BB%B6 tech-partner-s2s-integration=%E6%8A%80%E6%9C%AF%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4-s2s-%E5%AF%B9%E6%8E%A5%E6%96%B9%E5%BC%8F h_01JMHXS5MZ7B781WNNVYMDGGFY=%E6%8A%80%E6%9C%AF%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4-s2s-%E5%AF%B9%E6%8E%A5%E6%96%B9%E5%BC%8F web-sdk-integration=web-sdk%E5%AF%B9%E6%8E%A5%E6%96%B9%E5%BC%8F h_01JMHXX7VBPPS7GQ0VBGWRPT7X=web-sdk%E5%AF%B9%E6%8E%A5%E6%96%B9%E5%BC%8F h_01JN0HXSEJV9JPAXGSBM7B3X7X=traits-and-limitations h_01J1C78W0MP8KXFB4251FKWJBX=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

---
title: ChatGPT Ads（OpenAI）对接设置
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-07-05T13:42:23Z'
  edited_at: '2026-10-14T10:00:36Z'
  id: 48439655791249
  locale: zh-cn
  section: Measure paid media
  section_id: 6550990672401
  url: https://support.appsflyer.com/hc/zh-cn/articles/48439655791249
---
> **概览：** ChatGPT Ads是OpenAI的广告平台，也是AppsFlyer的对接合作伙伴。完成对接设置后，即可衡量并归因由ChatGPT Ads广告系列带来的移动应用安装、应用内事件和网站转化。

<div id="about-the-integration-with-chatgpt-ads" />

## 关于与ChatGPT Ads的对接

AppsFlyer与ChatGPT Ads（OpenAI）的对接可帮助您衡量并归因由ChatGPT Ads广告系列带来的应用安装、应用内事件和网站转化。该对接同时支持移动应用和网站衡量。

* **移动端** - AppsFlyer可将应用安装和再互动归因至ChatGPT Ads广告系列，并回传应用内事件。
* **网页端** - AppsFlyer可将AppsFlyer Web SDK采集的网站事件（如页面浏览、内容浏览和购买）转发至ChatGPT Ads的Conversions API（CAPI），也可配合或替代ChatGPT Ads JavaScript Pixel使用。

如果您的网站同时部署了ChatGPT Ads Pixel，ChatGPT Ads会通过共享的事件ID，对服务端（CAPI）事件与Pixel事件进行去重。因此，两者可以同时使用，不会造成转化次数重复统计。

<div id="set-up-the-integration" />

## 设置对接

您需要为每个移动应用和网站分别完成对接设置。对接时，需使用应用或网站在ChatGPT Ads（OpenAI）Ads Manager账户中的Pixel ID和API密钥。

**前提条件：**

* 完成对接前，请先注册ChatGPT Ads账户。
* 您的移动应用和网站应用已在 AppsFlyer 中设置。<Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer">了解详情</Anchor>

**设置对接：**

1. **激活：** 在AppsFlyer中，从侧边菜单选择**协作**>**渠道对接**>**Marketplace**选项卡。  
   **编辑：** 在AppsFlyer中，从侧边菜单选择**协作**>**渠道对接**>**活跃对接**选项卡。
2. 分别为以下对象设置对接：

* [**移动端**](#对接移动应用) - 将安装、再互动和应用内事件归因至ChatGPT Ads广告系列。
* [**网页端**](#对接网站) - 将网站转化事件转发至ChatGPT Ads的Conversions API，并与ChatGPT Ads Pixel事件去重。

<div id="integrate-your-mobile-app" />

## 对接移动应用

按照以下步骤，为移动应用配置ChatGPT Ads归因和应用内事件回传。

**对接移动应用：**

1. 在AppsFlyer中，从侧边菜单选择**协作**>**渠道对接**>**Marketplace**选项卡。
2. 从下拉菜单中选择您的移动应用。  
   **注意：** 如果应用同时运行在多个平台（例如Android和iOS），需要分别完成以下配置。
3. 搜索**ChatGPT Ads（OpenAI）**，然后点击**对接**。
4. 按照下文说明完成各选项卡配置。

<div id="integration-tab" />

<Accordion title="对接选项卡">

<div id="activate-partner" />

#### 激活合作伙伴

**激活对接：**

开启**活跃对接**开关。

**重要提示：** 使用ChatGPT Ads期间，请始终保持**开启**此开关。关闭对接后，广告系列的归因和事件回传都会停止。  
详细了解<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">合作伙伴激活</Anchor>。

<div id="general-settings" />

#### 常规设置

填写以下凭证：

* **Pixel ID** - 请前往ChatGPT Ads Manager创建Pixel，并在Ads Manager账户的Conversions选项卡中获取Pixel ID。**API密钥** - 调用Events API时需要使用API密钥进行身份验证。前往ChatGPT Ads Manager账户的Conversions选项卡获取API密钥。
* **API密钥** - 调用Events API时，需要使用API密钥进行身份验证。您可以在ChatGPT Ads Manager账户的转化选项卡中获取。   
  **注意：** 使用API密钥时，请选择Conversions API密钥。广告管理API密钥不具备所需权限，无法用于此对接。

**高级匹配数据共享：** 开启此项以与 ChatGPT Ads 共享高级匹配字段（例如哈希处理后的电子邮件、哈希处理后的电话号码、哈希处理后的名字和哈希处理后的姓氏），前提是这些字段包含在发送给 AppsFlyer 的事件信息中。详情请见：<Anchor target="_blank" href="/marketers/zh/docs/advanced-matching-data-sharing">高级匹配数据共享</Anchor>。

<div id="default-postbacks" />

#### 默认回传

回传（Postback）是AppsFlyer发送至ChatGPT Ads的服务器到服务器（S2S）通知，用于上报已归因的事件（例如安装或应用内操作）。本部分显示当前配置的回传。了解如何<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">设置安装和重新归因回传</Anchor>。

详细了解<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#default-postbacks">默认回传设置</Anchor>。

<div id="in-app-event-settings" />

#### 应用内事件设置

如需将应用内事件回传至ChatGPT Ads，请填写以下凭证：

* Pixel ID
* API密钥

具体说明请参阅上文的[常规设置](#常规设置)。

<div id="in-app-event-postbacks" />

#### 应用内事件回传

配置发送至ChatGPT Ads的应用内事件回传。<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration">了解详情</Anchor>

**启用应用内事件回传：**

开启**应用内事件回传**开关。

**应用内事件回传窗口期**

设置安装、重新归因或再互动后，AppsFlyer向ChatGPT Ads发送应用内事件回传的有效时间范围。<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration">了解详情</Anchor>

**事件映射**

将AppsFlyer事件名称映射到ChatGPT Ads中的对应事件名称，确保事件能够正确匹配。<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#事件映射">了解详情</Anchor>

ChatGPT Ads支持以下标准事件；对于未包含在下表中的事件，可使用**Custom**作为自定义事件。

| ChatGPT Ads事件名称 | 适用场景 |
| --- | --- |
| page\_viewed | 用户访问或浏览重要页面。 |
| contents\_viewed | 用户浏览某个商品、列表、文章或内容。 |
| items\_added | 用户将一个或多个商品加入购物车、套餐或待选列表。 |
| checkout\_started | 用户开始结账流程。 |
| order\_created | 用户完成购买。 |
| registration\_completed | 用户完成账户注册或活动报名。 |
| lead\_created | 用户提交线索表单或发起联系请求。 |
| appointment\_scheduled | 用户预约会议、产品演示或咨询。 |
| trial\_started | 用户开始免费试用。 |
| subscription\_created | 用户开通付费订阅。 |
| app\_opened | 用户打开移动应用。 |
| custom | 适用于所有未包含在标准事件中的自定义事件。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

ChatGPT Ads（OpenAI）支持归因链接。

<div id="choose-your-attribution-type" />

#### 选择您的归因类型

根据您的广告系列需求，决定使用单平台归因链接还是 <Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink</Anchor> 作为您的最终 URL。

* 如果您使用单平台链接，请确保最终 URL 是透明的，例如 `af_r={store URL}`。
* 您无法为每个操作系统设置单独的广告系列，因为 ChatGPT Ads 不支持原生 iOS 或 Android 定向。
* 如果您使用 OneLink，可能会收到较低的质量评分，这会影响广告投放，因为 ChatGPT Ads 的广告审核流程包括抓取最终 URL。

**推荐：** 使用落地页作为广告目标页面，并使用 <Anchor target="_blank" href="/marketers/zh/docs/onelink-smart-script-overview">Smart Script</Anchor> 或 <Anchor target="_blank" href="/marketers/zh/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner</Anchor> 将用户引导至 App Store 或 Google Play。

<div id="select-parameters" />

#### 选择参数

选择您想要包含的归因链接参数。

* 选择您想要包含的归因链接参数（例如， **广告系列名称** 和 **站点 ID**） 并设置您的 **点击归因回溯窗口**（7 天是 AppsFlyer 推荐的默认设置）。AppsFlyer 会自动生成 您的归因链接，供您在 ChatGPT Ads 中使用。 触达范围。
* 以下 URL 参数可由 ChatGPT 自动填充， 使用这些动态 URL 宏：
  * `af_partner_account_id={ad_account_id}`
  * `af_c_id={campaign_id}`
  * `af_adset_id={ad_group_id}`
  * `af_ad_id={ad_id}`
  * `clickid={oppref}`

**重要提示：** 为了让 AppsFlyer 能够捕获 ChatGPT Ads 的点击 ID 并 发送回 ChatGPT Ads，请确保使用 `clickid={oppref}`，如果 您的广告直接引导至 App Store 或 Google Play。当广告目标页面 是带有 Smart Script 的落地页时，请确保捕获传入的 `oppref` 参数并将其映射到传出链接中的 `clickid` URL

* 不支持名称字段宏。

**注意：生成的链接中包含**（ChatGPT Ads在AppsFlyer中的集成ID）/strong>。

详细了解<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">归因链接</Anchor>。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

ChatGPT Ads目前暂不支持成本API对接。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

AppsFlyer无法从ChatGPT Ads获取广告收入数据。如需共享广告收入数据以优化广告系列，可通过回传或UA信号实现。

</Accordion>

<div id="permissions-tab" />

<Accordion title="权限选项卡">

开启**广告平台权限**，即可向ChatGPT Ads团队成员授予数据访问权限。启用后，您可以选择授予具体权限，例如配置对接、访问留存和队列分析报告，或查看汇总转化和收入数据。即使已关闭ChatGPT Ads的归因功能，仍可授予相关权限。

详细了解<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">权限</Anchor>。

</Accordion>

<div id="integrate-your-website" />

## 对接网站

按照以下步骤，为您的网站设置向ChatGPT Ads转发服务端事件。

**对接网站：**

1. 在AppsFlyer中，从侧边菜单选择**协作**>**渠道对接**>**Marketplace**选项卡。
2. 从下拉菜单中选择您的网站应用。
3. 搜索**ChatGPT Ads（OpenAI）**，然后点击**对接**。
4. 按照以下说明，在对接选项卡中完成配置。

<div id="integration-tab::2739744d" />

<Accordion title="对接选项卡">

<div id="activate-partner-1" />

#### 激活合作伙伴

**激活对接：**

开启**活跃对接**开关。

**重要提示：** 使用ChatGPT Ads期间，请始终保持**开启**此开关。停用对接后，网站事件将停止转发。  
详细了解<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">合作伙伴激活</Anchor>。

<div id="in-app-event-settings-1" />

#### 应用内事件设置

如需将事件回传至ChatGPT Ads，请填写以下凭证：

* **Pixel ID** - 请前往ChatGPT Ads Manager创建Pixel，并在Ads Manager账户的Conversions选项卡中获取Pixel ID。**API密钥** - 调用Events API时需要使用API密钥进行身份验证。前往ChatGPT Ads Manager账户的Conversions选项卡获取API密钥。
* **API密钥** - 调用Events API时，需要使用API密钥进行身份验证。您可以在ChatGPT Ads Manager账户的转化选项卡中获取。

**高级匹配数据共享：** 开启此项以与 ChatGPT Ads 共享高级匹配字段（例如哈希处理后的电子邮件、哈希处理后的电话号码、哈希处理后的名字和哈希处理后的姓氏），前提是这些字段包含在发送给 AppsFlyer 的事件信息中。详情请见：<Anchor target="_blank" href="/marketers/zh/docs/advanced-matching-data-sharing">高级匹配数据共享</Anchor>。

<div id="in-app-event-postbacks-1" />

#### 应用内事件回传

配置发送至ChatGPT Ads的事件回传。<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration">了解详情</Anchor>

**启用事件回传：**

开启**应用内事件回传**开关。

**事件映射**

将AppsFlyer事件名称映射到ChatGPT Ads中的对应事件名称，确保事件能够正确匹配。ChatGPT Ads支持的标准事件请参阅上文事件列表。<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#事件映射">了解详情</Anchor>

</Accordion>

<div id="h_01KWVSPJ9WATTRLNK" />

<Accordion title="归因链接选项卡">

对于网站对接，ChatGPT Ads（OpenAI）不使用外部归因链接。AppsFlyer Web SDK会采集网站事件，并直接转发至ChatGPT Ads的Conversions API，因此无需配置基于链接的归因。

</Accordion>

<div id="h_01KWVSPJ9WCOST" />

<Accordion title="成本选项卡">

对于网站对接，ChatGPT Ads不提供成本数据。

</Accordion>

<div id="h_01KWVSPJ9WADREV" />

<Accordion title="广告收入选项卡">

对于网站对接，ChatGPT Ads不提供广告收入数据。

</Accordion>

<div id="h_01KWVSPJ9WPERM" />

<Accordion title="权限选项卡">

对于网站对接，ChatGPT Ads不支持权限设置。

</Accordion>

<div id="traits-and-limitations" />

## 特性与限制

| 特性 | 说明 |
| --- | --- |
| 支持的国家/地区 | 目前，ChatGPT Ads仅支持在以下国家/地区投放广告系列：美国、加拿大、澳大利亚、新西兰、英国、日本和韩国。墨西哥和巴西即将开放支持。 |

<div id="see-also" />

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">合作伙伴对接</Anchor>

<div data-zendesk-anchors="about-the-integration=%E5%85%B3%E4%BA%8E%E4%B8%8Echatgpt-ads%E7%9A%84%E5%AF%B9%E6%8E%A5 h_01KWS8SS8RE2VQ275MFB7CT39J=%E5%85%B3%E4%BA%8E%E4%B8%8Echatgpt-ads%E7%9A%84%E5%AF%B9%E6%8E%A5 set-up-the%20integration=%E8%AE%BE%E7%BD%AE%E5%AF%B9%E6%8E%A5 h_01H95QTA3Z5HXW39AHAF8FMFWH=%E8%AE%BE%E7%BD%AE%E5%AF%B9%E6%8E%A5 integrate-your-mobile-app=%E5%AF%B9%E6%8E%A5%E7%A7%BB%E5%8A%A8%E5%BA%94%E7%94%A8 h_01KWVBQG0G85W6QJ8AT2520GTX=%E5%AF%B9%E6%8E%A5%E7%A7%BB%E5%8A%A8%E5%BA%94%E7%94%A8 h_01KWVK5J7FBA81238JD4AD0219=integration-tab activate-partner=%E6%BF%80%E6%B4%BB%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4 h_01H95QTA3ZGEM34HY1A7NC8NX7=%E6%BF%80%E6%B4%BB%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4 general-settings=%E5%B8%B8%E8%A7%84%E8%AE%BE%E7%BD%AE h_01KWVKHV36H34XCHYBFRHNF8TB=%E5%B8%B8%E8%A7%84%E8%AE%BE%E7%BD%AE default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01KWVKZJ7AZ8Z4CFM8J0PV071A=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-event-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01JTDP2T0BFP5WP03X5EMXVAWA=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE inapp-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01KWVMZC74AQSN7BDQP2QQWBT4=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01KWVK5J7FE0ZF74NGXKSASMBV=attribution-link-tab h_01_choose-your-attribution-type=%E9%80%89%E6%8B%A9%E6%82%A8%E7%9A%84%E5%BD%92%E5%9B%A0%E7%B1%BB%E5%9E%8B choose-your-attribution-type=%E9%80%89%E6%8B%A9%E6%82%A8%E7%9A%84%E5%BD%92%E5%9B%A0%E7%B1%BB%E5%9E%8B h_01_select-parameters=%E9%80%89%E6%8B%A9%E5%8F%82%E6%95%B0 select-parameters=%E9%80%89%E6%8B%A9%E5%8F%82%E6%95%B0 h_01KWVK5J7FK8BAQKEMNA35ABPY=cost-tab h_01KWVK5J7FQRYXQ9FGCWHWY16T=ad-revenue-tab h_01KWVK5J7G3E8NSNDG4CR9FA7N=permissions-tab integrate-your-website=%E5%AF%B9%E6%8E%A5%E7%BD%91%E7%AB%99 h_01KWVSJRYSQEH12C5RH7BN4CC2=%E5%AF%B9%E6%8E%A5%E7%BD%91%E7%AB%99 h_01KWVSPJ9WJERF84ZNGTS7P0HZ=integration-tab::2739744d activate-partner::3c5a91e7=%E6%BF%80%E6%B4%BB%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4-1 h_01KWVSPJ9WBQ2AS5JZPTJZPTRG=%E6%BF%80%E6%B4%BB%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4-1 inapp-event-settings::a3adef08=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE-1 h_01KWVSPJ9WV7ZQZD00ZB7T639X=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE-1 inapp-event-postbacks::c3d06354=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0-1 h_01KWVSPJ9WA7Q1M281Q5NBYHV7=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0-1 attribution-link-tab::3e2b1646=h_01KWVSPJ9WATTRLNK cost-tab::c486dc3c=h_01KWVSPJ9WCOST ad-revenue-tab::84884d8a=h_01KWVSPJ9WADREV permissions-tab::6f805250=h_01KWVSPJ9WPERM traits-and-limitations=%E7%89%B9%E6%80%A7%E4%B8%8E%E9%99%90%E5%88%B6 h_01KX3DAS0FBTKGKE7CZJTDTY2X=%E7%89%B9%E6%80%A7%E4%B8%8E%E9%99%90%E5%88%B6 h_01KWVT1XJ2FKP1CACRV24C1R8E=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85" />

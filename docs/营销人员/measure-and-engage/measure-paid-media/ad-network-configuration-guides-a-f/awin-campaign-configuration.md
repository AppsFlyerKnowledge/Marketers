---
title: Awin活动配置
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
  created_at: '2023-09-13T11:50:38Z'
  edited_at: '2026-10-14T10:06:06Z'
  id: 18532554968849
  locale: zh-cn
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/zh-cn/articles/18532554968849
---
> **概要：** Awin（affiliatewindow\_int）是一个集成合作伙伴，允许广告主进行用户获取和重定向活动。Awin的营销平台帮助商家（广告主）与联盟（发布者）连接。

![awin icon.png](https://files.readme.io/2a7f22084586fec820c0bfab7f3a256259c43d37f14d6fed8e8db3d2e9905947-18533392495377.png)

## 启用渠道

**前提条件：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式如下：** 从AppsFlyer面板左侧的菜单栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**，界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">（启用）</Anchor>状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

## 设置Awin

与Awin的集成支持点击归因。

配置窗口包括以下选项卡：渠道对接、归因链接、成本、广告收入和授权。对于Awin，可用的选项卡有集成、归因链接和权限。

> 📘 **注意**
>
> * 部分设置分iOS和安卓
> * 进一步了解<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">渠道对接配置</Anchor>

### 前期准备

在设置集成之前，请确保在SDK中实现所需的“佣金组”参数，如<Anchor target="_blank" href="https://help.awin.com/docs/appsflyer">Awin文档</Anchor>中所述。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

**渠道对接**选项卡中包括以下几个部分。

#### 启用渠道

在配置对接之前，必须先<Anchor target="_blank" href="/marketers/zh/docs/amazon-ads-campaign-configuration#启用渠道">打开</Anchor>**启用该渠道**开关。详情请见渠道对接的启用和停用说明。有关更多信息，您可以参考<Anchor target="_blank" href="https://developer.awin.com/docs/appsflyer">Awin集成页面</Anchor>.

#### 高级隐私保护

仅适用于iOS应用：通过回传和<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">报告</Anchor>与共享渠道数据时，您对这些数据的控制范围取决于<strong>高级隐私模式（用于iOS14.5+）</strong>的启用状态：

| 高级隐私保护：启用 | 高级隐私保护：停用 |
| --- | --- |
| 仅发送归因到该渠道的事件回传 | 根据您指定的配置发送回传：<ul><li>**所有媒体渠道，包括自然流量**</li><li>**仅该合作渠道**</li></ul> |
| 根据<Anchor target="_blank" href="/partners/zh/docs/advanced-privacy-guide-postback-macros-for-ad-networks">高级隐私模板</Anchor>发送回传 |  |
| 与该渠道分享<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">汇总和匿名数据</Anchor>，即不分享用户级别的数据（设备ID）。 |  |

#### 通用设置

**Awin广告主ID**

添加您的Awin商家ID。

> 📘 **注意**
>
> 如果您有多个商家ID，请连接主要的一个。

#### 默认回传

安装的回调仅发送给此合作伙伴。

#### 应用内事件设置

**Awin广告主ID**

添加您的Awin商家ID。

#### 应用内事件回传

将回传中的应用内事件映射到Amazon Ads平台中的对应事件：

1. 打开**应用内事件回传**开关。
2. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。下表列出了必须配置的字段：

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。<br />**提示**：如果下拉菜单中没有您要查看的事件：<ul><li>请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。</li><li>在**AppsFlyer事件**中输入该事件的名称，然后点击**创建自定义事件**。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">自定义事件映射</Anchor>。</li></ul> |
| **渠道映射事件** | 渠道侧为每个事件定义的专属名称或ID。映射配置包括以下几种：<ul><li>**文本字段：** 从渠道处获取相应的事件ID。</li><li>**下拉菜单：** 选择最合适的AppsFlyer预定义事件。</li><li>**按原样**：按原样发送事件，不进行名称映射。</li></ul> |
| **事件来源** | **仅该合作渠道：** 仅该合作渠道：仅回传归因到该渠道的事件，也就是说完成这些事件的用户来自该渠道。 |
| **回传内容** | <ul><li>**不发送值与收入（默认）**：仅发送事件本身，不带任何事件值。</li><li>**发送值与收入**：发送所有事件参数，**包括**收入（若有）。</li><li>**仅发送值：** 发送**除**收入以外的所有参数。</li></ul> |

3. 【可选】点击**添加条件**<Image alt="onditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />图标，<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">设置事件的回传条件</Anchor>。
4. 设置**应用内事件回传窗口**（如有需要）。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">应用内事件回传窗口配置</Anchor>。
5. 点击**保存对接**。
6. 【可选】您可以在保存对接后留在配置页面，将其他应用也对接到该渠道：
   1. 点击页面左上角渠道名称下方的应用名称，打开应用列表。
   2. 在下拉菜单中选择一个其他应用。
   3. 为选定应用完成<Anchor target="_blank" href="/marketers/zh/docs/amazon-ads-campaign-configuration#integration-tab">对接流程</Anchor>。

> 📘 **注意事项**
>
> 仅适用于iOS应用：仅适用于iOS应用：通过回传和<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">报告</Anchor>与共享渠道数据时，您对这些数据的控制范围取决于**高级隐私模式（用于iOS14.5+）**<Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-advanced-srn-integration-setup#高级隐私保护">的启用状态</Anchor>：

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

生成并保存归因链接，然后将其发送到该渠道，使得相关流量可以被归因到具体的广告系列、广告组或单个广告，UA和再营销广告都在归因范围内。您也可以通过单平台链接或<Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink</Anchor>链接来实现归因。 详情请见归因链接结构和参数<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">。</Anchor> 请按照相关说明生成归因链接。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

Awin没有可用的成本数据。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

X Ads的对接不支持广告收入数据。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

您可以在这个板块中选择需要向Snapchat开放的数据权限，以便其提供各种功能。

> 📘 **注意**
>
> * 请注意，即使您<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">停用</Anchor>了这个对接，但只要其权限开关处于打开状态，相关权限就仍向Amazon Ads开放。
> * 进一步了解与<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">授权</Anchor>相关的信息。

</Accordion>

## 使用OneLink进行深度链接和延迟深度链接

AWIN会将其平台上使用的任何链接进行包装，以便向客户提供分析数据。这意味着链接将在将用户发送到最终目的地之前重定向到AWIN的网站。<Anchor target="_blank" href="https://www.appsflyer.com/blog/mobile-marketing/universal-links-app-links/#:~:text=%231%3A%20Link%20wrapping%20and%20Universal%20Links">了解更多关于链接包装的信息</Anchor>。  
AWIN作为一个平台支持URI方案，但**不支持**处理iOS通用链接和Android应用链接的深度链接方法。这适用于AWIN中使用的任何链接。

通过AWIN使用OneLink进行深度链接：

* <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">设置您的 OneLink URL 和 URI 方案</Anchor>

> 📘 **注意**
>
> 对于 iOS 应用，请在 OneLink URL 上使用 `af_force_deeplink=true` 参数来激活深度链接 <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">URI 方案</Anchor>.

<div data-zendesk-anchors="activate-partner=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 01H88VAJH3B5ESK12D3ATMMVZ8=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 setting-up-amazon-dsp-integration=%E8%AE%BE%E7%BD%AEawin 01H88VAJH3VENKYVRQY5RXN63P=%E8%AE%BE%E7%BD%AEawin 01H88VAJH3BYZSXQGGZZJQ9N0C=%E6%B3%A8%E6%84%8F prerequisite=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01HFPEEW4FXS9AFQTTEF2ZBDZW=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93-1 01H88VAJH34GP7FK1KTJGRDPM7=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93-1 advanced-privacy=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 01H88VAJH3G5FAR7RRNDEPNGME=%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE 01H88VAJH3F2FJK5YP3M2V7RWD=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01K4VVB00RYB0XRANWQ29M6P36=%E6%B3%A8%E6%84%8F-1 default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 01H88VAJH3WE9Z0971WMBRBJRS=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-event-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01HA77JYAR06HA5FZGSRQJATHF=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE inapp-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H88VAJH3AS37MVF75GANWX4B=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H88VAJH36MYZ9W1YPWA92Z1Z=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%E6%B3%A8%E6%84%8F-2 deep-linking-and-deferred-deep-linking-using-onelink=%E4%BD%BF%E7%94%A8onelink%E8%BF%9B%E8%A1%8C%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%92%8C%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01HA77Q9RWZ3FRE5KEN854ZZ78=%E4%BD%BF%E7%94%A8onelink%E8%BF%9B%E8%A1%8C%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%92%8C%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01HA78QWQVXEWHPEQE6XWBB64M=%E6%B3%A8%E6%84%8F-3" />

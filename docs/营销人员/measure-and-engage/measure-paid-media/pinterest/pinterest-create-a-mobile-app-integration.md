---
title: Pinterest投放配置
metadata:
  keywords:
    - Pinterest
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
  created_at: '2016-11-09T12:51:03Z'
  edited_at: '2026-10-14T09:59:22Z'
  id: 216912786
  locale: zh-cn
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/zh-cn/articles/216912786
---
> **概要：** 作为AppsFlyer的对接渠道，是博客作者和品牌的重要流量来源。Pinterest支持点击归因和浏览归因，同时提供基于点击的再营销归因，相关数据可通过AppsFlyer记录。

<div id="note" />

> 📘 **注意**
>
> * 自2021年6月起，Pinterest不再支持CPI广告。因此，AppsFlyer不再向Pinterest发送激活回传。
> * 接受Pinterest广告条款后，您还需在<Anchor target="_blank" href="https://ads.pinterest.com/terms/app_install/">这里</Anchor>接受Pinterest的移动衡量条款和条件。
> * Pinterest要求归因服务商在应用激活发生的6个月后删除相关用户的设备级别数据。6个月后用户产生的事件将被视为自然行为，但历史汇总数据不受影响。
> * 自2023年9月4日起，Pinterest要求归因提供商<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions#媒体渠道数据限制">对原始数据报告中某些字段的可用性进行限制</Anchor>，以保护用户隐私并满足合规要求。

<div id="set-up-pinterest" />

## 设置Pinterest对接

**前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作**> **Partner Marketplace**。  
   **修改方式**：从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索并选择**Pinterest**。
3. 点击**设置对接**。界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开 <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">（启用）</Anchor> 状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

Pinterest的配置窗口中有以下4个选项卡：渠道对接、归因链接、成本和授权。点击下方了解各部分的配置信息。

请点击<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">此处</Anchor>查看渠道配置页的标头（Header）示例。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

<div id="activate-partner" />

### 启用渠道

请在首次访问该页面时打开**启用该渠道**开关，然后就可以设置对接了。在您与该渠道合作期间，请确保该开关总是处于打开状态。  
有关渠道激活的详细说明请参见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。

<div id="general-settings" />

### 通用设置

以下是Pinterest对接选项卡的通用设置。

**启用浏览型归因**

如需获取来自Pinterest的浏览型归因，请打开此选项。您可以使用归因链接选项卡中对应的滑块来调整浏览回溯窗口。

<div id="legacy-set-tag-id" />

<div id="in-app-events-settings" />

<div id="including" />

<div id="to-users-from" />

<div id="partner-event-name" />

<div id="appsflyer-event-name" />

<div id="in-app-event-postbacks" />

### 应用内事件设置

您可以在这个板块中设置AppsFlyer事件与Pinterest之间的回传映射。

**Tag ID**

如需向Pinterest发送应用内事件回传，则必须输入Tag ID。如果您没有Tag ID，请从Pinterest获取。

**如何获取Tag ID并设置应用内事件回传**：

1. 在您的Pinterest企业账户中，进入**广告**> **转化**并复制**Tag ID**。  
   如无可用标签，请点击**创建标签**并完成创建流程。复制新标签。  
   **请注意**：仅有事件回传需Tag ID。
2. 在AppsFlyer的Pinterest对接设置中，下滑至**应用内事件设置** 并输入Pinterest Tag ID。
3. 打开**应用内事件回传**开关。
4. 设置应用内事件回传窗口。
5. 选择事件的回传设置和映射。
6.
   | 参数名称 | 说明 |
   | --- | --- |
   | **AppsFlyer事件名称** | 即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。  <br />**提示**：如果列表中没有您要找的事件，请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。 |
   | **渠道事件名称** | Pinterest平台中各事件的专属名称或ID。  <br />从Pinterest获取相应的事件ID，并在文字段中进行设置。 |
   | **事件来源** | **仅该合作渠道**：仅回传由该渠道带来的用户所产生的事件。  <br />**所有媒体渠道，包括自然流量**：向该渠道回传所有用户的事件。 |
   | **包含数据** | 请选择是否将事件收入或参数值回传给该渠道。<br /><br />仅发送值—向该渠道发送富应用内事件中除收入以外的所有参数（收入参数以**af\_revenue**表达）。否则，AppsFlyer将发送所有参数，包括收入值（若有）。 |

7. 点击**添加事件**，将SDK事件添加到列表中。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

生成并保存归因链接，然后将其发送到该渠道，使得相关流量可以被归因到具体的广告系列、广告组或单个广告，UA和再营销广告都在归因范围内。您也可以通过单平台链接或OneLink链接来实现归因。  
详情请见<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">归因链接结构和参数</Anchor>。

请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">相关说明</Anchor>**生成归因链接**。

<div id="attribution-link-for-retargeting-campaign" />

#### 用于再营销广告的归因链接

Pinterest建议广告主为不同操作系统单独设置再营销广告归因链接。选择**使用单一平台链接**选项，并在再营销归因链接中添加必要参数。

<div id="deep-link-url" />

#### 深度链接URL

<div id="note-1" />

> 📘 **注意**
>
> 要实现Pin内跳转，请确保您的应用已被Pinterest加入白名单。
> 请联系您的Pinterest客户经理，或发送邮件至[apps@pinterest.com](mailto:apps@pinterest.com)申请加入。

如果该链接旨在将用户深度链接到应用中的某个特定活动，请使用此字段。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

配置成本对接后，请勿修改任何正在投放中的广告系列、广告组或广告名称，也不要在广告名称中使用动态宏，避免出现数据缺失或成本偏差。

<div id="enabling-and-testing-pinterest-integration" />

### 启用和测试Pinterest对接

AppsFlyer通过API获取成本信息。详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">广告平台成本对接表</Anchor>，其中详细说明了适用维度、指标和功能。**请注意**：您需要购买ROI360才能获得成本数据。

**成本API的启用方式如下**：

* 请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">对接指南</Anchor>进行操作。

<div id="cost-data-sync-status" />

### 成本数据同步状态

<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">您可以在成本（及广告收入）对接状态面板或单独的广告平台面板中查看AppsFlyer最近一次获取匹配成本数据的时间以及</Anchor> API状态。

<div id="stop-pinterest-cost-sync" />

### 停止成本同步

**请按以下步骤解除账户绑定：**

* <Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">在行动栏中，将鼠标悬停在账户上，点击***删除连接***</Anchor>。连接删除后，AppsFlyer将不再接收成本数据，但不会影响历史记录。

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

该合渠道不支持广告收入数据。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

在该选项卡中，您可以为Pinterest开放所需权限。请注意：即使您停用了Pinterest归因，仍可以使用授权选项卡向Pinterest开放各类权限。

具体可开放的权限请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">此文档</Anchor>。

</Accordion>

</Accordion>

<div id="troubleshooting" />

## 问题排查

成本标签错误信息：*无匹配的数据*可能是因为您连接的Pinterest账户与应用不匹配，未能找到相关数据。请尝试使用其他Pinterest凭据登录并重新连接。

<div data-zendesk-anchors="h_01H95QTA3ZZ9GJW9EN1VZ01TH2=%E6%B3%A8%E6%84%8F set-up-pinterest=%E8%AE%BE%E7%BD%AEpinterest%E5%AF%B9%E6%8E%A5 h_01H95QTA3Z5HXW39AHAF8FMFWH=%E8%AE%BE%E7%BD%AEpinterest%E5%AF%B9%E6%8E%A5 h_01H95QTA3ZNQWBRA86E6TRQ46Y=integration-tab activate-partner=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01H95QTA3ZGEM34HY1A7NC8NX7=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01H95QTA3Z0NW9V51D8J7MHEX0=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE inapp-events-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01H95QTA3ZWSF0JYZ9D4HEB4A4=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01H95QTA3ZT7PVGAJW5AKPC186=attribution-link-tab attribution-link-for-retargeting-campaigns=%E7%94%A8%E4%BA%8E%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E7%9A%84%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01H95QTA3ZPQZ422AB2JBZAS07=%E7%94%A8%E4%BA%8E%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E7%9A%84%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 deep-link-url=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5url h_01H95QTA3ZT23CYTCE2V3728MD=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5url h_01H95QTA3ZYHQED2T5B2FA5PV8=%E6%B3%A8%E6%84%8F-1 h_01H95QTA3Z3XJDM5YRXFK7DA0E=cost-tab enabling-and-testing-pinterest-integration=%E5%90%AF%E7%94%A8%E5%92%8C%E6%B5%8B%E8%AF%95pinterest%E5%AF%B9%E6%8E%A5 h_01H95QTA3ZZ56R8EZBJY1ESX5W=%E5%90%AF%E7%94%A8%E5%92%8C%E6%B5%8B%E8%AF%95pinterest%E5%AF%B9%E6%8E%A5 cost-data-sync-status=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E5%90%8C%E6%AD%A5%E7%8A%B6%E6%80%81 h_01H95QTA3ZST8WS3TAR79H06FM=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E5%90%8C%E6%AD%A5%E7%8A%B6%E6%80%81 stop-pinterest-cost-sync=%E5%81%9C%E6%AD%A2%E6%88%90%E6%9C%AC%E5%90%8C%E6%AD%A5 h_01H95QTA3ZFCJ82E3YDMP7S716=%E5%81%9C%E6%AD%A2%E6%88%90%E6%9C%AC%E5%90%8C%E6%AD%A5 h_01H95QTA3ZM2REWR2A5DHK1DSA=ad-revenue-tab h_01H95QTA3ZM4WPHV3MB00WZXSB=permissions-tab troubleshooting=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 h_01H95QTA3ZP20DSJQGY4QQX0Z7=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5" />

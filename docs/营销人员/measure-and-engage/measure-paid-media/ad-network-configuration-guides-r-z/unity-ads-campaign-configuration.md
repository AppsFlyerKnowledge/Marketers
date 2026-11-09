---
title: Unity Ads投放配置
metadata:
  keywords:
    - Unity Ads
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
  created_at: '2016-03-06T10:05:52Z'
  edited_at: '2026-10-14T10:13:05Z'
  id: 208005086
  locale: zh-cn
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/zh-cn/articles/208005086
---
> **概要：** 概要：Unity Ads是iOS和安卓应用的视频广告平台，也是AppsFlyer的对接渠道之一，除了点击型移动归因外，Unity Ads还支持成本、广告收入和浏览型归因，您可以通过AppsFlyer记录相关的数据。

请按以下步骤针对您在Unity Ads上投放的广告配置对接。

<div id="setting-up-unity-ads" />

## 启用Unity Ads对接

**前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式**：从AppsFlyer面板左侧的菜单栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**， 界面会跳转到对接设置页。
4. 在**渠道对接**选项卡中，打开**启用该渠道**开关。  
   **请注意：在您与该渠道合作期间，请确保该开关总是处于打开（即**启用/strong>）状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

渠道对接、归因链接、成本、广告收入和授权。下文分小节介绍了各部分的配置信息。

如需进一步了合作伙伴配置页面中各选项卡的详细说明，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">此文档</Anchor>。

> 👍 **提示**
>
> * 对接页面中的<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#d-general-settings">通用设置</Anchor>是广告主**必须**为所有合作渠道都配置的内容。
> * 其他部分的流程都是说明性的或**可选的**。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

<div id="activate-partners" />

### 启用渠道

请在首次访问该页面时打开**启用该渠道**开关，然后就可以设置对接了。在您与Unity Ads合作期间，请确保该开关总是处于打开状态。  
有关启用渠道的详细说明请参见<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">此文档</Anchor>。

<div id="general-settings" />

### 通用设置

**向Unity发送设备ID（Advertising ID）**

渠道对接选项卡顶部的提示中说明了Unity Ads要求每次向其发送激活时都带有设备ID。该信息是自动发送的，广告主侧无需进行任何操作。

Unity\_msc\_new\_2.png

**Unity Ads Game ID**

Unity Ads要求广告主使用其专属的Game ID与AppsFlyer进行对接。如果您还不知道您的Game ID，请在Unity Ads后台查看该信息，也可以在上传游戏后进入**Apps** > **Campaigns**查看该信，如下图所示。

<Image align="center" alt="" src="https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png" />

Unity Ads平台中每个账户下的各个应用只有一个对应的Unity Ads Game ID（同一个应用在广告主账户和代理账户下会有不同的Game ID）。如果您在Unity Ads平台上有多个账户，不能使用不同的Game ID来投放同一个应用的广告。

**启用展示归因**

打开这个开关后，AppsFlyer就会将浏览型激活归因到Unity Ads。您可以使用归因链接选项卡中对应的滑块来调整浏览回溯窗口。

Unity\_ads\_msc\_new\_3.png

<div id="default-postbacks" />

### 默认回传

<Image align="center" alt="Screen_Shot_2022-07-28_at_13.07.25.png" src="https://files.readme.io/a571ddc49e490373b34144e34626a18c6c18908cec3345cd7ac70c49aa855c05-7975491293329.png" />

您可以在这个板块中设置可用回传的事件来源：

* **仅该合作渠道**：仅回传由Unity Ads带来的用户所产生的事件。
* **所有媒体渠道，包括自然流量**：向Unity Ads回传所有用户的事件。

<div id="note" />

> 📘 **注意**
>
> 由于Unity Ads支持所有类型的激活归因，因此该平台更希望广告主向其回传所有来源的全部新增激活，并建议您在对接配置的“事件来源”一栏选择**所有媒体渠道，包括自然流量**。

<div id="in-app-events-settings" />

### 应用内事件设置

通过回传将AppsFlyer事件映射到渠道。启用回传后，被拦截的应用内事件（被Protect360屏蔽的事件或未通过验证的事件）也会被一并发送。

<Image align="center" alt="" src="https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png" />

<div id="important" />

<div id="to-configure-in-app-event-postbacks" />

#### 请按以下步骤配置应用内事件回传：

1. 输入**game\_id**。请确保您输入的game\_id正确无误，且与激活归因中使用的ID一致。
2. 打开**应用内事件回传**开关。
3. 设置**应用内事件回传窗口**（如有需要）。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">应用内事件回传窗口配置</Anchor>。
4. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。
5. 请配置以下参数：

| 参数名称 | 说明 |
| --- | --- |
| AppsFlyer事件： | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。<br />**提示**：如果下拉菜单中没有您要查看的事件：<ul><li>请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。</li><li>在**AppsFlyer事件**中输入该事件的名称，然后点击**创建自定义事件**。详情请见自定义事件映射。</li></ul> |
| **渠道映射事件** | 渠道侧为每个事件定义的专属名称或ID。映射配置包括以下几种：<ul><li>**文本字段：** 从渠道处获取相应的事件ID。</li><li>**下拉菜单：** 选择最合适的AppsFlyer预定义事件。</li><li>**按原样**：按原样发送事件，不进行名称映射。</li></ul> |
| **事件来源** | 选择事件回传的范围：<ul><li>**仅该合作渠道**：仅回传归因到该渠道的事件。</li><li>**所有媒体渠道，包括自然流量**：回传归因到任何渠道以及自然量的事件。</li></ul> |
| **回传内容** | <ul><li>**无数据（默认）**：仅发送事件本身，不带事件值</li><li>**值和收入** ：发送所有事件参数，**包括**收入（若有）。</li><li>**仅发送值：** 发送**除**收入以外的所有参数。</li></ul> |

<div id="note-1" />

> 📘 **注意**
>
> 您可以向Unity Ads发送<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">广告收入回传</Anchor>，以便Unity侧根据相关的广告收入数据优化投放：
>
> * **AppsFlyer事件名称：** af\_ad\_revenue
> * **渠道映射事件名称**：ad\_revenue

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

生成并保存归因链接，然后将其发送到该渠道，使得相关流量可以被归因到具体的广告系列、广告组或单个广告，UA和再营销广告都在归因范围内。归因可以通过单平台链接或OneLink链接来实现。  
详情请见<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">归因链接结构和参数</Anchor>说明。

请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">相关说明</Anchor>**生成归因链接**。

**请注意：**

* 如果某个安卓应用的目标人群涉及儿童，Unity会发送全部为零的广告ID。
* 详情请见Unity Ads对点击和浏览的定义。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

AppsFlyer通过API获取成本信息。详情请见广告平台成本对接表，其中详细说明了适用维度、指标和功能。

**请注意**：

* 您需要购买ROI360才能获得成本数据。
* 不支持通过点击或API上报代理成本。广告主可以通过广告消耗数据上传来发送代理成本数据。

**成本API的启用方式如下**：

* 请按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">对接指南</Anchor>进行操作。  
  **请注意**：否则会影响成本数据的拉取。

<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">您可以在成本（及广告收入）对接状态面板或单独的广告平台面板中查看AppsFlyer最近一次获取匹配成本数据的时间以及</Anchor> API状态。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

本节内容适用于广告发布平台。向用户展示合作伙伴的广告时，广告发布平台需要衡量不同来源的用户与广告的互动情况，从而判断哪个用户来源最有价值。

**请按以下方式启用广告收入API**：

* 请按照<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">对接指南</Anchor>进行操作。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

您可以在授权选项卡中为Unity Ads开放某些操作的权限。请注意：即使您停用了Unity Ads的归因，授权选项卡仍然有效，可以用于给Unity Ads授权。  
具体可开放的权限请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">此文档</Anchor>。

</Accordion>

</Accordion>

<div data-zendesk-anchors="setting-up-unity-ads=%E5%90%AF%E7%94%A8unity-ads%E5%AF%B9%E6%8E%A5 h_01HAPVZ510GTJRY1NXE0T3SMR6=%E5%90%AF%E7%94%A8unity-ads%E5%AF%B9%E6%8E%A5 h_01HAPVZ5109NKD8GHD36EDN810=%E6%8F%90%E7%A4%BA h_01HAPVZ510KPB0HQS9X6R4BCWT=integration-tab activate-partners=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01HAPVZ510BGQ4KZ3S6ZP0QRE8=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01HAPVZ510EZ3HKJQVPMKHV5FH=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HAPVZ511MRQXKPC78HR61X9P=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01HAPVZ511CCXS93Y714STGQ67=%E6%B3%A8%E6%84%8F inapp-events-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01HAPVZ511CJ6JP49HYG9T6RPF=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE to-configure-inapp-event-postbacks=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%AD%A5%E9%AA%A4%E9%85%8D%E7%BD%AE%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01HAPVZ511RMEVNASSTJNXKCJG=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%AD%A5%E9%AA%A4%E9%85%8D%E7%BD%AE%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01HAPVZ511AV30DEKMZ0YB5ZBD=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%AD%A5%E9%AA%A4%E9%85%8D%E7%BD%AE%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 h_01HAPVZ511PC45Q5FEXQMZ4MFC=%E6%B3%A8%E6%84%8F-1 h_01HAPVZ5110QVYGGCGQDHRJEQM=attribution-link-tab h_01HAPVZ511DSKFAKKNWTKV9522=cost-tab h_01HAPVZ5111WPRRMPF6GZJTRJS=ad-revenue-tab h_01HAPVZ511RBNY3HHSHJHJDPWG=permissions-tab" />

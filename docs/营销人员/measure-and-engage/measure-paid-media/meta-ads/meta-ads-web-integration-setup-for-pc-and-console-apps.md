---
title: PC和主机端应用的Meta Web对接设置
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-09-20T09:54:52Z'
  edited_at: '2026-10-14T10:07:44Z'
  id: 18704273772689
  locale: zh-cn
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/zh-cn/articles/18704273772689
---
> **概要：** 本文说明了PC和主机端应用通过AppsFlyer与Meta Web对接的方式，并介绍了Meta Web中的投放设置方式。

> 🚧 **重要提示！**
>
> 此对接仅适用于PC或主机端的应用，包括Steam、Epic及PC端原生应用。如需了解适用于移动端应用的对接，请参阅<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-integration-setup">Meta ads对接设置</Anchor>说明。

## 速览

本文针对使用AppsFlyer的PC和主机端应用，提供了Meta Web对接的设置和使用说明及其相关步骤，其中包含以下信息；

* [在AppsFlyer中启用Meta Web对接](#在appsflyer后台启用meta-web)。
* [在AppsFlyer中设置Meta Web对接](#在appsflyer中设置meta-web对接)。
* [在Meta中为相关PC和主机端应用设置广告投放](/docs/meta-ads-web-integration-setup-for-pc-and-console-apps#在meta-web中为相关pc和主机端应用设置广告投放)。

### 前期准备

在启用Meta Web对接前，请确保您已在[Meta Business Manager](https://www.facebook.com/business/help/1710077379203657?id=180505742745347)中开设了企业账户。

## 在AppsFlyer后台启用Meta Web

**请按以下步骤启用该渠道：**

1. 在AppsFlyer面板的左侧菜单栏中点击**协作** > **Partner Marketplace**。
2. 搜索并选择**Meta Web**。
3. 点击**设置对接**，然后界面会跳转到**活跃对接**设置页面。
4. 在**渠道对接**选项卡中，打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开（即<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">启用</Anchor>）状态。
5. 参考下文说明，根据您的具体需求在相关选项卡中完成各项配置。

## 在AppsFlyer中设置Meta Web对接

这部分对接设置中包含Meta Web的回传配置。配置Meta Web（metaweb\_int）对接后，广告主可以使用Meta ads提供的一个Conversions API工具从其**PC和主机端应用**直接向Meta服务器发送数据。这类数据包括用户在非移动端（包括网页和应用）完成的购买、注册等等各种转化行为。Meta ads会使用这些数据来优化广告的定向投放，衡量广告效果并创建用于再营销的自定义人群包。

Meta Web对接仅支持发送激活和应用内事件的回传。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

**渠道对接**选项卡中包括以下几个部分。

#### 启用渠道

在配置对接之前，必须先打开**启用该渠道**开关。

#### 通用设置

* **Pixel ID：** 输入相关的Pixe ID。您可以从Meta ads Manager后台获取该信息，具体方式如下：
  1. 在<Anchor target="_blank" href="https://www.facebook.com/ads/manager">Ads manager</Anchor>侧边栏菜单中，向下滚动到**All tools**> **Events Manager**。   
     **请注意：** 请确保您在右上角的下拉菜单中选择的业务（Business）正确无误。
  2. 从**Events Manager**侧边栏菜单中选择**Data sources**。您会看到一个pixel列表。如果您选定的业务尚无pixel，可以在该窗口中创建一个pixel。
  3. 复制相关pixel名称下方的pixel ID，并将其粘贴到AppsFlyer后台对接页面的Pixel ID字段中。  
     <Image alt="pixel id3.png" src="https://files.readme.io/77969160b04357d056f2eee435a61314b95225f43e03cb31dd21a80dceef0dae-20748699506193.png" width="283px" />
* **Access token（访问令牌）：** 输入相关的token。您可以按照[这里的操作说明](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)来获取此信息。
* **限制Meta ads对用户个人信息的使用（CCPA）：** 打开此开关可确保数据的使用方式符合相关的<Anchor target="_blank" href="/marketers/zh/docs/send-opendsr-api-requests">数据保护法</Anchor>规定。  
  **请注意：** 在CCPA隐私条例合规的情况下，来自美国加州Meta ads用户的数据会受到限制。

#### 启用浏览型归因

AppsFlyer支持通过启用<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">智能脚本</Anchor>或<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">智能横幅</Anchor>的落地页，基于概率性模型（PMOD）对Meta Web广告系列进行浏览型归因。因此，AppsFlyer能够将用户浏览广告带来的应用激活归因至Meta，即便用户未直接点击广告，也能在跨平台环境中识别。

当用户点击Meta Web广告并进入<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">智能脚本</Anchor>或<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">智能横幅</Anchor>落地页时，AppsFlyer可以将该活动与后续的应用安装进行匹配。若可用，AppsFlyer还会在给Meta的回传中包含`fbclid`，以提高归因精准度。

**启用浏览型归因**

1. 在AppsFlyer中，从侧边栏打开**活跃对接**> **Meta web ads**。
2. 在**对接**选项卡中，下滑到**激活归因**部分。
3. 打开**浏览型激活归因**开关。
4. **[可选]** 开启**跨平台归因具有同等优先级**并设置回溯窗口。有关更多信息，请参见<Anchor target="_blank" href="/marketers/zh/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">为跨平台展示启用同等优先级</Anchor>。
5. 打开**归因链接**选项卡。
6. 下滑到**浏览型归因**部分并设置**浏览归因回溯窗口**（最长24小时）。
7. 点击**保存对接**以应用您的设置。

#### 默认回传

激活回传自动发送到Meta Web，不会回传给其他任何渠道。在**用户来源**字段中，选择以下选项之一：

* **仅此合作伙伴**以确保应用内事件回调仅针对来自此合作伙伴的用户执行的事件。
* <strong>所有媒体来源，包括自然流量，</strong>确保应用内事件回调针对来自此合作伙伴、其他合作伙伴或自然来源的用户执行的事件。

#### 应用内事件回传

将回传中的应用内事件映射到Meta Web中的对应事件。您可以在<Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">Meta Events Manager</Anchor>中查看这些事件，具体方式如下：

1. 打开**应用内事件回传**开关。
2. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。下表列出了必须配置的字段：

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。<ul><li>点击**添加项目**，输入事件名称，然后点击![check.png](https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png)。</li></ul> |
| **渠道映射事件** | Meta Web为每个事件定义的专属名称或ID。<ul><li>从下拉菜单中选择最合适的预定义渠道事件，或选择“自定义”。</li></ul> |
| **事件来源** | <ul><li>**仅此合作伙伴**以确保应用内事件回调仅针对来自此合作伙伴的用户执行的事件。</li><li><strong>所有媒体来源，包括自然流量，</strong>确保应用内事件回调针对来自此合作伙伴、其他合作伙伴或自然来源的用户执行的事件。</li></ul> |
| **回传内容** | **发送值与收入：** 在回传中发送所有事件参数，包括收入（若有）。 |

3. 【可选】点击**添加条件**<Image alt="onditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />图标，<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">设置事件的回传条件</Anchor>。
4. 设置**应用内事件回传窗口**（如有需要）。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">应用内事件回传窗口配置</Anchor>。
5. 点击**保存对接**。
6. 【可选】您可以在保存对接后留在配置页面，将其他应用也对接到该渠道：
   1. 点击页面左上角渠道名称下方的应用名称，打开应用列表。
   2. 在下拉菜单中选择一个其他应用。
   3. 为选定应用完成对接流程。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

目前尚不支持从AppsFlyer后台生成归因链接。但您可以使用带有智能脚本的跨平台落地页，或为相关应用创建一条直接归因链接（见下表）。

| 可选方案 | 可用操作 | 人员 |
| --- | --- | --- |
| 跨平台落地页 | **推荐**：如果您要推广的应用在Epic和Steam等多个平台中上架，建议使用这种方式。<br /><br /><Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">进一步了解跨平台落地页</Anchor><br /><br /><Anchor target="_blank" href="/marketers/zh/docs/cross-platform-landing-pages-with-smart-script">了解跨平台落地页的设置方式</Anchor><ul><li>请确保所有相关URL参数（即智能脚本要抓取的参数）都已添加到广告链接中。</li><li>请确保该脚本能从入链URL中抓取FBCLID，并将其添加到生成的链接中。也就是说，传出链接（即智能脚本生成的链接）中的`fbclid`参数必须映射到传入链接中`fbclid`参数。**请注意**：如需让AppsFlyer的原始数据报告呈现该数据，还必须将传入的参数`fbclid`映射到传出的参数之一`af_sub[1-5]`。</li><li>可选：使用Meta的动态URL宏，而非手动将参数值在代码中写死。<Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">详情请见此处说明。</Anchor></li></ul> | 营销人员（可能需要开发人员协助） |
| 直接归因链接 | 如果您要推广的应用仅在1个平台中上架，因而决定不使用跨平台落地页，可以创建直接归因链接，将其附在广告背后。<br /><br /><Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links">了解直接归因链接的创建方式</Anchor><ul><li>请务必在您的链接中添加下列参数：<ul><li>af\_media\_source</li><li>af\_campaign\_id</li><li>af\_r</li></ul></li></ul>用于Meta Web广告链接的模板如下：<br /><br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={encoded landing page and URL params}`<br /><br />用于Steam的Meta Web广告链接如下：`https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello`<br /><br />**请注意**：该模板中包含Meta支持的部分动态URL参数。您也可以手动使用实际值覆盖。<Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">进一步了解Meta动态URL参数</Anchor> | 营销人员 |

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

Meta Web的对接不支持成本数据。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

Meta Web的对接不支持广告收入数据。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

目前尚未向Meta Web开放权限。

</Accordion>

## 在Meta Web中为相关PC和主机端应用设置广告投放

**设置新的广告系列时请完成以下操作**：

* 选择一个投放目标（campaign objective）。建议您使用以下任一选项：
  * **Sales**：该选项能让Meta针对某个具体事件进行优化（比如您的主要KPI事件）。
  * **Traffic**：该选项能让Meta针对广告点击进行优化。建议您仅在没有其他KPI或其他KPI事件的流量太低时使用该选项。
  * **Custom**：适用于需要将某个自定义事件设置为投放目标的场景。**请注意：** 如需在Meta的面板中将自定义事件设置为投放目标，请先在AppsFlyer中配置该自定义事件。
* 将转化位置（conversion location）设置为**Website**。
* 为您的Facebook conversion pixel（转化追踪像素）命名时，请确保该名称与您在AppsFlyer Partner Marketplace中的metaweb\_int对接下输入的pixel ID一致。
* 设置广告的跳转终点时，请务必使用以下任一网页的URL：
  * 网站落地页（一个应用在多个平台中上架时建议使用该方式）
  * 商店URL（相关应用仅在一个平台的一个应用商店中上架时建议使用该方式）

## 查看网页到应用的归因数据

尽管基于网页的转化事件以原始`metaweb_int` PID发送到Meta，但它们在AppsFlyer仪表板和原始数据报告中以`Facebook Ads` PID报告。这适用于主要转化事件和转化辅助事件。

此统一报告视图让您在一个地方分析网页和应用活动的表现，包括完整的网页和移动成本报告。

### 在仪表板中查看

所有Meta网页到应用的归因在概览和活动仪表板下显示为`Facebook Ads`。这提供了跨平台活动结果的单一、综合视图。使用标准过滤器和细分来比较您的Meta广告数据中的应用和网页流量。

### 在原始数据和API报告中查看

* **原始数据导出和API响应**在Meta网页活动的`media_source`字段中包含`Facebook Ads` PID。要验证网页活动设置的详细信息，请参考显示`metaweb_int`作为创建网页活动时使用的PID的`original_url`字段。
* **回调报告**显示`metaweb_int`作为发送回调的原始媒体来源。

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 点击和展示（临时限制） | 针对PC和控制台应用的活动的点击和展示暂时无法从Meta SRN获取（`Facebook Ads`）。 |

<div data-zendesk-anchors="h_01HE2XD0FSY0QMJSKVC0FHHK5P=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA overview=%E9%80%9F%E8%A7%88 h_01HK4QHRJG6WTN9P6ZG83XQ6AY=%E9%80%9F%E8%A7%88 prerequisite=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01HFXV8HPGCRGYPEW0NPJ0NR0S=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 activate-partner=%E5%9C%A8appsflyer%E5%90%8E%E5%8F%B0%E5%90%AF%E7%94%A8meta-web h_01HFXV8HPH3N4DBKKTQE6DK7FK=%E5%9C%A8appsflyer%E5%90%8E%E5%8F%B0%E5%90%AF%E7%94%A8meta-web setting-up-metaweb-in-appsflyer=%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEmeta-web%E5%AF%B9%E6%8E%A5 01H88VAJH3VENKYVRQY5RXN63P=%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEmeta-web%E5%AF%B9%E6%8E%A5 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01HFXV8HPH6X92YETNAGZ910AV=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 transaction-id=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01HARQDVEDA206D0BBXBC6WEHH=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE enable-viewthrough-attribution=%E5%90%AF%E7%94%A8%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01ZXVWB1ZYKK4DP38QY1RMEY6M=%E5%90%AF%E7%94%A8%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0 default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 01H88VAJH3WE9Z0971WMBRBJRS=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H88VAJH3AS37MVF75GANWX4B=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab setting-up-campaigns-in-meta-web-for-pc-and-console-apps=%E5%9C%A8meta-web%E4%B8%AD%E4%B8%BA%E7%9B%B8%E5%85%B3pc%E5%92%8C%E4%B8%BB%E6%9C%BA%E7%AB%AF%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AE%E5%B9%BF%E5%91%8A%E6%8A%95%E6%94%BE h_01HK4S03KVAN99YKXTHAKCT420=%E5%9C%A8meta-web%E4%B8%AD%E4%B8%BA%E7%9B%B8%E5%85%B3pc%E5%92%8C%E4%B8%BB%E6%9C%BA%E7%AB%AF%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AE%E5%B9%BF%E5%91%8A%E6%8A%95%E6%94%BE meta%20view=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E5%88%B0%E5%BA%94%E7%94%A8%E7%9A%84%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE view-webtoapp-attribution-data-from-november-2-2025=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E5%88%B0%E5%BA%94%E7%94%A8%E7%9A%84%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01K88J8JFNEYBZNR18133NMRP9=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E5%88%B0%E5%BA%94%E7%94%A8%E7%9A%84%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE view-in-the-dashboard=%E5%9C%A8%E4%BB%AA%E8%A1%A8%E6%9D%BF%E4%B8%AD%E6%9F%A5%E7%9C%8B h_01K88J8JFNMHCVZ0C34E3D7AST=%E5%9C%A8%E4%BB%AA%E8%A1%A8%E6%9D%BF%E4%B8%AD%E6%9F%A5%E7%9C%8B view-in-raw-data-and-api-reports=%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%92%8Capi%E6%8A%A5%E5%91%8A%E4%B8%AD%E6%9F%A5%E7%9C%8B h_01K88J8JFN8W2572N92466YFZQ=%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%92%8Capi%E6%8A%A5%E5%91%8A%E4%B8%AD%E6%9F%A5%E7%9C%8B traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01KB503RDVWPSFBAPAPW4CNZXM=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />

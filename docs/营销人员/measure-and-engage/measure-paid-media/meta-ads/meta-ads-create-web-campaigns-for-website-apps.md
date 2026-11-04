---
title: 元广告——为网站应用创建网络广告系列
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-28T14:18:14Z'
  edited_at: '2026-10-14T10:00:41Z'
  id: 46172666260241
  locale: zh-cn
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/zh-cn/articles/46172666260241
---
> 概览：为您的网站应用设置 Meta Ads 集成，通过 Conversions API (CAPI) 向 Meta 发送网络转化信号，以便 Meta 可以优化广告定位并衡量广告系列效果。

<div id="overview" />

## 概览

AppsFlyer支持专用于网页广告的Meta Ads对接（`metaweb_int`），通过集成，您可以直接通过 Meta 的转化 API (CAPI) 报告归因和转化数据，然后 Meta 会使用这些数据来优化广告定位、衡量效果并构建自定义受众群体。

工作原理如下：当用户点击 Meta 广告并访问您的网站时，AppsFlyer 会捕获用户完成的任何转化事件（例如购买或注册），并通过 CAPI 将该信号发送给 Meta。Meta 利用这些数据来优化目标定位并评估广告活动效果。

<div id="see-also-1" />

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/web-performance-measurement-overview">AppsFlyer 网络归因分析 - 概述</Anchor>

<div id="note" />

> 📘 **注意**
>
> 当前 Meta Web 集成不支持向 CAPI 发送重新互动回传。

<div id="prerequisites" />

### 前期准备

启用Meta Web对接前，请先确保：

* 在 AppsFlyer 中设置的网站应用程序。详情请见：
  * <Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer#web">添加 Web 应用程序</Anchor>
  * <Anchor target="_blank" href="/marketers/zh/docs/configure-web-performance-measurement-settings">配置 AppsFlyer 网络归因设置</Anchor>
* <Anchor target="_blank" href="https://www.facebook.com/business/help/1710077379203657?id=180505742745347">Meta Business Manager 中的企业帐户</Anchor>。

<div id="set-up-meta-ads-web-campaigns-for-website-apps" />

## 为网站应用设置 Meta Ads 网络广告系列

该流程主要包含两个方面：1）配置Meta Web和Appsflyer之间的对接，以及2）在Meta和AppsFlyer两个平台上分别完成投放配置。请按顺序完成两部分。

* 第二部分：在AppsFlyer中设置Meta Web对接 （必须完成）
* 第二部分：在Meta Ads中设置AppsFlyer对接 （必须完成）

<div id="part-1-set-up-meta-ads-integration-in-appsflyer" />

## 第一部分：在AppsFlyer中设置Meta Web对接

请先在AppsFlyer后台启用Meta Web对接，并设置AppsFlyer向CAPI发送回传的方式。

<div id="step-1-activate-the-meta-ads-integration" />

<Accordion title="第1步：启用Meta Web对接">

请按以下方式启用Meta Web对接：

1. 在AppsFlyer面板的左侧菜单栏中点击**协作** > **Partner Marketplace**。
2. 搜索并选择Meta ads。
3. 点击**设置对接**，然后界面会跳转到活跃对接设置页面。
4. 在**渠道对接**选项卡中，打开**启用该渠道**开关。

   <div id="note-1" />

   > 📘 **注意**
   >
   > <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">在您与该渠道合作期间，请确保该开关总是处于打开（即启用）状态。</Anchor>

5. 填写**像素 ID**字段。要从 Meta Ads Manager 中检索您的像素 ​​ID：
   1. <span class="af-ol-a"></span>在<Anchor target="_blank" href="https://www.facebook.com/ads/manager">Ads manager</Anchor>侧边栏菜单中，向下滚动到**All tools**> **Events Manager**。

      <div id="note-2" />

      > 📘 **注意**
      >
      > 请确保您在右上角的下拉菜单中选择的业务（Business）正确无误。

   2. 从**Events Manager**侧边栏菜单中选择**Data sources**。您会看到一个pixel列表。如果您选定的业务尚无pixel，可以在该窗口中创建一个pixel。
   3. 复制像素名称下方显示的像素 ID，并将其粘贴到 AppsFlyer 的**像素 ID**字段中。
6. 填写**访问令牌**字段。您可以按照这里的说明来获取该token信息。
7. 打开<strong>限制Meta Ads对用户个人信息的使用（CCPA）</strong>开关，以确保数据的使用方式符合相关的<Anchor target="_blank" href="/marketers/zh/docs/send-opendsr-api-requests">数据保护法</Anchor>规定。

   <div id="note-3" />

   > 📘 **注意**
   >
   > CCPA隐私条例限制他人使用加州的用户所产生的数据，因此CCPA合规后，Meta Ads上这类用户的数据可用性有限。


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="第2步：应用内事件回传">

您可以通过将 AppsFlyer 事件映射到 Meta Ads 事件来定义 AppsFlyer 将哪些网络转化事件发送到 Meta Ads。这些回传信息可以在<Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">元事件管理器</Anchor>中查看。Meta 利用映射事件进行广告系列优化和报告。

应用内事件回传

1. 打开**应用内事件回传**开关。
2. 如有需要，设置应用内事件回发窗口。有关更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">应用内事件回发窗口配置</Anchor>。
3. 点击**添加事件**，将相关事件添加到列表中。
4. 在**AppsFlyer事件**一列，从下拉菜单中选择相关的事件名称。AppsFlyer 从您网站上集成的 Web SDK 或您发送给 AppsFlyer 的服务器到服务器 (S2S) 事件中接收事件名称。
5. 在**渠道映射事件**一列，从下拉菜单中选最合适的渠道侧预定义事件，或选择自定义事件（CUSTOM）。
6. 在 **“面向用户”** 列中，选择事件的发送选项：
   * **仅该合作渠道**：仅回传归因到Google Ads的事件。
   * **所有媒体渠道，包括自然流量**：回传所有带量渠道以及自然量的事件。
7. 在**包括**列中，选择是否将事件与其收入值一起发送。请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#回传内容">回传中包含的数据</Anchor>。

   <div id="note-5" />

   <div id="note-4" />

   <div id="important" />

   > 🚧 **重要提示！**
   >
   > 如果您设置的是购买事件，请将**包含**列设为**值和收入**。选择其他任何选项都会导致回发失败。

8. 【可选】点击**添加条件**图标，设置事件的<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">映射条件</Anchor>。
9. 点击**保存对接**。

</Accordion>

<div id="part-2-set-up-appsflyer-integration-in-meta-ads" />

## 第二部分：在Meta Ads中配置AppsFlyer对接

请在 Meta Ads Manager 中完成以下步骤。

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="第1步：设置投放类型、投放目标和转化目标">

1. 登入Meta Ads并创建一个广告系列。
2. 在**Campaign objective**部分中选择以下任一选项：
   * **Sales**：该选项能让Meta针对某个具体事件进行优化（比如您的主要KPI事件）。
   * **Traffic**：该选项能让Meta针对广告点击进行优化。仅当您没有其他 KPI 或其他 KPI 事件的数量太少时才使用此选项。
3. 【可选】要添加自定义目标，请执行以下操作：

   1. 在Meta Ads中选择一个要作为投放目标的自定义事件，并将其标记为转化行为（conversion action）。
   2. 进入AppsFlyer面板，在**Meta Web**对接页面中的**应用内事件**部分选择一个AppsFlyer事件，将其映射到渠道侧的自定义事件（在**渠道映射事件**一列中选择CUSTOM），并使用Meta Ads中的转化行为名称（conversion action）为其命名。

   <div id="note-6" />

   > 📘 **注意**
   >
   > 如需进一步了解Meta的投放目标（Campaign Objectives），请参阅<Anchor target="_blank" href="https://www.facebook.com/business/help/175683976191028">Meta提供的相关说明</Anchor>。

4. 将<strong>转化位置（conversion location）</strong>设置为**Website**。
5. 请确保**Pixel**字段的值与您在AppsFlyer中为Meta Web对接（`metaweb_int`）所配置的Pixel ID完全一致。如需进一步了解Meta Pixel，请参阅Meta提供的相关说明（需登录）。
6. 点击**Next**。

</Accordion>

<div id="step-2-set-destination-url" />

<Accordion title="第2步：设置目标网址（Destination URL）">

1. 在**Destination**下的**Website URL**部分中，输入相关URL，作为用户点击广告后访问的页面。iOS： 请执行以下任一操作：

   * 网站URL当您希望用户直接访问您的网站并完成网站转化事件（例如购买或注册）时，请使用您的网站 URL。
   * **AF 归属链接 (OneLink)** ：当您希望用户重定向到您的移动应用时，请使用 AF 归因链接；如果应用未安装，则回退到您的网站。当您的营销活动同时面向应用程序用户和网页用户时，这将非常有用。更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink 链接和体验</Anchor>。

   <div id="important-1" />

   > 🚧 **重要提示！**
   >
   > 在某些情况下，使用 AF 归属链接可能会导致错误。如果出现这种情况，请向您的 Meta 代表寻求解决方案，或者改用您的网站 URL 作为目标 URL。

2. 点击 **“构建 URL 参数”** 以向目标 URL 添加 URL 参数。
3. 在**Custom parameters**下点击**Add parameter**。
4. 将 AppsFlyer 参数映射到其 Meta 值，如下表所示：

| AF参数 | Meta映射值 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

生成的 URL 示例：

```http
https://www.example.com?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}
```

<div id="note-7" />

> 📘 **注意**
>
> 元数据自动添加`fbclid={{fbclid}}`当广告被点击时，跳转到目标网址。

<div id="tip" />

> 👍 **提示**
>
> 为了简化广告系列分析，请在广告系列名称中添加广告系列类型（网页或移动端）作为前缀或后缀，例如：`campaign-name_web` 。

<div id="see-also" />

> 📄 **另请参阅**
>
> * 有关构建包含所有相关参数的广告网址的最佳实践，请参阅<Anchor target="_blank" href="/marketers/zh/docs/about-traffic-source-resolution">“关于流量来源解析”</Anchor> 。

</Accordion>

<div id="step-3-select-tracked-events" />

<Accordion title="第3步：选择需要监测的事件（tracked events）">

使用 **“跟踪”** 部分选择广告所促进的转化事件。您可以通过<Anchor target="_blank" href="https://www.facebook.com/business/help/898185560232180?id=1205376682832142">活动管理器</Anchor>设置活动。

<div id="important-2" />

> 🚧 **重要提示！**
>
> 不要选择 **“应用事件”** 。这样做会导致 Meta 通过 SRN API 声称这些转化，从而可能导致报告和优化出现偏差。

</Accordion>

<div id="view-web-attribution-data" />

## 查看网络归因数据

以下是设置完成后查看归因数据时可以看到的内容：

* **原始数据导出和 API 响应**包括 Meta Web。`media_source` Meta 网络活动字段。
* 要验证网络营销活动设置详情，请检查以下内容：`original_url`显示字段`facebook_int`作为网络营销活动创建期间使用的 PID。

> 📘 **注意**
>
> 网站应用推广活动的仪表盘报告功能尚未推出。我们计划在未来的版本中推出统一的报告视图，让用户可以分析网络营销活动以及其他渠道的营销活动效果。

<div id="measure-web-attribution-data-with-web-cost" />

## 使用网络成本衡量网络归因数据

要在控制面板和<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">成本 ETL 报告</Anchor>中查看 Meta Ads 的网络归因数据和网络成本数据的完整性能视图，请确保您拥有<Anchor target="_blank" href="/marketers/zh/docs/roi360-onboarding-guide#roi360简介">ROI360 软件包</Anchor>，并完成以下设置：

1. 通过以下方式将成本连接到您的网站应用程序`facebook_int`（并非通过）`metaweb_int` ）从 **“成本”** 选项卡或 **“成本设置”** 页面。有关如何连接成本的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#启用cost-api">设置 ROI360 成本 API 以测量成本数据</Anchor>。
2. 请提供活动 ID（`af_c_id` ）在着陆页 URL 中。确保 URL 包含完整的广告系列层级结构，以便以最精细的级别查看与网络归因匹配的成本、点击次数和展示次数。

<div id="traits-and-limitations" />

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 点击和展示 | 网络广告活动的点击量和曝光量需要<Anchor target="_blank" href="/marketers/zh/docs/roi360-onboarding-guide">ROI360 订阅</Anchor>。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01KQA78RE9FRENQAK31Q641C0N=%E6%A6%82%E8%A7%88 h_01KQC27K5KWP3A6HMM2W7N3MVB=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85 h_01KQA78RE9F82ZBVF4YZHZTEEX=%E6%B3%A8%E6%84%8F prerequisites=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01KQA78RE93B09A9YH2FRB3XRR=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 set-up-meta-ads-web-campaigns=%E4%B8%BA%E7%BD%91%E7%AB%99%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AE-meta-ads-%E7%BD%91%E7%BB%9C%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 h_01KQA78RE9J681CJ8DQNWJC37H=%E4%B8%BA%E7%BD%91%E7%AB%99%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AE-meta-ads-%E7%BD%91%E7%BB%9C%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 part-1-set-up-meta-ads-integration-in-appsflyer=%E7%AC%AC%E4%B8%80%E9%83%A8%E5%88%86%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEmeta-web%E5%AF%B9%E6%8E%A5 h_01KQA78RE93JYCV2P0DDZC0A4B=%E7%AC%AC%E4%B8%80%E9%83%A8%E5%88%86%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEmeta-web%E5%AF%B9%E6%8E%A5 h_01KQA78RE94B1JSVJFWR1V9QE5=step-1-activate-the-meta-ads-integration h_01KQA78REA5VN1229F2J3QH794=%E6%B3%A8%E6%84%8F-1 h_01KQA78REANHAQ88N4MXWM832D=%E6%B3%A8%E6%84%8F-2 h_01KQA78REA08SNB0BKCJDJZ2R0=%E6%B3%A8%E6%84%8F-3 h_01KQA78REACR7QTMQWJMV6VJSF=step-2-set-inapp-event-postbacks h_01KQA78REA1EB5ZHX4HKJSW7ZD=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA part-2-set-up-appsflyer-integration-in-meta-ads=%E7%AC%AC%E4%BA%8C%E9%83%A8%E5%88%86%E5%9C%A8meta-ads%E4%B8%AD%E9%85%8D%E7%BD%AEappsflyer%E5%AF%B9%E6%8E%A5 h_01KQA78REAEZQPDSKZ0GRNKEJJ=%E7%AC%AC%E4%BA%8C%E9%83%A8%E5%88%86%E5%9C%A8meta-ads%E4%B8%AD%E9%85%8D%E7%BD%AEappsflyer%E5%AF%B9%E6%8E%A5 h_01KQA78REASX8JX1H37075WT82=step-1-set-the-campaign-type-objective-and-goals h_01KQA78REA5JZ44C4BE77JCHG8=%E6%B3%A8%E6%84%8F-4 h_01KQA78REAKBGQRC713FZ3J02P=step-2-set-destination-url h_01KQA78REAXZ1BFGC5BR75ZB5X=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 h_01KQA78REARWGQDCJ4KN3FM120=%E6%B3%A8%E6%84%8F-5 h_01KQA78REA7MZSG5JZ1XX2C65P=%E6%8F%90%E7%A4%BA h_01KQA78REA3ZW7W9M3VFSQASB6=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85-1 h_01KQA78REASTZH19CM58M5Z43R=step-3-select-tracked-events h_01KQA78REBHCR1AHA254BTFZC6=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2 view-web-attribution-data=%E6%9F%A5%E7%9C%8B%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01KQA78REBK1PWXNA1PM9118TA=%E6%9F%A5%E7%9C%8B%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01KQA78REBAW2SM5DRD68DP8W1=%E6%B3%A8%E6%84%8F-6 measure-web-attribution-data-with-web-cost=%E4%BD%BF%E7%94%A8%E7%BD%91%E7%BB%9C%E6%88%90%E6%9C%AC%E8%A1%A1%E9%87%8F%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01KNM00RR9TF8JRTJXWN23MF1S=%E4%BD%BF%E7%94%A8%E7%BD%91%E7%BB%9C%E6%88%90%E6%9C%AC%E8%A1%A1%E9%87%8F%E7%BD%91%E7%BB%9C%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01KQAE3JKMQ6ZEATDAEXBC4PT6=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />

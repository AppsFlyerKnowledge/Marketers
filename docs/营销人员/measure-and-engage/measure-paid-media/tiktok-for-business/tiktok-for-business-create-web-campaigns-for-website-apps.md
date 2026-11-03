---
title: TikTok商业版—为网站应用创建网络广告活动
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
  created_at: '2026-04-29T07:09:07Z'
  edited_at: '2026-10-14T10:00:37Z'
  id: 46191822292113
  locale: zh-cn
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/zh-cn/articles/46191822292113
---
> 概览：为您的网站应用设置TikTok Web Ads集成，通过事件API向TikTok发送网络转化信号。

## 概览

AppsFlyer支持与TikTok Web Ads（`tiktokweb_int`）的集成，用于网站应用广告活动，让您可以通过TikTok的事件API直接报告归因和转化数据。Meta可以利用这些数据来优化定向投放、衡量广告效果并打造自定义人群包。

其工作原理如下：当用户点击TikTok广告并访问您的网站，然后完成网站事件（例如，购买或注册）时，AppsFlyer通过事件API向TikTok发送转化信号。TikTok利用这些数据来优化广告定位和衡量广告活动的表现。

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/web-performance-measurement-overview">AppsFlyer网络归因 - 概述</Anchor>

> 🚧 **重要提示！**
>
> 目前，该集成不支持通过事件API发送重新参与的回调。

### 前期准备

在激活您的网站应用的TikTok Web Ads集成之前，请确保您已：

* 在AppsFlyer中设置了一个网站应用
* 在<Anchor target="_blank" href="https://getstarted.tiktok.com/grow-your-business-gb">TikTok广告管理平台</Anchor>中拥有一个商业账户

### 如何为您的网站应用设置TikTok Web Ads

设置过程包括定义TikTok Web Ads与AppsFlyer之间的集成，并在TikTok广告管理平台中配置广告活动。它包括以下部分：

* 第二部分：在AppsFlyer中设置Meta Web对接 （必须完成）
* 第二部分：在TikTok Web Ads中设置AppsFlyer集成（必需）

## 第一部分：在AppsFlyer中设置TikTok Web Ads集成

首先激活TikTok Web Ads集成，并设置AppsFlyer发送到事件API的回调。

<div id="1-activate-the-tiktok-ads-integration" />

<Accordion title="1.激活TikTok Web Ads集成">

要激活TikTok Web Ads集成：

1. 在AppsFlyer面板的左侧菜单栏中点击**协作** > **Partner Marketplace**。
2. 搜索**TikTok商业版 - 高级SRN**（或`tiktokweb_int`）并选择它。
3. 点击**设置对接**，然后界面会跳转到活跃对接设置页面。
4. 在**渠道对接**选项卡中，打开**启用该渠道**开关。在您与该渠道合作期间，请确保该开关总是处于打开状态。
5. **Pixel ID：输入相关的Pixe ID。您可以生成它或通过遵循<Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">TikTok文档</Anchor>中的说明从您的TikTok广告管理平台中检索它。**
6. Access token输入相关的token。要生成或检索它，请遵循相同的 <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">抖音文档</Anchor>。
7. **限制抖音网页广告对用户个人信息的使用（CCPA）：** 打开此开关可确保数据的使用方式符合相关的<Anchor target="_blank" href="/marketers/zh/docs/send-opendsr-api-requests">数据保护法</Anchor>规定。

> 📘 **注意**
>
> 启用CCPA合规性限制来自加利福尼亚州或美国其他敏感州的抖音网页广告用户的数据。

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2.应用内事件回传">

您可以通过将AppsFlyer事件映射到抖音网页广告事件来定义AppsFlyer发送到抖音广告的网页转化事件。这些回调可以在抖音广告管理器中查看，抖音使用映射的事件进行活动优化和报告。

应用内事件回传

1. 打开**应用内事件回传**开关。
2. 如有需要，请设置应用内事件回调窗口。在 <Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">应用内事件回调配置</Anchor> 中了解更多关于应用内事件回调窗口配置的信息。
3. 点击**添加事件**，将相关事件添加到列表中。
4. 在**AppsFlyer事件**一列，从下拉菜单中选择相关的事件名称。AppsFlyer通过您网站上集成的Web SDK或您发送给AppsFlyer的服务器到服务器（S2S）事件接收事件名称。
5. 在 **映射到合作伙伴事件** 列中，选择最合适的预定义合作伙伴事件。
6. 在 **来自用户** 列中，选择适当的选项：
   * **仅此合作伙伴**，仅发送归因于抖音网页广告的事件。
   * **所有媒体来源，包括自然流量**，发送所有事件，无论归因来源。
7. 在**包括**列中，选择是否将事件与其收入值一起发送。请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#回传内容">回传中包含的数据</Anchor>。
8. 【可选】点击**添加条件**图标，设置事件的<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">映射条件</Anchor>。
9. 点击**保存对接**。

> 📘 **注意**
>
> * 如果您设置的是购买事件，请将**包含**列设为**值和收入**。选择其他选项将导致回传失败。
> * 目前，仅购买事件支持包含收入。

</Accordion>

## 第二部分：在抖音网页广告中设置AppsFlyer集成。

在抖音广告管理器中完成以下步骤。

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1.设置投放类型、投放目标和转化目标">

您可以选择从AppsFlyer发送的任何预定义应用内事件作为您的活动目标。选择与您的网站转化目标一致的活动目标，例如，推动流量到您的网站或优化现场转化。

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. 设置目标网址（Destination URL）">

1. 在 **目标** 下，在 **网站URL** 字段中，输入您网站的URL，即用户点击广告后着陆的页面。

   **网站URL** 是主要的目标选项。用户点击广告并直接进入您的网站以完成转化事件。
2. **[替代] AF归因链接（OneLink）：** 如果您希望将用户重定向到移动应用程序，并回退到网站，您可以使用 AF 归因链接（OneLink）作为目标 URL。
3. 点击**Build a URL parameter**，在该网址中添加URL参数。
4. 在**Custom parameters**下点击**Add parameter**。
5. 将 AppsFlyer 参数映射到其 TikTok 值：

| AF参数 | 映射的 TikTok 值 |
| --- | --- |
| `pid` | `tiktokweb_int` |
| `c` | `__campaign_name__` |
| `af_c_id` | `__campaign_id__` |
| `af_adset` | `__aid_name__` |
| `af_adset_id` | `__aid__` |
| `af_ad` | `__cid_name__` |
| `af_ad_id` | `__cid__` |

   > 📘 **注意**
   >
   > 为了简化活动分析，请在活动名称中包含活动类型（网页或移动）作为前缀或后缀，例如，`campaign-name_web`。


   有关 URL 参数配置和流量来源解析的最佳实践，请参见 <Anchor target="_blank" href="/marketers/zh/docs/about-traffic-source-resolution">关于流量来源解析</Anchor>。

   生成的 URL 示例：

   ```http
   https://www.example.com?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__
   ```

   > 📘 **注意**
   >
   > 当广告被点击时，TikTok 会自动将 `ttclid={{ttclid}}` 添加到目标 URL。


</Accordion>

## 查看网页归因数据

网页转化事件在 `tiktokweb_int` PID 下报告，位于 `media_source` 字段中。要查看网页归因数据，请使用原始数据报告并按 `media_source = tiktokweb_int` 过滤，以隔离 TikTok 网站应用转化。

网站应用活动的仪表板报告尚不可用。计划在未来发布一个统一的报告视图，让您可以分析网页活动的表现与其他渠道的表现。

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 成本数据 | TikTok 广告（`tiktokglobal_int`）网站应用活动的成本数据在仪表板中未报告，并且在成本 ETL 报告中也未报告，除了 **所有成本** 报告。   <br />要在 **所有成本** 报告中获取 TikTok 网站应用活动的成本数据，请通过 **成本设置** 页面或 **成本** 选项卡将您的 TikTok 广告账户连接到 TikTok 成本集成（`tiktokglobal_int`）。 |
| 点击和展示 | 目前无法从 TikTok 获取网站应用活动的点击和展示数据。 |
| 再互动 | 通过事件 API 的重新参与回调目前不受支持。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01KQC152Q49R7P96BPMMZGVZWS=%E6%A6%82%E8%A7%88 h_01KQC25PY3PPRTQBJ7K8NV3JWQ=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85 h_01KQC152Q42VT7XKTGCEJV7V7S=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA prerequisites=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01KQC152Q4A31VJ1JTXWJG6CN0=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 how-to-set-up-tiktok-ads-for-your-website-app=%E5%A6%82%E4%BD%95%E4%B8%BA%E6%82%A8%E7%9A%84%E7%BD%91%E7%AB%99%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AEtiktok-web-ads h_01KQC152Q4S1VTK7BGWPHHD27W=%E5%A6%82%E4%BD%95%E4%B8%BA%E6%82%A8%E7%9A%84%E7%BD%91%E7%AB%99%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AEtiktok-web-ads part-1-set-up-tiktok-ads-integration-in-appsflyer=%E7%AC%AC%E4%B8%80%E9%83%A8%E5%88%86%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEtiktok-web-ads%E9%9B%86%E6%88%90 h_01KQC152Q4J5ZCSFVM8EZ8ZBTZ=%E7%AC%AC%E4%B8%80%E9%83%A8%E5%88%86%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEtiktok-web-ads%E9%9B%86%E6%88%90 h_01KQC152Q4WDH8W6AVV679JPGS=1-activate-the-tiktok-ads-integration h_01KQC152Q492SBJMJ3J10B1R84=%E6%B3%A8%E6%84%8F h_01KQC152Q4QWF2996MBS0BYCK7=2-set-inapp-event-postbacks h_01KQC152Q4561EWHVKB7A1AWDX=%E6%B3%A8%E6%84%8F-1 part-2-set-up-appsflyer-integration-in-tiktok-ads=%E7%AC%AC%E4%BA%8C%E9%83%A8%E5%88%86%E5%9C%A8%E6%8A%96%E9%9F%B3%E7%BD%91%E9%A1%B5%E5%B9%BF%E5%91%8A%E4%B8%AD%E8%AE%BE%E7%BD%AEappsflyer%E9%9B%86%E6%88%90 h_01KQC152Q4NKQHF75Y14XCCFNH=%E7%AC%AC%E4%BA%8C%E9%83%A8%E5%88%86%E5%9C%A8%E6%8A%96%E9%9F%B3%E7%BD%91%E9%A1%B5%E5%B9%BF%E5%91%8A%E4%B8%AD%E8%AE%BE%E7%BD%AEappsflyer%E9%9B%86%E6%88%90 h_01KQC152Q4TMJ0F09Q1PZYV71A=1-set-the-campaign-type-objective-and-goals h_01KQC152Q414XNHHR0Q2B8ZCST=2-set-destination-url h_01KQC152Q4F3WQKETR34WRHACT=%E6%B3%A8%E6%84%8F-2 h_01KQC152Q4BYHRW52BYBJHBGJ4=%E6%B3%A8%E6%84%8F-3 view-web-attribution-data=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01KQC152Q45QE5M5BGD4RJNFR9=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01KQC152Q45WC7HNZ64T98JJ6Y=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />

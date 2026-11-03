---
title: Snapchat—为网站应用创建 Web 活动
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
  created_at: '2026-04-29T09:02:24Z'
  edited_at: '2026-10-14T10:00:18Z'
  id: 46196482479249
  locale: zh-cn
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/zh-cn/articles/46196482479249
---
> 概览：为您的网站应用设置 Snapchat 网络广告集成，通过转换 API 向 Snapchat 发送网络转换信号。

## 概览

AppsFlyer 支持与 Snapchat Web Ads (`snapweb_int`) 集成，用于网站应用活动，让您直接通过 Snapchat 的转化 API 报告归属和转化数据。Meta可以利用这些数据来优化定向投放、衡量广告效果并打造自定义人群包。

其工作原理如下：当用户点击Snapchat广告并登陆您的网站，然后完成网站事件(例如购买或注册 ) , AppsFlyer通过转换API向Snapchat发送转换信号。Snapchat使用这些数据来优化广告定位和衡量广告活动绩效。

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/web-performance-measurement-overview">AppsFlyer Web 署名 - 概述</Anchor>

> 🚧 **重要提示！**
>
> 目前，集成尚不支持通过 Conversions API 发送再参与回传数据。

### 前期准备

在为您的网站应用激活 Snapchat Web Ads 集成之前，请确保您已：

* AppsFlyer中设置的网站应用
* <Anchor target="_blank" href="https://ads.snapchat.com/">Snapchat广告管理</Anchor>器中的企业帐户

### 如何为您的网站应用设置Snapchat网页广告

设置涉及定义 Snapchat Web Ads 和 AppsFlyer 之间的集成，并在 Snapchat Ads Manager 中配置活动。它包括以下步骤：

* 第二部分：在AppsFlyer中设置Snapchat Web广告对接 （必须完成）
* 第二部分：在Snapchat Web Ads中设置AppsFlyer对接 （必须完成）

## 第一部分：在AppsFlyer中设置Snapchat Web广告对接

首先激活Snapchat网页广告集成。然后配置 AppsFlyer 发送到 Conversions API 的回发。

<div id="1-activate-the-snapchat-ads-integration" />

<Accordion title="1.激活 Snapchat Web 广告集成">

要启用Snapchat Web广告整合，请执行以下操作：

1. 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。
2. 搜索**Snapchat**并选择它。
3. 点击**设置对接**，然后界面会跳转到活跃对接设置页面。
4. 在**渠道对接**选项卡中，打开**启用该渠道**开关。在您与该渠道合作期间，请确保该开关总是处于打开状态。
5. **Pixel ID：输入相关的Pixe ID。您可以按照 <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US">Snapchat Web Ads 文档</Anchor>中的说明生成它或从 Snapchat Ads Manager 中检索它。**
6. Access token输入相关的token。要创建或检索它，请按照 Snapchat Web Ads 官方文档的<Anchor target="_blank" href="https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted">说明</Anchor>进行操作。

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2.应用内事件回传">

您可以通过将 AppsFlyer 事件映射到 Snapchat Web Ads 事件来定义 AppsFlyer 将哪些 Web 转换事件发送到 Snapchat Ads。这些回帖可以在Snapchat广告管理器中查看。Snapchat 使用映射的事件进行活动优化和报告。

应用内事件回传

1. 打开**应用内事件回传**开关。
2. 如果需要，设置应用内事件回传窗口。在<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">应用内事件回传配置</Anchor>中了解更多信息。
3. 点击**添加事件**，将相关事件添加到列表中。
4. 在**AppsFlyer事件**一列，从下拉菜单中选择相关的事件名称。AppsFlyer 从您网站上集成的 Web SDK 或您发送给 AppsFlyer 的服务器到服务器 (S2S) 事件接收事件名称。
5. 在“**映射到合作伙伴事件**”列中，从列表中选择最合适的预定义合作伙伴事件。
6. 在“**对于用户来源**”列中，选择适当的选项：
   * **此合作伙伴仅**发送归因于 Snapchat Web Ads 的事件。
   * **所有媒体来源，包括有机**，都要发送所有事件，无论归属来源。
7. 在**包括**列中，选择是否将事件与其收入值一起发送。请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#回传内容">回传中包含的数据</Anchor>。
8. 【可选】点击**添加条件**图标，设置事件的<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">映射条件</Anchor>。
9. 点击**保存对接**。

> 📘 **注意**
>
> * 如果您设置的是购买事件，请将**包含**列设为**值和收入**。选择任何其他选项将导致回传失败。
> * 目前，仅购买事件支持包含收入。

</Accordion>

## 第二部分：在Snapchat网页广告中设置AppsFlyer集成

在 Snapchat 广告管理器中执行以下步骤。

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1.设置投放类型、投放目标和转化目标">

您可以选择从 AppsFlyer 发送的任何预定义应用内事件作为您的活动目标。选择一个与您的网站转化目标相一致的活动目标，例如，推动流量到您的网站或优化现场转化。

</Accordion>

<div id="2-set-the-destination-url" />

<Accordion title="2. 设置目标 URL">

1. 在"**目标**"下，在"**网站 URL**"字段中，输入您网站的网址，即用户点击您的广告后登陆的页面。**网站 URL** 是主要的目标选项。用户点击广告，直接登陆您的网站，完成转化活动。
2. **[替代]AF归属链接(OneLink):** 如果您想将用户重定向到具有回退到网站的移动应用，您可以使用AF归属链接(OneLink)作为目标URL。
3. 点击**Build a URL parameter**，在该网址中添加URL参数。
4. 在**Custom parameters**下点击**Add parameter**。
5. 将AppsFlyer参数映射到它们的Snapchat值：

| AF参数 | 映射的 Snapchat 值 |
| --- | --- |
| `pid` | `snapweb_int` |
| `c`c | `{{campaign.name}}` |
| `af_c_id` | `{{campaign.id}}` |
| `af_adset` | `{{adSet.name}}` |
| `af_adset_id` | `{{adSet.id}}` |
| `af_ad` | `{{creative.name}}` |
| `af_ad_id` | `{{ad.id}}` |
| `af_channel` | `{{site_source_name}}` |

   *为简化活动分析，在活动名称中包括活动类型(网络或移动)作为前缀或后缀，例如`campaign-name_web`。

   有关 URL 参数配置和流量源解析的最佳做法，请参阅<Anchor target="_blank" href="/marketers/zh/docs/about-traffic-source-resolution">关于流量源解析</Anchor>。

   完成上述步骤后，可得到如下URL：

   ```http
   https://www.example.com?pid=snapweb_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}
   ```

> 📘 **注意**
>
> 用户点击相关广告时，Meta会自动将`ScCid={{ScCid}}`添加到目标网址（ destination URL）。

</Accordion>

## 查看 Web 归属数据

下面是您在设置后查看归属数据时的预期：

* **原始数据导出和 API 响应**在 Snap Web 活动的 `media_source` 字段中包括 Snap Web。
* 要验证 Web 活动设置详细信息，请检查显示`snapchat_int`为 Web 活动创建期间使用的 PID 的`original_url`字段。

> 📘 **注意**
>
> 网站应用活动的仪表板报告尚未提供。计划在未来发布一个统一的报告视图，让您可以与其他渠道一起分析网络活动绩效。

## 用网络成本衡量网络归属数据

要从Snapchat广告、仪表板和<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">成本ETL报告</Anchor>中获得网页归属数据和网页成本数据的完整性能视图，请确保您拥有<Anchor target="_blank" href="/marketers/zh/docs/roi360-onboarding-guide#roi360简介">ROI360软件包</Anchor>，并完成以下设置：

1. 通过"**成本**"选项卡或"**成本设置**"页中的`snapchat_int`(不是通过`snapweb_int`)将成本连接到您的网站应用程序。有关如何连接到成本的详细信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#启用cost-api">设置ROI360成本API以测量成本数据</Anchor>。
2. 在登录页 URL 中包含活动 ID(`af_c_id`)。确保 URL 包括完整的活动层次结构，以查看成本、点击和印象，并在最细粒度级别与 Web 归属匹配。

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 点击和展示 | 网络广告活动的点击和印象需要<Anchor target="_blank" href="/marketers/zh/docs/roi360-onboarding-guide">ROI360订阅</Anchor>。 |
| 再互动 | 目前不支持通过转换 API 重新约定回发。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01KQC7RA5R1PS69N3015WY4QRY=%E6%A6%82%E8%A7%88 h_01KQC80MBB1KCVVNDSFSJHG5ZT=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85 h_01KQC7RA5RAY6R70GNHCYWAMRC=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA prerequisites=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01KQC7RA5R02QV60T81NX055DM=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 how-to-set-up-snapchat-ads-for-your-website-app=%E5%A6%82%E4%BD%95%E4%B8%BA%E6%82%A8%E7%9A%84%E7%BD%91%E7%AB%99%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AEsnapchat%E7%BD%91%E9%A1%B5%E5%B9%BF%E5%91%8A h_01KQC7RA5RPWP0X927ENN6KJ9V=%E5%A6%82%E4%BD%95%E4%B8%BA%E6%82%A8%E7%9A%84%E7%BD%91%E7%AB%99%E5%BA%94%E7%94%A8%E8%AE%BE%E7%BD%AEsnapchat%E7%BD%91%E9%A1%B5%E5%B9%BF%E5%91%8A part-1-set-up-snapchat-ads-integration-in-appsflyer=%E7%AC%AC%E4%B8%80%E9%83%A8%E5%88%86%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEsnapchat-web%E5%B9%BF%E5%91%8A%E5%AF%B9%E6%8E%A5 h_01KQC7RA5RY1HF9VHC332FVBFR=%E7%AC%AC%E4%B8%80%E9%83%A8%E5%88%86%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEsnapchat-web%E5%B9%BF%E5%91%8A%E5%AF%B9%E6%8E%A5 h_01KQC7RA5RJXR5N13SYW3QMMDQ=1-activate-the-snapchat-ads-integration h_01KQC7RA5R3TZZ8PPHHC8EXPG1=2-set-inapp-event-postbacks h_01KQC7RA5RZVTM2X3N6WXRTAT8=%E6%B3%A8%E6%84%8F part-2-set-up-appsflyer-integration-in-snapchat-ads=%E7%AC%AC%E4%BA%8C%E9%83%A8%E5%88%86%E5%9C%A8snapchat%E7%BD%91%E9%A1%B5%E5%B9%BF%E5%91%8A%E4%B8%AD%E8%AE%BE%E7%BD%AEappsflyer%E9%9B%86%E6%88%90 h_01KQC7RA5REPX0WDDHT7YWDHMC=%E7%AC%AC%E4%BA%8C%E9%83%A8%E5%88%86%E5%9C%A8snapchat%E7%BD%91%E9%A1%B5%E5%B9%BF%E5%91%8A%E4%B8%AD%E8%AE%BE%E7%BD%AEappsflyer%E9%9B%86%E6%88%90 h_01KQC7RA5R8MDFAF9R5YH1TFPX=1-set-the-campaign-type-objective-and-goals h_01KQC7RA5SB11HRSQR493PM121=2-set-the-destination-url h_01KQC7RA5S422C22YQX1VQ4R7A=%E6%B3%A8%E6%84%8F-1 view-web-attribution-data=%E6%9F%A5%E7%9C%8B-web-%E5%BD%92%E5%B1%9E%E6%95%B0%E6%8D%AE h_01KQC7RA5SKRWGGCKV71MV8J56=%E6%9F%A5%E7%9C%8B-web-%E5%BD%92%E5%B1%9E%E6%95%B0%E6%8D%AE h_01KQC7RA5S5VWHT4DW2MPSMNY0=%E6%B3%A8%E6%84%8F-2 measure-web-attribution-data-with-web-cost=%E7%94%A8%E7%BD%91%E7%BB%9C%E6%88%90%E6%9C%AC%E8%A1%A1%E9%87%8F%E7%BD%91%E7%BB%9C%E5%BD%92%E5%B1%9E%E6%95%B0%E6%8D%AE h_01KQC7XYSWPTHVDY5R3EG8H4K2=%E7%94%A8%E7%BD%91%E7%BB%9C%E6%88%90%E6%9C%AC%E8%A1%A1%E9%87%8F%E7%BD%91%E7%BB%9C%E5%BD%92%E5%B1%9E%E6%95%B0%E6%8D%AE traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01KQC7RA5SSZB8M8G00NTXG71K=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />

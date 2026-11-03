---
title: 扩展广告交互类型
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-01-21T13:45:23Z'
  edited_at: '2026-10-14T10:08:46Z'
  id: 21837486015889
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/21837486015889
---
> **概要：** 在广告样式不断精细化、复杂化、互动化的同时，数据上报的方式却一直没有出现相应的扩展，仅将浏览和点击归因作为重点。但扩展广告交互类型（Enriched Engagement Types）突破了这方面的局限，帮助广告主全面了解用户在浏览广告或与广告交互时所产生的各种互动层次和意向强度。

## 简介

在过去几年中，广告形式不断推陈出新，出现了可玩、可跳过、短视频等多种不同类型的广告，拓展了广告主触达用户的方式。这些新型广告与过去的静态横幅和低保真视频单元大不相同，为广告主带来了大量新的可用功能和样式。

在广告样式不断精细化、复杂化、互动化的同时，数据上报的重点却一直停留在浏览和点击归因。各种类型的互动具有不同的权重、意向层次和影响力，但当前的归因衡量方法论却忽视了这一发展态势。同时，广告平台自然希望各个层次的用户意向和广告交互能得到准确的体现。这样一来，整个生态系统缺乏统一的数据标准，最终导致广告主无法全面完整地了解其广告投放效果。

AppsFlyer与业界领先的广告平台多方协作，推出了新的广告交互标准，旨在为整个生态系统的所有参与者都带来可信且透明的数据。扩展广告交互类型（Enriched Engagement Types）能帮助广告主全面掌握用户在浏览广告或与广告交互时所产生的各种互动层次和意向强度，覆盖了从短暂曝光到即时反馈等各种级别的互动。这一框架可确保相关数据标准在AppsFlyer的渠道生态系统内外得到全面贯彻。广告主可通过扩展广告交互类型获得高度标准化的详尽效果数据，以便利用这些关键信息来优化预算分配并提升ROAS。

## 什么是扩展广告交互类型

扩展广告交互类型（Enriched Engagement Types）框架能够标记出深度浏览（如用户在可跳过按钮出现后继续观看超过5秒）以及深度点击（用户点击后不打开应用或进入应用商店），从而深入呈现用户链路中的各种细节。营销人员可以通过这些数据更深入地洞察用户行为，进而更有效地配置预算并提升ROI。

扩展广告交互类型如下表所示：

| engagement\_type | 说明 |
| --- | --- |
| <span id="preload"></span>preload | 相关应用由OEM在设备出厂时预装到设备上，或由服务商在设备首次激活时完成预装。也可以在设备首次激活时通过向导对话框引导用户下载相关应用。 |
| <span id="click_to_download"></span>click\_to\_download | 如果用户与广告进行了互动，相关应用会自动下载并安装到用户设备中，无需跳转到应用商店。 |
| <span id="click_to_app"></span>click\_to\_app | 用户点击广告、扫描二维码、通过深度链接或其它类型的点击后跳转到应用中，或跳转到对应的应用商店中下载相关应用。 |
| <span id="engaged_click"></span>engaged\_click | 用户完成点击后停留在原来的网页环境中与广告进行互动，不跳转到应用商店或调起应用。 |
| <span id="engaged_view"></span>engaged\_view | 在可跳过视频、激励视频或StoreKit渲染型广告中发生了较为重要的深度浏览。比如用户观看可跳过的视频广告时，在跳过按钮出现后继续观看了至少5秒时，即可视为重要的深度浏览。 |
| <span id="view"></span>view | 广告呈现并完成展示，即记为一次广告浏览（ad view）。 |
| <span id="listening"></span>listening | 指用户聆听音频广告，如播客广告。 |

## **EET归因优先级和回溯窗口**

扩展广告交互类型框架不会影响交互类型的归因优先级。因此，引入EET预计不会对您的安装量和转化率产生影响。

每种交互类型的归因优先级和回溯窗口如下表所示：

<table><thead><tr><th>广告交互</th><th>交互类型</th><th>归因优先级</th><th>回溯窗口\*\*</th></tr></thead><tbody><tr><td rowspan="2">下载</td><td>preload</td><td>1</td><td>1小时-180天｜默认：90天</td></tr><tr><td>click_to_download</td><td>2</td><td>1小时-30天｜默认：7天</td></tr><tr><td rowspan="2">Click（点击）</td><td>click_to_app</td><td>2</td><td>1小时-30天｜默认：7天</td></tr><tr><td>engaged_click</td><td>2</td><td>1小时-7天｜默认：2天 </td></tr><tr><td rowspan="3">Impression（展示）</td><td>engaged_view</td><td>2</td><td>1小时-7天｜默认：2天</td></tr><tr><td>view</td><td>3</td><td>1小时-24小时｜默认：24小时</td></tr><tr><td>listening</td><td>3</td><td>1小时-24小时｜默认：24小时</td></tr></tbody></table>

若未上报互动类型，系统会为其设置默认的归因优先级（点击为2，展示为3）。

<strong>`engaged_click`和`engaged_view`的回溯窗口仅限于SRN平台。对于SRN，`engaged_click`和`engaged_view`的回溯窗口和点击相同，因此需通过</strong>安装点击归因回溯滑块设置。

## 哪些广告平台可以上报深度浏览和深度点击？

AppsFlyer认证的可上报`engaged_clicks`和`engaged_views`的广告平台如下表所示。 对于希望加入此表的广告平台，请联系AppsFlyer支持。

| **广告平台** | 深度浏览（Engaged Views） | 深度点击 |
| --- | --- | --- |
| facebook\_int | 是 |  |
| googleadwords\_int | 是 |  |
| tiktokglobal\_int* | 是 | 是 |
| twitter\_int | 是 | 是 |
| snapchat\_int | 是 | 是 |
| bytedanceglobal\_int | 是 | 是 |
| aarki\_int | 是 | 是 |
| adjoe\_int |  | 是 |
| appier\_int | 是 | 是 |
| appnext\_int | 是 |  |
| bidease\_int | 是 | 是 |
| bigabid\_int | 是 | 是 |
| inmobidsp\_int | 是 | 是 |
| ironsource\_int | 是 |  |
| lap\_int | 是 |  |
| liftoff\_int | 是 | 是 |
| mdsp\_int | 是 | 是 |
| mintegral\_int | 是 | 是 |
| onedigitalturbine\_int | 是 |  |
| personalyrtb\_int | 是 | 是 |
| pinterest\_int | 是 |  |
| remerge\_int | 是 | 是 |
| revx\_int | 是 | 是 |
| rtbhouse\_int | 是 | 是 |
| smadex\_int | 是 | 是 |
| trademob\_int | 是 | 是 |
| unityads\_int | 是 | 是 |
| vungle\_int | 是 |  |
| yahoojapan\_int | 是 |  |
| yandexdirect\_int | 是 | 是 |
| youappi\_int | 是 | 是 |
| jampp\_int | 是 | 是 |

* TikTok 支持增强型互动类型，但其互动浏览量目前未在报告中得到正确反映。AppsFlyer 正在与 TikTok 合作解决此问题。

> 📘 **注意**
>
> 并非所有列出的平台都支持深度点击和深度浏览。要确定某一平台是否支持`engaged_clicks`和`engaged_views`，请查阅原始数据报告，查看该平台的`engagement_type`参数中是否填充了以上数值。

## 为深度点击和深度浏览设置回溯窗口

**如需为深度点击和深度浏览设置回溯窗口：**

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 选择相关的对接渠道。
3. 为深度浏览和深度点击归因设置回溯窗口。

   > 📘 **注意**
   >
   > 与普通的浏览和点击回溯窗口不同，深度点击和深度浏览的回溯窗口总是在**渠道对接**选项卡中设置，而不是在归因链接中设置。
   >
   > 对于SRN，设置点击回溯窗口也决定了深度点击和深度浏览的回溯窗口。

4. 点击**保存对接**。

## 查看和分析EET数据

### 原始数据报告

只要广告平台上报`engagement_type`，该数据就会出现在原始数据报告中。助攻渠道的数据也可使用该字段。

> 📘 **注意**
>
> 原始数据报告中始终包含深度浏览数据，即使浏览归因关闭时也是如此。

如果没有记录到点击，比如在预装或深度链接场景中，AppsFlyer会在原始数据报告的`engagement_type`字段中设置相应的值（预装为“preload”，深度链接为“`click_to_app`”）。

以下场景将导致原始数据报告中的字段接收到`engagement_type`和`click_unspecified`值。

* 广告交互行为（点击/展示）与广告交互类型不匹配。
* 当`af_engagement_type`未发送或发送了空值时。

如需在原始数据报告中看到广告交互类型数据，请确保在相关原始数据产品中选择这些字段（广告交互类型和助攻交互类型不是默认选定的字段）。

### 面板

AppsFlyer面板中已新增广告交互类型维度。

[![eet-dashboard.png](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)

> 📘 **注意**
>
> 控制面板中始终包含深度浏览数据，即使浏览归因关闭时也是如此。

### 如何计算**每千次安装（IPM）**

展示包括深度浏览和普通浏览。如需计算IPM，则必须从展示总数中**减去深度浏览**，因为深度浏览是展示的一个子集，如不减去会导致重复计算。

## 常见问题解答

<div id="what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types" />

<Accordion title="扩展广告交互类型适用于哪些类型的广告投放？">

扩展广告交互类型适用于UA和再营销广告，具体取决于平台。要了解某个渠道是否支持重定向广告活动，请参阅该渠道的原始数据报告，并检查 `engagement_type` 是否已针对该重定向广告活动填充。

</Accordion>

<div id="are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard" />

<Accordion title="数据总览面板中的点击和展示汇总数据中是否包含engaged_click以及engaged_view？">

非SRN下包含该数据，并按触达类型统计（即深度点击计入点击，深度浏览计入展示）。SRN下目前尚不包含或统计该数据，后续取决于相关SRN的API是否支持这类数据。

</Accordion>

<div id="why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions" />

<Accordion title="为什么Meta的gp_referrer转化中没有广告交互类型信息？">

Meta仅在其SRN API中上报engagement\_type=engaged\_view。Meta 不支持其他转化的 engagement\_type 值，包括 gp\_referrer。

</Accordion>

<div id="why-cant-i-see-the-engagement-type-i2" />

<Accordion title="为什么在关闭了浏览归因后，我仍可以看到安装和在互动的 attributed_touch_type = impression ？">

即使浏览归因按钮被关闭，深度浏览仍会被衡量和上报。要将这些展示识别为深度浏览，请在数据面板和原始数据报告中使用指标，而不是仅仅依赖于`engagement_type = engaged_views`。

</Accordion>

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| <span id="cross-platform-engaged-view-support"></span>跨平台深度浏览支持 | 扩展广告交互类型尚不支持跨平台使用。即使在展示URL中发送了`engaged_view`，合作伙伴和广告主仍会在归因数据中看到`view`。 |
| <span id="owned-media-support"></span>自有媒体支持 | 目前尚不支持自有媒体，因此切勿在自有媒体链接中使用`af_engagement_type`参数。 |

<div data-zendesk-anchors="introduction=%E7%AE%80%E4%BB%8B h_01HNCNA03SZ0MJFQ9XHDFXNTA1=%E7%AE%80%E4%BB%8B enriched-engagement-types=%E4%BB%80%E4%B9%88%E6%98%AF%E6%89%A9%E5%B1%95%E5%B9%BF%E5%91%8A%E4%BA%A4%E4%BA%92%E7%B1%BB%E5%9E%8B h_01HNCNBR7KMT1KQBG5CPZY8YQY=%E4%BB%80%E4%B9%88%E6%98%AF%E6%89%A9%E5%B1%95%E5%B9%BF%E5%91%8A%E4%BA%A4%E4%BA%92%E7%B1%BB%E5%9E%8B eet-attribution-priority-and-lookback-window=eet%E5%BD%92%E5%9B%A0%E4%BC%98%E5%85%88%E7%BA%A7%E5%92%8C%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01HNCVYDH17NGA8SH5XNWR4P9X=eet%E5%BD%92%E5%9B%A0%E4%BC%98%E5%85%88%E7%BA%A7%E5%92%8C%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 allowed-networks=%E5%93%AA%E4%BA%9B%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E5%8F%AF%E4%BB%A5%E4%B8%8A%E6%8A%A5%E6%B7%B1%E5%BA%A6%E6%B5%8F%E8%A7%88%E5%92%8C%E6%B7%B1%E5%BA%A6%E7%82%B9%E5%87%BB h_01J00XFV136HPEHVQNPD934409=%E5%93%AA%E4%BA%9B%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E5%8F%AF%E4%BB%A5%E4%B8%8A%E6%8A%A5%E6%B7%B1%E5%BA%A6%E6%B5%8F%E8%A7%88%E5%92%8C%E6%B7%B1%E5%BA%A6%E7%82%B9%E5%87%BB 01JENXRAMPFXTMF7SKDN2Y0E5M=%E6%B3%A8%E6%84%8F set%C2%A0engaged-enrichment-attribution=%E4%B8%BA%E6%B7%B1%E5%BA%A6%E7%82%B9%E5%87%BB%E5%92%8C%E6%B7%B1%E5%BA%A6%E6%B5%8F%E8%A7%88%E8%AE%BE%E7%BD%AE%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01J5B6EVM9P3M1SVR3K7WWK02J=%E4%B8%BA%E6%B7%B1%E5%BA%A6%E7%82%B9%E5%87%BB%E5%92%8C%E6%B7%B1%E5%BA%A6%E6%B5%8F%E8%A7%88%E8%AE%BE%E7%BD%AE%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01J5B97RCQQG6GN4PCKTQWVF54=%E6%B3%A8%E6%84%8F-1 reporting=%E6%9F%A5%E7%9C%8B%E5%92%8C%E5%88%86%E6%9E%90eet%E6%95%B0%E6%8D%AE h_01J00XFV13YN8QNFZJTGM78EG2=%E6%9F%A5%E7%9C%8B%E5%92%8C%E5%88%86%E6%9E%90eet%E6%95%B0%E6%8D%AE raw-data=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01J00XFV132M8TM6EGFZ7A7C3A=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A 01JFCPX6WKCWY9RM470H23EDQ0=%E6%B3%A8%E6%84%8F-2 dashboards=%E9%9D%A2%E6%9D%BF h_01J00XFV13W0SD4MD7H4BT1RC9=%E9%9D%A2%E6%9D%BF 01JFCPX6WNCFC0R0N90G4HFYZX=%E6%B3%A8%E6%84%8F-3 how-to-calculate-installs-per-mille-ipm=%E5%A6%82%E4%BD%95%E8%AE%A1%E7%AE%97%E6%AF%8F%E5%8D%83%E6%AC%A1%E5%AE%89%E8%A3%85ipm h_01JHG3EQN6FNJAHX1S91JE3MPT=%E5%A6%82%E4%BD%95%E8%AE%A1%E7%AE%97%E6%AF%8F%E5%8D%83%E6%AC%A1%E5%AE%89%E8%A3%85ipm faqs=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01JFCKK7FK0B5Z7QCZNSX14WF2=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HNFTS74KF3YFA0SWRGEQAGYQ=what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types h_01HNYY1S6YQ6YNR6RSY7B8H4EM=are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard h_01HQG5Y4JVNCB60AXR9K2GGD0H=why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions h_01JJP3TT2QMH5Y94C4Q7V6HFP1=why-cant-i-see-the-engagement-type-i2 cross-platform-traits-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />

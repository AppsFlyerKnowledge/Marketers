---
title: 为多设备活动设置跨平台链接
metadata:
  keywords:
    - Attribution
    - Advertisers
    - CTV
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2022-06-19T07:02:43Z'
  edited_at: '2026-10-14T09:59:58Z'
  id: 6966260647185
  locale: zh-cn
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/zh-cn/articles/6966260647185
---
> **概要：本文介绍了AppsFlyer如何对发生在不同设备上的应用激活和广告展示进行匹配，帮助广告主开展跨平台的应用推广和衡量工作。比如将移动端的应用激活归因到CTV设备上的广告展示、将掌机端或CTV设备上的应用激活归因到移动端或PC端（网页）的广告展示等等。**

<div id="how-does-the-attribution-logic-work" />

<div id="overview" />

## 概览

使用AppsFlyer的跨平台归因链接（展示URL）后，您就可以将一个平台上发生的激活归因到另一个平台上的广告展示。此外，该功能还可以将一所住宅内的多个激活归因到同一个跨平台广告展示。

<div id="create-a-onelink-templatefor-cross-platform-attribution" />

## 创建或编辑OneLink模板，用于跨平台归因。

一个模板能支持多个系统平台的应用版本（即只需一个模板就能实现跨设备归因）。

1. 创建或编辑<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">OneLink模板</Anchor>，用于跨平台归因。
2. 进入**跨平台归因**板块，点击**编辑按钮 ->** **启用跨平台归因**。
3. 在相关系统平台的下拉菜单中，选择需要使用跨平台归因的应用。**注意**： 每个应用只能添加到一个启用跨平台归因的 OneLink 模板中。[<Image alt="跨平台归因.png" src="https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png" width="476px" />](https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png)

<div id="set-up-cross-platform-partner-integration" />

## 设置跨平台合作伙伴集成

要使用跨平台印象 URL 设置跨平台归因，请为每个目标应用配置合作伙伴集成。

<div id="important" />

> 🚧 **重要提示！**
>
> 确保通过执行以下步骤启用合作伙伴集成，适用于您在 OneLink 模板中选择的所有目标应用（请参见 [上面的部分](#创建或编辑onelink模板用于跨平台归因)）。如果某个目标应用的集成被禁用，则不会发生跨平台归因。

<div id="h_01K2HBXDWSG3R1WZXT5RB0W48D" />

<Accordion title="第1步：选择合作伙伴集成的目标应用">

1. 从AppsFlyer面板左侧的菜单栏中选择协作 > **活跃对接**。
2. 选择相关的对接渠道。
3. 在 **集成** 选项卡中，从 **应用** 下拉框中选择目标应用。

</Accordion>

<div id="step-2-enable-viewthrough-attribution" />

<Accordion title="第2步：启用浏览型归因">

为对接渠道的归因链接启用浏览型归因。

1. 在**渠道对接**选项卡中打开**浏览型激活归因**的开关。
2. 点击**保存对接**。

</Accordion>

<div id="step-4-create-an-attribution-link-crossplatform-impression-url" />

<Accordion title="第3步：创建一条归因链接（跨平台展示URL）">

请按以下方式创建一条<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">归因链接</Anchor>（跨平台展示链接），用于对接渠道中的投放：

1. 从AppsFlyer后台左侧的菜单栏中选择**协作** > **活跃对接**，然后选择相关渠道。
2. 进入**归因链接**选项卡，在创建<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">OneLink链接</Anchor>时选择“使用OneLink”。
3. 选择要用于跨平台归因所的OneLink模板。
4. 向下滚动到**浏览型归因**。[![](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)
5. 打开**跨平台归因**开关。该操作会在展示归因链接中添加`af_xplatform=true`参数，为该链接赋以跨平台归因功能。如果不添加这个参数，则相关URL仅能用作常规的展示链接，无法将多个激活归因到同一个广告展示。
6. 设置**跨平台浏览型归因回溯窗口**。该操作会将`af_xplatform_vt_lookback`参数添加到展示归因链接中，代表从广告展示到应用激活之间的归因时限，最多72小时。
7. 根据实际需求添加其它归因参数。使用有助于识别跨平台应用广告的方式来命名相关广告系列。 如需进一步了解其他可用参数及其对应的数据和指标，请参考<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">此文档</Anchor>。示例链接：

   ```http
   https://impressions.onelink.me/{template_id}?pid=__media_source__&af_xplatform=true&af_xplatform_vt_lookback=24h&af_siteid=__CSITE__&c=__ctv_to_mobile__&af_channel=__PLACEMENT__&af_c_id=__CAMPAIGN_ID__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_source_platform=__source_platform__&af_source_device_category=__device_category__&af_ad_type=__CTYPE__&redirect=false
   ```
8. 让广告平台将该链接放在CTV、PC端货主机端广告中。

<div id="important-1" />

> 🚧 **重要提示！**
>
> 请根据实际需求为自有媒体和非对接渠道添加适用的参数。 如需进一步了解其他可用参数及其对应的数据和指标，请参考<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">此文档</Anchor>。

</Accordion>

<div id="equal-priority-advanced-setting" />

<Accordion title="Advanced > 相等优先级设置（可选）">

您可以选择性地为跨平台归因中的点击和印象分配 **相等优先级**。此高级设置允许 AppsFlyer 将印象（例如，在 CTV 或控制台中）视为与点击具有相同的归因优先级。有关更多信息，请参见 <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#各种归因方式的优先级归因瀑布流">归因方法优先级</Anchor>。

**启用相等优先级：**

1. 在跨平台设置部分，选中 **相等优先级** 复选框。
2. 点击**保存**。

<div id="note" />

> 📘 **注意事项**
>
> 启用相等优先级可能会导致 AppsFlyer 优先考虑其自身的归因，而不是其他来源。谨慎使用此设置，仅在其与您的整体归因策略一致时使用。

</Accordion>

## 广告平台列表

如需了解哪些广告平台能在CTV、PC端和主机端展示广告且支持跨平台归因，请先登入您的AppsFlyer账号，然后在<Anchor target="_blank" href="https://hq1.appsflyer.com/partner-marketplace/explore?integrationLevels=CROSS_PLATFORM">AppsFlyer的Partner Marketplace</Anchor>渠道平台中查看相关列表。

<div id="traits-and-limitations" />

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| <span id="attribution-window"></span>归因窗口 | 在1-72小时之间，具体取决于回溯窗口参数`af_xplatform_vt_lookback`af\_xplatform\_vt\_lookback（默认为24小时）。 |
| <span id="retargeting"></span>再营销 | <ul><li>Re-attribution（再归因）：支持跨平台到移动端，不支持到其它平台。</li><li>Re-engagement不支持</li></ul> |
| <span id="attribution-method"></span>归因方法 | 使用概率模型完成浏览型归因 |
| <span id="household-attribution"></span>基于住宅的归因 | 支持。也就是说，该功能可以将一所住宅内的多个激活跨归因到同一个跨平台广告展示。 |
| <span id="reporting"></span>报告功能 | <ul><li>您可以在AppsFlyer的常规面板和报告中查看跨平台激活数据：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview">汇总数据</Anchor>面板及报告</li><li>原始数据报告</li></ul></li><li>应用层级的面板中不会呈现跨平台展示。但您可以在Data Locker的<Anchor target="_blank" href="/marketers/zh/docs/data-locker-advertiser-reports#user-journey">跨平台互动报告</Anchor>中查看这些数据。</li><li>请确保您使用的参数名称易于识别跨平台广告。</li></ul> |
| <span id="ip-masking"></span>掩盖IP | 不支持在跨平台互动中掩盖IP，因为这是一个应用层级的信息。如果链接中配置了`ip_masking` ip\_masking参数，AppsFlyer就不会将相关激活归因到跨平台互动。 |
| <span id="ctvto-mobile"></span>CTV到移动端 | 相关对接渠道必须具有必要授权，可投放跨平台广告，才能被纳入CTV到移动端的归因流程。 |
| <span id="cross-platform-attribution-links-in-mobile-devices"></span>移动设备中的跨平台归因链接 | 当用户在移动端设备上看到跨平台归因链接时，AF会通过常规的移动端概率模型逻辑对该用户进行归因，而不使用<Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts#tv-screens">CTV</Anchor>、PC和主机端专用的跨平台归因流程。因此，移动端的展示不能使用同等归因优先级设置、[延长的回溯窗口期](#step-3-enable-equal-priority-for-crossplatform-impressions)或[基于住宅的归因](#attribution-window)，这些设置只支持真实的跨平台展示。 |
| <span id="agency-permissions"></span>代理权限 | 代理商无法在其端切换“跨平台相等归因优先级”。此配置直接复制自特定广告网络的广告主设置。 |

<div id="discrepancies" />

## 数据差异

AppsFlyer和tvScientific的归因模式不同，因此两者的面板之间可能会有一些数据差异。具体的差异原因请见下表：

| 原因 | tvScientific | AppsFlyer |
| --- | --- | --- |
| 基础模式 | 共享归因模式 | 末次点击模式 |
| 回溯窗口 | 最长30天 | 最长72天 |
| 再营销 | 同时支持新用户（激活）以及老用户（再互动）的归因 | 仅支持新用户（激活）的归因 |
| 成本归因 | 成本归因到展示，不分操作系统 | 成本归因到iOS和安卓系统中对应的展示 |

<div id="faq" />

## 常见问题解答

<div id="does-enable-viewthrough-attribution-via-probabilistic-modeling-need-to-be-turned-on" />

<Accordion title="是否需要打开“使用概率模型进行浏览型归因”的开关？">

不需要。即使您不在应用配置页面中打开使用概率模型进行浏览型归因开关，跨平台浏览型归因也会生效。

</Accordion>

<div id="why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard" />

<Accordion title="为什么我在仪表板中看不到我的跨平台活动的印象？">

应用层级的面板中不会呈现跨平台展示。这是因为一个CTV展示可以在不同的应用程序中导致多个转化，并且没有准确的方法将展示分配给每个应用程序。您可以在<Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-data-via-data-locker#报告类型及可用性">数据锁定中的跨平台参与报告</Anchor>中访问展示数据。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 01H8V0RV7X8JEVEJ36TJB1X43D=%E6%A6%82%E8%A7%88 step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution=%E5%88%9B%E5%BB%BA%E6%88%96%E7%BC%96%E8%BE%91onelink%E6%A8%A1%E6%9D%BF%E7%94%A8%E4%BA%8E%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0 h_01HVECG1TZ8B5GH28CZM2186BF=%E5%88%9B%E5%BB%BA%E6%88%96%E7%BC%96%E8%BE%91onelink%E6%A8%A1%E6%9D%BF%E7%94%A8%E4%BA%8E%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0 set-up-crossplatform-attribution=%E8%AE%BE%E7%BD%AE%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4%E9%9B%86%E6%88%90 h_01HVECG1TZSDTP0WBG7XYM509G=%E8%AE%BE%E7%BD%AE%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4%E9%9B%86%E6%88%90 01JEKG3V0C75G782RC7CE9DAV2=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HVECG1TZKNG17STSN5XJAF9C=step-2-enable-viewthrough-attribution step-4-create-an%C2%A0attribution-link%C2%A0crossplatform-impression-url=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ6WP257R9D8A105FR=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ3K1EFA22716K2B9X=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 h_01K2HBZKX0EJHSVCXJJ97NMVXZ=equal-priority-advanced-setting equal-priority-impact-note=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01K2HBZKX0ECJPTQMPPXC3JBVC=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 list-of-ad-networks=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E5%88%97%E8%A1%A8 h_01HVED5DJP78EGF2D8SFJVND1H=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E5%88%97%E8%A1%A8 traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HVED5DJPFR5XCWYDSYCHMCR6=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 discrepancies=%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 h_01HVED5DJPMP3AQDTN3GM77T2F=%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 faq=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HVED5DJPBPDSZ0AAY1RG8NEZ=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01K4AC2J63B4MBTDGZHH7ACRCG=does-enable-viewthrough-attribution-via-probabilistic-modeling-need-to-be-turned-on why-don%E2%80%99t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard=why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard h_01K4AC2J63KBF8X20DMNPW1GTK=why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard" />

---
title: CTV、PC和主机端的归因原理
metadata:
  keywords:
    - Attribution
    - Advertisers
    - Developers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2021-07-15T11:30:45Z'
  edited_at: '2026-10-14T10:00:07Z'
  id: 4404083608849
  locale: zh-cn
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/zh-cn/articles/4404083608849
---
> **概要：** 本文说明了CTV、PC和主机端的归因原理，帮助您在投放跨平台广告时向AppsFlyer发送归因和事件数据。

<Image alt="7435_CTV_image.png" src="https://files.readme.io/7fc57fd80ad86bb173bcf81581b9fe8b4625ed2a044d302a6d72194560019e81-4410336840977.png" width="471px" />

## AppsFlyer的跨端归因方案

在当今的互联网营销行业中，要在多个设备和平台中触达用户是用户增长方面的一大难题。传统的衡量方法无法捕捉到完整的跨平台用户链路。如果要了解营销推广的效果并作出明智的决策，就必须进行跨平台的归因衡量。

AppsFlyer为广告主提供全面的跨端归因解决方案，可配合传统的移动端归因工具一并使用，可帮助用户增长负责人准确衡量跨端营销效果，并对多平台、多设备访问的用户进行归因。该解决方案主要用于CTV、PC 和主机端应用。

推广相关应用时，广告主可以选择在该应用的平台中投放广告，也可以在其他平台上进行推广。举例来说，广告主可以在Steam平台上投放广告，推广其Steam应用，也可以通过Google Ads等渠道在PC端投放该Steam应用的广告。

无论广告主采取哪一种营销策略，都可以与AppsFlyer对接并针对其CTV、PC和主机端应用的激活和激活后事件，获取流量来源（自然或非自然）及带量广告的归因和效果数据。营销人员可以利用这些关键信息计算其用户的生命周期价值（LTV），进而对营销工作进行评估和优化。<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">进一步了解AppsFlyer归因</Anchor>

### 适配平台

<table><thead><tr><th>操作系统</th><th colspan="2">AppsFlyer对接方式</th></tr><tr><th> </th><th>S2S</th><th>SDK</th></tr></thead><tbody><tr><td>Android TV</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>tvOS（Apple TV）</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>MacOS</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Amazon Fire TV</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Chromecast</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Roku</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Vizio</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Samsung</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>LG</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>PlayStation</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Vidaa</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Steam</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>PC端原生应用（Native PC）</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Meta Quest（Oculus）</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Epic Games</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Nintendo Switch</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Xbox</td><td><span>✓</span></td><td><span>-</span></td></tr></tbody></table>


<span id="list-of-supporting-ad-networks"></span>如需了解哪些广告平台能在CTV、PC端和主机端展示广告且支持跨平台归因，请先登入您的AppsFlyer账号，然后在<Anchor target="_blank" href="https://hq1.appsflyer.com/partner-marketplace/explore?integrationLevels=CROSS_PLATFORM">AppsFlyer的Partner Marketplace</Anchor>渠道平台

1. **从AppsFlyer的侧边栏中选择协作** > Partner Marketplace。


1. **<span id="list-of-specified-platforms"></span>从AppsFlyer的侧边栏中选择协作** > Partner Marketplace。

## 跨平台归因流程

在推广CTV、PC和主机端应用时，从广告触达（展示或点击）到AppsFlyer归因之间有多种适用于各个平台的通用流程，具体如下：

* 直接归因链接
* 跨平台OneLink链接
* SRN（自归因平台，或称SAN）
* 跨平台落地页

一个应用、广告主和平台可同时使用多种流程。下文介绍了各类流程及其使用场景。

<div id="direct-attribution-link" />

<Accordion title="直接归因链接">

直接归因链接是一种AppsFlyer链接，支持单平台应用的单平台跳转和归因，通常用于：

* 同一平台的广告投放，即在支持相关应用的平台中投放广告。比如广告主可以在三星智能电视上投放广告，推广某个三星电视的应用。
* 固定终点/平台的多端广告投放，比如在PC端落地页中展示带有多个按钮的广告，每个按钮跳转到不同平台的商店/交易平台。

直接归因链接同时支持概率模型和确定性匹配（通过链接提供ID时）的归因模式，将一个用户的一次激活归因到一个广告点击或展示。具体归因流程如下图所示。

![CTV attribution flow - Direct attribution link flow.png](https://files.readme.io/2af32b096faa381843040314c9c183056256d03a7e2e6095e72a59bb7211727f-19374976446225.png)

由于直接归因链接用于固定平台中单个应用的单一终点跳转，因此其URL中总是包含相关的应用ID和平台信息。

直接归因链接示例：`https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/1234561?&af_media_source=game_media_source&af_campaign=campaign_yellow&af_campaign_id=1234&af_ad=game_ad_name&af_adset=game_adset_name&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F1176160%2FSpace_Wars%2F`

如需了解直接归因链接的设置方式，请参考<Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links#归因链接">此文档</Anchor>。

</Accordion>

<div id="crossplatform-onelink" />

<Accordion title="跨平台OneLink链接">

广告投放平台不同于引流终点平台时，可使用跨平台的OneLink链接来实现跳转和归因。这种方式适用于多平台场景。比如在“CTV到移动端”链路中，广告主在Roku平台/设备中展示广告，但引流终点可以是安卓/iOS应用。类似的例子还有“PC到主机端”链路，游戏广告主在PC端网页中展示广告，推广其在PC端及多个主机平台上架的游戏，如PlayStation、Xbox和Steam等。

跨平台OneLink链接仅支持概率模型归因（以IP地址为基础），因此可以将多个用户的多次激活归因到同一个广告展示。具体归因流程如下图所示。

![CTV attribution flow - Cross-platform Onelink link attribution flow (1).png](https://files.readme.io/926ecf50c96dc72b05d107f1cf7b17b8c343b6e31f3755a1c39c801496568f50-51911195677329.png)

由于OneLink模板中含有所有可能出现的应用端/平台，因此跨平台OneLink链接的URL中不包含具体的应用ID或平台信息，而是使用相关的OneLink模板ID，以传递模板中配置的应用端/平台信息。

跨平台OneLink链接示例：`https://impressions.onelink.me/ch/AG7A?pid=game_media_source&c=game_landing_page&af_ad=game_ad_name&af_adset=game_adset_name&af_xplatform=true`

<Anchor target="_blank" href="/marketers/zh/docs/set-up-cross-platform-links-for-multi-device-campaigns">如需了解跨平台OneLink链接的设置方式，请参考此文档。</Anchor>

</Accordion>

<div id="srn" />

<Accordion title="SRN">

使用直接归因链接和跨平台OneLink链接时，AppsFlyer会通过URL中的数据对用户激活进行归因。但自归因平台（SRN，或称SAN）会在AppsFlyer向其发送激活信息时，通过设备ID认领相关激活，从而自行完成归因。

对于SRN的归因是通过确定性匹配完成的。广告主与SRN对接后，其归因流程如下图所示。

![CTV attribution flow - SRN attribution flow (1).png](https://files.readme.io/ba0d84643aefd6a20e95c8aca9424affea8169c95ccc428ddf3d35bb8787a67c-19374961372945.png)

SRN归因目前仅适用于同平台投放，也就是说营销触点（点击或展示）的平台必须与用户完成激活的平台一致。举例来说，如果AppsFlyer向Roku Endemic Media（即Roku的SRN）查询了Roku CTV上的某个激活，并发现Roku设备上发生了广告展示，这时该次激活会被纳入归因流程，但如果广告展示发生在其他平台（如移动端），则该次激活会被排除在归因流程之外。

未来SRN归因将支持多平台投放，以更全面地覆盖跨平台归因。

</Accordion>

<div id="landing-page" />

<Accordion title="跨平台落地页">

跨平台落地页用于支持常见的跨平台用户链路和营销流程，在游戏类应用中最为常用。在落地页中部署AppsFlyer的智能脚本即可进行网页到应用归因，将任何平台上发生的激活（CTV、PC、主机和移动端）归因到网页中展示的广告。

跨平台落地页中的智能脚本通过传入链接（即网页广告上的链接）完成以下行为，以确保将相关激活归因到最初的带量渠道及网页广告：

* 创建跨平台OneLink链接，向AppsFlyer发送一个广告展示。这样，AppsFlyer就能记录到一次展示，用于后续的用户激活归因。该次展示会在落地页打开时发送。即使用户在离开落地页之前未点击任何按钮，并自行完成了相关应用的下载、安装和激活，仍可将其归因到该次广告展示。
* 为每个应用/平台创建直接归因链接。用户点击这些链接后，会跳转到与其设备适配的平台/应用商店。若该用户后续下载并激活了相关应用，则其激活会被归因到这次点击。

落地页同时支持概率模型和确定性匹配（链接中提供ID时）两种归因模式。使用概率模型归因时，可将多个用户的多次激活归因到同一个广告展示。具体归因流程如下图所示。

![CTV attribution flow - Landing page attribution flow.png](https://files.readme.io/28e4d14d14532332027e5d429ac3f95c8d4d451d94125e399cfb9ad04727b278-19374961376529.png)

使用场景示例:

1. 假设您有一个游戏类应用，用户可在PC端、移动端、Epic或Steam平台上下载并游玩该游戏。
2. 您投放了一条网页广告，推广该游戏。
3. 您通过付费搜索结果或社交媒体推广，让用户在网页上看到了这条广告。
4. 该用户点击广告后，跳转到落地页，落地页中针对PC端、移动端、Epic及Steam，展示了分平台的下载按钮。
5. 该落地页中运行的AppsFlyer智能脚本完成以下工作：
6. 捕捉入链（将用户从网页引导到落地页的链接）中的关键数据点，如查询参数、UTM参数、默认值，用于识别媒体渠道、广告系列、广告等等。
7. 使用上述数据点生成一次展示，并将其发送给AppsFlyer。
8. 针对各个平台的下载按钮生成传出的链接。
9. 用户点击任一下载按钮后，即会跳转到相应平台的应用商店，以便其下载并激活该应用。
10. 用户的激活/首次应用打开会匹配到该次展示，并归因到最初在网页中展示广告的媒体渠道。

其他相关信息：

* <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">跨平台落地页示例</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/cross-platform-landing-pages-with-smart-script">如需了解如何设置带有智能脚本的跨平台落地页，请参考此文档。</Anchor>

</Accordion>

## 数据可用性

CTV、PC和主机端的数据包括激活和应用内事件，能让广告主根据订阅、应用内购买和广告变现等信息，分析其自然和非自然用户的生命周期价值（LTV）。 AppsFlyer会根据归因之日起到当前为止的数据计算LTV指标。

数据可用性如下：

* 通过数据总览面板呈现汇总数据。
* 原始数据的传输方式如下：
  * <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-data-via-data-locker">Data Locker</Anchor>
  * <Anchor target="_blank" href="/marketers/zh/docs/raw-data-export-page">导出</Anchor>
  * <Anchor target="_blank" href="/marketers/zh/docs/pull-api-raw-data">Pull API</Anchor>

**请注意**：对于搭载了安卓和iOS操作系统的平台，汇总数据和<Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview">原始数据</Anchor>报告的可用性与移动端应用的数据可用性一致。

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 再归因窗口 | 对于CTV、PC和主机平台，再归因窗口期取决于广告主设定的不活跃窗口期（默认为90天）。 |
| 重装激活后的事件 | 归因到首次激活。<Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls#attributed-to-the-first-install">了解详情</Anchor> |
| 再营销 | <ul><li>再归因：支持跨平台到移动端，不支持到其它平台。</li><li>再互动：不支持</li></ul> |
| 归因方法 | 请参考<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#归因方法">CTV、PC和主机端的归因方式</Anchor>说明 |
| 货币 | USD（美元）或广告主在AppsFlyer后台的应用配置中指定的货币 |
| 时区 | UTC |
| 成本数据 | 对于CTV、PC和主机端的应用，广告主必须通过<Anchor target="_blank" href="/marketers/zh/docs/import-cost-data">广告消耗数据上传</Anchor>工具中的邮件上传法来发送其成本数据。 |

</Accordion>

<div data-zendesk-anchors="about-ctv-attribution=appsflyer%E7%9A%84%E8%B7%A8%E7%AB%AF%E5%BD%92%E5%9B%A0%E6%96%B9%E6%A1%88 01H7ZRK7PCNZG54ZQ0804HMR38=appsflyer%E7%9A%84%E8%B7%A8%E7%AB%AF%E5%BD%92%E5%9B%A0%E6%96%B9%E6%A1%88 list-of-supported-ctv-and-gaming-device-types=%E9%80%82%E9%85%8D%E5%B9%B3%E5%8F%B0 01H7ZRK7PCP1KWRX1A5K81F4KR=%E9%80%82%E9%85%8D%E5%B9%B3%E5%8F%B0 h_01J2XT3HFBYD7KX47E6NRP2XZ2=list-of-supporting-ad-networks crossplatform-attribution=%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B 01H8EHHJNBA8NKMX2C8RSV7P31=%E8%B7%A8%E5%B9%B3%E5%8F%B0%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B 01H8EQ4KS75Q62Z7WVNSTDXBZX=direct-attribution-link 01H8EQ4KS7C6HADNKQZYNTTFMF=crossplatform-onelink 01H8EQ4KS7NVYAD6MQ6MM26AVW=srn data-availability=%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01H9G52NKMQG9QD9S3N537BM7N=%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 01H7ZRK7PCJ6BRQZ2AKQTV5Q5E=traits-and-limitations" />

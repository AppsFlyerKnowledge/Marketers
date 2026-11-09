---
title: AppsFlyer归因模型
metadata:
  keywords:
    - Attribution
    - NativeTrack
    - Look-Back
    - Twiiter
    - Multi-Channel
    - Re-Install
    - Facebook
    - media source
    - Advertisers
    - Ad Networks
    - reinstall
    - branch
    - attribution determination
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T10:54:37Z'
  edited_at: '2026-10-14T10:05:19Z'
  id: 207447053
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/207447053
---
> **概要：** 通过AppsFlyer归因模型，我们能判断哪些媒体渠道有效促成了拉新或促活，并将相关的激活或互动行为归因给这些渠道。

 <Image align="center" alt="" src="https://files.readme.io/20b5c0674ce4b20df7c82398d7a769274dd8467d129adbaad0d40e4f37d39091-31937603228177.png" />

<div id="what-is-attribution" />

## 什么是归因？

**归因**用于判断是什么原因促使用户下载应用，或在激活应用后进行各种操作（如再次打开或重新安装）。归因结果分为以下两种：

* **非自然流量**：用户与媒体渠道进行了互动（通常通过展示或点击来完成）
* <strong>自然流量</strong>：用户没有与媒体渠道进行互动。请注意：为了便于理解，我们经常会使用<em>“该用户被归因为自然流量”</em>这样的表达，但是严格来说这种说法是不准确的，因为自然流量不会被归因。

归因能极大地推动拉新和促活的优化，并提升优化效果。

> 👍 **提示**
>
> 如需进一步了解归因，我们在<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7766/play/18609/attribution-101-part-1">AppsFlyer充电站里为您准备了相关课程</Anchor>，视频虽短，但干货满满！

<div id="what-is-an-app-install" />

## 如何计算一次激活？

**归因模型**是由一系列规则组成的，用于判断转化路径中的哪些营销触点促成了哪些事件。应用营销生态中的每一个参与方，不管是Google Play、App Store、CTV、PC端、主机平台，还是Meta ads和X Ads等广告平台，亦或移动度量供应商，他们各自都有自己的归因模型，每个模型对于激活和事件的计算方式都有所不同。

但归因的关键并不在于这些模型间的差异，而在于其规则是否清晰明确、公平公正，以及是否能帮助广告主优化他们的广告计划并比较不同渠道的用户质量。

了解合作方所使用的模型和规则至关重要，特别是要理清适用于AppsFlyer的模型和各种方法之间的细微区别。

根据AppsFlyer的归因模型，可归因事件需符合以下条件：

* 在拉新获客场景中：用户下载并启动应用后，AppsFlyer将该行为计为**激活**并进行归因。也就是说，AppsFlyer将**应用首次启动的时间点计为激活时间戳**，这样的设定与广告平台或应用商店有所不同，前者按用户与广告互动的时间计算，后者则按用户下载应用的时间计算。
* 在[再营销](/docs/appsflyer-attribution-model#retargeting-attribution)场景中：
  * **再互动**
  * **再归因（reattribution）**

<div id="attribution-methods" />

## 归因方法

AppsFlyer使用以下各种方法进行归因：

<table><thead><tr><th>方法</th><th>用户设备ID</th><th>技术</th><th>归因方</th><th><p>安卓（Google Play和第三方商店）</p></th><th>iOS </th><th>Universal Windows Platform（UWP）</th><th>CTV、PC和主机平台（3）</th></tr></thead><tbody><tr><td> <a href="#install-referrer-android-only">Referrer</a>归因（1）</td><td>否</td><td>确定性匹配</td><td>AppsFlyer</td><td>是（2）</td><td>否</td><td>是</td><td>否</td></tr><tr><td> <a href="#device-id-matching">设备ID匹配</a>（1）</td><td>是</td><td>确定性匹配</td><td>AppsFlyer</td><td>是 </td><td>是</td><td>是</td><td>是</td></tr><tr><td> <a href="#probabilistic-modeling">概率模型</a>（1）</td><td>否</td><td>概率匹配</td><td>AppsFlyer</td><td>是 </td><td>是 </td><td>否</td><td>是</td></tr><tr><td> <a href="#aggregated-advanced-privacy-aap">汇总层级的高级隐私保护（AAP）</a>（1）</td><td>否</td><td>汇总</td><td>AppsFlyer</td><td>否</td><td>是</td><td>否</td><td>否</td></tr><tr><td> <a href="#preload-campaigns">预装归因</a>（1）</td><td>否</td><td>确定性匹配</td><td>AppsFlyer</td><td>是</td><td>否</td><td>是</td><td>否</td></tr><tr><td> <a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork</a>（SKAN）</td><td>否</td><td>确定性匹配</td><td>苹果</td><td>否</td><td>是</td><td>否</td><td>否</td></tr><tr><td> <a href="./apple-ads-integration-setup" target="_blank">Apple Search Ads</a>（1）</td><td>否</td><td>确定性匹配</td><td>苹果</td><td>否</td><td>是</td><td>否</td><td>否</td></tr><tr><td> <a href="./appsflyer-attribution-model#deep-link">深度链接</a>（1）</td><td>否</td><td>确定性匹配</td><td>AppsFlyer</td><td>是</td><td>是</td><td>是</td><td>否</td></tr><tr><td colspan="7"><p>（1）AppsFlyer面板和报告中有时会称其为传统（Classic）归因方式。</p><p>（2）第三方商店可用</p><p>（3）参见<a href="./ctv-pc-and-console-platform-attribution-concepts#适配平台" target="_blank"><span>CTV、PC端和主机</span>平台完整列表</a></p></td><td> </td></tr></tbody></table>

<div id="attribution-method-priorities-attribution-waterfall" />

### 各种归因方式的优先级（归因瀑布流）

如果在一个新增激活前发生了多个有效互动，**AppsFlyer会把该激活优先归因到点击，其次是展示；并会优先使用确定性归因，其次是概率匹配**。下图展示了Appsflyer的归因优先级。

<Image align="center" alt="Attribution method priorities 23.png" src="https://files.readme.io/d88dcebc9095b2f92e24817ab0041d015c80201ab8cda6233a41ea4b626aa998-51911487537937.png" />

以下内容详细阐释了AppsFlyer的各个归因模型。

<div id="install-referrer-android-only" />

<Accordion title="Referrer归因（安装引荐来源 ，仅限安卓）">

* 从Google Play及部分其他应用商店下载的安卓应用一般可以通过Install Referrer来归因。referrer会提供跳转到安卓应用商店之前的原始URL。这是安卓端归因的主要方法。目前Google Play、华为应用商店、三星盖乐世商店和小米GetApps应用商店都支持激活referrer归因。<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution#referrer-implementation%E2%80%94thirdparty-android-app-stores">支持referrer归因的第三方应用商店。</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/meta-ads-integration-setup#Meta_install_referrer_anchor">Meta install referrer：AppsFlyer</Anchor>可以接收设备本地存储中的广告系列原数据，从而对支持安卓应用的Meta ads归因。这些数据用于归因衡量（Meta端内归因）。

</Accordion>

<div id="device-id-matching" />

<Accordion title="设备ID匹配">

在传统归因模式中，广告平台会读取用户的设备信息，并在用户点击广告链接或浏览广告时将设备ID发送给AppsFlyer。这样，AppsFlyer就能将发生广告互动的设备ID与AppsFlyer SDK获取的设备ID进行匹配。

设备ID匹配是iOS系统中的主要归因方法。

可用于匹配的ID有以下几种:

* **iOS设备**：IDFA、IDFV
* **支持Google Play服务的安卓设备：** GAID
* **不支持Google Play服务的安卓设备：** OAID、Android ID、IMEI、Fire ID

设备ID可以使用归因链接上的SHA1或MD5进行加密处理。

</Accordion>

<div id="device-id-matching-using-idfv-ios" />

<Accordion title="使用IDFV（iOS）进行设备ID匹配">

* 对于操作系统为iOS 6.0及以上的设备，在传统归因模式中，我们可以读取其供应商标识符（IDFV），不受Apple的<Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor>（应用跟踪透明度框架）和LAT（限制广告跟踪）机制的影响。广告主可以通过IDFV来交叉推广旗下的不同应用。
* AppsFlyer SDK默认收集IDFV。
* <Anchor target="_blank" href="https://developer.apple.com/documentation/uikit/uidevice/1620059-identifierforvendor">根据Apple的说法，</Anchor>*只要是来自同一家供应商的应用，它们在同一台设备上的IDFV值都是一样的。*
* 当用户第一次激活某个厂商的应用时，Apple就会生成一个对应的IDFV。也就是说，Apple会检查设备上是否有来自同一家厂商的其他应用程序。因此，如果用户删除了某厂商旗下的所有应用程序之后再下载并激活该厂商的产品，Apple就会生成一个新的IDFV。
* 由于IDFV能改善归因效果，因此如果条件允许，请务必发送IDFV。我们会在以下场景中用到IDFV：
  * 交叉推广归因。
  * 同一设备上的卸载重装归因。
  * 原始数据报告。
  * 受众定向。

</Accordion>

<div id="device-id-matching-for-selfreporting-networks" />

<Accordion title="自归因平台的设备ID匹配">

在传统归因模式中，当用户首次打开相关应用时，AppsFlyer会检查应用配置，判断是否有来自<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#与appsflyer对接的srn">自归因平台</Anchor>（SRN）的流量，如Meta ads、Snapchat和Google Ads等。

AppsFlyer会使用新增激活的唯一设备ID去查询该应用配置的所有自归因平台（SRN）。这是通过SRN授权AppsFlyer使用的MMP (移动监测合作伙伴) API完成的。根据返回的结果, AppsFlyer可以将新增激活归因给相应的SRN。

</Accordion>

<div id="probabilistic-modeling" />

<Accordion title="概率模型">

概率匹配模型是一种利用机器学习来预估广告活动效果的统计技术，能够对以下两种数据进行匹配：

* 用户点击或浏览广告时收集到的数据（前提是概率匹配功能已启用）
* 用户打开应用时收集到的数据

**功能特点**

* 使用统计学原理，而不是通过唯一ID进行匹配。
* 概率匹配是一种备选方案，在追踪码或广告标识符不可用时帮助我们进行归因。由于确定性归因法可以把点击行为匹配到追踪码或ID，因此具有更高的优先级。也就是说，在归因窗口期内，如果条件允许，我们会先使用确定性归因法。
* 也就是说这个窗口期是会自动变化的，但比其他方法的窗口期要短（最多24小时）。
* 点击型概率匹配功能是默认开启的。
* 如需使用浏览型概率模型归因，请在应用配置页面和非SRN的渠道对接选项卡中开启相应的开关。对于CTV、PC端和主机端应用，该功能默认开启。

#### 适用于广告平台的概率模型归因参数

使用概率模型归因的广告平台必须在归因链接或HTTP请求header中发送以下参数：

* <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_os_version">af\_os\_version</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_model">af\_model</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_ip">af\_ip</Anchor>

</Accordion>

<div id="aggregated-advanced-privacy-aap" />

<Accordion title="汇总层级的高级隐私保护（AAP）">

汇总层级的高级隐私保护（Aggregated Advanced Privacy，简称AAP）是一种传统归因方式。使用这种归因方式时，我们会以汇总的方式呈现广告活动的效果数据，防止以任何形式对用户进行跨设备、跨平台的记录，或一对一地识别出用户或设备。

AAP将Apple SKAdNetwork作为隐私保护的最低标准。除自有媒体和ATT授权用户等Apple明确允许追踪的情况外，AAP是iOS 14.5+设备上的默认归因模型。

与其他归因方法不同，AAP机器学习算法的目标是更准确地通过数据汇总归因来衡量投放效果，而不是匹配到终端用户。

</Accordion>

<div id="preload-campaigns" />

<Accordion title="预装广告">

在预装广告的传统归因场景中，预装渠道会在设备出厂或激活时就将应用安装在设备上。预装渠道包括以下几种：

* 原始设备制造商（OEM）
* 应用探索平台
* 移动运营商

预装广告的归因方式共有三种。广告主可以同时使用这三种方式，不会造成彼此干扰。

下表列出了这三种归因方式及其主要特点。您可以点击第一列中的各个链接，进一步了解其对应的预装方式。

<table><thead><tr><th>预装归因方式</th><th>使用场景</th><th>从设备激活到应用打开的信息\*</th><th>回溯窗口\*\*</th><th>原始数据中的匹配类型</th></tr></thead><tbody><tr><td> <a href="./set-up-appsflyer-preload-referrer-attribution" target="_blank">AppsFlyer referrer</a>\*</td><td><ul><li>出厂预装</li><li>设备激活时预装</li></ul></td><td>是</td><td><ul><li>最长180天</li><li>默认90天</li></ul></td><td><ul><li>预装：preload_rfr</li><li>点击下载：af_referrer</li></ul></td></tr><tr><td> <a href="./measure-preload-campaigns-with-google-play-install" target="_blank">Google Play auto-install</a>（PAI云预装归因）\*\*</td><td>设备激活时预装（适用于Google Play中的应用）</td><td>否</td><td><ul><li>最长180天</li><li>默认90天</li></ul></td><td>preload_pai</td></tr><tr><td> <a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">通过System Property或manifest实现的出厂预装归因（安卓）</a>\*\*</td><td><ul><li>出厂预装</li><li>设备激活时预装</li></ul></td><td>否</td><td>无限制</td><td>preload_conf</td></tr><tr><td colspan="5"><p>\* AppsFlyer预装来源referrer归因方案能够呈现并衡量设备初次激活以及应用首次打开的数据以及两者之间的差别。这样您就可以了解具体渠道的预装设备激活数量，以及相关应用的首次打开时间。</p><p>另两种归因方式仅在应用首次打开后判定归因结果，不提供应用首次打开前已完成预装的设备数量。</p><p>\*\* 该过程可能需要数天或数周，即从用户首次启动设备开始，直到他们首次打开预装应用为止。因此预装广告在AppsFlyer判定归因结果时的优先级最高，且回溯窗口也更长。</p></td></tr></tbody></table>

</Accordion>

<div id="deep-link" />

<Accordion title="深度链接">

这是一种仅适用于再互动的传统归因方式，不需要让用户跳转到应用商店下载应用，因此URL中的信息可以直接关联到点击（以及后续的应用打开）。我们将这种归因方式称为深度链接，这是因为用于归因再互动的信息是通过深度链接URL传递的。

</Accordion>

<div id="attribution-methods-per-media-source-and-appsflyer-feature" />

### 按渠道类型梳理的归因方法和AF功能

在下面的章节中，我们按以下三个纬度详细剖析了各种归因方法的适配情况：

* 媒体渠道：自有或付费
* 所使用的AppsFlyer功能
* 用户设备：安卓或iOS。

<div id="owned-media" />

<Accordion title="自有媒体">

<table><thead><tr><th rowspan="2">Media source（媒体渠道）</th><th rowspan="2">功能</th><th colspan="2">归因方法</th></tr><tr><th>安卓</th><th>iOS</th></tr></thead><tbody><tr><td>自有媒体：电子邮件（包括ESP）、短信、社交媒体帖子、网红/联盟营销、平面媒体等</td><td><a href="./onelink-guide" target="_blank"><span>OneLink</span></a></td><td><ul><li>安装来源追踪码</li><li>概率模型</li></ul></td><td>概率模型</td></tr><tr><td rowspan="2">有付费或自然流量的自有移动网站/落地页</td><td><a href="./smart-banners-mobile-web-to-app-for-marketers" target="_blank">智能横幅</a></td><td><ul><li>安装来源追踪码</li><li>概率模型</li></ul></td><td>概率模型</td></tr><tr><td><a href="./onelink-smart-script-overview" target="_blank">OneLink智能脚本</a></td><td><ul><li>安装来源追踪码</li><li>概率模型</li></ul></td><td>概率模型</td></tr><tr><td rowspan="2">自有移动应用</td><td><a href="./user-invite-attribution" target="_blank">用户邀请/引荐</a></td><td><ul><li>安装来源追踪码</li><li>概率模型</li></ul></td><td>概率模型</td></tr><tr><td><a href="./cross-promotion-attribution-for-marketers" target="_blank">交叉推广</a></td><td><ul><li>安装来源追踪码</li><li>设备ID匹配</li></ul></td><td>设备ID匹配</td></tr></tbody></table>

</Accordion>

<div id="paid-media" />

<Accordion title="付费媒体">

<table><thead><tr><th rowspan="2">Media source（媒体渠道）</th><th colspan="3">归因方法</th></tr><tr><th>安卓</th><th>iOS</th><th><strong>CTV、PC和主机平台</strong></th></tr></thead><tbody><tr><td><a href="./self-reporting-networks-srns" target="_blank">SRN</a></td><td>设备ID匹配</td><td><ul><li>设备ID匹配</li><li>AAP（iOS 14.5+）</li><li>SKAdNetwork（iOS 14+）</li></ul></td><td>设备ID匹配</td></tr><tr><td><ul><li>通过<a href="./set-up-an-integrated-partner#attribution-link-tab" target="_blank">渠道归因链接</a>对接的广告平台（非SRN） </li><li><span>CTV、PC和主机平台</span></li></ul></td><td><ul><li>安装来源追踪码</li><li>设备ID匹配</li><li>概率模型</li></ul></td><td><ul><li>设备ID匹配</li><li>概率匹配（iOS 14.5之前的版本）</li><li>AAP（iOS 14.5+）</li><li>SKAdNetwork（iOS 14+）</li></ul></td><td> </td></tr><tr><td><a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">随设备预装</a></td><td>预装</td><td>--</td><td> </td></tr></tbody></table>

</Accordion>

<div id="engaged-click-attribution" />

<div id="user-engagement-attribution-types" />

## 用户互动归因类型

我们通过设备ID匹配和概率匹配技术，将点击和浏览行为归因到媒体渠道。

<div id="clickthrough-attribution" />

<Accordion title="点击型归因">

广告点击行为是大多数激活的来源，这些广告包括横幅、视频和插屏等样式。

用户点击广告后触发回溯，窗口期默认为7天。在回溯窗口期内发生的激活将作为非自然流量归因到媒体渠道。在窗口期之后发生的激活则视为自然流量，也就是我们常说的“归因到自然流量（organically attributed）”。

* 点击型归因的回溯窗口一般是七天，您也可以根据您和渠道之间的协议来自行调整窗口期的时长。
* 您在AppsFlyer中设置的SRN回溯窗口需要与SRN本身的回溯窗口保持一致。

<table><thead><tr><th rowspan="2"><strong>归因类型</strong></th><th rowspan="2"><strong>归因方法</strong></th><th rowspan="2">范围</th><th rowspan="2">默认</th></tr></thead><tbody><tr><td rowspan="2"><p>点击归因</p><p>（所有已对接渠道）</p></td><td>Referrer、ID匹配</td><td>1–30天</td><td>7天</td></tr><tr><td>概率模型</td><td>0–24小时</td><td><ul><li>自动调整</li><li>由AppsFlyer确定</li></ul></td></tr></tbody></table>

<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">进一步了解回溯窗口</Anchor>

</Accordion>

<div id="viewthrough-attribution" />

<div id="engaged-view-attribution" />

<Accordion title="浏览型归因">

我们也可以对仅浏览而未点击广告的用户进行归因，把他们匹配到该广告的投放平台。

浏览型归因的回溯窗口：

* 比点击归因的时间短
* 可自行调整。

这类归因不仅对视频广告点击率较低的视频广告平台非常有利，投放常规广告的传统广告平台也能从中受益。

在既有点击也有浏览的情况下， 总是**优先归因到点击** ，因为点击是更为主动的互动行为。

<table><thead><tr><th><strong>归因类型</strong></th><th><strong>归因方法</strong></th><th><strong>范围</strong></th><th> <strong>默认</strong><br/> </th></tr></thead><tbody><tr><td rowspan="2"><p>浏览型（适用于<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">指定对接渠道</a>）</p></td><td>ID匹配</td><td>0–24小时</td><td>1天</td></tr><tr><td>概率模型</td><td>0-24小时</td><td><ul><li>自动调整</li><li>由AppsFlyer确定</li></ul></td></tr></tbody></table>

**请按以下方式启用浏览型归因：**

* 在<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#浏览型归因窗口期">窗口期配置部分</Anchor>设定回溯窗口。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/measure-view-through-engagements">浏览型归因</Anchor>。

</Accordion>

<div id="advanced-attribution-topics" />

## 高级归因话题

<div id="in-app-events" />

<Accordion title="应用内事件">

对于应用激活、重装激活/再归因，AppsFlyer会使用设备ID或具有唯一性的AppsFlyer ID将**应用内事件归因到相关的媒体渠道**。广告主可以使用该信息通过相关应用的原始数据追溯用户链路。在汇总数据中，设备ID/AppsFlyer ID用于计算独立用户的数量，比如完成某个应用内事件的独立用户数。

如需进一步了解事件归因，请查看<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview?query=in%20app%20event#how-does-appsflyer-attribute-events">此文档</Anchor>。

</Accordion>

<div id="assisted-installs" />

<Accordion title="助攻激活">

AppsFlyer会根据激活前的最后一次广告点击或广告展示（若无点击），把激活一对一地归因到渠道。

在助攻激活（即多触点归因）场景中，渠道/广告在归因窗口内触达了用户，但该触点不是用户激活前的最后一次互动行为，我们将这样的情况视为间接促成激活的“助攻”。

AppsFlyer会将这些形成助攻的渠道作为促成激活的辅助方记录激活报告中。

请点击<Anchor target="_blank" href="/marketers/zh/docs/measure-assisted-installs">此链接</Anchor>查看详情。

</Accordion>

<div id="reinstalls" />

<Accordion title="重装激活">

如果用户在激活应用后，将其卸载再重新激活，AppsFlyer就会将该行为视为重装激活。AF会根据<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口期</Anchor>对其进行界定，逻辑如下：

* 如果重装激活发生在窗口期之后，AppsFlyer会将其计为新增激活。
* 如果重装激活发生在窗口期内，则分以下两种情况：
  * 用户在重新激活之前与再营销广告进行了互动：视为<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销重装激活</Anchor> （又称再归因）。
  * 用户没有与再营销广告互动/用户与拉新广告互动：不计为激活，重装激活用户的应用内事件会归因到自然量或初始激活，具体取决于<Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls#速览">**重装激活后事件归因**</Anchor>的状态。

如需进行设备测试和多次激活，请在AppsFlyer系统中为相关设备<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices">加白</Anchor>。对于未加白的设备，AF仅记录第一次激活。

请注意：AppsFlyer可以对没有设备ID的iOS重装激活进行更准确的归因，但需要您在AF后台的<Anchor target="_blank" href="/marketers/zh/docs/app-settings#reinstall-detection-using-ondevice-storage-ios-only">应用配置页</Anchor>中打开这个功能。

<div id="reinstalling-ios-apps-that-are-backed-up-in-icloud" />

#### 重新激活在iCloud中备份过的iOS应用

如果用户在iCloud上备份了一个应用，之后再从备份中恢复该应用（不管是否恢复到同一台设备上），AppsFlyer都不会将其作为新增激活或重装激活。在该场景中，用户的AppsFlyer ID和归因数据保持不变。

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="再营销归因">

<Image align="center" alt="Retargeting_-_Flow__2_.png" src="https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png" />

用户如果在<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口</Anchor>（默认为90天）内重新激活应用程序，AF会把该行为视作重装激活进行归因。如果用户与再营销广告互动后重新激活应用，AF会将该行为计为再营销重装激活（即再归因），您可以在<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销</Anchor>报告中查看相关数据。

</Accordion>

<div id="app-updates" />

<Accordion title="应用更新">

* 在存量用户更新应用版本的场景中，如果AppsFlyer此前已归因过该用户，则不会再对该行为进行归因。请注意：如果您从其他MMP迁移到AppsFlyer，那么在迁移完成后，存量用户第一次打开应用时，AF会将其归因为自然流量。
* 您可在<Anchor target="_blank" href="/marketers/zh/docs/sdk-information-version-consent-dashboard">SDK信息面板</Anchor>中查看按应用版本细分的用户数量指标。

</Accordion>

<div data-zendesk-anchors="what-is-attribution=%E4%BB%80%E4%B9%88%E6%98%AF%E5%BD%92%E5%9B%A0 01H8GG9XPSS8KA9CHPD6ECNR2J=%E4%BB%80%E4%B9%88%E6%98%AF%E5%BD%92%E5%9B%A0 01H8GG9XPSA15N5CSHGZNBWSAV=%E6%8F%90%E7%A4%BA what-is-an-app-install=%E5%A6%82%E4%BD%95%E8%AE%A1%E7%AE%97%E4%B8%80%E6%AC%A1%E6%BF%80%E6%B4%BB 01EDRHGMTXK94Y97DPKFAMCJ5B=%E5%A6%82%E4%BD%95%E8%AE%A1%E7%AE%97%E4%B8%80%E6%AC%A1%E6%BF%80%E6%B4%BB attribution-methods=%E5%BD%92%E5%9B%A0%E6%96%B9%E6%B3%95 01EDRHGMTXCRNVXS9JGHQ1JAQT=%E5%BD%92%E5%9B%A0%E6%96%B9%E6%B3%95 attribution-waterfall=%E5%90%84%E7%A7%8D%E5%BD%92%E5%9B%A0%E6%96%B9%E5%BC%8F%E7%9A%84%E4%BC%98%E5%85%88%E7%BA%A7%E5%BD%92%E5%9B%A0%E7%80%91%E5%B8%83%E6%B5%81 h_01JBC8582ABTE00W29PM5Y5X0B=%E5%90%84%E7%A7%8D%E5%BD%92%E5%9B%A0%E6%96%B9%E5%BC%8F%E7%9A%84%E4%BC%98%E5%85%88%E7%BA%A7%E5%BD%92%E5%9B%A0%E7%80%91%E5%B8%83%E6%B5%81 01H8GG9XPS6P3CXX5AN2KY8WN4=install-referrer-android-only 01H8GG9XPSGVK90FV0K9HZARH7=device-id-matching 01H8GG9XPSQZPWJZ0BC0EAMB97=device-id-matching-using-idfv-ios 01H8GG9XPSV247F3JRCR870JK0=device-id-matching-for-selfreporting-networks 01EDRHGMTXHAKWZK99Q2X86BND=probabilistic-modeling probabilistic-modeling-parameters-for-ad-networks=%E9%80%82%E7%94%A8%E4%BA%8E%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E7%9A%84%E6%A6%82%E7%8E%87%E6%A8%A1%E5%9E%8B%E5%BD%92%E5%9B%A0%E5%8F%82%E6%95%B0 h_01HEMSHXKGNW2DF41094BXY0FY=%E9%80%82%E7%94%A8%E4%BA%8E%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E7%9A%84%E6%A6%82%E7%8E%87%E6%A8%A1%E5%9E%8B%E5%BD%92%E5%9B%A0%E5%8F%82%E6%95%B0 01H8GG9XPSZ5CPKNSCV7NF1MKW=preload-campaigns attribution-methods-per-media-source-and-appsflyer-feature=%E6%8C%89%E6%B8%A0%E9%81%93%E7%B1%BB%E5%9E%8B%E6%A2%B3%E7%90%86%E7%9A%84%E5%BD%92%E5%9B%A0%E6%96%B9%E6%B3%95%E5%92%8Caf%E5%8A%9F%E8%83%BD 01H8GG9XPTXDR41QANF4XVSZMM=%E6%8C%89%E6%B8%A0%E9%81%93%E7%B1%BB%E5%9E%8B%E6%A2%B3%E7%90%86%E7%9A%84%E5%BD%92%E5%9B%A0%E6%96%B9%E6%B3%95%E5%92%8Caf%E5%8A%9F%E8%83%BD 01H8GG9XPT65G88DE8548HZREE=owned-media 01H8GG9XPTADWMQ37WBB6P9WVS=paid-media user-engagement-attribution-types=%E7%94%A8%E6%88%B7%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0%E7%B1%BB%E5%9E%8B 01EDRHGMTX7851H14R20F9KNAN=%E7%94%A8%E6%88%B7%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0%E7%B1%BB%E5%9E%8B 01EDRHGMTXJ7WKTWQXFCHTD9AV=clickthrough-attribution 01EDRHGMTXN0Y0ZRVBX7HHW7NN=viewthrough-attribution advanced-attribution-topics=%E9%AB%98%E7%BA%A7%E5%BD%92%E5%9B%A0%E8%AF%9D%E9%A2%98 01EDRHGMTYYXBSCDPKXCDK1641=%E9%AB%98%E7%BA%A7%E5%BD%92%E5%9B%A0%E8%AF%9D%E9%A2%98 01EDRHGMTYMH3SVNBTQ28D4F42=in-app-events 01EDRHGMTY2CF0B70T3RAGPCJ1=reinstalls reinstalling-ios-apps-that-are-backed-up-in-icloud=%E9%87%8D%E6%96%B0%E6%BF%80%E6%B4%BB%E5%9C%A8icloud%E4%B8%AD%E5%A4%87%E4%BB%BD%E8%BF%87%E7%9A%84ios%E5%BA%94%E7%94%A8 01EDRHGMTYDSNJKQNPNYFXJPAZ=%E9%87%8D%E6%96%B0%E6%BF%80%E6%B4%BB%E5%9C%A8icloud%E4%B8%AD%E5%A4%87%E4%BB%BD%E8%BF%87%E7%9A%84ios%E5%BA%94%E7%94%A8 01EDRHGMTYYB9XVM5CBWSPJGMN=retargeting-attribution 01EDRHGMTYTQRMG1W7ZBW4G6W4=app-updates" />

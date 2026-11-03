---
title: SKAdNetwork（SKAN）解决方案指南
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-07-25T21:19:42Z'
  edited_at: '2026-10-14T10:03:50Z'
  id: 360011420698
  locale: zh-cn
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/zh-cn/articles/360011420698
---
> **概要**：本文将为您讲解如何通过SKAN对应用激活进行归因。

![5754](https://files.readme.io/a970d7b0e8da300ded2138f941bf2e891f32d396c8500292534992a4b4449d71-30757780264337.png)

## SKAN

SKAdNetwork（SKAN）是Apple iOS系统的一部分，能让广告主在确保用户隐私的前提下衡量投放效果。SKAN的归因不涉及IDFA或其他设备ID，且无需用户进行ATT授权。

> 👍 **提示**
>
> * iOS 15上线后，建议您将<Anchor target="_blank" href="/marketers/zh/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">SKAN的回传数据备份发送</Anchor>给AppsFlyer，这样AppsFlyer就能够验证回传中的转化值是否被篡改。
> * 如需进一步了解AppsFlyer的SKAN解决方案，我们在<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/internal/view/elearning/7810/ios14-and-skadnetwork">AppsFlyer充电站里为您准备了相关课程</Anchor>，视频虽短，但干货满满！

**定义**

* <Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">SDK</Anchor>**：确保应用中接入了最新版本的AppsFlyer iOS SDK。**
* **SKAN衡量窗口期**：适用于SKAN 4+。用户激活应用后共有3个窗口期，用于衡量用户行为，分别是：
  * 窗口1（Window 1）：1-2天
  * 窗口2（Window 2）：3-7天
  * 窗口3（Window 3）：8-35天
* **转化值（CV）**：在SKAN 4的衡量窗口期或SKAN 3及以下的用户行为窗口期（Activity Window）结束后，基于iOS回传数据得出的用户质量信息。您可以直接通过AppsFlyer SDK设置CV值，也可以手动设置CV值。如需手动设置，请使用<Anchor target="_blank" href="/marketers/zh/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor>（解析）模式上传您的CV映射文件。
  * SKAN 4+中的CV值有精细值和粗略值两种。
* **转化值操作台**：AppsFlyer为广告主提供的解决方案，是一个将转化值（CV）映射到事件的基础构架。
* **解决方案**：SDK、底层架构、转化值操作台以及AppsFlyer平台的协同。该解决方案通过面板数据分析、报告和回传，为广告主和广告平台提供LTV数据。
* **用户行为窗口期**仅适用于SKAN 3及以下版本。该窗口期有固定的时长，默认为24小时，从应用首次启动开始计时。如果您启用了SKAN 4+，但用户设备或广告平台尚不支持SKAN 4，则用户行为窗口期自动设置为48小时。

本文解释了底层逻辑和解决方案的相关特点。如需了如何设置衡量方式，请参考<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">SKAN转化值操作台指南</Anchor>。

<div id="about-apple-skan" />

<Accordion title="SKAN简介">

| 主要特点 | 说明 |
| --- | --- |
| 前期准备 | 请按以下步骤在应用中启用SKAN：<ul><li>在广告主应用（即您要推广的应用）中接入AppsFlyer SDK以设置CV值，也可以使用<Anchor target="_blank" href="/marketers/zh/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor>（解析）模式设置CV值。</li><li>流量方应用（即展示广告的应用）：必须<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app">配置对应的广告主应用</Anchor></li><li><Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/registering_an_ad_network">广告平台必须在Apple注册</Anchor></li></ul>**\*请注意：**请确保您的应用中没有接入其他可以设置转化值的SDK。 |
| 支持 | <ul><li>适配的SKAdNetwork版本取决于用户使用的iOS版本：<ul><li>iOS 11-13：V1（只有激活数据，没有CV值）</li><li>iOS 14-14.5：V2+（有CV值）</li><li>iOS 14.6-16：V3（有CV值）</li><li>iOS 16.1+：V4+（有3个窗口期，分为精细值和粗略值两种CV）</li></ul></li><li>端到端（app-to-app）归因</li></ul> |
| 局限性 | <ul><li>不适用于Apple Search Ads</li><li>不适用于移动网页。</li><li>SKAN 4之前的广告系列编号<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skstoreproductparameteradnetworkcampaignidentifier">仅限于1-100之间</Anchor>，也就是说一个应用在一个广告平台上只能有100个独立的广告系列。 广告平台会把这些广告系列ID和名称发送给AppsFlyer，广告主可以在AppsFlyer的数据面板和报告中查看相关信息。</li><li>从SKAN 4开始，来源标识符（Source Identifier）的范围为1-10,000。</li><li>自然量：SKAN不支持自然量的衡量。</li><li>不支持再互动归因。</li></ul> |
| SKAN归因原理 | <ul><li>SKAN基于以下<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">模型</Anchor>进行归因：<ul><li>用户点击广告后，在30天内安装（下载）相关应用，接着在下载后的60天内首次打开应用。</li><li>用户在与广告互动后的24小时内安装（下载）应用，并在下载后的60天内首次打开应用。</li><li>SKAdNetwork V2.2调整了归因优先级，此后的点击型归因优先级高于浏览型归因。具体的SKAN可用版本取决于用户使用的iOS版本。</li><li>iOS系统会将归因数据回传给带来用户的广告平台。从iOS 15开始，广告主可以把回传数据的备份直接发送给AppsFlyer。</li></ul></li></ul> |
| 群组匿名性阈值（Crowd Anonymity） | 为了保护用户隐私，Apple会限制回传中所包含的数据。Apple的用户隐私保护政策将回传信息量分为几个梯度，若转化量没有达到对应梯度的阈值，则Apple会相应地限制细粒度或粗粒度CV值、广告主应用ID（Source App ID）或完整来源标识符（Source Identifier）在回传中的上报。<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">了解详情</Anchor> |

</Accordion>

## AppsFlyer的SKAN解决方案

AppsFlyer会根据iOS的SKAN回传来提供汇总的iOS归因结果。这些回传数据先由iOS发送到广告平台，再由广告平台转发到AppsFlyer，其中包含经匿名化处理的归因记录，且每次回传都带有对应的转化值（CV）。转化值是由广告主设置的，用于在激活后最初的一段时间内衡量用户质量。

AppsFlyer的SKAN解决方案能为广告主提供以下功能：

* 汇总各广告平台的回传数据，并使用成本等其他数据加以补充，最终形成面板和报告中的SKAN数据。
* 广告主可以使用AppsFlyer的转化值操作台调整CV值衡量的对象，无需更改应用代码。CV值可用于衡量收入、互动或转化事件。  
  **请注意：** 使用该方案时，AppsFlyer SDK必须是唯一可以设置转化值的SDK，请确保您的应用中没有接入其他可以设置转化值的SDK。

<div id="principles-and-flow" />

<Accordion title="原理和流程">

#### **SKAN归因流程。**

![SKAN_flow_-_Affinity_diagram_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. 广告主在AppsFlyer的转化值操作台中完成SKAN衡量设置。
2. 用户首次打开应用。
3. AppsFlyer在每个衡量窗口期内根据用户行为和广告主设定的CV映射构架设置CV值。
4. 窗口期结束后，iOS向相关的广告平台发送回传，同时向AppsFlyer发送回传备份。回传接收时间会有一定的延迟，具体如下：
   * SKAN 4衡量窗口1:24-48小时
   * SKAN 4衡量窗口2-3：24-144小时
   * SKAN 3：最近一次CV值上升后的24-48小时
5. iOS设备直接把回传数据备份发送到AppsFlyer，然后AF将其转发到广告主指定的端点。详见<Anchor target="_blank" href="/marketers/zh/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">如何将SKAN回传数据备份发送到AppsFlyer</Anchor>。
6. 广告平台扩充回传数据，然后转发给AppsFlyer，或者由SRN通过API向AF发送回传数据。
7. AppsFlyer验证并解析CV。AF会先对解析后的数据进行记录并归因，然后广告主就可以通过AF的面板、报告和API拉取这些数据。

为了克服SKAN底层构架的功能性和结构性限制，AF的SKAN解决方案考虑到了下列因素：

| 主要特点 | 说明 |
| --- | --- |
| <span id="data-collection"></span>数据收集 | <ul><li>广告主可以从多个广告平台收集SKAN回传数据。</li><li>广告主无需分别对接不同渠道，节省大量时间和人力。</li></ul> |
| <span id="data-validation"></span>数据验证 | <ul><li>确保所有回传数据都带有Apple签名，这样就能减少数据篡改的发生几率。</li><li>通过transaction ID（交易ID）验证回传数据的唯一性。</li></ul> |
| <span id="data-enrichment"></span>数据丰富度 | <ul><li>利用额外的数据点扩充SKAN回传数据，形成全面的ROI分析报告，包括广告平台提供的广告系列名称等。</li><li>数据点包括展示、点击、成本等等。</li></ul> |
| <span id="data-delivery"></span>数据传输 | 您可以通过以下途径获取SKAN扩充数据：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN面板</Anchor></li><li>[可下载的报告](/docs/skadnetwork-skan-solution-guide#reporting-options)</li></ul> |
| <span id="seamless-integration"></span>无缝对接 | <ul><li>广告主无需在应用配置页面进行任何额外操作。</li><li>广告主无需修改应用代码，只需在应用中接入最新版的SDK。</li><li>可适应Apple对SKAN底层构架的后续更新。</li></ul> |
| <span id="agility"></span>灵活应变 | 广告主可以根据需要在面板中更改衡量配置。 |

</Accordion>

<div id="conversion-studio" />

<Accordion title="转化值操作台">

AppsFlyer<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">转化值操作台</Anchor>是SKAN解决方案的核心组成部分。该产品的可配置性极高，可细化到转化值的每一位比特，便于广告主充分利用SKAN回传。您可以精确设置CV中需要对哪些数据进行加密以用于衡量，比如在激活后要衡量多长时间内的哪些用户行为。我们提供多个衡量模式，用于CV值的配置。

| 类型 | 衡量模式 | 说明 | 用户行为窗口期 |
| --- | --- | --- | --- |
| 可配置 | SKAN 4.0<br /><br />【推荐】 | 针对3个可配置的衡量窗口期，分别设置收入、转化（应用内事件）和互动的衡量方式。 | <ul><li>窗口1（Window 1）：1-2天</li><li>窗口2（Window 2）：3-7天</li><li>窗口3（Window 3）：8-35天</li></ul> |
| 可配置 | <Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio#custom">自定义</Anchor> | 在可配置的用户行为窗口期内设置收入、转化（应用内事件）和互动的衡量方式 | 12小时-63天 |
| 固定 | 收入<br /><br />【默认】<br /><br />【历史】 | 在下列区间中任选一个，用以衡量收入：<ul><li>1-630美元，以10美元为最小单位</li><li>1-63美元，以1美元为最小单位</li><li>0.01-0.63美元，以0.01美元为最小单位</li></ul> | 24小时 |
| 固定 | 转化<br /><br />【历史版本】 | 选择1-6个应用内事件 | 24小时 |
| 固定 | 广告交互<br /><br />【历史版本】 | 用户完成某一事件的次数 | 24小时 |
| 可配置 | <Anchor target="_blank" href="/marketers/zh/docs/skan-cv-decode-map-your-cv-to-events">Decode（解析）</Anchor> | <ul><li>手动创建用于事件映射的CV值，并在应用中进行对应的CV设置。该方案适用于无法在应用中接入AppsFlyer SDK的广告主。Decode（解析）模式的启用方式如下：从AF后台进入**SKAN转化值操作台**，点击“⋮”选项图标，选择**上传自定义解析映射文件**。</li></ul> | 12-1512小时（63天） |

</Accordion>

## 关于SKAN的其他信息

<div id="reporting-options" />

<Accordion title="报告选项">

SKAN报告不包含用户层级的标识符。

| 报告名称 | 类型 | AF提升数据丰富度 | 传输方式 | 高级功能 |
| --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/skan-aggregated-performance-report-api">SKAN汇总效果报告。</Anchor><br /><br />显示汇总的激活、应用内事件以及收入数据，与SKAN总览面板中的数据一致。 | 按激活日期或数据接收日期汇总 | 是 | API | 否 |
| <Anchor target="_blank" href="/marketers/zh/docs/skan-aggregated-postback-arrival-date-api">SKAN汇总回传报告</Anchor>：<br /><br />SKAN回传的最细粒度的汇总数据。 | 按回传数据接收日期汇总 | 否 | API | 否 |
| <Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports#raw-data-report-types">通过Data Locker生成的SKAN原始数据（行级）报告</Anchor>（请点击链接查看示例）。<br /><br />其中包含下列报告：<ul><li>经渠道扩充后的iOS回传数据</li><li>激活假量</li><li>重新下载（Redownloads）</li><li>应用内事件</li><li>SRN广告维度</li></ul> |  | 是 | Data Locker | 区分。需要购买原始数据功能，无需购买Data Locker功能。 |
| 通过Push API获取的SKAN数据 |  | 是 | Push API | 是 |

</Accordion>

<div id="skadnetwork-solution-implementation-checklist" />

<Accordion title="SKAN解决方案启用流程">

| 不可以。 | 操作 | 说明 | 负责人员 |
| --- | --- | --- | --- |
| 1 | 准备工作 | <ul><li>参阅<Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">SKAN解决方案使用指南</Anchor></li><li>其他相关资料：<Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">应用侧的iOS 14应对措施</Anchor></li></ul> | 市场人员、开发人员 |
| 2 | 配置 | 从AF后台进入<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">SKAN转化值操作台</Anchor>，配置SKAdNetwork方案。 | 营销人员 |
| 3 | 应用侧工作 | 在应用中接入AppsFlyer <Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">SDK V6版本</Anchor><ul><li>无需修改应用逻辑或代码</li><li>本解决方案需要通过应用内事件设置CV。广告主可使用常规方式发送应用内事件，且无需就本解决方案进行单独的测试。</li><li>在App Store提交应用</li><li>无需在App Store完成SKAN注册或其他流程</li></ul> | 开发人员 |
| 4 | 渠道对接 | 渠道需要通过SKAN对接方式与AppsFlyer进行对接。请注意： AppsFlyer的SKAN模拟视图包含所有对接渠道的数据，不考虑其当前的对接状态，因此会与真实的SKAN回传上报的实际数据有所不同。<br /><br />渠道对接要求如下：<br /><br />**非SRN**：<ol><li>确认渠道已获得AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#c-transaction-id">SKAdNetwork能力认证</Anchor>，且您已在渠道后台打开了SKAdNetwork广告数据上报功能。</li><li>确认您[已将应用内事件名称映射](#sending-postbacks-to-integrated-partners)到渠道侧。</li></ol>**Meta ads**：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-interoperation-with-meta-ads">AppsFlyer的SKAN方案与Meta ads的互通设置</Anchor></li></ul> | 营销人员 |

</Accordion>

<div id="troubleshooting-guide" />

<Accordion title="问题排查指南">

| 问题表现 | 说明 |
| --- | --- |
| 面板中未显示任何非自然激活。 | <ol><li>确认**SKAN衡量**开关已打开。<ol><li>从后台进入**配置** > **SKAN转化值操作台**。</li><li>点击选项图标（⋮），检查SKAN衡量的设置。</li></ol></li><li>确认应用中接入的SDK版本为6.2.6及以上。<ul><li>从AF后台进入**对接**> **SDK信息 > 按SDK版本显示用户数**，即可查看。</li></ul></li><li>如果您使用了SDK插件，请确认插件版本支持AF的SKAN解决方案。</li><li>确认您的渠道已对接AppsFlyer且已将iOS回传数据转发给AF。</li></ol> |
| 面板只显示非自然激活，没有应用内事件 | <ol><li>确认应用中接入的SDK版本为6.2.6及以上。<ul><li>从AF后台进入**对接**> **SDK信息 > 按SDK版本显示用户数**，即可查看。</li></ul></li><li>如果您使用了SDK插件，请确认插件版本支持AF的SKAN解决方案。</li><li>如果通过S2S的方式发送事件，请确认**由S2S API发送的应用内事件记录**开关已打开。<ol><li>从后台进入**配置** > **SKAN转化值操作台**。</li><li>**点击选项图标（⋮），确认S2S配置已启用。** 请注意：在Custom（自定义）及Decode（解析）模式中，该配置默认启用，且无法更改。</li></ol></li></ol> |
| 面板显示了激活及部分应用内事件，但仍有事件缺失 | <ol><li>如果通过S2S的方式发送事件，请确认**由S2S API发送的应用内事件记录**开关已打开。<ol><li>从后台进入**配置** > **SKAN转化值操作台**。</li><li>**点击选项图标（⋮），确认S2S配置已启用。** 请注意：在Custom（自定义）及Decode（解析）模式中，该配置默认启用，且无法更改。</li></ol></li><li>在您的<Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports#raw-data-report-types">回传原始数据</Anchor>检查是否所有的事件都已上报。</li></ol> |
| 地理位置（国家）信息不准确 | 地理位置数据是通过以下方式生成的：<ul><li>根据与广告投放相关的国家以及由广告平台上报给AF的国家数据判断。</li><li>通过设备IP地址判断。从iOS 14.6开始，系统仅发送代理服务器地址，因而无法确定用户的真实地理位置。</li></ul> |

</Accordion>

<div id="timing-from-app-install-until-dashboard-and-reports-update" />

<Accordion title="从应用激活到面板和报告更新的时间节点">

| 键 | 节点名称 | 说明 | 示例A | 示例B | 示例C | 示例D | 示例E |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | SKAN 4衡量窗口1 | <ul><li>窗口期内的CV由应用设置</li><li>0-2天</li><li>第2天前可在转化值操作台中锁定窗口</li></ul> | - | - | 2天 | - | - |
| B | SKAN 4衡量窗口2 | <ul><li>窗口期内的CV由应用设置</li><li>3-7天</li><li>第7天前可在转化值操作台中锁定窗口期</li></ul> | - | - | - | 7天 | - |
| C | SKAN 4衡量窗口3 | <ul><li>窗口期内的CV由应用设置</li><li>8-35天</li><li>第35天前可在转化值操作台中锁定窗口</li></ul> | - | - |  | - | 35天 |
| D | SKAN 4衡量窗口1的回传延时 | 24-48小时 | - | - | 24-48小时 | - | - |
| E | SKAN 4衡量窗口2-3的回传延时 | 24-144小时 | - | - | - | 24-144小时 | 24-144小时 |
| F | 用户行为窗口期<br /><br />（不适用于SKAN 4） | <ul><li>窗口期内的CV由应用设置</li><li>窗口期从应用首次打开开始计算</li><li>12小时-63天。</li></ul> | 24小时 | 72小时 | - | - | - |
| G | SKAN计时器<br /><br />（不适用于SKAN 4） | <ul><li>倒计时：24小时</li><li>每次CV值上升后计时器就会归零重启，即从24小时开始倒数计时。</li></ul> | 0-24小时 | 0-24小时 | - | - | - |
| H | SKAdNetwork随机延迟<br /><br />（不适用于SKAN 4） | 随机延迟数据回传。倒计时开始时间取决于F+G的结束时间。 | 0-24小时 | 0-24小时 | - | - | - |
| I | AppsFlyer处理数据 | 当天接收到的回传数据会在次日的UTC时间00:01开始处理，数据会在8小时后准备就绪，也就是说数据处理需要8-32小时。可能出现平均20小时的延迟。假设AF在周一接收到回传数据，就会从周二开始处理该数据，并在UTC时间08:00点之前更新面板。 | 8-32小时 | 8-32小时 | 8-32小时 | 8-32小时 | 8-32小时 |
| J | 总耗时 | 总体消耗时间 | 32-104小时 | 80-152小时 | 80-128小时 | 200-344小时 | 872-1016小时 |

</Accordion>

<div id="organic-metrics-in-the-context-of-skadnetwork" />

<Accordion title="SKAN面板中的自然量指标定义">

SKAN面板中的自然量指标是通过以下机制计算的：

* 用户与媒体渠道互动并安装应用后，SKAN会回传与该用户有关的数据，非自然量指标是基于这些数据生成的。
* AppsFlyer的归因面板包含所有激活的指标，包括自然量和非自然量。  详情请见<Anchor target="_blank" href="/marketers/zh/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side">AppsFlyer归因与SKAN归因的对比</Anchor>。
* 自然量指标是通过总量（A）减去非自然量（B）得出的，A和B的具体含义如下：
  * A = 基于旧版数据总览面板的用户总数
  * B = 由SKAN回传上报的非自然量

**Apple Search Ads注意事项**：在旧版的总览面板中，通过Apple Search Ads买的量会显示为非自然量。但在SKAN逻辑中，这部分用户则被视为自然量。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 渠道权限 | 向广告平台提供回传数据 |
| 代理 | 不支持。也就是说代理商不能对广告平台启用SKAN投放。代理商一定要让广告主对广告平台启用SKAN，千万不要自己去操作。代理商可以说明自己是通过<Anchor target="_blank" href="/partners/zh/docs/getting-started-agency-onboarding#skadnetwork中的代理投放">SKAN代理商认证</Anchor>来获取用户的。 |
| 代理数据透明化 | 不适用 |
| 时区 | UTC |
| 货币 | USD |
| 自然量数据 | 基于SDK事件数据得出。比如，自然激活指标的计算方式如下：由SDK上报的所有激活减去由SKAN上报的非自然激活。 |
| 非自然量数据 | 基于SKAN回传 |
| 数据时效性 | 每日更新 |
| 历史数据 | iOS 14（2020年9月16日）上线后的最早可用数据 |
| 用户权限 | AF账户下的用户必须具备<Anchor target="_blank" href="/marketers/zh/docs/user-management">必要的权限</Anchor> |
| App Clip（苹果小程序） | App Clip在SKAN面板上归为自然量，但您可以在数据总览面板中的自定义媒体渠道下看到App Clip的投放效果。 |

</Accordion>

## SKAN对接渠道

<div id="recording-ad-revenue" />

<Accordion title="记录广告收入">

在SKAN衡量窗口期内产生的收入会归因到获取用户的广告。目前只有通过SDK对接常规展示层级广告收入数据的广告主才能使用收入归因功能。

请按以下步骤在SKAN面板中记录广告收入：

* 在应用中接入<Anchor target="_blank" href="/marketers/zh/docs/integrate-the-roi360-ad-revenue-sdk-api">常规展示层级广告收入SDK</Anchor>。
* 如果您在SKAN转化值操作台中使用固定模式（旧版），请打开<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio#report-events-by-servertoserver-api">SKAdNetwork服务器到服务器支持</Anchor>开关。

**请注意**：另请参阅<Anchor target="_blank" href="/marketers/zh/docs/integrate-the-roi360-ad-revenue-sdk-api">常规SDK connector</Anchor>的说明文档，了解可支持此功能的聚合平台。

</Accordion>

<div id="sending-postbacks-to-integrated-partners" />

<Accordion title="将回传数据发送给对接渠道">

AppsFlyer会把SKAN归因相关的回传数据发送给对接渠道（若使用SKAN 4，则仅发送窗口1的回传）。

下表列出了各种数据共享方式及要求：

| 主题 | 说明 |
| --- | --- |
| <span id="transaction-id-sharing"></span>交易ID共享 | **必要的前期工作**：与渠道确认他们是否需要<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/verifying_an_install_validation_postback">transaction ID</Anchor>（交易ID）并做好相应的配置。<br /><br />AppsFlyer把回传数据发送给带来转化的广告平台。这里的回传数据是解码后的回传数据，而不是由iOS发送的SKAN回传数据。这些回传数据中包含了解析后的CV数据，记录用户在用户行为窗口期内完成的激活及后续应用内事件。<br /><br />由于transaction ID（交易ID）可以用于解析CV，因此在没有得到广告主授权的情况下，AF不会将其共享给他方。<br /><br />**交易ID共享**<br /><br />广告主按以下步骤<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#b-advanced-privacy">启用transaction ID共享</Anchor>：从AF后台进入**协作** > **活跃对接** > 选择渠道 > **渠道对接选项卡** > **数据共享**。 |
| <span id="inapp-event-mapping-verification"></span>应用内事件映射验证 | **<span id="1611499069.009700"></span>必要的前期工作**：请务必确保SKAN衡量中设置的<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#映射方式">应用内事件</Anchor>在渠道侧有准确的映射，这样渠道才能以正确的方式记录回传数据。<br /><br />投放SKAN广告的渠道需要确保按照正确的衡量模式设置应用内事件。<br /><br />**请按以下步骤确认或更改渠道的事件映射**：<ol><li>从AppsFlyer后台进入**协作** > **活跃对接**。</li><li>选择您要查看的渠道，</li><li>进入**对接**选项卡。</li><li>确认设置是否符合以下描述，若不符合，请更改设置：<ol><li>打开**应用内事件回传**开关。</li><li>在SKAN衡量中设置的应用内事件、**SDK事件名称**与**渠道的事件标识符**准确对应。</li></ol></li><li>点击**保存对接**。</li></ol> |

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/about-att-and-skan">iOS 14、ATT和SKAN的快速入门指南及常见问题答疑</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">SKAN转化值操作台设置指南（SKAdNetwork设置）</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">AppsFlyer的SKAN面板</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/skan-integrated-partners-list">SKAN对接渠道列表</Anchor>
> * 如需与SKAN渠道互通，请在AppsFlyer后台完成相关配置：
>   * <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-interoperation-with-meta-ads">Meta ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/zh/docs/get-skan-postback-data-from-google-ads">Google Ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/zh/docs/skan-interoperation-with-tiktok-for-business">TikTok for Business</Anchor>
>   * <Anchor target="_blank" href="/marketers/zh/docs/skan-interoperation-with-snapchat">Snapchat</Anchor>

<div data-zendesk-anchors="01H7Z06Z03AQY25A3E45Z47A9G=skan 01H7Z06Z03CSKH1ZB9RQP6SHA8=%E6%8F%90%E7%A4%BA 01H7Z06Z03MRE6BCSG1AEXN947=about-apple-skan appsflyer-skan-solution=appsflyer%E7%9A%84skan%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88 01H7Z06Z04G479NAKBEA33SGSZ=appsflyer%E7%9A%84skan%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88 01H7Z06Z05CAVK3CR7F5FBKFC5=principles-and-flow skan-attribution-flow=skan%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B 01H7Z06Z05EGK5QBDK6G7BJQJK=skan%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B 01H7Z06Z053M2H3CJ6SV4VDZPZ=conversion-studio additional-skadnetwork-information=%E5%85%B3%E4%BA%8Eskan%E7%9A%84%E5%85%B6%E4%BB%96%E4%BF%A1%E6%81%AF 01H7Z06Z05556NQ35HMR4E2TRY=%E5%85%B3%E4%BA%8Eskan%E7%9A%84%E5%85%B6%E4%BB%96%E4%BF%A1%E6%81%AF 01H7Z06Z05G0YB56GDG5E196QM=reporting-options 01H7Z06Z05M3BPSBTCMJ3NHK5D=skadnetwork-solution-implementation-checklist 01H7Z06Z05YF4J0MPMJ40EG7BX=troubleshooting-guide 01H7Z06Z0502NW8KFJ7XRZFWJR=timing-from-app-install-until-dashboard-and-reports-update 01H7Z06Z068462E4QTGTSMNS7H=organic-metrics-in-the-context-of-skadnetwork 01H7Z06Z0615QHCY6JZ4MAMTJ8=traits-and-limitations skadnetwork-integrated-partners=skan%E5%AF%B9%E6%8E%A5%E6%B8%A0%E9%81%93 01H7Z06Z06KGT6ESN42XTJSK2F=skan%E5%AF%B9%E6%8E%A5%E6%B8%A0%E9%81%93 01H7Z06Z06NWJQ6W50MCD3P352=recording-ad-revenue 01H7Z06Z06K2ZB949GGTJV6MJP=sending-postbacks-to-integrated-partners h_01HE7TC49KRRX1RVGX1FY7C52T=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

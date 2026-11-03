---
title: ROI360 指南 - 广告收入归因
metadata:
  keywords:
    - ad revenue
    - ad monetization
    - monetization
    - Advertisers
    - adrevenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2016-12-12T10:53:27Z'
  edited_at: '2026-10-14T10:01:52Z'
  id: 217490046
  locale: zh-cn
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/zh-cn/articles/217490046
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 对广告收入进行归因，全面了解LTV维度的变现效果。

[![Attributes_ad_revenue.png](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)

## 广告收入归因

* 广告主可以在相关应用中通过横幅、积分墙、插屏等形式展示广告，从而产生广告收入。
* 将广告收入与应用内购和订阅收入相结合，就可以全方位了解用户的LTV价值。将用户的LTV数据与渠道买量成本进行匹配，便可判断广告投放的ROI，并将其用于投放渠道的进一步分析。

**非自然广告收入数据：**

* 来自聚合平台和/或变现渠道，通过服务器API或内嵌SDK（支持iOS 14）上报给AF。
* 变现收入会归因给将用户带来的买量渠道。例如:
  * 用户在广告平台A上看到一则广告，然后下载了您的应用。
  * 您的应用向用户展示广告。
  * 不论这些广告是由哪个渠道发布的，所产生的广告收入都会归因到A平台（即最初带来用户的平台）。
* 上报数据的颗粒度取决于变现渠道的对接类型以及广告收入的归因类型。

<div id="integration-types-for-ad-revenue-attribution" />

<Accordion title="广告收入归因的对接类型">

数据的准确性和时效性取决于广告收入归因的对接类型，详见下表说明。

**请注意**：以SDK为基础的对接需要开发人员协助部署；以S2S为基础的对接需要您具备正确的认证证书信息。

| 广告收入归因的对接类型 | 说明 |
| --- | --- |
| [汇总数据](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events)（通过S2S API上报） | <ul><li>AppsFlyer按照国家/地区获取每日的变现数据。</li><li>eRPA（单个事件的有效收入）的计算方式为：收入/实际触发事件数。</li><li>触发事件可以是应用打开或指定的应用内事件。</li><li>如果您使用的是聚合平台，请务必先停用通过该平台聚合的变现渠道的广告收入对接，然后再启用该聚合平台的广告收入对接，否则会产生重复数据。</li><li>原始数据报告中没有提供数据，无法通过回传或 UA 信号与广告网络共享。</li></ul> |
| 通过S2S API上报[设备级别](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data)数据 | <ul><li>聚合平台或变现渠道一般会上报设备级别的分用户收入，但不是所有的平台/渠道都支持设备级别的数据颗粒度。</li><li>这部分收入会归因给带来相关用户的媒体渠道。也就是说，AppsFlyer对变现收入归因时，会遵守广告平台的归因原则，包括再营销的归因原则。</li><li>如果您使用的是聚合平台，请务必先停用通过该平台聚合的变现渠道的广告收入对接，然后再启用该聚合平台的广告收入对接，否则会产生重复数据。</li><li>通过S2S API上报的设备级别数据包含完整的广告收入，是数据精度最高的一种广告收入对接。</li><li>数据以原始数据报告的形式提供，可通过<Anchor target="_blank" href="/marketers/zh/docs/share-ad-revenue-data-with-partners">与广告网络共享</Anchor> <Anchor target="_blank" href="/marketers/zh/docs/share-ad-revenue-data-with-partners">仅 UA 信号。</Anchor></li><li>安卓应用商店包括：请确保开发人员已启用 AppSet\_id 的收集，因为一些媒介可能仅提供此标识符。请参阅开发人员说明 [收集 AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).</li></ul> |
| 通过SDK上报的展示级别数据 | <ul><li>“展示级别”指的是AppsFlyer接收数据的方式。展示级别的数据最终可能会以其他的颗粒度上报（如设备级别）。</li><li>聚合平台或变现渠道一般会上报展示级别的分用户收入，但不是所有的平台/渠道都支持展示级别的数据颗粒度。</li><li>这部分收入会归因给带来相关用户的媒体渠道。也就是说，AppsFlyer对变现收入归因时，会遵守广告平台的归因原则，包括再营销的归因原则。</li><li>如果您使用的是聚合平台，请务必先停用通过该平台聚合的变现渠道的广告收入对接，然后再启用该聚合平台的广告收入对接，否则会产生重复数据。</li><li>通过SDK上报的展示级别数据是时效性最强的一种广告收入对接。</li><li>支持SKAN归因。</li><li>通过 SDK 实现印象级别是必须使用的集成类型，当您使用未包含在 AppsFlyer 集成合作伙伴列表中的媒介平台时。在广告收入 SDK 中，对于 mediation\_network，开发人员需要选择 customMediation。</li><li>可以通过以下方式与广告网络共享数据： <Anchor target="_blank" href="/marketers/zh/docs/share-ad-revenue-data-with-partners">仅限回传</Anchor>.</li></ul> |
| 由SDK上报的展示级别数据与由S2S API上报的设备级别数据相结合 | <ul><li>可对第X天由SDK上报的展示级别数据进行归因并展示在报告中，然后切换到第X+1天由API上报的设备级别数据。**请注意**：对于安卓应用，未知设备（即无可用设备ID）的SDK上报数据不会被API上报数据覆盖。</li><li>使用此类对接可以获得兼具时效性和准确性的数据（简称F2A）。也就是说，您可以在第X天获得当天数据，并在第X+1天及之后获得准确数据。</li><li>支持SKAN归因。</li><li>可以通过以下两种方式与广告网络共享数据 <Anchor target="_blank" href="/marketers/zh/docs/share-ad-revenue-data-with-partners">回传和用户代理信号</Anchor>.</li><li>安卓应用商店包括：请确保开发人员已启用 AppSet\_id 的收集，因为一些媒介可能仅提供此标识符。请参阅开发人员说明 [收集 AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).</li></ul> |

</Accordion>

## 启用方式

以下章节介绍了各种类型的广告收入归因，以及您在启用这维护这些功能时需要完成的流程和步骤。

<div id="connect-to-ad-revenue-integrated-partners" />

<Accordion title="广告收入平台的对接方式">

**前期准备**：

* 让广告收入对接渠道将API证书发送给您。

**请按以下方式与变现渠道对接广告收入**：

1. 从AppsFlyer后台的侧边栏中选择**配置** > **收入设置** > **广告收入。**
2. 在广告收入配置页面中，点击**新建广告收入对接**。
3. 选择要添加的广告收入合作渠道，然后点击**下一步**。  
   [![ad revenue 3.6(2).png](https://files.readme.io/8ccba7d0909c15e92507bc55c7bf2bf003e1a9431fb6bd1d32a0f41959f7a904-47792643579153.png)](https://files.readme.io/8ccba7d0909c15e92507bc55c7bf2bf003e1a9431fb6bd1d32a0f41959f7a904-47792643579153.png)
4. 选择您想要接收的广告收入数据类型。**请注意**：并非所有广告平台都能提供下列所有数据类型。
   * 归因收入（Attributed Revenue）是指可归因到获客渠道的收入数据。归因记录报告分为以下两种：
     * [汇总数据](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events)（通过S2S API上报）
       * 选择相关事件（该事件与广告收入的计算相关联）。假设您选择的事件是af\_app\_opened，那么广告收入就是平均每次应用打开所产生的广告收入，即总体广告收入除以应用打开事件总数。
     * 通过S2S API上报设备级别数据。
       * 安卓应用商店包括：确保开发人员启用以下标识符的收集： `app_set_id`, ，因为有些调解可能只提供此标识符。请参阅开发人员说明 [收集 AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).
       * **请注意**：如果您需要启用某聚合平台的设备级别广告收入API，就必须关闭该平台所聚合的变现渠道的广告收入对接，否则会产生重复数据。
     * 通过SDK上报的展示级别数据。
       * 让您的开发人员在相关应用中接入AppsFlyer的广告收入SDK API。
     * **建议：** 由SDK上报的展示级别数据与由S2S API上报的设备级别数据相结合。
       * 让您的开发人员在相关应用中接入AppsFlyer的广告收入SDK API。
     * 安卓应用商店包括：确保开发人员启用以下标识符的收集： `app_set_id`, ，因为有些调解可能只提供此标识符。请参阅开发人员说明 [收集 AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).
     * **请注意**： 如果您使用的是聚合平台，请务必先停用通过该平台聚合的变现渠道的广告收入对接，然后再启用该聚合平台的广告收入对接，否则会产生重复数据。
5. 按对接渠道的要求填写API证书或登录信息。此处填写的信息与SDK对接无关。
6. 点击**保存**。
7. 如果界面显示“测试连接”按钮（如上图所示），请点击**测试连接**。
   * 如果界面显示消息“API key verified”（API密钥已验证），则表示您已顺利完成该流程。
   * 若界面显示其它信息，请参照[广告收入API的连接状态与测试](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-api-status-and-testing)排查问题，然后重复上述流程。
8. 如果界面未显示“测试连接”的按钮，说明您已经完成对接流程。   
   AppsFlyer以一天多次的频率从渠道侧收集数据。 有关详细信息，请参阅 [数据新鲜度](/docs/roi360-guide-ad-revenue-attribution#data-freshness).
9. 【可选】核查您在AppsFlyer中看到的广告收入数据，并将其与聚合平台和UA渠道面板中的广告收入进行对比。<Anchor target="_blank" href="/marketers/zh/docs/compare-roi360-ad-revenue-data-with-partner-data">详情请见此处说明。</Anchor>
10. 【可选】通过<Anchor target="_blank" href="/marketers/zh/docs/share-ad-revenue-data-with-partners">UA signals和广告收入事件回传</Anchor>将广告收入数据分享给您的UA合作渠道。

**请注意**：如果您更改了对接方式，新的对接配置将在第二天UTC时间的凌晨12点生效。

</Accordion>

<div id="view-edit-and-delete-ad-revenue-integrated-partners" />

<Accordion title="查看、修改或删除广告收入对接渠道">

![delete_edit_adi.png](https://files.readme.io/2d2153ec3248061dab4072e1d981e237f553e32824a68e392ae239778b307610-47792653636113.png)

**如需查看、修改或删除您与广告收入平台的对接，请按以下方式操作**：

1. 从AppsFlyer后台左侧的菜单栏中选择**配置** > **收入设置** > **广告收入**，然后选择相关应用。  
   界面会列出您所有的渠道对接，包括对应的产品和对接类型、对接状态以及广告收入事件名称。
2. 将鼠标悬停在相关对接上，然后根据实际需要点击**编辑**或**删除**。

</Accordion>

<div id="deduplicate-cross-referenced" />

<Accordion title="广告收入去重">

如果您的应用通过API（无论是汇总级别还是设备级别）同时对接了两个<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary#mediation-platform">聚合平台</Anchor>，且这两个平台都关联了同一个<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary#monetization-network">变现渠道</Anchor>，这时可能会有一部分广告收入出现重复。这种情况下，每个聚合平台都会上报其关联变现渠道带来的所有广告收入，无论这些广告收入是否确实通过自身平台的聚合产生。

**如需在两个聚合平台同时上报相互对应的广告收入时尽量避免出现数据重复，请按以下方式操作**：

1. 使用展示级别的SDK对接（若可用）。
   * 如果两个聚合平台都使用展示级别的SDK对接，就不会产生重复数据。
   * 如果您有多个对接，而其中有一个是SDK对接，建议您将其他对接也切换成SDK对接。
2. 如果您使用基于API的对接，请按以下方式对广告收入去重： 
   1. 从AppsFlyer后台的侧边栏中选择**配置** > **收入设置** > **广告收入**。
   2. 勾选**通用设置**下的**两个聚合平台上报对应广告收入时去重**。**请注意**：若出现以下情况，请勿勾选此选项：
      * 两个聚合平台使用不同的广告样式进行聚合。比如平台1展示横幅和插屏广告，而平台2展示开屏和原生广告，这时就无需进行去重。
      * 两个聚合平台都使用展示级别的SDK对接。

[![dedup.png](https://files.readme.io/a739bc7e3557913bf6a67afa74a71dd72673d5b4e4d6bbe1d3ef872e46609422-47792653637265.png)](https://files.readme.io/a739bc7e3557913bf6a67afa74a71dd72673d5b4e4d6bbe1d3ef872e46609422-47792653637265.png)

</Accordion>

<div id="aggregate-granularity-using-app-open-or-inapp-events" />

<Accordion title="按应用打开或应用内事件汇总数据">

汇总级别广告收入数据的作用原理如下：

* 对接平台上报分地区的每日总收入。
* AppsFlyer的eRPA（实际用户行为平均收入）计算方式为：广告收入/某个事件的触发次数
* AppsFlyer创建a \_monetized事件，其中包含每个已归因设备的总体eRPA，如ad\_matched\_monetized。
* 通过eRPA将收入归因到媒体渠道。
* 您可以使用以下任一事件类型：
  * **特有变现事件**要求对应用进行相应修改。
  * **af\_app\_opened**事件默认可用。
* 请勿在使用广告收入对接的同时通过应用内事件上报广告收入金额，否则会导致面板中出现重复的广告收入数据。这是因为AppsFlyer会通过对接获取变现渠道的收入数据。

#### 按事件汇总广告收入

| 事件类型 | 触发方式 | 注意事项 |
| --- | --- | --- |
| 特有变现事件 | <ul><li>在展示广告时触发应用内事件</li><li>这样就可以记录到准确的用户行为次数，从而得出更准确的eRPA</li><li>您还可以为每个变现渠道分别配置应用内事件，这样就能按平台细分收入，从而进一步打磨数据<br />各种方式的对比请见下文表格。</li></ul> | <ul><li>需要开发人员修改应用</li><li>可以在面板中按变现渠道细分收入</li></ul> |
| af\_app\_opened event | <ul><li>默认情况下，af\_app\_opened事件由AppsFlyer SDK发送</li><li>每次用户打开应用时触发该事件</li></ul> | <ul><li>无需修改应用</li><li>启用快捷</li><li>每个session只能对应到一个应用，否则eRPA值会严重失真</li><li>无法按变现渠道细分收入</li><li>该事件仅说明用户打开了应用，但不表示用户愿意观看广告</li></ul> |

#### 应用内事件配置方式对比

| 方法 | 优点 | 缺点 | 注意事项 |
| --- | --- | --- | --- |
| 在所有变现渠道中都使用相同的事件，如“ad\_watched”，从而自动生成包含变现信息的“ ad\_watched\_monetized”事件 | 配置最便捷 | 无法产生有价值的信息，如分变现渠道的点击次数及广告收入数据 | <ul><li>有助于判断最能拉动用户点击的渠道/广告系列</li><li>不适用于变现渠道的效果对比</li></ul> |
| **推荐做法：** 为每个平台单独配置专用的广告观看事件，如**ad\_watch\_admob**。<br /><br /> ad\_watch\_vungle. | 除了获取原始数据之外，还能在面板上看到所有变现渠道的数据并进行对比。 | 无法累计单个事件的总体广告收入数据。事件数量等于变现渠道的数量。 | 可在面板中对比各个变现渠道的效果。由于此方案中针对每个变现渠道分别配置了应用内事件，因此广告收入可按变现渠道细分。 |

</Accordion>

<div id="ad-revenue-api-status-and-testing" />

<Accordion title="广告收入API的连接状态与测试">

* 广告收入对接正常时的状态信息如下：
  * <Anchor target="_blank" href="/marketers/zh/docs/dashboard-cost-and-ad-revenue-status">成本和广告收入对接状态面板</Anchor>：集中查看账户下已对接相关应用（一个或多个）广告收入的渠道列表。
  * 一些合作伙伴允许测试广告变现API的连接状态。这种情况下界面会显示**测试连接**按钮。<Image alt="mceclip0.png" src="https://support.appsflyer.com/hc/article_attachments/51911279045009" width="104px" />
  * 验证API连接是否正常：
  * 点击**测试连接**。  
    此时界面会显示消息“**API key verified**”（API key已验证）。若未出现此消息，请按下表中的说明进行排查和纠错。

| 界面消息 | 含义 | 说明/所需操作 |
| --- | --- | --- |
| API key verified（API key已验证） | <ul><li>连接处于活跃状态，可以拉取数据。</li></ul>AppsFlyer 每天多次收集数据。有关详细信息，请参阅 [数据新颖性](/docs/roi360-guide-ad-revenue-attribution#data-freshness). | 无 |
| Invalid credentials（证书无效） | 一个或多个证书错误。 | 请从变现渠道获取正确的证书信息。 |
| Missing configuration details（配置信息缺失） | 一个或多个证书字段不完整。 | 从广告收入平台的面板中获取证书信息，或联系该渠道要求其提供证书信息。 |

</Accordion>

## 广告收入数据

您可以通过AppsFlyer面板和原始数据报告查看广告收入数据。

<div id="ad-revenue-aggregate-data" />

<Accordion title="汇总层级的广告收入数据">

广告收入展示了某段时间内不同渠道所获用户的质量。随着用户打开应用并与广告互动的行为逐渐累积，用户的LTV就会持续提升。

**请注意**：各面板和报告的广告收入数据之间可能会有差异，如需了解详情，请参考[此文档](#is-there-discrepency)。

您可通过下列方式查看广告收入：

* LTV维度：
  * 可在数据总览和事件面板中查看
  * LTV报告
  * 群组面板和报告
  * Master API
* 活跃维度：
  * 可在活跃数据面板中查看
  * 广告收入原始数据

#### **数据总览面板——汇总效果报告**

[![](https://files.readme.io/f3ea2c79ed42c59d26f6f82d7f68e20b319a005e6a3131239b99f13db59b3cff-47792643589393.png)](https://files.readme.io/f3ea2c79ed42c59d26f6f82d7f68e20b319a005e6a3131239b99f13db59b3cff-47792643589393.png)

数据总览面板：

* 面板中的收入等各种数据是LTV维度的。详情请见<Anchor target="_blank" href="/marketers/zh/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV数据与活跃数据的差异</Anchor>。
* **收入**一栏显示所有收入，包括广告收入和应用内购。
* 深入各广告层级（媒体渠道、广告系列、广告组、地理位置）对数据进行切分，查看报告中的**变现**事件。

**事件报告面板**[![](https://files.readme.io/c7c8fddb68f705a7be694afdde6faf387cf34b79abfbc68c39e53823549a385d-47792643591057.png)](https://files.readme.io/c7c8fddb68f705a7be694afdde6faf387cf34b79abfbc68c39e53823549a385d-47792643591057.png)

活跃面板：

* 面板中的收入等各种数据是活跃维度的（即按用户行为发生日期计算），详情请见<Anchor target="_blank" href="/marketers/zh/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV数据与活跃数据的差异</Anchor>。
* **用户平均操作次数**用于说明用户在应用中完成广告交互的可能性。

> 📄 **示例**
>
> 三名用户于2017年12月31日安装了一个应用。他们的归因信息如下：
>
> * 用户A：广告平台A
> * 用户B：广告平台B
> * 用户C：自然量
>
> 这个应用对接了五个不同的变现平台。广告主通过AppsFlyer的SDK为每个平台分别配置了单独的应用内事件，具体如下：
>
> * Meta Audience Network：fb\_ad\_view
> * Chartboost：chartboost\_ad\_view
> * Admob：admob\_ad\_view
> * Applovin：applovin\_ad\_view
> * IronSource：is\_ad\_view
>
> 在用户激活应用的四天后向用户展示广告，具体如下：
>
>
>
> | 用户 | UA平台 | fb\_  <br />ad\_view | chartboost\_  <br />ad\_view | admob\_  <br />ad\_view | applovin\_  <br />ad\_view | is\_ad\_view | Total（总计） |
> | --- | --- | --- | --- | --- | --- | --- | --- |
> | A | 广告平台A<br /><br />2017-12-31 | 2018-01-01<br /><br />$1 | 2018-01-02<br /><br />$1 | 2018-01-03<br /><br />$1 | 2018-01-04<br /><br />$1 |  | $4 |
> | B | 广告平台B<br /><br />2017-12-31 | 2018-01-02<br /><br />$1 |  | 2018-01-04<br /><br />$1 |  |  | $2 |
> | C | 自然量<br /><br />2017-12-31 | 2018-01-01<br /><br />$1 |  |  |  | 2018-01-02<br /><br />$1 | $2 |
>
>
>
> 我们可以从这些数据中总结出每个用户每天（通过每个应用内事件）所带来的广告收入：
>
>
>
> | 用户 | 2018-01-01 | 2018-01-02 | 2018-01-03 | 2018-01-04 | 总LTV |
> | --- | --- | --- | --- | --- | --- |
> | A | $1 | $1 | $1 | $1 | $4 |
> | B |  | $1 |  | $1 | $2 |
> | C | $1 | $1 |  |  | $2 |
> | Total（总计） | $2 | $3 | $1 | $2 | $8 |
>
>
>
> **报告解读：**
>
> 如前所述，广告收入是LTV维度的数据，即在面板中选定时间段内激活应用的用户从激活之日起到当前为止的累计收入。以下示例展示了选定时间段内面板呈现的数据：
>
> 汇总报告：选定日期：2017-12-31-2018-01-05
>
>
>
> | 广告平台 | LTV收入 |
> | --- | --- |
> | 自然量 | $2 |
> | 广告平台A | $4 |
> | 广告平台B | $2 |
> | 广告平台C | $2 |
>
>
>
> 这时面板中显示的用户是在2017-12-31到2018-01-05期间激活应用的用户。这些用户产生的所有收入都归因给最初激活的带量渠道，显示在用户LTV下。

</Accordion>

<div id="ad-revenue-raw-data" />

<Accordion title="广告收入原始数据">

<Image alt="PremiumFeature.jpg" src="https://files.readme.io/674e5d0c9efde9d12008bd705b3ba95f04e133fec3f39d4278612675123d4de4-360007173877.jpg" width="78px" />

广告收入原始数据报告中的数据来自与AppsFlyer对接的变现平台，对接类型可以是设备级别，也可以是展示级别。

**广告收入原始数据的作用原理**

* 广告收入数据是基于每个用户的独立展示数来汇总的。独立展示数是根据广告变现平台、广告单元和广告位综合计算得出的。
* 展示级别的原始数据：
  * 汇总到设备级别，呈现在设备级别的报告中。
  * 呈现在Data Locker的展示级别报告中。

<table><thead><tr><th>报告</th><th>导出<br/>数据页面</th><th>Pull API </th><th>Data Locker</th></tr></thead><tbody><tr><td>归因广告收入（非自然）</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>自然广告收入</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>再营销变现收入 </td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>展示级别原始数据</td><td><span>-</span></td><td><span>-</span></td><td><span>✓ </span></td></tr><tr><td colspan="4"><p>\* 还提供版本报告，每天更新多次。非版本化的Data Locker报告每天更新一次。有关详细信息，请参阅 <a href="./roi360-guide-ad-revenue-attribution#data-freshness">数据新颖性</a>.</p><p>\*\* 此处指名称中带有“impression-level”（展示级别）字样的报告，而非展示级别的广告收入对接。</p></td></tr></tbody></table>

**数据特征和字段**

广告收入报告中的填充字段：

* 按广告收入事件填充，详见下文表格。这些字段分为两类：
  * **专用字段：** 专用于广告收入的字段，如展示数和广告位。**请注意**：具体的字段填充取决于变现渠道，详情请见下文表格，其中列出了分变现渠道的填充字段。
  * **通用字段：** 与其他原始数据报告相似的字段，如事件名称、事件值、货币等。
* AppsFlyer将广告收入事件归因到相关用户的拉新渠道，并以此为基础来填充相应字段。也就是说，这些字段按最初的拉新转化事件信息来填充，如媒体渠道和广告系列。这些字段不包含在下表所列范围内。

#### 广告收入填充字段

| api\_name | 字段名称 | 字段类型 | 说明 |
| --- | --- | --- | --- |
| <span id="event_time"></span>event\_time | Event time | 通用 | 变现收入归因到的日期 |
| <span id="event_name"></span>event\_name | Event name | 通用 | 设置为af\_ad\_revenue |
| <span id="event_revenue"></span>event\_revenue | Event Revenue Currency | 通用 | <ul><li>基于event\_revenue\_currency（收入货币）的收入金额。</li><li>零值表示广告展示没有带来收入</li></ul> |
| <span id="event_revenue_currency"></span>event\_revenue\_currency | Event Currency | 通用 | 事件收入货币 |
| <span id="event_revenue_xxx"></span>event\_revenue\_XXX | Event Revenue XXX | 通用 | <ul><li>导出数据页按应用配置中的指定货币换算收入数据。</li><li>在Data Locker中始终为USD</li><li>Pull API报告按您在Pull API中配置的货币来展示收入。</li></ul> |
| <span id="country"></span>country | Country | 通用 | 发生激活转化的国家/地区 |
| <span id="ad_unit"></span>ad\_unit | Ad unit | 专用 | 此字段的值特定于广告网络。对于服务器对服务器 (S2S) 集成：<ul><li>最大值使用广告单元 ID（例如，f53328a3c）。</li><li>ironSource使用广告单元类型，如横幅、奖励视频或插页式。</li></ul>对于其他网络，请参阅相关合作伙伴集成指南，或联系您的网络代表以确认所需格式。 |
| <span id="segment"></span>segment | Segment | 专用 | 广告展示位置的名称 |
| <span id="monetization_network"></span>monetization\_network | Monetization Network | 专用 | 发送广告的平台 |
| <span id="impressions"></span>impressions | Impressions | 专用 | 用户看到广告的次数 |
| <span id="mediation_network"></span>mediation\_network | Mediation Network | 专用 | 将事件上报给AppsFlyer的变现平台 |
| <span id="customer_user_id"></span>customer\_user\_id | 客户用户ID | 通用 | 如果广告商提供，则填充：<ul><li>展示层级的SDK对接：通过以下方式收集： `setCustomerUserId()` 在 AppsFlyer SDK 中。</li><li>对于设备级（API）集成：从中介 API 收集（通过中介 SDK 设置的用户 ID 或发布商用户 ID）。</li><li>不支持 Odeeo 和 Appodeal。</li></ul> |

#### 分变现渠道的字段填充情况

<table><thead><tr><th>字段名称</th><th>Admob</th><th>ironSource（LevelPlay）</th><th>AppLovin MAX</th><th>Appodeal</th><th>Fyber</th></tr></thead><tbody><tr><td>Ad unit</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Segment</td><td>-</td><td>(1)</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Placement</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Monetization Network</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Impressions</td><td><span>-</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td>Mediation Network</td><td><span>-</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">（1）广告主需要在ironSource中进行配置</td></tr></tbody></table>

[广告收入原始数据报告范例](https://docs.google.com/spreadsheets/d/e/2PACX-1vRm_1tevWFdzdj6JgdxYawLBtYAJj-ubDeY4g1QfbdSkd2-Adi18oemPMdd7m7cM2e3fzm7VH0w6lhD/pub?output=xlsx)

</Accordion>

<div id="data-freshness" />

<Accordion title="数据时效性">

数据时效性取决于对接类型以及数据上报方式。

**在S2S API对接中，数据的最早呈现时间为：**

* 面板和Data Locker中的报告会从UTC时间第X+1天的上午8点开始呈现数据，每天约更新4次，每6小时更新一次。第 2、3、7 和 14 天，每天一次。

**在展示级别的SDK对接中，数据的最早呈现时间为：**

* 仪表板（活动和群体指标）：连续（事件发生后 15–60 分钟）
* 理想状态下，面板和Data Locker中的报告会从UTC时间第X天的早晨5点开始呈现数据，每天约更新6次，每4小时更新一次。
* 展示级别的原始数据报告（通过Data Locker拉取）在UTC时间第X天的凌晨1点呈现数据，且每小时更新一次。

对于带有设备级别数据（通过S2S API上报）的展示级别数据（通过SDK上报），您可以在第X天获得当天数据，并在第X+1天获得准确数据，具体如下：

* 对于通过SDK上报的展示级别数据：

  * 仪表板（活动和群体指标）：连续（事件发生后 15–60 分钟）
  * 理想状态下，面板和Data Locker中的报告会从UTC时间第X天的早晨5点开始呈现数据，每天约更新6次，每4小时更新一次。
  * 展示级别的原始数据报告（通过Data Locker拉取）在UTC时间第X天的凌晨1点呈现数据，且每小时更新一次。
* 对于通过S2S API上报的设备级别数据：

  * 面板和Data Locker中的报告会从UTC时间第X+1天的上午8点开始呈现数据，每天约更新4次，每6小时更新一次。第 2、3、7 和 14 天，每天一次。

对于**原始数据导出和拉取 API**，无论集成类型或 ROI360 套餐（高级版或标准版）如何，特定日期的数据均将于次日（第 X+1 天）UTC 时间下午 6 点提供。此后，这些工具的数据将不再更新。

**请注意：** 仪表板中的日内数据可用性需要 ROI360 高级订阅。

<div id="ad-revenue-data-locker-reports" />

<Accordion title="Data Locker的广告收入报告">

| 名称 | 数据时效性 | 报告结构 |
| --- | --- | --- |
| ***每日广告收入（从设备层级进行汇总）*** | 第X天的广告收入会在次日（即第X+1天）的UTC时间晚上8点进行上报。<br /><br />比如5月1日的广告收入会在5月2日上报。 | 该报告包含Attributed（非自然广告收入）、Organic（自然广告收入）、和Retargeting AdRevenue（再营销广告收入）几个部分。 |
| ***版本化的每日广告收入报告（从设备层级进行汇总）*** | 每日报告中包含以下内容：<ul><li>一天多次的收入报告在收入产生当天（即第X天）每4小时生成一次。当日数据通过SDK API收集。</li><li>全天版本的报告以S2S API报告中的数据为基础，在第2、3、7和13天生成。</li></ul>也就是说，一天中可能生成的各种报告版本如下：<ul><li>第X天的00:00 — 04:00。</li><li>第X天的00:00 — 08:00 【SDK API】</li><li>第X天的00:00 — 12:00 【SDK API】</li><li>第X天的00:00 — 24:00 【SDK API】</li><li>第X+1天的00:00 — 24:00【S2S】</li><li>第X+2天的00:00 — 24:00【S2S】</li><li>第X+1天的00:00 — 24:00【S2S】</li><li>第X+1天的00:00 — 24:00【S2S】</li><li>第X+13天的00:00 — 24:00【S2S】</li></ul> | 报告的各个版本都包含Attributed（非自然广告收入）、Organic（自然广告收入）、和Retargeting AdRevenue（再营销广告收入）几个部分。 |
| ***展示级别的广告收入报告*** | 展示级别的广告收入记录每小时写入单独的文件中。 |  |

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/revenue-etl-reports">收入 ETL 报告</Anchor>

</Accordion>

</Accordion>

## 其他相关信息

<div id="migrating-from-aggregate-to-userlevel-granularity" />

<Accordion title="将数据颗粒度从汇总层级切换到设备级别">

* 切换颗粒度不会影响历史广告收入数据，也就是说历史数据保持不变。
* 广告收入数据每天会多次提取，从协调世界时（UTC）03:00开始，并采用当时选定的粒度选项。
* 与汇总层级不同，设备级别的数据上报不需要定义应用内事件。您可以继续发送这些事件，但它们不会出现在AppsFlyer的设备级别数据中。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点和局限性">

| 特点 | 备注说明 |
| --- | --- |
| 局限性 | 广告收入事件目前不适用于：<ul><li>Push API</li><li>重定向控制面板</li></ul>设备级别数据颗粒度的局限性：<ul><li>Master API和数据透视表的群组报告不支持af\_ad\_revenue事件。</li><li>可在群组报告中查看该事件。</li><li><Anchor target="_blank" href="/marketers/zh/docs/applovin-max-ad-revenue-configuration#best-practice">如果广告主使用了Meta ads的**应用内**竞价（in-app bid）收入，可能会产生数据差异。</Anchor></li></ul>AppsFlyer面板不支持通过独立用户数来触发af\_ad\_revenue事件。 |
| 支持的设备 ID | 以下设备 ID 支持广告收入归因：<ul><li>AppsFlyer ID</li><li>IDFA</li><li>IDFV</li><li>GAID</li><li>AppSet ID*</li><li>Android ID</li><li>IMEI</li></ul><ul><li>仅支持 Applovin MAX 和 IronSource LevelPlay 中介的 AppSet ID。请参阅开发人员说明 [收集 AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).</li></ul> |
| 广告平台访问权限 | 无法访问群组报告 |
| 代理访问权限 | 代理：<ul><li>无法访问广告收入配置</li><li>可以看到与其相关的所有面板和数据</li></ul> |
| 代理数据透明化 | 不支持 |
| 时区 | AppsFlyer面板和报告仅按UTC时间呈现广告收入数据。也就是说，如果数据在UTC+2时区的下午2点上报，该时间在AppsFlyer中会呈现为UTC时间下午2点。<br /><br />这是因为AppsFlyer需要对来自多个渠道和平台的数据进行归一，而大部分渠道和平台都是按UTC时间来上报数据的。 |
| 货币 | 在AppsFlyer后台：<ul><li>面板展示广告主在应用配置中指定的货币。</li><li>原始数据报告展示原始货币，并将其换算成应用配置中的指定货币。</li></ul> |
| 数据类型 | 同时支持自然量和非自然量数据 |
| 数据时效性 | [广告收入](/docs/roi360-guide-ad-revenue-attribution#data-freshness) |
| 历史/回溯数据 | <ul><li>自对接完成当日起拉取并呈现数据。也就是说对接当日（第0天）之前的历史数据不可用。</li><li>指定某天的S2S API广告收入数据会在第1、2、3天更新。</li><li>对于数据总览、群组和活跃面板的广告收入数据，以及通过Master API和Cohort API传输的数据，AF会进行回溯更新；对于原始数据导出以及Pull API中的广告收入数据，AF不会回溯更新。如果您购买了高阶收入套餐，Data Locker也会更新广告收入数据。</li></ul> |
| 账户用户权限 | 支持 |
| SKAN | 展示级别的广告收入SDK API支持SKAN。 |
| 地理位置/国家 | 在群组面板中，如果地理位置信息不可用（呈现为“N/A”），则按地理位置汇总数据时面板不呈现N/A数据。 |
| 应用内事件回传 | <ul><li>向渠道回传的数据仅限归因到该渠道的应用内事件，不能将回传的事件来源设置为“所有媒体渠道，包括自然流量”。<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#回传中的事件来源选项">详情请见此处说明。</Anchor></li><li>仅可通过展示级别的SDK对接和设备级别的S2S API对接向广告平台发送广告收入事件回传。</li></ul> |
| CTV、PC和主机端应用 | <ul><li>支持安卓和iOS应用。</li><li>Vungle支持Windows平台（UWP）。</li><li>不支持其他任何平台。</li></ul> |
| 广告收入去重 | 不支持设备级别的API MAX对接 |
| Customer user ID（客户用户ID，即CUID） | 支持 SDK 和设备级别的集成。 |
| 仪表板中的事件计数 | 预计日内（今日）数据的事件数量将高于历史同期水平。历史数据被汇总为独特的广告收入展示次数（同一设备×网络×广告单元×投放），导致事件计数较低。 |

</Accordion>

<div id="list-of-ad-revenue-integrated-partners" />

<Accordion title="已对接广告收入的渠道列表">

<table><thead><tr><th rowspan="2">适用渠道</th><th colspan="3">可用的对接类型</th></tr><tr><th>汇总级别</th><th>设备级别</th><th>展示级别</th></tr></thead><tbody><tr><td>Admost</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./applovin-campaign-configuration#ad-revenue-tab" target="_blank">AppLovin</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./applovin-max-ad-revenue-configuration" target="_blank">AppLovin Max</a></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./appodeal-campaign-configuration" target="_blank">Appodeal</a></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td> <a href="./bytedance-ads-china-campaign-configuration" target="_blank"></a><a href="./bytedance-ads-china-campaign-configuration" target="_blank">Bytedance Ads - 中国本地流量</a> </td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Pangle（TikTok for Business）</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./chartboost-campaign-configuration#ad-revenue-tab" target="_blank">Chartboost</a></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td></tr><tr><td>Custom Mediation</td><td>-</td><td>-</td><td><span>✓</span></td></tr><tr><td>Google Ad Manager</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./meta-ads-integration-setup" target="_blank">Meta ads</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./fyber-campaign-configuration#ad-revenue-tab" target="_blank">Fyber</a></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./google-admob-ad-revenue-attribution-configuration" target="_blank">Google Admob</a></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td></tr><tr><td>Inmobi</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td> <a href="./ironsource-campaign-configuration#ad-revenue-tab" target="_blank">ironSource</a> (LevelPlay)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Mintegral</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Odeeo</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tapjoy</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Topon</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Topon Pte</td><td>-</td><td>-</td><td> <span>✓</span><br/> </td></tr><tr><td>Tradplus</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./unity-ads-campaign-configuration" target="_blank">Unity Ads</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Unity Ads Mediation</td><td>-</td><td>-</td><td><span>✓</span></td></tr><tr><td>Voodoo</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./vungle-campaign-configuration" target="_blank">Vungle</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Yandex</td><td>-</td><td>-</td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div data-zendesk-anchors="ad-revenue-attribution=%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E5%BD%92%E5%9B%A0 01ECF1PZ2XNCHR4QPATTBV0VMV=%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E5%BD%92%E5%9B%A0 01ECF1PZ2Y6ZBAWSNQPEXGJWX3=integration-types-for-ad-revenue-attribution implementation=%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F 01ECF1PZ2Y9ERT5C50ZD4CDJET=%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F 01ECF1PZ31TBRGG7GW3404Y1HN=connect-to-ad-revenue-integrated-partners h_01JYRKB8Q34X79MZ4JY99T6YXY=view-edit-and-delete-ad-revenue-integrated-partners 01H8V10BKK6TVY9G1KWC273K0S=deduplicate-cross-referenced h_01JYRKB8Q3D3W0FM75VH78XQTS=aggregate-granularity-using-app-open-or-inapp-events aggregate-ad-revenue-using-events=%E6%8C%89%E4%BA%8B%E4%BB%B6%E6%B1%87%E6%80%BB%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5 01H8V10BKK06Z3E823G6GNTPKH=%E6%8C%89%E4%BA%8B%E4%BB%B6%E6%B1%87%E6%80%BB%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5 comparison-of-inapp-event-methods=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E9%85%8D%E7%BD%AE%E6%96%B9%E5%BC%8F%E5%AF%B9%E6%AF%94 01H8V10BKKMG2A704NZC2VFSJM=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E9%85%8D%E7%BD%AE%E6%96%B9%E5%BC%8F%E5%AF%B9%E6%AF%94 01ECF1PZ32Z4C20NADJ2SF3EPC=ad-revenue-api-status-and-testing ad-revenue-data=%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE 01ECF1PZ3315R242DC78HV60YC=%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE 01ECF1PZ33EJHN1YY0DMFKWY7N=ad-revenue-aggregate-data overview-dashboard-aggregated-performance-report=%E6%95%B0%E6%8D%AE%E6%80%BB%E8%A7%88%E9%9D%A2%E6%9D%BF%E6%B1%87%E6%80%BB%E6%95%88%E6%9E%9C%E6%8A%A5%E5%91%8A 01ECF1PZ348365STFGE3136WEJ=%E6%95%B0%E6%8D%AE%E6%80%BB%E8%A7%88%E9%9D%A2%E6%9D%BF%E6%B1%87%E6%80%BB%E6%95%88%E6%9E%9C%E6%8A%A5%E5%91%8A 01ECF1PZ348P0JCBASS4QBD56W=%E7%A4%BA%E4%BE%8B 01ECF1PZ36R9W7A0X4WBR95JDS=ad-revenue-raw-data fields-populated-by-ad-revenue=%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E5%A1%AB%E5%85%85%E5%AD%97%E6%AE%B5 01H8V10BKK7BHC31W27G22D23K=%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E5%A1%AB%E5%85%85%E5%AD%97%E6%AE%B5 fields-by-network=%E5%88%86%E5%8F%98%E7%8E%B0%E6%B8%A0%E9%81%93%E7%9A%84%E5%AD%97%E6%AE%B5%E5%A1%AB%E5%85%85%E6%83%85%E5%86%B5 01H8V10BKKW6NERRYCRD6BVZ54=%E5%88%86%E5%8F%98%E7%8E%B0%E6%B8%A0%E9%81%93%E7%9A%84%E5%AD%97%E6%AE%B5%E5%A1%AB%E5%85%85%E6%83%85%E5%86%B5 01H8V10BKK6N5XJ6GHKC201E3Y=data-freshness 01H8V10BKKG50X5RZR8T2YB092=ad-revenue-data-locker-reports h_01KRKHJN2G5SER73D3EZB14GDS=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85 additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H8V10BKMX7H9H04ZBF3HRJVY=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H8V10BKMH781GR6GHFSD5N50=migrating-from-aggregate-to-userlevel-granularity 01ECF1PZ39PTEPWJDQA4XPBR4R=traits-and-limitations 01ECF1PZ3A2E5GVNC6D6XDC6WW=list-of-ad-revenue-integrated-partners" />

---
title: 再营销广告归因指南
metadata:
  keywords:
    - Attribution
    - Re-targeting
    - retargeting
    - Advertisers
    - reatribution
    - re-atribution
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-30T13:18:26Z'
  edited_at: '2026-10-14T10:11:46Z'
  id: 207033786
  locale: zh-cn
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/zh-cn/articles/207033786
---
> **概要：概要：再营销广告能促使沉睡用户再次打开并使用应用，或让已卸载的用户重新下载并激活应用。**

<div id="retargeting-fundamentals" />

## 再营销的基本原理

当用户点击[再营销归因链接](/docs/retargeting-attribution-guide#retargeting-attribution-links)或<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">深度链接</Anchor>时，就构成了与在营销广告的互动，这时就会发生再营销归因。再营销归因的结果分以下两种：

* **再互动：再互动（沉睡用户唤醒）：用户设备上仍装有相关应用，这时用户与再营销广告互动后打开该应用，则展示该广告的媒体渠道就会获得一次再互动归因。**
* 再归因（流失用户召回）：即再营销广告带来的重装激活。如果上述情况发生在<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口期</Anchor>内，那么AF会将这次重装激活归因给展示相关广告的再营销渠道，并记录为一次再归因。相关文档：重装激活

![](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

在投放再营销广告之前，请先查看下一节中的再互动归因规则以及示例，然后再根据本文所述的再营销流程设置再营销归因。建议您先熟悉AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">归因模型</Anchor>以及相关的归因窗口期，以便于理解本文内容。

<div id="tip" />

> 👍 **提示**
>
> 如需进一步了解再营销，请查看我们在<Anchor target="_blank" href="https://elevate.appsflyer.com/pages/142/remarketing">AppsFlyer充电站里为您准备的相关课程</Anchor>。视频虽短，但干货满满！

<div id="reengagement-rules-and-windows" />

<Accordion title="再互动的归因规则和窗口期">

* 再营销归因规则用于判定某个事件是否为再营销事件，并将其归因到相关的再营销渠道。
* 在SRN上投放的再营销广告所形成的再互动通过API上报，而非SRN的再互动则通过归因链接上报，这与拉新广告的上报方式相同。
* 归因规则建立在用户链路之上，包含以下两方面：
  * [归因窗口期](/docs/retargeting-attribution-guide#归因窗口期)：在该窗口期内发生的互动会被记录为再互动。
  * [排除窗口期](/docs/retargeting-attribution-guide#排除窗口期)：在该窗口期内发生的互动不会被记录为再互动。
* 如果AF记录到了再互动，则相关再互动窗口期内发生的应用内事件会得到<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">双重归因</Anchor>。也就是说，这些应用内事件会被同时归因到再营销渠道和最初的UA渠道（若有）。

下图说明了再互动的归因规则，帮助您判断用户与再营销广告的互动是否会被归因为再互动。

**再互动归因规则**

![](https://files.readme.io/e6643112f3e9969242c0dd394f6401406fbc837a9494cc4bb3825cff6365f36d-33563511578513.png)**参考信息——归因窗口期和排除窗口期**

下表说明了再营销归因的相关窗口期。

<div id="inclusion-windows" />

#### 归因窗口期

| 窗口期类型 | 说明 |
| --- | --- |
| 浏览型归因 | 用户从浏览广告到打开应用之间的最长间隔时间。<br /><br />归因链接<br /><br />**时长**：<ul><li>默认1天</li><li>范围：12-1512小时（63天）</li></ul> |
| 点击回溯 | 用户从点击广告到打开应用的最长间隔时间。<br /><br />归因链接<br /><br />**时长**：<ul><li>默认7天</li><li>范围：12-1512小时（63天）</li></ul>SRN相关说明：请确认您使用的SRN是否有其特定的回溯窗口期规定。 |
| Re-engagement（再互动） | 请注意再互动窗口期的以下相关事项：<ul><li>用户与再营销渠道互动后首次打开应用时，该窗口期开始计时。</li><li>在该窗口期内发生的应用内事件会得到<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">双重归因</Anchor>，即同时归因给再营销渠道和拉新渠道。</li><li>该窗口期的时长由广告主在AF后台的应用配置页中设置，或取决于具体的SRN。</li><li>如果用户在再互动窗口期内与其他的再营销广告进行了互动，且互动时间不在排除窗口期内，则当前的再互动窗口期立即终止，并重新开始另一轮再互动窗口期的计时。</li><li>直到发生新激活、重装激活为止，或以数据保留规定为准。</li></ul>归因链接<ul><li>默认30天</li><li>范围：</li></ul>如果您更改了该窗口期的设置，新设置会对之后的再互动生效，但不会影响已经记录到的再互动。 |

<div id="exclusion-windows" />

#### 排除窗口期

| 窗口期类型 | 说明 |
| --- | --- |
| 再互动转化间的最短时间 | AF不会在这个排除窗口期内记录再互动。<br /><br />**再互动转化间的最短时间**<ul><li>该窗口期从再互动发生时开始计时，在该窗口期内发生的应用内事件会同时归因到再营销（主）和拉新（次）投放。</li><li>这样，您就能衡量再营销广告的投放效果了。</li><li>如果在该窗口期内有另一个广告平台或广告系列带来了一次再互动：<ul><li>【默认】当前的再互动窗口期结束，记录到一次新的再互动，且之后的应用内事件会归因到最近的那一次再互动。</li><li>为了防止出现以上情况，建议设置再互动转化之间的最短间隔时间，这样就能仅记录过了这段时间之后发生的再互动。</li></ul></li><li>如果再互动窗口期比您设置的最短间隔还要短，那么这个最短间隔等于无效。举例来说，举例说明：如果再互动窗口期为1天，而最短间隔设置为4天，那么该设置完全不会影响到任何一次再互动。</li><li>该设置不会限定激活和再互动之间的时间间隔。</li></ul>**时长**：<ul><li>默认无</li><li>范围：12-1512小时（63天）</li></ul> |
| <Anchor target="_blank" href="/marketers/zh/docs/set-retargeting-inactivity-window">最短沉睡时长</Anchor> | AF不会在这个排除窗口期内记录再互动和再归因。<br /><br />配置方位：相关渠道配置页面的对接选项卡。<br /><br />**时长**：<ul><li>默认无</li><li>0-30天</li></ul>SRN相关说明：请注意，SRN通常设有自己的沉睡时长规则。如果您的设置与SRN不同，会导致数据差异。 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因（reattribution）</Anchor> | 再归因窗口期仅对再归因生效，不会影响到再互动。<br /><br />用户与再营销广告互动后，在再归因窗口期内重新安装并激活相关应用，该用户就会被归因到对应的再营销渠道。相关文档：<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#reinstalls">重装激活</Anchor><br /><br />应用配置 |

<div id="example-flow-implementing-the-rules" />

#### 再营销归因链路示例

![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)

点击和浏览型再互动归因的规则列表：

| 规范 | 规范 |
| --- | --- |
| A | 用户与再营销广告互动，即用户浏览或点击了一则再营销广告。 |
| B | 该次广告互动发生在点击回溯窗口期或浏览窗口期**内**。 |
| C | 用户的实际沉睡时长超过广告主设定的最短沉睡时长。 |
| D | 在再互动窗口期内发生了应用内事件。 |
| E | 前后两次再互动之间的时间间隔大于广告主指定的最短间隔。 |

</Accordion>

<div id="example-retargeting-scenarios" />

<Accordion title="再营销场景示例">

| 场景2场景1：在再互动窗口期之前、之内、之后发生了购买事件<br /><br />用户链路：<ul><li>与Z渠道的广告互动，激活应用并完成了一次购买（A）。</li><li>与Y渠道的再营销广告互动，打开应用并完成了一次购买（B）。</li><li>完成了一次购买（C）。</li></ul>![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)<br /><br />P/S列：P代表主要归因（Primary），S代表次要归因（Secondary），详见<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">再营销事件双重归因</Anchor> |
| --- |
| **场景2示例2：“再互动”归因窗口期间发生多次转化**<br /><br />用户链路：<ul><li>与Z渠道的广告互动，激活应用并完成了一次购买（A）。</li><li>与Y渠道的再营销广告互动，打开应用并完成了一次购买（B）。</li><li>完成了一次购买（C）。</li></ul>![](https://files.readme.io/bf57f8a9597bd56a89bb3f1be3700195e1b153b548cb11ee3d37c65d5382e711-33563474530321.png)<br /><br />P/S列：P代表主要归因（Primary），S代表次要归因（Secondary），详见<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">再营销事件双重归因</Anchor> |

</Accordion>

<div id="retargeting-operations" />

## 再营销设置

<div id="retargeting-settings" />

<Accordion title="再营销设置">

如需启用再营销归因，请务必完成以下设置。具体细节取决于您的再营销场景。

| Conversion type （转化类型） | SRN | 非SRN |
| --- | --- | --- |
| Re-engagement（再互动） | <ol><li>从AppsFlyer后台的侧边栏中选择**配置** > **应用配置**。</li><li>检查**再互动归因**开关是否处于打开状态。</li><li>从AppsFlyer的侧边栏中选择**协作** > **活跃对接**，然后选择相关的SRN。</li><li>打开**再互动归因**开关。</li></ol> | <ol><li>从AppsFlyer后台的侧边栏中选择**配置** > **应用配置**。</li><li>检查**再互动归因**开关是否处于打开状态。</li><li>在归因链接中添加下文所述的再营销参数。</li></ol> |
| 再归因（reattribution） | <ol><li>从AppsFlyer的侧边栏中选择协作 > 活跃对接。</li><li>打开**重装激活归因**开关。</li></ol> | <ol><li>无需在面板中设置。</li><li>在归因链接中添加下文所述的再营销参数。</li></ol> |

<div id="non-srn-settings" />

#### **非SRN设置**

**请按以下方式将广告平台（非SRN）设置为再营销渠道**：

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 选择相关广告平台。
3. 打开**启用再营销设置**开关。   

   [![](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)
4. 请根据需要选择
   * **使用标准归因链接**进行单平台（分应用）跳转。
   * **使用OneLink**。
     * 如有需要，请输入**深度链接URL**（详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">深度链接指南</Anchor>）
5. 复制后台生成的URL，将其发送给广告平台，用于再营销广告。  
   **请注意**：注意：该URL无法保存，会在关闭页面后消失。

</Accordion>

<div id="retargeting-dashboard" />

<Accordion title="重定向控制面板">

除了用户获取指标之外，数据总览面板中还包含LTV维度的再营销指标，相关数据来自于再营销广告互动的用户。

**请按以下方式查看再营销数据**：

1. 从后台侧边栏中选择**分析** > **数据总览**。
2. 点击**视图类型**，然后选择**再营销**。  
   面板会显示再营销。  
   **请注意**：您也可以在统一视图中查看再营销数据，详情请见面板视图类型。

</Accordion>

<div id="retargeting-attribution-links" />

<Accordion title="再营销归因链接">

* 再营销链接类似于常规的用户获取链接。
* 创建再营销链接后可将其用于：
  * 支持再营销的非SRN。
  * 自有媒体（在<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">链接管理</Anchor>页配置）。

再营销归因链接参数

| 参数 | 说明 | 必须配置 |
| --- | --- | --- |
| `is_retargeting` |  | 是 |
| Advertising ID | 广告ID可用时尽量发送广告ID，包括IDFA、OAID、IDFV等等。<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#probabilistic-modeling">详情请见iOS应用的概率模型归因局限性。</Anchor> | 否 |
| 再营销点击回溯窗口 | <ul><li>再营销<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">点击回溯窗口</Anchor>与拉新广告的点击回溯窗口原理相同。</li><li>这个窗口期从用户点击广告开始计算，在窗口期内发生的转化才会被归因到该点击。</li><li>默认为7天。</li></ul>**<span id="01ECF12NKTFH6Q2NH4B1WKSYF9"></span>示例**<br />如需将点击回溯窗口期设置为14天，请在再营销广告的归因链接中加入以下参数：`&af_click_lookback=14d`&af\_click\_lookback=14d&af\_click\_lookback=14d | 否 |
| 再营销浏览回溯窗口 | <ul><li>再营销<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">浏览回溯窗口</Anchor>与拉新广告的浏览回溯窗口原理相同。</li><li>这个窗口期从用户浏览广告开始计算，在窗口期内发生的转化才会被归因到该次浏览。</li><li>默认为1天。</li><li>该回溯窗口是通过以下参数设置的：</li></ul>`af_viewthrough_lookback={time}`<br /><br /><br /><br />**<span id="01ECF12NKTE8W4K72VATN9RM2X"></span>示例**<br />如需将浏览窗口期设置为5小时，请在再营销广告系列的归因链接中添加以下参数： `&af_viewthrough_lookback=5h`&af\_viewthrough\_lookback=5h&af\_viewthrough\_lookback=5h | 否 |
| 再互动窗口期 | <ul><li>您可以在AF后台的归因链接部分配置**再互动窗口**，该操作用于设置归因链接中的**af\_reengagement\_window**参数。您也可以手动添加该参数。</li><li>默认值为30天。</li><li>可用的再互动窗口期范围如下：</li><li>若以小时为单位：1-23小时</li><li>1-90天60天。</li><li>全周期：不限：窗口期一直延续到用户卸载应用或再次与应用互动为止，对应的参数为af\_reengagement\_window=lifetime</li></ul>举例来说，**af\_reengagement\_window=60d**表示再互动发生后60天内上报的事件会被归因到再营销渠道。 | 否 |

<div id="retargeting-view-through-lookback-period" />

#### 再营销浏览回溯窗口

```http
https://app.appsflyer.com/id123456789?pid=remerge_int&af_dp=mydeeplink%3A%2F%2F&
clickid={clickid}&af_siteid={publisher}&idfa={device_id_raw}&sha1_idfa={device_id}
&af_sub1={creative_name}&is_retargeting=true&af_reengagement_window=60d
```

</Accordion>

<div id="retargeting-reports-and-raw-data" />

<Accordion title="再营销报告及原始数据">

* 再营销报告与UA的<Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview">汇总</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">原始数据</Anchor>报告原理类似，可通过报告工具拉取。
* AF会对再营销的应用内事件和应用打开（session）数据进行<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">双重归因</Anchor>。

**再营销转化报告**

* 再营销转化报告中包含再互动和再归因的原始数据。
* 部分字段在再营销报告和用户获取报告中分别具有不同的含义。

再营销场景中的原始数据解读

| 栏位 | **说明** |
| --- | --- |
| 事件名称 | <ul><li>该字段中的值取决于具体的报告类型。</li><li>应用内事件名称</li><li>再营销转化报告：re-engagement（再互动）或re-attribution（再归因）**请注意**：该字段在Data Locker中可能出现的值及其含义如下：<ul><li>install是指再归因</li><li>retargeting是指再互动</li></ul></li></ul> |
| 归因到的触点类型 | 用户与广告的互动形式，可能出现的值为：<ul><li>Click（点击）</li><li>Impression（展示）</li></ul> |
| Attributed touch time | 用户与再营销广告互动的时间 |
| Install time | 再互动或再归因后，用户首次打开应用的时间。 |
| Event time | 事件发生的时间 |
| AppsFlyer ID | <ul><li>再归因（流失用户召回）：</li><li>Re-engagement</li></ul> |
| Is retargeting | 对于再营销转化和事件，该字段的值为TRUE |
| Is primary attribution | 对于再营销转化和事件，该字段的值为TRUE |
| Retargeting conversion type | 该字段未来将弃用（下线日期待定）。转而通过conversion\_type和campaign\_type来判断转化行为的背景信息。<ul><li>Re-engagement（再互动）</li><li>再归因（reattribution）</li></ul> |
| Conversion type （转化类型） | 指转化类型，可能出现的值为：<ul><li>激活</li><li>Reinstall（重装激活）（1）</li><li>Re-engagement（再互动）</li><li>Unknown（未知）（2）</li></ul>1）如果conversion\_type=reinstall（转化类型为重装激活）且campaign\_type=retargeting（广告系列类型为再营销），则相当于retargeting\_conversion\_type=re-attribution（再营销转化类型为再归因）<br /><br />2）没有归因到任何渠道的应用内事件/应用打开（session） |
| Campaign type | 带来相关用户的流量来源，可能出现的值为：<ul><li>UA（用户获取）</li><li>自然量</li><li>再营销</li><li>Unknown（未知）</li></ul> |
| Attribution lookback | 再营销点击回溯窗口期 |
| Original URL | 该列可能出现的内容为：<ul><li>再营销链接</li><li>深度链接数据</li><li>若对应渠道为SRN，则该列为空</li></ul> |
| 助攻字段 | 不适用于再互动 |

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="probabilistic-modeling" />

<Accordion title="概率模型">

AF的再营销衡量从2021年2月17日起开始支持概率模型归因，但对于<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#note-for-ios-apps">iOS 14.5+应用</Anchor>的归因有一定局限性。用于再营销概率模型归因的回溯窗口是由AppsFlyer动态设置的，具体时长取决于用户的操作系统。

请确保发送的点击带有必要的概率模型参数。

</Accordion>

<div id="app-requirements" />

<Accordion title="应用的必备条件">

如需为某个应用投放再营销广告，该应用必须符合以下要求：

* iOS
  * 除了标准的AppsFlyer SDK对接以外，您还必须在应用的委托类（delegate）中额外添加代码，详见<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#onelink深度链接">SDK对接指南</Anchor>（归因链接部分）。
  * 对于在iOS 9中运行的应用，还必须添加Universal Link App Open代码。详见<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">在iOS 9中使用Universal Link</Anchor>。
* 安卓：

  * 如需使用深度链接打开应用中的某个具体页面（非主页），请参考<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#deep-linking">SDK对接指南</Anchor>（归因链接部分）的说明。

</Accordion>

<div id="retargeting-limitations" />

<Accordion title="再营销局限性">

* AF的再营销衡量从2021年2月17日起开始支持概率模型归因。
* 您可以在数据总览和群组面板及报告的统一视图中查看再营销的投放成本数据。

</Accordion>

<div id="faq" />

<Accordion title="常见问题解答">

| **再营销点击**：<ul><li>看到再营销广告的用户点击AppsFlyer归因链接时，就形成了再营销点击。</li><li>来自SRN或<Anchor target="_blank" href="/marketers/zh/docs/measuring-push-notification-re-engagement-campaigns">推送消息</Anchor>的点击不计入此项指标。</li><li>部分点击形成了新增激活，进而被归因到用户获取广告。当现有用户或过去用户在<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口</Anchor>期满后与再互动链接互动并安装时，会发生这种情况。</li></ul> |
| --- |
| **在哪些情况下attributed touch time（记录到的广告触达时间）与install time（激活时间）的值是相同的？**<ul><li>通过universal link或Android app link实现的深度链接可直接将用户跳转到应用中，无需先发送到AppsFlyer服务器。</li><li>当用户打开应用且SDK记录到新的再互动时，AppsFlyer会使用该次应用打开的时间戳来展示点击数据，因而使再互动与应用打开的时间相同。</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">AppsFlyer归因模型</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/audiences-guide">受众共享（Audiences）功能指南</Anchor>

<div data-zendesk-anchors="retargeting-fundamentals=%E5%86%8D%E8%90%A5%E9%94%80%E7%9A%84%E5%9F%BA%E6%9C%AC%E5%8E%9F%E7%90%86 h_01HCFJHC85VK0A05X5F69E2WKT=%E5%86%8D%E8%90%A5%E9%94%80%E7%9A%84%E5%9F%BA%E6%9C%AC%E5%8E%9F%E7%90%86 h_01HCFJHC851PV0VR42H07VQAXF=%E6%8F%90%E7%A4%BA h_01HCFJHC85EW8MBQ8MBXBVPF03=reengagement-rules-and-windows inclusion-windows=%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F h_01HCFJHC85FRFJ531Y08DW03Y2=%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F exclusion-windows=%E6%8E%92%E9%99%A4%E7%AA%97%E5%8F%A3%E6%9C%9F h_01HCFJHC85ECS3PJV80D943TVY=%E6%8E%92%E9%99%A4%E7%AA%97%E5%8F%A3%E6%9C%9F example-flow-implementing-the-rules=%E5%86%8D%E8%90%A5%E9%94%80%E5%BD%92%E5%9B%A0%E9%93%BE%E8%B7%AF%E7%A4%BA%E4%BE%8B h_01HCFJHC8529NW0ABMQ0RB3E8R=%E5%86%8D%E8%90%A5%E9%94%80%E5%BD%92%E5%9B%A0%E9%93%BE%E8%B7%AF%E7%A4%BA%E4%BE%8B h_01HCFJHC85E1SWGYN0BH603BV9=example-retargeting-scenarios retargeting-operations=%E5%86%8D%E8%90%A5%E9%94%80%E8%AE%BE%E7%BD%AE h_01HCFJHC863XPHNWRHJ60JPSRF=%E5%86%8D%E8%90%A5%E9%94%80%E8%AE%BE%E7%BD%AE h_01HCFJHC86XNCT5AQP48R9ZDC4=retargeting-settings nonsrn-settings=%E9%9D%9Esrn%E8%AE%BE%E7%BD%AE h_01HCFJHC865V36R3H58D5PWXYY=%E9%9D%9Esrn%E8%AE%BE%E7%BD%AE h_01HCFJHC860BS9YJM99G437G24=retargeting-dashboard h_01HCFJHC860Y5HZN66DRNN2Q89=retargeting-attribution-links retargeting-viewthrough-lookback-period=%E5%86%8D%E8%90%A5%E9%94%80%E6%B5%8F%E8%A7%88%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01HCFJHC863CSP03AYBXFSNC37=%E5%86%8D%E8%90%A5%E9%94%80%E6%B5%8F%E8%A7%88%E5%9B%9E%E6%BA%AF%E7%AA%97%E5%8F%A3 h_01HCFJHC86MNFRGYMN776FYHJV=retargeting-reports-and-raw-data additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HCFJHC86RKKPPMBYEZV4Q3X9=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HCFJHC8690EN19DDX7P24AD0=probabilistic-modeling h_01HCFJHC862E6C46Q7645VJ6CZ=app-requirements h_01HCFJHC86SMKZ1HT5KHQNQS1N=retargeting-limitations h_01HCFJHC86BVSVRNAGJEKZFCJP=faq h_01HE7TPR7928SF2W8ZJS55Y5BG=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

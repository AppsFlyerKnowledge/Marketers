---
title: Protect360防作弊解决方案
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - p360
    - p 360
    - 360protect
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2016-12-06T07:47:17Z'
  edited_at: '2026-10-14T10:10:44Z'
  id: 218254203
  locale: zh-cn
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/zh-cn/articles/218254203
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 概要：归因作弊不但会对广告主造成严重的营销资金浪费，而且还会扭曲投放效果，导致投放策略的误判。**Protect360能通过实时拦截和归因后检测来保护广告主不受假量侵扰。**

![p360intro2.jpg](https://files.readme.io/c8476382eeff62164ca93b9bf2f3c4cdbe0609d4160047eac36a44d5f333ffdb-360014803578.jpg)

## Protect360简介

* 保护广告主不受归因作弊的侵害，其中的动态工具可用于识别作弊并拦截假量。
* 以AppsFlyer的海量数据、机器学习以及行为分析为基础，P360可以探测到各种已知和新生的点击/激活作弊，包括自动化脚本/程序（bots）以及行为异常。
* 在设备、媒体和广告平台层级帮助营销人员阻断广告作弊。
* 采用实时拦截与归因后识别相结合的逐层递进式方案阻断广告作弊。
* 对用户体验没有任何影响。对于涉及真实用户的作弊行为，P360不会干扰其正常的应用激活，仅会在归因记录中反应相关的作弊行为。

<div id="realtime-blocking" />

<Accordion title="实时拦截">

* 如果某次激活在归因之前被AF实时判断为来自作弊媒体的假量，那么该激活就会从归因链路中被拦截下来。
* 来自相应用户的后续应用内事件也会被拦截。
* 已拦截的激活和应用内事件会显示在Protect360的面板和已拦截的假量报告中。
  * 被阻止的安装和应用内事件：这些事件未包含在AppsFlyer归因和仪表板中，因为它们从未被归因。
* AF会将被拦截的激活回传给对应渠道，其中还包含拦截原因，以便渠道进行优化。

<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports">进一步了解被拦截的事件</Anchor>

</Accordion>

<div id="postattribution-detection" />

<Accordion title="归因后识别的假量">

* 在归因完成后检测到的作弊行为称为归因后识别的假量。AF可在这类假量的激活当天到之后7天（共8天）内对其进行检测识别。
* 激活一旦被归因，其归因记录就无法消除。因此，AF在处理归因后识别的假量时使用的方式与实时拦截有所不同。
* 归因后追溯到的激活和应用内事件假量也视为确凿的假量，不收取任何归因费用。

一旦某个渠道（如广告平台或子渠道）被判定为作弊渠道：

* 后续来自该渠道的点击会被拦截。
* 此前发生的激活：
  * 从当月（以公历日期为准）月初至今发生的激活将标记为归因后识别的假量，但**归因数据中不会将其剔除**。自2020年1月起，这些激活的归因费用不会再记入P360客户的账单中。
  * 当月月初之前发生的激活没有变化。
* 应用内事件：

  * 发生在AF标记激活**之前**：标记为假量
  * **发生在AF标记激活之后：标记为假量。**

  请注意：对于被识别为欺诈的用户获取（UA）重新安装，Protect360通过将安装重新分配给有机来源来纠正归因。因此，这些重新安装的任何后续应用内事件都归因于有机，并将出现在有机应用内事件报告中。

归因后识别的作弊类型包括：

* 激活看似正常，但激活后的应用内事件中有作弊迹象
* AF发现了一种新型的作弊方式
* P360算法收集某个媒体的统计数据，达到一定量级后检测出异常，从而识别出虚假激活

</Accordion>

<div id="common-fraud-issues-and-solutions" />

<Accordion title="常见的作弊问题和解决方案">

当 AppsFlyer 识别欺诈时，与欺诈关联的**归因** **事件**将被拦截。这消除了欺诈者的收益和动机。**请注意**：应用安装本身发生并且没有被阻止。这意味着应用程序用户可以使用该应用程序，并为广告主产生收入。

您可以在<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports">Protect360假量原始数据报告</Anchor>中查看已拦截的作弊点击、激活和应用内事件。

下表说明了广告作弊的类型以及Protect360对应的处理方式。

| 作弊类型 | 描述 | AppsFlyer解决方案 |
| --- | --- | --- |
| <span id="device-id-reset-fraud"></span>**DeviceID 重置作弊** | 作弊平台会不断在同一台实体设备上重置设备ID，以此来生成大量激活。 | AppsFlyer会识别异常的新设备比例，并屏蔽对应的流量来源。 |
| <span id="install-hijacking"></span>**安装劫持** | 作弊平台会在移动设备上植入恶意软件，当该设备上安装新应用时向作弊平台发送通知。然后作弊平台会立即向AppsFlyer发送点击，试图抢得该次激活的归因。 | <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-to-install-time-ctit/">AppsFlyer会拦截CTIT</Anchor>（点击到激活时间）过短，且通过Google Play服务器侧API发出的末次点击。 |
| <span id="click-hijacking"></span>点击劫持 | 恶意软件探测到相关应用即将激活后立即发送点击，试图劫取末次点击的归因。 | 如果在同一设备上对于同一应用发生点击后，很快又有获得归因的点击出现，这时AppsFlyer会拦截这些末次点击。 |
| <span id="click-flooding"></span>点击刷量 | 通过发送大量虚假点击制造假量的作弊方式，意在抢得激活前的末次点击。 | 对于转化率低、CTIT长的子渠道，AF会拦截其末次点击。 |
| <span id="behavioral-anomalies"></span>**行为异常** | 作弊平台生成虚假的激活后行为，这类行为会呈现出前后不一致或异常的迹象。 | 凭借AF独有的数据量级在应用、地区、广告平台和子渠道等各个层级对广告互动的行为模式进行跟踪和分析，从而实时检测出非人类行为模式，从源头上遏制假量的侵入。 |
| <span id="ip-denylists"></span>**IP黑名单** | <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-farms/">对于</Anchor>刷量作弊平台，可以通过IP地址长时间不变这一点来识别。 | <ul><li><Anchor target="_blank" href="http://www.digitalelement.com/">AF通过全球第三方服务商Digital</Anchor> Element获取相关的最新数据，并以此为依据将涉嫌作弊的IP地址加入每日更新的黑名单。</li><li>IP黑名单的保护范围覆盖到所有应用。</li></ul> |
| <span id="sdk-authentication"></span>**SDK验证** | 作弊平台会发送虚假的SDK消息，来模拟高价值用户的行为。 | <ul><li>使用AF专有的哈希协议对SDK和Web服务之间的消息进行加密，防止作弊平台模拟这类消息。</li><li>SDK验证的保护范围覆盖到所有应用。</li></ul> |
| <span id="store-validations"></span>**商店验证** | 欺诈者发送虚假的SDK消息来模拟安装或应用内购买，因此他们可以认领高昂的CPA费用。<Anchor target="_blank" href="/marketers/zh/docs/implement-apple-app-store-itunes-install-validation">苹果商店验证</Anchor> 。 | <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/install-validation/">对于已发生的所有激活和应用内购，AF都会在iTunes中进行</Anchor>激活验证，并在iTunes和Google Play中进行应用内购验证，避免对假量进行归因。 |

**请注意**：注意：上文引用的时间值已经过处理，以保护客户的数据隐私。

<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports">如需进一步了解其他的拦截原因，请参考</Anchor>原始数据说明。

</Accordion>

下表列出了各种激活和应用内事件的作弊类型，以及Protect360在实时拦截/后期探测到这些假量之后的处理方式。

<table><thead><tr><th>作弊类型</th><th>检测时间</th><th>激活的后续处理方式</th><th>应用内事件的后续处理方式</th></tr></thead><tbody><tr><td rowspan="2"><span>虚假激活</span></td><td><span>实时</span></td><td><span>实时拦截</span></td><td><span>实时拦截</span></td></tr><tr><td><span>归因后被识别为假量的激活</span></td><td><span>在归因后识别的激活假量报告中标出</span></td><td><ul><li><span>AppsFlyer记录到应用内事件之后将其识别为假量时，会在归因后识别的应用内事件假量报告中标出。</span></li><li><span>识别后：实时拦截</span></li></ul></td></tr><tr><td rowspan="2"><span>激活归因劫持</span></td><td><span>实时</span></td><td><ul><li><span>实时拦截</span></li><li><span>更正归因结果，将激活归因到有效的末次触达渠道</span></li></ul></td><td><ul><li><span>在原始报告中未显示，仅在仪表板上可见</span></li><li><span>归因到有效渠道（与激活一致）</span></li></ul></td></tr><tr><td><span>归因后被识别为假量的激活</span></td><td><span>在归因后识别的激活假量报告中标出</span></td><td><ul><li><span>AppsFlyer记录到应用内事件之后将其识别为假量时，会在归因后识别的应用内事件假量报告中标出。</span></li><li><p>识别为假量后：在归因后识别的应用内事件假量报告中标记出来（覆盖激活后30天内的应用内事件）\*</p><p>\*AppsFlyer会更正归因结果，将激活后30天内的相关应用内事件归因到有效的末次触达渠道。对于30天之后发生的事件，AppsFlyer不会更正其归因结果。</p></li></ul></td></tr><tr><td rowspan="2"><span>应用内事件假量</span></td><td><span>实时</span></td><td>-</td><td><span>实时拦截</span></td></tr><tr><td><span>归因后被识别为假量的激活</span></td><td>-</td><td><span>在归因后识别的应用内事件假量中标出</span></td></tr></tbody></table>

Protect360防作弊措施及其成效

## Protect360的使用方式

<div id="dashboard" />

<Accordion title="面板">

<Anchor target="_blank" href="/marketers/zh/docs/protect360-dashboard">Protect360面板</Anchor>显示汇总假量数据以及与假量相关的分析信息。

面板版式

激活假量激活：<Anchor target="_blank" href="/marketers/zh/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV维度</Anchor>的假量分析信息，包括实时拦截的激活以及归因后识别的假量。您可以使用筛选和分组选项对激活假量进行细化拆解分析。

被识别为假量的**应用内事件**应用内事件：<Anchor target="_blank" href="/marketers/zh/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">活跃维度</Anchor>的分析信息，包括实时拦截和归因后识别的应用内事件假量。您可以使用筛选和分组选项对激活假量进行细化拆解分析。

</Accordion>

<div id="raw-data" />

<Accordion title="原始数据">

假量的<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports">原始数据</Anchor>可以通过Pull API、导出数据和<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">Data Locker</Anchor>（高阶付费功能）拉取。

原始数据报告分为以下几类：

* 被阻止的报告：已拦截的报告：安装，点击和应用内事件报告。其归因被阻止，且用户没有被归因于任何媒体平台。
* 归因后识别的假量报告
  * 归因于媒体渠道的安装，但后来发现是欺诈性的。
  * 应用内事件：
    * 来自归因后被识别为假量的激活。
    * 与激活本身无关，直接被判断为假量。

* 广告主可以使用这些报告与广告平台核对流量，从而进行相关优化，并根据归因后识别的假量调整归因面板。

</Accordion>

<div id="validation-rules" />

<Accordion title="验证规则">

广告主（应用所有者）可以在<Anchor target="_blank" href="/marketers/zh/docs/implement-validation-rules-to-prevent-fraud">验证规则</Anchor>中设置拦截激活、归因（确保激活被归因到有效的末次触达媒体）、应用内事件的条件。

</Accordion>

<div id="fraud-reconciliation-with-ad-networks" />

<Accordion title="与广告平台核对假量">

广告主可以使用Protect360获取激活和应用内事件假量的原始数据，而广告平台侧可能不会把这些转化记录为假量。

如果您发现某个广告平台一直向您发送来源可疑的流量，可以告知该平台并让其停止发送可疑流量。沟通完相关事宜后，您可以使用原始数据激活报告中的**Attributed Touch Time**（广告触达时间）字段来检查这些可疑的流量来源是否确实不再向您发送激活。

您也可以使用Protect360的数据与广告平台核对流量，并对来源可疑的流量收取退款。

**使用Protect360核对CPI广告的方式如下：**

* 在每月月初与出现作弊流量的广告平台客户经理沟通相关事宜。
* [从已拦截的激活报告和](/docs/protect360-anti-fraud-guide#postattribution-detection)归因后被判断为假量的激活报告中收集相关的激活假量原始数据。
* 将假量的原始数据发送给相关的广告平台，用于流量核对和优化。
* 可以创建仅包含有效安装的原始数据报告，但不包括归因后-重新被判断为假量的激活。为此，您需要下载每月的***UA归因激活***报告，并排除所有在***归因后-重新被判断为假量的***报告中包含的数据。

**使用Protect360核对CPA/CPE广告的方式如下：**

* 在每月月初与出现作弊流量的广告平台客户经理沟通相关事宜。
* [从已拦截的应用内事件报告和](/docs/protect360-anti-fraud-guide#postattribution-detection)归因后被判断为假量的应用内事件报告中收集相关的应用内事件假量原始数据。
* 将假量的原始数据发送给相关的广告平台，用于流量核对和优化。
* 可以创建仅包含有效IAE，但不包括归因后欺诈的应用内事件的原始数据报告。为此，您需要下载每月 ***UA归因的应用内事件*** 报告，并排除 ***归因后欺诈的应用内事件*** 报告中包含的数据。

</Accordion>

## 特点与局限性

<div id="traits-and-limitations::a07033c3" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 广告主权限 | 所有AppsFlyer用户 |
| 渠道权限 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#广告平台权限">需要广告主开通Protect360</Anchor>面板和原始数据的权限。</li><li>广告主使用的广告平台必须与AppsFlyer对接。</li></ul> |
| 代理访问权限 | <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#广告平台权限">需要广告主开通Protect360</Anchor>面板和原始数据的权限。 |
| 代理数据透明化 | 透明代理：可以查看特定媒体来源<br /><br />不透明代理：无法查看特定媒体来源 |
| 应用层级的指定时区 | <ul><li>如果广告主为其账户下的所有应用都配置了同一个时区，那么面板就会使用应用配置中设定的时区来显示数据。</li><li>如果各应用的时区不统一，则面板会按默认的UTC时区显示数据。</li></ul> |
| 数据时效性 | <ul><li>Protect360控制面板每日更新。<br />最新更新时间显示在仪表板中的日期范围过滤器下。</li><li>报告：<ul><li>被阻止的安装和应用内事件：几乎实时持续更新。</li><li>归因后 <Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#eod">每日</Anchor>使用UTC。</li></ul></li></ul> |
| 再次安装 | 假量数据和重装激活仅显示在原始数据报告中，因此面板和原始数据报告中的总体数据会有多处差异。 |
| 再营销 | <ul><li>对于被判定为假量的激活，面板会显示AF记录到的广告互动类型，并细分为激活、再归因和再互动。</li><li>应用内事件：<ul><li>应用内事件（CPA）面板显示来自UA激活的事件假量，但不包含再营销激活的事件假量。</li><li>AF会实时识别来自再归因的事件假量，并记录在原始数据报告中。来自再互动的事件假量无法被识别。</li><li>来自再营销的事件假量无法在归因后识别。</li></ul></li></ul> |
| 局限性 | <ul><li>表格最多包含2万行数据。</li><li>如果您查询的数据范围较大，部分媒体可能会被排除在查询结果之外。您可以通过以下方法解决此问题：<ul><li>缩小查询范围——如缩短日期范围、指定具体应用和媒体渠道等</li><li><Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports">导出Protect360</Anchor>原始数据报告</li><li><Anchor target="_blank" href="/marketers/zh/docs/pull-api-aggregate-data">通过Pull API</Anchor>导出Protect360汇总高级检测报告</li></ul></li></ul> |

特点与局限性

</Accordion>

## 疑难解答及使用技巧

<div id="faq" />

<Accordion title="常见问题解答">

| **Protect360是否可以阻断来自自定义归因链接的假量？**<br /><br />当然！当然，除了广告平台的假量以外，Protect360也会检测并拦截自定义归因链接带来的假量。也就是说，如果您通过自有媒体进行投放，Protect360也能为您提供全方位的反作弊防护，覆盖范围包括网红营销、邮件和短信营销、网页横幅和落地页、社交媒体帖子、推送通知以及二维码等等。 |
| --- |
| **Protect360的V2比V1多了哪些新功能？**<ol><li>P360 V2.0中有3个主要变化：<br />后归因欺诈 - 无论我们展示被阻止的安装，我们也会显示后归因欺诈安装。归因后重新被判断为假量也可以下载原始数据报告使用。</li><li>异常洞察-添加了一个称为“异常洞察”的新部分，广告客户可以在其中通过可视化工具分析异常。该部分替换了之前的“高级检测”（Advanced Detection）选项卡中的2个图表。</li><li>集中查看假量数据——我们下线了“高级检测”选项卡，将所有信息集中在一个页面中，便于您查看假量数据。</li></ol> |
| **为什么“导出数据”页面中没有归因后识别的假量原始数据？**<br /><br />归因后报告位于每个媒体平台的帐户级别，以便简化对帐过程。“ **导出数据”** 页面在单个应用程序级别上，并且仍包含应用程序级别上的“已拦截欺诈”数据，以实现向后兼容性。 |
| **AF会对归因后数据进行回溯更新吗？**<ul><li>**激活**——AF不会回溯更新总览面板中的激活数据以及Protect360面板以外所有其他报告中的激活数据。</li><li>**应用内事件** -归因后将安装识别为假量后，此安装产生的应用内事件将被拦截。以前的应用内事件不会追溯更新。</li></ul> |
| **在异常分析部分选择具体/不同的广告平台时数据会发生变化，这是为什么？**<br /><br />假设您在CTIT异常部分选择AF\_Baseline作为基线，就能看到平台A的异常情况。之后若再将平台A设为基线，就能看到除平台A以外其他平台的异常情况。<br /><br />这个结果实际上是您应该期望的。当您使用可靠的AppsFlyer基线时，就能看到各平台的CTIT异常率。但如果您使用异常平台作为基线，则该平台的激活就不会被视为异常，而其他正常平台的激活由于与其相异，反而会被判定为异常。 |
| **出现异常数据的自然流量也可能是假量吗？**<br /><br />如果自然流量中出现异常数据激增，也有可能是由作弊行为导致的。一般情况下，如果您怀疑AppsFlyer中的某些自然流量是假量，可能是由于以下原因：<ul><li>**失败的归因欺诈：** 归因作弊失败：作弊平台的点击未能获得归因，如撞库作弊中的末次点击发生在点击回溯窗口期之后。</li><li>2019-04 2019-05 归因作弊非归因作弊：/strong>用户的作弊行为与归因无关，如在策略游戏中通过作弊来收集资源。</li><li>**SDK集成问题：** SDK对接问题：/strong>请检查您的应用内事件是否能正常发送，即是否在应用链路中正确的时间点发送正确的事件参数值。</li></ul> |

常见问题解答

</Accordion>

<div id="benchmarks-and-tips" />

<Accordion title="假量检测标准和技巧">

| **检测新设备假量**<br /><br />作弊平台会频繁重置设备ID，以此来伪装其设备，这些ID包括iOS设备的IDFA和安卓设备的GAID。<br /><br />但您可以放心，凭借AppsFlyer强大的数据库，我们可以识别全球98％以上的移动设备。<br /><br />因此，除非广告主有意针对新设备进行定向投放，否则我们一般可以通过新设备占比是否过高来检测群控作弊。<br /><br />**请按以下步骤检测新设备假量：**<ol><li>*从Protect360面板进入***识别的作弊分析**表。</li><li>向右滚动到***设备农场指标—新设备***一列。</li><li>*点击***作弊激活%** 一列的表头，按新设备占比对表格进行降序排列。</li><li>新设备作弊迹象：</li></ol><ul><li>新设备占比较高的渠道。**请注意**：请注意：如果出现大量激活，但新设备占比较低时也有可能是作弊（因为基数很大）。<ul><li>如果某渠道的忠实用户占比低于总体忠实用户比例，则作弊的可能性很高。</li></ul></li></ul>**请注意**：预安装应用程序的广告系列通常具有极高的新设备率，因为这些可能是用户激活新设备时启动的最早的应用程序之一。因此，对于预安装的应用程序，即使新设备的使用率很高，也不太可能发生新设备欺诈。 |
| --- |
| **检测LAT假量**<br /><br />LAT（受限广告跟踪）用户选择不向广告主展示其设备ID，IDFA或GAID。大约15％的iOS用户和10％的Android用户会选择此选项。<br /><br />LAT用户指标与新设备占比指标相似，LAT用户很可能是正常的用户。但如果LAT用户占比过高，则表示可能有作弊行为。<br /><br />**请按以下步骤检测LAT假量：**<ol><li>*从Protect360面板进入***识别的作弊分析**表。</li><li>*向右滚动到***设备农场指标—LAT设备**一列。</li><li>*点击*<strong>作弊激活%</strong>一列的表头，按LAT设备占比对表格进行降序排列。</li><li>LAT设备作弊迹象：</li></ol><ul><li>**LAT**设备占比较高的渠道。**请注意**：请注意：如果出现大量激活，但新设备占比较低时也有可能是作弊（因为基数很大）。</li><li>如果某渠道的忠实用户占比低于总体忠实用户比例，则作弊的可能性很高。</li></ul> |
| **检测撞库作弊**<ol><li>欺诈者通过使用点击泛滥功能，以真实的设备ID发送数百万次点击，希望将其注册归因为真实用户的最终点击。具有此类欺诈的媒体平台的转化率非常低，但质量较高的用户，因为这些是真正的用户。</li></ol>**请按以下方式检测撞库作弊：**<ol><li>*从Protect360面板进入***识别的作弊分析**表。</li><li>*向右滚动到***撞库指标**一列。</li><li>*点击***转化率**一列的表头，按转化率对表格进行生序排列。</li><li>撞库作弊检测标准：</li></ol><ul><li>正常的***转化率***在0.5%到35%之间。<br />可疑来源的转化率异常低，或**低于应用平均转化率的25%**。您可以在仪表板概览页面的“综合性能报告”表中找到此KPI。</li><li>对于边缘来源，将***助攻百分比***与平均助攻率进行比较。您可以在仪表板概览页面的辅助部件中看到正常的辅助比率。<br />**如果某个渠道的助攻率**超过正常助攻率的50%或以上，AF会视其为可疑渠道。<br />请注意：您推广一个应用时使用的渠道越多，正常助攻率就越高。</li></ul> |
| **使用CTIT指标检测撞库**<br /><br />**如果**CTIT的分布较为平均，说明可能出现了撞库作弊。<br />一般情况下，70%的正常激活会在广告互动后的1小时内发生。<br />点击泛滥，实际上虚假的广告互动和真实安装之间没有任何联系。这导致超过30％的欺诈安装，而CTIT的安装时间超过1小时。<br /><br />**检测点击泛滥CTIT指示：**<ol><li>*从Protect360面板进入***识别的作弊分析**表。</li><li>*向右滚动到\*\*撞库指标*-CTIT一列。</li><li>用于撞库检测的CTIT标准：</li></ol><ul><li>通常，  *超过60分钟的值应为30％左右* 。可疑的媒体渠道，此指标超过50％。</li><li>通常， *超过5小时的值应为20％左右* 。可疑的媒体渠道，此指标超过40％。</li></ul>*您可以通过***<Anchor target="_blank" href="/marketers/zh/docs/protect360-dashboard#anomalies-dashboard">异常分析</Anchor>** 页面的信息深入了解CTIT指标异常的可疑渠道。 |

假量检测标准和技巧

</Accordion>

<div id="advanced-antifraud-tips" />

<Accordion title="进阶防作弊技巧">

| **激活数量**<br /><br />按每个检查媒体渠道的安装数量进行过滤，对于检测最大的欺诈媒体渠道很重要。此外，激活数量过低时该规则没有统计意义。请注意：<br /><br />**请注意**：少于30个安装甚至50个安装的媒体渠道不足以得出结论。您可以尝试扩大日期范围或其他的搜索条件，提升样本量。 |
| --- |
| **更改忠实用户的定义**<br /><br />忠诚度用户的默认定义是应用程序打开3次或以上。对于用户参与而言，它是一个重要的KPI，但不幸的是，许多欺诈者都知道并使用它来伪造高忠诚度用户，从而避免了怀疑。通过创建并选择更好的、更详尽的忠诚用户定义，来避免陷入上述困境。<br /><br />分析应用程序的用户质量KPI，例如注册，教程完成，购买，多个会话等。如果用户执行所有KPI列表，则在应用程序代码内，通过应用程序事件发送新的**忠实用户** 。<br /><br />发送第一个非自然的**忠实用户**事件后，转到“ **应用程序设置”** 并选择它以指示您的应用程序的忠实用户定义。预计一般的忠实用户率会略有下降，然后对于欺诈媒体渠道会急剧下降。 |

进阶防作弊技巧

</Accordion>

> 👍 **提示**
>
> 想要了解更多关于防止欺诈的知识吗？我们在<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7809/play/18635/mobile-app-fraud-and-protect360">AppsFlyer充电站里为您准备了相关课程</Anchor>，视频虽短，但干货满满！

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports">原始数据</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/marketers-guide-mobile-ad-fraud/">营销人员的移动端广告作弊初探</Anchor>

<div data-zendesk-anchors="protect360-overview=protect360%E7%AE%80%E4%BB%8B h_01HE7RSPPQ4T5J3W038EZRCTCE=protect360%E7%AE%80%E4%BB%8B h_01HE7RSPPQ5BH7HBK0R8SY1T16=realtime-blocking h_01HE7RSPPRW4CQ3GB9ZEYAA6YN=postattribution-detection h_01HE7RSPPRYMQKJH46JET2ZZ0T=common-fraud-issues-and-solutions using-protect360=protect360%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HE7RSPPR8Y8J1VJJXXDCAZE6=protect360%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HE7RSPPR04G3SCSYHSWJKQDG=dashboard h_01HE7RSPPRS6PSTZCR5RT4A5ND=raw-data h_01HE7RSPPR8C9MHRAGJXYD2VVZ=validation-rules h_01HE7RSPPR1PQ2R6NJPRQGS1K1=fraud-reconciliation-with-ad-networks traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HE7RSPPRV797PS12NFQHX1X5=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HE7RSPPRWRKR1Y25PZV2RMVV=traits-and-limitations::a07033c3 faq-and-tips=%E7%96%91%E9%9A%BE%E8%A7%A3%E7%AD%94%E5%8F%8A%E4%BD%BF%E7%94%A8%E6%8A%80%E5%B7%A7 h_01HE7RSPPSV2TT8SMK8JZXFKMC=%E7%96%91%E9%9A%BE%E8%A7%A3%E7%AD%94%E5%8F%8A%E4%BD%BF%E7%94%A8%E6%8A%80%E5%B7%A7 h_01HE7RSPPS01J796008HDS1CRW=faq h_01HE7RSPPS018W98JWZGED54W8=benchmarks-and-tips h_01HE7RSPPSEDZWRH929DBSWEWM=advanced-antifraud-tips h_01HE7RSPPSY161MSQVQW7M767F=%E6%8F%90%E7%A4%BA h_01HE7RX6167Q5QP5JNZDSXCCK5=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

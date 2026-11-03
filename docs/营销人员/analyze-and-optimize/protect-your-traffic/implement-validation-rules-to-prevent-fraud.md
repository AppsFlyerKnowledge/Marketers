---
title: 实施验证规则以防止欺诈
metadata:
  keywords:
    - Advertisers
    - validation rule
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2017-09-14T14:43:46Z'
  edited_at: '2026-10-14T10:15:16Z'
  id: 115004703926
  locale: zh-cn
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/zh-cn/articles/115004703926
---
> **概要：** 验证规则（Validation Rules）可针对广告误投和作弊强化防护。广告主可以通过自定义的规则，把控应用内事件的拦截和归因修正。

![5906_animation-750x330__1_.gif](https://files.readme.io/2a5fbee83bdbc342c744f8079b743f06cb3205697bd9caa183593c411ae03d08-360014483338.gif)

## 简介

* 广告主可以在AppsFlyer后台的规则配置页面中界定流量的验证规则。我们提供多种可定制的条件和逻辑，帮助广告主筛选出需要保留或拦截的应用激活或应用内事件。
* 这些规则以一系列参数为基础，适用于下列各种使用场景：
  * 排除不符合定向人群的激活（如国家/地区、操作系统版本等不匹配）
  * 流量不符合广告主与广告平台签订的广告订单时，排除相关激活
  * 排除被作弊平台劫持的激活
  * 排除由自动化脚本（bots）、模拟器或设备农场伪造的虚假激活
* 针对应用内事件配置的规则仅对未被拦截的激活所产生的应用内事件生效。
* 如果规则中涉及某个广告平台，则该广告平台的成员可以看到这条规则（但无法看到该规则中涉及的其他广告平台）。这一机制既是为了提高透明度，也有助于广告平台更好地了解其流量质量。
* AppsFlyer实时执行这些规则，触发后即时生效。详情请见验证[结果](/docs/implement-validation-rules-to-prevent-fraud#outcomes)说明部分。
* 标记模式允许您在阻止归因之前，针对实时流量测试验证规则。当规则设置为标记时，AppsFlyer会标记匹配的安装和应用内事件以进行报告和分析，但不会影响归因。使用标记模式监控规则行为，识别可能的误报，并在将规则状态更改为已实施之前确认规则的影响。在[VR标记模式](/docs/implement-validation-rules-to-prevent-fraud#view-validation-rule-impact)中查看更多。
* 购买了<Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide">Protect360</Anchor>的广告主除了自动的Protect360假量拦截和检测功能外，还可以手动设置额外的验证规则。实践证明，这些验证条件对于激活劫持、虚假激活和应用内事件这几种作弊类型非常有效。  
  **请注意**：验证规则仅用于验证未被Protect360判定为假量的激活/应用内事件。

<div id="outcomes" />

<Accordion title="验证结果">

* 适用于激活的验证结果： 阻断当前渠道的归因并将激活归因到上一个触达用户的有效渠道，或彻底阻断归因。具体取决于选定操作。
* 适用于应用内事件的验证结果：阻断应用内事件的归因。
* 详见下表所列的验证规则拦截类型及其结果。

<table><thead><tr><th> </th><th>拦截类型</th><th>说明</th><th>激活数据的呈现位置</th><th>后续的应用内事件</th></tr></thead><tbody><tr><td rowspan="2"><strong>激活假量</strong></td><td>阻断当前渠道的归因并纠正到上一个有效渠道</td><td><ul><li><span>适用于真实激活，可根据您指定的条件归因或不归因到具体渠道。</span></li><li><span>AppsFlyer会纠正归因结果，即将激活归因到上一个触达用户的有效渠道。</span></li><li><span>如果未发现有效渠道，则相关激活会标记为自然量。</span></li></ul></td><td><ul><li>AppsFlyer面板及原始数据报告中显示为常规激活（归因到上一个触达用户的有效渠道）</li><li>购买了Protect360高阶付费套餐的广告主：<ul><li><a href="./protect360-dashboard#激活假量面板" target="_blank">Protect360激活面板</a></li><li>Protect360激活原始数据报告（<span>包含被拦截的媒体渠道）</span> </li></ul></li><li>未购买Protect360高阶付费套餐的广告主：<ul><li>Protect360激活原始数据报告（<span>包含被拦截的媒体渠道）</span> </li></ul></li></ul></td><td><ul><li>归因结果与纠正渠道后的激活相同</li><li>Protect360高阶付费套餐可提供下列数据：<ul><li>AppsFlyer面板和报告中标记为常规应用内事件，并显示已纠正的归因结果</li><li>Protect360的应用内事件面板和已拦截的应用内事件原始数据报告中也会显示这些事件，并同时呈现被拦截的渠道</li></ul></li></ul></td></tr><tr><td>将激活标记为无效，不进行归因</td><td><ul><li><span>适用于根据指定规则的条件被判定为虚假激活的流量</span></li><li><span>相关激活的归因会被彻底阻断（即不会归为非自然量也不会归为自然量）</span></li></ul></td><td><ul><li>购买了Protect360高阶付费套餐的广告主：<ul><li><a href="./protect360-dashboard#激活假量面板" target="_blank">Protect360激活面板</a></li><li>Protect360激活原始数据报告（<span>包含被拦截的媒体渠道）</span> </li></ul></li><li>未购买Protect360高阶付费套餐的广告主：<ul><li>Protect360激活原始数据报告（<span>包含被拦截的媒体渠道）</span> </li></ul></li></ul></td><td><ul><li><span>已拦截</span></li><li><span>已购买Protect360高阶付费套餐的广告主可在Protect360的应用内事件面板和已拦截的应用内事件原始数据报告中查看该数据</span></li></ul></td></tr><tr><td rowspan="2"><strong>应用内事件</strong></td><td>拦截归因 </td><td><ul><li><span>适用于根据指定规则的条件被判定为假量的无效应用内事件</span></li></ul></td><td><ul><li> <span>购买了Protect360高阶付费套餐的广告主：</span><ul><li><a href="./protect360-dashboard#应用内事件控制面板" target="_blank">Protect360的应用内事件面板</a></li><li>Protect360应用内事件原始数据报告</li></ul></li><li>未购买Protect360高阶付费套餐的广告主：不适用</li></ul></td><td><ul><li> <span>已购买Protect360高阶付费套餐的广告主可在Protect360的</span><a href="./protect360-dashboard#应用内事件控制面板" target="_blank"><span>应用内事件面板</span></a><span>和已拦截的应用内事件原始数据报告中查看该数据</span> </li></ul></td></tr><tr><td>从AppsFlyer中彻底删除相关事件</td><td><ul><li><span>如果您对于某些应用内事件完全不需要任何数据，建议使用该选项</span></li><li><span>选择该选项后AppsFlyer完全不会记录这些事件</span></li></ul></td><td><span></span></td><td><span></span></td></tr></tbody></table>

* 广告平台和代理可以查看相关数据，但需要广告主为其开通<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview#protect360-fraud-and-validation-rules">权限</Anchor>。
* 每当有激活被实时拦截或归因纠正到有效渠道时，我们会立即向被拦截的广告平台发送拦截流量回传，以简化您的对账流程。AppsFlyer阻断当前渠道的归因并将流量归到上一个有效渠道时，也会向获得归因的广告平台发送回传。
* 每当有应用内事件被拦截时，我们会立即向被拦截的广告平台发送拦截回传。  
  **请注意**：
  * 我们仅向已与AppsFlyer对接的广告平台发送回传。
  * 您可以通过导出数据页获取这些回传及拦截回传报告。
  * 详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">回传</Anchor>和<Anchor target="_blank" href="/partners/zh/docs/rejected-attribution-postbacks-to-integrated-partners">拦截回传</Anchor>说明。
* 激活和应用内事件的拦截仅会影响相关数据在AppsFlyer中的上报方式及呈现位置，不会影响终端用户对相关应用的使用。
  * 如有需要，您可以使用<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports">被拦截的激活和应用内事件原始数据报告</Anchor>（可通过导出数据页面、Pull API和Data Locker获取）来创建用户黑名单。
* 被拦截的激活/应用内事件报告以及拦截回传的拦截原因一栏中会列出拦截相关激活/事件时所使用的规则。对于多规则场景，请参阅[多规则并行](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules)部分的说明。
  * 如果相关激活/应用内事件被Protect360的防作弊引擎拦截，则即使有适用的验证规则，报告中仍会呈现Protect360的拦截原因。
* 启用验证规则可能会导致AppsFlyer与<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-discrepancies">Meta ads</Anchor>及<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-faq-and-discrepancies">Google Adwords</Anchor>等SRN之间产生数据差异，因为这些平台会使用其自有逻辑来验证激活。

</Accordion>

<div id="multiple-rules" />

<Accordion title="多规则并行">

* 如果某个激活/事件同时满足多个规则的条件，就会出现多条验证规则同时对同一个激活/事件生效的情况。
* 如果某个激活/事件不符合任何一条规则的条件，则会被判定为无效。
* 原始数据报告及拦截回传会在**拦截原因（block reason）字段的值**中列出所有将相关激活或事件判定为无效的规则名称。
* 多规则并行时，各规则的执行顺序按其拦截类型排列，具体如下：

| 规则/拦截类型 | 执行顺序 |
| --- | --- |
| 拦截激活 | 随机 |
| 阻断归因 | 随机 |
| 拦截应用内事件 | 随机 |
| 从AppsFlyer中彻底删除 | 将事件及其所有相关数据从AppsFlyer中删除，并忽略其他规则。 |
| 拦截激活及阻断归因 | <ol><li>激活拦截规则（顺序随机）</li><li>归因阻断规则（顺序随机）</li></ol> |
| 使用Protect360引擎和验证规则拦截激活和阻断归因 | <ol><li>由Protect360引擎拦截激活</li><li>根据验证规则拦截激活</li><li>由Protect360引擎阻断归因</li><li>根据验证规则阻断归因</li></ol> |
| 使用Protect360引擎和验证规则拦截应用内事件 | <ol><li>由Protect360引擎拦截事件</li><li>根据验证规则拦截事件</li></ol> |

</Accordion>

## 规则配置界面

规则配置界面旨在为您提供更具互动性的规则配置体验。**小贴士：** 建议您在细读本文前先探索一下规则配置界面中的各种选项，熟悉其中的内容。

![New Validation Rule page.jpg](https://files.readme.io/23875c647c24226c09f5aa2f4dbb85264f95b09e867a053ee55bc2d3ebbc9895-21855980276753.png)

规则配置界面中包含以下几个板块：

| 板块 | 说明 |
| --- | --- |
| 通用信息 | <ul><li>**规则名称** - 输入新规则的名称。</li><li>**规则类型 -** 选择规则类型，**实时**，或**归因后**。</li><li>**事件** - 选择这条规则所适用的事件类型。可用选项为**激活**或**应用内事件**。</li><li>**应用选择 -** 选择 **选定的应用**，或 **所有应用。**<ul><li>如果选择了**选定的应用**：<br />**选择应用** - 选择这条规则所适用的应用。您可以选择帐户中的单个应用、多个应用或所有应用。</li><li>如果选择了**所有应用**：<br />可勾选**包含未来新增应用**选项 - 允许将未来新增的应用纳入此规则中。</li></ul></li></ul>这里的设置决定了后面几个板块（代理、媒体渠道、广告投放等）中可用的选项<br /><br /><br /><br />**注意**<br />应用版本仅限数字。如 2.2.1<br /><br />请注意：<br /><br />数值型应用版本（例如 2.2.1）支持所有运算符（等于、大于、小于等）。<br /><br />如果应用版本为自定义文本（例如 version123 或 our\_latest\_version），仅可使用“等于”或“不等于”运算符；“大于”或“小于”将不适用。 |
| 流量来源 | 设定这条规则所适用的流量。[另请参阅Protect360流量来源说明部分](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) |
| 条件 | 选择拦截“符合”或“不符合”指定条件的激活/应用内事件。<ul><li>**符合条件** - 对于符合指定条件的所有激活/应用内事件，AppsFlyer会阻断其归因，并执行您在“操作”部分指定的操作。</li><li>**不符合条件** - 对于不符合指定条件的所有激活/应用内事件，AppsFlyer会阻断其归因，并根据您在下个部分中指定的方式进行处理。</li></ul>另请参见适用于[激活](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions)和[应用内事件](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions)的Protect360条件。 |
| 可用操作 | 对于符合指定条件的激活，设置AppsFlyer的处理方式：<ul><li>**将这些激活标记为无效，并不对其进行归因**。这些激活不会出现在Protect360面板及报告以外的AppsFlyer面板中。</li><li>**阻断当前渠道的归因并将结果纠正到上一个有效渠道**。如果未发现有效渠道，则相关激活会被判定为自然量。</li></ul>对于符合指定条件的应用内事件，设置AppsFlyer的处理方式：<ul><li>**阻断归因，但在Protect360数据中呈现该事件**。相关事件不会被归因，但会出现在Protect360的面板和原始数据报告中。</li><li>**从AppsFlyer中删除**。相关事件完全不会出现在AppsFlyer平台中。</li></ul>详情请见[验证结果](/docs/implement-validation-rules-to-prevent-fraud#outcomes)说明部分 。 |

## 验证规则示例

<div id="install-sources" />

<Accordion title="激活来源">

**来源**部分用于设定相关规则所适用的激活流量来源。

有三个主要选项：

* **所有流量**：包括有机和非有机安装。来源信息不可用于自然激活。此选项包括所有媒体来源，包括将来添加的来源。  
  *示例*:对所有应用版本低于X的流量应用规则。
* **所有非有机流量：** 适用于所有代理和非代理的非有机流量来源，包括后续添加的新来源。  
  *示例*:阻止来自特定地理位置的非有机流量，在该位置您不进行UA或重定向活动。
* **选定的非有机流量：** 仅对特定代理或媒体来源应用规则。编辑规则时，您必须手动选择或添加媒体来源。  
  *示例*:如果CTIT超过X天，则阻止来自特定媒体来源的安装。

购买了Protect360的广告主还可以使用额外的[激活](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) 和[应用内事件](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions)流量选项。

<table><thead><tr><th>字段</th><th>Operator</th><th>字段值</th><th>说明</th></tr></thead><tbody><tr><td>Agency（代理）</td><td><ul><li>In（分类）</li></ul></td><td><ul><li>代理和非代理流量</li><li>非代理流量</li><li>透明代理（在下拉菜单中选择）</li></ul></td><td><p><span>透明代理：</span></p><ul><li>这类代理会共享其媒体渠道信息。</li><li>如果相关代理仅针对部分指定应用共享数据，则会显示在不透明代理的列表中。</li><li>所有代理都必须共享他们的媒体来源。&lt;/li&gt;&lt;li&gt;仅为您选择的某些应用共享媒体来源的代理会出现在透明代理菜单中。&lt;/li&gt;&lt;/ul&gt;</li></ul></td></tr><tr><td>Media source（媒体渠道）</td><td><ul><li><span>In list（在列表中）</span></li><li><span>Not in list（不在列表中）</span></li><li><span>Equals（等于）</span></li><li><span>Doesn't equal（不等于）</span></li><li><span>Contains（包含）</span></li><li><span>Doesn't contain（不包含）</span></li><li><span>Starts with（开头是）</span></li><li><span>Ends with（结尾是）</span></li><li> <span>Matches regular expression</span><span></span>（匹配正则表达式） </li></ul></td><td><ul><li><span>搜索所需的值。</span></li><li><span>从菜单中选择所需值。 </span></li><li><span>输入自定义值（用于未出现在搜索结果中的值）。</span></li></ul></td><td rowspan="6"><ul><li> <span>菜单中的选项取决于：</span><ul><li>选定的应用和代理。</li><li>按过去30天内的流量高低排序。</li></ul></li><li><span>输入的自定义文本必须与原始数据中的名称完全一致。</span></li></ul></td></tr><tr><td>Campaign</td><td rowspan="5"><ul><li><span>In list（在列表中）</span></li><li><span>Not in list（不在列表中）</span></li><li><span>Equals（等于）</span></li><li><span>Doesn't equal（不等于）</span></li><li><span>Contains（包含）</span></li><li><span>Doesn't contain（不包含）</span></li><li><span>Starts with（开头是）</span></li><li><span>Ends with（结尾是）</span></li><li><span>Is empty（是空值）</span></li><li><span>Isn't empty（不是空值）</span></li><li><span>Matches regular expression（匹配正则表达式）</span></li></ul></td><td><ul><li>搜索所需的值。</li><li>从菜单中选择所需值。</li><li>输入自定义文本（用于未出现在搜索结果中的值）。</li></ul></td></tr><tr><td>Campaign ID（广告系列ID）</td><td rowspan="4"><ul><li><span>仅支持输入自定义文本。</span></li><li><span>可以添加多个值，以空格分隔。</span></li></ul></td></tr><tr><td>Ad ID（广告ID）</td></tr><tr><td>Ad set ID（广告组ID）</td></tr><tr><td>Ad set name（广告组名称）</td></tr></tbody></table>

</Accordion>

<div id="install-conditions" />

<Accordion title="激活条件">

您可以在**条件**部分中设置判定条件，以便针对符合条件的激活阻断归因或将其归因到上一个有效渠道。

每一条规则下都可以添加多个条件和条件组合。

下表列出了设置条件时可用的维度、运算符和值。

#### 批量上传

在条件支持的情况下，选择**In list**或**not in list**运算符时，可通过上传CSV文件批量添加新项。

具体方法如下：

1. 选择包含**in list**或**not in list**运算符的条件。
2. 从运算符下拉列表中选择**In list**或 **not in list**。
3. 在**添加新项**框中，选择**上传CSV文件**选项。

请注意：CSV文件最多可包含17,000个值。

购买了Protect360的广告主还可以使用额外的[激活](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions)和[应用内事件](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions)条件选项。

<table><thead><tr><th><span>条件</span></th><th><span>Operator</span></th><th><span>字段值</span></th><th><span>说明</span></th></tr></thead><tbody><tr><td><span>Campaign（广告系列）</span></td><td rowspan="6"><ul><li><span>Equals（等于）</span></li><li><span>Doesn't equal（不等于）</span></li><li><span>Doesn't contain（不包含）</span></li><li><span>Contains（包含）</span></li><li><span>Starts with（开头是）</span></li><li><span>Ends with（结尾是）</span></li><li><span>In list（在列表中）</span></li><li><span>Not in list（不在列表中）</span></li><li><span>Matches regular expression（匹配正则表达式）</span></li><li><span>Is empty（是空值）</span></li><li><span>Isn't empty（不是空值）</span></li></ul></td><td><ul><li>搜索所需的值。</li><li>从菜单中选择所需值。</li><li>输入自定义文本（用于未出现在搜索结果中的值）。</li></ul></td><td rowspan="11"><ul><li> <span>菜单中的选项取决于：</span><ul><li>选定的应用和代理。</li><li>按过去30天内的频次排序。</li></ul></li><li><span>输入的自定义文本必须与原始数据中的名称完全一致。</span></li></ul></td></tr><tr><td><span>Campaign ID（广告系列ID）</span></td><td rowspan="5"><ul><li><span>仅支持输入自定义文本。</span></li><li><span>可以添加多个值，以空格分隔。</span></li></ul></td></tr><tr><td><span>Ad ID（广告ID）</span></td></tr><tr><td><span>Ad set ID（广告组ID）</span></td></tr><tr><td><span>Ad set name（广告组名称）</span></td></tr><tr><td><span>Device type（设备类型）</span></td></tr><tr><td><span>Geo（国家/地区）</span></td><td rowspan="3"><ul><li><span>In list（在列表中）</span></li><li><span>Not in list（不在列表中）</span></li><li><span>Equals（等于）</span></li><li><span>Doesn't equal（不等于）</span></li></ul></td><td><ul><li><span>搜索所需值（按国家名称、国家代码、州或城市搜索）。</span></li><li><span>从菜单中选择所需值。</span></li></ul></td></tr><tr><td><span>Platform（系统平台）</span></td><td><span>从菜单中选择所需值。</span></td></tr><tr><td><span>货币</span></td><td><p>仅限货币。可用值包括：</p><p>USD, NZD, SGD, IMP, ANG, MNT, BIF, BBD, HUF, ERN, AZN, AOA, PYG, MYR, GYD, VUV, SLL', FKP, DJF, GNF, LVL, MMK, MRO, RSD, CLF, XDR, ZAR, TND, PHP, KGS, XPD, RON, RUB, KMF, SCR, GIP, TRY, JEP, UYU, XCD, FJD, GHS, MVR, AWG, UGX, TOP, CVE, MKD, COP, CUC, GTQ, KZT, MXN, MGA, AUD, BDT, ISK, KRW, DZD, GGP, OMR, ZMW, MOP, CUP, JPY, SHP, LSL, ETB, BWP, MAD, AED, NGN, BRL, GEL, IDR, EUR, GBP, WST, XAF, SZL, XOF, SEK, UZS, KES, KYD, ILS, KWD, NPR, BZD, QAR, UAH, BTN, HTG, DKK, VND, SBD, JMD, IQD, LBP, XPT, HRK, HKD, JOD, PAB, CDF, VEF, XAU, BAM, CNY, SOS, XPF, GMD, DOP, XAG, KPW, BOB, BHD, BYN, BYR, LRD, BGN, AMD, CZK, CAD, LAK, EEK, MTL, PLN, LKR, BTC, MWK, LTL, ZMK, PGK, YER, PEN, KHR, RWF, BSD, AFN, ZWL, LYD, TMT, HNL, TWD, IRR, MUR, THB, ALL, TJS, SDG, BMD, CRC, NOK, SRD, MZN, CLP, STD, SYP, TZS, EGP, ARS, MDL, INR, SAR, PKR, TTD, NIO, BND, NAD, SVC, CHF</p></td></tr><tr><td><span>收入</span></td><td><ul><li><span>Lower than（低于）</span></li><li><span>Lower than or equals（低于或等于）</span></li><li><span>Greater than（高于）</span></li><li><span>Greater than or equals（高于或等于）</span></li><li><span>Is between（在指定范围区间内）</span></li><li><span>Equals（等于）</span></li><li><span>Doesn't equal（不等于）</span></li></ul></td><td><ul><li><span>仅支持输入自定义文本。</span></li></ul></td></tr><tr><td><span>OS version</span></td><td><ul><li><span>Lower than（低于）</span></li><li><span>Lower than or equals（低于或等于）</span></li><li><span>Greater than（高于）</span></li><li><span>Greater than or equals（高于或等于）</span></li><li><span>Equals（等于）</span></li><li><span>Doesn't equal（不等于）</span></li><li><span>Is between（在指定范围区间内）</span></li><li><span>In list（在列表中）</span></li><li><span>Not in list（不在列表中）</span></li></ul></td><td><ul><li><span>搜索所需的值。</span></li><li><span>从菜单中选择所需值。 </span></li><li><span>输入自定义文本（用于未出现在搜索结果中的值）。</span></li></ul></td></tr><tr><td><span>Lookback days（回溯天数）</span></td><td><ul><li><span>Lower than（低于）</span></li><li><span>Greater than or equals（高于或等于）</span></li><li><span>Is between（在指定范围区间内）</span></li></ul></td><td><ul><li><span>自定义文本：单个数值。</span></li></ul></td><td><ul><li><span>指展示/点击的回溯窗口期（以天为单位）。</span></li><li><span>适用于某些平台为了延长归因窗口期而篡改归因链接的情况，可避免为窗口期外的激活付费。</span></li><li><span>不会影响您在归因链接中配置的窗口期。</span></li><li> <span>【推荐方式】建议结合使用回溯天数和归因触点类型这两个条件（</span><a href="./implement-validation-rules-to-prevent-fraud#protect360-install-conditions"><span>购买Protect360后可用</span></a><span>）</span> </li></ul></td></tr><tr><td><span>Is preinstalled（是否为预装）</span></td><td rowspan="2"><ul><li><span>Yes（是）</span></li><li><span>No（否）</span></li></ul></td><td rowspan="2"><ul><li>无值（运算符即为值）</li></ul></td><td><ul><li> <span>验证所有类型的预装：</span><ul><li><span>出厂预装，即相关应用作为操作系统的一部份安装在设备中。</span></li><li><span>可选预装（Offered preinstalls），即设备激活时立即向用户推广相关应用，引导用户安装。这类预装推广由专门的预装渠道执行。</span></li></ul></li><li>适用于带有多个点击/渠道的激活，该条件可验证其中是否包含预装渠道。</li></ul></td></tr><tr><td><span>Is deeplink（是否为深度链接）</span></td><td><span>若某激活原始数据中的深度链接字段为空，该激活会被判定为Is deeplink = No</span></td></tr></tbody></table>

</Accordion>

<div id="inapp-event-sources" />

<Accordion title="应用内事件来源">

如果您购买了Protect360，并在**事件**部分中选择了**应用内事件**，则在界定规则所适用的应用内事件时，除了[常规的流量来源选项](/docs/implement-validation-rules-to-prevent-fraud#install-sources)之外，还有一个额外的专属选项可用。

您可以使用下表所列的字段、运算符和值来界定流量来源。

**请注意**：相关应用内事件的所有其他来源字段都与其初始激活一致（如代理、媒体渠道、广告系列、广告系列ID、子渠道ID等）。

| 字段 | Operator | 字段值 | 说明 |
| --- | --- | --- | --- |
| 事件名称 | <ul><li>In list（在列表中）</li><li>Not in list（不在列表中）</li><li>Equals（等于）</li><li>Doesn’t equal（不等于）</li><li>Contains（包含）</li><li>Doesn’t contain（不包含）</li><li>Starts with（开头是）</li><li>Ends with（结尾是）</li><li>Is empty（是空值）</li><li>Isn’t empty（不是空值）</li><li>Matches regular expression（匹配正则表达式）</li></ul> | <ul><li>搜索所需的值。</li><li>从菜单中选择所需值。</li><li>输入自定义文本（用于未出现在搜索结果中的值）。</li></ul> | <ul><li>输入的自定义文本必须与原始数据中的名称完全一致。</li></ul> |

</Accordion>

<div id="inapp-event-conditions" />

<Accordion title="应用内事件条件">

如果您购买了Protect360，并在**事件**部分中选择了**应用内事件**，则在界定规则所适用的应用内事件时，还可以使用额外的专属选项。这些条件可以与[前文所列](/docs/implement-validation-rules-to-prevent-fraud#install-conditions)的非Protect360专属条件搭配使用。

您可以使用下表所列的条件、运算符和值来界定Protect专属条件。

| 条件 | Operator | 字段值 | 说明 |
| --- | --- | --- | --- |
| 事件名称 | <ul><li>In list（在列表中）</li><li>Not in list（不在列表中）</li><li>Equals（等于）</li><li>Doesn’t equal（不等于）</li><li>Contains（包含）</li><li>Doesn’t contain（不包含）</li><li>Starts with（开头是）</li><li>Ends with（结尾是）</li><li>Is empty（是空值）</li><li>Isn’t empty（不是空值）</li><li>Matches regular expression（匹配正则表达式）</li></ul> | <ul><li>搜索所需的值。</li><li>从菜单中选择所需值。</li><li>输入自定义文本（用于未出现在搜索结果中的值）。</li></ul> | <ul><li>输入的自定义文本必须与原始数据中的名称完全一致。</li></ul> |

> 📘 **注意**
>
> 事件名称条件不区分大小写。所有事件名称在评估之前会自动转换为小写。例如，如果您输入 **提交表单**，系统将其视为 **提交表单**。

</Accordion>

<div id="protect360-install-and-inapp-event-sources" />

<Accordion title="Protect360专属的激活和应用内事件来源选项">

如果您购买了Protect360，则在界定相关规则所适用的流量来源时，除了[常规流量来源选项](/docs/implement-validation-rules-to-prevent-fraud#install-sources)外，还会有额外的专属选项可用。您可以使用下表所列的字段、运算符和值来界定流量来源。

| 字段 | Operator | 字段值 | 说明 |
| --- | --- | --- | --- |
| Site ID | <ul><li>In list（在列表中）</li><li>Not in list（不在列表中）</li><li>Equals（等于）</li><li>Doesn’t equal（不等于）</li><li>Contains（包含）</li><li>Doesn’t contain（不包含）</li><li>Starts with（开头是）</li><li>Ends with（结尾是）</li><li>Is empty（是空值）</li><li>Isn’t empty（不是空值）</li><li>Matches regular expression（匹配正则表达式）</li></ul> | <ul><li>仅支持输入自定义文本。</li><li>可以添加多个值，以空格分隔。</li></ul> | <ul><li>输入的自定义文本必须与原始数据中的名称完全一致。</li></ul> |

</Accordion>

<div id="protect360-install-conditions" />

<Accordion title="Protect360专属的激活验证条件">

购买了Protect360d的广告主可使用一系列专属条件来验证其激活。这些条件可以与[前文所列](/docs/implement-validation-rules-to-prevent-fraud#install-conditions)的非Protect360专属条件搭配使用。

您可以使用下表所列的条件、运算符和值来界定Protect专属条件。

<table><thead><tr><th><span>条件</span></th><th><span>Operator</span></th><th><span>字段值</span></th><th><span>说明</span></th></tr></thead><tbody><tr><td><span>CTIT（点击到激活时间）</span></td><td><ul><li><span>Lower than（低于）</span></li><li><span>Greater than or equals（高于或等于）</span></li><li><span>Is between（在指定范围区间内）</span></li></ul></td><td><ul><li><span>自定义文本：单个数值。</span></li></ul></td><td><ul><li> <span>请在您确定某个具体CTIT有问题时（通常仅在特定的国家/地区出现）才使用这个字段，否则可能会误伤正常的激活。</span><br/><span><strong>请注意</strong>：Protect360防作弊引擎具有精密的内置识别机制，可检测到复杂的CTIT异常，无论其成因是归因劫持、点击撞库、bots伪造的虚假激活还是其他作弊行为。</span> </li><li> <span>建议您将此字段与以下字段搭配使用：</span><ul><li>Is pre-installed（是否为预装）</li><li>Is deeplink（是否为深度链接）</li><li>Geo（国家/地区）</li></ul></li></ul><div><div><div><div><div><div><div><div>请注意：CTIT安装条件不支持阻止归因于参与点击类型的安装，仅支持'常规'点击。</div></div></div></div></div></div></div></div><div><div><div> </div></div></div></td></tr><tr><td><span>Customer user ID（客户用户ID，即CUID）</span></td><td><ul><li><span>Equals（等于）</span></li><li><span>Doesn't equal（不等于）</span></li><li><span>Doesn't contain（不包含）</span></li><li><span>Contains（包含）</span></li><li><span>Starts with（开头是）</span></li><li><span>Ends with（结尾是）</span></li><li><span>In list（在列表中）</span></li><li><span>Not in list（不在列表中）</span></li><li><span>Matches regular expression（匹配正则表达式）</span></li><li><span>Is empty（是空值）</span></li><li><span>Isn't empty（不是空值）</span></li></ul></td><td><ul><li><span>仅支持输入自定义文本。</span></li><li><span>可以添加多个值，以空格分隔。</span></li></ul></td><td><ul><li> <span>菜单中的选项</span>按过去30天内的流量频次排序。</li><li><span>输入的自定义文本必须与原始数据中的名称完全一致。</span></li></ul></td></tr><tr><td><span>App version（应用版本）</span></td><td><ul><li><span>Lower than（低于）</span></li><li><span>Lower than or equals（低于或等于）</span></li><li><span>Greater than（高于）</span></li><li><span>Greater than or equals（高于或等于）</span></li><li><span>Equals（等于）</span></li><li><span>Doesn't equal（不等于）</span></li><li><span>Is Between（在指定范围区间内）</span></li><li><span>In list（在列表中）</span></li><li><span>Not in list（不在列表中）</span></li><li><span>Not in last（不在最后n个版本中）</span></li><li><span>Not in last (major)（不在主版本的最后n个次版本中）</span></li></ul></td><td><ul><li>搜索所需的值。</li><li>从菜单中选择所需值。</li><li>输入自定义文本（用于未出现在搜索结果中的值）。</li></ul></td><td><ul><li> <span>菜单中的选项</span>按过去30天内的流量频次排序。</li><li><span>输入的自定义文本必须与原始数据中的名称完全一致。</span></li><li> <span>使用“Not in last”运算符时，如果您的应用有多个主版本号，请选择“Not in last (major)”。</span><a href="./implement-validation-rules-to-prevent-fraud#how-do-the-not-in-last-conditions-work"><span>了解详情</span></a> </li></ul></td></tr><tr><td><span>SDK version</span></td><td><ul><li><span>Lower than（低于）</span></li><li><span>Lower than or equals（低于或等于）</span></li><li><span>Greater than（高于）</span></li><li><span>Greater than or equals（高于或等于）</span></li><li><span>Equals（等于）</span></li><li><span>Doesn't equal（不等于）</span></li><li><span>Is Between（在指定范围区间内）</span></li><li><span>In list（在列表中）</span></li><li><span>Not in list（不在列表中）</span></li></ul></td><td><ul><li>搜索所需的值。</li><li>从菜单中选择所需值。</li><li>输入自定义文本（用于未出现在搜索结果中的值）。</li></ul></td><td><ul><li> <span>菜单中的选项</span>按过去30天内的流量频次排序。</li><li><span>输入的自定义文本必须与原始数据中的名称完全一致。</span></li></ul></td></tr><tr><td><span>Installer/Store（安装程序/商店）</span></td><td rowspan="3"><ul><li>In list（在列表中）</li><li>Not in list（不在列表中）</li><li>Equals（等于）</li><li>Doesn’t equal（不等于）</li></ul></td><td><p><span>从菜单中选择所需值：</span></p><ul><li>Google Play</li><li>第三方商店</li><li>非商店下载</li></ul></td><td><ul><li>Google play：AppsFlyer识别出相关安装包为<code>com.android.vending</code>。</li><li>第三方商店：AppsFlyer识别出相关激活来自第三方安卓商店。</li><li>非商店下载：AppsFlyer发现一个未在任何安卓商店中上架的APK。</li></ul><p><span>如果某个用户的设备不向AppsFlyer提供安装程序/商店参数，这条规则不会对此用户生效。</span></p></td></tr><tr><td>自定义安装程序/商店</td><td>输入自定义文本（用于未出现在搜索结果中的值）。</td><td><ul><li>如果客户选择了“other”条件，并且选择了自定义条件installer=X，则仅适用于安装程序 X。</li><li>如果客户选择了“other”条件，或选择了自定义条件 installer=X，则将适用于所有“other”安装程序/商店，而X是该组的一部分。</li></ul></td></tr><tr><td><span>Attribution touch type（广告触达类型）</span></td><td><ul><li><span>Click（点击）</span></li><li><span>Impression（展示）</span></li></ul></td><td><ul><li>【推荐方式】搭配使用回溯天数条件</li><li>如果您只是不想要对展示进行归因，可以直接<a href="./measure-view-through-engagements#turn-off-viewthroughattribution" target="_blank">关闭浏览型归因</a>。</li></ul></td></tr><tr><td><span>Carrier</span></td><td><ul><li>In list（在列表中）</li><li>Not in list（不在列表中）</li><li>Equals（等于）</li><li>Doesn't equal（不等于）</li></ul></td><td><ul><li><span>仅限自定义文本</span></li></ul></td><td> </td></tr><tr><td><span>User agent</span></td><td><ul><li>Contains（包含）</li><li>Doesn't contain（不包含）</li></ul></td><td><ul><li><span>仅限自定义文本</span></li></ul></td><td> </td></tr><tr><td><span>IP address（IP地址）</span></td><td><ul><li>In list（在列表中）</li><li>Not in list（不在列表中）</li><li>Equals（等于）</li><li>Doesn't equal（不等于）</li></ul></td><td><ul><li><span>仅限自定义文本</span></li></ul></td><td> </td></tr></tbody></table>

</Accordion>

<div id="protect360-inapp-event-conditions" />

<Accordion title="Protect360专属的应用内事件验证条件">

如果购买了Protect360的广告主在**事件**部分中选择了**应用内事件**，则在界定规则所适用的应用内事件时，还可以使用额外的选项。这些条件可以与[前文所列](/docs/implement-validation-rules-to-prevent-fraud#install-conditions)的非Protect360专属条件搭配使用。

您可以使用下表所列的条件、运算符和值来界定Protect专属条件。

| 条件 | Operator | 字段值 | 说明 |
| --- | --- | --- | --- |
| Event source | <ul><li>In list（在列表中）</li><li>Not in list（不在列表中）</li><li>Equals（等于）</li><li>Doesn’t equal（不等于）</li></ul> | <ul><li>搜索所需的值。</li><li>从菜单中选择所需值。</li></ul> | 选择SDK或服务器到服务器 |
| Event value | <ul><li>In list（在列表中）</li><li>Not in list（不在列表中）</li><li>Equals（等于）</li><li>Doesn’t equal（不等于）</li><li>Contains（包含）</li><li>Doesn’t contain（不包含）</li><li>Starts with（开头是）</li><li>Ends with（结尾是）</li><li>Is empty（是空值）</li><li>Isn’t empty（不是空值）</li><li>Matches regular expression（匹配正则表达式）</li></ul> | <ul><li>仅支持输入自定义文本。</li><li>可以添加多个值，以空格分隔。</li></ul> | <ul><li>选择符合您需求的值。</li></ul> |
| Install to event time（激活到事件时间，以秒为单位） | <ul><li>Lower than（低于）</li><li>Greater than or equals（高于或等于）</li><li>Is between（在指定范围区间内）</li></ul> | 输入自定义文本，仅支持单个数值。 | <ul><li>根据相关应用的用户链路，确定从用户激活应用到完成应用内事件之间所需的有效时长。<ul><li>比如从激活到进入第5关、完成首次存款，支付订单等等的时长。</li></ul></li><li>这里的时长以秒为单位，您可以设置数分钟、数小时或数天的时长条件，但需要换算成秒。</li></ul> |

</Accordion>

<div id="logic-between-conditions-and-condition-groups" />

<Accordion title="条件和条件组之间的逻辑">

如果您在一条规则下添加了多个条件或条件组，需要选择这些条件或条件组之间的逻辑关系，可用选项为：

* **And**（并且）：即相关激活需符合您设定的所有条件。
* **Or**（或者）：即相关激活至少需符合您设定的条件之一。

举例来说，如果您想要同时根据系统平台和系统版本来验证激活，这时必须选择** and **，让AppsFlyer只验证使用指定版本的指定系统的用户。如果您想要根据系统平台或系统版本两者之一来验证激活，则必须选择** or **。

</Accordion>

## 其他功能

<div id="view-rule-list" />

<Accordion title="查看规则列表">

**如需查看相关账户下的所有规则，请按以下方式操作**：

1. 从AppsFlyer后台进入**配置** > **验证规则**。  
   界面会打开验证规则窗口，其中呈现验证规则列表。
2. 使用**列表视图/详情视图**切换按钮，根据您的偏好选择表格视图。
3. 使用搜索和筛选选项对列表中的规则进行筛选。
   * 您可以按规则名称、流量来源、条件名称和字段值进行搜索。
   * 比如可以输入数字**7**来搜索将操作系统版本条件设置为版本号带有7的所有规则（如“2.7.4”、“7.1”等等），或者输入**Canada**搜索将加拿大设置为国家/地理条件的规则。

</Accordion>

<div id="add-rule" />

<Accordion title="添加规则">

**新规则的添加方式如下：**

1. 从AppsFlyer后台进入**配置** > **验证规则**。  
   界面会打开验证规则窗口。
2. 点击**添加规则。**  
   界面会打开“添加新规则”窗口。
3. 输入**规则名称**。 请使用符合以下要求且带有唯一性的名称：
   * 可准确描述该规则。
   * 对广告平台没有冒犯性。该名称会出现在被拦截的激活报告以及拦截回传中，发送给广告平台。
4. 完成[规则配置部分](/docs/implement-validation-rules-to-prevent-fraud#规则配置界面)的设置。
5. 【可选】根据实际需求添加条件和/或条件组。请确保各条件/条件组之间的逻辑关系[设置正确](/docs/implement-validation-rules-to-prevent-fraud#logic-between-conditions-and-condition-groups)。
6. 点击【可选】**预估流量变化**，查看[这条规则会对流量产生什么样的影响](/docs/implement-validation-rules-to-prevent-fraud#view-validation-rule-impact)。
7. 点击**保存**。

> 📘 **注意**
>
> 应用版本仅限数字。如 2.2.1
>
> 请注意：
>
> 数值型应用版本（例如 2.2.1）支持所有运算符（等于、大于、小于等）。
>
> 如果应用版本为自定义文本（例如 version123 或 our\_latest\_version），仅可使用“等于”或“不等于”运算符；“大于”或“小于”将不适用。

<div id="view-validation-rule-impact" />

<Accordion title="VR标记模式">

使用标记模式在阻止归因之前测试实时流量的验证规则。标记规则标记符合规则条件的安装和应用内事件，但不影响归因。

标记模式仅支持安装和应用内事件。

使用标记模式来：

* 在阻止归因之前测试实时流量中的复杂规则。
* 识别可能的误报。
* 在执行规则之前，审查规则触发的原因。
* 在将规则状态更改为已实施之前，了解真实流量的影响。

推荐方法：首先在标记模式中创建规则，审查数据存储中的标记流量，并在对规则的准确性有信心时将规则状态更改为已实施。力争在7天内完成此审查，以保持主动保护。

#### 标记模式的工作原理

当您创建或编辑验证规则时，在规则结果部分选择检测状态。

* 已标记该规则标记匹配的数据以进行报告和分析。归因不受影响。
* 或实施假量处理该规则根据所选的规则结果主动阻止归因。

请注意：标记模式仅适用于规则保存后的实时流量。它不会标记历史数据。

#### 规则结果配置

规则结果部分，之前称为操作，定义了AppsFlyer如何处理符合规则条件的流量。它还提供了规则配置的高级摘要，以便您在保存规则之前验证预期的影响。

| 检测状态 | 归因的影响 | 数据可用性 |
| --- | --- | --- |
| 已标记 | 无影响流量正常归因。 | 在数据锁定报告中可见。原始数据报告的可用性计划在第二季度。 |
| 或实施假量处理 | 主动阻止。根据所选规则结果，归因被阻止。 | 在Protect360仪表板和导出报告中可见。 |

#### 配置规则时的预期情况

在您配置规则时，动态信息面板显示基于以下内容的预期规则行为：

* 匹配或不匹配逻辑
* 应用选择
* 检测状态

当检测状态设置为标记时，规则充当发现工具。AppsFlyer显示通知，确认匹配的数据在导出报告中被标记，包括数据锁定，但不被阻止归因。

当检测状态设置为已实施时，符合规则标准的安装或应用内事件将被阻止归因或根据所选规则结果重新归因。信息面板在您保存规则之前总结了活动结果。

#### 示例：匹配逻辑

对于符合所选应用规则条件的检测到的安装，信息面板可以指示这些安装为：

* 被阻止归因或被检测为后归因。
* 重新归因于最后一个有效的非自然或自然来源。
* 在导出报告中可见。

#### 示例：不要匹配逻辑

对于未满足所选应用程序规则条件的检测到的安装，包括未来的应用程序，信息面板可以指示这些安装为：

* 被阻止归因或被检测为后归因。
* 标记为欺诈且未进行归因修正。
* 在导出报告中可见。

所有其他满足这些应用程序规则条件的安装不会被阻止。

#### 将规则设置为标记模式

要测试标记模式下的验证规则：

1. 从AppsFlyer后台进入配置 > 验证规则。
2. 选择一个现有规则或点击添加规则。
3. 填写规则详细信息、流量来源和条件。
4. 在规则结果部分，将检测状态设置为标记。
5. 点击保存。

规则保存后，AppsFlyer会标记匹配的实时流量以便报告和分析。归因照常进行。

#### 分析标记数据

标记的验证规则数据在Protect360仪表板或欺诈保护套件中不可见。

要分析标记规则的影响，请使用数据锁定器导出标记数据。标记数据会在安装和应用内事件报告中填充，因此您可以将标记流量与有效归因进行比较。

数据锁定器中的数据映射：

| 标记数据 | 数据锁定器报告 |
| --- | --- |
| 已标记的激活 | 卸载报告 |
| 已标记的应用内事件 | 应用内事件报告 |

在数据锁定器导出中使用以下列以识别被验证规则标记的流量：

| 列 | 说明 |
| --- | --- |
| tagged\_reason | 识别触发类型。例如，安装的验证归因为 validation\_attributions，应用内事件的验证归因为 validation\_inapps。 |
| tagged\_sub\_reason | 表示流量是通过验证规则标记的。 |
| detected\_rule\_name | 标记记录的验证规则名称。 |
| detected\_rule\_id | 标记记录的验证规则的唯一 ID。 |

#### 将标记的规则更改为已实施。

在您审核标记的数据并确认规则按预期工作后，将规则状态更改为已实施。

要将规则从标记更改为已实施：

1. 从AppsFlyer后台进入配置 > 验证规则。
2. 选择该规则。
3. 在规则结果部分，将检测状态设置为已实施。
4. 点击保存。

从规则保存的那一刻起，AppsFlyer 会根据所选规则结果主动阻止匹配的流量。

</Accordion>

<div id="edit-or-delete-a-rule" />

<Accordion title="验证规则的编辑或删除">

**如需编辑、删除、启用或禁用某条规则，请按以下方式操作**：

* 在[规则列表](/docs/implement-validation-rules-to-prevent-fraud)中找到相关规则。
  * 使用**活跃**（Active）按钮启用或禁用该规则。
  * 点击规则名称进入**操作**页面。点击垃圾桶图标删除该规则，或更改该页面中的内容对该规则进行编辑。

</Accordion>

</Accordion>

## 常见问题解答

<div id="what-is-a-regular-expression" />

<Accordion title="什么是“正则表达式”（regular expression）？">

正则表达式由字符组成，用于查找匹配项。如果您需要查找某个字符串的直接匹配项，可使用该字符串组成简单的正则表达式。如需查找更为复杂的匹配项，可在表达式中加入特殊字符。

**示例**：

| **正则表达式** | **说明** |
| --- | --- |
| ^abc | 以abc开头 |
| xyz$ | 以xyz结尾 |
| ^abc.*(?&lt;xyz)$ | 以abc开头且以xyz结尾 |
| ^abc.*(?&lt;xyz)$ | 以abc开头且不以xyz结尾 |
| ^([0-9]`{2}`) | 以2位数字开头 |
| \"example\_param\":\"[5\|6] | 指定参数的值以5或6开头。 |
| ^.\{0\}$\|^\{\}$ | 值为空或\{\} |

</Accordion>

<div id="why-doesnt-the-source-or-condition-display-as-a-suggested-value-when-i-search-for-it" />

<Accordion title="搜索流量来源或条件时没有出现相关词条，为什么？">

可能导致该情况的原因有以下两种：

* 应用的选择有误。请确保您要搜索的值适用于选定应用，否则搜索结果中不会出现这些值。
* 搜索结果仅显示过去30天内的流量中出现过的值。此外，相关转化发生后，其流量来源或的条件选项最多需要1天时间才会出现在菜单中。

如果您需要的值未出现在搜索结果中，可以将其作为自定义文本输入相应字段中，然后按下回车键。

</Accordion>

<div id="why-do-my-media-source-options-only-include-facebook-ads-and-twitter" />

<Accordion title="为什么媒体渠道菜单中只有Meta ads和X Ads两个选项？">

媒体渠道字段的选项取决于您选定的代理。

</Accordion>

<div id="is-it-necessary-to-have-andor-both-within-specific-conditions-and-between-condition-groups" />

<Accordion title="具体条件和条件组之间是否必须同时使用“and”和“or”的逻辑关系？">

不是一定要同时使用这两个逻辑关系，具体取决于您的实际需求。某些情况下任一选项都可产生所需的结果，有时则必须两者一并使用。

举例来说，假设您在美国仅验证V10或以上版本的操作系统产生的激活，但在巴西验证V7或以上版本，这时需要设置以下规则：

`{[Geo = US] and [OS version = 10]} OR {[Geo = Brazil] and [OS version = 7]}`

</Accordion>

<div id="do-validation-rules-block-clicks" />

<Accordion title="验证规则会拦截点击吗？">

不会。验证规则可以拦截激活、阻断某个激活流量来源的归因（即不让产生点击/展示的媒体渠道获得归因）或拦截应用内事件，但这些验证方式中都不包含实际点击的拦截，且执行验证规则不会影响点击KPI。

</Accordion>

<div id="looking-at-the-raw-data-i-see-that-installs-i-expected-to-be-blocked-by-validation-rules-have-a-different-block-reason-than-my-rule-name-why-is-that" />

<Accordion title="在原始数据中，本应被某个验证规则拦截的激活下显示的拦截原因不是该规则的名称，为什么？">

出现这种情况说明相关激活是被<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports#拦截原因blocked-reason">Protect360引擎</Anchor>拦截的，而非验证规则。详情请见[多规则并行](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules)说明部分。

</Accordion>

<div id="do-existing-rules-automatically-apply-for-newlyintegrated-agency-traffic" />

<Accordion title="现有规则是否会自动对新对接的代理流量生效？">

这取决于您在**流量来源**部分的设置，详见下表。

如果相关规则未自动生效，请按以下方式编辑该规则：

* 将代理字段更改为**代理和非代理流量**或选择具体代理。

<table><thead><tr><th>流量来源设置</th><th>代理字段的选项</th><th>如果该规则创建时您的应用尚未与任何代理对接，则对接新代理后该规则是否自动生效？</th><th>如果该规则创建时您的应用已至少与一个代理对接，则对接新代理后该规则是否生效？</th></tr></thead><tbody><tr><td> <span>所有流量</span>：</td><td><span>不适用</span></td><td><span>是</span></td><td><span>是</span></td></tr><tr><td rowspan="3"> <br/><span>仅非自然量</span> </td><td><span>不适用</span></td><td><span>否</span></td><td><span>不适用</span></td></tr><tr><td><span>代理和非代理流量</span></td><td><span>不适用</span></td><td><span>是</span></td></tr><tr><td><p><span>非代理流量和/或</span></p><p><span>特定代理</span></p></td><td><span>不适用</span></td><td><span>否</span></td></tr></tbody></table>

</Accordion>

<div id="how-do-the-not-in-last-conditions-work" />

<Accordion title="如何使用“not in last”条件？">

使用 **最近未安装** 允许从您的 **最新应用版本** 安装，并阻止从 **旧版本** 安装。

* **最近未安装** ***X*** **版本**：允许从所选应用的 **最后 X 版本** 安装，并 **阻止** 从 **所有早期版本** 安装。
* **最近未安装 (主要)** ***X*** **版本**：当您的版本控制包括 **多个主要版本系列** 时使用（例如，1.x 和 2.x）。此条件允许 **每个主要系列中的最后 X 版本**，并阻止每个系列中的早期版本。

##### 示例：Not in last（不在最后n个版本中）

您有这些现有的应用版本：

* 1.0.01
* 1.0.02
* 1.0.03
* 2.0.01
* 2.0.02
* 2.0.03

若将验证规则设定为“Not in last 2 versions”（不在最后2个版本中），则该规则会拦截：

* **允许**：
  * 2.0.02
  * 2.0.03
* **阻止**：
  * 1.0.01
  * 1.0.02
  * 1.0.03
  * 2.0.01

##### 示例：Not in last (major)（不在主版本的最后n个次版本中）

使用上面的相同版本列表，定义的规则为 **最近未安装 (主要) 2 版本**：

* **允许**：
  * 1.0.02
  * 1.0.03
  * 2.0.02
  * 2.0.03
* **阻止**：
  * 1.0.01
  * 2.0.01

##### **了解条件如何与多个应用一起工作**

如果您在规则中选择 **多个应用**，AppsFlyer 将 **最近未安装** 条件 **分别针对每个应用** 进行评估。

例如，如果您设置 **最近未安装 3 版本** 并选择应用 A、应用 B 和应用 C：

* 应用 A 根据 **应用 A 的** 版本历史记录允许其 **最后 3 版本**。
* 应用 B 根据 **应用 B 的** 版本历史记录允许其 **最后 3 版本**。

应用 C 根据 **应用 C 的** 版本历史记录允许其 **最后 3 版本**。

</Accordion>

<div id="how-do-i-block-attribution-for-installs-or-inapp-events-from-impressions" />

<Accordion title="我如何阻止将安装或应用内事件的归因与展示相关联？">

当您想要防止基于展示的互动归因，并仅将归因保留给有效点击时，请使用验证规则。如果未找到有效的点击媒体来源，则该安装将被归因为自然流量。此设置可以帮助解决与安装劫持相关的归因场景。

要配置规则：

* 在 **流量来源** 下，选择 **所有非自然流量。**
* 在 **条件** 下，选择 **归因接触类型**。

  * 将操作符设置为 **在列表中**。
  * 选择 **展示**。
* 在 **操作** 下，选择 **阻止归因并更正为最后有效的媒体来源**。

对于此用例，请不要选择 **将安装标记为无效并且不归因**。该操作是针对您认为无效或虚假的安装。如果安装是真实的，但您不想将其归因于基于展示的互动，请改用 **阻止归因并更正为最后有效的媒体来源**。

</Accordion>

<div id="does-tagged-mode-support-all-condition-types" />

<Accordion title="标记模式支持所有条件类型吗？">

支持。标记模式支持所有验证规则运算符和字段，包括与/或逻辑、地理位置、操作系统版本、SDK 版本和事件值。

</Accordion>

<div id="will-tagged-data-appear-in-blocked-reports" />

<Accordion title="标记的数据会出现在被阻止的报告中吗？">

不会。标记的数据不被归类为被阻止的流量。标记的流量被标记为已标记，并被视为有效流量的子集。它在数据锁定器的有效报告中可见。

</Accordion>

<div id="where-can-i-view-tagged-data" />

<Accordion title="我在哪里可以查看标记的数据？">

使用数据锁定器查看标记的验证规则数据。标记的安装在安装报告中可用，标记的应用内事件在应用内事件报告中可用。

标记的数据在 Protect360 仪表板或欺诈保护套件中不可见。

</Accordion>

<div id="can-i-change-a-rule-from-tagged-to-implemented-at-any-time" />

<Accordion title="我可以随时将规则从标记更改为已实施吗？">

支持。在您审核导出数据并确认规则按预期工作后，请编辑规则，将检测状态设置为已实施，然后保存规则。从那时起，规则会根据所选规则结果主动阻止匹配的流量。

</Accordion>

<div id="is-there-a-limit-to-how-many-rules-can-be-set-to-tagged" />

<Accordion title="设置为标记的规则数量有限制吗？">

标记模式仅对高级客户可用。设置为标记的规则数量没有严格限制。作为最佳实践，请审核标记的规则，并在您对规则的准确性有信心时将其更改为已实施。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 相关账户下的用户权限 | 相关账户下的用户必须具有<Anchor target="_blank" href="/marketers/zh/docs/user-management">必要权限</Anchor>才能查看、添加和编辑验证规则。 |
| 用户获取 | 验证规则适用于激活、重装激活和再归因（即已从设备中移除相关应用的用户），但不适用于再互动（即设备中仍装有相关应用的用户）。 |
| 自动停用规则 | 如果您创建的规则：<ul><li>使用了Protect360专属的流量来源或条件，则当您的Protect360使用许可或试用期过期时，这些规则会自动停用。</li></ul> |
| 广告平台 | 广告平台仅在广告主为其开通权限后才能**查看验证规则**，了解规则详情。**请注意**：规则名称总是对代理可见（原始数据中也会呈现规则名称）。<br /><br /><Anchor target="_blank" href="/partners/zh/docs/validation-rules-for-ad-networks-and-agencies">详情请见广告平台的验证规则说明</Anchor> |
| 代理 | *代理仅在广告主为其开放相关权限后才能：<ul><li>**查看验证规则**，了解规则详情。**请注意**：规则名称总是对代理可见（原始数据中也会呈现规则名称）。</li><li>**添加和编辑验证规则**。**请注意**：代理无法编辑由广告主创建的规则。</li><li>**访问Protect360面板和原始数据**，查看规则并在其中添加Protect360专属条件。</li></ul>详情请见<Anchor target="_blank" href="/partners/zh/docs/validation-rules-for-ad-networks-and-agencies">代理的验证规则说明</Anchor> |
| 独立用户数 | 如果您配置了超过100个应用内事件，即使您使用了验证规则来排除应用内事件，仍会受到<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#limitations">独立用户数限制</Anchor>的影响。也就是说，对于100个以后的事件，即使AF根据您的验证规则将这些事件判定为无效，这些事件也不会有独立用户数信息。 |
| SKAN | 不支持 |

</Accordion>

<div data-zendesk-anchors="overview=%E7%AE%80%E4%BB%8B 01H8VFA2ADGT4AMC0NGDFXRB6Z=%E7%AE%80%E4%BB%8B 01H8VFA2AD99JSA6F6A3GKEXWV=outcomes 01H8VFA2AD9XSKKWHGM8KMN94Y=multiple-rules rule-builder=%E8%A7%84%E5%88%99%E9%85%8D%E7%BD%AE%E7%95%8C%E9%9D%A2 01H8VFA2ADQVCR8RYV9SBG52R7=%E8%A7%84%E5%88%99%E9%85%8D%E7%BD%AE%E7%95%8C%E9%9D%A2 h_01JK5G66CM9TCDK6GATNZC4QMW=%E6%B3%A8%E6%84%8F-1 validation-rule-examples=%E9%AA%8C%E8%AF%81%E8%A7%84%E5%88%99%E7%A4%BA%E4%BE%8B h_01KQER0NTPGGC7RYVBGKTZP02S=%E9%AA%8C%E8%AF%81%E8%A7%84%E5%88%99%E7%A4%BA%E4%BE%8B 01H8VFA2AD5Q2ZAB8BWEC7G1CF=install-sources 01H8VFA2AE4SEX1XRNVNHZ42TH=install-conditions bulk-upload=%E6%89%B9%E9%87%8F%E4%B8%8A%E4%BC%A0 h_01J4HRXAH6DEXXQZZ3YAWHY4TP=%E6%89%B9%E9%87%8F%E4%B8%8A%E4%BC%A0 01H8VFA2AE3SQ2X25JSXMS1SEY=inapp-event-sources 01H8VFA2AEDNXY70WZFBHFMB0S=inapp-event-conditions h_01JWX0RVRCNAQ0SVRDMAJ5HPW1=%E6%B3%A8%E6%84%8F 01H8VFA2AFYDB1RADDJFP34Q4M=protect360-install-and-inapp-event-sources 01H8VFA2AFHYK26P44VE16F4E4=protect360-install-conditions 01H8VFA2AFJGSFFM9QASF0H0Z4=protect360-inapp-event-conditions 01H8VFA2AFWE5FVC87XHWHVBBK=logic-between-conditions-and-condition-groups procedures=%E5%85%B6%E4%BB%96%E5%8A%9F%E8%83%BD 01H8VFA2AF6M84FKKVDTCXJEFR=%E5%85%B6%E4%BB%96%E5%8A%9F%E8%83%BD 01H8VFA2AFJFYFBA5HY2DH55VM=view-rule-list 01H8VFA2AF6CSC9W0949RFJ7C6=add-rule h_01JK5GDDGAZRKBVXZCCZ0RRB56=%E6%B3%A8%E6%84%8F-1 01H8VFA2AG2SWC9DVYWJXYNGXX=view-validation-rule-impact how-tagged-mode-works=%E6%A0%87%E8%AE%B0%E6%A8%A1%E5%BC%8F%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 h_01KQERXDE5SPB182AFA2CM2C78=%E6%A0%87%E8%AE%B0%E6%A8%A1%E5%BC%8F%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 rule-outcome-configuration=%E8%A7%84%E5%88%99%E7%BB%93%E6%9E%9C%E9%85%8D%E7%BD%AE h_01KQERXDE6668BR0EFDX9F5CYZ=%E8%A7%84%E5%88%99%E7%BB%93%E6%9E%9C%E9%85%8D%E7%BD%AE what-to-expect-when-configuring-a-rule=%E9%85%8D%E7%BD%AE%E8%A7%84%E5%88%99%E6%97%B6%E7%9A%84%E9%A2%84%E6%9C%9F%E6%83%85%E5%86%B5 h_01KQERXDE9AM8TWAAQK6XHETSA=%E9%85%8D%E7%BD%AE%E8%A7%84%E5%88%99%E6%97%B6%E7%9A%84%E9%A2%84%E6%9C%9F%E6%83%85%E5%86%B5 example-match-logic=%E7%A4%BA%E4%BE%8B%E5%8C%B9%E9%85%8D%E9%80%BB%E8%BE%91 h_01KQERXDEAQHC3SVFRT8V5X5S3=%E7%A4%BA%E4%BE%8B%E5%8C%B9%E9%85%8D%E9%80%BB%E8%BE%91 example-do-not-match-logic=%E7%A4%BA%E4%BE%8B%E4%B8%8D%E8%A6%81%E5%8C%B9%E9%85%8D%E9%80%BB%E8%BE%91 h_01KQERXDEA63J9ST9YSF27JKRD=%E7%A4%BA%E4%BE%8B%E4%B8%8D%E8%A6%81%E5%8C%B9%E9%85%8D%E9%80%BB%E8%BE%91 set-a-rule-to-tagged-mode=%E5%B0%86%E8%A7%84%E5%88%99%E8%AE%BE%E7%BD%AE%E4%B8%BA%E6%A0%87%E8%AE%B0%E6%A8%A1%E5%BC%8F h_01KQERXDEBEKF59KBVYTBWS471=%E5%B0%86%E8%A7%84%E5%88%99%E8%AE%BE%E7%BD%AE%E4%B8%BA%E6%A0%87%E8%AE%B0%E6%A8%A1%E5%BC%8F analyze-tagged-data=%E5%88%86%E6%9E%90%E6%A0%87%E8%AE%B0%E6%95%B0%E6%8D%AE h_01KQERXDEC1574K0V677N6ZGSY=%E5%88%86%E6%9E%90%E6%A0%87%E8%AE%B0%E6%95%B0%E6%8D%AE change-a-tagged-rule-to-implemented=%E5%B0%86%E6%A0%87%E8%AE%B0%E7%9A%84%E8%A7%84%E5%88%99%E6%9B%B4%E6%94%B9%E4%B8%BA%E5%B7%B2%E5%AE%9E%E6%96%BD h_01KQERXDEG3ZQPEYTSXAMMJNYC=%E5%B0%86%E6%A0%87%E8%AE%B0%E7%9A%84%E8%A7%84%E5%88%99%E6%9B%B4%E6%94%B9%E4%B8%BA%E5%B7%B2%E5%AE%9E%E6%96%BD 01H8VFA2AGAS3HH45Y5RJY1AA0=edit-or-delete-a-rule faq=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H8VFA2AG5DW5Z9G9FPSWM464=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H8VFA2AG49TT9HJZV03DV9FZ=what-is-a-regular-expression 01H8VFA2AGRG6D4MN0512E3T5C=why-doesnt-the-source-or-condition-display-as-a-suggested-value-when-i-search-for-it 01H8VFA2AGRQ5QTP081D9ED2VY=why-do-my-media-source-options-only-include-facebook-ads-and-twitter 01H8VFA2AGNTQZJEYTMM1FE5QM=is-it-necessary-to-have-andor-both-within-specific-conditions-and-between-condition-groups 01H8VFA2AGVJVBKG6SGZQJQD79=do-validation-rules-block-clicks 01H8VFA2AG4GNGMBW31HT4JF1W=looking-at-the-raw-data-i-see-that-installs-i-expected-to-be-blocked-by-validation-rules-have-a-different-block-reason-than-my-rule-name-why-is-that 01H8VFA2AGAK9BMAHTHQ3DFW2N=do-existing-rules-automatically-apply-for-newlyintegrated-agency-traffic 01H8VFA2AGACRX511105Z06XKK=how-do-the-not-in-last-conditions-work h_01KHRB9CBYYPK73K7SVC3N4B6A=%E7%A4%BA%E4%BE%8Bnot-in-last%E4%B8%8D%E5%9C%A8%E6%9C%80%E5%90%8En%E4%B8%AA%E7%89%88%E6%9C%AC%E4%B8%AD h_01KHRB9CC3BBTC41SXC482S7EY=%E7%A4%BA%E4%BE%8Bnot-in-last-major%E4%B8%8D%E5%9C%A8%E4%B8%BB%E7%89%88%E6%9C%AC%E7%9A%84%E6%9C%80%E5%90%8En%E4%B8%AA%E6%AC%A1%E7%89%88%E6%9C%AC%E4%B8%AD h_01KHRB9CC6GJDNH97N0GSHDNKE=%E4%BA%86%E8%A7%A3%E6%9D%A1%E4%BB%B6%E5%A6%82%E4%BD%95%E4%B8%8E%E5%A4%9A%E4%B8%AA%E5%BA%94%E7%94%A8%E4%B8%80%E8%B5%B7%E5%B7%A5%E4%BD%9C h_01KKBT57F97HFYM4SKD0BSDC0P=how-do-i-block-attribution-for-installs-or-inapp-events-from-impressions h_01KQES367JXZSZ983MP1YB5EBH=does-tagged-mode-support-all-condition-types h_01KQES367JPE3HW5YQAGCGYA7Y=will-tagged-data-appear-in-blocked-reports h_01KQES367JXHC1F55THKW6DP89=where-can-i-view-tagged-data h_01KQES367JVF34N3FMTE9FMQ4B=can-i-change-a-rule-from-tagged-to-implemented-at-any-time h_01KQES367J827ZQEENHCMWZS6S=is-there-a-limit-to-how-many-rules-can-be-set-to-tagged 01H8VFA2AHHEYDV763QQ6KPMWK=traits-and-limitations" />

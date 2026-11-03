---
title: iOS 14、ATT和SKAN的快速入门指南及常见问题答疑
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-08-11T09:19:23Z'
  edited_at: '2026-10-14T09:59:18Z'
  id: 360011890298
  locale: zh-cn
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/zh-cn/articles/360011890298
---
> **概要**：概要：自iOS 14.5上线后，Apple就开始要求广告主使用<Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency">AppTrackingTransparency</Anchor>（应用跟踪透明度，简称ATT）弹窗，并遵守相关规定。ATT要求广告主必须同时在流量方应用（Publisher App）和广告主应用（Advertiser App）中都通过ATT授权弹窗获得终端用户的授权，然后才能收集其数据并与其他公司分享该数据，用以进行跨应用、跨网站的跟踪。如果不跟踪，则无需显示该弹窗。

![iOS14-consent-pre-ATT-enforcement-6522_Cover-image_917x480.jpg](https://files.readme.io/622b57cf6b6b7ad9472b3d072f44d9b451e82fec6b0c918427e39e9e6700602e-360019478118.jpg)

## ATT环境中的移动归因与衡量

对于应用到应用的付费广告，SKAN可提供确定性归因。自有媒体、网页到应用及Apple Search Ads等其他类型的广告仍可通过AppsFlyer的传统归因工具进行归因。这些传统归因工具可提供长期的LTV衡量数据，而SKAN只衡量激活后较短一段时间内的用户行为。

总而言之，要全面了解投放效果和应用使用情况，您需要同时使用SKAN和AppsFlyer传统归因解决方案，以互为补充。

本文的目的是为广告主介绍SKAN和ATT，其中的内容需要您对AppsFlyer平台有一定的了解。

<div id="skan-solution-principles" />

<Accordion title="SKAN解决方案原理">

AppsFlyer会根据iOS的SKAN回传来提供汇总的iOS归因结果。这些回传数据先由iOS发送到广告平台，再由广告平台转发到AppsFlyer，其中包含经匿名化处理的归因记录，且每次回传都带有对应的转化值（CV）。转化值是由广告主设置的，用于在激活后最初的一段时间内衡量用户质量。

AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">SKAN</Anchor>解决方案能为广告主提供以下功能：

* 汇总各广告平台的回传数据，并使用成本等其他数据加以补充，最终形成面板和报告中的SKAN数据。
* 广告主可以使用AppsFlyer的转化值操作台调整CV值衡量的对象，无需更改应用代码。CV值可用于衡量收入、互动或转化事件。

**SKAN的局限性**

* 触达范围。投放数据：SKAN不提供Apple Search Ads或交叉推广的投放数据以及移动端网页助攻激活的数据。

**SKAN归因链路**

![SKAN_flow_-_Affinity_diagram_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. 广告主在AppsFlyer的转化值操作台中完成SKAN衡量设置。
2. 用户首次打开应用。
3. AppsFlyer在每个衡量窗口期内根据用户行为和广告主设定的CV映射构架设置CV值。
4. 窗口期结束后，iOS向相关的广告平台发送回传，同时向AppsFlyer发送回传备份。回传接收时间会有一定的延迟，具体如下：
   * SKAN 4衡量窗口1:0-24小时
   * SKAN 4衡量窗口2-3：0-24小时
   * SKAN 3：最近一次CV值上升后的24-48小时
5. iOS设备直接把回传数据备份发送到AppsFlyer，然后AF将其转发到广告主指定的端点。详见如何将SKAN回传数据备份发送到AppsFlyer。
6. 广告平台扩充回传数据，然后转发给AppsFlyer，或者由SRN通过API向AF发送回传数据。
7. AppsFlyer验证并解析CV。AF会先对解析后的数据进行记录并归因，然后广告主就可以通过AF的面板、报告和API拉取这些数据。

</Accordion>

<div id="att-principles" />

<Accordion title="ATT原理">

广告主能够通过ATT弹窗来获取明确的用户授权，用以进行数据收集和共享。从iOS 14.5开始，广告主必须获得用户授权才可读取IDFA。

流量方应用（Publisher App）和广告主应用（Advertiser App）都必须显示ATT弹窗。如果用户在两个应用中都同意授权，则表示该用户同意被*跟踪*，且Apple允许广告主在不同厂商的应用之间对该用户进行跨应用跟踪。

**ATT的设置**

下表列出了ATT可能出现的值。 最初的ATT值由iOS设置为not determined（未确定）或restricted（受限）。

需要注意，您可以自行决定是否使用授权弹窗。如果您展示该弹窗，则有可能使用户的授权状态从*not determined*（未确定）转变为*authorized*（已授权），如果您不展示该弹窗，则无法获得*授权*。

| ATT值 | IDFA是否可用 | 说明 |
| --- | --- | --- |
| Restricted（受限） | 否 | <ul><li>由Apple根据用户年龄等标准判定，相关设备的用户无法更改该值。</li><li>授权弹窗无法向这类用户展示。</li></ul> |
| Not determined（未确定，适用于iOS 14.4及之前版本） | 是 | 默认值 |
| Not determined<br /><br />（未确定，适用于iOS 14.5及之后版本） | 否 | 默认值 |
| Denied（拒绝授权） | 否 | 符合下列任一条件时会出现该值：<ul><li>该值是在展示弹窗后设定的</li><li>用户点击了*要求App不跟踪*（设备层级总开关）</li><li>在安装iOS 14以前，用户启用了LAT</li></ul> |
| 已授权 | 是 | 该值是在展示弹窗后设定的 |

**ATT的影响**

ATT弹窗出现后，很多用户会选择拒绝授权，导致IDFA不可用，进而阻断了广告跟踪。这就迫使在iOS 14.5之前依赖用户级别归因报告的广告主改用汇总的归因和报告来完成一部分数据分析。有关传统归因方式请见<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">AppsFlyer归因模型</Anchor>。

具体应用的归因数据可有多个来源，每个应用的可用和适用标识符各不相同。大部分数据通过传统归因工具上报，但由SKAN归因的激活数据通过SKAN面板上报。

</Accordion>

<div id="which-dashboard-has-the-install" />

<Accordion title="激活数据落在哪个面板？">

iOS 14平台中的激活可能会同时由传统归因方式和SKAN面板重复归因。此外，这类激活可能在一个面板上显示为自然量，而在另一个面板上显示为非自然量，具体取决于媒体渠道的投放场景。

</Accordion>

## iOS 14重点内容

#### iOS 14及SKAN相关的文档和链接

| 主题 | 文档 |  |
| --- | --- | --- |
| SKAN | <Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports">SKAN原始数据字段</Anchor> | SKAN原始数据报告中的新增字段，支持did\_win上报，适用于SKAN 3.0 |
| SKAN | <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">SKAN解决方案</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">应用激活显示到面板的时间</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#organic-metrics-in-the-context-of-skadnetwork">SKAN中的自然量指标</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#appsflyer-attribution-vs-skan-attribution">AppsFlyer归因与SKAN归因的对比</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#faq-skan-discrepancies">SKAN数据差异的常见问题解答</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/zh/docs/skan-interoperation">渠道的SKAN互通性</Anchor>（文档列表） | <Anchor target="_blank" href="/marketers/zh/docs/skan-integrated-partners-list">SKAN对接渠道列表</Anchor> |
| SKAN | <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-interoperation-with-meta-ads">Meta ads与AppsFlyer的SKAN对接</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq">问题排查及数据差异</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook">衡量与时间差异</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/zh/docs/skan-interoperation-with-snapchat">Snapchat与AppsFlyer的SKAN对接</Anchor> | <Anchor target="_blank" href="/marketers/zh/docs/skan-interoperation-with-snapchat#discrepancies-guide">数据差异指南</Anchor> |
| 隐私 | <Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">汇总层级的高级隐私保护（AAP）</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework#受aap影响的功能">受AAP影响的功能</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework#aap-central-switch">AAP的启用与停用</Anchor></li></ul> |
| 隐私 | <Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">受限媒体渠道</Anchor> | <Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields">受限原始数据字段</Anchor> |
| iOS 14 | <Anchor target="_blank" href="/marketers/zh/docs/preparing-for-the-app-store-review-nutrition-labels">隐私标签（Nutrition Labels）—如何应对App Store的审核</Anchor> |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">如何在应用中配置ATT</Anchor>（开发人员的SDK指南） |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">Google、Meta ads等自归因平台（SRN）说明</Anchor> | SRN的激活上报说明 |
| 计费 | <Anchor target="_blank" href="https://content.appsflyer.com/ios-14-hub/billing/">iOS应用的计费方式</Anchor> |  |

<div id="ios-14-impact-on-attribution-and-measurement" />

<Accordion title="iOS对归因和衡量的影响">

#### **指标**

对于拒绝ATT授权的用户，其相关指标会出现以下变化：

| 指标 | 上升 | 下降 | 说明 |
| --- | --- | --- | --- |
| 非自然量与自然量 | 自然量 | 非自然量 |  |
| 重装激活与新增激活 | 激活假量 | 重装激活 |  |
| 再营销 | 自然激活及应用内事件 | 再互动、再归因 |  |
| Apple Search Ads | -- | -- | 无变化。无论用户授权与否，都会得到正确归因。 |

#### **深度链接**

使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-legacy-apis#deferred-deep-linking">onConversionDataSuccess</Anchor>这一历史方法实现的延迟深度链接在iOS 14.5中可能会失效，因为这类链接所需的归因数据可能会受到隐私保护机制的影响而不可用。

建议您使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl-1">Unified Deep Linking（UDL）</Anchor>，详情请见此处说明。

</Accordion>

## 常见问题解答—iOS 14+

<div id="what-happens-to-an-app-using-an-sdk-version-before-v6" />

<Accordion title="如果应用中接入了V6+之前的SDK会导致什么结果？">

如果您应用中接入的SDK版本早于6.0：

* SKAdNetwork和Apple Search Ads无法生效。
* 如果在App Store中提交该应用，基本无法通过审核。

</Accordion>

<div id="is-it-mandatory-to-display-the-att-prompt" />

<Accordion title="应用中必须展示ATT弹窗吗？">

不一定。仅当您需要*跟踪*用户和/或收集IDFA时才需要获得ATT授权。

</Accordion>

## 常见问题解答—SKAN

<div id="how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4" />

<Accordion title="如何确定何时收到回传？如何确定收到的回传是SKAN 3还是SKAN 4？">

您接收到的SKAN回传类型取决于多种因素，包括您在转化值操作台中使用的衡量模式、您使用的广告平台以及用户的iOS版本。

这些因素会影响到以下几个方面：

* <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#principles-and-flow">了解详情</Anchor>
* 在SKAN 3中则为用户行为窗口期（AW）。请注意：请注意：如果您在转化值操作台中没有启用SKAN 4，但是广告平台的签名是SKAN 4，则该窗口期取AW和48小时之间较短的一个。
* 取决于窗口期结束的时间。<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide?query=skan%20faq#timing-from-app-install-until-dashboard-and-reports-update">了解详情</Anchor>
* 滚动计时器：SKAN 3的用户行为窗口期最长可达63天，iOS仅在窗口期结束后才会发送回传。

下图展示了回传的详细流程：

![SKAN_4_matrix_-_Page_8__1_.png](https://files.readme.io/0dbd4cae34d9f9fed80dbe835485789dab75d46dbb38de055f454d01efb97350-13756140934545.png)

</Accordion>

<div id="in-skan-am-i-limited-to-100-campaign-ids-per-ad-network" />

<Accordion title="在SKAN场景中，每个广告平台上使用的来源标识符/广告系列ID数量是否有限制？">

是是的，之前的上限是每个广告平台最多100个广告系列ID。但从SKAN 4开始，广告系列ID改为分等级的来源标识符（source identifier），上限为10000个。来源标识符为4位整数。

广告平台会将SKAN来源标识符映射到其广告系列ID。

</Accordion>

<div id="what-is-the-use-case-for-skan-raw-data" />

<Accordion title="在哪些场景中会用到SKAN原始数据？">

* 您可以使用汇总API中不可用的维度对原始数据进行汇总。
* 便于您调整现有的原始数据入库流程以导入SKAN原始数据。

</Accordion>

<div id="why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio" />

<Accordion title="为什么我收到的转化值跟我在AppsFlyer转化值操作台里配置的转化值不匹配？">

一般来说，这是因为您的应用中还有另一个能够设置转化值的SDK，与AppsFlyer的SDK冲突，导致转化值与您在AppsFlyer中的设置不匹配。请确保您的应用中没有接入其他可以设置转化值的SDK。

</Accordion>

<div id="why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports" />

<Accordion title="为什么SKAN面板中的汇总数据与Data Locker的SKAN报告原始数据不匹配？">

举例来说，

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/getting-started-onboarding-for-marketers#第3步归因设置">AppsFlyer入门分步指南</Anchor>

<div data-zendesk-anchors="attribution-measurement-in-an-att-environment=att%E7%8E%AF%E5%A2%83%E4%B8%AD%E7%9A%84%E7%A7%BB%E5%8A%A8%E5%BD%92%E5%9B%A0%E4%B8%8E%E8%A1%A1%E9%87%8F h_01HE0C8YXSXSX003X0671Z97KZ=att%E7%8E%AF%E5%A2%83%E4%B8%AD%E7%9A%84%E7%A7%BB%E5%8A%A8%E5%BD%92%E5%9B%A0%E4%B8%8E%E8%A1%A1%E9%87%8F h_01HE0C8YXSCA8M57F1RG4CJ7HK=skan-solution-principles h_01HE0C8YXSSCTQJAPDE27FB1H8=att-principles h_01HE0C8YXS0BFA2M16D1Q2PQYW=which-dashboard-has-the-install ios-14-important-knowledge=ios-14%E9%87%8D%E7%82%B9%E5%86%85%E5%AE%B9 h_01HE0C8YXS3BH109DF1Y1KNK5P=ios-14%E9%87%8D%E7%82%B9%E5%86%85%E5%AE%B9 ios-14-and-skan-articles-and-links=ios-14%E5%8F%8Askan%E7%9B%B8%E5%85%B3%E7%9A%84%E6%96%87%E6%A1%A3%E5%92%8C%E9%93%BE%E6%8E%A5 h_01HE0C8YXSPZKBWXC51Z2636R0=ios-14%E5%8F%8Askan%E7%9B%B8%E5%85%B3%E7%9A%84%E6%96%87%E6%A1%A3%E5%92%8C%E9%93%BE%E6%8E%A5 h_01HE0C8YXSTCVA8YYR4BQVHVXS=ios-14-impact-on-attribution-and-measurement metrics=%E6%8C%87%E6%A0%87 h_01HE0C8YXSJMYN81FKPCA8ATK7=%E6%8C%87%E6%A0%87 deep-linking=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01HE0C8YXS6ADG1SQCMVP0W69B=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 faq%E2%80%94ios-14=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94ios-14 h_01HE0C8YXSV9VSK1NPG9RCTQW1=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94ios-14 h_01HE0C8YXS1FFYQJ8YZXP9W9ZV=what-happens-to-an-app-using-an-sdk-version-before-v6 h_01HE0C8YXSKA0325YJSXV81ZB9=is-it-mandatory-to-display-the-att-prompt faq%E2%80%94skan=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94skan h_01HE0C8YXSQKH8ER1Q5VS6Z0NM=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94skan how-do-i-know-when-i%E2%80%99ll-receive-postbacks-and-if-they%E2%80%99ll-be-skan-3-or-skan-4=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXS44YXAN2DV2ZR03GE=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXSCWM892QH0N7YQ8HP=in-skan-am-i-limited-to-100-campaign-ids-per-ad-network h_01HE0C8YXSSWHV45M6P7SQGCRD=what-is-the-use-case-for-skan-raw-data h_01HE0C8YXS8GJKFC23S1R9TWW0=why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio why-doesn%E2%80%99t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE0C8YXS1VW1T50ARJE0MP62=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE7SNR02VQDKG55QP06ECNAR=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

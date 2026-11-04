---
title: Meta ads数据差异
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-09T10:10:54Z'
  edited_at: '2026-10-14T10:07:53Z'
  id: 4410481130641
  locale: zh-cn
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410481130641
---
> **概要：** 本文重点解释了Meta ads和AppsFlyer之间的归因模式差异。

<div id="meta-ads-discrepancies-with-appsflyer" />

## Meta ads与AppsFlyer的数据差异

移动获客生态中的各大平台都有其独有的归因模式，AppsFlyer和Meta ads也不例外。而双方归因模式的不同会使得Meta ads和AppsFlyer面板中呈现的数据也有所差异。

虽然我们一直与Meta ads保持紧密的合作，以尽可能地减少这样的差异，但广告主仍应了解下文所述的各种数据差异成因。

<div id="detect-a-discrepancy-between-appsflyer-and-meta-ads" />

### AppsFlyer与Meta ads的数据差异判断方式

对比Meta ads **Event Manager**和AppsFlyer报告中的事件，如果事件数量相差很大，说明可能存在数据差异。

<div id="differences-in-attribution-models" />

## 归因模型的差异

<table><thead><tr><th>原因</th><th>Meta ads</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><strong>点击型归因窗口期</strong></td><td>7天（请注意：<a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">某些情况下，默认窗口期会有所变化</a>）。</td><td>1-30天。使用Meta ads时，请务必将该窗口设置为7天。</td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><strong>浏览型归因窗口期</strong></td><td>1天（请注意：<a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">某些情况下，默认窗口期会有所变化</a>）。</td><td>默认情况下为1天，但可以配置为1-48小时（保留此默认值）</td></tr><tr><td><span id="multichannel-sourceattribution"></span> <strong>多源<br/>归因 </strong> </td><td>Meta ads无视其他渠道的广告互动，将激活归因给自己。</td><td>AppsFlyer使用末次点击归因（详情请见<a href="./appsflyer-attribution-model" title="AppsFlyer归因模型" target="_blank"></a> ）。</td></tr><tr><td><span id="crossdevice-attribution"></span><strong>跨设备归因</strong></td><td>Meta ads按用户归因，将在不同平台（iOS/安卓/PC端）上完成的点击和激活关联到相关用户。</td><td>AppsFlyer按独立设备归因，该设备既有互动也有安装</td></tr><tr><td><span id="different-time-zones"></span><strong>时区不同</strong></td><td>Meta ads默认的报告时区为PST。请将<a href="https://www.facebook.com/business/help/754049591334898" target="_blank">Meta ads Manager中的时区调整</a>到您在AppsFlyer后台应用配置中设定的时区。</td><td>AppsFlyer中默认的应用时区为UTC+0。您可以在<a href="./app-settings#localization-time-zone" target="_blank">应用配置页面</a>中更改时区设置，使其与Meta ads Manager中的时区一致。</td></tr><tr><td><span id="google-install-referrer"></span> <strong>Install referrer（激活来源标识）</strong>：</td><td colspan="2"></td></tr></tbody></table>

<div id="click-through-and-view-through-attribution" />

## 点击型和浏览型归因

AppsFlyer支持点击型归因和浏览型归因。为了尽量减少Meta ads和AppsFlyer之间的数据差异，请确保您在AF中设置的点击和展示回溯窗口与Meta Ads中对应的默认窗口期保持一致。

Meta ads中默认的点击型回溯窗口为7天。虽然[在某些情况下默认窗口期会有所不同](https://www.facebook.com/business/help/395050428485124?id=428636648170202)，但仍建议您将AppsFlyer中的点击型回溯窗口设为7天，与Meta ads的默认设置保持一致。

![image__4_.png](https://files.readme.io/215d2234aae1ec6b4e1c6ac922915851bf8ab02574a874119d286fa49c64f9ba-25899749062033.png)

<div id="example" />

> 📄 **示例**
>
> 假设您在AppsFlyer后台将com.greatapp应用的Meta ads点击回溯窗口期设为1天，而在Meta ads中该窗口期默认为7天。如果用户在Facebook中点击了Greatapp的广告，并在之后的2-7天内激活该应用，这些用户在AppsFlyer中会被记录为自然流量，而Meta ads则会将其归因给自己。

### 媒体渠道受限导致的数据差异

到2021年10月28日为止，所有展示归因（VTA）的用户数据都<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">呈受限状态，不向广告主开放</Anchor>。  
从2021年10月29日开始，除了展示归因外，该限制还扩展到点击归因的用户数据。汇总报告不受此限制影响。

由于Meta ads不发送用户级别数据，因此AppsFlyer无法将形成转化助攻的展示和点击归因到Meta ads。下文示例说明了这类差异的具体场景：

> 📄 **示例**
>
> 1. 用户在Facebook上浏览并点击AwesomeApp的广告。之后该用户又在名为GreatAdNetwork的广告平台上看到并点击了AwesomeApp的广告，然后安装了该应用。
> 2. 由于这次转化发生在Meta ads的回溯窗口内，因此FB会认领该转化。
> 3. AppsFlyer则会将该次转化归因给GreatAdNetwork广告平台，因为该平台带来了应用激活前的最后一次广告互动。
> 4. AppsFlyer不会将Meta ads记录为助攻渠道，因为Meta ads的原始数据受限。这时，您实际看到的内容如下：
>    * 面板中："Restricted"
>    * 原始数据报告中：“Contributor Media Source”列（助攻渠道）为空

但是，对于点击归因，如果广告将用户引导到Google Play Store，则广告主可以通过Google Install Referrer获得归因数据。AppsFlyer会用Referrer中的字段填充原始数据报告并呈现给广告主，同时使用该数据对没有设备ID（即启用了LAT）的用户进行归因。

<div id="in-app-events-differences" />

## 应用内事件差异

Meta ads和AppsFlyer的激活后事件（如应用内购）数据中也可能出现差异。下表列出了造成这些差异的常见原因，并提供了相应的建议，帮助您尽量避免相关差异：

| 原因 | 说明 | AppsFlyer 的提示 |
| --- | --- | --- |
| <span id="different-lifetime-definition"></span>**生命周期定义差异** | Meta ads将用户的生命周期界定为最长7天，也就是说，用户点击广告的7天之后发生的事件不会出现在Meta ads数据中。  <br />而AppsFlyer将Meta ads用户的生命周期界定为最长180天。 | 对于由Meta ads广告带来的用户，如需评估其在广告互动的7天之后的价值，请使用AppsFlyer的数据，更全面地了解用户价值。 |
| <span id="unmapped-events"></span>**未映射的事件** | AppsFlyer通过SDK获取事件信息，如果您未将相关事件映射到Meta ads，则AF不会向其发送这些事件。 | 请确保将所有代表用户质量的应用内事件都<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-in-app-event-mapping">映射到Meta ads</Anchor>。 |
| <span id="unsent-revenue"></span>**未发送的收入** | AppsFlyer通过SDK获取收入信息，如果您未选择发送收入，则AF不会将其发送给Meta ads。 | 在AF渠道对接配置的应用内事件回传部分，请务必对收入相关事件（如购买等）选择**发送值与收入**。 |
| <span id="missing-event-values-on-facebook"></span>**Meta ads数据缺少事件值** | 如果参数和值的结构正确，AppsFlyer就会将其作为映射事件的一部分发送给Meta ads。 | 请根据<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-event-structure">AppsFlyer推荐的结构</Anchor>打点SDK应用内事件，以充分映射Meta ads事件值。 |
|  <span id="different-event-count"></span>|  | 有关更多信息，请参见<Anchor target="_blank" href="/marketers/zh/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports#关于数据差异">这里</Anchor> 。活跃数据 |

<div id="installs-from-re-engagement-campaigns-in-my-ua-dashboard" />

## 为什么UA面板中会出现再营销广告带来的激活？

再营销广告可以使已安装用户打开应用（ **再互动** ）。或者，当AppsFlyer识别到某个设备曾经安装过该应用时，AppsFlyer就会将这个转化记录为**再归因** 。

如果Meta ads向**新用户**或**在**<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">**再归因窗口**之后</Anchor>重装激活应用的用户投放了再营销广告，AppsFlyer会将这些用户记录为**新增激活**，而在Meta ads中这些用户则会出现在再营销广告下。

但如果重装激活发生在原始激活后的**再归因窗口期内**，AppsFlyer会将其记录为再归因，呈现在再营销面板中，而Meta ads则会将其记录为新增激活。

<div id="note" />

> 📘 **注意事项**
>
> 对于再营销广告，Meta ads会在同一个面板中呈现所有相关激活，而AppsFlyer则会在数据总览面板和再营销面板中分别呈现新增激活和再归因/再互动。

<div id="cross-device-attribution" />

## 跨设备归因

Meta ads会上报跨设备归因，因此有时广告所定向的平台（iOS/安卓）与用户最终激活的平台可能会不一致，从而造成数据差异。

<div id="example-1" />

> 📄 **示例**
>
> Linda在她的安卓手机上点击了一则有关GreatApp应用的Facebook广告。Meta ads上报Linda完成的点击，并将其记录在名为“Android Females”的原始安卓广告系列下。然后，Linda决定在她的iPad上下载GreatApp。在Linda首次打开该应用时，AppsFlyer会向Meta ads查询该次iOS激活的来源，这时Meta ads会回复该激活来自“Android Females”广告系列。

<div id="validation-rules-and-protect360" />

## 验证规则和Protect360

如果您启用了<Anchor target="_blank" href="/marketers/zh/docs/implement-validation-rules-to-prevent-fraud">AppsFlyer的验证规则</Anchor>功能，则AF可能会按照您设定的规则拦截部分来自Meta ads的激活，从而造成数据差异。在这样的情况下，Meta ads会将相关激活归因给自己，而AppsFlyer则会拦截这些激活。

同理，如果您使用了AppsFlyer的Protect360防作弊解决方案，也可能会出现被Meta ads自归因而被AF拦截的激活。

<div id="example-2" />

> 📄 **示例**
>
> GreatApp的UA经理Jeff创建了一个名为SPNA的广告系列，定向投放到生活在北美的西班牙语用户。为了确保这一点，Jeff定义了一个验证规则，该规则是仅接受来自加拿大和美国的用户。
> 这时，某个位于西班牙的Meta ads用户点击了该广告并激活应用，Meta ads就会将该次激活归因给自己，而AppsFlyer则会因为该激活不符合验证规则而将其拦截下来。

<div id="meta-probabilistic-modeling-aem-discrepancies-in-ios-apps" />

<div id="sdk-related-discrepancies" />

## SDK相关的数据差异

<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-faq#who-needs-facebooks-sdk">有些情况下，广告主会在其应用中同时接入AppsFlyer和Facebook SDK</Anchor>。这可能会使应用内事件的数据出现差异。对于同时由Facebook SDK和AppsFlyer SDK上报的事件， Meta ads不会进行去重。也就是说，Meta ads可能会上报双倍的收入等事件，造成数据虚高。

* 请使用以下任一方法避免Meta ads重复上报应用内事件：
  * 不在Facebook SDK中配置事件。
  * 在AppsFlyer后台关闭<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-in-app-event-mapping">Meta ads应用内事件映射</Anchor>。

<div data-zendesk-anchors="facebook-ads-discrepancies-with-appsflyer=meta-ads%E4%B8%8Eappsflyer%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 01H890CZSXPMK0BDMC4202HNYM=meta-ads%E4%B8%8Eappsflyer%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 detect-a-discrepancy-between-appsflyer-and-facebook=appsflyer%E4%B8%8Emeta-ads%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82%E5%88%A4%E6%96%AD%E6%96%B9%E5%BC%8F 01H890CZSXGHVBH21SQA0671JQ=appsflyer%E4%B8%8Emeta-ads%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82%E5%88%A4%E6%96%AD%E6%96%B9%E5%BC%8F differences-in-attribution-models=%E5%BD%92%E5%9B%A0%E6%A8%A1%E5%9E%8B%E7%9A%84%E5%B7%AE%E5%BC%82 01H890CZSX8M6VGGREYX4W2X37=%E5%BD%92%E5%9B%A0%E6%A8%A1%E5%9E%8B%E7%9A%84%E5%B7%AE%E5%BC%82 clickthrough-and-viewthrough-attribution=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%92%8C%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0 01H890CZSX40JDGY8P8AQ4CYGS=%E7%82%B9%E5%87%BB%E5%9E%8B%E5%92%8C%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0 01H890CZSXRD7PCZBK52GW7QE9=%E7%A4%BA%E4%BE%8B restricted-media-discrepancies=%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E5%8F%97%E9%99%90%E5%AF%BC%E8%87%B4%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 01H890CZSX5WFX5Q0RNSG01GFH=%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E5%8F%97%E9%99%90%E5%AF%BC%E8%87%B4%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 01H890CZSX567CQ3ZWZS5F05XW=%E7%A4%BA%E4%BE%8B-1 inapp-events-differences=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%B7%AE%E5%BC%82 01H890CZSXKC5JKK9051MC0VY6=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%B7%AE%E5%BC%82 installs-from-reengagement-campaigns-in-my-ua-dashboard=%E4%B8%BA%E4%BB%80%E4%B9%88ua%E9%9D%A2%E6%9D%BF%E4%B8%AD%E4%BC%9A%E5%87%BA%E7%8E%B0%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E5%B8%A6%E6%9D%A5%E7%9A%84%E6%BF%80%E6%B4%BB 01H890CZSYE21K7PBQK4PNMGJR=%E4%B8%BA%E4%BB%80%E4%B9%88ua%E9%9D%A2%E6%9D%BF%E4%B8%AD%E4%BC%9A%E5%87%BA%E7%8E%B0%E5%86%8D%E8%90%A5%E9%94%80%E5%B9%BF%E5%91%8A%E5%B8%A6%E6%9D%A5%E7%9A%84%E6%BF%80%E6%B4%BB 01H890CZSY7TRCA4NVKSVPY7DB=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 crossdevice-attribution::77a37a1f=%E8%B7%A8%E8%AE%BE%E5%A4%87%E5%BD%92%E5%9B%A0 01H890CZSYS8QKEAF6799SBS8J=%E8%B7%A8%E8%AE%BE%E5%A4%87%E5%BD%92%E5%9B%A0 01H890CZSY2Z3S6E9R5MYC1CHX=%E7%A4%BA%E4%BE%8B-2 validation-rules-and-protect360=%E9%AA%8C%E8%AF%81%E8%A7%84%E5%88%99%E5%92%8Cprotect360 01H890CZSYDHZE4V0ZWTT8V0EJ=%E9%AA%8C%E8%AF%81%E8%A7%84%E5%88%99%E5%92%8Cprotect360 01H890CZSYCTQZCAYAZP9TCBBF=%E7%A4%BA%E4%BE%8B-3 sdk-related-discrepancies=sdk%E7%9B%B8%E5%85%B3%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 01H890CZSYVFPQP0SKNPWMPB1R=sdk%E7%9B%B8%E5%85%B3%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82" />

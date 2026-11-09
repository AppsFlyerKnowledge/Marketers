---
title: 自归因平台（SRN）
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Ad Networks
    - srn
    - Self-reporting
    - networks
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
    - Ad Networks
  created_at: '2018-10-22T05:21:45Z'
  edited_at: '2026-10-14T10:05:13Z'
  id: 360001546905
  locale: zh-cn
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001546905
---
> **概要：** 本文介绍了自归因平台（简称SRN）的归因方式、深度链接、iOS应对方案，并提供常见问题答疑。

<div id="srns-integrated-with-appsflyer" />

## 与AppsFlyer对接的SRN

| **SRN** | **Logo** |
| --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/amazon-ads-campaign-configuration">Amazon Ads</Anchor> | <Image alt="amazon-ads-logo.png" src="https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png" width="134px" /> |
| <Anchor target="_blank" href="/marketers/zh/docs/apple-ads-integration-setup">Apple Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/iossearchads.png" width="131px" /> |
| <Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png?v=1" width="47px" /> |
| <Anchor target="_blank" href="/marketers/zh/docs/google-marketing-platform-display-video-360-dv360-integration">Google Marketing Platform</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png?v=1" width="45px" /> |
| <Anchor target="_blank" href="/marketers/zh/docs/meta-ads-integration-setup">Meta ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/facebook.png?v=1" width="67px" /> |
| <Anchor target="_blank" href="/marketers/zh/docs/roku-integration-with-appsflyer">Roku</Anchor> | <Image alt="roku.png" src="https://files.readme.io/4909a45e611700e5c2a69f94710226e65e10faf620e3a7939a2c038bea1736ca-33565070184337.png" width="150px" /> |
| <Anchor target="_blank" href="/marketers/zh/docs/snapchat-advanced-srn-integration-setup">Snapchat—高级SRN</Anchor> | <Image alt="snapchat_logo.png" src="https://files.readme.io/c9b62d55d5c1497011d7411a21dca6f1668308bbe2806ab238b71742c421b182-32259457816209.png" width="41px" /> |
| 腾讯社交广告 | <Image alt="blobid0.jpg" src="https://files.readme.io/6d6e9661c9d81f80ffeedfdf4850a84f3cc183faa49a514d1d3bb116641738da-32259428896017.jpg" width="80px" /> |
| <Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Business——高级SRN</Anchor> | ![TTFB_logo__4C_horizontal_black.png](https://files.readme.io/caa8c9e02b161eea10740cb79f26d04d3324e87b9cfd929281374d2d7936ef2e-32259428903953.png) |
| <Anchor target="_blank" href="/marketers/zh/docs/x-ads-formerly-twitter-ads-setup-guide-overview">X Ads</Anchor> | <Image alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="37px" /> |
| <Anchor target="_blank" href="/marketers/zh/docs/yahoo-integration-setup">Yahoo（Oath：Ad Platforms / Yahoo Gemini）</Anchor> | <Image alt="verizonmedia.png" src="https://files.readme.io/36291ff556d07a5dbf2ae8ff693ea33d21dae9e0518a94b251202634a24049cf-32259428916369.png" width="76px" /> |
| <Anchor target="_blank" href="/marketers/zh/docs/yahoo-japan-search-ads-campaign-configuration">Yahoo!Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yahoojapansearch.png" width="139px" /> |

**请注意：** 各SRN都有其自己的<Anchor target="_blank" href="/marketers/zh/docs/user-level-data-retention">用户级别数据使用和保留政策</Anchor>。

<div id="attribution" />

## 归因

非SRN平台通过归因链接向AppsFlyer上报事件，而SRN则使用设备ID对AppsFlyer发出的激活信息进行匹配，从而完成自归因。在iOS应用中，相关流量的归因通过<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">SKAN</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">汇总层级的高级隐私保护机制</Anchor>完成。

无论是SRN还是非SRN，AppsFlyer都根据以下逻辑进行归因：

* 末次触达和多点触达方法论。
* AppsFlyer的标准归因逻辑，用于对相关的展示和点击数据进行排序。

<div id="how-does-attribution-work-with-srns" />

### SRN的归因原理

SRN会通过以下方式向AppsFlyer上报新增激活和应用内事件等数据：

* 使用API与归因衡量服务商进行数据传输。
* 当第三方归因服务商检测到激活时，会使用与该激活相关的设备ID（Advertising ID）向SRN发出查询请求。
* 上报所有相关点击或展示的详细信息。

AppsFlyer完成归因后，会该<Anchor target="_blank" href="/marketers/zh/docs/user-level-data-retention#渠道的数据保留期限">SRN的数据保留期限</Anchor>内向其发送应用内事件回传。

<div id="how-does-attribution-work-with-advanced-srns" />

### 高级SRN的归因原理

高级SRN的归因原理与常规SRN相同，但高级SRN可以在没有设备ID（IDFA）的情况下对广告交互行为进行归因，这是通过<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary#aggregated-advanced-privacy">汇总层级的高级隐私保护j</Anchor>机制完成的。某些情况下，AF会通过双授权用户（在广告主应用和媒体侧应用中都授权允许广告跟踪）的ID匹配来完成归因，而对于部分高级SRN，AF则会通过API互通点击和展示数据，并根据<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#probabilistic-modeling">概率建模</Anchor>来完成归因。

<div id="install-attribution" />

### 激活归因

潜在应用用户看到多条广告，并与其发生交互，然后激活应用。一般情况下，归因服务商会为广告主提供末次触达归因。也就是说，用户激活会被归因到实际激活之前发生的最后一次点击。

用户首次打开相关应用时：

* AppsFlyer可以检测到以下信息：
  * 该应用是否收到由SRN带来的流量。
  * 相关用户是否带有设备ID（Advertising ID）。
* 如果同时符合这两个条件，AppsFlyer就会使用相关设备ID向SRN发出查询请求。
* AppsFlyer在考量SRN的认领响应后得出归因结果。

<div id="install-attribution-examples" />

#### 激活归因示例

<div id="example-a-assisted-attribution" />

<Accordion title="示例A：助攻归因">

<Image align="center" alt="SRN_1.png" src="https://files.readme.io/8e244c99f54b36a4e88b03bf05bb7ca0da2db5c7c601882ea9f68c191c38981b-32259428920337.png" />

**星期一：** 广告平台A上报了一个用户点击。

**星期二：** 广告平台B上报了一个视频交互。

**星期三：** 广告平台C上报了一个可玩广告的点击。在此之后的30分钟，发生了用户激活。

**AppsFlyer**会将此次激活归因到平台C，并为平台A和B各记录一次助攻激活。

AppsFlyer会向广告主提供助攻数据（即在激活之前发生但未获得归因的广告交互）。这些信息可以帮助广告主对自己的多触点（multi-touch）或多分法（fractional）归因模型进行自定义调整。详情请见<Anchor target="_blank" href="/marketers/zh/docs/measure-assisted-installs">助攻激活说明</Anchor>。

</Accordion>

<div id="example-b-last-click-attribution" />

<Accordion title="示例B：末次点击归因">

<Image align="center" alt="SRN_2.png" src="https://files.readme.io/6817d8235acfdbbb5324d07ea8a31ace21cf2306e8e099129d9802e3e0d58b0c-32259457863825.png" />

**广告平台D**（SRN）比广告平台C早几分钟上报了一个点击。

**广告平台C**使用常规的归因对接。

**AppsFlyer**会根据末次点击原则将相关激活归因给平台C。

</Accordion>

<div id="attribution-windows" />

### 归因窗口期

归因窗口期点击型和浏览型回溯窗口。 部分SRN会按CPM（千次展示成本）和CPA（特定行为成本）计价模式向广告主收取激活流量的费用，这些费用是根据1-28天的期限内发生的点击或展示来计算的。

**AppsFlyer**会根据广告主偏好的归因方法论和回溯窗口期对用户的激活和其他行为进行归因，并计算eCPI（和eCPA。

**广告主**可能需要根据SRN的归因回溯窗口和浏览模型未用户激活付费。

* 广告主依靠AppsFlyer的第三方全局归因方法论来优化并合理分配广告消耗。
* 这是因为AppsFlyer会根据广告主设置的条件上报真实的eCPI和eCPA。
* 由于SRN通常会设定自己的计费条款，因此可收获短期利益。但广告主可通过第三方归因服务商来更正计费结果。

<div id="deep-linking-with-srns" />

## 在SRN中使用深度链接

如需让用户点击链接后触发应用调起，您仅需设置App Link、Universal Link或URI scheme即可。但如需通过深度链接或延迟深度链接将用户引导到应用中的特定页面，各SRN会使用自己特有的方法来实现，不涉及AppsFlyer的深度链接方法。

那么要如何通过深度链接在引导用户的同时从SRN获取相关的数据呢？

<div id="direct-deep-linking" />

<Accordion title="直接深度链接">

用户设备平台执行深度链接时，不会调用AppsFlyer的深度链接方法，而是完成SRN的直接深度链接。在下文示例中，点击广告的现有用户会通过Facebook的方法直接跳转到应用内的具体页面，而新用户则会根据AppsFlyer得到的转化数据获得同样的体验。详情请见<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-faq#who-needs-facebooks-sdk">在Meta ads中使用OneLink实现深度链接</Anchor>

<div id="example" />

> 📄 **示例**
>
> Greatapp的移动营销人员Jill决定在Facebook上针对普通用户投放一系列深度链接广告。用户点击这些广告后，会跳转到应用中名为“Bonus”（奖励）的页面。
> 移动端开发人员Jack在获取转化数据后添加以下逻辑：
>
> 1. 流量是否来自Facebook（"is\_fb=true"）？
> 2. 如果该参数的值为true，则抓取广告组参数的值。
> 3. 如果广告组参数的值中包含“Bonus”字样，则让用户进入Bonus页面。

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="延迟深度链接">

与深度链接不同，在SRN中使用的延迟深度链接可以通过AppsFlyer GCD API来实现。  AppsFlyer会接收归因转化数据，并在首次启动时提供给应用程序。对于通过自归因广告平台（SRN）点击深度链接/再营销广告从而安装应用的新用户，广告主也能通过归因转化数据，在app启动时，将用户重定向至app内的指定页面。

Google Ads、Snapchat和TikTok for Business使用实际深度链接值来支持延迟深度链接，您可以在GCD中使用`af_dp`字段进行查询。对于TikTok for Business，您还可以通过`deep_link_value`字段来获取这个值。但在其他SRN中，深度链接数据不包含常规的AppsFlyer深度链接参数。如需在相关应用中使用这些数据，开发人员需要根据可用参数（如广告系列、广告组或单个广告名称等）部署其他逻辑。

**请注意**：在<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-faq#who-needs-facebooks-sdk">Meta ads</Anchor>中，安卓应用可使用Google Install Referrer机制，通过GCD来实现延迟深度链接。对用 iOS 应用，只有对接了 Facebook SDK 的应用才能使用此功能。

</Accordion>

<div id="ios-implications" />

## iOS政策的应对方式

大部分SRN都支持SKAN，并与AppsFlyer做了必要的对接。

<div id="ios-145-srn-attribution" />

<Accordion title="iOS 14.5中的SRN归因方式">

从iOS 14.5开始，如果SRN带来的用户在广告主应用和媒体侧应用中都完成了ATT授权（<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary#dual-consent">即双授权用户</Anchor>），则<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN面板</Anchor>和传统面板中都会显示这些SRN激活。

<div id="note" />

> 📘 **注意**
>
> * 传统面板中归因到SRN的激活会减少。因此在考量SRN的投放表现时，请使用<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN面板</Anchor>中的数据为准。总体而言，归因到SRN的激活数量会有所下降，自然激活也会相应减少。但ATT的限制对高级SRN的影响相对较小，因为这些平台可以在没有设备ID的情况下对广告交互行为进行归因。
> * 用户激活之后，相关数据需要48-73小时才会更新到<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN面板</Anchor>中。
> * SKAN面板中不呈现Apple Search Ads（ASA）带来的激活。

</Accordion>

<div id="sending-event-postbacks-to-srns" />

<Accordion title="向SRN发送事件回传">

SRN在收到事件回传后，需要使用其中包含的设备ID信息，才能对回传中上报的用户行为进行自归因。但大部分iOS 14用户都会选择拒绝数据跟踪，使相关应用无法读取其设备ID（IDFA）。这就会引发以下情况：

* 发送到SRN的事件回传数量减少
* SRN和AppsFlyer之间的事件回传数量存在差异——这是因为AppsFlyer会记录所有事件。

<div id="note-1" />

> 📘 **注意**
>
> * 在没有IDFA的情况下，激活、应用打开或应用内事件的回传不会被发送到SRN。[但在部分场景中，AppsFlyer会在设备ID缺失时仍向SRN发送回传](/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid)。
> * 广告点击平台不受此限制影响，因为这些平台不使用设备ID，而是使用自己的交易ID（transaction ID）根据事件回传中的信息进行自归因。

</Accordion>

<div id="faq" />

## 常见问题解答

<div id="how-does-retargeting-work-with-srns" />

<Accordion title="如何衡量SRN带来的再营销转化？">

非SRN带来的再营销点击可通过再营销归因链接中的`is_retargeting=true`参数来识别，非常方便。  
但SRN中不支持类似的判断方式。这时，AppsFlyer会使用以下逻辑对SRN带来的再互动进行归因：

* 前期准备：
  * 进入**应用配置**页面，打开**启用再营销**的开关。
  * 进入**活跃对接**页面，选择相关SRN并打开**再营销**开关。
* 每当发生应用打开时，AppsFlyer会向该SRN发出请求，查询相关设备ID与该应用的一系列广告最近一次发生交互的信息。
  * 如果该SRN在响应中提供了详细的广告交互信息，AppsFlyer就会验证该次广告交互是否发生在回溯窗口期内，且距离上一次再互动的时间间隔是否超过广告主设置的最短间隔。
  * AppsFlyer会将经验证符合条件的互动行为记录为再互动，并归因到该SRN。

</Accordion>

<div id="what-is-srn-mistargeting" />

<Accordion title="什么是SRN的定向误差？">

SRN应针对特定人群定向投放广告，但无法总是确保定向的准确性，比如可能发生向现有用户投放拉新广告或向非用户投放再营销广告等。

如果您使用同一个SRN同时投放拉新和再营销广告，可能会导致定向误差。这时，您可能会为目标受众以外的流量支付不必要的费用。

**场景：** 您在AppsFlyer平台中启用了某个SRN，用于拉新投放。

* 每当发生应用打开时，AppsFlyer会向该SRN发出查询请求，检查相关用户（以设备ID表示）最近是否完成了广告交互。
* 如果是，
  * SRN会在响应中提供对应的广告系列名称。
  * AppsFlyer会判断该次应用打开是否为首次打开，并进行相应的归因：  
    **首次打开**：记录为新增激活，归因到相应的广告系列。  
    **非首次打开**：记录为再营销事件，归因到相应的广告系列。

**结论：** 如果在投放拉新广告时获得了再营销事件，说明发生了预算浪费。

<div id="is-mistargeting-a-problem" />

#### 定向误差问题大吗？

AppsFlyer的数据分析师考察了某月内Meta ads中的**拉新**广告投放情况。

* 广告主已启用再营销。
* 在30%的广告投放中，至少有15%看到广告的用户是相关应用的现有用户。
* 在5%的广告投放中，至少有40%看到广告的用户是相关应用的现有用户。
* **结论：在SRN的拉新投放中，有10%看到广告的用户是现有用户。**

<Image align="center" alt="mistargeted_users.png" src="https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png" />

<div id="solving-the-mistargeting-problem" />

#### 定向误差的解决方式

**基础解决方案：** 在拉新广告的目标人群中排除所有现有用户。

* SRN仅向潜在的新用户投放广告。
* **在预算不变的前提下充分提升拉新效果**。
* 定期（如每个月）手动更新相关广告系列的投放设置。
* 假设用户在第一个月内激活了应用，则在您更新广告系列之前的这段时间内，这些现有用户可能仍会看到拉新广告。

AppsFlyer提供的高阶付费产品<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide">**受众共享**</Anchor>可每天自动向数十个广告平台发送各类人群包数据，帮助您实现准确的定向投放。

AppsFlyer的研究表明，解决定向误差问题可大幅改善您的营销和获客效果。

</Accordion>

<div id="why-is-the-original-url-field-empty-in-raw-data-reports" />

<Accordion title="原始数据报告中的原始URL字段为何为空？">

用户在SRN环境中点击广告，但这些广告中没有AppsFlyer的归因链接。因此，AppsFlyer就无法获取这类点击的原始URL数据。

</Accordion>

<div id="dashboard-doesnt-show-srn-clicks-and-impressions" />

<Accordion title="面板中没有SRN的点击和展示数据">

用户在SRN环境中点击广告，但这些广告中没有AppsFlyer的归因链接。因此，某些SRN不向AppsFlyer提供点击和展示数据。

<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta ads</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-cost-and-ad-revenue">Google</Anchor>会向AppsFlyer提供部分汇总数据。

</Accordion>

<div id="can-agencies-configure-srn-campaigns" />

<Accordion title="代理是否可以配置SRN中的广告投放？">

是的，详细说明请见<Anchor target="_blank" href="/partners/zh/docs/about-agency-accounts#自归因平台平台">代理的SRN配置说明</Anchor>。

</Accordion>

<div id="does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid" />

<Accordion title="AppsFlyer是否会发送不带设备ID（IDFA/GAID）的回传？">

如果设备ID中包含空字符串（“”）或其值为‘00000000-0000-0000-0000-000000000000’（零值IDFA），AppsFlyer不会发送激活、应用打开或应用内事件的回传，但以下场景除外：

* Google Ads：作为Google Ads再营销衡量对接的一部分，当未授权的iOS用户打开应用或完成应用内事件时，AppsFlyer会向Google Ads发送`gbraid`以及事件信息（用于`additional_data_json`事件）。
* Google Ads：对于安卓应用，在没有设备ID的情况下，如果激活中的referrer值包含`gclid`，或再互动事件中包含带有`gclid`参数的深度链接，AppsFlyer会向Google Ads发送`gclid`以及事件信息。
* Meta：深度链接或先前的再互动中带有Facebook cookie或广告系列ID，或广告主已启用AEM。
* Snapchat和TikTok（高级SRN）：如果AppsFlyer通过PMOD将某个激活归因给Snapchat或TikTok，之后又接收到与该激活相关的应用内事件，这时AppsFlyer会向其发送回传。

**Google Ads**的`gbraid`**参数：** 由Google生成的汇总标识符信息，用于识别设备群组，并会在深度链接中体现该信息。

**Google Click ID（**`gclid`**参数）：** 通过广告点击链接传递的参数，用于识别广告系列以及相关广告的其他点击信息。适用于广告跟踪和投放归因。

</Accordion>

<div id="are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />

<Accordion title="原始数据报告是否显示来自SRN的点击和展示？">

不会，SRN的点击和展示数据不会包含在原始数据报告中。虽然SRN数据可用于归因分析，但原始点击和展示数据不会出现在报告中。这适用于所有SRN，包括TikTok、Snap、Meta 和 Google。

</Accordion>

<div data-zendesk-anchors="srns-integrated-with-appsflyer=%E4%B8%8Eappsflyer%E5%AF%B9%E6%8E%A5%E7%9A%84srn h_01HFM2MET40AFB84AW5N8GKWF3=%E4%B8%8Eappsflyer%E5%AF%B9%E6%8E%A5%E7%9A%84srn attribution=%E5%BD%92%E5%9B%A0 h_01HFM2MET4ZNKEZBT3S74N8CMC=%E5%BD%92%E5%9B%A0 how-does-attribution-work-with-srns=srn%E7%9A%84%E5%BD%92%E5%9B%A0%E5%8E%9F%E7%90%86 h_01HFM2MET42R6C87XB5RWX9ABJ=srn%E7%9A%84%E5%BD%92%E5%9B%A0%E5%8E%9F%E7%90%86 how-does-attribution-work-with-advanced%E2%80%94srns=%E9%AB%98%E7%BA%A7srn%E7%9A%84%E5%BD%92%E5%9B%A0%E5%8E%9F%E7%90%86 h_01HFM2MET4Q6WCSANH18VTGBQX=%E9%AB%98%E7%BA%A7srn%E7%9A%84%E5%BD%92%E5%9B%A0%E5%8E%9F%E7%90%86 install-attribution=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 h_01HFM2MET4YQGN3GZKTTBRQ4HK=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0 install-attribution-examples=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0%E7%A4%BA%E4%BE%8B h_01HFM2MET40Y9V8YGA20CCGVNN=%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0%E7%A4%BA%E4%BE%8B h_01HFM2MET47BP3T07NTRVDWSJ3=example-a-assisted-attribution h_01HFM2MET4FY6SRS534NEA25WV=example-b-last-click-attribution attribution-windows=%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F h_01HFM2MET4ZJF290QNE3TPXQMA=%E5%BD%92%E5%9B%A0%E7%AA%97%E5%8F%A3%E6%9C%9F deep-linking-with-srns=%E5%9C%A8srn%E4%B8%AD%E4%BD%BF%E7%94%A8%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01HFM2MET4ZA6WD6HX92JNFW7X=%E5%9C%A8srn%E4%B8%AD%E4%BD%BF%E7%94%A8%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01HFM2MET4VZX943736W52V0ZJ=direct-deep-linking h_01HFM2MET4HSVHM0Q1C8D5Z279=%E7%A4%BA%E4%BE%8B h_01HFM2MET4WGVMRJW7NJ7TF8GQ=deferred-deep-linking ios-implications=ios%E6%94%BF%E7%AD%96%E7%9A%84%E5%BA%94%E5%AF%B9%E6%96%B9%E5%BC%8F h_01HFM2MET4DGERZJ18A7CEFDS9=ios%E6%94%BF%E7%AD%96%E7%9A%84%E5%BA%94%E5%AF%B9%E6%96%B9%E5%BC%8F h_01HFM2MET4SRX0YRZRMHBY6DKT=ios-145-srn-attribution h_01HFM2MET471M5J2XFE7G2Z6J3=%E6%B3%A8%E6%84%8F h_01HFM2MET42KNAMWE9S9BSF4PK=sending-event-postbacks-to-srns h_01HFM2MET4WJ6TMTXM03NFFCAG=%E6%B3%A8%E6%84%8F-1 faq=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HFM2MET49FZ8QHDMA7H92BTE=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HFM2MET4VYGPWR98HMAWK4YP=how-does-retargeting-work-with-srns h_01HFM2MET4JGYTW6P1VGYMYGFS=what-is-srn-mistargeting is-mistargeting-a-problem=%E5%AE%9A%E5%90%91%E8%AF%AF%E5%B7%AE%E9%97%AE%E9%A2%98%E5%A4%A7%E5%90%97 h_01HFM2MET4C1HMWH715XP42ZAQ=%E5%AE%9A%E5%90%91%E8%AF%AF%E5%B7%AE%E9%97%AE%E9%A2%98%E5%A4%A7%E5%90%97 solving-the-mistargeting-problem=%E5%AE%9A%E5%90%91%E8%AF%AF%E5%B7%AE%E7%9A%84%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F h_01HFM2MET41CDCP8VNGR39YMCK=%E5%AE%9A%E5%90%91%E8%AF%AF%E5%B7%AE%E7%9A%84%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F h_01HFM2MET4DETEHT8PACHS6C6B=why-is-the-original-url-field-empty-in-raw-data-reports h_01HFM2MET48Y4ATGB1HNDGSFEP=dashboard-doesnt-show-srn-clicks-and-impressions h_01HFM2MET4JEA8BBGN564CQPYX=can-agencies-configure-srn-campaigns h_01HFM2MET42V7AVV2BPZGDRARV=does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid h_01JMJ79S862T4M96ECZPVRZVJJ=are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />

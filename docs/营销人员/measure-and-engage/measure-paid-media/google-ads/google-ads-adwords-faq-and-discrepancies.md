---
title: Google Ads（AdWords）— 常见问题及数据差异
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T10:06:31Z'
  edited_at: '2026-10-14T10:07:32Z'
  id: 4417303339921
  locale: zh-cn
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/zh-cn/articles/4417303339921
---
> **概要：概要：本文将帮助您排查Google Ads相关的常见问题以及数据差异。**

## Google Ads常见问题解答

<div id="why-am-i-not-seeing-clicks-from-google-ads" />

<Accordion title="为什么我没有看到来自Google Ads的点击？">

您需要在<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">成本</Anchor>选项卡中**确认收集成本、点击和展示数据**后才能看到来自Google Ads的汇总点击和展示数据。

Google Ads的点击和展示数据于2018年8月发布，先用于Android应用，后来用于iOS应用。因此，在分析2018年及之前的点击数据时，Google Ads点击数据可能会丢失或不完整。

</Accordion>

<div id="why-am-i-not-seeing-first_open-conversions-on-google-ads" />

<Accordion title="为什么我在Google Ads上看不到first_open转化">

如果您在Google Ads上看不到如下所示的first\_open转化：

![AW_13.png](https://files.readme.io/082f79266fced9fc012cdb373321a836129205992adbe29f7509321516e8f5ab-33743114088849.png)

这表示您需要在Google Ads中导入转化，具体操作请参考<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">导入转化指南</Anchor>。

</Accordion>

<div id="why-don-t-i-see-installs-from-google-ads" />

<Accordion title="为什么我看不到来自 Google Ads 的安装？">

按照此检查清单排查缺失的安装：

#### 快速修复

1. **在 AppsFlyer 中激活 Google Ads**  
   在 AppsFlyer 中，从侧边栏打开 **协作 > 活跃集成**，搜索 **Google Ads**，并确认集成已激活。
2. **在 Google Ads 中导入**`first_open` **转换**  
   在 Google Ads 中，转到 <Anchor target="_blank" href="https://ads.google.com/aw/conversions">转换摘要</Anchor> 页面，确保 `first_open` 转换事件已被导入。有关更多信息，请参见 导入您的应用转换。

#### 仍然无法正常工作？

1. **检查哪个 Google Ads 账户导入了转换**  
   确定 **Google Ads MCC 账户或子账户** 是否负责导入转换：

   * **如果使用 MCC（管理账户）：** MCC 应代表所有链接的子账户导入 `first_open` 转换。
   * **如果使用子账户：**
     * MCC 必须 **与子账户共享链接 ID**。
     * 子账户必须 **直接导入**`first_open` **转换**。

   有关 Google Ads MCC 账户的更多信息，请参见：MCC
2. **检查已移除的**`first_open` **转换**  
   在 <Anchor target="_blank" href="https://ads.google.com/aw/conversions">转换摘要</Anchor> 页面，检查 `first_open` 转换事件是否已被移除。如果已移除，请联系 **Google 支持** 寻求帮助。
3. **确认链接ID**  
   确保AppsFlyer中的链接ID与Google Ads中的链接ID匹配。

</Accordion>

<div id="why-dont-i-see-inapp-events-in-the-google-ads-dashboard" />

<Accordion title="为什么我在Google Ads仪表板中看不到应用内事件？">

使用此检查清单确保您的应用内事件在AppsFlyer和Google Ads之间正确设置和同步。

#### 快速修复检查清单

按照以下步骤快速解决最常见的问题：

1. **验证AppsFlyer中的事件回传**（有关逐步说明，请参见<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended">在AppsFlyer上设置Google Ads。</Anchor>）
   1. 前往AppsFlyer中的**Google Ads集成标签**。
   2. 确保为每个您想要测量的应用内事件正确配置回传。
   3. 在<strong>来自</strong>下，选择<em>所有媒体来源，包括自然流量，</em>以确保Google Ads接收事件数据。
   4. （可选）初始设置后，如有需要，调整此选择以适应特定事件。
2. **触发测试应用内事件**
   1. 启动您的应用。
   2. 对于iOS应用，确保通过允许应用跟踪来启用IDFA收集。
   3. 手动执行映射的应用内事件（例如，购买或注册）。
3. **在Google Ads中导入事件**
   1. 在Google Ads中，点击**工具 转换**。
   2. 检查**转换操作摘要**。
   3. 导入相关的应用内事件。有关更多信息，请参见导入您的应用转换。

      > 📘 **注意**
      >
      > 转换可能需要最多6小时才能在事件执行后显示。


#### 仍然无法正常工作？

如果您在Google Ads中修改了合作伙伴事件标识符（例如，如果它标记为`CUSTOM`）并更改了AppsFlyer中的相应事件名称，则需要将事件重新导入Google Ads。

</Accordion>

<div id="can-i-stop-google-cost-sync" />

<Accordion title="可以停止同步Google成本吗？">

关闭Google成本同步的方式如下：

1. 进入<Anchor target="_blank" href="https://myaccount.google.com/permissions">Google Account Permissions</Anchor>（帐户权限）部分。
2. 点击“AppsFlyer Google Cost”旁边的“Remove”（移除）按钮。  
   ![remove_appsflyer_cost.png](https://files.readme.io/56840e708c98875c8db176c642dd324150a76aef9697fcc2756f524b2a6c0a16-33743128661137.png)

</Accordion>

<div id="do-i-need-to-create-and-then-import-session_start" />

<Accordion title="是否需要先创建然后再导入session_start？">

这取决于正在运行的广告系列类型。如果您正在投放重新再互动广告系列，则建议您创建并导入`session_start` session\_start session\_start来衡量互动度。

如果您投放的是拉新广告，则不一定需要完成此操作。

</Accordion>

<div id="can-i-send-uninstall-information-to-google-ads" />

<Accordion title="我可以将卸载信息发送到Google Ads吗？">

是  
是。 **要开始向Google发送卸载事件：**

1. 将af\_uninstall事件映射为Google Ads设置窗口中的自定义事件。
2. 在Google中导入该转化。
3. Google会确认事件如果在Google的归因窗口中收到（从广告互动开始，持续30-90天）。窗口结束后Google收到的事件不会记录在Google中。

</Accordion>

<div id="what-google-ads-data-does-appsflyer-display" />

<Accordion title="AppsFlyer如何呈现Google Ads的数据？">

AppsFlyer按以下几个层级呈现数据：广告系列、流量入口、广告组和地理位置。

</Accordion>

<div id="do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data" />

<Accordion title="我是否需要配置什么内容以便在Google Ads 中创建基于AppsFlyer数据的受众列表？">

不需要，Google会根据您的应用内事件配置在Google API中设置相关信息。

</Accordion>

<div id="im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard" />

<Accordion title="我投放了一个App Campaign（应用广告），但在AppsFlyer和Google Ads面板中看不到相关数据及转化事件，这是为什么？">

您很可能还没有导入事件。请参考<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">此文档</Anchor>，了解如何导入事件。

</Accordion>

<div id="what-do-i-do-if-there-are-multiple-accounts" />

<Accordion title="如果有多个帐户怎么办？">

在AppsFlyer中使用多个Google Ads账户是没有问题的。AppsFlyer 仅使用一个Link ID。因此，Google Ads中只要生成一个Link ID并在多个帐户之间分享即可。请点击<Anchor target="_blank" href="https://support.google.com/google-ads/answer/3030657">此链接</Anchor>查看详情。

</Accordion>

<div id="what-happens-with-link-ids-created-at-mcc-level-vs-account-level" />

<Accordion title="MCC级别的Link ID和帐户级别的Link ID在AppsFlyer中有什么区别？">

AppsFlyer支持MCC或帐户级别的Link ID。我们建议您与Google Ads 的账户经理密切合作，以确保您的帐户结构配置正确。请点击<Anchor target="_blank" href="/marketers/zh/docs/recording-multiple-agency-mcc-google-ads-accounts">此链接</Anchor>查看详情。

</Accordion>

<div id="what-is-parallel-tracking" />

<Accordion title="什么是并行追踪？">

Google Ads的并行追踪使您的落地页加载速度更快，从而减少访问丢失的问题。因此，转化数会增加，广告效果会提高。借助并行跟踪，可以在把用户发送到归因链接前直接把用户从广告端发送到最终URL，此时，点击测量正在后台运行。

关于Parallel Tracking的完整说明，请点击<Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">这里</Anchor> 。

#### 如何操作？

为了保证并行追踪（Parallel tracking）能正常生效，跳转终点的URL必须与Google Ads广告链接（Campaign URL）中的网址一致，且该网址必须设置在<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en">Google的 ValueTrack参数</Anchor>中。

具体的操作方法如下：

* 使用单平台归因链接（不推荐）
  * 链接中必须包含af\_r参数
* 使用<Anchor target="_blank" href="/marketers/zh/docs/understand-onelink-short-vs-long-urls">OneLink长链</Anchor>（推荐）
  * 在广告链接中添加下列链接参数
    * af\_android\_url
    * af\_ios\_url
    * af\_web\_dp
  * 切勿使用af\_dp
  * 在Google的ValueTrack参数中添加跳转终点URL。<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en#urlinsertion&zippy=%2Ctracking-template-only">详情请见此处说明。</Anchor>

示例：

```
https://subdomain.onelink.me/template_id?pid=xxx&af_ios_url={lpurl}
&af_android_url={lpurl}&af_web_dp={lpurl}
```

注意：[请注意：](https://support.google.com/google-ads/answer/6305348?hl=en&sjid=12409212435602417786-AP#zippy=%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-campaign-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-ad-group-level%2Cfinal-url-tracking-template-or-custom-parameter)如需了解所有可用参数，请见此文档。

如需进一步了解如何配置带有并行追踪的Google Ads网页广告系列，请点击此处。

</Accordion>

<div id="how-do-you-configure-a-campaign-with-android-or-ios-configuration" />

<Accordion title="如何为安卓或iOS应用配置广告投放？">

> 🚧 **重要提示！**
>
> AppsFlyer支持所有的Google Ads广告系列。
>
> 谷歌是一个SRN (自归因渠道)。更多关于这类平台的归因信息，请<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">点击此处</Anchor>。
>
> 也就是说，AppsFlyer可以呈现Google提供的所有投放信息。Search（搜索广告）、Video（视频广告）、Display（展示广告）、Re-engagement（再互动广告）等广告系列类型以及相关信息由Google提供。建议您配置App Campaign类广告系列。如需了解其他广告系列类型，请联系您的Google客户经理。广告系列说明请见<Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">此文档</Anchor>。

<div id="android-configuration-for-google-ads" />

<Accordion title="适用于Google Ads的Android配置">

为了进行Android应用归因，请确保您的应用支持GAID（Google广告ID）收集，并通过SDK将该值传递给AppsFlyer。

#### 创建转化记录（激活）

有关创建转化记录的详细说明，请见<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">此文档</Anchor>。

<span id="inapp_events"></span>Google Ads - 安卓配置 - 发送应用内事件

如果您想进一步衡量Google移动应用安装广告系列在Google中的成功程度，则可以从AppsFlyer帐户向您的Google Ads帐户发送应用内事件。

#### 创建转化（应用内事件）

有关如何衡量应用转化的详细信息，请点击<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">这里</Anchor> 。

</Accordion>

<div id="ios-configuration-for-google-ads" />

<Accordion title="Google Ads的iOS配置">

#### Google Ads — iOS配置：App Campaign类广告系列

投放App Campaign类广告可以一次性配置Google Search（搜索广告）、YouTube、Display（展示广告）等多种广告形式，用于推广您的iOS应用。

一般情况下，点击来自移动网络渠道，因此Google Ads本身无法从搜索广告系列中自归因iOS安装，进而使得Google无法获取设备IDFA进行ID匹配。

反之，对于在**Google Search App**上投放的广告，Google Ads就可以对App Campaign带来的iOS搜索进行归因。

#### 创建转换记录（激活）

有关创建转化记录的详细说明，请见<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">此文档</Anchor>。

#### Google Ads - iOS配置 - 发送应用内事件

如果您想进一步衡量Google移动应用安装广告系列在Google中的成功程度，则可以从AppsFlyer帐户向您的Google Ads帐户发送应用内事件。

#### 创建转化（应用内事件）

有关如何衡量应用转化的详细信息，请点击<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">这里</Anchor> 。

</Accordion>

</Accordion>

<div id="for-how-long-do-you-keep-google-ads--userlevel-data" />

<Accordion title="Google Ads的用户级数据会在AF中保留多长时间？">

Google Ads要求归因提供商在安装后6个月内删除其用户级数据。这意味着这些用户在安装应用6个月后触发的事件会被算为自然事件。

历史汇总数据保持不变。

这与所有Google Ads渠道有关。

</Accordion>

## Google Ads的数据差异

Google Ads面板和AppsFlyer面板之间有时会出现数据差异。

尽管我们与Google Ads紧密合作以最大程度地减少数据差异，但广告主仍应注意以下原因：

#### 同时适用于iOS和安卓的数据差异

| **原因** | **Google Ads** | **AppsFlyer** |
| --- | --- | --- |
| **建模转换和ICM转换** | Google Ads显示由Google内部建模生成的建模安装，而不显示基于ICM的建模安装。 | AppsFlyer显示由Google ICM（概率声明）生成的建模安装，而不显示Google内部建模的安装。 |
| **助攻激活（即多触点归因）** | Google Ads 作为一个SRN（自归因）平台，会把所有在其归因窗口期内的与Google Ads互动过的全部安装都归因给他们自己。 | AppsFlyer只会把安装归因给最后一次点击，并将最后一次点击之前的广告互动记为<Anchor target="_blank" href="/marketers/zh/docs/measure-assisted-installs">辅助激活</Anchor> 。 |
| **激活记录日期** | Google Ads将点击时间记为转化时间。 | AppsFlyer将应用首次启动时间（应用打开）归因为转化时间。 |
| **时区** | 取决于地理位置 | 取决于地理位置 |
| **归因窗口** | 30天 | Google集成默认设置为30天（可以修改）。 |
| **浏览型转化** | 仅**所有转化**一栏显示浏览型转化，**转化**栏不显示，除非在Google Ads中另有设置。 | AppsFlyer显示总激活数量，点击型激活和浏览型激活。 |
| **重装激活** | Google Ads将重装激活作为session\_start转化呈现。 | AppsFlyer会把再次安装记为再安装（即再归因）作为再营销数据的一部分。 |
| **应用内事件** | Google Ads将点击时间归因为应用内事件时间。 | 在AppsFlyer面板中，应用内事件是根据安装时间归因的。在原始数据报告中，AppsFlyer根据应用内事件时间归因。 |
| **验证规则** | 无论验证规则如何，Google都会从AppsFlyer接收所有信息。 | AppsFlyer可能会根据相关的验证规则剔除一部分激活。 |
| **成本 - Google Ads流量入口** | 针对具体的广告系列，Google会上报所有流量入口（YouTube、展示广告和搜索广告）的相关成本。 | AppsFlyer会从Google获取广告系列所有渠道的成本数据，但只能归因YouTube和展示广告带来的iOS AC转化。因此，AppsFlyer显示的总体CPI更高。 |
| **SKAN安装** | 从Google Ads API V10+开始，Google Ads面板不再区分did\_win=TRUE和did\_win=NULL的激活，这两种激活仅在原始数据中有所区分。 | 从Google Ads API V10+开始，AppsFlyer仅展示回传中带有did\_win=TRUE的激活。因此AppsFlyer中呈现的激活数量可能会比Google Ads低。 |
| **first\_open events** | Google Ads从Firebase获取事件，其中DMA正确实施，随后声明DMA同意的事件。 | Google Ads还从AppsFlyer获取相同的事件，其中DMA实施不正确，导致所有事件被报告为非DMA同意，Google不予声明。<ul><li>要检查DMA是否正确实施，<Anchor target="_blank" href="/marketers/zh/docs/raw-data-export-page#download-report">下载原始数据报告</Anchor>并关注<Anchor target="_blank" href="/marketers/zh/docs/bulletin-dma-support-in-raw-data-reports">本公告</Anchor>中指定的字段。</li><li>请参见[开发者中心](https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance)以了解如何在SDK中实施DMA。</li></ul> |
| **重定向事件** | Google Ads可以在响应中声明与`ad_type=ClickToDownload`的重新参与。 | AppsFlyer将`ad_type=ClickToDownload`计为UA转换事件，而不是重新参与。因此，AppsFlyer中的重新参与数量可能会更低。 |

> 📘 **说明**
>
> * Google Ads会在后台集中显示某个再营销广告系列产生的所有激活，而AppsFlyer的数据总览面板会分UA、再营销和统一视图分别显示新增激活、再归因以及两者相结合的数据。
> * 在比较Google Ads和AppsFlyer的数据时，请确保Google Ads面板的数据是从第三方分析平台（AppsFlyer）导入的数据。从Firebase或Google Play导入的数据结构与AppsFlyer不同，因此无法进行全面的对比。如需了解如何将数据从AppsFlyer导入到Google Ads面板，请参考<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">此文档</Anchor>。
> * 要比较安装事件（在Google Ads中为first\_open），请确保在Google Ads的转化报告中分层查看安装事件。Google Ads可能会显示所有转化（可能是安装、购买、订阅），这就是为什么仅从所有转化事件中选择安装事件的重要原因。

> 📄 **相关文档**
>
> * 请参考<Anchor target="_blank" href="/marketers/zh/docs/get-skan-postback-data-from-google-ads">Google Ads与AppsFlyer的SKAN互动设置</Anchor>，了解iOS 14的相关注意事项。

<div data-zendesk-anchors="google-ads-faq=google-ads%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HA1SM7D91QPG17WH752FBAFT=google-ads%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HA1SM7D9JWBEPNE0E8FE665E=why-am-i-not-seeing-clicks-from-google-ads h_01HA1SM7DAW984PPRGHXA5BYSX=why-am-i-not-seeing-first_open-conversions-on-google-ads why-don%E2%80%99t-i-see-installs-from-google-ads=why-don-t-i-see-installs-from-google-ads h_01K5DZBDMS0D2S5XYDC22WQ19H=why-don-t-i-see-installs-from-google-ads quick-fix=%E5%BF%AB%E9%80%9F%E4%BF%AE%E5%A4%8D h_01K5DZBDMSBDKAFHVVPYD6YKRK=%E5%BF%AB%E9%80%9F%E4%BF%AE%E5%A4%8D still-not-working=%E4%BB%8D%E7%84%B6%E6%97%A0%E6%B3%95%E6%AD%A3%E5%B8%B8%E5%B7%A5%E4%BD%9C h_01K5DZBDMSVTE6M2J235ST85DE=%E4%BB%8D%E7%84%B6%E6%97%A0%E6%B3%95%E6%AD%A3%E5%B8%B8%E5%B7%A5%E4%BD%9C h_01K7NT8FVC3K3861WN9VKRZ2HB=why-dont-i-see-inapp-events-in-the-google-ads-dashboard quick-fix-checklist=%E5%BF%AB%E9%80%9F%E4%BF%AE%E5%A4%8D%E6%A3%80%E6%9F%A5%E6%B8%85%E5%8D%95 h_01K7NT8FVC1T557GPG7ZCYX33J=%E5%BF%AB%E9%80%9F%E4%BF%AE%E5%A4%8D%E6%A3%80%E6%9F%A5%E6%B8%85%E5%8D%95 h_01K7PAH7VDS7NGW6R6HERGXK9H=%E6%B3%A8%E6%84%8F still-not-working::77f3165b=%E4%BB%8D%E7%84%B6%E6%97%A0%E6%B3%95%E6%AD%A3%E5%B8%B8%E5%B7%A5%E4%BD%9C-1 h_01K7NT8FVCD4DNFKP3DS75ZKR0=%E4%BB%8D%E7%84%B6%E6%97%A0%E6%B3%95%E6%AD%A3%E5%B8%B8%E5%B7%A5%E4%BD%9C-1 h_01HA1SM7DACQDVGWGKV5MZ63D6=can-i-stop-google-cost-sync h_01HA1SM7DA415FQP3MFC09AE3Y=do-i-need-to-create-and-then-import-session_start h_01HA1SM7DAEKGVPDTX77RJ9Y37=can-i-send-uninstall-information-to-google-ads h_01HA1SM7DAKKVZ82WF6RVEDHE9=what-google-ads-data-does-appsflyer-display h_01HA1SM7DANYQ0DAY54CH4HPV4=do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data h_01HA1SM7DA3XF8NBGYGZ0XTB69=im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard h_01HA1SM7DAY7JNTFSG86A1QGKC=what-do-i-do-if-there-are-multiple-accounts h_01HA1SM7DAYSVMENT91T2BE26Z=what-happens-with-link-ids-created-at-mcc-level-vs-account-level h_01HA1SM7DAK186BRZN970PKPRM=what-is-parallel-tracking additional-information=%E5%A6%82%E4%BD%95%E6%93%8D%E4%BD%9C h_01HA1SM7DAMNG8X22VNWMKBJ8R=%E5%A6%82%E4%BD%95%E6%93%8D%E4%BD%9C h_01HA1SM7DBNAS6DP8G9D8KFHPW=how-do-you-configure-a-campaign-with-android-or-ios-configuration h_01HA1SM7DB16T3RGBVGT5Z9REW=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HA1SM7DBC38CY8AN3EPMMJFW=android-configuration-for-google-ads creating-conversion-recording-installs=%E5%88%9B%E5%BB%BA%E8%BD%AC%E5%8C%96%E8%AE%B0%E5%BD%95%E6%BF%80%E6%B4%BB h_01HA1SM7DBF9KDRNEV25KJHGHN=%E5%88%9B%E5%BB%BA%E8%BD%AC%E5%8C%96%E8%AE%B0%E5%BD%95%E6%BF%80%E6%B4%BB create-a-conversion-inapp-events=%E5%88%9B%E5%BB%BA%E8%BD%AC%E5%8C%96%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HA1SM7DBDQVNDQ5GG7X2PJ8K=%E5%88%9B%E5%BB%BA%E8%BD%AC%E5%8C%96%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HA1SM7DBKKQ9R8MQMQT9GRXV=ios-configuration-for-google-ads google-ads-ios-configuration-app-campaigns=google-ads--ios%E9%85%8D%E7%BD%AEapp-campaign%E7%B1%BB%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 h_01HA1SM7DBNSDFCJA5BP59MMQ2=google-ads--ios%E9%85%8D%E7%BD%AEapp-campaign%E7%B1%BB%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 creating-conversion-recording-installs::6a56eb4b=%E5%88%9B%E5%BB%BA%E8%BD%AC%E6%8D%A2%E8%AE%B0%E5%BD%95%E6%BF%80%E6%B4%BB h_01HA1SM7DBXCT0NS4W50D4ZGEK=%E5%88%9B%E5%BB%BA%E8%BD%AC%E6%8D%A2%E8%AE%B0%E5%BD%95%E6%BF%80%E6%B4%BB google-ads-ios-configuration-sending-inapp-events=google-ads---ios%E9%85%8D%E7%BD%AE---%E5%8F%91%E9%80%81%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HA1SM7DBEV9CJTAB5YHRJHYK=google-ads---ios%E9%85%8D%E7%BD%AE---%E5%8F%91%E9%80%81%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 creating-a-conversion-inapp-events=%E5%88%9B%E5%BB%BA%E8%BD%AC%E5%8C%96%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6-1 h_01HA1SM7DBCQYSJ3R67F0856QK=%E5%88%9B%E5%BB%BA%E8%BD%AC%E5%8C%96%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6-1 for-how-long-do-you-keep-google-ads%E2%80%99-userlevel-data=for-how-long-do-you-keep-google-ads--userlevel-data h_01HA1SM7DBFAAV7C4ENA34B7JP=for-how-long-do-you-keep-google-ads--userlevel-data google-ads-discrepancies=google-ads%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 h_01HA1SM7DBA7KK1DXFCE2G0QTP=google-ads%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 both-ios-and-android=%E5%90%8C%E6%97%B6%E9%80%82%E7%94%A8%E4%BA%8Eios%E5%92%8C%E5%AE%89%E5%8D%93%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 h_01HA1SM7DB18BTDKK5BK4949HX=%E5%90%8C%E6%97%B6%E9%80%82%E7%94%A8%E4%BA%8Eios%E5%92%8C%E5%AE%89%E5%8D%93%E7%9A%84%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 h_01HA1SM7DBSTAREA36YWRRRG82=%E8%AF%B4%E6%98%8E h_01HDP2XBSEJVQ5G0MD0V5R05CM=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

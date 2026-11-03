---
title: Meta ads常见问题解答
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
  created_at: '2021-11-09T10:04:49Z'
  edited_at: '2026-10-14T10:10:01Z'
  id: 4410472805649
  locale: zh-cn
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410472805649
---
> **概要：** 本文主要解答了广告主在AppsFlyer中使用Meta ads时经常会碰到的一些问题。

## Meta ads常见问题解答

<div id="i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard" />

<Accordion title="为什么在AppsFlyer面板上看不到Meta ads广告系列的点击？">

默认情况下，Meta ads仅发送转化和互动数据。但要<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-integration-setup#cost-clicks-and-impressions">获取Meta ads投放的点击、展示和成本数据</Anchor>也很容易。

</Accordion>

<div id="can-appsflyer-show-the-campaign-level-and-ad-groups" />

<Accordion title="AppsFlyer可以显示广告系列级别和广告组吗？">

安全。AppsFlyer还可以呈现广告级别的数据。也就是说，您可以在Meta ads下按广告系列>>广告组>>广告3个维度逐层切入查看数据。

</Accordion>

<div id="is-facebook-data-shown-in-realtime" />

<Accordion title="AppsFlyer中的Meta ads数据是实时的吗？">

是的，所有激活和后续的应用内事件均实时显示。但是，AppsFlyer仅能获取汇总的Meta ads点展消数据，这些汇总数据是每隔几个小时定时发送的，因此不能实时显示在AF后台。

</Accordion>

<div id="when-can-i-see-a-new-campaigns-data-on-appsflyer" />

<Accordion title="我什么时候可以在AppsFlyer上看到新广告系列的数据？">

在Meta ads上投放的广告、广告组和广告系列只有在带来激活之后才能被AppsFlyer记录到。

假设您新投了两则广告，其中一则广告产生了100次点击，但是没有带来任何激活，该广告就不会显示在AppsFlyer面板或报告中。另一则广告只有1次点击和1次安装，却会显示在AppsFlyer上。

</Accordion>

<div id="how-can-i-get-more-installs-from-facebook" />

<Accordion title="如何充分利用Meta ads拉动更多激活？">

如果您启用了Meta ads的再营销，就能免费让拉新广告的激活数翻一倍！  
详情请见<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#what-is-srn-mistargeting">此文档</Anchor>。

</Accordion>

<div id="how-can-i-get-device-level" />

<Accordion title="我如何使用Google Play和Meta安装引用获取设备级Android安装数据？">

#### Google Play Install Referrer API

Google Play安装引用API允许广告商检索来自Google Play商店的安装的归因数据，例如活动信息。此API必须<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">集成到您的应用中</Anchor>，并通过在安装后首次打开应用时传递引用数据来工作。在提交所需的解密密钥后，归因字段将在AppsFlyer原始数据报告中以匹配类型`gp_referrer`可用。

#### Meta install referrer

Meta安装引用提供存储在设备本地的额外活动元数据。这可以通过[AppsFlyer SDK](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer)访问。它通过启用更丰富的数据（包括点击和展示数据）来补充Google Play安装引用，并可能跨多个会话。通过Meta安装引用的归因使用匹配类型，如`fb_referrer`（Facebook）和`ig_referrer`（Instagram）。

#### 活动归因字段

* Ad ID
* Ad name（广告名称）
* Adset ID（广告组 ID）
* Adset name（广告组名称）
* 广告系列 ID
* Campaign name（广告系列名称）
* Account ID（账户ID）
* Channel（流量入口）

#### SDK和设置说明

* Google Play引用数据需要AppsFlyer SDK版本5.4.0及以上。
* Meta引用支持取决于正确的SDK配置。请参见<Anchor target="_blank" href="/marketers/zh/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">此公告</Anchor>以获取实施细节。

#### 提交解密密钥

两种引用类型都需要来自您的Meta开发者帐户的解密密钥。您只需为每个应用提供一次此密钥。步骤包括：

1. 登录Meta开发者平台。
2. 导航到**我的应用**并选择相关应用。
3. 转到**设置 > 基本**并找到"安装引用解密密钥。"
4. 在 AppsFlyer 中，导航到 **协作 > 活跃集成 > Meta 广告**。
5. 将密钥粘贴到 **安装引用解密密钥** 字段中并保存。

</Accordion>

<div id="do-you-make-facebook-raw-data-available-to-agencies" />

<Accordion title="代理可以获取Meta ads的原始数据吗？">

不提供。AF不能向代理提供Meta ads的原始数据，这是因为Meta的服务条款中将代理商界定为第三方。

</Accordion>

<div id="i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports" />

<Accordion title="激活和应用内事件报告中没有Meta ads原始数据">

默认情况下，Meta 广告不允许分发带有无限制归因信息的设备级数据。但是，如果您接受 Meta 高级移动测量 (AMM) 条款，您将能够无障碍访问 Meta 广告的设备级归因数据。启用Meta广告设备层级数据

</Accordion>

<div id="any-specific-columns-for-facebook-in-appsflyers-performance-reports" />

<Accordion title="AppsFlyer的效果报告中是否有Meta ads的专用字段？">

安全。无论您在效果报告中选择哪些媒体渠道的组合，报告的字段结构都是不变的，其中的数据可一直细分到广告系列层级。  
但是如果您仅选择Meta ads，AppsFlyer就会在报告中添加4个字段，其中包含的信息可一直深入到广告级别。新增的列包括广告组名称、广告组 ID、广告组（即单个广告）名称和广告组 ID。

[![](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)

</Accordion>

<div id="can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer" />

<Accordion title="我可以使用AppsFlyer来衡量Meta投放管理合作平台的投放效果吗？">

可以。AppsFlyer已与数十个Meta投放管理合作平台形成对接，您可以在AF面板的“活跃对接”页中启用并设置这些渠道的归因。

如需进一步了解Meta投放管理合作平台的归因设置，请点击<Anchor target="_blank" href="/marketers/zh/docs/configuring-meta-campaign-management-partners">此处</Anchor>。

</Accordion>

<div id="what-should-i-do-when-i-receive-the-following-warning" />

<Accordion title="收到以下警告时该怎么办？">

[![](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)

* 请检查您的FacebookApp ID是否正确无误，并检查该ID是否受地理或年龄限制。
* 如果归因已正常生效，就表示该应用已在Meta Developer Portal中上架，您可以忽略上述报错消息。

</Accordion>

<div id="what-happens-with-different-lookback-windows-than-on-facebook" />

<Accordion title="如果在AF中使用的归因窗口期与Meta ads不同会发生什么情况？">

Meta ads中默认的点击归因窗口期是7天，浏览归因窗口期是1天，这也是Meta ads中最长的可用窗口期。

在 AppsFlyer 上配置较短的窗口会减少 Meta 广告在 AppsFlyer 上的归因。相反，在 AppsFlyer 上配置较长的窗口会导致 AppsFlyer 侧的归因多于 Meta 侧。

因此，为了尽量减少数据差异，建议您在AppsFlyer中为Meta ads设置点击7天、浏览1天的回溯窗口。

</Accordion>

<div id="what-are-the-facebook-api-parameters" />

<Accordion title="哪些是Meta API中的专用参数？">

为了确保向后兼容，部分AppsFlyer API中的Meta参数名称与面板上显示的名称有所不同。具体请见下表：

| 转化数据 | AppsFlyer原始数据 | Meta |
| --- | --- | --- |
| campaign | campaign | campaign\_group\_name |
| campaign\_id | Campaign ID | campaign\_group\_id |
| adgroup | Ad | adgroup\_name |
| adgroup\_id | Ad ID | adgroup\_id |
| adset | Adset | campaign\_name |
| adset\_id | Adset ID（广告组 ID） | campaign\_id |
| agency | Partner | N/A |
| is\_fb | Media Source | is\_fb |
| af\_channel | Channel | publisher\_platform |
| af\_siteid | Site ID（子渠道ID） | 当`publisher_platform`值不等于`facebook` else `null`时，Publisher\_platform。 |

</Accordion>

<div id="how-long-do-you-keep-facebook-s-userlevel-data" />

<Accordion title="Meta ads的用户级数据会在AF中保留多长时间？">

Meta ads要求归因服务商在用户激活应用后的6个月内删除其设备级数据。6个月后用户产生的事件将被视为自然行为，  
但历史汇总数据不受影响。  
上述规则适用于所有的Meta ads流量入口（Facebook应用、Instagram、Messenger和AudienceNetwork）。

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-meta-ads" />

<Accordion title="Meta Ads是否支持iOS Universal Link和Android App Link？">

Meta Ads支持iOS Universal Link和Android App Link，可以在该平台中使用。详情请见<Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">Meta帮助中心</Anchor>。

* 对于静态广告（非catalog），仅在跳转终点设为**App**的广告系列中支持iOS Universal Link和Android App Link。
* 对于动态广告，您可以按照[这部分](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads)的说明使用iOS Universal Link、Android App Link和URI scheme。

**请注意：** iOS Universal Link和Android App Link仅可在付费广告中使用。

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content" />

<Accordion title="Meta 的非付费内容是否支持 iOS 通用链接和 Android 应用链接？">

iOS Universal Link和Android App Link仅可在付费广告中使用。在非付费社交应用内容中，可能需要设置社交应用着陆页或 URI 方案以重定向或深度链接用户。

</Accordion>

<div id="aem-attribution-is-not-working" />

<Accordion title="AEM归因未生效">

如果**高级数据共享**开关一打开，但您未收到Meta的归因数据，请检查这些事件是否符合Meta的共享标准。详情请见[Meta提供的说明文档](https://www.facebook.com/business/help/716239976391518?id=1877298665783613)。

</Accordion>

<div id="can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads" />

<Accordion title="可以在动态产品广告中使用OneLink打开应用并进行深度链接吗？">

可以。配置了应用链接、通用链接或 URI 方案的 OneLink 链接在动态产品广告中受支持。您可以在数据源中使用 OneLink 链接，用于动态广告中在 **applink.ios\_url** 和 **applink.android\_url** 字段.中使用的目录。

</Accordion>

<div id="conversion-events-are-not-sent-to-meta-ads" />

<Accordion title="转换事件不会发送到 Meta 广告。">

您可能处于不包括归因的零套餐中。

</Accordion>

<div id="can-i-use-get" />

<Accordion title="能否使用Get Conversion Data（GCD）从Meta拉取转化数据？">

<strong>支持。</strong>您可以继续使用**GCD**从Meta拉取转化数据，具体取决于您的应用配置和AMM协议状态：

* **如果您的应用中接入了Facebook SDK：**

  如<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#deferred-deep-linking">延迟深度链接（DDL</Anchor>）文档中所述，您可以通过GCD获取并使用DDL数据。
* **如果您的应用中未接入Facebook SDK：**

  您仍可以通过GCD拉取**广告系列、广告**组和广告名称，但需要<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions#meta-ads">签署高级</Anchor>移动衡量（AMM）。在这种情况下，您可以使用这些值来应用您自己的**自定义深度链接逻辑**。

> 📘 **注意**
>
> Meta的数据共享政策会影响GCD的数据可用性。请确保对AMM进行签名，以充分利用广告系列层级的数据。

</Accordion>

## Meta ads成本的常见问题解答

<div id="getting-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="在AppsFlyer面板中查看Meta ads的成本数据">

AppsFlyer可以获取Meta ads上的广告消耗数据（包括点击和展示），但前提是相关广告系列在过去7天中必须至少拉动一次激活。

如果您在多个平台（安卓、iOS、PC端等）上投放Meta ads广告，面板会呈现分平台的成本，这些成本数据是由Meta ads计算的。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-integration-setup#cost-clicks-and-impressions">包含点击和展示的Meta ads成本数据</Anchor>。

</Accordion>

<div id="facebook-cost-example" />

<Accordion title="Meta ads成本数据示例">

如果广告主使用Meta投放广告，就会在AppsFlyer后台看到以下信息：

![mceclip2.png](https://files.readme.io/a1aa5847db5c0b873b34b1d4de43ade7d4109608371e05a84342122e56d0ce08-4411031032081.png)

The cost information is provided by Meta ads to AppsFlyer.而**激活**数据则是由AppsFlyer基于我们自己的归因逻辑计算得出的，因此Meta ads和AppsFlyer后台的eCPI数据一般都会有一定差异。

</Accordion>

<div id="i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="为什么AppsFlye面板上没有Meta ads成本的历史数据？">

完成首次Meta ads管理员登录之后，AppsFlyer就会收到正在投放中的Meta ads广告系列在过去7天内产生的历史成本数据。超过7天之前的成本数据不可用。

后续同步数据时，AppsFlyer也会接收最近7天的数据。也就是说AppsFlyer会收集所有广告系列的成本、点击和展示数据，前提是这些广告系列在过去7天中至少带来过1次转化。

</Accordion>

<div id="can-i-stop-cost-data-sync" />

<Accordion title="我可以停止费用数据同步吗？">

如需停止与Meta ads同步成本数据，请<Anchor target="_blank" href="https://www.facebook.com/help/405094243235242">进入相关Meta ads帐户的Business Integration（业务对接）部分，然后删除AppsFlyer</Anchor> 。

</Accordion>

<div id="cost-data-was-fine-for-a-few-months-but-it-stopped-displaying" />

<Accordion title="成本数据可以使用几个月，但它停止显示">

Meta ads可能会每隔几个月重置该权限。如果您发现面板停止显示成本数据，请重新完成Meta ads管理员登录操作。

如果Meta ads管理员用户更改了Meta ads密码，则也必须重复登录操作。

</Accordion>

<div id="i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer" />

<Accordion title="我5分钟前点击了我的Facebook广告。为什么在AppsFlyer中看不到点击？">

AppsFlyer会每隔几个小时定时从Meta ads拉取汇总的点击、展示和成本数据。因此，可能需要几个小时才能将这些操作显示在AppsFlyer面板上。

</Accordion>

<div id="can-i-get-raw-data-on-clicks-and-impressions-from-facebook" />

<Accordion title="是否能从Meta ads拉取到点击和展示的原始数据？">

AppsFlyer只能从Meta ads获取汇总的点击和展示数据，因此无法提供完整的点击和展示原始数据。只有带来过激活的点击和展示才会出现在原始数据报告中。

</Accordion>

<div id="are-there-limitations-of-facebook-cost-data-by-geo" />

<Accordion title="Meta ads的成本数据有没有地理位置维度的限制？">

在AppsFlyer面板上按地理位置筛选数据时，可以查看Meta ads成本数据的总结和明细。

地理位置维度仅适用于Meta ads上的“Mobile App Install Campaigns”（移动应用激活广告）。

此外，按地理位置分组的成本数据仅适用于单平台的广告系列。也就是说，如果一个广告系列下既有投放给安卓用户的广告组，又有投放给iOS用户的广告组，您就不能分地理位置查看其成本数据。**如需获取完整的成本数据，请分平台投放专用的广告系列** 。

</Accordion>

<div id="what-are-the-limitations-of-facebook-cost-data-in-master-api" />

<Accordion title="Master API的Meta ads成本数据有什么限制？">

Meta ads不支持在<Anchor target="_blank" href="/marketers/zh/docs/master-api-user-acquisition-metrics-via-api">Master API报告</Anchor>中同时按地理位置（Geo）和流量入口（Channel）来分组显示成本数据。

如需拉取完整的成本数据报告，请仅选择其中的一个维度对其进行分组。

</Accordion>

<div id="the-total-cost-doesnt-match" />

<Accordion title="为什么Meta和AppsFlyer中显示的总成本不匹配？">

由于Meta ads和AppsFlyer的归因模型有所不同，因此会使两者的成本数据之间出现差异：

* **Meta ads跨设备归因：** 如果某次激活及其相应的成本数据分别出现在不同平台（iOS/安卓）的广告系列下，就会造成数据差异问题。
* **Meta ads非移动端广告系列**：在这些广告系列（如Meta ads的链接点击广告）中，用户可能会在PC端与广告互动后在移动端安装应用。对于这些跨设备广告系列，AppsFlyer不显示成本。但是，如果链接单击是由安装该应用程序的同一设备执行的，则会收到费用数据。  
  例如，Facebook用户在台式计算机上单击指向广告客户登录页面的广告。一周后，同一位Facebook用户在iPhone设备上安装了广告客户的iOS应用。在这类场景中，AppsFlyer面板上会显示该用户的激活及其归因信息，但没有该次跨设备激活的成本数据。
* **过去7天内未带来转化的广告系列** - AppsFlyer仅同步过去7天内带来过激活/转化的广告系列的成本。如果您刚刚启用Meta ads的成本对接，则对于此前7天内转化为0的广告系列AF不会显示其成本数据。
* **已删除和归档的广告**：Meta 不会向 AppsFlyer 报告已删除和归档广告的成本，但该成本会反映在 Meta 仪表板中。这可能导致在按活动级别比较数据时，Meta 和 AppsFlyer 报告之间存在差异。

</Accordion>

<div id="why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical" />

<Accordion title="为什么在总成本相同的情况下，AppsFlyer计算出的eCPI和Meta ads不一样？">

平均激活成本的计算方式是将总成本除以激活数量。由于<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-discrepancies">AppsFlyer与Meta ads统计激活的方式不同</Anchor> ，因此两者的eCPI通常也会有所差异。

</Accordion>

<div id="why-doesnt-cost-data-include-data-from-all-campaigns" />

<Accordion title="为什么成本数据不包含部分广告系列？">

如果完成Meta ads登录（见上文）的用户在Meta ads中没有某些广告系列的权限，那么AppsFlyer面板虽然会这些广告系列，但部分成本、点击和展示数据会有所缺失。

**注意：** 即使有多个用户有权限在Meta Business Manager中投放广告，仍仅需一名用户完成Meta ads登录。

</Accordion>

<div id="is-facebook-cost-data-displayed-for-retargeting-campaigns" />

<Accordion title="Meta ads的再营销广告有没有对应的成本数据？">

您可以在群组分析报告的**统一**视图中查看<Anchor target="_blank" href="/marketers/zh/docs/cohort-and-retention-dashboard">成本和ROI数据</Anchor>。

</Accordion>

<div id="why-does-the-facebook-cost-configuration-window-close-before-login" />

<Accordion title="为什么我还没登录到Meta ads，成本配置窗口就自动关闭了？">

如果您使用同一个浏览器进行Meta ads登录和配置操作，则该窗口会使用相关的登录认证信息自动连接到Meta ads，而此时如果您已向AppsFlyer授权，则无需再执行任何操作，因此该窗口就会自动关闭。

</Accordion>

<div id="why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store" />

<Accordion title="对于在Amazon应用商店中上架的应用，其成本数据为何会出现差异？">

与AppsFlyer不同，Meta ads不会区分安卓应用和Amazon应用（以安卓系统为基础）的成本数据。因此，Amazon用户的成本数据可能会被归到投放给安卓用户的广告系列，而归不到原本的Amazon广告。

</Accordion>

<div id="how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked" />

<Accordion title="如果我的旧账户仍处于关联状态，要如何将成本数据连接到新的Meta ads广告帐户？">

如果您的成本数据仍通过AppsFlyer与老账户关联，但想要切换到新账户，必须先通过Meta ads断开老账户的连接，然后在AppsFlyer中连接新账户。

1. 从Meta ads后台进入**Settings** > **Business Integration**。
2. 在**Active**选项卡中删除AppsFlyer对接。  

   [![](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)
3. 进入AppsFlyer面板，然后使用新账户连接成本数据。

</Accordion>

## Facebook SDK疑难解答

<div id="who-needs-facebooks-sdk" />

<Accordion title="哪些场景中需要Facebook SDK？">

在接入AppsFlyer SDK之前，您可能已经在应用中安装了Facebook的SDK。如果尚未安装，那么您除了AppsFlyer SDK之外，是否还需要Facebook SDK？如果这样做，那么可以在没有重复报告的情况下将两者并存吗？

以下场景中无需使用Facebook SDK：

* **用户获取**：一般来说，AppsFlyer SDK可以对所有来自Meta ads的流量进行移动端的用户获取归因，归因范围覆盖广告互动、激活、应用打开（session）以及激活后的事件。
* **深度链接**：如果您想让用户点击链接后打开应用，并通过深度链接将用户引导至应用中的具体页面或内容，可以直接使用OneLink实现，无需用到Facebook SDK。您可以使用 iOS 通用链接、Android 应用链接和 URI 方案来做到这一点。详情请见**Meta帮助中心**。  

  请注意：  
  对于静态广告（非catalog），仅在跳转终点设为**App**的广告系列中支持iOS Universal Link和Android App Link。  
  例如，如果您在 Meta 中设置了一个意识活动 - 由于该活动不允许选择 **应用** 作为目标，因此不支持 iOS 通用链接和 Android 应用链接。  

  对于动态广告，您可以按照[这部分](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads)的说明使用iOS Universal Link、Android App Link和URI scheme。  

  Meta ads会抓取OneLink链接，并以其为基础创建Meta ads App Link，用于打开应用并对用户进行深度链接。

以下场景中需要同时接入Facebook SDK和AppsFlyer SDK：

* **延迟深度链接**：  
  Meta 广告 DDL 值在转换数据中不可用。客户必须与Meta协调，通常需要Facebook SDK来访问这些数据。
* **动态产品广告活动数据**:您只能通过Facebook SDK获取动态产品广告的数据。
* **其他Meta广告功能**:其他Facebook功能 您可能需要Facebook SDK是出于与归属无关的原因，例如身份验证，广告获利，社交共享，用户邀请等。

> 📘 **注意**
>
> 上述关于深度链接和延迟深度链接的信息及建议是基于AF对Facebook广告的全面测试得出的，在这些测试中我们使用的是Meta ads的演示/预览工具，其机制与实际投放的广告并不完全一致。

</Accordion>

<div id="avoiding-duplicates-with-facebook-sdk" />

<Accordion title="使用Facebook SDK避免数据重复">

如果您的<Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#faq_593792547454717">应用中同时接入了AppsFlyer SDK和Facebook SDK</Anchor>，Facebook SDK会上报激活和应用内事件，然后再通过AppsFlyer回传到Meta ads服务器。在这种情况下，您可以通过以下方式来避免数据的重复上报。

* Meta会对**激活**数据去重。也就是说每个激活只记录一次，因此激活数据**不会出现重复**。
* **对于应用内事件**，Meta广告不会去重应用内事件，这可能导致双重计数和不准确的应用内事件报告。为了避免Meta广告中的这种重复，请考虑以下任一选项：
  * 不要在Facebook SDK中配置事件
  * 对于安卓应用，您也可以停用AppsFlyer侧的<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-in-app-event-mapping">Meta ads应用内事件映射</Anchor>。  
    请注意：如要启用iOS 14.5+的SKAN归因，必须<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-interoperation-with-meta-ads#in-app-event-mapping">将应用内事件映射到Meta ads。</Anchor>

</Accordion>

## Meta ads归因的常见问题解答

<div id="attributing-agencies-with-facebook" />

<Accordion title="对代理投放的Meta ads广告进行归因">

代理和Meta投放管理合作平台可以为AppsFlyer上的广告主代投Meta ads广告或与广告主并行投放Meta ads广告，并对其进行归因。为确保能将代理带来的流量准确归因到代理，代理投放的广告系列在命名时必须以代理名称开头。

请注意：对于iOS 14流量，一个广告账户下只能有**一个**代理投放广告。详情请见<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-interoperation-with-meta-ads#skan互通appsflyer---meta-ads">Meta ads和AppsFlyer之间的SKAN互通设置</Anchor>。

如需进一步了解代理账户和Meta ads激活归因，请参阅<Anchor target="_blank" href="/partners/zh/docs/about-agency-accounts#srn配置">此文档</Anchor>。

此外，**代理无法更改Meta ads的归因窗口期以及再营销配置**。如有需要，代理需请广告主代为更改相关设置。

另外，代理也无法更改向Meta ads发送的任何应用内事件回传。这是因为Meta ads要求回传所有的激活信息，包括没有归因到Meta ads的激活（即不是由代理带来的流量）。

广告主需完成下图所示的所有配置后，代理才能管理其Meta ads上的广告投放：

[![advertiser-vs-agency-facebook-int-new.png](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)

</Accordion>

<div id="attribution-for-facebook-for-outofstore-android-apps" />

<Accordion title="第三方安卓应用商店的Meta ads广告归因">

Meta ads不允许广告主为第三方应用商店（如百度等）中的安卓应用投放应用激活广告。

但是，您可以按照以下说明在Meta ads上宣传第三方商店的应用并记录其激活：

1. 开发人员必须给每个第三方应用商店准备一个单独的APK包。详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution">此文档</Anchor>。
2. 在Meta ads中创建一个**Traffic**（流量）或**Conversion**（转化）广告系列，并启用移动归因，让潜在用户跳转到相关落地页。
3. 落地页中必须设计一个**下载应用**按钮，直接链接到APK包所在的第三方商店。
4. 潜在用户点击按钮后跳转到第三方商店，并完成应用激活。然后AppsFlyer会通过MMP API将该用户归因到Meta ads。

> 📘 **注意**
>
> 上述解决方案也适用于Google Play和App Store中的应用，用户需要先跳转到相关的<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">落地页</Anchor>，然后才能进入商店。

如需进一步了解Amazon应用的归因，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution#driving-users-to-the-amazon-app-store-from-facebook">此文档</Anchor>。

</Accordion>

<div id="what-is-facebook-android-and-ios-crossattribution" />

<Accordion title="Meta ads的安卓与iOS跨平台归因是如何实现的？">

Meta Ads是通过Meta ads账号来识别用户的，而有些用户会将同一个Meta ads账户同时关联到其iOS和安卓设备。

如果此类用户在其安卓设备上点击或浏览了相关应用的广告，然后在iOS设备上激活了该应用，Meta ads会将该次激活归因给自己。这种情况就会导致iOS应用的面板中出现安卓广告系列的名称。

> 📄 **示例**
>
> Andrew Josef在使用其安卓设备时点击了一则Meta广告，该广告向其推广了一个名为**Bubbles**的安卓应用，但他当下没有下载该应用。
>
> 过了一天，Andrew Josef决定在其iOS设备上直接下载并打开（即自然激活）**Bubbles**。
>
> 在该场景中，AppsFlyer会在iOS版Bubbles（即Andrew Josef最终下载并打开的应用）的面板上展示最初的那个安卓Meta ads广告系列。

</Accordion>

<div id="what-are-facebook-ads-channels" />

<Accordion title="Meta ads的流量入口有哪些？">

对于Meta ads的数据，您可以使用的细分维度包括广告系列、广告组、广告以及Meta ads流量入口（在Meta ads中称为Placements）。

* **Facebook**——来自Facebook应用的用户
* **Instagram**——来自Instagram应用的用户
* **Messenger**——来自Facebook Messenger应用的用户
* **AudienceNetwork**——Meta ads旗下其他应用的用户
* **线程** - 来自线程应用程序的用户
* **WhatsApp** - 来自WhatsApp应用的用户

您可以使用流量入口维度来比较各流量入口的用户质量。

![Facebook_channels.png](https://files.readme.io/f6b51baf3056f42ee32ac9709b1e4b3661580ce6148acfa36fc2bad102e7bfd8-4411036713745.png)

</Accordion>

<div data-zendesk-anchors="facebook-ads-faq=meta-ads%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HD1JTW2EP1MY3DD9136E9CHC=meta-ads%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HD1JTW2EN36V9SHH11283Y3A=i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard h_01HD1JTW2EJE0K034KSV8B3WZQ=can-appsflyer-show-the-campaign-level-and-ad-groups h_01HD1JTW2EFKCJMNBXBK2C55DN=is-facebook-data-shown-in-realtime h_01HD1JTW2E4SVC1Z9C3K6XJB2G=when-can-i-see-a-new-campaigns-data-on-appsflyer h_01HD1JTW2ECWSXFKQC1YBP1592=how-can-i-get-more-installs-from-facebook h_01K8B4YFDKKYP25V6NR12CE9RF=how-can-i-get-device-level h_google_play_referrer=google-play-install-referrer-api h_meta_install_referrer=meta-install-referrer h_attribution_fields=%E6%B4%BB%E5%8A%A8%E5%BD%92%E5%9B%A0%E5%AD%97%E6%AE%B5 campaign-attribution-fields=%E6%B4%BB%E5%8A%A8%E5%BD%92%E5%9B%A0%E5%AD%97%E6%AE%B5 h_sdk_requirements=sdk%E5%92%8C%E8%AE%BE%E7%BD%AE%E8%AF%B4%E6%98%8E sdk-requirements=sdk%E5%92%8C%E8%AE%BE%E7%BD%AE%E8%AF%B4%E6%98%8E h_decryption=%E6%8F%90%E4%BA%A4%E8%A7%A3%E5%AF%86%E5%AF%86%E9%92%A5 decryption-key=%E6%8F%90%E4%BA%A4%E8%A7%A3%E5%AF%86%E5%AF%86%E9%92%A5 h_01HD1JTW2ED762B3K1QS6QC38M=do-you-make-facebook-raw-data-available-to-agencies h_01HD1JTW2EWQGK4QA9W8DFZTMH=i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports h_01HD1JTW2EYSBJ38WNS1HP5MCE=any-specific-columns-for-facebook-in-appsflyers-performance-reports h_01HD1JTW2ETTXQAP7ZSTMVGA8K=can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer h_01HD1JTW2EPY8W5Z84PBWSM86G=what-should-i-do-when-i-receive-the-following-warning h_01HD1JTW2ED2DNPTXAFYJTTGV3=what-happens-with-different-lookback-windows-than-on-facebook h_01HD1JTW2EXF1R0MA91ZSW7QG4=what-are-the-facebook-api-parameters how-long-do-you-keep-facebook%E2%80%99s-userlevel-data=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EPDNSY30J45JB443A=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EN8THFCRNZ0EBQ2M3=are-ios-universal-links-and-android-app-links-supported-in-meta-ads h_01JJVVX9NCSTVQKG2ENTGDRDK9=are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content 01H7YJVNMVBRVTT9HH7KM8P33B=aem-attribution-is-not-working h_01HD1JTW2ETG739TWQVTKPCM2R=can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads h_01JTG2474VHWAD8EK8ASPWZY0W=conversion-events-are-not-sent-to-meta-ads h_01K8B4AKSHSMP18MM0GAAZEQMF=can-i-use-get h_01K8B4AKSH7E8TBEG024NAV1A5=%E6%B3%A8%E6%84%8F facebook-ads-cost-faq=meta-ads%E6%88%90%E6%9C%AC%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HD1JTW2EEVD1PDPFW15K45CE=meta-ads%E6%88%90%E6%9C%AC%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HD1JTW2EE0WQ90J431Z8NQ8Q=getting-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2ESVMMPK32W34PA54T=facebook-cost-example h_01HD1JTW2EVFXAET26WK2KSHTV=i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2EJQHKVJF4XHWGVASJ=can-i-stop-cost-data-sync h_01HD1JTW2EYJTA2TRY7EE75KXA=cost-data-was-fine-for-a-few-months-but-it-stopped-displaying h_01HD1JTW2EYXZW2QCMQH5CRFSK=i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer h_01HD1JTW2EYE2ZDNVRT5BCRXZJ=can-i-get-raw-data-on-clicks-and-impressions-from-facebook h_01HD1JTW2EG11RRBYHJ5BMJM5M=are-there-limitations-of-facebook-cost-data-by-geo h_01HD1JTW2E3RMV2TMPNZZ86HG5=what-are-the-limitations-of-facebook-cost-data-in-master-api h_01HD1JTW2EKVSAQ3706NC8JV9M=the-total-cost-doesnt-match h_01HD1JTW2EMJQJHBBB9SRJ6MZN=why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical h_01HD1JTW2E2S79FC9VAHA12X93=why-doesnt-cost-data-include-data-from-all-campaigns h_01HD1JTW2ET6Y2EHG29AQS09NA=is-facebook-cost-data-displayed-for-retargeting-campaigns h_01HD1JTW2EXTS1GDZHN8PAMV8C=why-does-the-facebook-cost-configuration-window-close-before-login h_01HD1JTW2FC0NJK00HZ76SFH30=why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store how-to-connect-cost-data-of%C2%A0a-new-facebook-ad-account-while-my-old-account-is-linked=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked h_01HD1JTW2F401DA2NHBSPTKATB=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked facebook-ads-sdk-faq=facebook-sdk%E7%96%91%E9%9A%BE%E8%A7%A3%E7%AD%94 h_01HD1JTW2FPRCVGBF7CG7ZMKXF=facebook-sdk%E7%96%91%E9%9A%BE%E8%A7%A3%E7%AD%94 h_01HD1JTW2F03XQSEVTFBW8JCX3=who-needs-facebooks-sdk h_01HD1JTW2FB09HM2CC83GMT901=%E6%B3%A8%E6%84%8F-1 h_01HD1JTW2FNNHPZQARZNCCP7ER=avoiding-duplicates-with-facebook-sdk facebook-ads-attribution-faq=meta-ads%E5%BD%92%E5%9B%A0%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HD1JTW2F2JV2BMDS40HFG6K0=meta-ads%E5%BD%92%E5%9B%A0%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HD1JTW2FK1ZTPTA8B8A4N64Z=attributing-agencies-with-facebook h_01HD1JTW2F63AT1NGBY96Y6CCE=attribution-for-facebook-for-outofstore-android-apps h_01HD1JTW2FMKYDHNSM7G182EY0=%E6%B3%A8%E6%84%8F-2 h_01HD1JTW2F8JT69CSN04GCZ91V=what-is-facebook-android-and-ios-crossattribution h_01HD1JTW2F5PY7A8T5NMHBZ87B=%E7%A4%BA%E4%BE%8B h_01HD1JTW2FX3QWC9BKWQ65E5B8=what-are-facebook-ads-channels" />

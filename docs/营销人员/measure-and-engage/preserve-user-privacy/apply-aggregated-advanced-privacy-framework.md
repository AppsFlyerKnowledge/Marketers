---
title: 汇总层级的高级隐私保护（AAP）框架
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
  created_at: '2021-03-15T11:32:31Z'
  edited_at: '2026-10-14T10:08:09Z'
  id: 360018515798
  locale: zh-cn
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/zh-cn/articles/360018515798
---
> **概要：** 为了应对iOS 14.5全量上线、Apple推行ATT后的隐私政策，广告主可以使用汇总层级的高级隐私保护（AAP）框架，在AF后台调整用户层级级别归因数据的可用性。

<div id="aggregated-advanced-privacy-aap-framework" />

## 基于高级隐私保护的汇总数据框架

AppsFlyer汇总层级的高级隐私保护（AAP）框架可阻断不同厂商的应用和网站之间的用户跟踪，并防止用户或设备被精确识别。AAP将Apple的应用跟踪透明度（App Tracking Transparency）原则作为隐私保护的最低标准。

广告主可通过AAP框架在AppsFlyer后台调整用户级别归因数据的可用性。

iOS 14.5全量上线、Apple推行ATT以后，如果您启用了AAP，那么对于拒绝授权的iOS 14.5+用户，广告主和渠道将无法获取其用户级别的归因数据。

AAP不影响广告主和渠道对于汇总归因数据和分析报告的获取。

<div id="aap-impacted-features" />

### 受AAP影响的功能

AAP启用后，原始数据会受到影响，其中的部分字段会变为受限或不可用。这种影响会波及下列数据传输工具：

* Data Locker
* Pull API原始数据
* Push API
* 面板的导出数据页
* 发送给广告平台的回传
* 客户侧用户层级数据API中的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">GCD API（获取转化数据）</Anchor>

AAP启用时对数据可用性的影响如下：

* **归因数据与作弊检测（Protect360）:** <Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">部分归因字段将受限或无法获取。</Anchor>
* **点击、展示及被拦截的点击（作弊）数据：** <Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions#identifier-restriction">用户和设备相关标识符信息</Anchor>将不可用。
* **延迟深度链接**：如果您计划在付费媒体中投放延迟深度链接，请使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unifieddeeplink">Unified Deep Linking API（UDL）。</Anchor>如果在付费媒体中使用GCD历史API实现延迟深度链接，则该链接对拒绝授权的用户无法生效。在自有媒体场景中，GCD历史API和新版深度链接API都可使延迟深度链接生效。

<div id="data-availability-principles-in-aggregated-advanced-privacy" />

## AAP中的数据可用性原则

如果具体到某一个用户，其AAP下的数据可用性取决于该用户的ATT授权状态以及带来该用户的媒体渠道。

**定义：**

* **用户级别归因数据：** 这类数据记录中包含设备层级标识符，且这些标识符关联到用户层级的归因信息。
* **广告主的受限归因数据**
  * 可用：设备层级标识符（IDFA仅在用户同意ATT授权时可用）。
  * 不可用通过出版商归属链接接收的归属参数（例如，`pid` 和 `c`）。不对广告主开放的字段列表，即受限媒体渠道。
* **渠道的受限归因数据：**
  * 可用： 汇总的投放信息。
  * 不可用不可用：可识别用户身份的用户级别数据，包括AppsFlyer ID、自定义数据（Custom Data）、客户用户ID（CUID）、点击ID（Click ID）、IDFA、IDFV、IMEI、用户代理（User Agent)、IP地址。

下图及下文中使用了上述概念来说明广告主和渠道的可用数据。

<Image align="center" alt="Advanced Privacy Framework - Advertisers (4).png" src="https://files.readme.io/0291fe2eea5f6efc41f2338824a0017be3e265f502e0d3999d52ac87b1ee7719-35847850634897.png" />

高级隐私保护模式对于网页广告和应用内广告的生效方式有所不同，因此必须使用af\_media\_type=web或af\_media\_type=app参数来说明媒体类型。点击<Anchor target="_blank" href="/partners/zh/docs/advanced-privacy-guide-postback-macros-for-ad-networks#网页广告">这里了解更多信息。</Anchor>

<div id="paid-and-owned-media-data-availability" />

### 付费及自有媒体的数据可用性

<div id="paid-media" />

<Accordion title="付费媒体">

付费媒体包括与AppsFlyer对接的移动广告平台，广告主会在这些平台上投放广告。

<div id="paid-media-data-availability-by-att-status" />

#### 分ATT授权状态的付费媒体数据可用性

<table><thead><tr><th rowspan="2">媒体类型</th><th colspan="2">ATT状态</th><th colspan="2">广告主</th></tr><tr><th>流量侧应用（Publisher App）</th><th>广告主 App</th><th>广告主</th><th>广告平台</th></tr></thead><tbody><tr><td rowspan="4">应用</td><td>已授权</td><td>已授权</td><td>\*用户级别归因数据</td><td>\*用户级别归因数据</td></tr><tr><td>Not authorized（拒绝授权）</td><td>已授权</td><td>广告主的受限归因数据 </td><td>渠道的受限归因数据</td></tr><tr><td>已授权</td><td>Not authorized（拒绝授权）</td><td>广告主的受限归因数据 </td><td>渠道的受限归因数据</td></tr><tr><td>Not authorized（拒绝授权）</td><td>Not authorized（拒绝授权）</td><td>广告主的受限归因数据 </td><td>渠道的受限归因数据</td></tr><tr><td> </td><td colspan="4"> </td></tr><tr><td rowspan="2"><p>网页</p></td><td>N/A</td><td>已授权</td><td>\*用户级别归因数据</td><td>\*用户级别归因数据</td></tr><tr><td>N/A</td><td>Not authorized（拒绝授权）</td><td>广告主的受限归因数据 </td><td>渠道的受限归因数据</td></tr></tbody></table>

</Accordion>

<div id="owned-media" />

<Accordion title="自有媒体">

Apple的AppTrackingTransparency（应用跟踪透明度，简称ATT）框架仅用于限制共享不同公司各自收集的数据。因此无论用户的ATT授权状态如何，广告主总是可以获取其自有媒体的用户级别归因数据。

自有媒体包括广告主用于触达用户的互联网营销投放，如邮件广告、交叉推广、推送通知等等。在AppsFlyer的语境中，通过广告平台投放的广告不算做自有媒体。

</Accordion>

<div id="controlling-advanced-aggregated-privacy" />

## 汇总层级高级隐私保护设置的调控方式

<div id="aap-central-switch" />

<Accordion title="汇总层级高级隐私保护（AAP）——分应用调控">

AAP是一个用于调控应用级别高级隐私保护设置的开关。您在选定应用中打开/关闭该开关后，相应的AAP设置就会对该应用下所有的渠道生效。您可以在**应用配置**页面中看到AAP开关。该开关打开时，该应用下所有渠道的**高级隐私保护**开关都会自动打开，且不能在渠道层级更改该设置。该开关处于关闭状态时，广告主可以在具体渠道的对接页面中单独打开该渠道的**高级隐私保护**功能。

<Image align="center" alt="AAPcontrol.png" src="https://files.readme.io/ddc8140ada9278eab447ecdfa4d88c56e07a0ed54b10b71de1cc2352f9590d40-35847850639121.png" />

<div id="aap-enabled" />

#### AAP开启时

* 汇总的归因数据仍可用，这包括数据总览面板以及群组和Master API等报告工具。
* 相关应用下所有渠道的[高级隐私保护开关都处于打开状态，且无法在渠道层级更改。请注意：以上设置已被锁定，无法调整位置。](#partner-advanced-privacy-switch)
* 广告主和渠道的用户级别数据可用性会受到限制，这在[上文相关部分](/docs/apply-aggregated-advanced-privacy-framework#aap中的数据可用性原则)有详细解说明。

<div id="aap-disabled" />

#### AAP关闭时

* 用户级别归因数据对广告主可用。
* 广告主可单独设置各渠道的高级隐私保护。

*需注意，关闭AAP可使第三方获取户级别的归因数据，请斟酌第三方对这些数据的使用方式再决定是否要关闭AAP。建议您与法务团队及其他相关专业顾问密切合作，确定Apple对“跟踪”的界定方式。 本文所述的所有内容仅供参考，不构成法律意见。*

**请按以下步骤设置汇总层级的高级隐私保护**：

1. 从AppsFlyer后台的侧边栏中选择**配置** > **应用配置**。
2. **根据需要打开或关闭汇总层级的**高级隐私保护开关。
3. 点击**保存**。

</Accordion>

<div id="partner-advanced-privacy-switch" />

<Accordion title="高级隐私保护（AP）——分渠道调控">

AAP关闭时，广告主仍可为各广告平台单独设置高级隐私保护。

<Image align="center" alt="APControl.png" src="https://files.readme.io/8e5a005cbadb5665cf255d39d6fa425298510f719b166c2013a2dfe57d4e982b-35847865312657.png" />

**请按以下步骤关闭渠道的高级隐私保护：**

1. **请先在应用配置页面中检查总体AAP开关是否处于关闭状态。**
2. 从AppsFlyer的侧边栏中选择**协作** > 活跃对接。
3. 选择相关广告平台。
4. **在渠道对接**选项卡中关闭高级隐私保护开关。

**AAP设置的更改及其对渠道高级隐私保护设置的影响**

如上文所述，AAP设置会覆盖渠道层级的高级隐私保护（AP）设置。但即使您之后关闭了AAP（总开关），还是可以在渠道层级单独将其高级隐私保护设置调回原来的状态。请参考以下示例场景：

* 您先前关闭了AAP总开关以及部分渠道的AP设置。
* 之后又打开了AAP总开关。注意，AAP开关打开时，会覆盖渠道层级的设置，使得所有渠道的AP设置都呈开启状态。
* 现在您再次关闭AAP，使得渠道的单独设置又变回之前的状态，对于之前已经关闭AP设置的渠道来说则没有变化。

</Accordion>

<div id="advanced-aggregated-privacy-implications-for-your-partners" />

## 汇总层级高级隐私保护对于合作渠道的影响

<div id="ad-networks" />

<Accordion title="广告平台">

<div id="postbacks-to-ad-network-partners" />

#### **发送到广告平台的回传数据**

<Anchor target="_blank" href="/partners/zh/docs/advanced-privacy-guide-postback-macros-for-ad-networks">AAP会影响广告平台</Anchor>接收到的共享数据，其原理与AAP对广告主的影响一致。数据是通过回传共享给广告平台的，而具体回传的数据视广告平台是否获得归因而有所不同。

以下任一开关呈开启状态时，上文所述的数据共享规则就会对相应的广告平台生效：

* AAP:应用层级开关
* AP:渠道层级开关

<div id="postbacks-for-attributed-ad-networks" />

#### **广告平台获得归因时收到的回传**

广告平台获得归因时，用于数据共享的回传类型取决于用户的授权状态，具体如下：

* **如用户同意授权：** 常规回传，其中包含带有标识符的用户级别归因数据。
* **未授权用户：** 高级隐私保护（AP）回传，其中包含的归因数据有限，仅提供广告投放信息，没有标识符。
  * **前提条件：** 广告平台必须先与AppsFlyer进行AP对接才能收到AP回传。如果没有对接，AF不会向该广告平台发送未授权用户的回传数据。
  * **例外情况：** 对于归因到Apple Search Ads（ASA）的激活，当广告平台不支持高级隐私保护，而其激活回传设置为**所有媒体渠道，包括自然流量**时，不论广告主侧是否启用了高级隐私保护，ASA都会向该广告平台发送激活回传。

下图详细说明了各种用户授权场景及其对应的回传类型。

<Image align="center" alt="AAP - Attributed ad networks.png" src="https://files.readme.io/d776c77115beb4c6b6ada1850077f186aa2feb809a8b69af8cf0ec760cd02b39-35847865314961.png" />

高级隐私保护模式对于网页广告和应用内广告的生效方式有所不同，因此必须使用af\_media\_type=web或af\_media\_type=app参数来说明媒体类型。点击<Anchor target="_blank" href="/partners/zh/docs/advanced-privacy-guide-postback-macros-for-ad-networks#网页广告">这里了解更多信息。</Anchor>

<div id="postbacks-for-unattributed-partners" />

#### **渠道未获得归因时收到的回传**

如果某渠道“合作伙伴配置”页的“对接”选项卡中的发送选项设置为*所有媒体渠道，包括自然流量*，即使该渠道未获得指定事件的归因（如下图所示），AF也会向其发送未归因到该渠道的回传。

<Image align="center" alt="InAppEventAll.png" src="https://files.readme.io/e24037f75b2b82797031eb13d5e063b8c2006812491e69674ff066ac830919f7-35847850644881.png" />

以下流程图解释了各种用户授权场景及其对应的回传类型。

<Image align="center" alt="AAP - Unattributed ad networks.png" src="https://files.readme.io/bb8a5d192e2120f8df90b9be044c0b4abf48c2250f5128fbbce76c60c89718cc-35847850645649.png" />

高级隐私保护模式对于网页广告和应用内广告的生效方式有所不同，因此必须使用af\_media\_type=web或af\_media\_type=app参数来说明媒体类型。如需了解详情，请参阅<Anchor target="_blank" href="/partners/zh/docs/advanced-privacy-guide-postback-macros-for-ad-networks#网页广告">此文档</Anchor>。

</Accordion>

<div id="analytics-partners" />

<Accordion title="数据分析平台">

AAP会影响数据分析平台接收到的共享数据，其原理与AAP对广告主的影响一致。  与这类平台的数据共享是通过回传来实现的。

以下任一开关呈开启状态时，上文所述的数据共享规则就会对相应的数据分析平台生效：

* AAP:应用层级开关
* AP:渠道层级开关

授权用户的回传数据中包含用户级别的归因数据，并带有用户标识符。若用户拒绝授权，则不发送回传。

下图详细说明了各种用户授权场景及其对应的回传类型。

<Image align="center" alt="AAP - Analytics partner.png" src="https://files.readme.io/4bb77720f9e0be093e325f989987f5b5ba2dba5aa26e2f32df5f1bd5b99161eb-35847865320593.png" />

高级隐私保护模式对于网页广告和应用内广告的生效方式有所不同，因此必须使用af\_media\_type=web或af\_media\_type=app参数来说明媒体类型。如需了解详情，请参阅<Anchor target="_blank" href="/partners/zh/docs/advanced-privacy-guide-postback-macros-for-ad-networks#网页广告">此文档</Anchor>。

</Accordion>

<div id="agencies" />

<Accordion title="代理">

数据可用性AAP对代理商的影响与广告主相似。如果代理商具有某个应用的原始数据权限，且AAP对某个用户的数据生效，则代理商的数据可用性遵循广告主的受限归因数据原则。

**代理商对广告平台AP设置的更改权限**

* AAP关闭时，各对接渠道的高级隐私保护可单独设置。
* 默认情况下，仅广告主可更改高级隐私保护设置。但广告主可以为代理商手动开放权限，让其设置广告平台的高级隐私保护。

**为代理商开放高级隐私保护的设置权限**

<Image align="center" alt="agency_advanced_privacy.png" src="https://files.readme.io/ac4a1aae41e9e39b9759006db84ea14df7495d0a14c02df7dbfb8dd93a2d2c23-35847865322129.png" />

**请按以下步骤为代理开放AP设置权限**：

1. 从AppsFlyer的侧边栏中选择**协作** > 活跃对接。
2. 选择代理商。
3. **在授权选项卡中打开更改**高级隐私保护设置开关。
4. 点击**保存**。

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/partners/zh/docs/advanced-privacy-guide-postback-macros-for-ad-networks">广告平台的高级隐私保护指南和回传宏</Anchor>

<div data-zendesk-anchors="aggregated-advanced-privacy-framework=%E5%9F%BA%E4%BA%8E%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4%E7%9A%84%E6%B1%87%E6%80%BB%E6%95%B0%E6%8D%AE%E6%A1%86%E6%9E%B6 h_01HDPDE0H3SYFWBHK59HBV2P6N=%E5%9F%BA%E4%BA%8E%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4%E7%9A%84%E6%B1%87%E6%80%BB%E6%95%B0%E6%8D%AE%E6%A1%86%E6%9E%B6 aapimpacted-features=%E5%8F%97aap%E5%BD%B1%E5%93%8D%E7%9A%84%E5%8A%9F%E8%83%BD h_01HDPDE0H339BPACN235V70MWW=%E5%8F%97aap%E5%BD%B1%E5%93%8D%E7%9A%84%E5%8A%9F%E8%83%BD data-availability-principles-in-aggregated-advanced-privacy=aap%E4%B8%AD%E7%9A%84%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7%E5%8E%9F%E5%88%99 h_01HDPDE0H3QBE60DVBZ1MWNB9N=aap%E4%B8%AD%E7%9A%84%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7%E5%8E%9F%E5%88%99 paid-and-owned-media-data-availability=%E4%BB%98%E8%B4%B9%E5%8F%8A%E8%87%AA%E6%9C%89%E5%AA%92%E4%BD%93%E7%9A%84%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HDPDE0H326EXNCQHPVJWXK3H=%E4%BB%98%E8%B4%B9%E5%8F%8A%E8%87%AA%E6%9C%89%E5%AA%92%E4%BD%93%E7%9A%84%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HDPDE0H3TBDSXCNW5Q3E1Q7P=paid-media paid-media-data-availability-by-att-status=%E5%88%86att%E6%8E%88%E6%9D%83%E7%8A%B6%E6%80%81%E7%9A%84%E4%BB%98%E8%B4%B9%E5%AA%92%E4%BD%93%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HDPDE0H3SACYAV19WQD9TCQ3=%E5%88%86att%E6%8E%88%E6%9D%83%E7%8A%B6%E6%80%81%E7%9A%84%E4%BB%98%E8%B4%B9%E5%AA%92%E4%BD%93%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HDPDE0H4M4XPE1C54K284BGW=owned-media controlling-aap=%E6%B1%87%E6%80%BB%E5%B1%82%E7%BA%A7%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4%E8%AE%BE%E7%BD%AE%E7%9A%84%E8%B0%83%E6%8E%A7%E6%96%B9%E5%BC%8F h_01HDPDE0H4VQC2DWAV68Q9VDVQ=%E6%B1%87%E6%80%BB%E5%B1%82%E7%BA%A7%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4%E8%AE%BE%E7%BD%AE%E7%9A%84%E8%B0%83%E6%8E%A7%E6%96%B9%E5%BC%8F h_01HDPDE0H4BHG114REGTWCDBP9=aap-central-switch aap-enabled=aap%E5%BC%80%E5%90%AF%E6%97%B6 h_01HDPDE0H4SC810EBK7ZGQ02K0=aap%E5%BC%80%E5%90%AF%E6%97%B6 aap-disabled=aap%E5%85%B3%E9%97%AD%E6%97%B6 h_01HKHPGQ1R6HZEXSRTX7ATVWE9=aap%E5%85%B3%E9%97%AD%E6%97%B6 h_01HDPDE0H4FRDXWRCYAWTPZZWE=partner-advanced-privacy-switch 01HKHPEBBFGQ5ZX4J6G50GEN64=%E6%B1%87%E6%80%BB%E5%B1%82%E7%BA%A7%E9%AB%98%E7%BA%A7%E9%9A%90%E7%A7%81%E4%BF%9D%E6%8A%A4%E5%AF%B9%E4%BA%8E%E5%90%88%E4%BD%9C%E6%B8%A0%E9%81%93%E7%9A%84%E5%BD%B1%E5%93%8D h_01HDPDE0H4PDJ4TC02TED0DB8P=ad-networks postbacks-to-ad-network-partners=%E5%8F%91%E9%80%81%E5%88%B0%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E7%9A%84%E5%9B%9E%E4%BC%A0%E6%95%B0%E6%8D%AE h_01HDPDE0H47ENYTWRVFPX0VTZC=%E5%8F%91%E9%80%81%E5%88%B0%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E7%9A%84%E5%9B%9E%E4%BC%A0%E6%95%B0%E6%8D%AE postbacks-for-attributed-ad-networks=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E8%8E%B7%E5%BE%97%E5%BD%92%E5%9B%A0%E6%97%B6%E6%94%B6%E5%88%B0%E7%9A%84%E5%9B%9E%E4%BC%A0 h_01HDPDE0H4B01YG577QZCG7TA7=%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E8%8E%B7%E5%BE%97%E5%BD%92%E5%9B%A0%E6%97%B6%E6%94%B6%E5%88%B0%E7%9A%84%E5%9B%9E%E4%BC%A0 postbacks-for-unattributed-partners=%E6%B8%A0%E9%81%93%E6%9C%AA%E8%8E%B7%E5%BE%97%E5%BD%92%E5%9B%A0%E6%97%B6%E6%94%B6%E5%88%B0%E7%9A%84%E5%9B%9E%E4%BC%A0 h_01HDPDE0H63ZMV255SN7EKDRMV=%E6%B8%A0%E9%81%93%E6%9C%AA%E8%8E%B7%E5%BE%97%E5%BD%92%E5%9B%A0%E6%97%B6%E6%94%B6%E5%88%B0%E7%9A%84%E5%9B%9E%E4%BC%A0 h_01HDPDE0H67T1XFTEB2N0NN6YN=analytics-partners h_01HDPDE0H6AM91W49W2G2Z94DM=agencies h_01HDPDMX05ZZCAMW4TTWF4M4YN=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

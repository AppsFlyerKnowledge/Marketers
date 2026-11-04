---
title: Protect360原始数据报告
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - Raw Data
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-09T13:03:45Z'
  edited_at: '2026-10-14T09:59:11Z'
  id: 360015179337
  locale: zh-cn
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/zh-cn/articles/360015179337
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 您可以通过Protect360原始数据报告查看被Protect360引擎拦截的激活和应用内事件，以及根据您手动添加的验证规则（Validation Rules）拦截的流量。

<div id="about-protect360-raw-data-reports" />

## Protect360原始数据报告简介

原始数据报告：

* 呈现以下数据：
  * 由Protect360引擎识别为假量的点击、激活和应用内事件。
  * 根据验证规则拦截的激活和应用内事件。
* 报告中包含每个点击、激活或应用内事件的拦截原因。
* 广告主可以使用这些报告与广告平台核对流量，从而进行相关优化，并根据归因后识别的假量调整归因面板。
* 如果您启用了AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">汇总层级高级隐私保护（AAP）功能，报告中的[部分字段可能受限或不可用](/docs/apply-aggregated-advanced-privacy-framework)。</Anchor>
* 报告类型及其可用性在各类数据传输方式中有所不同，分为下载、API和Data Locker（S3存储桶）几种，具体请见下文说明。
* 历史原始数据报告最多保留90天，具体取决于数据传输方式以及原始数据来源。

<div id="note" />

> 📘 **注意**
>
> 由于原始数据会受到数据隐私方面的限制，因此原始数据报告中会出现空值字段，比如助攻渠道字段的值可能为空。

<div id="report-types" />

<Accordion title="报告类型">

<div id="protect360-raw-data-report-types" />

#### Protect360原始数据报告分为以下几类：

| 报告 | 说明 |
| --- | --- |
| <span id="installs"></span>激活假量 | 这类报告中包含以下信息：<ul><li>**虚假激活（Fake installs）**：由Protect360引擎识别为假量的激活。只有Protect360的面板及原始数据会包含这些激活，AppsFlyer的任何其他面板和原始数据中都不会出现相关信息。</li><li>**被劫持的激活**（Hijacked installs）：这些激活来自真实用户，其激活归因遭到窃取，但由Protect360[纠正了归因结果](/docs/protect360-raw-data-reports#被劫持的激活归因更正)。</li><li>**验证规则**（Validation Rules）：根据验证规则拦截的激活或归因（由Protect360[纠正归因结果](/docs/protect360-raw-data-reports#被劫持的激活归因更正)）。</li></ul> |
| <span id="postattribution-installs"></span>归因后判定为假量的激活 | 这类报告中包含归因到某个渠道后被识别为假量的激活。Protect360会[纠正其归因结果](/docs/protect360-raw-data-reports#被劫持的激活归因更正)。 |
| <span id="blocked-inapp-events"></span>已拦截的应用内事件 | 这类报告中包含以下信息：<ul><li>由**虚假激活**产生的应用内事件</li><li>被识别为假量的**应用内事件**（与相关初始激活的判定结果无关）</li><li>**验证规则**（Validation Rules）：<ul><li>根据验证规则被拦截的激活或归因所产生的应用内事件</li><li>根据验证规则被拦截的应用内事件</li></ul></li></ul> |
| <span id="postattribution-inapp-events"></span>归因后识别为假量的应用内事件 | 这类报告中的应用内事件：<ul><li>在归因后被识别为假量</li><li>由归因后被识别为假量的激活所产生</li></ul> |
| <span id="clicks"></span>点击 | 这类报告中包含被拦截的激活及其拦截原因。 |
| <span id="blocked-install-postbacks"></span>已拦截的激活回传 | 如果某个渠道带来的激活被拦截，我们会向其发送被拦截的数据回传。这类报告中即包含这些回传信息。 |

</Accordion>

<div id="postattribution-reports" />

<Accordion title="归因后识别的假量报告">

* 归因后识别为假量的原始数据报告与已拦截的假量报告具有相同的结构。
* 当前月份（按激活日期计算）的归因后假量报告到次月七日（即检测日期）之前会持续更新。
* 归因后的原始数据报告仅对广告主开放。代理如需访问该数据，需要广告主为其<Anchor target="_blank" href="/partners/zh/docs/protect360-for-integrated-partners">授权</Anchor>。
* 该报告中包含在归因后被Protect360识别出来的假量，覆盖所有相关的媒体渠道。**请注意**：如果在指定日期范围内没有出现归因后被识别的假量，则该报告为空。
* 归因后原始数据拦截报告如下：

  * 后台面板：每个日历月内限一个媒体渠道。
  * Pull API：包含所有媒体平台 。限制条件：仅对广告主（应用所有者）开放。

<div id="using-post-attribution-reports" />

#### **归因后报告的使用方式**

* 根据实际需要选择一种激活/IAE组合以及检测日期范围。
* 请注意：Protect360会在激活发生当月到次月7日之间检测归因后的假量。比如，对于在11月内发生的激活，Protect360会一直检测到12月7日。
* Pull API的最佳使用方法如下：
  * 假设您拉取报告的频率为每天一次。
  * 将激活日期范围设置为60天前-当天。
  * 将“detect-from/detect-to”的范围设置为当天的前一天。  
    这样，您就能获得前一天的归因后假量报告。如果您已有数天没有拉取该报告，请根据实际情况调整检测日期范围，然后拉取报告。

<div id="example" />

> 📄 **示例**
>
> **示例A**：在12月发生的激活中，有15个激活被归因到example\_media。Protect360在1月3日（检测日期）将example\_media识别为作弊平台。这时，归因到example\_media的15个激活就会出现在归因后识别的假量报告中，以便广告主后续采取相应措施。
>
> **示例B**：在12月发生的激活中，有12个激活被归因到example\_media。Protect360在1月9日将example\_media识别为作弊平台。在这种情况下，Protect360不会采取任何措施，因为检测出作弊的日期在1月7日之后，这时上个月的归因后假量检测已经结束。

</Accordion>

<div id="raw-data-availability-by-tool-type" />

<Accordion title="分数据传输方式的原始数据可用性">

<div id="protect360-raw-data-availability-by-tool-type" />

#### 各种数据传输工具中的Protect 360原始数据可用性

<table><thead><tr><th>报告</th><th>数据时效性</th><th>Pull API</th><th>导出数据页面</th><th>Data Locker</th></tr></thead><tbody><tr><td>激活假量</td><td>实时</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>已拦截的应用内事件</td><td>实时</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>点击</td><td>实时</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>已拦截的激活回传</td><td>实时</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>归因后判定为假量的激活</td><td><p>每天UTC时间10:00更新</p></td><td><p><span>✓</span></p></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>归因后识别为假量的应用内事件</td><td><p>每天UTC时间10:00更新</p></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr></tbody><tfoot><tr><td colspan="5"><p>\*通过Data Locker获取报告的限制：</p><ul><li>不支持代理数据透明化。也就是说，代理流量中不包含带来激活的媒体渠道的名称。 </li><li>该报告中有一组专属字段，是其他Data Locker报告中所没有的，且这组字段无法更改。 </li><li>激活报告中不包含再营销数据，只有归因后识别的激活假量报告中会呈现该信息。 </li></ul></td></tr></tfoot></table>

</Accordion>

<div id="getting-raw-data-reports" />

## 获取原始数据报告

您可以通过下载、Pull API和Data Locker（S3存储桶）获取原始数据报告，也可以<Anchor target="_blank" href="/partners/zh/docs/protect360-for-integrated-partners">向渠道开放报告访问权限</Anchor>。

<div id="download" />

<Accordion title="下载">

**Protect360原始数据报告的下载方式如下：**

1. 在Protect360面板中点击**原始数据报告** > **实时**或**归因后**。
   * 对于归因后识别的假量报告，需要选择媒体渠道和月份。
2. 选择并下载**Protect360与验证规则**报告。

**或**

1. 从AppsFlyer面板进入**导出数据**。
2. 选择并下载**Protect360与验证规则**报告。

**请注意**：从导出数据页面中下载的报告包含所有媒体渠道。

</Accordion>

<div id="pull-api" />

<Accordion title="Pull API">

**通过Pull API下载原始数据报告的操作方法如下：**

**前期准备：**

您需要一个Pull API token，请让相关账户的<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">管理员</Anchor>为您提供该token。

1. 进入<strong>报告 > API数据接口。</strong>界面会打开<Anchor target="_blank" href="/marketers/zh/docs/pull-api-raw-data">Pull API</Anchor>页面。
2. 在Protect360假量报告部分中选择所需的Pull API。
3. 根据需要填充参数。下表列出了各项参数。
4. 拉取报告。

<div id="pull-api-raw-data-report-parameters" />

#### Pull API原始数据报告参数

| 参数 | 说明 | 格式 | 是否必须发送 |
| --- | --- | --- | --- |
| app\_id | 在AppsFlyer中显示的 App ID | 字符串 | 是 |
| api\_token | 如需获取该token，请在**报告** > **API数据接口** 中查看。仅帐户管理员可获取该API token。 | 字符串 | 是 |
| from | 日期范围起始时间：<ul><li>在激活记录中指激活日期。</li><li>在应用内事件记录中指事件发生日期。</li></ul> | YYYY-MM-DD | 是 |
| to | 日期范围结束时间：<ul><li>在激活记录中指激活日期。</li><li>在应用内事件记录中指事件发生日期。</li></ul> | YYYY-MM-DD | 是 |
| event\_name | 【可选】适用于归因后识别的应用内事件假量<br /><br />按应用内事件筛选数据，让报告仅呈现特定的事件，  其中可包含一个或多个事件。<br /><br />示例：`&event_name=af_purchase,af_login` | 字符串 | 否 |
| additional\_fields=rejected\_reason\_value | 【可选】适用于归因后识别的应用内事件假量<br /><br />**<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor>** 字段用于说明被劫持的激活/应用内事件的实际助攻渠道，可能出现的值为<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#attribution::2a6fd501">**contributor[1-3]**</Anchor>或者**organic**。 | 字符串 | 否 |
| detect-from | 【可选】适用于归因后识别的激活假量<br /><br />假量检测日期范围的起始时间（默认为from）。 | YYYY-MM-DD | 否 |
| detect-to | 【可选】适用于归因后识别的激活假量<br /><br />假量检测日期范围的结束时间（默认为to）。 | YYYY-MM-DD | 否 |

</Accordion>

<div id="data-locker" />

<Accordion title="Data Locker">

即使用Data Locker将原始数据写入AWS S3存储桶。

另请参阅<Anchor target="_blank" href="/marketers/zh/docs/data-locker-advertiser-reports#protect360">Protect360可用报告列表</Anchor>。

以及<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers#aws-cli">Data Locker配置说明</Anchor>。

</Accordion>

<div id="protect360-report-structure" />

## Protect360报告结构

Protect360报告的总体结构与用户获取报告一致。

除了常规的<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">原始数据报告字段</Anchor>，Protect360报告还包含再营销和拦截原因字段，具体如下：

<div id="blocked-reasons" />

### 拦截原因（Blocked reason）

<div id="click-level-blocked-reasons" />

<Accordion title="点击层级的拦截原因">

在点击层级，点击被拦截，在归因过程将忽略被拦截的点击。

| 拦截原因（Blocked reason） | 说明 |
| --- | --- |
| ip\_blacklist | 根据动态黑名单（<Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide#ip-denylists">了解详情</Anchor>）进行拦截 |
| invalid\_fingerprint | 仅适用于S2S点击：媒体渠道发送的参数无效（用于概率匹配） |
| click\_capping | 检测到该广告平台的点击作弊率极高。详情请见<Anchor target="_blank" href="/partners/zh/docs/protect360-for-integrated-partners#展示和点击截断capping">此文档</Anchor>。 |
| click\_signing | 点击中的签名未通过验证。<Anchor target="_blank" href="/partners/zh/docs/click-signing-for-ad-networks">详情请见此处说明。</Anchor> |
| input\_validation | 媒体渠道名称无效 |

</Accordion>

<div id="install-level-blocked-reasons" />

<Accordion title="激活层级的拦截原因">

我们在激活发生时根据充分信息判断该流量为假量，具体分为以下两种：

* 虚假激活，即激活相关应用的用户并非真实存在。这时，该激活的归因会完全被拦截。
* 归因劫持，即用户真实存在但广告交互是伪造的。这时我们会拦截虚假的广告交互，并将该激活重新归因到最初的真实助攻平台。

下表列出了可能出现的激活层级拦截原因：

<div id="install-level-fake-install-block-sub-reasons" />

#### 激活层级：适用于虚假激活的拦截原因

| 拦截原因（Blocked reason） | 详细拦截原因 （Blocked sub reason） | 说明 |
| --- | --- | --- |
| bots | fake\_device\_parameters | 在应用激活过程中，通过与设备相关的参数检测到非人类行为。 |
| bots | fake\_install\_parameters | 在应用激活过程中，通过与激活相关的参数检测到非人类行为。 |
| bots | bayesian\_network | 通过贝叶斯网络识别的作弊规律 |
| install\_store\_validation | - | 未通过Apple App Store的<Anchor target="_blank" href="/marketers/zh/docs/implement-apple-app-store-itunes-install-validation">激活验证</Anchor> |
| validation\_bots | invalid\_device\_parameters | 特定设备字段出现反常值，具体由客户定义 |
| validation\_bots | validation\_rules | 由于广告主自定义的验证规则而被拦截的激活 |
| bots | ai\_layer | AppsFlyer利用AI模型分析海量数据点，针对作弊设备和作弊激活提升假量识别能力 |

<div id="install-level-attribution-hijacking-block-sub-reasons" />

#### 激活层级：适用于归因劫持的拦截原因

| 拦截原因（Blocked reason） | 详细拦截原因 （Blocked sub reason） | 说明 |
| --- | --- | --- |
| ctit\_anomalies | short\_ctit | 由于CTIT过短而导致激活被拦截，具体由Protect360判定 |
| install\_hijacking | referrer\_hijack | 根据GooglePlay API和AppsFlyer SDK参数被拦截的归因劫持 |
| install\_hijacking | integration\_temporarily\_blocked | 由于渠道（pid）作弊率过高且所有流量中均存在明显异常，因而导致激活被拦截 |
| validation\_hijacking | short\_ctit | 由于CTIT过短而导致激活被拦截，具体由客户定义 |
| validation\_hijacking | empty\_site\_id | 由于未填充子渠道（site） ID，导致激活被拦截。 |
| validation\_hijacking | validation\_rules | 由于广告主自定义的验证规则而被拦截的归因 |

</Accordion>

<div id="cluster-level-blocked-reasons" />

<Accordion title="聚类层级的拦截原因">

AppsFlyer检测到有规律的作弊行为时，会将作弊平台加入黑名单。来自该平台的激活会被拦截，拦截原因分为以下两种：

* 虚假激活，即激活相关应用的用户并非真实存在。这时，该激活的归因会完全被拦截。
* 归因劫持，即用户真实存在但广告交互是伪造的。这时我们会拦截虚假的广告交互，并将该激活重新归因到最初的真实助攻平台。

下表列出了可能出现的激活层级拦截原因：

<div id="cluster-level-fake-install-block-reasons" />

#### 聚类层级：适用于虚假激活的拦截原因

| 拦截原因（Blocked reason） | 详细拦截原因 （Blocked sub reason） | 说明 |
| --- | --- | --- |
| bots | timestamp\_anomalies | 归因链路中的激活时间或从相关设备收集的其他时间戳出现异常 |
| bots, site\_blacklist | device\_emulators | 通过虚拟环境中的自动化脚本大批量生成的激活 |
| site\_blacklist | device\_farms | 未知（新）设备占比过高 |
| behavioral\_anomalies | behavioral\_anomalies | 有异于普通应用用户行为模式的可疑应用内行为 |

<div id="cluster-level-attribution-hijacking-block-reasons" />

#### 聚类层级：适用于归因劫持的拦截原因

| 拦截原因（Blocked reason） | 详细拦截原因 （Blocked sub reason） | 说明 |
| --- | --- | --- |
| ctit\_anomalies, install\_hijacking | ctit\_anomalies | 根据相关应用的CTIT标准判定CTIT模式异常 |
| click\_flood | click\_flood | 在CTIT的长期分布趋势中出现点击量异常激增 |
| install\_hijacking | click\_clusters | 由设备层级的恶意软件生成的点击 |

</Accordion>

<div id="inapp-level-blocked-reasons" />

<Accordion title="应用内事件层级的拦截原因">

应用内事件可能会由于以下原因被拦截：

* 相关的初始激活被判定为虚假激活。
* 根据您定义的验证规则进行拦截。
* 我们的算法检测到作弊行为。

下表列出了可能出现的应用内事件拦截原因。

<div id="in-app-level-block-reasons" />

#### 应用内事件层级的拦截原因

| 拦截原因（Blocked reason） | 详细拦截原因 （Blocked sub reason） | 说明 |
| --- | --- | --- |
| Inherits from install | Inherits from install | 初始激活在[激活](/docs/protect360-raw-data-reports#install-level-blocked-reasons)层级被判定为虚假激活，或根据[黑名单](/docs/protect360-raw-data-reports#cluster-level-blocked-reasons)被拦截。 |
| inapps\_bots | fake\_device\_parameters | AppsFlyer算法检测到作弊行为 |
| in\_app\_store\_validation | - | 未通过相关应用内购买的<Anchor target="_blank" href="/marketers/zh/docs/legacy-receipt-validation-for-in-app-purchases">收据验证</Anchor> |
| validation\_inapps | validation\_rules | 根据广告主自定义的验证规则判定 |

</Accordion>

<div id="retargeting" />

### 再营销

Protect360原始数据中包含由再营销广告代带来的激活和应用打开（session）假量（分别记录为再归因和再互动假量）。这些数据会通过<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#event">event name</Anchor>（事件名称）和<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#attribution::e9c68f6c">retargeting conversion type</Anchor>（再营销转化类型）字段来呈现，可能出现的字段值为：

* Install（即激活。该字段值适用于事件名称，但不会出现在再营销转化类型中）
* Re-attribution（再归因）
* Re-engagement（再互动）
* Reinstall（重装激活）

Protect360再营销原始数据中包含实时拦截以及归因后识别的假量，具体如下：

<table><thead><tr><th>报告 </th><th>导出数据</th><th>Pull API</th><th>Data Locker</th></tr></thead><tbody><tr><td>激活假量</td><td><span>✓\*</span></td><td><span>✓\*</span></td><td>-</td></tr><tr><td>归因后判定为假量的激活</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="4"> <span>\*再互动数据不可用</span><span><br/></span> </td></tr></tbody></table>

<div id="hijacked-installs-attribution-correction" />

### 被劫持的激活归因更正

对于被劫持的激活，AppsFlyer会拦截其归因，即阻止该激活被归因到作弊平台，并将其归因到最后一个触达用户的真实助攻渠道。

AppsFlyer会使用<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor>字段来标记激活劫持场景中的真实助攻渠道（即原本应获得激活归因的助攻渠道）。

* **rejected\_reason\_value**字段中可能出现的值为<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#attribution::2a6fd501">**contributor[1-3]**</Anchor>或**organic**。您可以通过**contributor[1-3]** **渠道**字段查看助攻渠道的详细信息并核算流量。
* 如果您的报告中未出现助攻渠道字段（contributor），可以通过**导出数据**页面添加。

**请注意**：在激活劫持场景中，如果激活被实时拦截，则AppsFlyer面板和报告中也会显示正确的归因结果，而不是仅仅在Protect360中呈现该信息。但如果在归因后被识别为激活劫持，则正确的归因结果仅显示在Protect360原始数据中。

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 应用内事件报告 | 应用内事件报告中不包含助攻渠道字段，该字段仅在激活报告中呈现。 |
| 空值 | 由于原始数据会受到数据隐私方面的限制，因此原始数据报告中会出现空值字段，比如助攻渠道字段的值可能为空。 |

</Accordion>

<div data-zendesk-anchors="about-protect360-raw-data-reports=protect360%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E7%AE%80%E4%BB%8B h_01HE7S55TCE60A34T6RCNTCQK8=protect360%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E7%AE%80%E4%BB%8B h_01J91EP40Q69KXXF2SR66AM2FQ=%E6%B3%A8%E6%84%8F h_01HE7S55TC4G31R9EANMKCZ7V5=report-types protect360-rawdata-report-types=protect360%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E5%88%86%E4%B8%BA%E4%BB%A5%E4%B8%8B%E5%87%A0%E7%B1%BB h_01HE7S55TCKQYTXPV6J54SHM0D=protect360%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E5%88%86%E4%B8%BA%E4%BB%A5%E4%B8%8B%E5%87%A0%E7%B1%BB h_01HE7S55TC4F5S243BSGN74RDK=postattribution-reports using-postattribution-reports=%E5%BD%92%E5%9B%A0%E5%90%8E%E6%8A%A5%E5%91%8A%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HE7S55TC7KCF75KFXHCE3K2K=%E5%BD%92%E5%9B%A0%E5%90%8E%E6%8A%A5%E5%91%8A%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HE7S55TCR8BKZ0PQ5B14X3X4=%E7%A4%BA%E4%BE%8B h_01HE7S55TC95YC1BJJ0ZERCQ14=raw-data-availability-by-tool-type protect360-rawdata-availability-by-tool-type=%E5%90%84%E7%A7%8D%E6%95%B0%E6%8D%AE%E4%BC%A0%E8%BE%93%E5%B7%A5%E5%85%B7%E4%B8%AD%E7%9A%84protect-360%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HE7S55TCH4CES29C5J3QXQK4=%E5%90%84%E7%A7%8D%E6%95%B0%E6%8D%AE%E4%BC%A0%E8%BE%93%E5%B7%A5%E5%85%B7%E4%B8%AD%E7%9A%84protect-360%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 getting-raw-data-reports=%E8%8E%B7%E5%8F%96%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01HE7S55TC3MRT6E9QV0J0X6FC=%E8%8E%B7%E5%8F%96%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01HE7S55TCBVFQ1DH06G53BNEN=download h_01HE7S55TCMT81J4SWBFQFYV2C=pull-api pull-api-raw-data-report-parameters=pull-api%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E5%8F%82%E6%95%B0 h_01HE7S55TCRRD95D0QPCXBRF8T=pull-api%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E5%8F%82%E6%95%B0 h_01HE7S55TCMAY86J1HKYB0APZ6=data-locker protect360-report-structure=protect360%E6%8A%A5%E5%91%8A%E7%BB%93%E6%9E%84 h_01HE7S55TCS91ZC9V3K0VDSVXK=protect360%E6%8A%A5%E5%91%8A%E7%BB%93%E6%9E%84 blocked-reasons=%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0blocked-reason h_01HE7S55TC1ZEDD5ABD21FCPY2=%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0blocked-reason h_01HE7S55TDMDSVQCVSV5YS3CZN=click-level-blocked-reasons h_01HE7S55TD754T07FWHFK5P71K=install-level-blocked-reasons install-level-fake-install-block-reasons=%E6%BF%80%E6%B4%BB%E5%B1%82%E7%BA%A7%E9%80%82%E7%94%A8%E4%BA%8E%E8%99%9A%E5%81%87%E6%BF%80%E6%B4%BB%E7%9A%84%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0 h_01HE7S55TDHTE5P47N1CCREGZX=%E6%BF%80%E6%B4%BB%E5%B1%82%E7%BA%A7%E9%80%82%E7%94%A8%E4%BA%8E%E8%99%9A%E5%81%87%E6%BF%80%E6%B4%BB%E7%9A%84%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0 install-level-attribution-hijacking-block-reasons=%E6%BF%80%E6%B4%BB%E5%B1%82%E7%BA%A7%E9%80%82%E7%94%A8%E4%BA%8E%E5%BD%92%E5%9B%A0%E5%8A%AB%E6%8C%81%E7%9A%84%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0 h_01HE7S55TDFA6WGAHE80ECV8CA=%E6%BF%80%E6%B4%BB%E5%B1%82%E7%BA%A7%E9%80%82%E7%94%A8%E4%BA%8E%E5%BD%92%E5%9B%A0%E5%8A%AB%E6%8C%81%E7%9A%84%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0 h_01HE7S55TDCHG0CVJA3JRSAW3G=cluster-level-blocked-reasons cluster-level-fake-install-block-reasons=%E8%81%9A%E7%B1%BB%E5%B1%82%E7%BA%A7%E9%80%82%E7%94%A8%E4%BA%8E%E8%99%9A%E5%81%87%E6%BF%80%E6%B4%BB%E7%9A%84%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0 h_01HE7S55TDBES0BY0FF3WKSSVG=%E8%81%9A%E7%B1%BB%E5%B1%82%E7%BA%A7%E9%80%82%E7%94%A8%E4%BA%8E%E8%99%9A%E5%81%87%E6%BF%80%E6%B4%BB%E7%9A%84%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0 cluster-level-attribution-hijacking-block-reasons=%E8%81%9A%E7%B1%BB%E5%B1%82%E7%BA%A7%E9%80%82%E7%94%A8%E4%BA%8E%E5%BD%92%E5%9B%A0%E5%8A%AB%E6%8C%81%E7%9A%84%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0 h_01HE7S55TD3M45TH4PY2W805W7=%E8%81%9A%E7%B1%BB%E5%B1%82%E7%BA%A7%E9%80%82%E7%94%A8%E4%BA%8E%E5%BD%92%E5%9B%A0%E5%8A%AB%E6%8C%81%E7%9A%84%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0 h_01HE7S55TDGB05PEZX8KS3J3QJ=inapp-level-blocked-reasons inapp-level-block-reasons=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%B1%82%E7%BA%A7%E7%9A%84%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0 h_01HE7S55TD661EHCV50S9BW5MS=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%B1%82%E7%BA%A7%E7%9A%84%E6%8B%A6%E6%88%AA%E5%8E%9F%E5%9B%A0 retargeting=%E5%86%8D%E8%90%A5%E9%94%80 h_01HE7S55TDSYDC8BWZ8D8DF9JE=%E5%86%8D%E8%90%A5%E9%94%80 hijacked-installs-attribution-correction=%E8%A2%AB%E5%8A%AB%E6%8C%81%E7%9A%84%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0%E6%9B%B4%E6%AD%A3 h_01HE7S55TD8SDCQJCCYQC0MNES=%E8%A2%AB%E5%8A%AB%E6%8C%81%E7%9A%84%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0%E6%9B%B4%E6%AD%A3 h_01J91E55BXQ4E01A9R3EB33WYF=traits-and-limitations" />

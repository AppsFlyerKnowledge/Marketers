---
title: 适用于iOS的Aggregate Event Measurement（AEM）
metadata:
  keywords:
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
  created_at: '2023-10-09T16:40:55Z'
  edited_at: '2026-10-14T10:07:17Z'
  id: 19228737402129
  locale: zh-cn
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/zh-cn/articles/19228737402129
---
> **概要：** 了解AEM解决方案，以优化iOS转化和应用内事件，并为Meta广告上的iOS重新参与进行归因。

<div id="overview" />

## 速览

AppsFlyer支持<Anchor target="_blank" href="https://www.facebook.com/business/help/721422165168355">Meta ads的Aggregated Event Measurement</Anchor>（全事件衡量，简称AEM）解决方案。该解决方案支持使用以下归因方法来测量iOS 14+设备的网页和应用事件：

* [针对再互动的应用AEM](#针对再互动的应用aem)
* [针对拉新推广的应用AEM](#针对拉新推广的应用aem)

作为AEM解决方案的一部分，Meta接受来自AppsFlyer的转化和应用内回调，前提是事件符合AEM的资格。要检查您的事件是否符合AEM资格，请参见以下内容：

* [检查您的应用事件是否符合AEM资格](#检查您的应用事件是否符合aem资格)

<div id="app-aem-for-re-engagement" />

## 针对再互动的应用AEM

启用AEM功能后，Meta ads可以在没有设备ID的情况下获取iOS用户的深度链接再互动归因信息。

<div id="attribution-flow" />

### 归因链路

Meta ads会在深度链接中附加归因数据以及AEM `campaign_ids`campaign\_idscampaign\_ids标识符。AppsFlyer接收到深度链接数据及其中所带的广告系列标识符后会进行如下处理：

* 向Meta ads回传汇总上报数据
* 根据Meta ads提供的深度链接信息完成归因
* 在原始数据报告和汇总数据报告中写入相关深度链接的归因数据

<div id="attribution-data-parameters" />

### 归因数据参数

AppsFlyer报告中包含由Meta ads上报的下列归因数据参数：

* `ad_id`
* `adgroup_id`
* `campaign_id`
* `campaign_group_id`
* `account_id`

<div id="faqs-on-deep-link-re-engagement-attribution" />

### 深度链接再互动归因疑难解答

<div id="what-must-the-advertiser-do-to-enable-this-attribution" />

<Accordion title="广告主应如何启用这一归因功能？">

广告主**无需在AF后台完成任何操作**，即可接收这些归因参数。

但如需衡量深度链接带来的再互动，请确保**再互动归因开关已打开**。

**请注意：请注意：Meta ads的AEM服务条款中指出，启用Meta ads的再互动归因衡量后，所有发送到Meta ads的回传都包含不完整的IP地址信息。**

</Accordion>

<div id="what-about-agencies-and-meta-campaign-management-partners" />

<Accordion title="对于代理和Meta广告投放管理平台有何影响？">

该功能目前不支持代理和Meta广告投放管理平台的归因，也就是说所有的流量都会归因到Meta ads。这一情况是暂时的，后续会有所变化。

</Accordion>

<div id="are-there-any-restrictions-on-data-from-this-attribution" />

<Accordion title="这一归因模式对数据有何限制？">

来自深度链接转化的数据没有上报限制，也就是说所有相关数据都会出现在汇总级别和用户级别的原始数据报告中。

</Accordion>

<div id="app-aem-for-app-promotion" />

## 针对拉新推广的应用AEM

<div id="aem-eligibility" />

### AEM适用性

对于可以使用AEM的应用，在其广告组（Ad Set）创建流程中，系统会默认选择**Aggregated Event Measurement**。在这种情况下，AEM和SKAN会同时对相关的广告系列生效。但如果广告主选择了**Apple的SKAdNetwork**，则只有SKAN会对相关广告系列生效。这种情况下，对于Meta ads上的应用使用情况，AppsFlyer的衡量能力有限。

<Image alt="aem_meta_ads_platform.png" src="https://support.appsflyer.com/hc/article_attachments/19228698538769" width="563px" />

<div id="note-1" />

> 📘 **注意**
>
> 如果您在AEM资格方面遇到问题，请参见[检查您的应用事件是否符合AEM资格](#检查您的应用事件是否符合aem资格)。

<div id="aem-data-sharing" />

### AEM数据共享

**高级数据共享**使您能够与Meta广告共享所有转化事件，并归因于所有安装和后续的应用内事件，无论ATT同意状态如何。

* 当关闭时，高级数据共享仅限于响应ATT提示同意的用户的转化事件；来自不同意用户的事件既不共享也不归因。
* 当开启时，高级数据共享允许发送所有用户的转化事件，无论ATT状态如何。AppsFlyer对这些事件进行归因。共享的数据可能包括不涉及设备ID的其他设备相关信息。要了解更多信息，请参见<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-integration-setup#advanced_data_sharing">高级数据共享</Anchor>。

aem

<div id="note-2" />

> 📘 **注意**
>
> * 所有事件包含激活、应用打开和应用内事件。
> * **在启用高级数据共享功能前，请先确这样的数据共享，包括第三方对您数据的使用，符合你需要遵守的所有平台政策和/或法律法规。** 该功能启用时，共享的数据可能包括IP地址、anon\_ids（若可用）、vendor\_id和User Agent等。
> * 对于通过服务器到服务器（S2S）发送的应用内事件，Meta要求事件负载中包含**IP地址**和**供应商标识符（IDFV）**。没有这些标识符，事件将不符合Meta的AEM归因资格。
> * Meta AEM用于应用推广也可能包括非确定性的查看归因。要支持通过Meta AEM进行非确定性的查看归因，请确保应用级**启用v通过概率建模进行查看归因**开关已打开。有关详细信息，请参见<Anchor target="_blank" href="/marketers/zh/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">通过概率建模进行查看归因</Anchor>。

<div id="check-if-your-app-events-are-eligible-for-aem" />

## 检查您的应用事件是否符合AEM资格

您可以访问Meta事件管理器检查您的应用事件是否符合AEM资格。一旦您的应用事件符合资格，您可以在广告管理器中查看所选AEM活动的结果。要了解如何检查您的应用事件是否符合 AEM 的资格，请参阅 <Anchor target="_blank" href="https://www.facebook.com/business/help/716239976391518?id=1877298665783613">元文档</Anchor>。

<div id="enable-aem-summary" />

## 如何启用 AEM - 概要

使用下面的表格作为在 AppsFlyer 中启用 Meta 广告 AEM 的快速检查清单。

| **解决方案** | **切换** | **切换位置** | **业务影响** |
| --- | --- | --- | --- |
| **AEM 再营销（重新参与）** | 再互动归因 | 合作伙伴集成（Meta 广告） | 启用 AEM 进行再营销（重新参与归因）。 |
| **AEM 应用推广（安装）** | 高级数据共享（Advanced data sharing） | 合作伙伴集成（Meta 广告） | 启用 AEM 进行应用推广，包括与 Meta 共享来自 ATT 选择退出用户的事件，并接受非确定性索赔（如适用）。 |
| **AEM 应用推广（安装）** | 通过概率建模实现浏览归因 | 应用配置 | 启用非确定性索赔的查看归因。 |

<div id="troubleshooting" />

## 问题排查

<div id="troubleshooting-ineligible-events-in-meta-aem" />

<Accordion title="排查 Meta AEM 中不合格事件的问题">

如果 Meta 广告将您的应用事件标记为不合格——显示错误如 **“缺少选择退出事件”** 或其他与 AEM 相关的消息——通常是由于缺少或配置错误的数据。使用下面的检查清单来诊断和修复常见问题。

<div id="important" />

> 🚧 **重要提示！**
>
> 完成以下步骤后，请允许时间让更改生效。更改应用后，Meta 广告可能需要最多 **2-3 天** 才能反映 AEM 资格。

<div id="step-1-advanced-data-sharing-is-enabled" />

<Accordion title="第1步：已启用高级数据共享">

1. 进入**协作** > **活跃对接**。
2. 确保 **高级数据共享** 已开启。

</Accordion>

<div id="step-2-ip-masking-is-disabled" />

<Accordion title="第2步：IP 屏蔽已禁用">

带有屏蔽 IP 的事件不符合 AEM 的资格。

* 转到应用设置
* 确保 **IP掩码** 已关闭。

</Accordion>

<div id="step-3-servertoserver-s2s-events-include-required-parameters" />

<Accordion title="第3步：服务器到服务器（S2S）事件包括必需的参数">

每个 S2S 事件必须包括：

* **IP地址**
* **IDFV**（供应商标识符）

</Accordion>

<div id="step-4-review-att-consent-rate" />

<Accordion title="第4步：查看 ATT 同意率">

Meta 接受有限数量缺失或为零的 IDFA 事件。如果您的应用超出此阈值，您可能会看到此错误：**广告主跟踪启用参数超出范围。**

</Accordion>

<div id="step-5-postback-mapping-configuration" />

<Accordion title="第5步：回调映射配置">

确保事件回调映射到 **发送所有（包括自然流量）**。

</Accordion>

<div id="step-6-check-reengagement-settings-if-relevant" />

<Accordion title="第6步:检查重新参与设置（如相关）">

再互动广告

* 在 **应用设置** 和 **Meta 活动集成页面** 中启用 **重新参与归因**。

</Accordion>

<div id="still-not-working" />

#### 仍然无法工作？

如果特定事件仍然不合格：

1. 前往 Meta 的事件管理器并按照屏幕上的指导操作。
2. 选择受影响的应用事件。
3. 将 **MMP 流量** 设置为首选连接方式。

<div id="need-help" />

#### 如需支持，

如果问题仍然存在：

* 向技术支持团队提交工单
* 包括来自 Meta 广告的屏幕截图，显示不合格的事件。

</Accordion>

<div id="i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible" />

<Accordion title="我在仪表板和报告中没有收到 AEM 数据，尽管我的活动符合 AEM 条件。">

这是Meta的回复：“我们将在接下来的几个月与您的MMP合作推出此更新，部分广告主在更新完成之前可能无法访问。”

</Accordion>

<div id="why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement" />

<Accordion title="为什么即使在签署AMM协议后，我仍然看不到AEM归因的安装在原始报告中？">

当AAP启用时，通过Meta的聚合事件测量（AEM）归因的安装将被排除在原始数据报告之外。即使签署了AMM协议，这也适用。

</Accordion>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01HCAM4CEVRCG13CA32B0GM9QS=%E9%80%9F%E8%A7%88 app-aem-for-reengagement=%E9%92%88%E5%AF%B9%E5%86%8D%E4%BA%92%E5%8A%A8%E7%9A%84%E5%BA%94%E7%94%A8aem 01H88ZM20H99W37M0H6XXQVMQA=%E9%92%88%E5%AF%B9%E5%86%8D%E4%BA%92%E5%8A%A8%E7%9A%84%E5%BA%94%E7%94%A8aem attribution-flow=%E5%BD%92%E5%9B%A0%E9%93%BE%E8%B7%AF 01H7YJVNMV7QSZJWKZZA9042K6=%E5%BD%92%E5%9B%A0%E9%93%BE%E8%B7%AF attribution-data-parameters=%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE%E5%8F%82%E6%95%B0 01H7YJVNMVPPCD08Z2R0V5GCMY=%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE%E5%8F%82%E6%95%B0 faqs-on-deep-link-reengagement-attribution=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0%E7%96%91%E9%9A%BE%E8%A7%A3%E7%AD%94 01H7YJVNMV4ZKMWKD06RC6GKFW=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%86%8D%E4%BA%92%E5%8A%A8%E5%BD%92%E5%9B%A0%E7%96%91%E9%9A%BE%E8%A7%A3%E7%AD%94 01H7YJVNMVSGMNJ3K84MCENXYG=what-must-the-advertiser-do-to-enable-this-attribution 01H7YJVNMVP7ZRCKXDRRH7GZBY=what-about-agencies-and-meta-campaign-management-partners are-there-any-restrictions-on-data-from-this%C2%A0attribution=are-there-any-restrictions-on-data-from-this-attribution 01H7YJVNMVQF0B0DV2NQYQVYHK=are-there-any-restrictions-on-data-from-this-attribution app-aem-for-app-promotion=%E9%92%88%E5%AF%B9%E6%8B%89%E6%96%B0%E6%8E%A8%E5%B9%BF%E7%9A%84%E5%BA%94%E7%94%A8aem 01H88ZM20HQFMG962AZGYA98FR=%E9%92%88%E5%AF%B9%E6%8B%89%E6%96%B0%E6%8E%A8%E5%B9%BF%E7%9A%84%E5%BA%94%E7%94%A8aem aem-eligibility=aem%E9%80%82%E7%94%A8%E6%80%A7 01H7YJVNMVPB054VFS60KH9N7W=aem%E9%80%82%E7%94%A8%E6%80%A7 h_01HR886Q0KPM99FCQXD6RDPSBK=%E6%B3%A8%E6%84%8F aem-data-sharing=aem%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%AB 01H88ZM20HK2HY32M4BKZ4N0B9=aem%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%AB 01H7YK9CHHNARCD7M2VZRMEW6S=%E6%B3%A8%E6%84%8F-1 check-eligibility=%E6%A3%80%E6%9F%A5%E6%82%A8%E7%9A%84%E5%BA%94%E7%94%A8%E4%BA%8B%E4%BB%B6%E6%98%AF%E5%90%A6%E7%AC%A6%E5%90%88aem%E8%B5%84%E6%A0%BC 01JBHQSHF8NA4SGVJ3WYPRN9B3=%E6%A3%80%E6%9F%A5%E6%82%A8%E7%9A%84%E5%BA%94%E7%94%A8%E4%BA%8B%E4%BB%B6%E6%98%AF%E5%90%A6%E7%AC%A6%E5%90%88aem%E8%B5%84%E6%A0%BC enable-aem-toggles-summary=%E5%A6%82%E4%BD%95%E5%90%AF%E7%94%A8-aem---%E6%A6%82%E8%A6%81 h_01KJ28ETP9GK6TBTJK8SBZ5PFW=%E5%A6%82%E4%BD%95%E5%90%AF%E7%94%A8-aem---%E6%A6%82%E8%A6%81 faqs-and-troubleshooting=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 01H7YK9CHHZN78CBHFTQ7E9RKQ=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 h_01K720W9MYXFTYG18368SKHGGC=troubleshooting-ineligible-events-in-meta-aem h_01K720W9MYDKK5Q2J1M8VT9JFP=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01K722GQSB92J5KFFYQNP5WR29=step-1-advanced-data-sharing-is-enabled h_01K722GQSBV3GY2ZNN29ENG7Q2=step-2-ip-masking-is-disabled h_01K722GQSBVTSC09EPPCZQ6WN3=step-3-servertoserver-s2s-events-include-required-parameters h_01K722GQSBSX06A56ZX8RJ6YKT=step-4-review-att-consent-rate h_01K722GQSB26TN65JVJD6R7BAV=step-5-postback-mapping-configuration h_01K722GQSBTD4J9TZHBRGYS1XV=step-6-check-reengagement-settings-if-relevant still-not-working=%E4%BB%8D%E7%84%B6%E6%97%A0%E6%B3%95%E5%B7%A5%E4%BD%9C h_01K722GQSB8CXSSCVZPA3R3CJX=%E4%BB%8D%E7%84%B6%E6%97%A0%E6%B3%95%E5%B7%A5%E4%BD%9C need-help=%E5%A6%82%E9%9C%80%E6%94%AF%E6%8C%81 h_01K722GQSBBB8KS8JNRBJZ4WWT=%E5%A6%82%E9%9C%80%E6%94%AF%E6%8C%81 01JCX7SKJ76KGW9SN7RCFA18E6=i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible why-can%E2%80%99t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement h_01K4ADBT26D2KD5MH568542XSV=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement" />

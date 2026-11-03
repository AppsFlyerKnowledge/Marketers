---
title: 数据行数限制以及超限数据的处理
metadata:
  keywords:
    - performance reports
    - Advertisers
    - exceeded
    - reports
    - faq
    - Agencies
    - Exceeded_Events_Limit
    - Exceeded Events Limit
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
  created_at: '2017-10-08T15:20:55Z'
  edited_at: '2026-10-14T10:09:22Z'
  id: 115005099063
  locale: zh-cn
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/zh-cn/articles/115005099063
---
> **概要：** 本文解释了汇总数据中某些维度显示为*exceeded*（超限）的原因，以及避免数据超限的方法。

## 超限维度的含义

AppsFlyer会收集您的激活和事件数据并对其进行汇总。数据汇总的原理是将唯一值填充到给定的维度，而某个维度中唯一值的数量即称为基数（Cardinality，在数据表中体现为行数）。大部分的数据分析及汇总工具都有分维度的行数限制。当某个维度中的唯一值数量超出该限制时，超出部分的数据就会被另行分组为*exceeded*（超限），单独分行显示。当媒体渠道维度中的唯一值数量超出行数限制时，剩余的渠道数据，**包括所有相关维度的渠道细分数据**都会被归到*exceeded*分组下。

关于行数限制对具体报告的影响，请见下文示例。

> 📄 **示例**
>
> **示例A：广告系列ID的行数限制**
>
> 广告系列ID的行数限制为3000行。也就是说，如果某天上报的广告系列ID数量超过3000，则超出部分的广告系列ID会被另行分组为Exceeded\_CampaignID\_Limit，单开一行显示。
>
> **示例B：事件的行数限制**
>
> * 假设相关事件的行数限制为3行。
> * 某天上报的独立事件数量为7，分别是A、B、C、D、E、F 和 G。换句话说，此时事件维度下有7个唯一值。
> * 汇总报告中会分别列出事件A、B、和C，而事件D、E、F和G会被一起归到Exceeded\_Events\_Limit一行中。

维度值超限以及行数限制会影响到下列汇总数据：

* 数据总览面板
* 汇总数据导出和Pull API报告
* Master API报告
* 活跃数据和自定义面板中的点击和展示数据
* Protect360面板

原始数据不受行数限制的影响。

如果您的大部分数据都被归到*exceeded*分组内，表示这些数据并没有得到细分，致使分析报告的结果不够精确。您可以根据实际需求，使用原始数据来创建没有行数限制的分组。

下表列出了单个应用每天的数据行数限制。

<table><tbody><tr><th>维度</th><th>超限数据的分组名称</th><th>限制类型的维度</th><th>每天的数据行数限制 </th><th>Protect360每日数据行数</th></tr><tr><td>广告</td><td>Exceeded_Ad_Limit</td><td>媒体渠道</td><td>1000</td><td>-</td></tr><tr><td>广告ID</td><td>Exceeded_AdID_Limit</td><td>媒体渠道</td><td>1000</td><td>-</td></tr><tr><td>广告组</td><td>Exceeded_AdSet_Limit</td><td>媒体渠道</td><td>1000</td><td>-</td></tr><tr><td>广告组ID</td><td>Exceeded_AdSetID_Limit</td><td>媒体渠道</td><td>1000</td><td>-</td></tr><tr><td>广告系列</td><td>Exceeded_Campaign_Limit</td><td>媒体渠道</td><td>3000</td><td><ul><li>激活/应用内事件：3000</li><li>展示/点击：100 </li></ul></td></tr><tr><td>广告系列ID</td><td>Exceeded_CampaignID_Limit</td><td>媒体渠道</td><td>3000</td><td><ul><li>激活/应用内事件：3000</li><li>展示/点击：100 </li></ul></td></tr><tr><td>流量入口（Channel）</td><td>Exceeded_Channels_Limit</td><td>媒体渠道</td><td>20</td><td>20</td></tr><tr><td>子渠道ID</td><td>Exceeded_SiteID_Limit</td><td>媒体渠道</td><td>1000\*\*</td><td><ul><li>激活/应用内事件/展示/点击：1000\*\*</li></ul></td></tr><tr><td>事件</td><td>Exceeded_Events_Limit</td><td>应用 </td><td>300 </td><td>激活/应用内事件：300 </td></tr><tr><td>关键词</td><td>Exceeded_Keywords_Limit</td><td>媒体渠道</td><td>1000</td><td>-</td></tr><tr><td>媒体渠道名称\*</td><td>Exceeded_MediaSource_Limit</td><td>应用</td><td>1000</td><td><ul><li>激活/应用内事件：1000</li><li>展示/点击：100 </li></ul></td></tr><tr><td colspan="5"><p>\*当<span>媒体渠道维度中的唯一值数量超出行数限制时，剩余的渠道数据</span><strong>，包括所有相关维度的渠道细分数据</strong><span>都会被归到</span><em>exceeded</em><span>分组下。</span></p><p><span>\*\*详情请见<a href="./measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">Exceeded_SiteID_Limit</a>部分的说明。</span></p></td></tr></tbody></table>

## 每个维度的数据行数限制

<div id="exceeded_adset_limit-and-exceeded_ad_limit" />

<Accordion title="Exceeded_AdSet_Limit and Exceeded_Ad_Limit">

* 每个媒体渠道下，独立广告组名称的数量上限为1000个，独立广告名称的数量上限也是1000。
  * 也就是说，任意一天内，从第1001个开始的所有广告组信息都会被归到名为**Exceeded\_AdSet\_Limit**的渠道分组下。同理，超限广告的信息会被归到名为**Exceeded\_Ad\_Limit**的渠道分组下。

> 👍 **提示**
>
> 出现超限情况时，可以使用“分治法”来解决数据细分问题。具体方法为：设置少量通用广告组名称（最好不超过50个），然后将之前所有的广告组名称作为单个广告的名称，放到新设置的通用广告组名称下。您也可以在AppsFlyer归因链接中使用 **af\_sub**参数来解决此问题。这一方法可以帮助您：
> 1. 防止数据表中出现**Exceeded\_AdSet\_Limit** 或<strong>Exceeded\_Ad\_Limit分组。</strong>2. 根据重要的广告组和广告流量有效优化投放。
> 3. 根据原始数据中的广告组和广告名称进行深度分析。

</Accordion>

<div id="exceeded_adsetid_limit-and-exceeded_adid_limit" />

<Accordion title="Exceeded_AdSetID_Limit和Exceeded_AdID_Limit">

* 每个媒体渠道下，独立广告组ID的数量上限为1000个，独立广告ID的数量上限也是1000。
  * 也就是说，任意一天内，从第1001个开始的所有广告组ID信息都会被归到名为**Exceeded\_AdSetID\_Limit**的渠道分组下。同理，超限广告ID的信息会被归到名为**Exceeded\_AdID\_Limit**的渠道分组下。

</Accordion>

<div id="exceeded_campaign_limit" />

<Accordion title="Exceeded_Campaign_Limit">

**[![](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)**

* 一天内独立广告系列名称的数量上限为3000个。
  * 也就是说任意一天内，从第3001个开始的所有广告系列都会被归到名为**Exceeded\_Campaign\_Limit**的渠道分组中。

> 👍 **提示**
>
> 解决方法如下：设置少量通用广告系列名称（最好不超过300个），然后将之前所有的广告系列名称作为广告组的名称，放到新设置的通用广告系列名称下。您也可以在AppsFlyer归因链接中使用 **af\_sub**参数来解决此问题。这一方法可以帮助您：
> 1. 防止数据表中出现**Exceeded\_Campaign\_Limit**。
> 2. 根据重要的广告组流量有效优化投放。
> 3. 根据原始数据中的广告系列和广告组名称进行深度分析。

</Accordion>

<div id="exceeded_campaignid_limit" />

<Accordion title="Exceeded_CampaignID_Limit">

* 一天内独立广告系列ID的数量上限为3000个。
  * 也就是说任意一天内，从第3001个开始的所有广告系列ID都会被归到名为**Exceeded\_CampaignID\_Limit**的渠道分组中。

</Accordion>

<div id="exceeded_channels_limit" />

<Accordion title="Exceeded_Channels_Limit">

* 一天内每个渠道下独立流量入口名称的数量上限为20个。Protect360中该维度的数量限制是1000个。
  * 也就是说任意一天内，从第21个开始的所有流量入口都会被归到名为**Exceeded\_Channel\_Limit**的渠道分组中。

</Accordion>

<div id="exceeded_events_limit" />

<Accordion title="Exceeded_Events_Limit">

* 一天内独立事件名称的数量上限为300个。
  * 也就是说任意一天内，从第301个开始的所有事件名称都会被归到名为**Exceeded\_Events\_Limit**的分组中。

> 👍 **提示**
>
> 如需解决超限问题，使数据表中不再出现**Exceeded\_Events\_Limit**分组，可使用以下方式：
>
> * 配置<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">富应用内事件</Anchor>。设置少量通用事件名称（最好不超过20个），减少独立事件的上报数量。使用动态事件值来区分这些事件。这样您就可以根据事件值参数来优化投放，并使用<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">应用内事件原始数据报告</Anchor>中的事件值进行数据分析。
> * 利用<Anchor target="_blank" href="/marketers/zh/docs/implement-validation-rules-to-prevent-fraud">验证规则</Anchor>，将多余的应用内事件从AppsFlyer平台中移除。

> 📄 **示例**
>
> 您有一个名为com.greatapp的应用，该应用针对每种已出售的袜子颜色发送一个购买事件，如buy\_red\_socks、buy\_blue\_socks、buy\_white\_socks等等。为了避免上报过多的独立事件，您使用单个事件名buy\_socks来概括这些事件，并将袜子颜色信息作为一个<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">事件参数</Anchor>添加到该购买事件中。

</Accordion>

<div id="exceeded_keywords_limit" />

<Accordion title="Exceeded_Keywords_Limit">

* 一天内每个渠道下独立关键词的数量上限为1000个。
  * 也就是说，任意一天内，从第1001个开始的所有关键词信息都会被归到名为**Exceeded\_Keywords\_Limit**的渠道分组下。

</Accordion>

<div id="exceeded_mediasource_limit" />

<Accordion title="Exceeded_MediaSource_Limit">

* 一天内独立媒体渠道名称的数量上限为1000个。
  * 也就是说任意一天内，从第1001个媒体渠道开始，所有渠道的投放信息都会被归到名为**Exceeded\_MediasSource\_Limit**的渠道分组中。

</Accordion>

<div id="exceeded_siteid_limit" />

<Accordion title="Exceeded_SiteID_Limit">

子渠道ID（分点击、展示、激活和应用内事件）有2个限值：1000和5000。

* 一般情况下，一天内每个渠道下独立子渠道ID的数量上限为1000个。
  * 也就是说任意一天内的单个媒体渠道下，从第1001个开始的所有子渠道ID都会被归到名为**Exceeded\_SiteID\_Limit**的子渠道分组中。因此，如果您的数据表中出现名为**Exceeded\_SiteID\_Limit**的子渠道ID，即表示相关渠道下的子渠道ID数量超限，此时若针对子渠道ID进行流量优化，其准确性和有效性会有所下降。
* 从2024年8月19日起，如果一点内单个媒体渠道下的子渠道ID数量超过5000个，则数据表仅显示其中的10个子渠道ID。剩余的所有子渠道ID都会被归到一个名为**Exceeded\_SiteID\_Limit**的子渠道ID下。

> 👍 **提示**
>
> 出现超限情况时，可以使用“分治法”来解决数据细分问题。建议您在归因链接中增加一个名为**af\_sub\_siteid**的参数，避免在一个渠道下出现上千个子渠道ID，导致汇总数据失真。您可以设置少量通用的子渠道ID（最好不超过50个），然后将之前所有的子渠道ID作为次级子渠道ID，放到这些通用子渠道ID下。这一方法可以帮助您：
> 1. Prevent seeing **Exceeded\_SiteID\_Limit**2. 根据重要的子渠道流量有效优化投放。
> 3. 根据原始数据中的子渠道ID和次级子渠道ID进行深度分析。

> 📘 **注意**
>
> 查看留存报告时，即使其中不包含Exceeded\_SiteID\_Limit也不表示该报告已呈现所有的子渠道ID。当子渠道ID数量超限时，面板会随机显示子渠道ID。若使用Master API获取留存数据，即可克服这一限制。

</Accordion>

## 避免数据超限的方法

### 长期方案

正常情况下，大部分广告主不会手动设置超过3000个广告系列，因此不会在数据表中看到**Exceeded**这个数据超限分组。

如果您遇到了**Exceeded**超限分组，很可能是因为您的一个或多个渠道在广告系列名称、子渠道ID、广告组名称或广告名称中使用了动态值。应用代码中的动态应用内事件也可能会导致事件数量超限，并产生**Exceeded\_Events\_Limit**超限分组。

> 👍 **提示**
>
> 建议在应用内事件、广告系列、子渠道ID、广告组和广告名称中仅使用静态值，避免出现**Exceeded**数据超限分组。
>
> 另请参见上文针对各个**Exceeded**超限分组的具体解决方式。

### 短期方案

长期方案的实施可能需要数天到数周的时间。

在此期间，如需解决当前的数据超限问题，可参考下文说明。

如前文所述，当AppsFlyer在一天内收到N+1个点击（或事件）带量渠道时，数据表中就会出现**Exceeded**超限分组。这时有可能发生这样的情况：某个较为重要的渠道由于数据送达时间较晚而被归到**Exceeded**超限分组中。这种情况下，您可以使用以下方式来减轻**Exceeded**分组带来的影响：

> 👍 **提示**
>
> 忽略当天数据，仅查看前一天及之前的数据。AppsFlyer的数据汇总流程每天都会重新计算前一天的数据，并将流量最小的（而非数据到达最晚的）渠道归到**Exceeded**分组中。这样就能在数据超限的情况下，尽可能地减少结果失真所产生的影响。

<div data-zendesk-anchors="what-are-exceeded-dimensions=%E8%B6%85%E9%99%90%E7%BB%B4%E5%BA%A6%E7%9A%84%E5%90%AB%E4%B9%89 h_01J1VY82KFVMRW99RK0SXWSEZ4=%E8%B6%85%E9%99%90%E7%BB%B4%E5%BA%A6%E7%9A%84%E5%90%AB%E4%B9%89 h_01J1VY82KFXYA0XCA1XFVTJ2DZ=%E7%A4%BA%E4%BE%8B cardinality-limits-per-dimension=%E6%AF%8F%E4%B8%AA%E7%BB%B4%E5%BA%A6%E7%9A%84%E6%95%B0%E6%8D%AE%E8%A1%8C%E6%95%B0%E9%99%90%E5%88%B6 h_01J1VY82KF5WP6PJQ1MKYPP7YY=%E6%AF%8F%E4%B8%AA%E7%BB%B4%E5%BA%A6%E7%9A%84%E6%95%B0%E6%8D%AE%E8%A1%8C%E6%95%B0%E9%99%90%E5%88%B6 h_01J1VY82KF9XQ08EQ2BH89B6QK=exceeded_adset_limit-and-exceeded_ad_limit h_01J1VY82KFM4VAD4FG5CEKTQK6=%E6%8F%90%E7%A4%BA h_01J1VY82KFWMF6DN3XNFSWBFHH=exceeded_adsetid_limit-and-exceeded_adid_limit h_01J1VY82KFF7AWBCB54KRPJNS4=exceeded_campaign_limit h_01J1VY82KFBPK2PAHSSMCER6TW=%E6%8F%90%E7%A4%BA-1 h_01J1VY82KF4TFVTGQ31RCE3QK7=exceeded_campaignid_limit h_01J1VY82KFXPX63XKKKTZ9AWN1=exceeded_channels_limit h_01J1VY82KFRDRVNEAG6S72Q1T4=exceeded_events_limit h_01J1VY82KFYXAXTJ613VAN1PXX=%E6%8F%90%E7%A4%BA-2 h_01J1VY82KF48N1M8DZ89XQBJTD=%E7%A4%BA%E4%BE%8B-1 h_01J1VY82KFAFK03F3SDJBA5ZNX=exceeded_keywords_limit h_01J1VY82KFV85460FCZB77EY1A=exceeded_mediasource_limit h_01J1VY82KFQG2ZGF91F80X2AAK=exceeded_siteid_limit h_01J1VY82KFMD2DJWDYXF8528CY=%E6%8F%90%E7%A4%BA-3 h_01J1VY82KFQRVCAW82ZSNJ96G7=%E6%B3%A8%E6%84%8F how-to-avoid-getting-exceeded-sources=%E9%81%BF%E5%85%8D%E6%95%B0%E6%8D%AE%E8%B6%85%E9%99%90%E7%9A%84%E6%96%B9%E6%B3%95 h_01J1VY82KFE9E2DNRNPBRQSW22=%E9%81%BF%E5%85%8D%E6%95%B0%E6%8D%AE%E8%B6%85%E9%99%90%E7%9A%84%E6%96%B9%E6%B3%95 the-long-term-solution=%E9%95%BF%E6%9C%9F%E6%96%B9%E6%A1%88 h_01J1VY82KFDBASKPRK2GJ16FDZ=%E9%95%BF%E6%9C%9F%E6%96%B9%E6%A1%88 h_01J1VY82KFSWQ2Y4WSSASYDFWR=%E6%8F%90%E7%A4%BA-4 the-short-term-solution=%E7%9F%AD%E6%9C%9F%E6%96%B9%E6%A1%88 h_01J1VY82KFR7Z8422MYFK71ET8=%E7%9F%AD%E6%9C%9F%E6%96%B9%E6%A1%88 h_01J1VY82KF83SADWJCESRNSJCJ=%E6%8F%90%E7%A4%BA-5" />

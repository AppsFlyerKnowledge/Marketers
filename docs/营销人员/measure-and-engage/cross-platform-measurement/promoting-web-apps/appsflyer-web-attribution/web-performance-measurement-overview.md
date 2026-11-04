---
title: 网页端效果衡量 - 概述
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T15:07:53Z'
  edited_at: '2026-10-14T10:00:25Z'
  id: 43521734577809
  locale: zh-cn
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/zh-cn/articles/43521734577809
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概览：** 网页端效果衡量可帮助您了解哪些媒体渠道和广告系列为网站带来用户，并衡量这些访问对用户后续行为产生的影响。网页端效果衡量可以端到端采集用户互动并完成归因，覆盖从首次访问到生命周期价值衡量的全过程，同时支持新客获取（首次访问者）和再互动衡量。

<div id="about-web-performance-measurement" />

## 关于网页端效果衡量

网页端归因指识别哪些媒体渠道和广告系列为网站带来用户，以及这些渠道和广告系列如何影响用户的后续行为。

用户每次访问网站时，系统既会记录此次浏览，也会将访问前的最后一次广告互动与此次访问关联。移动归因需要对点击和激活进行匹配，而网站访问的目标URL和标头中已包含营销来源数据，因此可以立即完成初始匹配。

本文将为您介绍网页端效果衡量的完整流程，说明从用户首次访问网站直至衡量生命周期价值的整个过程中，如何采集、识别和衡量用户互动。借助这一流程，衡量引擎既能识别首次访问网站的用户并完成归因，也能衡量再营销或再互动广告系列对再次访问用户的影响。

<div id="if-you-use-people-based-attribution-pba" />

#### 如果您正在使用People-Based Attribution（PBA）

如果您目前使用<Anchor target="_blank" href="/marketers/zh/docs/people-based-attribution-pba">People-Based Attribution（PBA）</Anchor>，建议迁移至网页端效果衡量，以获得更精细的归因结果和更多数据信号。

<div id="the-web-performance-measurement-flow" />

### 网页端效果衡量流程

网页端效果衡量按照一套规范流程，将原始网站访问数据转化为可用于营销决策的洞察。

1. [数据采集](#1-data-collection)：系统通过Web SDK（Pixel）或服务器到服务器（S2S）API采集用户互动数据。
2. [访问记录](#2-visit-recording)[：](/docs/web-performance-measurement-overview#2-visit-recording)记录用户访问网站并生成访问事件，即使暂时无法确定流量来源。
3. [媒体渠道识别](#3-media-source-resolution)：按照预先设定的优先顺序解析URL参数，确定媒体渠道。
4. [30分钟身份识别延迟期](#4-the-30minute-identity-delay)：系统会等待30分钟后再确定归因结果，以便根据用户登录信息识别用户身份。
5. [数据拼接与身份识别](#5-stitching-and-identity-resolution)：将当前访问与持久化的Customer User ID（CUID）或浏览器Cookie关联。
6. [新客获取事件](#6-user-acquisition-ua-event)：在UA回溯窗口内记录用于判定新客获取的事件（例如`first_visit`或自定义新客获取事件）。
7. [新客获取前阶段](#7-preacquisition-period)：对首次访问与新客获取事件之间发生的事件进行归因。
8. [再互动与再次获取](#8-reengagement-and-reacquisition)：根据休眠窗口对再次访问用户（再次访问）进行归因，并判断此次再次访问属于再互动还是再次获取。
9. [LTV衡量](#9-ltv-measurement)：在归因窗口范围内，对后续事件和收入进行归因，以衡量用户生命周期价值。

<div id="the-web-performance-measurement-process---step-by-step" />

## 网页端效果衡量流程详解

以下各节将为您详细介绍每个步骤。

<div id="1-data-collection" />

<Accordion title="1. 数据采集">

用户到达落地页后，AppsFlyer必须通过已对接的监听器采集此次互动数据。

* **Web SDK（Pixel）**：一种客户端代码段，可<Anchor target="_blank" href="/marketers/zh/docs/integrate-appsflyer-web-sdk">直接部署在网站中，也可通过Google Tag Manager（GTM）部署</Anchor>。
* **服务器到服务器（S2S）API**：一种可靠的服务器端对接方式，可以绕过浏览器衡量限制和广告拦截器，并在数据发送至AppsFlyer前补充更多信息。S2S对接可以直接从客户服务器完成，也可以通过Google Tag Manager Server Side完成。

</Accordion>

<div id="2-visit-recording" />

<Accordion title="2. 访问记录">

采集会话数据后，系统会判断是否创建首次访问记录。这条记录用于预处理：系统先采集用户的原始活动数据，再识别媒体渠道并完成归因。系统不会将所有会话都记录为访问。

用户通过新会话进入网站，或访问中包含可识别的来源参数时，AppsFlyer会记录一次访问；来自排除域名的访问则不会记录。这些访问记录规则可避免重复计算会话。

详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/about-traffic-source-resolution#步骤-1记录识别访问">访问记录</Anchor>。

</Accordion>

<div id="3-media-source-resolution" />

<Accordion title="3. 媒体渠道识别">

完成数据采集和访问记录后，衡量引擎会按照预先设定的优先顺序评估相关数据。这一瀑布式匹配流程同时支持AppsFlyer专用参数和行业标准参数，因此客户**迁移期间无需更改现有归因链接**。系统会使用瀑布式匹配流程中首个匹配的信号确定访问来源。

* **PID**：系统首先检查是否存在AppsFlyer专用参数。
* **UTM参数**：如果未找到PID，系统会查找`utm_source`等标准标记。
* **点击ID**：之后，系统会查找广告平台专属ID，例如Google Click ID（`gclid`）或TikTok Click ID（`ttclid`）。
* **Referrer**:如果以上参数均不可用，系统最后会识别用户进入网站前所在页面的URL。

详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/about-traffic-source-resolution#第-2-步媒体渠道解析">媒体渠道识别</Anchor>。

</Accordion>

<div id="4-the-30minute-identity-delay" />

<Accordion title="4. 30分钟身份识别延迟期">

由于大多数用户会在访问网站后的30分钟内登录，AppsFlyer会将归因判断延迟30分钟。这段延迟期便于系统采集CUID，将Cookie已过期的再次访问用户正确关联至原始来源，避免将用户误判为「自然量」。

</Accordion>

<div id="5-stitching-and-identity-resolution" />

<Accordion title="5. 数据拼接与身份识别">

识别来源并完成30分钟延迟期后，系统会将用户分散的多个会话「拼接」为一条完整的用户旅程。

* **CUID数据拼接**：如果采集到Customer User ID（例如经过哈希处理的电子邮箱），衡量引擎会将当前会话与用户的跨设备历史记录关联。
* **Cookie回退机制**：如果无法获取CUID，系统会改用浏览器Cookie，但Cookie的稳定性较低，且仅能识别单一设备。

</Accordion>

<div id="6-user-acquisition-ua-event" />

<Accordion title="6. 新客获取事件">

完成用户身份识别后，衡量引擎会查找用于判定新客获取的特定行为。行业通常以`first_visit`为标准，但这一信号往往不够可靠——用户可能只是误点广告，或进入网站后立即离开。将注册或购买等事件设置为自定义新客获取事件，可以确保长期价值（LTV）归因至真正带来有效行为的营销来源，避免仅根据一次出于好奇的点击完成归因。

新客获取事件发生后，归因引擎会在<strong>回溯窗口（新客获取）</strong>规定的时间范围内，向前查找可归因的非自然访问。该设置规定了用户访问网站到完成新客获取事件之间允许的最长时间（默认值：30天）。如果回溯窗口内未找到非自然触点，该新客获取事件将被视为自然量，不进行归因。将网页端应用添加至AppsFlyer时，您可以设置自定义事件的回溯窗口时长。详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/configure-web-performance-measurement-settings#lookback-window-user-acquisition">回溯窗口（新客获取）</Anchor>。

您可以根据业务模式，将不同事件设为新客获取触发事件，例如：

* **完成注册事件（例如银行应用）**。仅在用户成功完成注册流程后触发新客获取事件。
* **首次下单事件（例如外卖应用）**。浏览商品或将商品加入购物车均不计入，仅在交易成功后触发该事件。
* **订阅激活事件（例如流媒体或SaaS应用）**。只有确认订阅后才会记录新客获取事件；开始试用或激活应用均不计入。

有关设置新客获取事件的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/configure-web-performance-measurement-settings#获客设置">新客获取设置</Anchor>。

</Accordion>

<div id="7-preacquisition-period" />

<Accordion title="7. 新客获取前阶段">

系统识别用户身份后、正式完成新客获取前，用户旅程中可能存在一段间隔，称为新客获取前阶段。仅在使用自定义新客获取（UA）事件取代默认`first_visit`的情况下，才会涉及这一阶段。在正式完成新客获取事件（例如注册或首次购买）前，用户可能会将商品加入购物车、浏览商品或与内容互动。

AppsFlyer会采集这些新客获取前事件并归因至对应的营销来源，同时在报表中标记为「新客获取前」。新客获取前归因与新客获取后归因的主要区别在于归因窗口。在新客获取前阶段，归因窗口较短，与UA事件回溯窗口一致，因为这些事件发生在用于判定新客获取的UA事件之前。自定义UA事件触发、用户完成新客获取后，归因窗口将延长，以衡量生命周期价值（LTV），并将用户的长期价值归因至获取该用户的营销来源。

</Accordion>

<div id="8-reengagement-and-reacquisition" />

<Accordion title="8. 再互动与再次获取">

完成新客获取后，用户日后可能再次访问网站。再次访问用户点击广告并访问网站时，会触发再互动（再次访问）归因。

*再互动*面向现有用户；如果用户长时间未活跃，再次访问也可能归类为*再次获取*。如需符合再次获取条件，用户的未活跃时长必须超过**休眠窗口**（默认值：90天），即系统将用户视为「流失」前所需的连续未活跃时长。超过该窗口后，如果用户再次访问，衡量引擎会重新记录一次新客获取事件，不再将其视为普通再次访问。

详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/configure-web-performance-measurement-settings#再互动设置">再互动设置</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/configure-web-performance-measurement-settings#再次获取设置">再次获取设置</Anchor>。

</Accordion>

<div id="9-ltv-measurement" />

<Accordion title="9. LTV衡量">

无论用户由首次新客获取广告系列带来，还是通过后续再营销再次访问，最终目标都是衡量用户长期产生的总价值。成功将用户归因至某一来源后，系统会衡量用户的后续活动，计算生命周期价值（LTV）。

衡量范围由**归因窗口**控制，默认设置为「永久」。这样，重复购买、续订等后续行为都会归因至最初将用户带到网站的营销来源。借助这些长期数据，您不仅可以统计转化次数，还能确定广告系列的真实广告支出回报率（ROAS）。

有关设置**归因窗口**的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/configure-web-performance-measurement-settings#归因窗口">归因窗口</Anchor>。

</Accordion>

<div data-zendesk-anchors="about-web-attribution=%E5%85%B3%E4%BA%8E%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F h_01KGMK4P46QE2HQHADD25TPCQF=%E5%85%B3%E4%BA%8E%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F if-you-use-peoplebased-attribution-pba=%E5%A6%82%E6%9E%9C%E6%82%A8%E6%AD%A3%E5%9C%A8%E4%BD%BF%E7%94%A8people-based-attributionpba h_01KH0P7BB9KF19S8XRH49DKMZA=%E5%A6%82%E6%9E%9C%E6%82%A8%E6%AD%A3%E5%9C%A8%E4%BD%BF%E7%94%A8people-based-attributionpba the-appsflyer-web-attribution-flow=%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F%E6%B5%81%E7%A8%8B h_01KGMK4P4614EEQ28V5FV32CY5=%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F%E6%B5%81%E7%A8%8B the-appsflyer-web-attribution-process-step-by-step=%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F%E6%B5%81%E7%A8%8B%E8%AF%A6%E8%A7%A3 h_01KGMK4P46HTB82K2PH9V0E33B=%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F%E6%B5%81%E7%A8%8B%E8%AF%A6%E8%A7%A3 h_01KGMK4P46VJ0NF1FKFRS8V6J2=1-data-collection h_01KGMK4P46GWBP56NJM2ENARTR=2-visit-recording h_01KGMK4P46ZKS856R5C5KEQDBK=3-media-source-resolution h_01KGMK4P465777YN9MQ1JYZ7HT=4-the-30minute-identity-delay h_01KGMK4P46GFBZTMHDVW2MD3K1=5-stitching-and-identity-resolution h_01KGMK4P46MBT49ECD7RFHDY3X=6-user-acquisition-ua-event h_01KGMK4P46XYPVFV67F000EM6C=7-preacquisition-period h_01KGMK4P472B4TFGVR4VBH4REH=8-reengagement-and-reacquisition h_01KGMK4P47E9TPX0S26TTPW4CB=9-ltv-measurement" />

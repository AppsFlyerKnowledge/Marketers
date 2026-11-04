---
title: 通过API设置ROI360广告收入合作伙伴集成
metadata:
  keywords:
    - ad revenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-10-16T14:53:47Z'
  edited_at: '2026-10-14T10:00:48Z'
  id: 9901416616465
  locale: zh-cn
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/zh-cn/articles/9901416616465
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 通过 API 为您的 AppsFlyer 帐户或单个应用配置广告收入合作伙伴集成。

<div id="ad-revenue-partner-integration-api" />

## 广告收入合作伙伴集成 API

广告收入合作伙伴集成 API 用于：

* 为您的整个帐户设置应用级别的广告收入合作伙伴配置。
* 获取整个帐户的当前广告收入合作伙伴配置列表。

<div id="set-api" />

<Accordion title="设置 API">

**要通过 API 设置(配置)广告收入合作伙伴集成，请执行以下操作：**

1. 如何从 AppsFlyer 控制面板获取 API v2 令牌API 授权所必需的。**请注意**：这必须由帐户管理员完成。
2. 准备要包含在 API 请求中的参数，如下表所述。
3. 给开发人员提供参数值，并告诉他们遵循开发中心中的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">Set integrations API说明</Anchor>。  
   整合于次日 00:00 UTC 生效。

<div id="request-parameters" />

#### 请求参数

| 参数 | 描述 |
| --- | --- |
| 对接 | <ul><li>顶层对象，必须包括app\_id、网络和产品(下面列出)。</li><li>其他字段可以包括凭据、event\_name 和 source\_event。</li></ul> |
| app\_id | 要集成的应用程序的应用程序 ID。 |
| network | <ul><li>您要集成的合作伙伴。</li><li>有关支持的网络列表，请参阅<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">广告收入合作伙伴</Anchor> API 参数表的网络列。</li></ul> |
| 凭证： | <ul><li>网络集成需要 1 个或更多凭据。</li><li>有关凭据列表，请参阅<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">广告收入合作伙伴</Anchor> API 参数表的信条列。</li></ul> |
| event\_name | <ul><li>默认值：af\_ad\_revenue</li><li>广告主可自行调整为自定义事件名称[测试版]</li><li>如果启用设置为 false,则不需要 event\_name。</li></ul> |
| 产品 | <ul><li>集成下所有已启用产品的列表，包括参数名称、已启用以及相关的 source\_event(如下所示)。</li><li>有关每个网络支持的产品列表，请参阅<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">广告收入合作伙伴</Anchor> API 参数表的批量 API 产品列。</li></ul> |
| 特点 | <ul><li>集成类型的名称。</li><li>有关集成类型名称的列表， 请参阅 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">广告收入合作伙伴 API 参数表</Anchor>的批量 API 产品列。</li></ul> |
| enabled（启用） | <ul><li>可用值包括：<ul><li>true</li><li>false</li></ul></li><li>对于应用级集成类型，需要源事件。</li><li>如果值为 false,则 source\_event 和 event\_name 都不是必需的。</li></ul> |
| source\_event | <ul><li>仅与聚合级 S2S API 合作伙伴集成相关。</li><li>对于应用级集成类型，如果启用设置为 true,则需要一个 source\_event。</li></ul> |

</Accordion>

<div id="get-api" />

<Accordion title="获取 API">

**要通过 API 获取广告收入合作伙伴集成列表，请执行以下操作：**

1. 如何从 AppsFlyer 控制面板获取 API v2 令牌API 授权所必需的。
2. 告诉你的开发人员按照开发中心中的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">List集成API说明</Anchor>。

</Accordion>

<div id="specs-and-limitations" />

### 规格和限制

| 特点 | **说明** |
| --- | --- |
| 呼叫限制 | 单个呼叫中最多可集成 1,000 个。 |
| OAuth | 不支持通过 OAuth 集成的合作伙伴(如 Google 和 Facebook)。 |

<div data-zendesk-anchors="ad-revenue-partner-integration-api=%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4%E9%9B%86%E6%88%90-api h_01HYD2M7E1PH0ARZRF0P17K80J=%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E5%90%88%E4%BD%9C%E4%BC%99%E4%BC%B4%E9%9B%86%E6%88%90-api h_01HYD2M7E1DX9FAJ0MGN500NZV=set-api request-parameters=%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0 h_01HYD2M7E1FYY96HNM6DSHXPQ5=%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0 h_01HYD2M7E19XCCFF1NT40VBWH7=get-api specs-and-limitations=%E8%A7%84%E6%A0%BC%E5%92%8C%E9%99%90%E5%88%B6 h_01HYD2M7E1X2PEQ616PWMTWCH7=%E8%A7%84%E6%A0%BC%E5%92%8C%E9%99%90%E5%88%B6" />

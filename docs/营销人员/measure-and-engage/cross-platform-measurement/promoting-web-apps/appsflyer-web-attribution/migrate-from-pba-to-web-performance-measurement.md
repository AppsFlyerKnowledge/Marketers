---
title: 从PBA迁移至网页端效果衡量
metadata:
  keywords:
    - Developers
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
  created_at: '2026-07-26T11:53:06Z'
  edited_at: '2026-10-14T10:00:32Z'
  id: 49156441281425
  locale: zh-cn
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/zh-cn/articles/49156441281425
---
> **概览：** AppsFlyer已对网页端衡量解决方案进行升级，旧版基于用户的归因(PBA)将更新为「网页端效果衡量」。本文将为您介绍本次升级的具体变化和迁移步骤，以及报告和服务器端对接所涉及的完整字段映射。

<div id="comparing-pba-and-web-performance-measurement" />

<div id="note" />

<div id="why-were-upgrading-your-web-measurement" />

## 为何升级网页端衡量方案

网页端衡量的重要性日益凸显。许多用户会在网站上完成转化，网站也是用户进入移动应用的重要起点。网站不只是落地页，还承载着问答流程、个性化新客引导、付费墙和网页端商店等完整获客流程，往往能够以更低的获客成本吸引意向更高的用户。

AppsFlyer正在以移动端的衡量标准对网页端衡量能力进行更新。旧版网页端产品基于用户的归因(PBA)将更新为「网页端效果衡量」。新版解决方案基于AppsFlyer核心归因引擎和统一数据模型构建。除PBA现有的全部功能外，网页端效果衡量还新增了以下功能：

* **单一可信数据源**：在同一平台衡量网页端和移动应用，并统一进行成本汇总、优化回传和素材优化。
* **优化预算决策**：根据业务逻辑灵活配置归因，将更多预算投入真正有效的广告系列。
* **提升ROAS**：向广告平台发送更丰富的优化回传，并通过完整的服务器端配置衡量更多转化，让广告平台利用更优质的信号进行优化。
* **衡量真正的跨平台ROI**：衡量用户在网页端、应用及其他平台上的完整旅程。
* **简洁统一的报表**：通过统一的数据面板和报表查看所有平台的数据，每小时更新一次。

> 📘 **注意**
>
> 仅需简单操作即可完成迁移。您可以继续使用原有的Web SDK，无需修改网站代码。

> 🚧 **重要提示！**
>
> 迁移后，部分数据可能会出现差异。网页端效果衡量采用更先进、更灵活的归因逻辑，因此数据结果可能会与PBA存在差异。

<div id="web-performance-measurement-vs-pba" />

## 网页端效果衡量与PBA对比

<table><thead><tr><th>功能</th><th>说明</th><th>与PBA对比</th><th>网页端效果衡量</th></tr></thead><tbody><tr><td colspan="4"><strong>数据</strong></td></tr><tr><td>数据时效性</td><td>数据多久后可在报表中显示</td><td>✗每天更新</td><td>✓报表每小时更新，数据延迟约2小时</td></tr><tr><td>数据模型</td><td>数据结构与移动端归因数据是否一致</td><td>✗与移动端不同</td><td>✓与移动端一致，便于合并和分析</td></tr><tr><td colspan="4"><strong>报表</strong></td></tr><tr><td>活跃数据面板</td><td>按事件发生时间统计的数据面板</td><td>✓支持</td><td>✓支持</td></tr><tr><td>群组面板</td><td>获客群组表现随时间变化</td><td>✗不支持</td><td>✓支持</td></tr><tr><td>Data Locker原始数据</td><td>通过Data Locker导出并访问原始归因数据</td><td>✓支持</td><td>✓支持</td></tr><tr><td>广告层级数据颗粒度</td><td>报告可从广告系列逐层细分至广告层级</td><td>✗仅面板支持，原始数据不支持</td><td>✓面板和原始数据均支持完整的广告系列层级粒度</td></tr><tr><td>跨平台LTV</td><td>打通网页端和移动端用户旅程，呈现统一的LTV</td><td>✗不支持</td><td>✓支持</td></tr><tr><td colspan="4"><strong>成本与信号</strong></td></tr><tr><td>网页端成本</td><td>接收并报告网页端广告的支出数据</td><td>✗不支持</td><td>✓支持</td></tr><tr><td>优化回传</td><td>向广告平台回传优化信号</td><td>✗不支持</td><td>✓支持</td></tr><tr><td colspan="4"><strong>实施</strong></td></tr><tr><td>网页端SDK(Pixel)</td><td>用于衡量网页访问和事件的客户端SDK</td><td>✓支持</td><td>✓沿用原有SDK，无需对代码进行调整</td></tr><tr><td>S2S支持</td><td><b>对访问和事件进行完整的服务器端衡量</b></td><td>✗仅支持事件</td><td>✓支持事件和访问可通过服务器端实施。</td></tr><tr><td colspan="4"><strong>归因引擎</strong></td></tr><tr><td>归因窗口</td><td>可配置回溯窗口、归因窗口、再互动窗口和非活跃窗口</td><td>✗仅支持点击回溯窗口</td><td>✓支持5个可配置窗口（完全掌控）</td></tr><tr><td>自定义UA事件</td><td>定义除首次访问外还定义哪些事件属于获客事件</td><td>✗仅限首次访问</td><td>✓支持任意自定义事件，例如注册、购买</td></tr><tr><td>UA与再营销</td><td>分别对新用户获取和再互动进行归因</td><td>✗无UA概念，事件归因至最终触点</td><td>✓提供独立的UA和再营销视图，并支持双重归因</td></tr></tbody></table>

<div id="step-4-if-you-use-the-pba-brand-bundle-for-cross-platform-reporting" />

<div id="step-3-if-you-consume-pbas-raw-data-reports" />

<div id="step-2-if-you-send-events-through-the-s2s-api" />

<div id="step-1-create-a-web-app-required-everyone" />

<div id="note-1" />

<div id="migrate-to-web-performance-measurement" />

## 迁移步骤

下表将迁移流程分为5个步骤。所有客户均需创建网页端应用；其余步骤取决于当前使用的PBA功能，例如S2S API或Data Locker报告。

| 操作 | 适用对象 | 操作说明 |
| --- | --- | --- |
| 创建网页端应用 | 所有客户 | <Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer#web">创建新的网页端应用</Anchor>时，在**网页端SDK ID**字段中选择现有的网页端Dev Key。该操作可为您省去更改代码的步骤，网站上的现有代码即可继续正常运行。随后，在新应用中配置归因设置。 |
| 迁移至新版S2S API | 使用PBA S2S API的客户 | 设置<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-s2s-api-for-web-performance-measurement">新版S2S API</Anchor>。新版API同时支持访问和事件，可完全通过服务器端实施。请参阅下方的[S2S API迁移附录](#附录从pba-web-s2s迁移至新版s2s-api)。 |
| 迁移至新版Data Locker报告 | 使用PBA Data Locker报告的客户 | 在UI中启用<Anchor target="_blank" href="/marketers/zh/docs/export-web-performance-measurement-report-data-from-data-locker">新版网页端报告</Anchor>，并将BI/ETL切换至更新后的数据。新报告遵循在所有平台（包括移动应用程序、网站、CTV 和 PC）上共享的单一架构。请参阅下方的[原始数据字段映射附录](#附录原始数据报告变更)。 |
| 检查归因参数 | 建议执行 | PBA采用独立的<Anchor target="_blank" href="/marketers/zh/docs/pba-media-source-attribution-rules">媒体渠道归因规则</Anchor>。网页端效果衡量采用<Anchor target="_blank" href="/marketers/zh/docs/about-traffic-source-resolution">优化后的流量来源识别方式</Anchor>，提高分析准确性。请查看两者之间的差异，了解报告中可能出现的数据结果。请参阅下方的[流量来源识别对比附录](#附录pba与网页端效果衡量的流量来源识别对比网页端效果衡量)。 |
| 将应用归入同一产品线 | 可选 | 创建产品线，并将网页端应用与移动应用归入同一产品线，即可使用<Anchor target="_blank" href="/marketers/zh/docs/beta-user-based-cross-platform-attribution">跨平台用户LTV报告</Anchor>，功能类似于PBA Brand Bundle。 |

> 📘 **注意**
>
> 迁移后，部分数据可能会出现差异。网页端效果衡量采用更先进、更灵活的归因逻辑，因此数据结果可能会与PBA存在差异。**<Anchor target="_blank" href="/marketers/zh/docs/about-traffic-source-resolution#步骤-1记录识别访问">应用打开记录逻辑</Anchor>保持不变。按照行业标准，系统仍会将30分钟内的用户活动记录为同一次应用打开。**

<div id="capabilities-being-discontinued" />

## 停用的功能

| 功能 | 具体变化 | 详细说明 |
| --- | --- | --- |
| 转化路径 | 已弃用。 | — |
| 网页端助攻激活（网页端广告系列推动用户后续完成移动端激活，并获得助攻归因） | 不再提供专门的「网页端助攻激活」视图。 | Web-to-app用户旅程可通过智能脚本和智能横幅进行衡量。跨平台报告可提供类似的分析，但结果并不完全相同。与PBA一样，该报告基于CUID：<ul><li>此前由网页端广告系列助攻、并报告为自然激活的用户，现在将显示为非自然用户获取。此类情况不再视为助攻，网页端广告系列将作为获客来源。</li><li>**如果网页端广告系列助攻了一次非自然激活，网页端广告系列将被视为用户获取来源，移动端激活则会被视为跨平台再营销。**</li></ul> |
| 回溯重算 | 除默认延迟的30分钟外，系统不会回溯重算此前数据。 | 系统将在延迟30分钟内确定归因结果，用户可在此期间完成身份识别。 |
| 原始数据字段 | 网页端不再支持移动端相关字段。部分字段将重命名，部分字段值也会发生变化。 | 请参阅下方的[原始数据字段映射附录](#附录原始数据报告变更)。 |
| 延迟传入的S2S事件 | 如果事件在发生当日UTC时间结束30分钟后才传入，系统仍会接收该事件，但会将事件时间替换为AppsFlyer收到事件的时间。 | 请实时发送事件，最好在事件发生后30分钟内发送，不要将事件汇总后每日一次性上传。为确保归因准确，请尽量在事件发生后及时传入数据。这会使网页端与移动端现有的处理逻辑保持一致。 |

<div id="note-2" />

<div id="raw-data-field-mapping" />

## 附录：原始数据报告变更

本附录逐一列出了PBA原始数据报告（网站访问和网站事件）中所有字段与新版终端用户事件报告字段之间的映射关系。来源：<Anchor target="_blank" href="/marketers/zh/docs/pba-raw-data-reports">PBA原始数据报告</Anchor>。

范围：PBA网站访问和网站事件报告。

* **未变更**：字段名称和数据均保持不变。
* **已更名**：数据保持不变，但列名称已更新。
* **已重新定义**：字段名称相同或相近，但数据或值格式发生变化，继续使用前需仔细检查。
* **已弃用**：新版报告中没有对应字段。

| 字段名称 | 说明 | 状态 | 新字段/备注 |
| --- | --- | --- | --- |
| `advertising_id` | 广告ID(GAID) | 已弃用 | 移动端/设备广告ID，PBA使用该字段关联跨平台数据。跨平台LTV和用户旅程报告基于CUID，不使用此字段。 |
| `af_web_id` | 由网页端SDK发送的Cookie ID | 已更名 | `appsflyer_id_value`，对应同一个网页端Cookie。 |
| `amazon_aid` | Amazon Fire TV广告ID | 已弃用 | 移动端/设备ID，不适用于网页端。 |
| `android_id` | Android设备ID | 已弃用 | 移动端/设备ID，不适用于网页端。 |
| `app_id` | 最近安装的应用ID | 已弃用 | 移动端跨平台字段。新版报告中的网页端应用标识符为`unified_app_id`(「website-`{domain}`」)，两者含义不同。 |
| `app_name` | 最近安装的应用名称 | 未变更 | `app_name`。 |
| `app_version` | 最近安装的应用版本 | 已弃用 | 移动端跨平台字段，不适用于网页端。 |
| `appsflyer_id` | AppsFlyer（激活）ID | 已弃用 | 移动端激活ID。新版`appsflyer_id_value`为网页端Cookie(`af_web_id`)，属于不同的标识符。 |
| **`attributed_touch_time`** | 归因网站访问的时间戳 | 已更名 | `event_time__attribution`，即归因触点（广告交互）的发生时间。 |
| **`attributed_touch_type`** | 触点类型，固定为「web visit」 | 已弃用 | 该字段在PBA中为固定值。目前通过`end_user_event_type`(SESSION/IN\_APP)区分访问和事件。 |
| **`bundle_id`** | PBA组合ID | 已弃用 | 跨平台报告改用产品线分组，将网页端应用和移动应用归入同一产品线。 |
| **`campaign`** | 归因至网站访问 | 已更名 | `campaign_name`。 |
| **`campaign_id`** | 归因至网站访问 | 未变更 | `campaign_id`。 |
| **`city`** | 根据IP地址识别 | 未变更 | `city`。 |
| **`country_code`** | 根据IP地址识别 | 未变更 | `country_code`。 |
| **`customer_user_id`** | 客户用户ID(CUID) | 未变更 | `customer_user_id`。 |
| **`device_type`** | 设备类型 | 已更名 | `device_category`，字段值有所不同（「Desktop」与「MOBILE\_PHONE」/「TV」）。 |
| **`dma`** | 根据IP地址识别 | 未变更 | `dma`。 |
| **`event_name`** | 访问：固定为「website visit」。事件：传入的事件名称 | 已重新定义 | 访问记录中为空（PBA中记录为“website visit”）。事件记录保持不变。 |
| **`event_revenue`** | 以购买币种计算的事件收入金额 | 已更名 | `revenue_value_original`。 |
| **`event_revenue_currency`** | `event_revenue`对应的3位币种代码 | 已更名 | `revenue_currency_original`。 |
| **`event_revenue_usd`** | 将`event_revenue`换算为美元后的金额 | 已更名 | `revenue_usd`。 |
| **`event_source`** | 网页端SDK或服务器到服务器(S2S) | 未变更 | `event_source`。 |
| **`event_time`** | 访问：访问时间。事件：事件发生时间 | 未变更 | `event_time`。 |
| **`event_type`** | 标准事件/转化事件/网站访问 | 已重新定义 | 不再提供转化事件标记。目前通过`end_user_event_type`(SESSION/IN\_APP)区分访问和事件。 |
| **`event_url`** | 事件发生页面的URL（对于访问记录，该值与原始URL相同） | 未变更 | `event_url`，目前也是获取URL查询参数（UTM等）的主要字段。 |
| **`event_value`** | 事件：JSON格式的事件详情。访问：空值 | 未变更 | `event_value`。 |
| **`idfa`** | 广告标识符 | 已弃用 | 移动端/设备ID，不适用于网页端。 |
| **`idfv`** | 广告标识符 | 已弃用 | 移动端/设备ID，不适用于网页端。 |
| **`imei`** | 设备标识符 | 已弃用 | 移动端/设备ID，不适用于网页端。 |
| **`install_time`** | 最近一次应用激活时间 | 已弃用 | 移动端跨平台字段。网页端用户获取（转化）时间由`event_time__conversion`记录，两者含义不同。 |
| **`ip`** | 访客IP地址 | 已更名 | `ip_address_value`，字段值不变；另新增`ip_address_type`，用于记录哈希处理方式。 |
| **`language`** | User Agent报告的语言（例如「English」） | 已重新定义 | `language`，字段值格式改为ISO 639-1语言代码和国家/地区代码。 |
| **`media_channel`** | 归因至网站访问（「Ad」） | 已弃用 | 如有需要，可通过`sub_param_1-5`获取相关信息。 |
| **`media_source`** | 归因至网站访问 | 未变更 | `media_source`。 |
| **`media_type`** | 归因至网站访问（「Paid」） | 已弃用 | 网页端记录中为空。目前通过`is_organic`布尔值区分自然流量和付费流量。 |
| **`oaid`** | 广告标识符 | 已弃用 | 移动端/设备ID，不适用于网页端。 |
| **`original_url`** | 归因访问中的重定向URL | 已更名 | 已合并至`event_url`（在访问记录中，`event_url`与原始URL相同）。不再提供单独的列。 |
| **`platform`** | 平台（「macOS」「Windows」） | 已重新定义 | 平台固定为「WEBSITE」。操作系统信息已移至`os_version`/`user_agent`。 |
| **`postal_code`** | 根据IP地址识别 | 未变更 | `postal_code`。 |
| **`query_params` **| 重定向URL中的查询参数，以JSON格式记录 | 已弃用 |** 原始查询字符串保存在`event_url`中，不再提供解析后的JSON列。** |
| **`referrer`** | 归因网站访问的HTTP Referrer | 已更名 | `http_referrer`。 |
| **`region`** | 根据IP地址识别（「NA」） | 已更名 | `continent`，即大洲代码，例如「NA」。 |
| **`state`** | 根据IP地址识别 | 未变更 | `state`。 |

<div id="readytouse-codingagent-prompt-for-data-locker-etl-migration" />

<Accordion title="用于Data Locker ETL迁移的AI编程智能体提示词">

为了简化迁移流程，我们准备了一段可以直接用于AI编程智能体（Claude Code、Cursor或类似工具）的提示词。授予智能体访问现有ETL代码的权限，然后粘贴下方提示词。提示词中包含完整的字段映射和所有处理逻辑差异。智能体将分析当前的数据管道，并根据新版报告重新构建数据管道。

```
You are migrating an ETL pipeline from AppsFlyer's legacy PBA Data Locker raw-data reports (Website visits + Website events) to AppsFlyer's Web Performance Measurement Data Locker report (End User Events). Everything you need is in this prompt: the structural changes, the complete field-by-field mapping, and the validation steps. Do not guess anything beyond what is written here; if something is ambiguous, ask me.

## Step 1: Learn the current pipeline

Before writing any code, explore the existing codebase and produce an inventory:
1. Which PBA reports we consume (Website visits, Website events, or both) and where they are ingested.
2. Every PBA field we read, and where each is used downstream (transforms, joins, dashboards, alerts, exports).
3. The load cadence and scheduling assumptions (PBA delivered daily).
4. Any logic that separates or joins visit rows and event rows.
5. Any filters, groupings, or hardcoded values keyed on PBA field values (e.g. media_source names, channel labels, event_type, platform values).

Present this inventory to me and wait for my confirmation before proceeding.

## Step 2: Ask me these questions

1. Is the new End User Events report already enabled in Data Locker (enabled from the AppsFlyer UI)? If not, I need to enable it first.
2. What is our new web app's Unified App ID? Format: "website-{domain}" (e.g. website-www.example.com). If I don't know it, I'll get it from the AppsFlyer dashboard before we continue.
3. Do we want a parallel-run period (old and new pipelines side by side, comparing outputs) or a direct cutover? Recommend parallel-run.
4. Should the new pipeline also consume the Conversions report (unique attribution instances, no duplicate rows) or the cross-platform End User Events report (CUID-deduplicated, web+mobile user-level)? Default scope is the platform-level End User Events report, the direct successor of the PBA reports.

## Structural changes to design around

1. **One report instead of two.** PBA split visits and events into two reports. The new End User Events report holds both: visits are rows with end_user_event_type = 'SESSION', events are rows with end_user_event_type = 'IN_APP'. Only IN_APP rows carry a valid event_name; on SESSION rows event_name is empty (PBA wrote "website visit" there).
2. **One schema across platforms.** The report is shared by website, mobile, CTV, and PC. Always filter platform = 'WEBSITE' to isolate web data.
3. **Dual attribution credit, deduplicate.** The same action can appear twice: a primary-credit row and a secondary-credit row (original UA source, for UA-view LTV). Filter is_primary_attribution = true by default to avoid double-counting. Drop the filter only for dedicated UA-view vs retargeting-view analysis using conversion_type.
4. **Hourly instead of daily.** The new report delivers hourly with approximately 2 hours of data freshness. Redesign incremental loads around hourly batches instead of a daily drop.
5. **Organic vs paid.** PBA's media_type ("Paid") is gone. Use the is_organic boolean; never infer organic/paid from media_source.
6. **User counting.** Count and join users with COALESCE(customer_user_id, appsflyer_id_value), the stable customer user ID first, the cookie-based ID as fallback.
7. **Empty values.** STRING fields are '', NUMERIC fields are NULL.

## Field-by-field mapping (PBA → End User Events)

Status legend: Unchanged = same name and data. Renamed = same data, new column. Redefined = data or value format changes (handle with care). Deprecated = no equivalent.

| PBA field | Status | New field / handling |
|---|---|---|
| advertising_id | Deprecated | Mobile/device ID. Cross-platform reports are CUID-based; drop it. |
| af_web_id | Renamed | appsflyer_id_value, same web cookie. |
| amazon_aid | Deprecated | Mobile/device ID, not relevant for web. |
| android_id | Deprecated | Mobile/device ID, not relevant for web. |
| app_id | Deprecated | Mobile cross-platform field. The new web app identifier is unified_app_id ("website-{domain}"), a different concept, not a rename. |
| app_name | Unchanged | app_name. |
| app_version | Deprecated | Mobile cross-platform field. |
| appsflyer_id | Deprecated | Mobile install ID. Note: the new appsflyer_id_value is the web cookie (PBA's af_web_id), NOT this field. |
| attributed_touch_time | Renamed | event_time__attribution. |
| attributed_touch_type | Deprecated | Was a constant. Visit-vs-event now lives in end_user_event_type. |
| bundle_id | Deprecated | Replaced by the Product Line grouping in the cross-platform report. |
| campaign | Renamed | campaign_name. |
| campaign_id | Unchanged | campaign_id. |
| city | Unchanged | city. |
| country_code | Unchanged | country_code. |
| customer_user_id | Unchanged | customer_user_id. |
| device_type | Renamed + values change | device_category, values differ (e.g. "Desktop" → "MOBILE_PHONE" / "TV" style values). Update any value-keyed logic. |
| dma | Unchanged | dma. |
| event_name | Redefined | Events: unchanged. Visits: now empty (PBA wrote "website visit"). Use end_user_event_type = 'SESSION' to identify visits. |
| event_revenue | Renamed | revenue_value_original. |
| event_revenue_currency | Renamed | revenue_currency_original. |
| event_revenue_usd | Renamed | revenue_usd. |
| event_source | Unchanged | event_source. |
| event_time | Unchanged | event_time. |
| event_type | Redefined | "Conversion event" marking no longer exists. Visit-vs-event lives in end_user_event_type (SESSION / IN_APP). |
| event_url | Unchanged | event_url, now also the primary place URL query params (UTMs, etc.) are read from. |
| event_value | Unchanged | event_value. |
| idfa / idfv / imei / oaid | Deprecated | Mobile/device IDs, not relevant for web. |
| install_time | Deprecated | Mobile field. The web user-acquisition time is event_time__conversion, a separate concept. |
| ip | Renamed | ip_address_value (plus ip_address_type for the hashing method). |
| language | Redefined | language, format changes to ISO 639-1 + country code (was e.g. "English"). |
| media_channel | Deprecated | Can be covered by sub_param_1-5 if needed. |
| media_source | Unchanged | media_source (but see value renames below). |
| media_type | Deprecated | Use the is_organic boolean instead. |
| original_url | Renamed | Consolidated into event_url (on visits, event_url equals the original URL). Standalone column gone. |
| platform | Redefined | platform is always "WEBSITE". The OS moved to os_version / user_agent. |
| postal_code | Unchanged | postal_code. |
| query_params | Deprecated | The raw query string lives in event_url; the parsed-JSON column is gone. Re-implement parsing from event_url if needed. |
| referrer | Renamed | http_referrer. |
| region | Renamed | continent, continent code (e.g. "NA"). |
| state | Unchanged | state. |

## Attributed-value changes (update filters and groupings)

The attribution engine resolves traffic sources differently, so some VALUES change even where field names don't:
- media_source renames: doubleclick_int → dv360_int (Google display/video via UTM); "X Ads" → "Twitter" (Twitter via UTM). More PID values now remap to display names (e.g. iossearchads_int → Apple Search Ads, metweb_int → Facebook Ads, tiktokweb_int → tiktokglobal_int, snapweb_int → snapchat_int).
- Channel labels change format: Direct / Organic search / Social media / Email / Ad / Referral / Other become DIRECT / ORGANIC_SEARCH / SOCIAL_MEDIA / EMAIL / AD / REFERRAL / OTHER.
- Click-ID coverage expanded (more networks resolve from click IDs); dclid alone no longer resolves; fbclid is not used.

Scan the codebase for any filter, CASE, join key, or dashboard grouping keyed on these old values and update them.

## Step 3: Build

1. Propose the new ETL design (ingestion, schema, incremental hourly logic, the mandatory filters from "Structural changes").
2. After my approval, implement it, reusing our existing conventions and infrastructure.
3. For every Deprecated field the inventory found in downstream use, list the consumer and propose a resolution (drop, replace with the suggested alternative, or flag to the business owner).

## Step 4: Validate

1. Run both pipelines on the same day range and compare: visits (SESSION rows) vs PBA website visits, events (IN_APP rows) vs PBA website events, and revenue totals.
2. Expect differences, not equality: the new attribution logic is more advanced, so attributed dimensions (media_source, campaign) will not match PBA exactly. Session counting logic is unchanged (30 minutes of activity), so visit volumes should be in the same ballpark.
3. Verify the is_primary_attribution filter is applied everywhere; its absence shows up as inflated event counts.
4. Produce a short migration report: what was mapped, what was dropped, what changed in values, and any open items for the business owner.
```

</Accordion>

<div id="pba-web-s2s-to-new-s2s-api-migration" />

## 附录：从PBA Web-S2S迁移至新版S2S API

如果目前通过<Anchor target="_blank" href="/marketers/zh/docs/web-server-to-server-events-api-for-pba-web-s2s">网页端服务器到服务器事件API(Web-S2S)</Anchor>向PBA报告事件，请迁移至<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-s2s-api-for-web-performance-measurement">新版S2S API</Anchor>。新版API同时支持访问和事件，因此网站可以完全通过服务器端运行；PBA S2S仅支持接收事件。

<div id="endpoints-and-authentication" />

<Accordion title="端点与身份验证">

|  | PBA Web-S2S | 新版S2S API |
| --- | --- | --- |
| 基础URL | `https://webs2s.appsflyer.com` | `https://events.appsflyer.com` |
| 事件调用 | **`POST /v1/{bundleId}/event` **|** `POST /v2.0/s2s/inapps/app/web/{appId}`** |
| 访问调用 | 不支持（访问数据只能通过网页端SDK传入） | **`POST /v2.0/s2s/visits/app/web/{appId}`** |
| 身份关联调用 | `POST /v1/{bundleId}/setcuid`（用于将CUID与网页端用户关联的单独调用） | 无需单独调用。身份信息通过每个事件或访问的`user_id`对象直接传入。 |
| 应用标识符 | 路径中的`bundleId`（品牌组合ID） | 路径中的`appId`=网页端`unified_app_id`(「website-`{domain}`」) |
| 身份验证 | 每次调用时，在JSON正文中传入`webDevKey` | 在Authorization请求头中传入S2S API密钥 |
| 内容类型 | **`application/json` **|** `application/json`** |
| 成功响应 | 200 OK | 202 Accepted |

</Accordion>

<div id="payload-field-mapping" />

<Accordion title="请求数据字段映射">

| PBA Web-S2S字段 | 新版S2S字段 | 备注 |
| --- | --- | --- |
| **`customerUserId` **|** `user_id.customer_user_id`** | 现已嵌套在`user_id`对象中。 |
| **`afUserId` **|** `user_id.appsflyer_id`** | 现已嵌套在`user_id`对象中。至少传入`customer_user_id`或`appsflyer_id`中的一个；识别出用户身份后，请同时传入两个字段。 |
| **`webDevKey`** | — | 已从请求正文中移除。身份验证已移至Authorization请求头，应用则通过路径中的`appId`进行识别。 |
| `eventType`（固定为EVENT） | — | 已移除。类型由端点（/inapps或/visits）决定。 |
| **`eventName` **|** `event_name`** | 长度为1-64个字符，不能包含`@ = + -`。 |
| `timestamp`（Unix毫秒时间戳，13位） | `timestamp`（Unix毫秒时间戳） | 格式不变。建议每次调用时均传入；如果未传入，AppsFlyer将使用收到数据的时间。 |
| **`eventValue` **|** `event_value`** | 支持自由格式，并可包含`custom_parameters`子对象。 |
| **`eventRevenue` **|** `event_revenue`** | 现为可选字段（PBA要求必须传入，才能在面板中显示）。 |
| **`eventRevenueCurrency` **|** `event_revenue_currency`** | 现为可选字段（PBA要求必须传入，才能在面板中显示）。 |
| **`referrer` **|** `http_referrer`** | 已重命名。 |
| **`userAgent` **|** `user_agent`** | 已重命名。 |
| **`ip` **|** `ip`** | 未更改。 |
| — | **`event_url`** | 新增字段。访问调用必填，事件调用可选。 |
| — | **`customer_dedup_id`** | 新增字段。用于对来自其他来源（例如网页端SDK）的同一事件进行去重。 |
| — | `email_hashed` `phone_number_hashed` `phone_number_e164_hashed` `first_name_hashed` `last_name_hashed` | 新增字段。**对标准化后的值进行SHA256哈希处理（64位小写十六进制），用于补充身份信息。** |

</Accordion>

<div id="s2s-api-notes" />

<Accordion title="S2S API注意事项">

* <strong>访问现已支持通过服务器端传入。</strong>PBA S2S仅支持接收事件，访问数据必须通过网页端SDK传入。新版/visits端点支持网站完全通过服务器端运行。
* <strong>不再需要调用setcuid。</strong>PBA需要使用网页端SDK，因此必须单独调用接口，将CUID与网页端用户关联。新版API会在每次请求中直接传入身份信息，因此不再需要执行此步骤。
* <strong>延迟数据接收窗口。</strong>请实时发送事件和访问数据，最好在事件发生后30分钟内发送，不要将数据汇总后每日一次性上传。如果数据在事件发生当日UTC时间结束30分钟后才传入，系统仍会接收数据，但会将事件时间替换为AppsFlyer收到数据的时间。

</Accordion>

<div id="s2s-service-migration-readytouse-codingagent-prompt" />

<Accordion title="用于S2S服务迁移的AI编程智能体提示词">

如果目前通过PBA服务器到服务器API报告事件，可以使用我们为AI编程智能体（Claude Code、Cursor或类似工具）准备的提示词。授予智能体访问AppsFlyer事件发送服务的权限，然后粘贴下方提示词。提示词中包含完整的端点和请求数据映射。智能体将分析当前的实施方式，并完成新版API的实施。

```
You are migrating a server-side integration from AppsFlyer's legacy PBA Web S2S events API (webs2s.appsflyer.com) to AppsFlyer's new S2S API for Web Performance Measurement (events.appsflyer.com). Everything you need is in this prompt: endpoints, authentication, the complete payload mapping, and the behavior changes. Do not guess anything beyond what is written here; if something is ambiguous, ask me.

## Step 0: Ask me these questions before touching code

1. Should we modify the existing service in place, or create a new service/module alongside it (allowing a parallel-run and clean cutover)? Recommend a new module alongside.
2. Do I know our new web app's Unified App ID? Format: "website-{domain}" (e.g. website-www.example.com). It replaces PBA's bundle ID in the URL path. If I don't know it, I'll get it from the AppsFlyer dashboard before we continue.
3. Do I have the new S2S API key? Authentication moved from the webDevKey in the request body to an Authorization header carrying this key. If I don't have it, I'll retrieve it from the AppsFlyer dashboard.
4. Do we want to send events only (like PBA), or adopt the new visits endpoint too? The new API supports server-side visits, so the website can run fully server-side; PBA accepted events only.
5. Is the AppsFlyer Web SDK still running on our site? (Determines whether visits come from the SDK and whether we need event deduplication between SDK and S2S.)

## Step 1: Learn the current service

Explore the codebase and produce an inventory:
1. Every call site to webs2s.appsflyer.com, the /event calls and any /setcuid calls.
2. The fields populated on each call (customerUserId, afUserId, eventName, eventValue, eventRevenue, timestamp, referrer, userAgent, ip, etc.) and where their values come from.
3. Error handling and monitoring keyed on the 200 OK response.
4. Retry, batching, and queueing behavior.

Present this inventory to me and wait for my confirmation before proceeding.

## What changed: endpoints and authentication

|  | PBA Web-S2S (old) | New S2S API |
|---|---|---|
| Base URL | https://webs2s.appsflyer.com | https://events.appsflyer.com |
| Event call | POST /v1/{bundleId}/event | POST /v2.0/s2s/inapps/app/web/{appId} |
| Visit call | Not available | POST /v2.0/s2s/visits/app/web/{appId} |
| Identity call | POST /v1/{bundleId}/setcuid | None, identity is inline in the user_id object on every call |
| App identifier in path | bundleId (brand bundle ID) | appId = the web Unified App ID ("website-{domain}") |
| Authentication | webDevKey in the JSON body | Authorization header with the S2S API key |
| Content type | application/json | application/json (415 if missing) |
| Success response | 200 OK | 202 Accepted |

## Payload field mapping

| PBA field | New field | Note |
|---|---|---|
| customerUserId | user_id.customer_user_id | Nested in the user_id object. |
| afUserId | user_id.appsflyer_id | Nested in the user_id object. Send at least one of customer_user_id or appsflyer_id; send both whenever the user is identified. |
| webDevKey | (removed) | Auth moved to the Authorization header; the app is identified by appId in the path. |
| eventType (always "EVENT") | (removed) | The endpoint (/inapps vs /visits) determines the type. |
| eventName | event_name | 1-64 chars; cannot contain @ = + - characters. |
| timestamp (Unix ms) | timestamp (Unix ms) | Same format. Recommended on every call; if omitted, AppsFlyer uses receive time. |
| eventValue | event_value | Free-form; supports a custom_parameters sub-object. |
| eventRevenue | event_revenue | Now optional (PBA required it for dashboards). |
| eventRevenueCurrency | event_revenue_currency | Now optional (PBA required it for dashboards). |
| referrer | http_referrer | Renamed. |
| userAgent | user_agent | Renamed. |
| ip | ip | Unchanged. |
| (new) | event_url | Required on visits; optional on events. |
| (new) | customer_dedup_id | Deduplicates against the same event arriving from another source (e.g. the Web SDK). |
| (new) | email_hashed, phone_number_hashed, phone_number_e164_hashed, first_name_hashed, last_name_hashed | SHA256 (64-char lowercase hex) of normalized values, for identity enrichment. |

## Behavior changes and gotchas

1. **appId is the Unified App ID, not the "Web SDK ID".** The AppsFlyer app settings page shows a "Web SDK ID" UUID (the former Web Dev Key, kept for SDK continuity). The S2S path must carry the Unified App ID ("website-{domain}"), never that UUID. A 401 "app not found" usually means a wrong appId in the path or a missing/invalid Authorization header.
2. **Success is 202, not 200.** Update health checks, retries, and alerting accordingly.
3. **Don't validate against the old endpoint.** The legacy endpoint may still return 200, but that response is not proof that data reached Web Performance Measurement. Always verify events actually appear in the new web app's data.
4. **Drop the setcuid flow entirely.** Identity travels inline in the user_id object on every event and visit.
5. **Visits before events.** The system expects a visit before any event from a user; events for a user with no prior visit are classified as organic. Visits come from the Web SDK, or, new, from the /visits endpoint.
6. **Send in real time; don't batch.** Send every event and visit as it happens, preferably within 30 minutes of the event occurring. Data that arrives later than 30 minutes after the end of the UTC day in which the event occurred is still accepted, but its event time is replaced with the receive time, which distorts attribution. Always send a timestamp. Note that the approximately 30-minute attribution delay you may read about is a separate, server-side hold on AppsFlyer's side, nothing for us to implement.
7. **Full server-side option (if we adopt visits).** With no Web SDK, our server owns the web user identifier: generate a stable ID for first-time visitors, persist it as a server-set first-party HTTP cookie (Set-Cookie header, not JavaScript; JS cookies are capped at approximately 7 days on Safari), reuse it on every request, and send it as user_id.appsflyer_id. The visit payload must include event_url (and should include ip, user_agent, http_referrer for attribution quality).
8. **SDK + S2S together.** If both send the same event, populate customer_dedup_id so AppsFlyer keeps one copy.

## Step 2: Build

1. Propose the design: new client/module, config (base URL, appId, API key storage in our secrets manager, never hardcoded), payload builders for events (and visits, if in scope), and the response/retry handling for 202.
2. After my approval, implement it following our existing conventions.
3. Map every field from the inventory through the payload mapping above; flag any field we currently send that has no new equivalent.

## Step 3: Validate

1. Send a test event (and visit, if in scope) and confirm a 202 response.
2. Verify the test data appears in the new web app in AppsFlyer (dashboard or Data Locker); this is the real success signal, not the HTTP response.
3. Confirm event names comply with the new constraints (1-64 chars, no @ = + -).
4. If running in parallel with the old service, compare event volumes between old and new for a few days before cutover, then decommission the old calls including setcuid.
```

</Accordion>

<div id="important" />

<div id="traffic-source-resolution-pba-vs-web-performance-measurement" />

## 附录：PBA与网页端效果衡量的流量来源识别对比网页端效果衡量

如果媒体渠道、渠道或广告系列值与PBA报告中的结果不同，您可以在本节了解具体原因。两种方案采用相同的基本逻辑：根据网站访问中的URL参数和HTTP Referrer识别媒体渠道，并按照优先级顺序逐项匹配，以首个匹配结果为准。但部分规则已发生变化，因此报告中显示的值也会有所不同。来源：<Anchor target="_blank" href="/marketers/zh/docs/pba-media-source-attribution-rules">PBA媒体渠道归因规则</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/about-traffic-source-resolution">流量来源识别简介</Anchor>。

<div id="media-source-values-renamed" />

<Accordion title="媒体渠道值更名">

| 触发条件 | PBA值 | 新值 |
| --- | --- | --- |
| Google展示广告/视频广告（utm\_source=Google+utm\_medium=cpm/display/banner/video/listing） | **`doubleclick_int` **|** `dv360_int`** |
| 通过UTM识别的Twitter（twitter+cpc） | X Ads | Twitter |

网页端效果衡量还会将更多PID值映射为对应的显示名称，例如将`iossearchads_int`映射为Apple Search Ads、`metweb_int`映射为Facebook Ads、`twitterweb_int`映射为Twitter、`tiktokweb_int`映射为`tiktokglobal_int`、`snapweb_int`映射为`snapchat_int`。基于旧版原始值构建的报告需要调整，以适配新的字段值。

</Accordion>

<div id="click-id-coverage-expanded-and-dclid-dropped" />

<Accordion title="扩大Click ID覆盖范围，不再使用dclid">

PBA可识别3种Click ID：将`gclid`识别为`googleadwords_int`、`dclid`识别为`doubleclick_int`、`msclkid`识别为`bingsearch_int`。

网页端效果衡量支持识别更多Click ID：将`gclid`/`wbraid`/`gbraid`识别为`googleadwords_int`、`msclkid`识别为`bingsearch_int`、`twclid`识别为Twitter、`vmcid`识别为`yahoogemini_int`、`sccid`识别为`snapchat_int`、`li_fat_id`识别为`linkedin_int`、`ttclid`识别为`tiktokglobal_int`、`tbclid`识别为`taboola_int`、`ob_click_id`/`dicbo`识别为`outbrain_int`、`yclid`识别为`yandex_int`、`rdt_cid`识别为`reddit_int`。

> ❗️ **注意**
>
> 处理逻辑有两项变化：系统不再单独使用`dclid`识别流量来源（PBA会将其识别为`doubleclick_int`），并且明确不使用`fbclid`。

</Accordion>

<div id="utm-custom-rules-expanded" />

<Accordion title="扩展UTM自定义规则">

网页端效果衡量扩大了自定义`utm_source`+`utm_medium`映射的覆盖范围，支持更多medium同义值（paid、paid\_search、paid-search等），并新增对TikTok、Snapchat和Pinterest的支持。相比之下，PBA仅支持少量单一medium规则。如果没有匹配的自定义规则，两种方案均会使用`utm_source`的原始值。

</Accordion>

<div id="channel" />

<Accordion title="渠道">

渠道**值**的格式也会发生变化，由PBA中的Direct/Organic search/Social media/Email/Ad/Referral/Other改为DIRECT/ORGANIC\_SEARCH/SOCIAL\_MEDIA/EMAIL/AD/REFERRAL/OTHER。使用旧版标签设置的筛选条件和分组需要相应更新。

</Accordion>

<div data-zendesk-anchors="why-were-upgrading-your-web-measurement=%E4%B8%BA%E4%BD%95%E5%8D%87%E7%BA%A7%E7%BD%91%E9%A1%B5%E7%AB%AF%E8%A1%A1%E9%87%8F%E6%96%B9%E6%A1%88 h_01KYM7JM37WVTV7XHEHVTPKWM9=%E4%B8%BA%E4%BD%95%E5%8D%87%E7%BA%A7%E7%BD%91%E9%A1%B5%E7%AB%AF%E8%A1%A1%E9%87%8F%E6%96%B9%E6%A1%88 h_01KYM7JM375VPAAVQEN43F2X73=%E6%B3%A8%E6%84%8F h_01KYM7JM37WTAX6JTQFZJ189TK=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA web-performance-measurement-vs-pba=%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F%E4%B8%8Epba%E5%AF%B9%E6%AF%94 h_01KYM7JM3711FXC132MSC3B4A8=%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F%E4%B8%8Epba%E5%AF%B9%E6%AF%94 migration-steps=%E8%BF%81%E7%A7%BB%E6%AD%A5%E9%AA%A4 h_01KYM7JM37HG8YAX02XMSKBTPP=%E8%BF%81%E7%A7%BB%E6%AD%A5%E9%AA%A4 h_01KYM7JM37ZHHDBR961W2XGWPN=%E6%B3%A8%E6%84%8F-1 capabilities-being-discontinued=%E5%81%9C%E7%94%A8%E7%9A%84%E5%8A%9F%E8%83%BD h_01KYM7JM37JJ25D3RFE2V7BM4D=%E5%81%9C%E7%94%A8%E7%9A%84%E5%8A%9F%E8%83%BD appendix-raw-data-reports-changes=%E9%99%84%E5%BD%95%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E5%8F%98%E6%9B%B4 h_01KYM7JM37Z7Z21FJ2G83T2WPG=%E9%99%84%E5%BD%95%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E5%8F%98%E6%9B%B4 h_01KYM7JM38PDKMST3E5CWN3NC1=readytouse-codingagent-prompt-for-data-locker-etl-migration appendix-pba-web-s2s-to-new-s2s-api-migration=%E9%99%84%E5%BD%95%E4%BB%8Epba-web-s2s%E8%BF%81%E7%A7%BB%E8%87%B3%E6%96%B0%E7%89%88s2s-api h_01KYM7JM38K9C01XDZY99KZVTX=%E9%99%84%E5%BD%95%E4%BB%8Epba-web-s2s%E8%BF%81%E7%A7%BB%E8%87%B3%E6%96%B0%E7%89%88s2s-api h_01KYM7JM38NY2VQKWGV884M79N=endpoints-and-authentication h_01KYM7JM38RBC9SCJ3YESYP68H=payload-field-mapping h_01KYM7JM38H9EJZDF9441XBRHQ=s2s-api-notes h_01KYM7JM38RS0DZ13ZW228S9EB=s2s-service-migration-readytouse-codingagent-prompt appendix-traffic-source-resolution-pba-vs-web-performance-measurement=%E9%99%84%E5%BD%95pba%E4%B8%8E%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F%E7%9A%84%E6%B5%81%E9%87%8F%E6%9D%A5%E6%BA%90%E8%AF%86%E5%88%AB%E5%AF%B9%E6%AF%94%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F h_01KYM7JM387R5YEYJK9CD0AQJ0=%E9%99%84%E5%BD%95pba%E4%B8%8E%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F%E7%9A%84%E6%B5%81%E9%87%8F%E6%9D%A5%E6%BA%90%E8%AF%86%E5%88%AB%E5%AF%B9%E6%AF%94%E7%BD%91%E9%A1%B5%E7%AB%AF%E6%95%88%E6%9E%9C%E8%A1%A1%E9%87%8F h_01KYM7JM388C143S76GH58DEZB=media-source-values-renamed h_01KYM7JM380B4S13JDW9FWHMWT=click-id-coverage-expanded-and-dclid-dropped h_01KYM7JM3889HC2VTC1QN9JAZG=%E6%B3%A8%E6%84%8F-2 h_01KYM7JM38CNVZ43EFK0HMJ3VY=utm-custom-rules-expanded h_01KYM7JM38E9P4MS4Q6TNZ1TH1=channel" />

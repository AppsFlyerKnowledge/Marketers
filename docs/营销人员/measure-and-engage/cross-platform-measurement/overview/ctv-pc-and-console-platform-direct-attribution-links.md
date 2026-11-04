---
title: CTV、PC和主机端的直接归因链接
metadata:
  keywords:
    - Advertiser
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2023-05-10T10:21:14Z'
  edited_at: '2026-10-14T10:12:52Z'
  id: 15199908310801
  locale: zh-cn
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/zh-cn/articles/15199908310801
---
> **概要：**  本文针对适用于CTV、PC和主机端的AppsFlyer归因链接，介绍了其结构和参数。**请注意**：如需了解适用于安卓和iOS应用的归因链接，包括PC端的安卓游戏，请参考<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">移动端归因链接说明</Anchor>。

<div id="overview" />

## 速览

广告主能通过**CTV、PC和主机端**的直接归因链接为用户实现跳转，并在点击发生之后收集数据。直接归因链接是一种AppsFlyer链接，支持**单平台应用的单平台跳转和归因**，跳转后到达的网址通过链接中af\_r参数的值来表达。

**请注意**：如需了解适用于安卓和iOS应用的归因链接，包括PC端的安卓游戏，请参考<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">移动端归因链接说明</Anchor>。

您可以直接创建归因链接并将其设置在广告中。如需创建此类链接，请按照本文说明操作。

另外，您也可以使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_click-app-platform-app-id">Engagements API</Anchor>通过S2S的方式创建链接。如选择这种方式，需要引入开发人员协助。**请注意**：通过S2S的方式创建的链接也可以收集展示数据。

<div id="attribution-link" />

### 归因链接

| 参数 | 在这个区间之外的值 |
| --- | --- |
| 基础链接 | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| 必须配置的路径参数 | <ul><li>platform<br />示例：steam</li><li>app\_id<br />示例：123456</li></ul> |
| 必须配置的查询参数 | <ul><li>af\_media\_source</li><li>af\_campaign\_id</li></ul> |
| 其他参数 | [查看所有参数](/docs/ctv-pc-and-console-platform-direct-attribution-links#参数) |
| 链接结构 | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |
| 示例URL | `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=aloha&af_campaign_id=1234&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello` |

<div id="parameters" />

### 参数

| 参数 | 通过数据导出和Pull API获取的原始数据中显示的字段名称 | 说明 | 字段类型 |
| --- | --- | --- | --- |
| platform | Platform（系统平台） | <ul><li>路径参数，用于说明应用所在的系统平台</li><li>可能出现的值为：<ul><li>smartcast</li><li>tizen</li><li>roku</li><li>webos</li><li>vidaa</li><li>playstation</li><li>steam</li><li>quest</li><li>battlenet</li><li>epic</li><li>switch</li><li>xbox</li><li>nativepc</li></ul></li></ul> | 字符串 |
| app\_id | App ID（应用ID） | <ul><li>路径参数，用于说明您推广的应用所带的应用ID。</li><li>示例：`ap123456`</li><li>请勿在App ID值前添加平台前缀。例如，如果App ID为`ap123456`，平台为`platformX`，请勿将`platformX_ap123456`用作`app_id`值。</li></ul> | 字符串 |
| af\_media\_source | Media Source（媒体渠道） | AppsFlyer平台所定义的渠道唯一标识符  <br />不支持下列字符：;、*、!、@、#、?、$、^、:、&、~、\`、=、+、’、>、&lt;、/、\{、\}、%。 | 字符串 |
| af\_campaign | Campaign | 即广告系列的名称 | 字符串 |
| af\_campaign\_id | 即广告系列的ID | 即广告系列的ID | 字符串 |
| af\_request\_id | 不适用 | 渠道用于识别相关请求的唯一标识符 | 字符串 |
| af\_adset | Adset | 即广告组的名称 | 字符串 |
| af\_adset\_id | 即广告组的ID | 即广告组的ID | 字符串 |
| af\_ad | Ad | 即相关广告的名称 | 字符串 |
| af\_ad\_id | 即相关广告的ID | 即相关广告的ID | 字符串 |
| af\_campaign\_type | campaign\_type | 可以是以下两类广告系列中的任意一种：<ul><li>user\_acquisition（获客）</li><li>retargeting（再营销）</li></ul> | 字符串 |
| af\_prt | Partner | <ul><li>代理账号的名称，在链接中添加该参数后可将激活归因到相关代理</li><li>**注意事项**：如需使用此参数，请务必先开放**代理权限**。</li></ul> | 字符串 |
| af\_siteid | Site ID | <span id="query-getImpressionAppPlatformApp_id_af_siteid__description"></span>用于识别子渠道的唯一标识符。 | 字符串 |
| af\_sub\_siteid | Sub Site ID | <span id="query-getImpressionAppPlatformApp_id_af_sub_siteid__description"></span>次级广告平台/子渠道的ID。 | 字符串 |
| af\_click\_id | 不适用 | <span id="query-getImpressionAppPlatformApp_id_af_click_id__description"></span>广告平台的交易标识符 | 字符串 |
| af\_lookback\_window | 不适用 | <ul><li>回溯窗口适用于通过ID匹配完成的归因。</li><li>回溯窗口期可按天数或小时数自行调整。可用的参数值为：1d-30d（天）或1h-23h（小时）。</li><li>请确保：参数值使用上述格式，长度不超过三个字符。</li><li>广告展示的默认回溯窗口为24小时，广告点击的默认回溯窗口为7天。</li></ul> | 字符串 |
| af\_ad\_placement | 不适用 | <span id="query-getImpressionAppPlatformApp_id_af_ad_placement__description"></span>广告平台的交易标识符 | 字符串 |
| af\_ad\_type | Ad Type | <ul><li>即广告样式。请使用以下命名方式配置参数值：<ul><li>**text**（文本）：仅包含文本的广告，比如搜索结果</li><li>**banner**（横幅）；显示在设备屏幕顶部或底部的基础样式</li><li>**interstitial**（插屏）：在当前体验暂停时出现的全屏广告</li><li>**video**（视频）：无奖励的标准视频</li><li>**rewarded\_video**（奖励视频）：向观看视频的用户提供应用内奖励的广告</li><li>**playable**（可玩广告）：包含预览式互动体验的广告</li><li>**audio**（音频）：音频广告</li></ul></li><li>区分大小写。</li></ul> | 字符串 |
| af\_channel | Channel | <span id="query-getImpressionAppPlatformApp_id_af_channel__description"></span>相关媒体渠道的流量入口，用于分发广告，比如UAC\_Search、UAC\_Display、Instagram、Meta Audience Network等。 | 字符串 |
| af\_model | Device Model | 设备型号 | 字符串限长64 |
| af\_os\_version | 不适用 | <ul><li>设备的操作系统版本</li><li>仅可使用数字和句点</li><li>举例来说，8.1.0</li></ul> | 字符串 |
| af\_device\_id\_type | 不适用 | <span id="query-getImpressionAppPlatformApp_id_af_device_id_type__description"></span>设备标识符类型。可以是以下任意一种：<ul><li>vida</li><li>tifa</li><li>rida</li><li>lgudid</li><li>fire</li><li>advertising\_id</li><li>fire</li><li>custom</li></ul> | 字符串 |
| af\_device\_id\_value | 不适用 | <span id="query-getImpressionAppPlatformApp_id_af_device_id_value__description"></span>设备的标识符类型 | 字符串 |
| af\_r | 不适用 | <ul><li>跳转到适配应用商店的或落地页的链接</li><li>af\_r参数中包含的所有值都必须编码。如果其末尾添加了UTM参数值，这些值也需要编码。</li></ul>**请注意：** 请确保在<Anchor target="_blank" href="/marketers/zh/docs/set-up-your-domain-redirect-allowlist">跳转白名单</Anchor>中加入af\_r参数使用的URL域名。 | 字符串 |

<div id="traits-and-limitations" />

## 特点与局限性

| 回溯窗口 | 概率模型归因中，广告点击和广告展示的回溯窗口固定不变，都是24小时。此时af\_lookback\_window值会被忽略。 |
| --- | --- |
| 代理归因 | <ul><li>CTV-PC-主机端到移动端的归因流程支持代理归因，</li><li>但移动端到CTV-PC-主机端的归因流程不支持代理归因。</li></ul> |

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 01H7Z1003GTTMRY072BXWDFNP0=%E9%80%9F%E8%A7%88 attribution-link=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 01H7Z1003G0WYBCK3530064WM1=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 attribution-link-parameters=%E5%8F%82%E6%95%B0 01H7Z1003GNC551PDCKKFQMPVN=%E5%8F%82%E6%95%B0 traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HVED5DJPFR5XCWYDSYCHMCR6=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />

---
title: 原始数据限制——媒体渠道或设备标识符
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2020-03-23T08:29:01Z'
  edited_at: '2026-10-14T10:10:13Z'
  id: 360006868017
  locale: zh-cn
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/zh-cn/articles/360006868017
---
> **概要：** 部分渠道要求AppsFlyer在特定的原始数据报告中限制某些字段的呈现，其他渠道则会要求第三方平台共享回传时掩去媒体渠道信息。本文解释了相关的限制及其影响。

## 原始数据限制

为了符合广告主的<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">AAP</Anchor>设置，或遵守相关广告平台的数据共享政策，AppsFlyer会限制原始数据报告中部分字段的可用性。具体的限制内容取决于报告的类型以及限制原因。

### 媒体渠道数据限制

下表列出了各媒体渠道对于转化、点击和展示的数据限制。

> 📘 **注意**
>
> * 汇总层级的归因和分析数据不受限制，仍然可用。但所有回传和设备级别数据的报告会受到下文所述的限制。
> * <Anchor target="_blank" href="/marketers/zh/docs/discrepancies-between-appsflyer-and-third-party-platforms#第三方平台的回传限制">第三方平台的回传限制：</Anchor>
>   * 发送到第三方平台（如数据分析平台和营销平台等）的回传中所包含的事件受到下表所列的限制。
>   * 其它事件可能会有进一步的回传限制。

| Media source（媒体渠道） | 受限的归因类型 |
| --- | --- |
| <span id="amazon-ads"></span>亚马逊广告 | 来自Amazon Ads的原始数据在AppsFlyer平台中的呈现会受到限制。在原始数据中，该平台的媒体渠道名称会显示为“restricted”（受限），且广告系列信息为null。<br /><br />原始数据报告中不会呈现来自Amazon Ads（以及其他SRN）的点击和展示。 |
| <span id="meta-ads"></span>Meta ads | <ul><li>点击及浏览型归因数据受到限制。</li><li>AEM深度链接解决方案（适用于iOS）所产生的数据以及来自Google Play Install Referrer和Meta Install Referrer（适用于安卓）在原始数据报告中不受限制，可供使用。</li></ul><ul><li>来自Meta ads的点击和展示不包含在原始数据报告中</li></ul> |
| <span id="pinterest"></span>Pinterest | <ul><li>点击及浏览型归因数据受到限制。</li><li>来自Pinterest的点击和展示不包含在原始数据报告中</li></ul> |
| <span id="reddit"></span>Reddit | <ul><li>自2024年10月22日起，来自Reddit的原始数据在AppsFlyer平台中的呈现会受到限制。该平台的媒体渠道名称会显示为“restricted”（受限）。来自Reddit的点击和展示不包含在原始数据报告中</li></ul> |
| <span id="roku-oneview"></span>Roku OneView | <ul><li>2024年4月18日之前的Roku OneView点击和展示不包含在原始数据报告中</li></ul> |
| <span id="samsung-dsp"></span>Samsung DSP | <ul><li>自2023年10月17日起，来自Samsung DSP的点击和展示不包含在原始数据报告中</li></ul> |
| <span id="snapchat"></span>Snapchat | <ul><li>从2023年3月1日开始，原始数据报告不再呈现Snapchat的卸载（Uninstalls）数据</li><li>浏览型归因受到限制，原始数据传输工具中相关字段限制如下：<ul><li>Media source（snapchat\_int）</li><li>Channel</li><li>Attributed touch type（广告互动类型，显示为“impression”）</li><li>Attributed touch time（广告互动时间，该字段仅上报日期，格式为“dd/mm/yyyy”）</li><li>Campaign（显示为“*restricted*”）</li></ul></li><li>来自Snapchat的点击和展示不包含在原始数据报告中</li></ul> |
| <span id="tiktok-for-business"></span>TikTok for Business | <ul><li>Media source（显示为bytedanceglobal\_int和tiktokglobal\_int）<ul><li>Channel</li><li>Attributed touch type（广告互动类型，显示为“impression”）</li><li>Attributed touch time（广告互动时间，该字段仅上报日期，格式为“dd/mm/yyyy”）</li><li>Campaign（显示为“*restricted*”）</li></ul></li><li>来自bytedanceglobal\_int的展示在原始数据中受限</li><li>Data Locker的点击和展的原始数据报告中不包含tiktokglobal\_int的点击和展示数据。</li></ul> |
| <span id="x-ads-formerly-twitter"></span>X Ads（前身为Twitter） | <ul><li>在某些情况下，X Ads不允许AppsFlyer呈现原始数据，这时原始数据报告中不会包含相关的事件。</li><li>来自X Ads的点击和展示不包含在原始数据报告中</li></ul> |

### 原始数据报告类型

字段层级的原始数据限制取决于数据所在的报告类型，详情请见下表。

| 限制类型 | 受限报告 |
| --- | --- |
| [受限媒体渠道](/docs/about-raw-data-identifier-restrictions#媒体渠道数据限制)：用户来源信息 | <ul><li>归因：激活、再营销转化、卸载</li><li>应用内事件、应用打开（session）</li><li>Protect360报告</li></ul> |
| 完全受限 | <ul><li>Clicks</li><li>Impressions</li><li>被拦截的点击（Protect360）</li></ul> |

**原始数据传输**

AppsFlyer的用户级别归因数据是通过以下原始数据传输工具传输的：

* Data Locker
* Pull API原始数据
* Push API
* 面板的导出数据页
* 发送给广告平台的回传
* 客户侧用户层级数据API中的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">GCD API</Anchor><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">（获取转化数据）</Anchor>

<div id="unavailable-attribution-fields" />

<Accordion title="不可用的归因字段">

媒体渠道信息受限时不可用的字段如下：

| 字段名称 | API 名称 |
| --- | --- |
| Ad | af\_ad |
| 广告ID | af\_ad\_id |
| 广告样式 | af\_ad\_type |
| Adset | af\_adset |
| 广告组ID | af\_adset\_id |
| 归因回溯窗口期 | af\_attribution\_lookback |
| Campaign ID | af\_c\_id |
| Channel | af\_channel |
| Cost currency | af\_cost\_currency |
| Cost model | af\_cost\_model |
| Cost value | af\_cost\_value |
| Keywords | af\_keywords |
| 适用渠道 | af\_prt |
| 子渠道ID | af\_siteid |
| Sub site ID | af\_sub\_siteid |
| Sub param [n] (n=1-5) | af\_sub[n] (n=1-5) |
| Attributed touch time | attributed\_touch\_time |
| Attributed touch type | attributed\_touch\_type |
| Campaign | campaign |
| Contributor [n] media source (n=1-3) | contributor[n]\_media\_source (n=1-3) |
| Contributor [n] partner (n=1-3) | contributor[n]\_af\_prt (n=1-3) |
| Contributor [n] campaign (n=1-3) | contributor[n]\_campaign (n=1-3) |
| Contributor [n] match type (n=1-3) | contributor[n]\_match\_type (n=1-3) |
| Contributor [n] touch time (n=1-3) | contributor[n]\_touch\_time (n=1-3) |
| Contributor [n] touch type (n=1-3) | contributor[n]\_touch\_type (n=1-3) |
| 深度链接URL | deeplink\_url |
| HTTP Referrer | http\_referrer |
| Install app store（带来激活的应用商店） | install\_app\_store |
| Keyword ID | keyword\_id |
| Keyword match type | keyword\_match\_type |
| Match type | match\_type |
| Network account ID | network\_account\_id |
| Original URL | original\_url |
| 再互动窗口期 | af\_reengagement\_window |
| 自定义产品页面 | store\_product\_page |

</Accordion>

<div id="identifier-restriction" />

<Accordion title="标识符数据限制">

标识符数据受限时，原始数据报告中仅包含下表所列的字段。

| API 名称 |
| --- |
| <span id="event_time"></span>event\_time |
| <span id="event_name"></span>event\_name |
| <span id="event_revenue"></span>event\_revenue |
| <span id="event_revenue_currency"></span>event\_revenue\_currency |
| <span id="event_revenue_usd"></span>event\_revenue\_usd |
| <span id="af_cost_model"></span>af\_cost\_model |
| <span id="af_cost_value"></span>af\_cost\_value |
| <span id="af_cost_currency"></span>af\_cost\_currency |
| <span id="event_source"></span>event\_source |
| <span id="media_source"></span>media\_source |
| <span id="af_channel"></span>af\_channel |
| <span id="campaign"></span>campaign |
| <span id="af_c_id"></span>af\_c\_id |
| <span id="af_adset"></span>af\_adset |
| <span id="af_adset_id"></span>af\_adset\_id |
| <span id="af_ad"></span>af\_ad |
| <span id="af_ad_id"></span>af\_ad\_id |
| <span id="af_ad_type"></span>af\_ad\_type |
| <span id="af_siteid"></span>af\_siteid |
| <span id="af_sub_siteid"></span>af\_sub\_siteid |
| <span id="app_id"></span>app\_id |
| <span id="app_name"></span>app\_name |
| <span id="bundle_id"></span>bundle\_id |
| <span id="is_retargeting"></span>is\_retargeting |
| <span id="retargeting_conversion_type"></span>retargeting\_conversion\_type |
| <span id="is_primary_attribution"></span>is\_primary\_attribution |
| <span id="af_attribution_lookback"></span>af\_attribution\_lookback |
| <span id="af_reengagement_window"></span>af\_reengagement\_window |
| <span id="country_code"></span>country\_code |
| <span id="blocked_reason"></span>blocked\_reason |
| <span id="blocked_reason_value"></span>blocked\_reason\_value |
| <span id="blocked_reason_rule"></span>blocked\_reason\_rule |
| <span id="blocked_sub_reason"></span>blocked\_sub\_reason |
| <span id="platform"></span>platform |
| <span id="is_paid_media"></span>is\_paid\_media |

</Accordion>

## 常见问题解答

<div id="what-events-are-restricted" />

<Accordion title="哪些是受限事件？">

[上表](/docs/about-raw-data-identifier-restrictions#媒体渠道数据限制)详细列出了受限事件，其中可能包含实施数据限制的广告平台所带来的转化（激活和再互动）以及相关的应用内事件。

</Accordion>

<div id="how-does-the-restricted-media-source-impact-raw-data-reports" />

<Accordion title="媒体渠道信息受限对原始数据报告有什么影响？">

* *media source*字段显示为*restricted*。
* 本文所列的归因字段皆为空或*null*。

**报告示例：** <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv">原始数据受限</Anchor>的激活报告（CSV文件）。其他原始数据报告的填充方式相同。

</Accordion>

<div id="what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted" />

<Accordion title="媒体渠道受限对发送给渠道的回传有何影响？">

发送到渠道的回传数据中不含归因字段。

</Accordion>

<div id="how-do-restricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="受限事件对发送给第三方平台的回传有何影响？">

发送到带量广告平台的回传数据（见[上表](#媒体渠道数据限制)）不会发送给第三方平台。

</Accordion>

<div id="do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="非受限事件对发送给第三方平台的回传有何影响？">

<Anchor target="_blank" href="/marketers/zh/docs/discrepancies-between-appsflyer-and-third-party-platforms#第三方平台的回传限制">部分情况下</Anchor>，向第三方平台发送的非受限事件回传中不包含媒体渠道信息，这表示该次转化归因到自然量。

</Accordion>

<div id="what-about-the-data-of-assists-that-form-part-of-the-attribution" />

<Accordion title="对构成归因的助攻数据又有什么影响？">

与助攻相关的数据是归因数据，因此不可用。

</Accordion>

> 📄 **相关文档**
>
> <Anchor target="_blank" href="/marketers/zh/docs/user-level-data-retention">用户级别数据的保留规定</Anchor>

<div data-zendesk-anchors="raw-data-restriction=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E9%99%90%E5%88%B6 01H7WQHTV9RM2JF2BV45XF626H=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E9%99%90%E5%88%B6 media-source-restrictions=%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E6%95%B0%E6%8D%AE%E9%99%90%E5%88%B6 01H7WQHTV9HJEHHH1N8VN6APX6=%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E6%95%B0%E6%8D%AE%E9%99%90%E5%88%B6 01H7WQHTV90YFRP3Z9AEP7ACRD=%E6%B3%A8%E6%84%8F raw-data-context=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E7%B1%BB%E5%9E%8B 01H7WQHTVA8H9FTBJ1FB6BJQ2A=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E7%B1%BB%E5%9E%8B 01H7WQHTVA0XP6B2H95EEM7EYD=unavailable-attribution-fields 01H7WQHTVA7ERWW1PC3DF5H0NP=identifier-restriction faq=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WQHTVA5439QPE6GNXNKJ63=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HDBND48E05P1WV51ZJGD072N=what-events-are-restricted 01H7WQHTVAHCK7QDZ5P25YRQ2D=how-does-the-restricted-media-source-impact-raw-data-reports 01H7WQHTVABKATP6B6XN4NRC54=what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted h_01HDBND48EDTAFBFXTADGWJADM=how-do-restricted-events-impact-postbacks-to-thirdparty-platforms h_01HE5TK3WSNBPM6W5D1Y9S6PDX=do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms 01H7WQHTVA60PWZ017WJMRTKVP=what-about-the-data-of-assists-that-form-part-of-the-attribution h_01HE7SCVN3VJ4Y6KF2QZSNBEMZ=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

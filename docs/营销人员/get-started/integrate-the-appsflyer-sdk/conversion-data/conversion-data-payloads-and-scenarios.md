---
title: 转化数据有效信息及使用场景
metadata:
  keywords:
    - Conversion
    - Retargeting
    - Installs
    - Re-attribution
    - Re-engagement
    - Developers
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-31T13:05:33Z'
  edited_at: '2026-10-14T10:07:07Z'
  id: 360000726098
  locale: zh-cn
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000726098
---
> **概要：** 本文介绍了如何利用转化数据识别各种转化场景、打造定制化用户体验等等。

<div id="overview" />

## 速览

下文说明了各种用户转化场景及其对应的转化数据有效信息（payloads）。

* [用户获取（UA）](#srn的ua转化数据)
* [再营销](#再营销转化数据)

您可以使用以下任一方式获取AppsFlyer平台中的转化数据：

* <Anchor target="_blank" href="/marketers/zh/docs/raw-data-export-page">原始数据报告</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/push-api-streaming-raw-data">Push API</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">AppsFlyer SDK</Anchor>

由于数据准确性和延时之间存在此消彼长的关系，因此同一个设备ID的转化数据可能会因API而异。

<div id="non-organic-conversion-data-payload-fields" />

### 非自然转化数据的payload字段

<div id="fields-always-available" />

#### 总是呈现的字段

无论**非自然**来自哪个媒体渠道(`media_source`)，其payloads中总是包含的下表所列的字段。

| payload字段名称 | 原始数据字段名称 | 说明 |
| --- | --- | --- |
| `media_source` | 媒体渠道 | 获得归因的媒体渠道。等同于归因链接中的`pid`参数。 |
| `install_time` | Install time |  |
| `click_time` | Attributed touch time | 点击或展示发生的时间，以UTC时间计算 |
| `is_first_launch` | 不适用 | 可能出现的值为`true`和`false` |
| `af_status` | 原始数据分别呈现在自然量和非自然量两个报告中。 | `"Non-organic"` |
| `af_siteid` | Site ID |  |
| `adgroup_id` | Ad ID（广告ID） |  |
| `adset` | Adset |  |
| `adset_id` | Adset ID（广告组ID） |  |
| `agency` | Partner | `null`或代理名称（适用于代理代投的广告） |
| `campaign` | Campaign |  |
| `campaign_id` | Campaign ID（广告系列ID） |  |
| `http_referrer` | HTTP Referrer |  |
| `retargeting_conversion_type` | Retargeting Conversion Type（再营销转化类型） | “none”或者retargeting\_conversion\_type |
| `af_sub[n] (n=1—5)` | Sub Param [n]（n=1–5） |  |

<div id="fields-available-in-some-cases" />

#### 部分情况下会呈现的字段

下表列出了部分情况下会出现的字段，具体取决于SRN对于相关事件的填充方式。

<table><thead><tr><th>payload字段名称</th><th>原始数据字段名称</th><th>说明</th><th> </th></tr></thead><tbody><tr><td><code>af_channel</code></td><td>流量入口（Channel）</td><td><p>会填充该字段的SRN包括：</p><ul><li>AppLovin</li><li>Google Ads</li><li>Meta ads</li><li>Snapchat</li><li>TikTok for Business</li><li>X Ads</li></ul><p>举例来说，Facebook—Instagram、Google—YouTube </p></td><td> </td></tr><tr><td><code>orig_cost</code></td><td> </td><td>备注（1）</td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td> </td><td>备注（1）</td><td> </td></tr><tr><td><code>af_cpi</code></td><td> </td><td>备注（1）</td><td> </td></tr><tr><td colspan="4"><p><strong>注意事项</strong></p><p>（1）成本字段的值由广告平台提供。您必须在<a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank"><strong>活跃对接</strong></a>页面中打开成本对接，才能让广告平台将成本数据分享给AppsFlyer。部分SRN支持成本数据的批量分享，这时事件层级的成本字段返回的值为0。 </p></td></tr></tbody></table>

<div id="additional-fields" />

### 可选的非默认字段

* <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#归因链接参数">AppsFlyer参数列表</Anchor>
* 您可以在归因链接中添加参数，添加完毕后，这些参数就会出现在payload中

详情请见<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#data-fields-dictionary">原始数据字段词典</Anchor>

<div id="limitations" />

### 局限性

<div id="custom-parameter-names" />

<Accordion title="自定义参数名称">

自定义参数的名称不能设置为`name`（注意这里是小写“n”，`Name`仍是有效的参数名）。

任何名为`name`的参数都会被移除，不会出现在payload中。

</Accordion>

---

<div id="ua-conversion-data-with-srns" />

## SRN的UA转化数据

<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">自归因平台</Anchor>（SRN）是指实行其自有归因机制的广告平台，如Meta ads和Google。

SRN不使用归因链接。也就是说：

* payload字段是预先定义好的
* 在归因链接后拼接参数不能使payload中呈现其他字段

SRN会向AppsFlyer上报转化数据，然后AppsFlyer将这些转化数据呈现在相关应用的面板中。其中可用的字段因SRN而异，详情请见下文的SRN部分。

<div id="a-note-about-meta-ads" />

#### Meta ads注意事项

如果您在Meta ads上投放广告，但未签署Meta的服务条款，AppsFlyer仍能对相关的激活进行归因，但报告可用性会有以下限制：

* **可用：** 汇总和分析数据的面板和报告
* **不可用：** 原始数据

<Tabs>
<Tab title="Meta ads">

<div id="meta-ads-conversion-data" />

### Meta ads转化数据

| 字段名称 | 说明 | 数据来源 |
| --- | --- | --- |
| `match_type` | `srn`、`gp_referrer` | AppsFlyer |
| `media_source` | 字段值总是为`Facebook Ads` | AppsFlyer |
| `agency` | 若不使用代理，则字段值为`null`；若通过代理投放<Anchor target="_blank" href="/partners/zh/docs/about-agency-accounts#srn配置">Meta ads广告</Anchor>，则字段值为代理名称 | Meta ads |
| `http_referrer` | 字段值总是为`null` | Meta ads |
| `retargeting_conversion_type` |  | AppsFlyer |
| `af_channel` |  | Meta ads（publisher\_platform） |
| `af_status` | 字段值总是为`Non-organic` | AppsFlyer |
| `ad_id` | 仅供Meta ads内部使用。 | Meta ads（ad\_id） |
| `click_time` |  | AppsFlyer |
| `install_time` |  | AppsFlyer |
| `is_first_launch` | 可能出现的值为`true`和`false` | 设备 |
| `adset_id` | 在原始数据中可用，对应字段为：Adset ID | Meta ads (campaign\_id) |
| `is_fb` | 字段值总是为`true` | AppsFlyer |
| `campaign` | 在原始数据中可用，对应字段为Campaign Name | Meta ads（campaign\_group\_name） |
| `campaign_id` | 在原始数据中可用，对应字段为：Campaign ID | Meta ads（campaign\_group\_id） |
| `is_paid` | 字段值总是为`true` | Meta ads |
| `adgroup` | 在原始数据中可用，对应字段为Ad | Meta ads（adgroup\_name） |
| `adgroup_id` | 在原始数据中可用，对应字段为Ad ID | Meta ads（adgroup\_id） |
| `adset` | 在原始数据中可用，对应字段为Adset | Meta ads（campaign\_name） |
| `af_siteid` | 字段值总是为`null` | Meta ads |
| `af_sub[1-5]` | 字段值总是为`null` | 广告主 |

**请注意：** 与成本有关的字段不可用，这是因为Meta ads不会在转化发生时共享成本数据。如果您开通了<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-integration-setup#cost-clicks-and-impressions">成本共享</Anchor>，Meta ads会与AppsFlyer共享成本，频次为一天数次。

</Tab>

<Tab title="Google Ads">

<div id="google-ads-conversion-data" />

### Google Ads转化数据

<table><thead><tr><th>字段名称</th><th>说明</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>字段值总是为<code>srn</code> </td></tr><tr><td><code>media_source</code></td><td>字段值总是为<code>googleadwords_int</code> </td></tr><tr><td><code>agency</code></td><td> 字段值为<code>none</code>或<code>af_prt</code>的值 </td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td><code>af_channel</code></td><td><p>备注（1）</p></td></tr><tr><td><code>af_status</code></td><td>字段值总是为<code>Non-organic</code> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>、<code>false</code> </td></tr><tr><td><code>adgroup_name</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td>字段值总是为<code>null</code> </td></tr><tr><td><code>campaign</code></td><td>备注（3）</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>adset</code></td><td>备注（3）</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>ad_event_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td>空字符串</td></tr><tr><td><code>af_ad_id</code></td><td>空字符串</td></tr><tr><td><code>af_ad_type</code></td><td><span>AdWords广告类型</span></td></tr><tr><td><code>af_adset</code></td><td><span>在原始数据中可用，对应字段为：Adset</span></td></tr><tr><td><code>af_adset_id</code></td><td>在原始数据中可用，对应字段为：Adset ID</td></tr><tr><td><code>af_c_id</code></td><td>在原始数据中可用，对应字段为：Campaign ID</td></tr><tr><td><code>af_click_lookback</code></td><td></td></tr><tr><td><code>af_cpi</code></td><td>备注（2）</td></tr><tr><td><code>af_dp</code></td><td>仅适用于<a href="./google-ads-adwords-integration-setup-for-advertisers#在应用广告中使用延迟深度链接" target="_blank">Google的信息流应用广告</a>（App campaigns in Feeds）</td></tr><tr><td><code>af_keywords</code></td><td>在原始数据中可用，对应字段为：Keywords（关键词）</td></tr><tr><td><code>af_prt</code></td><td> 字段值为<code>none</code>或<code>af_prt</code>的值 </td></tr><tr><td><code>af_reengagement_window</code></td><td>在原始数据中可用，对应字段为：再互动窗口期 </td></tr><tr><td><code>af_viewthrough_lookback</code></td><td>在原始数据中可用，对应字段为：展示归因的窗口期</td></tr><tr><td><code>click_url</code></td><td>在原始数据中可用，对应字段为：HTTP Referrer</td></tr><tr><td><code>click-timestamp</code></td><td>数据来源：AppsFlyer</td></tr><tr><td><code>cost_cents_USD</code></td><td>备注（2）</td></tr><tr><td><code>external_account_id</code></td><td>AdWords账户ID</td></tr><tr><td><code>gclid</code></td><td> </td></tr><tr><td><code>lat</code></td><td> </td></tr><tr><td><code>network</code></td><td>备注（1）</td></tr><tr><td><code>orig_cost</code></td><td>备注（2）</td></tr><tr><td><code>video_id</code></td><td>字段值总是为<code>null</code> </td></tr><tr><td colspan="2"><p><strong>备注</strong><br/>（1）由于Google旗下有多个广告平台，您可以结合使用<code>af_channel</code>和<code>network</code>来判断相关激活具体来自哪一个平台。<br/>（2） 这些字段会返回0值。如果广告主开放了成本数据共享，Google会以一天数次的频率向AppsFlyer发送成本数据。<br/>（3）您可以使用<code>campaign</code>和<code>af_adset</code>向不同用户群体展示特定的内容。</p></td></tr></tbody></table>

</Tab>

<Tab title="ASA">

<div id="twitter-conversion-data" />

<div id="tiktok-for-business-conversion-data" />

<div id="x-ads-conversion-data" />

<div id="snapchat-conversion-data" />

<div id="apple-search-ads-conversion-data" />

### Apple Search Ads转化数据

<table><thead><tr><th>字段名称</th><th>说明</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>字段值总是为<code>srn</code> </td></tr><tr><td><code>media_source</code></td><td>字段值总是为<code>Apple Search Ads</code> </td></tr><tr><td><del><code>adset</code></del></td><td>备注（2）</td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><del><code>af_adset</code></del></td><td>备注（2）</td></tr><tr><td><code>af_adset_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>备注（1）</td></tr><tr><td><del><code>af_keywords</code></del></td><td><p>备注（2）—使用关键词ID（keywords ID）</p></td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>字段值总是为<code>Non-organic</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td> 字段值为<code>null</code>或<code>af_prt</code>的值 </td></tr><tr><td><del><code>campaign</code></del></td><td>备注（2）</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>、<code>false</code> </td></tr><tr><td><code>cost_cents_USD</code></td><td>备注（1）</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>备注（1）</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr></tbody><tbody><tr><td colspan="3"><p><strong>备注</strong><br/>（1）Apple Search Ads支持批量化成本共享，但不支持在转化数据中分享成本数据。<br/>（2）由于Apple Search Ads采用了dServices AP，因此已在2021年2月15日下线。</p></td></tr></tbody></table>

</Tab>

<Tab title="Snapchat">

### Snapchat转化数据

| 字段名称 | 说明 |
| --- | --- |
| `match_type` | 可能出现的值为`srn`、`gp_referrer`、`id_matching`、`probabilistic`  <br />该平台的高级SRN对接支持所有匹配类型 |
| `media_source` | `snapchat_int` |
| `adset` |  |
| `adset_id` |  |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_c_id` |  |
| `af_channel` |  |
| `af_cpi` |  |
| `af_siteid` |  |
| `af_status` | 字段值总是为`Non-organic` |
| `af_sub[1-5]` |  |
| `af_viewthrough_lookback` |  |
| `agency` |  |
| `campaign` |  |
| `campaign_id` |  |
| `click_time` |  |
| `cost_cents_USD` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `orig_cost` |  |
| `retargeting_conversion_type` |  |

</Tab>

<Tab title="X Ads">

### X Ads转化数据

| 字段名称 | 说明 |
| --- | --- |
| `match_type` | 字段值总是为`srn` |
| `media_source` | 字段值总是为`Twitter` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_channel` |  |
| `af_siteid` |  |
| `af_status` | 字段值总是为`Non-organic` |
| `af_sub[1-5]` |  |
| `agency` | 字段值总是为`null` |
| `campaign` |  |
| `campaign_id` | `null`或Campaign ID |
| `click_time` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` | `true`、`false` |
| `adgroup` |  |
| `adgroup_id` |  |
| `retargeting_conversion_type` | 字段值总是为`none` |

**请注意：** 由于X Ads不支持成本数据共享，因此payload中不包含成本数据。

</Tab>

<Tab title="TikTok">

<div id="tiktok-conversion-data" />

### TikTok for Business的转化数据

| 字段名称 | 说明 |
| --- | --- |
| `match_type` | 可能出现的值为`srn`、`gp_referrer`、`id_matching`、`probabilistic`  <br />该平台的高级SRN对接支持所有匹配类型 |
| `media_source` | `tiktokglobal_int` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_channel` | `tiktok`、`pangle` |
| `af_siteid` |  |
| `af_status` | 字段值总是为`Non-organic` |
| `af_sub[1-5]` |  |
| `agency` |  |
| `campaign` |  |
| `campaign_id` |  |
| `click_time` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `retargeting_conversion_type` |  |

**请注意：** 由于TikTok不支持成本数据共享，因此payload中不包含成本数据。

</Tab>

<Tab title="Oath">

<div id="oath-ad-platforms-conversion-data" />

### Oath Ad Platforms转化数据

<table><thead><tr><th>字段名称</th><th>说明</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>字段值总是为<code>srn</code> </td></tr><tr><td><code>media_source</code></td><td>字段值总是为<code>yahoogemini_int</code> </td></tr><tr><td><code>adset</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td> </td></tr><tr><td><code>af_ad_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>备注（1）</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>字段值总是为<code>Non-organic</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td> </td></tr><tr><td><code>campaign</code></td><td> </td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>campaign_type</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td>备注（1）</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>备注（1）</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td colspan="2"> <strong>备注</strong><br/>（1）Oath支持成本数据共享，但仅可批量共享，不能在转化数据中共享。</td></tr></tbody></table>

</Tab>
</Tabs>

<div id="ua-conversion-with-other-ad-networks" />

## 其他广告平台的UA转化

对于非自归因的常规广告平台，相关<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">归因链接中的参数</Anchor>会直接影响到payload中的数据。

请参考以下JSON格式的payloads。

**请注意：** 返回的转化数据呈映射结构。开发人员**不**直接接触原始JSON。

<div id="applovin" />

<Accordion title="Applovin">

<div id="attribution-link" />

#### 归因链接:

```http HTTPS
https://app.appsflyer.com/com.company.app?af_ad=ad_name&af_ad_type=INTER
  &af_channel=video&af_siteid=123_site_id&af_c_id=b8******************************&
  af_adset=_DEFAULT&pid=applovin_int&c=campaign_name
  &af_click_lookback=7d&clickid=10****************
  &advertising_id=50********************************&af_ip=
```

#### Payload：

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "applovin_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:49:54.186",
      "adgroup_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-24 14:29:33.738",
      "agency": null,
      "cost_cents_USD": "0",
      "af_ad_type": "INTER",
      "af_c_id": "b8******************************",
      "adset": null,
      "advertising_id": "50********************************",
      "af_sub1": null,
      "clickid": "10****************",
      "af_click_lookback": "7d",
      "af_siteid": "123_site_id",
      "af_ad": "ad_name",
      "http_referrer": null,
      "af_channel": "video",
      "af_adset": "_DEFAULT",
      "af_sub5": null,
      "af_sub4": null,
      "af_cpi": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* 归因链接中的参数在payload中以字段的形式呈现
* Payload中的其他参数（即**归因链接中不包含的参数**）值为null。
* AppLovin支持广告成本共享，但仅限以批量化方式向AppsFlyer发送成本数据，并在转化数据中返回0值的成本相关字段。

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

<div id="attribution-link-1" />

#### 归因链接:

```http HTTPS
https://app.appsflyer.com/id123456789?
  af_ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &clickid=ab*******************&redirect=false
  &ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &af_lang=pt&imei=&af_sub1=&advertising_id=&af_ip=192.168.0.1&pid=ironsource_int
  &device_ip=192.168.0.1&c=campaign_name
  &idfa=01**********************************&af_siteid=123_site_id&
  af_enc_data=cN*********************************************************************
```

#### Payload：

```json
{
      "adgroup": null,
      "af_enc_data": "cN**************************************************************************************",
      "campaign": "campaign_name",
      "media_source": "ironsource_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:59:32.194",
      "adgroup_id": null,
      "redirect": "false",
      "orig_cost": "0.75",
      "click_time": "2018-12-30 23:58:54.517",
     "agency": null,
      "cost_cents_USD": "75",
      "adset": null,
      "advertising_id": "35**********************************",
      "af_sub1": null,
      "af_ip": "192.168.0.1",
      "clickid": "ab*******************",
      "af_sub3": null,
      "af_cost_value": "0.75",
      "af_ref": "ironsource_5f******************************************",
      "af_siteid": "123_site_id",
      "http_referrer": null,
      "af_cost_model": "cpi",
      "af_ua": "Mozilla/5.0 (Linux; Android 8.0.0; SM-N950F Build/R16NW; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/71.0.3578.99 Mobile Safari/537.36",
      "af_cost_currency": "USD",
      "af_sub5": null,
      "af_sub4": null,
      "af_lang": "en",
      "af_cpi": null,
      "af_click_lookback": "7d",
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

ironSource会通过`orig_cost`、`cost_cents_USD`和`af_cost_value`字段在转化发生时将成本相关数据共享给AppsFlyer。

但成本相关数据**不会呈现在归因链接中**。ironSource会对成本数据加密，并将其储存在`af_enc_data`字段中。

</Accordion>

<div id="tip" />

<div id="retargeting-conversion-data" />

## 再营销转化数据

再营销转化分为再归因和再互动两种类型。

> 👍 **提示**
>
> 某些情况下，您可能无法通过再营销转化数据明确地判断转化类型，具体请参考[其他的转化数据来源](#转化数据的其他来源)说明。

<div id="note" />

<div id="re-attribution-with-srns" />

### SRN带来的再归因

如果某个用户通过SRN完成了再归因，其转化数据的payload中不会说明该流量来自再营销广告。这是因为SRN不使用归因链接，因此无法在链接中设置`is_retargeting=true`参数。对于**支持再营销的SRN**，AppsFlyer会判断是否将相关用户记录为再归因流量。

这种情况下，AppsFlyer无法在SDK层级确定某个激活是否来自再营销广告，只能通过广告系列名称来识别再营销广告带来的流量。

> 📘 **注意**
>
> 即使您在广告系列名称中标识出再营销也**无法确保**一定能识别出再营销广告。详情请见[示例](#用户获取与再归因混合场景)部分的说明。

<div id="re-attribution-with-regular-ad-networks" />

### 常规广告平台带来的再归因

非SRN广告平台的归因一般通过归因链接完成。不论您通过常规归因链接还是OneLink投放再营销广告，其链接中总是包含`is_retargeting=true`参数。

<div id="retargeting-campaign-with-criteo" />

<Accordion title="Criteo上的再营销广告">

<div id="attribution-link-2" />

#### 归因链接

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

<div id="conversion-data-payload" />

#### 转化数据payload

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "criteo_int",
      "retargeting_conversion_type": "re-attribution",
      "adset_id": null,
      "campaign_id": null,
      "af_reengagement_window": "30d",
      "install_time": "2018-12-01 23:13:03.126",
      "adgroup_id": null,
      "redirect": "false",
      "af_sub5": null,
      "click_time": "2018-11-18 20:02:31.559",
      "agency": null,
      "cost_cents_USD": "0",
      "is_retargeting": "true",
      "af_cpi": null,
      "af_click_lookback": "30d",
      "af_siteid": null,
      "idfa": "68**********************************",
      "http_referrer": null,
      "orig_cost": "0.0",
      "af_sub4": null,
      "adset": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* `retargeting_conversion_type`参数——该参数用于说明再营销转化的类型。可能出现的参数值为re-attribution（再归因）、re-engagement（再互动）或none（无）。
* `is_retargeting: true`参数——该参数用于标识相关激活是否为再归因。
* `af_reengagement_window`：用于说明再互动归因窗口期。用户与再营销广告互动后，仅在该窗口期所限定的天数内发生的事件才能归因为**再互动**。当转化类型为再归因时，可忽略该参数。

</Accordion>

<div id="re-attribution-with-deferred-deep-linking" />

### 延迟深度链接带来的再归因

您可能经常需要为再归因（即卸载后重新安装相关应用）的用户部署深度链接。假设您为了召回已卸载的流失用户而投放广告，在广告中推广某个产品或服务，并让用户在重新安装并打开应用后直接进入该产品或服务的页面。

用于实现这种场景的技术叫做“延迟深度链接”（Deferred Deep Linking）。您可以使用`onConversionDataSuccess`方法来获取延迟深度链接的转化数据payload。

<div id="deferred-deep-linking-with-srns" />

<Accordion title="在SRN中使用延迟深度链接">

SRN广告中设定的深度链接参数在SRN之外不可用，其中包括含有应用内scheme路径的`af_dp`参数。唯一的例外情况是<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#在应用广告中使用延迟深度链接">Google的信息流应用广告</Anchor>（App campaigns in Feeds）如需再SRN广告中使用延迟深度链接，您必须在其中添加额外的逻辑。您可以使用`onConversionSuccess`响应中的数据，如广告系列、广告组（adset、adgroup）等，以程序化的方式实现用户跳转。

<div id="note-1" />

<div id="conversion-data-for-deferred-deep-linking-with-meta-ads" />

#### Meta ads中延迟深度链接的转化数据

安卓 + iOS

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"Non-organic",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

您可以使用getConversionData响应中的数据，如广告系列、广告组等，以程序化的方式为用户实现跳转，并向其展示相关内容。

> 📄 **比如**
>
> 假设您有一个运动服装类电商应用。有一个未安装该应用的用户与某个广告互动后激活了应用。在应用首次启动时，SDK会返回相应的转化数据。开发人员让该应用打开店铺中的**夏季跑鞋系列**页面（与广告系列对应），并展示**女士跑鞋**类别（与广告组对应）。

</Accordion>

<div id="deferred-deep-linking-with-attribution-links" />

<Accordion title="通过归因链接实现延迟深度链接">

深度链接的实现方式共有以下三种：

<div id="uri-schemes" />

#### URI scheme

在归因链接和OneLink中使用URI scheme时，相关归因链接和payload如下：

**归因链接**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**Payload**

```json
{
      "af_deeplink": true,
      "campaign": "campaign_name",
      "media_source": "media_source_name",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-30 23:59:09",
      "install_time": "2018-12-30 23:59:39.330",
      "agency": null,
      "cost_cents_USD": "0",
      "adset": "AD_SET_NAME",
      "ad_id": "AD_ID",
      "af_siteid": null,
      "http_referrer": null,
      "af_cpi": null,
      "af_sub5": null,
      "af_sub4": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink: true`——出现该参数且参数值为true时，请查看`scheme`和`host`字段
* `scheme`和`host`——这两个字段来自归因链接中的`af_dp`参数，用于说明相关scheme以及通过深度链接向用户展示的页面

<div id="note-2" />

<div id="important" />

<div id="ios-universal-links-and-android-app-links" />

#### iOS Universal Link和安卓App Link

这两种方式也可以实现深度链接。

使用Universal Link或App Link时，相关的OneLink和payload如下：

**OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**Payload**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "Non-organic",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* `shortlink`字段用于说明带来用户的具体OneLink。开发人员可根据此信息设置应用打开后跳转的页面和展示的内容。`campaign`等其他字段也具有此用途。

  > 🚧 **重要提示！**
  >
  > 使用OneLink长链时，payload中不会出现`shortlink`字段。
  >
  > 不管您使用长链还是短链，都建议您添加一个自定义参数来说明相关的跳转内容，例如：`&deep_link_activity=shoes_cateogry`。


> 📘 **请注意 ：**
>
> 只有在OneLink场景中才能使用Universal Link和App Link。

</Accordion>

<div id="re-engagement-with-srns" />

### SRN带来的再互动

与再归因相同，当用户通过SRN上的广告再次打开应用（即完成再互动）时，转化数据无法体现该流量是否来自再互动广告。如需解决此问题，您可以在广告系列名称中标识出再互动广告类型。

<div id="re-engagement-with-regular-ad-networks" />

### 常规广告平台带来的再互动

在该场景中，转化数据payload也无法体现出该流量是否来自再归因广告。如需解决此问题，您可以在广告系列名称中标识出再互动广告类型。

<div id="re-engagement-with-deep-linking" />

### 深度链接带来的再互动

大部分的再互动广告会让用户跳转到应用中的某个具体页面。举例来说，假设您投放广告宣传某个商品或优惠活动，并希望点击广告的用户能直接进入应用中与该商品或活动相关的页面。

这时您就要用到深度链接。开发人员需要根据深度链接中的转化数据定制用户体验，并将用户引导到对应的页面。

<div id="reengagement-deep-linking-with-srns" />

<Accordion title="再互动：在SRN中使用深度链接">

来自SRN的再互动用户没有可用的转化数据。开发人员需要使用相关SRN提供的方法在应用打开时获取转化数据。

</Accordion>

<div id="reengagement-deep-linking-with-ad-networks" />

<Accordion title="再互动：在广告平台中使用深度链接">

沉睡用户被唤醒并打开应用时，您可以通过`onAppOpenAttribution`方法获取以下转化数据：

在iOS和安卓平台上使用OneLink短链时，转化数据是链接中所有参数的结构化映射：

举例来说，

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* 应用开发人员可以根据`af_dp`和广告系列名称等参数将用户引导到应用内的具体页面并向其展示相关内容。

<div id="important-1" />

> 🚧 **重要提示！**
>
> 建议使用OneLink短链。详情请见<Anchor target="_blank" href="/marketers/zh/docs/understand-onelink-short-vs-long-urls">此文档</Anchor>。

建议使用OneLink短链的另一个原因是长链返回的转化数据结构较为复杂。使用长链时，转化数据仅通过一个`link`字段进行映射，该字段中包含整条OneLink长链。

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

<div id="alternative-conversion-data-sources" />

### 转化数据的其他来源

* Push API可提供详细的转化数据payload，其中会标识出再归因和再互动。Push API的payload中包含`re_targeting_conversion_type`字段，该字段可说明转化类型，即再归因或再互动。详情请见<Anchor target="_blank" href="/marketers/zh/docs/push-api-streaming-raw-data">Push API指南</Anchor>。
* 原始数据报告也会标识出转化类型。再营销转化的原始数据报告中包含***Event Name***（事件名称）字段，该字段中可能出现的值为re-engagement（再互动）或***re-attribution*** （再归因），用于说明转化类型。

<div id="note-3" />

<div id="examples-of-mixed-user-acquisition-and-re-attribution" />

### 用户获取与再归因混合场景

> 📄
>
> 1. 某个用户激活您的应用后将其卸载。其激活行为触发了<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口期</Anchor>。您在Meta ads上投放拉新广告（非再营销广告），同时在AppsFlyer后台的Meta ads对接中启用再营销衡量。
>
>    该用户在再归因窗口期内看到并点击该广告，随后重新安装并激活了您的应用。AppsFlyer会将其记录为一次再归因。
>
>    该归因结果基于以下两个因素得出：
>
>    1. Meta ads对接中启用了再营销
>    2. 用户仍处于再归因窗口期内
>
>    在该场景中，广告系列名称中并未标识出再营销。
> 2. 沿用以上示例，但这次假设该用户在再归因窗口期之后点击广告并重新激活应用。这时AppsFlyer会将其记录为一次新增非自然激活。
> 3. 再以另外一种场景为例，假设您在Meta ads上投放了再营销广告，一部分从未安装过应用的用户与该广告互动后激活了应用。AppsFlyer不会将这些用户记录为再归因，而是将其视为来自拉新广告的用户。

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01HCY86CKDJK9TNHPAZB0QX2ZX=%E9%80%9F%E8%A7%88 nonorganic-conversion-data-payload-fields=%E9%9D%9E%E8%87%AA%E7%84%B6%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE%E7%9A%84payload%E5%AD%97%E6%AE%B5 h_01HCY86CKDEMB3428YHCNJQA5R=%E9%9D%9E%E8%87%AA%E7%84%B6%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE%E7%9A%84payload%E5%AD%97%E6%AE%B5 fields-always-available=%E6%80%BB%E6%98%AF%E5%91%88%E7%8E%B0%E7%9A%84%E5%AD%97%E6%AE%B5 h_01HCY86CKDBQRGAY7GHNBJE4WK=%E6%80%BB%E6%98%AF%E5%91%88%E7%8E%B0%E7%9A%84%E5%AD%97%E6%AE%B5 fields-available-in-some-cases=%E9%83%A8%E5%88%86%E6%83%85%E5%86%B5%E4%B8%8B%E4%BC%9A%E5%91%88%E7%8E%B0%E7%9A%84%E5%AD%97%E6%AE%B5 h_01HCY86CKDYQMYB9BQ4MXWP8A5=%E9%83%A8%E5%88%86%E6%83%85%E5%86%B5%E4%B8%8B%E4%BC%9A%E5%91%88%E7%8E%B0%E7%9A%84%E5%AD%97%E6%AE%B5 additional-fields=%E5%8F%AF%E9%80%89%E7%9A%84%E9%9D%9E%E9%BB%98%E8%AE%A4%E5%AD%97%E6%AE%B5 h_01HCY86CKD47M85AZVEA5C4JH7=%E5%8F%AF%E9%80%89%E7%9A%84%E9%9D%9E%E9%BB%98%E8%AE%A4%E5%AD%97%E6%AE%B5 limitations=%E5%B1%80%E9%99%90%E6%80%A7 h_01HCY86CKEFX646H9BSKSFGZ36=%E5%B1%80%E9%99%90%E6%80%A7 h_01HCY86CKEZ2483XB461M2C9EC=custom-parameter-names ua-conversion-data-with-srns=srn%E7%9A%84ua%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE h_01EGKTQN6XDYHA60P2WKHBBVFT=srn%E7%9A%84ua%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE a-note-about-facebook=meta-ads%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01HCY86CKENFEGX53G9G4SGPSK=meta-ads%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 facebook-conversion-data=meta-ads%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE h_01HCY86CKE658H36F3VJQMATQK=meta-ads%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE h_01HCY86CKF6FY96PAWB5Y7YXSQ=google-ads-conversion-data h_01HCY86CKFMNNNJZTPGK4870YN=apple-search-ads-conversion-data h_01HSQRQSK8W9K6871K0EWHDF76=tiktok-conversion-data h_01HCY86CKFS5SJBECSY42VRJWP=oath-ad-platforms-conversion-data ua-conversion-with-other-ad-networks=%E5%85%B6%E4%BB%96%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E7%9A%84ua%E8%BD%AC%E5%8C%96 h_01HCY86CKFB0GEJRTYSXN9YZ08=%E5%85%B6%E4%BB%96%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E7%9A%84ua%E8%BD%AC%E5%8C%96 h_01HCY86CKFY787RD4BHQDVEVFV=applovin attribution-link=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HCY86CKFXM5XXJZSPXPB6397=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 h_01HCY86CKFDDXWT2KKFTKKBGHM=payload h_01HCY86CKFV55GYY7C51D7F72S=ironsource attribution-link::a45a1b4a=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5-1 h_01HCY86CKFYGEYR2TRPSD87KDA=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5-1 payload::81867f5c=payload-1 h_01HCY86CKFKKFQDG1P42R1FSDJ=payload-1 retargeting-conversion-data=%E5%86%8D%E8%90%A5%E9%94%80%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE h_01EHQ74JS84509GT6M93SZA4HX=%E5%86%8D%E8%90%A5%E9%94%80%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE h_01HCY86CKFP0DWCFMKSB1V130D=%E6%8F%90%E7%A4%BA reattribution-with-srns=srn%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E5%BD%92%E5%9B%A0 h_01HCY86CKFAVWP1W0ZNEN5P30A=srn%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E5%BD%92%E5%9B%A0 h_01HCY86CKF2QY9DV1J9MWHKJ5P=%E6%B3%A8%E6%84%8F reattribution-with-regular-ad-networks=%E5%B8%B8%E8%A7%84%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E5%BD%92%E5%9B%A0 h_01HCY86CKF1PV8MRR902RAHQGW=%E5%B8%B8%E8%A7%84%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E5%BD%92%E5%9B%A0 h_01HCY86CKF1RGK01VTV3EEHQVM=retargeting-campaign-with-criteo attribution-link::c16e96bb=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5-2 h_01HCY86CKFSKBBMFKA8NN8XTPC=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5-2 conversion-data-payload=%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AEpayload h_01HCY86CKG2YQQC629SC3RAFKE=%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AEpayload reattribution-with-deferred-deep-linking=%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E5%BD%92%E5%9B%A0 h_01HCY86CKGXV50H79R0YH1GB2C=%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E5%BD%92%E5%9B%A0 h_01HCY86CKG12YRGFEEJ27DQART=deferred-deep-linking-with-srns conversion-data-for-deferred-deep-linking-with-facebook=meta-ads%E4%B8%AD%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E7%9A%84%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE h_01HCY86CKGX9VHSV3ASKXMFM0X=meta-ads%E4%B8%AD%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E7%9A%84%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE h_01HCY86CKGHM9FKBEHMYBF4597=%E6%AF%94%E5%A6%82 h_01HCY86CKG3XWM4X0YH7WYCEH4=deferred-deep-linking-with-attribution-links uri-schemes=uri-scheme h_01HCY86CKGDM2NE1FCRC92K8R0=uri-scheme ios-universal-links-and-android-app-links=ios-universal-link%E5%92%8C%E5%AE%89%E5%8D%93app-link h_01HCY86CKGY1NE4214DES0Y2AV=ios-universal-link%E5%92%8C%E5%AE%89%E5%8D%93app-link h_01HCY86CKG1NGYR8WCS7NMM782=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HCY86CKG9VF8MBJQTWJGDJ6Z=%E8%AF%B7%E6%B3%A8%E6%84%8F- reengagement-with-srns=srn%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E4%BA%92%E5%8A%A8 h_01HCY86CKG4TRYR6TWYYVB0FJE=srn%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E4%BA%92%E5%8A%A8 reengagement-with-regular-ad-networks=%E5%B8%B8%E8%A7%84%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E4%BA%92%E5%8A%A8 h_01HCY86CKGM2JS7C9T71R6GPH1=%E5%B8%B8%E8%A7%84%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E4%BA%92%E5%8A%A8 reengagement-with-deep-linking=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E4%BA%92%E5%8A%A8 h_01HCY86CKG0NPQAA2ZRWWNKGQD=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E4%BA%92%E5%8A%A8 h_01HCY86CKGEBHQVFRGJH96KDFJ=reengagement-deep-linking-with-srns h_01HCY86CKGJ9HG7AGB5MFP33RK=reengagement-deep-linking-with-ad-networks h_01HCY86CKGC3AF6YDKTY95XMV5=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 alternative-conversion-data-sources=%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE%E7%9A%84%E5%85%B6%E4%BB%96%E6%9D%A5%E6%BA%90 h_01HCY86CKG3N6ZXV70G4VMZ0X5=%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE%E7%9A%84%E5%85%B6%E4%BB%96%E6%9D%A5%E6%BA%90 examples-of-mixed-user-acquisition-and-reattribution=%E7%94%A8%E6%88%B7%E8%8E%B7%E5%8F%96%E4%B8%8E%E5%86%8D%E5%BD%92%E5%9B%A0%E6%B7%B7%E5%90%88%E5%9C%BA%E6%99%AF h_01HCY86CKGK9DVVB7T6CVNB8ZN=%E7%94%A8%E6%88%B7%E8%8E%B7%E5%8F%96%E4%B8%8E%E5%86%8D%E5%BD%92%E5%9B%A0%E6%B7%B7%E5%90%88%E5%9C%BA%E6%99%AF" />

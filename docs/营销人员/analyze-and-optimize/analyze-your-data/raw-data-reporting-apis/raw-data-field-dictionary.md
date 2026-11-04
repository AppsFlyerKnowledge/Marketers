---
title: 原始数据字段释义
metadata:
  keywords:
    - raw reports
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2016-03-10T14:37:44Z'
  edited_at: '2026-10-14T10:03:37Z'
  id: 208387843
  locale: zh-cn
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/zh-cn/articles/208387843
---
> **概要：** 本文解释了每个字段的具体内容，旨在帮助您了解各种字段的含义、格式以及可用性。

<div id="overview" />

## 概览

原始数据字段字典表列出了在各种AppsFlyer报告中可用的原始数据字段。随着在AppsFlyer中添加更多原始数据字段，该表会不断更新。

该表格由以下各列组成：

* **字段分组：** 基于字段用途的分组。**请注意**：原始数据中的广告收入类字段会单独成列显示，或以**事件值**的形式呈现。
* **姓名：**
  * 在Data Locker和Push API报告中显示的字段名称。
  * 符号[n]表示一个字段下有多个字段名，以编号区分。比如Sub Param [n]表示Sub Param这个字段分为Sub Param 1、Sub Param 2等等，一直到Sub Param 5，而这里n的值就是1-5。
* **字段名称**：
  * Export（导出数据）页面和Pull API的报告中使用的字段名称。
  * 符号[n]表示一个字段下有多个字段名，以编号区分。比如Sub Param [n]表示Sub Param这个字段分为Sub Param 1、Sub Param 2等等，一直到Sub Param 5，而这里n的值就是1-5。
* **数据来源**：字段内容的数据来源，比如：
  * **链接**：归因链接（请参阅 <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">AppsFlyer归因链接的结构和参数</Anchor> ）或来自相关SRN的API
  * **SDK**：通过相关应用中接入的SDK收集数据。
  * **AF**：由AppsFlyer生成数据。
  * 以及未来开发的其他功能。
* **说明**
  * 某些字段会根据具体事件产生的场景不同而带有不同的含义，比如由UA和再营销广告带来的事件之间会有所区分。
* **格式：** 字段类型和长度。
  * <span id="wYXz"></span>**字符串**：即字符串长度上限。建议字符串不要超过<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#归因链接参数拉新及再营销">此处</Anchor>所列的长度上限。
  * 日期时间
    * 格式为`yyyy-mm-dd hh:mm:ss`的字符串。如`2019-09-17 00:09:25`，其时区取决于数据传输工具，具体如下：
      * Export Data（导出数据）页面：在应用层级设置的时区。
      * Push API：时间字段中有一个*selected\_time\_zone*选项，您可以通过该选项使用应用层级的指定时区，若未启用该选项则默认为UTC时间。
      * Master API：默认为应用层级指定时区。
      * Data Locker：UTC
    * CSV文件中的日期字段格式为yyyy-mm-dd。如果您在Excel中打开CSV文件，那么日期字段的格式则取决于计算机的日期和时间设置，您可以在[Excel](https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows)中更改显示格式。如需查看未格式化的值，请使用编辑器打开该文件。
    * Push API:
      * 以UTC时间显示的时间戳字段，格式为`yyyy-mm-dd hh:mm:ss.sss`。 比如：`2019-09-17 00:09:25.123`
      * 以指定时区显示的时间戳字段，格式为`yyyy-mm-dd hh:mm:ss.sss±th:tm`。比如：`2019-01-20 04:51:16.000+0000`
  * **n字符枚举**：枚举字段仅可包含特定的值。比如成本的货币单位只能由指定的3字符货币代码组成。
  * **5字符布尔式枚举：** 这类字段的值只有`TRUE`或`FALSE`两种。

<div id="tip" />

> 👍 **提示**
>
> * 如需调整排序方式，请点击相应列的名称。
> * 您也可以<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRDdd2FKVQ0eISEwGVYyTeF4JD0rlOLnrepz8Nf1R3Kc6o7AESDwXQLOuSB41xN6wIuhmIFlb5b9Gvp/pub?output=xlsx">下载该表格</Anchor>。
> * 除了上文提到的字段外，您下载的CSV文件中还包含以下额外字段：
>   * **属于AppsFlyer主要报告结构的字段**：
>     * 大部分的AppsFlyer报告都是基于同一个结构搭建的，并且都含有相同的字段。
>     * 部分字段可能会填充null值或空值，具体填充方式取决于相关报告以及数据提供方（广告平台、广告主、设备平台等）。
>     * 建议您在配置BI系统时将所有的AppsFlyer主要报告结构字段都配置进去，即使某个报告中的部分字段可能会返回null值或空值。这有助于您在数据可用时便捷完成入库。
>     * <span id="Ao"></span>AppsFlyer主要报告结构之外的字段仅会出现在特殊的报告中，比如SKAN报告。
>   * **报告传输方式**：用于说明相关字段的拉取途径，即Push API、导出数据/Pull API以及Data Locker。**请注意**：即使某个字段属于AppsFlyer主要报告结构的一部分，但也可能不包含在某个传输方式能拉取到的报告中。比如 placement（广告位）是一个AppsFlyer主要报告结构字段，但仅在Data Locker、Pull API或导出数据页的报告中呈现，不会出现在Push API传输的报告中。

| 字段分组 | 名称 | 字段名称 | 数据来源 | 说明 | 格式 |
| --- | --- | --- | --- | --- | --- |
| <span id="attribution::xde448d77"></span>归因 | ad\_id | 广告ID | 链接 | 分配给特定广告的唯一标识符<ul><li>与[af\_ad\_id](#attribution::de448d77)相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::b19119e4"></span>归因 | {"ad_id__assist_[n]"} (n=1-3) |  | AF | 分配给来自第一个辅助归因的特定广告的唯一标识符。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="xattribution"></span>归因 | ad\_name | 广告名称 | 链接 | 分配给广告的描述性标签<ul><li>与[af\_ad](#attribution)相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::ce2d519c"></span>归因 | {"ad_name__assist_[n]"} (n=1-3) |  | AF | 分配给来自第一个辅助归因的广告的描述性标签。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="skan"></span>SKAN | ad\_network\_ad\_id | Ad ID | 广告平台 | Ad ID | 字符串 |
| <span id="skan::2fb2335a"></span>SKAN | ad\_network\_ad\_name | 广告名称 | 广告平台 | 广告名称 | 字符串 |
| <span id="skan::5dca70a1"></span>SKAN | ad\_network\_adset\_id | Adset ID | 广告平台 | Adset ID | 字符串 |
| <span id="skan::d952fce5"></span>SKAN | ad\_network\_adset\_name | Adset name | 广告平台 | Adset name | 字符串 |
| <span id="skan::6f93cee6"></span>SKAN | ad\_network\_campaign\_id | Campaign ID | 广告平台 | 广告平台上报给AppsFlyer的广告系列ID | 字符串 |
| <span id="skan::ccaf995e"></span>SKAN | ad\_network\_campaign\_name | 广告系列 | 广告平台 | 广告平台上包给AppsFlyer的广告系列名称 | 字符串 |
| <span id="skan::5fe116d5"></span>SKAN | ad\_network\_channel | 渠道 | 广告平台 | 报告中已添加该字段，但不一定带有值。 | 字符串 |
| <span id="skan::5125d426"></span>SKAN | ad\_network\_creative | 素材 | 广告平台 | <ul><li>该字段的值基于广告平台提供的扩充数据得出</li><li>在SKAN 3中该值为null</li></ul> | 字符串 |
| <span id="skan::5a2fa279"></span>SKAN | ad\_network\_name | Ad network name | 广告平台 | 广告平台向AppsFlyer上报的广告平台名称。<ul><li>如果该字段为空，则表示广告平台没有（无法）填充该字段。</li><li>您可以通过skad\_ad\_network\_id来解析广告平台的名称。请使用<Anchor target="_blank" href="/marketers/zh/docs/skan-integrated-partners-list#apple-skadnetwork-ids-of-ad-networks">该表格</Anchor>进行解析。</li></ul> | 字符串 |
| <span id="skan::39724216"></span>SKAN | ad\_network\_source\_app\_id | Ad network source app ID | 广告平台 | 广告平台上报的流量侧应用（Publisher App）ID，用于核对成本。该数据基于流量侧应用提供的信息得出。 | 字符串 |
| <span id="skan::11414be7"></span>SKAN | ad\_network\_timestamp | Ad network timestamp | 广告平台 | <ul><li>广告平台接收到回传的时间。</li><li>在Google Ads的投放场景中，该字段不填充。</li></ul> | 时间戳 |
| <span id="device-info::e7dfb109"></span>设备信息 | ad\_personalization\_enabled | Ad personalization enabled | SDK | 用于标识用户是否已同意允许Google将其用户级数据用于个性化广告：同意为true，未同意为false。 | Boolean |
| <span id="attribution::7ea87d9e"></span>归因 | ad\_placement | Ad placement | 链接 | 在CTV场景下以广告位填充。 | 字符串 |
| <span id="ad-revenue::a77b252f"></span>广告收入 | ad\_revenue\_ad\_type | ad\_revenue\_ad\_type | 广告收入SDK | 向用户展示的广告类型 | 字符串 |
| <span id="ad-revenue::e2b62d09"></span>广告收入 | ad\_revenue\_custom\_parameters | ad\_revenue\_custom\_parameters | 广告收入SDK | 广告主通过广告收入SDK配置的自定义参数，用于相关应用向用户展示的广告。 | 字符串 |
| <span id="attribution::x5954755967"></span>归因 | ad\_type | Ad type | 链接 | 定义产生互动的广告类型<ul><li>与[af\_ad\_type](#attribution::59547559)相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="ad-revenue"></span>广告收入 | ad\_unit | 广告单元 | Ad revenue API | 在A/B测试中指用于变现的广告段位（ad segment）名称 | 字符串 |
| <span id="device-info::ce4bb08e"></span>设备信息 | ad\_user\_data\_enabled | Ad user data enabled | SDK | 用于标识用户是否已同意允许Google将其用户级数据用于效果衡量和个性化广告：同意为true，未同意为false。 | 布尔 |
| <span id="attribution::x9b2f9ab6"></span>归因 | adset\_id | 广告组ID | 链接 | 广告系列中广告组的唯一标识符<ul><li>与[af\_adset\_id](#attribution::9b2f9ab6)相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::9964905a"></span>归因 | {"adset_id__assist_[n]"} (n=1-3) |  | AF | 来自第一个辅助归因的广告组在一个活动中的唯一标识符。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::x5209dd66"></span>归因 | adset\_name | Adset name | 链接 | 广告系列中的广告分组<ul><li>与[af\_adset](#attribution::5209dd66)相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::f348c026"></span>归因 | {"adset_name__assist_[n]"} (n=1-3) |  | AF | 第三次助攻归因中的广告系列广告分组<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info-advertising-id"></span>设备信息 | advertising\_id | Advertising ID for Android devices | SDK | <ul><li>用户可重置的设备ID，又称GAID。</li><li>在CTV场景中该字段为CTV ID，如RIDA或VIDA。</li></ul> | 字符串 |
| <span id="attribution::929faa8"></span>归因 | advertising\_id\_type | 广告ID类型 | 链接 | <ul><li>用户可重置的设备唯一标识符类型。</li><li>指定 advertising\_id [\_value 字段中提供的广告](#attribution::be9cb893) ID 的类型。常见类型包括IDFA（iOS）和GAID（Android）。</li></ul> | 字符串 |
| <span id="attribution::be9cb893"></span>归因 | advertising\_id\_value | 广告ID值 | 链接 | 用户可重置的设备唯一标识符值。<ul><li>与[advertising\_id](#device-info-advertising-id)、[idfa](#device-info::e0372922)、[oaid](#device-info::4afa15f)相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution"></span>归因 | af\_ad | Ad | 链接 | 广告名称 | 字符串 |
| <span id="attribution::de448d77"></span>归因 | af\_ad\_id | Ad ID | 链接 | Ad ID | 字符串/整数 |
| <span id="attribution::59547559"></span>归因 | af\_ad\_type | Ad type | 链接 | <ul><li>如横幅、页脚</li></ul> | 字符串 |
| <span id="attribution::5209dd66"></span>归因 | af\_adset | Adset | 链接 | 广告组名称，用于标识包含一个或多个广告的群组。 | 字符串 |
| <span id="attribution::9b2f9ab6"></span>归因 | af\_adset\_id | Adset ID | 链接 | 广告组ID，用于标识包含一个或多个广告的群组。 | 字符串 |
| <span id="skan::1e316e1d"></span>SKAN | af\_attribution\_flag | AF attribution flag | AF | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#null-conversion-values">单一可信数据源（SSOT）</Anchor>机制启用时：如果该字段的值为true，则表示该次激活同时被AppsFlyer和SKAN归因。如果该值为false，则表示该次激活没有被AppsFlyer归因。即使skad\_conversion\_value的值为null，该参数的值仍为true或false（取决于模型推算）。</li></ul> | 布尔 |
| <span id="attribution::acbd5bea"></span>归因 | af\_attribution\_lookback | Attribution lookback window | 链接 | <ul><li>归因回溯窗口期，在这个时间段内可将激活归因到具体广告。</li><li>UA（用户获取）：点击型归因的回溯窗口期在af\_click\_lookback归因链接参数中设置。</li><li>再营销：在应用配置部分的<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window#再归因窗口期的设置">再营销点击回溯</Anchor>中设置。</li></ul> | 字符 |
| <span id="attribution::reqloopback"></span>归因 | requested\_lookback\_window |  | AF | 在任务链接中指定的原始未解析值。用于确定点击或展示可归因于转化所对应的时段。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::75430560"></span>归因 | af\_c\_id | Campaign ID | 链接 | Campaign ID | 字符串 |
| <span id="iap::a1f84da0"></span>IAP | af\_cancelation\_date\_ms |  | AppsFlyer购买验证 | 取消日期 |  |
| <span id="attribution::1d1e08b5"></span>归因 | af\_channel | 渠道 | 链接 | 媒体渠道的流量入口，举例来说，Google下的YouTube，Meta ads下的Instagram等等 | 动态枚举型字符串 |
| <span id="attribution::8c179e3b"></span>归因 | af\_cost\_currency | Cost currency | 链接 | <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">符合IOS-4217的三位字母货币代码（如USD、EUR等）</Anchor>默认为USD（美元）。 | 字符串 |
| <span id="attribution::8733a05b"></span>归因 | af\_cost\_model | 成本模式 | 链接 | 通过归因链接上报的成本模型，包括CPC/CPI/CPM等等。目前所有成本都以CPI计算，不考虑该字段的值。 | 字符串 |
| <span id="attribution::5647f309"></span>归因 | af\_cost\_value | Cost value | 链接 | Cost Currency（成本货币）的金额，最多精确到小数点后4位，举例来说，320.5095 | 字符串 |
| <span id="subscription"></span>订阅 | af\_cuids | CUIDs | AppsFlyer购买验证 | <ul><li>在ARS场景中，该参数会包含一个带有所有CUID的数组。</li><li>无论设备ID是否一致，都会显示CUID的数组，这样就可以让多个设备ID对应相同的CUID。</li></ul> |  |
| <span id="iapsubscription"></span>订阅 | af\_discount\_id | Discount ID | AppsFlyer购买验证 | 在首次购买过程中呈现给用户的优惠ID。只有在使用优惠码时才会填充该ID。 |  |
| <span id="subscription::83d8905f"></span>订阅 | af\_discount\_type | Discount type | AppsFlyer购买验证 | 用户领取的优惠类型。可能出现的值为：<ul><li>iOS：<ul><li>introductory（试销）</li><li>subscription（订阅）</li></ul></li><li>安卓：<ul><li>intro price（试销价）</li><li>one\_time\_code（一次性优惠码）</li><li>vanity\_code（定制优惠码）</li></ul></li></ul> |  |
| <span id="attribution::4c444ee7"></span>归因 | af\_engagement\_destination | 参与目的地 | AF | 指示从广告链接的目的地类别，例如**网页**着陆页、**移动**应用（通过深度链接或应用商店）或其他目的地类型，如**CTV**、**PC**或**控制台**。 | 字符串 |
| <span id="iapsubscription::6b5c7f1f"></span>订阅 | af\_environment | Environment | AppsFlyer购买验证 | 数据接收环境，可能出现的值为production（生产环境）和sandbox（沙盒环境）两种。 |  |
| <span id="subscription::9d10090e"></span>订阅 | af\_expires\_date\_ms | Subscription expiration date |  | 当前订阅周期的截止日期。 |  |
| <span id="attribution::9dd48973"></span>归因 | af\_keywords | 关键词 | 链接 | 用户在线搜索时所使用的字词，由广告平台上报。 | 字符串 |
| <span id="iapsubscription::ebbabfd3"></span>订阅 | af\_net\_revenue | 净收入 | True Revenue API | 根据所有相关因素计算得出的净收入。详情请见af\_net\_revenue\_factors说明。 |  |
| <span id="iapsubscription::d4d47a47"></span>订阅 | af\_net\_revenue\_country | Net revenue country | True Revenue API | 由两个字符组成的ISO国家代码，用于说明收取税费的国家。<ul><li>举例来说，GB</li></ul> |  |
| <span id="iapsubscription::398dcab"></span>订阅 | af\_net\_revenue\_factors | Net revenue factors | True Revenue API | [由一个数组组成，代表了计算af\_net\_revenue金额时涉及到的所有因素。](#iapsubscription::ebbabfd3)<ul><li>[示例：store\_commission](#iapsubscription::bd419a23)</li></ul> |  |
| <span id="iapsubscription::45acb981"></span>订阅 | af\_net\_revenue\_postal\_code | Net revenue postal code | True Revenue API | 由字母和/或数字组成的字符串<ul><li>举例来说，L4J8E3</li></ul> |  |
| <span id="iapsubscription::e1bc387a"></span>订阅 | af\_net\_revenue\_subdivision | Net revenue subdivision | True Revenue API | 部分国家可能需要区分州/细分区划。这里使用ISO 3166-2中的细分区划代码。<ul><li>同时包含国家代码和细分区划代码。</li><li>举例来说，US-CA</li></ul> |  |
| <span id="iapsubscription::9767b912"></span>订阅 | af\_net\_revenue\_tax\_exclusive | Net revenue tax exclusive | True Revenue API | <ul><li>布尔型参数，仅有true或false两种值。</li><li>参数值为false时，表示总收入中包含税费。</li><li>参数值为true时，表示总收入中不包含税费，需要另行添加。比如在美国和加拿大等地区，零售价中不包含营业税，这时就需要用到这个参数。</li></ul> |  |
| <span id="iapsubscription::60f8530"></span>订阅 | af\_net\_revenue\_tax\_name | Net revenue tax name | True Revenue API | 广告主出具的费用清单中用于表述具体税费类型的税费名称。<ul><li>举例来说，销售税、增值税（VAT）、商品及服务税（GST）</li></ul> |  |
| <span id="iapsubscription::e9ec3c4c"></span>订阅 | af\_net\_revenue\_tax\_rate | Net revenue tax rate | True Revenue API | 精确到小数点后4位的数字，代表税率百分点。<ul><li>举例来说，7.25</li></ul> |  |
| <span id="iapsubscription::ddec7a40"></span>订阅 | af\_offer\_id | 优惠ID | AppsFlyer购买验证 | 在相关情况下，适用于交易的优惠 ID，例如折扣或促销优惠。 | 字符串 |
| <span id="iapsubscription::6a1d1d2a"></span>订阅 | af\_original\_transaction\_id | Original transaction ID | AppsFlyer购买验证 | <ul><li>初始交易ID。</li><li>仅适用于iOS</li></ul> |  |
| <span id="subscription::b4ee3dae"></span>订阅 | af\_period\_type | Subscription period type | AppsFlyer 购买验证 | <ul><li>订阅或试用期类型。</li></ul>可能出现的值为：<ul><li>试用，入门，正常</li></ul> |  |
| <span id="iapsubscription::bb6f0cb2"></span>订阅 | af\_product\_id | Product ID | AppsFlyer 购买验证 | 相关订阅产品的ID |  |
| <span id="attribution::9067a60e"></span>归因 | af\_prt | 渠道 | 链接 | 代理标识符。SKAN场景中可能不填充该字段。 | 字符串 |
| <span id="iapsubscription::a48bb9e9"></span>订阅 | af\_purchase\_date\_ms | Purchase date | AppsFlyer 购买验证 | 报告中与产品ID应用内事件相关联的购买日期。 |  |
| <span id="iapsubscription::a56bb9e9"></span>IAP | af\_purchase\_option\_id | 购买选项 ID | AppsFlyer 购买验证 | 与交易相关的购买选项 ID。 | 字符串 |
| <span id="iapsubscription::a49872e9"></span>IAP | af\_purchase\_option\_type | 购买选项类型 | AppsFlyer 购买验证 | 交易的购买选项类型。可能的值（Android）：购买，租赁。 | 字符串 |
| <span id="iap"></span>IAP | af\_purchase\_state | Purchase state | AppsFlyer 购买验证 | 可能出现的值为：<ul><li>Purchased（已购买）</li><li>Canceled（已取消）</li><li>Pending（未完成）</li></ul> |  |
| <span id="iapsubscription::4d962f68"></span>订阅 | af\_purchase\_token | Purchase token | AppsFlyer 购买验证 | <ul><li>相关交易的purchase token</li><li>仅适用于安卓</li></ul> |  |
| <span id="iapsubscription::b0119997"></span>订阅 | af\_reason | 使用原因 | AppsFlyer 购买验证 | 在订单取消或用户流失相关的事件中，用户取消或流失的原因。可能出现的值为：<ul><li>iOS：<ul><li>cancel\_intent（取消意向）</li><li>billing\_issue（付款问题）</li><li>declined\_price\_increase（拒绝加价）</li><li>product\_unavailable（产品不可用）</li></ul></li><li>安卓：<ul><li>I don't use this service enough（不太常用该服务）</li><li>Technical issues（技术问题）</li><li>Cost-related reasons（费用相关的原因）</li><li>I found a better app（发现了更好的应用）</li><li>Other（其他）</li></ul></li><li>在续订事件中，表示用户续订的原因。可能出现的值为： 安卓： paused and resumed（暂定后续订）<br />disabled and enabled auto-renew（取消后开启自动续订）</li><li>在退款相关的事件中，指用户获得退款的原因。可能出现的值为： iOS： 1：表示您的应用出现了问题<br />0：表示其他原因</li></ul> |  |
| <span id="attribution::15cc3657"></span>归因 | af\_reengagement\_window | Reengagement window | 链接 | 再营销：用户与再营销广告交互后，在这个窗口期内完成转化事件时，AppsFlyer会将该事件归因到相应的再营销广告。<ul><li>请注意：在再营销广告系列中，不填充该字段的值。</li></ul> | 字符串 |
| <span id="iapsubscription::d5fc1fe4"></span>订阅 | af\_refunded\_transaction\_ids | Refund transaction ID | AppsFlyer 购买验证 | <ul><li>由一个数组组成，其中包含所有退款的交易ID</li><li>仅适用于iOS</li></ul> |  |
| <span id="attribution::e9b53459"></span>归因 | af\_siteid | Site ID（子渠道ID） | 链接 | 子渠道ID | 字符串 |
| <span id="iapsubscription::22a14b24"></span>订阅 | af\_store | App ID | AppsFlyer 购买验证 | 指用户购买订阅产品时使用的应用商店 |  |
| <span id="attribution::eaeca85c"></span>归因 | af\_sub[n] (n=1-5) | Sub param [n] | 链接 | 广告主在归因链接中自行配置的参数 | 字符串 |
| <span id="attribution::9fdff16d"></span>归因 | af\_sub\_siteid | Sub site ID | 链接 | 次级子渠道ID | 字符串 |
| <span id="subscription::6f140cd3"></span>订阅 | af\_subscription\_ownership\_type | Subscription ownership type | AppsFlyer 购买验证 | 若字段值为FAMILY\_SHARED，表示该用户通过家人共享套餐获取访问权限。若字段值为PURCHASED，表示付费用户完成了一次购买。 |  |
| <span id="iapsubscription::4571d5da"></span>订阅 | af\_transaction\_id | Transaction ID | AppsFlyer 购买验证 | <ul><li>相关交易的ID</li><li>仅适用于iOS</li></ul> |  |
| <span id="attribution::x9067a60e"></span>归因 | agency | 代理 | 链接 | 代理标识符<ul><li>与 [af\_prt](#attribution::9067a60e) 相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::ba8e1da9"></span>归因 | {"agency__assist_[n]"} (n=1-3) |  | AF | 来自第一个辅助归因的代理标识符<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::a9ae30bc"></span>设备信息 | amazon\_aid | Amazon Fire ID | SDK | 亚马逊设备上的用户可重置广告ID。 | 字符串 |
| <span id="device-info::3a055021"></span>设备信息 | android\_id | Android ID | SDK | 不可重置的永久性设备ID | 字符串 |
| <span id="attribution::fbb2666c"></span>归因 | app\_group\_id | App group ID | AF | 与某个用于跨平台归因的OneLink模板关联的应用。 | 字符串 |
| <span id="app"></span>应用 | app\_id | 应用ID | SDK | AppsFlyer后台的应用唯一标识符。举例来说，<ul><li>iOS应用：id123456789</li><li>安卓应用：com.appsflyer.referrersender</li></ul> | 字符串 |
| <span id="app::38720e5d"></span>应用 | app\_name | 应用名称 | SDK | 应用在公开应用商店和HQ1中显示的官方名称。该值面向用户展示，可能不同于内部标识符或包标识符。用于显示和报告<ul><li>由广告主设置</li></ul> | 字符串 |
| <span id="attribution::b4bcbe76"></span>归因 | app\_store\_id | App store ID | AF | 应用商店中显示的App ID | 字符串 |
| <span id="app::5a1697f1"></span>应用 | app\_type | App type | App clip | 可能出现的值为：<ul><li>app\_clip, full\_app</li></ul> | 字符串 |
| <span id="app::f992fbe9"></span>应用 | app\_version | 应用版本 | SDK | 客户应用的版本，由客户SDK上报，或通过AF S2S API上报。<ul><li>由广告主设置</li></ul> | 字符 |
| <span id="app::avc00001"></span>应用 | app\_version\_\_conversion | 转化时的应用版本 | SDK | 转化发生时，由客户 SDK 或通过 AF S2S API 报告的客户应用版本。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::98b3ecc7"></span>设备信息 | appsflyer\_id | AppsFlyer ID | SDK | <ul><li>用户在其设备上安装应用时由SKD生成的专属ID，用于在LTV维度对应用内事件进行归因、获取转化数据并关联应用内事件。</li><li>如果用户对应用进行了卸载重装，SDK会生成新的ID。从iCloud备份中恢复应用不计为新增激活。</li><li>在CTV场景中，该字段以custom\_device\_id（由广告主管理的设备ID）填充。</li></ul> | 字符串 |
| <span id="device-info"></span>设备信息 | appsflyer\_id\_type | AppsFlyer ID 类型 | SDK | 标识appsflyer\_id\_value的来源，例如移动SDK或网页端SDK。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::b482a05"></span>设备信息 | appsflyer\_id\_value | AppsFlyer ID Value | SDK | 用于表示单个上下文的平台范围标识符——无论是移动应用安装还是 Web 会话。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::dd85d811"></span>设备信息 | att | ATT | SDK | <ul><li>iOS 14以上的版本中可以使用ATT，即att\_status，该字段的值可以由<Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor>返回、由S2S发送或由AppsFlyer判断。</li><li>可能出现的ATT<Anchor target="_blank" href="/marketers/zh/docs/att-implications-ios-14-and-deprecation-of-lat">值</Anchor>包括：not\_determined、restricted、denied、authorized、af\_unknown、af\_authorized、af\_unavailable。</li></ul> | 字符串 |
| <span id="attribution::46498f6f"></span>归因 | attributed\_touch\_time | Attributed touch time | AF | <ul><li>UA：AF记录到的广告互动时间。</li><li>再营销：AF记录到的广告互动时间。</li></ul> | 日期时间 |
| <span id="attribution::65deebe6"></span>归因 | attributed\_touch\_type | 归因到的触点类型 | AF | 用于对广告交互行为进行分类。将广告交互匹配到某个激活后，AppsFlyer会设置该字段的值。<ul><li>UA（用户获取）：可能出现的值包括click、download、impression、pre-installed</li><li>再营销：可能出现的值包括click和impression</li></ul> | 枚举型 |
| <span id="protect360"></span>Protect360 | blocked\_reason | 拦截原因（Blocked reason） | AF | Protect360：激活被拦截的原因。例如：install\_hijacking（安装劫持）、bots（机器人作弊） | 字符串 |
| <span id="protect360::e47c57b1"></span>Protect360 | blocked\_reason\_rule | Blocked reason rule（已弃用） | AF | 已弃用 | 字符串 |
| <span id="protect360::ecb2f1e5"></span>Protect360 | blocked\_reason\_value | Blocked reason value | AF | Protect360：关于此次拦截的其他信息。举例来说，Site ID（子渠道）、validation rule name（验证规则名称）等。 | 字符串 |
| <span id="protect360::e5842829"></span>Protect360 | blocked\_sub\_reason | 详细拦截原因 （Blocked sub reason） | AF | Protect360：更为详细的激活拦截原因。举例来说，拦截原因为install\_hijacking（激活劫持），详细拦截原因可以是referrer hijack（referrer劫持）、CTIT\_anomalies（CTIC异常）、validation\_rules（验证规则） | 字符串 |
| <span id="app::d66d86c7"></span>应用 | bundle\_id | Bundle ID | SDK | <Anchor target="_blank" href="https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids">iOS：用于标记iOS平台中一个或一组应用的标识符（请参阅Apple关于Bundle ID的开发者文档</Anchor>）<ul><li>安卓：应用ID</li><li>请注意：该字段与AppsFlyer PBA无关。</li></ul> | 字符串 |
| <span id="attribution::274e74d5"></span>归因 | campaign | 广告系列 | 链接 | 广告系列名称 | 字符串 |
| <span id="attribution::x75430560"></span>归因 | campaign\_id | 广告系列ID | 链接 | 特定广告系列的唯一标识符<ul><li>与 [af\_c\_id](#attribution::75430560) 相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::f8b1a2e"></span>归因 | {"campaign_id__assist_[n]"} (n=1-3) |  | AF | 来自第一个辅助归因的特定广告活动的唯一标识符<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::x274e74d5"></span>归因 | campaign\_name | 广告系列名称 | 链接 | 分配给广告系列的描述性标签<ul><li>与 [campaign](#attribution::274e74d5) 相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::64d77c36"></span>归因 | {"campaign_name__assist_[n]"} (n=1-3) |  | AF | 来自第一个辅助归因的广告活动的描述性标签<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::1ce994b8"></span>归因 | campaign\_type | Campaign type | AF | 带来相关用户的流量来源，可能出现的值为：<ul><li>AppsFlyer对广告系列目的的分类</li><li>UA（拉新）</li><li>Organic（自然量）</li><li>Retargeting（再营销）</li><li>Unknown（未知）（1）</li></ul>（1）应用内事件/应用打开（session）没有归因到任何渠道，或为了遵守隐私保护政策或GDPR的要求，该数据已被删除。 | 字符串 |
| <span id="attribution::d8d5132b"></span>归因 | campaign\_type | Campaign type |  | 指定该活动是用户获取、重定向还是其他类型。 | 字符串 |
| <span id="attribution::76ae00fe"></span>归因 | campaign\_type\_\_assist\_3 |  | AF | 来自第三个辅助归因的活动意图的 AppsFlyer 分类<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::5ba059c9"></span>设备信息 | carrier | 运营商 | SDK | 通过<Anchor target="_blank" href="https://developer.android.com/reference/android/telephony/TelephonyManager#getSimCarrierIdName()">getSimCarrierIdName()</Anchor>获取的运营商名称，由安卓系统提供。另请参见<Anchor target="_blank" href="https://android.googlesource.com/platform/packages/providers/TelephonyProvider/+/master/assets/carrier_list.textpb">运营商映射</Anchor> 。 | 字符串 |
| <span id="attribution::x1d1e08b5"></span>归因 | channel | 渠道 | 链接 | 媒体渠道的流量入口<ul><li>与 [af\_channel](#attribution::1d1e08b5) 相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::760ee8ed"></span>归因 | {"channel__assist_[n]"} (n=1-3) |  | AF | 来自第一个辅助归因的媒体源渠道<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-location"></span>设备位置 | city | 城市 | AF | 设备所在城市该值通常会包含城市名称, 但也可能出现城市行政区划等更准确的位置。 | 字符串 |
| <span id="device-location::ctc00001"></span>设备位置 | city\_\_conversion | 转换后的城市 | AF | 设备在转换时的所在城市。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::cit00001"></span>归因 | click\_id\_type | 点击 ID 类型 | 链接 | 网络点击ID类型。点击ID是附加在广告点击链接后的一组唯一的字母数字标识符，通过追踪具体是哪条广告、哪个广告系列或哪个关键词产生了该点击，从而实现精准的归因。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::civ00001"></span>归因 | click\_id\_value | 点击 ID 值 | 链接 | 来自着陆页 URL 的实际点击 ID 值，用于发送信号以及通过合作伙伴 API 解析完整的活动层级结构。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-location::11aea02f"></span>设备位置 | 大陆 | 大陆 | AF | 大陆名称的两个字母缩写<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::f1c497c7"></span>归因 | contributor[n]\_af\_prt(n=1-3) | Contributor[n] partner | AF | 代理或PMD - 通常转换为小写英文 | 字符串 |
| <span id="attribution::860c6c0d"></span>归因 | contributor[n]\_campaign(n=1-3) | Contributor[n] campaign | AF | 形成助攻的广告系列 | 字符串 |
| 归因 | contributor[n]\_engagement\_type (n=1-3) | Contributor[n] engagement type | AF | 可能出现的值为：<ul><li>可能出现的值包括：preload, click\_to\_download, click\_to\_app, engaged\_click, engaged\_view, view, listening, click\_unspecified, impression\_unspecified</li></ul> | 枚举型 |
| <span id="attribution::daff87fa"></span>归因 | contributor[n]\_match\_type(n=1-3) | Contributor[n] match type | AF | 与match type字段中可能出现的值一致。 | 字符串 |
| <span id="attribution::78fcf7ca"></span>归因 | contributor[n]\_media\_source(n=1-3) | Contributor[n] media source | AF | 形成助攻的媒体渠道 | 字符串 |
| <span id="attribution::d7d270cf"></span>归因 | contributor[n]\_touch\_time(n=1-3) | Contributor[n] touch time | AF | 助攻广告触达用户的时间 | 日期时间 |
| <span id="attribution::43d06f64"></span>归因 | contributor[n]\_touch\_type(n=1-3) | Contributor[n] touch type | AF | 可能出现的值为：<ul><li>点击、展示、TV</li></ul> | 枚举型 |
| <span id="attribution::afacec40"></span>归因 | contributor\_[n]\_engagement\_type | Contributor[n] engagement type | AF | The contributor engagement type | 枚举型 |
| <span id="attribution::942d31ab"></span>归因 | conversion\_name | 转换名称 | AF | 由于用户活动在AppsFlyer系统中创建的转换名称。该字段与conversion\_type相关。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::40c20c30"></span>归因 | conversion\_type | 转化类型 | AF | 转化类型，可能出现的值为：<ul><li>转化类型，记录在AppsFlyer系统中，由用户行为产生，与conversion\_name相关。</li><li>Install（激活）</li><li>Reinstall（重装激活）（1）</li><li>Re-engagement（再互动）</li><li>Unknown（未知）（2）</li></ul>1）如果conversion\_type=reinstall（转化类型为重装激活）且campaign\_type=retargeting（广告系列类型为再营销），则相当于retargeting\_conversion\_type=re-attribution（再营销转化类型为再归因）<br /><br />2）没有归因到任何渠道的应用内事件/应用打开（session） | 字符串 |
| <span id="attribution::x8c179e3b"></span>归因 | cost\_currency | Cost currency | 链接 | 成本币种，参见cost\_value<ul><li>与[af\_cost\_currency](#attribution::8c179e3b)相同</li></ul> | 字符串 |
| <span id="attribution::x8733a05b"></span>归因 | cost\_model | 成本模式 | 链接 | 广告的定价模式（例如CPC、CPM）<ul><li>与[af\_cost\_model](#attribution::8733a05b)相同</li></ul> | 字符串 |
| <span id="attribution::x5647f309"></span>归因 | cost\_value | Cost value | 链接 | 与广告系列相关的成本，参见cost\_model和cost\_currency<ul><li>与[af\_cost\_value](#attribution::5647f309)相同</li></ul> | 货币 |
| <span id="device-location::4a3ca194"></span>设备位置 | country\_code | 国家代码 | AF | <ul><li><Anchor target="_blank" href="https://www.iso.org/iso-3166-country-codes.html">ISO 3166（alpha-2）</Anchor>中两个字符的国家代码，举例来说，US、CN。</li><li>英国的代码是UK而不是GB。</li></ul> | 枚举型 |
| <span id="device-location::ccc00001"></span>设备位置 | country\_code\_\_conversion | 转换时的国家代码 | AF | 转换时采用的ISO 3166（alpha-2）国家代码。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="monetary"></span>monetary | currency\_customer | 货币客户 | N/A | 客户偏好的币种，参见revenue\_value\_customer<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="monetary::rco00001"></span>monetary | revenue\_currency\_original | 收入货币（原始） | SDK | 该事件中报告的原始收入的货币。原始收入值<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::36c62977"></span>归因 | custom\_data | Custom data | SDK | 由广告主在SDK中设置的数据或通过S2S设置的数据，通常用于与第三方对接、受众共享等等。详见针对<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">安卓</Anchor>和<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">iOS</Anchor>应用的具体文档。 | 字符串 \| 对象 |
| <span id="attribution::dc3d05d"></span>归因 | custom\_dimension | 自定义维度 | SDK | AppsFlyer留作后用 | 字符串 |
| <span id="device-info::40b02bb7"></span>设备信息 | customer\_user\_id | Customer user ID | SDK | 客户用户ID（CUID）是一种具有唯一性的用户标识符。该标识符通常由应用所有者（广告主）在用户完成注册时生成并设置。广告主能依据CUID将不同设备中的用户行为串联起来，形成完整的用户链路。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 \| 整数 |
| <span id="device-info::8be2aaee"></span>设备信息 | customer\_user\_id | Customer user ID | SDK | 由应用所有者（广告主）设置的应用用户专属ID。 | 字符串 \| 整数 |
| <span id="device-info::ed856308"></span>设备信息 | deeplink\_url | Deeplink URL | SDK | 把用户引导到具体应用内体验的路径，用于深度链接和延迟深度链接，  <br />体现在归因链接的af\_dp值中。 | 字符串 |
| <span id="protect360::8cb25250"></span>Protect360 | detection\_date | Detection date | AF | 归因后检测到假量的日期。 | 字符串 |
| <span id="protect360::detstate"></span>Protect360 | protect\_detection\_state | Protect 检测状态 | AF | <ul><li>表示 Protect360 为事件（例如广告交互、转化或终端用户事件）判定的作弊检测结果。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::1fd8f0c4"></span>设备信息 | device\_category | 设备类别 | 上报的user\_agent | <ul><li>设备类别（例如MOBILE\_PHONE、TV）</li><li>使用的设备类型：平板电脑、手机、台式机、电视、set\_top\_box、游戏机、媒体播放器、未知设备类别。每当 AppsFlyer 无法检测到设备的用户代理时，就会产生 “未知设备类别” 值。出现这个值时，说明AppsFlyer已尝试识别该设备的特征，但无法将其归纳到任何一个已知的设备类别。</li></ul> | 字符串 |
| <span id="device-info::dfd9504e"></span>设备信息 | device\_download\_time | Device download Time | SDK | 由设备计时器（<Anchor target="_blank" href="https://developer.android.com/reference/android/content/pm/PackageInfo#firstInstallTime">Android</Anchor>/<Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=occ">iOS</Anchor>）记录并转换到UTC时间的应用下载完成时间。该字段值总是以UTC时间显示，  <br />格式为：yyyy-mm-dd hh:mm:ss.sss | 日期时间 |
| <span id="device-info::4a5568db"></span>设备信息 | device\_id\_type | Device ID type | SDK | 在CTV场景中以CTV平台ID类型填充，如Roku的RIDA。 | 枚举型 |
| <span id="device-info::716c46bf"></span>设备信息 | device\_model | 设备型号 | SDK | 设备的商业型号名称。如xiaomi::Redmi或iPhone7 | 字符串 |
| <span id="device-info::2be6278"></span>设备信息 | device\_type | Device Type | SDK | 设备的商业型号名称。<ul><li>【从2022年2月2日开始不再填充该字段】</li><li>该字段将由Device model（设备型号）取代，两者填充的内容相似。</li><li>举例来说，<ul><li>Device model: xiaomi::Redmi Note 8</li><li>Device type: xiaomi-Redmi Note 8</li><li>Device model: iPhone7</li><li>Device type: iPhone 7</li></ul></li></ul> | 字符串 |
| <span id="skan::d5ea0b47"></span>SKAN | did\_win |  | iOS | 用于区分<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">助攻和获得激活归因</Anchor>的广告系列。<ul><li>如果该字段值为true，则表示该广告系列获得了此次激活的归因</li><li>如果该字段值为false，则表示该广告系列在此次激活中形成助攻，但不会呈现在任何SKAN面板或报告中。</li><li>如果该字段值为null，则表示<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">iOS或SKAN版本过低</Anchor>，因此iOS未填充该字段。</li></ul> | Boolean |
| <span id="device-location::e6a26925"></span>设备位置 | dma | DMA（指定市场区域） | AF | 指定市场区域（Designated Market Area）或地理区域，具体由<Anchor target="_blank" href="https://www.nielsen.com/us/en/solutions/nielsen-global-connect/">Nielsen公司</Anchor>界定，用以<Anchor target="_blank" href="/marketers/zh/docs/determine-user-location">判断用户的位置</Anchor>。 | 字符串 |
| <span id="device-location::dmac0001"></span>设备位置 | dma\_\_conversion | 转换时的DMA | AF | 转换时的指定市场区域。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="lifetime-value-events"></span>生命周期价值事件 | end\_user\_event\_type | 最终用户事件类型 | N/A | 识别最终用户事件的类型。值包括 IN\_APP，表示由用户操作触发的应用内事件，以及 SESSION，表示应用启动。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 枚举型 |
| <span id="attribution::8aab1f4d"></span>归因 | engagement\_destination | 参与目的地 | AF | 广告链接到的目标平台组，例如网页登录页面（WEBSITE）或通过深度链接或应用商店（MOBILE）的移动应用程序。当目的地未知或未指定时，可以为空。 |  |
| <span id="attribution::engcat"></span>归因 | engagement\_category | 互动类别 | AF | 描述用户如何与广告互动的高层级分组。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::isintegrated"></span>归因 | is\_integrated | 是否已对接 | AF | 媒体渠道是否已对接？<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | Boolean |
| <span id="attribution::8cea583a"></span>归因 | engagement\_subtype | 参与子类型 | AF | 用户与广告互动的具体方式，比engagement\_type更细分<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::f7713604"></span>归因 | {"engagement_subtype__assist_[n]"} (n=1-3) |  | AF | 用户与广告互动的具体方式，比engagement\_type更细分<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="event"></span>归因 | engagement\_type | 交互类型 | AF | <ul><li>描述用户如何与广告互动的高层级分组</li></ul>可能出现的值为：<ul><li>可能出现的值包括：preload, click\_to\_download, click\_to\_app, engaged\_click, engaged\_view, view, listening, click\_unspecified, impression\_unspecified</li></ul> | 字符串 |
| <span id="attribution::18bbe871"></span>归因 | {"engagement_type__assist_[n]"} (n=1-3) |  | AF | 描述用户与来自第一个辅助归因的广告互动的高级分组<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="event::13df6252"></span>事件 | event\_name | 事件名称 | AF/SDK | <ul><li>由应用发送的归因事件类型或应用内事件名称。归因事件类型包括install（激活）、re-engagement（再互动）等。</li><li>Data Locker中的再营销报告对事件名称的界定如下：retargeting（再营销）指再互动，install（激活）指再归因（重装激活）。在SKAN报告中，应用内事件名称是您在AppsFlyer后台配置的名称。</li><li>在SKAN SRN report中，该字段为Meta ads中配置的应用内事件名称。</li></ul> | 字符串 |
| <span id="event::2f7f426"></span>事件 | event\_revenue | 事件收入 | SDK | <ul><li>以事件收入货币为单位的收入金额</li><li>在$-1,000,000到$+1,000,000（或等值）这个范围以外的金额会显示在原始数据报告，但不显示在汇总报告中。</li></ul> | 字符串 |
| <span id="skan::eb2c0d57"></span>SKAN | event\_revenue | 事件收入 | AF | 计算方式：[以USD为单位的具体事件值总和]/[在指定日期中的事件发生数量] | 浮点数 |
| <span id="event::78cfad98"></span>事件 | event\_revenue\_currency | 事件收入货币 | SDK | 上报到SDK的事件收入货币代码。 | 字符串 |
| <span id="event::f6999087"></span>事件 | event\_revenue\_usd* | 以美元为单位的事件收入 | AF | <ul><li>收入金额。货币单位取决于所使用的报告工具。</li><li>Preferred（首选）或selected（已选）是指在应用层级设置的指定货币。</li><li>Data Locker：始终为USD</li><li>Export（导出数据页）: 指定货币</li><li>Pull API：默认为USD，也可通过&currency=preferred设置指定货币</li><li>Push API：同时包含USD和指定货币这两个字段</li></ul> | 字符串 \| 十进制 |
| <span id="event::6b26cc93"></span>事件 | event\_revenue\_xxx | Event revenue selected currency |  | <ul><li>收入金额。货币单位取决于所使用的报告工具。</li><li>Preferred（首选）或selected（已选）是指在应用层级设置的指定货币。</li><li>Data Locker：始终为USD</li><li>Export（导出数据页）: 指定货币</li><li>Pull API：默认为USD，也可通过&currency=preferred设置指定货币</li><li>Push API：同时包含USD和指定货币这两个字段</li></ul> | 字符串 |
| <span id="attribution::eb80c5ea"></span>归因 | event\_source | 事件来源 | AF | 可能的值取决于互动类型：<ul><li>点击<ul><li>`s2s` （当链接中包含 redirect=false 时）</li><li>`sdk` 否则</li></ul></li><li>展示<ul><li>`s2s` 当出现`af_ua` 或 `af_ip`时，</li><li>`unknown` 否则</li></ul></li><li>跨平台展示<ul><li>无值</li></ul></li></ul> | 枚举型 |
| 事件 | event\_time | 事件时间 | 回传 | 事件时间向下取整后的小时数 | 日期时间 |
| <span id="event::b3d24688"></span>事件 | event\_time | 事件时间 | SDK | <ul><li>事件发生时间</li><li>事件发生时间</li></ul> | 日期时间 |
| <span id="event::isfirstevent"></span>事件 | is\_first\_event |  | AF | <ul><li>表示用户在完成转化后首次执行了该应用内事件。将该字段作为指标随时间汇总，可用于衡量执行特定应用内事件的独立用户数量。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 布尔 |
| <span id="event::isattributed"></span>事件 | is\_attributed |  | AF | <ul><li>表示某个终端用户事件是否已关联到归因记录。当事件关联到归因记录（自然或非自然）时为True。当没有可用归因记录时为False（例如因GDPR被删除、已过期或其他不可用情况）；这些事件被视为自然事件。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 布尔 |
| <span id="event::devevttime"></span>事件 | device\_event\_time | 设备事件时间 | AF | 设备端事件时间戳（af\_timestamp），记录事件生成并添加到SDK缓存的时间。AppsFlyerSDK以Unix纪元以来的毫秒数形式发送该时间。在Android上，该时间使用System.currentTimeMillis()生成；在iOS上，则使用等效的系统API生成。该值会在服务端进行标准化，并存储为GMT时间戳。注意：此处为客户端时间，并不完全可信，因为设备时钟可能不准确或被人为更改。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 时间戳 |
| <span id="event::origevttime"></span>事件 | original\_event\_time | 原始事件时间 | AF | 应用截断逻辑前的原始事件发生时间。适用于超晚事件<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 时间戳 |
| <span id="event::556034db"></span>事件 | {"event_time__assist_[n]"} (n=1-3) |  | AF | 来自第一个辅助归因的事件发生时间<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | TIMESTAMP |
| <span id="event::55b76d8f"></span>事件 | event\_time\_\_attribution |  | AF | 来自归因（参与）事件的事件发生时间<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | TIMESTAMP |
| <span id="time"></span>用时 | event\_time\_\_conversion |  | N/A | 事件时间戳（转化、归因、会话或应用内事件）。*注意*：[event\_time\_\_](#time) conversion 是一个上下文别名。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 日期时间 |
| <span id="event::94d6064c"></span>事件 | event\_type | 事件类型 | AF/SDK | 归因事件类型。归因事件类型包括install（激活）、re-engagement（再互动）等。 | 字符串 |
| <span id="pba-event"></span>PBA事件 | event\_url | Event URL | Web SDK | 产生事件的网页的URL（相当于网站访问中的Original URL） | 字符串 |
| <span id="skan::ed9e6b7a"></span>SKAN | event\_uuid |  | AF | 具有唯一性的随机标识符，便于渠道识别重复的回传 | 字符串 |
| <span id="event::819be544"></span>事件 | event\_value | 事件值 | SDK | 通常由AppsFlyer SDK发送的事件内容。以JSON形式存储；如果值无法解析为JSON，则使用\_\_unparseable\_\_键进行包装。如果值超过3000个字符，则会被截断为3000个字符，并在JSON中添加is\_truncated=true。 | 字符串 |
| <span id="event::evtorder"></span>事件 | event\_order | 事件顺序 | AF | 事件生成时设备上记录的事件顺序计数器，采用AppsFlyer SDK使用的格式。SDK名称：iaecounter。这是一个持续递增的计数器，会随每个应用内事件递增，并在应用重新安装时重置。该值由SDK以字符串形式发送。重要提示：该字段在设备端生成，可能会被作弊者篡改。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 长 |
| <span id="skan::b328108"></span>SKAN | event\_value | 事件值 | S2S | <ul><li>默认值为null</li><li>包含一个字符串。该字符串由使用自定义解析方式或通过<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>发送事件的应用设置。</li><li>该数据供广告主在其内部系统中使用，AppsFlyer不会使用该数据。</li></ul> | 字符串（JSON） |
| <span id="skan::15ab0ab2"></span>SKAN | fidelity\_type | Fidelity type |  | <ul><li><Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">用于区分广告呈现</Anchor>方式，这会影响到归因结果。通过0和1来表达，具体如下：<ul><li>浏览型广告（View-though Ads）：0</li><li>渲染型广告（StoreKit-rendered Ads）：1</li><li>如果SKAN版本低于2.2，请忽略该字段值。</li></ul></li></ul> | 整数 |
| <span id="protect360::e2ef1cd4"></span>Protect360 | fraud\_reason | Fraud reason | AF | Protect360：详见blocked reason（拦截原因）字段的说明。 | 字符串 |
| <span id="protect360::f3bc9fc2"></span>Protect360 | fraud\_sub\_reason | Fraud sub reason | AF | Protect360：详见blocked sub reason（详细拦截原因）字段的说明。 | 字符串 |
| <span id="device-info::e7bb2cb9"></span>设备信息 | gdpr\_applies | GDPR applies | SDK | 用于标识用户是否属于DMA（数字市场法案）监管范围：属于为true，不属于为false。 | 布尔 |
| <span id="attribution::169162d3"></span>归因 | gp\_broadcast\_referrer | Google Play broadcast referrer | Google Play Store | Google Play Broadcast Referrer | 字符串 |
| <span id="attribution::2ad3d84b"></span>归因 | gp\_click\_time | Google Play click time | Google Play字段 | 用户点击广告后，在Google Play中看到相关应用页面的时间。<ul><li>时间数据的来源：Google API</li><li>4.8.5及以上版本的Android SDK支持该字段</li><li>举例来说，将install\_time与gp\_click time进行对比，从而考察用户从下载应用到首次打开应用之间的时间跨度。</li></ul> | 时间戳 |
| <span id="attribution::d8bdd9fe"></span>归因 | gp\_install\_begin | Google Play install begin time | Google Play Store | 激活起始时间<ul><li>时间数据的来源：Google API</li><li>4.8.5及以上版本的Android SDK支持该字段</li></ul> | 时间戳 |
| <span id="attribution::67a30c47"></span>归因 | gp\_referrer | Google Play Referrer | Google Play Store | 安装包的referrer链接<ul><li>4.8.5及以上版本的Android SDK支持该字段</li></ul> | 字符串 |
| <span id="attribution::fe9e4cb0"></span>归因 | hardware\_id\_type | 硬件ID类型 |  | 用户不可重置的设备唯一标识符类型。 | 字符串 |
| <span id="attribution::6bcef26e"></span>归因 | hardware\_id\_value | 硬件ID值 |  | 一个唯一的设备级标识符（例如，Android ID、IMEI），用户无法重置。该值对应于 hard [ware\_id\_type 字段](#attribution::fe9e4cb0)中指定的类型。<ul><li>与 android\_id 和 imei 相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::2191a08e"></span>归因 | http\_referrer | HTTP Referrer | AF | 客户网站的前序网页URL，即在访问客户网站前立即链接到客户网站的网页。当访问URL中没有特定归因参数（PID、UTM或点击ID）时，该字段用作归因兜底依据。 | 字符串 |
| <span id="device-info::e0372922"></span>设备信息 | idfa | IDFA | SDK | iOS设备上的可重置广告ID。若IDFA不可用，该字段会显示为0。 | 字符 |
| <span id="device-info::8471310d"></span>设备信息 | idfv | IDFV | SDK | iOS提供的应用开发者标识符 | 字符 |
| <span id="device-info::d4bf0a30"></span>设备信息 | imei | IMEI | SDK | 不可重置的永久性设备ID | 字符 |
| <span id="ad-revenue::5406d519"></span>广告收入 | impressions | 展示 | Ad revenue API | 用户看到广告的次数 | 字符串 |
| <span id="attribution::instappdl"></span>归因 | install\_app\_store | 安装应用商店 | AF | 应用的安装来源应用商店（例如Google Play、Samsung Galaxy Store、Xiaomi Marketplace、Huawei AppGallery）。该字段仅适用于Android，并由应用开发者填充。在我们的 KB 中查看更多详情 — <Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation">设置多店铺 Android 归因</Anchor><ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="skan::913c6896"></span>SKAN | install\_date | 激活日期 | iOS | 由AppsFlyer根据回传接收时间估算得出 | 时间字符串 |
| <span id="attribution::15b5bb86"></span>归因 | install\_time | 激活时间 | 回传 | <ul><li>UA（用户获取）：用户安装相关应用后首次打开该应用的时间。</li><li>再营销：再互动/再归因后首次打开应用的时间。</li></ul> | 日期时间 |
| <span id="skan::84c4214f"></span>SKAN | install\_type | 激活类型 | iOS | 新增激活 | 字符串 |
| <span id="skan::576274f5"></span>SKAN | interval | Interval | AF | 用户行为窗口期间隔时长。 | 整数 |
| <span id="device-location::f8003308"></span>设备位置 | ip | IP | AF | <Anchor target="_blank" href="/marketers/zh/docs/determine-user-location">IP地址</Anchor>：IPV4或IPV6。AppsFlyer会根据IP地址判断用户位置。如有需要，广告主可以选择在报告和回传中<Anchor target="_blank" href="/marketers/zh/docs/apply-ip-masking-to-user-data">掩盖IP地址</Anchor>。 | 字符串 |
| <span id="attribution::869dd814"></span>归因 | ip\_address\_type | IP 地址类型 |  | 指定 ip\_addres [s\_value 字段中提供的 IP 地址的格式（例如 IP](#device-location::xf8003308) v4、IPv6）。<ul><li>启用IP屏蔽后，类型将为「MD5\_HASH」。对于中国PIPL解决方案，类型将为「SHA256\_PIPL\_HASH」。</li></ul> | 字符串 |
| <span id="device-location::xf8003308"></span>归因 | ip\_address\_value | IP地址值 | AF | 设备的 IPv4 或 IPv6 地址值。可以是MD5或SHA256哈希值。<ul><li>与 ip 相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::e79f7a7b"></span>设备信息 | is\_lat | Limit ad tracking | SDK | Limit ad tracking（限制广告跟踪，简称LAT）：<ul><li>iOS：Apple在iOS 14以后的版本中不再使用LAT，而是通过ATT判断用户的隐私状态，在这种情况下请忽略is\_lat。<br />对于iOS 14以下的版本，如果该字段值为true，即表示IDFA不可用且显示为0。</li><li><Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/identifier/AdvertisingIdClient.Info#public-constructor-summary">安卓</Anchor>：如果该字段值为true，即表示用户选择了关闭个性化广告，这种情况下SDK不会收集GAID信息，且GAID字段值为0。</li></ul> | 布尔式枚举 |
| <span id="protect360::d8a27dfc"></span>Protect360 | is\_organic | 是否自然 | AF | 表示应用内事件是否与自然激活有关。 | 字符串 |
| <span id="attribution::8aef34c8"></span>归因 | is\_primary\_attribution | 是否主归因 | AF | UA（用户获取）：True  <br />  <br />再营销：在再互动窗口期内，AF会将用户同时归因到最初的拉新渠道（即再互动之前的渠道）以及带来再互动的渠道。如果事件发生在再互动窗口期内，初始媒体渠道字段会显示为FALSE（即不是主要渠道），而再互动渠道字段则为TRUE。<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">详情请见此处。</Anchor> | 布尔式枚举 |
| <span id="event::isa00001"></span>事件 | is\_attributed | is\_attributed | AF | <ul><li>表示某个终端用户事件是否已关联到归因记录。当连接到归因记录（自然流量或非自然流量）时为真。当没有归因记录时返回 false（例如，因 GDPR 要求被删除、已过期或因其他原因不可用）；此类事件被视为自然流量。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 布尔 |
| <span id="event::ife00001"></span>事件 | is\_first\_event | 是首次活动 | AF | <ul><li>表示用户在完成转化后首次执行了该应用内事件。将此数据作为指标进行统计，有助于衡量执行了特定应用内操作的独立用户数量。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 布尔 |
| <span id="event::3177f2dd"></span>事件 | is\_receipt\_validated | 收入已验证 | AF | 在SDK中配置的话则为true/false/null，否则为空 | 布尔式枚举 |
| <span id="attribution::e433456e"></span>归因 | is\_retargeting | Is retargeting | 链接 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports#拦截原因blocked-reason">UA：false</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports#拦截原因blocked-reason">再营销</Anchor>：对于再营销转化和事件，该字段的值为True</li></ul> | 布尔式枚举 |
<span id="d-Y"></span>| <span id="protect360::1e7f166b"></span>Protect360 | <span id="K-gt-FI"></span>is\_tagged |  | AppsFlyer | <span id="YPo"></span>表示检测是否被标记。 | 字符串 |
| <span id="attribution::1fb276b0"></span>归因 | keyword\_id | 关键词ID | 链接 | 由广告平台返回，是af\_keyword的ID。 | 字符串 |
| <span id="attribution::dc04765b"></span>归因 | keyword\_match\_type | Keyword match type | AF | <ul><li>仅Google Adwords提供该字段。</li><li>从2021年2月15日开始，该字段不再显示与Apple Search Ads相关的值。</li></ul> | 字符串 |
| <span id="attribution::x9dd48973"></span>归因 | keywords | 关键词 | 链接 | 用户在线搜索时使用的字词<ul><li>与[af\_keywords](#attribution::9dd48973)相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::80f36786"></span>归因 | keywords\_id |  | 链接 | 广告网络返回的ID，作为关键词的标识符。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::5d72ff40"></span>设备信息 | language | 语言 | SDK | 由设备报告并由设备操作系统设置的语言（区域设置）（IETF BCP 47 语言标签）。通常以ll-DD格式显示。其中ll是语言， DD是方言。例如，en-ZA表示南非地区使用的英语。 | 字符串 |
| <span id="attribution::cecc12c5"></span>归因 | match\_type | 匹配类型 | AF | <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#归因方法">各种类型的归因方法</Anchor>。可能出现的值有：<ul><li>SRN</li><li>id\_matching（ID匹配）</li><li>probabilistic（概率模型匹配）</li><li>deeplink（深度链接）</li><li>preinstall（预装）</li><li>gp\_referrer (Google Play referrer字符串)</li><li>fb\_referrer、ig\_referrer（Meta install referrer)）</li><li><Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution#referrer-implementation%E2%80%94thirdparty-android-app-stores">第三方安卓应用商店referrer</Anchor></li></ul> | 字符串 |
| <span id="skan::ae39e2c4"></span>SKAN | max\_event\_counter | Max event counter | AF | 用于判断用户完成某个应用内事件的次数，计算方法为：[ (min\_event\_counter + max\_event\_counter) / 2]取整。请注意：必须四舍五入取整。  <br />举例来说，  <br />A. 如果min = 0，max = 1，则平均值为0.5；取整后得到的结果为1。  <br />B. 如果min = 5，max = 10，则平均值为7.5；取整后得到的结果为8。 | 整数 |
| <span id="skan::11f44c7e"></span>SKAN | max\_revenue | Max revenue | AF | 收入数据总是呈现在skad\_revenue字段中。如果您使用SKAN 4或自定义模式（Custom Mode），则用于计算skad\_revenue的范围（即关联到相关事件的范围）通过min\_revenue 和max\_revenue表达。 | 实数 |
| <span id="skan::61d427e9"></span>SKAN | max\_time\_post\_install | Max time post-install | AF | <ul><li>在自定义模式（Custom）中：AppsFlyer对于激活时间的计算方式为回传接收时间 - 36h - (min\_time\_post\_install + max\_time\_post\_install)的平均值。但如果CV = 0，则(min\_time\_post\_install + max\_time\_post\_install)的平均值视为0。</li><li>在解析模式（Decode）中：min\_time\_post\_install比max\_time\_post\_install中设置的值少一小时，max值等于您在解析模式的转化映射中设置的[hours\_from\_install](#skan::2c7e94a3)。</li></ul> | 整数 |
| <span id="skan::8c407dd5"></span>SKAN | measurement\_window | SKAN measurement window | AF | 用户行为窗口期的时长。默认情况下，该字段的值为24h（即窗口期默认为24小时）。 | 整数 |
| <span id="pba-attribution"></span>PBA归因 | media\_channel | Media channel | Web SDK | 获得网站访问归因的媒体渠道 | 字符串 |
| <span id="attribution::83b91456"></span>归因 | media\_source | 媒体渠道 | 链接 | <Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions#媒体渠道数据限制">获得归因的媒体渠道或restricted</Anchor>（受限） | 字符串 |
| <span id="attribution::41d00e54"></span>归因 | {"media_source__assist_[n]"} (n=1-3) |  | AF | 媒体来源归因于来自第一个辅助归因的事件<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::929e716c"></span>归因 | media\_type | 媒体类型 | AF | 用于标记广告链接所在的媒体类型。分为以下两种：<ul><li>app：广告链接投放在应用中</li><li>web：广告链接投放在移动端网页中</li></ul> | 字符串 |
| <span id="ad-revenue::63a5ea9a"></span>广告收入 | mediation\_network | Mediation network | Ad revenue API | 向AppsFlyer上报事件的聚合平台 | 字符串 |
| <span id="skan::f2af60ce"></span>SKAN | min\_event\_counter | Min event count | AF | 用于计算用户完成某一事件的次数。用于判断用户完成某个应用内事件的次数，计算方法为：[ (min\_event\_counter + max\_event\_counter) / 2]取整。请注意：必须四舍五入取整。  <br />举例来说，  <br />A. 如果min = 0，max = 1，则平均值为0.5；取整后得到的结果为1。  <br />B. 如果min = 5，max = 10，则平均值为7.5；取整后得到的结果为8。 | 整数 |
| <span id="skan::224372e8"></span>SKAN | min\_revenue | Min revenue | AF | 收入数据总是呈现在skad\_revenue字段中。如果您使用SKAN 4或自定义模式（Custom Mode），则用于计算skad\_revenue的范围（即关联到相关事件的范围）通过min\_revenue 和max\_revenue表达。 | 实数 |
| <span id="skan::2c7e94a3"></span>SKAN | min\_time\_post\_install | Min time post-install | AF | <ul><li>在自定义模式（Custom）中：AppsFlyer对于激活时间的计算方式为回传接收时间 - 36h - (min\_time\_post\_install + max\_time\_post\_install)的平均值。但如果CV = 0，则(min\_time\_post\_install + max\_time\_post\_install)的平均值视为0。</li><li>在解析模式（Decode）中：min\_time\_post\_install比max\_time\_post\_install中设置的值少一小时，max值等于您在解析模式的转化映射中设置的[hours\_from\_install](#skan::2c7e94a3)。</li></ul> | 整数 |
| <span id="ad-revenue::90d3bcb3"></span>广告收入 | monetization\_network | Monetization network | Ad revenue API | 分发广告的渠道 | 字符串 |
| <span id="attribution::7160d53a"></span>归因 | network\_account\_id | Network account ID | 链接 | 广告主在广告平台上的账户ID | 字符串 \| 整数 |
| <span id="device-info::4afa15f"></span>设备信息 | oaid | <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary#o">OAID</Anchor> | SDK | 部分安卓设备上的用户可重置ID，通常作为GAID的替代。 | 字符 |
| <span id="device-info::44749108"></span>设备信息 | operator | 运算符 | SDK | <Anchor target="_blank" href="https://developer.android.com/reference/android/telephony/TelephonyManager#getNetworkOperatorName()">根据SIM MCCMNC识别的移动服务商名称。对于注册用户，可通过安卓的getNetworkOperatorName()获取该名称。</Anchor> | 字符串 |
| <span id="attribution::2e20e418"></span>归因 | original\_url | Original URL | 链接 | <ul><li>UA（用户获取）：点击/展示链接。若使用品牌链接，则该字段的值为品牌链接。</li><li>在再营销场景中，该字段的值为以下任意一种：再营销链接、深度链接数据、空值（SRN）</li></ul> | 字符串（URL） |
| <span id="attribution::rlw00001"></span>归因 | requested\_lookback\_window | 要求的回溯窗口 | 链接 | 在任务链接中指定的原始未解析值。用于确定点击或展示可归因于转化所对应的时段。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::c9430692"></span>设备信息 | os\_version | OS 版本 | SDK | 设备上的操作系统版本 | 字符串 |
| <span id="device-info::ovc00001"></span>设备信息 | os\_version\_\_conversion | 转换时的操作系统版本 | AF | 转换时设备上运行的操作系统版本。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="ad-revenue::88ea46f4"></span>广告收入 | placement | Placement | Ad revenue API | 相关应用中的广告展示位置。 | 字符串 |
| <span id="device-info::858b3f6a"></span>设备信息 | platform | 平台 | SDK | 应用运行所在的操作系统或生态系统OS版本 | 枚举型 |
| <span id="app::1f608704"></span>应用 | 平台组 | 平台组 | AF | 业务层级分组，用于将多个Platform值归入更广泛的类别，以支持有意义的报告。这有助于团队按「Mobile App」「Web」「CTV app」等分组分析表现，反映事件发生的平台类别。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::3d0f4698"></span>设备信息 | platform\_user\_id\_type |  | SDK | 平台生成的用户唯一标识符类型。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::bbda346b"></span>设备信息 | platform\_user\_id\_value |  | SDK | 平台生成的用户唯一标识符值。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-location::9d71ef7e"></span>设备位置 | postal\_code | Postal code | AF | 设备所在地的邮政编码或邮政编码 | 字符串 |
| <span id="product-line"></span>产品线 | product\_line\_id | 产品线 ID | N/A | AppsFlyer 中产品线实体的唯一标识符。跨平台分组相似应用，以实现统一的跨平台测量。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="product-line::d5e0225b"></span>产品线 | product\_line\_name | 产品线名称 | N/A | 跨平台分组相似应用的产品线实体名称。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="pba"></span>pba | query\_params | Query params | 链接 | 跳转URL中“？”号之后的查询参数  <br />示例：<Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">https://www.brandpitt.com/signin?utm_source=Google</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&utm\_term=shoes</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&utm\_campaign=cool</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&c=summer</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&af\_siteid=publisher</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&af\_sub1=helloworld</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&af\_keyword=shoes</Anchor><br /><br />如果URL中没有查询参数，则该字段的值为null | 字符串 |
| <span id="device-info::195c85df"></span>设备信息 | raw\_consent\_data | Raw consent data | SDK | 返回一个JSON对象，包含广告主发送给AppsFlyer的完整原始DMA同意数据。 | 字符串 \| 对象 |
| <span id="device-location::1720981c"></span>设备位置 | region | 区域 | AF | 根据SDK上报的设备IP地址判断。SKAN场景中根据country\_code（国家代码）的参数值来判断。 | 字符串 |
| <span id="protect360::d685b64e"></span>Protect360 | rejected\_reason | Rejected reason | AF | Protect360：计划弃用。目前该字段显示拦截原因。 | 字符串 |
| <span id="protect360::440536f1"></span>Protect360 | rejected\_reason\_value | Rejected Reason value | AF | <ul><li>Protect360：适用于归因后识别出的被劫持的激活/应用内事件，显示其真实的有效助攻渠道。可能出现的值为contributor[1-3]或者organic。</li><li>在Data Locker中，该字段显示为validation\_reason\_value。</li></ul> | 字符串 |
| <span id="attribution::eecda2a2"></span>归因 | retargeting\_conversion\_type | Retargeting conversion type | AF | <ul><li>UA（用户获取）：Re-install（重装激活）</li><li>再营销场景中可能出现的值为Re-engagement（再互动）或Re-attribution（再归因）</li></ul> | 枚举型 |
| <span id="monetary::cf660373"></span>monetary | revenue\_usd | revenue\_usd | N/A | 事件收入转换为美元。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 数值 |
| <span id="monetary::1248941c"></span>monetary | revenue\_value\_customer | 收入值客户 | N/A | 换算为客户首选币种的事件收入——请参见currency\_customer。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 数值 |
| <span id="monetary::nrvcust"></span>monetary | net\_revenue\_value\_customer | 客户币种净收入值 | AF | 事件净收入（例如购买或订阅），已转换为客户偏好的币种，请参见currency\_customer。该值等于总金额（event\_revenue\_value\_customer）减去应用商店/平台佣金和任何适用税费（VAT/GST、销售税）。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 十进制 |
| <span id="monetary::nrusd"></span>monetary | net\_revenue\_usd | 净收入USD | AF | 事件净收入（例如购买或订阅），已转换为美元。该值等于总金额（event\_revenue\_usd）减去应用商店/平台佣金和任何适用税费（VAT/GST、销售税）。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 十进制 |
| <span id="monetary::rvo00001"></span>monetary | revenue\_value\_original | 收入金额（原始） | SDK | 该事件中报告的原始收入金额，以原始货币计价。原始收入币种<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 数值 |
| <span id="app::89931c41"></span>应用 | sdk\_version | SDK version | SDK | AppsFlyer SDK版本 | 字符串 |
| <span id="ad-revenue::ae2875be"></span>广告收入 | segment | 细分 | Ad revenue API | 广告收入中的广告段位名称 | 字符串 |
| <span id="attribution::xe9b53459"></span>归因 | site\_id | 子渠道ID | 链接 | <ul><li>表示发布商ID。一个媒体渠道可在多个发布商投放广告，每个发布商均通过不同的站点ID进行标识。</li><li>与 [af\_siteid](#attribution::e9b53459) 相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::b09cbd8f"></span>归因 | {"site_id__assist_[n]"} (n=1-3) |  | AF | <ul><li>表示来自第一个辅助归因的发布者 ID</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="skan::70c7a914"></span>SKAN | skad\_ad\_network\_id | Ad network ID | iOS | 接收回传的广告平台的ID | 字符串 |
| <span id="skan::85b51b68"></span>SKAN | {"skad_ambiguous"} {"_event"} | Ambiguous event | AF | 如果该参数的值为true，则表示iOS回传的接收时间在广告主在面板中更改SKAN设置后的最初72小时内。  <br />由于SKAN使用的计时器过多，因此AppsFlyer无法准确地映射该事件。 | 布尔 |
| <span id="skan::89c88e44"></span>SKAN | skad\_app\_id | 应用ID | iOS | 应用ID | 字符串 |
| <span id="skan::95b0801d"></span>SKAN | skad\_attribution\_signature | Attribution signature | iOS | 广告平台在SKAN回传中添加的签名。 | 字符串 |
| <span id="skan::9c8a097a"></span>SKAN | skad\_campaign\_id | Campaign ID | iOS | 用于发布该则广告的广告系列ID，范围为0-100。 | 整数 \| 字符串 |
| <span id="skan::275a8850"></span>SKAN | skad\_coarse\_conversion\_value | Coarse conversion value | iOS | <ul><li>粗粒度转化值，可能出现的值为low、medium或high。</li><li>在SKAN 3中该值为null</li></ul> | 字符串 |
| <span id="skan::41d3b405"></span>SKAN | skad\_conversion\_value | Conversion value | iOS | iOS上报的转化值，范围为0-63。<ul><li>若该字段的值为null，则表示iOS未填充该字段</li></ul> | 整数 |
| <span id="skan::accd42a5"></span>SKAN | skad\_did\_win | Did win | iOS | 用于区分<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">助攻和获得激活归因</Anchor>的广告系列。<ul><li>如果该字段值为true，则表示该广告系列获得了此次激活的归因</li><li>如果该字段值为false，则表示该广告系列在此次激活中形成助攻，但不会呈现在任何SKAN面板或报告中。</li><li>如果该字段值为null，则表示<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">iOS或SKAN版本过低</Anchor>，因此iOS未填充该字段。</li></ul> | 布尔 |
| <span id="skan::3b4ad54f"></span>SKAN | skad\_fidelity\_type | Fidelity type | iOS | <ul><li>用于区分<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">广告呈现</Anchor>方式，这会影响到归因结果。通过0和1来表达，具体如下：<ul><li>浏览型广告（View-though Ads）：0</li><li>渲染型广告（StoreKit-rendered Ads）：1</li><li>如果SKAN版本低于2.2，请忽略该字段值。报告中已添加该字段，但不一定带有值。</li></ul></li></ul> | 整数 |
| <span id="skan::a36c9f3c"></span>SKAN | skad\_mode | SKAN mode | AF | 用于解析iOS回传的转化衡量模式，可用值包括：<ul><li>custom\_decode</li><li>revenue</li><li>events</li><li>skan4</li><li>custom\_encode</li><li>engagement</li></ul> | 字符串 |
| <span id="skan::546f8b91"></span>SKAN | skad\_postback\_sequence\_index | Postback sequence index | iOS | <ul><li>该字段代表SKAN窗口，可能出现的值为0、1或2。</li><li>在SKAN 3中，该字段的值为0。</li></ul> | 整数 |
| <span id="skan::8e4acd4"></span>SKAN | skad\_redownload | Redownload | iOS | 如果该字段的值为true，则表示用户重新下载了相关应用 | 布尔 |
| <span id="skan::d831aefd"></span>SKAN | skad\_revenue | 收入 | iOS | 以USD为单位的事件收入金额。 | 浮点数 |
| <span id="skan::6d2ea88c"></span>SKAN | skad\_source\_app\_id | Source app ID | iOS | <ul><li>子渠道ID，即发布相关广告的应用。</li><li>字段填充方式取决于隐私阈值。</li></ul> | 字符串 |
| <span id="skan::3dbc953"></span>SKAN | skad\_source\_domain | Source domain | iOS | <ul><li>该字段的值代表可归因的网页广告来源</li><li>在SKAN 3中该值为null</li></ul> | 字符串 |
| <span id="skan::19de61ba"></span>SKAN | skad\_source\_identifier | Source identifier | iOS | <ul><li>该字段的值最多可有四位数</li><li>在SKAN 3中该值为null</li></ul> | 字符串 |
| <span id="skan::b186321d"></span>SKAN | skad\_transaction\_id | SKAN transaction ID | iOS | 由Apple提供的回传ID | 字符串 |
| <span id="skan::3f316453"></span>SKAN | skad\_version | SKAN version | iOS | SKAN version | 字符串 |
| <span id="skan::3cd1002"></span>SKAN | source\_app\_id |  | AF | 子渠道ID，即发布该广告的应用。该字段与skad\_source\_app\_id完全一致。 | 字符串 |
| <span id="device-location::6ae9b695"></span>设备位置 | state | 州/省 | AF | 设备所在的州或省 | 字符串 |
| <span id="device-location::stc00001"></span>设备位置 | state\_\_conversion | 转换时的状态 | AF | 设备在转换时的所在州或省。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="iapsubscription::bd419a23"></span>订阅 | store\_commission | 商店抽成 | True Revenue API | 应用商店在已售产品中的抽成比例。<ul><li>以百分点的形式表达。</li><li>举例来说，30</li></ul> |  |
| <span id="attribution::4c11e393"></span>归因 | store\_product\_page | Store product page | AF | 安卓或Apple App Store（iOS 15+）的自定义产品页，用户点击广告后会跳转到该页面。 | 字符串 |
| <span id="attribution::b75cae23"></span>归因 | store\_product\_page\_id |  | 链接 | 安卓或Apple App Store（iOS 15+）的自定义产品页，用户点击广告后会跳转到该页面。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::2dc09e38"></span>设备信息 | store\_reinstall | Store reinstall | SDK | Apple应用商店基于Apple用户ID来判断Apple Search Ads带来的用户是否记为重装激活：<ul><li>新用户：false</li><li>现有用户重装激活：true</li></ul> | 布尔值 \| 字符串 |
| <span id="attribution::ef045054"></span>归因 | {"sub_param_[n]"} (n=1-5) |  | 链接 | 用于归因的附加跟踪参数<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::subp4"></span>归因 | sub\_param\_4 |  | AF | 用于归因的附加跟踪参数<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::subp5"></span>归因 | sub\_param\_5 |  | AF | 用于归因的附加跟踪参数<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::x9fdff16d"></span>归因 | sub\_site\_id | 子站点ID | 链接 | 分发布商分配的标识符。<ul><li>与 [af\_sub\_siteid](#attribution::9fdff16d) 相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="protect360::3b89b7c1"></span>Protect360 | tagged\_additional\_data |  | AF | 一个动态字段，正在根据标记类型填充相关数据。例如：如果标记的原因是“新发布” - 我们将反映相关发布包的包号。 | 字符串 |
| <span id="protect360::d46f7957"></span>Protect360 | tagged\_type |  | AF | 表示标记类型，该类型标记了检测。标记类型示例包括：新发布、应用评估等。 | 字符串 |
| <span id="protect360::c64c1afb"></span>Protect360 | tagged\_validation\_reason\_value |  | AF | 说明在检测处于实施模式和实时情况下，合法的贡献者以获得归属。 | 字符串 |
| <span id="skan::c7910cfb"></span>SKAN | timestamp | 时间戳 | 广告平台 | AppsFlyer接收到回传数据的时间。  <br />在Google Ads和Meta ads投放场景中，该字段代表AppsFlyer从Google和Meta ads API接收到数据的时间 | 时间戳 |
| <span id="time::tzc00001"></span>用时 | timezone\_customer | 时区（客户） | AF | 应用所有者首选的时区，采用 IANA 格式（例如：Europe/Paris、America/Sao\_Paulo）。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="time::tzcc0001"></span>用时 | timezone\_customer\_\_conversion | 转化时的时区（客户） | AF | 应用所有者在转换时所选的时区，采用 IANA 格式（例如：Europe/Paris、America/Sao\_Paulo）。<ul><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="attribution::a543f19e"></span>归因 | total\_candidates | 总候选人 | AF | 表示在转换时评估的给定设备的总参与次数（点击、展示和其他参与类型）。 | 字符串 |
| <span id="xapp"></span>归因 | unified\_app\_id | 统一应用ID | SDK | AppsFlyer中的应用唯一标识符。原始 [app\_id](#app) 是平台内应用程序的标识符；[unified\_app\_id](#xapp) 将其跨平台标准化，以防止平台之间发生冲突。&lt;platform>[构造规则：-对于移动平台（安卓、ios），](#app)[unified\_app\_id](#xapp) 等于原始 [app\_id](#app)。-对于所有其他平台（网络、CTV 等），[unified\_app\_id 是以平台和连字符为前缀的原始 app\_id](#xapp)，例如 “-&lt; [app\_id](#app) >”。<ul><li>与[应用ID](#app)相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="device-info::a74b0cd"></span>设备信息 | user\_agent | User agent | 链接 | 用于标识发起请求的浏览器、操作系统、设备类型和应用版本的字符串。 | 字符串 |
| <span id="attribution::32f28e6f"></span>归因 | vendor\_id\_type | 供应商 ID 类型 |  | 设备+应用程序供应商的唯一标识符类型。 | 字符串 |
| <span id="device-info::x8471310d"></span>归因 | vendor\_id\_value | 供应商 ID 值 | SDK | 设备+应用程序供应商的唯一标识符值。<ul><li>与[idfv](#device-info::8471310d)相同。</li><li>仅在<Anchor target="_blank" href="/marketers/zh/docs/about-data-locker-advanced-reports">高级报表</Anchor>中提供。</li></ul> | 字符串 |
| <span id="pba-event::c1d28dd1"></span>PBA - 事件 | web\_event\_type | Web event type | Web SDK | 网页事件的类型（访问、事件等） | 字符串 |
| <span id="device-info::fdb1b524"></span>设备信息 | wifi | WIFI | SDK | 仅可能出现TRUE或FALSE两种值 | 布尔式枚举 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01JYP22DSGHFMRW5JXDWH6YZZQ=%E6%A6%82%E8%A7%88 01H8BNKT33XGHES55AZXCY1H03=%E6%8F%90%E7%A4%BA d%3FY%3D=d-Y K%26gt%3BFI=K-gt-FI Ao%3B%7C=Ao YPo%5B=YPo" />

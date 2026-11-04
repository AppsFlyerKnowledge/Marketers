---
title: Pull API原始数据报告
metadata:
  keywords:
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2020-04-14T18:24:00Z'
  edited_at: '2026-10-14T10:05:57Z'
  id: 360007530258
  locale: zh-cn
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/zh-cn/articles/360007530258
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 您可以使用该API拉取CSV格式的原始数据报告。本文为您介绍了具体的使用方法。

[![PullAPIRaw_us-en.png](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)

<div id="pull-api-raw-data" />

## Pull API原始数据报告

* Pull API能够帮助您拉取到CSV格式的原始数据报告。<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">详情请见原始数据报告说明。</Anchor>
* 可用的筛选条件包括：媒体渠道、日期范围、应用内事件名称以及地理位置。
* Pull API的其他功能包括：
  * 选择货币
  * 选择时区

<div id="raw-data-reports-nonorganic" />

<div id="protect360-fraud" />

<div id="ad-revenue-raw-data" />

<div id="retargeting" />

<div id="raw-data-reports-organic" />

<div id="raw-data-reports-available-via-pull-api" />

#### Pull API能够拉取到的原始数据报告

<table><tbody><tr><th><span>报告</span></th><th><span>说明</span></th><th><span>更新频率</span></th></tr><tr><td colspan="3"><strong>原始数据报告（非自然）</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-report-v5" target="_blank">激活</a></td><td><span>用于记录非自然激活。每当有用户首次启动应用时就会生成一条记录。<br/></span></td><td><span>实时</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-report-v5" target="_blank">应用内事件</a></td><td><span>于记录用户完成的事件。<br/></span></td><td><span>实时</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-uninstall-events-report-v5" target="_blank">卸载</a></td><td><span>用于记录用户的应用卸载情况。<br/></span></td><td><span>每日更新</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-v5" target="_blank">重装激活</a><br/></span></td><td><span>用于记录用户卸载应用后与拉新渠道互动并在再归因窗口期内重新安装并激活应用的情况。</span></td><td><span>实时</span></td></tr><tr><td colspan="3"> <span><strong>原始数据报告（自然量）</strong></span><span><br/></span> </td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-installs-report-v5" target="_blank">自然激活</a><br/></span></td><td><span>用于记录用户首次打开应用的情况。<br/></span></td><td><span>持续滚动</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-in-app-events-report-v5" target="_blank">自然应用内事件</a><br/></span></td><td><span>用于记录用户所完成的事件的详细信息。<br/></span></td><td><span>持续滚动</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-uninstall-events-report-v5" target="_blank">自然卸载</a><br/></span></td><td><span>用于记录用户的应用卸载情况。<br/></span></td><td><span>每日更新</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-organic-v5" target="_blank">自然重装激活</a><br/></span></td><td><span>用于记录带量的再营销渠道在再互动窗口期内带来的广告收入。<br/></span></td><td><span>每天更新一次<br/></span></td></tr><tr><td colspan="3"><span><strong>再营销</strong></span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-retarget-v5">转化</a></td><td>用于记录用户与再营销广告交互后打开相关应用的行为。</td><td>实时</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-retarget-v5">应用内事件</a></td><td>用于记录用户在再互动窗口期内完成的应用内事件。</td><td>实时</td></tr><tr><td colspan="3"> <span><strong>广告收入原始数据</strong></span><span><br/></span> </td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5" target="_blank">已归因的广告收入</a><span><br/></span> </td><td>用于记录非自然（由媒体渠道带来的）用户产生的广告收入。</td><td>每日更新</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-organic-raw-v5" target="_blank">自然广告收入</a></td><td>用于记录自然（未归因到任何渠道的）用户产生的广告收入。</td><td>每日更新</td></tr><tr><td colspan="3"><span><strong>Protect360防作弊</strong></span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-installs-report-v5" target="_blank">激活</a></td><td>用于记录系统识别的激活假量，AF不会将这些激活归因到任何媒体渠道。</td><td><span>实时</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-detection-v5" target="_blank">归因后判定为假量的激活</a></td><td>用于记录来自虚假激活的应用内事件，AF不会对这些事件进行归因。</td><td>实时</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-in-app-events-report-v5" target="_blank">应用内事件</a></td><td>用于记录Protect360识别到的应用内事件假量。</td><td>每日更新</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-fraud-post-inapps-v5" target="_blank">归因后识别为假量的应用内事件</a></td><td>用于记录归因到某渠道后被识别为假量的激活所产生的应用内事件，或直接被识别为假量的应用内事件。</td><td>每日更新</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-clicks-report-v5" target="_blank">Clicks</a></td><td>用于记录被Protect360拦截的用户所完成的点击。</td><td>每日更新</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-install-postbacks-v5" target="_blank">已拦截的激活回传</a></td><td>若某渠道带来的激活被拦截，该报告会记录发送到这些渠道的回传。</td><td>实时</td></tr><tr><td colspan="3"><strong>数据回传</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5" target="_blank">激活回传</a></td><td>用于记录用户首次打开应用所形成的激活。</td><td>每日更新</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-postbacks-v5" target="_blank">应用内事件回传</a></td><td>用于记录发送到渠道的应用内事件回传。</td><td>每日更新</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-in-app-events-postbacks-v5" target="_blank">再营销应用内事件回传</a></td><td>用于记录用户在再互动窗口期内完成的应用内事件。</td><td>实时</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-install-postbacks-v5" target="_blank">再营销转化回传</a></td><td>用于记录用户在再互动窗口期内完成的应用内事件。</td><td>实时</td></tr></tbody></table>

<div id="using-pull-api-raw-data" />

<Accordion title="使用Pull API拉取原始数据">

**Pull API原始数据的拉取方式**：

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)获取API token。只有相关账户的管理员才能获取该token。
2. 将该API token发送给您的开发人员，用于认证头（Authentication Header）中。
3. 将下表所列的相关参数发送给您的开发人员，让其在调用API时输入这些参数。这些参数用于界定报告的重点内容、信息梳理方式以及报告覆盖的时间范围。
4. 让您的开发人员按照开发者资源中心的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">Pull API原始数据指南</Anchor>进行操作。

<div id="parameters" />

#### 参数

| 参数 | 说明 |
| --- | --- |
| from | <ul><li>日期范围包含一个`from`和`to`参数，其中的日期指的是用户行为发生的时间。</li><li>格式：`yyyy-mm-dd`、`yyyy-mm-dd hh:mm`或`yyyy-mm-dd hh:mm:ss`**。请注意**：需要对空格进行编码，如：`from=2020-04-01%2001:00:00`。一般情况下，浏览器会对空格进行编码。</li><li>示例：2010-01-01或2010-01-01 20:15（原始数据报告中可以显示小时数和分钟数）。</li></ul> |
| to | 表示截至日期，与`from`相对 |
| media\_source | `media_source`：用于限制对某个具体媒体渠道的调用（即筛选某个具体渠道的数据）。<br /><br />请按以下方式设置`media_source`和`category`这两个参数：<ul><li>如需筛选Meta ads的数据，请将category和media source都设置为*facebook*</li><li>如需筛选X Ads的数据，请将category和media\_source都设置为*twitter*</li><li>如需筛选其他任何媒体渠道的数据，请将category设为*standard*，并将media\_source设为该媒体渠道的名称。</li></ul><ul><li>示例<ul><li>`media_source=facebook&category=facebook`</li><li>`media_source=abc_example&category=standard`</li></ul></li></ul> |
| maximum\_rows | 单次API调用最多可以拉取到的数据行数。<ul><li>【默认】如果不发送该值，则最多返回20万行数据。该字段只支持以下两个值：</li><li>200000：最多可返回20万行数据</li><li>1000000：最多可返回100万行数据</li><li>示例：`maximum_rows=1000000`最多可拉取100万行数据。</li></ul> |
| event\_name | 按指定事件来筛选应用内事件数据。可以选择多个事件，事件之间用逗号分隔。<br /><br />**示例**：`event_name=af_purchase,ftd` |
| reattr | 设置再营销归因数据<ul><li>【默认】如果该参数为false，就会拉取到用户获取（UA）的投放数据。</li><li>如果该参数的值为true，就会拉取再营销归因数据。</li><li>**示例**：`reattr=true`</li></ul> |
| additional\_fields | 用于拉取默认字段之外的数据。<br /><br />**示例**：`additional_fields=device_download_time,deeplink_url` |
| currency | 收入和成本的货币币种<ul><li>【默认】如果不发送该参数，则相关数据以USD显示。也就是说在不配置该参数的情况下，报告中的结果是以美元为单位的。</li><li>如果发送`currency=preferred`，相关数据会以<Anchor target="_blank" href="/marketers/zh/docs/app-settings#localization-time-zone">应用层级</Anchor>的指定货币来显示。 也就是说报告中的货币单位与应用层级的指定货币相同。</li></ul>**示例**：如果应用层级的指定货币是EUR（欧元），发送`currency=preferred`后就可拉取以EUR为单位的值。 |
| timezone | 【默认】数据以UTC时间显示。<ul><li>如果要让报告按<Anchor target="_blank" href="/marketers/zh/docs/app-settings#localization-time-zone">应用层级的</Anchor>指定时区来显示相关数据，请按以下方式在调用中添加`timezone`这个参数：</li></ul><ul><li>`timezone=[Numerical value]`</li><li>示例：假设您要使用的时区为UTC+10:00，则需要发送`timezone=+10:00`**。请注意**：`+`、`-`和`:`这几个符号需要加密。例如：+10:00需加密为`%2B10%3A00`</li></ul> |
| geo | 按国家代码筛选数据<br /><br />局限性：每次调用API时只能设置一个国家代码。<br /><br />示例：`geo=ZA` |
| from\_install time | <ul><li>日期范围包含一个`from`和`to`参数，其中的日期指的是用户行为发生的时间。</li><li>格式：`yyyy-mm-dd`</li><li>示例：2010-01-01</li></ul> |
| to\_install\_time | 表示截至日期，与`from_install time`相对 |
| agency | 用于筛选出某个具体代理的数据。 |

</Accordion>

<div id="protect360-fields" />

<Accordion title="Protect360字段">

<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports#postattribution-reports">详情请见Protect360原始数据指南</Anchor>

</Accordion>

<div id="time-frame-fields" />

<Accordion title="时间范围字段">

如果API返回的结果超过行数上限，请通过小时数和分钟数来拆分报告。具体方法如下：

* **from**/**to**参数的格式为：**yyyy-mm-dd hh:mm**
* **from：** 
  * 如果参数仅包含日期 = 从选定日期的零时（00:00）开始
  * 如果同时包含日期和时间 = 从选定时间（含）开始
* 参数**to**：
  * 如果参数仅包含日期 = 到选定日期结束（24:00）为止
  * 如果同时包含日期和时间 = 到选定时间（不含）为止

**示例：** 各渠道每天共为某广告主带来130万个新增激活。为克服100万行的限制，该广告主分两次调用API，每次拉取12小时的数据。具体方案请见下表：

<table><tbody><tr><th>API调用</th><th>From </th><th>To </th></tr><tr><td><strong>首次API调用</strong></td><td><p><span><strong>from</strong>=yyyy-mm-dd</span></p><p><span><strong>示例：</strong></span></p><ul><li><span><strong>from</strong>=<code>2019-12-29</code></span></li><li><span>从这一天的00:00开始</span></li></ul></td><td><p><span><strong>to</strong>=yyy</span><span>y-mm-dd 12:00</span></p><p><strong>示例：</strong></p><ul><li><span><strong>to</strong>=<code>2019-12-29 12:00</code></span></li><li> <span>到11:59:59结束，不包含12:00</span><span> </span> </li></ul></td></tr><tr><td><p><strong>方案A：</strong> <strong>第二次API调用</strong> </p><p><span><strong>示例</strong></span><span>：</span></p><p><span><strong><kbd><code><kbd>&amp;from=2019-12-29 12:00&amp;to=2019-12-29</kbd></code></kbd></strong></span></p><ul><li><span>从2019年12月29日中午开始</span></li><li><span>到2019年12月29日凌晨结束</span></li></ul></td><td> <p><span><strong>from</strong>=yyyy-mm-dd 12:00</span></p><p><strong>示例：</strong></p><ul><li> <strong>from</strong>=<span><code>2019-12-29 12:00</code></span> </li><li><span>从12:00开始，包含12:00</span></li></ul></td><td><p><span> </span></p><p><span><strong>to</strong>=yyy</span><span>y-mm-dd </span></p><p><span><strong>示例：</strong></span></p><ul><li><span><strong>to</strong>=<code>2019-12-29</code></span></li><li><span>到凌晨结束</span></li></ul><p><span> </span></p></td></tr><tr><td><strong>方案B：第二次API调用</strong></td><td><p><span><strong>from</strong>=yyyy-mm-dd 12:00</span></p><p><strong>示例：</strong></p><ul><li> <strong>from</strong>=<span><code>2019-12-29 12:00</code></span> </li><li><span>从12:00开始，包含12:00</span></li></ul></td><td><p><span><strong>to</strong>=yyyy-mm-dd+1 00:00</span></p><p><span><strong>+1</strong> = 第二天的00:00</span></p><p><strong>示例：</strong></p><ul><li><span><strong>to=<code>2019-12-30 00:00</code></strong></span></li><li>表示在12月30日开始之前。</li></ul></td></tr><tr><td colspan="3"><p><span><strong>请注意：方案A和方案B拉取到的结果是一样的。</strong></span></p></td></tr></tbody></table>

</Accordion>

<div id="additional-fields" />

<Accordion title="可选的非默认字段">

额外添加的非默认字段不会影响您的数据入库和上传流程。您可以使用`additional_fields`这个参数来拉取非默认字段的值。

* 这个参数在每个URI中只能出现一次。
* 可用字段请见<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">此列表</Anchor>。
* 示例：`additional_fields=device_download_time,deeplink_url`

</Accordion>

<div id="default-fields" />

<Accordion title="默认字段">

| Pull API默认字段 |
| --- |
| Attributed Touch Type（归因到的广告触达类型） |
| Attributed Touch Time（归因到的广告触达时间） |
| Install Time（激活时间） |
| Event Time（事件时间） |
| Event Name（事件名称） |
| Event Value（事件值） |
| Event Revenue（事件收入） |
| Event Revenue Currency（事件收入货币） |
| Event Revenue USD（以美元为单位的事件收入） |
| Event Source（事件来源） |
| Is Receipt Validated（收入验证） |
| Partner（合作代理） |
| Media Source（媒体渠道） |
| Channel（流量入口） |
| Keywords（关键词） |
| Campaign（广告系列） |
| Campaign ID（广告系列ID） |
| Adset（广告组） |
| Adset ID（广告组ID） |
| Ad（广告） |
| Ad ID（广告ID） |
| Ad Type（广告类型） |
| Site ID（子渠道ID） |
| Sub Site ID（次级子渠道ID） |
| Sub Param 1（可配置参数1） |
| Sub Param 2（可配置参数2） |
| Sub Param 3（可配置参数3） |
| Sub Param 4（可配置参数4） |
| Sub Param 5（可配置参数5） |
| Cost Model（计费模式） |
| Cost Value（成本值） |
| Cost Currency（成本货币） |
| Contributor 1 Partner（助攻1合作代理） |
| Contributor 1 Media Source（助攻1媒体渠道） |
| Contributor 1 Campaign（助攻1广告系列） |
| Contributor 1 Touch Type（助攻1触达类型） |
| Contributor 1 Touch Time（助攻1触达时间） |
| Contributor 2 Partner（助攻2合作代理） |
| Contributor 2 Media Source（助攻2媒体渠道） |
| Contributor 2 Campaign（助攻2广告系列） |
| Contributor 2 Touch Type（助攻2触达类型） |
| Contributor 2 Touch Time（助攻2触达时间） |
| Contributor 3 Partner（助攻3合作代理） |
| Contributor 3 Media Source（助攻3媒体渠道） |
| Contributor 3 Campaign（助攻3广告系列） |
| Contributor 3 Touch Type（助攻3触达类型） |
| Contributor 3 Touch Time（助攻3触达时间） |
| Region（地区） |
| Country Code（国家代码） |
| State（州） |
| City（城市） |
| Postal Code（邮政编码） |
| DMA（指定市场区域） |
| IP |
| WIFI |
| Operator（移动服务商） |
| Carrier（网络运营商） |
| Language（语言） |
| AppsFlyer ID |
| Advertising ID |
| IDFA |
| Android ID |
| Customer User ID（客户用户ID） |
| IMEI |
| IDFV |
| Platform（系统平台） |
| Device Type（设备类型） |
| OS Version（操作系统版本） |
| App Version（应用版本） |
| SDK Version（SDK版本） |
| App ID（应用ID） |
| App Name（应用名称） |
| Bundle ID |
| Is Retargeting（是否为再营销广告） |
| Retargeting Conversion Type（再营销转化类型） |
| Attribution Lookback（归因回溯窗口期） |
| Reengagement Window（再互动窗口期） |
| Is Primary Attribution（是否为主要带量渠道） |
| User Agent（用户代理） |
| HTTP Referrer |
| Original URL |

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 注意事项 |
| --- | --- |
| 规定的API密钥类型 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">V2.0 token</Anchor> |
| 渠道权限 | 否 |
| 代理访问权限 | 是 |
| 代理数据透明化 | 区分。但如果您同时使用“代理”和“媒体渠道”这两个筛选条件，“媒体渠道”这个筛选条件不会对数据不透明的代理生效。也就是说报告中会包含所有不透明代理的数据，而不仅仅是按媒体渠道筛选出来的数据。 |
| 应用配置中的指定货币 | 是 |
| 应用层级指定时区 | 是 |
| 数据时效性 | <ul><li>与数据总览面板的时效性一致。</li><li>报告更新会有数小时的延迟：<ul><li>自然应用内事件</li></ul></li><li>每日更新一次的报告包括：<ul><li>卸载</li><li>归因后识别为假量的应用内事件</li><li>广告收入</li></ul></li></ul> |
| 历史数据 | 区分。  须遵循<Anchor target="_blank" href="/marketers/zh/docs/user-level-data-retention">数据保存期限</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/report-generation-quotas-rate-limitations">频次限制</Anchor>规定。 |
| 非自然量数据 | 是 |
| 自然量数据 | 是 |
| 拉取频次限制 | <Anchor target="_blank" href="/marketers/zh/docs/report-generation-quotas-rate-limitations">原始数据</Anchor>的API调用限制 |
| 大小限制 | <ul><li>调用API后最多可拉取20万/100万行数据。</li><li>如果报告中的数据条数正好是20万/100万条，基本可以判定数据有缺失。</li><li>您可以使用maximum\_rows参数来选择报告所含的数据行数上限。</li><li>出现这种情况时，请进行多次调用，每次在from/to时间范围中指定某一天的具体时间。</li></ul> |
| Install\_date\_from和install\_date\_to | 激活日期范围必须早于用户行为日期范围。 |

</Accordion>

<div id="troubleshooting" />

<Accordion title="问题排查">

| 问题表现/报错消息 | 解决方法 |
| --- | --- |
| 所选时间段中有数据缺失，或原始数据和汇总数据报告之间有数据差异。 | 请检查`timezone`时区参数是否已配置。如果未配置该参数，则数据会以UTC时间发送，而非应用层级的指定时区。 |

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">如何选择合适的数据传输工具/报告API</Anchor>

<div data-zendesk-anchors="pull-api-raw-data=pull-api%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01HE7S6WDVJD2XFW498P8FPY7W=pull-api%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A aggregate-performance-reports-available-via-pull-api=pull-api%E8%83%BD%E5%A4%9F%E6%8B%89%E5%8F%96%E5%88%B0%E7%9A%84%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01HE7S6WDV59VTP6Z4X790QDRD=pull-api%E8%83%BD%E5%A4%9F%E6%8B%89%E5%8F%96%E5%88%B0%E7%9A%84%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01HE7S6WDVYJ5MAK04VWB4MF6A=using-pull-api-raw-data parameters=%E5%8F%82%E6%95%B0 h_01HE7S6WDVF8T4719HWDJH8JN1=%E5%8F%82%E6%95%B0 h_01HE7S6WDVGSS0F116ZB6QVG1N=protect360-fields h_01HE7S6WDVP47A3Q8J7NPH54T5=time-frame-fields h_01HE7S6WDWZ8FR6GRJ40B4CJAV=additional-fields h_01HE7S6WDWMXYF0RHYPF058A9K=default-fields additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HE7S6WDW9V8XC3CJ0F96EHN0=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HE7S6WDWV87YVJMN76STX7A1=traits-and-limitations h_01HE7S6WDWMZPPTR41VHJQ8MWC=troubleshooting h_01HE7S8S8QCSKRA62A2HVK2MYJ=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

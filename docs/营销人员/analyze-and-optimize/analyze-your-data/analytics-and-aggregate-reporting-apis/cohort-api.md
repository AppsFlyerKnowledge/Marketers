---
title: Cohort API
metadata:
  keywords:
    - API
    - Advertisers
    - Partners
    - Developer
    - Premium
    - Gray
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2020-01-14T07:04:32Z'
  edited_at: '2026-10-14T10:11:41Z'
  id: 360004799057
  locale: zh-cn
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/zh-cn/articles/360004799057
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 广告主可以利用Cohort API以程序化的方式来获取群组数据，并将群组数据接入内部BI以及自动化营销系统中。

## Cohort API

Cohort API旨在帮助广告主从AppsFlyer平台获取不同用户群组的投放效果数据，其功能相当于<Anchor target="_blank" href="/marketers/zh/docs/cohort-and-retention-dashboard">群组面板</Anchor>。

如需使用群组和留存面板，您必须先界定您要查看的数据，即选择某个特定应用的用户，并将其按转化时间分组。可用的群组指标包括收入、ROI和事件转化率等。您可以将相关用户群组按广告系列或媒体渠道等维度进行拆分，以便对比分析。调用Cohort API后，会返回CSV或JSON格式的文件。您可以使用这些数据，考察用户或广告生命周期内的投放效果规律或变化。

详情请见<Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">群组功能的使用场景</Anchor>。

**Cohort API的使用方式如下**：

1. ![](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) alt<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">AppsFlyerAdmin\_us-en.png</Anchor>获取API token。只有账户管理员才能获取该token。
2. 将该API token发送给您的开发人员，用于认证头（Authentication Header）中。
3. 将下表所列的相关[参数](#filtering-and-grouping-parameters)发送给您的开发人员，让其在调用API时输入这些参数。这些参数用于界定报告的重点内容、信息梳理方式以及报告覆盖的时间范围。
4. 让您的开发人员按照开发者资源中心的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_app-id">Cohort API使用指南</Anchor>进行操作。

<div id="filtering-and-grouping-parameters" />

<Accordion title="Cohort API的参数">

您可以使用下列参数获取您需要的数据。

| 参数名称 | 说明 | 必须配置 |
| --- | --- | --- |
| <span id="bearer"></span>bearer | 在API验证头（authentication header）中使用的API token。 | 是 |
| <span id="cohort-_type"></span>cohort \_type | 可能出现的群组归因（转化）类型为：`user_acquisition` user\_acquisition`retargeting``unified`（新用户获取）、（再营销）、retargeting（统一）<ul><li>Unified（统一）指同时包含拉新广告和再营销广告的投放效果数据。</li><li>如果一个事件同时被归因到再营销和拉新广告，则返回的KPI中仅包含再营销事件，即is_primary=true。</li><li>格式：字符串</li><li>例如： `"cohort_type": "user_acquisition"`</li></ul> | 是 |
| <span id="min_cohort_size"></span>min\_cohort\_size | 群组体量下限可排除用户数量较少的群组，从而减少返回的数据条数。 也就是说用户KPI的值不小于您指定的群组体量下限。<ul><li>格式：整数</li><li>允许发送的最小值:1. 请勿发送零值（0）</li><li>默认1</li><li>例如： `"min_cohort_size": 50`</li></ul> | 否 |
| <span id="from"></span>from | 用于指定日期范围中的起始日期（LTV维度）最早可设为当前日期之前的720天。<ul><li>格式：格式为yyyy-mm-dd的字符串</li><li>示例：`"from": "2020-01-02"`</li></ul> | 是 |
| <span id="to"></span>to | LTV归因日期范围的截止日期<ul><li>日期范围内可包含的天数：1-31天</li><li>如需查看单天数据：请将`from`和`to`设为同一个值。</li><li>格式：yyyy-mm-dd</li><li>示例：`"from": "2020-01-01", "to": 2020-01-31`，即为31天。</li></ul> | 是 |
| <span id="granularity"></span>granularity | 过去72小时的数据颗粒度可精确到小时数。如需查看精确到小时数的数据，请发送`"granularity": "hour"`，并在`from`和`to`的日期范围内设置具体时间值。<ul><li>格式：yyyy-mm-dd hh:mm:ss</li><li>举例来说，</li></ul>`"granularity": "hour", "from": "2021-12-01 14:00:00", "to": "2021-12-03 11:00:00",` | 否 |
| <span id="partial_data"></span>partial\_data | 为了避免数据失真和误判，群组报告会返回天数完整的数据。但广告主有时可能需要查看天数不完整的数据。<br /><br />针对某个查询的同类群组完整天数 = 当前日期 - *to*日期。<ul><li>【默认】如果为false，则返回天数完整的数据。</li><li>如果为true，则最多返回同类群组180天的数据，包括不完整数据。</li><li>格式：布尔</li><li>AF面板：false（即仅显示天数完整的数据）</li></ul>**示例**:假设4月1日到30日之间转化的用户为一个群组，到5月10日，该群组的完整天数为10天。<ul><li>如果没有设置，则【默认】返回群组第0-9天的数据，即从最后一个转化日期到当前日期的天数（10）。</li><li>如果设置为true，则返回群组第1-40天的数据。群组第11-40天包含不完整数据，因此不会返回这部分数据。以4月20日为例，由于自该日期以来仅过去了20天，因此数据不完整。其他日期以此类推。</li></ul>**请注意**：仅在汇总类型为“累计”时才能拉取不完整数据。 | 否 |
| <span id="filters"></span>filters | 您可以按归因后天数及其他条件对返回的数据进行筛选。 可用的筛选条件请见[筛选维度列表](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions)。<ul><li>格式：多层嵌套JSON中的字符串，必须以数组的形式发送相关值。</li><li>**按Geo（国家/地区）筛选示例：**`"filters": {"geo": ["US"]}`表示仅包含归因到美国的用户。"filters":></li><li>**群组维度的period示例：`period`（归因后天数）用于界定报告返回哪几天的衡量数据。可用的值为：0-180。21**</li><li>默认如果不设置period筛选条件，则返回群组第0-30天、60天、90天和180天的数据。 [period筛选条件使用示例。](/docs/cohort-api#using-period-filters)</li></ul> | 否 |
| <span id="groupings"></span>groupings | <ul><li>您可以使用分组参数在报告中添加列，帮助您更为宏观地了解数据。</li><li>从[分组维度列表](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions)中选择1-7个值。</li><li>格式：以数组形式组成的字符串</li><li>示例：`"groupings": ["af_ad", "c", "af_c_id", "af_prt"]`</li></ul> | 是 |
| <span id="kpis"></span>kpis | KPI可以说明您应用的使用情况，帮助您提炼用户行为中的关键信息。详情请见[KPI的选择方式和格式设置说明](/docs/cohort-api#selecting-and-formatting-kpis) | 是 |
| <span id="preferred_currency"></span>preferred\_currency | 该参数用于设置返回的KPI格式。详情请见[KPI格式设置说明](/docs/cohort-api#设置kpi函数的格式) | 否 |
| <span id="preferred_timezone"></span>preferred\_timezone | 该参数用于设置返回的KPI格式。详情请见[KPI格式设置说明](/docs/cohort-api#设置kpi函数的格式) | 否 |
| <span id="aggregation_type"></span>aggregation\_type | 该参数用于设置返回的KPI格式。详情请见[KPI格式设置说明](/docs/cohort-api#设置kpi函数的格式) | 是 |
| <span id="per_user"></span>per\_user | 该参数用于设置返回的KPI格式。详情请见[KPI格式设置说明](/docs/cohort-api#设置kpi函数的格式) | 否 |

</Accordion>

<div id="selecting-and-formatting-kpis" />

<Accordion title="选择KPI并调整格式">

* 下表列出了可用的KPI以及各KPI对应的函数，调用某个KPI时会返回其对应的所有函数。
* 拉取报告时默认包含的KPI为：users（用户）、ecpi（有效平均激活成本）以及cost（成本）。
* 每次调用仅限发送一个可选KPI。
* 调用任一个KPI都会返回其对应的对应函数。
* 格式：以数组形式组成的字符串
  * 示例A：
  * 示例B：

<table><thead><tr><th> </th><th> </th><th colspan="5">功能</th></tr><tr><th rowspan="2">默认/可选 </th><th rowspan="2">KPI（维度名称） </th><th>数量</th><th>cvr（转化率）</th><th>Rate</th><th>总和</th><th>独立用户数</th></tr><tr><th>数字</th><th>百分比</th><th>百分比</th><th>数字</th><th>数字</th></tr></thead><tbody><tr><td>默认</td><td>users</td><td><span>Y</span></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>默认</td><td>ecpi</td><td>-</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>默认</td><td>cost</td><td>-</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>可选</td><td> <code>"event_name"</code>(4) </td><td><span>Y</span></td><td><span>Y</span></td><td>-</td><td><span>Y (3)</span></td><td><span>Y</span></td></tr><tr><td>可选</td><td>revenue</td><td><span>Y</span></td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>可选</td><td>roas</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>可选</td><td>roi</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>可选</td><td>sessions</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td><span>Y(1)</span></td></tr><tr><td>可选</td><td>uninstalls (2)</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td colspan="7"><p>(1) <em>aggregation_type=on_day</em> 时返回独立session（应用打开）数据。</p><p>(2) cohort_type=unified时不可用。 </p><p>(3) 这里的总和是指定事件产生的收入总和，在报告中显示为<code>sum_event_name"</code>sum_event_name"</p><p>(4) 请注意：事件名称区分大小写。</p></td></tr></tbody></table>

<div id="formatting-kpi-functions" />

#### 设置KPI函数的格式

您可以使用下列参数设置报告中的KPI格式。

| 参数 | 值 | 必须配置 |
| --- | --- | --- |
| preferred\_currency | KPI收入的货币单位<ul><li>如果为true，则报告以<Anchor target="_blank" href="/marketers/zh/docs/app-settings#localization-currency">应用层级的指定货币</Anchor>（在AF后台设置）为单位显示收入。</li><li>【默认】如果为false，则报告以美元为单位显示收入。</li><li>格式：布尔</li><li>AF面板：true</li></ul> | 否 |
| preferred\_timezone | **日期范围的时区**<ul><li>如果为true，则报告以<Anchor target="_blank" href="/marketers/zh/docs/app-settings#localization-time-zone">应用层级的指定时区</Anchor>（在AF后台设置）显示时间。</li><li>【默认】如果为false，则报告以UTC时区显示时间。</li><li>格式：布尔</li><li>AF面板：true</li></ul> | 否 |
| aggregation\_type | <ul><li>`cumulative`</li><li>`on_day`</li></ul>`"aggregation_type": "cumulative"`<br /><br />`Format: String` | 是 |
| per\_user | 由KPI值除以用户数得出。仅适用于相关KPI。<ul><li>如为true，则将KPI值除以该群组中的用户数。</li><li>如为false，则不相除。</li><li>格式：布尔</li><li>参数值为true的示例：假设总收入为$1000，用户数为500，则返回的值为$2。</li></ul> | 否 |

</Accordion>

<div id="list-of-group-by-and-filter-by-dimensions" />

<Accordion title="分组及筛选维度列表">

<table><thead><tr><th>维度名称 </th><th>对应的API参数</th><th>分组</th><th>筛选条件</th></tr></thead><tbody><tr><td>Ad</td><td>af_ad</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>即相关广告的ID</td><td>af_ad_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Campaign</td><td>c</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>即广告系列的ID</td><td>af_c_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>流量入口（Channel）</td><td>af_channel</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Media Source（媒体渠道）</td><td>pid</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Sub Param 1（可配置参数1）</td><td>af_sub1</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Keywords（关键词）</td><td>af_keywords</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>代理</td><td>af_prt</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Conversion Type（转化类型，见脚注1） </td><td>cohort _type</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Site ID</td><td>site_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Revenue Type（收入类型，见脚注2）</td><td>revenue_type</td><td><span>x </span></td><td><span>Y</span></td></tr><tr><td>Attributed Touch Type（归因到的触点类型，见脚注3）</td><td>attributed_touch_type</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Adset</td><td>af_adset</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>即广告组的ID</td><td>af_adset_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Country（国家）</td><td>geo</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Date（基于选定的cohort_type所定义的激活/再归因/再互动日期） </td><td>date</td><td><span>Y</span></td><td><span>x </span></td></tr><tr><td>Period（归因后天数）</td><td><p>period</p><p><a href="./cohort-api#using-period-filters">详细说明</a></p></td><td><span>X</span></td><td><span>Y</span></td></tr><tr><td colspan="4"><p>请注意： </p><p>可选维度：</p><p>(1) Conversion Type（转化类型）：<code>user_acquisition</code><code>retargeting</code>（用户获取）、<code>re-engagement</code>（再营销，包括<code>re-attribution</code>和<code>unified</code>，即再互动和再归因）、user_acquisition（统一）</p><ul><li>导出数据时：<ul><li> <code>re-engagement</code><code>retargeting</code>会显示为re-engagement </li><li> <code>re-attribution</code><code>reattr</code>会显示为re-attribution </li></ul></li></ul><p>(2) 收入类型（Revenue Type）：<code>regular</code>、<code>ad_monetization</code><span></span></p><p>(3) Attributed Touch Type（归因到的触点类型）：<code>click</code>、<code>impression</code>、<code>TV</code>、<code>pre-installed</code></p></td></tr></tbody></table>

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="using-period-filters" />

<Accordion title="period（归因后天数）筛选条件使用方式">

Period是指归因后的天数，period 0即为归因当天（归因日）。假设某用户在1月1日激活应用，1月1日则为归因日。在period 0发生的购买事件即为用户在1月1日完成的购买；在period 3发生的购买事件即为用户在1月4日完成的购买；同理，对于在1月11日激活的用户，1月11日即为period 0，其在1月14日完成的购买即为period 3的购买事件。

如果您的报告日期范围设置为1月1日至1月11日，则返回的数据仅限在这段时间内归因（激活）的用户，而不包含其他数据。

* period可以是0-180之间的一个或多个值，如0、1、2、30、180。
* 如果没有指定period，则报告会根据默认值0、1、2到30、60、90和180返回数据。

<div id="example-period-filter" />

> 📄 **period筛选条件使用示例**
>
> * 该示例包含JSON查询参数、原始数据以及返回的CSV文件。
> * 查询*筛选period* 0、1和2，并选择*revenue*（收入）为KPI。
> * 该条查询命令将数据汇总类型（aggregation type）指定为“cumulative”（累计）如需获取当日数据，请将汇总类型改为“on\_day”。
> * 返回的数据包含：
>   * 总是返回用户、成本和ecpi数据
>   * 收入数据，包括收入总和以及每个period（即period 0、1和2）的收入。
>
> **查询语句**
>
> ```json
> {
>     "cohort_type": "user_acquisition",
>     "min_cohort_size": 1,
>     "preferred_timezone": false,
>     "from": "2019-12-01",
>     "to": "2020-01-01",
>     "filters": {
>         "period": [
>             0,
>             1,
>             2
>         ]
>     },
>     "aggregation_type": "cumulative",
>     "per_user": false,
>     "groupings": [
>         "pid"
>     ],
>     "kpis": [
>         "revenue"
>     ]
> }
> ```
>
> **原始数据**
>
> **![mceclip1.png](https://files.readme.io/846aade481d3b5fa72536817533bc3edad721f1ce6015edcb48bd500461342b9-32131110606865.png)**
>
> **结果**
>
> ![mceclip0.png](https://files.readme.io/c284e5133e4e811b9416c850e399ddefb3c5bfcfcf879f469556b7a6bc0062c6-32131110607249.png)

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 渠道权限 | 否 |
| 代理访问权限 | 否 |
| 代理数据透明化 | 不支持。对于通过代理带来的流量，其媒体渠道总是显示为相关代理的名称，而非实际带量渠道的名称。 |
| 应用层级的指定时区 | 是 |
| 应用配置中的指定货币 | 是 |
| 大小限制 | 无 |
| 拉取频次限制 | <ul><li>API调用频次限制：每个账户下每分钟最多60次，每天最多5万次</li><li>调用后最多返回3万行数据。</li></ul> |
| 自然量数据 | 可用 |
| 非自然量数据 | 可用 |
| 成本数据局限性 | <ul><li>只有带来过激活的广告系列才会有成本数据。</li><li>AppsFlyer的群组报告或Cohort API不上报包含大写字母的关键词成本数据。</li><li>成本指标不能与某些分组维度相结合。如FMeta ads的数据可以按Geo（国家/地区）或Channel（流量入口）分组，但不能同时结合这两个维度进行分组。具体的可用分组维度组合取决于广告平台。</li></ul> |
| 数据时效性 | 数据时效性取决于[partial\_data](/docs/cohort-api#partial_data)的值，具体如下：<ul><li>【默认】false，<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#daily-processing">每天更新一次</Anchor></li><li>如果为true，则<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">持续滚动更新（实时）</Anchor></li><li>成本和卸载指标在任何情况下都是每天更新一次</li></ul> |
| 历史数据 | 日度群组数据：2年。 |
| 相关账户下的用户权限 | AF账户管理员可在面板中查看身份验证token |
| 广告收入 | 出现以下情况时，af\_ad\_revenue事件的独立用户指标不可用不可用：<ul><li>汇总类型设置为“cumulative”（累计）时。</li><li>汇总类型设置为“on day”（当天）时，2022年10月5日到2023年2月16日之间的独立用户指标不可用。</li></ul> |
| 按周和按月分组 | Cohort API不支持按周或按月分组。如需查看这两个维度的数据，请使用群组面板。 |
| Cohort API的周期 | <ul><li>转化发生的当前周期为第0期，如第0个小时（Hour 0）或第0天（Day 0）；下一个周期即为第1期，如第1个小时（Hour 1）或第1天（Day 1），以此类推。</li><li>AppsFlyer平台中的群组周期不考虑具体的激活时间戳，而是对群组小时数就近取整，群组天数以公历日期为准。对于根据具体激活时间戳判定群组周期（1小时为激活时间戳后的60分钟，1天为激活时间戳后的24小时）的平台，这一逻辑可能会使其群组数据与AppsFlyer之间产生一定差异。</li></ul> |
| 日期 | <ul><li>这里的日期或日期范围是指生命周期价值（LTV）维度的日期，即用户被归因（激活转化）的日期，而不是具体用户行为发生的日期。</li><li>最多可查看当前日期之前730天（即2年）内的数据</li><li>查询范围上限为60天。</li></ul> |
| 重装激活 | <ul><li>如果重装激活发生后的事件被记录为未归因的自然量：<ul><li>2024年5月26日之后的报告不呈现该数据。<Anchor target="_blank" href="/marketers/zh/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">详情请见此处说明。</Anchor></li><li>激活时间以<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>字段的值为准。</li><li>不计入独立用户数和留存指标。</li></ul></li><li>如果重装激活后发生的事件被归因到首次激活，则报告中总是包含该数据。<Anchor target="_blank" href="/marketers/zh/docs/unique-users">详情请见此处说明。</Anchor></li></ul> |
| 渠道的Cohort API权限 | 营销渠道的Cohort API权限于2024年9月15日关闭。建议渠道<Anchor target="_blank" href="/partners/zh/docs/data-locker-reports-for-api-partners">使用Data Locker</Anchor>，该工具可确保其持续访问客户的数据。 |

</Accordion>

<div data-zendesk-anchors="cohort-reporting-api=cohort-api 01H7WFZR41YAQX4MFPBMJD1MBP=cohort-api 01H7WFZR42H3CA0CSB4E3XED3H=filtering-and-grouping-parameters 01H7WFZR42XV4JY46GY11KT3CF=selecting-and-formatting-kpis presentation-of-kpi-functions=%E8%AE%BE%E7%BD%AEkpi%E5%87%BD%E6%95%B0%E7%9A%84%E6%A0%BC%E5%BC%8F 01H7WFZR43HFF65TSWG1AN0JTB=%E8%AE%BE%E7%BD%AEkpi%E5%87%BD%E6%95%B0%E7%9A%84%E6%A0%BC%E5%BC%8F 01H7WFZR43BJ8E6KVHSGV4CDDP=list-of-group-by-and-filter-by-dimensions additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HMY09W324E54VPZWPJVS2KB8=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H7WFZR440NTXWWQ2T4P2ANWK=using-period-filters 01H7WFZR44RCXA56CXSCEZ0KXH=period%E7%AD%9B%E9%80%89%E6%9D%A1%E4%BB%B6%E4%BD%BF%E7%94%A8%E7%A4%BA%E4%BE%8B 01H7WFZR45VC96KYW1W9A8PBFT=traits-and-limitations" />

---
title: Master API — 通过API获取拉新指标
metadata:
  keywords:
    - Master API
    - Customizable
    - Aggregated Data
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-09-27T15:10:38Z'
  edited_at: '2026-10-14T10:15:27Z'
  id: 213223166
  locale: zh-cn
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/zh-cn/articles/213223166
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 通过该API获取指定的LTV、活跃、群组、Protect360、和留存等维度的投放效果指标（CSV或JSON格式）。选择一个或多个应用。

<div id="master-apiuser-acquisition-metrics-via-api" />

## Master API — 通过API获取拉新指标

Master API：

* 您可以获取指定的LTV、活跃、群组、Protect360和留存等维度的投放效果指标。可用KPI与数据总览、活跃、留存、群组和Protect360面板中的KPI一致。
* 每天计算一次。您可在更新后的24-48小时内拉取到新数据，具体取决于您应用配置中的指定时区。
* 以AppsFlyer<Anchor target="_blank" href="/marketers/zh/docs/pivot-table-user-metrics">数据透视表</Anchor>的结构为基础

使用Master API时，请定义您需要拉取的数据（这与<Anchor target="_blank" href="/marketers/zh/docs/pull-api-aggregate-data">Pull API</Anchor>的使用方式很相似），调用Cohort API后，会返回CSV或JSON格式的文件。

**请按以下方式使用Master API**：

1. ![](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) alt<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">AppsFlyerAdmin\_us-en.png</Anchor>获取API token。只有账户管理员才能获取该token。
2. 将该API token发送给您的开发人员，用于认证头（Authentication Header）中。
3. 将下表所列的相关参数发送给您的开发人员，让其在调用API时输入这些参数。这些参数用于界定报告的重点内容、信息梳理方式以及报告覆盖的时间范围。
4. 让您的开发人员按照开发者资源中心的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-9">Master API使用指南</Anchor>进行操作。
5.
   <div id="api-parameters" />

   <Accordion title="API参数">

   | 参数 | 参数值 | 必须配置 |
   | --- | --- | --- |
   | app\_id | * 即AppsFlyer后台显示的应用ID。<br />* 请将此应用ID复制粘贴到路径中。<br />* **对于iOS应用，请添加前缀**id<br />* 如需查询所有应用的数据，请使用**all app IDs**作为参数值 | 是 |
   | from | 用于指定日期范围中的起始日期（LTV维度）<br /><br />* 格式：格式为yyyy-mm-dd的字符串<br />* 示例：`from: 2020-01-02` | 是 |
   | to | 用于指定日期范围中的截止日期（LTV维度）<br /><br />* 日期范围内可包含的天数：1-31天<br />* 如需查看单天数据：请将`from`和`to`设为同一个值。<br />* 格式：yyyy-mm-dd<br />* 示例：`from: 2021-01-01, to: 2021-01-31`，即为31天。 | 是 |
   | [分组](/docs/master-api-user-acquisition-metrics-via-api#groupings) | 用于将数据按参数分组，以逗号区隔。可用参数请见下一节中的分组维度表。<br /><br />例如： `groupings=pid,geo` | 是 |
   | [KPI](/docs/master-api-user-acquisition-metrics-via-api#kpis) | 用于配置您想要拉取的KPI，各KPI之间以逗号区隔。可用的KPI列表请见后文表格。<br /><br />示例：`kpis=installs,clicks, impressions,sessions,retention_day_7` | 是 |
   | [筛选条件](/docs/master-api-user-acquisition-metrics-via-api#filters-optional) | 您可以使用一个或多个筛选条件来筛选数据。 | 否 |
   | [货币](/docs/master-api-user-acquisition-metrics-via-api#localization) | 如需按应用配置中的指定货币拉取数据，请将该参数设置为currency=preferred | 否 |
   | [时区](/docs/master-api-user-acquisition-metrics-via-api#localization) | 如需按应用配置中的指定时区拉取数据，请将该参数设置为timezone=preferred。  详情请见[数据本地化规则](/docs/master-api-user-acquisition-metrics-via-api#localization) | 否 |
   | 格式 |  | 否 |

   </Accordion>

   <div id="groupings" />

   <Accordion title="分组">

   您可以使用以下维度对收集到的数据进行分组，以便更快捷准确地分析相关信息。这些字段的详细说明请见<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">此文档</Anchor>。

   <table><thead><tr><th>分组维度<br/>API 名称</th><th>分组维度的显示名称</th><th>LTV KPI</th><th>留存KPI</th><th>活跃KPI</th><th>Protect360</th><th>群组</th></tr></thead><tbody><tr><td>app_id</td><td>App ID（应用ID）</td><td>是</td><td>是</td><td>是</td><td>是</td><td>是</td></tr><tr><td>pid</td><td>媒体渠道</td><td>是</td><td>是</td><td>是</td><td>是</td><td>是</td></tr><tr><td>af_prt</td><td>代理</td><td>是</td><td>是</td><td>是</td><td>是</td><td>否</td></tr><tr><td>c</td><td>Campaign</td><td>是</td><td>是</td><td>是</td><td>是</td><td>是</td></tr><tr><td>af_adset</td><td>Adset</td><td>是</td><td>是</td><td>是</td><td>否</td><td>否</td></tr><tr><td>af_ad</td><td>Ad</td><td>是</td><td>是</td><td>是</td><td>否</td><td>否</td></tr><tr><td>af_channel</td><td>流量入口（Channel）</td><td>是</td><td>是</td><td>是</td><td>是</td><td>否</td></tr><tr><td>af_siteid</td><td>Publisher ID（子渠道ID）</td><td>是</td><td>是</td><td>是</td><td>是</td><td>是</td></tr><tr><td>af_keywords</td><td>Keywords（关键词）</td><td>是</td><td>是</td><td>是</td><td>否</td><td>否</td></tr><tr><td>is_primary</td><td>Is primary attribution</td><td>是</td><td>否</td><td>是</td><td>是</td><td>否</td></tr><tr><td>af_c_id</td><td>即广告系列的ID</td><td>是</td><td>否</td><td>是</td><td>是</td><td>否</td></tr><tr><td>af_adset_id</td><td>即广告组的ID</td><td>是</td><td>否</td><td>是</td><td>否</td><td>否</td></tr><tr><td>af_ad_id</td><td>即相关广告的ID</td><td>是</td><td>否</td><td>是</td><td>否</td><td>否</td></tr><tr><td>install_time</td><td>Install Time（激活时间）</td><td>是</td><td>是</td><td>是\*</td><td>是</td><td>是</td></tr><tr><td>attributed_touch_type</td><td>Touch Type（广告互动类型）</td><td>是</td><td>是</td><td>是</td><td>是</td><td>否</td></tr><tr><td>geo</td><td>国家/地区</td><td>是</td><td>是</td><td>是</td><td>是</td><td>是</td></tr><tr><td colspan="7">\*在活跃维度的KPI中，激活时间即事件时间。 </td></tr></tbody></table>

   </Accordion>

   <div id="kpis" />

   <Accordion title="KPI">

   KPI可以说明您应用的使用情况，帮助您提炼用户行为中的关键信息。

   <div id="ltv" />

   <Accordion title="LTV">

   LTV（生命周期价值）— 汇总的事件数据，即选定时间范围内激活应用的用户从激活之日起到目前为止所完成的事件数据。

   | KPI的API名称 | 说明 |
   | --- | --- |
   | impressions | 选定时间范围内的展示量 |
   | clicks | 选定时间范围内的点击量 |
   | installs | 选定时间范围内的激活量 |
   | cr | Conversion Rate |
   | sessions | 在选定时间范围内激活应用的用户打开应用的次数 |
   | loyal\_users | 在选定时间内激活应用的忠实用户数 |
   | loyal\_users\_rate | 忠实用户数/总激活数 |
   | cost | 选定时间范围内所产生的总成本。*详情请见局限性说明。 |
   | revenue | 在选定时间范围内激活应用的用户所产生的LTV收入 |
   | roi | 在选定时间范围内的投资回报率 |
   | arpu\_ltv | 在选定时间范围内激活应用的用户平均带来的收入 |
   | average\_ecpi | 选定时间范围内的平均有效激活成本（eCPI）。需在调用中同时包含成本和激活参数才能获取该指标。 |
   | 卸载 | 在选定时间范围内激活应用，之后又将其卸载的用户 |
   | uninstalls\_rate | 卸载率 |
   | event\_counter\_[event\_name] | 事件发生次数 |
   | unique\_users\_[event\_name] | 完成相关事件的独立用户数 |
   | sales\_in\_usd\_[event\_name] | 与事件一并上报的收入 |

   </Accordion>

   <div id="retention" />

   <Accordion title="留存">

   留存是用于衡量现有活跃用户的指标。

   **请注意：**

   * 留存天数最长可支持到激活后的第30天，第0天为激活当天。也就是说，[x]的值不能超过30。
   * 如果您请求的是retention\_day\_1（留存第1天）的数据，而该数据还未达到可用状态，则该指标会返回前一天激活应用的用户数据。举例来说，假设您在1月2日请求retention\_day\_1（留存第1天），拉取1月1日激活应用的用户数据。由于该指标尚未达到可用状态，因此该指标会返回12月31日激活应用的用户数据。

   | 关键绩效指标 | 说明 |
   | --- | --- |
   | retention\_day\_[x] | 第X天的用户留存量 |
   | retention\_rate\_day\_[x] | 第X天的用户留存量在激活量中的占比 |

   </Accordion>

   <div id="activity" />

   <Accordion title="活跃数据">

   选定时间范围内的应用使用情况**请注意**：

   | 关键绩效指标 | 说明 |
   | --- | --- |
   | activity\_average\_dau | 选定时间范围内的平均日活用户（DAU） |
   | activity\_average\_mau | 选定时间范围内的平均月活用户（该时间范围中某个日期的单天数据是该日期之前30天内的独立用户总数） |
   | activity\_average\_dau\_mau\_rate | 平均DAU/MAU比率 |
   | activity\_average\_arpdau | 平均日活用户收入——某一天的收入除以总独立用户数得到的平均值 |
   | activity\_sessions | 在选定时间范围内的应用打开次数 |
   | activity\_revenue | 选定时间范围内上报的收入 |
   | activity\_event\_counter\_[event\_name] | 选定时间范围内用户产生的事件数 |
   | activity\_sales\_in\_usd\_[event\_name] | 选定时间范围内与事件一并上报的收入 |
   | activity\_average\_unique\_users\_[event\_name] | 在选定时间范围内完成某个事件的平均独立用户数 |

   </Accordion>

   <div id="cohort" />

   <Accordion title="群组">

   广告主可以使用AppsFlyer的群组功能来查看并对比多个群组在不同时间范围内的不同指标。

   **请注意：**

   * 则每用户平均收入为9/100000=0.00009，因此该值会显示为0。
   * 群组天数：群组天数最长可支持到激活后的第90天，第0天为激活当天。群组天数的值[x]必须在1-90之间，  请注意：虽然您可以在群组面板查看第0天的数据，但Master API不支持cohort\_day\_0（群组第0天）。
   * Master API V2

   **应用打开（Sessions）**

   | 关键绩效指标 | 说明 |
   | --- | --- |
   | cohort\_day\_[x]\_total\_sessions\_per\_user | 群组第X天 - 到第X天（含）的每用户累计session数 |
   | cohort\_day\_[x]\_sessions\_per\_user | 群组第X天 - 仅该群组在第X天的session数 |
   | cohort\_[x]\_days\_total\_sessions\_per\_user | 现已无需再指定Cohort\_day\_1\_total\_sessions\_per\_user的KPI，而是在URL中添加Cohort\_day\_x\_total\_sessions\_per\_user |

   **收入**

   | 关键绩效指标 | 说明 |
   | --- | --- |
   | cohort\_day\_[x]\_total\_revenue\_per\_user | 群组第X天 - 到第X天（含）的每用户累计收入 |
   | cohort\_day\_[x]\_revenue\_per\_user | 群组第X天 - 仅该群组在第X天的ARPU |
   | cohort\_[x]\_days\_total\_revenue\_per\_user | 现已无需再逐个指定各天的Cohort\_day\_1\_total\_revenue\_per\_user，而是在URL中添加Cohort\_day\_x\_total\_revenue\_per\_user。 |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_revenue\_per\_user | 群组第X天指定应用内事件的每用户累计收入 |
   | cohort\_day\_[x]\_event\_[eventname]\_revenue\_per\_user | 群组第X天指定应用内事件的每用户收入 |

   **事件**

   | 关键绩效指标 | 说明 |
   | --- | --- |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_per\_user | 群组第X天 - 到第X天（含）的每用户累计事件数 |
   | cohort\_day\_[x]\_event\_[eventname]\_per\_user | 群组第X天 - 仅该群组在第X天的事件 |
   | cohort\_[x]\_days\_total\_event\_[eventname]\_per\_user | 现已无需再逐个指定各天的KPI，而是在URL中添加Cohort\_day\_x\_total\_revenue\_per\_user。 |

   </Accordion>

   <div id="protect360" />

   <Accordion title="Protect360">

   **Protect360的KPI**

   | 说明 | 关键绩效指标 |
   | --- | --- |
   | **激活假量** |  |
   | Total （总计） | protect360\_total\_installs |
   | 已拦截 | blocked\_installs |
   | 拦截率 | blocked\_installs\_rate |
   | 归因后被识别为假量的激活 | 归因后判定为假量的激活 |
   | 归因后的激活假量识别率 | post\_attribution\_installs\_rate |
   | 总体激活假量 | total\_fraudulent\_installs |
   | 激活假量占比 | fraudulent\_installs\_rate |
   | **虚假激活** |  |
   | 实时拦截 | real\_time\_fake\_installs |
   | 归因后假量 | 归因后识别的虚假激活 |
   | **被劫持的激活** |  |
   | 实时拦截 | real\_time\_hijacked\_installs |
   | 归因后假量 | post\_attribution\_installs\_hijacked\_installs |
   | **验证规则** |  |
   | 已拦截的激活 | validation\_rules\_blocked\_installs |
   | 已拦截的归因 | validation\_rules\_blocked\_attribution |
   | **虚假流量细分** |  |
   | 黑名单拦截的 SiteID | blocked\_installs\_siteid\_blacklist |
   | 归因后 SiteID 黑名单 | post\_attribution\_installs\_siteid\_blacklist |
   | 已拦截的机器人作弊 | blocked\_installs\_bots |
   | 归因后识别的机器人作弊 | post\_attribution\_installs\_bots |
   | 已拦截 - 行为异常 | blocked\_installs\_behavioral\_anomalies |
   | 归因后识别 - 行为异常 | post\_attribution\_installs\_behavioral\_anomalies |
   | 已拦截 - 激活验证 | blocked\_installs\_install\_validation |
   | **被劫持的流量细分** |  |
   | 已拦截的激活劫持 | blocked\_installs\_install\_hijacking |
   | 归因后识别的激活劫持 | post\_attribution\_installs\_installs\_hijacking |
   | 已拦截 - CTIT异常 | blocked\_installs\_ctit\_anomalies |
   | 归因后识别 - CTIT异常 | post\_attribution\_installs\_ctit\_anomalies |
   | 已拦截 - 撞库 | blocked\_installs\_click\_flood |
   | 归因后识别 - 撞库 | post\_attribution\_installs\_click\_flood |
   | **点击** |  |
   | Total （总计） | protect360\_total\_clicks |
   | 已拦截 | blocked\_clicks |
   | % | blocked\_clicks\_rate |
   | **应用内事件** |  |
   | Total （总计） | protect360\_total\_in\_apps |
   | 已拦截 | blocked\_in-app-events |
   | % | blocked\_in-app-events\_rate |
   | 刷单迹象 - 新设备 |  |
   | 激活假量 | install\_fraud\_new\_devices\_total |
   | 激活假量占比 | install\_fraud\_new\_devices\_total\_installs\_rate |
   | 忠实用户% | install\_fraud\_new\_devices\_total\_loyal\_user\_rate |
   | **刷单迹象 - LAT设备** |  |
   | 激活假量 | install\_fraud\_lat\_devices\_total |
   | 激活假量占比 | install\_fraud\_lat\_devices\_total\_installs\_rate |
   | 忠实用户% | install\_fraud\_lat\_devices\_total\_loyal\_user\_rate |
   | **点击撞库预警指标** |  |
   | 转化率 | conversion\_rate |
   | **点击撞库迹象 - CTIT** |  |
   | 超过60分钟 | click\_flood\_over\_1\_hour\_rate |
   | 超过5小时 | click\_flood\_over\_5\_hours\_rate |

   </Accordion>

   <div id="calculated-kpis" />

   #### 推算KPI

   除上文所述的KPI之外，您也可以在Master API报告中添加推算KPI，这样您就能在Master API报告中配置自定义的推算报告。

   您可以在KPI计算公式中添加各种预定义的KPI对象，数量不限。每个KPI计算对象中包含一个键和一个值。其中的键即为该KPI的名称，值则为该KPI的计算公式。

   Master API支持标准的算术运算符，包括转码为%2b的加号（+）、减号（-）、乘号（*）和转码为%2f的除号（/）。

   推算KPI的字段键**必须**以“calculated\_kpi\_”开头，后接任意有效字符串，如“calculated\_kpi\_purchaserate”。

   <div id="example" />

   > 📄 **示例**
   >
   > 前三天的综合留存率
   >
   > ```http
   > kpis=installs,loyal_users_rate&calculated_kpi_3days_retention=
   > retention_day_1%2Bretention_day_2%2Bretention_day_3
   > ```
   >
   > 每次展示的平均收入
   >
   > ```http
   > kpis=installs&calculated_kpi_rev_per_impression=revenue%2Fimpression
   > ```
   >
   > 群组第7天的ROI
   >
   > ```http
   > kpis=installs,roi,arpu_ltv,cost,revenue&calculated_kpi_roi_day_7=
   > (cohort_day_7_total_revenue_per_user-average_ecpi)%2Faverage_ecpi
   > ```

   </Accordion>

   <div id="filters-optional" />

   <Accordion title="筛选条件（可选）">

   | 参数 | 说明 | 示例 | 是否必须配置 |
   | --- | --- | --- | --- |
   | pid | * 用于筛选具体渠道的数据。<br />* 可以用逗号来区隔多个渠道名称。 | pid=organic,applovin\_int | 否 |
   | c | * 用于按广告系列名称筛选数据。<br />* 可以用逗号来区隔多个渠道名称。 | c=my\_sample\_campaign | 否 |
   | af\_prt | * 用于按代理名称筛选数据。<br />* 可以用逗号来区隔多个渠道名称。 | af\_prt=moburst | 否 |
   | af\_channel | * 用于按流量入口名称筛选数据。<br />* 可以用逗号来区隔多个渠道名称。 | af\_channel=Instagram | 否 |
   | af\_siteid | * 用于按子渠道筛选数据。<br />* 可以用逗号来区隔多个渠道名称。 | af\_siteid=12345678 | 否 |
   | geo | * 用于按国家筛选数据。<br />* 可以用逗号来区隔多个渠道名称。 | geo=US,DE | 否 |

   </Accordion>

   <div id="localization" />

   <Accordion title="本土化">

   本地货币和应用层级指定时区是在AF后台的<Anchor target="_blank" href="/marketers/zh/docs/app-settings">应用配置</Anchor>页中设置的。Master API数据可以使用系统默认货币和时区拉取数据，也可以按应用层级的指定货币和时区拉取。

   数据本地化遵循以下规则：

   * 如需按应用层级的指定时区/货币来拉取数据，请确保所有应用都配置了相同的时区/货币，否则只能按UTC和USD来拉取数据。时区和货币是分开设置的，也就是说，如果您为所有应用配置了相同的货币和不同的时区，那么您可以用指定货币来拉取数据，但不能用指定时区拉取。
   * 如果您在选定时间范围内更改了面板应用配置中的时区，则报告会呈现最近一次时区更改后的相关值。

   您可以使用以下参数来选择应用层级设置。**请注意**：注意：如果您不使用应用层级设置参数，则会拉取到以USD为货币、以UTC为时区的数据。

   | 参数 | 说明 | 示例 | 是否必须配置 |
   | --- | --- | --- | --- |
   | currency | 以应用配置中的指定货币显示金额 | currency=preferred | 否 |
   | timezone | 使用应用配置中的指定时区 | timezone=preferred | 否 |

   </Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 成本数据 | <ul><li>不同成本维度的可用性（即广告组、广告、地理位置、流量入口和子渠道）取决于<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">具体的广告平台</Anchor>。</li><li>如需拉取eCPI数据，请在URL中同时加入激活和成本参数。</li><li>总体而言，无论您查询的是什么维度的数据，所有流量来源，包括自有媒体（只要您使用带成本参数的AppsFlyer链接进行投放），都能全面支持成本数据。部分自归因平台会使用他们自己的API，这类API通常仅支持某些特定维度的成本数据。 比如<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-faq#what-are-the-limitations-of-facebook-cost-data-in-master-api">Meta ads</Anchor>不支持在一次调用中同时按地理位置和流量入口分组，但可以分两次单独调用这两个维度的数据。</li><li>对于近期（约最近7天内）有成本数据但无激活数据的广告系列，Master API无法拉取其相关数据。</li></ul> |
| 分组 | 指定的分组维度仅适用于LTV、活跃和留存KPI。如某个KPI的数据不可用，则API会返回N/A。举例来说，假设您请求了retention\_rate\_day\_7（第7天的留存率）数据，并以af\_channel（流量入口）分组，这时API返回N/A，则表示该数据不可用。 |
| 报告行数上限 | 20万 |
| 事件名称 | Master API目前不支持带有正斜杠`/`//的事件名称。为避免出现数据拉取不到的情况，请勿在事件名称中使用“/”。 |
| 数据处理时长 | 您选择的应用越多，处理时间就越长，等待响应的时间也就越长。 |
| 日期范围 | 以天为单位。 |
| 代理 | Master API不可用 |
| 广告平台 | Master API不可用 |
| 历史数据 | <ul><li>LTV数据：5年</li><li>2年。</li><li>活跃数据：3年</li></ul> |
| 再营销 | <ul><li>不支持。</li><li>请注意：</li></ul> |

</Accordion>

<div data-zendesk-anchors="master-api%E2%80%94user-acquisition-metrics-via-api=master-api--%E9%80%9A%E8%BF%87api%E8%8E%B7%E5%8F%96%E6%8B%89%E6%96%B0%E6%8C%87%E6%A0%87 h_01JJVMXKACJ2V4YZFGYXVB8FQF=master-api--%E9%80%9A%E8%BF%87api%E8%8E%B7%E5%8F%96%E6%8B%89%E6%96%B0%E6%8C%87%E6%A0%87 h_01JJVMXKACZDXPQG4271HFYWCE=api-parameters h_01JJVMXKAEXMKQQRT0RT6N8P74=groupings h_01JJVMXKAEHM0871GBQHZENRXA=kpis h_01JK2ZEH32Y92Y553540XDYZFA=ltv h_01JK2ZEH32A08EEDZEWFSX3ZFS=retention h_01JK2ZEH3219694E4PFPZ8ZXZF=activity h_01JK2ZEH32NCWZWKTDS0J6DFS2=cohort h_01JK2ZEH32Q7B6RCQYXNHM8KGK=protect360 calculated-kpis=%E6%8E%A8%E7%AE%97kpi h_01JJVMXKAFW1TEE35GK9B20TRP=%E6%8E%A8%E7%AE%97kpi h_01JJVMXKAFZDPNXKAZCBQ27DBD=%E7%A4%BA%E4%BE%8B h_01JJVMXKAFWA4D47MH7VSXKN14=filters-optional h_01JJVMXKAFSBXJ9EJJ16BF8H7Q=localization additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01JJVMXKAFFW2G3N7188DHYCB8=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01JJVMXKAF25YX092NE9DV9862=limitations" />

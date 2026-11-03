---
title: '[Beta] 跨平台终端用户事件报告在数据存储中'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2025-10-07T10:37:56Z'
  edited_at: '2026-10-14T10:01:31Z'
  id: 39748676204817
  locale: zh-cn
  section: Cross platform reports
  section_id: 50467263168657
  url: https://support.appsflyer.com/hc/zh-cn/articles/39748676204817
---
> **概要：** 跨平台终端用户事件报告衡量跨平台和设备的完整用户旅程、转化和LTV

跨平台终端用户事件报告是一个原始数据报告，提供每个用户的会话和应用内事件的事件级日志，通过您的客户用户ID（CUID）在平台之间链接。每个事件包括跨平台归因结果，使您能够分析完整的用户旅程。

有关基于用户的归因流程和配置的更多信息，请参见<Anchor target="_blank" href="/marketers/zh/docs/beta-user-based-cross-platform-attribution">基于用户的跨平台归因</Anchor>。

## 报告字段

要了解报告中包含哪些字段，[下载报告样本](https://docs.google.com/spreadsheets/d/e/2PACX-1vRhOl-tyaJvgPd9rxGkGMNrgzHPpr7ZsMMnONOHkzdObor158gJPt7XwCBkreM4ka4OkGIyDmqCp_hh/pub?output=csv)。

报告样本包括所有报告字段及其值。有关字段的定义，请参见<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">字段字典</Anchor>。

## 报告数据的新鲜度

* 报告每4小时运行一次批处理。
* 每次批处理运行处理在前一个4小时窗口内进入数据库的事件。
  * 示例：上午8:00的批处理运行处理在上午3:00到7:00之间输入数据库的事件。

* 事件被分配到相应的每小时桶中。
  * 示例：在上午3:00到4:00之间进入数据库的事件将出现在上午3:00的桶中。

> 🚧 **重要提示！**
>
> 事件实际发生与其进入数据库之间通常会有短暂的延迟。报告使用数据库输入时间以确保准确和一致的每小时分组。

### 上午8:00批处理运行的示例

| 日期 | 报告版本 | 报告可在此处获取 | 报告包括发生在之间的事件 | 报告包括在数据库中输入的事件，时间范围为 |
| --- | --- | --- | --- | --- |
| 2025-10-01 | 3:00 | 9:00 | 2:00-4:00 | 3:00-4:00 |
| 2025-10-01 | 4:00 | 9:00 | 3:00-5:00 | 4:00-5:00 |
| 2025-10-01 | 5:00 | 9:00 | 4:00-6:00 | 5:00-6:00 |
| 2025-10-01 | 6:00 | 9:00 | 5:00-7:00 | 6:00-7:00 |

上述示例的说明：

* 在运行前的最后一小时内的事件不会被处理，以便有足够的时间丰富事件及其相关的CUID。在上述示例中，上午8:00的批处理过程处理在3:00到7:00之间输入数据库的事件。在7:00到8:00之间输入数据库的事件不会被处理。
* 报告在批处理运行后一个小时内才可用，因为内部过程在该小时内更新批处理。在上述示例中，上午8:00的批处理在上午9:00可用。

## 如何订阅报告？

1. 从AppsFlyer后台左侧的菜单栏中选择**导出 > Data Locker**。
2. 在**数据储存库内容**窗格中，向下滚动到**高级报告**部分。
3. 选择**终端用户事件跨平台。**

## 如何访问您云存储桶中的报告数据？

构成报告路径的文件夹结构如下：

```
<bucket-name>/<DataLocker connection name>/t=end_user_events_user_level_cross_platform/dt=<dt=yyyy-mm-dd>/h=<hour>/
```

### 报告文件夹的层次结构

[![](https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png)](https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png)

## BI开发者注意事项

* 每个报告的每小时存储桶包含独特的终端用户事件。确保您每小时或每天提取所有报告。
* 广告收入事件尚未包含。
* 所有应用的数据都集中在一个文件中。您可以使用App ID字段来区分各应用的数据，或将Data Locker设置为按应用区分数据。建议使用统一的隔离类型。
* 归因前数据（如成本、点击和展示）应从Cost ETL报告中获取。

### 查询示例

本节列举了一些通过Data Locker拉取数据并用于BI的常见使用场景，每个示例由SQL语句说明

<div id="calculating-total-user-acquisitions" />

<Accordion title="计算总用户获取">

计算每个媒体来源和活动的新独特用户数量。

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT customer_user_id) AS user_acquisition
	,
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-platform-activations" />

<Accordion title="计算总平台激活数">

计算每个用户带来的新平台、组、媒体来源和活动的总数。

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT CASE 
			WHEN platform_group = 'PC'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CONSOLE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CTV'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'MOBILE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Web'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Other'
				THEN customer_user_id
			ELSE NULL
			END) AS total_activations
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-revenue" />

<Accordion title="计算总收入">

计算每个媒体来源和活动的总收入。

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,SUM(revenue_value_customer) AS total_revenue
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = ’YOUR_PRODUCT_LINE_NAME’
GROUP BY install_date
	,media_source
	,campaign_name;
```

</Accordion>

<div data-zendesk-anchors="the-report-fields=%E6%8A%A5%E5%91%8A%E5%AD%97%E6%AE%B5 h_01K6Z40KG9H1AC81H77XXEGK1B=%E6%8A%A5%E5%91%8A%E5%AD%97%E6%AE%B5 report-data-freshness=%E6%8A%A5%E5%91%8A%E6%95%B0%E6%8D%AE%E7%9A%84%E6%96%B0%E9%B2%9C%E5%BA%A6 h_01K6Z40KG9PTRAFGXB3XJH5TJ7=%E6%8A%A5%E5%91%8A%E6%95%B0%E6%8D%AE%E7%9A%84%E6%96%B0%E9%B2%9C%E5%BA%A6 h_01K6Z40KG9QPSMXT13N50TE7KE=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA example-of-the-800-am-batch-run=%E4%B8%8A%E5%8D%88800%E6%89%B9%E5%A4%84%E7%90%86%E8%BF%90%E8%A1%8C%E7%9A%84%E7%A4%BA%E4%BE%8B h_01K6Z40KG9JTHGJG7YJNH9TTDT=%E4%B8%8A%E5%8D%88800%E6%89%B9%E5%A4%84%E7%90%86%E8%BF%90%E8%A1%8C%E7%9A%84%E7%A4%BA%E4%BE%8B how-to-subscribe-to-the-report=%E5%A6%82%E4%BD%95%E8%AE%A2%E9%98%85%E6%8A%A5%E5%91%8A h_01K6Z40KG9J1XWV99Z9M7AG0BY=%E5%A6%82%E4%BD%95%E8%AE%A2%E9%98%85%E6%8A%A5%E5%91%8A how-to-access-the-report-in-your-bucket=%E5%A6%82%E4%BD%95%E8%AE%BF%E9%97%AE%E6%82%A8%E4%BA%91%E5%AD%98%E5%82%A8%E6%A1%B6%E4%B8%AD%E7%9A%84%E6%8A%A5%E5%91%8A%E6%95%B0%E6%8D%AE h_01K6Z40KG9CDQ43ASM5T80AK65=%E5%A6%82%E4%BD%95%E8%AE%BF%E9%97%AE%E6%82%A8%E4%BA%91%E5%AD%98%E5%82%A8%E6%A1%B6%E4%B8%AD%E7%9A%84%E6%8A%A5%E5%91%8A%E6%95%B0%E6%8D%AE dl-report-folder-hierarchy=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84 h_01K6Z40KG9NSVWTRSHR71Q7PM6=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84 bi-developer-considerations=bi%E5%BC%80%E5%8F%91%E8%80%85%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01K6Z7QHDT4Q2D4JFGC28W8MND=bi%E5%BC%80%E5%8F%91%E8%80%85%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 query-examples=%E6%9F%A5%E8%AF%A2%E7%A4%BA%E4%BE%8B h_01K6Z40KG9E2F30Q9P5GFA9TWT=%E6%9F%A5%E8%AF%A2%E7%A4%BA%E4%BE%8B h_01K6Z40KG9Y4MWKY6HX8A5NPXA=calculating-total-user-acquisitions h_01K6Z40KG9J9VKC3JH6XNNDA52=calculating-total-platform-activations h_01K6Z40KG9SE8068HG75H59E8Q=calculating-total-revenue" />

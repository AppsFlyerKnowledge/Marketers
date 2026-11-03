---
title: 公告：Master API与Pivot活跃维度数据更新
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-08-17T07:26:26Z'
  edited_at: '2026-10-14T10:00:20Z'
  id: 49896622875537
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/49896622875537
---
| 部分 | 详情 |
| --- | --- |
| 更新内容 | 为确保各产品中显示的活跃维度指标的一致性，Master API和Pivot的活跃维度数据将切换至My Dashboards、AppsFlyer MCP、AI Assistant及代理当前使用的数据源。<br /><br />本次更新将对活跃数据中用于筛选和分组的部分底层字段值进行调整，详情见下文。<br /><br />通常情况下，您无需采取任何操作。 |
| 生效日期 | 2026年9月14日 |
| 影响范围 | <ul><li>所有通过Master API和Pivot分析以下活跃维度指标的客户：`activity_average_dau`、`activity_average_dau_mau_rate`、`activity_average_arpdau`、`activity_sessions`、`activity_revenue`、`activity_event_counter_[event_name]`、`activity_sales_in_usd_[event_name]`、`activity_average_unique_users_[event_name]`。</li></ul>注意：`activity_average_mau`不受影响。<ul><li>群组、LTV、留存及其他类型的数据不会发生变化。如果在同一份报表中同时使用活跃数据和上述数据，在其他数据类型完成相同更新前，部分字段值可能暂时不一致，尤其是媒体渠道/`pid`。</li></ul> |
| 待办事项 | 本次更新将自动完成，通常情况下，您无需采取任何操作。<br /><br />如果您的活跃维度数据报表包含下文所列字段值进行筛选或分组，请在2026年9月14日后检查相关筛选条件。更新后，原有字段值可能返回不同的结果，或可能无法返回结果。 |
| 注意事项 | 请留意以下变化：<br /><br />* <strong>更新后，部分指标值可能出现小幅波动。</strong>活跃数据将迁移至新的数据处理系统，因此指标值可能略有变化。独立用户数、DAU及相关指标的差异预计不超过3%。这是数据处理系统切换带来的正常变化，并非数据错误。<br />* 在`attributed_touch_type`分组中，**“Pre-install”和“preload”将统一归入“download”**。在Master API中按`attributed_touch_type`筛选或分组时，“pre-install”和“preload”将不再单独返回结果。相关流量将统一计入“download”。<br />* <strong>空值将改为空字符串。</strong>其中包括自然量/None媒体渠道（Master API中的`pid`、Pivot中的Media source），更新后将返回空字符串。<br />* **两个媒体渠道名称将发生变化：**`facebook`将改为`Facebook Ads`，`twitter`和`twitter_int`将统一改为`Twitter`。其他媒体渠道名称保持不变。<br />* <strong>部分字符将替换为下划线。</strong>所有控制字符以及字符`;`、`{`、`}`、`$`、`<`、`>`、`'`、`\`均将替换为下划线。<br />* **以下字段将采用新的字符数上限：**<br />  * `ad_id`（最多250个字符）<br />  * `ad_name`（最多256个字符）<br />  * `event_name`（最多100个字符）<br />  * `app_version`（最多64个字符）<br />  * `agency`（最多32个字符）<br />  * `keywords`（最多90个字符）<br />  * `install_app_store`（最多50个字符）<br />  * `os_version`（最多20个字符）<br /><br />此次更新后，活跃维度数据将迁移至更加现代化且易于扩展的基础架构，以提升可靠性和性能，并为后续产品升级提供支持。 |
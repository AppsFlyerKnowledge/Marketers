---
title: 公告：My Dashboards 中的群组与活跃数据指标更新
metadata:
  keywords:
    - Partners
    - Marketers
    - Marketing Analytics
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maya-kahane
    - Marketers
    - Marketing Analytics
  created_at: '2026-04-19T14:38:57Z'
  edited_at: '2026-10-14T10:00:43Z'
  id: 45887523041425
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/45887523041425
---
| **最新动态** | 自**2026年7月**起，**My Dashboards**中的群组与活跃数据指标将迁移至升级后的数据基础设施，以支持面向**AI的数据能力**。本次更新将于**2026年7月至8月**期间，分阶段向客户开放。<br /><br />在逐步上线过程中，您可能会看到部分指标数值、历史数据可用性和细分维度发生变化。<br /><br />本次更新为活跃数据引入了新的视图类型和指标，提高了群组数据中独立用户数的准确性，并扩展了群组和活跃数据两部分的历史数据及细分选项。 |
| --- | --- |
| **生效日期** | 2026年7月至8月逐步推出。 |
| **适用人群** | 在**My Dashboards**中使用组群指标的所有广告主、代理商和合作渠道。 |
| **待办事项** | 无需进行任何操作，更新将自动生效。 |
| **须知事项** | **<span id="h_activity-retargeting-and-ua-view-types"></span>活跃数据新增再营销和获客视图类型**<br /><br />现在，活跃数据可按视图类型进行筛选和分析，包括再营销和获客。<ul><li>再营销数据自2025年2月起可用。</li><li>获客数据自2026年2月起可用。</li><li>再营销和获客视图不包含当天数据，数据延迟1天。</li></ul>**<span id="h_net-revenue-metrics"></span>群组与活跃数据新增净收入指标**<br /><br />对于通过**ROI360 商店收入**衡量净收入，或在应用内事件中传递`af_net_revenue`事件参数的客户，现在可查看以下指标：<ul><li>净收入</li><li>净ROAS</li><li>净ROI</li><li>净ARPU</li><li>净毛利润</li></ul>以上指标仅对发送净收入数据的客户可见。<br /><br />**<span id="h_ctv-app-support"></span>群组与活跃数据现已支持 CTV 应用**<br /><br />群组与活跃数据指标现已支持 CTV 应用。<br /><br />**<span id="h_new-dimensions"></span>群组与活跃数据新增维度**<br /><br />群组和活跃数据现已支持使用以下维度进行细分分析：<ul><li>平台</li><li>Sub 1</li><li>互动目标位置</li></ul>**<span id="h_extended-historical-data"></span>群组历史数据范围扩展**<br /><br />对于大多数群组指标，您现在可以查看自**2024年5月6日**起的数据，历史数据范围较此前增加约6个月。<br /><br />这一变化不适用于「独立用户」的每日数据，该数据自**2025年6月3日**起可用。<br /><br />**<span id="h_unique-users-updated-calculation-method"></span>群组每日明细中「独立用户」计算方式更新**<br /><br />以下指标现已在群组每日明细中采用更新后的计算方式，例如第1天、第7天及其他每日明细：<ul><li>应用内事件唯一用户</li><li>留存</li><li>留存率</li><li>ARPU</li></ul>**<span id="h_what-changed-and-why"></span>变更内容及原因**<br /><br />现在，系统会在设备层面识别用户。对于多次再互动的用户，系统仅计为1名用户，而不是按每次再互动分别计数。<br /><br />这一更新修正了此前针对投放再互动广告系列的应用可能出现的重复计数问题。<br /><br />如果您的应用投放了再互动广告系列，可能会看到每日独立用户数下降。这是一次数据修正，并不代表实际用户数或效果下降。<br /><br />该新方法采用概率计数法，由此产生的误差幅度非常小，通常在1%至2%之间。属于正常现象，并非数据错误。<br /><br />**<span id="h_unique-users-data-availability"></span>数据可用性**<ul><li>每日粒度数据自**2025年6月3日**起可用。</li><li>2025年6月3日之前的每日独立用户数据无法在My Dashboards中查看。</li><li>周粒度和月粒度不受影响，完整历史数据仍可查看。</li></ul>**<span id="h_activity-unique-users-and-active-users-historical-availability"></span>活跃数据中独立用户和活跃用户的历史数据可用范围**<br /><br />对于**2025年6月3日**之前的日期，活跃数据中的独立用户和活跃用户仅支持按日期拆分查看。<br /><br />自**2025年6月3日**起，可查看某个日期范围内的汇总数据。<br /><br />这一限制适用于所有基于独立用户或活跃用户计算的指标，并且属于永久限制。<br /><br />**<span id="h_uninstalls-temporarily-unavailable"></span>群组中的卸载量暂不可用。**<br /><br />「卸载量」指标暂时不可用。<br /><br />**LTV将不会受到影响。**<br /><br />**<span id="h_ad-revenue-unified-in-utc"></span>所有面板中的广告收入统一采用UTC显示**<br /><br />所有面板中的广告收入指标现在均采用UTC显示，不受对接类型或应用层级时区设置影响。历史数据不受影响。<ul><li>这一变更适用于通过展示级(SDK)对接类型收集的广告收入。其他对接类型的数据此前已按UTC报表。</li><li>我们进行这一调整，是为了标准化来自多个来源和合作渠道的广告收入数据，因为其中大多数来源和合作渠道均以UTC上报数据。</li><li>在变更日期（7月20日），如果您的应用在应用设置中使用非UTC时区，您可能会看到广告收入数据有所上升。这并不是数据重复或新增数据，也没有任何数据被删除，而是同一批数据被移动到不同日期，以便与UTC保持一致。</li></ul>**<span id="h_about-the-transition"></span>关于本次迁移**<br /><br />本次迁移旨在将群组和活跃数据转移至更现代化、可扩展性的数据基础设施，以提高数据可靠性和表现，支持AI分析功能，并为AppsFlyer汇总归因数据的未来产品升级提供支持。<br /><br />如果您需要查看更早期的数据，仍可使用Cohort&Retention面板。您可以通过该面板访问**2025年6月3日**之前的群组独立用户数据，或在「卸载量」指标重建期间查看卸载量数据。 |

<div data-zendesk-anchors="activity-retargeting-and-ua-view-types=h_activity-retargeting-and-ua-view-types net-revenue-metrics=h_net-revenue-metrics ctv-app-support=h_ctv-app-support new-dimensions=h_new-dimensions extended-historical-data=h_extended-historical-data unique-users-updated-calculation-method=h_unique-users-updated-calculation-method what-changed-and-why=h_what-changed-and-why unique-users-data-availability=h_unique-users-data-availability activity-unique-users-and-active-users-historical-availability=h_activity-unique-users-and-active-users-historical-availability uninstalls-temporarily-unavailable=h_uninstalls-temporarily-unavailable ad-revenue-unified-in-utc=h_ad-revenue-unified-in-utc about-the-transition=h_about-the-transition" />

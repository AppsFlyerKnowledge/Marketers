---
title: 数据协作平台（DCP） - 运行和管理测量
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2026-03-04T10:59:23Z'
  edited_at: '2026-10-14T10:01:04Z'
  id: 44427723216017
  locale: zh-cn
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/zh-cn/articles/44427723216017
---
> **概要：** 在您配置现场或非现场测量后，可以将其作为实时测量或历史测量运行。选择最符合您目标的模式：持续测量性能或验证特定时间段的结果。

<div id="about-the-measurement-run-modes" />

## 关于测量运行模式

在您<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#站内与站外广告系列归因">配置现场或非现场测量</Anchor>后，您可以选择如何运行测量。

您可以选择两种运行模式：

* **实时测量**：持续测量，定期更新，因此您可以在实时仪表板上监控性能，随着新数据的添加而不断更新。
* **历史测量**：在特定日期范围内进行的一次性测量，您可以在历史仪表板上查看和分析。

<div id="live-vs-historical-measurements" />

### 实时与历史测量

| 项目 | 历史测量 | 实时测量 |
| --- | --- | --- |
| 运行时 | **按需**（手动）执行 | **自动化**每日执行 |
| 数据来源 | 使用**历史数据上传** | 需要**SDK/ETL设置**并在预定时间间隔运行 |
| 支持的源类型 | <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">追加</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">覆盖（快照）</Anchor> | <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">附加类型自定义源</Anchor> |
| 时间范围选择 | 选择一个**开始和结束日期**（从可用数据中） | 选择一个**仅开始日期**（平台在激活时计算历史时间范围，并持续累积数据） |
| 每次测量多少 | 多应用 | 一个 |

<div id="choose-the-measurement-you-need" />

### 选择您需要的测量

使用下面的指导来决定哪个测量适合您的目标。

**如果您想选择实时测量**

* 持续更新的测量，随着新数据的到来而更新
* 一个可以持续监控性能的仪表板
* 一个旨在长期、始终在线测量的设置（不是一次性分析）

**如果您想选择历史测量**

* 在特定日期范围内进行一次性测量。
* 在活动结束后分析性能。
* 通过更改回顾窗口进行假设分析，以查看其对归因的影响。

**提示：** 如果您首先在测试设置或验证特定期间，请从**历史测量**开始。当您准备好进行持续监控时，切换到**实时测量**以获取持续更新。

<div id="run-a-live-measurement" />

## 进行实时测量

**前期准备：** <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#站内与站外广告系列归因">在测量设置页面配置现场或非现场测量活动</Anchor>.

1. 在**测量设置**页面，点击**立即运行**。

   如果**立即运行**被禁用，您的测量任务不完整。完成所有必需的设置任务以运行测量。
2. 在**准备运行**对话框中，选择**实时仪表板**。

   <div id="note" />

   > 📘 **注意**
   >
   > * 如果测量使用<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">覆盖</Anchor>源，则仅可用**历史仪表板**。**实时仪表板**需要**附加类型**源（或AppsFlyer SDK内事件）才能自动刷新。
   > * 在一次协作中只能运行**一个实时测量**。如果您在另一个实时测量正在运行时启动新的实时测量，系统会提示您暂停现有的测量。

3. 重命名仪表板或保留默认名称。
4. 选择**测量开始日期**。默认是今天的日期，但您可以从日期选择器中选择过去的日期。（您只能选择在数据源中存在的日期。）
5. 点击**开始**以开始实时测量。您将被重定向到协作测量页面。
6. 在协作测量页面上，自动验证检查成功完成后，点击**立即运行**。

<div id="run-a-historical-measurement" />

## 运行历史测量

**前期准备：** <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#站内与站外广告系列归因">在测量设置页面配置现场或非现场测量活动</Anchor>.

1. 在**测量设置**中，点击**立即运行**。  
   如果**立即运行**被禁用，您的测量任务不完整。完成所有必需的设置任务以运行测量。
2. 在**准备运行**对话框中，选择**历史仪表板**。
3. 重命名仪表板或保留默认名称。
4. 选择**测量日期范围**（您只能选择在数据源中存在的日期）：
   * 设置**开始日期**。
   * 设置 **结束日期**。
5. 点击 **开始** 开始历史测量。您将被重定向到协作测量页面。
6. 在协作测量页面上，自动验证检查成功完成后，点击**立即运行**。

<div id="manage-measurements" />

## 管理衡量

在您设置并运行测量后，从协作测量页面的测量面板管理它。您可以暂停或重新启动实时测量，调整日期，重新运行历史测量，或复制测量以创建新的运行。

<div id="the-collaboration-measurement-page" />

### 协作测量页面

[![](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)

<div id="pause-or-restart-live-measurement" />

<Accordion title="暂停或重新启动实时测量">

<div id="legend" />

#### 图例

* **A** - 测量面板
* **B** - 选定的测量
* **C** - 共享切换
* **D** - 选项菜单。

1. 打开协作测量页面。
2. 从测量面板 ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#协作测量页面)) 选择 **实时仪表板**。
3. 打开选项菜单 ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#协作测量页面)) 并点击 **测量设置**。
4. 在 **测量设置** 页面中，执行以下操作之一：
   * 要 **暂停** 实时归因，请关闭 **激活测量**，然后在 **暂停测量？** 对话框中确认。
   * 要 **重新启动** 实时归因，请打开 **激活测量**。

</Accordion>

<div id="change-measurement-start-and-end-dates" />

<Accordion title="更改测量的开始和结束日期">

您可以更改：

* 实时测量的 **开始日期**，或
* 历史测量的 **开始和结束日期**。

要更改测量的开始和结束日期，请按照以下步骤操作：

1. 打开协作测量页面。
2. 从测量面板中选择测量（[A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#协作测量页面)）。
3. 打开选项菜单 ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#协作测量页面)) 并点击 **测量设置**。
4. 在**测量设置**页面中，点击铅笔图标。
5. 点击开始或结束日期。
6. 从日期选择器中选择新日期。

</Accordion>

<div id="rerun-a-historical-measurement" />

<Accordion title="重新运行历史测量">

重新运行历史测量会使用最新数据重新计算归因。当前结果将被新结果替代。

1. 打开协作测量页面。
2. 从测量面板中选择测量（[A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#协作测量页面)）。
3. 打开选项菜单（[D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#协作测量页面)），然后点击**重新运行**。
4. 在提示消息中，点击**重新运行**。
5. 在协作测量页面上，自动验证检查成功完成后，点击**立即运行**。

</Accordion>

<div id="duplicate-a-live-or-historical-measurement" />

<Accordion title="复制实时或历史测量">

复制会基于现有设置创建一个新的测量。您可以更新设置并将其作为新的测量运行。

1. 打开协作测量页面。
2. 从测量面板中选择测量（[A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#协作测量页面)）。
3. 打开选项菜单（[D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#协作测量页面)），然后点击**复制**。
4. 在复制的**测量设置**页面中，根据您的需求自定义测量。

</Accordion>

<div id="share-a-dashboard" />

<Accordion title="分享仪表板">

您可以通过打开**共享**开关与您的合作者分享仪表板。当**共享**开启时，仪表板（及其测量结果）对协作中的其他用户可用。

当**共享**开启时，合作者可以做什么取决于他们是否被**分配**到仪表板。

* **分配的用户可以：**
  * 打开并查看仪表板
  * 打开测量设置并仅编辑分配给他们的任务。

* 分配的用户不能：
  * 开启/关闭共享（分享或取消分享）
  * 重新运行测量

* 未分配的用户访问权限更有限，即使仪表板被共享（例如，他们可能看不到结果摘要，也无法重新运行或分享）。

要分享仪表板：

1. 打开协作测量页面，从测量面板中选择您想要分享的仪表板。
2. 开启共享。仪表板将在您的协作者测量页面中可用。
3. 关闭共享以停止分享。当共享关闭时，只有您（和具有正确权限的用户）可以访问仪表板。

</Accordion>

<div data-zendesk-anchors="about-the-measurement-run-modes=%E5%85%B3%E4%BA%8E%E6%B5%8B%E9%87%8F%E8%BF%90%E8%A1%8C%E6%A8%A1%E5%BC%8F h_01KJW81RSZPK2Y1PSAF9FSMXB6=%E5%85%B3%E4%BA%8E%E6%B5%8B%E9%87%8F%E8%BF%90%E8%A1%8C%E6%A8%A1%E5%BC%8F live-vs-historical-measurements=%E5%AE%9E%E6%97%B6%E4%B8%8E%E5%8E%86%E5%8F%B2%E6%B5%8B%E9%87%8F h_01KJW81RSZBG5ZC8HE9WFXE34D=%E5%AE%9E%E6%97%B6%E4%B8%8E%E5%8E%86%E5%8F%B2%E6%B5%8B%E9%87%8F choose-the-measurement-you-need=%E9%80%89%E6%8B%A9%E6%82%A8%E9%9C%80%E8%A6%81%E7%9A%84%E6%B5%8B%E9%87%8F h_01KJW81RSZQG21Z0MRHWPMD69F=%E9%80%89%E6%8B%A9%E6%82%A8%E9%9C%80%E8%A6%81%E7%9A%84%E6%B5%8B%E9%87%8F run-a-live-measurement=%E8%BF%9B%E8%A1%8C%E5%AE%9E%E6%97%B6%E6%B5%8B%E9%87%8F h_01KJW81RT0Q1RWEHZP66B5141M=%E8%BF%9B%E8%A1%8C%E5%AE%9E%E6%97%B6%E6%B5%8B%E9%87%8F h_01KJW81RT0N37ARE5570X7MYJF=%E6%B3%A8%E6%84%8F run-a-historical-measurement=%E8%BF%90%E8%A1%8C%E5%8E%86%E5%8F%B2%E6%B5%8B%E9%87%8F h_01KJW81RT0QECMGBTRFSETA5A8=%E8%BF%90%E8%A1%8C%E5%8E%86%E5%8F%B2%E6%B5%8B%E9%87%8F manage-measurements=%E7%AE%A1%E7%90%86%E8%A1%A1%E9%87%8F h_01KJW81RT046RE5FVHPGEDMCC5=%E7%AE%A1%E7%90%86%E8%A1%A1%E9%87%8F the-collaboration-measurement-page=%E5%8D%8F%E4%BD%9C%E6%B5%8B%E9%87%8F%E9%A1%B5%E9%9D%A2 h_01KJWNTR04PRG54W0GZVGQY72X=%E5%8D%8F%E4%BD%9C%E6%B5%8B%E9%87%8F%E9%A1%B5%E9%9D%A2 legend=%E5%9B%BE%E4%BE%8B h_01KJWNF8NAJ9NT5T8NAVTCMZVA=%E5%9B%BE%E4%BE%8B h_01KJW81RT0A148W49X0BR0V9YM=pause-or-restart-live-measurement h_01KJW81RT0GYDCZCXXV2G5EJD7=change-measurement-start-and-end-dates h_01KJW81RT054CCYMTKFN7TS1XV=rerun-a-historical-measurement h_01KJW81RT0RKQJRCTRVP36YBKV=duplicate-a-live-or-historical-measurement h_01KJW81RT0C3R95JQVPGSZ043B=share-a-dashboard" />

---
title: 作弊防护操作台
metadata:
  keywords:
    - Marketers
    - Beta feature
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2024-12-08T06:38:30Z'
  edited_at: '2026-10-14T10:07:34Z'
  id: 30754984040977
  locale: zh-cn
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/zh-cn/articles/30754984040977
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

<Image align="center" alt="beta_feature.png" src="https://files.readme.io/d57432ddeb4d168760f9acd97f4287473658a8528edc1114ecee8ee2f8e9c9b2-16484830033425.png" width="805px" />

> **概要：** Protect360的作弊防护操作台（简称FPS）能让广告主自主管控假量检测的生效方式，与常规模式相比提供更高的自由度。FPS配置针对假量检测数据提供多种可选的处理方式，包括拦截、上报为假量或进行流量标记，让广告主能够按需定制假量管理方式。

<div id="about-fraud-protection-studio" />

## 作弊防护操作台简介

我们在FPS中引入了一个新的检测状态，即“已标记”。

这一状态信息能让广告主在检测假量的同时关闭相关数据的自动处理，带来以下优势：

* 提前评估：在假量处理逻辑正式生效之前，先评估更新后的检测方式对业务的影响。
* 自主管控：根据您的业务模式和需求实施定制化的检测结果处理方式。
* 数据透明：您可以通过已标记的数据深入了新增的假量防护机制。

<div id="important" />

> 🚧 **重要提示！**
>
> 只有行政、市场负责人、团队经理和安全人员 <Anchor target="_blank" href="/marketers/zh/docs/user-management#管理角色">权限角色</Anchor> 能够访问欺诈保护工作室。

<div id="how-the-fraud-protection-studio-works" />

## 作弊防护操作台的原理

<div id="key-concepts" />

<Accordion title="核心理念">

<div id="fps-modes" />

#### FPS模式

FPS有两种模式，**已实施**和**已标记**。广告主可以根据自己的业务目标在两者之间进行切换，确保假量检测机制贴合其具体需求。

<strong>在当前的假量检测机制中，</strong>激活流量的归类分为以下两种：

* **有效**转化
* **检测到的假量**
  * 实时**拦截**
  * 作为归因后识别的假量**上报**

<Image align="center" alt="Image description" src="https://files.readme.io/86996ca9cf4fb83b5cfa24473a302d4e978732495348e3e7432ca2117d1f03c9-30885578633745.png" width="75%" />
<strong>在FPS检测机制中，</strong>激活流量的归类分为以下两种：

* **有效**转化
* **检测到的假量**，此时
  * 仍可作为**有效**转化纳入归因流程，并进行**标记**
  * **或实施假量处理**
    * 实时**拦截**
    * 作为归因后识别的假量**上报**

<Image align="center" alt="Image description" src="https://files.readme.io/465289666e54257f02cfe0a3b34a765e7109426c1f6438f455613cc53351e4f4-31990048826513.png" width="75%" />

<div id="note" />

> 📘 **注意**
>
> 在标记模式下，AppsFlyer会对检测到的所有假量进行标记，但仍按照客户的配置将这些数据保留在有效转化中，并从套餐额度中扣除这些转化，不予返还。

<div id="where-is-tagged-detection-reflected" />

#### 查看已标记的检测结果

已标记的检测结果不会呈现在假量报告中。您可以在下列常规归因报告以及Protect360面板中查看已标记的检测结果：

**报告**：

* 实时标记的激活
* 归因后标记的激活
* 实时标记的应用内事件
* 归因后标记的应用内事件

**Protect360面板**：

<Image align="center" alt="example10.png" src="https://files.readme.io/cf4c836ee78519bd0723bcc1fafb202110fa014be1582853646261d89eb37104-48783289649937.png" width="50%" />

* 页面上方显示已标记的数据总量（1）
* 一段时间内的“检测状态”变化趋势（2）
* 已识别的假量，可按“标记类型”、“标记原因”、“详细标记原因”分组（3）

</Accordion>

<div id="how-to-use-fraud-protection-studio" />

## 作弊防护操作台的使用方式

<div id="general" />

<Accordion title="总体介绍">

FPS是一个配置页面，您可以通过该页面指定检测结果的处理方式，即[实施或标记](/docs/beta-fraud-protection-studio#fps模式)。您可以通过以下各项界定标记要求：

* 检测状态数据
* 实施和标记之间的切换

启用方式：

1. 登入AppsFlyer。
2. 在面板左侧的菜单栏中点击**配置 > Protect360 > 作弊防护操作台**。
3. 使用页面顶部的应用下拉菜单，选择您想要配置的应用。
4. 从左侧菜单栏中选择相关的选项卡。目前有以下选项可用：
   * [点击撞库](/docs/beta-fraud-protection-studio#click-flood-detection)
   * [最新发布](/docs/beta-fraud-protection-studio#new-releases)

</Accordion>

<div id="click-flood-detection" />

<Accordion title="点击撞库检测">

您可以通过FPS管理点击撞库检测的处理方式，操作简单且可按需定制。该页面能让您在应用层级启用点击撞库检测的标记（对所有渠道生效）并在专用报告中呈现已标记的撞库检测数据。

进入点击撞库页面后，您可以[检查并调整检测状态](/docs/beta-fraud-protection-studio#点击撞库选项卡的访问方式)（在“已实施”和“已标记”之间切换），并查看[当前检测状态](/docs/beta-fraud-protection-studio#analyze-click-flood-by-media-source)的数据

下载点击撞库报告数据样例

<div id="important-2" />

<div id="important-1" />

> 🚧 **重要提示！**
>
> * 选择标记检测结果后，所有检测结果都会通过原始数据报告上报，而不会呈现在假量报告中。
> * 您可以针对具体应用配置点击撞库的标记，可关闭实时拦截或归因后的处理。也就是说，配置标记模式后，您的自然和非自然激活数据可能会遭受假量侵蚀。

<div id="how-to-access-click-flood" />

#### 点击撞库选项卡的访问方式

1. 登入AppsFlyer。
2. 在面板左侧的菜单栏中点击**配置 > Protect360 > 作弊防护操作台**。
3. 使用页面顶部的应用下拉菜单，选择您想要配置的应用。
4. 从左侧菜单栏中选择**点击撞库**选项卡。

<div id="click-flood-page" />

### 点击撞库页面

点击撞库页面分为三个部分。

检测状态

[当前检测状态](/docs/beta-fraud-protection-studio#当前检测状态)

<div id="detection-status" />

#### 检测状态

* [检测状态](/docs/beta-fraud-protection-studio#点击撞库选项卡的访问方式) - 可供您选择[检测](/docs/beta-fraud-protection-studio#fps模式)模式，即**已实施**或**已标记**
* [当前检测状态](/docs/beta-fraud-protection-studio#当前检测状态) - 显示启用点击撞库后可能对激活和相关事件数据产生的影响（基于上周之前的7天内数据）。该板块中包含以下几个部分：
  * 当前检测微件
  * 点击撞库检测细分微件
  * 分媒体渠道的点击撞库微件

<div id="how-to-adjust-the-detection-status" />

#### **检测状态的调整方式**

您可在“检测状态”部分选择[检测](/docs/beta-fraud-protection-studio#fps模式)模式，即**已实施**或**已标记**。

1. 在“点击撞库”窗口中，选择[检测模式](/docs/beta-fraud-protection-studio#fps模式)。
2. 点击页面底部的**保存**按钮。

   <Image align="center" alt="可放大的图像" src="https://files.readme.io/c472a15b2775d97c097196d2ce97d59f997219beb44c662a7c7a0e1c17682fb6-31776609579025.png" width="1906px" />

<div id="current-detection-status" />

#### **当前检测状态**

当前检测状态部分显示的预估数据以上周之前7天的数据为基准。

当前检测状态部分呈现以下内容：

* 当前检测微件
* 点击撞库检测细分微件
* 分媒体渠道的点击撞库微件

**当前检测微件**

* **总体激活**——应用激活总量
* **点击撞库检测量**——检测到的点击撞库总数
* **总体检测量**（不含点击撞库）——不包括点击撞库的作弊检测总量
* **总体检测量**（含点击撞库）——包括点击撞库在内的作弊总量。计算方式：点击撞库检测量 + 不含点击撞库的总体检测量

**点击撞库检测细分微件**

这部分显示按自然和非自然激活细分的点击撞库检测数据。

**分媒体渠道的点击撞库微件**

这部分显示按媒体渠道细分的点击撞库检测数据。

请注意：如需更为详尽的报告，请点击**导出**按钮，下载CSV格式的检测指标数据，用于离线分析。

</Accordion>

<div id="new-releases" />

<Accordion title="最新发布">

您可以通过最新发布页面在正式启用假量检测更新前评估其对业务的影响。所有新上线的假量检测更新包都默认使用标记模式，这是为了留出时间，以便您评估假量检测对业务目标的影响，并进行相应的调整。

下载“最新发布”的报告数据样例

<div id="note-1" />

> 📘 **注意**
>
> 我们会将一个或多个检测更新组合起来一起发布，即检测更新包。

<div id="how-this-works" />

#### 作用原理

* AppsFlyer将假量检测更新组合为更新包。
* 假量检测更新包在[标记模式](/docs/beta-fraud-protection-studio#fps模式)中启动。
* 对于最新发布的更新包，其标记模式最长可以设置为14天。
* 对于当前已生效的更新包，您可以进行评估并启用。
* 发布更新包时，通知铃铛图标会显示新消息，提醒您查看更新。

<div id="how-to-access-new-releases" />

#### 最新发布板块的访问方式

1. 登入AppsFlyer。
2. 在面板左侧的菜单栏中点击**配置 > Protect360 > 作弊防护操作台**。
3. 使用页面顶部的应用下拉菜单，选择您想要配置的应用。
4. 从左侧菜单栏中选择**最新发布**选项卡。

<div id="new-releases-page" />

### 最新发布页面

最新发布页面分为以下两个部分：

* [未发布](/docs/beta-fraud-protection-studio#最新发布板块的访问方式)——您可以在更新包正式生效之前标记检测结果（最长14天），评估其业务影响。
* [已发布](/docs/beta-fraud-protection-studio#当前已生效更新包的评估和启用)——对于当前已生效的更新包，您可以监测其检测效果，以便评估和启用。

<div id="how-to-set-the-tagged-mode-time-period-for-future-packages" />

#### 针对未发布的更新包设置标记模式的时长

您可以在“未发布”部分中设定未来更新包处于[标记](/docs/beta-fraud-protection-studio#fps模式)模式天数。设置方式如下：

1. 进入“最新发布”窗口，从下拉菜单中选择您想要让未来更新包在正式生效前处于标记模式的天数（默认为14天，最长可调节到14天）。
2. 点击**保存**。

<Image align="center" alt="futrele.png" src="https://files.readme.io/eb832fdacd720f273a5ac26bc8e08fe1d215a99e477ff3bcfe3b91d46c41234a-31500353666321.png" width="2142px" />

<div id="note-2" />

> 📘 **注意**
>
> * 该设置仅对未来的更新包生效。当前已生效的更新包不会延迟生效或发生变更。
> * 如果在下拉框中选择0天，相当于选择[立即实施](/docs/beta-fraud-protection-studio#启用处于标记模式的已发布更新包)，并且会覆盖此更新包的[未发布](/docs/beta-fraud-protection-studio#最新发布板块的访问方式)设置。

<div id="how-to-evaluate-and-implement-current-active-packages" />

#### 当前已生效更新包的评估和启用

您可以在“最新当前发布”部分中看到以下内容：

* 最新发布的更新包
* 发布日期
* 状态——该更新包正式生效的时间（若处于标记模式）
* 相关指标，用于说明该更新包可能对您的数据产生的影响
* 导出详细报告
* 跳过“未发布”设置，直接立即使用此更新包。

<div id="to-implement-the-current-package-if-in-tagged-status" />

#### 启用处于标记模式的已发布更新包

1. 在FPS选项卡中打开**最新发布**窗口。
2. 使用该数据表以及可导出的报告监测假量检测效果。
3. 准备就绪后，点击**立即实施**，启用更新。  
   <Image align="center" alt="" src="https://files.readme.io/4c11614b4f74ffa435e75cb7e79ef4f61ac750f5bc49331387b45a0ceb83e0da-31776606696081.png" />

<div id="note-3" />

> 📘 **注意**
>
> 该设置会覆盖相关更新包的[未发布](/docs/beta-fraud-protection-studio#最新发布板块的访问方式)设置。

</Accordion>

<div id="app-detection-evaluation" />

<Accordion title="应用检测评估">

应用检测评估卡允许您根据业务目标更改检测状态。这里的决策在应用层面生效，影响所有广告主的合作伙伴。

在应用检测评估卡上标记检测会影响所有Protect360逻辑。然而，由你定义的验证规则触发的检测不会受到影响。除非你手动停用相应的验证规则，否则这些检测会保持“已实施”状态。

进入点击撞库页面后，您可以检查并调整检测状态（在“已实施”和“已标记”之间切换），并查看[当前检测状态](/docs/beta-fraud-protection-studio#点击撞库选项卡的访问方式)的数据

> 🚧 **重要提示！**
>
> * 选择标记检测结果后，所有检测结果都会通过原始数据报告上报，而不会呈现在假量报告中。
> * 应用检测评估的标签是在应用层面进行，可以防止Protect360逻辑的阻断或归因后实现。也就是说，配置标记模式后，您的自然和非自然激活数据可能会遭受假量侵蚀。
> * 任何定义并激活的验证规则都会始终保持在实现模式。要暂停任何验证规则的实施，请访问验证规则页面并在那里将其停用.

<div id="how-to-access-app-detection-evaluation" />

#### **如何访问应用检测评估**

1. 登录AppsFlyer。
2. 在面板左侧的菜单栏中点击配置 > Protect360 > 作弊防护操作台。
3. 使用页面顶部的应用下拉菜单，选择您想要配置的应用。
4. 在左侧菜单中，选择 **应用检测评估** 卡片。

<div id="app-detection-evaluation-page" />

#### 应用检测评估

应用检测评估页面分为两个部分。

* [检测状态](/docs/beta-fraud-protection-studio#点击撞库选项卡的访问方式) - 可供您选择检测模式，即已实施或[已标记](/docs/beta-fraud-protection-studio#fps模式)
* [当前检测状态](/docs/beta-fraud-protection-studio#当前检测状态) - 显示当前检测对安装的影响及相关事件，基于上周前的7天。该板块中包含以下几个部分：
  * **Protect360 逻辑**   
    已实施的检测
    * **实施率** - 速率表示（*Protect360 逻辑实现的逻辑量*）除以（*该应用的总归属*).
  * 应用层级  
    标记检测模式：
    * **标签率** - 速率表示（*应用检测评估标签所标记的逻辑量*）除以（*该应用的总归属*)
  * 总激活量
  * **总检测次数**
  * **实现的检测** - 在决定更改 [检测状态](/docs/beta-fraud-protection-studio#点击撞库选项卡的访问方式) 从实现到标记
    * Protect360 逻辑——这显示了检测有多少是由 Protect360 逻辑完成的。切换为带标签检测时——这是预期的检测量，将转换为带标签检测
    * 验证规则——显示检测中有多少是基于你定义并激活的验证规则。如果你将检测模式改为标记，基于规则的验证检测将保持在已实现的模式中。
  * **标记检测** - 在决定更改 [检测状态](/docs/beta-fraud-protection-studio#点击撞库选项卡的访问方式) 从标签到实施。你将反映所有标记原因，以反映预期结果，然后再将检测状态从标记状态改为已实现 
    * 应用层面——这个KPI让你了解被标记的部分内容是应用检测评估卡的标签造成的。KPI中反映的数字是实施检测状态后预期的增长。
    * 其他标签——你可以在防欺诈工作室中为多种功能（卡片）标记检测。

<div id="how-to-adjust-the-detection-status-1" />

#### 检测状态的调整方式

检测状态允许你选择 [检测](/docs/beta-fraud-protection-studio#fps模式) 模式。你可以选择实现和标记（默认是实现）

1. 在应用检测评估页面，选择 [探测模式](/docs/beta-fraud-protection-studio#fps模式).
2. 点击页面底部的保存按钮。

</Accordion>

<div id="reengagement-hijacking-detection" />

<Accordion title="重新交战劫机侦测">

Protect360中的再参与劫持检测扩展了针对重新参与活动的标准欺诈检测覆盖范围。这种检测增强了你对欺诈管理的控制力。

默认情况下，该检测在 [标记模式](/docs/beta-fraud-protection-studio#fps模式)，允许您在实施前评估其有效性和潜在影响。

<div id="how-this-works-1" />

#### 作用原理

* 重新交战劫机检测默认设置为标记模式。你可以在不影响实时归因数据的情况下评估其检测性能。
* 实施后，检测发生在归因后，即欺诈性重新参与被识别并从归因记录中删除。
* 实现后，检测移除后的所有应用内事件将重新归因于原始用户获取（UA）提供商，或如果没有有效的用户获取提供商，则标记为自然事件。

<div id="how-to-access" />

#### 访问方式

1. 登录AppsFlyer。
2. 在面板左侧的菜单栏中点击**配置 > Protect360 > 作弊防护操作台**。
3. 通过顶部的应用下拉菜单选择你想配置的应用。
4. 从左侧菜单中选择 **重新交战劫机** 卡片。

<div id="re-engagement-hijacking-page" />

#### 重新参与劫持页面

重新参与劫持页面分为两个部分。

* [检测状态](/docs/beta-fraud-protection-studio#点击撞库选项卡的访问方式) - 允许您选择 [检测](/docs/beta-fraud-protection-studio#fps模式) 模式。你可以选择实现型和标记型
* [当前检测状态](/docs/beta-fraud-protection-studio#当前检测状态) - 展示了启用Re-engagement hijacking会如何影响你的安装和相关事件，基于过去14天（不包括当天）。  
  **注意：** 由于再参与劫机检测是在归因后运行的，过去7天的数据可能为部分，并会持续追溯更新。  

  该板块中包含以下几个部分：
  * 重新交战劫机检测小部件
    * 探测次数——仅凭重新交战劫持逻辑检测到的次数
    * 检测率——重新交战劫机检测中被重新交战检测排除的百分比
  * 总重新接入检测小部件——所有逻辑的整体重新接入检测量
  * 再参与归因卷小部件
    * 归因——时间范围内的再参与归因量
    * 总归因中的排名——所有应用归因中再参与归因的比例
  * 媒体来源的再参与检测——最高检测媒体来源的再参与劫持检测次数

<Image align="center" alt="" src="https://files.readme.io/bab73f39f3792401dd8795a78c64d88c26d075cdb7d693a5871bba668495f8d1-35682380370321.png" width="624px" />

</Accordion>

<div id="inapp-based-detection" />

<Accordion title="基于应用内的作弊监测">

基于应用的检测通过分析应用内行为异常，确定性地将安装标记为欺诈。它识别出复杂的欺诈手法，比如模拟真实互动但安装后显示异常事件流和时间模式的机器人。

#### 访问方式

1. 登入AppsFlyer。
2. 在面板左侧的菜单栏中点击**配置 > Protect360 > 作弊防护操作台**。
3. 使用页面顶部的应用下拉菜单，选择您想要配置的应用。
4. 在左侧菜单中，选择 **基于应用的检测** 卡片。

<div id="the-in-app-based-detection-page" />

#### 基于应用的检测页面

应用内的基地检测页面分为两个部分。

* [检测状态](/docs/beta-fraud-protection-studio#点击撞库选项卡的访问方式) - 允许您选择 [检测](/docs/beta-fraud-protection-studio#fps模式) 模式。你可以选择实现型和标记型。
* [当前检测状态](/docs/beta-fraud-protection-studio#当前检测状态) - 展示了启用基于应用的检测功能，基于过去14天（不包括当天）对你的安装结果的影响。   

  注意：由于基于应用的检测是在归因后进行的，过去7天的数据可能为部分，并会持续追溯更新。

该板块中包含以下几个部分：

* **基于应用内逻辑的新检测**
  * 检测——应用内逻辑检测到的安装数量
  * 附加值率—— 基于应用内的检测结果除以应用的总安装量
* **识别出的虚假激活**
  * 检测——假检测总数
  * 检测率——假检测数除以应用总安装量
* **总激活量**

* **基于应用的媒体源检测** - 顶级媒体来源的安装数量。

<Image align="center" alt="" src="https://files.readme.io/63eedf0c4aa28471d4044a8896e349612fb9d8e9f06aed6b1efbaa825330d150-36947287654033.png" width="624px" />

</Accordion>

<div id="h_01K0ASM01ADVSECMOD01" />

<Accordion title="高级安全模块">

实时审查安卓应用中安装候选网络攻击的高级安全模块检测数据。这有助于确保只有经过验证的流量才能到达你的应用。

<div id="how-to-access-2" />

<div id="how-to-access-1" />

#### 访问方式

1. 登入AppsFlyer。
2. 在面板左侧的菜单栏中点击**配置 > Protect360 > 作弊防护操作台**。
3. 使用页面顶部的应用下拉菜单，选择您想要配置的应用。
4. 在左侧菜单中，选择 **高级安全模块** 卡片。

<div id="the-advanced-security-module-page" />

#### 高级安全模块页面

高级安全模块页面显示：

* **顶级应用版本** ——按安装量排名前五的应用版本，以便你识别伪造流量的集中地点。

检测结果通常以以下方式之一显示：

* **被封锁** ——在归属前实时停止了交通。
* **标签** —— 流量被标记为可疑但仍有归属，所以你可以在执行前审核。这是默认的检测模式。
* **未标记** ——安装模块未标记的候选方案。

<div id="note-4" />

> 📘 **注意**
>
> 有关完整设置、需求和详细报告，请参见 <Anchor target="_blank" href="/marketers/zh/docs/beta-advanced-security-protect360-module">[测试版]高级安全保护360模块</Anchor>.

</Accordion>

<div id="faqs" />

## 常见问题解答

<div id="can-i-tag-detection-for-specific-partnersmedia-sources" />

<Accordion title="能否为渠道配置检测标记？">

取决于具体的检测类型。比如对于劫持类的检测，广告主无法为渠道配置检测标记，这是为了避免出现带有倾向性的检测结果。

<div id="what-happens-when-the-tagging-period-ends" />

<Accordion title="标记周期结束后会发生什么变化？">

评估周期结束时，标记模式会自动切换为实施模式。

</Accordion>

<div id="where-can-i-see-tagged-installs" />

<Accordion title="如何查看已标记的激活？">

带标记的数据可在以下报告中获得。 **原始数据报告**:

* 已标记的激活
  * 实时数据
* 已标记的激活
  * 归因后被识别为假量的激活
* 已标记的应用内事件
  * 实时数据
* 已标记的应用内事件
* 归因后被识别为假量的激活

以下带标签的报告也可在 **数据存储器**:

* 已标记的激活
  * 实时数据
* 已标记的应用内事件
  * 实时数据

</Accordion>

<div id="can-tagged-detection-be-adjusted-for-appspecific-settings" />

<Accordion title="是否可针对具体应用调整检测标记配置？">

可以，点击撞库标记是应用层级的配置。

</Accordion>

<div id="can-i-see-tagged-inapp-events" />

<Accordion title="是否可查看已标记的应用内事件？">

是如果应用内事件与某个已标记的激活相关具有同一个AppsFlyer ID，则该事件也会被标记。

</Accordion>

<div id="who-can-change-set-up-or-view-fps" />

<Accordion title="更改、设置和查看FPS需要哪些权限？">

仅有管理员可以更改FPS的配置。FPS的查看权限已<Anchor target="_blank" href="/marketers/zh/docs/manage-data-access-permissions">权限页面</Anchor>中的配置为准。

</Accordion>

<div id="are-tagged-installs-credited-back-to-the-consumption-plan" />

<Accordion title="已标记的激活是否会返还到套餐额度？">

已标记激活的对应额度不会返还到套餐中。

</Accordion>

<div id="are-tagged-installs-considered-as-fraud" />

<Accordion title="已标记的激活是否视为假量？">

已标记的激活是由Protect360检测到的流量，但AppsFlyer会依照客户配置的要求对其进行标记。因此，在数据总览和Protect360面板中，这些激活都会呈现在已归因的指标中。

</Accordion>

<div id="can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />

<Accordion title="是否能查看仅通过点击撞库标记机制的标记到的激活数量？">

是您可以使用数据导出页面和Protect360面板，在新推出的专用报告中看到这些数据。

</Accordion>

</Accordion>

<div data-zendesk-anchors="why-flexible-protection=%E4%BD%9C%E5%BC%8A%E9%98%B2%E6%8A%A4%E6%93%8D%E4%BD%9C%E5%8F%B0%E7%AE%80%E4%BB%8B 01JEQR86DC1CK03DKCZH760N4M=%E4%BD%9C%E5%BC%8A%E9%98%B2%E6%8A%A4%E6%93%8D%E4%BD%9C%E5%8F%B0%E7%AE%80%E4%BB%8B h_01JK3BGVNMYFQYQGRPJBVN2A7Z=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA how-flexible-protection-works=%E4%BD%9C%E5%BC%8A%E9%98%B2%E6%8A%A4%E6%93%8D%E4%BD%9C%E5%8F%B0%E7%9A%84%E5%8E%9F%E7%90%86 01JEQR86DEG7RTRNYFP02WHJGQ=%E4%BD%9C%E5%BC%8A%E9%98%B2%E6%8A%A4%E6%93%8D%E4%BD%9C%E5%8F%B0%E7%9A%84%E5%8E%9F%E7%90%86 01JETRN5S347ZXV8CGZJDHQH56=key-concepts fps-modes=fps%E6%A8%A1%E5%BC%8F h_01JEWZEBBA9VAPCKR87NJ5AK3C=fps%E6%A8%A1%E5%BC%8F 01JEWZQ7PBD6W4J15W0HE2Q4MJ=%E6%B3%A8%E6%84%8F where-is-tagged-detection-reflected=%E6%9F%A5%E7%9C%8B%E5%B7%B2%E6%A0%87%E8%AE%B0%E7%9A%84%E6%A3%80%E6%B5%8B%E7%BB%93%E6%9E%9C 01JEWZT9N34FZ9SE8H7EGCMPBZ=%E6%9F%A5%E7%9C%8B%E5%B7%B2%E6%A0%87%E8%AE%B0%E7%9A%84%E6%A3%80%E6%B5%8B%E7%BB%93%E6%9E%9C how-to-use-flexible-protection=%E4%BD%9C%E5%BC%8A%E9%98%B2%E6%8A%A4%E6%93%8D%E4%BD%9C%E5%8F%B0%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F 01JEQR86ECSYTM7RN3YPYRSAGE=%E4%BD%9C%E5%BC%8A%E9%98%B2%E6%8A%A4%E6%93%8D%E4%BD%9C%E5%8F%B0%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F 01JETF4NJX02APNK1TDV91JQAB=general 01JETF4NJZ7P5M5RTCEFFD0WEP=click-flood-detection 01JFSPDB630RE494JG1W618TKR=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 adjust-detection-status=%E7%82%B9%E5%87%BB%E6%92%9E%E5%BA%93%E9%80%89%E9%A1%B9%E5%8D%A1%E7%9A%84%E8%AE%BF%E9%97%AE%E6%96%B9%E5%BC%8F 01JEQVJS6YTQD299X39Q8E3506=%E7%82%B9%E5%87%BB%E6%92%9E%E5%BA%93%E9%80%89%E9%A1%B9%E5%8D%A1%E7%9A%84%E8%AE%BF%E9%97%AE%E6%96%B9%E5%BC%8F click-flood-page=%E7%82%B9%E5%87%BB%E6%92%9E%E5%BA%93%E9%A1%B5%E9%9D%A2 h_01JJKE1ZKE5WDRSPKS8JE9MRRG=%E7%82%B9%E5%87%BB%E6%92%9E%E5%BA%93%E9%A1%B5%E9%9D%A2 detection-status=%E6%A3%80%E6%B5%8B%E7%8A%B6%E6%80%81 h_01JZQ81MW4HMY9B782Y7PWVE8Y=%E6%A3%80%E6%B5%8B%E7%8A%B6%E6%80%81 h_01JJKE1ZKEJ4QM2HTT37FERA92=%E6%A3%80%E6%B5%8B%E7%8A%B6%E6%80%81%E7%9A%84%E8%B0%83%E6%95%B4%E6%96%B9%E5%BC%8F current-detection-status=%E5%BD%93%E5%89%8D%E6%A3%80%E6%B5%8B%E7%8A%B6%E6%80%81 01JEQVZCNSTXY4V8H2Y1QP224C=%E5%BD%93%E5%89%8D%E6%A3%80%E6%B5%8B%E7%8A%B6%E6%80%81 01JETF4NK2KT4MY2G6WMWGMVKB=new-releases 01JFQPRZ5NGEAFBWB1FS0D6DCT=%E6%B3%A8%E6%84%8F-1 how-this-works=%E4%BD%9C%E7%94%A8%E5%8E%9F%E7%90%86 h_01JEXC0ABSTCEA939DGQ5SDJBJ=%E4%BD%9C%E7%94%A8%E5%8E%9F%E7%90%86 how-to-set-the-tagged-mode-time-period-for-future-packages=%E6%9C%80%E6%96%B0%E5%8F%91%E5%B8%83%E6%9D%BF%E5%9D%97%E7%9A%84%E8%AE%BF%E9%97%AE%E6%96%B9%E5%BC%8F h_01JEXC2HAR2S6BWK28N8W3HHSZ=%E6%9C%80%E6%96%B0%E5%8F%91%E5%B8%83%E6%9D%BF%E5%9D%97%E7%9A%84%E8%AE%BF%E9%97%AE%E6%96%B9%E5%BC%8F new-releases-page=%E6%9C%80%E6%96%B0%E5%8F%91%E5%B8%83%E9%A1%B5%E9%9D%A2 h_01JJKE1ZKE0K1W2VE3KHQ639B1=%E6%9C%80%E6%96%B0%E5%8F%91%E5%B8%83%E9%A1%B5%E9%9D%A2 h_01JJKE1ZKE13D7EC6BMN3JJNGW=%E9%92%88%E5%AF%B9%E6%9C%AA%E5%8F%91%E5%B8%83%E7%9A%84%E6%9B%B4%E6%96%B0%E5%8C%85%E8%AE%BE%E7%BD%AE%E6%A0%87%E8%AE%B0%E6%A8%A1%E5%BC%8F%E7%9A%84%E6%97%B6%E9%95%BF 01JF50BVZ75ZSXTJEKAV4HVSTZ=%E6%B3%A8%E6%84%8F-2 how-to-evaluate-and-implement-current-active-packages=%E5%BD%93%E5%89%8D%E5%B7%B2%E7%94%9F%E6%95%88%E6%9B%B4%E6%96%B0%E5%8C%85%E7%9A%84%E8%AF%84%E4%BC%B0%E5%92%8C%E5%90%AF%E7%94%A8 h_01JEXC3DESR10WVV34ED30B7BH=%E5%BD%93%E5%89%8D%E5%B7%B2%E7%94%9F%E6%95%88%E6%9B%B4%E6%96%B0%E5%8C%85%E7%9A%84%E8%AF%84%E4%BC%B0%E5%92%8C%E5%90%AF%E7%94%A8 to-implement-the-current-package-if-in-tagged-status=%E5%90%AF%E7%94%A8%E5%A4%84%E4%BA%8E%E6%A0%87%E8%AE%B0%E6%A8%A1%E5%BC%8F%E7%9A%84%E5%B7%B2%E5%8F%91%E5%B8%83%E6%9B%B4%E6%96%B0%E5%8C%85 h_01JF505FK4NP88WYXP8PVQRYDS=%E5%90%AF%E7%94%A8%E5%A4%84%E4%BA%8E%E6%A0%87%E8%AE%B0%E6%A8%A1%E5%BC%8F%E7%9A%84%E5%B7%B2%E5%8F%91%E5%B8%83%E6%9B%B4%E6%96%B0%E5%8C%85 01JF50BVZ9QPT5W41P8KQAREKV=%E6%B3%A8%E6%84%8F-3 h_01JQXFMBGXWKXMFFAPHN5V66Q7=app-detection-evaluation h_01JQXPVD4MXPYQQZXNTM2H9BNA=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2 how-to-access-app-detection-evaluation=%E5%A6%82%E4%BD%95%E8%AE%BF%E9%97%AE%E5%BA%94%E7%94%A8%E6%A3%80%E6%B5%8B%E8%AF%84%E4%BC%B0 h_01JQXG4GJ2DB8HM26K3E1WA3A1=%E5%A6%82%E4%BD%95%E8%AE%BF%E9%97%AE%E5%BA%94%E7%94%A8%E6%A3%80%E6%B5%8B%E8%AF%84%E4%BC%B0 app-detection-evaluation-page=%E5%BA%94%E7%94%A8%E6%A3%80%E6%B5%8B%E8%AF%84%E4%BC%B0 h_01JQXG6QDSTAPCJDMQVQMXS86W=%E5%BA%94%E7%94%A8%E6%A3%80%E6%B5%8B%E8%AF%84%E4%BC%B0 how-to-adjust-the-detection-status=%E6%A3%80%E6%B5%8B%E7%8A%B6%E6%80%81%E7%9A%84%E8%B0%83%E6%95%B4%E6%96%B9%E5%BC%8F-1 h_01JQXG6QEAM0Y67G504JV2SA5R=%E6%A3%80%E6%B5%8B%E7%8A%B6%E6%80%81%E7%9A%84%E8%B0%83%E6%95%B4%E6%96%B9%E5%BC%8F-1 h_01JWAVMSW1K6R4FJ8J9AYYNHQW=reengagement-hijacking-detection how-this-works::a0e9054=%E4%BD%9C%E7%94%A8%E5%8E%9F%E7%90%86-1 h_01JWAVPAVKM9RSXFMZN9CM36ER=%E4%BD%9C%E7%94%A8%E5%8E%9F%E7%90%86-1 how-to-access=%E8%AE%BF%E9%97%AE%E6%96%B9%E5%BC%8F h_01JWAVPAVK7ZT471AQAFKAS64K=%E8%AE%BF%E9%97%AE%E6%96%B9%E5%BC%8F reengagement-hijacking-page=%E9%87%8D%E6%96%B0%E5%8F%82%E4%B8%8E%E5%8A%AB%E6%8C%81%E9%A1%B5%E9%9D%A2 h_01JWAVPAVKKB4JSP41P967EESS=%E9%87%8D%E6%96%B0%E5%8F%82%E4%B8%8E%E5%8A%AB%E6%8C%81%E9%A1%B5%E9%9D%A2 h_01JZMAX35E1KT04VTKAFB8FAF3=inapp-based-detection how-to-access::db81debe=%E8%AE%BF%E9%97%AE%E6%96%B9%E5%BC%8F-2 h_01JZMAZET0JXYEDGKE0B797TQ7=%E8%AE%BF%E9%97%AE%E6%96%B9%E5%BC%8F-2 the-inapp-based-detection-page=%E5%9F%BA%E4%BA%8E%E5%BA%94%E7%94%A8%E7%9A%84%E6%A3%80%E6%B5%8B%E9%A1%B5%E9%9D%A2 h_01JZMB0NET3Y8CFVZ1WP0WDPMJ=%E5%9F%BA%E4%BA%8E%E5%BA%94%E7%94%A8%E7%9A%84%E6%A3%80%E6%B5%8B%E9%A1%B5%E9%9D%A2 advanced-security-module=h_01K0ASM01ADVSECMOD01 h_01K0ASM02ADVSECMOD02=%E8%AE%BF%E9%97%AE%E6%96%B9%E5%BC%8F-2 h_01K0ASM07ADVSECMOD07=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%A8%A1%E5%9D%97%E9%A1%B5%E9%9D%A2 the-advanced-security-module-page=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%A8%A1%E5%9D%97%E9%A1%B5%E9%9D%A2 h_01K0ASM13ADVSECMOD13=%E6%B3%A8%E6%84%8F-4 faqs=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01JEQR86EMZQFNSZ5NWZ08F5YQ=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01JETRQMEJHZMHAKHHX5SZ028N=can-i-tag-detection-for-specific-partnersmedia-sources 01JETRQMEKJ27S5GGVR73H6WZB=what-happens-when-the-tagging-period-ends 01JETRQMEMKV8K7EQMS1BJB989=where-can-i-see-tagged-installs 01JETRQMEM6BMEXGYJM6WVE313=can-tagged-detection-be-adjusted-for-appspecific-settings 01JF79M50ZZ7HP0XCW1F4YJH7R=can-i-see-tagged-inapp-events 01JF79M50ZTMM1Y2YW8ARTYVTN=who-can-change-set-up-or-view-fps 01JF79M510HGEVC1WTWXAHSAQH=are-tagged-installs-credited-back-to-the-consumption-plan 01JF79M510B5WW067Q4T4FDVSC=are-tagged-installs-considered-as-fraud 01JF79M5105Z9AH95K6VVANANM=can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />

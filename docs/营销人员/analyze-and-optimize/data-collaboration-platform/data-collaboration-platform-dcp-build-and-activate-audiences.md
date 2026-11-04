---
title: 数据协作平台 (DCP) - 构建和激活受众
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-04-25T12:55:13Z'
  edited_at: '2026-10-14T10:03:19Z'
  id: 24522739719057
  locale: zh-cn
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/zh-cn/articles/24522739719057
---
> **概要：** 使用受众构建工具创建和激活受众。根据必要的权限，受众可以基于双方的组合数据集或仅基于一方的数据集。

> 👍 **关于 DCP**
>
> 数据协作平台 (DCP) 作为数据协作的中心点，包含受众创建和激活。DCP 依赖于数据清理室 (DCR) 的先进技术，以确保协作和受众管理过程中的数据隐私和安全。

<div id="about-dcp-audiences" />

## 速览

从庞大的数据集中构建受众的过程涉及组合数据集以生成丰富的数据，这可以用来精确接触您想要接触的消费者。受众可以使用双方的组合数据集创建，或仅由一方提供。在这两种情况下，提供数据的协作者根据他们商定的条款授予权限和访问权。构建受众后，您可以将其发送给您的媒体合作伙伴进行激活或发送到您的云服务。

## 受众构建工具

以下工具可用于构建您的受众：

* **可视化受众构建器:** 可视化受众构建器是一个用户友好的工具，允许非技术用户在不需要 SQL 技能的情况下创建受众细分。它允许使用图形界面进行高级受众细分。
* **受众构建智能体**： 一个允许无限制查询数据的 SQL 查询。需要 SQL 专业知识。

<div id="key-features" />

<div id="build-an-audience" />

#### 主要功能

| 可视化受众构建器 | 受众构建智能体： |
| --- | --- |
| <span id="supports-using-one-source-from-each-collaborating-party"></span>支持使用每个合作方的一个来源或一个合作方的多个来源 | 支持双方的多个来源 |
| <span id="supports-using-overlapping-data-only"></span>每个协作者一个数据源，仅支持使用重叠数据 | 支持查询所有数据 |
| <span id="supports-retrieving-values-within-the-selected-attribute-range"></span>支持在选定属性范围内检索值。 | 支持查询超出属性范围的值 |

## 建立你的受众

建立受众的步骤根据受众构建工具而异。所以首先，决定使用哪个[受众构建工具](#受众构建工具)：

* [可视化受众构建器](/docs/data-collaboration-platform-dcp-build-and-activate-audiences#visual-audience-builder)
* [SQL受众构建器](#sql-audience-builder)（需要SQL专业知识）

<div id="visual-audience-builder" />

<Accordion title="可视化受众构建器">

**按照以下步骤使用可视化受众构建器构建你的受众：**

<div id="note" />

> 📘 **注意**
>
> 确保你拥有<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">建立受众</Anchor>的权限以创建受众。

1. 在AppsFlyer中，从侧边菜单选择**协作** > **数据清理室**。

   <Image alt="from Collaborate.png" src="https://support.appsflyer.com/hc/article_attachments/32455804422545" width="266px" />
2. 在**协作**选项卡中，点击相关的协作。

   <Image alt="点击相关协作.png" src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. 在协作中，点击**新受众** > **可视化受众构建器**。  
   **请注意：** 在你可以建立受众之前，必须关联至少一个数据源。

   <Image alt="新受众可视化受众构建器.png" src="https://files.readme.io/31458edec870140b9c4eb0805aef0175ca5f3c698b6faa380f979398046eb58b-32455804445201.png" width="355px" />
4. 继续进行以下**受众构建器**的逐步指导：

<div id="step-1-details-and-sources" />

#### 第1步：详细信息和来源

可以使用来自单个协作者的数据创建受众，或通过合并每个协作者的一个数据源来启用组合数据源。

![New aud.png](https://files.readme.io/c110dcda7524ddcb4ce255ac5eb1f33ffec61103219e35f54f1d5687135cf915-35683488156433.png)   

1. audience\_name命名观众协作。
2. 选择数据源从下拉列表中选择一个来源：
   * 对于单向协作：选择您自己的来源或您合作者的来源。
   * 对于双向协作：选择您自己的一个来源和您合作者的一个来源。  
     **请注意：** 当两个来源共享交集用户时，右侧窗格显示来源交集的摘要，提供两个来源共同用户的估计数量。
3. **数据组合方法：** 选择您想要构建观众的数据：
   * **交集用户** - 仅包括出现在两个来源（您的和您合作者的）中的用户。
   * **仅来自我的来源的用户** - 仅包括您来源中独特的用户。排除所有出现在您合作者来源中的用户。
   * **仅来自合作者来源的用户** - 仅包括您合作者关联来源中独特的用户。排除所有出现在您来源中的用户。  

     **请注意：** 只有在来源权限已启用 "**构建观众**" > "**可以使用所有数据** - **通用数据集**" 时，所有三个选项才会可用。<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#共享权限">了解更多关于来源权限的信息</Anchor>  

     <Image alt="可以使用所有数据权限已启用 w arrow.png" src="https://support.appsflyer.com/hc/article_attachments/34588579107345" width="87.42%" />
4. 点击**Next**。

<div id="step-2-define-the-audience" />

#### 第2步：定义受众

在选择数据来源后，此步骤涉及选择要包含在您的观众中的属性和值。

1. 点击 **选择列** 查看来源的属性列表。
2. 选择一个属性、运算符和属性值。
   * **数值和日期属性** 可以使用以下运算符进行过滤：  
     等于、不等于、大于、小于、大于或等于，  
     小于或等于，介于，过去 "X" 天（也可以包括当前一天）
   * **文本属性** 可以使用以下运算符进行过滤：  
     等于或不等于

     <div id="note-2" />

     > 📘 **注意事项**
     >
     > * 如果未选择某个属性，则默认包含所有属性。
     > * 一旦选择了属性值，受众规模将会调整。

3. [可选] 点击 **+ 条件** 添加另一个属性，并选择其值。  
   根据需要重复。
4. 点击**Next**。
5. 继续下一步 [发送受众](#发送受众以进行激活) 以激活受众。

<Image alt="Definetheaudience.png" src="https://files.readme.io/70c93dbb737563f7b62e8a8ba111e7d5e7e1a0fa2697a2be69d5caa579bbf3dc-34588602544017.png" width="75.57%" />

</Accordion>

<div id="sql-audience-builder" />

<Accordion title="受众构建智能体：">

按照以下步骤使用 SQL 受众构建器构建您的受众。

<div id="note-4" />

> 📘 **注意**
>
> 确保你拥有<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">建立受众</Anchor>的权限以创建受众。

1. 在AppsFlyer中，从侧边菜单选择**协作** > **数据清理室**。

   <Image alt="from Collaborate.png" src="https://support.appsflyer.com/hc/article_attachments/32455804422545" width="266px" />
2. 在**协作**选项卡中，点击相关的协作。

   <Image alt="点击相关协作.png" src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. 在协作中，点击 **新受众** > **SQL 受众构建器**。

   <Image alt="新受众 SQL 受众构建器.png" src="https://files.readme.io/e955bdd8a90a92dff5bb695cd64621860e79413f42ac8a8efaefc3cb80d061a5-32455799682193.png" width="355px" />
4. 继续进行 **受众构建器** 的演练步骤：

<div id="set-details" />

#### 设置详细信息

命名受众，然后点击 **下一步**。

<div id="build-query" />

#### 构建查询

1. 点击编辑器以打开 [SQL 构建器](#sql-audience-builder)。
2. 编写您的 SQL 查询以构建您的受众。您可以使用连接或单侧来源。
3. 点击 **测试** 并查看查询语句下方显示的查询结果（受众样本）。
4. 点击 **继续** 然后 **下一步** 以继续进行 **受众构建器** 的下一步演练，或 **保存为草稿** 并稍后继续。
5. 继续 [发送给观众](#发送受众以进行激活)。

<div id="the-sql-audience-builder" />

#### SQL 观众构建器

使用 SQL 构建器查询数据并创建观众。下表概述了构建器中的各个部分：

| 板块 | 说明 |
| --- | --- |
| <span id="left-pane"></span>左侧窗格： | 展示所有可用的来源以创建您的观众。这可能包括您的来源和与您共享的来源。您只能查看您拥有 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">**构建观众**</Anchor> 权限的来源。<br /><br />选择一个来源会展开它以显示相应的列。 |
| <span id="topmiddle-section-text-editor"></span>顶部中间部分（查询编辑器） | 用于编写 SQL 语句的查询编辑器。 |
| <span id="bottommiddle-section-context-panel"></span>底部中间部分（上下文面板） | 此部分根据左侧窗格中选择的对象动态显示详细信息：<ul><li>**选择来源时：** 显示列名（"字段名称"）及其对应的类型（"类型"）。</li><li>**选择列时：** 显示列值（"不同值"）及每个值的行数（"计数"）。</li><li>**查询执行后：** 显示查询结果的示例。<br />**请注意：** 作为隐私措施，结果表不显示哈希值，例如电子邮件和 ID。这些值显示为“受限”。</li></ul> |
| <span id="right-pane"></span>右侧窗格： | 此部分根据所选对象动态显示详细信息：<ul><li>**选择来源时：** 显示源授予的权限。</li><li>**在编写 SQL 查询时：**<ul><li>在页面右上角显示查询有效性状态。这可能包括以下任何状态：<ul><li>**准备运行：** 未发现问题。您可以测试查询并继续下一步。</li><li>**语法错误：** 检测到语法错误，并提供解决该错误的指导。</li><li>**权限错误：** 表示缺少所需权限，工具提示详细说明了为源提供的<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#view-permissions-for-collaborator%E2%80%99s-source">访问权限</Anchor>。</li></ul></li><li>在页面右上角显示一个**测试**按钮。完成查询编写后，您必须测试它以确认目标受众的准确性。<br />点击**测试**以测试您的查询并检查结果。</li></ul></li></ul> |

</Accordion>

<div id="send-an-audience-for-activation" />

## 发送受众以进行激活

当您完成定义受众时，您选择希望将受众发送到的位置（考虑所需的<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#共享权限">权限</Anchor>）。这意味着组成受众的用户 ID 列表会不断刷新，并每天发送到您选择的目的地。提供两个目的地。您可以：

* [**将受众连接到媒体合作伙伴**](#将人群包连接到渠道) - 媒体合作伙伴平台包括 Meta 广告、谷歌广告等。在您想要进行付费活动、再营销或相似受众扩展时，将您的受众连接到媒体合作伙伴。
* [**将受众导出到您的云服务**](#将受众导出到云服务) - 云存储通过 AppsFlyer 数据锁定器进行管理。当您需要在 BI 模型、CDP 或内部丰富管道中使用文件时，将您的受众连接到云服务。

<div id="note-6" />

> 📘 **注意**
>
> * 每次更新源数据时，受众会自动转发到选定的目的地。
> * 发送用于激活的数据是用户 ID 的列表。

#### 将人群包连接到渠道

直接在您首选的媒体合作伙伴平台上发送受众以进行激活，例如 Meta 广告和 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10010286?hl=en">Google Ads</Anchor>。系统会转发用户 ID 的 CSV 文件，如果合作伙伴要求，自动进行哈希处理。

<div id="note-7" />

> 📘 **注意**
>
> 当您没有权限激活受众时，受众会被发送给您的合作者，以便他们在其端进行激活。

**将受众连接到媒体合作伙伴：**

1. 在受众构建器中，启用 **将受众连接到媒体合作伙伴**。  
     
   ![连接受众到媒体合作伙伴.png](https://files.readme.io/d1e6558183eed8f239f1d61efd81cd71db7a2c7f6acfdef7e1c029dea51af172-37184169230097.png)
2. 点击**添加渠道连接**。
3. 如果没有建立合作伙伴连接，请创建一个新的合作伙伴连接：
   1. 点击**Add Connection**。
   2. 选择相关的媒体合作伙伴（Meta 广告、Google 广告、DV360 或 TikTok）。
   3. 输入连接的名称。
   4. 点击 **使用 [合作伙伴名称] 登录**。您将被引导到合作伙伴登录页面。选择接收受众的账户。然后，您将被引导回对话窗口。
   5. 点击 **选择账户 ID** 并选择相关的账户 ID。
   6. 点击**保存**。
4. 点击 **保存并发送**.

<Image alt="选择媒体合作伙伴连接.png" src="https://support.appsflyer.com/hc/article_attachments/35682279443857" width="610px" />

#### 将受众导出到云服务

将受众发送到您的云服务。受众通过您的 <Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">AppsFlyer 数据存储</Anchor> 连接导出到所选的云服务。用户 ID 的 CSV 文件写入您选择的存储桶。

* 请注意<strong>：</strong>使用 AppsFlyer 数据存储接收 DCR 受众不需要 Data Locker 的高级订阅。如果您需要通过Data Locker接收其他的AppsFlyer报告，请联系您的CSM或发送邮件至hello@appsflyer.com咨询详情。

**将受众发送到您的云服务：**

1. 在受众构建器中，打开 **导出受众到云**。  
     
   将受众导出到云端
2. 点击 **选择连接** 从列表中选择现有的云连接以发送受众，或点击 **+ 新连接** 来 <Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers#set-up-data-locker">在数据存储中创建新连接</Anchor>。请查看这里的操作方法。
3. 点击**保存并发送**。您的受众正在发送到所选的云服务。此过程可能需要最多 15 分钟才能完成。

<div id="manage-audiences" />

## 管理人群包

您可以从相关协作仪表板的 **受众** 部分查看和管理相关受众。

<Image alt="Audiences section.png" src="https://support.appsflyer.com/hc/article_attachments/32456187667345" width="2836px" />

**您可以从此页面执行的操作：**

* **搜索受众：** 按源名称或受众名称进行搜索。
* **筛选受众：** 选择按您的受众或与您共享的受众进行筛选。
* **查看受众详细信息：** 查看详细信息，例如合作者的姓名、重叠用户的统计数据、[受众状态](#观众状态)和激活位置。
* **更多操作:** 点击受众卡片的三点菜单图标可打开其他可用操作：
  * 编辑修改受众激活目标。
  * **查看受众历史:** 查看受众激活的所有实例，包含连接和激活状态等详细信息。
  * 下载CSV文件将受众下载为CSV文件。
  * **暂停：** 当数据源被修改时，防止受众被更新和重新激活。
  * 删除删除人群包

<div id="edit-the-audience-activation-destination" />

### 编辑受众激活目标

在构建受众时，您可以将其保存为草稿，然后返回并编辑激活目标（具体取决于您的权限）。

**要编辑受众激活目标:**

1. 在**协作**选项卡中，点击相关的协作。
2. 点击**受众**部分并找到相关受众。
3. 点击在受众上悬停时出现的三点菜单图标 > **编辑**。
4. 在连接和导出（受众页面底部）下，打开相关开关：
   * [连接到媒体合作伙伴](#将人群包连接到渠道)
   * [导出到云服务](#将受众导出到云服务)

<div id="delete-an-audience" />

### 删除受众

您可以删除在您的账户中创建的受众。这样做会将其永久从您的账户中移除。

**要删除受众:**

1. 在**协作**选项卡中，点击相关的协作。
2. 点击**受众**部分并找到相关受众。
3. 单击在观众上悬停时出现的 3 点菜单图标 > **删除**。
4. 确认删除。

### 观众状态

您可以查看与协作相关的观众状态。

![观众状态 - doctored w arrow.png](https://support.appsflyer.com/hc/article_attachments/36573611849361)

观众可以有多种状态：

* 活跃观众已成功发送到目标平台，并可在活动中使用。
* 草案观众已保存为草稿（从未连接、导出或交付）。
* 无效表示用于观众的源或数据视图已过期、已删除或已从协作中移除。
* **未连接:** 观众已从合作者处接收以进行激活，但尚未连接。
* **待交付:** 观众已发送给合作者以进行激活，正在等待激活。
* 已暂停观众已手动暂停，新的数据可用时不会发送。
* 已停用协作及其相关观众已被暂停。

您还可以查看观众的 **上传历史** 状态。

**查看上传历史：**

单击特定观众旁边的下拉菜单并选择 **查看历史**。

![查看历史 doctored .png](https://files.readme.io/7840f05fd8f6a98445c29e5a59813776378d842dd54fab4e3f66111c34dd89dd-36573637043089.png)

**上传历史状态包括:**

* **成功**：观众已成功发送到所有连接。
* 部分上传失败观众无法发送到一个或多个连接。
* 失败处理观众时出现问题（例如，由于数据不匹配、平台限制或平台错误）。

<div data-zendesk-anchors="h_01HZHB2GVA3W5EXG8MM6Y9QZR2=%E5%85%B3%E4%BA%8E-dcp overview=%E9%80%9F%E8%A7%88 h_01HWG1P909NHBXC5VF23BDVVPH=%E9%80%9F%E8%A7%88 audience-builder-tools=%E5%8F%97%E4%BC%97%E6%9E%84%E5%BB%BA%E5%B7%A5%E5%85%B7 01HWG510K97GCB137ZJZQE21DH=%E5%8F%97%E4%BC%97%E6%9E%84%E5%BB%BA%E5%B7%A5%E5%85%B7 key-features=%E4%B8%BB%E8%A6%81%E5%8A%9F%E8%83%BD h_01HWG5B2MEJH7M8E9BWA3FQFQ2=%E4%B8%BB%E8%A6%81%E5%8A%9F%E8%83%BD build-and-activate-your-audiences=%E5%BB%BA%E7%AB%8B%E4%BD%A0%E7%9A%84%E5%8F%97%E4%BC%97 h_01HWETSZWYZ8SFV9BH2N7X5BAE=%E5%BB%BA%E7%AB%8B%E4%BD%A0%E7%9A%84%E5%8F%97%E4%BC%97 h_01HWG62BA9X4VRRDXAEKA07FTJ=visual-audience-builder h_01HZMBFKV40PHFN1B8PVVCMWQQ=%E6%B3%A8%E6%84%8F step-1-join-sources=%E7%AC%AC1%E6%AD%A5%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF%E5%92%8C%E6%9D%A5%E6%BA%90 h_01HWFRRGP99KKGBSQ6QB10RD26=%E7%AC%AC1%E6%AD%A5%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF%E5%92%8C%E6%9D%A5%E6%BA%90 step-2-build-audiences=%E7%AC%AC2%E6%AD%A5%E5%AE%9A%E4%B9%89%E5%8F%97%E4%BC%97 h_01HWFRRPFTCFGEHY1AW8G4VMY4=%E7%AC%AC2%E6%AD%A5%E5%AE%9A%E4%B9%89%E5%8F%97%E4%BC%97 h_01JSEPSRF3FFJJ4S20GJJPJVWF=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01HWG62BAAD46MTK385756T4AQ=sql-audience-builder h_01HZM8X9RZ1A9CKWYNM61QW515=%E6%B3%A8%E6%84%8F-1 step-1-set-details=%E8%AE%BE%E7%BD%AE%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF h_01HWG9VX0QB3GFZDARAT5QKHV0=%E8%AE%BE%E7%BD%AE%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF step-2-build-query=%E6%9E%84%E5%BB%BA%E6%9F%A5%E8%AF%A2 h_01HWG9Y6B9X3T1FFM9ZR8TVBVC=%E6%9E%84%E5%BB%BA%E6%9F%A5%E8%AF%A2 the-sql-audience-builder=sql-%E8%A7%82%E4%BC%97%E6%9E%84%E5%BB%BA%E5%99%A8 h_01HZM9P2GNCPGJDEA51HCV1Y99=sql-%E8%A7%82%E4%BC%97%E6%9E%84%E5%BB%BA%E5%99%A8 send-audience-for-activation=%E5%8F%91%E9%80%81%E5%8F%97%E4%BC%97%E4%BB%A5%E8%BF%9B%E8%A1%8C%E6%BF%80%E6%B4%BB h_01HZMCHKMVXRWK7RXZ7NN65JQX=%E5%8F%91%E9%80%81%E5%8F%97%E4%BC%97%E4%BB%A5%E8%BF%9B%E8%A1%8C%E6%BF%80%E6%B4%BB h_01HZMCRJBBXFEV6JXEHGFXZDZW=%E6%B3%A8%E6%84%8F-2 connect-audience-to-media-partners=%E5%B0%86%E4%BA%BA%E7%BE%A4%E5%8C%85%E8%BF%9E%E6%8E%A5%E5%88%B0%E6%B8%A0%E9%81%93 h_01J8HNKQ08EVKXA75C9MZB7AW9=%E5%B0%86%E4%BA%BA%E7%BE%A4%E5%8C%85%E8%BF%9E%E6%8E%A5%E5%88%B0%E6%B8%A0%E9%81%93 h_01HZMDXEEABQRQE8XMZNE86SRF=%E6%B3%A8%E6%84%8F-3 export-audience-to-cloud-services=%E5%B0%86%E5%8F%97%E4%BC%97%E5%AF%BC%E5%87%BA%E5%88%B0%E4%BA%91%E6%9C%8D%E5%8A%A1 h_01HZPCCXTT91FQSTSEXN8GS2Y5=%E5%B0%86%E5%8F%97%E4%BC%97%E5%AF%BC%E5%87%BA%E5%88%B0%E4%BA%91%E6%9C%8D%E5%8A%A1 manage-audiences=%E7%AE%A1%E7%90%86%E4%BA%BA%E7%BE%A4%E5%8C%85 h_01HZPWTG23YQ5Y1GAPXT65DK07=%E7%AE%A1%E7%90%86%E4%BA%BA%E7%BE%A4%E5%8C%85 edit-the-audience-activation-destination=%E7%BC%96%E8%BE%91%E5%8F%97%E4%BC%97%E6%BF%80%E6%B4%BB%E7%9B%AE%E6%A0%87 h_01HZPXJEDPB6EB4HK2BW8RDDJM=%E7%BC%96%E8%BE%91%E5%8F%97%E4%BC%97%E6%BF%80%E6%B4%BB%E7%9B%AE%E6%A0%87 delete-an-audience=%E5%88%A0%E9%99%A4%E5%8F%97%E4%BC%97 h_01HZPXJMANK6PBQCHAQ4XQSTF4=%E5%88%A0%E9%99%A4%E5%8F%97%E4%BC%97 audience-statuses=%E8%A7%82%E4%BC%97%E7%8A%B6%E6%80%81 h_01HZPXAKV9YTAN2MNZCD22S5AX=%E8%A7%82%E4%BC%97%E7%8A%B6%E6%80%81" />

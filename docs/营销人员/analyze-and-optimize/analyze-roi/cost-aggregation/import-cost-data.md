---
title: 导入成本数据
metadata:
  keywords:
    - Ad Network
    - Agency
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Xpend
    - Marketers
    - ROI360
    - Ad Networks
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
    - Ad Networks
  created_at: '2019-09-15T15:53:44Z'
  edited_at: '2026-10-14T10:11:51Z'
  id: 360002516838
  locale: zh-cn
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/zh-cn/articles/360002516838
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 成本导入（Cost Import）功能是AppsFlyer ROI360解决方案中的一部分。广告主可以上传或通过邮件发送CSV格式的成本数据，全面满足营销成本的上报需求，同时确保数据的完整性和准确性。

<div id="overview" />

## 速览

成本导入功能适用于以下场景：

* 将所有营销投放（网红营销、移动端广告、CTV广告等等）的成本数据发送到AppsFlyer。尤其适用于不支持通过API或归因链接上报成本的媒体渠道。
* 回滚更正之前的成本数据。

该功能支持您通过上传或发送邮件的方式将CSV格式的成本数据发送到AppsFlyer。AppsFlyer收到这些文件后会对其进行处理，并在数小时内将处理完毕的数据呈现在面板和报告中，为您提供全面的投放成本和ROI信息。

**请注意**：

* 广告平台也可以为其广告主导入成本文件，但必须先由广告主为其开通必要权限。
* 代理不能上传数据。但代理可以制备文件，然后将这些文件发送给广告主，由广告主完成上传。

<div id="procedures" />

## 配置流程

使用成本导入功能向AppsFlyer发送成本数据时，需要完成以下操作：

1. [制作带有相关成本数据的CSV文件](/docs/import-cost-data#prepare-csv-file-with-cost-data)，用于数据导入。
2. 通过以下任一方式将该文件发送到AppsFlyer：
   * 在AppsFlyer面板中[上传](/docs/import-cost-data#email-file)该文件
   * 通过[电子邮件](/docs/import-cost-data#email-file)发送该文件**请注意**：CTV、PC和主机平台上的应用仅可使用此方法上报成本数据。

下文分别解释了这两种流程。

<div id="prepare-csv-file-with-cost-data" />

<Accordion title="制备成本数据的CSV文件">

广告主、广告平台和代理都可以制备用于成本导入的CSV文件。请参考<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv">文件范例</Anchor>。

**制备CSV文件时**：

* 请遵循下表所列的文件结构、格式和规范。  
  **请注意**：如果您使用Excel或Google Sheets来创建该文件，请务必参照[Excel和Google Sheets的格式](/docs/import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file)说明进行操作。

<div id="csv-schema" />

#### CSV文件结构

<table><thead><tr><th><p><span>字段名称</span></p><p><span>（区分大小写）</span></p></th><th><span>格式/说明</span></th><th><span>示例</span></th><th><span>是否必须发送</span></th></tr></thead><tbody><tr><td><span>date</span></td><td><ul><li><span>产生相关成本的日期</span></li><li> <span>格式：字符串</span><br/>推荐方法：<ul><li><span>YYYY-MM-DD</span></li><li><span>YYYY-MM-DD</span></li><li><span>MM-DD-YYYY</span></li><li> <span>MM/DD/YYYY</span><br/> </li></ul></li><li>不允许使用未来的日期</li><li> <strong>推荐设置</strong>：使用您在AppsFlyer后台为相关应用设置的时区。</li><li> <strong>请注意</strong>：如果您使用Excel或者Google Sheets来创建CSV文件，请务必<a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">参考相关说明</a>。 </li></ul></td><td><ul><li><span>2019-05-30</span></li><li><span>2019/05/30</span></li><li><span>5-30-2019</span></li><li>5/30/2019</li><li>05-30-2019</li><li>05/30/2019</li></ul></td><td><span>✓</span></td></tr><tr><td><span>app-id</span></td><td><ul><li><span>格式：字符串</span></li><li> <span>即AppsFlyer面板中显示的App ID</span>，</li><li>一个文件中可包含多个App ID。</li><li>所有App ID都必须属于同一个广告主账号。</li></ul></td><td><ul><li><span>com.app.name </span></li><li><span>id12356789</span></li></ul></td><td><span>✓</span></td></tr><tr><td><span>media-source</span></td><td><ul><li><span>格式：字符串</span></li><li><span>这里的媒体渠道名称必须与AppsFlyer面板显示的渠道名称的<strong>完全一致</strong>。<strong>请注意：</strong>如果面板显示的名称中带有后缀_int，也必须一并包含。</span></li><li> <span>每个文件只能包含一个媒体渠道的数据。</span><span></span>同一个媒体渠道的文件中可以包含多个应用的数据。</li></ul></td><td><span>network_x_int</span></td><td><span>✓</span></td></tr><tr><td><span>campaign</span></td><td><ul><li> <span>格式：字符串</span><span></span> </li><li><span>广告系列名称。请确保该名称与广告平台中对应广告系列的名称一致（区分大小写）。</span></li><li>不同应用下切勿使用相同的广告系列名称。</li></ul></td><td>campaign_a</td><td><p><span>✓</span></p><p><span><strong>请注意</strong>：如果归因数据同时带有名称和ID信息，那么CSV文件中也必须同样带有名称和ID。</span></p></td></tr><tr><td><span>spend</span></td><td><ul><li><span>广告消耗的金额</span></li><li><span>最多可精确到小数点后五位</span></li><li><span>可填充零值（0）</span></li><li> <span><strong>请注意</strong>：</span><ul><li>不可使用千位分隔符，如："2,874.12"。</li><li>如果您使用Excel或者Google Sheets来创建CSV文件，请务必<a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">参考相关说明</a>。</li></ul></li></ul></td><td><p><span>2874.12345</span></p></td><td><span><span>✓</span></span></td></tr><tr><td><span>geo</span></td><td><ul><li><span>格式：字符串</span></li><li> <span><a href="https://www.iso.org/iso-3166-country-codes.html">ISO 3166</a>中的国家代码，由两个字母组成。</span><strong>请注意</strong>：请确保您发送的是2个字符，中间无空格。 </li><li> <span>英国的国家代码是UK</span><span>而非GB。</span><br/> </li></ul></td><td><p><span>US, CN, AU</span></p></td><td><span>否</span></td></tr><tr><td><span>currency</span></td><td><ul><li><span>格式：字符串</span></li><li> <a href="https://www.iso.org/iso-4217-currency-codes.html" target="_blank">ISO 4217</a>中的货币代码，由三个字母组成。 <strong>请注意</strong>：切勿在代码前后使用空格。</li><li> <span>文件中的每个应用只能对应一个货币代码，不同的</span><span>应用可以使用不同的货币代码。 </span> </li></ul></td><td><span>USD, GBP, EUR, JPY</span></td><td><p><span>不可以。</span></p><p><span>若该字段留空，则默认使用USD（美元）。</span></p></td></tr><tr><td><span>campaign-id</span></td><td>格式：字符串</td><td>abc1234def</td><td rowspan="5"><p>不可以。</p><p><strong>请注意</strong>：如果归因数据同时带有名称和ID信息，那么CSV文件中也必须同样带有名称和ID。</p></td></tr><tr><td><span>adset</span></td><td>格式：字符串 </td><td>my_adset_1</td></tr><tr><td><span>adset-id</span></td><td>格式：字符串</td><td>id5678ghi</td></tr><tr><td><span>ad</span></td><td>格式：字符串 </td><td>my_ad_name</td></tr><tr><td> <span>ad-</span><span>id</span> </td><td>格式：字符串 </td><td>id91011jkl</td></tr><tr><td><span>site-id</span></td><td><ul><li>格式：字符串 </li><li>用于标记媒体的唯一ID。 <a href="./about-link-structure-and-parameters#site-id-parameter" target="_blank">了解详情</a> </li></ul></td><td>id1213mno</td><td>否</td></tr><tr><td><span>channel</span></td><td>格式：字符串 </td><td> video</td><td>否</td></tr><tr><td><span>keywords</span></td><td>格式：字符串</td><td><ul><li>better</li><li>better you app</li><li>better you online</li></ul></td><td>否</td></tr><tr><td><span>agency</span></td><td><ul><li>格式：字符串</li><li>相关代理的名称，<code>af_prt</code> 参数中的值。</li><li>一个文件中仅可包含一个代理，且不能出现非该代理代投的广告系列。</li><li>每行都必须包含该代理的名称。代理字段一列不能出现空白的单元格。</li><li>代理必须具备文件中涵盖的所有应用的权限。</li><li>只有广告主可以上传文件，代理不能上传数据。但代理可以制备文件，然后将这些文件发送给广告主，让广告主完成上传。</li><li>如果在后续提交中包含了相同日期的成本数据和机构名称（<code>af_prt</code>），而在原始提交中缺失，这将导致成本数据重复。</li></ul></td><td>AgencyName</td><td>否</td></tr><tr><td colspan="4"><span><strong>请注意：</strong>如果名称中带有非英文字符，必须使用UTF-8对其进行编码。</span></td></tr></tbody></table>

<div id="csv-format-and-rules" />

#### CSV文件的格式和规范

| 规范 | 要求 |
| --- | --- |
| 禁用字符 | 字段须以字符串格式填充，且不能以`=`、`+`、`-`或者`@`作为第一个字符，例如`@example_campign`或`=123`会被视为无效。 |
| 应用拥有者 | 一个文件中只能包含一个广告主（应用所有者）的数据，但可包含该广告主账号下多个应用的数据。 |
| 文件扩展名 | CSV文件名示例：abc123.csv |
| 文件结构 | <ul><li>**格式**：文件必须使用CSV格式，也就是说每栏之间都以逗号分隔。</li><li>**标题行**：第一行是与栏位相匹配的标题行。</li><li>**数据行**： 包含必须配置的字段。 **请注意**：请确保您的数据末尾不带空格。比如末尾带空格的[USD ]（字母**D**后有空格）必须更正为[USD]。</li><li>**空白行**：不允许</li><li>含有同一个key的**重复行**：不允许。key是在配置必填字段时生成的。</li><li>**空白单元格：** <mark>文件中不允许包含空值。</mark>如果您不想上传某些字段，请不要在文件中添加这些字段。</li></ul> |
| 广告层级 | 记录成本时，广告系列是必须包含的维度，其他的投放维度是可选的。<br /><br />任何比广告系列粒度更细的不完整数据都会覆盖对应广告系列层级以下的所有数据。<br /><br />**举例说明：** 假设您导入了某广告系列下adset 1的成本数据，然后在另一个文件中单独导入了同一个广告系列下adset 2的成本数据，则该广告系列的总成本会被替换为adset 2的成本数据。为了确保能记录到该广告系列的总成本，您导入的文件中必须同时包含adset 1和adset 2的数据。 |

</Accordion>

<div id="upload-file" />

<Accordion title="上传文件">

广告主和广告平台都可以上传CSV文件，用于成本导入。

**前期准备**：广告平台需要先让[广告主为其开通成本导入的权限](/docs/import-cost-data#cost-import-permissions-for-ad-networks)。

**通过AppsFlyer面板上传CSV文件的方式如下**：

1. 在AppsFlyer后台的左侧菜单栏中选择**配置** > 成本导入。  
   **界面会显示成本导入页面。**
2. 点击+ 导入成本文件  
   界面会打开导入成本的窗口。
3. 将CSV文件拖拽至**导入成本文件**的窗口内。  
   界面显示“正在处理文件”的消息。
4. 如果在上传过程中报错，请修正错误，然后重复相关步骤。
5. 界面会打开**成本导入：文件摘要**窗口。
6. 此时可完成以下任一操作：
   * 点击**取消导入**中止上传。
   * 点击**导入文件**完成导入流程。  
     上传完毕后，界面会显示“准备就绪”的消息。
   * 如果出现报错，请按照[报错](#error-messages-and-solutions)部分的说明排查并解决问题。
7. 点击**导入其他文件**或**完成**。

</Accordion>

<div id="email-file" />

<Accordion title="通过邮件发送文件">

广告主和广告平台都可以通过邮件发送CSV文件，用于成本导入。

**前期准备**：

* 广告主：
  * 邮件发送方必须是已注册的AppsFlyer用户。
* **广告平台**：
  * 邮件发送方必须是已注册的AppsFlyer用户。
  * [需要广告主为其开通成本导入权限。](/docs/import-cost-data#cost-import-permissions-for-ad-networks)

**请按以下步骤通过邮件发送CSV数据文件**：

1. 获取[邮件导入的token。](/docs/import-cost-data#token-for-email-import)
   1. 在AppsFlyer后台的左侧菜单栏中选择**配置** >**成本导入**。
   2. 点击页面右上角的**邮件导入token**。
   3. 复制并保存该token。
2. 编写邮件，其中必须带有以下字段：
   * **收件人**：`adspend-upload@appsflyer.com`
   * **CC：抄送给需要收到自动回复的用户**
   * **主题**：将邮件导入的token复制粘贴到主题栏中。
   * **附件**：包含相关数据的CSV文件。
3. 发送邮件。
   * AppsFlyer收到文件并处理完数据后，会向您发送状态报告邮件，邮件中说明文件上传的总体情况以及处理数据的过程中发生的具体问题和错误。原始邮件中抄送的各方以及广告主账户的管理员都会收到该邮件。如果邮件中说明出现错误，请按报错部分的说明排查并解决问题。
   * 您可以在[成本导入](/docs/import-cost-data#error-messages-and-solutions)面板中查看已提交文件的导入状态。

</Accordion>

<div id="dashboard" />

## 面板

成本导入仪表板允许您上传文件并查看之前上传文件的详细信息。

<div id="cost-import-dashboard" />

<Accordion title="成本导入面板">

如需查看成本导入面板，请在AppsFlyer后台的左侧菜单栏中选择**配置** > **成本导入**。

下表列出了面板对于先前导入的文件所提供的信息。

| 字段名称 | 说明 |
| --- | --- |
| CSV文件名 | 即导入AppsFlyer的成本文件的名称。 |
| 上传日期 | 文件导入的日期。 |
| 媒体渠道 | 文件中包含的媒体渠道。 |
| 日期范围 | 文件中广告消耗发生的起始和截止日期。 |
| 匹配行（%） | 文件中成本可匹配到归因的数据量（以行数计算）所占的百分比。[详情请见此处说明](#matched-rows)。 |
| 状态 | 导入文件的状态：<ul><li>**成功**：操作成功。表示成本数据已记录到AppsFlyer面板和报告中，可供查看取用。</li><li>**验证错误**：AppsFlyer系统问题。请等待10分钟，然后重试。若仍无法完成上传，请联系AppsFlyer的技术支持团队。</li><li>**无权限**：该token未授权给此应用<ul><li>广告主：请确保您使用的应用ID正确无误。</li><li>广告平台：请让广告主确认已向您开放成本导入权限。</li></ul></li><li>**已撤销**：操作成功。表示该文件已被其他数据覆盖/替换。</li></ul> |
| 操作 | <ul><li>文件层级的操作：如果您有文件中所有应用的权限，就可以完成以下操作：<ul><li>**下载CSV文件**：这里下载的文件是之前导入的CSV文件的副本。</li><li>下载文件中所有应用的**未匹配数据报告**。详情请见此表中的匹配行说明部分。</li></ul></li><li>应用层级的操作：您点击某个具体文件时，面板会呈现相关应用的所有成本导入信息，包括您点击的文件以及其他文件。如果您有相关应用的权限，可以完成以下操作：<ul><li>**下载该应用的数据。**</li><li>下载该应用的**未匹配数据报告**</li><li>**撤销**（取消）文件中选定应用的成本导入。</li></ul></li></ul> |

</Accordion>

<div id="matched-rows" />

<Accordion title="匹配行">

行数据匹配是一种数据处理方式，将导入的成本数据匹配到AppsFlyer记录到的归因数据。使用这种方式处理数据时，AppsFlyer会对所有可用维度（而非ID）的数据都进行匹配，包括媒体渠道、广告系列、广告组、广告等等。如果文件中某行数据的所有维度都与面板数据匹配，AppsFlyer会将该行标记为is-matching=TRUE。

无论匹配状态如何，成本数据都会被记录到AppsFlyer面板和报告中，供您查看取用。

成本导入面板中会显示匹配行的占比。如果出现反常的不匹配行，或不匹配行的占比过高：

* 请下载未匹配数据报告，以便考察问题根因。未匹配数据报告中有一栏叫做is-matched，该字段可能出现的值为TRUE（表示匹配）或FALSE（表示未匹配）。
* 必要时请点击“撤销”按钮以取消数据导入。
* 详情请见上文表格中的“操作”部分说明。

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="using-excel-or-google-sheets-to-prepare-csv-file" />

<Accordion title="使用Excel或者Google Sheets制备CSV文件">

如果您使用Excel或Google Sheets制备CSV文件，请务必先确认日期（date）和广告消耗（spend）字段的设置正确无误，然后再将文件保存为CSV格式。保存CSV文件之后，请检查其格式是否正确无误。请按照下文所述的方式分别完成以下操作：

* 设置日期单元格的格式。
* 设置广告消耗单元格的格式。
* 检查并确认文件内容的格式正确无误。

<div id="format-date-cells" />

#### 日期单元格的格式设置

**在Excel中按YYYY-MM-DD设置日期单元格的格式**：

1. 选中需要设置格式的单元格。
2. 右击并选择**设置单元格格式**（Format cells）。  
   界面会打开设置单元格格式的窗口。  
   <Image align="center" alt="Formatdate..png" src="https://files.readme.io/43d0f370f299d73b8ce93fec1c912cb7525d0071db779a64a58f5917df2a5531-360004042458.png" width="379px" />
3. 选择**自定义**（Custom）。
4. 在类型（Type）字段中，输入**YYYY-MM-DD**
5. 点击**OK**。  
   日期格式设置完毕。

<div id="formatting-spend-cells" />

#### 广告消耗单元格的格式设置

如下图所示，Excel对数值单元格进行格式化时，通常使用逗号作为千位分隔符。此格式不适用于成本导入文件。

<Image align="center" alt="mceclip1.png" src="https://files.readme.io/d54e21ddd937dfe25a33bb96193761a5a724c22a35a55bb7d71eb03a6433d7ed-360003949177.png" width="291px" />

**如需设置广告消耗单元格的格式，使其不带千位分隔符：**

1. 选中需要设置格式的单元格。
2. 右击并选择**设置单元格格式**（Format cells）。  
   界面会打开设置单元格格式的窗口。
3. 选择**Number**。  
   <Image align="center" alt="Formatnumbers.png" src="https://files.readme.io/4c1b61d1eae9149e818d4cc9793128fbdaafed5daed9acf6cbc503571475cc0e-34255643022481.png" width="381px" />
4. 取消**千位分隔符 (,)**。
5. 【可选】设置数值的**小数点后位数**，默认值为2，最多可精确到小数点后5位。
6. 点击**OK**。  
   单元格格式化完毕。

<div id="verify-content-format" />

#### 检查文件内容的格式

**请按以下方式检查文件内容的格式**：

1. 使用以下任一编辑器查看相关文件。
   * Windows：Notepad、Notepad++
   * MacOS：TextEdit
2. 请特别注意以下几点：
   * **空格：** 请确保字段分隔符（即逗号）的前后没有空格。您可以在Excel中使用@trim命令来删除空格。
   * **日期（date）：** 请确保日期字段的格式为YYYY-MM-DD。
   * **广告消耗**请确保广告消耗单元格中没有逗号。
   * **分隔符**：必须是逗号。如出现分号分隔符：
     * 这可能是因为您电脑的区域设置为非英语语言/地区（此问题在德语设置中尤为普遍）。
     * 在不同的计算机操作系统（macOS或Windows）中解决此问题的方法不同。
     * 如需解决此问题，请在<Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor>或其他论坛中搜索相关指南。您可以在搜索中使用以下关键词：Operating system (macOS or Windows) Excel change delimiter for CSV files（在macOS或Windows中通过Excel更改CSV文件分隔符）。

下图为[CSV示例文件](https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv)在编辑器中的截屏。

<Image align="center" alt="mceclip1.png" src="https://files.readme.io/1398c5e9bad7a46b697e3b21030e64d656162e33a4a63f39475c64993bbe7a72-360003996197.png" width="672px" />

</Accordion>

<div id="token-for-email-import" />

<Accordion title="邮件导入的token">

邮件导入token用于验证邮件发送方是否已获得授权，可以提交成本导入文件。

广告主和广告平台分别有其各自的token。

* 广告主的token：
  * 一个账号下的所有应用共用同一个token。
  * 一个账号下的所有用户都可以获取该token。
* 广告平台的token：
  * 所有广告主共用同一个token。

广告主与广告平台之间切勿共享token！

</Accordion>

<div id="cost-import-permissions-for-ad-networks" />

<Accordion title="广告平台的成本导入权限">

广告平台需要广告主为其开放分应用的成本导入权限，才能使用该功能。

**请按以下方式为广告平台开放成本导入权限：**

1. <strong>广告主</strong>需要从AppsFlyer后台的左侧菜单栏中选择<strong>协作</strong> > 活跃对接。  
   界面会显示对接渠道页面。
2. 选择相关的对接渠道。
3. 进入**授权**选项卡。
4. 确保**广告平台权限**开关已打开。
5. 【可选】添加账户用户。
6. 打开**使用成本导入**的权限开关。
7. 点击**保存权限**。

</Accordion>

<div id="see-also" />

<div id="troubleshooting-traits-and-limitations" />

## 问题排查、特点和局限性

<div id="error-messages-and-solutions" />

<Accordion title="报错消息和解决方法">

下表列出了成本导入时可能出现的所有报错消息和相应的解决方法。

| 报错消息 | 说明 | 解决方法 |
| --- | --- | --- |
| AppsFlyer平台中不存在该文件所包含的任何应用ID。请确认文件中的应用ID是否正确。 | 您的账户中不存在该应用ID。 | 更正应用ID，然后重新上传。 |
| [某某]行的字段数量有误。应包含[X个]字段，实际接收到[Y个]字段。 | 文件中所有的字段都必须含有字段值。 | 根据您定义的表头更改文件中填充的值。 |
| 文件表头中缺少“media-source”。 | <ul><li>文件表头中缺失media-source一列。</li><li>列名称必须与上文CSV栏位说明列表中的名称完全一致。</li></ul> | 将media-source添加在表头行名。 |
| 一个文件中只能包含一个媒体渠道。发现该文件中出现多个媒体渠道：[媒体渠道数量]。 | 该文件包含多个媒体源。CSV中的隐藏空行或格式错误的行也可能触发此错误，即使它们在Excel中不可见。 | 在文本编辑器中打开该文件，例如Notepad++，并删除任何空行或格式错误的行。保存该文件并重新上传。如果该文件包含多个媒体源，请将其拆分为每个媒体源一个文件。 |
| 字段[X]的值[Y]对此列无效。 | 相关列中的数据格式不正确。比如日期（date）字段的格式应为dd-mm-yy而非yyyy-mm-dd。 | 更正格式后重新上传。 |
| 在该应用下发现了多种货币。文件中的每个应用只能使用一种货币。发现的货币：%货币种类的数量% | 一个应用只能对应一种货币。 | 在文件中统一货币后重新上传。 |
| 文件表头中的以下各列不适用：[文件表头] | 文件表头与栏位名称不一致。表头的参数名必须与上文所列的栏位名称完全一致。 | 删除不适用的列，然后重新上传。 |
| 文件表头中缺少必须配置的列：[文件表头] | 文件表头中缺失必须配置的字段。 | 添加缺少的字段和对应的值，然后重新上传。 |
| 文件中包含了未来的日期：[日期] | 不可使用未来日期。 | 更正日期，然后重新上传。最晚的可用日期为当天的日期。 |
| 文件为空，没有待处理的数据。 | 文件为空， | 请在文件中添加数据，然后重新上传。 |
| 以下两行的维度完全一致，造成冲突。请将广告消耗数据按各组维度在单独的行中分开提供。[出现数据冲突的行] | 多行数据的key完全相同（即必填字段相同）。 | 请删除重复行，然后重新上传。 |
| 一个文件中只能包含一个广告主账户的数据。发现该文件中包含多个广告主：[广告主名称] | 广告平台上传文件时不能在同一个文件中加入多个广告主的数据。 | 请将各广告主的数据拆分到单独的文件中分别上传。 |
| 相关账户中不存在应用[应用ID]。请检查应用ID是否正确。 | 账户中不存在该app id。 | 请更正应用ID，然后重新上传。 |
| 未发现应用[应用ID]的地理位置（即国家代码）信息。请使用ISO 3166中的2字母代码。 | 地理位置字段值无效。 | 请更正地理位置信息，然后重新上传。 |
| 未发现应用[应用ID]的货币代码。请使用ISO 4217中的3字母代码。 | 货币字段值无效。 | 请使用有效的货币值更正文件内容，然后重新上传。 |
| 文件中一个或多个应用的验证出错。请重新检查文件信息以了解详情。 | 文件中存在多处错误。 | 请下载文件并查看错误详情。 |
| 处理文件时发生内部错误，请重新上传。 | <ul><li>处理文件时发生后端错误。</li><li>通常是暂时性的问题。</li></ul> | 请等待一小时，然后重试。 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 广告平台 | 支持。<br /><br />例外：<ul><li>Meta Ads</li><li>X Ads</li><li>ASA</li></ul> |
| 代理 | <ul><li>代理不能上传数据。但代理可以制备文件，然后将这些文件发送给广告主，让广告主完成上传。</li><li>制备这些CSV文件时，请务必确保文件中包含一个带有代理名称（即af\_prt参数的值）的Agency（代理）字段。详见[CSV文件结构示例](/docs/import-cost-data#csv文件结构)</li></ul> |
| 代理数据透明化 | 不支持 |
| 应用层级指定时区 | 支持 |
| 应用配置中的指定货币 | 支持。面板会按应用层级的指定货币对投放成本进行换算。 |
| 广告系列名称 | 请勿对不同的应用使用相同的广告系列名称，否则一个成本的成本会出现在个应用的数据中。 |
| 字段名称 | 如果与广告层级相关的字段名称与归因数据中的字段名称不一致，面板就会将相关数据分行单独显示。<br /><br />举例来说，假设广告系列名称不一致，那么即使广告系列ID相同，面板也会将其视为不同的广告系列。 |
| 文件大小 | 上传CSV格式的成本导入文件时，文件大小限制如下：<ul><li>通过AppsFlyer面板导入：2MB</li><li>通过电子邮件导入：每个文件不超过5MB</li></ul> |
| 自然量数据 | 支持 |
| 非自然量数据 | 支持 |
| 数据时效性 | <Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">广告消耗数据</Anchor> |
| 历史数据 | 支持。上传文件后的90天内可以还原其中上报的成本数据，并在更正数据后重新上传。 |
| 再营销 | 不支持。 |
| 相关账户下的用户权限 | 对于国家/地区或媒体渠道受限的用户不可用。 |

</Accordion>

<div data-zendesk-anchors="ad-spend-import=%E9%80%9F%E8%A7%88 01H7VYHJ2BN3EFDC4J3YN3P4WM=%E9%80%9F%E8%A7%88 procedures=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B h_01HYZBZMNTM0244V4PN6AJ45KR=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B h_01HYZD52VRTMGJ0BFBFJNGQ50E=prepare-csv-file-with-cost-data ad-spend-csv-schema=csv%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84 01H7VYHJ2CWF2HWHCTZDEZHT29=csv%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84 csv-format-and-rules=csv%E6%96%87%E4%BB%B6%E7%9A%84%E6%A0%BC%E5%BC%8F%E5%92%8C%E8%A7%84%E8%8C%83 h_01HYZEDYKCAPTK1WD6VGWTA6PQ=csv%E6%96%87%E4%BB%B6%E7%9A%84%E6%A0%BC%E5%BC%8F%E5%92%8C%E8%A7%84%E8%8C%83 h_01HYZD52VRWK7D6Q0YBW9SEFK6=upload-file h_01HYZKN3YEPFG8525GFQD0PC5K=email-file dashboard=%E9%9D%A2%E6%9D%BF h_01HZ4NVKPVHV1KT12V59MZBGPZ=%E9%9D%A2%E6%9D%BF h_01HZ1SXQQ2CHG77KX96D74J6TQ=cost-import-dashboard h_01HZ4NVKPVSM5ZTG76HJF3GW4J=matched-rows additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HYZFNKFEQW13F0BWAG3FZF69=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HYZFNKFE3AVH1GNGDT511M5B=using-excel-or-google-sheets-to-prepare-csv-file formatting-date-cells-in-excel=%E6%97%A5%E6%9C%9F%E5%8D%95%E5%85%83%E6%A0%BC%E7%9A%84%E6%A0%BC%E5%BC%8F%E8%AE%BE%E7%BD%AE 01H7VYHJ2DSWC2J1NY04Q9Q620=%E6%97%A5%E6%9C%9F%E5%8D%95%E5%85%83%E6%A0%BC%E7%9A%84%E6%A0%BC%E5%BC%8F%E8%AE%BE%E7%BD%AE formatting-spend-cells-in-excel=%E5%B9%BF%E5%91%8A%E6%B6%88%E8%80%97%E5%8D%95%E5%85%83%E6%A0%BC%E7%9A%84%E6%A0%BC%E5%BC%8F%E8%AE%BE%E7%BD%AE 01H7VYHJ2DA9JM4Q33V2TF7BD3=%E5%B9%BF%E5%91%8A%E6%B6%88%E8%80%97%E5%8D%95%E5%85%83%E6%A0%BC%E7%9A%84%E6%A0%BC%E5%BC%8F%E8%AE%BE%E7%BD%AE verify-content-format=%E6%A3%80%E6%9F%A5%E6%96%87%E4%BB%B6%E5%86%85%E5%AE%B9%E7%9A%84%E6%A0%BC%E5%BC%8F h_01HYZJJVC463C141AQ3VY5Z0TQ=%E6%A3%80%E6%9F%A5%E6%96%87%E4%BB%B6%E5%86%85%E5%AE%B9%E7%9A%84%E6%A0%BC%E5%BC%8F h_01HYZFNKFEXK4CYRBZ3ABRCWNJ=token-for-email-import h_01HZ1XV6ZX5FAN9JJPQM9RYD3Z=cost-import-permissions-for-ad-networks troubleshooting-traits-and-limitations=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5%E7%89%B9%E7%82%B9%E5%92%8C%E5%B1%80%E9%99%90%E6%80%A7 h_01HZ4PBGAG9R9JMHPXVQC1GX3V=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5%E7%89%B9%E7%82%B9%E5%92%8C%E5%B1%80%E9%99%90%E6%80%A7 h_01HZ2859J5P6MFKACKBK46J6GP=error-messages-and-solutions h_01HZ27W0409NF4Y6RNT8WPW8HP=traits-and-limitations" />

---
title: 数据净室——数据源使用指南
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-03-27T10:58:23Z'
  edited_at: '2026-10-14T10:09:02Z'
  id: 5041487011601
  locale: zh-cn
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/zh-cn/articles/5041487011601
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 概要：本文说明了自定义数据源文件的设置方式。您可以与数据净室（DCR）共享数据源，将其与归因数据进行匹配，并生成DCR报告。

<div id="introduction" />

## 简介

大部分DCR报告的目的是将您的**归因数据**与**指定来源**的数据进行匹配。本文将为您详细解释如何在DCR中使用自定义数据源，包括：

* 在DCR中[创建数据源](/docs/data-clean-room-working-with-sources#创建数据源)
  * [为数据源命名](/docs/data-clean-room-working-with-sources#1-name-the-source)
  * 说明自定义来源数据的[获取位置](/docs/data-clean-room-working-with-sources#2-specify-the-source-location)
  * [定义数据源结构](/docs/data-clean-room-working-with-sources#3-define-the-source-structure)（将相关字段标识为指标、维度和标识符）
  * [保存数据源](/docs/data-clean-room-working-with-sources#4-save-the-source)
* 定期[更新自定义来源数据](/docs/data-clean-room-working-with-sources#更新数据以触发报告处理流程)，触发数据处理流程以生成报告
* [现有数据源的使用方式](/docs/data-clean-room-working-with-sources#现有数据源的使用方式)

> 🚧 **前期准备**
>
> 创建自定义数据源之前，请先完成以下工作：
>
> * 【必须完成】<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-setting-up-cloud-services">设置云存储工具</Anchor>，供DCR获取相关数据。AppsFlyer支持以下两种云存储工具：
> * 【可选】在AppsFlyer平台中<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-connections#creating-inbound-connections">创建数据连接</Anchor>，将相关的云存储工具连接到DCR。
>   * 如果您前期未设置数据连接，则会在创建自定义数据源时收到弹窗提示，指引您设置连接。


<span id="source-requirements"></span><span id="source-format"></span>自定义数据源必须具备以下条件，否则在创建数据源和处理数据、生成报告的过程中可能会出现错误。

自定义来源的数据必须符合以下要求：

* **日期与时间：**
  * **格式：** yyyy-MMM-dd hh:mm:ss（*如*`2023-APR-18 15:30:35`2023-APR-18 15:30:352023-APR-18>）
  * 时区UTC
* **数值**：小数点后最多2位
* **字符串长度**：最多256个字符
* **字符限制：**
  * **字段名称（列标题）**：不可使用空格或特殊字符
  * 所有其他数据：无限制（所有字符皆可用）


<div id="table-columns" />

<Accordion title="表格栏位 （仅适用于数据仓库中的数据源）">

除了用于匹配的数据以外，BigQuery或Snowflake中的表格还必须包含2各额外的栏位，一个用于说明**日期**，另一个用于说明**版本**：

* **日期（date）：**
  * 列标题
  * **数据类型**：日期
  * **数据格式：** yyyy-mm-dd（*如*`2023-04-18`2023-04-182023-04-18）
  * **其他要求：** 其他注意事项：BigQuery中的表格必须按此列<Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/partitioned-tables">分区</Anchor>
* **版本：**
  * 列标题
  * **数据类型**：字符串
  * **数据格式**：数字（如`1`11、`2`22、`3`33、`10`1010）
  * <strong>重要提示！</strong>每次DCR检测到此列中出现新值时都会触发新版本报告的生成。为了确保报告的完整性，请务必在该列的值发生变化时向表格中填充完整的一组数据。

</Accordion>

<div id="file-format" />

<Accordion title="文件名称和格式 （仅适用于云存储桶中的数据源）">

存储在Amazon S3或GCS中的数据文件必须符合以下名称和格式要求：

* 文件名称必须符合<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR的命名规则</Anchor>
* 必须为CSV或GZIP格式。
  * GZIP压缩文件中的文件必须为CSV格式。
* 每个[数据文件夹](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version)下的数据源文件数量：
  * **CSV**。
  * GZIPGZIP： 最多1个不分卷的压缩文件。

</Accordion>

<div id="creating-a-source" />

## 创建数据源

下文介绍了数据源创建流程中涉及的**所有步骤**。我们把这些步骤分在单独的标签中，以便查阅。

**请按以下步骤创建数据源：**

<div id="1-name-the-source" />

<Accordion title="21为数据源命名">

1. 进入**数据净室**中的**数据源选项卡**。
2. 点击 **+ 新数据源**按钮。  
   界面打开**新数据源**页面。
3. 在左上角输入该数据源的名称。
   * 数据源名称用于标识出DCR所使用的数据源。
   * <strong>重要提示！</strong>切勿使用已经存在的其他数据源名称来命名，否则无法保存该数据源。
   * 数据源名称要求：
     * 1000个字符。
     * 有效字符：

       * 数字`(0-9)`（0-9）(0-9)，*不能作为名称中的第一个字符*
     * 无效字符：
       * 空格
       * 所有其他符号和特殊字符

</Accordion>

<div id="2-specify-the-source-location" />

<Accordion title="6.16.0#2：指定数据源位置">

1. 选择<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-setting-up-cloud-services#速览">数据连接</Anchor>，在其中创建相关数据源。
   * 如果您的账户中没有设置连接，界面会打开创建**新数据连接**的对话框。请按照对话框中的<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-connections#速览">指引说明</Anchor>创建数据连接。
   * 请按照对话框中的指引说明创建数据连接。
2. 根据您使用的数据源按下文中的相关说明继续进行设置。

<div id="source-locations-in-bigquery" />

#### BigQuery中的数据源位置

设置BigQuery数据源位置的方法如下：

1. 选择数据表所在的数据集。
2. 选择相关数据所在的表格。

创建数据连接时供您完成上述选择的列表包含您指定的BigQuery项目中可用的数据集和表格。

<div id="source-locations-in-snowflake" />

#### Snowflake中的数据源位置

**设置Snowflake数据源位置的方法如下：**

1. 选择相关数据所在的共享位置（share）。
2. 选择数据表所在的模式（schema）。
3. 选择相关数据所在的表格。

创建数据连接时供您完成上述选择的列表包含您指定的Snowflake账户中可用的共享位置（share）、模式（schema）和表格。

<div id="source-locations-in-cloud-storage-buckets" />

#### 云端存储桶中的数据源位置

Amazon S3或GCS中的数据源位置信息包括数据连接中指定的云存储桶以及相关文件的文件夹路径（DCR会根据该路径在数据更新时读取文件）。

数据连接设置完毕后，AppsFlyer就能自动生成文件夹路径，完成数据源创建流程中的必要环节。

**设置云端存储桶中的数据源位置时，请输入数据源文件夹的名称。**

* 默认情况下，数据源文件夹名称应符合以下条件：
  * 以您[指定的数据源名称](/docs/data-clean-room-working-with-sources#1-name-the-source)为基础。您可以根据需求更改文件夹名称，但必须符合<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR命名要求</Anchor>。
  * 通过文件夹名称可看出该文件夹位于**input**母文件夹下。“input”文件夹是所有DCR数据源的母文件夹。
    * **input**不是必须配置的文件夹，您可以将其移除或重新命名，但必须符合<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR命名要求</Anchor>。
    * 虽然不是必要配置，但仍建议您设置input文件夹（也可以以其他名称命名）。尤其是使用同一个云端存储桶上传（输入）和接收（输出）数据文件时，更需要设置该文件夹。

> 🚧 **重要提示！**
>
> 如果您选择手动创建该文件夹路径，请确保您在**数据源位置**部分输入的数据连接路径与您手动创建的路径一致。

</Accordion>

<div id="3-define-the-source-structure" />

<Accordion title="21#3：设置数据源结构">

对于您与DCR共享的所有数据源，您需要让AppsFlyer了解其中各字段的使用方式，这样AppsFlyer才能创建相应的报告。请完成以下操作，定义数据源结构：

* [加载数据源字段](/docs/data-clean-room-working-with-sources#加载数据源字段)
* [对每个字段（即列）分类](/docs/data-clean-room-working-with-sources#字段分类)，可选的字段类型有以下几种：
  * \_identifier
    * 标识符在DCR场景中的主要目的是将数据源串联起来，从而完成用户级数据的匹配。
  * dimension 维度：您对应用用户分类时使用的特征信息（如地理位置、激活日期、广告系列等）。/span>/strong>
  * 指标指标：有关某应用用户的数值型数据（如收入、应用打开次数、LTV等）
    * 标识为“指标”的字段仅可包含数值。

<div id="loading-source-fields" />

#### 加载数据源字段

请使用下文中相关的说明加载数据源字段：

**数据仓库中的数据源**

> 🚧 **重要提示！**
>
> 如果您选择的数据表中不包含必要的[日期和版本数据](/docs/data-clean-room-working-with-sources#table-columns)，就会收到报错消息。

**云端存储桶中的数据源**

如需加载云端存储桶（Amazon S3或GCS）中的数据源字段，必须先上传一个数据源文件样本。

请使用以下任一方式设置数据源结构：

* 您可以上传本地的数据源文件样本。
  * 使用此方式时，AppsFlyer总是会自动创建数据源文件夹路径。

                                                                或

* 您也可以直接从数据连接侧上传数据源文件样本。
  * 使用此方式时，还必须完成以下任一操作：
    * 允许AppsFlyer自动创建数据源文件夹结构；或
    * 手动创建数据源文件夹结构

**请根据实际需求按下方相关标签中的说明上传数据源文件样本：**

<Tabs>
<Tab title="本地文件">

2. 在界面新开的窗口中选择**上传本地文件**。
3. 选择您要上传的文件格式（CSV或GZIP），然后点击OK。

</Tab>

<Tab title="数据连接（自动创建）">

如需从数据连接侧上传该文件并允许AppsFlyer自动创建数据源文件夹结构：

2. 在界面新开的窗口中选择**从数据连接侧上传**。
3. 点击“**生成文件夹**”。
   * AppsFlyer会自动在您指定的数据连接中使用您指定的数据源文件夹名称创建相应的文件夹结构和数据源文件夹。
4. 数据源文件夹结构创建完毕后，界面会弹出确认消息，并提供数据源文件夹的链接。点击该链接，然后在该数据源文件夹中上传样本文件。
5. 文件上传完毕后，点击**OK**。

</Tab>

<Tab title="数据连接（手动创建）">

**如需从手动创建的结构中上传数据源文件，请完成以下操作：**

2. 在界面新开的窗口中选择**从数据连接侧上传**。
3. **切勿**点击**生成文件夹**，而是将文件直接上传到您为其创建的数据源文件夹中。
4. 文件上传完毕后，点击**OK**。

</Tab>
</Tabs>

<div id="categorize-fields" />

#### 字段分类

字段加载完毕后，AppsFlyer会解析该文件，并在**可用字段**列表中列出其中的所有字段（列）。

**请按以下步骤对字段进行分类：**

1. 在左侧的**可用字段**列表中选择一个或多个字段，然后使用页面中间的按钮将各字段分为[标识符、维度或指标](/docs/data-clean-room-working-with-sources#3-define-the-source-structure)。
   * 完成字段分类后，相关字段会出现在页面右侧的分类列表中。
   * 您可以使用搜索栏搜索列表中的字段
   * 如需从某个分类中移除一个字段，请在相关分类列表中选择要移除的字段，并点击**移除**按钮，该字段就会重新回到**可用字段**列表中。
2. 重复上述流程，为DCR报告中需要包含的每个字段都进行分类。
   * 您不必为**可用字段**列表中的所有字段都进行分类，但只有分过类的字段才会出现在DCR报告中。
3. 如果您在[保存该数据源](/docs/data-clean-room-working-with-sources#4-save-the-source)之前对其进行了修改，并且需要使用修改后的数据中的字段，请点击**可用字段**列表底部的“**重新加载字段**”。
   * 请注意：重新加载数据源后，可用字段列表中的字段名称会被覆盖。之前已经分过类的字段仍会保留在相应的**标识符**、**维度**或**指标**列表中。
   * 如果重新加载后的数据中不再包含之前已分类的字段，该字段仍会出现在相关的分类列表中，但会以错误图标标记出来。

> 📘 **注意**
>
> 如果您在保存该数据源后，发现还需要使用其他尚未分类的字段，可以通过[修改数据源结构](/docs/data-clean-room-working-with-sources#editing-the-source-structure)来达成该目的。

</Accordion>

<div id="4-save-the-source" />

<Accordion title="21保存数据源">

**请按以下方式保存数据源：**

2. 点击**保存**，保存该数据源。

   数据源创建完毕，界面弹出确认消息。

   * 如果您从本地上传数据源文件，则在保存数据源时系统会触发文件夹结构的自动生成，且界面会弹出确认消息，展示该数据源文件夹的链接。

   在数据净室的**数据源**选项卡中，现有数据源的完整列表下会显示新的数据源。

</Accordion>

<div id="updating-sources-to-trigger-report-processing" />

## 更新数据以触发报告处理流程

每当您需要让AppsFlyer处理数据源文件，并基于其中的信息产出报告时，可以在数据源文件夹下的子文件夹中上传新版本的文件，这些子文件夹的嵌套结构用于标识出日期和版本号（此外还需要一个子文件夹，为AppsFlyer标识出数据所在位置）。

AppsFlyer会反复查找**当天和2天前的**数据源文件更新版本，且每次检测到数据源文件（包括[\_SUCCESS文件](/docs/data-clean-room-working-with-sources#_success-files)，详见下文说明）更新后，就会触发新版本报告的生成。

<div id="nested-subfolders-for-each-date-and-version" />

<Accordion title="分日期和版本的子文件夹">

嵌套式子文件夹的结构如下：

* 在数据源文件夹中 --> 每个日期占用1个子文件夹（即“日期文件夹”）
  * 格式：
  * **比如**
* 每个日期文件夹中 --> 当日的每个数据版本占用一个子文件夹（即“版本文件夹”）
  * 格式：
  * **比如**
  * **请注意：** 请注意：即使您每天只上传一次数据文件，也需要设置版本文件夹。
* 每个版本文件夹中 --> 包含1个用于标识数据所在位置的子文件夹（即“数据文件夹”）
  * 格式：
  * 数据文件夹是数据源文件上传的位置。

一般情况下可使用API或其他程序化工具，在每次上传数据源文件时自动创建日期/版本/数据文件夹。其他相关信息请见相关云服务平台的API参考信息：AWS, GCS。

</Accordion>

<div id="_success-files" />

<Accordion title="_SUCCESS文件">

数据源文件成功上传到相应的数据文件夹后，须向版本文件夹中上传一个名为 `_SUCCESS`\_SUCCESS\_SUCCESS的空文件，用于通知AppsFlyer有新文件需要处理。一般可使用API脚本自动生成并上传该文件。

**重要提示！**\_SUCCESS文件必须上传到数据文件夹外层的`_SUCCESS`版本\_SUCCESS文件夹。

\_SUCCESS文件的命名要求：

* 必须全部为大写字母
* 必须以下划线`(_)`（\_）(\_)开头
* 不能带有扩展名

对于分卷式GZIP文件：

* `_SUCCESS`\_SUCCESS\_SUCCESS文件须在所有分卷上传完毕后方可上传。

</Accordion>

<div id="example-after-uploading-files" />

<Accordion title="示例（文件上传完毕后）">

2天内的数据源文件上传完毕（且以程序化方式创建日期/版本/数据文件夹和`_SUCCESS`\_SUCCESS\_SUCCESS文件）后的存储桶/文件夹结构如下：

<Image alt="dcr_file_structure_after_uploads.png" src="https://files.readme.io/f6e753cdf8389c0b99cad9cbf1a06261473ef87ce6f840a21ab8d9ccea20aed4-11420299723665.png" width="308px" />

</Accordion>

<div id="working-with-existing-sources" />

## 现有数据源的使用方式

现有数据源的使用方式有很多种，您可以根据自己的实际需求选用。您需要从数据净室的**数据源**选项卡中发起相关流程：

* [修改数据源名称](/docs/data-clean-room-working-with-sources#editing-the-source-name)
* [修改数据源结构](/docs/data-clean-room-working-with-sources#editing-the-source-structure)
* [删除数据源](/docs/data-clean-room-working-with-sources#deleting-a-source)（仅限不在使用中的数据源）

<div id="editing-the-source-name" />

<Accordion title="修改数据源名称">

请按以下方式修改数据源名称：

1. 进入**数据净室**中的**数据源选项卡**。
2. 将鼠标悬停在数据源列表中您需要修改的那一行。
4. 在**编辑数据源**页面中修改该数据源的名称。
5. 点击**保存**按钮，用新名称保存该数据源，或点击**取消**按钮，撤销您所做的更改。

</Accordion>

<div id="editing-the-source-structure" />

<Accordion title="修改数据源结构">

请按以下方式修改数据源结构：

1. 进入**数据净室**中的**数据源选项卡**。
2. 将鼠标悬停在数据源列表中您需要修改的那一行。
4. 在**编辑数据源**页面中，之前已经分过类的字段会出现在页面右侧的对应分类列表（[标识符、维度或指标](/docs/data-clean-room-working-with-sources#3-define-the-source-structure)）下。
5. 您可以改变已分类字段的类别，无需再次从数据源文件中重新加载字段。具体方法如下：
   1. 首先，请在相关类别列表中选择要移除的字段，并点击**移除**按钮，该字段会重新回到**可用字段**列表中。
   2. 然后在**可用字段**列表中选择该字段，并使用页面中间的分类按钮将该字段标记为标识符、维度或指标。
6. 如需使用数据源文件中尚未分类的字段，必须从相关数据源位置或本地文件重新加载这些字段。请点击**可用字段**列表底部的**重新加载字段**，然后选择加载方式。
7. AppsFlyer会解析该文件，并在**可用字段**列表中列出所有未分类的字段（列）。
   * 之前已分类的字段会显示在页面右侧的相关分类列表中（即标识符、维度或指标）。
   * 如果重新加载后的数据源文件中不再包含之前已分类的字段，该字段仍会出现在相关的分类列表中，但会以错误图标标记出来。
8. 在左侧的**可用字段**列表中选择一个或多个字段，然后使用页面中间的按钮将各字段分为标识符、维度或指标。
9. 完成必要的更改后，请点击**保存**按钮，使用更新后的结构保存该数据源，或点击**取消**按钮，撤销您所做的更改。

> 🚧 **重要提示！**
>
> 更新数据源结构后，请务必对使用该数据源的报告做出相应的更改：
>
> * 已移除的、未分类的、或已变更分类的字段会自动从相关报告中移除。
> * 新增字段或新近完成分类的字段不会自动出现在现有报告中。如需在报告中看到这些字段，您必须先将其添加到报告定义。

</Accordion>

<div id="deleting-a-source" />

<Accordion title="删除数据源">

1. 进入**数据净室**中的**数据源选项卡**。
2. 将鼠标悬停在数据源列表中您需要删除的那一行。
4. 在弹窗中确认您要删除该数据源。
   * 如果有报告正在使用该数据源，则无法将其删除。发生这种情况时，界面会弹出消息，列出正在使用该数据源的报告。您可以完成以下任一操作，以删除该数据源：
     * 删除正在使用该数据源的报告，或
     * 从这些报告的定义中移除与该数据源相关的字段。

</Accordion>

<div id="reference" />

## 详细说明

<div id="manually-creating-a-folder-structure" />

<Accordion title="手动创建存储桶文件夹结构 （仅在选择手动操作时适用）">

一般情况下，最简便的方法是让AppsFlyer自动生成必要的文件夹结构，从而完成数据源创建流程。但如果您想要手动创建这些文件夹，可以按下问说明进行操作。

<div id="create-a-dcr-key-folder" />

#### 创建一个DCR密钥文件夹

为了提升安全性，存储桶下的直属文件夹（即“DCR密钥文件夹”）的名称必须以您账户下的8字符（字母加数字）**DCR密钥**来命名（如`01bcc5fb`01bcc5fb01bcc5fb）。*请注意，这是DCR专属密钥，独立于您AppsFlyer账户下的任何其他密码或密钥。*

DCR密钥文件夹一般需要通过云服务平台的界面手动创建。

**如需获取您账户的DCR密钥，请点击DCR主页面顶部的DCR密钥按钮。**

[![dcr_key_button.png](https://files.readme.io/8d02c129ce45b19b28523419e43ec8227a9179e3bafb2b84c0a523b247061c19-16571022734353.png)](https://files.readme.io/8d02c129ce45b19b28523419e43ec8227a9179e3bafb2b84c0a523b247061c19-16571022734353.png)

创建DCR密钥文件夹后，您的存储桶/文件夹结构如下：

<Image alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png" width="308px" />

<div id="top-level-input-folder" />

#### 顶层输入型文件夹

创建顶层输入型文件夹时最好将其直接置于DCR密钥文件夹下一层。该文件夹专用于向DCR上传文件。

顶层输入型文件夹一般需要您在自己选用的云服务平台中手动创建。

* 如果您使用同一个存储桶上传（输入）和接收（输出）数据文件，则更需要完成上述设置。
* 您可以用任意的名称为该文件夹命名，但必须符合<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR命名要求</Anchor>。为了便于识别，建议在名称中使用input/。

创建顶层输入型文件夹后，您的存储桶/文件夹架构入下：

<Image alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png" width="308px" />

<div id="second-level-folder-for-each-data-source" />

#### 为各数据源设置第二层文件夹

您可以定期向DCR上传不同来源的数据文件。这时，您需要为每个数据源分配一个单独的文件夹（即“数据源文件夹”）。

数据源文件夹一般需要您在自己选用的云服务平台中手动创建。

上述2个数据源文件夹创建完毕后，您的存储桶/文件夹结构如下：

<Image alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png" width="307px" />

必须在每次数据源发生更新时[在各个数据源文件夹下按日期和版本](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version)创建子文件夹。

</Accordion>

<div data-zendesk-anchors="introduction=%E7%AE%80%E4%BB%8B h_01HPKB2ERNRQG73AFA0X7XEDEF=%E7%AE%80%E4%BB%8B h_01HPKB2ERPGD2PS4JBSDGYW3MC=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01HPKB2ERPANE0CAXFP9RG5YEH=source-format h_01HPKB2ERPJ5PVQ2QM5XCYZE0D=table-columns h_01HPKB2ERPWZFZN2DSCHWNXKXX=file-format creating-a-source=%E5%88%9B%E5%BB%BA%E6%95%B0%E6%8D%AE%E6%BA%90 h_01HPKB2ERPX2T413N3T93YBBZB=%E5%88%9B%E5%BB%BA%E6%95%B0%E6%8D%AE%E6%BA%90 h_01HPKB2ERPQMT0NKTE5NN40KG4=1-name-the-source h_01HPKB2ERQWDMYBEPDZY17T9PG=2-specify-the-source-location source-locations-in-bigquery=bigquery%E4%B8%AD%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE h_01HPKB2ERQ28JQ2CK16RYZ38G6=bigquery%E4%B8%AD%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE source-locations-in-snowflake=snowflake%E4%B8%AD%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE h_01HPKB2ERQWFGF8MN8ZYAXWC87=snowflake%E4%B8%AD%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE source-locations-in-cloud-storage-buckets=%E4%BA%91%E7%AB%AF%E5%AD%98%E5%82%A8%E6%A1%B6%E4%B8%AD%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE h_01HPKB2ERQZT3Y6GNZ2WWWM0M7=%E4%BA%91%E7%AB%AF%E5%AD%98%E5%82%A8%E6%A1%B6%E4%B8%AD%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE h_01HPKB2ERQK2HFDATGKV0X7GCG=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HPKB2ERQ40VTVZA5DGNR907G=3-define-the-source-structure loading-source-fields=%E5%8A%A0%E8%BD%BD%E6%95%B0%E6%8D%AE%E6%BA%90%E5%AD%97%E6%AE%B5 h_01HPKB2ERQTJPGG68FSEBHVVJA=%E5%8A%A0%E8%BD%BD%E6%95%B0%E6%8D%AE%E6%BA%90%E5%AD%97%E6%AE%B5 h_01HPKB2ERRZNPYVVD8GHD7PBPE=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 categorize-fields=%E5%AD%97%E6%AE%B5%E5%88%86%E7%B1%BB h_01HPKB2ERSYCFE1EYTCK550VTK=%E5%AD%97%E6%AE%B5%E5%88%86%E7%B1%BB h_01HPKB2ERSNT8Y9QPN03HJKHCD=%E6%B3%A8%E6%84%8F h_01HPKB2ERS55YGWY3RMRPR02Y4=4-save-the-source uploading-source-files-to-trigger-report-processing=%E6%9B%B4%E6%96%B0%E6%95%B0%E6%8D%AE%E4%BB%A5%E8%A7%A6%E5%8F%91%E6%8A%A5%E5%91%8A%E5%A4%84%E7%90%86%E6%B5%81%E7%A8%8B h_01HPKB2ERSCPAPB6WE3354ECW9=%E6%9B%B4%E6%96%B0%E6%95%B0%E6%8D%AE%E4%BB%A5%E8%A7%A6%E5%8F%91%E6%8A%A5%E5%91%8A%E5%A4%84%E7%90%86%E6%B5%81%E7%A8%8B h_01HPKB2ERSEVBTS3DR2TB6Y1AQ=nested-subfolders-for-each-date-and-version h_01HPKB2ERSJ9KNDK6CEBRQB65C=_success-files h_01HPKB2ERSJKGVE61T6J9HXTCK=example-after-uploading-files working-with-existing-sources=%E7%8E%B0%E6%9C%89%E6%95%B0%E6%8D%AE%E6%BA%90%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HPKB2ERS5PK2P2XTC4ZMPCMC=%E7%8E%B0%E6%9C%89%E6%95%B0%E6%8D%AE%E6%BA%90%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HPKB2ERTC48MGS0BM5SDR6XV=editing-the-source-name h_01HPKB2ERTS6DEQX0KP0EQTGSP=editing-the-source-structure h_01HPKB2ERTYP6BFAESN3MHZSQG=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2 h_01HPKB2ERVGJYJ9KW1RGX24CGV=deleting-a-source reference=%E8%AF%A6%E7%BB%86%E8%AF%B4%E6%98%8E h_01HPKB2ERV1KK3J8YX918GCF3M=%E8%AF%A6%E7%BB%86%E8%AF%B4%E6%98%8E h_01HPKB2ERVZ88MJ35JC66YDPAB=manually-creating-a-folder-structure creating-a-dcr-key-folder=%E5%88%9B%E5%BB%BA%E4%B8%80%E4%B8%AAdcr%E5%AF%86%E9%92%A5%E6%96%87%E4%BB%B6%E5%A4%B9 h_01HPKB2ERV7MQJ9CK44T92GK2G=%E5%88%9B%E5%BB%BA%E4%B8%80%E4%B8%AAdcr%E5%AF%86%E9%92%A5%E6%96%87%E4%BB%B6%E5%A4%B9 toplevel-input-folder=%E9%A1%B6%E5%B1%82%E8%BE%93%E5%85%A5%E5%9E%8B%E6%96%87%E4%BB%B6%E5%A4%B9 h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=%E9%A1%B6%E5%B1%82%E8%BE%93%E5%85%A5%E5%9E%8B%E6%96%87%E4%BB%B6%E5%A4%B9 secondlevel-folder-for-each-data-source=%E4%B8%BA%E5%90%84%E6%95%B0%E6%8D%AE%E6%BA%90%E8%AE%BE%E7%BD%AE%E7%AC%AC%E4%BA%8C%E5%B1%82%E6%96%87%E4%BB%B6%E5%A4%B9 h_01HPKB2ERVVFMP81RE8ATZ6SZ8=%E4%B8%BA%E5%90%84%E6%95%B0%E6%8D%AE%E6%BA%90%E8%AE%BE%E7%BD%AE%E7%AC%AC%E4%BA%8C%E5%B1%82%E6%96%87%E4%BB%B6%E5%A4%B9" />

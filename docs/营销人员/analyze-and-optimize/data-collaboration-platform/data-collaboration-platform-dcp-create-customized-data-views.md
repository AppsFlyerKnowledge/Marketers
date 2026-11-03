---
title: 数据协作平台 (DCP) - 创建自定义数据视图
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
  created_at: '2024-11-22T12:57:55Z'
  edited_at: '2026-10-14T10:08:00Z'
  id: 30296051098897
  locale: zh-cn
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/zh-cn/articles/30296051098897
---
> **概要：** 使用转换和聚合函数以及数据过滤工具从数据源创建自定义数据视图。您可以预览修改后的数据样本，反映您在进展中的更改。

## 速览

数据视图构建器使您能够创建数据源的自定义版本，并使其与您预期的受众相关，而无需修改原始数据集。不需要 SQL 知识、数据专家或数据工程师，允许您在预览数据并进行调整的同时执行修改、精炼和汇总数据的功能。

### 数据视图功能

数据视图构建器工具包括以下功能：

* **转换:** 修改数据的格式、结构或值，以便为分析做好准备。这会创建新列，以纳入现有数据的见解。
* 汇总结合多个数据记录，使用求和、平均、计数、最小值和最大值等函数生成摘要或组。
* **过滤:** 通过应用所选属性（如时间范围、类别或自定义参数）来缩小数据范围，以专注于特定相关信息。

## 数据视图构建器

[![](https://files.readme.io/281dbd296fee9118ca4dc9729a624f9127e9b4d05436448f06d235e2a7d762ea-51911637005457.png)](https://files.readme.io/281dbd296fee9118ca4dc9729a624f9127e9b4d05436448f06d235e2a7d762ea-51911637005457.png)

数据视图构建器页面包括两个部分：

### 主要部分

在此部分中，您可以找到创建数据视图的元素，这些元素由三个关键组件组成：

* 说明命名并描述数据视图
* **自定义数据:** 应用功能和过滤器以自定义数据
* 选择字段通过删除不必要的字段或调整字段类型来选择数据视图结构。

### 侧边栏

页面右侧的侧边面板展示了两组数据，一组来自原始来源，另一组来自由此创建的数据视图。每组包括表名和描述、字段数量和行数，以及包含五行数据的示例表。当对数据视图应用函数和过滤器时，侧边面板会反映这些变化，使您能够在修改数据时验证数据，并与原始版本进行比较。

## 设置数据视图

了解如何在AppsFlyer中创建和自定义数据视图，以转换、聚合和过滤数据，使其与您的目标受众相关，而无需修改原始数据集。

<div id="set-the-data-view-general-details" />

<Accordion title="设置数据视图的一般详细信息">

1. 在AppsFlyer中，从侧边菜单中选择 **协作** > **数据清理室**。
2. 在 **来源** 标签中，将鼠标悬停在要用于创建数据视图的来源上，然后点击 <Image alt="ellipsis.png" src="https://files.readme.io/d3e33f1864edb1d9d2f8e18c9c7887454018a67e9f7fed054e7134231dba60a2-30296671836433.png" width="0.6%" /> （菜单图标），位于行末。
3. 选择 **创建数据视图**。您将被引导到 **新数据视图** 页面。
4. 设置以下字段：
   * 数据视图名称输入数据视图的名称。这可以是任何唯一的名称，帮助您识别它。请参见下面的 [命名要求和指南](#命名要求和指南)。
   * 说明提供描述。当将鼠标悬停在 **来源** 标签下的数据视图名称上时，这将作为工具提示显示。建议突出主要目标和执行的数据操作。
   * **添加标签：** 您可以选择最能代表视图的结构和数据的标签。

#### 命名要求和指南

* 确保名称在您帐户中的所有其他源和子源中是唯一的。否则，您将无法保存它。
* 对于云集成，名称不需要与文件名匹配。
* 名称要求：
  * 长度1000个字符。
  * 有效字符：
    * 字母（A-Z、a-z）
    * 数字*（0-9）*，不能作为名称中的第一个字符
  * 无效字符：
    * 空格
    * 下划线，
    * 所有其他符号和特殊字符

</Accordion>

<div id="transform-aggregate-and-filter-data" />

<Accordion title="自定义数据">

应用下面的工具来自定义您的数据：

* **转换** 和 **聚合** 函数：用于创建您的自定义字段。每个新创建的字段将作为列添加到您的数据视图中。
* 筛选条件使用选定的属性来缩小数据范围，专注于相关信息。

在此过程中，您可以在 [侧边面板](#侧边栏) 中预览修改后的数据样本。

> 📘 **注意**
>
> * 虽然可以在任何时候添加过滤器，但当存在聚合函数时，过滤器将在这些函数执行后应用于数据。
> * 在对日期类型字段（列）使用函数或过滤器时，请确保日期值符合所选函数特定支持的日期格式。任何差异可能导致在提供的选项中做出次优选择。

<div id="transform-and-aggregate-your-data" />

<Accordion title="转换和聚合您的数据">

**要创建转换或聚合字段：**

1. 在 **转换与聚合** 下，单击 **创建字段**。
2. 选择 **转换** 或 **聚合** 选项卡，然后单击 + **新字段**。
3. 输入字段名称。
4. 单击 **设置函数**，并从 [函数列表](#list-of-functions-and-use-case-examples) 中选择一个函数。输入所需信息的相关字段会自动添加。
5. 对于**聚合**字段：

   [可选] 点击 **+ 条件**以应用在函数执行之前聚合发生的条件。

   **请注意：**

   该条件适用于**所有聚合函数**。
6. [可选] 点击 **+ 新字段**以添加更多**转换**或**聚合**字段。您可以根据需要添加任意数量。

创建后，新字段：

* 出现在 [转换与聚合](#transform-aggregate-and-filter-data)部分。
* 包含在所有函数和过滤器可用字段的列表中。
* 包含在[选择字段](#select-fields) 部分的字段列表中。
* 在点击“刷新”图标时反映在[侧边面板](#侧边栏)中，更新样本表和列或行的数量。

</Accordion>

<div id="filter-your-data" />

<Accordion title="过滤您的数据">

您可以通过使用选定的属性应用过滤器来缩小数据范围，帮助您专注于特定和相关的信息。

> 📘 **注意**
>
> 当聚合函数被添加或更新时，过滤器仅在执行后应用于数据。

应用筛选选项

1. 在**过滤器**下，点击**过滤您的数据**。
2. 点击**选择列**并选择要过滤的列。
3. 点击**操作符** > **等于**或**不等于**。
4. 输入一个值
5. [可选] 点击 **+ 条件**以向过滤器添加条件。

   > 📘 **注意**
   >
   > * 您可以根据需要添加任意数量的条件，使用AND和OR操作。
   > * 多个条件根据标准逻辑顺序处理，优先考虑AND操作。


</Accordion>

<div id="list-of-functions-and-use-case-examples" />

<Accordion title="函数列表和用例示例">

#### **转换函数**

* 如果一个条件语句，根据指定条件是否为真或假执行不同的操作。
* CONCAT合并两个字符串
* CONST返回 CONCAT 函数的参数
* LEAST返回两个值中的最低值
* GREATEST返回两个值中的最高值

#### **示例：转换**

您想指示从合作者处购买的产品，同时掩盖与您合作的其他品牌的购买。

[![](https://files.readme.io/1ce74573ea075baa4d7bf8299abc7dbf01fdb4afce870bc9282ed7c3ab1f5bd9-51911620451217.png)](https://files.readme.io/1ce74573ea075baa4d7bf8299abc7dbf01fdb4afce870bc9282ed7c3ab1f5bd9-51911620451217.png)

#### **聚合函数**

* 数量返回行数。
* 加总返回所有值的总和。
* AVG返回所有值的平均值。
* 最小值返回两个数字的最小值
* 最大值返回两个数字的最大值

#### **示例：汇总**

您想计算每个用户的总购买次数，并汇总他们支付的总价格。

[![](https://files.readme.io/e9ed7aa29fb6e25d16076089b848496aa9a42355ceba17c18210d0d6596a677f-51911637008017.png)](https://files.readme.io/e9ed7aa29fb6e25d16076089b848496aa9a42355ceba17c18210d0d6596a677f-51911637008017.png)

#### 示例：带条件的聚合

您想获取位于德国的用户最近购买的 P&G 产品的数据。

[![](https://files.readme.io/9d7e3774e21d6f48deeef05eb3f1ef98de4cc44b590cb23603e8ed8679f8a7fd-51911620451729.png)](https://files.readme.io/9d7e3774e21d6f48deeef05eb3f1ef98de4cc44b590cb23603e8ed8679f8a7fd-51911620451729.png)

</Accordion>

</Accordion>

<div id="select-fields" />

<Accordion title="选择字段">

数据视图结构包括来自原始数据源的字段和在数据视图构建器中创建的任何自定义数据字段。在这里，您可以删除字段（标识符字段除外）或重新排列它们的顺序。

> 📘 **注意**
>
> * 在应用聚合函数时删除字段会降低数据粒度，这可能会影响数据视图中的结果。
> * 当聚合函数应用于字段时，这些字段将从列表中移除，并放置在 **已移除** 部分，无法恢复。这发生是因为该函数已将这些字段中的数据合并。
> * 保存新数据视图后，所有被移除的字段将不再可见，您无法恢复它们。
> * 调整字段类型只能从原始来源进行，而不能从数据视图中进行。

<div id="adjust-field-types" />

<Accordion title="调整字段类型">

查看每个字段，并从旁边的下拉列表中选择适当的数据类型以进行更改。

</Accordion>

<div id="remove-fields" />

<Accordion title="移除字段">

您可以移除任何字段，除了标识符字段。

**要移除一个字段：**

1. 将鼠标悬停在您想要移除的字段的右侧。
2. 单击出现的垃圾桶图标。该字段现在出现在**已移除**部分，并有一个**恢复**按钮，允许您恢复被移除的字段。
3. 点击[保存](#save-your-data-view)。

</Accordion>

<div id="restoring-temporarily-removed-fields" />

<Accordion title="恢复临时移除的字段">

当一个字段从列表中移除时，它会被放置在**已移除**部分。只要您没有保存数据视图，您可以通过单击**恢复**按钮来恢复它。

</Accordion>

</Accordion>

<div id="save-your-data-view" />

<Accordion title="保存数据视图">

您可以在任何阶段保存数据视图。一旦保存，它将被添加到源列表中的原始数据源下，您可以[编辑、共享或删除它](#编辑数据视图)。

> 📘 **注意**
>
> 当保存新的数据视图时，任何[已移除的字段](#remove-fields)将不再可见。这意味着您无法恢复它们。但是，您始终可以使用原始数据源创建另一个数据视图。

**要保存数据视图：**

* 点击 **保存** 在页面底部。

</Accordion>

## 编辑数据视图

数据视图出现在 **来源** 标签中，位于原始来源下。您可以编辑、删除或与合作者共享它们。

<div id="edit-details" />

<Accordion title="编辑一般细节">

您可以修改数据视图描述或描述中使用的标签。

1. 在AppsFlyer中，从侧边菜单中选择 **协作** > **数据清理室**。
2. 在 **来源** 标签中，点击来源名称。相关的数据视图将显示。
3. 将鼠标悬停在数据视图上以进行修改，然后点击 [<Image alt="编辑子域名.png" src="https://files.readme.io/ffe3da7d1c065a806a44c607bcf1231e06bf7e7478ca50187e57cb5ab876ae72-30192959751185.png" width="2.39%" />](/docs/data-collaboration-platform-dcp-create-customized-data-views#share-a-data-view)（编辑图标）在行末。
4. 编辑描述或应用的标签。

</Accordion>

<div id="edit-customization-fields" />

<Accordion title="编辑自定义字段">

您可以调整功能和过滤器，创建新字段，编辑现有字段，或从数据视图中删除字段。

**要编辑转换或聚合字段：**

1. 在 **自定义数据** 下，点击 **管理字段**。
2. 从 [转换与聚合](#transform-aggregate-and-filter-data) 标签中选择相关字段进行编辑并进行必要的更改。
3. 点击**保存**。

**要编辑过滤器：**

* 在 **自定义数据** > [过滤器](#filter-your-data) 下，对过滤器及其条件应用必要的更改。

**注意：** 当转换或聚合功能被更新时，任何过滤器仅在其执行后应用于数据。

</Accordion>

<div id="edit-structure" />

<Accordion title="编辑字段">

* 在 [选择字段](#select-fields) 下，进行必要的更改。

</Accordion>

<div id="delete-a-data-view" />

<Accordion title="删除数据视图">

删除数据视图时，适用以下内容：

* 数据视图从列表中移除
* 任何关联的受众变为 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-build-and-activate-audiences#观众状态">过期</Anchor> 并显示为灰色
* 任何关联的 [共享数据](#share-a-data-view) 变为未共享

**要删除数据视图：**

1. 在AppsFlyer中，从侧边菜单中选择 **协作** > **数据清理室**。
2. 在 **来源** 标签中，点击来源名称。相关的数据视图将显示。
3. 将鼠标悬停在您想要删除的数据视图上，然后点击 <Image alt="delete.jpeg" src="https://files.readme.io/9ba72d22f765e7fc7f0f8c17a53aa3bc15111e410bfb82d809a62b2a9021fc76-51911637009809.jpg" width="2.3%" />（垃圾桶图标）在行的末尾。
4. 在删除确认窗口中，点击 **删除**。数据视图已被删除。

</Accordion>

<div id="share-a-data-view" />

<Accordion title="共享数据视图">

与合作者共享您的数据视图并提供权限。

1. 在AppsFlyer中，从侧边菜单中选择 **协作** > **数据清理室**。
2. 在 **来源** 标签中，点击来源名称。相关的数据视图将显示。
3. 将鼠标悬停在您想要共享的数据视图上，然后点击 <Image alt="share-icon.jpeg" src="https://files.readme.io/83b3d977775b0e2bdf4a096eab856990c52cc65bb95408b68f3db25e039ba480-51911637010065.jpg" width="3.01%" />（共享图标）在行的末尾。
4. 输入合作者的电子邮件地址，然后点击 **下一步**。
5. 选择相关的 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#共享权限">共享权限</Anchor>。
6. 点击 **保存并发送**。

> 📘 **注意**
>
> 您只能共享从您的来源创建的数据视图。从共享来源创建的视图不能与他人共享。

</Accordion>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 01JD9Z4WKKDWS2EQND0SY7EADZ=%E9%80%9F%E8%A7%88 data-view-functions=%E6%95%B0%E6%8D%AE%E8%A7%86%E5%9B%BE%E5%8A%9F%E8%83%BD 01JD9Z4WKMTZ18E13E6V3KZYB3=%E6%95%B0%E6%8D%AE%E8%A7%86%E5%9B%BE%E5%8A%9F%E8%83%BD the-data-view-builder=%E6%95%B0%E6%8D%AE%E8%A7%86%E5%9B%BE%E6%9E%84%E5%BB%BA%E5%99%A8 01JD9Z4WKNREMCMB9PNSVVQ024=%E6%95%B0%E6%8D%AE%E8%A7%86%E5%9B%BE%E6%9E%84%E5%BB%BA%E5%99%A8 main-section=%E4%B8%BB%E8%A6%81%E9%83%A8%E5%88%86 01JD9Z4WKQQXPN1SBK5K5C8ZGC=%E4%B8%BB%E8%A6%81%E9%83%A8%E5%88%86 side-panel=%E4%BE%A7%E8%BE%B9%E6%A0%8F 01JD9Z4WKRTXMMBBPS41AXHPE1=%E4%BE%A7%E8%BE%B9%E6%A0%8F set-a-data-view=%E8%AE%BE%E7%BD%AE%E6%95%B0%E6%8D%AE%E8%A7%86%E5%9B%BE 01JD9Z4WKRD4V4A07WT5YG42RZ=%E8%AE%BE%E7%BD%AE%E6%95%B0%E6%8D%AE%E8%A7%86%E5%9B%BE 01JD9Z4WKWQJJE9Q8EMQY8NCMD=set-the-data-view-general-details naming-requirements=%E5%91%BD%E5%90%8D%E8%A6%81%E6%B1%82%E5%92%8C%E6%8C%87%E5%8D%97 01JD9Z4WKX3BGN7V9V1V1YBYWT=%E5%91%BD%E5%90%8D%E8%A6%81%E6%B1%82%E5%92%8C%E6%8C%87%E5%8D%97 01JD9Z4WM1EQVKS9B4EHMTHW41=transform-aggregate-and-filter-data 01JD9Z4WM2TMAX43HEP7J68E0Y=%E6%B3%A8%E6%84%8F 01JD9Z4WM4RP9HVF171YH7BFQZ=transform-and-aggregate-your-data 01JD9Z4WM9TP35VPCNMQ98Z8R1=filter-your-data 01JDEVJ95NXPNDT8VMX0YS179S=%E6%B3%A8%E6%84%8F-1 01JDEVRX2EV64YQN2JE901CEK8=%E6%B3%A8%E6%84%8F-2 01JD9Z4WMDV8B7P8W5E13J7HNJ=list-of-functions-and-use-case-examples transformation-functions=%E8%BD%AC%E6%8D%A2%E5%87%BD%E6%95%B0 h_01JDA45VWKH2ZKVBTK87VFVKTB=%E8%BD%AC%E6%8D%A2%E5%87%BD%E6%95%B0 example-transformation=%E7%A4%BA%E4%BE%8B%E8%BD%AC%E6%8D%A2 h_01JDA4611HFFEA17352NSNCJYX=%E7%A4%BA%E4%BE%8B%E8%BD%AC%E6%8D%A2 aggregate-functions=%E8%81%9A%E5%90%88%E5%87%BD%E6%95%B0 h_01JDA467NV99FDAXJCXYSD5PBF=%E8%81%9A%E5%90%88%E5%87%BD%E6%95%B0 example-aggregation=%E7%A4%BA%E4%BE%8B%E6%B1%87%E6%80%BB h_01JDA46DWD6G3S4S5FM48KWQXA=%E7%A4%BA%E4%BE%8B%E6%B1%87%E6%80%BB example-aggregation-with-a-condition=%E7%A4%BA%E4%BE%8B%E5%B8%A6%E6%9D%A1%E4%BB%B6%E7%9A%84%E8%81%9A%E5%90%88 01JDETVS9XQ9XCNEFVCSC8GAJR=%E7%A4%BA%E4%BE%8B%E5%B8%A6%E6%9D%A1%E4%BB%B6%E7%9A%84%E8%81%9A%E5%90%88 01JD9Z4WMJ9XFBXPJAM6RNRP96=select-fields 01JD9Z4WMJJGXG9XXSW6Q6S5KE=%E6%B3%A8%E6%84%8F-3 01JD9Z4WMKA2J94AYW9VXKKVKQ=adjust-field-types 01JD9Z4WMM4QQDP749R7H93Z67=remove-fields 01JD9Z4WMNHXCP4Q66C1TN67Y4=restoring-temporarily-removed-fields 01JD9Z4WMQGY8DCEWMPGX8FC2Y=save-your-data-view 01JDA2A87AC37C41ADJ9BHRW0H=%E6%B3%A8%E6%84%8F-4 manage-data-views=%E7%BC%96%E8%BE%91%E6%95%B0%E6%8D%AE%E8%A7%86%E5%9B%BE 01JD9Z4WMRFS0S408ZJ2YKBZF3=%E7%BC%96%E8%BE%91%E6%95%B0%E6%8D%AE%E8%A7%86%E5%9B%BE 01JD9Z4WMT7GG4JV91JE5KAJ4X=edit-details 01JD9Z4WMVN8VXF3R471XSR0CG=edit-customization-fields 01JD9Z4WMYY6ZJ78S5ZH8QHFQY=edit-structure 01JD9Z4WMZGV916XJ77V3NR1HK=delete-a-data-view 01JD9Z4WN3VX56JDWK937D1WXH=share-a-data-view 01JDA2A87RG8V8RZW4EB1B2K56=%E6%B3%A8%E6%84%8F-5" />

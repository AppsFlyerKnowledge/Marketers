---
title: SKAN中的CV值解析（CV值与事件的映射配置）
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-26T20:31:40Z'
  edited_at: '2026-10-14T10:05:02Z'
  id: 360014696297
  locale: zh-cn
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/zh-cn/articles/360014696297
---
> **概要：** AppsFlyer可将您配置的转化值解析为具体事件，并将这些事件信息填充到SKAN面板、原始数据报告以及渠道回传中。

![SKAdNetwork_-_Custom__1_.png](https://files.readme.io/74f0d3836ee6a73f6746afa2d6d6a468c09cba696561c5a2075149ca360b78bf-34255690318097.png)

## 解析SKAN转换值

如果广告主不想使用<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">转化值操作台</Anchor>中提供的选项，可以将转化值解析作为一种替代方案。若您选择使用解析模式（Decode），须自行负责<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/4097267-updatepostbackconversionvalue">updatePostbackConversionValue</Anchor>的设置，使其符合相关应用的业务逻辑。

除了应用中的转化值（CV）配置之外的其他流程、功能以及数据上报方式都与<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">SKAN解决方案指南</Anchor>中所述一致。也就是说，由广告主设定的用户行为窗口期结束后，iOS会向广告平台发送回传，并由平台转发给AppsFlyer。AppsFlyer会根据您的映射配置将转化值解析为事件，与SDK解析CV值的处理方式相同。

## 自定义CV值解析（Decode）

启用自定义的CV解析时，您需要上传一个CSV文件，其中包含针对AppsFlyer的CV值映射配置。

**解析映射原理**

* 您需要为第1-3个窗口期设置精细转化值（1-63）和粗略转化值（Low, Medium和High）的解析映射方式。不要求必须映射所有转化值，比如可以仅映射1、2、10和43。
* 0值的CV总是映射到激活，无法更改。
* 您需要将映射配置表以CSV文件的方式上传到AppsFlyer。您可以按实际需求编辑并上传映射配置表。
* 收到iOS的回传后，AppsFlyer会将CV值解析为事件，详见下文示例说明。
* 激活日期根据回传送达的时间推算得出。
* 事件时间与激活时间相同。
* 为了便于您更好地理解映射构架的配置方式，下文列出了映射场景说明，供您参考。
* 您可以使用<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">自定义的应用内事件</Anchor>名称。
  * 包括SDK从未发送过的全新事件名称。
  * 您可以将这些应用内事件映射到广告平台侧对应的事件。
  * Meta ads对接也支持自定义事件名称，但须遵循下文所述的Meta对接要求。

<div id="decode-mapping-scenario-rules" />

<Accordion title="解析模式中的映射配置要求">

注意事项：

* 可用的精细转化值：1-63
* 可用的粗略转化值：Low（低）、Medium（中）、High（高）
* 某个具体转化值可对应到您指定的一个或多个应用内事件。您可以选择为应用内事件添加参数。
* 在下文示例中，假设激活日期为2月1日08:00。
* 请参考下文的解析模式映射表示例。该表格的结构与您需要上传的CSV文件相同。表格下方展示了解析完成后得到的事件。
* 无论您配置了怎样的映射关系，解析后总是会生成一个激活事件。
* 收入衡量：
  * 收入金额以美元（USD）计算。
  * 某个具体转化值所代表的收入范围通过min\_revenue和max\_revenue表达。
  * 汇总报告和面板按此范围的平均值计算收入。举例来说，假设min\_revenue=4，且max\_revenue=10，则计算出得出的收入为7。
  * 原始数据报告中包含计算后得出的收入（skad\_revenue）、min\_revenue以及max\_revenue。

#### **针对Meta ads对接的要求**

如果您对接了Meta ads，请按以下要求配置映射架构：

* 某个具体转化值所对应的收入范围中，最小值和最大值不能相等，必须使用不同的值。
* 收入范围之间不能有重叠，并且必须依次构成连续的数值。请参考下表中conversion\_value为1、2和62时对应的收入范围。
* event\_counter：Meta ads不会计算该参数值。【最佳配置】：用1值填充该参数。

### 示例：解析模式下的映射配置

| conversion\_  <br />value | event\_  <br />name | event\_  <br />value | min\_revenue<br /><br />（不含） | max\_revenue（含） | event\_  <br />counter | hours\_from\_  <br />install |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | af\_purchase | `{abc}` | 0 | 3 | 1 | 24 |
| 2 | af\_purchase | `{def}` | 3 | 10 | 3 | 36 |
| 21 | event\_a |  |  |  | 1 | 24 |
| 21 | event\_b |  |  |  | 3 | 24 |
| 21 | event\_c | `{xyz}` |  |  | 2 | 24 |
| 21 | event\_d |  |  |  | 1 | 24 |
| 21 | event\_e |  |  |  | 1 | 24 |
| 21 | event\_f |  |  |  | 1 | 24 |
| 21 | event\_g |  |  |  | 1 | 24 |
| 62 | af\_purchase | \{fgh) | 10 | 17 | 2 | 72 |
| 62 | event\_a | `{klm}` |  |  | 3 | 72 |

### 示例A：精细转化值为1

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 1.5 | 0 | 3 | `{abc}` |

### 示例B：精细转化值为2

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 65 | 3 | 10 | `{def}` |
| af\_purchase | 65 | 3 | 10 | `{def}` |
| af\_purchase | 65 | 3 | 10 | `{def}` |

### 示例C：精细转化值为21

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| event\_a |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_c |  |  |  | `{xyz}` |
| event\_c |  |  |  | `{xyz}` |
| event\_d |  |  |  |  |
| event\_e |  |  |  |  |
| event\_f |  |  |  |  |
| event\_g |  |  |  |  |

### 示例D：精细转化值为62

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 13.5 | 10 | 17 | `{fgh}` |
| af\_purchase | 13.5 | 10 | 17 | `{fgh}` |
| event\_a |  |  |  | `{klm}` |
| event\_a |  |  |  | `{klm}` |
| event\_a |  |  |  | `{klm}` |

</Accordion>

<div id="decode-csv-file-specification" />

<Accordion title="解析模式中的CSV文件内容及格式要求">

CSV文件的内容须反映转化值的映射方式，一个转化值可以映射到一个或多个应用内事件。

**文件内容及格式要求**

* 格式：CSV文件
* 行数上限：640 + 标题行；共641行。
* 标题行中的栏位必须与下表所列的栏位完全一致。建议您使用超链接中的CSV示例文件作为模板，完成<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=0&single=true&output=csv">SKAN 3</Anchor>和<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=1187444449&single=true&output=csv">SKAN 4</Anchor>的解析模式映射配置。
* 栏位字段切勿以下列字符开头：`=`、`+`、`-`和`@`。

### 解析模式中的CSV文件内容及格式要求

| 栏位 | 是否必须配置 | 内容 | 说明 |
| --- | --- | --- | --- |
| conversion\_value | 在下列场景中必须配置：<ul><li>使用SKAN 3及以下</li><li>SKAN 4中postback\_sequence\_index为0时</li></ul> | 1–63的整数值 | 同一个精细转化值可对应多个事件。详见示例说明。 |
| coarse\_conversion\_value | 仅适用于SKAN 4 | 字符串：<ul><li>low</li><li>medium</li><li>high</li></ul> | 同一个粗略转化值可对应多个事件。 |
| event\_name | 是 | 字符串 | 即应用内事件的名称。可以是AppsFlyer SDK从未上报过的事件。<br /><br />请注意：应用内事件名称区分大小写。<br /><br />【推荐方式】：建议将收入事件的名称设置为af\_skad\_revenue。 |
| event\_value | 否 | 字符串 | 由开发人员设置的字符串，其中的数据需由广告主侧的内部系统解析。这些字符串一般为JSON格式。 |
| min\_revenue | 否 | 整数或浮点数 | 请使用min\_revenue和max\_revenue来设置以美元为单位的收入范围。<ul><li>如果转化值不需要关联到收入，请将min\_revenue和 max\_revenue设置为空值。</li><li>min\_revenue的值不包含在收入范围内。比如该参数的值为0时，其收入范围中的最小值无限接近并大于0，类似于0.0001。</li><li>max\_value的值包含在收入范围中。</li><li>示例：假设min\_revenue为0且 max\_revenue为4，则收入范围是0.0001-4</li><li>max\_revenue必须大于min\_revenue</li></ul>**请注意：** 如果您使用Excel编辑文件，请先在列格式中设置逗号分隔符，然后再保存。切勿使用货币格式，否则Excel会自动在生成的CSV文件中添加$符号。 |
| max\_revenue | 否 |  | 如果您设置了非空值的min\_revenue，则max\_revenue的值必须大于 0。<br /><br />详见min\_revenue部分的说明。 |
| event\_revenue\_usd | 否 |  | 自2021年6月7日起已弃用。请使用min\_revenue和max\_revenue |
| event\_counter | 是 | 整数 | <ul><li>解析后得出的事件重复次数，通常表示用户完成某个操作的次数。</li><li>最小值为1。</li></ul>示例：如果用户完成某事件共5次，则会生成5个事件。<br /><br />注意事项：如果您发送收入，则最终上报的总收入是事件收入乘以 event\_counter值得出的金额（以美元计）。举例来说，假设min\_revenue = 0、max\_revenue = 3且event\_counter = 4，则上报的总收入为1.5 X 4 = 6。<br /><br />详见示例说明。 |
| hours\_from\_install | 是 | 整数 | <ul><li>激活后的小时数</li><li>最小值：1</li><li>最大值：1512（63天）</li><li>如果一个转化值对应多个事件，则所有这些事件（行）中该参数的值必须完全一致。不同转化值所对应的事件中，该参数的值可以不同。</li></ul>AppsFlyer会使用该信息来推算并设置激活日期，具体如下：<ul><li>根据SKAN 4的回传推算激活日期的方式如下：激活日期 = 回传送达时间 - [累计窗口期时长] - [平均回传延时]。<ul><li>第1次回传：激活日期 = 回传接收时间 - 48h - 36h</li></ul></li><li>根据SKAN 3的回传推算激活日期的方式如下：激活日期 = 回传送达时间 - 36小时 - [用户上次打开应用的时间距激活的平均小时数]。<ul><li>上述公式中的平均激活后小时数默认为12小时。</li><li>对于转化值为0的事件（即激活），则平均激活后小时数为0。</li></ul></li></ul> |
| postback\_sequence\_index | 仅在SKAN 4中是必须配置的参数 | 整数：<ul><li>0</li><li>1</li><li>2</li></ul> | 对于精细转化值，该参数的值只能为0。 |

</Accordion>

<div id="upload-conversion-value-schema-file" />

<Accordion title="上传转化值映射架构文件">

**前期准备** ：

* 制备CSV格式的转化值映射架构文件。
* 如果您对接了Meta ads且需要衡量收入，请确保您的映射架构符合[Meta ads的配置要求](/docs/skan-cv-decode-map-your-cv-to-events#针对meta-ads对接的要求)，否则Meta ads无法使用该架构解析映射关系。

**请按以下方式启用解析模式（Decode）进行SKAN衡量：**

1. 从AF后台进入**配置** > **SKAN转化值操作台**。
2. 点击选项图标（⋮），选择**上传自定义解析规则文件**。
3. 如果您尚未升级到SKAN 4，可以选择上传适用于SKAN 4或之前版本的文件。升级到SKAN 4后将无法选择适用于其他版本的文件。
4. 完成以下任一操作：
   * **点击拖放文件。**
   * **上传最新的映射架构文件。**
5. 按面板中显示的提示说明上传文件。
6. 打开**SKAN衡量**开关。
7. 点击**保存更改**。   
   请注意：在接下来的48-72小时内，面板板会显示不明确的过渡期数据。这是因为受到iOS计时器的限制，AppsFlyer无法确认用于解析的映射架构与您使用的编码架构是否一致。
8. 请确保您已将应用内事件映射到渠道侧的对应事件，以便相关渠道能正常利用回传数据。

</Accordion>

## CSV文件上传中的问题排查

<div id="upload-error-messages" />

<Accordion title="上传时报错">

文件中有一个或多个值不符合格式要求：文件格式要求自2021年6月7日起发生了一些变化，请确保您的文件格式与本文所提供的示例文件格式一致。

</Accordion>

<div id="using-excel-to-format-the-event_revenue_usd-column" />

<Accordion title="使用Excel调整event_revenue_usd一列的格式">

如果您使用Excel/Google Sheets创建CSV文件，请务必先确认event\_revenue\_usd一列的格式正确无误，然后再将文件保存为CSV格式。

保存CSV文件之后，请再次检查其格式是否正确无误。**请注意**：请勿使用Excel来检查文件格式，而须在[编辑器](/docs/skan-cv-decode-map-your-cv-to-events#visual-inspection-of-the-csv-file-without-excel)中检查。

#### 在Excel调整event\_revenue\_usd单元格的格式

如下图所示，Excel对数值单元格进行格式化时，通常使用逗号作为千位分隔符。此格式不适用于CSV文件上传。 此外，您还需要删除$符号。

![mceclip0.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

您可以在Excel中对这些单元格进行格式化，便可更正此问题。

**请按以下方式对金额进行格式化，确保其中没有千位分隔符（逗号）或$符号：**

1. 选中需要调整格式的单元格。
2. 右击**Format cells**（调整单元格格式）。  
   界面会打开单元格格式调整窗口。
3. 选择**Number**。  

   <Image alt="Formatnumbers.png" src="https://files.readme.io/4c1b61d1eae9149e818d4cc9793128fbdaafed5daed9acf6cbc503571475cc0e-34255643022481.png" width="381px" />

1. 取消**Use 1000 separator (,)**（使用逗号为千位分隔符）的勾选。
2. 【可选】设置数值的**小数点后位数**，默认值为2，最多可精确到小数点后5位。
3. 点击**OK**。  
   单元格格式化完毕。

</Accordion>

<div id="visual-inspection-of-the-csv-file-without-excel" />

<Accordion title="请勿使用Excel来检查CSV文件">

如需检查CSV文件的内容，请务必在编辑器中查看该文件。

* Windows：Notepad、Notepad++
* MacOS：TextEdit

下图为<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?output=csv">CSV示例文件</Anchor>在编辑器中的截屏。

**编辑器视图**

![SKCustomeEditor.png](https://files.readme.io/d8677e9967a70db32e8d04c4ee835bd477b18c1cb464a9cd0e593f72ce3f3c15-34255690323217.png)

在编辑器中检查CSV文件时请特别注意以下几点：

* **空格：** 请确保字段分隔符（即逗号）的前后没有空格。您可以在Excel中使用@trim命令来删除空格。
* **event\_revenue\_usd：** 确保event\_revenue\_usd一列中没有逗号或$符号。  

  ![mceclip1.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

</Accordion>

<div id="csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

<Accordion title="Excel生成CSV文件时不使用逗号作为分隔符">

如果Excel生成CSV文件时使用分号“;”等非逗号的字符作为分隔符：

* 这可能是因为您电脑的区域设置为非英语语言/地区。
* 当区域设置为德语时，此问题尤其普遍。
* 在不同的计算机操作系统（macOS或Windows）中解决此问题的方法不同。
* 如需解决此问题，请在<Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor>或其他论坛中搜索相关指南。您可以在搜索中使用以下关键词：*Operating system (macOS or Windows) Excel change delimiter for CSV files（在macOS或Windows中通过Excel更改CSV文件分隔符）。*

</Accordion>

<div data-zendesk-anchors="decode-skan-conversion-value=%E8%A7%A3%E6%9E%90skan%E8%BD%AC%E6%8D%A2%E5%80%BC h_01HAMKKCKJEGCDPN5P8J6X0E8E=%E8%A7%A3%E6%9E%90skan%E8%BD%AC%E6%8D%A2%E5%80%BC custom-conversion-value%E2%80%94decode=%E8%87%AA%E5%AE%9A%E4%B9%89cv%E5%80%BC%E8%A7%A3%E6%9E%90decode h_01HAMKKCKJ5K6J6NNPF394ZK61=%E8%87%AA%E5%AE%9A%E4%B9%89cv%E5%80%BC%E8%A7%A3%E6%9E%90decode h_01HAMKKCKJT7MA03SHT4X3MH4W=decode-mapping-scenario-rules facebookspecific-rules=%E9%92%88%E5%AF%B9meta-ads%E5%AF%B9%E6%8E%A5%E7%9A%84%E8%A6%81%E6%B1%82 h_01HAMKKCKJDCEKCNZFSF0V6KH8=%E9%92%88%E5%AF%B9meta-ads%E5%AF%B9%E6%8E%A5%E7%9A%84%E8%A6%81%E6%B1%82 example-decode-mapping=%E7%A4%BA%E4%BE%8B%E8%A7%A3%E6%9E%90%E6%A8%A1%E5%BC%8F%E4%B8%8B%E7%9A%84%E6%98%A0%E5%B0%84%E9%85%8D%E7%BD%AE h_01HAMKKCKJ5B7W8FGK01QCKN7Y=%E7%A4%BA%E4%BE%8B%E8%A7%A3%E6%9E%90%E6%A8%A1%E5%BC%8F%E4%B8%8B%E7%9A%84%E6%98%A0%E5%B0%84%E9%85%8D%E7%BD%AE example-b-conversion-value-1=%E7%A4%BA%E4%BE%8Ba%E7%B2%BE%E7%BB%86%E8%BD%AC%E5%8C%96%E5%80%BC%E4%B8%BA1 h_01HAMKKCKJ1ZRH00A7Q4HZ4BBK=%E7%A4%BA%E4%BE%8Ba%E7%B2%BE%E7%BB%86%E8%BD%AC%E5%8C%96%E5%80%BC%E4%B8%BA1 example-b-conversion-value-2=%E7%A4%BA%E4%BE%8Bb%E7%B2%BE%E7%BB%86%E8%BD%AC%E5%8C%96%E5%80%BC%E4%B8%BA2 h_01HAMKKCKJZBASWWM1VD0VXWBX=%E7%A4%BA%E4%BE%8Bb%E7%B2%BE%E7%BB%86%E8%BD%AC%E5%8C%96%E5%80%BC%E4%B8%BA2 example-c-conversion-value-21=%E7%A4%BA%E4%BE%8Bc%E7%B2%BE%E7%BB%86%E8%BD%AC%E5%8C%96%E5%80%BC%E4%B8%BA21 h_01HAMKKCKJ4YHMQENKNVPMV4KC=%E7%A4%BA%E4%BE%8Bc%E7%B2%BE%E7%BB%86%E8%BD%AC%E5%8C%96%E5%80%BC%E4%B8%BA21 example-d-conversion-value-62=%E7%A4%BA%E4%BE%8Bd%E7%B2%BE%E7%BB%86%E8%BD%AC%E5%8C%96%E5%80%BC%E4%B8%BA62 h_01HAMKKCKJP7V7D26MGM1WVDTE=%E7%A4%BA%E4%BE%8Bd%E7%B2%BE%E7%BB%86%E8%BD%AC%E5%8C%96%E5%80%BC%E4%B8%BA62 h_01HAMKKCKKJFRTXYJNWZNGF97V=decode-csv-file-specification decode-csv-file-specification::d6a1f3f1=%E8%A7%A3%E6%9E%90%E6%A8%A1%E5%BC%8F%E4%B8%AD%E7%9A%84csv%E6%96%87%E4%BB%B6%E5%86%85%E5%AE%B9%E5%8F%8A%E6%A0%BC%E5%BC%8F%E8%A6%81%E6%B1%82 h_01HAMKKCKK7G7VP6SDEHBH6383=%E8%A7%A3%E6%9E%90%E6%A8%A1%E5%BC%8F%E4%B8%AD%E7%9A%84csv%E6%96%87%E4%BB%B6%E5%86%85%E5%AE%B9%E5%8F%8A%E6%A0%BC%E5%BC%8F%E8%A6%81%E6%B1%82 h_01HAMKKCKKN7WDP6F5E4W91HQJ=upload-conversion-value-schema-file troubleshooting-the-csv-upload-errors-file=csv%E6%96%87%E4%BB%B6%E4%B8%8A%E4%BC%A0%E4%B8%AD%E7%9A%84%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 h_01HAMKKCKK0QQ8AS8FZ83MZ8FH=csv%E6%96%87%E4%BB%B6%E4%B8%8A%E4%BC%A0%E4%B8%AD%E7%9A%84%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5 h_01HAMKKCKK3B2T9VSTYCVE0017=upload-error-messages h_01HAMKKCKKFJAE4B88QV00HYPW=using-excel-to-format-the-event_revenue_usd-column formatting-event_revenue_usd-cells-in-excel=%E5%9C%A8excel%E8%B0%83%E6%95%B4event_revenue_usd%E5%8D%95%E5%85%83%E6%A0%BC%E7%9A%84%E6%A0%BC%E5%BC%8F h_01HAMKKCKKKVYCWCQCAEMSBMF7=%E5%9C%A8excel%E8%B0%83%E6%95%B4event_revenue_usd%E5%8D%95%E5%85%83%E6%A0%BC%E7%9A%84%E6%A0%BC%E5%BC%8F h_01HAMKKCKK39C9SP7K86ER3HZK=visual-inspection-of-the-csv-file-without-excel h_01HAMKKCKK9GEBC64JE4DSDAMQ=csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

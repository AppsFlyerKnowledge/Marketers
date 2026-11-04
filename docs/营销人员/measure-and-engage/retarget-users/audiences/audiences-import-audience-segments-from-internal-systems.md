---
title: 受众共享——导入人群包
metadata:
  keywords:
    - Developers
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-09-15T10:45:43Z'
  edited_at: '2026-10-14T10:12:13Z'
  id: 360013291857
  locale: zh-cn
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/zh-cn/articles/360013291857
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 您可以将贵司内部系统（如BI和CRM）中的预定义人群分组导入到AppsFlyer的受众共享面板（Audiences），以便使用受众共享功能将这些人群对接到您合作的广告平台并对其进行维护。

<div id="why-import-audiences" />

## 导入人群包的意义

在某些情况下，您的内部系统中可能存在预定义的人群分组。将这些人群包（以设备和/或用户标识符列表的形式呈现）导入AppsFlyer之后，您就可以把受众共享面板作为一个人群管理枢纽，将所有人群包都对接到您合作的广告平台并对其进行维护。此外，您还可以利用受众共享所提供的标识符匹配、数据扩充和相关投放指标等其他功能，充分汲取关键信息。

请参考以下使用场景：

<div id="examples" />

> 📄 **示例**
>
> 假设您想要在用户生日当月向其定向发放优惠福利。
>
> 这时您可以通过受众共享完成以下操作：
>
> 1. 使用您的内部CRM生成一个包含用户及其生日的列表。
> 2. 根据生日月份将其拆分成多个列表，并分别导出对应的设备ID列表。
> 3. 将这些列表作为人群包导入AppsFlyer，并将其关联到投放相关广告的合作平台。
> 4. 在这些平台上设置广告，使其定向投放到对应的人群包。
>
> **定向拓展获客范围**您的应用开发工作室并购了另一家工作室。这家被并购了的工作室具有之前安装了其应用的用户设备ID，您想要向这些用户定向投放广告，让其安装贵工作室的现有应用。
>
> 这时您可以通过受众共享完成以下操作：
>
> 1. 从贵司并购的工作室获取设备ID列表，然后将其作为一个人群包导入AppsFlyer。
> 2. 将该人群包关联到您投放相关广告的合作平台。
> 3. 在这些平台上设置广告，使其定向投放到对应的用户。

<div id="audiences-import-v20" />

## 受众共享的人群包导入功能V2.0

本文解释了人群包导入功能V2.0的作用原理和操作流程（涵盖CSV和API两种导入方式）。

<div id="imported-audience-types" />

## 可用的人群包类型

导入人群包时，您可以指定其类型。共有两种人群包类型可供选择，AppsFlyer会根据您选定的类型来处理并向渠道上传相应的人群包。**人群包类型的设定需在首次导入人群包时完成，且后续无法更改。**

**若以标准方式导入人群包：**

* AppsFlyer会对其进行标识符匹配和数据扩充——即AF受众共享将AF数据库中的现有标识符与您导入的标识符进行匹配（同一应用中的同一用户），用以扩充上传到渠道的受众数据。
* 依据相关账户的用户标识符共享规则，向合作渠道上传该人群包。
* 必须使用本文所述的V2.0导入功能完成人群包的导入。

**若“按原样”导入人群包：**

* AppsFlyer不会对其进行标识符匹配和数据扩充。
* 向渠道上传这类人群包时不考虑相关账户的用户标识符共享规则（即将您导入的所有标识符都上传到渠道）。
* 可以使用本文所述的V2.0导入功能完成人群包的导入。

<div id="important" />

> 🚧 **重要提示！**
>
> * 截至2021年11月23日的所有现存人群包都会以“按原样”的方式处理，且无法将其更改为标准人群包。您仍然可以通过本文所述的V2.0导入功能对这些人群包进行必要的更新。
> * 您最多可以同时有500个活跃的导入人群包。
> * 仅账户管理员可以将新的导入人群包设定为“按原样”。
> * 将CUID作为标识符导入人群包时，须确保AppsFlyer接收到的相关激活（而不仅仅是激活后事件）中包含其关联的CUID数据，从而完成CUID与相关设备的完整关联，同时添加其它设备标识符（即GAID、IDFA），实现数据扩充。<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid#设置cuid">详情请见此处说明。</Anchor>

<div id="audience-import-procedures" />

## 人群包导入流程

您可以通过上传CSV文件或使用Import Audience API来导入人群包。

<div id="import-a-csv-file" />

<Accordion title="通过CSV文件导入">

按以下要求制作一个CSV文件：

**格式**

* 分列显示每一种需要上传的用户标识符
* 表头行中显示各列标识符的名称（全部小写）
* 无空白行
* 行数上限：1千万
* 如果您使用Excel制作该文件，请将其另存为**CSV (Comma delimited) (\*.csv)** 文件，如下图所示：

  <Image alt="CSV.jpg" src="https://support.appsflyer.com/hc/article_attachments/18502652300561" width="339px" />

<div id="note" />

<div id="identifier-hash" />

#### 标识符哈希

**列和标识符**

* AF会通过表头行来识别并处理各列的数据，因此：
  * 对各列的前后顺序没有特定要求。
  * 如果您不计划上传某种标识符，则无需在CSV文件中列出该标识符。
  * 您可以在一个CSV文件中导入所有相关标识符，只需确保每行都包含必要的标识符值即可，详见以下说明。
* 可用标识符：
  * app\_id
  * idfv
  * idfa
  * gaid
  * oaid
  * imei
  * cuid
  * emails
  * phone
  * phone\_e164
  * braze\_id
  * amplitude\_id
* 必要标识符：  
  * 对于安卓受众：**app\_id**以及以下标识符中的任意一种：**gaid**、**oiad**、**imei**、**cuid**、**braze\_id**或**amplitude\_id**
  * 对于iOS受众：**app\_id**以及以下标识符中的任意一种：**idfv**、**cuid**、**braze\_id**或**amplitude\_id**
* <Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy#eu-digital-markets-act">数字市场法案（DMA）</Anchor>于2024年3月6日生效，Google为此推行了相应的合规政策。为了达到合规要求，“按原样”导入人群包时，需在其中添加两列AppsFlyer授权字段，具体如下：

| AppsFlyer授权字段 | Google字段 | 值 | 字段用途 |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true/false | 用于说明该用户是否允许Google将其数据用于个性化广告 |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true/false | 用于说明该用户是否同意将其数据发送到Google |

如果这些授权字段中没有值，则该人群包发送到Google时，相关用户会被视为授权状态不明确（Unspecified），因而不被纳入Google侧的人群包中。填充这些字段可确保您的Google人群包能充分覆盖来自<Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">欧洲经济区（EEA）</Anchor>的用户。

**CSV文件样例：**

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/4413851475729">new-import-android-example.csv</Anchor>  
<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/4413840980497">new-import-ios-example.csv</Anchor>

<span id="01ECF4ZD0RB90HZC6ZFNTKMDSG"></span>**使用CSV文件创建并导入人群包的方法如下：**

1. 在AppsFlyer面板的左侧菜单栏中点击**互动** > **受众共享**。
2. 点击**添加人群包**。
3. 选择**导入人群包** 。  
   界面会打开**导入人群包**窗口。
4. 输入**人群包名称**，不能与其他人群包的名称重复。
5. 选择相关用户所在的操作平台：**安卓**或**iOS**。
6. 说明该人群包是[**标准**人群包还是**按原样**导入的人群包](/docs/audiences-import-audience-segments-from-internal-systems#可用的人群包类型)。
7. 如果是标准人群包，则勿勾选相应方框。
8. 如果是按原样导入的人群包，请勾选相应方框。（**请注意：** 该选项仅对账户管理员可见。）
9. 点击<strong>保存人群包，并进入下一步。</strong>界面会显示**导入**选项卡。
10. 在**通过CSV文件导入**部分，保留默认的**添加新设备/用户**选项。
11. 选择要上传的CSV文件。  
    等待上传成功（Uploaded successfully）的确认消息 。
12. 点击<strong>下一步。</strong>界面会显示**连接**选项卡。
13. <strong>【可选】</strong>如需将人群包关联到合作渠道，请按<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#connect-an-audience-to-media-partners">相关说明</Anchor>进行操作。
14. 点击**完成**。

此时，您已完成该人群包的导入和渠道关联，并且可以在受众共享面板中看到该人群包。但请注意，新导入的人群包无法立即上传到渠道，这是因为AF对于导入人群包的处理频次为<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#eod">每天一次</Anchor>。

**通过CSV文件更新现有人群包的方法如下：**

1. 在AppsFlyer面板的左侧菜单栏中点击**互动** > **受众共享**。
2. 找到需要更新的人群包，点击该人群包的名称。  
   界面会打开**编辑人群包**窗口，其中包含**定义**选项卡。
3. 如需修改人群包名称，可在此处完成。如需更新人群包内容，请选择**导入**选项卡，上传新的CSV文件。
4. 在**通过CSV文件导入**部分选择上传列表的使用方式：
5. **添加新设备/用户：** 在现有人群包中添加设备/用户标识符
6. **从现有人群包列表中移除设备/用户：** 将上传列表中的设备/用户标识符从该人群包中移除
7. **以新的设备/用户覆盖现有人群包：** 将整个人群包中的所有设备/用户替换为上传列表中的设备/用户
8. 选择要上传的CSV文件。  
   等待上传成功（Uploaded successfully）的确认消息 。
9. 点击<strong>下一步。</strong>界面会显示**连接**选项卡。
10. 根据实际需求更改该人群包的<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#connect-an-audience-to-media-partners">渠道连接</Anchor>。
11. 点击**完成**。

此时，该人群包已通过您上传的CSV文件完成更新。但请注意，更新后的人群包无法立即上传到渠道，这是因为AF对于导入人群包的处理频次为<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#eod">每天一次</Anchor>。

<div id="error-messages" />

### 报错

| 响应消息 | 原因 | 应对措施 |
| --- | --- | --- |
| 设备列表有问题 | 设备列表存在一个或多个问题 | 请检查CSV文件：<ul><li>是否以正确的格式填充设备以及GAID/IDFA标识符</li><li>知否包含必要的标识符</li><li>是否包含表头行，表头格式是否正确</li><li>是否包含空白行</li><li>app\_id字段中是否填充了用于受众共享的正确应用</li></ul> |
| 您的设备列表为空。请在其中添加设备ID，然后重试 | CSV文件为空 | 请确保CSV文件中至少包含一个设备ID |
| 无法解析您上传的一个或多个设备ID | <ul><li>CSV格式不正确</li><li>您上传的文件不是CSV文件</li><li>您用于编辑并保存该CSV文件的工具不是有效的CSV编辑器（如Microsoft Excel）</li><li>一个或多个设备ID的格式错误</li></ul> | <ul><li>确保该CSV文件的格式符合要求</li><li>确保文件中所有设备ID的格式都正确无误</li><li>如果您使用的是Excel，请按上文所述方式将该文件另存为CSV文件。</li></ul> |
| 用户账户政策对受众共享生效后无法使用V1版本的导入功能 | 您使用V1.0的导入结构上传了[标准人群包](/docs/audiences-import-audience-segments-from-internal-systems#可用的人群包类型)。标准人群包必须按照V2.0结构上传。 | 请按上文所述的格式、字段列和标识符要求编辑您要上传的CSV文件。 |
| 发生暂时性的连接问题，无法上传您的文件。请重试。 | 可能出现了的网络错误 | 请尝试再次上传CSV文件。 |

</Accordion>

<div id="use-the-import-audience-api" />

<Accordion title="用于导入人群包的API">

您可以使用Import Audience API在人群包中添加或删除设备。

**使用该API导入新人群包的方法如下：**

1. 在AppsFlyer面板的左侧菜单栏中点击**互动** > **受众共享**。
2. 点击**添加人群包**。
3. 选择**导入人群包** 。  
   界面会打开**导入人群包**窗口。
4. 输入**人群包名称**，不能与其他人群包的名称重复。
5. 选择相关用户所在的操作平台：**安卓**或**iOS**。
6. 说明该人群包是[**标准**人群包还是**按原样**导入的人群包](/docs/audiences-import-audience-segments-from-internal-systems#可用的人群包类型)。
   * 如果是**标准人群包**，则勿勾选相应方框。
   * 如果是按原样导入的人群包，请勾选相应方框。（请注意：该选项仅对账户管理员可见。）针对2024年3月6日生效的数字市场法案（DMA），Google推行了相应的合规政策。为了达到合规要求，“按原样”导入人群包时，需在其中添加<Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy#导入人群包">两列AppsFlyer授权字段</Anchor>。填充这些字段可确保您的Google人群包能充分覆盖来自<Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">欧洲经济区（EEA）</Anchor>的用户。
7. 点击**保存**。  
   界面会显示“导入”页面。
8. 在**通过API导入**部分，保留默认的**添加新设备/用户**选项。
9. 复制<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/audience-import-post">导入新人群包API</Anchor>页面中的API请求URL（其中已包含API token）。
10. 然后复制并粘贴API请求体（request body）。
11. 点击**完成**。  
    界面会显示**连接**选项卡。
12. <strong>【可选】</strong>如需将人群包关联到合作渠道，请按<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#connect-an-audience-to-media-partners">相关说明</Anchor>进行操作。
13. 点击**完成**。
14. 创建一个包含用户/设备标识符的API请求，然后通过POST方式将其发送到AppsFlyer。

**通过API更新现有人群包的方法如下：**

1. 在AppsFlyer面板的左侧菜单栏中点击**互动** > **受众共享**。
2. 找到需要更新的人群包，点击该人群包的名称。  
   界面会打开**编辑人群包**窗口，其中包含**定义**选项卡。
3. 如需修改人群包名称，可在此处完成。如需修改人群包内容，请选择**导入**选项卡。
4. 在**通过API导入**部分选择上传列表的使用方式：
5. **添加新设备/用户：** 在现有人群包中添加设备/用户标识符。
6. **从现有人群包中移除设备/用户：** 将列表中的设备/用户标识符从现有人群包中删除。
7. 复制<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/audience-import-post">导入新人群包API</Anchor>页面中的**API请求URL**（其中已包含API token）。**请注意：** 更改此选项会使后续复制的代码中的端点路径发生变化。请确保您在当前以及后续的API请求中都针对所需操作使用正确的端点。
8. 复制**API请求体**（request body）。
9. 点击<strong>下一步。</strong>界面会显示**连接**选项卡。
10. 根据实际需求更改该人群包的<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#connect-an-audience-to-media-partners">渠道连接</Anchor>。
11. 点击**完成**。
12. 创建一个包含用户/设备标识符的API请求，然后通过POST方式将其发送到AppsFlyer。

**请注意：** 通过API导入人群包时，相关人群包会在24小时内更新。

<div id="response-codes" />

### 响应代码

| 代码 | 响应消息 | 说明 |
| --- | --- | --- |
| 200 | 请求成功 | 人群包导入成功 |
| 400 | 人群包平台无效，该人群包已针对安卓/iOS配置。如需使用其他平台，请在面板中创建新的人群包。 | 请求体（request body）中指定的平台于创建该人群包时指定的平台不匹配。 |
| 400 | 一行或多行数据中不包含应用ID。请务必在每一行中都添加一个应用ID。 | 每行数据中都必须包含一个**app\_id**<ul><li>**注意：** 使用旧版的V1.0导入结构[按原样](/docs/audiences-import-audience-segments-from-internal-systems#可用的人群包类型)导入人群包时，app\_id不是必须包含的数据。</li></ul> |
| 400 | 一行或多行数据中不包含有效的唯一标识符 | 所有或某些行中不包含格式有效的以下任一种标识符：<ul><li>对于安卓用户：**gaid**、**oiad**、**imei**、**cuid**、**braze\_id**或**amplitude\_id**</li><li>对于iOS用户：**idfv**、**cuid**、**braze\_id**或**amplitude\_id**</li></ul> |
| 400 | 每个请求最多可处理10,000个设备（此请求中共有n个设备） | 请求体（request body）列表中的设备ID数量超过10,000个 |
| 400 | 设备列表不能为空 | 请求体（request body）中的设备列表为空。<br /><br />每个请求中必须提供至少1个设备ID。 |
| 400 | 无法解析一个或多个设备ID | 全部或部分设备ID的格式无效 |
| 400 | 要删除的一个或多个设备各对应了多个标识符 | 发送的删除请求中出现一个设备对应多个标识符的现象 |
| 403 | 拒绝请求 | 该请求未经授权：导入密钥不正确或缺失 |
| 429 | 请求次数过多 | 请求频次上限为每分钟350次 |
| 500 | 无法解析请求 | 请求体（request body）格式无效（JSON结构不正确或不是JSON格式）<br /><br />请参考上文的请求示例 |

**API限制**

* 一次请求只能将设备添加到一个人群包
* 一次请求只能从一个人群包中删除设备
* 每次请求最多可以发送2万个设备ID
* 每分钟最多可以发送350个请求

</Accordion>

<div id="imported-audience-management-api" />

<Accordion title="用于管理导入人群包的API">

广告主可以通过<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-2">Imported Audience Management API</Anchor>创建并配置导入人群包、将导入的人群包连接到渠道、向渠道上传导入的人群包等等。

</Accordion>

<div data-zendesk-anchors="why-import-audiences=%E5%AF%BC%E5%85%A5%E4%BA%BA%E7%BE%A4%E5%8C%85%E7%9A%84%E6%84%8F%E4%B9%89 h_01HA4M61P4H5AVXQFA5ETABA67=%E5%AF%BC%E5%85%A5%E4%BA%BA%E7%BE%A4%E5%8C%85%E7%9A%84%E6%84%8F%E4%B9%89 01ECF4ZD0QQ5JJNH624D0E9WRF=%E7%A4%BA%E4%BE%8B audiences-import-v20=%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB%E7%9A%84%E4%BA%BA%E7%BE%A4%E5%8C%85%E5%AF%BC%E5%85%A5%E5%8A%9F%E8%83%BDv20 h_01HA4M61P41RSJMKSJ2V9WJH8W=%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB%E7%9A%84%E4%BA%BA%E7%BE%A4%E5%8C%85%E5%AF%BC%E5%85%A5%E5%8A%9F%E8%83%BDv20 imported-audience-types=%E5%8F%AF%E7%94%A8%E7%9A%84%E4%BA%BA%E7%BE%A4%E5%8C%85%E7%B1%BB%E5%9E%8B h_01HA4M61P4TEBNF264RNFC57YP=%E5%8F%AF%E7%94%A8%E7%9A%84%E4%BA%BA%E7%BE%A4%E5%8C%85%E7%B1%BB%E5%9E%8B h_01HA4M61P4NVDJ393HA4V75PQV=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA audience-import-procedures=%E4%BA%BA%E7%BE%A4%E5%8C%85%E5%AF%BC%E5%85%A5%E6%B5%81%E7%A8%8B h_01HA4M61P4EEYGJNZ3N2D0KXS5=%E4%BA%BA%E7%BE%A4%E5%8C%85%E5%AF%BC%E5%85%A5%E6%B5%81%E7%A8%8B 01ECF4ZD0RHJAQ31NKFCX8QEWW=import-a-csv-file identifier-hash=%E6%A0%87%E8%AF%86%E7%AC%A6%E5%93%88%E5%B8%8C h_01HA4M61P4BJZKN97ZTT8TKRBK=%E6%A0%87%E8%AF%86%E7%AC%A6%E5%93%88%E5%B8%8C confirmation-messages=%E6%8A%A5%E9%94%99 h_01HA4M61P57TMZRK4XX7ARK896=%E6%8A%A5%E9%94%99 h_01HA4M61P5XZR7C20Y5D3XX4K9=use-the-import-audience-api response-codes=%E5%93%8D%E5%BA%94%E4%BB%A3%E7%A0%81 h_01HA4M61P5YGX4QP2PDSVW7D3G=%E5%93%8D%E5%BA%94%E4%BB%A3%E7%A0%81 h_01HA4M61P6CE4RBCVTA3KE15VN=imported-audience-management-api" />

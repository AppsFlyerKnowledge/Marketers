---
title: 受众共享——用户特征
metadata:
  keywords:
    - Advertisers
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
  created_at: '2020-06-11T06:13:55Z'
  edited_at: '2026-10-14T10:10:32Z'
  id: 360009775517
  locale: zh-cn
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/zh-cn/articles/360009775517
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 您可以在受众共享面板中添加用户特征信息，从而提升人群分组的精准度。

[![UserAttributionNavigationXL3_us-en.png](https://files.readme.io/d308c590f656a155845af5c181322a3876d2e4dd7df458f4899861954dbd4de7-33375683032465.png)](https://files.readme.io/d308c590f656a155845af5c181322a3876d2e4dd7df458f4899861954dbd4de7-33375683032465.png)

<div id="about-user-attributes" />

## 用户特征简介

用户特征与事件数据不同，是指用户与您分享的常规特征信息，可涵盖性别、年龄、生日和国家等静态信息以及游戏得分等动态信息。

用户特征数据：

* 通过API以JSON格式上传或使用CSV文件上传
* 以哈希形式存储
* 可用于任何人群分组的规则组合

用户特征数据**不会与广告渠道共享**。

您可以选择在应用层级或账户层级添加用户特征，详见下文说明。若您在应用层级添加了用户特征，则您账户下的用户需要获取相关<Anchor target="_blank" href="/marketers/zh/docs/user-management#速览">应用的权限</Anchor>，然后才能管理并使用这些特征信息。

请参考下列场景，了解用户特征的具体使用方式。

<div id="scenario-app-marketer-requirements" />

<Accordion title="场景 - 应用营销">

假设您负责以下应用营销工作：

* game\_a和game\_b两个游戏的运营维护
* game\_c的上线发布
* 基于下列用户特征向现有用户定向投放广告：
  * 最喜欢的运动：板球
  * 当前游戏得分：在当前游玩的游戏中获得15分及以上

下表为您CRM中的用户特征数据。创建人群包规则组合时需要这些数据的访问权限。    
![UserAttributuesExample_us-en.png](https://files.readme.io/6f86d8659ef089ac82bb8401b4af650fbc590d2293ac93de30e6f9b4fc2ceb86-33375683035281.png)

**在规则组合中使用CRM数据**

在受众共享面板中创建用户特征（基于最喜欢的运动以及游戏得分），该操作会向规则组合开放CRM数据的访问权限。

<div id="scenario-user-attributes" />

#### 此场景中的用户特征

| 特点 | 格式 | 层级 |
| --- | --- | --- |
| <span id="game-score"></span>游戏得分 | **数字**——规则示例：*ScoreGameB大于29* | **应用层级**：记录每个游戏的用户得分。<br /><br />字段：ScoreGameA、ScoreGameB。 |
| <span id="favorite-sport"></span>最喜欢的运动 | **字符串——** 规则示例：*最喜欢的运动是网球*<br /><br />请注意：参数值区分大小写 | **账户层级**：用户“最喜欢的运动”在所有应用中都是相同的<br /><br />请注意：一个用户只能有一个关联到账户层级用户特征的值 |

**规则组合中的用户特征**

用户特征在受众共享面板的人群包规则组合中用作用户筛选条件。此示例场景中使用的是营销人员设置的标准（“最喜欢的运动”和“游戏得分”）。

[<Image alt="UserAttributedExample.jpg" src="https://files.readme.io/296ab5e13abedd5f11c7d445ec9bf4a9b62295c18ad783228d6ccb9b631be74f-33375704836625.jpg" width="276px" />](https://files.readme.io/296ab5e13abedd5f11c7d445ec9bf4a9b62295c18ad783228d6ccb9b631be74f-33375704836625.jpg)

</Accordion>

<div id="implement-user-attributes" />

## 用户特征配置

下文说明了用户特征的设置、添加和删除方式。

<div id="set-up" />

<Accordion title="设置方式">

**前期准备**：

如需管理应用层级的用户特征，账户下的用户必须获得相关应用的权限。

**请按以下流程设置用户特征：**

1. [添加用户特征](/docs/audiences-create-better-audiences-with-user-attribute-data#add)
2. [完成以下任一操作：](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)

   * [通过CSV文件导入用户特征数据](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)
   * [通过API导入用户特征数据](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)
3. <Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#user-attributes">在规则组合中使用用户特征</Anchor>

</Accordion>

<div id="add" />

<Accordion title="添加方式">

**请按以下方式添加用户特征：**

1. 从AppsFlyer后台的侧边栏中选择**互动** > **受众共享**。
2. 点击用户特征选项卡。
3. 点击**添加用户特征**。  

   ![UserAttributeAdd.png](https://files.readme.io/6c7f25bb23d47e67aaef34264029daa9ab058f08e218a441ab9dde8240b0b384-33375683046033.png)
4. 填写下列字段。各字段说明详见下表。   
   * **用户特征名称**
   * **格式**
   * **层级**
5. 点击**保存**。

| 字段 | 说明 |
| --- | --- |
| <span id="attribute-name"></span>用户特征名称 | <ul><li>仅可使用英文字符</li><li>不可使用标点符号或特殊字符</li><li>不可同时在应用层级和账户层级使用相同的名称</li><li>**可以**在不同的应用中使用相同的用户特征名称；如上文场景中使用的ScoreGameA和ScoreGameB</li></ul> |
| <span id="format"></span>格式 | <ul><li>文本：可用条件为用户特征值**是**或**不是**某个指定值。举例来说，“是板球”或“不是板球”。</li><li>数字——可用条件为用户特征值大于、小于或等于某个指定值。举例来说，得分大于15</li></ul> |
| <span id="level"></span>层级 | <ul><li>账户层级 用户特征与具体应用之间没有关联<br />比如：性别、最喜欢的运动</li><li>应用层级： 用户特征与具体应用相关。请在下拉菜单中选择与该用户特征相关的应用。</li></ul> |

</Accordion>

<div id="manage" />

<Accordion title="管理方式">

如需管理用户特征配置，请进入**受众共享** > **用户特征**选项卡。

[![AudiencesUserAttributes_us-en.png](https://files.readme.io/6baee58e9cd9b2b39bc8facf0af72abe71a4bd1cd2f844f49467fbaeb7252cd7-33375704844049.png)](https://files.readme.io/6baee58e9cd9b2b39bc8facf0af72abe71a4bd1cd2f844f49467fbaeb7252cd7-33375704844049.png)

| 功能 | 说明 |
| --- | --- |
| <span id="search-and-filter"></span>搜索和筛选 | 可用维度包括用户特征名称、应用名称和用户特征所在层级（应用层级/账户层级）。 |
| <span id="sort-by"></span>排序方式 | 点击列标题即可调整表格内各行的排序。 |
| <span id="zd-import-data"></span><span id="import-data"></span>导入数据 | <ul><li>[通过CSV文件导入数据](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)</li><li>[通过API导入数据](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)</li></ul> |
| <span id="change-api-import-key"></span>更改API导入密钥 | **API导入密钥的更改方式如下：**<ol><li>点击**导入数据**。</li><li>选择**API**。</li><li>点击**刷新导入密钥**。</li></ol>**请注意：** 密钥更新完毕后，请务必对嵌有密钥的脚本做相应的更新。 |

</Accordion>

<div id="delete" />

<Accordion title="删除">

![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)仅限账户管理员可以删除用户特征。

**从规则组合中删除特定用户特征的方法如下：**

1. 将相关用户特征从规则组合中移除。
2. 删除该用户特征。

</Accordion>

## 导入数据

<div id="import-field-specifications" />

<Accordion title="导入字段说明">

| 字段 | 内容 | 格式 | 通过CSV文件  <br />添加数据 | 通过CSV文件 删除数据 |
| --- | --- | --- | --- | --- |
| <span id="device_id"></span>device\_id | 需包含以下任一用户ID：<ul><li>IDFA</li><li>GAID</li></ul> | 文本 | 必须包含**device\_id**或**customer\_id**字段 | 必须包含**device\_id**或**customer\_id**字段<br /><br />如需移除现有数据，请勿发送值 |
| <span id="customer_id"></span>customer\_id | <Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">Customer user ID</Anchor> | 文本 | 必须包含**device\_id**或**customer\_id**字段 | 必须包含**device\_id**或**customer\_id**字段<br /><br />如需移除现有数据，请勿发送值 |
| <span id="app_id"></span>app\_id | **应用层级的用户特征：** 请使用AF面板中显示的应用ID<br /><br />对于iOS应用，需包含前缀*ID*<br /><br />**账户层级的用户特征**：总是使用星号（*）填充 | 文本 | 必须发送 | 必须发送 |
| <span id="attribute_key"></span>attribute\_key | 需与用户特征选项卡中显示的名称完全一致 | 文本 | 必须发送 | 必须发送 |
| <span id="attribute_value"></span>attribute\_value | 根据需要为字段赋值<br /><br />[*详情请见局限性说明。](/docs/audiences-create-better-audiences-with-user-attribute-data#limitations) | 文本或数字 | 必须发送 | 请勿发送 |

</Accordion>

<div id="import-data-by-csv" />

<Accordion title="通过CSV文件导入数据">

通过CSV文件添加或移除用户特征数据。以下CSV示例文件符合上文所述的示例场景。

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012423857">User-attribute-example.csv</Anchor>

![FileForAttributes.png](https://files.readme.io/2a9075ab7f900648aeebe3b5fca807c6b931ba5295f35708ee6c48d345f681b9-33375704847633.png)

**CSV文件要求**

* 无标题行
* 包含上表中列出的所有字段（列）。

**通过CSV文件导入用户特征数据的方式如下：**

1. 进入**受众共享** > **用户特征**选项卡。
2. 点击**导入数据**。
3. 选择**CSV**。
4. 选择以下任一选项：
   * **通过CSV文件**
   * **移除数据**
5. 选择要导入的CSV文件。
6. 点击**上传**，界面会弹出上传状态消息。

**请注意：** 导入用户特征时，AF会使用该用户特征来标记所有关联到同一个CUID的已知设备。举例来说，假设您导入了10个设备（以customer\_id区分），并使用“游戏得分”（Game score）标记其用户特征。其中，有一个customer\_id关联到了2个设备（即2个GAID带有同一个CUID），则此次数据导入会产生11条用户特征记录。

</Accordion>

<div id="import-data-by-api" />

<Accordion title="通过API导入数据">

使用此导入方式时需要准备一条请求路径（Request URL）以及带有用户特征数据的JSON。

1. 在面板中复制现成的API调用请求以及JSON模板。
2. 根据[字段要求说明](/docs/audiences-create-better-audiences-with-user-attribute-data#import-field-specifications)在JSON模板中填入您的数据。

**API请求路径和JSON模板的生成方式如下：**

1. 点击**导入数据**。
2. 选择**API**。
3. 选择所需操作：  
   * 更新用户特征：覆盖或添加。
   * 移除用户特征。
   * 移除用户数据：移除于某个特定用户相关的所有数据。AF通过AppsFlyer ID识别用户。
   * 移除应用数据：删除应用级别的所有数据。
4. 复制生成的API请求路径（Request URL）。
5. 复制生成的API请求体（Request Body）。
6. 按照上文所述的JSON格式准备带有相关用户特征数据的JSON。对于账户层级的用户特征，请将应用ID设置为"app\_ids": ["*"]
7. 以上述Request URL和Request Body为基础，编写API请求。
8. 以程序化方式发送该请求。

**API请求及JSON示例**  

```json
https://hq1.appsflyer.com/api/user-attributes-import-api/set-user-data
{
  "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
  "attributes_values": [
    {
      "device_id": "",
      "customer_id": "",
      "app_ids": [],
      "attributes": [
        {
          "attribute_key": "",
          "attribute_value": ""
        }
      ]
    }
  ]
}
```

<div id="note-1" />

> 📘 **注意**
>
> 必须使用带有<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens#广告主">API token V2.0</Anchor>的Authorization Bearer Header来验证该请求。

**包含多个设备ID、用户特征参数和参数值的请求示例**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "2222222",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 5
                }
                ,
                {
                    "attribute_key": "favorite_sport",
                    "attribute_value": "cricket"
                }
            ]
        }
        ,
        {
            "device_id": "555555-d1d1-d1d1-555-fffffffff",
            "customer_id": "111111",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "order",
                    "attribute_value": 7
                }
                ,
                {
                    "attribute_key": "number",
                    "attribute_value": 8
                }
            ]
        }]
}
```

**包含单个设备ID和多个用户特征参数及参数值的请求示例**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "12345678",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 90
                }
                ,
                {
                    "attribute_key": "favorite-sport",
                    "attribute_value": "cricket"
                }
                ,
                {
                    "attribute_key": "orderNumber",
                    "attribute_value": 93
                }
                ,
                {
                    "attribute_key": "netPromoterScore",
                    "attribute_value": 94
                }
            ]
        }
    ]
}
```

**请注意：** 导入用户特征时，AF会使用该用户特征来标记所有关联到同一个CUID的已知设备。举例来说，假设您导入了10个设备（以customer\_id区分），并使用“游戏得分”（Game score）标记其用户特征。其中，有一个customer\_id关联到了2个设备（即2个GAID带有同一个CUID），则此次数据导入会产生11条用户特征记录。详情请见局限性说明部分。

</Accordion>

<div id="limitations" />

<Accordion title="局限性">

<div id="general-limitations" />

#### 一般局限性

* CSV/API数据导入方式仅支持整数，不支持小数型数值。**举例来说，**“score”（得分）参数的值可以是90，但不能是90.5。
* 用户特征数据无法打印或下载。
* #### <span id="attribute-value-limitations"></span>用户特征的参数值限制：

  * 参数值内不能包含逗号、点或其他特殊字符。
  * 字符串形式的参数值不能超过40个字符。
  * 参数值不能以0开头。

<div id="api-import-limitations" />

#### API导入限制

* 每分钟最多可请求350次，每次请求的有效信息（payload）展平后的数据量为10K个设备（若导入1个用户特征，可包含10K个设备；若导入2个用户特征，可包含5K个设备，以此类推）。
* 每个导入请求都必须同时包含`device_id`和`customer_id`这两个参数。如果您需要导入的用户特征数据仅包含其中一种标识符，相关调用请求中仍须包含另一种标识符的“header”，并以空字符串填充。比如，假设您需要按`device_id`导入用户特征数据，但其中不含`customer_id`信息，则调用请求如下：

```json
"attributes_values": [
{
"device_id": "39e123.......",
"customer_id": "",
```

<div id="csv-import-limitations" />

#### 详情请见局限性说明部分。

* 添加用户特征值时，每个CSV文件中最多可包含1千万行数据。

</Accordion>

<div data-zendesk-anchors="user-attributes=%E7%94%A8%E6%88%B7%E7%89%B9%E5%BE%81%E7%AE%80%E4%BB%8B h_01HDNZH1XVX5BYQBPG848M8QZM=%E7%94%A8%E6%88%B7%E7%89%B9%E5%BE%81%E7%AE%80%E4%BB%8B scenario%E2%80%94app-marketer-requirements=scenario-app-marketer-requirements h_01HDNZH1XV8AWVVGNYVA9G4PAG=scenario-app-marketer-requirements scenario-user-attributes=%E6%AD%A4%E5%9C%BA%E6%99%AF%E4%B8%AD%E7%9A%84%E7%94%A8%E6%88%B7%E7%89%B9%E5%BE%81 h_01HDNZH1XW32ZJJRSANBQCTBV0=%E6%AD%A4%E5%9C%BA%E6%99%AF%E4%B8%AD%E7%9A%84%E7%94%A8%E6%88%B7%E7%89%B9%E5%BE%81 implement-user-attributes=%E7%94%A8%E6%88%B7%E7%89%B9%E5%BE%81%E9%85%8D%E7%BD%AE h_01HDNZH1XWPBVDHJ7AGPT5ZM9W=%E7%94%A8%E6%88%B7%E7%89%B9%E5%BE%81%E9%85%8D%E7%BD%AE h_01HDNZH1XWYA9TQZ1B342A661R=set-up h_01HDNZH1XW0PPJF78EVFQTW3R7=add h_01HDNZH1XWGZ04TQXD5D50771A=manage h_01HDNZH1XWP8P1ZVJX11AXCS2P=delete import-data::b50dc884=%E5%AF%BC%E5%85%A5%E6%95%B0%E6%8D%AE h_01HDNZH1XWCXV89YJV7EBJXNK5=%E5%AF%BC%E5%85%A5%E6%95%B0%E6%8D%AE h_01HDNZH1XW87W1PV4C3PMY9QD6=import-field-specifications h_01HDNZH1XW3XC893Q8BQZQW2AG=import-data-by-csv h_01HDNZH1XX7PMGNTD683DD2B49=import-data-by-api h_01HDNZH1XXF6DSNKG19ZRZ01AZ=%E6%B3%A8%E6%84%8F h_01HDNZH1XX61DVGK96C2TDSYW9=limitations general-limitations=%E4%B8%80%E8%88%AC%E5%B1%80%E9%99%90%E6%80%A7 h_01HDNZH1XXZZFA3WHZEE5N24AB=%E4%B8%80%E8%88%AC%E5%B1%80%E9%99%90%E6%80%A7 attribute-value-limitations=%E7%94%A8%E6%88%B7%E7%89%B9%E5%BE%81%E7%9A%84%E5%8F%82%E6%95%B0%E5%80%BC%E9%99%90%E5%88%B6 h_01GZTGPK2FTHTV4NQ2HKV1HK00=%E7%94%A8%E6%88%B7%E7%89%B9%E5%BE%81%E7%9A%84%E5%8F%82%E6%95%B0%E5%80%BC%E9%99%90%E5%88%B6 api-import-limitations=api%E5%AF%BC%E5%85%A5%E9%99%90%E5%88%B6 h_01HDNZH1XX4JWSMSF4672ENWNS=api%E5%AF%BC%E5%85%A5%E9%99%90%E5%88%B6 csv-import-limitations=%E8%AF%A6%E6%83%85%E8%AF%B7%E8%A7%81%E5%B1%80%E9%99%90%E6%80%A7%E8%AF%B4%E6%98%8E%E9%83%A8%E5%88%86 h_01J3APYQ8MXG1SGREVN638R75N=%E8%AF%A6%E6%83%85%E8%AF%B7%E8%A7%81%E5%B1%80%E9%99%90%E6%80%A7%E8%AF%B4%E6%98%8E%E9%83%A8%E5%88%86" />

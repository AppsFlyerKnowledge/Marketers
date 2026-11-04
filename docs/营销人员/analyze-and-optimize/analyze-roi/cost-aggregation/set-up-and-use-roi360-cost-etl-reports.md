---
title: Cost ETL——投放成本深度数据“桶”统解决
metadata:
  keywords:
    - Campaign
    - eCPI
    - clicks
    - Impressions
    - ROI
    - cost
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2020-05-17T15:36:41Z'
  edited_at: '2026-10-14T10:05:58Z'
  id: 360008849238
  locale: zh-cn
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/zh-cn/articles/360008849238
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** AppsFlyer ROI360解决方案中的Cost ETL可为广告主提供最详细的分渠道投放成本。

![5896_CostETL_graphic__2_.png](https://files.readme.io/3c9b8721fa4aba170c1ed7b7b365b4a5fe1cd74080469b3020d395352cede674-11178721788817.png)


<span id="cost-etl-principles"></span>AppsFlyer ROI360解决方案中的Cost ETL可为广告主提供最详细的分渠道投放成本。

投放成本数据：

* 涵盖当天和前6天（即本文中所说的“最近7天”），以及第14天、29天、88天的数据。在数据入库时需要注意这一点。
  * 举例来说，假设当天日期为2024年10月14日，则文件覆盖以下几天的数据：10月14日（当天）、10月13日（1天前）、10月12日（2天前）、10月11日（3天前）、10月10日（4天前）、10月9日（5天前）、10月8日（6天前）、9月30日（14天前）、9月15日（29天前）以及7月18日（88天前）。
  * 数据回滚是为了对上报的成本数据进行更新和校准。
* 适用于匹配到归因（转化）、点击或展示的成本。  
  **请注意**：
  * 最近7天的数据是取自渠道的最新数据，而第14/29/88天的数据则是经过重新处理得到的。
  * 数据的回滚更新仅针对成本，不涵盖归因数据。

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRqyHRTiLq8KUtELHqdaF6yVTfNE22X5UmUqXX89oOK5ZpS6lksXD0401G8MFmsaEzg2Csvf-d3y08Z/pub?output=xlsx">查看示例文件</Anchor>。

**请注意**：

* 建议选择最适合您业务需求的维度和指标，具体的最优解视渠道而定。


<div id="report-details" />

<div id="directory-and-filename-structure" />

<Accordion title="目录与文件名结构">

* *Cost ETL在某个目录中写入数据后，会创建一个名为success的文件，以标记数据写入成功，该文件总是带有该目录下最新的时间戳。*
* 文件夹/文件数量的规则如下：
  * 总结报告：
    * 每个批次的文件夹内包含最近7天数据的parquet文件。
  * * 每个批次的文件夹内包含的parquet文件以数字命名（从1开始）。
  * 【封闭Beta】完全成本报告：


`///t=/dt=/v=<1/2/3/4>/`

| **组成部分** | **内容** |
| --- | --- |
|  |  |
|  |  |
| 连接名称。 |  |
| t | 您可以使用以下任一方式：<ul><li>cost\_etl\_summary</li><li>cost\_etl\_geo</li><li>cost\_etl\_channel</li></ul> |
| dt | <ul><li>YYYY-MM-DD</li></ul> |
| v |  |
| Parquet文件编号 | <ul><li>从00000开始编号</li><li>示例：`part-`</li></ul> |


`/cost_etl/version/dt=/b=//`

| **组成部分** | **内容** |
| --- | --- |
| advertiser\_bucket\_name | 在Cost ETL配置中设定的存储桶名称：af-xpend-cost-etl-&lt;af-account-id>-[您的存储桶名称后缀] |
| cost\_etl | 总是为“cost\_etl”不变 |
| version | Cost ETL的版本 |
| date | 成本数据的日期<br /><br />格式：yyyy-mm-dd |
| 批次 | 以数字1-4命名 |
| dimension | 数据维度：<ul><li>geo</li><li>channel</li></ul> |
| file\_name | <ul><li>summary</li><li>all-cost</li></ul> |
| Parquet文件编号 | <ul><li>从00000开始编号</li><li>示例：`part-`</li></ul> |

**比如对于2020年6月23日中首次拉取的数据，其目录及文件名结构如下：**

</Accordion>

<div id="file-fields" />

<Accordion title="文件字段">

<div id="fieldsdimensions" />

#### 字段/维度

| **字段** | **说明** | **是否默认填充** | **格式** | **是否包含在总结文件中** |
| --- | --- | --- | --- | --- |
| date | 由渠道上报的成本发生日期 | 是 | 格式为yyyy-mm-dd的字符串 | ✓ |
| app\_id | AppsFlyer后台的应用ID | 是 | 字符串 | ✓ |
| media\_source | 展示广告的媒体渠道 | 是 | 字符串 | ✓ |
| OS | 指设备操作系统。可用值包括：<ul><li>Android</li><li>Windows Phone</li><li>iOS</li></ul> | 是 | 字符串 | - |
| agency | 投放广告的代理商 | 否 | 字符串 | - |
| campaign | 广告层次结构中的一个层级 | 否 | 字符串 | - |
| campaign\_id | 广告层次结构中的一个层级 | 否 | 字符串 | - |
| adset | 广告层次结构中的一个层级 | 否 | 字符串 | - |
| adset\_id | 广告层次结构中的一个层级 | 否 | 字符串 | - |
| ad | 广告层次结构中的一个层级 | 否 | 字符串 | - |
| ad\_id | 广告层次结构中的一个层级 | 否 | 字符串 | - |
| ad\_account | <ul><li>提供成本数据的广告账户</li><li>适用于通过oAuth（使用证书登录）实现连接的广告平台，如Google或Meta ads</li></ul> | 否 | 字符串 | - |
| currency | 广告消耗的货币单位，即您在AppsFlyer后台的应用配置中设定的货币单位。 | 是 | ISO-4217中的3字母字符串 | ✓ |
| original\_currency | 由广告平台上报的成本货币（未换算） | 是 | ISO-4217中的3字母字符串 | - |
| timezone | <ul><li>AppsFlyer储存数据时用到的时区</li><li>广告平台用来上报数据的时区可能与AppsFlyer后台配置的时区不同。这是AppsFlyer与广告平台之间出现数据差异的原因之一。</li></ul> | 是 | 字符串 | - |
| geo | 广告层级中的维度 | 否 | ISO 3166中的2字母字符串 | ✓ |
| channel | 广告层级中的维度 | 否 | 字符串 | - |
| keyword\_term | 用户在线搜索时使用的字词。 | 是 | 字符串 | - |
| keyword\_id | ASA关键词ID | 是 | 字符串 | - |
| site\_id | Publisher ID（子渠道ID） | 否 | 字符串 | - |
| campaign\_objective | 该字段是广告系列属性的一部分，<Anchor target="_blank" href="/marketers/zh/docs/campaign-properties-in-cost-etl-reports">详情请见此处说明。</Anchor> | 否 | 字符串 | - |
| cost\_model | 该字段是广告系列属性的一部分，<Anchor target="_blank" href="/marketers/zh/docs/campaign-properties-in-cost-etl-reports">详情请见此处说明。</Anchor> | 否 | 字符串 | - |
| af\_cost\_model | 由AppsFlyer对成本模型进行映射和归一。该字段是广告系列属性的一部分，<Anchor target="_blank" href="/marketers/zh/docs/campaign-properties-in-cost-etl-reports">详情请见此处说明。</Anchor> | 否 | 字符串 | - |
| bid\_strategy | 该字段是广告系列属性的一部分，<Anchor target="_blank" href="/marketers/zh/docs/campaign-properties-in-cost-etl-reports">详情请见此处说明。</Anchor> | 否 | 字符串 | - |
| af\_bid\_strategy | 由AppsFlyer对竞价策略进行映射并归一。该字段是广告系列属性的一部分，<Anchor target="_blank" href="/marketers/zh/docs/campaign-properties-in-cost-etl-reports">详情请见此处说明。</Anchor> | 否 | 字符串 | - |
| bid\_amount | 该字段是广告系列属性的一部分，<Anchor target="_blank" href="/marketers/zh/docs/campaign-properties-in-cost-etl-reports">详情请见此处说明。</Anchor> | 否 | 整数 | - |
| original\_bid\_amount | 该字段是广告系列属性的一部分，<Anchor target="_blank" href="/marketers/zh/docs/campaign-properties-in-cost-etl-reports">详情请见此处说明。</Anchor> | 否 | 整数 | - |

<div id="metrics" />

#### 指标

<table><thead><tr><th><strong>字段</strong></th><th><strong>说明</strong></th><th><strong>是否默认填充</strong></th><th><strong>格式</strong></th><th><strong>是否包含在总结文件中</strong></th></tr></thead><tbody><tr><td>impressions</td><td><ul><li>由AppsFlyer统计。</li><li>同时包含UA和再营销数据。</li><li> </li></ul></td><td rowspan="13"><p>是</p><p>如果某个指标没有可用值，则以0填充。</p></td><td>整数</td><td><span>✓</span></td></tr><tr><td>clicks</td><td><ul><li>由AppsFlyer统计。</li><li>同时包含UA和再营销数据。</li><li> </li></ul></td><td>整数</td><td><span>✓</span></td></tr><tr><td>reported_impressions</td><td>由渠道统计</td><td>整数</td><td><span>✓</span></td></tr><tr><td>reported_clicks</td><td>由渠道统计</td><td>整数</td><td><span>✓</span></td></tr><tr><td>installs</td><td>点击率。</td><td>整数</td><td><span>✓</span></td></tr><tr><td>reported_conversions</td><td>由渠道统计</td><td>整数</td><td> </td></tr><tr><td>re_engagements</td><td>点击率。</td><td>整数</td><td><span>✓</span></td></tr><tr><td>re_attributions</td><td>点击率。</td><td>整数</td><td><span>✓</span></td></tr><tr><td>cost</td><td>广告消耗金额（包括相关的代理费用）</td><td>参数值</td><td><span>✓</span></td></tr><tr><td>original_cost</td><td>由广告平台上报的成本数据，以广告平台设定的货币为单位（未经换算），加上由AppsFlyer计算的相关代理费用（若有）</td><td>参数值 </td><td><span>-</span></td></tr><tr><td>impressions_discrepancy</td><td><ul><li>广告平台和AppsFlyer之间的数据统计差异。</li><li>如果出现以下情况，请忽略该指标：<ul><li>成本与归因结果不匹配。</li><li>广告平台不支持<a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank">上报展示成本</a>。 </li></ul></li></ul></td><td>整数</td><td><span>-</span></td></tr><tr><td>clicks_discrepancy</td><td><ul><li>广告平台和AppsFlyer之间的数据统计差异。</li><li>如果出现以下情况，请忽略该指标：<ul><li>成本与归因结果不匹配。</li><li>广告平台不支持<a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank">上报点击成本</a>。 </li></ul></li></ul></td><td>整数</td><td><span>-</span></td></tr><tr><td>installs_discrepancy</td><td><ul><li>广告平台和AppsFlyer之间的数据统计差异。</li><li>如果出现以下情况，请忽略该指标：<ul><li>成本与归因结果不匹配。</li><li>广告平台不支持<a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank">上报转化成本</a>。 </li></ul></li></ul></td><td>整数</td><td><span>-</span></td></tr><tr><td>fees</td><td><span>代理商在广告成本以外额外收取的费用。由AppsFlyer统计</span></td><td>是</td><td>整数</td><td><span>-</span></td></tr><tr><td>cost_without_fees</td><td>剔除代理费后的成本。点击率。</td><td>是</td><td>整数</td><td><span>-</span></td></tr><tr><td>original_cost_without_fees</td><td>广告平台上报的原始成本数据，不含代理费用</td><td>是</td><td>整数</td><td><span>-</span></td></tr><tr><td>ctr</td><td><ul><li>点击率点击率。</li><li>计算方式为：点击量/展示量</li></ul></td><td rowspan="12"><p>否</p></td><td>整数</td><td><span>-</span></td></tr><tr><td>cvr</td><td><ul><li>由AppsFlyer统计的点击率。</li><li>计算方式为：激活量/点击量</li></ul></td><td>整数 </td><td><span>-</span></td></tr><tr><td>ecpm</td><td><ul><li>点击率。</li><li>计算方式为：（成本/展示量）\* 1000  </li></ul></td><td>整数</td><td><span>- </span></td></tr><tr><td>cpi</td><td><ul><li>点击率。</li><li>计算方式为：成本/激活量</li></ul></td><td>整数</td><td><span>- </span></td></tr><tr><td>ccvr</td><td><ul><li>每次转化的平均成本</li><li><span>计算方式为：成本/（激活量+再归因+再互动）</span></li></ul></td><td>整数</td><td><span>- </span></td></tr><tr><td>cvvr</td><td><ul><li>由AppsFlyer统计的点击率。</li><li>计算方式为：视频完播量/展示量</li></ul></td><td>整数</td><td><span>-</span></td></tr><tr><td>reported_cvr</td><td><ul><li>广告平台上报的转化率</li><li>计算方式为：上报转化量/上报点击量</li></ul></td><td>整数</td><td><span>- </span></td></tr><tr><td>ecpc</td><td><ul><li>点击率。</li><li>计算方式为：成本/点击量</li></ul></td><td>整数</td><td><span>-</span></td></tr><tr><td>video_25p_views</td><td>由广告平台上报的由广告平台上报</td><td>整数</td><td><span>- </span></td></tr><tr><td>video_50p_views</td><td>由广告平台上报的由广告平台上报</td><td>整数</td><td><span>- </span></td></tr><tr><td>video_75p_views</td><td>由广告平台上报的由广告平台上报</td><td>整数</td><td><span>- </span></td></tr><tr><td>video_completions</td><td>由广告平台上报</td><td>整数</td><td><span>- </span></td></tr></tbody></table>

</Accordion>

<div id="change-from-cost-etl-to-data-locker-connection" />

<div id="change-data-locker-connection" />

<div id="edit-connection" />

<div id="procedures" />

## 配置流程

您需要具备管理员权限才能够完成以下配置操作。

**温馨提示以下信息** ：

* * <Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>存储桶
  * <Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>存储桶
  * 【Beta】<Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor> Blob
  * 【Beta】<Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor>存储桶
  * <Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor>数据仓库
  * <Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor>数据仓库

2. * [<Image alt="" src="https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png" width="700px" />](https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png)
   * [<Image alt="" src="https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png" width="700px" />](https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png)
     1. 为新连接命名。  
        [<Image alt="" src="https://files.readme.io/734060321cf14a4ebbce66fe2abc71ff299218f7c52cb64dc5b8e71c42d3632d-31233921530001.png" width="2100px" />](https://files.readme.io/734060321cf14a4ebbce66fe2abc71ff299218f7c52cb64dc5b8e71c42d3632d-31233921530001.png)
     2. **选择一个云服务数据宿端**。完成以下任一操作：
        * 选择**S3**。  
          [<Image alt="" src="https://files.readme.io/1a78090f00407d44a5b74f3cb3b94e3a28064bc9b991b1cecf506fa0b9053842-31233961351441.png" width="945px" />](https://files.readme.io/1a78090f00407d44a5b74f3cb3b94e3a28064bc9b991b1cecf506fa0b9053842-31233961351441.png)
          1. 输入您的Amazon S3存储桶名称，`af-`必须手动在其中添加前缀af-af-。
          2. 点击**测试连接**。
          3. 确保未收到“存储桶路径无效”的报错消息。
          4. 选择该连接是否需要**支持Adobe Experience Platform**。
          5. 点击**保存**。
        * 选择**GCS**。  
          [<Image alt="" src="https://files.readme.io/6da526f43131887270136e9fcfa9434ad88c2ce8cebdb896c07dac4a0652d683-31233921536913.png" width="944px" />](https://files.readme.io/6da526f43131887270136e9fcfa9434ad88c2ce8cebdb896c07dac4a0652d683-31233921536913.png)
          1. 输入您的**GCS存储桶名称**。
          2. 点击**测试连接**。
          3. 确保未收到“存储桶路径无效”的报错消息。
          4. 选择该连接是否需要**支持Adobe Experience Platform**。
          5. 点击**保存**。
        * 【Beta】选择**Azure**。  
          [<Image alt="" src="https://files.readme.io/cd718eeebc5965d24a2d38457d4fa22c5691d6a186464187bea12199fb96671b-31233921550481.png" width="943px" />](https://files.readme.io/cd718eeebc5965d24a2d38457d4fa22c5691d6a186464187bea12199fb96671b-31233921550481.png)
          1. 输入您的**连接名称**、**存储账户名称**以及**密钥**。
          2. 确保未收到“存储桶路径无效”的报错消息。
          3. 选择该连接是否需要**支持Adobe Experience Platform**。
          4. 点击**保存**。
        * 【Beta】选择**Yandex**。  
          [<Image alt="" src="https://files.readme.io/230e0d9c0b56b4c9f85da8c97f1ab91818c16ecfbabbf81ecb35f12d41716888-31233961360273.png" width="944px" />](https://files.readme.io/230e0d9c0b56b4c9f85da8c97f1ab91818c16ecfbabbf81ecb35f12d41716888-31233961360273.png)
          1. 输入您的**存储桶名称**、**访问密钥**（Access Key）和**私人密钥**（Secret key）。
          2. 确保未收到“存储桶路径无效”的报错消息。
          3. 选择该连接是否需要**支持Adobe Experience Platform**。
          4. 点击**保存**。
        * 选择**BigQuery**。  
          [<Image alt="" src="https://files.readme.io/6989fa8c869c08440da757b3ebb385754a4f23dbe4e2d38c50837448c08ab03b-31233921555857.png" width="945px" />](https://files.readme.io/6989fa8c869c08440da757b3ebb385754a4f23dbe4e2d38c50837448c08ab03b-31233921555857.png)
          1. 输入您的BigQuery项目ID和数据集名称。
          2. 点击**测试连接**。
          3. 确保未收到“存储桶路径无效”的报错消息。
          4. 点击**保存**。
        * 选择**Snowflake**。  
          [<Image alt="" src="https://files.readme.io/b0e5f5ece797f46006d6e29a6afd01bc120b035590bd2ee87a54daa8c36bb0ed-31233961363985.png" width="944px" />](https://files.readme.io/b0e5f5ece797f46006d6e29a6afd01bc120b035590bd2ee87a54daa8c36bb0ed-31233961363985.png)
          1. 输入您的Snowflake地区和账户ID。
          2. 点击**测试连接**。
          3. 确保未收到“存储桶路径无效”的报错消息。
          4. 点击**保存**。
3. 点击**Next**。  
   [<Image alt="" src="https://files.readme.io/4237ca8e7e70e0c04e924b61839d47d88e42075b4c257fcdf5e78870712d3582-31233921563153.png" width="746px" />](https://files.readme.io/4237ca8e7e70e0c04e924b61839d47d88e42075b4c257fcdf5e78870712d3582-31233921563153.png)
4. [<Image alt="" src="https://files.readme.io/427b18043c0ab53ea559d53094efb6f04ad7505659c08ba7345b3a647f78d64d-31233961369105.png" width="607px" />](https://files.readme.io/427b18043c0ab53ea559d53094efb6f04ad7505659c08ba7345b3a647f78d64d-31233961369105.png)

   2. [详情请见此处说明。](/docs/set-up-and-use-roi360-cost-etl-reports#report-schedule)
   3. 点击**Next**。
5. 1. [<Image alt="" src="https://files.readme.io/a5d453f40a7c5318f6a4c6cdfc5cf4d645c540c4b684362a796cda41d3c058c6-31233961373585.png" width="566px" />](https://files.readme.io/a5d453f40a7c5318f6a4c6cdfc5cf4d645c540c4b684362a796cda41d3c058c6-31233961373585.png)
   2. [<Image alt="" src="https://files.readme.io/3662c55c71f3390ac651c9269eac519f846b53ad675dab224b62fb09f81d4578-31233921571345.png" width="1921px" />](https://files.readme.io/3662c55c71f3390ac651c9269eac519f846b53ad675dab224b62fb09f81d4578-31233921571345.png)
      * 总耗时
      * **geo**
      * **流量入口**（Channel）：
      * **【封闭Beta】完全成本报告：按国家/地区维度分组，涵盖全平台的所有营销活动所产生的成本数据，包括未添加到AppsFlyer的应用/平台（这时应用ID会标记为“unknown”，即未知）。**
   3. **请注意**：   
      [<Image alt="" src="https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png" width="1921px" />](https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png)
   4. [<Image alt="" src="https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg" width="1863px" />](https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg)
6. 点击**启用**。


**请注意**：


2. * [<Image alt="" src="https://files.readme.io/95c76d3bfc4a4db4bb9b4e67e4460680e0039e91dd930903515771e52c00ac7a-31233961377937.png" width="695px" />](https://files.readme.io/95c76d3bfc4a4db4bb9b4e67e4460680e0039e91dd930903515771e52c00ac7a-31233961377937.png)
   * [<Image alt="" src="https://files.readme.io/67a1fb2ce45a49fc75d12eba4d1c3e67875b83883b0fc05307c080c6050be0f2-31233961380369.png" width="651px" />](https://files.readme.io/67a1fb2ce45a49fc75d12eba4d1c3e67875b83883b0fc05307c080c6050be0f2-31233961380369.png)


2. * [<Image alt="" src="https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png" width="700px" />](https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png)
   * [<Image alt="" src="https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png" width="700px" />](https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png)
3. 点击**Save changes**。


**前期准备** ：

2. [<Image alt="" src="https://files.readme.io/2608d88368579c9fd3aa7648905484a56a7f0d989a96582cee51303409ce427c-31233961382289.png" width="631px" />](https://files.readme.io/2608d88368579c9fd3aa7648905484a56a7f0d989a96582cee51303409ce427c-31233961382289.png)
3. * [<Image alt="" src="https://files.readme.io/da486f6399e92c49923527da3348f4535691768cebd7a776ec84f7a2a739c204-31233961385617.png" width="501px" />](https://files.readme.io/da486f6399e92c49923527da3348f4535691768cebd7a776ec84f7a2a739c204-31233961385617.png)
   * [<Image alt="" src="https://files.readme.io/0d48f83f30954f5f68efecf7e6c4cf2b39b295e0b893711bd2e2756406c42461-31233921587985.png" width="631px" />](https://files.readme.io/0d48f83f30954f5f68efecf7e6c4cf2b39b295e0b893711bd2e2756406c42461-31233921587985.png)
4. 点击**Save changes**。


AppsFlyer将数据写入您的存储桶时，AWS平台默认该数据的所有者是AppsFlyer。您可能需要将默认归属权改为存储桶所有者（即您自己），具体取决于您的数据入库流程。

**请按以下步骤更改存储桶中数据的归属权：**

1. 登录AWS Management Console，打开Amazon S3后台，地址为<Anchor target="_blank" href="https://console.aws.amazon.com/s3/">https://console.aws.amazon.com/s3/</Anchor>。
2. 在**Bucket**列表中，选择存储桶名称，以启用S3 Object Ownership（对象所有权）。
3. 进入**授权**选项卡。
4. 点击**Object Ownership**下的**Edit**。
5. 选择**Bucket owner preferred**。
6. 点击**Save**。


<div id="best-practices" />

## 最佳实践

<div id="report-schedule" />

<Accordion title="定时拉取报告">

您可以利用定时拉取报告的设置根据实际需求获得最新数据。

设定报告拉取时间时：

* 尽量选择离您BI系统处理数据的时间最近的选项。
* 如果您合作的某个广告平台在提供前一天的数据时晚于其他平台，可以在该平台的数据可用时额外设置一次报告拉取。

</Accordion>

<div id="override-data" />

<Accordion title="数据覆盖">

在拉取和分析数据时，建议您拉取某个日期和批次的数据，或用当前批次的数据覆盖之前收到的同一时段的数据，否则可能会出现重复数据。

例如，在2月20日写入的第1批数据中包含2月14-20日的数据，但在2月19日写入的各批数据中也包含2月14-20日的数据。这种情况下，建议用最近收到的（即2月20日）数据覆盖掉之前收到的（即2月19日）数据。

</Accordion>

<div id="geo-versus-channel" />

<Accordion title="国家/地区（Geo）与流量入口（Channel）">

不是所有的广告平台都会同时提供所有维度的数据，最常见的例子就是Meta ads的国家/地区（Geo）数据和流量入口（Channel）数据。因此，我们将这两个维度的数据分为两个数据集。Geo数据集必定包含Geo数据，而 Channel数据集则必定包含Channel数据。

一般情况下，对大多数媒体渠道来说，Geo和Channel数据集中的数据完全一致。因此，您可以根据您的业务需求选用最合适的数据集（Geo或Channel）。

如果某个渠道的对接协议中不包含流量入口（Channel）上报，则流量入口字段为空，AF仍将其视为包含流量入口的数据。

</Accordion>

<div id="aggregate-data" />

<Accordion title="汇总数据">

Cost ETL能从广告平台侧提取最深入的数据，从而为广告主提供更细的颗粒度和更灵活的报告配置。建议您考量实际业务需求，并以最合适的方式对数据进行汇总，否则数据量过于庞大，难以汲取真正有决策价值的洞察。举例来说，如果您想要了解广告系列和国家层级的成本数据，可以仅拉取这些维度的数据。

</Accordion>

<div id="standardization-across-networks" />

<Accordion title="广告平台数据的标准化">

各广告平台支持的数据颗粒度不尽相同。比如Meta ads不提供子渠道层级的成本数据，而X Ads不提供国家/地区层级的成本数据。在对Cost ETL数据进行汇总时，需注意这方面的差别，确保您在对比各渠道时使用的数据具有可比性。

</Accordion>

<div id="compare-data" />

<Accordion title="数据对比分析">

Cost ETL提供的信息涵盖您所有的成本数据。Cost ETL中有时会出现AF面板上没有的广告系列数据，比如空耗的广告系列（即未带来激活的广告系列）产生的成本数据。如需对比数据，请在数据总览面板中找出具体的广告系列ID，然后将其面板数据与Cost ETL中的成本数据进行对比。详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">成本数据可用性</Anchor>。

</Accordion>

<div id="combine-cost-etl-and-cohort-reports" />

<Accordion title="合并Cost ETL和群组报告">

您可以将Cost ETL报告和高级汇总群组报告（或Data Locker中的常规群组报告）相结合，导入BI系统。这两种报告合并后可以提供最全面、最准确、时效性最高的营销效果信息，其中包含点击、展示、成本、收入、应用内事件等各种数据。您还可以使用合并后的数据计算ROAS、CPA等等。<Anchor target="_blank" href="/marketers/zh/docs/combine-cost-etl-and-cohort-reports-via-data-locker">详情请见此处说明。</Anchor>

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 时区 | 如果时区有所变更，则变更当天的成本数据会重复。<Anchor target="_blank" href="/marketers/zh/docs/changing-app-time-zone-settings">详情请见此处说明。</Anchor> |
| 数据时效性 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">一天多次</Anchor>。Cost ETL的配置流程包含定时拉取报告的设置，您可以通过该设置来指定报告的送达时间。</li><li>相关数据会在指定时间前的一小时内写入存储桶。也就是说，如果您选择的报告送达时间为早晨6，则该报告会在早晨5-6之间写入存储桶。</li></ul>**请注意**：成本数据写入您的存储桶后，入库BI的数据量可大至数GB，小至数KB，具体取决于报告和parquet文件的大小。 |
|  |  |

</Accordion>

<div data-zendesk-anchors="h_01HA29GW8PVZJ8MP23K7QVR40J=cost-etl-principles 01JCZDREEY73373HQCFJK8D163=report-details h_01HA29GW8PWN30BCQCK29V0FTA=directory-and-filename-structure h_01HA29GW8P0B1JJTGYDW863D7Z=file-fields fieldsdimensions=%E5%AD%97%E6%AE%B5%E7%BB%B4%E5%BA%A6 h_01HA29GW8PQATB4K5VJP1HD4NW=%E5%AD%97%E6%AE%B5%E7%BB%B4%E5%BA%A6 metrics=%E6%8C%87%E6%A0%87 h_01HA29GW8PZTS7XDWGYWXFZPYG=%E6%8C%87%E6%A0%87 procedures=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B 01JCZDRERADNNX04RT752793PG=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B edit-connection=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B change-data-locker-connections=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B h_01JCZMGC8J41Y7H4JGZDVWYDJS=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B h_01JCZNQF3QE7P8PBQPKXZK1SA2=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B change-from-cost-etl-to-data-locker-connection=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B h_01JKWMF6V70W9FA90SSKJ77R2Z=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B best-practices=%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5 h_01HA29GW8QKPQXE4GHECAC5R5X=%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5 h_01J0NRD227RQR50CMNW60SF7SK=report-schedule h_01HA29GW8QHX8AMK4T7E85H7RS=override-data h_01HA29GW8QT5FNNYSWHCT99D68=geo-versus-channel h_01HA29GW8QA3FP46EMZVYDEZF3=aggregate-data h_01HA29GW8QPW0NXEMF1WGJMKSF=standardization-across-networks h_01HA29GW8Q3FNS0W7SKTG7S9R1=compare-data h_01J582E5JNR5DJ9T8HKDG2XSRR=combine-cost-etl-and-cohort-reports additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HA286GA6WPYVNN7KCXK7DGFM=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HA282W8WHHNDG75XZNSV2QQF=traits-and-limitations" />

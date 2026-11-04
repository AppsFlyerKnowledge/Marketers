---
title: 营销人员的Data Locker使用指南
metadata:
  keywords:
    - Reports
    - Data Locker
    - Advertisers
    - Raw Data
    - Developers
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2019-02-03T12:20:08Z'
  edited_at: '2026-10-14T10:04:55Z'
  id: 360000877538
  locale: zh-cn
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000877538
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** Data Locker可以将您的报告发送到云端，或入库到您的BI系统。我们支持多种云端存储方式，您可以选择AppsFlyer的AWS数据存储桶，也可以使用您在 AWS、GCS、Yandex、BigQuery和Snowflake上的自有存储桶。Data Locker还支持[多宿端数据传输](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination)，也就是说，您可以将所有数据传输到多个宿端、分宿端传输不同数据，或结合这两种方式传输数据，

## 速览

![6133DataLockerForAdvertisers.png](https://files.readme.io/820fee89515ccdcdfac2043bcb9fde722ddc8ec852a140ec250378c581d9c375-32966274469649.png)

您可以在Data Locker中选择您需要AppsFlyer传输到指定宿端的数据，可用的维度包括应用、媒体渠道、事件和报告。然后您就能通过程序化的方式将这些数据从云端入库到您的系统中。

<div id="data-locker-features" />

<Accordion title="Data Locker——功能简介">

| 功能 | 说明 |
| --- | --- |
| [存储方式](/docs/data-locker-for-marketers#storage-options) | Data Locker可以将您的数据发送到下列任一云平台：<ul><li>AppsFlyer的AWS数据存储桶</li><li>您在以下平台的<Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup">自有数据存储桶</Anchor>：<ul><li>AWS</li><li>GCS</li><li>Azure Blob</li><li>【Beta】Yandex</li><li>BigQuery</li><li>Snowflake</li></ul></li></ul>您可以在Data Locker中设置多个宿端。也就是说，您可以将部分或所有数据发送到[多个宿端](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination)。<br /><br />**示例**<ul><li>按报告类型隔离数据：将原始数据发送到GCS，将汇总数据发送到Snowflake。</li><li>按应用隔离数据：将各应用组的数据分别发送到不同的数据存储桶。</li></ul> |
| 多应用程序 | Data Locker可以发送您AF账户下的某个、某些或所有应用的数据。您在账户中添加应用时，Data Locker可自动涵盖这些新应用的数据。 |
| 可用窗口期 | 14天 |
| [数据隔离](/docs/data-locker-for-marketers#app-segregation) | 云端数据存储桶的数据隔离选项包括：<ul><li>【默认】**归并：** 即合并所有应用的数据。您可以使用每一行中的应用ID字段在数据文档中区分具体应用。</li><li>**按应用隔离数据：** Data Locker可以将每个应用的数据分别放在单独的文件夹里，文件夹名称中包含具体的应用ID。</li></ul> |
| 数据格式选项 | <ul><li>适用于云端数据存储桶：<ul><li>CSV</li><li>PARQUET</li><li><Anchor target="_blank" href="/marketers/zh/docs/adobe-experience-platform-aep-integration-with-appsflyer-data-locker">Adobe</Anchor></li></ul></li><li>数据仓库</li></ul> |
| 数据时效性 | 不同报告类型的数据时效性不同：<ul><li>**每小时：** 滚动生成数据；AppsFlyer接收到激活和应用事件数据后数小时内就会将其写入存储桶。</li><li>**每日：卸载等报告每天更新一次，您可在次日拉取前一天生成的报告。**</li><li>**文档编号： 如果在同一指定时段内多次生成同一种报告，Data Locker会对文档进行编号。**</li></ul> |

</Accordion>

<div id="reports-available-via-data-locker" />

<Accordion title="可通过Data Locker拉取的报告">

<Anchor target="_blank" href="/marketers/zh/docs/data-locker-advertiser-reports">可通过Data Locker拉取的报告</Anchor>

</Accordion>

<div id="set-data-locker-report-settings" />

## Data Locker报告设置

如需配置Data Locker，请按照以下步骤完成云服务对接、导出设置以及报告内容的自定义：

<div id="1-set-up-your-cloud-service" />

<Accordion title="1. 设置云服务">

您可以将Data Locker与一个或多个云服务提供商连接。请参考以下说明，了解如何将云服务与Data Locker对接：

* <Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>存储桶
* <Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>存储桶
* <Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor>斑点
* 【Beta】<Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor>存储桶
* <Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor>数据仓库
* <Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor>数据仓库

**请注意**：如果您的套餐中不含Data Locker，但含群组分析报告或SKAN数据，您也必须完成上述自有云端存储工具设置。

</Accordion>

<div id="2-add-a-connection-to-your-cloud-service" />

<Accordion title="2. 添加云服务连接">

在完成云服务账号与Data Locker的对接配置后（参见上文设置云服务），您需要在Data Locker中使用账号凭证创建一个连接。每个账号最多可以创建2个连接。

<div id="note" />

> 📘 **注意**
>
> 默认情况下，每个账号最多可以开启<strong>2个Data Locker连接。</strong>如需创建其他连接，请联系您的客户成功经理（CSM）。

创建云服务连接步骤如下：

1. 在AppsFlyer后台左侧的菜单栏中选择**导出** > **Data Locker**。
2. 在右侧点击**新建连接。**
3. 在**连接名称** 中输入您的连接名称。仅限小写字母、数字和连字符（-）。
4. 单击您需要连接的云服务图标。
5. 根据所选服务，输入对应的连接信息。

   <div id="aws-cloud-bucket-connection" />

   <Accordion title="AWS云存储桶连接">

   在设置AWS连接之前，请先创建一个AWS存储桶。如需了解创建方法，请参见<Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#aws-storage">此处</Anchor>。

   设置步骤如下：

   1. 输入您的Amazon S3存储桶名称，必须手动在其中添加前缀`af-`。
   2. 点击**测试连接**。
   3. 确保未收到“存储桶路径无效”的报错消息。
   4. 选择该连接是否需要**支持Adobe Experience Platform**。如选择启用，请点击**保存**并继续[设置全局过滤器](#select-global-level-filters)。
   5. 点击**Save**保存。

   </Accordion>

   <div id="gcs-cloud-bucket-connection" />

   <Accordion title="GCS云存储桶连接">

   在设置GCS连接之前，请先创建一个存储桶。如需了解创建方法，请参见<Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#gcs-storage">此处</Anchor>。

   设置步骤如下：

   1. 输入您的**GCS存储桶名称**。
   2. 点击**测试连接**。
   3. 确保未收到“存储桶路径无效”的报错消息。
   4. 选择该连接是否需要**支持Adobe Experience Platform**。 如选择启用，请点击**保存**并继续[设置全局过滤器](#select-global-level-filters)。
   5. 点击**Save**保存。

   </Accordion>

   <div id="azure-cloud-bucket-connection" />

   <Accordion title="Azure云存储桶连接">

   在设置Azure连接之前，请先创建一个Azure存储账号。如需了解创建方法，请参见<Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#beta--azure-storage">此处</Anchor>。

   设置步骤如下：

   1. 输入您的**连接名称**、**存储账户名称**以及**密钥**。
   2. 确保未收到“存储桶路径无效”的报错消息。
   3. 选择该连接是否需要**支持Adobe Experience Platform**。 如选择启用，请点击**保存**并继续[设置全局过滤器](#select-global-level-filters)。
   4. 点击**Save**保存。

   </Accordion>

   <div id="yandex-cloud-bucket-connection" />

   <Accordion title="Yandex云存储桶连接">

   在设置Yandex连接之前，请先创建Yandex服务账号。如需了解创建方法，请参见<Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#yandex">此处</Anchor>。

   设置步骤如下：

   1. 输入您的**存储桶名称**、**访问密钥**（Access Key）和**私人密钥**（Secret key）。
   2. 确保未收到“存储桶路径无效”的报错消息。
   3. 选择该连接是否需要**支持Adobe Experience Platform**。 如选择启用，请点击**保存**并继续[设置全局过滤器](#select-global-level-filters)。
   4. 点击**Save**保存。

   </Accordion>

   <div id="bigquery-data-warehouse-connection" />

   <Accordion title="BigQuery 数据仓库连接">

   在设置Yandex连接之前，请先创建Yandex数据集。如需了解创建方法，请参见<Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#bigquery">此处</Anchor>。

   设置步骤如下：

   1. 输入您的BigQuery项目ID和数据集名称。
   2. 点击**测试连接**。
   3. 确保未收到“存储桶路径无效”的报错消息。
   4. 点击**保存**并继续[设置全局过滤器](#select-global-level-filters)。

   </Accordion>

   <div id="snowflake-data-warehouse-connection" />

   <Accordion title="Snowflake数据仓库连接">

   在设置Snowflake连接之前，请先创建Snowflake账户。如需了解创建方法，请参见<Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#snowflake">此处</Anchor>。

   设置步骤如下：

   1. 输入您的Snowflake地区和账户ID。
   2. 点击**测试连接**。
   3. 确保未收到“存储桶路径无效”的报错消息。
   4. 点击**保存**并继续[设置全局过滤器](#select-global-level-filters)。

   </Accordion>

6. 点击<strong>保存。</strong>系统将显示**报告输出设置**部分。

<div id="note-1" />

> 📘 **注意**
>
> 您可以通过[审计日志](#track-connection-changes-in-the-audit-log)确认连接是否已创建、更新或删除，并查看操作的执行者。

</Accordion>

<div id="3-set-the-report-output-settings" />

<Accordion title="3. 设置报告输出参数">

在完成与云服务的连接后，接下来可对Data Locker报告输出的通用参数进行设置。**如果您使用的云服务是BigQuery或Snowflake，则可跳过此步骤**。

1. 在**报告输出设置**部分下，选择文件夹结构 ([数据分流方式](/docs/data-locker-for-marketers#app-segregation))：
   * **统一** (默认）：报告文件包含所有应用的数据记录。
   * **按应用取数：** 每份报告文件只包含一个应用的数据。
2. 选择报告文件格式：Parquet（默认）或CSV。
3. 选择报告的文件压缩类型：
   * Snappy（仅限Parquet文件）
   * GZIP
4. 选择单个文件中的最大行数：可选值为10k，25k，50，100k，200k，或500k。 行数越多，生成的文件数量越少，单个文件越大。

   <div id="note-2" />

   > 📘 **注意**
   >
   > 在**预期路径** 下，查看报告的路径模式。请注意：实际路径可能与显示不同。


</Accordion>

<div id="select-global-level-filters" />

<Accordion title="4. 选择全局筛选条件">

全局筛选条件可帮助您**按应用或媒体渠道筛选报告**。这些筛选条件适用于您数据存储账户中的大多数报告，您也对报告进行单独设置（请参见后文中的[7-选择报告层级筛选条件](#select-the-report-level-filters)）。如果在全局和报告层级同时设置筛选条件，则报告层级的筛选条件优先。

设置筛选条件的操作如下：

1. 在**报告**部分，点击所需的筛选条件并选择报告中需包含的项目。 例如，点击**应用**筛选条件<Image alt="无标题.png" src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" width="53px" />并选择报告中需包含的应用。
2. 点击回车（⏎）按钮。

</Accordion>

<div id="5-select-the-report" />

<Accordion title="5. 选择报告组">

选择您希望在云服务中获取的报告。报告以组的形式列出，点击组名可以展开或收起。

* 选择一份报告，点击<Image alt="向下.png" src="https://files.readme.io/3f59bcc54434374270c0099394a740cc650a3b4a1be0f3f34d298be1ebcad40c-34623601355409.png" width="20px" />展开报告组。展开报告组后，报告会显示以下信息：
  * **报告名称**：报告的名称。
  * **数据集名称：** 包含该报告数据的数据库名称。
  * **数据时效性：** 数据更新频率（例如：按小时、按天或按版本）。
  * **字段：** 已选择的字段数量/可供选择的字段总数。

</Accordion>

<div id="customize-or-duplicate" />

<Accordion title="6. 自定义或复制报告">

选定一个或多个报告后，您可以选择**自定义原始报告**或**复制并自定义报告副本**。该功能可帮助您在不影响原始版本的情况下，为不同的业务场景创建定制化报告。

**方案A：自定义原始报告**

1. 点击报告名称旁边的<Image alt="customize.png" src="https://files.readme.io/35f4653b944cd5dc81c6de76f8dcacd9c3413ea49915ba2b5865a244ede3c4b6-35437232722833.png" width="20px" /> **自定义**按钮。
2. 打开报告编辑器，选择需要的字段并应用筛选条件。
3. 修改将直接保存到原始报告配置中。

*请注意：该操作将改变报告传送到云存储的方式。*

**方案B：复制报告**

* 点击报告名称的<Image alt="Untitled 2.png" src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" width="5px" />。
* 在下拉菜单中选择<Image alt="duplicate2.png" src="https://files.readme.io/d8fbf09b3a8e3839f80a0a4fec90e0360dc1c2a4a066bf58438364c0d8a15c65-35439088509073.png" width="17px" /> **复制**。
* 系统会生成一个新副本，名称前缀为`copy_of_`。
* 复制后的报告将以编辑模式打开，方便您进行自定义设置。

*提示：复制功能适用于为不同场景创建多种版本的报告。*

完成自定义设置或复制报告后，您可进入下一步，配置报告字段。

</Accordion>

<div id="6-select-the-report-fields" />

<Accordion title="7. 选择报告字段">

完成自定义设置或复制报告后，您需要定义报告中应包含哪些字段。所有报告均包含完整的字段集合，您可以根据分析或对接需求进行筛选。默认情况下，所有字段均已选中。您也可以手动勾选需要的字段，或取消不需要的字段。

操作步骤：

1. 在所选报告的编辑窗口中，在**字段**将鼠标悬停在字段上，可查看字段说明。

   [![HQ1_2024-08-26_15.44.23.png](https://files.readme.io/293d227464e3907982e0c82187915ee1b16386a4111e83ebd8db065ade64a48b-34623601367697.png)](https://files.readme.io/293d227464e3907982e0c82187915ee1b16386a4111e83ebd8db065ade64a48b-34623601367697.png)
2. 勾选要包含的字段，取消勾选要排除的字段。
3. 点击**应用**保存设置。

**从其他报告复制字段配置**

您可以先从其他报告中复制字段为基础，然后继续勾选或取消勾选字段以微调报告。

1. 在**字段**选项卡中，先随意取消勾选一个字段。
2. 点击**Pull schema from report**。
3. 选择您希望复制字段配置的报告。
4. 根据需要继续勾选或取消字段。
5. 如需恢复报告的原始字段配置，点击<Image alt="无标题 4.png" src="https://files.readme.io/dda26e3d18c52049cf92d7862a87ce7a46e6a00c349afd70dfe6d1809e00b89e-34623601369361.png" width="15px" /> **刷新**。

</Accordion>

<div id="7-select-the-reportlevel-filters" />

<Accordion title="8. 选择报告级筛选条件">

您可以借助报告级筛选条件对某一份报告按**应用、媒体渠道**等维度进行筛选。您也可以设置全局筛选条件，应用于账号中的所有报告；参见[选择全局筛选条件](#select-global-level-filters)。默认情况下，报告级筛选条件是根据全局筛选条件设置的，您也可以仅针对该报告进行自定义设置。

为指定报告设置筛选条件的步骤如下：

1. 将鼠标悬停在要自定义的报告上。
2. 点击<Image alt="无标题 2.png" src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" width="6px" />打开操作菜单，然后选择<Image alt="无标题 3.png" src="https://files.readme.io/c27f864253e6749f883047b4529ad292153500db5aebd452568a6aa04407472e-34623601366033.png" width="20px" /> **编辑报告**。
3. 打开**筛选条件**选项卡。此时筛选条件默认为全局筛选条件。
4. 点击筛选条件并选择报告中需包含的项目。例如，点击**应用**筛选条件<Image alt="无标题.png" src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" width="53px" />并选择报告中需包含的应用。
5. 点击回车（⏎）按钮。您的选择将应用于全局设置。
6. （可选）对于**应用内**报告，您可以设置**应用内事件**筛选条件。请输入事件的准确名称。
7. 点击**应用**保存设置。

</Accordion>

<div id="8-remove-legacy-fields" />

<Accordion title="9. 移除历史字段">

历史字段指之前包含在报告结构中，但现在已不包含的字段。建议您移除这些字段，确保报告只包含相关信息。在移除前，请确认该操作不会对您的工作流或对接流程产生影响。

**移除历史字段的操作如下**

1. 打开**历史字段**选项卡。
2. 启用：**在报告中包含旧版字段（Include legacy fields in the report）**。
3. 取消勾选要排除的字段。
4. 点击**应用**。
5. 保存连接设置。

**移除所有历史字段：**

1. 打开历史字段选项卡。
2. 关闭：**在报告中包含旧版字段（Include legacy fields in the report）**。

<div id="note-3" />

> 📘 **注意**
>
> 如果您希望在报告中包含旧版字段，但字段列表呈灰色且被锁定，请联系您的客户成功经理（CSM）。

<div id="non-empty-legacy-fields" />

#### 非空值历史字段

大多数旧版字段为空或null`null`。但少部分字段仍包含数据，之所以被归类为历史字段，是因为：

* 它们在报告中已被重命名。
* 它们被排除在报告架构之外（已弃用）。

[下载非空值历史字段列表（CSV）。](https://docs.google.com/spreadsheets/d/e/2PACX-1vRzJr2IgKTHKq_6IFX-PFFv6_89ixtlbGZ9RNH134TniGlWa_M-85D1L2E7LhzQrDjictnSnNNnN2mm/pub?output=csv)

</Accordion>

<div id="9-save-the-connection" />

<Accordion title="10. 保存连接">

点击**保存**，首次数据转储将在3小时内写入您的云服务。此后，数据更新频率视具体报告而定。

<div id="important" />

> 🚧 **重要提示！**
>
> 对Data Locker设置的任何更改最多3小时后才能生效。

</Accordion>

<div id="set-user-permissions" />

## 设置用户权限

具有必要权限的管理员和团队成员都可以访问Data Locker。

* 管理员可以访问Data Locker页面、创建并管理所有的连接、开放编辑权限、指定现有连接的所有者。
* 团队成员可以访问Data Locker页面、编辑现有连接（需具备所有者权限）、创建新连接。他们 **不能** 管理所有权（设置所有者和编辑者），即使他们是账户所有者。

<div id="manage-data-locker-access-and-ownership-admins" />

### 管理数据存储器访问和所有权（管理员）

<div id="give-data-locker-access" />

#### 赋予数据存储器访问权限

* 如需向某个团队成员开放Data Locker的权限，请为其分配一个带有**Data Locker**管理权限的角色。

<div id="manage-ownership-and-editors" />

#### 管理所有权和编辑

要转移所有权或添加团队成员作为现有连接的编辑：

1. 点击三点选项菜单 <Image alt="3个点icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="1.18%" /> 在连接中。
2. 精选 **管理所有权**.
3. 更改连接所有者或添加编辑器。

<div id="review-filters-after-changing-ownership" />

#### 更换所有权后的审核过滤器

如果你将数据存储器连接的所有者更改为一个有数据访问限制（例如受应用、媒体来源、机构或国家限制）的用户，则该连接已存在 [全球层面](#select-global-level-filters) 或 [报告级过滤器](#7-select-the-reportlevel-filters) 可能会重置以匹配新所有者的权限。

转移所有权后，检查过滤器，确认连接是否反映预期的数据范围。

有关数据访问限制的更多信息，请参见 <Anchor target="_blank" href="/marketers/zh/docs/user-management#数据访问权限">用户管理>数据访问</Anchor>.

<div id="note-4" />

> 📘 **注意**
>
> 在 AF AWS 连接中，即使是管理员也没有 **管理所有权** 选项，因为只有管理员可以编辑、删除或创建新的 AF AWS 连接。采取此预防措施是为了防止暴露存储桶凭据。

<div id="data-storage-architecture" />

## 数据存储结构

<div id="zd-overview" />

<div id="overview" />

<Accordion title="概览">

您的数据构架取决于您使用的数据存储工具，即云存储或数据仓库。下文所述的目录结构是数据存储桶中的结构。如果您使用数据仓库存储数据，则其中的视图结构与本文中的目录结构类似，

Data Locker会将数据写入您指定的存储工具中。如果您使用云存储，您可以选择AppsFlyer的AWS存储桶或者您在AWS、GCS或Yandex上的自有存储桶。您可以随时切换存储工具、数据切分方式和数据宿端。

Data Locker以分级的目录结构将数据写入存储桶中，分级维度为报告类型、日期和时间。下图为目录结构示例：下图为目录结构示例：

![DLFolderOVerview.png](https://files.readme.io/78f360ec1df72253e5b2cd725f3eecf4e17548a7f06b544a94a75a2c319d77a0-18107910420369.png)

具体报告的数据保存在该报告类型下的小时数（h）文件夹中：

* 报告的数据时效性（每小时更新、每天更新或版本化）决定了文件夹名称中的小时数。
* 通过Snappy或GZIP压缩文件或未压缩的Parquet或CSV文件提供数据。
* 数据文件由列（字段）组成。
* 各种<Anchor target="_blank" href="/marketers/zh/docs/data-locker-advertiser-reports#user-journey">用户链路报告</Anchor>都具有完全相同的schema（字段）结构，具体取决于您选择的字段。其他报告各自有其显式字段，即无结构（schemaless）报告。详情请见<Anchor target="_blank" href="/marketers/zh/docs/data-locker-advertiser-reports#user-journey">营销人员的Data Locker报告</Anchor>，其中列出了可用的报告并提供了各种报告的说明文档链接。

</Accordion>

<div id="folder-structure" />

<Accordion title="目录结构">

| 文件夹 | 说明 |
| --- | --- |
| 订阅ID（Subscription ID） | <Image alt="DataLockerFolders.png" src="https://files.readme.io/0cda5728e48dab772878cad13ed3b81168f152e1bf01604ac45b700af804dd16-32966264039185.png" width="439px" /><ul><li>存储桶中的根目录命名方式取决于广告主和云服务商。一般情况下，根目录的名称即您的Subscription ID，但如果您使用Cyberduck，则该ID通过书签设置，而不会显示在目录结构中。</li><li>*data-locker-hourly*目录下是报告主题文件夹，其上级目录取决于存储桶的所有者和相关的云服务商。</li></ul>**各种场景的文件夹结构示例：**<ul><li>**AppsFlyer存储桶**：&lt;af-ext-reports>/&lt;unique\_identifier>/&lt;data-locker-hourly></li><li>**您的AWS存储桶**：*&lt;af-datalocker-your bucket prefix>/&lt;generated-home-folder>&lt;subscription-id>*</li><li>**您的GCS存储桶：** &lt;your bucket name>/&lt;generated-home-folder>/&lt;subscription-id></li></ul> |
| 主题（t） | 报告类型与报告主题相关。 |
| 日期（dt） | 代表相关的数据日期。对于原始数据，该日期表示事件发生的日期。对于汇总数据，该日期表示上报日期。 |
| 时间（h或版本编号） | 日期文件夹以<strong>小时数（h）</strong>或**版本编号**命名，具体取决于报告类型。<br /><br />**<span id="hourly-folders"></span>以小时数命名的文件夹**<br /><br />h文件夹的小时数是指AppsFlyer接收到数据的时间。比如AF会将UTC时间14:00-15:00之间接收到的激活数据写入h=14文件夹中。请注意：AF接收数据后需要1-3小时左右才能将相应的h文件夹写入Data Locker中。比如h=14文件夹会在1小时后，即UTC时间15:00写入到Data Locker中。<br /><br />**小时数文件夹的特点**：<ul><li>共有24个h文件夹，分别以0-23编号，比如h=0、h=1等等。</li><li>h=late（延迟）文件夹用于存储次日凌晨之后接收到的前一天的事件，即UTC时间的次日00:00–02:00之间发送到AF的事件。举例来说，如果某用户在UTC时间周一08:00激活某个应用，AF在UTC时间周二01:00接收到该激活，则AF会将该激活写入周一的延迟文件夹中。</li><li>AF会将UTC时间02:00之后接收到的数据按实际的接收日期和小时数写入相应的文件夹中。</li><li>取数时请务必一并拉取h=late文件夹中的数据，任何其他文件夹都不包含这些数据。</li><li>\_temporary 文件夹：在某些情况下，系统会在h文件夹内生成一个临时文件夹。请忽略这些临时文件夹及其子文件夹。例如：/t=impressions/dt=2021-04-11/h=18/**\_temporary**。</li></ul>日度报告：<ul><li>原始数据报告每天写入一次，保存在h=23文件夹中。卸载报告一般保存在h=2文件夹中，但也可能出现在其他文件夹中。</li><li>群组和增量报告直接保存在dt文件夹中。</li><li>版本化报告的命名与本节所述方式不同。</li></ul>**非UTC时区应用的逐时报告注意事项**<br /><br />要确保拉取到某一天的全部数据，必须按应用时区来确定具体日期，并拉取该日期的文件夹。方法如下：<ul><li>**东半球时区**：如需拉取某个日期的所有数据，必须按UTC时间和日期取相应文件夹中的数据。举例来说，假设相关应用的时区是UTC+10（澳大利亚悉尼）。要获取悉尼时间周二的所有小时数据，您需要读取以下文件夹：周一：h=14–23 以及晚些时候的文件夹 周二：h=0–13 和 h=14–15 为什么需要读取周二的 h=14–15 文件夹？这是因为有些数据传输到AF可能会有延迟，h=14–15 文件夹中可能包含这些延迟事件。然后，您还需要将悉尼日期换算成UTC日期，按相应的event\_time（事件时间）筛选数据。</li><li>**西半球时区如需拉取某个日期的所有数据，必须按UTC时间和日期取相应文件夹中的数据。举例来说，示例：假设相关应用的时区是UTC- 7（美国洛杉矶）。要获取洛杉矶时间周二的所有小时数据，您需要读取以下文件夹：周二：h=7–23 以及晚些时候的文件夹 周三：h=0–6 和 h=7–8注意：取数时必须包含周三的h=7-8文件夹，这是因为有些数据传输到AF可能会有延迟，而这些延迟送达的事件数据会出现在h=7–8文件夹中。然后，您还需要将悉尼日期换算成UTC日期，按相应的event\_time（事件时间）筛选数据。**</li></ul>**<span id="version-folders"></span>部分报告可按版本化方式命名**<br /><br />部分报告会按版本化方式命名。也就是说，Data Locker会多次写入指定日期的最新数据。这是因为有些数据的接收会有延迟，或后续出现了更准确的数据，因此Data Locker中的数据会持续更新，从而使同一个报告出现多个版本，其中最近期的版本数据最准确。<br /><br />指定日期的报告保存在该日期下的版本编号文件夹中。每个版本各自放在单独的文件夹中，这些文件夹的名称是通过Epoch时间戳来命名的，用以识别相关报告。<br /><br />在设计数据入库流程时，请务必注意Data Locker会回溯性地写入数据。比如Data Locker可能会在1月14日在1月1日的文件夹中写入数据。如果您使用的是自有存储桶，建议使用云服务消息通知来触发入库流程（<Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/NotificationHowTo.html">AWS</Anchor> \| <Anchor target="_blank" href="https://cloud.google.com/storage/docs/pubsub-notifications">GCS</Anchor>） |

</Accordion>

<div id="app-segregation" />

<Accordion title="分应用取数">

如果您使用云端存储桶，Data Locker可以将所有指定应用的数据文件合并到统一的数据文件中，也可以将数据按应用分别写入不同的文件夹中。分应用写入的数据会放在h文件夹下，详情请见下表。

| 区隔类型 | 说明 |
| --- | --- |
| 【默认】合并 | 所有应用的数据合并在统一的数据文件中。取数时请使用行级的app\_id field字段来区分不同应用的数据。<br /><br /><strong>示例：h=2文件夹下为数据文件</strong><br /><br />![UnifiedByApp.png](https://files.readme.io/dbc39c2ce99c1ff607fd553b9c9034e55728c102f31fd18a501cc00910267b28-18107874522513.png)<br /><br />数据文件的命名方式为unique\_id.gz。<ul><li>您的数据拉取流程必须符合以下要求：<ul><li>必须在\_SUCCESS标签设置完毕后再拉取数据。</li><li>必须拉取扩展名为<em>.gz</em>的文件夹中的所有文件。在数据入库流程中使用分卷编号逻辑。</li></ul></li></ul> |
| 分应用取数 | 文件夹中包含分应用的子文件夹。具体应用的数据文件保存在该应用的文件夹中。下图中的h=19文件夹含有应用文件夹，每个应用文件夹中包含相关的数据文件。请注意：数据文件名称中没有app\_id，必须通过文件夹名称中的app\_id来识别。<br /><br />![DLSegregateByApp.png](https://files.readme.io/90639507da82f7dafacfa5bfb67fa96a8277747cd0eee226d74498bf5ff16869-32966264040977.png)<br /><br />各应用文件夹的命名方式为unique\_id.gz：<ul><li>您的数据拉取流程必须符合以下要求：<ul><li>必须在\_SUCCESS标签设置完毕后再拉取数据。</li><li>必须拉取扩展名为*.gz*的文件夹中的所有文件。在数据入库流程中使用分卷编号逻辑。</li></ul></li></ul>局限性：PBA报告无此选项。 |

</Accordion>

<div id="data-files" />

<Accordion title="数据文件">

不同的分类取数方式会产生不同的数据文件。

<table><thead><tr><th>内容</th><th colspan="2">说明</th></tr></thead><tbody><tr><td>完成标签</td><td colspan="2"><p>一个h文件夹中的所有数据都写入完毕后，系统会设置末尾文件（完成）标签。 </p><ul><li>请务必先确认数据带有_SUCCESS标签，然后再拉取数据。</li><li>即使某个文件夹中没有数据可写（即该文件夹为空时），系统也会设置_SUCCESS标签。</li><li>请注意：在分应用取数时，需在h文件夹（而非应用文件夹）中确认该标签。详情请见上节图示。 </li></ul></td></tr><tr><td>文件类型</td><td colspan="2"><ul><li>通过Snappy或GZIP压缩文件或未压缩的Parquet或CSV文件提供数据。</li><li>解压后的数据文件是Parquet或CSV格式的，具体取决于您的设置。</li></ul></td></tr><tr><td>字段顺序（CSV文件） </td><td colspan="2"><p>如果是CSV文件，则报告中的字段顺序总是不变的，新添加的字段会出现在现有字段的右侧。 </p><p>在这种情况下： </p><ul><li>各种用户链路报告的字段结构完全一致。也就是说，不同类型的报告可以使用相同的数据入库流程。请参考<a href="./raw-data-field-dictionary" target="_blank">原始数据字段词典</a>中的字段释义，在报告中选择您需要的字段。</li><li>在报告可用性部分中，带有FF标记的报告字段结构与一般报告不同。 </li></ul></td></tr><tr><td>字段填充注意事项</td><td colspan="2"><p><strong>空白或空字段：</strong> 字段可能为空或为<em>null</em>，出现这种情况即表示这个字段在该报告中没有数据可以上报。一般来说，<em>null</em>表示该字段在相应报告和应用类型中不适用。空值（显示为"'）表示该字段适用于相应的报告和应用类型，但未找到相关数据。 </p><p>如果媒体渠道受限，则受限字段的值为“null”。 </p><p>总体而言，null值和空值的含义基本相同，都可以理解为没有可用的值。 </p><p><strong>时区和货币</strong></p><p>您在应用配置中指定的时区和货币对Data Locker中的数据无效。Data Locker数据的时区和货币单位如下： </p><ul><li> 时区日期和小时数按UTC时间计算。</li><li> <strong>货币</strong>：event_revenue_usd字段以美元为单位。</li></ul><p><strong>带逗号的值</strong>：逗号包含在双引号`"`中，例如，<code>`"iPhone6,1"`</code>。</p></td></tr></tbody></table>

</Accordion>

<div id="storage-options" />

<Accordion title="存储工具选项">

<div id="caution" />

> ❗️ **注意：**
>
> 如果您使用的是广告主侧自有存储工具：
>
> * 请确保您符合GDPR等数据隐私条例以及广告平台/SRN的数据保存规定。
> * 请勿使用您的自有存储桶向第三方发送数据。

* 可选的存储工具如下：
  * AppsFlyer存储桶
  * 客户自有存储工具——AWS、GCS、Azure、Yandex、BigQuery和Snowflake
* 您可以随时切换存储工具。
* 更改存储工具后会发生以下变化：
  * AF会在一小时内将数据写入新的存储桶。
  * 更改存储工具后会有一个7天的过渡期，在此期间我们会继续将数据写入原先的存储工具。您可以在AF后台查看过渡期的结束时间，以便对后续的数据入库流程变更做出相应的安排。您也可以根据实际情况重启过渡期，或换回AppsFlyer存储桶。
  * **切换存储选项**：您可以使用多宿端存储选项，将数据同时发送到多个宿端，这样就能切换存储选项。完成迁移和测试后，请删除弃用的存储选项。

|  | AppsFlyer的AWS存储桶 | 广告主自有存储工具（AWS、GCS、Azure、Yandex、BigQuery和Snowflake） |
| --- | --- | --- |
| 存储区名称 | 由AppsFlyer设置 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>：没有限制</li><li><Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>：由广告主设置。必须带有前缀af-。</li></ul>示例：`af-datalocker-your-bucket-name` |
| 存储桶所有者 | AppsFlyer | 营销人员 |
| 存储平台 | AWS | AWS、GCS、Azure、Yandex、BigQuery、Snowflake |
| 广告主用于访问数据的证书 | AppsFlyer账户的管理员可以在其Data Locker界面中查看此信息。 | AppsFlyer不掌握该信息。用户证书是由云服务商提供的。 |
| 数据保留 | 数据会在14天后自动删除。 | 广告主侧负责 |
| 数据删除请求 | 由AppsFlyer执行 | 广告主侧负责 |
| 数据安全 | 存储桶由AppsFlyer管理。客户具有只读权限。 | 存储工具的控制权限在广告主侧。<ul><li>**AWS**：AppsFlyer需要存储桶的GetObject、ListBucket、DeleteObject、PutObject权限。该存储桶必须仅用于AppsFlyer数据存储。请勿将其用于其他用途。</li><li>**GCS**：详情请见<Anchor target="_blank" href="/marketers/zh/docs/data-locker-cloud-service-setup">GCS配置指南</Anchor>。</li></ul> |
| 存储容量 | 由AppsFlyer管理 | 由广告主侧管理 |
| 使用带存储桶策略的VPC端点读取数据 | 不适用 | 【可选】如果您在AWS的存储桶层级采取了VPC端点安全防护措施，必须将AppsFlyer的服务器加白。 |

<div id="notice-to-security-officers-in-the-case-of-customer-controlled-storage" />

#### **广告主自有存储桶的数据安全负责人须知**

考虑：

* 该存储桶或宿端仅可用于AppsFlyer的数据写入，不能有其他实体向该宿端写入数据。
* AF写入数据的25小时后您可以从相关宿端中删除该数据。
* 宿端中的数据是AF服务器中数据的副本。我们会按AF的数据保存规定将这些数据保存在服务器中。
* 出于技术原因，我们有时需要删除并重写数据。Data Locker需要具备delete（删除） 和list（列出）权限。这两项权限不会带来安全风险。对于list权限，，我们是唯一可以向存储桶写入数据的实体。在delete权限下，我们能够在需要时重新生成数据。
* 如需了解其他相关信息，请发送邮件至[hello@appsflyer.com](mailto:hello@appsflyer.com)联系我们的数据安全团队或您的CSM。

</Accordion>

<div id="multipleconnections-principles-more-than-one-destination" />

<Accordion title="多宿端作用原理">

您可以使用Data Locker将您的部分或所有数据发送到2个宿端（在连接部分设置）。比如，将A应用的数据发送到AWS，将B应用的数据发送到GCS。

每个连接由一套完整的Data Locker设置组成，其中包含一个宿端。每个连接的设置都是单独分开的。

管理宿端连接时需注意以下几点：

* 宿端连接在Data Locker设置部分中，分单独的标签页显示。也就是说，您可以在各连接的专属标签页中管理其配置。每个标签页的图标代表相应的存储工具类型。
* 如需查看连接详情、创建连接副本或删除连接，请点击⋮（选项图标）。

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="track-connection-changes-in-the-audit-log" />

<Accordion title="在审计日志中跟踪连接变更">

您可以在AppsFlyer面板的安全中心查看Data Locker连接的变更记录。通过审计日志，您可以确认是否发生了变更、变更时间以及执行操作的用户。您可以在不依赖支持团队的情况下，排查缺失数据或连接意外变更等问题。

审计日志会记录以下生命周期事件：

* 创建新连接
* 更新连接
* 禁用连接
* 删除连接

**访问审计日志的步骤如下：**

1. 在顶部导航栏中，打开<Image alt="HQ1 2025-05-05 10.48.04.png" src="https://files.readme.io/b7020f3b633fb66e0e2d4988c7903426509b1fa871693cee602a39b8eb9d69d1-34955489919889.png" width="4.24%" />账户菜单。
2. 选择**安全中心**。
3. 在**审计日志**部分，点击**查看审计日志**。
4. 在筛选条件中选择“服务”：**Data Locker**以查看相关条目。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/audit-log">审计日志</Anchor>。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特性与局限性">

| **特点** | 说明 |
| --- | --- |
| 广告平台 | 广告平台不可用 |
| 代理 | 代理不可用 |
| 应用层级的指定时区 | 不适用。Data locker文件夹按UTC时间逐时拆分。实际事件时间是以UTC时间显示的，请根据需要将其换算到其他时区。不论您在应用配置中设定了哪个时区，从事件发生到Data Locker记录事件之间的延迟保持不变。 |
| 应用配置中的指定货币 | 不支持 |
| 大小限制 | 不适用 |
| 数据时效性 | 数据的更新频率取决于具体报告的数据时效性，详情请见<Anchor target="_blank" href="/marketers/zh/docs/data-locker-advertiser-reports#原始数据报告">本文档</Anchor>。 |
| 历史数据 | 不支持。如需拉取历史数据，请使用Pull API（仅部分报告具有可用的历史数据）。 |
| 受限数据 | 为了符合隐私政策的规定，部分报告中的字段受限。<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">详情请见此处说明。</Anchor> |
| 用户权限 | 如需配置Data Locker，<Anchor target="_blank" href="/marketers/zh/docs/user-management">须具备相关权限</Anchor>。 |
| 单应用/多应用 | 支持多应用取数。Data Locker是帐户级别的功能。 |
| 最大连接数 | 默认情况下，每个账号最多可以开启**2个Data Locker连接**。如需申请额外连接，**请联系您的客户成功经理（CSM）**。 |

</Accordion>

<div id="troubleshooting" />

<Accordion title="问题排查">

* **问题**：无法使用AWS CLI获取数据
* 报错消息 调用ListObjectsV2时出现错误（AccessDenied），收到“Access Denied”消息（拒绝访问）访问被拒绝
* **原因**：AppsFlyer存储桶的AWS证书不正确。这可能是由于您的计算机上有多个证书或无效证书。
* **解决方法**：
  1. 请换一种方法（例如[Cyberduck](/docs/data-locker-for-marketers#cyberduck)）访问存储桶，不要使用CLI。这是为了验证您使用的证书是否能正常生效。如果可以通过Cyberduck连接，则表明是证书缓存的问题。
  2. <Anchor target="_blank" href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-role.html">刷新AWS证书缓存</Anchor>。  
     **Screenshot from AWS** ![mceclip0.png](https://files.readme.io/e6608b196c39cb71e0a02e0eabe95378f24659a1578a16fd381bfd0053ca309e-32966264043537.png)

</Accordion>

<div id="aws-data-retrieval" />

## AWS数据拉取

本节解释了AWS数据拉取工具的使用方式，这些工具包括AWS CLI、Cyberduck、Amazon S3浏览器。请注意：下文说明是针对AppsFlyer存储桶编写的。如果您使用的自有存储桶，请根据实际情况调整相关操作。

<div id="aws-cli" />

<Accordion title="AWS CLI">

**前期准备** ：

* 在您的电脑上安装AWS CLI。
* 从AppsFlyer面板进入Data Locker配置页面，然后在证书栏中获取所需信息。

**请按以下方式使用AWS CLI**：

1. 在Windows中使用&lt;Windows>+&lt;R>键，然后点击**OK**，打开相关终端。  
   界面显示命令行窗口。
2. 输入**aws configure**。
3. 输入证书面板中显示的AWS Access Key。
4. 输入证书面板中显示的AWS Secret Key。
5. 输入**eu-west-1**。
6. 按下回车键。

根据需要使用以下CLI命令。

您可以在以下命令中找到`{home-folder}` 的值

**如需在存储桶中列出文件夹：**

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/
```

<div id="listing-files-and-folders" />

### 列出文件和文件夹

Data Locker存储桶中有三类文件夹：

* 报告类型`t=`
* 日期（date）`dt=`
* 小时`h=`

如需列出某个报告类型下的所有报告：

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/
```

如需列出某个报告类型在某个日期的所有报告：

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17
```

如需列出某报告类型在某日某时的所有报告：

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17/h=23
```

如需下载特定日期的文件：

```bash
aws s3 cp s3://af-ext-reports/<home-folder>/data-locker-hourly/t=installs/dt=2020-08-01/h=9/part-00000.gz ~/Downloads/
```

</Accordion>

<div id="cyberduck" />

<Accordion title="Cyberduck">

**前期准备** ：

* 安装Cyberduck客户端。
* 从AppsFlyer面板进入Data Locker配置页面，然后在证书栏中获取所需信息。

**请按以下步骤配置Cyberduck**：

1. 在Cyberduck后台点击“Action”（操作）。
2. 选择**New Bookmark**（新建书签），打开配置窗口。
3. 在第一个字段（在下面的截图中标记为 [1]）中选择 **Amazon S3。** [![DataDuckSmall2.png](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)
4. 填写以下字段：
   * <strong>昵称：</strong> 自定义文本
   * **Server**（服务器）：s3.amazonaws.com
   * **Access Key ID（访问密钥ID）：复制AppsFlyer后台的证书栏中显示的AWS Access Key。**
   * **Secret access key（秘密访问密钥）：复制AppsFlyer后台的证书栏中显示的Bucket Secret Key。**
   * 路径：`{存储桶名称}/{主文件夹}` 例如：**af-ext-reports/1234-abc-ffffffff**
5. 点击窗口右上角的X，关闭该窗口。
6. 选择相关连接。  
   界面会展示数据目录。

</Accordion>

<div id="amazon-s3-browser" />

<Accordion title="Amazon S3浏览器">

**前期准备** ：

* 安装Amazon S3浏览器。
* 从AppsFlyer面板进入Data Locker配置页面，然后在证书栏中获取所需信息。

**请按以下步骤配置Amazon S3浏览器**：

1. 在S3浏览器中点击**Accounts** > **Add** **New Account**。  
   界面打开Add New Account（添加新账户）窗口。
2. 填写以下字段：
   * **Account Name**（账户名）：自定义文本。
   * **Access Key ID**（访问密钥ID）：复制证书栏中的AWS Access Key。
   * **Secret Access Key**（秘密访问密钥）：复制证书栏中的Bucket Secret Key。
   * 选择**Encrypt Access Keys**（对密钥加密），输入密码。将此密码记录下来，以防遗忘。
   * 选择**Use secure transfer**（使用安全传输）。
3. 点击**Save changes**。
4. 点击**Buckets** > **Add External Bucket（添加外部存储桶）**。  
   界面打开Add External Bucket窗口。  
   <Image alt="mceclip2.png" src="https://files.readme.io/88dd43f62dbd68d0295b52a7f7b9b09449bd915e6a6d52703c24a50583e05a6e-32966264054929.png" width="433px" />
5. 输入**Bucket name**（存储桶名称）。桶名称的格式如下：`{桶名称}/{主文件夹}`。您可以在在证书窗口中看到存储桶名称和主文件夹的值。
6. 点击**Add External bucket**（添加外部存储桶）。系统创建存储桶并将其展示在窗口左侧边栏中。  
   完成上述操作后，您就能访问Data Locker文件了。

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/data-locker-advertiser-reports">可通过Data Locker拉取的报告</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">如何选择合适的原始数据传输工具</Anchor>

<div data-zendesk-anchors="data-locker=%E9%80%9F%E8%A7%88 h_01HE2S6FANNTNB580CMHNX34YA=%E9%80%9F%E8%A7%88 data-locker%E2%80%94features=data-locker-features h_01HE2S6FANQH2GZ11S8S87H0YH=data-locker-features h_01HE2S6FAN6BFPJSZJBEE9P5VK=reports-available-via-data-locker set-data-locker-report-settings=data-locker%E6%8A%A5%E5%91%8A%E8%AE%BE%E7%BD%AE h_01JS45N2DNWZBHP5PH8ZG6FBTF=data-locker%E6%8A%A5%E5%91%8A%E8%AE%BE%E7%BD%AE h_01JS45N2DNEZZJRF2RKG1RM9NK=1-set-up-your-cloud-service h_01JS45N2DNVA0SHBA49G42GNFE=2-add-a-connection-to-your-cloud-service h_01K22P5FWJ96CPFJPW0XDCHNNJ=%E6%B3%A8%E6%84%8F h_01JS4ASE6J6X1DD33PEGQAPXPA=aws-cloud-bucket-connection h_01JS4ASE6J587JPHAMCSBA2Z92=gcs-cloud-bucket-connection h_01JS4ASE6J4NC7M0TRFDT7F2X7=azure-cloud-bucket-connection h_01JS4ASE6JKFTM3FYAEKFHRW2M=yandex-cloud-bucket-connection h_01JS4ASE6JKV8WJG68RMHKVCE5=bigquery-data-warehouse-connection h_01JS4ASE6JBNE5BK04QDRM7CW4=snowflake-data-warehouse-connection h_01JTFRHNRRJB76JBXXT1TBNRBY=%E6%B3%A8%E6%84%8F-1 h_01JS45N2DN8JTMQCK76PDBBWA4=3-set-the-report-output-settings h_01JSBTCZ5569RCV6W6QWT400R7=%E6%B3%A8%E6%84%8F-2 h_01JS45N2DNMQAGFVHDDD5JGF2M=select-global-level-filters h_01JS45N2DN388YVP29DDBBBFBP=5-select-the-report h_01JVPJ9CG45JREBKP3ZQXKZWRZ=customize-or-duplicate h_01JS45N2DP4FK9EZYNTY2GX2GK=6-select-the-report-fields h_01JS45N2DPN7B73X0TRC82JW87=7-select-the-reportlevel-filters h_01JS45N2DPYYABS9NXFXP23ARA=8-remove-legacy-fields h_01JS45N2DPYNBG9VPCZJ481DFE=%E6%B3%A8%E6%84%8F-3 nonempty-legacy-fields=%E9%9D%9E%E7%A9%BA%E5%80%BC%E5%8E%86%E5%8F%B2%E5%AD%97%E6%AE%B5 h_01JSCC6KZNKJAVYSFCDDSE80YW=%E9%9D%9E%E7%A9%BA%E5%80%BC%E5%8E%86%E5%8F%B2%E5%AD%97%E6%AE%B5 h_01JS45N2DPH1QAREYGN5H20T8R=9-save-the-connection h_01JS45N2DPNPXAEZ74J0ETP7BS=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA set-user-permissions=%E8%AE%BE%E7%BD%AE%E7%94%A8%E6%88%B7%E6%9D%83%E9%99%90 h_01KH8D60TDTNS4EWNXJ4JPGXZ2=%E8%AE%BE%E7%BD%AE%E7%94%A8%E6%88%B7%E6%9D%83%E9%99%90 manage-data-locker-access-and-ownership-admins=%E7%AE%A1%E7%90%86%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E5%99%A8%E8%AE%BF%E9%97%AE%E5%92%8C%E6%89%80%E6%9C%89%E6%9D%83%E7%AE%A1%E7%90%86%E5%91%98 h_01KH8D60TEFX2MCW00JT94F9AQ=%E7%AE%A1%E7%90%86%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E5%99%A8%E8%AE%BF%E9%97%AE%E5%92%8C%E6%89%80%E6%9C%89%E6%9D%83%E7%AE%A1%E7%90%86%E5%91%98 give-data-locker-access=%E8%B5%8B%E4%BA%88%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E5%99%A8%E8%AE%BF%E9%97%AE%E6%9D%83%E9%99%90 h_01KH8D60TE541XMXWCVK0HZTJA=%E8%B5%8B%E4%BA%88%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E5%99%A8%E8%AE%BF%E9%97%AE%E6%9D%83%E9%99%90 manage-ownership-and-editors=%E7%AE%A1%E7%90%86%E6%89%80%E6%9C%89%E6%9D%83%E5%92%8C%E7%BC%96%E8%BE%91 h_01KH8D60TF69FN7KMBPMZHBW27=%E7%AE%A1%E7%90%86%E6%89%80%E6%9C%89%E6%9D%83%E5%92%8C%E7%BC%96%E8%BE%91 review-filters-after-changing-ownership=%E6%9B%B4%E6%8D%A2%E6%89%80%E6%9C%89%E6%9D%83%E5%90%8E%E7%9A%84%E5%AE%A1%E6%A0%B8%E8%BF%87%E6%BB%A4%E5%99%A8 h_01KH8D60TFYMEY8FEPR4YKJRYJ=%E6%9B%B4%E6%8D%A2%E6%89%80%E6%9C%89%E6%9D%83%E5%90%8E%E7%9A%84%E5%AE%A1%E6%A0%B8%E8%BF%87%E6%BB%A4%E5%99%A8 h_01KH8D60TGVN75TMS9QES0G6CQ=%E6%B3%A8%E6%84%8F-4 architecture=%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E7%BB%93%E6%9E%84 data-storage-architecture=%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E7%BB%93%E6%9E%84 h_01HE2S6FAN4H9DQ5HBTKSNJ72B=%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E7%BB%93%E6%9E%84 h_01HE2S6FANY1FWEY6Y34T85GHM=overview h_01HE2S6FANDJ65MZ2H2FBAZYJR=folder-structure h_01HE2S6FAN7PBZ8M86FQVSN5KQ=hourly-folders h_01HE2S6FAN366V8HNCY4PFNTFG=version-folders h_01HE2S6FANHFZMCY3WZBZB9QMP=app-segregation h_01HE2S6FANVDFH9S9JN8E9J7ES=data-files h_01HE2S6FAN8ZDF5N4ECKKN1D1H=storage-options h_01HE2S6FAN2HY7V3G9NS9XCVE1=%E6%B3%A8%E6%84%8F-5 notice-to-security-officers-in-the-case-of-customercontrolled-storage=%E5%B9%BF%E5%91%8A%E4%B8%BB%E8%87%AA%E6%9C%89%E5%AD%98%E5%82%A8%E6%A1%B6%E7%9A%84%E6%95%B0%E6%8D%AE%E5%AE%89%E5%85%A8%E8%B4%9F%E8%B4%A3%E4%BA%BA%E9%A1%BB%E7%9F%A5 h_01HE2S6FANRVGYPRWWFA50JAQ4=%E5%B9%BF%E5%91%8A%E4%B8%BB%E8%87%AA%E6%9C%89%E5%AD%98%E5%82%A8%E6%A1%B6%E7%9A%84%E6%95%B0%E6%8D%AE%E5%AE%89%E5%85%A8%E8%B4%9F%E8%B4%A3%E4%BA%BA%E9%A1%BB%E7%9F%A5 h_01HE2S6FANBRXA0NS4E8SP3618=multipleconnections-principles-more-than-one-destination additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HE2S6FAP4SA77B0SX7R8JMTY=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01JTFQMKN0046SNBB4YSRJMQG9=track-connection-changes-in-the-audit-log h_01HE2S6FAP6FKAJCW92JVWD828=traits-and-limitations h_01HE2S6FAPJC20G7YZSRWP5E34=troubleshooting aws-data-retrieval=aws%E6%95%B0%E6%8D%AE%E6%8B%89%E5%8F%96 h_01HE2S6FAPJMKX567HSAR16TCN=aws%E6%95%B0%E6%8D%AE%E6%8B%89%E5%8F%96 h_01HE2S6FAPB5MW09Y4HKFV3RM8=aws-cli listing-files-and-folders=%E5%88%97%E5%87%BA%E6%96%87%E4%BB%B6%E5%92%8C%E6%96%87%E4%BB%B6%E5%A4%B9 h_01HE2S6FAP31H9NK6V870FGXZF=%E5%88%97%E5%87%BA%E6%96%87%E4%BB%B6%E5%92%8C%E6%96%87%E4%BB%B6%E5%A4%B9 h_01HE2S6FAP2E2TW4F5PJ4226Q0=cyberduck h_01HE2S6FAP74NG5VNEWKWXXJX2=amazon-s3-browser h_01HE7RB5N99WJ3XP69Z69H81AD=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

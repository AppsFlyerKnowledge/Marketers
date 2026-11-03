---
title: 数据协作平台 (DCP)-添加连接
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
  created_at: '2024-04-28T13:26:59Z'
  edited_at: '2026-10-14T10:07:29Z'
  id: 24603890457617
  locale: zh-cn
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/zh-cn/articles/24603890457617
---
> **概要：** 设置 DCP 连接以连接数据源、丰富数据并将受众导出到云存储和媒体合作伙伴。

## 关于 DCP 连接

连接决定了 DCP 如何摄取您的数据和导出受众。<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">设置云服务</Anchor>后，使用**管理连接模式将它们连接**到 DCP。以下连接类型可用：

* [**源连接**](#create-source-connections)：用于将您的第一方数据从云存储或数据仓库摄入到 DCP 中。
* [**云存储连接**](#create-cloud-storage-connections)：用于将受众导出到您的亚马逊 S3 或谷歌云存储 (GCS) 存储桶。
* [**媒体合作伙伴关系**](#create-media-partner-connections)：用于将您的受众引导到广告平台进行激活。
* [**数据和身份连接**](#create-data-identity-connections)：用于统一分散的用户数据，以提高匹配率并扩大合作伙伴方面的受众。

DCP 为不同的连接方向支持不同的云服务。使用下表查看每种连接类型可以使用哪些服务：

| 云服务 | 来源（入站） | 云存储导出（出站） |
| --- | --- | --- |
| Amazon S3 | ✓ | ✓ |
| Google Cloud Storage | ✓ | ✓ |
| BigQuery | ✓ | - |
| Snowflake | ✓ | - |
| Salesforce Cloud/CRM | ✓ | - |

对于 Amazon S3 和 Google 云存储，单个连接既是源（入站）又是云存储导出（出站）目的地。创建与 S3 或 GCS 的源连接会自动创建匹配的云存储（导出）连接，反之亦然。

<div id="create-source-connections" />

<Accordion title="创建源连接">

创建源连接，将第一方数据导入 DCP。

**要创建源连接，请执行以下操作：**

1. 在 AppsFlyer 中，前往 “**协作**” > “**数据整理室**”。
2. 点击右上角的**管理连接**。
3. 转到**来源**选项卡，然后单击 **+ 新建连接**。  
   <Image alt="2026-07-27_13-30-46.png" src="https://files.readme.io/dec879432c0b9d6ba4eeec2c175dfce145c99652ccabb02d37f3434627f9310f-49189748198289.png" width="529px" />
4. 继续使用[云服务连接，获取以下源数据说明](#源数据的云服务连接)。

您也可以在设置源时直接创建源连接。有关说明，请参阅<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources">创建和管理来源</Anchor>。

> 📘 **注意**
>
> 创建与 Amazon S3 或 GCS 的传入源连接会自动创建匹配的传出云存储连接（反之亦然）。删除 Amazon S3 或 GCS 连接也会自动删除另一个连接。由于它实际上是一个基础连接，因此将其从任一选项卡中删除都会将其移除到任何使用的地方。

#### 源数据的云服务连接

源连接用于将您的数据源安全地连接到 DCP。在 “**新建连接**” 对话框中，选择您的云服务并填写提供商的详细信息：

BigQuery**在新建连接**对话框中，输入包含您的源数据的**项目的 BigQuery 项目 ID**。你可以在谷歌云端控制台的 BigQuery 页面上找到这个信息。

Snowflake在 “**新建连接**” 对话框中，输入包含源**数据的账户的 Snowflake 账户 ID** 和**区域**。要找到此信息，请单击 Snowflake 控制台左下角的账户名称：

**账户管理员** > **账户** > 将鼠标悬停在相关账户上 > **复制账户**标识符。有关详细信息，请参阅 <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/admin-account-identifier#finding-the-organization-and-account-name-for-an-account">Snowflake 文档</Anchor>。

> 🚧 **重要提示！**
>
> 寻找标有 “**定位器**” 的 ID。**这**与创建出站 Snowflake 连接时使用的 ID 不同。

**亚马逊 S3 和 GCS：** 在 “**新建连接**” 对话框中，输入<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#cloud-storage-buckets-inbound">您创建的专供 AppsFlyer 数据净化室 (DCR) 使用的存储分区的</Anchor>名称。

**Salesforce 云/CRM：** 查看<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-integration-with-salesforce-data-cloud">如何设置 Salesforce 连接</Anchor>。

#### 本地文件连接

本地文件系统连接允许您将数据文件直接从计算机上传到 DCP。此选项通常仅用于测试，不建议用于持续或大规模的数据摄取。

<div id="set-up-a-local-file-connection" />

<Accordion title="设置本地文件连接">

本地文件连接用于使用示例文件测试平台。它可以让你在开始共享数据之前熟悉 DCP 功能。请记住，不建议共享数据，数据保留期限为 14 天，并且不支持自动化流程。

可以在<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#本地文件的数据源位置">创建源代码期间设置</Anchor>本地文件连接。

</Accordion>

</Accordion>

<div id="create-cloud-storage-connections" />

<Accordion title="创建云存储连接">

云存储连接允许您在每次受众更新后自动将 DCP 受众导出到您的 Amazon S3 或谷歌云存储 (GCS) 存储桶。

**要创建云存储连接，请执行以下操作：**

1. 在 AppsFlyer 中，前往 “**协作**” > “**数据整理室**”。
2. 点击右上角的**管理连接**。
3. 转到**云存储**选项卡，然后单击 **+ 新建连接**。  
   <Image alt="2026-07-27_13-30-34.png" src="https://files.readme.io/1da10127617317d0ff466433c89712d78c104b6a943b4b669e1d7180d22df958-49189843742609.png" width="533px" />
4. **新的云存储连接**模式打开。
5. **在新云存储连接**模式中，选择您的云提供商：**谷歌云存储**或**亚马逊简单存储**。
6. 请输入您的存储桶名称
   * **GCS：** 按以下格式`gs://my-bucket`输入 GCS 存储桶名称。
   * **S3：** 输入 S3 存储桶名称。
7. 单击 “**测试连接**” 以验证 DCP 是否可以连接到您的存储桶。
8. 点击**保存**。新连接显示在 “**云存储” 选项卡中的 “您的云存储连接**” 下。

您也可以直接从受众生成器创建云存储连接。有关说明，请参阅<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-build-and-activate-audiences">建立和激活受众</Anchor>。

<div id="understand-export-path" />

<Accordion title="了解导出路径">

每次导出受众时，DCP 都会使用固定的、可预测的路径将其写入您的存储桶：

```
<bucket>/dcp-output/audiences/<collaboration-id>/t=<audience_name>_<id>/dt=<YYYY-MM-DD>/v=<version>/<file>.csv
```

**一次交付的文件夹内容示例：**

```
s3://af-dcr-example-bucket/dcp-output/audiences/8f3a1c02-44b1-4e9a-9c7d-2b6e1a0f5d3e/t=example_audience_6148a3/dt=2026-07-18/v=1/
  ├── part-00000-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv
  ├── part-00001-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv
  └── _SUCCESS
```

| 路径段 | 这是什么意思 |
| --- | --- |
| 存储桶： | 您连接的 S3 或 GCS 存储桶。 |
| dcp-output/audiences/ | 修复了 DCP 为所有受众导出自动创建的文件夹。 |
|  | 该受众所属合作的唯一 ID。你可以在 DCP 的协作网址中找到它。 |
| t=\_ | 受众名称（空格和特殊字符替换为下划线），外加唯一的 ID。这样可以确保已删除并重新创建的同名受众不会覆盖旧文件或与之发生冲突。 |
| dt= | 交货日期。 |
| v= | 该受众导出的版本号。每次新交付都会增加。 |
| part-NNNNN--c000.csv | 此交付的输出文件之一 — 请参阅下面的文件格式和拆分。 |
| \_SUCCESS | 导出完成写入所有零件文件后写入的空标记文件。 |

> 📘 **注意**
>
> 此文件夹结构是自动创建和管理的。不要手动对其进行重命名或重构——读取这些文件的任何自动流程都应遵循此路径模式，并且应等待 \_SUCCESS 出现后再处理零件文件，以避免读取部分交付。

**文件格式和拆分**

* 受众始终导出为未压缩的 CSV 文件，包含两列：`value`（标识符）和`taxonomy`（标识符类型）。
* 更大的受众可能以多个文件而不是编号的单个文件`part-00000``part-00001`等形式交付。默认情况下，每个文件最多包含大约 500,000 行。
* 单个文件可以在同一行中包含多种标识符类型——使用所需的标识符`taxonomy`列进行过滤。常见的分类值包括`customer_id`、`mobile_ad_id``hashed_email`、和。`hashed_phone_number_without_plus_sha256`

**示例：**

```
value,taxonomy
6f1a2b3c4d5e6f7a8b9c0d1e2f3a4b5c,customer_id
1a2b3c4d-5e6f-4a7b-8c9d-0e1f2a3b4c5d,mobile_ad_id
b7e2c9a1f4d6e8b0a2c4d6e8f0a1b3c5d7e9f1a3b5c7d9e0f2a4b6c8d0e2f4a6,hashed_email
c1d3e5f7a9b1c3d5e7f9a1b3c5d7e9f1a3b5c7d9e1f3a5b7c9d1e3f5a7b9c1d3,hashed_phone_number_without_plus_sha256
```

</Accordion>

</Accordion>

<div id="create-media-partner-connections" />

<Accordion title="建立媒体合作伙伴关系">

出站媒体合作伙伴连接使您可以安全地将您的DCP受众与支持的媒体合作伙伴联系起来，这样您就可以在他们的平台上激活量身定制的活动。媒体合作伙伴是激活受众的主要目的地。了解如何<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-media-partner-connections">建立特定的媒体合作伙伴关系</Anchor>。

**要创建媒体合作伙伴连接，请执行以下操作：**

1. 在 AppsFlyer 中，前往 “**协作**” > “**数据整理室**”。
2. 点击右上角的**管理连接**。
3. 转到**媒体合作伙伴**选项卡，然后单击 **+ 新建连接**。如果您已经有连接，则会在 “**媒体合作伙伴**” 下看到这些连接。
4. 在 “**新媒体合作伙伴连接**” 对话框中，选择相关的媒体合作伙伴。
5. 输入连接名称。
6. 使用您的凭证登录媒体合作伙伴账户，按照他们的指示启用 AppsFlyer 访问权限。
7. 单击 **“选择账户 ID**”，然后选择此连接的相关帐户。
8. 点击**保存**。新连接将添加到合作伙伴列表中。

您也可以直接从受众生成器中创建媒体合作伙伴连接。有关说明，请参阅<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-build-and-activate-audiences">建立和激活受众</Anchor>。

</Accordion>

<div id="create-data-identity-connections" />

<Accordion title="您的数据和身份连接">

数据和身份连接统一了分散的用户数据，以提高与激活合作伙伴的匹配率。这样可以扩大合作伙伴方的受众群体，并从您的活动中获得更大的影响力。

#### ID5

<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-enrich-sources-with-id5">使用 ID5 标识符丰富您的第一方数据</Anchor>，以统一分散的用户数据，提高与激活合作伙伴的匹配率，并增加合作伙伴端的受众规模。

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">配置您的云服务</Anchor>。
> * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-build-and-activate-audiences">DCP-建立和激活受众</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-media-partner-connections">DCP-媒体合作伙伴关系</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-enrich-sources-with-id5">DCP-使用 ID5 丰富资源</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-guide">数据协作平台 (DCP) 指南</Anchor>

</Accordion>

<div data-zendesk-anchors="about-dcp-connections=%E5%85%B3%E4%BA%8E-dcp-%E8%BF%9E%E6%8E%A5 h_01KXX80P91T92MH8KEGHVG3QP1=%E5%85%B3%E4%BA%8E-dcp-%E8%BF%9E%E6%8E%A5 h_01KXX80P913HRREW60M6S316PP=create-source-connections h_01KY4HCGBBCD5FZD9RYNNVDYRC=%E6%B3%A8%E6%84%8F source-cloud-service-connections=%E6%BA%90%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BA%91%E6%9C%8D%E5%8A%A1%E8%BF%9E%E6%8E%A5 cloud-service-connections-for-source-data=%E6%BA%90%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BA%91%E6%9C%8D%E5%8A%A1%E8%BF%9E%E6%8E%A5 h_01KXX80P914VFMH1T6FQF9KC31=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA local-file-connection=%E6%9C%AC%E5%9C%B0%E6%96%87%E4%BB%B6%E8%BF%9E%E6%8E%A5 h_01KXX80P91EFCGH3MYV729TGTH=%E6%9C%AC%E5%9C%B0%E6%96%87%E4%BB%B6%E8%BF%9E%E6%8E%A5 h_01KXX80P91HG17YTWE15ZWTBZ8=set-up-a-local-file-connection h_01KXX80P91F8TG9FR1XQ7QVNCY=create-cloud-storage-connections h_01KYEP2MX3KQ3BAP7VRSGYTFBB=understand-export-path h_01KYEP2MX3SHFCECTSTHV9RMS4=%E6%B3%A8%E6%84%8F-1 h_01KXX80P91BMB45ETZQSKWJWZB=create-media-partner-connections h_01KXX80P91PS35EG5P5YJB9EHC=create-data-identity-connections h_01KXX80P92BXD3B7ZVT1FC5HCF=id5 h_01KXX80P92WMPPRGD7321TBS7Y=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85" />

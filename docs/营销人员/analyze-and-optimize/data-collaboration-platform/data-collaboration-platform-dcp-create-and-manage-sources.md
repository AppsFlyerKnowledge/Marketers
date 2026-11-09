---
title: 数据协作平台 (DCP) - 创建和管理数据源
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2024-05-02T13:56:27Z'
  edited_at: '2026-11-01T10:52:27Z'
  id: 24740010687249
  locale: zh-cn
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/zh-cn/articles/24740010687249
---
> **At a glance:** 创建和管理数据源，以便安全地与其他协作者共享您的第一方数据。

<div id="about-dcp-sources" />

## 关于 DCP 数据源

在数据协作平台 (DCP) 中，数据源是指数据集，通常从您的云存储上传到 AppsFlyer。这些数据源构成了任何协作的基础，为您的协作者提供可用于创建和激活受众的数据。本文包含您需要了解的有关创建和管理数据源的全部内容，包括：

* [数据源要求](#数据源要求)
* [创建数据源](#创建数据源)
* [管理您的数据源](#管理您的数据源)

<div id="source-data-requirements" />

## 数据源要求

建议您对<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion">数据</Anchor>源进行预处理，以最大限度提高协作者数据集之间的匹配率，并优化协作结果。此外，所有数据源**都必须满足以下要求**。

<Accordion title="数据格式 （适用于所有数据源）">

数据必须满足以下要求：

* **日期** （仅）: yyyy-mm-dd（例如，`2023-04-18`）
* **日期与时间：**
  * **格式：** yyyy-MMM-dd hh:mm:ss （*例如*，`2023-APR-18 15:30:35`）
  * **时区：** UTC
* **数值：** 小数点后最多 2 位
* **字符串长度：** 最多 256 个字符
* **字符限制：**
  * **字段名称（列标题）：** 不可使用空格或特殊字符
  * **所有其他数据：** 无限制（所有字符均有效）

</Accordion>

<Accordion title="表列 （仅适用于数据仓库中的数据源）">

除了用于处理的数据之外，BigQuery 或 Snowflake 中的数据源表还必须包含另外 2 列：一列**日期**，一列**版本：**

* **日期：**
  * **列标题：**`dt`
  * **列类型：** date
  * **数据格式：** yyyy-mm-dd（*例如*，`2023-04-18`）
  * **其他说明：** BigQuery 表必须按此列<Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/partitioned-tables">分区</Anchor>
* **版本：**
  * **列标题：**`v`
  * **列类型：** 字符串
  * **数据格式：** 数字（例如，`1`、`2`、`3`、`10`）
  * <strong>重要提示！</strong>每次 DCR 检测到此列中出现新值时，都会触发生成新版本的报告。为了确保报告的完整性，请务必在该列的值发生变化时向表格中填充完整的一组数据。

</Accordion>

<Accordion title="文件名称和格式 （仅适用于云存储桶中的数据源）">

存储在 Amazon S3 或 GCS 中的数据源文件必须符合以下文件名称和格式要求：

* 文件名称必须符合 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR 命名要求</Anchor>
* CSV 或 GZIP 格式
  * GZIP 压缩文件中的文件必须为 CSV 格式。
* 每个<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-add-connections#snowflake-outbound">数据文件夹</Anchor>中的数据源文件数量：
  * **CSV：** 最多 1 个
  * **GZIP：** 最多 1 个不分卷的压缩文件。如需支持多部分 GZIP 文件，必须按照以下方式命名：`filename_part01.csv.gz`、`filename_part02.csv.gz` 等。

</Accordion>

<div id="create-a-source" />

## 创建数据源

**前提条件：** 在创建您的数据源之前，请先<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">设置云服务</Anchor>，AppsFlyer DCP 将使用这些服务来检索您的数据源数据。如果这些连接尚未设置，系统会在创建数据源时提示您进行设置。

**要在 DCP 中创建数据源，请按以下步骤操作：**

<Accordion title="步骤 1：访问 DCP 数据源">

1. 在 AppsFlyer 中，从侧边菜单选择 **协作** > **数据净室**。

   <Image align="center" alt="Click Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="644px" />
2. 点击 **+ 新数据源** （在主界面或在**数据源**标签页中）。

   <Image align="center" alt="sources empty state cropped.png" src="https://files.readme.io/629d8c7c68bfbce7c2307306128b0d0cc430886dc2a58200cb635bc0044d2bd7-33193030142609.png" width="482px" />
3. 继续完成 **新数据源** 的操作步骤：

</Accordion>

<Accordion title="步骤 2：设置数据源名称">

输入数据源名称。该名称可以是任意唯一名称，帮助您识别该数据源。您还可以选择添加关于该数据源的说明，帮助您轻松识别其中包含的内容（例如「2025 年的所有购买数据」）。

<div id="requirements-and-guidelines" />

#### 要求和指南

* 请确保该**数据源名称**在您账户中的所有数据源里是唯一的。否则，您将无法保存该数据源。
* 云服务对接的名称无需与文件名称一致。
* 数据源名称要求：
  * 长度：2-80 个字符
  * 有效字符：
    * 字母`（A-Z、a-z）`
    * 数字`（0-9）`，*不能作为名称的首字符；*
    * 下划线 `"_"`
  * 无效字符：
    * 空格
    * 所有其他符号和特殊字符

</Accordion>

<Accordion title="步骤 3：设置数据源位置">

**请按以下方式指定数据源位置：**

1. 选择即将创建（或已创建）数据源的<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#overview">连接</Anchor>。
   * 如果您的账户中没有定义任何连接，系统将弹出**新建连接的**对话框，提示您创建一个连接。请按照 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-add-connections">说明</Anchor>进行创建。
   * 如果您已有连接，但希望使用新的连接，请点击 **+ 新建连接** 并按照  <Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-connections">说明</Anchor>进行创建。
2. 根据您的数据源所在的位置，继续按下方说明进行操作。

**注意：** 当数据量较大时，为获得最佳性能，您的部分数据可能会被单独存储。当数据源更新时，此数据也会更新；当删除数据源时，此数据也会被删除。

<div id="source-locations-in-bigquery" />

#### BigQuery 数据源位置

**设置 BigQuery 的数据源位置：**

1. 选择源数据表所在的数据集。
2. 选择源数据所在的数据表。

您进行这些选择时，所用的列表分别包含您在创建连接时指定的 BigQuery 项目中的可用数据集和表。

<div id="source-locations-in-snowflake" />

#### Snowflake 数据源位置

**设置 Snowflake 的数据源位置：**

1. 选择包含源数据的共享（share）。
2. 选择源表所在的架构（schema）。
3. 选择源数据所在的数据表。

您进行这些选择时，所用的列表分别包含您在创建连接时指定的 Snowflake 账户中的共享（share）、架构（schema）和表。

<div id="source-locations-in-cloud-storage-buckets" />

#### 云存储桶的数据源位置

Amazon S3 或 GCS 的数据源位置由两部分组成：连接所指定的云存储桶，以及其下的文件夹路径——每次数据源更新时，DCR 都会从该路径读取源文件。

指定连接后，AppsFlyer 可在创建数据源的过程中，自动生成所需的底层文件夹路径。

* 允许 AppsFlyer 生成文件夹，这是最简单的操作。不过，您也可以选择根据<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">此处</Anchor>的说明改为手动创建。

如果由 AppsFlyer 生成这些文件夹，您唯一还需要额外提供的信息，是您希望为数据源文件夹指定的名称。（这是顶层文件夹。您还可以指定是否要将数据源文件夹创建在某个父文件夹之下– 该父文件夹通常命名为 **input**。

**设置云端存储桶中的数据源位置时，请输入数据源文件夹的名称。**

* 默认情况下，显示的数据源文件夹名称：
  * 是基于您指定的[数据源名称](#1-name-the-source)。您可以根据需求更改文件夹名称，但必须符合<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR 命名要求</Anchor>。
  * 表示它将在名为 <strong>input. 的父文件夹中生成。</strong>该文件夹是您上传到 DCR 的所有数据源的父文件夹。
    * **input** 文件夹不是必需的，您可以将其移除或改为其他名称，但必须符合<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR 命名要求</Anchor>。
    * 虽然该文件夹不是必需的，但设置 **input** 文件夹（或其他名称的等效文件夹）仍属于最佳实践。尤其是在您使用同一个云端存储桶同时上传数据文件（input）和接收报告（output）时，更建议这样做。

<div id="important" />

> 🚧 **重要提示！**
>
> 如果您手动创建了文件夹路径，请确保您在**数据源位置**部分输入的连接和路径与您手动创建的路径一致。


<div id="source-location-as-local-files" />

#### 本地文件的数据源位置

您也可以使用本地文件上传源数据。不过，**强烈建议您将云服务设置为数据源位置**（这对较大的数据集和自动更新尤为重要）。本地文件主要用于测试以及熟悉平台功能。

**使用本地文件上传源数据：**

1. **数据源文件夹设置**

<Image align="center" alt="Select Local file system.png" src="https://files.readme.io/08f4797196c915b73a543c7152b5090913287c61b12fefe893d3893ca76fc4d5-33193021989393.png" width="731px" />

<div id="note" />

> 📘 **备注**
>
> * 支持的文件类型：.CSV 和 .GZ 文件（最大 5 GB）。
> * 从本地文件上传的数据将保留 180 天。
> * 必须手动执行更新。

</Accordion>

<Accordion title="步骤 4。设置数据源更新方法">

在 Data Collaboration Platform（DCP）中设置数据源时，您必须选择希望如何处理该数据源的更新。 DCP 支持两种同步方法：**Snapshot** 和 **Append**。每种方法都适用于不同的使用场景和数据流：

* **Snapshot** - 此方法会在每次更新数据源时上传完整数据集，并以新数据集完全替换旧数据集。仅当您每次上传的文件始终包含完整且最新的数据集时，才选择此方法。
* **Append** - 此方法仅上传新增或已更改的数据，而不是完整数据集。旧数据集不会被删除或更新。此方法非常适合每日或每周报告等定期上传的场景。其优势包括上传量更小（可能降低云存储成本）、数据上传更快、更便于记录管理等。

<Image align="center" alt="Delta Generate folders.png" src="https://files.readme.io/105f55ff555565e97b82ecf86d58cfd2cf2a0340f83d6261fd3bd1c084b13889-38096875288977.png" width="637px" />

<div id="important-1" />

> 🚧 **重要提示！**
>
> 请在选择前先确定哪种方法最适合您。选择某个选项并点击 **Generate folders** 后，系统会在您所选的云服务中创建文件路径以及处理数据上传的说明。为防止文件夹重复和出现错误，在首次选择后，您**只能更改一次同步方法**。


<div id="h_01K2A7MAWTCYF3VAWJRRRJFNN5" />

<div id="snapshot-upload-requirements" />

#### Snapshot 上传要求

如果您要在每次更新数据源时上传一个完整且独立的文件，并完全替换之前的数据集，请使用此方法。

<span id="h_01K2A7MAWT05K506384QHYA0FN"></span>**支持的云服务**

* Amazon S3
* Google Cloud Storage（GCS）
* BigQuery
* Snowflake

**Snapshot 更新方法请遵循以下指南：**

1. **数据源文件夹路径**

   在 DCP 中注册云存储数据源时，系统会为该数据源定义一个根路径（例如 `input/my_source_folder/`）。每次刷新数据集时，您都会将**完整快照**——包含所有当前行的文件——上传到此文件夹。这可确保 DCP 始终处理最新且最完整的数据。
2. <span id="h_01K2A7MAWTPJ621MGBBG40N8H4"></span>**上传完整快照文件**

| 准则 | #save-the-source | 如何满足要求 |
| --- | --- | --- |
| **完整数据集** | DCP 必须完整替换先前状态 | 生成一份包含所有记录（而不仅仅是变更记录）的导出文件 |
| **按日期分区的文件夹（**`dt=`） | 支持按日期范围筛选 & 留存管理 | 将每个快照放在 `dt=YYYY‑MM‑DD/` 下 |
| **版本子文件夹（**`v=`） | 允许在同一天内有多个快照 | 首次上传使用 `v=1/`；重试时使用 `v=2/`、`v=3/` 等。 |
| `data/` **子文件夹** | 整理您的文件 | 将 Parquet / CSV / Avro 文件存储在此文件夹中 |
| `_SUCCESS` **标记** | 指示 DCP 开始采集数据 | 在所有数据文件都上传完成后，在 `v=` 文件夹内上传一个名为 `_SUCCESS` 的空文件 |
| **支持的文件类型和大小** |  | <ul><li>支持的文件类型：.csv 或 .gz</li><li>最大文件大小：5 GB</li></ul> |

<div id="important-2" />

> 🚧 **重要提示！**
>
> 完整快照文件（如下方截图中的 BI-data.csv）必须放置在：
>
> ```
> /v=1/data/
> ```
>
> 然后，当数据文件上传完成后，将一个空的 `_SUCCESS` 文件放置在：
>
> ```
> /v=1/
> ```

**文件夹结构：**

```
s3://af-dcr-xyz/abcd9876/input/source_name1/dt=2025-mm-dd/v=1/data/
└ 存储桶 ┘ └ 租户 ┘ └采集区┘ └数据源┘└快照日期┘└版本┘└文件┘
```

| 细分 | 描述 | 目的 |
| --- | --- | --- |
| `af-dcr-xyz` | S3 / GCS 存储桶 | 所有 DCP 数据的顶层容器 |
| `abcd9876/` | 租户 / 工作区 ID | 用于隔离每个客户的数据 |
| `input/` | 采集区 | 原始上传文件在处理前会先落入此处 |
| `source_name1/` | 数据源名称 | 在 DCP 中注册的逻辑数据集 |
| `dt=2025-mm-dd/` | 快照日期 | 表示该数据集在当日的完整状态 |
| `v=1/` | 版本（选填） | 支持重试上传，或添加额外快照 |
| `data/` | 文件 | Parquet / CSV / Avro 快照文件 |

<span id="h_01K2A7MAWTYFHBANCV9F2NKNCV"></span>**两天的快照结构示例：**

```
source_name1/
  dt=2025-08-10/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
  dt=2025-08-11/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
```

上传 2 天的数据源文件完整快照后（并以程序化方式创建日期/版本/data 文件夹及 \_SUCCESS 文件），您的存储桶/文件夹结构可能如下所示：

<Image align="center" alt="Snapshot example bucket.png" src="https://files.readme.io/a96762b43bbcae3d1265aa407e725ba885e27c3a83433d017aa30d7afaf31e37-38096860329233.png" width="219px" />


<div id="append-upload-requirements" />

#### Append 上传要求

当仅需要上传变化或新增数据时，可使用该方法。

为什么使用 Append？

* **效率**：上传量更小
* **数据完整性**：保留完整的变更历史，便于进行时间序列分析
* **隐私合规** – 简化记录删除 & 同意管理

**支持的云服务：** AWS S3 和 Google Cloud Storage (GCS)  
**注意：** BigQuery 和 Snowflake 不支持 Append 方法，必须使用 Snapshot 方法。

**请遵循以下 Append 更新方法指南：**

<span id="h_01K2A7MAWT8E6AX95VG86APXBB"></span>1. 点击**生成文件夹链接。**

| 步骤 | 描述 |
| --- | --- |
| **创建/分配存储桶** | 使用现有的 S3 / GCS 存储桶，或让 AppsFlyer 为您预配一个 |
| **定义根路径** | 已将租户范围的路径（例如 `s3://af‑dcr‑xyz/abcd1234/`）配置为输入目录 |
| **安全** | 仅向服务用户授予对此路径的写入权限 |

2. **上传追加（增量）文件**

| 指南 | 重要！ | 如何满足要求 |
| --- | --- | --- |
| **上传频率** | 可降低传输成本 & 运维开销 | 每天上传，或按 7 天文件夹打包后每周上传一次 |
| **每天一个文件夹** | 便于按日期筛选 & 避免扫描大批量数据 | 将每天的增量数据放在 `dt=YYYY‑MM‑DD/` 中 |
| **唯一的文件名** | 防止意外覆盖 | 为文件指定类似如下的唯一名称：`events_2025‑08‑04.parquet` `events_2025‑08‑05.parquet` |
| **必填列** | 支持追踪变更 | 文件必须包含：<ul><li>一个日期列，用于将记录与报告时间范围关联。<ul><li>一个版本列，用于追踪数据修订。</li></ul></li></ul>**注意：** 缺少这些列的文件将导致 DCP 加载出错。 |

<span id="h_01K2A7MAWTV3FY1GZSXQFNX4JS"></span>**文件夹结构：**

```
s3://af-dcr-xyz/abcd1234/input/source_name/dt=2025-08-10/\n└ bucket ┘ └ tenant ┘ └ ingestion ┘ └ source ┘ └ day partition ┘
```

| 细分 | 目的 |
| --- | --- |
| `af-dcr-xyz` | 客户的 S3/GCS 存储桶 |
| `abcd1234/` | 租户或工作区 ID |
| `input/` | 等待采集的原始上传数据 |
| `source_name/` | 逻辑 DCP 数据源（例如 CRM\_Events） |
| `dt=2025-08-10/` | 按日分区的文件夹 |

<span id="h_01K2A7MAWTRSYFTTDKG4G0TPZR"></span>**每周增量文件夹结构示例：**

```
source_name/
  dt=2025-08-04/
  dt=2025-08-05/
  dt=2025-08-06/
  dt=2025-08-07/
  dt=2025-08-08/
  dt=2025-08-09/
  dt=2025-08-10/
```

<span id="h_01K2A7MAWT5NDJQAYD16NRZSAQ"></span>**经验之谈：**

| 要求 | 为什么 | 示例 |
| --- | --- | --- |
| **每周批处理（可选）** | 减少推送次数，粒度不变 | 上传一个包含七个同级 `dt=` 文件夹的批次 |
| **按日分区** | 加快查询 & UI 筛选速度 | `s3://your‑bucket/source/ dt=2025‑08‑04/ ... dt=2025‑08‑10/` |

**关键结论：** 即使按周上传，也始终要按天将数据放到特定的 `dt=YYYY‑MM‑DD` 文件夹中。

</Accordion>

<Accordion title="步骤 5：映射数据源字段">

将数据源字段映射到 DCP 字段、进行测试并保存已配置的数据：

1. [加载数据源字段](#1-加载您的数据源字段)
2. [配置数据源字段](#2-配置数据源字段)
3. [验证是否包含欧盟用户](#3-验证是否包含欧盟用户)
4. [测试源数据](#4-测试源数据)
5. [保存数据源](#5-保存数据源)

<div id="1-load-your-source-fields" />

#### 1. 加载您的数据源字段

数据源字段会自动加载。如果需要手动加载，请根据数据源位置按照以下说明操作：

**数据仓库中的数据源**

如需加载位于数据仓库（BigQuery 或 Snowflake）中的数据源字段，请点击 **从数据源加载字段**。

<div id="important-3" />

> 🚧 **重要性**
>
> 如果所选源表不包含必需的[日期列和版本列](#table-columns)，您将收到错误提醒。

**云端存储桶中的数据源**

如需加载位于云端存储桶（Amazon S3 或 GCS）中的数据源字段，您必须上传一个数据源文件样本。

如需将数据源字段映射到 DCP 字段：

* 您可以上传本地的数据源文件样本。
  * 如果您选择此选项，AppsFlyer 将始终自动创建数据源文件夹路径。

                                                                - 或 -

* 您可以直接从已连接的云存储桶上传数据源文件样本。
  * 如果您选择此选项，还需要做出另外一项选择：
    * 允许 AppsFlyer 自动为数据源文件生成云文件夹；或
    * [手动为数据源文件创建云文件夹](#h_01HPKB2ERVZ88MJ35JC66YDPAB)

**如需上传您的样本数据源文件，请按照下方相应标签页中的说明操作：**

<Tabs>
<Tab title="采集区">

1. 在**映射数据源字段**部分，点击**从数据源加载字段**。
2. <span id="h_01K2A7MAWT86J2S65D99BC66PQ"></span>2. **上传追加（增量）文件**
3. 指定您要上传的 CSV 或 GZIP 文件，然后点击“OK”。

</Tab>

<Tab title="连接（自动创建）">

**若要从已连接的云存储桶加载文件，并由 AppsFlyer 自动生成源文件所需的云端文件夹：**

1. 在**映射数据源字段**部分，点击**从数据源加载字段**。
2. 在打开的窗口中，选择**从云存储桶加载。**
3. 点击**生成文件夹链接。**
   * AppsFlyer 会自动生成所需的文件夹结构和云端数据源文件夹（创建位置为你指定的连接，名称为你指定的数据源文件夹名称）。
4. 数据源文件夹结构创建完成后，界面会显示一条确认消息，其中包含一个指向该数据源文件夹的链接。点击该链接，将你的样例文件上传到数据源文件夹中。
5. 文件上传完成后，点击 **OK。**

</Tab>

<Tab title="连接（手动创建）">

**若要从你手动创建的文件夹结构中上传源文件：**

1. 在**配置数据源结构区域**，点击**从数据源加载字段**。
2. 在打开的窗口中，选择**从云存储桶加载。**
3. **请勿** 点击**生成文件夹。** 应直接将文件上传到[你为该数据源手动创建的数据源文件夹](#manually-creating-a-folder-structure)中。
4. 文件上传完成后，点击 **OK**。

</Tab>
</Tabs>

<div id="2-configure-the-source-fields" />

#### 2. 配置数据源字段

加载数据源字段后，每个数据源字段（列）都会显示一个 DCP 字段与之对应。检查每个数据源字段，并从旁边的下拉列表中将其映射到相应的 DCP 字段。注意事项：

<div id="note-1" />

> 📘 **备注**
>
> * 当双方共享各自的源数据时，**必须至少将一个字段设为标识符**，这样才能在相应数据源之间匹配用户层级数据。标识符是可唯一标识用户的字段（例如 CUID、AppsFlyer ID 或加密 email）。
> * 虽然无需配置每个已上传的数据源字段（列），但这对分类、有效解读数据、协助创建受众、提供洞察，以及高效促进验证都很重要。

<div id="ai-assisted-field-type-detection" />

#### AI 辅助字段类型检测

DCP 可以基于列名，使用 AI 为每个数据源列建议一个 DCP 字段。

**如需启用 AI 辅助检测：**

1. 在 **映射数据源字段**部分中，找到以下横幅：“想快速获得字段映射帮助？**启用 DCP AI 助手**。」点击 **启用 DCP AI 助手**。
2. 字段加载完成后，点击 **自动检测字段类型**。 DCP 会评估每个列名，并为其建议一个 DCP 字段。
3. 保存前，请检查每一项建议。您可以直接接受建议，也可以像编辑其他字段一样手动更改映射。

每个字段都会处于以下某一种状态：

* **已映射：** AI 找到了一个可信的唯一匹配项。请检查后接受，或手动更改。
* **无法映射：** AI 无法确定字段。手动映射，或保留为未映射。

<div id="limitations" />

#### 局限性

* **列数限制：** AI 检测每个数据源最多支持 100 列。列数更多的数据源会显示“超出限制”信息。
* #configure-the-source-fields

<div id="important-4" />

> 🚧 **重要！**
>
> 如果某个数据源包含任何映射到 **列表...** 类型（标识符列表、数值列表或文本列表）的字段，则必须以 Parquet 格式上传或连接数据源文件。 CSV 和 GZ 文件不支持数组类型的列，因此可能无法从这些格式中正确摄取列表字段。

**如需移除字段：**

* 将鼠标悬停在要移除的字段右侧，然后点击悬停时显示的垃圾桶图标。

**如需手动添加字段：**

使用此选项，您可以在受众中加入数据源当前不存在的字段。

1. 点击 **+ New field**。系统会添加一个空字段。
2. 输入字段名称并选择其类型。

<Image align="center" alt="NewField.png" src="https://files.readme.io/8dfb70dcac2cc9a2257c6e092bc2185de74a3804bd608878eaaadf09cd903331-43749881081745.png" width="760px" />

**字段类型包括：**

* [**标识符**](#标识符与标识符列表)
  * Android ID
  * AppsFlyer ID
  * CUID
  * 邮件
  * 加密 email
  * 加密 email（无点号）
  * IDFA
  * IP 地址
  * ID5 ID
  * MediaMath Id
  * 移动广告 Id
  * 电话号码
  * 哈希处理后的电话号码（不含加号）
  * 平台 ID
  * SHA256 哈希处理的 ID
  * SHA256 电话号码
  * ZIP+5 邮编
  * ZIP+4 邮编
  * LUID
  * 个人 ID
* [**标识符列表**](#标识符与标识符列表)
  * 加密后的 email（不含点号）
  * 加密后的电话号码（不含加号）
  * 加密后的 email
  * 加密后的电话号码
  * 电子邮件
  * 电话
  * ID5 ID
  * MediaMath Id
  * 移动广告 Id
  * IDFA
  * Android ID
  * IP 地址列表
* 布尔值
* 日期和时间
  * 日期时间
  * 日期
* DMA
  * 已启用广告个性化
  * 已启用广告用户数据
  * 适用欧盟 DMA
* 数值
  * 双精度浮点数
  * 数值列表
  * 长整型
  * 数值
* 文本
  * 文本
  * App ID
  * 文本列表

<div id="identifier-vs-list-of-identifiers" />

#### **标识符与标识符列表：**

标识符类型每行仅包含一个值（例如，每行一个 email 或一个 CUID）。标识符列表类型每行包含一个值数组（例如，单行可包含多个哈希处理后的 email 或设备 ID）——当某个数据源需要针对每条记录中的多个标识符进行匹配时，请使用此类型。

<div id="important-5" />

> 🚧 **重要提示！**
>
> 如果某个数据源包含任何映射到 **列表...** 类型（标识符列表、数值列表或文本列表）的字段，则必须以 Parquet 格式上传或连接数据源文件。 CSV 和 GZ 文件不支持数组类型的列，因此可能无法从这些格式中正确摄取列表字段。

<div id="reload-source-fields" />

#### 重新加载数据源字段

如果您的某个数据文件配置已发生变化，您可以更新数据源文件以反映这些更改。

<div id="note-2" />

> 📘 **备注**
>
> 重新加载数据源会将数据源中的列名重置为与更新后的文件名一致。这会覆盖列表中的所有字段名称及其类型。

**如需从文件重新加载已更新的字段：**

1. 点击**重新加载字段**。
2. 选择文件位置。
   * 对于本地文件：上传文件。
   * 对于来自您的云服务的文件：点击**从云存储桶加载**，然后按照说明操作。
3. 点击 **OK**。现在将显示更新后的文件。

<div id="3-verify-eu-user-inclusion" />

#### 3. 验证是否包含欧盟用户

* 对于以下问题，选择**是** 或 **否**：**您的数据源是否包含受欧盟 DMA 法规约束的欧洲用户？**

详细了解欧盟《数字市场法案》相关的隐私法规。

<div id="4-test-the-source-data" />

#### 4. 测试源数据

* 【可选】点击**测试**，检查数据源字段的格式或有效性是否存在错误。

<div id="5-save-the-source" />

#### 5. 保存数据源

* 点击**保存**，保存该数据源。

确认后，新数据源会添加到**数据源**标签页下。

<div id="note-3" />

> 📘 **备注**
>
> 如果您从本地文件上传了数据源，保存数据源会自动创建文件夹结构，且显示的确认信息中包含指向源文件夹的链接。

</Accordion>

<div id="manage-your-sources" />

## 管理您的数据源

您创建的数据源会显示在**数据源**标签页中。在这里，您可以编辑数据源名称和结构，与协作者共享，并在其尚未用于任何受众的情况下将其删除。

<Accordion title="编辑数据源">

1. 前往**数据净室**的**数据源**选项卡。
2. 在数据源列表中，将鼠标悬停在您要编辑的数据源上，然后点击该行末尾的编辑图标 ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png)。
3. 在**编辑数据源**页面中，按如下所述编辑相关字段。
4. 点击**保存**。

<div id="edit-the-source-name" />

#### 编辑数据源名称

编辑数据源名称时，请确保[遵循这些命名要求](#要求和指南)。

<div id="edit-the-source-location" />

#### 编辑数据源位置

1. 在**编辑数据源**页面 > 数据源**位置**中，选择其他数据连接。
2. 选择相关的位置详细信息。
3. [可选] [测试](#4-测试源数据)数据源。
4. 点击**保存**。

<div id="edit-the-field-mapping" />

#### 编辑字段映射

1. 前往字段映射并进行必要的更改：更改字段，或更新其映射的 DCP 字段。
2. 点击**保存**。

<div id="important-6" />

> 🚧 **重要性**
>
> 更新数据源结构后，请务必对使用该数据源的报告做出相应的更改：
>
> * 已移除、已取消映射或与之前映射关系不同的字段，会自动从使用这些字段的所有报告中移除。
> * 新添加或新映射的字段不会自动包含在现有报告中，直到您编辑报告定义并将其纳入其中。

</Accordion>

<Accordion title="删除数据源">

除非某个数据源正在受众中使用，否则您可以删除任何数据源。如果属于这种情况，系统会通过通知说明哪些受众正在使用该数据源。如需删除该数据源，您必须先删除与其关联的受众。至于与您共享的数据源，则只能由数据源所有者删除。

1. 前往**数据净室**的**数据源**选项卡。
2. 在数据源列表中，将鼠标悬停在要删除的数据源所在行上。
3. 点击该行右侧显示的删除图标 ![delete_button.png](https://files.readme.io/10fbd4d4f09ddb56823a2824629f8bb9362b34c95038b3d9e747ffcde7b30381-24740010666129.png)。
4. 在对话框中，点击 **Delete** 以确认。

</Accordion>

<div id="sharing-permissions" />

## 共享权限

在<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-a-collaboration">创建协作</Anchor>时，您可以授予协作者查看和使用您的数据源数据的权限。了解更多关于<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-sharing-permissions">共享权限</Anchor>的信息。

<div id="additional-information" />

## 更多信息

本部分提供一些补充参考资料和实用信息。

<Accordion title="手动创建存储桶文件夹结构（可选）">

一般情况下，最简便的方法是让 AppsFlyer 在创建数据源过程中自动生成所需的文件夹结构。不过，如果您希望手动创建这些文件夹，可以按以下说明操作。

<div id="create-a-dcr-key-folder" />

#### 创建 DCR 密钥文件夹

为确保最高安全性，存储桶正下方的文件夹（即“DCR 密钥文件夹”）必须使用分配给您账户的 8 位字母数字 **DCR 密钥** 命名（例如 `01bcc5fb`）。*请注意，这与您的 AppsFlyer 账户关联的任何其他密码或密钥不同。*

DCR 密钥文件夹通常需要通过您所选云服务的界面手动创建。

**获取您账户的 DCR 密钥：**

* 点击右上角的 3 点（操作）菜单，然后选择 **DCR key**。

[<Image align="center" alt="DCR key.png" src="https://files.readme.io/b892831ad68cffb5b8084949d759f402780536c7176aa27733c867aff6560684-43750165616657.png" width="1141px" />](https://support.appsflyer.com/hc/article_attachments/50255899579281)

创建 DCR 密钥文件夹后，您的存储桶/文件夹结构大致如下：

<Image align="center" alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png" width="308px" />

<div id="top-level-input-folder" />

#### 顶层输入文件夹

虽然这不是必需项，但最佳实践是直接在 DCR 密钥文件夹下创建一个顶层输入文件夹。此文件夹专用于您上传到 DCR 的文件。

顶层输入文件夹通常需要通过您所选云服务的界面手动创建。

* 如果您使用同一个存储桶既上传数据文件（输入）又接收报告（输出），则更推荐采用这种做法。
* 您可以用任意名称为该文件夹命名，只要符合 <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR 命名要求</Anchor>即可。为了便于识别，通常会将其命名为 `input/`。

创建顶层输入文件夹后，您的存储桶/文件夹结构可能如下所示：

<Image align="center" alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png" width="308px" />

<div id="second-level-folder-for-each-data-source" />

#### 各数据源的第二层级文件夹

您可以定期将不同数据源的文件上传到 DCR 进行处理。必须为每个数据源分配一个单独的文件夹（「数据源文件夹」）。

例如，如果您计划每天向 DCR 上传 2 个文件进行处理： *BI-data.csv* 和 *CRM-data.gzip*，则需要为这些数据源分别分配一个文件夹。您可以将这些文件夹命名为 `BI-data/` 和 `CRM-data/`。

数据源文件夹通常需要通过您所选云服务的界面手动创建。

创建这 2 个数据源文件夹后，您的存储桶/文件夹结构可能如下：

<Image align="center" alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png" width="307px" />

每次数据源更新时，都必须在各个数据源文件夹下创建[按日期和版本划分的嵌套子文件夹](#nested-subfolders-for-each-date-and-version)。

</Accordion>

<div id="privacy-regulations" />

## 隐私规定

本节概述与当前隐私规定相关的重要信息。

<Accordion title="了解 Google 的欧盟用户同意政策及其影响">

作为 Google 执行《数字市场法案》（DMA）的一部分，Google 已于 2024 年 3 月 6 日更新其欧盟用户同意政策。作为 Google 的应用归因合作伙伴，AppsFlyer 已做出必要调整，以支持其政策要求，同时确保广告主能够充分发挥 Google Ads 营销渠道的价值。

<div id="note-4" />

> 📘 **备注**
>
> * Google 对《数字市场法案》（DMA）的执行适用于所有平台。
> * 了解更多：
>   * <Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">关于《数字市场法案》的洞察与资源</Anchor>
>   * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">Google 常见问题解答</Anchor>

<div id="adding-consent-fields" />

#### 添加同意字段

在设置用于在 Google 上进行受众激活的数据源时，若您对问题“**您的数据源是否涉及受欧盟 DMA 法规约束的欧洲用户？**”选择**是**请确保下表中的附加同意字段已包含在源文件中。这样，AppsFlyer 就能在激活过程中将必要信息传输给 Google。

**附加同意字段及其响应值：**

<table><thead><tr><th>字段名称</th><th>响应值</th><th>字段用途</th></tr></thead><tbody><tr><td><span id="eea"></span><code>eea</code></td><td>真/假</td><td>该用户是否位于 DMA 适用的 EEA（欧洲经济区）？</td></tr><tr><td><span id="ad_personalization"></span><code>ad_personalization</code></td><td>\*真/假</td><td>用户是否已同意 Google 将其数据用于个性化广告？</td></tr><tr><td><span id="ad_user_data"></span><code>ad_user_data</code></td><td>\*真/假</td><td>用户是否已同意将其用户数据发送给 Google？ </td></tr><tr><td colspan="3"><span id="when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them"></span>\* 当为「<strong>true</strong>」时，AppsFlyer 会包含您为已给予同意的用户发送的用户标识符。<br/>   当为「<strong>false</strong>」时：AppsFlyer 不会包含这些标识符，因为它们未发送到 AppsFlyer。</td></tr></tbody></table>

<div id="potential-impact-on-the-audience-size" />

#### 对受众规模的潜在影响

发送到 Google 的实际和预估受众规模可能会因同意或拒绝的用户数量而有所不同。

</Accordion>

<div data-zendesk-anchors="introduction=%E5%85%B3%E4%BA%8E-dcp-%E6%95%B0%E6%8D%AE%E6%BA%90 h_01HPKB2ERNRQG73AFA0X7XEDEF=%E5%85%B3%E4%BA%8E-dcp-%E6%95%B0%E6%8D%AE%E6%BA%90 source-format=%E6%95%B0%E6%8D%AE%E6%BA%90%E8%A6%81%E6%B1%82 h_01HPKB2ERPANE0CAXFP9RG5YEH=%E6%95%B0%E6%8D%AE%E6%BA%90%E8%A6%81%E6%B1%82 creating-a-source=%E5%88%9B%E5%BB%BA%E6%95%B0%E6%8D%AE%E6%BA%90 h_01HPKB2ERPX2T413N3T93YBBZB=%E5%88%9B%E5%BB%BA%E6%95%B0%E6%8D%AE%E6%BA%90 requirements-and-guidelines=%E8%A6%81%E6%B1%82%E5%92%8C%E6%8C%87%E5%8D%97 h_01K1ZHNZEQ3NSN3V7NQ34G8VC8=%E8%A6%81%E6%B1%82%E5%92%8C%E6%8C%87%E5%8D%97 source-locations-in-bigquery=bigquery-%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE 01HX49VY7D8KG5DCB82BP69BXV=bigquery-%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE source-locations-in-snowflake=snowflake-%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE 01HX49VY7DXH5YN8FF0NFAJBC2=snowflake-%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE source-locations-in-cloud-storage-buckets=%E4%BA%91%E5%AD%98%E5%82%A8%E6%A1%B6%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE 01HX49VY7D3CSF4SQ79Q7CZKWX=%E4%BA%91%E5%AD%98%E5%82%A8%E6%A1%B6%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE 01HX49VY7D307DT5VTMGHPF3WA=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA local-file-system=%E6%9C%AC%E5%9C%B0%E6%96%87%E4%BB%B6%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE h_01HX4SKEGE9NVCA6VYSR77S2DK=%E6%9C%AC%E5%9C%B0%E6%96%87%E4%BB%B6%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE h_01K1FW3AW2AW4TPDS0ZGPQCMX3=%E6%9C%AC%E5%9C%B0%E6%96%87%E4%BB%B6%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE h_01HX4T0H6SFQJEWFETKFD1CY6S=%E5%A4%87%E6%B3%A8 h_01K29ETW94GQM9YYF5A4Y6DKB6=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 overwrite-method-specifications=snapshot-%E4%B8%8A%E4%BC%A0%E8%A6%81%E6%B1%82 snapshot-upload-requirements=snapshot-%E4%B8%8A%E4%BC%A0%E8%A6%81%E6%B1%82 h_01K1G33RX95KP9TJ4002DDJBCE=snapshot-%E4%B8%8A%E4%BC%A0%E8%A6%81%E6%B1%82 h_01K2A7MAWS5KR16QV0Y8AE39GW=snapshot-%E4%B8%8A%E4%BC%A0%E8%A6%81%E6%B1%82 h_01K2A7MAWTCYF3VAWJRRRJFNN5=snapshot-%E4%B8%8A%E4%BC%A0%E8%A6%81%E6%B1%82 h_01K2CC62XGAVTD5JH5DYXP0947=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2 data-title=append-%E4%B8%8A%E4%BC%A0%E8%A6%81%E6%B1%82 append-delta-upload-requirements=append-%E4%B8%8A%E4%BC%A0%E8%A6%81%E6%B1%82 h_01K2A7MAWT7CRHY1TV5J41MM0D=append-%E4%B8%8A%E4%BC%A0%E8%A6%81%E6%B1%82 h_01K2C6QNJSAH9D3M48T02JHQ3R=append-%E4%B8%8A%E4%BC%A0%E8%A6%81%E6%B1%82 load-the-source-fields=1-%E5%8A%A0%E8%BD%BD%E6%82%A8%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E5%AD%97%E6%AE%B5 h_01HPKB2ERQTJPGG68FSEBHVVJA=1-%E5%8A%A0%E8%BD%BD%E6%82%A8%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90%E5%AD%97%E6%AE%B5 h_01HPKB2ERRZNPYVVD8GHD7PBPE=%E9%87%8D%E8%A6%81%E6%80%A7 configure-the-source-fields=2-%E9%85%8D%E7%BD%AE%E6%95%B0%E6%8D%AE%E6%BA%90%E5%AD%97%E6%AE%B5 h_01HX64YHGHMK352E3RXHBFV0B5=2-%E9%85%8D%E7%BD%AE%E6%95%B0%E6%8D%AE%E6%BA%90%E5%AD%97%E6%AE%B5 01HX6HVZ6DK2WH71JVB0J9WPBF=%E5%A4%87%E6%B3%A8-1 h_01K5AI0D3TFIELDTYPEDETECT=ai-%E8%BE%85%E5%8A%A9%E5%AD%97%E6%AE%B5%E7%B1%BB%E5%9E%8B%E6%A3%80%E6%B5%8B ai-assisted-field-type-detection=ai-%E8%BE%85%E5%8A%A9%E5%AD%97%E6%AE%B5%E7%B1%BB%E5%9E%8B%E6%A3%80%E6%B5%8B h_01K5AI0D3TLIMITATIONS=%E5%B1%80%E9%99%90%E6%80%A7 limitations=%E5%B1%80%E9%99%90%E6%80%A7 h_01K5AI0D3TIMPORTANT=%E9%87%8D%E8%A6%81 identifier-vs-list-of-identifiers=%E6%A0%87%E8%AF%86%E7%AC%A6%E4%B8%8E%E6%A0%87%E8%AF%86%E7%AC%A6%E5%88%97%E8%A1%A8 h_01KYSMJKRA2E13PH2QS671BSKG=%E6%A0%87%E8%AF%86%E7%AC%A6%E4%B8%8E%E6%A0%87%E8%AF%86%E7%AC%A6%E5%88%97%E8%A1%A8 h_01KYSJNEWS5QY5Q13Z11TNJHX1=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-3 reload-source-fields=%E9%87%8D%E6%96%B0%E5%8A%A0%E8%BD%BD%E6%95%B0%E6%8D%AE%E6%BA%90%E5%AD%97%E6%AE%B5 h_01HX6TDNEMJFQM5FA95Y3C1QHD=%E9%87%8D%E6%96%B0%E5%8A%A0%E8%BD%BD%E6%95%B0%E6%8D%AE%E6%BA%90%E5%AD%97%E6%AE%B5 h_01HX6WF7YC014Z7ZX359RB5ZRZ=%E5%A4%87%E6%B3%A8-2 verify-eu-user-inclusion=3-%E9%AA%8C%E8%AF%81%E6%98%AF%E5%90%A6%E5%8C%85%E5%90%AB%E6%AC%A7%E7%9B%9F%E7%94%A8%E6%88%B7 01HZKZ2T33TYCQ8J59YGDYN7DK=3-%E9%AA%8C%E8%AF%81%E6%98%AF%E5%90%A6%E5%8C%85%E5%90%AB%E6%AC%A7%E7%9B%9F%E7%94%A8%E6%88%B7 test-the-source-data=4-%E6%B5%8B%E8%AF%95%E6%BA%90%E6%95%B0%E6%8D%AE h_01HX6WGD421PCWEWTN5YJ7V42H=4-%E6%B5%8B%E8%AF%95%E6%BA%90%E6%95%B0%E6%8D%AE save-the-source=5-%E4%BF%9D%E5%AD%98%E6%95%B0%E6%8D%AE%E6%BA%90 h_01HYX92EXSJNM5B2PDXEAEBNFS=5-%E4%BF%9D%E5%AD%98%E6%95%B0%E6%8D%AE%E6%BA%90 h_01HYXC06K3ZWQE867NKBT95RFH=%E5%A4%87%E6%B3%A8-3 working-with-existing-sources=%E7%AE%A1%E7%90%86%E6%82%A8%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90 h_01HPKB2ERS5PK2P2XTC4ZMPCMC=%E7%AE%A1%E7%90%86%E6%82%A8%E7%9A%84%E6%95%B0%E6%8D%AE%E6%BA%90 edit-the-source-name=%E7%BC%96%E8%BE%91%E6%95%B0%E6%8D%AE%E6%BA%90%E5%90%8D%E7%A7%B0 01J1SMACQHFEVAR8ZC6W8T0BAV=%E7%BC%96%E8%BE%91%E6%95%B0%E6%8D%AE%E6%BA%90%E5%90%8D%E7%A7%B0 edit-the-source-location=%E7%BC%96%E8%BE%91%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE h_01J1SM789AFJBSD0NG826P98Q4=%E7%BC%96%E8%BE%91%E6%95%B0%E6%8D%AE%E6%BA%90%E4%BD%8D%E7%BD%AE edit-the-source-structure=%E7%BC%96%E8%BE%91%E5%AD%97%E6%AE%B5%E6%98%A0%E5%B0%84 h_01J1SNB66WQMBV1GQE4PDQ0NW4=%E7%BC%96%E8%BE%91%E5%AD%97%E6%AE%B5%E6%98%A0%E5%B0%84 h_01HPKB2ERTYP6BFAESN3MHZSQG=%E9%87%8D%E8%A6%81%E6%80%A7-1 permissions=%E5%85%B1%E4%BA%AB%E6%9D%83%E9%99%90 h_01HZHBDPZ8FFQCB9DZ2Q8XSC2R=%E5%85%B1%E4%BA%AB%E6%9D%83%E9%99%90 reference=%E6%9B%B4%E5%A4%9A%E4%BF%A1%E6%81%AF h_01HPKB2ERV1KK3J8YX918GCF3M=%E6%9B%B4%E5%A4%9A%E4%BF%A1%E6%81%AF creating-a-dcr-key-folder=%E5%88%9B%E5%BB%BA-dcr-%E5%AF%86%E9%92%A5%E6%96%87%E4%BB%B6%E5%A4%B9 h_01HPKB2ERV7MQJ9CK44T92GK2G=%E5%88%9B%E5%BB%BA-dcr-%E5%AF%86%E9%92%A5%E6%96%87%E4%BB%B6%E5%A4%B9 toplevel-input-folder=%E9%A1%B6%E5%B1%82%E8%BE%93%E5%85%A5%E6%96%87%E4%BB%B6%E5%A4%B9 h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=%E9%A1%B6%E5%B1%82%E8%BE%93%E5%85%A5%E6%96%87%E4%BB%B6%E5%A4%B9 secondlevel-folder-for-each-data-source=%E5%90%84%E6%95%B0%E6%8D%AE%E6%BA%90%E7%9A%84%E7%AC%AC%E4%BA%8C%E5%B1%82%E7%BA%A7%E6%96%87%E4%BB%B6%E5%A4%B9 h_01HPKB2ERVVFMP81RE8ATZ6SZ8=%E5%90%84%E6%95%B0%E6%8D%AE%E6%BA%90%E7%9A%84%E7%AC%AC%E4%BA%8C%E5%B1%82%E7%BA%A7%E6%96%87%E4%BB%B6%E5%A4%B9 privacy-regulations-eu-digital-markets-act=%E9%9A%90%E7%A7%81%E8%A7%84%E5%AE%9A h_01HZHBF0NZDTXAA3MY1A0BPE5E=%E9%9A%90%E7%A7%81%E8%A7%84%E5%AE%9A h_01HZM4EFRJD483NARKDPPPPXCY=%E5%A4%87%E6%B3%A8-4 adding-consent-fields=%E6%B7%BB%E5%8A%A0%E5%90%8C%E6%84%8F%E5%AD%97%E6%AE%B5 h_01HZHBF0NZSDGDYG2ZWNW4KQYD=%E6%B7%BB%E5%8A%A0%E5%90%8C%E6%84%8F%E5%AD%97%E6%AE%B5 -when-%E2%80%9Ctrue%E2%80%9D-appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google%C2%A0-when-%E2%80%9Cfalse%E2%80%9D-appsflyer-abstains-from-sending-them=when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them potential-impact-on-the-audience-size=%E5%AF%B9%E5%8F%97%E4%BC%97%E8%A7%84%E6%A8%A1%E7%9A%84%E6%BD%9C%E5%9C%A8%E5%BD%B1%E5%93%8D h_01HZHBF0NZJBSXNBDFZH4YKNSH=%E5%AF%B9%E5%8F%97%E4%BC%97%E8%A7%84%E6%A8%A1%E7%9A%84%E6%BD%9C%E5%9C%A8%E5%BD%B1%E5%93%8D" />

---
title: 数据协作平台 (DCP) - 准备用于摄取的数据源
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2026-01-26T12:08:32Z'
  edited_at: '2026-10-14T10:00:39Z'
  id: 43205325114897
  locale: zh-cn
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/zh-cn/articles/43205325114897
---
> **概览：** 准备您的数据源，以最大程度地提高协作方数据集之间的匹配率，并优化协作成果。

<div id="about-data-preparation" />

## 关于数据准备

AppsFlyer <Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-guide">数据协作平台 (DCP)</Anchor> 旨在摄取和处理来自多个协作方的大规模交易数据、用户级数据或两者的组合。摄取后，DCP 可以使用共享标识符（例如，哈希电子邮件或哈希电话）跨数据集匹配用户，并基于该数据启用协作工作流。

本文概述了：

* DCP 可以处理的数据类型（交易数据、用户级数据或两者的组合）
* 如何构建数据以最大程度地提高协作方之间的匹配率，以及如何实现激活合作伙伴的最佳匹配
* 推荐使用哪些数据结构，不推荐使用哪些数据结构
* 使用 CSV 文件时如何处理多值标识符

<div id="understand-data-types" />

## 了解数据类型

协作中使用的大多数数据源涉及以下一种或两种数据类型：

* **用户级（身份）数据**
  * 目标代表每个用户以及用于匹配的标识符
  * **推荐结构：** 每个用户一行
* **交易（事件）数据**
  * 目标代表用户操作（购买、访问、交易）
  * **典型结构：** 每个用户多行（因为一个用户可以有多次交易）

<div id="data-structuring-guidelines" />

## 数据结构指南

本节概述了 DCP 数据结构指南和最佳实践。

<div id="workflow-and-structuring-guidelines" />

<Accordion title="推荐的数据结构">

**为了构建您的源数据以实现 DCP 中的最佳摄取和最大化成果：**

1. 确保其<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-and-manage-sources#数据源要求">符合源数据格式要求</Anchor>。
2. 为获得最佳结果，<strong>请将身份数据结构化为每个用户一行，并包含该用户的所有可用标识符。</strong>请参阅[推荐的标识符结构](#推荐的标识符结构)。
   * 如果用户有多个电子邮件地址或电话号码，请使用基于数组的格式（例如 Parquet、BigQuery 或 Snowflake）。
3. 检查是否遵循了[哈希指南](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-e-hashed-data-formatting-guidelines-by-media-partner)。
4. 对于交易数据集（以及其他适用的数据类型），请**使用 DCP 数据视图工具**创建一个面向业务、保护隐私的数据子集，以优化协作，并共享该子集而非原始表。[为什么推荐使用数据视图](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-c-why-dataviews-matter-and-recommended)。

虽然可以使用其他结构，但它们可能并不适合充分利用 DCP。请参阅[不推荐的数据结构](#data-structures-that-arent-recommended)。

<div id="recommended-identifier-structures" />

#### 推荐的标识符结构

为了最大化匹配率，建议尽可能以每个用户一行的方式发送用户级身份数据，并以准确反映用户表示方式的结构包含所有可用标识符。

**Option 1:每个用户一行，每种标识符类型一个值**

**简单且有效。**

当每个用户最多拥有一个哈希电子邮件地址、一个哈希电话号码等时，请使用此结构。

**示例**

| User ID | `{hashed_emails}` | 哈希电话号码 |
| --- | --- | --- |
| 123 | 5d41402 | 152d234b70 |
| 456 | 7d793037 |  |
| 789 |  | 0e6e5414 |

**为什么推荐此结构**

* 最易于准备和摄取
* 易于验证和排查故障
* 当标识符完整且一致时，匹配性能强（适用于与协作者数据集匹配以及激活媒体合作伙伴匹配）

**最适合**

* 非常适合基于 CSV 的上传
* 在 Parquet / BigQuery / Snowflake 中也表现良好

**Option 2:用于多值字段的标识符数组（列表）**

**当用户拥有多个电子邮件和电话号码时，此方式的准确性最高。**

当用户可以拥有多个相同类型的标识符时，请使用此方式，例如：

* 多个哈希电子邮件
* 多个哈希电话号码

此结构应表示为 **原生数组**。

**示例**

| User ID | `{hashed_emails}` | 哈希电话号码 | 移动设备广告标识符 (MAID) |
| --- | --- | --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] | [p1q2 · r3s4] | m001 |
| u\_0002 | [z9y8 · x7w6] |  | m002 |
| u\_0003 |  | [t1u2 · v3w4 · x5y6] |  |

**为何首选此方式**

* 反映了身份数据在内部的常见存储方式
* 无需猜测需要多少个“电子邮件列”
* 避免持续的架构变更
* 通过允许每个用户拥有多个标识符，最大限度地提高匹配潜力（适用于协作者数据集和激活媒体合作伙伴匹配）

**最适合**

* Parquet (S3/GCS)
* BigQuery
* Snowflake

</Accordion>

<div id="practical-checklist-for-dcp-collaborators" />

<Accordion title="数据结构化实用清单">

<div id="identity-user-level-dataset-checklist" />

#### 身份（用户级）数据集清单

* 一行代表一个用户。
* 包含所有可用的标识符（哈希电子邮件、哈希电话、MAID 等）。
* 如果存在多个值（例如，多个电子邮件），请尽可能使用原生数组。
* 避免在单元格中使用列表，避免“email\_1/email\_2/email\_3”，并避免多行身份结构。

<div id="transactional-events-dataset-checklist" />

#### 事务（事件）数据集清单

* 保持事件/事务行原样。请参阅 [事务数据示例](#appendix-a-transactional-data-examples)
* 在适当的情况下，使用 [数据视图](#appendix-c-why-dataviews-matter-and-recommended) 创建可供协作的用户级摘要。

<div id="data-views-checklist" />

#### 数据视图清单

* 构建面向业务的 [数据视图](#appendix-c-why-dataviews-matter-and-recommended)（即：可供受众使用、已汇总、已标准化）。
* 尽可能共享数据视图，而非原始敏感表。
* 将共享字段最小化至仅需内容（出于隐私和业务保护考虑）。
* 考虑使用聚合来减少对敏感数据的访问并提高效率。

</Accordion>

<div id="supported-ingestion-cloud-services-and-formats" />

<Accordion title="支持的摄取云服务和格式">

DCP 支持通过多种云服务进行摄取，例如：

* AWS S3
* Google Cloud Storage
* BigQuery
* Snowflake

<div id="format-guidance" />

#### 格式指南

* 当每个用户对于 **每种标识符类型仅有一个值**（一个电子邮件、一个电话等）时，请使用 **CSV（逗号分隔）**。
* 当用户可以拥有 **多个值** 的相同标识符类型（例如，多个哈希电子邮件）时，请优先使用 **支持数组的格式**：
  * Parquet（大数据中常见）
  * BigQuery（内置数组）
  * Snowflake（内置数组）

**补充说明：**

* “数组”仅指“值列表”。
* Parquet 以及 BigQuery/Snowflake 中的数组是标准配置，大多数数据团队都能自然地支持这一点。

请参阅 [连接器特定的示例资产（AWS S3、GCS、BigQuery、Snowflake）。](#appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake)

<div id="data-structures-that-arent-recommended" />

<Accordion title="不建议使用的数据结构">

某些类型的数据结构非常适合摄取到 DCP 中，而另一些则不然。以下是不建议使用的数据结构列表 ：

<div id="avoid-multiple-columns-for-the-same-identifier-type" />

#### 避免：针对同一标识符类型使用多个列

不建议使用“主要/次要/第三电子邮件”之类的示例。

**避免使用的示例**

| User ID | 电子邮件（哈希加密） | 电子邮件（哈希加密） | 电子邮件（哈希加密） |
| --- | --- | --- | --- |
| 123 | a1b2 | c3d4 |  |
| 456 | z9y8 |  |  |

**避免原因**

* 每个用户的数值数量不可预测
* 导致列激增和架构维护问题

<div id="avoid-lists-inside-a-single-cell-free-text" />

#### 避免：“单个单元格内的列表”（自由文本）

即使看起来很方便，也容易出错。

**避免使用的示例**

| User ID | 哈希电子邮件（文本） |
| --- | --- |
| 123 | a1b2 · c3d4 · e5f6 |

**避免原因**

* 并非真正的数组类型
* 格式/转义问题很常见
* 细微的不一致可能会导致摄取中断

<div id="avoid-multiple-rows-per-user-for-identifiers-when-your-goal-is-a-user-identity-table" />

#### 避免：标识符的每个用户多行（当您的目标是用户身份表时）

当您可以保持每个用户一行时，不要跨行拆分身份数据。

**避免使用的示例**

| User ID | 标识符类型 | 标识符值 |
| --- | --- | --- |
| 123 | hashed\_email | a1b2 |
| 123 | hashed\_email | c3d4 |

**避免原因**

* 需要额外处理来重建用户
* 重复和不一致的风险更高
* 在大规模下效率较低

**注意：** 对于事务表，每个用户有多行是正常的，但对于用于匹配的身份（用户级）表来说，这并不理想。

</Accordion>

</Accordion>

<div id="additional-information" />

## 补充信息

本节提供有关相关主题的额外深入信息。

<div id="appendix-a-transactional-data-examples" />

<Accordion title="事务数据示例">

事务/事件数据可能每个用户有多行：

| Transaction ID | User ID | 交易日期 | 量 | 品类 |
| --- | --- | --- | --- | --- |
| t\_001 | 123 | 2025-12-01 | 120.00 | 杂货 |
| t\_002 | 123 | 2025-12-15 | 45.00 | 药店 |
| t\_003 | 456 | 1 | 300.00 | 电子产品 |

**推荐**

* 以其自然结构摄取事务数据
* 使用“数据视图”工具生成可协作的用户级视图（例如，过去30天的支出、类别偏好、最近度/频率摘要）

</Accordion>

<div id="appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake" />

<Accordion title="连接器特定的示例资产（AWS S3、GCS、BigQuery、Snowflake）">

<div id="what-does-arraylist-of-identifiers-mean" />

### “标识符数组/列表”是什么意思？

有时，单个用户可能拥有多个电子邮件或电话（例如，个人电子邮件和工作电子邮件）。我们不将其强行放入额外的列或杂乱的文本字段中，而是将其表示为值列表。

| User ID | 哈希电子邮件（列表） |
| --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] |
| u\_0002 | [z9y8 · x7w6] |

<div id="1-aws-s3-and-gcs-connector-parquet" />

### 1.AWS S3 和 GCS 连接器 (Parquet)

**身份样本应包含的内容（架构）**

| 字段 | 类型 | 备注 |
| --- | --- | --- |
| user\_id | 字符串 | 每个用户一行 |
| hashed\_emails | 字符串数组 | 多值标识符（推荐） |
| hashed\_phones | 字符串数组 | 多值标识符（推荐） |
| maid | 字符串 | 可选的附加标识符 |

Parquet 原生支持列表，这就是为什么当用户拥有多个电子邮件/电话时推荐使用它的原因。

<div id="2-bigquery-connector-table-preview-and-schema-screenshot" />

### 2. BigQuery 连接器（表预览和架构截图）

**身份架构示例 (BigQuery)**

| 字段 | 类型 | 模式 |
| --- | --- | --- |
| user\_id | 字符串 | NULLABLE（可为空） |
| hashed\_emails | 字符串 | REPEATED（数组） |
| hashed\_phones | 字符串 | REPEATED（数组） |
| maid | 字符串 | NULLABLE（可为空） |

数组在 BigQuery 中是原生的（REPEATED 字段）。当存在多个电子邮件/电话时，这是推荐的方法。

<div id="3-snowflake-connector-table-preview-and-schema-screenshot" />

### 3.Snowflake 连接器（表预览和架构截图）

**身份架构示例 (Snowflake)**

| 字段 | 类型 | 备注 |
| --- | --- | --- |
| USER\_ID | VARCHAR | 每个用户一行 |
| HASHED\_EMAILS | 排列 | 多值标识符 |
| HASHED\_PHONES | 排列 | 多值标识符 |
| 移动设备广告标识符 (MAID) | VARCHAR | 可选 |

Snowflake 支持类似列表的字段（数组）。相比创建 email\_1/email\_2/email\_3 列，这种方式更可取。

</Accordion>

<div id="appendix-c-why-dataviews-matter-and-recommended" />

<Accordion title="为什么推荐使用数据视图">

<Anchor target="_blank" href="/marketers/zh/docs/data-collaboration-platform-dcp-create-customized-data-views">数据视图</Anchor>是您现有数据源的自定义子集，您无需更改原始数据集即可创建它们。它们让您能够执行修改、优化和汇总数据的函数，以便您在协作中仅共享相关内容，从而保持共享数据的清晰和专注，并确保所有其他数据私密且安全。在协作中使用数据视图，因为它们：

<div id="are-business-oriented-and-easier-to-collaborate-with" />

#### 以业务为导向，更易于协作

* 数据视图让您能够以清晰、业务友好的结构（例如，“客户身份视图”、“合格受众视图”、“购买汇总视图”）呈现数据，而不是原始日志或复杂的事务模式。
* 它们有助于标准化定义（例如，“活跃客户”、“过去 30 天总支出”），以便双方保持一致并使用相同的逻辑。

<div id="are-more-privacy-safe-by-design" />

#### 在设计上更注重隐私安全

* 数据视图支持数据最小化：您可以仅共享协作所需的字段和行，而无需暴露完整的原始数据集。
* 它们通过允许您执行以下操作来降低隐私风险：
  * 排除不必要的属性
  * 限制粒度（例如，共享汇总指标而非行级交易）
  * 仅共享匹配所需的标识符（而非其他敏感列）

<div id="protect-sensitive-business-data" />

#### 保护敏感的业务数据

* 原始交易表可能包含高度敏感的业务信号（例如，详细的购买行为、定价模式、商户关系、内部 ID）。
* 数据视图让您仅共享协作所需的内容：
  * 示例：共享类别级汇总而非项目级详细信息
  * 示例：共享支出区间或汇总指标而非精确的行项目
* 这降低了无意中泄露竞争性或专有信息的风险。

<div id="can-make-your-data-more-cost-effective-and-performant" />

#### 可以使您的数据更具成本效益且性能更高

数据视图可以构建得更轻量、更高效，这通常会减少：

* 扫描的数据量
* 数据处理时长
* 计算成本

预先构建协作就绪视图（尤其是聚合视图）可以使协作更快，且在操作上更具可预测性。

</Accordion>

<div id="appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform" />

<Accordion title="平台的多 ID/键上传和匹配行为">

**DCP 标识符上传**

| 上的相应事件。 | 支持的标识符类型 | 上传模式 | 上传行为 | 标识符优先级（针对单一类型合作伙伴） |
| --- | --- | --- | --- | --- |
| Meta | 电子邮件、电话、IDFA、GAID、Android ID、名字、姓氏、出生日期、城市、州、邮编、国家/地区 | 所有支持的类型 | 上传所有支持的标识符类型 | 不适用 - 上传全部 |
| Google | 电子邮件、电话、IDFA、GAID、Android ID、客户 ID | 单一类型 | 每个受众上传一种标识符类型 | 1.Email 1:手机移动设备 ID 4.客户ID |
| TikTok | 电子邮件、电话、IDFA、GAID、Android ID | 所有支持的类型 | 上传所有支持的标识符类型 | 不适用 - 上传全部 |
| pinterest | 电子邮件、电话、IDFA、GAID | 单一类型 | 每个受众上传一种标识符类型 | 1.Email 1:手机移动设备ID |
| Infillion | 电子邮件、电话、IDFA、GAID、MM-UUID | 所有支持的类型 | 上传所有支持的类型，最多分为3个文件 | 不适用 - 上传全部 |
| TheTradeDesk | 邮箱地址、电话： | 单一类型 | 每个受众上传一种标识符类型 | 1.Email 1:手机 |
| AppsFlyer - Data Locker | 可用标识符： | 所有类型合并 | 在单个合并文件中交付所有标识符 | 不适用 - 交付所有内容 |

| 平台 | 您可以为每个用户发送多个ID吗？ | 他们可以匹配其中任何一个吗？ | 他们可以合并多个ID吗？ | 匹配模型（实际） | 备注 |
| --- | --- | --- | --- | --- | --- |
| Meta | 是 | 是 | 是 | 确定性，任意ID/组合 | 电子邮件、电话、MAID、fbp/fbc均经过评估；最强的“任意一个”行为 |
| Google | 是 | 受限 | 否 | 确定性，优先级排序 | 一个ID即可解析用户；ID不会合并以形成匹配 |
| TikTok | 是 | 是 | 是 | 确定性，任意ID/组合 | 与Meta非常相似；ttclid对事件非常有效 |
| pinterest | 是 | 不完整数据 | 受限 | 确定性，以ID为中心 | 主要是电子邮件+MAID；有限的跨ID增强 |
| The Trade Desk (TTD) | 是 | 通过ID图谱 | 是（通过图谱） | 通过身份图谱确定性匹配 | 通过 EUID/UID2 图谱解析的 UID2 + MAID + cookie |
| Infillion | 是 | 通过ID图谱 | 是（通过图谱） | 通过合作伙伴图谱确定性匹配 | 依赖 OmniID / 合作伙伴身份解析 |

**激活规划的要点**

* **Meta 和 TikTok**
  * 发送您拥有的所有内容
  * 真正的“任意ID”行为
  * 身份丰富型净室激活的最佳平台
* **Google**
  * 发送多个ID以实现覆盖
  * 不要指望跨ID增强效果
  * 电子邮件/电话的主导地位是真实的
* **TTD 和 Infillion**
  * 匹配质量更多地取决于身份图谱的参与度
  * UID2 / OmniID 的覆盖范围比原始标识符数量更重要
* **pinterest**
  * 表现更接近 Google 而非 Meta
  * 除电子邮件 + MAID 外，上升空间有限

**TL;DR**

* 只有 Meta 和 TikTok 原生支持“任意其一”匹配
* Google 是确定性的，但属于单ID解析
* 开放式网络平台通过身份图谱而非原始ID进行匹配

</Accordion>

<div id="appendix-e-hashed-data-formatting-guidelines-by-media-partner" />

<Accordion title="媒体合作伙伴的哈希数据格式指南">

**通用标准化规则：**  
在对任何数据进行哈希处理之前，几乎所有平台都要求执行以下标准化步骤，以确保匹配准确性：

* 文本转换为小写并去除所有前导/尾随空格。
* 手机转换为 E.164 格式（例如：+15551234567）
* 哈希SHA-256 是行业标准，尽管某些平台接受 MD5 或 SHA-1。

| 媒体合作伙伴 | 电子邮件指南 | 电话号码指南 | 移动设备ID (MAID) 指南 | 特定平台细微差别与匹配逻辑 | 相关参考 |
| --- | --- | --- | --- | --- | --- |
| Google Ads / DV360 | 格式：转换为小写，去除空格。包含域名。Gmail规则：对于 @gmail.com / @googlemail.com，请移除“@”之前的句点 (.) 以及 (+) 之后的后缀。哈希SHA-256（十六进制编码）。 | 格式：E.164（例如：+16505551212）。须包含国家代码哈希SHA-256. | 格式：IDFA (iOS) 或 GAID (Android)。哈希请勿进行哈希处理。 | 匹配优先级：确定性且已确定优先级（1.Email 1:手机移动设备 ID）。它不会组合多个 ID 来形成匹配（单 ID 解析）。DV360 PAIR:DV360 还支持用于安全发布商-广告客户对账的 PAIR 协议。 | <Anchor target="_blank" href="https://developers.google.com/google-ads/api/docs/remarketing/audience-segments/customer-match/get-started">开始使用客户匹配 (Google Ads API)</Anchor> |
| Meta (Facebook/ Instagram) | 格式：转换为小写，去除空格。哈希需要 SHA-256。<br /><br />**注意：** Meta 在进行哈希标准化时不会从电子邮件地址中删除点号。在为 Meta 进行哈希处理之前，仅应应用小写转换和去除空格。发送去除点号后的哈希电子邮件（DCP 源映射中的“哈希电子邮件（无点号）”）将无法与 Meta 自身的哈希匹配，并会导致电子邮件域用户的匹配率降低。此标识符变体旨在供需要去除点号的合作伙伴（例如 Google Ads）使用，不应将其用于 Meta/Facebook 激活。 | 格式：删除符号、字母和前导零。须包含国家代码哈希SHA-256. | 格式：IDFA 或 GAID。哈希请勿进行哈希处理。转换为小写，保留连字符。 | 匹配逻辑：使用“任一匹配”逻辑；组合多个 ID（电子邮件、电话、MAID 等）来解析用户，从而提供强大的跨 ID 增强功能。<br /><br />CAPI：需要未哈希的 client\_ip\_address 和 client\_user\_agent 以进行浏览器匹配。 | <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/conversions-api/parameters/customer-information-parameters/">客户信息参数 - Conversions API</Anchor> |
| TikTok | 格式：转换为小写，移除所有空格。哈希SHA-256. | 格式：E.164 (+[国家代码][号码])。也接受不带 + 的格式。哈希SHA-256. | 格式：GAID (Android) 或 IDFA (iOS)。大小写：全大写或全小写。哈希SHA-256 或 MD5。 | 匹配逻辑：与 Meta 类似，使用“任意匹配”确定性匹配逻辑，即任何单个有效 ID 均可。<br /><br />人群包人数需要至少 1,000 名匹配用户才能激活自定义受众。 | <Anchor target="_blank" href="https://ads.tiktok.com/help/article/how-to-create-a-custom-audience-with-a-customer-file">如何使用客户文件创建自定义受众</Anchor> |
| The Trade Desk (UID2) | 格式：与 Google 相同的“Gmail 规则”（移除点号/加号）。编码：对原始字节进行 Base64 编码（结果为 44 个字符）。 | 格式：E.164.哈希SHA-256.编码：对原始字节进行 Base64 编码。 | 格式：AAID（小写）/ IDFA（大写）。哈希SHA-256、MD5 或 SHA-1。 | 匹配逻辑：通过身份图谱进行确定性匹配。匹配取决于图谱参与度，而非原始 ID 覆盖率。<br /><br />关键细微差别：您必须对哈希的原始字节进行 Base64 编码。对十六进制字符串进行编码将会失败。 |  |
| pinterest | 格式：必须包含“@”。哈希SHA-256、MD5 或 SHA-1。 | 格式：E.164.移除特殊字符（空格、连字符）。哈希SHA-256、MD5 或 SHA-1。 | 格式：IDFA 或 GAID。哈希SHA-256、MD5 或 SHA-1。 | 匹配逻辑："ID-Centric."匹配主要由电子邮件和 MAID 驱动。提供其他 ID 的“收益有限”，因为与 Meta 相比，跨 ID 增强的效果较弱。上传行为：每个受众上传一种标识符类型。 | DCP 数据摄取与结构化指南 |

</Accordion>

<div data-zendesk-anchors="about-dcp-ingestion-and-preparation-of-data=%E5%85%B3%E4%BA%8E%E6%95%B0%E6%8D%AE%E5%87%86%E5%A4%87 h_01KFX4HVTT50TZMY2YF37B1C4R=%E5%85%B3%E4%BA%8E%E6%95%B0%E6%8D%AE%E5%87%86%E5%A4%87 data-types=%E4%BA%86%E8%A7%A3%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B h_01KFX4HVTTAMFEGJQEYXXWG9PT=%E4%BA%86%E8%A7%A3%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B data-ingestion-recommendations=%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E6%8C%87%E5%8D%97 h_01KFX4HVTT2Q2EV4GAC6M8R4A2=%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E6%8C%87%E5%8D%97 h_01KFZJ2PK9XADZ2143VJB3YZ55=workflow-and-structuring-guidelines recommended-identifier-structures=%E6%8E%A8%E8%8D%90%E7%9A%84%E6%A0%87%E8%AF%86%E7%AC%A6%E7%BB%93%E6%9E%84 h_01KFXB0KEF59QCYET0R8XNH84D=%E6%8E%A8%E8%8D%90%E7%9A%84%E6%A0%87%E8%AF%86%E7%AC%A6%E7%BB%93%E6%9E%84 h_01KFZN8104KSPFRSS5SED7VT19=practical-checklist-for-dcp-collaborators identity-userlevel-dataset-checklist=%E8%BA%AB%E4%BB%BD%E7%94%A8%E6%88%B7%E7%BA%A7%E6%95%B0%E6%8D%AE%E9%9B%86%E6%B8%85%E5%8D%95 h_01KFZNGRC0XX7YYBYT09M49YFA=%E8%BA%AB%E4%BB%BD%E7%94%A8%E6%88%B7%E7%BA%A7%E6%95%B0%E6%8D%AE%E9%9B%86%E6%B8%85%E5%8D%95 transactional-events-dataset-checklist=%E4%BA%8B%E5%8A%A1%E4%BA%8B%E4%BB%B6%E6%95%B0%E6%8D%AE%E9%9B%86%E6%B8%85%E5%8D%95 h_01KFZNJ7YKCT1YFYE400CNY6SP=%E4%BA%8B%E5%8A%A1%E4%BA%8B%E4%BB%B6%E6%95%B0%E6%8D%AE%E9%9B%86%E6%B8%85%E5%8D%95 dataviews-checklist=%E6%95%B0%E6%8D%AE%E8%A7%86%E5%9B%BE%E6%B8%85%E5%8D%95 h_01KFZNKBXJQ4S89YHCGKP8J5F4=%E6%95%B0%E6%8D%AE%E8%A7%86%E5%9B%BE%E6%B8%85%E5%8D%95 h_01KFZJ2PK9TT2RZQ366Y2THS7E=supported-ingestion-cloud-services-and-formats format-guidance=%E6%A0%BC%E5%BC%8F%E6%8C%87%E5%8D%97 h_01KFX6XSNACVR9JWZWZW12F6C4=%E6%A0%BC%E5%BC%8F%E6%8C%87%E5%8D%97 h_01KFZJ2PK92Y5HHFC2D1H8AD9B=data-structures-that-arent-recommended avoid-multiple-columns-for-the-same-identifier-type=%E9%81%BF%E5%85%8D%E9%92%88%E5%AF%B9%E5%90%8C%E4%B8%80%E6%A0%87%E8%AF%86%E7%AC%A6%E7%B1%BB%E5%9E%8B%E4%BD%BF%E7%94%A8%E5%A4%9A%E4%B8%AA%E5%88%97 h_01KFX72MNYH1CSKWZAGZ2XETXY=%E9%81%BF%E5%85%8D%E9%92%88%E5%AF%B9%E5%90%8C%E4%B8%80%E6%A0%87%E8%AF%86%E7%AC%A6%E7%B1%BB%E5%9E%8B%E4%BD%BF%E7%94%A8%E5%A4%9A%E4%B8%AA%E5%88%97 avoid-%E2%80%9Clists-inside-a-single-cell%E2%80%9D-free-text=%E9%81%BF%E5%85%8D%E5%8D%95%E4%B8%AA%E5%8D%95%E5%85%83%E6%A0%BC%E5%86%85%E7%9A%84%E5%88%97%E8%A1%A8%E8%87%AA%E7%94%B1%E6%96%87%E6%9C%AC h_01KFX70V3BHNK93SKCRGGDVY3W=%E9%81%BF%E5%85%8D%E5%8D%95%E4%B8%AA%E5%8D%95%E5%85%83%E6%A0%BC%E5%86%85%E7%9A%84%E5%88%97%E8%A1%A8%E8%87%AA%E7%94%B1%E6%96%87%E6%9C%AC avoid-multiple-rows-per-user-for-identifiers-when-your-goal-is-a-user-identity-table=%E9%81%BF%E5%85%8D%E6%A0%87%E8%AF%86%E7%AC%A6%E7%9A%84%E6%AF%8F%E4%B8%AA%E7%94%A8%E6%88%B7%E5%A4%9A%E8%A1%8C%E5%BD%93%E6%82%A8%E7%9A%84%E7%9B%AE%E6%A0%87%E6%98%AF%E7%94%A8%E6%88%B7%E8%BA%AB%E4%BB%BD%E8%A1%A8%E6%97%B6 h_01KFX70V3BJE2PR7132QE27C4V=%E9%81%BF%E5%85%8D%E6%A0%87%E8%AF%86%E7%AC%A6%E7%9A%84%E6%AF%8F%E4%B8%AA%E7%94%A8%E6%88%B7%E5%A4%9A%E8%A1%8C%E5%BD%93%E6%82%A8%E7%9A%84%E7%9B%AE%E6%A0%87%E6%98%AF%E7%94%A8%E6%88%B7%E8%BA%AB%E4%BB%BD%E8%A1%A8%E6%97%B6 additional-information=%E8%A1%A5%E5%85%85%E4%BF%A1%E6%81%AF h_01KFZJ2PNKB4X962VKCKSYVFFB=%E8%A1%A5%E5%85%85%E4%BF%A1%E6%81%AF h_01KFX6XSJYGYFF052EM8NHNMYQ=appendix-a-transactional-data-examples h_01KFX6XSJYZNCTGD5CNSKN5KF7=appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake what-does-%E2%80%9Carraylist-of-identifiers%E2%80%9D-mean=%E6%A0%87%E8%AF%86%E7%AC%A6%E6%95%B0%E7%BB%84%E5%88%97%E8%A1%A8%E6%98%AF%E4%BB%80%E4%B9%88%E6%84%8F%E6%80%9D h_01KFX4HVTVPHZQFNRWDH9VCEZQ=%E6%A0%87%E8%AF%86%E7%AC%A6%E6%95%B0%E7%BB%84%E5%88%97%E8%A1%A8%E6%98%AF%E4%BB%80%E4%B9%88%E6%84%8F%E6%80%9D 1-aws-s3-and-gcs-connector-parquet=1aws-s3-%E5%92%8C-gcs-%E8%BF%9E%E6%8E%A5%E5%99%A8-parquet h_01KFX4HVTVNQZY9A8AGEBBHF6Y=1aws-s3-%E5%92%8C-gcs-%E8%BF%9E%E6%8E%A5%E5%99%A8-parquet 2-bigquery-connector-table-preview-and-schema-screenshot=2-bigquery-%E8%BF%9E%E6%8E%A5%E5%99%A8%E8%A1%A8%E9%A2%84%E8%A7%88%E5%92%8C%E6%9E%B6%E6%9E%84%E6%88%AA%E5%9B%BE h_01KFX4HVTVCMB0H1B76TCK36SF=2-bigquery-%E8%BF%9E%E6%8E%A5%E5%99%A8%E8%A1%A8%E9%A2%84%E8%A7%88%E5%92%8C%E6%9E%B6%E6%9E%84%E6%88%AA%E5%9B%BE 3-snowflake-connector-table-preview-and-schema-screenshot=3snowflake-%E8%BF%9E%E6%8E%A5%E5%99%A8%E8%A1%A8%E9%A2%84%E8%A7%88%E5%92%8C%E6%9E%B6%E6%9E%84%E6%88%AA%E5%9B%BE h_01KFX4HVTVN9MSWFB7ZRT9MVCG=3snowflake-%E8%BF%9E%E6%8E%A5%E5%99%A8%E8%A1%A8%E9%A2%84%E8%A7%88%E5%92%8C%E6%9E%B6%E6%9E%84%E6%88%AA%E5%9B%BE h_01KFX6XSJYF4V3ZTX8X07J0FGS=appendix-c-why-dataviews-matter-and-recommended are-businessoriented-and-easier-to-collaborate-with=%E4%BB%A5%E4%B8%9A%E5%8A%A1%E4%B8%BA%E5%AF%BC%E5%90%91%E6%9B%B4%E6%98%93%E4%BA%8E%E5%8D%8F%E4%BD%9C h_01KFX4HVTV43QFEQARSB2N49Z5=%E4%BB%A5%E4%B8%9A%E5%8A%A1%E4%B8%BA%E5%AF%BC%E5%90%91%E6%9B%B4%E6%98%93%E4%BA%8E%E5%8D%8F%E4%BD%9C are-more-privacysafe-by-design=%E5%9C%A8%E8%AE%BE%E8%AE%A1%E4%B8%8A%E6%9B%B4%E6%B3%A8%E9%87%8D%E9%9A%90%E7%A7%81%E5%AE%89%E5%85%A8 h_01KFX4HVTVJA8Q3FTQB8A94MA1=%E5%9C%A8%E8%AE%BE%E8%AE%A1%E4%B8%8A%E6%9B%B4%E6%B3%A8%E9%87%8D%E9%9A%90%E7%A7%81%E5%AE%89%E5%85%A8 protect-sensitive-business-data=%E4%BF%9D%E6%8A%A4%E6%95%8F%E6%84%9F%E7%9A%84%E4%B8%9A%E5%8A%A1%E6%95%B0%E6%8D%AE h_01KFX4HVTVF8A0PM90FA6XA0V5=%E4%BF%9D%E6%8A%A4%E6%95%8F%E6%84%9F%E7%9A%84%E4%B8%9A%E5%8A%A1%E6%95%B0%E6%8D%AE can-make-your-data-more-costeffective-and-performant=%E5%8F%AF%E4%BB%A5%E4%BD%BF%E6%82%A8%E7%9A%84%E6%95%B0%E6%8D%AE%E6%9B%B4%E5%85%B7%E6%88%90%E6%9C%AC%E6%95%88%E7%9B%8A%E4%B8%94%E6%80%A7%E8%83%BD%E6%9B%B4%E9%AB%98 h_01KFX4HVTVJ70HV606Y8KE4JD1=%E5%8F%AF%E4%BB%A5%E4%BD%BF%E6%82%A8%E7%9A%84%E6%95%B0%E6%8D%AE%E6%9B%B4%E5%85%B7%E6%88%90%E6%9C%AC%E6%95%88%E7%9B%8A%E4%B8%94%E6%80%A7%E8%83%BD%E6%9B%B4%E9%AB%98 h_01KFX6XSJY4WGJDBP5JEQXC6E3=appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform h_01KGFDYKG8KPYR7H5VBKVTXTQS=appendix-e-hashed-data-formatting-guidelines-by-media-partner" />

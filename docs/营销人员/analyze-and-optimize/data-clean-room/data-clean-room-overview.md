---
title: 数据净室简介
metadata:
  keywords:
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
  created_at: '2022-03-08T14:47:36Z'
  edited_at: '2026-10-14T09:59:46Z'
  id: 4626852381713
  locale: zh-cn
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/zh-cn/articles/4626852381713
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**![privacy_cloud_logo.png](https://files.readme.io/5862beb63a4b22f68fc230f89c3faa260a15ab40e1defa70c59604d5a81e759d-5583061038225.png)**

> **概要：** 将广告主侧的用户级别数据与AppsFlyer的用户级别归因数据进行匹配，结合双方数据形成扩充的汇总报告，充分解锁数据价值，发掘有效信息。

## 简介

自移动营销生态系统成形以来，广告主一直都通过用户级别的数据提炼关键信息，并优化广告投放：

1. 媒体渠道向归因服务商（如AppsFlyer）提供用户级别数据，用于归因衡量，然后归因服务商再将这些数据发送给广告主。
2. 广告主将这些用户级别数据与其第一方用户级别数据（如BI或CRM系统内的数据）进行匹配、分析，并根据实际需求进行数据分组，从而提炼出汇总的关键信息，用于优化投放。

在用户隐私至上的新形势下，渠道侧的用户级别数据大幅受限，具体如下：

1. 渠道仍会向归因服务商（如AppsFlyer）提供用户级别数据，用于归因衡量；**但归因服务商无法再将这些数据发送给广告主。**
2. 这样一来，广告主就无法再将用户级别的归因数据匹配到其第一方数据，进而无法提炼所需的关键信息。

AppsFlyer推出数据净室（DCR），正是为了填补这个数据盲区。

### 原理

我们改变了以往的模式，不再将用户级别的归因数据发送给广告主，让***广告主***将其与第一方数据进行匹配，而是通过***DCR直接将用户级别的归因数据匹配***到广告主的用户级数据——换言之，我们将数据匹配工作转移到了AppsFlyer。DCR会对这些数据进行分析和分组，并以汇总的形式发送给广告主。这样，广告主就能获得必要的关键信息，同时**确保用户隐私不受侵犯**。

### DCR如何获取数据？

DCR目前使用的数据有以下两种：

* **自定义来源的数据**：上传到云存储的用户级数据，专用于DCR。这类数据来自广告主的内部系统（如BI或CRM）。
* **归因数据：** 由媒体渠道发送给AppsFlyer的用户级数据，用于归因。

### DCR如何处理数据？

DCR按照标准的数据库原理处理数据。也就是说，DCR会将来自不同表格（即 **“数据源”**）的数据进行匹配，形成一个统一的数据集，然后通过合并的数据来创建**报告**：

* 为了匹配不同来源的数据，将其合并到一个数据集中，各数据源之间必须共享至少一个相同的独立用户标识字段<strong>（“标识符”）</strong>。
* DCR通过标识符将广告主侧的用户级数据与AppsFlyer的用户级归因数据进行匹配，形成用户级别的数据集。
* 为了在保护用户隐私的条件下攫取关键信息，DCR会在该数据集的基础上创建**汇总报告**，并按照您指定的特征<strong>（“维度”）</strong>进行分组。

## DCR相关概念

下文列出了DCR中常用的一些术语及其定义：

* **连接器（connector）：** 广告主侧自有的AWS或GCS存储桶，用于存储DCR数据。连接器可以包括从您的数据源传输到DCR的文件夹和/或DCR产出的报告文件夹的传输终点。您可以使用单个或多个连接器向DCR传入/从DCR传出数据。
* **数据源：**
  * 传入DCR中的广告主第一方数据文件，用于匹配并扩充AppsFlyer归因数据。更新的数据源文件最多可以每6小时上传并处理一次。在AppsFlyer的DCR平台中设置数据源时，您需要定义其**结构**和**位置**：
    * **数据源结构：** 数据源中的一系列字段以及您为每个字段分配的类别（标识符、维度或指标），用于创建报告。
    * **数据源位置：** 您每次更新数据源文件时，供AppsFlyer获取这些数据的云服务文件夹。该文件夹存放于数据存储桶中（即connector，连接器）。
  * **归因数据：** 来自您AppsFlyer账户的用户级归因数据（用于匹配并扩充DCR中的广告主数据）。
* **报告：** DCR处理完毕后传出的数据文件。每次相关数据源文件更新后都会生成报告。在AppsFlyer的DCR平台中设置报告时，您需要定义其**结构**和**传输终点**：
  * **报告结构：** 广告主数据源和归因数据的取用标准，用于创建相关报告，包括用于数据匹配的标识符、报告中需包含的指标，以及报告中的数据分组维度。
  * **报告传输终点：** AppsFlyer每次处理完数据后，从AF接收相关报告的云服务文件夹。该文件夹存放于数据存储桶中（即connector，连接器）。

## DCR的使用方式（设置流程）

AppsFlyer的数据净室（DCR）具有非常灵活全面的适配能力，您可以选择需要上传的数据类型、需要接收的报告，以及数据处理的时间和频次。因此您需要对其设置流程做一定的规划——可能会涉及贵司内部多方人员的协作。

请按以下步骤完成符合贵司需求的DCR设置：

1. 规划您要从DCR接收的报告类型。DCR会使用AppsFlyer的归因数据对广告主侧的数据进行扩充，然后形成报告。因此您需要确定上传到DCR的第一方数据源，作为这些报告的基础。
2. <Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-setting-up-cloud-services">创建基础的云存储结构</Anchor>，用以支持相关的数据源和报告。
3. 配置用于拉取数据并产出源数据文件的查询参数；制定源数据文件的原型。
4. 开发自动化流程，用于定时拉取数据、创建数据源子文件夹、上传源数据以及<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-sources#_success-files">\_SUCCESS文件夹</Anchor>。
5. 在AppsFlyer的DCR平台中设置您的<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-sources">数据源</Anchor>。
6. 在AppsFlyer的DCR平台中设置您的<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-reports">报告</Anchor>。
7. 开发自动化流程，在DCR产出和报告后将其上传到您的云存储工具中。

<div data-zendesk-anchors="introduction=%E7%AE%80%E4%BB%8B h_01HE7SDH5PWCW6YG00GC12W4BS=%E7%AE%80%E4%BB%8B how-does-it-work=%E5%8E%9F%E7%90%86 h_01HE7SDH5PW64CHNJVJJ30V5ZY=%E5%8E%9F%E7%90%86 how-does-the-dcr-obtain-data=dcr%E5%A6%82%E4%BD%95%E8%8E%B7%E5%8F%96%E6%95%B0%E6%8D%AE h_01HE7SDH5P82HCEN52ZBPMQV16=dcr%E5%A6%82%E4%BD%95%E8%8E%B7%E5%8F%96%E6%95%B0%E6%8D%AE what-does-the-dcr-do-with-the-data=dcr%E5%A6%82%E4%BD%95%E5%A4%84%E7%90%86%E6%95%B0%E6%8D%AE h_01HE7SDH5PWDQ61389TT7V83F8=dcr%E5%A6%82%E4%BD%95%E5%A4%84%E7%90%86%E6%95%B0%E6%8D%AE dcr-terminology=dcr%E7%9B%B8%E5%85%B3%E6%A6%82%E5%BF%B5 h_01HE7SDH5P3QSG874XASXNH1YS=dcr%E7%9B%B8%E5%85%B3%E6%A6%82%E5%BF%B5 working-with-the-dcr-setup-workflow=dcr%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B h_01HE7SDH5P0S9542P2CB22KKVT=dcr%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B" />

---
title: 原始数据导出页面
metadata:
  keywords:
    - ad networks
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
    - Ad Networks
  created_at: '2020-05-11T22:25:33Z'
  edited_at: '2026-10-14T10:03:23Z'
  id: 360008613838
  locale: zh-cn
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/zh-cn/articles/360008613838
---
> **概要：** 本文讲解了如何拉取CSV格式的原始数据报告。每次最多可下载100万行数据。您可以使用筛选条件，让报告仅呈现您需要的数据。

下图展示了您首次进入**原始数据导出**页面时所看到的界面；当您有可下载或复制的报告时，界面会展示**我的报告**页面。

[![RawDataSplash.png](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)

**我的报告**

**我的报告**页面中会列出前90天内已创建且可下载和/或复制的一系列报告，其下载期限为7天。7天过后，您需要重新创建相关报告才能进行下载。

如需查看原始数据报告的详细说明，请参阅<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">原始数据报告简介</Anchor>。

如需生成或下载报告，请参考本文中的流程说明部分。

[![MyReportsRawDataExport.png](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)

<div id="raw-data-export-page-features-and-filter-options" />

<Accordion title="原始数据导出页面的功能和筛选条件选项">

下表列出了原始数据导出页中的报告特点：

<Table>
  <thead>
    <tr>
      <th>
        功能
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-categories"></span>
        报告类别
      </td>
      <td>
        具体可用类别取决您订阅的套餐
      </td>
    </tr>
    <tr>
      <td><span id="date-range"></span>
        日期范围
      </td>
      <td>
        原始数据报告按活跃日期（即事件发生日期）筛选数据。您也可以添加以激活日期为准的筛选条件。具体请参见下文表格，其中列出了各种筛选条件选项。
      </td>
    </tr>
    <tr>
      <td><span id="maximum-number-of-rows"></span>
        行数上限
      </td>
      <td>
        100万行
      </td>
    </tr>
    <tr>
      <td><span id="rate-limitation"></span>
        拉取频次限制
      </td>
      <td>
        每天的报告拉取次数是有<Anchor target="_blank" href="/marketers/zh/docs/report-generation-quotas-rate-limitations">限额</Anchor>的。
      </td>
    </tr>
    <tr>
      <td><span id="retentionreport-window"></span>
        数据保留/报告窗口期
      </td>
      <td>
        激活相关的报告（激活、激活回传）每次下载可包含前90天中**60**天的数据。

        应用内事件相关的报告：每次下载可包含前90天中31天的数据。
      </td>
    </tr>
    <tr>
      <td><span id="filter-options"></span>
        筛选选项
      </td>
      <td>
        界面中会列出可用的筛选条件。部分筛选条件的选项会自动填充。比如按国家/地区（Geo）筛选数据时下拉菜单中会列出可用的国家选项。
      </td>
    </tr>
    <tr>
      <td><span id="field-selection"></span>
        字段选择
      </td>
      <td>
        最重要的字段自动勾选且无法取消。您可以在**报告字段**选项卡中添加/清除选定字段。部分字段对可能不适用于某些报告，但您仍可以选择这些字段。这样是为了便于您拉取格式一致的报告（即具有相同的列）。

        比如在用户获取的应用内事件报告中选择假量相关（Protect360）的字段时，会返回空白列。这些字段仅在Protect360报告中才会填充。
      </td>
    </tr>
    <tr>
      <td><span id="report-csv-field-order"></span>
        报告（CSV）字段顺序
      </td>
      <td>
        报告中的各列按字段排序设置排列。[这张Excel表](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx)中分“legacy”（历史）和“default”（默认）两个工作表分别列出了相应的字段顺序。

        | 配置 | 是否可选择字段 | 说明 |
        | --- | --- | --- |
        | <span id="default"></span>默认 | 是 | * 选定字段按AppsFlyer模板排序。<br />* 该顺序会被保留下来，后续添加的字段会显示在现有字段的右侧。 |
        | <span id="alphabetical-az"></span>按字母顺序（A-Z） | 是 | 选定的字段会按字母顺序排列（升序）。 |
        | <span id="alphabetical-za"></span>按字母顺序（Z-A） | 是 | 选定的字段会按字母逆序排列（降序）。 |
        | <span id="legacy"></span>旧版 | 否 | * 即通过之前的导出数据页面拉取的报告中所使用的字段顺序。<br />* 字段选择是固定的，无法更改。<br />* 部分报告的字段顺序可能会有所变化，具体取决于实际拉取的报告。 |
      </td>
    </tr>
  </tbody>
</Table>

> 📘 **注意**
>
> 如果您同时使用“代理”和“媒体渠道”这两个筛选条件，则“媒体渠道”这个筛选条件不会对数据不透明的代理生效。也就是说报告中会包含所有不透明代理的数据，而不仅仅是按媒体渠道筛选出来的数据。

| 筛选条件 | 广告主 | 广告平台 | Agency（代理） |
| --- | --- | --- | --- |
| Media source（媒体渠道） | 是 | 否 | 是 |
| 活跃日期范围 | 是 | 是 | 是 |
| 安装日期范围 | 是 | 是 | 是 |
| Agency（代理） | 是 | 否 | 否 |
| Geo（国家/地区） | 是 | 是 | 是 |
| 应用内事件（适用于应用内事件报告） | 是 | 否 | 是 |

</Accordion>

<div id="note" />

<div id="procedures" />

## 流程

<div id="create-a-default-report" />

<Accordion title="创建默认报告">

您可以使用默认设置创建报告，无需自行设置报告中的字段或筛选条件。

**如需创建默认报告，请按以下方式操作：**

1. 在AppsFlyer后台左侧的菜单栏中选择**导出** > **原始数据导出**。
2. 点击 + **新报告**
3. 将鼠标悬停在您需要创建的报告类型上，然后点击**创建**。
4. 在下拉菜单中选择**立即生成**。
5. 在弹窗中点击立即生成。该生成过程最多可能需要10分钟。
   * 在报告生成期间，您可以继续创建其它报告或访问其它页面。

**默认报告中的筛选条件设置：**

| 筛选条件 | 默认设置 |
| --- | --- |
| 活跃数据日期 | 过去7天 |
| 每个文件中最多可包含的行数 | 200,000 |
| Media source（媒体渠道） | 所有媒体渠道 |
| Agency（代理） | 所有代理 |
| 国家/地区 | 所有国家/地区 |

</Accordion>

<div id="create-a-custom-report" />

<Accordion title="创建自定义报告">

您可以自行设置原始数据报告的筛选条件和字段，创建自定义报告。

**如需创建自定义报告，请按以下方式操作：**

1. 在AppsFlyer后台左侧的菜单栏中选择**导出** > **原始数据导出**。
2. 点击 + **新报告**
3. 将鼠标悬停在您需要创建的报告类型上，然后点击**创建**。
4. 从下拉菜单中选择**自定义**。
5. 设置报告的筛选条件
   * **活跃数据日期：** 选择活跃数据的日期范围。您可以设置具体日期或从自定义、昨天、近7天等选项中选择。
   * **每个文件最多可包含的行数**：【可选】设置文件中的数据行数上限。可用选项为100、20万、50万或100万行。
   * **媒体渠道**：【可选】报告仅呈现归因到选定渠道的事件。您可以点击**添加项目**，在列表中添加所需的媒体渠道。
   * **代理**：【可选】报告仅呈现归因到选定代理的事件。您可以点击**添加项目**，在列表中添加所需的代理。
   * **国家/地区**：【可选】报告仅呈现归因到选定国家/地区的事件。
   * **分报告类型的筛选条件：** 每种报告类型都有一些专属的筛选条件供您选用。
6. 【可选】：报告会自动填充所需字段。您可以按以下方式添加或移除字段：
   1. <span class="af-ol-a"></span>进入**报告字段**选项卡。界面会显示已选定的字段。必填字段默认勾选且无法取消。
   2. 根据实际需求勾选或取消勾选相关字段。
   3. 【可选】设置**报告（CSV）字段排序**，调整各列顺序。
   4. 【可选】如有需要，可点击**恢复默认**。
7. 点击**创建**，
   * 界面会显示**我的报告**页面。状态部分最初会显示“报告正在生成中”。
   * 该生成过程最多可能需要10分钟。
   * 在报告生成期间，您可以继续创建其它报告或访问其它页面。

</Accordion>

<div id="download-report" />

<Accordion title="下载报告">

**报告的下载方式如下：**

1. 在AppsFlyer后台左侧的菜单栏中选择**导出** > **原始数据导出**。
2. 点击![DownloadIcon.png](https://files.readme.io/6c00f4922fc3a835a856d7fdf527aa32d2f50570710c1527b039f43a7acbba79-41225791763217.png)（下载），即可下载该报告。生成后的报告在7天内都可供下载。

</Accordion>

<div id="duplicate-and-edit-report-settings" />

<Accordion title="复制并修改报告设置">

**请按以下方式复制并修改报告设置：**

1. 在AppsFlyer后台左侧的菜单栏中选择**导出** > **原始数据导出**。
2. 点击![Duplicate.png](https://files.readme.io/f745081f1bf0c4f5861e275a29048fe84e8020f8b3bf4ebe4ad6a8d9254ab4b5-41225784681233.png)复制报告设置并进行必要修改。
3. 点击**创建**。生成后的报告在7天内都可供使用。   
   * 界面会显示**我的报告**页面。状态部分最初会显示“报告正在生成中”。
   * 该生成过程最多可能需要10分钟。
   * 在报告生成期间，您可以继续创建其它报告或访问其它页面。

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 渠道权限 | 是 |
| 代理访问权限 | 是 |
| 代理数据透明化 | 区分。 但如果您同时使用“代理”和“媒体渠道”这两个筛选条件，“媒体渠道”这个筛选条件不会对数据不透明的代理生效。也就是说报告中会包含所有不透明代理的数据，而不仅仅是按媒体渠道筛选出来的数据。 |
| 应用层级的指定时区 | 是 |
| 应用配置中的指定货币 | 是 |
| 局限性 | 每次最多可下载100万条数据 |
| 自然量数据 | 可用 |
| 非自然量数据 | 可用 |
| 数据时效性 | 取决于具体报告 |
| 历史数据 | 前90天 |
| 相关账户下的用户权限 | <Anchor target="_blank" href="/marketers/zh/docs/user-management">角色中具有必要权限</Anchor>的用户 |
| 通过邮件发送 | 不支持 |
| 安装日期范围 | 激活日期范围必须早于活跃日期范围。 |
| 原始数据回传报告 | 如果事件被归因到数据不透明的代理，则这些事件的渠道回传不会包含在广告主的原始数据回传报告中。 |

</Accordion>

<div id="field-sequence-templates" />

<Accordion title="字段顺序模板">

您可以通过报告字段排序设置来指定报告中各列的顺序，在部分情况下还能调整字段本身。

| 配置 | 是否可选择字段 | 说明 |
| --- | --- | --- |
| <span id="default::b7bb6355"></span>默认 | 是 | <ul><li>选定字段按AppsFlyer模板排序。</li><li>该顺序会被保留下来，后续添加的字段会显示在现有字段的右侧。</li></ul> |
| <span id="alphabetical-az::b08af6b3"></span>按字母顺序（A-Z） | 是 | 选定的字段会按字母顺序排列。 |
| <span id="alphabetical-za::f0b3beb8"></span>按字母顺序（Z-A） | 是 | 选定的字段会按字母逆序排列。 |
| <span id="legacy::fb5fd8ec"></span>旧版 | 否 | <ul><li>即通过之前的导出数据页面拉取的报告中所使用的字段顺序。</li><li>字段选择是固定的，无法更改。</li><li>部分报告的字段顺序可能会有所变化，具体取决于实际拉取的报告。</li></ul> |

[这张Excel表](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx)中同时包含“legacy”（历史）和“default”（默认）两个工作表。每张工作表中分别列出了相应的字段排序。

**如需更改字段排序，请按以下方式操作：**

1. 进入报告字段选项卡，选择一种**报告字段排序**方式。
2. 如有需要，您还可以更改选定字段，只需勾选或取消勾选相关字段即可。

</Accordion>

<div data-zendesk-anchors="h_01HA28AT6QRSG68NBFYHH5SQY8=raw-data-export-page-features-and-filter-options h_01HA28CJ4W692V6EVC7XTQEZG6=%E6%B3%A8%E6%84%8F procedures=%E6%B5%81%E7%A8%8B h_01HA28AT6Q9PV3M55C1YM3XN2E=%E6%B5%81%E7%A8%8B h_01HZY1HQ9AVH6Q9QAQB4SM1VPX=create-a-default-report h_01HZY1HQ9ACEMZ4N8WPYNHZQP7=create-a-custom-report h_01HA28AT6QV1XP4N952PAEGSSG=download-report h_01HA28AT6QFT88RHJ3M05MV3B3=duplicate-and-edit-report-settings additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HA28AT6Q4DXKCZ22R9XEN2RR=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HA28AT6Q6SE8CB3EEXFMAN0H=traits-and-limitations h_01HA28AT6RW8C99ZGEBTN5E44R=field-sequence-templates" />

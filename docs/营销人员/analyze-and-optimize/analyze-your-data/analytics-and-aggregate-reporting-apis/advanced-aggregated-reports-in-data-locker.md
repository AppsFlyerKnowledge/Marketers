---
title: Data Locker中的高级汇总报告
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2024-03-06T10:46:12Z'
  edited_at: '2026-10-14T10:03:05Z'
  id: 23127074968721
  locale: zh-cn
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/zh-cn/articles/23127074968721
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要**：Data Locker中的高级汇总报告具有最高的时效性和准确性，可呈现颗粒度最细的数据，且对数据量没有限制。

<div id="advanced-aggregated-reports-in-data-locker" />

## Data Locker中的高级汇总报告

Data Locker中的高级汇总报告具有下列优势：

* 以汇总数据为基础，在保障用户隐私的前提下帮助您高效搭建内部BI系统。按可用范围内所有的维度和指标，提供归因、事件和收入数据。
* 您可以将该数据入库到BI，用于投放效果分析和优化。
* 提供最佳的F2A数据：<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">一天多次</Anchor>拉取数据，每次都使用当天所有可用数据更新相关报告，并以版本化的形式呈现。
* 当原始数据受到媒体渠道数据共享政策或广告主<Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">隐私保护政策</Anchor>的<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">限制</Anchor>时，高级汇总报告可帮助您扩充原始数据。这样的限制会影响到与归因有关的字段，如广告系列和广告组。

<div id="setup" />

## 设置方式

如需获取高级汇总报告，请按您的实际情况完成以下任一流程。

| 您目前是否通过Data Locker取数 | 流程 |
| --- | --- |
| 是 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)将报告添加到Data Locker：<ol><li>从AppsFlyer后台左侧的菜单栏中选择**导出 > Data Locker**。</li><li>选择您需要的所有报告。</li><li>点击**保存配置**。<br />相关报告将于次日制作完毕。</li></ol> |
| 否 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**完成Data Locker的设置**：<ol><li>完成Data Locker的初始设置（<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers#set-up-data-locker">广告主指南</Anchor>｜<Anchor target="_blank" href="/partners/zh/docs/data-locker-for-partners">渠道指南</Anchor>）。</li><li>将相关报告添加到Data Locker：<ol><li>从AppsFlyer后台左侧的菜单栏中选择**导出 > Data Locker**。</li><li>选择您需要的所有报告。</li><li>点击**保存配置**。<br />相关报告将于次日制作完毕。</li></ol></li></ol> |

<div id="reports-available" />

## 可用报告

<div id="cohort-versioned-report" />

<Accordion title="高级汇总（版本化的群组数据）报告">

<div id="report-facts" />

### 详情说明

| 速览 | 版本化的群组数据报告中包含所有按群组汇总的数据，并提供所有投放维度，细化到所有颗粒度。该报告数小时更新一次，确保最高的数据时效性和准确性。<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vT8NQKO287TxXpdTYpIASL55t4muIt9G3lnkEE436FQhNn5_14DfYgf0ztbm1VVZXI4ecPaGktdixS7/pub?output=xlsx">下载报告样例</Anchor> |
| --- | --- |
| 可用报告 | 可下载的报告包括以下几种（各类报告的详细介绍请参见群组面板）：<ul><li>**用户获取**：归因到拉新（UA）渠道的LTV数据，包括再互动窗口期内的LTV。</li><li>**再营销**：归因到再营销渠道的LTV数据。分以下两种情况：<ul><li>再互动窗口期内发生的事件</li><li>再归因后发生的事件</li></ul></li><li>**统一**：根据AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">双重归因</Anchor>规则，归因到末次触达渠道的LTV数据。也就是说在统一视图中，再互动LTV数据会显示在再营销渠道下，而不会显示在UA渠道下。</li></ul> |
| 报告周期 | 报告涵盖在过去1095天内转化的用户。也就是说每一天的报告都包含了在当前日期之前的1095天内转化的用户所产生的事件。 |
| 报告结构 | 报告结构（即其中的维度和指标）是固定的，无法更改。 |
| 数据时效性 | <ul><li>一天更新多次，每数小时发送一次报告。</li><li>报告提供当日数据。举例来说，4月28日内每个版本的报告都包含4月28日当天截至该版本创建时间为止的所有可用数据。[详情请见此处说明。](/docs/advanced-aggregated-reports-in-data-locker#报告版本和数据时效性)</li></ul> |
| 时区 | UTC |
| 目录与文件名结构 | [详情请见此处说明。](/docs/advanced-aggregated-reports-in-data-locker#报告结构) |
| 渠道的数据保存期限 | 有些渠道设有数据保存期限。对于数据保存期限之后发生的事件，群组报告会将其记录为自然量。<br /><br />举例说明：SRN A的数据保存期限为180天。第180天之前发生的用户事件会被归因到SRN A，第180天之后发生的事件被记录为自然量。 |

<div id="report-structure" />

### 报告结构

报告由不同的维度和指标组成。

具体的字段格式如下：

* **维度**：以字符串格式呈现，长度不定，一般取决于广告层级的填充方式。
* **指标**：以数字的形式呈现。**请注意：** selected\_currency字段以字符串的格式呈现。  
  可用指标为收入、完成某事件的独立用户数以及事件发生次数。ROI、ROAS等成本指标的计算需要同时用到收入和成本数据。收入数据可通过群组报告获取，而成本数据则需使用<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL。</Anchor>

<div id="dimensions" />

#### 维度

<Table>
  <thead>
    <tr>
      <th>
        字段名称
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        可能出现的值：install（激活）、install-unified（统一视图报告中的激活）、re-engagement（再互动）、re-attribution（再归因）
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        可能出现的值包括click（点击）、impression（展示）、pre-installed（预装）、unknown（未知）、tv、null
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        * 转化后的天数（不是实际转化的时间戳）
        * 小贴士：您可以使用该数据来计算留存和KPI天数。
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        * 用户完成某个事件的日期。
        * 格式：yyyy-mm-dd
        * 举例来说，用户完成某个应用内事件的日期。
        * 请注意：如果event\_name是af\_conversion，则事件日期与转化日期相同。
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        * 转化发生的日期
        * 格式：yyyy-mm-dd
        * 举例来说，激活日期
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        用于标识事件。有些事件名称具有特定含义，而有些则与广告主在应用中设置的应用内事件有关。 

        | event\_name | 用户行为 |
        | --- | --- |
        | af\_conversion | 用户转化。使用conversion\_type来识别转化类型，即激活、再互动、再归因或再互动。 |
        | af\_session | 用户打开应用 |
        | cohort\_uninstalls | 用户卸载应用 |
        | 广告主定义的应用内事件 | 用户完成指定应用内事件。 |
      </td>
    </tr>
    <tr>
      <td>
        campaign
      </td>
      <td>
        广告层次结构中的一个层级

        需注意：不支持更改广告系列名称。也就是说，如果您更改了广告系列名称，就会出现多个广告系列名称对应同一个广告系列ID的现象。
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        adset
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        ad
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        channel
      </td>
      <td>
        广告层次结构中的一个层级。

        【2021年10月27日更新】目前Meta ads不在channel字段中填充来自Google Install Referrer机制的数据。
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        is\_primary\_attribution
      </td>
      <td>
        用于识别再营销数据并去重。
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        基于用户IP地址的ISO国家代码。
      </td>
    </tr>
    <tr>
      <td>
        agency
      </td>
      <td>
        * 支持代理数据透明化。
        * 在代理数据不透明的情况下，如果广告主和代理同时使用同一个广告系列名称进行投放，则报告中会有多行数据显示该名称。但这些数据并不是重复数据，所以不必担心。
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        仅适用于安卓应用：用于表达用户下载相关应用的安卓商店。使用<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution">第三方安卓应用商店归因方案</Anchor>的广告主会看到这个字段。如果该字段为空，则表示用户从Google Play Store下载应用。
      </td>
    </tr>
    <tr>
      <td>
        keywords
      </td>
      <td>
        用户在线搜索时所使用的字词，由广告平台上报。
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        由广告平台返回，
      </td>
    </tr>
  </tbody>
</Table>

<div id="metrics" />

#### 指标

| 字段名称 | 说明 | 格式 |
| --- | --- | --- |
| unique\_users | 当日完成相关事件的独立用户数。 | 数字 |
| revenue\_usd | <ul><li>以USD为单位的收入数额。如100.56美元会显示为100.56。</li><li>最多精确到小数点后2位。</li></ul> | 数字 |
| event\_count | 事件发生次数 | 数字 |
| selected\_currency | 3字母货币代码（如USD、EUR等），由广告主在AF后台的应用设置页面中配置。完整列表请参考<Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>。这里的货币与AF群组面板中收入指标的货币单位一致。 | 字符串 |
| revenue\_selected\_currency | <ul><li>以指定货币为单位的收入数额。假设指定货币为EUR，则1234.56欧元会显示为1234.56。</li><li>最多精确到小数点后2位。</li></ul> | 数字 |
| first\_inapp | <ul><li>转化后首次完成相关应用内事件的用户数量。</li><li>将first\_inapp指标加总后可得出该事件的累计独立用户数。</li></ul> | 数字 |

<div id="directory-and-filename-structure" />

#### 目录与文件名结构

构成报告路径的文件夹结构如下：

格式：`/t=cohort_unified_versioned/dt=/version=/`

<div id="report-folder-hierarchy" />

#### 报告文件夹的层次结构

在广告主的数据存储桶中，版本化群组数据报告的文件夹结构如下方样例所示：

```
bucket
|
└── t=cohort_unified_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**说明：**

* **dt**：报告中的事件发生的日期。
* **t**：报告类型。
* **version**：相关版本的创建时间，以Unix时间戳表达。

<div id="report-versions-and-data-freshness" />

### 报告版本和数据时效性

* 一天更新多次，每数小时发送一次报告。
* 报告中包含当前可用的所有当日数据。举例来说，4月28日内每个版本的报告都包含4月28日当天截至该版本创建时间为止的所有可用数据。
* **建议您总是导入最近期的那一版数据。**

| 版本 | AppsFlyer接收数据的截止时间（以UTC时区为准） | 使用场景 | 报告制作完毕的时间（以UTC时区为准） |
| --- | --- | --- | --- |
| 1 | 第0天凌晨4点 | 第0天的部分数据 | 第0天上午8点 |
| 2 | 第0天上午8点 | 第0天的部分数据 | 第0天下午1点 |
| 3 | 第0天中午12 点 | 第0天的部分数据 | 第0天下午6点 |
| 4 | 第0天下午4点 | 第0天的部分数据 | 第0天晚上9点 |
| 5 | 第0天晚上8点 | 第0天的部分数据 | 第0天晚上11:59 |
| 6 | 第0天晚上11:59 | 第0天完整的转化和应用内事件数据（不包含AppsFlyer从第0天晚上11:59到第1天凌晨2点接收到的S2S事件） | 第1天凌晨4点 |
| 7 | 第1天凌晨3点 | 第0天完整的转化和应用内事件数据，以及通过S2S发送的所有当前广告收入数据。 | 第1天上午8点 |
| 8 | 第1天上午11点 | 第0天完整的转化和应用内事件数据，以及通过S2S发送的所有当前广告收入数据。 | 第1天下午6点 |
| 9 | 第1天下午5点 | 第0天完整的转化和应用内事件数据，以及通过S2S发送的所有当前广告收入数据。 | 第1天晚上11:59 |
| 10 | 第8天上午7点 | 第0天完整的转化和应用内事件数据，以及通过S2S发送的完整广告收入数据，这些数据已经根据变现平台侧可能出现的任何问题进行了调整。 | 第8天下午1点 |

</Accordion>

<div id="cohort-timezone-versioned-report" />

<Accordion title="高级汇总（按本地时区版本化的群组数据）报告">

<div id="report-facts-1" />

### 详情说明

| 速览 | 按本地时区版本化的群组数据报告中包含所有按群组汇总的数据，并提供所有投放维度，细化到所有颗粒度。该报告数小时更新一次，确保最高的数据时效性和准确性。<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQk1cZkeJhlx3trW13SjGbD4aWX3LmXZJRDJRApuAJkjB7XAg4nSFUyN0_YoirX-QMHkhFeMHwEmiVj/pub?output=xlsx">下载报告样例</Anchor> |
| --- | --- |
| 可用报告 | 可下载的报告包括以下几种（各类报告的详细介绍请参见<Anchor target="_blank" href="/marketers/zh/docs/cohort-and-retention-dashboard#cohort-principles">群组面板</Anchor>）：<ul><li>**用户获取**：归因到拉新（UA）渠道的LTV数据，包括再互动窗口期内的LTV。</li><li>**再营销**：归因到再营销渠道的LTV数据。分以下两种情况：<ul><li>再互动窗口期内发生的事件</li><li>再归因后发生的事件</li></ul></li><li>**统一**：根据AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">双重归因</Anchor>规则，归因到末次触达渠道的LTV数据。也就是说在统一视图中，再互动LTV数据会显示在再营销渠道下，而不会显示在UA渠道下。</li></ul> |
| 报告周期 | 报告涵盖在过去1095天内转化的用户。也就是说每一天的报告都包含了在当前日期之前的1095天内转化的用户所产生的事件。<br /><br />**请注意**：在本地时区中，某一天尚未开始时，则该日按本地时区版本化的报告中不会呈现数据。 |
| 报告结构 | 报告结构（即其中的维度和指标）是固定的，无法更改。 |
| 数据时效性 | <ul><li>一天更新多次，每数小时发送一次报告。</li><li>报告提供当日数据。举例来说，4月28日内每个版本的报告都包含4月28日当天截至该版本创建时间为止的所有可用数据。[详情请见此处说明。](/docs/advanced-aggregated-reports-in-data-locker#报告版本和数据时效性-1)</li></ul> |
| 时区 | 除UTC以外的任何时区。也就是说，如果某应用在AppsFlyer平台内将时区设置为UTC，则该报告中不会包含此应用所产生的数据。 |
| 目录与文件名结构 | [详情请见此处说明。](/docs/advanced-aggregated-reports-in-data-locker#报告结构-1) |
| 渠道的数据保存期限 | 有些渠道设有数据保存期限。这种情况下，在数据保存期限之后发生的事件不会出现在群组报告中。<br /><br />举例说明：SRN A的数据保存期限为180天。第180天之前发生的用户事件会被归因到SRN A，第180天之后发生的事件会被忽略。<br /><br />**请注意**：这些事件在总览面板中显示为自然量。 |

<div id="report-structure-1" />

### 报告结构

报告由不同的维度和指标组成。

具体的字段格式如下：

* **维度**：以字符串格式呈现，长度不定，一般取决于广告层级的填充方式。
* **指标**：以数字的形式呈现。**请注意：** selected\_currency字段以字符串的格式呈现。  
  可用指标为收入、完成某事件的独立用户数以及事件发生次数。ROI、ROAS等成本指标的计算需要同时用到收入和成本数据。收入数据可通过群组报告获取，而成本数据则需使用<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL。</Anchor>

<div id="dimensions-1" />

#### 维度

<Table>
  <thead>
    <tr>
      <th>
        字段名称
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        可能出现的值：install（激活）、install-unified（统一视图报告中的激活）、re-engagement（再互动）、re-attribution（再归因）
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        可能出现的值包括click（点击）、impression（展示）、pre-installed（预装）、unknown（未知）、tv、null
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        * 转化后的天数（不是实际转化的时间戳）
        * 小贴士：您可以使用该数据来计算留存和KPI天数。
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        * 用户完成某个事件的日期。
        * 格式：yyyy-mm-dd
        * 举例来说，用户完成某个应用内事件的日期。
        * 请注意：如果event\_name是af\_conversion，则事件日期与转化日期相同。
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        * 转化发生的日期
        * 格式：yyyy-mm-dd
        * 举例来说，激活日期
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        用于标识事件。有些事件名称具有特定含义，而有些则与广告主在应用中设置的应用内事件有关。 

        | event\_name | 用户行为 |
        | --- | --- |
        | af\_conversion | 用户转化。使用conversion\_type来识别转化类型，即激活、再互动、再归因或再互动。 |
        | af\_session | 用户打开应用 |
        | cohort\_uninstalls | 用户卸载应用 |
        | 广告主定义的应用内事件 | 用户完成指定应用内事件。 |
      </td>
    </tr>
    <tr>
      <td>
        event\_timezone
      </td>
      <td>
        表示以下参数的时区：

        * days\_post\_atribution
        * event\_date
        * conversion\_date
      </td>
    </tr>
    <tr>
      <td>
        campaign
      </td>
      <td>
        广告层次结构中的一个层级

        需注意：不支持更改广告系列名称。也就是说，如果您更改了广告系列名称，就会出现多个广告系列名称对应同一个广告系列ID的现象。
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        adset
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        ad
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        channel
      </td>
      <td>
        广告层次结构中的一个层级。

        【2021年10月27日更新】目前Meta ads不在channel字段中填充来自Google Install Referrer机制的数据。
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        广告层次结构中的一个层级
      </td>
    </tr>
    <tr>
      <td>
        is\_primary\_attribution
      </td>
      <td>
        用于识别再营销数据并去重。
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        基于用户IP地址的ISO国家代码。
      </td>
    </tr>
    <tr>
      <td>
        agency
      </td>
      <td>
        * 支持代理数据透明化。
        * 在代理数据不透明的情况下，如果广告主和代理同时使用同一个广告系列名称进行投放，则报告中会有多行数据显示该名称。但这些数据并不是重复数据，所以不必担心。
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        仅适用于安卓应用：用于表达用户下载相关应用的安卓商店。使用<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution">第三方安卓应用商店归因方案</Anchor>的广告主会看到这个字段。如果该字段为空，则表示用户从Google Play Store下载应用。
      </td>
    </tr>
    <tr>
      <td>
        keywords
      </td>
      <td>
        用户在线搜索时所使用的字词，由广告平台上报。
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        由广告平台返回，
      </td>
    </tr>
  </tbody>
</Table>

<div id="metrics-1" />

#### 指标

| 字段名称 | 说明 | 格式 |
| --- | --- | --- |
| unique\_users | 当日完成相关事件的独立用户数。 | 数字 |
| revenue\_usd | <ul><li>以USD为单位的收入数额。如100.56美元会显示为100.56。</li><li>最多精确到小数点后2位。</li></ul> | 数字 |
| event\_count | 事件发生次数 | 数字 |
| selected\_currency | 3字母货币代码（如USD、EUR等），由广告主在AF后台的应用设置页面中配置。完整列表请参考<Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>。这里的货币与AF群组面板中收入指标的货币单位一致。 | 字符串 |
| revenue\_selected\_currency | <ul><li>以指定货币为单位的收入数额。假设指定货币为EUR，则1234.56欧元会显示为1234.56。</li><li>最多精确到小数点后2位。</li></ul> | 数字 |
| first\_inapp | <ul><li>转化后首次完成相关应用内事件的用户数量。</li><li>将first\_inapp指标加总后可得出该事件的累计独立用户数。</li></ul> | 数字 |

<div id="directory-and-filename-structure-1" />

#### 目录与文件名结构

构成报告路径的文件夹结构如下：

格式：`/t=cohort_unified_timezone_versioned/dt=/version=/`

<div id="report-folder-hierarchy-1" />

#### 报告文件夹的层次结构

在广告主的数据存储桶中，按本地时区版本化的群组数据报告的文件夹结构如下方样例所示：

```
bucket
|
└── t=cohort_unified_timezone_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**说明：**

* **dt**：报告中的事件发生的日期。
* **t**：报告类型。
* **version**：相关版本的创建时间，以Unix时间戳表达。

<div id="report-versions-and-data-freshness-1" />

### 报告版本和数据时效性

* 一天更新多次，每数小时发送一次报告。
* 报告中包含当前可用的所有当日数据。举例来说，4月28日内每个版本的报告都包含4月28日当天截至该版本创建时间为止的所有可用数据。
* 该报告的使用场景取决于您所在的国家/地区和时区。[详情请见此处说明。](/docs/advanced-aggregated-reports-in-data-locker#timezone-geos)
* **建议您总是导入最近期的那一版数据。**

| 版本 | AppsFlyer接收数据的截止时间（以UTC时区为准） | 使用场景 | 报告制作完毕的时间（以UTC时区为准） |
| --- | --- | --- | --- |
| 1 | 第1天凌晨4点 | 东部地区 - 第0天的部分数据 | 第1天上午8点 |
| 2 | 第1天上午8点 | 东部地区 - 第0天的部分数据 | 第1天下午1点 |
| 3 | 第1天中午12点 | 东部地区 - 第0天的部分数据 | 第1天下午6点 |
| 4 | 第1天下午4点 | 东部地区 - 第0天的部分数据 | 第1天晚上9点 |
| 5 | 第1天晚上8点 | 东部地区 - 第0天的部分数据 | 第1天晚上11:59 |
| 6 | 第1天晚上11:59 | 东部和中部地区 - 第0天的部分数据 | 第0天凌晨4点 |
| 7 | 第0天凌晨4点 | 所有地区 - 第0天的部分数据 | 第0天上午8点 |
| 8 | 第0天上午8点 | 所有地区 - 第0天的部分数据 | 第0天下午1点 |
| 9 | 第0天中午12 点 | 所有地区 - 第0天的部分数据 | 第0天下午6点 |
| 10 | 第0天下午4点 | 所有地区 - 第0天的部分数据 | 第0天晚上9点 |
| 11 | 第0天晚上8点 | <ul><li>东部地区 - 第0天完整的转化和应用内事件数据</li><li>中部和西部地区 - 第0天的部分数据</li></ul> | 第0天晚上11:59 |
| 12 | 第0天晚上11:59 | 中部和西部地区 - 第0天的部分数据 | 第1天凌晨4点 |
| 13 | 第1天凌晨4点 | <ul><li>中部地区 - 第0天完整的转化和应用内事件数据</li><li>西部地区 - 第0天的部分数据</li><li>通过S2S发送的当前所有可用广告收入数据</li></ul> | 第1天上午8点 |
| 14 | 第1天上午8点 | 西部地区 - 第0天完整的转化和应用内事件数据，以及通过S2S发送的所有当前可用广告收入数据。 | 第1天下午1点 |
| 15 | 第1天中午12点 |  | 第1天下午6点 |
| 16 | 第1天中午12点 |  | 第1天下午6点 |
| 17 | 第1天下午4点 | 西部地区 - 第0天完整的转化和应用内事件数据，以及通过S2S发送的所有当前可用广告收入数据。 | 第1天晚上9点 |
| 18 | 第1天下午6点 | 西部地区 - 第0天完整的转化和应用内事件数据，以及通过S2S发送的所有当前可用广告收入数据。 | 第1天晚上11:59 |
| 19 | 第1天晚上8点 | 西部地区 - 第0天完整的转化和应用内事件数据，以及通过S2S发送的完整广告收入数据。 | 第1天晚上11:59 |
| 20 | 第1天晚上11:59 | 第0天完整的转化和应用内事件数据，以及通过S2S发送的完整广告收入数据，这些数据已经根据变现平台侧可能出现的任何问题进行了调整。 | 第2天凌晨4点 |
| 21 | 第8天午夜00:00 | 第0天完整的转化和应用内事件数据，以及通过S2S发送的完整广告收入数据，这些数据已经根据变现平台侧可能出现的任何问题进行了调整。 | 第8天早上6点 |

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="timezone-geos" />

<Accordion title="时区及国家/地区">

该报告的使用场景取决于您所在的国家/地区和时区。下表列出了国家/地区与时区的对应关系，供您参考。

| 国家/地区 | 时区 |
| --- | --- |
| 东部 | UTC+12 - UTC+3 |
| 中部 | UTC+2.5 - UTC-3 |
| 西部 | UTC-3.5 - UTC-12 |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="BI开发人员的注意事项">

**报告中的数据范围**

报告涵盖UA视图的激活、再营销视图的再归因和再互动，及其相关的应用内事件。

您可以将统一、UA和再营销报告分别导入您的BI。或者同时入库但需要筛选不同视图的数据：

* 对于统一视图，请使用is\_primary\_attribution=true或null字段。
* 对于UA视图，请使用conversion\_type=Install。
* 对于再营销视图，请使用conversion\_type=re-engagement或re-attribution。

如果您仅使用统一视图查看数据，可以运用逻辑来拆分不同投放类型所对应的数据，即用户归因（激活）及再营销（再互动）。具体操作时请根据实际需求将conversion\_type设置为install、install\_unified、re-engagement或re-attribution。另请参见<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">再营销事件的双重归因</Anchor>。

**字段级注意事项**

* 您可以通过归因后的天数来计算留存指标。
* 您可以使用广告系列名称和广告系列ID这两个维度来计算独立用户数：在不用考虑广告系列名称颗粒度的情况下，将广告系列ID的独立用户数相加可以得出准确的指标。
* 您可以使用广告层次结构字段来汇总数据。
* 以美元为单位的收入指标是根据事件当天的汇率计算的。

**常规注意事项**

AppsFlyer支持所有应用的数据配置，您可以将多个应用的数据合并到一个文件中，也可以分应用单独取数。

</Accordion>

<div id="use-cases" />

<Accordion title="使用场景">

本节列举了一些通过Data Locker拉取数据并用于BI的常见使用场景，且每个示例都配以相关的SQL语句及Excel表格数据作为详细说明。

<div id="1-calculate-retention" />

#### **1. 计算留存率**

在这个示例中，我们需要完成以下工作：

* 计算Day 1（转化次日）和Day7的留存率，以及分广告系列和广告素材的总体激活数量。
* 将`event_name`设定为`af_conversion`，按转化事件统计事件总数。
* 将数据筛选条件设置为`conversion_type=install`，重点分析拉新广告的数据。

**SQL语句**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as installs,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified', 'retargeting', 'reattr')
    and conversion_type = 'install'
    and app_id = YOUR_APP
group by 1,2
```

**Excel表格示例**

| Campaign ID （广告系列ID） | Ad ID （广告ID） | Installs （激活） | Retention Day 1 （次留） | Retention Day 7 （周留） |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30% | 10% |
| 98765432 | 123456 | 200 | 25% | 15% |
| 07315466 | 613770 | 300 | 20% | 12% |

<div id="2-calculate-arpu-of-multiple-in-app-events" />

#### **2. 计算多个应用内事件的ARPU**

在这个示例中，我们需要完成以下工作：

* 分广告系列计算多个应用内事件的ARPU。
* 将数据筛选条件设置为`conversion_type=re-engagement`和`conversion_type=re-attribution`，重点分析再营销广告的数据。
* 将`event_name`设定为`af_conversion`，按转化事件统计事件总数。
* 统计多个事件（在本场景中为`af_purchase`和`af_coins`）的总体收入。
* 将`days_post_attribution`设为您所需的最低值（在本场景中为7），这是为了减轻数据处理量。

**SQL语句**

```sql
select
    campaign_id,
    sum(if(days_post_attribution <= 1 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day1,
    sum(if(days_post_attribution <= 3 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day3,
    sum(if(days_post_attribution <= 7 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and days_post_attribution <= 7
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')
    and conversion_type in ('re-engagement', 're-attribution')
    and app_id = YOUR_APP
group by 1
```

**Excel表格示例**

| Campaign ID （广告系列ID） | Conversion type （转化类型） | ARPU<br /><br />Day 1 | ARPU<br /><br />Day 3 | ARPU<br /><br />Day 7 |
| --- | --- | --- | --- | --- |
| 12345678 | re-engagement | 6.23 | 5.11 | 2.34 |
| 98765432 | re-engagement | 3.57 | 1.34 | 4.86 |
| 07315466 | re-attribution | 7.41 | 6.79 | 5.29 |

<div id="3-calculate-in-app-event-conversion-rate-for-a-specific-cohort-day" />

#### **3. 针对具体的群组日期计算应用内事件的转化率**

在这个示例中，我们需要完成以下工作：

* 分多个维度（本场景中为转化日期、国家/地区、广告系列、广告素材和子渠道）计算Day0（转化当日）的应用内事件转化率。
* 将数据筛选条件设置为`is_primary_attribution=true`，分析统一维度的数据（即同时包含UA和再营销广告）。
* 将`event_name`设定为`af_conversion`，按转化事件统计事件总数。
* 将`days_post_attribution`设为您所需的最低值（在本场景中为7），这是为了减轻数据处理量。

**SQL语句**

```sql
select
    conversion_date, geo, campaign_id, ad_id, site_id,
    sum(if(days_post_attribution = 0 and event_name = 'af_complete_tutorial', unique_users, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as day0_af_tutorial_conversion
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and is_primary_attribution = true
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excel表格示例**

| Conversion date（转化日期） | Geo （国家/地区） | Campaign ID （广告系列ID） | Ad ID （广告ID） | Site ID （子渠道ID） | Day 0 af\_complete\_tutorial （当日教程完成率） |
| --- | --- | --- | --- | --- | --- |
| 2022-11-07 | US | 12345678 | 123456 | site\_123 | 45% |
| 2022-11-05 | UK | 98765432 | null | site\_654 | 70% |
| 2022-10-31 | KR | 07315466 | null | null | 63% |

<div id="4-calculate-daily-installs" />

#### **4. 计算每日激活量**

在这个示例中，我们需要完成以下工作：

* 分应用ID、转化日期、媒体渠道、事件名称和转化类型计算激活数量。
* 将`conversion_type`设定为`install`，从而筛选出UA激活（排除再营销）。
* 将`event_name`设定为`af_conversion`，对激活量进行加总。

**SQL语句**

```sql
select
    app_id,
    conversion_date,
    media_source,
    event_name,
    conversion_type,
    sum(events_count) as total
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and event_name = 'af_conversion'
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excel表格示例**

| App ID （应用ID） | Conversion date（转化日期） | Media source （媒体渠道） | Event name （事件名称） | Total （总计） |
| --- | --- | --- | --- | --- |
| id123456789 | 2022-11-07 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 2022-11-05 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 2022-10-31 | adnet3\_int | af\_conversion | 327 |

<div id="5-calculate-revenue-from-facebook-ads" />

#### **5. 计算由Facebook Ads带来的收入**

在这个示例中，我们需要完成以下工作：

* 按转化日期和应用ID计算Day 3的Facebook收入。
* 将数据筛选条件设置为`media_source='Facebook Ads'`，分析Facebook的数据。
* 将`days_post_attribution`设为您所需的最低值（在本场景中为3），这是为了减轻数据处理量。

**SQL语句**

```sql
select
    conversion_date,
    app_id,
    media_source,
    sum(if(days_post_attribution <= 3, revenue_usd, 0)) as revenue_day3
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and days_post_attribution <= 3
    and media_source = 'Facebook Ads'
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3
```

**Excel表格示例**

| Conversion date（转化日期） | App ID （应用ID） | Media source （媒体渠道） | Revenue （收入）<br /><br />Day 3 |
| --- | --- | --- | --- |
| 2022-11-07 | id123456789 | adnet1\_int | 400.45 |
| 2022-11-05 | id123456789 | adnet2\_int | 99.23 |
| 2022-10-31 | id123456789 | adnet3\_int | 13.34 |

<div id="6-calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days" />

#### **6. 分ASA关键词ID计算365天以内的ARPU**

在这个示例中，我们需要完成以下工作：

* 分关键词ID计算ASA的ARPU，以群组日期第365天为截止日期。
* 将数据筛选条件设置为`media_source='Apple Search Ads'`，分析ASA的数据。
* 将`event_name`设定为`af_conversion`，按转化事件统计事件总数。

**SQL语句**

```sql
select
    media_source,
    keyword_id,
    sum(if(days_post_attribution <= 365, revenue_usd,0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day365
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and media_source = 'Apple Search Ads'
    and app_id = YOUR_APP
group by 1
```

**Excel表格示例**

| Media source （媒体渠道） | Keyword ID （关键词ID） | ARPU<br /><br />Day 365 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57,019.93 |
| adnet2\_int | 987654 | 64,867.84 |
| adnet3\_int | 666854 | 48,160.02 |

<div id="7-calculate-arpu-days-7-by-attribution-time-per-geo" />

#### **7. 分国家/地区按归因时间计算7日ARPU**

下文示例说明了<Anchor target="_blank" href="/marketers/zh/docs/cohort-and-retention-dashboard#trend-type%E2%80%94kpi-by-attribution-time">归因时间KPI</Anchor>的使用方式。在这个示例中，我们需要完成以下工作：

* 分国家/地区按归因日期计算7日ARPU。
* 按转化数量对结果排序，表格显示前20个国家/地区。
* 将数据筛选条件设置为`conversion_type='install'`。
* 表格第一列显示国家/地区，第二列显示总体转化量，之后各列显示查询参数指定日期的7日收入。

**SQL语句**

```sql
select
    geo,
    sum(if(event_name = 'af_conversion', event_count, 0)) total_conversions,
    sum(if(cohort_day = '2023-07-11' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-11' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_11,
    sum(if(cohort_day = '2023-07-12' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-12' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_12,
    sum(if(cohort_day = '2023-07-13' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-13' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_13,
    sum(if(cohort_day = '2023-07-14' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-14' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_14,
    sum(if(cohort_day = '2023-07-15' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-15' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_15,
    sum(if(cohort_day = '2023-07-16' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-16' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_16
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-07-11' and '2023-07-16'
    and days_post_attribution <= 7
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')    
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Excel表格示例**

| Geo （国家/地区） | Total conversions （转化总量） | ARPU Day 7 for 2023-07-11 （2023年7月11日的第7天ARPU，后同） | ARPU Day 7 for 2023-07-12 | ARPU Day 7 for 2023-07-13 | ARPU Day 7 for 2023-07-14 | ARPU Day 7 for 2023-07-15 | ARPU Day 7 for 2023-07-16 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| South Korea | 120,660 | $7,798.89 | $6,997.37 | $8,258.95 | $9,050.21 | $10,018.04 | $13,765.73 |
| Canada | 35,099 | $64,867.84 | $7,050.19 | $5,656.33 | $9,553.75 | $8,632.41 | $11,308.06 |
| Chile | 26,750 | $48,160.02 | $21,249.55 | $22,584.57 | $24,033.07 | $31,118.91 | $41,145.22 |

<div id="8-calculate-purchases-day-7-after-conversion" />

#### **8. 计算转化后第7天的购买事件数量**

在这个示例中，我们需要完成以下工作：

* 计算在转化后7天内完成af\_purchase事件的累计独立用户数（统一视图）。
* 计算该事件的转化率，即转化后7天内完成购买的用户所占的比例。
* 将数据筛选条件设置为`conversion_type='install'`。
* 按应用、转化日期、媒体渠道、广告系列和广告组将数据分组。

**SQL语句**

```sql
select
    app_id, conversion_date, media_source, campaign, adset,
    sum(if(event_name = 'af_conversion', event_count,0)) as unified_conversions,
    sum(if(event_name = 'af_purchase', first_inapp, 0)) as af_purchase_day_7_cumulative_unique_users,
    concat(
        cast(
            round(
                sum(if(event_name = 'af_purchase', first_inapp, 0)) /
                sum(if(event_name = 'af_conversion', event_count, 0)) * 100.0
            ,2)
        as varchar),
    '%') as af_purchase_day_7_cumulative_unique_users_conversion_rate
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-12-01' and '2023-12-31'
    and is_primary_attribution = true
    and days_post_attribution <= 7
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3,4,5
```

**Excel表格示例**

| App ID （应用ID） | Conversion date（转化日期） | Media source | Campaign | Adset | Unified conversions | D7 af\_purchase cumulative | D7 af\_purchase conversion rate |
| --- | --- | --- | --- | --- | --- | --- | --- |
| id123456789 | 2024-03-05 | adnet1\_int | campaign\_1 | adset\_1 | 100 | 20 | 20% |
| id123456789 | 2024-03-07 | adnet2\_int | campaign\_2 | adset\_2 | 200 | 10 | 5% |
| id123456789 | 2024-03-31 | adnet3\_int | campaign\_3 | adset\_3 | 150 | 15 | 10% |

<div id="9-calculate-dau" />

#### **9. 计算DAU**

在这个示例中，我们需要完成以下工作：

* 按媒体渠道、广告系列和广告对数据分组，计算选定时段各天的DAU。
* 将数据筛选条件设置为`event_name = 'af_session'`。
* 分天依次将独立用户加总，每个日期单独为一个维度（即各个日期分列呈现）。

**请注意**：

* 不能计算多天数据的总和（比如为了计算WAU或MAU）。
* DAU以过去1095天内转化的用户所产生的行为数据为基础，这与活跃数据面板和报告中的数据不同，活跃数据没有这一限制。详情请见[特点和局限性](/docs/advanced-aggregated-reports-in-data-locker#traits-and-limitations)部分的“转化后天数”一行的说明。

**SQL语句**

```sql
select
media_source,campaign_id, ad_id,
sum(case when event_date = '2024-08-06' then unique_users end) as dau_2024_08_06,
sum(case when event_date = '2024-08-07' then unique_users end) as dau_2024_08_07,
sum(case when event_date = '2024-08-08' then unique_users end) as dau_2024_08_08
from YOUR_DATA_LOCKER_REPORT
where event_date between '2024-08-06' and '2024-08-08'
and event_name = 'af_session'
and app_id = YOUR_APP
group by 1,2,3
```

**Excel表格示例**

| Media source | Campaign | Ad | DAU August 6 | DAU August 7 | DAU August 8 |
| --- | --- | --- | --- | --- | --- |
| adnet1\_int | campaign\_1 | adset\_1 | 475,250 | 420,485 | 463,912 |
| adnet2\_int | campaign\_2 | adset\_2 | 380,987 | 355,665 | 401,232 |
| adnet3\_int | campaign\_3 | adset\_3 | 290,042 | 570,322 | 489,787 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 |  |
| --- | --- |
| 成本数据 | <ul><li>不支持。<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports">需使用Cost ETL</Anchor>才能获得成本数据。</li><li>另请参阅<Anchor target="_blank" href="/marketers/zh/docs/combine-cost-etl-and-cohort-reports-via-data-locker">合并Cost ETL和群组报告</Anchor>的说明。</li></ul> |
| 广告系列名称变更 | 不支持。如果广告系列名称发生变更，请使用广告系列ID对数据进行分组和筛选。 |
| 数据时效性 | 一天多次 |
| 广告收入 | 可用 |
| 货币 | 可分行显示USD和应用层级指定货币的收入数据 |
| 时区 | 按本地时区版本化的报告可以使用应用配置中设定的时区。 |
| 自然量数据 | 可用 |
| 支持转化（激活、再归因、再互动）后天数 | 最多可支持到1095天。 |
| 代理数据透明化 | <ul><li>支持</li><li>X Ads和Meta ads数据总是对广告主可见</li></ul> |
| 分应用取数 | 支持 |
| SKAN数据 | 不包含。这些数据来自iOS回传，Data Locker报告不提供此类数据。 |
| 卸载数据 | AppsFlyer每天处理一次卸载数据。因此，这些数据仅会出现在包含完整数据（而非部分数据）的报告中。 |
| 重装激活 | <ul><li>如果重装激活发生后的事件被记录为未归因的自然量：<ul><li>2024年5月26日之后的报告不呈现该数据。<Anchor target="_blank" href="/marketers/zh/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">详情请见此处说明。</Anchor></li><li>激活时间以<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>字段的值为准。</li><li>不计入独立用户数和留存指标。</li></ul></li><li>如果重装激活后发生的事件被归因到首次激活，则报告中总是包含该数据。<Anchor target="_blank" href="/marketers/zh/docs/unique-users">详情请见此处说明。</Anchor></li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/combine-cost-etl-and-cohort-reports-via-data-locker">合并Cost ETL与高级汇总群组报告</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/cohort-and-retention-dashboard">群组面板</Anchor>

<div data-zendesk-anchors="advanced-aggregated-reports-in-data-locker=data-locker%E4%B8%AD%E7%9A%84%E9%AB%98%E7%BA%A7%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A h_01HWWH83KNSF4BRGTDJ0JD271G=data-locker%E4%B8%AD%E7%9A%84%E9%AB%98%E7%BA%A7%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A setup=%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01HWWH83KN9CM7ZY43W01AV6TA=%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F reports-available=%E5%8F%AF%E7%94%A8%E6%8A%A5%E5%91%8A h_01HWWNY76W6RFKX33MXHE4GSBD=%E5%8F%AF%E7%94%A8%E6%8A%A5%E5%91%8A h_01HWWNR256DRMBNFX3NV8ATNAY=cohort-versioned-report report-facts=%E8%AF%A6%E6%83%85%E8%AF%B4%E6%98%8E h_01HVRBVXS47K91A6KVV33S1BY6=%E8%AF%A6%E6%83%85%E8%AF%B4%E6%98%8E report-structure=%E6%8A%A5%E5%91%8A%E7%BB%93%E6%9E%84 h_01HWWH83KNE46SPK1MS99XX64D=%E6%8A%A5%E5%91%8A%E7%BB%93%E6%9E%84 dimensions=%E7%BB%B4%E5%BA%A6 01H7WG3CA14PQ2PJ58FX8TE6ZH=%E7%BB%B4%E5%BA%A6 metrics=%E6%8C%87%E6%A0%87 01H7WG3CA24VQKFVP99S82GCXZ=%E6%8C%87%E6%A0%87 directory-and-filename-structure=%E7%9B%AE%E5%BD%95%E4%B8%8E%E6%96%87%E4%BB%B6%E5%90%8D%E7%BB%93%E6%9E%84 h_01HVRDKKQA17SMJFFAEDG7A2X2=%E7%9B%AE%E5%BD%95%E4%B8%8E%E6%96%87%E4%BB%B6%E5%90%8D%E7%BB%93%E6%9E%84 the-report-folder-hierarchy-in-aws=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84 h_01HETBAQVVA750VTE1ABSM2M47=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84 report-versions-and-data-freshness=%E6%8A%A5%E5%91%8A%E7%89%88%E6%9C%AC%E5%92%8C%E6%95%B0%E6%8D%AE%E6%97%B6%E6%95%88%E6%80%A7 h_01HWWH83KN51RR2VJ2F5N8YQ3J=%E6%8A%A5%E5%91%8A%E7%89%88%E6%9C%AC%E5%92%8C%E6%95%B0%E6%8D%AE%E6%97%B6%E6%95%88%E6%80%A7 h_01HWWNVFCWJ7DZCKKKSBMH9NM5=cohort-timezone-versioned-report report-facts::15e071f=%E8%AF%A6%E6%83%85%E8%AF%B4%E6%98%8E-1 h_01HWWH83KNPZETHR2TQS2E4QNT=%E8%AF%A6%E6%83%85%E8%AF%B4%E6%98%8E-1 report-structure::43ffff28=%E6%8A%A5%E5%91%8A%E7%BB%93%E6%9E%84-1 h_01HWWH83KNG0V2ZMZZ7CTV2GE7=%E6%8A%A5%E5%91%8A%E7%BB%93%E6%9E%84-1 01HWSX3FA0K39D9M5RQ7J36Q23=%E7%BB%B4%E5%BA%A6-1 01HWSX3FA035Z8W6EPV4Q6E3JP=%E6%8C%87%E6%A0%87-1 01HWSX3FA189EMBJZ1P21YHC45=%E7%9B%AE%E5%BD%95%E4%B8%8E%E6%96%87%E4%BB%B6%E5%90%8D%E7%BB%93%E6%9E%84-1 01HX97NC4F2WCJABSM2NBSBEDN=%E6%8A%A5%E5%91%8A%E6%96%87%E4%BB%B6%E5%A4%B9%E7%9A%84%E5%B1%82%E6%AC%A1%E7%BB%93%E6%9E%84-1 report-versions-and-data-freshness::e0755e26=%E6%8A%A5%E5%91%8A%E7%89%88%E6%9C%AC%E5%92%8C%E6%95%B0%E6%8D%AE%E6%97%B6%E6%95%88%E6%80%A7-1 h_01HWWH83KPS2ANCQKS2B3V529Z=%E6%8A%A5%E5%91%8A%E7%89%88%E6%9C%AC%E5%92%8C%E6%95%B0%E6%8D%AE%E6%97%B6%E6%95%88%E6%80%A7-1 additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HWWH83KPK8535X9EBZVJ9SQK=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HWWN6GAAD75HPC5GTE40QA37=timezone-geos 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-Calculate-retention=1-%E8%AE%A1%E7%AE%97%E7%95%99%E5%AD%98%E7%8E%87 h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-%E8%AE%A1%E7%AE%97%E7%95%99%E5%AD%98%E7%8E%87 2-Calculate-arpu-of-multiple-inapp-events=2-%E8%AE%A1%E7%AE%97%E5%A4%9A%E4%B8%AA%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84arpu h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-%E8%AE%A1%E7%AE%97%E5%A4%9A%E4%B8%AA%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84arpu 3-Calculate-inapp-event-conversion-rate-for-a-specific-cohort-day=3-%E9%92%88%E5%AF%B9%E5%85%B7%E4%BD%93%E7%9A%84%E7%BE%A4%E7%BB%84%E6%97%A5%E6%9C%9F%E8%AE%A1%E7%AE%97%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84%E8%BD%AC%E5%8C%96%E7%8E%87 h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-%E9%92%88%E5%AF%B9%E5%85%B7%E4%BD%93%E7%9A%84%E7%BE%A4%E7%BB%84%E6%97%A5%E6%9C%9F%E8%AE%A1%E7%AE%97%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84%E8%BD%AC%E5%8C%96%E7%8E%87 4-Calculate-daily-installs=4-%E8%AE%A1%E7%AE%97%E6%AF%8F%E6%97%A5%E6%BF%80%E6%B4%BB%E9%87%8F h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-%E8%AE%A1%E7%AE%97%E6%AF%8F%E6%97%A5%E6%BF%80%E6%B4%BB%E9%87%8F 5-Calculate-revenue-from-facebook-ads=5-%E8%AE%A1%E7%AE%97%E7%94%B1facebook-ads%E5%B8%A6%E6%9D%A5%E7%9A%84%E6%94%B6%E5%85%A5 h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-%E8%AE%A1%E7%AE%97%E7%94%B1facebook-ads%E5%B8%A6%E6%9D%A5%E7%9A%84%E6%94%B6%E5%85%A5 6-Calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-%E5%88%86asa%E5%85%B3%E9%94%AE%E8%AF%8Did%E8%AE%A1%E7%AE%97365%E5%A4%A9%E4%BB%A5%E5%86%85%E7%9A%84arpu h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-%E5%88%86asa%E5%85%B3%E9%94%AE%E8%AF%8Did%E8%AE%A1%E7%AE%97365%E5%A4%A9%E4%BB%A5%E5%86%85%E7%9A%84arpu Calculate-arpu-days-0-7-by-attribution-time-per-geo=7-%E5%88%86%E5%9B%BD%E5%AE%B6%E5%9C%B0%E5%8C%BA%E6%8C%89%E5%BD%92%E5%9B%A0%E6%97%B6%E9%97%B4%E8%AE%A1%E7%AE%977%E6%97%A5arpu 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-%E5%88%86%E5%9B%BD%E5%AE%B6%E5%9C%B0%E5%8C%BA%E6%8C%89%E5%BD%92%E5%9B%A0%E6%97%B6%E9%97%B4%E8%AE%A1%E7%AE%977%E6%97%A5arpu 8-calculate-purchases-day-7-after-conversion=8-%E8%AE%A1%E7%AE%97%E8%BD%AC%E5%8C%96%E5%90%8E%E7%AC%AC7%E5%A4%A9%E7%9A%84%E8%B4%AD%E4%B9%B0%E4%BA%8B%E4%BB%B6%E6%95%B0%E9%87%8F h_01J7N4VB83T4KZ6G0Q634ASMHV=8-%E8%AE%A1%E7%AE%97%E8%BD%AC%E5%8C%96%E5%90%8E%E7%AC%AC7%E5%A4%A9%E7%9A%84%E8%B4%AD%E4%B9%B0%E4%BA%8B%E4%BB%B6%E6%95%B0%E9%87%8F 9-calculate-dau=9-%E8%AE%A1%E7%AE%97dau h_01J55D2FFW0XSH3G6AXRS06RPV=9-%E8%AE%A1%E7%AE%97dau 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

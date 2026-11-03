---
title: Data Locker的群组分析报告
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2021-10-14T08:46:00Z'
  edited_at: '2026-10-14T10:02:39Z'
  id: 4408945472529
  locale: zh-cn
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/zh-cn/articles/4408945472529
---
> **概要**：Data Locker的群组分析报告覆盖各广告层级的汇总数据，其中包含过去365天内的用户归因数据。即使您未购买Data Locker，只要您的套餐中包含原始数据和/或群组API，就可以获取该报告。

## Data Locker中的群组分析报告

AppsFlyer中的原始归因数据有时会受到媒体渠道数据共享政策或广告主<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">隐私保护政策的</Anchor><Anchor target="_blank" href="/marketers/zh/docs/about-raw-data-identifier-restrictions">限制</Anchor>，这样的限制会影响到所有与归因有关的字段，如广告系列和广告组。这种情况下，您可以使用群组报告以汇总数据的形式来代替原始数据。

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ8q_4xv83wHkl4fs6jndEffRu-RHsPobBRfxDG-bUNXb0pOnvJH4QT0nXKdWvi3JPtVUBegTFbxIEe/pub?output=xlsx">下载示例报告</Anchor>

<div id="enable-data-locker" />

<Accordion title="启用Data Locker">

套餐中包含Data Locker、群组API和原始数据的广告主可以获取该报告。请选择以下任一流程完成相关操作，以启用<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">Data Locker</Anchor>中的群组分析报告。

| 您目前是否通过Data Locker取数 | 流程 |
| --- | --- |
| 是 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)将群组报告添加到Data Locker：<ol><li>从AppsFlyer后台的侧边栏中选择**报告 > Data Locker**。</li><li>全选**Cohort analytics**（群组分析报告）部分的所有报告。</li><li>点击**保存配置**。<br />报告会在第二天的UTC时间10:00之前准备就绪。</li></ol> |
| 否 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**Data Locker的设置方式如下**：<ol><li>完成Data Locker的初始设置（<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers#set-up-data-locker">广告主指南</Anchor>｜<Anchor target="_blank" href="/partners/zh/docs/data-locker-for-partners">渠道指南</Anchor>）。</li><li>将群组报告添加到Data Locker中：<ol><li>从AppsFlyer后台的侧边栏中选择**报告 > Data Locker**。</li><li>全选**Cohort analytics**（群组分析报告）部分的所有报告。</li><li>点击**保存配置**。<br />报告会在第二天的UTC时间10:00之前准备就绪。</li></ol></li></ol> |

</Accordion>

您可以将该数据入库到BI，用于投放效果分析和优化。

**可用指标**

可用指标为收入、完成某事件的独立用户数以及事件发生次数。ROI、ROAS等成本指标的计算需要同时用到收入和成本数据。收入数据可通过群组报告获取，而成本数据则需使用<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL</Anchor>。

<div id="facts" />

<Accordion title="群组分析报告要点简介">

| 可用报告 | 可下载的报告包括以下几种（各类报告的详细介绍请参见<Anchor target="_blank" href="/marketers/zh/docs/cohort-and-retention-dashboard#cohort-principles">群组面板</Anchor>）：<ul><li>**用户获取**：归因到拉新（UA）渠道的LTV数据，包括再互动窗口期内的LTV。</li><li>**再营销**：归因到再营销渠道的LTV数据。分以下两种情况：<ul><li>再互动窗口期内发生的事件</li><li>再归因后发生的事件</li></ul></li><li>**统一**：根据AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">双重归因</Anchor>规则，归因到末次触达渠道的LTV数据。也就是说在统一视图中，再互动LTV数据会显示在再营销渠道下，而不会显示在UA渠道下。</li></ul> |
| --- | --- |
| 报告周期 | 报告涵盖在过去365天内转化的用户。也就是说每一天的报告都包含了在当前日期之前的365天内转化的用户。 |
| 报告结构 | 各个报告的结构（即其中的维度和指标）是固定的，无法更改。详情请见[报告结构](/docs/cohort-analytics-via-data-locker#report-structure)。 |
| 报告传输 | 详情请见[启用Data Locker的群组报告](/docs/cohort-analytics-via-data-locker#enable-data-locker)。 |
| 数据时效性 | <ul><li>每天更新一次，</li><li>根据UTC时间凌晨（即一天结束）时的数据计算指标。</li><li>报告会在UTC时间10:00前更新到Data Locker的日期-时间（dt）文件夹中。比如周一的数据会在UTC时间周二10:00前更新到周一的文件夹中。</li></ul> |
| 渠道的数据保存期限 | 有些渠道设有数据保存期限。对于数据保存期限之后发生的事件，群组报告会将其记录为自然量。<br /><br />举例来说，SRN A的数据保存期限为180天。第180天之前产生的用户事件会归因到SRN A，第180天之后的事件则记录为自然量。 |

</Accordion>

<div id="report-structure" />

<Accordion title="报告结构">

报告由不同的维度和指标组成。

具体的字段格式如下：

* **维度**：以字符串格式呈现，长度不定，一般取决于广告层级的填充方式。
* **指标**：以数字的形式呈现。**请注意：** selected\_currency字段以字符串的格式呈现。

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
        --
      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>
        --
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
        由广告平台上报的关键词ID【该字段自2022年4月27起可用】。
      </td>
    </tr>
  </tbody>
</Table>

#### 指标

| 字段名称 | 说明 | 格式 |
| --- | --- | --- |
| unique\_users | 当日完成相关事件的独立用户数。 | 数字 |
| revenue\_usd | <ul><li>以USD为单位的收入数额。如100.56美元会显示为100.56。</li><li>最多精确到小数点后2位。</li></ul> | 数字 |
| event\_count | 事件发生次数 | 数字 |
| selected\_currency | 3字母货币代码（如USD、EUR等），由广告主在AF后台的应用设置页面中配置。完整列表请参考<Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>。这里的货币与AF群组面板中收入指标的货币单位一致。 | 字符串 |
| revenue\_selected\_currency | <ul><li>以指定货币为单位的收入数额。假设指定货币为EUR，则1234.56欧元会显示为1234.56。</li><li>最多精确到小数点后2位。</li></ul> | 数字 |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="BI开发者注意事项">

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
* 在有可用数据时，报告会包含广告收入事件，但可能会有最长3天的更新延时。

**常规注意事项**

报告会将所有应用的数据都集中在一个文件中。您可以使用App ID字段来区分各应用的数据，或将Data Locker设置为按应用区分。

</Accordion>

<div id="use-cases" />

<Accordion title="使用场景">

本节列举了一些通过Data Locker拉取群组数据用于BI的常见使用场景，且每个示例都配以相关的SQL语句及Excel表格数据作为详细说明。

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
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')    
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

#### **4. 计算每天的激活量**

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

#### **5.计算由Facebook Ads带来的收入**

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

#### **6.分ASA关键词ID计算365天以内的ARPU**

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

</Accordion>

## 其他相关信息

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 |  |
| --- | --- |
| 成本数据 | <ul><li>不支持。<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports">需使用Cost ETL</Anchor>才能获得成本数据。</li><li>另请参阅<Anchor target="_blank" href="/marketers/zh/docs/combine-cost-etl-and-cohort-reports-via-data-locker">合并Cost ETL和群组报告</Anchor>的说明。</li></ul> |
| 广告系列名称变更 | 不支持。 |
| 数据时效性 | 每天更新（按UTC时间计算）。报告会在次日UTC时间10:00前更新到Data Locker，放在报告当天的日期-时间（dt）文件夹中。 |
| 广告收入 | <ul><li>可用</li><li>对于af\_ad\_revenue事件，2022年10月5日到2023年2月16日之间的独立用户指标不可用。</li></ul> |
| 货币 | 可分行显示USD和应用层级指定货币的收入数据 |
| 时区 | <ul><li>UTC</li><li>您可以在<Anchor target="_blank" href="/marketers/zh/docs/advanced-aggregated-reports-in-data-locker">按本地时区版本化的高级汇总群组报告</Anchor>中使用应用配置的指定时区。</li></ul> |
| 自然量数据 | 可用 |
| 转化后天数（激活、再归因、再互动） | <ul><li>数据可用范围为激活后的365天内。</li><li><Anchor target="_blank" href="/marketers/zh/docs/advanced-aggregated-reports-in-data-locker">高级汇总报告</Anchor>的数据可用范围为激活后的1095天。</li></ul> |
| 代理数据透明化 | <ul><li>支持</li><li>X Ads和Meta ads数据总是对广告主可见</li></ul> |
| 分应用取数 | 支持 |
| SKAN数据 | 不包含。SKAN数据是指由iOS回传提供的数据。 |
| 重装激活 | <ul><li>如果重装激活发生后的事件被记录为未归因的自然量：<ul><li>2024年5月26日之后的报告不呈现该数据。<Anchor target="_blank" href="/marketers/zh/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">详情请见此处说明。</Anchor></li><li>激活时间以<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>字段的值为准。</li><li>不计入独立用户数和留存指标。</li></ul></li><li>如果重装激活后发生的事件被归因到首次激活，则报告中总是包含该数据。<Anchor target="_blank" href="/marketers/zh/docs/unique-users">详情请见此处说明。</Anchor></li></ul> |

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/combine-cost-etl-and-cohort-reports-via-data-locker">合并Cost ETL和群组报告</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/cohort-and-retention-dashboard">群组面板</Anchor>

<div data-zendesk-anchors="cohort-analytics-in-data-locker=data-locker%E4%B8%AD%E7%9A%84%E7%BE%A4%E7%BB%84%E5%88%86%E6%9E%90%E6%8A%A5%E5%91%8A 01H7WG3CA1DDAN79D1PBPE0RJ3=data-locker%E4%B8%AD%E7%9A%84%E7%BE%A4%E7%BB%84%E5%88%86%E6%9E%90%E6%8A%A5%E5%91%8A 01H7WG3CA1ZMNTGZ5B8FNXNC4A=enable-data-locker 01H7WG3CA179D6VCWYPCJ1G49M=facts 01H7WG3CA1R3PZCKSGWC90E7RC=report-structure dimensions=%E7%BB%B4%E5%BA%A6 01H7WG3CA14PQ2PJ58FX8TE6ZH=%E7%BB%B4%E5%BA%A6 metrics=%E6%8C%87%E6%A0%87 01H7WG3CA24VQKFVP99S82GCXZ=%E6%8C%87%E6%A0%87 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-calculating-retention=1-%E8%AE%A1%E7%AE%97%E7%95%99%E5%AD%98%E7%8E%87 h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-%E8%AE%A1%E7%AE%97%E7%95%99%E5%AD%98%E7%8E%87 2-calculating-arpu-of-multiple-inapp-events=2-%E8%AE%A1%E7%AE%97%E5%A4%9A%E4%B8%AA%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84arpu h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-%E8%AE%A1%E7%AE%97%E5%A4%9A%E4%B8%AA%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84arpu 3-calculating-inapp-event-conversion-rate-for-a-specific-cohort-day=3-%E9%92%88%E5%AF%B9%E5%85%B7%E4%BD%93%E7%9A%84%E7%BE%A4%E7%BB%84%E6%97%A5%E6%9C%9F%E8%AE%A1%E7%AE%97%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84%E8%BD%AC%E5%8C%96%E7%8E%87 h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-%E9%92%88%E5%AF%B9%E5%85%B7%E4%BD%93%E7%9A%84%E7%BE%A4%E7%BB%84%E6%97%A5%E6%9C%9F%E8%AE%A1%E7%AE%97%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E7%9A%84%E8%BD%AC%E5%8C%96%E7%8E%87 4-calculating-daily-installs=4-%E8%AE%A1%E7%AE%97%E6%AF%8F%E5%A4%A9%E7%9A%84%E6%BF%80%E6%B4%BB%E9%87%8F h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-%E8%AE%A1%E7%AE%97%E6%AF%8F%E5%A4%A9%E7%9A%84%E6%BF%80%E6%B4%BB%E9%87%8F 5-calculating-revenue-from-facebook-ads=5%E8%AE%A1%E7%AE%97%E7%94%B1facebook-ads%E5%B8%A6%E6%9D%A5%E7%9A%84%E6%94%B6%E5%85%A5 h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5%E8%AE%A1%E7%AE%97%E7%94%B1facebook-ads%E5%B8%A6%E6%9D%A5%E7%9A%84%E6%94%B6%E5%85%A5 6-calculating-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6%E5%88%86asa%E5%85%B3%E9%94%AE%E8%AF%8Did%E8%AE%A1%E7%AE%97365%E5%A4%A9%E4%BB%A5%E5%86%85%E7%9A%84arpu h_01HMTZ0DZWSN83V0TEHVM2H5XS=6%E5%88%86asa%E5%85%B3%E9%94%AE%E8%AF%8Did%E8%AE%A1%E7%AE%97365%E5%A4%A9%E4%BB%A5%E5%86%85%E7%9A%84arpu calculating-arpu-days-0-7-by-attribution-time-per-geo=7-%E5%88%86%E5%9B%BD%E5%AE%B6%E5%9C%B0%E5%8C%BA%E6%8C%89%E5%BD%92%E5%9B%A0%E6%97%B6%E9%97%B4%E8%AE%A1%E7%AE%977%E6%97%A5arpu 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-%E5%88%86%E5%9B%BD%E5%AE%B6%E5%9C%B0%E5%8C%BA%E6%8C%89%E5%BD%92%E5%9B%A0%E6%97%B6%E9%97%B4%E8%AE%A1%E7%AE%977%E6%97%A5arpu additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H7WG3CA255TG9HW150RW1QTX=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

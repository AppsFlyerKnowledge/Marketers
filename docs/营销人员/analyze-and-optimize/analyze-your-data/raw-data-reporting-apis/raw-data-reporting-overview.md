---
title: 原始数据报告概览
metadata:
  keywords:
    - LTV
    - raw data
    - uninstalls
    - AFI
    - Advertisers
    - Agencies
    - Premium Feature
    - Gray
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
  created_at: '2016-03-21T08:32:06Z'
  edited_at: '2026-10-14T10:11:27Z'
  id: 209680773
  locale: zh-cn
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/zh-cn/articles/209680773
---
> **概要：** 设备层级数据（即原始数据）用于说明与用户有关的各种事件，如激活、应用内事件、网页浏览、被Protect360拦截的激活、变现收入以及回传给渠道的用户相关数据。广告主可以通过文件下载、API和Data Locker获取原始数据报告。

<div id="raw-data-reportingtools-and-reports" />

## 原始数据的上报——工具与报告

您可以使用原始数据报告分析用户行为及用户链路、核对广告平台账目、扩充CRM和BI系统，从而提升分析、优化能力，改善用户与应用的互动。

您可以通过各种报告工具拉取原始数据报告。这些工具各有特点，因而适用于不同的场景。举例来说，如果您要核对广告平台的账目，可以在导出数据页面按需下载报告。而如果您需要将用户行为数据入库到您的BI系统，则可以使用Data Locker或Pull API，以程序化的方式拉取数据。

<div id="tip" />

> 👍 **提示**
>
> 如需进一步了解您的原始数据，我们在<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7806/play/18629/viewing-and-understanding-your-raw-data">AppsFlyer充电站里为您准备了相关课程</Anchor>，视频虽短，但干货满满！

<div id="reporting-tools-characteristics-and-features" />

<Accordion title="报告工具——特点与功能">

本节列出了用来拉取报告的各种工具。

注意事项：

* 报告的日期范围是用户行为维度的（即事件实际发生的日期），这与<Anchor target="_blank" href="/marketers/zh/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV维度</Anchor>的汇总报告不同。
* 字段说明——请见<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">原始数据字段词典</Anchor>。

<div id="reporting-tools" />

#### 报告工具

<table><thead><tr><th>工具</th><th>说明</th><th>多/单应用 (1)</th><th>数据时效性（2）</th><th>是否嵌入脚本</th><th>时区</th><th>货币</th></tr></thead><tbody><tr><td><a href="./raw-data-export-page" target="_blank">原始数据导出页面</a></td><td><ul><li>从面板下载报告</li><li>格式：CSV文件</li></ul></td><td>单应用</td><td>持续滚动更新</td><td><span><strong>x</strong></span></td><td>取决于应用层级的配置</td><td>取决于应用层级的配置</td></tr><tr><td><a href="./pull-api-raw-data" target="_blank">Pull API\*</a></td><td><ul><li>通过调用API下载报告</li><li>格式：CSV文件</li></ul></td><td>单应用</td><td>持续滚动更新</td><td><span>✓</span></td><td><ul><li>可选</li><li>默认UTC</li></ul></td><td><ul><li>可选</li><li>默认USD</li></ul></td></tr><tr><td> <a href="./data-locker-for-marketers" target="_blank">Data Locker</a> <span><strong>P</strong></span> </td><td><ul><li>数据写入<a href="./data-locker-cloud-service-setup" target="_blank">云端存储桶</a> </li><li>无行数限制</li><li>数据可用期限14天。</li><li>格式：CSV或parquet</li></ul></td><td>多应用</td><td>持续滚动更新，有数小时延迟</td><td><span>✓</span></td><td>UTC</td><td>USD </td></tr><tr><td> <a href="./push-api-streaming-raw-data" target="_blank">Push API<span></span></a> <span><strong>P</strong></span> </td><td><ul><li>用户链路数据（激活、应用内事件、再营销、SKAN）实时发送到您的服务器</li><li>格式：JSON或查询参数</li></ul></td><td>可使用同一个端点</td><td>AppsFlyer后台记录到事件的数分钟后更新</td><td><span>✓</span></td><td>UTC + 应用层级配置</td><td>USD + 应用层级配置</td></tr><tr><td> <a href="./conversion-data-payloads-and-scenarios" target="_blank">SDK转化数据</a> (3)</td><td><ul><li>从应用侧获取归因转化数据</li><li>格式：JSON</li></ul></td><td>不适用</td><td>应用首次上线的几秒钟内</td><td><span>✓</span></td><td>UTC</td><td>不适用</td></tr><tr><td colspan="7"> <strong>备注与缩略词</strong>:<br/>(1) 是否支持多个应用同时上报<br/>(2) 实际的数据时效性取决于报告本身，有些报告是每天更新一次的。<br/>（3） SDK转换数据在应用首次上线后几秒钟内获取用户归因数据，因此是最不准确的方法。<br/><span><strong>(P)</strong></span><span>高级功能</span><br/><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) 报告有行数上线</a> </td></tr></tbody></table>

<div id="tool-limitations" />

#### 报告工具的局限性

<table><thead><tr><th>局限性 </th><th>Pull API (\*)</th><th>Push API</th><th>Data Locker</th><th>SDK<br/>转化数据</th></tr></thead><tbody><tr><td>数据限制</td><td>每次调用限100万行</td><td>不适用</td><td>N/A</td><td>N/A</td></tr><tr><td>数据选项</td><td>数据类型可选，字段选项有限。</td><td>可以选择数据类型、字段、应用内事件</td><td>可以选择数据类型、字段、应用内事件</td><td>否</td></tr><tr><td>数据可用期限</td><td>90天</td><td>N/A</td><td>14天 </td><td>用户生命周期内可用（数据来自SDK）</td></tr><tr><td colspan="5"><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) 报告有行数上线</a></td></tr></tbody></table>

<div id="integration-considerations" />

#### 对接中的注意事项

| 注意事项 | Pull API | Push API | Data Locker | SDK  <br />转化数据 |
| --- | --- | --- | --- | --- |
| 服务器侧开发 | 可选 | 必须配置 | 可选 | 可选 |
| 数据处理需求 | 可选 | 必须配置 | 可选 | 可选 |
| 数据丢失风险 | 否 | 服务器宕机时数据会丢失 | 否 | 如果广告平台响应延迟可能会有数据丢失，但风险较低 |
| 客户服务器处理成本 | 无 | 高 | 低 | 无（除非数据发送到服务器） |
| 客户服务器维护 | 无 | 高 | 低 | 无（除非数据发送到服务器） |
| 数据格式 | CSV文件 | JSON或查询参数 | CSV或parquet | JSON |

</Accordion>

原始数据报告可对指定维度的记录进行分组，如非自然激活、自然应用内事件等。为便于理解，我们将报告分组维度分为以下两种：

* **用户链路：** 用于追溯用户的行为链路及其与应用的互动。  
  例如：点击 > 激活 > 应用内事件 > 卸载。
* **功能：** 与AppsFlyer的具体功能相关，但与主要的用户链路无关。例如发送给广告平台的回传数据、作弊及验证规则报告、用户级别的变现收入报告等。

<div id="report-fields" />

<Accordion title="报告字段">

<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">原始数据字段词典</Anchor>包含了用户链路报告和部分功能报告的字段说明，字段原则如下：

* **用户链路：**
  * 有一组通用字段。
  * 字段的填充取决于具体的链路。比如非自然量报告中包含带来用户的媒体渠道， 而自然量报告则由于没有相应的媒体渠道而不填充归因字段。
* **功能**：有一组专用的字段，或包含与该功能有关的用户链路字段以及其他字段。比如SKAN报告中包含一系列专用字段，而回传报告中则包含与渠道回传相关的用户链路字段及其他字段。

**提示**！建议您多查看报告，以熟练掌握相关的字段及含义。您可以在导出数据页下载报告。

为便于理解，我们根据不同场景对用户链路字段进行了分组。

<div id="user-journey-raw-data-field-groups" />

#### 用户链路原始数据字段分组

| 字段分组 | 是否与自然量相关 | 字段示例 |
| --- | --- | --- |
| 应用 | 是 | App ID（应用ID）、app name（应用名称）、app version（应用版本）、SDK version（SDK版本）、ATT |
| 归因 | 否（激活时间除外） | Install time（激活时间）、attributed touch time（广告触达时间）、media source（媒体渠道）、campaign（广告系列）、adset（广告组）、ad（广告）、partner（渠道）、retargeting conversion type（再互动转化类型） |
| 助攻归因 | 否 | Contributor partner（助攻渠道）、match type（匹配类型） |
| 设备信息 | 是 | Advertising ID（广告ID）、GAID、OAID、device type（设备类型）、customer user ID（客户用户ID，即CUID） |
| 设备位置 | 是 | IP address（IP地址）、city（城市）、country（国家） |
| 事件 | 是 | 在应用内事件报告中填充的字段：<br /><br />Event name（事件名称）、event value（事件值）、event revenue（事件收入） |

</Accordion>

<div id="user-journey-reports" />

## 用户链路报告

<Image align="center" alt="Raw_data_-_User_acquisition_.png" src="https://files.readme.io/319da2a6a5567d6cfe4a74337279e67e0bdcdb063e62ecacde5eb4293a98a1a2-36317497158033.png" />

<div id="user-journey-basics" />

<Accordion title="用户链路报告简介">

用户链路报告中的数据与用户生命周期内所发生的事件相关。这些数据按以下维度分为不同的报告：

* 用户来源：自然量或非自然量
* 链路场景：
  * 用户在激活应用前与广告有互动（浏览及点击）
  * 用户获取
  * 再营销

**用户获取（UA）报告**涵盖以下内容：

* *潜在*用户在激活前的广告浏览和点击。
* 应用激活。
* 用户在激活后完成的应用内事件。

**再营销报告涵盖以下内容：**

* 再营销广告覆盖到的用户所产生的展示和点击。
* 转化事件：再互动或再归因。
* 用户转化后完成的应用内事件，这些事件构成了再互动。注意事项：
  * 再营销数据仅记录非自然量。
  * UA和再营销应用内事件报告都包含再营销应用内事件，详见<Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">再营销双重归因法</Anchor>。

    <Image align="center" alt="Raw_data_-_Retargeting.png" src="https://files.readme.io/717f6e43ca3b224ead9e3e1c5f9b277d2f21dbc1fe3b4c217ebf4bdbc539bab7-36317470735249.png" />

如果您需要追溯某条用户链路，可以将链路重点环节的相关报告合并查看（比如激活和应用内事件），然后从AppsFlyer ID、事件时间和报告类型这几个维度来梳理报告，这样就能得到用户在过去一段时间内所完成的事件，即用户链路。

</Accordion>

<div id="user-journey-report-availability" />

<Accordion title="用户链路报告的可用性">

* 报告可用性取决于您购买的套餐。
* 报告中可包含自然量和/或非自然量数据，具体的数据可用性请见下表说明。
* 以往的原始数据报告也受到数据保存期限的限制，具体取决于您所使用的报告工具以及原始数据的来源。一般情况下，过去90天内的数据是可用的。**请注意**！汇总数据不受数据保存期限的限制。

<div id="user-journey-reports-1" />

#### 用户链路报告

<table><thead><tr><th>类别</th><th>仅限Data Locker</th><th>报告主题</th><th>自然量</th><th>非自然量</th></tr></thead><tbody><tr><td>用户获取</td><td><span>✓</span></td><td>点击</td><td colspan="2">N/A</td></tr><tr><td>再营销</td><td><span>✓</span></td><td>再营销广告的点击 </td><td colspan="2">再营销只记录非自然量</td></tr><tr><td>用户获取</td><td><span>✓</span></td><td>展示</td><td colspan="2">N/A</td></tr><tr><td>再营销</td><td><span>✓</span></td><td>再营销广告的展示</td><td colspan="2">再营销只记录非自然量</td></tr><tr><td>用户获取</td><td>-</td><td>激活假量 </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>用户获取</td><td>-</td><td>应用内事件 </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>用户获取</td><td>-</td><td>记录到的变现收入</td><td>-</td><td><span>✓</span></td></tr><tr><td>用户获取</td><td>-</td><td>自然广告收入</td><td><span>✓</span></td><td>-</td></tr><tr><td>再营销</td><td>-</td><td>再营销变现收入</td><td colspan="2">再营销只记录非自然量</td></tr><tr><td>再营销</td><td>-</td><td>再营销转化（再互动及再归因）</td><td colspan="2">再营销只记录非自然量</td></tr><tr><td>再营销</td><td>-</td><td>再营销应用内事件（再互动及再归因）</td><td colspan="2">再营销只记录非自然量</td></tr><tr><td>再营销</td><td><span>✓</span></td><td>再营销session（再互动及再归因）</td><td colspan="2">再营销只记录非自然量</td></tr><tr><td>用户获取</td><td><span>✓</span></td><td>应用打开（Sessions）</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>用户获取</td><td>-</td><td>非自然安装卸载 </td><td>-</td><td><span>✓</span></td></tr><tr><td>用户获取</td><td>-</td><td>自然卸载</td><td><span>✓</span></td><td>-</td></tr><tr><td>用户获取</td><td><span>✓</span></td><td>跨平台广告交互</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div id="user-journey-report-descriptions" />

<Accordion title="用户链路报告说明">

<div id="clicks-and-impressions" />

#### 点击和展示

| 报告 | 说明 |
| --- | --- |
| 通用 | 用户通过点击或浏览与广告互动。 |
| 说明 | 用户点击或<Anchor target="_blank" href="/marketers/zh/docs/measure-view-through-engagements#set-impression-links">浏览</Anchor>广告时，报告会记录该广告的归因链接和HTTP标头。 |
| 使用场景 | <ul><li>对于未促使用户打开应用（激活、再归因、再互动）的广告进行优化。</li><li>使用其他广告对这些用户进行再营销。</li></ul> |
| 报告示例 | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1036692270&single=true&output=csv">点击</Anchor> |
| 说明 | SRN数据不可用。 |
| 受限用户 | 有些情况下由于隐私政策的规定，会导致展示或点击数据受限（无用户标识符）或不可用。具体的数据可用性取决于媒体渠道和操作系统。 |

<div id="installs-and-retargeting-conversions" />

#### 激活和再营销转化

<table><thead><tr><th rowspan="2">报告名称 </th><th rowspan="2"><p>用户获取（UA）：激活假量</p></th><th rowspan="2">再营销：转化</th></tr></thead><tbody><tr><td>通用</td><td><p>用户首次打开应用。</p></td><td><p>用户与再营销广告互动后打开应用即为再营销转化。再营销转化包括再互动和再归因。</p> 详情请见<a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">再营销归因指南</a>。 </td></tr><tr><td>使用场景</td><td><ul><li>使用AppsFlyer分析工具中不可用的字段，生成汇总报告。</li><li>结合其他报告，形成进阶跨维度分析。</li><li>分析城市、都会区等不同维度的效果数据。 </li><li>按国家、城市和语言对用户进行分组，用于定向投放。</li><li>获取用户的设备ID，用于再营销。</li></ul></td><td>与激活类似。</td></tr><tr><td>自然量与非自然量对比</td><td><ul><li> <strong>非自然量</strong>：填充归因与助攻归因字段组。</li><li> <strong>自然量</strong> 媒体渠道字段为空/null/organic，数据入库时需要注意这一点。 </li></ul></td><td>不适用</td></tr><tr><td>报告示例</td><td><a href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR2yvNGmZp8ataHBj89CFq856PmDixnyjKK75O8fQcS9TjT8J2jBAnJoTn3350NV-7pCSlaT0oh8ebs/pub?output=csv" target="_blank">激活假量</a></td><td>再营销转化报告的结构与激活报告相同，填充再营销场景中的部分字段。详见<a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">再营销原始数据</a>。 </td></tr></tbody></table>

<div id="in-app-events" />

#### 应用内事件

<Table>
  <thead>
    <tr>
      <th>
        报告
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-context"></span>
        报告内容
      </td>
      <td>
        按时间顺序列出用户在归因（激活、再归因、再互动）后的一系列行为。
      </td>
    </tr>
    <tr>
      <td><span id="characteristics"></span>
        说明
      </td>
      <td>
        * 该报告的结构和字段与激活报告类似。
        * 具有描述事件的专用字段，包括事件名称、事件值、收入和时间。
      </td>
    </tr>
    <tr>
      <td><span id="use-case"></span>
        使用场景
      </td>
      <td>
        该报告可用于：

        * 观察用户生命周期内的用户链路，获得深入洞察。
        * 合并激活和应用内事件的原始数据报告，追溯整个用户链路。
      </td>
    </tr>
    <tr>
      <td><span id="event-values"></span>
        事件值
      </td>
      <td>
        **Event value（事件值）字段**

        事件值字段包含所有与事件相关的数据，以JSON格式显示。您可以将该信息导入您的BI系统，进行深入分析。

        **提示**：您可以使用<Anchor target="_blank" href="https://docs.microsoft.com/en-us/power-query/parse-json-xml">微软Excel中的Power Query</Anchor>对事件参数的JSON字符串进行解析。

        ```json
        {"af_level":"10","af_user_journey":"3387","arena":"7","char_type":"paladin"}
        ```

        **上报收入**

        AppsFlyer后台的收入和ROI数据是基于事件中发送的af\_revenue得出的。

        发送带有af\_revenue参数的应用内事件时，AppsFlyer会使用该参数填充对应事件的收入字段。面板和汇总报告中的收入值就来源于这个字段。

        请注意：注意：在应用内事件中只能使用af\_revenue参数来描述**实际产生的收入。** 对于add\_to\_cart（加购）等涉及收入但不代表最终收入的事件，请使用af\_price等其他参数来描述。
      </td>
    </tr>
    <tr>
      <td><span id="example-report"></span>
        报告示例
      </td>
      <td>
        <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQhOF-g3HeqZt3rXx7WZVQnB54p7ALW_IEpnJ9xtAkrcb9XzZwweiNCZzEmuX7q0i1g6yYMxYtuuX1c/pub?output=csv">应用内事件</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="remarks"></span>
        说明
      </td>
      <td>
        * <Anchor target="_blank" href="/marketers/zh/docs/resolve-retargeting-double-attribution">再营销应用内事件会同时记录到UA和再营销应用内事件的原始数据报告中。</Anchor>
        * 应用内事件不包括应用打开（af\_app\_opened）事件，请在<Anchor target="_blank" href="/marketers/zh/docs/measure-sessions">sessions</Anchor>原始数据报告中查看应用打开数据。
        * 地理位置：根据用户在完成事件时的IP地址得出。
      </td>
    </tr>
  </tbody>
</Table>

<div id="sessions" />

#### 应用打开（Sessions）

| 报告 | 说明 |
| --- | --- |
| 通用 | 用户打开应用时，SDK会发送session事件到AppsFlyer。如果前后两次应用打开的时间间隔超过<Anchor target="_blank" href="/marketers/zh/docs/measure-sessions">指定的session间最短间隔</Anchor>，则AppsFlyer后台会记录该session。 |
| 说明 | session报告的结构与应用内事件报告相同。由于session（应用打开事件）的数量较大，因此分开在单独的报告中显示。 |
| 使用场景 | 用于了解用户与应用的互动情况。 |
| 报告示例 | Session报告与应用内事件报告类似。请注意：session在原始数据中的事件名称为*launch*。 |

<div id="uninstalls" />

#### 卸载

| 报告 | 说明 |
| --- | --- |
| 通用 | 用于查看用户的应用卸载记录。 |
| 说明 | <ul><li>该报告每日更新一次，非持续滚动更新，其他的用户链路报告也是如此。</li><li>该报告中的事件时间指AppsFlyer判定应用被卸载的时间，而非实际卸载的时间。详见卸载衡量。</li></ul> |
| 可用字段 | <ul><li>如果用户是由媒体渠道带来的非自然量，则报告会填充媒体渠道字段。</li><li>需注意：卸载事件是由AppsFlyer服务器在判定用户已卸载后生成，因此会有很多不填充的字段。</li><li>可用的用户标识符是激活时记录到的，CUID总是不可用。</li><li>地理位置相关字段的值代表用户在与媒体渠道互动（即点击或浏览广告）时的位置。如果没有互动时的地理位置信息，报告会用激活事件的位置信息来填充该字段。</li></ul> |
| 报告示例 | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1558773473&single=true&output=csv">卸载报告示例</Anchor>说明：在该示例中，第2行显示了相关数据可用时会填充的字段。 |
| 使用场景 | <ul><li>分析卸载事件、设备和用户特征。</li><li>通过卸载事件进行人群分组，用于再营销。</li></ul> |

</Accordion>

<div id="user-journey-report-availability-per-tool" />

<Accordion title="各报告工具的用户链路报告可用性">

<div id="ad-engagement-report-by-tool" />

#### 各报告工具的广告互动报告

<table><thead><tr><th>报告</th><th>导出数据</th><th>Pull API</th><th>Data Locker</th><th>Push API</th><th>SDK<br/>转化数据</th></tr></thead><tbody><tr><td>展示 (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>点击 (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td colspan="6">（1）只有非SRN平台才会提供点击和展示数据，SRN不提供此类信息。</td></tr></tbody></table>

<div id="user-acquisition-reports-by-tool" />

#### 各报告工具的用户获取报告

| 报告 | 导出数据 | Pull API | Data Locker | Push API | SDK转化数据 |
| --- | --- | --- | --- | --- | --- |
| 激活 | ✓ | ✓ | ✓ | ✓ | ✓ |
| 应用打开（Sessions） | - | - | ✓ | - | - |
| 应用内事件 | ✓ | ✓ | ✓ | ✓ | - |
| 卸载 | ✓ | ✓ | ✓ | - | - |

<div id="retargeting-raw-data-reports-by-tool" />

#### 各报告工具的再营销原始数据报告

<table><thead><tr><th>报告</th><th>导出数据</th><th>Pull API</th><th>Data Locker</th><th>Push API</th><th>SDK<br/>转化数据</th></tr></thead><tbody><tr><td>点击 (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>转化（再归因 + 再互动）</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>展示 (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>应用打开（Sessions）</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>应用内事件</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">（1）只有非SRN平台才会提供点击和展示数据，SRN不提供此类信息。</td></tr></tbody></table>

</Accordion>

<div id="faq" />

<Accordion title="常见问题解答">

| 说明 |
| --- |
| **各种时间戳之间有什么区别？**<br /><br />所有报告的时间戳类型都是一样的，因此不同报告才能互相合并。<br /><br />下列时间戳是较为重要的：<ul><li>**Attributed Touch Time（广告触达时间）**：用户与广告互动的时间。</li><li>**激活时间**：应用首次打开的时间。</li><li>**事件时间**：事件发生的时间。</li></ul>注意事项：<ul><li>在激活报告中，激活时间与事件时间相同。</li><li>在应用内事件报告中，激活时间与事件时间不同。两者之间的时间差为用户从打开应用到与应用互动之间的时间。</li></ul> |
| **contributor（助攻）字段有什么意义？**<br /><br />助攻字段会列出助攻媒体渠道，也称为<Anchor target="_blank" href="/marketers/zh/docs/measure-assisted-installs#assisted-installs-reporting">Assisted Installs</Anchor>（助攻激活）。在Protect360中，该字段也用于<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports#被劫持的激活归因更正">校正被劫持的激活归因</Anchor>。 |
| **什么是关键词字段？为什么不是所有的非自然激活都有关键词字段？**<br /><br />归因到Google Ads或Apple Search Ads的激活才会包含关键词或关键词ID（关联到带来激活的广告）。 |

</Accordion>

<div id="install-report-tips" />

<Accordion title="激活报告使用贴士">

**了解用户链路**

用户链路是指用户在达成目标行为（如购买产品或订购机票）前所经历的一系列环节。分析用户链路是为了了解用户在应用中的行为、活跃程度，以及在某段时间内用户所带来的价值。

您可以通过AppsFlyer ID来识别并突出显示用户链路。该ID是每个设备每次安装应用时生成的，并在用户的生命周期中（从激活到卸载）保持不变，即使用户重置设备ID也不会改变AppsFlyer ID。

由于激活报告和应用内事件报告的结构相同，因此可以合并成一个报告。在合并报告中，您可以使用AppsFlyer ID和CUID（如可用）对数据进行汇总和筛选，从而分析用户链路。

> 📄 **示例**
>
> #### <span id="engaged-userstrong"></span>活跃用户——强互动
>
> * 某用户在8月20日09:31激活应用。
> * 合并报告显示该用户在8月20日10:31、8月22日15:22以及8月25日16:47分别完成了购买事件。
> * 基于此信息，我们可以判断该用户是活跃用户，因其在首次打开应用的一小时后就完成了购买事件，且在激活之后的数天中持续下单。
>
> #### <span id="engaged-userweak"></span>活跃用户——若互动
>
> * 某用户在7月30日激活应用。合并报告显示该用户在8月15日将某商品添加至购物车，但之后没有完成购买事件。
> * 基于此信息，可推测该用户正在犹豫是否要下单，因此您可以通过其加购的商品对其进行再营销。
>
> #### <span id="analyzing-the-user-journey-for-campaign-optimization"></span>分析用户链路可推动投放优化
>
> * 某旅游应用的拉新（UA）经理下载了激活报告和应用内事件报告，并将两个报告合并。
> * 然后他通过AppsFlyer ID筛选或汇总报告中的数据，以查看用户在应用中的链路。
> * 这位经理发现某个用户（通过AppsFlyer识别）在12个月前下载了应用，并在激活后的数天内订购了一张机票。
> * 之后，该用户查看了一些特价航班，但最终没有预定。UA经理继续往下看报告，发现有很多用户都有相似的行为，于是决定深入调查该现象。
> * 结果发现，这些用户大多来自**媒体渠道C**上投放的**Campaign B**中的**Ad A**。这则广告和该营销活动的目标受众是计划前往某一特定目的地的用户。
> * 通过分析用户链路，这位经理找出了用户与应用互动不足的原因，可能是因为该广告系列的内容太具体、受众面太窄了。

</Accordion>

<div id="feature-reports" />

## 功能报告

与平台其他功能相关的可用报告如下：

* <Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">广告收入</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview#原始数据报告">增量分析</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports">SKAdNetwork</Anchor>

<div id="postbacks" />

<Accordion title="数据回传">

您可以使用回传报告查看发送给广告平台的数据副本，从而考察数据差异等事项。这些报告仅作参考，并非与广告平台对接时必须配置的内容。

* 该报告包含以下内容：
  * 向获得归因的媒体渠道发送的回传数据副本
  * <Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">原始数据字段</Anchor>及其他字段的具体说明请见本节中的表格。
* 该报告不包含以下内容：
  * SRN激活。
  * 与Meta ads、X Ads和Apple Search Ads相关的应用内事件。
  * 未归因的渠道回传。详见<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">归因到渠道或自然量的数据</Anchor>。
  * 自然用户。详见<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#default-postbacks">自然激活</Anchor>。
* 从2021年3月起，该报告会根据相关广告平台的Advanced Privacy（高级隐私保护）设置来填充字段。也就是说，Advanced Privacy处于启用状态时，用户标识符等字段不填充。详见<Anchor target="_blank" href="/partners/zh/docs/advanced-privacy-guide-postback-macros-for-ad-networks#advanced-privacy-postback-specification">广告平台的Advanced Privacy回传配置</Anchor>。
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5">通过Pull API获取回传报告</Anchor>

<div id="postback-reports-available-via-the-export-data-page-and-pull-api" />

#### 回传报告（通过导出数据或Pull API拉取）

| 报告主题 | 回传给渠道的事件 |
| --- | --- |
| 激活 | 非自然（UA）激活 |
| 应用内事件 | 非自然安装应用内事件 |
| 再营销转化回传 | 再营销（再互动与再归因） |
| 再营销应用内事件 | 再营销应用内事件 |

<div id="additional-fields-in-postback-reports" />

#### 回传报告中的其他字段

| 字段 | 说明 |
| --- | --- |
| Postback URL（回传链接） | 收入等一部分值可能不会出现在对应的字段中，但您仍可以在**回传**URL中看到这些数据。 |
| Postback method（回传方式） |  |
| Postback HTTP response code（回传HTTP响应代码） | 200:确认广告平台已接收到回传 |
| Postback error message（回传报错消息） |  |

</Accordion>

<div id="protect360-fraud-and-validation-rules" />

<Accordion title="Protect360防作弊及验证规则">

* 详见<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports">Protect360</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/implement-validation-rules-to-prevent-fraud#outcomes">验证规则</Anchor>原始数据报告
* <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#access-protect360-dashboard-raw-data">广告平台和代理需要在广告主授权后才能获取Protect360和验证规则报告</Anchor>

**请按以下步骤向对接渠道开放Protect360的权限：**

1. 进入**协作** > **活跃对接**。
2. 选择相关的对接渠道。
3. 在**授权**选项卡中，打开**访问Protect360面板和原始数据**的开关。
4. 如需开放应用内事件（CPA）面板的权限，请打开**访问汇总应用内事件数据**的开关。

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview">汇总报告和分析工具</Anchor>

<div data-zendesk-anchors="raw-data-reporting%E2%80%94tools-and-reports=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E7%9A%84%E4%B8%8A%E6%8A%A5%E5%B7%A5%E5%85%B7%E4%B8%8E%E6%8A%A5%E5%91%8A h_01HE7SRDXQ9TR0CRB2JC9XCQE2=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E7%9A%84%E4%B8%8A%E6%8A%A5%E5%B7%A5%E5%85%B7%E4%B8%8E%E6%8A%A5%E5%91%8A h_01HE7SRDXQQJFMV9EJKPY34D00=%E6%8F%90%E7%A4%BA reporting-tools%E2%80%94characteristics-and-features=reporting-tools-characteristics-and-features h_01HE7SRDXQFJGMY05K1SV4TF63=reporting-tools-characteristics-and-features reporting-tools=%E6%8A%A5%E5%91%8A%E5%B7%A5%E5%85%B7 h_01HE7SRDXQ647XRQ8QVMPGH43B=%E6%8A%A5%E5%91%8A%E5%B7%A5%E5%85%B7 tool-limitations=%E6%8A%A5%E5%91%8A%E5%B7%A5%E5%85%B7%E7%9A%84%E5%B1%80%E9%99%90%E6%80%A7 h_01HE7SRDXQWQAKR0G6CNKC5AMT=%E6%8A%A5%E5%91%8A%E5%B7%A5%E5%85%B7%E7%9A%84%E5%B1%80%E9%99%90%E6%80%A7 integration-considerations=%E5%AF%B9%E6%8E%A5%E4%B8%AD%E7%9A%84%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01HE7SRDXQN3HSMGAPBAX9S3MB=%E5%AF%B9%E6%8E%A5%E4%B8%AD%E7%9A%84%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01HE7SRDXQRPD8MHC8M5916HTQ=report-fields user-journey-raw-data-field-groups=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%AD%97%E6%AE%B5%E5%88%86%E7%BB%84 h_01HE7SRDXQMGQEG1QWGWEESQER=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%AD%97%E6%AE%B5%E5%88%86%E7%BB%84 user-journey-reports=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E6%8A%A5%E5%91%8A h_01HE7SRDXQZ50WMKCMYHZM7D92=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E6%8A%A5%E5%91%8A h_01HE7SRDXQFN0P9QK8SKAZKVKP=user-journey-basics h_01HE7SRDXRS2B12Z67MYMH0QN9=user-journey-report-availability user-journey-reports::d286e1f5=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E6%8A%A5%E5%91%8A-1 h_01HE7SRDXR7YQGWN4FNDXMNMX8=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E6%8A%A5%E5%91%8A-1 h_01HE7SRDXRK6G27SDFK3CGDCRC=user-journey-report-descriptions clicks-and-impressions=%E7%82%B9%E5%87%BB%E5%92%8C%E5%B1%95%E7%A4%BA h_01HE7SRDXRC9YKZ0P9ED0218SJ=%E7%82%B9%E5%87%BB%E5%92%8C%E5%B1%95%E7%A4%BA installs-and-retargeting-conversions=%E6%BF%80%E6%B4%BB%E5%92%8C%E5%86%8D%E8%90%A5%E9%94%80%E8%BD%AC%E5%8C%96 h_01HE7SRDXRN60XE5BSDQY28N71=%E6%BF%80%E6%B4%BB%E5%92%8C%E5%86%8D%E8%90%A5%E9%94%80%E8%BD%AC%E5%8C%96 inapp-events=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HE7SRDXR3ZT39EDNW4MVZZTX=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 sessions=%E5%BA%94%E7%94%A8%E6%89%93%E5%BC%80sessions h_01HE7SRDXRY05XQCMZE6YPXGWQ=%E5%BA%94%E7%94%A8%E6%89%93%E5%BC%80sessions uninstalls=%E5%8D%B8%E8%BD%BD h_01HE7SRDXRA7ESDD4ME51WWBPR=%E5%8D%B8%E8%BD%BD h_01HE7SRDXRZYNFGK4CNP4VPAE0=user-journey-report-availability-per-tool ad-engagement-report-by-tool=%E5%90%84%E6%8A%A5%E5%91%8A%E5%B7%A5%E5%85%B7%E7%9A%84%E5%B9%BF%E5%91%8A%E4%BA%92%E5%8A%A8%E6%8A%A5%E5%91%8A h_01HE7SRDXR171M74HMQBZJ2E8R=%E5%90%84%E6%8A%A5%E5%91%8A%E5%B7%A5%E5%85%B7%E7%9A%84%E5%B9%BF%E5%91%8A%E4%BA%92%E5%8A%A8%E6%8A%A5%E5%91%8A user-acquisition-reports-by-tool=%E5%90%84%E6%8A%A5%E5%91%8A%E5%B7%A5%E5%85%B7%E7%9A%84%E7%94%A8%E6%88%B7%E8%8E%B7%E5%8F%96%E6%8A%A5%E5%91%8A h_01HE7SRDXRMGEP5QB452ZKQ8X7=%E5%90%84%E6%8A%A5%E5%91%8A%E5%B7%A5%E5%85%B7%E7%9A%84%E7%94%A8%E6%88%B7%E8%8E%B7%E5%8F%96%E6%8A%A5%E5%91%8A retargeting-raw-data-reports-by-tool=%E5%90%84%E6%8A%A5%E5%91%8A%E5%B7%A5%E5%85%B7%E7%9A%84%E5%86%8D%E8%90%A5%E9%94%80%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01HE7SRDXRXR4J3HTMYW2P233Y=%E5%90%84%E6%8A%A5%E5%91%8A%E5%B7%A5%E5%85%B7%E7%9A%84%E5%86%8D%E8%90%A5%E9%94%80%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01HE7SRDXRWW3JKNESSN2QA4DV=faq h_01HE7SRDXR61K28JGA8944D6HV=install-report-tips h_01HE7SRDXRKFR2WYGNF317CTRX=%E7%A4%BA%E4%BE%8B engaged-user%E2%80%94strong=%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7%E5%BC%BA%E4%BA%92%E5%8A%A8 h_01HE7SRDXRW0CWHGQV75VF66DC=%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7%E5%BC%BA%E4%BA%92%E5%8A%A8 engaged-user%E2%80%94weak=%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7%E8%8B%A5%E4%BA%92%E5%8A%A8 h_01HE7SRDXRNMDZEJQ32665T14F=%E6%B4%BB%E8%B7%83%E7%94%A8%E6%88%B7%E8%8B%A5%E4%BA%92%E5%8A%A8 analyzing-the-user-journey-for-campaign-optimization=%E5%88%86%E6%9E%90%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E5%8F%AF%E6%8E%A8%E5%8A%A8%E6%8A%95%E6%94%BE%E4%BC%98%E5%8C%96 h_01HE7SRDXRRET0YN4Q8WYMENSR=%E5%88%86%E6%9E%90%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E5%8F%AF%E6%8E%A8%E5%8A%A8%E6%8A%95%E6%94%BE%E4%BC%98%E5%8C%96 feature-reports=%E5%8A%9F%E8%83%BD%E6%8A%A5%E5%91%8A h_01HE7SRDXSVAHKBYQK0C71K6AR=%E5%8A%9F%E8%83%BD%E6%8A%A5%E5%91%8A h_01HE7SRDXSFWMVY61NBYFQ4XSM=postbacks postback-reports-available-via-the-export-data-page-and-pull-api=%E5%9B%9E%E4%BC%A0%E6%8A%A5%E5%91%8A%E9%80%9A%E8%BF%87%E5%AF%BC%E5%87%BA%E6%95%B0%E6%8D%AE%E6%88%96pull-api%E6%8B%89%E5%8F%96 h_01HE7SRDXS6T4M4CRQN0ZTJETR=%E5%9B%9E%E4%BC%A0%E6%8A%A5%E5%91%8A%E9%80%9A%E8%BF%87%E5%AF%BC%E5%87%BA%E6%95%B0%E6%8D%AE%E6%88%96pull-api%E6%8B%89%E5%8F%96 additional-fields-in-postback-reports=%E5%9B%9E%E4%BC%A0%E6%8A%A5%E5%91%8A%E4%B8%AD%E7%9A%84%E5%85%B6%E4%BB%96%E5%AD%97%E6%AE%B5 h_01HE7SRDXSYBDG0H2QEYBFWSRH=%E5%9B%9E%E4%BC%A0%E6%8A%A5%E5%91%8A%E4%B8%AD%E7%9A%84%E5%85%B6%E4%BB%96%E5%AD%97%E6%AE%B5 h_01HE7SRDXS8K4MB76WVBCBHASQ=protect360-fraud-and-validation-rules h_01HE7ST20N8ZBFNY2QXW5G44A1=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

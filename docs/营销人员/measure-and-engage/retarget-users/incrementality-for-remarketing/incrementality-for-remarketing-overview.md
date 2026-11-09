---
title: 再营销增量分析概述
metadata:
  keywords:
    - Analytics
    - Audiences
    - Advertisers
    - Premium
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2020-05-29T19:29:03Z'
  edited_at: '2026-10-14T10:00:03Z'
  id: 360009360978
  locale: zh-cn
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/zh-cn/articles/360009360978
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 本文解释了如何衡量再营销广告带来的增量。

<div id="what-is-incrementality" />

## 什么是增量分析？

我们可以通过以下示例来直观地理解增量分析这一概念：

假设您近期在某个广告平台上投放了一系列再营销广告。该广告系列的转化率为5%。

您想要评估该次投放是否成功，并回答以下问题：

* 对于这个广告系列来说，5%的转化率是否合格？
* 如何判断该广告系列确实带来了额外的转化？
* 这次活动投入的成本是否获得了理想回报？

要准确、客观地回答这些问题，不能只看表面上的转化数据。我们必须考虑到这样一种情况：有一部分用户即使没有接触到这次再营销活动，也会自然转化。

因此，“总转化量”与“自然转化量”之间的差值，就是所谓的**增量提升**（incremental lift，或简称**lift**），这是判断活动真实价值的关键指标。但要精确衡量这一差值并不简单，而这正是AppsFlyer增量分析所提供的功能。

<div id="incrementality-experiments" />

### 增量实验

增量分析可通过科学的实验方法，帮助您衡量增量提升。其核心思路是将用户划分为行为特征相似的群组。被营销活动触达的用户被分为 **"测试组"**，而未被营销活动触达的用户则被分为 **"对照组"**。

<Anchor target="_blank" href="/marketers/zh/docs/run-an-incrementality-for-remarketing-experiment">通过对比两组的转化表现，即可清晰了解广告活动带来的真实增量。</Anchor>

<div id="calculation-methodology" />

## 计算方法

以下内容说明了增量分析面板中各项数据的计算逻辑。

<div id="lift" />

<Accordion title="增量提升">

AppsFlyer增量分析使用两种不同的方法计算 增量提升：

* 意向处理法（ITT，Intent-to-treat）
* 基于触达法（Reach-based）

在评估广告活动表现时，**基于触达法**更为理想， 但这种方法需要广告平台提供额外的数据， 而并非所有平台能提供这样的数据。在这类平台上， 将采用ITT方法。

<div id="note" />

> 📘 **注意**
>
> 在2021年12月16日之前， 系统仅通过ITT的方法计算增量提升。此后，历史数据已更新为在适用的情况下采用基于触达法计算。 因此，您可以重新查看早期实验，并根据新的方法论来解读结果。

<div id="itt-based-lift" />

#### 基于ITT的增量计算

ITT（意向处理法）方法源自于医学实验。 研究人员会将受试人群随机分为两组：未接受治疗的病人为对照组，计划接受治疗的病人为实验组。 研究人员通过比较两组的结果，来衡量治疗效果。 在计算时，不考虑实验组成员是否真正接受了治疗。

在再营销场景下，增量提升衡量的是活动效果。 即使实验组中的用户没有真正与广告互动（没有“接受治疗”），只要他们属于实验组，就会被纳入计算范围。 换句话说，我们假设实验组中所有用户都接触过广告活动，以此来进行计算增量。

**适用场景**

AppsFlyer增量分析在SRN（自归因网络）中使用ITT方法。

虽然这并非首选方式，但ITT是一种科学严谨的实验方法，在无法进行基于触达计算时仍然能提供有效结果。

**结果解读**

由于ITT方法假设实验组所有用户都接触了广告，这可能会导致转化率偏低，从而出现增量提升值较低的情况。

<div id="reach-based-lift" />

#### 基于触达的增量计算

顾名思义，基于触达的增量计算会考虑实验组用户在转化之前是否真正被广告触达（即是否实际看到过广告）。 此外，它还需要对对照组进行特定数学调整，以保证统计学上的有效性。 这类调整被称为创建一个“反事实对照组（counterfactual control group）”。

**适用场景**

AppsFlyer增量分析在非SRN（基于归因链接的广告平台）中采用基于触达的计算。

该方法需要广告平台向AppsFlyer提供以下数据：

* 曝光数据
* 归因链接中的广告系列ID

如果这些数据未上报，则无法进行增量分析（面板中会显示**N/A**）。

**结果解读**

由于基于触达的方法仅考虑真正看到广告的实验组用户，因此其结果通常会被“放大”：正向增量提升会更高，负向增量提升会更低。

<div id="best-practices" />

#### 最佳实践

由于两种计算方法可能产生显著差异，建议采取以下做法来确保结果解读的正确性：

* 创建实验时，应将受众划分为对照组和同类平台的一个或多个实验组：
  * 归因链接广告平台（非SRN）用于基于触达计算；或
  * SRN用于ITT计算
* 在初始实验中，建议仅将一个广告平台上的首重分为实验组和对照组，避免同时将计算方法不同的多个平台进行对比。

</Accordion>

<div id="statistical-significance" />

<Accordion title="统计显著性">

在评估增量实验的可靠性时，需要考虑统计显著性（即结果不是偶然发生的）。

在增量分析面板中，媒体渠道的显著性以百分比显示：

* 百分比表示：如果在相似条件下再次进行实验，该结果复现的可能性。
* 如果显著性低于 60%，面板会显示“结果不可靠（Unreliable results）”，而不再显示百分比。
* 显著性会受到受众规模、实验周期和渠道表现的影响。

</Accordion>

<div id="scaled-control-group" />

<Accordion title="按比例缩放的对照组">

在计算[群组层级指标](/docs/incrementality-for-remarketing-overview#::2c5f08ec)（非[用户层级指标](/docs/incrementality-for-remarketing-overview#::6143ff4f)）时，将基于按比例缩放的对照组计算增量。 也就是说，系统会调整对照组规模，使其与每个媒体渠道的对照组规模保持一致。

<div id="example" />

> 📄 **示例**
>
> 假设以下场景：
>
> * 平台A实验组规模：100人
> * 对照组规模：90人
> * 实验结果：
>   * 平台A转化数：40
>   * 对照组转化数：20
> * 系统将总转化数调整为基于标准化对照组（100 人）的结果：
>   * 假设成员 - 实际成员 = 100 - 90 = 11%
>      实际成员      90
>   * 实际增量转化 + 11% = 20 x 1.11 = 22
>
> 最终将基于对照组规模100人和22个增量转化来计算增量提升。

</Accordion>

<div id="::6ba593ae" />

<div id="::3b361a96" />

<div id="incrementality-dashboard" />

## 增量分析面板

<Image align="center" alt="New_Incrementality_Guide_image.jpg" src="https://files.readme.io/a14fa7ae346177dbdd7de5fde4917d7300cbc148097a2239e29460a67eacd9a6-15317247527569.jpg" />

<div id="accessing-the-dashboard" />

<Accordion title="访问面板">

增量分析是AppsFlyer的高阶功能。如需使用，请联系您的客户成功经理，或发送邮件至 hello@appsflyer.com。 订阅后，您即可访问增量分析面板。

**访问方法：**

1. 从AppsFlyer后台的侧边栏中选择**优化** > **增量分析**。
2. 在实验列表中，点击想查看的实验行，即可进入对应的面板。

</Accordion>

<div id="a-tour-of-the-dashboard" />

<Accordion title="面板导览">

<Table>
  <thead>
    <tr>
      <th>

      </th>
      <th>
        组成部分
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ![A.png](https://files.readme.io/66b5bb0c4ea35f232f65dbc8dcbdfd6a91c12cf94915b19d33dae44834127058-31237653543313.png)
      </td>
      <td>
        筛选条件栏
      </td>
      <td>
        **衡量：** 选择您要查看的指标：

        * **转化** – 完成所选事件的独立用户数
        * **收入** – 完成所选事件的用户带来的收入
        * **活动** - 转化用户完成所选事件的总次数

        您在**衡量**筛选条件中选择的指标将在整个面板中显示。

        **事件：** 选择要查看的应用内事件。

        **媒体渠道：** 按实验中测试的一个或多个媒体渠道筛选数据。

        **日期范围：** 按所选日期范围筛选增量分析结果。
      </td>
    </tr>
    <tr>
      <td>
        ![B.png](https://files.readme.io/f63914d3fefb55b627559c6e4c7d7cdef89239c0376a14c25c713a0a76dbad1b-31237653544337.png)
      </td>
      <td>
        实验摘要
      </td>
      <td>
        快速汇总整个实验的关键结果，一目了然。
      </td>
    </tr>
    <tr>
      <td>
        ![C.png](https://files.readme.io/b428e77b299e10fe0701b7850cea1da8942905ad38d7b30c32f99f0240b22a63-5397303804945.png)
      </td>
      <td>
        显著性卡片
      </td>
      <td>
        展示实验结果的统计显著性。
      </td>
    </tr>
    <tr>
      <td>
        ![D.png](https://files.readme.io/9d9abd09fc45ec65fc52cbc1c8011117b555629d243444d076a392b4245effdd-5397362181265.png)
      </td>
      <td>
        <span id="::4c3ffd21"></span>核心指标卡片
      </td>
      <td>
        显示您在“衡量筛选条件”中选择的指标，如下所示。

        | 选择衡量筛选条件 | 显示的标题指标 |
        | --- | --- |
        | <span id="conversionsevents"></span>转化/事件 | 每个增量行为的成本（CPiA）<br /><br />* 基于广告成本计算的单次增量事件成本 |
        | <span id="revenue"></span>收入 | 增量广告支出回报率 (iROAS)<br /><br />* 每1美元广告花费带来的增量收入比 |

        **注意：** 核心指标计算依赖成本数据，因此仅供ROI360订阅用户使用。 如果缺少成本或收入数据，对应指标将显示为N/A。
      </td>
    </tr>
    <tr>
      <td>
        ![E.png](https://files.readme.io/28563cf0057cdd6ccfd8ebb5b727ae80bef81ec66697f8e11eadc698f72e7acd-5397355189777.png)
      </td>
      <td>
        <span id="::c0b74d1b"></span>目标规模与触达卡片
      </td>
      <td>
        **目标规模：** 实验期间首次加入受众的独立用户数（按媒体渠道）。在饼图内环（深色部分）展示。

        **覆盖范围：** 目标用户中实际看到该媒体渠道广告的比例。在饼图外环（浅色部分）展示。
      </td>
    </tr>
    <tr>
      <td>
        ![F.png](https://files.readme.io/99f2fb8f45215ddebf9582f215e3647bc35f5a812015733b3f6e3cb8d2784bd7-5397365201809.png)
      </td>
      <td>
        <span id="::2c5f08ec"></span>实验组层级增量提升卡片显示实验组的总增量指标与提升值（按媒体渠道）。
      </td>
      <td>
        * 总增量提升基于比例调整后的对照组数据计算。
        * 显示您在“衡量筛选条件”中选择的指标，如下所示。

        | 选择衡量筛选条件 | 显示的指标 |
        | --- | --- |
        | <span id="conversions"></span>转化 | 总增量转化 |
        | <span id="events"></span>事件 | 总增量事件 |
        | <span id="revenue::3f000a8e"></span>收入 | 总增量收入 |
      </td>
    </tr>
    <tr>
      <td>
        ![G.png](https://files.readme.io/7301cda39a8a6bcd08d199097ff9b11d496c5f01ab34422364a4e467a752338a-5397303963409.png)
      </td>
      <td>
        <span id="::6143ff4f"></span>人均增量提升卡片
      </td>
      <td>
        显示实验组用户的人均增量指标与提升值（按媒体渠道）。

        * 人均增量提升基于实验组和对照组的实际用户数计算。
        * 显示您在“衡量筛选条件”中选择的指标，如下所示。

        | 选择衡量筛选条件 | 显示的指标 |
        | --- | --- |
        | <span id="conversions::b51393dc"></span>转化 | 增量转化率 |
        | <span id="events::3b4fa416"></span>事件 | 每用户增量事件 |
        | <span id="revenue::b432caf"></span>收入 | 每用户增量收入 |
      </td>
    </tr>
    <tr>
      <td>
        ![H.png](https://files.readme.io/36085f38ba02d718acc766af3865073bf13960b2a1c755bd48302ab5415ff89a-5397355274513.png)
      </td>
      <td>
        <span id="::a6a95657"></span>趋势图
      </td>
      <td>
        展示实验周期内的人均增量指标/提升变化：

        * 您可在“衡量筛选条件”中选择显示的指标，内容与 **“人均增量提升卡片”** 一致。
        * 图中虚线代表部分数据（指未来事件可能会影响数据）。
        * 您可使用**趋势图视图控制**选择不同的视图和下载选项（如下所述）。
      </td>
    </tr>
    <tr>
      <td><span id="::64e4f3f6"></span>
        <Image alt="I.jpg" src="https://files.readme.io/19ab5c305d3eb2609031a1a88f6f4069015b6eefe9ef4f1501613f62e5024739-15317326904465.jpg" width="29px" />
      </td>
      <td>
        趋势图视图控件
      </td>
      <td>
        您可使用**趋势图**选择不同的视图和下载选项

        * 按累计值或当日值 (On-day)
        * 图表或表格形式

        点击**导出**按钮，将数据下载为CSV报告。

        * 您可使用**视图控件**选择下载的数据： **累计**或**当天**

        **报告中的术语说明**

        | 术语 | 说明 |
        | --- | --- |
        | 原始指标 | 实验组产生的总转化/事件/收入，仅基于用户随机分组结果，不考虑实际曝光情况。 |
        | 触达指标 | 实验组中，在触发事件前实际看到过广告的用户所带来的转化/事件/收入。 |
        | 未触达指标 | 原始指标 - 触达指标， 表示实验组中未看到广告但仍完成事件的用户所带来的转化/事件/收入。 |
        | 人均指标 | 实验组触达/原始指标（取决于广告平台是否支持触达数据）除以实验组的规模/触达用户数。 |
        | 对照组原始指标 | 对照组产生的总转化/事件/收入。 |
        | 对照组触达指标 | 对照组的转化/事件/收入，基于实验组的触达比例推算（属于“反事实”数据，用于对比）。 |
        | 对照组未触达指标 | 对照组原始指标减去反事实触达指标， 表示未看到广告的对照组用户带来的的转化/事件/收入。 |
        | 对照组人均指标 | 对照组触达/原始指标（取决于是否支持触达数据）除以对照组规模/反事实触达用户数。 |
        | 总增量指标 | 实验组触达指标减去对照组反事实触达指标。 |
        | 人均增量指标 | 实验组人均指标减去对照组人均指标。 |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-reports" />

## 原始数据报告

使用增量分析原始数据报表，可以深入分析用户与再营销活动的互动情况：

* **内容：** 包含参与增量实验的用户逐行级别数据。
* **获取方式：**
  * 通过<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">Data Locker</Anchor>下载
  * 数据更新频率：每日19:00–23:00（UTC）

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012600697">下载示例：增量分析原始数据文件</Anchor>

<div id="available-reports" />

<Accordion title="可用报告">

<table><thead><tr><th>类别</th><th>报告名称 </th><th>Data Locker文件夹</th></tr></thead><tbody><tr><td>首次识别</td><td>首次识别用户</td><td>incrementality_first_seen_users</td></tr><tr><td rowspan="3">应用内事件</td><td>自然应用内事件</td><td>incrementality_organic_inapps</td></tr><tr><td>非自然应用内事件</td><td>incrementality_inapps</td></tr><tr><td>应用内事件再归因</td><td>incrementality_inapps_reattr</td></tr><tr><td rowspan="3"><p>应用打开（Sessions）</p></td><td>自然应用打开数</td><td>incrementality_organic_sessions</td></tr><tr><td>非自然应用打开数</td><td>incrementality_sessions</td></tr><tr><td>应用打开再归因</td><td>incrementality_sessions_reattr</td></tr><tr><td>卸载</td><td>卸载<br/>（目前未填充数据） </td><td>incrementality_uninstalls</td></tr></tbody></table>

</Accordion>

<div id="report-logic" />

<Accordion title="报告逻辑">

报告结构的基本逻辑如下：

* **参与实验的用户—首次识别报告**
  * 在共享受众中设置规则，用于定义哪些用户进入实验。
  * 当用户符合规则时，会在*first\_seen*报告中记录事件。
    * 用户会被随机分配到实验组或对照组中，并以*is\_control\_group*字段区分。
    * 实验组用户会被分配至某个媒体渠道（*pid\_destination*）用于再营销投放。
* **应用内交互：** 用户在实验期间与应用的交互会记录在相应报告中：
  * **交互类型：** 会话或应用内事件
  * **用户归因状态** - 首次识别时：自然流量、非自然流量、再归因。例如：某用户最初通过自然渠道激活应用，则在实验中其状态仍为自然流量。
* **卸载：** 用户在测试期间卸载了应用。需启用卸载监测功能。

</Accordion>

<div id="data-characteristics-and-fields" />

<Accordion title="数据特征和字段">

字段的可用性视报告类型而有所不同：

<div id="fields-unique-to-incrementality-per-report-type" />

#### 增量分析专属字段（按报表类型区分）

| 字段 | 说明 | 首次识别 | 应用内事件 | 应用打开（Sessions） | 卸载 |
| --- | --- | --- | --- | --- | --- |
| <span id="is_control_group"></span>is\_control\_group | 如果为true，则该用户属于对照组。 | Y | Y | Y | Y |
| <span id="pid_destination"></span>pid\_destination | 用户被发送到的媒体渠道 | Y | Y | Y | Y |
| <span id="audience_id"></span>audience\_id | 独立标识符 | Y | Y | Y | Y |
| <span id="joined_audience_date"></span>joined\_audience\_date | 用户首次加入受众规则的日期 | Y | Y | Y | Y |
| <span id="audience_name"></span>audience\_name | 受众名称（非唯一） | Y | Y | Y | Y |
| <span id="tm"></span>tm | 一天中的时间 |  | Y | Y | Y |
| <span id="timestamp"></span>timestamp | 事件时间戳 YYYY-MM-DD HH:MM |  | Y | Y |  |
| <span id="app_ids"></span>app\_ids | 关联到共享受众规则的 App ID | Y |  |  |  |

<div id="other-incrementality-report-fields-per-report-type" />

#### 其他增量报告字段（按报告类型）

<table><thead><tr><th>字段</th><th>显示名称\*</th><th>首次识别</th><th>应用内事件</th><th>应用打开（Sessions）</th><th>卸载</th></tr></thead><tbody><tr><td><span id="advertising_id"></span>advertising_id</td><td>广告ID (GAID)</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="android_id"></span>android_id</td><td>Android ID</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="app_id"></span>app_id</td><td>App ID（应用ID）</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="app_name"></span>app_name</td><td>应用名称</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="app_version"></span>app_version</td><td>应用版本</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="appsflyer_id"></span>appsflyer_id</td><td>AppsFlyer ID</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="revenue_alt"></span>revenue_alt</td><td>应用配置中的指定货币</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="bundle_id"></span>bundle_id</td><td>Bundle ID</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="country"></span>country</td><td>国家代码</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="currency"></span>currency</td><td>货币代码</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="customer_user_id"></span>customer_user_id</td><td>Customer user ID</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="brand"></span>brand</td><td>设备品牌</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="device_category"></span>device_category</td><td>设备类别</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="model"></span>model</td><td>设备型号</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="device_model"></span>device_model</td><td>设备型号</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="device_type"></span>device_type</td><td>设备类型</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="event_name"></span>event_name</td><td>事件名称</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="event_revenue"></span>event_revenue</td><td>事件收入</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="event_revenue_currency"></span>event_revenue_currency</td><td>事件收入货币</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="event_revenue_u_s_d"></span>event_revenue_u_s_d</td><td>以美元为单位的事件收入</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="event_time"></span>event_time</td><td>事件时间</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="event_value"></span>event_value</td><td>事件值</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="idfa"></span>idfa</td><td>IDFA</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="idfv"></span>idfv</td><td>IDFV</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="imei"></span>imei</td><td>IMEI</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="is_purchase_validated"></span>is_purchase_validated</td><td>收入已验证</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="os_version"></span>os_version</td><td>OS version</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="platform"></span>platform</td><td>系统平台</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="sdk_version"></span>sdk_version</td><td>SDK version</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td colspan="6"><span id="-according-to-raw-data-specification"></span>\* <a href="./raw-data-field-dictionary#data-fields-dictionary" target="_blank">根据原始数据规则</a> </td></tr></tbody></table>

</Accordion>

<div id="incrementality-specifications-and-limitations" />

## 增量功能特性与局限性

| 特点 | 说明 |
| --- | --- |
| 账户用户访问权限 | 可用（具体取决于账户授权） |
| 广告平台访问权限 | 不可用 |
| 代理访问权限 | 不可用。增量分析仅对广告主账户开放。 |
| 代理数据透明化 | 若代理开启了透明度模式，您也可以衡量由代理执行的广告活动。 |
| 币种 | USD |
| 数据时效性 | 面板：每日18:00 UTC更新前一日的数据。<br /><br />Data Locker中的原始数据报告：每日19:00–23:00 UTC更新前一日的数据。 |
| 历史数据 | N/A |
| 非自然量数据 | 包含 |
| 自然量数据 | 包含 |
| S2S事件 | 如需将<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile#移动设备的s2s事件api">S2S事件</Anchor>计入增量分析，其数据中必须包含广告ID（iOS需包含IDFA，Android需包含GAID）。 |
| 时区 | UTC |

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/audiences-guide">受众共享（Audiences）功能指南</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/blog/tips-strategy/incrementality-testing-for-marketers/">面向营销人员的增量分析测试博客文章</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/blog/topic/incrementality/">增量分析博客文章</Anchor>

<div data-zendesk-anchors="what-is-incrementality=%E4%BB%80%E4%B9%88%E6%98%AF%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90 h_01HB86QVQ0TM91XB8VSZYD42ZA=%E4%BB%80%E4%B9%88%E6%98%AF%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90 incrementality-experiments=%E5%A2%9E%E9%87%8F%E5%AE%9E%E9%AA%8C h_01HB86QVQ0HR436K24V3SQXVXT=%E5%A2%9E%E9%87%8F%E5%AE%9E%E9%AA%8C calculation-methodology=%E8%AE%A1%E7%AE%97%E6%96%B9%E6%B3%95 h_01HB86QVQ0FYTCEVATBEC91ZC1=%E8%AE%A1%E7%AE%97%E6%96%B9%E6%B3%95 h_01HB86QVQ0SMJFEPJ8048NBQTN=lift h_01HB86QVQ1MREDW50YTKSY2KZJ=%E6%B3%A8%E6%84%8F ittbased-lift=%E5%9F%BA%E4%BA%8Eitt%E7%9A%84%E5%A2%9E%E9%87%8F%E8%AE%A1%E7%AE%97 h_01HB86QVQ1NGWZM604A45K03TA=%E5%9F%BA%E4%BA%8Eitt%E7%9A%84%E5%A2%9E%E9%87%8F%E8%AE%A1%E7%AE%97 reachbased-lift=%E5%9F%BA%E4%BA%8E%E8%A7%A6%E8%BE%BE%E7%9A%84%E5%A2%9E%E9%87%8F%E8%AE%A1%E7%AE%97 h_01HB86QVQ1N67SFWKRG1BKZE5A=%E5%9F%BA%E4%BA%8E%E8%A7%A6%E8%BE%BE%E7%9A%84%E5%A2%9E%E9%87%8F%E8%AE%A1%E7%AE%97 best-practices=%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5 h_01HB86QVQ1RDMFT5FH53BYDNSV=%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5 h_01HB86QVQ1K2SPBXTG67B5PV33=statistical-significance h_01HB86QVQ1CAZ0ZDJDKPC1B36S=scaled-control-group h_01HB86QVQ16EZVAATG4DPTDVTQ=%E7%A4%BA%E4%BE%8B incrementality-dashboard=%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90%E9%9D%A2%E6%9D%BF h_01HB86QVQ10C1YHC8HZ9Z8T089=%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90%E9%9D%A2%E6%9D%BF h_01HB86QVQ1ECVT0BT4GYC81DH4=accessing-the-dashboard h_01HB86QVQ1JN8SPHXJGHT4NFSB=a-tour-of-the-dashboard ::3b361a96=%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90%E9%9D%A2%E6%9D%BF ::6ba593ae=%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90%E9%9D%A2%E6%9D%BF raw-data-reports=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01HB86QVQ27FXXBRSH2V8ZK78X=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01HB86QVQ24932F7CHY666730J=available-reports h_01HB86QVQ2YXRVFKEE20E787BK=report-logic h_01HB86QVQ2VK6TX3CSA4S6QSKZ=data-characteristics-and-fields fields-unique-to-incrementality-per-report-type=%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90%E4%B8%93%E5%B1%9E%E5%AD%97%E6%AE%B5%E6%8C%89%E6%8A%A5%E8%A1%A8%E7%B1%BB%E5%9E%8B%E5%8C%BA%E5%88%86 h_01HB86QVQ2CAN02B8GWEZTTTVW=%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90%E4%B8%93%E5%B1%9E%E5%AD%97%E6%AE%B5%E6%8C%89%E6%8A%A5%E8%A1%A8%E7%B1%BB%E5%9E%8B%E5%8C%BA%E5%88%86 other-incrementality-report-fields-per-report-type=%E5%85%B6%E4%BB%96%E5%A2%9E%E9%87%8F%E6%8A%A5%E5%91%8A%E5%AD%97%E6%AE%B5%E6%8C%89%E6%8A%A5%E5%91%8A%E7%B1%BB%E5%9E%8B h_01HB86QVQ221QK6WYRZQ3MJDSY=%E5%85%B6%E4%BB%96%E5%A2%9E%E9%87%8F%E6%8A%A5%E5%91%8A%E5%AD%97%E6%AE%B5%E6%8C%89%E6%8A%A5%E5%91%8A%E7%B1%BB%E5%9E%8B incrementality-specifications-and-limitations=%E5%A2%9E%E9%87%8F%E5%8A%9F%E8%83%BD%E7%89%B9%E6%80%A7%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HB86QVQ2W6X5Z485WM371GGE=%E5%A2%9E%E9%87%8F%E5%8A%9F%E8%83%BD%E7%89%B9%E6%80%A7%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HE7RBMSE1RHVSJC7B7FZG8SJ=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

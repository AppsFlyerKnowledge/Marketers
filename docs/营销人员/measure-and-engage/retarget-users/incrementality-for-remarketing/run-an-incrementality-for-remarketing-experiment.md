---
title: 增量分析实验实操指南
metadata:
  keywords:
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
  created_at: '2020-10-12T19:26:09Z'
  edited_at: '2026-10-14T10:13:26Z'
  id: 360014225577
  locale: zh-cn
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/zh-cn/articles/360014225577
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 增量分析实验能帮助您了解再营销广告的真实效果。本文将为您介绍增量分析实验中所涉及的各项操作。

![KB_toggle_final.jpg](https://files.readme.io/4de8c3ff1edaaae77fc0571de6125b25c884bcc4e4ac67471fc90610298866e1-30780522054801.jpg)

## 增量分析实验简介

<Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview">增量</Anchor>测试功能可通过A/B测试精确衡量广告投放的增效幅度——即对比投放广告与不投放广告时的转化量差异，帮助您了解再营销广告的真实效果。

您可以从增量实验的结果中攫取非常关键的信息，帮助您了解营销投入所产出的真实价值。您可以通过增量分析测试客观地观测到具体流量入口和广告系列的效果，从而优化预算分配和广告投放。

AppsFlyer的增量分析测试从人群包创建开始，该流程完全自动化，非常易于上手。打开“衡量增量效果”开关后，AF就会自动将新建的人群包拆分到对接的渠道和对照组。对照组会保留相关人群包中的一部分流量不发送给渠道，这是增量测试中必不可少的部分。人群包保存成功后，AF就会自动创建增量分析实验。在渠道侧投放广告，并将相关的广告系列正确关联到增量分析实验后，您就能在增量分析面板中看到相关实验的结果。

## 启用方式

如需进一步了解各步骤的详细信息，请参考下文的[设置实验](/docs/run-an-incrementality-for-remarketing-experiment#设置实验)部分。

|  | 步骤 |
| --- | --- |
| 1 | [**确定测试目标**](/docs/run-an-incrementality-for-remarketing-experiment#know-your-test-objectives)<br /><br />请清晰地定义您的测试目标以及结果假设，以提升实验结果在实际决策中的实用性。 |
| 2 | [**创建并拆分目标受众的人群包**](/docs/run-an-incrementality-for-remarketing-experiment#create-the-target-audience-and-split-groups)<br /><br />在<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide">受众共享</Anchor>面板中：<ul><li>配置相关人群包。</li><li>将人群包关联到广告平台。</li><li>打开增量分析开关后（仅限购买了增量分析功能的客户在2023年1月11日以后创建的人群包）AF会自动将该人群包拆分到测试组和对照组。<br />AppsFlyer的受众共享面板会将测试组的用户上传到广告平台，并保留对照组的用户。</li></ul> |
| 3 | [**投放广告并开启实验**](/docs/run-an-incrementality-for-remarketing-experiment#launch-the-campaign-and-experiment)<ul><li>在广告平台上面向人群包中的目标受众创建并投放广告系列。</li><li>AF会自动创建增量分析实验（仅限购买了增量分析功能的客户）。</li></ul>测试组的用户会看到广告，但对照组的用户不会。 |
| 4 | [**分析结果**](/docs/run-an-incrementality-for-remarketing-experiment#analyze-the-results)<ul><li>增量分析会呈现在<Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview#增量分析面板">增量分析面板</Anchor>中。</li><li>设备层级用户数据会呈现在<Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview#原始数据报告">增量分析原始数据报告</Anchor>中（通过Data Locker拉取）。</li></ul>设计合理的增量分析实验能够产出有价值的关键信息，帮助您优化营销投放，充分提升广告效果。比如帮助您发现对某个目标人群最有效的文案、素材、推广活动、媒体渠道等等。 |

## 设置实验

<div id="know-your-test-objectives" />

<Accordion title="确定测试目标">

与其他类型的实验一样，您需要在增量分析实验中准确界定您的测试对象（变量）以及预期结果（假设）。下表列出了实验设计的指导原则和推荐配置：

| 变量/假设 | 指导原则和推荐配置 |
| --- | --- |
| 适用对象 | 描述您要测试的目标人群。在AppsFlyer受众共享面板中选择一个现有人群包或根据您的要求创建一个新的人群包。 |
| 受众数量 | 选择一个基数较大人群包以及转化率较高的事件。样本量越大越有可能产出<Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview#statistical-significance">有效结果</Anchor>。<br /><br />**推荐配置：** 选择不低于5万名用户的人群包，以1：3的比例拆分到广告平台和对照组。 |
| Campaign | 描述相关的广告系列（文案、奖励等）。 |
| 对照组占比 | AF会将对照组自动设置为相关人群包的15%（推荐配置为15%到25%）。 |
| 测试组 | 确定您要测试的广告平台。测试组的流量会在广告平台之间平均分配（您也可以手动调整各平台收到的流量比例）。<br /><br />**推荐配置：** 1-3个广告平台 |
| 假设 | 定义该实验的预期结果。<br /><br />在测试开始前就让您预测测试结果看起来可能不合常理，但结果假设是实验设计中极为重要的元素。有了结果假设，您才能解读实验结果。<br /><br />**推荐配置：** 使用确切的百分比值来设置一个易于测试的假设结果，避免模糊的预估值。使用场景示例:<ul><li>“***超过15%的用户会购买升级产品***”是一个易于测试的假设结果。</li><li>“***购买升级产品的用户会有大幅提升***”是一个较难测试的假设结果。</li></ul> |

> 📄 **示例**
>
> 根据上文所述的指导原则定义的实验示例如下：
>
>
>
> | 变量/假设 | 示例 |
> | --- | --- |
> | 适用对象 | 完成了注册但未购买的用户 |
> | 受众数量 | 100,000 |
> | Campaign | 在指定时段内向完成购买的用户提供优惠券的广告系列 |
> | 对照组占比 | 相关人群包中15%的流量 |
> | 测试组 | 将其余用户分别发送到：<br /><br />* 广告平台A（42%的流量）<br />* 广告平台B（43%的流量） |
> | 假设 | 测试组中与再营销广告互动并完成购买的用户比例会比对照组高10%。 |

</Accordion>

<div id="create-the-target-audience-and-split-groups" />

<Accordion title="创建并拆分目标受众的人群包">

测试目标设定完毕后，您需要配置用于测试的人群包：

1. 在AppsFlyer受众共享面板中<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#创建并管理人群包">创建人群包</Anchor>（或选择一个符合实验要求的现有人群包）。
2. 在**连接**选项卡中为指定人群包完成以下配置：
   * 将该人群包关联到1-3个广告平台。
   * 确保<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#audience-split-and-control-groups">拆分人群包</Anchor>开关已打开（**对于购买了增量分析功能的客户在2023年1月11日以后创建的人群包，该开关会自动打开**）。  
     ![Measure_inc_impact_toggle.jpg](https://files.readme.io/a04b3be68fcc00d62e6a92391fbbea685ca2bfcbf83bd5678660c6a1b8c58fc2-30780493858065.jpg)
   * 对照组默认设为15%（推荐）。
   * 人群包中的其余流量会自动平均分配到您指定的渠道。
     * 各拆分比例（包括对照组）的加总必须为100%。

人群包拆分完毕并成功保存后，AF会自动开启增量分析实验（仅限购买了增量分析功能的客户）。这些实验会以“[Auto]”为标题前缀呈现在增量分析面板中。

![Auto_before_title.jpg](https://files.readme.io/fdab39eee29240ae0d9b907f7c6504a9e08e470454d5f8e43933512c65db15d4-30780522066833.jpg)

**重要说明：**

* 实验期间切勿更改人群包配置。更改渠道、人群包名称或其他设置会导致统计结果不准确。  
  **推荐方式：** 即使您需要在实验结束后更改其中的人群包定义，也必须先创建该人群包的副本，然后在副本中进行相关修改。这是为了确保增量分析面板中历史数据的完整性。
* 更改现有人群包的拆分比例和渠道配置会自动终止正在进行中的增量分析实验，并创建新实验。
* #### 检查人群扩展功能的使用情况：

Meta ads和Google Ads提供的可选功能可让广告主将相关广告投放到指定的人群包之外的用户，以扩大广告的触达范围。如果您启用了该功能，会使增量分析实验产生偏差，导致结果不准确。**因此请务必关闭该功能。**

该功能在Meta ads中称为“Advantage custom audience”，在广告组级别设置，且默认打开。

<Image alt="image__4_.png" src="https://files.readme.io/a0bee1bbb2c6521007146a5ac70de52ce821f459fd2aece127a97a2e0b75c93d-30780493862033.png" width="458px" />  
该功能在Google Ads中成为“Audience expansion”。

<Image alt="Google_Ads_Incrementality_limitation_cropped.jpg" src="https://files.readme.io/042aac534d0a527753b643bb63a52f59889219ebda922cc04f8a61c5984afb80-30780493867409.jpg" width="436px" />

</Accordion>

<div id="launch-the-campaign-and-experiment" />

<Accordion title="投放广告并开启实验">

**请完成以下操作：**

#### 1. 在广告平台中配置广告系列

首先，您需要创建一个面向指定人群的广告系列，然后将其投放到广告平台（需要对相关人群包关联到的每个广告平台都完成该操作）。

* <strong>重要提示！</strong>为了得到准确的测试结果，请务必将广告系列配置为**仅**投放给测试人群包中的用户，切勿投放到其他来源的用户。
* 新建的测试人群包对接到相关广告平台最多可能需要24小时。

#### 2. 确保关联到增量实验的广告系列正确无误。

您每次创建新的人群包并打开其“衡量增量效果”开关时（或对现有人群包打开该开关时），AF会自动开启新的增量分析实验，并将相关性最高的广告系列自动关联到该实验，但您可以手动更改关联的广告系列。

**关联/更改广告系列的方法如下：**

1. 进入**增量分析面板** > 需要调整的实验 > 点击**编辑实验**

<Image alt="Edit_experiment.jpg" src="https://files.readme.io/f478737e2a8db560a5ea33b287fe8f41587ec1f743c1bc01ba15ab6ce72478e9-30780493873425.jpg" width="642px" />

或

在**受众共享**面板中找到您需要的人群包，然后点击“增量分析”一栏中的 **+ 关联广告系列**。

<Image alt="Link_campaign__audiences_status_.jpg" src="https://files.readme.io/5da762448fb731843fef0aec66ae826ed6922a5dd213a78ccd93f544b21fcfdc-small-30780522084625.jpg" width="768px" />

界面会弹出“关联广告系列”窗口。

<Image alt="Link_campaign_to_experiment_window.jpg" src="https://files.readme.io/9492444847bfc6a26778624d72d5b468acc62b705530db66d0bd0fdff89f5e89-30780493883409.jpg" width="506px" />

2. 为每个广告平台选择相关的广告系列

**请注意：** 下拉菜单中的选项来自渠道侧的广告系列信息。该数据可用时，下拉菜单中广告系列的排序标准为：定向投放到该人群包的可能性。默认预选最优推荐项。

3. 点击**保存**。

保存完毕即表示该广告系列已成功关联到实验。

#### 手动创建实验

如果您购买了增量分析产品且您的人群包添加日期在2023年1月11日之后，则无需手动创建实验。AF会针对您的人群包自动创建实验，这些实验会以“[Auto]”为标题前缀呈现在增量分析面板中。如果您需要针对2023年1月11日以前添加的人群包手动创建实验，请完成以下各步骤的操作。

**请按以下步骤手动创建新的增量分析实验：**

* 从AppsFlyer后台的侧边栏中选择**优化** > **增量分析**。
* 在**增量分析实验**页面中点击**新实验**按钮。
* 按页面向导工具的提示创建相关实验。该流程中的每一步都会有详细说明。

  > 📘 **注意**
  >
  > [<Image alt="" src="https://files.readme.io/e956b50df1931b190206f42b48a8f2f061937fe1f25c96801a416d287d7eb3f5-30780493888273.png" width="603px" />](https://files.readme.io/e956b50df1931b190206f42b48a8f2f061937fe1f25c96801a416d287d7eb3f5-30780493888273.png)
  >
  > 进入第2步时，页面向导工具会让您选择**实验目标人群的起始日期**。
  >
  > 该日期默认设置为该人群包最初拆分到对照组的日期。为了确保实验结果的准确性，在发生以下任一情况时，您必须更改该日期：
  >
  > * 如果您更改了选定人群包的定义（即<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#规则组合说明">人群分组规则组合</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#user-identifier-device-id-vs-customer-id">用户标识符</Anchor>等）→ 请将该日期改为人群包定义最近一次变更的日期。
  > * 如果您要使用现有的人群包来测试新投放的广告系列 →  请将此日期更改为新广告系列的投放日期。
  >
  > **页面向导第3步 – 设置目标**
  >
  > ![Step_3_Set_targets.jpg](https://files.readme.io/9c58ad61463b1751f5ad8b2c5235d6d61b13baa156db56d5edeb156debbcfeaa-30780522104081.jpg)
  >
  > 上图显示了目标应用和KPI的配置界面。
  >
  > **请注意：** 即使您没有选择其他KPI，仍能在增量分析实验结束后看到所有KPI。
  >
  > **页面向导第4步–检查配置**
  >
  > [<Image alt="" src="https://files.readme.io/75c90dc66cff6abc772a352d81b6b57498e5915da66efaa83a754d9a5a08be70-30780522113681.png" width="583px" />](https://files.readme.io/75c90dc66cff6abc772a352d81b6b57498e5915da66efaa83a754d9a5a08be70-30780522113681.png)
  >
  > 进入第4步时，页面向导工具会让您设置**实验时长**。
  >
  > * 实验时长默认设为30天，从实验创建之日开始计算。这是AF推荐的最短实验时长。
  > * 如果您想要让该实验一直进行下去，请选择**无限延续该实验**选项（之后如要停止该实验，需手动将其关闭）。


</Accordion>

<div id="analyze-the-results" />

<Accordion title="分析结果">

关联的广告系列投放到广告平台约48小时后，<Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview#增量分析面板">增量分析面板</Anchor>中就会呈现最初的实验结果（<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#eod">每日</Anchor>更新一次）。<Anchor target="_blank" href="/marketers/zh/docs/understand-incrementality-for-remarketing-experiment-alerts">实验页面会显示提示消息</Anchor>，帮助您找出那些会影响准确率的问题，并提出相应的解决方法。

您可以通过Data Locker拉取<Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview#原始数据报告">增量分析原始数据报告</Anchor>。

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/audiences-guide">受众共享（Audiences）功能指南</Anchor>

<div data-zendesk-anchors="overview=%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90%E5%AE%9E%E9%AA%8C%E7%AE%80%E4%BB%8B h_01HARVCSMM80QXXXKJC8TX7CKC=%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90%E5%AE%9E%E9%AA%8C%E7%AE%80%E4%BB%8B get-started=%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HARVCSMMYJVN6GJ3TB46P8AC=%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F set-up-the-experiment=%E8%AE%BE%E7%BD%AE%E5%AE%9E%E9%AA%8C h_01HARVCSMMMAJ6VTYHZ2ZJ5HNS=%E8%AE%BE%E7%BD%AE%E5%AE%9E%E9%AA%8C h_01HARVCSMM9P2HN5WA9C16PA5E=know-your-test-objectives h_01HARVCSMM2THH54JH58GM1K57=%E7%A4%BA%E4%BE%8B h_01HARVCSMM77RV7NM9K7D5FJM5=create-the-target-audience-and-split-groups check-for-audience-expansion-features=%E6%A3%80%E6%9F%A5%E4%BA%BA%E7%BE%A4%E6%89%A9%E5%B1%95%E5%8A%9F%E8%83%BD%E7%9A%84%E4%BD%BF%E7%94%A8%E6%83%85%E5%86%B5 h_01HARVCSMMXNE4NCWSQZ9SHK1J=%E6%A3%80%E6%9F%A5%E4%BA%BA%E7%BE%A4%E6%89%A9%E5%B1%95%E5%8A%9F%E8%83%BD%E7%9A%84%E4%BD%BF%E7%94%A8%E6%83%85%E5%86%B5 h_01HARVCSMMH11D6RKDZQZ3WVZ6=launch-the-campaign-and-experiment 1-configure-campaigns-on-ad-networks=1-%E5%9C%A8%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E4%B8%AD%E9%85%8D%E7%BD%AE%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 h_01HARVCSMMVXJWCT2BX3CVC3VT=1-%E5%9C%A8%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E4%B8%AD%E9%85%8D%E7%BD%AE%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 2-link-campaigns-to-experiment=2-%E7%A1%AE%E4%BF%9D%E5%85%B3%E8%81%94%E5%88%B0%E5%A2%9E%E9%87%8F%E5%AE%9E%E9%AA%8C%E7%9A%84%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E6%AD%A3%E7%A1%AE%E6%97%A0%E8%AF%AF h_01HARVCSMNAWNYEY83NC6Y5XV4=2-%E7%A1%AE%E4%BF%9D%E5%85%B3%E8%81%94%E5%88%B0%E5%A2%9E%E9%87%8F%E5%AE%9E%E9%AA%8C%E7%9A%84%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E6%AD%A3%E7%A1%AE%E6%97%A0%E8%AF%AF manually-create-an-experiment=%E6%89%8B%E5%8A%A8%E5%88%9B%E5%BB%BA%E5%AE%9E%E9%AA%8C h_01HARVCSMNZVWK8Z36ER1HH10W=%E6%89%8B%E5%8A%A8%E5%88%9B%E5%BB%BA%E5%AE%9E%E9%AA%8C h_01HARVCSMN5944HRD9N7YEKT3P=%E6%B3%A8%E6%84%8F h_01HARVCSMNS961WKFX280J3R2X=analyze-the-results h_01HE7RBMSE1RHVSJC7B7FZG8SJ=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

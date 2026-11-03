---
title: 增量分析实验提醒消息
metadata:
  keywords:
    - Premium Feature
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2023-03-05T12:31:35Z'
  edited_at: '2026-10-14T10:03:02Z'
  id: 13479545385489
  locale: zh-cn
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/zh-cn/articles/13479545385489
---
> **概要：** 本文解释了增量分析实验中会出现的提醒消息，解决消息中提示的问题有助于保障实验结果的准确性。

![exp_alerts_doctored.jpg](https://files.readme.io/3981e4a4bd66206d9b5986cc1b573f67e1ab836042a1f73518f48a1ea17b6568-35266706078481.jpg)

## 增量分析实验中的提醒消息简介

<Anchor target="_blank" href="/marketers/zh/docs/run-an-incrementality-for-remarketing-experiment">设置增量分析实验</Anchor>后，您可能会在增量分析面板中看到一些提醒消息。这些消息旨在帮助您找出影响实验结果完整性和准确性的问题所在。这些消息可提供相关问题的具体信息以及推荐的解决方式，以确保准确的实验结果。本文全面综述了各类提醒消息，以及对应的推荐解决方式。

## 提醒消息类型

增量分析实验的提醒罅隙分为以下几类：

<div id="experiment-setup" />

<Accordion title="实验设置">

#### 人群包删除或对照组移除

关联到相关实验的人群包被删除，或拆分人群包中的对照组被移除。若发生这两种情况，您在访问实验页面时会看到404报错。

**请按以下方式解决此问题并修复实验结果：**  
如果**人群包已删除** - 请联系您的CSM，让他们帮您手动复原相关人群包。  
如果**对照组已移除** - 请重新拆分相关人群包，以之前的拆分比例设置对照组。

#### 发现更合适的广告系列（仅限SRN）

这条提醒消息仅适用于自归因平台（SRN）。相关实验已有关联的广告系列，但根据数据显示有其他更适合该人群包的广告系列。  
“更合适的广告系列”是指在实验期限内处于在投状态，且相较于实验中配置的广告系列来说，该广告系列的定向更贴合测试组用户，更具针对性，且不投放到对照组。

**建议措施：** 检查相关实验是否已关联到合适的广告系列。

**请注意：** 另一种方法是确保该人群包未配置为其他广告系列的定向人群。

#### 无展示（仅限非SRN）

针对非SRN平台上的广告系列进行增量分析实验时，AppsFlyer需要展示数据才能准确计算这些广告系列的增量效果，如果没有展示数据，实验页面中就不会显示实验结果。

这条提醒消息用于说明AppsFlyer未接收到关联到相关实验的广告系列所产生的展示数据。

**建议措施：** 请检查您是否从渠道侧接收到展示数据，以及在测广告系列是否在正常投放广告。

</Accordion>

<div id="experiment-background-environment" />

<Accordion title="实验背景环境">

#### 实验背景中的广告系列（一个或多个）

如果与实验无关的大量级广告系列对于相关人群包的影响远超实验中配置的广告系列，您就会看到这条提醒消息。

原因  
作为实验背景的整体投放中存在与实验无关的广告系列是很常见的，但如果这些广告系列的预算更高或投放强度更大，可能会削弱在测广告系列的影响力，进而使实验结果产生偏差。

**建议措施：**

* 提升测试广告系列的预算，以增强其影响力。
* 检查测试人群包是否与提示中的广告系列定向投放的人群有所重合（可使用受众共享的渠道重合功能查看）。
* 检查测试人群包是否与其他不相关的广告系列有所重合。
* 强化测试人群包的筛选条件。
* 采取措施减轻背景广告系列的影响后，请将实验开始日期设定在配置更改之后。

**请注意：** 建议您尽量减少其他广告系列对测试人群包的定向投放。

</Accordion>

<div id="linked-campaign-performance" />

<Accordion title="关联广告系列的投放效果">

#### 目标人群重合

关联到实验的广告系列所投放的人群有重合。也就是说，相关广告系列的定向配置中包含多个人群包。  
此外，配置到测试广告系列的多个人群包有重合。这会导致相关广告被投放到测试人群包之外，甚至定向到对照组中的用户。

**建议措施：**  
调整该广告系列的定向配置，移除测试人群包以外的其他所有人群包。

#### 对照组在定向投放范围内

这条提醒消息用于说明实验中配置的广告系列正在定向投放给对照组（但应该投放给测试组）。

**原因**

* 相关实验所关联的广告系列不正确。
* 根据渠道侧的配置，该广告系列定向到了测试人群包以外的用户（详见Facebook和Google中的<Anchor target="_blank" href="/marketers/zh/docs/run-an-incrementality-for-remarketing-experiment#检查人群扩展功能的使用情况">人群定向扩展功能</Anchor>）。
* 平台侧未按指定配置进行定向投放。

**建议措施：**  
请检查是否出现了上文所列的情况。如不确定，请联系您的CSM。该问题在某些情况下无法修复，这时您需要创建一个新的增量分析实验，具体取决于相关广告系列在对照组中的曝光度。

如果相关广告系列在对照组中的曝光程度不高，则只需停止对照组的定向投放即可。调整完毕后，请跟进相关实验的面板提示，检查该提醒消息在数天后是否仍然出现。

#### 精细化定向（Detailed targeting）开关处于打开状态

部分广告平台提供精细化定向功能（Detailed targeting），让广告主对相关广告的目标投放群体进行微调。如果实验中的广告系列启用了精细化定向，面板就会显示这条提醒消息。启用该功能后，相关广告系列就能定向投放到指定人群包以外的用户。

**建议措施：** 请确保在渠道侧的配置中，相关广告系列的精细化定向开关处于关闭状态。

#### 活跃度过低

相关广告系列不向目标人群发布广告，或向其发布的广告非常少。

**建议措施：** 检查渠道侧是否出现问题，了解相关广告系列不发布广告的原因。

#### 关联到多个人群包

该广告系列的定向配置中包含多个人群包。这可能会导致相关广告被投放到在测人群包以外的用户或对照组，最终影响测试结果。

**建议措施：**  
配置增量分析实验的最佳方式是使在测广告系列仅针对一个人群包进行定向投放。

#### 定向到人群包以外的用户

除了指定人群包的测试组以外，在测广告系列还同时向其他用户进行定向投放。由于该广告系列向在测人群包以外的无关用户发布广告，而这些用户不会被计入增量分析实验的结果中，导致本应花费在测试上的预算被稀释。

在不相关的用户群体中消耗广告预算时，iROAS和CPiA等与投放成本相关的指标就会出现偏差。增量分析实验在计算这些指标时会使用该广告系列的总体投放成本，包括向在测人群包以外的用户发布广告的成本，但不计入这部分用户的转化。

**原因**

* 相关实验所关联的广告系列不正确。
* 根据渠道侧的配置，该广告系列定向到了测试人群包以外的用户（详见Facebook和Google中的<Anchor target="_blank" href="/marketers/zh/docs/run-an-incrementality-for-remarketing-experiment#检查人群扩展功能的使用情况">人群定向扩展功能</Anchor>）。
* 平台侧未按指定配置进行定向投放。

**建议措施：**  
请确保相关广告系列的定向配置中仅包含在测人群包，且不允许投放到该人群包以外的用户。

</Accordion>

<div data-zendesk-anchors="about-experiment-alerts=%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90%E5%AE%9E%E9%AA%8C%E4%B8%AD%E7%9A%84%E6%8F%90%E9%86%92%E6%B6%88%E6%81%AF%E7%AE%80%E4%BB%8B h_01HNZPQJDA5D7Q04CDKMYCW763=%E5%A2%9E%E9%87%8F%E5%88%86%E6%9E%90%E5%AE%9E%E9%AA%8C%E4%B8%AD%E7%9A%84%E6%8F%90%E9%86%92%E6%B6%88%E6%81%AF%E7%AE%80%E4%BB%8B types-of-alerts=%E6%8F%90%E9%86%92%E6%B6%88%E6%81%AF%E7%B1%BB%E5%9E%8B h_01HE7R6CQ5R9HAYG83B3903AY8=%E6%8F%90%E9%86%92%E6%B6%88%E6%81%AF%E7%B1%BB%E5%9E%8B h_01HE7R6CQ5SNX6VYFD18501JYT=experiment-setup audience-deletion-or-control-group-removal=%E4%BA%BA%E7%BE%A4%E5%8C%85%E5%88%A0%E9%99%A4%E6%88%96%E5%AF%B9%E7%85%A7%E7%BB%84%E7%A7%BB%E9%99%A4 h_01HE7R6CQ5DM1QNN1E55TGDKKH=%E4%BA%BA%E7%BE%A4%E5%8C%85%E5%88%A0%E9%99%A4%E6%88%96%E5%AF%B9%E7%85%A7%E7%BB%84%E7%A7%BB%E9%99%A4 more-suitable-campaigns-srns-only=%E5%8F%91%E7%8E%B0%E6%9B%B4%E5%90%88%E9%80%82%E7%9A%84%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E4%BB%85%E9%99%90srn h_01HE7R6CQ518RS50X87243M7BV=%E5%8F%91%E7%8E%B0%E6%9B%B4%E5%90%88%E9%80%82%E7%9A%84%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E4%BB%85%E9%99%90srn no-impressions-received-nonsrns-only=%E6%97%A0%E5%B1%95%E7%A4%BA%E4%BB%85%E9%99%90%E9%9D%9Esrn h_01HE7R6CQ57DV8D642APE01JV0=%E6%97%A0%E5%B1%95%E7%A4%BA%E4%BB%85%E9%99%90%E9%9D%9Esrn h_01HE7R6CQ5XFAE56PTX6RRZD5J=experiment-background-environment background-campaign-one-or-multiple=%E5%AE%9E%E9%AA%8C%E8%83%8C%E6%99%AF%E4%B8%AD%E7%9A%84%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E4%B8%80%E4%B8%AA%E6%88%96%E5%A4%9A%E4%B8%AA h_01HE7R6CQ5AZW1RB7XJH4GEEBT=%E5%AE%9E%E9%AA%8C%E8%83%8C%E6%99%AF%E4%B8%AD%E7%9A%84%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E4%B8%80%E4%B8%AA%E6%88%96%E5%A4%9A%E4%B8%AA h_01HE7R6CQ5C6009QZK6TQS6QGC=linked-campaign-performance audience-overlap=%E7%9B%AE%E6%A0%87%E4%BA%BA%E7%BE%A4%E9%87%8D%E5%90%88 h_01HE7R6CQ6X5C0D4E519W535PH=%E7%9B%AE%E6%A0%87%E4%BA%BA%E7%BE%A4%E9%87%8D%E5%90%88 control-group-is-targeted=%E5%AF%B9%E7%85%A7%E7%BB%84%E5%9C%A8%E5%AE%9A%E5%90%91%E6%8A%95%E6%94%BE%E8%8C%83%E5%9B%B4%E5%86%85 h_01HE7R6CQ5NFH58H8ZNRG6E4MG=%E5%AF%B9%E7%85%A7%E7%BB%84%E5%9C%A8%E5%AE%9A%E5%90%91%E6%8A%95%E6%94%BE%E8%8C%83%E5%9B%B4%E5%86%85 detailed-targeting-toggle-is-enabled=%E7%B2%BE%E7%BB%86%E5%8C%96%E5%AE%9A%E5%90%91detailed-targeting%E5%BC%80%E5%85%B3%E5%A4%84%E4%BA%8E%E6%89%93%E5%BC%80%E7%8A%B6%E6%80%81 h_01HKSTD08WK37RHM5DM922GGWF=%E7%B2%BE%E7%BB%86%E5%8C%96%E5%AE%9A%E5%90%91detailed-targeting%E5%BC%80%E5%85%B3%E5%A4%84%E4%BA%8E%E6%89%93%E5%BC%80%E7%8A%B6%E6%80%81 low-activity=%E6%B4%BB%E8%B7%83%E5%BA%A6%E8%BF%87%E4%BD%8E h_01HE7R6CQ6C76SZEAN0R93H9QN=%E6%B4%BB%E8%B7%83%E5%BA%A6%E8%BF%87%E4%BD%8E multiple-audiences-connected=%E5%85%B3%E8%81%94%E5%88%B0%E5%A4%9A%E4%B8%AA%E4%BA%BA%E7%BE%A4%E5%8C%85 h_01HKSTFSKDTD2Z8HKCCX2MWBJQ=%E5%85%B3%E8%81%94%E5%88%B0%E5%A4%9A%E4%B8%AA%E4%BA%BA%E7%BE%A4%E5%8C%85 outofaudience-targeting=%E5%AE%9A%E5%90%91%E5%88%B0%E4%BA%BA%E7%BE%A4%E5%8C%85%E4%BB%A5%E5%A4%96%E7%9A%84%E7%94%A8%E6%88%B7 h_01HE7R6CQ6TVCGW5X8GBX0AJKS=%E5%AE%9A%E5%90%91%E5%88%B0%E4%BA%BA%E7%BE%A4%E5%8C%85%E4%BB%A5%E5%A4%96%E7%9A%84%E7%94%A8%E6%88%B7" />

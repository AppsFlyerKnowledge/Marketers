---
title: SKAN模型推算数据
metadata:
  keywords:
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T12:02:02Z'
  edited_at: '2026-10-14T10:12:49Z'
  id: 7086372479505
  locale: zh-cn
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/zh-cn/articles/7086372479505
---
> **概要**：AppsFlyer模型可以推算出基础SKAN归因无法提供的汇总数据。

<div id="overview" />

## 速览

SKAN的数据上报会受到以下规则的限制：

* SKAN依靠转化值（CV）完成归因，而转化值最多只能包含6比特，也就是说最多只能有64个值（0-63）。
* 有些情况下Apple为了保护用户隐私而不上报实际CV（并返回“null”值）。
* 数据可用范围限制在12-72小时的用户行为窗口期内，无法得知完整的用户生命周期价值（LTV）。

SKAN模型推算数据可通过以下方式解决上述问题：

* AppsFlyer使用机器学习技术和贝叶斯统计法，基于AppsFlyer上报数据以及SKAN数据来推算隐藏的数据点。
* 广告主能够更全面地了解LTV维度的应用使用情况和广告投放效果。

**请注意**：注意：转化值映射构架若发生更改，AppsFlyer需要2天的时间来准备变更后的模型推算数据。

<div id="modeled-data-types-and-availability" />

## 模型推算的数据类型和可用性

| 数据类型 | 可用性 | 说明 |
| --- | --- | --- |
| null值 | <ul><li>数据总览面板的SSOT视图</li><li>SKAN面板</li><li>SKAN汇总效果报告API（SKAN aggregated performance report API）</li><li>SKAN回传接收日期汇总报告API</li></ul> |  |
| LTV收入 | 数据总览面板的SSOT视图 | 目前可推算7天内的LTV收入。 |
|  | 数据总览面板的SSOT视图 | 目前可推算7天内的LTV收入。 |
| 国家/地区 | 数据总览面板的SSOT视图 |  |

<div id="null-conversion-values" />

<Accordion title="null值">

某些情况下，Apple会为了保护用户隐私而不上报确切的转化值（CV），这时CV值即为null。AppsFlyer会将一个null值记为一次激活。注意事项：

* null值和零值的含义不同：
  * Zero零值：用户激活了应用，但未在用户行为窗口期内完成任何可衡量的操作。因此该指标的准确值就是0，这不是由模型推算出来的值。
  * nullnull值：无法获知用户完成了什么操作，因为Apple未上报CV。
* null值会使您的效果指标失真。为了克服这类问题，更准确地呈现应用使用情况，我们会将通过推算模型将null值转化为0-63的转化值。

模型推算的转化值：

* 我们会根据带有转化值的SKAN激活分布来推算null值激活的确切转化值。这里使用的算法是动态的，会综合考量多种变量。请参考以下示例，了解大致的推算原理：
  * 假设共有100个激活，其中60个为null值、10个为CV=1、5个为CV=3，还有25个为CV=5。
  * 也就是说，共有40个带有转化值的激活，其中25%的转化值为1，12.5%的转化值为3，还有62.5%的转化值为5。
* 如果某个维度的推算数据不可用，则相应的值会显示为N/A。

可根据转化值推算的指标包括：

* 收入
* 事件次数
* eCPA
* ARPU
* ROI
* ROAS（广告支出回报率）

</Accordion>

<div id="revenue-ltv" />

<Accordion title="LTV收入">

[![modeled_d7.png](https://files.readme.io/ec175800b52164844c56743a33fe412eef02c3b76975ca572819535bb5e5eff9-12183780248081.png)](https://files.readme.io/ec175800b52164844c56743a33fe412eef02c3b76975ca572819535bb5e5eff9-12183780248081.png)

SKAN上报机制仅可在SKAN衡量窗口内根据转化值操作台中收入维度的CV配置来提供收入数据。SKAN模型推算机制则能够推算出激活后7天（168小时）内的收入数据。

这一方法的**优势**在于：

对于SKAN 3及之前的版本，模型推算数据可以打破用户行为窗口期的时间限制。

对于SKAN 4+：

* 数据时效性：数据时效性：在第二次SKAN回传送达之前就可以看到LTV收入（回传会有24-144小时的延时）。
* 衡量内容更丰富：即使您使用第二和第三次回传的粗略值来衡量其他指标（如事件和留存），仍可通过模型推算来获取LTV收入数据。
* 数据丰富度数据扩充：如果您使用第二次回传来衡量收入，我们会根据该次回传中的信息来优化模型推算的LTV收入数据，并提供比3个粗略转化值粒度更细的收入数据。

**注意事项**：

* 您在相关应用的SKAN转化值操作台中配置收入后，面板会呈现其LTV收入指标，这个数据包含应用内购买和广告变现的收入。
* 至少需要有14天的收入数据才能呈现LTV收入。举例来说，如果您在2022年11月1日配置了总体收入（Overall Revenue），那么在2022年11月14日之后的激活才有可用的模型推算数据。面板会在出现可用数据后的第8天（即2022年11月22日）呈现这些数据。
* 您可以在激活后的第8天在SSOT面板（微件、图表和表格）中查看LTV收入（目前限激活后7天内的数据）以及下列基于模型推算得出的指标：
  * D7收入
  * D7 ARPU
  * D7毛利
  * D7 ROI
  * D7 ROAS

</Accordion>

这一方法的**优势**在于：

对于SKAN 3及之前的版本，模型推算数据可以打破用户行为窗口期的时间限制。

对于SKAN 4+：

* 数据时效性：数据时效性：在第二次SKAN回传送达之前就可以看到LTV收入（回传会有24-144小时的延时）。
* 数据丰富度

**注意事项**：

* 仅符合以下条件的应用内事件及其指标可用作分组维度：
* 面板会在出现可用数据后的第8天（即2022年11月22日）呈现这些数据。
* 您可以在激活后的第8天在SSOT面板（微件、图表和表格）中查看LTV收入（目前限激活后7天内的数据）以及下列基于模型推算得出的指标：
  * 事件独立用户数
  * 事件转化率（D7）
  * 事件eCPA（D7）
  * 事件收入（D7）


<div id="geo" />

<Accordion title="国家/地区">

SKAN回传不包含国家/地区维度，因此不能使用国家/地区维度对SKAN回传数据进行分组，但AppsFlyer能够通过模型推算得出SKAN激活的国家/地区信息，针对SKAN数据提供国家/地区的分组维度。

通过模型推算得出的国家/地区信息：

* 使用机器学习工具，结合通过AppsFlyer传统模式归因的非自然激活，考量其国家/地区分布情况。
* 请注意/span>：

注意事项：

* AppsFlyer国家/地区模型推算数据的准确率大约在90%左右。如果无法推算出国家/地区信息，则SKAN激活的分组维度显示为None，意即“国家/地区未知”。

</Accordion>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 01H8TZR38AC6P264CGF4PX4SJ5=%E9%80%9F%E8%A7%88 modeled-data-types-and-availability=%E6%A8%A1%E5%9E%8B%E6%8E%A8%E7%AE%97%E7%9A%84%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E5%92%8C%E5%8F%AF%E7%94%A8%E6%80%A7 01H8TZR38A2V9ZSSGKHF3XCX0P=%E6%A8%A1%E5%9E%8B%E6%8E%A8%E7%AE%97%E7%9A%84%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E5%92%8C%E5%8F%AF%E7%94%A8%E6%80%A7 01H8TZR38A4RDX42B7J5X9SPMQ=null-conversion-values 01H8TZR38BG9XEM2FTJADJ27VK=revenue-ltv 01H8TZR38BSFVDSQCH915ACSYH=geo" />

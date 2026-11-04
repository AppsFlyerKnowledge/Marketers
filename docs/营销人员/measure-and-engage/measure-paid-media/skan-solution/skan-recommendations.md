---
title: SKAN推荐设置
metadata:
  keywords:
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T07:56:50Z'
  edited_at: '2026-10-14T10:14:51Z'
  id: 7078169815057
  locale: zh-cn
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/zh-cn/articles/7078169815057
---
> **概要**：概要：AppsFlyer推荐的SKAN设置能帮助您更合理地利用转化值，并获取更准确的激活后用户行为信息。

<div id="overview" />

## 速览

SKAdNetwork（SKAN）是Apple iOS系统的一部分，能让广告主在确保用户隐私的前提下衡量投放效果。SKAN通过数值来衡量激活后的用户行为，这些数值被称为转化值（conversion value，简称CV值），可用的转化值为0-63。

AppsFlyer的转化值操作台具有很强的可配置性，能帮助广告主充分利用SKAN回传。您可以设置每一个CV值需要表达的衡量数据，包括激活后的用户行为和衡量时长。

但由于SKAN的衡量功能有限，使得广告主很难选择衡量对象（比如收入、应用内事件或留存），而且很难高效地利用0-63的CV值。

AppsFlyer的SKAN推荐设置：

* 针对当前的CV设置、CV值利用效率和衡量准确性提出优化建议。
* 帮助您解决CV值设置决策中的一些难题。
* 以您所在的垂类、国家/地区、用户行为以及SKAN和非SKAN应用数据为基础。

<div id="recommendations" />

## 推荐设置

<div id="revenue" />

<Accordion title="收入">

<div id="understanding-revenue-recommendations" />

#### **推荐的收入设置**

准确的收入上报必须以恰当的收入维度CV配置为基础。

收入维度的CV值配置不能保证上报的收入100%准确，SKAN上报的收入可能与实际收入有一些差异。比如，假设实际ARPPU（即AF上报的数据）是$10，但是通过您当前的CV配置上报的SKAN ARPPU可能是$7，也就是说对于每个付费用户，SKAN少上报了$3的收入。

AppsFlyer每天都会检查您的非SKAN收入数据（这个数据是100%准确的），在此基础上生成定制化的推荐设置，您可以用它来改善SKAN上报收入的准确性。这些推荐设置同时也以您在转化值操作台中设置的用户行为窗口期、您所处的垂类、国家/地区和应用用户行为为基础。

推荐设置：

* 能通过准确的收入上报让您对投放效果有更清晰的了解。
* 减少范围使用数量，准确衡量收入，节省CV值的用量。
* 同时涵盖应用内购买和广告收入。

<div id="revenue-recommendations-layout" />

#### **推荐的收入设置布局**

<table><tbody><tr><td colspan="2"><p><img alt="revenue_recommendions_layout.png" src="https://files.readme.io/1595d3f59b6e30154da560a99430e231d8353d1bd54ebed6192ec0f13cd3f5b3-8976338886801.png"/></p></td></tr><tr><td><p><span>A</span></p></td><td><span>您在转化值操作台中设置的用户行为窗口期，SKAN会在此期间衡量收入。</span></td></tr><tr><td><p><span>B</span></p></td><td><span>实际的应用付费用户平均收入（ARPPU）是由AppsFlyer归因模式记录到的精确数据，涵盖自然和非自然用户。</span></td></tr><tr><td><p><span>C</span></p></td><td><p>当前配置的ARPPU（SKAN ARPPU）是指<span>根据您当前在转化值操作台中配置的、用于上报收入的用户行为窗口期和CV值</span>衡量的ARPPU。</p></td></tr><tr><td><span>D</span></td><td><p>详见F和G。</p><p><span><strong>请注意：</strong></span></p></td></tr><tr><td><p><span>E</span></p></td><td><p>近似误差：<span>B和C之间的差异，可能是正误差也可能是负误差，具体取决于上报的SKAN ARPRPU值是偏高还是偏低。</span></p><p><span>比如示例：如果实际ARPPU是$10，SKAN ARPPU是$7，那么近似误差就是上报值偏低30%（每个用户-$3）。</span></p></td></tr><tr><td><p><span>F</span></p></td><td><p>推荐的SKAN收入配置。选择您想要在配置中使用的范围数量。</p></td></tr><tr><td><p><span>G</span></p></td><td><p><span>转化值操作台中的当前收入配置。</span><span></span></p></td></tr></tbody></table>

<div id="using-revenue-recommendations" />

#### **使用推荐的收入设置**

**前期准备： 使用条件：如需使用AppsFlyer推荐的收入设置，必须有至少14天的收入数据。**

<div id="note" />

> 📘 **注意**
>
> 这里使用的收入数据每天都会更新，也就是说系统会使用前15天到前1天内的数据作为当前推荐设置的基础。举例来说，假设今天是8月28日，则当前的推荐设置所使用的数据基础为8月13日到8月27日之间的数据。

**请按以下步骤启用推荐的收入设置：**

1. 进入AppsFlyer后台，然后根据您使用的衡量模式（SKAN 4、自定义或固定模式）分别完成以下操作：
   * **配置** > **SKAN转化值操作台** > **SKAN 4** > **总收入/应用内事件**。
   * **配置** > **SKAN转化值操作台** > **SKAN 4** > **总收入/应用内事件**。
   * **配置** > **SKAN转化值操作台** > **收入**。
2. 如果您已经配置了收入范围，请跳过这一步。如果您还没有配置收入范围，请在这一步完成该配置。  
   配置完毕后，界面会呈现您配置的准确度和近似误差信息。
3. 点击**查看推荐设置**。  
   界面会呈现您当前的配置信息、推荐的收入范围，以及使用推荐设置后的预估上报准确性（近似误差）。不管您是否要更改范围数量，都有对应的推荐设置。
4. 选择一个推荐的范围设置。
5. 点击**使用推荐设置**。
   * 如果您已经在自定义模式中完成了收入配置，推荐设置就会生效。
   * 如果您在固定模式（收入）中完成了收入配置，则需要先将推荐的范围设置记录下来，然后进入**SKAN转化值操作台** > **自定义** > **总收入**，并使用推荐的范围进行配置。
6. 点击**保存**。
   * 如果您后续对收入配置进行了任何更改，可以重新在配置板块下查看新的推荐设置。

</Accordion>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01HGSZ05CH4P8BQT23VYH6DKVP=%E9%80%9F%E8%A7%88 recommendations=%E6%8E%A8%E8%8D%90%E8%AE%BE%E7%BD%AE h_01HGSZ05CHPZKWKY7MR6MA68YZ=%E6%8E%A8%E8%8D%90%E8%AE%BE%E7%BD%AE h_01HGSZ05CH2RG3514N576ZGDFM=revenue understanding-revenue-recommendations=%E6%8E%A8%E8%8D%90%E7%9A%84%E6%94%B6%E5%85%A5%E8%AE%BE%E7%BD%AE h_01HGSZ05CHC93SHP28DN9EK27N=%E6%8E%A8%E8%8D%90%E7%9A%84%E6%94%B6%E5%85%A5%E8%AE%BE%E7%BD%AE revenue-recommendations-layout=%E6%8E%A8%E8%8D%90%E7%9A%84%E6%94%B6%E5%85%A5%E8%AE%BE%E7%BD%AE%E5%B8%83%E5%B1%80 h_01HGSZ05CH5DVKAQ24EED16JRN=%E6%8E%A8%E8%8D%90%E7%9A%84%E6%94%B6%E5%85%A5%E8%AE%BE%E7%BD%AE%E5%B8%83%E5%B1%80 using-revenue-recommendations=%E4%BD%BF%E7%94%A8%E6%8E%A8%E8%8D%90%E7%9A%84%E6%94%B6%E5%85%A5%E8%AE%BE%E7%BD%AE h_01HGSZ05CJ4W0V3Y4XBWRMFW8K=%E4%BD%BF%E7%94%A8%E6%8E%A8%E8%8D%90%E7%9A%84%E6%94%B6%E5%85%A5%E8%AE%BE%E7%BD%AE h_01HGSZCYCWRYEJPWZKDBC9SX8H=%E6%B3%A8%E6%84%8F" />

---
title: 报告拉取限额（频次限制）
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2014-05-01T12:55:30Z'
  edited_at: '2026-10-14T10:13:30Z'
  id: 207034366
  locale: zh-cn
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/zh-cn/articles/207034366
---
> **概要：** 概要：Pull API和导出数据页设有限额（频次限制）机制，即每天可拉取的报告数量有一个上限。

<div id="rate-limits-for-reports" />

## 报告拉取频次限制

AF的每种报告类型都设有一个每日可拉取的报告数量限额。具体限额取决于您订购的产品套餐。

**原理：**

* 代理代理商和广告商有单独的 Pull API 配额。配额适用于每个报告、每天和每个应用，两者适用的方式相同。对于导出数据页的报告，代理商和广告主各自有单独的限额。如果您经常出现超额情况，请联系您的客户经理。
* **广告平台**：广告平台：广告平台拉取的报告不会从广告主的限额中扣除。
* 第[n]天每日限额：限额会在每天UTC时间的00:00刷新。

<div id="aggregated-and-analytics-reports" />

### 汇总及分析报告

| 数据传输工具 | 限额 |
| --- | --- |
| Pull API汇总报告 | <ul><li>相关日期范围内最多2天：<ul><li>一个应用下的每种报告每分钟最多1次</li></ul></li><li>第3天及之后的拉取频次限制如下：<ul><li>每个账户每天最多120次</li><li>每个应用每天最多24次</li></ul></li></ul> |
| 导出数据页汇总报告 | 无上限 |
| Master API | 无上限 |
| Cohort API | 每个帐户每分钟60次 |
| SKAN汇总报告 | 每个帐户每分钟60次 |

<div id="raw-data" />

### 原始数据

* Pull API和原始数据导出页各自有单独的限额。
* 代理商和广告商有单独的 Pull API 配额。代理拉取的报告也会从广告主的限额中扣除。唯一的例外是代理使用广告商的 API 令牌而不是他们自己的令牌，在这种情况下，请求与广告商请求无法区分，并计入广告商配额。对于导出数据页的报告，代理商和广告主各自有单独的限额。
* API的拉取频次限额分为以下几个层级：
  * 报告
  * 第[n]天
  * 应用层级
  * 账户层级
* 广告主的频次限额取决于其购买的AppsFlyer套餐。**请注意**：请注意：需要订阅高阶付费功能才能拉取的报告也有拉取频次限额。
* 广告网络回发报告的每日配额如下表所示。

为了便于理解，请参考表格下方的常见问题解答部分。

<div id="ad-network-postback-reports-daily-quota" />

#### 广告网络回发报告每日配额

广告网络可以调出以下回发报告类型：

| 回发组 | 报告类型  <br />（每种报告类型有单独的限额） | 应用级每日配额 | 帐户级别的每日配额 |
| --- | --- | --- | --- |
| 归因回贴 | <ul><li>激活量</li><li>再营销转化</li></ul> | 24 | 120 |
| 应用内事件的回发 | <ul><li>应用内事件</li><li>再营销应用内事件</li></ul> | 12 | 60 |

<div id="faq" />

#### **常见问题解答**

* 问题：问：对于某个具体应用，我能不能使用Pull API拉取24个自然激活报告，再从原始数据导出页拉取24个报告？答：可以，  
  A：是因为每种报告工具的限额是单独计算的。
* 问题：问：对于某个具体应用，我能不能从原始数据导出页拉取24个自然激活报告、24个非自然激活报告以及24个再营销转化报告？  
  A：是因为每一种报告的限额是单独计算的。
* 问题：问：我的账户下有25个应用。我能不能针对每个应用各拉取10个自然激活报告？答：不能，  
  A：因为这样总共需要拉取250个报告，超出了120的账户层级限额。
* 问题：代理生成的 Pull API 报告是否计入广告商的配额？  
  A：不。代理和广告商有单独的 Pull API 配额。代理拉取的报告也会从广告主的限额中扣除。唯一的例外是代理使用广告商的 API 令牌而不是他们自己的令牌，在这种情况下，这些请求被计为广告商请求。

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/data-availability-windows">数据可用期限</Anchor>

<div data-zendesk-anchors="rate-limits-for-reports=%E6%8A%A5%E5%91%8A%E6%8B%89%E5%8F%96%E9%A2%91%E6%AC%A1%E9%99%90%E5%88%B6 h_01H9JNZFPSVXPKMEVR1ZR6PSYG=%E6%8A%A5%E5%91%8A%E6%8B%89%E5%8F%96%E9%A2%91%E6%AC%A1%E9%99%90%E5%88%B6 aggregated-and-analytics-reports=%E6%B1%87%E6%80%BB%E5%8F%8A%E5%88%86%E6%9E%90%E6%8A%A5%E5%91%8A h_01H9JNZFPS62A5CFWSXVPN8XM5=%E6%B1%87%E6%80%BB%E5%8F%8A%E5%88%86%E6%9E%90%E6%8A%A5%E5%91%8A raw-data=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE h_01H9JNZFPSPYWBB2MCZV2R2KX1=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE ad-network-raw-data-daily-quota=%E5%B9%BF%E5%91%8A%E7%BD%91%E7%BB%9C%E5%9B%9E%E5%8F%91%E6%8A%A5%E5%91%8A%E6%AF%8F%E6%97%A5%E9%85%8D%E9%A2%9D h_01H9JNZFPSYXZNW81BZTRDS576=%E5%B9%BF%E5%91%8A%E7%BD%91%E7%BB%9C%E5%9B%9E%E5%8F%91%E6%8A%A5%E5%91%8A%E6%AF%8F%E6%97%A5%E9%85%8D%E9%A2%9D faq=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01H9JNZFPT76RAV8JBTY2K75V4=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HE7SW3VWRNVY1WFB4YCSAVY6=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

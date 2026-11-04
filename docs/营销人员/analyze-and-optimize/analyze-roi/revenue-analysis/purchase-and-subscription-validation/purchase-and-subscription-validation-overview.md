---
title: 购买和订阅验证 - 概述
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-20T16:30:47Z'
  edited_at: '2026-10-14T10:01:20Z'
  id: 42120228484241
  locale: zh-cn
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/zh-cn/articles/42120228484241
---
> **概要：** 如何通过AppsFlyer进行购买与订阅收入，以及两种解决方案的对比：收据验证与ROI360商店收入。

<div id="about-purchase-and-subscription-validation" />

## 关于购买和订阅验证

购买与订阅验证可以帮助您提高收入数据的真实性与可信度。用户在应用内完成一次性购买或订阅后，您可以通过与应用商店（Apple App Store和Google Play）核验交易，确保只有真实完成付款的交易被纳入衡量与归因。

AppsFlyer为您提供了两种验证和衡量应用内购买及订阅收入的解决方案：收据验证和ROI360商店收入。

本文将对两种方案进行整体介绍，并通过[功能对比](#收据验证与roi360商店收入对比)，帮助您判断哪一种更适合您。

<div id="the-two-solutions-for-purchase-and-subscription-validation" />

## 购买和订阅验证的两种解决方案

<div id="receipt-validation" />

### 收据验证

收据验证是AppsFlyer提供的免费解决方案，用于在iOS和Android平台上验证应用内购买和订阅，确保只有真实交易被纳入统计。通过直接与应用商店校验收据，对数据进行验证。

在该模式下，您应用中对接的AppsFlyer SDK将上传最基础的信息，例如产品ID、购买ID和购买类型。AppsFlyer随后会从商店返回的响应中获取完整的收入数据，包括金额和币种。该方案不支持净收入计算、完整订阅生命周期洞察、退款处理，也不包含自动识别与去重功能。

通过收据验证，您可以基于已验证的收入数据进行分析，并以此为依据优化营销活动。

详情请见：

* <Anchor target="_blank" href="/marketers/zh/docs/about-receipt-validation">关于收据验证</Anchor>

* <Anchor target="_blank" href="/marketers/zh/docs/set-up-receipt-validation">设置收据验证</Anchor>

<div id="roi360-store-revenuepremium" />

### ROI360 商店收入溢价

<div id="important" />

> 🚧 **重要提示！**
>
> ROI360商店收入仅提供给ROI360高级计划的客户。要检查您的计划或升级，请联系您的客户成功经理 (CSM)。

ROI360商店收入是AppsFlyer的高阶解决方案，面向需要高精度收入衡量的应用，覆盖应用内购买和订阅的完整收入场景。该方案通过与应用商店进行S2S验证，返回经验证的丰富数据。

在S2S验证流程中，ROI360商店收入可对交易数据去重、扣除商店佣金和税费后计算净收入，覆盖完整的订阅生命周期，包括续订、取消、退款和升级，还可处理现有订阅用户事件，解决来自Google Play等商店的延迟付款问题。

如果您需要高精准度的收入数据、清晰的订阅生命周期洞察，以及对复杂商业模式的支持，ROI360商店收入将您的理想之选。

详情请见：

* <Anchor target="_blank" href="/marketers/zh/docs/about-roi360-store-revenue">关于ROI360商店收入</Anchor>

* <Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-store-revenue">设置ROI360商店收入</Anchor>

<div id="compare-receipt-validation-and-roi360-store-revenue" />

## 收据验证与ROI360商店收入对比

参考下方对比表，根据您的业务需求，选择最合适的解决方案。

<div id="compare-features" />

<Accordion title="比较功能">

| **功能** | **收据验证** | ROI360 商店收入溢价 |
| --- | --- | --- |
| **收据验证**  <br />验证应用内购买，过滤作弊交易 | ✔ | ✔ |
| **自动购买识别与去重**  <br />自动识别应用内购买和订阅（包括现有订阅用户产生的交易），去除重复数据，确保报表更清晰 | ✖ | ✔ |
| **退款处理**  <br />识别退款行为，并将其归因至原始购买，真实反映收入情况 | ✖ | ✔* |
| **应用内购买完整衡量**  <br />支持家庭共享场景，并通过App Store确认机制回传待处理订单的最终结果 | ✖ | ✔ |
| **覆盖完整订阅漏斗**  <br />衡量续订、升级和转化，全面反映订阅用户带来的长期价值 | ✖ | ✔ |
| **净收入计算**  <br />自动扣除商店佣金和税费，同时提供毛收入与净收入数据 | ✖ | ✔ |

* **应用内购买**的退款处理仅在ROI360 Advanced计划上提供。

</Accordion>

<div id="compare-inapp-purchase-event-support" />

<Accordion title="应用内购买事件对比">

| **事件名称** | **收据验证** | **ROI360** 商店收入 |
| --- | --- | --- |
| af\_purchase | ✔ | ✔ |
| af\_purchase\_refund* | ❌ | ✔ |
| af\_purchase\_pending | ❌ | ✔ |
| af\_purchase\_canceled* | ❌ | ✔ |
| af\_purchase\_free | ❌ | ✔ |
| af\_purchase\_sandbox\_sdk | ✔ | ✔ |
| af\_purchase\_sandbox\_s2s* | ❌ | ✔ |

*仅在ROI360高级计划中提供。

</Accordion>

<div id="compare-subscriptionrelated-event-support" />

<Accordion title="订阅事件对比">

| **事件名称** | **收据验证** | **ROI360** 商店收入 |
| --- | --- | --- |
| af\_ars\_trial\_started | ✔ | ✔ |
| af\_ars\_trial\_canceled | ❌ | ✔ |
| af\_ars\_trial\_churned | ❌ | ✔ |
| af\_ars\_trial\_converted | ❌ | ✔ |
| af\_ars\_subscription\_started | ✔ | ✔ |
| af\_ars\_subscription\_canceled | ❌ | ✔ |
| af\_ars\_subscription\_paused | ❌ | ✔ |
| af\_ars\_subscription\_resumed | ❌ | ✔ |
| af\_ars\_subscription\_churned | ❌ | ✔ |
| af\_ars\_subscription\_refunded | ❌ | ✔ |
| af\_ars\_subscription\_billing\_grace | ❌ | ✔ |
| af\_ars\_subscription\_renewed | ❌ | ✔ |
| af\_ars\_subscription\_xgraded | ❌ | ✔ |
| af\_ars\_existing\_subscriber | ❌ | ✔ |
| af\_ars\_sandbox\_sdk | ✔ | ✔ |
| af\_ars\_sandbox\_s2s | ❌ | ✔ |

</Accordion>

<div data-zendesk-anchors="about-purchase-validation=%E5%85%B3%E4%BA%8E%E8%B4%AD%E4%B9%B0%E5%92%8C%E8%AE%A2%E9%98%85%E9%AA%8C%E8%AF%81 h_01KCY9DHB7PBM3CZS65WMHR8B5=%E5%85%B3%E4%BA%8E%E8%B4%AD%E4%B9%B0%E5%92%8C%E8%AE%A2%E9%98%85%E9%AA%8C%E8%AF%81 appsflyer-solutions=%E8%B4%AD%E4%B9%B0%E5%92%8C%E8%AE%A2%E9%98%85%E9%AA%8C%E8%AF%81%E7%9A%84%E4%B8%A4%E7%A7%8D%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88 h_01KCY9DHB7XKWP0P8WMTSXVT4A=%E8%B4%AD%E4%B9%B0%E5%92%8C%E8%AE%A2%E9%98%85%E9%AA%8C%E8%AF%81%E7%9A%84%E4%B8%A4%E7%A7%8D%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88 receipt-validation=%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81 h_01KCY9DHB7DC66Q3H9W9064CZY=%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81 roi360-store-revenue=roi360-%E5%95%86%E5%BA%97%E6%94%B6%E5%85%A5%E6%BA%A2%E4%BB%B7 h_01KCY9DHB70VN27BYR3ZG0JD86=roi360-%E5%95%86%E5%BA%97%E6%94%B6%E5%85%A5%E6%BA%A2%E4%BB%B7 h_01KSAJM50XFXVQXZC59D1BE5XN=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA compare-receipt-validation-and-roi360-stores-revenue=%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81%E4%B8%8Eroi360%E5%95%86%E5%BA%97%E6%94%B6%E5%85%A5%E5%AF%B9%E6%AF%94 h_01KCY9DHB7RJ89GB5CM29T2AK5=%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81%E4%B8%8Eroi360%E5%95%86%E5%BA%97%E6%94%B6%E5%85%A5%E5%AF%B9%E6%AF%94 h_01KCY9DHB7M46DNAN0RABRRJ3X=compare-features h_01KCY9DHB7K8RF5TRGBVMDQ63F=compare-inapp-purchase-event-support h_01KCY9DHB7V7HRMKQRHZZT4EJ9=compare-subscriptionrelated-event-support" />

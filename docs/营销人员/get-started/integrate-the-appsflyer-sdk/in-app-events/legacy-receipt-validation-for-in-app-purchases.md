---
title: '[历史版本]应用内购买的收据验证功能'
deprecated: true
metadata:
  keywords:
    - iOS
    - Android
    - Receipt
    - Validation
    - Receipt Validation
    - SDK
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-02-26T10:30:58Z'
  edited_at: '2026-10-14T10:07:49Z'
  id: 207032106
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/207032106
---
<div id="important" />

> 🚧 **重要提示！**
>
> 本文为您介绍的是已下线的收据验证功能。如需了解更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/bulletin-legacy-receipt-validation-is-deprecated">公告：旧版收据验证已弃用</Anchor>

> **概要：** 收据验证可有效防止iOS或Android应用商店中的虚假应用内购买，并确保相关购买事件真实有效。**请注意**：本文为您介绍的是“历史版本”功能。如需了解最新的全自动增强型<Anchor target="_blank" href="/marketers/zh/docs/purchase-and-subscription-validation-overview">应用内购买验证机制</Anchor>，请参阅相关文档。

<div id="receipt-validation-flow" />

## 收据验证流程

收据验证流程如下：

1. 用户在应用内进行购买。
2. 应用商店确认购买成功，并通知应用。
3. 应用开发者调用SDK中的收据验证函数。

   ```
   validateAndLogInAppPurchase
   ```
4. SDK调用AppsFlyer验证服务。
5. AppsFlyer判断该购买是否真实有效。
6. 若验证通过，系统内部会自动生成一个标准的af\_purchase事件；若验证失败，该事件将被标记为作弊行为（可在Protect360中查看）。
7. AppsFlyer验证服务将结果返回给SDK。
8. SDK将验证结果（成功或失败）返回给应用。  
   如果收据验证失败，则该事件会显示在被拦截的应用内事件原始数据报告中（需购买Protect360）。

如需了解各平台的具体实现方式，请参见开发者SDK文档：

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-android#validating-purchases">安卓</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-ios#purchase-validation-using-validateandloginapppurchase">iOS</Anchor>

**补充说明：**

* 对于iOS沙盒应用（即尚未上线App Store的版本），在进行收据验证时需要<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/validate-and-log-purchase-ios#testing-purchase-validation-in-sandbox-mode">额外添加部分代码</Anchor>。
* 沙盒环境下的购买行为也会被记录为标准的af\_purchase事件，其收入数据也会在AppsFlyer面板及报告中显示。
* AppsFlyer的收据验证服务 对所有账户免费开放。
* 对于Android端应用，如果用户购买时没有连接网络，系统可能会返回`null`作为验证结果，将其视为验证失败。

<div id="important-1" />

> 🚧 **重要提示！**
>
> 调用`validateAndLogInAppPurchase`时，系统会自动生成一个**af\_purchase**应用内事件。因此，请勿在验证过程中手动生成该事件，以免收入数据重复。

<div id="note" />

> 📘 **注意**
>
> * 本文介绍的历史版本不支持*StoreKit v2*。关于当前版本，详见设置与iOS App Store的对接。
> * 第三方Android应用商店不支持应用内购买的收据验证。

<div data-zendesk-anchors="h_01KDJ7QZD8X692EVP1XXGV0KY4=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA receipt-validation-flow=%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81%E6%B5%81%E7%A8%8B 01JDSM0JDAQXH8QX8ZAXNB0ZMB=%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81%E6%B5%81%E7%A8%8B 01JDSM0JDT6Q3WYW9K484QHY2M=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 01JDSM0JD90J3EDMVN6D6Z9J40=%E6%B3%A8%E6%84%8F" />

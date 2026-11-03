---
title: 关于ROI360商店收入
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T16:34:39Z'
  edited_at: '2026-10-14T10:00:59Z'
  id: 42138855425297
  locale: zh-cn
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/zh-cn/articles/42138855425297
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 利用 ROI360 商店收入数据来验证应用内购买和订阅情况、防止重复计费，并计算净收入。

> 🚧 **重要提示！**
>
> ROI360 商店收入功能仅面向订阅 ROI360 高级套餐的客户开放。如需查看您的套餐或进行升级，请联系您的客户成功经理（CSM）。

ROI360 应用商店收入是 AppsFlyer 推出的一款高端解决方案，旨在全面、准确地衡量应用内购买和订阅带来的收入。它提供了客户生命周期的全面视图，从而能够准确衡量广告投资回报率（ROAS）。

| 功能 | 说明 |
| --- | --- |
| 收入确认范围 | <ul><li>所有通过App Store Connect（iOS）或Google Play Console（安卓）管理的应用内商品购买和订阅收入。</li><li>退款</li><li>未完成交易及延期交易的收入（安卓）。</li><li>发生在应用内和应用外的订阅相关事件</li><li>净收入（已扣除店铺佣金和税费）</li></ul> |
| 收入验证与准确性 | 该方案可防止重复交易被记录。在 iOS 系统上，这还包括防止因“家庭共享”功能导致的重复。ROI360 商店收入功能还可以将 Apple App Store 的交易数据直接转发给广告主。 |
| Data Sources。 | <ul><li>AppsFlyer 购买 SDK 连接器（适用于 Android 和 iOS）</li><li>设置App Store服务器通知</li><li>Google Play 实时开发者通知 (RTDN)</li></ul> |
| 报告与数据可用性 | 收入数据可在 AppsFlyer 仪表盘和报告中查看，也可通过回传与合作伙伴共享。 |

> ❗️ **重要提示**
>
> 在使用 ROI360 商店收入时，请勿发送应用内购买事件，否则会导致收入报告重复。

## ROI360 的收入存储机制是怎样的？

1. 用户完成一次应用内购买或自动续订。
2. 该应用在应用商店中完成一次交易。
3. AppsFlyer 购买 SDK 连接器会自动检测购买行为，并将相关数据包发送至 AppsFlyer 进行验证和记录。
4. AppsFlyer会与相关的商店验证该次购买，以确保交易信息的真实性。
   * 验证成功后，AppsFlyer会记录购买或订阅事件。
   * 如果收据验证失败，事件将显示在 `af_validated`已拦截应用内事件af\_validated原始数据报告中（仅对Protect360订阅用户开放），并在实时事件查看器页面显示，参数设置为 。
5. AppsFlyer将商店的响应消息发送到SDK connector，然后SDK connector会将收据验证的响应消息（成功或失败）发送到应用。
6. 所有传入AppsFlyer的服务器通知都会按照我们的购买和订阅收入逻辑进行处理：
   * 对于之前已经由SDK connector上报的交易，我们会对其相关通知进行验证和处理，并在系统内部生成一个购买事件或生命周期事件。
   * 与未知交易相关的通知会被忽略。
   * 对于iOS平台的所有服务器通知，您可以更改其发送路径，将其发送到您自己的服务器。

## 启用 ROI360 店铺收入

要启用 ROI360 店铺收入测量功能，请按照以下步骤操作：

1. 在AppsFlyer中，从左侧菜单进入<Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.17%" />**设置**，在**ROI360**下选择**收入设置**。
2. 打开**购买与订阅**标签页。
3. 在 **“1**”下，**选择“产品类型**”，然后选择 **“ROI360**”。
4. 点击 **“下一步**”继续。

## 设置ROI360商店收入

请参阅《<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-store-revenue">设置 ROI360 店铺收入</Anchor>》一文

## 其他参考信息

以下各节将详细介绍ROI360应用内购买（IAP）和订阅收入测量的关键方面。其中包括应用内购和订阅事件的相关事件及参数、净收入（支持毛收入转净收入的计算），以及ROI360应用内购和订阅收入测量解决方案的一般特性与限制。

> 📘 **注意**
>
> 若要在应用内事件中发送额外的自定义参数，请在<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-connector">“Purchase SDK 连接器</Anchor>”中配置**自定义数据源**。这使您能够通过自定义业务逻辑或元数据来丰富购买和订阅事件。
> 这些参数将在原始数据报告的`custom_data`字段中显示。

<div id="iaprelated-events-and-parameters" />

<Accordion title="与IAP相关的事件和参数">

以下几个小节分别说明了AppsFlyer所衡量的各个IAP相关事件及其参数。如需了解这些参数的含义，请参考[事件参数详解](#parameter-dictionary)部分。

**所有生成的事件均具有以下属性：**

* 服务器对服务器（S2S）事件。
* 可在原始数据报告中以自然流量或非自然流量的应用内事件形式查看，并包含在“收入 ETL 存储库”报告中。
* 通过回调发送给合作伙伴。
* 在 SKAN Conversion Studio 中受支持。

<div id="purchase-af_purchase" />

<Accordion title="购买（af_purchase）">

**说明**

用户完成购买时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-af_purchase_free" />

<Accordion title="免费购买（af_purchase_free）">

**说明**

用户完成不带收入金额的购买时记录该事件，此时所有收入参数都显示0值。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-canceled-af_purchase_canceled" />

<Accordion title="已取消的购买（af_purchase_canceled）">

**说明**

用户取消购买时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="purchase-pending-af_purchase_pending" />

<Accordion title="尚未完成的购买（af_purchase_pending）">

**说明**

用户下单但未完成付款时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="refund-af_purchase_refund" />

<Accordion title="退款（af_purchase_refund）">

**说明**

购买交易退款时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue（收入超过零时事件中会带有该参数）
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="test-purchase-af_purchase_sandbox_sdk" />

<Accordion title="用于测试的购买（af_purchase_sandbox_sdk）">

**说明**

在沙盒环境中测试SDK记录到的购买时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_purchase_sandbox_s2s" />

<Accordion title="用于测试的购买（af_purchase_sandbox_s2s）">

**说明**

在沙盒环境中测试S2S上报的购买时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="subscriptionrelated-events-and-parameters" />

<Accordion title="与订阅相关的事件和参数">

以下几个小节分别说明了AppsFlyer所衡量的各个订阅相关事件及其参数。如需了解这些参数的含义，请参考[事件参数详解](#parameter-dictionary)部分。

生成的所有事件：

* 都被视为S2S事件。
* 会呈现在原始数据报告中（记录为自然或非自然应用内事件）。
* 可以通过回传发送给合作渠道。
* 可以在SKAN转化值操作台中使用。

**请注意：** 一个应用内事件中可能会有部分参数得不到填充，具体取决于用户设备的操作平台。

<div id="trial-started-af_ars_trial_started" />

<Accordion title="开始试用（af_ars_trial_started）">

**说明**

订阅用户的试用期开始时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-canceled-af_ars_trial_canceled" />

<Accordion title="取消试用（af_ars_trial_canceled）">

**说明**

订阅用户在试用期内取消自动续订时记录该事件。如果用户后续未在试用期内恢复自动续订，还会记录用户流失事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-churned-af_ars_trial_churned" />

<Accordion title="试用后流失 (af_ars_trial_churned)">

**说明**

订阅用户在试用期结束后流失时记录该事件。用户的试用期结束，且该用户取消了自动续订时，即视为发生了试用后流失事件。这类事件之前可能发生了与续订有关的计费或技术问题，进而导致用户流失。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_reason

</Accordion>

<div id="trial-converted-af_ars_trial_converted" />

<Accordion title="试用后转化（af_ars_trial_converted）">

**说明**

用户完成试用后全价续订时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* store\_commission
* af\_revenue（仅在收入超过零时，事件中才会带有该参数）
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-started-af_ars_subscription_started" />

<Accordion title="套餐生效（af_ars_subscription_started）">

**说明**

用户以折扣价或全价订阅的套餐生效时记录该事件。

**请注意**：

* 新增的套餐订阅事件只能通过SDK connector记录。
* 对于iOS应用，如果某个订阅用户重复订阅现有套餐，SDK connector会向相关应用上报一个收据验证成功事件，但不会在AppsFlyer中记录新增交易。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue（收入超过零时事件中会带有该参数）
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-canceled-af_ars_subscription_canceled" />

<Accordion title="订阅已取消（af_ars_subscription_canceled）">

**说明**

用户在计费周期内取消自动续订时记录该事件。如果用户后续未在同一个计费周期内恢复自动续订，还会记录用户流失事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-paused-af_ars_subscription_paused-android-only" />

<Accordion title="订阅已暂停（af_ars_subscription_paused）- 仅适用于安卓应用">

**说明**

用户暂停已生效的套餐时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-resumed-af_ars_subscription_resumed" />

<Accordion title="订阅已恢复（af_ars_subscription_resumed）">

**说明**

用户流失或套餐发生退款后，以全价订阅套餐重新生效时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* af\_reason
* event\_revenue（事件收入超过零值时，相关事件中会带有该参数）
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-churned-af_ars_subscription_churned" />

<Accordion title="订阅用户流失（af_ars_subscription_churned）">

**说明**

订阅用户流失时记录该事件。一般情况下，当用户的计费周期结束，或用户取消自动续订时，说明该订阅用户发生了流失。这类事件之前可能发生了与续订有关的计费或技术问题，进而导致用户流失。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_reason

</Accordion>

<div id="subscription-refunded-af_ars_subscription_refunded" />

<Accordion title="订阅已退款（af_ars_subscription_refunded）">

**说明**

向订阅用户退款发出时记录该事件。

**请注意：**

* 该事件通常带有负值。如果AppsFlyer无法识别出发生退款的交易，或服务器通知中未包含退款详情，则相关退款事件不会显示事件值。

**参数**

* app\_id
* customer\_user\_id
* af\_reason
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_refunded\_transaction\_ids
* event\_revenue\_usd
* event\_revenue（收入超过零时事件中会带有该参数）
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_store
* af\_environment
* af\_period\_type
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-billing-grace-af_ars_subscription_billing_grace" />

<Accordion title="订阅计费宽限期（af_ars_subscription_billing_grace）">

**说明**

若出现支付问题导致续订失败，相关订阅用户进入计费宽限期时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-renewed-af_ars_subscription_renewed" />

<Accordion title="订阅已更新（af_ars_subscription_renewed）">

**说明**

订阅自动续费时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue（收入超过零时事件中会带有该参数）
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-changed-af_ars_subscription_xgraded" />

<Accordion title="订阅已变更（af_ars_subscription_xgraded）">

**说明**

用户订阅的产品发生升级、降级或变更时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue（收入超过零时事件中会带有该参数）
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="existing-subscriber-af_ars_existing_subscriber" />

<Accordion title="现有订阅用户（af_ars_existing_subscriber）">

**说明**

SDK connector针对处于计费周期内的订阅用户收到通知，但尚未收到后续通知要将此用户转移至生命周期的其它阶段时，即会生成该事件。该事件通常会在ROI360方案的启用期间以及SDK connector的采纳期间生成。

**参数**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated

</Accordion>

<div id="test-purchase-af_ars_sandbox_sdk" />

<Accordion title="用于测试的购买 (af_ars_sandbox_sdk)">

**说明**

在沙盒环境中测试SDK记录到的购买时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_ars_sandbox_s2s" />

<Accordion title="用于测试的购买 (af_ars_sandbox_s2s)">

**说明**

在沙盒环境中测试S2S上报的购买时记录该事件。

**参数**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="parameter-dictionary" />

<Accordion title="参数详解">

在原始数据中，IAP和订阅事件的参数会单独成列显示，或以**事件值**的形式呈现。

单独成列的参数如下：

* app\_id
* customer\_user\_id
* country\_code
* af\_currency
* event\_revenue\_usd
* af\_revenue
* android\_id
* ip
* idfa
* appsflyer\_id

如需进一步了解这些参数的详细信息，请参考<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">原始数据字段释义</Anchor>文档。

下表列出了ARS（自动续订）和VIAP（经验证的应用内购买）事件中可用的原始数据参数。

| 参数 | 说明 | 产品 |
| --- | --- | --- |
| af\_cancelation\_date\_ms | 取消日期 | IAP |
| af\_cuids | <ul><li>在ARS场景中，该参数会包含一个带有所有CUID的数组。</li><li>无论设备ID是否一致，都会显示CUID的数组，这样就可以让多个设备ID对应相同的CUID。</li></ul> | 订阅 |
| af\_discount\_id | 在首次购买过程中呈现给用户的优惠ID。只有在使用优惠码时才会填充该ID。 | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_discount\_type | 用户领取的优惠类型。可用值包括：<ul><li>IOS<ul><li>introductory（试销）</li><li>promotional（推广）</li><li>offer\_codes</li><li>win\_back</li></ul></li><li>安卓<ul><li>intro price（试销价）</li><li>one\_time\_code（一次性优惠码）</li><li>vanity\_code（定制优惠码）</li></ul></li></ul> | 订阅 |
| af\_environment | 数据接收环境，可能出现的值为production（生产环境）和sandbox（沙盒环境）两种。 | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_expires\_date\_ms | 当前订阅周期的截止日期。 | 订阅 |
| af\_net\_revenue | 根据所有相关因素计算得出的净收入。详情请见af\_net\_revenue\_factors说明。 | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_net\_revenue\_country | <ul><li>由两个字符组成的ISO国家代码，用于说明收取税费的国家。</li><li>示例：CA</li><li>注意：英国的代码是UK而不是GB。</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_net\_revenue\_factors | <ul><li>由一个数组组成，代表了计算af\_net\_revenue金额时涉及到的所有因素。</li><li>示例：store\_commission</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_net\_revenue\_postal\_code | <ul><li>由字母和/或数字组成的字符串，表示邮政编码</li><li>举例来说，L4J8E3</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_net\_revenue\_subdivision | <ul><li>部分国家可能需要区分州/细分区划。这里使用ISO 3166-2中的细分区划代码。</li><li>同时包含国家代码和细分区划代码。</li><li>举例来说，US-CA</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_net\_revenue\_tax\_exclusive | <ul><li>布尔型参数，仅有true或false两种值。</li><li>参数值为false时，表示总收入中包含税费。</li><li>参数值为true时，表示总收入中不包含税费，需要另行添加。</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_net\_revenue\_tax\_name | <ul><li>广告主出具的费用清单中用于表述具体税费类型的税费名称。</li><li>举例来说，销售税、增值税（VAT）、商品及服务税（GST）</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_net\_revenue\_tax\_rate | <ul><li>精确到小数点后4位的数字，代表税率百分点。</li><li>举例来说，7.25</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_offer\_id | <ul><li>适用于该交易的优惠ID（如适用，例如折扣或促销优惠）。</li><li>仅适用于安卓</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_order\_id | <ul><li>相关交易的订单ID。</li><li>仅适用于安卓</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_original\_transaction\_id | <ul><li>初始交易ID。</li><li>仅适用于iOS</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_original\_transaction\_id | <ul><li>相关交易的原始ID</li><li>仅适用于iOS</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_period\_type | <ul><li>订阅或试用期类型。</li><li>可用值包括：<ul><li>试用</li><li>intro（教学）</li><li>normal（正常使用）</li></ul></li></ul> | 订阅 |
| af\_product\_id | 相关订阅产品的ID | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_purchase\_date\_ms | 报告中与产品ID应用内事件相关联的购买日期。 | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_purchase\_option\_id | <ul><li>与该交易关联的购买选项 ID。</li><li>仅适用于安卓</li></ul> | IAP |
| af\_purchase\_option\_type | 该交易的购买选项类型。可能的值（Android）：<ul><li>购买</li><li>租金</li></ul> | IAP |
| af\_purchase\_state | 可用值包括：<ul><li>Purchased（已购买）</li><li>Canceled（已取消）</li><li>Pending（未完成）</li></ul> | IAP |
| af\_purchase\_token | <ul><li>相关交易的purchase token</li><li>仅适用于安卓</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_reason | [内容未变] | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_refunded\_transaction\_ids | <ul><li>由一个数组构成，其中包含所有退款的交易ID</li><li>仅适用于iOS</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_store | 指用户购买订阅产品时使用的应用商店 | <ul><li>IAP</li><li>订阅</li></ul> |
| af\_subscription\_ownership\_type | 若字段值为FAMILY\_SHARED，表示该用户通过家人共享套餐获取访问权限。若字段值为PURCHASED，表示付费用户完成了一次购买。 | 订阅 |
| af\_transaction\_id | <ul><li>相关交易的ID</li><li>仅适用于iOS</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |
| store\_commission | <ul><li>应用商店在已售产品中的抽成比例。</li><li>以百分点的形式表达。</li><li>举例来说，30</li></ul> | <ul><li>IAP</li><li>订阅</li></ul> |

</Accordion>

<div id="true-revenue" />

<Accordion title="净收入计算">

Net revenue 是一个专为支持 ROI360 Store 收入解决方案而构建的业务逻辑层。AppsFlyer会按照这层逻辑对接收到的每一笔交易信息实时自动计算净收入值，并将这些数据纳入报告中。

> 📘 **注意**
>
> 净收入会在原始数据报告中显示，并可通过应用内事件回调实时发送。在<Anchor target="_blank" href="/marketers/zh/docs/my-dashboards">“我的仪表盘”</Anchor>中，它以净指标（净收入、净投资回报率、净广告支出回报率、净每用户平均收入、净毛利润）的形式提供。
>
> 若要在回调中发送净收入，请在应用内事件配置中选择 **“值、收入和净收入**”选项。详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#回传内容">“应用内事件回调配置</Anchor>”。

> 📘 **提示**
>
> 您还可以配置应用内事件回调，在标准收入（货币）参数中发送净收入，而非总收入。如需访问此配置，请联系您的客户成功经理（CSM）。

净收入衡量逻辑会按以下因素根据总收入计算净收入：

* **商店抽成**：
  * AppsFlyer会自动计算和上报该信息，您无需采取任何行动。
  * 对于应用内购买（IAP），默认的商店佣金取决于应用商店：
    * App Store — 日本：24/12/2025中国大陆 (CN)：24/12/2025其他地区：24/12/2025
    * • Google Play24/12/2025
  * 对于订阅服务，佣金将根据订阅者的订阅时长，按每位订阅者自动计算。
    * App Store — 首12个月：日本为26%，中国大陆（CN）为25%，世界其他地区为30%。从第13个月起：日本为15%，中国大陆（CN）为12%，世界其他地区为15%。
    * • Google Play从第一天起即享15%折扣。
  * 原始数据报告中会呈现相关的净收入参数。
  * 使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">净收入 API</Anchor> 设置与默认值不同的商店佣金率。例如，如果您的应用已加入苹果的“小微企业计划”，该计划的佣金率为15%（中国大陆地区为12%），那么此功能将非常有用。
* **税费**：
  * ROI360对于其衡量范围内的所有交易都会按默认税率上报税费数据。
  * 此规定适用于含税国家（即税费已包含在标价中）。例如，在英国，AppsFlyer 会扣除税款和应用商店佣金的总和。对于美国等不含税的国家，其标价中不包含税费，因此“收入”和“净收入”参数默认不包含税费。
  * 可以使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">净收入 API</Anchor> 编辑该配置。要了解支持的国家及其默认税率，请参阅<Anchor target="_blank" href="https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub">此 JSON 文件</Anchor>。开发人员可以在示例文件的基础上进行修改，或直接按原样在API中使用该文件。

下表列出了包含净收入数据的参数，便于您在报告中查看真实收入。详情请见[参数详解](#parameter-dictionary)部分。

| 参数 | 净收入因素 |
| --- | --- |
| `store_commission` | 商店抽成 |
| `af_net_revenue_tax_name` | 税费 |
| `af_net_revenue_tax_rate` | 税费 |
| `af_net_revenue_tax_exclusive` | 税费 |
| `af_net_revenue_postal_code` | 税费 |
| `af_net_revenue_country` | 税费 |
| `af_net_revenue_subdivision` | 税费 |
| `af_net_revenue` | <ul><li>商店抽成</li><li>税费</li></ul> |
| `af_net_revenue_factors` | <ul><li>商店抽成</li><li>税费</li></ul> |

</Accordion>

<div id="troubleshooting-and-disprepancies" />

<Accordion title="故障排除与差异">

| 问题描述 | 解释 / 解答 |
| --- | --- |
| AppsFlyer 显示的应用内购买和订阅事件数量少于实际的应用商店数据。 | 在 AppsFlyer 中，仅会为已更新至包含 SDK 连接器的应用版本的用户生成事件。与此同时，应用商店会记录每一项事件，无论用户使用的应用版本如何。因此，在新版应用全面覆盖前，应用中的收入数据与商店端数据之间可能会存在差异。 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 维度 | 产品 | 说明 |
| --- | --- | --- |
| 分期订阅（Android） | 订阅收入 | 不支持 |
| 订阅正在处理中  <br />交易（Android） | 订阅收入 | 不支持 |
| 新增订阅 | 订阅收入 | 仅通过AppsFlyer Purchase SDK记录 |
| 价格变动 | 订阅收入 | 对于订阅收入，如果AppsFlyer没有接收到带有新价格的SDK通知，则会持续上报之前的价格，将其记录为收入。AppsFlyer接收到Purchase SDK发出的新价格后，即会记录新价格。 |
| 总收入 | <ul><li>IAP</li><li>订阅收入</li></ul> | 支持 |
| 净收入 | <ul><li>IAP</li><li>订阅收入</li></ul> | 原始数据和“我的仪表盘”（作为净指标）均支持此功能。 |
| 退款 | IAP | 上报窗口期为初始购买发生后的180天内。 |
| 数据去重 | <ul><li>IAP</li><li>订阅收入</li></ul> | 事件发生日期后180天内上报的交易可进行去重。 |
| SDK严格模式 | <ul><li>IAP</li><li>订阅收入</li></ul> | 对于以下版本的SDK connector，AppsFlyer在SDK严格模式下仍支持ROI360订阅和IAP解决方案：<ul><li>AppsFlyer iOS purchase SDK connector V6.13.0</li><li>Unity purchase SDK connector V2.0.1</li></ul> |
| 货币 | <ul><li>IAP</li><li>订阅收入</li></ul> | 收入数据以实际货币（通过event\_revenue参数）和美元（通过event\_revenue\_usd参数）为单位上报。 |
| 数据时效性 | <ul><li>IAP</li><li>订阅收入</li></ul> | <ul><li>交易级别的商店收入报告：每小时更新一次</li><li>设备级别的商店收入报告：每8小时更新一次</li></ul> |
| StoreKit 2 | <ul><li>IAP</li><li>订阅收入</li></ul> | <ul><li>从 Purchase SDK Connector 6.16.2 版本开始，支持 StoreKit 2。</li><li>请确保您的应用已按照<Anchor target="_blank" href="/marketers/zh/docs/bulletin-update-app-store-credentials-for-ios-roi360-receipt-validation">此处的</Anchor>说明使用了更新的 App Store 凭据。</li></ul> |
| Google 一次性产品 | IAP | <ul><li>支持的购买选项：购买与租赁</li><li>预购：不支持</li></ul> |

</Accordion>

<div data-zendesk-anchors="h_01KSAJW61CZZBWBQ112VR5095C=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01KD0W3J6105033NV6FYKGQ8BQ=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 how-does-roi360-store-revenue-work=roi360-%E7%9A%84%E6%94%B6%E5%85%A5%E5%AD%98%E5%82%A8%E6%9C%BA%E5%88%B6%E6%98%AF%E6%80%8E%E6%A0%B7%E7%9A%84 h_01KD2JZQ0JYVF8S1E2W3N91KYV=roi360-%E7%9A%84%E6%94%B6%E5%85%A5%E5%AD%98%E5%82%A8%E6%9C%BA%E5%88%B6%E6%98%AF%E6%80%8E%E6%A0%B7%E7%9A%84 enable-roi360-store-revenue=%E5%90%AF%E7%94%A8-roi360-%E5%BA%97%E9%93%BA%E6%94%B6%E5%85%A5 h_01KD2JZQ0JS9YQ2SPNN6NHAJEH=%E5%90%AF%E7%94%A8-roi360-%E5%BA%97%E9%93%BA%E6%94%B6%E5%85%A5 set-up-roi360-store-revenue=%E8%AE%BE%E7%BD%AEroi360%E5%95%86%E5%BA%97%E6%94%B6%E5%85%A5 h_01KD2JZQ0JD53598CES8ECAHR3=%E8%AE%BE%E7%BD%AEroi360%E5%95%86%E5%BA%97%E6%94%B6%E5%85%A5 reference=%E5%85%B6%E4%BB%96%E5%8F%82%E8%80%83%E4%BF%A1%E6%81%AF h_01JKWGTJQY938NV6VCJ7KKS23E=%E5%85%B6%E4%BB%96%E5%8F%82%E8%80%83%E4%BF%A1%E6%81%AF h_01KD6B3KC75RFDV08G9RT1BX1M=%E6%B3%A8%E6%84%8F h_01HDEPSK8DFQ24EZ5T0EPBSVS4=iaprelated-events-and-parameters 01H8VJJP1ER9N6BPAES8H8CK4T=purchase-af_purchase h_01J50N58GYF2BYC57HA7THSWW6=purchase-af_purchase_free 01H8VJJP1EXYE1EQS08CK8BG02=purchase-canceled-af_purchase_canceled 01H8VJJP1ET5TAAQ17EMK6TVRE=purchase-pending-af_purchase_pending 01H8VJJP1E8JKPGT2V9CCB1XW8=refund-af_purchase_refund 01H8VJJP1ECQMS49M8Z1X1FT4B=test-purchase-af_purchase_sandbox_sdk 01H8VJJP1E3X7YZNYT5D8REVEW=test-purchase-af_purchase_sandbox_s2s h_01HDEQBACTTPZ04YYD1KV49SEZ=subscriptionrelated-events-and-parameters 01H8VJJP1EHAZBGT82WRWB00JT=trial-started-af_ars_trial_started 01H8VJJP1ETCHTK6JMK9ERS5A5=trial-canceled-af_ars_trial_canceled 01H8VJJP1EC45X8PJVPWT3G7S3=trial-churned-af_ars_trial_churned 01H8VJJP1EYPQM50JVX1KPZXAZ=trial-converted-af_ars_trial_converted 01H8VJJP1EA4WTCEJWBB1HPRJF=subscription-started-af_ars_subscription_started 01H8VJJP1EF744NE425Y30VG0M=subscription-canceled-af_ars_subscription_canceled 01H8VJJP1EMKBP27070NRR9CZ5=subscription-paused-af_ars_subscription_paused-android-only 01H8VJJP1EGHNQ35JM1TWV4ND0=subscription-resumed-af_ars_subscription_resumed 01H8VJJP1EM2GJ28VBE6V76SBG=subscription-churned-af_ars_subscription_churned 01H8VJJP1E28XXAQSGZ9PYDT08=subscription-refunded-af_ars_subscription_refunded 01H8VJJP1E399B2AVWP9VKZ0D4=subscription-billing-grace-af_ars_subscription_billing_grace 01H8VJJP1EEZZ0DE75VXAZQP3E=subscription-renewed-af_ars_subscription_renewed 01H8VJJP1FGXHRK3J0XB2G4PCQ=subscription-changed-af_ars_subscription_xgraded 01H8VJJP1FKC8KZ2HKJVGZEV23=existing-subscriber-af_ars_existing_subscriber 01H8VJJP1F720QT97Q0TW4SEM2=test-purchase-af_ars_sandbox_sdk 01H8VJJP1FSRHG26EXMEG3325P=test-purchase-af_ars_sandbox_s2s 01H8VJJP1F0ZV2PX39D9JCG6B4=parameter-dictionary 01H8VJJP1FF219YN3XHRCGW7Z3=true-revenue h_01KBFWTM4XJ417930YVDD36ASK=%E6%B3%A8%E6%84%8F-1 h_01KRKEP613DR8RZ5Q2A5H7KZAH=%E6%8F%90%E7%A4%BA 01JHZG8FFHTYE2PMRWWS8WNR6X=troubleshooting-and-disprepancies 01H8VJJP1FP2MPRF8AN77REXD0=traits-and-limitations" />

---
title: 关于收据验证
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
  created_at: '2025-12-21T14:32:24Z'
  edited_at: '2026-10-14T10:01:23Z'
  id: 42136725767569
  locale: zh-cn
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/zh-cn/articles/42136725767569
---
> **概要：** 了解如何通过收据验证对应用内购买和订阅收入进行衡量，并与应用商店校验，从而确保收入衡量的准确性。

广告主可使用收据验证，对来自Google Play和App Store的应用内购买进行验证与衡量。

收据验证对所有账户方案免费开放。

> 📘 **注意**
>
> 建议您使用我们的高级ROI360商店收入解决方案，以使用净收入计算、完整漏斗衡量、处理退款以及自动化购买识别与去重等功能。如需详细信息，或两种方案的对比，请参阅<Anchor target="_blank" href="/marketers/zh/docs/purchase-and-subscription-validation-overview#购买和订阅验证的两种解决方案">购买与订阅验证的两种解决方案</Anchor>。

## 收据验证的工作原理

收据验证流程如下：

1. 用户在应用内进行购买。
2. 应用商店确认购买成功，并通知应用。
3. 应用开发者调用SDK中的收据验证：`validateAndLogInAppPurchase`
4. SDK调用AppsFlyer验证服务。
5. AppsFlyer判断该购买是否真实有效。
6. 验证成功后，AppsFlyer会记录购买或订阅事件。
7. 如果收据验证失败，事件将显示在 <Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports#blocked-inapp-events">已拦截应用内事件</Anchor>原始数据报告中（仅对Protect360订阅用户开放），并在<Anchor target="_blank" href="/marketers/zh/docs/testing-the-sdk-integration-for-marketers#view-live-events">实时事件查看器页面</Anchor>显示，参数`af_validated`设置为 `false`。
8. AppsFlyer验证服务将结果返回给SDK。
9. SDK将验证结果（成功或失败）返回给应用。

## 启用收据验证

请按照以下步骤启用收据验证：

1. 在AppsFlyer中，从左侧菜单进入<Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.02%" />**设置**，在**ROI360**下选择**收入设置**。
2. 打开**购买与订阅**标签页。
3. 在步骤1**选择产品类型**中，选择**收据验证**。
4. 点击**保存并继续**，进入收据验证流程。

## 设置收据验证

有关详细信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/set-up-receipt-validation">设置收据验证。</Anchor>

## 收据验证的应用内购买事件和参数

所有预定义事件的共同特性：

* 均作为S2S事件处理。
* 可在面板和原始数据报告中，以自然量或非自然量应用内事件形式查看。
* 可以通过回传发送给合作渠道。
* 可以在SKAN转化值操作台中使用。

**应用内购买事件：**

* `af_purchase` - 正式环境
* `af_purchase_sandbox_sdk` - 沙盒

**订阅事件：**

* `af_ars_trial_started` - 订阅试用期开始。
* `af_ars_subscriptions_started` - 付费订阅开始（无试用期，正式环境）
* `af_ars_sandbox_sdk` - 试用或付费订阅开始（沙盒环境）

**事件包含的预定义参数：**

* `af_product_id`
* `af_transaction_id` (iOS only)
* `af_purchase_token` (Android only)
* `af_revenue` （沙盒事件中为`af_sandbox_revenue`)
* `af_currency`
* `af_store` (app\_store / play\_store)
* `af_environment` （沙盒/正式环境）
* `af_validation_type` (receipt\_validation)

**其他自定义参数：**

* 在SDK调用中传入的任何自定义参数，都会显示在原始数据报告的`custom_data`字段中。

## 从ROI360商店收入切换至收据验证

如果您当前使用的是ROI360商店收入，并希望切换为收据验证，请按以下步骤操作：

1. 在AppsFlyer中，从左侧菜单进入<Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.02%" />**设置**，在**ROI360**下选择**收入设置**。
2. 在**购买和订阅**选项卡中，确认**产品类型**设置为**ROI360**。
3. 点击<Image alt="无标题 3.png" src="https://files.readme.io/c27f864253e6749f883047b4529ad292153500db5aebd452568a6aa04407472e-34623601366033.png" width="2.07%" />。
4. 系统将弹出提示，显示切换将对收据验证产生的影响：
   * ROI360相关功能，包括退款归因、订阅续费衡量以及净收入计算将被禁用。
   * 数据准确性可能会下降。
   * 购买连接器不支持收据验证。
   * 仅支持`validateAndLogInAppPurchase`这一SDK方法。
5. 如果需要，请点击**查看比较表**进行对比。
6. 如需继续操作，点击**确认切换**完成操作。
7. 切换完成后，**产品类型**将更新为**收据验证**，界面将显示为简化配置。
8. 您需要重新验证以下内容：
   * 用于validateAndLog方法的**SDK部署**

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 支持的商店 | • Google Play  <br />• App Store  <br />• 如使用其他第三方商店，需手动发送应用内购买事件 |
| iOS沙盒应用 | 对于尚未在App Store上线的iOS沙盒应用，“验证密钥”将始终显示为无效状态 |

<div data-zendesk-anchors="h_01KD0PBEK0P2PACH8PX8M068S1=%E6%B3%A8%E6%84%8F how-does-receipt-validation-work=%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 h_01KD0PBEK0M2NEZJ95QXBA1H3W=%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 enable-receipt-validation=%E5%90%AF%E7%94%A8%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81 h_01KD0PBEK0BZNW8YP02EW0DHH4=%E5%90%AF%E7%94%A8%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81 set-up-receipt-validation=%E8%AE%BE%E7%BD%AE%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81 h_01KD0PBEK1GZSJQPTP0P2TJMNJ=%E8%AE%BE%E7%BD%AE%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81 inapp-purchase-events-and-parameters-for-receipt-validation=%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E8%B4%AD%E4%B9%B0%E4%BA%8B%E4%BB%B6%E5%92%8C%E5%8F%82%E6%95%B0 h_01KD0PBEK1DVMRXR64EMSWT75W=%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E8%B4%AD%E4%B9%B0%E4%BA%8B%E4%BB%B6%E5%92%8C%E5%8F%82%E6%95%B0 switch-from-roi360-store-revenue-to-receipt-validation=%E4%BB%8Eroi360%E5%95%86%E5%BA%97%E6%94%B6%E5%85%A5%E5%88%87%E6%8D%A2%E8%87%B3%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81 h_01KD0PBEK1AKE1XM2XVTCNTJ68=%E4%BB%8Eroi360%E5%95%86%E5%BA%97%E6%94%B6%E5%85%A5%E5%88%87%E6%8D%A2%E8%87%B3%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81 traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01KD0PBEK1HQKTGM7JP2KYPJAR=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />

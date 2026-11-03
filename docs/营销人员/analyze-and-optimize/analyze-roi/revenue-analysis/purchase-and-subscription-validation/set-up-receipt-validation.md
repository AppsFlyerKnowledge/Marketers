---
title: 设置收据验证
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
  created_at: '2025-12-21T15:14:21Z'
  edited_at: '2026-10-14T10:00:53Z'
  id: 42137474889489
  locale: zh-cn
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/zh-cn/articles/42137474889489
---
> **概要：** 了解如何通过收据验证对应用内购买和订阅收入进行衡量，并与应用商店校验，从而确保收入衡量的准确性。

## 概览

> 📘 **注意**
>
> 有关收据验证的更多信息，包括其工作原理以及如何在 AppsFlyer 中启用它，请参见 <Anchor target="_blank" href="/marketers/zh/docs/about-receipt-validation">关于收据验证</Anchor>。

要设置收据验证，请按顺序完成以下步骤：

1. 设置商店凭据（iOS 和 Android）
   * iOS在 AppsFlyer 中配置 App Store Connect 密钥（应用内购买密钥、密钥 ID 和发行者 ID）以启用收据验证。
   * 安卓配置 Google Cloud 服务帐户，在 Google Play 控制台中设置所需权限，并将服务帐户 JSON 密钥上传到 AppsFlyer。
2. [实现 validateAndLog SDK API](#第2步2实施sdk-v6)：准备开发人员集成 AppsFlyer `validateAndLog` SDK API，并配置沙盒环境以进行测试。
3. [测试 validateAndLog SDK API 实现](#第3步验证sdk实现)：在 iOS 和 Android 上执行沙盒测试购买和订阅，以验证收据验证事件是否生成并被 AppsFlyer 正确记录。
4. [验证并更新设置](#第4步验证并更新设置)：确认产品类型设置为收据验证，并检查商店密钥和 SDK 集成状态，以确保准确、持续的收入测量。
5. [发布带有 validateAndLog SDK API 的应用版本](#第5步发布带有-validateandlog-sdk-api-的应用版本)：发布集成了 `validateAndLog` SDK API 的更新应用版本，确保沙盒标志已禁用，并且所需的应用内事件未被验证规则阻止。

## 步骤 1（iOS）设置 App Store Connect 密钥

在步骤1中，从App Store Connect获取以下凭据，并填写在AppsFlyer后台的收入设置页面中：

* In-App Purchase key
* Key ID
* Issuer ID

**前期准备** ：

* 设置证书时，您需要在App Store Connect和AppsFlyer中分别完成相关步骤。请在操作过程中同时打开App Store Connect和AppsFlyer两个标签页。
* 您的iOS应用需要使用StoreKit v1或v2，StoreKit可提供处理应用内购买与订阅的基础框架。

<div id="11-create-the-app-store-connect-keys" />

<Accordion title="1.1 生成App Store Connect密钥">

要设置iOS凭据， 请按照以下步骤操作：

1. **在App Store Connect中，进入用户和访问权限**页面

   [![](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)
2. 前往**用户和访问权限**> **对接**，在**密钥**列表中，选择**应用内购买**。

   [![](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)
3. 点击+生成一个新的应用内购买密钥。

   [![](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)
4. 输入您的API密钥名称。
5. 点击**生成**。
6. 在生成的密钥旁边，点击**下载应用内购买密钥**。 **注意**：该密钥只能下载一次，请妥善保存。
7. 在App Store Connect中，复制生成的密钥的**Key ID**，并将其粘贴到AppsFlyer购买和订阅设置中的**Key ID**字段里。

   [![](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)
8. 复制**发行者 ID**。 **注意**： 如果页面顶部未显示**Issuer ID**，请创建一个App Store Connect API私钥（具有任意权限级别）。之后，Issuer ID将出现在应用内购买私钥的页面顶部。

   [![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)

</Accordion>

<div id="12-set-the-app-store-connect-key" />

<Accordion title="1.2 设置 App Store Connect 密钥">

1. 启用收据验证。#enable-receipt-validation
2. 在 **App Store Connect 密钥** 步骤下，点击 [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.45%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **上传** 在 **应用内购买密钥** 字段中上传 p8 文件。
3. 在名为**App Store Connect密钥**的部分，粘贴您从App Store Connect复制的值。

   * **Key ID**
   * **Issuer ID**
4. 点击**验证密钥**，确保密钥输入正确。 **请注意**：如果您的应用尚未在App Store中发布，验证密钥可能无法正常工作。
5. 单击**保存并继续**。

</Accordion>

## 步骤 2（Android）：设置服务账户密钥和权限

在步骤 1 中，从 *Google Play* 和 *Google Cloud* 获取以下凭据，并在 AppsFlyer 平台的 **收入设置** 页面中输入它们。

**前期准备** ：

* 设置应用内购买和订阅收入衡量时，您需要在<Anchor target="_blank" href="https://cloud.google.com/">Google Cloud Platform</Anchor>、<Anchor target="_blank" href="https://play.google.com/console/">Google Play Console</Anchor>以及<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">AppsFlyer界面</Anchor>中分别完成相关操作。建议您在设置过程中同时打开以上三个标签页。
* 在AppsFlyer后台进行设置需具备管理员权限。

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1 将您的Google Play开发者账号关联到您的Google Cloud项目">

**前提条件**：Google Play Console和Google Cloud访问权限。

**请按照以下步骤将您的Google Play开发者账号关联到您的Google Cloud项目**：

1. 从Google Play Console进入您的Google Play开发者账号。
2. 将该账号关联到您的Google Cloud项目。详细指南请参考<Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">Google提供的说明文档</Anchor>。
3. 启用Google Play Developer API。详细指南请参考<Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">Google提供的说明文档</Anchor>。

   [![](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="在Google Cloud Platform中配置您的服务账户">

**前提条件**：访问Google Cloud Platform。

**要配置您的服务帐户，请按照以下步骤操作**:

1. 创建或找到**服务账号**：

   1. 在Google Cloud Platform中，前往<strong>Service accounts（服务账号）</strong>部分，点击 **“Create Service Account（创建服务账号）”**。
   2. 填写服务账号的详细信息。
   3. 复制电子邮件地址。
   4. 点击**Create and continue（创建并继续）**，进入下一步。
   5. 在**Grant this service account access to the project**（为该服务账号开放项目权限）部分的“Select a role”（选择角色）字段中，选择**Pub/Sub subscriber**。
   6. 点击**Continue** > **Done**，完成服务账号的创建。

      [![](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)
2. 下载服务账号私钥：

   1. 在Google Cloud Platform中，进入<strong>Service accounts（服务账号）</strong>部分，从列表中找到你刚创建的服务账号，点击 **“更多操作”** 图标。
   2. 点击 **“管理私钥（Manage keys）”**。
   3. 点击 **添加私钥** > **创建新私钥**。

      [![](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)
   4. 在**创建私钥**窗口中，
   5. 在**私钥类型**下，选择**JSON**，

      然后单击**创建**。[![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)点击[Create](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)，下载JSON格式的密钥文件。[![](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)
   6. 保存 JSON 密钥文件，稍后您将上传到 AppsFlyer。 **请注意**：请务必保存密钥，关闭窗口后将无法再次获取。如果您不保存它，您必须创建一个全新的密钥。

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="在Google Play Console中设置API访问权限。">

**前提条件**：Google Play Console访问权限。

**请注意**：服务账号的证书和权限设置完毕后，可能需要等待一段时间（最长可达24小时），然后才能正常使用。在此期间你可能会在后续步骤中遇到报错。

**在Google Play Console中设置API访问权限的操作如下：**

1. 在Google Play Console中，进入**Users and permissions（用户和权限）**，找到您创建的服务账号并点击**Invite new users（邀请新用户）**。

   [![](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)
2. 在<strong>Email address（邮箱地址）</strong>字段中，填写您在第1.2.1.3步创建服务账号时复制的邮箱地址。

   [![](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)
3. 在**Permissions**（权限）部分，进入**Account permissions**（账号权限）选项卡，然后同时勾选以下两项：

   * View financial data, orders, and cancellation survey responses（查看财务数据、订单和取消订阅问卷答复）
   * Manage orders and subscriptions（管理订单和订阅）
4. 在**App permissions**（应用权限）标签页中，点击**Add app**（添加应用），然后选择应用。如有需要可添加多个应用。

   [![](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)
5. 点击**Invite user**（邀请用户）。

   [![](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)
6. 在确认弹出窗口中，点击**Send invite**（发送邀请）。

   [![](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="将服务账户私钥上传到AppsFlyer。">

上传并验证您在[步骤 1.2](#12-configure-your-service-account-in-the-google-cloud-platform)中下载的 Google JSON 密钥。

**前提条件**：具备AppsFlyer管理员权限。

**要将账户私钥上传到 AppsFlyer，请按照以下步骤操作**:

1. 启用收据验证
2. 在**服务账户密钥和权限**步骤中，在**上传Google JSON密钥**字段中，点击[<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.23%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png)**上传**。
3. 上传您在[步骤 1.2](#12-configure-your-service-account-in-the-google-cloud-platform)中下载的JSON文件。
4. 点击**验证密钥。** **请注意：**

   * 设置服务账号凭据和权限后，最多可能需要 24 小时才能生效。在此期间进行密钥验证或验证测试时可能会出现错误。
   * 如需绕过最长 24 小时的等待时间，可在Google Play Console中打开任意应用，进入**Monetize > Products > Subscriptions/In-app products**，并对某项内容进行修改（如编辑商品描述并保存）。这通常会立即更新账户凭据和权限。修改完成后可撤销操作。
5. 点击**Next**。**SDK实现**步骤已打开。

</Accordion>

## 第2步：2.实施SDK V6

在此步骤中，您准备开发人员集成SDK `validateAndLog` API，并设置一个用于测试的沙盒环境。支持最新`validateAndLog` API的最低SDK版本为Android的**6.17.5**和iOS的**6.17.8**。

要实现validateAndLog SDK API，请按照以下步骤操作：

1. 在**SDK实现**步骤中，复制仪表板中显示的**预写消息**。
2. 将其发送给您的开发人员。它包括：

   * 应用名称和App ID
   * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">SDK对接指南</Anchor>链接。
   * 沙盒环境配置说明 (`sandbox = true`)
   * 测试步骤（使用**TestFlight**）

   此处包含了开发人员进行对接和测试所需的全部信息。
3. 点击**Next**。**验证SDK实现**步骤已打开。

## 第3步：验证SDK实现

建议在沙盒环境中测试IAP和订阅收入对接，确保SDK connector已正确接入到相关应用中，且服务器通知的配置正确无误，AppsFlyer可正常收到通知。

<div id="test-sdk-implementation" />

<Accordion title="测试SDK实现">

要检查AppsFlyer在过去7天内是否收到了来自您应用程序的有效`validateAndLog`有效载荷，请执行以下步骤：

1. 在**验证SDK实现**步骤中，点击**测试SDK实现**。
2. 查看结果，包括AppsFlyer收到的最新有效载荷的时间戳。请注意，此检查仅确认请求已到达AppsFlyer，并不验证数据的完整性或正确性。
3. 要完全验证实现，请继续进行以下测试步骤。

</Accordion>

<div id="sandbox-environment-considerations" />

<Accordion title="沙盒环境的注意事项">

在沙盒环境中：

* 只有初始购买事件会导致validateAndLog SDK API生成一个由AppsFlyer记录的事件。应用内购买事件称为`af_purchase_sandbox_sdk`。订阅事件称为`af_ars_sandbox_sdk`.。
* 沙盒事件的收入为0。
* 对于安卓应用，由已获许可的测试人员（Licensed Tester）开展的测试总是会触发沙盒事件，无论SDK中是否配置了沙盒环境。

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="测试应用内购买（IAP）和订阅收入数据">

[![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

**测试应用内购买和订阅收入**：

1. 告诉您的开发人员按照他们的说明配置validateAndLog SDK API的沙盒环境。
2. 使用<Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">Google Play的License Tester</Anchor>或<Anchor target="_blank" href="https://developer.apple.com/testflight/">iOS的TestFlight</Anchor>进行测试购买或订阅启动操作。
3. 查看测试事件以以下方式显示：

   * 在 <Anchor target="_blank" href="/marketers/zh/docs/testing-the-sdk-integration-for-marketers#view-live-events">实时事件查看器</Anchor> 中查看事件。
   * 在 <Anchor target="_blank" href="/marketers/zh/docs/activity-metrics-in-my-dashboards">我的仪表板 - 活动视图</Anchor> 中查看事件数据。
4. 查找以下测试事件：

   * 购买事件的 `af_purchase_sandbox_sdk`。
   * 订阅事件的 `af_ars_sandbox_sdk`。
5. 确保测试事件包括以下内容：

   * 收入值为0（避免AppsFlyer的实际报告数据受到扭曲）。
   * 一个 `af_sandbox_revenue` 参数，包含所购产品的收入值，确保报告的收入正确。
   * 一个 `af_validated` 参数是 `true`。如果 `af_validated` 是 `false` - 返回到上面的第 2 步并验证从商店提供的密钥。
   * 一个 `af_validation_type` 参数是 `receipt_validation`。

</Accordion>

## 第4步：验证并更新设置。

完成上述设置配置并保存后，您将被重定向到活动配置视图，在此您可以验证或更新以下设置：

1. 验证 **产品类型** 是否为 **收据验证**。
2. 确保 **与 App Store 验证购买** 已开启。
3. 验证或更新以下设置：

   * **App Store 密钥** 设置。
   * **SDK 集成** 设置。

## 第5步：发布带有 validateAndLog SDK API 的应用版本。

在前面的步骤都配置完毕并将 AppsFlyer validateAndLog SDK API 集成到您的应用后，告诉您的开发人员发布集成了 validateAndLog SDK API 的应用版本。

在开发人员发布新应用版本之前，请确保：

* 您在AppsFlyer中配置的验证规则不会拦截您想要记录的IAP或订阅事件。
* 您的开发人员已将所有沙盒标志设置为`false`。

[<Image alt="" src="https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png" width="512px" />](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

一旦包含validateAndLog SDK API的应用程序发布，<Anchor target="_blank" href="/marketers/zh/docs/about-receipt-validation#收据验证的应用内购买事件和参数">应用内购买和订阅事件</Anchor>将生成并在所有AppsFlyer仪表板上可用，同时也会出现在汇总和原始数据报告中。

仅为已更新到包含validateAndLog SDK API版本的用户生成事件。因此，在新版应用全面覆盖前，应用中的收入数据与商店端数据之间可能会存在差异。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01KD0RY1HMV71TGDZZX7JWM3XJ=%E6%A6%82%E8%A7%88 h_01KD0RY1HMMSR4ZDW5GF4N05P1=%E6%B3%A8%E6%84%8F step-1-ios-set-up-app-store-connect-keys=%E6%AD%A5%E9%AA%A4-1ios%E8%AE%BE%E7%BD%AE-app-store-connect-%E5%AF%86%E9%92%A5 h_01KD0RY1HM14KNGKADCBMHJXH6=%E6%AD%A5%E9%AA%A4-1ios%E8%AE%BE%E7%BD%AE-app-store-connect-%E5%AF%86%E9%92%A5 h_01KD0RY1HM08AS4RGNR1QE598K=11-create-the-app-store-connect-keys h_01KD0RY1HMPJGGHQ19D5K70JSZ=12-set-the-app-store-connect-key step-1-android-set-up-service-account-key-and-permissions=%E6%AD%A5%E9%AA%A4-2android%E8%AE%BE%E7%BD%AE%E6%9C%8D%E5%8A%A1%E8%B4%A6%E6%88%B7%E5%AF%86%E9%92%A5%E5%92%8C%E6%9D%83%E9%99%90 h_01KD0RY1HMG9DGKGEY8XVR3K7Z=%E6%AD%A5%E9%AA%A4-2android%E8%AE%BE%E7%BD%AE%E6%9C%8D%E5%8A%A1%E8%B4%A6%E6%88%B7%E5%AF%86%E9%92%A5%E5%92%8C%E6%9D%83%E9%99%90 h_01KD0RY1HMRK0B1Z4FKD0DD2KQ=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD0RY1HN9ER2FZ7XN93SGEN9=12-configure-your-service-account-in-the-google-cloud-platform h_01KD0RY1HN03Y7T4KCNYX9FWS0=13-set-api-access-permissions-in-google-play-console h_01KD0RY1HNS6EPAKZ4YY3MZZK9=14-upload-the-service-account-private-key-to-appsflyer step-2-implement-sdk=%E7%AC%AC2%E6%AD%A52%E5%AE%9E%E6%96%BDsdk-v6 h_01KD0RY1HN63X3WM1RH19W2HZ5=%E7%AC%AC2%E6%AD%A52%E5%AE%9E%E6%96%BDsdk-v6 step-3-verify-sdk-implementation=%E7%AC%AC3%E6%AD%A5%E9%AA%8C%E8%AF%81sdk%E5%AE%9E%E7%8E%B0 h_01KD0RY1HNDMSWGDW6ZQDZ5DAM=%E7%AC%AC3%E6%AD%A5%E9%AA%8C%E8%AF%81sdk%E5%AE%9E%E7%8E%B0 h_01KD0RY1HNC4VXSRFC1ZMKWWS6=test-sdk-implementation h_01KD0RY1HNDFF6J29AHG6S4EFM=sandbox-environment-considerations h_01KD0RY1HN5EBX3VGMH5PNHTA8=test-inapp-purchase-and-subscription-revenue step-4-verify-and-update-settings=%E7%AC%AC4%E6%AD%A5%E9%AA%8C%E8%AF%81%E5%B9%B6%E6%9B%B4%E6%96%B0%E8%AE%BE%E7%BD%AE h_01KD0RY1HN2HZEW9ANBPNRMXPP=%E7%AC%AC4%E6%AD%A5%E9%AA%8C%E8%AF%81%E5%B9%B6%E6%9B%B4%E6%96%B0%E8%AE%BE%E7%BD%AE step-5-release-the-app-versions-with-the-validateandlog-sdk-api=%E7%AC%AC5%E6%AD%A5%E5%8F%91%E5%B8%83%E5%B8%A6%E6%9C%89-validateandlog-sdk-api-%E7%9A%84%E5%BA%94%E7%94%A8%E7%89%88%E6%9C%AC h_01KD0RY1HNECTDNNHK78F9KDPS=%E7%AC%AC5%E6%AD%A5%E5%8F%91%E5%B8%83%E5%B8%A6%E6%9C%89-validateandlog-sdk-api-%E7%9A%84%E5%BA%94%E7%94%A8%E7%89%88%E6%9C%AC" />

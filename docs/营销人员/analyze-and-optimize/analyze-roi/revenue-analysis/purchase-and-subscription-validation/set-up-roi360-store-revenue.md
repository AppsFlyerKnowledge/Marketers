---
title: 设置ROI360商店收入
metadata:
  keywords:
    - Premium
    - Advertisters
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-22T11:05:11Z'
  edited_at: '2026-10-14T10:00:58Z'
  id: 42158608158353
  locale: zh-cn
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/zh-cn/articles/42158608158353
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 设置 AppsFlyer ROI360 应用商店收入解决方案。

<div id="overview" />

## 概览

<div id="note" />

> 📘 **注意**
>
> 如需了解有关 ROI360 的更多信息（包括其工作原理以及如何在 AppsFlyer 中启用该功能），请参阅《<Anchor target="_blank" href="/marketers/zh/docs/about-roi360-store-revenue">关于 ROI360 商店收入》</Anchor>。

要设置 ROI360 店铺收入，请按以下顺序完成以下步骤：

1. 设置商店凭据（iOS 和 Android）：
   * iOS在 AppsFlyer 中配置 App Store Connect 密钥（应用内购买密钥、密钥 ID 和发行者 ID）。
   * 安卓配置一个 Google Cloud 服务账户，在 Google Play 控制台中设置所需权限，并将服务账户的 JSON 密钥上传至 AppsFlyer。
2. 配置服务器通知（iOS 和 Android）：
   * iOS设置 App Store 服务器通知，可通过直接将通知发送至 AppsFlyer（推荐）或从您自己的端点转发通知，并验证集成是否成功。
   * 安卓设置 Google Play 实时开发者通知 (RTDN)，方法包括允许 Google Play 直接向 AppsFlyer 发送通知（推荐），或通过 Pub/Sub 转发通知。
3. [实现 SDK 连接器](#第3步部署sdk-connector)：帮助开发者做好集成 AppsFlyer 购买 SDK 连接器的准备。
4. [验证 SDK 实现](#第4步验证-sdk-的实现)：在两个平台上测试应用内购买和订阅功能，以确认 AppsFlyer 能正确接收并处理 SDK 事件和服务器通知。
5. [验证并更新设置](#第5步验证并更新设置)：审查并确认购买验证、退款处理、订阅统计和商店集成等环节的状态，以确保跨平台收入归因的准确性和持续性。
6. [应用版本](#第6步发布已对接sdk-connector的应用版本)：发布已集成 SDK Connector 的更新版应用，确保已禁用沙盒标记，且验证规则允许所需的收入事件。

<div id="step-1-ios-set-up-app-store-connect-keys" />

## 步骤2（iOS）：设置App Store Connect密钥

在步骤1中，从App Store Connect获取以下凭据，并填写在AppsFlyer后台的收入设置页面中：

* In-App Purchase key
* Key ID
* Issuer ID

**前期准备** ：

设置证书时，您需要在App Store Connect和AppsFlyer中分别完成相关步骤。请在操作过程中同时打开App Store Connect和AppsFlyer两个标签页。

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

<div id="12-set-the-app-store-connect-key-in-appsflyer" />

<Accordion title="1.2 在AppsFlyer中设置App Store Connect密钥">

1. <Anchor target="_blank" href="/marketers/zh/docs/about-roi360-store-revenue#启用-roi360-店铺收入">启用 ROI360 商店收入</Anchor>。
2. 在 **“App Store Connect 密钥**”步骤下，点击[<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png)**“应用内购买”密钥**字段中的 **“上传**”按钮，上传 p8 文件。
3. 在名为**App Store Connect密钥**的部分，粘贴您从App Store Connect复制的值。

   * **Key ID**

   * **Issuer ID**
4. 点击**验证密钥**，确保密钥输入正确。 **注意：如果您的应用尚未在App Store中发布，验证密钥**可能无法正常工作。
5. 点击**保存并继续**。

</Accordion>

<div id="step-1-android-set-up-service-account-key-and-permissions" />

## 步骤 2（Android）：设置服务账户密钥和权限

请从App Store Connect获取以下凭据，并填写在AppsFlyer后台的收入设置页面中：

**前期准备** ：

* 设置应用内购买和订阅收入衡量时，您需要在<Anchor target="_blank" href="https://cloud.google.com/">Google Cloud Platform</Anchor>、<Anchor target="_blank" href="https://play.google.com/console/">Google Play Console</Anchor>以及<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">AppsFlyer界面</Anchor>中分别完成相关操作。建议您在设置过程中同时打开以上三个标签页。
* 在AppsFlyer后台进行设置需具备管理员权限。

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1.将您的Google Play开发者账号关联到您的Google Cloud项目">

**前期准备**：Google Play Console和Google Cloud访问权限。

**请按照以下步骤将您的Google Play开发者账号关联到您的Google Cloud项目**：

1. 从Google Play Console进入您的Google Play开发者账号。
2. 将该账号关联到您的Google Cloud项目。详细指南请参考<Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">Google提供的说明文档</Anchor>。
3. 启用Google Play Developer API。详细指南请参考<Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">Google提供的说明文档</Anchor>。

   [![](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="1.2.在Google Cloud Platform中配置您的服务账户">

**前提条件**：访问Google Cloud Platform。

**要配置您的服务帐户，请按照以下步骤操作**:

1. 创建或找到**服务账号**：
   1. <span class="af-ol-a"></span>在Google Cloud Platform中，前往<strong>Service accounts（服务账号）</strong>部分，点击 **“Create Service Account（创建服务账号）”**。

      [![](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)
   2. 填写服务账号的详细信息。

      [![](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)
   3. 复制电子邮件地址。

      [![](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)
   4. 点击**Create and continue（创建并继续）**，进入下一步。

      [![](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)
   5. 在**Grant this service account access to the project**（为该服务账号开放项目权限）部分的“Select a role”（选择角色）字段中，选择**Pub/Sub subscriber**。

      [![](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)
   6. 点击**Continue** > **Done**，完成服务账号的创建。

      [![](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)
2. 下载**服务账号私钥**：
   1. <span class="af-ol-a"></span>在Google Cloud Platform中，进入<strong>Service accounts（服务账号）</strong>部分，从列表中找到你刚创建的服务账号，点击 **“更多操作”** 图标。
   2. 点击 **“管理私钥（Manage keys）”**。

      [![](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)
   3. 点击 **添加私钥** > **创建新私钥**。

      [![](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)
   4. 在**创建私钥**窗口中，

      在
   5. ![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)私钥类型下，选择**JSON**，然后单击**创建**。**![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)** 点击**Create**，下载JSON格式的密钥文件。

      [![](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)
   6. 保存JSON私钥文件，稍后您需要将该文件将上传至AppsFlyer。 **请注意**：请务必保存密钥，关闭窗口后将无法再次获取。如未保存，您需要重新创建新密钥。

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="1.3.在Google Play Console中设置API访问权限。">

**前提条件**：Google Play Console访问权限。

**注意**：服务账号的证书和权限设置完毕后，可能需要等待一段时间（有时可达24小时），然后才能正常使用。在此期间你可能会在后续步骤中遇到报错。

**在Google Play Console中设置API访问权限的操作如下：**

1. 在Google Play Console中，进入**Users and permissions（用户和权限）**，找到您创建的服务账号并点击**Invite new users（邀请新用户）**。

   [![](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)
2. 在<strong>Email address（邮箱地址）</strong>字段中，填写您在第1.2.1.3步创建服务账号时复制的邮箱地址。

   [![](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)
3. 在**Permissions**（权限）部分，进入**Account permissions**（账号权限）选项卡，然后同时勾选以下两项：

   * View financial data, orders, and cancellation survey responses（查看财务数据、订单和取消订阅问卷答复）
   * Manage orders and subscriptions（管理订单和订阅）[![](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)
4. 在**App permissions**（应用权限）标签页中，点击**Add app**（添加应用），然后选择应用。如有需要可添加多个应用。

   [![](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)
5. 点击**Invite user**（邀请用户）。

   [![](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)
6. 在确认弹出窗口中，点击**Send invite**（发送邀请）。

   [![](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="1.4.将服务账户私钥上传到AppsFlyer。">

上传并验证您在[步骤 1.2](#12-configure-your-service-account-in-the-google-cloud-platform)中下载的 Google JSON 密钥。

**前提条件**：具备AppsFlyer管理员权限。

**要将账户私钥上传到 AppsFlyer，请按照以下步骤操作**:

1. <Anchor target="_blank" href="/marketers/zh/docs/about-roi360-store-revenue#启用-roi360-店铺收入">启用 ROI360 商店收入</Anchor>。
2. 在**服务账户私钥和权限**步骤中，在**上传Google JSON密钥**字段里，单击[<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.2%" />upload-2.png **上传图标。**](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png)
3. 上传您在[步骤 1.2](#12-configure-your-service-account-in-the-google-cloud-platform)中下载的JSON文件。
4. 点击**验证密钥。** **请注意：**
   * 设置服务账号凭据和权限后，最多可能需要 24 小时才能生效。在此期间进行密钥验证或验证测试时可能会出现错误。
   * 如需绕过最长 24 小时的等待时间，可在Google Play Console中打开任意应用，进入**Monetize > Products > Subscriptions/In-app products**，并对某项内容进行修改（如编辑商品描述并保存）。该操作将立即刷新账号凭据和权限。修改完成后可撤销操作。
5. 单击**保存并继续**。

</Accordion>

<div id="note-1" />

<div id="option-2---your-endpoint-as-the-primary-endpoint" />

<div id="option-1-recommended---appsflyer-as-the-primary-endpoint" />

<div id="step-2-ios-set-up-app-store-server-notifications" />

## 步骤2（iOS）：设置App Store服务器通知

在步骤2中，设置通过AppsFlyer接收App Store通知的方式。

* 如果您已在 App Store Connect 中配置了 App Store 服务器通知端点（例如，您自己的后端或另一项服务），请<strong>在选项 1（推荐）</strong>和**选项 2** 之间进行选择。
* 如果您尚未在 App Store Connect 中配置端点，请选择**选项 1**。

**选项 1（推荐）——将 AppsFlyer 设为主要终点**

将现有的 App Store Connect 通知 URL 替换为 AppsFlyer 端点，并在 AppsFlyer 中将您之前的端点添加为转发目标。您当前的订阅逻辑和工作流保持不变，并将继续按预期运行。

此选项的通知流程如下：

1. App Store Connect 会向 AppsFlyer 发送通知
2. AppsFlyer 会为 ROI360 处理这些数据
3. AppsFlyer 会将所有通知**实时**转发至您的现有端点

要使用此选项，请完成步骤 [2.1](#21-copy-the-appsflyer-server-notifications-endpoint)、[2.2](#22-send-notifications-directly-to-appsflyer) 和 [2.4](#24-test-the-server-notifications-integration)。

**选项 2 - 将您的终点设为主要终点**

如果您希望保留现有端点作为主要接收端，请将服务器配置为将 App Store 服务器通知转发至 AppsFlyer。

若要使用此选项，请跳过步骤 2.1 和 2.2，并完成步骤 [2.3](#23--optional--forward-notifications-from-your-endpoint-to-appsflyer) 和 [2.4](#24-test-the-server-notifications-integration)

<div id="21-copy-the-appsflyer-server-notifications-endpoint" />

<Accordion title="2.1 复制AppsFlyer服务器通知端点">

要复制AppsFlyer服务器通知端点，请按照以下步骤操作：

1. <strong>在AppsFlyer中，</strong>在**App Store服务器通知**步骤，复制AppsFlyer服务器通知端点。
2. 如果您之前已拥有另一个 App Store 服务器通知端点，并希望 AppsFlyer 将通知转发至该端点，请选择 **“将通知副本转发至您的服务器”（仅适用于选项 1）。**
3. 在弹出的文本框中输入您的通知转发端点。

</Accordion>

<div id="22-send-notifications-directly-to-appsflyer" />

<Accordion title="直接将通知发送到AppsFlyer:">

若要将通知直接发送至 AppsFlyer，请将 AppsFlyer 设置为 App Store 服务器通知的主要端点。

1. 在**App Store Connect**中，进入**App Information**部分，向下滚动至**App Store Server Notifications**，在**Production Server URL**右侧点击**Edit**。

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. 粘贴[从AppsFlyer复制的AppsFlyer服务器通知端点](#21-copy-the-appsflyer-server-notifications-endpoint)，选择**版本2通知**，然后点击 **保存**。 **注意：** 系统已不再支持版本1通知。如果 Apple Store Connect 中未显示“通知版本”选择器，则说明您已使用第 2 版。

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. 进入**App Information**部分，向下滚动至**App Store Server Notifications**，在**Sandbox Server URL**右侧点击Edit。

   [![](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)
4. 粘贴[从AppsFlyer复制的AppsFlyer服务器通知端点](#21-copy-the-appsflyer-server-notifications-endpoint)，选择**版本2通知**，然后点击 **保存**。**注意：** 系统已不再支持版本1通知。如果 Apple Store Connect 中未显示“通知版本”选择器，则说明您已使用第 2 版。

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)

</Accordion>

<div id="23--optional--forward-notifications-from-your-endpoint-to-appsflyer" />

<Accordion title="2.3 [可选]将通知从您的端点转发到 AppsFlyer">

仅当您希望将端点保留为 App Store 服务器通知的主要接收端（而非直接将通知发送至 AppsFlyer）时，才需执行此步骤。

此选项并非推荐的配置方案，且需要进行后端实现。如果您已在上述第 **2.2** 步中将 AppsFlyer 配置为主端点，请跳过此步骤。

要将服务器通知从您的端点转发到AppsFlyer，请按照以下步骤操作：

1. 在**App Store Connect**中，进入**App Information**部分，向下滚动至**App Store Server Notifications**，在**Production Server URL**右侧点击**Edit**。

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. 粘贴**您的服务器端点URL**。

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. 选择**版本2通知。请注意：** 系统已**不再支持**版本1通知。如果 Apple Store Connect 中未显示“通知版本”选择器，则说明您已使用第 2 版。
4. 点击**Save**保存。
5. **同样在App Store Connect的App Information部分，找到Sandbox Server URL，点击Edit。**

   [![](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)
6. 粘贴**您的服务器端点URL**。

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)
7. 选择**版本2通知。请注意：** 系统已**不再支持**版本1通知。
8. 点击**Save**保存。
9. 请配置您的后端，将 Apple 服务器通知转发至 AppsFlyer 通知端点 URL。请求必须与从 Apple 接收到的 App Store 有效负载完全一致，请参阅 <Anchor target="_blank" href="https://developer.apple.com/documentation/appstoreserverapi/signedpayload#discussion">Apple 的格式要求</Anchor>。

</Accordion>

<div id="24-test-the-server-notifications-integration" />

<Accordion title="2.4 测试服务器通知集成">

若要确认 AppsFlyer 是否正确接收了 App Store 服务器通知，或者如果您最近配置了端点但尚未收到任何服务器通知：

1. 在 AppsFlyer 中，进入 **“App Store 服务器通知**”步骤。
2. 点击 **“测试集成**”。AppsFlyer 会向 Apple 发送一条测试通知请求，并检查过去 7 天内是否收到过 Apple 发来的有效通知，随后显示以下其中一项：

   * 确认是否已收到有效通知。
   * 一条状态消息，表示未找到任何通知。

   <div id="note-2" />

   > 📘 **注意**
   >
   > Apple 可能需要几秒钟才能发送测试消息。


   * 如果状态仍显示为无效，请稍等片刻后再试一次。
   * 测试成功后，或者当您准备继续时，请点击 **“保存并下一步**”。

</Accordion>

<div id="step-2-android-set-up-google-play-server-notifications" />

## 步骤 2（Android）：设置Google Play服务器通知

要接收来自Google Play 的应用内购买和订阅收入数据，可选择以下两种方式之一：

* 【推荐】由Google Play直接向AppsFlyer发送通知若选择此方式，通知副本将不会转发至你的端点。如果您想选择此选项，可以查看[直接将 Google Play通知发送到AppsFlyer](#21-send-google-play-notifications-directly-to-appsflyer)。
* Google Play先将通知发送给您，再由您转发至AppsFlyer。如果您选择此选项，请查看[将Google Play通知转发到AppsFlyer](#22--optional--forward-google-play-notifications-to-appsflyer)。

**前提条件**：Google Play Console以及AppsFlyer后台访问权限。

<div id="21-send-google-play-notifications-directly-to-appsflyer" />

<Accordion title="2.1将Google Play通知直接发送至AppsFlyer的操作如下：">

1. 在 AppsFlyer 中，在第 2 步 **“设置 Google Play 服务器通知**”中，请选择 **“允许 AppsFlyer 主题直接从 Google 接收 RTDN 消息**”。
2. 将AppsFlyer topic复制到剪贴板。
3. 在**Google Play Console** > **主页**中，选择查看您的应用程序。打开面板。

   [![](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)
4. 前往**Monetize with Play** > **Monetization setup**，在**Google Play Billing**部分，确认已勾选Enable real-time notification（启用实时通知）

   [![](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)
5. 在**Topic name**（主题名称）字段中，粘贴您复制的AppsFlyer topic地址。

   [![](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)
6. 在**Notification content**部分选择**Subscriptions, voided purchases, and all one-time products**（订阅、作废的购买交易以及所有一次性付费产品）。

   [![](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)
7. 点击**Save Changes**，保存更改。设置可能需要一些时间才能生效（最长可达24小时），请等待设置生效后再进行测试。

</Accordion>

<div id="22--optional--forward-google-play-notifications-to-appsflyer" />

<Accordion title="1.6. 【或者】将Google Play的通知转发给AppsFlyer">

**注意**：如果你已选择推荐方式（即由Google Play直接将通知发送至AppsFlyer）来接收应用内购买和订阅收入数据，请跳过此步骤。此步骤仅适用于未使用推荐方法的情况。如果你已完成推荐方式中的相关设置，即创建了由AppsFlyer直接接收Google Play RTDN通知的topic，请跳过此步骤。

如需将AppsFlyer设置为现有Pub/Sub topic的订阅者，请按照以下说明操作。

**前提条件**：Google Cloud Platform及AppsFlyer后台访问权限。

<strong>【或者】</strong>1.6：将Google Play的通知转发给AppsFlyer

1. 在**AppsFlyer**平台中，从侧边菜单选择**设置** > 收入设置。
2. 选择您的应用，
3. 在**购买与订阅**标签中，选择**将您的RTDN主题消息转发到AppsFlyer**。
4. 将端点URL复制到剪贴板。
5. 进入Google Cloud Platform，在相关项目下搜索**Pub/Sub**。

   [![](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)
6. 进入**Pub/Sub**的**Topics**部分，确认您有一个专用于订阅的pub/sub topic。

   [![](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)
7. 进入**Pub/Sub**的**Subscriptions**部分，点击**Create subscription**。

   [![](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)
8. 输入**Subscription ID**。

   [![](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)
9. 从下拉列表中选择相关订阅的pub/sub主题。

   [![](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)
10. 在**Delivery type**（发送方式）部分中，选择**Push**（推送）。

    [![](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)
11. 粘贴从AppsFlyer复制的**端点 URL**。

    [![](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)
12. 在**Expiry period**（期限）部分，选择**Never expire**（永不过期）。

    [![](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)
13. 点击**Create**，

    [![](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)
14. 进入**Subscriptions**部分，点击您选择的Topic name（主题名称）。

    [![](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)
15. 将主题名称复制到剪贴板。

    [![](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)
16. 从**Google Play Console**进入**Monetization setup**> **Monetization setup.** ，在**Google Play Billing**部分中，将前一步中复制的topic名称粘贴到Topic name字段中。

    [![](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)
17. 在**Notification content**部分选择**Subscriptions, voided purchases, and all one-time products**（订阅、作废的购买交易以及所有一次性付费产品）。

    [![](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)
18. 点击**保存更改**。设置可能需要一些时间才能生效（最长可达24小时），请等待设置生效后再进行测试。

</Accordion>

<div id="23-send-a-test-notification-from-google-play-console" />

<Accordion title="2.3 从 Google Play 控制台发送测试通知">

要验证 AppsFlyer 是否正确接收了 Google Play 实时开发者通知 (RTDN)，请从 Google Play 控制台发送一条测试通知：

1. 点击 **“发送测试通知”**。这将向为 AppsFlyer 配置的 Pub/Sub 主题发送一条测试 RTDN 消息。

   <Image alt="" src="https://files.readme.io/4d7aa79eb963373223cfde1d32db16b739119a86d8d4f0cf6ce026d42a709bf3-42170040528657.png" width="1444px" />altimage (9).png
2. 在 **“Google Play 计费**”下，找到“主题名称”部分。
3. 在左侧菜单中，导航至 **“通过 Play 变现**”→**“变现设置**”。
4. 前往 Google Play 控制台。

<div id="24-confirm-notification-delivery-in-appsflyer" />

<Accordion title="2.4 在 AppsFlyer 中确认通知送达情况">

1. 测试成功后，或者当您准备继续时，请点击 **“保存并下一步**”。
2. 结果：AppsFlyer 会显示过去 7 天内是否收到过任何通知。
   * 如果操作成功，界面将显示最近一条通知的日期和时间。
   * 如果未收到任何通知，界面将显示过去7天内未发现任何通知。
   * 如果未显示状态，请检查您的 Pub/Sub 配置，然后重新发送测试通知。
3. 在 **“Google Play 服务器通知**”步骤中，点击 **“测试集成**”。

</Accordion>

</Accordion>

<div id="step-3-implement-sdk-connector" />

## 第3步：部署SDK connector

在此步骤中，您需要请开发人员对AppsFlyer Purchase SDK connector进行对接，并配置沙盒环境以进行测试。

部署SDK connector的操作步骤如下：

1. 在 **“实施 SDK 连接器**”步骤中，复制仪表盘中显示的**预设消息**。
2. 将其发送给您的开发人员。包括：
   * 应用名称和App ID
   * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">SDK对接指南</Anchor>链接。
   * 沙盒环境配置说明 (`sandbox = true`)
   * 测试步骤（使用**TestFlight**）

此处包含了开发人员进行对接和测试所需的全部信息。

<div id="note-3" />

> 📘 **注意**
>
> 该连接器使用自动事务检测。作为另一种方法，您可以调用 SDK 方法`validateAndLog`来手动记录每笔交易。此方法不支持连接器提供的所有功能。有关这两种 SDK 集成选项的详细信息，请参阅 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">DevHub 文档</Anchor>。

<div id="step-4-verify-sdk-implementation" />

## 第4步：验证 SDK 的实现

建议在沙盒环境中测试IAP和订阅收入对接，确保SDK connector已正确接入到相关应用中，且服务器通知的配置正确无误，AppsFlyer可正常收到通知。

<div id="test-sdk-implementation" />

<Accordion title="测试 SDK 实现">

若要查看 AppsFlyer 在过去 7 天内是否已收到来自您应用的有效购买和订阅事件数据包，请按照以下步骤操作：

1. 在 **“验证 SDK 实现**”步骤中，点击 **“测试 SDK 实现”**。
2. 查看结果，包括 AppsFlyer 接收到的最新有效负载的时间戳。

   <div id="note-4" />

   > 📘 **注意**
   >
   > 此测试仅用于确认请求已成功发送至 AppsFlyer，并不验证数据的完整性或准确性。

3. 要全面验证该实现，请继续执行以下测试步骤。

</Accordion>

<div id="sandbox-events-and-parameters" />

<Accordion title="沙盒事件和参数">

* SDK 连接器仅针对初始沙箱事务生成事件：
  * 应用内购买
  * 订阅
* AppsFlyer 仅在原始交易的 SDK 事件已被记录的情况下，才会处理服务器通知。
  * In-App Purchase key
  * 订阅 S2S： `af_ars_sandbox_s2s`
* 如果 SDK 从未记录原始交易，则不会创建 S2S 事件。

**iOS 注意事项**

* 如果`af_purchase_sandbox_sdk` 包含 `af_sandbox_revenue`，则它映射到一个生产规则 `af_purchase`。
* `af_purchase_free`如果没有收入，则映射到生产环节。

**关于 Android 的注意事项**

* **许可证**测试者的购买操作始终会触发沙盒事件，即使 SDK 中未配置沙盒模式。

**测试事件的必填参数**

请确保每个沙盒购买事件包含：

* **收入 = 0**（以免影响实际报表）。
* `af_sandbox_revenue` = 实际产品价格（以便正确核算收入）。
* True请`false`返回并核对商店密钥。
* `af_validation_type`**af\_validation\_type**

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="测试应用内购买（IAP）和订阅收入数据">

**前提条件**：

* 对于iOS应用，请确保App Store connect中“App Store Server Notifications”（应用商店服务器通知）部分下的**Sandbox Server URL**（沙盒服务器地址）配置为AppsFlyer端点。

  [![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

**测试应用内购买和订阅收入**：

1. 请让您的开发人员按照<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-android-purchase-connector#-testing-the-integration">安卓</Anchor>、 <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-apple-purchase-connector#-testing-the-implementation-in-sandbox">iOS</Anchor>和<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-purchase-connector/blob/master/docs/purchaseConnectorUnity.md#testing-the-implementation-in-sandbox">Unity</Anchor>的专用说明在SDK connector中配置沙盒环境。
2. <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">在 Google Play 中</Anchor>使用<Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">“许可证测试工具</Anchor>”进行试购或订阅。对于 iOS 设备，请使用 <Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight</Anchor>。**请注意**：每台设备仅可对订阅产品进行一次测试。实际上，一台设备无法对同一项订阅进行多次测试购买。后续尝试将不予记录。
3. 使用Google Play中的<Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">License Tester</Anchor>或iOS中的<Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight</Anchor>，进行测试退款、订阅续订或取消订阅的操作。**请注意**：如果您正在测试订阅类产品，请预留足够的时间，以便 AppsFlyer 接收来自应用商店的服务器通知——该通知通常会在首次购买完成后几分钟内发送。
4. 在 **“Verify SDK 连接器实现**”步骤下，点击 <strong>“测试 SDK 实现”。</strong>该指标显示过去 7 天内是否成功接收到了来自 Purchase Connector 的任何 SDK 有效载荷。
5. 请确保测试事件以以下其中一种方式显示：

   * 在“<Anchor target="_blank" href="/marketers/zh/docs/testing-the-sdk-integration-for-marketers#view-live-events">实时事件查看器</Anchor>”中查看该事件。

   * 在<Anchor target="_blank" href="/marketers/zh/docs/activity-metrics-in-my-dashboards">“我的仪表板</Anchor>”中的<Anchor target="_blank" href="/marketers/zh/docs/activity-metrics-in-my-dashboards">“活动视图”</Anchor>中查看事件数据。
6. 请确认该事件是否显示在 AppsFlyer 活动仪表盘中。在 AppsFlyer 中，进入 **“分析**”**>“活动**”，在 **“活动趋势**”图表中，打开“应用内事件”选项卡，然后选择要测试的事件。自动续订的订阅购买称为 `af_ars_s2s_sandbox`.该事件具有以下特征：
   * 收入值为0（避免AppsFlyer的实际报告数据受到扭曲）。
   * 一个`af_sandbox_revenue`包含所购产品收入值的参数，以确保报告的收入准确无误。

</Accordion>

<div id="step-5-verify-and-update-settings" />

## 第5步：验证并更新设置

完成上述设置的配置并保存最后一步后，系统将自动跳转至当前配置视图，您可以在该视图中验证或更新以下设置：

1. 请确保“**通过 App Store 验证购买**”开关已开启。
2. 在**购买**中检查以下选项：
   * **防止重复计算，确保数据准确性**：避免记录已被上报的交易。
   * **自动衡量退款、取消和负收入**：对退款相关事件进行统计，并将其记录为负收入。
   * **消除家庭共享带来的误差**：避免因家庭共享导致收入被重复计算。这些事件会被标记为并报告为零收入。
3. 请确保“**为自动续订订阅测量并计入收入**”开关已开启：
4. 以下设置的状态：
   * **App Store 密钥**设置
   * **服务器通知端**点的设置
   * 实施并测试 SDK 连接器

<div id="step-6-release-the-app-versions-with-the-sdk-connector" />

## 第6步:发布已对接SDK connector的应用版本

完成前述所有配置并将AppsFlyer的purchase SDK connector集成至应用后，请通知开发人员发布集成后的新版本应用。

但在发布前，请确保以下事项已处理：

* 您在AppsFlyer中配置的验证规则不会拦截您想要记录的IAP或订阅事件。
* 您的开发人员已将所有沙盒标签设置为“false”。

[![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

一旦包含SDK connector的应用版本发布，相关的<Anchor target="_blank" href="/marketers/zh/docs/about-roi360-store-revenue#iaprelated-events-and-parameters">应用内购买</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/about-roi360-store-revenue#subscriptionrelated-events-and-parameters">订阅事件</Anchor>将开始生成，并出现在所有AppsFlyer面板中，以及汇总数据和原始数据报告（<Anchor target="_blank" href="/marketers/zh/docs/revenue-etl-reports">包括Revenue ETL</Anchor>）中。

**注意：** 仅当用户更新至包含SDK connector的应用版本后，事件才会开始生成。因此，在更新后的应用版本被全面采用之前，预计应用的收入数据与商店数据之间会出现差异。

<div id="switch-to-roi360-store-revenue-from-receipt-validation" />

## 切换至 ROI360 店铺收入（来自收据验证）

如果您已完成“收据验证”的入门设置，但希望启用 ROI360 Store 收入产品，请执行以下操作：

1. 在AppsFlyer中，从左侧菜单进入[<Image alt="" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.54%" />settings-roi.png**设置**，在**ROI360**下选择**收入设置**。](https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png)
2. 打开**购买与订阅**标签页。出现一条横幅提示，显示ROI360已可用但尚未激活。
3. 点击 **“查看产品对比**”，了解相关优势，包括退款归因、净收入报告以及完整的订阅生命周期衡量。
4. 点击 **“激活 ROI360”。**
5. 执行 **“启用 App Store 服务器通知**”步骤。如需了解更多信息，请参阅[“设置 App Store 服务器通知](#步骤2ios设置app-store服务器通知)”或[“设置 Google Play 服务器通知”](#步骤-2android设置google-play服务器通知)。
6. 在“**购买与订阅**”部分，请确认“**产品类型**”现已设置为 **ROI360**。
7. 请检查您当前的 SDK 配置，以确保其能够支持您所需的 ROI360 Store 收入功能。

<div id="note-5" />

> 📘 **注意**
>
> ROI360 Store 的收入支持两种集成方式：购买 SDK 连接器，并进行验证和日志记录。在这两者中，我们建议使用 **“Purchase SDK Connector**”，以便享受以下优势：
>
> * 自动交易检测
> * 现有订阅用户（整合前已订阅的用户）的收入核算
> * 支持订阅价格变更，确保在价格更新时能够准确报告收入。
>
> 如果您不需要这些功能，可以继续使用 **“验证和日志记录**”集成。
>
> **如何查看您的 SDK 集成方式**
>
> 要确认您的应用是否使用“购买 SDK 连接器”或“验证和记录”功能：
>
> 1. 转到 **“集成 SDK 连接器**”步骤。
> 2. 点击 **“测试 SDK 集成**”。您将看到过去 7 天内 AppsFlyer 接收到的最新 SDK 数据包的时间，以及该数据包是来自 **“购买 SDK 连接器**”还是 **“验证和日志记录**”。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01KD31QE0BCW0BX9BNNDK6DJRA=%E6%A6%82%E8%A7%88 h_01KD31QE0BQAQ0CS1FJ46TV6K1=%E6%B3%A8%E6%84%8F step-1-ios-set-up-app-store-connect-keys=%E6%AD%A5%E9%AA%A42ios%E8%AE%BE%E7%BD%AEapp-store-connect%E5%AF%86%E9%92%A5 h_01KD31QE0BE3ST0TV3KQ1M5AB0=%E6%AD%A5%E9%AA%A42ios%E8%AE%BE%E7%BD%AEapp-store-connect%E5%AF%86%E9%92%A5 h_01KD31QE0BBYES1C2Y1MB665EF=11-create-the-app-store-connect-keys h_01KD31QE0B4G0NGRYBTS2TRZQR=12-set-the-app-store-connect-key-in-appsflyer step-1-android-set-up-service-account-key-and-permissions=%E6%AD%A5%E9%AA%A4-2android%E8%AE%BE%E7%BD%AE%E6%9C%8D%E5%8A%A1%E8%B4%A6%E6%88%B7%E5%AF%86%E9%92%A5%E5%92%8C%E6%9D%83%E9%99%90 h_01KD31QE0BVQNJZ8PKKYKK9Q79=%E6%AD%A5%E9%AA%A4-2android%E8%AE%BE%E7%BD%AE%E6%9C%8D%E5%8A%A1%E8%B4%A6%E6%88%B7%E5%AF%86%E9%92%A5%E5%92%8C%E6%9D%83%E9%99%90 h_01KD31QE0BP21EHP5RPBZ5PX2N=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD31QE0B5G8SDGZQ8NE07QAE=12-configure-your-service-account-in-the-google-cloud-platform h_01KD31QE0CBMGHXJTXT4JPBV70=13-set-api-access-permissions-in-google-play-console h_01KD31QE0CH5M5X9M9G68N2PPZ=14-upload-the-service-account-private-key-to-appsflyer step-2-ios-set-up-app-store-server-notifications=%E6%AD%A5%E9%AA%A42ios%E8%AE%BE%E7%BD%AEapp-store%E6%9C%8D%E5%8A%A1%E5%99%A8%E9%80%9A%E7%9F%A5 h_01KD31QE0CZAJ7SH2EECDJ11YN=%E6%AD%A5%E9%AA%A42ios%E8%AE%BE%E7%BD%AEapp-store%E6%9C%8D%E5%8A%A1%E5%99%A8%E9%80%9A%E7%9F%A5 h_01KD31QE0C9YFBM01GGE2PZDNR=21-copy-the-appsflyer-server-notifications-endpoint h_01KD31QE0C4MRYPMMQ31BRAYS7=22-send-notifications-directly-to-appsflyer 23-%5Boptional%5D-forward-notifications-from-your-endpoint-to-appsflyer=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0CWXTKDND5F4Q34J7G=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0C2QWHBJ8AWMEMP2SD=24-test-the-server-notifications-integration h_01KD31QE0CA26Y430AMK474NTC=%E6%B3%A8%E6%84%8F-1 step-2-android-set-up-google-play-server-notifications=%E6%AD%A5%E9%AA%A4-2android%E8%AE%BE%E7%BD%AEgoogle-play%E6%9C%8D%E5%8A%A1%E5%99%A8%E9%80%9A%E7%9F%A5 h_01KD31QE0CKP0PTBQ4XCT9NDE1=%E6%AD%A5%E9%AA%A4-2android%E8%AE%BE%E7%BD%AEgoogle-play%E6%9C%8D%E5%8A%A1%E5%99%A8%E9%80%9A%E7%9F%A5 h_01KD31QE0C1RYXW6ADHMQJ3908=21-send-google-play-notifications-directly-to-appsflyer 22-%5Boptional%5D-forward-google-play-notifications-to-appsflyer=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CFVEBJV3E93Z5RDAP=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CTFNTY52F0C9D3RY2=23-send-a-test-notification-from-google-play-console h_01KD31QE0CV17JMVVB7ZPT1G8W=24-confirm-notification-delivery-in-appsflyer step-3-implement-sdk-connector=%E7%AC%AC3%E6%AD%A5%E9%83%A8%E7%BD%B2sdk-connector h_01KD31QE0CPK1EYVT0BSYTTZFM=%E7%AC%AC3%E6%AD%A5%E9%83%A8%E7%BD%B2sdk-connector h_01KD31QE0C65DQ59ZKG8V886JW=%E6%B3%A8%E6%84%8F-2 step-4-verify-sdk-implementation=%E7%AC%AC4%E6%AD%A5%E9%AA%8C%E8%AF%81-sdk-%E7%9A%84%E5%AE%9E%E7%8E%B0 h_01KD31QE0C9KGGFVQR6HYR5AYM=%E7%AC%AC4%E6%AD%A5%E9%AA%8C%E8%AF%81-sdk-%E7%9A%84%E5%AE%9E%E7%8E%B0 h_01KD31QE0C0VKWF5EBBR761C1J=test-sdk-implementation h_01KD31QE0C7RN657P9KPFV5725=%E6%B3%A8%E6%84%8F-3 h_01KD31QE0D0CR02260J5K8V8QX=sandbox-events-and-parameters h_01KD31QE0DNEBYXH4672363WYM=test-inapp-purchase-and-subscription-revenue step-5-verify-and-update-settings=%E7%AC%AC5%E6%AD%A5%E9%AA%8C%E8%AF%81%E5%B9%B6%E6%9B%B4%E6%96%B0%E8%AE%BE%E7%BD%AE h_01KD31QE0DQP78QG5HRSERR5S9=%E7%AC%AC5%E6%AD%A5%E9%AA%8C%E8%AF%81%E5%B9%B6%E6%9B%B4%E6%96%B0%E8%AE%BE%E7%BD%AE step-6-release-the-app-versions-with-the-sdk-connector=%E7%AC%AC6%E6%AD%A5%E5%8F%91%E5%B8%83%E5%B7%B2%E5%AF%B9%E6%8E%A5sdk-connector%E7%9A%84%E5%BA%94%E7%94%A8%E7%89%88%E6%9C%AC h_01KD31QE0D3HX2DEH7FQ1JR4MS=%E7%AC%AC6%E6%AD%A5%E5%8F%91%E5%B8%83%E5%B7%B2%E5%AF%B9%E6%8E%A5sdk-connector%E7%9A%84%E5%BA%94%E7%94%A8%E7%89%88%E6%9C%AC switch-to-roi360-store-revenue-from-receipt-validation=%E5%88%87%E6%8D%A2%E8%87%B3-roi360-%E5%BA%97%E9%93%BA%E6%94%B6%E5%85%A5%E6%9D%A5%E8%87%AA%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81 h_01KD31QE0DJNJ8T5XSZFCACMQF=%E5%88%87%E6%8D%A2%E8%87%B3-roi360-%E5%BA%97%E9%93%BA%E6%94%B6%E5%85%A5%E6%9D%A5%E8%87%AA%E6%94%B6%E6%8D%AE%E9%AA%8C%E8%AF%81 h_01KD31QE0DX0VDXKHDZTWTYHHX=%E6%B3%A8%E6%84%8F-4" />

---
title: 公告：更新用于 ROI360 iOS 收据验证的 App Store 凭证
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-08-28T09:24:00Z'
  edited_at: '2026-10-14T10:02:05Z'
  id: 27880822483985
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/27880822483985
---
| **最新动态** | 由于 Apple 已弃用当前的验证 API，AppsFlyer ROI360 的 iOS 收入验证流程将迁移至 Apple 全新的应用内购买验证 API。  <br />为了确保您能够持续实时、准确地验证 iOS 收入数据，请您在 AppsFlyer 平台中更新 App Store 凭证。  <br />如果您的应用仍在使用 Apple Notifications Version 1，请在更新凭证前切换至 Version 2 。 |
| --- | --- |
| **更新日期** | 02/04/2025 |
| **重要须知** | 此变更适用于使用 ROI360 进行 iOS 应用内购买与订阅收入验证的应用。<br />升级至新版 iOS 验证流程后，您将获得以下优势：<ul><li>通过 Apple 新的接口端点，增强与 Apple Store 的实时验证功能。</li><li>应用内事件结构或参数保持不变。</li><li>AppsFlyer Purchase SDK Connector 的验证结果响应将会更新，其中包括一个`store_status`用于标识验证失败的新代码。</li><li>无需更改现有 SDK 实现方式。</li></ul>Apple 可能随时停用旧版 API，为避免数据中断，我们强烈建议您尽快完成更新。 |
| **待办事项** | 请按照以下步骤操作：<ol><li>在 App Store Connect 中生成应用内购买密钥。</li><li>将该密钥上传至 AppsFlyer 平台中的「收入设置（Revenue Settings）」页面。</li></ol>如果您的应用仍在使用 Apple 服务器通知版本 1，则在更新凭证前必须先切换至版本 2 。若您的应用需满足此前提条件，系统将在「收入设置」页面显示提示消息。<br /><br />请参阅下方的详细操作指南：<ul><li>[更新用于 ROI360 iOS 收据验证的 App Store 凭证](#get-ios-credentials)</li><li>[设置苹果服务器通知的版本2](#send-app-store-notifications-directly-to-appsflyer)</li></ul> |

<div id="send-app-store-notifications-directly-to-appsflyer" />

<Accordion title="设置苹果服务器通知的版本2">

如果您的应用之前使用了 Apple 服务器通知版本 1，您必须在更新验证凭据之前在 App Store Connect 中切换到版本 2。（如果您的应用符合此前提条件，您将在**收入设置**页面看到相应提示。）

**设置苹果服务器通知的版本 2**

1. 在 **App Store Connect** 中，进入**应用信息**部分，找到 **App Store 服务器通知**。

   <Image alt="image__9_.png" src="https://files.readme.io/8e9c92cdf87303b58a6b604640b4f7adb3cf56c03e57df053e9d486b89345547-33812520143505.png" width="2009px" />
2. 对于 **Production Server URL**，点击 **编辑**。
3. 请勿更改 **Production Server URL** 中的 URL。

   <Image alt="image__9_.png" src="https://files.readme.io/fc7737793f2e7982e3e92d30dec45d7def98ef8ec6c3186ebbdf32a78f217a3d-33812683240977.png" width="1182px" />
4. 在**通知版本**项下，选择版本 2 通知。
5. 点击**保存**。
6. 在**App Store 服务器通知**部分，点击**Sandbox Server（沙盒服务器） URL**旁的**编辑**按钮。
7. 重复步骤 3-5。

</Accordion>

<div id="get-ios-credentials" />

<Accordion title="更新用于 ROI360 iOS 收据验证的 App Store 凭证">

iOS 应用内购买 API 对接所需的凭证是：

* 应用内购买密钥
* Key ID
* Issuer ID

**前期准备** ：

* 更新密钥涉及在 App Store Connect 和 AppsFlyer 两个平台中的操作。请在设置过程中保持这两个页面同时开启。
* 您需要管理员权限才能在 AppsFlyer 中设置密钥。

**更新 iOS 凭证的步骤**：

1. 在 App Store Connect 中，进入 **用户和访问权限**页面
2. 前往**用户和访问权限**> **对接**，在**密钥**列表中，选择**应用内购买**。  
   <Image alt="" src="https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png" width="532px" />
3. 点击 + 生成一个新的应用内购买密钥。  
   <Image alt="" src="https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png" width="384px" />
4. 输入您的 API 密钥名称。
5. 点击**生成**。
6. 在刚刚生成的密钥旁边，点击**下载应用内购买密钥**。**请注意**：该密钥只能下载一次，请妥善保存。
7. 在 **AppsFlyer** 平台中，从侧边菜单选择**设置** > **收入设置**。
8. 从列表中选择相关应用。
9. 在**购买和订阅**选项卡中，点击**更新密钥**。<Image alt="" src="https://files.readme.io/edcb9ef1c24f58b911792e924ca69173c487261e2ef35cf1a21270251c50e586-33405937635601.png" width="549px" />
10. 在**新密钥**区域的**应用内购买密钥**字段中，单击**上传图标**（<Image alt="upload-2.png" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="15px" />）以上传 p8 文件。
11. 在 App Store Connect 中，复制您刚刚生成的密钥的 **Key ID**，并将其粘贴到 AppsFlyer 购买和订阅设置中的 **Key ID**字段里。 <Image alt="" src="https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png" width="484px" />
12. 在 App Store Connect 中，复制 **Issuer ID** ，并将其粘贴到 AppsFlyer 购买和订阅设置中的 **Issuer ID**字段。**请注意**：如果页面顶部未显示 **Issuer ID**，请创建一个 App Store Connect API 密钥（具有任意权限级别）。之后，Issuer ID 将出现在应用内购买密钥的页面顶部。

    <Image alt="" src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw" width="474px" />
13. 在 AppsFlyer 购买和订阅设置中，点击 **验证密钥** 以确保您输入的密钥是正确的。
14. 点击**更新密钥**。一旦密钥更新，您的应用将全面迁移至 Apple 的新版 iOS 验证流程。

</Accordion>

<div data-zendesk-anchors="h_01JP2XAKZABDJYB9ZQS4N3ST4Z=send-app-store-notifications-directly-to-appsflyer h_01J14M3C6WNXPJJQHVWVNFB4GS=get-ios-credentials" />

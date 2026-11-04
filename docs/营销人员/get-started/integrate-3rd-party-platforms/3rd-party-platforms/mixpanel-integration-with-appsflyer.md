---
title: Mixpanel与AppsFlyer的集成
metadata:
  keywords:
    - Attribution
    - Mixpanel
    - SDK
    - integrated partner
    - Advertisers
    - Ad Networks
    - facebook mixpabel
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:33:01Z'
  edited_at: '2026-10-14T10:11:10Z'
  id: 207447103
  locale: zh-cn
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/zh-cn/articles/207447103
---
> **概要：** 了解如何自动将数据从AppsFlyer共享到Mixpanel，一个产品分析平台。

![](https://cdn.appsflyer.com/marketplace/static/logo/mixpanel.png)

AppsFlyer与Mixpanel之间的集成使您能够将来自AppsFlyer的获取活动信息导入到Mixpanel。

<div id="important" />

> 🚧 **重要提示！**
>
> 部分渠道限制第三方的数据共享。 这时，我们不会向渠道发送受限事件的回传，不论您是否在回传配置部分选择了该事件。

<div id="setting-up-mixpanel" />

## 设置Mixpanel

**前期准备：** 设置对接前，请务必先<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#联系相关渠道">联系该渠道</Anchor>并在其平台上开设账户。

**请按以下方式启用或修改该对接：**

1. **启用方式：** 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。  
   **修改方式**：从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索并选择相关渠道。
3. 点击**设置对接**，界面会跳转到对接设置页。
4. 进入**渠道对接**选项卡，选择需要对接的应用，并打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开 （启用） 状态。
5. 请按照下文说明，在各个选项卡中完成相关的对接配置。

了解更多关于<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">合作伙伴配置窗口标题</Anchor>.

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

下文说明了对接选项卡中所包含各部分内容。

<div id="general-settings" />

### 通用设置

<Image alt="mixpanel-general-settings.png" src="https://files.readme.io/df1b95eb3926aa7e10db338f156a87b88aabda6b97a4d28db2953e9e48a114e6-360017400598.png" width="542px" />

* * * **欧盟数据驻留**：默认情况下，AppsFlyer将数据发送到Mixpanel的美国服务器。要将数据发送到Mixpanel的欧盟服务器，请打开此切换。  
      \_token Mixpanel通过唯一的Token与AppsFlyer连接。如果您还没有Token，您必须从Mixpanel获取它以继续集成。

      **从Mixpanel获取Token：**

      1. 登录到您的Mixpanel账户： https://mixpanel.com/login/
      2. 在**Mixpanel**中，转到**分析**仪表板并点击齿轮图标。

         ![mixpanel-token-1.png](https://files.readme.io/f1fbc76fff621e12a7d91fed5ba49eb20f2b049de65c70b0ab32cadd997287d2-small-360014578477.png)
      3. 从项目的访问密钥部分复制您的Token，并将其粘贴到AppsFlyer Mixpanel集成选项卡中的**token**字段中。

         ![mixpanel-token-2.png](https://files.readme.io/e8e633ec87d963244652a53b9b21c495b0a850e234621a44d93b3034c640bff7-360014578757.png)
    * **发送广告主ID**：
      * 如果您使用AppsFlyer的customer\_user\_id参数，则在每次安装时都会将其发送到Mixpanel（请保持**发送广告主ID**禁用）。
      * 如果您没有使用AppsFlyer的customer\_user\_id - 启用<strong>发送广告主ID。</strong>设备ID作为customer\_user\_id（Mixpanel中的unique\_id）发送到Mixpanel。  
        了解更多关于AppsFlyer SDK集成指南的信息，适用于<Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">Android</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">iOS</Anchor>。
    * events开启以将安装数据发送到Mixpanel事件端点。
    * 人员启用此选项以将安装数据发送到 Mixpanel People 端点。  

      <div id="note" />

      > 📘 **注意**
      >
      > 要将安装回调发送到 Mixpanel，必须启用两个端点中的至少一个，**事件** 或 **用户**。

    * 高级数据共享启用此选项以向 Mixpanel 发送附加信息：c（活动）、network（pid）、impression\_based（是否为展示）。

<div id="default-postbacks" />

### 默认回传

AppsFlyer 可以在用户安装后自动将回调发送到 Mixpanel，包括安装和重新参与。重新参与发生在已经安装应用的用户通过活动点击后打开应用时。了解更多关于 <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#default-postbacks">默认回调</Anchor> 的信息。

[![](https://files.readme.io/6cf4f0e1b73c634c5fbe8f79e654ff3a3cd318bdca51d5e6b17933c307eb769d-36693858465809.png)](https://files.readme.io/6cf4f0e1b73c634c5fbe8f79e654ff3a3cd318bdca51d5e6b17933c307eb769d-36693858465809.png)

<div id="in-app-events-settings" />

### 应用内事件设置

![mixpanel-in-app-events-settings.png](https://files.readme.io/db5e4e6d5bbe084a94b90425d49345511c214ddc39380a2b8419659ad752cdb2-360014576637.png)

在此部分，您通过回调将 AppsFlyer 事件与 Mixpanel 进行映射。

<div id="note-1" />

> 📘 **注意**
>
> Mixpanel 使用他们自己的 SDK 捕获应用内事件。唯一可以发送到 Mixpanel 的事件是 af\_uninstall，而不是由他们捕获的事件。

详情请见应用内事件回传说明文档。

请按以下步骤配置应用内事件回传：

1. 输入 Mixpanel 令牌。
2. 启用应用内事件回传。
3. **要发送卸载的广告商 ID**，请启用 **发送广告商 ID**。
4. **要发送卸载的附加信息**，请启用 **高级数据共享**。
5. 点击**添加事件**，在列表中添加AppsFlyer事件。
6. 从下拉菜单中选择 **af\_uninstall**。
7. 从下拉菜单中选择相应的 **合作伙伴事件标识符**。
8. 从发送收入下拉菜单中选择所需选项：  
   * **不发送值与收入：** 仅发送事件本身，不发送事件值。
   * **含事件值不含收入值：** 发送除收入值以外的所有参数。
   * **含事件值和收入值** ：发送所有事件参数，包括收入值（如果事件中存在）。
9. 要完成集成配置，请单击 **保存集成**。

保存集成后，AppsFlyer 会将以下数据发送到 Mixpanel，以便每个有机和非有机安装：

* Mixpanel 令牌参数
* Customer\_user\_id 或设备 ID（IDFA / Google 广告 ID）
* Media Source（媒体渠道）
* 即广告系列的名称

**请注意**：卸载回传中不包含CUID。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

此合作伙伴不提供归因链接。

</Accordion>

<div id="cost-tab" />

<Accordion title="成本选项卡">

该合作伙伴不支持成本数据对接。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="广告收入选项卡">

该渠道不支持广告收入对接。

</Accordion>

<div id="permissions-tab" />

<Accordion title="授权选项卡">

此合作伙伴没有可用的权限。

</Accordion>

<div id="integrating-with-mixpanel-when-using-a-login-mechanism" />

## 在使用登录机制时与 Mixpanel 集成

以下是集成步骤的示例：

1. 用户已启动（打开）应用。
2. Mixpanel SDK 生成一个随机的唯一 ID (**distinct\_id**)。
3. 获取 Mixpanel 唯一 ID，并使用 Appsflyer SDK 函数 **setCustomerUserId** 将其设置为客户用户 ID。
4. 发送 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#start">**Start**</Anchor>。该 API 确保 AppsFlyer 可以成功检测安装、事件、回话和应用更新。
5. 在应用安装被归因后，向 Mixpanel 发送一个 **install** 事件，包含客户用户 ID，其中包括 Mixpanel 唯一 ID。
6. 当用户注册或登录时，Mixpanel 的 identify() 命令会使用用户标识符（例如，电子邮件或客户 ID）被调用。这将把初始随机唯一 ID 映射到注册用户 ID。  

   <Tabs>
   <Tab title="Android">

   Mixpanel Android - <Anchor target="_blank" href="https://developer.mixpanel.com/docs/android#section-combining-anonymous-and-identifiable-user-data">合并匿名和可识别的用户数据</Anchor>

   ```java
   MixpanelAPI mixpanel = MixpanelAPI.getInstance(context, MIXPANEL_TOKEN);
   mixpanel.identify("user@example.com");

   // Mixpanel v6.2.0 and below should use the following API:
   mixpanel.getPeople().identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Objective C">

   Mixpanel iOS Objective C - <Anchor target="_blank" href="https://developer.mixpanel.com/docs/ios#section-combining-anonymous-and-identifiable-user-data">合并匿名和可识别的用户数据</Anchor>

   ```objectivec
   [mixpanel identify:@“user@example.com”];
   ```

   </Tab>

   <Tab title="Swift">

   Mixpanel iOS Swift - [合并匿名和可识别的用户数据](https://developer.mixpanel.com/docs/swift#section-combining-anonymous-and-identifiable-user-data)

   ```swift
   mixpanel.identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Unity">

   Mixpanel Unity - [合并匿名和可识别的用户数据](https://developer.mixpanel.com/docs/unity#section-combining-anonymous-user-data-with-identifiable-user-data)

   ```csharp
   // set customer user id or device id
   Mixpanel.Identify(“user@example.com”);
   ```

   </Tab>
   </Tabs>

7. Mixpanel 从 AppsFlyer 接收 customer\_user\_id，作为用户 ID 的别名（例如，电子邮件地址）。

<div id="note-2" />

> 📘 **注意**
>
> 如果您在应用程序中没有使用任何注册流程，请按照上述步骤 1-3 实施。

<div id="viewing-appsflyer-data-in-mixpanel" />

## 在 Mixpanel 中查看 AppsFlyer 数据

下面的截图是一个漏斗报告，用于查看从安装到价值事件的转化，按媒体来源细分。此外，还可以查看每个媒体来源的转化时间。

[![](https://files.readme.io/fdffbe0a2f29c8a8b02b600966583cdeb4917bb48f0502e9b00ef39daa2fa835-9646475113361.png)](https://files.readme.io/fdffbe0a2f29c8a8b02b600966583cdeb4917bb48f0502e9b00ef39daa2fa835-9646475113361.png)

[![](https://files.readme.io/043a96a00e46a3daaef2b9fa4d58d252391ca2bb14307437f28c447d96ae97d6-9646475229841.png)](https://files.readme.io/043a96a00e46a3daaef2b9fa4d58d252391ca2bb14307437f28c447d96ae97d6-9646475229841.png)

<div data-zendesk-anchors="h_01H9FKEWTEN4F8FM5C9A9ES6HN=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA setting-up-mixpanel=%E8%AE%BE%E7%BD%AEmixpanel h_01H9FKEWTEGMEVH3SK739DD719=%E8%AE%BE%E7%BD%AEmixpanel h_01H9FKEWTE90WR75PMNN93JAXE=integration-tab general-settings=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01H9FKEWTEMT7VGTTFWFMJHYA8=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01H9FKEWTEV3RWKMWZN0EXFFNP=%E6%B3%A8%E6%84%8F default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 h_01H9FKEWTER31RXAH216TRXQPM=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-events-settings=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01H9FKEWTERRVKPQFF1B8QQERE=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%AE%BE%E7%BD%AE h_01H9FKEWTEEMMQ0KKRZXRJRE25=%E6%B3%A8%E6%84%8F-1 h_01H9FKEWTEEQ0GHF87V20TX9W0=attribution-link-tab h_01H9FKEWTEJ61197SN3R6JXYCP=cost-tab h_01H9FKEWTEA7GN2HHK3QD62A3A=ad-revenue-tab h_01H9FKEWTET4QD1RE0HJZM64D4=permissions-tab integrating-with-mixpanel-when-using-a-login-mechanism=%E5%9C%A8%E4%BD%BF%E7%94%A8%E7%99%BB%E5%BD%95%E6%9C%BA%E5%88%B6%E6%97%B6%E4%B8%8E-mixpanel-%E9%9B%86%E6%88%90 h_01H9FKEWTE9DEANTXKPD286GD2=%E5%9C%A8%E4%BD%BF%E7%94%A8%E7%99%BB%E5%BD%95%E6%9C%BA%E5%88%B6%E6%97%B6%E4%B8%8E-mixpanel-%E9%9B%86%E6%88%90 h_01H9FKEWTFZ107Y999WEMB3409=%E6%B3%A8%E6%84%8F-2 viewing-appsflyer-data-in-mixpanel=%E5%9C%A8-mixpanel-%E4%B8%AD%E6%9F%A5%E7%9C%8B-appsflyer-%E6%95%B0%E6%8D%AE h_01H9FKEWTF9PFNVHTZGDKBX75Y=%E5%9C%A8-mixpanel-%E4%B8%AD%E6%9F%A5%E7%9C%8B-appsflyer-%E6%95%B0%E6%8D%AE" />

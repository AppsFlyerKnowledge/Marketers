---
title: 广告主的Google Ads（AdWords）对接设置指南
metadata:
  keywords:
    - Integration
    - Google AdWords
    - Configuration
    - google
    - migration
    - Advertisers
    - google ads configuration
    - ads
    - google ads
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-05-17T19:16:15Z'
  edited_at: '2026-10-14T10:12:33Z'
  id: 115002504686
  locale: zh-cn
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/zh-cn/articles/115002504686
---
> **概要：** 本文重点讲解了如何将您的Google Ads账户接入AppsFlyer，以便集中查看所有广告的归因数据。

在 AppsFlyer 中设置 Google Ads 集成，以测量和归因来自您的 Google Ads 活动的安装和应用内事件。在 AppsFlyer 中，此集成被称为 `googleadwords_int`，归因结果在媒体来源 `googleadwords_int` 下报告。

## Google Ads 归因流程与高级数据共享

[![Google ads attribution flow.png](https://files.readme.io/1c49e06e48658a8cb60ae6a9e9a83c0fad751766f3d4ce9c6afdd041fb5e8579-small-38644882427537.png)](https://files.readme.io/1c49e06e48658a8cb60ae6a9e9a83c0fad751766f3d4ce9c6afdd041fb5e8579-small-38644882427537.png)

1. AppsFlyer 像往常一样将安装事件发送给 Google。如果 **高级数据共享** 开启，安装将带有或不带设备 ID 发送。如果关闭，安装仅在存在设备 ID 时发送 。
2. Google 尝试通过确定性声明（ID 匹配，使用设备 ID 如果可用）或非确定性声明（当设备 ID 不可用时）来声称安装，使用概率模型。
3. 在这两种情况下，Google 向 AppsFlyer 响应一个声明——无论是确定性还是非确定性。
4. AppsFlyer 使用其自己的概率模型验证非确定性声明。仅接受经过验证的声明。
5. 验证后，Google 声明（如果被接受）进入归因决策步骤，AppsFlyer 将其与其他潜在的归因候选者（例如，其他 SRN、基于点击的网络、自然流量）进行比较。安装根据 AppsFlyer 的归因逻辑和优先规则归因于获胜来源。
6. 如果声明被接受并选为获胜候选，安装将归因于 Google。在原始数据报告中，确定性声明将显示 <Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#attribution::cecc12c5">匹配类型</Anchor> 为 `srn`，而非确定性声明将显示匹配类型为 “`probabilistic`”。

## 广告主的Google Ads归因配置指南

请按以下步骤使用AppsFlyer对Google Ads投放进行归因：

<div id="h_01HXXXXXPRECONDITIONSTEP1" />

<Accordion title="第1步：验证 ICM 前提条件">

确保满足以下要求，以支持通过 AppsFlyer 在 iOS 上的 Google PMOD 安装声明。这对于启用 Google 的设备内测量（ODM）是必要的。Android 不需要 SDK 更新。

1. [将 AppsFlyer 的 iOS SDK 更新](https://dev.appsflyer.com/hc/docs/install-ios-sdk)到**v6.17.9 或更高版本**（无需额外的 SDK 配置）。
2. 对于 Google SDK 更新，请选择以下其中之一：
   * **Google 的 Firebase iOS** SDK <strong>v11.14.0 或更高版本。</strong>有关更多信息，请参见 [Google 文档](https://github.com/firebase/firebase-ios-sdk/releases)。**或**
   * **Google ODM 独立** SDK。有关更多信息，请参见 [Firebase 文档.](https://support.google.com/google-ads/answer/16384720)。
3. 确保 <Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary#idfv">IDFV</Anchor> 在每次应用打开或应用内事件时发送到 AppsFlyer。
4. 确保在每次应用打开事件时将 IP 地址发送到 AppsFlyer。当为应用配置 IP 掩码时，ICM 可能无法正常工作。

</Accordion>

<div id="step-1-create-the-google-ads-link-id-mandatory" />

<Accordion title="第2步：创建Google Ads Link ID（必需完成）">

请注意：相关账户必须具有**Google管理员权限**才能创建Link ID。请按照以下步骤操作或 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">Google 文档</Anchor>。

1. 登入您的Google Ads管理员账户。
2. 在顶部菜单栏中点击**Tools and settings**。
3. 在**Setup**菜单下选择**Data manager**，并点击 **+ Connect Product**。
4. 在**Data sources**搜索栏中，输入“Third-party app analytics”并选择该选项，然后点击**Continue**。
5. 点击**Create link ID**。
6. 选择**AppsFlyer**作为您的应用分析服务商（app analytics provider）。
7. 选择安卓或iOS作为相关操作平台。
8. 搜索并选择您的应用。
9. 点击**Create link ID**。

</Accordion>

<div id="step-2-set-up-google-ads-on-appsflyer-mandatory" />

<Accordion title="第3步：在AppsFlyer后台设置Google Ads（必需完成）">

**（AppsFlyer帐户中的任何成员都可执行以下操作）**

1. 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。
2. 搜索并选择**Google Ads**。
3. 点击**设置对接**，界面会跳转到对接设置页。
4. 打开**渠道对接**选项卡中的**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开（<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">即启用</Anchor>）状态<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">。</Anchor>
5. 将您在上一步流程中复制的**Link ID**粘贴到相关字段中。
6. 确定是否打开<Anchor target="_blank" href="/marketers/zh/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**非欧盟用户**</Anchor>开关。  
   <Image alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="557px" />
7. 将 **高级数据共享** 打开 或 关闭.当打开时，Google Ads 会接收带有设备级标识符的回调和事件，适用于所有设备，包括未提供其广告 ID（IDFA 或 Google 广告 ID）的设备。

   此外，启用**高级数据共享**后，AppsFlyer 会对这些事件进行归因。该功能关闭时，仅限带有IDFA的设备所产生的回传和事件才会得到共享和归因。
8. 配置**激活归因**：
   1. 设置**点击型激活回溯窗口期**。   
      选择归因窗口期的单位（小时或天），并将滑块滑动到所需值。我们建议将窗口期设置为30天，以便与Google Ads匹配。

      > 📘 **注意**
      >
      > 由于 Google Ads 的限制，<Anchor target="_blank" href="/marketers/zh/docs/about-enriched-engagement-types#engaged_view">参与的观看次数</Anchor>和 <Anchor target="_blank" href="/marketers/zh/docs/about-enriched-engagement-types#engaged_click">参与的点击次数</Anchor> 在 iOS 上报告为点击。

   2. 【可选】若投放安卓应用的预注册广告，请设置**预注册广告回溯窗口期**（默认为90天）。这个滑动条用于调整预注册广告的激活归因回溯窗口期。
   3. 启用**浏览型激活归因**。

      > 📘 **注意**
      >
      > 由于 Google Ads 的限制，iOS 上不支持查看归因。

   4. 选择归因窗口期的单位（小时或天），并将滑块滑动到所需值。建议将浏览型窗口期设置为1天，以便与Google Ads的窗口期相匹配。   
      **请注意：** Google不认领iOS应用的展示，因此对于iOS应用，您无需使用浏览型激活归因开关和回溯窗口期滑动条。

      [![](https://files.readme.io/a6f05b9f92abf6dfdbaafc248c0381bfe063086daa10727dc088d484c1b38f0b-30759221879825.png)](https://files.readme.io/a6f05b9f92abf6dfdbaafc248c0381bfe063086daa10727dc088d484c1b38f0b-30759221879825.png)
9. **重新安装归因** 切换默认情况下为新集成开启。重新安装归因让您可以衡量在重新归因窗口期间重新安装您应用的用户。

   不需要单独的回顾窗口配置，因为重新安装归因使用您安装归因设置中的值。有关更多信息，请参见 <Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls">衡量重新安装</Anchor>。

   > 🚧 **重要提示！**
   >
   > 重装激活的转化数据在Google Ads控制面板上**记录为session\_start** ，而AppsFlyer则会对其归因并在面板上将其记录为再归因。

10. 配置**再互动归因**：
    1. <Anchor target="_blank" href="/marketers/zh/docs/app-settings#reengagement-attribution">在应用配置页面启用再营销</Anchor>。
    2. 在Google Ads的对接设置中启用再互动归因
    3. 设置**再互动点击回溯窗口期**。用户点击广告后在该窗口期内打开应用时，AF会将其记录为再互动。选择归因窗口期的单位（小时或天），并将滑块滑动到所需值。
    4. 启用**浏览型再互动归因**。  
       **请注意：** Google不认领iOS应用的展示，因此对于iOS应用，您无需使用浏览型激活归因开关和回溯窗口期滑动条。
    5. 设置**浏览型再互动窗口期**。用户浏览广告后在该窗口期内打开应用时，AF会将其记录为再互动。选择归因窗口期的单位（小时或天），并将滑块滑动到所需值。
    6. 设置 **再互动窗口期**。用户点击或浏览广告后在该窗口期内完成的应用内事件会被归因到再营销渠道。这个值可以设置为数天（1-90天）、数小时（至多23小时）或用户的整个生命周期。默认值为30天。  
       [![](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)
11. 如果拥有 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2402582?hl=en">Google Ads iOS 应用资源</Anchor>（即此前的应用扩展）：  
    如需通过广告链接获取归因信息，请在<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">**归因链接**</Anchor>选项卡中创建一个单平台的AppsFlyer归因链接，然后将其添加到该Google Ads扩展程序中。  
    **请注意：** 请务必添加一个静态的广告系列名称（必须配置）。  
    [![](https://files.readme.io/6b7513829fb3abbaab75942e3612760f39f6ae6502064eac1f31b0783a63e95b-30759221884561.png)](https://files.readme.io/6b7513829fb3abbaab75942e3612760f39f6ae6502064eac1f31b0783a63e95b-30759221884561.png)
12. 进入**成本**选项卡。
13. 打开**获取成本、点击和展示数据**开关。
14. 点击**Connect Google Ads**按钮并登录到您的Google帐户，这样您就能在AppsFlyer上查看所有的Google Ads投放成本了。 更多详情, 请<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-cost-and-ad-revenue">点击此处</Anchor>
15. 点击**保存**。

> ❗️ **重要提示！**
>
> * 如需在Google Ads中查看AppsFlyer归因到的激活和再互动数据，必须导入以下AppsFlyer事件：
>   * “First open”（首次打开，用于激活）
>   * “Session start”（会话开始，用于再互动）
> * 只有在[完成第4步](#step-4-measure-your-app-conversions-mandatory)之后，您才能在AppsFlyer后台看到Google Ads激活。如果您还需要将应用内事件映射到Google Ads，请先完成[第3步](#step-3-map-your-inapp-events-recommended)。

</Accordion>

<div id="step-4-measure-your-app-conversions-mandatory" />

<Accordion title="第4步：导入应用转化（必须完成）">

> 🚧 **重要提示！**
>
> 您必须打开应用并触发需要映射的应用内事件，才能让**Google Ads**记录新增的转化。如需测试iOS应用，则必须收集IDFA才能看到该事件。添加事件转化后最多需等待6小时才能生效。添加完毕后，您就可以导入这些事件。导入后，新增转化的状态就会从“No recent conversion”（最近无转化）变为“recording conversion”（正在记录转化）。

请注意：相关账户必须具有**Google管理员权限**才能创建Link ID，从而完成此步骤。

请根据<Anchor target="_blank" href="https://support.google.com/google-ads/answer/7382633?sjid=11699141105296914680-EU">Google Ads提供的说明文档</Anchor>完成相关操作。在此过程中请注意以下事项：

* 将 **first\_open** 事件设置为所有应用的转化事件（安装测量所需）。
* 如果您计划测量与 Google 的重新参与，请将 **session\_start** 事件设置为转化事件。
* 对您希望与 Google 测量的每个应用内事件重复此过程。

  > 📘 **注意**
  >
  > 如果Google Ads中的渠道映射事件ID（Partner Event identifier）发生了变更，或被标记为自定义（CUSTOM），这时即使对应的事件在AppsFlyer中也做了相应的更改，您仍需要重新导入相关数据。

* 完成相关流程后，进入**Conversions** > **Summary**页面时您就能看到第三方转化事件。如果您需要的事件未出现在列表中，或者该事件已从Google Ads的转化列表中移除，请按以下方式操作：
  1. 点击**View all conversion actions**（查看所有转化行为）。此时界面会显示Status状态筛选条件。
  2. 点击**Status**并选择**All**查看所有事件，包括已停用或删除的事件。
* 请确保“include in conversions”的设置与您的Google Ads投放目标（campaign goals）一致。详情请咨询您的Google账户经理或参阅<Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">此处的Google文档</Anchor>。

完成上述操作后，您就能通过AppsFlyer来衡量Google Ads移动广告了。

</Accordion>

<div id="step-3-map-your-inapp-events-recommended" />

<Accordion title="第5步：映射应用内事件（推荐）">

**（AppsFlyer帐户中的任何成员）**

[![In-app_event_postbacks_en-us.png](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)

1. 进入**对接**选项卡，向下滚动到**应用内事件回传**部分。

   > 📘 **注意**
   >
   > 启用某个应用的Google Ads应用内事件映射时：
   >
   > * **af\_app\_opened**会自动定义并映射到**session\_start**（如未自动映射，请手动添加）。
   > * 请务必在**事件来源**菜单中选择**所有媒体渠道，包括自然流量**，这样Google Ads才能收到这些事件。您可以在对接设置完成后根据实际情况更改事件来源选项。

2. 打开**应用内事件回传**开关。
3. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。
4. 请配置以下参数：

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。<br />**提示**：如果下拉菜单中没有您要查看的事件：<ul><li>请确保以非自然方式激活应用，并完成该事件，然后再次检查该事件是否在列表中。</li><li>在**AppsFlyer事件**中输入该事件的名称，然后点击**创建自定义事件**。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">自定义事件映射</Anchor>。</li></ul> |
| **渠道映射事件** | Google Ads为每个事件定义的专属名称或ID。从下拉菜单中选择最贴合您业务需求的AppsFlyer预定义事件。 |
| **事件来源** | 选择事件回传的范围：<ul><li>**仅该合作渠道**：仅回传归因到Google Ads的事件。</li><li>所有媒体渠道，包括自然流量回传所有带量渠道以及自然量的事件。</li></ul> |
| **回传内容** | <ul><li>**无数据（默认）**：仅发送事件本身，不带任何事件值。</li><li>**发送值与收入**：发送所有事件参数，**包括**收入（若有）。</li><li>**仅发送值**：发送**除**收入以外的所有参数。</li></ul> |

5. 点击**保存对接**。
6. 您可以在保存对接后留在配置页面，将其他应用也对接到该渠道。
   1. 点击页面左上角渠道名称下方的应用名称，打开应用列表。
   2. 在下拉菜单中选择一个其他应用。
   3. 为选定应用完成对接设置。

</Accordion>

> 👍 **提示**
>
> Google Ads API对接默认包含Google Ads再营销功能，因此您在完成该对接并向Google Ads发送事件后，就可以直接在Google Ads中创建再营销受众列表，而无需再进行任何其他对接。

## 如何为Google Ads团队成员开放权限

您可以向Google Ads<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">开放您帐户中某些数据的访问权限</Anchor>，只需在Google Ads配置页面的授权选项卡中完成相应操作即可。

您的Google Ads服务代表必须是AppsFlyer中Google Ads渠道账户下的团队成员，否则无法获得权限并访问您的应用。

受Google的隐私要求限制，Google只有在广告主提出明确要求时才能在其AppsFlyer渠道帐户中添加新的团队成员。

请按以下步骤为Google Ads团队成员开放应用访问权限：

1. 填写并提交<Anchor target="_blank" href="https://docs.google.com/forms/d/e/1FAIpQLSfJmwEPxy4bXw0mEsKfJ3D5dZmRZgHS3LCiyoEFsZRos0jWIQ/viewform">此表格</Anchor>，申请将您的Google账户经理添加到AppsFlyer的Google渠道帐户中。
2. 等待Google Ads确认已添加您的GA账户经理。
3. 进入**配置** > **活跃对接** > **Google Ads** > **授权**，并将您客户经理的邮箱地址添加到团队成员列表中。
4. 激活您要授予Google Ads账户经理的权限。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">如何为广告平台授权</Anchor> 。

## 代理如何启用Google Ads归因

AppsFlyer支持Google Ads的代理配置，但广告主和代理必须各自有单独的Google Ads帐户，这样AppsFlyer才能对数据进行正确的归因。有关详细信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-agencies">Google Ads 集成的代理配置</Anchor>。

## 多个Google Ads帐号同时投放

如果您同时使用多个Google Ads帐户推广同一个应用，AppsFlyer也能衡量其投放效果。您只需要在Google Ads中共享Link ID并将事件导入各个Google Ads帐户中即可。

有关更多详细信息，请参阅<Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001">Google 文档，了解如何共享您的 Google Ads 链接 ID</Anchor> 。

## iOS应用广告

**请注意**：本章节内容仅适用于以激活（installs）为目标的的应用广告，**不适用于**互动（engagement）。

2021年1月27日，<Anchor target="_blank" href="https://blog.google/products/ads-commerce/preparing-developers-and-advertisers-for-policy-updates/">Google出台新政策</Anchor>，以顺应iOS 14的要求。

ATT实行后，由于Google iOS应用不使用ATT弹窗，因此Google Ads产品也就<Anchor target="_blank" href="https://support.google.com/google-ads/answer/10417364">不再使用ATT</Anchor>框架下的设备标识符IDFA（YouTube应用除外，该应用支持ATT弹窗）。

为了实现针对iOS 14+流量的报告和投放优化，Google扩展了其模型转化功能。

由于模型转化是不需要设备ID的，因此在iOS 14.5上线后，Google的iOS激活广告库存逻辑如下：

* iOS ACI 搜索库存不按设备 ID 归因。这遵循 Google 于 2020 年 1 月 24 日的政策。
* 当设备 ID 存在时，iOS ACI 展示库存可以归因，前提是广告主应用和发布者应用均已获得用户同意。
* 任何 iOS ACI 活动都可以通过 ICM 进行归因。当设备 ID 在广告商应用、发布者应用或两者中都不可用时适用。
* 谷歌目前仅声称 iOS 上的点击。它不声称展示次数。

## 在应用广告中使用延迟深度链接

**深度链接的含义和作用原理**

潜在用户点击信息流广告后会跳转到应用页面。用户安装并打开该应用后，SDK会通过延迟深度链接提供具体的产品信息。应用开发人员可以使用这个数据将用户带入应用中的相关体验。

**Google中的延迟深度链接**

您可以利用<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9959794?hl=en&ref_topic=10011599">Google应用广告系列中的广告Feed</Anchor>或<Anchor target="_blank" href="https://support.google.com/google-ads/answer/12373847?">广告组的延迟深度链接</Anchor>为移动端的新增用户打造一个丝滑的使用体验，为其呈现定制化内容。Google支持广告Feed或广告组中的深度链接。在这两种场景中，AppsFlyer都支持延迟深度链接。

**请按以下步骤在Google Ads中启用延迟深度链接：**

1. 如需从AppsFlyer SDK侧拉取`af_dp`参数，请务必使用<Anchor target="_blank" href="/marketers/zh/docs/conversion-data-payloads-and-scenarios#延迟深度链接带来的再归因">GCD</Anchor>。
2. 进入Google后台，设置<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9958973?hl=en&ref_topic=10011599">Feeds</Anchor>或<Anchor target="_blank" href="https://support.google.com/google-ads/answer/12373847?">广告组级别的延迟深度链接</Anchor>。
3. 从AppsFlyer后台进入**配置** > **活跃对接**。 选择**Google Ads (Adwords)**。
4. 在**对接**选项卡中，启用**Google Ads的延迟深度链接**。
5. 点击**保存对接**。

## Google Ads参数映射

下表说明了Google Ads和AppsFlyer之间的参数映射关系。请注意：广告主无法在Google Ads广告中添加自定义参数。

| **平台类型** | **搜索** | **展示** | **YouTube** |
| --- | --- | --- | --- |
| 渠道 | [`Channel`（流量入口）参数的填充方式](/docs/google-ads-adwords-integration-setup-for-advertisers#google-ads参数映射)请见下表 |  |  |
| 广告系列 | 是 | 是 | 是 |
| 广告系列ID | 是 | 是 | 是 |
| Adset  <br />由 `ad_group_name` 参数填充。  <br />如果该参数为空，AF 将 `af_adset` 填充为 `ad_group_id`。 | 是 | 是 | 是 |
| 广告组 ID (`af_adset_id`) 由谷歌 `ad_group_id` 参数填充。 | 是 | 是 | 是 |
| Ad | 不适用 | 不适用 | 不适用 |
| 广告 ID  <br />由谷歌的 `creative_id` 参数填充。 | 是 | 是 | 是 |
| Ad type | 是* | 是* | 是* |
| 子渠道ID | GoogleSearch/  <br />SearchPartners | 不适用 | YouTubeVideos/  <br />VideoPartners |
| Keywords | 不适用 | 不适用 | 不适用 |

`Channel`（流量入口）参数的填充方式

Google Ads不发送`Channel(af_channel)`参数。AppsFlyer会按Google Ads侧的广告系列类型，根据以下规则判断如何填充该参数：

<table><thead><tr><th colspan="2">广告系列类型<strong>和</strong>平台类型逻辑：</th><th rowspan="2"> <kbd>Channel</kbd>参数</th><th rowspan="2">示例</th></tr><tr><th>campaign_type</th><th>network_type</th></tr></thead><tbody><tr><td> <kbd>ACI</kbd>、<kbd>ACE</kbd>、<kbd>ACPRE</kbd>、<kbd>Shopping</kbd>或<kbd>Hotel</kbd> </td><td>所有平台类型</td><td><kbd>campaign_type_network_type</kbd></td><td>channel = <kbd>ACI_Search</kbd> </td></tr><tr><td><p><strong>若非</strong></p><p><kbd>ACI</kbd>、<kbd>ACE</kbd>、<kbd>ACPRE</kbd>、<kbd>Shopping</kbd>或<kbd>Hotel</kbd></p></td><td><kbd>展示</kbd></td><td><kbd>network_subtype</kbd></td><td>channel = <kbd>mGDN</kbd> </td></tr><tr><td><p><strong>若非</strong></p><p><kbd>ACI</kbd>、<kbd>ACE</kbd>、<kbd>ACPRE</kbd>、<kbd>Shopping</kbd>或<kbd>Hotel</kbd></p></td><td><p><strong>若非</strong></p><p><kbd>展示</kbd></p></td><td><kbd>network_type</kbd></td><td>channel = <kbd>Search</kbd> </td></tr></tbody></table>

有关 Google 响应中可用的广告类型的更多信息，请参阅<Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">Google 请求和响应规范</Anchor>。

> 📘 **注意**
>
> 当谷歌通过概率归因 (ICM) 归因安装时，谷歌不会与 AppsFlyer 分享 `network_type`。因此，网络类型缺失，渠道值为 `ACI_`（没有后缀）。

### 广告系列类型：应用广告系列

#### Google Ads的广告系列名称变更

| 到2021年2月15日为止 | 从2021年2月23日开始 |
| --- | --- |
| UAC | ACI |
| UACE | ACE |
| UACPre | ACPRE |

**请注意：** 广告系列名称类型取决于点击或展示日期而非激活日期。

### 原始数据报告中的engaged view参数

Engaged view（深度观看）是指用户观看时间超过10秒的视频广告展示，它的归因优先级与点击相同。 在Android设备上，“深度观看”会在原始数据报表中`Engagement Type`和`Sub Param 5`参数下显示为`engaged_view`。   
当“深度观看”发生在 AppsFlyer 中定义的点击回溯窗口期内（最长为 3 天），就会被计入归因。

> 🚧 **重要提示！**
>
> * 谷歌是一个SRN (自归因渠道)。有关这些网络归因流程如何运作的更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">自我报告网络 (SRN)</Anchor> 。
> * 也就是说，AppsFlyer可以呈现Google提供的所有投放信息。广告类型（搜索、视频、展示）和相关信息取决于Google。更多信息，请参阅<Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">Google 请求和响应规范</Anchor>。

## 没有设备ID时如何优化Google Ads投放

iOS14.5+和Android 12+上线后，Google Ads推出了多种新的标识符，以便在没有设备ID的情况下进行确定性归因：

| 标识符 | 上线日期 | 数据来源 | 操作系统 | 用于 | 数据颗粒度 |
| --- | --- | --- | --- | --- | --- |
| gclid | 2021年12月 | Google Play Referrer | 安卓 | 安装/重新安装 | 用户层级数据 |
| gclid | 2021年12月 | 深度链接URL | 安卓 + iOS | 再互动 | 用户层级数据 |
| gbraid | 2021年3月 | 深度链接URL | iOS | 再互动 | 汇总 |
| odm\_info | 2017 年 11 月 | AppsFlyer SDK / S2S | iOS | 安装/重新安装 | 汇总 |

在谷歌广告和 AppsFlyer 中，广告商可以接收没有设备 ID 的流量的活动级数据，用于重新参与、安装和重新归因活动。然而，谷歌不共享广告组和广告级数据。  
**这个环节无需广告主进行任何操作。**

### 分操作系统的数据可用性

**安卓应用：**

对于没有设备ID的流量，广告主可在AppsFlyer和Google Ads后台看到完整的拉新和再营销投放数据。

**iOS应用**

对于没有设备ID的流量，广告主可以在Google Ads和AppsFlyer后台看到完整的再营销投放数据。

## 没有 Firebase SDK 的广告

在未实现 Firebase SDK 的情况下使用 Google Ads 广告时，适用以下限制。

| 局限性 | 说明 |
| --- | --- |
| 不支持 tROAS | tROAS（目标广告支出回报）优化仅在使用 Firebase SDK 收入事件时可用。AppsFlyer 收入事件以及来自所有其他 MMP 的事件不符合此优化的资格。 |
| 不支持受众排除 | 广告主只能在广告活动针对 Firebase SDK 事件优化时排除用户，而不是 MMP 事件。 |

## 谷歌概率归因 (ICM) 特征和限制

| 局限性 | 说明 |
| --- | --- |
| 归因范围 | 仅支持 **安装和重新归因**；不支持 **重新参与**。 |
| 包含的声明数据 | 谷歌声明包括：<ul><li>**广告系列名称**</li><li>**广告系列ID**</li></ul>不包括**广告组**或**广告信息。** |
| 渠道字段 | 未提供网络类型或子类型；**渠道**字段将包含部分值：`ACI_`  <br />有关“渠道”逻辑的更多信息，请参见[如何填充`渠道`参数](/docs/google-ads-adwords-integration-setup-for-advertisers#google-ads参数映射)。 |
| iOS ODM区域支持 | **在欧盟、英国和瑞士不支持** |
| 聚合高级隐私（AAP） | 当\{iOS应用设置中的<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework">AAP</Anchor>（聚合高级隐私）开关被设置为**开启**时，原始数据报告中的谷歌归因数据将显示为受限。要查看谷歌未同意的数据，请确保AAP开关为**关闭**。 |
| Attributed touch time | 谷歌概率声明的时间戳四舍五入到15分钟的间隔（00:00，00:15，00:30等） |
| 掩盖IP | 使用 IP 地址掩码可能会影响 ICM 性能。谷歌建议禁用 IP 地址掩码，因为它可能会影响谷歌广告的衡量和效果。请参阅<Anchor target="_blank" href="/marketers/zh/docs/apply-ip-masking-to-user-data#掩盖ip">“将 IP 地址掩码应用于用户数据”</Anchor> 。 |
| IDFV | Google 要求在应用安装、应用打开和应用内事件中发送<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-knowledge-base-glossary#idfv">IDFV</Anchor> （如果可用），以最大限度地提高 ICM 性能。 |

> 📄 **相关文档**
>
> * 请参考<Anchor target="_blank" href="/marketers/zh/docs/get-skan-postback-data-from-google-ads">Google Ads与AppsFlyer的SKAN互动设置</Anchor>，了解iOS 14的相关注意事项。

<div data-zendesk-anchors="google-icm-attribution-flow-with-advanced-data-sharing=google-ads-%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B%E4%B8%8E%E9%AB%98%E7%BA%A7%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%AB h_01K0VKGRK7XXC4GNF6B9X76M4T=google-ads-%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B%E4%B8%8E%E9%AB%98%E7%BA%A7%E6%95%B0%E6%8D%AE%E5%85%B1%E4%BA%AB configuring-google-ads-attribution-for-advertisers=%E5%B9%BF%E5%91%8A%E4%B8%BB%E7%9A%84google-ads%E5%BD%92%E5%9B%A0%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97 h_01HACTC1H5MANBCRWYQPNW5CC2=%E5%B9%BF%E5%91%8A%E4%B8%BB%E7%9A%84google-ads%E5%BD%92%E5%9B%A0%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97 step-1-verify-prerequisites=h_01HXXXXXPRECONDITIONSTEP1 h_01HACTC1H5XEJEPMZ4C7GP8GG6=step-1-create-the-google-ads-link-id-mandatory h_01HACTC1H5HEP9759J2PCPPZSW=step-2-set-up-google-ads-on-appsflyer-mandatory h_01K9S9C04GHJW1C88R64V742VZ=%E6%B3%A8%E6%84%8F h_01K9S93R7E30BCCEYJA4TW2AXV=%E6%B3%A8%E6%84%8F-1 h_01HACTC1H5R995RXYRFQBFHRF1=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HACTC1H5EFJKV6AXNSTNFZA4=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 h_01HACTC1H5GV04KFM29NCCK8J2=step-4-measure-your-app-conversions-mandatory h_01HSX7TJC7PQ0ATM1J86Z4HMYJ=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2 h_01KA6S8V6CKRATXHZQZ4YN7V9R=%E6%B3%A8%E6%84%8F-2 h_01HACTC1H50DDS3WCZ9DCHKN0P=step-3-map-your-inapp-events-recommended h_01HACTC1H58WHJDBN2DRQAZKGB=%E6%B3%A8%E6%84%8F-3 h_01HACTC1H5Z3XXS1MGBS4WYJBV=%E6%8F%90%E7%A4%BA granting-permissions-to-google-ads-team-members=%E5%A6%82%E4%BD%95%E4%B8%BAgoogle-ads%E5%9B%A2%E9%98%9F%E6%88%90%E5%91%98%E5%BC%80%E6%94%BE%E6%9D%83%E9%99%90 h_01HACTC1H5PAY95M4H1A6WTSEF=%E5%A6%82%E4%BD%95%E4%B8%BAgoogle-ads%E5%9B%A2%E9%98%9F%E6%88%90%E5%91%98%E5%BC%80%E6%94%BE%E6%9D%83%E9%99%90 enabling-google-ads-attribution-for-agencies=%E4%BB%A3%E7%90%86%E5%A6%82%E4%BD%95%E5%90%AF%E7%94%A8google-ads%E5%BD%92%E5%9B%A0 h_01HACTC1H5QE93EAYYVVDQV2WC=%E4%BB%A3%E7%90%86%E5%A6%82%E4%BD%95%E5%90%AF%E7%94%A8google-ads%E5%BD%92%E5%9B%A0 running-with-multiple-google-ads-accounts=%E5%A4%9A%E4%B8%AAgoogle-ads%E5%B8%90%E5%8F%B7%E5%90%8C%E6%97%B6%E6%8A%95%E6%94%BE h_01HACTC1H5Z8B15RHQ75HVV2RP=%E5%A4%9A%E4%B8%AAgoogle-ads%E5%B8%90%E5%8F%B7%E5%90%8C%E6%97%B6%E6%8A%95%E6%94%BE ios-app-campaigns=ios%E5%BA%94%E7%94%A8%E5%B9%BF%E5%91%8A h_01HACTC1H5X567H6A8M3FWCTAN=ios%E5%BA%94%E7%94%A8%E5%B9%BF%E5%91%8A using-deferred-deep-linking-in-app-campaigns=%E5%9C%A8%E5%BA%94%E7%94%A8%E5%B9%BF%E5%91%8A%E4%B8%AD%E4%BD%BF%E7%94%A8%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01HACTC1H57HJZNAGDKSQD6MVC=%E5%9C%A8%E5%BA%94%E7%94%A8%E5%B9%BF%E5%91%8A%E4%B8%AD%E4%BD%BF%E7%94%A8%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 google-ads-parameter-mapping=google-ads%E5%8F%82%E6%95%B0%E6%98%A0%E5%B0%84 h_01HACTC1H6P1A2E160Z6GAGZZS=google-ads%E5%8F%82%E6%95%B0%E6%98%A0%E5%B0%84 how-to-populate-the-channel-parameter=google-ads%E5%8F%82%E6%95%B0%E6%98%A0%E5%B0%84 h_01HACTC1H6TPTDDFSMPQ9YVMDY=google-ads%E5%8F%82%E6%95%B0%E6%98%A0%E5%B0%84 h_01KEYE1W4VJYXYHY4FP1KN3SP9=%E6%B3%A8%E6%84%8F-4 campaign-type-app-campaigns=%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E7%B1%BB%E5%9E%8B%E5%BA%94%E7%94%A8%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 h_01HACTC1H6CEGD2E3HXHWFWBRB=%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E7%B1%BB%E5%9E%8B%E5%BA%94%E7%94%A8%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97 changes-to-campaign-names-by-google-ads=google-ads%E7%9A%84%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E5%90%8D%E7%A7%B0%E5%8F%98%E6%9B%B4 h_01HACTC1H6A028HKVXJ66MCF6M=google-ads%E7%9A%84%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E5%90%8D%E7%A7%B0%E5%8F%98%E6%9B%B4 engaged-view-parameter-in-raw-data-reports=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E4%B8%AD%E7%9A%84engaged-view%E5%8F%82%E6%95%B0 h_01HACTC1H6Q6WCTK4Z9RGV6PA4=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E4%B8%AD%E7%9A%84engaged-view%E5%8F%82%E6%95%B0 h_01HACTC1H62HC36C08ZBFZ05XS=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-3 optimize-google-ads-campaigns-for-conversions-without-device-id=%E6%B2%A1%E6%9C%89%E8%AE%BE%E5%A4%87id%E6%97%B6%E5%A6%82%E4%BD%95%E4%BC%98%E5%8C%96google-ads%E6%8A%95%E6%94%BE h_01HACTC1H6EFDVN9N89Y17HDFR=%E6%B2%A1%E6%9C%89%E8%AE%BE%E5%A4%87id%E6%97%B6%E5%A6%82%E4%BD%95%E4%BC%98%E5%8C%96google-ads%E6%8A%95%E6%94%BE data-visibility-by-operating-system=%E5%88%86%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E7%9A%84%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HACTC1H6WZNMVJK479M5KJYF=%E5%88%86%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E7%9A%84%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01_advertising-without-firebase-sdk=%E6%B2%A1%E6%9C%89-firebase-sdk-%E7%9A%84%E5%B9%BF%E5%91%8A advertising-without-the-firebase-sdk=%E6%B2%A1%E6%9C%89-firebase-sdk-%E7%9A%84%E5%B9%BF%E5%91%8A google-icm-traits-and-limitations=%E8%B0%B7%E6%AD%8C%E6%A6%82%E7%8E%87%E5%BD%92%E5%9B%A0-icm-%E7%89%B9%E5%BE%81%E5%92%8C%E9%99%90%E5%88%B6 h_01K0XMCXSS5MKY90DZWJTNVBBS=%E8%B0%B7%E6%AD%8C%E6%A6%82%E7%8E%87%E5%BD%92%E5%9B%A0-icm-%E7%89%B9%E5%BE%81%E5%92%8C%E9%99%90%E5%88%B6 h_01HDP0SBEE75MAT4A4S9E7Y7FF=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

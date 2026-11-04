---
title: 素材优化——渠道对接
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-09-14T13:52:36Z'
  edited_at: '2026-10-14T10:05:08Z'
  id: 18565403047569
  locale: zh-cn
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/zh-cn/articles/18565403047569
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 配置渠道对接后，您就能自动将所有素材数据导入素材优化面板。

![Creative integrations New.jpg](https://files.readme.io/2bfead93dbaac902956ea4379e3f360120d59e7454be354c567b2f182382ab2d-20130430776337.jpg)

<div id="about-partner-integrations" />

## 渠道对接简介

渠道对接可以将您在相关渠道上投放的广告素材持续不断地无缝导入<Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-guide">素材优化</Anchor>面板。

<div id="data-availability" />

### 数据可用性

添加渠道对接后：

* 系统会回填过去90天内的素材数据和AppsFlyer效果数据。素材优化面板一般会在24小时内呈现这些数据。
* AppsFlyer会以一天两次的频率持续从对接渠道侧拉取素材优化数据。系统会在这些数据中糅和其它AppsFlyer效果数据，并将两者进行匹配，这类效果数据包括归因、广告消耗、点击、展示、收入等等（AppsFlyer效果数据每小时更新一次）。素材优化面板综合呈现上述所有处理流程所得出数据，并且每天在**UTC+10**时更新（最近90天的所有素材数据都会更新）。

<div id="note" />

> 📘 **注意**
>
> 如需查看AppsFlyer成本数据（如ROAS），必须购买<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview">ROI360</Anchor>。

<div id="media-partner-integrations" />

## 媒体渠道对接

本章节说明了各个渠道对接的设置方式。

<div id="adikteev" />

<Accordion title="Adikteev">

**前期准备：**

* 用于对接的证书信息：
  * 邮箱地址（Adikteev用户名）
  * Adikteev密码
  * **请注意：** 您在对接Adikteev时输入的证书信息必须与您登录Adikteev面板时使用的证书一致。
* 为了确保AppsFlyer能从Adikteev拉取到所有成本数据，请确保对接素材优化的AF用户与对接<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview">ROI360</Anchor>的用户一致。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材效果对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**Adikteev**。
4. 选择您要推广的应用。
5. 输入邮箱地址和密码。
6. 点击**保存**。

**请注意：** Adikteev又名Trademob（trademob\_int）。

</Accordion>

<div id="adjoe" />

<Accordion title="Adjoe">

**前期准备：**

* 用于对接的证书信息：
  * Token  
    请让您的Adjoe账户经理为您提供该token。详见<Anchor target="_blank" href="https://drive.google.com/file/d/16zMpKbRLmTLU-plnodELGAHZVe0CuC_F/view">Adjoe相关文档</Anchor>。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**Adjoe GmbH**。
4. 选择您要推广的应用。
5. 输入相关token。
6. 点击**保存**。

</Accordion>

<div id="applovin" />

<Accordion title="AppLovin">

**前期准备：**

* 您必须具有相关应用的广告账户权限才能配置对接。**请注意**：AppLovin的身份验证必须由账户管理员完成。
* 需要一个 AppLovin **账户 ID**、**广告系列管理 API 密钥** 和 **报告 API 密钥**。您可以从您的 AppLovin Axon 仪表板获取这些信息（点击右上角的账户并选择密钥）。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：

   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。

   ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**AppLovin**。
4. 选择您要推广的应用。
5. 输入 AppLovin **账户 ID**、**活动管理 API 密钥**和**报告 API** 密钥。
6. 然后点击 **保存**。

<div id="note-1" />

> 📘 **注意**
>
> AppLovin的资产级报告API仅返回前一天的数据。它不支持历史回顾。因此，当您激活集成时，AppsFlyer 只能从激活之日起开始收集资产级数据。因此，完整的数据覆盖范围逐渐增强，通常在激活后 30 天内完成。

</Accordion>

<div id="google-ads" />

<Accordion title="Google Ads">

**前期准备：**

* 您必须具有相关应用的广告账户管理员权限才能配置对接。
* 为了确保AppsFlyer能从Google拉取到所有素材数据，请确保对接素材优化的AF用户与对接<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview">ROI360</Anchor>的用户一致。如果您的套餐中没有ROI360，您必须具备所有相关应用以及Google Adwords广告账户的管理员权限才能确保Google素材数据的完整拉取。

**请注意：**

* Google Ads分用户对接，也就是说多个用户可同时具备活跃的Google Ads对接。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 点击**渠道**列表并选择**Google Ads (AdWords)**。
4. 选择您要推广的应用。
5. 点击**登录到Google**。界面会打开**通过Google登录**的窗口。
6. 完成Google登录流程并提供您的权限信息。请注意，为了确保AppsFlyer能拉取到完整的数据，您最好具备所有权限。
7. 点击**保存**。

**请注意：** 仅支持UAC（ACi、ACe和ACpre）类型的广告。对于不支持的广告类型，素材优化产品仅可提供其广告层级的数据（即没有素材层级的数据）。

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

**前期准备：**

* 用于对接ironSource的证书信息：
  * Secret Key
  * Refresh token
  * 如需了解如何获取这些证书信息，请参考<Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/ios/authentication/#step-1">此文档</Anchor>。
* 您必须在IronSource账户中具备Administrator或Contributor用户角色，才能取得这些信息。如需了解用户角色的设置方式，请参考<Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/air/user-management/#step-1">此文档</Anchor>。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**ironSource**。
4. 选择您要推广的应用。
5. 输入相关的Secret Key和Refresh Token。
6. 点击**保存**。

**请注意：** 不支持部分广告类型。对于不支持的广告类型，素材优化产品仅可提供其广告层级的数据（即没有素材层级的数据）。不适配的广告样式包括任务墙。

</Accordion>

<div id="liftoff" />

<Accordion title="Liftoff">

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**Liftoff**。
4. 选择您要推广的应用。
5. 请让您的Liftoff CSM为您提供Liftoff数据上报API的用户名和密码。
6. 点击**保存**。

</Accordion>

<div id="facebook-ads" />

<Accordion title="Meta Ads">

**前期准备：**

* 您必须具有相关应用的广告账户权限才能配置对接。**请注意**：请注意，Meta Ads分用户对接，也就是说可以有多个用户同时具备活跃对接。
* 如需拉取呈现在内部和/或外部Facebook页面上的素材数据，相关Facebook Business Center账户管理员必须为素材优化对接的设置人员开放相关权限。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**Meta Ads**。
4. 选择您要推广的应用。
5. 点击**通过Meta Ads登录**。
6. 完成登录流程并提供您的权限信息。**请注意**：为了确保AppsFlyer能拉取到完整的数据，您最好具备所有权限。
7. 点击**保存**。

**请注意：**

* 由于Meta Flexible Ads仅针对一个广告素材提供报告，因此仅显示与广告中表现最佳的素材数据。
* 不支持部分广告类型。对于不支持的广告类型，素材优化产品仅可提供其广告层级的数据（即没有素材层级的数据）。不支持的广告类型包括：目录/DPA。

</Accordion>

<div id="mintegral" />

<Accordion title="Mintegral">

**前期准备：**

* Mintegral 集成凭证：
  * API key
  * 访问密钥
  * 如需了解如何获取这些证书信息，请参考<Anchor target="_blank" href="https://adv-new.mintegral.com/doc/en/guide/introduction/register.html">此文档</Anchor>。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在 **合作伙伴** 列表中，选择 **Mintegral**。
4. 选择您要推广的应用。
5. 输入 **API 密钥**和**密钥。**
6. 点击**保存**。

</Accordion>

<div id="moloco" />

<Accordion title="Moloco">

**前期准备：**

* 您的Moloco账户必须具备 <Anchor target="_blank" href="https://help.moloco.com/hc/en-us/articles/360050566173-Invite-and-manage-users">“Workplace Owner”或“Ad Account Owner”</Anchor>角色才能拉取素材数据。
* 访问您的 Moloco API 密钥。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材效果对接**部分。![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**Moloco**。
4. 选择您要推广的应用。
5. 输入您的 Moloco API 密钥。
6. 点击**保存**。

**请注意**：

* 不支持部分广告类型。对于不支持的广告类型，素材优化产品仅可提供其广告层级的数据（即没有素材层级的数据）。不支持的广告类型包括CTV广告。

</Accordion>

<div id="personaly" />

<Accordion title="Persona.l">

**前期准备：**

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. 点击 **+新对接**。
3. 在**合作伙伴**列表中，选择 **Persona.ly**。
4. 选择您要推广的应用。
5. 输入 Persona.ly **API 密钥**（从你的 Persona.ly 账户中获取）。
6. 点击**保存**。

</Accordion>

<div id="reddit" />

<Accordion title="Reddit">

**前期准备：**

* 为确保能成功拉取到素材数据，您必须具有Reddit的“Creator”或“Admin”角色。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**Reddit**。
4. 选择您要推广的应用。
5. 点击**通过Reddit登录**。
6. 完成登录流程并提供您的权限信息。**请注意**：为了确保AppsFlyer能拉取到完整的数据，您最好具备所有权限。
7. 点击**保存**。

</Accordion>

<div id="remerge" />

<Accordion title="Remerge">

**前期准备：**

* 用于对接的证书信息（**请注意**：您在对接Remerge时输入的证书信息必须与您登录Remerge面板时使用的信息一致。详见<Anchor target="_blank" href="https://help.remerge.io/hc/en-us/articles/115003440434-Remerge-Reporting-API">Remerge的文档</Anchor>）：
  * 用户邮箱地址
  * 密码

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材效果对接**部分。![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**Remerge**。
4. 选择您要推广的应用。
5. 输入邮箱地址和密码。
6. 点击**保存**。

</Accordion>

<div id="revx" />

<Accordion title="RevX">

**前期准备：**

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**Reddit**。
4. 选择您要推广的应用。
5. 输入 RevX **API 密钥**（直接联系您的 RevX 客户经理获取您的 API 密钥）。
6. 点击**保存**。

</Accordion>

<div id="smadex" />

<Accordion title="Smadex">

**前期准备：**

* 用于对接Smadex的证书信息（**请注意**：您在对接Smadex时输入的证书信息必须与您登录Smadex面板时使用的信息一致）：
  * 电子邮件
  * 密码

**请按以下方式添加对接：**

1. 登入AF后台，**进入素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材效果对接**部分。![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**Smadex**。
4. 选择您要推广的应用。
5. 输入必填的证书信息。
6. 点击**保存**。

</Accordion>

<div id="snap" />

<Accordion title="Snapchat">

**前期准备：** 您必须具有相关应用的广告账户权限才能配置对接。**请注意**：请注意，Snapchat分用户对接，也就是说可以有多个用户同时具备活跃对接。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**Snapchat**。
4. 选择您要推广的应用。
5. 点击**通过Snapchat登录**。打开配置**窗口。**
6. 完成登录流程并提供您的权限信息。请注意，为了确保AppsFlyer能拉取到完整的数据，您最好具备所有权限。
7. 点击**保存**。

**请注意：** 不支持部分广告类型。对于不支持的广告类型，素材优化产品仅可提供其广告层级的数据（即没有素材层级的数据）。不支持的广告类型包括精品栏广告（Collection Ads）。

</Accordion>

<div id="tiktok" />

<Accordion title="TikTok">

**前期准备：**

* 您必须具有相关应用的广告账户权限才能配置对接。**请注意**：TikTok分用户对接，也就是说可以有多个用户同时具备活跃对接。
* 如需从Spark Ads拉取素材数据，相关TikTok Business Center账户管理员必须为素材优化对接的设置人员开放相关权限。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**TikTok**。
4. 选择您要推广的应用。
5. 点击**通过TikTok登录**。打开配置**窗口。**
6. 完成登录流程并提供您的权限信息。请注意，为了确保AppsFlyer能拉取到完整的数据，您最好具备所有权限。
7. 点击**保存**。

<div id="notes" />

> 📘 **注意**
>
> * 2023年1月30日，我们上线了新的**TikTok for Business高级SRN**对接`tiktokglobal_int`，**TikTok for Business**的历史对接`bytedanceglobal_int`将逐步下线，到2024年3月完全停用。详情请见这篇<Anchor target="_blank" href="/marketers/zh/docs/bulletin-tiktok-for-business-advanced-srn">公告文档</Anchor>。
>   * 如果新对接（tiktokglobal\_int）启用后历史对接（bytedanceglobal\_int）仍处于活跃状态，素材优化面板会同时从新旧两个对接拉取数据，从而产生重复的效果数据。
>   * 但素材不会出现重复，这是因为AI会识别实际的素材资产（asset）。
>   * 移除历史对接时，历史数据不会从素材优化产品中删除。
>   * 如需拉取所有必要数据，进行TikTok SRN对接操作的人员必须具有相关权限（建议使用广告账户管理员权限）。
> * 不支持部分广告类型。对于不支持的广告类型，素材优化产品仅可提供其广告层级的数据（即没有素材层级的数据）。不支持的广告类型包括收藏广告和购物广告。

</Accordion>

<div id="unity-ads" />

<Accordion title="Unity Ads">

**前期准备：**

* 用于对接的Unity服务账号证书信息：
  * Key ID
  * Secret Key
  * Organization core ID

[请点击此链接查看这些证书信息的获取方式。](/docs/creative-optimization-partner-integrations#相关证书信息的获取方式说明)

* 请在Unity中选择以下Service Account（组织）角色：
  * 拉取素材请务必选择**广告API管理员**。
  * 除素材外，如需拉取Unity指标，请务必选择**Advertisers API Stats Viewer**。<Anchor target="_blank" href="https://services.docs.unity.com/statistics/#section/Migrating-from-the-previous-version-of-the-API/Query-parameters">了解详情</Anchor>

**请注意：** 如缺少相关权限，请联系Unity广告客户成功经理。

<div id="instructions-for-retrieving-the-credentials" />

#### 相关证书信息的获取方式说明

**Key ID和Secret key的获取方式如下：**

1. 登入Unity Ads。
2. 在主菜单的侧边栏中依次点击**Administration**和**Service Accounts**。
3. 点击相关服务账户（service account）。
4. 点击 **+ Add key**。  
   这样界面就会显示Key ID和Secret key。
5. 复制该**Key ID**和**Secret key**。  
   ![Unity get Key ID & Secret key image.jpg](https://files.readme.io/9c4d1b1e0e476546b8f8be3a7375c610c48db6f94344a3dbe48277a6d115f52e-20344146224401.jpg)

<Anchor target="_blank" href="https://services.docs.unity.com/advertise/v1/index.html#section/General-Information/Resource-IDs-Used-in-the-API-Calls">**Organization core ID**</Anchor>的获取方式如下：

1. 在Unity Ads后台的侧边栏中点击**Products**。
2. 点击**Grow**。  
   ![Unity Org ID step 1 cropped.jpg](https://files.readme.io/5e8d2f54f5999c58b2e2b3591ae889f5051cae4073aa6c5ef17e16da6a60131f-22859368875153.jpg)
3. 点击**Unity Ads User Acquisition**。  
   <Image alt="Unity Org ID step 2 cropped.jpg" src="https://files.readme.io/07a1c8e878a9ed7b6832012b3261866477b825d3b23e4973b8c5dadd675973e2-22859368883473.jpg" width="347px" />
4. 点击**Settings**。  
   ![Get Organization core ID instructions 2 arrows.jpg](https://files.readme.io/aff97bcb1c255771fc46483d8d94a2f13c7ef26c45a7fc884b1c03c83da91ae5-20344868139153.jpg)
5. 复制该**Organization core ID**。

<div id="to-select-a-service-account-organization-role" />

#### **请按以下方式选择Service Account组织角色：**

1. 在Unity面板中点击**Administration**。  
   **<Image alt="Org roles step 1.jpg" src="https://files.readme.io/b9a9258cf324cdf0c73ab9be8d1646c43d2211d23cebafa3624582e6e964851f-20347001525777.jpg" width="372px" />**
2. 点击**Service accounts**。
3. 点击相关服务账户（service account），然后点击 **+ Manage organization roles**。  
   **![Org roles step 2.jpg](https://files.readme.io/f72334c392a89084c22fc6c6d97cedb051b4a53de9bad1eb3722c2e0f31852de-20347023191697.jpg)**
4. 在**Growth**下拉菜单中，选择以下服务账号组织角色（Service Account Organization Role）：
   * Advertisers API Stats Viewer，用于拉取Unity指标。
   * 以下任一角色，用于拉取素材信息：
     * Advertise API Admin
     * Advertise API Viewer
     * Advertise API Creative Packs Editor  
       <Image alt="Org roles step 3 without role names.jpg" src="https://files.readme.io/7b46417e6389f7c3675cc6f72b33e9b2833d5c561ef1d79122ed24605533b265-20347535827217.jpg" width="471px" />
5. 点击**Save**。

**请注意：** 如果您没有这些角色的访问权限，请联系您的Unity客户成功经理或发送邮件至[unityads-support@unity3d.com](mailto:unityads-support@unity3d.com)让Unity侧开放必要权限。

<div id="to-add-a-unity-integration-to-the-creative-dashboard" />

#### **请按以下方式在素材面板中添加Unity对接：**

1. 在**素材优化**面板中完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**Unity Ads**。
4. 选择您要推广的应用。
5. 输入相关Key ID、Secret Key以及Organization Core ID。
6. 输入<Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-guide#partner-metrics::e592ecd3">渠道指标</Anchor>信息，获取Unity Ads上报的指标数据（可选）。
7. 点击**保存**。

</Accordion>

<div id="x-ads" />

<Accordion title="X Ads（前身为Twitter Ads）">

**前期准备：**

* 为确保能成功拉取到素材数据，您必须具有X Ads账号的“Account admin”或“Ad manager”角色。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**X Ads**。
4. 选择您要推广的应用。
5. 点击**通过X Ads登录**。
6. 完成登录流程并提供您的权限信息。**请注意**：为了确保AppsFlyer能拉取到完整的数据，您最好具备所有权限。
7. 点击**保存**。

</Accordion>

<div id="youappi" />

<Accordion title="YouAppi">

**前期准备：**

用于对接YouAppi的证书信息：

* Token  
  **请注意**：您可以让您的YouAppi账户经理为您提供该token信息。详情请见<Anchor target="_blank" href="https://support.youappi.com/knowledgebase/reporting-api-for-re-engagement/">YouAppi说明文档</Anchor>。

**请按以下方式添加对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入**素材对接**部分。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. 点击 **+新对接**。
3. 在**渠道**列表中选择**YouAppi**。
4. 选择您要推广的应用。
5. 输入相关token。
6. 点击**保存**。

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="creative-integrations-dashboard" />

<Accordion title="素材对接面板">

您可以在素材对接面板中添加新的渠道对接。如需添加新对接，请按[分渠道说明](/docs/creative-optimization-partner-integrations#数据可用性)完成相应操作。

添加完毕后，面板会显示您当前所有对接的状态，并在以下各列中呈现其他相关信息：

| 栏位 | 说明 |
| --- | --- |
| 适用渠道 | 对接渠道的名称，如Meta Ads或ironsource\_int。展开渠道一栏后，您可以看到该渠道的所有连接，比如相关账号下的各个用户可能都有自己的连接。 |
| 应用 | 各对接渠道下分用户连接的应用列表。 |
| 对接更新 | 相关渠道的对接设置最近一次更新的日期。 |
| 素材数据覆盖级别 | 素材优化面板和报告中来自此渠道对接的素材效果数据量：<ul><li>**低**：此对接中的所有应用都有数据缺失。</li><li>**不完整**：此对接中的部分应用有数据缺失。</li><li>**高**：此对接中的所有应用均有数据。</li><li>**处理中**：数据覆盖级别会在24小时内更新。</li><li>**无数据**：该对接在过去30天内没有数据。</li></ul>点击数据覆盖级别后，界面会弹出窗口，列出分应用的数据覆盖级别。分应用的数据覆盖级别在不同情况下含义有所区别，具体取决于您是否购买了ROI360。<br /><br />**若未购买ROI360：**<ul><li>**高**：该应用有大量可用数据。具体是指对于最近30天内发生的应用激活（以AppsFlyer上报的激活量为准），AppsFlyer所拉取到的素材信息可覆盖超过85%的数据。</li><li>**低**：该应用有数据缺失。具体是指对于最近30天内发生的应用激活（以AppsFlyer上报的激活量为准），AppsFlyer所拉取到的素材信息可覆盖不到85%的数据。</li></ul>**若已购买ROI360：**<ul><li>**高**：对于最近30天内由AppsFlyer ROI360记录到的数据，AF拉取到的素材覆盖了超过85%的成本。</li><li>**低**：对于最近30天内由AppsFlyer ROI360记录到的数据，AF拉取到的素材覆盖了不到85%的成本。<br />**示例**:<ul><li>AppsFlyer从“渠道A”获取数据，总广告支出为$100。</li><li>素材1的广告支出为$85，素材2的广告支出为$15。</li><li>如果AppsFlyer拉取素材1的数据，则覆盖85%的成本，因此被视为“高”覆盖率。</li><li>如果AppsFlyer仅拉取素材2的数据，则仅覆盖15%的成本，因此被视为“低”覆盖率。</li></ul></li></ul>**无论是否购买了ROI360：**<ul><li>**处理中**：数据覆盖级别会在24小时内更新。</li><li>**低**：请按[分渠道的对接说明](/docs/creative-optimization-partner-integrations#数据可用性)，检查该渠道对接是否设置正确。</li><li>**无数据**：该应用在过去30天内没有数据。<ul><li>请检查您是否已完成AppsFlyer通用设置，以及各项配置是否正常生效（不仅针对素材优化）。</li><li>请确保您的应用处于正常使用状态，且有流量产生。<br />如果相关对接由代理托管，请按照[代理专用的对接配置指南](/docs/creative-optimization-partner-integrations#agencies)，确保该对接的设置正确无误。</li></ul></li></ul> |

</Accordion>

<div id="agencies" />

<Accordion title="代理对接">

<div id="add-an-agency-integration" />

#### 请按以下方式添加代理对接：

您可以与您的合作代理对接，将代理侧的数据拉取到素材面板。

**请按以下方式添加代理对接：**

1. 登入AF后台，进入**素材优化**面板，并根据实际情况完成以下任一操作：
   * 如果您尚未配置任何渠道对接，请点击 + **添加新对接**。
   * 否则请点击面板右上方的⋮图标，进入素材效果对接部分。  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. 点击 **+新对接**。
3. 在渠道对接窗口中选择相关的渠道和应用，然后打开**代理**开关。在代理 下拉菜单中，选择相关代理。  

   <Image alt="创意代理.png" src="https://files.readme.io/74f0dc492bc530278687becdd0061e9c06081653b69ed525f237b97a9568e413-38395601553169.png" width="288px" />
4. 点击**保存**。  
   完成上述步骤后代理对接即已添加完毕。

**请注意：**

* 如果您想要在素材面板中查看某个代理的素材数据，必须单独创建一个渠道对接，并打开其中的“代理”开关。
* 仅数据透明的代理有可用数据。<Anchor target="_blank" href="/marketers/zh/docs/view-agency-data">了解详情</Anchor>
* 素材数据仅从相关代理侧拉取。以上图为例，假设您选择了Google Ads作为合作代理，但您同时又在Google Ads上直接投放广告，这时您就需要为Google Ads单独再创建一个对接。

<div id="grant-dashboard-access-to-an-agency" />

#### 授予代理访问仪表板的权限

如果他们拥有 AppsFlyer <Anchor target="_blank" href="/partners/zh/docs/about-agency-accounts">代理账户</Anchor>，您可以授予您的代理访问查看他们自己的创意表现数据的权限。这可以增强透明度和协作。

**启用访问：**

1. 从 AppsFlyer 侧边菜单中，点击 **协作** > **合作伙伴市场**  

   **<Image alt="从 “协作” 中单击 “合作伙伴 Marketplace.png”" src="https://files.readme.io/96485cefae79412a680915810c16b23619f73d9109212bfc45d1c0d42c2e529a-39258887136785.png" width="33.9%" />**
2. 从页面顶部的搜索栏中搜索相关的合作伙伴代理，然后点击该合作伙伴。

   <Image alt="Search bar.png" src="https://files.readme.io/f1ff34a547af45eec73e7abd41105bbab9ff12d4a2636ed4b99634985ec58044-39258887138449.png" width="1210px" />
3. 在合作伙伴页面上，转到**权限**选项卡并启用**代理权限**

   agency\_permissions.png
4. 然后启用 **访问创意优化仪表板**   

   该机构现在可以在其仪表板中查看您共享的创意。对于尚未设置 AppsFlyer 代理账户并希望设置的代理，他们可以在 <Anchor target="_blank" href="/partners/zh/docs/getting-started-agency-onboarding">这里了解更多。</Anchor>

</Accordion>

<div id="update-credentials" />

<Accordion title="更新证书信息">

相关的渠道对接设置完毕后，就无法更改其账户级别的证书信息（Meta ads、Google Ads、TikTok和AppLovin除外）。如果您需要更新某个渠道的证书信息，请按以下说明操作。

1. 在**素材对接**页面中找到需要更新的渠道，并点击该渠道左边的展开图标，打开渠道连接列表。
2. 找到需要更新的渠道连接，并点击其右侧的<Image alt="3 dots icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="7px" />菜单图标，然后选择**删除对接**。![partner-integration-side-menu.png](https://files.readme.io/43ba588af05ffb8dafa165cf5d760010d36bd8b6409f6f9f4ef131d695989ed2-18565371542033.png)
3. 使用最新的证书信息为该渠道创建一个新对接。

</Accordion>

<div data-zendesk-anchors="about-creative-partner-integrations=%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5%E7%AE%80%E4%BB%8B h_01HAP6JQEFKAFK96WDBN0MERB6=%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5%E7%AE%80%E4%BB%8B media-partner-integrations=%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HEQ2QR21MZB57S6MQ5ZWZ7ZQ=%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01K4M4JF53A3J1R5VACNVN4X8A=%E6%B3%A8%E6%84%8F h_01HC7W736NDRRAJ95Z28JS2J46=%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E5%AF%B9%E6%8E%A5 h_01HBAZ8724YYFVQWYV5F8F4F5S=adikteev 01H7SZ8RA055S4M11TTX1J0E55=adjoe 01H7SZ8RA0A52YQEMYX0GV44AB=applovin h_01KY4CAH2MKX650JS1R0N8X6B4=%E6%B3%A8%E6%84%8F-1 01H7SZ8RA0980TH09EP2ED9WSF=google-ads 01H7SZ8RA0DRWC76119ED96KHP=ironsource 01H7SZ8RA0428ZPRYD99GWRMK0=liftoff 01H7SZ8RA06V5BR4ABV0ZVK82Z=facebook-ads h_01JXCRAESXDAHGGJ71EB32NAPD=mintegral 01H7SZ8RA06G1W04NSEHSPSV2D=moloco h_01KRGPVZH0Z0DHEEJNP4ST5CD9=personaly 01J9V2ZJR6KYJERPR2Y2XNCREP=reddit 01H7SZ8RA0CDR1M5V2F177TG84=remerge h_01KRGPVZH00WKJ4VJN8QHAW3YS=revx h_01HZEP4F6M2W5HC76WVFP5Z5C0=smadex 01H7SZ8RA1H0Q47N1W3NST4PZW=snap 01H7SZ8RA1E221TK8VRWEF1FA4=tiktok 01H8VVCC8GW5AZ3M475XFZY9JW=%E6%B3%A8%E6%84%8F-2 01H7SZ8RA1YTA3MGVJMXVTP78Y=unity-ads instructions-for-retrieving-the-credentials=%E7%9B%B8%E5%85%B3%E8%AF%81%E4%B9%A6%E4%BF%A1%E6%81%AF%E7%9A%84%E8%8E%B7%E5%8F%96%E6%96%B9%E5%BC%8F%E8%AF%B4%E6%98%8E h_01GT6Z998RCBQWKDC9YGPJQGN6=%E7%9B%B8%E5%85%B3%E8%AF%81%E4%B9%A6%E4%BF%A1%E6%81%AF%E7%9A%84%E8%8E%B7%E5%8F%96%E6%96%B9%E5%BC%8F%E8%AF%B4%E6%98%8E to-select-a-service-account-organization-role=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%96%B9%E5%BC%8F%E9%80%89%E6%8B%A9service-account%E7%BB%84%E7%BB%87%E8%A7%92%E8%89%B2 h_01GT6ZFTGKMR18DTNVX706DH1R=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%96%B9%E5%BC%8F%E9%80%89%E6%8B%A9service-account%E7%BB%84%E7%BB%87%E8%A7%92%E8%89%B2 to-add-a-unity-connection-to-the-creative-dashboard=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%96%B9%E5%BC%8F%E5%9C%A8%E7%B4%A0%E6%9D%90%E9%9D%A2%E6%9D%BF%E4%B8%AD%E6%B7%BB%E5%8A%A0unity%E5%AF%B9%E6%8E%A5 h_01GT6ZS52ZWY47BCT2NJVCFFEP=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%96%B9%E5%BC%8F%E5%9C%A8%E7%B4%A0%E6%9D%90%E9%9D%A2%E6%9D%BF%E4%B8%AD%E6%B7%BB%E5%8A%A0unity%E5%AF%B9%E6%8E%A5 01J9V2ZJSKN37WSGKA6D12MYBH=x-ads 01H7SZ8RA1E37649AAH1DNRXA9=youappi agency-integrations=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HC7WCZ143S29PGTVNFEX962Y=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01J9WK9A78RP6BKX6860MAABFM=creative-integrations-dashboard h_01HC7WCE9EJK3NDJQE88RZ3T0Z=agencies add-an-agency-integration=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%96%B9%E5%BC%8F%E6%B7%BB%E5%8A%A0%E4%BB%A3%E7%90%86%E5%AF%B9%E6%8E%A5 h_01K5PE1K1G75KEF9HXMAW9YP2F=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%96%B9%E5%BC%8F%E6%B7%BB%E5%8A%A0%E4%BB%A3%E7%90%86%E5%AF%B9%E6%8E%A5 grant-dashboard-access=%E6%8E%88%E4%BA%88%E4%BB%A3%E7%90%86%E8%AE%BF%E9%97%AE%E4%BB%AA%E8%A1%A8%E6%9D%BF%E7%9A%84%E6%9D%83%E9%99%90 h_01K5PE1WK5AE2MX235B8FA4YJ0=%E6%8E%88%E4%BA%88%E4%BB%A3%E7%90%86%E8%AE%BF%E9%97%AE%E4%BB%AA%E8%A1%A8%E6%9D%BF%E7%9A%84%E6%9D%83%E9%99%90 01J9WKGYM1D04ZT14EPZ13VE4P=update-credentials" />

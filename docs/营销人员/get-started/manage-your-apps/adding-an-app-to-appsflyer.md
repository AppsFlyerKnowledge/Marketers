---
title: 在 AppsFlyer 中添加应用
metadata:
  keywords:
    - Add App
    - adding an app
    - Advertisers
    - could not add app
    - security reasons
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2016-01-20T08:57:00Z'
  edited_at: '2026-11-01T10:54:54Z'
  id: 207377436
  locale: zh-cn
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/zh-cn/articles/207377436
---
> **核心要点：** 了解如何在 AppsFlyer 中添加应用，以获取安装和应用内事件的归因数据，并使用 AppsFlyer 提供的各种工具分析数据。

<div id="overview" />

## 概述

如果您尚未在 AppsFlyer 面板中添加应用，登录 AppsFlyer 后，系统会显示应用接入页面。该页面将引导您完成添加应用的所有步骤，并帮助您为归因做好准备。

<div id="entering-the-wizard-for-adding-an-app" />

### 进入添加应用向导

您可以从平台进入添加应用向导，也可以通过应用接入页面添加应用（仅适用于 Android 和 iOS 应用）。

**通过应用接入页面进入向导：**

* 在 **Add your app（添加应用）** 步骤中，点击 **Add app（添加应用）**，然后按照提示操作。

<div id="note" />

> 📘 **注意**
>
> 如果应用接入页面尚未打开，请在顶部菜单栏中点击电子邮件地址下拉菜单，然后选择 **App onboarding（应用接入）**。

<Image align="center" alt="onboarding page.png" src="https://files.readme.io/8903839c25f12df28e1c4b488699670e2dadca83af9ddfebfc0cf4eacd2ce744-33198275479953.png" />

**通过平台进入添加应用向导：**

* 在顶部菜单栏中选择 **My Apps（我的应用）**，然后点击 **+ Add app（添加应用）**。
* 在 AppsFlyer 首页点击 **+ Add app（添加应用）**。
* 在顶部菜单栏中打开账户菜单（电子邮件地址下拉菜单），选择 **App onboarding（应用接入）**，然后点击 **+ Onboard another app（接入另一个应用）**。

<Image align="center" alt="add an app (1).png" src="https://files.readme.io/894b7b76c1da76e2308b110266cbffeb579c551033ce302ade182c1d63fd9384-33198275483793.png" width="593px" />

<div id="adding-an-app" />

## 添加应用

进入 [添加应用](#进入添加应用向导) 向导后，按照以下步骤操作：

1. [填写应用详细信息](#填写应用详细信息)。
2. [填写其他信息](#填写其他信息不适用于网页端应用)。
3. 点击 **Add my app（添加我的应用）**。
4. 复制 Dev Key，供 <Anchor target="_blank" href="/marketers/zh/docs/getting-started-onboarding-for-marketers#第2步sdk--api对接">SDK 对接</Anchor>时使用（您也可以稍后在 <Anchor target="_blank" href="/marketers/zh/docs/app-settings#常规应用设置">应用设置</Anchor>页面中查看该密钥）。
5. 点击 **Done（完成）**，或点击 <strong>+ Add another app（添加另一个应用）</strong>继续添加其他应用。重复上述步骤即可。

<div id="note-1" />

> 📘 **注意**
>
> * 只有管理员及<Anchor target="_blank" href="/marketers/zh/docs/user-management">拥有相应权限的账户用户</Anchor>才能添加应用。
> * 添加应用时，可选项会根据您之前选择的选项而有所不同。

注册应用后，该应用会显示在面板中。要确保系统记录安装和应用内事件，并将其正确归因到相应的媒体渠道，您还需要：

* 对接 SDK。
* 在合作伙伴市场中将应用与合作伙伴关联。

请参阅<Anchor target="_blank" href="/marketers/zh/docs/getting-started-onboarding-for-marketers">完整的应用接入流程说明</Anchor>，了解如何完成后续步骤。

<div id="enter-app-details" />

### 填写应用详细信息

选择应用所属的平台，并填写相应的必填信息，如下所示：

<div id="android-androidtv-fire" />

<Accordion title="Android、Android TV 和 Fire">

以下平台适用此选项：

* Android（移动端）
* Android TV
* Amazon Fire
* Amazon Fire TV
* Kindle

<Table>
  <thead>
    <tr>
      <th>
        Google Play 状态
      </th>
      <th>
        适用情况
      </th>
      <th>
        必填信息
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="in-store"></span>
        已上架
      </td>
      <td>
        应用已在 Google Play 商店上架
      </td>
      <td>
        **Google Play URL**（从 Google Play 复制）

        * **示例：** https://play.google.com/store/apps/details?id=com.appsflyer.adNetworkTest&hl=en&gl=GB
        * **重要提示！**
          * 如果您的应用**未**在美国的 Google Play 商店上架：
            * URL 必须包含应用实际上架的国家或地区代码，如上述示例所示：<strong>&gl=`{country_code}`。</strong>如果未填写国家或地区代码，添加应用时会报错。
            * 语言代码为可选项： **&hl=`{language_code}`**
          * 如果应用**已**在美国的 Google Play 商店上架，国家或地区代码和语言代码均为可选项。
      </td>
    </tr>
    <tr>
      <td><span id="pending-approval-not-published"></span>
        等待审核/尚未发布
      </td>
      <td>
        应用尚未发布，或正在等待 Google Play 审核
      </td>
      <td>
        **Android 包名**

        * **示例：** com.appsflyer.adNetworkTest
        * **注意：** 包名区分大小写
        * **格式要求：**
          * 至少包含两个字段段落，各段之间以一个或多个句点分隔
          * 每个字段段落都必须以字母开头
          * 仅允许使用字母、数字和下划线（a-z、A-Z、0-9 或 \_）
          * 最长为 100 个字符

        详情请参阅 <Anchor target="_blank" href="https://developer.android.com/studio/build/application-id">Android 开发者文档</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="third-party-store-out-of-store"></span>
        第三方商店/非应用商店渠道
      </td>
      <td>
        应用位于 Google Play 以外的 Android 应用商店，和/或可通过应用商店以外的渠道下载
      </td>
      <td>
        * **Android 包名：** 具体要求请参阅上文。
        * **应用 URL：** 从第三方应用商店或应用下载页面复制。
        * **渠道名称（可选）：** 您可以在为相应商店或下载渠道准备的 APK 文件的 AndroidManifest.xml 中设置唯一名称，例如 my\_apk。渠道名称必须符合以下要求：
          * 区分大小写
          * 必须与<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">添加应用时在 **Channel name（渠道名称）** 字段中填写的名称</Anchor>完全一致

        ```xml
        <application>
             ...
             <meta-data android:name="CHANNEL" android:value="my_apk"/>
             ...
        </application>
        ```

        <div id="note-2" />

        > 📘 **注意**
        >
        > 不建议使用 channel 参数实现多商店归因。为简化对接流程并采用更标准化的实现方式，建议改用 af\_store 参数。

        <div id="important" />

        > 🚧 **重要提示！**
        >
        > 如果您的应用可以通过多个来源获取，例如 Google Play、第三方应用商店和应用商店以外的下载渠道，请务必考虑如何设置<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution">Android 多商店归因</Anchor>。
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="ios-tvos-macos" />

<Accordion title="iOS、tvOS 和 macOS">

以下平台适用此选项：

* iOS
* tvOS
* macOS

| App Store 状态 | 适用情况 | 必填信息 |
| --- | --- | --- |
| <span id="in-store::f93cfa22"></span>已上架 | 应用已在 App Store 上架 | **App Store URL**（从 App Store 复制）<ul><li>**示例：** https://apps.apple.com/us/app/partner-integrations/id1543229303</li><li>**注意事项：**<ul><li>URL 必须包含商店所在国家或地区的两位字母代码，例如上述 URL 中的 **us**</li><li>如果应用在 2019 年 6 月 14 日之前已上架 App Store，其 URL 中可能包含 itunes.apple.com，而不是 apps.apple.com。</li></ul></li></ul> |
| <span id="pending-approvalnot-published"></span>等待审核/尚未发布 | 应用尚未发布，或正在等待 App Store 审核 | 应用提交至的 App Store 所在**国家或地区**<br /><br />App Store 分配的**应用 ID**，不包含前缀 id<ul><li>**示例：** 1543229303</li><li>**格式：** 由 9 位或 10 位数字组成，仅允许使用 0-9</li></ul> |

</Accordion>

<div id="windows-xbox" />

<Accordion title="Windows">

以下平台适用此选项：

* Windows Phone
* Windows（桌面端）

| Microsoft Store 状态 | 适用情况 | 必填信息 |
| --- | --- | --- |
| 已上架 | 应用已在 Microsoft Store 上架 | **Microsoft Store URL**（从 Microsoft Store 复制）<ul><li>**示例：** https://www.microsoft.com/en-us/p/wordament/9wzdncrfhwfg</li><li>**注意：** 上述 URL 是 Windows Phone 应用的示例。 Windows 桌面端应用的 URL 格式可能有所不同。</li></ul>**应用 ID：** 最长为 150 个字符。 |
| 等待审核/尚未发布 | 应用尚未发布，或正在等待商店审核 | Microsoft Store 分配的**应用 ID**<ul><li>**最长为：** 150 个字符</li><li>**示例：** 9wzdncrfhwfg</li><li>**注意：** 应用 ID 区分大小写</li></ul> |

</Accordion>

<div id="web-pba" />

<Accordion title="Web（PBA）">

<div id="note-3" />

> 📘 **注意**
>
> Web 应用用于定义一个网站，并将其纳入 People-Based Attribution（PBA，基于用户的归因）功能所使用的品牌组合。
>
> * 此选项仅向已订阅 PBA 的客户开放。
> * <Anchor target="_blank" href="/marketers/zh/docs/people-based-attribution-pba-overview">了解更多</Anchor>关于 PBA，以及如何归因网站访问、网页事件和由网站辅助促成的应用安装，从而统一查看用户在不同渠道、平台和设备上的旅程。

**完整 URL：** 输入您希望衡量流量的网站完整 URL。您需要在该网站上部署或计划部署 <Anchor target="_blank" href="/marketers/zh/docs/onboarding-guide-to-people-based-attribution#2">PBA网页端SDK</Anchor>。

<Image align="center" alt="URL_diagram" src="https://files.readme.io/45c6e433af693fd8c293380192a8e60f26c82588195bab61bafbc9839baf5c7b-33198323426961.png" width="377px" />

URL 需要包含 –

* 协议
* 子域名【可选】
* 域名
* 顶级域名
* 路径［可选］– 用于指定网站上的某个目录或页面

**应用名称：** 您为该应用选择的名称

* 最长为 100 个字符
* 不允许使用 XSS 标签

<div id="important-1" />

> 🚧 **重要提示！**
>
> 创建网页端应用后，如果要修改其属性（URL 和应用名称），必须先删除该应用，再重新创建；**这也意味着您必须**<Anchor target="_blank" href="/marketers/zh/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle">**删除该应用所属的品牌组合**</Anchor>。

**后续步骤：**

* 将新创建的网页端应用添加到 <Anchor target="_blank" href="/marketers/zh/docs/pba-brand-bundles-and-settings">PBA 品牌组合</Anchor>中，以便在 PBA 面板中查看。
  * 创建品牌组合前，请确保已将所有计划纳入该品牌组合的移动应用添加到账户中。
* 在网页端应用指定的网站上<Anchor target="_blank" href="/marketers/zh/docs/pba-web-sdk-integration-guide">对接 PBA网页端SDK</Anchor>，以开始获取衡量数据。

</Accordion>

<div id="web" />

<Accordion title="Web">

使用网页端平台创建新的网页端应用，通过网页端Performance Measurement（网页效果衡量）衡量网站访问和转化。

<div id="before-you-begin" />

#### **开始之前**

* 旧版 People-Based Attribution（PBA）Web 应用会显示在<strong>「Web（PBA）」</strong>分类下，并标记为<strong>「Legacy（旧版）」</strong>。
* 如果您正在从旧版 PBA网页端应用迁移，可以继续使用现有的 PBA网页端Dev Key。

<div id="to-add-a-web-app" />

#### **添加网页端应用**

1. 进入 **My Apps（我的应用）** > **Add app（添加应用）**。
2. 选择 **Website（网站）**。
3. 填写以下信息。

**应用名称：** 为网页端应用选择的名称。

* **长度：** 1–100 个字符
* **允许使用的字符：** 各语言的字母、数字、空格（不能位于开头或结尾），以及以下特殊字符：. - \_ :
* **不允许使用的字符：** ; \`{ }\` $ &lt; > \` \

**示例：** My Online Store、Corporate Website 2024、E-Commerce\_Production

**主域名（完整 URL）：** 网站的主域名。创建网页端应用时需要设置此项，创建后无法修改。

* **格式：** 有效的域名，不包含协议、路径或端口
* **长度：** 最多 500 个字符
* **处理：** AppsFlyer 会自动执行以下处理
  * 移除 http:// 或 https://
  * 移除末尾的斜杠
  * 将域名转换为小写
* **不可修改：** 创建应用后，无法编辑主域名

**重要提示：** 如果需要更改主域名，必须删除并重新创建网页端应用，这会导致历史数据的连续性受到影响。

**示例：**

* https://shop.example.com/checkout → 保存为 shop.example.com → 应用 ID：website-shop.example.com
* example.com/ → 保存为 example.com → 应用 ID：[website-example.com](http://website-example.com)

**应用 ID：** AppsFlyer 根据主域名为网页端应用生成的唯一 ID。

* 系统会按照以下格式自动生成：website-`<primary_domain>`
* 示例：website-shop.example.com

**Web SDK ID：** Web SDK 用于归因的标识符（之前称为 web\_dev\_key）。

创建应用时有两种选择：

**选项 1：生成新的 ID（默认）**

* 自动创建新的网页端SDK ID
* 格式：website-`{yourdomain.com}`
* 示例：website-shop.example.com
* **适用场景：** 全新的网页归因对接

**选项 2：沿用现有 PBA Dev Key**

* 从下拉菜单中选择现有 PBA（People-Based Attribution）Web 应用的 Dev Key
* 无需修改网站代码，即可平滑迁移
* **适用场景：** 从旧版 PBA 迁移至新的网页归因解决方案

**注意：** 沿用 PBA Dev Key 后，您无需修改网站的现有实现<strong>，即可从 PBA 迁移到新的网页端应用</strong>

每个 PBA Dev Key 只能分配给**一个**Web 应用。分配给某个网页端应用后，该密钥便不能再用于其他网页端应用。

* **长度：** 1–550 个字符
* **不可修改：** 创建应用后无法更改
* **PBA 迁移：** 下拉菜单中仅显示您账户下 PBA网页端应用所使用的 Dev Key

**币种：** 应用报告所使用的币种。

* 使用标准 ISO 4217 币种代码（例如 USD、EUR、GBP、ILS）
* 从下拉菜单中选择
* 此项为必填项

**时区：** 应用报告所使用的时区。

* 使用 IANA 时区格式（例如 America/New\_York、Europe/London、Asia/Tokyo）
* 从下拉菜单中选择
* 此项为必填项

4. 点击 **Create app（创建应用）**。

**限制**

* 创建应用后，**无法更改主域名**。
* 主域名会自动以 **PRIMARY** 类型添加到 **Excluded Domains（排除域名）**。

每个旧版 **Web Dev Key 只能用于一个**新的网页端应用。

<div id="note-4" />

> 📘 **注意**
>
> 有关网页归因设置的完整信息，请<Anchor target="_blank" href="/marketers/zh/docs/configure-web-performance-measurement-settings">参阅相关文档</Anchor>。

</Accordion>

<div id="roku" />

<Accordion title="Roku">

**应用名称：** 从 <Anchor target="_blank" href="https://developer.roku.com/developer">Roku Developer Dashboard</Anchor>（Roku 开发者面板）复制的频道名称。

* **示例：** My Roku channel
* **格式要求：**
  * 最长为 100 个字符
  * 不允许使用 XSS 标签

**频道 ID：** Roku 分配给该频道的数字 ID。

* **格式要求：**
  * 仅允许使用数字（0–9）
  * 最长为 50 个字符
* **如何查找频道 ID？**
  * 打开 <Anchor target="_blank" href="https://developer.roku.com/developer">Roku Developer Dashboard</Anchor>，点击要添加到 AppsFlyer 的频道名称，进入该频道的 Roku Preview & Publish 页面。这将打开该频道的 Roku Preview & Publish 页面。
  * 页面 URL 末尾的数字就是频道 ID：

    <Image align="center" alt="" src="https://files.readme.io/89f6513eee03558a9dc8e465fe67953780074477fc0fe20675b721d8116671af-33198275490577.png" />

</Accordion>

<div id="amazon-vega-os" />

<Accordion title="Amazon Vega OS">

**应用名称：** 您为应用选择的名称。

**应用 ID：** 应用的 ID。采用反向 DNS 格式：`<tld>`.`<company_name>`.`<app_name>`  
至少包含两个字段段落。每个字段段落都必须以字母开头，后续可使用 `A-Z` `a-z` `0-9.` `-`  

示例：com.company.my\_app

详情请参阅 <Anchor target="_blank" href="https://developer.amazon.com/docs/vega/0.21/manifest-package.html#fields">Amazon Vega OS 文档</Anchor>中的“id”字段。

</Accordion>

<div id="vizio-smartcast" />

<Accordion title="Vizio SmartCast">

**应用名称：** 您为应用选择的名称。

**应用 ID：** Vizio 识别的应用 ID。必须以 `vizio.` 开头，后续包含 2–10 个字符，可使用 `A-Z` `a-z` `0-9.` `-`。如需确认应用 ID，请联系您的 Vizio 对接代表。

</Accordion>

<div id="samsung-tizen" />

<Accordion title="Samsung Tizen">

**应用名称：** 您为应用选择的名称。

**应用 ID：** Samsung 分配给应用的 Bundle ID。以字母 `G` 开头，后跟 8–15 位数字。如何获取应用 ID？

1. 通过[相关链接](https://developer.samsung.com/tv-seller-office/guides/overview.html)登录 Samsung TV Seller Office。

   1. 输入开发者 URL。
2. 系统会自动生成并显示 Bundle ID。您可以使用该 ID 访问应用商店 URL。
3. 如果遇到问题，请在 Seller Office 中提交工单。

注意：要访问应用专属的商店网页，请将 Bundle ID 添加到以下 URL 中：“[https://www.samsung.com/us/appstore/app/](https://www.samsung.com/us/appstore/app/)”。

例如，如果 Bundle ID 为“G15147002586”，对应的网页 URL 为：“[https://www.samsung.com/us/appstore/app/G15147002586/](https://www.samsung.com/us/appstore/app/G15147002586/)”。该页面的元数据中会显示开发者 URL、Bundle ID 和应用商店 ID。

<Image align="center" alt="" src="https://files.readme.io/ee4b192abab24e064013a4a034bda38fb3ed49497ae333e327e1b78dd05d5349-33198275491729.png" />

</Accordion>

<div id="lg-webos" />

<Accordion title="LG WebOS">

**应用名称：** 您为应用选择的名称。

**应用 ID：** LG WebOS 应用 ID。

* **格式要求：**
  * 最长为 50 个字符
  * 使用类似 Bundle ID 的格式，可包含 `A-Z` `a-z._` 必须以字母开头。
* **示例：** com.my-company.app

如需确认应用 ID，请联系您的 LG WebOS 对接代表。

</Accordion>

<div id="playstation" />

<Accordion title="PlayStation">

**应用名称：** 您为应用选择的名称。

**应用 ID：** PlayStation concept ID，即分配给游戏或其他内容项目的唯一标识符。该 ID 是 PlayStation 商店 URL 中的一个 5–9 位数字。该 ID 位于应用商店 URL 的末尾：

<Image align="center" alt="playstation_app_id_url.png" src="https://files.readme.io/df92705244e55e7adc44a88076556609983ec3dff89c03df77e19f0f1a061bbb-33198323434513.png" />

</Accordion>

<div id="vidaa" />

<Accordion title="Vidaa">

**应用名称：** 您为应用选择的名称。

**应用 ID：** Vidaa 应用 ID。最长为 50 个字符。

</Accordion>

<div id="steam" />

<Accordion title="Steam">

**应用名称：** 您为应用选择的名称。

**应用 ID：** Steam 应用 ID。即 Steam 商店 URL 中显示的 5–8 位数字：

<Image align="center" alt="steam_store_app_url.png" src="https://files.readme.io/4976c0323eab0c08b61d4a1a7a75ebf7ea9fcd819176ff574421f0de4d8c614c-33198275497617.png" />

</Accordion>

<div id="meta-quest" />

<Accordion title="Meta Quest（Oculus）">

**应用名称：** 您为应用选择的名称。

**应用 ID：** Meta Quest 应用 ID，显示在下载该应用的 Meta 应用商店 URL 末尾。长度为 3–50 个字符，可使用 `A-Z` `a-z0-9._-`

<Image align="center" alt="" src="https://files.readme.io/1938b3f89b866ebdd3452367d7410c423ce57372544a801ca3d1b409f3bff541-33198323442449.png" width="397px" />

</Accordion>

<div id="nintendo-switch" />

<Accordion title="Nintendo Switch">

**应用名称：** 您为应用选择的名称。

**应用 ID：** Nintendo Switch 应用 ID，显示在下载该应用的商店 URL 末尾。由 14 位数字组成。

* **示例：** 70010000012345

</Accordion>

<div id="xbox" />

<Accordion title="Xbox">

**应用名称：** 您为应用选择的名称。

**应用 ID：** Xbox 应用 ID，显示在下载该应用的 Xbox 商店 URL 末尾。仅包含 12 位字母和数字（`A-Z` `a-z0-9`）。

<Image align="center" alt="" src="https://files.readme.io/c33ffcb35d4488b9340cfa8b475097eab7b79bfeaf94e8cf8ce6478dda07d341-33198275505041.png" />

**注意：** 应用 ID 区分大小写。

</Accordion>

<div id="epic-games" />

<Accordion title="Epic Games">

**应用名称：** 您为应用选择的名称。

**应用 ID：** Epic Games 应用 ID，可在下载该应用的商店中找到。长度为 3–50 个字符，可使用：`A-Z` `a-z0-9._-`。

<Image align="center" alt="" src="https://files.readme.io/81d1f043c8a7ef5e367a62d564f8c6241c6057445363b21286e3f72ad4210cf6-33198275508497.png" />

</Accordion>

<div id="native-pc" />

<Accordion title="Native PC">

**应用名称：** 您为应用选择的名称。

**应用 ID：** Native PC 应用 ID。长度为 3–50 个字符，可使用：`A-Z` `a-z0-9._-`。

</Accordion>

<div id="enter-additional-information-not-applicable-to-web-apps" />

### 填写其他信息（不适用于网页端应用）：

<Image align="center" alt="" src="https://files.readme.io/561aea51bbfaa733721040706cac2b9520e35cfe71027fa34d08ed7890baf00c-33198323448081.png" width="559px" />

<div id="select-currency" />

#### **选择币种**

选择应用数据在面板中显示时使用的币种。系统会根据事件发生时适用的汇率，将收入和支出事件转换为所选币种。<Anchor target="_blank" href="/marketers/zh/docs/app-settings#localization-currency">详情请参阅</Anchor>有关应用币种设置及其影响的说明。

<div id="important-2" />

> 🚧 **重要提示！**
>
> 请谨慎选择应用币种。一旦系统记录了成本和收入数据，就无法再更改币种。

<div id="select-timezone" />

#### **选择时区**

此处选择的时区应与您在其他归因合作伙伴平台（例如 Meta Ads 和 Google Ads）中设置的时区保持一致。这样可以尽可能确保 AppsFlyer 面板中的数据与合作伙伴提供的数据相匹配。

<div id="note-5" />

> 📘 **注意**
>
> * 设置时区后，该设置会被锁定，直到次日才能更改。
> * <Anchor target="_blank" href="/marketers/zh/docs/changing-app-time-zone-settings">详情请参阅</Anchor>有关应用时区设置及其影响的说明。

<div id="define-app-audience" />

#### **定义应用受众**

选择 **Yes（是）** 或 **No（否）**，说明您的应用是否面向儿童，或是否面向混合受众（包括儿童和成人）。  
如果选择 **Yes（是）**：

1. 打开并阅读有关如何为面向儿童的应用实施合规要求的<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">指南</Anchor>。
2. 勾选确认框，确认您已阅读该指南，并将按照指南要求实施相应的控制措施。

<div id="note-6" />

> 📘 **注意**
>
> * 添加应用两周后，系统会向您发送通知，要求您确认已为面向儿童的应用实施隐私控制措施。确认后，您将收到确认消息。您可以随时在通知中心查看该消息，也可以在<Anchor target="_blank" href="/marketers/zh/docs/audit-log">审计日志</Anchor>中查看确认详情。
> * 有关面向儿童的应用，请参阅<Anchor target="_blank" href="/marketers/zh/docs/child-directed-apps-faq">常见问题</Anchor>。

<div id="manage-your-apps-in-bulk-via-api" />

#### 通过 API 批量管理应用

账户管理员可以通过<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/app-management-v2-overview">专用 API 批量管理多个应用</Anchor>。该 API 支持界面中的主要功能，包括添加和删除应用，以及更新应用设置。该 API 同时还采用了相同的错误验证机制。

<div id="note-7" />

> 📘 **注意**
>
> 目前，通过 API 添加应用和更新应用设置仅适用于移动应用；删除应用则适用于所有平台。

<div id="add-a-debug-or-testing-app" />

### 添加调试或测试应用

如果开发人员创建了**调试**、**沙盒**或**测试应用**，您必须先将其添加到面板。开发人员开始使用该应用进行测试后，相关数据便会显示在该应用的面板中。

<div id="note-8" />

> 📘 **注意**
>
> 对于尚未在 App Store 上架且没有有效 App Store ID 的 iOS 应用，您仍然可以使用**虚拟的 iOS App Store ID**添加应用，并继续进行 SDK 测试。这样无需真实的 App Store 上架记录，也可以对接 SDK 并开展测试。

有关如何创建调试应用并将其添加到面板的开发说明，请参阅：

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/testing-android#creating-an-android-debug-app">Android 说明</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/testing-ios#creating-an-ios-debug-app">iOS 说明</Anchor>

<div id="about-pending-apps" />

## 关于待发布应用

在调试应用或测试 AppsFlyer SDK 时，将应用设置为待发布状态会很有帮助。

应用在面板中显示为待发布状态，不会影响数据采集和衡量。无论应用在应用商店中处于待发布状态还是已正式上线，只要用户安装并使用该应用，安装数据和应用内事件数据都会照常记录在面板中。

待发布应用正式上线后，AppsFlyer 会自动检测并更新其状态，因此您无需重新添加应用。详情请参阅有关待发布应用的说明，以及如何手动刷新应用状态的可选操作步骤，请<Anchor target="_blank" href="/marketers/zh/docs/why-is-my-app-still-pending">了解更多</Anchor>。

<div id="troubleshooting" />

## 故障排查

以下是一些常见问题及解决方法：

<div id="app-wasnt-added" />

<Accordion title="无法添加应用">

如果出现此错误，请联系您的客户成功经理（CSM），或发送电子邮件至[hello@appsflyer.com](mailto:hello@appsflyer.com)。

</Accordion>

<div id="app-not-in-the-store" />

<Accordion title="应用未在商店中上架">

请确认您复制的商店 URL 正确，并且使用了相应的应用名称或应用 ID。

</Accordion>

<div id="cant-access-marketplace" />

<Accordion title="无法访问应用市场">

从非美国地区的商店添加 Android 应用时，有时会出现此错误。请按照以下步骤解决：

1. 按照上文所述，将应用状态设置为**等待审核/尚未发布**，然后添加应用。
2. 进入 AppsFlyer 的**应用设置**页面。
3. 将**应用商店国家/地区**更改为正确的选项（例如日本）。

</Accordion>

<div id="something-went-wrong" />

<Accordion title="出现错误：“出了点问题，请重试。”">

一种可能的原因是：尝试添加 Android 应用时没有填写国家或地区代码，而该应用又未在美国的 Google Play 商店上架。请参阅[上文](/docs/adding-an-app-to-appsflyer#in-store)的详细说明，了解如何解决此问题。

</Accordion>

<div id="my-ios-app" />

<Accordion title="我的 iOS 应用已从 App Store 下架，为什么仍然能看到安装数据？">

这是因为，如果用户的设备之前安装过该应用，操作系统仍可能允许用户重新安装。因此，即使应用已不再出现在 App Store 中，用户仍可能安装该应用，而这些安装仍会计入 AppsFlyer 的统计数据。

</Accordion>

<div id="other-information" />

## 其他信息

<div id="product-line" />

<Accordion title="产品线">

您可以向产品线添加应用，也可以从产品线中移除应用。有关产品线及其功能的详细信息，请<Anchor target="_blank" href="/marketers/zh/docs/product-line-group-apps-for-cross-platform-attribution">参阅产品线相关文档</Anchor>。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%BF%B0 01H8Y09SSKZS2RHM35JT16ESKM=%E6%A6%82%E8%BF%B0 entering-the-wizard-for-adding-an-app=%E8%BF%9B%E5%85%A5%E6%B7%BB%E5%8A%A0%E5%BA%94%E7%94%A8%E5%90%91%E5%AF%BC 01H8Y0K9EHWH05DB5K02ASJG11=%E8%BF%9B%E5%85%A5%E6%B7%BB%E5%8A%A0%E5%BA%94%E7%94%A8%E5%90%91%E5%AF%BC 01H8F2TENNWXADKVZFHY9SE8JC=%E6%B3%A8%E6%84%8F adding-an-app=%E6%B7%BB%E5%8A%A0%E5%BA%94%E7%94%A8 01H8ECFB7V0DCNE0ZKPZ2GCVMP=%E6%B7%BB%E5%8A%A0%E5%BA%94%E7%94%A8 01H81661SR41SQFZZ0AW6K2EDM=%E6%B3%A8%E6%84%8F-1 enter-app-details=%E5%A1%AB%E5%86%99%E5%BA%94%E7%94%A8%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF 01H815FE64VZZS9WGJSC8VY74D=%E5%A1%AB%E5%86%99%E5%BA%94%E7%94%A8%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF 01H815FE64CXEHWTV40NVYQHGJ=android-androidtv-fire h_01KRB930DZ2NRYBZSERSG7WB3A=%E6%B3%A8%E6%84%8F-2 01H815FE641Q6N5JY5846QE59Y=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA 01H815FE64X0SPA71TBQ9T4ZVB=ios-tvos-macos 01H815FE64ZZA2N1XQFBRXVF41=windows-xbox 01H815FE64XZKDJW1CX5R1JE1T=web-pba 01H815FE646GWA7KJ83KTGHH05=%E6%B3%A8%E6%84%8F-3 01H815FE65R1Z06TJR0DNC8PFY=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 h_01KGEPG8V7ZZ6V2EYYPES0QM77=web before-you-begin=%E5%BC%80%E5%A7%8B%E4%B9%8B%E5%89%8D h_01KGPM33BA6AJSX32CTN808AXM=%E5%BC%80%E5%A7%8B%E4%B9%8B%E5%89%8D to-add-a-web-app=%E6%B7%BB%E5%8A%A0%E7%BD%91%E9%A1%B5%E7%AB%AF%E5%BA%94%E7%94%A8 h_01KGPM3GTYJJ0ARD3R1XHVAQ8F=%E6%B7%BB%E5%8A%A0%E7%BD%91%E9%A1%B5%E7%AB%AF%E5%BA%94%E7%94%A8 h_01KGPM5TTNSECSWEAQY5VH7DTY=%E6%B3%A8%E6%84%8F-4 01H815FE65X37H40AN99EZJ940=roku h_01KDJP1G4QZHAKH13M5D3CD793=amazon-vega-os 01H815FE654W6D4FCANR1DET8A=vizio-smartcast 01H815FE65J6T610QQXWJS0CJS=samsung-tizen 01H815FE65CRW81AD1006KHGV4=lg-webos 01H815FE65ESQZ56C8B4HG9P8M=playstation 01H815FE65483DV8MD4STH3QTR=vidaa 01H815FE655PZS1H9YW95X1R53=steam 01H815FE655XP075WYRVVFKD4F=meta-quest 01H815FE65XJEVHNT45SHGWJS4=nintendo-switch 01H815FE6598PD87PNBE7MFEQ8=xbox 01H815FE658WJCB1ZCPGAD4GGS=epic-games 01H815FE652P3HCWY2PEDJJARM=native-pc enter-additional-information-not-applicable-to-web-apps=%E5%A1%AB%E5%86%99%E5%85%B6%E4%BB%96%E4%BF%A1%E6%81%AF%E4%B8%8D%E9%80%82%E7%94%A8%E4%BA%8E%E7%BD%91%E9%A1%B5%E7%AB%AF%E5%BA%94%E7%94%A8 01H815FE65AWE8VKV9FYJ7N8MV=%E5%A1%AB%E5%86%99%E5%85%B6%E4%BB%96%E4%BF%A1%E6%81%AF%E4%B8%8D%E9%80%82%E7%94%A8%E4%BA%8E%E7%BD%91%E9%A1%B5%E7%AB%AF%E5%BA%94%E7%94%A8 select-currency=%E9%80%89%E6%8B%A9%E5%B8%81%E7%A7%8D h_01HHCFD94K6PGQRED6Z6KXKRQF=%E9%80%89%E6%8B%A9%E5%B8%81%E7%A7%8D 01H815FE65X7BCFKH1EEFA91GQ=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-2 select-timezone=%E9%80%89%E6%8B%A9%E6%97%B6%E5%8C%BA h_01HHCFDE25S92GZ9TPGQW4PXHV=%E9%80%89%E6%8B%A9%E6%97%B6%E5%8C%BA h_01HMNSSBP2EFXCVW290MKW1EFV=%E6%B3%A8%E6%84%8F-5 define-app-audience=%E5%AE%9A%E4%B9%89%E5%BA%94%E7%94%A8%E5%8F%97%E4%BC%97 h_01HHCFDRNFDERZZV3TT8BVXMB4=%E5%AE%9A%E4%B9%89%E5%BA%94%E7%94%A8%E5%8F%97%E4%BC%97 h_01H9MYF17VNBETQ0HS745EJ85H=%E6%B3%A8%E6%84%8F-6 manage-your-apps-in-bulk-via-api=%E9%80%9A%E8%BF%87-api-%E6%89%B9%E9%87%8F%E7%AE%A1%E7%90%86%E5%BA%94%E7%94%A8 h_01HR3Z81NXCAZKK26HWCN5VD9D=%E9%80%9A%E8%BF%87-api-%E6%89%B9%E9%87%8F%E7%AE%A1%E7%90%86%E5%BA%94%E7%94%A8 h_01HR3ZJW7YD4B8WV0NW9MX6EVP=%E6%B3%A8%E6%84%8F-7 add-debug-or-testing-app=%E6%B7%BB%E5%8A%A0%E8%B0%83%E8%AF%95%E6%88%96%E6%B5%8B%E8%AF%95%E5%BA%94%E7%94%A8 h_01K2F8JX66F614HF8D5MWQ26P7=%E6%B7%BB%E5%8A%A0%E8%B0%83%E8%AF%95%E6%88%96%E6%B5%8B%E8%AF%95%E5%BA%94%E7%94%A8 ios-dummy-app-id-note=%E6%B3%A8%E6%84%8F-8 h_01K2F8JX662XEY0A47DZG6DHWQ=%E6%B3%A8%E6%84%8F-8 about-pending-apps=%E5%85%B3%E4%BA%8E%E5%BE%85%E5%8F%91%E5%B8%83%E5%BA%94%E7%94%A8 01H815FE65MYPABC3DTVEMA8E9=%E5%85%B3%E4%BA%8E%E5%BE%85%E5%8F%91%E5%B8%83%E5%BA%94%E7%94%A8 troubleshooting=%E6%95%85%E9%9A%9C%E6%8E%92%E6%9F%A5 01H815FE655HS8EA4R00D0VCYD=%E6%95%85%E9%9A%9C%E6%8E%92%E6%9F%A5 01H815FE65V2GYP0Q612512DE0=app-wasnt-added 01H815FE65A0HPTVVCT42QQA6M=app-not-in-the-store 01H815FE65EN3PBSH5BKRGNNXD=cant-access-marketplace 01H815FE65FR4ATDA4CVX2FW9N=something-went-wrong h_01JNK9HB2ZWQ78XK9B33QWHV49=my-ios-app other-information=%E5%85%B6%E4%BB%96%E4%BF%A1%E6%81%AF h_01K7KSRWCB1Y89T21JFJR42VAJ=%E5%85%B6%E4%BB%96%E4%BF%A1%E6%81%AF h_01K7KSPDSSG8CRCQB5V545Y12Z=product-line" />

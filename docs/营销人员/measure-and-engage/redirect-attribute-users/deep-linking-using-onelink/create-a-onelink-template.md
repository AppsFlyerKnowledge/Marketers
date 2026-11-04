---
title: 创建OneLink模板
metadata:
  keywords:
    - template
    - Marketers
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2014-11-03T12:35:49Z'
  edited_at: '2026-10-14T10:14:31Z'
  id: 207032246
  locale: zh-cn
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/zh-cn/articles/207032246
---
> **概要：** 本文介绍了OneLink模板的配置方式。后续创建的OneLink链接将以模板中的跳转逻辑为基础，用于各类营销投放。您必须先配置模板，然后才能创建链接并打造终端用户体验。

<div id="onelink-templates" />

## OneLink模板

<Embed title="创建OneLink模板" typeOfEmbed="youtube" url="https://www.youtube.com/embed/d4AtCJ9122Q" providerUrl="https://www.youtube.com" />

OneLink模板具有以下特点：

* OneLink模板不是终端用户可点击的链接，而是生成一组自定义链接的基础。通常每个应用只需要一个模板（测试除外），就能满足所有的链接创建需求，用于各类广告投放。
* 您可以在OneLink模板中针对不同的设备平台及应用安装状态配置不同的跳转行为。
* OneLink模板代表了后续所有OneLink链接的引流逻辑，适用于各类营销投放。其中包括针对以下场景的跳转设置：
  * **未安装应用的新用户**：跳转到与其设备适配的应用商店或网址
  * **已安装应用的现有用户**：通过安卓的App Link、iOS的Universal Link或URI scheme调起应用需要协同开发人员完成相关设置。
  * **请注意**：网站或应用商店的跳转可以分链接单独设置。

<div id="create-a-onelink-template" />

## 创建OneLink模板

| 人员 | 前期准备 | 所需时间 | 结果 |
| --- | --- | --- | --- |
| <ul><li>如需为尚未安装应用的新用户配置跳转逻辑（如跳转到与设备适配的应用商店或网页），仅需市场人员即可完成。</li><li>如需为已经安装用户的现有用户配置跳转逻辑（如吊起应用）则需要市场人员与安卓/iOS开发人员协作完成。</li></ul> | <ul><li>确保您有一个AppsFlyer帐户，且账户中至少有一个应用。</li><li>配置模板的市场人员必须具备AppsFlyer的管理员账户或OneLink模板的添加/修改权限。</li></ul> | 功能对接，用时约为1.5个小时。 | 获得一个OneLink模板，作为后续创建链接的基础，将用户引导到与其设备适配的应用商店、网页或应用。 |

<div id="create-a-onelink-template-with-redirection-logic-for-new-app-users" />

<Accordion title="针对新用户的OneLink模板及其跳转逻辑">

**要创建OneLink模板，请执行以下操作：**

1. 从AppsFlyer后台的侧边栏中选择**互动** > **OneLink管理**。  
   OneLink解决方案向所有账户开放，您可以使用该功能为您的各个应用创建OneLink模板及其下属的自定义链接。  
   [![](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png) **请注意**：如果您还未创建任何模板，系统会弹出新客户使用指引。这时请根据指引操作，无需参照本流程。
2. 点击菜单图标 > **添加OneLink模板**。  
   进入 OneLink模板设置页面。  
   [![OneLink_template_page_en-us.png](https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png)](https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png)
3. 在**OneLink模板名称**字段中为其命名。

   <div id="note" />

   > 📘 **注意**
   >
   > * 建议在OneLink模板名称中包含**应用名称**（如上述示例中的feed\_me）或OneLink所代表的使用场景或用户体验（如pre\_launch\_landing\_page）。
   > * 名称中不应包含广告活动或渠道名称或媒体渠道（因为这不是实际的终端用户链接，而只是用于创建许多链接的基础模板）或平台名称（Android、iOS，因为多平台通常是首先使用OneLink模板的原因）。
   > * 该模板名称仅在内部使用。它不会影响营销归因数据，也不会被用户看到。

4. 填写**子域名**字段。
   * 选择与您的品牌匹配的子域。举例来说，假设您的网站是[www.abcd.com](https://www.abcd.com)，那么您可以将abcd作为您的子域名。
   * 用户会在链接URL中看到这个子域名，使用场景示例:`https://abcd.onelink.me/RPsv/37e5cd36`。
   * 基于该模板创建自定义链接后，即无法更改其子域名。
   * 仅限填写小写字母、数字或连字符（-）。
   * OneLink全面支持品牌域名，帮助您优化投放效果，提升品牌曝光。 <Anchor target="_blank" href="/marketers/zh/docs/brand-onelink-with-your-domain">详情请见此处说明。</Anchor>
5. 选择相关的安卓和/或iOS应用。
6. （可选）如果您想使用额外的参数阻止链接被劫持，请开启安全短链接。**要开启安全短链接，请执行以下操作：**

   在 “**安全短链接**” 下，启用 **“不要将点击归因于已添加的参数**”。

   这对你来说意味着什么：一旦开启，如果有人向根据此模板创建的短链接添加参数，则该点击不会被归因。根据模板的重定向设置重定向用户；仅影响归因。

   > 📄 **示例**
   >
   > | 链接 | 归因结果 |
   > | --- | --- |
   > | `[subdomain].onelink.me/[template_id]/[shortlink_id]` | 像往常一样归因。 |
   > | `[subdomain].onelink.me/[template_id]/[shortlink_id]?param=value` | 添加了一个参数，因此点击不归因。 |


   > 📘 **备注**
   >
   > * 此设置适用于模板级别。无法为单个链接打开或关闭它。
   > * 对于在此功能发布之前创建的模板，该设置处于关闭状态。如果你想要的话可以把它打开。对于发布后创建的模板，它默认处于启用状态；如果您不想要它，请将其关闭。

7. 针对**未安装应用**的用户设置跳转路径。  
   * 如果您同时选择了一个安卓应用和一个iOS应用，则模版默认会将新应用跳转到与其设备适配的应用商店
   * 如果您仅选择了一个应用（不管是安卓应用还是iOS应用），模板会默认把所有用户（不管是iOS还是安卓用户、新用户还是老用户）都引导到同一个终点。
   * 如果您选择的安卓应用尚未在Google Play上架，请输入安卓用户的跳转链接。
   * 【可选】如果应用在Google Play以外的应用商店上架，可设置**跳转到第三方应用商店**。请确保该应用在其他商店中的包名与OneLink模板中所选的安卓应用包名一致。
   * 【可选】**改为其他网址**：在某些场景中，您可能希望新用户先去落地页进行体验，而不是直接去应用商店下载应用（或者应用还未上架）。要实现这样的跳转，请在URL字段填写相应的网址。**请注意**：如果您同时设置了第三方应用跳转和网页跳转，用户会默认跳转到第三方应用商店。
   * 【可选】**向启用保密传送（Private Relay）的用户展示轻应用（App Clip）**（适用于iOS 14+）。<Anchor target="_blank" href="/marketers/zh/docs/apple-app-clips-integration-guide">参见轻应用详解</Anchor>。
8. 若需为**已安装应用**的用户配置模板，请跳过此步。针对现有用户的相关配置请见[下一节](/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users)。
9. 【可选】针对**在PC端点击链接**的用户配置跳转路径。  
   * 如果您通过电子邮件或社交媒体分享链接，用户可能会在PC端点击您的链接。如果您觉得可能会有大量用户从PC端点击链接，建议将这些用户引导到落地页或主站主页，或者让用户在手机上接收短信链接，而不是直接跳转应用商店。
   * 默认情况下，PC端用户会跳转到网页版的App Store或Google Play商店——具体取决于模版的应用设置。
     * 要更改默认商店选项，请选择“PC 网页 URL”并添加相关的网店 URL。请确保将商店域名添加到跳转白名单中。
10. 【可选】**选择其他平台的应用**  
    适用于在以下平台有专属应用版本的场景：
    * **Windows phone**：打开相应的开关并选择应用，或**改为其他网址**。
    * **iPad**：打开相应的开关并选择iPad应用。
    * **Amazon Kindle Fire**：打开相应的开关并添加Amazon Store ASIN或应用页的URL。
11. 点击**保存OneLink模板**（将OneLink模板更新为已编辑的模板）。   
    OneLink模板创建完成，后续可在该模板下创建大量可点击链接（请参阅<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink链接与用户体验</Anchor>）。

</Accordion>

<div id="add-redirection-logic-for-existing-app-users" />

<Accordion title="为现有用户配置跳转逻辑">

现有用户通常希望在点击链接后直接进入应用，而非跳转到应用商店或网页。点击后 ，可以使用三种技术直接打开应用程序：

* **iOS Universal Links**: 适用于iOS 9及以上版本，能以流畅、安全的方式调起应用。
* **安卓App Link**：适用于安卓6及以上版本，能以流畅、安全的方式调起应用。**请注意**：三星互联网浏览器无法使用安卓应用程序链接打开应用程序。
* URI scheme：  
  * 备用方案：
    * 安卓：当安卓App Link由于失效或未设置而无法打开应用时，URI scheme可作为有效的备用方案。
    * iOS：i当Universal Link由于失效或未设置而无法打开应用时，URI scheme可作为备用，但功能有限。<Anchor target="_blank" href="/marketers/zh/docs/uri-scheme-fallback-for-ios">详情请见此处说明。</Anchor>
  * 这是在三星设备上吊起应用的主要方式。
  * URI scheme是一个地址，用户访问该地址时会打开应用（若已安装）。它们类似于网站链接，但是打开的是应用程序而非网站。
  * 对同一个应用的iOS和安卓用户必须使用同一个URI。

建议尽量使用以上所有技术手段，以确保最佳的用户体验、数据安全和设备覆盖率。 在以上所有链接技术全部启用时，OneLink会自动根据每个用户的具体情况使用最合适的方式打开应用。

**请按以下方式在OneLink模板中为现有用户配置跳转逻辑：**

1. 从AppsFlyer后台的侧边栏中选择**互动** > **OneLink管理**。
2. 选择您想要修改的OneLink模板。
3. 点击菜单图标（⋮），然后点击**编辑OneLink模板**。
4. 向下滚动到**应用程序安装时** 。[![](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)
5. 请按照iOS、安卓和备用方案对应所的指南进行操作：

   <Tabs>
   <Tab title="iOS Universal Link">

   Universal Link的格式与常规网页链接相同（如[https://yourbrand.onelink.me](https://yourbrand.onelink.me)或 [https://www.yourbrand.com](https://www.yourbrand.com)） ，因此需要设置一个子域名（具体请见[上一篇指南](/docs/create-a-onelink-template#创建onelink模板)）。OneLink还支持全面<Anchor target="_blank" href="/marketers/zh/docs/brand-onelink-with-your-domain">品牌化的域名</Anchor>，但这不是本指南的要点。

   **如需通过Universal Link调起应用**，请按以下步骤操作：

   1. 让您的iOS开发人员完成以下事项：
      * 把这个OneLink模板的子域名同步给开发人员。
      * 把<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">这些指南</Anchor>发送给开发人员。
      * 开发人员会把Team ID（或称Apple App ID Prefix，结构为PF23MIWNTW）返回给您。
      * 如果您的应用还未上架，还需要让开发人员将Bundle Identifier发送给您（结构为：com.myapp.something）。  
        [![](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)
   2. 在OneLink模板页面中，点击**改用Universal Link打开应用** 。
   3. 在新窗口中，选取**使用通用链接开启应用程序**。
   4. 在**Team ID**字段中，输入开发人员提供的Team ID。
   5. 如果您的应用还未上架，请同时输入**Bundle Identifier**。
   6. 点击**保存更改** 。

   </Tab>

   <Tab title="安卓App Link">

   App Link的格式与常规网页链接相同（如[https://yourbrand.onelink.me](https://yourbrand.onelink.me)或[https://www.yourbrand.com](https://www.yourbrand.com)），因此需要设置一个子域名（具体见[上一篇指南](/docs/create-a-onelink-template#创建onelink模板) ）。OneLink还支持全面<Anchor target="_blank" href="/marketers/zh/docs/brand-onelink-with-your-domain">品牌化的域名</Anchor>，但这不是本指南的要点。

   **前期准备** ：

   记录您为此OneLink模板选择的子域。

   **如需通过安卓App Link调起应用**，请按以下步骤操作：

   1. 联系您的安卓开发人员：   
      让他们按照<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#generating-a-sha256-fingerprint">相关说明</Anchor>生成一个SHA256证书指纹。  
      然后他们会给您发送一个结构如下的SHA256证书指纹：`DC:65:43:67:F3:BD:02:52:AC:B4:50:F1:74:54: 23:49:4D:49:6C:E6:DF:56:BD:CB:53:06:11:5B:C9:4E:5D:0C`。
   2. 在OneLink模板页面中，点击**改用App Link打开应用** 。
   3. 在新窗口中，选择**使用App Link打开应用**。
   4. 在**SHA256指纹识别**字段中，输入开发人员提供的SHA256指纹识别。   
      界面会显示自动生成的意图过滤器代码。
   5. 联系您的安卓开发人员：   
      将自动生成的意图过滤器代码发送给他们。  
      让他们按照<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">相关说明</Anchor>进行操作并确认完成。

   </Tab>

   <Tab title="URI scheme">

   URI Scheme主要用作备选方案让iOS和安卓用户打开应用，因此针对这两个平台的URI必须相同。

   **设置Android和iOS URI备选：**

   1. 请联系您的iOS和安卓开发人员，确定一个URI Scheme，例如：`feedmeapp://`。

      <div id="h_01H9Q4E7VR4CAK0PJY269GQ9XJ" />

      > 👍 **提示**
      >
      > * Apple 和 Google 对于应用方案都不强制实施唯一命名。 **为您的品牌选择一个独特的方案名称**，以避免不同应用之间的方案冲突。建议将应用的包名（bundle ID）作为其scheme名称，如com.company.app<strong>。</strong>
      > * 如果您想要对应用的iOS和安卓版本都启用OneLink，请务必**为两个平台设定相同的scheme**。我们对<Anchor target="_blank" href="https://help.contrast.co/hc/en-us/articles/200865293-URL-Scheme-Intro-for-App-Developers">iOS</Anchor>和<Anchor target="_blank" href="https://developer.android.com/training/app-links/deep-linking.html">安卓</Anchor>分别做了具体说明。
      > * URI Scheme不能以http或https开头。

   2. 让iOS开发人员根据<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-uri-scheme">iOS相关指南</Anchor>在应用中添加URI scheme。  
      **并且**  
      让安卓开发人员根据<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#procedures-for-uri-scheme">安卓相关指南</Anchor>在应用中添加URI scheme。
   3. 完成上一步后，开发人员需要确认所添加的URI scheme值，结构类似`exampleapp://`、`exampleapp://home`或`exampleapp://main`等等。
   4. 在OneLink模板页面中，点击**同时使用URI Scheme打开应用** 。
   5. 选择**使用URI Scheme打开应用** 。
   6. 输入URI方案值。
   7. 点击**保存更改** 。
   8. 测试URI方案（可以由您或您的开发人员完成）：
      1. 准备一个iOS设备和一个安卓设备，在两个设备上都安装您的应用后，使用<Anchor target="_blank" href="https://halgatewood.com/deeplink/">免费的公共测试工具</Anchor>进行测试。
      2. 点击由该工具生成的链接。  
         如果URI方案正确，应用程序将打开。

   </Tab>
   </Tabs>

6. 点击**更新OneLink模板**。

<div id="note-1" />

> 📘 **注意**
>
> * 保存或更新OneLink模板时，AppsFlyer的系统会自动生成AASA和/或Digital Asset Link的JSON文件用于域名验证，并为您保存在服务器中。如果验证失败，Universal Link和App Link可能无法正常跳转。
> * OneLink模板从更新到生效之间最多会有1小时的延迟。

</Accordion>

<div id="customize-qr-codes" />

<Accordion title="定制化二维码">

![OnelinkQRFinal__1_.gif](https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif)

您可以通过以下方式对OneLink生成的二维码进行定制：

* 在二维码中添加品牌标识
* 更改二维码的颜色

**请注意**：您需要在OneLink模板中定制二维码，而不能在具体链接中操作，定制后的二维码会应用到模版下的所有链接中。

**请按以下步骤定制二维码**：

1. 从AppsFlyer后台的侧边栏中选择**互动** > **OneLink自定义链接**。
2. 选定要编辑的模版，将鼠标悬停在对应的**操作**图标上，然后点击**定制二维码**。  
   界面会打开二维码编辑器。
3. 输入您品牌logo图片的URL，如[https://yourbrand.com/logo.png](https://yourbrand.com/logo.png)。  
   品牌logo图片须符合以下要求：

   * PNG或JPG格式
   * 透明背景的方形或圆形图像
   * 尺寸不能小于400 x 400 px
   * 为确保印刷效果，请使用分辨率最高的图像
4. 设置二维码颜色。
5. 点击**Save**保存。

</Accordion>

## 特点与局限性

<div id="key-traits-and-limitations" />

<div id="traits-and-limitations" />

<Accordion title="特性与限制">

| 特点 | 说明 |
| --- | --- |
| 代理 | 代理无法创建OneLink模板和链接。 |
| 添加/编辑OneLink模板 | 账户用户如要添加或编辑OneLink模板需申请相关<Anchor target="_blank" href="/marketers/zh/docs/user-management">权限</Anchor>。 |
| OneLink模板 | 每个账户最多可创建600个OneLink模板。 |
| PC端 | 如果您想让PC端用户在点击OneLink链接后跳转到其他网址，那么请在配置OneLink链接或模板时使用`af_web_dp`参数，并在其中添加该网址。如果用户在PC端点击了包含`af_web_dp`的链接，AppsFlyer不会将其记为一次点击。 |
| 跳转到第三方应用商店 | 如果您需要在OneLink模板中设置多个应用商店，请确保您的应用在这些商店中的包名是完全一致的。如需进一步了解跳转到第三方安卓应用商店的OneLink设置，请参考<Anchor target="_blank" href="/marketers/zh/docs/bulletin-onelink-redirection-to-third-party-android-app-stores?query=3rd%20party%20store">此文档</Anchor>。<br /><br />**请注意**：<ul><li>由于华为等一部分第三方应用商店使用的包名不同于其他商店，因此跳转到华为应用商店的OneLink模板不能添加其他应用商店。</li><li>部分小米设备上预装了GetApps应用商店，与Google Play的URI scheme相同。因此，如果您打算将使用这些设备的用户引导到Google Play，但您的应用未在GetApps上架，链接会自动跳转至 GetApps。</li><li>如果包名一致但流量入口不同，跳转不会收到影响，但无法进行归因。</li><li>详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution">第三方应用商店的归因与数据</Anchor>。</li></ul> |
| 更新模版 | <ul><li>更新OneLink模板后，新的配置会在1小时内生效。</li><li>如果与之关联的应用被删除，则您将无法编辑OneLink模板。在这种情况下，您可以：<ul><li>创建新模板。</li><li>请联系您的AppsFlyer客户成功经理，或发送邮件至hello@appsflyer.com以恢复已删除的应用。</li></ul></li></ul> |
| URI Scheme | 参阅<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#chrome-browser-on-ios">此处</Anchor>。 |

</Accordion>

对OneLink模板有疑问？我们的<Anchor target="_blank" href="/marketers/zh/docs/onelink-troubleshooting-and-faq#onelink模板常见问题解答">常见问题解答</Anchor>文档可以帮助您找到答案！

<div id="next-step" />

## 下一步

请按面板提示在您的模板下<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">创建OneLink链接</Anchor>。

<div data-zendesk-anchors="onelink-templates=onelink%E6%A8%A1%E6%9D%BF h_01H9Q4E7VQ0GKZ9HFF88190TYN=onelink%E6%A8%A1%E6%9D%BF procedures=%E5%88%9B%E5%BB%BAonelink%E6%A8%A1%E6%9D%BF h_01H9Q4E7VQYGZ1MH5SS3ZYZF1K=%E5%88%9B%E5%BB%BAonelink%E6%A8%A1%E6%9D%BF h_01H9Q4E7VQ648CQ1VJTB1TC571=create-a-onelink-template-with-redirection-logic-for-new-app-users h_01H9Q4E7VQ15AAR1VXNKWR1XGT=%E6%B3%A8%E6%84%8F h_01KYMEP248AG3T4M0MPD6YW5P1=%E7%A4%BA%E4%BE%8B h_01KYMEP248VHE2TDCD3KXNSV4F=%E5%A4%87%E6%B3%A8 h_01H9Q4E7VQ4NEWYAD6AMR9YKGY=add-redirection-logic-for-existing-app-users h_01H9Q4E7VR8164HR6MD0EAV2SN=%E6%B3%A8%E6%84%8F-1 h_01H9Q4E7VR0F4B7CTF08YTG715=customize-qr-codes traits-and-limitations::f2d46c64=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01KZX7Q3V7PNRJKKC6PDMABVKQ=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01H9Q4E7VR2B50EQE31DDG8GNZ=traits-and-limitations next-step=%E4%B8%8B%E4%B8%80%E6%AD%A5 h_01H9Q4E7VRJK31P9CSGJFCKQQF=%E4%B8%8B%E4%B8%80%E6%AD%A5" />

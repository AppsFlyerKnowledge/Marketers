---
title: PBA Web SDK对接指南
metadata:
  keywords:
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-05-17T09:05:30Z'
  edited_at: '2026-10-14T10:06:10Z'
  id: 360001610038
  locale: zh-cn
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/zh-cn/articles/360001610038
---
> **概要：** 通过Web SDK将AppsFlyer对接到您的网站，记录和衡量访问、事件、转化以及收入。

[![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)

<div id="web-sdk-user-and-integration-guide" />

## Web SDK用户与对接指南

* Web SDK JavaScript标签：
  * PBA（People-Based Attribution，基于用户的归因）解决方案的一部分，用于分析跨平台的用户路径。
  * 可将网站上的访问和行为上报至AppsFlyer平台。
  * 是一个无需编程的网站插件模块，与访客的操作系统和浏览器无关。
  * 大小：40-60KB。
* 建议在移动应用中部署AppsFlyer移动SDK，并在网站端部署Web SDK，从而对用户行为进行统一记录与映射。
* 发生在网站之外的事件，可通过<Anchor target="_blank" href="/marketers/zh/docs/web-server-to-server-events-api-for-pba-web-s2s">Web S2S event API</Anchor>（Web S2S）进行记录。

<div id="selecting-a-code-snippet" />

## 选择代码片段

选择与您的集成类型和安全要求相匹配的片段。有两个选项可供选择：

* [标准Web SDK](#标准web-sdk)：标准集成。
* [高级SDK验证](#高级sdk验证)：一种增强的集成，为Web SDK增加供应链保护。使用此功能为CDN攻击、DNS劫持和中间人攻击增加额外的安全层。

<div id="important" />

> 🚧 **重要提示！**
>
> 如果您正在从标准Web SDK过渡到高级SDK验证，请用新的片段替换现有的片段。请勿在现有片段上添加新的片段。

<div id="standard-web-sdk" />

### 标准Web SDK

使用此片段来部署标准Web SDK集成。将其粘贴在您希望加载SDK的所有页面的标签的顶部附近。

<div id="standard-without-smart-banners" />

<Accordion title="没有智能横幅">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
</script>
```

</Accordion>

<div id="standard-with-smart-banners" />

<Accordion title="（智能横幅助力）">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba,banners&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
  AF('banners', 'showBanner');
</script>
```

</Accordion>

<div id="advanced-sdk-verification" />

### 高级SDK验证

高级SDK验证为Web SDK增加供应链保护。它确保在用户浏览器中运行的代码与AppsFlyer发布的代码完全相同。SDK源代码本身与标准集成相同；只有交付和验证机制不同。

高级SDK验证：

* 为CDN攻击、DNS劫持和中间人攻击增加额外的安全层。
* 大约增加250毫秒的SDK加载时间。

高级SDK验证是可选的。标准集成仍然完全支持，并且是第三方分析像素的市场标准。高级SDK验证提供了超出标准的额外保护层。

如果您的网站使用nonce强制实施内容安全策略（CSP），请参见[内容安全策略（CSP）](#内容安全策略csp)中的管理隐私部分，以获取此代码片段的nonce扩展变体。

<div id="advanced-verification-without-smart-banners" />

<Accordion title="没有智能横幅">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="advanced-verification-with-smart-banners" />

<Accordion title="（智能横幅助力）">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="integrating-the-web-sdk-into-the-website" />

## 在网站中对接Web SDK

<div id="installation-and-integration" />

<Accordion title="安装与对接">

<div id="considerations-and-actions-required" />

#### 注意事项与操作要求

| 对接检查清单 |
| --- |
| 为确保事件被完整记录和正常访问，请务必在网站的所有页面中安装Web SDK。 |
| 将您在上面选择的代码片段[放置](#选择代码片段)在页面范围内尽可能早地加载。最好位于head标签顶部位置，以确保尽早加载。 |
| 如通过Google Tag Manager（GTM）对接：<ul><li>确保SDK在页面中只加载一次。</li><li>通过<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">GTM的优先级设置</Anchor>，使SDK在第一时间完成加载。</li></ul> |
| 在设置Web SDK时，可选择**使用**或**不使用**智能横幅。请遵循后文中的相关说明。 |
| 对接必备条件<ul><li>访问记录</li><li>事件记录</li><li>设置[Customer User ID](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid)（CUID）如果没有CUID，请与您的CSM讨论备选方案。</li></ul>使用<Anchor target="_blank" href="/marketers/zh/docs/test-pba-web-sdk-integration">测试工具</Anchor>验证对接是否成功。 |

**前期准备** ：

* 请与市场营销人员确认已创建<Anchor target="_blank" href="/marketers/zh/docs/pba-brand-bundles-and-settings">品牌套件</Anchor>。
* 如需更多说明，请参见<Anchor target="_blank" href="/marketers/zh/docs/onboarding-guide-to-people-based-attribution">PBA上手指南</Anchor>。
* 注意事项：如您已经在使用独立的智能横幅Web SDK，请先将其移除，统一替换为Web SDK，以便同时支持Smart Banners和PBA；请勿为PBA添加单独的Web SDK。

**具体方法如下：**

* 获取Web SDK的网页开发者密钥。 **注意：** 此密钥与移动应用使用的密钥不同。
  * **如需获取网页开发者密钥：**
    1. 从AppsFlyer后台的顶部菜单栏中选**我的应用**
    2. 点击**查看品牌套件。**
    3. 复制所需的**Web Dev Key(WEB\_DEV\_KEY)。**
* 如需使用智能横幅，请获取智能横幅密钥。
  * **操作方法如下：**
    1. 从AppsFlyer后台的侧边栏中选择**互动**> **网页到应用**>**智能横幅**。
    2. 复制所需的**智能横幅密钥**。
* 确认您已获得在网站的head标签中添加脚本的权限。
* 如果使用Google Tag Manager（GTM），请确保GTM已完成与网站的对接。

**您可以通过以下任意方式对接Web SDK：**

<Tabs>
<Tab title="原生">

<div id="javascript-code-snippet" />

#### 嵌入JavaScript代码片段

请使用以下方法之一对接Web SDK。

<div id="to-install-the-web-sdk-without-smart-banners" />

#### **如需在不使用智能横幅的情况下安装Web SDK：**

1. 请在网站所有页面中重复以下操作：
2. 在下面的代码片段中，将`WEB_DEV_KEY`替换为准备阶段获取的WEB\_DEV\_KEY。
3. 将您在上面选择的代码片段[粘贴](#选择代码片段)到您网站的head标签中。位置尽量靠前。

<div id="to-implement-the-web-sdk-with-smart-banners" />

#### **如需在使用智能横幅的情况下安装Web SDK：**

1. 在您网站的所有页面上重复以下程序。
2. 在您选择的代码片段[中](#选择代码片段)，使用先决条件中指定的键替换`WEB_DEV_KEY`和`YOUR_BANNER_KEY`。
3. 将此代码片段粘贴到网站的head标签中。位置尽量靠前。

</Tab>

<Tab title="Google Tag Manager">

**要使用Google Tag Manager (GTM)实现Web SDK：**

1. <Anchor target="_blank" href="https://developers.google.com/tag-manager/quickstart">进入Google Tag Manager。</Anchor>
2. 为AppsFlyer Web SDK创建一个新标签。

   [![](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)
3. 选择**自定义HTML**标签类型。
4. 给标签起一个有意义的名称。
5. 根据是否使用智能横幅，执行以下步骤：
   * 如果**不使用**智能横幅：
     1. 将您选择的代码片段[粘贴](#选择代码片段)到**标签配置**窗口中。
     2. 在代码片段中，将`WEB_DEV_KEY`替换为前置条件中获取的 WEB\_DEV\_KEY。
   * 如果**使用**智能横幅：
     1. 将您选择的代码片段[粘贴](#选择代码片段)到**标签配置**窗口中。
     2. 在代码片段中，将`WEB_DEV_KEY`和`YOUR_BANNER_KEY`替换为前置条件中获取的WEB\_DEV\_KEY。
6. 点击**保存**。
7. 根据是否使用智能横幅，执行以下步骤：
   * **要将触发条件添加到所有页面：**
     1. 点击**添加触发条件**。

        [![gtm-af-tag-sdk-trigger.png](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)
     2. 选择**所有页面**。
     3. 点击**保存**。
     4. 输入标签名称并点击**保存**。  
        至此，操作完成。
   * **要将触发条件添加到特定页面：**
     1. 点击**保存标签**。
     2. 在GTM主界面中，选择<strong>触发条件。</strong>点击**新建**。
     3. 点击铅笔图标。
     4. 选择**页面视图**作为触发条件类型。  
        [![PBAselectTrigger_us-en.jpg](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)
     5. 选择**部分页面视图。**
     6. 根据需要设置页面和触发条件。
     7. 点击**保存**。
     8. 将触发条件与AppsFlyer Web SDK标签关联。具体操作如下：
        1. 在GTM主界面中，选择标签。
        2. 选择您之前创建的标签。
        3. 在触发面板中，点击铅笔图标。
        4. 选择您之前创建的页面视图触发条件。

           [![](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)
        5. 点击**保存**。

</Tab>

<Tab title="Adobe Launch Tag Manager">

1. [在Adobe Experience Cloud后台创建一个Property（即标签）。](/docs/pba-web-sdk-integration-guide#create-a-property-in-adobe-experience-cloud)
2. [将Web SDK添加到Adobe Launch标签](/docs/pba-web-sdk-integration-guide#add-the-web-sdk-to-the-adobe-launch-property)
3. [将Adobe Launch标签添加到网站](/docs/pba-web-sdk-integration-guide#add-the-adobe-launch-tag-to-the-website)
4. [发布Adobe Launch环境](/docs/pba-web-sdk-integration-guide#publish-the-adobe-launch-environment)

<div id="create-a-property-in-adobe-experience-cloud" />

<Accordion title="在Adobe Experience Cloud后台创建一个Property（即标签）。">

![adobe_create_property.png](https://files.readme.io/1f97d619d5fdfe47b1dd1a2e17c0169e939c32bcda62580ba259d6e86f61d6c2-20260884824209.png)

1. 进入**Adobe Experience Cloud** > Launch。
2. 点击**Adobe Experience Cloud Launch**下的**Go to Launch**。
3. 点击**New Property**。
4. 命名属性。
5. 选择**Platform**下的**Web**。
6. 输入您的网站域名。
7. 点击**保存**。

</Accordion>

<div id="add-the-web-sdk-to-the-adobe-launch-property" />

<Accordion title="将Web SDK添加到Adobe Launch标签">

<Image alt="web_property_rules.png" src="https://files.readme.io/5f592f3ce1f5b319c8f6f96a6235618d884a4faccb1387b1f22c1fd2ce662d15-360006168098.png" width="491px" />

1. 在**My web property**页面中，选择**Rules**选项卡。
2. 为该规则命名。推荐使用，**加载Web SDK**。
3. 在**If**部分，点击**Events**下的 **+Add**。
   * 在**Event Type**下选择**Core - DOM Ready**。
   * 点击**Keep Changes**。
4. 在**Then**部分，点击**Actions**下的 **+Add**。
   * 在**Action Type**下，进入**Custom Code**。
   * 选择**JavaScript** > **Open Editor**，将**不带&lt;script>标签**的Web SDK代码片段粘贴到编辑器中。
   * 点击**Keep Changes**，关闭代码编辑器。
5. 点击**保存**。

</Accordion>

<div id="add-the-adobe-launch-tag-to-the-website" />

<Accordion title="将Adobe Launch标签添加到网站">

[![adobe_tag.png](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)

1. 在**My web property**页面中选择**Environments**选项卡。
2. 找到您想要发布的环境（Development或Production）所在的那一行。
   * 在**激活**header下，点击相关行的方框图标；通常是Production环境。
   * 有关发布**Adobe Launch**环境的详细信息，请见下一小节内容。
3. 在**Web Install Instructions**对话框中执行以下操作：
   * 复制脚本代码片段。
   * 关闭对话框。
4. 将代码片段粘贴到网站的&lt;head>标贴中。

</Accordion>

<div id="publish-the-adobe-launch-environment" />

<Accordion title="发布Adobe Launch环境">

[![adobe_publishing_env.png](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)

1. 从**My web property**进入**Publishing**选项卡。
2. 在**Development**部分下点击**Add New Library**。
   * 为该Library命名并选择一个环境。
   * 在**Resource Changes**下，点击**Add a Resource**。
   * 点击**Rules** > **Load Web Banners** > **Latest** > **Select & Create a New Revision**。
   * 点击**保存**。
3. 在**Development**部分下执行以下操作：
   * 点击新创建的library旁边的操作菜单（以3个点表示），并选择**Build for Development**。
   * 再次点击操作菜单，并选择**Submit for Approval**。
4. 在**Submitted**部分下执行以下操作：
   * 点击操作菜单并选择**Build for Staging**。
   * 再次点击操作菜单并选择**Approve for Publishing**。
5. 在**已批准**部分：
   * 点击操作菜单并选择**Build & Publish to Production**。
   * 至此，该流程操作完毕。

</Accordion>

在移动设备上加网站载时，横幅中会显示当前启用的素材。如需在特定页面或根据用户操作显示横幅，请参见<Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Adobe Launch规则</Anchor>。

</Tab>
</Tabs>

</Accordion>

<div id="ensure-that-the-sdk-is-working" />

<Accordion title="确保SDK正常运行">

安装完成后，需要验证访客浏览器是否能够成功调用AppsFlyer Web SDK，并确保数据消息已正常发送。您可以通过检查浏览器开发者工具中的网络请求来完成此操作。

**验证SDK加载和运行的步骤如下：**

1. 打开网站。
2. 打开浏览器开发者工具。

   ![WebSDK_us-en.jpg](https://files.readme.io/5550f0ee8c1a5852a983e6482cb0489696b669ffe5fade49d2308ee32f57201b-360009548497.jpg)
3. 转到（A）**广告平台**选项卡。
4. 刷新页面。
5. 按（B）**wa.** appsflyer筛选。
6. 选择（C）**events**消息。
7. 在 Headers（D）中确认以下信息：
   * **Request URL**为wa.appsflyer.com/events。
   * site\_id 查询参数=`WEB_DEV_KEY`。
   * (E) **status code is 200**.
8. 验证site\_id的值是否与品牌套件设置中的WEB\_DEV\_KEY一致：
   1. 在AppsFlyer后台的侧边栏中选择**设置**> **品牌套件。**
   2. 点击**网页开发者密钥**复制密钥。
   3. 将密钥粘贴到任意位置（例如新浏览器标签页或记事本）以查看。
   4. 验证site\_id和`WEB_DEV_KEY`是否匹配。
9. 确保SDK仅加载一次。多次加载可能会导致SDK无法正常运行。

</Accordion>

<div id="sending-events-optinoptout" />

<Accordion title="事件发送的启用与停用">

![5578-VistiorPrivacyOptIn_us-en.png](https://files.readme.io/cd6cbcaeb7f831f4efe74a9a6c6b20d5095602e7edf4dd38becd90864e73c2fb-360010263157.png)

Web SDK会将访客事件数据发送至AppsFlyer。您可以根据需要开启、关闭或控制事件发送。

注意事项：

* **SDK初始状态设置**：确定SDK是在页面加载时立即发送事件，还是等待明确的命令后再发送。该设置包含在网页代码片段中。
* **显式控制：** 可随时手动启用或停止事件发送。例如，如果您设置了数据授权横幅（如Cookie授权弹窗），可以在横幅的控制逻辑中嵌入命令，来启动或停止事件发送。显式控制的优先级高于SDK初始设置，且第一方Cookie具有以下特征：
  * Cookie设置在网站域名下。
  * Cookie过期时间由Web SDK或浏览器决定；到期后，SDK会恢复至初始设置。
  * SDK设置的Cookie不会影响浏览器自身的Cookie规则。

<div id="sdk-initial-state-setting" />

#### SDK初始状态设置

| 配置 | 代码片段 |
| --- | --- |
| [默认] 发送事件 | 对Web SDK代码片段进行以下更改。 如有需要，请添加measurementStatus参数：<br /><br />设置measurementStatus=true<br /><br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:true}` |
| 不发送事件 | 对Web SDK代码片段进行以下更改。如有必要，添加 measurementStatus 参数：<br /><br />设置measurementStatus=false  <br />  <br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:false}` |

<div id="explicit-control" />

#### 显式控制

| 操作 | 命令 |
| --- | --- |
| 开始发送事件（opt-in） | `window.AF_SDK.PLUGINS.PBA.enableMeasurement()` |
| 停止发送事件（opt-out） | `window.AF_SDK.PLUGINS.PBA.disableMeasurement()` |

</Accordion>

<div id="implement-a-content-security-policy-csp-policy" />

<Accordion title="实施内容安全策略 (CSP)">

如果您的网站需要严格的安全或数据隐私协议，请使用以下机制配置Web SDK如何与您的环境和数据交互。

<div id="content-security-policy-csp" />

#### 内容安全策略（CSP）

如果您的网站要求JavaScript通过CSP进行安全保护，Web SDK支持两种方法，具体取决于您的CSP配置。

* 使用**self**将`https://websdk.appsflyersdk.com`添加到您的`script-src`允许列表中。这适用于标准Web SDK和高级SDK验证。
* 使用nonce：如果您的策略使用`script-src 'nonce-...'`，您可以使用[高级SDK验证的nonce扩展变体](#带有csp-nonce片段的高级sdk验证)。这将nonce转发到验证过程所需的所有三个脚本标签。用您服务器生成的每个请求的nonce值替换`{{CSP_NONCE}}`。

下表显示了哪些CSP策略与nonce扩展变体兼容。

| 策略 | 有效 | 说明 |
| --- | --- | --- |
| `script-src 'self'` | 否 | 不允许外部CDN来源；内联脚本也被阻止。 |
| `script-src 'self' https://websdk.appsflyersdk.com` | 不完整数据 | 允许加载器和SDK，但内联设置脚本仍然被阻止。 |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | 是 | Nonce覆盖内联脚本和加载器；SDK标签通过加载器转发nonce。 |
| `script-src 'nonce-...' 'strict-dynamic'` | 是（推荐） | Nonce覆盖内联脚本和加载器；`strict-dynamic`将信任传播到动态注入的SDK标签。允许列表中不需要CDN来源。 |

CSP政策兼容性

<div id="advanced-sdk-verification-with-csp-nonce-snippets" />

#### 带有CSP nonce片段的高级SDK验证

<div id="nonce-without-smart-banners" />

<Accordion title="没有智能横幅">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="nonce-with-smart-banners" />

<Accordion title="（智能横幅助力）">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

</Accordion>

<div id="discard-query-params" />

<Accordion title="丢弃查询参数">

如果您的查询参数包含您不希望AppsFlyer记录的数据，您可以要求AppsFlyer平台丢弃某些或所有查询参数。这些参数将不会出现在原始数据或报表中。

您可以使用以下方法丢弃URL、referrer和header\_referer查询参数。

<div id="query-discard-options" />

#### 查询参数丢弃选项

| 方法 | 说明 |
| --- | --- |
| 丢弃所有查询参数 | 在URL后加上`af_url=true` |
| 丢弃指定查询参数 | 通过设置查询参数掩码，指定要丢弃的参数。  使用`af_url_mask=param`设置丢弃掩码，其中param为参数名称。<br /><br />示例：<br /><br />**带掩码的Url:**<br /><br />`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`<br /><br />**丢弃后的Url:**<br /><br />`param1=value1&af_url_mask=param2;param3` |

</Accordion>

<div id="principles-of-event-recording" />

## 事件记录原则

<div id="conversion-and-standard-events" />

<Accordion title="转化事件和标准事件">

* 用户事件由SDK记录并发送到AppsFlyer平台。
* 根据市场人员设置的<Anchor target="_blank" href="/marketers/zh/docs/pba-brand-bundles-and-settings#web-event-settings">转化事件</Anchor>列表，AppsFlyer会将事件分为 标准事件和转化事件：
* 转化事件数据可在PBA面板中查看。
* 转化和标准事件数据可在<Anchor target="_blank" href="/marketers/zh/docs/pba-raw-data-reports">原始数据报告</Anchor>中查看。

<div id="conversion-events" />

### 转化事件

* 转化事件能够帮助您洞察营销和业务成效，此类事件包括购买、下载、注册和订阅。
* PBA会将转化事件归因到驱动用户访问网站的媒体渠道。
* 通过识别被归因的媒体渠道，您可以评估并比较不同渠道带来的用户质量。
* 转化事件还可用于记录收入并计算ROI。
* 您可将广告在不同媒体渠道的投放成本与这些渠道带来的收入进行对比。

<div id="standard-events" />

### 标准事件

* 标准事件主要用于验证带来最终转化的用户路径和漏斗。
* 标准事件可用来衡量用户活跃度，突出带来深度用户的媒体渠道。
* 记录的用户行为也能帮助您标记用户，以便后续进行再营销活动。

<div id="recording-events" />

### 事件记录

在满足某些条件时触发Web SDK记录事件，例如，落地页加载时或用户与网页元素互动时。请参见[事件记录示例](#recording-events::f1e16eae)。

</Accordion>

<div id="identifying-users-using-customer-user-id-cuid" />

<Accordion title="使用客户用户ID（CUID）识别用户">

* AppsFlyer通过您分配的唯一CUID对Web用户进行识别。通常CUID由您的后端服务器管理。
* 建议使用与移动端相同的CUID，以便统一分析跨平台的用户行为。移动SDK中的函数为setCustomerUserId函数（iOS/span>，Android，<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid#设置cuid">Unity</Anchor>）。
* 在Web SDK中设置CUID：
  * 请在能够获取CUID后尽早设置。通常您需要等待用户通过登录或注册进行身份验证。
  * 触发JavaScript调用setCustomerUserId()的方法如下所示。  
    请注意：即使CUID是数字，也必须以字符串形式传递（需加引号）。
* 如果使用Web S2S，可能需要在后端将CUID与Web访客ID关联后通知PBA。
* CUID不得包含<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid#cuid与隐私保护">可直接识别个人身份的信息</Anchor>，如手机号或邮箱。

**示例：设置CUID**

```javascript
// Associate all current user web events to distinct ID 663274 
AF('pba', 'setCustomerUserId' , '663274')
```

</Accordion>

<div id="web-sdk-event-parameters" />

<Accordion title="Web SDK事件参数">

| 参数名称 | 是否必须配置 | 说明 |
| --- | --- | --- |
| eventType | 是 | 事件类型<br /><br />格式：字符串<br /><br />始终填写 "EVENT"<br /><br />示例：eventType："EVENT" |
| eventName | 是 | 事件名称<br /><br />格式：字符串<br /><br />示例：Purchase, Subscription |
| ~~eventCategory~~ | 否 | 已弃用，将在未来移除。请改用eventValue参数。 |
| ~~eventLabel~~ | 否 | 已弃用，将在未来移除。请改用eventValue参数。 |
| eventRevenue | 否 | 转化事件关联的收入。<br /><br />格式：浮点数 |
| eventRevenueCurrency | 否 | 收入数据的货币单位<ul><li><Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor>三位货币代码</li><li>默认：USD</li></ul>格式：字符串 |
| eventValue | 否 | 描述事件的事件参数映射。用于发送富应用内事件，如商品SKU、单价。<br /><br />格式：JSON<br /><br />**示例：** 要发送SKU ABC123，颜色为蓝色，单价为$3.99<br /><br />`{"sku": "ABC123", “color": "blue", "unit_price":3.99,"currency": "USD"}`<br /><br />**限制：** 1000个字符以内，超出部分将被截断。 |

</Accordion>

<div id="recording-event-scenarios" />

<Accordion title="事件记录场景示例">

示例事件

```javascript
// purchase event of shoes with associated revenue
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

您需要发送的事件类型取决于网站的业务性质。例如：电商网站与新闻网站所需的事件类型可能有所不同。请参阅以下场景，以了解您应该在何时发送何种事件。

<div id="online-store" />

#### 电商网站

假设您正在运营一家电商网站，您可能需要记录以下标准事件与转化事件：

* 搜索：标准事件
* 加入购物车：标准事件
* 从购物车中移除：标准事件
* 购买：转化事件

新闻网站

假设您正在运营一家新闻网站，您可能需要记录以下转化事件：

* 注册：转化事件
* 购买订阅：转化事件

</Accordion>

<div id="ensuring-that-events-are-sent" />

<Accordion title="确保事件被成功发送">

请网页开发人员参阅以下内容。

您可以通过实时查看测试事件，<Anchor target="_blank" href="/marketers/zh/docs/test-pba-web-sdk-integration">测试PBA Web SDK是否已正确对接</Anchor>。

**操作步骤如下**：

1. 打开网站。
2. 打开浏览器开发者工具。
   * <Anchor target="_blank" href="https://developers.google.com/web/tools/chrome-devtools/open#console">如何在Chrome中打开开发者工具</Anchor>
   * <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/Web_Inspector_Tutorial/EnableWebInspector/EnableWebInspector.html">如何在Safari中打开开发者工具</Anchor>
3. 切换到Network（平台）标签。
4. 触发事件。
5. 按消息筛选。

   ![pba_af_event.png](https://files.readme.io/394f43890d1aaf09114054a3bca1a003178526e768a5da0b554dbc8d63ef1eb4-360003502238.png)
6. 查找发送到wa.appsflyer.com的网络请求。
7. 检查以下内容：
   1. Status code = 200。
   2. Request Payload与事件参数一致。

</Accordion>

<div id="examples" />

## 示例

<div id="recording-events::f1e16eae" />

<Accordion title="事件记录">

以下示例代码仅供参考，请勿直接使用。

* 假设：在事件发送时，页面已经加载了Web SDK。
* 示例场景包含在以下场景下记录事件的代码：
  * 落地页加载时。
  * 用户与网站发生交互时。

<Tabs>
<Tab title="记录原生事件">

**在落地页加载时记录事件**

* 您有一个新闻订阅页面，您希望在该页面记录订阅事件。
* 你也可以设置一个“感谢页面”，用户订阅后会跳转到该页面。

```html
<html>
    <head>
        <!-- Assume that the server returns a response with details about the newly subscribed user -->
        <!-- Alternatively, you can extract data from localStorage or cookies,
            in case data was set in either of them during the subscription process
        -->
        <script>window.onload = function(){
            AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion', eventValue: {'label' : 'newspaper'}, eventName: 'subscription',}); } </script> </head> <body> <h1>Thank You for Subscribing to Our Newsletter</h1> </body> </html>
```

* 上述代码包含基本的HTML页面。页面必须先加载Web SDK，才能发送事件。
* 当用户跳转到感谢页面时，window.onload方法会调用AF()，将订阅事件发送至AppsFlyer。

**用户与网站互动时记录事件**

* 您运营一家电商网站，希望记录结算事件。
* 在用户点击结账按钮时，Web SDK会向AppsFlyer发送事件。

```html
<html>
<head>
    <!-- Assume that data about products in the shopping cart
    is stored in localStorage -->
    <script>
        window.onload = function () {
            document.getElementById('checkout').addEventListener('click', function () {
                AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
            });
        }
    </script>
</head>
<body>
    <h1>Shopping Cart</h1>
    <h2>Shirt</h2>
    <p>
        <ul>
            <li>Color: Blue</li>
            <li>Quantity: 2</li>
            <li>Price: $20</li>
        </ul>
    </p>
    <h2>Pants</h2>
    <p>
        <ul>
            <li>Color: Black</li>
            <li>Quantity: 3</li>
            <li>Price: $15</li>
        </ul>
    </p>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

上述代码包含基本的HTML页面。 页面必须先加载Web SDK，才能发送事件。

* 页面加载完成后，会将点击事件监听器（click listener）绑定到**结账**按钮。
* 当用户点击**结账**按钮时，回调函数：
  * 从localStorage中获取数据。
  * 调用AF()并传递数据。
* AF()将事件发送到AppsFlyer。

</Tab>

<Tab title="通过Tag Manager记录事件">

**在落地页加载时记录事件**

* 您有一个新闻订阅页面，您希望在该页面记录订阅事件。
* 您设置了一个感谢页面，用户在成功订阅后会跳转至该页面。

1. 设置感谢页面

   ```html Markup
   <html>
   <head>
       <script>
            // Google Tag Manager loads the Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
        <script>
           // Assume that the server returns a response with details about the newly subscribed user
           function getResponseFromServer() {
               return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
           }
           //Alternatively, you can extract data from localStorage or cookies,
           //in case data was set in either of them during the subscription process
           localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
       </script>
   </head>
   <body>
       <h1>Thank You for Subscribing to Our Newsletter</h1>
   </body>
   </html>
   ```

   上述代码加载了GTM，进而加载了Web SDK。接下来脚本中会发生两个操作：一个是从服务器获取用户详细信息的函数。另一个是将数据设置到本地存储的函数。GTM可以访问函数和localStorage。您可以通过GTM调用该函数并访问localStorage。
2. 在感谢页面加载后，添加一个新的标签用于归因订阅事件。

   [![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
3. 给标签起一个唯一的名称，并选择**自定义HTML**标签类型。
4. 将以下代码放入**自定义HTML**中。

   ```html
   <script> 
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'}); </script>
   ```

   ![gtm_tag_after_subscribe.png](https://files.readme.io/6cf080f94a97a7f38c50899a93d154320995e91f60963c075a5dd03b3a080408-360003515298.png)
5. 展开**高级设置**控件，然后在**标签顺序**控件中确保设置正确，以便在该标签执行后触发转化事件。

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. 要触发转换标签，请设置一个触发条件。在本示例中，触发条件为感谢页面加载。

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

**用户与网站互动时记录事件**

* 您运营一家电商网站，希望记录结算事件。
* 用户点击结账按钮后，Web SDK会向AppsFlyer发送事件。

1. 设置结账页面

   ```html Markup
   <html>
   <head>
       <script>
           // Google Tag Manager loads the Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
   </head>
   <body>
       <h1>Shopping Cart</h1>
       <h2>Shirt</h2>
       <p>
           <ul>
               <li>Color: Blue</li>
               <li>Quantity: 2</li>
               <li>Price: $20</li>
           </ul>
       </p>
       <h2>Pants</h2>
       <p>
           <ul>
               <li>Color: Black</li>
               <li>Quantity: 3</li>
               <li>Price: $15</li>
           </ul>
       </p>
       <button id='checkout'>Checkout</button>
   </body>
   </html>
   ```

   代码通过GTM加载Web SDK，其余部分为模拟的购物车HTML页面。**结账**按钮的ID为checkout。在GTM中配置点击事件时需要用到。
2. 在GTM中，点击<strong>Variables（变量）</strong>中的**Configure（配置）**，勾选**Built-In Variables**中的**Click Element（点击元素）**。  

   [![gtm-create-variable.png](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)
3. 新建变量，设置有意义的名称，类型选择All Elements（所有元素）。  

   [![gtm-checkout-all-elements.png](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png)](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png)
4. 在触发条件配置中，选择**Some Clicks（部分点击）**，根据#checkout的**CSS Selector**选择**Click Element（点击元素）**。  

   [![gtm-checkout-click-elememt.png](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)
5. 为结账操作创建一个新标签，选择自定义HTML类型，并将触发条件设置为结账。

   ```html
   <script>
    AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'}); </script>
   ```

   ![gtm-checkout-tag.png](https://files.readme.io/8d3f99dcd3c3ff8df9e6fc13076b798237b86f8cbc5bbd26f349fa9948edb0d6-360003431857.png)

</Tab>
</Tabs>

* 确保Web SDK功能标签在事件触发前已加载。
* 不要在事件值中包含特殊字符（例如货币符号）。
* 事件值字符串应少于50个字符。

</Accordion>

<div id="setting-customer-user-id-after-signup" />

<Accordion title="设置用户注册后的CUID">

以下示例中的代码仅供参考。请勿直接使用。如不确定如何使用此代码，请咨询网页开发人员。

注意事项：确保Web SDK在事件触发前已加载；请勿重复加载SDK。

使用场景：

* 用户在您的网站上注册。
* 网站代码收集用户信息并发送到服务器。
* 服务器为用户生成唯一的CUID。
* 在注册完成后跳转的感谢页面中，网站通过服务器返回的结果获取该CUID。
* 借助服务器响应，使用Web SDK的 setCustomerUserId() 方法设置CUID。

<Tabs>
<Tab title="原生">

注册页面示例：

```html Markup
<html>
<head>
    <!-- The Web SDK script loads first -->
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        };
    // This function stores the user email sent to the server after the user reaches the thank you page
    // The response from the server is a unique CUID that should be set using the web SDK setCustomerUserId method
        function storeUserEmail (){
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Sign Up</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Name</label>
            <input type="text" name="name" id="name"></div>
        <br />
        <div> <label>Email</label>
            <input type="email" name="email" id="email"></div>
        <br />
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

该代码展示了一个简单的注册表单。表单提交时，用户邮箱会保存到localStorage。跳转至感谢页面时，用户的电子邮件地址会呗发送到服务器，以生成该电子邮件地址的唯一CUID。

为注册的用户设置感谢页面：

```html Markup
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        // Using the fetch API to send the user email to the server
        // and get the unique user id in return	
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                   res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }  </script> 
     </head> 
     <body> 
        <h1>Thank You for Signing Up!</h1> 
     </body> 
</html>
```

该代码使用fetch API将邮箱发送至服务器。假设服务器在注册时为用户生成唯一CUID，将电子邮件地址发送到服务器的目的是为了接收唯一的CUID。服务器返回的CUID作为setCustomerUserId()的参数传递给AppsFlyer。。

</Tab>

<Tab title="谷歌标签管理器">

1. 注册页面示例：

   ```html Markup
   <html>
   <head>
       <script>
            // Google Tag Manager loads the Web SDK
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({
                   'gtm.start':
                       new Date().getTime(), event: 'gtm.js'
               }); var f = d.getElementsByTagName(s)[0],
                   j = d.createElement(s), dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true; j.src =
                       'https://www.googletagmanager.com/gtm.js?id=' + i + dl; f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');

       // This function stores the user email to be sent to the server after the user reaches the thank you page
       // the response from the server is a unique CUID that should be used in the web SDK setCustomerUserId method
           function storeUserEmail (){
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
   </head>
   <body>
       <h1>Sign Up</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Name</label>
               <input type="text" name="name" id="name"></div>
           <br />
           <div> <label>Email</label>
               <input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
   </body>
   </html>
   ```

   该代码展示了一个简单的注册表单。表单提交时，用户邮箱会保存到localStorage。当用户到达感谢页面时，用户的电子邮件地址会发送到服务器，以获取该电子邮件的唯一CUID。
2. 为注册的用户设置感谢页面：

   ```
   (t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
   t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
   o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
   p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
       </script>
       <script>
           // using the fetch api to send the user email to the server
           // and get the unique user id in return 
           window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
                  res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
           } </script> 
       </head>
       <body> 
               <h1>Thank You for Signing Up!</h1> 
        </body> 
    </html>
   ```

   前述代码示例展示了一个感谢页面，在该页面中通过GTM触发器将用户在注册表单中填写的邮箱发送到服务器。  
   服务器会为用户创建一个唯一的CUID。  
   将电子邮件发送到服务器的目的是为了获取该CUID。  
   服务器返回CUID后，会通过 setCustomerUserId()传递给AppsFlyer。  
   继续按照该流程创建触发条件和标签。
3. 在感谢页面加载后，添加一个新的标签，用于归因订阅。[![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. 给该标签起一个唯一的名称，并选择Custom HTML（自定义HTML）作为标签类型 [![GoogleTag.jpg](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

   ```html
   <script>
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
            res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
   </script>
   ```
5. 展开**高级设置**控件，然后在**标签顺序**控件中确保设置正确，以便在该标签执行后触发转化事件。

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. 为转化标签配置一个触发条件，用来规定该标签在何时触发（在本示例中，触发条件会在 “感谢页面”加载时触发）。

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Tab>
</Tabs>

setCustomerUserId()函数可以在用户流程中的任意阶段调用，例如：用户登录或注册之后。AppsFlyer会使用最近一次发送的CUID来更新该用户，应用于过去或未来的触点和事件。

请在网页端使用与移动端应用（iOS、Android、Unity）中setCustomerUserId函数相同的CUID值。

</Accordion>

<div id="addtional-information" />

## 附加信息

<div id="web-sdk-cookies" />

<Accordion title="Web SDK cookies">

您网站上Web SDK设置或使用的cookies如下表所示：

缩写说明：

* AMP：Accelerated Mobile Pages（加速移动页面）
* CDN：Content Delivery Network（内容分发网络）
* 3PC：Third-party Cookies（第三方Cookie）

| Cookie名称 | 域名 | 有效期 | 使用场景 | 说明 |
| --- | --- | --- | --- | --- |
| afUserid | 您的网站域名 | 395天 | 非AMP | 标识用户在网页加载和导航事件中的身份 |
| AF\_SYNC | 您的网站域名 | 1周 | 非AMP | <ul><li>标记最终用户ID已设置</li><li>用于缩短站点加载时间</li></ul> |
| af\_id | appsflyer.com | 395天 | 非AMP（允许三方Cookie时） | 标识用户在应用启动和导航事件中的身份 |
| af\_id | .onelink.me | 395天 | 非AMP（允许三方Cookie时） | 将横幅交互、OneLink交互或两者与应用启动事件关联。 |
| amp-afUserid | AMP CDN或您的网站域名 | 1年 | AMP页面 |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | 您的网站域名 | 395天 | 存储PBA同意状态。在获得用户同意前阻止SDK运行。默认不设置，仅在配置[同意](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout)拦截时使用。 | 非AMP |

</Accordion>

<div id="release-notes" />

<Accordion title="Web SDK发布说明">

| 日期 | 版本 | 说明 |
| --- | --- | --- |
| 2021-07-01 | 1.0 | [支持丢弃查询参数](/docs/pba-web-sdk-integration-guide#discard-query-params) |
| 2021-06-01 | 1.0 | [支持内容安全策略（CSP）](/docs/pba-web-sdk-integration-guide#implement-a-content-security-policy-csp-policy) |
| 2020-08-31 | 1.0 | [添加选择加入和退出功能](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) |
| 2020-04-16 | 1.0 | customerUserId()函数取代IDENTIFY事件来发送唯一的CUID |
| 2020-07-30 | 1.0 | <ul><li>添加显式启停事件控件</li><li>修改默认初始状态</li></ul> |

</Accordion>

<div id="deprecations" />

<Accordion title="弃用日期">

* 弃用通知用于提前告知某个功能或方法即将停止支持。在正式下线之前，该功能或方法仍然可以正常使用。
* 建议您将弃用通知视为优化代码的契机，提前进行调整。

| 弃用日期 | 终止日期 | 说明 |
| --- | --- | --- |
| 2020-04-16 | 待宣布 | **弃用方法：** 在事件参数customUserId中发送客户用户ID（CUID），事件类型设置为"IDENTIFY"<br /><br />**当前方法:** 使用setCustomerUserId()函数发送 CUID |

</Accordion>

<div data-zendesk-anchors="web-sdk-user-and-integration-guide=web-sdk%E7%94%A8%E6%88%B7%E4%B8%8E%E5%AF%B9%E6%8E%A5%E6%8C%87%E5%8D%97 h_01HFKCMH8HAW5DN4K9H1A5Q2NJ=web-sdk%E7%94%A8%E6%88%B7%E4%B8%8E%E5%AF%B9%E6%8E%A5%E6%8C%87%E5%8D%97 step-2-select-a-code-snippet=%E9%80%89%E6%8B%A9%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5 h_01KP11XJV8RDV378GMFF0DVZ8V=%E9%80%89%E6%8B%A9%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5 h_01KP3CJBZWJF8X46W2BBCS9ZVX=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA standard=%E6%A0%87%E5%87%86web-sdk h_01KP11XJV8MN64YV17D1M0T5B9=%E6%A0%87%E5%87%86web-sdk h_01KP3CJBZWK17M58W9M2EP8VC3=standard-without-smart-banners h_01KP3CJBZWKW1K9P9V1XGYM5ED=standard-with-smart-banners advanced-sdk-verification=%E9%AB%98%E7%BA%A7sdk%E9%AA%8C%E8%AF%81 h_01KP11XJV8ZGF4SDXJH6FKX18E=%E9%AB%98%E7%BA%A7sdk%E9%AA%8C%E8%AF%81 h_01KP3CJBZWP7HDJ0GE2DF3TTE3=advanced-verification-without-smart-banners h_01KP3CJBZWJWS9H0XVHQFF758B=advanced-verification-with-smart-banners integrating-the-web-sdk-into-the-website=%E5%9C%A8%E7%BD%91%E7%AB%99%E4%B8%AD%E5%AF%B9%E6%8E%A5web-sdk h_01HFKCMH8HCDNGFJEN32BNA9F2=%E5%9C%A8%E7%BD%91%E7%AB%99%E4%B8%AD%E5%AF%B9%E6%8E%A5web-sdk h_01HFKCMH8HVTJX37PD22ZFV0AY=installation-and-integration considerations-and-actions-required=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9%E4%B8%8E%E6%93%8D%E4%BD%9C%E8%A6%81%E6%B1%82 h_01HFKCMH8H0JBGD2GWY127428R=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9%E4%B8%8E%E6%93%8D%E4%BD%9C%E8%A6%81%E6%B1%82 javascript-code-snippet=%E5%B5%8C%E5%85%A5javascript%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5 h_01HFKCMH8HC064MHGH8D66QCYK=%E5%B5%8C%E5%85%A5javascript%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5 to-install-the-web-sdk-without-smart-banners=%E5%A6%82%E9%9C%80%E5%9C%A8%E4%B8%8D%E4%BD%BF%E7%94%A8%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85%E7%9A%84%E6%83%85%E5%86%B5%E4%B8%8B%E5%AE%89%E8%A3%85web-sdk h_01HFKCMH8HST7G880G44WXXXB6=%E5%A6%82%E9%9C%80%E5%9C%A8%E4%B8%8D%E4%BD%BF%E7%94%A8%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85%E7%9A%84%E6%83%85%E5%86%B5%E4%B8%8B%E5%AE%89%E8%A3%85web-sdk to-implement-the-web-sdk-with-smart-banners=%E5%A6%82%E9%9C%80%E5%9C%A8%E4%BD%BF%E7%94%A8%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85%E7%9A%84%E6%83%85%E5%86%B5%E4%B8%8B%E5%AE%89%E8%A3%85web-sdk h_01HFKCMH8HX4SQP6YCBHJH4AX5=%E5%A6%82%E9%9C%80%E5%9C%A8%E4%BD%BF%E7%94%A8%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85%E7%9A%84%E6%83%85%E5%86%B5%E4%B8%8B%E5%AE%89%E8%A3%85web-sdk h_01HFKCMH8JMMPMHFR4399QPRJV=create-a-property-in-adobe-experience-cloud h_01HFKCMH8J8WVHP7RZ2ENHGY9V=add-the-web-sdk-to-the-adobe-launch-property h_01HFKCMH8J2MAXJ3YVHJ2AJHWQ=add-the-adobe-launch-tag-to-the-website h_01HFKCMH8JWE1Q2749N54MAYRT=publish-the-adobe-launch-environment h_01HFKCMH8JFQQG0BEQ5CATGQ2P=ensure-that-the-sdk-is-working h_01HFKCMH8JCHH5WB5XRC8029DE=sending-events-optinoptout sdk-initial-state-setting=sdk%E5%88%9D%E5%A7%8B%E7%8A%B6%E6%80%81%E8%AE%BE%E7%BD%AE h_01HFKCMH8JSJR95Y9KNANABBKR=sdk%E5%88%9D%E5%A7%8B%E7%8A%B6%E6%80%81%E8%AE%BE%E7%BD%AE explicit-control=%E6%98%BE%E5%BC%8F%E6%8E%A7%E5%88%B6 h_01HFKCMH8JG2C43P8QZ0SKZCBB=%E6%98%BE%E5%BC%8F%E6%8E%A7%E5%88%B6 h_01HFKCMH8J9XDX87ES4F5WW4GJ=implement-a-content-security-policy-csp-policy content-security-policy-csp=%E5%86%85%E5%AE%B9%E5%AE%89%E5%85%A8%E7%AD%96%E7%95%A5csp h_01KGJCGCQ0QB7NK6YNZT5XJVJY=%E5%86%85%E5%AE%B9%E5%AE%89%E5%85%A8%E7%AD%96%E7%95%A5csp advanced-sdk-verification-with-csp-nonce-snippets=%E5%B8%A6%E6%9C%89csp-nonce%E7%89%87%E6%AE%B5%E7%9A%84%E9%AB%98%E7%BA%A7sdk%E9%AA%8C%E8%AF%81 h_01KP11XJV88YB2NSBZJTX9K7ZQ=%E5%B8%A6%E6%9C%89csp-nonce%E7%89%87%E6%AE%B5%E7%9A%84%E9%AB%98%E7%BA%A7sdk%E9%AA%8C%E8%AF%81 h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners h_01HFKCMH8JG40DT9NHXG6TPMJ1=discard-query-params query-discard-options=%E6%9F%A5%E8%AF%A2%E5%8F%82%E6%95%B0%E4%B8%A2%E5%BC%83%E9%80%89%E9%A1%B9 h_01HFKCMH8JYSV81BEY5XQRZ24Y=%E6%9F%A5%E8%AF%A2%E5%8F%82%E6%95%B0%E4%B8%A2%E5%BC%83%E9%80%89%E9%A1%B9 principles-of-event-recording=%E4%BA%8B%E4%BB%B6%E8%AE%B0%E5%BD%95%E5%8E%9F%E5%88%99 h_01HFKCMH8JZCKH1JPTGBVJ3QP4=%E4%BA%8B%E4%BB%B6%E8%AE%B0%E5%BD%95%E5%8E%9F%E5%88%99 h_01HFKCMH8JEDEDC48AH5A2797D=conversion-and-standard-events conversion-events=%E8%BD%AC%E5%8C%96%E4%BA%8B%E4%BB%B6 h_01HFKCMH8JYYB7HG2W8XQ7RFPD=%E8%BD%AC%E5%8C%96%E4%BA%8B%E4%BB%B6 standard-events=%E6%A0%87%E5%87%86%E4%BA%8B%E4%BB%B6 h_01HFKCMH8JQHSJF3T8SF4ZES7W=%E6%A0%87%E5%87%86%E4%BA%8B%E4%BB%B6 recording-events=%E4%BA%8B%E4%BB%B6%E8%AE%B0%E5%BD%95 h_01HFKCMH8J79VD5BX96ANAYAFQ=%E4%BA%8B%E4%BB%B6%E8%AE%B0%E5%BD%95 h_01HFKCMH8JPJZQ81TYZX5PDF91=identifying-users-using-customer-user-id-cuid h_01HFKCMH8JYPNHJGYVRK1SZFYB=web-sdk-event-parameters h_01HFKCMH8J35YT2448PX8ZRM5P=recording-event-scenarios online-store=%E7%94%B5%E5%95%86%E7%BD%91%E7%AB%99 h_01HFKCMH8JQS3CTE6NTZY4G8ZR=%E7%94%B5%E5%95%86%E7%BD%91%E7%AB%99 h_01HFKCMH8J1EDH3XM5V4ECYCPS=ensuring-that-events-are-sent examples=%E7%A4%BA%E4%BE%8B h_01HFKCMH8J4KQSZ489TMDEN426=%E7%A4%BA%E4%BE%8B h_01HFKCMH8JAK25DZ1BZDFS4THD=recording-events::f1e16eae h_01HFKCMH8J4XNY5B9MKAS81T6Z=setting-customer-user-id-after-signup addtional-information=%E9%99%84%E5%8A%A0%E4%BF%A1%E6%81%AF h_01HFKCMH8KJDZ0A15RMQ8BDMDH=%E9%99%84%E5%8A%A0%E4%BF%A1%E6%81%AF h_01HFKCMH8KV3QD9CPBSVWM3EVE=web-sdk-cookies h_01HFKCMH8KGJTE7BMK4VSQJF33=release-notes h_01HFKCMH8KP1SHA21JZA5PTZXG=deprecations" />

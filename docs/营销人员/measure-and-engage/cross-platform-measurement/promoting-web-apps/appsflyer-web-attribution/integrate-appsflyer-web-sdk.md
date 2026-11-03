---
title: 对接AppsFlyer Web SDK
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-03T15:23:52Z'
  edited_at: '2026-10-14T10:01:21Z'
  id: 43485611331473
  locale: zh-cn
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/zh-cn/articles/43485611331473
---
> **概览：** 在网站中安装AppsFlyer Web SDK（也称为Pixel），向AppsFlyer上报用户访问和事件，并设置长期有效的客户用户ID（CUID），统一跨平台用户旅程。

## 概览

Web SDK可记录访客与网站的互动情况，并将相关信息发送至AppsFlyer。Web SDK是一个40–60KB的插件模块，可将用户访问和在网站上的操作上报至AppsFlyer平台。

请按照以下步骤完成Web SDK对接，包括安装、验证和隐私控制。

1. [获取密钥。](#1获取密钥)获取Web SDK ID（也称为Web Dev Key）。
2. [选择代码片段。](#2选择代码片段)根据对接类型和安全要求选择相应的代码片段。
3. [部署Web SDK。](#3部署代码片段)使用原生代码片段、Google Tag Manager或Adobe Launch Tag Manager部署SDK。
4. [确认SDK正常运行。](#2确认sdk正常运行)在浏览器开发者工具中检查网络调用，确认SDK能够发送请求。
5. [设置和记录事件。](#3设置和记录事件)使用原生JavaScript或Google Tag Manager定义自定义事件，并在页面加载或用户互动时发送事件。
6. [设置客户用户ID。](#4设置客户用户id)设置长期有效的CUID，将网页端与其他平台的用户活跃数据统一关联。
7. [管理隐私。](#5管理隐私)控制用户是否参与效果衡量，并配置安全和数据过滤功能（内容安全策略和丢弃查询参数）。
8. [Web SDK Cookie说明。](#web-sdk-cookie说明)查看Web SDK设置或使用的Cookie，包括用途、有效期和作用域。

## 1获取密钥

**获取Web SDK ID（也称为Web Dev Key）：**

1. 在AppsFlyer顶部菜单中，打开**应用设置**。
2. 在页面顶部的应用选择器中，选择您的网页端应用（即以「website-」为前缀的网站域名）。
3. 在**SDK身份验证**下，复制**Web SDK ID**。

**获取智能横幅密钥（如有需要）：**

1. 在AppsFlyer侧边菜单中，打开**互动**>**Web to App**>**智能横幅**。
2. 复制所需的智能横幅密钥。

## 2选择代码片段

根据对接类型和安全要求选择相应的代码片段。有以下两种方案：

* [标准Web SDK](#标准web-sdk)：标准对接方案。
* [高级SDK验证](#高级sdk验证)：增强型对接方案，可为Web SDK提供供应链防护。使用该方案可加强安全防护，防范CDN遭入侵、DNS劫持和中间人攻击。

> 🚧 **重要！**
>
> 如果要从标准Web SDK迁移至高级SDK验证，请使用新代码片段替换现有代码片段。不要在现有代码片段的基础上再添加新代码片段。

### 标准Web SDK

使用此代码片段部署标准Web SDK对接方案。在所有需要加载SDK的页面中，将代码片段粘贴到标签内靠近开头的位置。

<div id="standard-without-smart-banners" />

<Accordion title="不使用智能横幅">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  // Replace WEB_DEV_KEY with your Web SDK ID
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
</script>
```

</Accordion>

<div id="standard-with-smart-banners" />

<Accordion title="使用智能横幅">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  // Replace WEB_DEV_KEY with your Web SDK ID
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba,banners&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
  AF('banners', 'showBanner');
</script>
```

</Accordion>

### 高级SDK验证

高级SDK验证可为Web SDK提供供应链防护。该方案可确保用户浏览器中运行的代码与AppsFlyer发布的代码完全一致。SDK源代码与标准对接方案完全相同，区别仅在于代码加载和验证机制。

高级SDK验证：

* 加强安全防护，防范CDN遭入侵、DNS劫持和中间人攻击。
* SDK加载时间延长约250毫秒。

高级SDK验证为可选功能。标准对接方案仍受到全面支持，也是第三方分析追踪代码的行业标准。高级SDK验证可在此标准的基础上再提供一层防护。

如果您的网站使用nonce实施内容安全策略（CSP），请参阅「管理隐私」部分的[内容安全策略（CSP）](#内容安全策略csp)，了解此代码片段支持nonce的扩展版本。

<div id="advanced-verification-without-smart-banners" />

<Accordion title="不使用智能横幅">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
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

<Accordion title="使用智能横幅">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
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

## 3部署代码片段

使用以下任一方式部署您在第2步中选择的代码片段。每次加载页面时，只加载一次SDK。

<div id="option-a-add-directly-to-your-website" />

<Accordion title="方式A：直接添加到您的网站">

在所有页面中执行以下操作：

1. 在第2步的代码片段中，将`WEB_DEV_KEY`替换为您的Web SDK ID（如适用，还需替换`YOUR_BANNER_KEY`）。
2. 将代码片段粘贴到网站标签内靠近开头的位置。

</Accordion>

<div id="option-b-deploy-via-google-tag-manager" />

<Accordion title="方式B：通过Google Tag Manager（GTM）部署">

使用GTM优先级设置，让SDK在页面加载后尽快加载；每次加载页面时，只加载一次SDK。

1. 打开Google Tag Manager。
2. 新建AppsFlyer Web SDK代码。
3. 选择**自定义HTML**代码类型。
4. 为代码指定一个清晰易懂的名称。
5. 将第2步中的代码片段粘贴到**代码配置**中。
6. 点击**保存**。
7. 添加触发器：
   * 针对所有网页：
     1. 点击**添加触发器**。
     2. 选择**所有网页**。
     3. 点击**保存**。
     4. 输入代码名称，然后点击**保存**。
   * 针对特定网页：
     1. 点击**保存代码**。
     2. 在GTM主窗口中，选择**触发器**。点击**新建**。
     3. 点击铅笔图标。
     4. 选择**网页浏览**触发器类型。
     5. 选择**某些网页浏览**。
     6. 根据需要设置网页和触发条件。
     7. 点击**保存**。
     8. 将触发器与AppsFlyer Web SDK代码关联：
        1. 在**GTM**主窗口中，选择**代码**。
        2. 选择之前创建的代码。
        3. 在触发条件面板中，点击铅笔图标。
        4. 选择之前创建的网页浏览触发器。
        5. 点击**保存**。

> 📘 **注意**
>
> GTM自定义模板不支持高级SDK验证，因为其沙盒环境不允许设置验证所需的`integrity`属性。请改用**自定义HTML**代码类型。

</Accordion>

<div id="option-c-deploy-via-adobe-launch-tag-manager" />

<Accordion title="方式C：通过Adobe Launch Tag Manager部署">

#### 在Adobe Experience Cloud中创建属性

1. 打开Adobe Experience Cloud>Launch。
2. 在Adobe Experience Cloud Launch中，点击**转到Launch**。
3. 点击**新建属性**。
4. 输入属性名称。
5. 在**平台**下，选择**网页端**。
6. 输入网站域名。
7. 点击**保存**。

#### 将代码片段添加到Adobe Launch属性

1. 在**我的网页端属性**页面中，选择**规则**选项卡。
2. 输入规则名称。建议名称：加载Web SDK。
3. 在**如果**部分的**事件**下，点击**添加**。
   * 在**事件类型**下，选择**Core–DOM已就绪**。
   * 点击**保留更改**。
4. 在**然后**部分的**操作**下，点击**添加**。
   * 在**操作类型**下，选择**自定义代码**。
   * 选择**JavaScript**>**打开编辑器**，然后粘贴第2步中的代码片段（不要包含任何外层封装代码行）。
   * 点击**保留更改**，关闭代码编辑器。
5. 点击**保存**。

#### 将Adobe Launch标签添加到网站

1. 在**我的网页端属性**页面中，选择**环境**选项卡。
2. 找到要发布的环境所在行（开发或生产环境）。
3. 在**安装**列中，点击相应行的方框图标。
4. 在**网页端安装说明**对话框中，复制脚本代码片段并关闭对话框。
5. 将代码片段粘贴到网站的head部分。

#### 发布Adobe Launch环境

1. 在**我的网页端属性**页面中，前往**发布**选项卡。
2. 在**开发**部分下，点击**添加新库**。
   * 输入库名称并选择环境。
   * 在**资源更改**下，点击**添加资源**。
   * 点击**规则**>**加载Web SDK**>**最新**>**选择并创建新修订版本**。
   * 点击**保存**。
3. 在**开发**部分下：
   * 点击新建库旁的操作菜单（三点图标），然后选择**生成到开发环境**。
   * 再次点击操作菜单，然后选择**提交以供审批**。
4. 在**已提交**部分下：
   * 点击操作菜单，然后选择**生成到暂存环境**。
   * 再次点击操作菜单，然后选择**批准发布**。
5. 在**已批准**部分下：
   * 点击操作菜单，然后选择**生成并发布到生产环境**。

</Accordion>

## 2确认SDK正常运行

安装后，在浏览器开发者工具中检查网络请求，确认SDK能够发送请求。

[<Image alt="开发者工具截图" src="https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png" width="1015px" />](https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png)

**按照以下步骤确认SDK是否正常运行：**

1. 打开网站。
2. 打开浏览器开发者工具。
3. 前往(A)**网络**选项卡。
4. 刷新页面。
5. 按(B)`appsflyer`筛选。可能会显示两个请求：
   * **SDK加载器**——请求URL以`https://websdk.appsflyersdk.com`开头。这表示SDK脚本已正确加载。
   * **事件数据**——请求URL以`https://wa.appsflyer.com/events`开头。这表示SDK正在向AppsFlyer发送事件数据。
6. 选择(C)**events**请求（即`wa.appsflyer.com`调用）。
7. 在「标头」下，确认(D)以下信息：
   * 请求URL以`https://wa.appsflyer.com/events?site-id=`开头。
   * `site_id`查询参数=`WEB_SDK_KEY`。
   * 状态码为200。
8. 确认`site_id`与AppsFlyer顶部菜单中**我的应用**下的`WEB_SDK_KEY`一致。
9. 确认SDK只加载一次。多次加载SDK可能会导致SDK停止运行。

## 3设置和记录事件

初始化Web SDK后，即可在衡量基本访问数据的基础上，进一步采集具体的用户操作。本节将介绍如何使用**原生JavaScript**或**Google Tag Manager**定义和记录购买、注册等自定义事件。

<div id="set-events" />

<Accordion title="设置事件">

事件是网页端效果衡量的基础，用于表示对您业务具有价值的具体用户操作。要记录这些互动，需为每个事件定义相应的逻辑和参数，并正确地将收入、自定义元数据等事件参数传递至AppsFlyer平台。

**事件示例（包含相关收入的购买事件）**

```javascript
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

<div id="web-sdk-event-parameters-table" />

<Accordion title="Web SDK事件参数表">

| 参数名称 | 必填 | 说明 |
| --- | --- | --- |
| `eventType` | 是 | 事件类型。格式：字符串。此参数必须始终填入`EVENT`。示例：`eventType: "EVENT"` |
| `eventName` | 是 | 事件名称。格式：字符串。示例：Purchase、Subscription |
| `eventRevenue` | 否 | 分配给转化事件的收入。格式：浮点数 |
| `eventRevenueCurrency` | 否 | 收入币种。3位ISO 4217货币代码。默认值：USD。格式：字符串 |
| `eventValue` | 否 | 描述事件的事件参数映射。使用此参数可发送产品SKU、商品明细价格等富应用内事件数据。格式：JSON。示例：`{"sku": "ABC123", "color": "blue", "unit_price": 3.99, "currency": "USD"}`限制：1000个字符。请勿超过此限制，否则超出部分将被截断。 |

</Accordion>

</Accordion>

<div id="record-events-on-page-load" />

<Accordion title="页面加载时记录事件">

对于最终跳转至**感谢**页面或确认页面的转化，通常采用这种方式记录事件。

您可以通过以下任一方式实现该触发器：在**原生JavaScript**中添加窗口加载方法，或在**Google Tag Manager**中配置网页浏览触发器。

> ❗️ **警告**
>
> 以下代码示例仅用于说明。**请勿直接使用此代码**；请根据网站的具体结构进行调整。

<div id="example-record-event-via-af-web-sdk" />

<Accordion title="示例：通过AF Web SDK记录事件">

这种方式适合记录通过页面跳转完成的转化，例如用户订阅邮件简报后进入感谢页面。

**使用场景：** 用户完成邮件简报订阅后，页面跳转至确认页面。您希望确认页面显示后立即记录subscription事件。

**原生页面加载示例：**

```javascript
window.onload = function(){
  AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion'}, eventName: 'subscription'});
}
```

**运行方式：**

1. 页面会加载必要内容。
2. 窗口完全加载后（`window.onload`），脚本会自动调用`AF()`方法。
3. **subscription**事件及其相关元数据（category和label）会直接发送至AppsFlyer。

</Accordion>

<div id="example-record-event-via-gtm" />

<Accordion title="示例：通过GTM记录事件">

这种方式会在「感谢」页面加载时触发代码，从而记录邮件简报订阅等成功转化。

#### 1设置「感谢」页面

以下HTML结构先加载GTM，再由GTM加载Web SDK。此外，该结构还演示了如何通过函数或`localStorage`向GTM提供数据。

```html
<html>
<head>
    <script>
        // Google Tag Manager loads the Web SDK
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-XXXX');
    </script>
    <script>
        function getResponseFromServer() {
            return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
        }
        localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
    </script>
</head>
<body>
    <h1>Thank You for Subscribing to Our Newsletter</h1>
</body>
</html>
```

#### 2配置GTM代码

1. 在GTM中新建代码，并选择**自定义HTML**代码类型。
2. 输入一个易于区分的名称（例如「AF Subscription Event」）。
3. 将以下脚本粘贴到HTML文本区域：

   ```javascript
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'});
   ```
4. 展开**高级设置**>**代码排序**。将此代码配置为在Web SDK主初始化代码触发后运行。
5. 为此代码设置触发器，使其在「感谢」页面发生**网页浏览**时触发。

</Accordion>

</Accordion>

<div id="record-events-on-user-interaction" />

<Accordion title="用户互动时记录事件">

使用这种方式追踪无需重新加载页面的操作（点击按钮、下载、添加到购物车）。

通常可通过以下方式处理此类互动：为**原生HTML元素**绑定点击监听器，或使用**Google Tag Manager**变量，根据特定元素ID或CSS选择器识别并衡量互动。

> ❗️ **警告**
>
> 以下代码示例仅用于说明。**请勿直接使用此代码**；请根据网站的具体结构进行调整。

<div id="example-record-event-via-af-web-sdk-interaction" />

<Accordion title="示例：通过AF Web SDK记录事件">

使用此方法追踪用户在页面上的具体操作，例如点击**结账**或**下载**按钮。

**使用场景：** 您经营一个电商网站，希望用户点击购物车中的**结账**按钮时，立即采集**checkout**事件。

**原生用户互动示例：**

```html
<html>
<head>
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
    <button id='checkout'>Checkout</button>
</body>
</html>
```

**运行方式：**

1. 页面加载时，脚本会为ID为`checkout`的元素添加**click**事件监听器。
2. 用户点击按钮后，系统会触发回调函数。
3. 该函数可以获取相关数据（例如从`localStorage`中获取），并传递至`AF()`方法。
4. 随后，SDK会将**checkout**事件发送至AppsFlyer平台。

</Accordion>

<div id="example-record-event-via-gtm-interaction" />

<Accordion title="示例：通过GTM记录事件">

此方法使用GTM的内置变量和触发器，采集点击**结账**按钮等具体操作。

#### 1设置结账页面

```html
<html>
<head>
    <script>
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-XXXX');
    </script>
</head>
<body>
    <h1>Shopping Cart</h1>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

#### 2配置GTM变量和触发器

1. 在GTM中，点击**变量**>**配置**，然后在内置变量列表中启用**点击元素**。
2. 新建一个用户定义的变量（类型：**所有元素**）。
3. 新建**触发器**：
   * 触发器类型：**点击–所有元素**。
   * 此触发器的触发条件：**某些点击**。
   * 条件：**点击元素**与CSS选择器`#checkout`匹配。

#### 3创建互动代码

1. 为结账操作新建**自定义HTML**代码。
2. 粘贴互动脚本：

   ```html
   <script>
     AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
   </script>
   ```
3. 为其分配上一步创建的「Checkout Click」触发器。

</Accordion>

</Accordion>

<div id="event-implementation-best-practices" />

<Accordion title="事件实施最佳实践">

为保证数据准确并成功发送，请注意以下技术要求：

* **加载顺序：** 调用任何事件前，Web SDK函数代码必须已在页面作用域中完全加载。
* **数据格式：** 事件值中不得包含特殊字符。例如，收入应使用数值，不要包含货币符号（使用`10.50`，而非`$10.50`）。
* **字符串长度限制：** 尽量缩短`event_value`字符串；超过4000个字符的值将被截断。

</Accordion>

## 4设置客户用户ID

完成事件衡量配置后，使用`setCustomerUserId`设置长期有效的身份标识，将网页端活跃数据与移动端、PC和CTV等其他平台关联，统一查看用户的跨平台旅程。

**主要规则**

* **一致性：** CUID值应与移动应用配置中使用的值一致（有关移动端`setCustomerUserId`，请参阅<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk">iOS</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-android-sdk#setting-the-customer-user-id">Android</Anchor>和<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id">Unity</Anchor>）。
* **设置时机：** 您可以在任意阶段发送CUID，例如用户登录或注册后。获取CUID后，应尽早完成设置。通常需要等到用户登录或注册并表明身份后，才能获取CUID。
* **语法：** 以字符串形式发送该值（使用引号括起）。**示例：**`AF('pba', 'setCustomerUserId', '663274')`
* **隐私：** 请勿包含邮箱地址或电话号码等个人身份信息（PII）。

<div id="example-setting-cuid-after-signup-native" />

<Accordion title="示例：注册后设置CUID（原生代码）">

以下示例中的代码仅供参考。请勿直接使用此代码。如果不确定如何使用，请咨询网站开发人员。

前提条件：发送事件前，页面已加载Web SDK；请勿重复加载。

用户场景：

* 用户在网站中注册。
* 网站代码收集用户信息并发送至服务器。
* 服务器为用户生成唯一CUID。
* 用户进入注册完成后的感谢页面后，网站会向服务器查询新CUID。
* 根据服务器返回的响应，使用Web SDK的`setCustomerUserId()`方法设置AppsFlyer CUID。

#### 注册表单示例

以下代码是一个简单的注册表单。提交表单后，邮箱地址会存储在`localStorage`中。用户进入感谢页面后，系统会将其邮箱地址发送至服务器，以获取该邮箱地址对应的唯一CUID。

```html
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
        function storeUserEmail() {
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Sign Up</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Name</label><input type="text" name="name" id="name"></div>
        <br/>
        <div><label>Email</label><input type="email" name="email" id="email"></div>
        <br/>
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

#### 感谢页面示例

该代码使用Fetch API。代码会将用户输入的邮箱地址发送至服务器。假设服务器会在用户注册时创建用户并生成唯一CUID，将邮箱地址发送至服务器后，即可获取该CUID。服务器返回唯一CUID，该值随后会通过`setCustomerUserId`方法传递。

```html
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
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }
    </script>
</head>
<body>
    <h1>Thank You for Signing Up!</h1>
</body>
</html>
```

</Accordion>

<div id="example-setting-cuid-after-signup-google-tag-manager" />

<Accordion title="示例：注册后设置CUID（Google Tag Manager）">

1. 设置注册页面。

   以下代码示例是一个简单的注册表单。提交表单后，邮箱地址会存储在`localStorage`中。用户进入感谢页面后，系统会将其邮箱地址发送至服务器，以获取该邮箱地址对应的唯一CUID。

   ```html
   <html>
   <head>
       <script>
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({ 'gtm.start': new Date().getTime(), event: 'gtm.js' });
               var f = d.getElementsByTagName(s)[0], j = d.createElement(s),
                   dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true;
               j.src = 'https://www.googletagmanager.com/gtm.js?id=' + i + dl;
               f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');
           function storeUserEmail() {
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
   </head>
   <body>
       <h1>Sign Up</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Name</label><input type="text" name="name" id="name"></div>
           <br />
           <div><label>Email</label><input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
   </body>
   </html>
   ```
2. 为完成注册的用户设置感谢页面。以下代码用于感谢页面，其中的GTM触发器会将用户在注册表单中填写的邮箱地址发送至服务器。假设服务器会在用户注册时创建用户并生成唯一CUID，将邮箱地址发送至服务器后，即可获取该CUID。服务器返回唯一CUID，该值随后会通过`setCustomerUserId()`方法发送。

   ```html
   <script>
       window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
               res.text().then(function (id) {
                   console.log(id);
                   AF('pba', 'setCustomerUserId', id);
               });
           });
       }
   </script>
   ```
3. 添加一个新代码，用于在感谢页面加载后归因订阅事件。

   [![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. 为代码指定一个易于区分的名称，并选择**自定义HTML**代码类型。

   [![](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

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
5. 展开文本区域下方的**高级设置**和**代码排序**，并将其配置为在此代码执行后触发转化。

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. 为转化代码设置触发器，指定转化代码的触发时机（以下示例会在「感谢」页面加载时触发）。

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Accordion>

## 5管理隐私

完成事件衡量配置后，您可能还需要根据组织或地区标准设置特定的安全与隐私限制。

<div id="opt-in-or-opt-out-of-sending-events" />

<Accordion title="选择是否发送事件">

您可以通过以下两种方式控制效果衡量：

#### SDK初始状态设置（在代码片段中）

用于决定网页首次加载时，SDK是立即发送事件，还是等到您明确发出指令后再开始发送。此设置在网页端代码片段中定义。

* 发送事件：`{pba: {webAppId: "...", measurementStatus:true}}`
* 不发送事件：`{pba: {webAppId: "...", measurementStatus:false}}`

> 📘 **注意**
>
> 如果`measurementStatus`为空或值为`NULL`，AppsFlyer会按`measurementStatus:true`处理。

#### 显式控制

显式控制的优先级高于初始状态设置，并通过第一方Cookie持续保存设置：

* Cookie设置在您的网站域名下。
* Cookie会在Web SDK或浏览器设定的期限后过期。
* Cookie始终受浏览器Cookie设置限制。

**命令**

* 开始发送事件（选择发送）：`window.AF_SDK.PLUGINS.PBA.enableMeasurement()`
* 停止发送事件（选择不发送）：`window.AF_SDK.PLUGINS.PBA.disableMeasurement()`

</Accordion>

<div id="secure-and-filter-data" />

<Accordion title="数据安全与过滤">

如果网站需要遵循严格的安全或数据隐私协议，请使用以下机制配置Web SDK与运行环境及数据的交互方式。

#### 内容安全策略（CSP）

如果网站要求通过CSP保护JavaScript，Web SDK可根据您的CSP配置和第2步所选的代码片段采用以下两种方案。

* **使用self的CSP**：将`https://websdk.appsflyersdk.com`添加到`script-src`允许列表中。标准Web SDK和高级SDK验证均支持这种方式。
* **使用nonce的CSP**：如果您的策略使用`script-src 'nonce-...'`，请使用下方支持nonce的高级SDK验证扩展版本。该版本会将nonce传递给验证流程所需的全部3个脚本标签。将`{{CSP_NONCE}}`替换为服务器针对每个请求生成的nonce值。

下表列出了与nonce扩展版本兼容的CSP策略。

| 策略 | 是否支持 | 说明 |
| --- | --- | --- |
| `script-src 'self'` | 否 | 不允许外部CDN源；内联脚本也会被阻止。 |
| `script-src 'self' https://websdk.appsflyersdk.com` | 部分支持 | 允许加载器和SDK，但内联设置脚本仍会被阻止。 |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | 是 | nonce涵盖内联脚本和加载器；加载器会将nonce转发至SDK脚本标签。 |
| `script-src 'nonce-...' 'strict-dynamic'` | 是（推荐） | nonce涵盖内联脚本和加载器；`strict-dynamic`会将信任传递给动态注入的SDK脚本标签。无需将CDN源添加到允许列表。 |

CSP策略兼容性

#### 使用CSP nonce的高级SDK验证代码片段

<div id="nonce-without-smart-banners" />

<Accordion title="不使用智能横幅">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
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

<Accordion title="使用智能横幅">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
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

#### 丢弃查询参数

如果URL查询参数包含敏感信息，可让AppsFlyer丢弃URL、引荐来源网址和`header_referer`中的查询参数。

* **丢弃所有**查询参数：附加`af_url=true`
* **丢弃特定**查询参数：使用`af_url_mask=param`（使用`;`分隔多个参数）

示例：

* 原始值：`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`
* 结果：`param1=value1&af_url_mask=param2;param3`

</Accordion>

## Web SDK Cookie说明

Web SDK会设置或使用以下Cookie：

| Cookie名称 | 域名 | 有效期 | 使用场景 | 说明 |
| --- | --- | --- | --- | --- |
| afUserid | 您的网站域名 | 395天 | 非AMP页面 | 用于在网页加载和导航事件中识别用户。 |
| AF\\_SYNC | 您的网站域名 | 1周 | 非AMP页面 | 表示已设置最终用户标识符。用于缩短网站加载时间。 |
| af\\_id | <Anchor target="_blank" href="http://appsflyer.com/">appsflyer.com</Anchor> | 395天 | 允许第三方Cookie的非AMP页面 | 用于在应用启动和导航事件中识别用户。 |
| af\\_id | <Anchor target="_blank" href="http://onelink.me/">onelink.me</Anchor> | 395天 | 允许第三方Cookie的非AMP页面 | 将链接横幅互动、OneLink互动或两者与应用启动事件关联。 |
| amp-afUserid | AMP CDN或您的网站域名 | 1年 | AMP页面 |  |
| AF\\_DEFAULT\\_MEASUREMENT\\_STATUS | 您的网站域名 | 395天 | 非AMP页面 | 存储用户同意状态。在用户同意前阻止SDK运行。默认不设置。仅在配置<Anchor target="_blank" href="/marketers/zh/docs/pba-web-sdk-integration-guide#sending-events-optinoptout">用户同意控制</Anchor>后使用。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01KGJCGCPZDJ446QHW80H9Z4C3=%E6%A6%82%E8%A7%88 step-1-obtain-your-keys=1%E8%8E%B7%E5%8F%96%E5%AF%86%E9%92%A5 h_01KP11XJV8B56W7FK2KAAFH0NE=1%E8%8E%B7%E5%8F%96%E5%AF%86%E9%92%A5 step-2-select-a-code-snippet=2%E9%80%89%E6%8B%A9%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5 h_01KP11XJV8RDV378GMFF0DVZ8V=2%E9%80%89%E6%8B%A9%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5 h_01KP3CJBZWJF8X46W2BBCS9ZVX=%E9%87%8D%E8%A6%81 standard=%E6%A0%87%E5%87%86web-sdk h_01KP11XJV8MN64YV17D1M0T5B9=%E6%A0%87%E5%87%86web-sdk h_01KP3CJBZWK17M58W9M2EP8VC3=standard-without-smart-banners h_01KP3CJBZWKW1K9P9V1XGYM5ED=standard-with-smart-banners advanced-sdk-verification=%E9%AB%98%E7%BA%A7sdk%E9%AA%8C%E8%AF%81 h_01KP11XJV8ZGF4SDXJH6FKX18E=%E9%AB%98%E7%BA%A7sdk%E9%AA%8C%E8%AF%81 h_01KP3CJBZWP7HDJ0GE2DF3TTE3=advanced-verification-without-smart-banners h_01KP3CJBZWJWS9H0XVHQFF758B=advanced-verification-with-smart-banners step-3-deploy-the-snippet=3%E9%83%A8%E7%BD%B2%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5 h_01KP11XJV8JQ5S2BBS18RV2H2R=3%E9%83%A8%E7%BD%B2%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5 h_01KP3CJBZWSKRZBRB66419E3TR=option-a-add-directly-to-your-website h_01KP3CJBZW1PE1VNCV6MSNWT8Q=option-b-deploy-via-google-tag-manager h_01KP3CJBZWWNXX6N5DBJKKGN6M=%E6%B3%A8%E6%84%8F h_01KP3CJBZWF4SW63KA6XCQ3BBD=option-c-deploy-via-adobe-launch-tag-manager create-a-property-in-adobe-experience-cloud=%E5%9C%A8adobe-experience-cloud%E4%B8%AD%E5%88%9B%E5%BB%BA%E5%B1%9E%E6%80%A7 h_01KP11XJV9RWY4TTWACW69YGJH=%E5%9C%A8adobe-experience-cloud%E4%B8%AD%E5%88%9B%E5%BB%BA%E5%B1%9E%E6%80%A7 add-the-snippet-to-the-adobe-launch-property=%E5%B0%86%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5%E6%B7%BB%E5%8A%A0%E5%88%B0adobe-launch%E5%B1%9E%E6%80%A7 h_01KP11XJV9ZHMP9M85S3KG0V6R=%E5%B0%86%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5%E6%B7%BB%E5%8A%A0%E5%88%B0adobe-launch%E5%B1%9E%E6%80%A7 add-the-adobe-launch-tag-to-the-website=%E5%B0%86adobe-launch%E6%A0%87%E7%AD%BE%E6%B7%BB%E5%8A%A0%E5%88%B0%E7%BD%91%E7%AB%99 h_01KP11XJVBV5J9E0HV5DM9HS7B=%E5%B0%86adobe-launch%E6%A0%87%E7%AD%BE%E6%B7%BB%E5%8A%A0%E5%88%B0%E7%BD%91%E7%AB%99 publish-the-adobe-launch-environment=%E5%8F%91%E5%B8%83adobe-launch%E7%8E%AF%E5%A2%83 h_01KP11XJVB0Y4RCBS9QCFBAKRD=%E5%8F%91%E5%B8%83adobe-launch%E7%8E%AF%E5%A2%83 2-make-sure-the-sdk-is-working=2%E7%A1%AE%E8%AE%A4sdk%E6%AD%A3%E5%B8%B8%E8%BF%90%E8%A1%8C h_01KGJCGCPZ38XZAY8SXB48YWBD=2%E7%A1%AE%E8%AE%A4sdk%E6%AD%A3%E5%B8%B8%E8%BF%90%E8%A1%8C 3-set-and-record-events=3%E8%AE%BE%E7%BD%AE%E5%92%8C%E8%AE%B0%E5%BD%95%E4%BA%8B%E4%BB%B6 h_01KGJCGCPZMPX1FH58MVGM9VQS=3%E8%AE%BE%E7%BD%AE%E5%92%8C%E8%AE%B0%E5%BD%95%E4%BA%8B%E4%BB%B6 h_01KP3CJBZXQRMCG9CCH7N1RQ7Y=set-events h_01KP3CJBZXV66CCP4N0482DG1N=web-sdk-event-parameters-table h_01KP3CJBZXEA5SN763P1ZX8EH3=record-events-on-page-load h_01KP3CJBZXHTGFHR9D4KM6S6GH=%E8%AD%A6%E5%91%8A h_01KP3CJBZXB328CABH2QCRXTHX=example-record-event-via-af-web-sdk h_01KP3CJBZXM3WK0JYB6S8P6SMQ=example-record-event-via-gtm 1-set-up-a-thank-you-page=1%E8%AE%BE%E7%BD%AE%E6%84%9F%E8%B0%A2%E9%A1%B5%E9%9D%A2 h_01KGJCGCPZQDP9KVBSE1Z1GT48=1%E8%AE%BE%E7%BD%AE%E6%84%9F%E8%B0%A2%E9%A1%B5%E9%9D%A2 2-configure-the-gtm-tag=2%E9%85%8D%E7%BD%AEgtm%E4%BB%A3%E7%A0%81 h_01KGJCGCPZ2YVRY6VYJ0BTC14N=2%E9%85%8D%E7%BD%AEgtm%E4%BB%A3%E7%A0%81 h_01KP3CJBZXZ2F32FJG9GENBPWW=record-events-on-user-interaction h_01KP3CJBZX6763D546AK5AS1TN=%E8%AD%A6%E5%91%8A-1 h_01KP3CJBZXD6MPTQ0KCPMTM1Y9=example-record-event-via-af-web-sdk-interaction h_01KP3CJBZX53G1HABG3TKN2X6S=example-record-event-via-gtm-interaction 1-set-up-a-checkout-page=1%E8%AE%BE%E7%BD%AE%E7%BB%93%E8%B4%A6%E9%A1%B5%E9%9D%A2 h_01KGJCGCQ0858AAJC82Y2G0GNP=1%E8%AE%BE%E7%BD%AE%E7%BB%93%E8%B4%A6%E9%A1%B5%E9%9D%A2 2-configure-gtm-variables-and-triggers=2%E9%85%8D%E7%BD%AEgtm%E5%8F%98%E9%87%8F%E5%92%8C%E8%A7%A6%E5%8F%91%E5%99%A8 h_01KGJCGCQ0GGYDQBP9CJNM9AXQ=2%E9%85%8D%E7%BD%AEgtm%E5%8F%98%E9%87%8F%E5%92%8C%E8%A7%A6%E5%8F%91%E5%99%A8 3-create-the-interaction-tag=3%E5%88%9B%E5%BB%BA%E4%BA%92%E5%8A%A8%E4%BB%A3%E7%A0%81 h_01KGJCGCQ0EV557QF3CGZ6YB4X=3%E5%88%9B%E5%BB%BA%E4%BA%92%E5%8A%A8%E4%BB%A3%E7%A0%81 h_01KP3CJBZX5K72JC1NK1P1S1S8=event-implementation-best-practices 4-set-customer-user-id=4%E8%AE%BE%E7%BD%AE%E5%AE%A2%E6%88%B7%E7%94%A8%E6%88%B7id h_01KGJCGCQ0RNBW7V5T4PXVXQW1=4%E8%AE%BE%E7%BD%AE%E5%AE%A2%E6%88%B7%E7%94%A8%E6%88%B7id h_01KP3CJBZXXKM662TJP0M5BJAR=example-setting-cuid-after-signup-native a-sign-up-form-example=%E6%B3%A8%E5%86%8C%E8%A1%A8%E5%8D%95%E7%A4%BA%E4%BE%8B h_01KGJCGCQ0M0ESXFMK45PJ3SX9=%E6%B3%A8%E5%86%8C%E8%A1%A8%E5%8D%95%E7%A4%BA%E4%BE%8B a-thank-you-page-example=%E6%84%9F%E8%B0%A2%E9%A1%B5%E9%9D%A2%E7%A4%BA%E4%BE%8B h_01KGJCGCQ0FMKFKM2SWV2794T5=%E6%84%9F%E8%B0%A2%E9%A1%B5%E9%9D%A2%E7%A4%BA%E4%BE%8B h_01KP3CJBZX4BXQSGN70TRJDNX1=example-setting-cuid-after-signup-google-tag-manager 5-manage-privacy=5%E7%AE%A1%E7%90%86%E9%9A%90%E7%A7%81 h_01KGJCGCQ01PQWT44ZWE329DWX=5%E7%AE%A1%E7%90%86%E9%9A%90%E7%A7%81 h_01KP3CJBZXVR16943T16XT82G5=opt-in-or-opt-out-of-sending-events sdk-initial-state-setting-in-the-snippet=sdk%E5%88%9D%E5%A7%8B%E7%8A%B6%E6%80%81%E8%AE%BE%E7%BD%AE%E5%9C%A8%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5%E4%B8%AD h_01KGJCGCQ0AQM3Y9NNCJF2XP9G=sdk%E5%88%9D%E5%A7%8B%E7%8A%B6%E6%80%81%E8%AE%BE%E7%BD%AE%E5%9C%A8%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5%E4%B8%AD h_01KP3CJBZX8V6TGE5NVR6SW49G=%E6%B3%A8%E6%84%8F-1 explicit-control=%E6%98%BE%E5%BC%8F%E6%8E%A7%E5%88%B6 h_01KGJCGCQ07KKYGN5JZF41A6W7=%E6%98%BE%E5%BC%8F%E6%8E%A7%E5%88%B6 h_01KP3CJBZXZBFCXD1E38JKWW6H=secure-and-filter-data content-security-policy-csp=%E5%86%85%E5%AE%B9%E5%AE%89%E5%85%A8%E7%AD%96%E7%95%A5csp h_01KGJCGCQ0QB7NK6YNZT5XJVJY=%E5%86%85%E5%AE%B9%E5%AE%89%E5%85%A8%E7%AD%96%E7%95%A5csp advanced-sdk-verification-with-csp-nonce-snippets=%E4%BD%BF%E7%94%A8csp-nonce%E7%9A%84%E9%AB%98%E7%BA%A7sdk%E9%AA%8C%E8%AF%81%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5 h_01KP11XJV88YB2NSBZJTX9K7ZQ=%E4%BD%BF%E7%94%A8csp-nonce%E7%9A%84%E9%AB%98%E7%BA%A7sdk%E9%AA%8C%E8%AF%81%E4%BB%A3%E7%A0%81%E7%89%87%E6%AE%B5 h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners discard-query-parameters=%E4%B8%A2%E5%BC%83%E6%9F%A5%E8%AF%A2%E5%8F%82%E6%95%B0 h_01KGJCGCQ010K4RMFMGHD5NDC3=%E4%B8%A2%E5%BC%83%E6%9F%A5%E8%AF%A2%E5%8F%82%E6%95%B0 web-sdk-cookies-reference=web-sdk-cookie%E8%AF%B4%E6%98%8E h_01KGJCGCQ03A1H7NA5ZGPSGKP3=web-sdk-cookie%E8%AF%B4%E6%98%8E" />

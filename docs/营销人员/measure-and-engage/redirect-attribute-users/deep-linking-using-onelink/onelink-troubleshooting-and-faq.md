---
title: OneLink问题排查及疑难解答
metadata:
  keywords:
    - faq
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2020-10-27T11:26:30Z'
  edited_at: '2026-10-14T09:59:13Z'
  id: 360014821438
  locale: zh-cn
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/zh-cn/articles/360014821438
---
> **概要：** 如果OneLink自定义链接在测试和调试过程中出现跳转/功能问题，您可以在本文中快速找到解决方法。

## OneLink故障排查指南

## OneLink常见问题答疑

### OneLink模板常见问题解答

<div id="which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes" />

<Accordion title="如何在Universal Links、App Links和URI schemes中选择最合适的应用调起方式？">

**Universal Links：** 98%的iOS用户都需要使用此方法来调起应用

**App Links：** 适用于6.0及以上版本的安卓用户。**请注意**：三星的操作系统无法通过安卓App Links打开应用。

> 📘 **注意**
>
> 使用Universal Link和App Link调起应用时，都需要证明用户所点击的URL中的域名（即OneLink自定义域名或品牌域名）属于且关联到要打开的应用。您可以通过**Apple App Site Association（AASA）文件**（适用于iOS）和**Assetlinks**文件（适用于安卓）来关联域名。
>
> 这些文件存于AppsFlyer服务器或广告主网站中。默认情况下，在您创建OneLink模板并设置Universal Link和App Link时，AppsFlyer会自动生成并托管这些文件。

**URI schemes：** 这是在三星设备上调起应用的主要方式。在非三星设备上，这是一种较为传统的应用调起方式，您可以将其作为备用方案。该方式可用于以下场景中：

* 为6.0以下版本的安卓用户打开应用（在总体安卓用户中的占比不到15%）
* Universal Link和App Link失效或尚未设置时，作为备用方式打开应用<strong>请注意：</strong>将URI scheme作为Universal Link的备用方案时，其功能性会受到iOS相关限制的影响。详情请见<Anchor target="_blank" href="/marketers/zh/docs/uri-scheme-fallback-for-ios">此文档</Anchor>。

#### 深度链接

Universal Link、App Link和URI scheme都是安全的应用**打开**方式。如需通过深度链接让用户跳转到应用中的具体页面或体验，请参考<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">OneLink深度链接指南</Anchor>。

</Accordion>

<div id="which-operating-systems-allow-uri-schemes-to-open-the-app" />

<Accordion title="哪些操作系统支持通过URI scheme打开应用？">

| 操作系统 | URI scheme是否能打开应用 |
| --- | --- |
| iOS | **可以**在Universal Link失效时作为备用方案调起应用。<br /><br />**重要说明：**<ul><li>将URI scheme作为Universal Link的备用方案时，其功能性会受到iOS相关限制的影响。</li><li>对于大部分浏览器（包括Safari），都必须在URL中添加`af_force_deeplink=true`参数，才能将URI scheme作为备用方式打开应用。详情请见<Anchor target="_blank" href="/marketers/zh/docs/uri-scheme-fallback-for-ios">此文档</Anchor>。</li></ul> |
| 安卓 | **可以**用于三星设备和6.0以下版本的安卓系统，或在之后的安卓版本中作为App Link失效时的备用方案。 |
| Amazon | **否** |
| Windows Mobile | **否** |

</Accordion>

<div id="do-i-need-to-update-the-app-after-ios-universal-links-and-android-app-links-setup" />

<Accordion title="iOS的Universal Link和安卓的App Link设置完毕后是否需要更新应用？">

**可以**您每次配置Universal Link或App Link为现有用户打开应用时，iOS Associated Domains或AndroidManifest.xml都会更新，因此您必须向对应的应用商店上传更新后的应用。**小贴士：** 为了尽量减少应用更新的频次，建议您一次性完成<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">应用打开</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">深度链接</Anchor>中所有与开发相关的必要更新。

</Accordion>

<div id="can-i-redirect-existing-users-to-a-web-page-instead-of-the-app" />

<Accordion title="是否能让现有用户跳转到网页，而非应用？">

<strong>可以，</strong>但以此方式配置模板后会影响所有用户（潜在用户及现有用户）——相关的链接会让所有人都跳转到落地页/网页URL。也就是说，潜在用户不会被引导到应用商店。

如需让用户跳转到网页，请按以下步骤操作：

1. 不要在您的模板中设置Universal Link、App Link或URI scheme。
2. 为未激活相关应用的用户设置跳转，将其引导到落地页/网页URL。
   * 将落地页/网页URL添加为af\_android\_url和af\_ios\_ur的参数值。
   * 请确保作为用户跳转终点的网址已添加到<Anchor target="_blank" href="/marketers/zh/docs/set-up-your-domain-redirect-allowlist">跳转白名单</Anchor>中。
   * 在已激活相关应用的设备中（即对于现有用户），跳转设置也会自动生效。

**请注意**：如果您想要让现有用户在打开应用后跳转到移动端网页，需要您的开发人员在应用中配置该行为。

</Accordion>

<div id="can-i-redirect-tablet-users-to-a-different-app-or-url-then-mobile-app-users" />

<Accordion title="是否能让平板用户和手机用户跳转到不同的应用或URL？">

您可以针对以下设备设置专用的跳转行为：

* Windows Phone
* iPad
* Amazon Kindle Fire

目前尚不支持其它平板设备的专用跳转。

</Accordion>

<div id="can-i-assign-an-app-to-multiple-onelink-templates" />

<Accordion title="是否能将同一个应用放到多个OneLink模板下？">

**可以**虽然一个OneLink模板就可以生成无限多条OneLink URL，但有些情况下，您可能需要将同一个应用分配到多个OneLink模板下。举例来说，假设您的安卓应用有多个版本，分别在不同的第三方应用商店上架，您就需要为每个安卓应用版本都设置一个OneLink模板，并将对应的iOS应用分配到所有模板下。

**重要提示**：

对于使用iOS Universal Link和安卓App Link打开应用的模板，**如果模板中有多个子域名**，则必须为每个子域名都配置并更新您的iOS和安卓应用，具体方法如下：

* **iOS Universal Links：** 新建OneLink模板并在应用中更新关联的域名后，向App Store提交更新版本的应用。只有更新到新版本的iOS用户才能激活基于新模板创建的OneLink链接。
* **安卓App Link：**
  1. 创建新的OneLink模板后，复制App Link部分底部的XML代码段。在您需要深度链接的intent以及所有之前的intent中，将该代码段粘贴到**AndroidManifest.xml**文件里。
  2. 在商店上架新版本的应用。只有更新到新版本的安卓用户才能激活基于新模板创建的OneLink URL。

</Accordion>

<div id="can-i-delete-a-onelink-template" />

<Accordion title="我可以删除 OneLink 模板吗">

是

**要删除模板：**

2. 选择OneLink模板。
3. <Image alt="delete template.png" src="https://files.readme.io/72b68cb979e2360f4e3065f99fbb547a91713a40dcc9adee59028ed2945f794a-31094482204945.png" width="1204px" />

**请注意：** 如果被删除的模板下还有在用的OneLink链接，<strong>这些链接会失效，无法让用户跳转到应用商店。</strong>因此，在删除任何模板之前，请务必确保当前没有正在使用该模板的OneLink链接。此外，您也可以尝试根据实际需求更改现有模板的配置，省去删除模板的麻烦。

</Accordion>

<div id="can-i-change-the-subdomain-in-a-onelink-template" />

<Accordion title="OneLink模板中的子域名可否更改？">

**可以，但您必须先确保该模板下没有任何自定义链接。**

如果AppsFlyer平台中还有基于此模板创建的自定义链接，则相关子域名无法更改。我们设置这一限制的目的是为了防止正在使用中的链接跳转/深度链接行为出现中断。

对于仍含有自定义链接的模板，如果您确实需要更改其子域名，可以使用以下任一方式：

* 使用新的子域名创建一个新的OneLink模板，并在该模板下创建链接。
* 在需要更改子域名的模板下，删除所有现存的自定义链接。将所有基于该模板创建的链接全部删除后，子域名部分就会显示为可编辑。

</Accordion>

<div id="can-the-domainsubdomain-of-a-onelink-template-be-applied-to-the-template-id-of-another-template" />

<Accordion title="不同OneLink模板的域名/子域名和模板ID是否可以混搭？">

<strong>不可以。</strong>如果您将某个模板和模板ID专用的域名/子域名手动拼接到另一个模板ID，会导致Universal Link和App Link失效，并造成安全隐患。

**举例来说，**

* ID为1ABC的模板下配置的子域名为**bank.onelink.me**。
* ID为D123的模板下配置的子域名为**game.onelink.me**。
* 您在1ABC模板下创建链接**bank.onelink.me/1ABC/shorturl**。该链接可正常生效。
* 您在D123模板下创建链接**game.onelink.me/D123/exampleurl**。该链接可正常生效。
* 若创建的链接为**game.onelink.me/1ABC/shorturl**，该链接将无法生效。
* 若创建的链接为**link bank.onelink.me/D123/exampleurl**，该链接将无法生效。

</Accordion>

<div id="can-i-use-the-same-subdomain-for-more-than-one-template" />

<Accordion title="是否能在多个模板中使用同一个子域名？">

<strong>可以，</strong>但必须单独创建带有该子域名的模板，切勿手动将该子域名添加到模板ID中。

</Accordion>

<div id="how-can-i-redirect-desktop-users" />

<Accordion title="如何为PC端用户实现跳转？">

您可以通过邮件营销等方式引导PC端用户点击您的OneLink自定义链接。但PC端用户点击这些链接时，无法跳转到移动端网页、应用商店或打开应用。默认情况下，PC端用户会跳转到网页版的App Store或Google Play商店。

**那么要如何为PC端用户打造良好的用户体验，并将其转化为移动端用户呢？**

您可以对OneLink链接或模板进行配置，从而让PC端（Windows或Mac）用户跳转到另一个网页。请使用`af_web_dp`参数，在链接中添加该网页地址。请确保作为用户跳转终点的网址已添加到跳转白名单中。

**请注意：** 如果您的链接中包含`af_web_dp`，则AppsFlyer不会记录该链接来自PC端的点击。

> 👍 **提示**
>
> 建议让PC端用户跳转到含有网页专用表单的网页URL，可通过SMS或邮件向PC端用户的移动设备发送OneLink链接。详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#desktop">OneLink智能脚本</Anchor>，其中详细解释了这一方案。

</Accordion>

<div id="how-can-i-redirect-chrome-os-users" />

<Accordion title="如何为Chrome操作系统的用户实现跳转？">

AppsFlyer将Chromebooks上的应用视为安卓应用。

如需让Chromebook平台中尚未激活应用的新用户跳转到专门的网页URL，请完成以下操作：

1. 进入OneLink模板设置页面，**配置链接参数** > **若用户未安装相关应用** > **安卓**，点击**让用户跳转到其他URL**。  
   或  
   进入OneLink模板设置页面，**深度链接与跳转** > **跳转** > **若用户未安装相关应用** > **安卓**，选择**网址**。
2. 输入相关URL。  
   通过链接设置添加URL时，该URL在您的链接中会以`af_android_url`参数表达。

</Accordion>

### OneLink链接常见问题解答

<div id="does-onelink-work-without-the-appsflyer-sdk" />

<Accordion title="如果没有接入AppsFlyer SDK，OneLink是否能生效？">

**可以，但有一定局限。**

如果您需要在短时间内将移动端网页用户转化为应用用户，且无法接入AppsFlyer SDK，这个方法也是可行的。

即使您的应用内没有接入AppsFlyer SDK，OneLink仍然可以实现基本的用户跳转和应用调起。此外，由于智能横幅的实现不需要SDK，因此在没有接入的情况下也能正常生效。

但SDK的缺失会造成以下影响：

* 无法实现深度链接，即用户点击链接后只能打开应用，无法进入具体页面。
* 无法记录归因数据。
* 无法记录应用内事件。

</Accordion>

<div id="what-methods-are-available-for-creating-onelink-custom-links" />

<Accordion title="OneLink自定义链接的创建方式有哪几种？">

下表列出了OneLink自定义链接的创建方式，并对比了各种方式之间的差异。

| 链接创建方式 | 用途 | 短/长链 | 高级功能 | 是否在面板中呈现 | 归因效期（TTL）上限及默认值 |
| --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">AppsFlyer面板</Anchor> | 创建OneLink模板和自定义链接 | 两者皆可 | -- | ✓ | 无限制 |
| <Anchor target="_blank" href="/marketers/zh/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> | 快速创建大量OneLink | 短 | ✓ | -- | 31天 |
| OneLink链接批量创建功能 | 通过CSV文件中定义的参数快速创建大量OneLink短链 | 短 | -- | -- | 365天 |
| <Anchor target="_blank" href="/marketers/zh/docs/user-invite-attribution">SDK</Anchor> | 用户邀请（推荐）广告 | 短 | -- | -- | 60天 |
| <Anchor target="_blank" href="/marketers/zh/docs/onelink-smart-script-overview">OneLink智能脚本</Anchor> | 移动端网页到应用广告 | 长 | -- | -- | 无限制 |
| <Anchor target="_blank" href="/marketers/zh/docs/understand-onelink-short-vs-long-urls">电子表格</Anchor> | 使用您自己的计算方式创建大量OneLink自定义链接 | 长 | -- | -- | 无限制 |

</Accordion>

<div id="can-onelink-custom-links-open-the-app-from-a-browser" />

<Accordion title="OneLink自定义链接是否能通过浏览器调起应用？">

**可以**，但需注意Universal Link和App Link只有在用户点击链接时（比如网页或邮件中的链接）才能生效。<strong>如果用户将链接粘贴到浏览器的地址栏中，则无法调起应用。</strong>在测试链接时，请务必点击URL，而不要将其粘贴到浏览器的地址栏中。

</Accordion>

<div id="why-doesnt-the-onelink-url-open-the-app-or-deep-link-existing-users" />

<Accordion title="OneLink链接为何无法为现有用户打开应用或实现深度链接？">

即使您已经做了万全的准备，在部分情况下，您的OneLink链接可能还是无法按预期实现深度链接。这时，用户可能会跳转到应用商店或报错页面，而不是打开应用或深度链接到应用中的具体页面。

出现这种情况的原因有以下几种：

* **宿主应用问题：** 您在WhatsApp、Gmail、WeChat等应用中分享您的归因链接时，这些应用即称为宿主应用。宿主应用可能会使用不同的方式来激活被点击的链接（比如其内部的专用浏览器），其中有一部分会屏蔽所有的归因链接。
* **浏览器问题：** 部分浏览器和操作系统对于链接的处理方式有所不同。比如在有些浏览器中，粘贴链接无效，必须点击该链接才能使其生效。
* **操作系统更新：操作系统（iOS和安卓）更新后可能会出现意想不到的漏洞，导致深度链接无法生效。**
* **设备问题：** 不同的智能手机、平板、笔记本等设备使用的iOS、安卓、Windows Mobile版本不同，而其他操作系统对于归因链接的处理方式则各不相同。
* **配置问题：** 深度链接值中不能使用<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#traits-and-limitations">特殊字符</Anchor>，否则链接会失效。

为了应对这些问题，您可以通过备用URL和强制深度链接来优化用户体验。

#### 备用URL

应用调起或深度链接失败时，备用URL可让用户跳转到指定的网页。**注意：** 备用链接会将未安装应用的用户一并送往备用网页，而非应用商店。因此，请仅在向已安装应用的现有用户进行再营销投放时使用此方式。

启用备用URL时，请在OneLink模板或自定义链接设置中专门为未安装应用的用户配置相关的链接行为，让其跳转到其他URL。

[![different_url.png](https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png)](https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png)

该设置会在备用链接中添加`af_ios_url`和`af_android_url`参数，表示跳转终点，让iOS用户跳转到`af_ios_url`参数中指定的页面，安卓用户跳转到`af_android_url`参数中指定的页面。

> 📄 **示例**
>
> 以下方OneLink URL为例：
>
> ```http
> https://go.onelink.ly/qwerty?pid=source&af_dp=greatapp%3A%2F%2F&af_ios_url=www.yoursite.com/ios-bonus
> &af_android_url=www.yoursite.com/android-bonus
> ```
>
> 正常情况下，点击此链接的iOS和安卓用户会被深度链接到应用中的具体页面。但如果深度链接失败，则用户会进行以下跳转：
>
> * iOS用户：www.yoursite.com/ios-bonus
> * 安卓用户：www.yoursite.com/android-bonus

> 📘 **注意**
>
> * 如果您在URL的参数值中使用井号（#），必须对其进行编码。
> * 发生跳转时，OneLink链接参数会传递到`af_ios_url`或`af_android_url`中指定的页面。若要防止此行为，请在OneLink中添加参数`af_param_forwarding=false`。

#### 强制深度链接

您可以通过强制深度链接的方式使用URI scheme，作为应用调起和深度链接的备用方案。

该方案适用于大部分已安装应用的用户。但是对于iOS用户，URI scheme的应用调起方案用一定的局限性，您可能需要在OneLink URL中添加`af_force_deeplink=true`来强制执行深度链接，让用户进入URI scheme中指定的应用内页面（以`af_dp`参数表达）。详情请见<Anchor target="_blank" href="/marketers/zh/docs/uri-scheme-fallback-for-ios">iOS的URI scheme备用方案</Anchor>。

</Accordion>

<div id="why-does-my-onelink-url-open-a-blank-page-in-chrome" />

<Accordion title="OneLink URL在Chrome里打开了空白页面，这是为什么？">

请检查您是否使用了带有`target`属性的HTML 标签。如果OneLink URL处于带有`target="_blank"`属性的标签内，就会在Chrome内（不论是iOS还是安卓设备）打开空白页面，且用户无法跳转到App Store或Google Play。

</Accordion>

<div id="can-i-use-onelink-for-redirection-on-brave" />

<Accordion title="OneLink能否在Brave中实现跳转？">

可以但用户在安卓设备的Brave浏览器中点击OneLink链接时，延迟深度链接会失效。而当用户在iOS设备上点击链接时，会出现空白页面，这时用户用户必须在该空白页面上有所操作（如滚动或触屏），才能让延迟深度链接生效。

</Accordion>

<div id="do-onelink-custom-links-take-longer-to-load-than-other-links" />

<Accordion title="OneLink自定义链接的加载时间是否会比其他链接长？">

<strong>不会。</strong>OneLink自定义链接正常生效、实现跳转时不会产生额外的处理需求，也不会延长加载时间，在加载时长方面与其他AppsFlyer链接没有区别。

</Accordion>

<div id="how-can-i-record-the-cost-per-install-when-using-onelink" />

<Accordion title="使用OneLink时如何记录激活成本？">

请进入OneLink面板的**其它参数**部分，打开<strong>记录激活成本（CPI）</strong>开关，然后您就可以对该链接带来的激活设定具体的CPI值。

请选择成本货币并输入**数值**（可精确到小数点后4位）作为CPI。该操作会在链接中添加af\_cost\_currency和af\_cost\_value参数。

> 📄 **示例**
>
> 假设您开展了SMS营销投放，其中每1000条短信的成本（CPM）为$20。投放一段时间后，您发现其广告转化率为5%，因此得出CPI为$0.40。将激活成本设为0.40 USD后，您就能衡量该次投放最终的ROI。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview">成本与ROI的衡量</Anchor>。

</Accordion>

<div id="how-can-i-prevent-parameter-forwarding-on-redirections" />

<Accordion title="如何防止跳转时发生参数转发？">

`af_r`、`af_ios_url`、`af_android_url`和`af_web_dp`参数会从归因链接或OneLink链接传递到跳转后的页面。您可以在链接中添加`af_param_forwarding=false`来防止这类参数转发行为。

</Accordion>

<div id="how-can-i-remove-appsflyer-pid-and-c-parameters-when-forwarding-while-keeping-all-other-parameters-on-redirection-urls" />

<Accordion title="如何从跳转链接中移除AppsFlyer的PID和C参数，但保留所有其他参数？">

您有时可能会看到带有多个PID的URL。这是因为AppsFlyer会在跳转链接中添加PID和C参数，而这时如果客户侧也在其中加入了自己的PID参数，就会出现这样的情况。比如“pid”在客户侧网站URL中可能代表“Product ID”（产品ID）。

一般情况下，在归因链接中添加`af_param_forwarding=false`就能移除所有参数。

但如果用户在PD端点击该链接，您可能需要在链接中保留基本的CRM参数。这时，您可以在该归因链接中添加`af_base_params_forward=false`，这样就能只移除AppsFlyer的PID和C参数，保留所有其他参数。

</Accordion>

<div id="are-singleplatform-custom-links-still-available" />

<Accordion title="OneLink是否仍支持单平台自定义链接？">

OneLink是目前唯一一个支持针对自有媒体创建自定义归因链接的解决方案。

过去，广告主还可以在没有OneLink的情况下使用单平台（分应用）的自定义链接。我们现在已弃用该方法，仅支持通过OneLink模板创建新的自定义链接。

但您之前遗留的单平台自定义链接仍可如常生效。您也可以在OneLink自定义链接页面点击右上角的**查看旧版单平台链接**按钮，查看并修改您的遗留链接。

</Accordion>

<div id="can-i-change-the-short-url-id-after-saving-a-link" />

<Accordion title="保存链接后可否修改其短链ID？">

**不可以**，短链ID仅可在链接创建的当下设置。

</Accordion>

<div id="can-i-wrap-and-shorten-onelink-custom-links" />

<Accordion title="能否对OneLink自定义链接进行嵌套并将其缩短？">

**使用外部链接缩短器或对OneLink自定义链接进行嵌套会干扰Universal Link和App Link的应用调起功能。**

激活Universal Link或App Link时，操作系统必须能识别出URL中与应用相关联的域名，因此在面向用户的链接中使用任何外部的嵌套、缩短或跳转都会导致激活失败。这些外部工具包括bit.ly、非AppsFlyer品牌链接，以及使用点击记录的邮件营销服务商（ESP）。

**如需在确保跳转功能正常的情况下嵌套并缩短链接，请完成以下操作：**

* 您创建OneLink自定义链接时，AppsFlyer会生成相应的短链。请使用该链接，而非bit.ly等外部链接缩短器。  
  **提示**：您还可以在短链中使用品牌域名，进一步缩短链接长度。如果您通过AppsFlyer面板创建链接，可以做到URL ID的极致精简，最终得到一个类似“https://brand.com/a1b2/a”结构的链接（其中brand.com是品牌域名，a1b2是4字符的模板ID，a是URL ID，最多可以缩短到1个字符。）   
  这一方法的优势在于：
  * 该方法能够生效的原因在于其使用了OneLink模板中配置的OneLink子域名。
  * 使用该方法时，您可以随时更改链接参数，包括各种深度链接设置，甚至在向潜在用户发送归因链接后仍能进行修改链接。
  * 该方法可统计来自移动端设备的点击，并呈现在AppsFlyer面板中，您无需再使用其他工具查看此数据。
  * 您可以使用<Anchor target="_blank" href="/marketers/zh/docs/brand-onelink-with-your-domain">品牌域名</Anchor>对短链中的最后一部分进行定制。
* 使用<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">URI scheme</Anchor>作为备用方案，在Universal Link和App Link失效时调起应用，并在链接中添加参数`af_force_deeplink=true`。
* 与邮件营销服务商合作时的可用方案详见[此文档](/docs/onelink-troubleshooting-and-faq#can-i-use-onelink-custom-links-in-emails)。

</Accordion>

<div id="can-i-use-onelink-custom-links-in-emails" />

<Accordion title="是否能在邮件中使用OneLink自定义链接？">

**可以**，但如果您与邮件营销服务商（ESP）合作，需要特别注意链接嵌套问题。ESP为了统计有效点击，会对邮件中的所有链接进行嵌套。用户点击链接后，这类嵌套会中断应用打开/深度链接流程。

您可以使用以下任一方式预防此类问题：

* 在您的ESP配置中关闭点击记录。  
  **（提示**：一般来说这是最简便的解决方式。）
* 在归因链接中添加标签`af_esp=true`，从而通过`af_dp`参数中指定的URI scheme强制应用打开。该方案适用于已安装相关应用的用户。
* 确保与您合作的ESP支持AppsFlyer的应用打开和深度链接解决方案（尤其是通过Universal Link实现的方案）。<Anchor target="_blank" href="/marketers/zh/docs/email-service-provider-esp-integration-guide">了解详情</Anchor>。

</Accordion>

<div id="how-do-users-get-redirected-to-their-regional-app-store" />

<Accordion title="如何让用户跳转到其所在国家/地区的应用商店？">

OneLink会根据用户的IP地址让其跳转到对应的国家/地区应用商店。

</Accordion>

<div id="why-isnt-my-onelink-url-redirecting-users-to-the-specified-domain" />

<Accordion title="OneLink链接为什么没有让用户跳转到指定的网页？">

请检查您是否在AppsFlyer中启用了跳转白名单。如果您启用了该功能，就必须对跳转网页的URL域名或子域名加白。<Anchor target="_blank" href="/marketers/zh/docs/set-up-your-domain-redirect-allowlist">详情请见跳转白名单。</Anchor>

</Accordion>

<div id="why-do-i-get-the-app-you-are-looking-for-is-unavailable-error" />

<Accordion title="为什么会出现报错“您要查找的应用不可用”？">

如果链接未跳转到Google Play，并出现“您要查找的应用不可用”（App you are looking for is unavailable）的报错，可能是因为发生了下列情况：

* 您的应用目前尚未在Google Play正式上架，处于待批状态（Pending）。为了避免发生上述问题，请将链接的跳转终点设置为网址，而非Google Play。后续应用获批上架后再将跳转终点改为Google Play。请在相关<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">链接的模板页面</Anchor>中更改这些配置。
* 如果您的应用仅在第三方应用商店上架，该应用在AppsFlyer中设置的Google Play上架状态可能有误，从而导致了上述问题。请进入“我的应用”页面，并在相关应用的配置中将其<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">Google Play上架状态设置为“在第三方应用商店上架”</Anchor>。

</Accordion>

<div id="why-is-my-monelinkme-shortlink-not-working" />

<Accordion title="m.onelink.me短链为什么无法正常生效？">

AppsFlyer自2024年6月起弃用旧版短链**m.onelink.me**。使用这个子域名的链接不再跳转到指定网址，导致预期的用户体验出现中断。

</Accordion>

<div id="can-i-manually-switch-between-the-branded-domain-and-its-onelink-subdomain-in-an-existing-link" />

<Accordion title="能否在现有链接中手动切换品牌域名和其OneLink子域名?">

可以，但必须先确保品牌域名和其OneLink子域名之间有正确的映射。详情请见<Anchor target="_blank" href="/marketers/zh/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer">在AppsFlyer后台设置品牌域名的说明文档。</Anchor>

**示例**:  
OneLink子域名：**demo.onelink.me**  
模板ID：**A1r4**  
映射到[**demo.onelink.me**](http://demo.onelink.me)子域名的品牌域名为：

* **app.simulatorapp.com**
* **click.simulatorapp.com**

您在OneLink面板中创建了以下品牌链接：  
**app.simulatorapp.com/A1r4/simulationlink**  
您可以使用其他品牌域名链接或OneLink子域名链接来替换上面这条的品牌链接。  
以下链接的功能是以完全一致的，且在任何平台中的效果都一样：

* app.simulatorapp.com/A1r4/simulationlink
* demo.onelink.me/A1r4/simulationlink
* click.simulatorapp.com/A1r4/simulationlink

</Accordion>

### OneLink参数常见问题答疑

<div id="what-parameters-are-mandatory-for-onelink-custom-links" />

<Accordion title="OneLink自定义链接中有哪些必要字段？">

只有媒体渠道（**pid**）是必须配置的参数。

</Accordion>

<div id="can-parameters-be-appended-to-the-short-url" />

<Accordion title="可否在短链后拼接参数？">

**可以**，您可以在短链后添加任何参数。

<strong>重要提示！</strong>短链后拼接的参数无法覆盖该链接中已配置的参数。

> 📄 **示例**
>
> * 假设您创建了以下OneLink自定义链接：
>   * **长链：** https://onelink-sim.onelink.me/Il2C?pid=training&c=peaches
>   * **短链：** https://onelink-sim.onelink.me/Il2C/70e6d165
> * 您在短链后添加以下参数：https://onelink-sim.onelink.me/Il2C/70e6d165?c=bananas&af_adset=fruits
> * 短链后添加的**af\_adset=fruits**参数可正常生效，用于归因。但**c=bananas**参数**则无法生效**，因为长链中已经存在**c**参数。

</Accordion>

<div id="what-custom-media-source-names-can-i-use" />

<Accordion title="自定义媒体渠道的命名有何限制？">

但是建议您不要使用*organic*来命名自定义媒体渠道，因为这会影响归因数据的可靠性。

如果您在付费媒体中使用OneLink：

* 请在OneLink自定义链接的媒体渠道参数中使用对接渠道专用的**PID**值（以 **\_int**结尾）。切勿以*googleadwords*或*facebook*等SRN的名称来命名您的自定义媒体渠道，否则会影响归因数据的准确性。
* 对于您在OneLink模板中配置的所有应用，请确保该渠道已与AppsFlyer对接并且处于活跃状态（即“**启用该渠道**”开关已打开）。

</Accordion>

<div id="what-attribution-parameters-can-be-added-to-a-onelink" />

<Accordion title="OneLink中可以添加哪些归因参数？">

您可以在OneLink中添加各种归因参数，帮助您对归因数据进行深入剖析。

| **归因参数** | **说明** | **链接中的参数名称** |
| --- | --- | --- |
| **Campaign** | 设置广告系列名称后可以比较自有媒体上不同广告系列的投放指标 | c |
| **Adset** | 设置广告组名称后可以比较自有媒体中同一个广告系列下不同广告组的投放指标 | af\_adset |
| **广告名称** | 设置广告名称后可以比较自有媒体中同一个广告组/广告系列下不同广告的投放指标 | af\_ad |
| **Channel** | 设置流量入口后可以比较自有媒体下多个流量入口的投放指标<br /><br />举例来说，假设您同时使用两家SMS服务商发送SMS短信广告，可以使用流量入口参数来区分这两家服务商，然后比较两者的转化率。 | af\_channel |
| **可配置参数** | AppsFlyer提供5个可配置参数，您可以在其中添加自定义值，用于数据分析。<br /><br />**请注意：** AppsFlyer会对这些参数进行解析，并将解析后的结果呈现在原始数据报告中，用于数据汇总或筛选。 | af\_sub1、af\_sub2、af\_sub3、af\_sub4、af\_sub5 |
| **自定义参数** | 与可配置参数类似，您可以使用任意参数名和参数值来配置字段。<br /><br />但与可配置参数不同，AppsFlyer不会在原始数据中解析自定义参数，这些参数仅呈现在原始数据报告中的**original url**一列中。 | 自定义  <br />（广告主自行配置） |

详情请见<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">AppsFlyer的归因链接结构和参数</Anchor>。

</Accordion>

<div id="are-custom-parameters-added-to-onelink-custom-links-available-in-raw-data" />

<Accordion title="添加到OneLink自定义链接中的自定义参数是否能通过原始数据中拉取？">

**可以**自定义参数会呈现在原始数据中的**original url**一列，但是不会单独分列显示。

如果您需要解析后的数据，请使用可配置参数`af_sub1-5`，这些参数在原始数据报告中会单独分列显示。

</Accordion>

<div id="are-parameter-names-case-sensitive" />

<Accordion title="参数名称区分大小写吗？">

**可以**请确保您的参数名称和参数值中仅包含小写字母。如果参数名称或参数值中带有大写字母或大小写不一致，会在面板和原始数据中造成数据误差和差异。

</Accordion>

### 对接渠道的常见问题解答

<div id="can-i-use-onelink-in-social-apps-unpaid" />

<Accordion title="OneLink能否在社交应用（非付费渠道）中使用？">

如果您在社交应用的非付费帖子中投放广告，但无法根据受众群体的设备进行定向投放，您可以使用OneLink来解决这一问题。

但是部分应用针对iOS的Universal Link设置了一定的限制，使得OneLink的设备识别、跳转、归因、深度链接等基本功能的实现变得更加复杂。某些情况下，您可能需要通过社交应用落地页或URI scheme来为用户实现跳转或深度链接。

下表总结了目前常见的社交应用对OneLink的支持情况：

<table><thead><tr><th>社交应用</th><th>未安装广告主应用的安卓用户</th><th>安卓深度链接</th><th>未安装广告主应用的iOS用户</th><th>iOS深度链接</th></tr></thead><tbody><tr><td> <strong>Facebook</strong> （包括Boosted Posts）</td><td><span>✓\*\*†† </span></td><td><span>✓\*\*††</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Facebook Messenger</strong></td><td><span>✓\*\*†† </span></td><td> <span>✓\*\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Snapchat</strong></td><td><span>✓†† </span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Instagram</strong></td><td><span>✓†† </span></td><td><span>✓††</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>LinkedIn</strong></td><td><span>✓</span></td><td><span>✓\*\*</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td><strong>Reddit</strong></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td><strong>Slack</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>X（前身为Twitter）</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>微信</strong></td><td><span>✓† </span></td><td><span>✓† </span></td><td><span>✓\*</span></td><td><span>✓\*† </span></td></tr><tr><td><strong>WhatsApp</strong></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="5"><p>\* 需要设置<a href="./onelink-troubleshooting-and-faq#which-operating-systems-allow-uri-schemes-to-open-the-app">URI scheme</a>或<a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page" target="_blank">社交应用落地页</a>。<strong>请注意</strong>：在Facebook和Facebook Messenger中，如果您同时设置了URI scheme和社交应用落地页，界面不会显示落地页。</p><p>\*\* 必须配有URI scheme。</p><p><span>†</span> 界面可能会显示弹窗，让用户在外部浏览器中打开链接。</p><p><span>†† 安卓社交应用的Webview深度链接跳转有一定限制。详情请见</span><a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection" target="_blank"><span>此文档</span></a><span>。</span></p></td></tr></tbody></table>

</Accordion>

<div id="can-i-use-onelink-with-ad-networks-paid" />

<Accordion title="能否在广告平台（付费渠道）中使用OneLink？">

**可以**，但OneLink主要用于自有媒体，而非广告平台。 这是因为广告平台通常在流量侧应用中投放广告（也就是说，他们掌握用户的操作平台、设备ID等信息），因此您只需针对不同的应用和操作平台配置归因链接即可，无需使用OneLink。 但如果广告平台无法预判用户的操作平台（比如通过广告平台投放邮件或SMS广告时），就需要使用OneLink解决此问题。

> 🚧 **重要提示！**
>
> 通过OneLink在广告平台中进行投放时，必须使用OneLink长链。

**请按以下方式设置广告平台的OneLink：**

* 按照<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#attribution-link-tab">广告平台的归因链接说明</Anchor>进行操作，并在界面弹出OneLink提示时选择**使用OneLink**。

正确无误地将适用于安卓和iOS的所有参数添加到OneLink自定义链接后，用户点击该链接就能跳转到对应的平台，且用户激活应用后，必要参数会通过回传发送到广告平台。

> 📄 **示例**
>
> ```http
> https://greatapp.onelink.me/3287867539?pid=network_int&c=email&
> idfa{$IDFA}&gaid={$GAID}&clickid=$SITEID&
> af_sub1=[pixel_code]&af_sub2=[creative]
> ```
>
> 广告平台根据客户端设备的操作平台选取IDFA或GAID。

</Accordion>

<div id="how-can-i-solve-the-ios-applaunching-issue-from-social-media-apps" />

<Accordion title="如何解决社交媒体应用中的iOS应用打开问题？">

Facebook等社交媒体应用在部分情况下会阻止iOS的Universal Link完成应用打开。建议您使用<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">社交应用落地页</Anchor>来解决此类应用打开问题。

如果您不想使用社交媒体落地页，也可以配置一个URI scheme作为备用方案。但请注意以下事项：

* 将URI scheme作为Universal Link的备用方案时，其功能性会受到iOS相关限制的影响。
* 对于大部分浏览器（包括Safari），都必须在URL中添加`af_force_deeplink=true`参数，才能将URI scheme作为备用方式打开应用。详情请见<Anchor target="_blank" href="/marketers/zh/docs/uri-scheme-fallback-for-ios">此文档</Anchor>。

</Accordion>

<div id="can-i-use-onelink-on-instagram" />

<Accordion title="能否在Instagram上使用OneLink？">

**可以**，但请务必注意一下限制：

* Instagram对于帖子文案的渲染方式会使得帖子标题中的链接无法点击。
* Instagram支持安卓应用的调起和深度链接，没有特别需要注意的事项。但该平台不支持iOS应用的调起和深度链接。如需解决此问题，您可以使用以下任一方案：
  * **建议：** 配置一个<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">社交应用落地页</Anchor>。Clustered Poster和ShowAndTell模板最适合Insta上的帖子。另外，还建议您同时在的OneLink模板中设置一个URI scheme。
  * 在Instagram上投放OneLink时使用URI scheme和[强制深度链接](/docs/onelink-troubleshooting-and-faq#强制深度链接)。在Instagram上的OneLink中使用`af_force_deeplink=true`时请务必注意以下链路：  

| 用户是否已激活应用 | 链接中是否带有af\_force\_deeplink=true？ | 结果 |
| --- | --- | --- |
| 否 | 是 | 点击后打开应用商店页面 |
| 否 | 否 | 点击后打开应用商店页面 |
| 是 | 是 | 点击后打开应用 |
| 是 | 否 | 点击后打开应用商店页面 |

</Accordion>

<div id="can-i-use-onelink-for-redirection-on-wechat" />

<Accordion title="能否使用OneLink在微信上实现跳转？">

微信会覆盖安卓和iOS的深度链接，并让用户跳转到网页。用户必须在该网页中点击**选项**按钮，并选择“在浏览器中打开该页面”。这就会干扰用户体验的连贯性，致使用户脱离转化漏斗。

为了克服这个问题，OneLink会识别出微信中发生的点击，并打开一个专用的落地页，引导用户点击选项按钮并选择**在浏览器中打开**。完成该操作后，界面就会打开OneLink模板中设置的跳转链接页面。

![WeChat_a.jpg](https://files.readme.io/49c03a10d458f6ce71fd6448e922294682ac9239775534c6264c29151ec1ea6d-30192900489105.jpg)

如果用户将微信的语言设置为中文，OneLink会生成本地化版的落地页：

![WeChat_b.jpg](https://files.readme.io/502ef821a122459ab991f2a507c720f25fcac7129eb647a01290e8cabfa7a34e-30192887085841.jpg)

</Accordion>

<div id="why-are-android-users-with-the-app-installed-being-redirected-to-a-web-url-and-not-into-the-app-when-they-click-a-link-on-facebook-webview" />

<Accordion title="为何已安装应用的安卓用户在Facebook WebView上点击链接后，跳转到了网页，而没有进入应用？">

Facebook上的广告通常支持应用调起和深度链接。但如果出现以下情况，Facebook就不支持现有用户通过OneLink URL打开应用。这时，所有用户（包括已安装应用的现有用户）都会跳转到OneLink模板中设定的URL，或**af\_android\_url**、**af\_r**或**af\_custom\_android\_url**参数中指定的地址：

* 用户使用安卓移动端设备。
* 用户在Facebook应用中点击链接。
* 链接所指的HTML页面设置为在Facebook WebView中打开（移动端网站或社交应用落地页）。
* HTML页面中的链接同时包含**af\_dp**参数（带有URI scheme）和URL跳转设置（通过OneLink模板、**af\_android\_url**、**af\_r**或**af\_custom\_android\_url**参数设置）。

</Accordion>

### 有关测试的常见问题解答

<div id="how-can-i-ab-test-the-social-app-landing-page" />

<Accordion title="如何对社交应用落地页进行A/B测试？">

在社交媒体应用中投放OneLink时，您可以使用<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">社交应用落地页</Anchor>为用户打造无缝衔接的应用间跳转。一般情况下，在转化漏斗中添加额外的步骤会降低转化率。但在该场景中，如果没有落地页，用户链路就会出现断裂，导致转化率低靡。

如果您还不确定社交应用落地页是否确实有必要，可以先测试一下。

以有/无社交应用落地页为变量，对社交媒体应用中的自定义链接进行<Anchor target="_blank" href="/marketers/zh/docs/create-a-b-tests">A/B测试</Anchor>：

**请按以下步骤对社交应用落地页进行A/B测试：**

1. <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">创建一条OneLink链接</Anchor>（命名为Link1），用于社交媒体应用中的投放，且不为该链接配置社交应用落地页。
2. 添加**af\_adset**归因参数。
3. 添加**af\_ad**归因参数，将参数值设为“no lp”。
4. 在社交媒体应用以外的环境中测试Link1，确认该链接确实可正常生效并打开您的应用。
5. 创建Link1的副本，并将其命名为Link2。
6. 将**af\_ad**归因参数的值更改为“using lp”。
7. 仅为Link2<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">创建社交媒体落地页</Anchor>。
8. 在**同一个**社交媒体应用中使用Link1和Link2分别发2个贴子。  
   这里可以忽视两个链接之间的点击量差异，重点关注每个链接最终的转化率。
9. **产生足够流量后，查看A/B测试的结果。**
   1. 进入AppsFlyer总览面板，向下滚动到**汇总效果报告**表。
   2. Link1和Link2具有相同的媒体渠道、广告系列和广告组名称，因此需要切入到广告组维度查看数据。
   3. 对比用户点击Link1和Link2后的转化率（以及其他指标）。

</Accordion>

<div id="how-can-i-bypass-the-app-selection-dialog" />

<Accordion title="能否避开应用选择对话框？">

如果您在测试OneLink时看到要求您选择应用的对话框，请务必选择<Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing">给应用签名</Anchor>，而非<Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing#debug-mode">调试应用</Anchor>。您给应用签名时使用的证书就是您为App Link配置OneLink时用来<Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-for-deep-linking-and-deferred-deep-linking#generating-a-sha256-fingerprint">生成SHA256数字指纹</Anchor>的证书。

</Accordion>

### 深度链接常见问题解答

<div id="what-deep-linking-methods-should-be-implemented" />

<Accordion title="推荐使用哪种深度链接方案？">

建议您的开发人员使用Unified Deep Linking（UDL）方案来实现深度链接功能。详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">深度链接指南</Anchor>。

iOS的Universal Link和安卓的App Link是用于**调起应用的方法，不会为用户实现深度链接**（即让用户进入应用内的具体页面）。URI scheme可以打开应用并进行深度链接（通过**af\_dp**自定义链接参数实现），但建议您仅将该方法用于应用调起。该方法最主要的用途是作为Universal Link和App Link的备用方案，以及为6.0版本以前的安卓用户打开应用。

通过上述任一方法打开应用时，AppsFlyer SDK会上报自定义归因链接中**deep\_link\_value**参数的值。这个值需要通过开发人员配置的UDL方式来传递。

</Accordion>

<div id="can-a-uri-scheme-af_dp-parameter-be-used-for-deep-linking" />

<Accordion title="能否使用URI scheme（af_dp参数）实现深度链接？">

**可以**，但不建议这样操作。推荐使用**deep\_link\_value**来实现深度链接，并将URI scheme作为应用打开的备用方案，不带有通过**af\_dp**参数实现深度链接功能。但如果您已经设置了深度链接的URI scheme，并在其中添加了其他的URI路径参数（如greatapp://param1/param2），也无需更改现有的配置或代码；该URI scheme仍可正常生效。

**建议您在自定义链接设置页面中添加自定义参数。**

</Accordion>

### 与iOS 14相关的常见问题解答

<div id="does-onelink-deep-linking-work-for-ios-14" />

<Accordion title="OneLink深度链接在iOS 14中是否能生效？">

不论您将广告投放在付费渠道还是自有媒体，通过UDL实现的深度链接对iOS用户的体验没有任何影响。但以历史方式实现的深度链接可能会出现问题。

IDFA或IDFV可用时，AppsFlyer会使用这两种ID进行归因/数据上报。如果IDFA和IDFV都不可用，AppsFlyer会通过概率模型进行归因。从iOS 14.5+开始，概率模型的使用场景仅限于自有媒体、交叉推广和授权用户的网页到应用归因。

</Accordion>

<div id="does-onelink-deferred-deep-linking-work-for-ios-14" />

<Accordion title="OneLink延迟深度链接支持iOS 14吗？">

不论您将广告投放在付费渠道还是自有媒体，通过UDL实现的延迟深度链接对iOS用户的体验没有任何影响。但以历史方式实现的延迟深度链接可能会出现问题。

IDFA或IDFV可用时，AppsFlyer会使用这两种ID进行归因/数据上报。如果IDFA和IDFV都不可用，AppsFlyer会通过概率模型进行归因。从iOS 14.5+开始，概率模型的使用场景仅限于自有媒体、交叉推广和授权用户的网页到应用归因。如果您想要在付费渠道和自有媒体的投放中使用延迟深度链接，建议您使用AppsFlyer的iOS SDK V6.1.0+，以支持ATT授权（如有需要）、缓解归因方面的影响，并缩短响应时间。

</Accordion>

<div data-zendesk-anchors="onelink-troubleshooting-guide=onelink%E6%95%85%E9%9A%9C%E6%8E%92%E6%9F%A5%E6%8C%87%E5%8D%97 01H7WPYJV9CQ1J6J3PFCEQFGB0=onelink%E6%95%85%E9%9A%9C%E6%8E%92%E6%9F%A5%E6%8C%87%E5%8D%97 onelink-frequently-asked-questions=onelink%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E7%AD%94%E7%96%91 01H7WPYJV9H52P659N8JPRX2TY=onelink%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E7%AD%94%E7%96%91 onelink-template-faq=onelink%E6%A8%A1%E6%9D%BF%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WPYJV9TJRKHFZ77DFMKDDG=onelink%E6%A8%A1%E6%9D%BF%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 which-method-should-i-use-for-opening-apps%E2%80%94universal-links-app-links-or-uri-schemes=which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes 01H7WPYJV9JQG66S3K7TRHMFHA=which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes 01H7WPYJV9TV402AGAAGYARATW=%E6%B3%A8%E6%84%8F deep-linking=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 01H7WPYJV9JSQ5FV73YCE3H5AF=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 01H7WPYJV9CMQAQZ56P5P2MDBV=which-operating-systems-allow-uri-schemes-to-open-the-app 01H7WPYJV975A2YS61MQM1WX4W=do-i-need-to-update-the-app-after-ios-universal-links-and-android-app-links-setup 01H7WPYJV9GPXDP0KSQEPZXJCH=can-i-redirect-existing-users-to-a-web-page-instead-of-the-app 01H7WPYJV9A266QMK2J1K2AQXR=can-i-redirect-tablet-users-to-a-different-app-or-url-then-mobile-app-users 01H7WPYJV9DCVNRR3NNF7JMR0D=can-i-assign-an-app-to-multiple-onelink-templates 01H7WPYJV90RVHSAWA2YHBNNHA=can-i-delete-a-onelink-template 01H7WPYJV9RPNG3Z94630B789K=can-i-change-the-subdomain-in-a-onelink-template 01H7WPYJV9C0H3ZH6F6F3E43WH=can-the-domainsubdomain-of-a-onelink-template-be-applied-to-the-template-id-of-another-template 01H7WPYJV9246X8821B943N9AD=can-i-use-the-same-subdomain-for-more-than-one-template 01H7WPYJVAFBS0Y56NWN8M979B=how-can-i-redirect-desktop-users 01H7WPYJVA6PWA88VD8V0B3M74=%E6%8F%90%E7%A4%BA 01H7WPYJVAB57R0VQAS7C0D9NK=how-can-i-redirect-chrome-os-users onelink-link-faq=onelink%E9%93%BE%E6%8E%A5%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WPYJVAPNYAQ1SH4FBX4Z9F=onelink%E9%93%BE%E6%8E%A5%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WPYJVAEQQDSJ298M8JV361=does-onelink-work-without-the-appsflyer-sdk 01H7WPYJVA8XASRX9X3QVAWYS9=what-methods-are-available-for-creating-onelink-custom-links 01H7WPYJVATBVVMEPNAVBW9ZFZ=can-onelink-custom-links-open-the-app-from-a-browser 01H7WPYJVAWJ9BFYBXM6DJ3V22=why-doesnt-the-onelink-url-open-the-app-or-deep-link-existing-users fallback-urls=%E5%A4%87%E7%94%A8url 01H7WPYJVACCGVJD1Z7ZPVG2SQ=%E5%A4%87%E7%94%A8url 01H7WPYJVAHXE4M12X94T9C7A5=%E7%A4%BA%E4%BE%8B 01H7WPYJVAEMX54GZAX166FPS7=%E6%B3%A8%E6%84%8F-1 forced-deep-linking=%E5%BC%BA%E5%88%B6%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 01H7WPYJVA1W3HYYJJFQM01136=%E5%BC%BA%E5%88%B6%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 01H7WPYJVAWSD03E141SZEN2J9=why-does-my-onelink-url-open-a-blank-page-in-chrome 01H7WPYJVAV93G4EGDH2A91XMP=can-i-use-onelink-for-redirection-on-brave 01H7WPYJVAJQ6FKWDK8MNZAZT3=do-onelink-custom-links-take-longer-to-load-than-other-links 01H7WPYJVAX7P2YCBV1K1DCGEJ=how-can-i-record-the-cost-per-install-when-using-onelink 01H7WPYJVAEFX5306YA4GA45FW=%E7%A4%BA%E4%BE%8B-1 01H7WPYJVAQZJQYX3H5V8YTC27=how-can-i-prevent-parameter-forwarding-on-redirections 01H7WPYJVAYVK3A77Q35H1ENKF=how-can-i-remove-appsflyer-pid-and-c-parameters-when-forwarding-while-keeping-all-other-parameters-on-redirection-urls 01H7WPYJVA89118V5Y2DSM67Y4=are-singleplatform-custom-links-still-available 01H7WPYJVANDKXGFKYXZ6CKHSF=can-i-change-the-short-url-id-after-saving-a-link 01H7WPYJVAC2WXXY43WEYKVPYP=can-i-wrap-and-shorten-onelink-custom-links 01H7WPYJVANTMSMGZ6VP36DTV1=can-i-use-onelink-custom-links-in-emails 01H7WPYJVAE0TSRPPTD21X9Q4V=how-do-users-get-redirected-to-their-regional-app-store 01H7WPYJVA4W7YFMQD4HEE313P=why-isnt-my-onelink-url-redirecting-users-to-the-specified-domain h_01JJRP42HGK2YAQ902ADS178GD=why-do-i-get-the-app-you-are-looking-for-is-unavailable-error h_01HZKZRQW63QBJEB7HPDPAZMG1=why-is-my-monelinkme-shortlink-not-working h_01HAKSWWMSHVW9KFWA34XGXWN2=can-i-manually-switch-between-the-branded-domain-and-its-onelink-subdomain-in-an-existing-link onelink-parameter-faq=onelink%E5%8F%82%E6%95%B0%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E7%AD%94%E7%96%91 01H7WPYJVAGRVWHRVMZVQG1ZVE=onelink%E5%8F%82%E6%95%B0%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E7%AD%94%E7%96%91 01H7WPYJVBCS3JZ98FYMAPY2YT=what-parameters-are-mandatory-for-onelink-custom-links 01H7WPYJVBCD7GG37JZTF919YQ=can-parameters-be-appended-to-the-short-url 01H7WPYJVB15Q3YAVJ8M7EQ1FW=%E7%A4%BA%E4%BE%8B-2 01H7WPYJVBNTKJM3F72ZEZG32Z=what-custom-media-source-names-can-i-use 01H7WPYJVB25VGB37D3DZ2J786=what-attribution-parameters-can-be-added-to-a-onelink 01H7WPYJVBSQBR8E9NY0GJ3APT=are-custom-parameters-added-to-onelink-custom-links-available-in-raw-data 01H7WPYJVB3CCB838A7N6K932G=are-parameter-names-case-sensitive integrated-partner-faq=%E5%AF%B9%E6%8E%A5%E6%B8%A0%E9%81%93%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WPYJVB8ZZSKFT1V01EN6QF=%E5%AF%B9%E6%8E%A5%E6%B8%A0%E9%81%93%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WPYJVBCQNPTEZPM8KFE6YX=can-i-use-onelink-in-social-apps-unpaid 01H7WPYJVBTBQKK50JR179S7MW=can-i-use-onelink-with-ad-networks-paid 01H7WPYJVBJ0DX0MZPGXYF76EP=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA 01H7WPYJVBB9KJRZQTFZDG7NDK=%E7%A4%BA%E4%BE%8B-3 01H7WPYJVB60DFMHN8PCVFC5S9=how-can-i-solve-the-ios-applaunching-issue-from-social-media-apps 01H7WPYJVB94NGD94MW4HYDB5S=can-i-use-onelink-on-instagram 01H7WPYJVBT5PJHVAFD1TY6CDY=can-i-use-onelink-for-redirection-on-wechat 01H7WPYJVB05C8BXKRG0WGBJ8P=why-are-android-users-with-the-app-installed-being-redirected-to-a-web-url-and-not-into-the-app-when-they-click-a-link-on-facebook-webview testing-faq=%E6%9C%89%E5%85%B3%E6%B5%8B%E8%AF%95%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WPYJVC1PJJDA0GGT1DVVCF=%E6%9C%89%E5%85%B3%E6%B5%8B%E8%AF%95%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WPYJVCQ89S3R4X1111TRGZ=how-can-i-ab-test-the-social-app-landing-page 01H7WPYJVC20TXWKRB89XFTK1N=how-can-i-bypass-the-app-selection-dialog deep-linking-faq=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WPYJVCTM39HKCG9JN03BN6=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WPYJVCZMRN53QG5JNSB8MP=what-deep-linking-methods-should-be-implemented 01H7WPYJVC6BXRJGTJBY6KG8JX=can-a-uri-scheme-af_dp-parameter-be-used-for-deep-linking ios-14-faq=%E4%B8%8Eios-14%E7%9B%B8%E5%85%B3%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WPYJVCVCVWHJW4RH85KC40=%E4%B8%8Eios-14%E7%9B%B8%E5%85%B3%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 01H7WPYJVCFANQQ9T27M2YGGBD=does-onelink-deep-linking-work-for-ios-14 01H7WPYJVCBC9YMBQ6TV1B2SBV=does-onelink-deferred-deep-linking-work-for-ios-14" />

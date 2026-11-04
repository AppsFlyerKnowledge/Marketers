---
title: 设置智能脚本，将网页访客转化为用户
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2021-12-13T09:57:23Z'
  edited_at: '2026-10-08T13:06:10Z'
  id: 4413588932241
  locale: zh-cn
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/zh-cn/articles/4413588932241
---
> **概览：** 设置 OneLink 智能脚本，将来自任意来源的移动网站访客转化为移动应用用户，并进行归因。

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

<div id="setup" />

## 设置方式

OneLink 智能脚本 有两个版本：

**OneLink 智能脚本 V2（推荐）**：如果您是首次设置 OneLink 智能脚本，建议使用此版本。您可以直接在 AppsFlyer UI 中生成，无需开发者协助。如果因某些原因需要开发者参与，他们的工作量也会更少。此外，还可以使用 Google Tag Manager 进行设置。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2">查看开发者说明文档</Anchor>

<Anchor target="_blank" href="/marketers/zh/docs/legacy-onelink-smart-script-v1-setup">**OneLink 智能脚本 V1（旧版）**</Anchor>：如果您已设置 OneLink 智能脚本，请使用此版本的文档来维护和编辑该脚本。**注意**：虽然不是强制要求，但建议您迁移到 V2，以便使用 OneLink 智能脚本 正确获取<Anchor target="_blank" href="https://www.appsflyer.com/glossary/view-through-attribution/">浏览型归因</Anchor>。

<div id="set-up-onelink-smart-script" />

### 设置 OneLink 智能脚本

要设置智能脚本，您可以选择以下任一方式：

* 将脚本嵌入您的网站。
* 使用 Google Tag Manager。

<div id="scope-of-work" />

#### 工作范围

**参与人员**

* **广告主**：
  * 将此内容提供给网页开发者，并写入 [参数列表](/docs/set-up-smart-script-to-convert-web-visitors#arguments)中。结果是，在传出 URL 中，GCLID 将作为 **af\_sub[1-5]** 参数的值。
  * 在 AppsFlyer UI 中生成智能脚本。
  * 确保所有导向移动网页端的广告系列，其传入 URL 都包含脚本可用的参数。
  * <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">测试智能脚本</Anchor>。
* **网页开发者**：
  * 验证脚本是否会在您希望其运行的移动网站/页面上运行。
  * 根据需要使用结果值，例如将其作为链接放在您网站的 CTA 下方。
  * 使用脚本创建二维码时可能需要此项。
  * 手动向脚本添加高级参数时可能需要此项。

**前期准备**

* 拥有一个 AppsFlyer 账户，且账户中至少有一个应用。
* 一个用作 [OneLinkURL 参数](/docs/set-up-smart-script-to-convert-web-visitors#arguments)的值的 <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink 模板</Anchor>。

<div id="how-to-create-a-onelink-smart-script" />

<Accordion title="创建 OneLink 智能脚本">

**如需创建 OneLink 智能脚本：**

1. 在 AppsFlyer 中，从侧边菜单中选择 **互动** > **Web-to-app** > **智能脚本**。
2. ***对于新用户***
   1. *点击 **开始使用** 按钮。*
   2. *从第 4 步开始，完成各步骤操作。*
3. 点击页面顶部的 **+ New 智能脚本** 按钮。
4. 按照屏幕提示为您的智能脚本命名。
5. 选择一个 OneLink 模板作为脚本基础。该模板包含基础跳转设置。
6. 映射传出 URL 应包含的参数。这些参数基于传入 URL 的参数。**注意**：媒体渠道 (pid) 参数为必填项。
   1. 选择要映射的传出参数/维度。  
      通常，这是不可更改的 AppsFlyer 参数名称，但在某些情况下，您需要输入您自己的参数名称。
   2. 确定并配置传出参数的值应基于以下任一项：
      * 传入 URL 参数：列出一个或多个您希望由传出 URL 参数替换的传入 URL 参数。传入 URL 参数的值将成为您的传出 URL 参数的值。
        * 示例：any\_param\_name、utm\_param\_name。如果在传入 URL 中找到 utm\_param\_name，则其值将用作您所选传出 URL 参数的值。
        * 智能脚本会按从左到右的顺序搜索参数列表，并将第一个匹配项映射到传出 URL 参数。
        * 开发者将此参数列表称为键。
      * 默认值：当未找到传入 URL 参数，或者您未列出任何传入 URL 参数时，输入您希望用作传出参数值的默认值。
        * 示例：对于传出参数，如果传入 URL 参数列表中包含 any\_paramname、utm\_paramname，而列表中的这两个参数都未找到，则会使用默认值作为传出参数的值。
      * 覆盖值：配置传入 URL 中的一个或多个值，以及要用来替换它们的传出 URL 值。
        * 示例：对于广告系列参数，如果传入 URL 中的值为 campaign\_name，则可将传出 URL 中的值更改为 new\_campaign\_name。
   3. [可选] 点击 **+ New parameter** 以映射其他参数。查看您可以使用的所有[其他参数](/docs/set-up-smart-script-to-convert-web-visitors#arguments)（参数配置）。
7. [可选] 在**Web** **referrer mapping** 部分，打开**Media Source for organic search installs**；当 URL 参数映射部分未能识别媒体渠道时，系统会自动为自然搜索流量设置媒体渠道。[了解更多](#seo-referrer-mapping)
8. 选择如何在您的网站上实施智能脚本：
   * **将脚本嵌入您的网站。**
   * **使用 Google Tag Manager。**
9. 点击 **Test**，在<Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">智能脚本测试页面</Anchor>上测试该脚本。请确保生成的传出 URL 正确。
10. 点击
    1. **Save** 以保存您的更改
    2. **Save and Generate** 以保存并生成脚本
       1. 点击 **Download script**。
11. 如果您选择将脚本嵌入网站：将脚本发送给您的网站开发者进行实施，并告知他们如何处理生成的传出 URL。例如，将其放在您移动网站的 CTA 按钮下方，或在桌面网站上展示二维码。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#embed-the-script-in-your-website">开发者说明</Anchor>
12. 如果您选择使用 Google Tag Manager：
    1. 在 Google Tag Manager 中，创建一个新代码标记，为该代码标记命名，点击 **Tag Configuration**，然后选择 **Custom HTML**。
    2. 在 HTML 框中，粘贴生成的智能脚本代码。
    3. 点击 **Triggering**，创建一个新触发器，为其命名，并选择**触发器配置**（例如，所有页面浏览）。<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">查看 GTM 文档，了解更多</Anchor>
    4. 点击**保存**
    5. 告知您的网站开发者如何处理生成的出站 URL。例如，将其放置在移动网站的 CTA 按钮下方，或在桌面网站上显示二维码。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#use-google-tag-manager">开发人员相关说明</Anchor>
13. 已保存的脚本可在[下拉菜单](/docs/set-up-smart-script-to-convert-web-visitors#how-to-edit-or-delete-a-script)中查看。

<div id="important" />

> 🚧 **重要！**
>
> 每次更新脚本后，都需要重新部署

</Accordion>

<div id="how-to-edit-or-delete-a-script" />

<Accordion title="编辑或删除脚本">

**如需编辑或删除脚本：**

1. 点击 智能脚本 名称旁边的下拉箭头 <Image alt="Down_arrow.jpg" src="https://files.readme.io/a82023665721be681f985548857c4c329f626435780bb1bff7a3821b32b69078-42045468433041.jpg" width="28px" />。  
   您可以在此查看所有已保存的脚本  

   <Image alt="脚本步骤.jpg" src="https://files.readme.io/824c042dc23acaa14b360ce8cd792cfc2e85ee3c9c95e3fa694f96badfeb1fc2-42045468432657.jpg" width="1732px" />
2. 点击您要编辑的脚本旁边的铅笔图标
   1. 按照[如何创建 OneLink 智能脚本](/docs/set-up-smart-script-to-convert-web-visitors#设置-onelink-智能脚本)中的步骤操作
3. 点击垃圾桶图标以删除智能脚本

<div id="important-1" />

> 🚧 **重要！**
>
> 每次更新脚本后，都需要重新部署

</Accordion>

<div id="how-to-duplicate-a-script" />

<Accordion title="复制脚本">

**如需复制脚本：**

1. 前往您要复制的智能脚本
2. 点击顶部横幅上的复制按钮 <Image alt="SmartScript_duplicate.jpg" src="https://files.readme.io/ec05ea217331b588dc7033984287d46b61a37e41510546b67a0046ea281e0979-42045454920721.jpg" width="21px" />
3. 按照[如何创建 OneLink 智能脚本](/docs/set-up-smart-script-to-convert-web-visitors#设置-onelink-智能脚本)中的步骤操作

</Accordion>

<div id="argument-structure" />

<Accordion title="参数结构">

OneLink 智能脚本 使用参数，根据传入 URL 的参数以及脚本中定义的参数生成传出 URL。 afParameters 参数由多个用于归因和深度链接的其他参数组成，每个参数都包含一个结构（开发者称之为配置对象），其中包含键、覆盖值和默认值，如下表所示。

| 参数 | 描述 | 示例 |
| --- | --- | --- |
| 传入 URL 参数（开发者称之为键） | <ul><li>字符串列表</li><li>脚本会在传入 URL 中查找可能的参数列表，并将找到的参数值放入传出 URL 中作为对应的值。</li><li>脚本会从左到右搜索，并在找到第一个匹配项后停止。</li></ul> | <ul><li>示例：['in\_channel', 'utm\_channel']</li><li>对于脚本中的 channel 参数，脚本会在传入链接中查找 in\_channel，并将其值用作 channel 的值。</li></ul> |
| 默认值 | <ul><li>字符串</li><li>指定您希望作为「后备」的值。</li><li>如果在键列表中找不到某个参数，则会在传出 URL 中使用 defaultValue 值。</li><li>您可以通过传递空的键列表来强制使用默认值。</li></ul> | 示例：['web\_video']<br /><br />对于脚本中的 channel 参数，如果找不到参数 in\_channel，则会使用 web\_video 作为 channel 的值。 |
| 覆盖值 | <ul><li>字典 \{字符串: 字符串\}</li><li>对于您希望在传出链接中更改的值，请列出传入 URL 中的值，以及您希望替换成的值。</li><li>脚本会将传入 URL 中的参数值替换为您定义的值。</li></ul> | 示例：\{'video': 'video\_new'\}<br /><br />对于脚本中的 channel 参数，只要传入值为 video，脚本就会在传出链接中将其更改为 video\_new。 |

</Accordion>

<div id="arguments" />

<Accordion title="参数（参数和值）">

OneLink 智能脚本 使用参数，根据传入 URL 的参数以及脚本中定义的参数生成传出 URL。

<div id="arguments-parameters-and-values-to-implement-the-smart-script" />

#### 用于实现智能脚本的参数（参数及其值）

<table><thead><tr><th colspan="2">参数</th><th>备注说明</th><th>记录您的响应内容（供您或开发者使用）</th></tr></thead><tbody><tr><td colspan="2">oneLinkURL（必填）</td><td><ul><li>提供 OneLink 模板域名 + 模板 ID。<strong>注意：</strong>不是 OneLink 自定义链接 URL！</li><li>示例：<strong>yourbrand.onelink.me/A1b2</strong> </li><li>品牌域名示例：<strong>click.yourbrand.com/A1b2</strong> </li></ul></td><td> </td></tr><tr><td rowspan="9"><p>afParameters</p><p>（必填）</p></td><td><p>媒体渠道</p><p>（必填）</p></td><td><ul><li>用于媒体渠道的配置对象。</li><li>示例：<ul><li>键：['incoming_mediasource', 'utm_source']</li><li>默认值：['any_source']</li><li>覆盖值：`{twitter: 'twitter_int', orig_src: 'new_src'}</li></ul></li></ul></td><td><p>键：</p><p>默认值：</p><p>覆盖值：</p></td></tr><tr><td>广告系列</td><td><ul><li>用于广告系列的配置对象。</li><li>如：<ul><li>键：['incoming_campaign', 'utm_campaign']</li><li>默认值：['any_campaign_name']</li><li>覆盖值：{campaign_name: 'new_campaign_name'}</li></ul></li></ul></td><td><p>键：</p><p>默认值：</p><p>覆盖值：</p></td></tr><tr><td>渠道</td><td><ul><li>渠道的配置对象。</li><li>例如：<ul><li>键：['incoming_channel', 'utm_channel']</li><li>默认值：['any_video']</li><li>覆盖值：{video: 'new_video'}</li></ul></li></ul></td><td><p>键：</p><p>默认值：</p><p>覆盖值：</p></td></tr><tr><td>广告</td><td><ul><li>广告的配置对象。</li><li>例如：<ul><li>键：['incoming_ad', 'utm_ad']</li><li>默认值：['any_ad_name']</li><li>覆盖值：{ad_name: 'new_ad_name'}</li></ul></li></ul></td><td><p>键：</p><p>默认值：</p><p>覆盖值：</p></td></tr><tr><td>广告组</td><td><ul><li>用于广告组的配置对象。</li><li>示例：<ul><li>键：['incoming_adset', 'utm_adset']</li><li>默认值：['any_ad_name']</li><li>覆盖值：{adset_name: 'new_adset_name'}</li></ul></li></ul></td><td><p>键：</p><p>默认值：</p><p>覆盖值：</p></td></tr><tr><td>deepLinkValue</td><td><ul><li>用于 <strong>deep_link_value</strong> 的配置对象。</li><li>示例：<ul><li>键：['product_id', 'page_name']</li><li>默认值：'new_offers_page'</li><li>覆盖值：{twenty_percent_off: 'thirty_percent_off'}</li></ul></li></ul></td><td><p>键：</p><p>默认值：</p><p>覆盖值：</p></td></tr><tr><td>afSub1-5</td><td>用于 <strong>af_sub[1-5]</strong> 的配置对象。</td><td><p>键：</p><p>默认值：</p><p>覆盖值：</p></td></tr><tr><td>googleClickIdKey</td><td>指定携带 <a href="https://support.google.com/google-ads/answer/9744275?hl=en" target="_blank">GCLID</a> 的参数名称。<br/><strong>注意</strong>！<span>如需显示在 AppsFlyer 原始数据报告中，该参数必须是 <strong>af_sub[1-5]</strong> 之一。 </span> </td><td> </td></tr><tr><td> <span>其他（自定义）查询参数</span><br/> </td><td><ul><li>列出您希望包含在传出 OneLink URL 中用于归因或深度链接的所有其他参数，以及它们各自的配置对象。</li><li>自定义参数的名称由开发者在配置对象中列为 paramKey。<span></span> </li><li>例如：<ul><li>paramKey: 'deep_link_sub1'</li><li>键：['page_id']</li><li>默认值：'page1'</li><li>覆盖值：{page12: 'new_page12'}`</li></ul></li></ul></td><td><p>参数键：</p><p>键：</p><p>默认值：</p><p>覆盖值：</p></td></tr></tbody></table>

</Accordion>

<div id="advanced-arguments" />

<Accordion title="高级参数">

下表介绍了技术能力较强的营销人员或开发者可在智能脚本中实施的参数。

<div id="advanced-arguments-parameters-and-values-to-implement-in-the-smart-script" />

#### 在智能脚本中实施的高级参数（参数和值）

<table><thead><tr><th colspan="2">参数</th><th>备注说明</th><th>记录您的回答（供您或开发者使用）</th></tr></thead><tbody><tr><td colspan="2"> <br/>referrerSkipList</td><td><ul><li>特定点击的 HTTP referrer 中的字符串列表（例如 Twitter 或 Facebook）；如果找到这些字符串，智能脚本会返回 <code>null</code>。这对于 X Ads 和 Meta Ads 之类的 SRN 很有用，因为这些平台的点击已被报告。</li><li>实施此参数后，脚本将不会生成 OneLink URL。</li></ul></td><td> </td></tr><tr><td colspan="2">urlSkipList</td><td><ul><li>特定点击的 URL 中的字符串列表（例如 af_r）；如果找到这些字符串，智能脚本会返回 <code>null</code>。如果您使用带有 af_r 的 AppsFlyer 归因链接将用户重定向到您的移动网页端，并且不希望原始点击数据丢失，这会很有用。</li><li>使用此参数后，脚本将不会生成 OneLink URL。</li></ul></td><td> </td></tr><tr><td colspan="2">SEO</td><td><ul><li>启用后，如果<strong>URL parameter mapping</strong>部分未能识别媒体渠道，系统会根据用户的 web referrer URL 判断其是否来自某个搜索引擎，并据此设置媒体渠道。（自 2.10.3 版本起可用）</li></ul></td><td> </td></tr></tbody></table>

</Accordion>

<div id="use-cases" />

## 使用场景

以下部分针对一些常见的广告系列/媒体渠道场景，提供了智能脚本用例。

<div id="utm-parameters" />

<Accordion title="UTM 参数">

**设置脚本以支持 UTM 参数**：

1. 列出传入 URL 中的 UTM 参数（例如：**utm\_source** 和 **utm\_campaign**），并将其与传出 URL 中的参数（例如：**media\_source** 和 **campaign**）进行匹配。
2. 将这些内容提供给网页开发者，并写入 [参数列表](/docs/set-up-smart-script-to-convert-web-visitors#arguments) 中。

**结果**：传入参数（**utm\_source** 和 **utm\_campaign**）中的值将用于填充传出链接中参数（**media\_source** 和 **campaign**）的值。

</Accordion>

<div id="google-ads-gclid" />

<Accordion title="Google Ads GCLID">

Google Ads 广告系列安装归因的常规流程（此类广告系列带有 GCLID 参数）要求点击您广告的用户被重定向到应用商店页面 URL。

由于在这种情况下，您会将来自 Google Ads 的用户重定向到网页/落地页，因此脚本会从 Google Ads 安装广告系列 URL 中提取 GCLID 参数，并将其放入传出 URL 中。从智能脚本 2.9.0 版本开始，只要可用，GCLID、WBRAID 和 GBRAID 参数都会按原样自动转发到由智能脚本生成的传出 URL 中。

您也可以将点击 ID 映射到其他传出参数（**af\_sub[1-5]**），以便在 AppsFlyer 原始数据报告中查看这些数据。

**注意！**

* 这适用于安装广告系列。对于非 ACI 搜索广告系列（即再互动广告系列），尽管智能脚本有输出结果，Google 仍可能被归因为媒体渠道。
* 如果找到 GCLID，脚本会查找传入参数 keyword。如果找到，脚本会将 keyword 的值作为 af\_keywords 的值放入传出 URL 中。

**前提条件**: 在 Google 数据面板中，<Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">启用自动标记</Anchor>。    
启用自动标记后， URL 中会包含 *GCLID* 参数。

**设置脚本以将 Google Ads GCLID 映射到其他参数**：

1. 在传出 URL 中选择一个用于包含 GCLID 的参数。  
   最佳实践：选择 **af\_sub[1-5]**，这样数据就会显示在 AppsFlyer 原始数据报告中。
2. 将此内容提供给网页开发者，供其填写到[参数列表](/docs/set-up-smart-script-to-convert-web-visitors#arguments)中。结果是，在传出 URL 中，FBCLID 将作为 **af\_sub[1-5]** 参数的值。

**如需将这些安装通知给 Google Ads ：**

**推荐：** 设置 <Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-create-web-based-campaigns">Google 网页对接</Anchor>。此对接支持针对安装的自动回传。

**如果您尚未完成对接：**

1. 通过 CSV 从 **af\_sub[1-5]** 参数中获取 GCLID 数据，或通过 Push API 实时获取每次安装的 GCLID 数据。
2. 通过 <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">手动</Anchor>或通过 <Anchor target="_blank" href="https://developers.google.com/google-ads/api/docs/start">Google Ads API</Anchor> 将 GCLID 数据上传到 Google。

<div id="note" />

> 📘 **注意**
>
> 此 GCLID 解决方案未获得 Google 的官方支持或推荐。如果 Google 弃用 GCLID 参数，我们将修改脚本以支持相关变更。点击文章标题中的 **Follow** 按钮关注本文，以便在文章或所附脚本更新时收到通知。

</Accordion>

<div id="facebook-click-id" />

<Accordion title="Facebook FBCLID">

Meta 广告会携带点击 ID，称为 FBCLID。从智能脚本 2.8.1 版本开始，如有 FBCLID，智能脚本会在其生成的传出 URL 中按原样自动转发该值。您也可以将点击 ID 映射到其他传出参数，以便在 AppsFlyer 原始数据报告中查看这些数据。

**如需设置脚本以将 FBCLID 映射到其他参数：**

1. 在传出 URL 中选择一个用于承载 FBCLID 的参数。   
   最佳实践：选择 **af\_sub[1-5]**，这样数据就会显示在 AppsFlyer 原始数据报告中。
2. 将此内容提供给网页开发者，供其填写到[参数列表](/docs/set-up-smart-script-to-convert-web-visitors#arguments)中。结果是，在传出 URL 中，FBCLID 将作为 **af\_sub[1-5]** 参数的值。

</Accordion>

<div id="tiktok-ttclid-x-twclid-and-snapsccid" />

<Accordion title="TikTok（ttclid）、X（twclid）和 Snap（ScCid）">

TikTok、X（原 Twitter）和 Snap 广告系列的安装归因依赖于各广告平台特有的点击 ID 参数；这些参数会附加到广告点击中，用于将安装及安装后事件与其来源广告进行匹配。

当流量首次重定向到网页或落地页时，应保留并转发点击 ID，以确保正确归因。在这种情况下，智能脚本会捕获传入的点击 ID 参数，并将其附加到它生成的传出 URL 中。

点击 ID 会在安装时被捕获，并用于与该安装相关的后续事件。

从智能脚本 2.10.0 版本开始，以下“点击 ID”参数（如可用）会由智能脚本在其生成的传出 URL 中自动按原样转发：

* TikTok：ttclid
* X（前身为 Twitter）：twclid
* Snap：ScCid

您还可以将这些点击 ID 映射到其他传出参数（例如 af\_sub1-af\_sub5），以便在 AppsFlyer 原始数据报告中使用这些数据。

请参阅以下相关的 Web 对接文章：

* <Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-create-web-based-campaigns">抖音</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/snapchat-create-web-based-campaigns">Snap</Anchor>

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="SRN、自有媒体和其他媒体渠道链接">

像 Snapchat 或 X Ads 这样的 <Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#与appsflyer对接的srn">SRN</Anchor>，其运作方式与 Google Ads 或 Meta Ads 这类跨平台广告不同。这些 SRN 的广告系列会将用户引导至 Web/落地页，您的计费依据是点击带来的潜在客户，而与由此产生的任何移动用户无关。

对于这些 SRN，脚本设置方式与自有媒体或您可能使用的其他媒体渠道链接相同。

**设置脚本**：

1. 列出传入链接中的媒体渠道和广告系列参数名称。
2. 将这些内容提供给 Web 开发者，作为 [list of arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) 。  
   SRN/媒体渠道类型应为传入 URL 中的媒体渠道值。 脚本会找到该值，并将其用作 Web/落地页下载按钮后方的传出 OneLink URL 中的 **media\_source** 值。如果您想更改传出的 **media\_source**，请在提供给 Web 开发者的[参数列表](/docs/set-up-smart-script-to-convert-web-visitors#arguments)中提供传入的媒体渠道值以及要覆盖的 media\_source 值。

**结果**：对于这些 SRN/媒体渠道，传入链接中媒体渠道参数和广告系列参数的值将用于填充传出链接中的 **media\_source** and **campaign** 参数值。

<div id="example" />

> 📄 **示例**
>
> **传入 URL**：https://hotel.me/incoming_mediasource=twitter&incoming_campaign=big_social
>
> **传出 URL**：https://hotel.onelink.me/Ac4G?pid=twitter&c=big_social

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="AppsFlyer 归因链接">

当媒体渠道为点击广告平台时，可以使用 AppsFlyer 归因链接。在 AppsFlyer 中设置此类链接时，您可以添加一个 <strong>重定向 URL 路径（af\_r）</strong>参数，并填入指向您的移动网页端的目标 URL 路径，以实现 Web 广告系列到 App 的归因。您可能不希望脚本创建传出的 OneLink URL，因为这样可能会丢失原始点击中的部分数据。

**操作：** 使用 **urlSkipList** 参数列出 **af\_r** 参数。

**结果**：当智能脚本在传入链接中发现 **af\_r** 参数时，智能脚本不会生成传出 URL，开发者必须决定将哪个链接作为传出 URL，并完成相应实现。

<div id="example-1" />

> 📄 **示例**
>
> **传入 URL**：https://app.appsflyer.com/id123456789?pid=click_ad_network_int&c=orlando&af_r=hotel.me
>
> **传出 URL**：无传出 URL。

</Accordion>

<div id="web-referrer-mapping" />

<Accordion title="Web referrer 映射">

Web referrer 映射可帮助您了解用户是从哪个页面进入您的网站的（例如来自自然搜索结果），从而丰富您可用于分析源自智能脚本网页至应用流程的安装和再互动的数据。

您可以将智能脚本设置为从您的落地页或网站 HTTP 标头的 [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) 字段收集此信息。此字段包含这样一个页面的基础 URL：用户点击了该页面上的某个链接后，被带到您的网页。

**设置脚本以收集 Web referrer**

1. 打开**智能脚本**页面
2. 在 **Web referrer mapping** 区域中，为 Web referrer 值选择传出 URL 参数键：
   * af\_channel - 参数会呈现在数据面板和原始数据中
   * af\_sub1-5 - 参数会呈现在原始数据中的 **af\_sub1-5** 列以及 **original URL** 列下。
   * 自定义参数 - 由参数名称和值组成。该参数会呈现在原始数据中的 **original URL** 列下。

如需了解如何使用 Universal Links 和 App Links 对再互动进行自然搜索归因，请参阅<Anchor target="_blank" href="/marketers/zh/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">此处</Anchor>。

</Accordion>

<div id="seo-referrer-mapping" />

<Accordion title="SEO referrer 映射">

您可以打开**Media source for organic search installs**，当**URL parameter mapping**部分未能识别媒体渠道时，系统会自动为自然搜索流量设置媒体渠道。

* 如果用户的 web referrer 与受支持的搜索引擎（例如 google.com 或 bing.com）匹配，Media Source 将被设置为对应的渠道（例如 google\_organic\_seo）。
* 如果没有匹配项，则使用在 URL parameter mapping 中配置的**Default value**。

</Accordion>

<div id="desktop" />

<Accordion title="桌面端">

本文中的大多数使用场景都与来自移动设备的用户有关。因此，当他们从移动网页端被引导至应用商店时，可以立即下载您的应用。

但是，不应立即将桌面用户发送到应用商店，因为他们的设备（台式机或笔记本电脑）与移动应用下载不兼容。

为桌面用户设置脚本：

* 在您的 <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink 模板</Anchor>中，为**在桌面设备上点击链接时**设置目标 URL。该 URL 应重定向到专用的网页/落地页。该落地页可包含一个 Web 表单，用户可填写其详细信息，以接收包含应用下载链接的短信或 email。您需要自行创建网页表单，并在脚本中提供其 URL。

**结果**：脚本会检测用户所使用的设备或平台。如果是桌面端，脚本会生成一个传出 OneLink URL，将用户重定向到您专用的网页/落地页。

另请参见<Anchor target="_blank" href="/marketers/zh/docs/qr-to-app-conversion">桌面端到应用转化</Anchor>。

</Accordion>

<div id="qr-codes" />

<Accordion title="QR 码">

智能脚本会在您的网页上显示二维码，而不是显示带有链接的按钮。 

**要显示二维码：**

1. 设置智能脚本时，请确保您使用的是 智能脚本 2.6+。
2. 请让您的开发者按照<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#create-a-qr-code-with-the-smart-script-result">相关说明</Anchor>，使用智能脚本结果创建二维码。
3. [最佳实践] 请告知开发者：
   * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#create-a-qr-code-with-the-smart-script-result">自定义二维码</Anchor>，例如在二维码中央添加您的应用 Logo，并自定义颜色。
   * 当用户在桌面端时显示二维码，当用户在移动端时显示带有链接的按钮。

**结果**：脚本会显示二维码，而不是显示带有 URL 的按钮。

<div id="example-2" />

> 📄 **示例**
>
> **传入 URL**：
>
> https://hotel.me/qr_code.html?incmp=gogo&inmedia=email
>
> **传出 URL**：
>
> https://hotel.onelink.me/LtRd/?af_js_web=true&af_ss_ver=2_1_0&pid=email&c=gogo
>
> **传出二维码**：
>
> <Image alt="" src="https://files.readme.io/2f06149c901d8a97c2a544b8196e9afecbe3b3748ed8419a39c2dc5e3afa61ba-42045454923153.png" width="48.07%" />

</Accordion>

<div id="impressions" />

<Accordion title="曝光">

OneLink 智能脚本 可用于统计您网站上的曝光。为此，开发人员需要调用 impression 函数。随后，安装会通过<Anchor target="_blank" href="/marketers/zh/docs/measure-view-through-engagements">浏览型归因</Anchor>归因到这些曝光。

**注意**：

* 曝光统计是在正常的智能脚本生成 URL 点击统计之外额外进行的。智能脚本 可用于统计点击、曝光，或同时统计两者。
* 通过 智能脚本 实现的浏览型归因仅适用于移动设备，不适用于桌面端。

**要将新安装归因于这些曝光（即浏览型归因）：**

1. 设置 智能脚本 时，请确保您使用 智能脚本 2.3+。
2. 请告知您的开发者在 智能脚本 中<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#fire-an-impression">调用曝光函数</Anchor>。
3. 请确保已开启 <Anchor target="_blank" href="/marketers/zh/docs/measure-view-through-engagements">浏览型归因</Anchor>。

<div id="important-2" />

> 🚧 **重要！**
>
> 自 2023 年 2 月 1 日起（Chrome 110 stable release），Google 已进行一些变更，以<Anchor target="_blank" href="https://developer.chrome.com/en/docs/privacy-sandbox/user-agent/">减少 User-Agent 数据</Anchor>。要使用 OneLink 智能脚本 正确获取<Anchor target="_blank" href="https://www.appsflyer.com/glossary/view-through-attribution/">浏览型归因</Anchor>，您应使用 2.3 及以上版本的 OneLink 智能脚本。

</Accordion>

<div id="additional-information" />

## 更多信息

<div id="faq" />

<Accordion title="常见问题">

<div id="will-the-incoming-url-for-onelink-link-generation-work-if-the-user-browses-to-a-different-page-on-the-website" />

#### **如果用户浏览网站上的其他页面，用于生成 OneLink 链接的传入 URL 还会生效吗？**

是的。传入 URL 参数会在整个会话期间存储，并应用于由 智能脚本 生成的 OneLink 链接的传出参数。如需了解更多实施信息，请<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#preserve-incoming-url-parameters-across-pages">参阅我们的开发者中心</Anchor>。

<div id="why-do-i-get-an-error-when-implementing-smart-script-via-google-tag-manager" />

#### **为什么通过 Google Tag Manager 实施 智能脚本 时会报错？**

有时，您在 AppsFlyer 中生成 智能脚本 并尝试将其插入 Google Tag Manager（GTM）时，会显示「JavaScript too long」错误。如果发生这种情况，请删除 GTM 标签并重新创建一个。

<div id="can-i-add-parameters-that-are-not-listed" />

#### **我可以添加未列出的参数吗？**

是的。在您的 OneLink 智能脚本 页面中，点击 + **新参数** 以映射其他参数。

* 新参数可以是自定义参数，也可以是下拉菜单中未列出的 AppsFlyer 预留参数。
  * 查看您可使用的所有[附加参数](/docs/set-up-smart-script-to-convert-web-visitors#arguments)（参数配置）。
* 使用下拉菜单中的「自定义」选项，并将您的参数添加到 **传出 URL 参数** 字段中。

例如，要将 is\_retargeting 添加为参数，应在 **mapping for** 字段中选择「自定义参数」，然后将 is\_retargeting 参数添加到 **传出 URL 参数** 字段中。

![Smart_Script_Custom.jpg](https://files.readme.io/5a09d18b01ece93bbb47667b676039c98742ebc3b88c5235ad92c7e44d5316b9-small-42045454926609.jpg)

<div id="adset-and-other-parameters-are-not-showing-in-the-dropdown" />

#### **广告组和其他参数未显示在下拉菜单中**

我们建议您在创建或添加新参数时，关闭浏览器中已启用的所有广告拦截器。有时，如果某个选项中包含「广告」一词，广告拦截器会将其移除。

<div id="what-browsers-does-smart-script-work-on" />

#### **智能脚本 支持哪些浏览器？**

智能脚本 使用 Javascript，应可在所有浏览器上运行。

</Accordion>

<div id="specs-and-limitations" />

<Accordion title="规格与限制">

| **规格** | **备注说明** |
| --- | --- |
| URI scheme | 即使在 OneLink 模板中已设置 URI scheme，以便为现有用户打开应用，但对于使用 智能脚本 创建的链接，开发者仍必须将带有 URI scheme 的 af\_dp 参数作为<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#set-additional-custom-parameters">自定义参数</Anchor>添加到 URL 中。 |
| 传入 URL 中的 # | 当处理传入 URL 时，如果其中包含位于查询参数（以「?」表示）之前的井号（「#」）符号，智能脚本 会遇到问题。在这种情况下，智能脚本 会恢复为默认值。 |

</Accordion>

<div data-zendesk-anchors="setup=%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01H95PGMNWR12KQ2P0KT8BBGEC=%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F set-up-onelink-smart-script=%E8%AE%BE%E7%BD%AE-onelink-%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC h_01H95PGMNW6N63XQ1EQSQSHHB2=%E8%AE%BE%E7%BD%AE-onelink-%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC scope-of-work=%E5%B7%A5%E4%BD%9C%E8%8C%83%E5%9B%B4 h_01H95PGMNWPBRHSZBPMKNJ2PS6=%E5%B7%A5%E4%BD%9C%E8%8C%83%E5%9B%B4 h_01H95PGMNWWYRRNVNTK31XYRN3=how-to-create-a-onelink-smart-script h_01H95PGMNW5HA4FWBFW7AR89AV=%E9%87%8D%E8%A6%81 h_01H95PGMNXZAES8DPJ1B4E1QV8=how-to-edit-or-delete-a-script h_01H95PGMNX5ZT7DPV2WBG0CTKB=%E9%87%8D%E8%A6%81-1 h_01H95PGMNXNT9C07B0YTS1KK82=how-to-duplicate-a-script h_01H95PGMNXWJ9V5JW9JEAHF81S=argument-structure h_01H95PGMNXR2HTV1EF07QVQB6W=arguments arguments-parameters-and-values-to-implement-the-smart-script::d4f6bf94=%E7%94%A8%E4%BA%8E%E5%AE%9E%E7%8E%B0%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC%E7%9A%84%E5%8F%82%E6%95%B0%E5%8F%82%E6%95%B0%E5%8F%8A%E5%85%B6%E5%80%BC h_01H95PGMNXPMCM73XT3GTDVAXJ=%E7%94%A8%E4%BA%8E%E5%AE%9E%E7%8E%B0%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC%E7%9A%84%E5%8F%82%E6%95%B0%E5%8F%82%E6%95%B0%E5%8F%8A%E5%85%B6%E5%80%BC h_01H95PGMNX4B8W84DHJR9T4CR2=advanced-arguments arguments-parameters-and-values-to-implement-the-smart-script=%E5%9C%A8%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC%E4%B8%AD%E5%AE%9E%E6%96%BD%E7%9A%84%E9%AB%98%E7%BA%A7%E5%8F%82%E6%95%B0%E5%8F%82%E6%95%B0%E5%92%8C%E5%80%BC h_01H95PGMNXCAHTTJATG75Y3TRN=%E5%9C%A8%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC%E4%B8%AD%E5%AE%9E%E6%96%BD%E7%9A%84%E9%AB%98%E7%BA%A7%E5%8F%82%E6%95%B0%E5%8F%82%E6%95%B0%E5%92%8C%E5%80%BC use-cases=%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF h_01H95PGMNXBPFFNE44YGGECBPR=%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF h_01H95PGMNX3W95JW47YQGSEYQ6=utm-parameters h_01H95PGMNXGZZEMZ6PMAB4XFQQ=google-ads-gclid h_01H95PGMNXZT08G8RTMMG6BQCJ=%E6%B3%A8%E6%84%8F h_01H95PGMNXHJXGB2QXH0YTB6Z0=facebook-click-id h_01KD5EZQFF23MYGXGJF1CF6VPT=tiktok-ttclid-x-twclid-and-snapsccid h_01H95PGMNXBKXFG9M169WG89TK=srns-owned-media-and-other-media-source-links h_01H95PGMNXZPB6CT3ZKJ2KMQ1J=%E7%A4%BA%E4%BE%8B h_01H95PGMNX8Q0BASSESVD06MXE=appsflyer-attribution-links h_01H95PGMNX741EJGPF9G2DS67N=%E7%A4%BA%E4%BE%8B-1 h_01HAS199KS0C0V3G41WGXTK4PF=web-referrer-mapping h_01M1BK4M22YAQ6YX4RZXRKZF7C=seo-referrer-mapping h_01H95PGMNY0P2354ZFVC92TMVC=desktop h_01H95PGMNYDSFP6GJDWC9AE0J2=qr-codes h_01H95PGMNYGJ9BJ86YCP7FYH6G=%E7%A4%BA%E4%BE%8B-2 h_01H95PGMNYZBGZWNFESDTE9GY9=impressions h_01H95PGMNYX1FDT1KK9PQAMX5N=%E9%87%8D%E8%A6%81-2 additional-information=%E6%9B%B4%E5%A4%9A%E4%BF%A1%E6%81%AF h_01H95PGMNYB6A8VKEAH8Z8TDPE=%E6%9B%B4%E5%A4%9A%E4%BF%A1%E6%81%AF h_01H95PGMNYKQ8TNM3KKK9EXANV=faq will-the-incoming-url-for-onelink-link-generation-work-if-the-user-browses-to-a-different-page-on-the-website=%E5%A6%82%E6%9E%9C%E7%94%A8%E6%88%B7%E6%B5%8F%E8%A7%88%E7%BD%91%E7%AB%99%E4%B8%8A%E7%9A%84%E5%85%B6%E4%BB%96%E9%A1%B5%E9%9D%A2%E7%94%A8%E4%BA%8E%E7%94%9F%E6%88%90-onelink-%E9%93%BE%E6%8E%A5%E7%9A%84%E4%BC%A0%E5%85%A5-url-%E8%BF%98%E4%BC%9A%E7%94%9F%E6%95%88%E5%90%97 h_01H95PGMNYM5X2K9J0WZW6PZ8A=%E5%A6%82%E6%9E%9C%E7%94%A8%E6%88%B7%E6%B5%8F%E8%A7%88%E7%BD%91%E7%AB%99%E4%B8%8A%E7%9A%84%E5%85%B6%E4%BB%96%E9%A1%B5%E9%9D%A2%E7%94%A8%E4%BA%8E%E7%94%9F%E6%88%90-onelink-%E9%93%BE%E6%8E%A5%E7%9A%84%E4%BC%A0%E5%85%A5-url-%E8%BF%98%E4%BC%9A%E7%94%9F%E6%95%88%E5%90%97 why-do-i-get-an-error-when-implemeting-smart-script-via-google-tag-manager=%E4%B8%BA%E4%BB%80%E4%B9%88%E9%80%9A%E8%BF%87-google-tag-manager-%E5%AE%9E%E6%96%BD-%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC-%E6%97%B6%E4%BC%9A%E6%8A%A5%E9%94%99 h_01H95PGMNYSQX6BJCN56D4XZZF=%E4%B8%BA%E4%BB%80%E4%B9%88%E9%80%9A%E8%BF%87-google-tag-manager-%E5%AE%9E%E6%96%BD-%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC-%E6%97%B6%E4%BC%9A%E6%8A%A5%E9%94%99 can-i-add-parameters-that-are-not-listed=%E6%88%91%E5%8F%AF%E4%BB%A5%E6%B7%BB%E5%8A%A0%E6%9C%AA%E5%88%97%E5%87%BA%E7%9A%84%E5%8F%82%E6%95%B0%E5%90%97 h_01H95PGMNY2AVJ0CYDAM62Q9PA=%E6%88%91%E5%8F%AF%E4%BB%A5%E6%B7%BB%E5%8A%A0%E6%9C%AA%E5%88%97%E5%87%BA%E7%9A%84%E5%8F%82%E6%95%B0%E5%90%97 adset-and-other-parameters-are-not-showing-in-the-dropdown=%E5%B9%BF%E5%91%8A%E7%BB%84%E5%92%8C%E5%85%B6%E4%BB%96%E5%8F%82%E6%95%B0%E6%9C%AA%E6%98%BE%E7%A4%BA%E5%9C%A8%E4%B8%8B%E6%8B%89%E8%8F%9C%E5%8D%95%E4%B8%AD h_01H95PGMNY97BY6BCPPMYHBF0Q=%E5%B9%BF%E5%91%8A%E7%BB%84%E5%92%8C%E5%85%B6%E4%BB%96%E5%8F%82%E6%95%B0%E6%9C%AA%E6%98%BE%E7%A4%BA%E5%9C%A8%E4%B8%8B%E6%8B%89%E8%8F%9C%E5%8D%95%E4%B8%AD what-browsers-does-smart-script-work-on=%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC-%E6%94%AF%E6%8C%81%E5%93%AA%E4%BA%9B%E6%B5%8F%E8%A7%88%E5%99%A8 h_01H95PGMNY5AV0DTX51X0DJMTK=%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC-%E6%94%AF%E6%8C%81%E5%93%AA%E4%BA%9B%E6%B5%8F%E8%A7%88%E5%99%A8 h_01H95PGMNY4W9X51KV6GM4BSPG=specs-and-limitations" />

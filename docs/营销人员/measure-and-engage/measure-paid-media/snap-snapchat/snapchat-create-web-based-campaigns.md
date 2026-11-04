---
title: 为Snapchat创建网页广告
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-11-27T14:39:44Z'
  edited_at: '2026-10-14T10:01:08Z'
  id: 41365000854161
  locale: zh-cn
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/zh-cn/articles/41365000854161
---
> **概要：** 您可以使用Snapchat Web对接对Snapchat Ads带来的网页到应用转化进行归因

<div id="overview" />

## 概览

AppsFlyer支持网页端获客广告专用的Meta Ads对接（`snapweb_int`），您可以通过Meta的Conversion API（CAPI）上报相关广告的归因和转化数据。Meta可以利用这些数据来优化定向投放、衡量广告效果并打造自定义人群包。

<div id="important" />

> 🚧 **重要提示！**
>
> 目前，Meta Web对接尚不支持通过CAPI发送再营销回传数据。

<div id="prerequisites" />

### 前期准备

在启用Snapchat Web对接前，请确保您已在Snapchat Web对接中开设了企业账户。

<div id="how-to-create-a-snapchat-ads-web-campaign" />

### 如何创建Snapchat Ads网页广告

本文说明了Meta Ads中网页广告的设置方式，适用于通过AppsFlyer衡量投放效果的移动端、PC端和主机端应用。设置流程包括：将Meta Ads与AppsFlyer对接、在两个平台上完成广告活动配置，并使用OneLink Smart Script或OneLink Smart Banners创建落地页。

该流程中必须完成的步骤如下：

* [在AppsFlyer中设置Snapchat Ads网页对接](#在appsflyer中设置snapchat-ads网页对接) （必填）
* 在[Snapchat Ads中设置AppsFlyer对接](#在snapchat-ads中配置appsflyer对接) （必须完成）

该流程中的可选步骤如下：

* [创建带有OneLink智能脚本的落地页](#创建带有onelink智能脚本的落地页)（可选）
* [创建带有OneLink智能横幅的落地页](#创建带有onelink智能横幅的落地页)（可选）

<div id="set-up-snapchat-ads-web-integration-in-appsflyer" />

## 在AppsFlyer中设置Snapchat Ads网页对接

首先激活Snapchat Ads网页对接。然后配置AppsFlyer发送到Events API的回传。

<div id="1-activate-the-snapchat-ads-web-integration" />

<Accordion title="1.激活Snapchat Ads网页对接">

请按以下步骤激活Snapchat Ads网页对接：

1. 从AppsFlyer的侧边栏中选择**协作** > **Partner Marketplace**。
2. 搜索并选择**Snapchat Web**。
3. 点击**设置对接**，然后界面会跳转到活跃对接设置页面。
4. 在**渠道对接**选项卡中，打开**启用该渠道**开关。 在您与该渠道合作期间，请确保该开关总是处于打开（即启用）状态。
5. 关闭**高级隐私保护**开关（设置iOS应用对接时适用）。
6. **Pixel ID：** 输入相关的Pixe ID。您可以按照 [Snapchat Ads 官方文档](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US)中的说明生成或从 Snapchat Ads Manager 获取该数据
7. **Access token（访问令牌）：** 输入相关的token。请按Snapchat Ads官方[文档中说明](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted)生成或获取该ID

</Accordion>

<div id="2-enable-viewthrough-attribution" />

<Accordion title="2.启用浏览型归因">

使用[智能脚本](#创建带有onelink智能脚本的落地页)或[智能横幅](#set-up-smart-banners-landing-page)的落地页时，AppsFlyer支持对Snapchat Web广告系列的浏览型归因。这项功能可以基于概率建模（PMOD），将因广告曝光而触发的App激活进行归因，即使用户并未直接点击广告。

若可用，AppsFlyer还会在给Meta的回传中包含`ScCid`，以提高归因精准度。

**如需启用Snapchat Web的浏览型归因：**

1. 在AppsFlyer中，从侧边栏打开**活动对接**> **Google Ads Web**。
2. 在**对接**选项卡中，下滑到**激活归因**部分。
3. 打开**浏览型激活归因**开关。
4. **[可选]** 开启**跨平台归因具有同等优先级**并设置回溯窗口。有关更多信息，请参见为跨平台展示启用同等优先级。
5. 打开**归因链接**选项卡。
6. 下滑到**浏览型归因**部分并设置**浏览归因回溯窗口**（最长24小时）。
7. 点击**保存对接**以应用您的设置。

</Accordion>

<div id="3-set-inapp-event-postbacks" />

<Accordion title="3.应用内事件回传">

目前只有用户激活才能触发自动的Meta Ads默认回传。对于所有其他事件类型，您可以通过将AppsFlyer事件映射到Snapchat Ads事件来创建自定义回传。您可以在Snapchat Ads后台查看这些回传。

请按以下方式设置应用内事件回传：

1. 打开**应用内事件回传**开关。
2. 根据实际需求设置应用内事件回传窗口（详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">应用内事件回传</Anchor>窗口配置）。
3. 点击**添加事件**，将相关事件添加到列表中。
4. 在**AppsFlyer事件**一列，从下拉菜单中选择相关的事件名称。AppsFlyer会通过已接入您应用的SDK或S2S事件来获取该事件的名称信息。
5. 在**映射到渠道事件**列<strong>中，</strong>从列表中选择最合适的预定义渠道事件。
6. 在**事件来源**一列，选择**仅限该合作渠道**，确保仅回传Meta Ads带来的用户所完成的事件。
7. 在**包括**列中，选择是否将事件与其收入值一起发送。请见回传中包含的数据。

   <div id="note" />

   > 📘 **注意**
   >
   > * 如果您设置的是购买事件，请将**包含**列设为**值和收入**。选择其他选项将导致回传失败。
   > * 目前，仅购买事件支持包含收入。

8. 【可选】点击**添加条件**图标，设置事件的<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">映射条件</Anchor>。
9. 点击**保存对接**。
10. 【可选】保存对接后，在配置页面停留期间，您可以与该渠道对接其他应用：
    1. <span class="af-ol-a"></span>点击页面左上角渠道名称下方的应用名称，打开应用列表。
    2. 从列表中选择其他应用。
    3. 对所选应用重复上述步骤。

</Accordion>

<div id="set-up-appsflyer-integration-in-snapchat-ads" />

## 在Snapchat Ads中配置AppsFlyer对接

本节所述步骤主要在Snapchat Ads Manager中完成。

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1.设置投放类型、投放目标和转化目标">

您可以选择从 AppsFlyer 发送的任何预定义 INAPP 事件作为您的营销活动目标，或者如果您想针对移动应用安装进行优化，请选择“PAGE\_VIEW”。

<div id="warning" />

> ❗️ **重要提示**
>
> 切勿选择<strong>应用事件，</strong>否则Snapchat会通过SRN API认领这些转化，导致报告和优化不一致。

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. 设置目标网址（Destination URL）">

1. 在**Destination**下的**Website URL**部分中，输入相关URL，作为用户点击广告后访问的页面。请将此处的URL设置为以下任一网址：
   * 落地页 **-** 适用于以下场景：

     * 您的应用在多个平台发布。
     * 您希望通过落地页更详细地介绍您要推广的产品。
     * 您希望通过落地页收集更多数据。

     在以上所有场景中都可以使用带有[智能脚本](#创建带有onelink智能脚本的落地页)或[智能横幅](#创建带有onelink智能横幅的落地页)的落地页。
   * AF归因链接<strong>：</strong> 如果您不想让用户访问落地页，而是直接跳转到商店并下载相关应用，建议您使用AF归因链接（包括OneLink链接、单平台链接和跨平台链接）作为目标网址。
2. 点击**Build a URL parameter**，将链接参数添加到该URL中（落地页地址或AF归因链接都适用）。
3. 在**Custom parameters**下点击**Add parameter**。

   [<Image alt="" src="https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png" width="2810px" />Screenshot 2024-06-11 at 8.44.30.png](https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png)
4. 将AppsFlyer参数映射到Snapchat中对应的值。
   * 如果您的目标网址是**落地页、OneLink归因链接或单平台归因链接**，请将以下AF参数映射到Meta侧的对应参数：

| AF参数 | 映射的Snapchat值 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `snapweb_int` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_channel`</Anchor> | `{{site_source_name}}` |

     完成上述步骤后，可得到如下URL：

     ```
     https://app.appsflyer.com/{app_id}?pid=snapweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
     ```

     * 如果您通过Google Play Store以外的方式提供相关应用的APK，请在URL中添加<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor>参数，并将其映射到该应用的下载地址，如`https://Add-your-store-url.com`

* 如果您的目标网址是**PC或主机端的应用商店**，请按下表说明创建链接。如需了解其他相关信息，请参阅 <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV、PC和主机平台的直接归因链接</Anchor>

| 归因链接结构 |  |
| --- | --- |
| 基础链接 | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| 必须配置的路径参数 | ▪ platform例如: steam  <br />▪ app\_id示例：123456 |
| 必须配置的查询参数 | ▪ af\_media\_source  <br />▪ af\_campaign\_id  <br />▪ af\_r |
| 其他参数 | <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links#参数">查看所有参数</Anchor> |
| 链接结构 | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

  将以下AppsFlyer参数映射到Meta侧的对应参数：

| AF参数 | 映射的Snapchat值 |
| --- | --- |
| `af_media_source` | `snapweb_int` |
| `af_campaign` * | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_channel`</Anchor> | `{{site_source_name}}` |

  * 为了简化广告系列分析，请在广告系列名称中以前缀或后缀的形式添加广告系列类型，即网页或移动端（如campaign-name\_web）

  跨平台URL的示例：

  ```
  https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
  ```

  <div id="note-1" />

  > 📘 **注意**
  >
  > 用户点击相关广告时，Meta会自动将`ScCid={{ScCid}}`添加到目标网址（ destination URL）。


  > 📄
  >
  > 如需全面了解AF链接参数的详细信息，请参考<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#归因链接参数">此文档</Anchor>。


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-script" />

## 创建带有OneLink智能脚本的落地页

**用户链路：** 用户点击Meta广告后跳转到您的移动端网站，并进入一个带有CTA按钮的网页，引导用户从一个或多个平台下载您的应用。用户点击该按钮后，就会跳转到相应的商店。

<div id="endtoend-data-flow" />

<Accordion title="整个链路中的数据流">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. Snapchat广告的URL中包含`pid=snapweb_int`参数。当用户点击该广告时，参数会被自动添加到该广告URL的末尾。
2. 用户跳转到指定的目标网址——即一个带有智能脚本的落地页。
3. 在该落地页加载时，智能脚本会向AppsFlyer发送一个展示，其中包含从Meta传入落地页的URL参数。AppsFlyer可通过该展示对落地页进行浏览型归因。如需进一步了解广告展示和浏览型归因，请参阅<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">此文档</Anchor>。
4. 智能脚本会根据传入链接中的参数，为落地页的CTA按钮生成传出链接，其中包含`ScCid`参数（这里的传入链接是指从广告进入落地页的链接，传出链接是指从落地页跳转到其他地址的链接）。这些按钮可以引导用户：
   * 进入Google Play和App Store（通过OneLink归因链接实现）。
   * 进入多个平台的商店（例如CTV、Epic和Steam）。在此场景中，智能脚本会针对各个平台生成一条单平台归因链接，用户点击后会跳转到对应平台的商店。
   * 在用户设备中下载APK文件。
5. 用户点击CTA按钮后，AppsFlyer会收到并记录该次点击。
6. 用户跳转到相应的商店并下载该应用。
7. 用户打开该应用时，AppsFlyer会记录到一个激活。
8. 如果激活数据中带有可用的[install referrer](https://www.appsflyer.com/glossary/install-referrer/)，AppsFlyer会根据概率模型或确定性归因逻辑对这个激活进行归因。
9. AF会生成一条带有`ScCid`参数以及其他事件参数的回传，并通过Events API将其发送到Snapchat。Google通过参数来识别相关点击，并使用其他参数对具体广告系列的投放进行优化。

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="设置带有智能脚本的落地页">

如需在您的Meta Ads广告投放中使用智能脚本，请按以下方式操作：

1. 为您要投放的广告系列设置一个OneLink模板，用于生成相关的OneLink归因链接。详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink模板的创建方式</Anchor>说明。
2. 创建一个智能脚本。详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink智能脚本的创建方式</Anchor>说明。

   <div id="note-5" />

   <div id="note-2" />

   > 📘 **注意**
   >
   > 下文内容主要针对使用智能脚本的Snapchat Ads广告系列，说明了具体的设置步骤。如需了解更具普适性的智能脚本投放设置方式，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink智能脚本V2设置说明</Anchor>中的<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink智能脚本创建方式</Anchor>部分。

3. 请确保所有相关的URL参数都已添加到传入链接末尾。如需检查附加在传入链接末尾的参数，请打开Snapchat Ads Manager，查看您在创建目标网址（Destination URL）时设置的URL参数。详情请见[目标网址（destination URL）的设置说明](#2-set-destination-url)部分。
4. 将Snapchat Ads广告系列所需的传入URL参数映射到传出URL参数。当用户点击CTA按钮时，这些参数会发送到AppsFlyer：
   * **PID**：确保智能脚本从传入链接中提取`pid=snapweb_int`参数，并将其映射到传出链接中对应的参数。
   * **ScCid**：如需将应用内事件回传成功发送到Snapchat，必须配置该 `ScCid` 参数。必须在`ScCid`智能脚本ScCid页面的URL参数映射部分手动配置参数的映射。

     1. 在**映射对象**一栏中选择**自定义参数**。
     2. 在**出链参数**和**入链参数**字段中输入**ScCid**。

     <div id="note-3" />

     > 📘 **注意**
     >
     > 如需使相关数据呈现在AppsFlyer的原始数据报告中，必须将传入的`ScCid`参数同时映射到传出的`ScCid`参数和传出的`af_sub[1–5]`参数。


</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="设置带有智能脚本的跨平台落地页">

如需在您的Meta Ads广告投放中使用带有智能脚本的跨平台落地页，请按以下方式操作：

1. 为您要投放的广告系列设置一个OneLink模板，用于生成相关的OneLink归因链接。详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink模板的创建方式</Anchor>说明。
   * 请参考此文档中的说明，将您的OneLink模板应用于跨平台归因。详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-cross-platform-links-for-multi-device-campaigns#创建或编辑onelink模板用于跨平台归因">创建OneLink模板</Anchor>，用于跨平台归因。
2. 请确保所有相关的URL参数都已添加到传入链接末尾。如需查看附加在传入链接末尾的参数，请打开Meta Ads Manager，检查您在创建目标网址（Destination URL）时设置的URL参数。详情请见[目标网址（destination URL）的设置说明](#2-set-destination-url)部分。
3. 为每个传入参数确定要映射到的传出参数。例如，传入链接中的传入`af_site_id`参数将映射到传出链接中的`af_site_id`参数。
4. 请列出必要传出参数（即不能出现空值的参数）的默认值。
5. 向您的开发人员发送以下信息：
   * 您的传入-传出参数的映射方式。开发人员会创建一个脚本，根据您指定的传入-传出参数的对应关系，生成传出的直接访问链接。
   * 各参数的默认值。脚本若未在传入的链接中发现对应的参数值，就会使用默认值来填充传出链接中的参数。
   * 如果您使用OneLink归因链接，请将相关域名和模板ID发送给您的开发人员，用于创建传出的OneLink链接。域名和模板ID的格式为`yourbrand.onelink.me/A1b2`，若您使用品牌域名，则为`click.yourbrand.com/A1b2`
   * 将以下Dev Hub文档发送给您的开发人员：
     * 创建可直接访问非移动端页面的传出链接时，请参考这些[说明及代码示例](https://dev.appsflyer.com/hc/docs/create-direct-click-url)。
     * 创建跨平台落地页时，请参考这些[演示和说明](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/)。

* 提醒开发人员务必在传出链接中加入传入参数`ScCid`的映射。

  <div id="note-4" />

  > 📘 **注意**
  >
  > 如需使相关数据呈现在AppsFlyer的原始数据报告中，必须将传入的`ScCid`参数同时映射到传出的`ScCid`参数和`af_sub[1-5]`参数。


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## 创建带有OneLink智能横幅的落地页

**用户链路：** 用户点击Meta广告后跳转到您的移动端网站，并进入一个展示智能横幅的页面，该横幅中带有CTA按钮，引导用户从对应的应用商店下载相关应用。

<div id="endtoend-data-flow::b905b9a5" />

<Accordion title="整个链路中的数据流">

1. Snapchat广告的URL中包含`pid=snapweb_int`参数。当用户点击该广告时，参数会被自动添加到该广告URL的末尾。
2. 用户跳转到指定的目标网址——即一个带有智能横幅的落地页。
3. 落地页加载的同时，智能横幅会向AppsFlyer发送一条<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">展示</Anchor>，其中包含传入链接参数（传入链接是指从广告进入落地页的链接）。有了这条展示数据，AppsFlyer就能通过浏览型归因将转化匹配到落地页。如需进一步了解展示和浏览型归因，请参考<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">创建自定义展示URL</Anchor>。
4. 智能横幅针对该横幅中的CTA按钮，生成传出的URL。生成的传出链接以传入链接中的参数（包括`ScCid`）为基础。智能横幅只能生成OneLink链接。
5. 当用户点击智能横幅中的CTA按钮时，AppsFlyer就会接收并记录该次点击。
6. 用户跳转到相应的商店并下载该应用。
7. 用户打开该应用时，AppsFlyer会记录到一个激活。
8. 如果激活数据中带有可用的install referrer，AppsFlyer会根据概率模型或确定性归因逻辑对这个激活进行归因。
9. AF会生成一条带有`ScCid`参数以及其他事件参数的回传，并通过Events API将其发送到Snapchat。Google通过参数来识别相关点击，并使用其他参数对具体广告系列的投放进行优化。

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="设置带有智能横幅的落地页">

如需在您的Meta Ads广告投放中使用智能横幅，请按以下方式操作：

1. 为您要投放的广告系列设置一个OneLink模板，用于生成相关的OneLink归因链接。详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink模板的创建方式</Anchor>说明。
2. 创建一个智能横幅。

   > 📘 **注意**
   >
   > 下文内容主要针对使用智能横幅的Snapchat Ads广告系列，说明了具体的设置步骤。如需了解更具普适性的智能脚本投放设置方式，请参考<Anchor target="_blank" href="/marketers/zh/docs/smart-banners-mobile-web-to-app-for-marketers">《智能横幅——移动端网页到应用解决方案（市场人员专用）》</Anchor>文档中的<Anchor target="_blank" href="/marketers/zh/docs/smart-banners-mobile-web-to-app-for-marketers#设置">设置</Anchor>部分。

3. 设置智能横幅参数，用于Snapchat Ads广告：

   * 请确保所有相关的URL参数都已添加到传入链接末尾。
   * 如需查看附加在传入链接末尾的参数，请打开Snapchat Ads Manager，检查您在[创建目标网址](#2-set-destination-url)（Destination URL）时设置的URL参数。

   <div id="note-6" />

   > 📘 **注意**
   >
   > 其中最重要的两个参数是`pid=snapweb_int`和`ScCid`。请务必确保传入链接中包含这两个参数，这样智能横幅才能收集相关信息。如果缺少这两个参数，就无法对相关流量进行归因，也无法向Meta Ads发送回传。


</Accordion>

<div id="view-web-to-app-attribution-data" />

## **查看网页至应用归因数据**

虽然网页端转化事件是通过原始的`snapweb_int` PID发送到Snapchat的，但AppsFlyer面板和原始数据报告会通过`snapchat_int` PID上报。这既适用于主要转化事件，也适用于转化辅助事件。

该统一报告视图使您能够在同一位置分析网页和应用广告活动绩效，包括全面的移动端和网络端成本报告。

<div id="view-in-the-dashboard" />

### **面板中的视图**

所有Snapchat的网页到应用归因都会显示在数据总览和活跃面板的`snapchat_int`下。这样，您就可以一站式查看跨平台的广告投放效果。您可以使用标准的筛选条件和细分条件来对比Snapchat数据中的应用流量和网页流量。

<div id="view-in-raw-data-and-api-reports" />

### **在原始数据和API报告中查看**

* **原始数据导出和API响应**在Google网页活动的`media_source`字段中包含`snapchat_int`PID。要验证网页广告设置的详细信息，请参阅`original_url`字段，其中显示的`snapchat_int`是网页广告创建过程中使用的PID。
* **回传报告**显示`snapweb_int`为回传发送到的原始媒体渠道。

<div id="traits-and-limitations" />

## 特性与局限性

| 特点 | 说明 |
| --- | --- |
| 成本数据 | 系统不会自动获取Meta Ads（`snapweb_int`）网页广告的成本数据。您需通过以下两种方式之一手动导入：通过电子邮件上传文件，或通过AppsFlyer主机端界面手动上传。此规则适用于所有用户，包括ROI360订阅用户。 |
| 点击和展示（暂时受限） | 网页广告的点击和展示暂时无法从Snapchat SRN（`snapchat_int`）获取。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A7%88 h_01KB2W28THC55F0AJ0KZJPQ6S5=%E6%A6%82%E8%A7%88 h_01KB2W28THSST3148Y5Y07PJ7S=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA prerequisites=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01KB2W28THW7E6TRVTTHJZ9BP4=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 how-to-create-a-snapchat-ads-web-campaign=%E5%A6%82%E4%BD%95%E5%88%9B%E5%BB%BAsnapchat-ads%E7%BD%91%E9%A1%B5%E5%B9%BF%E5%91%8A h_01KB2W28THTST7HWTJA9TTGPGG=%E5%A6%82%E4%BD%95%E5%88%9B%E5%BB%BAsnapchat-ads%E7%BD%91%E9%A1%B5%E5%B9%BF%E5%91%8A set-up-snapchat-ads-web-integration-in-appsflyer=%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEsnapchat-ads%E7%BD%91%E9%A1%B5%E5%AF%B9%E6%8E%A5 h_01KB2W28THQJF8K4AWTRXNA3RX=%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEsnapchat-ads%E7%BD%91%E9%A1%B5%E5%AF%B9%E6%8E%A5 h_01KB2W28TH6NZCGCJAN8K3WFGA=1-activate-the-snapchat-ads-web-integration h_01KB2W28TJ6XY7WKR4VC5XS7DS=2-enable-viewthrough-attribution h_01KB2W28TJGRKP3C50ZPQAWAS9=3-set-inapp-event-postbacks h_01KB2W28TJ14KC606KE82Q7BB7=%E6%B3%A8%E6%84%8F set-up-appsflyer-integration-in-snapchat-ads=%E5%9C%A8snapchat-ads%E4%B8%AD%E9%85%8D%E7%BD%AEappsflyer%E5%AF%B9%E6%8E%A5 h_01KB2W28TJVZ1BX94SZYH1K5EM=%E5%9C%A8snapchat-ads%E4%B8%AD%E9%85%8D%E7%BD%AEappsflyer%E5%AF%B9%E6%8E%A5 h_01KB2W28TJ2R95JK7C1PQE644C=1-set-the-campaign-type-objective-and-goals h_01KB2W28TJ4BK88DVYJG4XYE0S=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 h_01KB2W28TJB1V382HD09M9Y0C3=2-set-destination-url h_01KB2W28TJT7QZ2P7AZ5X61ZXV=%E6%B3%A8%E6%84%8F-1 create-a-landing-page-with-onelink-smart-script=%E5%88%9B%E5%BB%BA%E5%B8%A6%E6%9C%89onelink%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC%E7%9A%84%E8%90%BD%E5%9C%B0%E9%A1%B5 h_01KB2W28TJQA1TBXXQ7MA1F0CB=%E5%88%9B%E5%BB%BA%E5%B8%A6%E6%9C%89onelink%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC%E7%9A%84%E8%90%BD%E5%9C%B0%E9%A1%B5 h_01KB2W28TJ4J426HD3ZFHXAV4J=endtoend-data-flow h_01KB2W28TJR8S029FJ3Y81MG8Y=set-up-a-smart-script-landing-page h_01KB2W28TJBYHKYNQRMJ4ZGWYD=%E6%B3%A8%E6%84%8F-2 h_01KB2W28TJZMQEDSNVWRZCNXYD=%E6%B3%A8%E6%84%8F-3 h_01KB2W28TJT0TEFB97RXEGDVRM=set-up-a-smart-script-crossplatform-landing-page h_01KB2W28TJ6XWR7GW4SQQAKZH9=%E6%B3%A8%E6%84%8F-4 create-a-landing-page-with-onelink-smart-banners=%E5%88%9B%E5%BB%BA%E5%B8%A6%E6%9C%89onelink%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85%E7%9A%84%E8%90%BD%E5%9C%B0%E9%A1%B5 h_01KB2W28TJM0X7K5Z7M2120MT9=%E5%88%9B%E5%BB%BA%E5%B8%A6%E6%9C%89onelink%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85%E7%9A%84%E8%90%BD%E5%9C%B0%E9%A1%B5 h_01KB2W28TKJZBNFR335SXKY6FC=endtoend-data-flow::b905b9a5 h_01KB2W28TKKA9NTQEC7ZA9E6EA=set-up-a-smart-banners-landing-page h_01KB2W28TKW8B6H4W0R9YJM3ZE=%E6%B3%A8%E6%84%8F-5 h_01KB2W28TKRH3NC73J2JHNSMWD=%E6%B3%A8%E6%84%8F-6 view-webtoapp-attribution-data=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E8%87%B3%E5%BA%94%E7%94%A8%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01KB2W28TKDAV34JGYJKF2VT43=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E8%87%B3%E5%BA%94%E7%94%A8%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE view-in-the-dashboard=%E9%9D%A2%E6%9D%BF%E4%B8%AD%E7%9A%84%E8%A7%86%E5%9B%BE h_01KB2W28TKNWYXJX189EP2HPN2=%E9%9D%A2%E6%9D%BF%E4%B8%AD%E7%9A%84%E8%A7%86%E5%9B%BE view-in-raw-data-and-api-reports=%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%92%8Capi%E6%8A%A5%E5%91%8A%E4%B8%AD%E6%9F%A5%E7%9C%8B h_01KB2W28TKJ1MAMM00KY3M3S2W=%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%92%8Capi%E6%8A%A5%E5%91%8A%E4%B8%AD%E6%9F%A5%E7%9C%8B traits-and-limitations=%E7%89%B9%E6%80%A7%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01KB2W28TKFY74YBXHD91QP9V0=%E7%89%B9%E6%80%A7%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />

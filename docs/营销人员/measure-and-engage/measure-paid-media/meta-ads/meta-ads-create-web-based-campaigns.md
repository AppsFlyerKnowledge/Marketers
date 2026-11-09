---
title: Meta Ads网页广告的投放配置说明
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
  created_at: '2024-06-04T16:08:28Z'
  edited_at: '2026-10-14T10:02:13Z'
  id: 25646834966033
  locale: zh-cn
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/zh-cn/articles/25646834966033
---
> **概要：** 您可以使用Meta Web对接对Meta Ads带来的网页到应用转化进行归因。

<div id="overview" />

## 速览

AppsFlyer支持网页端获客广告专用的Meta Ads对接（`metaweb_int`），您可以通过Meta的Conversion API（CAPI）上报相关广告的归因和转化数据。然后，Meta就可以利用这些数据来优化定向投放、衡量广告效果并打造自定义人群包。

<div id="note" />

> 📘 **注意**
>
> 目前，Meta Web对接尚不支持通过CAPI发送再营销回传数据。

<div id="prerequisites" />

### 前期准备

在启用Meta Ads对接前，请确保您已在[Meta Business Manager](https://www.facebook.com/business/help/1710077379203657?id=180505742745347)中开设了企业账户。

<div id="how-to-create-a-meta-web-ads-campaign" />

### 如何创建Meta Web广告活动

本文说明了Meta Ads中网页广告的设置方式，适用于通过AppsFlyer衡量投放效果的移动端、PC端和主机端应用。设置流程包括：将Meta Ads与AppsFlyer对接、在两个平台上完成广告活动配置，并使用OneLink Smart Script或OneLink Smart Banners创建落地页。  
该流程中必须完成的步骤如下：

* [在AppsFlyer中设置Meta Web对接](#在appsflyer中设置meta-web对接) （必须完成）
* [在Meta Ads中设置AppsFlyer对接](#在meta-ads中配置appsflyer对接) （必须完成）

该流程中的可选步骤如下：

* [创建带有OneLink智能脚本的落地页](#创建带有onelink智能脚本的落地页)（可选）
* [创建带有OneLink智能横幅的落地页](#创建带有onelink智能横幅的落地页)（可选）

<div id="set-up-meta-web-ads-integration-in-appsflyer" />

## 在AppsFlyer中设置Meta Web对接

请先在AppsFlyer后台启用Meta Web对接，并设置AppsFlyer向CAPI发送回传的方式。

<div id="a-activate-the-meta-ads-integration" />

<Accordion title="1. 激活Meta Web广告对接">

请按以下方式启用Meta Web对接：

1. 在AppsFlyer面板的左侧菜单栏中点击**协作** > **Partner Marketplace**。
2. 搜索并选择**Meta Web**。
3. 点击**设置对接**，然后界面会跳转到**活跃对接**设置页面。
4. 在**渠道对接**选项卡中，打开**启用该渠道**开关。**请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开（即<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">启用</Anchor>）状态。
5. 关闭**高级隐私保护开关** （设置iOS应用对接时适用）。
6. 填写**Pixel ID**字段。您可以从Meta ads Manager后台获取Pixel ID信息，具体方式如下：
   1. <span class="af-ol-a"></span>在[Ads manager](https://www.facebook.com/ads/manager)侧边栏菜单中，向下滚动到**All tools** > **Events Manager**。 **请注意：** 请确保您在右上角的下拉菜单中选择的业务（Business）正确无误。
   2. 从**Events Manager**侧边栏菜单中选择**Data sources**。您会看到一个pixel列表。 如果您选定的业务尚无pixel，可以在该窗口中创建一个pixel。
   3. 复制该pixel名称下方的pixel ID，  
      并将其粘贴到  
      AppsFlyer面板中的**Pixel ID**字段。
7. 填写**Access Token**字段。您可以按照[这里的说明](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)来获取该token信息。
8. 打开<strong>限制Meta Ads对用户个人信息的使用（CCPA）</strong>开关，以确保数据的使用方式符合相关的<Anchor target="_blank" href="/marketers/zh/docs/send-opendsr-api-requests">数据保护法</Anchor>规定。**请注意：** CCPA隐私条例限制他人使用加州的用户所产生的数据，因此CCPA合规后，Meta Ads上这类用户的数据可用性有限。

</Accordion>

<div id="d-enable-view-through-attribution-for-meta-web" />

<Accordion title="2. 启用浏览型归因">

AppsFlyer支持通过启用[智能脚本](#set-up-smart-script-crossplatform-landing-page)或[智能横幅](#set-up-smart-banners-landing-page)的落地页，对Meta Web广告系列进行浏览型归因。这项功能可以基于概率模型(PMOD)，将因广告曝光而触发的App激活进行归因，即使用户并未直接点击广告。

当用户点击Meta Web广告并进入[智能脚本](#set-up-smart-script-crossplatform-landing-page)或[智能横幅](#set-up-smart-banners-landing-page)落地页时，AppsFlyer可以将该活动与后续的应用安装进行匹配。如果可用，回传中将包含`fbclid`以提高归因准确性。

**如需启用Meta Web的浏览型归因:**

1. 在AppsFlyer中，从侧边栏打开**活跃对接**> **Meta web ads**。
2. 在**对接**选项卡中，下滑到**激活归因**部分。
3. 打开**浏览型激活归因**开关。
4. **[可选]** 开启**跨平台归因具有同等优先级**并设置回溯窗口。有关更多信息，请参见<Anchor target="_blank" href="/marketers/zh/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">为跨平台展示启用同等优先级</Anchor>。
5. 打开**归因链接**选项卡。
6. 下滑到**浏览型归因**部分并设置**浏览归因回溯窗口**（最长24小时）。
7. 点击**保存对接**以应用您的设置。

</Accordion>

<div id="b-set-inapp-event-postbacks" />

<Accordion title="3. 应用内事件回传">

目前只有用户激活才能触发自动的Meta Ads默认回传。如需回传其他类型的事件，可以将AppsFlyer事件映射到Meta Ads事件（请在[Meta Events Manager](https://www.facebook.com/business/help/1541268312717919?id=818859032317965)中查看Meta侧的事件名称信息），从而创建自定义回传。  
请按以下方式设置应用内事件回传：

1. 打开**应用内事件回传**开关。
2. 根据实际需求设置应用内事件回传窗口。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">应用内事件回传窗口配置</Anchor>。
3. 点击**添加事件**，将相关事件添加到列表中。
4. 在**AppsFlyer事件**一列，从下拉菜单中选择相关的事件名称。AppsFlyer会通过已接入您应用的SDK或S2S事件来获取该事件的名称信息。
5. 在**渠道映射事件**一列，从下拉菜单中选最合适的渠道侧预定义事件，或选择自定义事件（CUSTOM）。
6. 在**用户来源**列中，选择事件的发送选项：
   * **仅该合作渠道**：仅回传归因到Meta ads的事件。
   * **所有媒体渠道，包括自然流量**：回传归因到任何渠道以及自然量的事件。
7. 在**包括**列中，选择是否将事件与其收入值一起发送。请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#回传内容">回传中包含的数据</Anchor>。

   <div id="note-2" />

   <div id="note-1" />

   > 📘 **注意**
   >
   > 如果您设置的是购买事件，请将**包含**列设为**值和收入**。选择其他选项将导致回传失败。

8. 【可选】点击**添加条件**图标，设置事件的<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">映射条件</Anchor>。
9. 点击**保存对接**。
10. 【可选】您可以在保存对接后留在配置页面，将其他应用也对接到该渠道：
    1. <span class="af-ol-a"></span>点击页面左上角渠道名称下方的应用名称，打开应用列表。
    2. 在下拉菜单中选择一个其他应用。
    3. 为选定应用完成对接流程。

</Accordion>

<div id="set-up-appsflyer-integration-in-meta-ads" />

## 在Meta Ads中配置AppsFlyer对接

本节所述步骤主要在Meta Ads Manager中完成。

<div id="a-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. 设置投放类型、投放目标和转化目标">

1. 登入Meta Ads并创建一个广告系列。
2. 在**Campaign objective**部分中选择以下任一选项：
   * **Sales**：该选项能让Meta针对某个具体事件进行优化（比如您的主要KPI事件）。
   * **Traffic**：该选项能让Meta针对广告点击进行优化。建议您仅在没有其他KPI或其他KPI事件的流量太低时使用该选项。
3. 【可选】如果您想要在上述选项中添加自定义的投放目标，请按以下方式操作：
   1. <span class="af-ol-a"></span>在Meta Ads中选择一个要作为投放目标的自定义事件，并将其标记为转化行为（conversion action）。
   2. 进入AppsFlyer面板，在**Meta Web**对接页面中的**应用内事件**部分选择一个AppsFlyer事件，将其映射到渠道侧的自定义事件（在**渠道映射事件**一列中选择CUSTOM），并使用Meta Ads中的转化行为名称（conversion action）为其命名。

      <div id="note-3" />

      > 📘 **注意**
      >
      > 如需进一步了解Meta的投放目标（Campaign Objectives），请参阅[Meta提供的相关说明](https://www.facebook.com/business/help/175683976191028)。

4. 将<strong>转化位置（conversion location）</strong>设置为**Website**。[![](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)
5. 请确保**Pixel**字段的值与您在AppsFlyer中为Meta Web对接（`metaweb_int`）所配置的Pixel ID完全一致。如需进一步了解Meta Pixel，请参阅[Meta提供的相关说明](https://www.facebook.com/business/help/742478679120153)（需登录）。
6. 点击**Next**。

</Accordion>

<div id="b-set-destination-url" />

<Accordion title="2. 设置目标网址（Destination URL）">

1. 在**Destination**下的**Website URL**部分中，输入相关URL，作为用户点击广告后访问的页面。请将此处的URL设置为以下任一网址：

   <Image align="center" alt="" src="https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png" />

   * **落地页 -** 适用于以下场景：

     * 您的应用在多个平台发布。
     * 您希望通过落地页更详细地介绍您要推广的产品。
     * 您希望通过落地页收集更多数据。

     在以上所有场景中都可以使用带有[智能脚本](#创建带有onelink智能脚本的落地页)或[智能横幅](#创建带有onelink智能横幅的落地页)的落地页。
   * **AF归因链接**：如果您不想让用户访问落地页，而是直接跳转到商店并下载相关应用，建议您使用AF归因链接（包括OneLink链接、单平台链接和跨平台链接）作为目标网址。

     <div id="important" />

     > 🚧 **重要提示！**
     >
     > 部分情况下，AF归因链接无法正常生效。如果发生这种情况，请向您的Meta客户经理咨询解决方案，或直接使用落地页作为目标网址。

2. 点击**Build a URL parameter**，将链接参数添加到该URL中（落地页地址或AF归因链接都适用）。
3. 在**Custom parameters**下点击**Add parameter**。

   <Image align="center" alt="4.png" src="https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png" />
4. 将AppsFlyer参数映射到Meta中对应的值。

   * 如果您的目标网址是**落地页、OneLink归因链接或单平台归因链接**，请将以下AF参数映射到Meta侧的对应参数： 

| AF参数 | Meta映射值 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     完成上述步骤后，可得到如下URL：

     ```http
     https://app.appsflyer.com/{app_id}?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={https://Add-your-store-url.com}
     ```

     * 如果您通过Google Play Store以外的方式提供相关应用的APK，请在URL中添加<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor>参数，并将其映射到该应用的下载地址，如`https://Add-your-store-url.com`
   * 如果您的目标网址是**PC或主机端的应用商店**，请按下表说明创建链接。如需了解其他相关信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV、PC和主机平台的直接归因链接</Anchor>

<table><thead><tr><th colspan="2">归因链接结构</th></tr></thead><tbody><tr><td>基础链接</td><td>engagements.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>必须配置的路径参数</td><td><ul><li>platform<br/>示例：steam</li><li>app_id<br/>示例：123456</li></ul></td></tr><tr><td>必须配置的查询参数</td><td><ul><li>af_media_source</li><li>af_campaign_id</li><li>af_r</li></ul></td></tr><tr><td>其他参数</td><td><a href="./ctv-pc-and-console-platform-direct-attribution-links#参数" target="_blank">查看所有参数</a></td></tr><tr><td>链接结构</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr></tbody></table>

     将以下AppsFlyer参数映射到Meta侧的对应参数：

| AF参数 | Meta映射值 |
| --- | --- |
| `af_media_source` | `metaweb_int` |
| `af_campaign` | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     跨平台URL的示例：

     ```http
     https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
     ```

   <div id="note-4" />

   > 📘 **注意**
   >
   > 用户点击相关广告时，Meta会自动将`fbclid={{fbclid}}`添加到目标网址（ destination URL）。


   <div id="tip" />

   > 👍 **提示**
   >
   > 为了简化活动分析，请在活动名称中包含活动类型、网页或移动，作为前缀或后缀（例如，活动名称\_web）


<div id="note-5" />

> 📘 **注意**
>
> 如需全面了解AF链接参数的详细信息，请参考<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#归因链接参数">此文档</Anchor>。

</Accordion>

<div id="c-select-tracked-events" />

<Accordion title="3. 选择需要监测的事件（tracked events）">

在Tracking部分中选择需通过相关广告促成的转化事件（这些事件的设置在[Event Manager](https://www.facebook.com/business/help/898185560232180?id=1205376682832142)中完成）。

<Image align="center" alt="" src="https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png" />

<div id="important-1" />

> 🚧 **重要提示！**
>
> 切勿选择**App Events**，否则Meta会通过SRN API来认领这些转化，从而造成数据上报和投放优化之间发生错配。

</Accordion>

<div id="note-6" />

<div id="create-a-landing-page-with-onelink-smart-script" />

## 创建带有OneLink智能脚本的落地页

**用户链路：** 用户点击Meta广告后跳转到您的移动端网站，并进入一个带有CTA按钮的网页，引导用户从一个或多个平台下载您的应用。用户点击该按钮后，就会跳转到相应的商店。

<div id="end-to-end-data-flow" />

<Accordion title="整个链路中的数据流">

<Image align="center" alt="" src="https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png" />

1. Meta广告的URL中包含`pid=metaweb_int`参数。当用户点击该广告时，`fbclid`参数会被自动添加到该广告URL的末尾。
2. 用户跳转到指定的目标网址——即一个带有智能脚本的落地页。
3. 在该落地页加载时，智能脚本会向AppsFlyer发送一个展示，其中包含从Meta传入落地页的URL参数。AppsFlyer可通过该展示对落地页进行浏览型归因。如需进一步了解广告展示和浏览型归因，请参阅<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">此文档</Anchor>。
4. 智能脚本会根据传入链接中的参数，为落地页的CTA按钮生成传出链接，其中包含`fbclid`参数（这里的传入链接是指从广告进入落地页的链接，传出链接是指从落地页跳转到其他地址的链接）。这些按钮可以引导用户：
   * 进入Google Play和App Store（通过OneLink归因链接实现）。
   * 进入多个平台的商店（例如CTV、Epic和Steam）。在此场景中，智能脚本会针对各个平台生成一条单平台归因链接，用户点击后会跳转到对应平台的商店。
   * 在用户设备中下载APK文件。
5. 用户点击CTA按钮后，AppsFlyer会收到并记录该次点击。
6. 用户跳转到相应的商店并下载该应用。
7. 用户打开该应用时，AppsFlyer会记录到一个激活。
8. 如果激活数据中带有可用的[install referrer](https://www.appsflyer.com/glossary/install-referrer/)，AppsFlyer会根据概率模型或确定性归因逻辑对这个激活进行归因。
9. AF会生成一条带有`fbclid`参数以及其他事件参数的回传，并通过CAPI将其发送到Meta。Meta通过`fbclid`参数来识别相关点击，并使用其他参数对具体广告系列的投放进行优化。

</Accordion>

<div id="set-up-smart-script-landing-page" />

<Accordion title="设置带有智能脚本的落地页">

如需在您的Meta Ads广告投放中使用智能脚本，请按以下方式操作：

1. 为您要投放的广告系列设置一个OneLink模板，用于生成相关的OneLink归因链接。详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink模板的创建方式</Anchor>说明。
2. 创建一个智能脚本。详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink智能脚本的创建方式</Anchor>说明。

   <div id="note-9" />

   > 📘 **注意**
   >
   > 下文内容主要针对使用智能脚本的Meta Ads广告系列，说明了具体的设置步骤。如需了解更具普适性的智能脚本投放设置方式，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink智能脚本V2设置说明</Anchor>中的<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink智能脚本创建方式</Anchor>部分。

3. 请确保所有相关的URL参数都已添加到传入链接末尾。如需检查附加在传入链接末尾的参数，请打开Meta Ads Manager，查看您在创建目标网址（Destination URL）时设置的URL参数。详情请见 [设置目标网址（Destination URL）](/docs/meta-ads-create-web-based-campaigns#b-set-destination-url)。
4. 将Meta Ads广告中必须配置的传入URL参数映射到由脚本生成的传出URL参数，用户点击CTA按钮时，智能脚本会将这些参数发送到AppsFlyer：
   * **PID**：确保智能脚本从传入链接中提取`pid=metaweb_int`参数，并将其映射到传出链接中对应的参数。
   * **FBCLID**:为确保应用内事件的回传能成功发送到Google Ads，传出链接中必须带有`fbclid`参数。传出链接中的FBCLID参数映射取决于您使用的智能脚本版本。

     * 2.8.1及以上版本：传入链接中带有`fbclid`参数时，其参数值会自动传递到传出链接的对应参数中，无需手动映射。
     * 2.8.0及以下版本：必须在**智能脚本**页面的**URL参数映射**部分手动配置`fbclid`参数的映射。
       1. 在**映射对象**一栏中选择**自定义参数**。
       2. 在**出链参数**和**入链参数**字段中输入**fbclid**。

     <div id="note-7" />

     > 📘 **注意**
     >
     > 如需使相关数据呈现在AppsFlyer的原始数据报告中，必须将传入的`fbclid`参数同时映射到传出的`fbclid`参数和`af_sub[1-5]`参数。详情请见<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">Facebook FBCLID的说明</Anchor>。


</Accordion>

<div id="set-up-smart-script-crossplatform-landing-page" />

<Accordion title="设置带有智能脚本的跨平台落地页">

如需在您的Meta Ads广告投放中使用带有智能脚本的跨平台落地页，请按以下方式操作：

1. 为您要投放的广告系列设置一个OneLink模板，用于生成相关的OneLink归因链接。详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink模板的创建方式</Anchor>说明。
   * 请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-cross-platform-links-for-multi-device-campaigns#创建或编辑onelink模板用于跨平台归因">此文档</Anchor>中的说明，将您的OneLink模板应用于跨平台归因。
2. 请确保所有相关的URL参数都已添加到传入链接末尾。如需查看附加在传入链接末尾的参数，请打开Meta Ads Manager，检查您在创建目标网址（Destination URL）时设置的URL参数。详情请见[目标网址（destination URL）的设置说明](#b-set-destination-url)部分。
3. 请列出各传入参数在传出链接中的对应参数。例如将传入链接中的`af_site_id`参数映射到传出链接中的`af_site_id`参数。
4. 请列出必要传出参数（即不能出现空值的参数）的默认值。
5. 向您的开发人员发送以下信息：
   * 您的传入-传出参数的映射方式。开发人员会创建一个脚本，根据您指定的传入-传出参数的对应关系，生成传出的直接访问链接。
   * 各参数的默认值。脚本若未在传入的链接中发现对应的参数值，就会使用默认值来填充传出链接中的参数。
   * 如果您使用OneLink归因链接，请将相关域名和模板ID发送给您的开发人员，用于创建传出的OneLink链接。域名和模板ID的格式为`yourbrand.onelink.me/A1b2`，若您使用品牌域名，则为`click.yourbrand.com/A1b2`
   * 将以下Dev Hub文档发送给您的开发人员：
     * 创建可直接访问非移动端页面的传出链接时，请参考这些[说明及代码示例](https://dev.appsflyer.com/hc/docs/create-direct-click-url)。
     * 创建跨平台落地页时，请参考这些[演示和说明](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/)。
   * 提醒开发人员务必在传出链接中加入传入参数`fbclid`的映射。

     <div id="note-8" />

     > 📘 **注意**
     >
     > 如需使相关数据呈现在AppsFlyer的原始数据报告中，必须将传入的`fbclid`参数同时映射到传出的`fbclid`参数和`af_sub[1-5]`参数。


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## 创建带有OneLink智能横幅的落地页

**用户链路：** 用户点击Meta广告后跳转到您的移动端网站，并进入一个展示智能横幅的页面，该横幅中带有CTA按钮，引导用户从对应的应用商店下载相关应用。

<div id="end-to-end-data-flow::4f887e1c" />

<Accordion title="整个链路中的数据流">

1. Meta广告的URL中包含`pid=metaweb_int`参数。当用户点击该广告时，`fbclid`参数会被自动添加到该广告URL的末尾。
2. 用户跳转到指定的目标网址——即一个带有智能横幅的落地页。
3. 落地页加载的同时，智能横幅会向AppsFlyer发送一条<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">展示</Anchor>，其中包含传入链接参数（传入链接是指从广告进入落地页的链接）。有了这条展示数据，AppsFlyer就能通过浏览型归因将转化匹配到落地页。如需进一步了解广告展示和浏览型归因，请参阅<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">此文档</Anchor>。
4. 智能横幅针对该横幅中的CTA按钮，生成传出的URL。生成的传出链接以传入链接中的参数（包括`fbclid`）为基础。智能横幅只能生成OneLink链接。
5. 当用户点击智能横幅中的CTA按钮时，AppsFlyer就会接收并记录该次点击。
6. 用户跳转到相应的商店并下载该应用。
7. 用户打开该应用时，AppsFlyer会记录到一个激活。
8. 如果激活数据中带有可用的install referrer，AppsFlyer会根据概率模型或确定性归因逻辑对这个激活进行归因。
9. AF会生成一条带有`fbclid`参数以及其他事件参数的回传，并通过CAPI将其发送到Meta。Meta通过`fbclid`参数来识别相关点击，并使用其他参数对具体广告系列的投放进行优化。

</Accordion>

<div id="set-up-smart-banners-landing-page" />

<Accordion title="设置带有智能横幅的落地页">

如需在您的Meta Ads广告投放中使用智能横幅，请按以下方式操作：

1. 为您要投放的广告系列设置一个OneLink模板，用于生成相关的OneLink归因链接。详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink模板的创建方式</Anchor>说明。
2. 创建一个智能横幅。

   > 📘 **注意**
   >
   > 下文内容主要针对使用智能横幅的Meta Ads广告系列，说明了具体的设置步骤。如需了解更具普适性的智能脚本投放设置方式，请参考<Anchor target="_blank" href="/marketers/zh/docs/smart-banners-mobile-web-to-app-for-marketers">《智能横幅——移动端网页到应用解决方案（市场人员专用）》</Anchor>文档中的<Anchor target="_blank" href="/marketers/zh/docs/smart-banners-mobile-web-to-app-for-marketers#设置">设置</Anchor>部分。

3. 设置智能横幅参数，用于Meta Ads广告：
   * 请确保所有相关的URL参数都已添加到传入链接末尾。其中最重要的两个参数是`pid=metaweb_int`和`fbclid`。请务必确保传入链接中包含这两个参数，这样智能横幅才能收集相关信息。如果缺少这两个参数，就无法对相关流量进行归因，也无法向Meta Ads发送回传。如需查看附加在传入链接末尾的参数，请打开Meta Ads Manager，检查您在创建目标网址（Destination URL）时设置的URL参数。[设置目标网址（Destination URL）](#b-set-destination-url)。

</Accordion>

<div id="view-web-to-app-attribution-data" />

## 查看网页到应用的归因数据

尽管基于网页的转化事件以原始`metaweb_int` PID发送到Meta，但在AppsFlyer仪表板和原始数据报告中以`Facebook Ads` PID报告。这适用于主要转化事件和转化辅助事件。

此统一报告视图使您能够在一个地方分析网页和应用活动的表现，包括完整的网页和移动成本报告。

<div id="view-in-the-dashboard" />

### 在仪表板中查看

所有Meta网页到应用的归因都出现在概述和活动仪表板的`Facebook Ads`下。这提供了跨平台活动结果的单一整合视图。使用标准过滤器和细分来比较您的Meta广告数据中的应用和网页流量。

<div id="view-in-raw-data-and-api-reports" />

### 在原始数据和API报告中查看

* **原始数据导出和API响应**在`media_source`字段中包含`Facebook Ads` PID，用于Google网页活动。要验证网页活动设置的详细信息，请参考`original_url`字段，该字段显示`metaweb_int`作为创建网页活动时使用的PID。
* **回调报告**显示`metaweb_int`作为发送回调的原始媒体来源。

## 常见问题

<div id="why-am-i-seeing" />

<Accordion title="为什么我看到激活和应用内事件归因为Meta Ads（facebook_int），而不是Meta Web（metaweb_int）？">

这是由于您在 Meta Ads 中[设置追踪事件](#c-select-tracked-events)时，将其设置为应用事件而非网页事件。请将设置改为网页事件。

</Accordion>

<div id="traits-and-limitations" />

## 特性与局限性

| 特点 | 说明 |
| --- | --- |
| 成本、点击和展示数据 | Meta Ads Web (`metaweb_int`)的成本、点击和展示数据通过Meta Ads集成（`Facebook Ads`）支持。<ul><li>要获取数据，请确保将广告网络账户连接到主PID（`Facebook Ads`）：<ul><li>ROI360订阅者：在**成本设置**页面中，</li><li>ROI360非订阅者：在**活动集成**页面（**成本**选项卡）中。</li></ul></li><li>要查看Meta Ads Web活动的成本、点击和展示数据，请确保活动ID（<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>）包含在归因链接中。</li><li>归因链接必须包含完整的活动层级，以查看与归因相关的成本、点击和展示数据，达到最细粒度的水平。</li></ul> |

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01HZKNS17JYFQ3F5TKNE5Q5TJ4=%E9%80%9F%E8%A7%88 h_01J8CYG29BETYPZ03A1X54M3ZF=%E6%B3%A8%E6%84%8F prerequisite=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01HZKNS17JTCXE4JMZ64NEVPS6=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 how-to-create-a-meta-ads-campaign=%E5%A6%82%E4%BD%95%E5%88%9B%E5%BB%BAmeta-web%E5%B9%BF%E5%91%8A%E6%B4%BB%E5%8A%A8 h_01HZKNS17JERCAKZHK43ZQWARJ=%E5%A6%82%E4%BD%95%E5%88%9B%E5%BB%BAmeta-web%E5%B9%BF%E5%91%8A%E6%B4%BB%E5%8A%A8 set-up-meta-ads-integration-in-appsflyer=%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEmeta-web%E5%AF%B9%E6%8E%A5 h_01HZKNS17J284R2MAN42WV7F0S=%E5%9C%A8appsflyer%E4%B8%AD%E8%AE%BE%E7%BD%AEmeta-web%E5%AF%B9%E6%8E%A5 h_01HZKNS17JGQBENY2X8S5PHFVH=a-activate-the-meta-ads-integration h_01ZXVWB1ZYKK4DP38QY1RMEY6M=d-enable-view-through-attribution-for-meta-web h_01HZKNS17JH2ZJKATV1AP6JDWP=b-set-inapp-event-postbacks 01JJ4MGS84WXEVG4FWQ0YQ7GN6=%E6%B3%A8%E6%84%8F-1 set-up-appsflyer-integration-in-meta-ads=%E5%9C%A8meta-ads%E4%B8%AD%E9%85%8D%E7%BD%AEappsflyer%E5%AF%B9%E6%8E%A5 h_01HZKNS17JJWX7N9W6BN05B57C=%E5%9C%A8meta-ads%E4%B8%AD%E9%85%8D%E7%BD%AEappsflyer%E5%AF%B9%E6%8E%A5 h_01HZKNS17JTVX8N5CKTKVGH0QB=a-set-the-campaign-type-objective-and-goals h_01HZKNS17JHHS7GYPBT441ND7A=%E6%B3%A8%E6%84%8F-2 h_01HZKNS17KT8TRD2TGDBRGKBZ3=b-set-destination-url h_01HZKNS17KCNKS4YY4JHMQRM1Z=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01J2V9WF300WDY0PWV68TDR9TT=%E6%B3%A8%E6%84%8F-3 h_01K88MSNRX9QFQ49FN2MXPMADX=%E6%8F%90%E7%A4%BA 01J2V903C36X5K6VRPGQQGWFMW=%E6%B3%A8%E6%84%8F-4 h_01HZKNS17K07CENP8GG7MQRKHK=c-select-tracked-events h_01HZKNS17KARAENYPMVJSM1ARQ=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 create-landing-page-with-onelink-smart-script=%E5%88%9B%E5%BB%BA%E5%B8%A6%E6%9C%89onelink%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC%E7%9A%84%E8%90%BD%E5%9C%B0%E9%A1%B5 h_01HZKNS17KPJMP74HQKWY022T2=%E5%88%9B%E5%BB%BA%E5%B8%A6%E6%9C%89onelink%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC%E7%9A%84%E8%90%BD%E5%9C%B0%E9%A1%B5 h_01HZKNS17K5PRRXSD2JMJ54NTN=end-to-end-data-flow h_01HZKNS17KA8VAK5TDFG1NV9YN=set-up-smart-script-landing-page h_01HZKNS17K6DPA6E9CTM5F3X1A=%E6%B3%A8%E6%84%8F-5 h_01HZKNS17K2W4XJB0BH87RZYTJ=%E6%B3%A8%E6%84%8F-7 h_01HZKNS17K5RRAFFTNA6QT7AKJ=set-up-smart-script-crossplatform-landing-page h_01HZKNS17K03S4B3ZRQ62TRFRE=%E6%B3%A8%E6%84%8F-7 create-landing-page-with-onelink-smart-banners=%E5%88%9B%E5%BB%BA%E5%B8%A6%E6%9C%89onelink%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85%E7%9A%84%E8%90%BD%E5%9C%B0%E9%A1%B5 h_01HZKNS17KH8NQ68RPZGMEAQTV=%E5%88%9B%E5%BB%BA%E5%B8%A6%E6%9C%89onelink%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85%E7%9A%84%E8%90%BD%E5%9C%B0%E9%A1%B5 h_01HZKNS17K4Y7WSM14EEJ2G5NC=end-to-end-data-flow::4f887e1c h_01HZKNS17KZ3YKS5R52SRKR9P2=set-up-smart-banners-landing-page h_01HZKNS17K3W3GPV6TM5RQS1WP=%E6%B3%A8%E6%84%8F-8 meta%20view=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E5%88%B0%E5%BA%94%E7%94%A8%E7%9A%84%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE view-webtoapp-attribution-data-from-november-2-2025=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E5%88%B0%E5%BA%94%E7%94%A8%E7%9A%84%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE h_01K88J8JFNEYBZNR18133NMRP9=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E5%88%B0%E5%BA%94%E7%94%A8%E7%9A%84%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE view-in-the-dashboard=%E5%9C%A8%E4%BB%AA%E8%A1%A8%E6%9D%BF%E4%B8%AD%E6%9F%A5%E7%9C%8B h_01K88J8JFNMHCVZ0C34E3D7AST=%E5%9C%A8%E4%BB%AA%E8%A1%A8%E6%9D%BF%E4%B8%AD%E6%9F%A5%E7%9C%8B view-in-raw-data-and-api-reports=%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%92%8Capi%E6%8A%A5%E5%91%8A%E4%B8%AD%E6%9F%A5%E7%9C%8B h_01K88J8JFN8W2572N92466YFZQ=%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%92%8Capi%E6%8A%A5%E5%91%8A%E4%B8%AD%E6%9F%A5%E7%9C%8B frequently-asked-questions-faq=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98 01JCJ9GGDT8GGPRF2YBNSJZ579=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98 01JCJ9GGDVNFW6YBJTC0CKVKGM=why-am-i-seeing traits-and-limitations=%E7%89%B9%E6%80%A7%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 01JEZXJNF1C932KGAEFS4P5D51=%E7%89%B9%E6%80%A7%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />

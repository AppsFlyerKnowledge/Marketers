---
title: PC与主机端的Google Ads Web对接
metadata:
  keywords:
    - google ads configuration
    - google ads
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2024-01-18T11:04:33Z'
  edited_at: '2026-10-14T09:59:59Z'
  id: 21768823915665
  locale: zh-cn
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/zh-cn/articles/21768823915665
---
> **概要：** 通过Google Ads网页广告活动推广您的PC及主机端应用，实现归因分析。AppsFlyer支持使用跨平台落地页或直接归因链接的Google网页广告。

<div id="note" />

> 📘 **注意**
>
> 本文重点关注用于推广PC或主机端应用的网页广告活动。如需创建推广移动应用的网页广告活动，请参阅<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-create-web-based-campaigns">Google Ads（AdWords）- 网页端广告活动</Anchor>。

<div id="overview" />

## 速览

本文详细说明了PC和主机端应用在AppsFlyer中与Google Ads Web对接的流程及其使用方式。其中包含以下信息；

* [在AppsFlyer中启用合作渠道对接](/docs/google-ads-web-integration-for-pc-and-console-apps#在appsflyer中激活合作渠道)。
* [在AppsFlyer中配置Google Ads Web对接](/docs/google-ads-web-integration-for-pc-and-console-apps#setting-up-Googleadsweb-in-appsflyer)。
* [在Google Ads中设置PC和主机端应用广告](/docs/google-ads-web-integration-for-pc-and-console-apps#在google-ads-web中设置pc和主机端应用的广告)。

<div id="prerequisites" />

### 前期准备

在启用Google Ads Web对接之前，请确保您已具备以下条件：

* 一个PC或主机端应用
* 具备一个AppsFlyer账户
* 具备必要<Anchor target="_blank" href="https://developers.google.com/identity/protocols/oauth2/scopes">OAuth权限</Anchor>的Google访问令牌。您可在Google Developer Console中验证访问令牌的权限范围。
* 设置该对接的AppsFlyer<Anchor target="_blank" href="/marketers/zh/docs/user-management">用户具有必要的角色/权限</Anchor>，并有权访问相关应用

<div id="activate-partner-in-appsflyer" />

## 在AppsFlyer中激活合作渠道

**请按以下步骤启用该渠道：**

1. 在AppsFlyer面板的左侧菜单栏中点击**协作** > **Partner Marketplace**。
2. 搜索并选择**Google Ads Web**。
3. 点击**设置对接**，然后界面会跳转到**活跃对接**设置页面。
4. 在**渠道对接**选项卡中，打开**启用该渠道**开关。  
   **请注意：** 在您与该渠道合作期间，请确保该开关总是处于打开（即<Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">启用</Anchor>）状态。
5. 参考下文说明，根据您的具体需求在相关选项卡中完成各项配置。

<div id="set-up-google-ads-web-in-appsflyer" />

## 在AppsFlyer中配置Google Ads Web对接

这部分还包括Google Ads的回传配置。Google Ads Web（googleads\_int）对接通过Google Ads为广告主提供的API工具，将相关的**PC和主机端应用数据**直接发送到Google的服务器。这类数据包括用户在非移动端（包括网页和应用）完成的购买、注册等等各种转化行为。然后Google Ads会使用这些回传数据对广告投放进行优化和定向、衡量广告效果，并创建用于再营销的自定义人群包。

Google Ads Web对接仅支持激活和应用内事件的回传。

<div id="integration-tab" />

<Accordion title="渠道对接选项卡">

**渠道对接**选项卡中包括以下几个部分。

<div id="activate-partner" />

#### 启用渠道

在配置对接之前，必须先打开**启用该渠道**开关。

<div id="general-settings" />

#### 通用设置

<div id="note-1" />

> 📘 **注意**
>
> 将在您使用Google登录并允许AppsFlyer获取 token（见下方步骤），“令牌缺失”的错误提示将不再显示。如果在登录后错误仍然存在，<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-create-web-based-campaigns#access-token-permissions">请验证您的令牌是否具有所需的权限</Anchor>。

1. **首次打开转换ID**：输入您在Google广告中设置的`First open`转化操作ID。如需查看该ID，
   1. 请进入Google Ads后台并打开**First open**转化操作页面中的**Details**选项卡。
   2. 在该页面URL中复制`ctid=*`查询参数的值。举例来说，假设`ctid=123456789`，您需要将`123456789`添加到**First open conversion action ID**字段中。
2. 输入您的**Customer ID**。您可以从Google Ads Manager中获取该ID：
   1. 登入您的Google Ads账户。
   2. 点击界面右上角的Google账户图标，然后向下滚动到Customer ID部分。
   3. 如果您有多个Google Ads账户同时为相关应用投放广告，必须使用经理账号（MCC）的Customer ID才能进行跨账户的转化监测。将 **MCC ID**（而不是特定账户的客户 ID）粘贴到 **客户 ID** 文本框中，并在 **MCC 客户 ID** 文本框中也粘贴相同的 ID（两个框中相同的 ID）。   
      如果您只使用一个 Google Ads 账户来投放广告，只需将账户 ID 粘贴到 **客户 ID** 文本框中，并将 **MCC 客户 ID** 文本框留空。详情请见<Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">Google提供的MCC账号配置说明</Anchor>。
3. 如需允许AppsFlyer将转化数据上传到Google Ads，请点击**使用Google登录**。
4. 在Google中，选择MCC账号（即您在以上步骤中获取到Customer ID的MCC账号）中的管理员。
5. 点击**Allow**。

<div id="enable-view-through-attribution" />

#### 启用浏览型归因

AppsFlyer支持通过启用<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-create-web-based-campaigns#create-a-landing-page-with-onelink-smart-script">智能脚本</Anchor>或<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-create-web-based-campaigns#create-a-landing-page-with-onelink-smart-banners">智能横幅</Anchor>的落地页，对Google Web广告系列进行浏览型归因。这项功能可以基于概率模型(PMOD)，将因广告曝光而触发的App激活进行归因，即使用户并未直接点击广告。

当用户看到Google广告并访问启用了智能脚本或智能横幅的落地页时，AppsFlyer可以将后续发生的App激活归因至最初的网页曝光事件，包括跨平台场景。

在可用的情况下，AppsFlyer会在给Google的回传中包含gclid参数。

**启用浏览型归因**

1. 在AppsFlyer中，从侧边栏打开**活动对接**> **Google Ads Web**。
2. 在**对接**选项卡中，下滑到**激活归因**部分。
3. 打开**浏览型激活归因**开关。
4. **[可选]** 开启**跨平台归因具有同等优先级**并设置回溯窗口。有关更多信息，请参见<Anchor target="_blank" href="/marketers/zh/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">为跨平台展示启用同等优先级</Anchor>。
5. 打开**归因**选项卡。
6. 下滑到**浏览型归因**部分并设置所需的**浏览归因回溯窗口**（最长24小时）。
7. 点击**保存对接**以应用更改。

<div id="default-postbacks" />

#### 默认回传

激活回传自动发送到Google Ads Web，不会发送到其他渠道。

<div id="in-app-event-postbacks" />

#### 应用内事件回传

针对发送到Google Ads Web的应用内事件配置回传映射。您可以在Google Ads Manager中查看这些事件。

1. 打开**应用内事件回传**开关。
2. 点击**添加事件**，将SDK事件或S2S事件添加到列表中。下表列出了必须配置的字段：

| 参数名称 | 说明 |
| --- | --- |
| **AppsFlyer事件** | 事件的名称，即AppsFlyer从SDK侧接收到的事件名称或来自S2S事件的名称。<ul><li>点击**添加项目**，输入事件名称，然后点击![check.png](https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png)。</li></ul> |
| **渠道映射事件** | 事件的转化操作ID需与合作渠道端保持一致。<ol><li>在Google Ads**转化目标**页面，单击您创建的转化操作。</li><li>在转化操作**详情**页面，从URL参数`ctId=`中复制**转化操作ID**。</li><li>返回AppsFlyer并粘贴到对应位置。举例来说，假设`ctid=123456789`，则将`123456789`粘贴到渠道映射事件字段中。</li></ol> |
| **事件来源** | **仅该合作渠道：** 仅回传归因到Meta Web的事件，也就是说完成该事件的用户来自Meta Web。 |
| **回传内容** | **发送值与收入：** 在回传中发送所有事件参数，包括收入（若有）。 |

3. 【可选】点击**添加条件**<Image alt="onditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />图标，<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">设置事件的回传条件</Anchor>。
4. 设置**应用内事件回传窗口**（如有需要）。详情请见<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">应用内事件回传窗口配置</Anchor>。
5. 点击**保存对接**。
6. 【可选】您可以在保存对接后留在配置页面，将其他应用也对接到该渠道：
   1. 点击页面左上角渠道名称下方的应用名称，打开应用列表。
   2. 在下拉菜单中选择一个其他应用。
   3. 为选定应用完成对接设置。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="归因链接选项卡">

目前尚不支持从AppsFlyer后台生成归因链接。但您可以使用带有智能脚本的跨平台落地页，或为相关应用创建一条直接归因链接（见下表）。

| 可选方案 | 可用操作 | 人员 |
| --- | --- | --- |
| 跨平台落地页 | **推荐**：如果您要推广的应用在Epic和Steam等多个平台中上架，建议使用这种方式。<br /><br /><Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">进一步了解跨平台落地页</Anchor><br /><br /><Anchor target="_blank" href="/marketers/zh/docs/cross-platform-landing-pages-with-smart-script">了解跨平台落地页的设置方式</Anchor><ul><li>请确保所有相关URL参数（即智能脚本要抓取的参数）都已添加到广告链接中。</li><li>请确保智能脚本能从入链中抓取GCLID，并将其添加到生成的链接中。也就是说，传出链接GCLID（即智能脚本生成的链接）中的参数`gclid`必须映射到传入链接中`gclid`参数。**请注意**：如需让AppsFlyer的原始数据报告呈现该数据，还必须将传入的`gclid`参数与`af_sub[1-5]`参数之一进行映射。</li></ul> | 营销人员（可能需要开发人员协助） |
| 直接归因链接 | 如果您要推广的应用仅在1个平台中上架，因而决定不使用跨平台落地页，可以创建直接归因链接，将其附在广告背后。<br /><br /><Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links">了解直接归因链接的创建方式</Anchor><ul><li>请务必在您的链接中添加下列参数：<ul><li>af\_media\_source</li><li>af\_campaign\_id</li><li>af\_r<br />**请注意**：如果您使用Google Ads的<Anchor target="_blank" href="https://support.google.com/google-ads/answer/3095550?hl=en">自动标记（auto-tagging）</Anchor>功能，Google会自动将这个<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">Google点击标识符</Anchor>参数添加到生成的链接中。如果您的Google Ads中禁用了自动标记功能，请在Google广告跟踪模板URL中添加`gclid={gclid}`。</li></ul></li><li>配置af\_camapign\_id、af\_adset\_id和af\_ad\_id参数时，可以使用Google的[ValueTrack参数](https://support.google.com/google-ads/answer/6305348)(即动态URL参数）宏。所有其他参数都需要手动设置。</li><li>切勿添加af\_dp参数。</li></ul>**适用于大多数平台（Epic、Steam、Xbox、PlayStation 等）的模板**如下：<br /><br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}? af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**用于Steam的链接示例**：`https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**仅适用于Google PC和Mac应用的模板**如下：<br /><br />`https://app.appsflyer.com/{app_id}?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**用于Google PC的链接示例**：`https://app.appsflyer.com/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}` | 营销人员 |

<div id="tip" />

> 👍 **提示**
>
> 为了简化广告系列分析，请在广告系列名称中包含广告系列类型、网页或移动，作为前缀或后缀（例如，广告系列名称\_web）

</Accordion>

<div id="set-up-campaigns-in-google-ads-web-for-pc-and-console-apps" />

## 在Google Ads Web中设置PC和主机端应用的广告

设置全新的广告系列时，您可以选择将用户引导到：

* 跨平台落地页如果您要推广的应用在Epic和Steam等多个平台中上架，建议使用这种方式。
* 单一应用商店：使用直接归因链接，适用于仅在一个平台中上架的应用。

下文分别针对这两种方式，说明了相应的广告系列设置方法。

**请注意**：在设置广告系列的过程中，您可能需要根据自己的实际需求自行配置转化行为和目标。下文单开一节对这部分配置进行了说明，供您参考。

<div id="campaigns-that-redirect-to-a-crossplatform-landing-page" />

<Accordion title="跳转到跨平台落地页的广告">

**如需让用户跳转到跨平台落地页，请按以下方式设置您的广告系列**：

1. 按[归因链接部分](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab)的说明，创建一个跨平台落地页。
2. 登入Google Ads并创建一个新的广告系列。
3. 选择投放目标（campaign objective）。  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * 除“App promotion”之外，所有目标均适用（“App promotion”仅适用于移动端应用的广告）。
   * 建议您将投放目标设置为“Sales”，以便根据具体的应用内事件进行优化。
4. 选择转化目标（conversion goals）。  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * 默认情况下，您会看到账户层级的预定义投放目标（campaign goals）。您可以根据实际的投放需求保留或移除相关目标。
   * 如果您没有在预定义列表中看到所需目标，请手动[添加相应的转化行为和转化目标](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals)。
   * 您还可以在Conversion页面中修改您的预定义目标。
5. 选择所需的campaign type（广告系列类型）  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * 除“Shopping”之外的所有广告系列类型均适用（“Shopping”类广告系列要求广告主配置商品目录，且仅限已验证的域名）。
6. 输入跨平台落地页的网址，作为Google广告的跳转终点（Final URL）。

</Accordion>

<div id="campaigns-that-redirect-to-a-single-app-store" />

<Accordion title="跳转到单一应用商店的广告">

**如需让用户跳转到某一个特定的应用商店，请按以下方式设置您的广告系列**：

1. 按[归因链接部分](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab)的说明，创建一条直接归因链接。
2. 登入Google Ads并创建一个新的广告系列。
3. 选择投放目标（campaign objective）。  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * 除“App promotion”之外，所有目标均适用（“App promotion”仅适用于移动端应用的广告）。
   * 建议您将投放目标设置为“Sales”，以便根据具体的应用内事件进行优化。
4. 选择转化目标（conversion goals）。  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * 默认情况下，您会看到账户层级的预定义投放目标（campaign goals）。您可以根据实际的投放需求保留或移除相关目标。
   * 如果您没有在预定义列表中看到所需目标，请手动[添加相应的转化行为和转化目标](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals)。
   * 您还可以在Conversion页面中修改您的预定义目标。
5. 选择所需的campaign type（广告系列类型）  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * 除“Shopping”之外的所有广告系列类型均适用（“Shopping”类广告系列要求广告主配置商品目录，且仅限已验证的域名）。
6. 输入链接，作为Google广告的跳转终点（Final URL）。
   * 请确保该网址是您需要引导用户进入的页面。您可以使用网站落地页或商店页面等的任何网址，例如：`https://store.steampowered.com/app/{appid}/{myapp}/`。
   * 切勿使用AppsFlyer URL作为Final URL，否则可能会导致您的广告系列被拒审。请仅使用不带跳转的直接访问网址。
7. 输入您的AppsFlyer直接归因链接，作为Google的跟踪模板（Tracking Template URL）。
   * 为了保证并行追踪（Parallel tracking）能正常生效，请务必将跳转终点（Final URL）配置在Google的`{lpurl}` ValueTrack参数中（具体可参考Google的相关说明）。
   * 切勿添加af\_dp参数。

</Accordion>

<div id="creating-conversion-actions-and-goals" />

<Accordion title="创建转化操作和目标">

您可以从Google Ads预定义的转化行为（Conversion Actions）和目标（Goals）中选择，也可以创建自定义的行为和目标。

<strong>重要提示！</strong>如果需要AppsFlyer发送“First Open”（首次打开）事件回传，情在Google Ads中创建一个转化操作，并将其命名为“First Open”。

**请按以下方式创建您自定义的Google Ads转化行为和目标**：

1. 进入您的Google Ads账户总览页面（Overview），从侧边栏中选择**Goals** > **Conversions** > **Summary**。
2. 点击 **+ New conversion action**。
3. 选择 **离线转化** 作为您的转化操作数据源。
4. 从转化类型（Conversion Types）列表中选择**Import**，然后选择**Manual import using API or uploads** > **Track conversions from clicks**。

   <div id="note-2" />

   > 📘 **注意**
   >
   > 如果无法**使用API或手动**上传：
   >
   > 1. 选择**CRM、文件或其他数据源** > **基于点击追踪转化。**
   > 2. 在**数据源**中选择**跳过此步骤，稍后设置数据源。**

5. 点击**继续**，进入下一步。  
   界面会显示一张表格。
6. 填写表格并点击**Create and continue**，完成转化追踪（Conversion Tracker）的设置。
7. 在**Goal and action optimization**部分，选择一个类别（category），用于映射您设置的转化行为。  
   **请注意**：请注意：Google会按类别而非转化行为来优化投放。如果您只需针对某一个具体转化行为来优化投放，请仅将此转化行为映射到选定类别中。举例来说，假设您需要针对“install”（激活）行为来优化投放，请将“install”行为单独映射到其专用的类别中（如“Other”）。 然后您就可以在创建广告系列时选择这个类别作为投放目标。
8. 从Google Ads复制转化操作ID，并将其输入到**映射到合作渠道事件**字段中。 **转化操作ID**将作为合作渠道事件ID，用于在应用内事件回传设置中，将AppsFlyer事件名称映射到合作渠道事件ID。如需从Google Ads中复制转化操作ID，请执行以下操作：
   1. <span class="af-ol-a"></span>在Google Ads**转化目标**页面，点击您创建的转化操作。
   2. 在转化操作**详细信息**页面，从URL参数`ctId=`中复制**转化操作ID**并粘贴。
9. 点击**Create and continue（创建并继续）**，进入下一步。
10. 点击**Finish**，完成设置。

</Accordion>

<div id="view-web-to-app-attribution-data-from-november-2-2025" />

## 查看网页到应用的归因数据（自 2025 年 11 月 2 日起）

尽管基于网页的转化事件以原始 `googleads_int` PID 发送到 Google，但在 AppsFlyer 仪表板和原始数据报告中以 `googleadwords_int` PID 报告。这适用于主要转化事件和转化辅助事件。

此统一报告视图使您能够在一个地方分析网页和应用广告系列的表现，包括完整的移动和网页成本报告。

<div id="view-in-the-dashboard" />

### 在仪表板中查看

所有 Google 网页到应用的归因都出现在概览和活动仪表板的 `googleadwords_int` 下。这提供了跨平台广告系列结果的单一、综合视图。使用标准过滤器和细分来比较您的 Google Ads 数据中的应用和网页流量。

<div id="view-in-raw-data-and-api-reports" />

### 在原始数据和 API 报告中查看

* **原始数据导出和 API 响应** 在 `media_source` 字段中包含 `googleadwords_int` PID，用于 Google 网页活动。要验证网页广告系列设置的详细信息，请参考显示 `googleads_int` 作为创建网页广告系列时使用的 PID 的 `original_url` 字段。
* **回传报告** 显示 `googleads_int` 作为发送回传的原始媒体来源。

<div id="traits-and-limitations" />

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 点击和展示（临时限制） | 针对 PC 和控制台应用的广告系列的点击和展示暂时无法从 Google SRN 获取（`googleadwords_int`）。 |

<div data-zendesk-anchors="h_01JP7SMGEPTQGHRYYCBWECH46X=%E6%B3%A8%E6%84%8F overview=%E9%80%9F%E8%A7%88 h_01HK4QHRJG6WTN9P6ZG83XQ6AY=%E9%80%9F%E8%A7%88 prerequisites=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01HFXV8HPGCRGYPEW0NPJ0NR0S=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 activate-partner=%E5%9C%A8appsflyer%E4%B8%AD%E6%BF%80%E6%B4%BB%E5%90%88%E4%BD%9C%E6%B8%A0%E9%81%93 h_01HFXV8HPH3N4DBKKTQE6DK7FK=%E5%9C%A8appsflyer%E4%B8%AD%E6%BF%80%E6%B4%BB%E5%90%88%E4%BD%9C%E6%B8%A0%E9%81%93 setting-up-metaweb-in-appsflyer=%E5%9C%A8appsflyer%E4%B8%AD%E9%85%8D%E7%BD%AEgoogle-ads-web%E5%AF%B9%E6%8E%A5 01H88VAJH3VENKYVRQY5RXN63P=%E5%9C%A8appsflyer%E4%B8%AD%E9%85%8D%E7%BD%AEgoogle-ads-web%E5%AF%B9%E6%8E%A5 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 h_01HFXV8HPH6X92YETNAGZ910AV=%E5%90%AF%E7%94%A8%E6%B8%A0%E9%81%93 transaction-id=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01HARQDVEDA206D0BBXBC6WEHH=%E9%80%9A%E7%94%A8%E8%AE%BE%E7%BD%AE h_01JK8XJJWQK5MEJF7GTC5C1707=%E6%B3%A8%E6%84%8F-1 enable-viewthrough-attribution=%E5%90%AF%E7%94%A8%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0 h_01ZXVWB0GZKWB53KTBWJ51RMBM=%E5%90%AF%E7%94%A8%E6%B5%8F%E8%A7%88%E5%9E%8B%E5%BD%92%E5%9B%A0 default-postbacks=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 01H88VAJH3WE9Z0971WMBRBJRS=%E9%BB%98%E8%AE%A4%E5%9B%9E%E4%BC%A0 inapp-event-postbacks=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H88VAJH3AS37MVF75GANWX4B=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%9B%9E%E4%BC%A0 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab h_01K88M617Q7SVMDEKP5HTKANJM=%E6%8F%90%E7%A4%BA setting-up-campaigns-in-meta-web-for-pc-and-console-apps=%E5%9C%A8google-ads-web%E4%B8%AD%E8%AE%BE%E7%BD%AEpc%E5%92%8C%E4%B8%BB%E6%9C%BA%E7%AB%AF%E5%BA%94%E7%94%A8%E7%9A%84%E5%B9%BF%E5%91%8A h_01HK4S03KVAN99YKXTHAKCT420=%E5%9C%A8google-ads-web%E4%B8%AD%E8%AE%BE%E7%BD%AEpc%E5%92%8C%E4%B8%BB%E6%9C%BA%E7%AB%AF%E5%BA%94%E7%94%A8%E7%9A%84%E5%B9%BF%E5%91%8A h_01HMR6HVJF4QT1EZKYZKRVTWEE=campaigns-that-redirect-to-a-crossplatform-landing-page h_01HMR6HVJFMN1V7VM58ZMQFEXF=campaigns-that-redirect-to-a-single-app-store h_01HMTXEZB3W19TKK8ZR6JK2TPG=creating-conversion-actions-and-goals h_01HV6FR2TFYT11H9EVT9Y9TZ3S=%E6%B3%A8%E6%84%8F-2 google%20view-web-to-app=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E5%88%B0%E5%BA%94%E7%94%A8%E7%9A%84%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE%E8%87%AA-2025-%E5%B9%B4-11-%E6%9C%88-2-%E6%97%A5%E8%B5%B7 view-webtoapp-attribution-data-from-november-2-2025=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E5%88%B0%E5%BA%94%E7%94%A8%E7%9A%84%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE%E8%87%AA-2025-%E5%B9%B4-11-%E6%9C%88-2-%E6%97%A5%E8%B5%B7 h_01K88H6ETM23EV0PTR8GS13KRN=%E6%9F%A5%E7%9C%8B%E7%BD%91%E9%A1%B5%E5%88%B0%E5%BA%94%E7%94%A8%E7%9A%84%E5%BD%92%E5%9B%A0%E6%95%B0%E6%8D%AE%E8%87%AA-2025-%E5%B9%B4-11-%E6%9C%88-2-%E6%97%A5%E8%B5%B7 view-in-the-dashboard=%E5%9C%A8%E4%BB%AA%E8%A1%A8%E6%9D%BF%E4%B8%AD%E6%9F%A5%E7%9C%8B h_01K88H6ETMG7007CJ0ADD8VQH4=%E5%9C%A8%E4%BB%AA%E8%A1%A8%E6%9D%BF%E4%B8%AD%E6%9F%A5%E7%9C%8B view-in-raw-data-and-api-reports=%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%92%8C-api-%E6%8A%A5%E5%91%8A%E4%B8%AD%E6%9F%A5%E7%9C%8B h_01K88H6ETM502Z2XDC63602FGD=%E5%9C%A8%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E5%92%8C-api-%E6%8A%A5%E5%91%8A%E4%B8%AD%E6%9F%A5%E7%9C%8B traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01KB5085FX7G6Y5E200KVH0ABJ=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />

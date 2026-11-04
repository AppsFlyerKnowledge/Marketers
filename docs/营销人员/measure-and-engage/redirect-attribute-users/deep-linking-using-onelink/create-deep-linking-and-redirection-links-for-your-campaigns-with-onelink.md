---
title: 为您的广告系列创建 OneLink 链接
metadata:
  keywords:
    - Marketers
    - onelink
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2016-05-22T10:03:37Z'
  edited_at: '2026-10-14T10:04:17Z'
  id: 208874366
  locale: zh-cn
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/zh-cn/articles/208874366
---
> **概要：** 本文介绍了如何根据您的实际需求创建OneLink链接，打造理想的用户体验。用户点击链接后会跳转到与其设备适配的应用商店、网址或进入应用，并被归因到相应的带量渠道。

<div id="onelink-links-and-experiences" />

## OneLink链接与用户体验

<Embed title="为您的广告系列创建 OneLink 链接" typeOfEmbed="youtube" url="https://www.youtube.com/embed/KZBrxGEjVUE" providerUrl="https://www.youtube.com" />

您的用户会通过各种线上和线下触点与您的品牌进行互动。但不论您的用户来自何方，您都可以为他们打造专属的理想体验，不管是从点击到应用激活，还是到深度链接或延迟深度链接。

本文的流程详解部分详细介绍了链接设置中所涉及的具体步骤，总体可概括为以下几点：

* 选择一种用户体验
* 通用设置
* 分用户体验的专用设置
* 深度链接及跳转设置
* 其他参数设置

<div id="create-a-onelink-link" />

## 创建OneLink链接

| **负责人员**<ul><li>如需让用户跳转到应用商店、网页URL，或在模板设置完毕后通过安卓App Link或iOS Universal Link打开应用并进入应用主页，创建带有这类跳转体验的OneLink链接仅涉及营销人员。</li><li>如需在链接中添加深度链接或延迟深度链接功能，市场人员和安卓/iOS开发人员都需要参与到设置流程中来。</li></ul> |
| --- |
| **前期准备**<ul><li>确保您有一个AppsFlyer帐户，且账户中至少有一个应用。</li><li>准备一个<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">OneLink模板</Anchor>，这是之后创建链接的基础。</li><li>如需归因： 确保您的所有应用中都<Anchor target="_blank" href="/marketers/zh/docs/integrate-the-appsflyer-sdk">已安装AppsFlyer SDK</Anchor>。<ul><li>如果 您的应用尚未安装SDK，仍然可以创建有效的重定向链接，但无法评估控制面板、深度链接或延迟深度链接中的安装。</li></ul></li></ul> |
| **所需时间**<br /><br />大部分链接的设置仅需30分钟，但带有深度链接或延迟深度链接功能的链接需要3小时左右。 |
| **结果**<ul><li>您创建的链接能让用户跳转到与其设备适配的应用商店、网页或进入应用，按照您设计的链路打造理想的用户体验。</li></ul> |

**如需创建一条带有指定用户体验的OneLink链接，请按以下方式操作：**

1. 从AppsFlyer后台的侧边栏中选择**互动** > **OneLink管理**。
2. 选择要为其添加自定义链接的**OneLink模板**。
3. 点击**添加链接**。
4. 选择您想要打造的[用户体验](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#experiences)。
5. 选择一个媒体渠道或输入自定义媒体渠道名称。AppsFlyer后台会将该链接产生的数据展示在这个渠道名称下。媒体渠道在您的链接中表达为`pid`参数值。

   <div id="note" />

   > 📘 **注意**
   >
   > AppsFlyer将拦截在自有媒体来源（如电子邮件或短信）中将<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#与appsflyer对接的srn">SRN</Anchor>名称用作PID值的归因链接。此限制不适用于ASRN。

6. 点击**下一步**。
7. 完成[常规设置](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings)。
8. 点击**下一步**。
9. 【可选】完成指定用户体验的专属设置流程：

| 体验 | 流程选项 |
| --- | --- |
| <ul><li>社媒到应用</li><li>短信到应用</li><li>推荐到应用</li><li>自定义链接</li></ul> | <ul><li>[社交媒体预览](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[社交应用落地页](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li></ul> |
| 邮件到应用 | 如果您使用了ESP（邮件营销服务商），请按<Anchor target="_blank" href="/marketers/zh/docs/email-service-provider-esp-integration-guide">ESP对接指南</Anchor>操作。 |
| 应用到应用 | 您可以创建动态链接，通过<Anchor target="_blank" href="/marketers/zh/docs/cross-promotion-attribution-for-marketers">交叉推广</Anchor>功能实现多应用联动营销。 |
| 推荐到应用 | <ul><li>[社交媒体预览](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[社交应用落地页](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li><li>您可以为相关应用中的SDK配置<Anchor target="_blank" href="/marketers/zh/docs/user-invite-attribution">用户邀请对接</Anchor>，从而动态创建“推荐到应用”链接。</li></ul> |

10. 点击**下一步**。
11. 【可选】完成**深度链接与跳转**部分的[深度链接/延迟深度链接设置](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)。如果您不需要该链接带有深度链接行为，请跳过这一步。
12. 【可选】在**深度链接与跳转**部分更改[跳转设置](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection)。如果OneLink模板中的跳转设置符合您的需求，请跳过这一步。
13. 点击**下一步**。
14. 您可以在**其它参数**部分[添加预定义或自定义参数](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#additional-parameters)，用于更细致深入的数据分析。<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">详情请见归因参数详解。</Anchor>
15. 点击**生成链接**。
16. 确保您的<Anchor target="_blank" href="/marketers/zh/docs/set-up-your-domain-redirect-allowlist">跳转白名单</Anchor>已更新，其中包含您想让用户跳转的所有域名。

<div id="experiences" />

<Accordion title="用户体验">

您可以针对下列用户体验创建链接：

* **社媒到应用**： 在社交媒体上吸引用户互动，将流量从社交媒体帖子引导到您的应用。
* **应用到应用**：在其他应用上投放广告，将看到广告的用户引入您的应用。
* **二维码到应用**： 通过二维码推动拉新，让用户在线下体验过程的关键环节中扫描二维码。您也可以在PC端、电视或CTV广告中添加二维码，将用户引导到应用。
* **邮件到应用**：通过邮件服务商（ESP）向用户发送邮件，并将他们引导到应用。
* **短信到应用**： 创建专用于短信和短消息营销的链接，通过文字消息与用户互动。
* **推荐到应用**： 创建用户邀请链接，让用户以及博主邀请其他人使用您的应用或分享应用中的指定内容（如文章）。
* **自定义链接**： 除了上述用户体验之外，您还可以创建OneLink自定义链接，打造更为定制化的用户链路。不论您的用户来自PC端还是移动端，线上还是线下，自有媒体还是付费媒体，OneLink都能按您的要求来引导流量。

</Accordion>

<div id="general-settings" />

<Accordion title="通用设置">

通用设置是OneLink链接创建流程中的一个环节，适用于各类用于体验。

**请按以下步骤完成通用设置**：

1. 【可选】更改媒体渠道名称。
2. 【可选】更改广告系列名称。
3. 【可选】如果您计划将该链接投放给现有用户，请打开**再营销**开关。

   打开该开关后，您就可以看到点击自定义链接的用户所完成的再互动。

   现有用户点击非再营销（UA）链接后也会打开应用，并获得相同的用户体验，但这些用户的再互动会被记录为常规的应用打开（session）。也就是说这种情况下，您无法衡量自有媒体上的广告投放是否有效。

   **重要提示**！您必须同时打开应用配置中的再营销归因开关，才能使再营销功能正常生效。
4. 【可选】打开**再营销广告中忽略活跃用户**的开关，并设置不活跃窗口。  
   该操作会在您的链接中添加参数af\_inactivity\_window=[天数]，营销归因会忽略在此期间的所有活跃用户。
5. 设置再互动窗口期。用户再次打开应用后，在该窗口期以内的应用内事件会归因到再营销渠道。
   * 这个值可以设置为数天（1-90天）、数小时（至多23小时）或用户的整个生命周期。
   * 再互动窗口期会以af\_reengagement\_window参数的形式体现在归因链接中。
6. 【可选】在**品牌链接**部分：
   * 另选一个域名来代表您的品牌。<Anchor target="_blank" href="/marketers/zh/docs/brand-onelink-with-your-domain">了解详情</Anchor>
   * <span id="url-id"></span>修改URL ID来凸显该广告系列的内容。URL ID默认为8个字符，最多可包含50个字符，默认长度为8个字符。

<div id="enable-retargeting-for-the-app" />

#### 在应用配置中启用再营销

如果您的应用从未启用过再营销功能，您需要先启用一次。 <Anchor target="_blank" href="/marketers/zh/docs/app-settings#归因设置">了解详情</Anchor>

**如需在应用层级配置再营销功能，请按以下步骤操作：**

1. 从AppsFlyer后台的侧边栏中选择**配置** > **应用配置**。
2. 在**归因**部分中打开**再互动归因**开关。
3. 点击**保存配置**。

</Accordion>

<div id="social-media-preview-og-tags" />

<Accordion title="社交媒体预览——OG标签">

您可以使用Open Graph（开放图谱，简称OG）标签，在分享链接时生成带有标题、描述和图像的预览。

系统可以从网页URL或应用商店页中自动攫取OG标签，但由于这种生成预览的方法不能保证百分百奏效，因此还是建议您在OneLink中设置社交媒体预览。您可以在OneLink界面进行相关操作，也可以直接在链接中添加OG标签参数（适用于不在OneLink后台生成的链接）。

社交媒体预览功能适用于以下平台：

* Facebook：帖子和私信
* X（前身为Twitter）：帖子和私信
* iMessage
* WhatsApp
* LinkedIn：帖子和私信
* Line
* Telegram
* Slack
* Signal
* KakaoTalk
* Discord
* Reddit

**请按以下步骤在OneLink界面中创建社交媒体预览：**

1. **从OneLink自定义链接编辑页面进入社媒分享部分。**
2. 在**社交媒体预览**板块中填写以下字段：
   * 标题
   * 说明
   * 图像URL

**请按以下步骤在链接中添加OG标签参数**（适用于不在OneLink后台生成的链接）：

* 请添加以下几个必须配置的参数：
  * af\_og\_title（最多40个字符）
  * af\_og\_description（最多300个字符）
  * af\_og\_image

**请注意：**

* 如果您的链接不是在AppsFlyer后台生成的，也可以在其中添加上述OG标签参数。
* 如果您专为X（前身为Twitter）添加了单独的OG标签，这些标签会覆盖常规的AppsFlyer预览。

</Accordion>

<div id="social-app-landing-page" />

<Accordion title="社交应用落地页">

<div id="important-1" />

> 🚧 **重要提示！**
>
> Meta ads现可支持iOS Universal Link。
>
> * 由于现在Meta<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-faq#are-ios-universal-links-and-android-app-links-supported-in-meta-ads">支持Universal Link</Anchor>，因此在提供此类支持的Meta付费广告中无需再使用社交应用落地页。
> * 自有帖子（即非付费广告）中仍需要设置社交应用落地页。

部分社交媒体应用会干扰Universal Link的跳转，影响现有用户的体验。您可以通过以下方法来解决这个问题：

* 【**推荐**】创建社交应用落地页。  
  创建社交应用落地页时，请务必设置一个URI scheme。
* 【备选方案】使用`af_force_deeplink=true`参数<Anchor target="_blank" href="/marketers/zh/docs/onelink-troubleshooting-and-faq#强制深度链接">强制打开应用</Anchor>。   
  **请注意**：该参数在Kakaotalk、Naver、Naver-Blog、Chrome、微博和X（前身为Twitter）中默认启用。

启用社交应用落地页后，在社交应用中点击广告的用户会跳转到AppsFlyer生成的落地页，然后再从落地页通过深度链接打开或下载应用。

AppsFlyer提供了一系列社交应用落地页的模板。模板中元素的位置是固定的，但是元素本身可以自行调整，包括背景图像或颜色、标题、文本、图像、按钮、标签等。

社交应用落地页可用于以下平台：

* Instagram
* Facebook/Facebook Messenger（**请注意**：在Facebook和Facebook Messenger中，如果您同时设置了URI scheme和社交应用落地页，界面不会显示落地页。）
* LinkedIn
* iOS版Pinterest
* Snapchat
* X（前身为Twitter）
* 微信

**用户体验**

当用户使用登录页面中的CTA按钮时：

* **如果用户已安装应用**：点击后调起应用。
* **如果用户未安装应用**：跳转到对应的应用商店，并在激活应用后通过延迟深度链接进入应用中的具体页面（详情请见[深度链接与延迟深度链接](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)）。

<div id="note-2" />

> 📘 **注意事项**
>
> 社交应用落地页仅支持OneLink短链。

<div id="to-use-the-social-app-landing-page" />

#### **如需启用社交应用落地页，请按以下步骤操作：**

1. 按下文所述步骤配置落地页。
2. 复制OneLink**短链**。  
   社交应用落地页不支持长链。
3. 社交应用落地页仅支持OneLink短链。

这里的归因结果取决于您的归因设置。

<div id="to-set-up-the-social-apps-landing-page" />

#### **社交应用落地页的设置方式如下：**

1. 从自定义链接的配置页面进入**社媒到应用**部分。
2. 在**社交应用落地页**部分，点击**创建社交应用落地页**。  
   操作界面会打开一个窗口，让您选择落地页模板。  
   [![](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)
3. 将鼠标悬停在选中的模板上，然后点击**创建**。**建议**：可以将鼠标悬停在模板的 🛈 图标上，查看每个模板的使用场景。建议在Instagram中使用Clustered Poster和ShowAndTell模板。
4. 自定义目标网页广告素材中的所有元素。您只需选择要编辑的元素名称，或在预览页面点击相应元素便可进行配置。    
   **建议**：请保存文本，以防更换素材模板时丢失文案。
5. 将模板中的图像换成您自己的图像。  
   1. 输入带有扩展名的图片网址，例如`https://example.com/image.png`。
   2. 可用格式包括：jpeg、jpg、png。   
      **请注意**：不支持webp格式。
   3. 各模板对图像文件的要求请见下表：  

| 模板名称 | 最大图像文件大小 | 图像比例 |
| --- | --- | --- |
| 系列名称 | 300 KB | 16：9（横屏） |
| <ul><li>Trapeze</li><li>Carousel</li><li>ShowAndTell</li></ul> | 300 KB | 1:1 |
| <ul><li>Flyer</li><li>Poster</li><li>Blurry Poster</li><li>Clustered Poster</li></ul> | 300 KB | 9:16（竖屏） |

   4. 如果图片URL不正确，系统会报错，且无法显示素材。   
      [![](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)
6. 点击**查看**，查看落地页素材。   
   如需修改素材，请点击**返回编辑器**。  
   [![](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)
7. 点击**完成**，保存落地页。  
   **重要提示**：新建/更新后的落地页素材仅在自定义链接生成/更新后才会生效。
8. 【可选】如需修改您的落地页，请点击**修改社交应用落地页**。

</Accordion>

<div id="deep-linking-and-deferred-deep-linking" />

<Accordion title="深度链接和延迟深度链接">

您可以通过深度链接向现有用户进行再营销，将他们直接引导到应用中的具体页面，而不用先跳转到应用商店或应用主页。AF会通过再营销逻辑对这些用户进行归因。

延迟深度链接则针对新用户，为他们提供与现有用户一样的深度链接体验，但其中涉及的用户链路有所不同。在延迟深度链接场景中，新用户先跳转到应用商店，然后下载应用，并在首次打开该应用时直接进入应用中的指定页面。

**请注意**：设置深度链接和延迟深度链接时需要安卓和iOS开发人员的支持。

**请按以下步骤设置深度链接和延迟深度链接，将用户引入应用中的指定体验：**

1. 请联系您的iOS和安卓开发人员，确定您的链接中要设置什么样的**deep\_link\_value**（深度链接值）。
   * **deep\_link\_value**（深度链接值）是一个值的名称，指的是用户点击链接后跳转到应用中的哪个具体页面。需要开发人员把**deep\_link\_value**要执行的跳转写入代码中。
   * 开发人员把要执行的任务写入代码中。请把这篇指南发送给开发人员，以便于他们理解技术流程和具体操作：
     * 无论用户是否安装了您的应用，您都可以使用UDL来为他们创建[深度链接和延迟深度链接](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl)。  
       **UDL适配要求：**
       * SDK V6.1或以上版本。
       * 点击回溯窗口最长不能超过15分钟。
     * **请注意**：如果您已经在使用OneLink进行深度链接，那么您可能是通过<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_gcd_legacy">安卓</Anchor>和<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_gcd_legacy">iOS</Anchor>的历史API方式实现的，而不是UDL。  

       <div id="tips" />

       > 👍 **提示**
       >
       > **deep\_link\_value**可以是商品SKU、社交媒体帖子ID、URL路径或任何其他值。
       >
       > 请务必与您的开发人员合作，确定**deep\_link\_value**以及其他参数和参数值的最佳长期解决方案，以尽可能地减少应用更新频次。如需生成多个深度链接，让用户跳转到不同的应用内页面，请与您的开发人员沟通动态值的使用事宜，**避免每次都更改应用代码**。
       >
       > 在上文的示例场景中，市场人员和开发人员共同决定将水果种类设置为**deep\_link\_value**，然后开发人员将该参数值设置为动态，这样市场人员就能够对任何水果页面启用深度链接，无需再引入开发人员。
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=apples``...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=bananas``...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=peaches``...`

2. 开发人员确认应用能基于指定的参数和值进行跳转后，请在链接设置页面的**深度链接与跳转**部分输入您与开发人员共同设定的**深度链接值**。
3. 【可选】如果您需要通过深度链接把用户带入多个应用内体验（比如先跳转到产品页然后领取优惠券），可以在深度链接数据内容里再添加一个**其他深度链接值**（使用deep\_link\_sub1参数）。您还可以在**其它参数**部分进一步添加更多深度链接参数（deep\_link\_sub2-10）。
   1. 联系您的iOS和安卓开发人员共同确定参数值。
   2. 开发人员把要执行的任务写入代码中。 将相关OneLink指南发送给开发人员，助其了解技术流程并查看示例。

      <Tabs>
      <Tab title="Android">

      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_overview">安卓开发人员说明文档</Anchor>

      </Tab>

      <Tab title="iOS">

      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_overview">iOS开发人员说明文档</Anchor>

      </Tab>
      </Tabs>

   3. 在**其它参数**部分，根据实际需要添加自定义参数**deep\_link\_sub2-10**及对应的值，具体取决于您与开发人员的共同决策。

<div id="note-4" />

> 📘 **注意**
>
> 开发人员添加参数和动态值后，市场人员就可以使用OneLink API自动生成数千个自定义链接。<Anchor target="_blank" href="/marketers/zh/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">了解详情</Anchor>

</Accordion>

<div id="redirection" />

<Accordion title="跳转">

**如需让新用户跳转到落地页（而非应用商店），请按以下方式操作**：

1. 在链接设置页面的**深度链接与跳转**部分，下滚至“若用户未安装相关应用”，选择“网址”，让用户跳转到另一个URL。  
   安卓及iOS自定义链接会让新用户跳转到您指定的落地页。   
   **请注意：** 如果您已经在OneLink模板中设置了自定义的跳转URL，那么模板中的自定义URL会覆盖这里设置的URL。
2. 您也可以将新用户引导到<Anchor target="_blank" href="/marketers/zh/docs/redirect-users-to-custom-app-store-product-pages">自定义产品页</Anchor>。

</Accordion>

<div id="additional-parameters" />

<Accordion title="其他参数">

您可以根据实际需求在链接中另外添加一些其他参数，如广告系列、广告组名称、广告名称、流量入口、自定义参数或1-5个<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">可配置参数</Anchor>，从而对营销效果进行更为深入细致的分析。详情请见<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">其它归因参数</Anchor>。

您还可以另外添加其他的深度链接参数（deep\_link\_sub2-10）。

**添加参数的方法如下**：

1. 在链接设置页面的**其他参数**部分，点击**添加参数**。
2. 选择要添加的参数，或输入自定义参数。

</Accordion>

<div id="testing" />

<Accordion title="测试">

您可以对链接进行测试，检查其跳转是否可以对以下用户正常生效：

* 未安装应用的新用户
* 已安装应用的现有用户

<div id="new-users-without-your-app-installed" />

#### 未安装应用的新用户

**前期准备**：没有安装应用但已<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices">加白的测试设备</Anchor>。

**测试链接的方法如下**：

1. 从AppsFlyer后台的侧边栏中选择**互动** > **OneLink管理**。
2. 将鼠标悬停在测试链接的**操作**图标上，然后点击**获取URL**。
3. 将短链或长链发送到您的测试设备上。您可以：
   * 扫描二维码。
   * 将链接通过邮件或WhatsApp发送给自己，然后在手机上打开该链接。  
     **请注意：** 请不要将链接复制粘贴到iOS记事本或浏览器中，因为这种情况下，移动端操作系统会有意不打开相关应用。
4. 在手机上点击该链接。  
   正常情况下，您会跳转到与您的操作系统对应的应用商店或落地页。  
   **请注意**： 请务必在您的测试设备上完成实际点击，Javascript或301/302跳转无法触发Universal Link和安卓App Link。在部分浏览器中，即使是最基础的跳转也无法通过这些方法实现。
5. 下载并启动该应用。
   * 正常情况下，应用会自动打开并进入主页。
   * 如果您在应用中写入了延迟深度链接，那么该应用就会在打开时进入链接参数中指定的内容。
6. 在AppsFlyer的**数据总览面板**中查看是否出现了一个新增激活。  
   这个新增激活应该显示在链接中指定媒体渠道（如test）和广告系列的名称下。

如果您的链接效果不符合预期，请查看<Anchor target="_blank" href="/marketers/zh/docs/onelink-troubleshooting-and-faq">OneLink疑难解答及问题排查指南</Anchor>。

<div id="existing-users-with-your-app-installed" />

#### 已安装应用的现有用户

**前期准备**： 在安卓和/或iOS设备中安装相关应用， 并确保该应用的来源和版本准确无误（即应用中已接入Universal Link、App Link和/或URI Scheme）。

**测试链接的方法如下：**

1. 从AppsFlyer后台的侧边栏中选择**互动** > **OneLink管理**。
2. 点击选定的**OneLink模板**。
3. 从列表中选择相关的自定义链接。
4. 将鼠标悬停在测试链接的**操作**图标上，然后点击**获取URL**。
5. 将短链或长链发送到您的测试设备上。您可以：
   * 扫描二维码。
   * 将链接通过邮件或WhatsApp发送给自己，然后在手机上打开该链接。  
     **请注意：** 请不要将链接复制粘贴到iOS记事本或浏览器中，因为这种情况下，移动端操作系统会有意不打开相关应用。
6. 在手机上点击该链接。
   * 正常情况下，应用会自动打开并进入主页。
   * 如果您在应用中写入了深度链接，那么该应用就会在打开时进入链接参数中指定的内容。
7. 从AppsFlyer后台进入**数据总览**面板 (**视图类型：再营销**）。  
   在该URL中所设的媒体渠道名称（如“test“）和广告系列名称下查看是否出现了新增点击/激活。

如果您的链接效果不符合预期，请查看<Anchor target="_blank" href="/marketers/zh/docs/onelink-troubleshooting-and-faq">OneLink疑难解答及问题排查指南</Anchor>。

</Accordion>

<div id="additional-procedures" />

## 其他操作

<div id="create-a-custom-impression-url" />

<Accordion title="创建自定义展示链接">

您可以利用自定义展示链接：

* 衡量广告的<Anchor target="_blank" href="/marketers/zh/docs/about-conversion-rates#marketing-funnel-stages-and-conversion-rates-1">展示到点击转化率</Anchor>。
* 获取广告展示的归因信息。

**前期准备：** 一条有效的OneLink自定义链接（长链）。此操作不能使用短链。

**涉及职能：**

市场人员和网页端开发人员

**若仅需衡量展示量，请按以下步骤创建展示链接：**

1. 从AppsFlyer后台的侧边栏中选择**互动** > **OneLink管理**。
2. 将鼠标悬停在测试链接的选项菜单上，然后点击**获取URL**。
3. 复制OneLink长链，进行编辑。   
   示例：`https://subdomain.onelink.me/j7rN?pid=email&c=Spring`
4. 将链接中的子域名（或者整个品牌域名）改为“impressions”。  示例：`https://impressions.onelink.me/j7rN?pid=email&c=Spring`
5. 复制展示链接并发送给开发人员。
6. 让开发人员在网站逻辑中部署该展示链接。

您所生成的这个展示链接可用于统计网站页面的展示次数，但不能用来**对新增激活进行归因**。 如果需要进行浏览型归因，请按以下步骤操作。

**要将展示链接用于归因，请执行以下操作：**

1. 按上文步骤生成展示链接。
2. 请确保您<Anchor target="_blank" href="/marketers/zh/docs/measure-view-through-engagements">已启用浏览型归因</Anchor>。
3. 【可选】浏览型归因的默认<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">回溯窗口</Anchor>是1天，如果您想要调整这个窗口，请添加`af_viewthrough_lookback`参数并赋以新值，如`af_viewthrough_lookback=1d`。
4. 复制展示链接并发送给开发人员。
5. 让开发人员在网站逻辑中部署该展示链接。

完整的展示链接示例：

```http
https://impressions.onelink.me/j7rN?pid=email&c=Spring&af_viewthrough_lookback=1d
```

</Accordion>

<div id="deep-linking-post-event" />

<Accordion title="事件完成后触发的深度链接">

某些场景中您可能需要让用户完成某个事件后再通过深度链接进入指定的页面，这类事件包括：

* 登录
* 浏览开屏广告
* 接受服务条款
* 以及其他

**如需在事件完成后触发深度链接**：

让开发人员根据操作平台按照相关说明进行操作（[安卓](https://dev.appsflyer.com/hc/docs/dl_android_dl_post_event)和[iOS](https://dev.appsflyer.com/hc/docs/dl_ios_dl_post_event)）。

</Accordion>

<div id="deferred-deep-linking-with-ios-private-relay" />

<Accordion title="iOS Private Relay启用时的延迟深度链接">

Apple新上线的iOS 15系统为iCloud用户提供了<Anchor target="_blank" href="https://www.macworld.com/article/348965/icloud-plus-private-relay-safari-vpn-ip-address-encryption-privacy.html">Private Relay</Anchor>（保密传送）功能，用户可以通过该功能选择对自己的网页浏览流量加密，并隐藏自己的确切位置、IP地址以及浏览内容。如果用户启用了Private Relay，可能会对归因和延迟深度链接造成影响。也就是说，如果一个还没有安装应用的用户到应用商店去下载并启动了应用，Private Relay可能会在首次启动时阻止其跳转到应用中的具体页面。

您可以使用以下任意一个AppsFlyer解决方案来确保延迟深度链接（DDL）正常生效：

* **【推荐】App Clip方案**：您可以创建一个App Clip（苹果小程序），然后通过这个App Clip来获取用户归因数据，并将用户引导到定制化的App Clip体验中，这跟DDL能实现的功能一样。您还可以在App Clip中添加一条路径，把用户从App Clip引导到完整版应用。
* **剪贴板方案**：创建一个落地页，用来复制URL中的延迟深度链接的数据，并让用户跳转到应用中指定的页面。**请注意**：此方案不能解决归因问题。

<div id="app-clipbased-solution" />

<Accordion title="App Clip解决方案">

该方案结合了OneLink短链与iOS的App Clip技术，可以让用户在不安装完整应用的情况下获得特定的产品体验。OneLink短链能为广告主提供用户归因数据，并把用户带入指定的App Clip体验，这与DDL的功能类似。您还可以在App Clip中添加一条路径，把用户从App Clip引导到完整版应用。**请注意**：如果用户在卸载完整版应用后，又通过App Clip进行了重新安装，那么这次激活在AppsFlyer面板上会记为自然量。 

<div id="flow" />

#### **链路**

基于App Clip的DDL方案链路如下：

1. 广告主创建App Clip，将其添加到OneLink模板中，为已启用Private Relay的用户实现跳转。
2. 用户点击OneLink链接。
3. AppsFlyer的网页消息机制（handler）检测以下信息：
   * 设备是否使用iOS 15+系统
   * 浏览器是否为Safari
   * 用户是否启用了Private Relay
4. AppsFlyer根据上述信息，在用户界面中展示**播放App Clip**或**在Safari中浏览**的弹窗。
   * 如果用户点击**播放App Clip**，则会触发App Clip卡片播放。
   * 如果用户点击“在Safari中浏览”，则会触发落地页打开，引导用户打开App Clip。
5. 用户打开App Clip。
6. App Clip打开，并根据市场人员和开发人员的设置为用户提供个性化体验。
7. 如果App Clip中包含了引导用户使用完整版应用的路径，那么用户会跳转到App Store下载完整版应用，然后在首次打开应用时，进入指定的用户体验。

**前期准备：** AppsFlyer SDK V6.4.0+

**请按以下步骤配置基于App Clip的DDL方案**：

1. 让开发人员按照<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#app-clip-based-solution">App Clip方案的开发者文档</Anchor>创建App Clip，为用户提供个性化体验，还可以在其中添加一条路径，把用户从App Clip引导到完整版应用。
2. 使用[Universal Link](https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links)和[延迟深度链接](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)，创建或编辑<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">OneLink模板</Anchor>。
3. 在OneLink模板中，打开**用户启用Private Relay时显示App Clip**的开关。请确保App Clip已创建完毕，然后再打开这个开关。  
   **请注意**：使用Universal Link修改OneLink模板（包括添加或移除App Clip功能）时，AASA文件可能需要几个小时才能更新完毕。因此，您基于修改后的模板所创建的链接可能无法立刻实现新增功能。
4. 基于OneLink模板创建自定义链接。
5. 从App Store Connect后台进入**App Clip Experience**板块，向下滚动到**App URLs**，然后输入您的OneLink模板URL（即域名+模板ID，如`yourbrand.onelink.me/GrbZ`）或具体的OneLink短链。  
   **请注意**：如果您输入了某一条OneLink自定义链接，那么App Clip方案仅在用户点击这条链接的时候才会生效，而不会对基于同一个OneLink模板创建的其他链接生效。

</Accordion>

<div id="clipboardbased-solution" />

<Accordion title="剪贴板解决方案">

<div id="flow-1" />

#### **链路**

基于剪贴板的DDL解决方案链路如下：

1. 广告主创建一条延迟深度链接，其中包含`af_cp_lp=true`参数。
2. 用户点击这条延迟深度链接。
3. AppsFlyer检测以下信息：
   * 设备是否使用iOS 15+系统
   * 浏览器是否为Safari
   * 用户是否启用了Private Relay
   * 该链接是否包含`af_cp_lp=true`参数
4. AppsFlyer确认以上信息后，打开落地页。其中包含应用图标、图像以及CTA按钮，引导用户去App Store下载应用，同时跳出弹窗信息，向用户解释复制URL是为了让他们跳转到应用具体页面时享受最流畅的用户体验。  
   ![ios_15_ip_masking__1_.png](https://files.readme.io/c130314c98ebd42f50feaafd752c0cea954f42c5bfd99a6dbd94daf9e48c2ff4-30151216595345.png)
5. 用户点击**下载应用**。
6. 用户跳转到App Store并下载应用，然后在首次启动应用时进入指定的页面。

<div id="requirements" />

#### **要求**

如果您要使用复制/粘贴落地页DDL解决方案，需确保以下几点：

* 用户在Safari上浏览网页。
* 延迟深度链接中包含`af_cp_lp=true`参数。
* 接入AppsFlyer iOS SDK V6及以上版本。
* 您的iOS应用开发人员需要添加代码，把剪贴板里的延迟深度链接数据粘贴到URL中。该操作不在AppsFlyer SDK的控制范围内。
* 用户勾选弹窗中的复选框（默认勾选）。如果没有勾选，则无法复制URL，延迟深度链接也无法生效。

<div id="setup" />

#### **设置**

**请按以下步骤配置基于剪贴板的DDL解决方案**：

1. 让您的iOS开发人员完成以下事项：
   1. 根据<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#clipboard-based-solution">开发者文档</Anchor>的说明，在AppsFlyer SDK中接入必要的代码。
   2. 添加代码，把剪贴板里的延迟深度链接数据粘贴到URL中。该操作不在AppsFlyer SDK的控制范围内。
2. 在您的链接中添加`af_cp_lp=true`参数。   
   您可以在AppsFlyer的OneLink界面中把它添加为自定义参数，或者直接在链接中插入这个参数。

</Accordion>

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="examples" />

<Accordion title="示例">

**基础示例**

Mark负责为一家名为“Feed Me”的生鲜配送服务商进行市场推广。他希望利用电话号码来触达用户，让他们下载新的Feed Me软件，该软件有iOS和安卓两个版本。为此他策划了一个短信营销方案。但是，Mark无法区分哪些用户使用安卓设备，哪些使用iOS设备。他也不知道哪些用户已经安装了这个应用，哪些还没有安装。

为了解决这个问题，Mark决定在短信中发送一条通过OneLink生成的短链。用户收到短信并点击这条链接时会形成以下链路：

* 如果用户还未安装应用，则点击链接后会自动跳转到与其设备适配的应用商店或落地页，引导其安装应用。
* 如果用户已经安装了应用，则点击后调起应用。

AppsFlyer会将相关的新增激活和再互动归因到这次短信营销活动，这样，Mark就能在AF后台查看短信营销的效果。

**深度链接示例**

接上文示例场景：负责市场推广的Mark投放营销短信后，成功拉动了部分潜在用户下载并打开应用。但是，在点击链接并打开应用的用户中，最后真正下单的并不多。

因此，Mark决定推出下单即送活动，赠品分别为一袋桃子、苹果或牛油果，希望以此来提高转化率。为此，Mark为现有用户打造了丝滑流畅的深度链接体验，并向他们发送邮件，着重宣传这3种水果如何有益健康。

Mark使用OneLink为这3种水果分别创建了一条带有深度链接值的链接，链接配置完成（需与移动端开发人员配合）后可实现以下功能：

为了解决这个问题，Mark决定在短信中发送一条通过OneLink生成的短链。用户收到短信并点击这条链接时会形成以下链路：

* 如果用户已经安装了应用，则点击链接后会直接进入应用中对应水果的页面。
* 如果用户还没有安装应用，则点击链接后会跳转到与其设备适配的应用商店或落地页，引导其下载应用，并在用户首次打开应用时，让其直接进入相关的水果页面。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| <span id="onelink-characters"></span>OneLink特点 | <ul><li>URL总长度不得超过2000个字符</li><li>链接名称和媒体渠道: 不得超过100个字符</li><li>短链ID不能超过50个字符</li><li>参见其他跳转参数<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters#special-characters">特性与局限性</Anchor>。</li></ul> |
| <span id="maximum-links"></span>链接数量上限 | 每个账号最多可以在AppsFlyer中创建12万条OneLink链接。 |
| <span id="posting-onelink-urls-in-web-pages"></span>在网页中发布OneLink链接 | 当HTML的href属性值中包含`target="_blank"` 时，链接不会跳转到Google Play或App Store。 如果OneLink链接被嵌套在带有**target="\_blank**"属性值的HTML **a** 标签中，该链接会在安卓或iOS设备的Chrome浏览器中打开一个空白页。由于这会影响到OneLink的效用，因此请确保 **a**标签中不包含上述属性值。 |
| <span id="agencies"></span>代理 | OneLink模板或链接仅适用于自定义/自有媒体，不对代理开放。 |
| <span id="ad-networks"></span>广告平台 | OneLink模板或链接仅适用于自定义/自有媒体，不对代理开放。 |
| <span id="social-media-preview-image"></span>社交媒体预览图像 | <ul><li>如果您所选用社交媒体平台不支持您所设置的图像类型，则无法显示预览。</li><li>用于WhatsApp的图像大小不能超过300KB。</li></ul> |
| <span id="desktop"></span>PC端 | 如果您想让PC端用户在点击OneLink链接后跳转到其他网址，那么请在配置OneLink链接或模板时使用`af_web_dp`参数，并在其中添加该网址。如果用户在PC端点击了包含`af_web_dp`的链接，AppsFlyer不会将其记为一次点击。 |
| <span id="af_enc_data"></span>af\_enc\_data | 不适用于展示链接。 |
| <span id="android-social-apps-webview-deep-linking-redirection"></span>安卓社交应用的Webview深度链接跳转 | 安卓社交应用近期发生更新，使得内部浏览器展示（WebView）中的部分深度链接和店铺跳转链路断裂。<br /><br />**安卓App Link**<br /><br />在Facebook应用内浏览器中点击时，Android App Links暂不支持跳转。使用URI Scheme的链接可以正常跳转。<br /><br />**商店跳转**<br /><br />为了兼容此次更新，让深度链接和商店跳转继续生效，我们针对以下安卓社交应用推出了新的用户互动链路：<ul><li>v420以上的版本Facebook</li><li>Instagram</li><li>Facebook Messenger</li><li>Snapchat</li></ul>新的用户链路需要上述应用的用户另行点击一个落地页按钮，才能触发跳转，进入Google Play Store或其他第三方应用商店。<br /><br />该按钮会被自动添加，无需任何操作。<br /><br />**请注意：**<ul><li>在420及以下版本的Facebook中，深度链接可正常跳转，无需添加其他的用户互动链路。</li><li>Facebook帖子中使用URI scheme的App Link可正常跳转，无需添加其他的用户互动链路。</li><li>Instagram私信中的App Link可正常跳转，无需添加其他的用户互动链路。</li><li>在深度链接链路中，若用户未安装相关应用，系统会弹出报错消息。但该消息不会影响用户互动链路，用户仍会正常跳转到商店。</li></ul> |
| <span id="onelink-link-previews-sometimes-fail-to-display-correctly-on-facebook-and-linkedin"></span>OneLink链接预览 | **说明**  <br />OneLink链接预览在Facebook和LinkedIn上有时可能无法正常显示。如果作为跳转终点的网站无法识别出预览请求中的用户代理（user-agent）字符串`AppsFlyerBot-Previewer/1.0`来自robot（或爬虫），就会出现这个问题。这时，相关网站无法正常响应带有OG标签的预览内容。<br /><br />**解决方法**  <br />您可以<Anchor target="_blank" href="https://moz.com/learn/seo/robotstxt">更新您网站的robot.txt文件</Anchor>，使相关落地页将带有`AppsFlyerBot-Previewer/1.0`用户代理请求头（user-agent header）字符串的页面视为来自robot。 |
| <span id="deep-linking-is-not-supported-on-android-naver-blog-app"></span>Android Naver Blog应用 | 安卓版Naver Blog应用不支持深度链接，用户点击后会跳转到Google Play Store或相关链接指定的网页。 |
| <span id="chrome-browser-on-ios"></span>iOS上的Chrome浏览器 | iOS版的Chrome发生了更新。更新后，用户在iOS的Chrome中点击URI scheme链接时，界面会跳出弹窗，让用户确认是否要打开相关应用/跳转到App Store。 |
| <span id="telegram-webview"></span>Telegram Webview | 由于该WebView在发起交互请求未包含设备型号和操作系统版本信息，因此概率模型归因不适用于Telegram WebView（Telegram浏览器）中的用户交互。 |

</Accordion>

<div data-zendesk-anchors="onelink-links-and-experiences=onelink%E9%93%BE%E6%8E%A5%E4%B8%8E%E7%94%A8%E6%88%B7%E4%BD%93%E9%AA%8C h_01H8Y6DDT4M8XGAEJJVTHKHPKV=onelink%E9%93%BE%E6%8E%A5%E4%B8%8E%E7%94%A8%E6%88%B7%E4%BD%93%E9%AA%8C create-a-onelink-link=%E5%88%9B%E5%BB%BAonelink%E9%93%BE%E6%8E%A5 h_01H8Y6DDT41C6JYKXET0NDRB1G=%E5%88%9B%E5%BB%BAonelink%E9%93%BE%E6%8E%A5 h_01JRX3VWTVE77QVNG37BKPKHWW=%E6%B3%A8%E6%84%8F h_01H8Y6DDT4C543RS2BXAGS487M=experiences h_01H8Y6DDT4WZ5FKZYBX2H08MFD=general-settings enable-retargeting-for-the-app=%E5%9C%A8%E5%BA%94%E7%94%A8%E9%85%8D%E7%BD%AE%E4%B8%AD%E5%90%AF%E7%94%A8%E5%86%8D%E8%90%A5%E9%94%80 h_01H8Y6DDT4R7785X5DRES66BKJ=%E5%9C%A8%E5%BA%94%E7%94%A8%E9%85%8D%E7%BD%AE%E4%B8%AD%E5%90%AF%E7%94%A8%E5%86%8D%E8%90%A5%E9%94%80 h_01H8Y6DDT4JT9H0R13ZNGHJ79S=social-media-preview-og-tags h_01H8Y6DDT4PHY2F5E3GK582P51=social-app-landing-page h_01H8Y6DDT463F5569B28DD17SV=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01H8Y6DDT4MMD1AW6D1PNGNX5X=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 to-use-the-social-app-landing-page=%E5%A6%82%E9%9C%80%E5%90%AF%E7%94%A8%E7%A4%BE%E4%BA%A4%E5%BA%94%E7%94%A8%E8%90%BD%E5%9C%B0%E9%A1%B5%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%AD%A5%E9%AA%A4%E6%93%8D%E4%BD%9C h_01H8Y6DDT4JB4RT438MAGNNX2S=%E5%A6%82%E9%9C%80%E5%90%AF%E7%94%A8%E7%A4%BE%E4%BA%A4%E5%BA%94%E7%94%A8%E8%90%BD%E5%9C%B0%E9%A1%B5%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%AD%A5%E9%AA%A4%E6%93%8D%E4%BD%9C to-set-up-the-social-apps-landing-page=%E7%A4%BE%E4%BA%A4%E5%BA%94%E7%94%A8%E8%90%BD%E5%9C%B0%E9%A1%B5%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F%E5%A6%82%E4%B8%8B h_01H8Y6DDT4G34S3RV3ZH64XT19=%E7%A4%BE%E4%BA%A4%E5%BA%94%E7%94%A8%E8%90%BD%E5%9C%B0%E9%A1%B5%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F%E5%A6%82%E4%B8%8B h_01H8Y6DDT5XNJVYW2Y8F6JWPK2=deep-linking-and-deferred-deep-linking h_01H8Y6DDT5JR3B3DMR87JCBZ69=%E6%8F%90%E7%A4%BA h_01H8Y6DDT5KSBE00WWDGQ5R1AQ=%E6%B3%A8%E6%84%8F-1 h_01H8Y6DDT58FC3HMSRZBMGZZRJ=redirection h_01H8Y6DDT5AAQ3BZD8QB9H19QB=additional-parameters h_01H8Y6DDT5B6M7CETQRD9NKX8R=testing new-users-without-your-app-installed=%E6%9C%AA%E5%AE%89%E8%A3%85%E5%BA%94%E7%94%A8%E7%9A%84%E6%96%B0%E7%94%A8%E6%88%B7 h_01H8Y6DDT50DH5TGVVPJPJC4MG=%E6%9C%AA%E5%AE%89%E8%A3%85%E5%BA%94%E7%94%A8%E7%9A%84%E6%96%B0%E7%94%A8%E6%88%B7 existing-users-with-your-app-installed=%E5%B7%B2%E5%AE%89%E8%A3%85%E5%BA%94%E7%94%A8%E7%9A%84%E7%8E%B0%E6%9C%89%E7%94%A8%E6%88%B7 h_01H8Y6DDT5KDEWS40XPYGYC8HK=%E5%B7%B2%E5%AE%89%E8%A3%85%E5%BA%94%E7%94%A8%E7%9A%84%E7%8E%B0%E6%9C%89%E7%94%A8%E6%88%B7 additional-procedures=%E5%85%B6%E4%BB%96%E6%93%8D%E4%BD%9C h_01H8Y6DDT5YR8JA5YMZFPMCC2X=%E5%85%B6%E4%BB%96%E6%93%8D%E4%BD%9C h_01H8Y6DDT58EFS8S46D1AVP3T1=create-a-custom-impression-url h_01H8Y6DDT5S4NEJMNJR4K3QMNH=deep-linking-post-event h_01H8Y6DDT58Y6CS27M2W3MHYAD=deferred-deep-linking-with-ios-private-relay h_01H8Y6DDT5A7J07KNNRWCXCBH2=app-clipbased-solution flow=%E9%93%BE%E8%B7%AF h_01H8Y6DDT5VDKAR89B8N6D7YMB=%E9%93%BE%E8%B7%AF h_01H8Y6DDT62H71A8DPG00A3ZTN=clipboardbased-solution flow::21baf6ac=%E9%93%BE%E8%B7%AF-1 h_01H8Y6DDT638T7C9HQHZ1CJ726=%E9%93%BE%E8%B7%AF-1 requirements=%E8%A6%81%E6%B1%82 h_01H8Y6DDT6JGP33AWFQV6Z8FF0=%E8%A6%81%E6%B1%82 setup=%E8%AE%BE%E7%BD%AE h_01H8Y6DDT61ENGJFZ1XS28GS1T=%E8%AE%BE%E7%BD%AE additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01H8Y6DDT679SGBTSM669F9FHV=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01H8Y6DDT6TX4WTP2HYRF11DZ3=examples h_01H8Y6DDT6TQYRS81BMHARB62S=traits-and-limitations" />

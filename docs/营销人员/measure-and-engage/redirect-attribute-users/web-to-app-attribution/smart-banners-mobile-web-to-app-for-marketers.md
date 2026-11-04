---
title: 智能横幅——移动端网页到应用解决方案（市场人员专用）
metadata:
  keywords:
    - Landing Page
    - Advertisers
    - Web Attribution
    - Developers
    - Smart Banner
    - sb
    - Marketers
    - Banner
    - Banners
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2019-01-14T12:33:07Z'
  edited_at: '2026-10-14T10:03:33Z'
  id: 360000764837
  locale: zh-cn
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000764837
---
> **概要：** 本文介绍了如何通过智能横幅将您的网页用户转化为应用用户。

[![](https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg)](https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg)

<div id="note" />

> 📘 **注意**
>
> AppsFlyer智能横幅网页SDK v1已于2023年11月8日下线。如需在您的网站中展示智能横幅，请升级到v2。<Anchor target="_blank" href="/marketers/zh/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">了解详情</Anchor>

<div id="smart-banners" />

## 智能横幅

智能横幅：

* 您可以在**移动端品牌网站上展示智能横幅**，推动高意向用户的转化。
* 可帮助您衡量移动端网页用户的质量。
* 可帮助您将移动端的网页到应用流量准确地归因到各种渠道（包括SRN）。
* 您可以对智能横幅进行<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model#用户互动归因类型">浏览型归因和点击型归因</Anchor>，并统计展示量：
  * **点击：** 用户点击智能横幅广告，然后安装并打开应用。
  * **展示：** 当横幅广告加载完毕时（即用户看到该横幅广告时），向AppsFlyer发送展示统计事件。

用户邀请场景中的归因链路如下：

1. 用户点击广告后跳转到广告主的移动端网页。
2. 广告主的移动端网页上[展示](/docs/smart-banners-mobile-web-to-app-for-marketers#banner-group-display-logic)智能横幅。
3. 用户点击智能横幅，然后：
   * **如果用户尚未安装应用**，则会跳转到应用商店的相应页面，安装并激活应用。
   * **如果用户已安装应用**，则会通过Universal Link、App Link和/或URI链接直接打开应用。
4. 用户进入与推广活动相关的应用内页面。
5. AF将用户归因给最初展示点击广告的媒体渠道。

**人员**

* 网站开发人员仅需<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#installation">在网站的HTML中写入一个代码片段</Anchor>。
* 其他操作仅涉及市场人员。

---

**前期准备**

* 确保您有一个AppsFlyer帐户，且账户中至少有一个应用。
* 确保<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">OneLink模板</Anchor>中包含由智能横幅推广的应用。这是为了让智能横幅能根据设备的操作系统将移动端网页用户跳转到相应的应用商店。

---

**所需时间**

大约20 分钟。

---

**成果**

* 网页用户点击CTA按钮后会跳转到与其设备操作系统相对应的应用商店或网页。
* 应用用户点击CTA按钮后会深度链接到应用中的具体内容。
* AF会根据用户的点击/激活将其归因到初始媒体渠道或您的自有媒体。
* 您可以在投放效果页面和卡片中查看横幅投放效果。

---

---

<div id="example" />

> 📄 **示例**
>
> Mark负责食品配送服务商Feed Me的市场营销工作。
>
> 他想要把Feed Me的移动端网页用户转化为应用用户。
>
> 为此，Mark运用自己的图像和文字素材创建了智能横幅广告。
>
> 智能横幅是通过OneLink技术实现的。移动端网页用户点击CTA按钮后，智能横幅广告**会自动将其跳转到正确的应用商店或落地页**，便于用户安装相关应用。当现有应用用户点击CTA按钮时，智能横幅广告会直接吊起应用。
>
> 然后，AppsFlyer**会将点击/激活归因到Mark指定的媒体渠道和广告**。

<div id="important" />

> 🚧 **重要提示！**
>
> AppsFlyer的智能横幅和iOS Safari的Smart App Banner两者之间只能选择一种，切勿同时使用，否则会使移动端网页无法正常显示，并造成归因差异。

<div id="setup" />

## 设置

按下文所述流程创建智能横幅后可实现以下功能：

* 通过智能横幅让用户从移动端网页跳转到与其操作系统相对应的应用商店或应用页面。
* 通过OneLink将点击/激活归因到您的自有媒体渠道。

<div id="1-website-workplace-setup" />

<Accordion title="1. 网页配置中心的设置">

<div id="prepare-your-mobile-site-to-display-smart-banners-for-the-first-time" />

#### 首次在移动端网站中投放智能横幅前，您需要先完成以下准备工作：

1. 从AppsFlyer后台的侧边栏中选择**互动** > **网页到应用** > **智能横幅** > **进入智能横幅板块**。
2. 点击**开始使用**，然后按照设置向导工具的指示完成必要的配置步骤。网站配置中心的详细设置指南请见下文。
3. 为该网页配置中心设置一个名称。
4. 点击**创建**。打开网页配置中心界面。
5. 复制横幅的**代码片段**。
6. 将该代码片段写入您的网站中。每个网站只需写入一次。
   * 如需通过Google Tag Manager、Adobe Tag Manager、Shopify、Wix、Squarespace或WordPress将该代码添加到您的网站，请参考<Anchor target="_blank" href="/marketers/zh/docs/smart-banners-website-code-implementation-for-marketers">营销人员的智能横幅网页代码添加指南</Anchor>。
   * 如需通过其他平台添加该代码，或根据实际需求（包括添加参数、深度链接、隐藏横幅或结合PBA使用智能横幅等）更改该代码，请参考<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">开发人员专用的智能横幅网页代码添加指南</Anchor>。
7. 【可选】复制**Web Key**（该密钥已经包含在代码片段中）。
8. 点击**下一步**。

<div id="to-create-website-workplaces-after-the-first-time" />

#### 后续创建网站配置中心的方式

1. 从AppsFlyer后台的侧边栏中选择**互动** > **网页到应用** > **智能横幅** > **操作台**。
2. 点击选项菜单。
3. 选择**创建新的网站配置**。
4. 为该网页配置中心设置一个名称。
5. 点击**创建**。打开网页配置中心界面。
6. 复制横幅的**代码片段**。
7. 将该代码片段写入您的网站中。每个网站只需写入一次。
   * 如需通过Google Tag Manager、Adobe Tag Manager、Shopify、Wix、Squarespace或WordPress将该代码添加到您的网站，请参考<Anchor target="_blank" href="/marketers/zh/docs/smart-banners-website-code-implementation-for-marketers">营销人员的智能横幅网页代码添加指南</Anchor>。
   * 如需通过其他平台添加该代码，或根据实际需求（包括添加参数、深度链接、隐藏横幅或结合PBA使用智能横幅等）更改该代码，请参考<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">开发人员专用的智能横幅网页代码添加指南</Anchor>。
8. 【可选】复制**Web Key**（该密钥已经包含在代码片段中）。
9. 点击**下一步**。

</Accordion>

<div id="2-banner-group-setup" />

<Accordion title="2. 横幅组的设置">

一个横幅组可包含一个或多个横幅。您可以在这个环节完成下列配置：

* 选择该横幅组需要用到的OneLink模板，其中包含作为网页用户跳转终点的应用。
* 设置一个具体的深度链接scheme。
* 设定该横幅组中所有横幅的定向规则、上线时间、行为以及具体的归因方式。
* 选定具体的展示页面，用户在浏览这些页面时会触发该横幅组中的横幅。

**请按以下步骤创建新的横幅组或横幅组副本：**

1. 从AppsFlyer后台的侧边栏中选择**互动** > **网页到应用** > **智能横幅** 。
2. **如果之前没有创建过横幅组：**
   1. <span class="af-ol-a"></span>点击页面左边的**添加横幅组**。
   2. 从第5步开始，完成各步骤操作。
3. **如需添加其他横幅组：**
   1. <span class="af-ol-a"></span>进入**Studio**选项卡。
   2. 点击 **+新建**。
   3. 从第5步开始，完成各步骤操作。
4. **如需创建某个横幅组的副本：**
   1. <span class="af-ol-a"></span>点击删除图标旁边的**创建副本**图标。
5. 设置一个具有唯一性的**横幅组名称**，且能反映出组下各横幅的共同主题（如要推广的应用）。
6. 选择该横幅组要用到的OneLink模板。
7. 【可选】为该横幅组设置**URI scheme**，作为Universal Link和App Link失效时的备用方案，为用户打开应用。由于该值默认从OneLink模板中提取，因此一般情况下很少会用到这个方案。只有在使用模板以外的值时，才需要为横幅组设置URI scheme。
8. <span id="attributed-sources"></span>设置主要及次要**归因渠道**，对来自该横幅组的新增激活进行归因。   
    **关于点击ID传递的注意事项：** 如果传入链接中包含可用的FBCLID、GCLID、WBRAID及GBRAID，这些ID会自动传递到智能横幅生成的传出链接中。对于Google的点击ID，如果传入链接中还包含“keyword”（关键词）参数，则传出链接会以af\_keywords来表达该参数的值。  

   请参考下表，选择最合适的自定义链接方案。

<div id="param-table" />

| 可选方案 | 使用场景 | 注意事项 |
| --- | --- | --- |
| **使用UTM参数** | 当移动端网页的大部分非自然流量来自带UTM参数的渠道时可选用该方式。 | ◦ 媒体渠道名称（pid）= UTM\_Source   <br />◦ 广告系列（c）= UTM\_campaign  <br />◦ 如果UTM\_source或UTM\_campaign出现缺失，则会以静态名称替代。 |
| **使用传入的归因链接参数** | 当移动端网页的大部分非自然流量来自使用AppsFlyer归因链接的点击型广告平台时可选用该方案。 | ◦ 由AppsFlyer归因链接传入的所有可用参数都会添加到智能横幅链接中。<br /><br />◦ 如果传入的AppsFlyer归因链接和智能横幅中同时存在某一个参数，最终的自定义链接中会优先攫取传入的参数。 |
| **添加其它归因参数** | 可根据需要添加其他的网页归因数据，用以对每个激活进行深度剖析。 | 比如，电商网站可以为每个品类创建相同的自定义链接，并以af\_adset的值区分（如“af\_adset=fruit”） |
| **使用默认归因参数** | ◦ 符合以下条件时使用此选项：移动端网页的大部分流量都是自然量。▪ 非自然流量不是从点击型广告平台或带UTM参数的渠道进入网站的。◦ 您可以自行调整参数值。 | <strong>重要提示！</strong>建议选择UTM或传入的归因链接参数，因为自定义链接本来就会使用默认的智能横幅归因参数作为备用，以应对媒体渠道、广告系列或流量入口名称缺失的情况。 |

9. 【推荐】建议设置默认归因参数**Channel name**（流量入口名称），这样就能将所有来自智能横幅的激活归因到具体的流量入口，并能在**群组报告**、**数据总览面板**、**留存报告**等多种报告中将同一个流量入口下多个媒体渠道的数据进行汇总。
10. <span id="2-banner-group-setup-step10"></span>【可选】如果您想要使用该横幅组来记录用户点击横幅后的再互动情况，请打开**再营销**开关。如需进一步了解再营销解决方案，请参阅<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销归因指南</Anchor>。

    <div id="important-1" />

    > 🚧 **重要提示！**
    >
    > 如需使用再营销功能，您需要完成以下操作：
    >
    > * <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#在应用配置中启用再营销">在应用配置中启用再营销</Anchor>


    在非再营销的UA推广中使用基于OneLink的横幅链接时，现有用户点击该链接后也会打开应用，并有相同的用户体验。但是，他们的再次互动被记录为常规互动，这意味着无法评估自有媒体广告活动的成功情况。
11. 【可选】打开**再营销广告中忽略活跃用户**的开关，并设置不活跃窗口。该操作会在您的智能横幅组链接中添加参数af\_inactivity\_window=[天数]，使得再营销归因忽略在此期间的所有活跃用户。
12. 设置再互动窗口期。用户再次打开应用后，在该窗口期以内的应用内事件会归因到再营销渠道。
    * 这个值可以设置为数天（1-90天）、数小时（至多23小时）或用户的整个生命周期。
    * 再互动窗口期会以af\_reengagement\_window参数的形式体现在归因链接中。
13. <span id="dismissal-behaviour"></span>【可选】设置**展示间隔**，即向用户展示了某个横幅后，至少隔多长时间再向该用户展示该横幅。您可从以下3种方案中选择一种：
    * 按时间设置：1小时、1天或1周。
    * 下一个会话（session）：即用户关闭该横幅后，在另一个标签页或窗口中开启的session。
    * 永不：不再展示该横幅。 **请注意**：
      * 如果用户清除了浏览器缓存，或在隐私浏览模式下访问网站，则展示间隔设置会丢失。
      * 展示间隔对已经展示完毕的横幅生效，但同一横幅组下的其他横幅仍可展示。
14. 【可选】设置**频次上限**。  您可以通过频次上限来限定横幅组中的每个横幅对一个独立用户的展示次数。您可以选择**无限制**（即总是展示横幅）或**限制横幅展示次数**。

    举例来说，如果某个横幅组中包含三个横幅，且展示频次上限为1，则这三个横幅对每个用户各展示一次。这种情况下，某用户在三次访问相关网站后，就会看到该横幅组中的所有横幅。从第四次访问开始，该用户就不会再看到这一组中的任何横幅。如果频次上限设置为2，则该组横幅对每个用户各展示2次，也就是说用户在六次访问后才会到达这一组横幅的频次上限。
15. 【可选】设定该横幅要在哪个**操作系统**中展示：
    * 所有的移动端操作系统。
    * 仅安卓或仅iOS。
16. 【可选】**设置**横幅组的上线时间：马上开始（默认）或限时投放。
17. 【可选】设置横幅组上线的**地理位置**。
    1. <span class="af-ol-a"></span>若选择**全球**，该横幅组会对所有用户展示。您可根据需要排除具体地区、国家或州的流量。
    2. 若选择**指定地理位置**选项，则可向一个或多个指定区域的用户展示该横幅组。
18. 【可选】设置**展示页面**，即该横幅组在哪些页面中展示：
    * 【默认】在网站的**所有页面中展示**。 **请注意**：建议至少设置一个在所有页面展示的横幅组，以留作备用。
    * **在指定页面中展示**：在指定页面或链接中展示或不展示横幅。
      * 您可在以下两种方案中选择一种：
        * **指定页面**：指定横幅展示页面的服务器和/或路径，这里输入的任何查询参数都会被忽略。如：http://www.example.com/path?query
        * **URL路径和查询参数**：输入路径和/或查询参数，用于判定横幅是否展示。如：path?query。 **请注意**：切勿输入整条URL，如[http://www.example.com/path?query](http://www.example.com/path?query)，而是仅输入路径和/或请求参数。
      * 您可以使用“and/or”（“和/或”关系）添加最多15个条件。
      * 如果条件之间有冲突，则无法显示横幅。
19. 点击**创建横幅组**。
20. 【可选】再次编辑横幅组，将鼠标悬停在**定向及行为**上，然后点击**编辑**。

<div id="example-1" />

> 📄 **示例**
>
> Mark负责食品配送服务商“Feed Me”的市场营销工作，他决定要宣传该应用的李子促销活动。他决定群发短信，并在广告平台和Google投放广告。
>
> Mark为这个推广活动做了以下准备工作：
>
> * 选择同时使用入链的归因参数以及UTM参数（并将默认参数作为备用，用以对入链和UTM广告以外的渠道带来的点击进行归因）。
> * 向广告平台发送其专属的归因链接，用于广告中，以引导用户进入Feed Me移动端网站的李子促销页面。该链接包含跳转URL（af\_r）参数，并带有链接到李子促销页面的URL：`http://feedme.com/plums_link`。
> * 准备一个Google Ads广告系列，当用户进入网站中带有“plums\_utm”的页面时向其展示广告。
> * 对于短信推广，Mark在广告链接中添加了专属的归因参数，引导用户进入Feed Me移动端网站的李子促销页面。该链接包含跳转URL（af\_r）参数，并带有链接到李子促销页面的URL：`http://feedme.com/plums_link?pid=sms&c=plums`.
>
> 然后，Mark开始投放广告。
>
> 该场景中的用户链路如下：
>
> * 用户看到李子促销广告，点击该广告后进入Feed Me移动端网站。
> * 用户点击Google Ads广告及所有其他广告后，会跳转到入链落地页，分页面触发相应的智能横幅。
> * 在移动端网站上看到智能横幅后点击该横幅。
> * 进入Feed Me应用的下载页面，完成应用激活。
> * 首次打开应用时直接进入李子促销页面。
> * AF将用户正确归因给将其带入Feed Me移动端网站的媒体渠道。

<div id="targeting--behavior" />

#### 定向与行为

定向与行为工具栏中会显示您为该横幅组设定的配置。如需更改配置，请点击“编辑”图标。

</Accordion>

<div id="3-banner-setup" />

<Accordion title="3. 横幅的设置">

**请按以下步骤在横幅组中创建横幅：**

1. 点击**创建横幅**，进入**编辑横幅**页面。
2. 设置该横幅的**名称**。
3. 创建一个**设计素材**：
   1. <span class="af-ol-a"></span>点击**设计素材**，设置该横幅的素材。

      界面会打开一个横幅模板选择窗口。

      [![](https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png)](https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png)
   2. 将鼠标悬停在某个**素材模板**上，然后点击**创建**，进入**搭建素材**页面。
   3. 智能横幅素材中的所有元素都可以调整。您只需选择要编辑的元素名称，或在预览页面点击相应元素便可进行配置。 **请注意：** 部分模板中可能会有一些元素不可用。
      * 标题
      * 说明
      * 评分星级
      * 关闭按钮
      * CTA
      * 应用Logo
      * 背景
      * 横幅位置
      * 横幅填充（用来调整横幅尺寸）
      * 设备透明度
      * 可用的图像格式为：jpeg、jpg、png。 **请注意**：不支持webp格式。  各模板对图像文件的要求请见下表： 

| 模板类型 | 最大图像文件大小 | 图像比例 | 图像高度 | 图像宽度 |
| --- | --- | --- | --- | --- |
| Minimal（极简） | 300 KB | 3:1（宽 x 高） | 70 px | 按屏幕大小缩放 |
| Standard（标准） | 300 KB | 3:1（宽 x 高） | 70 px | 按屏幕大小缩放 |
| Enhanced（优化） | 300 KB | 9:4（宽 x 高） | 110 px | 按屏幕大小缩放 |
| Multi-choice（多按钮） | 300 KB | 9:4（宽 x 高） | 110 px | 按屏幕大小缩放 |
| Promotional（推广） | 300 KB | 4:5（宽 x 高） | 300 px | 按屏幕大小缩放 |
| Multi-choice overlay（多按钮覆盖式） | 300 KB | 9:4（宽 x 高） | 110 px | 按屏幕大小缩放 |
| Interstitial（插屏） | 700 KB | 9:16（宽 x 高） | 按屏幕大小缩放 | 按屏幕大小缩放 |

   4. 点击**查看**，查看横幅素材并检查该素材在不同设备上的展示效果。**请注意**：横幅的预览效果可能会与上线后的展示效果稍有不同。
   5. 如需修改素材，请点击**返回编辑器**。
   6. 点击**完成**，回到横幅设置页面。
4. 【可选】添加自定义归因参数，例如：`ad_adset`和`af_ad`。**请注意**：`pid`、`c`和`channel`这几个参数是横幅组层级的参数，因此不能在横幅层级添加。
5. 新的素材创建完毕并保存后，横幅状态变为“在投”。您可以使用**状态**开关切换横幅状态，让其变为**在投**或**停投**。
6. 点击**全部保存**以保存您的配置，或点击**全部保存并关闭**在保存配置后关闭该横幅设置页面。

<div id="example-2" />

> 📄 **示例**
>
> 另请参考<Anchor target="_blank" href="https://drive.google.com/file/d/1mr6g3uNwlLw6UQ_WgtQZprJMhauw7Xi3/view?usp=sharing">此文档</Anchor>，查看相关使用技巧、窍门和笔记。

</Accordion>

<div id="4-testing" />

<Accordion title="4. 测试">

素材完成后，建议在正式投放**之前**先进行测试。

**请按以下步骤测试智能横幅素材：**

**前期准备：** 请确保已将该智能横幅的代码片段写入您的网站。

1. 在**测试素材**页面，输入已集成智能横幅SDK（详见[开发人员专用的智能横幅指南](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2)）的网页链接。
2. 点击**生成**。
3. 复制生成的链接，将其发送到您的测试机，或用测试机扫描二维码。 **正常情况下，该链接或二维码会让您跳转到相应的网页，并展示您所配置的横幅素材。**
4. 点击**编辑素材**返回素材配置页面，或点击**完成**保存素材。

</Accordion>

<div id="view-banner-performance" />

## 考察横幅效果

您可以在投放效果页面中查看并对比所有横幅的投放效果。

您还可以在各横幅的效果卡片中快速浏览其效果数据。

横幅效果数据包括以下指标：

* 展示
* 点击
* 激活
* 再互动
* 再归因
* 点击率（CTR），计算方式为：点击量/展示量 *100
* 转化率 (CVR)，计算方式为：转化量/点击量 *100

**请注意**：

* 数据是按UTC时间统计的。
* 数据<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">持续滚动更新</Anchor>。
* 数据是分横幅和OneLink模板显示的。也就是说，如果您同时为多个应用（如某应用的安卓和iOS版本）配置了同一个横幅和OneLink模板，则这里显示的效果数据会涵盖所有相关应用。
* CVR可能会高于预期，有时甚至会超过100%，这是因为浏览和点击都会被算作转化。

<div id="performance-page" />

<Accordion title="投放效果页面">

您可以在投放效果页面查看并对比所有智能横幅的效果数据，最多可覆盖90天内的投放效果。

**请按以下方式查看投放效果页面**：

1. 从AppsFlyer后台的侧边栏中选择**互动** > **网页到应用** > **智能横幅** > **投放效果**。
2. 选择您要查看的日期范围。默认为最近7天。
3. 【可选】打开**仅显示当前活跃的横幅**开关。该开关打开时，暂时停投或不活跃的横幅即使在所选时间段内正常投放，也不显示其相关数据。界面显示选定时间段内的效果数据。

</Accordion>

<div id="performance-cards" />

<Accordion title="效果数据卡片">

您可以查看各横幅在过去7天内的效果数据。

**请按以下步骤查看横幅的效果数据**：

1. 从AppsFlyer后台的侧边栏中选择**互动** > **网页到应用** > **智能横幅** > **操作台**。
2. 选择您要查看的横幅所在的网页配置中心和横幅组。
3. 将鼠标悬停在该横幅组的任何一条横幅上。界面会显示过去一周的效果数据。

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="banner-group-display-logic" />

<Accordion title="横幅组的展示逻辑">

AppsFlyer在判定是否显示智能横幅/显示哪个智能横幅时会考虑以下两个问题：

* 横幅组是否设有具体的规则（展示间隔、频次上限、地理位置、展示页面等）？
* 终端用户是否符合展示横幅的规则和条件？

如果以上两个问题的答案都是肯定的，即横幅组设有规则且用户符合展示横幅的条件，那么AppsFlyer就会按下表所述原理展示横幅。

| 横幅组的设置 | 得到展示的横幅 | 示例 |
| --- | --- | --- |
| 单个横幅组 | AppsFlyer会将横幅组中的所有在投横幅平均分配到所有符合条件的用户。 | • 示例1：有1个在投横幅时，则向所有用户展示该横幅。<br /><br />• 示例2：有2个在投横幅时，则一半用户看到横幅1，另一半看到横幅2。<br /><br />• 示例3：共有3个在投横幅，则每个横幅会展示给1/3的用户。<br /><br />• 示例4：横幅组下无在投横幅时，则不展示任何内容。 |
| 多个规则相同的横幅组 | AppsFlyer会将横幅组中的所有在投横幅平均分配到所有符合条件的用户。 | 共有2个横幅组（A和B），每个横幅组中有3个横幅（即共有6个横幅），则每个横幅向1/6的用户展示。 |
| 多个规则不同的横幅组 | AppsFlyer会选择*用户匹配规则最为具体的横幅组*，并将其中的所有在投横幅平均分配到符合条件的用户。如果这些横幅组的规则不同，但具体程度相同，则会展示所有横幅组的横幅。 | • 示例1：共有A和B两个横幅组。横幅组A设置为向全球展示，横幅组B设置为向日本用户展示。由于横幅组B的设置更具体，因此只有该组中的横幅会向日本用户展示。如果该横幅组中无在投横幅，则不展示任何内容。<br /><br />• 示例2：共有A和B两个横幅组，横幅组A设置为向全球展示，而横幅组B设置为向乌克兰以外的全世界展示。由于横幅组B的设置更具体，因此仅该组中的横幅会展示给除乌克兰以外的全球用户。如果B组中没有在投横幅，则不展示任何内容。组A的横幅向乌克兰用户展示。<br /><br />• 示例3：共有A和B两个横幅组。组A设置为在日本展示，组B设置为在4月展示。两组的设置不同但具体程度相同。由于两组的优先级没有高低之分，因此日本用户在4月中会同时看到AB两组的横幅。 |

</Accordion>

<div id="ab-testing-banner-performance" />

<Accordion title="横幅效果的A/B测试">

您可以在效果面板中对比各横幅的投放效果，从而对横幅进行A/B测试。如需获取额外的归因相关数据，建议您添加`af_adset`、 `af_ad`或其他归因参数（`pid`、`c`和`channel`除外），并为每个横幅素材或横幅组配置独立的值。这样，您就能在AppsFlyer的面板和报告中使用这些参数来对比各横幅组的投放效果。

</Accordion>

<div id="faq" />

## 常见问题解答

<div id="why-does-my-banner-not-display" />

<Accordion title="为什么页面中没有展示我的横幅？">

这是由于您在横幅组层级设置的频次上限造成的。频次上限决定了横幅组中的每个横幅对一个独立用户的展示次数。 假设您将频次上限设置为3，那么如果一个用户4次访问您的网站，她在前三次访问时都会看到同一个横幅，但从第4次开始就不会再看到该横幅。您也可以关闭频次上限。请在这一步选择一个频次上限的值或关闭频次上限。

</Accordion>

<div id="can-i-use-my-own-font-for-my-banner" />

<Accordion title="能否在横幅中使用我司专用的字体？">

可以。您可以将横幅中的字体设置为您网站的专用字体，具体请按照[开发者资源中心的说明](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#control-smart-banner-font)进行操作。使用专用字体时请注意以下事项：

* 需要网页开发人员接入专用字体。
* 该字体会对您网站中的所有横幅以及横幅中的所有文字元素生效。
* 无法在素材编辑器中查看该字体。
* 接入字体后，请[测试您的横幅素材](/docs/smart-banners-mobile-web-to-app-for-marketers#4-testing)。
* 如果您的字体无法正常显示，请在[素材编辑器](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup)中重新保存您的横幅。

</Accordion>

<div id="can-i-add-parameters-to-the-url-of-my-smart-banners" />

<Accordion title="可以在智能横幅的URL中添加参数吗？">

是的，您可以在相关智能脚本中调用以下两个函数：

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">showBanner</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams">updateParams</Anchor>

</Accordion>

<div id="do-smart-banners-support-deep-linking" />

<Accordion title="智能横幅是否支持深度链接？">

区分。如需实现深度链接，请按以下任意一种方式添加<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep\_link\_value参数</Anchor>：

* 在AppsFlyer后台的[横幅设置](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup)页面中添加静态的自定义归因参数。
* 在[showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=)函数中使用additionalParams，可在展示横幅前向URL中添加参数。
* 使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams">updateParams</Anchor>函数，可在横幅展示后向URL中添加参数。

请确保您的开发人员在deep\_link\_value中写入正确的深度链接行为。

</Accordion>

<div id="can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed" />

<Accordion title="智能横幅是否能根据应用在用户设备上的激活状态来展示不同内容？">

不能。如果您不知道用户是否已安装您的应用，建议您选择对新老用户都适用的CTA，使用场景示例:如“进入应用”或“打开应用”。

</Accordion>

<div id="do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page" />

<Accordion title="如果用户离开横幅落地页后重新返回，这时智能横幅URL是否能保留初始的入链URL参数呢？">

区分。如果最初的入链URL包含utm\_source或pid参数，那么这条初始URL在用户的整个浏览过程中都会被保存下来，其参数会被提取到横幅的出链。

</Accordion>

<div id="can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app" />

<Accordion title="是否能将横幅设置为在移动端网页中展示，但不在嵌套/混合型应用中展示？">

区分。如果您在嵌套/混合型应用中接入智能横幅，并在应用中（而非网页浏览器中）加载横幅页面时，请勿使用[showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=)函数，因为该函数会在应用中展示横幅。在这类场景中，您需要使用<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#hidebanner">hideBanner</Anchor>函数。

</Accordion>

<div id="do-smart-banners-support-web-accessibility" />

<Accordion title="智能横幅支持无障碍访问吗？">

我们致力于保障您的所有用户，包括残障人士，都可以访问智能横幅中的全部内容并与其互动。

因此我们在智能横幅元素中添加了相关的HTML属性，尽全力实现智能横幅的无障碍访问支持，并符合WCAG 2.1（《网页内容无障碍准则）标准最佳实践的要求。

但您必须自行判断使用这类智能横幅时需要满足的无障碍访问要求。您需要全权确保您使用的智能横幅在生效期间遵照相关的网页无障碍访问要求，对所有用户都保持无障碍支持。

请注意：对智能横幅做各种修改时可能会影响其与相关无障碍要求的一致性，这类修改包括横幅内部元素的颜色和大小变更。

</Accordion>

<div id="if-a-smart-banner-is-deleted-from-a-banner-group-will-the-data-associated-with-that-banner-group-also-be-removed" />

<Accordion title="如果从横幅组中删除智能横幅，与该横幅组相关的数据是否也会被删除？">

不会。如果删除智能横幅，归因数据不会被删除。

</Accordion>

<div id="troubleshooting--traits-and-limitations" />

## 问题排查 & 特点和局限性

| 特点 | 说明 |
| --- | --- |
| 横幅展示拆分 | AppsFlyer会将在投横幅平均分配到符合条件的用户，无法选择哪个横幅展示更多，哪个横幅展示更少。比如，如果一组中有两个横幅，那么这两个横幅就会分别展示给50%的用户，而不能拆分成70%-30%的展示比例。 |
| 自定义参数 | • 自定义参数中不能使用下列特殊字符：;、*、!、@、#、?、$、^、:、&、~、\`、=、+、’、>、&lt;、/• 如果您在配置参数时使用了这些特殊字符，该参数不会被保存。 |
| 名称变更 | 您可以更改横幅组和横幅的名称。相关的效果数据会流转到新名称下，因此没有影响。 |
| 按钮点击/关闭次数 | 不支持衡量点击横幅但随后关闭横幅的用户数。 |
| 指定页面 | 将横幅组设置为在指定页面中展示横幅时，横幅规则仅对您输入的服务器/路径生效。如果没有完全匹配的结果（比如说您的网页中带有规则设置范围以外的其他字符串），则规则不生效。 |
| 平板设备 | • 智能横幅是专为移动端设备设计的产品，其分辨率对于屏幕尺寸较大的平板设备来说可能不是最理想的。• 平板设备上的浏览器可能会被识别为PC端。 |
| 横幅周围出现空白 | 出现这类问题时，请通过以下方式检查其成因：<ul><li>检查SDK代码片段是否在该网页中多次部署</li><li>确保<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">`showBanner`</Anchor>函数没有被多次调用</li></ul> |

<div data-zendesk-anchors="h_01HB5W700P3GP7JS4PFDF65EWT=%E6%B3%A8%E6%84%8F smart-banners=%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85 h_01HB5W700PWY5G45BYNWPKAC52=%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85 h_01HB5W700QQMYSEFBBXVJ97M0M=%E7%A4%BA%E4%BE%8B h_01HB5W700QGWTWDXBNB2GAPQ3B=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA setup=%E8%AE%BE%E7%BD%AE h_01HB5W700QVNYJT48VAP9Y7HQS=%E8%AE%BE%E7%BD%AE h_01HB5W700Q7G5E98V0DBN9P5VZ=1-website-workplace-setup prepare-your-mobile-site-to-display-smart-banners-for-the-first-time=%E9%A6%96%E6%AC%A1%E5%9C%A8%E7%A7%BB%E5%8A%A8%E7%AB%AF%E7%BD%91%E7%AB%99%E4%B8%AD%E6%8A%95%E6%94%BE%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85%E5%89%8D%E6%82%A8%E9%9C%80%E8%A6%81%E5%85%88%E5%AE%8C%E6%88%90%E4%BB%A5%E4%B8%8B%E5%87%86%E5%A4%87%E5%B7%A5%E4%BD%9C h_01HB5W700QE7MDBSN5GH4E7ABR=%E9%A6%96%E6%AC%A1%E5%9C%A8%E7%A7%BB%E5%8A%A8%E7%AB%AF%E7%BD%91%E7%AB%99%E4%B8%AD%E6%8A%95%E6%94%BE%E6%99%BA%E8%83%BD%E6%A8%AA%E5%B9%85%E5%89%8D%E6%82%A8%E9%9C%80%E8%A6%81%E5%85%88%E5%AE%8C%E6%88%90%E4%BB%A5%E4%B8%8B%E5%87%86%E5%A4%87%E5%B7%A5%E4%BD%9C to-create-website-workplaces-after-the-first-time=%E5%90%8E%E7%BB%AD%E5%88%9B%E5%BB%BA%E7%BD%91%E7%AB%99%E9%85%8D%E7%BD%AE%E4%B8%AD%E5%BF%83%E7%9A%84%E6%96%B9%E5%BC%8F h_01HB5W700Q57WXKFSWXNF22QZ1=%E5%90%8E%E7%BB%AD%E5%88%9B%E5%BB%BA%E7%BD%91%E7%AB%99%E9%85%8D%E7%BD%AE%E4%B8%AD%E5%BF%83%E7%9A%84%E6%96%B9%E5%BC%8F h_01HB5W700QY1FH2SYX6DM4HDEQ=2-banner-group-setup h_01HDH1BQSXCQV9QCJGZ4VNXGPQ=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA-1 h_01HB5W700QYJ9NR5F4VT59NG2Q=%E7%A4%BA%E4%BE%8B-1 targeting-behavior=%E5%AE%9A%E5%90%91%E4%B8%8E%E8%A1%8C%E4%B8%BA h_01HB5W700QYC48YTJY9B8JT0XM=%E5%AE%9A%E5%90%91%E4%B8%8E%E8%A1%8C%E4%B8%BA h_01HB5W700QG54YYQFHGA2J41RY=3-banner-setup h_01HB5W700QD0WKNAP5X6T9E6DQ=%E7%A4%BA%E4%BE%8B-2 h_01HB5W700QX5J59BBK1AV7VFV6=4-testing view-banner-performance=%E8%80%83%E5%AF%9F%E6%A8%AA%E5%B9%85%E6%95%88%E6%9E%9C h_01HB5W700Q6WHMVFNSVM2E9JXN=%E8%80%83%E5%AF%9F%E6%A8%AA%E5%B9%85%E6%95%88%E6%9E%9C h_01HB5W700QEP46WV78KEYD1RT1=performance-page h_01HB5W700QZ705H5EE0PFHB1KY=performance-cards additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HB5W700Q9XD8MGEK0B3ZZJS3=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HB5W700QHW078W3RRCB81AWM=banner-group-display-logic h_01HB5W700QNYT482FR0FRHP2DC=ab-testing-banner-performance faq=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HB5W700Q90F1KMASF94EZWEM=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HB5W700Q1ZP3RAR94T41SXK2=why-does-my-banner-not-display h_01HB5W700QKBVFQHH9D8WD36R2=can-i-use-my-own-font-for-my-banner h_01HB5W700R2AJC2C1PRT5PTH8G=can-i-add-parameters-to-the-url-of-my-smart-banners h_01HB5W700RAVG10QZDBPXWT14G=do-smart-banners-support-deep-linking h_01HB5W700R12DSA6HF4HVWGW9P=can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed h_01HB5W700RT122T2M6NXFPSXDV=do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page h_01HB5W700RH40FGHWVJ9J31R9F=can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app h_01HB5W700R11SHAKV5W21MXCX8=do-smart-banners-support-web-accessibility h_01JSVH17EH97S8B7EBCD4QHS1Q=if-a-smart-banner-is-deleted-from-a-banner-group-will-the-data-associated-with-that-banner-group-also-be-removed traits-and-limitations=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5--%E7%89%B9%E7%82%B9%E5%92%8C%E5%B1%80%E9%99%90%E6%80%A7 h_01HB5W700RXHC22QGXDX4GG1AR=%E9%97%AE%E9%A2%98%E6%8E%92%E6%9F%A5--%E7%89%B9%E7%82%B9%E5%92%8C%E5%B1%80%E9%99%90%E6%80%A7" />

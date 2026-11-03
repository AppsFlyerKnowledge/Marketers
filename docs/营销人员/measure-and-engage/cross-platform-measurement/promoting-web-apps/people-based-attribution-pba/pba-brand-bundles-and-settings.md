---
title: PBA品牌套件设置
metadata:
  keywords:
    - Advertisers
    - Bundles
    - Web Attribution
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
  created_at: '2018-12-09T11:42:52Z'
  edited_at: '2026-10-14T10:10:54Z'
  id: 360000646498
  locale: zh-cn
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000646498
---
> **概要：** 品牌套件可用于整合特定品牌下多个应用和网站的转化归因、事件、访问量和收入数据。您可以通过品牌套件的配置页面标记转化事件、对接Google Ads或实现其他功能。

![BrandBundles.png](https://files.readme.io/eab9447f0bdd225ab7915724f996555057fa7f2840ec6e69a89465a90af6181e-360017356617.png)

## 关于品牌套件

品牌通常在网页和移动端资源共同组成的生态环境内运营。因此，广告主需要了解品牌在网页与移动平台上的整体表现。在PBA中，品牌套件可将移动端与网页属性的数据整合为统一实体，以便广告主进原始数据分析和处理。

> 📘 **什么是网页应用？**
>
> 网页应用是您在AppsFlyer中创建的一个实体，您可以通过这个实体衡量某一网站的表现。
>
> * AppsFlyer在2022年2月9日添加了网页应用实体功能。在此日期之前，创建品牌套件时需单独设置品牌套件的域名。现在，您可以先为该域名创建网页应用，然后在创建品牌套件时，将该网页应用加入套件。
> * 如果您在2022年2月9日前已创建了品牌套件，您可以在**我的应用**页面中看到每个套件对应的网页应用。**请放心**，您的网页流量仍可正常归因，PBA面板和原始数据报告也未发生任何变化。

**品牌套件基本说明：**

* 每个品牌套件必须包含1个网页应用*（必需）*，以及1个或多个移动应用*（可选）*。
* 每个应用（无论网页或移动）只能归属于1个套件。
* 您无法从一个套件中移除应用或将其转移至另一个套件，除非将原套件删除。
  * 删除品牌套件后，AppsFlyer将停止为该套件归因PBA数据，历史数据也将无法访问。

## 访问品牌套件

您可以通过以下路径进入**品牌套件**页面，以管理套件及其相关设置：

* 从AppsFlyer后台的顶部菜单栏中选**我的应用 >** **查看品牌套件**。  
                           或
* 在AppsFlyer后台的侧边栏中选择**设置**> **品牌套件。**

## 管理品牌套件

如需在**品牌套件**页面添加、删除或管理品牌套件：

| 操作 | 说明 |
| --- | --- |
| 添加品牌套件 | 打开**创建套件**页面  <br />请按照[提示](/docs/pba-brand-bundles-and-settings#add-brand-bundle)创建新套件。 |
| PBA面板 | 打开品牌仪表板 |
| 品牌套件ID | 将品牌套件ID复制到剪贴板 |
| 网页开发者密钥 | 将网页开发密钥复制到剪贴板 |
| 选择已有套件以更新设置 | 可用操作包括：<ul><li>将事件标记为转化事件：<ul><li>[网页事件设置](/docs/pba-brand-bundles-and-settings#web-event-settings)</li><li>[应用内事件设置](/docs/pba-brand-bundles-and-settings#inapp-event-settings)</li></ul></li><li>[域名排除](/docs/pba-brand-bundles-and-settings#domain-exclusion)</li><li><Anchor target="_blank" href="/marketers/zh/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Google Ads对接</Anchor></li></ul> |
| 删除图标 | [删除所选品牌套件](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle)（需确认操作） |

<div id="add-brand-bundle" />

<Accordion title="添加品牌套件">

在创建品牌套件前，请确保您已将所有相关应用添加到了账户中。一旦完成创建，您将无法修改其中包含的应用，除非删除该套件并重新创建。

**添加品牌套件：**

1. 在[品牌套件](/docs/pba-brand-bundles-and-settings#访问品牌套件)页面，点击**添加品牌套件。**
2. 输入**品牌套件名称**（用于标识该套件的任意名称）。
3. 选择套件中包含的应用：

   **请注意：** 您无法选择其他套件中包含的应用。

   * 网页应用*[必填]*：选择1个可用的网页应用。
   * 移动应用*[可选]：*选择套件中包含的可用移动应用。
     * 移动应用不是创建套件时的必选项。
     * 您可以在套件中可添加任意数量的移动应用，无数量限制。
4. 点击创建套件。

> 🚧 **重要提示！**
>
> 在以下情况下将无法创建品牌套件：
>
> * 所选网页应用指向的不是有效URL；
> * 所选网页应用与某个Android移动应用的App ID相同。

</Accordion>

<div id="web-event-settings" />

<Accordion title="网页事件设置">

网页事件分为两类：**标准事件**和**转化事件**。为了优化资源投入，可将部分重要事件设为转化事件。

* 在PBA中，标准事件与转化事件的归因方式相同；
* <Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">原始数据</Anchor>报告包含标准事件和转化事件。
* PBA面板仅展示转化事件；
* 事件类型可随时更改，更改不会应用于历史数据。

**设置转化事件：**

1. 在[品牌套件](/docs/pba-brand-bundles-and-settings#访问品牌套件)页面中，选择品牌套件。  
   系统打开**更新品牌套件**页面。
2. 进入**网页事件设置**选项卡。
3. 根据需要开启**标记为转化事件**。
4. 点击**更新套件**。

</Accordion>

<div id="inapp-event-settings" />

<Accordion title="应用内事件设置">

默认情况下，带有收入的应用内事件会自动被标记为转化事件。**注意：** 如果您修改了默认事件配置，则必须手动将所有收入事件标记为转化事件。

**设置方法如下：**

1. 在[品牌套件](/docs/pba-brand-bundles-and-settings#访问品牌套件)页面中，选择品牌套件。  
   系统打开**更新品牌套件**页面。
2. 进入**应用内事件设置**选项卡。
3. 根据需要开启**标记为转化事件**。
4. 点击**更新套件**。

</Accordion>

<div id="domain-exclusion" />

<Accordion title="域名排除">

域名排除功能是<Anchor target="_blank" href="/marketers/zh/docs/pba-media-source-attribution-rules">PBA媒体渠道归因规则</Anchor>的重要组成部分，可用于避免以下情况：

* 自归因：也就是说，AppsFlyer不会将事件归因到网页应用中定义的网站本身，或是您指定为相关联网站的域名；
* 避免将与用户路径相关、但并不属于您品牌的域名（例如支付平台）所产生的事件进行归因或记录。

| 域类型 | 说明 | 排除后的影响 |
| --- | --- | --- |
| 主要 | 品牌套件中**网页应用**所属域名（包括子域名）。<br /><br />例如，若主域名是mydomain.co.za，则a.mydomain.co.za、b.mydomain.co.za等子域名会被自动排除。<br /><br />网页应用的域名不可更改，需[删除](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle)并重建网页应用及其所在的品牌套件。 | 避免自归因 |
| 内部域名 | 与品牌相关的其他域名，例如mydomain.com、mydomain.in、mydomain.co.ng、abc.com | 避免自归因 |
| 外部域名（由您列出） | 虽由您的网站调用，但不属于品牌自身的域名，例如支付平台或结算网站。 | <Anchor target="_blank" href="/marketers/zh/docs/pba-media-source-attribution-rules#visit-recognition-rules">访问被忽略</Anchor> |
| 外部域名（由AppsFlyer列出） | AppsFlyer默认排除的域名，包括：<ul><li>PayPal</li><li>Stripe</li><li>Adyen</li></ul>该列表不可编辑。 | <Anchor target="_blank" href="/marketers/zh/docs/pba-media-source-attribution-rules#visit-recognition-rules">访问被忽略</Anchor> |

**如需添加内部或外部域名进行排除：**

1. 在[品牌套件](/docs/pba-brand-bundles-and-settings#访问品牌套件)页面中，选择品牌套件。  
   系统打开**更新品牌套件**页面。
2. 进入**域名排除**选项卡。
3. 点击**添加域名。**
4. 输入域名。
5. 选择域名类型：**内部**或**外部。**
6. 点击**添加域名。**  
   排除规则将在1小时内生效。

</Accordion>

## 常见问题解答

<div id="can-i-include-the-same-app-in-more-than-one-bundle" />

<Accordion title="我可以将同一个应用添加到多个品牌套件中吗？">

<strong>不可以。</strong>应用一旦被添加到某个品牌套件中，就无法再添加到其他套件中。

</Accordion>

<div id="can-i-add-or-remove-apps-after-creating-a-bundle" />

<Accordion title="创建品牌套件后还能新增或移除应用吗？">

<strong>不可以。</strong>品牌套件一经创建，其中包含的应用将无法更改。

<strong>原因是什么？</strong>每个应用都有其独立的数据，AppsFlyer正是利用这些数据来分析用户在网页与App之间的完整旅程。如果替换了应用，所涉及的数据也将发生变化，无法与之前的数据兼容。

</Accordion>

<div id="how-do-i-add-or-remove-delete-apps-from-a-bundle" />

<Accordion title="那我该如何添加或移除套件中的应用？">

如需变更某个品牌套件中的应用，您需要先删除原有套件，然后重新创建一个包含所需应用的新套件。

</Accordion>

<div id="what-happens-if-i-delete-a-bundle" />

<Accordion title="删除品牌套件后会发生什么？">

#### 删除品牌套件后会发生什么？

如果您删除了某个品牌套件：

* AppsFlyer将停止对该套件的数据归因；
* 套件相关的数据会被保留（即不会永久删除），但该套件无法恢复，也无法再查看其数据。

  <strong>原因是什么？</strong>新的品牌套件会使用不同的网页开发密钥（web dev key），即便包含相同应用，也会被视为全新的套件，无法还原原有套件的结构或数据访问权限。

</Accordion>

<div id="why-are-certain-apps-not-available-for-me-to-add-to-a-bundle" />

<Accordion title="为什么我无法将某些应用添加到品牌套件中？">

* **如果您是管理员：** 请确保该应用已添加到您的AppsFlyer账户中，且未被其他品牌套件包含。
* **如果您是其他角色的用户：** 请联系账户管理员，确认您是否拥有访问并添加相关应用的权限。

</Accordion>

<div id="page-404" />

<Accordion title="为什么我在创建或查看品牌套件时看到“We couldn't find that Page”（找不到页面）的错误提示？">

您可能尚未订阅PBA服务。请联系您的客户成功经理或发送邮件至 [hello@appsflyer.com](mailto:hello@appsflyer.com)以升级套餐。

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/onboarding-guide-to-people-based-attribution">PBA入门指南</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/people-based-attribution-pba-overview">PBA启用流畅</Anchor>

<div data-zendesk-anchors="about-brand-bundles=%E5%85%B3%E4%BA%8E%E5%93%81%E7%89%8C%E5%A5%97%E4%BB%B6 h_01HE0Y2A3A5W86YY44RWCTKM1Y=%E5%85%B3%E4%BA%8E%E5%93%81%E7%89%8C%E5%A5%97%E4%BB%B6 h_01HE0Y2A3AYAFFSPRSH2BQ00Z3=%E4%BB%80%E4%B9%88%E6%98%AF%E7%BD%91%E9%A1%B5%E5%BA%94%E7%94%A8 accessing-brand-bundles=%E8%AE%BF%E9%97%AE%E5%93%81%E7%89%8C%E5%A5%97%E4%BB%B6 h_01HE0Y2A3A7265NYM7GVBZVXEN=%E8%AE%BF%E9%97%AE%E5%93%81%E7%89%8C%E5%A5%97%E4%BB%B6 managing-brand-bundles=%E7%AE%A1%E7%90%86%E5%93%81%E7%89%8C%E5%A5%97%E4%BB%B6 h_01HE0Y2A3A272QJ4ZQH7VXJWCC=%E7%AE%A1%E7%90%86%E5%93%81%E7%89%8C%E5%A5%97%E4%BB%B6 h_01HE0Y2A3ATX4ZDYZSRQGSJ4G7=add-brand-bundle h_01HE0Y2A3AQC5MMNQA0AV34MZ3=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01HE0Y2A3ATN6DEQ2KHCGT6VPQ=web-event-settings h_01HE0Y2A3A76VBZ17W4P1D0K2A=inapp-event-settings h_01HE0Y2A3A7F2YEW2SK0PSXXE4=domain-exclusion faq=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HE0Y2A3AB24NCNPAYFC0J4YH=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HE0Y2A3A5E816CYG2TMZ37DA=can-i-include-the-same-app-in-more-than-one-bundle h_01HE0Y2A3BENKY1AM51VM76TVS=can-i-add-or-remove-apps-after-creating-a-bundle h_01HE0Y2A3BK4JKMTND0JFCB179=how-do-i-add-or-remove-delete-apps-from-a-bundle h_01HE0Y2A3BKJTQZJXV49X32N1E=what-happens-if-i-delete-a-bundle faqs-what-happens-if-i-delete-a-bundle=%E5%88%A0%E9%99%A4%E5%93%81%E7%89%8C%E5%A5%97%E4%BB%B6%E5%90%8E%E4%BC%9A%E5%8F%91%E7%94%9F%E4%BB%80%E4%B9%88 h_01HE0Y2A3B276FV92EYBCZRA6C=%E5%88%A0%E9%99%A4%E5%93%81%E7%89%8C%E5%A5%97%E4%BB%B6%E5%90%8E%E4%BC%9A%E5%8F%91%E7%94%9F%E4%BB%80%E4%B9%88 h_01HE0Y2A3BEB2JG8CPSX3DA1V9=why-are-certain-apps-not-available-for-me-to-add-to-a-bundle h_01JTQF9DZZZ5JFN43Y5KJJV943=page-404 h_01HE0Y2KTXS06WHN57MQ91AD09=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

---
title: 市场人员专用的智能横幅网页代码添加指南
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developer
    - Developers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-10T11:25:54Z'
  edited_at: '2026-10-14T10:07:37Z'
  id: 4416119954705
  locale: zh-cn
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/zh-cn/articles/4416119954705
---
> **概要：** 概要：本文讲解了如何将智能横幅代码添加到您的网站中，从而将网站流量转化为移动应用的用户。

<div id="note" />

> 📘 **注意**
>
> AppsFlyer智能横幅网页SDK v1已于2023年11月8日下线。如需在您的网站中展示智能横幅，请升级到v2。<Anchor target="_blank" href="/marketers/zh/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">详情请见此处说明。</Anchor>

<div id="website-code-implementation" />

## 网页代码添加方式

本文旨在帮助市场人员通过以下方式在其网站中添加智能横幅代码：

* Google Tag Manager（GTM）
* Adobe Launch Tag Manager
* Shopify
* Wix
* Squarespace
* WordPress

如需通过其他平台在网站中添加代码，或根据具体需求修改代码（包括添加参数、深度链接、隐藏横幅或结合PBA使用智能横幅等），请参考<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">开发人员专用的智能横幅网页代码添加指南</Anchor>。

**请按以下步骤在您的网站中添加智能横幅代码**：

1. 按照<Anchor target="_blank" href="/marketers/zh/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup">网站配置中心指南</Anchor>获取智能横幅代码。
2. 请参考以下各个分平台指南，按所述步骤将代码添加到您的网站中：

<div id="google-tag-manager" />

<Accordion title="Google Tag Manager">

**请按以下步骤通过Google Tag Manager添加代码**：

1. 在GTM中，创建一个新标签。
2. 为标签命名，点击**Tag Configuration**并选择**Custom HTML**。
3. 将智能横幅代码片段粘贴到HTML字段框中。请将代码片段中的YOUR-BANNER-KEY改成您实际使用的横幅密钥。
4. 点击**Triggering**并点击右上角的加号创建一个新的trigger。
5. 为该trigger（触发条件）命名，然后在**Trigger Configuration**下选择**Page View**。
6. 如果您想要在所有页面展示横幅，请选择**All Page Views**。如果您想要在选定页面上展示横幅，请选择**Some Page Views**，并定义触发这个tag（标签）的条件。关于trigger的详细信息请见<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">GTM的trigger说明文档</Anchor>。
8. 返回tag配置页面。确认所有内容都已配置完毕，然后点击右上角的**Save**进行保存。
9. 发布您的GTM container。

</Accordion>

<div id="adobe-launch-tag-manager" />

<Accordion title="Adobe Launch Tag Manager">

**请按以下步骤通过Adobe Launch Tag Manager添加代码**：

<div id="step-1-create-a-property-in-adobe-experience-cloud" />

<Accordion title="第1步：第1步：在Adobe Experience Cloud后台创建一个Property（即标签）。">

**请按以下步骤创建property（标签），用于托管智能横幅代码**：

1. 进入**Adobe Experience Cloud** > **Launch**。
2. 点击**Adobe Experience Cloud Launch**下的**Go to Launch**。
3. 点击**New Property**。
4. 为您的property命名。
5. 选择**Platform**下的**Web**。
6. 输入您的网站域名。
7. 点击**保存**。

</Accordion>

<div id="step-2-add-smart-banners-code-to-the-adobe-launch-property" />

<Accordion title="第2步：第2步：将智能横幅代码添加到Adobe Launch property中">

**请按以下步骤在标签中添加智能横幅代码**：

1. 在**My web property**页面中，选择**Rules**选项卡。
2. 为该规则命名。建议：AppsFlyer智能横幅
3. 在**If**部分，点击**Events**下的 **+Add**。
   * 在**Event Type**下选择**Core - DOM Ready**。
   * 点击**Keep Changes**。
4. 在**Then**部分，点击**Actions**下的 **+Add**。
   * 在**Action Type**下，进入**Custom Code**。
   * 选择**JavaScript** > **Open Editor**，将**不带&lt;script>标签**的智能横幅SDK代码片段粘贴到编辑器中。
   * 点击**Keep Changes**，关闭代码编辑器。
5. 点击**保存**。

</Accordion>

<div id="step-3-add-the-adobe-launch-tag-to-your-website" />

<Accordion title="第3步：第3步：将Adobe Launch标签添加到您的网站中">

**请按以下步骤将Adobe Launch标签添加到您的网站（即加载智能横幅代码的网站）**：

1. 在**My web property**页面中选择**Environments**选项卡。
2. 找到您想要发布的环境（Development或Production）所在的那一行。
   * 在**激活**标头下，点击相关行的方框图标；通常是Production环境。
   * 有关发布**Adobe Launch**环境的详细信息，请见下一小节内容。
3. 在**Web Install Instructions**对话框中执行以下操作：
   * 复制脚本代码片段。
   * 关闭对话框。
4. 将代码片段粘贴到网站的&lt;head>标贴中。

</Accordion>

<div id="step-4-publish-the-adobe-launch-environment" />

<Accordion title="第4步：第4步：发布Adobe Launch环境">

**请按以下步骤发布相关环境，以激活Adobe Launch标签**：

1. 从**My web property**进入**Publishing**选项卡。
2. 在**Development**部分下点击**Add New Library**。
   1. 为该Library命名并选择一个环境。
   2. 在**Resource Changes**下，点击**Add a Resource**。
   3. 点击**Rules** > **Load Smart Banners** > **Latest** > **Select & Create a New Revision**。
   4. 点击**保存**。
3. 在**Development**部分下执行以下操作：
   1. 点击新创建的library旁边的操作菜单（以3个点表示），并选择**Build for Development**。
   2. 再次点击操作菜单，并选择**Submit for Approval**。
4. 在**Submitted**部分下执行以下操作：
   1. 点击操作菜单并选择**Build for Staging**。
   2. 再次点击操作菜单并选择**Approve for Publishing**。
5. 在**Approved**部分下，点击操作菜单并选择**Build & Publish to Production**。  
   至此，该流程操作完毕。

</Accordion>

接下来，当您在移动设备上打开您的网站时，网页就会展示横幅的活跃素材。如果您想要在指定页面中显示横幅，或通过特定的用户行为触发横幅，请参考<Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Adobe Launch规则。</Anchor>

</Accordion>

<div id="shopify" />

<Accordion title="Shopify">

**请按以下步骤在您的Shopify网站中添加智能横幅代码**：

1. 从Shopify后台进入**Sales Channels** > **Online Store** > **Themes**。  
   界面会显示当前主题。
2. 点击**Actions** > **Edit code**。  
   打开当前主题的代码编辑页面。
3. 在Layout文件夹中，点击以 **theme**开头的文件。  
   界面显示网页代码。
4. 将智能横幅代码粘贴到在代码正下方的 **&lt;head>** 下。

</Accordion>

<div id="wix" />

<Accordion title="Wix">

**请按以下步骤将智能横幅代码添加到您的Wix网站中**：

1. 进入您的Wix面板，点击Settings。
2. 在“Settings”页面的“Advanced”部分中，点击Custom code。
3. 点击+ Add Custom Code。
4. 将智能横幅代码粘贴到Paste the code snippet here方框中。
5. 建议：AppsFlyer智能横幅
6. 在**Add Code to Pages**部分，选择横幅展示页面。您可以使用以下任一方式：
   * All pages（所有页面）
   * Choose specific pages（选择特定页面）
7. 点击**启用**。  
   正常情况下，“Custom Code”页面会显示您的代码。请确保代码位于**Head**部分。

</Accordion>

<div id="squarespace" />

<Accordion title="Squarespace">

**请按以下步骤在您的Squarespace网站中添加智能横幅代码**：

1. 进入您的Squarespace面板，点击Website。
2. 点击Settings。
3. 点击Advanced。
4. 点击Code Injection。
5. 将智能横幅代码粘贴到Header中。
6. 点击**Save**保存。

</Accordion>

<div id="wordpress" />

<Accordion title="WordPress">

**请按以下步骤在您的WordPress网站中添加智能横幅代码**：

1. 进入您的WordPress面板，点击Appearance > **Theme Editor**。  
   **打开Edit Themes页面，页面中会显示您网站的CSS代码。**
2. 在Theme Files下，点击**Theme Header (header.php)**。
3. 界面显示代码，将智能横幅代码粘贴到代码中的&lt;head>下方。
4. 点击Update File。

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/pba-web-sdk-integration-guide#installation-and-integration">结合PBA使用智能横幅</Anchor>

<div data-zendesk-anchors="h_01HBT97B1ZGKKTD0TN2J2W56ZQ=%E6%B3%A8%E6%84%8F website-code-implementation=%E7%BD%91%E9%A1%B5%E4%BB%A3%E7%A0%81%E6%B7%BB%E5%8A%A0%E6%96%B9%E5%BC%8F h_01HBT97B1Z0F4B8E9GQWJEE6BH=%E7%BD%91%E9%A1%B5%E4%BB%A3%E7%A0%81%E6%B7%BB%E5%8A%A0%E6%96%B9%E5%BC%8F h_01HBT97B1ZKW36W9F0XQKM323P=google-tag-manager h_01HBT97B1ZX6VM1YER2HXTYQJ2=adobe-launch-tag-manager h_01HBT97B1ZPP0AKB5E31W36VC2=step-1-create-a-property-in-adobe-experience-cloud h_01HBT97B1ZK4T23MF4D6VGP4B8=step-2-add-smart-banners-code-to-the-adobe-launch-property h_01HBT97B1Z0W9VJ5FCW4605RDC=step-3-add-the-adobe-launch-tag-to-your-website h_01HBT97B1Z1W33DTT6NR4PQHQ0=step-4-publish-the-adobe-launch-environment h_01HBT97B1Z0NTYJKB2YFMX62P9=shopify h_01HBT97B1ZYVJ6PW7F811V5TAX=wix h_01HBT97B1ZS0FDM60M1GA04PRT=squarespace h_01HBT97B1ZKYB7XPGFG00PB2BT=wordpress h_01HE7SG3MJ4WTPMTXF0DA0M07D=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />

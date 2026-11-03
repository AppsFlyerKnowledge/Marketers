---
title: 二维码到应用的转化
metadata:
  keywords:
    - OneLink
    - Advertisers
    - owned media
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2020-11-04T09:49:23Z'
  edited_at: '2026-10-14T10:08:19Z'
  id: 360015119718
  locale: zh-cn
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/zh-cn/articles/360015119718
---
> **概要：** 概要：通过OneLink生成二维码，用于引导PC端、电视、CTV或线下流量转化为移动端应用用户。

![6005_QR_code_4.jpg](https://files.readme.io/6db45d7e82bc33ba8af8c6e7d096011d71b06766da9df348dccfa1b3e4aa380d-12368835107601.jpg)

## 引导移动端、非移动端和线下流量转化为移动端应用用户

在投放到PC端、电视、CTV或线下的广告中发布通过OneLink生成的二维码，这类推广方式包括店内陈列、宣传手册、产品包装等，具有下列优势：

* 用户可迅速便捷地使用其移动设备扫描二维码，进而下载并安装您的应用。
* 用户无需手动进入应用商店并搜索您的应用，大幅提升二维码到应用的激活转化率。
* 这类转化避开了短信的使用，因此用户无需提供电话号码等个人信息，可保障用户的隐私安全。
* 便于您对激活进行归因，并衡量相关广告的有效性。

* [在AppsFlyer面板中手动创建](/docs/qr-to-app-conversion#二维码的手动设置方式)
* <Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#qr-codes">或使用OneLink智能脚本动态创建二维码</Anchor>（专为网页到应用的PC端链路所设计）

<div id="qr-to-app-conversion" />

<Accordion title="二维码到应用的转化">

#### 二维码的手动设置方式

**前期准备：**

* 确保您有一个AppsFlyer帐户，且账户中至少有一个应用。
* 如需归因： 确保您的所有应用中都<Anchor target="_blank" href="/marketers/zh/docs/integrate-the-appsflyer-sdk">已安装AppsFlyer SDK</Anchor>。
  * 如果您的应用中尚未安装SDK，仍可创建有效的跳转链接，但无法实现深度链接或延迟深度链接，也无法在面板中衡量激活情况。

* 设置一个<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">OneLink模板</Anchor>。

**对于二维码到应用的转化，请按以下方式设置二维码：**

1. 请完成以下**任一**操作：
   * <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#创建onelink链接">创建单个二维码图像</Anchor>
     1. 【推荐方式】创建一条新的链接，并为其设置自定义媒体渠道。如**desktop\_web**。您也可以使用现有链接的二维码。但为了便于数据上报，建议您不要与其他链接共享媒体渠道，而是使用单独的链接及其专属的媒体渠道。
     2. 点击**生成链接**后，界面会显示相应的二维码。
     3. 点击二维码即可下载SVG或PNG格式的二维码原图。
   * <Anchor target="_blank" href="/marketers/zh/docs/perform-onelink-bulk-actions-via-csv#downloading-a-collection-of-qr-codes">创建系列二维码</Anchor>
     1. 在**批量链接**页面中创建一个链接系列。
     2. 下载该系列链接的二维码。
2. 在您的广告中添加该二维码，与图片/内容的添加方式相同。
   * 请参考二维码的[最佳使用方式](/docs/qr-to-app-conversion#best-practices)。
   * 您可能需要开发人员协助您完成此步骤。

</Accordion>

<div id="customize-qr-code" />

<Accordion title="定制化二维码">

![OnelinkQRFinal__1_.gif](https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif)

您可以通过以下方式对OneLink生成的二维码进行定制：

* 在二维码中添加品牌标识
* 更改二维码的颜色

**请注意**：

* 您需要在OneLink模板中定制二维码，而不能在具体链接中操作，定制后的二维码会应用到模版下的所有链接中。
* 通过智能脚本创建的二维码无法进行自定义调整。

**请按以下步骤定制二维码**：

1. 从AppsFlyer面板进入**用户体验与深度链接** > **OneLink管理**。
2. 界面会打开二维码编辑器。
3. 输入您品牌logo图片的URL，如https://yourbrand.com/logo.png。  

   品牌logo图片须符合以下要求：

   * PNG或JPG格式
   * 透明背景的方形或圆形图像
   * 尺寸不能小于400 x 400 px
4. 设置二维码颜色。
5. 点击**保存**。

</Accordion>

<div id="measure-qrtoapp-conversions" />

<Accordion title="二维码到应用的转化衡量方式">

您可以通过展示量（PC端页面访问量）、点击量（二维码扫描次数）和应用激活量的对比分析来衡量相关二维码及其在不同广告/媒体渠道中的投放效果。

**请按以下方式衡量二维码到应用的转化**：

1. 您可以在AppsFlyer后台查看数据总览面板或使用其它AppsFlyer分析工具，并通过相关二维码的媒体渠道（如**desktop\_web**）来记录总体**点击量**和**激活量**。
2. 使用您的网页分析软件来记录总体PC端页面浏览量（展示）。
3. 衡量投放效果：
   * <Anchor target="_blank" href="/marketers/zh/docs/about-conversion-rates#marketing-funnel-stages-and-conversion-rates-1">点击至激活率</Anchor>
   * <Anchor target="_blank" href="/marketers/zh/docs/about-conversion-rates#marketing-funnel-stages-and-conversion-rates-1">点击到激活比率</Anchor>

</Accordion>

<div id="best-practices" />

<Accordion title="最佳实践">

下文的小贴士可帮助您充分提升二维码到应用的转化量。

* 对于PC端，如果您打算手动设置二维码，请在您的网站中创建一个单独的页面，用于展示该二维码。
  * 为相关页面选择一个URL slug（网址中最后一个反斜杠后的部分），如 **/app**、**/download-app**或 **/mobile-app**。
  * 将相关页面设置为仅在PC端/大屏宽度下可见。
* 对于所有广告：
  * 在您的广告中提供高清二维码大图，便于用户扫描。
  * 在广告中的显著位置添加**从App Store下载**和**从Google Play下载**按钮，作为视觉触发器（而非链接）。
  * 考虑添加二维码的扫描方式说明。
* 若您已经在使用OneLink，在您的*其它*OneLink自定义链接（如用于邮件等）中添加参数**af\_web\_dp**，并将参数值设为带有相关二维码的网页地址。这样，在PC端点击链接的用户就会跳转到该网页，而非应用商店。  

  [![](https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg)](https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg)

</Accordion>

<div data-zendesk-anchors="converting-mobile-nonmobile-and-offline-traffic-into-mobile-app-users=%E5%BC%95%E5%AF%BC%E7%A7%BB%E5%8A%A8%E7%AB%AF%E9%9D%9E%E7%A7%BB%E5%8A%A8%E7%AB%AF%E5%92%8C%E7%BA%BF%E4%B8%8B%E6%B5%81%E9%87%8F%E8%BD%AC%E5%8C%96%E4%B8%BA%E7%A7%BB%E5%8A%A8%E7%AB%AF%E5%BA%94%E7%94%A8%E7%94%A8%E6%88%B7 h_01HKWVMKP3QT59EXPHQEPHW8K9=%E5%BC%95%E5%AF%BC%E7%A7%BB%E5%8A%A8%E7%AB%AF%E9%9D%9E%E7%A7%BB%E5%8A%A8%E7%AB%AF%E5%92%8C%E7%BA%BF%E4%B8%8B%E6%B5%81%E9%87%8F%E8%BD%AC%E5%8C%96%E4%B8%BA%E7%A7%BB%E5%8A%A8%E7%AB%AF%E5%BA%94%E7%94%A8%E7%94%A8%E6%88%B7 h_01HKWWQXVC11E8M3NV3A03SWYD=qr-to-app-conversion manual-qr-code-setup=%E4%BA%8C%E7%BB%B4%E7%A0%81%E7%9A%84%E6%89%8B%E5%8A%A8%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01HKWWQXVCB96WDMBSE9WH9ZC5=%E4%BA%8C%E7%BB%B4%E7%A0%81%E7%9A%84%E6%89%8B%E5%8A%A8%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01HKWVMKP3R5C5FPH010ZJZAHS=customize-qr-code h_01HKWVMKP3XTF6NNPNM8J00NWD=measure-qrtoapp-conversions h_01HKWVMKP3P6FNRPP1X7ZTNH10=best-practices" />

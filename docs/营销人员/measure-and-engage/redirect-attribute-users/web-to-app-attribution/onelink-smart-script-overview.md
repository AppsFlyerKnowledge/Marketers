---
title: Onelink智能脚本简介
metadata:
  keywords:
    - OneLink
    - Adwords
    - Advertisers
    - referral
    - referal
    - landing
    - redirect
    - gclid
    - facebook
    - landing page
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
  created_at: '2018-12-12T16:32:47Z'
  edited_at: '2026-10-14T10:06:08Z'
  id: 360000677217
  locale: zh-cn
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000677217
---
> **概要：** 您可以使用OneLink智能脚本推动移动端网页用户转化为应用用户，并将其准确归因到对应的流量来源渠道。

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

<div id="about-onelink-smart-script" />

## OneLink智能脚本简介

用户通过自然或非自然（与广告互动）的方式从您的移动端网站进入应用商店的相关页面，这条链路中涉及到两个点击：

* 点击后进入网页
* 点击后从网页进入应用商店

在该场景中，归因和深度链接会出现问题——最终下载并激活应用的用户可能会被归因到自然量。如果最初的点击是由广告平台、Google或自有媒体带来的，那么这样的归因方式就会导致结果的偏差。

OneLink智能脚本可以通过以下方式解决上述问题：

* 通过链接到网页的入链动态生成专属的OneLink出链，让用户跳转到应用商店。
* 将移动端的网页到应用流量准确地归因到各种渠道，包括广告平台、SRN、Google点击以及自有媒体。
* 可用于深度链接。
* 可在任何网页或落地页中实现无缝衔接。
* 无需使用智能横幅。   
  **请注意**：智能横幅也是高效好用的转化工具，很适合某些垂类且无需开发人员进行设置，但需要在用户链路中增加横幅这一环节。
* 可以由市场人员在Google Tag Manager后台设置。

OneLink智能脚本有两个版本：

<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors">**OneLink智能脚本V2（推荐）**</Anchor>：如果您之前从未使用过OneLink智能脚本，建议您使用这个版本进行首次设置。您可以在AppsFlyer面板中配置智能脚本，减轻开发人员的工作量，也可以使用Google Tag Manager来设置脚本。

<Anchor target="_blank" href="/marketers/zh/docs/legacy-onelink-smart-script-v1-setup">**OneLink智能脚本V1（旧版）**</Anchor>：如果您已经有现成的OneLink智能脚本配置，请参照该版本的相关文档对脚本进行维护和编辑。 **请注意**：虽然AF不规定必须使用V2，但仍建议您迁移到V2。

<div id="note" />

> 📘 **注意**
>
> 建议您将OneLink智能脚本与其他的AppsFlyer网页到应用解决方案一一<Anchor target="_blank" href="/marketers/zh/docs/convert-your-mobile-web-visitors-to-app-users">对比</Anchor>，找出最适合您的解决方案。

<div id="examples" />

### 示例

本节中的示例说明了广告主应如何使用OneLink智能脚本来生成OneLink出链的URL，从而实现准确归因以及深度链接。另请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#使用场景">使用场景</Anchor>，了解在具体渠道上投放各类广告时如何使用智能脚本。

<div id="attribution" />

<Accordion title="归因">

Mark负责某家连锁酒店的市场营销，他向潜在用户发送了一封邮件，宣传位于佛罗里达州奥兰多的酒店度假套餐。该邮件中包含以下链接：https://hotel.me/pid=email&c=orlando

用户点击该链接后会跳转到酒店的移动端网站，并在网页中看到CTA按钮，吸引他们下载该酒店的移动端应用。OneLink智能脚本自动生成一条URL，其中包含与邮件中的原始链接相同的**pid**和**c**参数，具体链接如下：https://hotel.onelink.me/Ac4G?pid=email&c=orlando

用户点击网页中的按钮后下载应用，相应的激活会归因到Mark的奥兰多宣传邮件。

</Accordion>

<div id="deep-linking" />

<Accordion title="深度链接">

Emma收到奥兰多酒店度假项目的宣传邮件。

邮件中的链接如下：https://hotel.me?type=email&campaign=Florida&city=orlando

她点击该链接后，跳转到酒店的移动端网站。她在网站上看到吸引她下载该酒店应用的CTA按钮。OneLink智能脚本自动生成一条URL，其中包含与邮件中的原始链接相同的**pid**和**c**参数，具体链接如下：https://hotel.onelink.me/Ac4G?pid=email&c=Florida&deep_link_value=orlando

**Emma点击网站上的按钮后，跳转到应用商店。她下载并打开应用，然后通过深度链接进入应用中的奥兰多度假页面。**

<div id="note-1" />

> 📘 **注意**
>
> 要实现深度链接，还需要应用开发人员添加相应的应用设置。详情请见<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#创建onelink链接">此文档</Anchor>。

</Accordion>

<div data-zendesk-anchors="about-onelink-smart-script=onelink%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC%E7%AE%80%E4%BB%8B h_01HE7RW9G26CNME9TP350GFGS4=onelink%E6%99%BA%E8%83%BD%E8%84%9A%E6%9C%AC%E7%AE%80%E4%BB%8B h_01HE7RW9G2BV2NFJ0YZ9QKAA2V=%E6%B3%A8%E6%84%8F examples=%E7%A4%BA%E4%BE%8B h_01HE7RW9G2WBZ1A0RS66CJ7BNH=%E7%A4%BA%E4%BE%8B h_01HE7RW9G24Y604NTZFGKJJXSS=attribution h_01HE7RW9G2ZDDWE1M1B2G175ZF=deep-linking h_01HE7RW9G3W5GKQ2CD2BZW8YAW=%E6%B3%A8%E6%84%8F-1" />

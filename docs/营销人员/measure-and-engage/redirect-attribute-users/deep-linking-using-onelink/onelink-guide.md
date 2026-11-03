---
title: OneLink指南
metadata:
  keywords:
    - Marketers
    - start
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-10-19T08:53:16Z'
  edited_at: '2026-10-14T10:11:37Z'
  id: 115005248543
  locale: zh-cn
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/zh-cn/articles/115005248543
---
> **概要：** 您在AppsFlyer后台创建的OneLink链接可同时具备归因、跳转和深度链接功能，帮助您将自有和付费媒体的用户转化为应用用户，且不受设备、操作系统、流量入口和平台的限制。您可以在各种自有媒体中使用这些链接，无论是网站、横幅、社交媒体帖子、邮件还是短信文案，为用户带来最丝滑流畅的体验，从而推动他们的转化。

## 视频简介

<Embed title="YouTube视频播放器" typeOfEmbed="youtube" url="https://www.youtube.com/embed/golT4p9D8MA" providerUrl="https://www.youtube.com" />

## 优势

AppsFlyer的用户体验和深度链接产品套件以OneLink为核心技术，广告主使用该产品创建链接后就能衡量各大流量入口的移动营销效果。这些链接可以帮助广告主实现以下功能：

* 打通线上线下各类营销触点，与用户互动。
* 分营销触点为用户带来最佳场景化体验，提升从点击到激活的转化率。
* 对广告投放进行精确的归因和衡量。
* 让还未安装应用的潜在用户跳转到与其设备适配的应用商店或网页，不受设备、操作系统、流量入口或平台的限制。
* 为已经安装应用的现有用户吊起应用（通过App Link、Universal Link、和URI scheme实现）。
* 通过深度链接让用户进入应用内指定的页面或体验。

AppsFlyer将该产品套件免费提供给所有账户使用。

## 用户体验

AppsFlyer的用户体验和深度链接产品包以OneLink为核心技术，广告主使用该产品所创建的链接能够为各种来源的用户带来最佳的体验。该产品支持下列用户体验的配置：

* **社媒到应用**： 在社交媒体上吸引用户互动，将流量从社交媒体帖子引导到您的应用。
* **应用到应用**：将用户从其他应用引导到您的应用。
* <Anchor target="_blank" href="/marketers/zh/docs/convert-your-mobile-web-visitors-to-app-users">**网页到应用**</Anchor>：通过智能横幅（Smart Banner）和智能脚本（Smart Script）将移动端网页访客转化为应用用户。
* **二维码到应用**： 通过二维码推动拉新，让用户在线下体验过程的关键环节中扫描二维码。您也可以在PC端、电视或CTV广告中添加二维码，将用户引导到应用。
* **邮件到应用**：通过邮件服务商（ESP）向用户发送邮件，并将他们引导到应用。
* **短信到应用**：创建专用于短信和短消息营销的链接，通过文字消息与用户互动。
* **推荐到应用**：创建用户邀请链接，让用户以及博主邀请其他人使用您的应用或分享应用中的指定内容（如文章）。
* **自定义**：不论您的用户来自PC端还是移动端，线上还是线下，自有媒体还是付费媒体，OneLink都能按您的要求对其进行导流。

## 设置OneLink

如需使用AppsFlyer面板打造特定的用户体验，推动从点击到激活的转化，须具备以下条件：

* 需要广告主侧的市场和开发团队通力合作。
* <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">创建OneLink模板</Anchor>，奠定所有链接的核心导流逻辑，实现下列跳转行为：
  * 让未安装应用的潜在用户跳转到与其设备适配的应用商店或网址。
  * 通过App Link、Universal Link、或URI scheme让已经安装应用的现有用户进入应用。
    * 如果没有设定这些内容，则会默认沿用针对新用户的设置（即跳转到网页URL或应用商店）。**请注意**：OneLink模板不是终端用户可点击的链接，而是生成一组自定义链接的基础。您可以一个模板创建多条可点击的OneLink自定义链接。在应用程序的生命周期内（测试之外）很少需要一个或两个以上的OneLink模板。
* <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">创建OneLink链接</Anchor>。它会以链接或二维码的形式出现在您的广告中，供用户点击或扫描。在设置链接时，请按实际需求设定用户体验并添加参数。

下表详细说明了市场和开发分别需要完成的工作，并列出了对应的文档链接。

| 事项 | 说明 | 资料 |
| --- | --- | --- |
| 创建OneLink模板 | <ul><li>市场人员/产品经理在AppsFlyer后台设置模板。</li><li>安卓开发人员配置现有用户的应用打开方式（使用安卓App Lin和URI scheme）</li><li>iOS开发人员配置现有用户的应用打开方式（使用iOS Universal Link和URI scheme）。</li></ul> | <ul><li>AppsFlyer面板</li><li><Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">市场人员指南</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">安卓</Anchor>及<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup">iOS</Anchor>开发人员指南</li></ul> |
| 创建OneLink链接 | <ul><li>市场人员/产品经理在AppsFlyer后台设置链接，选择所需的用户体验并添加相关的归因或深度链接参数。</li><li>安卓和iOS开发人员在应用中写入深度链接的UDL方法（如需使用深度链接）。</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">市场人员指南</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_unified_deep_linking">安卓</Anchor>及<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_unified_deep_linking">iOS</Anchor>开发人员指南</li><li>应用示例（Github）</li></ul> |

## 其他选项

如果您已完成面板中的部分或所有设置，可以考虑使用下文所述的各种其他功能。

**请注意**：下列功能中除了OneLink API是高阶付费功能外，其他都已包含在AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/account-management-plans-payments-and-billing">Zero和Growth套餐</Anchor>中。

* <Anchor target="_blank" href="/marketers/zh/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor>以及<Anchor target="_blank" href="/marketers/zh/docs/perform-onelink-bulk-actions-via-csv">批量创建</Anchor>功能：您可以通过该功能快速创建数千个OneLink链接，同时进行投放，实现平铺扩量，大幅释放生产力，让您腾出时间和精力去优化投放和营销。
* <Anchor target="_blank" href="/marketers/zh/docs/export-onelink-urls">导出OneLink链接</Anchor>：您可以下载所有在AppsFlyer后台创建的链接（通过SDK、OneLink API或批量上传生成的OneLink链接除外）。
* <Anchor target="_blank" href="/marketers/zh/docs/measuring-push-notification-re-engagement-campaigns">衡量消息推送型再互动广告</Anchor>：您可以结合OneLink使用推送通知进行推广，衡量用户的再互动行为。
* <Anchor target="_blank" href="/marketers/zh/docs/cross-promotion-attribution-for-marketers">交叉推广归因</Anchor>：现有用户是您在推广新应用时的优质资源，他们是最有可能安装新应用的人群。 具体请查阅如何通过SDK方式创建并衡量交叉推广广告。
* <Anchor target="_blank" href="/marketers/zh/docs/understand-onelink-short-vs-long-urls">长链</Anchor>：您可以在OneLink自定义链接中添加参数，或通过简单的工作表公式生成大量OneLink自定义链接。
* <Anchor target="_blank" href="/marketers/zh/docs/redirect-app-users-to-a-website">实现从应用到网页的跳转</Anchor>：您可以让用户从您的应用中跳转到某个网站或社交媒体平台中的某个页面。

## 故障排查和FAQ

如果OneLink链接在测试和调试过程中出现跳转/功能问题，请参阅<Anchor target="_blank" href="/marketers/zh/docs/onelink-troubleshooting-and-faq">OneLink故障排查指南</Anchor>，快速找到解决方法。

## 局限性

* OneLink不适用于Meta中以移动应用激活为目标的广告投放，因为Meta ads只支持Meta App Link的跳转。

<div data-zendesk-anchors="introduction-video=%E8%A7%86%E9%A2%91%E7%AE%80%E4%BB%8B h_01HGE1D5JZ4Y603BD55W2P7DPW=%E8%A7%86%E9%A2%91%E7%AE%80%E4%BB%8B benefits=%E4%BC%98%E5%8A%BF h_01HGE1D5JZJGY8BZX8ZTSXQ635=%E4%BC%98%E5%8A%BF experiences=%E7%94%A8%E6%88%B7%E4%BD%93%E9%AA%8C h_01HGE1D5JZV65E9YWG424HYRNW=%E7%94%A8%E6%88%B7%E4%BD%93%E9%AA%8C setup=%E8%AE%BE%E7%BD%AEonelink h_01HGE1D5K0RKHHV9SVH4VREMXQ=%E8%AE%BE%E7%BD%AEonelink additional-options=%E5%85%B6%E4%BB%96%E9%80%89%E9%A1%B9 h_01HGE1D5K2VCKYJY3Y8MKYVT2V=%E5%85%B6%E4%BB%96%E9%80%89%E9%A1%B9 troubleshooting-and-faq=%E6%95%85%E9%9A%9C%E6%8E%92%E6%9F%A5%E5%92%8Cfaq h_01HGE1D5K24FG3F8G54DYTK599=%E6%95%85%E9%9A%9C%E6%8E%92%E6%9F%A5%E5%92%8Cfaq limitations=%E5%B1%80%E9%99%90%E6%80%A7 h_01HGE1D5K2M0VMJPMP4EJ0QGPY=%E5%B1%80%E9%99%90%E6%80%A7" />

---
title: 设置自然搜索归因
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-05-07T13:34:36Z'
  edited_at: '2026-10-14T10:12:44Z'
  id: 15123194526353
  locale: zh-cn
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/zh-cn/articles/15123194526353
---
> **概要：** 本文说明了如何针对已安装相关应用的用户，获取其再互动的自然搜索归因数据，帮助您优化自然搜索转化。

<div id="overview" />

## 概览

自然搜索归因（Organic search attribution）是一种新型的归因解决方案。使用AppsFlyer的广告主可以通过该方案将再互动（即已激活相关应用的用户再次打开应用）归因到各种自然搜索引擎。

这部分独特的数据能为SEO（搜索引擎优化）成效提供重要的反馈信息，因此非常有助于SEO团队的工作。

<div id="flow" />

#### 链路

![自然量](https://files.readme.io/4b33060cfa30a4e2786c4a3a213ca41223ae276d63c97ab7c2cb5a997a4b010c-16540659217809.png)

1. 用户在其移动端浏览器的搜索引擎（Google、Bing等等）中搜索某个关键词后，该搜索引擎显示了数条可点击的搜索结果。
2. 您的网页开发人员对部分搜索结果进行了映射配置，使其通过安卓的App Link或iOS的Universal Link吊起相关应用。如果用户已安装相关应用，则点击这些搜索结果时就会直接吊起应用（不会先跳转到应用商店）。
3. 应用打开时，AppsFlyer会收集必要的信息，并能够将此次应用打开归因到该用户使用的搜索引擎。
4. 对于未安装应用的用户，您可以使用AppsFlyer的网页到应用解决方案（包括智能横幅、智能脚本和二维码）将这些用户引导至落地页，为其实现跳转并进行归因。

<div id="note" />

<div id="setup" />

## 设置方式

**前期准备**：

* AppsFlyer Android SDK V6.12.1
* AppsFlyer iOS SDK V6.12.1

**请按以下方式设置自然搜索归因**：

1. 请让您的开发人员根据相应的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">安卓App Link</Anchor>和<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#app-opening-methods">iOS Universal Link</Anchor>指南（使用相关应用的顶级域名）实现应用吊起。
2. 从AppsFlyer后台的侧边栏中选择**配置** > <Anchor target="_blank" href="/marketers/zh/docs/app-settings">应用配置</Anchor>。然后启用：
   * **自然搜索（SEO）移动应用归因**。
   * **再互动归因**的开关。

> 📘 **开发人员的注意事项**
>
> 调用`performOnDeepLinking`会强制执行并解析深度链接URL，这会使SEO归因功能无法正常生效，导致相关转化无法归因到正确的SEO媒体渠道。

<div id="data-availability" />

## 数据可用性

数据可用性如下：

* 在面板和报告的汇总数据中，媒体渠道（media source）字段会显示带来相关用户的搜索引擎，比如：`google_organic_seo`。
* 原始数据报告中：
  * `media source`字段会显示带来相关用户的搜索引擎，比如：`google_organic_seo`。
  * `http_referrer`字段中包括搜索结果页面的完整URL，用户从该页面进入应用或跳转到移动端落地页。
  * `channel`字段的值为`seo`。

<div id="note-2" />

<div id="note-1" />

<div id="additional-information" />

## 其他相关信息

<div id="list-of-supported-search-engines" />

<Accordion title="使用搜索引擎列表">

自然搜索归因支持下列搜索引擎：

* Google
* Bing
* Yahoo
* Ask
* DuckDuckGo
* Yandex
* Naver
* Daum
* 百度
* Ecosia
* Coccoc
* 搜狗
* Yahoo Japan

**请注意**：

* 如需对其他搜索引擎进行归因，请使用<Anchor target="_blank" href="/marketers/zh/docs/legacy-set-up-organic-search-attribution">旧版自然搜索归因解决方案</Anchor>（需要开发人员介入）。
* 面板和报告以`<search engine>`\_organic\_seo的格式显示搜索引擎，例如：`google_organic_seo`。

</Accordion>

<div id="faq" />

<Accordion title="常见问题解答">

| <span id="q-does-organic-seo-attribution-incur-an-additional-fee-a-no-this-feature-is-included-in-your-subscription"></span>**问：使用自然SEO归因需要额外付费吗？**<br /><br />答：不需要，该功能已包含在您的套餐中。 |
| --- |
| <span id="q-do-organic-seo-conversions-count-as-part-of-my-package-a-yes-same-as-nonorganic-conversions"></span>**问：自然SEO转化会计入我的套餐使用量吗？**<br /><br />答：是的，这类转化在套餐使用量中的统计方式与非自然转化相同。 |
| <span id="q-can-i-customize-the-name-of-the-seo-media-source-a-no-the-name-of-the-organic-seo-media-source-is-determined-by-appsflyer-and-cant-be-customized-at-this-point"></span>**问：SEO媒体渠道的名称可以自行调整吗？**<br /><br />答：不可以，自然SEO媒体渠道的名称是由AppsFlyer设定的，目前尚不支持自定义。 |
| <span id="q-if-the-search-engine-displays-an-install-button-next-to-the-organic-search-results-and-the-user-clicks-it-and-navigates-to-the-app-store-does-appsflyer-attribute-the-install-to-the-search-engine-a-no-in-this-case-appsflyer-cant-collect-the-required-information-for-attribution-organic-search-attribution-requires-the-app-to-already-be-installed"></span>**问：如果相关搜索引擎在自然搜索结果旁边展示安装按钮，用户点击该按钮后进入应用商店，AppsFlyer能将后续激活归因到这个搜索引擎吗？**<br /><br />答：在上述场景中，AppsFlyer无法收集到必要的归因信息。自然搜索归因仅适用于已安装相关应用的用户。 |
| <span id="q-is-keyword-data-available-a-keyword-data-isnt-available-via-this-organic-search-attribution-solution-however-there-are-rare-instances-where-keyword-data-is-available-for-android-learn-more"></span>**问：关键词数据是否可用？**<br /><br />答：关键词数据无法通过自然搜索归因解决方案获取，但在极少数情况中可能会有可用的安卓关键词数据。<Anchor target="_blank" href="/marketers/zh/docs/evaluate-keyword-data#安卓关键词">详情请见此处说明。</Anchor> |
| <span id="q-is-organic-search-attribution-supported-in-an-install-flow-a-yes-you-can-learn-from-what-page-users-who-installed-your-app-arrived-at-your-website-smart-script-can-collect-this-page-url-domain-referred-to-as-the-web-referrer-and-map-it-as-a-value-to-a-parameter-key-of-your-choosing-in-the-outgoing-url-web-referrer-is-especially-useful-for-identifying-the-search-engine-that-guided-users-to-your-website-this-information-can-be-displayed-in-the-dashboard-and-raw-data-reports-under-the-appsflyer-parameter-key-you-selected-to-learn-how-to-set-the-smart-script-to-collect-the-web-referrer-see-here"></span>**问：激活链路中支持自然搜索归因吗？**<br /><br />答：是的，对于已安装您应用的用户，您可以了解他们从哪个页面进入了您的网站。智能脚本可以收集这个页面的URL域名（也称为Web Referrer），然后在生成的链接中将其映射为指定参数的值。<br /><br />Web Referrer尤其适用于识别引导用户到您网站的搜索引擎。面板和原始数据报告会在您指定的AppsFlyer参数下呈现该信息。<br /><br />如需进一步了解通过智能脚本收集Web Referrer的方式，请参考<Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors#web-referrer-mapping">此文档</Anchor>。 |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 浏览器 | 下列浏览器不支持自然搜索归因：<ul><li>安卓中的FireFox</li><li>iOS中除了Safari之外的所有浏览器</li></ul> |

</Accordion>

<div data-zendesk-anchors="organic-search-attribution=%E6%A6%82%E8%A7%88 h_01H9G0W21SRDC6ZSR1E8AQFZFC=%E6%A6%82%E8%A7%88 flow=%E9%93%BE%E8%B7%AF h_01H9G0W21S4RB56PNV9DAYZPB2=%E9%93%BE%E8%B7%AF setup=%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01H9G0W21S6Z0A5QXC52KSYVQS=%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F h_01HEHTAYMRTRW6AK946YZA54M8=%E5%BC%80%E5%8F%91%E4%BA%BA%E5%91%98%E7%9A%84%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 data-availability=%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01H9G0W21S7KVJ2Z5DRPCHZF4Z=%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7 additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01H9G0W21SERW2HC44KD77FNCG=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01H9G0W21SW5E938HEQGTYA9X3=list-of-supported-search-engines h_01H9G0W21TF08JW4FYVWV4K0CW=faq q-does-organic-seo-attribution-incur-an-additional-fee%0Aa-no-this-feature-is-included-in-your-subscription=q-does-organic-seo-attribution-incur-an-additional-fee-a-no-this-feature-is-included-in-your-subscription q-do-organic-seo-conversions-count-as-part-of-my-package%0Aa-yes-same-as-nonorganic-conversions=q-do-organic-seo-conversions-count-as-part-of-my-package-a-yes-same-as-nonorganic-conversions q-can-i-customize-the-name-of-the-seo-media-source%0Aa-no-the-name-of-the-organic-seo-media-source-is-determined-by-appsflyer-and-cant-be-customized-at-this-point=q-can-i-customize-the-name-of-the-seo-media-source-a-no-the-name-of-the-organic-seo-media-source-is-determined-by-appsflyer-and-cant-be-customized-at-this-point q-if-the-search-engine-displays-an-install-button-next-to-the-organic-search-results-and-the-user-clicks-it-and-navigates-to-the-app-store-does-appsflyer-attribute-the-install-to-the-search-engine%0Aa-no-in-this-case-appsflyer-cant-collect-the-required-information-for-attribution-organic-search-attribution-requires-the-app-to-already-be-installed=q-if-the-search-engine-displays-an-install-button-next-to-the-organic-search-results-and-the-user-clicks-it-and-navigates-to-the-app-store-does-appsflyer-attribute-the-install-to-the-search-engine-a-no-in-this-case-appsflyer-cant-collect-the-required-information-for-attribution-organic-search-attribution-requires-the-app-to-already-be-installed q-is-keyword-data-available%0Aa-keyword-data-isnt-available-via-this-organic-search-attribution-solution-however-there-are-rare-instances-where-keyword-data-is-available-for-android-learn-more=q-is-keyword-data-available-a-keyword-data-isnt-available-via-this-organic-search-attribution-solution-however-there-are-rare-instances-where-keyword-data-is-available-for-android-learn-more q-is-organic-search-attribution-supported-in-an-install-flow%0Aa-yes-you-can-learn-from-what-page-users-who-installed-your-app-arrived-at-your-website-smart-script-can-collect-this-page-url-domain-referred-to-as-the-web-referrer-and-map-it-as-a-value-to-a-parameter-key-of-your-choosing-in-the-outgoing-url%0Aweb-referrer-is-especially-useful-for-identifying-the-search-engine-that-guided-users-to-your-website-this-information-can-be-displayed-in-the-dashboard-and-raw-data-reports-under-the-appsflyer-parameter-key-you-selected%0Ato-learn-how-to-set-the-smart-script-to-collect-the-web-referrer-see-here=q-is-organic-search-attribution-supported-in-an-install-flow-a-yes-you-can-learn-from-what-page-users-who-installed-your-app-arrived-at-your-website-smart-script-can-collect-this-page-url-domain-referred-to-as-the-web-referrer-and-map-it-as-a-value-to-a-parameter-key-of-your-choosing-in-the-outgoing-url-web-referrer-is-especially-useful-for-identifying-the-search-engine-that-guided-users-to-your-website-this-information-can-be-displayed-in-the-dashboard-and-raw-data-reports-under-the-appsflyer-parameter-key-you-selected-to-learn-how-to-set-the-smart-script-to-collect-the-web-referrer-see-here h_01H9G0W21TQCKKTZ1FXMGPWR9E=specifications-and-limitations" />

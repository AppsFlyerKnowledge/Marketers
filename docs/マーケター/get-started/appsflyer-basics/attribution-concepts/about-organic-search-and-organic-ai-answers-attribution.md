---
title: About organic search and organic AI answers attribution
deprecated: false
hidden: false
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
  created_at: '2026-11-01T17:06:19Z'
  edited_at: '2026-11-03T07:39:51Z'
  id: 52556274395537
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/52556274395537-About-organic-search-and-organic-AI-answers-attribution
---
> **At a glance:** Use organic search (SEO) and organic AI answers (AEO) attribution to see which search engines and AI answer engines send non-paid traffic to your website and app. Attribute web conversions, app installs, and app re-engagements to them.

## About SEO and AEO attribution

A user searches Google or asks ChatGPT a question, then clicks a result that leads to your website. AppsFlyer credits the search engine or AI answer engine for visits and conversions on your website, app installs, and app opens.

## Supported user journeys

Each journey starts when a user searches a supported search engine or asks a supported AI answer engine a question. If the answer includes a non-paid link and the user clicks it, one of three journeys follows:

| Journey | What AppsFlyer measures | Required implementation |
| --- | --- | --- |
| The user lands on your website | Web visits and web conversions, such as sign-ups and purchases | AppsFlyer web attribution SDK or server-to-server (S2S) integration |
| The user lands on your website, then taps a download button that leads to the app store | App installs | AppsFlyer mobile SDK and Smart Script version 2.10.3 or later, with **Media source for organic search installs** turned on |
| The user lands on your website and is sent straight into your installed app | App re-engagements (app opens) | AppsFlyer Android and iOS SDK version 6.12.1 or later, plus Android App Links and iOS Universal Links |

## Use case 1: Web measurement

Attribute website visits and conversions to the search engine or AI answer engine the user came from.

**Prerequisites:**

* AppsFlyer web attribution SDK or server-to-server (S2S) integration. Learn more in <Anchor target="_blank" href="/marketers/ja/docs/web-performance-measurement-overview">Web Performance Measurement - Overview</Anchor>.

**How it works:**

1. A user clicks a non-paid search result or AI answer link and lands on your website.
2. The web attribution SDK or S2S integration reads the web referrer, the field that shows where the user came from. AppsFlyer attributes the web visit to the matching SEO or AEO media source.
3. If the user later completes a meaningful action, such as signing up or making a purchase, AppsFlyer attributes the event to that search engine or AI answer engine.

<Image align="center" alt="Google Chrome 2026-11-01 19.17.00.png" src="https://files.readme.io/b0303adbc9f9d5baf0be323844859ffd6987257534b6843e10777f290926eef4-52556690362257.png" width="2266px" />

Learn more about <Anchor target="_blank" href="/marketers/ja/docs/about-traffic-source-resolution#ステップ２メディアソースの判定">traffic source resolution</Anchor>.

## Use case 2: App install measurement

Attribute app installs to the search engine or AI answer engine that sent the user to your website.

**Prerequisites:**

* AppsFlyer mobile SDK
* AppsFlyer Smart Script version 2.10.3 or later, with **Media source for organic search installs** turned on

**How it works:**

1. A user clicks a non-paid search result or AI answer link and lands on your website.
2. The page shows a download button with Smart Script behind it. The user doesn't have your app installed, so the button sends them to the app store.
3. Smart Script creates an AppsFlyer attribution link. Its media source (`pid`) is based on the web referrer, the page the user came from. For example, a user comes from google.com, and the visit has no paid indicators (`pid`, UTM parameters, `gclid`, `gbraid`, or `wbraid`). Smart Script can then set `pid=google_organic_seo`.
4. The user installs the app and opens it for the first time. AppsFlyer can attribute the install to that click and credit the search engine or AI answer engine that sent the user to your website.

<Image align="center" alt="Google Chrome 2026-11-01 19.18.06.png" src="https://files.readme.io/c6d27c8feafd44ab5addbbffff2d541936237e3fe45b0b44a6432ac57fe1a35c-52556736289425.png" width="2250px" />

Learn more about <Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#seo-referrer-mapping">setting up Smart Script to convert web visitors</Anchor>.

## Use case 3: App re-engagement measurement

Attribute app opens by users who already have your app installed.

**Prerequisites:**

* AppsFlyer Android and iOS SDK version 6.12.1 or later
* Website content mapped to app content using Android App Links and iOS Universal Links

**How it works:**

1. A user clicks a non-paid search result or AI answer link.
2. Your website content is mapped to your app, and the user has the app installed. The link opens the app directly at the relevant content.
3. The app opens through the deep link. The web referrer, the page the user came from, is sent to AppsFlyer. AppsFlyer uses it to attribute the app open to the matching search engine or AI answer engine.

<Image align="center" alt="Google Chrome 2026-11-01 19.18.53.png" src="https://files.readme.io/e58e45aa7a0adc6beed42e7687fa9c77346f3cd94f69b293514b15d765dab4c7-52556690362641.png" width="2227px" />

Learn more about <Anchor target="_blank" href="/marketers/ja/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">setting up organic search (SEO) and organic AI answers (AEO) re-engagement attribution</Anchor>.

## Data availability

SEO and AEO traffic appears in AppsFlyer as follows:

* **Dashboards and reports:** Search engines appear as `<search engine>_organic_seo`, for example `google_organic_seo`. AI answer engines appear as `<AI engine>_organic_aeo`, for example `chatgpt_organic_aeo`.
* **Raw data reports:** The `channel` field is `seo` for search engine traffic and `aeo` for AI answer engine traffic.

## Supported search engines and AI answer engines

AppsFlyer attributes traffic from the following engines.

**Search engines:** Google, Bing, Yahoo, Ask, DuckDuckGo, Yandex, Naver, Daum, Baidu, Ecosia, Coccoc, Sogou, and Yahoo Japan.

**AI answer engines:** ChatGPT, Claude, Perplexity, Manus, Copilot, Gemini, Grok, and DeepSeek.

## FAQ

### Is there an additional fee for SEO and AEO attribution?

No. It's included in your subscription. Organic conversions count toward your package the same way non-organic conversions do.

### Can I customize the SEO or AEO media source name?

No. AppsFlyer sets the media source name.

### Does AppsFlyer attribute an install when the user taps an install button shown in the search results?

No. In that flow, AppsFlyer can't collect the information needed for attribution.

### Is keyword, search term, or prompt data available?

No. The web referrer doesn't include this information.

## See also

* <Anchor target="_blank" href="/marketers/ja/docs/about-traffic-source-resolution">About traffic source resolution</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors">Set up Smart Script to convert web visitors</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Set up organic search (SEO) and organic AI answers (AEO) re-engagement attribution</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">AppsFlyer attribution model</Anchor>

<div data-zendesk-anchors="h_01M6C15DBDG1JVJ11WZ2ZB5A0R=about-seo-and-aeo-attribution h_01M6C15DBDFD0H52Y2V2X9J89K=supported-user-journeys h_01M6C15DBDKJH8NN771ED3ZWVX=use-case-1-web-measurement h_01M6C15DBDY5Y4KM23NBYN12RH=use-case-2-app-install-measurement h_01M6C15DBDK3HC4SD9X9V7BGWD=use-case-3-app-re-engagement-measurement h_01M6C15DBDSSBM7JK28KT01EA9=data-availability h_01M6C15DBDQSE84ZGBJ7EBHR99=supported-search-engines-and-ai-answer-engines h_01M6C15DBDFQ4R4CE8021ANQ8Z=faq h_01M6C15DBDP74VR7JTPMMDP91H=is-there-an-additional-fee-for-seo-and-aeo-attribution h_01M6C15DBDSVC2E5HTRPJ27PM2=can-i-customize-the-seo-or-aeo-media-source-name h_01M6C15DBD6Q000S8S8VZ2PEK9=does-appsflyer-attribute-an-install-when-the-user-taps-an-install-button-shown-in-the-search-results h_01M6C15DBDQ2JPM01NX82N110A=is-keyword-search-term-or-prompt-data-available h_01M6C15DBD6442ATGZVZNZKGJ9=see-also" />

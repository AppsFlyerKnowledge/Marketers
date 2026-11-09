---
title: >-
  Set up organic search (SEO) and organic AI answers (AEO) re-engagement
  attribution
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
  edited_at: '2026-09-14T15:30:59Z'
  id: 15123194526353
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/15123194526353-Set-up-organic-search-SEO-and-organic-AI-answers-AEO-re-engagement-attribution
---
> **At a glance:** Get detailed attribution data about re-engagements (users who already have your app installed) from organic search engines and AI answer engines so that you can optimize your organic search and AI-driven conversions.

## Overview

Organic search (SEO) and Organic AI answers (AEO re-engagement attribution is an attribution solution that allows AppsFlyer customers to attribute re-engagements (meaning mobile app opens of users who already have your app installed) to various organic search engines and AI answer engines.

Having access to this unique data is very useful to SEO (search engine optimization) and AEO (answer engine optimization) teams, and provides invaluable feedback on their SEO and AEO efforts.

### Flow

<Image align="center" alt="Diagram showing the organic search attribution flow, from a user clicking a search result to the app opening or the user landing on a web page" src="https://files.readme.io/4b33060cfa30a4e2786c4a3a213ca41223ae276d63c97ab7c2cb5a997a4b010c-16540659217809.png" />

The organic search attribution flow works as follows:

1. A user searches for a term on their mobile browser search engine (Google, Bing, etc.). The search engine displays several clickable results.
2. Your web developer maps some of these search results to open your mobile app using Android App Links and iOS Universal Links. If a user has the app installed, when they click the search result, the app opens (without redirecting to an app store first).
3. Upon app launch, AppsFlyer collects the required information and can attribute the app open to the user's search engine.
4. If the user doesn't have the app installed, they are sent to a web landing page, where you can use any of several AppsFlyer web-to-app solutions (like Smart Banners, Smart Script, or QR codes) to redirect and attribute them.

## Setup

**Prerequisites**:

* AppsFlyer Android SDK V6.12.1
* AppsFlyer iOS SDK V6.12.1

**To set up organic search attribution**:

1. Tell your developers to enable app opening by following the instructions for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">Android App Links</Anchor> and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#app-opening-methods">iOS Universal Links</Anchor> (using the app's top-level domain).
2. In AppsFlyer, from the side menu, select **Settings** > <Anchor target="_blank" href="/marketers/vi/docs/app-settings">App Settings</Anchor>, and turn on:
   * **SEO (organic search) and AEO mobile app re-engagement attribution.**
   * **Re-engagement attribution**.

> 📘 **Note**
>
> **A note for your developer**
>
> performOnDeepLinking forcefully consumes and resolves the deep linking URL when invoked. This will prevent the SEO attribution feature from functioning properly and will result in attribution not being reported to the correct SEO media source.

## Data availability

Data is available as follows:

* In aggregate data in dashboards and reports, the `media_source` field indicates which search engine the user arrived from. Example: `google_organic_seo`.
* In raw data reports:
  * `media_source` field indicates which search engine the user arrived from. Example: `google_organic_seo`.
  * `http_referrer` field includes the base URL of the search results page, from which the user was sent to the app or mobile landing page.
  * `channel` field has value `seo` for organic search engine traffic, or `aeo` for AI answer engine traffic.

## Additional information

<Accordion title="List of supported search engines">

Organic search attribution supports the following search engines:

* Google
* Bing
* Yahoo
* Ask
* DuckDuckGo
* Yandex
* Naver
* Daum
* Baidu
* Ecosia
* Coccoc
* Sogou
* Yahoo Japan

> 📘 **Note**
>
> For other search engines, use the legacy organic search attribution solution (requires developer input).
>
> In dashboards and data reports, search engines display as `<search engine>`\_organic\_seo. For example: google\_organic\_seo.

</Accordion>

<Accordion title="List of supported AI answer engines">

Organic search attribution also supports the following AI answer engines:

* ChatGPT
* Claude
* Perplexity
* Manus
* Copilot
* Gemini
* Grok
* Deepseek

> 📘 **Note**
>
> In dashboards and data reports, AI answer engines display as `<AI engine>`\_organic\_aeo. For example: chatgpt\_organic\_aeo.

</Accordion>

<Accordion title="FAQ">

<Accordion title="Does organic SEO attribution incur an additional fee?">

No, this feature is included in your subscription.

</Accordion>

<Accordion title="Do organic SEO conversions count as part of my package?">

Yes, same as non-organic conversions.

</Accordion>

<Accordion title="Can I customize the name of the SEO media source?">

No. AppsFlyer determines the name of the organic SEO media source and can't be customized at this point.

</Accordion>

<Accordion title="If the search engine displays an install button next to the organic search results and the user clicks it and navigates to the app store, does AppsFlyer attribute the install to the search engine?">

No. In this case, AppsFlyer can't collect the required information for attribution. Organic search attribution requires the app to be already installed.

</Accordion>

<Accordion title="Is keyword data available?">

Keyword data isn't available via this organic search attribution solution. However, there are rare instances where keyword data is available for Android. See <Anchor target="_blank" href="/marketers/vi/docs/evaluate-keyword-data#android-keywords">Android keyword data availability</Anchor>.

</Accordion>

<Accordion title="Is organic search attribution supported in an install flow?">

Yes, you can see from which page users who installed your app arrived at your website.

Smart Script does this by:

* Collecting the page's URL domain, referred to as the web referrer
* Creating a relevant `pid` (later displayed as the media source) based on the user's specific origin
* Mapping it to a parameter key of your choosing, such as `af_sub1`, in the outgoing URL

To learn how to set up Smart Script to collect the web referrer, see <Anchor target="_blank" href="/marketers/vi/docs/set-up-smart-script-to-convert-web-visitors#seo-referrer-mapping">OneLink Smart Script V2 setup guide</Anchor>.

</Accordion>

</Accordion>

<Accordion title="Traits and limitations">

| Trait | Description |
| --- | --- |
| Browsers | Organic search attribution isn't supported by:<ul><li>Firefox on Android</li><li>Any browser except for Safari on iOS.</li></ul> |
| SwiftUI apps (iOS) | Organic search attribution is not supported for iOS apps built with SwiftUI. |
| Reengagement window | Organic search has a fixed reengagement window of 30 days. The window size cannot be modified. For more information, see <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide#khung-thời-gian-đưa-vào">Retargeting attribution guide</Anchor>. |

</Accordion>

<div data-zendesk-anchors="organic-search-attribution=overview h_01H9G0W21SRDC6ZSR1E8AQFZFC=overview h_01H9G0W21S4RB56PNV9DAYZPB2=flow h_01H9G0W21S6Z0A5QXC52KSYVQS=setup h_01H9G0W21S7KVJ2Z5DRPCHZF4Z=data-availability h_01H9G0W21SERW2HC44KD77FNCG=additional-information" />

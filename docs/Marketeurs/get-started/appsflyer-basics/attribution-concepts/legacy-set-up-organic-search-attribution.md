---
title: '[Legacy] Set up organic search attribution'
deprecated: true
metadata:
  keywords:
    - Android
    - organic
    - keyword
    - search
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-28T06:35:08Z'
  edited_at: '2025-04-05T12:55:18Z'
  id: 210195193
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/210195193--Legacy-Set-up-organic-search-attribution
---
> **At a glance:** Get detailed organic search attribution data so you can optimize organic conversions. <Anchor target="_blank" href="/marketers/fr/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">See our updated organic search attribution method</Anchor>.

> 🚧 **Important!**
>
> We recommend implementing our <Anchor target="_blank" href="/marketers/fr/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">updated organic search attribution method</Anchor>.

## Organic search attribution

Organic search attribution is an innovative attribution solution that allows AppsFlyer customers to attribute mobile app opens of users who already have your app installed to organic search.

Use organic search attribution to attribute these existing users who re-engage with your app after an organic web search.

#### FLOW

![Organic_SEO_attribution_flow.png](https://files.readme.io/1772808df9d9e521204153d9f0689b3f9f156dd8c0ab8555673b1d321f28aece-15320495862545.png)

1. A user searches for a term (for example “mens shoes”) on their mobile browser search engine (Google, Bing, etc.). The search engine displays several clickable results.
2. Some of these search results are mapped by your web developer to open your mobile open using Android App Links and iOS Universal Links. If a user has the app installed, when they click the search result, the app opens (without redirecting to an app store first).
3. Upon app launch, AppsFlyer collects the required information and is able to attribute the app open to your configured media source (for example search\_engine).
4. If the user doesn’t have the app installed, they are sent to a web landing page, where you can use any of several AppsFlyer web-to-app solutions (like Smart Banners, Smart Script, or QR codes) to redirect and attribute them.

**To set up attribution**:

1. Give your app Android and iOS app developers the domain associated with your app. For Android, this means the domain with Android App Links configured to open the app for existing users. And for iOS, this means the domain with Universal Links is configured to open the app for existing users.
2. Tell the developers what value to use for the media source (`pid`) parameter. For example: search\_engine.
3. Tell your developers to follow their <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_organic_search_attr">Android</Anchor> and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_organic_search_attr">iOS</Anchor> organic search attribution instructions.  
   Any installs from organic searches will display with the media source value you chose. For example: search\_engine.

**Tip!** Learn about <Anchor target="_blank" href="https://gs.statcounter.com/search-engine-market-share">search engine usage breakdown by geo</Anchor>
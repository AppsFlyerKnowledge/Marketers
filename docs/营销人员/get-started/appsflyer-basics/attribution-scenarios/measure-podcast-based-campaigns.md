---
title: Measure podcast-based campaigns
metadata:
  keywords:
    - Advertisers
    - Agencies
    - audio
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2019-12-22T15:49:12Z'
  edited_at: '2026-10-13T00:25:32Z'
  id: 360004494318
  locale: zh-cn
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/zh-cn/articles/360004494318
---
> **At a glance:** Overcome the attribution challenge of mobile app advertising on podcasts by using one of several AppsFlyer solutions.

## Podcast attribution methods

Podcasts are a relatively untapped source of mobile user traffic. Podcast users may react favorably to mobile app ads, but attribution is a challenge. That is because podcasts don’t have a visual interface that generates user impressions or clicks.

However, there are options that bypass these limitations to successfully perform podcast attribution:

* Dedicated landing page
* Firing a OneLink click from a dedicated Podcast app

### Dedicated landing page

A podcast call-to-action (CTA), when it advertises a mobile app, usually involves mentioning an app name so users can search for it.

* In a dedicated landing-page scenario, the CTA is a specific web destination on a landing page.
* This page includes a web element (button, banner, etc.), powered by OneLink. To easily create dynamic landing-page banners without coding, we recommend using <Anchor target="_blank" href="/marketers/zh/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor>.
* Users who engage with this element, and install the mobile app, are attributed according to the OneLink parameters.

> 📄 **Example**
>
> You decide to promote your app on Joe Rogan's podcast and use a dedicated landing page.
>
> Joe smokes, speaks about your app, and then finishes with "go to www.greatapp.com/joe and get 25% off".
>
> The landing page has a **Download app** banner with a OneLink URL. The URL includes the media source "podcast" (&pid=podcast) and the campaign name "joe" (&c=joe).
>
> Users, who click the OneLink URL and install the app, are attributed in the AppsFlyer platform, to the "podcast" media source and the "joe" campaign.

### Firing OneLink click from a Podcast app

This method overcomes the lack of visual interface and allows user attribution without visiting a dedicated landing page.

* In a Firing OneLink Click scenario, the Podcast app fires a OneLink URL click (or impression) when a user is exposed to the ad.
* Normally this occurs at the end of an ad, but it can be timed differently.
* Users, who install an app after listening to a podcast ad, are attributed according to the OneLink parameters.

> 📄 **Example**
>
> You decide to promote your app on the "Making history" podcast, which supports firing OneLink directly after users listen to the ad.
>
> The OneLink URL contains device ID, media source "podcast" (&pid=podcast), and the campaign name "making history" (&c=making%20history).
>
> The ad mentions the name of your app several times, but without a specific URL. Yet, in AppsFlyer, users that install the app are attributed to the "podcast" media source and the "making history" campaign.

#### Who gets the attribution?

In AppsFlyer, the "podcast" media source is considered a custom media source, and not an integrated partner. However, by integrating with AppsFlyer, Podcast app owners can receive postbacks for installs attributed to them. Podcast app owners are welcome to <Anchor target="_blank" href="https://www.appsflyer.com/get-started/partners">contact</Anchor> AppsFlyer's partner development group.

<div data-zendesk-anchors="01JB9NB6DY4ZTS1VAK9S0QSM2R=podcast-attribution-methods 01JB9NB6E5BHETTEY7Q0WD8JXE=dedicated-landing-page 01JB9NB6E9DZXTJTGDPT6HA3FS=example 01JB9NB6EANCCA0FG7ZQY48VSB=firing-onelink-click-from-a-podcast-app 01JB9NB6EDW22XGAM2HCA3CY9Q=example-1 01JB9NB6EDFJ3YNP1JYKDGPHEX=who-gets-the-attribution" />

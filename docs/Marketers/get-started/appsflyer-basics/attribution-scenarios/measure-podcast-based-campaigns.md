---
title: "Measure podcast-based campaigns"
excerpt: "Learn how to overcome the attribution challenge of mobile app advertising on podcasts using AppsFlyer solutions."
---
**At a glance:** Overcome the attribution challenge of mobile app advertising on podcasts by using one of several AppsFlyer solutions.

## Podcast attribution methods

Podcasts are a relatively untapped source of mobile user traffic. Podcast users may react favorably to mobile app ads, but attribution is a challenge. That is because podcasts don’t have a visual interface that generates user impressions or clicks.

However, there are options that bypass these limitations to successfully perform podcast attribution:

- Dedicated landing page
- Firing a OneLink click from a dedicated Podcast app

### Dedicated landing page

A podcast call-to-action (CTA), when it advertises a mobile app, usually involves mentioning an app name so users can search for it.

- In a dedicated landing-page scenario, the CTA is a specific web destination on a landing page.
- This page includes a web element (button, banner, etc.), powered by OneLink. To easily create dynamic landing-page banners without coding, we recommend using [Smart Banners](https://support.appsflyer.com/hc/articles/360000764837).
- Users who engage with this element, and install the mobile app, are attributed according to the OneLink parameters.

#### Example

You decide to promote your app on Joe Rogan's podcast and use a dedicated landing page.

Joe smokes, speaks about your app, and then finishes with "go to www.greatapp.com/joe and get 25% off".

The landing page has a **Download app** banner with a OneLink URL. The URL includes the media source "podcast" (&pid=podcast) and the campaign name "joe" (&c=joe).

Users, who click the OneLink URL and install the app, are attributed in the AppsFlyer platform, to the "podcast" media source and the "joe" campaign.

### Firing OneLink click from a Podcast app

This method overcomes the lack of visual interface and allows user attribution without visiting a dedicated landing page.

- In a Firing OneLink Click scenario, the Podcast app fires a OneLink URL click (or impression) when a user is exposed to the ad.
- Normally this occurs at the end of an ad, but it can be timed differently.
- Users, who install an app after listening to a podcast ad, are attributed according to the OneLink parameters.

#### Example

You decide to promote your app on the "Making history" podcast, which supports firing OneLink directly after users listen to the ad.

The OneLink URL contains device ID, media source "podcast" (&pid=podcast), and the campaign name "making history" (&c=making%20history).

The ad mentions the name of your app several times, but without a specific URL. Yet, in AppsFlyer, users that install the app are attributed to the "podcast" media source and the "making history" campaign.

#### Who gets the attribution?

In AppsFlyer, the "podcast" media source is considered a custom media source, and not an integrated partner. However, by integrating with AppsFlyer, Podcast app owners can receive postbacks for installs attributed to them. Podcast app owners are welcome to [contact](https://www.appsflyer.com/get-started/partners) AppsFlyer's partner development group.
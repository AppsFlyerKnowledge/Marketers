---
title: OneLink Smart Script overview
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
  edited_at: '2024-11-19T13:16:26Z'
  id: 360000677217
  locale: en-us
  section: Web-to-app attribution
  section_id: 6551240476177
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360000677217-OneLink-Smart-Script-overview
---
**At a glance:** Use OneLink Smart Script to convert and attribute your mobile website visitors, coming from any source, into mobile app users.

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

## About OneLink Smart Script

Users arrive at your mobile website before reaching your app store page, either organically, or after engaging with advertising campaigns. However, there are two clicks as follows:

* Direct to the web page
* Direct from the web page to the app store

In this scenario, attribution and deep linking are problematic. Installs by users who eventually download the app may be wrongfully attributed, or attributed as organic. This can occur even if the first click comes from an ad network, Google click, or owned media source.

OneLink Smart Script solves these problems in that it:

* Uses the incoming URLs leading to the web page to dynamically generate unique outgoing OneLink long URLs leading to the app store.
* Provides accurate web-to-app attribution for all media sources, including ad networks, SRNs, Google clicks, and owned media.
* Can be used for deep linking.
* Runs seamlessly on any web page or landing page.
* Doesn't require the use of Smart Banners.   
  **Note**: Smart Banners can be a great conversion tool for many verticals and do not require a developer to set up, but they add another step, the banner, to the user journey.
* Can be set up by the marketer in Google Tag Manager.

There are two versions of OneLink Smart Script:

<Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors">**OneLink Smart Script V2 (recommended)**</Anchor>: If you are setting up OneLink Smart Script for the first time, this is the preferred version to use. It can be configured in the AppsFlyer UI, the developer work portion is easier, and it can also be set up using Google Tag Manager.

<Anchor target="_blank" href="/marketers/docs/legacy-onelink-smart-script-v1-setup">**OneLink Smart Script V1 (legacy)**</Anchor>: If you already have Onelink Smart Script set up, use the documentation for this version to maintain and edit this script. **Note**: Although not mandatory, consider migrating to V2. 

> 📘 **Note**
>
> Not sure whether OneLink Smart Script is the right solution for you? <Anchor target="_blank" href="/marketers/docs/convert-your-mobile-web-visitors-to-app-users">Compare</Anchor> OneLink Smart Script with other AppsFlyer web-to-app solutions.

### Examples

The examples in this section demonstrate how OneLink Smart Script is used to generate outgoing OneLink URLs that provide accurate attribution, or deep linking functionality. For use cases of campaign types with particular media sources, see <Anchor target="_blank" href="/marketers/docs/set-up-smart-script-to-convert-web-visitors#use-cases">Use cases</Anchor>.

<div id="attribution" />

<Accordion title="Attribution">

Mark is the marketer for a hotel chain. He sends an email advertising a hotel vacation in Orlando, Florida. The link in the email looks like this: https://hotel.me/pid=email&c=orlando

The link redirects users to the hotel’s mobile website. There, users see buttons inviting them to download the hotel’s mobile app. The OneLink Smart Script automatically generates a URL that contains the same **pid** and **c** parameters as the original link in the email. The link looks like this: https://hotel.onelink.me/Ac4G?pid=email&c=orlando

When users click the buttons on the mobile site to download the app, the app install is attributed to Mark’s Orlando email campaign.

</Accordion>

<div id="deep-linking" />

<Accordion title="Deep linking">

Emma gets an email advertising a hotel vacation in Orlando, Florida.

The link in the email looks like this: https://hotel.me?type=email&campaign=Florida&city=orlando

When she clicks the link, it redirects her to the hotel’s mobile website. There, she sees buttons inviting her to download the hotel’s mobile app. The OneLink Smart Script automatically generates a URL that contains the same **pid** and **c** parameters as the original link in the email. The link looks like this: https://hotel.onelink.me/Ac4G?pid=email&c=Florida&deep_link_value=orlando

**When Emma clicks the buttons on the mobile site, she is redirected to the app store. And when she downloads and launches the app, she is deep linked to the Orlando vacation page in the app.**

> 📘 **Note**
>
> The deep linking is in accordance with the app settings implemented by the app developers. <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link">Learn more</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HE7RW9G26CNME9TP350GFGS4=about-onelink-smart-script h_01HE7RW9G2BV2NFJ0YZ9QKAA2V=note h_01HE7RW9G2WBZ1A0RS66CJ7BNH=examples h_01HE7RW9G24Y604NTZFGKJJXSS=attribution h_01HE7RW9G2ZDDWE1M1B2G175ZF=deep-linking h_01HE7RW9G3W5GKQ2CD2BZW8YAW=note-1" />

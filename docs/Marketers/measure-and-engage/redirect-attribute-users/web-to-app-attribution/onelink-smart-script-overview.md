---
title: "OneLink Smart Script overview"
excerpt: "Use OneLink Smart Script to convert and attribute your mobile website visitors, coming from any source, into mobile app users."
---
![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

## About OneLink Smart Script

Users arrive at your mobile website before reaching your app store page, either organically, or after engaging with advertising campaigns. However, there are two clicks as follows:

- Direct to the web page
- Direct from the web page to the app store

In this scenario, attribution and deep linking are problematic. Installs by users who eventually download the app may be wrongfully attributed, or attributed as organic. This can occur even if the first click comes from an ad network, Google click, or owned media source.

OneLink Smart Script solves these problems in that it:

- Uses the incoming URLs leading to the web page to dynamically generate unique outgoing OneLink long URLs leading to the app store.
- Provides accurate web-to-app attribution for all media sources, including ad networks, SRNs, Google clicks, and owned media.
- Can be used for deep linking.
- Runs seamlessly on any web page or landing page.
- Doesn't require the use of Smart Banners.

> 📘 Note
>
> Smart Banners can be a great conversion tool for many verticals and do not require a developer to set up, but they add another step, the banner, to the user journey.

- Can be set up by the marketer in Google Tag Manager.

There are two versions of OneLink Smart Script:

<Tabs>
<Tab title="OneLink Smart Script V2 (recommended)">

[OneLink Smart Script V2 (recommended)](/docs/set-up-smart-script-to-convert-web-visitors): If you are setting up OneLink Smart Script for the first time, this is the preferred version to use. It can be configured in the AppsFlyer UI, the developer work portion is easier, and it can also be set up using Google Tag Manager.

</Tab>
<Tab title="OneLink Smart Script V1 (legacy)">

[OneLink Smart Script V1 (legacy)](/docs/legacy-onelink-smart-script-v1-setup): If you already have Onelink Smart Script set up, use the documentation for this version to maintain and edit this script. **Note**: Although not mandatory, consider migrating to V2.

</Tab>
</Tabs>

> 📘 Note
>
> Not sure whether OneLink Smart Script is the right solution for you? [Compare](/docs/convert-your-mobile-web-visitors-to-app-users) OneLink Smart Script with other AppsFlyer web-to-app solutions.

### Examples

The examples in this section demonstrate how OneLink Smart Script is used to generate outgoing OneLink URLs that provide accurate attribution, or deep linking functionality. For use cases of campaign types with particular media sources, see [Use cases](/docs/set-up-smart-script-to-convert-web-visitors#use-cases).

### Attribution

Mark is the marketer for a hotel chain. He sends an email advertising a hotel vacation in Orlando, Florida. The link in the email looks like this: **https://hotel.me/pid=email&c=orlando**

The link redirects users to the hotel’s mobile website. There, users see buttons inviting them to download the hotel’s mobile app. The OneLink Smart Script automatically generates a URL that contains the same **pid** and **c** parameters as the original link in the email. The link looks like this: **https://hotel.onelink.me/Ac4G?pid=email&c=orlando**

When users click the buttons on the mobile site to download the app, the app install is attributed to Mark’s Orlando email campaign.

### Deep linking

Emma gets an email advertising a hotel vacation in Orlando, Florida.

The link in the email looks like this: **https://hotel.me?type=email&campaign=Florida&** **city=orlando**

When she clicks the link, it redirects her to the hotel’s mobile website. There, she sees buttons inviting her to download the hotel’s mobile app. The OneLink Smart Script automatically generates a URL that contains the same **pid** and **c** parameters as the original link in the email. The link looks like this: **https://hotel.onelink.me/Ac4G?pid=email&c=Florida&deep\_link\_value=orlando**

**When Emma clicks the buttons on the mobile site, she is redirected to the app store. And when she downloads and launches the app, she is deep linked to the Orlando vacation page in the app.**

> 📘 Note
>
> The deep linking is in accordance with the app settings implemented by the app developers. [Learn more](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link).
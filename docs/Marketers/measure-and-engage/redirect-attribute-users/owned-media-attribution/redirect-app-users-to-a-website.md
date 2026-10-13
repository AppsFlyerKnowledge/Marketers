---
title: "Redirect app users to a website"
excerpt: "Redirect app users to a web URL or social media page by using a URL generated with OneLink."
x-zendesk:
  id: 4460838224273
  url: https://support.appsflyer.com/hc/en-us/articles/4460838224273-Redirect-app-users-to-a-website
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Owned media attribution
  section_id: 6551214397585
  position: 4
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, Social-to-App]
  labels: [OneLink, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-02-22T11:45:43Z'
  edited_at: '2024-12-09T09:17:42Z'
---
Advertisers can post OneLink URLs leading to external web pages or social media sites. AppsFlyer measures the clicks on the link inside the app, by which you can determine the efficacy of the ad.

### Redirect app users to a web URL

**Prerequisites**: An AppsFlyer account with at least one app.

**To set up app-to-web redirection**:

1. Set up a [OneLink template](/docs/create-a-onelink-template#procedures).
   - In the **When app is installed** section, make sure you don't set up an app-opening method (Universal Links, App Links, or URI scheme).
2. Create a [OneLink custom link](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link).
   - In the **When app isn’t installed** section, make sure the redirection settings are to the desired web URL.
   - Don't add an `af_dp` parameter with a URI Scheme.
3. Make sure the domain you're redirecting users to appears in your [redirect allowlist](/docs/set-up-your-domain-redirect-allowlist).

> 📘 Note
>
> Setting up a domain redirect allowlist is required to ensure users are redirected to verified, trustworthy domains.

**To test your link**:

**Prerequisites**: A mobile device with the app installed.

1. Send the short or long URL to your phone, and click it.

> 📘 Note
>
> Email or WhatsApp yourself the link, and open it on your phone. Don't paste into iOS notes, or directly into a mobile browser.

2. You should be redirected to the web URL.
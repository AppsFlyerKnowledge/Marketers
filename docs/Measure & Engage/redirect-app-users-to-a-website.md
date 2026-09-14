---
title: "Redirect app users to a website"
excerpt: "Learn how to redirect app users to an external web URL or social media page using a OneLink URL while measuring click efficacy."
---
Advertisers can post OneLink URLs leading to external web pages or social media sites. AppsFlyer measures the clicks on the link inside the app, by which you can determine the efficacy of the ad.

### Redirect app users to a web URL

**Prerequisites**: An AppsFlyer account with at least one app.

**To set up app-to-web redirection**:

1. Set up a [OneLink template](https://support.appsflyer.com/hc/articles/207032246#procedures).
   - In the **When app is installed** section, make sure you don't set up an app-opening method (Universal Links, App Links, or URI scheme).
2. Create a [OneLink custom link](https://support.appsflyer.com/hc/articles/208874366#create-a-onelink-link).
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
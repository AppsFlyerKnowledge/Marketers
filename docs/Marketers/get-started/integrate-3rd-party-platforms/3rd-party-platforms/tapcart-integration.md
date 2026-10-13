---
title: "Tapcart integration"
excerpt: "Use Tapcart to leverage AppsFlyer capabilities in your app."
x-zendesk:
  id: 4411720533905
  url: https://support.appsflyer.com/hc/en-us/articles/4411720533905-Tapcart-integration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 29
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-11-24T09:21:54Z'
  edited_at: '2025-03-25T10:24:36Z'
---
## Introduction

Tapcart makes it easy to send your data to AppsFlyer and utilize its capabilities. When developing your app with Tapcart, the AppsFlyer SDK is implemented in the app as a default. Once you have recorded your data through Tapcart, the data, including organic and non-organic installs, is displayed in AppsFlyer.

## Integrating Tapcart with AppsFlyer

AppsFlyer's SDK enables you to measure installs, uninstalls, referrals, user engagements with push notifications, perform deeplinking, handle user privacy scenarios, and more.

Follow [this page from Tapcart](https://tapcart.com/integrations/appsflyer) to learn how to integrate Tapcart with AppsFlyer.

## Default in-app events configured in the AppsFlyer SDK

After Tapcart has integrated the AppsFlyer SDK in your app, the following in-app events are recorded whenever a user performs them:

* Complete registration
* Login
* Search
* Content view
* List view
* Add to wishlist
* Add to cart
* Initiated checkout
* Purchase
* Completed purchase
* Remove from cart
* First purchase

## Enable deep linking with AppsFlyer

To enable deep linking with AppsFlyer, you need to provide Tapcart the following parameters:

1. **Dev key:** This unique identifier and authentication token is used to configure the SDK, encrypt its messages, and authenticate a client account or call a program to an API. Apps in the same account usually have the same dev key. Learn more about the [dev key](/docs/app-settings#sdk-authentication-dev-key).
2. **OneLink template ID:** This is the ID for the OneLink template used for generating your OneLink URLs. Learn more about [creating a OneLink template](/docs/create-a-onelink-template#procedures).

   **To get the ID for a specific template:**
   1. In AppsFlyer, go to **Experiences & Deep Linking** > **OneLink Custom Links**
   2. In the **OneLink template** menu, select the required template.
   3. Copy the ID displayed on the right-hand side.

   <Image src="https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png" alt="OneLink template ID location in AppsFlyer dashboard" />

3. **OneLink URL:** a specific OneLink URL generated in AppsFlyer for a specific campaign. Learn more about [how to generate your OneLink](/docs/onelink-guide).
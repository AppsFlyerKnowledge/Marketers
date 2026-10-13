---
title: "Dynamic event mapping for in-app events"
excerpt: "Learn how to configure your attribution links so partners can receive different postbacks for a single in-app event based on Goal IDs."
x-zendesk:
  id: 208996726
  url: https://support.appsflyer.com/hc/en-us/articles/208996726-Dynamic-event-mapping-for-in-app-events
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Platforms for ad networks
  section_id: 6551055575185
  position: 10
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Mobile Attribution, Ad Networks]
  labels: [In-App, Mapping, Dynamic Event Mapping, Ad Networks, Partners]
  promoted: false
  comments_disabled: true
  created_at: '2016-05-26T08:48:23Z'
  edited_at: '2023-05-14T14:09:20Z'
---
**At a glance:** Set up your attribution link so that your partners (such as TUNE or CAKE) can receive different postbacks for a single in-app event, based on Goal IDs.

## Introduction

Different postbacks can be sent for an in-app event depending on the Goal ID.

This feature supports networks using HasOffers, CAKE, or other networks that want to receive different in-app event postbacks for a single SDK in-app event.

On the Active Integrations page in the dashboard, advertisers map each of their SDK events to the preferred dynamic Event Tag for each partner. The event tag includes both in-app events and rejected in-app event postbacks.

This enables ad networks to open multiple campaigns with a separate dynamic event tag (example: HasOffers calls this goal_id) for each campaign. The dynamic event tags are then passed to the ad network in the postback based on the value that was placed in the click URL.

## Attribution link

#### Attribution Link Example

**Decoded**:

```http
https://app.appsflyer.com/com.xyz.abc?pid=mediasource_int&clickid={transaction_id}
&goalid_1={XXX}&goalid_2={YYY}
```

The advertiser must map all of the goal_ids in the in-app events section (see below) according to the network's instructions.

In the example below, level20_finished is mapped as $$click(goalid_1) and level25_finished is mapped as $$click(goalid_2).

When the app user completes level 20, AppsFlyer returns to the relevant value (in this case XXX as it appears in the attribution link above) and sends it in the postback.

If the same or a different user then completes level 25 AppsFlyer again returns to the attribution link and dynamically populates the goal_id with the relevant value (in this case YYY) and sends it in the postback.

<Image src="https://files.readme.io/828562b99269c27aef0f6f7516fefa32f7052eaf0d8d0dc54bc4cdf19da361d5-Goadid.png" alt="Goadid.png" />
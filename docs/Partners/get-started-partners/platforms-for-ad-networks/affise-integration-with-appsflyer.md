---
title: "Affise integration with AppsFlyer"
excerpt: "Ad networks that use Affise can utilize the AppsFlyer probabilistic modeling solution to receive attribution data about installs and in-app events."
x-zendesk:
  id: 208537116
  url: https://support.appsflyer.com/hc/en-us/articles/208537116-Affise-integration-with-AppsFlyer
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Platforms for ad networks
  section_id: 6551055575185
  position: 13
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Integration, affise, Advertisers, Ad Networks, Partners]
  promoted: false
  comments_disabled: true
  created_at: '2016-04-19T12:08:58Z'
  edited_at: '2024-12-23T15:05:34Z'
---
To start the integration you must send AppsFlyer both the attribution link and the postback for reporting purposes.

## Base attribution link

Below you can find the base attribution link with a detailed explanation per each parameter:

```
https://app.appsflyer.com/com.appsflyer?pid=mediaName_int&clickid={clickid}&af_siteid={pid}&af_c_id={offerid}
```

**Obligatory Attribution Link Parameters**

| AppsFlyer Parameter | Affise Macros | Description |
| --- | --- | --- |
| clickid | `{clickid}` | Request ID of each user session |
| af\_siteid | `{pid}` | ID of the affiliate promoting the offer |
| af\_c\_id | `{offer_id}` | ID of the offer |

For a complete AppsFlyer parameter list [click here](/docs/about-link-structure-and-parameters).

## Complete attribution link template

```
https://app.appsflyer.com/com.appsflyer?pid=mediaName_int&clickid={clickid}&af_siteid={pid}
```

## Install and in-app event postbacks

The following are examples of Install and In-App Event Postbacks:

### Global install postback iOS

```
https://domain.com/postback?clickid={clickid}&action_id={eventtime}&ios_idfa={idfa}
```

### Global install postback Android

```
https://domain.com/postback?clickid={clickid}&action_id={eventtime}&android_id={android_id}
```

### Global in-app event postback iOS

```
https://domain.com/postback?clickid={clickid}&action_id={eventtime}&ios_idfa={idfa}&goal={event-name}
```

### Global in-app event postback Android

```
https://domain.com/postback?clickid={clickid}&action_id={eventtime}&android_id={android_id}&goal={event-name}
```

Domain.com is the network ID (domain) name provided by Affise.

e= Set as **Event Name** in the AppsFlyer dashboard for each App by the advertiser - This is the actual in-app event name from the application.

Additional attribution information can be added to the postback by request such as Country Code, Advertising ID, IDFA etc.

## Finalizing your registration

* If you have an integration with AppsFlyer, contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).
* If you don't have an integration with AppsFlyer, complete the ad Partners Registration application [here](https://www.appsflyer.com/partners-registration/).
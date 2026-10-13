---
title: "Trackier integration with AppsFlyer"
excerpt: "Learn how to configure attribution links and postback URLs to integrate Trackier with AppsFlyer for tracking installs and in-app events."
x-zendesk:
  id: 360006111917
  url: https://support.appsflyer.com/hc/en-us/articles/360006111917-Trackier-integration-with-AppsFlyer
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Platforms for ad networks
  section_id: 6551055575185
  position: 14
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [AdNetwork Integration, ad networks, Advertisers, Ad Networks, ad network, Partners, trackier]
  promoted: false
  comments_disabled: true
  created_at: '2020-02-24T13:25:45Z'
  edited_at: '2024-12-23T15:22:55Z'
---
**At a glance:** Ad networks that use Trackier can receive attribution data from AppsFlyer about installs and in-app events.

To begin integration, provide AppsFlyer with both the attribution link URL and the postback URL. The URLs are needed for reporting purposes. This article explains how to build these URLs.

## Attribution link URL

This section provides the base attribution link and related parameter descriptions.

### Base attribution link URL

```http
https://app.appsflyer.com/com.yourapp?pid=mediaName_int&clickid={click_id}&af_siteid={publishedr_id}
&af_c_id={camp_id}
```

| AppsFlyer base URL | Definition | Description |
| --- | --- | --- |
| https://app.appsflyer.com | Base URL | AppsFlyer endpoint |
| app\_id | Application ID | Dynamic value that differs for each app |
| pid= | Media source name | **\_int** identifies an **integrated** network |
| c= | Campaign name | Name given by the advertiser |

### Attribution link parameters

> 📘 Note
>
> The attribution links in the following table are **mandatory**.

See complete parameter lists for:

- [AppsFlyer](/docs/about-link-structure-and-parameters)
- [Trackier](https://trackier.com/support/kb/tracking-macros/)

| AppsFlyer parameter | Trackier macro | Description |
| --- | --- | --- |
| &clickid= | `{click\_id}` | Request the ID for each user session |
| &af\_siteid= | `{publisher\_id}` | ID of the affiliate promoting an offer |
| &af\_c\_id= | `{camp\_id}` | Offer ID |

## Postback URLs for install and in-app events

This section provides examples of postback URLs and parameters for install and in-app events.

<Tabs>
<Tab title="iOS">

#### Global install postback

```http
https://yourdomain.com/acquisition?click_id={clickid}&security_token=xxxxxxxxxxxxxxx&idfa={idfa}
```

#### Global in-app event postback

```http
https://yourdomain.com/acquisition?click_id={clickid}&security_token=xxxxxxxxxxxxxxx&idfa={idfa}&goal_value={event-name}
```

</Tab>
<Tab title="Android">

#### Global install postback

```http
https://yourdomain.com/acquisition?click_id={clickid}&security_token=xxxxxxxxxxxxxxx&gaid={android_id}
```

#### Global in-app event postback

```http
https://yourdomain.com/acquisition?click_id={click_id}&security_token=xxxxxxxxxxxxxxx&gaid={android_id}&goal_value={event-name}
```

</Tab>
</Tabs>

### Postback parameters

| AppsFlyer Base URL | Description |
| --- | --- |
| yourdomain.com | - Network ID (domain) name<br />- Provided by Trackier |
| event-name | - In-app event name<br />- Defined by the advertiser |
| security\_token | Provided by Trackier |
| Country code, advertising ID, IDFA, etc. | [Optional] Attribution information that can be added to a postback |

## Finalizing your registration

Already integrated with AppsFlyer? Send us the URLs using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).

Not yet integrated with AppsFlyer? Complete the [Ad partners registration application](https://www.appsflyer.com/partners-registration/).
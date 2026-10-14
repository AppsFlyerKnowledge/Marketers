---
title: "Voluum integration with AppsFlyer"
excerpt: "Ad networks that use Voluum can utilize the AppsFlyer Probabilistic modeling solution to receive attribution data about installs and in-app events."
x-zendesk:
  id: 207274016
  url: https://support.appsflyer.com/hc/en-us/articles/207274016-Voluum-integration-with-AppsFlyer
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Platforms for ad networks
  section_id: 6551055575185
  position: 12
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Advertisers, Ad Networks, Partners]
  promoted: false
  comments_disabled: true
  created_at: '2016-01-11T14:46:09Z'
  edited_at: '2026-05-04T09:31:48Z'
---
## Starting the integration

To start the integration you must send AppsFlyer both the attribution link and the postback for reporting purposes.

Below you can find the base attribution link with a detailed explanation per each parameter:

`https://app.appsflyer.com/app_id?pid=mediaName_int&c={campaign}`

| AppsFlyer Base URL | Description |
| --- | --- |
| https://app.appsflyer.com | AppsFlyer End-Point |
| app\_id | Application Unique ID - Dynamic value changed per app promoted |
| pid= | Media source name include **\_int** to identify **integrated** network at AppsFlyer servers |
| c= | Campaign name |

**Recommended Attribution Link Parameters:**

| AppsFlyer Parameter | Voluum Macros | Description |
| --- | --- | --- |
| &clickid= | `{clickid}` | Unique transaction ID of the user session - **Required** |
| ⁡\_siteid= | `{trafficsource.id}` | ID of the traffic source - **Optional** |

** For complete AppsFlyer parameter list, [click here](/docs/about-link-structure-and-parameters)

** For complete Voluum macro list, [click here](http://feedback.voluum.com/knowledgebase/articles/318681-click-urls)

### Complete attribution link template

```
https://app.appsflyer.com/com.appsflyer?pid=mediaName_int&clickid={clickid}&af_siteid={trafficsource.id}
```

### Install and in-app event postbacks

Global Install Postback:

```
https://{Company-Domain}.voluumtrk.com/postback?cid={clickid}
```

Global In-App Event Postback:

```
https://{Company-Domain}.trackvoluum.com/postback?cid={clickid}&payout={monetary}&txid={event-name}
```

** `{Company-Domain}` the network ID (domain) name provided by Volumm.  
** txid= Set as **Event Tag** in the AppsFlyer dashboard for each App by the advertiser. This is the actual in-app event name from the application.

### AppsFlyer's in-app event dashboard

![Voluum_msc_new_1.png](https://files.readme.io/bb58ccaabf1eb8d615288d259102b3dc7883c5c79448131c67374ad8fbdaf6c0-360002325069.png)  
** Additional attribution information can be added to the postback by request such as Country Code, Advertising ID, IDFA, etc.

## Finalizing your registration

* If you have an integration with AppsFlyer, contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).
* If you don't have an integration with AppsFlyer, complete the ad Partners Registration application [here](https://www.appsflyer.com/partners-registration/).
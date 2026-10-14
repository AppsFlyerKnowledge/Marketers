---
title: "Appnexus integration with AppsFlyer"
excerpt: "Ad networks that use Affise can utilize the AppsFlyer Probabilistic modeling solution to receive attribution data about installs and in-app events."
x-zendesk:
  id: 207583523
  url: https://support.appsflyer.com/hc/en-us/articles/207583523-Appnexus-integration-with-AppsFlyer
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Platforms for ad networks
  section_id: 6551055575185
  position: 1
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Integration, AppNexus, Advertisers, Ad Networks, Partners]
  promoted: false
  comments_disabled: true
  created_at: '2016-01-11T14:45:34Z'
  edited_at: '2024-12-23T15:08:44Z'
---
## Starting the integration

To start the integration you must send AppsFlyer both the attribution link and the postback for reporting purposes.

Below you can find the base attribution link with a detailed explanation per each parameter:

`https://app.appsflyer.com/app_id?pid=mediaName_int&c={campaign}`

| AppsFlyer Base URL | Description |
| --- | --- |
| https://app.appsflyer.com | AppsFlyer end-Point |
| app\_id | Application Unique ID - Dynamic value changed per app promoted |
| pid | Media source name include **\_int** to identify<br />**integrated** network at AppsFlyer servers |
| c | Campaign name |

**AppNexus Advertising ID Macros**

| Operating System | Macro |
| --- | --- |
| Android | &advertising\_id=$`{DEVICE_AAID}` |
| iOS | idfa=$`{DEVICE_APPLE_IDA}` |

**Recommended Attribution Link Parameters**

| AppsFlyer Parameter | AppNexus Macros | Description |
| --- | --- | --- |
| clickid | $`{SSP_DATA}` | Request ID of each user session - **Required** |
| af\_siteid | $`{PUBLISHER_ID}` | ID of the affiliate promoting the offer - **Optional** |

For the complete AppsFlyer parameter list [click here](/docs/about-link-structure-and-parameters).

For the complete AppNexus macro list [click here](https://wiki.appnexus.com/display/sdk/Welcome).

### Complete attribution link template:

```
https://app.appsflyer.com/com.appsflyer?pid=mediaName_int&clickid=${SSP_DATA}&af_siteid=${PUBLISHER_ID}
```

### Install and in-app event postbacks

Global Install Postback:

```
https://sspx-router.adnxs.net/sspx?id={ID}&sspdata={clickid}
```

`{ID}` the Network ID provided by AppNexus, inserted in AppsFlyer dashboard per app.

### AppsFlyer install dashboard

[![appnexus-pixelid.png](https://files.readme.io/0f14632fc7421fbbb26f90c13cc37afad58e4e217f4bcebd931cddb7576c5113-360018728918.png)](https://files.readme.io/29832948c523c79327b1592dbf30ab4a1227cf5f7281cf7f09cee7450aff0170-360002326469.png)

Additional attribution information can be added to the postback by request such as Country Code, Advertising ID, IDFA, and so on.

## Finalizing your registration

* If you have an integration with AppsFlyer, contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).
* If you don't have an integration with AppsFlyer, complete the ad Partners Registration application [here](https://www.appsflyer.com/partners-registration/).
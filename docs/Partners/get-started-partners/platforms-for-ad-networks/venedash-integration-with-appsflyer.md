---
title: "venedash integration with AppsFlyer"
excerpt: "Send attribution data from AppsFlyer to venedash. AppsFlyer can send venedash both install and in-app event data."
x-zendesk:
  id: 360007705617
  url: https://support.appsflyer.com/hc/en-us/articles/360007705617-venedash-integration-with-AppsFlyer
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Platforms for ad networks
  section_id: 6551055575185
  position: 8
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Advertisers, Ad Networks, Partners]
  promoted: false
  comments_disabled: true
  created_at: '2020-04-24T21:20:47Z'
  edited_at: '2026-09-09T13:56:49Z'
---
## venedash integration setup

- If you have an integration with AppsFlyer, contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).
- If you don't have an integration with AppsFlyer, complete the ad Partners Registration application [here](https://www.appsflyer.com/partners-registration/).

**To enable the integration with AppsFlyer:**

1. In **AppsFlyer**, go to **Collaborate** **>** **Partner Integrations > Active Integrations** and select Venedash from the partner list.
2. In the **Integration** tab, enable **Activate partner**.
3. Go to the **Attribution Link** tab and generate an attribution link with the following mandatory parameters:

| AppsFlyer parameter | venedash parameter | Description |
| --- | --- | --- |
| &clickid= | `{#ydrid#}` | Request ID of each user session |
| &af\_siteid= | `{#ydr_pid#}` | ID of the affiliate who promotes the offer |
| &advertising\_id | `{#android_adv#}` | Android device ID |
| &idfa= | `{#iosidfa#}` | ​iOS device ID |

> 📘 Note
>
> The pid parameter is filled by the Appsflyer team.

Example:

```auto
https://app.appsflyer.com/com.appsflyer?pid=mediaName_int&clickid=#ydrid#&af_siteid=#ydr_pid#&advertising_id=advertising_id&idfa=#iosidfa#
```

Learn more about [attribution link parameters](/docs/about-link-structure-and-parameters).

4. In Venedash, create an offer and paste the AppsFlyer attribution link in the Destination URL field.

![venedash-destination_url-en_us.png](https://files.readme.io/2a284eab8d25f57f1bfa2981e2d86bf16bce16b64b61858fdb819d5ac14eac20-360016242798.png)
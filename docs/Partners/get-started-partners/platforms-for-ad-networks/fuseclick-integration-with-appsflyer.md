---
title: "Fuseclick integration with AppsFlyer"
excerpt: "Learn how to configure FuseClick integration with AppsFlyer, including setting up basic attribution links, recommended parameters, and postbacks."
---
Ad networks that use FuseClick can utilize the AppsFlyer Probabilistic modeling solution to receive attribution data about installs and in-app events.

## Basic attribution link

Below you can find the base attribution link with a detailed explanation per each parameter:

```http
https://app.appsflyer.com/app_id?pid=mediaName_int&c={campaign}
```

| AppsFlyer Base URL | Description |
| --- | --- |
| https://app.appsflyer.com | AppsFlyer endpoint |
| app\_id | Application unique ID - Dynamic value changed per-app promoted |
| pid | Media source name include **\_int** to identify<br />**integrated** network at AppsFlyer servers |
| c | Campaign name |

**Recommended Attribution Link Parameters:**

| AppsFlyer Parameter | FuseClick Macros | Description |
| --- | --- | --- |
| clickid | `{TID}` | Request ID of each user session - **Required** |
| af\_siteid | `{SC}` | ID of the affiliate promoting the offer - **Optional** |

For the complete AppsFlyer parameter list [click here](/docs/postback-macros-for-ad-networks)

For complete FuseClick macro list [click here](https://support.fuseclick.com/documentation/open/iwf/2016/0805/199.html)

Complete Attribution Link Template:

```http
https://app.appsflyer.com/com.appsflyer?pid=mediaName_int&clickid={TID}&af_siteid={ADV_SID}
```

### Install and in-app event postbacks

Global Install Postback:

```html
https://tracking.zadsmobile.com/pb?tid={TID}
```

Additional attribution information can be added to the postback by request such as: Country Code, Advertising ID, IDFA, and more.

## Finalizing your registration

- If you have an integration with AppsFlyer, contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).
- If you don't have an integration with AppsFlyer, complete the ad Partners Registration application [here](https://www.appsflyer.com/partners-registration/).
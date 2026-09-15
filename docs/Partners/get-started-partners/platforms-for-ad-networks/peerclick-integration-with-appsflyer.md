---
title: "PeerClick integration with AppsFlyer"
excerpt: "Learn how to integrate PeerClick with AppsFlyer to receive attribution data about installs and in-app events using probabilistic modeling."
---
Ad networks that use PeerClick can benefit from the AppsFlyer Probabilistic modeling solution to receive attribution data about installs and in-app events.

## Starting the integration

To start the integration you must send AppsFlyer both the attribution link and the postback for reporting purposes.

Below you can find the base attribution link with a detailed explanation per each parameter:

`https://app.appsflyer.com/app_id?pid=mediaName_int&c={campaign}`

| AppsFlyer Base URL | Description |
| --- | --- |
| https://app.appsflyer.com | AppsFlyer End-Point |
| app\_id | Application Unique ID - Dynamic value changed per app promoted |
| pid= | Media source name include **\_int** to identify<br>**integrated** network at AppsFlyer servers |
| c= | Campaign name |

**Recommended Attribution Link Parameters:**

| AppsFlyer Parameter | Voluum Macros | Description |
| --- | --- | --- |
| &clickid= | {clickid} | Unique transaction ID of the user session - **Required** |
| &af\_siteid= | {trafficsource.id} | ID of the traffic source - **Optional** |

> 📘 Note
>
> * For the complete AppsFlyer parameter list, [click here](https://support.appsflyer.com/hc/articles/207447163)
> * For the complete PeerClick list, [click here](https://help-center.peerclick.com/en/)

### Complete attribution link template

```http
https://app.appsflyer.com/com.appsflyer?pid=mediaName_int&clickid={clickid}&af_siteid={trafficsource.id}
```

### Install and in-app event postbacks

**Global Install Postback:**

```http
https://pstb.gopeerclick.com/postback?userid={peerclick_userid}&cid={clickid}
```

**Global In-App Event Postback:**

`https://pstb.gopeerclick.com/postback?userid={peerclick_userid}&cid={clickid}&payout={monetary}&txid={event-name}`

* **userid:** The user ID provided by PeerClick
* **txid:** The actual in-app event name from the application, set as **Event Tag** in the AppsFlyer dashboard for each App by the advertiser

### AppsFlyer's in-app event dashboard

![Voluum_msc_new_1.png](https://files.readme.io/ecad61ab31de52e88c483daeaa05cd223ece998f3d8c22ae400c68fc2b7537f2-21479841978001.png)

Additional attribution information can be added to the postback by request such as Country Code, Advertising ID, IDFA, etc.
---
title: "Affise integration with AppsFlyer"
excerpt: "Learn how to integrate Affise with AppsFlyer using attribution links and postbacks for tracking installs and in-app events."
---
Ad networks that use Affise can utilize the AppsFlyer probabilistic modeling solution to receive attribution data about installs and in-app events.

To start the integration you must send AppsFlyer both the attribution link and the postback for reporting purposes.

## Base attribution link

Below you can find the base attribution link with a detailed explanation per each parameter:

```http
https://app.appsflyer.com/com.appsflyer?pid=mediaName_int&clickid={clickid}&af_siteid={pid}&af_c_id={offerid}
```

**Obligatory Attribution Link Parameters**

| AppsFlyer Parameter | Affise Macros | Description |
| --- | --- | --- |
| clickid | {clickid} | Request ID of each user session |
| af\_siteid | {pid} | ID of the affiliate promoting the offer |
| af\_c\_id | {offer\_id} | ID of the offer |

For a complete AppsFlyer parameter list [click here](https://support.appsflyer.com/hc/articles/207447163).

## Complete attribution link template

```http
https://app.appsflyer.com/com.appsflyer?pid=mediaName_int&clickid={clickid}&af_siteid={pid}
```

## Install and in-app event postbacks

The following are examples of Install and In-App Event Postbacks:

<Tabs>
<Tab title="iOS Install">

```http
https://domain.com/postback?clickid={clickid}&action_id={eventtime}&ios_idfa={idfa}
```

</Tab>
<Tab title="Android Install">

```http
https://domain.com/postback?clickid={clickid}&action_id={eventtime}&android_id={android_id}
```

</Tab>
<Tab title="iOS In-App Event">

```http
https://domain.com/postback?clickid={clickid}&action_id={eventtime}&ios_idfa={idfa}&goal={event-name}
```

</Tab>
<Tab title="Android In-App Event">

```http
https://domain.com/postback?clickid={clickid}&action_id={eventtime}&android_id={android_id}&goal={event-name}
```

</Tab>
</Tabs>

Domain.com is the network ID (domain) name provided by Affise.

e= Set as **Event Name** in the AppsFlyer dashboard for each App by the advertiser - This is the actual in-app event name from the application.

Additional attribution information can be added to the postback by request such as Country Code, Advertising ID, IDFA etc.

## Finalizing your registration

* If you have an integration with AppsFlyer, contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).
* If you don't have an integration with AppsFlyer, complete the ad Partners Registration application [here](https://www.appsflyer.com/partners-registration/).
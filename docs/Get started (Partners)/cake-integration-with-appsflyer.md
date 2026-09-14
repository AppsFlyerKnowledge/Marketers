---
title: "Cake integration with AppsFlyer"
excerpt: "Learn how to configure attribution links and postbacks for CAKE-based ad networks integrating with AppsFlyer."
---
At a glance: Ad networks that use CAKE can receive attribution data from AppsFlyer about installs and in-app events.

## Base attribution link

Below you can find the base attribution link with a detailed explanation per each parameter:

`https://app.appsflyer.com/app_id?pid=mediaName_int&c={campaign}`

| AppsFlyer Base URL | Description |
| --- | --- |
| https://app.appsflyer.com | AppsFlyer endpoint |
| app\_id | Application unique ID - Dynamic value changed per app promoted |
| pid | Media source name include **\_int** to identify<br>**integrated** network at AppsFlyer servers |
| c | Campaign name |

### Recommended attribution link parameters

| AppsFlyer Parameter | CAKE Macros | Description |
| --- | --- | --- |
| clickid | #oreqid# | Request ID of each user session - **Required** |
| af\_siteid | #affid# | ID of the Affiliate promoting the offer - **Optional** |

For a complete AppsFlyer parameter list, click [here](https://support.appsflyer.com/hc/articles/207447163)

For a complete CAKE macro list, click [here](https://support.getcake.com/support/solutions/articles/5000566463-tokens).

### Complete attribution link template

```http
https://app.appsflyer.com/com.appsflyer?pid=mediaName_int&clickid=#oreqid#
```

## Install and in-app event postbacks

### Global install postback

```http
https://{company-domain}.com/p.ashx?f=pb&r=(Click-ID)
```

### Global in-app event postback

```http
Click-ID
```

{Company-Domain} the network ID (domain) name provided by CAKE.

e= Set as **Event Tag** in the AppsFlyer dashboard for each App by the advertiser - This is the actual in-app event name from the application.

For complete CAKE postback structure Click Here

### AppsFlyer in-app events dashboard

<Image src="https://files.readme.io/3ce734c3930649fdb0b119cd6e12e135e6bcba19225862e9e93b93991451fc8b-360002326529.png" alt="IAEP.png" />

Additional attribution information can be added to the postback by request such as Country Code, Advertising ID, IDFA, and so on.

## Finalizing your registration

- If you have an integration with AppsFlyer, contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).
- If you don't have an integration with AppsFlyer, complete the ad Partners Registration application [here](https://www.appsflyer.com/partners-registration/).
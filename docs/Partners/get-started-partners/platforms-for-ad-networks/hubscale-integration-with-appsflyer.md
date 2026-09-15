---
title: "Hubscale integration with AppsFlyer"
excerpt: "Learn how ad networks using Hubscale can integrate with AppsFlyer by setting up attribution links and global postbacks."
---
At a glance: Learn how ad networks using Hubscale can integrate with AppsFlyer.

To initiate the integration you need to send AppsFlyer:

1. Your attribution link
2. Your postback (for installs and in-app events)

## Creating the attribution link

The attribution link consists of the below AppsFlyer base attribution link and additional macros added by the ad network.

See below AppsFlyers base attribution link with a detailed explanation per macro:

| AppsFlyer Base URL | Description |
| --- | --- |
| https://app.appsflyer.com | AppsFlyer endpoint |
| app\_id | Application unique ID – dynamic value changed per app promoted |
| pid | Media source name concatenated with \_int to identify integrated<br>networks |
| c | Campaign name |

See below what the complete attribution link should look like after you have added additional Hubscale macros:

```http
https://app.appsflyer.com/com.appsflyer?pid=mediaName_int&clickid={transaction_id}&af_siteid={affiliate_id}&af_sub5={offer_id}af_ad_id={offer_file_id}&advertising_id={google_aid}&idfa={ios_ifa}
```

[AppsFlyer complete list of parameters](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters)

## Global postbacks for installs and in-app events:

Hubscale has global postbacks for installs and in-app events:

For installs:

```http
https://companyname.156th.com/conv?transaction_id={publisher_ref_id}&ios_ifa={ios_ifa}&google_id={google_aid}&app_version={app_version}&language={language}&ext_country_code={country_code}&ext_city={city}&user_agent={user_agent}&user_ip={device_ip}&adv_revenue={revenue_usd}
```

For post-install events, Hubscale can record up to nine post-install events for the same Transaction ID. Nine global postbacks should be created as templates as shown below:

| Event number | URL template |
| --- | --- |
| Event 2 (event 1 is the install) | `https://companyname.156th.com/conv?transaction_id={publisher_ref_id}&ios_ifa={ios_ifa}&google_id={google_aid}&app_version={app_version}&language={language}&ext_country_code={country_code}&ext_city={city}&user_agent={user_agent}&user_ip={device_ip}&adv_revenue={revenue_usd}&level=2` |
| Event 3 | `https://companyname.156th.com/conv?transaction_id={publisher_ref_id}&ios_ifa={ios_ifa}&google_id={google_aid}&app_version={app_version}&language={language}&ext_country_code={country_code}&ext_city={city}&user_agent={user_agent}&user_ip={device_ip}&adv_revenue={revenue_usd}&level=3` |
| Event 4 | ... |
| ... | ... |
| Event 10 | `https://companyname.156th.com/conv?transaction_id={publisher_ref_id}&ios_ifa={ios_ifa}&google_id={google_aid}&app_version={app_version}&language={language}&ext_country_code={country_code}&ext_city={city}&user_agent={user_agent}&user_ip={device_ip}&adv_revenue={revenue_usd}&level=10` |

The Event tag is what is entered by the advertiser when mapping the events.

<Image src="https://files.readme.io/5fa9ea3c2428e0dce7ce6a8062ebdf9aca5b2f873cc4e3d76d815d83b3a72b64-360002301369.png" alt="In-App Events mapping interface" />

If the name of the partner using Hubscale is PARTNER, then the domain is normally: partner.156th.com.

Generic attribution link:

```http
https://app.appsflyer.com/com.appsflyer?pid=partnername_int&clickid={transaction_id}&af_siteid={pub_id}-{sub_pub_id}&advertising_id={google_id}&idfa={ios_ifa}
```

## Finalizing your registration

* If you have an integration with AppsFlyer, contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).
* If you don't have an integration with AppsFlyer, complete the ad Partners Registration application [here](https://www.appsflyer.com/partners-registration/).

## Mapping of AppsFlyer parameters and hubscale macros

| AppsFlyer Parameters | Hubscale Macros | Description |
| --- | --- | --- |
| pid | pub\_id | Media source name - for integrated partners and should not be changed. [More details](https://support.appsflyer.com/hc/articles/207447163#partner-id-pid-parameter). |
| c | campaign\_name | Campaign name - provided by the advertiser. |
| clickid | transaction\_id | The Ad network unique click identifier |
| af\_siteid | pub\_id | Ad Network publisher ID |
| af\_sub\_siteid | sub\_pub\_id | Ad Sub-Network/Publisher ID |
| af\_c\_id | campaign\_id | Campaign ID - provided by the advertiser |
| af\_adset | | Adset Name - provided by the advertiser. Adset is an intermediate level in the hierarchy between Campaign and Ad. [See more](https://support.appsflyer.com/hc/articles/207447163#levels-of-data-granularity) |
| af\_ad | adv\_name | Ad Name ([see more](https://support.appsflyer.com/hc/articles/207447163#levels-of-data-granularity)) |
| af\_ad\_id | adv\_id | Ad ID |
| af\_cost\_model | adv\_payout\_model | Cost model - CPI is currently the only supported model |
| af\_cost\_currency | adv\_payout\_currency | Currency code (example: USD) |
| af\_cost\_value | adv\_payout\_amount | Cost value |
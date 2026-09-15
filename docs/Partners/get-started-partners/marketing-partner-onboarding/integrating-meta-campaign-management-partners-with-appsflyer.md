---
title: "Integrating Meta campaign management partners with AppsFlyer"
excerpt: "Learn what data types Meta campaign management partners can receive from AppsFlyer, including install postbacks, in-app event postbacks, and user-level data policies."
---
**At a glance:** Learn what data types Meta campaign management partners can receive from AppsFlyer.

## Install postbacks

Upon conversion, AppsFlyer can return the following parameters:



| Parameter Name | Parameter Name Convention |
| --- | --- |
| Campaign Name | `{campaign\_name}` |
| Campaign ID | `{campaign\_id}` |
| Ad Set Name | `{adset\_name}` |
| Ad Set ID | `{adset\_id}` |
| Ad Group Name | `{adgroup\_name}` |
| Ad Group ID | `{adgroup\_id}` |
| Event time – Rounded up | `{timestamp}` |
| Unique AppsFlyer User ID | `{sha1-appsflyer-device-id}` |
| Device ID Hashed MD5 | `{md5IDFA\md4GAID}` |
| If the attribution was from a view | `{is-impression}` |
| Channel (Instagram, Meta Audience Network, Facebook, Messenger) | `{af\_channel}` |
| Geo | `{user\_country}` |


> 📘 **Example**
>
> http://mcmp\_postbackURL.........&mcmp\_ADset\_name =`{adset\_name}`


## In-app event postbacks

Upon In-app events, AppsFlyer can return the following parameters (in addition to the above):



| Parameter Name | Parameter Name Convention |
| --- | --- |
| Event Name* | `{event\_name}` |
| Event Value | `{event\_value}` |


> 📘 **Example**
>
> http://FMP\_postbackURL.........&eventname=`{event\_name}`


* The Meta campaign management partner can choose to receive the in-app event name as the advertiser configured it in AppsFlyer's SDK or to have the advertiser fill in a free text field per event.

## User-level data policy

* AppsFlyer cannot pass IDFA or Android/Advertising ID.

* AppsFlyer passes rounded-up installs/events timestamps to the closest hour.

For example: If an install happened at 4.32 pm and 42 seconds, we can pass 5 pm as the timestamp

* AppsFlyer can use a Random ID of its own creation to attach to events that ID shouldn’t be derived from the IDFA/Android ID and should be unique to Meta ads. The same random ID can be passed downstream for In-app event postbacks.

> 📘 **Note**
>
> Based on Meta terms sending postbacks is available only for companies obtaining the following badges: Ad Technology

> 📘 **Example**
>
> ![](https://support.appsflyer.com/hc/article_attachments/360001440909/mceclip0.png)
>
> For the full list of Meta campaign management partners, click [here](https://www.facebook.com/business/partner-directory/search?programBadges=ADTECH_FB.ADTECH_IG&solution_type=campaign_management).
---
title: "FOCUUS integration with AppsFlyer"
excerpt: "Learn how to integrate FOCUUS with AppsFlyer to receive attribution data about installs and in-app events using probabilistic modeling."
---
Ad networks that use FOCUUS can utilize the AppsFlyer Probabilistic modeling solution to receive attribution data about installs and in-app events.

## Creating your attribution link

The attribution link consists of the below AppsFlyer base attribution link and additional macros added by the ad network.

See below AppsFlyers base attribution link with a detailed explanation per macro:

| AppsFlyer Base URL | Description |
| --- | --- |
| https://app.appsflyer.com | AppsFlyer endpoint |
| app\_id | Application unique ID |
| pid | Media source name include \_int to identify integrated network at AppsFlyer servers |
| c | Campaign name |

### Recommended attribution link parameters

| AppsFlyer Parameter | FOCUUS Macros | Description |
| --- | --- | --- |
| **clickid** | **`{tid}`** | **Request ID of each user session** \- **Required** |
| af\_siteid | `{publisher\_id}` | ID of the Affiliate promoting the offer - Optional |

For a complete list of AppsFlyer parameters, [click here](/docs/about-link-structure-and-parameters#attribution-link-parameters).

FOCUUS allows an unlimited number of macros, and you can name them as you wish, [click here](http://support.focuus.com/knowledgebase/articles/827379-traffic-source-template-tokens-macros "Link: http://support.focuus.com/knowledgebase/articles/827379-traffic-source-template-tokens-macros").

### Complete attribution link template

`https://app.appsflyer.com/com.appsflyer?pid={traffic_source}&clickid={tid}&af_siteid={publisher_id}`

This attribution link is set on your FOCUUS campaign [destination](http://support.focuus.com/knowledgebase/articles/827784-adding-a-new-link "Link: http://support.focuus.com/knowledgebase/articles/827784-adding-a-new-link").

## Install and in-app event postbacks

To create your install and in-app event postbacks at **FOCUUS**

1. Create a [new event](http://support.focuus.com/knowledgebase/articles/827775-events "Link: http://support.focuus.com/knowledgebase/articles/827775-events") (Install and any other in-app events).
2. [Generate pixel](http://support.focuus.com/knowledgebase/articles/827766-s2s-integration) (postback) for implementation.
3. Copy the postback URL that appears in the box labeled [Server2Server Pixel](http://support.focuus.com/knowledgebase/articles/827766-s2s-integration "Link: http://support.focuus.com/knowledgebase/articles/827766-s2s-integration") **.**
4. Replace the TRANSACTION\_ID with AppsFleyr macro - “ **clickid**”

https://pixel.focuusing.com/event.php?type=imp& **tid=`{clickid}`**

**Optional Postback Parameters**

| FOCUUS Macros | Description | Example |
| --- | --- | --- |
| event\_value | Payout value for each type of event | https://pixel.focuusing.com/event.php?type=cpi&tid=`{Your\_TRANSACTION\_ID}&eid=49816&event\_value={25}` |

**Event name (Install, Registration, etc.) appears by default on the generated pixel. for example:**

* https://traffic.focuusing.com/ **install**?tid=`{TRANSACTION\_ID}`
* https://traffic.focuusing.com/ **conversion**?tid=`{TRANSACTION\_ID}`
* https://traffic.focuusing.com/ **ftd**?tid=`{TRANSACTION\_ID}`
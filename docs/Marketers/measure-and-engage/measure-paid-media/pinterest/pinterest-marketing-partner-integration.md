---
title: "Pinterest Marketing Partner Integration"
excerpt: "Learn how to enable Pinterest Marketing Partners (PMPs) to receive install data for users attributed to Pinterest."
table_of_contents: false
---
Every PMP must be an official PMP and must also be approved by AppsFlyer on the back-end.

For AppsFlyer to send a postback to the PMP the `af_mp=` parameter with the AppsFlyer account name as a value must be added to the attribution link.

**Example**

<Tabs>
<Tab title="Android">

```http
https://app.appsflyer.com/com.king.candycrushsaga?pid=pinterest_int&clickid={click_id}
&af_adset={ad_group_name}&af_adset_id={ad_group_id}&af_ad={creative_name}&af_ad_id=
{creative_id}&af_siteid={publisher}&c={campaign_name}&af_c_id={campaign_id}&af_ad=
{ad_group_id}&af_ad_id={creative_id}&sha1_advertising_id={sha1_advertising_id}&tracking=
{limit_ad_tracking}&appid={app_id}&timestamp={click_timestamp}&af_mp=bidalgo
```

</Tab>
<Tab title="iOS">

```http
https://app.appsflyer.com/id340954503?pid=pinterest_int&clickid={click_id}
&af_adset={ad_group_name}&af_adset_id={ad_group_id}&af_ad={creative_name}&af_ad_id=
{creative_id}&af_siteid={publisher}&c={campaign_name}&af_c_id={campaign_id}&af_ad=
{ad_group_id}&af_ad_id={creative_id}&sha1_advertising_id={sha1_advertising_id}&tracking=
{limit_ad_tracking}&appid={app_id}&timestamp={click_timestamp}&af_mp=bidalgo
```

</Tab>
</Tabs>

Supported PMP partners include:

- Bidalgo
- Bidsaas (Bidalgo)
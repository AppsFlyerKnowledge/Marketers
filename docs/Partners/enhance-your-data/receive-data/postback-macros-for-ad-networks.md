---
title: "Postback macros for ad networks"
excerpt: "As an ad network, you can define the content and endpoints of postbacks sent to you as part of your integration with AppsFlyer."
---
As an ad network, you can define the content and endpoints of postbacks sent to you as part of your integration with AppsFlyer. Postbacks relate to app user engagement like installs, in-app events, re-engagements, and so on.

Related integrated partner postback guides:

<Cards>
  <Card title="Advanced Privacy" href="https://support.appsflyer.com/hc/articles/360011316197-iOS14-Advanced-Privacy-postback-guide-for-ad-networks">
    iOS14 Advanced Privacy postback guide for ad networks
  </Card>
  <Card title="SKAdNetwork" href="https://support.appsflyer.com/hc/articles/360011502657-SKAdNetwork-ad-networks-integration-guide">
    SKAdNetwork ad networks integration guide
  </Card>
  <Card title="Rejected attribution postbacks" href="/docs/rejected-attribution-postbacks-to-integrated-partners">
    Rejected attribution postbacks to integrated partners
  </Card>
</Cards>

## Postbacks for ad networks

* **Postback configuration:** To request changes to your postback settings, use the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif), or contact your AppsFlyer partner development manager.
* **Postback types**: Postbacks are available for install and in-app events and blocked install and in-app events (due to fraud identified by Protect360 or in violation of targeting validation rules).

### Postback data sources

| Source | Description |
| --- | --- |
| [Attribution link parameters](http://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters) | Parameters provided by the partner on click and impression URLs<br>Example: click ID parameter on the attribution link - "&click\_id=CLICK\_ID" |
| Partner IDs in AppsFlyer | Unique IDs provided to the advertiser by the partner<br>Examples: app ID, account ID, user ID, network ID |
| SDK derived information | Information extracted from the device by the AppsFlyer SDK<br>Example: iOS device IDs can be extracted by using "&IDFA=(idfa)" on the postback |
| Derived by the AppsFlyer platform | Information derived by the AppsFlyer platform. |
| Protect360 and validation rules | Information about installs identified as fraud and installs violating campaign targeting rules, and their associated in-app events |

## Postback macros

When included in a postback, macros are replaced with user-relevant data. For example, to get the IP address of the user installing the app, include `country_code=(ip)` in the postback structure. Supported macros are listed in the following table:

The columns in the table below have the following meaning:

* **Source:** Where the data originates from.
  * Link: Attribution links
  * SDK: AppsFlyer SDK embedded in the app or server-to-server API
  * AF: After processing by AppsFlyer
* **Send all**: If yes, you can receive the data of installs and events attributed to other networks or organic. (Means not attributed to you).
* **[Base] Macros for all postbacks**: Macros relevant to install, in-app event, and rejected event postbacks
* **[Optional]** for in-app events and rejected events as indicated in the column (rejected, in-app)

### Macros—installs, in-app events, and rejected events

| Postback macro (name) | Source | Send all | Description | [Base] Macros for all postbacks | [Optional] In-app and rejected events |
| --- | --- | --- | --- | --- | --- |
| advertising\_id | SDK | Yes | User-resettable device ID, AKA GAID. Also available as: (sha1-advertiserId) | Yes |  |
| af\_ad | LINK | No | Ad Name ( [see more](https://support.appsflyer.com/hc/articles/207447163#levels-of-data-granularity)) provided by the advertiser/publisher | Yes | Yes |
| af\_ad\_id | LINK | No | Provided by the advertiser/publisher | Yes | Yes |
| af\_ad\_type | Link | No | Use the following naming convention:<br>- **text:** an ad unit containing only text, for example a search result<br>- **banner:** a basic format that appears at the top or bottom of the device screen<br>- **interstitial:** a full-page ad that appears during breaks in the current experience<br>- **video:** a standard video, that is non-rewarded<br>- **rewarded\_video:** an ad unit offering in-app rewards in exchange for watching a video<br>- **playable:** an ad unit containing an interactive preview of the app experience<br>- **sponsored\_content:** a link included in a piece of sponsored content, like an advertorial article<br>- **audio:** an audio ad | Yes | Yes |
| af\_adset | Link | No | - Provided by the advertiser/publisher.<br>- Adset is an intermediate level in the hierarchy between Campaign and Ad. [See more](https://support.appsflyer.com/hc/articles/207447163#levels-of-data-granularity) | Yes | Yes |
| af\_adset\_id | Link | No | Provided by the advertiser/publisher | Yes | Yes |
| af\_c\_id | Link | No | Provided by the advertiser/publisher | Yes | Yes |
| af\_siteid | Link | No | - Unique ID that identifies the publisher that displays the ad. [Learn more](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#site-id-parameter) | Yes | Yes |
| af\_subsite\_id | Link | No | - Ad sub-network/Publisher ID.<br>- If in addition to the main publisher (site ID), there is a sub-publisher, or you want to include additional info, such as ad type/placement within the app, like banner, interstitial, video, etc. use af\_sub\_siteid. For example: af\_sub\_siteid =ABCD\_4567 | Yes | Yes |
| af\_validated | AF | Yes | Indicates whether the purchase was successfully validated. Possible values: true or false. | Yes |  |
| af\_validation\_type | AF | Yes | Indicates the type of validation performed. Possible values: roi360\_purchase, roi360\_subscription, or receipt\_validation. | Yes |  |
| app\_id | SDK | Yes | The app ID as reported by the app | Yes |  |
| app\_name | SDK | Yes | App name set by the advertiser | Yes |  |
| app\_version | SDK | Yes | App version name set by the developer in the app code | Yes |  |
| appsflyer\_id | SDK | Yes | AppsFlyer unique identifier recorded upon conversion | Yes |  |
| att-0-1 | SDK | Yes | Possible values:<br>- 1: The ATT status is authorized or af\_authorized.<br>- 0: Any other ATT status. | Yes |  |
| att-status | SDK | Yes | The [ATT status](https://support.appsflyer.com/hc/articles/360014090597-ATT-implications-iOS-14-and-deprecation-of-LAT-#att-values) reported by iOS. Like authorized, not\_determined. <br>In some cases there is no value and "" is returned. | Yes |  |
| attributed\_touch\_type | SDK | No | Possible values: click, impression, TV, pre-install | Yes |  |
| blocked\_reason | AF | No | Fraud/validation rules reason | No | Rejected |
| blocked\_reason\_value | AF | No | Fraud/validation rules reason value (like site ID) | No | Rejected |
| blocked\_sub\_reason | AF | No | Fraud/validation rules sub-reason | No | Rejected |
| bundle\_id | SDK | Yes | iOS: Identification to match either a single app or a group of apps in iOS (See Apple developer bundle ID) Android: The app name | Yes |  |
| c | Link | No | Provided by the advertiser/publisher. Campaign names that exceed 100 characters in length are displayed on the dashboard as "c\_name\_exceeded\_max\_length" | Yes | Yes |
| country\_code | AF | Yes | Country Code using ISO 3166 (alpha-2) Example: US, CN. | Yes |  |
| event\_name | SDK | Yes | Name allocated to an event | No | In-app |
| event\_revenue | SDK | Yes | Event value reported by SDK using event\_revenue\_currency or currency selected by you. | No | In-app |
| event\_revenue<br />\_currency | SDK | Yes | The event revenue currency code reported in the event or the currency selected by you | No | In-app |
| event\_revenue\_USD | AF | Yes | Event value in USD | No | In-app |
| event\_time | SDK | Yes | Event time | No | In-app |
| event\_value | SDK | Yes | in-app event includes attributes with values, which can be sent entirely on the postback in JSON format. URL encoded using the (encode) macro. | No | In-app |
| idfa | SDK | Yes | User resettable advertising ID found on iOS devices Also available as: (sha1-idfa) | Yes |  |
| idfv | SDK | Yes | Unique identifier per user per vendor on IOS devices | Yes |  |
| imei | SDK | Yes | A unique number used to identify mobile phones | Yes |  |
| install\_time | SDK | Yes | Install timestamp | Yes |  |
| install\_unix\_ts | SDK | Yes | Install timestamp in unix format | Yes |  |
| is\_attributed | AF | Yes | A flag marking if the install or event is attributed to this media source | Yes |  |
| is\_contrib | AF | Yes | Indicates whether the ad network was among the top 3 contributors to an install.<br>- If the ad network did not win the attribution but is in the top 3 contributors, `is_contrib=1`.<br>- If the ad network won the attribution, `is_contrib=0`.<br>- If the ad network is not in the top 3 contributors, `is_contrib=0`. | Yes |  |
| is\_lat | SDK | Yes | Limit ad tracking (LAT): iOS: Starting iOS 14 LAT is deprecated by Apple. Determine user privacy status using ATT. In this case disregard is\_lat. Before iOS 14, if true, IDFA is not available and is set to 0. Android: When true, the user has opted-out of interest-based ads. This does not prevent the collection of GAID. | Yes |  |
| is\_organic | AF | Yes | If an install postback is sent for all media sources including organic, then the ad network will receive an indication as to whether an install was organic or non-organic. | Installs only |  |
| is\_primary\_attribution | AF | Yes | If false, see is\_retargeting. | No | In-app |
| is\_reinstall | AF | Yes | If true, the event is reported as [a reinstall](/docs/measure-reinstalls). |  |  |
| is\_retargeting | Link | No | Use in conjunction with is\_primary\_attribution. Learn more about [double attribution of retargeting events.](https://support.appsflyer.com/hc/articles/360016371077)<br>If true (1), the event is reported as part of a retargeting campaign and the media source is the retargeting media source.<br>If false (0) and is\_primary\_attribution is false, the event is part of a retargeting campaign but the media source referenced is the user attribution media source | No |  |
| language | SDK | Yes | Language (locale) reported by the device and set by the device OS. | Yes |  |
| oaid | SDK | Yes | User-resettable ID on some Android devices usually as an alternative to GAID | Yes |  |
| partner\_event\_id | AF | Yes | Name/ID of the corresponding event in the partner's platform | No | In-app |
| platform | SDK | Yes | Device platform: iOS, Android, or Windows Mobile | Yes |  |
| retargeting\_conversion\_type | AF | No | A flag marking if this is a re-attribution or re-engagement | Retargeting only |  |

### In-app event only macros

The examples that follow relate to in-app event postbacks available to partners.

#### Example

Event postback template "&event=(event)&json=(encode)" was translated to the following postback for a specific af\_purchase event:

```http
&event=af_purchase&json=%7B%22af_quantity%22%3A1%2C%22
af_revenue%22%3A%2212000%22%2C%22af_currency%22%3A%
22USD%22%2C%22af_content_id%22%3A%221107%22%2C%22
af_content_type%22%3A%22default_type%22%7D%0A
```

The decoded JSON value of this postback is

```json
{"af_quantity":1,"af_revenue":"12000","af_currency":"USD","af_content_id":"1107","af_content_type":"default_type"}
```

#### Encoded values

Postbacks may contain irregular characters, which are not alpha-numerical. To transfer these values correctly via postbacks, AppsFlyer URL-encodes non-alpha-numerical values.

To decode or encode a postback use an [encoding web service.](https://www.urldecoder.org/)

## Sample postbacks

### General install postback examples

<Tabs>
<Tab title="Android">

```http
http://YourCompanyDomain.com?site_id=(publisher_id)
&advertising_id=(advertiser_id)&android_id=(android_id)
&install_time=(install_unix_ts)
```

</Tab>
<Tab title="iOS">

```http
http://YourCompanyDomain.com?&site_id=(publisher_id)&
device_ip=(ip)&;idfa=(idfa)&install_time=(install_unix_ts)
```

</Tab>
</Tabs>

### General in-app event postback examples

<Tabs>
<Tab title="Android">

```http
http://YourCompanyDomain.com?site_id=(publisher_id)&
device_ip=(ip)&advertising_id=(advertiserId)&android_id=(android_id)&
install_time=(install_unix_ts)&event_name=(event_name)&currency=(currency)&
json=(event_value)
```

</Tab>
<Tab title="iOS">

```http
http://YourCompanyDomain.com?clickid=(clickid)&site_id=(publisher_id)&
device_ip=(ip)&idfa=(idfa)&install_time=(install_unix_ts)
&event_name=(event_name)&currency=(currency)&json=(event_value)
```

</Tab>
</Tabs>

### In-app event postback example

Event Parameters:

* Event Name: af\_revenue
* Event Revenue: 120.00
* Event Currency: USD
* Event Value: `{"af_quantity":1,"af_revenue":"120","af_currency":"USD","af_content_id":"1107","af_content_type":"default_type"}`

Postback:

```http
http://YourCompanyDomain.com?clickid=8594845&site_id=click123&device_ip=
38.166.144.142&advertising_id=121sxxxx-xxxx-xxxx-xxxx-52454bd7500b&
android_id=9aaeecc4455xxxxx&;install_time=1451923560&event_name=af_purchase&
currency=USD&revenue=120.00&json=%7B%22af_quantity%22%3A1%2C%22 />af_revenue
%22%3A%22120.10%22%2C%22af_currency%22%3A%22USD%22%2C%22af_content_id
%22%3A%221107%22%2C%22af_content_type%22%3A%22default_type%22%7D%0A
```
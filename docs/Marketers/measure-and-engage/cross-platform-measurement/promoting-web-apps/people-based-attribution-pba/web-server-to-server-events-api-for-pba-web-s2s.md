---
title: "Web Server-to-server events API for PBA (Web-S2S)"
excerpt: "Use the Web Server-to-Server (Web-S2S) events API to report events and conversions to PBA that aren't reported by the Web SDK."
---
The Web-S2S API for People-Based Attribution complements the [Web SDK](https://support.appsflyer.com/hc/articles/360001610038-PBA-web-SDK-integration-guide) allowing marketers to report events occurring on their websites but outside the scope of the Web SDK. For example, a visitor to the website (a web user), triggers an online payment event, processed by backend systems. After processing, the backend, using the S2S API, reports the event to AppsFlyer.

Events sent by the S2S API:

- are recorded similarly to events reported by the Web SDK
- are included in PBA dashboards if set as conversion events
- populate PBA raw data with _event_source field_ set to _web S2S_

<Image src="https://files.readme.io/4694c3141c85a0dc62a29a3ace7b1986fa4cf7140cc5cdc532553b66dc100ff9-360007753757.jpg" alt="Web S2S Infographic" />

## API use instructions

Create your API call using the sections that follow.

| No. | Item | Remarks |
| --- | --- | --- |
| 1 | Unique user ID | - Strive to give us the best unique user ID available. This has a significant impact on data analysis.<br>- Best practice is to send the customerUserId. If it's not available send the afUserId being the website cookie ID set by the WebSdk.<br>- At any time you associate your customer user ID ( [CUID](https://support.appsflyer.com/hc/articles/207032016-Customer-user-ID-field-)) with the [afUserId](https://support.appsflyer.com/hc/articles/360006997298-Web-Server-to-server-events-API-for-PBA-Web-S2S-#extracting-the-web-sdk-afuserid) send a setCuID() message with both IDs. |
| 2 | Timestamp | - AppsFlyer applies strict validation to incoming event timestamps:<br>  - **Late-arriving events:** Events are accepted with their original timestamp if they arrive within 24 hours of the day they belong to. **For example**, an event with a Monday timestamp (2025-08-18 23:59 UTC) will retain that timestamp if it is sent **anytime up until Tuesday** 23:59:59 UTC. If the same event is sent after Tuesday 23:59:59 UTC, the timestamp is overwritten with the server’s reception time.<br>    <br>  - **Future timestamps:** Events with a timestamp later than the actual arrival time are not permitted. Such timestamps are also overwritten with the server’s reception time.<br>- Timestamps are UTC-based. If necessary, convert from local time to UTC time before populating the parameter |
| 3 | Revenue and currency | You must populate _eventRevenueCurrency_ and _eventRevenue_ even if they are contained in the eventValue. Do so because we use them in our dashboards. |

### API basics

API implementation requires the following credentials available in the dashboard:

- Bundle ID (aka brand bundle ID)
- Web Dev key

**To get the credentials:**

1. In AppsFlyer, from the top menu, select **My Apps** > **View brand bundles**.
2. Copy and record the appropriate:
   - _**Brand bundle ID**_
   - _**Web dev key**_

#### Web S2S API basics

| | |
| --- | --- |
| Path | `https://webs2s.appsflyer.com/v1/bundleId/method`<br>- `bundleId`: Is the app bundle ID available in the dashboard. <br>- `method` being one of the following:<br>  - [event](https://support.appsflyer.com/hc/articles/360006997298#event-method): send for reportable backend events<br>  - [setCuId:](https://support.appsflyer.com/hc/articles/360006997298#setcuid-method) send when associating afUserId with your CUID |
| HTTP method | `POST` |
| Accepted content type | `application/json` |
| JSON payload limitation | JSON payload size: maximum 1KB |
| Rate limitation | POST limitation volume: 60,000 POSTs per minute. To increase the limit, contact your CSM. |
| TLS | - TLS 1.2 or later<br>- [Ciphers supported](https://support.appsflyer.com/hc/articles/360001288945#outgoing-messages-appsflyer-as-client) |

### setCuId method

| | |
| --- | --- |
| Method name | setCuId |
| Use case | On associating a CUID with a visitor to your website. For example, any time you match the web `afUserId` with your customer user ID. Doing so enables PBA to match data from various sources. This is similar to [setCustomerUserId](https://support.appsflyer.com/hc/articles/360001610038-PBA-web-SDK-integration-guide#identifying-users-using-customer-user-id-cuid) on the website. |
| Method path | _`https://webs2s.appsflyer.com/v1/bundleId/setcuid`_ |
| Payload | The JSON payload consists of the parameters listed here. All parameters are mandatory.<br>- [customerUserID](https://support.appsflyer.com/hc/articles/360006997298#setcuid-method)<br>- [afUserId](https://support.appsflyer.com/hc/articles/360006997298-Web-Server-to-server-events-API-for-PBA-Web-S2S-#extracting-the-web-sdk-afuserid)<br>- [webDevKey](https://support.appsflyer.com/hc/articles/360006997298#webdevkey) |

#### Curl example setCuId

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/setcuid' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
        "webDevKey" : "99999999-9999-9999-9999-999999999999"}'
```

### Event method

| | |
| --- | --- |
| Method name | event |
| Use case | Send |
| Method Path | `https://webs2s.appsflyer.com/v1/bundleId/event` |
| Detailed information | [Event method details](https://support.appsflyer.com/hc/articles/360006997298#event-method-details) section of this article contains payload details, Curl example, Python example and testing suggestions. |

## Event method details

### Payload parameters

Payload parameters are divided into user identifiers and event parameters.

- User ID: You must send at least one user ID parameter.
- Event: Send the mandatory parameters and optional parameters as needed.

#### User identifier parameters (send at least one parameter)

| User ID Parameter | Description |
| --- | --- |
| customerUserId | [Customer user ID (CUID)](https://support.appsflyer.com/hc/articles/207032016-Customer-user-ID-field-) is a unique identifier set by you.<br>- Use the identical identifier for events reported by any means to AppsFlyer. Meaning the same identifier is used in the Web SDK, mobile SDK, and S2S APIs.<br>- [Web SDK customer user ID](https://support.appsflyer.com/hc/articles/360001610038-Web-SDK-integration-guide#setting-customer-user-id-after-signup)<br>- Format: String<br>- Example: `"customerUserId" : "663274"`<br>- Populates raw data field: `customer_user_id` |
| afUserId | The unique user ID assigned by the Web SDK to every user that visits your website. You will need to pass the cookie value to your backend servers.<br>- Cookie details:<br> - Name: afUserId<br> - Value: set _afUserId_ to this value<br> - Domain: website-domain<br>- Example: `"afUserId" : "unique_cookie_uuid"`<br>- Populates raw data field: `af_web_id` |

#### Event parameters

| Parameter Name | Mandatory | Description |
| --- | --- | --- |
| webDevKey | Yes | Populate using the [web dev key](https://support.appsflyer.com/hc/articles/360006997298#getting-the-web-dev-key) available on the Dashboard.<br>- Example:`"webDevKey" : "ffffffff-ffff-ffff-ffff-ffffffffffff"` |
| eventType | Yes | Event attribute identifier for internal use by AppsFlyer. Always set to _EVENT._<br>- Example: `"eventType" : "EVENT"` |
| eventName | Yes | - We use this parameter to differentiate conversion and non-conversion events using the [event conversion list](/docs/pba-brand-bundles-and-settings#web-event-settings) set by the marketer in PBA settings. <br>- Ensure that you populate it with values consistent to the marketer's conversion logic.<br>- Format: String<br>- Example: `"eventName" : "web_purchase"`<br>- Populates raw data field: `event_name` |
| timestamp | No | Time the event occurred in milliseconds. Send as a [Unix timestamp](https://www.unixtimestamp.com/) having 13 digits.<br>- If no timestamp is sent, the time is set using the server time. <br>- **Events arriving late are timestamped using the current server time.** Late means arrival after midnight UTC on the day following the event. For example, an event occurring on Monday **must** be processed before midnight UTC Tuesday. <br>- Events having a timestamp in the future (relative to the current server time) are timestamped with the server time.<br>- Format: Int<br>- Example: `"timestamp" : 1584835200123`<br>- Populates raw data field: `event_time` |
| eventValue | No | Map of event parameters describing the event. Use this parameter to send rich in-app events like product SKU, line item price.<br>- **Note about revenue!** You can populate this parameter with revenue details. In addition, you must populate _eventRevenue,_ and _eventRevenueCurrency._<br>- Format: JSON<br>- Example: To send SKU ABC123, having a blue color and a unit price of $3.99 set eventValue to:<br><br>`{"Purchase": {"sku" : "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}}`<br>- Limitation **:** 1000 characters. Do not exceed this; it will be truncated. <br>- Populates raw data field: `event_value` |
| eventRevenueCurrency | No | Currency code of a revenue event, being a three-character [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) currency code.<br>- Default: USD<br>- Format: String<br>- Example: ` "eventRevenueCurrency" : "EUR"`<br>- Populates raw data field: `event_revenue_currency` |
| eventRevenue | No | Revenue (monetary value) assigned to an event.<br>**Note!** If revenue is reported in _eventValue,_ report it also in _eventRevenue_ and populate eventRevenueCurrency. <br>- Negative values permitted. For example, a refund.<br>- Format: Float <br>- Example values: `1` `1.2` `1234.20` `-1234.20`<br>- Populates raw data field: `event_revenue` |
| ~~eventCategory~~ | No | This parameter is deprecated and will be removed from the system at a future date. Use eventValue instead. |
| ~~eventLabel~~ | No | This parameter is deprecated and will be removed from the system at a future date. Use eventValue instead. |
| referrer | No | HTTP referrer<br>- Format: String<br>- Example:`"referrer" : "https://www.google.com/"`<br>- Populates raw data field: `http_referrer` |
| userAgent | No | [User-agent request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent) sent by the browser to the server.<br>- Where possible send this value as it assists in determining the device type. <br>- Format: String<br>- Example: `"userAgent" : "Chrome/80.0.3987"`<br>- Populates raw data field: `user_agent` |
| ip | No | User IP address<br>- Where possible send the value of this field. It assists in determining the [geo-location](https://support.appsflyer.com/hc/articles/360000847378-Determining-user-location-using-the-user-IP-address-) of the user.<br>- Format: String<br>- Example: `"ip": "192.0.2.1"`<br>- Populates raw data field: `ip` |

### Code Examples

<Tabs>
<Tab title="cURL">

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/event' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey" : "99999999-9999-9999-9999-999999999999",
    "ip" : "192.0.2.1",
	"eventType":"EVENT",
	"timestamp" : 1234567890123,
	"eventName":"my_web_event",
	"eventRevenueCurrency" : "EUR",
	"eventRevenue" : 1234.56,
	"eventValue": {
		"purchase":{
		 "shoes": "color",
		 "quantity" : "3",
		 "Revenue" : "1234.56",
		 "Currency" : "ZAR"
		}
	}
}'
```

</Tab>
<Tab title="Python">

```python
import requests
url = "https://webs2s.appsflyer.com/v1/bundleId/event"
payload = {
    "customerUserId": "1234567890abcdef",
    "afUserId": "9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey": "99999999-9999-9999-9999-999999999999",
    "ip": "192.0.2.1",
    "eventType": "EVENT",
    "timestamp": 1234567890123,
    "eventName": "my_web_event",
    "eventRevenenuCurrency": "EUR",
    "eventRevenue": 1234.56,
    "eventValue":
        {
            "purchase":
            {
                "shoes": "color",
                "quantity": "3",
                "Revenue": "1234.56",
                "Currency": "ZAR"
            }
        }
    }
headers = {
    'Accept-Encoding': 'application/json',
    'Content-Type': 'application/json'
}
response = requests.request("POST", url, headers=headers, json=payload)
print(response.text.encode('utf8'))
```

</Tab>
</Tabs>

### Testing

For testing purposes, send several events as follows:

1. Send an event.
2. Ensure that you get a 200 OK return code. If not, take corrective action using the return codes and error messages.
3. Wait for several hours after midnight UTC to see the reported event in PBA raw data. You must wait because PBA data is processed once a day.

## Additional information

### Getting the Web Dev Key

**To get the Web Dev Key:**

1. In AppsFlyer, go to the _**My Apps**_ tab.
2. Click _**View brand bundles.**_

<Image src="https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png" alt="GetWebDevKeyPba_us-en.pn" />

3. Copy the required **_Web Dev Key_.**

### Extracting the Web SDK afUserID

- The `afUserId`, is a unique identifier, set by the Web SDK when a user first visits your site.
- If you need `afUserId` use one of the methods that follow.

#### **Get afUserId from the HTTP cookie header**

- The `afUserId` is sent by the visitors browser on calls to your site.
- Extract it from the HTTP cookie header if needed.

#### **Viewing afUserId in the visitor's browser**

- View the `afUserId` in the visitor's browser, for troubleshooting and debugging purposes.
- For it to be available, the visitor needs to have first visited a page having the Web SDK at least once.
- The cookie containing `afUserId` is a first-party cookie in relation to your domain.
- The procedure that follows was prepared using Chrome 81. There may be some differences between various browsers and operating systems.

**To get the afUserId from the visitor's browser:**

1. In your browser, go to your website.
2. Right-click, select _**Inspect**_. The browser's inspect element window opens.

<Image src="https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg" alt="S2S_inspect.jpg" />

3. Go to the (A) _**Application**_ tab.
4. In the side menu, (B) expand Cookies.
5. Select your website. If it does not display, refresh the browser.
6. In the (C) _**filter**_ field, enter `afUserId`

The value of afUserID displays.

### Response codes

| Response code | Message | How to Handle |
| --- | --- | --- |
| 200 | OK | |
| 404 | Not found | - Check the endpoint <br>- Check that the Bundle ID is correct |
| 400 | Bad request | - There is an error in the JSON. See the error message for details. |

### Troubleshooting

- Symptom: HTTP return codes do not return

Solution: [Allowlist](https://support.appsflyer.com/hc/articles/207447093-AppsFlyer-IP-address-ranges-) AppsFlyer servers.

### Release notes

| Date | Endpoint Version\* | Notes |
| --- | --- | --- |
| 2020-05-12 | 1 | Initial release |
| 2020-05-24 | 1 | |

\* Version number relates to the endpoint version number. `https://webs2s.appsflyer.com/v1/method` 

[Web SDK release notes](https://support.appsflyer.com/hc/articles/360001610038-PBA-web-SDK-integration-guide)
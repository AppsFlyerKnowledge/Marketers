---
title: Web Server-to-server events API for PBA (Web-S2S)
excerpt: >-
  Use the Web Server-to-Server (Web-S2S) events API to report events and
  conversions to PBA that aren't reported by the Web SDK.
metadata:
  keywords:
    - SDK
    - Developers
    - pba
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2020-03-23T23:59:00Z'
  edited_at: '2025-08-20T09:36:30Z'
  id: 360006997298
  locale: en-us
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360006997298-Web-Server-to-server-events-API-for-PBA-Web-S2S
---
[![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/4694c3141c85a0dc62a29a3ace7b1986fa4cf7140cc5cdc532553b66dc100ff9-360007753757.jpg)](https://files.readme.io/4694c3141c85a0dc62a29a3ace7b1986fa4cf7140cc5cdc532553b66dc100ff9-360007753757.jpg)

## Web Server-to-server events API for PBA

The Web-S2S API for People-Based Attribution complements the [Web SDK](/docs/pba-web-sdk-integration-guide) allowing marketers to report events occurring on their websites but outside the scope of the Web SDK. For example, a visitor to the website (a web user), triggers an online payment event, processed by backend systems. After processing, the backend, using the S2S API, reports the event to AppsFlyer.

Events sent by the S2S API:

* are recorded similarly to events reported by the Web SDK
* are included in PBA dashboards if set as conversion events
* populate PBA raw data with *event\_source field* set to *web S2S*

## API use instructions

Create your API call using the sections that follow.

| No. | Item | Remarks |
| --- | --- | --- |
| 1 | Unique user ID | <ul><li>Strive to give us the best unique user ID available. This has a significant impact on data analysis.</li><li>Best practice is to send the customerUserId. If it's not available send the afUserId being the website cookie ID set by the WebSdk.</li><li>At any time you associate your customer user ID ([CUID](/docs/customer-user-id-field-cuid)) with the [afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid) send a setCuID() message with both IDs.</li></ul> |
| 2 | Timestamp | <ul><li>AppsFlyer applies strict validation to incoming event timestamps:</li></ul><ul><li>**Late-arriving events:** Events are accepted with their original timestamp if they arrive within 24 hours of the day they belong to. **For example,** an event with a Monday timestamp (2025-08-18 23:59 UTC) will retain that timestamp if it is sent **anytime up until Tuesday** 23:59:59 UTC. If the same event is sent after Tuesday 23:59:59 UTC, the timestamp is overwritten with the server’s reception time.</li><li>**Future timestamps:** Events with a timestamp later than the actual arrival time are not permitted. Such timestamps are also overwritten with the server’s reception time.</li></ul><ul><li>Timestamps are UTC-based. If necessary, convert from local time to UTC time before populating the parameter</li></ul> |
| 3 | Revenue and currency | You must populate *eventRevenueCurrency* and *eventRevenue* even if they are contained in the eventValue. Do so because we use them in our dashboards. |

<div id="api-basics" />

<Accordion title="API basics">

API implementation requires the following credentials available in the dashboard:

* Bundle ID (aka brand bundle ID)
* Web Dev key

**To get the credentials:**

1. In AppsFlyer, from the top menu, select **My Apps** > **View brand bundles*.***The list of bundles display.
2. Copy and record the appropriate:
   * ***Brand bundle ID***
   * ***Web dev key***

#### Web S2S API basics

| Path | `https://webs2s.appsflyer.com/v1/bundleId/method`<ul><li>`bundleId`: Is the app bundle ID available in the dashboard.</li><li>`method` being one of the following:<ul><li>[event](/docs/web-server-to-server-events-api-for-pba-web-s2s#event-method): send for reportable backend events</li><li>[setCuId:](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method) send when associating afUserId with your CUID</li></ul></li></ul> |
| --- | --- |
| HTTP method | `POST` |
| Accepted content type | `application/json` |
| JSON payload limitation | JSON payload size: maximum 1KB |
| Rate limitation | POST limitation volume: 60,000 POSTs per minute. To increase the limit, contact your CSM. |
| TLS | <ul><li>TLS 1.2 or later</li><li>[Ciphers supported](/docs/appsflyer-https-ssl-encryption-policy-support#outgoing-messages-appsflyer-as-client)</li></ul> |

</Accordion>

<div id="setcuid-method" />

<Accordion title="setCuId method">

| Method name | setCuId |
| --- | --- |
| Use case | On associating a CUID with a visitor to your website. For example, any time you match the web `afUserId` with your customer user ID. Doing so enables PBA to match data from various sources. This is similar to [setCustomerUserId](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid) on the website. |
| Method path | *`https://webs2s.appsflyer.com/v1/bundleId/setcuid`* |
| Payload | The JSON payload consists of the parameters listed here. All parameters are mandatory.<ul><li>[customerUserID](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method)</li><li>[afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid)</li><li>[webDevKey](/docs/web-server-to-server-events-api-for-pba-web-s2s#webdevkey)</li></ul> |

#### Curl example setCuId

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/setcuid' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
        "webDevKey" : "99999999-9999-9999-9999-999999999999"}
```

</Accordion>

<div id="event-method" />

<Accordion title="Event method">

| Method name | event |
| --- | --- |
| Use case | Send |
| Method Path | `https://webs2s.appsflyer.com/v1/bundleId/event` |
| Detailed information | [Event method details](/docs/web-server-to-server-events-api-for-pba-web-s2s#event-method-details) section of this article contains payload details, Curl example, Python example and testing suggestions. |

</Accordion>

## Event method details

<div id="payload-parameters" />

<Accordion title="Payload parameters">

Payload parameters are divided into user identifiers and event parameters.

* User ID: You must send at least one user ID parameter.
* Event: Send the mandatory parameters and optional parameters as needed.

#### User identifier parameters (send at least one parameter)

| User ID Parameter | Description |
| --- | --- |
| <span id="customeruserid"></span>customerUserId | [Customer user ID (CUID)](/docs/customer-user-id-field-cuid) is a unique identifier set by you.<ul><li>Use the identical identifier for events reported by any means to AppsFlyer. Meaning the same identifier is used in the Web SDK, mobile SDK, and S2S APIs.</li><li>[Web SDK customer user ID](/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup)</li><li>Format: String</li><li>Example: `"customerUserId" : "663274"`</li><li>Populates raw data field: `customer_user_id`</li></ul> |
| <span id="afuserid"></span>afUserId | The unique user ID assigned by the Web SDK to every user that visits your website. You will need to pass the cookie value to your backend servers.<ul><li>Cookie details:<ul><li>Name: afUserId</li><li>Value: set *afUserId*to this value</li><li>Domain: website-domain</li></ul></li><li>Example: `"afUserId" : "unique_cookie_uuid"`</li><li>Populates raw data field: `af_web_id`</li></ul> |

#### Event parameters

| Parameter Name | Mandatory | Description |
| --- | --- | --- |
| <span id="webdevkey"></span>webDevKey | Yes | Populate using the [web dev key](/docs/web-server-to-server-events-api-for-pba-web-s2s#getting-the-web-dev-key) available on the Dashboard.<ul><li>Example:`"webDevKey" : "ffffffff-ffff-ffff-ffff-ffffffffffff"`</li></ul> |
| <span id="eventtype"></span>eventType | Yes | Event attribute identifier for internal use by AppsFlyer. Always set to *EVENT.*<ul><li>Example: `"eventType" : "EVENT"`</li></ul> |
| <span id="eventname"></span>eventName | Yes | <ul><li>We use this parameter to differentiate conversion and non-conversion events using the [event conversion list](/docs/pba-brand-bundles-and-settings#web-event-settings) set by the marketer in PBA settings.</li><li>Ensure that you populate it with values consistent to the marketer's conversion logic.</li><li>Format: String</li><li>Example: `"eventName" : "web_purchase"`</li><li>Populates raw data field: `event_name`</li></ul> |
| <span id="timestamp"></span>timestamp | No | Time the event occurred in milliseconds. Send as a [Unix timestamp](https://www.unixtimestamp.com/) having 13 digits.<ul><li>If no timestamp is sent, the time is set using the server time.</li><li>**Events arriving late are timestamped using the current server time.** Late means arrival after midnight UTC on the day following the event. For example, an event occurring on Monday **must** be processed before midnight UTC Tuesday.</li><li>Events having a timestamp in the future (relative to the current server time) are timestamped with the server time.</li><li>Format: Int</li><li>Example: `"timestamp" : 1584835200123`</li><li>Populates raw data field: `event_time`</li></ul> |
| <span id="eventvalue"></span>eventValue | No | Map of event parameters describing the event. Use this parameter to send rich in-app events like product SKU, line item price.<ul><li>**Note about revenue!** You can populate this parameter with revenue details. In addition, you must populate *eventRevenue,* and *eventRevenueCurrency.*</li></ul><ul><li>Format: JSON</li><li>Example: To send SKU ABC123, having a blue color and a unit price of $3.99 set eventValue to:<br />`{"Purchase": {"sku" : "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}}`</li><li>Limitation: 1000 characters. Do not exceed this; it will be truncated.</li><li>Populates raw data field: `event_value`</li></ul> |
| <span id="eventrevenuecurrency"></span>eventRevenueCurrency | No | Currency code of a revenue event, being a three-character [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) currency code.<ul><li>Default: USD</li><li>Format: String</li><li>Example:  `"eventRevenueCurrency" : "EUR"`</li><li>Populates raw data field: `event_revenue_currency`</li></ul> |
| <span id="eventrevenue"></span>eventRevenue | No | Revenue (monetary value) assigned to an event.<br /><br />**Note!** If revenue is reported in *eventValue,* report it also in *eventRevenue* and populate eventRevenueCurrency.<ul><li>Negative values permitted. For example, a refund.</li><li>Format: Float</li><li>Example values: `1``1.2``1234.20``-1234.20`</li><li>Populates raw data field: `event_revenue`</li></ul> |
| <span id="eventcategory"></span>eventCategory | No | This parameter is deprecated and will be removed from the system at a future date. Use eventValue instead. |
| <span id="eventlabel"></span>eventLabel | No | This parameter is deprecated and will be removed from the system at a future date. Use eventValue instead. |
| <span id="referrer"></span>referrer | No | HTTP referrer<ul><li>Format: String</li><li>Example:`"referrer" : "https://www.google.com/"`</li><li>Populates raw data field: `http_referrer`</li></ul> |
| <span id="useragent"></span>userAgent | No | [User-agent request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent)sent by the browser to the server.<ul><li>Where possible send this value as it assists in determining the device type.</li><li>Format: String</li><li>Example: `"userAgent" : "Chrome/80.0.3987"`</li><li>Populates raw data field: `user_agent`</li></ul> |
| <span id="ip"></span>ip | No | User IP address<ul><li>Where possible send the value of this field. It assists in determining the [geo-location](/docs/determine-user-location) of the user.</li></ul><ul><li>Format: String</li><li>Example: `"ip": "192.0.2.1"`</li><li>Populates raw data field: `ip`</li></ul> |

</Accordion>

<div id="curl-example" />

<Accordion title="Curl example">

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

</Accordion>

<div id="python-example" />

<Accordion title="Python example">

```
''' using the requests python package, install using pip install requests  '''
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

</Accordion>

<div id="testing" />

<Accordion title="Testing">

For testing purposes, send several events as follows:

1. Send an event.
2. Ensure that you get a 200 OK return code. If not, take corrective action using the return codes and error messages.
3. Wait for several hours after midnight UTC to see the reported event in PBA raw data. You must wait because PBA data is processed once a day.

</Accordion>

## Additional information

<div id="getting-the-web-dev-key" />

<Accordion title="Getting the Web Dev Key">

**To get the Web Dev Key:**

1. In AppsFlyer, go to the ***My Apps***tab.
2. Click View brand bundles.

   [![GetWebDevKeyPba_us-en.pn](https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png)](https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png)
3. Copy the required***Web Dev Key*.**

</Accordion>

<div id="extracting-the-web-sdk-afuserid" />

<Accordion title="Extracting the Web SDK afUserID">

* The `afUserId`, is a unique identifier, set by the Web SDK when a user first visits your site.
* If you need `afUserId`use one of the methods that follow.

#### **Get afUserId from the HTTP cookie header**

* The `afUserId` is sent by the visitors browser on calls to your site.
* Extract it from the HTTP cookie header if needed.

#### **Viewing afUserId in the visitor's browser**

* View the `afUserId` in the visitor's browser, for troubleshooting and debugging purposes.
* For it to be available, the visitor needs to have first visited a page having the Web SDK at least once.
* The cookie containing `afUserId` is a first-party cookie in relation to your domain.
* The procedure that follows was prepared using Chrome 81. There may be some differences between various browsers and operating systems.

**To get the afUserId from the visitor's browser:**

1. In your browser, go to your website.
2. Right-click, select ***Inspect***The browser's inspect element window opens.

   [![S2S_inspect.jpg](https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg)](https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg)
3. Go to the (A) ***Application*** tab.
4. In the side menu, (B) expand Cookies.
5. Select your website. If it does not display, refresh the browser.
6. In the (C) ***filter*** field, enter `afUserId`  
   The value of afUserID displays.

</Accordion>

<div id="response-codes" />

<Accordion title="Response codes">

| Response code | Message | How to Handle |
| --- | --- | --- |
| 200 | OK |  |
| 404 | Not found | <ul><li>Check the endpoint</li><li>Check that the Bundle ID is correct</li></ul> |
| 400 | Bad request | <ul><li>There is an error in the JSON. See the error message for details.</li></ul> |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Troubleshooting">

* Symptom: HTTP return codes do not return  
  Solution: [Allowlist](/docs/appsflyer-server-ip-address-ranges-allowlisting) AppsFlyer servers.

</Accordion>

<div id="release-notes" />

<Accordion title="Release notes">

<table><caption>Web SDK release notes</caption><thead><tr><th>Date </th><th>Endpoint Version\*</th><th>Notes</th></tr></thead><tbody><tr><td>2020-05-12</td><td>1</td><td> Initial release</td></tr><tr><td>2020-05-24</td><td>1</td><td> </td></tr></tbody><tfoot><tr><td colspan="3">\* Version number relates to the endpoint version number. <code>https://webs2s.appsflyer.com/v1/<var>method</var></code></td></tr></tfoot></table>

</Accordion>

<div data-zendesk-anchors="web-servertoserver-events-api-for-pba=web-server-to-server-events-api-for-pba h_01HKW2YAW4HHYK27F41HC3B24Y=web-server-to-server-events-api-for-pba h_01HKW2YAW4DCESP3MNY9D4GTFK=api-use-instructions h_01HKW2YAW4Z6G8HEVJJHCVG9G3=api-basics h_01HKW2YAW4XDKZ3YGAHAP3AG2T=web-s2s-api-basics h_01HKW2YAW4YFK2WWKM0VB8AGNN=setcuid-method h_01HKW2YAW5SJFKGTNRGRKN6NCJ=curl-example-setcuid h_01HKW2YAW5A9TJGZG08K4ZW69C=event-method h_01HKW2YAW53H43SCYTDXAYBDHX=event-method-details h_01HKW2YAW5WDPMXDKA3X4HZBD2=payload-parameters h_01HKW2YAW5RR4Q2PCWC9717ACG=user-identifier-parameters-send-at-least-one-parameter h_01HKW2YAW5G46ZV4Z0CYEWB011=event-parameters h_01HKW2YAW56HZ0WYRWNBATB8WR=curl-example h_01HKW2YAW5A78VREGZEZ12XMPE=python-example h_01HKW2YAW59JSCCACGD2H153M5=testing h_01HKW2YAW5D4N3SYA625F10YFW=additional-information h_01HKW2YAW5HV506YV5328ME236=getting-the-web-dev-key h_01HKW2YAW52T0KME7P2CRQ6WBR=extracting-the-web-sdk-afuserid h_01HKW2YAW5FK04C3AWCXGP1XAW=get-afuserid-from-the-http-cookie-header h_01HKW2YAW5CT2WZ229KJD2FWYK=viewing-afuserid-in-the-visitors-browser h_01HKW2YAW5HTV9N4ZEJJ99RBN0=response-codes h_01HKW2YAW6MG7VNQJAB1Q37K6T=troubleshooting h_01HKW2YAW6RM6VJKFECT0ETGTG=release-notes" />

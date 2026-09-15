---
title: "Server-to-server events API for mobile (S2S-mobile)"
excerpt: "Send events from your servers to AppsFlyer to measure mobile events that occur outside the app."
---
<Image src="https://files.readme.io/2f228a03ca00df529e42bd033825a0dca595e99a537cadcfd5419754a29b5490-35863179575441.png" alt="S2S_us-en.png" />

## Server-to-server events API for mobile

For iOS apps, starting iOS 14, you must send the os (operating system) parameter.

The AppsFlyer platform attributes and records mobile app events sent by the AppsFlyer SDK and by APIs. Use the S2S API to report events that take place outside the app; for example, a user renews their subscription using your web interface. S2S events, once recorded, are available across the platform, including dashboards, raw data, and analytics. For PBA web events see [Web S2S for PBA.](https://support.appsflyer.com/hc/articles/360006997298-)

AppsFlyer populates S2S events with:

- Values sent in the S2S message
- Some AppsFlyer install attribution values like, install time and media source.

To send events via API, tell your developer to follow their [server-to-server events API instructions](https://dev.appsflyer.com/hc/reference/s2s-events-api3-post).

## Populating parameters

### Difference between organic and non-organic

When AppsFlyer processes S2S in-app events, attribution fields are populated by using the AppsFlyer ID to identify the associated install event that preceded the in-app events.

What this means is that some data that AppsFlyer associates with non-organic S2S in-app events, is not associated with organic S2S in-app events.

**Example**

For example, if you compare raw data reports of non-organic and organic S2S in-app events, non-organic events contain data that organic in-app events do not.

Non-organic in-app events include data about the media source, campaign, attributed touch type, and attributed touch time.

Organic in-app events, on the other hand, follow an organic install. Organic installs don't have data related to campaign, media source, attributed touch type, and install time.

### Mapping AppsFlyer ID with customer user ID (CUID)

Backend logic is required to obtain values to populate parameter. The following describes how you can get the AppsFlyer ID:

- The AppsFlyer ID is mandatory and is used to attribute events.
- It is generated when a user first installs the mobile app.
- So that you can map your CUID to the AppsFlyer ID, you must set the CUID in the app.

To make it easier for you to know which user performed which event, implement the flow that follows:

- [Set customer user ID](https://support.appsflyer.com/hc/articles/207032016) when the user installs the app.
- AppsFlyer raw data reports contain the CUID and AppsFlyer ID. Use one of the data delivery tools to get this or AppsFlyer Push API.
- Use the raw data reports to match the CUID with the AppsFlyer ID.
- The AppsFlyer ID is available in the SDK integrated into your app (Android/iOS).
- Map AppsFlyer ID to customer user ID in your internal systems (important for future use).

Once you map AppsFlyer ID with your CUID, you can match the user to events performed. You can then obtain the other values (event value, event currency, event time, etc.) and send the server to server in-app event.

### Fetching the AppsFlyer ID

`appsflyer_id` is a mandatory parameter in server-to-server event messages. AppsFlyer uses this parameter to attribute the event to the original device and attributed media source. You can get the ID using one of the following methods:

- From the mobile device by calling the AppsFlyer SDK API:

<Tabs>
<Tab title="Android native">

[getAppsFlyerUID](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#getappsflyeruid)

</Tab>
<Tab title="iOS native">

[getAppsFlyerUID](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#getappsflyeruid)

</Tab>
<Tab title="Unity">

[getAppsFlyerId](https://dev.appsflyer.com/hc/docs/api#getappsflyerid)

</Tab>
<Tab title="React Native">

[getAppsFlyerUID](https://dev.appsflyer.com/hc/docs/rn_api#getappsflyeruid)

</Tab>
</Tabs>

- From the AppsFlyer platform using one of the following: [Pull API,](/docs/pull-api-raw-data) [Push API,](https://support.appsflyer.com/hc/articles/207034356) Export [raw data installation.](https://support.appsflyer.com/hc/articles/209680773-Export-Data-Reports)

### Time stamping S2S events

<Image src="https://files.readme.io/2d9138cc505b0ab1bb106c00fb2d71bd1d070ee236d7f928c8b8b85afe14af59-35863166628497.png" alt="time stamping logic diagram" />

When S2S events arrive in bulk to AppsFlyer, they are timestamped according to their `eventTime` property values and arrival time. The `eventTime` property denotes the in-app event occurrence time.

On arrival, events are time-stamped as follows:

- If the `eventTime` parameter is not included in the event record, the event time is set to the HTTP message arrival time.
- Events arriving before 02:00 UTC are stamped with the `eventTime` value. Meaning, for events to be stamped with the `eventTime`, they must be reported either on the day of the event, or the following day until 02:00 UTC.
- Events that took place the previous day or earlier, arriving after 02:00 UTC, are stamped with the arrival time (the time of the API call).
- Events arriving with a future `eventTime` value (eventTime > arrival time):
  - If the reported `eventTime` and the arrival time are both on the same calendar day, the event is timestamped with the `eventTime` value.
  - If the reported `eventTime` is on the next calendar day, the event is timestamped with the arrival time.
- Events with invalid `eventTime` Value are stamped with the HTTP message arrival time.

**Example**

- An event is sent with `eventTime` = Monday 21:00.

| Arrived to AppsFlyer | AppsFlyer timestamp | Remark |
| --- | --- | --- |
| Tuesday 01:00 | Monday 21:00 | Arrived before close-of-business. Time is set to the `eventTime` value. |
| Wednesday 09:00 | Wednesday 09:00 | Arrived after close-of-business. Time is set to arrival time. |

### Sending negative revenue

Events having a negative revenue value can be sent. For example, if a purchase was canceled. The parameter `af_revenue` can have negative values to record this.

If you populate `af_quantity`, you might want to populate it with a negative value depending on your system logic. AppsFlyer doesn't make use of `af_quantity`.

### Including User Agent and IP address in S2S events

When sending S2S events to the `metaweb_int` endpoint, the payload must include the `ua` (User Agent) and `ip` (IP address) parameters. Meta requires these values to optimize campaign performance via the Conversions API (CAPI).

AppsFlyer includes `ua` and `ip` automatically for events reported through the SDK. For S2S events, advertisers must send these parameters explicitly in the request payload.

> 📘 Note
>
> In order to be measured in [Incrementality](/docs/incrementality-for-remarketing-overview), S2S events must include the advertising ID in their payload (IDFA for iOS, GAID for Android).

## Increasing the volume of data transactions

When using gradual scaling, AppsFlyer can support a high volume of transactions per second (TPS) based on auto-scaling solutions. For example:

- Start with 10K transactions per second (TPS) and scale gradually, based on 1-minute minimum intervals.
  - 00:00:00 - send 10K TPS (baseline)
  - 00:01:00 - increase to 12K TPS
  - 00:02:00 - increase to 14K TPS
  - 00:03:00 - increase to 16K TPS
  - 00:04:00 - increase to 18K TPS
  - …
- Implement a retry mechanism to be used when receiving errors.

## Troubleshooting

<Accordion title="Events aren't displaying in the dashboard">

- Endpoint: Verify that the endpoint used is correct.
- Verify that the payload contains the mandatory parameters. See [here](https://support.appsflyer.com/hc/articles/207034486#mapping-appsflyer-id-with-customer-user-id-cuid).
- Ensure that the AppsFlyer ID you are using to fire the event is a real appsflyer\_id and related to an actual app install. See [here](https://support.appsflyer.com/hc/articles/207034486#fetching-the-appsflyer-id).
- S2S events don't support multi-events in one S2S request. Each event must be sent as a separate event.
  - Events can be sent with asynchronous method to ease response time.
- In the overview dashboard, the date range relates to the app install date (LTV) and not to the event date.
  - Make sure you select the correct date range.
  - Make sure that the dashboard date range corresponds to the install date of the device (appsflyer\_id) and not the date of the event.
- Event raw data reports: the date range relates to the event date and not the install date.

</Accordion>

<Accordion title="Events don't contain revenue">

If you send S2S events but their revenue is not recorded, ensure that the JSON that you send is stringified. The most important part is the event value parameter in the JSON. It must be stringified as shown in the example that follows.

```json
"{\"af_revenue\":\"6\" ,\"af_content_type\":\"wallets\"}"
```

If it is not stringified, then the event value is not processed correctly and revenue is not recorded.

Revenue values must not be formatted in any way. They can contain a decimal point. Don't include currency signs or codes nor `,` delimiters. The revenue can be prefixed by a `-`

- Example valid values are: `123`, `-123.45`, `123.456`
- Example Illegal values: `1,234.56`, `1,234`

</Accordion>

<Accordion title="Not all fields are populated in S2S events">

S2S events' raw data fields are populated exclusively with the values sent in the S2S call. The following fields cannot be reported through the S2S API, and therefore are not populated for S2S events in raw data reports:

- WIFI
- Operator
- Language
- Device Model
- Device Category
- App Version: You can use `app_version_name`
- App Name

</Accordion>

<Accordion title="S2S in-app events are wrongly attributed as organic">

S2S events, such as login events, can arrive at AppsFlyer as soon as the app is installed and the SDK is started. However, if these S2S in-app events arrive before AppsFlyer completes the processing of the install event, which generally takes 20-30 seconds or more, they may be marked as unattributed organic events.

We recommend introducing a short delay before reporting S2S in-app events that occur immediately after the install to our servers.

</Accordion>
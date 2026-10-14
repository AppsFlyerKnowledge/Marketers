---
title: In-app events—Overview
excerpt: >-
  Record post-install in-app events (such as login, register, or in-app
  purchase) attributed to media sources and campaigns.
metadata:
  keywords:
    - ios
    - Rich
    - In-App
    - android
    - Advertisers
    - In app events
    - Marketers
    - inapp events
    - attribution
    - inapp
    - inapp events attribution
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2017-11-02T08:12:51Z'
  edited_at: '2026-10-07T08:30:43Z'
  id: 115005544169
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115005544169-In-app-events-Overview
---
## Why record in-app events?

In-app events provide insight into what is happening in your app and are the ideal tool to determine the value of app users and the **quality of traffic originating from different media sources**. Recording in-app events helps you measure key performance indicators (KPIs) such as ROI (Return on Investment) and LTV (Lifetime Value).

When users perform registrations, complete tutorials, add items to the shopping cart, or make purchases, the in-app event data can record the events with the details. The implementation of in-app events is mandatory for all post-install analysis purposes.

## About in-app events

An in-app event comprises an event name and can include event parameters. When you add event parameters to an in-app event, it is referred to as an in-app event. Event parameters provide you with more context and information about the event. For example, while it helps to know that a user made a booking, event parameters can provide details such as the purchase type, destination, and revenue.

![travel.png](https://files.readme.io/0ebe64e7aa3ccc40ef014c55ee3a91edf678e21b2d00a7f8be1298d6b494e925-30858351609617.png)

> 📘 **Tip**
>
> Want to know more about in-app events? Check out this short, informative [course on the AppsFlyer Learning Portal](https://elevate.appsflyer.com/learn/course/7774/play/18613/in-app-events-and-integrated-partners-part-1).

### Predefined and custom events

In-app events that you want to send require your developer to implement code where applicable in your app. Event names and event parameters are classified as follows:

* **Predefined**: These are event names and event parameters that are commonly used among different apps. We highly recommend using [predefined event names](/docs/in-app-events-event-structure#predefined-event-names) and [event parameters](/docs/in-app-events-event-structure#predefined-event-parameters) as much as possible for the following reasons:
  * Predefined naming allows for smooth mapping of events to partners.
  * If AppsFlyer decides to change the name of any event or event parameter, your implementation is backward compatible.
* **Custom:** These are event names and parameters that you define for specific user scenarios that occur in your app. You can use any custom event name or parameter name string, but keep in mind that custom events need maintenance by your developer. See [Tips](/docs/in-app-events-overview#tips) and [Limitations](/docs/in-app-events-overview#limitations).

## Revenue in in-app events

The information in the following few sections explains how you can send revenue events to AppsFlyer and map the parameters the events include. However, it's important to note that with a ROI360 subscription, you get the most accurate and up-to-date cost and revenue data available (including revenue data from in-app purchases, subscriptions, and ads). [Learn more about ROI360](/docs/roi360-guide-cost-and-revenue-data)

<Accordion title="Event revenue">

`af_revenue` is the default parameter for reporting revenue. Revenue sent in `af_revenue` feeds all revenue metrics across AppsFlyer products (dashboards, LTV, cohort, ROAS, ROI) and is included in postbacks to partners. Always use it with in-app events that represent actual revenue generation in your business logic.

If you also want to report revenue with your own logic applied, for example, after app store fees and tax deductions, you can additionally send `af_net_revenue`. It is an addition to `af_revenue`, not a replacement. See [Net revenue](#net-revenue) below.

* [Recording revenue in the SDK](/docs/basic-sdk-integration-guide#record-revenue)
* Recording Revenue in Unity

You can also record negative revenue when a user cancels a purchase or when you issue a refund. To record negative revenue, all you have to do is append the minus sign (-) to the revenue value that you pass to `af_revenue`

The revenue value must contain only numbers (and a decimal point, if required):

* **Don't**include any other characters or format the revenue value in any other way. This means no commas, currency signs, for example, ($), special characters, or text.
* AppsFlyer provides revenue value with **up to 5 decimal places of precision**.
* The range of this value should be -1,000,000 to 1,000,000 in dollars or the equivalent original currency amount. Values outside of this range are included in raw data reports but not in aggregate reports.
* Example: 1234.56
* When revenue is sent as a string, the value inside the quotation marks must be valid. For example: "1234.56".

> 📘 **Note**
>
> AppsFlyer displays the exact revenue as sent from the SDK in `af_revenue`. It does not include any calculations for VAT or app store commissions, etc., unless these were included by the developer on the SDK side prior to it being sent to AppsFlyer. If you want to report revenue after such deductions, send it additionally in `af_net_revenue` (see [Net revenue](#net-revenue)).

`af_currency` represents the currency that is stated in `af_revenue` (or `af_price`). If `af_currency` is missing from the event's parameters, AppsFlyer sends it with the default value "USD".

You can use `af_price` as a monetary parameter that is not counted as revenue (such as in an “Add to Cart” event). This parameter refers to the individual item price. The total amount of all purchases appears under the `af_revenue` parameter.

</Accordion>

<Accordion title="Net revenue">

The `af_net_revenue` parameter provides an optional, additional way to report revenue when you want to apply your own logic to the revenue amount, for example, revenue after app store fees, tax deductions, gross margin, or service fees.

`af_net_revenue` **does not replace** `af_revenue`. Keep sending `af_revenue` as usual and add `af_net_revenue` alongside it when you want net reporting.

* Currency follows `af_currency` (default USD), similar to `af_revenue`.
* Since there is no predefined SDK constant for `af_net_revenue`, you must send it as a custom parameter with the key `af_net_revenue`.
* Net revenue powers the Net metrics (Net revenue, Net ROI, Net ROAS, Net ARPU, and Net profit) in [My Dashboards](/docs/my-dashboards#metrics).

> 📘 **Note**
>
> If you use [ROI360 store revenue](/docs/about-roi360-store-revenue) `af_net_revenue` is populated automatically for in-app purchase and subscription events, so you do not need to send `af_net_revenue` for those events. Net revenue equals gross revenue minus app store fees and taxes.

</Accordion>

<Accordion title="Revenue currency">

It's important to understand how AppsFlyer handles currency settings and currency conversion.

AppsFlyer handles the difference between app settings currency and in-app events currency using currency conversion.

![revenue_normalization_flow.png](https://files.readme.io/f890d34168f92202c94da4bfa548bd0f471c98dec9c8d4282b2549f5878e9321-46334674326033.png)

The diagram above demonstrates the following process:

1. In-app events are sent - different currency for each event
2. AppsFlyer normalizes all currencies to USD
3. AppsFlyer processes revenue data
4. Revenue data in the dashboard is displayed in app settings currency
5. AppsFlyer populates revenue data in raw data reports in both event and app settings currency

AppsFlyer uses [Open Exchange Rates](https://openexchangerates.org/) for currency conversion. The exchange rate is updated on an hourly basis. Whenever AppsFlyer performs currency conversion, it uses the exchange rate of the last hourly update.

#### Currency conversion

<span id="h_01HDBZW9XERK3VN1GS8GHM911W"></span>**Example**

In your app settings, you set currency to GBP. A user from France purchases a product using your app. The price is quoted in EUR (€). The in-app event that you send to AppsFlyer looks like this:

```
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REVENUE,200);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE,"category_a");
eventValue.put(AFInAppEventParameterName.CONTENT_ID,"1234567");
eventValue.put(AFInAppEventParameterName.CURRENCY,"EUR");
AppsFlyerLib.getInstance().trackEvent(getApplicationContext() , AFInAppEventType.PURCHASE , eventValue);
```

In this case, AppsFlyer converts revenue from EUR to USD and then to GBP. Let's assume the exchange rate is €1 = $1.13. So €200 becomes $226.85. Next, AppsFlyer converts from USD to GBP. Let's assume the exchange rate is $1 = £0.78. So $226.85 becomes £176.92.

#### Currency display

[Currency is set in the app settings](/docs/app-settings#localization-currency). The currency that you set in the app settings, is the currency that appears in the dashboard. No matter what currency you send in-app events, the revenue in the dashboard always appears in the currency that you set in the app settings.

<span id="h_01HDBZW9XEQNG1RDH7A8H002ZD"></span>**Example**

Let's say that you send in-app events with different currencies than the one set in the app settings, or with no currency at all. In this example, currency in the app settings is set to **GBP**.

You send three in-app events to AppsFlyer.

1. Event A has revenue of **234** and **GBP** as currency
2. Event B has revenue of **171** and **EUR** as currency
3. Event C has revenue of **171** but **no currency** specified

#### Revenue data in the dashboard

The revenue that appears in the dashboard is the **converted value** from the in-app event currency to USD and then to the app settings currency.

If no currency is specified in the event, **AppsFlyer defaults to USD**. The dashboard displays the event and revenue as follows:

| In-Apps Events | Unique Users | Number of Actions | Revenue |
| --- | --- | --- | --- |
| A | 1 | 1 | £234 |
| B | 1 | 1 | £149.4 - converted from EUR to USD and then to GBP. |
| C | 1 | 1 | £132.9 - defaults to USD as no currency is specified. Converted from USD to GBP directly. |

#### Revenue data in raw data reports

If you set the currency to **GBP** in the app settings but send in-app events with different currencies, the raw data report shows revenue in both app settings currency and in-app event currency.

If you set the currency to **GBP** in the app settings but send in-app events without currency, the raw data report shows revenue in both app settings currency and in USD.

The in-app events raw data report displays the event and revenue as follows:

| Event | Event Revenue | Event Revenue Currency | Event Revenue GBP |
| --- | --- | --- | --- |
| A | 234 | GBP | 234 |
| B | 171 | EUR | 149.4 - converted from EUR to USD and then to GBP. |
| C | 171 | USD | 132.9 defaults to USD as no currency is specified. Converted from USD to GBP directly. |

</Accordion>

## Sending events

There are several ways to send in-app events to AppsFlyer:

* [**AppsFlyer SDK:**](/docs/sdk-integration-overview) This is the most common way to send events. You can send in-app events that record user actions in the app using the AppsFlyer in-app events API at the SDK level.
* [**Server-to-server (S2S) API:**](/docs/server-to-server-events-api-for-mobile-s2s-mobile) Use the server-to-server (S2S) API to send events that occur outside the mobile app, directly to AppsFlyer. For example, if you have a user who is active on both web and mobile interfaces, you can record events from both sources and attribute them to the same user in AppsFlyer. It can be either an in-app event or other events, such as website events, call-center events, or purchases in your brick-and-mortar store.
* [**Receipt validation**](/docs/purchase-and-subscription-validation-overview): This is a secure mechanism where the payment platform, for example, Apple and Google, validate that the in-app purchase took place as reported. Validating purchases is the primary tool to prevent fraudulent revenue events. It also helps you see what the real revenue is, and filters out incomplete in-app purchases.
* [**Hybrid apps:**](/docs/in-app-events-for-hybrid-apps) These apps combine native views and HTML content and can also record in-app events. However, because the SDK can only send events from the native side, developers have to forward all event data to native code.

## Setting up in-app events

The process of setting up in-app events requires that the marketer and the developer work together as follows:

| Step | Role | Task | Details |
| --- | --- | --- | --- |
| 1 | Marketer | Determine the in-app events that you want to measure. [Define](/docs/in-app-events-overview#defining-an-inapp-event) and communicate the [event names](/docs/in-app-events-event-structure#predefined-event-names) and [event parameters](/docs/in-app-events-event-structure#predefined-event-parameters) to your developer. | It is recommended to start with 3-5 events that you can use as KPIs to measure the quality of your users (for example, purchases, registration, and sharing). Event parameters are optional, and you can use any event parameter with any event name.<br /><br />See [Recommended events by business vertical](/docs/in-app-events-overview#recommended-events-by-business-vertical) for typical in-app events. |
| 2 | Developer | Implement code in your app where applicable. | Developer documentation is [here](https://dev.appsflyer.com/hc/docs/in-app-events-sdk). |
| 3 [Optional] | Marketer | Work with your developer to set the [Customer User ID field (CUID)](/docs/customer-user-id-field-cuid). | This field helps enrich in-app events data by cross-referencing AppsFlyer attribution data with your other data using the CUID as a key. |
| 4 [Optional] | Marketer | [Map events](/docs/in-app-event-postback-configuration#event-mapping) to relevant partners in the dashboard. | This is an ongoing task, depending on the partners you integrate with. |

<Accordion title="Defining an in-app event">

Once you determine the in-app events that you want to measure, use our [In-app event generator](https://evgen.appsflyer.com/) to define the events and parameters as follows:

1. Select an event name that is most suitable to the scenario you want to record.
2. Select the event parameters that you want to associate with the event. Choose parameters that will provide additional context to the event and enrich the data.
3. Download the completed file from the in-app event generator, and then share it with your developer.

<span id="h_01HDBZW9XFN2B8AC18VW99G8Z6"></span>**Example**

A marketer for an ecommerce app wants to record the type of content users view in order to better understand what categories are the most popular and connect product views with product sales.

The following table shows an example of the event structure the marketer passes to the developer:

<table><thead><tr><th>Event name</th><th>Event parameters</th><th>Parameter values</th><th>When is the event triggered?</th></tr></thead><tbody><tr><td rowspan="3">af_content_view</td><td>af_price</td><td>Product price</td><td rowspan="3"><span>When a user views a specific product details page</span></td></tr><tr><td><span>af_content_type</span></td><td><span>Name of the product category, for example, shoes</span></td></tr><tr><td><span>af_content_id</span></td><td><span>Product ID, for example, SKU</span></td></tr></tbody></table>

</Accordion>

<Accordion title="Recommended events by business vertical">

The following table provides links to articles that include examples and flows of the typical in-app events we suggest recording per vertical.

| Business vertical | Article title |
| --- | --- |
| ![InApp_Events_games.png](https://files.readme.io/b077409a6be4b2fe917978ce4646c38e5dce7babccb23a3395d38da879d7ccde-46334674329489.png) | [Recommended gaming app events](/docs/recommended-gaming-app-events) |
| ![InApp_Events_ecommerce.png](https://files.readme.io/05ed5dbfbc47a56b0bd0b780d8e1682d147a6fbde2153ad741b5f42a03ac1348-46334674333713.png) | [Recommended eCommerce app events](/docs/recommended-ecommerce-app-events) |
| ![InApp_Events_streaming.png](https://files.readme.io/dd262ea557b66aad0583b1c4aa58f38ac686e4e0a853bfc9aa8aa02532c81e53-46334666560017.png) | [Recommended entertainment app events](/docs/recommended-entertainment-app-events) |
| ![banking.png](https://files.readme.io/8db0cf094393a560239c2c622f201d038798bcc7c28ed6f791b9a19c697fa98e-46334674335633.png) | [Recommended finance and banking app events](/docs/recommended-finance-and-banking-app-events) |
| ![InApp_Events_lending.png](https://files.readme.io/b3ef67b1390852ea37db2e73af92d8750bb37b2c70839abba2638e20c23d0f31-46334666567185.png) | [Recommended P2P lending app events](/docs/recommended-p2p-lending-app-events) |
| ![education.png](https://files.readme.io/a797d05a1db9c815987db4f65d5fb520769e2b61efdaf73c9274a431c9b19d1c-46334666568209.png) | [Recommended online education app events](/docs/recommended-online-education-app-events) |
| ![InApp_Events_ride.png](https://files.readme.io/c8d61bcdf3c222aac97586c03f95fab8a9dd4a11711112e609451930d54468bb-46334666569873.png) | [Recommended ride-hailing app events](/docs/recommended-ride-hailing-app-events) |
| ![InApp_Events_flight.png](https://files.readme.io/7c866bcfe74ce340d04436f9065bacb50b871c812ee96011842dcc4c8070dfa4-46334666570641.png) | [Recommended flight booking app events](/docs/recommended-flight-booking-app-events) |
| ![InApp_Events_hotel.png](https://files.readme.io/0a9fc3b486c7ce9c7204427b665d796a6030aa625abac6737e2529dd6f755476-46334674345105.png) | [Recommended hotel booking app events](/docs/recommended-hotel-booking-app-events) |
| ![5669_Healthcare_icon_3.png](https://files.readme.io/78a16579f1e661fe0fd1b42625ccfb08fac114ad8caff79105fb3e0f1e4c0fd9-46334674349073.png) | [Recommended healthcare app events](/docs/recommended-healthcare-app-events) |
| ![telecommunications_icon.png](https://files.readme.io/3ae58c98d9eb0e2e5cab51a281ad0b7d51862651d876a9a6c2a52a0ed30a7680-46334674351761.png) | [Recommended telecommunication app events](/docs/recommended-telecommunication-app-events) |
| ![InApp_Events_eWallet.png](https://files.readme.io/a4530bf762ecdf3082590731542a7deff87cf539a082128e0378cf70196554bc-46334674353809.png) | [Recommended eWallet app events](/docs/recommended-ewallet-app-events) |
| ![soccer_ball.png](https://files.readme.io/9df8f3a86da52422c5114143e141fc525c4a45906fc32f6c523c6a66b1c0e9e5-46334666576273.png) | [Recommended sports betting events](/docs/recommended-sports-betting-events) |

</Accordion>

<Accordion title="View in-app event data">

In-app events are attributed to the media source responsible for the install throughout the lifetime of the user. Event data is presented as [Life Time Value or Activity data](/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports).

You can view your in-app event data in these locations:

* Dashboard overview page: Displays real-time LTV user acquisition (UA) performance. **Note**: This includes revenue divided between organic and non-organic users reported via in-app events, and retargeting revenue that is [double-attributed.](/docs/resolve-retargeting-double-attribution)
* Events page: Displays LTV in-app event performance across media sources
* [Activity page](/docs/activity-dashboard): Displays in-app activities for the selected date range.
* [Raw data in-app event report](/docs/raw-data-reporting-overview): Displays activity data, meaning, a chronological list of the actions performed by your entire user base. This report includes event parameter values, for example:

  ```json
  {
    "af_level":"10",
    "af_score":"3387",
    "arena":"7",
    "char_type":"paladin"
  }
  ```

  Note that raw-data reporting is a premium feature.

> 📘 **Note**
>
> In-app event parameter values are available exclusively in [raw-data in-app event reports](/docs/raw-data-reporting-overview#in-app-events). They are not displayed in the Overview, Event, or Activity dashboards, nor in Aggregate data reports.

</Accordion>

<Accordion title="Tips">

Keep in mind the following when defining event names and parameters in the app:

* For data consistency in raw-data reporting, we recommend defining and using the same in-app event names and structures across all platforms.
* Use a minimal number of events to make it easier to compare the quality of users coming from different sources.
* **It is important that you ensure the privacy of your users.** **Don't populate in-app event values with restricted data that can directly identify them**. **For example, email address, name, identity number, and in some locations postal code. For more information about restricted data, read the** [**services privacy policy**](https://www.appsflyer.com/legal/services-privacy-policy/).
* Note that AppsFlyer includes the IP address of devices during [engagements](https://www.appsflyer.com/services-privacy-policy/#engagementinformation). In some jurisdictions or use scenarios, the IP address can be regarded as personally identifiable information (PII). We use the IP address to derive the broad geographic location (city, district level) of the device but not the specific address. If needed, you can select to [mask IP addresses](/docs/apply-ip-masking-to-user-data) so that they don't appear in raw data reports.
* In-app events are the only source of revenue data in AppsFlyer. You can attach a specific revenue value to each event, and view it on your app's dashboard. Learn more about the [monetizing parameters](/docs/in-app-events-overview#revenue-in-in-app-events). ![revenue_data.png](https://files.readme.io/9ada01568583ef5eb7d39ca09b2ae9dd68afb9415859574f35c477cf46d6272c-46334666577425.png)

</Accordion>

<Accordion title="Limitations">

Keep in mind the following when defining event names and parameters in the app:

* We recommend using only lower-case alpha-numeric characters (a-z and 0-9) for your in-app event names. Event names are case-sensitive, meaning that af\_purchase and af\_PURCHASE are two different events in the raw data. However, in aggregate reports and dashboards (for example, Overview or Events), only lowercase letters are permitted, and therefore, they can be displayed as a single event.
* There is a cardinality limit of 300 unique events per day. [Learn more](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_events_limit)
* Unique users are only counted for the first 100 events after they install the app.
* Event names cannot begin with these characters: **" = + -**
* Event values should not contain the **+** character, except in encoded URLs or encoded as per [ASCII](https://www.w3schools.com/tags/ref_urlencode.ASP).
* Event names cannot contain empty spaces. You can use underlined spaces (low dashes) before or after the name of the event.
* Event values should not exceed 2,000 characters to avoid being shortened in raw data reports. However, if the event originates from the SDK, it is recommended to keep it under 1,000 characters to make sure that the payload is not truncated when sent in the HTTP request.
* If you include the referring URL as an event value, it must be [URL encoded](https://www.w3schools.com/tags/ref_urlencode.ASP).
* Meta ads have some limitations about event names and parameters. Read about the limitations [here](https://developers.facebook.com/docs/app-events/faq#limits).

</Accordion>

## FAQ

The following section includes various FAQ about in-app events.

<Accordion title="How do I use the revenue parameter?">

You can send revenue values with any parameter name and event. However, to register the revenue (including [negative revenue](/docs/in-app-events-overview#revenue-in-in-app-events)) in the AppsFlyer raw and aggregated data, you must use the `af_revenue` parameter. Always use it with in-app events that represent actual revenue generation in your business logic.

`af_currency` represents the currency that is stated in `af_revenue` (or `af_price`). If `af_currency` is missing from the event's parameters, AppsFlyer sends it with the default value "USD". For more information about the `af_revenue` parameter, see the [Revenue Attribution guide](/docs/in-app-events-overview#revenue-in-in-app-events).

If you also want to report revenue with your own logic applied, for example, after fees and taxes, send `af_net_revenue` as a custom parameter alongside `af_revenue`. `af_net_revenue` does not replace `af_revenue`. For more information, see [Net revenue](#net-revenue).

</Accordion>

<Accordion title="How does AppsFlyer attribute events?">

In-app events are attributed to the original media source of the app install.

Upon the install of an app (first app launch) AppsFlyer uses various [attribution methods](/docs/appsflyer-attribution-model#attribution-methods) to determine the attribution of the install. At the same time, the AppsFlyer SDK creates a new unique [AppsFlyer ID](/docs/about-device-identifiers#appsflyer-id), which is associated with the attribution details.

Every consequent in-app event performed by the same device in the app has this ID. This lets AppsFlyer attribute the event to the original media source. Advertisers can use this to follow the full user journey in their app.

Events of recently retargeted users might have [double attribution](/docs/resolve-retargeting-double-attribution).

AppsFlyer attributes events of attributed installs as **organic** when:

* The media source's terms [dictate deleting the user-level data](/docs/in-app-events-overview#how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations)
* The user deletes the app's stored data on the device, forcing the creation of a new AppsFlyer ID.

</Accordion>

<Accordion title="Are events recorded if a device is offline?">

If a user initiates an event when the internet connection is unavailable, AppsFlyer is still able to record it. This is how it works:

1. SDK sends the events to the AppsFlyer servers and waits for a successful response.
2. If the SDK doesn’t receive a successful response, the event is stored in the cache.
3. Once the next successful response is received, the stored event is sent to the server again.
4. If there are multiple events in the cache, they are sent to the server, one after the other.

> 📘 **Note**
>
> The SDK cache can store up to 40 events, meaning only the first 40 events that occur offline are saved. Everything that follows until the next successful response is discarded.
>
> The event time displayed in the raw data is the time the event is sent to AppsFlyer after the device goes online again. It is not the actual time the event takes place.

</Accordion>

<Accordion title="What are complex in-app events and how do I set them up?">

Complex in-app events let you send multiple items in a single API call. They're useful when you want to group several closely related user actions together, for example, adding multiple products to a cart in one session.

We recommend using the `af_order_info` object to send complex in-app events to supported ad networks. For details, see [Item-level order data for ad networks (af\_order\_info)](/docs/item-level-order-data-for-ad-networks-af-order-info).

**Example** (recommended format, one field per item array):

```json
{
  "af_order_info": {
    "sku": ["ID1", "ID2", "ID3"],
    "revenue": [4.99, 9.99, 2.50],
    "qty": [1, 1, 2]
  }
}
```

See [Item-level order data for ad networks (af\_order\_info)](/docs/item-level-order-data-for-ad-networks-af-order-info) for the full field list (up to 7 fields per item) and the alternative one-object-per-item format.

As an alternative, you can still structure the event using `af_content` as a JSON array. Each object in the array must include `id` and `quantity`. `af_content_list` is optional and can be omitted.

<span id="h_01KSMX2ECGTDXQP3G9PZW1PFQD"></span>**Example**

```json
{
  "af_revenue": 4.99,
  "af_currency": "USD",
  "af_order_id": "12345",
  "af_content": "[{\"id\":\"ID1\",\"quantity\":\"1\"},{\"id\":\"ID2\",\"quantity\":\"1\"},{\"id\":\"ID3\",\"quantity\":\"2\"}]"
}
```

> 📘 **Important!**
>
> If the `af_content` string exceeds 1,000 characters, AppsFlyer might send the event to Meta without the `fb_content` parameter. If `af_content_list` is also absent in that case, Meta receives no product identification data. Keep `af_content` under 1,000 characters for events that include many items.

For full details about sending complex in-app events to Meta, see [Send complex in-app events to Meta ads](/docs/meta-ads-in-app-event-mapping#send-complex-in-app-events-to-meta-ads).

**Note:** In AppsFlyer [Audiences](/docs/audiences-guide#limitations), arrays are not supported within event attributes, only numbers or strings.

</Accordion>

<Accordion title="Can I add multiple items to a single transaction?">

You can add multiple items to a single transaction. Instead of single values per event parameter, you can have an array of items describing the transaction, separated by commas. The format should be a JSON string.

<span id="h_01HDBZW9XFB9TAT8W4CGNP1892"></span>**Example**

In the same transaction, Mr. Smith purchases two identical shirts, one pair of shoes, and a hat from a US-based online store. The sequence in which each item is listed must be identical for each

```
"{\"af_content_id\": [\"123\",\"988\",\"399\"], \"af_quantity\": [\"2\",\"1\",\"1\"], \"af_price\": [\"25\",\"50\",\"10\"], \"af_revenue\": \"110\", \"af_currency\": \"USD\"}"
```

Multiple items are sent onward as an array in [postbacks](/docs/in-app-event-postback-configuration). Currently, Meta ads and X Ads can't parse array parameters correctly. To assist with this issue, AppsFlyer sums up the number of items (`af_quantity`) instead of sending it to these self-reporting networks (SRNs) as an array. In our example, Meta ads would get `af_quantity=4`.

> 📘 **Notes**
>
> * In AppsFlyer [Audiences](/docs/audiences-guide#limitations), arrays are not supported within event attributes, only numbers or strings.
> * Multiple items can be used with the following in-app events:
>   `af_add_to_cart`, `af_add_to_wishlist`, `af_tutorial_completion`, `af_initiated_checkout`, `af_purchase`, `af_rate`, `af_spent_credits`, `af_content_view`, `af_travel_booking`, `af_update`

</Accordion>

<Accordion title="How does AppsFlyer handle event deduplication?">

We have an in-app event deduplication mechanism. It checks all in-app events to see if there was an identical in-app event that came from the same appsflyer\_id less than 10 seconds beforehand. If such an event is found, the mechanism removes the duplicate.

Two events are considered identical if the following fields in both events are the same:

* Event name
* Event value
* App ID
* AppsFlyer ID

> 📘 **Note**
>
> Deduplication works only for in-app events that are sent from the SDK.
>
> S2S in-app events don’t get deduplicated.

</Accordion>

<Accordion title="How long does AppsFlyer retain user-level data, and what are the deletion obligations?">

AppsFlyer retains raw user-level data based on integration type and partner requirements. Aggregated data might be retained for up to five years.

Retention periods can vary across media sources and delivery methods (for example, Data Locker or Pull API), and might change due to legal, contractual, or partner obligations.

After deletion, events related to deleted users display as organic. Past aggregate data is not changed. For more information, see [Data retention and deletion obligations](/docs/user-level-data-retention#data-retention-and-deletion-obligations).

</Accordion>

<Accordion title="Do I need to add the OS (operating system) parameter to my events?">

* The Android SDK and iOS SDK automatically add the OS (operating system) parameter.
* For the [S2S API](/docs/server-to-server-events-api-for-mobile-s2s-mobile), starting July 1, 2021, you must send the OS (operating system) parameter for iOS apps. If you do not send this parameter, data is regarded as having come from an iOS 14.5 user, and this impacts the way [raw data is made available](/docs/apply-aggregated-advanced-privacy-framework).

</Accordion>

<Accordion title="How can I ensure event deduplication on the partner side?">

If the same event is also uploaded directly to the network (for example, by developing in house support to the conversions API of the partner), you can ensure the partner can deduplicate the event, by sending a similar `event_id` via the direct CAPI integration as well as via AppsFlyer. In order to do so, make sure to include a field called “af\_customer\_event\_id” within the `event_value field`, and make sure to send the same value in the `event_id` field sent to the partner directly on the advertiser end.

This solution is supported for `metaweb_int`, `tiktokweb_int`, `snapweb_int`, `pinterest_int`  and `pinterest_int`.

</Accordion>

## See also

* [In-app event postback configuration](/docs/in-app-event-postback-configuration)

<div data-zendesk-anchors="why-record-inapp-events=why-record-in-app-events h_01HDBZW9XEBTY13MG4AN93RNCD=why-record-in-app-events about-inapp-events=about-in-app-events h_01HDBZW9XEBDSDA9T5X5B6KGTG=about-in-app-events h_01HDBZW9XE3Z40JE9576C4XSF4=tip predefind-and-custom-events=predefined-and-custom-events 01J9XGXGC7R9B19MMX4CQV7DAY=predefined-and-custom-events revenue-in-inapp-events=revenue-in-in-app-events 01J9XGXGC990R3AG0R0XT9E5Y7=revenue-in-in-app-events h_01M43GXKW5NCRE5MJG45EG9AYX=note h_NETREVENUE0002=note-1 h_01HDBZW9XEMGA5RAW0DBBPV3FQ=currency-conversion h_01HDBZW9XE85YC3JHG58YYAB8F=currency-display h_01HDBZW9XEVWB9045N0YEVWE6Z=revenue-data-in-the-dashboard h_01HDBZW9XEGYFD3W9FT1N3ZGQW=revenue-data-in-raw-data-reports h_01HDBZW9XFESG6MP9QF1XCJKE6=sending-events setting-up-inapp-events=setting-up-in-app-events h_01HDBZW9XF13AGRCN2HJ18RHS2=setting-up-in-app-events 01JEWW8YB6A91VT8Z4PM9NCV00=note-2 h_01HDBZW9XF5H24H2HCJKKHCRTE=faq h_01HDBZW9XFCDMKNWJ75AWHC2Y0=note-3 h_01KSMX2ECGNMX39RD2F6ZHQEK4=important h_01HDBZW9XFJ68WSM3066NVRATS=notes h_01HDBZW9XFWKN7W90PSVMX73FS=note-4 h_01HDNZ708FN0N286R5HDQGMNGZ=see-also" />

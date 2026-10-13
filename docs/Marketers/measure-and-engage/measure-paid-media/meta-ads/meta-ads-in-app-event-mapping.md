---
title: "Meta ads in-app event mapping"
excerpt: "Send your app's rich in-app events from AppsFlyer to Meta ads."
x-zendesk:
  id: 4410480904081
  url: https://support.appsflyer.com/hc/en-us/articles/4410480904081-Meta-ads-in-app-event-mapping
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Meta ads
  section_id: 6551109855761
  position: 4
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: [Facebook, Advertisers, facebook, Localize]
  promoted: false
  comments_disabled: true
  created_at: '2021-11-09T09:57:19Z'
  edited_at: '2026-09-10T11:15:42Z'
---
## Meta in-app events mapping

Advertisers map their in-app events, SDK or Servers-to-servers, to Meta predefined events. Advertisers can also send Meta postbacks about each [app launch](/docs/measure-sessions) or any known [app uninstall](/docs/measure-uninstalls#mapping-the-uninstall-event).

This enables advertisers to utilize Meta's advanced optimization capabilities, as well as build Custom and Lookalike Audience segments.

### Predefined event mapping

Meta ads offers a [wide range of events](https://developers.facebook.com/docs/app-events/getting-started-app-events-android#event-names) that are already predefined and can be mapped.

Find [here](/docs/in-app-events-event-structure) the list of **rich in-app events** that can be sent to Meta with additional parameters providing **extra information about the quality of events**.

Learn more about [mapping events on Meta](/docs/meta-ads-integration-setup#inapp-event-mapping).

[![In-app_event_postbacks_en-us.png](https://files.readme.io/ea80246ce8005c4150c70790aefb26aa6a73b5b5ae0eb07f90dcad8b50f2f1a8-37750374219153.png)](https://files.readme.io/ea80246ce8005c4150c70790aefb26aa6a73b5b5ae0eb07f90dcad8b50f2f1a8-37750374219153.png)

Note that there's no predefined event for sending uninstalls to Meta ads. To send uninstalls, use a [custom event](/docs/meta-ads-in-app-event-mapping#custom-inapp-events-mapping).

Below is the list of other predefined Meta events that don't have additional parameters:



| Meta event identifier | Description | Recommended AppsFlyer SDK name |
| --- | --- | --- |
| Donate | The donation of funds to your organization or cause. | af\_donate |
| Schedule | The booking of an appointment to visit one of your locations. | af\_schedule |
| SubmitApplication | The submission of an application for a product, service or program you offer, such as a credit card, educational program, or job. | af\_submit\_application |
| FindLocation | When a person finds one of your locations via web or app, with an intention to visit. For example, searching for a product and finding it at one of your local stores. | af\_find\_location |
| Contact | A telephone or SMS, email, chat or other type of contact between a customer and your business. | af\_contact |
| CustomizeProduct | The customization of products through a configuration tool or other application your business owns. | af\_customize\_product |
| `Adimpression`—for Android  <br />`Fb_mobile_purchase`—for iOS | Optimizes ad revenue on the Meta ads platform. [See details below](#mapping-ad-revenue-data-for-campaign-optimization). | af\_ad\_revenue |



### Mapping ad revenue data for campaign optimization

Meta ads can optimize your campaigns based on your ad revenue data. This is done by mapping the af\_ad\_revenue event to the following Meta ads event:



<table><colgroup><col/><col/><col/><col/></colgroup><thead><tr><th><strong>Event name in AppsFlyer</strong></th><th><strong>Platform </strong></th><th><strong>Mapped to partner event</strong></th><th><strong>Meta ads optimization based on:</strong></th></tr></thead><tbody><tr><td rowspan="2"><br/>af_ad_revenue</td><td>Android</td><td>Adimpression</td><td>Specific ad revenue</td></tr><tr><td>iOS</td><td>fb_mobile_purchase</td><td>In-app purchases</td></tr></tbody></table>



#### Availability limitations

* Currently, optimization via the **Adimpression** event is available only for:
  * Android apps. iOS apps can continue sending ad revenue data using the *fb\_mobile\_purchase* event.
  * Selected Meta ads accounts, as per Meta's criteria. When grayed out, [eligibility criteria may not be met](https://www.facebook.com/business/help/571188993373447?id=561906377587030).
* The *af\_ad\_revenue* event is available for plans with an [ROI360 advanced subscription](/docs/roi360-guide-cost-and-revenue-data) only. Additionally, you need the [impression-level via SDK ad revenue integration type](/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution).
  * Non-ROI360 plans can send ad revenue data using other event names.

### Custom in-app events mapping

AppsFlyer allows you to map any custom in-app event to send to Meta, by using the CUSTOM Meta Event Identifier option.

The event name and the event value (including the event parameters) configured in the SDK are forwarded to Meta, as is, and displayed under its original AppsFlyer SDK event name - not as "custom".

Note that you are able to [use these events to optimize your campaigns](https://www.facebook.com/business/help/2308889442692949?id=1716638325041491).

[![](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)

### Automatic parameter mapping with the custom event

Through the AppsFlyer deep integration with Meta, many of the AppsFlyer standard SDK event parameters are automatically mapped to Meta's predefined parameters. For example, the **af\_revenue** parameter is converted to the **\_valueToSum** parameter in Meta, which allows you to send a revenue per event that can be measured and optimized in Meta.

> 📘 **Note**
>
> Automatic parameter mapping can differ between CUSTOM and predefined events.
>
> For [predefined events](/docs/in-app-events-event-structure), **af\_price** is mapped to **\_valueToSum** in some cases (for example, `fb_mobile_add_to_cart`). In other cases, **af\_revenue** is mapped to **\_valueToSum** (for example, in `fb_mobile_purchase`).
>
> For events mapped to CUSTOM, **af\_price** is always mapped to **fb\_price**, and **af\_revenue** to **\_valueToSum**.


The following table details all the AppsFlyer event parameters, which when mapped through the CUSTOM event to Meta, are automatically mapped to Meta parameters.



| AppsFlyer Parameter | Meta Parameter |
| --- | --- |
| af\_city | fb\_city |
| af\_class | fb\_travel\_class |
| af\_content | fb\_content |
| af\_content\_id | fb\_content\_id |
| af\_content\_list | fb\_content\_id |
| af\_content\_type | fb\_content\_type |
| af\_country | fb\_country |
| af\_currency | fb\_currency |
| af\_date\_a | fb\_checkin\_date |
| af\_date\_b | fb\_checkout\_date |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date |
| af\_departing\_departure\_date | fb\_departing\_departure\_date |
| af\_description | fb\_description |
| af\_destination\_a | fb\_origin\_airport |
| af\_destination\_b | fb\_destination\_airport |
| af\_destination\_list | fb\_destination\_ids |
| af\_hotel\_score | fb\_hotel\_score |
| af\_level | fb\_level |
| af\_max\_rating\_value | fb\_max\_rating\_value |
| af\_num\_adults | fb\_num\_adults |
| af\_num\_children | fb\_num\_children |
| af\_num\_infants | fb\_num\_infants |
| af\_order\_id | fb\_order\_id |
| af\_payment\_info\_available | fb\_payment\_info\_available |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops |
| af\_preferred\_price\_range | fb\_preferred\_price\_range |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings |
| af\_price | fb\_price |
| af\_quantity | fb\_num\_items |
| af\_region | fb\_region |
| af\_registration\_method | fb\_registration\_method |
| af\_returning\_arrival\_date | fb\_returning\_arrival\_date |
| af\_returning\_departure\_date | fb\_returning\_departure\_date |
| af\_revenue | \_valueToSum |
| af\_search\_string | fb\_search\_string |
| af\_success | fb\_success |
| af\_suggested\_destinations | fb\_suggested\_destinations |
| af\_suggested\_hotels | fb\_suggested\_hotels |
| af\_travel\_end | fb\_travel\_end |
| af\_travel\_start | fb\_travel\_start |
| af\_user\_score | fb\_user\_score |



#### Predefined events automatic mapping to the `_valueToSum` parameter

For predefined events, the Meta parameter `_valueToSum` is mapped either to the `af_price` or to the `af_revenue` parameters.

The following table details this mapping for all predefined Meta events with the `_valueToSum` parameter:



| **Meta event** | **\_valueToSum mapped to** |
| --- | --- |
| fb\_mobile\_level\_achieved | none |
| fb\_mobile\_add\_payment\_info | none |
| fb\_mobile\_add\_to\_cart | af\_price |
| fb\_mobile\_add\_to\_wishlist | af\_price |
| fb\_mobile\_complete\_registration | none |
| fb\_mobile\_tutorial\_completion | none |
| fb\_mobile\_initiated\_checkout | af\_price |
| fb\_mobile\_purchase | af\_revenue |
| fb\_mobile\_rate | af\_rating\_value |
| fb\_mobile\_search | af\_revenue |
| fb\_mobile\_spent\_credits | af\_price |
| fb\_mobile\_achievement\_unlocked | none |
| fb\_mobile\_content\_view | af\_price |
| StartTrial | af\_price |
| Subscribe | af\_revenue |



### Send complex in-app events to Meta ads

As of September 2026, we recommend using the new `af_order_info` object to send complex in-app events – events with multiple items – to Meta Ads. This object lets advertisers share complex in-app events with multiple supported networks. For more information, see [Item-level order data for ad networks (af\_order\_info)](/docs/item-level-order-data-for-ad-networks-af-order-info).

When you use `af_order_info`, AppsFlyer sends the item information to Meta under the `fb_contents` event field, which supports SKU, quantity, and revenue per item.

As an alternative, you can still use a structured `af_content` array. Each object in the array must include `id` and `quantity` to ensure proper postback handling.

`af_content_list` is optional. When it is absent, Meta falls back to the `fb_content` field (mapped from `af_content`) to identify product IDs. As long as the `af_content` JSON includes an `id` field in each object, Meta can parse and extract content IDs from it.

If you do include `af_content_list`, do not also include `af_content_id` in the same event. Both parameters map to `fb_content_id`, and only one should be populated to prevent conflicts.

> 📘 **Note**
>
> `fb_content_id` is important for product-level use cases such as matching events to catalog items for Advantage+ Catalog Ads and Dynamic Ads, product-level performance reporting, and product-based optimization signals. For general conversion optimization based on event count and value, campaigns work without it.

> 📘 **Example, unified format compatible with Meta and TikTok**
>
> ```json
> {
>   "af_revenue": 4.99,
>   "af_currency": "USD",
>   "af_order_id": "12345",
>   "af_content": "[`{\"id\":\"ID1\",\"quantity\":\"1\"},{\"id\":\"ID2\",\"quantity\":\"1\"},{\"id\":\"ID3\",\"quantity\":\"2\"}`]"
> }
> ```


This format works for both Meta and TikTok. TikTok also reads `id` values from the `af_content` field, so a single payload is sufficient when postbacking to both networks.

> 📘 **Important!**
>
> If the `af_content` parameter exceeds 1,000 characters, AppsFlyer may send the event to Meta without the `fb_content` parameter. If `af_content_list` is also absent in that scenario, Meta receives no product identification data. Keep `af_content` under 1,000 characters for events that include many items.


For more details about structuring complex in-app events, see the [In-app events: Overview](/docs/in-app-events-overview#what-are-complex-inapp-events-and-how-do-i-set-them-up) article.

## Event and parameter limitations

The following limits apply to [events you send to Meta ads](https://developers.facebook.com/docs/app-events/faq#limits):

* The following characters are not allowed:
  * Colon (:)
  * Period (.)
  * Non-Latin (English) character sets: As of January 12, 2020, Meta rejects Chinese characters. AppsFlyer has not tested other character sets, and you should use them only after verifying with Meta if they support them in postbacks.
* Event names are case-sensitive. To avoid discrepancies, make sure you use the correct case in the event names for all media sources and app versions.
* Maximum number of parameters: 25.
* Length of event names and parameters: 2–40.
* Maximum parameter length: 100 characters.
* Maximum parameter length for the af\_content parameter: 1000 characters.
* Characters permitted: Alphanumeric characters, underscores, hyphens, or spaces. Don't use non-Latin (English) characters. Using non-Latin letters results in inconsistent results.

Considerations regarding in-app event naming:

* Event names on AppsFlyer can be named the same as Meta event names (for example, fb\_price), however, these should not be sent as CUSTOM events to Meta.  
  **To keep on the safe side, refrain from naming events the same as Meta event names.**
* To perform in-app events postback mapping with Meta, get events data from all sources, including organic.

> 📘 **Important!**
>
> With the exception of the above parameters, AppsFlyer sends the CUSTOM events data **as is** to Meta. It is the responsibility of the app owner to verify the event data is according to Meta requirements, using valid Meta parameters (see the table above). Otherwise, these parameters aren't sent to Meta.
---
title: Recommended eCommerce app events
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-04-19T06:32:18Z'
  edited_at: '2025-12-02T11:55:23Z'
  id: 360019347957
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360019347957-Recommended-eCommerce-app-events
---
> **At a glance:** Measure the quality of your users throughout their user journey by recording these suggested in-app events for your eCommerce app.

## <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="67px" /> eCommerce

eCommerce apps allow buyers to easily search for and buy goods online. The typical events that we suggest recording are search, purchase, adding to cart, and adding to wishlist.

Recording events can help you determine:

* The most popular categories
* What buyers are searching for
* How many buyers completed a checkout
* How many buyers are recurring buyers and how many are just one-time buyers

> 🚧 **Important!**
>
> * Make sure to read the <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#setting-up-in-app-events">instructions</Anchor> for marketers about implementing in-app events.
> * To streamline the implementation process, use our <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce">In-app event generator</Anchor>. This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are <Anchor target="_blank" href="https://evgen.appsflyer.com/?vertical=ecommerce&view=code">code samples</Anchor> for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">**AppsFlyer developer hub**</Anchor>.
>
> For more information about recording in-app events, see the <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview">In-app events guide</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events e-Commerce_app_user_journey" src="https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png" />

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the eCommerce vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Complete registration (af_complete_registration)">

**Purpose**

Learn how many users installed the app and completed the signup process, and what signup methods your users prefer.

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Type of signup method | Email, Meta ads |

</Accordion>

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Purpose**

Understand the retention of your registered users

**Trigger**

When the user successfully logs in

**Event parameters**

Can be sent without any additional parameters

</Accordion>

<div id="search-af_search" />

<Accordion title="Search (af_search)">

**Purpose**

Learn what users are looking for, and which search results are the most relevant and lead to a purchase.

**Trigger**

One of the following:

* When the user clicks on the search button
* When the user lands on the search results page

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_search\_string | Search term | Red dress, running shoes |
| af\_content\_list | List of content IDs | 001, 092 |

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Content view (af_content_view)">

**Purpose**

Determine the view rate of specific products. This event can help you:

* Correlate product views with product sales
* Understand what categories are the most popular according to product views
* See the correlation between buyers' currency and the products they view

**Trigger**

When the user views a specific product details page

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | Product price | 2000 |
| af\_content | International Article Number (EAN) when applicable, or other product or content identifier<br /><br />**Required parameter for Meta ads dynamic ads** | ABC123 |
| af\_content\_id | Product ID<br /><br />**Required parameter for Meta ads dynamic ads** | 102 |
| af\_content\_type | Item category<br /><br />**Required parameter for Meta ads dynamic ads**  <br />  <br />**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shoes |
| af\_currency | Currency on the product details page | THB, USD |

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="List view (af_list_view)">

**Purpose**

Record which lists (for example, newly added products, related products, or recommended products) buyers view the most.

**Trigger**

When the user views a specific list

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_content\_type | Item category<br /><br />**Required parameter for Meta ads dynamic ads**  <br />  <br />**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Related, recommended, new arrivals |
| af\_content\_list | List of content IDs from the category | 001, 092 |

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Add to wishlist (af_add_to_wishlist)">

**Purpose**

Record what products and categories buyers add to their wishlists. When you know what products are often added to wishlists, you can then offer these products in sales or discounts and encourage buyers to purchase them. You can also retarget users according to the products that they added to their wishlist.

**Trigger**

When the user adds items to their wishlist

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | Price of the product | 600 |
| af\_content\_id | Product ID | 300 |
| af\_content\_type | Item category<br /><br />**Required parameter for Meta ads dynamic ads**  <br />  <br />**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shoes, electronics |
| af\_currency | Currency displayed on the product details page | GBP |

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Add to cart (af_add_to_cart)">

**Purpose**

Record when a user adds products to their cart. This event can help you determine:

* How many products on average buyers add in one purchase
* How much time passes between adding two different products
* How many buyers abandon their cart

**Trigger**

When the user adds a product to the cart

**Event parameters**

| Field name | Description | Example value |
| --- | --- | --- |
| af\_price | Product price | 350, 1000 |
| af\_content | International Article Number (EAN) when applicable, or other product or content identifier<br /><br />**Required parameter for Meta ads dynamic ads** | ABC123 |
| af\_content\_id | Product ID<br /><br />**Required parameter for Meta ads dynamic ads** | 001, 092 |
| af\_content\_type | Item category<br /><br />**Required parameter for Meta ads dynamic ads**  <br />  <br />**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shirt, shoes |
| af\_currency | Product currency | THB, USD |
| af\_quantity | How many items of the same product were added to the cart | 2, 5 |

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Initiated checkout (af_initiated_checkout)">

**Purpose**

Understand how buyers behave when they proceed to checkout. This event can help you determine:

* The average price when buyers check out compared with the average price in the purchase event
* Whether users add or remove products after proceeding to checkout

**Trigger**

When the user initiates the checkout but didn't yet complete the checkout

**Event parameters**

| Field name | Description | Example value |
| --- | --- | --- |
| af\_price | Total price in the cart | 4000 |
| af\_content\_id | ID of products in the cart | 221, 124 |
| af\_content\_type | Item category<br /><br />**Required parameter for Meta ads dynamic ads**  <br />  <br />**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shirt, pants |
| af\_currency | Currency during time of checkout | THB |
| af\_quantity | Total number of items in the cart | 2, 5 |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Purchase (af_purchase)">

**Purpose**

Learn about purchase trends in your app. This event can help you:

* Determine the LTV of your users and the ROI of your campaigns across ad networks and ad agencies
* Determine which offers are most popular with your users
* Cross-reference campaigns with purchased items in order to optimize campaign targeting

**Trigger**

When the user lands on the thank you page after a successful purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#revenue-in-in-app-events">af\_revenue</Anchor> | Estimated revenue from the purchase | 1205.99 |
| af\_price | Overall purchase sum | 4000 |
| af\_content | International Article Number (EAN) when applicable, or other product or content identifier<br /><br />**Required parameter for Meta ads** **dynamic ads** | ABC123 |
| af\_content\_id | Item ID<br /><br />**Required parameter for Meta ads dynamic ads** | 121, 262 |
| af\_content\_type | Item category<br /><br />**Required parameter for Meta ads dynamic ads**  <br />  <br />**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | product\_group |
| af\_currency | Currency code | AUD |
| af\_quantity | Number of items in the cart | 2, 5 |
| af\_order\_id | ID of the order that is generated after the purchase | X123ABC |
| af\_receipt\_id | Order ID<br /><br />**Required parameter for CRITEO and Google Ad Words for purchase validation** | X123ABC |

</Accordion>

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="first-purchase-first_purchase" />

<Accordion title="First purchase (first_purchase)">

**Purpose**

Same as the [Purchase](/docs/recommended-ecommerce-app-events#purchase-af_purchase) event. In addition, this event can help you determine:

* How long it takes a new buyer to purchase
* What products first-time buyers prefer to purchase
* The average price and revenue of first-time purchases

**Trigger**

When the user completes their first purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview#revenue-in-in-app-events">af\_revenue</Anchor> | Revenue from purchase | 1205.99 |
| af\_price | Overall purchase sum | 4000 |
| af\_content | International Article Number (EAN) when applicable, or other product or content identifier<br /><br />**Required parameter for Meta ads dynamic ads** | ABC123 |
| af\_content\_id | Item ID<br /><br />**Required parameter for Meta ads dynamic ads** | 121, 262 |
| af\_content\_type | Item category<br /><br />**Required parameter for Meta ads dynamic ads**  <br />  <br />**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shoes, pants |
| af\_currency | Currency | AUD |
| af\_quantity | Quantity of items in the cart | 2, 5 |
| af\_order\_id | ID of the order that is generated after the purchase | X123ABC |
| af\_receipt\_id | Order ID<br /><br />**Required parameter for CRITEO and Google AdWords retargeting integration** | X123ABC |

</Accordion>

<div id="remove-from-cart-remove_from_cart" />

<Accordion title="Remove from cart (remove_from_cart)">

**Purpose**

Recording this event can help you:

* Determine what items buyers remove from their cart
* Determine the product categories of items that buyers remove from their cart
* Compare the data from the [Add to cart](/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart) event to gain insights into products that don't make it to checkout

**Trigger**

When the user removes an item from the cart

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_content\_id | Item or product ID | 521 |
| af\_content\_type | Item category<br /><br />**Required parameter for Meta ads dynamic ads**  <br />  <br />**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shoes |

</Accordion>

<div data-zendesk-anchors="ecommerce=-ecommerce h_01HGTAWG2166CZYKJE9166G12J=-ecommerce h_01HGTAWG21Z0C9SR2G54W68G8Q=important h_01HGTAWG2115VB3A8J2WG3DJKK=recommended-structures-for-predefined-events h_01HGTAWG21EQ0FE40WGFJRDJY5=complete-registration-af_complete_registration h_01HGTAWG22HFZ24V2BDCH3RFN8=login-af_login h_01HGTAWG22B5Z9AXENDATKR67T=search-af_search h_01HGTAWG22PSKS80ZQNAC0K24M=content-view-af_content_view h_01HGTAWG2219SVQ86PT1K3TVV9=list-view-af_list_view h_01HGTAWG22EQMVWXJCXC2KQDX8=add-to-wishlist-af_add_to_wishlist h_01HGTAWG23T81SPFJEA6BY5F2W=add-to-cart-af_add_to_cart h_01HGTAWG23FPKQ6RHJ9VYET63Y=initiated-checkout-af_initiated_checkout h_01HGTAWG2385E9Q0FXZXEW38YK=purchase-af_purchase h_01HGTAWG235EXE17EJ5DWQYERM=recommended-structures-for-custom-events h_01HGTAWG23NTG0Q70B9A3685AD=first-purchase-first_purchase h_01HGTAWG239TQ51Z7FQW4FC1TZ=remove-from-cart-remove_from_cart" />

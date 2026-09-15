---
title: "Recommended eCommerce app events"
excerpt: "Measure the quality of your users throughout their user journey by recording these suggested in-app events for your eCommerce app."
---
## eCommerce

![InApp_Events_ecommerce.png](https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png)

eCommerce apps allow buyers to easily search for and buy goods online. The typical events that we suggest recording are search, purchase, adding to cart, and adding to wishlist.

Recording events can help you determine:

- The most popular categories
- What buyers are searching for
- How many buyers completed a checkout
- How many buyers are recurring buyers and how many are just one-time buyers

> 📘 Important!
>
> * Make sure to read the [instructions](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-guide#setting-up-inapp-events) for marketers about implementing in-app events.
> * To streamline the implementation process, use our [In-app event generator](https://evgen.appsflyer.com/?vertical=ecommerce). This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are [code samples](https://evgen.appsflyer.com/?vertical=ecommerce&view=code) for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the [**AppsFlyer developer hub**](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions) **.**

For more information about recording in-app events, see the [In-app events guide](https://support.appsflyer.com/hc/articles/115005544169).

![Flowchart_for_recommended_events e-Commerce_app_user_journey](https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the eCommerce vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### Complete registration (af\_complete\_registration)

**Purpose**

Learn how many users installed the app and completed the signup process, and what signup methods your users prefer.

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Type of signup method | Email, Meta ads |

### Login (af\_login)

**Purpose**

Understand the retention of your registered users

**Trigger**

When the user successfully logs in

**Event parameters**

Can be sent without any additional parameters

### Search (af\_search)

**Purpose**

Learn what users are looking for, and which search results are the most relevant and lead to a purchase.

**Trigger**

One of the following:

- When the user clicks on the search button
- When the user lands on the search results page

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_search\_string | Search term | Red dress, running shoes |
| af\_content\_list | List of content IDs | 001, 092 |

### Content view (af\_content\_view)

**Purpose**

Determine the view rate of specific products. This event can help you:

- Correlate product views with product sales
- Understand what categories are the most popular according to product views
- See the correlation between buyers' currency and the products they view

**Trigger**

When the user views a specific product details page

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | Product price | 2000 |
| af\_content | International Article Number (EAN) when applicable, or other product or content identifier<br>**Required parameter for Meta ads dynamic ads** | ABC123 |
| af\_content\_id | Product ID<br>**Required parameter for Meta ads dynamic ads** | 102 |
| af\_content\_type | Item category<br>**Required parameter for Meta ads dynamic ads**<br>**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shoes |
| af\_currency | Currency on the product details page | THB, USD |

### List view (af\_list\_view)

**Purpose**

Record which lists (for example, newly added products, related products, or recommended products) buyers view the most.

**Trigger**

When the user views a specific list

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_content\_type | Item category<br>**Required parameter for Meta ads dynamic ads**<br>**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Related, recommended, new arrivals |
| af\_content\_list | List of content IDs from the category | 001, 092 |

### Add to wishlist (af\_add\_to\_wishlist)

**Purpose**

Record what products and categories buyers add to their wishlists. When you know what products are often added to wishlists, you can then offer these products in sales or discounts and encourage buyers to purchase them. You can also retarget users according to the products that they added to their wishlist.

**Trigger**

When the user adds items to their wishlist

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_price | Price of the product | 600 |
| af\_content\_id | Product ID | 300 |
| af\_content\_type | Item category<br>**Required parameter for Meta ads dynamic ads**<br>**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shoes, electronics |
| af\_currency | Currency displayed on the product details page | GBP |

### Add to cart (af\_add\_to\_cart)

**Purpose**

Record when a user adds products to their cart. This event can help you determine:

- How many products on average buyers add in one purchase
- How much time passes between adding two different products
- How many buyers abandon their cart

**Trigger**

When the user adds a product to the cart

**Event parameters**

| Field name | Description | Example value |
| --- | --- | --- |
| af\_price | Product price | 350, 1000 |
| af\_content | International Article Number (EAN) when applicable, or other product or content identifier<br>**Required parameter for Meta ads dynamic ads** | ABC123 |
| af\_content\_id | Product ID<br>**Required parameter for Meta ads dynamic ads** | 001, 092 |
| af\_content\_type | Item category<br>**Required parameter for Meta ads dynamic ads**<br>**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shirt, shoes |
| af\_currency | Product currency | THB, USD |
| af\_quantity | How many items of the same product were added to the cart | 2, 5 |

### Initiated checkout (af\_initiated\_checkout)

**Purpose**

Understand how buyers behave when they proceed to checkout. This event can help you determine:

- The average price when buyers check out compared with the average price in the purchase event
- Whether users add or remove products after proceeding to checkout

**Trigger**

When the user initiates the checkout but didn't yet complete the checkout

**Event parameters**

| Field name | Description | Example value |
| --- | --- | --- |
| af\_price | Total price in the cart | 4000 |
| af\_content\_id | ID of products in the cart | 221, 124 |
| af\_content\_type | Item category<br>**Required parameter for Meta ads dynamic ads**<br>**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shirt, pants |
| af\_currency | Currency during time of checkout | THB |
| af\_quantity | Total number of items in the cart | 2, 5 |

### Purchase (af\_purchase)

**Purpose**

Learn about purchase trends in your app. This event can help you:

- Determine the LTV of your users and the ROI of your campaigns across ad networks and ad agencies
- Determine which offers are most popular with your users
- Cross-reference campaigns with purchased items in order to optimize campaign targeting

**Trigger**

When the user lands on the thank you page after a successful purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| [af\_revenue](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-Overview#revenue-events) | Estimated revenue from the purchase | 1205.99 |
| af\_price | Overall purchase sum | 4000 |
| af\_content | International Article Number (EAN) when applicable, or other product or content identifier<br>**Required parameter for Meta ads** **dynamic ads** | ABC123 |
| af\_content\_id | Item ID<br>**Required parameter for Meta ads dynamic ads** | 121, 262 |
| af\_content\_type | Item category<br>**Required parameter for Meta ads dynamic ads**<br>**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | product\_group |
| af\_currency | Currency code | AUD |
| af\_quantity | Number of items in the cart | 2, 5 |
| af\_order\_id | ID of the order that is generated after the purchase | X123ABC |
| af\_receipt\_id | Order ID<br>**Required parameter for CRITEO and Google Ad Words for purchase validation** | X123ABC |

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

### First purchase (first\_purchase)

**Purpose**

Same as the [Purchase](https://support.appsflyer.com/hc/articles/360019347957#purchase-af_purchase) event. In addition, this event can help you determine:

- How long it takes a new buyer to purchase
- What products first-time buyers prefer to purchase
- The average price and revenue of first-time purchases

**Trigger**

When the user completes their first purchase

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| [af\_revenue](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-Overview#revenue-events) | Revenue from purchase | 1205.99 |
| af\_price | Overall purchase sum | 4000 |
| af\_content | International Article Number (EAN) when applicable, or other product or content identifier<br>**Required parameter for Meta ads dynamic ads** | ABC123 |
| af\_content\_id | Item ID<br>**Required parameter for Meta ads dynamic ads** | 121, 262 |
| af\_content\_type | Item category<br>**Required parameter for Meta ads dynamic ads**<br>**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shoes, pants |
| af\_currency | Currency | AUD |
| af\_quantity | Quantity of items in the cart | 2, 5 |
| af\_order\_id | ID of the order that is generated after the purchase | X123ABC |
| af\_receipt\_id | Order ID<br>**Required parameter for CRITEO and Google AdWords retargeting integration** | X123ABC |

### Remove from cart (remove\_from\_cart)

**Purpose**

Recording this event can help you:

- Determine what items buyers remove from their cart
- Determine the product categories of items that buyers remove from their cart
- Compare the data from the [Add to cart](https://support.appsflyer.com/hc/articles/360019347957#add-to-cart-af_add_to_cart) event to gain insights into products that don't make it to checkout

**Trigger**

When the user removes an item from the cart

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_content\_id | Item or product ID | 521 |
| af\_content\_type | Item category<br>**Required parameter for Meta ads dynamic ads**<br>**Note:** When mapping `af_content_type` to Meta’s `fb_content_type`, the only supported values are `product` or `product_group`. | Shoes |
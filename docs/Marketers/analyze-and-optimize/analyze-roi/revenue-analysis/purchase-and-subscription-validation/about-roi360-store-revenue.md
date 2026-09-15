---
title: About ROI360 store revenue
excerpt: >-
  ROI360 store revenue is AppsFlyer's premium solution for complete and accurate
  measurement of revenue from in-app purchases and subscriptions.
---
Use ROI360 store revenue to validate in-app purchases and subscriptions, prevent duplicates, and calculate net revenue.

<Callout icon="fad fa-triangle-exclamation" theme="warn">
  ### Important!

  ROI360 store revenue is available only to customers on the ROI360 premium plan. To check your plan or upgrade, contact your Customer Success Manager (CSM).
</Callout>

ROI360 store revenue is AppsFlyer’s premium solution for complete and accurate measurement of revenue from in-app purchases and subscriptions. It provides a comprehensive view of the customer life cycle, enabling the accurate measurement of Return On Ad Spend (ROAS).

<Table>
  <thead>
    <tr>
      <th>
        Feature
      </th>

      <th>
        Details
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Revenue measurement scope
      </td>

      <td>
        - Revenue from all in-app purchases of products and subscriptions managed through App Store Connect (iOS) and Google Play Console (Android)
        - Refunds
        - Pending and deferred transaction revenue (Android)
        - Subscription-related events that occur both inside and outside the app
        - Net revenue, which accounts for store commissions and taxes&#x20;
      </td>
    </tr>

    <tr>
      <td>
        Revenue validation and accuracy
      </td>

      <td>
        The solution prevents duplicate transactions from being recorded. On iOS, this also includes preventing duplication caused by Family Sharing. ROI360 store revenue can also forward Apple App Store transaction data directly to advertisers.
      </td>
    </tr>

    <tr>
      <td>
        Data sources
      </td>

      <td>
        - AppsFlyer purchase SDK connector for Android and iOS
        - App Store server notifications
        - Google Play Real-Time Developer Notifications (RTDN)
      </td>
    </tr>

    <tr>
      <td>
        Reporting and data availability
      </td>

      <td>
        Revenue data is available in AppsFlyer dashboards and reports and can also be shared with partners through postbacks.
      </td>
    </tr>
  </tbody>
</Table>

<Callout icon="far fa-circle-exclamation" theme="error">
  ### Warning

  When using ROI360 store revenue, do not send in-app purchase events, as this will result in duplicate revenue reporting.
</Callout>

## How does ROI360 store revenue work?

1. A user makes an in-app purchase or an auto-renewable subscription.
2. The app makes a transaction in the app store.
3. The AppsFlyer purchase SDK connector automatically detects purchases and sends their payloads to AppsFlyer for validation and logging.
4. AppsFlyer validates the purchase with the relevant store to ensure it's not fraudulent.
   - Upon successful validation, AppsFlyer logs the purchase or subscription in-app event.
   - If receipt validation fails, the event displays in the blocked in-app events raw data report (available to Protect360 subscribers) and in the Live events viewer page with parameter `af_validated` = false.
5. AppsFlyer transfers the response to the SDK connector, which in turn transfers the receipt validation response (success or failure) to the app.
6. Any incoming server notifications from the app stores are also processed by the AppsFlyer purchase and subscription revenue business logic.
   - Notifications regarding transactions previously reported via the SDK connector are validated and processed, and result in the internal creation of a purchase or life cycle event.
   - Notifications regarding unknown transactions are dropped.
   - For iOS, all server notifications can be rerouted to your own servers.

## Activate ROI360 store revenue

To activate ROI360 store revenue measurement, follow these steps:

1. In AppsFlyer, from the side menu, open ![settings-roi.png](https://files.readme.io/86023f68c41c5260314171f40b28b73ccd6c9dbdf263391c3c751041625a6ed9-42138855423633.png)**Settings** and under **ROI360** select **Revenue Settings**.
2. Open the **Purchases & subscriptions** tab.
3. Under **1 Choose Product type**, select **ROI360**.
4. Click **Next** to continue.

## Set up ROI360 store revenue

See the [Set up ROI360 store revenue](/docs/set-up-roi360-store-revenue) article

## Reference

The following sections provide additional details about key aspects of ROI360 in-app purchase (IAP) and subscription revenue measurement. These include events and parameters for IAP and subscription events, Net revenue, which supports gross-to-net revenue calculations, and the general characteristics and limitations of the ROI360 IAP and subscription revenue measurement solution.

<Callout icon="far fa-pen-field" theme="info">
  ### Note

  To send additional custom parameters with your in-app events, configure a **custom data source** in the [Purchase SDK Connector](https://dev.appsflyer.com/hc/docs/purchase-connector). This allows you to enrich purchase and subscription events with your own business logic or metadata.

  These parameters will be available in the raw data report's `custom_data` field.
</Callout>

<Accordion title="IAP-related events and parameters" icon="fa-info-circle">
  The following sections display the IAP-related events that AppsFlyer measures and the parameters recorded for each event. For an explanation of the included parameters, see the [event parameter dictionary](/docs/about-roi360-store-revenue#parameter-dictionary).

  **All generated events have the following properties:**

  - Server-to-server (S2S) events.
  - Available in raw data reports as organic or non-organic in-app events, and included in the Revenue ETL Stores reports.
  - Sent to partners via postbacks.
  - Supported in SKAN Conversion Studio.
    <Accordion title="Purchase (af_purchase)" icon="fa-info-circle">
      **Description**

      Recorded when a user makes a purchase.

      **Parameters**

      - app_id
      - customer_user_id
      - af_currency
      - af_original_transaction_id
      - af_order_id
      - af_purchase_token
      - af_transaction_id
      - af_product_id
      - android_id
      - idfa
      - ip
      - appsflyer_id
      - af_purchase_date_ms
      - af_store
      - af_environment
      - af_revenue
      - af_net_revenue
      - af_net_revenue_tax_name
      - af_net_revenue_tax_rate
      - af_net_revenue_tax_exclusive
      - af_net_revenue_country
      - af_net_revenue_subdivision
      - af_net_revenue_postal_code
      - af_net_revenue_factors
    </Accordion>
    <Accordion title="Purchase free (af_purchase_free)" icon="fa-info-circle">
      **Description**

      Recorded when a user makes a purchase that has no revenue amount. All revenue parameters will display 0.

      **Parameters**

      - app_id
      - customer_user_id
      - af_currency
      - af_original_transaction_id
      - af_order_id
      - af_purchase_token
      - af_transaction_id
      - af_product_id
      - android_id
      - idfa
      - ip
      - appsflyer_id
      - af_purchase_date_ms
      - af_store
      - af_environment
      - af_revenue
      - af_net_revenue
      - af_net_revenue_tax_name
      - af_net_revenue_tax_rate
      - af_net_revenue_tax_exclusive
      - af_net_revenue_country
      - af_net_revenue_subdivision
      - af_net_revenue_postal_code
      - af_net_revenue_factors

      ####
    </Accordion>
    <Accordion title="Purchase canceled (af_purchase_canceled)" icon="fa-info-circle">

    </Accordion>
    <Accordion title="Purchase" icon="fa-info-circle">

    </Accordion>
    <Accordion title="Purchase" icon="fa-info-circle">

    </Accordion>
    <Accordion title="Purchase (af_purchase)" icon="fa-info-circle">

    </Accordion>
    <Accordion title="Purchase (af_purchase) " icon="fa-info-circle">

    </Accordion>
</Accordion>

###

####

#### Purchase canceled (af_purchase_canceled)

**Description**

Recorded when a user cancels a purchase.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment

#### Purchase pending (af_purchase_pending)

**Description**

Recorded when a user makes a purchase but the payment isn't yet processed.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment

#### Refund (af_purchase_refund)

**Description**

Recorded when a purchase is refunded.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_discount_type
- event_revenue_usd
- event_revenue (included in the event when the revenue exceeds zero)
- store_commission
- af_revenue
- af_net_revenue
- af_net_revenue_factors
- af_net_revenue_tax_name
- af_net_revenue_tax_rate
- af_net_revenue_tax_exclusive
- af_net_revenue_country
- af_net_revenue_subdivision
- af_net_revenue_postal_code

#### Test purchase (af_purchase_sandbox_sdk)

**Description**

Recorded when testing a purchase recorded via SDK in sandbox environment.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_purchase_state
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_net
- af_sandbox_revenue

#### Test purchase (af_purchase_sandbox_s2s)

**Description**

Recorded when testing a purchase reported via S2S in a sandbox environment.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_purchase_state
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_net
- af_sandbox_revenue

### Subscription-related events and parameters

The following sections display the subscription-related events that AppsFlyer measures, and the parameters that are recorded for each event. See the [event parameter dictionary](/docs/about-roi360-store-revenue#parameter-dictionary) for an explanation of the included parameters.

All generated events:

- Are considered S2S events.
- Are accessible in raw data reports (as organic or non-organic in-app events).
- Can be sent via postbacks to partners.
- Can be used in SKAN Conversion Studio.

<Callout icon="📘" theme="info">
  ### Note

  Depending on the user device platform, some parameters aren't always populated for an in-app event.
</Callout>

#### Trial started (af_ars_trial_started)

**Description**

Recorded when a subscriber begins a trial period.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type

#### Trial canceled (af_ars_trial_canceled)

**Description**

Recorded when a subscriber cancels the automatic renewal of the subscription during the trial period. If a user doesn't restore the auto-renewal within the trial period, a churn event follows.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type

#### Trial churned (af_ars_trial_churned)

**Description**

Recorded when a subscriber churns following a trial period. This happens after auto-renewal cancelation and trial period expiration. It can also follow a billing or technical issue with the renewal leading to churn.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type
- af_reason

#### Trial converted (af_ars_trial_converted)

**Description**

Recorded when a fully priced renewal starts, following a trial period.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type
- af_discount_id
- af_discount_type
- event_revenue_usd
- store_commission
- af_revenue (included in the event only when the revenue exceeds zero)
- af_net_revenue
- af_net_revenue_factors
- af_net_revenue_tax_name
- af_net_revenue_tax_rate
- af_net_revenue_tax_exclusive
- af_net_revenue_country
- af_net_revenue_subdivision
- af_net_revenue_postal_code

#### Subscription started (af_ars_subscription_started)

**Description**

Recorded when a discounted or a fully priced subscription starts.

**Note**:

- New subscriptions can only be recorded via the SDK connector.
- For iOS, if a subscriber repurchases a subscription they already own, the SDK connector reports a successful receipt validation back to the app, but doesn't record a new transaction in AppsFlyer.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type
- af_discount_id
- af_discount_type
- event_revenue_usd
- event_revenue (included in the event when the revenue exceeds zero)
- store_commission
- af_revenue
- af_net_revenue
- af_net_revenue_factors
- af_net_revenue_tax_name
- af_net_revenue_tax_rate
- af_net_revenue_tax_exclusive
- af_net_revenue_country
- af_net_revenue_subdivision
- af_net_revenue_postal_code

#### Subscription canceled (af_ars_subscription_canceled)

**Description**

Recorded when an auto-renewal subscription is canceled in the middle of a billing period. If a user doesn't restore the auto-renewal within the same billing period, a churn event follows.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type

#### Subscription paused (af_ars_subscription_paused) - Android only

**Description**

Recorded when a user pauses an active subscription.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type

#### Subscription resumed (af_ars_subscription_resumed)

**Description**

Recorded when a fully priced subscription is resumed following a churned or refunded subscription.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type
- af_discount_id
- af_discount_type
- af_reason
- event_revenue (included in the event when event revenue exceeds zero)
- store_commission
- af_revenue
- af_net_revenue
- af_net_revenue_factors

#### Subscription churned (af_ars_subscription_churned)

**Description**

Recorded when a subscriber churns. This usually happens after auto-renewal cancelation or billing period expiration. It can also follow a billing or technical issue, with the renewal leading to churn.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type
- af_reason

#### Subscription refunded (af_ars_subscription_refunded)

**Description**

Recorded when a subscriber is issued a refund.

**Note:**

- This event is usually generated along with a negative value. In cases where it is impossible to detect which transactions were refunded, or details of the refund aren't included in the notification, the refund event shows no value.

**Parameters**

- app_id
- customer_user_id
- af_reason
- af_subscription_ownership_type
- af_discount_id
- af_discount_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_refunded_transaction_ids
- event_revenue_usd
- event_revenue (included in the event when the revenue exceeds zero)
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_store
- af_environment
- af_period_type
- store_commission
- af_revenue
- af_net_revenue
- af_net_revenue_factors
- af_net_revenue_tax_name
- af_net_revenue_tax_rate
- af_net_revenue_tax_exclusive
- af_net_revenue_country
- af_net_revenue_subdivision
- af_net_revenue_postal_code

#### Subscription billing grace (af_ars_subscription_billing_grace)

**Description**

Recorded when a subscription renewal fails due to a billing issue and the subscriber enters the billing grace period.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type

#### Subscription renewed (af_ars_subscription_renewed)

**Description**

Recorded when an auto-renewal subscription takes place.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type
- af_discount_id
- af_discount_type
- event_revenue_usd
- event_revenue (included in the event when the revenue exceeds zero)
- store_commission
- af_revenue
- af_net_revenue
- af_net_revenue_factors

#### Subscription changed (af_ars_subscription_xgraded)

**Description**

Recorded when a subscriber upgrades, downgrades, or cross-grades to a different product.

**Parameters**

- app_id
- customer_user_id
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type
- af_discount_id
- af_discount_type
- event_revenue_usd
- event_revenue (included in the event when the revenue exceeds zero)
- store_commission
- af_revenue
- af_net_revenue
- af_net_revenue_factors

#### Existing subscriber (af_ars_existing_subscriber)

**Description**

Recorded when the SDK connector is notified about a subscriber in the middle of a billing cycle, before getting a follow-up server notification that transitions the subscriber to another relevant lifecycle stage. This event is usually generated during your onboarding and SDK connector adoption period.

**Parameters**

- app_id
- customer_user_id
- country
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type
- af_cuids
- af_validated

#### Test purchase (af_ars_sandbox_sdk)

**Description**

Recorded when testing a purchase recorded via SDK in sandbox environment.

**Parameters**

- app_id
- customer_user_id
- country
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_discount_id
- af_discount_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type
- af_cuids
- af_validated
- af_net
- af_sandbox_revenue

#### Test purchase (af_ars_sandbox_s2s)

**Description**

Recorded when testing a purchase reported via S2S in a sandbox environment.

**Parameters**

- app_id
- customer_user_id
- country
- af_currency
- af_expires_date_ms
- af_subscription_ownership_type
- af_discount_id
- af_discount_type
- af_original_transaction_id
- af_order_id
- af_purchase_token
- af_transaction_id
- af_product_id
- android_id
- idfa
- ip
- appsflyer_id
- af_purchase_date_ms
- af_store
- af_environment
- af_period_type
- af_cuids
- af_validated
- af_net
- af_sandbox_revenue

### Parameter dictionary

Parameters for IAP and subscription events display in raw data reports either as their own columns or populated as part of the **Event value**.

The parameters that have their own columns are:

- app_id
- customer_user_id
- country_code
- af_currency
- event_revenue_usd
- af_revenue
- android_id
- ip
- idfa
- appsflyer_id

See the [data fields dictionary](/docs/raw-data-field-dictionary) for more details about these parameters.

The following table describes the raw data parameters available in ARS and VIAP events.

<Table>
  <thead>
    <tr>
      <th>
        Parameter
      </th>

      <th>
        Remarks
      </th>

      <th>
        Product
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        af_cancelation_date_ms
      </td>

      <td>
        Date of the cancelation
      </td>

      <td>
        IAP
      </td>
    </tr>

    <tr>
      <td>
        af_cuids
      </td>

      <td>
        - In the context of ARS, this parameter contains an array with all CUIDs.<br />- The array of CUIDs displays irrespective of the device IDs. Thus, the same CUIDs can display for more than one device ID.
      </td>

      <td>
        Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_discount_id
      </td>

      <td>
        The offer ID presented to the user during the initial purchase. The ID is populated only when there is a discount code.
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_discount_type
      </td>

      <td>
        The discount type redeemed by the user. Possible values:<br />- IOS<br />  - introductory<br />  - promotional<br />  - offer_codes<br />  - win_back<br />- Android<br />  - intro price<br />  - one_time_code<br />  - vanity_code
      </td>

      <td>
        Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_environment
      </td>

      <td>
        The environment from which data is received, either production or sandbox.
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_expires_date_ms
      </td>

      <td>
        The expiration date of the current subscription billing cycle
      </td>

      <td>
        Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_net_revenue
      </td>

      <td>
        Net revenue calculated based on all factored reasons. See af_net_revenue_factors.
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_net_revenue_country
      </td>

      <td>
        - [Two-letter ISO country code](https://www.nationsonline.org/oneworld/country_code_list.htm) for which the tax is applied.<br />- Example: CA<br />- Note: For United Kingdom, the code implemented is UK, not GB.
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_net_revenue_factors
      </td>

      <td>
        - An array representing all factored reasons that produce the reported af_net_revenue amount.<br />- Example value: store_commission
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_net_revenue_postal_code
      </td>

      <td>
        - String of letters and/or numbers<br />- Example: L4J8E3
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_net_revenue_subdivision
      </td>

      <td>
        - For some countries, there can be an additional state or subdivision. This is handled according to [ISO 3166-2 subdivision codes](https://service.unece.org/trade/locode/2023-1%20SubdivisionCodes.htm).<br />- Includes the country code and subdivision code.<br />- Example: US-CA
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_net_revenue_tax_exclusive
      </td>

      <td>
        - Boolean parameter, either true or false.<br />- False means tax is included in the overall revenue.<br />- True means tax is in addition to the overall stated revenue.
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_net_revenue_tax_name
      </td>

      <td>
        - Name appearing in the customer invoice that describes the specific type of tax.<br />- Example: Sales, VAT, GST
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_net_revenue_tax_rate
      </td>

      <td>
        - Number up to 4 decimal places representing the tax percentage collected.<br />- Example: 7.25
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_offer_id
      </td>

      <td>
        - The offer ID applied to the transaction, when relevant (for example, discounted or promotional offers).<br />- Android only
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_order_id
      </td>

      <td>
        - The order ID for the transaction<br />- Android only
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_original_transaction_id
      </td>

      <td>
        - The original transaction ID<br />- iOS only
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_original_transaction_id
      </td>

      <td>
        - The original ID of the transaction<br />- iOS only
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_period_type
      </td>

      <td>
        - Subscription or trial period type.<br />- Possible values:<br />  - trial<br />  - intro<br />  - normal
      </td>

      <td>
        Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_product_id
      </td>

      <td>
        The subscription product ID
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_purchase_date_ms
      </td>

      <td>
        The purchase date for the reported product ID in-app event
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_purchase_option_id
      </td>

      <td>
        - The purchase option ID associated with the transaction.<br />- Android only
      </td>

      <td>
        IAP
      </td>
    </tr>

    <tr>
      <td>
        af_purchase_option_type
      </td>

      <td>
        The purchase option type of the transaction. Possible values (Android):<br />- buy<br />- rent
      </td>

      <td>
        IAP
      </td>
    </tr>

    <tr>
      <td>
        af_purchase_state
      </td>

      <td>
        Possible values:<br />- Purchased<br />- Canceled<br />- Pending
      </td>

      <td>
        IAP
      </td>
    </tr>

    <tr>
      <td>
        af_purchase_token
      </td>

      <td>
        - The purchase token for the transaction<br />- Android only
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_reason
      </td>

      <td>
        \[content unchanged]
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_refunded_transaction_ids
      </td>

      <td>
        - An array of all refunded transaction IDs<br />- iOS only
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_store
      </td>

      <td>
        The app store the subscription product was purchased from
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_subscription_ownership_type
      </td>

      <td>
        FAMILY_SHARED means the user has access via family sharing. PURCHASED means the paying user made the purchase.
      </td>

      <td>
        Subscription
      </td>
    </tr>

    <tr>
      <td>
        af_transaction_id
      </td>

      <td>
        - The ID of the transaction<br />- iOS only
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>

    <tr>
      <td>
        store_commission
      </td>

      <td>
        - The calculated percentage of commission the store gets from the purchased product.<br />- Displayed as a decimal.<br />- Example: 30
      </td>

      <td>
        - IAP<br />- Subscription
      </td>
    </tr>
  </tbody>
</Table>

### Net revenue

Net revenue is a business logic layer built to serve the ROI360 Store revenue solution. It automatically calculates the net revenue value for each incoming transaction in real time and includes it in reports.

<Callout icon="📘" theme="info">
  ### Note

  Net revenue is displayed in raw data reports and can be sent in real time via in-app event postbacks. It is also available in [My Dashboards](/docs/my-dashboards) as the Net metrics (Net revenue, Net ROI, Net ROAS, Net ARPU, Net profit).

  To send net revenue in postbacks, configure the in-app event with the option **Values, revenue & net revenue**. See [In-app event postback configuration](/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks) for details.
</Callout>

<Callout icon="👍" theme="okay">
  ### Tip

  You can also configure your in-app event postbacks to send net revenue in place of gross revenue in the standard revenue (monetary) parameter. To get access to this configuration, contact your Customer Success Manager (CSM).
</Callout>

Net revenue considers the following factors in the gross-to-net revenue calculation:

- **Store commission**:
  - It is calculated and reported automatically. No action is required on your part.
  - For purchases (IAP), the default store commission depends on the storefront:
    - App Store — Japan: 26%. China mainland (CN): 25%. Rest of the world: 30%.
    - Play Store: 30%.
  - For subscriptions, the commission is automatically calculated per subscriber, based on the subscriber's lifetime.
    - App Store — first 12 months: 26% in Japan, 25% in China mainland (CN), 30% in the rest of the world. From the 13th month: 15% in Japan, 12% in China mainland (CN), 15% in the rest of the world.
    - Play Store: 15% from day one.
  - Related net revenue parameters are available in raw data reports.
  - Use [the Net revenue API](https://dev.appsflyer.com/hc/reference/overview-7) to set a different store commission rate than the default. This is useful, for example, if your app is enrolled in Apple's Small Business Program, where the commission rate is 15% (12% in China mainland (CN)).
- **Tax**:
  - Tax is reported by default for any transaction measured by ROI360 using the default tax rate configuration.
  - This applies to tax-inclusive countries (where tax is included in the list price). So, for example, in the UK, AppsFlyer deducts the sum of the tax and the store commission. For tax-exclusive countries, such as the USA, where the list price does not include tax, revenue and net revenue parameters do not include tax by default.
  - The configuration can be edited using [the Net revenue API](https://dev.appsflyer.com/hc/reference/overview-7). To learn which countries are supported and their default tax rates, see [this JSON file](https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub). The developer can edit it or use it as-is in the API.

When viewing net revenue in reports, the following parameters contain the net revenue data. See the [parameter dictionary](/docs/about-roi360-store-revenue#parameter-dictionary) for more details.

<Table>
  <thead>
    <tr>
      <th>
        Parameter
      </th>

      <th>
        Net revenue factor
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        `store_commission`
      </td>

      <td>
        Store commission
      </td>
    </tr>

    <tr>
      <td>
        `af_net_revenue_tax_name`
      </td>

      <td>
        Tax
      </td>
    </tr>

    <tr>
      <td>
        `af_net_revenue_tax_rate`
      </td>

      <td>
        Tax
      </td>
    </tr>

    <tr>
      <td>
        `af_net_revenue_tax_exclusive`
      </td>

      <td>
        Tax
      </td>
    </tr>

    <tr>
      <td>
        `af_net_revenue_postal_code`
      </td>

      <td>
        Tax
      </td>
    </tr>

    <tr>
      <td>
        `af_net_revenue_country`
      </td>

      <td>
        Tax
      </td>
    </tr>

    <tr>
      <td>
        `af_net_revenue_subdivision`
      </td>

      <td>
        Tax
      </td>
    </tr>

    <tr>
      <td>
        `af_net_revenue`
      </td>

      <td>
        - Store commission<br />- Tax
      </td>
    </tr>

    <tr>
      <td>
        `af_net_revenue_factors`
      </td>

      <td>
        - Store commission<br />- Tax
      </td>
    </tr>
  </tbody>
</Table>

### Troubleshooting and discrepancies

| Symptom                                                                                   | Explanation / Solution                                                                                                                                                                                                                                                                                                                                        |
| ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AppsFlyer shows fewer in-app purchase and subscription events than the actual app stores. | In AppsFlyer, events are only generated for users who have updated to a version of the app that includes the SDK connector. Meanwhile, the app stores log every event, regardless of the user's app version. As a result, until full adoption of the updated app version, a discrepancy between the revenue data from the app and the store data is expected. |

### Traits and limitations

<Table>
  <thead>
    <tr>
      <th>
        Specification
      </th>

      <th>
        Product
      </th>

      <th>
        Remarks
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Installment subscriptions (Android)
      </td>

      <td>
        Subscription revenue
      </td>

      <td>
        Not supported
      </td>
    </tr>

    <tr>
      <td>
        Subscription pending<br />transactions (Android)
      </td>

      <td>
        Subscription revenue
      </td>

      <td>
        Not supported
      </td>
    </tr>

    <tr>
      <td>
        New subscriptions
      </td>

      <td>
        Subscription revenue
      </td>

      <td>
        Only recorded via the AppsFlyer purchase SDK
      </td>
    </tr>

    <tr>
      <td>
        Price change
      </td>

      <td>
        Subscription revenue
      </td>

      <td>
        If subscription revenue doesn't receive an SDK-originated notification with the new product price, subscription revenue continues to report the previous product price as revenue. Once the new product price is received from the purchase SDK, the new price is recorded.
      </td>
    </tr>

    <tr>
      <td>
        Gross revenue
      </td>

      <td>
        - IAP<br />- Subscription revenue
      </td>

      <td>
        Supported
      </td>
    </tr>

    <tr>
      <td>
        Net revenue
      </td>

      <td>
        - IAP<br />- Subscription revenue
      </td>

      <td>
        Supported in raw data and in My Dashboards (as the Net metrics)
      </td>
    </tr>

    <tr>
      <td>
        Refunds
      </td>

      <td>
        IAP
      </td>

      <td>
        Can be reported until 180 days after the original purchase.
      </td>
    </tr>

    <tr>
      <td>
        Deduplication
      </td>

      <td>
        - IAP<br />- Subscription revenue
      </td>

      <td>
        Supported for transactions reported up to 180 days after event date.
      </td>
    </tr>

    <tr>
      <td>
        SDK strict mode
      </td>

      <td>
        - IAP<br />- Subscription revenue
      </td>

      <td>
        ROI360 subscriptions and IAP are supported under SDK strict mode from the:<br />- AppsFlyer iOS purchase SDK connector V6.13.0<br />- Unity purchase SDK connector V2.0.1
      </td>
    </tr>

    <tr>
      <td>
        Currency
      </td>

      <td>
        - IAP<br />- Subscription revenue
      </td>

      <td>
        Revenue is reported in the original currency (using the event_revenue parameter) and in USD (using the event_revenue_usd parameter).
      </td>
    </tr>

    <tr>
      <td>
        Data freshness
      </td>

      <td>
        - IAP<br />- Subscription revenue
      </td>

      <td>
        - Transaction-level store revenue report: Hourly<br />- Device-level store revenue report: Every 8 hours
      </td>
    </tr>

    <tr>
      <td>
        StoreKit 2
      </td>

      <td>
        - IAP<br />- Subscription revenue
      </td>

      <td>
        - StoreKit 2 is supported starting with Purchase SDK Connector version 6.16.2.<br />- Make sure your app is using the updated App Store credentials as described [here](/docs/bulletin-update-app-store-credentials-for-ios-roi360-receipt-validation).
      </td>
    </tr>

    <tr>
      <td>
        Google one-time products
      </td>

      <td>
        IAP
      </td>

      <td>
        - Supported purchase options: Buy and Rent<br />- Pre-order: Not supported
      </td>
    </tr>
  </tbody>
</Table>

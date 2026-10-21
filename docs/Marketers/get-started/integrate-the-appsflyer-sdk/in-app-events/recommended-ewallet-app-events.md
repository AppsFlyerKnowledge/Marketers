---
title: Recommended eWallet app events
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
  created_at: '2021-06-10T11:36:07Z'
  edited_at: '2023-12-04T11:47:33Z'
  id: 4402425586065
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4402425586065-Recommended-eWallet-app-events
---
**At a glance:** Measure the quality of your users throughout their user journey by recording these suggested in-app events for your eWallet app.

## <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="67px" /> eWallet

eWallet apps enable users to make digital payments or purchases from their devices. The typical events that we suggest recording include adding funds, viewing content, selecting merchants, viewing promotions, and completing transactions.

Recording these events can help you determine:

* What type of content and promotions are popular with users, and then offer them similar or related products
* What are the most popular types of services users use eWallet for when making bill payments
* Which merchants are the most popular

> 🚧 **Important!**
>
> * Make sure to read the <Anchor target="_blank" href="/marketers/docs/in-app-events-overview#setting-up-in-app-events">instructions</Anchor> for marketers about implementing in-app events.
> * To streamline the implementation process, use our <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ewallet">In-app event generator</Anchor>. This tool includes all of the typical in-app events described in this article and lets you modify the events according to your business needs. Once complete, share the file with your developer.
> * For each recommended event included in this article, there are <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ewallet&view=code">code samples</Anchor> for iOS, Android, and Unity developers.
> * Detailed instructions for your developer can be found in the **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">AppsFlyer developer hub</Anchor>.**
>
> For more information about recording in-app events, see the <Anchor target="_blank" href="/marketers/docs/in-app-events-overview">In-app events guide</Anchor>.

[![Flowchart_for_recommended_events e-Wallet_app_user_journey](https://files.readme.io/cf1f91f9c89d1f45448a6172e48b7f59fdce767f00c893d91b12a5f2d043945f-4404610923409.png)](https://files.readme.io/cf1f91f9c89d1f45448a6172e48b7f59fdce767f00c893d91b12a5f2d043945f-4404610923409.png)

## Recommended structures for predefined events

The following section provides a list of event structures that are typical to the eWallet vertical. Each structure includes a predefined event name and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Complete registration (af_complete_registration)">

**Purpose**

Learn how many users installed the app and completed the signup process and what signup methods your users prefer.

**Trigger**

When the user completes the signup process

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| af\_registration\_method | Type of signup method | Email, Facebook, Google |

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

<div id="content-view-af_content_view" />

<Accordion title="Content view (af_content_view)">

**Purpose**

Determine the view rate of specific content. This event can help you:

* Understand what type of content is most popular with your users, and then try to optimize your marketing campaigns
* Correlate item views with merchants

**Trigger**

When the user views a specific item or category content

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| item | Type of item | cinema ticket |
| merchant\_name | Name of merchant | cineplex |

</Accordion>

## Recommended structures for custom events

The following section provides a list of event structures that include custom event names and the suggested event parameters to use. Note that in-app events can include any event parameters that meet your business needs.

<div id="wallet-complete-topup-wallet_complete_topup" />

<Accordion title="Wallet complete top-up (wallet_complete_topup)">

**Purpose**

Top-up funds can be used to buy any package or any other service offered inside the app. Record this event and compare it with other data to learn more about your users. For example, you can learn what amounts users are willing to deposit into their accounts and then use the top-up amounts to target them with customized campaigns within their budgets.

**Trigger**

When the user completes the top-up from their bank or credit card to the eWallet app

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| top\_up\_amount | Amount of payment | 100 |
| top\_up\_method | Type of payment method | bank transfer |

</Accordion>

<div id="payment-transaction-completed-payment_transaction_completed" />

<Accordion title="Payment transaction completed ( payment_transaction_completed )">

**Purpose**

This event can help you:

* Highlight users who completed payment on a transaction.
* Identify large transactions, and then retarget users who top-up with a large sum of money.

**Trigger**

When the transaction of a specific purchase is completed

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| item | Item paid for | prepaid card reload |
| quantity | Amount paid | 1 |
| transaction\_amount | Amount of the transaction | 50 |

</Accordion>

<div id="bill-payment-success-bill_payment_success" />

<Accordion title="Bill payment success (bill_payment_success)">

**Purpose**

This event can help you determine the most popular type of service users use eWallet for when paying bills (for example, water bills, electricity bills, or credit card balances).

**Trigger**

When the user is using eWallet to make payments, such as bills, or credit card statements, or cinema tickets

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| merchant\_name | Name of merchant | Electricity provider |
| payment\_amount | Amount paid | 100 |
| category | Type of service | Electricity |

</Accordion>

<div id="promo-promo" />

<Accordion title="Promo (promo)">

**Purpose**

This event can help you determine:

* Whether the promotion being offered is popular with users
* Whether the promotion helps with cross-selling additional products to users

**Trigger**

When the user selects the promotion available within the app

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| promo\_type | Type of promotion being offered | 30% off |

</Accordion>

<div id="voucher-redeem-voucher_redeem" />

<Accordion title="Voucher redeem (voucher_redeem)">

**Purpose**

This event can help you determine:

* How many users redeem promotional codes
* What sort of vouchers and discounts users prefer

**Trigger**

When a user promotion code is redeemed

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| voucher\_ID | ID of the voucher | 1735103 |
| merchant\_name | Name of merchant | cineplex |

</Accordion>

<div id="select-merchant-select_merchant" />

<Accordion title="Select merchant ( select_merchant )">

**Purpose**

This event can help you determine which merchant is the most popular and then use this data to try and get similar merchants to join the eWallet service.

**Trigger**

When the user selects a merchant from the list of available merchants

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| merchant\_name | Name of merchant | cineplex |
| type | Type of business | cinema |
| amount | Currency used by the advertiser | USD |
| merchant\_ID | Specific ID attached to a business that tells the payment processing systems involved in a transaction where to send which funds | 123456 |

</Accordion>

<div id="scan-barcode-success-scan_barcode_success" />

<Accordion title="Scan barcode success ( scan_barcode_success )">

**Purpose**

This event can help you:

* Understand when a user completes a specific transaction with a merchant
* Determine which merchants are the most popular

**Trigger**

When the user scans the QR code from each merchant that they visited using the eWallet app

**Event parameters**

| Name | Description | Example value |
| --- | --- | --- |
| merchant\_name | Name of merchant | cineplex |
| merchant\_ID | Specific ID attached to a business that tells the payment processing systems involved in a transaction where to send which funds | 123456 |

</Accordion>

<div data-zendesk-anchors="ewallet=-ewallet h_01HGTAEVWFZXCA7AV0P35W992F=-ewallet h_01HGTAEVWFR4QS6XAT1T28N1R5=important h_01HGTAEVWF8SVYTQMQ12219HX0=recommended-structures-for-predefined-events h_01HGTAEVWFBA3CD7ZA40VCER95=complete-registration-af_complete_registration h_01HGTAEVWGDBN8B3P2YHQJ5RYF=login-af_login h_01HGTAEVWGYFYEZBD3ZED7GGFG=content-view-af_content_view h_01HGTAEVWG39P9A84P926BG3VE=recommended-structures-for-custom-events h_01HGTAEVWGNYC5Z0ACHV8CFVNQ=wallet-complete-topup-wallet_complete_topup h_01HGTAEVWG36K4V4Z0NN8QYDNV=payment-transaction-completed-payment_transaction_completed h_01HGTAEVWG136M86GM1JPV74RH=bill-payment-success-bill_payment_success h_01HGTAEVWG34EXM28GW2ZN0NRC=promo-promo h_01HGTAEVWG0EHESWPQHCX4P3SH=voucher-redeem-voucher_redeem h_01HGTAEVWGKGC7N8ZB0MMQJ4YE=select-merchant-select_merchant h_01HGTAEVWG20101JC5VVK29Y0E=scan-barcode-success-scan_barcode_success" />

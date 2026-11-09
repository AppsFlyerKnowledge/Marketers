---
title: Recording multiple agency/MCC Google Ads accounts
metadata:
  keywords:
    - Advertisers
    - Multiple Agencies
    - MCC
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-09-28T11:11:04Z'
  edited_at: '2023-03-12T12:50:37Z'
  id: 115004970386
  locale: en-us
  section: Google Ads
  section_id: 6551205645457
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115004970386-Recording-multiple-agency-MCC-Google-Ads-accounts
---
> **At a glance:** Set up recording for different Google Ads accounts so traffic gets attributed correctly.

<div id="introduction" />

## Introduction

Google Ads traffic often comes from various accounts, such as agencies specializing in Google Ads or even different local teams within the app owner’s organization. It is important to understand how to set up recordings for different Google Ads accounts so that attribution goes to the correct parties.

This article covers these cases, from measuring agencies to using MCCs and also MCCs of MCCs.

<div id="note" />

> 📘 **Note**
>
> The following applies **only** to clients using the Google Ads new API.

For details on agency account configuration on Google Ads <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-agencies">click here</Anchor>.

<div id="important-definitions" />

## Important definitions

* **Link ID** – **a** **unique identifier of a mobile app defined on Google Ads**.

<div id="note-1" />

> 📘 **Note**
>
> Android and iOS versions of the same app require different link IDs.

* **Customer ID** – **unique identifier of a Google Ads account**.  
  Every account can advertise multiple link IDs, for example, for all the apps of the company. When linking agency accounts with existing apps on AppsFlyer’s dashboard, you can define up to 10 customer IDs.
* **MCC** - A Google Ads manager account (MCC, formerly called My Clients Center) is a Google Ads **tool for handling multiple Google Ads accounts**.  
  With an MCC account, you can link several accounts so you can view them in a single location (<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186?hl=en&ref_topic=7554904">Read more</Anchor>).

<div id="setting-up-google-ads-recording" />

## Setting up Google Ads recording

AppsFlyer can record a single link ID per app. **When multiple accounts handle the same app, they should all use the same link ID.** This should be configured on AppsFlyer’s dashboard for attribution purposes.

<div id="sharing-google-link-id-with-another-account" />

### Sharing Google link ID with another account

App owners having a single Google Ads account, or that plan on working with agencies running Google Ads traffic should use the following method.

The app owner can share any link ID with any other account, identified by its customer ID, as the capture below shows. Here are some more details about <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-agencies#setting-up-google-ads-attribution-for-agencies">sharing the link ID with an agency</Anchor>.

<div id="important" />

> 🚧 **Important**
>
> * If MCC is the Recording Manager for subaccounts then there is no need to share the Link ID from the MCC to the subaccounts. However, if a subaccount, under the MCC is its own recording manager, then the MCC must share the Link ID with the subaccount Recording Manager.
> * Importing Conversions: If MCC is the Recording Manager then the MCC is responsible for importing conversions for the subaccounts controlled by it. However, if a subaccount under the MCC is its own recording manager then that subaccount must also import the conversions.

<div id="note-2" />

> 📘 **Note**
>
> * On the Google Ads dashboard click (3 dots) >> ***Linked accounts*** >> ***Third-party app analytics details*** [![](https://files.readme.io/3fa87bcaa7f1eecfdee20d6d7568e71bcc2ffe6ba20334fe473279ae484b2294-115016034186.png)](https://files.readme.io/3fa87bcaa7f1eecfdee20d6d7568e71bcc2ffe6ba20334fe473279ae484b2294-115016034186.png)
> * The other account needs to approve the "share".
> * As a result, the other account is authorized to run Google Ads campaigns for the app.

<div id="tip" />

> 👍 **Tip**
>
> AppsFlyer recommends sharing the Link ID from the advertiser’s main account to the other accounts, rather than directly generating link IDs in those accounts. This is the fastest option, and also enables easy detachment between the advertiser and the agencies once the mutual work is completed.

<div id="mcc" />

## MCC

Agencies or large advertisers, who manage multiple Google Ads accounts, often use an MCC (My Client Center), which enables viewing all their accounts in a single location.

During the MCC setup, it is possible to configure whether the MCC or the Subaccounts manage the conversions.

<Image align="center" alt="MCC_1_new.png" src="https://files.readme.io/3320465f5def5f3da9afdb028577e49cdbf0b5b9ddf2f04ce708b8a31c5d9cc3-360001513758.png" />

This setup can be modified afterward if needed.

<Image align="center" alt="mmc-googleads-settings.png" src="https://files.readme.io/d0f0ffda25f88d5a37c8466818170243ed9f0040b3a3ad03e860d9a92bf59d4d-11240341292049.png" />

<div id="mcc-of-mccs" />

## MCC of MCCs

<Image align="center" alt="" src="https://files.readme.io/21ae6517c8d933b654a7fd1b5af7987958b3982310f0ad5249d830abf47e7943-115016041206.png" />

Big advertisers working with multiple agencies may use an MCC of MCCs account. Similar to the standard MCC account. It is recommended that the highest level MCC of MCCs or Advertiser is the one to generate the link ID. The correct setup for this structure requires the subaccounts to select the correct level of MCC (most likely, the highest level of MCC) as the Recording Manager. If this is the setup used, then the Link ID does not need to be shared with subaccounts and the import conversions at the highest level are sufficient.

<div id="tip-1" />

> 👍 **Tip**
>
> For additional information about MCCs and hierarchies of accounts, see the links below:
>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7456530">Linking accounts to your account manager</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7519925?hl=en&ref_topic=7554359">Viewing hierarchy for your manager account</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/topic/7554359?hl=en&ref_topic=6031997">Working with managed accounts</Anchor>
>
> For questions regarding account structures and recommendations, consult with your Google representative.

<div id="opening-a-google-ads-campaign" />

## Opening a Google Ads campaign

An MCC can’t open a Google Ads campaign directly. Rather, this must be done via a standard Google Ads subaccount.

There are two options for conversion recording:

1. **MCC manages subaccount recording**  
   Common for when there are different teams within the same company, for example, **Google Ads account per geo region in the same company**.  
   The MCC holds the recording configuration (Recording Manager) for all its subaccounts. Any changes in the recording configuration are done only at the MCC level and all subaccounts inherit it automatically.  
   The MCC also needs to import the conversions, which is done once and covers all subaccounts, and also get the link IDs shared for the subaccounts.
2. **Subaccounts manage own recording**  
   Common for accounts that are not connected except for a single entity serving them, for example, **one agency serving different advertiser client accounts**.  
   Importing the conversions, in this case, needs to be done with every subaccount separately. AppsFlyer records a single link ID per app, so for mobile recording, the MCC or advertiser must share the link ID with the subaccounts.

The conversions on Google Ads can be imported ONLY after the first instance of any conversion occurs, whether install or in-app event.
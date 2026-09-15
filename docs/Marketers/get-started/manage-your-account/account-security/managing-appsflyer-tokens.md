---
title: "Managing AppsFlyer tokens"
excerpt: "Learn how to manage AppsFlyer API and server-to-server tokens to securely access data and integrate with external systems."
---
**At a glance:** Tokens enhance data security. They enable users to access data via the AppsFlyer APIs or receive event data using server-to-server calls. Admins can manage multiple tokens while maintaining data continuity. This includes creating, renaming, and removing API and server-to-server tokens as necessary.

> ❗️ Important!
>
> * Only admins can view and manage tokens. Account users have no access to the Tokens page.
> * Keep your tokens safe, as they enable access to your data. Don't publish tokens in public code repositories.
> * It's recommended to replace tokens every 180 days.

## About AppsFlyer tokens

Tokens are used to enable users to access data via AppsFlyer API and S2S calls. Admins use the tokens for various purposes:

- Security measures:
  - Replacing tokens to address specific security concerns, such as a token compromise or suspected unauthorized access
  - Periodically replacing tokens as part of routine security policy updates
- Managing different API calls
- Testing purposes
- For use with particular features, such as the OneLink API

## Reaching the Tokens page

1. From the top bar, open the account menu (email address dropdown) > **Security center.**
2. In the **AppsFlyer API tokens** section, click **Manage your AppsFlyer API tokens.** The current tokens are displayed.

## Token types

There are various types of tokens for different purposes. By default, an API token is generated for each new account (API token V2). Admins can create a maximum of two tokens for each type, as detailed in the table below.

| Token type | Intended use |
| --- | --- |
| API token | A JWT token (JSON Web Token) used to authorize API calls, such as Pull API, Cohort API, ROI API, and others. |
| [OneLink API](https://support.appsflyer.com/hc/articles/360001250345) (premium) | A unique token used for OneLink API, which generates personalized links for optimal user engagement in large-scale campaigns. |
| S2S token | Used for sending data using server-to-server calls. |
| MCP token | Used to authenticate third-party or self-hosted systems with the AppsFlyer MCP. |

## Manage your tokens

As an admin, you can manage multiple tokens: create, rename, and remove tokens. The main use would be to replace current tokens with new ones. This is done by first [creating](/docs/managing-appsflyer-tokens#create-a-token) a new token, implementing it in your systems, and after it becomes available, [deleting](/docs/managing-appsflyer-tokens#delete-a-token) the old token.

### Retrieve tokens

1. From the top bar, open the account menu (email address dropdown) > **Security center.**
2. In the **AppsFlyer API tokens** section, click **Manage your AppsFlyer API tokens.**
3. The available tokens are displayed.
4. Copy the required token.

### Create a token

1. From the [**Tokens** page](/docs/managing-appsflyer-tokens#reaching-the-tokens-page), click **+ New token**.
2. Enter the token name.
3. Select the token type.
4. Click **Create token**.

> 📘 Note
>
> * API V2 tokens are active immediately after you create them.
> * S2S, OneLink, and other token types may take up to 30 minutes to become active.
>   * Until activation is complete, the token status is **Pending**.
>   * Use the token only after its status changes to **Active**.
> * Make sure to implement the new token in your systems.

### Delete a token

> 🚧 Caution
>
> * Deleting a token could cause failure to systems depending on it.
> * When deleting a token, it's removed from the Tokens page, and all calls from the previous token are rejected.
> * If you wish to replace a token, make sure to first create a new token, implement it, and only after it becomes available, meaning it's not in "Pending" status, you can delete the old token.

1. From the [**Tokens** page](/docs/managing-appsflyer-tokens#reaching-the-tokens-page), click the delete icon of the token you want to delete.
2. You must confirm deleting the token by typing "Delete token".
3. Click **Delete token**.

## Applications of the API V2 token

Use cases for advertisers and ad networks using the API V2 token:

<Tabs>
<Tab title="Advertiser">

| API V2 token |
| --- |
| [Pull API raw data](/docs/pull-api-raw-data) |
| [Pull API aggregate data](https://support.appsflyer.com/hc/articles/207034346) |
| [Get app list](https://support.appsflyer.com/hc/articles/360011999877) |
| [Cohort](https://support.appsflyer.com/hc/articles/360004799057) |
| [SKAdNetwork aggregate reporting](https://support.appsflyer.com/hc/articles/360014104157) |
| [Copy partner integration settings](https://dev.appsflyer.com/hc/reference/post_copy) |
| [Set install referrer decryption key](https://dev.appsflyer.com/hc/reference/post_v1-integration-params) |
| [Net Revenue API](/docs/set-up-tax-and-store-commission-rates-with-the-net-revenue-api) |
| [OpenDSR API](https://support.appsflyer.com/hc/articles/11332840660625) |
| [Master API](https://support.appsflyer.com/hc/articles/213223166) |
| [Import audience API](https://support.appsflyer.com/hc/articles/360013291857-Audiences-import-an-audience#imported-audience-management-api) |

</Tab>
<Tab title="Ad network">

| API V2 token |
| --- |
| [App list for ad networks](/docs/app-list-api-for-ad-networks) |
| [Integration with campaign management platforms](https://support.appsflyer.com/hc/articles/360005854857) |
| [Protect360 reports for integrated partners](/docs/protect360-for-integrated-partners#protect360-ad-network-reporting-api) |
| [InCost](https://support.appsflyer.com/hc/articles/360007714957) |

</Tab>
</Tabs>

## Applications of the S2S token

Use cases for advertisers and advertisers using the S2S token:

<Tabs>
<Tab title="Advertiser">

| S2S token |
| --- |
| [Mobile in-app events S2S API](https://support.appsflyer.com/hc/articles/207034486) |
| [Web events S2S API](https://support.appsflyer.com/hc/articles/45670116601617--Beta-Server-to-Server-S2S-API-for-Web-Attribution) |

</Tab>
<Tab title="Ad network">

| S2S token |
| --- |
| [AppsFlyer preload referrer attribution](/docs/set-up-appsflyer-preload-referrer-attribution) |

</Tab>
</Tabs>

> 📘 Note
>
> For most ad networks, S2S token generation is no longer self-serve. As a result, admins won’t see the option to generate an S2S token in the UI. Self-serve token generation is available only for specific managed partners.

## Applications for the OneLink token

Use cases for advertisers using the OneLink API token:

[Create](https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link), [get](https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link), [update](https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link), and [delete](https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link) OneLink short URLs with customized parameters.

## Applications for the MCP token

See the [AppsFlyer MCP article](/docs/beta-appsflyer-mcp) to see available use cases for MCP tokens.
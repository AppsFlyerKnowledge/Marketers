---
title: Managing AppsFlyer tokens
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-01-01T09:50:22Z'
  edited_at: '2026-09-23T09:06:11Z'
  id: 360004562377
  locale: en-us
  section: Account security
  section_id: 6551173202065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360004562377-Managing-AppsFlyer-tokens
---
> **At a glance:** Tokens enhance data security. They enable users to access data via the AppsFlyer APIs or receive event data using server-to-server calls. Admins can manage multiple tokens while maintaining data continuity. This includes creating, renaming, and removing API and server-to-server tokens as necessary.

<div id="important" />

> 🚧 **Important!**
>
> <Image align="center" alt="AppsFlyerAdmin_us-en.png" src="https://files.readme.io/8597603fc60e16b6ee5048c90e6293bf42c4acf8b63d553d6f77c34ab7945d02-32934372878481.png" />
>
> * Only admins can view and manage tokens. Account users have no access to the Tokens page.
> * Keep your tokens safe, as they enable access to your data. Don't publish tokens in public code repositories.
> * It's recommended to replace tokens every 180 days.

<div id="about-appsflyer-tokens" />

## About AppsFlyer tokens

Tokens are used to enable users to access data via AppsFlyer API and S2S calls. Admins use the tokens for various purposes:

* Security measures:
  * Replacing tokens to address specific security concerns, such as a token compromise or suspected unauthorized access
  * Periodically replacing tokens as part of routine security policy updates
* Managing different API calls
* Testing purposes
* For use with particular features, such as the OneLink API

<div id="reaching-the-tokens-page" />

## Reaching the Tokens page

1. From the top bar, open the account menu (email address dropdown) > **Security center.**
2. In the **AppsFlyer API tokens** section, click **Manage your AppsFlyer API tokens.** The current tokens are displayed.

<div id="token-types" />

## Token types

There are various types of tokens for different purposes. By default, an API token is generated for each new account (API token V2). Admins can create a maximum of two tokens for each type, as detailed in the table below.

| Token type | Intended use |
| --- | --- |
| <span id="api-token"></span>API token | A JWT token (JSON Web Token) used to authorize API calls, such as Pull API, Cohort API, ROI API, and others. |
| <span id="onelink-api-premium"></span><Anchor target="_blank" href="/marketers/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> (premium) | A unique token used for OneLink API, which generates personalized links for optimal user engagement in large-scale campaigns. |
| <span id="s2s-token"></span>S2S token | Used for sending data using server-to-server calls. |
| <span id="mcp-token"></span>MCP token | Used to authenticate third-party or self-hosted systems with the AppsFlyer MCP. |

<div id="note" />

> 📘 **Note**
>
> If you're integrating a feature that requires a dedicated API V2 token (e.g., the <Anchor target="_blank" href="/marketers/docs/beta-advanced-security-protect360-module">Advanced Security Module</Anchor>) and you've already reached the two-token limit, you can repurpose an existing API V2 token rather than requesting a new one — the same token can serve multiple use cases.

<div id="manage-your-tokens" />

## Manage your tokens

As an admin, you can manage multiple tokens: create, rename, and remove tokens. The main use would be to replace current tokens with new ones. This is done by first [creating](#create-a-token) a new token, implementing it in your systems, and after it becomes available, [deleting](#delete-a-token) the old token.

<div id="retrieve-tokens" />

### Retrieve tokens

1. From the top bar, open the account menu (email address dropdown) > **Security center.**
2. In the **AppsFlyer API tokens** section, click **Manage your AppsFlyer API tokens.**
3. The available tokens are displayed.
4. Copy the required token.

<div id="create-a-token" />

### Create a token

1. From the [**Tokens** page](#reaching-the-tokens-page), click **+ New token**.
2. Enter the token name.
3. Select the token type.
4. Click **Create token**.

<div id="note-1" />

> 📘 **Note**
>
> * API V2 tokens are active immediately after you create them.
> * S2S, OneLink, and other token types may take up to 30 minutes to become active.
>   * Until activation is complete, the token status is **Pending**.
>   * Use the token only after its status changes to **Active**.
> * Make sure to implement the new token in your systems.

<div id="delete-a-token" />

### Delete a token

<div id="warning" />

> ❗️ **Warning**
>
> * Deleting a token could cause failure to systems depending on it.
> * When deleting a token, it's removed from the Tokens page, and all calls from the previous token are rejected.
> * If you wish to replace a token, make sure to first create a new token, implement it, and only after it becomes available, meaning it's not in "Pending" status, you can delete the old token.

1. From the [**Tokens** page](#reaching-the-tokens-page), click the delete icon of the token you want to delete.
2. You must confirm deleting the token by typing "Delete token".
3. Click **Delete token**.

<div id="applications-of-the-api-v2-token" />

## Applications of the API V2 token

Use cases for advertisers and ad networks using the API V2 token:

<div id="advertiser" />

### Advertiser

| API V2 token |
| --- |
| <Anchor target="_blank" href="/marketers/docs/pull-api-raw-data">Pull API raw data</Anchor> |
| <Anchor target="_blank" href="/marketers/docs/pull-api-aggregate-data">Pull API aggregate data</Anchor> |
| <Anchor target="_blank" href="/marketers/docs/app-list-api-for-app-owners">Get app list</Anchor> |
| <Anchor target="_blank" href="/marketers/docs/cohort-api">Cohort</Anchor> |
| <Anchor target="_blank" href="/marketers/docs/skan-aggregated-performance-report-api">SKAdNetwork aggregate reporting</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_copy">Copy partner integration settings</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Set install referrer decryption key</Anchor> |
| <Anchor target="_blank" href="/marketers/docs/set-up-tax-and-store-commission-rates-with-the-net-revenue-api">Net Revenue API</Anchor> |
| <Anchor target="_blank" href="/marketers/docs/send-opendsr-api-requests">OpenDSR API</Anchor> |
| <Anchor target="_blank" href="/marketers/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor> |
| <Anchor target="_blank" href="/marketers/docs/audiences-import-audience-segments-from-internal-systems#imported-audience-management-api">Import audience API</Anchor> |
| <Anchor target="_blank" href="/marketers/docs/beta-advanced-security-protect360-module">Advanced Security Module integration (Android)</Anchor> |

<div id="ad-network" />

### Ad network

| API V2 token |
| --- |
| <Anchor target="_blank" href="/partners/docs/app-list-api-for-ad-networks">App list for ad networks</Anchor> |
| <Anchor target="_blank" href="/partners/docs/access-to-aggregated-analytics-tools-for-api-partners">Integration with campaign management platforms</Anchor> |
| <Anchor target="_blank" href="/partners/docs/protect360-for-integrated-partners#protect360-ad-network-reporting-api">Protect360 reports for integrated partners</Anchor> |
| <Anchor target="_blank" href="/partners/docs/incost-api-for-ad-networks">InCost</Anchor> |

<div id="applications-of-the-s2s-token" />

## Applications of the S2S token

Use cases for advertisers and advertisers using the S2S token:

<div id="advertiser-1" />

### Advertiser

| S2S token |
| --- |
| <Anchor target="_blank" href="/marketers/docs/server-to-server-events-api-for-mobile-s2s-mobile">Mobile in-app events S2S API</Anchor> |
| <Anchor target="_blank" href="/marketers/docs/server-to-server-s2s-api-for-web-performance-measurement">Web events S2S API</Anchor> |

<div id="ad-network-1" />

### Ad network

| S2S token |
| --- |
| <Anchor target="_blank" href="/marketers/docs/set-up-appsflyer-preload-referrer-attribution">AppsFlyer preload referrer attribution</Anchor> |

<div id="note-2" />

> 📘 **Note**
>
> For most ad networks, S2S token generation is no longer self-serve. As a result, admins won’t see the option to generate an S2S token in the UI. Self-serve token generation is available only for specific managed partners.

<div id="applications-for-the-onelink-token" />

## Applications for the OneLink token

Use cases for advertisers using the OneLink API token:

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">Create</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">get</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">update</Anchor>, and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">delete</Anchor> OneLink short URLs with customized parameters.

<div id="applications-for-the-mcp-token" />

## Applications for the MCP token

See the <Anchor target="_blank" href="/marketers/docs/beta-appsflyer-mcp">AppsFlyer MCP article</Anchor> to see available use cases for MCP tokens.

<div data-zendesk-anchors="01HFNX0XS4RAB543NKR12B2W50=important overview=about-appsflyer-tokens h_01HFY5D0E1H66CEB3KMJQEXV4K=about-appsflyer-tokens h_01HFTT570KF3XM9MBSFYRDYN9S=reaching-the-tokens-page h_01HFBR7KP8BZN7KH0BNJ982WK8=token-types h_01M36NWJZ03NKZVAC2SCTAWBFX=note h_01HFY5D0E1AF4NYPX31W3VJYQC=manage-your-tokens retrieving-api-tokens=retrieve-tokens h_01HBQN3T2HKEMNC8MSR0THYW2S=retrieve-tokens h_01HFY5D0E1FECQC1HN0EXWMXAV=create-a-token h_01HFY5D0E1HJFKFPRT8WVNPHDG=note-1 h_01HFY5D0E2B1KXGSFZR0AYAER5=delete-a-token h_01HFY5D0E2KZYG0J2R7GR1R7W5=warning h_01HG64DMW7PYRXBMZN00EQN991=applications-of-the-api-v2-token v20-token%E2%80%94advertiser-apis=advertiser h_01HBQN7TBASK192P8D7AEWM9P6=advertiser v20-token%E2%80%94ad-network-apis=ad-network h_01HBQN7TBAWAHEQXMYK9V14G0M=ad-network h_01HG64M8K1PPY2Z2406MC78EEN=applications-of-the-s2s-token advertiser=advertiser-1 h_01JSKCVT6ACKHECVJGZ0QVD8C6=advertiser-1 h_01JSKD341C1EKE51Z16MMPG3Ckjh=ad-network-1 ad-network=ad-network-1 h_01KKBYBR8M9ZJWVB3MP1QG4FR4=note-2 h_01JSKCWS5406YQJP3RR9KAXJC9=applications-for-the-onelink-token h_01K9YD2Y9M1C8QDBS5H048XYYD=applications-for-the-mcp-token" />

---
title: "Set up your API allowlist"
excerpt: "Protect your AppsFlyer account by defining an API allowlist to restrict API calls to authorized IP addresses."
---
Protect your AppsFlyer account by defining an API allowlist.

## ![API allowlist](https://files.readme.io/05f8c46f81b679e2881bf72255ae835a70d1cb3be1ea862b90053c2c259f25b6-4423224122385.png)

## Overview

Protect your data from unauthorized access by setting up an API allowlist that specifies the IP addresses that can make API calls to your AppsFlyer account. Once your allowlist is active, only API calls originating from those IP addresses will be permitted while calls from all other IP addresses will be denied.

> 📘 Note
>
> * Only admins can access and manage the allowlist.
> * Use of the allowlist is optional and is inactive by default.
> * Activation of the allowlist is at the account level and applies to all apps in the account.

## Set up your API allowlist

### Set up the allowlist

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/bcee04c81f386f19d25893568f8ddeb0427d386153b2659968a9652e3506c5e6-4406016448401.png) To set up and activate the API allowlist:**

1. From the top bar, open the account menu (email address dropdown) > **Security center**.
2. In the API allowlist section, click **Manage API allowlist**.
3. Enter an IP address or range of IP addresses in standard format:
   - Examples: `192.168.1.1`, `185.114.120.140`
   - To enter a range of IP addresses, use this format: `185.114.120.1/32` (where `185.114.120.1` is the first address in the range and `185.114.120.32` is the last address in the range).
4. Click **Apply.**
5. [Optional] Click **+ Add** to add an additional IP address or range to the list.
6. Click the **Save list** button.
7. Set the allowlist to **Active.**

> 📘 Note
>
> The allowlist must contain at least one IP address or range before you can save and activate it.

### Edit the allowlist

You can add or delete IP addresses from the allowlist at any time (whether or not the list is active).

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/bcee04c81f386f19d25893568f8ddeb0427d386153b2659968a9652e3506c5e6-4406016448401.png) To add an IP address or range:**

1. From the top bar, open the account menu (email address dropdown) > **Security center**.
2. In the API allowlist section, click **Manage API allowlist**.
3. Click **+ Add** to add an IP address or range to the list.
4. Enter an IP address or range.
5. Click **Apply.**
6. Be sure to save your changes by clicking the **Save list** button.

> 📘 Note
>
> The list status (active or inactive) will not change when you save the list. Be sure to check the status of the **Active** toggle and activate/deactivate if necessary.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/bcee04c81f386f19d25893568f8ddeb0427d386153b2659968a9652e3506c5e6-4406016448401.png) To delete an IP address or range:**

1. From the top bar, open the account menu (email address dropdown) > **Security center**.
2. In the API allowlist section, click **Manage API allowlist**.
3. Click the trash icon next to the IP address you want to delete.
4. In the confirmation popup, click **Delete.**
5. Be sure to save your changes by clicking the **Save list** button.

### Allowlist specifications

- To protect your account from unauthorized API calls, the allowlist must be set to **Active** and include at least one IP address or range.
- The allowlist applies to all [AppsFlyer APIs that utilize the V2.0 token](/docs/managing-appsflyer-tokens#applications-of-the-api-v2-token). Calls from APIs that use the V1.0 API token will be permitted from all API addresses.
- Up to 20 IP addresses or ranges can be added to the allowlist.
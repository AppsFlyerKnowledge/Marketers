---
title: Bidalgo - Google Ads—Campaign configuration
excerpt: >-
  Bidalgo, an AppsFlyer integrated partner, is a leading provider of Artificial
  Intelligence solutions to help app marketers scale their growth.
metadata:
  keywords:
    - Advertisers
    - Bidalgo
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2018-07-19T11:46:44Z'
  edited_at: '2026-06-16T09:36:22Z'
  id: 360001325405
  locale: en-us
  section: Google Ads
  section_id: 6551205645457
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360001325405-Bidalgo-Google-Ads-Campaign-configuration
---
## Set up Bidalgo integration

**Prerequisite:** Before setting up the integration, make sure you contact the partner and open an account with them.

**New integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.
2. Select the relevant app.
3. Search for Bidalgo and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle. Keep it on as long as you work with Bidalgo.
5. Configure remaining tabs as needed below.

**Edit existing integration:**

In AppsFlyer, go to **Collaborate > Partner Integrations > Active integrations** tab, search for the partner, and make your changes.

> 📘 **Note**
>
> The Google Ads Customer ID must be entered **without** hyphens.

6. From your **Google Ads** account, copy the Customer ID (without hyphens) from the top left-hand corner and paste it into the AppsFlyer **Ads Customer ID** parameter as shown in the following screenshots.

[![](https://files.readme.io/50acdf0bc73854fd8c599cd89ffa168816cd9a0fc3b38bc794bd6f3d20807968-360002379489.png)](https://files.readme.io/50acdf0bc73854fd8c599cd89ffa168816cd9a0fc3b38bc794bd6f3d20807968-360002379489.png)

7. Enter the number in the **Google Ads Customer ID** field.

### In-app events

1. To send in-app event postbacks to Bidalgo, toggle the In-App Events Postback to **ON**.

2. Individually add the in-app events you want to send to Bidalgo and map them to the **Partner Event Identifier** field.

3. Select **Send Revenue** to send all the parameters including the revenue value (if it exists in the event).

4. Click **Save**.

> 📘 **Important Note**
>
> * Disabling attribution for Google Ads prevents sending postbacks to Google Ads Partners.
> * You can configure multiple Google Ads accounts (CID) to send postbacks (step 5) by separating each CID with a comma.

<div data-zendesk-anchors="h_01HKA1JNXMRJ8059FAJAEQ6RK5=set-up-bidalgo-integration h_01HKA1JNXM5R15CBVQ2WHT99Z9=note inapp-events=in-app-events h_01HKA1JNXM59W74725961FZA27=in-app-events h_01HKA1JNXMASTQ9X2144JCKKNQ=important-note" />

---
title: "Adquant by Kenshoo - Google Ads—Campaign configuration"
excerpt: "Optimize Google AdWords campaigns by using Adquant by Kenshoo. When configured, AppsFlyer sends postbacks to Adquant."
x-zendesk:
  id: 360000654357
  url: https://support.appsflyer.com/hc/en-us/articles/360000654357-Adquant-by-Kenshoo-Google-Ads-Campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Google Ads
  section_id: 6551205645457
  position: 12
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution, Ad Networks]
  labels: [Advertisers, Ad Networks, Kenshoo, Adquant, Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2018-12-09T07:43:55Z'
  edited_at: '2026-06-16T09:36:53Z'
---
## Setting up Adquant by Kenshoo

**Prerequisite:** Before setting up the integration, make sure you contact the partner and open an account with them.

**New integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.
2. Select the relevant app.
3. Search for Adquant by Kenshoo and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle. Keep it on as long as you work with Adquant by Kenshoo.
5. Configure remaining tabs as needed below.

**Edit existing integration:**

In AppsFlyer, go to **Collaborate > Partner Integrations > Active integrations** tab, search for the partner, and make your changes.

> 📘 **Note**
>
> The Google Ads Customer ID must be entered **without** hyphens.


6. From your **Google Ads** account, copy the Customer ID (without hyphens) from the top left-hand corner and paste it to the AppsFlyer **Ads Customer ID** parameter as shown in the screenshots below.

[![](https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png)](https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png)

7. Enter the **Action Identifier**, **Disable\_Country\_Sending** (provided by Adquant) and the **Google Ads Customer ID** number in the appropriate fields.

### In-app events

1. To send in-app event postbacks to Adquant by Kenshoo, toggle the In-App Events Postback to **ON**.

2. Individually add the in-app events you want to send to Adquant by Kenshoo and map them to the **Partner Event Identifier** field.

3. Select **Send Revenue** to send all the parameters including the revenue value (if it exists in the event).

4. Click **Save**

> 📘 **Important Note**
>
> * Disabling attribution for Google Ads prevents sending postbacks to Google Ads Partners.
> * You can configure multiple Google Ads accounts (CID) to send postbacks (step 5) by separating each CID with a comma.
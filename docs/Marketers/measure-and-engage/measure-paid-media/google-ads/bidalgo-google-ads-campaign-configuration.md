---
title: "Bidalgo - Google Ads—Campaign configuration"
excerpt: "Learn how to set up and configure the Bidalgo integration with Google Ads in AppsFlyer to scale your app growth using AI solutions."
---
**At a glance:** Bidalgo, an AppsFlyer integrated partner, is a leading provider of Artificial Intelligence solutions to help app marketers scale their growth.

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
> #### Note
>
> The Google Ads Customer ID must be entered **without** hyphens.


6. From your **Google Ads** account, copy the Customer ID (without hyphens) from the top left-hand corner and paste it into the AppsFlyer **Ads Customer ID** parameter as shown in the following screenshots.

[![](https://support.appsflyer.com/hc/article_attachments/360002379489)](https://support.appsflyer.com/hc/article_attachments/360002379489)

7. Enter the number in the **Google Ads Customer ID** field.

### In-app events

1. To send in-app event postbacks to Bidalgo, toggle the In-App Events Postback to **ON**.

2. Individually add the in-app events you want to send to Bidalgo and map them to the **Partner Event Identifier** field.

3. Select **Send Revenue** to send all the parameters including the revenue value (if it exists in the event).

4. Click **Save**.

> 📘 **Note**
>
> #### Important Note
>
> * Disabling attribution for Google Ads prevents sending postbacks to Google Ads Partners.
> * You can configure multiple Google Ads accounts (CID) to send postbacks (step 5) by separating each CID with a comma.
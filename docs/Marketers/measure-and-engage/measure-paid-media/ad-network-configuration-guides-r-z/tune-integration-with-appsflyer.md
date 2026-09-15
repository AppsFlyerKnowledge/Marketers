---
title: "TUNE integration with AppsFlyer"
excerpt: "Integrate AppsFlyer with TUNE to measure incoming traffic and enable deep linking into your mobile application."
---
**At a glance:** TUNE, an AppsFlyer integrated partner, is a partner marketing platform.  
Integrate with TUNE to measure incoming traffic and to enable deep linking into your app.

![](https://cdn.appsflyer.com/marketplace/static/logo/hasoffers.png)

## Setting up TUNE integration

AppsFlyer integration with TUNE supports click attribution.

**Prerequisite:** Before setting up the integration, make sure you contact the partner and open an account with them.

**To set up the integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.
2. Select the relevant app.
3. Search for Tune and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle. Keep it on as long as you work with Tune.
5. Configure remaining tabs as needed below.



| Settings tab | Remarks |
| --- | --- |
| **Integration** | Configure additional [integration](/docs/set-up-an-integrated-partner) settings as required.<br /><br />The Custom\_TUNE\_tracking\_domain field is used to build your specific endpoint URL. For example, if you enter "**greatapp**", your endpoint URL will be:  <br />https://**greatapp**.go2cloud.org/aff\_Isr?<br /><br />Use the same name for in-app events custom tracking domain. |
| **Attribution link** | Generate [attribution links.](/docs/set-up-an-integrated-partner#attribution-link-tab) |
| **Cost** | Get [cost data](/docs/set-up-an-integrated-partner#cost-tab). |
| **Ad revenue** | Not available for this partner |
| **Permissions** | Set ad network [permissions](/docs/set-up-an-integrated-partner#permissions-tab) as required. |



**To edit an existing integration:**

In AppsFlyer, go to **Collaborate > Partner Integrations > Active integrations** tab, search for the partner, and make your changes.

## Enabling deep linking into your app

Use [OneLink branded links](/docs/brand-onelink-with-your-domain) generated in AppsFlyer to measure clicks in TUNE. The following process enables deep linking users to a specific page in your app.

### Prerequisite

Verify  AppsFlyer mobile SDK versions:

* iOS: V4.9.0 or later
* Android: V4.9.0 or later

### Step 1: Configure links for your campaigns

* Create a [OneLink template](/docs/create-a-onelink-template#procedures) for your email campaigns.
* [Create a Branded link.](/docs/brand-onelink-with-your-domain)  
  When requested to add a CNAME to your domain, use `yourdomain.esplinks.appsflyer.com`, instead of the URL offered in the Branded Link creation page.  
  **Example:**
  * **Subdomain:** `click.example.com`
  * **CNAME:** `example.appsflyer.com`

    ![branded-link-esp-new-en_us.png](https://files.readme.io/a7433ac0e3b343195bac9b4be49d22c18534ec1c145189198c5ec467fea510bb-21323417936145.png)

    Note that when clicking **Verify** to verify the brand domain, a failure message regarding the AppsFlyer CNAME displays.

    ![branded-link-esp-cname-fail-message.png](https://files.readme.io/94f159a089152437111fc6e4308464bc48512ee18f5e249460006bfda05252c2-21323447961105.png)

    Ignore this message and change the CNAME as instructed above.

### Step 2: Set up the attribution link

1. Go to the Attribution link tab and copy only the link parameters under **Click attribution link** as highlighted below.[![](https://support.appsflyer.com/hc/article_attachments/4406164987537)](https://support.appsflyer.com/hc/article_attachments/4406164987537)
2. Add the copied parameters to your branded link.

   CALLSTART::Note::

   #### **Example:**

   ![TUNE-link-example2-en_us.png](https://files.readme.io/58f38eb0bb724b66d0c958454651e0950a54f6fd990220f2ac24f93ca89ba344-small-4410086650769.png)

   CALLEND::
3. To complete the setup, go to the [Managing Mobile Offers with AppsFlyer guide](https://support.tune.com/hc/en-us/articles/1500008336641-Managing-Mobile-Offers-with-Appsflyer) in TUNE's help center, scroll down to Universal Links via OneLink and follow the instructions.
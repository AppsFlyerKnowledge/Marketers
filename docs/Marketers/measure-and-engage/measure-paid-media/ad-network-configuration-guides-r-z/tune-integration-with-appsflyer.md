---
title: TUNE integration with AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-08-25T08:58:17Z'
  edited_at: '2026-07-07T09:51:48Z'
  id: 4406153487505
  locale: en-us
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4406153487505-TUNE-integration-with-AppsFlyer
---
**At a glance:** TUNE, an AppsFlyer integrated partner, is a partner marketing platform.  
Integrate with TUNE to measure incoming traffic and to enable deep linking into your app.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hasoffers.png" width="79px" />

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
| **Integration** | Configure additional <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">integration</Anchor> settings as required.<br /><br />The Custom\_TUNE\_tracking\_domain field is used to build your specific endpoint URL. For example, if you enter "**greatapp**", your endpoint URL will be:  <br />https://greatapp.go2cloud.org/aff_Isr?<br /><br />Use the same name for in-app events custom tracking domain. |
| **Attribution link** | Generate <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">attribution links.</Anchor> |
| **Cost** | Get <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#cost-tab">cost data</Anchor>. |
| **Ad revenue** | Not available for this partner |
| **Permissions** | Set ad network <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">permissions</Anchor> as required. |

**To edit an existing integration:**

In AppsFlyer, go to **Collaborate > Partner Integrations > Active integrations** tab, search for the partner, and make your changes.

## Enabling deep linking into your app

Use <Anchor target="_blank" href="/marketers/docs/brand-onelink-with-your-domain">OneLink branded links</Anchor> generated in AppsFlyer to measure clicks in TUNE. The following process enables deep linking users to a specific page in your app.

### Prerequisite

Verify  AppsFlyer mobile SDK versions:

* iOS: V4.9.0 or later
* Android: V4.9.0 or later

### Step 1: Configure links for your campaigns

* Create a <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#create-a-onelink-template">OneLink template</Anchor> for your email campaigns.
* <Anchor target="_blank" href="/marketers/docs/brand-onelink-with-your-domain">Create a Branded link.</Anchor>  
  When requested to add a CNAME to your domain, use `yourdomain.esplinks.appsflyer.com`, instead of the URL offered in the Branded Link creation page.  
  **Example:**
  * **Subdomain:** `click.example.com`
  * **CNAME:** `example.appsflyer.com`

    ![branded-link-esp-new-en_us.png](https://files.readme.io/a7433ac0e3b343195bac9b4be49d22c18534ec1c145189198c5ec467fea510bb-21323417936145.png)

    Note that when clicking **Verify** to verify the brand domain, a failure message regarding the AppsFlyer CNAME displays.

    ![branded-link-esp-cname-fail-message.png](https://files.readme.io/94f159a089152437111fc6e4308464bc48512ee18f5e249460006bfda05252c2-21323447961105.png)

    Ignore this message and change the CNAME as instructed above.

### Step 2: Set up the attribution link

1. Go to the Attribution link tab and copy only the link parameters under **Click attribution link** as highlighted below.[![](https://files.readme.io/51bb21c2fe4bd82965f30909fe5ed4ae6c5b906972789b143755982ea8b73f6e-4406164987537.png)](https://files.readme.io/51bb21c2fe4bd82965f30909fe5ed4ae6c5b906972789b143755982ea8b73f6e-4406164987537.png)
2. Add the copied parameters to your branded link.

   > 📄 **Example:**
   >
   > ![TUNE-link-example2-en_us.png](https://files.readme.io/58f38eb0bb724b66d0c958454651e0950a54f6fd990220f2ac24f93ca89ba344-small-4410086650769.png)

3. To complete the setup, go to the <Anchor target="_blank" href="https://support.tune.com/hc/en-us/articles/1500008336641-Managing-Mobile-Offers-with-Appsflyer">Managing Mobile Offers with AppsFlyer guide</Anchor> in TUNE's help center, scroll down to Universal Links via OneLink and follow the instructions.

<div data-zendesk-anchors="h_01HJZRGVZ1VQF4N93THDRT5YCJ=setting-up-tune-integration h_01HJZRGVZ1KJ80ZA1THKFZ535P=enabling-deep-linking-into-your-app h_01HJZRGVZ1ZC9G7M72V2HW4XDS=prerequisite h_01HJZRGVZ1GPR3NQQAXRBXV09Z=step-1-configure-links-for-your-campaigns h_01HJZRGVZ2F83PHABEWJXMMJ22=step-2-set-up-the-attribution-link h_01HJZRGVZ2435CGWY4FZ5FKKHV=example" />

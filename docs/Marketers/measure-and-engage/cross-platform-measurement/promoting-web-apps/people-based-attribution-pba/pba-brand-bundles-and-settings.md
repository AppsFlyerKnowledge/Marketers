---
title: "PBA brand bundles and settings"
excerpt: "Brand bundles consolidate the attribution, events, visits, and revenue of brand-related apps and websites. Use the brand bundle settings page to mark conversion events, integrate with Google Ads, and more."
x-zendesk:
  id: 360000646498
  url: https://support.appsflyer.com/hc/en-us/articles/360000646498-PBA-brand-bundles-and-settings
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, Cross-Platform Measurement]
  labels: [Advertisers, Bundles, Web Attribution, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2018-12-09T11:42:52Z'
  edited_at: '2025-05-08T09:17:30Z'
---
![BrandBundles.png](https://files.readme.io/eab9447f0bdd225ab7915724f996555057fa7f2840ec6e69a89465a90af6181e-360017356617.png)

## About brand bundles

Brands operate in an ecosystem encompassing both web and mobile properties. As an advertiser, a full picture of brand performance across platforms–web and mobile–is needed. In PBA, brand bundles consolidate the data of mobile and web properties into a single entity for purposes of analytics and raw data.

> 📘 **What is a web app?**
>
> A web app is an [entity you have created in AppsFlyer](/docs/adding-an-app-to-appsflyer) that specifies a website for which you want to measure performance.
>
> * The web app entity was added to AppsFlyer on February 9, 2022. Prior to that date, you entered the brand bundle domain as a separate setting when creating a brand bundle. Now, you first create a web app that defines the domain, then include that web app when creating a bundle.
> * If you had existing brand bundles on February 9, 2022, you will see that you now have a web app on the **My apps** page corresponding to each of those bundles. **Rest assured!** Your web traffic is being attributed just as it was before, and there have been no other changes to PBA dashboards or raw data reports.


**Brand bundle basics:**

* A brand bundle contains exactly 1 web app *(required)* and 1 or more mobile apps *(optional).*
* An app (web or mobile) can belong only to 1 bundle.
* Apps can't be deleted from a bundle or moved from one bundle to another without [deleting the original bundle](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle).
  * On bundle deletion, AppsFlyer stops attributing PBA data for the bundle, and access to its historical data is no longer available.

## Accessing brand bundles

Access the **Brand Bundles** page to manage brand bundles and their settings:

* In AppsFlyer, from the top menu, select **My Apps** > **View brand bundles.**  
                           - or -
* In AppsFlyer, from the side menu, go to **Settings** > **Brand Bundles.**

## Managing brand bundles

To add, delete, or manage brand bundles, select one of these options from the **Brand Bundles** page:



| Option | Details |
| --- | --- |
| Add a brand bundle | Opens the **Create bundle** page  <br />Follow the [instructions below](/docs/pba-brand-bundles-and-settings#add-brand-bundle) to create a new bundle. |
| PBA dashboard | Opens the brand dashboard |
| Brand bundle ID | Copies brand bundle ID to the clipboard |
| Web dev key | Copies the web dev key to the clipboard |
| Select an existing bundle to update brand bundle settings and options | Options available:<br /><br />* Mark events as conversion events:<br />  * [Web event settings](/docs/pba-brand-bundles-and-settings#web-event-settings)<br />  * [In-app event settings](/docs/pba-brand-bundles-and-settings#inapp-event-settings)<br />* [Domain exclusion](/docs/pba-brand-bundles-and-settings#domain-exclusion)<br />* [Google Ads integration](/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba) |
| Delete icon | [Deletes the selected brand bundle](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) (after you confirm your decision to do so) |



### Add brand bundle

Before proceeding, make sure that all the apps you want to include in the bundle have been added to your account. Once a brand bundle has been created, the apps it includes can not be changed without [deleting the bundle](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) and recreating it.

**To add a brand bundle:**

1. From the [Brand Bundles](/docs/pba-brand-bundles-and-settings#accessing-brand-bundles) page, click **Add brand bundle.**
2. Enter the **Brand bundle name** (any name you want to use to identify the bundle).
3. Select the apps to include in the bundle.

   **Note:** Apps that are included in other bundles are not available for selection.

   * Web app *[required]*: Select 1 available web app.
   * Mobile apps *[optional]:* Select the available mobile apps you want to include in the bundle.
     * Mobile apps are not required to create a bundle.
     * There is no limit to the number of mobile apps you can include in a bundle.
4. Click Create bundle.

> 📘 **Important!**
>
> Brand bundles cannot be created in the following circumstances:
>
> * The web app selected for inclusion in the bundle does not point to a valid URL.
> * The web app and an Android mobile app selected for inclusion in the bundle have the same app ID.


### Web event settings

There are two types of web events: **standard** and **conversion**. To focus and prioritize your optimization efforts, set some events as conversion events.

* PBA attributes standard and conversion events in the same way.
* [Raw data](/docs/raw-data-reporting-overview) reports include both standard and conversion events.
* PBA dashboards include conversion events only.
* An event type can be changed at any time; however, the change isn't retroactive.

**To set conversion events:**

1. From the [Brand Bundles](/docs/pba-brand-bundles-and-settings#accessing-brand-bundles) page, select the brand bundle.  
   The **Update Brand bundles** page opens.
2. Go to the **Web event settings** tab.
3. Turn on **Mark as conversion event**as required.
4. Click **Update bundle.**

### In-app event settings

In-app events having revenue are marked as conversion events [Default]. **Note!** If you change the default events, you must explicitly mark in-app revenue events yourself.

**To mark in-app events as conversion events:**

1. From the [Brand Bundles](/docs/pba-brand-bundles-and-settings#accessing-brand-bundles) page, select the brand bundle.  
   The **Update Brand bundles** page opens.
2. Go to the **In-app event settings** tab.
3. Turn on **Mark as conversion event**as required.
4. Click **Update bundle.**

### Domain exclusion

A domain exclusion mechanism, part of [PBA media source rules,](/docs/pba-media-source-attribution-rules) is implemented to prevent:

* Self-attribution: In other words, AppsFlyer will not attribute events to the website defined in the web app itself and to domains you specify are associated with that website.
* Attributing or recording events associated with domains that aren't part of your brand but participate in the user flow (for example, payment gateways).



| Domain type | Description | Impact of exclusion |
| --- | --- | --- |
| Primary | The domain of the **web app** included in the brand bundle. This includes sub-domains.<br /><br />For example, if your domain is mydomain.co.za then subdomains like a.mydomain.co.za, b.mydomain.co.za are excluded automatically. <br /><br />The domain of a web app cannot be changed without [deleting](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) and recreating the web app. (This also means deleting the bundle in which the web app is included). | No self-attribution |
| Internal | List other domains forming part of your brand, for example, mydomain.com, mydomain.in, mydomain.co.ng, abc.com | No self-attribution |
| External (listed by you) | Domains used by your website directly, but not part of the brand. These include payment gateways, payment processing sites, etc. | [Visits are disregarded](/docs/pba-media-source-attribution-rules#visit-recognition-rules) |
| External (listed by AppsFlyer) | Domains listed by AppsFlyer and always excluded.<br /><br />* PayPal<br />* Stripe<br />* Adyen<br /><br />The list of automatic domains cannot be edited. | [Visits are disregarded](/docs/pba-media-source-attribution-rules#visit-recognition-rules) |



**To exclude internal or external domains:**

1. From the [Brand Bundles](/docs/pba-brand-bundles-and-settings#accessing-brand-bundles) page, select the brand bundle.  
   The **Update Brand bundles** page opens.
2. Go to the **Domain exclusion** tab.
3. Click **Add domain.**
4. Enter a domain name.
5. Select a domain type: **Internal** or **External.**
6. Click **Add domain.**  
   It takes one hour for the exclusion to take effect.

## FAQ

### Can I include the same app in more than one bundle?

**No.** Once an app is added to a bundle, it can't be added to another bundle.

### Can I add or remove apps after creating a bundle?

**No.** Once a bundle has been created, the apps included in it cannot change.

**Why?** Each app has its own data, and AppsFlyer uses this data to analyze the user journey across platforms (web and app). If an app changed, this would involve a different set of data that is not compatible with the previous data.

### How do I add or remove (delete) apps from a bundle?

To change the bundle in which an app is included, delete the original bundle and create a new one that includes the app.

### What happens if I delete a bundle?

#### faqs what happens if i delete a bundle

If you delete a bundle:

* AppsFlyer stops attributing the bundle.
* The bundle data is retained (in other words, it's not permanently deleted), but the bundle itself can't be restored in order to view the data.

  **Why?** A new bundle uses a different web dev key so, even if it includes the same apps, the original bundle is not restored.

### Why are certain apps not available for me to add to a bundle?

* **Admins:** If you can't select an app when creating a bundle, be sure the app has been added to your AppsFlyer account and is not included in another bundle.
* **Other account users:** Check with an account admin to ensure you have the required role and permissions to access to the apps you are trying to add.

### Why do I get the "We couldn't find that Page" error when I try to view or create a brand bundle?

You probably didn’t subscribe to PBA. Please contact your CSM or [hello@appsflyer.com](mailto:hello@appsflyer.com) to upgrade your package.

> 📘 **See also**
>
> * [Onboarding guide to PBA](/docs/onboarding-guide-to-people-based-attribution)
> * [PBA getting started](/docs/people-based-attribution-pba-overview)
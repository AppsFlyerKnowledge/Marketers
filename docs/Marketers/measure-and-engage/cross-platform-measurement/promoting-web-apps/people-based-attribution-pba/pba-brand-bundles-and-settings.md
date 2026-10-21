---
title: PBA brand bundles and settings
metadata:
  keywords:
    - Advertisers
    - Bundles
    - Web Attribution
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2018-12-09T11:42:52Z'
  edited_at: '2025-05-08T09:17:30Z'
  id: 360000646498
  locale: en-us
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360000646498-PBA-brand-bundles-and-settings
---
**At a glance:** Brand bundles consolidate the attribution, events, visits, and revenue of brand-related apps and websites. Use the brand bundle settings page to mark conversion events, integrate with Google Ads, and more.

![BrandBundles.png](https://files.readme.io/eab9447f0bdd225ab7915724f996555057fa7f2840ec6e69a89465a90af6181e-360017356617.png)

## About brand bundles

Brands operate in an ecosystem encompassing both web and mobile properties. As an advertiser, a full picture of brand performance across platforms–web and mobile–is needed. In PBA, brand bundles consolidate the data of mobile and web properties into a single entity for purposes of analytics and raw data.

> 📘 **What is a web app?**
>
> A web app is an <Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer">entity you have created in AppsFlyer</Anchor> that specifies a website for which you want to measure performance.
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
| Select an existing bundle to update brand bundle settings and options | Options available:<ul><li>Mark events as conversion events:<ul><li>[Web event settings](/docs/pba-brand-bundles-and-settings#web-event-settings)</li><li>[In-app event settings](/docs/pba-brand-bundles-and-settings#inapp-event-settings)</li></ul></li><li>[Domain exclusion](/docs/pba-brand-bundles-and-settings#domain-exclusion)</li><li><Anchor target="_blank" href="/marketers/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Google Ads integration</Anchor></li></ul> |
| Delete icon | [Deletes the selected brand bundle](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) (after you confirm your decision to do so) |

<div id="add-brand-bundle" />

<Accordion title="Add brand bundle">

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

> 🚧 **Important!**
>
> Brand bundles cannot be created in the following circumstances:
>
> * The web app selected for inclusion in the bundle does not point to a valid URL.
> * The web app and an Android mobile app selected for inclusion in the bundle have the same app ID.

</Accordion>

<div id="web-event-settings" />

<Accordion title="Web event settings">

There are two types of web events: **standard** and **conversion**. To focus and prioritize your optimization efforts, set some events as conversion events.

* PBA attributes standard and conversion events in the same way.
* <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview">Raw data</Anchor> reports include both standard and conversion events.
* PBA dashboards include conversion events only.
* An event type can be changed at any time; however, the change isn't retroactive.

**To set conversion events:**

1. From the [Brand Bundles](/docs/pba-brand-bundles-and-settings#accessing-brand-bundles) page, select the brand bundle.  
   The **Update Brand bundles** page opens.
2. Go to the **Web event settings** tab.
3. Turn on **Mark as conversion event** as required.
4. Click **Update bundle.**

</Accordion>

<div id="inapp-event-settings" />

<Accordion title="In-app event settings">

In-app events having revenue are marked as conversion events [Default]. **Note!** If you change the default events, you must explicitly mark in-app revenue events yourself.

**To mark in-app events as conversion events:**

1. From the [Brand Bundles](/docs/pba-brand-bundles-and-settings#accessing-brand-bundles) page, select the brand bundle.  
   The **Update Brand bundles** page opens.
2. Go to the **In-app event settings** tab.
3. Turn on **Mark as conversion event** as required.
4. Click **Update bundle.**

</Accordion>

<div id="domain-exclusion" />

<Accordion title="Domain exclusion">

A domain exclusion mechanism, part of <Anchor target="_blank" href="/marketers/docs/pba-media-source-attribution-rules">PBA media source rules,</Anchor> is implemented to prevent:

* Self-attribution: In other words, AppsFlyer will not attribute events to the website defined in the web app itself and to domains you specify are associated with that website.
* Attributing or recording events associated with domains that aren't part of your brand but participate in the user flow (for example, payment gateways).

| Domain type | Description | Impact of exclusion |
| --- | --- | --- |
| Primary | The domain of the **web app** included in the brand bundle. This includes sub-domains.<br /><br />For example, if your domain is mydomain.co.za then subdomains like a.mydomain.co.za, b.mydomain.co.za are excluded automatically. <br /><br />The domain of a web app cannot be changed without [deleting](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) and recreating the web app. (This also means deleting the bundle in which the web app is included). | No self-attribution |
| Internal | List other domains forming part of your brand, for example, mydomain.com, mydomain.in, mydomain.co.ng, abc.com | No self-attribution |
| External (listed by you) | Domains used by your website directly, but not part of the brand. These include payment gateways, payment processing sites, etc. | <Anchor target="_blank" href="/marketers/docs/pba-media-source-attribution-rules#visit-recognition-rules">Visits are disregarded</Anchor> |
| External (listed by AppsFlyer) | Domains listed by AppsFlyer and always excluded.<ul><li>PayPal</li><li>Stripe</li><li>Adyen</li></ul>The list of automatic domains cannot be edited. | <Anchor target="_blank" href="/marketers/docs/pba-media-source-attribution-rules#visit-recognition-rules">Visits are disregarded</Anchor> |

**To exclude internal or external domains:**

1. From the [Brand Bundles](/docs/pba-brand-bundles-and-settings#accessing-brand-bundles) page, select the brand bundle.  
   The **Update Brand bundles** page opens.
2. Go to the **Domain exclusion** tab.
3. Click **Add domain.**
4. Enter a domain name.
5. Select a domain type: **Internal** or **External.**
6. Click **Add domain.**  
   It takes one hour for the exclusion to take effect.

</Accordion>

## FAQ

<div id="can-i-include-the-same-app-in-more-than-one-bundle" />

<Accordion title="Can I include the same app in more than one bundle?">

**No.** Once an app is added to a bundle, it can't be added to another bundle.

</Accordion>

<div id="can-i-add-or-remove-apps-after-creating-a-bundle" />

<Accordion title="Can I add or remove apps after creating a bundle?">

**No.** Once a bundle has been created, the apps included in it cannot change.

**Why?** Each app has its own data, and AppsFlyer uses this data to analyze the user journey across platforms (web and app). If an app changed, this would involve a different set of data that is not compatible with the previous data.

</Accordion>

<div id="how-do-i-add-or-remove-delete-apps-from-a-bundle" />

<Accordion title="How do I add or remove (delete) apps from a bundle?">

To change the bundle in which an app is included, delete the original bundle and create a new one that includes the app.

</Accordion>

<div id="what-happens-if-i-delete-a-bundle" />

<Accordion title="What happens if I delete a bundle?">

#### faqs what happens if i delete a bundle

If you delete a bundle:

* AppsFlyer stops attributing the bundle.
* The bundle data is retained (in other words, it's not permanently deleted), but the bundle itself can't be restored in order to view the data.

  **Why?** A new bundle uses a different web dev key so, even if it includes the same apps, the original bundle is not restored.

</Accordion>

<div id="why-are-certain-apps-not-available-for-me-to-add-to-a-bundle" />

<Accordion title="Why are certain apps not available for me to add to a bundle?">

* **Admins:** If you can't select an app when creating a bundle, be sure the app has been added to your AppsFlyer account and is not included in another bundle.
* **Other account users:** Check with an account admin to ensure you have the required role and permissions to access to the apps you are trying to add.

</Accordion>

<div id="page-404" />

<Accordion title="Why do I get the 'We couldn't find that Page' error when I try to view or create a brand bundle?">

You probably didn’t subscribe to PBA. Please contact your CSM or [hello@appsflyer.com](mailto:hello@appsflyer.com) to upgrade your package.

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/onboarding-guide-to-people-based-attribution">Onboarding guide to PBA</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/people-based-attribution-pba-overview">PBA getting started</Anchor>

<div data-zendesk-anchors="h_01HE0Y2A3A5W86YY44RWCTKM1Y=about-brand-bundles h_01HE0Y2A3AYAFFSPRSH2BQ00Z3=what-is-a-web-app h_01HE0Y2A3A7265NYM7GVBZVXEN=accessing-brand-bundles h_01HE0Y2A3A272QJ4ZQH7VXJWCC=managing-brand-bundles h_01HE0Y2A3ATX4ZDYZSRQGSJ4G7=add-brand-bundle h_01HE0Y2A3AQC5MMNQA0AV34MZ3=important h_01HE0Y2A3ATN6DEQ2KHCGT6VPQ=web-event-settings h_01HE0Y2A3A76VBZ17W4P1D0K2A=inapp-event-settings h_01HE0Y2A3A7F2YEW2SK0PSXXE4=domain-exclusion h_01HE0Y2A3AB24NCNPAYFC0J4YH=faq h_01HE0Y2A3A5E816CYG2TMZ37DA=can-i-include-the-same-app-in-more-than-one-bundle h_01HE0Y2A3BENKY1AM51VM76TVS=can-i-add-or-remove-apps-after-creating-a-bundle h_01HE0Y2A3BK4JKMTND0JFCB179=how-do-i-add-or-remove-delete-apps-from-a-bundle h_01HE0Y2A3BKJTQZJXV49X32N1E=what-happens-if-i-delete-a-bundle h_01HE0Y2A3B276FV92EYBCZRA6C=faqs-what-happens-if-i-delete-a-bundle h_01HE0Y2A3BEB2JG8CPSX3DA1V9=why-are-certain-apps-not-available-for-me-to-add-to-a-bundle h_01JTQF9DZZZ5JFN43Y5KJJV943=page-404 h_01HE0Y2KTXS06WHN57MQ91AD09=see-also" />

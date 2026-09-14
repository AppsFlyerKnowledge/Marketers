---
title: "PBA brand bundles and settings"
excerpt: "Learn how to consolidate attribution, events, visits, and revenue of brand-related apps and websites using PBA brand bundles."
---
Brand bundles consolidate the attribution, events, visits, and revenue of brand-related apps and websites. Use the brand bundle settings page to mark conversion events, integrate with Google Ads, and more.

![BrandBundles.png](https://files.readme.io/eab9447f0bdd225ab7915724f996555057fa7f2840ec6e69a89465a90af6181e-360017356617.png)

## About brand bundles

Brands operate in an ecosystem encompassing both web and mobile properties. As an advertiser, a full picture of brand performance across platforms–web and mobile–is needed. In PBA, brand bundles consolidate the data of mobile and web properties into a single entity for purposes of analytics and raw data.

#### What is a web app?

A web app is an [entity you have created in AppsFlyer](https://support.appsflyer.com/hc/articles/207377436) that specifies a website for which you want to measure performance.

- The web app entity was added to AppsFlyer on February 9, 2022. Prior to that date, you entered the brand bundle domain as a separate setting when creating a brand bundle. Now, you first create a web app that defines the domain, then include that web app when creating a bundle.
- If you had existing brand bundles on February 9, 2022, you will see that you now have a web app on the **My apps** page corresponding to each of those bundles. **Rest assured!** Your web traffic is being attributed just as it was before, and there have been no other changes to PBA dashboards or raw data reports.

**Brand bundle basics:**

- A brand bundle contains exactly 1 web app *(required)* and 1 or more mobile apps *(optional).*
- An app (web or mobile) can belong only to 1 bundle.
- Apps can't be deleted from a bundle or moved from one bundle to another without [deleting the original bundle](https://support.appsflyer.com/hc/articles/360000646498#what-happens-if-i-delete-a-bundle).
  - On bundle deletion, AppsFlyer stops attributing PBA data for the bundle, and access to its historical data is no longer available.

## Accessing brand bundles

Access the **Brand Bundles** page to manage brand bundles and their settings:

- In AppsFlyer, from the top menu, select **My Apps** \> **View brand bundles.**

  - or -
- In AppsFlyer, from the side menu, go to **Settings** \> **Brand Bundles.**

## Managing brand bundles

To add, delete, or manage brand bundles, select one of these options from the **Brand Bundles** page:

| Option | Details |
| --- | --- |
| Add a brand bundle | Opens the **Create bundle** page<br>Follow the [instructions below](https://support.appsflyer.com/hc/articles/360000646498#add-brand-bundle) to create a new bundle. |
| PBA dashboard | Opens the brand dashboard |
| Brand bundle ID | Copies brand bundle ID to the clipboard |
| Web dev key | Copies the web dev key to the clipboard |
| Select an existing bundle to update brand bundle settings and options | Options available:<br>- Mark events as conversion events:<br>  - [Web event settings](https://support.appsflyer.com/hc/articles/360000646498#web-event-settings)<br>  - [In-app event settings](https://support.appsflyer.com/hc/articles/360000646498#inapp-event-settings)<br>- [Domain exclusion](https://support.appsflyer.com/hc/articles/360000646498#domain-exclusion)<br>- [Google Ads integration](https://support.appsflyer.com/hc/articles/36011487937) |
| Delete icon | [Deletes the selected brand bundle](https://support.appsflyer.com/hc/articles/360000646498#what-happens-if-i-delete-a-bundle) (after you confirm your decision to do so) |

### Add brand bundle

Before proceeding, make sure that all the apps you want to include in the bundle have been added to your account. Once a brand bundle has been created, the apps it includes can not be changed without [deleting the bundle](https://support.appsflyer.com/hc/articles/360000646498#what-happens-if-i-delete-a-bundle) and recreating it.

**To add a brand bundle:**

1. From the [Brand Bundles](https://support.appsflyer.com/hc/articles/360000646498#accessing-brand-bundles) page, click **Add brand bundle.**
2. Enter the **Brand bundle name** (any name you want to use to identify the bundle).
3. Select the apps to include in the bundle.

> 📘 Note
>
> Apps that are included in other bundles are not available for selection.

- Web app *[required]*: Select 1 available web app.
- Mobile apps *[optional]:* Select the available mobile apps you want to include in the bundle.
  - Mobile apps are not required to create a bundle.
  - There is no limit to the number of mobile apps you can include in a bundle.
4. Click Create bundle.

> ❗️ Important!
>
> Brand bundles cannot be created in the following circumstances:
>
> - The web app selected for inclusion in the bundle does not point to a valid URL.
> - The web app and an Android mobile app selected for inclusion in the bundle have the same app ID.

### Web event settings

There are two types of web events: **standard** and **conversion**. To focus and prioritize your optimization efforts, set some events as conversion events.

- PBA attributes standard and conversion events in the same way.
- [Raw data](https://support.appsflyer.com/hc/articles/209680773) reports include both standard and conversion events.
- PBA dashboards include conversion events only.
- An event type can be changed at any time; however, the change isn't retroactive.

**To set conversion events:**

1. From the [Brand Bundles](https://support.appsflyer.com/hc/articles/360000646498#accessing-brand-bundles) page, select the brand bundle.

The **Update Brand bundles** page opens.
2. Go to the **Web event settings** tab.
3. Turn on **Mark as conversion event** as required.
4. Click **Update bundle.**

### In-app event settings

In-app events having revenue are marked as conversion events [Default].

> 📘 Note!
>
> If you change the default events, you must explicitly mark in-app revenue events yourself.

**To mark in-app events as conversion events:**

1. From the [Brand Bundles](https://support.appsflyer.com/hc/articles/360000646498#accessing-brand-bundles) page, select the brand bundle.

The **Update Brand bundles** page opens.
2. Go to the **In-app event settings** tab.
3. Turn on **Mark as conversion event** as required.
4. Click **Update bundle.**

### Domain exclusion

A domain exclusion mechanism, part of [PBA media source rules,](https://support.appsflyer.com/hc/articles/360002386997) is implemented to prevent:

- Self-attribution: In other words, AppsFlyer will not attribute events to the website defined in the web app itself and to domains you specify are associated with that website.
- Attributing or recording events associated with domains that aren't part of your brand but participate in the user flow (for example, payment gateways).

| Domain type | Description | Impact of exclusion |
| --- | --- | --- |
| Primary | The domain of the **web app** included in the brand bundle. This includes sub-domains.<br>For example, if your domain is mydomain.co.za then subdomains like a.mydomain.co.za, b.mydomain.co.za are excluded automatically.<br>The domain of a web app cannot be changed without [deleting](https://support.appsflyer.com/hc/articles/360000646498#what-happens-if-i-delete-a-bundle) and recreating the web app. (This also means deleting the bundle in which the web app is included). | No self-attribution |
| Internal | List other domains forming part of your brand, for example, mydomain.com, mydomain.in, mydomain.co.ng, abc.com | No self-attribution |
| External (listed by you) | Domains used by your website directly, but not part of the brand. These include payment gateways, payment processing sites, etc. | [Visits are disregarded](https://support.appsflyer.com/hc/articles/360002386997#visit-recognition-rules) |
| External (listed by AppsFlyer) | Domains listed by AppsFlyer and always excluded.<br>- PayPal<br>- Stripe<br>- Adyen<br>The list of automatic domains cannot be edited. | [Visits are disregarded](https://support.appsflyer.com/hc/articles/360002386997#visit-recognition-rules) |

**To exclude internal or external domains:**

1. From the [Brand Bundles](https://support.appsflyer.com/hc/articles/360000646498#accessing-brand-bundles) page, select the brand bundle.

The **Update Brand bundles** page opens.
2. Go to the **Domain exclusion** tab.
3. Click **Add domain.**
4. Enter a domain name.
5. Select a domain type: **Internal** or **External.**
6. Click **Add domain.**

It takes one hour for the exclusion to take effect.

## FAQ

<Accordion title="Can I include the same app in more than one bundle?">

**No.** Once an app is added to a bundle, it can't be added to another bundle.

</Accordion>

<Accordion title="Can I add or remove apps after creating a bundle?">

**No.** Once a bundle has been created, the apps included in it cannot change.

**Why?** Each app has its own data, and AppsFlyer uses this data to analyze the user journey across platforms (web and app). If an app changed, this would involve a different set of data that is not compatible with the previous data.

</Accordion>

<Accordion title="How do I add or remove (delete) apps from a bundle?">

To change the bundle in which an app is included, delete the original bundle and create a new one that includes the app.

</Accordion>

<Accordion title="What happens if I delete a bundle?">

If you delete a bundle:

- AppsFlyer stops attributing the bundle.
- The bundle data is retained (in other words, it's not permanently deleted), but the bundle itself can't be restored in order to view the data.

**Why?** A new bundle uses a different web dev key so, even if it includes the same apps, the original bundle is not restored.

</Accordion>

<Accordion title="Why are certain apps not available for me to add to a bundle?">

- **Admins:** If you can't select an app when creating a bundle, be sure the app has been added to your AppsFlyer account and is not included in another bundle.
- **Other account users:** Check with an account admin to ensure you have the required role and permissions to access to the apps you are trying to add.

</Accordion>

<Accordion title="Why do I get the \"We couldn't find that Page\" error when I try to view or create a brand bundle?">

You probably didn’t subscribe to PBA. Please contact your CSM or [hello@appsflyer.com](mailto:hello@appsflyer.com) to upgrade your package.

</Accordion>

### See also

<Cards>
  <Card title="Onboarding guide to PBA" href="https://support.appsflyer.com/hc/articles/36013821097">
    Read the onboarding guide to get started with PBA.
  </Card>
  <Card title="PBA getting started" href="https://support.appsflyer.com/hc/articles/360002274017">
    Learn the basics and how to get started with PBA.
  </Card>
</Cards>
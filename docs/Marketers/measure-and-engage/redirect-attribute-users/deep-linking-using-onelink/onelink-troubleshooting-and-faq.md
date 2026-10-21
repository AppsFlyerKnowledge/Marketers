---
title: OneLink troubleshooting and FAQ
metadata:
  keywords:
    - faq
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2020-10-27T11:26:30Z'
  edited_at: '2026-09-14T13:45:26Z'
  id: 360014821438
  locale: en-us
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360014821438-OneLink-troubleshooting-and-FAQ
---
> **At a glance:** Quickly find solutions for testing and debugging OneLink custom link redirection/behavior issues.

## OneLink troubleshooting guide

## OneLink frequently asked questions

### OneLink template FAQ

<Accordion title="Which method should I use for opening apps—Universal Links, App Links, or URI schemes?">

**Universal Links:** Required for over 98% of iOS users

**App Links:** For Android users with version 6.0+. **Note**: Samsung OS can't open apps using Android App Links.

> 📘 **Note**
>
> Both Universal Links and App Links require proof that the domain in the clicked URL (in other words, the OneLink custom link domain or branded domain) is owned and associated with the specific app it’s trying to open. This domain association is done via the **Apple App Site Association file (AASA)** for iOS and **Assetlinks** file for Android.
>
> These files are either hosted by AppsFlyer or by the advertiser on its website. By default, when you create OneLink templates and set up Universal Links and App Links, these files are generated and hosted by AppsFlyer.

**URI schemes:** The primary method for opening apps on Samsung devices. Otherwise, it is a legacy and fallback method for opening apps. Can be used:

* For Android users with versions prior to 6.0 (less than 15% of Android users)
* As a fallback for when Universal Links and App Links don't open the app, either because they don't work, or aren't set up. **Note:** Using URI schemes as a fallback for Universal Links is subject to iOS-based limitations. <Anchor target="_blank" href="/marketers/docs/uri-scheme-fallback-for-ios">Learn more</Anchor>.

#### Deep linking

Universal Links, App Links, and URI schemes are secure methods for **opening** an app. To deep link and redirect users into specific activities or pages in the app, follow the <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">OneLink deep linking instructions</Anchor>.

</Accordion>

<Accordion title="Which operating systems allow URI schemes to open the app?">

| OS | Do URI schemes work to open the app? |
| --- | --- |
| iOS | **Yes.** Use as a fallback for Universal Links failure.<br /><br />**Important notes:**<ul><li>Using URI schemes as a fallback is subject to iOS-based limitations.</li><li>For many browsers, including Safari, you must add the `af_force_deeplink=true` parameter to the URL to use URI schemes as a fallback. <Anchor target="_blank" href="/marketers/docs/uri-scheme-fallback-for-ios">Learn more</Anchor>.</li><li>If an error message appears that says: "Something went wrong. The application couldn’t be opened.”, this generally means that the application isn’t installed or an incorrect URI scheme was used.</li></ul> |
| Android | **Yes.** Use for Samsung devices, Android versions prior to 6.0 and as a fallback for when App Links fail on later Android versions. |
| Amazon | **No** |
| Windows Mobile | **No** |

</Accordion>

<Accordion title="Do I need to update the app after iOS Universal Links and Android App Links setup?">

**Yes.** Whenever Universal Links or App Links are implemented to open the app for existing users, iOS Associated Domains or AndroidManifest.xml is updated. This means that you must upload a new version of the app to the relevant app store. **Tip:** To minimize the need for app updates, make all the dev-related changes required to <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">open the app</Anchor> and <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep link</Anchor> at one time.

</Accordion>

<Accordion title="Can I redirect existing users to a web page instead of the app?">

**Yes.** However, configuring your template to do so affects all users (new and existing), and sends everyone to the landing page/web URL. Meaning, new users are not sent to the app store.

To send users to a web page:

1. In your template, do not set up Universal Links, App Links, or URI scheme.
2. Set up the redirections for when the app isn't installed to the landing page/web URL.
   * The landing page/web URLs are added as the values for the af\_android\_url and af\_ios\_url parameters.
   * Make sure any URLs you're redirecting users to have been added to your <Anchor target="_blank" href="/marketers/docs/set-up-your-domain-redirect-allowlist">domain redirect allowlist</Anchor>.
   * The redirections are then automatically applied for when the app is installed (for existing users), as well.

**Note**: If you want to redirect existing users to a mobile web page only after app launch, your app developer must configure that behavior.

</Accordion>

<Accordion title="Can I redirect tablet users to a different app or URL then mobile app users?">

You can set specific redirections for:

* Windows phones
* iPads
* Amazon Kindle Fire.

Other tablets are not currently supported for separate redirection.

</Accordion>

<Accordion title="Can I assign an app to multiple OneLink templates?">

**Yes.** While you can use a single OneLink template to create a limitless number of OneLink URLs, in some cases, it might be necessary to assign an app to more than one OneLink template. For example, if you have multiple versions of an Android app for out-of-store markets, you may need a separate OneLink template for each Android version with the same iOS app assigned to all of them.

**Important**:

For templates using iOS Universal Links and Android App Links to open the app, **if your templates have different subdomains**, you need to configure and update your iOS and Android apps for each one:

* **iOS Universal Links:** After creating the new OneLink template, and updating the associated domain in the app, submit a new version to the App Store. Only iOS users who have updated to the new version can activate a OneLink URL built on the new template.
* **Android App Links:**
  1. After creating the new OneLink template, copy the XML snippet at the bottom of the App Link section and add it to the **AndroidManifest.xml** file inside the intent you want to deep link into, in addition to any previous intents.
  2. Release the new version to the store. Only Android users who have updated to the new version can activate a OneLink URL built on the new template.

</Accordion>

<Accordion title="Can I delete a OneLink template?">

Yes.

**To delete a template:**

1. In AppsFlyer, go to the OneLink Management page.
2. Select the OneLink template.
3. Click the 'Edit template' option from the ellipsis menu.

   <Image alt="delete template.png" src="https://files.readme.io/72b68cb979e2360f4e3065f99fbb547a91713a40dcc9adee59028ed2945f794a-31094482204945.png" width="1204px" />
4. Click the trash icon.

**Note:** If you have existing OneLink URLs based on the deleted template, **they won’t work even to get users to the app store.** For this reason, it’s particularly important that you don’t delete a template without first making sure that there are no OneLink URLs using it. Alternatively, consider if it's possible to achieve the results you need by changing the existing template's configuration instead of deleting it.

</Accordion>

<Accordion title="Can I change the subdomain in a OneLink template?">

**Yes, as long as there are no existing custom links in AppsFlyer based on the template.**

If there are already custom links in AppsFlyer based on the OneLink template, then the subdomain can't be changed. This limitation is designed to prevent breaking the redirection/deep linking behavior of live links.

If you do need to change the subdomain in a template with existing custom links, you can either:

* Create a new OneLink template with the new subdomain, and create links based on it.
* Delete all existing custom links based on the template for which the subdomain needs to be changed. Once all links based on the template have been deleted, the subdomain becomes editable.

</Accordion>

<Accordion title="Can the domain/subdomain of a OneLink template be applied to the template ID of another template?">

**No.** Taking the subdomain/domain configured to a specific template and template ID and manually concatenating it to a different template ID breaks the functionality of Universal Links and App Links, and poses a security threat.

**Example:**

* Template 1ABC is configured with subdomain **bank.onelink.me**.
* Template D123 is configured with subdomain **game.onelink.me**.
* The link **bank.onelink.me/1ABC/shorturl** is created based on template 1ABC and works.
* The link **game.onelink.me/D123/exampleurl** is created based on template D123 and works.
* The link **game.onelink.me/1ABC/shorturl** doesn't work
* The **link bank.onelink.me/D123/exampleurl** doesn't work

</Accordion>

<Accordion title="Can I use the same subdomain for more than one template?">

**Yes.** However, make sure you create separate templates with the subdomain; don't just manually add the subdomain to a template ID.

</Accordion>

<Accordion title="How can I redirect desktop users?">

Desktop users can engage with your OneLink custom links, for example, via an email campaign. However, when desktop users click on these links, they cannot be redirected to a mobile site, app store, or app. By default, desktop users are redirected to a web version of the App Store or the Google Play store.

**So how can I give desktop users a good user experience and convert them into mobile users?**

In the OneLink URL or template, you can redirect desktop users (Windows or Mac) to a different URL. This web URL is added to the link in the `af_web_dp` parameter. Make sure all URLs you’re redirecting users to have been added to your domain <Anchor target="_blank" href="/marketers/docs/set-up-your-domain-redirect-allowlist">redirect allowlist</Anchor>. Otherwise, redirection will not work.

**Note:** If your link contains `af_web_dp`, AppsFlyer does not register a click when it comes from a desktop.

> 👍 **Tip**
>
> Try redirecting desktop users to a web URL that contains a dedicated web form that sends a OneLink URL to the mobile device of the desktop user via SMS or email. Learn more about this option as part of the OneLink Smart Script solution.

</Accordion>

<Accordion title="How can I redirect Chrome OS users?">

Apps on Chromebooks are considered to be Android apps.

For Chromebook, to redirect new users without your app installed to a different web URL:

1. In the OneLink template settings, under **Set link behavior** > **When app isn't installed** > **Android**, click **Change to a different URL**.  
   OR  
   In the OneLink link settings, under **Deep linking & redirection** > **Redirect** > **When app isn't installed** > **Android**, select **Web URL**.
2. Enter the URL.  
   When added via the link settings, the URL is added to your link in the `af_android_url` parameter.

</Accordion>

<Accordion title="Which app is a desktop OneLink click recorded for?">

OneLink template can be associated with two apps: one iOS and one Android. When a OneLink link is clicked on a mobile device, the click is recorded for the app that matches the device platform. A click on an iOS device is recorded for the iOS app, and a click on an Android device is recorded for the Android app.

When a OneLink link is clicked on a desktop, there is no device platform to match. In this case, the click is recorded as follows:

* If both an iOS app and an Android app are associated with the template, the click is recorded for the iOS app.
* If only one app is associated with the template, the click is recorded for that app.

</Accordion>

### OneLink link FAQ

<Accordion title="Does OneLink work without the AppsFlyer SDK?">

**Yes, but only in part.**

If you need to convert mobile web visitors into mobile users fast and can't integrate the AppsFlyer SDK, it is possible to do so.

Basic user redirection and app launching work even if AppsFlyer SDK isn't yet integrated into the app. Smart Banners don't require the SDK either and also work fine without it.

However, the absence of the SDK means that:

* Clicking users can't be deep linked beyond the initial app launch.
* Attribution data isn't recorded.
* In-app events aren't recorded.

</Accordion>

<Accordion title="What methods are available for creating OneLink custom links?">

The following table compares the different methods available for creating OneLink custom links.

| Link creation method | Uses | Short/long URL | Premium feature | Visible in UI? | Attribution TTL (Time to Live) max and default |
| --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">AppsFlyer UI</Anchor> | Create OneLink template and custom links | Both | -- | **✓** | No TTL |
| <Anchor target="_blank" href="/marketers/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> | Create thousands of OneLinks quickly | Short | **✓** | -- | 31 days |
| <Anchor target="_blank" href="/marketers/docs/perform-onelink-bulk-actions-via-csv">OneLink bulk link creation</Anchor> | Create thousands of OneLinks short URLs quickly using the parameters defined in a CSV | Short | -- | -- | 365 days |
| <Anchor target="_blank" href="/marketers/docs/user-invite-attribution">SDK</Anchor> | User invite (referral) campaigns | Short | -- | -- | 60 days |
| <Anchor target="_blank" href="/marketers/docs/onelink-smart-script-overview">OneLink Smart Script</Anchor> | Mobile web-to-app campaigns | Long | -- | -- | No TTL |
| <Anchor target="_blank" href="/marketers/docs/understand-onelink-short-vs-long-urls">Spreadsheet</Anchor> | Create thousands of OneLink custom links by applying your own formulas | Long | -- | -- | No TTL |

</Accordion>

<Accordion title="What happens when I delete a OneLink URL from the OneLink management page?">

As of November 2025,

* Once a link is deleted from the OneLink Management section, the link is deleted from the table and the database. This means that if an end user finds and clicks the link, they will be redirected based on the OneLink template settings. Attribution parameters, deep linking parameters, and link-level redirection settings will not apply.
* The link will stop working within 2 minutes of deletion.
* Links deleted via the UI after November 5, 2025, can be restored through the **Deleted links** table, accessible in OneLink management.

  <Image alt="deleted links.png" src="https://files.readme.io/d5a2cc7047fda06ba8249cc00b2830c309ec6137f10306cdabca61bcfe3d4d15-small-41829768141713.png" width="2768px" />
* Links can be restored up to 90 days from the deletion date. If more than 90 days have passed from the link deletion date, the link cannot be restored.

</Accordion>

<Accordion title="Can OneLink custom links open the app from a browser?">

**Yes,** but be aware that Universal Links and App Links only work when clicked on (for example, when clicking a link on a web page or email). **Pasting the link in the browser address bar doesn't launch the app.** Test your links by clicking on URLs; not by pasting them in the browser URL box.

</Accordion>

<Accordion title="Why doesn't the OneLink URL open the app or deep link existing users?">

Despite the best intentions, in some cases, your OneLink URLs may not perform the intended deep linking. When this happens, instead of opening the app or getting deep linked into a specific activity within the app, users are redirected to the app store or to an error page.

There are several possible reasons for this:

* **Host applications:** Apps in which your attribution links are shared (for example, WhatsApp, Gmail, WeChat) use different methods to activate clicked links, such as proprietary internal browsers. Some of these are known to block all attribution links.
* **Browsers:** Certain browsers and OS platforms behave differently with links. In certain browsers, for example, pasting a link does not work. The link must actually be clicked.
* **OS updates:** New OS updates (both iOS and Android) may introduce unexpected bugs that hamper deep linking.
* **Devices:** Different smartphones, tablets, laptops, and other devices running different versions of iOS, Android, Windows Mobile, and other operating systems can vary greatly in their handling of attribution links.
* **Misconfiguration:** The use of <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#traits-and-limitations">special characters</Anchor> in the deep linking value breaks the link.

Two solutions for improving the user experience are Fallback URLs and forced deep linking.

#### Fallback URLs

Fallback URLs send users to specified web pages if opening the app or deep linking fails for any reason. **Caution!** They also send users without your app installed to the fallback URL instead of to the correct app store. So, be sure to only use this option if you're retargeting users with your app already installed.

To implement a fallback URL, in the OneLink template or custom link settings, set the link behavior for when the app isn't installed to redirect to a different URL.

![different_url.png](https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png)

Using this setting adds `af_ios_url` and `af_android_url` as destination parameters for the fallback, which will cause iOS users to be redirected to the page specified by `af_ios_url` and Android users to be redirected to the page specified by `af_android_url`.

> 👍 **Tip**
>
> Consider, for example, the following OneLink URL:
>
> Both iOS and Android users who click on this link should be deep linked into the app. However, when deep linking fails, users are redirected as follows:
>
> * iOS: www.yoursite.com/ios-bonus
> * Android: www.yoursite.com/android-bonus

> 📘 **Note**
>
> When redirection occurs, OneLink URL parameters pass through to the destination page specified by af\_ios\_url or af\_android\_url. To prevent this behavior, add the parameter af\_param\_forwarding=false to the OneLink.

#### Forced deep linking

Forced deep linking allows you to use a URI scheme as a fallback to open the app and deep link users.

This solution works well for most users who have the app installed. However, for iOS, using a URI scheme to open the app has limitations, and you may need to add `af_force_deeplink=true` to the OneLink URL to force deep linking into the activity specified in the URI scheme (the `af_dp` parameter). Learn more about <Anchor target="_blank" href="/marketers/docs/uri-scheme-fallback-for-ios">URI scheme fallback for iOS.</Anchor>

</Accordion>

<Accordion title="Does OneLink support App Store Connect events?">

Yes. You can place a OneLink behind App Store Connect events. Redirection, app opens, installs, and re-engagement attribution will work as expected.

</Accordion>

<Accordion title="Why does my OneLink URL open a blank page in Chrome?">

Make sure you are not using an HTML `<a>` tag that includes the `target` attribute. If the OneLink URL is placed inside an `<a>` tag with the `target="_blank"` attribute, it opens a blank page in Chrome (on both iOS and Android), and the user is not redirected to the App Store or to Google Play.

</Accordion>

<Accordion title="Can I use OneLink for redirection on Brave?">

Yes. However, on Android, when a user clicks a OneLink link on a Brave browser, deferred deep linking doesn't work. And on iOS, after the user clicks, they see a blank screen, and deferred deep linking only works if they then do something on the blank screen, for example, scroll, or tap.

</Accordion>

<Accordion title="Do OneLink custom links take longer to load than other links?">

**No.** OneLink custom links do not add any extra processing or load time to function properly and redirect users as required. They're just as fast as any other AppsFlyer links.

</Accordion>

<Accordion title="How can I record the cost per install when using OneLink?">

Turning on **Enable cost per install** (under **Advanced parameters**) allows you to apply a specific CPI value to each install coming from the link.

Select the cost currency and then a **numeric ONLY value** (with up to 4 digits after the decimal point) representing the CPI. This adds the parameters af\_cost\_currency and af\_cost\_value to the link.

> 👍 **Tip**
>
> An SMS campaign costs $20 per 1000 messages (CPM). Experience has shown that your campaigns achieve a 5% conversion rate, meaning the derived CPI is $0.40. Setting the cost per install to 0.40 USD allows you to measure the eventual ROI of the SMS campaign.

Learn more about <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview">measuring cost and ROI</Anchor>.

</Accordion>

<Accordion title="How can I prevent parameter forwarding on redirections?">

`af_r`, `af_ios_url`, `af_android_url`, and `af_web_dp` carry over parameters from the attribution link or OneLink to the redirected page. To prevent this behavior, add `af_param_forwarding=false` to the attribution link.

</Accordion>

<Accordion title="How can I remove AppsFlyer PID and C parameters when forwarding while keeping all other parameters on redirection URLs?">

In some cases, you might have URLs with multiple PIDs. This happens because AppsFlyer adds PID and C parameters to a redirection URL and the client can also add their own PID parameters. For example, the 'product ID' might be 'pid' in the client website URL.

Normally, adding `af_param_forwarding=false` to the attribution link removes all parameters.

However, if the link is clicked on from a desktop, the client may want essential CRM parameters to remain. To remove only the AppsFlyer PID and C parameters and keep all the other parameters, add `af_base_params_forward=false` to the attribution link.

</Accordion>

<Accordion title="Are single-platform custom links still available?">

No, single-platform custom links are no longer available.

</Accordion>

<Accordion title="Can I change the short URL ID after saving a link?">

**No,** the short URL ID can only be set at the time the link is created.

</Accordion>

<Accordion title="Can I wrap and shorten OneLink custom links?">

**External link shorteners or wrapping your OneLink custom links will break the app-opening functionality of Universal Links and App Links.**

In order to activate Universal Links or App Links, the OS needs to recognize the domain of the URL associated with the app, and any type of external wrapping, shortening, or redirecting to the user-facing link makes this impossible. This includes using bit.ly, non-AppsFlyer branded links, or Email Service Providers (ESPs) with click recording enabled.

**To wrap or shorten a link in a way that allows the redirection to work properly:**

* Use the short URLs generated by AppsFlyer when you create OneLink custom links (instead of external shorteners like bit.ly).  
  **Tip**! Make the URL even shorter by creating a short branded domain on your link. And if you're creating the links in the AppsFlyer UI, you can edit the URL ID to be as short as possible. Example: https://brand.com/a1b2/a (where **brand.com** is your branded domain, **a1b2** is the template ID which is always 4 characters, and **a** is the URL ID, which can be edited down to 1 character.   
  Benefits:
  * This method works because it uses the OneLink subdomain configured in the OneLink template.
  * It enables you to change parameters on the fly, including any deep linking settings, even after distributing the attribution links to your leads.
  * It counts all the clicks from mobile devices in the AppsFlyer dashboard, so you don't need to check another service.
  * The last part of the short URL can be customized to make it a <Anchor target="_blank" href="/marketers/docs/brand-onelink-with-your-domain">branded domain</Anchor>.
* Use the <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">URI scheme</Anchor> as a fallback to open the app when Universal Links and App Links fail, and add the following parameter to the link: `af_force_deeplink=true`.
* See options for [working with ESPs](/docs/onelink-troubleshooting-and-faq#can-i-use-onelink-custom-links-in-emails).

</Accordion>

<Accordion title="Can I use OneLink custom links in emails?">

**Yes,** but it requires special consideration when you're working with Email Service Providers (ESPs). In order to count performed clicks, ESPs wrap all links placed inside emails. This breaks the app opening/deep linking flow for users who click the URL.

To prevent this, use one of the following optional solutions:

* Disable click recording in your ESP configuration.  
  **(Tip: This is generally the easiest solution.)**
* Force the app open with the URI scheme specified in the `af_dp` parameter by adding the flag `af_esp=true` to the attribution link. This solution works well for users who have the app installed.
* Use ESPs that support the AppsFlyer solution for app opening and deep linking with Universal Links. <Anchor target="_blank" href="/marketers/docs/email-service-provider-esp-integration-guide">Learn more</Anchor>.

</Accordion>

<Accordion title="How do users get redirected to their regional app store?">

OneLink redirects users to the correct regional app store based on their IP address.

</Accordion>

<Accordion title="Why isn't my OneLink URL redirecting users to the specified domain?">

Check whether you have activated Redirect allowlists in AppsFlyer. If you have it activated, the desired web URL domain or subdomain must be listed. <Anchor target="_blank" href="/marketers/docs/set-up-your-domain-redirect-allowlist">Learn more about Redirect allowlists</Anchor>

</Accordion>

<Accordion title="Why do I get the 'App you are looking for is unavailable' error?">

The 'App you are looking for is unavailable' error may arise instead of redirection to Google Play due to:

* Your app is currently in 'Pending' status on Google Play. To avoid the error message mentioned above, set the link's redirection to point to a web URL instead of Google Play. Once the app is approved, the redirection can be changed back to Google Play. These configuration changes are performed on the <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">link's template page</Anchor>.
* If your app is available exclusively through a third-party store, the issue may arise from it being assigned the incorrect Google Play status in AppsFlyer. To resolve this, you <Anchor target="_blank" href="/marketers/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">must set its Google Play status to Published out of store</Anchor> on the Settings My Apps page.

</Accordion>

<Accordion title="Why is my m.onelink.me shortlink not working?">

As of June 2024, the older shortlink version **m.onelink.me** was deprecated. Links still using this subdomain no longer redirect to their intended destination, potentially interrupting the planned user experience.

</Accordion>

<Accordion title="Can I manually switch between the branded domain and its OneLink subdomain in an existing link?">

Yes - If the branded domain and the OneLink subdomain are properly mapped. See: <Anchor target="_blank" href="/marketers/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer">Set up a Branded Domain in AppsFlyer</Anchor>

**Example**:  
OneLink subdomain: **demo.onelink.me**  
Template ID: **A1r4**  
The Branded domains mapped to the **demo.onelink.me** subdomain are:

* **app.simulatorapp.com**
* **click.simulatorapp.com**

You created the following branded link in the OneLink UI:  
**app.simulatorapp.com/A1r4/simulationlink**  
You can replace the branded link above with the other branded domain link or the OneLink subdomain link.  
The following links are functionally identical and work the same everywhere:

* app.simulatorapp.com/A1r4/simulationlink
* demo.onelink.me/A1r4/simulationlink
* click.simulatorapp.com/A1r4/simulationlink

</Accordion>

### OneLink parameter FAQ

<Accordion title="What parameters are mandatory for OneLink custom links?">

Only the media source (**pid**) parameter is mandatory.

</Accordion>

<Accordion title="Can parameters be appended to the short URL?">

**Yes,** any parameter can be appended to the short URL.

**Important!** Parameters appended to the short URL do not override the parameters inside the link.

> 👍 **Tip**
>
> * You create a OneLink custom link with the following output:
>   * **Long URL:** https://onelink-sim.onelink.me/Il2C?pid=training&c=peaches
>   * **Short URL:** https://onelink-sim.onelink.me/Il2C/70e6d165
> * You append the following parameters to the short URL: https://onelink-sim.onelink.me/Il2C/70e6d165?c=bananas&af_adset=fruits
> * The **af\_adset=fruits** parameter appended to the short URL is effective for attribution. However, the **c=bananas** parameter **is not effective** since there is already a **c** parameter in the long URL.

</Accordion>

<Accordion title="What custom media source names can I use?">

For owned media, the custom media source name (PID value) can be anything as long as it's not reserved by an integrated partner. To avoid a conflict, don't use the \_int suffix (e.g., googleadwords\_int) for custom media sources. It's also recommended not to use *organic* as a custom media source name as this could affect the attribution data integrity.

If you're using OneLink for paid media:

* Use the integrated partner-reserved **PID** values (those ending with **\_int**), as media source values in OneLink custom links. Don't use SRN media sources like *googleadwords* or *facebook* as custom media source names. This could affect attribution data integrity.
* Make sure the partner is integrated with AppsFlyer and active (the **Activate partner** toggle is turned on) for all apps that are set up in the OneLink template.

</Accordion>

<Accordion title="What attribution parameters can be added to a OneLink?">

You can add numerous attribution parameters to enable you to perform a thorough drill-down analysis.

| **Attribution parameter** | **Description** | **Parameter link name** |
| --- | --- | --- |
| **Campaign** | Set campaign names to compare different campaigns within the owned media source | c |
| **Adset** | Set ad set names to compare different ad sets within specific campaigns of the owned media source | af\_adset |
| **Ad Name** | Set ad names to compare different creatives within specific ad sets/campaigns of the owned media source | af\_ad |
| **Channel** | Set channel names if you want to compare more than one distribution channel for your owned media.<br /><br />Example: If you split SMS messages between two SMS service providers, specify the provider using the channel parameter. Later, you can compare the conversion rates of the two providers. | af\_channel |
| **Subscriber Parameters** | Use any of the 5 available subscriber parameters to insert values that are useful for your analysis.<br /><br />**Note:** These parameters are parsed and appear in raw data reports, which makes them useful for performing data aggregation or filtering. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |
| **Custom Parameters** | Similar to subscriber parameters, you can specify fields with any parameter names and values. and any names.<br /><br />Unlike subscriber parameters, custom parameters are not parsed in raw data; they appear in raw data reports only in the **original url** column. | Custom  <br />(as you specify) |

See more information about <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">AppsFlyer attribution link structure and parameters</Anchor>.

</Accordion>

<Accordion title="Are custom parameters added to OneLink custom links available in raw data?">

**Yes.** Custom parameters are passed to the **original url** column in raw data and can be seen there. They do not have their own columns in raw data.

For parsed data, use subscriber parameters `af_sub1-5`, each of which has a separate column in raw data reports.

</Accordion>

<Accordion title="Are parameter names case sensitive?">

**Yes.** Make sure you use only lowercase letters for your parameters and values. Uppercase letters or Inconsistent capitalization of parameter names and values could cause errors or data discrepancies, both on the dashboard and in raw data.

</Accordion>

### Integrated partner FAQ

<Accordion title="Can I use OneLink in social apps (unpaid)?">

You may want to use OneLink in unpaid posts on social apps since potential users who are exposed to such posts cannot be targeted in advance according to their devices.

Unfortunately, iOS Universal Link limitations and restrictions set by some social apps complicate the use of OneLink for basic device recognition, redirection and attribution, and deep linking. In certain cases, it may be necessary to set up a social app landing page or URI scheme in order to redirect or deep link users.

The following table summarizes when OneLinks can be used in today’s popular social apps:

<table><tbody><tr><td>Social app</td><td>Android users without app installed</td><td>Android deep linking</td><td>iOS users without app installed</td><td>iOS deep linking</td></tr><tr><td><strong>Facebook</strong> (including boosted posts)</td><td><span><strong>✓\*\*††</strong> </span></td><td><span><strong>✓\*\*††</strong></span></td><td><span><strong>✓</strong></span></td><td><span><strong>✓\*</strong></span> </td></tr><tr><td><strong>Facebook Messenger</strong></td><td><span><strong>✓\*\*††</strong> </span></td><td><span><strong>✓\*\*</strong></span> </td><td><span><strong>✓</strong></span></td><td><span><strong>✓\*</strong></span> </td></tr><tr><td><strong>Snapchat</strong></td><td><span><strong>✓††</strong> </span></td><td><span><strong>✓\*</strong></span> </td><td><span><strong>✓</strong></span></td><td><span><strong>✓\*</strong></span> </td></tr><tr><td><strong>Instagram</strong></td><td><span><strong>✓††</strong> </span></td><td><span><strong>✓††</strong></span></td><td><span><strong>✓</strong></span></td><td><span><strong>✓\*</strong></span> </td></tr><tr><td><strong>LinkedIn</strong></td><td><span><strong>✓</strong></span></td><td><span><strong>✓\*\*</strong></span></td><td><span><strong>✓</strong></span></td><td><span><strong>✓\*</strong></span></td></tr><tr><td><strong>Reddit</strong></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td><strong>Slack</strong></td><td><span><strong>✓</strong></span></td><td><span><strong>✓\*</strong></span> </td><td><span><strong>✓</strong></span></td><td><span><strong>✓\*</strong></span> </td></tr><tr><td><strong>X (formerly Twitter)</strong></td><td><span><strong>✓</strong></span></td><td><span><strong>✓\*</strong></span> </td><td><span><strong>✓</strong></span></td><td><span><strong>✓^</strong></span> </td></tr><tr><td><strong>WeChat</strong></td><td><span><strong>✓†</strong> </span></td><td><span><strong>✓†</strong> </span></td><td><span><strong>✓\*</strong></span></td><td><span><strong>✓\*†</strong> </span></td></tr><tr><td><strong>WhatsApp</strong></td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td colspan="5"><p>\* If <a href="./onelink-troubleshooting-and-faq#which-operating-systems-allow-uri-schemes-to-open-the-app">URI scheme</a>, or a <a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page" target="_blank">social app landing page</a> set up. <strong>Note</strong>: For Facebook and Facebook Messenger, if both URI scheme and a Social app landing page are set up, the Social app landing page doesn't display.</p><p>\*\* Must have URI scheme.</p><p>^ Must have social app landing page with Universal Links setup.</p><p><span><strong>†</strong></span> User may be prompted to open the link in an external browser.</p><p><span><strong>††</strong> Android social apps WebView deep linking redirection limitation. See details </span><a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection" target="_blank"><span>here</span></a><span>.</span></p></td></tr></tbody></table>

</Accordion>

<Accordion title="Can I use OneLink with ad networks (paid)?">

**Yes,** but note that OneLink is mainly used with owned media, not with ad networks. This is because ad networks usually advertise in apps (which means they know the user's platform, device ID, and so on), app and platform-specific attribution links suffice, so using OneLink isn't necessary. However, for cases in which ad networks don't know the user platform in advance (for example, when they run email or SMS campaigns themselves), OneLink can be the solution.

> 🚧 **Important**
>
> When you use OneLink with ad networks, you must use the OneLink long URL.

**To set up OneLink for partner ad networks:**

* Follow the <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">ad network attribution link instructions</Anchor>, and select **Use OneLink** when prompted.

Once all the parameters for Android and iOS are added correctly, when the OneLink custom link is clicked and the user is redirected to the right platform, the required parameters are sent to the network within a postback after the user installs.

> 👍 **Tip**
>
> The network uses either the IDFA or GAID parameters according to the client's device platform and disregards the other parameter.

</Accordion>

<Accordion title="How can I solve the iOS app-launching issue from social media apps?">

Facebook and other social media apps sometimes block iOS Universal Links from opening apps. <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Social app landing pages</Anchor> are the recommended solution for these app-launching issues.

If you do not want to use Social app landing pages, you can use URI schemes as a fallback method. Note, however:

* Using URI schemes as a fallback is subject to iOS-based limitations.
* For many browsers, including Safari, you must add the `af_force_deeplink=true` parameter to the URL to use URI schemes as a fallback. <Anchor target="_blank" href="/marketers/docs/uri-scheme-fallback-for-ios">Learn more</Anchor>.
* X (formerly Twitter) doesn't support URI schemes. A Social app landing page should be used to avoid app-launching issues.

</Accordion>

<Accordion title="Can I use OneLink on Instagram?">

**Yes,** but be aware of the following limitations:

* Due to the way Instagram renders the text of a page post, links are not clickable when entered into a post caption.
* App opening and deep linking into Android apps are supported without any special considerations. However, Instagram doesn't support app opening and deep linking into iOS apps. To overcome this issue, you can take one of two approaches:
  * **Recommended:** Configure a <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Social app landing page</Anchor>. The Clustered Poster and ShowAndTell templates work best. In addition to the Social landing page, we recommend setting a URI scheme in your OneLink template.
  * Use a URI scheme and [forced deep linking](/docs/onelink-troubleshooting-and-faq#forced-deep-linking) when using OneLinks on Instagram. Be sure to keep the following considerations in mind the following when using `af_force_deeplink=true` with OneLink on Instagram:

| App installed? | Click has af\_force\_deeplink=true? | Result |
| --- | --- | --- |
| No | Yes | Click opens the app store |
| No | No | Click opens the app store |
| Yes | Yes | Click opens the app |
| Yes | No | Click opens the app store |

</Accordion>

<Accordion title="Can I use OneLink on X (formerly Twitter)?">

Yes. You can use OneLink on X, but it’s strongly **recommended to configure it with a Social App Landing Page (SALP) and Universal Links.**

The reason is that X’s iOS in-app browser blocks redirection to the app-store and URI-scheme app opens, so OneLink setups that are configured only with URI scheme won’t open the app for existing users. Using SALP with Universal Links ensures that users are routed correctly—opening the app when installed, or sending new users to the App Store when needed.

</Accordion>

<Accordion title="Can I use OneLink for redirection on WeChat?">

WeChat overrides Android and iOS deep links and redirects users to a web page. From the web page, the user must click the **Options** button and choose to open the page in a browser. As a result, users encounter a broken user experience, increasing the chance for them to drop off in the conversion funnel.

To overcome this, OneLink recognizes clicks in WeChat and loads a dedicated landing page instructing the user to click the options button and then to click **Open in Browser.** This, in turn, opens the redirect URL defined in the OneLink template setup.

![WeChat_a.jpg](https://files.readme.io/49c03a10d458f6ce71fd6448e922294682ac9239775534c6264c29151ec1ea6d-30192900489105.jpg)

If the user’s WeChat language is registered as Chinese, OneLink generates a localized version of the landing page:

![WeChat_b.jpg](https://files.readme.io/502ef821a122459ab991f2a507c720f25fcac7129eb647a01290e8cabfa7a34e-30192887085841.jpg)

</Accordion>

<Accordion title="Why are Android users with the app installed being redirected to a web URL and not into the app when they click a link on Facebook webview?">

Opening the app and deep linking from an ad on Facebook is usually possible. However, if the following conditions apply, Facebook is not able to open the app for existing app users from the OneLink URL. Instead, all users, including those with the app, are sent to the URL defined in the OneLink template, or in the value of either the **af\_android\_url**, **af\_r**, or **af\_custom\_android\_url** parameter:

* User has an Android mobile device.
* Link is clicked on the Facebook app.
* Link leads to an HTML page that opens in Facebook webview (either a site or social app landing page).
* The HTML page contains a link with both an **af\_dp** parameter (with a URI scheme) and a URL redirection setting in either the OneLink template or in a parameter (one of **af\_android\_url**, **af\_r**, or **af\_custom\_android\_url**).

</Accordion>

<Accordion title="Why does clicking the video in a Meta Web Ads paid campaign result in a blank page on iOS?">

When a OneLink custom link is embedded behind the video in a Meta Web Ads paid campaign, clicking the video on iOS in the Facebook app requires a Social app landing page (SALP) to redirect the user to the App Store. If no SALP is configured, clicking the video results in a blank page instead.

</Accordion>

### Testing FAQ

<Accordion title="How can I A/B test the Social app landing page?">

The <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">social app landing page</Anchor> gives users a seamless app-launching experience when using OneLink in social network apps. You may be concerned that adding a step to the funnel decreases conversion rates. But the truth is, that without the landing page, user journeys are generally broken, resulting in very low conversion rates.

If you're not fully convinced, why not test it?

<Anchor target="_blank" href="/marketers/docs/create-a-b-tests">A/B test</Anchor> your custom link in social media apps, with and without the Social app landing page.

**To A/B test the Social app landing page:**

1. <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Create a OneLink link</Anchor> (called Link1) to use with social media apps. Don't set the Social app landing page for this link.
2. Add the **af\_adset** attribution parameter.
3. Add the **af\_ad** attribution parameter with the value "no lp".
4. Test Link1 outside of social media apps, and verify the link works and launches your app correctly.
5. Duplicate Link1 and call it Link2.
6. Change the **af\_ad** attribution parameter value to "using lp".
7. <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Create the Social app landing page</Anchor> for Link2 only.
8. Publish 2 different posts in the **same** social media app, using Link1 and Link2.  
   Don't worry about the different number of clicks each link produces. The important KPI is the final conversion rate of each link.
9. **Check the A/B test results after enough traffic is created.**
   1. Go to the AppsFlyer overview dashboard and scroll down to the **Aggregated performance report** table.
   2. Link1 and Link2 have the same media source, campaign, and adset name. Drill down to the specific adset.
   3. Compare the conversion rates (and other KPIs) of users that clicked either Link1 or Link2.

</Accordion>

<Accordion title="How can I bypass the app selection dialog?">

If you see an app selection dialog when testing your OneLinks, make sure to <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing">sign your app</Anchor>, even if it's a <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing#debug-mode">debug app.</Anchor> The certificate you use to sign the app is the same certificate you use to <Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-for-deep-linking-and-deferred-deep-linking#generating-a-sha256-fingerprint">generate the SHA256 fingerprint</Anchor> when configuring OneLink for App Links.

</Accordion>

### Deep linking FAQ

<Accordion title="What deep linking methods should be implemented?">

Your developers should implement the unified deep linking (UDL) method for deep linking. See our full <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">instructions for deep linking</Anchor>.

iOS Universal Links and Android App Links are **app-launching methods, which don't actually deep link users** (sending them to specific content within the app). The URI scheme method can launch the app and deep link users (via the **af\_dp** custom link parameter), but it should only be configured for app-launching. Its main usage is as a fallback method for Universal Links and App Links and for app-launching users with Android OS versions prior to 6.0.

After the app is launched using any of these methods, the AppsFlyer SDK supplies the **deep\_link\_value** specified in the custom attribution link. This value should be delivered via the UDL method implemented by your developers.

</Accordion>

<Accordion title="Can a URI scheme (af_dp parameter) be used for deep linking?">

**Yes,** but it's not recommended. Ideally, you should use the **deep\_link\_value** for deep linking, and the URI scheme as a fallback method to launch the app without deep linking (via the **af\_dp** parameter). However, if you already have the URI scheme set up to deep link, with additional parameters concatenated as part of the URI path (for example, greatapp://param1/param2), there is no need to change your existing configuration or code; the URI scheme will continue to work.

**The best practice for adding custom parameters is via the custom link setup page**.

</Accordion>

### iOS 14 FAQ

<Accordion title="Does OneLink deep linking work for iOS 14?">

There is no user experience impact to iOS 14 users who are deep linked from campaigns on ad networks and owned media using the UDL method. The legacy method may impede deep linking.

For attribution/reporting purposes, AppsFlyer uses IDFA or IDFV when available. If there is no IDFA or IDFV, probabilistic modeling may be used. Starting with iOS 14.5+, probabilistic modeling is limited to the context of owned media, cross-promotion, and consenting user web-to-app flows.

</Accordion>

<Accordion title="Does OneLink deferred deep linking work for iOS 14?">

There is no user experience impact to iOS 14 users who are deferred deep linked from campaigns on ad networks and owned media using the UDL method. The legacy method may impede deferred deep linking.

For attribution/reporting purposes, AppsFlyer uses IDFA or IDFV when available. If there is no IDFA or IDFV, probabilistic modeling may be used. Starting with iOS 14.5+, probabilistic modeling is limited to the context of owned media, cross-promotion, and consenting user web-to-app flows. We advise customers who want to implement deferred deep linking from ad networks and owned media to use AppsFlyer iOS SDK V6.1.0+ to allow for ATT consent (if needed), mitigate any attribution impact, and benefit from faster response times.

</Accordion>

<div data-zendesk-anchors="01H7WPYJV9CQ1J6J3PFCEQFGB0=onelink-troubleshooting-guide 01H7WPYJV9H52P659N8JPRX2TY=onelink-frequently-asked-questions 01H7WPYJV9TJRKHFZ77DFMKDDG=onelink-template-faq 01H7WPYJV9JSQ5FV73YCE3H5AF=deep-linking 01H7WPYJVAPNYAQ1SH4FBX4Z9F=onelink-link-faq 01H7WPYJVACCGVJD1Z7ZPVG2SQ=fallback-urls 01H7WPYJVA1W3HYYJJFQM01136=forced-deep-linking 01H7WPYJVAGRVWHRVMZVQG1ZVE=onelink-parameter-faq 01H7WPYJVB8ZZSKFT1V01EN6QF=integrated-partner-faq 01H7WPYJVC1PJJDA0GGT1DVVCF=testing-faq 01H7WPYJVCTM39HKCG9JN03BN6=deep-linking-faq 01H7WPYJVCVCVWHJW4RH85KC40=ios-14-faq" />

---
title: QR-to-app conversion
metadata:
  keywords:
    - OneLink
    - Advertisers
    - owned media
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2020-11-04T09:49:23Z'
  edited_at: '2026-02-24T15:52:52Z'
  id: 360015119718
  locale: en-us
  section: Owned media attribution
  section_id: 6551214397585
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360015119718-QR-to-app-conversion
---
> **At a glance:** Convert desktop, TV, CTV, or offline users, into mobile app users by using QR codes generated with OneLink.

![6005_QR_code_4.jpg](https://files.readme.io/6db45d7e82bc33ba8af8c6e7d096011d71b06766da9df348dccfa1b3e4aa380d-12368835107601.jpg)

## Converting mobile, non-mobile and offline traffic into mobile app users

Posting OneLink-generated QR codes on ads for desktop, TV, CTV, or offline, such as on in-store displays, brochures, and packaging, provides the following benefits:

* Users can quickly and easily scan the code with their mobile device to download and install your app.
* Users save the time and effort required to go to the app store and search for your app, which greatly increases QR-to-app install conversion rates.
* Privacy is protected, as this conversion method bypasses SMS, and users don't need to provide private information, such as a phone number for you to text.
* You can easily attribute installs and measure the efficacy of your ads.

QR codes can be created either:

* [Manually, in the AppsFlyer UI](/docs/qr-to-app-conversion#manual-qr-code-setup)
* <Anchor target="_blank" href="/marketers/fr/docs/set-up-smart-script-to-convert-web-visitors#qr-codes">Dynamically, using the OneLink Smart Script</Anchor> (specifically designed for web-to-app desktop flows)

<div id="qr-to-app-conversion" />

<Accordion title="QR to App conversion">

#### MANUAL QR CODE SETUP

**Prerequisites:**

* An AppsFlyer account with at least one app.
* For attribution: <Anchor target="_blank" href="/marketers/fr/docs/integrate-the-appsflyer-sdk">The AppsFlyer SDK already integrated</Anchor> in each of your mobile apps.
  * If the SDK is not yet installed in your apps, it is still possible to create a working redirection link, but it will not be possible to deep link, deferred deep link, or measure installs in your dashboard.

* A <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#create-a-onelink-template">OneLink template</Anchor> set up.

**To set up a QR code for QR-to-app conversion**:

1. Perform **one** of the following:
   * <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink">Create a single QR code image</Anchor>
     1. [Recommended] Create a new link and set the custom media source. For example, **desktop\_web**. Using a QR code from an existing link works. However, for reporting purposes, we recommend not sharing media sources with another link. Instead, use a separate link with the dedicated media source.
     2. After you click **Generate Link**, the QR code is displayed.
     3. Click the QR code to download it in full resolution, either in SVG or PNG format.
   * <Anchor target="_blank" href="/marketers/fr/docs/perform-onelink-bulk-actions-via-csv#downloading-a-collection-of-qr-codes">Create a collection of QR code images</Anchor>
     1. In the **Bulk Links** page, create a link collection.
     2. Download the QR images for the links in the collection.
2. Add the QR code to your ad, the same way you would add any other image/content.
   * See [best practices](/docs/qr-to-app-conversion#best-practices).
   * Developer assistance may be required.

</Accordion>

<div id="customize-qr-code" />

<Accordion title="Customize QR code">

![OnelinkQRFinal__1_.gif](https://files.readme.io/b1ad71a95057994fa0e2d4afbc1e75a99c468696ec90be419e38de664df86659-11941291055505.gif)

You can customize the QR codes generated via OneLink by:

* Adding your logo to the QR code
* Changing the color of the QR code.

**Note**:

* QR code customization occurs at the template level; not at the individual link level. Therefore, customizations affect all QR codes based on the edited template.
* QR codes created via the Smart Script can't be customized.

**To customize your QR code**:

1. In the AppsFlyer dashboard, go to **Experiences & deep linking** > **OneLink Management**.
2. Select the template you want to edit and click **Customize QR code** (available only to users with template editing permissions).  
   The QR code editor opens.
3. Enter the URL where your logo is hosted. For example: https://yourbrand.com/logo.png.

   Logo requirements:

   * PNG or JPG format
   * Square or circular with a transparent background
   * Minimum dimensions 400 x 400 px
   * For printing, use maximum image resolution
4. Set the QR code color.
5. Click **Save**.

</Accordion>

<div id="measure-qrtoapp-conversions" />

<Accordion title="Measure QR-to-app conversions">

You can measure the performance of your QR code and its placement on different ads/media sources, by comparing impressions (for desktop pageviews), clicks (for QR code scans), and app installs.

**To measure QR-to-app conversions**:

1. In AppsFlyer, check the Overview dashboard or other AppsFlyer analytics tools, and record the total **clicks** and **installs** with you QR code media source (such as **desktop\_web**).
2. Record the total desktop page views (impressions) using your web analytics software.
3. Measure performance:
   * <Anchor target="_blank" href="/marketers/fr/docs/about-conversion-rates#marketing-funnel-stages-and-conversion-rates-1">Click-through rate</Anchor>
   * <Anchor target="_blank" href="/marketers/fr/docs/about-conversion-rates#marketing-funnel-stages-and-conversion-rates-1">Click-to-install rate</Anchor>

</Accordion>

<div id="best-practices" />

<Accordion title="Best practices">

The following are tips to maximize QR-to-app conversions.

* For desktop, if you're using the manual QR code setup, build a separate page on your website to place the QR code.
  * Pick a URL slug for the page such as **/app**, **/download-app,** or **/mobile-app**.
  * Make the page viewable only for desktop/large screen width.
* For all ads:
  * Make the QR code on your ads large and high-resolution, so that it is easily scannable.
  * Add prominently situated **Download from App Store** and **Download from Google Play** badges as visual triggers (not as links).
  * Consider adding instructions on how to scan the QR code.
* Already using OneLink? In your *other* custom OneLinks, being used in emails, etc., add an **af\_web\_dp** parameter with the value being the URL to the page containing the QR code. This sends desktop users clicking the link to a webpage instead of the app store.

  [![](https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg)](https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg)

</Accordion>

## FAQ

In this section, you can find a list of frequently asked questions about QR codes.

<div id="qr-with-long-links-vs-short-links---is-there-any-difference" />

<Accordion title="QR creation with long links vs. short links – is there any difference?">

Your QR code will function with either a long or short URL. However, if you use a short URL, you'll be able to update the link parameters and behavior via the OneLink dashboard (under the Link Management or Bulk links section) without needing to replace the published QR code—since the short URL itself remains unchanged.

* **Short URLs:** If you change the parameters in the short URL configuration, the QR code remains the same. You don’t need to re-publish it.
* **Long URLs (e.g., Smart Script):** If you change the parameters on a long URL, the QR code changes as well. Once you've published it, you won’t be able to update the URL contents remotely—you'll need to generate and distribute a new QR code.

**Tip:** Creating a QR code using a short URL enables you to later modify the link’s parameters and behavior without needing to regenerate the QR code.

</Accordion>

<div id="can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example" />

<Accordion title="Can you create a QR code and change the behavior behind it retroactively, after printing the QR, for example?">

Yes, you can—if the QR code is based on a short OneLink URL that you can edit (for example, one created via the OneLink UI). A **QR code is a visual representation of the URL behind it**.  Changing the URL itself will create a new corresponding QR code (e.g., the QR code for mike.onelink.me/123A/shorturl is different from the QR code for mike.onelink.me/123A/example).

However, because a OneLink short URL is a hashed URL, its parameters and redirection rules are configured on the backend and aren't visible in the URL. This means you can keep the same visible URL and QR code while editing its backend configuration.

</Accordion>

<div id="what-appsflyer-options-are-available-for-generating-qr-codes" />

<Accordion title="What AppsFlyer options are available for generating QR codes?">

You have the following options:

* **Via the AppsFlyer Dashboard → OneLink UI:**
  * Automatically generates a QR code when you create a link
  * Allows QR code customization
  * Exportable as SVG or PNG
  * Based on a short URL
* **OneLink API v2 QR code:**
  * Generates large volumes of QR codes using <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelinkapi_v2_overview">OneLink API</Anchor>
* **Bulk QR code creation (via the Bulk Links page):**
  * Allows QR code customization
  * Exportable as SVG or PNG
  * Supports contextual file naming
  * Based on short URLs
* **Smart Script QR code generation:**
  * Based on dynamically generated long URLs
  * QR codes are created accordingly
  * Allows QR code customization

</Accordion>

<div id="can-you-bulk-create-qr-codes" />

<Accordion title="Can you bulk create QR codes?">

Yes. You can:

* <Anchor target="_blank" href="/marketers/fr/docs/perform-onelink-bulk-actions-via-csv">Bulk QR code creation feature</Anchor> available on the Bulk Links page.
* Create large volumes of QR codes using <Anchor target="_blank" href="/marketers/fr/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor>.

</Accordion>

<div data-zendesk-anchors="converting-mobile-nonmobile-and-offline-traffic-into-mobile-app-users=converting-mobile-non-mobile-and-offline-traffic-into-mobile-app-users h_01HKWVMKP3QT59EXPHQEPHW8K9=converting-mobile-non-mobile-and-offline-traffic-into-mobile-app-users h_01HKWWQXVC11E8M3NV3A03SWYD=qr-to-app-conversion h_01HKWWQXVCB96WDMBSE9WH9ZC5=manual-qr-code-setup h_01HKWVMKP3R5C5FPH010ZJZAHS=customize-qr-code h_01HKWVMKP3XTF6NNPNM8J00NWD=measure-qrtoapp-conversions h_01HKWVMKP3P6FNRPP1X7ZTNH10=best-practices qr-code-%E2%80%93-faq=faq h_01K42Q4QQVNQ4579CCM7QF7MQS=faq qr-with-long-links-vs-short-links-%E2%80%93-is-there-any-difference=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVKGQZKAS1PZ3B9H20=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVTV0KP280D15JF7NB=can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example h_01K42Q4QQVV1RZZXZK2Y9W8R58=what-appsflyer-options-are-available-for-generating-qr-codes h_01K42Q4QQVZF4H8FYZCTJPR0RX=can-you-bulk-create-qr-codes" />

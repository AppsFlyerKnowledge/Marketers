---
title: Smart Banners website code implementation for marketers
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developer
    - Developers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-10T11:25:54Z'
  edited_at: '2024-04-25T07:23:35Z'
  id: 4416119954705
  locale: en-us
  section: Web-to-app attribution
  section_id: 6551240476177
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4416119954705-Smart-Banners-website-code-implementation-for-marketers
---
> **At a glance:** Add the Smart Banners code to your website to convert your website visitors into mobile app users.

> 📘 **Note**
>
> AppsFlyer Smart Banner web SDK v1 was deprecated on Nov. 8th, 2023. To show Smart Banners on your website you need to upgrade to v2. <Anchor target="_blank" href="/marketers/id/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">Learn more</Anchor>

## Website code implementation

This article is intended for marketers who want to implement the Smart Banners code on their site via one of:

* Google Tag Manager (GTM)
* Adobe Launch Tag Manager
* Shopify
* Wix
* Squarespace
* WordPress

To add the code to your website via other platforms, or to make changes to the code based on need (including adding parameters, deep linking, hiding the banner, or integrating PBA with Smart Banners), see <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Smart Banners website code implementation for developers</Anchor>.

**To implement the Smart Banners code on your site**:

1. Follow the <Anchor target="_blank" href="/marketers/id/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup">website workplace instructions</Anchor> to get the Smart Banners code.
2. Use the platform-specific instructions that follow to implement the code into your website:

<div id="google-tag-manager" />

<Accordion title="Google Tag Manager">

**To implement the code via Google Tag Manager**:

1. In GTM, create a new tag.
2. Name the tag, click **Tag Configuration,** and select **Custom HTML**.
3. In the HTML box, paste the Smart Banner code snippet. Replace YOUR-BANNER-KEY in the snippet with your actual banner key.
4. Click **Triggering** and create a new trigger by clicking on the plus icon at the top right-hand corner of the screen.
5. Name the trigger, and then, under **Trigger Configuration,** and choose **Page View**.
6. If you want the banner to show up on all pages, select **All Page Views**. If you want the banner to show up on selected pages, select **Some Page Views** and define the condition to trigger the tag. To learn more about triggers, read <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">GTM's documentation</Anchor>.
7. Click **Save** at the top right-hand corner.
8. Return to the tag configuration screen. Verify that all is set and click **Save** at the top right-hand corner.
9. Publish your GTM container.

</Accordion>

<div id="adobe-launch-tag-manager" />

<Accordion title="Adobe Launch Tag Manager">

**To implement the code via Adobe Launch Tag Manager**:

<div id="step-1-create-a-property-in-adobe-experience-cloud" />

<Accordion title="Step 1: Create a property in Adobe Experience Cloud">

**To create a property (tag) that hosts the Smart Banners code**:

1. Go to **Adobe Experience Cloud** > **Launch**.
2. Under **Adobe Experience Cloud Launch**, click **Go to Launch**.
3. Click **New Property**.
4. Name your property.
5. Under **Platform**, select **Web**.
6. Enter your website domain.
7. Click **Save**.

</Accordion>

<div id="step-2-add-smart-banners-code-to-the-adobe-launch-property" />

<Accordion title="Step 2: Add Smart Banners code to the Adobe Launch property">

**To add the Smart Banners code to the tag**:

1. On **My web property** page, select the **Rules** tab.
2. Name the rule. Recommended: **AppsFlyer Smart Banners**.
3. In the **If** section, under **Events**, click **+Add**.
   * Under **Event Type**, select **Core - DOM Ready**.
   * Click **Keep Changes**.
4. In the **Then** section, under **Actions**, click **+Add**.
   * Under **Action Type** > **Custom Code**.
   * Select **JavaScript** > **Open Editor** and paste the Smart Banners SDK snippet **without the &lt;script> tags**.
   * Click **Keep Changes** to close the code editor.
5. Click **Save**.

</Accordion>

<div id="step-3-add-the-adobe-launch-tag-to-your-website" />

<Accordion title="Step 3: Add the Adobe Launch tag to your website">

**To add the Adobe Launch tag to your website (which loads the Smart Banners code)**:

1. On the **My web property** page, select the **Environments** tab.
2. Find the row with the environment you want to publish (development or production).
   * Under the **Install** header, click the box icon on the relevant row; this is usually a production environment.
   * See the section about publishing the **Adobe Launch** environment.
3. In the **Web Install Instructions** dialog box:
   * Copy the script code snippet.
   * Close the dialog box.
4. Paste the code snippet into the &lt;head> tag of your website.

</Accordion>

<div id="step-4-publish-the-adobe-launch-environment" />

<Accordion title="Step 4: Publish the Adobe Launch environment">

**To publish the environment to activate the Adobe Launch tag**:

1. On the **My web property** page, go to the **Publishing** tab.
2. Under the **Development** section, click **Add New Library.**
   1. Name the library and choose an environment.
   2. Under **Resource Changes**, click **Add a Resource.**
   3. Click **Rules** > **Load Smart Banners** > **Latest** > **Select & Create a New Revision**.
   4. Click **Save**.
3. Under the **Development** section:
   1. Next to the newly created library, click the Action menu (3 dots) and select **Build for Development**.
   2. Click the action menu again and select **Submit for Approval**.
4. Under the **Submitted** section:
   1. Click the action menu and select **Build for Staging**.
   2. Click the action menu again and select **Approve for Publishing**.
5. Under the **Approved** section click the action menu and select **Build & Publish to Production.** The process is now complete.

</Accordion>

Now, when your website loads on mobile, the banner's active creative will be displayed. To only display the banner on certain pages or according to user actions, see <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Adobe Launch rules</Anchor>.

</Accordion>

<div id="shopify" />

<Accordion title="Shopify">

**To implement the code in your Shopify website**:

1. In your Shopify dashboard, go to **Sales Channels** > **Online Store** > **Themes**.  
   Your current theme displays.
2. Click **Actions** > **Edit code**.  
   The Edit code page opens for your theme.
3. In the Layout folder, click the file that starts with **`{/}` theme**.  
   The webpage code displays.
4. In the code, directly under **&lt;head>**, paste your Smart Banners code.

</Accordion>

<div id="wix" />

<Accordion title="Wix">

**To implement the code in your Wix website**:

1. In your Wix dashboard, click **Settings**.
2. In the Advanced section of the Settings page, click **Custom code**.
3. Click **+ Add Custom Code**.
4. In the **Paste the code snippet here** box, paste the Smart Banners code.
5. In the Name box, enter a name for your code. **Recommended**: AppsFlyer Smart Banners.
6. In **Add Code to Pages**, select where to display your banners. Either:
   * All pages
   * Choose specific pages
7. Click **Apply**.  
   The Custom Code page should now show your code. Make sure it is placed in the **Head** section.

</Accordion>

<div id="squarespace" />

<Accordion title="Squarespace">

**To implement the code in your Squarespace website**:

1. In your Squarespace dashboard, click **Website**.
2. Click **Settings**.
3. Click **Advanced**.
4. Click **Code Injection**.
5. In the **Header** section, paste the Smart Banners code.
6. Click **Save**.

</Accordion>

<div id="wordpress" />

<Accordion title="WordPress">

**To implement the code in your WordPress website**:

1. In your WordPress dashboard, click **Appearance** > **Theme Editor**.  
   The Edit Themes page opens and the CSS code for your website displays.
2. Under **Theme Files**, click **Theme Header (header.php)**.
3. In the code that displays, under **&lt;head>**, paste the Smart Banners code.
4. Click **Update File**.

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/id/docs/pba-web-sdk-integration-guide#installation-and-integration">PBA integration with Smart Banners</Anchor>

<div data-zendesk-anchors="h_01HBT97B1ZGKKTD0TN2J2W56ZQ=note h_01HBT97B1Z0F4B8E9GQWJEE6BH=website-code-implementation h_01HBT97B1ZKW36W9F0XQKM323P=google-tag-manager h_01HBT97B1ZX6VM1YER2HXTYQJ2=adobe-launch-tag-manager h_01HBT97B1ZPP0AKB5E31W36VC2=step-1-create-a-property-in-adobe-experience-cloud h_01HBT97B1ZK4T23MF4D6VGP4B8=step-2-add-smart-banners-code-to-the-adobe-launch-property h_01HBT97B1Z0W9VJ5FCW4605RDC=step-3-add-the-adobe-launch-tag-to-your-website h_01HBT97B1Z1W33DTT6NR4PQHQ0=step-4-publish-the-adobe-launch-environment h_01HBT97B1Z0NTYJKB2YFMX62P9=shopify h_01HBT97B1ZYVJ6PW7F811V5TAX=wix h_01HBT97B1ZS0FDM60M1GA04PRT=squarespace h_01HBT97B1ZKYB7XPGFG00PB2BT=wordpress h_01HE7SG3MJ4WTPMTXF0DA0M07D=see-also" />

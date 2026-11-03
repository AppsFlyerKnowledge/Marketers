---
title: Perform OneLink bulk actions via CSV
metadata:
  keywords:
    - Marketers
    - bulk
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2023-04-13T11:31:43Z'
  edited_at: '2026-10-13T01:36:02Z'
  id: 14511403892369
  locale: ko
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ko/articles/14511403892369
---
> **At a glance:** The OneLink Bulk Links page allows you to create and manage OneLink custom shortlinks in bulk.

You can create, view, and edit links generated in bulk. These links are organized into a convenient collection format, allowing you to perform batch actions on the whole collection, such as adding new links, downloading them, and generating QR code image files.

## Getting started

1. In AppsFlyer, go to **Engage** > **Bulk links**.
2. You will see an intro page with one of the following buttons:
   1. **Get Started** - Click to create your first collection.
   2. **Create a OneLink template** - Make sure you have at least one OneLink template in your account, and a Growth/Enterprise plan. See <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">OneLink templates</Anchor>.
   3. **Upgrade** - Bulk links are available with the Enterprise or Growth plan. Contact your CSM or write to [hello@appsflyer.com](mailto:hello@appsflyer.com) about upgrading your package.

## Creating your first collection

1. Click **+ New collection.**
2. Enter a name for your collection.  
   Choose a name that reflects the purpose of your collection so you can quickly identify it later.
3. Select a OneLink template. Note: all the collection links will be based on this template
4. Click **Save & continue.**
5. Upload your CSV file. You can use the following [Sample CSV](https://cdn.appsflyer.com/onelink-bulk-links-mgmt/sample_file.csv) as a guide.  
   See  
   [Upload format](/docs/perform-onelink-bulk-actions-via-csv#upload-format) to make sure your CSV is compatible and uploads successfully. Once the CSV file is uploaded, it gets validated. If there are invalid rows, a validity report CSV will be available for download to help fix your file. Follow the instructions in the UI and upload a corrected file.
6. Click **Create collection.**

## Managing your bulk links with collections

Bulk links are managed in collections.

* At the top of the page, the **Bulk link usage this month** widget shows the number of link requests (that includes link creations and updates) out of the monthly quota for the current month.
  * Currently, the default limit is 20,000 link creations per month.

* The **Collections** section allows you to create a collection and perform other actions to your current link collections.
* You can search and filter your collection list if there are more than seven collections.
* Each collection can contain up to 2000 links.

## Other actions

Following are the other actions that can be performed on a collection:

<div id="creating-a-new-collection" />

<Accordion title="Creating a new collection">

Creating a new collection is available when the [monthly usage](#managing-your-bulk-links-with-collections) is not exceeded.

1. Click **New collection**.
2. Follow the instructions.
   1. The process follows the same steps as [Creating your first collection](/docs/perform-onelink-bulk-actions-via-csv#creating-your-first-collection).

</Accordion>

<div id="downloading-a-collection-of-links" />

<Accordion title="Downloading a collection of links">

The download collection option is available when:

* There are active links in that collection.
* You have app access permissions to at least one of the mobile apps of the OneLink template related to the collection.

To Download a collection:

1. In AppsFlyer, from the side menu, select **Engage** > **Bulk links.**
2. In the collection row click the download links icon ![links.png](https://files.readme.io/eb3548960149ec6d0274acf683f693773f4bb9800d624a6ed056c5a1b0b33343-21656949393937.png) .
3. Select the domain for the short URL output.
4. Click **Download**.

> 🚧 **Important!,**
>
> AppsFlyer recommends using Branded Domains as they can improve campaign performance by driving trust and promoting brand awareness. <Anchor target="_blank" href="/marketers/ko/docs/brand-onelink-with-your-domain">Learn more here.</Anchor>

</Accordion>

<div id="downloading-a-collection-of-qr-codes" />

<Accordion title="Downloading a collection of QR codes">

You can create QR code images for the entire collection.

1. In AppsFlyer, from the side menu, select **Engage** > **Bulk links.**
2. In the collection row, click the download QR code images icon <Image alt="generate qr.png" src="https://files.readme.io/23dbd4b2e3ed248e868ae7d5deee3cac383b0e018ae17204f9547f5707a428c9-21656949404561.png" width="22px" /> .
3. In the **Generate QR code images** dialog, set the following:
   * **Domain:** Select the subdomain or the branded domain of the URL that end users will see after they scan the QR code.
   * **QR code image format:** Choose either PNG or SVG as the format for the QR code image.
   * **QR code file name format:** Select the parameter whose values will be used as the prefix of the QR code image file names. Ensure that the values from this parameter add a meaningful context to the file names, helping you identify the purpose of each QR image.
4. Click **Generate.** You can monitor the file generation process in the **Download QR code images** panel.
5. To to download the ZIP file, click the download icon <Image alt="download-bulk.png" src="https://files.readme.io/8436aed2633bbed2f6cb65c00690711766c153c97042b5b157c199333e8723c2-21656949409041.png" width="18px" />.

> 📘 **Note**
>
> * Upon successful generation, the file will be accessible from the panel for 24 hours and then will be automatically deleted.
> * The downloaded file is provided in ZIP format because the payload consists of multiple QR image files. If prompted by your browser to allow ZIP downloads, provide the necessary confirmation to continue.
> * You can run up to 2 QR code generation processes concurrently.

</Accordion>

<div id="adding-links-to-a-collection" />

<Accordion title="Adding links to a collection">

The adding links option is available when:

* You have app access permissions to at least one of the mobile apps of the OneLink template related to the collection.
* There are under 2000 active links in the collection.
* [Monthly usage](#managing-your-bulk-links-with-collections) has not been exceeded.

To add links to a collection, click **menu options** > **Add links to collection.**

* Links will be added using the method described in [Creating your first collection](/docs/perform-onelink-bulk-actions-via-csv#creating-your-first-collection) from point 5 onwards.

</Accordion>

<div id="editing-links-in-a-collection" />

<Accordion title="Editing links in a collection">

The editing links option is available when:

* There are active links in that collection.
* You have app access permissions to at least one of the mobile apps of the OneLink template related to the collection.
* [Monthly usage](#managing-your-bulk-links-with-collections) has not been exceeded.

**To edit links in a collection:**

1. Click **menu options** > **Edit links**.
2. Download the collection base CSV. This file contains all the links in the collection you can edit.
3. Follow the instructions in the first step to edit link parameters. For any links you want to update, make sure **Mark for update** is set to **true**.
4. Click **Next**.
5. Upload your edited CSV. See [Upload format](/docs/perform-onelink-bulk-actions-via-csv#upload-format) to make sure your CSV is compatible and uploads successfully.
   * Once the CSV file is uploaded, it gets validated.
   * If there are invalid rows, a validity report CSV is available for download to help fix your file. Follow the instructions in the UI and upload a corrected file.
6. Click **Update links**.

> 📘 **Notes**
>
> * If you have downloaded QR code images from this link collection, you can update the link parameters and continue using the same images since the QR codes themselves do not change.
> * Updating links via bulk editing will extend the links' time to live (TTL) by 365 days.

</Accordion>

<div id="viewing-the-collection-history" />

<Accordion title="Viewing the collection history">

To view the history of a collection, click **menu options** > **View collection history.**

The history window will show you the following actions as well as the date and time the action was performed and by whom:

* **Name changes:** The changes to the name of the collection.
* **Links added:** When links were added to the collection.
* **Links updated**: When links in the collection were edited and updated.
* **Collection** **created**: When the collection was created.
* **QR codes ZIP downloaded**: When the QR code images were generated and downloaded for the collection.

**Links added and updated** also show you how the changes affected your [usage amount](#managing-your-bulk-links-with-collections) and allow you to download an action report on that change.

* Action reports can only be downloaded if you have app access permissions to at least one of the mobile apps of the OneLink template related to the collection.

</Accordion>

<div id="editing-the-collection-name" />

<Accordion title="Editing the collection name">

The editing collection name option is available when:

* You have app access permissions to at least one of the mobile apps of the OneLink template related to the collection.

To edit a collection name:

1. Hover over the collection name you want to change.
2. Click the edit icon next to the collection name.
3. After you have edited the name, click enter or click elsewhere on the screen.

</Accordion>

<div id="deleting-empty-collections" />

<Accordion title="Deleting collections">

To delete a collection, you'll need to have app access permissions to at least one of the mobile apps of the associated OneLink template.

**To delete a collection:**

1. In AppsFlyer, go to **Engage** > **Bulk links**.
2. Click the action menu next to the collection you want to delete and select **Delete collection**.

> 📘 **Important notes**
>
> * Make sure you want to delete the collection. Deleting a collection with active links will break the links, meaning users clicking them won’t be attributed or redirected correctly. **Deleting a collection is irreversible.**
> * If you want to keep a record of which links you've deleted, you can download the collection before deleting. **To download as a CSV file:**
>   Click **Download the collection** in the confirmation message.

### Empty collections

**Reasons a collection may be empty:**

* The TTL (time to live) of all links in the collection expired.
* The New collection process was canceled or failed to complete before links were created.

Empty collections can also be deleted in the way described above.

</Accordion>

## General information

> 📘 **Note**
>
> Bulk links created before April 2023 will not show or be managed on the bulk link page.

<div id="upload-format" />

<Accordion title="Upload format">

In order to make sure your CSV uploads without any errors, make sure that your file meets the following standards:

* The file must be in a CSV format
* The file cannot be bigger than 4 MB
* The file should only contain content for the links you are creating/updating
* Each link should be in their own row
* The **Custom Link ID** is a unique column, that enables the user to set the link short URL ID. The short URL ID cannot be edited after the link is created. To learn more about URL ID, see <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#url-id">here</Anchor>.
* Each column represents a parameter (Maximum 35 parameter columns)
* Only UTF-8 character encoding is accepted

</Accordion>

<div id="parameters-in-the-uploaded-csv" />

<Accordion title="Parameters in the uploaded CSV">

* Parameters in the CSV can be any parameter that is acceptable in an AppsFlyer link. It could be reserved parameters for attribution (e.g: c, af\_channel, af\_adset, etc.), for redirection & deep-linking (e.g: af\_ios\_url, af\_dp, deep\_link\_value, etc.), or custom parameters.
* The media source (pid) parameter is mandatory.
* Even if a URI scheme is set in the OneLink template, for links created in bulk, the af\_dp parameter with the URI scheme must be specified in your CSV file.

</Accordion>

## FAQ

<div id="qr-with-long-links-vs-short-links---is-there-any-difference" />

<Accordion title="QR with Long Links vs. Short Links – is there any difference?">

Your QR code will function with either a long or short URL. However, if you use a short URL, you'll be able to update the link parameters and behavior via the OneLink dashboard (under the Link Management section) without needing to replace the published QR code—since the short URL itself remains unchanged.

* **Short URLs:** If you change the parameters in the short URL configuration, the QR code remains the same. You don’t need to re-publish it.
* **Long URLs (e.g., Smart Script):** If you change the parameters on a long URL, the QR code changes as well. Once you've published it, you won’t be able to update the URL contents remotely—you'll need to generate and distribute a new QR code.

</Accordion>

<div id="can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example" />

<Accordion title="Can you create a QR code and change the behavior behind it retroactively, after printing the QR, for example?">

Yes, you can—if the QR code is based on a short OneLink URL that you can edit (for example, one created via the OneLink UI). A **QR code is a visual representation of the URL behind it**.  Changing the URL itself will create a new corresponding QR code (e.g., the QR code for mike.onelink.me/123A/shorturl is different from the QR code for mike.onelink.me/123A/example).

However, because a OneLink short URL is a hashed URL, its parameters and redirection rules are configured on the backend and aren't visible in the URL. This means you can keep the same visible URL and QR code while editing its backend configuration.

</Accordion>

<div id="what-options-are-available-for-generating-qr-codes-in-appsflyer" />

<Accordion title="What options are available for generating QR codes in AppsFlyer?">

You have the following options:

* **Via the AppsFlyer Dashboard → OneLink UI:**
  * Automatically generates a QR code when you create a link
  * Allows QR code customization
  * Exportable as SVG or PNG
  * Based on a short URL
* **Bulk QR code creation (via the Bulk Links page):**
  * Allows QR code customization
  * Exportable as SVG or PNG
  * Supports contextual file naming
  * Based on short URLs
* **Smart Script QR code generation:**
  * Based on dynamically generated long URLs
  * QR codes are created accordingly
  * Allows QR code customization
  * Supports bulk URL QR creation

</Accordion>

<div id="can-you-bulk-create-qr-codes" />

<Accordion title="Can you bulk create QR codes?">

Yes. You can bulk create QR codes using the [Bulk QR code creation feature](/docs/perform-onelink-bulk-actions-via-csv) available on the Bulk Links page.

</Accordion>

<div data-zendesk-anchors="h_01HKWSS511PMGTVEJN82SF5NX5=getting-started h_01HKWSS511SD4DFH7TMZV1EETH=creating-your-first-collection h_01HKWSS511XMB3CZ563SBZTEAC=managing-your-bulk-links-with-collections h_01HKWSS5113EPY13J2KHMWGDS7=other-actions h_01HKWSS511G8AREWDP05F6ZMER=creating-a-new-collection h_01HKWSS511DN9BSXFDNV053K63=downloading-a-collection-of-links h_01HKWSS511EDVWMAPHNGN711MG=important h_01HKWSS511SQR18RGSSKGTERCV=downloading-a-collection-of-qr-codes h_01HKWSS5112CT9HV7K81QSHMGM=note h_01HKWSS51125ZBCRQ087159YFH=adding-links-to-a-collection h_01HKWSS511AWCA4QV2NKVTTNKA=editing-links-in-a-collection h_01HKWSS512QYQBY0ZRE317528Z=notes h_01HKWSS512NZC3X8CPDDWB47JH=viewing-the-collection-history h_01HKWSS512RP5ATJWB38G88793=editing-the-collection-name h_01HKWSS512Q4MDFX75CK9VCREK=deleting-empty-collections h_01JQ69NF4SR7FT765JQP35B25G=important-notes h_01JQ69A1511N1GQFMBA2S748JK=empty-collections h_01HKWSS512JYNT3386P1KPZ452=general-information h_01HKWSS5123XVFKBZ892YCTFAC=note-1 h_01HKWSS5126A9XVE645CHCJD7X=upload-format h_01HKWSS512P7ZB213PCZ7JQTYP=parameters-in-the-uploaded-csv h_01K42S97K7KSKFC6BYEHPT0GZ5=faq qr-with-long-links-vs-short-links-%E2%80%93-is-there-any-difference=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVKGQZKAS1PZ3B9H20=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVTV0KP280D15JF7NB=can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example h_01K42Q4QQVV1RZZXZK2Y9W8R58=what-options-are-available-for-generating-qr-codes-in-appsflyer h_01K42Q4QQVZF4H8FYZCTJPR0RX=can-you-bulk-create-qr-codes" />

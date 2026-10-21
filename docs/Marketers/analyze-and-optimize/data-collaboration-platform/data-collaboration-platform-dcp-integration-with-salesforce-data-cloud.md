---
title: Data Collaboration Platform (DCP) - Integration with Salesforce Data Cloud
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-02-29T14:30:51Z'
  edited_at: '2025-02-03T13:14:45Z'
  id: 22977208909969
  locale: en-us
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/22977208909969-Data-Collaboration-Platform-DCP-Integration-with-Salesforce-Data-Cloud
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**At a glance:** The Salesforce Data Cloud integration allows you to bring your first-party data to the AppsFlyer Data Collaboration Platform with a click of a button.

> 🚧 **Before you begin**
>
> Before integrating Salesforce Data Cloud, you must **install the AppsFlyer app extension** from the Salesforce AppExchange. This must be performed by a Salesforce admin user with permission to download AppExchange packages.
>
> 1. Go to the <Anchor target="_blank" href="https://appexchange.salesforce.com/appxListingDetail?listingId=6c756ddf-777c-42fc-9eaf-d96ca36ed2e3">AppsFlyer listing</Anchor> on the Salesforce AppExchange.
> 2. Click **Get It Now**.
> 3. Follow the steps described in the <Anchor target="_blank" href="https://developer.salesforce.com/docs/atlas.en-us.appExchangeInstallGuide.meta/appExchangeInstallGuide/appexchange_install_installation.htm">Application Installation Guide</Anchor>.
>
> Upon successful installation, the process is complete and there's no need for any additional package configuration.

## Set up the integration

The integration involves creating a Salesforce Data Cloud connection and then creating sources. You only need one connection to authenticate your Salesforce account. Using this connection, you can create multiple sources based on Salesforce tables.

> 📘 **Note**
>
> If you've already set up a connection with Salesforce Data Cloud, you won't be able to create another one.

### Create a Salesforce Data Cloud connection

1. In AppsFlyer, from the side menu, select **Collaborate** > **Data Clean Room**.
2. From the top-right of the page, click **Manage connections** > **+ New connection**.
3. In the **New connection** dialog, select **Data providers** > **Salesforce Data Cloud**.  

   <Image alt="salesforce-data-cloud-new-connection.jpg" src="https://files.readme.io/6b240e0cff3f0bc9e6b7f6eaf45520a78252e1619769a696855e8d68d322ce60-23301617982353.jpg" width="517px" />
4. Click **Log in to Salesforce**.
5. Proceed with the authentication process and allow Salesforce access to AppsFlyer.   
   **Note:** If the authentication is unsuccessful, you're returned to the **New connection** dialog to try again.
6. After successful authentication, you're returned to the **New connection** dialog with an indication that you have an active connection with Salesforce. You can now proceed and create a source.
7. Click **Create source** and follow the [instructions below](#create-a-salesforce-data-cloud-source) to create a Salesforce Data Cloud source.

### Create a Salesforce Data Cloud source

After authenticating your Salesforce account and setting up the connection with Salesforce Data Cloud, the next step is to create sources. These sources provide AppsFlyer with the necessary data each time you perform updates.

Access the **Sources** tab using the following methods:

* After completing the previous step, click **Create source**.
* Navigate from the AppsFlyer side menu to **Collaborate** > **Data Clean Room** > **+ New Source** showing at the top-right corner of the page.

> 📘 **Note**
>
> When creating your source, make sure restricted data isn't sent to AppsFlyer.

**To create a source:**

1. **Set source name:** Enter a <Anchor target="_blank" href="/marketers/docs/data-clean-room-working-with-sources#1-name-the-source">name for the source</Anchor>, and click **Next**.
2. **Set source location:**
   * **Select connection:** Salesforce Data Cloud is auto-populated after adding the connection. If not, choose it from the connection list.
   * **Table or View:** After the Salesforce Data Cloud connection is selected, table names and views from your Salesforce account are auto-populated. Select the table or view, and click **Next**.  

     ![create-source-sf-3-steps.jpg](https://files.readme.io/44549ef1cd59b99610944c604c1cdfd4d598352cd106877fab3a301ce14650f8-23306070497169.jpg)
3. **Configure source schema:** After a table or view is selected, the field names and types are auto-populated. You can edit the field types or remove unwanted fields by selecting the bin icon at the end of the field row.  
   **Note:** Make sure at least one field type serves as an identifier. For example, CUID, Platform ID, AppsFlyer ID, and SHA256 hashed ID.
4. Click **Save**. The new source is displayed in the list of all existing sources.

<div data-zendesk-anchors="h_01HPKB2ERPGD2PS4JBSDGYW3MC=before-you-begin 01HRW9TK3YZV32CXRM6Q2HCHS4=set-up-the-integration 01HRSFKVQNJ264M16A9X9AEP53=note h_01HRSDCVMHQ6C5R6R4S5XRT5KQ=create-a-salesforce-data-cloud-connection h_01HRSG0P4Q38WHGQWBY3S3D11W=create-a-salesforce-data-cloud-source h_01HRVPJ801B0VC879APZCGKDNE=note-1" />

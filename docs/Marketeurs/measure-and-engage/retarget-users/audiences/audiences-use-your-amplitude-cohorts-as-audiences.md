---
title: Audiences - Use your Amplitude cohorts as audiences
metadata:
  keywords:
    - Audiences
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2022-02-23T14:27:13Z'
  edited_at: '2025-03-18T08:53:05Z'
  id: 4470658876817
  locale: en-us
  section: Audiences
  section_id: 6551336428945
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4470658876817-Audiences-Use-your-Amplitude-cohorts-as-audiences
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Leverage your first-party data by syncing your Amplitude cohorts to AppsFlyer as imported audiences.

## About the Amplitude integration

The **AppsFlyer Audiences-Amplitude integration** allows you to sync the cohorts you define in your Amplitude account directly to AppsFlyer as <Anchor target="_blank" href="/marketers/fr/docs/audiences-import-audience-segments-from-internal-systems">imported audiences</Anchor>. AppsFlyer can then serve as your centralized location for connecting and maintaining these audience segments with partners, reviewing connected campaign metrics, and linking your first-party Amplitude and AppsFlyer data to leverage the power of both.

Amplitude cohorts can be synced with AppsFlyer on a one-time basis or as a scheduled sync with daily or hourly updates.

## Setting up the integration

Set up the Audiences-Amplitude integration from within the Amplitude platform.

### Define AppsFlyer data destinations

**Follow these steps in Amplitude to define AppsFlyer data destinations.** *Note that you must define a separate data destination for each app for which you are importing AppsFlyer audiences.*

1. From the **Data Destinations** section in Amplitude, select the **AppsFlyer** tile.
2. Under **Cohort Destinations,** select **AppsFlyer.**
3. Enter the following information in the **Connect to AppsFlyer** dialog box.

   **Important!** If there are previously created AppsFlyer data destinations in your Amplitude account, the dialog box will be a scrollable list that shows all the existing destinations. To create a new destination, scroll to the end of this list and click **Add another destination.**

   <Image align="center" alt="" src="https://files.readme.io/ba47fc9a411bd55d84ad34ccd5c1d74fecb1648f8f7aed3ae713965bef616ae8-33375708375441.png" />

   

| Field | Description |
| --- | --- |
| Name | Enter a name for the destination.<br /><br />If you will be creating more than one AppsFlyer destination in a single Amplitude project (for example, if you have more than one app in the project), be sure to create a name you will be able to easily identify later. |
| AppsFlyer API Token V2.0 | **To retrieve the AppsFlyer API token, follow these steps in AppsFlyer:**<ol><li>From the top menu bar, access the user menu (email address drop-down in the top right corner).</li><li>Select **Security center.**</li><li>In the **AppsFlyer API tokens** section, click **Manage your AppsFlyer API tokens.**</li><li>Copy the **V2.0** token.</li></ol> |
| AppsFlyer App ID | Enter the App ID of the app for this destination as it appears in the AppsFlyer dashboard:<br /><br />![amplitude_app_id_from_appsflyer_dashboard.png](https://files.readme.io/2e7da9a20f0c4b59e58f51823dd9753ecc36b77e84622821cb3cb65e4f7b2743-33375708378385.png) |
| Platform | Select the app platform (iOS or Android). |
| Identifier | Instruct AppsFlyer how to connect your Amplitude data to your AppsFlyer data by selecting an Amplitude User Property on the left and the AppsFlyer key to map it to on the right. The AppsFlyer key you select must be one of the following:<ul><li>**For iOS audiences:** iOS Advertiser ID, Amplitude User ID, or AppsFlyer Customer User ID</li><li>**For Android audiences:** Google Advertiser ID, Amplitude User ID, or AppsFlyer Customer User ID</li></ul> |

4. Click **Save** to save the new AppsFlyer destination.

### Sync Amplitude cohorts to AppsFlyer destinations

**Next, follow these steps to sync any of your Amplitude cohorts to your AppsFlyer destinations:**

1. From the **Cohorts** section of the Amplitude platform, select the cohort for which you want to create an AppsFlyer audience. (Alternatively, you can create a new cohort.)
2. Follow the link: **Click to view the cohort details.**
3. From the **Cohort Definition** page, click the **Sync to…** button.
4. Select the AppsFlyer tile, then click **Next.**

   The **Define Destination and Cadence** dialog box opens.

   <Image align="center" alt="amplitude_define_destination_and_cadence_dialog.png" src="https://files.readme.io/e9f726c731e865e6313bf430b1e5506db5a820fc7d3d544747a873cf08139b26-33375708382097.png" />
5. From the **Select an API target to sync to** list, select the name of the relevant AppsFlyer destination.
6. Choose whether you want to sync this cohort to AppsFlyer one time only or as a scheduled sync. (For scheduled syncs, choose whether to update daily or hourly.)
7. Click the **Sync** button to start syncing.

After the first sync is completed successfully, a new audience for this cohort will be visible in the Audiences tab of the Audiences dashboard.

By default, the name of the new audience is the name of the synced Amplitude cohort, followed by an alphanumeric identifier. You can edit the audience name from the Audiences dashboard if you wish.

<Image align="center" alt="amplitude_imported_audience.png" src="https://files.readme.io/a4f8efc6818d94a68b28ca62ae26215f17bfc7edcfb990855a042a2dee71f8b6-33375708383249.png" />

<div data-zendesk-anchors="overview=about-the-amplitude-integration h_01HNZP6HDVC5RBMKTCZY81HG4M=about-the-amplitude-integration h_01HNZP6HDVZH6Q1KGJE7FXSPMT=setting-up-the-integration h_01HNZP6HDVV3GSEPARCY1VABX8=define-appsflyer-data-destinations h_01HNZP6HDV6EFPCM5FE5XBAS78=sync-amplitude-cohorts-to-appsflyer-destinations" />

---
title: Creative Optimization partner integrations
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-09-14T13:52:36Z'
  edited_at: '2026-07-22T07:41:56Z'
  id: 18565403047569
  locale: en-us
  section: Creative Optimization
  section_id: 4419063475217
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/18565403047569-Creative-Optimization-partner-integrations
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Set up partner integrations to automatically import all your creative data into Creative Optimization.

![Creative integrations New.jpg](https://files.readme.io/2bfead93dbaac902956ea4379e3f360120d59e7454be354c567b2f182382ab2d-20130430776337.jpg)

## About partner integrations

A partner integration seamlessly and continuously imports your creatives from campaigns run through the partner, into <Anchor target="_blank" href="/marketers/docs/creative-optimization-guide">Creative Optimization</Anchor>.

### Data availability

Once a partner integration is added:

* The system backfills creative data and AppsFlyer performance data from the past 90 days. The data is typically available in Creative Optimization within 24 hours.
* Creative data will continue to be pulled from integrated partners twice a day, every day. The data is incorporated, and matched to other performance data points from AppsFlyer such as attribution, spend, clicks, impressions, revenue, etc. (AppsFlyer performance data is refreshed hourly). The **Creative Optimization dashboards display the combined data from all the above processes and are updated once daily** **at UTC + 10** (all creative data from the last 90 days is updated).

> 📘 **Note**
>
> To see AppsFlyer cost data (such as ROAS), an <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview">ROI360 subscription</Anchor> is required.

## Media partner integrations

This section describes how to set up integrations with each partner.

<div id="adikteev" />

<Accordion title="Adikteev">

**Prerequisites:**

* Credentials for integration:
  * Email (Adikteev username)
  * Adikteev password
  * **Note:** These must be the same credentials used to access your Adikteev dashboard.
* To enable us to pull all cost data from Adikteev, the same user who integrated <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview">ROI360</Anchor> should be the one to integrate Creative Optimization as well.

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **Adikteev**.
4. Select the apps that you are promoting.
5. Enter the email and password.
6. Click **Save**.

**Note:** Adikteev is also known as Trademob (trademob\_int).

</Accordion>

<div id="adjoe" />

<Accordion title="Adjoe">

**Prerequisite:**

* Credential for integration:
  * Token  
    Reach out to your Adjoe account manager to get the token. See <Anchor target="_blank" href="https://drive.google.com/file/d/16zMpKbRLmTLU-plnodELGAHZVe0CuC_F/view">Adjoe documentation</Anchor>

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **Adjoe GmbH**.
4. Select the apps that you are promoting.
5. Enter the token.
6. Click **Save**.

</Accordion>

<div id="applovin" />

<Accordion title="AppLovin">

**Prerequisites:**

* Ad account permissions for the relevant apps you want to integrate. **Note**: Authentication to AppLovin must be done by the account admin.
* An AppLovin **Account ID**, **Campaign Management API key**, and **Reporting API Key** are required. You can get these from your AppLovin Axon dashboard (click your account at the top right and select keys).

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:

   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.

   ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click + **New integration**.
3. In the **Partner** list, select **AppLovin**.
4. Select the apps that you are promoting.
5. Enter the AppLovin **Account ID**, **Campaign Management API key**, and **Reporting API Key.**
6. Then click **Save**.

> 📘 **Note**
>
> AppLovin's asset-level reporting API only returns data for the previous day. It doesn't support historical lookback. Because of this, when you activate the integration, AppsFlyer can only start collecting asset-level data from the activation date forward. As a result, full data coverage builds up gradually and is typically complete within 30 days of activation.

</Accordion>

<div id="google-ads" />

<Accordion title="Google Ads">

**Prerequisites:**

* Ad account admin permissions for the relevant apps you want to integrate.
* To enable us to pull all creative data from Google, the same user who integrated <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview">ROI360</Anchor> should be the one to integrate Creative Optimization as well. If there is no ROI360 subscription then you must have admin permissions to all relevant apps and ad accounts in Google AdWords.

**Note:**

* The integration with Google Ads is per user, which means that multiple users can have active integrations simultaneously.

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click + **New integration**.
3. Click the **Partner** list and select **Google Ads (AdWords)**.
4. Select the apps that you are promoting.
5. Click **Log in to Google**. The **Sign in with Google window** opens.
6. Complete the Google sign-in and provide your permissions. Note that in order for AppsFlyer to pull complete data, it is recommended that you have full permissions.
7. Click **Save**.

**Note:** We support UAC campaign (ACi, ACe, and ACpre) ad types only. The data of unsupported ad types will be available in Creative Optimization on the ad level only (not the creative level).

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

**Prerequisites:**

* ironSource credentials for integration:
  * Secret key
  * Refresh token
  * <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/ios/authentication/#step-1">Learn</Anchor> where to find your unique credentials.
* Either an Administrator or Contributor user role in ironSource. <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/air/user-management/#step-1">Learn how to set up user roles</Anchor>.

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **ironSource**.
4. Select the apps that you are promoting.
5. Enter the Secret key and Refresh token.
6. Click **Save**.

**Note:** Certain ad types aren’t supported, which means that their data in Creative Optimization is available on the ad level only (not the creative level). Unsupported ad types include Offerwall ads.

</Accordion>

<div id="liftoff" />

<Accordion title="Liftoff">

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **Liftoff**.
4. Select the apps that you are promoting.
5. Contact your Liftoff CSM to get your Liftoff reporting API username and password.
6. Click **Save**.

</Accordion>

<div id="facebook-ads" />

<Accordion title="Meta Ads">

**Prerequisites:**

* Ad account permissions for the apps you want to integrate. **Note**: The integration with Meta Ads is per user, which means that multiple users can have active integrations simultaneously.
* To pull creatives that are displayed on internal and/or external Facebook pages, make sure your Facebook Business Center admin provides the relevant permissions to the user setting up the integration with Creative.

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **Meta Ads**.
4. Select the apps that you are promoting.
5. Click **Log in with Meta Ads**.
6. Complete the sign-in and provide your permissions. **Note**: For AppsFlyer to pull complete data, we recommend that you have full permissions.
7. Click **Save**.

**Notes:**

* Because Meta Flexible Ads provide only one asset for reporting, only performance data associated with the best-performing asset (of an ad) is shown.
* Certain ad types aren’t supported, which means that their data in Creative Optimization is available on the ad level only (not the creative level). Unsupported ad types include: Catalog/DPA.

</Accordion>

<div id="mintegral" />

<Accordion title="Mintegral">

**Prerequisites:**

* Mintegral credentials for integration:
  * API key
  * Access key
  * <Anchor target="_blank" href="https://adv-new.mintegral.com/doc/en/guide/introduction/register.html">Learn</Anchor> where to find your unique credentials.

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **Mintegral**.
4. Select the apps that you are promoting.
5. Enter the **API key** and **Secret key.**
6. Click **Save**.

</Accordion>

<div id="moloco" />

<Accordion title="Moloco">

**Prerequisites:**

* To be able to pull creatives, you'll need a Moloco <Anchor target="_blank" href="https://help.moloco.com/hc/en-us/articles/360050566173-Invite-and-manage-users">"Workplace Owner" or "Ad Account Owner"</Anchor> role.
* Access to your Moloco API key.

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **Moloco**.
4. Select the apps that you are promoting.
5. Enter your Moloco API key.
6. Click **Save**.

**Note**:

* Certain ad types aren’t supported, which means that their data in Creative Optimization is available on the ad level only (not the creative level). Unsupported ad types include CTV ads.

</Accordion>

<div id="personaly" />

<Accordion title="Persona.ly">

**Prerequisites:**

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Click **+ New integration**.
3. In the **Partner** list, select **Persona.ly**.
4. Select the apps that you are promoting.
5. Enter the Persona.ly **API key** (get it from your Persona.ly account).
6. Click **Save**.

</Accordion>

<div id="reddit" />

<Accordion title="Reddit">

**Prerequisites:**

* To be able to pull creatives, you need a Reddit "Creator" or "Admin" role.

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **Reddit**.
4. Select the apps that you are promoting.
5. Click **Log in with Reddit**.
6. Complete the sign-in and provide your permissions. **Note**: For AppsFlyer to pull complete data, we recommend that you have full permissions.
7. Click **Save**.

</Accordion>

<div id="remerge" />

<Accordion title="Remerge">

**Prerequisites:**

* Credentials for integration (**Note**: These are the same credentials used to access your Remerge dashboard. See <Anchor target="_blank" href="https://help.remerge.io/hc/en-us/articles/115003440434-Remerge-Reporting-API">Remerge documentation</Anchor>):
  * User email
  * Password

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **Remerge**.
4. Select the apps that you are promoting.
5. Enter the email and password.
6. Click **Save**.

</Accordion>

<div id="revx" />

<Accordion title="RevX">

**Prerequisites:**

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Click **+ New integration**.
3. In the **Partner** list, select **RevX**.
4. Select the apps that you are promoting.
5. Enter the RevX **API key** (Contact your RevX account manager directly to get your API key).
6. Click **Save**.

</Accordion>

<div id="smadex" />

<Accordion title="Smadex">

**Prerequisites:**

* Smadex credentials for integration (**Note**: These are the same credentials used to access your Smadex dashboard):
  * Email
  * Password

**To add an integration:**

1. **Log in to Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **Smadex**.
4. Select the apps that you are promoting.
5. Enter the required credentials.
6. Click **Save**.

</Accordion>

<div id="snap" />

<Accordion title="Snapchat">

**Prerequisites:** Ad account permissions for the relevant apps you want to integrate. **Note**: The integration with Snapchat is per user, which means that multiple users can have active integrations simultaneously.

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **Snapchat**.
4. Select the apps that you are promoting.
5. Click **Log in with Snapchat**. The **window** opens.
6. Complete the sign-in and provide your permissions. Note that in order for AppsFlyer to pull complete data, it is recommended that you have full permissions.
7. Click **Save**.

**Note:** Certain ad types aren’t supported, which means that their data in Creative Optimization is available on the ad level only (not the creative level). Unsupported ad types include Collection Ads.

</Accordion>

<div id="tiktok" />

<Accordion title="TikTok">

**Prerequisites:**

* Ad account permissions for the relevant apps you want to integrate. **Note**: The integration with TikTok is per user, which means that multiple users can have active integrations simultaneously.
* To pull creative data from Spark Ads, make sure your TikTok Business Center admin provides the relevant permissions to the user setting up the integration with Creative.

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **TikTok**.
4. Select the apps that you are promoting.
5. Click **Log in with TikTok**. The **window** opens.
6. Complete the sign-in and provide your permissions. Note that in order for AppsFlyer to pull complete data, it is recommended that you have full permissions.
7. Click **Save**.

> 📘 **Notes**
>
> * On January 30, 2023, the new **TikTok for Business—Advanced SRN** integration `tiktokglobal_int` was added, while the **[Legacy] TikTok for Business** integration `bytedanceglobal_int` is gradually phasing out and will be deprecated by March 2024. Learn more in this <Anchor target="_blank" href="/marketers/docs/bulletin-tiktok-for-business-advanced-srn">bulletin</Anchor>.
>   * If the legacy integration (bytedanceglobal\_int) is still active after the new one (tiktokglobal\_int) is integrated, there will be a duplication of performance data in Creative Optimization as it will be pulled from both networks.
>   * Creatives won’t be duplicated since AI identifies the actual assets.
>   * Removing the legacy integration will not delete historical data from the product.
>   * To pull all the required data, the one who connects TikTok SRN must have the relevant permissions (an ad account admin is recommended).
> * Certain ad types aren’t supported, which means that their data in Creative Optimization is available on the ad level only (not the creative level). Unsupported ad types include Collections Ads and Shopping Ads.

</Accordion>

<div id="unity-ads" />

<Accordion title="Unity Ads">

**Prerequisites:**

* Unity service account credentials for integration:
  * Key ID
  * Secret key
  * Organization core ID

[See instructions for retrieving the credentials.](/docs/creative-optimization-partner-integrations#instructions-for-retrieving-the-credentials)

* The following service account (organization) roles selected within Unity:
  * The **Advertise API Admin** role is necessary to pull creatives.
  * The **Advertisers API Stats Viewer** role is necessary if you'd like to pull Unity metrics (in addition to creatives). <Anchor target="_blank" href="https://services.docs.unity.com/statistics/#section/Migrating-from-the-previous-version-of-the-API/Query-parameters">Learn more</Anchor>

**Note:** If these roles aren't available to you, please reach out to your Unity Ads CSM.

#### Instructions for retrieving the credentials

**To retrieve the Key ID and Secret key:**

1. Log in to Unity Ads.
2. On the main menu side panel, click on **Administration**, then **Service Accounts**.
3. Click the specific service account.
4. Click **+ Add key**.  
   This brings up the Key ID and Secret key.
5. Copy the **Key ID** and **Secret key**.  
   ![Unity get Key ID & Secret key image.jpg](https://files.readme.io/9c4d1b1e0e476546b8f8be3a7375c610c48db6f94344a3dbe48277a6d115f52e-20344146224401.jpg)

**To** **retrieve the** <Anchor target="_blank" href="https://services.docs.unity.com/advertise/v1/index.html#section/General-Information/Resource-IDs-Used-in-the-API-Calls">**Organization core ID:**</Anchor>

1. Within Unity Ads, click **Products** on the side menu.
2. Cick **Grow**.  
   ![Unity Org ID step 1 cropped.jpg](https://files.readme.io/5e8d2f54f5999c58b2e2b3591ae889f5051cae4073aa6c5ef17e16da6a60131f-22859368875153.jpg)
3. Click **Unity Ads User Acquisition**.  
   <Image alt="Unity Org ID step 2 cropped.jpg" src="https://files.readme.io/07a1c8e878a9ed7b6832012b3261866477b825d3b23e4973b8c5dadd675973e2-22859368883473.jpg" width="347px" />
4. Click **Settings**.  
   ![Get Organization core ID instructions 2 arrows.jpg](https://files.readme.io/aff97bcb1c255771fc46483d8d94a2f13c7ef26c45a7fc884b1c03c83da91ae5-20344868139153.jpg)
5. Copy the **Organization core ID**.

#### **To select a service account (organization) role:**

1. In the Unity dashboard, click **Administration**.  
   **<Image alt="Org roles step 1.jpg" src="https://files.readme.io/b9a9258cf324cdf0c73ab9be8d1646c43d2211d23cebafa3624582e6e964851f-20347001525777.jpg" width="372px" />**
2. Click **Service accounts**.
3. Click the relevant service account, then click **+ Manage organization roles**.  
   **![Org roles step 2.jpg](https://files.readme.io/f72334c392a89084c22fc6c6d97cedb051b4a53de9bad1eb3722c2e0f31852de-20347023191697.jpg)**
4. In the **Growth** dropdown menu, select the following service account organization roles:
   * **Advertisers API Stats Viewer**, to pull Unity metrics.
   * One of the other below roles, to pull the creatives:
     * Advertise API Admin
     * Advertise API Viewer
     * Advertise API Creative Packs Editor  
       <Image alt="Org roles step 3 without role names.jpg" src="https://files.readme.io/7b46417e6389f7c3675cc6f72b33e9b2833d5c561ef1d79122ed24605533b265-20347535827217.jpg" width="471px" />
5. Click **Save**.

**Note:** If you don't have access to these roles, please contact your Unity customer success manager or email [unityads-support@unity3d.com](mailto:unityads-support@unity3d.com) to request the required permissions.

#### **To add a Unity integration to the Creative dashboard:**

1. In the **Creative Optimization** dashboard, do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **Unity Ads**.
4. Select the apps that you are promoting.
5. Enter the key ID, secret key, and organization core ID.
6. Enter the <Anchor target="_blank" href="/marketers/docs/creative-optimization-guide#partner-metrics::e592ecd3">Partner metrics</Anchor> information to also get metrics as reported by Unity Ads (optional).
7. Click **Save**.

</Accordion>

<div id="x-ads" />

<Accordion title="X Ads (formerly Twitter Ads)">

**Prerequisites:**

* To be able to pull creatives, you'll need an X Ads "Account admin" or "Ad manager" role.

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Click **+ New integration**.
3. In the **Partner** list, select **X Ads**.
4. Select the apps that you are promoting.
5. Click **Log in with X Ads**.
6. Complete the sign-in and provide your permissions. **Note**: For AppsFlyer to pull complete data, we recommend that you have full permissions.
7. Click **Save**.

</Accordion>

<div id="youappi" />

<Accordion title="YouAppi">

**Prerequisite:**

YouAppi credentials for integration :

* Token  
  **Note**: You can reach out to your account manager in YouAppi to get the token. For more information, see <Anchor target="_blank" href="https://support.youappi.com/knowledgebase/reporting-api-for-re-engagement/">YouAppi documentation</Anchor>.

**To add an integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Click **+ New integration**.
3. In the **Partner** list, select **YouAppi**.
4. Select the apps that you are promoting.
5. Enter the token.
6. Click **Save**.

</Accordion>

## Additional information

<div id="creative-integrations-dashboard" />

<Accordion title="Creative Integrations dashboard">

The Creative Integrations dashboard is where you can add new media partner integrations. To add a new integration, follow the [specific instructions per partner](/docs/creative-optimization-partner-integrations#data-availability).

Once added, the dashboard displays the status of all your current integrations, with the following columns:

| Column | Description |
| --- | --- |
| Partner | The name of the integrated partner, for example, Meta Ads or ironsource\_int. Expand the partner column to see all the different connections for the partner. For example, each user might have their own connection. |
| App | The list of apps per integrated partner and specific user connection. |
| Integration update | The date when the partner integration settings were last updated. |
| Coverage status | The amount of creative performance data from the partner integration available in Creative Optimization dashboards and reports:<ul><li>**Low**: All apps included in this integration are missing data.</li><li>**Partial**: Some apps included in this integration are missing data.</li><li>**High**: All apps included in this integration have data.</li><li>**In progress**: Wait up to 24 hours for a status update.</li><li>**No data**: No data from this partner for the past 30 days.</li></ul>Click the status to see the coverage status breakdown by app. The per-app status means different things depending on whether you’re an ROI360 subscriber or not.<br /><br />**Non-ROI360 subscriber:**<ul><li>**High**: App has a lot of data available. Meaning the creatives pulled cover more than 85% of the total app installs (as reported by AppsFlyer) in the last 30 days.</li><li>**Low**: App is missing data. Meaning the creatives pulled cover less than 85% of the total app installs (as reported by AppsFlyer) in the last 30 days.</li></ul>**ROI360 subscriber:**<ul><li>**High**: Creatives pulled cover more than 85% of the cost as measured by AppsFlyer ROI360 in the last 30 days.</li><li>**Low**: Creatives pulled cover less than 85% of the cost as measured by AppsFlyer ROI360 in the last 30 days.<br />**Example**:<ul><li>AppsFlyer gets data for media source "Network A" with a total ad spend of $100.</li><li>Creative 1 had $85 ad spend and Creative 2 had $15.</li><li>If AppsFlyer pulls Creative 1 data, that covers 85% of cost, so it's "high" coverage.</li><li>If AppsFlyer pulls only Creative 2 data, that covers just 15% of cost, so it's "low" coverage.</li></ul></li></ul>**For both ROI360 and non-ROI360 subscribers:**<ul><li>**In progress**: Wait up to 24 hours for a status update.</li><li>**Low data**: Make sure the partner is correctly integrated, following the [partner-specific instructions](/docs/creative-optimization-partner-integrations#data-availability).</li><li>**No data**: No data from this app for the past 30 days.<ul><li>Make sure your general AppsFlyer setup is complete and working (not specifically for Creative).</li><li>Make sure that your app is active and there is traffic.<br />If the integration is managed by an agency, make sure the integration is correct, following the [agency instructions](/docs/creative-optimization-partner-integrations#agencies).</li></ul></li></ul> |

</Accordion>

<div id="agencies" />

<Accordion title="Agency integrations">

#### Add an agency integration

You can integrate with your agency partners to pull their data into the Creative dashboard.

**To add an agency integration:**

1. Log in to **Creative Optimization** and do one of the following:
   * If you don't have any partner integrations, click + **Add new integration**.
   * Otherwise, click the  ⋮  icon on the upper right of the dashboard to get to **Creative integrations**.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Click + N**ew integration**.
3. After selecting the Partner and Apps in the partner integration window, click the **Advanced settings: Agency** dropdown, and select the relevant agency.  

   <Image alt="Creative agencies.png" src="https://files.readme.io/74f0dc492bc530278687becdd0061e9c06081653b69ed525f237b97a9568e413-38395601553169.png" width="288px" />
4. Click **Save**.  
   The agency integration is added.

**Notes:**

* For each agency whose creative data you want to see on the dashboard, you'll need to create a separate partner integration with the "Agency" checkbox selected.
* Data is available from transparent agencies only. <Anchor target="_blank" href="/marketers/docs/view-agency-data">Learn more</Anchor>
* Creative data will be pulled from the agency only. This means that if you selected Google Ads as the partner, as in the example above, but you also have campaigns running directly with Google Ads, you will need to create an additional partner integration for Google ads.

#### Grant dashboard access to an agency

You can grant your agencies access to view their own creative performance data in the Creative Optimization dashboard if they have an AppsFlyer <Anchor target="_blank" href="/partners/docs/about-agency-accounts">agency account</Anchor>. This could serve to enhance transparency and collaboration.

**To enable access:**

1. From the AppsFlyer side menu, click **Collaborate** > **Partner Marketplace**  

   **<Image alt="From Collaborate click Partner Marketplace.png" src="https://files.readme.io/96485cefae79412a680915810c16b23619f73d9109212bfc45d1c0d42c2e529a-39258887136785.png" width="33.9%" />**
2. Search for the relevant partner agency from the search bar at the top of the page, then click on the partner.

   <Image alt="Search bar.png" src="https://files.readme.io/f1ff34a547af45eec73e7abd41105bbab9ff12d4a2636ed4b99634985ec58044-39258887138449.png" width="1210px" />
3. On the partner page, go to the **Permissions** tab and enable **Agency permissions**

   <Image alt="Agency permissions.png" src="https://files.readme.io/b307601f9b41800a146c664bdd9f6d24a5398be9022801505419aebb0741162c-39258856594705.png" width="71.31%" />
4. Then enable **Access Creative Optimization dashboard**   

   The agency will now have access to see your shared creatives in their dashboard. For agencies that haven't yet set up an AppsFlyer agency account and would like to, they can learn more <Anchor target="_blank" href="/partners/docs/getting-started-agency-onboarding">here.</Anchor>

</Accordion>

<div id="update-credentials" />

<Accordion title="Update credentials">

Once certain partner integrations are set up, their account-level credentials can't be changed (this doesn't apply to Meta ads, Google Ads, TikTok, and AppLovin). If you need to update credentials for a partner:

1. On the **Creative integrations** page, select the expander to the left of the partner, to open the partner connections.
2. Click the  <Image alt="3 dots icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="7px" />  menu icon to the right of the connection, then click **Delete integration**. ![partner-integration-side-menu.png](https://files.readme.io/43ba588af05ffb8dafa165cf5d760010d36bd8b6409f6f9f4ef131d695989ed2-18565371542033.png)
3. Create a new integration for the partner with the updated credentials.

</Accordion>

<div data-zendesk-anchors="about-creative-partner-integrations=about-partner-integrations h_01HAP6JQEFKAFK96WDBN0MERB6=about-partner-integrations media-partner-integrations=data-availability h_01HEQ2QR21MZB57S6MQ5ZWZ7ZQ=data-availability h_01K4M4JF53A3J1R5VACNVN4X8A=note h_01HC7W736NDRRAJ95Z28JS2J46=media-partner-integrations h_01HBAZ8724YYFVQWYV5F8F4F5S=adikteev 01H7SZ8RA055S4M11TTX1J0E55=adjoe 01H7SZ8RA0A52YQEMYX0GV44AB=applovin h_01KY4CAH2MKX650JS1R0N8X6B4=note-1 01H7SZ8RA0980TH09EP2ED9WSF=google-ads 01H7SZ8RA0DRWC76119ED96KHP=ironsource 01H7SZ8RA0428ZPRYD99GWRMK0=liftoff 01H7SZ8RA06V5BR4ABV0ZVK82Z=facebook-ads h_01JXCRAESXDAHGGJ71EB32NAPD=mintegral 01H7SZ8RA06G1W04NSEHSPSV2D=moloco h_01KRGPVZH0Z0DHEEJNP4ST5CD9=personaly 01J9V2ZJR6KYJERPR2Y2XNCREP=reddit 01H7SZ8RA0CDR1M5V2F177TG84=remerge h_01KRGPVZH00WKJ4VJN8QHAW3YS=revx h_01HZEP4F6M2W5HC76WVFP5Z5C0=smadex 01H7SZ8RA1H0Q47N1W3NST4PZW=snap 01H7SZ8RA1E221TK8VRWEF1FA4=tiktok 01H8VVCC8GW5AZ3M475XFZY9JW=notes 01H7SZ8RA1YTA3MGVJMXVTP78Y=unity-ads h_01GT6Z998RCBQWKDC9YGPJQGN6=instructions-for-retrieving-the-credentials h_01GT6ZFTGKMR18DTNVX706DH1R=to-select-a-service-account-organization-role to-add-a-unity-connection-to-the-creative-dashboard=to-add-a-unity-integration-to-the-creative-dashboard h_01GT6ZS52ZWY47BCT2NJVCFFEP=to-add-a-unity-integration-to-the-creative-dashboard 01J9V2ZJSKN37WSGKA6D12MYBH=x-ads 01H7SZ8RA1E37649AAH1DNRXA9=youappi agency-integrations=additional-information h_01HC7WCZ143S29PGTVNFEX962Y=additional-information 01J9WK9A78RP6BKX6860MAABFM=creative-integrations-dashboard h_01HC7WCE9EJK3NDJQE88RZ3T0Z=agencies h_01K5PE1K1G75KEF9HXMAW9YP2F=add-an-agency-integration grant-dashboard-access=grant-dashboard-access-to-an-agency h_01K5PE1WK5AE2MX235B8FA4YJ0=grant-dashboard-access-to-an-agency 01J9WKGYM1D04ZT14EPZ13VE4P=update-credentials" />

---
title: "Bulletin: Unity Ads cost API integration update"
excerpt: "Learn how to update your Unity Ads cost API integration in AppsFlyer with the new credentials required before the October 1, 2024 sunset date."
---
| **What's new** | AppsFlyer has an API integration with Unity that allows us to get cost data. The API is being updated soon. Therefore, you need to update your integration to continue getting Unity cost data. |
| --- | --- |
| **Update date** | August 6, 2024 |
| **What you need to know** | * Unity is introducing a new cost API integration.<br />* The old cost API integration is able to get cost data until its sunset date of October 1, 2024. |
| **What you need to do** | You must update your credentials for the new Unity cost API integration to continue getting cost data after October 1, 2024.<br /><br />The credentials required are:<br /><br />* Organization Core ID<br />* Service Account Secret Key<br />* Service Account Key ID<br /><br />Follow our instructions in the following sections to update the Unity cost integration in AppsFlyer. The integration has 2 steps:<br /><br />1. [Get the new Unity credentials](/docs/bulletin-unity-ads-cost-api-integration-update#get-unity-credentials).<br />2. [Update the Unity cost API integration by entering the credentials in AppsFlyer.](/docs/bulletin-unity-ads-cost-api-integration-update#set-up-unity-cost-api-integration-in-appsflyer) |



## Unity cost API integration procedures

Integrating the Unity cost API requires 2 steps:

1. Get the new Unity credentials.
2. Update the Unity cost API integration by entering the credentials in AppsFlyer.

The steps are described in the following sections.

### Get Unity credentials

The required credentials for the Unity cost API integration are:

* Organization Core ID
* Service Account Secret Key
* Service Account Key ID

**Note**: It is recommended to create a new Unity service account to get the secret key and key ID. We provide instructions on how to do so below.

**To set up a Unity service account and get the required credentials for the Unity cost API integration**:

1. Log in to your Unity Cloud account.
2. From the left-side menu, go to **Grow (Unity Ads User Acquisition)** > **Settings**.  
    [![](https://support.appsflyer.com/hc/article_attachments/26134832885137)](https://support.appsflyer.com/hc/article_attachments/26134832885137)
3. Find, copy, and save the **Organization Core ID**.  
   Example Organization Core ID: 5773102414648
4. From the left-side menu, go to **Grow (Unity Ads User Acquisition)** > **`{}` API Management** and in the **Stats API v2.0** section, **click Service Account.**  
    [![](https://support.appsflyer.com/hc/article_attachments/26369979011985)](https://support.appsflyer.com/hc/article_attachments/26369979011985)
5. Click **+ New** to create a new service account.  
    [![](https://support.appsflyer.com/hc/article_attachments/26136910848785)](https://support.appsflyer.com/hc/article_attachments/26136910848785)
6. In the **Keys** section, click **+ Add key** to create a key for the service account.  
    [![](https://support.appsflyer.com/hc/article_attachments/26136957380753)](https://support.appsflyer.com/hc/article_attachments/26136957380753)
7. Copy and save the **Key ID** and **Secret key**. **Note**: This is the only time you can access the secret key, so make sure you save it now!
   * Example service account secret key: b0de73b1-b3ad-4175-bf9b-4913a0ff83ec
   * Example service account secret key key ID: a0X\_cqHiXH4ABPS1Qr9TCy6EJdvG8ql5  
      [![](https://support.appsflyer.com/hc/article_attachments/26136957383697)](https://support.appsflyer.com/hc/article_attachments/26136957383697)
8. In the **Organization roles** section, click **+ Manage organization roles**.  
    [![](https://support.appsflyer.com/hc/article_attachments/26136910860689)](https://support.appsflyer.com/hc/article_attachments/26136910860689)
9. Under **Edit roles in organization**, set **Growth** to **Advertise Stats API MMP Viewer**.  
    [![](https://support.appsflyer.com/hc/article_attachments/26136957386513)](https://support.appsflyer.com/hc/article_attachments/26136957386513)

### Update Unity cost API integration in AppsFlyer

**To update the Unity cost API in AppsFlyer**:

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**, and select **Unity**.
2. Click **Manage integration**.
3. Open the integrated partner **Cost** tab.
4. Turn on the **Get Cost Data** toggle. The requirements to connect to the partner display.
5. Enter your Unity credentials.
6. Click **Save Cost**.
7. Click **Test Connection.**  
   * The API is active. AppsFlyer collects data from the partner 6 times a day, on average once every four hours.

[Learn more about connecting cost integrations](/docs/set-up-roi360-cost-api-to-measure-cost-data)
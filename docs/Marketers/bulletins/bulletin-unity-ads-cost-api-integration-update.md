---
title: "Bulletin: Unity Ads cost API integration update"
x-zendesk:
  id: 26078530790289
  url: https://support.appsflyer.com/hc/en-us/articles/26078530790289-Bulletin-Unity-Ads-cost-API-integration-update
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 16
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-maytav-avnat, Marketers, ROI360]
  labels: [Marketers, Localize, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2024-06-20T14:43:15Z'
  edited_at: '2024-08-08T08:32:27Z'
---
| **What's new** | AppsFlyer has an API integration with Unity that allows us to get cost data. The API is being updated soon. Therefore, you need to update your integration to continue getting Unity cost data. |
| --- | --- |
| **Update date** | August 6, 2024 |
| **What you need to know** | <ul><li>Unity is introducing a new cost API integration.</li><li>The old cost API integration is able to get cost data until its sunset date of October 1, 2024.</li></ul> |
| **What you need to do** | You must update your credentials for the new Unity cost API integration to continue getting cost data after October 1, 2024.<br /><br />The credentials required are:<ul><li>Organization Core ID</li><li>Service Account Secret Key</li><li>Service Account Key ID</li></ul>Follow our instructions in the following sections to update the Unity cost integration in AppsFlyer. The integration has 2 steps:<ol><li>[Get the new Unity credentials](/docs/bulletin-unity-ads-cost-api-integration-update#get-unity-credentials).</li><li>[Update the Unity cost API integration by entering the credentials in AppsFlyer.](/docs/bulletin-unity-ads-cost-api-integration-update#set-up-unity-cost-api-integration-in-appsflyer)</li></ol> |

## Unity cost API integration procedures

Integrating the Unity cost API requires 2 steps:

1. Get the new Unity credentials.
2. Update the Unity cost API integration by entering the credentials in AppsFlyer.

The steps are described in the following sections.

<div id="get-unity-credentials" />

<Accordion title="Get Unity credentials">

The required credentials for the Unity cost API integration are:

* Organization Core ID
* Service Account Secret Key
* Service Account Key ID

**Note**: It is recommended to create a new Unity service account to get the secret key and key ID. We provide instructions on how to do so below.

**To set up a Unity service account and get the required credentials for the Unity cost API integration**:

1. Log in to your Unity Cloud account.
2. From the left-side menu, go to **Grow (Unity Ads User Acquisition)** > **Settings**.  
    [![](https://files.readme.io/2fcc359913c11a4bcce29e1aaf30cb84161a09e39b14cdcd4ad4f141debd1798-26134832885137.png)](https://files.readme.io/2fcc359913c11a4bcce29e1aaf30cb84161a09e39b14cdcd4ad4f141debd1798-26134832885137.png)
3. Find, copy, and save the **Organization Core ID**.  
   Example Organization Core ID: 5773102414648
4. From the left-side menu, go to **Grow (Unity Ads User Acquisition)** > **`{}` API Management** and in the **Stats API v2.0** section, **click Service Account.**  
    [![](https://files.readme.io/36dd40e68eeeb6562c1e5a19f92873e8eb99b66f80c45db066e0ff54b66d0080-26369979011985.png)](https://files.readme.io/36dd40e68eeeb6562c1e5a19f92873e8eb99b66f80c45db066e0ff54b66d0080-26369979011985.png)
5. Click **+ New** to create a new service account.  
    [![](https://files.readme.io/3a53e932bf8d023e910b66f74ea6f630c8048787885d45ea4206b2f1f3d4f65e-26136910848785.png)](https://files.readme.io/3a53e932bf8d023e910b66f74ea6f630c8048787885d45ea4206b2f1f3d4f65e-26136910848785.png)
6. In the **Keys** section, click **+ Add key** to create a key for the service account.  
    [![](https://files.readme.io/f528d44a9659372bfeeb8d13538f9caf0a7955f53194194543988af983f9c517-26136957380753.png)](https://files.readme.io/f528d44a9659372bfeeb8d13538f9caf0a7955f53194194543988af983f9c517-26136957380753.png)
7. Copy and save the **Key ID** and **Secret key**. **Note**: This is the only time you can access the secret key, so make sure you save it now!
   * Example service account secret key: b0de73b1-b3ad-4175-bf9b-4913a0ff83ec
   * Example service account secret key key ID: a0X\_cqHiXH4ABPS1Qr9TCy6EJdvG8ql5  
      [![](https://files.readme.io/6de3cd868541ab5487370dbefc758a375c3395434e07361f74553a1b9a9c7d57-26136957383697.png)](https://files.readme.io/6de3cd868541ab5487370dbefc758a375c3395434e07361f74553a1b9a9c7d57-26136957383697.png)
8. In the **Organization roles** section, click **+ Manage organization roles**.  
    [![](https://files.readme.io/d368d6c611db2a8df76e341c7b6a692128b5ae37f51f6642fa7e60cd00f29689-26136910860689.png)](https://files.readme.io/d368d6c611db2a8df76e341c7b6a692128b5ae37f51f6642fa7e60cd00f29689-26136910860689.png)
9. Under **Edit roles in organization**, set **Growth** to **Advertise Stats API MMP Viewer**.  
    [![](https://files.readme.io/f1243cb65978d2f96d148ceb34b528ca005091c38dbed95368923047b3cfbfd1-26136957386513.png)](https://files.readme.io/f1243cb65978d2f96d148ceb34b528ca005091c38dbed95368923047b3cfbfd1-26136957386513.png)

</Accordion>

<div id="set-up-unity-cost-api-integration-in-appsflyer" />

<Accordion title="Update Unity cost API integration in AppsFlyer">

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

</Accordion>

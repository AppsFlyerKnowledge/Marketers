---
title: 'Bulletin: Migration to Pinterest’s New Postback Endpoint'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2025-07-23T07:26:53Z'
  edited_at: '2026-09-01T10:34:33Z'
  id: 37418019002641
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/37418019002641-Bulletin-Migration-to-Pinterest-s-New-Postback-Endpoint
---
<Table>
  <thead>
    <tr>
      <th>
        Section
      </th>
      <th>
        Details
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        **What’s New**
      </td>
      <td>
        Pinterest has migrated to a new endpoint based on their Conversions API (CAPI) infrastructure. You must upgrade in order to continue to send your app events to Pinterest. We will be deprecating the old endpoint on September 30, 2025.
      </td>
    </tr>
    <tr>
      <td>
        **Effective Date**
      </td>
      <td>
        07/23/2025
      </td>
    </tr>
    <tr>
      <td>
        **What you need to know**
      </td>
      <td>
        This bulletin includes information relating to the migration phase to CAPI. For a general information about the Pinterest integration see <Anchor target="_blank" href="/marketers/id/docs/pinterest-create-a-mobile-app-integration#in-app-events-settings">the KB article</Anchor>.<br /><br />Updating to the new API In-app events settings will ensure Pinterest measurement will continue without interruption, and it also includes:<ul><li>**More “events” types**: Track additional events to better align with your goals, such as: Lead, Search, Category Viewed, Page Visit, and more.<ul><li>**Note:** event names for the new Pinterest V5 endpoint are different. Unless the dashboard is updated accordingly, events report will display “unknown”. Please review the new event names below.</li></ul></li><li>**Improved data quality:** Benefit from enhanced matching and stronger attribution accuracy.</li></ul>The new integration requires both an **Ad Account ID** and an **Access Token**. To maintain postback functionality, partners must transition to the new postback endpoint by 9/30/25.<br /><br />**How to find Pinterest AppsFlyer Ad Account ID**<br />You can find the current AppsFlyer Pinterest Conversion reporting Ad Account ID in Pinterest **Business Manager** or Pinterest **Conversions** reporting.<ol><li>Log in to your Pinterest business account (you must be in a business profile to see the Hub options).</li><li>Type or paste https://www.pinterest.com/business/hub/ into your browser and press Enter.</li><li>Look at the dark-gray navigation column on the left side of the Hub. If the column is collapsed, click the small “≡” (hamburger) icon in the upper-left corner to expand it.</li><li>Scroll a little until you see the section titled “Manage business.”</li><li>Click Conversions (it sits right under “Manage business”). This opens the Conversions dashboard, where you can review AppsFlyer conversions sent to Pinterest.</li><li>Ad Account ID will be present in the URL.</li><li>If multiple Pinterest Ad Account IDs receive cloned conversions from AppsFlyer, verify all existing Ad Account IDs with Conversions in Pinterest Business Manager. Please ensure the original parent Ad Account ID for AppsFlyer conversions is selected.</li></ol>**How to find Pinterest AppsFlyer Access Token**<br />Please follow the steps outlined on Pinterest’s Help Center <Anchor target="_blank" href="https://help.pinterest.com/en/business/article/getting-started-with-the-conversions-api">here</Anchor>. Once in Pinterest Conversions, click on **Conversions API** > **Set-up API**, and generate a new access token for the account.<br /><br />**Important Note:** If you have already set-up Conversions API for Pinterest separately outside of AppsFlyer, use the same Access Token here for AppsFlyer conversions as well.
      </td>
    </tr>
    <tr>
      <td>
        **What you need to do**
      </td>
      <td>
        Please follow the instructions below for setting up and migrating in-app event postbacks in the AppsFlyer dashboard.<ol><li>**In-App Event Settings and Dashboard Parameter Handling**<br />We currently support the following dashboard parameters for mapping your Appsflyer events with Pinterest:</li></ol><ul><li>**Ad Account ID** (visible)</li><li>**Access Token** (visible)</li><li>**Tag ID** (not visible on the dashboard, but supported in the backend to assist with the transition to the new V5 version. Once the transition to the V5 endpoint is fully supported, the Tag ID will also be removed from the backend.)</li></ul>**Please Note:**<br />For the new postback setup, you must enter both the **Ad Account ID** and **Access Token** (these can be obtained from Pinterest if not already available). **If either of these values are missing, the postback will fail**. Kindly ensure both parameters are correctly filled in the Pinterest **Active Integration** page. For more information, see <Anchor target="_blank" href="/marketers/id/docs/pinterest-create-a-mobile-app-integration#in-app-events-settings">the KB article</Anchor>.<br />Your cooperation is important for a smooth transition. Thank you for your support.<ol><li>**In-App Event Mapping and Postback Settings**<ol><li>Please replace and map your current Pinterest event names with the new Pinterest Conversion API event names for the **Partner event name** section. For example, if you are currently using `pin_add_to_cart` in the Partner event section, replace that with `add_to_cart` instead. For more information see <Anchor target="_blank" href="/marketers/id/docs/pinterest-create-a-mobile-app-integration#in-app-event-postbacks">the KB article</Anchor>.</li></ol></li></ol>

        | event name (Legacy) | event name (new Conversions API) |
        | --- | --- |
        | pin\_add\_to\_cart | add\_to\_cart |
        | pin\_purchase | checkout |
        | pin\_search | search |
        | pin\_registration | signup |
        | pin\_sign\_up | signup |
        | pin\_category\_view | view\_category |
        | add\_cart | add\_to\_cart |
        | start\_checkout | checkout |
        | content\_view | view\_category |

        **Note:** Failure to update the legacy event names with the correct event names for Conversions API will result in ‘Other’ showing up for event names in Pinterest, instead of the correct event name.<ol><li>Select **in-app event postback window** to **Lifetime** so Pinterest can receive maximum number of conversions for ads optimization</li><li>Select **All media sources including organic** for **To users from** so Pinterest can receive maximum number of conversions for ads optimization. For more information see <Anchor target="_blank" href="/marketers/id/docs/pinterest-create-a-mobile-app-integration#in-app-event-postbacks">the KB article</Anchor>.</li></ol><ol><li>**Roll-back process in case of issues**<br />Advertisers are advised to monitor their AppsFlyer app conversions on Pinterest to detect any issues or problems with the migration. Please give it up to 30 mins for AppsFlyer conversions data to show up in Pinterest and ensure regular monitoring for a few days to validate migration success.</li></ol>Advertisers can revert to the legacy endpoint by omitting either one or both of the `account_id` and `access_token` in the integration setup.<br /><br />**Behavior Rules:**<ul><li>Both `account_id` and `access_token` are absent → Postbacks are sent to the legacy (old) endpoint.</li><li>Only `account_id` is provided (i.e., `access_token` is empty) → Postbacks are sent to the legacy endpoint.</li><li>Only `access_token` is provided (i.e., `account_id` is empty) → Postbacks are sent to the legacy endpoint.</li><li>Both `account_id` and`access_token` are provided → Postbacks are sent to the new endpoint.</li></ul>If you are facing any issues, please reach out to AppsFlyer Support through support@appsflyer.com. For any issues on Pinterest please reach out to api-support@pinterest.com or to your Pinterest representative.
      </td>
    </tr>
  </tbody>
</Table>
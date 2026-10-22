---
title: 'Bulletin: New fields in ad revenue reports'
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-07-22T13:25:32Z'
  edited_at: '2024-09-24T12:01:56Z'
  id: 26907692192273
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/26907692192273-Bulletin-New-fields-in-ad-revenue-reports
---
<Table>
  <thead>
    <tr>
      <th>
        **What's new?**
      </th>
      <th>
        Ad revenue reports have new fields.
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        **Effective date**
      </td>
      <td>
        September 19, 2024
      </td>
    </tr>
    <tr>
      <td>
        **What you should know**
      </td>
      <td>
        The following table shows which fields are being added to which reports. See the <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary">raw data field dictionary</Anchor> for definitions and details of each field.<table><thead><tr><th>Report</th><th>API field names</th></tr></thead><tbody><tr><td><Anchor target="_blank" href="/marketers/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">Legacy ad revenue [single version]</Anchor></td><td><ul><li>engagement_type</li><li>custom_data</li><li>customer_user_id</li><li>ad_revenue_ad_type</li></ul></td></tr><tr><td><Anchor target="_blank" href="/marketers/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">Ad revenue [versioned]</Anchor></td><td><ul><li>engagement_type</li><li>custom_data</li><li>customer_user_id</li><li>ad_revenue_ad_type</li></ul></td></tr><tr><td><Anchor target="_blank" href="/marketers/docs/revenue-etl-reports#impression-level-report">Ad revenue [SDK impression level]</Anchor></td><td><ul><li>engagement_type</li><li>custom_data</li><li>customer_user_id</li><li>ad_revenue_ad_type</li><li>ad_revenue_custom_parameters</li><li>app_version</li><li>sdk_version</li></ul></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        **What you need to do**
      </td>
      <td>
        <ul><li>In <Anchor target="_blank" href="/marketers/docs/data-locker-for-marketers#set-up-data-locker">AppsFlyer Data Locker settings</Anchor>, select the new fields to be added to your reports.<br />**Tip**! If you already receive a field like customer\_user\_id via the default Data Locker settings, in order to populate the fields in ad revenue reports you need to add another new field and save the settings. You can revert the changes after.</li><li>Configure your BI systems to ingest and use the new fields.</li></ul>
      </td>
    </tr>
  </tbody>
</Table>
---
title: "Bulletin: DMA support in Raw data reports"
excerpt: "AppsFlyer is adding new DMA consent fields to raw data tools, including GDPR applicability and Google ad consent indicators."
table_of_contents: false
x-zendesk:
  id: 25485269115793
  url: https://support.appsflyer.com/hc/en-us/articles/25485269115793-Bulletin-DMA-support-in-Raw-data-reports
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 20
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-rona-einat, Marketers, Raw Reports]
  labels: [Marketers, Loc Published]
  promoted: false
  comments_disabled: false
  created_at: '2024-05-29T16:52:12Z'
  edited_at: '2024-09-11T11:28:36Z'
---
The following DMA consent fields are being added to raw data tools in AppsFlyer:

| Field | Details |
| --- | --- |
| **What's new** | The following DMA consent fields are being added to raw data tools in AppsFlyer:<br />- **gdpr_applies:** Indicates whether the user falls under DMA jurisdiction (true) or not (false). <br />- **ad_user_data_enabled**: Indicates whether the user has consented to allow Google to use their user-level data for measurement and personalized advertising (true), or not (false).<br />- **ad_personalization_enabled**: Indicates whether the user has consented to allow Google to use their user-level data for personal ads (true), or not (false).<br />- **raw_consent_data**: Returns a JSON object with the full raw consent data as sent from the advertiser to AppsFlyer. The information sent in this object is then used to populate the three fields above.<br />  - This field is not available in Raw data export and Pull API |
| **Effective date** | - Raw data export page and Pull API - June 3rd, 2024<br />- Push API and Data Locker - Oct 14, 2024 |
| **Where** | - Raw data export page <br />- Pull API<br />- Push API<br />- Datalocker |
| **Who should know** | - Advertisers and agencies using Raw data export page, Push API, Pull API and Datalocker to export raw data (event level) from AppsFlyer. |
| **How does it impact you** | - Configure your scheme and any other processes involved in consuming the data.<br />- Make sure that the new fields do not break your scheme for Push API and Data Locker. |
| **Additional Info** | Please review our [Supporting the Google EU consent policy](/docs/support-google-eu-consent-policy) article. |
---
title: 'Bulletin: DMA support in Raw data reports'
metadata:
  keywords:
    - Marketers
    - Raw Reports
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2024-05-29T16:52:12Z'
  edited_at: '2024-09-11T11:28:36Z'
  id: 25485269115793
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/25485269115793-Bulletin-DMA-support-in-Raw-data-reports
---
| **What's new** | The following DMA consent fields are being added to raw data tools in AppsFlyer:<ul><li>**gdpr\_applies:** Indicates whether the user falls under DMA jurisdiction (true) or not (false).</li><li>**ad\_user\_data\_enabled**: Indicates whether the user has consented to allow Google to use their user-level data for measurement and personalized advertising (true), or not (false).</li><li>**ad\_personalization\_enabled**: Indicates whether the user has consented to allow Google to use their user-level data for personal ads (true), or not (false).</li><li>**raw\_consent\_data**: Returns a JSON object with the full raw consent data as sent from the advertiser to AppsFlyer. The information sent in this object is then used to populate the three fields above.<ul><li>This field is not available in Raw data export and Pull API</li></ul></li></ul> |
| --- | --- |
| **Effective date** | <ul><li>Raw data export page and Pull API - June 3rd, 2024</li><li>Push API and Data Locker - Oct 14, 2024</li></ul> |
| **Where** | <ul><li>Raw data export page</li><li>Pull API</li><li>Push API</li><li>Datalocker</li></ul> |
| **Who should know** | <ul><li>Advertisers and agencies using Raw data export page, Push API, Pull API and Datalocker to export raw data (event level) from AppsFlyer.</li></ul> |
| **How does it impact you** | <ul><li>Configure your scheme and any other processes involved in consuming the data.</li><li>Make sure that the new fields do not break your scheme for Push API and Data Locker.</li></ul> |
| **Additional Info** | Please review our <Anchor target="_blank" href="/marketers/fr/docs/support-google-eu-consent-policy">Supporting the Google EU consent policy</Anchor> article. |
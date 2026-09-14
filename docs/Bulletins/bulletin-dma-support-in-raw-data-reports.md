---
title: "Bulletin: DMA support in Raw data reports"
excerpt: "AppsFlyer is adding new DMA consent fields to raw data tools, including GDPR applicability and Google ad consent indicators."
---
The following DMA consent fields are being added to raw data tools in AppsFlyer:

| Field | Details |
| --- | --- |
| **What's new** | The following DMA consent fields are being added to raw data tools in AppsFlyer:<br>- **gdpr_applies:** Indicates whether the user falls under DMA jurisdiction (true) or not (false). <br>- **ad_user_data_enabled**: Indicates whether the user has consented to allow Google to use their user-level data for measurement and personalized advertising (true), or not (false).<br>- **ad_personalization_enabled**: Indicates whether the user has consented to allow Google to use their user-level data for personal ads (true), or not (false).<br>- **raw_consent_data**: Returns a JSON object with the full raw consent data as sent from the advertiser to AppsFlyer. The information sent in this object is then used to populate the three fields above.<br>  - This field is not available in Raw data export and Pull API |
| **Effective date** | - Raw data export page and Pull API - June 3rd, 2024<br>- Push API and Data Locker - Oct 14, 2024 |
| **Where** | - Raw data export page <br>- Pull API<br>- Push API<br>- Datalocker |
| **Who should know** | - Advertisers and agencies using Raw data export page, Push API, Pull API and Datalocker to export raw data (event level) from AppsFlyer. |
| **How does it impact you** | - Configure your scheme and any other processes involved in consuming the data.<br>- Make sure that the new fields do not break your scheme for Push API and Data Locker. |
| **Additional Info** | Please review our [Supporting the Google EU consent policy](https://support.appsflyer.com/hc/articles/22310731147153-Supporting-the-Google-EU-consent-policy) article. |
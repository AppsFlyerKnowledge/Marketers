---
title: "Bulletin: Get Meta ads attribution in raw data reports with the Meta install referrer"
excerpt: "Learn how the Meta install referrer enables Android campaign attribution in raw data reports and how to configure it."
---
Meta install referrer helps with attribution measurement for your Android ad campaigns on Facebook, Instagram, and Audience Network, where the objective is app installs. This is in addition to the Google Play Install Referrer.

### Overview

| | |
| --- | --- |
| **What's new** | Meta install referrer helps with attribution measurement for your Android ad campaigns on Facebook, Instagram, and Audience Network, where the objective is app installs. This is in addition to the Google Play Install Referrer. |
| **Effective date** | Feb 28, 2024 |
| **Prerequisites** | Make sure of the following:<br>- You have the AppsFlyer SDK version **V6.12.6** or later to ensure the referrer data is passed properly<br>- The [Install Referrer decryption key](https://support.appsflyer.com/hc/articles/207033826-Meta-ads-integration-setup#encrypted-data-from-the-referrer) on the integration page is entered<br>- The versions [described here](https://dev.appsflyer.com/hc/docs/install-android-sdk#prerequisites) are installed on your user devices |
| **Required actions** | [Configure the Meta install referrer support](https://dev.appsflyer.com/hc/docs/install-android-sdk#configure-meta-install-referrer-support) |
| **What must I know?** | Referrer data has priority over data provided via the Meta ads integration and is available in raw data reports. This solution applies to both click-through attribution and view-through attribution. |
| **What's the impact?** | - You may see an increase in Meta-attributed installs in raw data reports<br>- Two new match-type fields are now included in raw data reports, `fb_referrer` and `ig_referrer`:<br>  <br>  <br>  - `fb_referrer` for attribution from the Facebook app<br>  - `ig_referrer` for attribution from the Instagram app<br>  - `fb_referrer` or `ig_referrer`for attribution from the Audience Network. |

<Cards>
  <Card title="Meta install referrer" href="https://support.appsflyer.com/hc/articles/207033826-Meta-ads-integration-setup#userlevel-data">
    Learn more about setting up user-level data and the Meta install referrer integration.
  </Card>
</Cards>
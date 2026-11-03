---
title: >-
  Bulletin: Get Meta ads attribution in raw data reports with the Meta install
  referrer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-02-12T10:47:33Z'
  edited_at: '2024-08-12T11:20:08Z'
  id: 22461635687185
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/22461635687185-Bulletin-Get-Meta-ads-attribution-in-raw-data-reports-with-the-Meta-install-referrer
---
| **What's new** | Meta install referrer helps with attribution measurement for your Android ad campaigns on Facebook, Instagram, and Audience Network, where the objective is app installs. This is in addition to the Google Play Install Referrer. |
| --- | --- |
| **Effective date** | Feb 28, 2024 |
| **Prerequisites** | Make sure of the following:<ul><li>You have the AppsFlyer SDK version **V6.12.6** or later to ensure the referrer data is passed properly</li><li>The <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#data-terenkripsi-dari-google-play-referrer-api-atau-meta-install-referrer">Install Referrer decryption key</Anchor> on the integration page is entered</li><li>The versions <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#prerequisites">described here</Anchor> are installed on your user devices</li></ul> |
| **Required actions** | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#configure-meta-install-referrer-support">Configure the Meta install referrer support</Anchor> |
| **What must I know?** | Referrer data has priority over data provided via the Meta ads integration and is available in raw data reports. This solution applies to both click-through attribution and view-through attribution. |
| **What's the impact?** | <ul><li>You may see an increase in Meta-attributed installs in raw data reports</li><li>Two new match-type fields are now included in raw data reports, `fb_referrer` and `ig_referrer`:<ul><li>`fb_referrer` for attribution from the Facebook app</li><li>`ig_referrer` for attribution from the Instagram app</li><li>`fb_referrer` or `ig_referrer`for attribution from the Audience Network.</li></ul></li></ul> |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/id/docs/meta-ads-integration-setup#userlevel-data">Meta install referrer</Anchor>

<div data-zendesk-anchors="h_01H9FHRVKE88CXGH8G7E26ZXT2=see-also" />

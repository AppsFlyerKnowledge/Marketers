---
title: Discover your campaign link parameters and behavior
metadata:
  keywords:
    - Marketers
    - discover
    - Social-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Social-to-App
  created_at: '2023-07-03T11:56:14Z'
  edited_at: '2025-04-20T10:38:06Z'
  id: 16678138044689
  locale: en-us
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/16678138044689-Discover-your-campaign-link-parameters-and-behavior
---
> **At a glance:** Discover the parameters included in your AppsFlyer campaign links and understand the expected user experience and link behavior.

## About Link Discovery

The Link Discovery feature provides information about your AppsFlyer campaign links, including link parameters and the expected user experience the links are intended to create.

### Benefits

Link Discovery helps advertisers:

* Get a deeper understanding of link meaning and behavior.
* Communicate with the teams responsible for link creation.
* Confirm link details before publishing the link in a campaign
* Troubleshoot unexpected behavior.
* See attribution parameters to know what to look for in the dashboards.

### Information available via Link Discovery

Link Discovery shows the following information about a URL:

* **General details**: Information about what apps the link is for, creation source (for example, OneLink management page or API), the OneLink template the link is based on, and the link expiration date and renewal period.   
  **Note:** If the creation source is 'Unknown', it's likely because it's either a legacy link created via the UI (OneLink Management) or an older link created in other ways (Bulk/API/SDK) pre-source-caller storage.
* **Parameters**: All the different parameters included in the link and their values, displayed by category.   
  **Note:** If there is redirection to a domain not in your <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-domain-redirect-allowlist">redirect allowlist</Anchor>, an alert should appear.
* **Capabilities**: The different capabilities enabled for the link, such as retargeting, deep linking, social media preview, and social media landing page.
* **Redirection**: A summary of how the link is designed to redirect users based on their device, platform, and whether they already have the app installed.

## Using Link Discovery

**To use Link Discovery and get information about a URL**:

1. In AppsFlyer, from the side menu, select **Engage** > **Link Discovery**.
2. Enter your URL and click **Discover.**

## Specifications and limitations

| Specification | Remarks |
| --- | --- |
| Links supported by Link Discovery | <ul><li>Short or long URLs created via AppsFlyer, whether they are single-platform links or multi-platform links created via OneLink.</li><li>Links created in the AppsFlyer UI, and via API, SDK, and bulk creation.</li><li>Links with branded domains.</li></ul> |
| Agencies | Not supported |
| Ad networks | Not supported |
| Impression URLs | Not supported |
| Cross-platform links | Not supported |

<div data-zendesk-anchors="what-is-app-attribution=about-link-discovery h_01HKW0CMGXXFKEY7W0NCN1SH76=about-link-discovery h_01HKW0CMGXEAYPDFMR4QCS9F52=benefits h_01HKW0CMGXHZ2NYP6YVPW6QNX3=information-available-via-link-discovery h_01HKW0CMGXD4Z0J7CCKJFZNVCG=using-link-discovery h_01HKW0CMGXX4VXBHFGG3TGGPRV=specifications-and-limitations" />

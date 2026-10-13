---
title: "Discover your campaign link parameters and behavior"
excerpt: "Learn how to use the Link Discovery feature to analyze your AppsFlyer campaign links, understand their parameters, and verify expected user redirection behavior."
x-zendesk:
  id: 16678138044689
  url: https://support.appsflyer.com/hc/en-us/articles/16678138044689-Discover-your-campaign-link-parameters-and-behavior
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Deep linking using OneLink
  section_id: 6551203111057
  position: 10
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, Social-to-App]
  labels: [Marketers, discover]
  promoted: false
  comments_disabled: true
  created_at: '2023-07-03T11:56:14Z'
  edited_at: '2025-04-20T10:38:06Z'
---
The Link Discovery feature provides information about your AppsFlyer campaign links, including link parameters and the expected user experience the links are intended to create.

### Benefits

Link Discovery helps advertisers:

- Get a deeper understanding of link meaning and behavior.
- Communicate with the teams responsible for link creation.
- Confirm link details before publishing the link in a campaign
- Troubleshoot unexpected behavior.
- See attribution parameters to know what to look for in the dashboards.

### Information available via Link Discovery

Link Discovery shows the following information about a URL:

- **General details**: Information about what apps the link is for, creation source (for example, OneLink management page or API), the OneLink template the link is based on, and the link expiration date and renewal period.

> 📘 Note
>
> If the creation source is 'Unknown', it's likely because it's either a legacy link created via the UI (OneLink Management) or an older link created in other ways (Bulk/API/SDK) pre-source-caller storage.

- **Parameters**: All the different parameters included in the link and their values, displayed by category.

> 📘 Note
>
> If there is redirection to a domain not in your [redirect allowlist](/docs/set-up-your-domain-redirect-allowlist), an alert should appear.

- **Capabilities**: The different capabilities enabled for the link, such as retargeting, deep linking, social media preview, and social media landing page.
- **Redirection**: A summary of how the link is designed to redirect users based on their device, platform, and whether they already have the app installed.

## Using Link Discovery

**To use Link Discovery and get information about a URL**:

1. In AppsFlyer, from the side menu, select **Engage** > **Link Discovery**.
2. Enter your URL and click **Discover.**

## Specifications and limitations

| Specification | Remarks |
| --- | --- |
| Links supported by Link Discovery | - Short or long URLs created via AppsFlyer, whether they are single-platform links or multi-platform links created via OneLink.<br />- Links created in the AppsFlyer UI, and via API, SDK, and bulk creation.<br />- Links with branded domains. |
| Agencies | Not supported |
| Ad networks | Not supported |
| Impression URLs | Not supported |
| Cross-platform links | Not supported |
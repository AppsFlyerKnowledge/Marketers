---
title: "Bulletin: Security enhancement for traffic managed by agencies"
excerpt: "AppsFlyer is enhancing security measures for agencies managing traffic on behalf of advertisers, requiring ad network authorization for traffic to be recorded and measured."
table_of_contents: false
x-zendesk:
  id: 25770412740369
  url: https://support.appsflyer.com/hc/en-us/articles/25770412740369-Bulletin-Security-enhancement-for-traffic-managed-by-agencies
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 18
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials, Agencies, Ad Networks]
  labels: [Advertisers, Agencies, Ad Networks, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2024-06-09T14:08:35Z'
  edited_at: '2024-08-12T13:38:27Z'
---
To protect your data, ensure its security, and reduce fraud, we're enhancing security measures for agencies managing traffic on behalf of advertisers that are running campaigns on ad networks. As of the effective date, only traffic from agencies authorized by the ad networks will be recorded and measured in AppsFlyer. This means unauthorized agencies won't be able to configure the integration (the partner configuration window will be grayed out), and unauthorized traffic from these agencies will result in a 403 (Forbidden) response from AppsFlyer. After the agencies are added to the list, the approval applies account-wide allowing them to run campaigns with all apps on your network.

> 📘 Note
>
> - Applies also to empty af_prt parameters on attribution links
> - Doesn't apply to agencies working with [SRNs](/docs/self-reporting-networks-srns)

| | |
| --- | --- |
| **Effective date** | July 31, 2024 |
| **Where** | - **Agency:** Integration page<br />- **Ad network:** Security center |
| **What you should know** | - **Agency:** Reach out to the partner and make sure your agency ID ( [the af_prt name](/docs/about-agency-accounts#af_prt-parameter)) is added to their list of authorized agencies.<br />- **Partner:** Make sure to add all agency IDs (af_prt) in the [new authorized agencies section](/docs/set-up-your-list-of-authorized-agencies). |
| **Implications** | Starting from the specified date, agencies not on the ad network's approved list won't have their traffic recorded and measured, nor will they be able to access the integration page for all apps running campaigns on the ad network. |
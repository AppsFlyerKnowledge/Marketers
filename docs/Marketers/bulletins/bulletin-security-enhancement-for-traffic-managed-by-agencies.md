---
title: "Bulletin: Security enhancement for traffic managed by agencies"
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
| **What's new?** | To protect your data, ensure its security, and reduce fraud, we're enhancing security measures for agencies managing traffic on behalf of advertisers that are running campaigns on ad networks. As of the effective date, only traffic from agencies authorized by the ad networks will be recorded and measured in AppsFlyer. This means unauthorized agencies won't be able to configure the integration (the partner configuration window will be grayed out), and unauthorized traffic from these agencies will result in a 403 (Forbidden) response from AppsFlyer. After the agencies are added to the list, the approval applies account-wide allowing them to run campaigns with all apps on your network.<br /><br />**Note:**<ul><li>Applies also to empty af\_prt parameters on attribution links</li><li>Doesn't apply to agencies working with [SRNs](/docs/self-reporting-networks-srns)</li></ul> |
| --- | --- |
| **Effective date** | July 31, 2024 |
| **Where** | <ul><li>**Agency:** Integration page</li><li>**Ad network:** Security center</li></ul> |
| **What you should know** | <ul><li>**Agency:** Reach out to the partner and make sure your agency ID ([the af\_prt name](/docs/about-agency-accounts#af_prt-parameter)) is added to their list of authorized agencies.</li><li>**Partner:** Make sure to add all agency IDs (af\_prt) in the [new authorized agencies section](/docs/set-up-your-list-of-authorized-agencies).</li></ul> |
| **Implications** | Starting from the specified date, agencies not on the ad network's approved list won't have their traffic recorded and measured, nor will they be able to access the integration page for all apps running campaigns on the ad network. |
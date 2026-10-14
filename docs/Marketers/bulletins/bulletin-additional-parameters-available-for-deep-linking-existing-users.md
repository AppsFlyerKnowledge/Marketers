---
title: "Bulletin: Additional parameters available for deep linking existing users"
excerpt: "Returning additional parameters for deep linking existing users via UDL method."
table_of_contents: false
x-zendesk:
  id: 5733303620113
  url: https://support.appsflyer.com/hc/en-us/articles/5733303620113-Bulletin-Additional-parameters-available-for-deep-linking-existing-users
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 49
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, OneLink]
  labels: [SDK, deep link, deep linking, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-04-27T09:49:22Z'
  edited_at: '2025-11-09T08:44:17Z'
---
| **What's new** | AppsFlyer SDK V6.6+ allows UDL method to return additional parameters for deep linking existing users (with the app installed). |
| --- | --- |
| **Effective date** | April 27, 2022 |
| **Where** | UDL method for deep linking existing users with the app installed |
| **What** | **Before the change:** UDL method only returned `deep_link_value` and `deep_link_sub1-10` parameters for deep linking existing users.<br /><br />**After the change:** UDL method returns all the parameters that figure in the link parameter, including:<ul><li>`c`</li><li>`pid`</li><li>`path`</li><li>`scheme`</li><li>`host`</li><li>`af_c_id`</li><li>`af_adset`</li><li>`af_adset_id`</li><li>`af_ad`</li><li>`af_ad_id`</li><li>`af_ad_type`</li><li>`af_channel`</li><li>`af_dp`</li><li>`esp_name`</li><li>`link`</li></ul> |
| **What you must know** | **Best practice**: Even though these parameters are available for deep linking existing users, we recommend you create new links using only `deep_link_value` and `deep_link_sub1-10` parameters, as documented in our [deep linking guide](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link).<ul><li>This change is only intended for customers with existing links using legacy methods for deep linking. These customers can now implement the UDL method for deep linking and use these additional parameters to deep link existing users, while continuing to use the same links. New links don't have to be created.</li><li>AppsFlyer SDK V6.6+ required</li></ul> |
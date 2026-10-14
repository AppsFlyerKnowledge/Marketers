---
title: "Postback troubleshooting for ad networks"
excerpt: "If you have problems receiving postbacks, review the following solutions."
table_of_contents: false
x-zendesk:
  id: 7466104144145
  url: https://support.appsflyer.com/hc/en-us/articles/7466104144145-Postback-troubleshooting-for-ad-networks
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Receive data
  section_id: 6551235995281
  position: 4
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Mobile Attribution, Ad Networks]
  labels: [Postback, Ad Networks, Partners, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2022-07-07T15:16:00Z'
  edited_at: '2026-01-13T10:25:26Z'
---
| **Problem** | **Solution** |
| --- | --- |
| <span id="i-dont-see-my-advertisers-app-under-my-apps"></span>I don't see my Advertiser's app under **My Apps** | <ul><li>If the Advertiser's app doesn't appear under **My Apps** (from the top menu), reach out to the Advertiser and ask them to [provide you with relevant permissions](/docs/set-up-an-integrated-partner#ad-network-permissions).</li><li>Verify that the [**Activate partner** toggle is enabled](/docs/partner-activation-deactivation#activate-a-partner-integration).</li></ul>**Note:** If you're running a test with a production application, make sure to register your device according to the instructions [here](/docs/registering-test-devices). |
| <span id="im-not-receiving-install-postbacks"></span>I'm not receiving install postbacks | <ul><li>If there were no app installs, you won't see install postbacks.  Check to see if your app has install attributions: go to **Settings** > **My Apps** > [Choose the app] > [**Overview**](/docs/integrated-partners-dashboard).</li></ul> |
| <span id="im-not-receiving-inapp-event-postbacks"></span>I'm not receiving in-app event postbacks | <ul><li>Verify that the events are [mapped correctly](/docs/in-app-event-postback-configuration) on the integration tab, under the **In-app event postbacks** section</li></ul>**Note:** Event names are case sensitive and should be mapped using the same name as delivered via server-to-server/SDK. |
| <span id="im-not-receiving-both-install-and-inapp-event-postbacks"></span>I'm not receiving both install and in-app event postbacks | <ul><li>If there were no app installs, you won't see install postbacks. Check to see if your app has install attributions. Go to **Settings** > **My Apps** > [Choose the app] > [**Overview**](/docs/integrated-partners-dashboard).</li><li>Check Install/In-app event postback reports and review the following fields:<ul><li>**Postback URL**: The actual delivered postback. Check that the template doesn't miss any crucial values.</li><li>**Postback HTTP Response Code**: The response code that AppsFlyer receives from the partner's server. Check the HTTP response code. If it's not 2XX, check your internal server setup.</li><li>**Original URL**: The click/impression URL that AppsFlyer receives for the corresponding install/event. Check the completeness of the attribution link. Data not provided in the link can't be returned via a postback.</li></ul></li><li>Check **Advanced Privacy** settings: when enabled, [user-level data for non-consenting users running iOS 14.5+](/docs/advanced-privacy-guide-postback-macros-for-ad-networks) is NOT available on postbacks.<ul><li>If the Advanced Privacy postback is not defined in your integration, but the advertiser decides to use Advanced Privacy, no postbacks are delivered for non-consenting iOS users.</li></ul></li><li>Check the [Postback Window](/docs/in-app-event-postback-configuration#in-app-event-postback-window) definition. Postbacks are not sent after the defined time period.</li><li>Check if the [conditional postback](/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks) is defined.</li><li>Check if the [traffic is blocked](/docs/rejected-attribution-postbacks-to-integrated-partners): download and review the **Blocked install postbacks** report.</li></ul> |

> 📘 **See also**
>
> * [Postback troubleshooting for advertisers](/docs/postback-troubleshooting-for-advertisers)
> * [In-app event postback configuration](/docs/in-app-event-postback-configuration)

<div data-zendesk-anchors="h_01HDP4JFM42RZNBGM9TTD5SRP0=see-also" />

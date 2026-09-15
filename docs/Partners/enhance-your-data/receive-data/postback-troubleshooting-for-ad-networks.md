---
title: "Postback troubleshooting for ad networks"
excerpt: "A troubleshooting guide for ad networks to resolve issues with receiving install and in-app event postbacks."
---
**At a glance:** If you have problems receiving postbacks, review the following solutions.

| **Problem** | **Solution** |
| --- | --- |
| I don't see my Advertiser's app under **My Apps** | - If the Advertiser's app doesn't appear under **My Apps** (from the top menu), reach out to the Advertiser and ask them to [provide you with relevant permissions](/docs/set-up-an-integrated-partner#ad-network-permissions).<br />- Verify that the [**Activate partner** toggle is enabled](/docs/partner-activation-deactivation#activating-a-partner).<br />**Note:** If you're running a test with a production application, make sure to register your device according to the instructions [here](/docs/registering-test-devices). |
| I'm not receiving install postbacks | - If there were no app installs, you won't see install postbacks.  Check to see if your app has install attributions: go to **Settings** \> **My Apps** \> [Choose the app] > [**Overview**](/docs/integrated-partners-dashboard). |
| I'm not receiving in-app event postbacks | - Verify that the events are [mapped correctly](/docs/in-app-event-postback-configuration) on the integration tab, under the **In-app event postbacks** section<br />**Note:** Event names are case sensitive and should be mapped using the same name as delivered via server-to-server/SDK. |
| I'm not receiving both install and in-app event postbacks | - If there were no app installs, you won't see install postbacks. Check to see if your app has install attributions. Go to **Settings** \> **My Apps** \> [Choose the app] > [**Overview**](/docs/integrated-partners-dashboard). <br />- Check Install/In-app event postback reports and review the following fields:<br />  - **Postback URL**: The actual delivered postback. Check that the template doesn't miss any crucial values. <br />  - **Postback HTTP Response Code**: The response code that AppsFlyer receives from the partner's server. Check the HTTP response code. If it's not 2XX, check your internal server setup. <br />  - **Original URL**: The click/impression URL that AppsFlyer receives for the corresponding install/event. Check the completeness of the attribution link. Data not provided in the link can't be returned via a postback.<br />- Check **Advanced Privacy** settings: when enabled, [user-level data for non-consenting users running iOS 14.5+](/docs/advanced-privacy-guide-postback-macros-for-ad-networks) is NOT available on postbacks.<br />  - If the Advanced Privacy postback is not defined in your integration, but the advertiser decides to use Advanced Privacy, no postbacks are delivered for non-consenting iOS users.<br />- Check the [Postback Window](/docs/in-app-event-postback-configuration#inapp-event-postback-window) definition. Postbacks are not sent after the defined time period.<br />- Check if the [conditional postback](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) is defined.<br />- Check if the [traffic is blocked](/docs/rejected-attribution-postbacks-to-integrated-partners): download and review the **Blocked install postbacks** report. |

<Cards>
  <Card title="Postback troubleshooting for advertisers" href="/docs/postback-troubleshooting-for-advertisers">
    Troubleshooting steps for advertisers experiencing postback delivery issues.
  </Card>
  <Card title="In-app event postback configuration" href="/docs/in-app-event-postback-configuration">
    Learn how to configure postbacks for in-app events.
  </Card>
</Cards>
---
title: X Ads (formerly Twitter Ads) FAQ and discrepancies
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:34:59Z'
  edited_at: '2026-11-02T07:48:34Z'
  id: 4410464352017
  locale: en-us
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4410464352017-X-Ads-formerly-Twitter-Ads-FAQ-and-discrepancies
---
> **At a glance:** Resolve X Ads FAQs and understand discrepancies.

## X Ads FAQ and discrepancies

<div id="who-can-perform-the-twitter-setup-on-appsflyer" />

<Accordion title="Who can perform the setup on AppsFlyer?">

The user who is authorizing the integration between AppsFlyer and X Ads must have X Ads Account Administrator access.

</Accordion>

<div id="what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer" />

<Accordion title="What happens if no X Ads account is selected for attributing on AppsFlyer?">

All attributions are for campaigns on the selected account. If no account is selected, no in-app events or attributions are sent to X Ads, even if the in-app event mapping is still visible on the X Ads configuration window.

</Accordion>

<div id="do-the-account-owner-and-the-team-members-see-the-same-twitter-data" />

<Accordion title="Do both the account owner and team members see the same X Ads data?">

No. The account owner sees all of the connected X Ads accounts. Team members only see their connected X Ads accounts.

</Accordion>

<div id="how-do-i-disconnect-twitter-from-appsflyer" />

<Accordion title="How do I disconnect AppsFlyer from X Ads?">

You can disconnect AppsFlyer from your X Ads account. The following instructions assume that you are logged into your X Ads account using a desktop or laptop browser:

1. Sign in to X Ads.
2. On the left menu, click **More** > **Settings and Privacy**.
3. Go to **Security and account access** > **Apps and sessions** > **Connected apps**.
4. Click AppsFlyer.
5. Click **Revoke Access**.

You can now go back to your AppsFlyer account and <Anchor target="_blank" href="/marketers/docs/x-ads-formerly-twitter-ads-integration-setup">connect a different X Ads account</Anchor> if you want.

</Accordion>

<div id="is-it-possible-to-attribute-installs-to-multiple-twitter-accounts" />

<Accordion title="Is it possible to attribute installs to multiple X Ads accounts?">

Yes, but it requires some actions in X Ads. But first, some background is required:

You can connect **only one handle** (also known as an X user) to your AppsFlyer account. When you connect this handle, your X Ads account appears in the X Ads configuration in AppsFlyer dashboard.

If one of your team members also has an X Ads account, this means they have a different handle than yours and cannot connect their handle to AppsFlyer. This is because **your handle is the one that is already connected with the AppsFlyer account**. In order for their X Ads account to also appear in AppsFlyer, they need to **give your handle access as account administrator to their X Ads account**.

Say your team member is Jenny and her handle is @jenny. Your handle is @nivi and is the handle that is connected to AppsFlyer. In order for her X Ads account to appear in the AppsFlyer account, **she needs to give your handle access as account administrator to her X Ads account**. Jenny needs to give access to Nivi to her X Ads account and not the other way around. When she does so, AppsFlyer looks at Nivi's handle, and sees all the ad accounts that it is associated with, Jenny's included.

**To connect Jenny's X Ads account to AppsFlyer:**

1. Jenny logs in to <Anchor target="_blank" href="https://ads.x.com/">X Ads</Anchor> with the @jenny handle.
2. In her X Ads account, Jenny opens the account access settings and gives @nivi access as **Account administrator**. See the <Anchor target="_blank" href="https://help.x.com/en/business-and-advertising/multi-user-login-faq">Multi-user login FAQ</Anchor> in the X Help Center.
3. Jenny logs in to AppsFlyer, goes to **Collaborate** > **Partner Integrations** > **Active integrations**, searches for **X Ads**, and selects it.
4. Her X Ads account now appears in the integration settings, and she can configure the integration. Jenny sees only her X Ads account. The account admin sees all connected X Ads accounts, including hers.

</Accordion>

<div id="any-special-instructions-for-agencies" />

<Accordion title="Any special instructions for agencies?">

Yes.  
When an agency creates a new X Ads campaign, the campaign name must start with the agency name and an underscore (Example: "AgencyName\_Campaign1").

> 📘 **Note**
>
> To establish the connection between AppsFlyer and X Ads, the advertiser MUST configure X Ads permissions allowing agencies to run X Ads traffic.

For more details go <Anchor target="_blank" href="/partners/docs/about-agency-accounts#srn-configurations">here</Anchor>.

</Accordion>

<div id="do-you-make-twitters-raw-data-available-to-agencies" />

<Accordion title="Is the X Ads raw data available to agencies?">

We don't provide X Ads raw data to agencies because X Ads' terms of service regard agencies as third parties.

</Accordion>

<div id="im-clicking-save-close-but-twitters-configuration-is-not-saved-help" />

<Accordion title="I'm clicking save & close but the X Ads configuration is not saved! help!">

If your app was subscribed to another attribution provider in the past, which was used to attribute X Ads installs, the following errors below when configuring X Ads on AppsFlyer's dashboard:

**Error: The app is associated with a different attribution provider. Please associate it with AppsFlyer.**

Alternatively, the following error may also appear:  

[![](https://support.appsflyer.com/hc/article_attachments/360001502209/X%20Ads_error_2.png)](https://support.appsflyer.com/hc/article_attachments/360001502209/X%20Ads_error_2.png)

**Error: Error has occurred while saving X Ads configuration. Some accounts failed to update: XX Multiple provider ids to same (appid, conversionType) for event appid2872.**

If the account selection does not save, this may be because the X Ads account in question was previously associated with a different provider at X Ads. To resolve this:

* Contact X Ads to remove the other provider from your end
* Select the Active Account name
* Click **Save and Close**.
* If this still doesn't solve the problem you will have to contact your previous measurement provider and ask to remove the past X Ads tags associated with your account.

</Accordion>

<div id="how-can-i-set-up-retargeting-campaigns-with-twitter" />

<Accordion title="How can I set up retargeting campaigns with X Ads?">

For details on how to configure an X Ads Retargeting Campaign, click here.

</Accordion>

<div id="does-retargeting-affect-inapp-events-sending-to-twitter" />

<Accordion title="Does retargeting affect in-app events sent to X Ads?">

Yes. If retargeting is turned on, AppsFlyer doesn't send the af\_app\_opened event postbacks to X Ads, as per X Ads' request.  
Note that even if the X Ads setup window allows this selection, the af\_app\_opened postbacks are not sent with retargeting.

</Accordion>

<div id="how-can-i-stop-measuring-twitter-attributions" />

<Accordion title="How can I stop measuring X Ads attributions?">

To deactivate the integration with X Ads, uncheck all accounts and click **Save & Close**.

</Accordion>

<div id="can-an-agency-measure-twitter-attributions-for-advertisers" />

<Accordion title="Can an agency measure X Ads attributions for advertisers?">

Yes!  
To establish the connection between AppsFlyer and X Ads, the advertiser MUST select an active account in the X Ads partner page on AppsFlyer's dashboard, so at least one X Ads account is checked.  
Afterwards, the agency needs to connect its X Ads account directly from its own agency dashboard.

</Accordion>

<div id="can-an-agency-configure-inapp-events-for-twitter" />

<Accordion title="Can an agency configure in-app events for X Ads?">

Agencies cannot configure in-app events for X Ads. Similar to Meta ads, these must be configured by the Advertiser.

</Accordion>

<div id="for-how-long-do-you-keep-twitter-s-userlevel-data" />

<Accordion title="For how long do you keep X Ads user-level data?">

X Ads requires attribution providers to delete their user-level data 3 months after the install. This means that the events performed by these users 3 months after they install the app are counted as organic.

Past aggregate data remains the same.

</Accordion>

<div id="why-do-i-see-duplicated-cost-data" />

<Accordion title="Why do I see duplicated cost data?">

When you set up a campaign in X Ads, you can add multiple apps to the campaign. When X Ads reports the cost, the total campaign cost data displays under each app in AppsFlyer, and is not divided per app.

For example, if you run one campaign that costs $1,000 for both an Android and iOS app, then a cost of $1,000 displays in the AppsFlyer dashboard under both the Android and iOS apps. The cost is not split, for example, to $500 each.

To avoid cost duplication, it is recommended that you define only one app per line item/campaign.

</Accordion>

<div id="im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message" />

<Accordion title="I'm trying to link my X Ads account with AppsFlyer, but I get an error message">

Your X Ads account needs to be an active Ad Account to receive attribution data from AppsFlyer.

**To solve this issue:**

1. Log out of X Ads.
2. In AppsFlyer, from the side menu, select **Collaborate > Partner Integrations >** **Active Integrations.**
3. Search for X Ads and select it. The partner setup window opens.
4. In the **Integration** tab, click on **Activate partner**.
5. Click on **Login with X Ads**,  
   a X Ads login window opens.
6. Sign in with your X Ads Account.

</Accordion>

## Discrepancies between X Ads and AppsFlyer

Although we work closely with X Ads, discrepancies might appear between the X Ads dashboard and the AppsFlyer dashboard/reports.

These are the common reasons for such discrepancies that advertisers should be aware of:

| Cause | X Ads | AppsFlyer |
| --- | --- | --- |
| **Attribution window** | X Ads allows its users to configure the attribution window and supports both click-through and view-through attributions. By default - 14 days click-through and 1 day view-through. | If you have not configured the AppsFlyer attribution lookback window for X Ads with the same values as in X Ads, discrepancies may occur. |
| **Multi-channel source attribution** | X Ads attribution works as specified above regardless of other sources. | AppsFlyer uses last click attribution (more information about AppsFlyer attribution available <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model">here</Anchor>). |
| **Timezone differences** | X Ads timezone is defined by the advertiser's app configured timezone. | AppsFlyer's default timezone is UTC±00:00, but can be set to any timezone by the advertiser. |
| **Install time differences** | X Ads shows installs based on the click time (referred to as "engagement time"). | AppsFlyer displays the time of the first app open. |
| **Attribution touch type** | X Ads attribution is based on their own clicks and impressions. | AppsFlyer gives priority to click-through attribution over view-through attribution. If X Ads counts an impression and AppsFlyer is aware of an additional click within the click-through attribution window, the click from another source is attributed on AppsFlyer's dashboard. On X Ads, the impression is attributed and is presented on their dashboard. |
| **X Ads data sharing settings** | X Ads allows its users to NOT <Anchor target="_blank" href="https://twitter.com/settings/account/personalization">share their personal data with third parties</Anchor>. This data includes ads they interact with.<br /><br />The stats on X Ads dashboard reflect all engagements, including the users who have opted out from sharing the data. | AppsFlyer shows the aggregate data of these X Ads users, but does not report their user-level raw data (more <Anchor target="_blank" href="/marketers/docs/x-ads-formerly-twitter-ads-setup-guide-overview#x-ads-user-privacy">details</Anchor>). |
| **X Ads re-engagement logic** | X Ads counts unique users. If a user re-engages more than once as a result of the same campaign, X Ads shows these engagements as one conversion. | AppsFlyer counts each re-engagement instance, and therefore, in a similar case, shows these engagements as multiple conversions. |

> 📘 **Note**
>
> As a result of <Anchor target="_blank" href="/marketers/docs/implement-validation-rules-to-prevent-fraud">AppsFlyer's Validation Rules</Anchor>, results may differ in the dashboards as some installs are shown in X Ads and are not shown in the AppsFlyer dashboard.

<div data-zendesk-anchors="twitter-ads-faq-and-discrepancies=x-ads-faq-and-discrepancies h_01HE7S15F9YR28FBA1TYCE3N0X=x-ads-faq-and-discrepancies h_01HE7S15F9NSQJSP268B0WF0JP=who-can-perform-the-twitter-setup-on-appsflyer h_01HE7S15F9PFZ8CATJC5YWC6QP=what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer h_01HE7S15F989Y94YFJ7TGK7QN5=do-the-account-owner-and-the-team-members-see-the-same-twitter-data h_01HE7S15F9GNWTK2N50GAHN52Q=how-do-i-disconnect-twitter-from-appsflyer h_01HE7S15F9CE4F29R97EVCG791=is-it-possible-to-attribute-installs-to-multiple-twitter-accounts h_01HE7S15F9G4M44CB2Q1KQMJPJ=any-special-instructions-for-agencies h_01HE7S15F9VG8XMJE7YSNN245P=note h_01HE7S15F9A7BBAW8BNN6H4AKQ=do-you-make-twitters-raw-data-available-to-agencies h_01HE7S15F9MM26SGKMAPGDH9F8=im-clicking-save-close-but-twitters-configuration-is-not-saved-help h_01HE7S15F923NKTTCS3Z1C40B5=how-can-i-set-up-retargeting-campaigns-with-twitter h_01HE7S15F931EWS48QVCQYPBCH=does-retargeting-affect-inapp-events-sending-to-twitter h_01HE7S15F98VN1TS99751S34C5=how-can-i-stop-measuring-twitter-attributions h_01HE7S15F9MEKBKAQ3NA76TFKY=can-an-agency-measure-twitter-attributions-for-advertisers h_01HE7S15F921V3T885F39VSPCQ=can-an-agency-configure-inapp-events-for-twitter for-how-long-do-you-keep-twitter%E2%80%99s-userlevel-data=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F90RXSWJ7HV3GSJB65=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F9B39KV628NSD29P6P=why-do-i-see-duplicated-cost-data h_01HE7S15F9N3CCJEMAD2QB38F9=im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message discrepancies-between-twitter-and-appsflyer=discrepancies-between-x-ads-and-appsflyer h_01HE7S15F9YWCY883DP9TEGQXK=discrepancies-between-x-ads-and-appsflyer h_01HE7S15FAPS2696J3KQG3P3ME=note-1" />

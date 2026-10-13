---
title: "X Ads (formerly Twitter Ads) FAQ and discrepancies"
excerpt: "Resolve frequently asked questions and understand attribution discrepancies between X Ads and AppsFlyer."
---
**At a glance:** Resolve X Ads FAQs and understand discrepancies.

## X Ads FAQ and discrepancies

### Who can perform the setup on AppsFlyer?

The user who is authorizing the integration between AppsFlyer and X Ads must have X Ads Account Administrator access.

### What happens if no X Ads account is selected for attributing on AppsFlyer?

All attributions are for campaigns on the selected account. If no account is selected, no in-app events or attributions are sent to X Ads, even if the in-app event mapping is still visible on the X Ads configuration window.

### Do both the account owner and team members see the same X Ads data?

No. The account owner sees all of the connected X Ads accounts. Team members only see their connected X Ads accounts.

### How do I disconnect AppsFlyer from X Ads?

You can disconnect AppsFlyer from your X Ads account. The following instructions assume that you are logged into your X Ads account using a desktop or laptop browser:

1. Sign in to X Ads.
2. On the left menu, click **More** > **Settings and Privacy**.
3. Go to **Security and account access** > **Apps and sessions** > **Connected apps**.
4. Click AppsFlyer.
5. Click **Revoke Access**.

You can now go back to your AppsFlyer account and [connect a different X Ads account](/docs/x-ads-formerly-twitter-ads-integration-setup%20Ads-Ads-setup-guide-integration-and-setup) if you want.

### Is it possible to attribute installs to multiple X Ads accounts?

Yes, but it requires some actions on X Ads. But first, some background is required:

You can connect **only one handle** (also known as an X user) to your AppsFlyer account. When you connect this handle, your X Ads Account appears in the X Ads configuration in AppsFlyer dashboard.

If one of your team members also has an X Ads Account, this means they have a different handle than yours and cannot connect their handle to AppsFlyer. This is because **your handle is the one that is already connected with the AppsFlyer account**. In order for their X Ads Account to also appear in AppsFlyer, they need to **give your handle access as account administrator to their X Ads Account**.

Say your team member is Jenny and her handle is @jenny. Your handle is @nivi and is the handle that is connected to AppsFlyer. In order for her X Ads Account to appear in the AppsFlyer account, **she needs to give your handle access as account administrator to her X Ads Account**. Jenny needs to give access to Nivi to her X Ads Account and not that other way around. When she does so, AppsFlyer looks at Nivi's handle, and sees all the ad accounts that it is associated with, Jenny's included.

1. Jenny signs into [ads.twitter.com](http://ads.twitter.com/)
2. She clicks on **Account** and then chooses **Edit access to account**

   ![twitter_assign_account2.PNG](https://files.readme.io/cd2aa0b7a700fd0eee8754ac850adb99cc22b1c42d0d94f18d31ca71901ff31f-50903273809937.png)
3. Jenny then gives @nivi access to her X Ads Account as or Account administrator  
     
   [![twitter_edit_access_to_account.png](https://files.readme.io/93cee24a4b77c48d47444c5992cffb40f082beda46bdb96e9f22eef5ae8d9269-4416810307601.png)](https://support.appsflyer.com/hc/article_attachments/360002514658/twitter_edit_access_to_account.png)
4. Jenny logs into the AppsFlyer account and goes to Active Integrations >> X Ads option
5. At this stage, she can see her X Ads Account also listed.
6. She can now see her X Ads account and configure the integration. The account admin can see all connected X Ads accounts.

   Jenny's view:

   ![jennys_ads_account.png](https://files.readme.io/73e3ca9be6090bfd47acb675e4faa634721d9aa75f5ebb8cf736fd56dd9e336b-50903273813137.png)

   Account admin view:

   ![jennys_ads_account__1_.png](https://files.readme.io/d744c0e2de60011a0395a407607ec90f4fac04f76787b430cf1a74eda2342e66-50903273813649.png)

### Any special instructions for agencies?

Yes.  
When an agency creates a new X Ads campaign, the campaign name must start with the agency name and an underscore (Example: "AgencyName\_Campaign1").

> 📘 **Note**
>
> To establish the connection between AppsFlyer and X Ads, the advertiser MUST configure X Ads permissions allowing agencies to run X Ads traffic.

For more details go [here](/docs/about-agency-accounts#srn-configurations).

### Is the X Ads raw data available to agencies?

We don't provide X Ads raw data to agencies because X Ads' terms of service regard agencies as third parties.

### I'm clicking save & close but the X Ads configuration is not saved! help!

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

### How can I set up retargeting campaigns with X Ads?

For details on how to configure an X Ads Retargeting Campaign, click here.

### Does retargeting affect in-app events sent to X Ads?

Yes. If retargeting is turned on, AppsFlyer doesn't send the af\_app\_opened event postbacks to X Ads, as per X Ads' request.  
Note that even if the X Ads setup window allows this selection, the af\_app\_opened postbacks are not sent with retargeting.

### How can I stop measuring X Ads attributions?

To deactivate the integration with X Ads, uncheck all accounts and click **Save & Close**.

### Can an agency measure X Ads attributions for advertisers?

Yes!  
To establish the connection between AppsFlyer and X Ads, the advertiser MUST select an active account in the X Ads partner page on AppsFlyer's dashboard, so at least one X Ads account is checked.  
Afterwards, the agency needs to connect its X Ads account directly from its own agency dashboard.

### Can an agency configure in-app events for X Ads?

Agencies cannot configure in-app events for X Ads. Similar to Meta ads, these must be configured by the Advertiser.

### For how long do you keep X Ads user-level data?

X Ads requires attribution providers to delete their user-level data 3 months after the install. This means that the events performed by these users 3 months after they install the app are counted as organic.

Past aggregate data remains the same.

### Why do I see duplicated cost data?

When you set up a campaign in X Ads, you can add multiple apps to the campaign. When X Ads reports the cost, the total campaign cost data displays under each app in AppsFlyer, and is not divided per app.

For example, if you run one campaign that costs $1,000 for both an Android and iOS app, then a cost of $1,000 displays in the AppsFlyer dashboard under both the Android and iOS apps. The cost is not split, for example, to $500 each.

To avoid cost duplication, it is recommended that you define only one app per line item/campaign.

### I'm trying to link my X Ads account with AppsFlyer, but I get an error message

Your X Ads account needs to be an active Ad Account to receive attribution data from AppsFlyer.

**To solve this issue:**

1. Log out of X Ads.
2. In AppsFlyer, from the side menu, select **Collaborate > Partner Integrations >** **Active Integrations.**
3. Search for X Ads and select it. The partner setup window opens.
4. In the **Integration** tab, click on **Activate partner**.
5. Click on **Login with X Ads**,  
   a X Ads login window opens.
6. Sign in with your X Ads Account.

## Discrepancies between X Ads and AppsFlyer

Although we work closely with X Ads, discrepancies might appear between the X Ads dashboard and the AppsFlyer dashboard/reports.

These are the common reasons for such discrepancies that advertisers should be aware of:

| Cause | X Ads | AppsFlyer |
| --- | --- | --- |
| **Attribution window** | X Ads allows its users to configure the attribution window and supports both click-through and view-through attributions. By default - 14 days click-through and 1 day view-through. | If you have not configured the AppsFlyer attribution lookback window for X Ads with the same values as in X Ads, discrepancies may occur. |
| **Multi-channel source attribution** | X Ads attribution works as specified above regardless of other sources. | AppsFlyer uses last click attribution (more information about AppsFlyer attribution available [here](/docs/appsflyer-attribution-model "AppsFlyer Attribution Model")). |
| **Timezone differences** | X Ads timezone is defined by the advertiser's app configured timezone. | AppsFlyer's default timezone is UTC±00:00, but can be set to any timezone by the advertiser. |
| **Install time differences** | X Ads shows installs based on the click time (referred to as "engagement time"). | AppsFlyer displays the time of the first app open. |
| **Attribution touch type** | X Ads attribution is based on their own clicks and impressions. | AppsFlyer gives priority to click-through attribution over view-through attribution. If X Ads counts an impression and AppsFlyer is aware of an additional click within the click-through attribution window, the click from another source is attributed on AppsFlyer's dashboard. On X Ads, the impression is attributed and is presented on their dashboard. |
| **X Ads data sharing settings** | X Ads allows its users to NOT [share their personal data with third parties](https://twitter.com/settings/account/personalization). This data includes ads they interact with.<br /><br />The stats on X Ads dashboard reflect all engagements, including the users who have opted out from sharing the data. | AppsFlyer shows the aggregate data of these X Ads users, but does not report their user-level raw data (more [details](/docs/x-ads-formerly-twitter-ads-setup-guide-overview#twitter-user-privacy)). |
| **X Ads re-engagement logic** | X Ads counts unique users. If a user re-engages more than once as a result of the same campaign, X Ads shows these engagements as one conversion. | AppsFlyer counts each re-engagement instance, and therefore, in a similar case, shows these engagements as multiple conversions. |

> 📘 **Note**
>
> As a result of [AppsFlyer's Validation Rules](/docs/implement-validation-rules-to-prevent-fraud), results may differ in the dashboards as some installs are shown in X Ads and are not shown in the AppsFlyer dashboard.
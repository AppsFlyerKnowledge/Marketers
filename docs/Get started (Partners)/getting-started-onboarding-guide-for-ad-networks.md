---
title: "Getting started—onboarding guide for ad networks"
excerpt: "Complete integration with AppsFlyer by setting up and testing your attribution link and postback integrations."
---
At a glance: Complete integration with AppsFlyer by setting up and testing your attribution link and postback integrations. Understand the steps, timelines, and dependencies of the process.

![AdNetworks_-_Onboarding__2_.png](https://files.readme.io/33217648d1f5c1ef327871b9b2ccfaadb6b9ae34fb2645ffcfbe187c378dd054-30603793569297.png)

## What is AppsFlyer?

AppsFlyer, a leader in mobile attribution, welcomes you as our ad network integrated partner. This article is for ad networks that have completed AppsFlyer partner registration. If you want to register as a partner, you must ask an [AppsFlyer customer (advertiser) to invite you to do so.](https://support.appsflyer.com/hc/articles/4410395957521#invite-new-partners-to-appsflyer)

## Ad network onboarding

The steps required to integrate and the estimated time to complete them are listed in the **Onboarding steps** section of this article.

Integration means that:

- AppsFlyer records your engagements (clicks and impressions). The engagements are attributed according to the [AppsFlyer attribution model](https://support.appsflyer.com/hc/articles/207447053).
- Postbacks of the format required by you are sent to your endpoints.
- You can access AppsFlyer features like click signing, Protect360, Data Locker, and so on.

### If you need help

- Look at the partner [FAQ](/docs/integrated-partners-faq)
- Consult the [Integration change requests](https://support.appsflyer.com/hc/articles/360017189177) article

Consider:

- Time estimates in this article are based on our experience working with ad networks. Each integration is slightly different, so the actual times can vary.
- AppsFlyer supports many [performance platforms](https://support.appsflyer.com/hc/sections/6551055575185). If you use one of the platforms on the list, you must review platform-specific instructions before integrating.

## Onboarding steps

**To integrate with AppsFlyer**:

1. [Complete part 1—integration and testing.](https://support.appsflyer.com/hc/articles/360001300998#part-1-integration-and-testing)
2. [Complete part 2—testing with advertiser apps.](https://support.appsflyer.com/hc/articles/360001300998#part-2-test-using-advertiser-apps)
3. [Complete part 3—use AppsFlyer dashboard and reporting tools.](https://support.appsflyer.com/hc/articles/360001300998#part-3-appsflyer-dashboard-and-reporting-options)

### Part 1: Integration and testing

| Action | Minutes required |
| --- | --- |
| Wait for your registration approval email inviting you to complete the mandatory integration steps. | -- |
| **Mandatory integration steps** | |
| [Specify your attribution link](https://support.appsflyer.com/hc/articles/360018512658#attribution-link): Attribution links are URLs with macros. These macros are populated by you with actual values and sent to AppsFlyer each time a user clicks on a link. <br>Note! If you use a performance network platform supported by AppsFlyer, you must consider the platform-specific instructions provided. See [Performance network guides.](https://support.appsflyer.com/hc/sections/6551055575185-Platforms-for-ad-networks) | 60 |
| [Specify postback macros](https://support.appsflyer.com/hc/articles/360018512658#default-postback): Postbacks are URLs containing macros populated by AppsFlyer and sent to your servers in real-time after each conversion. | 60 |
| Log in to the [AppsFlyer dashboard](https://hq1.appsflyer.com/auth/login) using the credentials provided. | |
| Upload your company logo. Your logo must have the format 200 X 50 transparent PNG. <br>1. In AppsFlyer, in the menu bar, select your email address > **Partner Setup**. <br>2. On the **Profile** tab, upload your company logo. <br>3. Click **Save**. | 5 |
| Test the integration using AppsFlyer test apps:<br>- [Android](https://support.appsflyer.com/hc/articles/4412945443857)<br>- [iOS](/docs/ios-integration-testing-for-ad-networks) | 10 |
| **Optional integration steps** | |
| [iOS] If your advertisers require AppsFlyer Aggregated Advanced Privacy, complete [Advanced Privacy](https://support.appsflyer.com/hc/articles/360018512658#advanced-privacy-and-skan-postbacks) integration. | 60 |
| [iOS] If you run SKAdNetwork campaigns, complete [SKAdNetwork integration.](https://support.appsflyer.com/hc/articles/360018512658#advanced-privacy-and-skan-postbacks) | 60 |
| #### **Authorized agencies**<br>Create and manage a list of agencies you approve to run campaigns through your network integration. This is done by entering their agency ID (af\_prt) in the [**Authorized agencies**](https://support.appsflyer.com/hc/articles/25774607860113-Agency-allowlist) section of the Security center. To obtain the agency ID, the agency must contact you and provide it. | 2 |
| **Optional features and considerations**<br>Consider implementing integrations and options based on advertiser requirements. | |
| To make sure that fraudulent clicks aren't sent using your partner identifier, implement [click signing.](https://support.appsflyer.com/hc/articles/360017831497) | 60+ |
| For advertisers that implement Protect360 or validation rules, add [rejected attribution postbacks](/docs/postback-macros-for-ad-networks#macros%E2%80%94installs-inapp-events-and-rejected-events). | 15 |
| Send cost to AppsFlyer by API. See [InCost API](https://support.appsflyer.com/hc/articles/360007714957). | 60+ |
| [Retargeting integration](/docs/retargeting-attribution-guide). | 15 |
| [View-through attribution integration](https://support.appsflyer.com/hc/articles/210084473-View-through-attribution-guide). | 15 |

### Part 2: Test using advertiser apps

In this part, you'll be testing your integration using an app that belongs to an advertiser. As such, you must contact the advertiser and ask them to complete some of the steps in this part. In this part, regard references to advertisers can also mean agencies if they are acting on behalf of an advertiser.

| Performed by | Action | Minutes required |
| --- | --- | --- |
| Advertiser | Turn on [activate partner.](https://support.appsflyer.com/hc/articles/4410395957521#integration-tab)<br>When on, AppsFlyer considers engagements brought by you as candidates for attribution. | 2 |
| Advertisers | Grant [ad network permissions\*](https://support.appsflyer.com/hc/articles/4410395957521#ad-network-permissions) and add your team members. <br>When on, app performance data is available in your AppsFlyer dashboard. Only listed team members can access the data. | 2 |
| Ad network | [Add team members to your account](https://support.appsflyer.com/hc/articles/4409128270481#creating-users). | 2 |
| Advertiser (admin) | [Register your test devices](https://support.appsflyer.com/hc/articles/207031996). Ask the advertiser to do this on your behalf. | 3 |
| Ad networks | [Test the integration using advertiser apps.](https://support.appsflyer.com/hc/articles/4413093220113) | 60 |

### Part 3: AppsFlyer dashboard and reporting options

| Option |
| --- |
| [Use the partner dashboard](https://support.appsflyer.com/hc/articles/212955423). |
| Get aggregated performance data via cloud storage with [Data Locker](https://support.appsflyer.com/hc/articles/360020818517-Data-Locker-for-ad-networks) for ad networks. |
| Get Protect360 [raw data.](/docs/raw-data-export-page) |

## Integration validation period

To ensure the integrity of the AppsFlyer ecosystem and protect internal systems from invalid traffic, all new ad network integrations undergo a validation period. During this period, AppsFlyer thoroughly verifies the traffic and evaluates its quality before making the integration available to other advertisers in the [Marketplace](https://support.appsflyer.com/hc/articles/9960361873809-Marketplace-Overview-). Ad network integrations that don’t meet high-quality traffic criteria will face removal.

### Validation period—FAQ

<Accordion title="Why can’t advertisers find me in the Marketplace even though I've completed the integration?">
During the validation period, your integration is visible only to the advertiser who referred you. After we've validated your traffic quality, you'll receive an email letting you know that your integration is available to all advertisers.
</Accordion>

<Accordion title="What can I do to make sure my integration will be approved?">
Deliver a significant volume of high-quality traffic for the advertiser who referred you.
</Accordion>

<Accordion title="When should I expect to receive the validation completion email?">
After we've been able to validate enough traffic, you'll receive an email notifying you that the validation period has ended.
</Accordion>

<Accordion title="Can I know the current status of my validation evaluation?">
You'll know only when the validation period has ended, after receiving an email notification.
</Accordion>

<Accordion title="What are the validation criteria based on?">
Validation criteria are based on [Protect360](https://support.appsflyer.com/hc/articles/218254203) dynamic machine learning algorithms. Factors such as traffic quality, volume, and data validity overall are considered, combined with industry best practices.
</Accordion>

<Accordion title="What if another advertiser wants to start working with me during my validation period?">
During the validation period, your integration is visible only to the referring advertiser. Other advertisers will be able to work with you after your validation period has ended successfully.
</Accordion>

<Accordion title="What happens if my integration fails the validation?">
The validation period may be extended to monitor for improvements in traffic quality, or your integration may be permanently removed from the AppsFlyer platform. You'll get notified in either case.
</Accordion>
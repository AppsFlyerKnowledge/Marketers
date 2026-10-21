---
title: Google Ads (AdWords)—Re-engagement
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
  created_at: '2022-01-20T09:55:51Z'
  edited_at: '2025-11-11T09:05:50Z'
  id: 4417296925073
  locale: en-us
  section: Google Ads
  section_id: 6551205645457
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4417296925073-Google-Ads-AdWords-Re-engagement
---
**At a glance:** Measure Google Ads retargeting campaigns.

## Google Ads retargeting campaigns

With AppsFlyer, you can measure the results of **Google Ads App Campaigns for Engagement**.  
In AppsFlyer, such campaigns are called <Anchor target="_blank" href="/marketers/docs/retargeting-attribution-guide">Retargeting</Anchor> campaigns. AppsFlyer supports getting cost, click and impression data for retargeting campaigns. This integration allows you to view and measure your ad spend on Google Ads, and then calculate eCPI and ROI of your Google Ads campaigns.

Retargeting campaigns target users who have installed your app in the past.

* Retargeting engagements by users, who still have your app installed, are called **Re-engagements**. These usually result in deep linking users.
* Retargeting engagements by users, who don't have your app installed, are called **Re-installs** or **Re-attributions**.

For more information, see <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">Google Ads for engagement support documentation</Anchor>.

## Setting up Google Ads app campaigns for engagement

Before you begin, review <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">Google’s instructions for how to share a link with other Google Ads accounts</Anchor> to ensure your engagement campaigns are properly measured via your existing link ID.

To measure Google Ads App Campaigns for Engagement, follow these three steps:

<div id="enabling-retargeting-in-app-settings" />

<Accordion title="Enabling retargeting in app settings">

To enable retargeting campaigns of any media source, you need to enable it on the app level. If this is the first retargeting campaign for your app, do the following:

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings**.
2. Scroll all the way down.
3. Turn on **Re-engagement attribution**.

</Accordion>

<div id="enable-google-ads-retargeting-in-appsflyer" />

<Accordion title="Enable Google Ads retargeting in AppsFlyer">

* Follow the <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">instructions</Anchor> for setting up Google Ads in AppsFlyer.

</Accordion>

<div id="importing-session-start-conversions-in-google-ads" />

<Accordion title="Importing session start conversions in Google Ads">

To record conversions for re-engagement campaigns **in Google Ads**, you need to import the event session\_start in Google Ads.

This event appears in Google Ads if at least one user launches the app after you enable retargeting in AppsFlyer for Google Ads. Just to be sure, launch the app yourself after you enable retargeting.

To learn how to import conversions in Google Ads, see <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">here</Anchor>.

> 📘 **Note**
>
> Unlike all other events, session\_start can be claimed by Google Ads API, even if you don't import session\_start into Google Ads from AppsFlyer.
> However, in that case, these conversions would still be attributed in AppsFlyer. This **creates a substantial discrepancy between your data in AppsFlyer and in Google Ads**. Furthermore, this **prevents Google Ads from optimizing** your campaign user targeting.

</Accordion>

<div id="setting-up-deep-linking-for-app-campaigns-for-engagement" />

<Accordion title="Setting up deep linking for app campaigns for engagement">

Google App Campaigns for Engagement require you to <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6310747?hl=en&ref_topic=3121770">use deep links for re-engagement campaigns</Anchor>. Third-party deep linking solutions cannot be used due to a domain mismatch. This includes AppsFlyer’s OneLink. Use your own <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6046977?hl=en">internally-developed App Links, Universal Links or custom URI schemas</Anchor>.

There is no need to add any additional parameters to the deep link (is\_retargeting=true and pid=adwords are not required).

</Accordion>

## Dynamic remarketing and shopping campaigns

Dynamic remarketing for apps and shopping campaigns is supported in AppsFlyer. The AppsFlyer platform treats them just like any other re-engagement campaign.

* To learn about Dynamic remarketing for apps, click <Anchor target="_blank" href="https://support.google.com/adwords/answer/7538938">here</Anchor>.
* To learn about Shopping campaigns, click <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2454022?hl=en">here</Anchor>.
* To learn more about Google Ads for Engagement click <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">here</Anchor>.

### Support for non-app campaigns (Demand Gen and SEM)

AppsFlyer only supports re-engagement measurement for Google’s non-app campaigns, including:

* Demand Gen campaigns
* Search Engine Marketing (SEM) campaigns

These campaigns work **out of the box** with AppsFlyer and do not require:

* Parallel tracking
* Smart Script implementation

**Limitations:**

* **Installs** from Demand Gen or SEM campaigns are not attributed on any platform.

**Opt-out:** Google does not currently support opting in or out of non-app campaign measurement (unlike platforms such as TikTok or Meta).

> 📄 **See also**
>
> * For iOS 14-related considerations, see <Anchor target="_blank" href="/marketers/docs/get-skan-postback-data-from-google-ads">Google Ads SKAdNetwork interoperability with AppsFlyer</Anchor>.

<div data-zendesk-anchors="h_01HDP34BWZFG09ABN5NQB6EY32=google-ads-retargeting-campaigns h_01HDP34BWZXXNZDE0SR4MXBC9V=setting-up-google-ads-app-campaigns-for-engagement h_01HDP34BWZNHY08NDX6YSE9CXR=enabling-retargeting-in-app-settings h_01HDP34BWZNNNT4HRMXJB2X3S2=enable-google-ads-retargeting-in-appsflyer h_01HDP34BWZ8MGJKEZFC77VYWNG=importing-session-start-conversions-in-google-ads h_01HDP34BWZHWVKKNB7CEHY73R0=note h_01HDP34BWZ64XG2G0PTH6XCCMG=setting-up-deep-linking-for-app-campaigns-for-engagement h_01HDP34BWZ990SD3B1C5DZRESK=dynamic-remarketing-and-shopping-campaigns h_google-non-app-campaign-support=support-for-non-app-campaigns-demand-gen-and-sem support-for-nonapp-campaigns-demand-gen-and-sem=support-for-non-app-campaigns-demand-gen-and-sem h_01HDP2XBSEJVQ5G0MD0V5R05CM=see-also" />

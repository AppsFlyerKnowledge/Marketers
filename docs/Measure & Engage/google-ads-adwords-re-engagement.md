---
title: "Google Ads (AdWords)—Re-engagement"
excerpt: "Learn how to measure Google Ads App Campaigns for Engagement, set up deep linking, and configure dynamic remarketing with AppsFlyer."
---
With AppsFlyer, you can measure the results of **Google Ads App Campaigns for Engagement**.

In AppsFlyer, such campaigns are called [Retargeting](https://support.appsflyer.com/hc/articles/207033786) campaigns. AppsFlyer supports getting cost, click and impression data for retargeting campaigns. This integration allows you to view and measure your ad spend on Google Ads, and then calculate eCPI and ROI of your Google Ads campaigns.

Retargeting campaigns target users who have installed your app in the past.

- Retargeting engagements by users, who still have your app installed, are called **Re-engagements**. These usually result in deep linking users.
- Retargeting engagements by users, who don't have your app installed, are called **Re-installs** or **Re-attributions**.

For more information, see [Google Ads for engagement support documentation](https://support.google.com/google-ads/answer/9234180).

## Setting up Google Ads app campaigns for engagement

Before you begin, review [Google’s instructions for how to share a link with other Google Ads accounts](https://support.google.com/google-ads/answer/7365001?hl=en) to ensure your engagement campaigns are properly measured via your existing link ID.

To measure Google Ads App Campaigns for Engagement, follow these three steps:

### Enabling retargeting in app settings

To enable retargeting campaigns of any media source, you need to enable it on the app level. If this is the first retargeting campaign for your app, do the following:

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings**.
2. Scroll all the way down.
3. Turn on **Re-engagement attribution**.

### Enable Google Ads retargeting in AppsFlyer

- Follow the [instructions](https://support.appsflyer.com/hc/articles/115002504686#step-2-set-up-google-ads-on-appsflyer-mandatory) for setting up Google Ads in AppsFlyer.

### Importing session start conversions in Google Ads

To record conversions for re-engagement campaigns **in Google Ads**, you need to import the event session\_start in Google Ads.

This event appears in Google Ads if at least one user launches the app after you enable retargeting in AppsFlyer for Google Ads. Just to be sure, launch the app yourself after you enable retargeting.

To learn how to import conversions in Google Ads, see [here](https://support.appsflyer.com/hc/articles/115002504686#step-4-measure-your-app-conversions-mandatory).

> 📘 Note
>
> Unlike all other events, session\_start can be claimed by Google Ads API, even if you don't import session\_start into Google Ads from AppsFlyer.
>
> However, in that case, these conversions would still be attributed in AppsFlyer. This **creates a substantial discrepancy between your data in AppsFlyer and in Google Ads**. Furthermore, this **prevents Google Ads from optimizing** your campaign user targeting.

### Setting up deep linking for app campaigns for engagement

Google App Campaigns for Engagement require you to [use deep links for re-engagement campaigns](https://support.google.com/google-ads/answer/6310747?hl=en&ref_topic=3121770). Third-party deep linking solutions cannot be used due to a domain mismatch. This includes AppsFlyer’s OneLink. Use your own [internally-developed App Links, Universal Links or custom URI schemas](https://support.google.com/google-ads/answer/6046977?hl=en).

There is no need to add any additional parameters to the deep link (is\_retargeting=true and pid=adwords are not required).

## Dynamic remarketing and shopping campaigns

Dynamic remarketing for apps and shopping campaigns is supported in AppsFlyer. The AppsFlyer platform treats them just like any other re-engagement campaign.

- To learn about Dynamic remarketing for apps, click [here](https://support.google.com/adwords/answer/7538938).
- To learn about Shopping campaigns, click [here](https://support.google.com/google-ads/answer/2454022?hl=en).
- To learn more about Google Ads for Engagement click [here](https://support.google.com/google-ads/answer/9234180).

### Support for non-app campaigns (Demand Gen and SEM)

AppsFlyer only supports re-engagement measurement for Google’s non-app campaigns, including:

- Demand Gen campaigns
- Search Engine Marketing (SEM) campaigns

These campaigns work **out of the box** with AppsFlyer and do not require:

- Parallel tracking
- Smart Script implementation

**Limitations:**

- **Installs** from Demand Gen or SEM campaigns are not attributed on any platform.

**Opt-out:** Google does not currently support opting in or out of non-app campaign measurement (unlike platforms such as TikTok or Meta).

<Cards>
  <Card title="Google Ads SKAdNetwork interoperability with AppsFlyer" href="https://support.appsflyer.com/hc/articles/4403215779857">
    For iOS 14-related considerations, see Google Ads SKAdNetwork interoperability with AppsFlyer.
  </Card>
</Cards>
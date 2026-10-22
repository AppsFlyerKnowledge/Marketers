---
title: Create A/B tests
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2019-05-07T09:17:43Z'
  edited_at: '2026-07-27T15:46:37Z'
  id: 360001523657
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360001523657-Create-A-B-tests
---
> **At a glance:** Use AppsFlyer to A/B test media sources, campaigns, creatives, targeting, and ad placement.

![AB_TESTING.jpg](https://files.readme.io/259277a96d044e85cbac39de0f636bad531706e53e2ad5a21475277ea9dbd3a6-360002822018.jpg)

## What is A/B testing?

A/B testing is a method used by marketers to test different elements of their ads and campaigns. Each ad contains elements (targeting, visual, texts), which may affect the conversion rates of potential users. Finding the best performing variations of your ad elements may have a significant impact on the bottom line of your mobile marketing efforts.

This article explains **how advertisers can perform A/B tests using AppsFlyer, to find the best performing ad elements**.

## How to A/B test mobile campaigns

To A/B test an element, split your mobile traffic 50/50 between two sources showing the identical offer. Next, create two variations of the element that you want to test. After sufficient traffic has flowed through, you can compare the results of your existing version (control) to the new version (variation).

The following steps apply to an A/B test you run using AppsFlyer.

**Setup**:

1. Select the element to test.  
   In this article, we explain about A/B testing [creatives](/docs/create-a-b-tests#ab-testing-creatives-and-targeting), ad placements, media sources, and campaigns.
2. Create two identical campaigns (or ads), and then vary a single element within the ad. For example,  call-to-action button copy.
   * To test the impact of the variation on **install conversion rates**, split the traffic equally between the two campaigns.   
     If full impression data is available for both sources, divide installations by impressions to calculate the install conversion rates.
   * To test the impact of the variation on the quality of users, **post-installation**, you can send different amounts of traffic to the two campaigns.
3. Drive sufficient traffic to each campaign to reach statistical significance, that means at least 50 installs per campaign. Use the <Anchor target="_blank" href="https://neilpatel.com/ab-testing-calculator/">A/B testing significance calculator</Anchor>.

**Analysis:**

1. Use AppsFlyer's dashboard and data to compare the performance of the key KPIs between the two campaigns.
2. Select the winning variation and use it in your live campaigns.

## A/B testing creatives and targeting

Creatives contain many elements with varying impact on user conversion rates, including copy, images, colors, fonts, buttons, etc. Targeting parameters, like country, age, or gender, may also have a major impact on conversion rates. And for iOS 15+, you can also have up to 35 custom product pages. **A/B testing these elements can help you find which factors have the biggest impact on improving user conversion rates**.

Below we explain two methods of A/B testing using:

* A single media source
* Multiple media sources

| Method | Pros | Cons |
| --- | --- | --- |
| A/B testing with a single media source | <ul><li>Quick setup</li><li>Easy to test install conversion rate</li></ul> | <ul><li>Results may only apply to users of the specific media source</li><li>May take longer to test</li></ul> |
| A/B testing across multiple media sources | <ul><li>Fast results</li><li>Results apply to users from all media sources</li></ul> | <ul><li>Need to update attribution links in multiple places</li></ul> |

<div id="method-1-ab-testing-with-a-single-media-source" />

<Accordion title="Method 1: A/B testing with a single media source">

**Setup**:

1. Select a trusted media source with sufficient traffic.
2. Create two campaigns or <Anchor target="_blank" href="/marketers/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup">Smart Banners</Anchor> in AppsFlyer by using one of the following methods:
   * Vary the campaign that is the name that is "**c**" parameter in the attribution link.
   * Alternately you can create two ad sets ("**af\_adset**=") within a campaign or single ads ("**af\_ad=**") within an ad set. **Note**: In Smart Banners, you can also <Anchor target="_blank" href="/marketers/docs/smart-banners-mobile-web-to-app-for-marketers#ab-testing-banner-performance">A/B test by putting different parameters for each banner</Anchor> within the same banner group.
   * For iOS 15+, you can also test the efficacy of different custom product pages, by sending different OneLink URLs to different product pages. <Anchor target="_blank" href="/marketers/docs/redirect-users-to-custom-app-store-product-pages">Learn more</Anchor>
3. Use the same creative in both campaigns, except for the tested variation.
4. Send the same amount of traffic to both campaigns.

**Analysis:**

* Compare KPIs (for example, install conversion rate, ROI, ARPU, loyal user rate) of the campaigns in the Overview dashboard page.

</Accordion>

<div id="method-2-ab-testing-across-multiple-media-sources" />

<Accordion title="Method 2: A/B testing across multiple media sources">

**Setup**:

1. Select a subscriber parameter to hold the variation value.  
   For example, to test 2 CTA text variations you can use af\_sub1="install now" or af\_sub1="please install". More about subscriber parameters and a creative test example <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">here</Anchor>.
2. Add the subscriber parameter with the matching value to every live attribution link.
3. It's recommended to use the same creatives in all campaigns, except for the tested variation.

**Analysis:**

1. Download the installation or in-app events raw data reports. Use your selected subscriber parameter column to filter and sort your data.
2. Compare the performance of creatives with either of the 2 stored values.

</Accordion>

## A/B testing ad placement on mobile web

![ad_placement.png](https://files.readme.io/6d64eed1a7a16c6daae9c93429d5bd46625dc4de12728e42b49a91ae69765f24-360002747977.png)

The location of banners for your apps on mobile websites may significantly impact user conversion rates. In most cases, advertisers use their own mobile websites to convert visitors into mobile users.

With the AppsFlyer <Anchor target="_blank" href="/marketers/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners feature</Anchor>, you can set up mobile web banners quickly and easily. In addition, the feature also enables you to easily run A/B tests to **determine the best placement for converting website visitors into mobile users**.

**Setup**:

1. Implement <Anchor target="_blank" href="/marketers/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor> in your mobile website.
2. For each new visitor, determine whether to show the banner at the top or bottom of the page. Make sure to split the traffic 50/50 between the two.  
   Developer Tip - A simple method for splitting your website traffic is to use a visitor counter, and then check whether the counter value is odd (option A) or even (option B) for each new visitor.
3. Set the banner location and attribution link according to the determined location using the Smart Banners' <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">SDK API ShowBanner</Anchor>.  
   Example:

   ```javascript
   showBanner({ bannerContainerQuery: "#document.body", additionalParams:{ af_sub5: "top"}})
   ```

**Analysis:**

1. Download the raw data reports for installs or in-app events. Use your selected subscriber parameter (e.g. af\_sub5) column to filter and sort your data.
2. Compare the performance of the two ad placements, i.e. which placement got more installs or post-install events.

## A/B testing media sources

Helping advertisers identify the best (and worst) performing media sources for their apps is what AppsFlyer was built for. However, **if advertisers fail to compare media sources correctly, they risk reaching the wrong conclusions about traffic quality**.

**Setup:**

1. Create a single ad creative for BOTH media sources.
2. Define an ad for each media source, with the same exact audience targeting parameters.
3. You can send different amounts of traffic to the 2 media sources.

**Analysis:**

1. If the ads being tested are the only ones running on both media sources, use AppsFlyer's dashboard and data to easily compare your key KPI between the two sources.  
     
   Otherwise:
2. Go to AppsFlyer's Retention Report, <Anchor target="_blank" href="/marketers/docs/cohort-and-retention-dashboard">Cohort Report</Anchor>, <Anchor target="_blank" href="/marketers/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor> or <Anchor target="_blank" href="/marketers/docs/pivot-table-user-metrics">Pivot Table</Anchor>.
3. Group by Media Source -> Campaign -> Ad set -> Ad.
4. Compare KPIs to identify the top-performing media source.

> 📄 **Example**
>
> [![](https://files.readme.io/bf907e0e67d24764a68579ba6fc42d0d49befbc7ffc7645b91ae1aa8f8b97c12-360002829938.png)](https://files.readme.io/bf907e0e67d24764a68579ba6fc42d0d49befbc7ffc7645b91ae1aa8f8b97c12-360002829938.png)
>
> * 1 and 2 are different ads on the same media source. Compare a single KPI for them, for example, retention day 4 rate, to A/B test creatives, targeting, or ad placement.
> * 2 and 3 are ads on different media sources. If the creatives and targeting of the ads are identical, comparing a single KPI enables A/B testing the media source.

### Using audiences split for easy A/B testing of media sources

If you set the same targeting parameters for each media source, the test includes the targeting abilities of the networks. When A/B testing, it’s best to test a single variation each time. As a result, it's advisable to eliminate the differences in targeting abilities, when A/B testing other factors in the performance of networks.

To achieve this, we recommend splitting an audience randomly and targeting both audiences with the same creative, on each tested network. AppsFlyer offers an **easy method for defining, splitting, and automatically distributing audiences between different media sources**. Read about it <Anchor target="_blank" href="/marketers/docs/audiences-guide#audience-split-and-incrementality-testing">here</Anchor>.

<div data-zendesk-anchors="h_01HN5CNKKBHV52ENXJXCBV2CES=what-is-ab-testing h_01HN5CNKKC02NKW4330QB6E01T=how-to-ab-test-mobile-campaigns h_01HN5CNKKCJPZSEEF1RAHC0HXD=ab-testing-creatives-and-targeting h_01HN5CNKKCMVE9YH379RP1S19W=method-1-ab-testing-with-a-single-media-source h_01HN5CNKKC53RTV61K08T9AVRA=method-2-ab-testing-across-multiple-media-sources h_01HN5CNKKCVPSSZZTJ8QGJHY1B=ab-testing-ad-placement-on-mobile-web h_01HN5CNKKC03ZAFCQZ0KJ0RHCE=ab-testing-media-sources h_01HN5CNKKC4M6YMPHTQCFHFDMD=example h_01HN5CNKKC551X3HQFNKHW1JBY=using-audiences-split-for-easy-ab-testing-of-media-sources" />

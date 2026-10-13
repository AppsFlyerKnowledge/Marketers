---
title: "People-Based Attribution vs. Google Analytics"
excerpt: "The differences between People-based Attribution (PBA) and Google Analytics"
x-zendesk:
  id: 360001305617
  url: https://support.appsflyer.com/hc/en-us/articles/360001305617-People-Based-Attribution-vs-Google-Analytics
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  position: 15
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-gil-or, Marketers, Cross-Platform Measurement]
  labels: [Google Analytics, People Based Analysis, People Based Attribution, People Based Attribution SDK, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2019-03-28T07:22:04Z'
  edited_at: '2023-02-15T13:15:05Z'
---
## PBA compared to Google Analytics

PBA and Google Analytics are web analytics and conversion measurement solutions. Each focuses on different measurement aspects. PBA also offers additional benefits.

- PBA is an independent, unbiased attribution authority that focuses on attribution measurement. PBA attributes conversions and revenue to media sources and campaigns that bring users to your website.
- Google Analytics focuses more on web analytics. It gathers, analyzes, and aggregates data related to user behavior. With Google Analytics you can analyze, for example, user behavior, funnels, web events.

### Benefits of PBA over Google Analytics

The following are the benefits of PBA over Google Analytics:

- PBA includes:
  - Web-to-app measurement. This metric tells you how many users move from your website to your app. It also tells you which media sources and campaigns bring users to your website who subsequently install your app.
  - [Raw data for conversions and events](/docs/pba-raw-data-reports) that you can pull into your own BI systems. This gives you the ability and power to run your analysis.

### Reasons for differences

If you compare data from PBA and Google Analytics, refer to the following reasons for differences in data.

#### SDK implementation

The way you implement PBA and Google Analytics could affect data collection.

<Accordion title="Google Analytics shows more sessions and visitors">

**Cause**

If Google Analytics loads before the Web SDK users that bounce or users that spend short periods of time on your website are not counted in PBA. This causes discrepancies in data for sessions and visitors.

**Solution**

We strongly recommend positioning the Web SDK such that it loads as early as possible.

Whether you [load the SDK directly or through Google Tag Manager](/docs/pba-web-sdk-integration-guide#integrating-the-web-sdk-into-the-website), late loading of the SDK can cause significant discrepancies.

</Accordion>

<Accordion title="Google Analytics shows more data for sessions, campaign, and conversions">

**Cause**

The Web SDK is present only on certain pages. Google Analytics is present on all pages. As a result, Google Analytics collects data from all over your website whereas the Web SDK collects data only from certain pages. This causes discrepancies in data for sessions, visitors, campaigns, and conversions.

**Solution**

Implement the Web SDK on all pages of your website.

</Accordion>

### Dashboard settings

Dashboard settings such as timezone and data filter could affect how data is presented to you.

<Accordion title="Timezone settings - discrepancies in data">

**Cause**

If the timezone settings in your Google Analytics are different from those in your PBA dashboard, you might encounter discrepancies.

**Example**

Your AppsFlyer dashboard is configured to UTC and your GA dashboard is configured to UTC +13. This means that your GA dashboard is ahead of your AppsFlyer dashboard by one day.

Therefore, data that appears in the AppsFlyer dashboard for March 2nd only appears in your GA dashboard if you choose March 3rd in the date range filter.

**Solution**

Make sure time zone settings are the same in both AppsFlyer and Google Analytics.

</Accordion>

<Accordion title="Data filters - discrepancies in data">

**Issue**

Both AppsFlyer and Google Analytics allow you to filter data according to date, attributed media sources, campaigns, and events. Different filters in AppsFlyer and Google Analytics can generate different views for the same data.

**Solution**

When you compare data from the two dashboards, make sure no filters are applied to the data set.

</Accordion>

### Conversions and events

Different attribution models, lookback windows, how you send events, and cookie settings, can all affect data collection and processing.

<Accordion title="Lookback window - discrepancies in conversion measurement">

**Cause**

If you have different lookback windows in Google Analytics and PBA, discrepancies might occur in attribution data.

**Solution**

PBA's lookback window is always 30 days. Make sure to set a 30-day lookback window in Google Analytics when you [choose your attribution model](https://support.google.com/analytics/answer/1665189).

</Accordion>

<Accordion title="Attribution model - discrepancies in conversion measurement">

**Cause**

Different attribution models in PBA and Google Analytics can cause discrepancies in attribution data.

**Solution**

Google Analytics offers [default attribution models](https://support.google.com/analytics/answer/1665189?hl=en) that you can choose from. However, PBA operates in a last non-direct touch, 30-day lookback window attribution model. Make sure to choose a last non-direct touch attribution model in Google Analytics.

</Accordion>

<Accordion title="Sending events">

**Issue**

Both Google Analytics SDK and the Web SDK allow you to send events. If you implement one logic for sending events to Google Analytics and another for sending events to PBA, discrepancies might arise.

**Solution**

When you send events, verify the following:

- Make sure that the same trigger applies to both
- Make sure you send the event to both Google Analytics and PBA

Click [here](/docs/pba-web-sdk-integration-guide#principles-of-event-recording) to learn how to send events using the Web SDK.

</Accordion>

#### Cookies

Both PBA and Google Analytics use cookies to recognize users.

<Accordion title="Cookie settings in Google Analytics">

Although it is recommended to let Google Analytics SDK automatically handle cookie settings, you can still [configure and change cookie settings](https://developers.google.com/analytics/devguides/collection/analyticsjs/cookies-user-id). Any change in cookie settings might cause discrepancies.

</Accordion>

<Accordion title="Setting Cookie Expiration">

Google Analytics allows you to set cookie expiry. If you set the Google Analytics cookie to expire before the Web SDK cookie does, it might cause discrepancies.

**Example**

Mark is a constant visitor to your website for over a year now and considers subscribing to premium content.

Your developer set the Google Analytics cookie to expire after a year. The Web SDK, however, sets the cookie to expire after two years.

When Mark finally subscribes and conversion is registered, the Google Analytics cookie is no longer valid and another is set in its stead.

The end result is that Google Analytics shows two users, both of them are Mark, with only one of them having a conversion associated with it. PBA however, shows one user for Mark and the same user that has a conversion associated with it.

This means that your conversion rate in Google Analytics is lower than that in PBA.

</Accordion>

<Accordion title="Setting Cookie Subdomain">

Google Analytics allows you to set cookies for subdomains whereas PBA only sets cookies on the top-level domain.

**Example**

You set a cookie to the subdomain **store.mywebsite.com**. Sharon visits your website and then goes to your online store at **store.mywebsite.com**. Google Analytics considers her **as two different users**.

Since PBA only sets cookies on the top-level domain **mywebsite.com**, it considers Sharon in **mywebsite.com** and **store.mywebsite.com** as the same user.

The end result is two users in Google Analytics and one user in PBA.

</Accordion>
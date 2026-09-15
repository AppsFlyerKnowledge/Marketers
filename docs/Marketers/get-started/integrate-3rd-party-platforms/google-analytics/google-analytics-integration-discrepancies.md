---
title: "Google Analytics integration—Discrepancies"
excerpt: "Understand the discrepancies that might occur between AppsFlyer and Google Analytics, including time zone differences, session counts, and duplicate events."
---
**At a glance:** Understand the discrepancies that might occur between AppsFlyer and Google Analytics.

## Discrepancies in data between AppsFlyer and Google Analytics

Listed below are reasons for discrepancies between AppsFlyer and Google Analytics.

### High volume of non-consenting iOS 14.5+ users

When [AAP is enabled for your app](https://support.appsflyer.com/hc/articles/360018515798-Aggregated-Advanced-Privacy-framework), AppsFlyer doesn't send postbacks to Google Analytics for non-consenting iOS 14.5+ users. In case your app has a large number of such users, there will be a discrepancy between AppsFlyer and Google Analytics dashboards.

### Customer user ID

Google Analytics associates events by Customer User ID. The Customer User ID that AppsFlyer sends by default is GAID or IDFA.

Therefore, Google Analytics sees re-installing users (users who install, uninstall and then reinstall) as the same users.

#### Example

A user installs your app and then uninstalls it. The user then re-installs the app through a retargeting campaign within the re-attribution window.

Google Analytics sees this user as the same user. In User Explorer in Google Analytics, this user has listed under them all of the following:

- regular-install
- regular-in-app-event
- reattribution-install
- reattribution-in-app-event

AppsFlyer, on the other hand, sees this user as two different users:

- A user that comes from a UA campaign
- A user that comes from a retargeting campaign

In addition, discrepancies might arise if you implement [both GA and AppsFlyer SDK](https://support.appsflyer.com/hc/articles/4413033818641#appsflyer-and-google-analytics-sdks).

### Time zone differences

If the time zone of your GA dashboard differs from that of your app's timezone in AppsFlyer, data might not align.

#### Example

Your app's dashboard is configured to GMT +13 and your GA dashboard is configured to GMT. This means that your app's dashboard is ahead of your GA's dashboard by one day.

Therefore, data that appears in GA dashboard for March 2nd only appears in your app's dashboard if you choose March 3rd in the date range filter.

### Duplicate events

If events occur in proximity to each other, both AppsFlyer and Google Analytics might drop them as duplicate events. AppsFlyer's [event deduplication mechanism](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-guide#how-does-appsflyer-handle-event-deduplication) is different than the one that Google Analytics uses.

Because AppsFlyer and Google Analytics deduplicate events differently, discrepancies in events data might occur.

### Session count

AppsFlyer counts sessions each time the app is launched or comes back to the foreground. Google Analytics counts sessions according to CID (customer user id) and activity.

#### Example

A user launches your app, performs some actions and then sends the app to the background. The user then repeats the process 4 times, each time in an interval of about 5 minutes.

To AppsFlyer, this counts as 5 different sessions. However, to Google Analytics this counts as a single session.

To learn more about how AppsFlyer and Google Analytics calculate sessions, check the resources below.

1. [How AppsFlyer counts sessions](https://support.appsflyer.com/hc/articles/360000520785)
2. [Google Analytics sessions](https://support.google.com/analytics/answer/2731565?hl=en)

### Google Analytics views and filters

Google Analytics allows you to create different views and apply different filters to them. When you compare data from AppsFlyer and Google Analytics, make sure you view data in the _**All Web Site Data**_ view in Google Analytics.
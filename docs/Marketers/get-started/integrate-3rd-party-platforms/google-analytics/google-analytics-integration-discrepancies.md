---
title: "Google Analytics integration—Discrepancies"
excerpt: "Understand the discrepancies that might occur between AppsFlyer and Google Analytics."
x-zendesk:
  id: 4413026674833
  url: https://support.appsflyer.com/hc/en-us/articles/4413026674833-Google-Analytics-integration-Discrepancies
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Google Analytics
  section_id: 6551226043793
  position: 3
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Analytics, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-12-07T13:38:17Z'
  edited_at: '2026-08-09T14:24:20Z'
---
## Discrepancies in data between AppsFlyer and Google Analytics

Listed below are reasons for discrepancies between AppsFlyer and Google Analytics.

<div id="high-volume-of-nonconsenting-ios-145-users" />

<Accordion title="High volume of non-consenting iOS 14.5+ users">

When [AAP is enabled for your app](/docs/apply-aggregated-advanced-privacy-framework), AppsFlyer doesn't send postbacks to Google Analytics for non-consenting iOS 14.5+ users. In case your app has a large number of such users, there will be a discrepancy between AppsFlyer and Google Analytics dashboards.

</Accordion>

<div id="customer-user-id" />

<Accordion title="Customer user ID">

Google Analytics associates events by Customer User ID. The Customer User ID that AppsFlyer sends by default is GAID or IDFA.

Therefore, Google Analytics sees re-installing users (users who install, uninstall and then reinstall) as the same users.

> 📘 **Example**
>
> A user installs your app and then uninstalls it. The user then re-installs the app through a retargeting campaign within the re-attribution window.
>
> Google Analytics sees this user as the same user. In User Explorer in Google Analytics, this user has listed under them all of the following:
>
> * regular-install
> * regular-in-app-event
> * reattribution-install
> * reattribution-in-app-event
>
> AppsFlyer, on the other hand, sees this user as two different users:
>
> * A user that comes from a UA campaign
> * A user that comes from a retargeting campaign

In addition, discrepancies might arise if you implement both GA and AppsFlyer SDK.

</Accordion>

<div id="time-zone-differences" />

<Accordion title="Time zone differences">

If the time zone of your GA dashboard differs from that of your app's timezone in AppsFlyer, data might not align.

> 📘 **Example**
>
> Your app's dashboard is configured to GMT +13 and your GA dashboard is configured to GMT. This means that your app's dashboard is ahead of your GA's dashboard by one day.
>
> Therefore, data that appears in GA dashboard for March 2nd only appears in your app's dashboard if you choose March 3rd in the date range filter.

</Accordion>

<div id="duplicate-events" />

<Accordion title="Duplicate events">

If events occur in proximity to each other, both AppsFlyer and Google Analytics might drop them as duplicate events. AppsFlyer's [event deduplication mechanism](/docs/in-app-events-overview#how-does-appsflyer-handle-event-deduplication) is different than the one that Google Analytics uses.

Because AppsFlyer and Google Analytics deduplicate events differently, discrepancies in events data might occur.

</Accordion>

<div id="session-count" />

<Accordion title="Session count">

AppsFlyer counts sessions each time the app is launched or comes back to the foreground. Google Analytics counts sessions according to CID (customer user id) and activity.

> 📘 **Example**
>
> A user launches your app, performs some actions and then sends the app to the background. The user then repeats the process 4 times, each time in an interval of about 5 minutes.
>
> To AppsFlyer, this counts as 5 different sessions. However, to Google Analytics this counts as a single session.

To learn more about how AppsFlyer and Google Analytics calculate sessions, check the resources below.

1. [How AppsFlyer counts sessions](/docs/measure-sessions)
2. [Google Analytics sessions](https://support.google.com/analytics/answer/2731565?hl=en)

</Accordion>

<div id="google-analytics-views-and-filters" />

<Accordion title="Google Analytics views and filters">

Google Analytics allows you to create different views and apply different filters to them. When you compare data from AppsFlyer and Google Analytics, make sure you view data in the ***All Web Site Data*** view in Google Analytics.

</Accordion>

<div data-zendesk-anchors="h_01HDP3G48R2XXEQDEAAJYGR9V9=discrepancies-in-data-between-appsflyer-and-google-analytics h_01HDP3G48RQD3EW0DTRE2252JF=high-volume-of-nonconsenting-ios-145-users h_01HDP3G48RPWDY7ZRG9HM1F5AR=customer-user-id h_01HDP3G48RMGSJSWQDSKW5DXD9=example h_01HDP3G48R2JWF3Y23011NDCAN=time-zone-differences h_01HDP3G48RXFWZX4FQ0V2ZE44D=example-1 h_01HDP3G48RHT7PWSWZZAG27CP0=duplicate-events h_01HDP3G48R1044364MF96QX41E=session-count h_01HDP3G48RHQ3VG6N4HTT1KJFS=example-2 h_01HDP3G48R9571AS0WH7TWQWJP=google-analytics-views-and-filters" />

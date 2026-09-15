---
title: "Measure sessions"
excerpt: "The sessions metric is used by advertisers to measure app user engagement during a given period."
---
<Image src="https://files.readme.io/97b845b9e04809dc6b670746c81cf1ca59dce11f492194ee7e7895ada01c0b86-360016015278.jpg" alt="DAU_example.jpg" />

## Sessions counting principles

The number of sessions, AKA launch, performed by users is an important metric and used as a measure of user engagement with the app. It is available via several reports and dashboards. Sessions is used to derive the following metrics:

- Daily active users (DAU)
- Monthly active users (MAU)
- Retention
- Loyal users using the default setting of 3-app opens

> 📘 Note!
>
> In the case of organic sessions, the metric is available in the Activity and Cohort dashboards but isn't available in the Overview dashboard.

### Sessions calculation

The sessions metric is calculated using the _af_app_opened_ event reported by the SDK. On the server side, the first 5 sessions are counted without regard for the time interval between them. However, from the sixth session onwards, a minimum time between sessions mechanism regulates which sessions are counted.

The _af_app_opened event_ displays as _launch_ in sessions raw data available via Data Locker. Sessions isn't available via other reporting tools. For ease of understanding, in this article, we'll use the term _af_app_opened_.

**Sessions reporting**

A session is reported by the SDK when any of the following occur:

- A user launches the app.
- When the app is brought to the foreground from the background. The developer can alter the reporting behavior by calling [setMinTimeBetweenSessions.](https://support.appsflyer.com/hc/articles/360000520785-How-does-AppsFlyer-Count-Sessions-#session-reporting-by-the-app-sdk)
- An explicit session report by the developer in Android apps. For example, this is implemented by utility apps that are always in the background.

**Sessions metric**

The sessions metric is counted from the first session onwards. From the sixth session, a minimum time between sessions mechanism is activated with a default duration of 10 minutes as described in the example that follows.

## Minimum time between sessions mechanism

The mechanism impacts the sessions count. 

> 🚧 Note!
>
> Consider that if the Minimum time between sessions is long, more than one hour, and users don't open the app many times a day, then some session-related metrics, such as DAU and retention can be impacted. This is especially true in the case of apps where users typically open the app once a day.

### Description and example

The mechanism is activated after the first five sessions are counted. From the sixth session onwards a session is counted if the minimum time allowed between sessions has passed.

The flow is as follows: A session is counted → A countdown timer starts → Sessions reported while the timer is counting down are disregarded.

**Example**

Assumption: The minimum allowed time between sessions setting is 10 minutes and the first five sessions were already counted.

| Example case | Session reporting times (number of minutes since 00:00) | Number of sessions counted | Sessions disregarded |
| --- | --- | --- | --- |
| A | 0, 10, 20, 30 | 4 | None |
| B | 0, 1, 9, 11 | 2 | 1, 9 |
| C | 0, 10, 15, 21 | 3 | 15 |

### Timer setting

- Default value: 10 minutes
- Possible values are:
  - 1-60 minutes
  - 1-24 hours

**To set the minimum allowed time between sessions timer:**

1. In AppsFlyer, from the side menu, select **Settings** > **App settings**.
2. Set **Minimum time between sessions.**
3. Click **Save settings.**

The change takes effect within an hour.

## Sessions related topics

### Retargeting sessions

- Retargeting sessions are available starting July 12, 2020.
- Retargeting sessions are available in:
  - Retargeting and unified view type in the overview dashboard.
  - The relevant Cohort views, meaning retargeting and unified.
    - In the case of the unified view, if sessions were attributed to a UA and retargeting media source, the retargeting media source prevails, and the UA media source is not displayed.
    - Data freshness: Daily 13:00 UTC.
  - Data Locker: Retargeting sessions reports can be enabled; they include both re-engagement and re-attribution sessions.
    - Data freshness: 6-hour lag.
- During re-engagement windows, sessions are attributed to both the UA and retargeting media source. Similarly, other re-engagement in-app events are [double-attributed](https://support.appsflyer.com/hc/articles/360016371077-Double-attribution-of-retargeting-events).
- In the case of Google Ads and X Ads, to avoid duplicate postbacks, the _af_app_opened_ event is sent once.

### Sessions postbacks to partners

You can send partner session postbacks so that a [postback](https://support.appsflyer.com/hc/articles/208439256-In-app-events-postback-configuration#mapping-methods) is sent for each session counted.

- To send the postback: Explicitly map _af_app_opened_ to a partner event. Note! In the AppsFlyer raw data report available via Data Locker this event reflects as a _launch._
- Consider that this is a high-volume event and that many partners don't want to receive it.

> 📘 Note
>
> The mapping of `af_app_opened` is only supported by partners with **Send Sessions** enabled.

### Session reporting by the app (SDK)

**App-side:** The SDK sends _af_app_opened_ each time the app is opened or brought to the foreground after considering the SDK _setMinTimeBetweenSessions_ setting.

**Server-side:** A session is counted **if it's not on of the first 5 sessions after the app's first launch** and after considering the minimum time between sessions mechanism. Counted sessions are attributed using the same [attribution rules](https://support.appsflyer.com/hc/articles/207447053-Attribution-model-explained) as other in-app events.

#### **Explicit sessions reporting by the developer (Android apps only)**

Use [logSession](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#logsession) in Android to explicitly report a session. An equivalent call is not available in iOS.

- Apps that work in the background continuously may require some logic implemented by the developer to report sessions. For example, utility apps like battery savers, launchers, screen locks, and antivirus apps. For these types of apps, consider reporting a session daily at midnight or some other interval appropriate to the app.
- In other cases, you may want to count sessions when users perform some in-app action, such as pressing the _clear memory_ button and so on.

#### **Setting minimum time between app launches**

In the SDK, set the minimum time that can lapse between two sessions for them to be reported separately.

Use **_setMinTimeBetweenSessions,_** meaning af_app_opened event, to control the minimum amount of time that must occur between sessions so that each of them is reported.

- [Default] five-seconds. Meaning at least 5 seconds must elapse before another session is reported.
- The API allows setting the minimum required time between sessions.

**The `setMinTimeBetweenSessions` SDK reference:**

<Tabs>
<Tab title="Android">

See the [`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setmintimebetweensessions) in the Android SDK reference

</Tab>
<Tab title="iOS">

See the [`minTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#mintimebetweensessions) in the iOS SDK reference

</Tab>
<Tab title="Unity">

See the [`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/api#setmintimebetweensessions) in the Unity SDK reference

</Tab>
</Tabs>
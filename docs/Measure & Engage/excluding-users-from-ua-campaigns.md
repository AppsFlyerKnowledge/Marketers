---
title: "Excluding users from UA campaigns"
excerpt: "Learn how to exclude existing users from user acquisition campaigns to optimize your budget and improve ROAS."
---
Excluding existing users from user acquisition (UA) campaigns helps you obtain more installs with the same budget and improve ROAS.

## Issues and consequences

If your app receives traffic from multiple media sources, then these sources can target your existing users in their UA campaigns.

Campaign performance can suffer for the following reasons:

- **Double payments** - Paying for user impressions/clicks that you paid for in the past.
- **Distorted conversion rates** - UA campaigns seem less successful. There are fewer installs as impressions are wasted on existing users.
- **Loss of alternative users** - Non-users could have seen the ads and become your mobile users.

[SRN mistargeting](https://support.appsflyer.com/hc/articles/360001546905#what-is-srn-mistargeting) is a similar and common performance issue. This significant issue may happen if both your UA and retargeting campaigns are with the same SRN. [Learn more](https://support.appsflyer.com/hc/articles/360001546905#is-mistargeting-a-problem)

## Solutions

These solutions outline how to update ad networks to exclude existing users from UA campaigns.

### Manual update

Collect your raw user-level install data from AppsFlyer to build device ID lists. Then, send these lists to ad networks to ensure user exclusion.

There are several ways to add this raw data to your BI system:

- Download raw-data reports
- Use periodic raw data Pull API requests
- Use Push API to implement real-time collection
- Get conversion data from the SDK

> 📘 Note
>
> In the time gap between manually sending the next list to the ad networks, UA campaigns can target your newest app users.

### Audiences

**[Audiences](/docs/audiences-guide)** is an AppsFlyer premium feature. Every day, selected segments of your user base are sent automatically to multiple ad networks, as chosen by you.

**Audiences** is very useful for maintaining exclude lists:

- **Low effort** - No development work or maintenance is required by you or the ad network.
- **User-friendly** - After a short, initial setup you can start uploading audiences.
- **Efficient** - Segments are sent to ad networks automatically every 24 hours.
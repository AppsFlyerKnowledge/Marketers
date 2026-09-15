---
title: "Redirecting users to the app store"
excerpt: "Learn about the options for redirecting users to the app store after an ad is served, and how to send engagement data to AppsFlyer."
---
## Overview

AppsFlyer receives engagement data (clicks and impressions) for attribution in a number of ways:

- The user **clicks** the ad and gets [redirected to AppsFlyer](#users-redirected-via-appsflyer), and then to the app store.
- The user **clicks or views** the ad and is [directly sent to the app store](#users-sent-directly-by-the-ad-network), while the **attribution link is sent to AppsFlyer from the server**.

In both cases, the regular [attribution link structure and parameters](/docs/about-link-structure-and-parameters) are used.

> 📘 Note
>
> For SRNs, data is received via specialized APIs

## Users redirected via AppsFlyer

When an ad is clicked, the user is directed to AppsFlyer, which then redirects them to the app store by the following flow:

1. The user is redirected to AppsFlyer
2. AppsFlyer logs the click
3. AppsFlyer redirects the user to the app store
4. The user installs the app
5. AppsFlyer attributes the install

## Users sent directly by the ad network

When an ad is clicked, the user is directed to the app store by the ad network, minimizing the number of redirects:

1. The user is sent to the app store
2. The ad network reports the engagement data to AppsFlyer from the device
3. The user installs the app
4. AppsFlyer attributes the install

### Sending engagement data to AppsFlyer

Sending user directly to the app store improves their experience by reducing the number of redirections. It also ensures accurate attribution of installs and enables high-quality traffic.

Ad networks can only report clicks and impressions to AppsFlyer **directly from the user's device**.

#### Timing of sending redirects

To prevent loss of attributions and revenue for the ad network, clicks and impressions must be sent to AppsFlyer in real-time:

- **Impression URLs** must be reported once an ad is served
- **Click URLs** must be reported once a user clicks the ad
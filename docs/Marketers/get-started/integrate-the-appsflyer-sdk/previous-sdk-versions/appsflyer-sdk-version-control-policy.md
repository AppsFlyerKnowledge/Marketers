---
title: "AppsFlyer SDK version control policy"
excerpt: "Learn about the AppsFlyer SDK version control policy, including version lifecycles, deprecation, and end-of-support timelines."
---
**At a glance:** Learn about the AppsFlyer SDK version control policy and what versions we maintain.

## About versioning

Throughout the years, AppsFlyer has released many versions of the SDK. Each SDK version calls a specific API version. The intent of the version control policy is to define how long an API will serve the SDK versions.

## Why do we need version control?

The purpose of version control includes the following:

- Helps you understand in advance when an API for the SDK versions that are integrated into your apps will no longer be supported. This is important because version adoption takes time, meaning it may take some time until your users upgrade to a newer app version.
- Improves stability (backward compatibility is for 2.5 years), thus eliminating unexpected errors when using very old SDK versions.
- Lets you take advantage of new features that require SDK upgrades.

## SDK version lifecycles

An API version is guaranteed to run for 2.5 years. Whenever a new major or minor version of the SDK is released, AppsFlyer will set an end-of-support date for the previous minor version (including all of its patch versions).

**Legacy SDK versions for iOS and Android will stop being supported on a fixed six-month cycle.** This cycle is designed to provide advanced notice, helping teams plan ahead and maintain full app functionality without disruption. Upgrading to the latest SDK ensures access to the newest features, improved stability, and ongoing support.

> ❗️ Important!
>
> To ensure a smooth transition, app developers are encouraged to update to the latest SDK version before the End-of-Support date.

## End of support vs. Deprecated

AppsFlyer distinguishes between **Deprecated** and **End-of-Support** SDK versions to clarify the level of support and impact on data measurement.

- **Deprecated versions:** SDK versions that are no longer recommended due to known issues, such as critical bugs. These versions can still send data to AppsFlyer, but continued use is discouraged. and upgrading to a supported version is strongly advised.
- **End-of-Support versions:** SDK versions for which measurement is fully stopped across all platforms. For both Android and iOS, installs, sessions, and in-app events will not be measured. Any traffic from these versions (unless specifically excluded by AppsFlyer) will receive a 400 status code, meaning the SDK will attempt to send API calls as usual, but AppsFlyer servers will reject them, and the data will not be processed.

## What happens when an SDK version has reached its end-of-support date?

Once a version of the SDK has reached its end-of-support date, AppsFlyer servers will no longer measure installs, sessions, and in-app events. Events that reach these endpoints will simply be rejected.

Since adoption takes time, it is **highly recommended** that your developer upgrade to the latest SDK version well in advance of the end-of-support date.

<Cards>
  <Card title="AppsFlyer Android SDK release notes" href="/docs/appsflyer-android-sdk-release-notes" icon="fa-solid fa-bullhorn">
    View release notes and updates for the Android SDK.
  </Card>
  <Card title="AppsFlyer iOS SDK release notes" href="/docs/appsflyer-ios-sdk-release-notes" icon="fa-solid fa-bullhorn">
    View release notes and updates for the iOS SDK.
  </Card>
</Cards>
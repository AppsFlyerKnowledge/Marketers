---
title: Set up re-attribution window
metadata:
  keywords:
    - Retargeting
    - Re-Attribution
    - reattribution
    - Advertisers
    - Ad Networks
    - re-attribution window
    - reattribution window
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2017-05-23T08:55:35Z'
  edited_at: '2025-04-17T09:39:55Z'
  id: 115002587066
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115002587066-Set-up-re-attribution-window
---
> **At a glance:** Learn about re-attribution window, during which reinstalls are not attributed as new installs.

<div id="re-attribution-window" />

## Re-attribution window

The re-attribution window is a time window that begins the first time a user installs the app and continues for a duration set by the advertiser (default 90 days.) During the re-attribution window app reinstalls aren't recorded as new installs and don't generate a new install postback unless they originate from a **retargeting** campaign.

[![ReAttributionWindow_us-en.png](https://files.readme.io/cc3c4286be2721571329a08cf13bb93acd0dc3ada4f5bc52f0ffd263eff671ca-360011750637.png)](https://files.readme.io/cc3c4286be2721571329a08cf13bb93acd0dc3ada4f5bc52f0ffd263eff671ca-360011750637.png)

<div id="setting-the-re-attribution-window" />

### Setting the re-attribution window

The re-attribution window:

* is set in the <Anchor target="_blank" href="/marketers/docs/app-settings">App Settings</Anchor> page
* the default value is 90 days (3 months)
* has a range of 1-24 months

Installs are evaluated relative to the setting at the moment of install. As such, If you change the setting, it impacts installs (reinstalls) going forward without considering previous installs.

* **Change the re-attribution window from 90 to 30 days**:
  * Install on September 1.
  * Re-attribution window changes on September 2.
  * A reinstall until October 1, is regarded as a reinstall. Starting October 2, it is regarded as a new install.
* **Change the re-attribution window from 30 to 90 days**:
  * Install on September 1.
  * Re-attribution window changes on September 2.
  * A reinstall on October 15, is a reinstall because of the current 90-day window.
  * A reinstall on December 15, is a new install because more than 90 days have elapsed since the install on September 1.

<div id="re-attribution-window-use-cases" />

## Re-attribution window use cases

<div id="first-install" />

<Accordion title="First install">

A lead (who never had the app installed) engages with either a user acquisition or retargeting campaign and installs the mobile app.

The following happens:

* A new install (or organic, if no engagement is recorded), is attributed to the media source in user acquisition dashboards and data
* A new re-attribution window commences
* Install and in-app event postbacks are sent to the attributed media source when configured
* Following in-app events are also attributed to the same media source

</Accordion>

<div id="reinstall" />

<Accordion title="Reinstall">

After the first app install, the user uninstalls and reinstalls during the re-attribution window.

The following happens:

* The install is NOT attributed - it doesn't appear on the dashboard, nor on the data
* NO install postback is sent to any media source
* Depending on the <Anchor target="_blank" href="/marketers/docs/measure-reinstalls#overview">**Post Reinstall Events Attribution**</Anchor> state, in-app events of these reinstalling users are either attributed to organic or to the original install.

</Accordion>

<div id="reattribution" />

<Accordion title="Re-attribution">

After the first app install, during the re-attribution window, the user uninstalls, then engages with a retargeting campaign and reinstalls.  
This is called a re-attribution.

The following happens:

* The install is attributed to the retargeting media source in the retargeting and unified view of the Overview dashboard. In other words, the user acquisition view doesn't contain re-attributions.
* All following in-app events are attributed to the retargeting media source
* An install postback is sent to the retargeting media source

For more Retargeting Attribution information, click <Anchor target="_blank" href="/marketers/docs/retargeting-attribution-guide">here</Anchor>.

</Accordion>

<div id="new-install" />

<Accordion title="New install">

The user uninstalls the app. Then, after the re-attribution window ends, the user reinstalls. This reinstall is considered as a first install and brings the same results:

* A new install (or organic, if no engagement is recorded), is attributed to the media source on the user acquisition dashboards and data
* **A new re-attribution window commences**
* Install and in-app event postbacks are sent to the attributed media source when configured
* Following in-app events are also attributed to the same media source

</Accordion>

<div id="ios-app-restored-from-icloud-backup" />

<Accordion title="iOS app restored from iCloud backup">

Regardless of the re-attribution window, when an application is backed up using iCloud and later restored (on the same device or on another device), AppsFlyer doesn't count it as a new install or reinstall. A user who restores an app from iCloud maintains their AppsFlyer ID and attribution data.

</Accordion>

<div data-zendesk-anchors="reattribution-window=re-attribution-window h_01H95B0F8XEX9RFXW8W6QBQJBY=re-attribution-window setting-the-reattribution-window=setting-the-re-attribution-window h_01H95B0F8X2YQWBB9H0WFXPK8C=setting-the-re-attribution-window reattribution-window-use-cases=re-attribution-window-use-cases h_01H95B0F8Y4T13VYEN2D7T5GHR=re-attribution-window-use-cases h_01H95B0F8Y58QFRSJ9TV3J34EX=first-install h_01H95B0F8YBY482KHT09CZNT9E=reinstall h_01H95B0F8YCQV3H6ZSZE0DF5VV=reattribution h_01H95B0F8Y046Q80V0S8YZ1DWG=new-install h_01H95B0F8Y6M7W02ZSNYCN66PD=ios-app-restored-from-icloud-backup" />

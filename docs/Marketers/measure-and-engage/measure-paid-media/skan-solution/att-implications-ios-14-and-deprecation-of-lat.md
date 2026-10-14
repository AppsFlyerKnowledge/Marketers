---
title: ATT implications (iOS 14+) and deprecation of LAT
excerpt: >-
  Starting iOS 14 iOS uses ATT to determine user privacy preferences and Limit
  ad tracking (LAT) is deprecated.
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2020-10-07T17:33:35Z'
  edited_at: '2023-12-06T00:00:59Z'
  id: 360014090597
  locale: en-us
  section: SKAN solution
  section_id: 6552135379985
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360014090597-ATT-implications-iOS-14-and-deprecation-of-LAT
---
### ATT values

* Starting iOS 14: Apple [ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) (ATT) provides the status values for app tracking authorization.
* AppsFlyer gets ATT from the following sources:
  * AppsFlyer SDK V6+ embedded in the app.
  * By API from advertisers. For example, S2S API.
* ATT is available in raw data reports. You need to explicitly request it as follows:
  * Pull API: Add ATT *to*the additional\_ fields parameter in your Pull API requests.
  * Export Data page: In the report fields tab, explicitly select ATT.
  * Data Locker: In the Data Locker configuration page, explicitly add ATT to the field list.
  * Push API: In the API Access page, explicitly add ATT to the field list.
* In some cases, ATT is populated by values defined by AppsFlyer. They are indicated by the prefix *af* in the table.
* If IDFA is not available it is populated with zeros.

#### ATT values defined by Apple

| ATT status | IDFA availability | Behavior |
| --- | --- | --- |
| not\_determined | In iOS 14-14.4: Available<br /><br />Starting iOS 14.5: Not available | ATT default value |
| restricted | Not available | This is determined by Apple based on the iTunes account and is not related to user behavior. For example, based on user age, devices controlled by organizations. |
| denied | Not available | Occurs if any of the following are true:<ul><li>Set after displaying the prompt</li><li>The user turned off *Allow Apps to Request to Track* (master switch at the device level)</li><li>Before installing iOS 14 on the device, LAT was on</li></ul> |
| authorized | Available | The user explicitly gave consent. |

#### Additional ATT values defined by AppsFlyer

| ATT status | Remark | IDFA availability |
| --- | --- | --- |
| af\_unknown | ATT value was reported by the advertiser but is not a known value per the [ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) specification | iOS version-dependent |
| af\_authorized | IDFA use is permitted for one of the following reasons:<ul><li>Device iOS version: prior to iOS 14.</li><li>The event reported contained IDFA but not ATT. For example, an app having SDK V5.X on a device running an iOS version before iOS 14.</li></ul> | Available |
| af\_unavailable | <ul><li>ATT was not reported in the event by the advertiser and IDFA is not available.</li><li>AppsFlyer SDK version V5.X is unable to get ATT and did not get IDFA</li></ul> | Not available |

### Is LAT in iOS—considerations and how LAT translates to ATT in iOS 14

| iOS version | Use of Is LAT |
| --- | --- |
| Until iOS 13 | ![IsLatTrue_us-en.png](https://files.readme.io/28440075d9c3913a148228a85ede15048d76f24913b48799ec4de3952d8f33e7-360011938457.png)<br /><br />If true, the user-enabled Limit Ad Tracking, IDFA is not available. |
| Starting in iOS 14 | [Apple deprecated I*s LAT*](https://developer.apple.com/documentation/adsupport/asidentifiermanager/1614148-isadvertisingtrackingenabled). Disregard the *Is LAT* value and use ATT instead. |

**How LAT translates to ATT in iOS 14**

[![LATtoiOS14.5.png](https://files.readme.io/872b3acdcd975337ff4de791a9fc98cd45eb50a487e80b3dfad6a1c7d9495739-360017977837.png)](https://files.readme.io/872b3acdcd975337ff4de791a9fc98cd45eb50a487e80b3dfad6a1c7d9495739-360017977837.png)

<div data-zendesk-anchors="h_01HGX9468F5YF0KSHB3S49CW2Y=att-values h_01HGX9468F0TFTMKP1W2J6GEBV=att-values-defined-by-apple h_01HGX96RG9NX9QM2WTX8789DDR=additional-att-values-defined-by-appsflyer is-lat-in-ios%E2%80%94considerations-and-how-lat-translates-to-att-in-ios-14=is-lat-in-iosconsiderations-and-how-lat-translates-to-att-in-ios-14 h_01HGX9468F0VTYNXBJRSTNBCMB=is-lat-in-iosconsiderations-and-how-lat-translates-to-att-in-ios-14" />

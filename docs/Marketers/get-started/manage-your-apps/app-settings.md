---
title: App Settings
excerpt: >-
  Learn about the settings that impact the attribution and analytics of your app
  across all media sources.
metadata:
  keywords:
    - App Settings
    - Advertisers
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Platform essentials
    - Agencies
    - pm-guy-riesenberg
  created_at: '2016-08-16T07:50:37Z'
  edited_at: '2026-10-12T15:24:47Z'
  id: 211719806
  locale: en-us
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/en-us/articles/211719806-App-Settings
---
## App Settings

**Access:**

* An admin (or other users with appropriate permissions) can **change** app settings.
* All account users with access to a specific app can **view** its app settings.

**To change or view app settings:**

1. In AppsFlyer, from the side menu, select**Settings** > **App Settings.**
2. View settings and make changes as needed on the App Settings page.
3. Click **Save settings.**

> 📘 **Note**
>
> You can also change many of these settings for multiple apps at once, instead of one at a time. Look for the **Apply to additional apps** button next to a changed setting. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once).

### General app settings

| Setting | Description |
| --- | --- |
| <span id="sdk-authentication-dev-key"></span>SDK authentication: Dev key | <ul><li>The Dev key authenticates events sent by the app or by S2S to AppsFlyer.</li><li>The key is unique per account and is used by all apps in the account.</li><li>The key is available on the App Settings page to any account user with access to that app.</li><li>[Optional] An individual app key can be allocated in certain scenarios. Reach out to your CSM to discuss this.</li></ul> |
| <span id="aggregated-advanced-privacy-ios-apps"></span>Aggregated Advanced Privacy (iOS apps) | When turned on, user-level attribution data is unavailable to advertisers. Postbacks and event data shared with partners are aggregated and anonymous (more about the [Aggregated Advanced Privacy](/docs/apply-aggregated-advanced-privacy-framework) framework).<br /><br />When turned off, user-level attribution data is available for all partners as aggregated data and can be set for each partner individually.<br /><br />You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| <span id="analytics-define-loyal-user-trigger"></span>Analytics: Define loyal user trigger | <ul><li>The trigger to designate a user as a loyal user. The default option set when you add the app is 3 app opens.</li><li>After attributing in-app events, you can use an in-app event as the trigger event.<ul><li>[Default] 3 app opens.</li><li>The loyal user setting is indicative of user quality. Consider using [Protect360](/docs/protect360-anti-fraud-guide#faq) to combat fraud.</li><li>Changing this setting impacts data retroactively, meaning historical loyal user data is recalculated.</li></ul></li><li>You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once).</li></ul> |
| <span id="minimum-time-between-sessions"></span>Minimum time between sessions | You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| <span id="app-store-country"></span>App store country | Sets the app store country where the app is available. This setting impacts the app as detailed here.<ul><li>**Changing the app status from pending to live**:<ul><li>[When the app goes live](/docs/why-is-my-app-still-pending), AppsFlyer checks the store using the country setting to retrieve details about the app like its icon.</li><li>If the app is not found in the store country set, AppsFlyer can't change the app status from pending to live.</li></ul></li><li>Redirection behavior is impacted by the setting depending on the scenario, as detailed in the table that follows.</li></ul><table><thead><tr><th>User type</th><th>Redirection scenario</th></tr></thead><tbody><tr><td><span id="mobile"></span>Mobile</td><td>Users usually click on attribution links within other mobile apps. On clicking, the operating system determines the app store country that users are redirected to:   \* **Android** redirects based on user IP/location. \* **iOS** redirects to the app store associated with the iTunes account active on the device.</td></tr><tr><td><span id="mobile-and-web"></span>Mobile and web</td><td>When web users click on attribution links, in **websites** (mobile and desktop), the initial redirection is to the store set in-app store country.  On attempting to install, the operating system redirects them to the country store as described for mobile in the preceding row.</td></tr><tr><td><span id="ipad-ios-13"></span>iPad iOS 13</td><td>Starting from iOS 13, [iPads serve the desktop version of websites](https://www.apple.com/ipados/features/). This means that the user type (mobile or web) is not relevant. A click on an attribution link goes to the desktop site, and after that, redirection rules are those of web users.</td></tr></tbody></table> |
| User type | Redirection scenario |
| Mobile | Users usually click on attribution links within other mobile apps. On clicking, the operating system determines the app store country that users are redirected to:<ul><li>**Android** redirects based on user IP/location.</li><li>**iOS** redirects to the app store associated with the iTunes account active on the device.</li></ul> |
| Mobile and web | When web users click on attribution links, in **websites** (mobile and desktop), the initial redirection is to the store set in-app store country.<br /><br />On attempting to install, the operating system redirects them to the country store as described for mobile in the preceding row. |
| iPad iOS 13 | Starting from iOS 13, [iPads serve the desktop version of websites](https://www.apple.com/ipados/features/). This means that the user type (mobile or web) is not relevant. A click on an attribution link goes to the desktop site, and after that, redirection rules are those of web users. |
| <span id="localization-time-zone"></span>Localization: Time Zone | The default app setting is UTC. [About the app time-zone.](/docs/changing-app-time-zone-settings)<br /><br />Support for changing this setting for multiple apps at once is coming soon. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| <span id="localization-currency"></span>Localization: Currency | <ul><li>This defines the app-specific currency which is used for the following metrics:<ul><li>Cost</li><li>In-app events revenue</li><li>Ad revenue</li></ul></li><li>The default app setting is USD.<ul><li>Currency change is available to apps with no revenue or cost.</li><li>For new apps, the currency is set when the app is added.</li></ul></li><li>Support for changing this setting for multiple apps at once is coming soon. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once).</li></ul>**<span id="reporting-tools-impacted-by-app-currency"></span>Reporting tools impacted by app currency**<table><thead><tr><th>Reporting tool</th><th>Currency options available</th></tr></thead><tbody><tr><td><span id="dashboards"></span>Dashboards</td><td>App-specific currency</td></tr><tr><td><span id="export-data-page"></span>Export data page</td><td>App-specific currency</td></tr><tr><td><span id="push-api"></span>Push API</td><td>App-specific currency and USD available simultaneously</td></tr><tr><td><span id="pull-api"></span>Pull API</td><td>Aggregate data: App-specific currency  Raw data: Selectable USD or app-specific currency</td></tr><tr><td><span id="master-api"></span>Master API</td><td>Selectable USD or app-specific currency</td></tr><tr><td>Data Locker</td><td>Only USD</td></tr></tbody></table> |
| Reporting tool | Currency options available |
| Dashboards | App-specific currency |
| Export data page | App-specific currency |
| Push API | App-specific currency and USD available simultaneously |
| Pull API | Aggregate data: App-specific currency<br /><br />Raw data: Selectable USD or app-specific currency |
| Master API | Selectable USD or app-specific currency |
| <span id="data-locker"></span>Data Locker | Only USD |

### Attribution settings

> 📘 **Note**
>
> The settings in this table apply to mobile apps (iOS and Android). Some settings may not be available, or may work differently, for Web apps.

| Setting | Description |
| --- | --- |
| <span id="reattribution-window"></span>Re-attribution window | The [Re-attribution window](/docs/set-up-re-attribution-window) is the period starting from the date of the first install, during which re-installs cannot be attributed as new installs.<ul><li>[Default] Three months</li><li>Value range: 1-24 months</li></ul>Support for changing this setting for multiple apps at once is coming soon. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| <span id="viewthrough-attribution-via-probabilistic-modeling"></span>Enable view-through attribution via probabilistic modeling | <ul><li>If disabled, enable view-through probabilistic modeling.</li><li>After enabling view-through probabilistic modeling, you must also enable view-through attribution in the ad network integration tab.</li><li>Support for changing this setting for multiple apps at once is coming soon. This will require fingerprinting to already be enabled. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once).</li></ul> |
| <span id="reengagement-attribution"></span>Re-engagement attribution | Related reading: [Retargeting guide](/docs/retargeting-attribution-guide)<br /><br />**To turn on re-engagement attribution:**<ul><li>In AppsFlyer, from the side menu, select **Settings** > **App settings**, turn on **Re-engagement attribution**.</li></ul>In addition to the app setting, you must also [make per partner settings](/docs/retargeting-attribution-guide#retargeting-settings).<br /><br />[**Minimum time between re-engagement conversions**](/docs/retargeting-attribution-guide#exclusion-windows)setting is used to prevent ending an existing re-engagement window before its set duration.<br /><br />You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). When applied in bulk, you'll also see a confirmation step before the change takes effect — this doesn't apply when changing an individual app. |
| <span id="minimum-time-between-reengagement-conversions"></span>Minimum time between re-engagement conversions | Prevents an existing re-engagement window from ending before its set duration. Related reading: [Retargeting attribution guide](/docs/retargeting-attribution-guide#exclusion-windows).<br /><br />You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| <span id="organic-search-seo-mobile-app-attribution"></span>SEO (organic search) and AEO mobile app re-engagement attribution | Related reading: [Organic search attribution](/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution)<br /><br />**To turn on SEO / AEO attribution:**<ul><li>In AppsFlyer, from the side menu, select **Settings** > **App settings**, turn on **SEO (organic search) and AEO mobile app re-engagement attribution.**</li></ul>You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| <span id="uninstall-measurement"></span>Uninstall measurement | [Measurement of uninstalls](/docs/measure-uninstalls) relates to installs occurring when uninstall measurement is on.<br /><br />This setting is available only to iOS and Android apps.<br /><br />**To enable uninstall measurement:**<ol><li>Complete per operating system the following:<ul><li>**iOS**: Apps that implement the iOS uninstall attribution feature need to upload the P12 certificate here.</li><li>**Android**: Apps require a Firebase/GCM Server Key to be defined here for Android uninstall attribution.</li></ul></li><li>Turn on **Uninstall measurement**.</li><li>Click **Save settings**</li></ol>**To stop uninstall measurment:**<ol><li>Turn off **Uninstall measurement**.</li><li>Click **Save settings.**</li></ol>Support for changing this setting for multiple apps at once is coming soon. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |

### Advanced settings

| Setting | Description |
| --- | --- |
| <span id="mask-ip-address-in-raw-data-reports"></span>Mask IP addresses | When turned on, end-user device [IP addresses are masked](/docs/apply-ip-masking-to-user-data) in raw data reports and in postbacks sent to partners from the currently selected app.<br /><br />You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| <span id="reinstall-detection-using-ondevice-storage-ios-only"></span>Reinstall detection using on-device storage (iOS only) | Detect reinstalls without depending on advertising IDs. This is done by storing the last app install date on the secure local storage in the device (in iOS, the Keychain). Determining whether an install was a reinstall or a new install, enables you to deduplicate reinstalls from your NOIs, making attribution analytics more accurate. Note: Only the last app install date is stored in the device's local storage for this purpose - no other device identifier (e.g., IDFA, IDFV) is stored.<br /><br />Support for changing this setting for multiple apps at once is coming soon. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| <span id="ios-103-redirect-fallback"></span>iOS 10.3 redirect fallback | [Deprecated] For iOS 10.3+. We've simplified the flow for iOS users and this parameter is no longer in use. [iOS redirections](/docs/uri-scheme-fallback-for-ios).<br /><br />This option is available only to iOS apps. |
| <span id="change-app-name"></span>Change app name | <ul><li>The name of the app, which is then displayed throughout the dashboard and data reports. This is useful if you have different versions of the same app, for example, for regional distribution reasons.</li><li>This change impacts the display of the app. The app ID, used to identify the app when using various AppsFlyer APIs, **remains the same**.</li><li>Names are limited to 50 characters.</li></ul> |
| <span id="outofstore-app-url"></span>Out-of-store app URL | <ul><li>Set the app download URL used as the default redirect destination in attribution links associated with the app.</li><li>This field is mandatory for Android apps specified as out-of-store apps.</li><li>Once set, the URL will be applied as the default redirect destination within about an hour.</li></ul> |

> 📘 **See also**
>
> * [Retargeting attribution guide](/docs/retargeting-attribution-guide)
> * [Organic search attribution](/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution)
> * [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once)

<div data-zendesk-anchors="01ECHQME56X51MDW9TMA6DBNCK=app-settings h_01M22QK1N5EMMPVZ7ZJ55Z3YFF=note h_01HAVS8CVPQKSDKCEM3YHHJ99Y=general-app-settings h_01HAVS8CVQESWAQXKDW5SNVHCJ=reporting-tools-impacted-by-app-currency h_01HAVS8CVQN1YYTT7S49VGB3J0=attribution-settings h_01M1XPKX6DECQPK4R9X6Y4KMBP=note-1 h_01HAVS8CVQTKXVXSMT5KNYZ3T4=advanced-settings h_01HDPCC9465DR4A3CCXYQC2M56=see-also" />

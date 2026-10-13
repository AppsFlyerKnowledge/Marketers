---
title: "App Settings"
excerpt: "Learn about the settings that impact the attribution and analytics of your app across all media sources in AppsFlyer."
---
Learn about the settings that impact the attribution and analytics of your app across all media sources.

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
| SDK authentication: Dev key | * The Dev key authenticates events sent by the app or by S2S to AppsFlyer.<br />* The key is unique per account and is used by all apps in the account.<br />* The key is available on the App Settings page to any account user with access to that app.<br />* [Optional] An individual app key can be allocated in certain scenarios. Reach out to your CSM to discuss this. |
| Aggregated Advanced Privacy (iOS apps) | When turned on, user-level attribution data is unavailable to advertisers. Postbacks and event data shared with partners are aggregated and anonymous (more about the [Aggregated Advanced Privacy](/docs/apply-aggregated-advanced-privacy-framework) framework).<br /><br />When turned off, user-level attribution data is available for all partners as aggregated data and can be set for each partner individually.<br /><br />You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| Analytics: Define loyal user trigger | * The trigger to designate a user as a loyal user. The default option set when you add the app is 3 app opens.<br />* After attributing in-app events, you can use an in-app event as the trigger event.<br />  * [Default] 3 app opens.<br />  * The loyal user setting is indicative of user quality. Consider using [Protect360](/docs/protect360-anti-fraud-guide#faq) to combat fraud.<br />  * Changing this setting impacts data retroactively, meaning historical loyal user data is recalculated.<br />* You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| Minimum time between sessions | You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| App store country | Sets the app store country where the app is available. This setting impacts the app as detailed here.<br /><br />* **Changing the app status from pending to live**:<br />  * [When the app goes live](/docs/why-is-my-app-still-pending), AppsFlyer checks the store using the country setting to retrieve details about the app like its icon.<br />  * If the app is not found in the store country set, AppsFlyer can't change the app status from pending to live.<br />* Redirection behavior is impacted by the setting depending on the scenario, as detailed in the table that follows.<br /><br />\| User type \| Redirection scenario \|<br />\| --- \| --- \|<br />\| Mobile \| Users usually click on attribution links within other mobile apps. On clicking, the operating system determines the app store country that users are redirected to:   * **Android** redirects based on user IP/location. * **iOS** redirects to the app store associated with the iTunes account active on the device. \|<br />\| Mobile and web \| When web users click on attribution links, in **websites** (mobile and desktop), the initial redirection is to the store set in-app store country.  On attempting to install, the operating system redirects them to the country store as described for mobile in the preceding row. \|<br />\| iPad iOS 13 \| Starting from iOS 13, [iPads serve the desktop version of websites](https://www.apple.com/ipados/features/). This means that the user type (mobile or web) is not relevant. A click on an attribution link goes to the desktop site, and after that, redirection rules are those of web users. \| |
| User type | Redirection scenario |
| Mobile | Users usually click on attribution links within other mobile apps. On clicking, the operating system determines the app store country that users are redirected to:<br /><br />* **Android** redirects based on user IP/location.<br />* **iOS** redirects to the app store associated with the iTunes account active on the device. |
| Mobile and web | When web users click on attribution links, in **websites** (mobile and desktop), the initial redirection is to the store set in-app store country.<br /><br />On attempting to install, the operating system redirects them to the country store as described for mobile in the preceding row. |
| iPad iOS 13 | Starting from iOS 13, [iPads serve the desktop version of websites](https://www.apple.com/ipados/features/). This means that the user type (mobile or web) is not relevant. A click on an attribution link goes to the desktop site, and after that, redirection rules are those of web users. |
| Localization: Time Zone | The default app setting is UTC. [About the app time-zone.](/docs/changing-app-time-zone-settings)<br /><br />Support for changing this setting for multiple apps at once is coming soon. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| Localization: Currency | * This defines the app-specific currency which is used for the following metrics:<br />  * Cost<br />  * In-app events revenue<br />  * Ad revenue<br />* The default app setting is USD.<br />  * Currency change is available to apps with no revenue or cost.<br />  * For new apps, the currency is set when the app is added.<br />* Support for changing this setting for multiple apps at once is coming soon. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once).<br /><br />#### Reporting tools impacted by app currency<br /><br />\| Reporting tool \| Currency options available \|<br />\| --- \| --- \|<br />\| Dashboards \| App-specific currency \|<br />\| Export data page \| App-specific currency \|<br />\| Push API \| App-specific currency and USD available simultaneously \|<br />\| Pull API \| Aggregate data: App-specific currency  Raw data: Selectable USD or app-specific currency \|<br />\| Master API \| Selectable USD or app-specific currency \|<br />\| Data Locker \| Only USD \| |
| Reporting tool | Currency options available |
| Dashboards | App-specific currency |
| Export data page | App-specific currency |
| Push API | App-specific currency and USD available simultaneously |
| Pull API | Aggregate data: App-specific currency<br /><br />Raw data: Selectable USD or app-specific currency |
| Master API | Selectable USD or app-specific currency |
| Data Locker | Only USD |

### Attribution settings

> 📘 **Note**
>
> The settings in this table apply to mobile apps (iOS and Android). Some settings may not be available, or may work differently, for Web apps.

| Setting | Description |
| --- | --- |
| Re-attribution window | The [Re-attribution window](/docs/set-up-re-attribution-window) is the period starting from the date of the first install, during which re-installs cannot be attributed as new installs.<br /><br />* [Default] Three months<br />* Value range: 1-24 months<br /><br />Support for changing this setting for multiple apps at once is coming soon. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| Enable view-through attribution via probabilistic modeling | * If disabled, enable view-through probabilistic modeling.<br />* After enabling view-through probabilistic modeling, you must also enable view-through attribution in the ad network integration tab.<br />* Support for changing this setting for multiple apps at once is coming soon. This will require fingerprinting to already be enabled. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| Re-engagement attribution | Related reading: [Retargeting guide](/docs/retargeting-attribution-guide)<br /><br />**To turn on re-engagement attribution:**<br /><br />* In AppsFlyer, from the side menu, select **Settings** > **App settings**, turn on **Re-engagement attribution**.<br /><br />In addition to the app setting, you must also [make per partner settings](/docs/retargeting-attribution-guide#retargeting-settings).<br /><br />[**Minimum time between re-engagement conversions**](/docs/retargeting-attribution-guide#exclusion-windows)setting is used to prevent ending an existing re-engagement window before its set duration.<br /><br />You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). When applied in bulk, you'll also see a confirmation step before the change takes effect — this doesn't apply when changing an individual app. |
| Minimum time between re-engagement conversions | Prevents an existing re-engagement window from ending before its set duration. Related reading: [Retargeting attribution guide](/docs/retargeting-attribution-guide#exclusion-windows).<br /><br />You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| SEO (organic search) and AEO mobile app re-engagement attribution | Related reading: [Organic search attribution](/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution)<br /><br />**To turn on SEO / AEO attribution:**<br /><br />* In AppsFlyer, from the side menu, select **Settings** > **App settings**, turn on **SEO (organic search) and AEO mobile app re-engagement attribution.**<br /><br />You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| Uninstall measurement | [Measurement of uninstalls](/docs/measure-uninstalls) relates to installs occurring when uninstall measurement is on.<br /><br />This setting is available only to iOS and Android apps.<br /><br />**To enable uninstall measurement:**<br /><br />1. Complete per operating system the following:<br />   * **iOS**: Apps that implement the iOS uninstall attribution feature need to upload the P12 certificate here.<br />   * **Android**: Apps require a Firebase/GCM Server Key to be defined here for Android uninstall attribution.<br />2. Turn on **Uninstall measurement**.<br />3. Click **Save settings**<br /><br />**To stop uninstall measurment:**<br /><br />1. Turn off **Uninstall measurement**.<br />2. Click **Save settings.**<br /><br />Support for changing this setting for multiple apps at once is coming soon. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |

### Advanced settings

| Setting | Description |
| --- | --- |
| Mask IP addresses | When turned on, end-user device [IP addresses are masked](/docs/apply-ip-masking-to-user-data) in raw data reports and in postbacks sent to partners from the currently selected app.<br /><br />You can also change this setting for multiple apps at once. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| Reinstall detection using on-device storage (iOS only) | Detect reinstalls without depending on advertising IDs. This is done by storing the last app install date on the secure local storage in the device (in iOS, the Keychain). Determining whether an install was a reinstall or a new install, enables you to deduplicate reinstalls from your NOIs, making attribution analytics more accurate. Note: Only the last app install date is stored in the device's local storage for this purpose - no other device identifier (e.g., IDFA, IDFV) is stored.<br /><br />Support for changing this setting for multiple apps at once is coming soon. Learn more in [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once). |
| iOS 10.3 redirect fallback | [Deprecated] For iOS 10.3+. We've simplified the flow for iOS users and this parameter is no longer in use. [iOS redirections](/docs/uri-scheme-fallback-for-ios).<br /><br />This option is available only to iOS apps. |
| Change app name | * The name of the app, which is then displayed throughout the dashboard and data reports. This is useful if you have different versions of the same app, for example, for regional distribution reasons.<br />* This change impacts the display of the app. The app ID, used to identify the app when using various AppsFlyer APIs, **remains the same**.<br />* Names are limited to 50 characters. |
| Out-of-store app URL | * Set the app download URL used as the default redirect destination in attribution links associated with the app.<br />* This field is mandatory for Android apps specified as out-of-store apps.<br />* Once set, the URL will be applied as the default redirect destination within about an hour. |

> 📘 **See also**
>
> * [Retargeting attribution guide](/docs/retargeting-attribution-guide)
> * [Organic search attribution](/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution)
> * [Apply settings to multiple apps at once](/docs/apply-settings-to-multiple-apps-at-once)
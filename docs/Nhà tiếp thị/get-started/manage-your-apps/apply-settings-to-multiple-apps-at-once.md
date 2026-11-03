---
title: Apply settings to multiple apps at once
deprecated: false
hidden: false
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
  created_at: '2026-09-09T09:10:13Z'
  edited_at: '2026-09-23T10:38:40Z'
  id: 50696362899089
  locale: en-us
  section: Manage your apps
  section_id: 6551015977105
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/50696362899089-Apply-settings-to-multiple-apps-at-once
---
> **At a glance:** Apply the same setting change to multiple apps at once instead of repeating it for each app individually.

## About bulk app settings

You can now apply the same setting changes to multiple apps at once using bulk app settings on the App Settings page. This lets you make a change once and apply it to other eligible apps in a single operation.

To access App Settings, from the side menu, select **Settings** > **App Settings**. Or, from **My Apps**, select an app and open its App Settings.

## Apply a setting to multiple apps

> 📘 **Note**
>
> An app is eligible for a bulk change if the setting applies to that app's platform, it doesn't already have the value you're applying, any required prerequisite is already in place, and you have Manage access to its App Settings. See **Traits and limitations** below for the full criteria per setting.

**To apply a setting change to multiple apps:**

1. Open App Settings for the app whose setting you want to change, and change a setting (toggle, dropdown, or slider).

   <Image alt="Screenshot 2026-09-16 at 14.31.44.png" src="https://files.readme.io/8a1abce58e1e8da4af5899e2e03a2a7fe9e6e9b8e9a04c240585bfd3e7934126-50944987863825.png" width="2557px" />
2. Next to the changed field, click **Apply to additional apps**.

   <Image alt="aap.png" src="https://files.readme.io/0f2144ca43c6db7ffe9967df5c2b2f2fe3e8cffdbefa77167ed9262a61511774-50945027652113.png" width="612px" />
3. Search by app name or app ID and select the apps that should get the same change. Apps that aren't eligible for this change stay visible but appear grayed out. Hover over one to see why.

   <Image alt="Screenshot 2026-09-16 at 14.32.32.png" src="https://files.readme.io/95c79ce8c176e4a0836661a119ca12b1268b8874181d4fd78c96113e5339d6c9-50945018039953.png" width="1304px" />
4. Click outside the list to close it and commit your selection. The **Apply to additional apps** button is replaced with a badge showing the number of apps selected, click it anytime to change your selection.

   <Image alt="ssa.png" src="https://files.readme.io/b93174999053cdbbf5591eb215e6cd10becbd2d1bcb699ff286a8b1523f8a8f0-50944987865361.png" width="1238px" />
5. Repeat these steps for as many settings as needed.
6. At the bottom of the page, click **Save changes** (if you didn't select any additional apps) or **Review & Save** (once you've included apps in a bulk change). Either button shows the total number of changes in parentheses.

   <Image alt="Screenshot 2026-09-16 at 14.33.32.png" src="https://files.readme.io/6dfb050b984932023455af9022364b37534af276d7bb117ddb05ad0fc25d936c-50945018041489.png" width="2269px" />
7. If you included additional apps, review the before and after values for each app on the **Review before saving** screen. Each app's own current value is used as its baseline. You can remove any change from the batch before confirming.

   <Image alt="Screenshot 2026-09-16 at 14.33.38.png" src="https://files.readme.io/c22f67575fc8ac9cbd868c923b5addfe8c70529ee1183fa7231f080d1b54d18c-50945018042385.png" width="1286px" />
8. Click **Confirm & Save**. This saves the app you started on together with every additional app in the batch, in a single operation.

> 📘 **Note**
>
> For Aggregated Advanced Privacy, you'll always see a confirmation step before the change takes effect. For Re-engagement attribution, you'll see this confirmation step only when applying the change in bulk.

> 🚧 **Important**
>
> Every app in the batch updates together at one time. The result will either be:
>
> 1. A success and all apps updated.
> 2. A failure and no app is updated.
>    1. If the save fails, you can retry.

## Traits and limitations

| Trait | Description |
| --- | --- |
| <span id="supported-settings-ships-first"></span>Supported settings (available now) | <ul><li>Aggregated Advanced Privacy (iOS only)</li><li>Re-engagement attribution (iOS, Android)</li><li>Minimum time between re-engagement conversions (iOS, Android)</li><li>SEO Attribution (iOS, Android for enabling; any platform for disabling)</li><li>Mask IP addresses (all platforms except Web)</li><li>Loyal User Event (iOS, Android)</li><li>Minimum time between sessions (iOS, Android)</li></ul> |
| <span id="supported-settings-coming-soon"></span>Supported settings (Coming soon) | These settings aren't supported for bulk changes yet. Coming soon:<ul><li>Re-attribution window (mobile, in days; website, in seconds — not combined in one action)</li><li>Probabilistic modeling (all platforms; requires fingerprinting to already be enabled)</li><li>Timezone (all platforms)</li><li>Currency (all platforms)</li><li>Uninstall measurement (iOS requires a P12 certificate already uploaded; Android requires Firebase already configured)</li><li>Reinstall detection (iOS, Android)</li></ul> |
| <span id="not-supported"></span>Not supported | SDK authentication (Dev key), App store country, Change app name, iOS uninstall certificate upload, and Firebase Project ID, and agency and partner seat settings. |
| <span id="why-an-app-might-be-grayed-out"></span>Why an app might appear grayed out | A grayed-out app isn't eligible for this change at this specific attempt. One of the following reasons will be shown:<ul><li>**Platform mismatch:** the setting doesn't exist on that app's platform.</li><li>**Already set:** the app already has the value you're applying.</li><li>**Missing prerequisite:** for example, probabilistic modeling requires fingerprinting to already be on.</li><li>**Cooldown:** Timezone can't be changed again within two days of a prior change. The tooltip shows the date it becomes available again.</li><li>**No permission:** you don't have Manage access to App Settings for that app.</li></ul> |
| <span id="limits"></span>Limits | There's no practical limit on the number of apps you can include in a bulk change. |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/app-settings">App Settings</Anchor>

<div data-zendesk-anchors="h_01N1A2B3C4D5E6F7G8H9J0K1L2=about-bulk-app-settings h_02N1A2B3C4D5E6F7G8H9J0K1L2=apply-a-setting-to-multiple-apps h_01M25MDHN4Q2TDAZHPGSXQFQKR=note h_01M22PVGBQT0V9BSE1Y37V0KB8=note-1 h_01M22PVGBQQAFHMR7XDYB2BMXN=important h_03N1A2B3C4D5E6F7G8H9J0K1L2=traits-and-limitations h_01M22PVGBQ8BZN09TZ2S4A70SW=see-also" />

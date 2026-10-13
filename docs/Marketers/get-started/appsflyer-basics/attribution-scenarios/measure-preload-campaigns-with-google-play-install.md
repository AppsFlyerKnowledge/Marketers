---
title: "Measure preload campaigns with Google Play Install"
x-zendesk:
  id: 4404557237649
  url: https://support.appsflyer.com/hc/en-us/articles/4404557237649-Measure-preload-campaigns-with-Google-Play-Install
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Attribution scenarios
  section_id: 6551328497041
  position: 3
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-alina-koifman, Marketers, Mobile Attribution]
  labels: [Advertisers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2021-07-25T11:31:06Z'
  edited_at: '2025-10-31T14:48:44Z'
---
AppsFlyer uses Google Play Auto Install (PAI) to attribute installs to preload campaigns, where marketers contract with mobile carriers, and app discovery partners to preload their app at the time the device is first turned on by the user. 

> 📘 Note
>
> This attribution method differs from [APK preinstall attribution](/docs/appsflyer-factory-preinstall-using-manifest-android).

## PAI preload attribution

In preload campaigns, Original Device Manufacturers (OEMs), mobile carriers, and app discovery partners preload apps on devices that get downloaded upon first device activation.

Preload campaigns allow advertisers to reach a potentially large audience without running online campaigns.

Google Play Auto Install (PAI) (one of three preload attribution methods) provides marketers with an accurate and privacy-preserving mechanism to measuring the performance of preload campaigns. This method provides marketers with deterministic attribution results and simultaneously ensures that user privacy is preserved since attribution is performed via referrer matching with a Google Play referrer generated independently of the device and user identifiers.

AppsFlyer gives the highest priority to preload attribution. This means that if a user engages with other campaigns before opening the app for the first time, the preload campaign is still awarded the attribution. Other engagements are regarded as assisted installs.

> 📘 Note
>
> The Preload Equal Attribution Priority setting does not apply to Google PAI.

### Flow

1. A new device is activated for the first time, and predefined apps are automatically installed on it from Google Play according to rules set by the preload partner.
2. The user launches a preloaded app for the first time.
3. The AppsFlyer SDK queries the Google Play referrer API.
4. AppsFlyer attributes are based on the data retrieved.

<Image src="https://files.readme.io/c7f02a0a6637e9c73e9a39f97e71d5d37d8d2712b458735cd87b4b245ad0fccb-small-4404791877649.png" alt="PAI-attribution-flow_en-us.png" />

### Data availability

Google Play Auto Install (PAI) preload performance data is available in:

- The Overview dashboard and in aggregate reports, aggregated at the preload partner (media source) and campaign levels.
- Raw data reports.

Raw data includes the following fields:

- Media\_source = Partner ID
- Match\_type = preload\_pai
- Campaign\_name = preload campaign by 

### Set up Google Play Auto Install (PAI) preload attribution

**To set up PAI preload attribution:**

1. In AppsFlyer, from the side menu, select **Collaborate** \> **Active Integrations**.
2. Select the preload partner.
3. Turn on **Preload attribution**.
4. Set the **Preload lookback window** duration.

> 📘 Note
>
> Google stores referrer data for up to 90 days. Set the PAI lookback window to 90 days or less. Although the UI allows up to 180 days, data beyond 90 days isn’t available from Google.

5. Click **Save Integration**.
6. Let the preload partner know that you are ready to attribute their campaigns.

### Partners supporting Google Play Auto Install (PAI) preload campaigns

| Partner | PID |
| --- | --- |
| Xiaomi | xiaomipai\_int |
| Transsion | shalltrypai\_int |
| Oppo | oppopaipreinstall\_int |
| Vivo | vivootapreload\_int |
| TCL | tclpai\_int |
| Motorola | motorola\_int |
| MITV | mitvpai\_int |
| ZTE | ztepai\_int |
| Lenovotab | lenovotabpai4p\_int |
| KDDI Pre-Install | kddipai\_int |

> 📘 Note
>
> Agencies can't enable preload campaigns for their clients.

## Postbacks for preload partners

As part of their integration with AppsFlyer, preload partners define the content and endpoints of postbacks sent to them by AppsFlyer.

When included in a postback, macros contain user-relevant data. Supported macros are listed in the following table:

- **Source**: Indicates where the data originates from:
  - **SDK**: AppsFlyer SDK embedded in the app or server-to-server API.
  - **AppsFlyer**: After processing by AppsFlyer.

| Postback macro for preload partners (parameter name) | Source | Description |
| --- | --- | --- |
| app\_name | SDK | App name set by the advertiser |
| country\_code | AppsFlyer | Country Code using ISO 3166 (alpha-2) Example: US, CN. |
| install\_time | SDK | Install timestamp |
| language | SDK | Language (locale) reported by the device and set by the device OS. |
| app\_id | SDK | Unique app identifier in Appsflyer |
| app\_version | SDK | App version set by the app developer in the app code |
| device\_type | SDK | The commercial model name of the device. Example: SM-GM284 or iPhone7 |
| os\_version | SDK | Device operating system version |

#### Postback example

```http
HTTPhttp://YourCompanyDomain.com?pid=(preinstall_partner)&app_name=(app-name)&app_id=(app-id)&install_time=(install-unix-ts)
```
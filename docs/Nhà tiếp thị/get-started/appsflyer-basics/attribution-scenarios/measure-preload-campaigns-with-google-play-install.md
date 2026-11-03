---
title: Measure preload campaigns with Google Play Install
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-07-25T11:31:06Z'
  edited_at: '2025-10-31T14:48:44Z'
  id: 4404557237649
  locale: en-us
  section: Attribution scenarios
  section_id: 6551328497041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4404557237649-Measure-preload-campaigns-with-Google-Play-Install
---
> **At a glance:** AppsFlyer uses Google Play Auto Install (PAI) to attribute installs to preload campaigns, where marketers contract with mobile carriers, and app discovery partners to preload their app at the time the device is first turned on by the user. **Note**: This attribution method differs from <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-factory-preinstall-using-manifest-android">APK preinstall attribution</Anchor>.

## PAI preload attribution

In preload campaigns, Original Device Manufacturers (OEMs), mobile carriers, and app discovery partners preload apps on devices that get downloaded upon first device activation.

Preload campaigns allow advertisers to reach a potentially large audience without running online campaigns.

Google Play Auto Install (PAI) (one of three preload attribution methods) provides marketers with an accurate and privacy-preserving mechanism to measuring the performance of preload campaigns. This method provides marketers with deterministic attribution results and simultaneously ensures that user privacy is preserved since attribution is performed via referrer matching with a Google Play referrer generated independently of the device and user identifiers.

AppsFlyer gives the highest priority to preload attribution. This means that if a user engages with other campaigns before opening the app for the first time, the preload campaign is still awarded the attribution. Other engagements are regarded as assisted installs.

> 📘 **Note**
>
> The Preload Equal Attribution Priority setting does not apply to Google PAI.

### Flow

1. A new device is activated for the first time, and predefined apps are automatically installed on it from Google Play according to rules set by the preload partner.
2. The user launches a preloaded app for the first time.
3. The AppsFlyer SDK queries the Google Play referrer API.
4. AppsFlyer attributes are based on the data retrieved.

![PAI-attribution-flow_en-us.png](https://files.readme.io/c7f02a0a6637e9c73e9a39f97e71d5d37d8d2712b458735cd87b4b245ad0fccb-small-4404791877649.png)

### Data availability

Google Play Auto Install (PAI) preload performance data is available in:

* The Overview dashboard and in aggregate reports, aggregated at the preload partner (media source) and campaign levels.
* Raw data reports.

Raw data includes the following fields:

* Media\_source = Partner ID
* Match\_type = preload\_pai
* Campaign\_name = preload campaign by `<preloadpartner ID>`

### Set up Google Play Auto Install (PAI) preload attribution

**To set up PAI preload attribution:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.
2. Select the preload partner.
3. Turn on **Preload attribution**.
4. Set the **Preload lookback window** duration. 

   > 📘 **Note**
   >
   > Google stores referrer data for up to 90 days. Set the PAI lookback window to 90 days or less. Although the UI allows up to 180 days, data beyond 90 days isn’t available from Google.

5. Click **Save Integration**.
6. Let the preload partner know that you are ready to attribute their campaigns.

### Partners supporting Google Play Auto Install (PAI) preload campaigns

<table><thead><tr><th rowspan="2">Partner</th><th rowspan="2">PID</th></tr></thead><tbody><tr><td><p>Xiaomi</p></td><td><span>xiaomipai_int</span></td></tr><tr><td><p>Transsion</p></td><td><span>shalltrypai_int</span></td></tr><tr><td><p>Oppo</p></td><td><span>oppopaipreinstall_int</span></td></tr><tr><td><p>Vivo</p></td><td><span>vivootapreload_int</span></td></tr><tr><td><p>TCL</p></td><td><span>tclpai_int</span></td></tr><tr><td><p>Motorola</p></td><td><span>motorola_int</span></td></tr><tr><td><p>MITV</p></td><td><span>mitvpai_int</span></td></tr><tr><td><p>ZTE</p></td><td><span>ztepai_int</span></td></tr><tr><td><p>Lenovotab</p></td><td><span>lenovotabpai4p_int</span></td></tr><tr><td><p>KDDI Pre-Install</p></td><td><span>kddipai_int</span></td></tr></tbody></table>

> 📘 **Note**
>
> Note: Agencies can't enable preload campaigns for their clients.

## Postbacks for preload partners

As part of their integration with AppsFlyer, preload partners define the content and endpoints of postbacks sent to them by AppsFlyer.

When included in a postback, macros contain user-relevant data. Supported macros are listed in the following table:

* **Source**: Indicates where the data originates from:
  * **SDK**: AppsFlyer SDK embedded in the app or server-to-server API.
  * **AppsFlyer**: After processing by AppsFlyer.

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
http://YourCompanyDomain.com?pid=(preinstall_partner)&app_name=(app-name)&app_id=(app-id)&install_time=(install-unix-ts)
```

<div data-zendesk-anchors="h_01HEJG4FHSGJDZ77Y281F7SG4R=pai-preload-attribution h_01K8XBQ3YKJ8KBMPMAAMBZP25E=note pai-preload-attribution-flow=flow h_01HEJG4FHSF8X1TEMMNJBYP71Z=flow campaign-performance-data-availability=data-availability h_01HEJG4FHSCMPJM5TRNSPNDHVN=data-availability run-preload-referrer-campaigns=set-up-google-play-auto-install-pai-preload-attribution h_01HEJG4FHS7E5JZT2BBYG2BNEK=set-up-google-play-auto-install-pai-preload-attribution h_01K8XBJ9EJ38ST3KAFF879ZQ1H=note-1 partners-supporting-preload-referrer-campaigns=partners-supporting-google-play-auto-install-pai-preload-campaigns h_01HEJG4FHSNEGR7R9VCSDT9TSZ=partners-supporting-google-play-auto-install-pai-preload-campaigns h_01K8XBVZJGG59K3XJ8R346X9FH=note-2 h_01HEJG4FHSKD7DY6W7W65YBMGN=postbacks-for-preload-partners preload-postback-example=postback-example h_01HEJG4FHSBFB456Z752HFC8KN=postback-example" />

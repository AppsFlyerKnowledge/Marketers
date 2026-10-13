---
title: "Share ad revenue data with partners"
excerpt: "Allow partners to receive ad revenue information from mediation networks so they can optimize their user acquisition (UA) campaigns. Note : This requires an ROI360 Advanced subscription."
x-zendesk:
  id: 24100803679761
  url: https://support.appsflyer.com/hc/en-us/articles/24100803679761-Share-ad-revenue-data-with-partners
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Revenue analysis
  section_id: 6551069075089
  position: 5
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-michael-talapov, Marketers, ROI360]
  labels: [Premium, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2024-04-11T11:04:45Z'
  edited_at: '2026-09-15T11:11:27Z'
---
## About sharing ad revenue data with partners

You can allow ad networks responsible for user acquisition to receive ad revenue data from mediation networks. The partners can then use the information to optimize their UA campaigns.

Partners can receive ad revenue data via either:

* [UA signals for ad networks](#ua-signals-for-ad-networks)
* [Ad revenue postbacks for ad networks](#ad-revenue-event-postbacks-for-ad-networks)

The following table compares the 2 ad-revenue-data-sharing solutions. 

| Ad revenue data-sharing solution | Data freshness | Use case | Integration type required | Subscription type required |
| --- | --- | --- | --- | --- |
| UA signals | Daily | Accurate and complete data, commonly used for D3 and D7 optimization. | * Impression-level or device-level<br />* If both are configured, device-level data is sent | ROI360 Advanced |
| Postbacks | Realtime | Fresh data, commonly used for D0 and D1 optimization. | Impression-level | ROI360 Advanced |

## Procedures

### UA signals for ad networks

You may want to work with ad networks that can receive UA signals. This means that ad networks responsible for user acquisition can receive ad revenue data from mediation networks and use it to optimize their customers' UA campaigns.

**To send UA signals to an ad network**:

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active integrations***.*
2. Select the integrated partner.
3. Go to the **Integration** tab.
4. Verify that **Activate Partner** is on. If not, data isn't shared.
5. Go to the **Permissions** tab.
6. Turn on **Ad network permissions**.
7. Turn on **Access ad revenue raw data (UA signals)**.
8. In **Sending option**, select whether to send data for ad revenue only from this partner (**This partner only**), or for ad revenue from all media sources (**All media sources, including organic**). **Note**: When **All media sources including organic** is selected, data for other partners doesn't include attribution data.
9. Click **Save Settings**.
10. Contact the ad network:
    1. Notify it that you've granted the permissions.
    2. Tell them to follow [their instructions](/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report) to receive the report.

**List of mediation partners that can send UA signals to ad networks:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Unity LevelPlay mediation (formerly ironSource)
* Admost
* Tradplusad
* Yandex
* Custom mediation

### Ad revenue event postbacks for ad networks

You can configure ad revenue postbacks for ad networks. This means that ad networks responsible for user acquisition can receive real-time data from mediation networks regarding ad revenue and use it to optimize their customers' UA campaigns. 

> 📘 **Important!**
>
> * Ad revenue event postbacks to ad networks only work with Impression-level via SDK and Impression-level (via SDK) with device-level (via server-to-server (S2S) API) ad revenue [integration types](/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution). This means your developer must integrate the [AppsFlyer ad revenue SDK API](/docs/integrate-the-roi360-ad-revenue-sdk-api).
> * While you can send ad revenue postbacks to specific partners, we recommend validating how partners use the data before starting the integration.

**To set up ad revenue event postbacks**:

1. Search for and select your partner, either [from the marketplace](/docs/partner-integrations#manage-existing-integrations) or from the **Collaborate** > **Partner Integrations** > **Active** **Integrations** page.
2. In the **Integration** tab, scroll down and turn on **In-app event postbacks**.
3. Select the AppsFlyer event af\_ad\_revenue. **Note**: Some ad network integrations have the option to **Select all events**. Don't use this option, as it excludes af\_ad\_revenue events.
4. Map it to the ad network event as follows:

   

| Ad network | Event to map af\_ad\_revenue to | Screenshot |
| --- | --- | --- |
| Google Ads | ad\_impression | ![Google Ads ad_impression event mapping](https://files.readme.io/883dd04563027d722e7e8e76a50f813c8a955db827cbb92e94cdc650ab7b234d-50421403523601.png) |
| Unity Ads | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Moloco | No mapping needed |  |
| Mintegral | No mapping needed |  |
| Smadex | No mapping needed |  |
| Mistplay | No mapping needed |  |
| Meta Ads | fb\_mobile\_purchase, for iOS apps  <br />or  <br />Adimpression, for Android apps  <br />[Meta Ads in-app event mapping guide](/docs/meta-ads-in-app-event-mapping#mapping-ad-revenue-data-for-campaign-optimization). | [![revenue-mapping-meta2.jpg](https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg)](https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg) |
| TikTok For Business - Advanced SRN | ImpressionLevelAdRevenue | [![](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png)](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png) |
| Aura from Unity | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| SingleTap by Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Persona.ly RTB | ad-revenue | [![](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png)](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png) |
| Bigo | ad\_watch | [![](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png)](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png) |
| Appier | No mapping needed |  |
| Bidease | No mapping needed |  |
| MAF | No mapping needed |  |

5. Select a **for user from** sending option for the event:
   * **This partner only**: Send postbacks only when the event is attributed to this partner, meaning the user who performed it came from this partner.
   * **All media sources including organic**: Send postbacks for events attributed to any partner and for organic events, meaning the user who performed it came from any media source. **Note**: When All media sources including organic is selected, postbacks for other partners don't contain attribution data.
6. Click **Save integration**.

**List of mediation partners that can send impression-level ad revenue events to ad networks:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Unity LevelPlay mediation (formerly ironSource)
* Admost
* Tradplusad
* Yandex
* Custom mediation

## Additional information

### List of ad networks that can receive UA signals and postbacks

The following table lists the ad networks that can receive ad revenue UA signals and postbacks from mediation networks.

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th rowspan="2">Ad network (partner)</th><th colspan="2">Supports</th></tr><tr><th>UA signals</th><th>Postbacks</th></tr></thead><tbody><tr><td>RZR (formerly Aarki)</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>AdAction</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Adaction3</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Adamobi</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Adikteev (Trademob)</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Adjoe</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Adonco</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Adshow</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Almedia GmbH</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Appgrowth</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Appier</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Apprainbow</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Aura from Unity</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Avow OEM</td><td> </td><td><span><strong>✓</strong></span></td></tr><tr><td>ayeT-Studios</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Betop</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Bidswave</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Bidease</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Bigo</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Brandscale</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Buzzvil</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Chameleostudios</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Chartboost</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Churney</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Datawave</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Digital Turbine</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>DLab</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Ecomonline</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Etusdigital</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Exmox</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Fluent</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Foregon</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>GNA Company</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Google Ads</td><td> </td><td><span><strong>✓</strong></span></td></tr><tr><td>Greedygame</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Happimobi</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Hybrid</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Inflecto</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Irismedia</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Kashkick</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Kwai ads</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Lacuna</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Lambadapp</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Leadidadmonster</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Lifestreet</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Liftoff</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>MAF</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Melodong</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Meta Ads</td><td><span>-</span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Miniclip</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Mintegral</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Mistplay</td><td><span>-</span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Mobrand</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Moloco</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Motive</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Mpnd</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Msla</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Muvmobile</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>NewsBreak</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Nexamob</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Nftdroper</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Nsofmedia</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Performadlive</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Persona.ly RTB</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Pitatroas</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Playgap</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Rebornads</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Remerge</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>RTBhouse</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Runfuns</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>SayGames LTD</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Scmobi</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Shalltry</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Shareit</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>SingleTap by Digital Turbine</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Smadex</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Surgex</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Tapjoy</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Targetmedia</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>TaurusX</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Thepurpleline</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>TikTok for Business</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Trade Desk</td><td> </td><td><span><strong>✓</strong></span></td></tr><tr><td>Transsion</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Truemoney</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Tyrads</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Unity Ads</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Unity CTV</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Vivo Global </td><td> </td><td><span><strong>✓</strong></span></td></tr><tr><td>Voodoo</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Vungle</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>VYBS</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Yandex</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Yeahmobi</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>YouAppi</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Xiaomi Global</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>YSO Network</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>Z2A Digital</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Zoyo</td><td><span><strong>✓</strong></span></td><td>-</td></tr></tbody></table>

### Traits and limitations

| Trait | Description |
| --- | --- |
| Conversion types | Both UA signals and ad revenue postbacks support data about all conversion types: installs, re-attributions, re-engagements, and reinstalls. |
| Agency postback permissions | Agencies cannot configure ad revenue postbacks |
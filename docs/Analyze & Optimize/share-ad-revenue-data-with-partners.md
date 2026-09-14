---
title: "Share ad revenue data with partners"
excerpt: "Allow user acquisition partners to receive ad revenue data from mediation networks to optimize their campaigns."
---
At a glance: Allow partners to receive ad revenue information from mediation networks so they can optimize their user acquisition (UA) campaigns.

> 📘 ROI360 Advanced Subscription
>
> Sharing ad revenue data with partners requires an ROI360 Advanced subscription.

## About sharing ad revenue data with partners

You can allow ad networks responsible for user acquisition to receive ad revenue data from mediation networks. The partners can then use the information to optimize their UA campaigns.

Partners can receive ad revenue data via either:

- [UA signals for ad networks](#ua-signals-for-ad-networks)
- [Ad revenue postbacks for ad networks](#ad-revenue-event-postbacks-for-ad-networks)

The following table compares the 2 ad-revenue-data-sharing solutions.

| Ad revenue data-sharing solution | Data freshness | Use case | Integration type required | Subscription type required |
| --- | --- | --- | --- | --- |
| UA signals | Daily | Accurate and complete data, commonly used for D3 and D7 optimization. | - Impression-level or device-level<br>- If both are configured, device-level data is sent | ROI360 Advanced |
| Postbacks | Realtime | Fresh data, commonly used for D0 and D1 optimization. | Impression-level | ROI360 Advanced |

## Procedures

### UA signals for ad networks

You may want to work with ad networks that can receive UA signals. This means that ad networks responsible for user acquisition can receive ad revenue data from mediation networks and use it to optimize their customers' UA campaigns.

**To send UA signals to an ad network**:

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active integrations**.
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
    2. Tell them to follow [their instructions](https://support.appsflyer.com/hc/articles/4402898251409#enable-the-ad-revenue-report) to receive the report.

**List of mediation partners that can send UA signals to ad networks:**

- Applovin Max
- Google AdMob
- Appodeal
- Chartboost
- Fyber
- Tapdaq
- Topon
- Unity
- Unity LevelPlay mediation (formerly ironSource)
- Admost
- Tradplusad
- Yandex
- Custom mediation

### Ad revenue event postbacks for ad networks

You can configure ad revenue postbacks for ad networks. This means that ad networks responsible for user acquisition can receive real-time data from mediation networks regarding ad revenue and use it to optimize their customers' UA campaigns.

> 🚧 Important requirements
>
> - Ad revenue event postbacks to ad networks only work with Impression-level via SDK and Impression-level (via SDK) with device-level (via server-to-server (S2S) API) ad revenue [integration types](https://support.appsflyer.com/hc/articles/217490046-Ad-revenue-attribution-guide#integration-types-for-ad-revenue-attribution). This means your developer must integrate the [AppsFlyer ad revenue SDK API](https://support.appsflyer.com/hc/articles/4416353506833).
> - While you can send ad revenue postbacks to specific partners, we recommend validating how partners use the data before starting the integration.

**To set up ad revenue event postbacks**:

1. Search for and select your partner, either [from the marketplace](https://support.appsflyer.com/hc/articles/9960361873809#manage-existing-integrations) or from the **Collaborate** > **Active Integrations** page.
2. In the **Integration** tab, scroll down and turn on **In-app event postbacks**.
3. Select the AppsFlyer event `af_ad_revenue`. **Note**: Some ad network integrations have the option to **Select all events**. Don't use this option, as it excludes `af_ad_revenue` events.
4. Map it to the ad network event as follows:

| Ad network | Event to map `af_ad_revenue` to | Screenshot |
| --- | --- | --- |
| Google Ads | ad\_impression | <Image src="https://support.appsflyer.com/hc/article_attachments/50421403523601" alt="Google Ads ad_impression event mapping" /> |
| Unity Ads | ad\_revenue | |
| Moloco | No mapping needed | |
| Mintegral | No mapping needed | |
| Smadex | No mapping needed | |
| Mistplay | No mapping needed | |
| Meta Ads | fb\_mobile\_purchase, for iOS apps<br />or<br />Adimpression, for Android apps<br />[Meta Ads in-app event mapping guide](/docs/meta-ads-in-app-event-mapping#mapping-ad-revenue-data-for-campaign-optimization). | <Image src="https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg" alt="revenue-mapping-meta2.jpg" /> |
| TikTok For Business - Advanced SRN | ImpressionLevelAdRevenue | |
| Aura from Unity | ad\_revenue | |
| Digital Turbine | ad\_revenue | |
| SingleTap by Digital Turbine | ad\_revenue | |
| Persona.ly RTB | ad-revenue | |
| Bigo | ad\_watch | |
| Appier | No mapping needed | |
| Bidease | No mapping needed | |
| MAF | No mapping needed | |

5. Select a **for user from** sending option for the event:
   - **This partner only**: Send postbacks only when the event is attributed to this partner, meaning the user who performed it came from this partner.
   - **All media sources including organic**: Send postbacks for events attributed to any partner and for organic events, meaning the user who performed it came from any media source. **Note**: When All media sources including organic is selected, postbacks for other partners don't contain attribution data.
6. Click **Save integration**.

**List of mediation partners that can send impression-level ad revenue events to ad networks:**

- Applovin Max
- Google AdMob
- Appodeal
- Chartboost
- Fyber
- Tapdaq
- Topon
- Unity
- Unity LevelPlay mediation (formerly ironSource)
- Admost
- Tradplusad
- Yandex
- Custom mediation

## Additional information

### List of ad networks that can receive UA signals and postbacks

The following table lists the ad networks that can receive ad revenue UA signals and postbacks from mediation networks.

| Ad network (partner) | Supports UA signals | Supports Postbacks |
| --- | --- | --- |
| RZR (formerly Aarki) | - | **✓** |
| AdAction | **✓** | - |
| Adaction3 | - | **✓** |
| Adamobi | **✓** | - |
| Adikteev (Trademob) | **✓** | - |
| Adjoe | **✓** | **✓** |
| Adonco | **✓** | - |
| Adshow | **✓** | - |
| Almedia GmbH | - | **✓** |
| Appgrowth | - | **✓** |
| Appier | **✓** | **✓** |
| Apprainbow | **✓** | - |
| Aura from Unity | **✓** | **✓** |
| Avow OEM | | **✓** |
| ayeT-Studios | - | **✓** |
| Betop | **✓** | - |
| Bidswave | **✓** | - |
| Bidease | - | **✓** |
| Bigo | - | **✓** |
| Brandscale | **✓** | - |
| Buzzvil | - | **✓** |
| Chameleostudios | **✓** | - |
| Chartboost | **✓** | - |
| Churney | - | **✓** |
| Datawave | **✓** | - |
| Digital Turbine | - | **✓** |
| DLab | **✓** | - |
| Ecomonline | **✓** | - |
| Etusdigital | **✓** | - |
| Exmox | - | **✓** |
| Fluent | **✓** | - |
| Foregon | **✓** | - |
| GNA Company | **✓** | - |
| Google Ads | | **✓** |
| Greedygame | **✓** | **✓** |
| Happimobi | **✓** | - |
| Hybrid | **✓** | - |
| Inflecto | **✓** | - |
| Irismedia | **✓** | - |
| Kashkick | - | **✓** |
| Kwai ads | - | **✓** |
| Lacuna | - | **✓** |
| Lambadapp | **✓** | - |
| Leadidadmonster | **✓** | - |
| Lifestreet | **✓** | - |
| Liftoff | **✓** | - |
| MAF | **✓** | **✓** |
| Melodong | **✓** | - |
| Meta Ads | - | **✓** |
| Miniclip | - | **✓** |
| Mintegral | - | **✓** |
| Mistplay | - | **✓** |
| Mobrand | **✓** | - |
| Moloco | **✓** | **✓** |
| Motive | **✓** | - |
| Mpnd | **✓** | - |
| Msla | **✓** | - |
| Muvmobile | **✓** | - |
| NewsBreak | - | **✓** |
| Nexamob | **✓** | - |
| Nftdroper | **✓** | - |
| Nsofmedia | **✓** | - |
| Performadlive | **✓** | - |
| Persona.ly RTB | **✓** | **✓** |
| Pitatroas | **✓** | - |
| Playgap | - | **✓** |
| Rebornads | **✓** | - |
| Remerge | **✓** | - |
| RTBhouse | **✓** | - |
| Runfuns | **✓** | - |
| SayGames LTD | - | **✓** |
| Scmobi | **✓** | - |
| Shalltry | **✓** | - |
| Shareit | **✓** | - |
| SingleTap by Digital Turbine | - | **✓** |
| Smadex | **✓** | **✓** |
| Surgex | - | **✓** |
| Tapjoy | **✓** | **✓** |
| Targetmedia | **✓** | - |
| TaurusX | - | **✓** |
| Thepurpleline | **✓** | - |
| TikTok for Business | **✓** | **✓** |
| Trade Desk | | **✓** |
| Transsion | - | **✓** |
| Truemoney | **✓** | - |
| Tyrads | - | **✓** |
| Unity Ads | **✓** | **✓** |
| Unity CTV | **✓** | **✓** |
| Vivo Global | | **✓** |
| Voodoo | - | **✓** |
| Vungle | **✓** | - |
| VYBS | - | **✓** |
| Yandex | **✓** | - |
| Yeahmobi | **✓** | - |
| YouAppi | - | **✓** |
| Xiaomi Global | - | **✓** |
| YSO Network | - | **✓** |
| Z2A Digital | **✓** | - |
| Zoyo | **✓** | - |

### Traits and limitations

| Trait | Description |
| --- | --- |
| Conversion types | Both UA signals and ad revenue postbacks support data about all conversion types: installs, re-attributions, re-engagements, and reinstalls. |
| Agency postback permissions | Agencies cannot configure ad revenue postbacks |
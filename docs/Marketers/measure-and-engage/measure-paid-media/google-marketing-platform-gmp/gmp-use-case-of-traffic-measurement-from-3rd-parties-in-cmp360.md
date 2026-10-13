---
title: "GMP use case of traffic measurement from 3rd parties in CMP360"
excerpt: "Learn how to buy traffic from third-party media sources in CM360 and measure mobile app conversions originating from this source both in AppsFlyer and CM360."
---
**At a glance**: Buy traffic from third-party media sources in CM360 and measure mobile app conversions originating from this source both in AppsFlyer (attributed to the third-party media source) and CM360.

![](https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png)

## Measurement of CM360 with non-DV360 third-party media sources

Google Marketing Platform (GMP) brings together your advertising and analytics to help you make quality customer connections, surface deeper insights, and drive better marketing results.

In the context of AppsFlyer, the standard DV360 SRN integration (dv360\_int) with GMP allows for easy attribution of DV360 campaigns **managed in CM360**, without the need for attribution links. AppsFlyer attributes installs and re-engagements to DV360 through the DV360 SRN claims using the integration.

> 📘 **Note**
>
> * AppsFlyer attributes DV360 campaigns managed in CM360 via the standard DV360 SRN integration, without the need for attribution links. Installs and re-engagements are attributed to DV360 via DV360 SRN claims using the integration. If you're running DV360 campaigns via CM360, refer to the [DV360 integration guide](/docs/google-marketing-platform-display-video-360-dv360-integration).
> * If the third-party media source is an SRN, AppsFlyer recommends not using the integration described in this article to avoid conflicts when conversions from the same partner are reported via two different integrations. For example, if the [Meta ads SRN integration](/docs/meta-ads-integration-setup) is enabled in AppsFlyer but CM360 is also utilized to report on Meta ads traffic (facebook\_int) using the method described in this article, conversions may be reported by both Meta ads and CM360, with CM360 capturing some of the conversions that would have been claimed by the main Meta ads integration.

### Measuring third-party traffic running via CM360

The following steps are recommended for measuring third-party media sources managed via CM360, in both AppsFlyer and CM360:

#### Step 1: Integrate the third-party media source and GMP with AppsFlyer

To ensure attribution by AppsFlyer:

* Make sure the third-party media source is integrated and activated, as it receives attribution rather than CM360. Activating GMP (dv360\_int) is only necessary to ensure data is sent back to CM360.
* If the third-party media source isn’t integrated with AppsFlyer, it should be handled as a custom or owned media source. In this case, implement an attribution link with any PID (media source) value.

> 📘 **Note**
>
> For Agency attribution: AppsFlyer requires the agency's name for install attribution. Include it using the `af_prt` parameter in the attribution link or through the referrer in the URL.

#### Step 2: Create the required attribution links

1. [Create a CM360 "tracking ad"](https://support.google.com/campaignmanager/answer/3040965?hl=en&ref_topic=2826011)
2. Create an attribution link in AppsFlyer:
   * The attribution link should contain the actual media source that you intend to report on, which should be a third-party media source, not GMP. For example, if the third-party media source is Rocketfuel, use `pid=rocketfuel_int` and not `pid=dv360_int`. [Learn more](/docs/retargeting-attribution-guide).
   * If your goal is to **re-engage existing users by opening the app** when they click the ad link (rather than being redirected to the App Store), **use the URI scheme method** for deep linking. This requires configuring the CM360 link with the following:
     * The `af_dp` parameter set to your app's URI scheme.
     * The `af_force_deeplink=true` parameter to explicitly force deep linking behavior.
3. Append the AppsFlyer attribution link to the CM360 link:

   Android iOS

   ```
   https://ad.doubleclick.net/ddm/trackclk/N736113.127733/B202683.204586115;
   dc_trk_aid=404426918;dc_trk_cid=92566356;dc_lat=;dc_rdid=13******-****-****-****-54**********
   ?https://app.appsflyer.com/com.example?pid=rocketfuel_int
   &c=campaign_name&advertising_id=13******-****-****-****-54**********
   ```

   ```
   https://ad.doubleclick.net/ddm/trackclk/N736113.127733/B202683.204586115;
   dc_trk_aid=404426918;dc_trk_cid=92566356;dc_lat=;dc_rdid=13******-****-****-****-54**********
   ?https://app.appsflyer.com/com.example?pid=rocketfuel_int
   &c=campaign_name&idfa=13******-****-****-****-54**********
   ```

   * See more about [iOS and Android attribution links structure and parameters](/docs/about-link-structure-and-parameters?)
   * See more about [CTV, Console, and PC attribution links structure and parameters](/docs/ctv-pc-and-console-platform-direct-attribution-links)

#### Step 3: Set in-app event postbacks

To ensure CM360 receives postbacks for events originating from these campaigns, it's advised to set in-app event postbacks in dv360\_int to “All media sources, including organic”.

### Using the attribution link

Once you have the attribution link, make sure it is used while running ads on your intended third-party media source. When an install occurs, AppsFlyer attributes the install to the selected third-party media source and notifies the partner via postbacks. AppsFlyer then lets CM360 know about the install or any following in-app event via the DV360 integration, as long as it's active.

The end result is an install or in-app event that's attributed to the media source, and also registered in DCM360.
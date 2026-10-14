---
title: "Luna Labs integration with AppsFlyer"
excerpt: "Luna Labs is an end-to-end platform that allows its customers to create, manage, and optimize playables and video ads."
x-zendesk:
  id: 360019465017
  url: https://support.appsflyer.com/hc/en-us/articles/360019465017-Luna-Labs-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 18
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Agencies]
  labels: [postbacks, integrated partner, Advertisers, Agencies, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-04-21T15:51:20Z'
  edited_at: '2026-06-16T09:38:55Z'
---
> 📘 **Important!**
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Luna Labs

**Prerequisite:** Before setting up the integration, make sure you contact the partner and open an account with them.

**New integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.
2. Select the relevant app.
3. Search for Luna Labs and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle. Keep it on as long as you work with Luna Labs.
5. Complete the configuration using the relevant tabs, as described below.

**Edit existing integration:**

In AppsFlyer, go to **Collaborate > Partner Integrations > Active integrations** tab, search for the partner, and make your changes.

## Integration

Use the Integration tab for the configuration. The remaining tabs are inactive.

> 📘 **Note**
>
> Luna Labs doesn't use its own attribution links. They get postbacks from ad networks that run campaigns with advertisers. Luna Labs only receives postbacks for their own creatives and only postbacks which include the `af_addpb=1` parameter and value. See further explanation below.

### Activate partner

On the **first visit** here, you need to turn on **Activate partner** to enable the setup of the integration tab's parameters. **The toggle must be on for as long as you work with the partner**.  
Learn more about [partner activation/deactivation](/docs/partner-activation-deactivation).

### Default postbacks

AppsFlyer can send automatic postbacks to Luna Labs following user installs.

**Note:** Luna Labs can receive postbacks only for their own creatives.

**To send postbacks to Luna Labs:**

1. Make sure that the ad network you are working with together with Luna Labs is activated and integrated with AppsFlyer.
2. Make sure that the ad network adds the parameter `af_addpb=1` to the attribution link sent to AppsFlyer and to Luna Labs by the ad network.  
   This parameter enables sending the postback to Luna Labs, and lets them know that the click came from their creative.
3. Select **Events attributed to any partner or organic**.

For example, if ad-network-X is working with a certain app (id1234567890), and wants to send postbacks to Luna Labs, then the URL should look like this:

```
https://app.appsflyer.com/id1234567890?pid=ad-network-X_int&af_siteid={ApplicationId}_{ApplicationName}&c={CampaignName}&af_adset={adgroup_name}&af_ad={CreativeName}&clickid={DynamicParameter}&af_addpb=1
```
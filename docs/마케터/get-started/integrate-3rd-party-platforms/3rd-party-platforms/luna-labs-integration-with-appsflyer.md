---
title: Luna Labs integration with AppsFlyer
metadata:
  keywords:
    - postbacks
    - integrated partner
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-04-21T15:51:20Z'
  edited_at: '2026-10-13T00:30:15Z'
  id: 360019465017
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/360019465017
---
> **At a glance:** Luna Labs is an end-to-end platform that allows its customers to create, manage, and optimize playables and video ads.

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

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
Learn more about <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">partner activation/deactivation</Anchor>.

### Default postbacks

AppsFlyer can send automatic postbacks to Luna Labs following user installs.

**Note:** Luna Labs can receive postbacks only for their own creatives.

**To send postbacks to Luna Labs:**

1. Make sure that the ad network you are working with together with Luna Labs is activated and integrated with AppsFlyer.
2. Make sure that the ad network adds the parameter `af_addpb=1` to the attribution link sent to AppsFlyer and to Luna Labs by the ad network.  
   This parameter enables sending the postback to Luna Labs, and lets them know that the click came from their creative.
3. Select **Events attributed to any partner or organic**.

For example, if ad-network-X is working with a certain app (id1234567890), and wants to send postbacks to Luna Labs, then the URL should look like this:

```http
https://app.appsflyer.com/id1234567890?pid=ad-network-X_int&af_siteid={ApplicationId}_{ApplicationName}&c={CampaignName}&af_adset={adgroup_name}&af_ad={CreativeName}&clickid={DynamicParameter}&af_addpb=1
```

<div data-zendesk-anchors="h_01H9FKCW1FJ2QCVVE6HEE640H9=important h_01HJR5M5C0P759S4X5SSJCY501=setting-up-luna-labs h_01H9FKCW1FE6JCY5FAFF3Y4TGH=integration h_01H9FKCW1FNPCF1M7SRWTMNDCW=note h_01H9FKCW1FV00605GYK498JZN9=activate-partner h_01H9FKCW1FGMA3FKAY5B9YCJVH=default-postbacks" />

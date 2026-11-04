---
title: Snapchat marketing partners setup
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-24T08:47:31Z'
  edited_at: '2026-09-15T11:22:07Z'
  id: 4417694142481
  locale: en-us
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4417694142481-Snapchat-marketing-partners-setup
---
> **At a glance:** Integrate with Snapchat marketing partners to measure campaigns you run with them. When configured, AppsFlyer sends postbacks to the configured Snapchat marketing partner.

<div id="setting-up-a-snapchat-marketing-partner" />

## Setting up a Snapchat Marketing Partner

Follow the steps below to configure your campaigns with any one of Snapchat Marketing Partners.

* Activate <Anchor target="_blank" href="/marketers/docs/snapchat-advanced-srn-integration-setup">Snapchat attribution</Anchor>.
* In the Snapchat **Business Manager** dashboard, copy the **Snap Account ID** highlighted below in green.

  ![snapchat-dashboard.png](https://files.readme.io/a0942bd27528d4a837edc6eb5d11338bf0622ddc42e382231a8f210aedad1424-50902448760337.png)

Once you have activated Snapchat and obtained the Snap Account ID, configure the Marketing Partner:

1. In AppsFlyer, from the side menu, select **Collaboration** > **Partner Integrations** > **Active Integrations.**
2. In the search box, enter the name of the specific partner, or 'Snapchat' to see the full list of Snapchat marketing partners.
3. Click the logo of the required partner to open the configuration window.
4. Enable **Activate partner**.
5. Paste the **Snap account ID** obtained from the Snapchat dashboard (with the hyphens) in the **Snap Account ID** field.
6. Click **Save**.

<div id="default-postbacks" />

### Default postbacks

AppsFlyer can send automatic install and re-engagement postbacks to partners. Use this section to define the **source of the users** that allow sending these postbacks. In some cases the source of users is predefined and cannot be changed:

![remerge2.png](https://files.readme.io/4f3f52b3610b3e3bcf0adc6e963f1f2c39cdb0b2de27569c890844aac477b3d0-50902448761873.png)

Select **Only events attributed to this partner** for events coming only from users attributed to this partner.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to this partner.

<div id="in-app-events" />

### In-app events

1. To send in-app event postbacks to the Snapchat marketing partner you're configuring, toggle the In-App Events Postback to **ON**.
2. Individually add the in-app events (SDK events) you want to send to the partner and <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#event-mapping">map them as required.</Anchor>

<div id="important" />

> 🚧 **Important!**
>
> Disabling attribution for Snapchat prevents sending postbacks to Snapchat Marketing Partners.

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/skan-interoperation-with-snapchat">Snapchat and AppsFlyer SKAdNetwork interoperation</Anchor>

<div data-zendesk-anchors="h_01HDNZAAS11ADG02FXNPSYYH69=setting-up-a-snapchat-marketing-partner h_01HDNZAAS1M2317CKQ13SP11KM=default-postbacks inapp-events=in-app-events h_01HDNZAAS1JZPHS32PNFFCR12A=in-app-events h_01HDNZAAS1PRWK6EVQTTV3YNQM=important h_01HDNZBZARD9E54VAFVSRQFWEH=see-also" />

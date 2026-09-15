---
title: "Vizio integration with AppsFlyer"
excerpt: "Integrate your Vizio Connected TV (CTV) app with AppsFlyer to receive attribution and event data for your campaigns on Vizio."
---
At a glance: Integrate your Vizio Connected TV (CTV) app (channel) with AppsFlyer to receive attribution and event data for your campaigns on Vizio.

## About Vizio CTV attribution

The Vizio SmartCast OS for streaming runs across all Vizio TVs.

CTV apps streaming on Vizio can integrate with AppsFlyer via API to receive attribution data and performance measurements about which sources (non-organic or organic) and paid campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The Vizio API integration supports:

- Vizio Smart TVs.
- CTV-to-CTV attribution and event recording. Meaning, attribution and recording of Vizio first app opens (the equivalent of installs) and events that occur on a user's Vizio device.

### Vizio attribution flow

<Image src="https://files.readme.io/f4ab4b6c9e045fe00b537814fa9f10746b525a5512e5805e62eb0c2e4c9a8615-6318406872337.png" alt="CTV attribution flow - Vizio" />

## Integration procedures

The following table lists the tasks required to integrate your Vizio CTV app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | - [Create an AppsFlyer account](https://www.appsflyer.com/get-started/)<br />- [Add account users with appropriate permissions](/docs/user-management)<br />- [Add your Vizio CTV app in AppsFlyer](/docs/adding-an-app-to-appsflyer) | Marketer |
| API integration with your app (via S2S) | [Integrate the AppsFlyer CTV API](https://dev.appsflyer.com/hc/reference/overview-4) into your CTV app with commands to report the following events to AppsFlyer.<br />- First opens<br />- In-app events<br />- Sessions<br />**Note**:<br />- Installs must be reported before in-app events and sessions.<br />- Send events using the API. Tell your developer which events to send.Verify that when you set up the API, you set up and map the events to send to AppsFlyer. <br />To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id) | App developer |
| Partner integration | Add Vizio as an ad network (integrated partner) in AppsFlyer:<br />1. [Activate partner](/docs/set-up-an-integrated-partner#a-activate-partner)<br />2. [Optional] Turn on **[View-through attribution](/docs/set-up-an-integrated-partner#e-install-attribution).** | Marketer |
| Link setup | [Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability) | Marketer/Data engineer |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| View-through attribution | Default is 24 hours |
| Cost data | Cost data must be sent via [Cost Import](/docs/import-cost-data) using the upload file by email method. |

<Cards>
  <Card title="CTV, PC, and console platform overview" href="/docs/ctv-pc-and-console-platform-attribution-concepts" icon="fa-solid fa-diagram-project">
    Learn more about the CTV, PC, and console platform overview.
  </Card>
</Cards>
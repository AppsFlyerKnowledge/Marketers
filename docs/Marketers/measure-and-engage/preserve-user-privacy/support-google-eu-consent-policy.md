---
title: "Support Google EU consent policy"
excerpt: "Learn how AppsFlyer helps marketers comply with the Digital Markets Act (DMA) and support Google's updated EU user consent policy."
x-zendesk:
  id: 22310731147153
  url: https://support.appsflyer.com/hc/en-us/articles/22310731147153-Support-Google-EU-consent-policy
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Preserve user privacy
  section_id: 6551440878097
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution, Agencies]
  labels: [Agencies, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2024-02-07T07:28:17Z'
  edited_at: '2026-08-14T10:58:57Z'
---
**At a glance:** AppsFlyer is helping marketers comply with the Digital Markets Act (DMA) and improve the value of their ads in Google. Find answers to frequently asked questions about compliance with the DMA and optimizing ad value.

## Overview

Google is updating its [EU user consent policy](https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA) in preparation for the enforcement of the [Digital Markets Act](https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en)(DMA). As a Google [App Attribution Partner](https://ads.google.com/lp/appcampaigns/attribution/), AppsFlyer is adapting to the policy changes while empowering advertisers to get the most out of their ads in Google. The updated policy is in effect as of March 6, 2024.

## Relevant integrations and continued use of Google features

### Which integrations are involved?

The following integrations are relevant to Google's new EU consent policy:

- Google Ads (`googleadwords_int`)
- GMP DV360 (`dv360_int`)

If end users of your apps via these integrations are based in the European Economic Area (EEA), make sure to take the necessary steps to comply with Google's new EU consent policy.

> 📘 Note
>
> The [Legacy] Google Marketing Platform DV360/CM integration (`doubleclick_int`) will be deprecated and not supported under Google's new EU consent policy. If you're using this integration, we recommend [transitioning to the new DV360 integration (dv360_int)](/docs/bulletin-google-marketing-platform-gmp-integration-transition).

### What should be done to continue using Google's features

Marketers need to obtain end-user consent in the EEA to continue using Google Ads and GMP DV360 features related to measurement, ad personalization, and remarketing.

## Updating the AppsFlyer SDK

### Steps needed for implementing consent data via the AppsFlyer SDK

The AppsFlyer SDK (Android - v6.13.0+, iOS - v6.13.1+) can send the necessary consent data with each event to meet Google's requirements.

- [Upgrade your SDK](https://dev.appsflyer.com/hc/docs/sdk-installation) to the latest version (Android - v6.13.0+, iOS - v6.13.1+). Applicable to Android or iOS apps.
- Once the SDK is upgraded, [see here](/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance) for implementation instructions for supporting the DMA.

## Sending consent data

### Send consent data to AppsFlyer

Marketers have two options to send the required consent data to AppsFlyer:

- [**Directly via the SDK**](/docs/support-google-eu-consent-policy#updating-the-appsflyer-sdk) **or an S2S (Server-to-Server) API:** Marketers can send the consent data directly to AppsFlyer using the SDK. Applicable to Android or iOS apps.
- **Via TCF Strings:** Marketers who currently use or plan to use a Consent Management Platform (CMP) can send the data fields through standard IAB (Interactive Advertising Bureau) Transparency and Consent Framework (TCF) strings (TCF V2.2/2.3). Make sure to include the Google vendor ID (755) in the list of consented vendors.

AppsFlyer then enables customers to transmit the consent signals to Google. However, it's important to note that AppsFlyer does not collect, alter, or control end-user consent. Marketers working with Google are responsible for collecting the necessary consent fields.

<Embed title="How to send consent data to AppsFlyer" typeOfEmbed="iframe" url="https://www.wistia.com/embed/iframe/0tnlyre8ai" />

### Consent values AppsFlyer sends to Google

End-user consent values are sent to Google for the relevant AppsFlyer integrations (`googleadwords_int` and `dv360_int`) using the following fields:

| AppsFlyer field | Google field (1) | Values | Field explained |
| --- | --- | --- | --- |
| gdpr_applies | eea | true/false (2) | Does DMA apply to this user? |
| ad_personalization_enabled | ad_personalization | true/false | Did the user give Google consent to use their data for personalized advertising? |
| ad_user_data_enabled | ad_user_data | true/false | Did the user give consent to send their user data to Google? |

1. See [Google's definition for each field](https://support.google.com/tagmanager/answer/13802165?hl=en).
2. When DMA doesn't apply to the user, AppsFlyer suggests refraining from sending consent fields other than `gdpr_applies=false`

### Sending consent data—FAQ

<Accordion title="Is there an option to avoid sending consent data to Google?">

AppsFlyer enables advertisers who believe the DMA requirements don't apply to their end-users (for example, when they are non-EU) to prevent sending consent data to Google. This is done by activating a toggle in the relevant integration pages.

> ❗️ Important!
>
> Before using this option, it's recommended to obtain approval from their legal and privacy teams to make sure it aligns with their policies. See Google's [consent mode article](https://support.google.com/tagmanager/answer/13802165?hl=en) for reference definitions.

**To refrain from sharing consent data with Google:**

1. In AppsFlyer, from the side menu, select **Collaboration** > **Active Integrations**.
2. Search for the partner and click **Manage integration**.
3. From the integration setup tab, turn on **Non-EU users**

![Non-EU users toggle in the integration setup tab](https://files.readme.io/6e86882f209773d7e8ca0ff801c23fd70ab0e3511c69b1a47c0ea48e0dd710db-22361665421713.png)

</Accordion>

<Accordion title="Is consent needed for mobile web events?">

At this stage, only mobile app events are shared with Google, so there's no need to share consent with AppsFlyer for web events. If users progress from the web to your app, their consent will still be collected within the app at a later stage.

</Accordion>

<Accordion title="To which countries does the Google DMA consent apply?">

The Digital Markets Act (DMA) applies to users within the EU and the EEA (European Economic Area), affecting [these regions](https://www.gov.uk/eu-eea). Although **the UK and Switzerland** are not part of the EU, Google has unilaterally extended its consent policy to include those countries as well.

</Accordion>

<Accordion title="What's the recommended way to ask for user consent in a compliant way?">

AppsFlyer recommends consulting with your legal team to secure consent in a DMA-compliant manner. While [Google provides general instructions](https://support.google.com/google-ads/answer/14009343?hl=en&sjid=3762335249108620505-NC#app-consent), it doesn't offer specific language for prompts.

</Accordion>

<Accordion title="How is AppsFlyer translating TCF strings to Google DMA consent flags?">

After AppsFlyer receives the TCF strings from your CMP (either through the AppsFlyer SDK or S2S), they are processed and translated on the AppsFlyer servers. The following translation is mapped and sent to Google, as recommended by Google:

| AppsFlyer collected strings | Google consent flags | Description |
| --- | --- | --- |
| `gdpr_applies=1/0` | `eea=1/0` | Identifies whether DMA is applicable or not for the respective user |
| `ad_user_data` | `ad_user_data=1` | When consent is given to Google for purpose 1, and consent/legitimate interest is given to Google for purpose 7 |
| `ad_user_data` | `ad_user_data=0` | When consent isn't given to Google for purpose 1 **or** consent/legitimate interest isn't given to Google for purpose 7 |
| `ad_personalization` | `ad_personalization=1` / `ad_personalization=0` | When consent is given to Google for purposes 3 and 4 / When consent isn't given to Google for purposes 3 and 4 |

</Accordion>

<Accordion title="Do I need to update both the AppsFlyer and Firebase SDKs to send consent data?">

Yes. Google requires consent data to be included in each event sent from AppsFlyer, as Google doesn't merge user consent data from Firebase with data sent from AppsFlyer. Therefore, consent data must be sent to AppsFlyer, which forwards it to Google. Similarly, sharing consent data with AppsFlyer alone is insufficient for Firebase SDK requirements. This means you must send the data to both AppsFlyer and Firebase.

</Accordion>

## Preparing for the upcoming changes

### Take the following preparatory steps

#### Address user consent in the European Economic Area (EEA)

Collaborate with your company's legal counsel. They can provide insights into the implications of European user consent policies for the data you share with partners like Google. If relevant, implement privacy prompts such as "Privacy Settings" or "Privacy Choices" to gather marketing and advertising-related user consent signals from your app users.

#### Verify CMP compliance and TCF 2.2/2.3 support

Make sure your Consent Management Platform (CMP) supports TCF 2.2/2.3, the most recent versions of the Transparency and Consent Framework (TCF). Your CMP should also be well informed about the new Google EU consent requirements and can advise you on how to support them under TCF.

#### Implement the newest SDK/Server-to-Server (S2S) APIs

Consider the following options for sending the new consent fields, either using the SDK or S2S API calls:

- **Using the SDK:**
  - Implement the latest version of the AppsFlyer SDK (Android - v6.13.0+, iOS - v6.13.1+) for iOS and Android apps
  - Choose how to [send the consent data](/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance)
- **Using [S2S](/docs/server-to-server-events-api-for-mobile-s2s-mobile) API calls:**
  - Before sending in-app events to AppsFlyer, update your API calls to include the `consent_data` object for each event. See [how to do this](https://dev.appsflyer.com/hc/reference/s2s-events-api3-post).

#### Transition from the legacy GMP integration (DoubleClick)

If you're still using the legacy AppsFlyer GMP integration (doubleclick_int), transition to the newer version (dv360_int), which is available now. The legacy integration is **not EU consent compatible** and will be deprecated soon. See more details [here](/docs/bulletin-google-marketing-platform-gmp-integration-transition).

## Impact on advertising activity—FAQ

<Accordion title="How will the upcoming change impact my campaign attribution?">

In some cases, EU users who opt out of having their data used by Google for advertising purposes (`ad_user_data=0`) won't be claimed for attribution by Google Ads and DV360. This means AppsFlyer won't be able to attribute them.

Google and AppsFlyer can still perform attribution in some cases when `ad_user_data=0`, based on Google's interpretation of the Digital Markets Act (DMA).

</Accordion>

<Accordion title="How will the upcoming change affect Audiences?">

The change may affect the number of EEA users who appear in your audiences and are exposed to remarketing campaigns on Google. EEA-based users will be required to consent before having their information shared with Google. Those who don't consent will be excluded from audiences on Google's side and won't be exposed to your campaigns. This raises the question of how to get consent from your users and what the ramifications may be for your business and advertising efforts. [Learn more about changes to Audiences](/docs/audiences-user-identifier-policy#eu-digital-markets-act).

</Accordion>

## Further information and contact details

In case you have further questions or any uncertainties, you can reach out to the following:

- For Google's requirements or how these updates may impact your Google data, please review [Google's help articles](https://www.google.com/about/company/user-consent-policy-help/) or reach out directly to your Google representative.
- For questions regarding AppsFlyer's support of EU end-user consent fields, reach out to your AppsFlyer CSM or write to [hello@appsflyer.com](mailto:hello@appsflyer.com).
- See Google's [consent mode article](https://support.google.com/tagmanager/answer/13802165?hl=en) for reference definitions.

<Cards>
  <Card title="Additional SDK integration guide" href="/docs/additional-sdk-integration-guide" icon="fa-solid fa-code">
    Learn how to implement consent and other advanced configurations in the AppsFlyer SDK.
  </Card>
  <Card title="Transition to the new DV360 integration" href="/docs/bulletin-google-marketing-platform-gmp-integration-transition" icon="fa-solid fa-bullhorn">
    Step-by-step instructions to migrate from the legacy DoubleClick integration to the new DV360 integration.
  </Card>
  <Card title="Audiences user identifier policy" href="/docs/audiences-user-identifier-policy" icon="fa-solid fa-users">
    Understand how the EU Digital Markets Act affects user identifiers and audience building.
  </Card>
</Cards>
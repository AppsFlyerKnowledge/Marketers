---
title: Preparing for the App Store review—nutrition labels
metadata:
  keywords:
    - iOS
    - iTunes
    - Apple
    - IDFA
    - Guidelines
    - IFA
    - Ad Tracking
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-04-12T13:28:26Z'
  edited_at: '2023-11-02T10:49:58Z'
  id: 207032086
  locale: en-us
  section: Preserve user privacy
  section_id: 6551440878097
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207032086-Preparing-for-the-App-Store-review-nutrition-labels
---
> **At a glance**: Starting iOS 14 App developers must provide the App Store information related to their Privacy Practices when they submit an app. The App Store publishes the practices in the format of a *nutrition label.*

**A word from our lawyers:** *Nothing stated here is legal advice. It is provided for your information and convenience. You should work closely with legal and other professional advisors to determine exactly how Apple policies apply to you.*

<div id="nutrition-labels-and-the-app-store-review" />

## Nutrition labels and the App Store review

* In order to generate the privacy labels, app developers must answer a questionnaire when submitting their app to App Store Connect that includes the following sections:
  * Data types collected
  * [Purposes for which data is collected](/docs/preparing-for-the-app-store-review-nutrition-labels#data-use-purposes)
  * [If the data type is linked to an identity](/docs/preparing-for-the-app-store-review-nutrition-labels#data-linked-to-an-identity)
  * If data is used for tracking (including in relation to any third-party service or SDK that is included in an app).
* App developers:
  * Have full control over how to implement and configure the AppsFlyer software, what data to collect, and how the data is used.
  * May have very different answers to the questionnaire based on how they configure the AppsFlyer software and the data points they choose to collect.
* According to the AppsFlyer understanding of the Apple policy, AppsFlyer doesn't *track.* That said, App developers must respond to the questionnaire in accordance with their specific uses and partner integrations.
* If you do use collected data for tracking purposes, you must implement the ATT prompt.
* The following assumes AppsFlyer software default configurations. App developers are responsible for ensuring that they adapt accordingly in line with their specific configurations and uses.

<div id="data-types-collected" />

#### Data types collected

| **Data type** | **AppsFlyer data collection** | **Remarks** |
| --- | --- | --- |
| **Contact information**<ul><li>Name</li><li>Email address (including hashed)</li><li>Phone number (including hashed)</li><li>Physical address</li><li>Other user contact info</li></ul> | No | Contact information should not be collected. However, if you have configured your app to transmit hashed emails or hashed phone numbers, respond accordingly in the App Store questionnaire. |
| **Fitness** | No | Don't collect |
| **Financial info**<ul><li>Payment info</li><li>Credit info</li><li>Other financial info</li></ul> | No | Don't collect |
| **Location info**<ul><li>Precise location</li><li>Coarse location</li></ul> | See remarks | <ul><li>Precise location: No</li><li>Coarse location: Yes. The IP address is collected and mapped to a coarse geographic location.</li></ul> |
| **Sensitive info** | No | Don't collect |
| **Contacts** | No | Don't collect |
| **User content**<ul><li>Emails or text messages</li><li>Photos or videos</li><li>Audio data</li></ul> | No | Don't collect |
| **Browsing history** | No | Don't collect |
| **Search history** | No | Don't collect |
| **Identifiers**<ul><li>User ID</li><li>Device ID (IDFA)</li></ul> | Optional | <ul><li>User ID: App developers may set and transmit user ID (CUID)</li><li>Device ID: The Advertising ID (IDFA) is collected only when accessible.</li></ul> |
| **Purchases**<ul><li>Purchase history</li></ul> | Optional | App developers can choose to configure certain in-app purchase events to measure. |
| **Usage data**<ul><li>Product interaction</li><li>Advertising data</li><li>Other usage data</li></ul> | <ul><li>Yes</li><li>Optional</li><li>No</li></ul> | <ul><li>Product interactions: App launches are measured, as well as any other user interaction configured by the app developer.</li><li>Advertising data: is received if the app developer uses the AppsFlyer ad revenue module.</li></ul> |
| **Diagnostics data**<ul><li>Crash data</li><li>Performance data</li><li>Other diagnostics data</li></ul> | <ul><li>No</li><li>Yes</li><li>No</li></ul> | Launch time and/or battery levels may be received for fraud detection. |
| **Other data**<ul><li>Other data types</li><li>IDFV</li></ul> | Yes | <ul><li>Technical device information (for example, OS, device type, language, screen size, etc.) or network information (for example, IP address, HTTP user agent) is received by AppsFlyer.</li><li>AppsFlyer applies an install ID to each app install called the AF ID.</li><li>IDFV is collected</li></ul> |

<div id="data-use-purposes" />

### Data use purposes

Apple has a list of purposes from which app developers must choose, as detailed in the table that follows. You must identify the relevant purposes for each data type related to your specific use.

| Data purpose | Selection based on how data from AppsFlyer will be used |
| --- | --- |
| Third-party advertising | Select if you share the data type with a third party for the purpose of displaying third-party ads in your app. |
| Developer’s advertising or marketing | Select if you use to display first-party ads in your app (including if sharing with a third party to display your ads) or for other marketing purposes. |
| Analytics | Yes |
| Product personalization | Select if you use data for any product personalization. |
| App functionality | Yes |
| Other purposes | Select if you use the data for any purpose not otherwise stated. |

<div id="data-linked-to-an-identity" />

### Data linked to an identity

Data types collected through AppsFlyer are typically connected to an identifier like device ID (when available), or other identifiers like customer-issued IDs when configured.

Therefore, app developers should select **Yes** when asked if the data is linked to an identity.

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/">AppsFlyer Service Privacy Policy</Anchor>: How AppsFlyer handles and uses data.
> * <Anchor target="_blank" href="https://developer.apple.com/app-store/app-privacy-details/">App privacy details on the App Store by Apple</Anchor>.

<div data-zendesk-anchors="h_01HE7T7J409620K5KX5XKPEQVZ=nutrition-labels-and-the-app-store-review h_01HE7T7J4004XVJTMF6S964DVB=data-types-collected h_01HE7T7J4098NNW8D0BCD3EFBJ=data-use-purposes h_01HE7T7J41BJG9GTBWMVKG7031=data-linked-to-an-identity h_01HE7TES34MEF1XR4B6BDEMJW4=see-also" />

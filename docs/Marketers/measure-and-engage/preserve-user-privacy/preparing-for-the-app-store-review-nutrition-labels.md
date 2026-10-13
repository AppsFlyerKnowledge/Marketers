---
title: "Preparing for the App Store review—nutrition labels"
excerpt: "Starting iOS 14 A pp developers must provide the App Store information related to their Privacy Practices when they submit an app. The App Store publishes the practices in the format of a nutrition label."
x-zendesk:
  id: 207032086
  url: https://support.appsflyer.com/hc/en-us/articles/207032086-Preparing-for-the-App-Store-review-nutrition-labels
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Preserve user privacy
  section_id: 6551440878097
  position: 5
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [iOS, iTunes, Apple, IDFA, Guidelines, IFA, Ad Tracking, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2014-04-12T13:28:26Z'
  edited_at: '2023-11-02T10:49:58Z'
---
**A word from our lawyers:***Nothing stated here is legal advice. It is provided for your information and convenience. You should work closely with legal and other professional advisors to determine exactly how Apple policies apply to you.*

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

#### Data types collected



| **Data type** | **AppsFlyer data collection** | **Remarks** |
| --- | --- | --- |
| **Contact information**<br /><br />* Name<br />* Email address (including hashed)<br />* Phone number (including hashed)<br />* Physical address<br />* Other user contact info | No | Contact information should not be collected. However, if you have configured your app to transmit hashed emails or hashed phone numbers, respond accordingly in the App Store questionnaire. |
| **Fitness** | No | Don't collect |
| **Financial info**<br /><br />* Payment info<br />* Credit info<br />* Other financial info | No | Don't collect |
| **Location info**<br /><br />* Precise location<br />* Coarse location | See remarks | * Precise location: No<br />* Coarse location: Yes. The IP address is collected and mapped to a coarse geographic location. |
| **Sensitive info** | No | Don't collect |
| **Contacts** | No | Don't collect |
| **User content**<br /><br />* Emails or text messages<br />* Photos or videos<br />* Audio data | No | Don't collect |
| **Browsing history** | No | Don't collect |
| **Search history** | No | Don't collect |
| **Identifiers**<br /><br />* User ID<br />* Device ID (IDFA) | Optional | * User ID: App developers may set and transmit user ID (CUID)<br />* Device ID: The Advertising ID (IDFA) is collected only when accessible. |
| **Purchases**<br /><br />* Purchase history | Optional | App developers can choose to configure certain in-app purchase events to measure. |
| **Usage data**<br /><br />* Product interaction<br />* Advertising data<br />* Other usage data | * Yes<br />* Optional<br />* No | * Product interactions: App launches are measured, as well as any other user interaction configured by the app developer.<br />* Advertising data: is received if the app developer uses the AppsFlyer ad revenue module. |
| **Diagnostics data**<br /><br />* Crash data<br />* Performance data<br />* Other diagnostics data | * No<br />* Yes<br />* No | Launch time and/or battery levels may be received for fraud detection. |
| **Other data**<br /><br />  <br /><br />* Other data types<br />* IDFV | Yes | * Technical device information (for example, OS, device type, language, screen size, etc.) or network information (for example, IP address, HTTP user agent) is received by AppsFlyer.<br />* AppsFlyer applies an install ID to each app install called the AF ID.<br />* IDFV is collected |



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



### Data linked to an identity

Data types collected through AppsFlyer are typically connected to an identifier like device ID (when available), or other identifiers like customer-issued IDs when configured.

Therefore, app developers should select **Yes** when asked if the data is linked to an identity.

> 📘 **See also**
>
> * [AppsFlyer Service Privacy Policy](https://www.appsflyer.com/services-privacy-policy/): How AppsFlyer handles and uses data.
> * [App privacy details on the App Store by Apple](https://developer.apple.com/app-store/app-privacy-details/).
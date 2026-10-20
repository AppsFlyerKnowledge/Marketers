---
title: 'For iOS and Android: The SDK integration wizard'
excerpt: Create and test your SDK integration code automatically.
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2024-04-10T12:17:00Z'
  edited_at: '2026-08-13T12:48:39Z'
  id: 24073235369617
  locale: en-us
  section: SDK integration planning
  section_id: 6551182964369
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/24073235369617-For-iOS-and-Android-The-SDK-integration-wizard
---
## About the SDK integration wizard

Let our [SDK integration wizard](https://dj.dev.appsflyer.com/?sourceos=android&utm_source=kb&utm_medium=sdk-int-wizard-orvw) guide the app developer through the SDK integration process. The app developer simply provides some credentials and customization choices, and the wizard generates code snippets to be copied and pasted into the project.

This article enables you to collect and send the app developer all the input and credentials required by the integration wizard flows. There are two developer journeys supported by the wizard:

* [The installation and integration developer journey](#the-installation-and-integration-flow): The wizard takes the developer from installation to successful testing of the integration.
* [The in-app event developer journey](#the-add-in-app-event-flow): The wizard guides the developer from defining in-app events to successfully testing their transmission to AppsFlyer.

## The installation and integration flow

Once the app developer has successfully completed the installation and setup using the Integration Wizard, the AppsFlyer SDK will be ready to begin sending attribution data. To verify successful integration, the flow includes a test that checks whether an 'install event' is correctly reported to AppsFlyer upon your app's installation.

The table below lists the questions that developers need to address during the wizard setup. Use the specified instructions in the table to collect the necessary information and provide it to the developers.

| Questions | Learn more |
| --- | --- |
| What is your App ID? (Required) | [Learn how to obtain the App ID in each store.](/docs/adding-an-app-to-appsflyer#enter-app-details) |
| What is your AppsFlyer Dev Key (Required) | [Learn how to obtain the Dev Key.](/docs/basic-sdk-integration-guide#retrieve-the-dev-key) |
| What SDK mode would you like to integrate? Regular or strict? | [Learn about SDK modes](/docs/additional-sdk-integration-guide#strictmode-sdk). |
| Should the SDK get conversion data? | [Learn about Conversion data in the SDK](/docs/get-conversion-data-using-appsflyer-sdk-overview). |
| Should the SDK receive confirmation that it was started successfully? | Learn about the SDK start method with a completion handler ([Android](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-with-a-response-listener), [iOS](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#start-with-completion-handler)). |
| Should the SDK support AppTrackingTransparency support (ATT)? | [Learn about ATT](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support). |
| What is your AppsFlyer v2 authentication token? (Required only if you follow the automatic test flow.) | [Learn how to retrieve your v2 token](/docs/managing-appsflyer-tokens#reaching-the-tokens-page). |

## The add-in-app event flow

After the app developer completes the installation and integration wizard, AppsFlyer SDK will be integrated successfully into your app. The flow includes an in-app event test confirming that the AppsFlyer when your app is installed.

The table below lists the questions that developers need to address during the wizard setup. Use the specified instructions in the table to collect the necessary information and provide it to the developers.

| Questions | Learn more |
| --- | --- |
| Choose the event name and its event parameters | [Learn which predefined events are available for you.](/docs/adding-an-app-to-appsflyer#enter-app-details) Each event description includes its typical event parameters.  <br />Alternatively, you can use our   <br />[In-app event generator](https://evgen.appsflyer.com/). |
| Should the SDK receive confirmation that the in-app event was received by AppsFlyer? | Learn about the code that verifies that events were successfully received in AppsFlyer ([Android](https://dev.appsflyer.com/hc/docs/in-app-events-android#handling-event-submission-success-and-failure), [iOS](https://dev.appsflyer.com/hc/docs/in-app-events-ios#handling-event-submission-success-and-failure)). |
| What is your AppsFlyer v2 authentication token? (Required only if you follow the automatic test flow.) | [Learn how to retrieve your v2 token](/docs/managing-appsflyer-tokens#reaching-the-tokens-page). |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Zero plan | The SDK integration wizard is not included in the [Zero plan](/docs/account-management-plans-payments-and-billing#appsflyer-plans). |

<div data-zendesk-anchors="h_01J6730Y7WE1AJXNXFZ0QX23T8=about-the-sdk-integration-wizard h_01J5K2A8BZS9CTZA45FB5VX8C0=the-installation-and-integration-flow h_01J5K2CG0H1G0BCSWHBJ8DPQWA=the-add-in-app-event-flow h_01J6S6HS0H0M6GQ81WGZ3XT0P9=traits-and-limitations" />

---
title: "Troubleshooting the web SDK"
excerpt: "A troubleshooting guide for AppsFlyer Web SDK added directly to your website or implemented via Google Tag Manager."
---
## SDK added directly

You can add the SDK directly to your website.

### No data or partial data in the PBA dashboard

| Cause | Solution |
| --- | --- |
| Data takes up to 24 hours to display in [People-Based Analysis dashboards](/docs/pba-website-attribution-dashboard) after you implement the SDK. | Wait 24 hours. If data is still not available, see additional causes in this document. |
| Incorrect web dev key | - Web SDK uses the web dev key to identify web events sent in order to know which bundle to attribute data to.<br />- Verify that you are using the [correct web dev key.](/docs/pba-web-sdk-integration-guide#ensure-that-the-sdk-is-working)<br />[Brand Bundle page](/docs/pba-brand-bundles-and-settings#add-brand-bundle) |
| You placed the web SDK in the body of the page | - You can put the web SDK in the body of the page, but this might affect the data that is sent to AppsFlyer.<br />- We recommend that you put it in the head section of the page. |
| The web SDK is not placed on all pages on your website | We recommend placing the web SDK on all pages of your website. |

### Events are not sent

| Cause | Solution |
| --- | --- |
| Events are being sent before the web SDK loads up. In such cases the browser developer console shows the error: `Uncaught ReferenceError: AF is not defined` | Verify that the web SDK is loaded before the code that sends events. |
| Incorrect web dev key | - PBA requires a web dev key in order to know which bundle to attribute data to. Make sure that the correct web dev key is used. <br />- Verify that you are using the [correct web dev key.](/docs/pba-web-sdk-integration-guide#ensure-that-the-sdk-is-working) |
| Malformed events | Make sure the event is well-formed. <br />See [available event parameters](/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters) to learn more about well-formed events. |
| SDK called twice |  |

### Conflicting SDKs and libraries

Many web SDKs make use of popular JavaScript libraries. Such SDKs also occupy names in the global scope. For example, our web SDK occupies **AF** as the main object that enables the web SDK.

- If some SDK makes use of library X version 1.2 and AppsFlyer SDK makes use of library X 2.1, the two libraries might conflict.
- If another SDK or library makes use of **AF** (in the global scope) as an object name, the two SDKs conflict, and one SDK might override the other.

## SDK added using Google Tag Manager

- Implementing the web SDK with the help of Google Tag Manager (GTM) can save you time.
- You can implement it independently and you don't have to rely on your web developer to add it to your website.

If you come across issues. Apart from the issues described in the [native implementation of the SDK](/docs/troubleshooting-the-web-sdk#sdk-added-directly), there are some possible issues specific to GTM.

### Calling the SDK

| Cause | Solution |
| --- | --- |
| - Our Web SDK guide shows how to add the web SDK using a tag.<br />- Some users, when creating tags to call events, set the tag to also call the SDK tag again. But this might cause issues.<br /><img src="https://files.readme.io/8875f44720e2ccd18557ea9be7f623f4196ac3982ff4b2d46366a0fa50f929aa-mceclip0.png" alt="mceclip0.png" /> | The best approach is to set one tag to load the SDK and set this tag to fire on all pages. For any tags that send events, they should not call the SDK tag again. |

### Tag priority

GTM allows you to [set tag priority](https://support.google.com/tagmanager/answer/2772421?hl=en). This means that you can control which tags are fired first.

| Cause | Solution |
| --- | --- |
| A tag that loads the SDK is set to lower priority than a tag that sends an event on page load. As a result, the SDK is not initialized in time to send the event. | For the tag that loads the SDK, always set higher priority over tags that send events or identify users. |

### Triggering tags

In GTM, every tag has a trigger that determines when this tag should be fired.

| Cause | Solution |
| --- | --- |
| The trigger responsible for firing the tag that loads the SDK is not set to all pages. As a result, not all page visits are logged and some events are not sent. | The best approach is to set an [all-page views](https://support.google.com/tagmanager/answer/7679319?hl=en) trigger for the tag that loads the SDK. |
| The trigger responsible for firing tags that send events is not configured correctly. As a result, some events are not sent. | Determine the conditions for the trigger. For example,<br />- an interaction with DOM elements like a click on a button<br />- a page visit to a page that has a certain path like **/thank-you-page** or **/confirmation-page** |

### Publishing GTM containers

Every change in GTM, like adding or editing tags and triggers, requires you to publish the GTM container for changes to take effect. If you use the web SDK using GTM but the SDK doesn't load or events are not sent, make sure to [publish the GTM container](https://support.google.com/tagmanager/answer/6107163?hl=en).
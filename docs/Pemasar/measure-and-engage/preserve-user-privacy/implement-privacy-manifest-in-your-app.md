---
title: Implement Privacy Manifest in your app
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2024-01-15T10:17:30Z'
  edited_at: '2026-05-04T09:19:15Z'
  id: 21677433322641
  locale: en-us
  section: Preserve user privacy
  section_id: 6551440878097
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/21677433322641-Implement-Privacy-Manifest-in-your-app
---
> **At a glance:** At WWDC23 Apple introduced new privacy manifests. With Privacy Manifests, app developers are able to provide more accurate descriptions of their apps privacy practices. AppsFlyer has created a Privacy Manifest for the AppsFlyer SDK and the details are explained below.

## Background

With Privacy Manifests, an app developer will be able to create a record of the categories of data that it collects through its app independently and through its use of third-party dependencies, such as third-party SDKs used by the app. This information helps app developers accurately represent privacy practices in their apps including through the nutrition labels they provide to their users.

In many cases, app developers are not aware of what data third-party SDKs are collecting or what a specific SDK is using the data for. The Privacy Manifest enables third-party SDKs to easily pass this information to the app developers, helping them create accurate nutrition labels.

### What are nutrition labels?

Nutrition Labels provide information about an apps' privacy practices in an easy-to-read and understandable format. End users have more transparency into what data the app is collecting and for what purpose. For more information on Nutrition Labels see <Anchor target="_blank" href="/marketers/id/docs/preparing-for-the-app-store-review-nutrition-labels">here</Anchor>.

## What is in the AppsFlyer Privacy Manifest?

> 🚧 **Important!**
>
> In addition to the AppsFlyer SDK, you will have to determine your own data collection, Required Reason API, and usage in your app or other SDKs and report that information in the Nutrition Labels

AppsFlyer SDK 6.14.0 includes the AppsFlyer Privacy Manifest. This includes:

* [Data usage](#data-usage)
* [Required Reason APIs](#required-reason-apis)
* [Tracking domains](#tracking-domains)

### Data usage

Apple requires app and SDK developers to record the category of data, and the reasons, that the app or third-party SDK collects such data.

App developers can then use Xcode to create a privacy report, summarizing the information about the collected data.

Following are the Data Types collected by the AppsFlyer SDK, that are included in the Privacy Manifest:

> 📘 **Note**
>
> The following assumes AppsFlyer software default configurations. App developers are responsible for ensuring that they adapt their own manifest accordingly in line with their specific configurations and uses of the AppsFlyer SDK.

| Name | NSPrivacyCollectedDataType | NSPrivacyCollectedDataTypeLinked | NSPrivacyCollectedDataTypeTracking | NSPrivacyCollectedDataTypePurposes |
| --- | --- | --- | --- | --- |
| Device ID (IDFA, IDFV) | NSPrivacyCollectedDataTypeDeviceID | Yes | Yes | NSPrivacyCollectedDataTypePurposeThirdPartyAdvertising |
| Product Interaction (Launches) | NSPrivacyCollectedDataTypeProductInteraction | No | No | NSPrivacyCollectedDataTypePurposeAnalytics |

### Required Reason APIs

Apple provided a list of APIs that require reasoning for their use. Apps and SDKs that use these APIs should detail them in the Required Reson API section of the Privacy Manifest. These APIs are divided into categories based on their functionality and the information they provide according to <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api?language=objc">Apple’s list of topics.</Anchor> These are the APIs that are included in the AppsFlyer SDK version 6.14.0 Privacy Manifest:

* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">File Timestamp APIs</Anchor>
* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">User defaults APIs</Anchor>

To clarify the usage of Required Reason APIs, app developers will be required to declare the API category and specify the reasons for using the API. Below are the AppsFlyer APIs and their usage.

<div id="sdk-version-6140-and-above" />

<Accordion title="SDK version 6.14.0 and above">

| API Category | API Category Type | Reason | Comments |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">File Timestamp APIs</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | The SDK is using the <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor> and <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> APIs to determine the app installation date and the app update date. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">User defaults APIs</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1<br /><br />notionvc: 8aa85ca2-5648-4caa-9cac-b5b5df9ac883 | The SDK stores data that is needed for its operation. For example - maintaining how many times the app was launched. |

</Accordion>

<div id="sdk-versions-6130-and-earlier" />

<Accordion title="SDK versions 6.13.x and earlier">

| API Category | API Category Type | Reason | Comments |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">File Timestamp APIs</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | The SDK is using the <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor> and <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> APIs to determine the app installation date and the app update date. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278394">System boot time APIs</Anchor> | NSPrivacyAccessedAPICategorySystemBootTime | 35F9.1 | Measure SDK performance (time it took to execute a request etc.) |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">User defaults APIs</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1<br /><br />notionvc: 8aa85ca2-5648-4caa-9cac-b5b5df9ac883 | The SDK stores data that is needed for its operation. For example - maintaining how many times the app was launched. |

For your convenience, you can copy the following code snippet which includes the Required Reasons above, and paste it within your PrivacyInfo.xcprivacy file.

```xml
<key>NSPrivacyAccessedAPITypes</key>
<array>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>CA92.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryUserDefaults</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>C617.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryFileTimestamp</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>35F9.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategorySystemBootTime</string>
    </dict>
</array>
```

</Accordion>

### Tracking Domains

Any Tracking Domain used in an app or a third-party SDK must be recorded in the privacy manifest. If users do not grant permissions (opt-out) through the App Tracking Transparency (ATT) framework, the iOS operating system will block all outgoing traffic to that domain. The AppsFlyer SDK checks the user's ATT status before any server request and executes the request based on whether the user has opted in.

## FAQ

<div id="do-i-have-to-update-my-appsflyer-sdk" />

<Accordion title="Does AppsFlyer have an SDK supporting the Privacy Manifest?">

Yes, starting with version 6.14.0, the SDK has full support for the Privacy Manifest.

</Accordion>

<div id="do-i-have-to-report-my-own-data-collection" />

<Accordion title="Do I have to report my own data collection?">

Yes, in addition to AppsFlyer or other SDKs, you will have to determine your own data collection and usage and report that information in the Nutrition Labels, including any configuration changes made to the default AppsFlyer SDK configurations (e.g. measurement of in-app events).

</Accordion>

<div data-zendesk-anchors="h_01HCY4D9EKHYB5B3YNWRCB53F4=background h_01HCY4ZASEAR69RT3YMHMSE4NP=what-are-nutrition-labels what-to-consider-when-getting-your-app-ready-to-ios17=what-is-in-the-appsflyer-privacy-manifest h_01HCY4D9EKTKB50BSZD7RBMMYB=what-is-in-the-appsflyer-privacy-manifest h_01HQ5C9WGW669HBWSG4WQMJTGP=important h_01HQ03P71BG159MCE3VQY4GTMH=data-usage h_01HT9QHRQSKDQ8GR17N7X5QB8N=note h_01HQ03NV880VHFTXQDE8R6ZRZH=required-reason-apis h_01HSZSWW6Y91BTY1GNXMMVJCEQ=sdk-version-6140-and-above h_01HT9QVD9KZVN7RXWP03XCH8JZ=sdk-versions-6130-and-earlier required-reasons-api=tracking-domains h_01HQ03NV88SJPYKBM66S7X6GP8=tracking-domains 01HQQXSN96D4QTTYHG8CBE8695=faq h_01HCY5XRA96XAYYGB4XCZ8EXXG=do-i-have-to-update-my-appsflyer-sdk h_01HDDQV25KC9XWF7CJ7QBH4XW2=do-i-have-to-report-my-own-data-collection" />

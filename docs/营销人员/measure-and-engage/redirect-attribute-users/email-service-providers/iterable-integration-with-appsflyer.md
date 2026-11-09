---
title: 与AppsFlyer对接。
metadata:
  keywords:
    - OneLink
    - Advertisers
    - ESP
    - Developers
    - Iterable
    - Deep Likning
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-09-16T13:14:19Z'
  edited_at: '2026-10-14T09:59:55Z'
  id: 360002522337
  locale: zh-cn
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/zh-cn/articles/360002522337
---
> **概要：**

<Image align="center" alt="iterable-af-logo.png" src="https://files.readme.io/e339ea75a54e53711f3c577c7f82339151af13e6c086cc1435cbb57cf1fae3f0-49839295443089.png" />

<div id="introduction" />

## 简介

<div id="prerequisites" />

## 前期准备

<Tabs>
<Tab title="iOS">

</Tab>

<Tab title="Android">

</Tab>
</Tabs>


<div id="step-1-setting-up-link-branding-in-iterable" />

<div id="setting-up-iterable" />

### 第1步：

<div id="step-2-uploading-your-ssl-certificate-to-iterable" />

### 第2步：

<div id="asset-links-for-android" />

<div id="aasa-for-ios" />

<div id="step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android" />

### 第2步：

4. 有关更多信息，请参见<Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511">这里</Anchor> 。



<div id="step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest" />

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<div id="setting-up-your-app" />

#### 第1步：

```html Markup
<activity android:name=".DeepLinkActivity">
    <intent-filter  android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" />
           <category android:name="android.intent.category.BROWSABLE" />
           <data android:scheme="https"
               android:host="click.example.com"
               android:pathPrefix="/campaign" />
     </intent-filter>
</activity>
```

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<div id="step-2-setting-up-the-app-to-resolve-click-domains" />

#### 第2步：

2.
   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```


<div id="note" />

<div id="sending-your-first-email" />

<div id="step-2-for-ios-resolve-deep-links" />

<div id="step-2-for-android-resolve-deep-links" />

<div id="step-1-associating-click-domains-in-xcode" />

#### 第1步：

1. 在 XCode 中选择您的项目


2.
   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("clickdomain.com", "myclickdomain.com", "anotherclickdomain.com");
   ```


2. 
<Tabs>
<Tab title="Objective-C">

```objectivec
[AppsFlyerLib shared].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
```

</Tab>

<Tab title="Swift">

```swift
AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
```

</Tab>
</Tabs>

3. 
<Tabs>
<Tab title="Objective-C">

```objectivec
- (NSDictionary *)allHTTPHeaderFieldsForResolveDeepLinkURL:(NSURL *)URL {
    if ([URL.host  isEqual: @"click.example.com"]) {
        return [NSDictionary dictionary];
    }
    else {
        return nil;
    }
}
```

</Tab>

<Tab title="Swift">

```swift
func allHTTPHeaderFields(forResolveDeepLinkURL URL: URL!) -> [String : String]! {
    if (URL.host == "click.example.com") {
        /// Change User-Agent
        return [:]
    } else {
        return nil;
    }
}
```

</Tab>
</Tabs>



4. 举例来说，

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

<div id="testing-your-links" />

> 📄 **示例**
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

<div data-zendesk-anchors="introduction=%E7%AE%80%E4%BB%8B h_01HV6PJQRMT8037JMVMMXDPWGN=%E7%AE%80%E4%BB%8B prerequisites=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 h_01HV6PJQRM5N1K6CY0NSSFXT3X=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87 setting-up-iterable=%E7%AC%AC1%E6%AD%A5 step-1-setting-up-link-branding-in-iterable=%E7%AC%AC1%E6%AD%A5 h_01HV6PJQRMX18FRB3NMZH6NCH0=%E7%AC%AC1%E6%AD%A5 h_01HV6PJQRMMYV3A5ZSEGTT7993=%E7%AC%AC1%E6%AD%A5 step-2-uploading-your-ssl-certificate-to-iterable=%E7%AC%AC2%E6%AD%A5 h_01HV6PJQRMYDDWK9AKGN258TTM=%E7%AC%AC2%E6%AD%A5 step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android=%E7%AC%AC2%E6%AD%A5-1 h_01HV6PJQRMFJ23627KS83D4C6A=%E7%AC%AC2%E6%AD%A5-1 setting-up-your-app=%E7%AC%AC1%E6%AD%A5-1 step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest=%E7%AC%AC1%E6%AD%A5-1 h_01HV6PJQRMJHDF94JSAT8N8SP9=%E7%AC%AC1%E6%AD%A5-1 h_01HV6PJQRM2V31JAJ52Q3FHQWH=%E7%AC%AC1%E6%AD%A5-1 step-2%C2%A0setting-up-the-app-to-resolve-click-domains=%E7%AC%AC2%E6%AD%A5-2 h_01HV6PJQRMCRFM90QSP5SS72SE=%E7%AC%AC2%E6%AD%A5-2 step-1-associating-click-domains-in-xcode=%E7%AC%AC1%E6%AD%A5-2 h_01HV6PJQRNRW8Y97JWHP0MSXZF=%E7%AC%AC1%E6%AD%A5-2 sending-your-first-email=%E7%AC%AC1%E6%AD%A5-2 h_01HV6PJQRN2H29D8HKXHBYE1NB=%E7%AC%AC1%E6%AD%A5-2 h_01HV6PJQRNB327E42Y0ZJM9306=%E7%A4%BA%E4%BE%8B testing-your-links=%E7%A4%BA%E4%BE%8B h_01HV6PJQRNET2J17ZGGZE0K0Q6=%E7%A4%BA%E4%BE%8B" />

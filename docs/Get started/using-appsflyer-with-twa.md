---
title: "Using AppsFlyer with TWA"
excerpt: "Learn how to use AppsFlyer with Trusted Web Activities (TWA) and Progressive Web Apps (PWA) to measure installs and record in-app events."
---
**At a glance:** Use AppsFlyer with Trusted Web Activities (TWA) to measure installs and record in-app events.

## Introduction

### What are Trusted Web Activities?

Trusted web activities (TWA) are a new way to integrate web content with your Android app. The challenge with TWA is to be able to record in-app events. This challenge is addressed in this article. For more information about TWA, see [here](https://developers.google.com/web/updates/2019/02/using-twa).

TWA can also be used with Progressive Web Apps.

### What are Progressive Web Apps?

Progressive Web Apps (PWA) are apps that deliver app-like experience but are actually completely web-based. One form of PWA is an Android app whose activities are TWA-based. This is the form of PWA that is discussed in this article. TWA enables you to embed your PWA inside a standalone android application, effectively allowing you to feature your existing PWA application on Play Store.

The other form, one that is purely web-based, is not discussed in this article. For more information about PWA, see [here](https://developers.google.com/web/progressive-web-apps/).

This tab discusses PWA that is embedded in a Trusted Web Activity, an in app full screen web browser. Such apps have the [Android global application class](https://developer.android.com/reference/android/app/Application) but whose activities are solely web-based.

This form of PWA allows you to measure installs. The other form of PWA, those that are purely web-based, doesn't give you the option to measure installs.

## TWA

### Sending in-app events from TWA

In-app events are sent using the AppsFlyer SDK from native app activities. Since TWA is web-based and not a native activity, you cannot send in-app events using the AppsFlyer SDK. You can use [server-to-server in-app events](https://support.appsflyer.com/hc/articles/207034486) as an alternative. Follow the instructions below to send server-to-server events with TWA.

### Prerequisites

Before you can start sending events from TWA to AppsFlyer, do the following:

1. Add the following repository to the project level gradle file:

```java
maven { url "https://jitpack.io"}
```

2. Add the following libraries:
   - For android.support libraries:
     - Add the following in your build.gradle:

       implementation 'com.github.GoogleChrome.custom-tabs-client:customtabs:91b4a1270b'
     - Import the following libraries:

       ```java
       import android.support.customtabs.CustomTabsClient;
       import android.support.customtabs.CustomTabsIntent;
       import android.support.customtabs.CustomTabsServiceConnection;
       import android.support.customtabs.CustomTabsSession;
       import android.support.customtabs.trusted.TrustedWebActivityIntentBuilder;
       import static android.support.customtabs.TrustedWebUtils.EXTRA_LAUNCH_AS_TRUSTED_WEB_ACTIVITY
       ```
   - For androidX libraries:
     - Add the following in your build.gradle:

       ```java
       implementation 'com.github.GoogleChrome:android-browser-helper:ff8dfc4ed3'
       ```

     - Import the following libraries:

       ```java
       import androidx.browser.customtabs.CustomTabsClient;
       import androidx.browser.customtabs.CustomTabsIntent;
       import androidx.browser.customtabs.CustomTabsServiceConnection;
       import androidx.browser.customtabs.CustomTabsSession;
       import androidx.browser.trusted.TrustedWebActivityIntentBuilder;
       ```

### Getting the AppsFlyer ID

To send server-to-server events, you need the AppsFlyer ID. You can get the AppsFlyer ID from AppsFlyer Android SDK.

First, make sure to [integrate the AppsFlyer Android SDK](https://support.appsflyer.com/hc/articles/207032126). You can then get the AppsFlyer ID using the following SDK API:

```java
String appsflyerId = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
```

### Sending the AppsFlyer ID to TWA

You can send the AppsFlyer ID in one of two ways:

### **Append AppsFlyer ID and customer user ID to URL**

When you build a trusted web activity intent, you can pass parameters to its URL:

```java
private void launchTwa(String cuid, String af_id) {

    CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Setting up CustomTabsSession that is used to build an intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Creating the intent to launch TWA using URL with query params that can be read by the Web App
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri + "?cuid=" + cuid + "&appsflyer_id=" + af_id));
            Intent twaIntent = twaIntentBuilder.build(session);

            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

#### Retrieving the AppsFlyer ID

Once the web activity is launched you can retrieve the AppsFlyer ID using a simple JavaScript snippet:

```javascript
let url = new URL(document.location.href);
let appsflyerID;
url.searchParams.forEach((value, key) => {
    if(key === 'appsflyer_id') {
    	appsflyerID = value;
    }
})
```

Once you have the AppsFlyer ID, store in local storage for later use.

### **Sending AppsFlyer ID through custom headers**

You can pass custom headers to the trusted web activities. The server gets these headers, sets them in a cookies and sends to the browser. You can then retrieve the AppsFlyer ID using javascript:

```java
private void launchTwa(String cuid, String af_id) {
        CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Setting up CustomTabsSession that is used to build an intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Creating the intent to launch TWA using URL with query params that can be read by the Web App
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri);
            Intent twaIntent = twaIntentBuilder.build(session);

            // Passing additional custom headers to the intent so they can be read by the Web App
            Bundle customHeaders = new Bundle();
            customHeaders.putString("twa_params", "cuid=" + cuid + "&=appsflyer_id" + af_id");
            twaIntent.putExtra(Browser.EXTRA_HEADERS, customHeaders);
            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

#### Retrieving the AppsFlyer ID

JavaScript doesn’t provide an API to allow developers to access headers. Therefore, the server should send the conversion data back to the web activity as a cookie. The server gets the custom headers containing the AppsFlyer ID, parses the data and sends it to the web page as a cookie.

When the page loads, a JavaScript snippet should be set in place to fetch the AppsFlyer ID cookie.

```javascript
// get the conversion data cookie
// function taken from https://plainjs.com/javascript/utilities/set-cookie-get-cookie-and-delete-cookie-5/
function getCookie(name) { 
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}

// get the cookie
var conversionData = JSON.parse(getCookie('appsflyer_id'));
console.log(appsflyer_id);
```

### Sending the in-app event

To send in-app events, you need to send the event data to your server and have your server send the event to AppsFlyer. There are a few other prerequisites for sending in-app events:

- [SDK dev key](https://support.appsflyer.com/hc/articles/207032126) -

> ❗️ Important
>
> The SDK dev key is a sensitive value and shouldn't be present in the TWA. If you are going to use TWA and send server-to-server in-app events, always store the SDK dev key securely server-side.

- App ID - the app ID as it appears in Android Manifest.xml.

Once you have these three parameters (AppsFlyer ID, SDK dev key, app ID), you can send the in-app event. Whenever an event takes place on the web activity you should send a request to your webserver to handle this event. The webserver gets the data related to the event, composes the event, and sends it to AppsFlyer.

See [here](https://support.appsflyer.com/hc/articles/207034486#servertoserver-events-api-for-mobile) for examples how to send server-to-server in-app events.

### Customizing web content with conversion data

The AppsFlyer SDK provides you with conversion data through two APIs:

- [Get conversion data](https://dev.appsflyer.com/hc/docs/conversion-data) - called when the app is launched for the first time after an install and for subsequent app launches.
- [On app open attribution](https://dev.appsflyer.com/docs/api-reference#onappopenattribution) - called when the app is deep-linked into using OneLink.

You can use conversion data to customize web content.

### Sending conversion data to TWA

Once you get the conversion data from either method listed above, you can send it to your web server. To do so, use custom headers:

```java
private void launchTwa(Map<String, String> conversionData, String cuid, String af_id) {
        CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Setting up CustomTabsSession that is used to build an intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Creating the intent to launch TWA using URL with query params that can be read by the Web App
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri);
            Intent twaIntent = twaIntentBuilder.build(session);

            // Passing additional custom headers to the intent so they can be read by the Web App
            Bundle customHeaders = new Bundle();
            customHeaders.putString("twa_params", "cuid=" + cuid + "&=" + af_id");
            customHeaders.putString("conversion_data", conversionData);
            twaIntent.putExtra(Browser.EXTRA_HEADERS, customHeaders);
            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

### Fetching the conversion data from the client-side

JavaScript doesn’t provide an API to allow developers to access headers. Therefore, the server should send the conversion data back to the web activity as a cookie. The server gets the custom headers containing the conversion data, parses the data and sends to the web page as a cookie.

When the page loads, a JavaScript snippet should be set in place to fetch the conversion data cookie and customize the content accordingly. For example, if a user installs the app from a campaign for deals on flights, you can populate the web activity with content relevant for the deals that the campaign promotes.

```javascript
// get the conversion data cookie
// function taken from https://plainjs.com/javascript/utilities/set-cookie-get-cookie-and-delete-cookie-5/
function getCookie(name) {
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}

// get the cookie
var conversionData = JSON.parse(getCookie('conversion_data'));
console.log(conversionData);
/*
conversion data example:
{
        campaign: "CAMPAIGN_NAME", // "None" if not specified on the link
        media_source: "MEDIA_SOURCE", //"None" if not specified on the link
        cost_cents_USD : "0",
        is_first_launch: true,
        install_time: "2018-12-30 23:59:39.330",
        orig_cost: "0.0",
        af_click_lookback: "7d",
        click_time: "2018-12-30 23:59:09",
        cost_cents_USD: "0",
        af_status: "Non-organic"
}
*/
```

To learn more about conversion data use cases, see [here](https://support.appsflyer.com/hc/articles/360000726098).

## PWA

### Measuring installs for PWA

As with any other Android app, you can integrate the AppsFlyer SDK with the app to measure installs and get conversion data.

To measure installs, all you need to do is integrate the SDK following the instructions [here](https://support.appsflyer.com/hc/articles/207032126).

### Customizing content using conversion data

You can customize web content according to the campaign that prompts a user to install your app. For example, if a user installs an app from a campaign that gives them 20% discount on products from your web store. You can get the conversion data and apply the discount as soon as the app opens the web activity.

To learn about using conversion data to customize web content, follow the instructions [here](https://support.appsflyer.com/hc/articles/360002330178#sending-conversion-data-to-twa).

### Recording events in PWA

PWA makes use of TWA which are essentially web activities. Since TWA is web-based and not a native activity, you cannot send in-app events using the AppsFlyer SDK. As an alternative, you can use server-to-server in-app events.

Follow the instructions [here](https://support.appsflyer.com/hc/articles/360002330178#sending-inapp-events-from-twa) to learn how to send in-app events for PWA.
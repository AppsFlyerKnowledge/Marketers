---
title: "In-app events for hybrid apps"
excerpt: "Record in-app events from web-views embedded in your mobile app, allowing full event measurement even when the interaction occurs in the app’s web-based content."
---
**At a glance:** Record in-app events from web-views embedded in your mobile app, allowing full event measurement even when the interaction occurs in the app’s web-based content.

## Introduction

[In-app events](/docs/in-app-events-overview) that occur within the app are reported using the SDK. What about events that occur outside the app?

There are a few scenarios in which events occur outside the app context:

* Events that take place on your website: Implement [People-Based Attribution (PBA)](/docs/people-based-attribution-pba-overview) to get a unified view of customer journeys across channels, platforms including the website, and devices. This provides you with Web-to-App, Conversion paths analysis, and raw-data.
* [Backend servers](/docs/server-to-server-events-api-for-mobile-s2s-mobile): Events occur independently of user action on either the website or app. For example, automatic subscription renewal
* Hybrid:  The event takes place on your mobile website on a device having the app as described in this article. In-app events are recorded by calling the AppsFlyer SDK API using JavaScript.

This guide regards the hybrid scenario. Learn how to bridge the gap between the HTML view and native views, enabling you to record events in the HTML view and send them to the app.

> 📘 **Note**
>
> #### Note
>
> If your app integrates AppsFlyer **using a hybrid plugin** (for example, Cordova, Ionic, React Native, or Flutter), the bridging method described in this guide doesn’t apply.
>
> We recommend sending WebView-based events using the [AppsFlyer server-to-server (S2S) API](/docs/server-to-server-events-api-for-mobile-s2s-mobile).

> 📘 **Note**
>
> #### Example
>
> You have a hybrid app that offers subscriptions. You implement the subscription form in a web view which actually loads from your website.
>
> You can record the subscription in-app event in the web view and send data related to it, like subscription type or price, to the native code.
>
> The native code collects the data and uses the AppsFlyer SDK to send the subscription in-app event.
>
> [![](https://support.appsflyer.com/hc/article_attachments/360002884745)](https://support.appsflyer.com/hc/article_attachments/360002884745)


### Recording in-app events in hybrid apps

In this guide we provide two methods for recording in-app events in hybrid apps:

* **[Recommended]** [**JavaScript interface**](/docs/in-app-events-for-hybrid-apps#JavaScript-interface): Uses the native JavaScript interface in order to establish communication between the HTML or Web View and the native code. This way you can send in-app event-related data from the web view to the native code. Once the native code obtains the data, it sends it to AppsFlyer using the SDK.
* [**URL loading**](/docs/in-app-events-for-hybrid-apps#url-loading): In this method, the native code listens to URL loading events. You can set the native code to listen to loading events of specific URLs and extract data from the URL parameters. The data is then passed to the SDK.

## JavaScript interface

Both Android and iOS have native JavaScript interfaces that allow web views to call native code.

* Android: [JavaScriptInterface](https://developer.android.com/guide/webapps/webview)
* iOS: [JavaScriptCore](https://developer.apple.com/documentation/JavaScriptcore)

Advantages of using the native JavaScript interface over URL loading:

* It doesn't require implementing logic that listens to URL loading.
* Native interfaces are preferable to other implementations.
* There is no need to parse parameters from the URL.
* There is less code and therefore less maintenance required.

The implementation consists of the following steps:

1. HTML code for webview or web page
2. Native code implementation for webview

### Android

#### HTML code for Android

Add the following HTML code to the web view or web page:

```
<h1>Recording Event From Web View</h1>
<div id="main">
 <button id="recordEvent" onclick="recordEvent()"> Record Event </button>
</div>
<script type="text/JavaScript">
{/* Set Customer User ID */}
function setCustomerUserId(){
   app.setCustomerUserId(customerUserId)
}
function recordEvent(){
   var eventName = "af_purchase"
   var eventParams = "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}";
   app.recordEvent(eventName, eventParams)
}
</script>
```

When passing event value, keep the following in mind:

* Make sure to pass the event value as a stringified JSON.

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* To avoid any possible problems AppsFlyer recommends using
  only
  lower-case alpha-numeric characters (a-z and 0-9) for your
  in-app
  event names.

#### WebActivity class

Create a web activity class with the following code:

```
public class WebActivity extends AppCompatActivity {
 WebView web;

 @Override
 public void onCreate(Bundle savedInstanceState) {
  super.onCreate(savedInstanceState);
  setContentView(R.layout.activity_web);
  web = (WebView) findViewById(R.id.webView);
  web.getSettings().setJavaScriptEnabled(true);
  web.addJavaScriptInterface(new MainJsInterface(getApplicationContext()), "app");
  web.loadUrl("https://yourwebsite.com");
 }
}
```

The code above creates an object called **app**
that
acts as the bridge between the web view and the native code.

#### JavaScript interface class

Create a MainJsInterface class to implement `recordEvent()`
as `JavaScriptInterface`

```
public class MainJsInterface {
 Context mContext;

 MainJsInterface(Context c) {
  mContext = c;
 }
 
 //Set Customer User ID
 @JavaScriptInterface
 public void setCustomerUserId(String customerUserId){
   AppsFlyerLib.getInstance().setCustomerUserId(customerUserId);
 }

 @JavaScriptInterface
 public void recordEvent(String name, String json){
  Map<String, Object> params = null;
  if(json!=null) {
   try {
    JSONObject jsonObject = new JSONObject(json);
    params = new HashMap<>();
    Iterator keys = jsonObject.keys();
    while (keys.hasNext()) {
     String key = keys.next();
     Object value = jsonObject.opt(key);
     params.put(key, value);
    }
   } catch (JSONException e) {
    e.printStackTrace();
   }
  }
  AppsFlyerLib.getInstance().logEvent(this.mContext, name, params);
 }
}
```

The code above declares a `recordEvent` method that
can
be called in the web view using JavaScript.

In the HTML code, you can see that the method is called using
`app.recordEvent(eventName, eventParams)`. Recall
that
we set **app** to act as the bridge between the
web
view and native code. This is why **app** can call
the
`recordEvent` method that we define in MainJsInterface
class.

### iOS

#### HTML code for iOS

Add the following HTML code to the web view or web page:

```
<body>
 <h1>Recroding Event From Web View</h1>
 <div id="main">
  <button id="recordEvent" onclick="recordEvent()"> Record Event </button>
 </div>
 <script type="text/JavaScript">
   {/* Set Customer User ID */} 
   function setCustomerUserId(){  
    customerUserIdwebkit.messageHandlers.cuid.postMessage(customerUserId); 
   }
   function recordEvent(){
    var eventName = "af_purchase"
    var eventParams = "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}";
    webkit.messageHandlers.event.postMessage(eventName + "+" + eventParams);
   }
 </script>
</body>
```

The code above sets a function to be triggered when a button
is clicked.
The function sets the `eventName` and
`eventParams` variables and passes them to the native
code using `webkit.messageHandlers`.

When passing event value, keep the following in mind:

* Make sure to pass the event value as a stringified JSON.

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* To avoid any possible problems AppsFlyer recommends using
  only
  lower-case alpha-numeric characters (a-z and 0-9) for your
  in-app
  event names.

> 📘 **Note**
>
> #### Note
>
> The HTML code is for both Objective C and Swift.


#### Objective c

#### Web view controller

In your web view controller, add the following code in the view
controller.

```
-(void) loadView{
 [super loadView];

 WKWebViewConfiguration *configuration =
 [[WKWebViewConfiguration alloc] init];
 [configuration.userContentController
 addScriptMessageHandler:self name:@"event"];

 _webView = [[WKWebView alloc] initWithFrame:self.view.frame
         configuration:configuration];
 [self.view addSubview:_webView];
}

- (void) viewDidLoad {

 [super viewDidLoad];

 NSString* page = @"https://yourwebsite.com";

 NSURL *url = [NSURL URLWithString:page];
 NSURLRequest *request = [NSURLRequest requestWithURL:url];

 [_webView loadRequest:request];

 }

- (void) userContentController:(WKUserContentController *) userContentController
  didReceiveScriptMessage:(WKScriptMessage *) message {

 NSString* messageBody = message.body;
 NSString* eventName = [messageBody componentsSeparatedByString:@"+"][0];
 NSString* eventValue = [messageBody componentsSeparatedByString:@"+"][1];
 [self recordEvent:eventName eventValue:eventValue];
}

- (void) recordEvent:(NSString*) eventName eventValue:(NSString*) eventValue{

 NSData *eventValuedata = [eventValue dataUsingEncoding:(NSUTF8StringEncoding)];

 NSDictionary *eventValueDict = [NSJSONSerialization JSONObjectWithData:eventValuedata options:NSJSONReadingMutableContainers error:nil];

 [[AppsFlyerLib shared] logEvent:eventName withValues:eventValueDict];

}
```

The code above receives the message from the web view. The message
contains the event name and event value. When the code detects
the
incoming message, it passes it on to the `recordEvent`
method which parses the values and calls the native SDK
`logEvent` method.

#### Swift WebView controller

In your web view controller, add the following code:

```
import WebKit
import UIKit
import AppsFlyerLib
import JavaScriptCore

 class JSViewController: UIViewController, WKNavigationDelegate, WKScriptMessageHandler {
   func userContentController(_ userContentController: WKUserContentController, didReceive message: WKScriptMessage) {
    if message.name == "event" {
      let messageBody = message.body as? String
      let eventName = messageBody?.components(separatedBy: "+")[0]
      let eventValue = messageBody?.components(separatedBy: "+")[1]
      recordEvent(eventName: eventName!, eventValue: eventValue!) 
    } else if message.name == "cuid" {
      AppsFlyerLib.shared().customerUserID = message.body as? String
    }
 }

 var webView: WKWebView!
 override func loadView(){
  webView = WKWebView()
  webView.navigationDelegate = self
  view = webView
 }

 override func viewDidLoad() {
  super.viewDidLoad()
  let url = URL(string: "https://yourwebsite.com")!
  webView.load(URLRequest(url: url))
  webView.configuration.userContentController.add(self, name:"event")
 }

 func recordEvent(eventName: String, eventValue: String) {

  var eventValueDict = [String: String]()

  let eventValuesData = eventValue.data(using: String.Encoding.utf8)
  do {
   eventValueDict = try (JSONSerialization.jsonObject(with: eventValuesData!, options:[]) as? [String: String])!
  } catch let error as NSError{
   print(error)
  }

  AppsFlyerLib.shared().logEvent(eventName as String?, withValues: eventValueDict)
 }

}
```

The code above receives the message from the web view. The message
contains the event name and event value. When the code detects
the
incoming message, it passes it on to the `recordEvent`
method which parses the values and calls the AppsFlyer SDK
`logEvent` method.

## URL loading

Both Android and iOS implement a native method that listens to url loading events. This method enables you to do the following:

* Listen to a loading event of a specific URL
* Extract parameters that are appended to the URL
* Use these parameters in native code

The implementation below consists of two steps:

1. HTML code for webview or web page
2. Native code implementation for URL loading

### WebView implementation

#### HTML code (for both Android WebView and iOS WKWebView)

```
<html>
<head>
</head>
 <body>
  <h1>Recording From Web View</h1>
  <div id="main">
   <input id="button" type="button" value="Record Event" />
  </div>
  <script type="text/JavaScript">
  function recordEvent(eventName,eventValue){
   var iframe = document.createElement("IFRAME");
   iframe.setAttribute("src", "af-event://inappevent?eventName="+eventName+"&eventValue="+eventValue);
   document.documentElement.appendChild(iframe);
   iframe.parentNode.removeChild(iframe);
   iframe = null;
  }
  var button = document.getElementById("button");
  button.onclick = function(event) {
   var eventName = "af_purchase";
   var eventValue = "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}";
   recordEvent(eventName, eventValue);
  }
  </script>
 </body>
</html>
```

The code above can be part of an actual web page or loaded natively into the webview.

The code sets a function to be triggered when a button is clicked. The function itself creates an iframe element that loads a custom URL. It is this URL loading that triggers the native Android or iOS method that then calls the AppsFlyer SDK `logEvent` method.

All the required parameters (event name and event values) are appended to the URL. The Android and iOS code examples below demonstrate how to extract these parameters and pass them to AppsFlyer's SDK `logEvent` method.

When passing event value, keep the following in mind:

* Make sure to pass the event value as a stringified JSON.

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* To avoid any possible problems AppsFlyer recommends using only lower-case alpha-numeric characters (a-z and 0-9) for your in-app event names.

### Native implementation

Android iOS

#### Android implementation

Android WebView uses a WebViewClient that receives notifications from the web view. In the `shouldOverrideUrlLoading`, you can handle URL loading events that come from the web view:

```
@Override
public boolean shouldOverrideUrlLoading(WebView view, String url) {
	if (url.startsWith("af-event://")) {
		String[] urlParts = url.split("\\?");
		if (urlParts.length > 1) {
			String query = urlParts[1];
			String eventName = null;
			HashMap<String, Object> eventValue = new HashMap<>();

			for (String param : query.split("&")) {
				String[] pair = param.split("=");
				String key = pair[0];
				if (pair.length > 1) {
					if ("eventName".equals(key)){
						eventName = pair[1];
					} else if ("eventValue".equals(key)){
						JSONObject event;
						JSONArray keys;
						try {
							event = new JSONObject(pair[1]);
							keys = event.names();
							for (int i = 0; i < keys.length(); i++){
								eventValue.put(keys.getString(i), event.getString(keys.getString(i)));
							}
						} catch (JSONException e) {
							e.printStackTrace();
						}
					}
				}
			}
			AppsFlyerLib.getInstance().logEvent(getApplicationContext(),eventName,eventValue);
		}
		return true;
	}
	view.loadUrl(url);
	return true;

}
```

#### iOS implementation

Objective C Swift

In your web view controller, add the following code in the `shouldStartLoadWithRequest` method.

```
- (void) viewDidLoad {
 [super viewDidLoad];
 NSString *page = @"https://yourwebsite.com";

 NSURL *url = [NSURL URLWithString:page];
 NSURLRequest *request = [NSURLRequest requestWithURL:url];

 _webView = [[WKWebView alloc] initWithFrame:self.view.frame];
 _webView.navigationDelegate = self;
 [_webView loadRequest:request];
 _webView.frame = CGRectMake(self.view.frame.origin.x,self.view.frame.origin.y, self.view.frame.size.width, self.view.frame.size.height);
 [self.view addSubview:_webView];
}

-(void) webView:(WKWebView *) webView decidePolicyForNavigationAction:(WKNavigationAction* ) navigationAction decisionHandler:(void (^) (WKNavigationActionPolicy)) decisionHandler {
 decisionHandler(WKNavigationActionPolicyAllow);
 NSString *url = navigationAction.request.URL.absoluteString;
 if([url containsString:(@"af-event")]){
  [self recordEvent:(url)];
 }
}

- (void) recordEvent:(NSString*) url{

 NSString *eventNameAndEventValueString = [url componentsSeparatedByString: @"?"][1];

 NSArray *eventNameAndEventValueArray = [eventNameAndEventValueString componentsSeparatedByString: @"&"];

 NSString *eventName = [eventNameAndEventValueArray[0] componentsSeparatedByString: @"="][1];

 NSString *eventValueParams = [eventNameAndEventValueArray[1] componentsSeparatedByString: @"="][1];
 NSString *decodedValueParams = [eventValueParams stringByRemovingPercentEncoding];
 NSData *eventValuedata = [decodedValueParams dataUsingEncoding:(NSUTF8StringEncoding)];
 NSDictionary *eventValue = [NSJSONSerialization JSONObjectWithData:eventValuedata options:NSJSONReadingMutableContainers error:nil];

 if (eventName != nil){
  [[AppsFlyerLib shared] logEvent:eventName withValues:eventValue];

 }

}
```

The code above listens to any URL loading. If a URL with "af-event" in it loads, it triggers the native `recordEvent` method. The native `recordEvent` method extracts the necessary parameters (eventName and eventValue) and passes them on to the native SDK `logEvent` method.

In your web view controller, add the following code in the `webView(_:decidePolicyFor:decisionHandler:)` method.

```
import WebKit
import UIKit
import AppsFlyerLib
class WebViewController: UIViewController, WKNavigationDelegate {
 var webView: WKWebView!
 override func loadView(){
  webView = WKWebView()
  webView.navigationDelegate = self
  view = webView
 }

 override func viewDidLoad() {
  super.viewDidLoad()
  let url = URL(string: "https://yourwebsite.com")!
  webView.load(URLRequest(url: url))

 }

 func webView(_ view: WKWebView, decidePolicyFor navigationAction: WKNavigationAction, decisionHandler: ((WKNavigationActionPolicy) -> Void)) {
  decisionHandler(.allow)
  let pageUrl = navigationAction.request.url?.absoluteString

  if(pageUrl?.hasPrefix("af-event://") ?? false){

   let scanner = Scanner(string: pageUrl!)
   scanner.charactersToBeSkipped = CharacterSet(charactersIn: "&?")
   scanner.scanUpTo("?", into: nil)
   var tempString, eventName : NSString?
   var eventValue: [String: String] = Dictionary()

   while(scanner.scanUpTo("&", into: &tempString)){

    if let tempString = tempString {
     if(tempString.hasPrefix("eventName=") && tempString.length > 10){
      eventName = tempString.substring(from: 10) as NSString
     }
     if(tempString.hasPrefix("eventValue=") && tempString.length > 11){
      let eventValues = tempString.components(separatedBy: "=")[1].removingPercentEncoding
      let eventValuesData = eventValues?.data(using: String.Encoding.utf8)
      do {
       eventValue = try (JSONSerialization.jsonObject(with: eventValuesData!, options:[]) as? [String: String])!
      } catch let error as NSError{
       print(error)
      }
     }
    }
   }

   if(eventName != nil){
    if let eventName = eventName {
     // record event
     AppsFlyerLib.shared().logEvent(eventName as String?, withValues: eventValue)
    }

   }

  }

 }

}
```

The code above listens to any URL loading. If a URL with "af-event" in it loads, it extracts the necessary parameters (eventName and eventValue) and passes them on to the native SDK `logEvent` method.
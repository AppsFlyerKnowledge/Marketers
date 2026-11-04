---
title: 混合模式下的应用内事件
metadata:
  keywords:
    - Event
    - In-App
    - Native
    - HTML
    - Web View
    - wkwebview
    - webkit
    - Developers
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2014-08-07T12:45:23Z'
  edited_at: '2026-10-14T10:11:28Z'
  id: 207031976
  locale: zh-cn
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/zh-cn/articles/207031976
---
> **概要：** 记录发生在移动应用内嵌网页视图（web-views）中的应用内事件，即使用户交互发生在应用的网页内容中，也能实现完整的事件衡量。

<div id="introduction" />

## 简介

<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">应用内事件</Anchor>（即在相关应用内发生的事件）通过SDK上报，那么应用之外发生的事件要如何上报呢？

在下列场景中，用户会在相关应用之外的环境中完成事件：

* 用户在您的网站中完成事件：使用<Anchor target="_blank" href="/marketers/zh/docs/people-based-attribution-pba-overview">基于用户的归因（PBA）</Anchor>方案，对于跨流量入口和操作平台（包括网站和设备）的用户链路实现全面覆盖，获取经过标准化的综合数据。该方案提供网页到应用归因、转化路径分析以及相关的原始数据。
* <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">后端服务器</Anchor>：事件的发生与网页或应用中的用户行为无关，比如自动续订事件。
* 混合模式： 事件发生在移动端网页，但用户设备中已安装相关应用（具体示例请见下文说明）。 通过Javascript调用AppsFlyer SDK API，实现应用内事件的记录。

本文说明适用于混合模式下的使用场景,解释了如何记录HTML视图中的事件，并将其发送到相关应用，从而打通HTML和原生视图之间的数据传输。

<div id="example" />

> 📄 **示例**
>
> 贵司开发了一个混合模式的应用，并向用户提供订阅套餐。您在网页视图中添加了订阅表格，该视图通过您的网站加载。
>
> 您可以在网页视图中记录订阅事件，并向原生代码发送套餐类型或价格等相关数据。
>
> 原生代码收集这些数据，并使用AppsFlyer SDK发送这些订阅事件。
>
> [![](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)

<div id="recording-in-app-events-in-hybrid-apps" />

### 在混合模式下记录应用内事件

本文针对混合模式下的应用内事件，介绍了以下两种事件记录方式：

* **【推荐】**[**JavaScript接口**](/docs/in-app-events-for-hybrid-apps#javascript接口)：使用原生JavaScript接口，打通HTML/网页视图（Web View）和原生代码之间的数据传输， 以便将应用内事件的相关数据从网页视图发送到原生代码。原生代码收到这些数据后，即通过SDK将其发送到AppsFlyer。
* [**URL加载**](/docs/in-app-events-for-hybrid-apps#url加载)：您可以让原生代码监听特定URL的加载事件， 并从URL参数重提取数据，然后将这些数据传递给SDK。

<div id="javascript-interface" />

## JavaScript接口

安卓和iOS都有原生的JavaScript接口，网页视图可以通过这些接口调用原生代码。

* 安卓：<Anchor target="_blank" href="https://developer.android.com/guide/webapps/webview">JavaScriptInterface</Anchor>
* iOS：<Anchor target="_blank" href="https://developer.apple.com/documentation/JavaScriptcore">JavaScriptCore</Anchor>

与URL加载相比，JavaScript接口具有以下优势：

* 不需要添加用于监听URL加载的逻辑。
* 原生接口优于额外配置。
* 不需要解析URL中的参数。
* 代码更少，减轻维护负担。

部署流程包含以下两个步骤：

1. 将HTML代码添加到网页视图或网页
2. 配置用于网页视图的原生代码

<div id="android" />

<Accordion title="安卓">

<div id="html-code-for-android" />

#### 适用于安卓的HTML代码

请将以下HTML代码添加到网页视图或网页：

```html Markup
<h1>Recording Event From Web View</h1>
<div id="main">
 <button id="recordEvent" onclick="recordEvent()"> Record Event </button>
</div>
<script type="text/JavaScript">
<!-- Set Customer User ID -->
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

传递事件值时，须注意以下几点：

* 确保事件值为JSON格式的字符串。

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* 为了避免任何可能出现的问题，AppsFlyer建议您仅使用小写字母和数字（a-z 和0-9）来命名您的应用内事件。

<div id="webactivity-class" />

#### WebActivity类

使用以下代码创建一个WebActivity类：

```java
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

上述代码可创建一个名为**app**的对象，用于连接网页视图与原生代码。

<div id="javascript-interface-class" />

#### JavaScript接口类

创建一个MainJsInterface类，将`recordEvent()`添加为`JavaScriptInterface`。

```java
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

上述代码声明了一个可在网页视图中通过Javascript调用的`recordEvent`方法。

请注意，在上文的HTML代码中，该方法通过`app.recordEvent(eventName, eventParams)`调用。 这时我们已经设置了连接网页视图与原生代码`app.recordEvent(eventName, eventParams)`appapp.recordEvent(eventName,>， 因此**app**可以调用我们在MainJsInterface类中定义的`recordEvent`方法。

</Accordion>

<div id="ios" />

<Accordion title="iOS">

<div id="html-code-for-ios" />

#### 适用于iOS的HTML代码

请将以下HTML代码添加到网页视图或网页：

```html Markup
<body>
 <h1>Recroding Event From Web View</h1>
 <div id="main">
  <button id="recordEvent" onclick="recordEvent()"> Record Event </button>
 </div>
 <script type="text/JavaScript">
   <!-- Set Customer User ID --> 
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

上述代码可设置一个函数，用户点击按钮时即会触发该函数。 该函数定义了`eventName`和`eventParams`变量，并通过`webkit.messageHandlers`将它们传递到原生代码。

传递事件值时，须注意以下几点：

* 确保事件值为JSON格式的字符串。

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* 为了避免任何可能出现的问题，AppsFlyer建议您仅使用小写字母和数字（a-z 和0-9）来命名您的应用内事件。

<div id="note-1" />

> 📘 **注意**
>
> 上述HTML代码适用于Objective C和Swift。

#### Objective c

<div id="web-view-controller" />

#### 网页视图控制器

在您的网页视图控制器（web view controller）中添加以下代码：

```objectivec
-(void)loadView{
 [super loadView];

 WKWebViewConfiguration *configuration =
 [[WKWebViewConfiguration alloc] init];
 [configuration.userContentController
 addScriptMessageHandler:self name:@"event"];

 _webView = [[WKWebView alloc] initWithFrame:self.view.frame
         configuration:configuration];
 [self.view addSubview:_webView];
}

- (void)viewDidLoad {

 [super viewDidLoad];

 NSString* page = @"https://yourwebsite.com";

 NSURL *url = [NSURL URLWithString:page];
 NSURLRequest *request = [NSURLRequest requestWithURL:url];

 [_webView loadRequest:request];

 }

- (void)userContentController:(WKUserContentController *)userContentController
  didReceiveScriptMessage:(WKScriptMessage *)message {

 NSString* messageBody = message.body;
 NSString* eventName = [messageBody componentsSeparatedByString:@"+"][0];
 NSString* eventValue = [messageBody componentsSeparatedByString:@"+"][1];
 [self recordEvent:eventName eventValue:eventValue];
}

- (void)recordEvent:(NSString*)eventName eventValue:(NSString*)eventValue{

 NSData *eventValuedata = [eventValue dataUsingEncoding:(NSUTF8StringEncoding)];

 NSDictionary *eventValueDict = [NSJSONSerialization JSONObjectWithData:eventValuedata options:NSJSONReadingMutableContainers error:nil];

 [[AppsFlyerLib shared] logEvent:eventName withValues:eventValueDict];

}
```

上述代码会接收网页视图发出的消息，该消息中包含事件名称和事件值。当该代码检测到有消息传入时，会将消息传递给`recordEvent`方法，然后该方法会解析这些事件值，并调用原生SDK的`logEvent`方法。

<div id="swift-webview-controller" />

#### 适用于Swift的WebView控制器

在您的网页视图控制器（web view controller）中添加以下代码：

```swift
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

上述代码会接收网页视图发出的消息，该消息中包含事件名称和事件值。 当该代码检测到有消息传入时，会将消息传递给`recordEvent`方法，然后该方法会解析这些事件值，并调用AppsFlyer SDK的`logEvent`方法。

</Accordion>

<div id="url-loading" />

## URL加载

安卓和iOS都部署了可监听URL加载事件的原生方法。您可以使用该方法完成以下操作：

* 监听特定URL的加载事件
* 提取附加在URL末尾的参数
* 在原生代码中使用这些参数

部署流程包含以下两个步骤：

1. 将HTML代码添加到网页视图或网页
2. 配置用于URL加载的原生代码

<div id="webview-implementation" />

### WebView部署方式

<div id="html-code-for-both-android-webview-and-ios-wkwebview" />

#### HTML代码（适用于安卓WebView和iOS WKWebView）

```html Markup
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

您可以将上述代码作为实际网页的一部分，或者以原生方式将其载入网页视图。

该代码可设置一个函数，用户点击按钮时即会触发该函数。该函数本身可创建一个用于加载自定义URL的iframe元素。此处的URL加载会触发安卓或iOS的原生方法，继而调用AppsFlyer SDK的`logEvent`方法。

所有必要参数（即事件名称和事件值）都会被添加到该URL的末尾。在下文的安卓和iOS代码示例中，我们会提取这些参数，并将其传递到AppsFlyer SDK的`logEvent`方法。

传递事件值时，须注意以下几点：

* 确保事件值为JSON格式的字符串。

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* 建议仅使用小写字母和数字（a-z 和0-9）来命名您的应用内事件，以避免在传递数据时出现任何问题。

<div id="native-implementation" />

### 原生部署

<Tabs>
<Tab title="Android">

<div id="ios-implementation" />

<div id="android-implementation" />

#### 安卓部署方式

安卓WebView使用WebViewClient接收网页视图发出的通知。您可以通过`shouldOverrideUrlLoading`处理网页视图产生的URL加载事件：

```java
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

</Tab>

<Tab title="iOS">

#### iOS部署方式

<Tabs>
<Tab title="Objective C">

在网页视图控制器（web view controller）的`shouldStartLoadWithRequest`方法中添加以下代码：

```objectivec
- (void)viewDidLoad {
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

-(void)webView:(WKWebView *)webView decidePolicyForNavigationAction:(WKNavigationAction* )navigationAction decisionHandler:(void (^)(WKNavigationActionPolicy))decisionHandler {
 decisionHandler(WKNavigationActionPolicyAllow);
 NSString *url = navigationAction.request.URL.absoluteString;
 if([url containsString:(@"af-event")]){
  [self recordEvent:(url)];
 }
}

- (void)recordEvent:(NSString*)url{

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

上述代码可监听任何URL的加载事件。如果某个包含“af-event”的URL发生了加载，即会触发原生的`recordEvent`方法。原生的`recordEvent`方法会提取必要参数（eventName和eventValue）并将其传递到原生SDK的`logEvent`方法。

</Tab>

<Tab title="Swift">

在网页视图控制器（web view controller）的`webView(_:decidePolicyFor:decisionHandler:)`方法中添加以下代码：

```swift
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

上述代码可监听任何URL的加载事件。如果某个包含“af-event”的URL发生了加载，该代码会提取必要参数（eventName和eventValue）并将其传递到原生SDK的`logEvent`方法。

</Tab>
</Tabs>

</Tab>
</Tabs>

<div data-zendesk-anchors="introduction=%E7%AE%80%E4%BB%8B h_01HGWH2AEJ0DHTGD41YN7R5A1V=%E7%AE%80%E4%BB%8B h_01HGWH2AEJZHV3KZR0ZPPFK71T=%E7%A4%BA%E4%BE%8B recording-inapp-events-in-hybrid-apps=%E5%9C%A8%E6%B7%B7%E5%90%88%E6%A8%A1%E5%BC%8F%E4%B8%8B%E8%AE%B0%E5%BD%95%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01HGWH2AEJFEZY7WBJTFP9N3AN=%E5%9C%A8%E6%B7%B7%E5%90%88%E6%A8%A1%E5%BC%8F%E4%B8%8B%E8%AE%B0%E5%BD%95%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 JavaScript-interface=javascript%E6%8E%A5%E5%8F%A3 h_01HGWH2AEJFVDZBPRS8DP64TRY=javascript%E6%8E%A5%E5%8F%A3 h_01HGWH2AEKB47CJ386AN7NNX4Y=android html-code-for-android=%E9%80%82%E7%94%A8%E4%BA%8E%E5%AE%89%E5%8D%93%E7%9A%84html%E4%BB%A3%E7%A0%81 h_01HGWH2AEKZG98VWPECP6FBHN3=%E9%80%82%E7%94%A8%E4%BA%8E%E5%AE%89%E5%8D%93%E7%9A%84html%E4%BB%A3%E7%A0%81 webactivity-class=webactivity%E7%B1%BB h_01HGWH2AEKA5X1DPWS51WRCMD4=webactivity%E7%B1%BB JavaScript-interface-class=javascript%E6%8E%A5%E5%8F%A3%E7%B1%BB h_01HGWH2AEK07MGR1FPFSWXYRKP=javascript%E6%8E%A5%E5%8F%A3%E7%B1%BB h_01HGWH2AEN4WHKBSM69S200F5H=ios html-code-for-ios=%E9%80%82%E7%94%A8%E4%BA%8Eios%E7%9A%84html%E4%BB%A3%E7%A0%81 h_01HGWH2AENKC2EEYJPW9KZDVJS=%E9%80%82%E7%94%A8%E4%BA%8Eios%E7%9A%84html%E4%BB%A3%E7%A0%81 h_01HGWH2AENTMA7A71K2Y7XQF9T=%E6%B3%A8%E6%84%8F h_01HGWH2AENGAWEGD5TRTR2P6PR=objective-c web-view-controller=%E7%BD%91%E9%A1%B5%E8%A7%86%E5%9B%BE%E6%8E%A7%E5%88%B6%E5%99%A8 h_01HGWH2AENJVMVHSDPMKBP6HNT=%E7%BD%91%E9%A1%B5%E8%A7%86%E5%9B%BE%E6%8E%A7%E5%88%B6%E5%99%A8 swift-webview-controller=%E9%80%82%E7%94%A8%E4%BA%8Eswift%E7%9A%84webview%E6%8E%A7%E5%88%B6%E5%99%A8 h_01HGWH2AENV1J1M0KH36K1YSCJ=%E9%80%82%E7%94%A8%E4%BA%8Eswift%E7%9A%84webview%E6%8E%A7%E5%88%B6%E5%99%A8 url-loading=url%E5%8A%A0%E8%BD%BD h_01HGWH2AENV0Q83A0GF8NK7S4B=url%E5%8A%A0%E8%BD%BD webview-implementation=webview%E9%83%A8%E7%BD%B2%E6%96%B9%E5%BC%8F h_01HGWH2AENFH6M2ZQSGH4EGEGB=webview%E9%83%A8%E7%BD%B2%E6%96%B9%E5%BC%8F html-code-for-both-android-webview-and-ios-wkwebview=html%E4%BB%A3%E7%A0%81%E9%80%82%E7%94%A8%E4%BA%8E%E5%AE%89%E5%8D%93webview%E5%92%8Cios-wkwebview h_01HGWH2AENEDT95283SQZDHPCD=html%E4%BB%A3%E7%A0%81%E9%80%82%E7%94%A8%E4%BA%8E%E5%AE%89%E5%8D%93webview%E5%92%8Cios-wkwebview native-implementation=%E5%8E%9F%E7%94%9F%E9%83%A8%E7%BD%B2 h_01HGWH2AENS43N93D65RN80VXN=%E5%8E%9F%E7%94%9F%E9%83%A8%E7%BD%B2 android-implementation=%E5%AE%89%E5%8D%93%E9%83%A8%E7%BD%B2%E6%96%B9%E5%BC%8F h_01HGWH2AEN0QYYJJGV90A27VAM=%E5%AE%89%E5%8D%93%E9%83%A8%E7%BD%B2%E6%96%B9%E5%BC%8F ios-implementation=%E5%AE%89%E5%8D%93%E9%83%A8%E7%BD%B2%E6%96%B9%E5%BC%8F h_01HGWH2AEN38VWNXE90BHGQQ9A=%E5%AE%89%E5%8D%93%E9%83%A8%E7%BD%B2%E6%96%B9%E5%BC%8F" />

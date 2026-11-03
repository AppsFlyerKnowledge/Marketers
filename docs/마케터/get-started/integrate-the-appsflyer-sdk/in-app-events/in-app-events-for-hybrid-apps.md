---
title: 하이브리드 앱 용 인앱 이벤트
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
  edited_at: '2026-10-14T10:36:41Z'
  id: 207031976
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/207031976
---
> **한눈에 보기:** 모바일 앱에 내장된 웹 뷰에서 인앱 이벤트를 기록하여, 상호작용이 앱의 웹 기반 콘텐츠에서 발생할 때도 전체 이벤트 측정이 가능합니다.

## 소개

<Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">앱 내 이벤트</Anchor>는 SDK를 사용하여 보고됩니다. 앱 외부에서 발생하는 이벤트는 어떻게 되나요?

앱 컨텍스트 외부에서 이벤트가 발생하는 시나리오는 다음의 몇 가지가 있습니다.

* 웹사이트에서 발생하는 이벤트: 웹사이트와 플랫폼을 포함한 채널 전반에 걸쳐 고객 여정을 통합적으로 보기 위해 <Anchor target="_blank" href="/marketers/ko/docs/people-based-attribution-pba-overview">사람 기반 귀속(PBA)</Anchor>을 구현하세요. 이것은 웹-앱, 전환 경로 분석 및 원시 데이터를 제공합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">백엔드 서버</Anchor>: 백엔드 서버: 이벤트는 웹 사이트 또는 앱에 대한 사용자 조치와 독립적으로 발생합니다. 예를 들어, 자동 구독 갱신
* Hybrid  하이브리드: 이벤트는 이 기사에 설명된 대로 앱이 설치된 장치의 모바일 웹 사이트에서 수행됩니다.  인앱 이벤트는 Javascript를 사용하는 앱스플라이어 SDK API를 호출하여 기록됩니다.

본 가이드에서는 하이브리드 시나리오를 다룹니다. HTML 뷰와 네이티브 뷰 간의 차이를 해소하여 HTML 뷰에서 이벤트를 기록하고 앱으로 보낼 수 있는 방법에 대해 알아봅니다.

> 📄 **예시**
>
> 구독 서비스를 제공하는 하이브리드 앱이 있습니다. 웹사이트에서 실제로 로드되는 web view에서 구독 양식을 구현합니다.
>
> 웹 뷰에서의 해당 구독 인앱 이벤트를 기록하고, 구독 유형, 가격 등 관련 데이터를 네이티브 코드로 보낼 수 있습니다.
>
> 네이티브 코드는 데이터를 수집하고 앱스플라이어 SDK를 이용하여 해당 구독 이벤트를 전송합니다.
>
> [![](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)

### 하이브리드 앱에서의 인앱 이벤트 기록

이 가이드에서는, 하이브리드 앱의 인앱 이벤트를 기록하는 두 가지 방법을 안내합니다.

* **[추천]** [**JavaScript 인터페이스**](/docs/in-app-events-for-hybrid-apps#자바스크립트-인터페이스): 이 메서드는 네이티브 자바스크립트 인터페이스를 사용하여 HTML 또는 웹 뷰와 네이티브 코드 사이의 통신을 설정합니다. 이런 방식으로 웹 뷰에서 네이티브 코드로 인앱 이벤트 관련 데이터를 보낼 수 있습니다. 네이티브 코드가 데이터를 확보하면, SDK를 사용하여 앱스플라이어로 전송합니다.
* URL 로딩 URL 로딩: 이 메서드에서, 네이티브 코드는 url 로딩 이벤트를 수신 대기합니다.  네이티브 코드를 설정하여 특정 URL로 로딩 이벤트를 수신 대기하고 URL 파라미터에서 데이터를 추출할 수 있습니다. 그런 다음 이 데이터는 앱스플라이어 SDK로 전달됩니다.

## 자바스크립트 인터페이스

안드로이드와 iOS 모두 web view에서 native code를 호출할 수 있는 네이티브 자바스크립트 인터페이스를 갖고 있습니다.

* 안드로이드: <Anchor target="_blank" href="https://developer.android.com/guide/webapps/webview">JavaScriptInterface</Anchor>
* iOS: <Anchor target="_blank" href="https://developer.apple.com/documentation/JavaScriptcore">JavaScriptCore</Anchor>

URL 로딩에 비한 네이티브 자바스크립트 인터페이스 사용의 장점:

* URL 로딩을 수신 대기하는 로직을 구현할 필요가 없습니다.
* 다른 구현에도 네이티브 인터페이스가 선호됩니다.
* URL 파라미터를 파싱할 필요가 없습니다.
* 코드가 더 적기 때문에, 유지보수가 덜 필요합니다.

구현은 다음 단계들로 구성됩니다.

1. Webview 또는 웹페이지를 위한 HTML 코드
2. Webview를 위한 네이티브 코드 구현

<div id="android" />

<Accordion title="안드로이드">

#### 안드로이드 용 HTML 코드

다음 HTML 코드를 web view 또는 웹 페이지에 추가합니다.

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

이벤트 값(event value)를 전달할 때, 다음 사항을 유의하십시오.

* Stringified JSON로 이벤트 값을 전달합니다.

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* 가능한 문제를 피하기 위해 AppsFlyer는 다음을 사용하는 것을 권장합니다. 딥링킹을 작동시키고 소문자 알파벳 숫자 문자(a-z 및 0-9)를 사용하여 인앱 이벤트 이름

#### WebActivity 클래스

다음 코드를 사용하여 웹 액티비티 클래스를 작성합니다.

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

위 코드는 **앱**이라는 객체를 생성합니다. 그 웹 뷰와 네이티브 코드 간의 다리 역할을 합니다.

#### Javascript 인터페이스 클래스

MainJsInterface 클래스를 생성하여 `recordEvent()`을 구현하세요. MoEngage 대시보드에서

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

위 코드는 `recordEvent` 메서드를 선언합니다. 이 메서드는 JavaScript를 사용하여 웹 뷰에서 호출될 수 있습니다.

HTML 코드에서 메서드가 호출되는 것을 볼 수 있습니다. `app.recordEvent(eventName, eventParams)` 회상하세요 그 우리는 **앱**을 다리 역할을 하도록 설정했습니다. 웹 뷰와 네이티브 코드. 이것이 **app**가 호출할 수 있는 이유입니다. 마지막 매시간 업데이트된 MainJsInterface에서 정의한 `recordEvent` 메서드입니다. CLASS

</Accordion>

<div id="ios" />

<Accordion title="iOS">

#### 에 대한 HTML 코드입니다. iOS

다음 HTML 코드를 web view 또는 웹 페이지에 추가합니다.

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

위 코드는 버튼이 클릭될 때 트리거되는 함수를 설정합니다. 클릭되었을 때입니다. 함수는 `eventName`과 `eventParams` 변수를 설정하고 이를 네이티브로 전달합니다. 코드 `webkit.messageHandlers`을 사용하여.

이벤트 값(event value)를 전달할 때, 다음 사항을 유의하십시오.

* Stringified JSON로 이벤트 값을 전달합니다.

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* 가능한 문제를 피하기 위해 AppsFlyer는 다음을 사용하는 것을 권장합니다. 딥링킹을 작동시키고 소문자 알파벳 숫자 문자(a-z 및 0-9)를 사용하여 인앱 이벤트 이름

> 📘 **참고**
>
> HTML 코드는 Objective C 및 Swift 모두를 위한 것입니다.

#### Objective c

#### Web view controller

Web view controller에서 다음 코드를 view controller에 추가합니다. 컨트롤러입니다.

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

위 코드는 웹 뷰의 메시지를 수신합니다. 메시지입니다. 이벤트 이름과 이벤트 값을 포함합니다. 코드가 감지할 때입니다. 마지막 매시간 업데이트된 들어오는 메시지는 `recordEvent`으로 전달됩니다. 값을 구문 분석하고 네이티브 SDK를 호출하는 메서드입니다. 방법

#### Swift WebView 컨트롤러

웹 뷰 컨트롤러에 다음 코드를 추가하세요:

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

위 코드는 웹 뷰의 메시지를 수신합니다. 메시지입니다. 이벤트 이름과 이벤트 값을 포함합니다. 코드가 감지할 때입니다. 마지막 매시간 업데이트된 들어오는 메시지는 `recordEvent`으로 전달됩니다. 값을 구문 분석하고 AppsFlyer SDK를 호출하는 메서드입니다. 방법

</Accordion>

## URL 로딩

안드로이드와 iOS 모두 url 로딩 이벤트를 받는(listen) 네이티브 메서드를 구현합니다. 이 메서드를 사용하면 다음을 할 수 있습니다.

* 특정 URL의 로딩 이벤트를 받음
* URL에 첨부된 파라미터 추출
* 네이티브 코드에 이 파라미터 사용

아래의 구현은 두 단계로 구성됩니다.

1. Webview 또는 웹페이지를 위한 HTML 코드
2. URL 로딩을 위한 네이티브 코드 구현

### Webview 구현

#### HTML 코드 (안드로이드 WebView 및 iOS WKWebView 모두에 사용)

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

상기 코드는 실제 웹 페이지의 일부이거나 webview에 기본적으로 로딩될 수 있습니다.

위 코드는 버튼이 클릭될 때 트리거되는 함수를 설정합니다. 함수 자체는 커스텀 URL을 로딩하는 iframe element를 생성합니다. 이 URL 로딩이 앱스플라이어 SDK의 `logEvent`logEventlogEvent 메서드를 호출하는 네이티브 안드로이드 또는 iOS 메서드를 트리거하는 것입니다.

모든 필수 파라미터(이벤트 이름과 이벤트 값)는 URL에 추가됩니다. 아래의 안드로이드와 iOS 코드 예시는 어떻게 이런 파라미터를 추출하고 앱스플라이어 SDK `logEvent`logEventlogEvent 메서드에 전달하는지 보여줍니다.

이벤트 값(event value)를 전달할 때, 다음 사항을 유의하십시오.

* Stringified JSON로 이벤트 값을 전달합니다.

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* 혹시 발생할 지 모르는 문제를 예방하기 위해서, 앱스플라이어에서는 인앱 이벤트 이름으로 오직 영문 소문자와 숫자(a-z 및 0-9)만 사용하도록 권장합니다.

### Native implementation

<Tabs>
<Tab title="안드로이드">

#### 안드로이드 구현

안드로이드 WebView는 웹 뷰에서 알림을 수신하는 WebViewClient를 사용합니다. `shouldOverrideUrlLoading`에서 웹 뷰에서 오는 URL 로딩 이벤트를 처리할 수 있습니다:

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

#### iOS 구현

<Tabs>
<Tab title="Objective C">

Web view controller에서 다음 코드를 `shouldStartLoadWithRequest`webViewshouldStartLoadWithRequest 메서드에 추가합니다.

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

위의 코드는 모든 URL 로딩을 리슨합니다. "af-event"가 포함된 URL이 로드되면 네이티브 `recordEvent` 메서드를 트리거합니다. 네이티브 `recordEvent` 메서드는 필요한 매개변수(이벤트 이름 및 이벤트 값)를 추출하고 이를 네이티브 SDK `logEvent` 메서드로 전달합니다.

</Tab>

<Tab title="Swift">

Web view controller에서 다음 코드를 `webView(_:decidePolicyFor:decisionHandler:)`webViewwebView(\_:decidePolicyFor:decisionHandler:) 메서드에 추가합니다.

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

위의 코드는 모든 URL 로딩을 리슨합니다. "af-event"를 포함하는 URL이 로딩되면 필요한 파라미터(eventName와 eventValue)를 추출하여 네이티브 SDK `logEvent`logEventlogEvent 메서드로 전달합니다.

</Tab>
</Tabs>

</Tab>
</Tabs>

<div data-zendesk-anchors="introduction=%EC%86%8C%EA%B0%9C h_01HGWH2AEJ0DHTGD41YN7R5A1V=%EC%86%8C%EA%B0%9C h_01HGWH2AEJZHV3KZR0ZPPFK71T=%EC%98%88%EC%8B%9C recording-inapp-events-in-hybrid-apps=%ED%95%98%EC%9D%B4%EB%B8%8C%EB%A6%AC%EB%93%9C-%EC%95%B1%EC%97%90%EC%84%9C%EC%9D%98-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B8%B0%EB%A1%9D h_01HGWH2AEJFEZY7WBJTFP9N3AN=%ED%95%98%EC%9D%B4%EB%B8%8C%EB%A6%AC%EB%93%9C-%EC%95%B1%EC%97%90%EC%84%9C%EC%9D%98-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B8%B0%EB%A1%9D JavaScript-interface=%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4 h_01HGWH2AEJFVDZBPRS8DP64TRY=%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4 h_01HGWH2AEKB47CJ386AN7NNX4Y=android html-code-for-android=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EC%9A%A9-html-%EC%BD%94%EB%93%9C h_01HGWH2AEKZG98VWPECP6FBHN3=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EC%9A%A9-html-%EC%BD%94%EB%93%9C webactivity-class=webactivity-%ED%81%B4%EB%9E%98%EC%8A%A4 h_01HGWH2AEKA5X1DPWS51WRCMD4=webactivity-%ED%81%B4%EB%9E%98%EC%8A%A4 JavaScript-interface-class=javascript-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4-%ED%81%B4%EB%9E%98%EC%8A%A4 h_01HGWH2AEK07MGR1FPFSWXYRKP=javascript-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4-%ED%81%B4%EB%9E%98%EC%8A%A4 h_01HGWH2AEN4WHKBSM69S200F5H=ios html-code-for-ios=%EC%97%90-%EB%8C%80%ED%95%9C-html-%EC%BD%94%EB%93%9C%EC%9E%85%EB%8B%88%EB%8B%A4-ios h_01HGWH2AENKC2EEYJPW9KZDVJS=%EC%97%90-%EB%8C%80%ED%95%9C-html-%EC%BD%94%EB%93%9C%EC%9E%85%EB%8B%88%EB%8B%A4-ios h_01HGWH2AENTMA7A71K2Y7XQF9T=%EC%B0%B8%EA%B3%A0 h_01HGWH2AENGAWEGD5TRTR2P6PR=objective-c h_01HGWH2AENJVMVHSDPMKBP6HNT=web-view-controller swift-webview-controller=swift-webview-%EC%BB%A8%ED%8A%B8%EB%A1%A4%EB%9F%AC h_01HGWH2AENV1J1M0KH36K1YSCJ=swift-webview-%EC%BB%A8%ED%8A%B8%EB%A1%A4%EB%9F%AC url-loading=url-%EB%A1%9C%EB%94%A9 h_01HGWH2AENV0Q83A0GF8NK7S4B=url-%EB%A1%9C%EB%94%A9 webview-implementation=webview-%EA%B5%AC%ED%98%84 h_01HGWH2AENFH6M2ZQSGH4EGEGB=webview-%EA%B5%AC%ED%98%84 html-code-for-both-android-webview-and-ios-wkwebview=html-%EC%BD%94%EB%93%9C-%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-webview-%EB%B0%8F-ios-wkwebview-%EB%AA%A8%EB%91%90%EC%97%90-%EC%82%AC%EC%9A%A9 h_01HGWH2AENEDT95283SQZDHPCD=html-%EC%BD%94%EB%93%9C-%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-webview-%EB%B0%8F-ios-wkwebview-%EB%AA%A8%EB%91%90%EC%97%90-%EC%82%AC%EC%9A%A9 h_01HGWH2AENS43N93D65RN80VXN=native-implementation android-implementation=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B5%AC%ED%98%84 h_01HGWH2AEN0QYYJJGV90A27VAM=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B5%AC%ED%98%84 ios-implementation=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B5%AC%ED%98%84 h_01HGWH2AEN38VWNXE90BHGQQ9A=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B5%AC%ED%98%84" />

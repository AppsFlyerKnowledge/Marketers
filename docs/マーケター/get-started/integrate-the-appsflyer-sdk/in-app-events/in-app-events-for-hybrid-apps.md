---
title: ハイブリッドアプリのアプリ内イベント
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
  edited_at: '2026-10-29T07:44:20Z'
  id: 207031976
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/207031976
---
> **概要：** モバイルアプリに組み込まれたWebViewからアプリ内イベントを記録し、アプリ内のWebコンテンツ上で行われた操作も漏れなく計測します。

<div id="introduction" />

## はじめに

アプリ内で発生する<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">アプリ内イベント</Anchor>は、SDKを使って送信します。アプリのネイティブ環境以外で発生するイベントは、どのように計測すればよいでしょうか？

ネイティブ環境以外でイベントが発生するケースには、次のようなものがあります。

* Webサイト上で発生するイベント：<Anchor target="_blank" href="/marketers/ja/docs/people-based-attribution-pba-overview">People-Based Attribution（PBA）</Anchor>を実装すると、チャネル、Webサイトなどのプラットフォーム、デバイスを横断して、ユーザーの一連の行動をまとめて把握できます。 Web-to-App、コンバージョン経路の分析、ローデータを利用できます。
* <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">バックエンドサーバー</Anchor>：Webサイトやアプリ上でのユーザー操作とは独立してイベントが発生します。例えば、サブスクリプションの自動更新などです。
* ハイブリッドアプリ：本記事で説明するように、アプリがインストールされているデバイス上のモバイル向けWebサイトでイベントが発生します。 JavaScriptからAppsFlyer SDK APIを呼び出して、アプリ内イベントを記録します。

このガイドでは、ハイブリッドアプリのケースを取り上げます。 HTML画面とネイティブ画面を連携させ、HTML画面のイベントを記録してアプリに送信する方法を説明します。

<div id="note" />

> 📘 **注意**
>
> Cordova、Ionic、React Native、Flutterなどの**ハイブリッドプラグインを使って**AppsFlyerを実装している場合、このガイドの連携方法は適用できません。
>
> この場合、WebViewで発生するイベントは、<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">AppsFlyerのサーバー間（S2S）API</Anchor>で送信することを推奨します。

<div id="example" />

> 📄 **例**
>
> サブスクリプションを提供するハイブリッドアプリがあるとします。 Webサイト上のサブスクリプション申し込みフォームを、WebViewで読み込むようにします。
>
> WebViewでサブスクリプションのアプリ内イベントを記録し、種類や価格などの関連データをネイティブコードに送信できます。
>
> ネイティブコードはデータを受け取り、AppsFlyer SDKを使ってサブスクリプションのアプリ内イベントを送信します。
>
> [![](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)

<div id="recording-in-app-events-in-hybrid-apps" />

### ハイブリッドアプリでのアプリ内イベントの記録

このガイドでは、ハイブリッドアプリでアプリ内イベントを記録する2つの方法を紹介します。

* **［推奨］**[**JavaScriptインターフェース**](/docs/in-app-events-for-hybrid-apps#javascriptインターフェース)：ネイティブのJavaScriptインターフェースを使い、HTML画面やWebViewとネイティブコードの間でデータをやり取りします。 これにより、WebViewからネイティブコードにアプリ内イベントの関連データを送信できます。ネイティブコードがデータを受け取ると、SDKを使ってAppsFlyerに送信します。
* [**URLの読み込み**](/docs/in-app-events-for-hybrid-apps#urlの読み込み)：ネイティブコードがURLの読み込みイベントを監視する方法です。 特定のURLの読み込みイベントを監視し、URLパラメータからデータを取得するよう、ネイティブコードを設定できます。取得したデータをSDKに渡します。

<div id="javascript-interface" />

## JavaScriptインターフェース

AndroidとiOSには、WebViewからネイティブコードを呼び出すためのネイティブJavaScriptインターフェースがあります。

* Android：<Anchor target="_blank" href="https://developer.android.com/guide/webapps/webview">JavaScriptInterface</Anchor>
* iOS：<Anchor target="_blank" href="https://developer.apple.com/documentation/JavaScriptcore">JavaScriptCore</Anchor>

URLの読み込み方式と比較した、ネイティブJavaScriptインターフェースの利点：

* URLの読み込みを監視する処理を実装する必要がありません。
* 他の実装方法よりも、ネイティブインターフェースの利用が推奨されます。
* URLのパラメータを解析する必要がありません。
* コード量が少なく、保守の負担も軽減されます。

実装手順は以下のとおりです。

1. WebViewまたはWebページへのHTMLコードの追加
2. WebViewのネイティブコードの実装

<div id="android" />

<Accordion title="Android">

<div id="html-code-for-android" />

#### Android向けのHTMLコード

WebViewまたはWebページに、次のHTMLコードを追加します。

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

イベントの値を渡す際は、以下に注意してください。

* イベント値は、文字列化したJSONとして渡してください。

  ```html Markup
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* 問題の発生を避けるため、AppsFlyerでは、アプリ内イベント名に小文字の英数字（a～z、0～9）のみを使用することを推奨します。

<div id="webactivity-class" />

#### WebActivityクラス

次のコードを使用して、WebActivityクラスを作成します。

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

上記のコードは、WebViewとネイティブコードを橋渡しする**app**というオブジェクトを作成します。

<div id="javascript-interface-class" />

#### JavaScriptインターフェースクラス

MainJsInterfaceクラスを作成し、`recordEvent()`を`JavaScriptInterface`経由で呼び出せるように実装します。

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

上記のコードは、WebView内のJavaScriptから呼び出せる`recordEvent`メソッドを宣言します。

HTMLコードでは、`app.recordEvent(eventName, eventParams)`でこのメソッドを呼び出しています。前述のとおり、**app**はWebViewとネイティブコードを橋渡しするよう設定されています。そのため、**app**からMainJsInterfaceクラスで定義した`recordEvent`メソッドを呼び出せます。

</Accordion>

<div id="ios" />

<Accordion title="iOS">

<div id="html-code-for-ios" />

#### iOS向けのHTMLコード

WebViewまたはWebページに、次のHTMLコードを追加します。

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

上記のコードは、ボタンのクリック時に実行する関数を設定します。 この関数は`eventName`と`eventParams`変数を設定し、`webkit.messageHandlers`を使ってネイティブコードに渡します。

イベントの値を渡す際は、以下に注意してください。

* イベント値は、文字列化したJSONとして渡してください。

  ```html Markup
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* 問題の発生を避けるため、AppsFlyerでは、アプリ内イベント名に小文字の英数字（a～z、0～9）のみを使用することを推奨します。

<div id="note-1" />

> 📘 **注意**
>
> このHTMLコードは、Objective-CとSwiftの両方で使用できます。

#### Objective-C

<div id="web-view-controller" />

#### WebViewコントローラー

WebViewのビューコントローラーに、次のコードを追加します。

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

上記のコードは、WebViewからメッセージを受け取ります。メッセージには、イベント名とイベント値が含まれます。メッセージを受信すると、`recordEvent`メソッドに渡して値を解析し、ネイティブSDKの`logEvent`メソッドを呼び出します。

<div id="swift-webview-controller" />

#### SwiftのWebViewコントローラー

WebViewコントローラーに、次のコードを追加します。

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

上記のコードは、WebViewからメッセージを受け取ります。メッセージには、イベント名とイベント値が含まれます。メッセージを受信すると、`recordEvent`メソッドに渡して値を解析し、AppsFlyer SDKの`logEvent`メソッドを呼び出します。

</Accordion>

<div id="url-loading" />

## URLの読み込み

AndroidとiOSには、URLの読み込みイベントを監視するネイティブメソッドがあります。この方法では、次のことが可能です。

* 特定のURLの読み込みイベントの監視
* URLに追加されたパラメータの抽出
* ネイティブコードでのパラメータの利用

以下の実装は、2つの手順で構成されます。

1. WebViewまたはWebページへのHTMLコードの追加
2. URL読み込み処理のネイティブコードの実装

<div id="webview-implementation" />

### WebViewの実装

<div id="html-code-for-both-android-webview-and-ios-wkwebview" />

#### HTMLコード（Android WebViewとiOS WKWebViewの両方に対応）

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

上記のコードは、実際のWebページに組み込むことも、ネイティブ側でWebViewに読み込むこともできます。

このコードは、ボタンのクリック時に実行する関数を設定します。関数は、独自のURLを読み込むiframe要素を作成します。このURLの読み込みをきっかけに、AndroidまたはiOSのネイティブメソッドが実行され、AppsFlyer SDKの`logEvent`メソッドが呼び出されます。

必要なすべてのパラメータ（イベント名とイベント値）は、URLに追加されます。以下のAndroidとiOSのコード例では、これらのパラメータを取得し、AppsFlyer SDKの`logEvent`メソッドに渡す方法を示しています。

イベントの値を渡す際は、以下に注意してください。

* イベント値は、文字列化したJSONとして渡してください。

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* 問題の発生を避けるため、AppsFlyerでは、アプリ内イベント名に小文字の英数字（a～z、0～9）のみを使用することを推奨します。

<div id="native-implementation" />

### ネイティブ側の実装

<Tabs>
<Tab title="Android">

<div id="ios-implementation" />

<div id="android-implementation" />

#### Androidでの実装

Android WebViewは、WebViewからの通知を受け取るWebViewClientを使用します。 `shouldOverrideUrlLoading`で、WebViewからのURL読み込みイベントを処理できます。

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

#### iOSでの実装

<Tabs>
<Tab title="Objective-C">

WebViewのビューコントローラーの`shouldStartLoadWithRequest`メソッドに、次のコードを追加します。

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

上記のコードは、すべてのURLの読み込みを監視します。 「af-event」を含むURLが読み込まれると、ネイティブの`recordEvent`メソッドが実行されます。ネイティブの`recordEvent`メソッドが必要なパラメータ（eventNameとeventValue）を取得し、ネイティブSDKの`logEvent`メソッドに渡します。

</Tab>

<Tab title="Swift">

WebViewのビューコントローラーの`webView(_:decidePolicyFor:decisionHandler:)`メソッドに、次のコードを追加します。

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

上記のコードは、すべてのURLの読み込みを監視します。 「af-event」を含むURLが読み込まれると、必要なパラメータ（eventNameとeventValue）を取得し、ネイティブSDKの`logEvent`メソッドに渡します。

</Tab>
</Tabs>

</Tab>
</Tabs>

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01HGWH2AEJ0DHTGD41YN7R5A1V=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01KB7M7ZSM5AZACJNB32F65A62=%E6%B3%A8%E6%84%8F h_01HGWH2AEJZHV3KZR0ZPPFK71T=%E4%BE%8B recording-inapp-events-in-hybrid-apps=%E3%83%8F%E3%82%A4%E3%83%96%E3%83%AA%E3%83%83%E3%83%89%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%98%E9%8C%B2 h_01HGWH2AEJFEZY7WBJTFP9N3AN=%E3%83%8F%E3%82%A4%E3%83%96%E3%83%AA%E3%83%83%E3%83%89%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%98%E9%8C%B2 JavaScript-interface=javascript%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%BC%E3%83%95%E3%82%A7%E3%83%BC%E3%82%B9 h_01HGWH2AEJFVDZBPRS8DP64TRY=javascript%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%BC%E3%83%95%E3%82%A7%E3%83%BC%E3%82%B9 h_01HGWH2AEKB47CJ386AN7NNX4Y=android html-code-for-android=android%E5%90%91%E3%81%91%E3%81%AEhtml%E3%82%B3%E3%83%BC%E3%83%89 h_01HGWH2AEKZG98VWPECP6FBHN3=android%E5%90%91%E3%81%91%E3%81%AEhtml%E3%82%B3%E3%83%BC%E3%83%89 webactivity-class=webactivity%E3%82%AF%E3%83%A9%E3%82%B9 h_01HGWH2AEKA5X1DPWS51WRCMD4=webactivity%E3%82%AF%E3%83%A9%E3%82%B9 JavaScript-interface-class=javascript%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%BC%E3%83%95%E3%82%A7%E3%83%BC%E3%82%B9%E3%82%AF%E3%83%A9%E3%82%B9 h_01HGWH2AEK07MGR1FPFSWXYRKP=javascript%E3%82%A4%E3%83%B3%E3%82%BF%E3%83%BC%E3%83%95%E3%82%A7%E3%83%BC%E3%82%B9%E3%82%AF%E3%83%A9%E3%82%B9 h_01HGWH2AEN4WHKBSM69S200F5H=ios html-code-for-ios=ios%E5%90%91%E3%81%91%E3%81%AEhtml%E3%82%B3%E3%83%BC%E3%83%89 h_01HGWH2AENKC2EEYJPW9KZDVJS=ios%E5%90%91%E3%81%91%E3%81%AEhtml%E3%82%B3%E3%83%BC%E3%83%89 h_01HGWH2AENTMA7A71K2Y7XQF9T=%E6%B3%A8%E6%84%8F-1 h_01HGWH2AENGAWEGD5TRTR2P6PR=objective-c web-view-controller=webview%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%A9%E3%83%BC h_01HGWH2AENJVMVHSDPMKBP6HNT=webview%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%A9%E3%83%BC swift-webview-controller=swift%E3%81%AEwebview%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%A9%E3%83%BC h_01HGWH2AENV1J1M0KH36K1YSCJ=swift%E3%81%AEwebview%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%A9%E3%83%BC url-loading=url%E3%81%AE%E8%AA%AD%E3%81%BF%E8%BE%BC%E3%81%BF h_01HGWH2AENV0Q83A0GF8NK7S4B=url%E3%81%AE%E8%AA%AD%E3%81%BF%E8%BE%BC%E3%81%BF webview-implementation=webview%E3%81%AE%E5%AE%9F%E8%A3%85 h_01HGWH2AENFH6M2ZQSGH4EGEGB=webview%E3%81%AE%E5%AE%9F%E8%A3%85 html-code-for-both-android-webview-and-ios-wkwebview=html%E3%82%B3%E3%83%BC%E3%83%89android-webview%E3%81%A8ios-wkwebview%E3%81%AE%E4%B8%A1%E6%96%B9%E3%81%AB%E5%AF%BE%E5%BF%9C h_01HGWH2AENEDT95283SQZDHPCD=html%E3%82%B3%E3%83%BC%E3%83%89android-webview%E3%81%A8ios-wkwebview%E3%81%AE%E4%B8%A1%E6%96%B9%E3%81%AB%E5%AF%BE%E5%BF%9C native-implementation=%E3%83%8D%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E5%81%B4%E3%81%AE%E5%AE%9F%E8%A3%85 h_01HGWH2AENS43N93D65RN80VXN=%E3%83%8D%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E5%81%B4%E3%81%AE%E5%AE%9F%E8%A3%85 android-implementation=android%E3%81%A7%E3%81%AE%E5%AE%9F%E8%A3%85 h_01HGWH2AEN0QYYJJGV90A27VAM=android%E3%81%A7%E3%81%AE%E5%AE%9F%E8%A3%85 ios-implementation=android%E3%81%A7%E3%81%AE%E5%AE%9F%E8%A3%85 h_01HGWH2AEN38VWNXE90BHGQQ9A=android%E3%81%A7%E3%81%AE%E5%AE%9F%E8%A3%85" />

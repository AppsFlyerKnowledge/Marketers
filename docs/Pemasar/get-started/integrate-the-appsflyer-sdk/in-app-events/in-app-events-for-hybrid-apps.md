---
title: In-app event untuk aplikasi hybrid
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
  edited_at: '2023-02-15T14:50:07Z'
  id: 207031976
  locale: id
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/id/articles/207031976
---
> **Sekilas:** Rekam in-app event Aplikasi dari pengguna yang menginstal aplikasi Anda, tetapi melakukan event di situs web seluler Anda, dan bukan aplikasinya.

## Pengantar

<Anchor target="_blank" href="/marketers/id/docs/in-app-events-overview">In-app event</Anchor> yang terjadi dalam aplikasi dilaporkan menggunakan SDK. Bagaimana dengan event yang terjadi di luar aplikasi?

Ada beberapa skenario di mana event terjadi di luar konteks aplikasi:

* Event yang terjadi di situs web Anda: Implementasikan <Anchor target="_blank" href="/marketers/id/docs/people-based-attribution-pba-overview">Atribusi Berbasis Orang (PBA)</Anchor> untuk mendapatkan tinjauan  terpadu tentang perjalanan pelanggan di seluruh channel, platform termasuk situs web, dan perangkat. Ini menyediakan Web-to-App, Analisis jalur konversi, dan data lengkap.
* <Anchor target="_blank" href="/marketers/id/docs/server-to-server-events-api-for-mobile-s2s-mobile">Server backend</Anchor>: Event terjadi secara independen dari tindakan pengguna di situs web atau aplikasi. Misalnya, perpanjangan langganan otomatis
* Hybrid:  Event berlangsung di situs web seluler Anda pada perangkat yang memiliki aplikasi seperti yang dijelaskan dalam artikel. In-app event direkam dengan memanggil AppsFlyer SDK API menggunakan Javascript.

Panduan ini berkaitan dengan skenario hybrid. Pelajari cara menjembatani kesenjangan antara tampilan HTML dan tampilan asli, memungkinkan Anda merekam event dalam tampilan HTML dan mengirimkannya ke aplikasi.

> 📄 **Contoh**
>
> Anda memiliki aplikasi hybrid yang menawarkan berlangganan. Anda menerapkan formulir berlangganan dalam web view (tampilan web) yang sebenarnya dimuat dari situs web Anda.
>
> Anda dapat merekam in-app event langganan di tampilan web dan mengirim data yang terkait dengannya, seperti jenis atau harga langganan, ke kode native.
>
> Kode native mengumpulkan data dan menggunakan SDK AppsFlyer untuk mengirim in-app event langganan.
>
> [![](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)

### Mencatat in-app event di aplikasi hybrid

Dalam panduan ini kami menyediakan dua metode untuk mencatat in-app event di aplikasi hybrid:

* **[Direkomendasikan] [Antarmuka JavaScript](/docs/in-app-events-for-hybrid-apps#antarmuka-javascript)** : Menggunakan antarmuka JavaScript native untuk membangun komunikasi antara HTML atau Tampilan Web dan kode native.Dengan cara ini Anda dapat mengirim data terkait peristiwa dalam aplikasi dari tampilan web ke kode native. Setelah kode native mendapatkan data, kode ini mengirimkannya ke AppsFlyer menggunakan SDK.
* [**Pemuatan URL**](/docs/in-app-events-for-hybrid-apps#pemuatan-url): Dalam metode ini, kode native mendengarkan event pemuatan URL.Anda dapat menyetel kode asli untuk mendengarkan event pemuatan URL tertentu dan mengekstrak data dari parameter URL. Data tersebut kemudian diteruskan ke SDK.

## Antarmuka Javascript

Baik Android dan iOS memiliki antarmuka Javascript asli yang memungkinkan tampilan web memanggil kode asli.

* Android: <Anchor target="_blank" href="https://developer.android.com/guide/webapps/webview">JavascriptInterface</Anchor>
* iOS: <Anchor target="_blank" href="https://developer.apple.com/documentation/javascriptcore">JavaScriptCore</Anchor>

Keuntungan menggunakan antarmuka JavaScript native dibandingkan pemuatan URL:

* Antarmuka ini tidak memerlukan penerapan logika yang memproses pemuatan URL.
* Antarmuka native lebih disukai daripada implementasi lain.
* Tidak perlu mengurai parameter dari URL.
* Ada lebih sedikit kode sehingga lebih sedikit perawatan yang diperlukan.

Implementasinya terdiri dari langkah-langkah berikut:

1. Kode HTML untuk tampilan web atau halaman web
2. Implementasi kode asli untuk tampilan web

<div id="android" />

<Accordion title="Android">

#### Kode HTML untuk Android

Tambahkan kode HTML berikut ke tampilan web atau halaman web:

```html Markup
<h1>Recording Event From Web View</h1>
<div id="main">
 <button id="recordEvent" onclick="recordEvent()"> Record Event </button>
</div>
<script type="text/javascript">
 function recordEvent(){
 var eventName = "af_purchase"
 var eventParams = "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}";
 app.recordEvent(eventName, eventParams)
}
</script>
```

Saat meneruskan nilai event, perhatikan hal berikut:

* Pastikan untuk meneruskan nilai event sebagai JSON stringify.

  ```html Markup
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Untuk menghindari terjadinya masalah, AppsFlyer menyarankan penggunaan karakter alfanumerik huruf kecil (a-z dan 0-9) untuk nama event in-app.

#### Kelas Aktivitas Web

Buat kelas aktivitas web dengan kode berikut:

```java
public class WebActivity extends AppCompatActivity {
 WebView web;

 @Override
 public void onCreate(Bundle savedInstanceState) {
  super.onCreate(savedInstanceState);
  setContentView(R.layout.activity_web);
  web = (WebView) findViewById(R.id.webView);
  web.getSettings().setJavaScriptEnabled(true);
  web.addJavascriptInterface(new MainJsInterface(getApplicationContext()), "app");
  web.loadUrl("https://yourwebsite.com");
 }
}
```

Kode di atas membuat obyek bernama **aplikasi** yang bertindak sebagai jembatan antara tampilan web dan kode asli.

#### Kelas antarmuka JavaScript

Buat kelas MainJsInterface untuk mengimplementasikan `recordEvent()` sebagai `JavascriptInterface`

```java
public class MainJsInterface {
 Context mContext;

 MainJsInterface(Context c) {
  mContext = c;
 }

 @JavascriptInterface
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

Kode di atas mendeklarasikan metode `recordEvent` yang dapat dipanggil dalam tampilan web menggunakan Javascript.

Dalam kode HTML, Anda dapat melihat bahwa metode tersebut dipanggil menggunakan `app.recordEvent(eventName, eventParams)`. Ingatlah bahwa kami mengatur **aplikasi** untuk bertindak sebagai jembatan antara tampilan web dan kode native. Inilah sebabnya mengapa **aplikasi** dapat memanggil metode `recordEvent` yang kita definisikan di kelas MainJsInterface.

</Accordion>

<div id="ios" />

<Accordion title="iOS">

#### Kode HTML untuk iOS

Tambahkan kode HTML berikut ke tampilan web atau halaman web:

```html Markup
<body>
 <h1>Recroding Event From Web View</h1>
 <div id="main">
  <button id="recordEvent" onclick="recordEvent()"> Record Event </button>
 </div>
 <script type="text/javascript">
 function recordEvent(){
  var eventName = "af_purchase"
  var eventParams = "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}";
  webkit.messageHandlers.event.postMessage(eventName + "+" + eventParams);
 }
 </script>
</body>
```

Kode di atas menetapkan fungsi yang akan dipicu saat tombol diklik. Fungsi ini mengatur variabel `eventName` dan `eventParams` dan meneruskannya ke kode asli menggunakan `webkit.messageHandlers` .

Saat meneruskan nilai event, perhatikan hal berikut:

* Pastikan untuk meneruskan nilai event sebagai JSON stringify.

  ```html Markup
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Untuk menghindari terjadinya masalah, AppsFlyer menyarankan penggunaan karakter alfanumerik huruf kecil (a-z dan 0-9) untuk nama event in-app.

> 📘 **Catatan**
>
> Kode HTML untuk Objective C dan Swift.

#### Tujuan c

#### Pengontrol tampilan web

Di pengontrol web view (tampilan web) Anda, tambahkan kode berikut di pengontrol tampilan.

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

Kode di atas menerima pesan dari tampilan web. Pesan tersebut berisi nama event dan nilai event. Saat kode mendeteksi pesan masuk, kode akan meneruskannya ke metode `recordEvent` yang mengurai nilai dan memanggil metode `logEvent` SDK native.

#### Pengontrol Swift WebView

Di pengontrol web view (tampilan web) Anda, tambahkan kode berikut dalam metode `viewDidLoad`

```swift
import WebKit
import UIKit
import AppsFlyerLib
import JavaScriptCore

class JSViewController: UIViewController, WKNavigationDelegate, WKScriptMessageHandler {
 func userContentController(_ userContentController: WKUserContentController, didReceive message: WKScriptMessage) {
  let messageBody = message.body as? String
  let eventName = messageBody?.components(separatedBy: "+")[0]
  let eventValue = messageBody?.components(separatedBy: "+")[1]
  recordEvent(eventName: eventName!, eventValue: eventValue!)
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

Kode di atas menerima pesan dari tampilan web. Pesan tersebut berisi nama event dan nilai event. Saat kode mendeteksi pesan masuk, kode akan meneruskannya ke metode `recordEvent` yang mengurai nilai dan memanggil metode `logEvent` SDK.

</Accordion>

## Pemuatan URL

Baik Android dan iOS menerapkan metode asli yang merespons event pemuatan url. Metode ini memungkinkan Anda melakukan hal berikut:

* Dengarkan event pemuatan URL tertentu
* Ekstrak parameter yang ditambahkan ke URL
* Gunakan parameter ini dalam kode asli

Implementasi di bawah ini terdiri dari dua langkah:

1. Kode HTML untuk tampilan web atau halaman web
2. Penerapan kode asli untuk pemuatan URL

### Implementasi Tampilan Web

#### Kode HTML (untuk Android WebView dan iOS UIWebView)

```html Markup
<html>
<head>
</head>
 <body>
  <h1>Recording From Web View</h1>
  <div id="main">
   <input id="button" type="button" value="Record Event" />
  </div>
  <script type="text/javascript">
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

Kode di atas dapat menjadi bagian dari halaman web yang sebenarnya atau dimuat secara native ke tampilan web.

Kode di atas menetapkan fungsi yang akan dipicu saat tombol diklik. Fungsi itu sendiri membuat elemen iframe yang memuat URL khusus. Pemuatan URL inilah yang memicu metode native Android atau iOS yang kemudian memanggil metode logEvent SDK `logEvent` .

Semua parameter yang diperlukan (nama event dan nilai event) ditambahkan ke URL. Contoh kode Android dan iOS di bawah ini menunjukkan cara mengekstrak parameter ini dan meneruskannya ke metode SDK `logEvent` .

Saat meneruskan nilai event, perhatikan hal berikut:

* Pastikan untuk meneruskan nilai event sebagai JSON stringify.

  ```html Markup
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Untuk menghindari terjadinya masalah, AppsFlyer menyarankan penggunaan karakter alfanumerik huruf kecil (a-z dan 0-9) untuk nama event in-app.

### Implementasi asli

<Tabs>
<Tab title="Android">

#### Implementasi Android

Android WebView menggunakan WebViewClient yang menerima notifikasi dari tampilan web. Di `shouldOverrideUrlLoading` , Anda dapat menangani peristiwa pemuatan URL yang berasal dari tampilan web:

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

#### Implementasi iOS

<Tabs>
<Tab title="Tujuan C">

Di pengontrol tampilan web Anda, tambahkan kode berikut dalam metode `shouldStartLoadWithRequest`

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

Kode di atas mendengarkan pemuatan URL apa pun. Jika URL dengan "af-event" di dalamnya dimuat, itu akan memicu metode `recordEvent` asli. Metode `recordEvent` native mengekstrak parameter yang diperlukan (eventName dan eventValue) dan meneruskannya ke metode `logEvent` SDK native.

</Tab>

<Tab title="Swift">

Di pengontrol tampilan web Anda, tambahkan kode berikut di metode `webView`

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

Kode di atas mendengarkan pemuatan URL apa pun. Jika URL dengan "af-event" di dalamnya dimuat, ini mengekstrak parameter yang diperlukan (eventName dan eventValue) dan meneruskannya ke metode `logEvent` SDK native.

</Tab>
</Tabs>

</Tab>
</Tabs>

<div data-zendesk-anchors="introduction=pengantar recording-inapp-events-in-hybrid-apps=mencatat-in-app-event-di-aplikasi-hybrid javascript-interface=antarmuka-javascript html-code-for-android=kode-html-untuk-android webactivity-class=kelas-aktivitas-web javascript-interface-class=kelas-antarmuka-javascript html-code-for-ios=kode-html-untuk-ios objective-c=tujuan-c web-view-controller=pengontrol-tampilan-web swift-webview-controller=pengontrol-swift-webview url-loading=pemuatan-url webview-implementation=implementasi-tampilan-web html-code-for-both-android-webview-and-ios-wkwebview=kode-html-untuk-android-webview-dan-ios-uiwebview native-implementation=implementasi-asli android-implementation=implementasi-android ios-implementation=implementasi-android" />

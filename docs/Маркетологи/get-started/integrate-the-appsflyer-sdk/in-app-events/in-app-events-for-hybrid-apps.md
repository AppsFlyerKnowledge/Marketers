---
title: Внутренние события гибридных приложений
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
  edited_at: '2026-08-19T00:13:13Z'
  id: 207031976
  locale: ru
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ru/articles/207031976
---
> **Краткий обзор.** Регистрируйте внутренние события приложения из веб-просмотров, встроенных в ваше мобильное приложение, обеспечивая полное измерение событий, даже если взаимодействие происходит в веб-контенте внутри приложения.

## Введение

<Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview">События в приложении</Anchor>, произошедшие внутри приложения, сообщаются с помощью SDK. Как быть с событиями, происходящими за пределами приложения?

События происходят вне контекста приложения в следующих сценариях:

* События, происходящие на вашем сайте: Внедрите <Anchor target="_blank" href="/marketers/ru/docs/people-based-attribution-pba-overview">атрибуцию People-Based (PBA)</Anchor>, чтобы получить единое представление о пути клиентов по каналам, платформам, включая веб-сайт, и устройствам. Это позволит вам анализировать переходы с сайта в приложение, пути конверсии и сырые данные.
* <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">Внутренние серверы</Anchor>: События происходят независимо от действий пользователя на сайте или в приложении. Например, автоматическое продление подписки.
* Гибридные:  Событие происходит на вашем мобильном сайте на устройстве с приложением, как описано в этой статье. Внутренние события регистрируются путем вызова API SDK AppsFlyer с использованием JavaScript.

В этом руководстве рассматривается гибридный сценарий. Узнайте, как преодолеть разрыв между HTML-представлением и нативными представлениями, чтобы регистрировать события в HTML-представлении и отправлять их в приложение.

> 📘 **Примечание**
>
> Если ваше приложение интегрирует AppsFlyer **с помощью гибридного плагина** (например, Cordova, Ionic, React Native или Flutter), метод мостового взаимодействия, описанный в этом руководстве, не применим.
>
> Мы рекомендуем отправлять события на основе WebView с помощью <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">server-to-server (S2S) API AppsFlyer</Anchor>.

> 📄 **Пример**
>
> У вас есть гибридное приложение, которое предлагает подписку. Вы реализуете форму подписки в веб-представлении, которое загружается с вашего сайта.
>
> Вы можете зарегистрировать внутреннее событие подписки в веб-представлении и отправить связанные с ним данные, такие как тип или стоимость подписки, в нативный код.
>
> Нативный код собирает эти данные и использует SDK AppsFlyer для отправки внутреннего события подписки.
>
> [![](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)

### Запись внутренних событий в гибридных приложениях

В этом руководстве мы предлагаем два метода записи событий в гибридных приложениях:

* **[Рекомендуется]** [**Интерфейс JavaScript**](/docs/in-app-events-for-hybrid-apps#интерфейс-javascript): Использует собственный интерфейс JavaScript для установления связи между HTML или веб-представлением и собственным кодом. Такм образом, можно отправлять данные, связанные с внутренними событиями, из веб-представления в нативный код. Получив данные, нативный код с помощью SDK отправляет их в AppsFlyer.
* [**Загрузка URL**](/docs/in-app-events-for-hybrid-apps#загрузка-url): Нативный код отслеживает события загрузки URL-адреса. Вы можете настроить отслеживание событий загрузки определенных URL-адресов и извлечение данных из параметров URL. Затем данные передаются в SDK.

## Интерфейс JavaScript

И в Android, и в iOS есть нативные интерфейсы JavaScript, которые позволяют веб-представлениям вызывать нативный код.

* Android: <Anchor target="_blank" href="https://developer.android.com/guide/webapps/webview">JavaScriptInterface</Anchor>
* iOS: <Anchor target="_blank" href="https://developer.apple.com/documentation/JavaScriptcore">JavaScriptCore</Anchor>

Преимущества использования нативного интерфейса JavaScript перед загрузкой URL-адреса:

* Не требуется реализация логики, отслеживающей загрузку URL-адреса.
* Нативные интерфейсы предпочтительнее других реализаций.
* Не требуется парсинг параметров из URL-адреса.
* Кода меньше, а значит его проще поддерживать.

Реализация состоит из следующих шагов:

1. HTML-код для веб-представления или веб-страницы.
2. Реализация нативного кода для веб-представления

<div id="android" />

<Accordion title="Android;">

#### HTML-код для Android

Добавьте следующий HTML-код в веб-представление или на веб-страницу:

```html Markup
<h1>Запись события из WebView</h1>
<div id="main">
 <button id="recordEvent" onclick="recordEvent()"> Записать событие </button>
</div>
<script type="text/JavaScript">
<!-- Установить идентификатор пользователя клиента -->
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

Передавая значение события, помните о следующем:

* Обязательно передавайте значение события в виде строкового JSON.

  ```html Markup
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Во избежание возможных проблем AppsFlyer рекомендует для имен внутренних событий приложений использовать только строчные буквенно-цифровые символы (a-z и 0-9).

#### Класс WebActivity

Создайте класс веб-активности со следующим кодом:

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

Приведенный выше код создает объект под названием **app**, который служит мостом между веб-представлением и нативным кодом.

#### Класс интерфейса JavaScript

Создайте класс MainJsInterface, чтобы реализовать `recordEvent()` как `JavaScriptInterface`

```java
public class MainJsInterface {
 Context mContext;

 MainJsInterface(Context c) {
  mContext = c;
 }

 //Установить идентификатор пользователя клиента
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

В приведенном выше коде объявлен метод `recordEvent`, который может быть вызван в веб-представлении с помощью JavaScript.

В HTML-коде видно, что метод вызывается с помощью `app.recordEvent(eventName, eventParams)`. Напомним, что настроили **приложение** как мост между веб-представлением и нативным кодом. Поэтому **app** может вызвать метод `recordEvent`, который мы определили в классе MainJsInterface.

</Accordion>

<Accordion title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

#### HTML-код для iOS

Добавьте следующий HTML-код в веб-представление или на веб-страницу:

```html Markup
<body>
 <h1>Запись события из WebView</h1>
 <div id="main">
  <button id="recordEvent" onclick="recordEvent()"> Записать событие </button>
 </div>
 <script type="text/JavaScript">
   <!-- Установить идентификатор пользователя клиента --> 
   function setCustomerUserId(){  
    webkit.messageHandlers.cuid.postMessage(customerUserId); 
   }
   function recordEvent(){
    var eventName = "af_purchase"
    var eventParams = "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}";
    webkit.messageHandlers.event.postMessage(eventName + "+" + eventParams);
   }
 </script>
</body>
```

Приведенный выше код задает функцию, которая будет срабатывать при нажатии на кнопку. Функция устанавливает переменные `eventName` и `eventParams` и передает их нативному коду с помощью `webkit.messageHandlers`.

Передавая значение события, помните о следующем:

* Обязательно передавайте значение события в виде строкового JSON.

  ```html Markup
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Во избежание возможных проблем AppsFlyer рекомендует для имен внутренних событий приложений использовать только строчные буквенно-цифровые символы (a-z и 0-9).

> 📘 **Примечание**
>
> HTML-код подходит и для Objective C, и для Swift.

#### Objective c

#### Контроллер веб-представления

Добавьте в контроллер веб-представления следующий код.

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

Приведенный выше код получает сообщение из веб-представления. Сообщение содержит имя и значение события. Когда код обнаруживает входящее сообщение, он передает его методу `recordEvent`, который разбирает значения и вызывает собственный метод SDK `logEvent`.

#### Контроллер Swift WebView

В контроллере веб-представления добавьте следующий код:

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
      AppsFlyerLib.shared().customerUserID = message.body as? 
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

Приведенный выше код получает сообщение из веб-представления. Сообщение содержит имя и значение события. Когда код обнаруживает входящее сообщение, он передает его методу `recordEvent`, который разбирает значения и вызывает метод AppsFlyer SDK `logEvent`.

</Accordion>

## Загрузка URL

И в Android, и в iOS реализован нативный метод, который прослушивает события загрузки url. Этот метод позволяет сделать следующее:

* Отслеживать событие загрузки конкретного URL-адреса.
* Извлекать параметры, добавленные в URL-адрес.
* Используйте эти параметры в нативном коде

Приведенная ниже реализация состоит из двух шагов:

1. HTML-код для веб-представления или веб-страницы.
2. Реализация нативного кода для загрузки URL

### Реализация веб-представления (WebView)

#### HTML-код (для Android WebView и iOS WKWebView)

```html Markup
<html>
<head>
</head>
 <body>
  <h1>Запись из Web View</h1>
  <div id="main">
   <input id="button" type="button" value="Записать событие" />
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

Приведенный выше код может находиться на реальной веб-странице или загружаться нативно в веб-представление.

В коде задана функция, вызываемая при нажатии кнопки. Сама функция создает элемент iframe, который загружает настраиваемый URL-адрес. Именно загрузка этого URL запускает нативный метод Android или iOS, который в свою очередь вызывает метод `logEvent` SDK AppsFlyer.

Все обязательные параметры (имя и значения события) добавляются в URL-адрес. В следующих примерах кода для Android и iOS показано, как извлечь и передать эти параметры в метод `logEvent` SDK AppsFlyer.

Передавая значение события, помните о следующем:

* Обязательно передавайте значение события в виде строкового JSON.

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Во избежание возможных проблем AppsFlyer рекомендует для имен внутренних событий приложений использовать только строчные буквенно-цифровые символы (a-z и 0-9).

### Нативная реализация

<Tabs>
<Tab title="Android">

#### Реализация Android

Android WebView использует WebViewClient, который получает уведомления от веб-представления. В `shouldOverrideUrlLoading` вы можете обрабатывать события загрузки URL, которые приходят из веб-представления:

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

#### Реализация iOS

<Tabs>
<Tab title="Objective-C">

В контроллере веб-представления добавьте следующий код в метод `shouldStartLoadWithRequest`.

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

Приведенный выше код отслеживает загрузку любого URL-адреса. Если загружается URL-адрес с параметром "af-event", он вызывает нативный метод `recordEvent`. Нативный метод `recordEvent` извлекает необходимые параметры (eventName и eventValue) и передает их в метод SDK `logEvent`.

</Tab>

<Tab title="Swift">

В контроллере веб-представления добавьте следующий код в метод `webView(_:decidePolicyFor:decisionHandler:)`.

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
   false){

   let scanner = Scanner(string: pageUrl!)
   scanner.charactersToBeSkipped = CharacterSet(charactersIn: "&?")
   scanner.scanUpTo("?", into: nil)
   var tempString, eventName : NSString?
   scanner.charactersToBeSkipped = CharacterSet(charactersIn: "&?")
   false){

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

Приведенный выше код отслеживает загрузку любого URL-адреса. Если загружается URL-адрес с параметром "af-event", он извлекает необходимые параметры (eventName и eventValue) и передает их в нативный метод SDK `logEvent`.

</Tab>
</Tabs>

</Tab>
</Tabs>

<div data-zendesk-anchors="introduction=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01HGWH2AEJ0DHTGD41YN7R5A1V=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01KB7M7ZSM5AZACJNB32F65A62=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HGWH2AEJZHV3KZR0ZPPFK71T=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 recording-inapp-events-in-hybrid-apps=%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8C-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%B3%D0%B8%D0%B1%D1%80%D0%B8%D0%B4%D0%BD%D1%8B%D1%85-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F%D1%85 h_01HGWH2AEJFEZY7WBJTFP9N3AN=%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8C-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%B3%D0%B8%D0%B1%D1%80%D0%B8%D0%B4%D0%BD%D1%8B%D1%85-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F%D1%85 JavaScript-interface=%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81-javascript h_01HGWH2AEJFVDZBPRS8DP64TRY=%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81-javascript h_01HGWH2AEKB47CJ386AN7NNX4Y=android html-code-for-android=html-%D0%BA%D0%BE%D0%B4-%D0%B4%D0%BB%D1%8F-android h_01HGWH2AEKZG98VWPECP6FBHN3=html-%D0%BA%D0%BE%D0%B4-%D0%B4%D0%BB%D1%8F-android webactivity-class=%D0%BA%D0%BB%D0%B0%D1%81%D1%81-webactivity h_01HGWH2AEKA5X1DPWS51WRCMD4=%D0%BA%D0%BB%D0%B0%D1%81%D1%81-webactivity JavaScript-interface-class=%D0%BA%D0%BB%D0%B0%D1%81%D1%81-%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81%D0%B0-javascript h_01HGWH2AEK07MGR1FPFSWXYRKP=%D0%BA%D0%BB%D0%B0%D1%81%D1%81-%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81%D0%B0-javascript ios=%D0%BA%D0%BB%D0%B0%D1%81%D1%81-%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81%D0%B0-javascript h_01HGWH2AEN4WHKBSM69S200F5H=%D0%BA%D0%BB%D0%B0%D1%81%D1%81-%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81%D0%B0-javascript html-code-for-ios=html-%D0%BA%D0%BE%D0%B4-%D0%B4%D0%BB%D1%8F-ios h_01HGWH2AENKC2EEYJPW9KZDVJS=html-%D0%BA%D0%BE%D0%B4-%D0%B4%D0%BB%D1%8F-ios h_01HGWH2AENTMA7A71K2Y7XQF9T=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01HGWH2AENGAWEGD5TRTR2P6PR=objective-c web-view-controller=%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D0%BB%D0%B5%D1%80-%D0%B2%D0%B5%D0%B1-%D0%BF%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F h_01HGWH2AENJVMVHSDPMKBP6HNT=%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D0%BB%D0%B5%D1%80-%D0%B2%D0%B5%D0%B1-%D0%BF%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F swift-webview-controller=%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D0%BB%D0%B5%D1%80-swift-webview h_01HGWH2AENV1J1M0KH36K1YSCJ=%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D0%BB%D0%B5%D1%80-swift-webview url-loading=%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-url h_01HGWH2AENV0Q83A0GF8NK7S4B=%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-url webview-implementation=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-%D0%B2%D0%B5%D0%B1-%D0%BF%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-webview h_01HGWH2AENFH6M2ZQSGH4EGEGB=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-%D0%B2%D0%B5%D0%B1-%D0%BF%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-webview html-code-for-both-android-webview-and-ios-wkwebview=html-%D0%BA%D0%BE%D0%B4-%D0%B4%D0%BB%D1%8F-android-webview-%D0%B8-ios-wkwebview h_01HGWH2AENEDT95283SQZDHPCD=html-%D0%BA%D0%BE%D0%B4-%D0%B4%D0%BB%D1%8F-android-webview-%D0%B8-ios-wkwebview native-implementation=%D0%BD%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D0%B0%D1%8F-%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F h_01HGWH2AENS43N93D65RN80VXN=%D0%BD%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D0%B0%D1%8F-%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F android-implementation=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-android h_01HGWH2AEN0QYYJJGV90A27VAM=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-android ios-implementation=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-android h_01HGWH2AEN38VWNXE90BHGQQ9A=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-android" />

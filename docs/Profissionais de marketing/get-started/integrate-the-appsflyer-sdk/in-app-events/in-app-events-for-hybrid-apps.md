---
title: Eventos in-app para aplicativos híbridos
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
  edited_at: '2026-08-19T00:13:09Z'
  id: 207031976
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/207031976
---
> **Resumo:** Registre eventos in-app de visualizações da web incorporadas ao seu app mobile para mensurar seus eventos por completo, mesmo quando a interação ocorre em um conteúdo web-based.

<div id="introduction" />

## Introdução

<Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">Eventos</Anchor> que ocorrem dentro do aplicativo são relatados usando o SDK. Mas e quanto aos eventos que ocorrem fora do aplicativo?

Nesse caso, existem alguns cenários possíveis:

* Eventos que ocorrem no seu site: Implemente <Anchor target="_blank" href="/marketers/pt/docs/people-based-attribution-pba-overview">People-Based Attribution (PBA)</Anchor> para ter uma visão centralizada das jornadas dos seus clientes em canais, plataformas (incluindo seu site) e dispositivos. Assim, você consegue analisar jornadas web-to-app, caminhos de conversão e dados brutos.
* <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">Servidores de back-end</Anchor>: os eventos ocorrem independentemente da ação do usuário no site ou no aplicativo. Por exemplo, renovação automática de assinatura
* Híbrido:  o evento ocorre em seu site mobile em um dispositivo com o aplicativo, conforme descrito neste artigo. Os eventos in-app são registrados chamando a SDK API da AppsFlyer usando Javascript.

Esse artigo foca em um cenário híbrido. Vamos falar sobre como você pode conectar a visualização HTML e as visualizações nativas, permitindo que você grave eventos na visualização HTML e os envie para o aplicativo.

<div id="note" />

> 📘 **Observação:**
>
> Se o seu aplicativo integra o AppsFlyer **usando um plugin híbrido** (por exemplo, Cordova, Ionic, React Native ou Flutter), o método de bridging descrito neste guia não se aplica.
>
> Recomendamos enviar eventos baseados em WebView usando a <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">API server-to-server (S2S) da AppsFlyer</Anchor>.

<div id="example" />

> 📄 **Exemplo**
>
> Você tem um aplicativo híbrido que oferece inscrições. Você implementa o formulário de inscrição em uma exibição da web que na verdade carrega a partir do seu site.
>
> Você pode gravar o evento in-app de inscrição na visualização da web e enviar dados relacionados a ele, como tipo de assinatura ou preço, para o código nativo.
>
> O código nativo coleta os dados e usa o SDK da AppsFlyer para enviar o evento in-app de inscrição.
>
> [![](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)](https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png)

<div id="recording-in-app-events-in-hybrid-apps" />

### Registro de eventos in-app em aplicativos híbridos

Neste guia, oferecemos dois métodos para registrar eventos in-app em aplicativos híbridos:

* **[Recomendado]** [**interface JavaScript**](/docs/in-app-events-for-hybrid-apps#interface-javascript): use a interface JavaScript nativa para estabelecer comunicação entre o HTML ou Web View e o código nativo. Dessa forma, você pode enviar dados relacionados a eventos in-app do web view para o código nativo. Depois que o código nativo obtém os dados, ele os envia para a AppsFlyer usando o SDK.
* [**Carregamento de URL**](/docs/in-app-events-for-hybrid-apps#carregamento-de-url): nesse método, o código nativo ouve os eventos de carregamento de URL. Você pode definir o código nativo para ouvir eventos de carregamento de URLs específicos e extrair dados dos parâmetros de URL. Em seguida, os dados são passados para o SDK.

<div id="javascript-interface" />

## Interface Javascript

Tanto o Android quanto o iOS têm interfaces Javascript nativas que permitem que web views façam chamadas para o código nativo.

* Android: <Anchor target="_blank" href="https://developer.android.com/guide/webapps/webview">JavaScriptInterface</Anchor>
* iOS: <Anchor target="_blank" href="https://developer.apple.com/documentation/JavaScriptcore">JavaScriptCore</Anchor>

Vantagens de usar a interface JavaScript nativa em relação ao carregamento de URL:

* Não requer a implementação de lógica para o carregamento de URL.
* Interfaces nativas são preferíveis a outras implementações.
* Não há necessidade de analisar os parâmetros do URL.
* Há menos código e, portanto, menos manutenção necessária.

A implementação consiste nas seguintes etapas:

1. Código HTML para visualização da web ou página da web
2. Implementação de código nativo para webview

<div id="android" />

<Accordion title="com o Android">

<div id="html-code-for-android" />

#### Código HTML para Android

Adicione o seguinte código HTML à exibição da web ou página da web:

```html Markup
<h1>Registro de evento da web view</h1>
<div id="main">
 <button id="recordEvent" onclick="recordEvent()"> Registrar evento </button>
</div>
<script type="text/JavaScript">
<!-- Definir ID de usuário do cliente -->
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

Ao transferir o valor do evento, lembre-se do seguinte:

* Certifique-se de transferir o valor do evento como JSON em string.

  ```html Markup
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Para evitar eventuais problemas o AppsFlyer recomenda usar apenas caracteres alfanuméricos minúsculos (a-z e 0-9) para nomes de eventos no aplicativo.

<div id="webactivity-class" />

#### Classe WebActivity

Crie uma classe de atividade da web com o seguinte código:

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

O código acima cria um objeto chamado **app** que atua como a ponte entre a exibição da web e o código nativo.

<div id="ios" />

<div id="javascript-interface-class" />

#### Classe de interface JavaScript

Crie uma classe MainJsInterface para implementar `recordEvent()` como`JavaScriptInterface`

```java
public class MainJsInterface {
 Context mContext;

 MainJsInterface(Context c) {
  mContext = c;
 }

 //Definir ID de usuário do cliente
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

O código acima declara um método `recordEvent` que pode ser chamado na exibição da web usando Javascript.

No código HTML, você pode ver que o método é chamado usando `app.recordEvent(eventName, eventParams)`. Lembre-se de que configuramos o **aplicativo** para atuar como a ponte entre a visualização da web e o código nativo. É por isso que o **app** pode chamar o método `recordEvent` que definimos na classe MainJsInterface.

</Accordion>

<Accordion title="/docs/ctv-pc-and-console-platform-attribution-concepts">

<div id="html-code-for-ios" />

#### Código HTML para iOS

Adicione o seguinte código HTML à exibição da web ou página da web:

```html Markup
<body>
 <h1>Registro de evento da web view</h1>
 <div id="main">
  <button id="recordEvent" onclick="recordEvent()"> Registrar evento </button>
 </div>
 <script type="text/JavaScript">
   <!-- Definir ID de usuário do cliente --> 
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

O código acima define uma função a ser acionada quando um botão é clicado. A função define `eventName` e as variáveis `eventParams`, enviando-as para o código nativo usando `webkit.messageHandlers`.

Ao transferir o valor do evento, lembre-se do seguinte:

* Certifique-se de transferir o valor do evento como JSON em string.

  ```html Markup
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Para evitar eventuais problemas, a AppsFlyer recomenda usar apenas caracteres alfanuméricos minúsculos (a-z e 0-9) para nomes de eventos no aplicativo.

<div id="note-1" />

> 📘 **Observação:**
>
> O código HTML deve ser usado para Objective C e Swift.

#### Objective c

<div id="web-view-controller" />

#### Controlador de exibição da web

Em seu controlador de exibição da web, adicione o seguinte código no controlador de exibição.

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

O código acima recebe a mensagem da visualização da web. A mensagem contém o nome e o valor do evento. Quando o código detecta a mensagem recebida, ele a transmite para o método `recordEvent` , que analisa os valores e chama o método `logEvent` do SDK nativo.

<div id="swift-webview-controller" />

#### Controlador WebView Swift

No seu controlador de visualização da web, adicione o seguinte código:

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
    String
    }
 }

 var webView: WKWebView! override func loadView(){
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

  let eventValuesData = eventValue.data(using: String.
  Encoding.utf8)
  do {
   eventValueDict = try (JSONSerialization.jsonObject(with: eventValuesData!, options:[]) as? [String: String])!
  } catch let error as NSError{
   print(error)
  }

  AppsFlyerLib.shared().logEvent(eventName as String?, withValues: eventValueDict)
 }

}
```

O código acima recebe a mensagem da visualização da web. A mensagem contém o nome e o valor do evento. Quando o código detecta a mensagem recebida, ele a transmite para o método `recordEvent` , que analisa os valores e chama o método `logEvent` do SDK da AppsFlyer.

</Accordion>

<div id="url-loading" />

## Carregamento de URL

Tanto o Android quanto o iOS implementam um método nativo que escuta eventos de carregamento de URL. Tanto o Android quanto o iOS implementam um método nativo que escuta eventos de carregamento de URL.

* Ouça um evento de carregamento de uma URL específica
* Extraia parâmetros que são anexados à URL
* Use esses parâmetros no código nativo

A implementação a seguir consiste em duas etapas:

1. Implementação de código nativo para carregamento de URL
2. Implementação de código nativo para carregamento de URL

<div id="webview-implementation" />

### Implementação do Android O Android WebView usa um WebViewClient que recebe notificações da exibição da web.

<div id="html-code-for-both-android-webview-and-ios-wkwebview" />

#### Implementação do WebView

```html Markup
<html>
<head>
</head>
 <body>
  <h1>Registro da web view</h1>
  <div id="main">
   <input id="button" type="button" value="Registrar evento" />
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

O código acima pode ser parte de uma página da web real ou carregado nativamente na visualização da web.

O código define uma função a ser acionada quando um botão é clicado. A função em si cria um elemento iframe que carrega uma URL personalizada. É esse carregamento de URL que aciona o método nativo do Android ou iOS, e chama o método `logEvent` do SDK da AppsFlyer.

Todos os parâmetros necessários (nome do evento e valores do evento) são anexados à URL. Os exemplos de código Android e iOS abaixo demonstram como extrair esses parâmetros e passá-los para o método `logEvent` do SDK da AppsFlyer.

Ao transferir o valor do evento, lembre-se do seguinte:

* Certifique-se de transferir o valor do evento como JSON em string.

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Para evitar eventuais problemas o AppsFlyer recomenda usar apenas caracteres alfanuméricos minúsculos (a-z e 0-9) para nomes de eventos no aplicativo.

<div id="native-implementation" />

### Implementação nativa

<Tabs>
<Tab title="Android">

<div id="android-implementation" />

#### Implementação do Android

O Android WebView usa um WebViewClient que recebe notificações da exibição da web. Em `shouldOverrideUrlLoading`, você pode manipular eventos de carregamento de URL que vêm da web view:

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

<div id="ios-implementation" />

#### Implementação iOS

<Tabs>
<Tab title="Objective C">

Em `shouldOverrideUrlLoading`, você pode lidar com eventos de carregamento de URL que vêm do web view:

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

O código acima ouve qualquer carregamento de URL. Se uma URL com "af-event" for carregada, ela aciona o método nativo `recordEvent`. O método nativo `recordEvent` extrai os parâmetros necessários (eventName e eventValue) e os envia para o método `logEvent` do SDK nativo.

</Tab>

<Tab title="Swift">

Este método permite que você faça o seguinte:

```swift
import WebKit
import UIKit
import AppsFlyerLib
class WebViewController: UIViewController, WKNavigationDelegate {
 var webView: WKWebView!
 webView.load(URLRequest(url: url))
  webView.configuration.userContentController.add(self, name:"event")
 }

 func recordEvent(eventName: String, eventValue: String) {

  var eventValueDict = [String: String]()

  let eventValuesData = eventValue.data(using: String.
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
   var eventValue:
   false){

   let scanner = Scanner(string: pageUrl!)
   scanner.charactersToBeSkipped = CharacterSet(charactersIn: "&?")
   scanner.scanUpTo("?", into: nil)
   var tempString, eventName : NSString?
   var eventValue:
   [String: String] = Dictionary()

   while(scanner.scanUpTo("&", into: &tempString)){

    if let tempString = tempString {
     if(tempString.hasPrefix("eventName=") && tempString.length > 10){
      eventName = tempString.substring(from: 10) as NSString
     }
     if(tempString.hasPrefix("eventValue=") && tempString.length > 11){
      let eventValues = tempString.components(separatedBy: "=")[1].removingPercentEncoding
      let eventValuesData = eventValues?.data(using: String. Encoding.utf8)
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
     // registrar evento
     AppsFlyerLib.shared().logEvent(eventName as String?, withValues: eventValue)
    }

   }

  }

 }

}
```

O código acima ouve qualquer carregamento de URL. Se uma URL com "af-event" for carregada, ela extrairá os parâmetros necessários (eventName e eventValue) e os transmitirá para o método `logEvent`logEventlogEvent do SDK nativo.

</Tab>
</Tabs>

</Tab>
</Tabs>

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01HGWH2AEJ0DHTGD41YN7R5A1V=introdu%C3%A7%C3%A3o h_01KB7M7ZSM5AZACJNB32F65A62=observa%C3%A7%C3%A3o h_01HGWH2AEJZHV3KZR0ZPPFK71T=exemplo recording-inapp-events-in-hybrid-apps=registro-de-eventos-in-app-em-aplicativos-h%C3%ADbridos h_01HGWH2AEJFEZY7WBJTFP9N3AN=registro-de-eventos-in-app-em-aplicativos-h%C3%ADbridos JavaScript-interface=interface-javascript h_01HGWH2AEJFVDZBPRS8DP64TRY=interface-javascript h_01HGWH2AEKB47CJ386AN7NNX4Y=android html-code-for-android=c%C3%B3digo-html-para-android h_01HGWH2AEKZG98VWPECP6FBHN3=c%C3%B3digo-html-para-android webactivity-class=classe-webactivity h_01HGWH2AEKA5X1DPWS51WRCMD4=classe-webactivity JavaScript-interface-class=classe-de-interface-javascript h_01HGWH2AEK07MGR1FPFSWXYRKP=classe-de-interface-javascript ios=classe-de-interface-javascript h_01HGWH2AEN4WHKBSM69S200F5H=classe-de-interface-javascript html-code-for-ios=c%C3%B3digo-html-para-ios h_01HGWH2AENKC2EEYJPW9KZDVJS=c%C3%B3digo-html-para-ios h_01HGWH2AENTMA7A71K2Y7XQF9T=observa%C3%A7%C3%A3o-1 h_01HGWH2AENGAWEGD5TRTR2P6PR=objective-c web-view-controller=controlador-de-exibi%C3%A7%C3%A3o-da-web h_01HGWH2AENJVMVHSDPMKBP6HNT=controlador-de-exibi%C3%A7%C3%A3o-da-web swift-webview-controller=controlador-webview-swift h_01HGWH2AENV1J1M0KH36K1YSCJ=controlador-webview-swift url-loading=carregamento-de-url h_01HGWH2AENV0Q83A0GF8NK7S4B=carregamento-de-url webview-implementation=implementa%C3%A7%C3%A3o-do-android-o-android-webview-usa-um-webviewclient-que-recebe-notifica%C3%A7%C3%B5es-da-exibi%C3%A7%C3%A3o-da-web h_01HGWH2AENFH6M2ZQSGH4EGEGB=implementa%C3%A7%C3%A3o-do-android-o-android-webview-usa-um-webviewclient-que-recebe-notifica%C3%A7%C3%B5es-da-exibi%C3%A7%C3%A3o-da-web html-code-for-both-android-webview-and-ios-wkwebview=implementa%C3%A7%C3%A3o-do-webview h_01HGWH2AENEDT95283SQZDHPCD=implementa%C3%A7%C3%A3o-do-webview native-implementation=implementa%C3%A7%C3%A3o-nativa h_01HGWH2AENS43N93D65RN80VXN=implementa%C3%A7%C3%A3o-nativa android-implementation=implementa%C3%A7%C3%A3o-do-android h_01HGWH2AEN0QYYJJGV90A27VAM=implementa%C3%A7%C3%A3o-do-android h_01HGWH2AEN38VWNXE90BHGQQ9A=ios-implementation" />

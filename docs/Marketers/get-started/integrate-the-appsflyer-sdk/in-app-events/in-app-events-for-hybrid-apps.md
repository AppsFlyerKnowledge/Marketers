---
title: Eventos in-app para aplicaciones híbridas
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
  edited_at: '2026-08-12T12:00:59Z'
  id: 207031976
  locale: es
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/es/articles/207031976
---
> **En resumen:** Registra eventos in-app a partir de vistas web integradas en tu aplicación móvil, lo que permite la medición completa de eventos incluso cuando la interacción ocurre dentro del contenido web de la aplicación.

<div id="introduction" />

## Introducción

Los <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">eventos in-app</Anchor> que ocurren dentro de la aplicación se reportan mediante el SDK. ¿Qué pasa con los eventos que ocurren fuera de la aplicación?

Hay algunos escenarios en los que ocurren eventos fuera del contexto de la aplicación:

* Eventos que tienen lugar en tu sitio web: Implementa la <Anchor target="_blank" href="/marketers/es/docs/people-based-attribution-pba-overview">Atribución people-based (PBA)</Anchor> para obtener una vista unificada de los viajes de los clientes a través de canales, plataformas, incluido el sitio web y dispositivos. Esto te ofrece web-to-app, análisis de rutas de conversión y raw data.
* <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">Servidores backend</Anchor>: Los eventos ocurren independientemente de la acción del usuario en el sitio web o la aplicación. Por ejemplo, renovación automática de suscripción
* Híbrido:  El evento se lleva a cabo en tu sitio web móvil en un dispositivo que tiene la aplicación como se describe en este artículo. Los eventos in-app se atribuyen llamando a la API del SDK de AppsFlyer usando JavaScript.

Esta guía se refiere al escenario híbrido. Aprende a cerrar la brecha entre la vista HTML y las vistas nativas, lo que te permite atribuir eventos en la vista HTML y enviarlos a la aplicación.

<div id="note" />

> 📘 **Nota**
>
> Si tu aplicación integra AppsFlyer **mediante un complemento híbrido** (por ejemplo, Cordova, Ionic, React Native o Flutter), el método de puente descrito en esta guía no es aplicable.
>
> Te recomendamos enviar eventos basados en WebView mediante la <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">API server-to-server (S2S) de AppsFlyer</Anchor>.

<div id="example" />

> 📄 **Ejemplo**
>
> Tienes una aplicación híbrida que ofrece suscripciones. Implementa el formulario de suscripción en una vista web que realmente se carga desde tu sitio web.
>
> Puedes atribuir el evento in-app de suscripción en la vista web y enviar datos relacionados con él, como el tipo de suscripción o el precio, al código nativo.
>
> El código nativo recopila los datos y utiliza el SDK de AppsFlyer para enviar el evento in-app de suscripción.
>
> <Image align="center" alt="" src="https://files.readme.io/b7162e6a421e2981490f5a5519e20879cfa9abf2d0eb84c5d59bd1a4e7aa8e22-360002884745.png" />

<div id="recording-in-app-events-in-hybrid-apps" />

### Registro de eventos in-app en aplicaciones híbridas

En esta guía proporcionamos dos métodos para registrar eventos in-app en aplicaciones híbridas:

* **[Recomendado]** [**Interfaz de JavaScript**](/docs/in-app-events-for-hybrid-apps#interfaz-de-javascript): Utiliza la interfaz nativa de JavaScript para establecer la comunicación entre la vista HTML o web y el código nativo. De esta manera, puedes enviar datos relacionados con eventos in-app desde la vista web al código nativo. Una vez que el código nativo obtiene los datos, los envía a AppsFlyer usando el SDK.
* [**Carga de URL**](/docs/in-app-events-for-hybrid-apps#carga-de-url): En este método, el código nativo escucha los eventos de carga de URL. Puedes establecer el código nativo para escuchar los eventos de carga de URL específicas y extraer datos de los parámetros de URL. Los datos se transfieren al SDK.

<div id="javascript-interface" />

## Interfaz de JavaScript

Tanto Android como iOS tienen interfaces nativas de Javascript que permiten que las vistas web llamen al código nativo.

* Android: <Anchor target="_blank" href="https://developer.android.com/guide/webapps/webview">JavaScriptInterface</Anchor>
* iOS: <Anchor target="_blank" href="https://developer.apple.com/documentation/JavaScriptcore">JavaScriptCore</Anchor>

Ventajas de usar la interfaz nativa de JavaScript vs la carga de URL:

* No requiere la implementación de lógica que detecte la carga de URL.
* Las interfaces nativas son preferibles a otras implementaciones.
* No es necesario analizar los parámetros de la URL.
* Hay menos código y, por lo tanto, se requiere menos mantenimiento.

La implementación consta de los siguientes pasos:

1. Código HTML para vista web o página web
2. Implementación de código nativo para vista web

<div id="android" />

<Accordion title="Android">

<div id="html-code-for-android" />

#### Código HTML para Android

Agrega el siguiente código HTML a la vista web o página web:

```html Markup
<h1>Registrar evento desde WebView</h1>
<div id="main">
 <button id="recordEvent" onclick="recordEvent()"> Registrar evento </button>
</div>
<script type="text/JavaScript">
<!-- Establecer ID de usuario del cliente -->
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

Cuando pases el valor del evento, ten presente lo siguiente:

* Asegúrate de pasar el valor del evento como un JSON en formato de secuencia.

  ```html Markup
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Para evitar cualquier posible problema, AppsFlyer recomienda usar sólo caracteres alfanuméricos en minúscula (a-z y 0-9) dentro de la aplicación para los nombres de los eventos.

<div id="webactivity-class" />

#### Clase WebActivity

Crea una clase de actividad web con el siguiente código:

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

El código anterior crea un objeto llamado **app** que actúa como puente entre la vista web y el código nativo.

<div id="javascript-interface-class" />

#### Clase de la interfaz de JavaScript

Crea una clase MainJsInterface para implementar `recordEvent()` como `JavaScriptInterface`

```java
public class MainJsInterface {
 Context mContext;

 MainJsInterface(Context c) {
  mContext = c;
 }

 //Establecer ID de usuario del cliente
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

El código anterior declara un método de `recordEvent` que puede llamarse en la vista web mediante JavaScript.

En el código HTML, puedes ver que se llama al método usando `app.recordEvent(eventName, eventParams)`. Recuerda que configuramos la **aplicación** para que actúe como puente entre la vista de la web y el código nativo. Es por eso que la **aplicación** puede llamar al método `recordEvent` que definamos en la clase MainJsInterface.

</Accordion>

<div id="ios" />

<Accordion title="apps de iOS,">

<div id="html-code-for-ios" />

#### Código HTML para iOS

Agrega el siguiente código HTML a la vista web o página web:

```html Markup
<body>
 <h1>Registro de evento desde WebView</h1>
 <div id="main">
  <button id="recordEvent" onclick="recordEvent()"> Registrar evento </button>
 </div>
 <script type="text/JavaScript">
   <!-- Establecer ID de usuario del cliente --> 
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

El código anterior establece una función que se activará cuando se haga clic en un botón. La función establece las variables `eventName` y `eventParams` y las pasa al archivo de código nativo usando `webkit.messageHandlers`.

Cuando pases el valor del evento, ten presente lo siguiente:

* Asegúrate de pasar el valor del evento como un JSON en formato de secuencia.

  ```html Markup
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Para evitar cualquier posible problema, AppsFlyer recomienda usar sólo caracteres alfanuméricos en minúscula (a-z y 0-9) dentro de la aplicación para los nombres de los eventos.

<div id="note-1" />

> 📘 **Nota**
>
> El código HTML es tanto para Objective C como para Swift.

#### Objective C

<div id="web-view-controller" />

#### Controlador de vista web

En tu controlador de vista web, agrega el siguiente código en el controlador de vista.

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
  didReceiveScriptMessage: (WKScriptMessage *)message {

 NSString* messageBody = message.body;
 NSString* eventName = [messageBody componentsSeparatedByString:@"+"][0];
 NSString* eventValue = [messageBody componentsSeparatedByString:@"+"][1];
 [self recordEvent:eventName eventValue:eventValue];
}

- (void)recordEvent:(NSString*)eventName eventValue: (NSString*)eventValue{

 NSData *eventValuedata = [eventValue dataUsingEncoding: (NSUTF8StringEncoding)];

 NSDictionary *eventValueDict = [NSJSONSerialization JSONObjectWithData:eventValuedata options: NSJSONReadingMutableContainers error:nil];

 [[AppsFlyerLib shared] logEvent:eventName withValues:eventValueDict];

}
```

El código anterior recibe el mensaje de la vista web. El mensaje contiene el nombre y el valor del evento. Cuando el código detecta al mensaje entrante, lo pasa al método `recordEvent` que analiza los valores y llama al método nativo `logEvent` del SDK.

<div id="swift-webview-controller" />

#### Controlador Swift WebView

En el controlador de vista web, agrega el siguiente código:

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

 var webView: 
    } else if message.name == "cuid" {
      AppsFlyerLib.shared().customerUserID = message.body as? String
    }
 }

 var webView: WKWebView!
 WKWebView!
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

 func webView(_ view:
  webView.load(URLRequest(url: url))
  webView.configuration.userContentController.add(self, name:"event")
 }

 func recordEvent(eventName: String, eventValue: String) {

  var eventValueDict = [String: String]()

  let eventValuesData = eventValue.data(using: String.Encoding.utf8)
  do {
   eventValueDict = try (JSONSerialization.jsonObject(with: eventValuesData!, options:[]) as? [String: String])!
  [String: String])!
  } catch let error as NSError{
   print(error)
  }

  AppsFlyerLib.shared().logEvent(eventName as String?, withValues: eventValueDict)
 }

}
```

El código anterior recibe el mensaje de la vista web. El mensaje contiene el nombre y el valor del evento. Cuando el código detecta al mensaje entrante, lo pasa al método `recordEvent` que analiza los valores y llama al método `logEvent` del SDK de AppsFlyer.

</Accordion>

<div id="url-loading" />

## Carga de URL

Tanto Android como iOS implementan un método nativo que escucha los eventos de carga de URL. Este método te permite hacer lo siguiente:

* Escuchar un evento de carga de una URL específica
* Extraer parámetros que se anexan a la URL
* Usar estos parámetros en el código nativo

La implementación a continuación consta de dos pasos:

1. Código HTML para vista web o página web
2. Implementación de código nativo para la carga de URL

<div id="webview-implementation" />

### Implementación de WebView

<div id="html-code-for-both-android-webview-and-ios-wkwebview" />

#### Código HTML (tanto para Android WebView como para iOS WKWebView)

```html Markup
<html>
<head>
</head>
 <body>
  <h1>Registro desde WebView</h1>
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

El código anterior puede ser parte de una página web real o cargada de forma nativa en la vista web.

El código anterior establece una función que se activará cuando se haga clic en un botón. La función en sí crea un elemento iframe que carga una URL personalizada. Es esta carga de URL la que activa el método nativo de Android o iOS que luego llama al método `logEvent`.

Todos los parámetros requeridos (nombre del evento y valores del evento) se agregan a la URL. Los ejemplos de código de Android e iOS a continuación demuestran cómo extraer estos parámetros y pasarlos al método `logEvent` del SDK de AppsFlyer.

Cuando pases el valor del evento, ten presente lo siguiente:

* Asegúrate de pasar el valor del evento como un JSON en formato de secuencia.

  ```
  "{\"af_revenue\":\"6.72\", \"af_content_type\": \"wallets\", \"af_content_id\": \"15854\"}"
  ```
* Para evitar posibles problemas, AppsFlyer recomienda usar únicamente caracteres alfanuméricos en minúsculas (a-z y 0-9) para tus nombres de eventos in-app.

<div id="native-implementation" />

### Implementación nativa

<Tabs>
<Tab title="Android">

<div id="android-implementation" />

#### Implementación de Android

Android WebView utiliza un WebViewClient que recibe notificaciones de la vista web. En el `shouldOverrideUrlLoading`, puedes manejar los eventos de carga de URL que provienen de la vista web:

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

#### Implementación de iOS

<Tabs>
<Tab title="Objective C">

En el controlador de vista web, agrega el siguiente código en el método `shouldStartLoadWithRequest`.

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

-(void)webView:(WKWebView *)webView decidePolicyForNavigationAction: (WKNavigationAction* )navigationAction decisionHandler:(void (^)(WKNavigationActionPolicy))decisionHandler {
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
 NSData *eventValuedata = [decodedValueParams dataUsingEncoding: (NSUTF8StringEncoding)];
 NSDictionary *eventValue = [NSJSONSerialization JSONObjectWithData:eventValuedata options: NSJSONReadingMutableContainers error:nil];

 if (eventName != nil){
  [[AppsFlyerLib shared] logEvent:eventName withValues:eventValue];

 }

}
```

El código anterior detecta cualquier carga de URL. Si se carga una URL con "af-event", activa el método nativo `recordEvent`. El método nativo `recordEvent` extrae los parámetros necesarios (eventName y eventValue) y los pasa al método nativo `logEvent` de SDK.

</Tab>

<Tab title="Swift">

En el controlador de vista web, agrega el siguiente código en el método `webView(_:decidePolicyFor:decisionHandler:)`.

```swift
import WebKit
import UIKit
import AppsFlyerLib
class WebViewController: UIViewController, WKNavigationDelegate {
 var webView:
 WKWebView!
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

 func webView(_ view:
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
      [String: String])!
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

El código anterior detecta cualquier carga de URL. Si se carga una URL con "af-event", extrae los parámetros necesarios (eventName y eventValue) y los pasa al método nativo `logEvent` del SDK.

</Tab>
</Tabs>

</Tab>
</Tabs>

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01HGWH2AEJ0DHTGD41YN7R5A1V=introducci%C3%B3n h_01KB7M7ZSM5AZACJNB32F65A62=nota h_01HGWH2AEJZHV3KZR0ZPPFK71T=ejemplo recording-inapp-events-in-hybrid-apps=registro-de-eventos-in-app-en-aplicaciones-h%C3%ADbridas h_01HGWH2AEJFEZY7WBJTFP9N3AN=registro-de-eventos-in-app-en-aplicaciones-h%C3%ADbridas JavaScript-interface=interfaz-de-javascript h_01HGWH2AEJFVDZBPRS8DP64TRY=interfaz-de-javascript h_01HGWH2AEKB47CJ386AN7NNX4Y=android html-code-for-android=c%C3%B3digo-html-para-android h_01HGWH2AEKZG98VWPECP6FBHN3=c%C3%B3digo-html-para-android webactivity-class=clase-webactivity h_01HGWH2AEKA5X1DPWS51WRCMD4=clase-webactivity JavaScript-interface-class=clase-de-la-interfaz-de-javascript h_01HGWH2AEK07MGR1FPFSWXYRKP=clase-de-la-interfaz-de-javascript h_01HGWH2AEN4WHKBSM69S200F5H=ios html-code-for-ios=c%C3%B3digo-html-para-ios h_01HGWH2AENKC2EEYJPW9KZDVJS=c%C3%B3digo-html-para-ios h_01HGWH2AENTMA7A71K2Y7XQF9T=nota-1 h_01HGWH2AENGAWEGD5TRTR2P6PR=objective-c web-view-controller=controlador-de-vista-web h_01HGWH2AENJVMVHSDPMKBP6HNT=controlador-de-vista-web swift-webview-controller=controlador-swift-webview h_01HGWH2AENV1J1M0KH36K1YSCJ=controlador-swift-webview url-loading=carga-de-url h_01HGWH2AENV0Q83A0GF8NK7S4B=carga-de-url webview-implementation=implementaci%C3%B3n-de-webview h_01HGWH2AENFH6M2ZQSGH4EGEGB=implementaci%C3%B3n-de-webview html-code-for-both-android-webview-and-ios-wkwebview=c%C3%B3digo-html-tanto-para-android-webview-como-para-ios-wkwebview h_01HGWH2AENEDT95283SQZDHPCD=c%C3%B3digo-html-tanto-para-android-webview-como-para-ios-wkwebview native-implementation=implementaci%C3%B3n-nativa h_01HGWH2AENS43N93D65RN80VXN=implementaci%C3%B3n-nativa android-implementation=implementaci%C3%B3n-de-android h_01HGWH2AEN0QYYJJGV90A27VAM=implementaci%C3%B3n-de-android h_01HGWH2AEN38VWNXE90BHGQQ9A=ios-implementation" />

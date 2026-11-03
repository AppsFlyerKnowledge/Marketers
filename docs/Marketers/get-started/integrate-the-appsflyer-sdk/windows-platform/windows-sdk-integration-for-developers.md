---
title: Integración del SDK de Windows para desarrolladores
metadata:
  keywords:
    - SDK
    - Integration
    - Windows Phone
    - In-App
    - windows universal apps
    - windows 10
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-05-07T12:17:52Z'
  edited_at: '2026-08-12T12:03:14Z'
  id: 207032026
  locale: es
  section: Windows platform
  section_id: 6551223206417
  url: https://support.appsflyer.com/hc/es/articles/207032026
---
> **De un vistazo:** Añade AppsFlyer a aplicaciones y juegos de Windows para medir instalaciones de la app, eventos in-app, fuentes de medios y mucho más.

**Versión actual: 3.1.0 (17/12/2023)**

El SDK de AppsFlyer proporciona la funcionalidad de registro de eventos e instalación de aplicaciones.

![SDK_Integration.jpg](https://files.readme.io/11ef01abe55ae3d53d1a3756ffd24bf3262002c3970005cd70047c9d0665b5d1-360001586617.jpg)

Puedes registrar instalaciones, actualizaciones y sesiones (siguiendo los pasos obligatorios que se indican a continuación), y también registrar eventos in-app adicionales además de las instalaciones de la app (incluidas las compras in-app, los niveles de juego, etc.) para evaluar el ROI y los niveles de engagement de los usuarios.

> 🚧 **Importante:**
>
> El SDK de AppsFlyer para Windows es compatible con todos los dispositivos de <Anchor target="_blank" href="https://docs.microsoft.com/en-us/windows/uwp/get-started/universal-application-platform-guide">Universal Windows Platform</Anchor> (UWP), incluidos teléfonos móviles con Windows, PC, HoloLens y Surface Hub.

## 1. Pasos de integración

El SDK Universal de Windows se instala mediante el administrador de paquetes NuGet. Para instalar el SDK de AppsFlyer para Windows mediante NuGet:

[![](https://files.readme.io/dcce7e82d681f6b0dfa5c6da26d183f331212dde51148d027d4dc75cb57d104a-21241904425489.png)](https://files.readme.io/dcce7e82d681f6b0dfa5c6da26d183f331212dde51148d027d4dc75cb57d104a-21241904425489.png)

1. Haz clic con el botón derecho en el archivo del proyecto.
2. Haz clic en ***Manage NuGet Packages***.
3. Haz clic en ***Browse*** y busca *AppsFlyerLib*.
4. Haz clic en ***AppsFlyerLib***.
5. Haz clic en ***Install***.

Si decides no usar el paquete NuGet, puedes integrar manualmente el SDK de AppsFlyer en tu aplicación:

1. Descarga el SDK de la aplicación para la Universal Windows Platform <Anchor target="_blank" href="https://s3-eu-west-1.amazonaws.com/download.appsflyer.com/windows-phone-sdk/AF-Windows-SDK-v3.1.0.zip">desde aquí</Anchor>.
2. Copia AppsFlyerLib.winmd en tu proyecto.
3. En Visual Studio, haz clic en ***Add Reference*** en el proyecto de Universal Windows Platform.

[![](https://files.readme.io/5606c0bcbaaffdeea5b43f9b0201263a6ad3ab5a610ccb7b7389737e84c22844-21241888352273.png)](https://files.readme.io/5606c0bcbaaffdeea5b43f9b0201263a6ad3ab5a610ccb7b7389737e84c22844-21241888352273.png)

* Busca AppsFlyerLib.winmd y añádelo.

[![](https://files.readme.io/fe03e297291cab276977287701e46d950c7444a47d28c01a75f01112992b57a9-21241904443153.png)](https://files.readme.io/fe03e297291cab276977287701e46d950c7444a47d28c01a75f01112992b57a9-21241904443153.png)

> 🚧 **Importante:**
>
> AppsFlyer usa un paquete de Newtonsoft.json. Esta es una biblioteca estándar para analizar Json en Windows. Puedes añadir este paquete con NuGet en Visual Studio. Esto resuelve la excepción «File Not Found» en la DLL.
>
> * En Visual Studio, haz clic con el botón derecho en References, selecciona el paquete NuGet Newtonsoft.json y añádelo.
> * Permite el acceso a Internet en el manifiesto de la aplicación o usa Visual Studio en la pestaña Capabilities.

## 2. Inicialización del SDK & evento de instalación (requisito mínimo para la atribución)

* Agrega el siguiente código al método App Launch.
* Configura tu appId y tu DevKey:
  * Rellena tracker.appId y tracker.devKey con tus valores.
  * Puedes obtener tu DevKey de AppsFlyer en nuestro Dashboard, en SDK Integration.

```csharp
protected override void OnLaunched(LaunchActivatedEventArgs e)
{
	this .InitializeComponent();
	this .Suspending += this .OnSuspending;
	AppsFlyerLib. AppsFlyerTracker tracker =
	AppsFlyerLib. AppsFlyerTracker .GetAppsFlyerTracker();
	tracker.appId = "YOUR_APP_ID_HERE" ;
	tracker.devKey = "YOUR_DEV_KEY_HERE" ;
	tracker.trackAppLaunch();
}
```

### Registro del inicio de la app de forma asíncrona

Puedes registrar el inicio de la app de forma asíncrona. Esto es útil cuando la red no está disponible o no responde. Puedes gestionar estos casos en la función de callback que pasas al método `TrackAppLaunchAsync`.

```csharp
tracker.TrackAppLaunchAsync(Callback);
public void Callback(AppsFlyerLib.ServerStatusCode code)
{
   if(code == AppsFlyerLib.ServerStatusCode.SUCCESS) {
      //success scenario
   } else if(code == AppsFlyerLib.ServerStatusCode.FAIL) {
   //failure scenario
   }
}
```

## 3. API de registro de eventos in-app (opcional)

Esta API permite a AppsFlyer registrar eventos posteriores a la instalación. Estos eventos los define el anunciante e incluyen un nombre de evento, además de valores de evento opcionales. Agrega el siguiente código para registrar eventos posteriores a la instalación:

```csharp
public void TrackEvent(string eventName, IDictionary<string, Object> eventValues)
```

* *eventName* puede ser cualquier cadena que defina el nombre del evento. Puedes consultar una lista de nombres de evento recomendados <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">aquí</Anchor>.
* *eventValues* es un diccionario de parámetros de evento que componen un evento. Puedes consultar una lista de parámetros recomendados <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">aquí</Anchor>.
* Al contabilizar ingresos como parte de eventos in-app, utiliza el nombre de parámetro constante InAppEventParameterName.REVENUE («af\_revenue») para contabilizar los ingresos como parte de un evento in-app. Puede completarlo con cualquier valor numérico, positivo o negativo.

> 📄 **Ejemplo**
>
> ```csharp
> AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
>       IDictionary<string, object> eventValues = new Dictionary<string, object>();
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CONTENT_ID, "id123");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.REVENUE, "10");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CURRENCY, "USD");
>       tracker.TrackEvent(AppsFlyerLib.AFInAppEventType.ADD_TO_CART, eventValues);
> ```

### Registrar eventos de forma asíncrona

Puedes registrar eventos de forma asíncrona. Esto es útil cuando la red no funciona o no responde. Puedes gestionar esos casos en la función de callback que pasas al método `TrackEventAsync`.

```csharp
tracker.TrackEventAsync(AppsFlyerLib.AFInAppEventType.PURCHASE, events, Callback);
public void Callback(AppsFlyerLib.ServerStatusCode code)
{
   if(code == AppsFlyerLib.ServerStatusCode.SUCCESS) {
      //success scenario
   } else if(code == AppsFlyerLib.ServerStatusCode.FAIL) {
     //failure scenario
   }
}
```

Para ver una lista completa de los eventos in-app enriquecidos de AppsFlyer, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">aquí</Anchor>.

## 4. Integración avanzada

Las siguientes API son opcionales y forman parte de la integración avanzada con el SDK de AppsFlyer.

### 4.1 Establecer código de moneda (opcional)

Puedes usar la siguiente API para establecer un código de moneda global, además de códigos de moneda específicos que se pueden usar como parte de cada evento in-app enviado a AppsFlyer.

USD es el valor predeterminado. Puedes consultar los códigos ISO de moneda aceptados <Anchor target="_blank" href="http://www.xe.com/iso4217.php">aquí</Anchor>.

Usa la siguiente API para configurar el código de moneda:

```csharp
tracker.currencyCode = "GBP";
```

### 4.2 getAppsFlyeruid (opcional)

Se crea un ID único de AppsFlyer para cada nueva instalación de una app.

Usa la siguiente API para obtener este ID:

```csharp
public string getAppsFlyerUID()
```

### 4.3 ID de usuario del cliente (opcional)

Configurar tu propio ID de cliente te permite establecer referencias cruzadas entre tu propio ID único, el ID de usuario de AppsFlyer y todos los demás ID de dispositivo. Este ID está disponible en los reportes CSV de AppsFlyer, junto con las API de postback, para establecer referencias cruzadas con tus ID internos.

Para configurar tu ID de usuario de cliente:

```csharp
tracker.customerUserId = "YOUR_CUSTOMER_USER_ID";
```

### 4.4 GetConversionDataAsync (opcional)

Puedes recibir los datos de conversión de cada instalación a través del SDK mediante esta API. Agrega el siguiente código para registrar eventos posteriores a la instalación:

```csharp
Task.Run(async () =>
{
   AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
   string conversionData = await tracker.GetConversionDataAsync();
});
```

### 4.5 Ejemplo de integración de C++ / CX

```csharp
AppsFlyerLib::AppsFlyerTracker^ tracker = AppsFlyerLib::AppsFlyerTracker::GetAppsFlyerTracker();
 tracker->appId = ref new Platform::String(L"APP_KEY");
 tracker->devKey = ref new Platform::String(L"APPSFLYER_KEY");
 tracker->TrackAppLaunch();
 create_task(tracker->GetConversionDataAsync()).then([tracker](Platform::String^ conversionData)
 {
 Windows::Foundation::Collections::IMap<Platform::String^, Platform::Object^>^ eventValues
 = ref new Platform::Collections::Map<Platform::String^, Platform::Object^>();

eventValues->Insert(AppsFlyerLib::AFInAppEventParameterName::CONTENT_ID, "134");
 eventValues->Insert(AppsFlyerLib::AFInAppEventParameterName::CONTENT_TYPE, "Virtual Goods");
 eventValues->Insert(AppsFlyerLib::AFInAppEventParameterName::CURRENCY, "USD");
 eventValues->Insert(AppsFlyerLib::AFInAppEventParameterName::REVENUE, "9.99");

tracker->TrackEvent(AppsFlyerLib::AFInAppEventType::PURCHASE, eventValues);
 });
```

<div data-zendesk-anchors="h_01H9G0X6VRCJCGHXWNJ2XFAQN9=importante 2-initial-steps=1-pasos-de-integraci%C3%B3n h_01H9G0X6VRQJ860K5QS7DE9DT4=1-pasos-de-integraci%C3%B3n h_01H9G0X6VRJ3KKZD6XM202NEX2=importante-1 3-sdk-initialization-installation-event-minimum-requirement-for-attributing=2-inicializaci%C3%B3n-del-sdk--evento-de-instalaci%C3%B3n-requisito-m%C3%ADnimo-para-la-atribuci%C3%B3n h_01H9G0X6VR9FW15TYS06M3JBYM=2-inicializaci%C3%B3n-del-sdk--evento-de-instalaci%C3%B3n-requisito-m%C3%ADnimo-para-la-atribuci%C3%B3n recording-app-launch%C2%A0asynchronously=registro-del-inicio-de-la-appde-forma-as%C3%ADncrona h_01H9G0X6VR6JHKGPTWERQGZNMW=registro-del-inicio-de-la-appde-forma-as%C3%ADncrona 4-inapp-event-recording-api-optional=3-api-de-registro-de-eventos-in-app-opcional h_01H9G0X6VRSBKYX4AJK5ZQ14EK=3-api-de-registro-de-eventos-in-app-opcional h_01H9G0X6VS1RA8K4EW4K1Q8B6P=ejemplo recording-events-asynchronously=registrar-eventos-de-forma-as%C3%ADncrona h_01H9G0X6VS5PYNZEZG86QJTSPJ=registrar-eventos-de-forma-as%C3%ADncrona 5-advanced-integration=4-integraci%C3%B3n-avanzada h_01H9G0X6VSW4A5B044HF1704XH=4-integraci%C3%B3n-avanzada 51-set-currency-code-optional=41-establecer-c%C3%B3digo-de-moneda-opcional h_01H9G0X6VSY3975EZNGD2NDSMR=41-establecer-c%C3%B3digo-de-moneda-opcional 52-getappsflyeruid-optional=42-getappsflyeruid-opcional h_01H9G0X6VS4MF8S85049HFJD8K=42-getappsflyeruid-opcional 53-customer-user-id-optional=43-id-de-usuario-del-cliente-opcional h_01H9G0X6VSM167RKESECBQCPZD=43-id-de-usuario-del-cliente-opcional 54-getconversiondataasync-optional=44-getconversiondataasync-opcional h_01H9G0X6VSJWZ3BFWP4AFMZXXY=44-getconversiondataasync-opcional 55-c-cx-integration-example=45-ejemplo-de-integraci%C3%B3n-de-c--cx h_01H9G0X6VSRNZXN8A22Q8KYYJR=45-ejemplo-de-integraci%C3%B3n-de-c--cx" />

---
title: Integração do SDK do Windows para desenvolvedores
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
  edited_at: '2026-08-19T00:15:22Z'
  id: 207032026
  locale: pt
  section: Windows platform
  section_id: 6551223206417
  url: https://support.appsflyer.com/hc/pt/articles/207032026
---
> **Visão geral:** adicione a AppsFlyer a aplicativos e jogos do Windows para medir instalações do aplicativo, eventos in-app, canais de mídia e muito mais.

**Versão atual: 3.1.0 (17/12/2023)**

O SDK da AppsFlyer fornece funcionalidade de instalação do aplicativo e registro de eventos.

![SDK_Integration.jpg](https://files.readme.io/11ef01abe55ae3d53d1a3756ffd24bf3262002c3970005cd70047c9d0665b5d1-360001586617.jpg)

Você pode registrar instalações, atualizações e sessões (seguindo as etapas obrigatórias abaixo) e também registrar eventos in-app adicionais além das instalações do aplicativo (incluindo compras in-app, níveis de jogo etc.) para avaliar o ROI e os níveis de engajamento do usuário.

> 🚧 **Importante!**
>
> O SDK do Windows da AppsFlyer é compatível com todos os dispositivos da <Anchor target="_blank" href="https://docs.microsoft.com/en-us/windows/uwp/get-started/universal-application-platform-guide">Universal Windows Platform</Anchor> (UWP), incluindo telefones Windows, PCs, HoloLens e Surface Hub.

## 1. Etapas de integração

O SDK Universal do Windows é instalado por meio do Gerenciador de Pacotes NuGet. Para instalar o SDK do Windows da AppsFlyer via NuGet:

[![](https://files.readme.io/dcce7e82d681f6b0dfa5c6da26d183f331212dde51148d027d4dc75cb57d104a-21241904425489.png)](https://files.readme.io/dcce7e82d681f6b0dfa5c6da26d183f331212dde51148d027d4dc75cb57d104a-21241904425489.png)

1. Clique com o botão direito no arquivo do projeto.
2. Clique em ***Gerenciar Pacotes NuGet***.
3. Clique em ***Procurar*** e pesquise por *AppsFlyerLib*.
4. Clique em ***AppsFlyerLib***.
5. Clique em ***Instalar***.

Se você optar por não usar o pacote NuGet, poderá incorporar o SDK da AppsFlyer ao seu aplicativo manualmente:

1. Baixe o SDK de aplicativo da Universal Windows Platform <Anchor target="_blank" href="https://s3-eu-west-1.amazonaws.com/download.appsflyer.com/windows-phone-sdk/AF-Windows-SDK-v3.1.0.zip">aqui</Anchor>.
2. Copie o AppsFlyerLib.winmd para o seu projeto.
3. No Visual Studio, clique em ***Adicionar Referência*** no projeto da Universal Windows Platform.

[![](https://files.readme.io/5606c0bcbaaffdeea5b43f9b0201263a6ad3ab5a610ccb7b7389737e84c22844-21241888352273.png)](https://files.readme.io/5606c0bcbaaffdeea5b43f9b0201263a6ad3ab5a610ccb7b7389737e84c22844-21241888352273.png)

* Localize o AppsFlyerLib.winmd e adicione-o.

[![](https://files.readme.io/fe03e297291cab276977287701e46d950c7444a47d28c01a75f01112992b57a9-21241904443153.png)](https://files.readme.io/fe03e297291cab276977287701e46d950c7444a47d28c01a75f01112992b57a9-21241904443153.png)

> 🚧 **Importante!**
>
> A AppsFlyer usa um pacote Newtonsoft.json. Esta é uma biblioteca padrão para analisar Json no Windows. Você pode adicionar esse pacote usando o NuGet no Visual Studio. Isso resolve a exceção File Not Found na DLL.
>
> * No Visual Studio, clique com o botão direito em Referências, selecione o pacote NuGet Newtonsoft.json e adicione-o.
> * Permita o acesso à Internet no manifesto do aplicativo ou use o Visual Studio na guia Capacidades.

## 2. Evento de inicialização do SDK & de instalação (requisito mínimo para atribuição)

* Adicione o seguinte código ao método de inicialização do aplicativo.
* Defina seu appId e sua DevKey:
  * Preencha tracker.appId e tracker.devKey com seus valores.
  * Você pode obter sua DevKey da AppsFlyer no dashboard, em Integração do SDK.

```csharp
protected override void OnLaunched(LaunchActivatedEventArgs e)
{
	this . InitializeComponent();
	this . Suspending += this . OnSuspending;
	AppsFlyerLib. AppsFlyerTracker tracker = AppsFlyerLib. AppsFlyerTracker . GetAppsFlyerTracker();
	tracker.appId = "YOUR_APP_ID_HERE" ;
	tracker.devKey = "YOUR_DEV_KEY_HERE" ;
	tracker.trackAppLaunch();
}
```

### Registro assíncrono da inicialização do aplicativo

Você pode registrar a inicialização do aplicativo de forma assíncrona. Isso é útil em casos em que a network está indisponível ou sem resposta. Você pode tratar esses casos na função Callback que você passa para o método `TrackAppLaunchAsync`.

```csharp
tracker. TrackAppLaunchAsync(Callback);
public void Callback(AppsFlyerLib. ServerStatusCode code)
{
   if(code == AppsFlyerLib. ServerStatusCode.SUCCESS) {
      //success scenario
   } else if(code == AppsFlyerLib. ServerStatusCode.FAIL) {
   //failure scenario
   }
}
```

## 3. API de registro de eventos in-app (opcional)

Essa API permite que a AppsFlyer registre eventos pós-instalação. Esses eventos são definidos pelo anunciante e incluem um nome de evento, além de valores de evento opcionais. Adicione o código a seguir para registrar eventos pós-instalação:

```csharp
public void TrackEvent(string eventName, IDictionary<string, Object> eventValues)
```

* *eventName* é qualquer string que define o nome do evento. Você pode encontrar uma lista de nomes de evento recomendados <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">aqui</Anchor>.
* *eventValues* é um dicionário de parâmetros de evento que compõem um evento. Você pode encontrar uma lista de parâmetros recomendados <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">aqui</Anchor>.
* Ao contabilizar a receita como parte de eventos in-app, use o nome de parâmetro constante InAppEventParameterName.REVENUE (“af\_revenue”) para contabilizar a receita como parte de um evento in-app. Você pode preenchê-lo com qualquer valor numérico, positivo ou negativo.

> 📄 **Exemplo**
>
> ```csharp
> AppsFlyerLib. AppsFlyerTracker tracker = AppsFlyerLib. AppsFlyerTracker. GetAppsFlyerTracker();
>       IDictionary<string, object> eventValues = new Dictionary<string, object>();
>       eventValues. Add(AppsFlyerLib.AFInAppEventParameterName.CONTENT_ID, "id123");
>       eventValues. Add(AppsFlyerLib.AFInAppEventParameterName.REVENUE, "10");
>       eventValues. Add(AppsFlyerLib.AFInAppEventParameterName.CURRENCY, "USD");
>       tracker. TrackEvent(AppsFlyerLib.AFInAppEventType.ADD_TO_CART, eventValues);
> ```

### Registrar eventos assincronamente

Você pode registrar eventos assincronamente. Isso é útil nos casos em que a network está indisponível ou sem resposta. Você pode lidar com esses casos na função Callback que você passa para o método `TrackEventAsync`.

```csharp
tracker. TrackEventAsync(AppsFlyerLib.AFInAppEventType.PURCHASE, events, Callback);
public void Callback(AppsFlyerLib. ServerStatusCode code)
{
   if(code == AppsFlyerLib. ServerStatusCode.SUCCESS) {
      //cenário de sucesso
   } else if(code == AppsFlyerLib. ServerStatusCode.FAIL) {
     //cenário de falha
   }
}
```

Para ver uma lista completa dos eventos in-app avançados da AppsFlyer, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">aqui</Anchor>.

## 4. Integração avançada

As APIs a seguir são opcionais e fazem parte da integração avançada com o SDK da AppsFlyer.

### 4.1 definir o código da moeda (opcional)

Você pode definir um código de moeda global usando a API abaixo, além de códigos de moeda específicos que podem ser usados como parte de cada evento no aplicativo enviado para a AppsFlyer.

USD é o valor padrão. Você pode encontrar os códigos de moeda ISO aceitos <Anchor target="_blank" href="http://www.xe.com/iso4217.php">aqui</Anchor>.

Use a seguinte API para definir o código de moeda:

```csharp
tracker.currencyCode = "GBP";
```

### 4.2 getAppsFlyeruid (opcional)

Uma ID exclusiva da AppsFlyer é criada para cada nova instalação de um aplicativo.

Use a seguinte API para obter essa ID:

```csharp
public string getAppsFlyerUID()
```

### 4.3 ID de usuário do cliente (opcional)

Definir seu próprio ID de cliente permite que você faça referência cruzada do seu próprio ID exclusivo com o ID de usuário da AppsFlyer e todos os outros IDs de dispositivo. Essa ID está disponível nos relatórios CSV da AppsFlyer junto com as APIs de postback para referência cruzada com suas IDs internas.

Para definir sua ID de usuário cliente:

```csharp
tracker.customerUserId = "YOUR_CUSTOMER_USER_ID";
```

### 4.4 GetConversionDataAsync (opcional)

Você pode receber os dados de conversão de cada instalação pelo SDK usando esta API. Adicione o código a seguir para registrar eventos de pós-instalação:

```csharp
Task.Run(async () =>
{
   AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
   string conversionData = await tracker.GetConversionDataAsync();
});
```

### 4.5 Exemplo de integração com C++ / CX

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

<div data-zendesk-anchors="h_01H9G0X6VRCJCGHXWNJ2XFAQN9=importante 2-initial-steps=1-etapas-de-integra%C3%A7%C3%A3o h_01H9G0X6VRQJ860K5QS7DE9DT4=1-etapas-de-integra%C3%A7%C3%A3o h_01H9G0X6VRJ3KKZD6XM202NEX2=importante-1 3-sdk-initialization-installation-event-minimum-requirement-for-attributing=2-evento-de-inicializa%C3%A7%C3%A3o-do-sdk--de-instala%C3%A7%C3%A3o-requisito-m%C3%ADnimo-para-atribui%C3%A7%C3%A3o h_01H9G0X6VR9FW15TYS06M3JBYM=2-evento-de-inicializa%C3%A7%C3%A3o-do-sdk--de-instala%C3%A7%C3%A3o-requisito-m%C3%ADnimo-para-atribui%C3%A7%C3%A3o recording-app-launch%C2%A0asynchronously=registroass%C3%ADncrono-da-inicializa%C3%A7%C3%A3o-do-aplicativo h_01H9G0X6VR6JHKGPTWERQGZNMW=registroass%C3%ADncrono-da-inicializa%C3%A7%C3%A3o-do-aplicativo 4-inapp-event-recording-api-optional=3-api-de-registro-de-eventos-in-app-opcional h_01H9G0X6VRSBKYX4AJK5ZQ14EK=3-api-de-registro-de-eventos-in-app-opcional h_01H9G0X6VS1RA8K4EW4K1Q8B6P=exemplo recording-events-asynchronously=registrar-eventos-assincronamente h_01H9G0X6VS5PYNZEZG86QJTSPJ=registrar-eventos-assincronamente 5-advanced-integration=4-integra%C3%A7%C3%A3o-avan%C3%A7ada h_01H9G0X6VSW4A5B044HF1704XH=4-integra%C3%A7%C3%A3o-avan%C3%A7ada 51-set-currency-code-optional=41-definir-o-c%C3%B3digo-da-moeda-opcional h_01H9G0X6VSY3975EZNGD2NDSMR=41-definir-o-c%C3%B3digo-da-moeda-opcional 52-getappsflyeruid-optional=42-getappsflyeruid-opcional h_01H9G0X6VS4MF8S85049HFJD8K=42-getappsflyeruid-opcional 53-customer-user-id-optional=43-id-de-usu%C3%A1rio-do-cliente-opcional h_01H9G0X6VSM167RKESECBQCPZD=43-id-de-usu%C3%A1rio-do-cliente-opcional 54-getconversiondataasync-optional=44-getconversiondataasync-opcional h_01H9G0X6VSJWZ3BFWP4AFMZXXY=44-getconversiondataasync-opcional 55-c-cx-integration-example=45-exemplo-de-integra%C3%A7%C3%A3o-com-c--cx h_01H9G0X6VSRNZXN8A22Q8KYYJR=45-exemplo-de-integra%C3%A7%C3%A3o-com-c--cx" />

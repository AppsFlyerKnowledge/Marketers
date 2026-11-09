---
title: Интеграция Windows SDK для разработчиков
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
  edited_at: '2026-08-19T00:15:25Z'
  id: 207032026
  locale: ru
  section: Windows platform
  section_id: 6551223206417
  url: https://support.appsflyer.com/hc/ru/articles/207032026
---
> **Краткий обзор:** добавьте AppsFlyer в приложения и игры для Windows, чтобы измерять установки приложения, события в приложении, медиаисточники и многое другое.

**Текущая версия: 3.1.0 (17/12/2023)**

SDK AppsFlyer предоставляет функциональность регистрации установок приложения и записи событий.

<Image align="center" alt="SDK_Integration.jpg" src="https://files.readme.io/11ef01abe55ae3d53d1a3756ffd24bf3262002c3970005cd70047c9d0665b5d1-360001586617.jpg" />

Вы можете регистрировать установки, обновления и сессии (выполнив обязательные шаги ниже), а также дополнительные события в приложении помимо установок приложения (включая покупки в приложении, уровни игры и т. д.) для оценки ROI и уровня вовлеченности пользователей.

<div id="important" />

> 🚧 **Важно!**
>
> SDK AppsFlyer для Windows совместим со всеми устройствами <Anchor target="_blank" href="https://docs.microsoft.com/en-us/windows/uwp/get-started/universal-application-platform-guide">Universal Windows Platform</Anchor> (UWP), включая мобильные телефоны Windows, ПК, HoloLens и Surface Hub.

<div id="1-integration-steps" />

## 1. Этапы интеграции

Универсальный SDK для Windows устанавливается через диспетчер пакетов NuGet. Чтобы установить SDK AppsFlyer для Windows через NuGet:

<Image align="center" alt="" src="https://files.readme.io/dcce7e82d681f6b0dfa5c6da26d183f331212dde51148d027d4dc75cb57d104a-21241904425489.png" />

1. Щелкните правой кнопкой мыши файл проекта.
2. Нажмите ***Manage NuGet Packages***.
3. Нажмите ***Browse*** и выполните поиск *AppsFlyerLib*.
4. Нажмите ***AppsFlyerLib***.
5. Нажмите кнопку ***Install***.

Если вы решили не использовать пакет NuGet, вы можете встроить SDK AppsFlyer в приложение вручную:

1. Загрузите SDK приложения Universal Windows Platform <Anchor target="_blank" href="https://s3-eu-west-1.amazonaws.com/download.appsflyer.com/windows-phone-sdk/AF-Windows-SDK-v3.1.0.zip">отсюда</Anchor>.
2. Скопируйте AppsFlyerLib.winmd в свой проект.
3. В Visual Studio в проекте Universal Windows Platform нажмите ***Add Reference***.

<Image align="center" alt="" src="https://files.readme.io/5606c0bcbaaffdeea5b43f9b0201263a6ad3ab5a610ccb7b7389737e84c22844-21241888352273.png" />

* Найдите AppsFlyerLib.winmd и добавьте его.

<Image align="center" alt="" src="https://files.readme.io/fe03e297291cab276977287701e46d950c7444a47d28c01a75f01112992b57a9-21241904443153.png" />

<div id="important-1" />

> 🚧 **Важно!**
>
> AppsFlyer использует пакет Newtonsoft.json. Это стандартная библиотека для парсинга Json в Windows. Вы можете добавить этот пакет через NuGet в Visual Studio. Это устраняет исключение File Not Found в DLL.
>
> * В Visual Studio щелкните правой кнопкой мыши References, выберите NuGet-пакет Newtonsoft.json и добавьте его.
> * Разрешите доступ к интернету в манифесте приложения или используйте вкладку Capabilities в Visual Studio.

<div id="2-sdk-initialization--installation-event-minimum-requirement-for-attributing" />

## 2. Инициализация SDK & событие установки (минимальное требование для атрибуции)

* Добавьте следующий код в метод запуска приложения.
* Укажите свои appId и DevKey:
  * Заполните tracker.appId и tracker.devKey своими значениями.
  * DevKey AppsFlyer можно найти на нашем дэшборде в разделе интеграции SDK.

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

<div id="recording-app-launchasynchronously" />

### Асинхронная запись запуска приложения

Вы можете записывать запуск приложения асинхронно. Это полезно в случаях, когда сеть недоступна или не отвечает. Такие случаи можно обрабатывать в функции callback, которую вы передаете методу `TrackAppLaunchAsync`.

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

<div id="3-in-app-event-recording-api-optional" />

## 3. 3. API для записи событий в приложении (необязательно)

Этот API позволяет AppsFlyer записывать события после установки. Эти события определяет рекламодатель; помимо имени события они могут включать необязательные значения события. Добавьте следующий код, чтобы записывать события после установки:

```csharp
public void TrackEvent(string eventName, IDictionary<string, Object> eventValues)
```

* *eventName* — это любая строка, определяющая имя события. Список рекомендованных имен событий можно найти <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview">здесь</Anchor>.
* *eventValues* — это словарь параметров события, которые составляют событие. Список рекомендуемых параметров можно найти <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview">здесь</Anchor>.
* При учете дохода в событиях в приложении используйте имя константного параметра InAppEventParameterName.REVENUE («af\_revenue»), чтобы учитывать доход как часть события в приложении. Этому параметру можно назначить любое числовое значение — положительное или отрицательное.

<div id="example" />

> 📄 **Например**
>
> ```csharp
> AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
>       IDictionary<string, object> eventValues = new Dictionary<string, object>();
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CONTENT_ID, "id123");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.REVENUE, "10");
>       eventValues.Add(AppsFlyerLib.AFInAppEventParameterName.CURRENCY, "USD");
>       tracker.TrackEvent(AppsFlyerLib.AFInAppEventType.ADD_TO_CART, eventValues);
> ```

<div id="recording-events-asynchronously" />

### Асинхронная запись событий

Вы можете записывать события асинхронно. Это полезно в кейсах, когда сеть недоступна или не отвечает. Такие кейсы можно обрабатывать в функции Callback, которую вы передаете методу `TrackEventAsync`.

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

Полный список расширенных событий AppsFlyer в приложении доступен <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview">здесь</Anchor>.

<div id="4-advanced-integration" />

## 4. Расширенная интеграция

Следующие API являются необязательными и относятся к расширенной интеграции с AppsFlyer SDK.

<div id="41-set-currency-code-optional" />

### 4.1 Установка кода валюты (необязательно)

Можно установить коды конкретных валют, используемых в каждом внутреннем событии приложения, которые передаются в AppsFlyer. Еще можно установить код глобальной валюты.

USD — значение по умолчанию. Допустимые коды валют ISO можно найти <Anchor target="_blank" href="http://www.xe.com/iso4217.php">здесь</Anchor>.

Чтобы установить код валюты, используйте этот API:

```csharp
tracker.currencyCode = "GBP";
```

<div id="42-getappsflyeruid-optional" />

### 4.2 getAppsFlyeruid (необязательно)

Для каждой новой установки приложения AppsFlyer создает уникальный идентификатор ID.

Чтобы получить этот идентификатор ID, используйте следующий API:

```csharp
public string getAppsFlyerUID()
```

<div id="43-customer-user-id-optional" />

### 4.3 Идентификатор пользователя клиента (необязательно)

Установка собственного идентификатора клиента позволяет сопоставить ваш уникальный идентификатор с идентификатором пользователя AppsFlyer и всеми остальными идентификаторами устройств. Этот идентификатор ID доступен в CSV-отчетах AppsFlyer, а также через API postback для сопоставления с вашими внутренними идентификаторами.

Для установки своего Customer User ID используйте такой код:

```csharp
tracker.customerUserId = "YOUR_CUSTOMER_USER_ID";
```

<div id="44-getconversiondataasync-optional" />

### 4.4 GetConversionDataAsync (необязательно)

С помощью этого API вы можете получать данные конверсии по каждой установке через SDK. Добавьте следующий код, чтобы записывать события после установки:

```csharp
Task.Run(async () =>
{
   AppsFlyerLib.AppsFlyerTracker tracker = AppsFlyerLib.AppsFlyerTracker.GetAppsFlyerTracker();
   string conversionData = await tracker.GetConversionDataAsync();
});
```

<div id="45-c--cx-integration-example" />

### 4.5 Пример интеграции C++ / CX

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

<div data-zendesk-anchors="h_01H9G0X6VRCJCGHXWNJ2XFAQN9=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE 2-initial-steps=1-%D1%8D%D1%82%D0%B0%D0%BF%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01H9G0X6VRQJ860K5QS7DE9DT4=1-%D1%8D%D1%82%D0%B0%D0%BF%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01H9G0X6VRJ3KKZD6XM202NEX2=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE-1 3-sdk-initialization-installation-event-minimum-requirement-for-attributing=2-%D0%B8%D0%BD%D0%B8%D1%86%D0%B8%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-sdk--%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%BC%D0%B8%D0%BD%D0%B8%D0%BC%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D0%B5-%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01H9G0X6VR9FW15TYS06M3JBYM=2-%D0%B8%D0%BD%D0%B8%D1%86%D0%B8%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-sdk--%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%BC%D0%B8%D0%BD%D0%B8%D0%BC%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D0%B5-%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 recording-app-launch%C2%A0asynchronously=%D0%B0%D1%81%D0%B8%D0%BD%D1%85%D1%80%D0%BE%D0%BD%D0%BD%D0%B0%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8C-%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9G0X6VR6JHKGPTWERQGZNMW=%D0%B0%D1%81%D0%B8%D0%BD%D1%85%D1%80%D0%BE%D0%BD%D0%BD%D0%B0%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8C-%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F 4-inapp-event-recording-api-optional=3-3-api-%D0%B4%D0%BB%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE h_01H9G0X6VRSBKYX4AJK5ZQ14EK=3-3-api-%D0%B4%D0%BB%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE h_01H9G0X6VS1RA8K4EW4K1Q8B6P=%D0%BD%D0%B0%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 recording-events-asynchronously=%D0%B0%D1%81%D0%B8%D0%BD%D1%85%D1%80%D0%BE%D0%BD%D0%BD%D0%B0%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8C-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01H9G0X6VS5PYNZEZG86QJTSPJ=%D0%B0%D1%81%D0%B8%D0%BD%D1%85%D1%80%D0%BE%D0%BD%D0%BD%D0%B0%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8C-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 5-advanced-integration=4-%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D0%B0%D1%8F-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F h_01H9G0X6VSW4A5B044HF1704XH=4-%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D0%B0%D1%8F-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F 51-set-currency-code-optional=41-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D0%BA%D0%BE%D0%B4%D0%B0-%D0%B2%D0%B0%D0%BB%D1%8E%D1%82%D1%8B-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE h_01H9G0X6VSY3975EZNGD2NDSMR=41-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D0%BA%D0%BE%D0%B4%D0%B0-%D0%B2%D0%B0%D0%BB%D1%8E%D1%82%D1%8B-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE 52-getappsflyeruid-optional=42-getappsflyeruid-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE h_01H9G0X6VS4MF8S85049HFJD8K=42-getappsflyeruid-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE 53-customer-user-id-optional=43-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE h_01H9G0X6VSM167RKESECBQCPZD=43-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE 54-getconversiondataasync-optional=44-getconversiondataasync-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE h_01H9G0X6VSJWZ3BFWP4AFMZXXY=44-getconversiondataasync-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE 55-c-cx-integration-example=45-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-c--cx h_01H9G0X6VSRNZXN8A22Q8KYYJR=45-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-c--cx" />

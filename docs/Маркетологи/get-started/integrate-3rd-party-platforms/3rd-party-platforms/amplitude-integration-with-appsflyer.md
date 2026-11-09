---
title: Интеграция Amplitude с AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Amplitude
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-08-02T05:18:03Z'
  edited_at: '2026-09-11T00:10:24Z'
  id: 211200306
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/211200306
---
> **At a glance:** **Краткий обзор:** Интегрируйте AppsFlyer с Amplitude, чтобы делиться данными атрибуции пользователей и аналитикой по событиям для лучшего понимания вовлечённости пользователей, удержания и дохода. Выберите **одну из двух версий интеграции: V1 или V2** в зависимости от ваших целей и потребностей в аналитике.

<div id="about-the-integration" />

## Об интеграции

Amplitude, интегрированный партнёр AppsFlyer, является платформой для аналитики продуктов, которую используют специалисты по продукту, росту и маркетингу для понимания поведения пользователей на мобильных и веб-платформах. Интеграция позволяет AppsFlyer отправлять ключевые данные о событиях в Amplitude после установки, что позволяет проводить комплексный анализ на уровне пользователей.

Существует две версии интеграции Amplitude:

* **Amplitude V1:**  
  Эта версия использует API атрибуции Amplitude. AppsFlyer отправляет данные об установках, собранные после завершения интеграции. Amplitude использует идентификатор рекламы в качестве идентификатора и удаляет данные, если в течение 72 часов не зарегистрировано соответствующее событие пользователя. <Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/attribution">Подробнее</Anchor>
* **Amplitude V2:**  
  Эта версия использует HTTP V2 API Amplitude. AppsFlyer отправляет как данные об установках, так и данные о событиях в приложении после завершения интеграции. Приоритет отдаётся идентификаторам (user\_id и device\_id) и, если сопоставление не удаётся, регистрируется новый пользователь. <Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/http-v2">Подробнее</Anchor>

<span id="h_01JSE81SX1FR182N1CZJ5CQP5N"></span>**<span id="integration-methods"></span>Версии интеграции:**

| Версия | Используемый API | Используемые идентификаторы | Охват событий |
| --- | --- | --- | --- |
| **V1** | API атрибуции | Рекламный идентификатор (AdID) | Только установки |
| **V2** | HTTP V2 API | `user_id`, `device_id` (логика резервного варианта) | Установки и внутренние события приложения |

> 🚧 **Important**
>
> **Двоеточие (:)**
>
> * Выберите интеграцию Amplitude V1 или V2. **Не используйте обе версии** одновременно. Использование обеих версий одновременно может привести к отправке дублирующихся событий в Amplitude.
> * Некоторые медиа-источники ограничивают передачу данных третьим лицам. Постбэки для ограниченных событий не будут отправляться этому партнёру, даже если они настроены.

<div id="prerequisites" />

## Необходимые условия

**Прежде чем начать:**

* Свяжитесь с Amplitude, чтобы создать учётную запись, если у вас её ещё нет.
* Выберите версию интеграции Amplitude: **V1** или **V2**.
* Проверьте, чтобы у вас не отправлялись одни и те же события как из SDK Amplitude, так и из AppsFlyer, чтобы предотвратить дублирование.
* См. дополнительные необходимые условия для интеграции Amplitude V2.

<div id="additional-prerequisites-for-the-amplitude-v2-integration" />

### Дополнительные необходимые условия для интеграции Amplitude V2.

Для интеграции V2 необходимо настроить:

* [Идентификатор устройства Amplitude](/docs/amplitude-integration-with-appsflyer#идентификатор-устройства-amplitude)
* [Идентификатор пользователя клиента](/docs/amplitude-integration-with-appsflyer#идентификатор-пользователя-клиента)
* [Идентификатор сессии Amplitude](/docs/amplitude-integration-with-appsflyer#идентификатор-сессии-amplitude)

<div id="amplitude-device-id" />

#### Идентификатор устройства Amplitude

Чтобы включить атрибуцию на уровне пользователя, вы должны передать идентификатор устройства Amplitude в SDK AppsFlyer. Это значение отправляется с каждым постбэком.

<Tabs>
<Tab title="Android iOS">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeDeviceId", amplitude.getDeviceId())
```

**Язык:** Java/Kotlin

**Документация:** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata">Справка по Android SDK</Anchor>, <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/android/android-kotlin-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Objective-C)">

```objectivec
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeDeviceId": [[Amplitude instance] getDeviceId]}];
```

**Язык:** Objective-C

**Документация:** [Справочник по iOS SDK](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeDeviceId": Amplitude.instance().getDeviceId()]
```

**Язык:** Swift

**Документация:** [Справочник по iOS SDK](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();  
customData.Add("AmplitudeDeviceId", Amplitude.getInstance().getDeviceId());  
AppsFlyer.setAdditionalData(customData);
```

**Язык:** C#

**Документация:** [Справочник по Unity SDK](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="iOS native UnityReact Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()},  
(res) => {  
//...  

}  
);
```

**Язык:** JavaScript

**Документация:** [Справочник по React Native SDK](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()});
```

**Язык:** JavaScript

**Документация:** Не применимо

</Tab>

<Tab title="Flutter">

```
var data = {"AmplitudeDeviceId": amplitude.getDeviceId()};  
appsFlyerSdk.setAdditionalData(data);
```

**Язык:** Dart

**Документация:** [Справочник по SDK Flutter](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="customer-user-id" />

#### Идентификатор пользователя клиента

Настройка идентификатора пользователя (CUID). Это уникальный идентификатор, который обычно генерируется и устанавливаемый владельцем приложения во время регистрации пользователя.  
 <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid?utm_source=chatgpt.com">Подробнее</Anchor>

<div id="amplitude-session-id" />

#### Идентификатор сессии Amplitude

Настройте идентификатор сессии Amplitude и передайте его в AppsFlyer (необязательно). <Anchor target="_blank" href="https://amplitude.com/docs/data/sources/instrument-track-sessions">Подробнее</Anchor>

<Tabs>
<Tab title="Android iOS">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeSessionId", amplitude.getSessionId())
```

**Язык:** Java/Kotlin

**Документация:** [Справочник по SDK Android](https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Objective-C)">

```objectivec
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeSessionId": [[Amplitude instance] getSessionId]}];
```

**Язык:** Objective-C

**Документация:** [Справочник по SDK iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeSessionId": Amplitude.instance().getSessionId()]
```

**Язык:** Swift

**Документация:** [Справочник по SDK iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();  
customData.Add("AmplitudeSessionId", Amplitude.getInstance().getSessionId());  
AppsFlyer.setAdditionalData(customData);
```

**Язык:** C#

**Документация:** [Справочник по Unity SDK](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="iOS native UnityReact Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()},  
(res) => {  
//...  

}  
);
```

**Язык:** JavaScript

**Документация:** [Справочник по React Native SDK](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()});
```

**Язык:** JavaScript

**Документация:** Не применимо

</Tab>

<Tab title="Flutter">

```
var data = {"AmplitudeSessionId": amplitude.getSessionId()};  
appsFlyerSdk.setAdditionalData(data);
```

**Язык:** Dart

**Документация:** [Справочник по SDK Flutter](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="set-up-the-integration" />

## Настройка интеграции

**Для настройки интеграции:**

1. В AppsFlyer перейдите на вкладку **Collaborate** > **Partner Integrations > Marketplace** .
2. Вкладка «Разрешения»

   <Image align="center" alt="Select Amplitude V1 doctored.png" src="https://files.readme.io/71721bb1a48dda061ce2a099522edf9baed39ef2d67edad8ac14277b42cd2d70-36713632837777.png" width="511px" />

   amplitude-blocked-data.png

   <Image align="center" alt="Select Amplitude V2.png" src="https://files.readme.io/4bbf57727a2b6e16e5205505b459a78f8642f02d1bb1c4e8f72e26b3bd9e1bd3-36713631187857.png" width="503px" />
3. После выбора версии Amplitude нажмите **Настроить интеграцию**.

   <Image align="center" alt="Click set up integration.png" src="https://files.readme.io/c13fef10fb4cf0ea12f44d56f8c3b64936376ce181a1d12c9f096ad6103c29a6-36713632857617.png" />
4. На вкладке **Интеграция**:
   * Выберите своё приложение.
   * Включите переключатель **Активировать партнёра**.

     <Image align="center" alt="Activate partner blurred.png" src="https://files.readme.io/5e0e7ae537cd89b2c561c8561de9ebc160f6d6eb0fedc5c7ba0c761ddb73632a-36713631194641.png" width="521px" />
5. Завершите настройку на оставшихся вкладках:

<Accordion title="Вкладка «Интеграция»">

Вкладка Integration («Интеграция») содержит несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнёра

При **первом заходе** сюда включите **Активацию партнёра**, чтобы настройка параметров на вкладке интеграции стала возможной. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.

<div id="general-settings" />

### Общие настройки

<div id="advanced-data-sharing" />

#### Расширенный обмен данными

Чтобы обмениваться с Amplitude дополнительной информацией об установках, включите функцию **обмена расширенными данными**. Если эта функция включена, Amplitude получает следующие данные по установкам (не по внутренним событиям), сопоставленные с перечисленными свойствами Amplitude:

| Свойство Amplitude | Точка данных AppsFlyer |
| --- | --- |
| sub\_publisher | af\_siteid |
| network\_name | pid |
| adgroup\_name | af\_adset |
| nazvanie\_kreativa | af\_ad\_id |
| installed\_at | install\_timestamp |
| search\_term | af\_keywords |
| Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>. | af\_channel |
| user\_id | af\_customer\_user\_id |
| af\_sub1 | af\_sub1 |
| af\_sub2 | af\_sub2 |
| af\_sub3 | af\_sub3 |
| af\_sub4 | af\_sub4 |
| af\_sub5 | af\_sub5 |
| Двухбуквенное сокращение названия континента | Двухбуквенное сокращение названия континента |

<div id="amplitude-eu-data-center" />

#### Центр обработки данных Amplitude в ЕС

Когда **Центр обработки данных Amplitude в ЕС** выключен, постбэки об установках отправляются в центр обработки данных в США.  
Для отправки постбэков об установках в центр обработки данных в ЕС включите Центр обработки данных Amplitude в ЕС.

<div id="api-key" />

#### Ключ API

Amplitude подключается с AppsFlyer через уникальный ключ API. Если у вас ещё нет ключа, для продолжения интеграции вы должны получить его от Amplitude или выполнить следующие шаги.

<span id="obtaining-the-api-key-from-amplitude"></span>**Получение ключа API от Amplitude**

**Примечание**: доступ к ключу API могут получить только пользователи, у которых есть роль администратора или менеджера.

1. Войдите в свой аккаунт Amplitude.
2. В правом верхнем углу страницы нажмите на значок настройки > **Organization Settings** (Настройки организации).

   <Image align="center" alt="Amplitude" src="https://files.readme.io/214df773c045239924b65a4a1e6b0a1957f6b7ea09e225af80d83ffa0a469c26-16258070772625.png" width="240px" />
3. Нажмите **Projects** (Проект) и выберите проект, из которого нужно отправлять данные в AppsFlyer.

   <Image align="center" alt="amplitude" src="https://files.readme.io/eaf158e4505f47f8da0fdae4f97be773ab32910352b50cab5ca5d4de3e8782ac-16335170399505.png" />
4. На вкладке **Project** (Проект) скопируйте свой ключ API.

   <Image align="center" alt="Amplitude" src="https://files.readme.io/cf65648a9a8c122febe2b36fd4bd0b9f7f436cac49cfeec7f41870f614a16c6c-16258070773649.png" width="648px" />
5. Перейдите к настройке Amplitude на дэшборде AppsFlyer.

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки в Amplitude после установки пользователя. В этом разделе можно определить источник пользователей, которому нужно отправлять постбэки. Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">постбэках по умолчанию</Anchor>.

<Image align="center" alt="Screenshot 2025-12-03 at 1.57.03 PM.png" src="https://files.readme.io/3454ca573ee63ea076251459a9c619a747fc5640862e83582b2d10a985c2489a-41748033847953.png" width="703px" />

<div id="in-app-event-settings" />

### Настройки внутренних событий приложения

* Введите ключ API.
* Когда **Центр обработки данных Amplitude** выключен, постбэки о внутренних событиях отправляются в центр обработки данных в США.  
  **Для отправки постбэков о внутренних событиях в центр обработки данных в ЕС включите Центр обработки данных Amplitude.**

После сохранения конфигурации AppsFlyer отправляет в Amplitude следующие данные:

* Идентификатор устройства (IDFV / Google Advertising ID)
* Источник медиа
* Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>.

Отправка IDFA для устройств iOS осуществляется с согласия пользователя <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">на ATT и с учётом настроек повышенной конфиденциальности</Anchor>.

<div id="in-app-event-postbacks" />

### Постбэки по внутренним событиям приложения

<Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">Настройка передачи постбэков по внутренним событиям приложения</Anchor> в Amplitude.

</Accordion>

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для Amplitude.

</Accordion>

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с этим партнёром.

</Accordion>

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнёром.

</Accordion>

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для Amplitude.

</Accordion>

<div id="viewing-attribution-data-in-the-amplitude-console" />

## Просмотр данных атрибуции в консоли Amplitude

Данные атрибуции, отправленные из AppsFlyer в Amplitude, отображаются на ваших дэшбордах в виде событий и свойств с префиксом **[AppsFlyer]**:

<Image align="center" alt="amplitude-properties.png" src="https://files.readme.io/bf52831ea6060172ce251136f47962ffb7f1ec9ffce13b9e35c614c4178e77f1-360009623597.png" />

> 🚧 **Important**
>
> **Двоеточие (:)**
>
> В некоторых случаях Amplitude показывает данные, полученные от AppsFlyer, как «Заблокировано». Если вы не видите данные AppsFlyer в Amplitude, проверьте, не определено ли это событие как заблокированное.

<div id="sending-amplitude-events-to-appsflyer" />

## Отправка событий Amplitude в AppsFlyer

Эта интеграция также позволяет отправлять ваши события Amplitude в AppsFlyer через API сервер-сервер. См. <Anchor target="_blank" href="https://www.docs.developers.amplitude.com/data/destinations/appsflyer/">документацию Amplitude</Anchor>, чтобы узнать, как это сделать.

<div data-zendesk-anchors="about-the-integration=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01JSE81SX1B1RH978Y08W1XXX8=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 set-up-the-integration=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01JSE958V510B9P6VEQTXC55S7=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F additional-prerequisites-for-the-v2-integration=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-amplitude-v2 h_01JSKEMMEB00PERVQWPYNF5V2E=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-amplitude-v2 amplitude-device-id=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0-amplitude h_01JSKFH7KPSE5P0CRPVJ3FJ2WN=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0-amplitude customer-user-id=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0 h_01JSKFK4BFH3PP98XAZ0W8GG11=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0 amplitude-session-id=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%81%D0%B5%D1%81%D1%81%D0%B8%D0%B8-amplitude h_01JSKFQXPPJVCW68C4H9B4EJ76=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%81%D0%B5%D1%81%D1%81%D0%B8%D0%B8-amplitude set-up-the-integration::45aa5acf=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01JSKFQAZ8Q76KF1JJKZTAPVBQ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0 01H8KPA9JKDRA680Y0WPZ172EM=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 01H8KPA9JKF4VCA4S22SYT40WT=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 advanced-data-sharing=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B9-%D0%BE%D0%B1%D0%BC%D0%B5%D0%BD-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8 01H8KPA9JKJ2XN1AEPV74QVJYZ=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B9-%D0%BE%D0%B1%D0%BC%D0%B5%D0%BD-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8 amplitude-data-center=%D1%86%D0%B5%D0%BD%D1%82%D1%80-%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-amplitude-%D0%B2-%D0%B5%D1%81 01H8KPA9JKP0T0FDND97VA23EY=%D1%86%D0%B5%D0%BD%D1%82%D1%80-%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-amplitude-%D0%B2-%D0%B5%D1%81 api-key=%D0%BA%D0%BB%D1%8E%D1%87-api 01H8KPA9JKDYDPDGRXZSH2BAV8=%D0%BA%D0%BB%D1%8E%D1%87-api 01H8KPA9JK510YKV47816DT7E7=obtaining-the-api-key-from-amplitude default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E 01H8KRBGYQ973CT3H8GHZ8R0BH=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-event-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F 01H8KPA9JKM4S79160BEYN3B6V=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F inapp-event-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F 01H8KSQ76XE9Z191P1RMANF6EQ=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F viewing-attribution-data-in-the-amplitude-console=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B8-amplitude 01H8KPA9JK75TA0H8T4P65BMSE=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B8-amplitude sending-amplitude-events-to-appsflyer=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-amplitude-%D0%B2-appsflyer h_01HPYFZDX1WWDWJEBZ4DK706B4=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-amplitude-%D0%B2-appsflyer" />

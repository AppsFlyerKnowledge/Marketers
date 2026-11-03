---
title: Интеграция Braze (ранее Appboy) с AppsFlyer
metadata:
  keywords:
    - Appboy
    - Advertisers
    - Ad Networks
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
  created_at: '2017-03-30T08:39:03Z'
  edited_at: '2026-08-28T00:10:22Z'
  id: 115001603343
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/115001603343
---
> **At a glance:** Braze, интегрированный партнер AppsFlyer, предлагает платформу для взаимодействий на протяжении всего жизненного цикла продуктов для команд маркетинга, развития и вовлечения клиентов. Платформа позволяет маркетологам налаживать прямые контакты со своими клиентами, способствуя глубокому вовлечению и повышению рентабельности инвестиций. Центром нашей платформы является целостный профиль пользователя, который предлагает единое представление о клиенте.

Узнайте больше на сайте <Anchor target="_blank" href="https://www.braze.com/">braze.com</Anchor>.

> 🚧 **Important**
>
> **Вкладка «Затраты»**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнеру, независимо от настроенной отправки постбэков.
> * Постбэки не будут отправляться, если источник — органический.

## Обзор интеграции

Чтобы настроить интеграцию с Braze, следуйте инструкциям ниже.

Минимальные требования — AppsFlyer SDK:

* <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">Android</Anchor> (Android SDK – версия 2.3.1.18 и выше)
* <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png</Anchor>

На Android для интеграции с Braze необходимо, чтобы <Anchor target="_blank" href="https://www.braze.com/docs/partners/advertising_technologies/attribution/appsflyer/#integration">идентификатор устройства</Anchor> Braze (уникальный идентификатор пользователя Braze) был указан в SDK AppsFlyer для Android. Этот параметр отправляется с каждым постбэком и позволяет идентифицировать каждого пользователя. Для этого необходимо вставить в код приложения следующие строки:

> 📘 **Note**
>
> **Важно!**
>
> Убедитесь, что строки кода вставлены в правильное место — после запуска Braze SDK и перед кодом инициализации AppsFlyer SDK (см. раздел «Инициализация SDK» в нашем Руководстве по интеграции Android SDK).

<Tabs>
<Tab title="Android;">

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId =(Braze.getInstance(MyActivity.this).getDeviceId());
customData.put("brazeCustomerId", deviceId);
AppsFlyerLib.getInstance().setAdditionalData(customData);
```

</Tab>

<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

**Swift**

Есть два API Swift: один с обработчиком завершения, а другой использует новую поддержку параллельных процессов Swift. Оба они выдают одно и то же значение — выбор того, какое из них использовать, зависит от контекста.

**Обработчик завершения Swift**

```swift
let configuration = Braze.Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
braze.deviceId {
    brazeDeviceId in
    AppsFlyerLib.shared().customData = [“brazeDeviceId”: brazeDeviceId]
}
```

**Swift await**

```swift
let configuration = Braze.Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
let brazeDeviceId = await braze.deviceId()
AppsFlyerLib.shared().customData = ["brazeDeviceId": brazeDeviceId]
```

**Objective C**

```objectivec
BRZConfiguration *configurations = [[BRZConfiguration alloc] initWithApiKey:@"BRAZE_API_KEY" endpoint:@"BRAZE_END_POINT"];
[configurations setUseUUIDAsDeviceId:NO];
Braze *braze = [[Braze alloc] initWithConfiguration:configurations];
[braze deviceIdWithCompletion:^(NSString * _Nonnull brazeDeviceId) {
    NSLog(@">>[BRZ]: %@", brazeDeviceId);
    [[AppsFlyerLib shared] setAdditionalData:@{
        @"brazeDeviceId": brazeDeviceId
    }];
}];
```

</Tab>

<Tab title="Unity">

```csharp
Appboy.AppboyBinding.getDeviceID()
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("brazeCustomerId", Appboy.AppboyBinding.getDeviceId());
AppsFlyer.setAdditionalData(customData);
```

</Tab>
</Tabs>

## Настройка Braze

**Необходимые условия:** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт. Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В AppsFlyer в боковом меню выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** вам необходимо ***активировать партнера***, чтобы включить настройку параметров вкладки интеграции.Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером.  
    Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже. Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner">партнерских интеграциях</Anchor>.

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

### Активация партнера

При **первом посещении** вам необходимо ***Активировать партнера***, чтобы включить настройку параметров вкладки интеграции. Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

### Общие настройки

Braze подключается к AppsFlyer через уникальный ключ API и конечную точку REST.

**Чтобы получить ключ API Braze и конечную точку REST:**

1. В своем аккаунте Braze в разделе **Технологические** **партнеры** перейдите в раздел **Атрибуция**.
2. Выберите **AppsFlyer**.  ![Выберите AppsFlyer в качестве технологического партнера в Braze](https://files.readme.io/db96e8b5e2363f5250c6c1146a1f7a15e1ed6457fe4543dbe649f8818bb5db78-360017328637.png)
3. В разделе **Импорт данных для атрибуции установок** нажмите «Сгенерировать ключ API».
4. braze-af-API-key.png
5. В AppsFlyer вставьте ключ API Braze и конечную точку REST.  ![Подробное описание заголовка окна настройки параметров партнера см. здесь.](https://files.readme.io/b13aba84c394c0b4603e0aad2edd723525dadf204250349620b571bc47b0ba9d-360001907229.png)
6. Нажмите **Сохранить и закрыть**.

После сохранения конфигурации AppsFlyer отправляет в Braze следующие данные для каждой органической и неорганической установки:

* Braze Dev\_ID
* Медиа-источник
* Название кампании
* Название группы объявлений
* Название объявления

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки об установках пользователей Braze. В этом разделе можно определить отправку этих постбэков.

 ![Раздел стандартных постбэков](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png) 

Выберите **События, атрибутированные любому партнеру или органически**, чтобы отправлять постбэки в Braze для любого пользователя, который загружает приложение.

Нажмите кнопку **Сохранить.**

> 📘 **Note**
>
> **Примечание**
>
> Хотя все события отправляются AppsFlyer, органические установки не учитываются в Braze и, следовательно, игнорируются API Braze.

</Accordion>

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для Braze.

</Accordion>

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с этим партнером.

</Accordion>

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнером.

</Accordion>

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения для Braze недоступны.

</Accordion>

## Просмотр данных атрибуции пользователя в Braze

Базу пользователей можно сегментировать по данным атрибуции на панели инструментов Braze с помощью фильтров атрибуции установки.

 ![Установите фильтры атрибуции установок в дэшборде Braze](https://files.readme.io/7289491d4d301eb38618298536ac5b895a610024bf162c733409d3f50b10b8f4-360001908045.png) 

Кроме того, данные об атрибуции конкретного пользователя доступны в профиле каждого пользователя на панели инструментов Braze.

 ![Braze_msc_new_2.png](https://files.readme.io/d9ee5206a8bf3c092c5297c361cf38b2c77717fbb9638b282032e4fc4c31091e-360001907289.png)
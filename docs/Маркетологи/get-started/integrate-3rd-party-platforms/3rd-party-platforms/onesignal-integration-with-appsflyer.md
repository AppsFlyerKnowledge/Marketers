---
title: Интеграция OneSignal с AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2020-11-29T08:11:41Z'
  edited_at: '2026-08-19T00:11:37Z'
  id: 360015926437
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/360015926437
---
> **At a glance:** OneSignal — ведущий на рынке поставщик push-уведомлений и рассылки в приложении, обслуживающий более 1 миллиона разработчиков и маркетологов с помощью передовой платформы для вовлеченности.

![onesignal-logo-stack__3_.png](https://files.readme.io/49c50c481c00391f25cf8cc7eb2c35cc166f6a88a10db9120769a7d11affa26a-13013733757841.png)

OneSignal ежедневно доставляет 8 миллиардов сообщений по всему миру. Благодаря превосходной архитектуре и удобной в использовании платформе OneSignal доставляет сообщения быстрее, эффективнее и в большем масштабе, чем любое другое решение в мире. Узнать больше на сайте [onesignal.com](https://onesignal.com/?utm_medium=partner&utm_source=appsflyer)

> 🚧 **Important**
>
> **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнеру, независимо от настроенной отправки постбэков.

<div id="setting-up-onesignal" />

## Настройка OneSignal

Интеграция с OneSignal включает добавление нескольких строк кода в SDK AppsFlyer в вашем приложении, а затем активацию интеграции в AppsFlyer.

<div id="set-up-the-appsflyer-sdk" />

### Настройка AppsFlyer SDK

При использовании Android для интеграции с OneSignal необходимо, чтобы OneSignal Player ID (уникальный идентификатор пользователя OneSignal) был указан в Android SDK AppsFlyer. Этот параметр отправляется с каждым постбэком и позволяет идентифицировать каждого пользователя.

**Чтобы настроить SDK AppsFlyer для Android:**

1. Убедитесь, что версия SDK, которую вы используете, — 2.3.1.18 или выше.
2. Вставьте следующие строки кода в код приложения — [после запуска SDK OneSignal](https://documentation.onesignal.com/docs/android-sdk-setup) и перед кодом инициализации SDK AppsFlyer.
   * Для устройств Android с OneSignal SDK версии 3.x.x:

     ```http
     OSPermissionSubscriptionState status = OneSignal.getPermissionSubscriptionState();

               String deviceId = status.getSubscriptionStatus().getUserId();

                 customData.put("onesignalCustomerId", deviceId);
     ```
   * Для Unity SDK:

     ```http
     var status = OneSignal.GetPermissionSubscriptionState();

               String deviceId = status.subscriptionStatus.userId;

                 customData.put("onesignalCustomerId", deviceId);
     ```
   * Для устройств Android с OneSignal Native SDK версии 4+:

     ```http
     OSDeviceState device = OneSignal.getDeviceState();

               String deviceId = device.getUserId();

                 customData.put("onesignalCustomerId", deviceId);
     ```

**Чтобы настроить SDK AppsFlyer для iOS:**

1. Убедитесь, что версия SDK, которую вы используете, — 2.3.1.18 или выше.
2. Вставьте следующие строки кода в код приложения — [после запуска SDK OneSignal](https://documentation.onesignal.com/docs/android-sdk-setup) и перед кодом инициализации SDK AppsFlyer.
   * Для устройств iOS с OneSignal SDK версии 2.x.x:

     <Tabs>
     <Tab title="Swift">

     ```http
     let status: OSPermissionSubscriptionState = OneSignal.getPermissionSubscriptionState()
     if let deviceId = status.subscriptionStatus.userId{
         customData.put("onesignalCustomerId", deviceId);
     ```

     </Tab>

     <Tab title="Objective C">

     ```http
     OSPermissionSubscriptionState* status = [OneSignal getPermissionSubscriptionState];
     NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:status.subscriptionStatus.userId, @"onesignalCustomerId", nil];
     [[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
     ```

     </Tab>
     </Tabs>

   * Для устройств iOS с OneSignal Native SDK версии 3+:

     <Tabs>
     <Tab title="Swift">

     ```http
     if let deviceState = OneSignal.getDeviceState() {
         let deviceId = deviceState.userId
         customData.put("onesignalCustomerId", deviceId);
     ```

     </Tab>

     <Tab title="Objective C">

     ```http
     OSDeviceState *deviceState = [OneSignal getDeviceState];
     NSString *deviceId = deviceState.userId;
     NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:deviceId, @"onesignalCustomerId", nil];
     [[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
     ```

     </Tab>
     </Tabs>

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.  
    **Примечание. <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Узнать больше</Anchor>**
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе:

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

![onesignal-integration-tab.png](https://files.readme.io/95ec88041360d492367ed383aa3242bebe1cd5c5abcff8fba64e7888f0a9c052-360017329277.png)

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

Этот параметр должен быть включен всё время, пока вы работаете с партнером.  
Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation#активировать-интеграцию-партнера">активации партнёров</Anchor>.

<div id="general-settings" />

### Общие настройки

<div id="onesignal-appid" />

#### AppID OneSignal

Идентификатор приложения OneSignal доступен на платформе OneSignal в разделе **Settings** > **Keys & IDs**.Чтобы подключить аккаунт OneSignal к AppsFlyer, введите идентификатор вашего приложения в поле **OneSignal AppID**.

![onesignal-app-id-en_us.png](https://files.readme.io/2801bce8ea7ef4be731d8429bd0408f432d4b5600fbd359e989b0013da56b93e-360015238678.png)

<div id="default-postbacks" />

### Постбэки по умолчанию

![onesignal-default-postbacks_en-us.png](https://files.readme.io/07e40365685543a318be8a16c9ea83638634d4a60333338eca0f76d140f84bef-360014377697.png)

AppsFlyer может отправлять автоматические постбэки в OneSignal после установки приложения пользователем. В этом разделе можно определить источник пользователей, которым отправляются постбэки для каждого события.  
Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">постбэках по умолчанию</Anchor>.

**Чтобы отправлять постбэки в OneSignal для любого пользователя, загрузившего приложение**, выберите **Все медиаисточники, включая органические**.

**Чтобы завершить настройку интеграции,** нажмите **Сохранить интеграцию**.

Хотя все события отправляются AppsFlyer, органические установки не учитываются в OneSignal и, следовательно, игнорируются API OneSignal.

После сохранения конфигурации AppsFlyer отправляет в OneSignal следующие данные для каждой органической и неорганической установки:

* Медиаисточник
* Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>.
* DeviceID
* Идентификатор

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для этого партнера.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о стоимости неприменимы при интеграции с этим партнёром.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы неприменим при интеграции с этим партнёром.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для этого партнера.

</Accordion>

<div id="view-user-attribution-data-in-onesignal" />

## Просмотр данных атрибуции пользователя в OneSignal

Вы можете просматривать атрибуцию в редакторе сегментов в тегах OneSignal — как на уровне отдельного устройства, так и при создании сегмента для использования в кампании.

![onesignal-view-attribution_en-us.png](https://files.readme.io/ac23c9310cad560f692598127f3e9efb7c2b905efb6fd5de21efabe90bf58eea-360014377737.png)

<div data-zendesk-anchors="setting-up-onesignal=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-onesignal h_01H9HWJTEYDEZ8AGVQBHZZTP7K=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-onesignal set-up-the-appsflyer-sdk=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-appsflyer-sdk h_01H9HWJTEY71PTXR1YSAK709QT=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-appsflyer-sdk h_01H9HWJTEZC62F9JW1KD4Y1CYS=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9HWJTEZH60AEPE7AB43X4YG=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9HWJTEZJAK2PTF4HQP3DQ1X=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 onesignal-appid=appid-onesignal h_01H9HWJTEZCNZX17K86H9KCRFN=appid-onesignal default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9HWJTEZ91KR3ZA8NX5BVZCF=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9HWJTEZZYRBS6PPRBBQAXZ5=attribution-link-tab h_01H9HWJTEZNT0EHJ7G4SFRD8K5=cost-tab h_01H9HWJTEZS7TN4FCAN40QB1NT=ad-revenue-tab h_01H9HWJTEZEY5VKCKDZ1Q7APRG=permissions-tab view-user-attribution-data-in-onesignal=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%B2-onesignal h_01H9HWJTEZZTJFTZC1Z2A6F5QM=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%B2-onesignal" />

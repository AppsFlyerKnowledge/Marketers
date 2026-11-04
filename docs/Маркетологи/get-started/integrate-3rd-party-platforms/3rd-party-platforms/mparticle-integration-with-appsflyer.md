---
title: Интеграция mParticle с AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - mParticle
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
  created_at: '2016-04-03T05:31:23Z'
  edited_at: '2026-08-28T00:11:05Z'
  id: 209787323
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/209787323
---
> **At a glance:** mParticle — интегрированный партнер AppsFlyer — собирает данные клиентов и отправляет их на различные платформы для аналитики, маркетинга и хранения данных.

> 🚧 **Important**
>
> **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнеру, независимо от настроенной отправки постбэков.

<div id="event-integrations" />

## Интеграции событий

Этот документ содержит сведения о том, как активировать данные событий из mParticle в AppsFlyer.

1. Клиенты mParticle должны интегрировать набор AppsFlyer Kit в своё приложение. SDK mParticle инициализирует SDK AppsFlyer, а также перенаправляет все необходимые события жизненного цикла в SDK AppsFlyer.

2. Подробнее о том, как настроить AppsFlyer kit с SDK mParticle в вашем приложении, см. в репозиториях GitHub SDK для <Anchor target="_blank" href="https://github.com/mParticle/mParticle-apple-SDK">iOS</Anchor> и <Anchor target="_blank" href="https://github.com/mParticle/mparticle-android-sdk">Android</Anchor>.

<div id="configure-the-appsflyer-event-integration" />

### Настройка интеграции событий AppsFlyer

1. На дэшборде mParticle ([https://app.mparticle.com](https://app.mparticle.com)) выберите свое Приложение (также называется Workspace)

2. Нажмите **Каталог** в левом меню навигации.

3. Нажмите плитку AppsFlyer, чтобы открыть сведения об интеграции, включая такие данные, как категории, доступные платформы, минимальные версии SDK mParticle (если есть), типы данных, идентификаторы пользователей, идентификаторы устройств, доступные события и доступные конфигурации.

![Плитка AppsFlyer в каталоге mParticle](https://files.readme.io/afa886e48f2cddde39007275a72ce03c4a6c4182408bb2ad4c8c183b1591b47d-115015666683.png)

4. Кликните **Добавить AppsFlyer к настройке**.

Откроется окно **Add to Setup**:

![mParticle Окно Add to Setup](https://files.readme.io/1eccc4ea365d41d4228eb07f4df88641458244b303ac8805932bf42ef4df5a74-115015476946.png)

5. Выберите тип интеграции **Output Event** и нажмите &lt;0>Добавить в настройки0>, чтобы открыть экран настройки конфигурации событий и продолжить процесс настройки.

![mParticle Экран настройки конфигурации событий](https://files.readme.io/9a4720fef99a21a67fd017f4485e73765ebcb7aeb126f5342cc911aff4a345d2-115015476966.png)

6. Введите параметры конфигурации AppsFlyer и нажмите **Сохранить**:

* Название конфигурации
* Используйте одинаковые настройки для сред разработки и продакшена.
* Ключ разработчика
* Созданная вами конфигурация отображается в группе AppsFlyer Default Group

![Конфигурация AppsFlyer, показанная в группе AppsFlyer Default Group](https://files.readme.io/4d82533f311b93373152f046e92fe46c5e515cb8f5084bb89e81bfcae608172c-115015666803.png)

Следующий шаг – установить связь между входными платформами и конфигурацией выходных событий AppsFlyer.

7. Нажмите **Соединения**.

8. Выберите входную платформу (в данном примере – iOS), затем нажмите **Подключить выход**.

9. Выберите карточку AppsFlyer, а затем выберите конфигурацию AppsFlyer, созданную ранее.

10. Введите настройки подключения AppsFlyer:   
Apple App ID (введите только номер, без префикса ID). Например, если ваш App ID — **id123456789**, введите **123456789**.)

![Экран настроек подключения AppsFlyer](https://files.readme.io/2fb4c7480c5813bf7d893318de5c4a8edfe3649293bf51c8dae422be65db726e-115015477066.png)

11. Нажмите **Добавить подключение**.

AppsFlyer теперь отображается как подключенный выходной источник. Могут быть доступны дополнительные параметры, например пользовательские сопоставления. Подробнее см. в <Anchor target="_blank" href="https://docs.mparticle.com/guides/getting-started/connect-an-event-output#outputs">документации mParticle</Anchor>.

![AppsFlyer отображается как подключенный вывод](https://files.readme.io/53ea474eeb94c551677dd7a4ce190d6ed5972d65eafacd773b61d4ebd954fe2c-115015667883.png)

<div id="feed-integrations" />

## Интеграции фидов

В этом разделе описано, как подключить поток данных из AppsFlyer к mParticle.

Общая информация об интеграции AppsFlyer доступна по адресу [https://docs.mparticle.com/integrations/appsflyer/feed/](https://docs.mparticle.com/integrations/appsflyer/feed/).

1. На дэшборде mParticle (<Anchor target="_blank" href="https://app.mparticle.com">https://app.mparticle.com</Anchor>) выберите свое Приложение (также называется Workspace)

2. Выберите **Directory** в левом навигационном меню

3. Кликните плитку AppsFlyer, чтобы просмотреть сведения об интеграции, содержащие информацию об интеграции.

![Плитка AppsFlyer в mParticle Directory](https://files.readme.io/53ea474eeb94c551677dd7a4ce190d6ed5972d65eafacd773b61d4ebd954fe2c-115015667883.png)
![Сведения об интеграции AppsFlyer в mParticle](https://files.readme.io/afa886e48f2cddde39007275a72ce03c4a6c4182408bb2ad4c8c183b1591b47d-115015666683.png)

4. Нажмите **Add AppsFlyer to Setup**.

5. Выберите тип интеграции Input Feed Integration Type и кликните **Add to Setup**.

После этого откроется экран Setup, где вы сможете продолжить процесс настройки.

6. Введите настройки конфигурации AppsFlyer и кликните **Create**:

* Название конфигурации
* Действовать от имени приложения

![Настройки конфигурации фида AppsFlyer](https://files.readme.io/b27aff8223a98b0bf4bd73b6a7a04dc73bc245fa062ac9dd47ed6f4bbeece3f2-115015668703.png)

7. Завершите настройку в дэшборде AppsFlyer, используя предоставленные данные аутентификации.

![Настройка аутентификации в дэшборде AppsFlyer](https://files.readme.io/3c751a38c3891f73485375d75eacde3e07f86969a7d44cd33bf29ace6bfa1875-115015478566.png)

<div id="deferred-deep-linking" />

## Отложенная глубинная ссылка (диплинкинг)

AppsFlyer предоставляет вам доступ к данным атрибуции пользователей в реальном времени на уровне SDK. Это позволяет персонализировать лендинг (посадочную страницу), которую увидит пользователь, когда откроет приложение в первый раз после установки. Эту функцию обычно называют "отложенным" глубинным связыванием.

Подробнее об отложенном диплинкинге см. <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">здесь</Anchor>.

Данные конверсии AppsFlyer содержат параметр под названием `is_First_Launch`. The value of `is_First_Launch` равно 'true' только при первом запуске и 'false' при всех последующих запусках. Этот параметр можно использовать, чтобы при каждом запуске определять, нужно ли приложению выполнять отложенный диплинкинг для пользователя.

```
af_dp → $deeplink_path
```

> 📘 **Note**
>
> **Например**
>
> ```
> $deeplink_path=product/Banana-Pet-Costume/dd67268672b345e491656c871af8aa29
> ```
>
> `af_dp` включает закодированную схему URI и путь
>
> `af_dp` →
>
> `%20jet%3A%2F%2Fproduct%2FBanana-Pet-Costume%2Fdd67268672b345e491656c871af8aa29`

<Tabs>
<Tab title="Android;">

Для Android выполните это с помощью SharedPreferences: <Anchor target="_blank" href="https://developer.android.com/reference/android/content/SharedPreferences.html">здесь.</Anchor>

```java
AttributionListener myListener = new AttributionListener() {
  @Override
  public void onResult(@NonNull AttributionResult attributionResult) {
   if (attributionResult.getServiceProviderId() == MParticle.ServiceProviders.APPSFLYER) {
    JSONObject attributionParams = attributionResult.getParameters();
    if (attributionParams != null && attributionParams.has(AppsFlyerKit.INSTALL_CONVERSION_RESULT)) {
     Log.d("Conversion result", attributionParams.toString());
    } else if (attributionParams != null && attributionParams.has(AppsFlyerKit.APP_OPEN_ATTRIBUTION_RESULT)) {
     Log.d("App open result", attributionParams.toString());
    }
   }
  }

  @Override
  public void onError(@NonNull AttributionError attributionError) {
   Log.d("Attribution Data Error", attributionError.toString());
  }
 };

 MParticleOptions options = MParticleOptions.builder(this)
  .credentials("replaceWithAPIKey", "replace-withAPISecret")
  .attributionListener(myListener)
  .build();

 MParticle.start(options);
```

</Tab>

<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

Для iOS: выполните это в UserDefaults: <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/userdefaults">здесь</Anchor>

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
 MParticleOptions *options = [MParticleOptions optionsWithKey:@"<>" secret:@"<>"];
 options.onAttributionComplete = ^void (MPAttributionResult *_Nullable attributionResult, NSError * _Nullable error) {
  if (error) {
   NSLog(@"Attribution fetching for kitCode=%@ failed with error=%@", error.userInfo[mParticleKitInstanceKey], error);
   return;
  }
  NSLog(@"Attribution fetching for kitCode=%@ completed with linkInfo: %@", attributionResult.kitCode, attributionResult.linkInfo);
 }
 [[MParticle sharedInstance] startWithOptions:options];
 return YES;
}
```

</Tab>
</Tabs>

<div id="appsflyermparticle-use-cases" />

### Сценарии использования AppsFlyer/mParticle

| Кейс использования | Окно повторного вовлечения | Метод SDK AppsFlyer | Метод mParticle-AF Kit |
| --- | --- | --- | --- |
| Отложенный диплинкинг | https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png | onConversionDataSuccess | checkForDeferredDeepLinkWithCompletionHandler |
| Universal Links (универсальные ссылки) | https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png | continueUserActivity | continueUserActivity |
| Открытие приложения | https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png | onAppOpenAttribution | checkForDeferredDeepLinkWithCompletionHandler |
| Отложенный диплинкинг | Android; | onConversionDataSuccess | checkForDeepLink |
| Ссылки Android-приложения | Android; |  | continueUserActivity |
| Открытие приложения | Android; | onAppOpenAttribution | checkForDeepLink |

<div id="handling-user-flags" />

### Обработка пользовательских флагов

AppsFlyer также позволяет показывать персонализированный контент или направлять существующих пользователей в определенные разделы приложения ПОСЛЕ первого запуска. Когда существующие пользователи переходят в приложение по диплинкингу, приложение открывается с помощью метода `onOpenAttribution`, который возвращает данные URL-адреса источника.

```swift
 if let conversionData = params?[MPKitAppsFlyerConversionResultKey] as? [AnyHashable: Any], !alreadyLoggedAppsflyerConversionData {
   logAppsflyerConversionData(conversionData: conversionData)
   alreadyLoggedAppsflyerConversionData = true
   if let onelinkURL = (conversionData["af_dp"] as? String).flatMap(URL.init) {
    UIApplication.appDelegate._linkController.handle(onelinkURL, source: .appsflyer)
   }
  } else if let appOpenData = params?[MPKitAppsFlyerAppOpenResultKey] as? [AnyHashable: Any] {
   logAppsflyerAppOpenData(appOpenData: appOpenData as? [String: Any])
  }
```

AppsFlyer использует ***UserDefaults*** в iOS и ***Shared Preferences*** в Android, чтобы указать, открывает ли пользователь приложение впервые и его нужно перенаправить на соответствующую страницу, или приложение уже открывалось и пользователь уже был направлен на эту страницу. Для этого значение `alreadyLoggedAppsflyerConversionData` считывается из UserDefaults/ SharedPreferences и записывается туда, чтобы значение ***af\_dp*** не проверялось при первом запуске.

Подробнее о показе персонализированного контента при диплинкинге <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">читайте здесь</Anchor>.

<div id="enabling-appsflyer-uninstall-measurement-in-mparticle" />

## Включение измерения удалений AppsFlyer в mParticle

Измерение удалений AppsFlyer не включается автоматически в наборе SDK mParticle-AppsFlyer. Чтобы измерять удаления приложения, вызывайте методы AppsFlyer напрямую, следуя документации AppsFlyer по измерению удалений.

**Чтобы настроить измерение удалений для iOS или Android:**

* Вызывайте методы AppsFlyer напрямую, следуя нашей документации по измерению удалений

<div data-zendesk-anchors="event-integrations=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01H9HWJRM2612MBM2Y7C5YZ2YY=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 configure-the-appsflyer-event-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-appsflyer h_01H9HWJRM2BJATV1QHS382J0ZN=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-appsflyer feed-integrations=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%84%D0%B8%D0%B4%D0%BE%D0%B2 h_01H9HWJRM2YV3CEH7J7EMA8E3Y=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%84%D0%B8%D0%B4%D0%BE%D0%B2 deferred-deep-linking=%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D0%B0%D1%8F-%D0%B3%D0%BB%D1%83%D0%B1%D0%B8%D0%BD%D0%BD%D0%B0%D1%8F-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3 h_01H9HWJRM2SZYRXFTSZPM1JHCJ=%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D0%B0%D1%8F-%D0%B3%D0%BB%D1%83%D0%B1%D0%B8%D0%BD%D0%BD%D0%B0%D1%8F-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3 appsflyermparticle-use-cases=%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B8-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-appsflyermparticle h_01H9HWJRM2HCB4YF2BP9RPK2RP=%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B8-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-appsflyermparticle handling-user-flags=%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B0-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D1%85-%D1%84%D0%BB%D0%B0%D0%B3%D0%BE%D0%B2 h_01H9HWJRM3HAGGWHF4YTQTTS2X=%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B0-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D1%85-%D1%84%D0%BB%D0%B0%D0%B3%D0%BE%D0%B2 known-mparticle-integration-limitation=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9-appsflyer-%D0%B2-mparticle h_01H9HWJRM321PSNQ480R96BN12=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9-appsflyer-%D0%B2-mparticle" />

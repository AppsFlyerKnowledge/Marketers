---
title: Интеграция Oracle Responsys с AppsFlyer
metadata:
  keywords:
    - Oracle Responsys
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-11-20T09:26:13Z'
  edited_at: '2026-08-18T00:35:49Z'
  id: 360003798297
  locale: ru
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ru/articles/360003798297
---
> **At a glance:** Oracle Responsys, платформа доставки и аналитики электронной почты, встраивает OneLink AppsFlyer в электронные письма. Получатели электронных писем, перешедшие по ссылке, направляются по диплинку в ваше приложение.

![oracle-responsys-af-logo.png](https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png)

ESP (поставщики услуг электронной почты) могут быть отличными источниками сегментированного пользовательского трафика.

Одной из проблем, возникающих при работе с ESP, является корректные атрибуция и диплинкинг. ESP упаковывают URL-адрес диплинка, используя свои собственные домены регистрации кликов. Эта процедура часто нарушает функциональность универсальных ссылок iOS и Android App Links.

Однако диплинкинг и регистрация кликов все еще возможны с ESP, поддерживающими универсальные ссылки и App Links в дополнение к домену регистрации кликов. Кроме того, можно настроить собственный домен для регистрации кликов.

<div id="prerequisites" />

## Необходимые условия

* Настройте приложение на поддержку <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">диплинкинга с помощью OneLink</Anchor>.
* Проверьте версию SDK (как для Android, так и для iOS)

<Tabs>
<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

* AppsFlyer SDK для iOS версии 4.9.0 (или выше)

</Tab>

<Tab title="Android;">

* AppsFlyer SDK для Android версии 4.9.0 (или выше)

</Tab>
</Tabs>

<div id="setting-up-oracle-responsys-click-domain" />

## Настройка домена регистрации кликов Oracle Responsys

Следуйте указаниям в этом разделе, чтобы настроить домен кликов (домен регистрации кликов) в Oracle Responsys.

<div id="step-1-set-up-a-click-domain-in-oracle-responsys" />

### Шаг 1: Настройка домена кликов в Oracle Responsys

Для настройки домена кликов следуйте официальному руководству Oracle Responsys по <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCEA/LinkTable_Main.htm?cshid=LinkTable_Main">созданию доменов кликов</Anchor>. Oracle Responsys использует таблицы ссылок для регистрации кликов для конкретной кампании.

iOSAndroid

![Oracle-responsys-link-tracking-table.png](https://files.readme.io/c151c58af73cf460ba4275a9159e45c15807f311fa8d8b4b1531b0cdf7e3bc4e-49839256667665.png)

После настройки доменов кликов в таблице ссылок компания Responsys использует эти домены для упаковывания OneLinks, которые вы включаете в рассылки. Таким образом, Responsys может регистрировать клики в своей системе, сохраняя при этом функциональность OneLink и диплинкинга.

<div id="step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android" />

### Шаг 2. Предоставьте Responsys файл AASA (iOS) и файл Asset Links (Android)

<div id="aasa-for-ios" />

<Accordion title="AASA для iOS">

Чтобы Responsys поддерживал универсальные ссылки iOS, ему необходим файл AASA. Ознакомьтесь со следующими инструкциями.

Когда вы устанавливаете OneLink с помощью универсальных ссылок, у вас уже есть файл AASA, связанный с OneLink. Для получения AASA:

1. Перейдите в раздел настройки OneLink и найдите ссылку OneLink, настроенную на работу с универсальными ссылками.
2. Добавьте **/.well-known/apple-app-site-association** в конец URL OneLink.
3. Вставьте OneLink в адресную строку браузера и нажмите клавишу ввода. Например: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**. После этого файл AASA будет загружен на ваш компьютер. Открыть его можно с помощью любого простого текстового редактора.
4. Отправьте этот файл AASA в Responsys. Более подробная информация и сведения о содержимом этого файла приведены на стр. 11 <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/pdf/ios-universal-links-dev-guide.pdf">руководства Oracle</Anchor>.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Asset Links для Android">

Когда вы настраиваете OneLink с помощью App Links, у вас уже есть файл Asset Links, связанный с OneLink. Для получения файла Asset Links. Для получения файла Asset Links:

1. Перейдите в раздел настройки OneLink и найдите ссылку OneLink, настроенную на работу с App Links.
2. Добавьте **/.well-known/assetlinks.json** в конец URL-адреса OneLink.
3. Вставьте OneLink в адресную строку браузера и нажмите клавишу ввода. Например:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. После этого файл Asset Links будет загружен на ваш компьютер. Открыть его можно с помощью любого простого текстового редактора.
4. Отправьте этот файл Asset Links в Responsys. Для получения дополнительной информации и ознакомления с содержимым этого файла см. <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/android/app-links/">данное руководство</Anchor>.

</Accordion>

<div id="setting-up-your-app" />

## Настройка приложения

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Шаг 1 для Android: Настройка приложения для поддержки App Links">

<div id="adding-the-click-domain-to-the-activity-in-the-android-manifest" />

#### Добавление домена кликов к активности в манифесте Android

В манифесте Android добавьте хост домена кликов и любой префикс в тег activity для активности, на которую должен вести диплинк.

```html Markup
<activity android:name=".DeepLinkActivity">
    <intent-filter  android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" />
           <category android:name="android.intent.category.BROWSABLE" />
           <data android:scheme="https"
               android:host="click.example.com"
               android:pathPrefix="/campaign" />
     </intent-filter>
</activity>
```

<div id="setting-up-the-app-to-resolve-click-domains" />

#### Настройка приложения для разрешения доменов кликов

SDK необходимо разрешить ссылку OneLink в рамках домена кликов, чтобы получить информацию о кампании. Данные возвращаются в методе `onAppOpenAttribution`.

Для разрешения доменов кликов:

1. Убедитесь, что версия SDK не ниже 4.9.0.
2. Перечислите домены кликов в API SDK `setResolveDeepLinkURLs`. Этот API необходимо вызывать до инициализации SDK. Более подробная информация приведена в документации по SDK <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">здесь</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

   * **Важно!** Если вы используете Movable Ink (MI) совместно с Oracle, то вам необходимо получить от менеджера MI CNAME и внутренние домены и добавить их в `setResolveDeepLinkURLs`, в дополнение к ссылке клика для Oracle. Например:

     ```java
     AppsFlyerLib.getInstance().setResolveDeepLinkURLs("oracle-click.example.com", "mi.example.com", "example.micpn.com");
     ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Шаг 1 для iOS: Настройка приложения для поддержки универсальных ссылок">

В этом разделе рассматривается настройка приложения для поддержки универсальных ссылок.

<div id="associating-click-domains-in-xcode" />

#### Ассоциирование доменов кликов в Xcode

1. Нажмите на свой проект в Xcode.
2. Нажмите ***Capabilities*** (Возможности). ![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Включите параметр ***Associated Domain*** (Связанный домен).
4. Нажмите на знак + и добавьте свой домен. Например, applinks:click.example.com.

</Accordion>

<div id="step-2-setting-up-the-app-to-resolve-click-domains" />

### Шаг 2: Настройка приложения для разрешения доменов кликов

SDK необходимо разрешить ссылку OneLink в рамках домена кликов, чтобы получить информацию о кампании. Данные возвращаются в методе `onAppOpenAttribution`.

Для разрешения доменов кликов:

1. Убедитесь, что версия SDK не ниже 4.9.0.
2. Перечислите домены кликов в свойстве SDK `resolveDeepLinkURLs`. Это свойство должно быть установлено перед инициализацией SDK. Более подробная информация приведена в документации по SDK <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">здесь</Anchor>.  

   <Tabs>
   <Tab title="Objective C">

   ```objectivec
   [AppsFlyerTracker sharedTracker].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerTracker.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

   * **Важно!** Если вы используете Movable Ink (MI) совместно с Oracle, то вам необходимо получить от менеджера MI CNAME и внутренние домены и добавить их в `setResolveDeepLinkURLs`, в дополнение к ссылке клика для Oracle. Пример доменов:
     * Домен Oracle: oracle-click.example.com
     * Домен MI CNAME: mi.example.com
     * Внутренний домен MI: example.micpn.com
3. Добавьте следующий код, чтобы SDK мог разрешить домен регистрации кликов:  

   <Tabs>
   <Tab title="Objective C">

   Добавьте этот код в AppDelegate.m

   ```objectivec
   - (NSDictionary *)allHTTPHeaderFieldsForResolveDeepLinkURL:(NSURL *)URL {
       if ([URL.host  isEqual: @"click.example.com"]) {
           return [NSDictionary dictionary];
       }
       else {
           return nil;
       }
   }
   ```

   </Tab>

   <Tab title="Swift">

   Добавьте этот код в AppDelegate.swift

   ```swift
   func allHTTPHeaderFields(forResolveDeepLinkURL URL: URL!) -> [String : String]! -> [String : String]! {
       if (URL.host == "click.example.com") {
           /// Измените User-Agent
           return [:]
       } else {
           return nil;
       }
   }
   ```

   </Tab>
   </Tabs>

<div id="sending-your-first-email" />

## Отправка первого письма

1. Создайте URL OneLink на странице управления ссылками (или вручную).
2. При создании URL OneLink убедитесь, что в URL все значения параметров закодированы.
3. Настоятельно рекомендуется использовать следующие параметры:
   * pid (media source) — используйте медиа-источник, который означает данное использование, например, Email.
   * c (campaign) — название кампании, которую вы хотите измерить.
   * af\_dp — схема URI диплинка, куда вы хотите перенаправлять своих пользователей.
   * af\_web\_dp — куда перенаправлять пользователей, перешедших по ссылке на компьютере.
   * af\_ios\_url — куда перенаправлять пользователей, не имеющих приложения, перешедших по ссылке на устройстве iOS.
   * af\_android\_url — куда перенаправлять пользователей, не имеющих приложения, при переходе по ссылке на устройстве Android.
4. Поместите URL-адрес OneLink в электронное письмо, созданное в Responsys. Пример:

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Скачайте это суперское приложение!</a>
   ```

   На этом этапе Responsys упаковывает приведенную выше ссылку с помощью домена кликов, который вы задали на предыдущих шагах. Любой клик по домену кликов перенаправляет на ссылку атрибуции OneLink. Если приложение установлено на устройство пользователя, то домен кликов перенаправляет по диплинку в приложение.

> 📘 **Note**
>
> **Например**
>
> В этом примере параметры URL не закодированы просто для удобства чтения:
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

<div id="testing-your-links" />

### Тестирование ссылок

После выполнения всех описанных выше действий, создания соответствующего URL OneLink и размещения его в электронном письме отправьте себе тестовое письмо.

Чего следует ожидать?

Если приложение установлено, оно должно быть вызвано. Если реализованы соответствующие API для диплинкинга AppsFlyer SDK, то вы должны перейти по диплинку на соответствующий контент.  
Кроме того, клик должен появиться как на дэшборде AppsFlyer, атрибутированный к указанному медиа-источнику и кампании, так и в данных Responsys.

<div data-zendesk-anchors="prerequisites=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01HDNSK7GR33AN2M4GP956S1FD=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F setting-up-oracle-responsys-click-domain=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D1%80%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-oracle-responsys h_01HDNSK7GR84QSRTS86GH556WK=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D1%80%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-oracle-responsys step-1-set-up-a-click-domain-in-oracle-responsys=%D1%88%D0%B0%D0%B3-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%B2-oracle-responsys h_01HDNSK7GRHYJZSMYCMT9RVEBW=%D1%88%D0%B0%D0%B3-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%B2-oracle-responsys step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android=%D1%88%D0%B0%D0%B3-2-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%8C%D1%82%D0%B5-responsys-%D1%84%D0%B0%D0%B9%D0%BB-aasa-ios-%D0%B8-%D1%84%D0%B0%D0%B9%D0%BB-asset-links-android h_01HDNSK7GRW57NNXMN1SWFTTFZ=%D1%88%D0%B0%D0%B3-2-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%8C%D1%82%D0%B5-responsys-%D1%84%D0%B0%D0%B9%D0%BB-aasa-ios-%D0%B8-%D1%84%D0%B0%D0%B9%D0%BB-asset-links-android h_01HDNSK7GR77N60SFVBD57S9GQ=aasa-for-ios h_01HDNSK7GR6ADJCPG63ZVP19NJ=asset-links-for-android setting-up-your-app=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HDNSK7GRN751HAPPQ3HVRMDG=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HDNSK7GRHCK378A8XKMK7ZZF=step-1-for-android-setting-up-your-app-to-support-app-links adding-the-click-domain-to-the-activity-in-the-android-manifest=%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%BA-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B2-%D0%BC%D0%B0%D0%BD%D0%B8%D1%84%D0%B5%D1%81%D1%82%D0%B5-android h_01HDNSK7GRQNQGWXAEGHSTHADH=%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%BA-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B2-%D0%BC%D0%B0%D0%BD%D0%B8%D1%84%D0%B5%D1%81%D1%82%D0%B5-android setting-up-the-app-to-resolve-click-domains=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2 h_01HDNSK7GRP9ND0MHC3ZHD7G8H=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2 h_01HDNSK7GRJ682QYAMPB4PSGRZ=step-1-for-ios-setting-up-your-app-to-support-universal-links associating-click-domains-in-xcode=%D0%B0%D1%81%D1%81%D0%BE%D1%86%D0%B8%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%B2-xcode h_01HDNSK7GSRENM232MQ25EB3J3=%D0%B0%D1%81%D1%81%D0%BE%D1%86%D0%B8%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%B2-xcode step-2-setting-up-the-app-to-resolve-click-domains=%D1%88%D0%B0%D0%B3-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2 h_01HDNSK7GSP08G2EQSNVR5G45B=%D1%88%D0%B0%D0%B3-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2 sending-your-first-email=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%BF%D0%B5%D1%80%D0%B2%D0%BE%D0%B3%D0%BE-%D0%BF%D0%B8%D1%81%D1%8C%D0%BC%D0%B0 h_01HDNSK7GSA9VAMTRFCX8SZGSC=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%BF%D0%B5%D1%80%D0%B2%D0%BE%D0%B3%D0%BE-%D0%BF%D0%B8%D1%81%D1%8C%D0%BC%D0%B0 testing-your-links=%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA h_01HDNSK7GSTAJXAP6KGKE9TD8T=%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA" />

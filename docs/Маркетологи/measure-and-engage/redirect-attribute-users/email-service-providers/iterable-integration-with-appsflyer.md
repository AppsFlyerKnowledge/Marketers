---
title: Интеграция Iterable с AppsFlyer
metadata:
  keywords:
    - OneLink
    - Advertisers
    - ESP
    - Developers
    - Iterable
    - Deep Likning
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-09-16T13:14:19Z'
  edited_at: '2026-08-18T00:35:44Z'
  id: 360002522337
  locale: ru
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ru/articles/360002522337
---
> **At a glance:** Интегрируйте ссылки атрибуции на основе OneLink с системой Iterable для <Anchor target="_blank" href="/marketers/ru/docs/email-service-provider-esp-integration-guide">перенаправления по диплинкам из электронных писем.</Anchor> В интеграции используется поддержка Iterable универсальных ссылок в дополнение к фирменным доменам регистрации кликов.

![iterable-af-logo.png](https://files.readme.io/e339ea75a54e53711f3c577c7f82339151af13e6c086cc1435cbb57cf1fae3f0-49839295443089.png)

<div id="introduction" />

## Введение

ESP (поставщики услуг электронной почты) могут быть отличными источниками сегментированного пользовательского трафика.

Одна из проблем ESP — запись кликов при сохранении функциональности диплинков. ESP упаковывают URL-адрес диплинка, используя свои собственные домены регистрации кликов. Эта процедура иногда прерывает процесс универсальных ссылок iOS.

Iterable поддерживает универсальные ссылки в дополнение к доменам записи кликов, и с помощью этого решения можно по-прежнему выполнять перенаправление по диплинкам и запись кликов.

<div id="prerequisites" />

## Необходимые условия

<Tabs>
<Tab title="https://files.readme.io/e339ea75a54e53711f3c577c7f82339151af13e6c086cc1435cbb57cf1fae3f0-49839295443089.png">

* SDK AppsFlyer для iOS версии 4.9.0

</Tab>

<Tab title="Android;">

* SDK AppsFlyer для Android версии 4.9.0

Iterable не поддерживает Android App Links. Однако <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">диплинкинг по схеме URI по-прежнему поддерживается</Anchor>. На стороне Iterable не требуется никаких специальных действий для поддержки диплинкинга в Android.

</Tab>
</Tabs>

<div id="setting-up-iterable" />

## Настройка Iterable

<div id="step-1-setting-up-link-branding-in-iterable" />

### Шаг 1: Настройка брендинга ссылок в Iterable

Создайте специальный домен для записи кликов и задайте субдомен (например,  [click.example.com](http://click.example.com)). Это можно сделать, купив выделенный домен или используя свой собственный домен.

Дополнительные сведения о настройке домена записи кликов с помощью Iterable см. <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/115002651226-Setting-up-mail-domains">здесь</Anchor>.

<div id="step-2-uploading-your-ssl-certificate-to-iterable" />

### Шаг 2: Загрузка SSL-сертификата в Iterable

Ваш домен регистрации кликов должен содержать сертификат SSL вашего домена. Сертификат SSL должен быть установлен в вашем аккаунте Iterable. Инструкции по установке сертификатов SSL можно найти <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/115000427446-How-to-Set-up-HTTPS-for-Links-for-Click-Tracking">здесь</Anchor>.

<div id="step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android" />

### Шаг 2: Предоставьте Iterable файл AASA (iOS) и ссылки на ресурсы (Android)

<div id="aasa-for-ios" />

<Accordion title="AASA для iOS">

Чтобы Iterable поддерживал универсальные ссылки iOS, ему необходим файл AASA. Ознакомьтесь со следующими инструкциями.

Когда вы устанавливаете OneLink с помощью универсальных ссылок, у вас уже есть файл AASA, связанный с OneLink. Для получения AASA:

1. Перейдите к ***шаблонам OneLink*** и найдите OneLink, в котором настроены универсальные ссылки.
2. Добавьте **/.well-known/apple-app-site-association** в конец URL OneLink.
3. Вставьте OneLink в адресную строку браузера и нажмите клавишу ввода. Например: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**. После этого файл AASA будет загружен на ваш компьютер. Открыть его можно с помощью любого простого текстового редактора.
4. Определите правила перезаписи ссылок. Подробные сведения см. <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511">здесь</Anchor>.
5. Отправьте этот файл AASA в Iterable. Для получения дополнительной информации и ознакомления с содержимым этого файла см. <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511-iOS-Universal-Lin">данное руководство</Anchor>.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Asset Links для Android">

Когда вы настраиваете OneLink с помощью App Links, у вас уже есть файл Asset Links, связанный с OneLink. Для получения файла Asset Links:

1. Перейдите к ***шаблонам OneLink*** и найдите OneLink, в котором настроены App Links.
2. Добавьте **/.well-known/assetlinks.json** в конец URL-адреса OneLink.
3. Вставьте OneLink в адресную строку браузера и нажмите Enter. Например:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. После этого файл Asset Links будет загружен на ваш компьютер. Открыть его можно с помощью любого простого текстового редактора.
4. Отправьте этот файл Asset Links в Iterable. Для получения дополнительной информации и ознакомления с содержимым этого файла см. <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035127392">данное руководство</Anchor>.

</Accordion>

<div id="setting-up-your-app" />

## Настройка приложения

Чтобы настроить приложения для поддержки App Links и универсальных ссылок iOS, см. следующее.

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Шаг 1 для Android: Настройка приложения для поддержки App Links">

<div id="step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest" />

#### Шаг 1: Добавление домена кликов к активности в манифесте Android

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

<div id="step-2-setting-up-the-app-to-resolve-click-domains" />

#### Шаг 2: Настройка приложения для разрешения доменов кликов

SDK необходимо разрешить ссылку OneLink в рамках домена кликов, чтобы получить информацию о кампании. Сведения возвращаются в методе `onAppOpenAttribution`.

Для разрешения доменов кликов:

1. Убедитесь, что версия SDK не ниже 4.9.0.
2. Перечислите домены кликов в API SDK `setResolveDeepLinkURLs`. Этот API необходимо вызывать до инициализации SDK. Дополнительные сведения см. в документации по SDK <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">здесь</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Шаг 1 для iOS: Настройка приложения для поддержки универсальных ссылок">

В этом разделе рассматривается настройка приложения для поддержки универсальных ссылок.

<div id="step-1-associating-click-domains-in-xcode" />

#### Шаг 1: Ассоциирование доменов кликов в Xcode

1. Нажмите на свой проект в Xcode.
2. Нажмите ***Capabilities***. ![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Включите параметр ***Associated Domain*** (Связанный домен).
4. Нажмите на знак + и добавьте свой домен. Например, applinks:click.example.com.

</Accordion>

См. следующее, чтобы настроить SDK для разрешения диплинков.

<div id="step-2-for-android-resolve-deep-links" />

<Accordion title="Шаг 2 для Android: разрешение диплинков">

SDK необходимо разрешить ссылку OneLink в рамках домена кликов, чтобы получить информацию о кампании. Сведения возвращаются в методе `onAppOpenAttribution`.

Для разрешения доменов кликов:

1. Убедитесь, что версия SDK не ниже 4.9.0.
2. Перечислите домены кликов в свойстве SDK `resolveDeepLinkURLs`. Это свойство должно быть установлено перед инициализацией SDK. Дополнительные сведения см. в документации по SDK <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">здесь</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("clickdomain.com", "myclickdomain.com", "anotherclickdomain.com");
   ```

</Accordion>

<div id="step-2-for-ios-resolve-deep-links" />

<Accordion title="Шаг 2 для iOS: разрешение диплинков">

SDK необходимо разрешить ссылку OneLink в рамках домена кликов, чтобы получить информацию о кампании. Сведения возвращаются в методе `onAppOpenAttribution`.

Для разрешения доменов кликов:

1. Убедитесь, что версия SDK не ниже 4.9.0.
2. Перечислите домены кликов в свойстве SDK `resolveDeepLinkURLs`. Это свойство должно быть установлено перед инициализацией SDK. Дополнительные сведения см. в документации по SDK <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">здесь</Anchor>.  

   <Tabs>
   <Tab title="Objective C">

   ```objectivec
   [AppsFlyerLib shared].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

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
           /// Изменить User-Agent
           return [:]
       } else {
           return nil;
       }
   }
   ```

   </Tab>
   </Tabs>

</Accordion>

<div id="sending-your-first-email" />

## Отправка первого письма

1. Создайте URL-адрес OneLink на странице управления ссылками (или вручную).
2. При создании URL OneLink убедитесь, что в URL все значения параметров закодированы.
3. Настоятельно рекомендуется использовать следующие параметры:
   * pid (медиа-источник) — используйте медиа-источник, который означает данное использование, например, Email.
   * c (кампания) — название кампании, которую вы хотите измерить.
   * af\_dp — схема URI диплинка, куда вы хотите перенаправлять своих пользователей.
   * af\_web\_dp — куда перенаправлять пользователей, переходящих по ссылке на компьютере.
   * af\_ios\_url — куда перенаправлять пользователей, у которых нет приложения, перешедших по ссылке на устройстве iOS.
   * af\_android\_url — куда перенаправлять пользователей, у которых нет приложения, по ссылке на устройстве Android.
4. Поместите URL-адрес OneLink в электронное письмо, созданное в Iterable. Пример:

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Скачайте это суперское приложение!</a>
   ```

   На этом этапе Iterable упаковывает приведенную выше ссылку с помощью домена кликов, который вы задали на предыдущих шагах. Любой клик по домену кликов перенаправляет на ссылку атрибуции OneLink. Если приложение установлено на устройство пользователя, то домен кликов перенаправляет по диплинку в приложение.

> 📘 **Note**
>
> **Пример**
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

Если приложение установлено, оно должно быть вызвано. Если реализованы соответствующие API для диплинкинга в AppsFlyer SDK, то вы должны перейти по диплинку на соответствующий контент.  
Кроме того, клик должен появиться как на дэшборде AppsFlyer, атрибутированный к указанному медиа-источнику и кампании, так и в данных Iterable.

<div data-zendesk-anchors="introduction=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01HV6PJQRMT8037JMVMMXDPWGN=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 prerequisites=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01HV6PJQRM5N1K6CY0NSSFXT3X=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F setting-up-iterable=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-iterable h_01HV6PJQRMX18FRB3NMZH6NCH0=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-iterable step-1-setting-up-link-branding-in-iterable=%D1%88%D0%B0%D0%B3-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D0%BD%D0%B3%D0%B0-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B2-iterable h_01HV6PJQRMMYV3A5ZSEGTT7993=%D1%88%D0%B0%D0%B3-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D0%BD%D0%B3%D0%B0-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B2-iterable step-2-uploading-your-ssl-certificate-to-iterable=%D1%88%D0%B0%D0%B3-2-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-ssl-%D1%81%D0%B5%D1%80%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%B0-%D0%B2-iterable h_01HV6PJQRMYDDWK9AKGN258TTM=%D1%88%D0%B0%D0%B3-2-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-ssl-%D1%81%D0%B5%D1%80%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%B0-%D0%B2-iterable step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android=%D1%88%D0%B0%D0%B3-2-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%8C%D1%82%D0%B5-iterable-%D1%84%D0%B0%D0%B9%D0%BB-aasa-ios-%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%BD%D0%B0-%D1%80%D0%B5%D1%81%D1%83%D1%80%D1%81%D1%8B-android h_01HV6PJQRMFJ23627KS83D4C6A=%D1%88%D0%B0%D0%B3-2-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%8C%D1%82%D0%B5-iterable-%D1%84%D0%B0%D0%B9%D0%BB-aasa-ios-%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%BD%D0%B0-%D1%80%D0%B5%D1%81%D1%83%D1%80%D1%81%D1%8B-android h_01HV6PJQRMNSYK8N7QEE00KSPE=aasa-for-ios h_01HV6PJQRMSMZCVJ5XRXZ3SWEH=asset-links-for-android setting-up-your-app=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HV6PJQRMJHDF94JSAT8N8SP9=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HV6PJQRM5S772CTH219MGY44=step-1-for-android-setting-up-your-app-to-support-app-links step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest=%D1%88%D0%B0%D0%B3-1-%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%BA-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B2-%D0%BC%D0%B0%D0%BD%D0%B8%D1%84%D0%B5%D1%81%D1%82%D0%B5-android h_01HV6PJQRM2V31JAJ52Q3FHQWH=%D1%88%D0%B0%D0%B3-1-%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%BA-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B2-%D0%BC%D0%B0%D0%BD%D0%B8%D1%84%D0%B5%D1%81%D1%82%D0%B5-android step-2%20setting-up-the-app-to-resolve-click-domains=%D1%88%D0%B0%D0%B3-2%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2 h_01HV6PJQRMCRFM90QSP5SS72SE=%D1%88%D0%B0%D0%B3-2%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2 h_01HV6PJQRMVJB6J6GV41DCYAVQ=step-1-for-ios-setting-up-your-app-to-support-universal-links step-1-associating-click-domains-in-xcode=%D1%88%D0%B0%D0%B3-1-%D0%B0%D1%81%D1%81%D0%BE%D1%86%D0%B8%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%B2-xcode h_01HV6PJQRNRW8Y97JWHP0MSXZF=%D1%88%D0%B0%D0%B3-1-%D0%B0%D1%81%D1%81%D0%BE%D1%86%D0%B8%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%B2-xcode h_01HV6PJQRNHFH8XGMCEWVGSPA5=step-2-for-android-resolve-deep-links h_01HV6PJQRN4NYPWS2XQQSJAM5R=step-2-for-ios-resolve-deep-links sending-your-first-email=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%BF%D0%B5%D1%80%D0%B2%D0%BE%D0%B3%D0%BE-%D0%BF%D0%B8%D1%81%D1%8C%D0%BC%D0%B0 h_01HV6PJQRN2H29D8HKXHBYE1NB=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%BF%D0%B5%D1%80%D0%B2%D0%BE%D0%B3%D0%BE-%D0%BF%D0%B8%D1%81%D1%8C%D0%BC%D0%B0 testing-your-links=%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA h_01HV6PJQRNET2J17ZGGZE0K0Q6=%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA" />

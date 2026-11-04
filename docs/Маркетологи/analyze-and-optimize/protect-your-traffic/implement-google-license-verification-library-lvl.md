---
title: Настройка библиотеки проверки лицензий Google (LVL)
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2023-07-27T14:45:46Z'
  edited_at: '2026-08-18T00:08:07Z'
  id: 17329535522961
  locale: ru
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ru/articles/17329535522961
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор.** Защитите свои приложения от несанкционированного использования, добавив библиотеку проверки лицензий Google (LVL) для обработки всех связанных с лицензиями взаимодействий с Google Play.

<div id="overview" />

## Обзор

Библиотека проверки лицензий (LVL) — это библиотека, которую вы можете добавить в свои приложения (загружаемая из Android SDK) и которая обрабатывает все связанные с лицензированием взаимодействия со службой лицензирования Google Play.

Это добавляет еще один уровень защиты поверх алгоритмов Protect360, позволяя убедиться, что установки поступают от реальных пользователей Google Play. Таким образом уменьшаются расхождения между количеством установок, отображаемых в Google Play и на дэшборде AppsFlyer.

* LVL доступен только клиентам Protect360. Без пакета P360 модуль не проверяет лицензии.
* LVL предотвращает потерю дохода из-за несанкционированного использования приложения, обеспечивая соблюдение правовых норм и защищая ваши инвестиции.

Служба лицензирования Google Play определяет, имеет ли пользователь лицензию на использование приложения или нет. Google Play считает пользователей лицензированными, если они являются зарегистрированными покупателями приложения. Лицензия уникальна для каждого приложения и может быть использована для усиления защиты. <Anchor target="_blank" href="https://developer.android.com/google/play/licensing">Узнать больше</Anchor>

SDK AppsFlyer собирает данные с клиентской стороны, а Protect360 выполняет проверку лицензий на стороне сервера, блокируя мошеннические установки, не прошедшие проверку, как органические, так неорганические. Причина блокировки, которую вы увидите на дэшборде Protect360 и в отчетах, будет «Боты».

<div id="set-up-lvl" />

## Настройка LVL

<div id="add-lvl" />

<Accordion title="Процесс установки">

В настоящее время это ручной процесс, в ходе которого вам нужно будет передать приведенную ниже информацию своему менеджеру AppsFlyer, чтобы он добавил ее вручную.

**Чтобы добавить LVL:**

1. Определите свойство в файле gradle.properties с именем:

   ```http
   appsflyerSdkVersion = "YOUR_SDK_VERSION" // e.g., 6.15.2
   ```
2. Динамически укажите это свойство в файле build.gradle:

   ```http
   dependencies {
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```
3. Для пользователей Kotlin DSL:

   ```http
   dependencies {
       val appsflyerSdkVersion = "<YOUR_SDK_VERSION>" // e.g., 6.15.2
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```

   <div id="note" />

   > 📘 **Примечание**
   >
   > Вы можете определить локальную переменную в разделе dependencies. Это позволит синхронизировать версии LVL и AppsFlyer SDK, чтобы оба модуля использовали одинаковые версии.

4. Получите лицензию на приложение и биллинг в приложении:  
   В консоли разработчика Google Play (Выберите приложение -> Инструменты разработчика -> Сервисы и API).

   ```http
   Открытый ключ RSA в кодировке Base64
   ```
5. Пожалуйста, предоставьте вашему менеджеру следующую информацию:

* открытый ключ
* app-id
* минимальная версия приложения, в которую интегрирован LVL
* Снимок экрана с реализацией LVL (Liveness Verification Library)

</Accordion>

<div id="test-and-troubleshoot" />

<Accordion title="Следующие шаги">

Как только мы получим ваш запрос, команда Protect360 настроит проверку LVL в режиме STAGING. На данном этапе система будет сообщать о результатах проверки LVL только внутри AppsFlyer. Через несколько дней мы проверим наши данные.

**Если все выглядит хорошо:**

* Мы переведем проверку LVL в режим PRODUCTION, и она начнет блокировать трафик.
* Команда Protect360 уведомит об этом менеджера.

**Если что-то не так** (например, если мы не видим информацию о LVL в событиях установки):

* Мы оставим проверку LVL в режиме STAGING.
* Ваш менеджер уведомит вас об этом и поможет устранить неполадки в приложении.

</Accordion>

<div id="setup-process" />

<Accordion title="Тестирование и устранение неисправностей">

При отладке приложения вы должны видеть информацию о LVL в полезной нагрузке, отправляемой в AppsFlyer, как показано в примере ниже:

```json
"lvl":{
      "ttr":,<ttr>,
      "signature":"<signature>",
      "signedData":"<signedData>"
   }
```

Поработайте с командой поддержки/SDK в случае отсутствия информации о LVL в сообщении об установке.

</Accordion>

<div id="faq" />

## Вопросы и ответы

<div id="what-if-an-app-is-installed-from-a-store-other-than-google-play" />

<Accordion title="Что делать, если приложение установлено не из Google Play, а из другого магазина?">

Валидация LVL не проверяет и не блокирует установки из других магазинов, кроме Google Play.

</Accordion>

<div id="how-much-time-does-it-take-to-get-lvl-set-up" />

<Accordion title="Сколько времени требуется для установки LVL?">

После получения информации нам потребуется несколько рабочих дней, чтобы настроить LVL и проверить данные. Подробнее о [процессе настройки](/docs/implement-google-license-verification-library-lvl#setup-process).

</Accordion>

<div id="does-lvl-affect-app-functionality" />

<Accordion title="Влияет ли LVL на функциональность приложения?">

Нет, на функциональность приложения это не влияет.

</Accordion>

<div id="what-is-the-difference-between-lvl-and-gpreferrer" />

<Accordion title="В чем разница между LVL и GP-реферером?">

Проверка лицензии с помощью LVL отличается от алгоритмов проверки GP-реферера тем, что LVL проверяет лицензию самого приложения (лицензия на приложение), а GP-реферер используется для получения источника, откуда пользователь перенаправлен для установки в магазин Google Play, с URL-адресом реферера для установленного пакета (временные метки того, когда произошел клик по рефереру, когда началась установка, версия приложения и т. д.). Короче говоря, если LVL используется для проверки того, что пользователь имеет лицензию на использование приложения, то GP-реферер используется для проверки того, что данные установки не были подделаны.

</Accordion>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 01H7YJ35YKDHJ2MDZSSYKMDCJ4=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 set-up-lvl=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-lvl 01H7YJ35YKDW0CB9TWRBKFBCDJ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-lvl 01H7YJ35YK585NA5F4HZN8C74K=add-lvl 01JGK7NK10ZDD6CM6Y4631FB4Q=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 01H7YJ35YKX1CVYMRZ1W8NRH7Y=test-and-troubleshoot 01H7YJ35YKMCN2E2BDWA5DD5M3=setup-process faq=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B 01H7YJ35YMR8PBTTSHD77WZ4AE=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B 01H7YJ35YMRZ8KRSVND1JT6JGH=what-if-an-app-is-installed-from-a-store-other-than-google-play 01H7YJ35YM11J0EG0B8PBMSPAC=how-much-time-does-it-take-to-get-lvl-set-up 01H7YJ35YMH0NM73Y1R90JDMEA=does-lvl-affect-app-functionality 01H7YJ35YM6RHCA6QP3MK0Y9J0=what-is-the-difference-between-lvl-and-gpreferrer" />

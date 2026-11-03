---
title: Переход с версии 3.3.X на версию 4.3.2 и выше
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2016-02-03T10:37:42Z'
  edited_at: '2026-08-19T00:14:52Z'
  id: 207606796
  locale: ru
  section: Previous SDK versions
  section_id: 6551300280977
  url: https://support.appsflyer.com/hc/ru/articles/207606796
---
> **Кратко:** что нужно учесть при переходе между версиями Android SDK AppsFlyer.

В интеграцию Android SDK были внесены значительные изменения.

Основные изменения:

* Теперь SDK является синглтоном, то есть все вызовы API должны выполняться следующим образом:

```java
AppsFlyerLib.getInstance().setCustomerUserId("myId");
```

* **SetAppsFlyerKey()** — этот метод был удален; в результате мы ожидаем получить dev key с помощью нового метода инициализации: AppsFlyerLib.getInstance().startTracking(this,"YOUR\_APPSFLYER\_DEV\_KEY")
* **sendTracking()**, **onActivityPause()**, **onActivityResume()** были удалены. SDK автоматически определяет запуски
* **Deep Link** — для активностей с поддержкой диплинкинга разработчик должен вызвать:

```java
AppsFlyerLib.getInstance().sendDeepLinkData(this) в onCreate()
```

отображаемой активности.

Это требуется только в том случае, если приложение не работает в фоновом режиме.

* **Logging** — значение флага логирования по умолчанию изменено на false. Кроме того, если флаг отключен, логи не выводятся (исправление ошибки). Чтобы включить флаг логирования, разработчик должен вызвать:

AppsFlyerLib.getInstance().setDebugLog(true);

Чтобы посмотреть руководство по интеграции AppsFlyer SDK для Android, нажмите <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">здесь</Anchor>.

**Переход на 4.4.0 и выше**

Android SDK AppsFlyer v4.4.0 **больше не поддерживает следующий receiver** в манифесте:

```html Markup
<receiver android:name="com.appsflyer.AppsFlyerLib">
  <intent-filter>
    <action android:name="android.intent.action.PACKAGE_REMOVED"/>
    <data android:scheme="package"/>
  </intent-filter> 
</receiver>
```

Если вы используете версию 4.4.0+, **удалите этот receiver из файла манифеста**.

Единственный **обязательный** receiver для SDK выглядит следующим образом:

```html Markup
<receiver
  android:name="com.appsflyer.MultipleInstallBroadcastReceiver"
  android:exported="true">
    <intent-filter>
      <action android:name="com.android.vending.INSTALL_REFERRER" />
    </intent-filter>
</receiver>
```
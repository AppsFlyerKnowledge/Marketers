---
title: Использование AppsFlyer с TWA
metadata:
  keywords:
    - Web View
    - Developers
    - TWA
    - PWA
    - Trusted web activities
    - Progressive web apps
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-26T05:08:01Z'
  edited_at: '2026-08-18T00:13:45Z'
  id: 360002330178
  locale: ru
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/ru/articles/360002330178
---
> **Краткий обзор.** Используйте AppsFlyer с Trusted Web Activities (TWA) для измерения количества установок и регистрации событий в приложении.

<div id="introduction" />

## Введение

<div id="what-are-trusted-web-activities" />

### Что такое Trusted Web Activities?

Trusted Web Activities (TWA) — это новый способ интеграции веб-контента в приложение для Android. Сложность с TWA заключается в том, чтобы иметь возможность регистрировать события в приложении. Эта проблема рассматривается в данной статье. Более подробную информацию о TWA смотрите <Anchor target="_blank" href="https://developers.google.com/web/updates/2019/02/using-twa">здесь</Anchor>.

TWA также можно использовать с Progressive Web Apps.

<div id="what-are-progressive-web-apps" />

### Что такое Progressive Web Apps?

Progressive Web Apps (PWA) — это приложения, которые выглядят для пользователя как приложения, но на самом деле полностью основаны на веб-технологиях. Одним из видов PWA является приложение для Android, активность которого основана на TWA. Именно эта форма PWA рассматривается в данной статье. TWA позволяет встроить PWA в отдельное приложение для Android, что дает вам возможность представить ваше PWA-приложение в Play Store.

Другая форма, исключительно веб-ориентированная, в этой статье не рассматривается. Более подробную информацию о PWA можно найти <Anchor target="_blank" href="https://developers.google.com/web/progressive-web-apps/">здесь</Anchor>.

На этой вкладке рассматриваются PWA, встроенные в Trusted Web Activity, полноэкранный веб-браузер в приложении. Такие приложения относятся к <Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">глобальному классу приложений Android</Anchor>, но их деятельность осуществляется исключительно через веб (браузер).

Эта форма PWA позволяет измерять количество установок. Другая разновидность PWA — те, что основаны исключительно на веб-технологиях, — не дает возможности измерять количество установок.

## TWA

<div id="sending-inapp-events-from-twa" />

<Accordion title="Отправка событий в приложении из TWA">

События в приложении отправляются с помощью AppsFlyer SDK из активностей нативного приложения. Поскольку TWA имеет веб-основу, а не нативные активности, вы не можете отправлять события в приложении с помощью AppsFlyer SDK. В качестве альтернативы можно использовать <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">события внутри приложения от сервера к серверу</Anchor>. Следуйте приведенным ниже инструкциям, чтобы отправить события с сервера на сервер с помощью TWA.

<div id="prerequisites" />

### Необходимые условия

Прежде чем начать отправлять события из TWA в AppsFlyer, выполните следующие действия:

1. Добавьте следующий репозиторий в файл gradle на уровне проекта:  

   ```java
   maven { url "https://jitpack.io"}
   ```
2. Добавьте следующие строки:
   * Для библиотек android.support:
     * Добавьте следующее в файл build.gradle:  
       implementation 'com.github.GoogleChrome.custom-tabs-client:customtabs:91b4a1270b'
     * Импортируйте следующие библиотеки:

       ```java
       import android.support.customtabs.CustomTabsClient;
       import android.support.customtabs.CustomTabsIntent;
       import android.support.customtabs.CustomTabsServiceConnection;
       import android.support.customtabs.CustomTabsSession;
       import android.support.customtabs.trusted.TrustedWebActivityIntentBuilder;
       import static android.support.customtabs.TrustedWebUtils.EXTRA_LAUNCH_AS_TRUSTED_WEB_ACTIVITY
       ```
   * Для библиотек androidX:
     * Добавьте следующее в файл build.gradle:  

       ```java
       implementation 'com.github.GoogleChrome:android-browser-helper:ff8dfc4ed3'
       ```
     * Импортируйте следующие библиотеки:

       ```java
       import androidx.browser.customtabs.CustomTabsClient;
       import androidx.browser.customtabs.CustomTabsIntent;
       import androidx.browser.customtabs.CustomTabsServiceConnection;
       import androidx.browser.customtabs.CustomTabsSession;
       import androidx.browser.trusted.TrustedWebActivityIntentBuilder;
       ```

<div id="getting-the-appsflyer-id" />

### Получение идентификатора AppsFlyer ID

Чтобы отправлять события с сервера на сервер, вам нужен идентификатор AppsFlyer. Вы можете получить AppsFlyer ID из SDK AppsFlyer для Android.

Во-первых, убедитесь, что <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">SDK AppsFlyer для Android интегрирован</Anchor>. Затем вы можете получить идентификатор AppsFlyer, используя следующий API SDK:

```java
String appsflyerId = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
```

<div id="sending-the-appsflyer-id-to-twa" />

### Отправка AppsFlyer ID в TWA

Вы можете отправить идентификатор AppsFlyer одним из двух способов:

<div id="append-appsflyer-id-and-customer-user-id-to-url" />

<Accordion title="Добавьте идентификатор AppsFlyer и идентификатор клиента в URL">

Когда вы создаете намерение для trusted web activity, вы можете передавать параметры в его URL:

```java
private void launchTwa(String cuid, String af_id) {

    CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Настройка CustomTabsSession, которая используется для создания intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Создание intent для запуска TWA с использованием URL-адреса с параметрами запроса, которые может прочитать веб-приложение
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri + "?cuid=" + cuid + "&appsflyer_id=" + af_id));
            Intent twaIntent = twaIntentBuilder.build(session);

            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

<div id="retrieving-the-appsflyer-id" />

#### Получение идентификатора AppsFlyer ID

После запуска веб-активности вы можете получить идентификатор AppsFlyer с помощью простого фрагмента JavaScript:

```javascript
let url = new URL(document.location.href);
    let appsflyerID;
url.searchParams.forEach((value, key) => {
    if(key === 'appsflyer_id') {
    	appsflyerID = value;
    }
})
```

Получив идентификатор AppsFlyer, сохраните его в локальном хранилище, чтобы использовать в дальнейшем.

</Accordion>

<div id="sending-appsflyer-id-through-custom-headers" />

<Accordion title="Отправка идентификатора AppsFlyer через пользовательские заголовки">

Вы можете передавать пользовательские заголовки в trusted web activities. Сервер получает эти заголовки, записывает их в cookie и отправляет в браузер. Затем вы можете получить идентификатор AppsFlyer с помощью javascript:

```java
private void launchTwa(String cuid, String af_id) { 
        CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Настройка CustomTabsSession, которая используется для создания intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Создание intent для запуска TWA с использованием URL-адреса с параметрами запроса, которые может прочитать веб-приложение
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri);
            Intent twaIntent = twaIntentBuilder.build(session);

            // Передача дополнительных пользовательских заголовков в intent, чтобы веб-приложение могло их прочитать
            Bundle customHeaders = new Bundle();
            customHeaders.putString("twa_params", "cuid=" + cuid + "&=appsflyer_id" + af_id");
            twaIntent.putExtra(Browser.EXTRA_HEADERS, customHeaders);
            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

<div id="retrieving-the-appsflyer-id-1" />

#### Получение идентификатора AppsFlyer ID

JavaScript не предоставляет API, позволяющего разработчикам получать доступ к заголовкам. Поэтому сервер должен отправить данные о конверсии обратно в веб-активность в виде cookie. Сервер получает пользовательские заголовки, содержащие идентификатор AppsFlyer, анализирует эти данные и отправляет их на веб-страницу в виде cookie.

Необходимо установить фрагмент JavaScript, чтобы получать cookie с AppsFlyer ID при загрузке страницы.

```javascript
// получить cookie с данными конверсии 
// функция взята с https://plainjs.com/javascript/utilities/set-cookie-get-cookie-and-delete-cookie-5/
function getCookie(name) {
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}

// получить cookie
var conversionData = JSON.parse(getCookie('appsflyer_id'));
console.log(appsflyer_id);
```

</Accordion>

<div id="sending-the-in-app-event" />

### Отправка события в приложении

Чтобы отправлять события в приложении, вам нужно отправить данные о событии на ваш сервер, а ваш сервер должен отправить событие в AppsFlyer. Есть еще несколько условий для отправки событий в приложении:

* <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">Ключ разработчика SDK</Anchor> — **Важно! Ключ разработчика SDK является конфиденциальным значением и не должен присутствовать в TWA. Если вы собираетесь использовать TWA и отправлять события внутри приложения с сервера на сервер, всегда храните ключ разработчика SDK в безопасном месте на стороне сервера.**
* App ID — идентификатор приложения, как он отображается в файле Manifest.xml в Android.

Получив эти три параметра (идентификатор AppsFlyer, ключ разработчика SDK, идентификатор приложения), вы можете отправить внутреннее событие приложения. Всякий раз, когда в веб-активности происходит событие, вы должны отправить запрос вашему веб-серверу на обработку этого события. Веб-сервер получает данные, относящиеся к событию, составляет событие и отправляет его в AppsFlyer.

Примеры отправки событий в приложении от сервера к серверу смотрите <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile#api-событий-от-сервера-к-серверу-для-мобильных-приложений">здесь</Anchor>.

</Accordion>

<div id="customizing-web-content-with-conversion-data" />

<Accordion title="Настройка веб-контента с помощью данных о конверсии">

AppsFlyer SDK предоставляет вам данные о конверсии через два API:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">Get conversion data</Anchor> вызывается при первом запуске приложения после установки и при последующих запусках приложения.
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/api-reference#onappopenattribution">On app open attribution</Anchor> вызывается при переходе пользователя в приложение по диплинку на основе OneLink.

Вы можете использовать данные о конверсии для настройки веб-контента.

<div id="sending-conversion-data-to-twa" />

### Отправка данных о конверсии в TWA

Получив данные о конверсии любым из вышеперечисленных способов, вы можете отправить их на свой веб-сервер. Для этого используйте пользовательские заголовки:

```java
private void launchTwa(Map<String, String> conversionData, String cuid, String af_id) { 
        CustomTabsServiceConnection customTabsServiceonnection = new CustomTabsServiceConnection() {

        @Override
        public void onCustomTabsServiceConnected(ComponentName name, CustomTabsClient client) {
            Log.d(LOG_TAG, "onCustomTabsServiceConnected");

            // Настройка CustomTabsSession, которая используется для создания intent
            mClient = client;
            CustomTabsSession session = mClient.newSession(null);

            // Создание intent для запуска TWA с использованием URL-адреса с параметрами запроса, которые может прочитать веб-приложение
            TrustedWebActivityIntentBuilder twaIntentBuilder = new TrustedWebActivityIntentBuilder(Uri.parse(defaultUri);
            Intent twaIntent = twaIntentBuilder.build(session);

            // Передача дополнительных пользовательских заголовков в intent, чтобы веб-приложение могло их прочитать
            Bundle customHeaders = new Bundle();
            customHeaders.putString("twa_params", "cuid=" + cuid + "&=" + af_id");
            customHeaders.putString("conversion_data", conversionData);
            twaIntent.putExtra(Browser.EXTRA_HEADERS, customHeaders);
            startActivity(twaIntent);
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {
            Log.d(LOG_TAG, "onCustomTabsServiceDisconnected");
        }
    };

    CustomTabsClient.bindCustomTabsService(getApplicationContext(), "com.android.chrome", customTabsServiceonnection);
}
```

<div id="fetching-the-conversion-data-from-the-client-side" />

### Получение данных о конверсии со стороны клиента

JavaScript не предоставляет API, позволяющего разработчикам получать доступ к заголовкам. Поэтому сервер должен отправить данные о конверсии обратно в веб-активность в виде cookie. Сервер получает пользовательские заголовки, содержащие данные о конверсии, анализирует их и отправляет на веб-страницу в виде cookie.

Следует установить фрагмент JavaScript, который при загрузке страницы будет получать cookie с данными о конверсии и соответствующим образом настраивать контент. Например, если пользователь устанавливает приложение в результате кампании, посвященной предложениям на авиабилеты, вы можете наполнить веб-активность контентом, относящимся к этим предложениям.

```javascript
// получить cookie с данными конверсии 
// функция взята с https://plainjs.com/javascript/utilities/set-cookie-get-cookie-and-delete-cookie-5/
function getCookie(name) {
    var v = document.cookie.match('(^|;) ?' + name + '=([^;]*)(;|$)');
    return v ? v[2] : null;
}

// получить cookie
var conversionData = JSON.parse(getCookie('conversion_data'));
console.log(conversionData);
/*
пример данных конверсии:
{ 
        campaign: "CAMPAIGN_NAME", // "None", если не указано в ссылке
        media_source: "MEDIA_SOURCE", //"None", если не указано в ссылке     
        cost_cents_USD : "0",
        is_first_launch: true,
        install_time: "2018-12-30 23:59:39.330",
        orig_cost: "0.0",
        af_click_lookback: "7d",
        click_time: "2018-12-30 23:59:09",
        cost_cents_USD: "0",
        af_status: "неорганический"
}
*/
```

Подробнее о вариантах использования данных о конверсии читайте <Anchor target="_blank" href="/marketers/ru/docs/conversion-data-payloads-and-scenarios">здесь</Anchor>.

</Accordion>

## PWA

<div id="measuring-installs-for-pwa" />

<Accordion title="Измерение количества установок для PWA">

Как и в случае с любым другим приложением для Android, вы можете интегрировать AppsFlyer SDK в приложение, чтобы измерять количество установок и получать данные о конверсии.

Для измерения установок достаточно интегрировать SDK, следуя инструкциям <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">здесь</Anchor>.

</Accordion>

<div id="customizing-content-using-conversion-data" />

<Accordion title="Персонализация контента с использованием данных о конверсии">

Вы можете настроить веб-контент в соответствии с кампанией, которая побуждает пользователя установить ваше приложение. Например, если пользователь устанавливает приложение из кампании, которая дает ему скидку 20% на товары из вашего интернет-магазина. Вы можете получить данные о конверсии и применить скидку, как только приложение откроет веб-активность.

Чтобы узнать, как использовать данные о конверсии для настройки веб-контента, следуйте инструкциям [здесь](/docs/using-appsflyer-with-twa#отправка-данных-о-конверсии-в-twa).

</Accordion>

<div id="recording-events-in-pwa" />

<Accordion title="Запись событий в PWA">

PWA использует TWA, которые по сути являются веб-активностями. Поскольку TWA имеет веб-основу, а не нативные активности, вы не можете отправлять события в приложении с помощью AppsFlyer SDK. В качестве альтернативы можно использовать события внутри приложения от сервера к серверу.

Следуйте инструкциям [здесь](/docs/using-appsflyer-with-twa#sending-inapp-events-from-twa), чтобы узнать, как отправлять события в приложении для PWA.

</Accordion>

<div data-zendesk-anchors="introduction=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 what-are-trusted-web-activities=%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-trusted-web-activities what-are-progressive-web-apps=%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-progressive-web-apps prerequisites=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F getting-the-appsflyer-id=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0-appsflyer-id sending-the-appsflyer-id-to-twa=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-appsflyer-id-%D0%B2-twa retrieving-the-appsflyer-id=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0-appsflyer-id-1 retrieving-the-appsflyer-id::a3f31d46=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0-appsflyer-id-2 sending-the-inapp-event=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 sending-conversion-data-to-twa=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%B2-twa fetching-the-conversion-data-from-the-clientside=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D1%81%D0%BE-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D1%8B-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0" />

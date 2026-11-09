---
title: Плагин Adobe AIR
metadata:
  keywords:
    - github
    - Adobe
    - Air
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
  created_at: '2013-12-09T11:32:45Z'
  edited_at: '2026-08-28T00:13:56Z'
  id: 207032226
  locale: ru
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/ru/articles/207032226
---
> **Краткий обзор:** Интегрируйте SDK AppsFlyer в приложения для iOS/Android, разработанные на платформе Adobe AIR, чтобы измерять установки, события в приложении, медиаисточники и многое другое.

<div id="plugin-information" />

## Информация о плагине

Поддерживаемые платформы:

* Android;
* iOS 6+

На основе:

* iOS AppsFlyer SDK V6.0.3
* Android AppsFlyer SDK V5.4.1

<div id="installation-and-implementation" />

## Установка и внедрение

<div id="installation" />

<Accordion title="Установка">

Загрузите файл  <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/blob/master/bin/AppsFlyerAIRExtension.ane">AppsFlyerAIRExtension.ane</Anchor>  из папки bin. Добавьте ANE в свой проект и убедитесь, что в IDE включено его добавление в пакет.

Если следующее не было добавлено автоматически, добавьте это в APP\_NAME-app.xml:

```html Markup
<extensions>
  <extensionID>com.appsflyer.adobeair</extensionID>
</extensions>
```

<div id="notes-for-android-apps" />

> 📘 **Примечания для приложений Android**
>
> * В дэшборде AppsFlyer нужно добавить префикс "air." к имени пакета, так как Air добавляет его автоматически. Например, для приложения с именем пакета "**com.test.android**" нужно задать идентификатор приложения в дэшборде AppsFlyer как "**air.com.test.android**".
> * Добавьте следующие разрешения в Android Manifest (в описании приложения `APP_NAME-app.xml`):
>
>   ```html Markup
>   <uses-permission android:name="android.permission.INTERNET"/>
>   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
>   <uses-permission android:name="com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE" />
>   ```
> * Добавьте следующий метатег в Android Manifest внутри тега application (в описании приложения `APP_NAME-app.xml`):
>
>
>   ```html Markup
>   meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />
>   ```
>
> В результате ваш Android Manifest должен выглядеть так:
>
> <Image align="center" alt="" src="https://files.readme.io/b50aa4f38d258eb2f6a01017da248fdf8a9fd21c3d83aae8bf4928094b8094b8-360010932998.png" />
>
> **Важно:** Из-за некоторых ограничений в <Anchor target="_blank" href="https://help.adobe.com/en_US/air/build/WS5b3ccc516d4fbf351e63e3d118666ade46-7fd9.html">ADT</Anchor> после сборки APK в нём отсутствуют некоторые важные файлы.
>
> Чтобы добавить эти файлы (с помощью **автоматизированного** скрипта):
>
> 1. Поместите в один каталог по вашему выбору:
>    * Файл APK
>    * Файл keystore, использованный для подписи APK
>    * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/blob/master/bin/af_apk_fix.sh">af\_apk\_fix.sh script</Anchor>
> 2. Запустите `./af_apk_fix.sh` и введите запрошенные данные по запросу.
>
> Вот что делает этот скрипт. Если возникнут какие-либо проблемы, вы можете выполнить эти шаги вручную:
>
> 1. Декодируйте APK с помощью <Anchor target="_blank" href="https://ibotpeaches.github.io/Apktool/">apktool</Anchor>. При этом будет создана папка app\_name.
>    `apktool d app_name.apk`
> 2. Загрузите [jar/aar SDK AppsFlyer](https://repo.maven.apache.org/maven2/com/appsflyer/af-android-sdk/5.4.1/af-android-sdk-5.4.1.aar) той же версии, которая использовалась в APK.
> 3. Извлеките файлы `a-` и `b-` из jar-файла (переименовав jar в zip) и поместите их в папку с декомпилированным apk по пути `app_name/unknown/com/appsflyer/internal`
> 4. Отредактируйте `apktool.yml` и добавьте эти строки в раздел `unknownFiles:`
>
>    ```
>    com/appsflyer/internal/b-: '0'
>    com/appsflyer/internal/a-: '0'
>    ```
>
>    См. пример снимка экрана ниже.
>
>    [![](https://files.readme.io/6bacbb55e5b1a7739034db8cc03313459ad6d048313a51ef6bf1e07500165cc0-360010933018.png)](https://files.readme.io/6bacbb55e5b1a7739034db8cc03313459ad6d048313a51ef6bf1e07500165cc0-360010933018.png)
> 5. Соберите APK.back (он появится в папке `app_name/dist` folder).
>    `apktool b app`
> 6. Подпишите APK.
>
>    ```html Markup
>    jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore myKeystore.keystore app_name/dist/app_name.apk myKey
>    ```
> 7. Выполните zipalign для apk (чтобы его можно было загрузить в Google Play)
>
>    ```html Markup
>    zipalign -f -v 4 app_name/dist/app_name.apk app_name/dist/zipalign_app_name.apk
>    ```
> 8. Проверьте zipalign
>
>    ```html Markup
>    zipalign -c -v 4 app_name/dist/zipalign_app_name.apk
>    ```
> 9. Ваш apk `zipalign_app_name.apk` готов к использованию!

</Accordion>

<div id="implementation" />

<Accordion title="Внедрение">

Импортируйте расширение AppsFlyer в свой проект:

```html Markup
import AppsFlyerInterface;
```

Создайте интерфейс AppsFlyer:

```html Markup
private static var appsFlyer:AppsFlyerInterface; 
appsFlyer = new AppsFlyerInterface();
```

[Необязательно] Если вы хотите настроить диплинкинг или получить доступ к данным о конверсиях AppsFlyer из приложения, зарегистрируйте Conversion Listener:

```html Markup
appsFlyer.registerConversionListener();
```

Задайте ключ разработчика и идентификатор ID приложения iOS (необязательно), а затем инициализируйте SDK:

```html Markup
appsFlyer.appsFlyer.init("DevKey", "iOSAppID");
```

Инициализируйте логирование сессий (автоматически регистрируются запуски приложения и переходы из фона на передний план) с помощью DevKey и идентификатора приложения iOS (необязательно):

```html Markup
appsFlyer.start("DevKey", "iOSAppID");
```

</Accordion>

<div id="deep-linking" />

<Accordion title="Диплинкинг">

Чтобы получать соответствующую информацию AppsFlyer из используемой ссылки для диплинкинга:

1. Зарегистрируйте следующие слушатели событий:

   ```html Markup
   appsFlyer.addEventListener(AppsFlyerEvent.APP_OPEN_ATTRIBUTION, eventHandler); // success 
   appsFlyer.addEventListener(AppsFlyerEvent.ATTRIBUTION_FAILURE, eventHandler); // error
   ```
2. Обработайте ответ в соответствующем обработчике события:

   ```html Markup
   private function eventHandler(event:AppsFlyerEvent):void {
   	log("AppsFlyer event: " + event.type + "; \nData: " + event.data);
   }
   ```

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Отложенная глубинная ссылка (диплинкинг)">

Чтобы получать данные конверсии для текущей установки:

1. Зарегистрируйте следующие слушатели событий:

   ```html Markup
   appsFlyer.addEventListener(AppsFlyerEvent.INSTALL_CONVERSATION_DATA_LOADED, eventHandler); // success
   appsFlyer.addEventListener(AppsFlyerEvent.INSTALL_CONVERSATION_FAILED, eventHandler); //error
   ```
2. Обработайте ответ в соответствующем обработчике события:

   ```html Markup
   private function eventHandler(event:AppsFlyerEvent):void {
   	log("AppsFlyer event: " + event.type + "; \nData: " + event.data);
   }
   ```

</Accordion>

<div id="imei-and-android-id-collection-android-only" />

<Accordion title="Сбор IMEI и идентификатора ID Android (только для Android)">

**Важно!** Приложения, использующие службы Google Play, не должны выполнять сбор данных IMEI, так как это противоречит политике Google Play.

Если приложение работает в ОС версии выше KitKat (4.4) и на устройстве установлены службы Google Play, то по умолчанию SDK не проводит сбор данных IMEI и Android ID.

Чтобы явно отправить эти идентификаторы в AppsFlyer, разработчики могут использовать следующие API и разместить их перед инициализацией SDK.

Если службы Google Play в приложении НЕ используются, сбор данных IMEI и Android ID выполняется с помощью SDK.

**Включить/отключить сбор IMEI (по умолчанию отключен)**

```html Markup
appsFlyer.setCollectIMEI(bool);
```

**Задать данные IMEI вручную**

```html Markup
appsFlyer.setImeiData("imeiString");
```

**Включить/отключить сбор идентификатора ID Android (по умолчанию отключен)**

```html Markup
appsFlyer.setCollectAndroidID(bool);
```

**Задать данные идентификатора ID Android вручную**

```html Markup
appsFlyer.setAndroidIdData("AndroidIDString");
```

</Accordion>

<div id="api-reference" />

## Справочник по API

<div id="api-methods" />

<Accordion title="Методы API">

<Table>
  <thead>
    <tr>
      <th>
        YouTube video player
      </th>
      <th>
        Description(Описание)
      </th>
      <th>
        Подпись/пример
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        logEvent
      </td>
      <td>
        Регистрирует события в приложении.
      </td>
      <td>
        ```html Markup
        var param:String = "Deposit";
        var value:String = '{"amount":10, "FTDLevel":"-"}';
        appsFlyer.logEvent(param, value);
        ```
      </td>
    </tr>
    <tr>
      <td>
        начать
      </td>
      <td>
        Отправляет событие логирования сессии независимо от состояния приложения.
      </td>
      <td>
        ```html Markup
        appsFlyer.start();
        ```
      </td>
    </tr>
    <tr>
      <td>
        setAppUserId
      </td>
      <td>
        Возвращает ID пользователя, используемый в приложении.
      </td>
      <td>
        ```html Markup
        appsFlyer.setAppUserId("user_id_as_used_in_the_app");
        ```
      </td>
    </tr>
    <tr>
      <td>
        setUserEmails
      </td>
      <td>
        Возвращает адрес электронной почты пользователя.
      </td>
      <td>
        ```html Markup
        appsFlyer.setUserEmails("example@example.com");
        ```
      </td>
    </tr>
    <tr>
      <td>
        setCurrency
      </td>
      <td>
        Устанавливает валюту для логирования событий о доходе, например USD.
      </td>
      <td>
        ```html Markup
        appsFlyer.setCurrency("USD");
        ```
      </td>
    </tr>
    <tr>
      <td>
        завершить
      </td>
      <td>
        Используется, если нужно полностью отключить логирование SDK для соблюдения правовых норм и требований конфиденциальности. После вызова этого API наш SDK больше не взаимодействует с нашими серверами.
      </td>
      <td>
        ```html Markup
        appsFlyer.stop();
        ```
      </td>
    </tr>
    <tr>
      <td>
        setDebug
      </td>
      <td>
        Включает/отключает отладочные журналы AppsFlyer.

        **Важно:** не публикуйте приложение в магазинах приложений с включенными журналами отладки.
      </td>
      <td>
        ```html Markup
        appsFlyer.setDebug(bool);
        ```
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="plugin-information=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BF%D0%BB%D0%B0%D0%B3%D0%B8%D0%BD%D0%B5 installation-and-implementation=%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D0%B8-%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5 api-reference=%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D1%87%D0%BD%D0%B8%D0%BA-%D0%BF%D0%BE-api" />

---
title: Методы сохранения конфиденциальности в SDK
metadata:
  keywords:
    - Advertisers
    - coppa
    - opt-out
    - opt out
    - consent management
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
  created_at: '2018-08-20T11:14:36Z'
  edited_at: '2026-08-18T00:34:46Z'
  id: 360001422989
  locale: ru
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ru/articles/360001422989
---
> **At a glance:** Сохраняйте конфиденциальность ваших пользователей с помощью одного или нескольких методов, доступных в AppsFlyer SDK.

> 📘 **Note**
>
> **Примечание**
>
> Информация в этой статье предназначена исключительно для того, чтобы дать представление о доступных разработчикам приложений методах контроля обмена пользовательскими данными с владельцами приложений, рекламными и социальными сетями. **Эта статья не включает в себя и не является руководством по соблюдению законодательных норм конфиденциальности, таких как COPPA или GDPR, или каких-либо конкретных правил по сохранению конфиденциальности.**

AppsFlyer SDK предлагает владельцам приложений несколько способов защиты конфиденциальности пользователей и контроля данных. В этой статье мы рассмотрим эти методы и оценим, как они влияют на пользовательские данные и как их использовать, чтобы сохранить конфиденциальность пользователей и при этом обеспечить возможность атрибуции.

После того как вы решите, какие варианты использовать, поделитесь информацией о внедрении из нашего хаба для разработчиков со своими разработчиками.

Давайте обсудим каждый метод.

<div id="use-start-and-stop-methods" />

## Использование методов start и stop

SDK отправляет установки и события в приложении в AppsFlyer только после вызова метода `start`. Любое событие, предшествующее вызову `start`, не будет сообщено SDK. Аналогичным образом, если вызов `start` впоследствии будет отменен вызовом метода `stop`, никакие события после этого отправляться не будут.

<div id="impact-on-attribution" />

### Влияние на атрибуцию

Атрибуция **не** происходит, когда:

* метод `start` не вызывается.
* метод `stop` вызывается для отмены предыдущего вызова start.

<div id="common-use-cases" />

### Распространенные варианты применения

| Пример использования | Описание |
| --- | --- |
| Согласие на сбор данных или отказ от него при запуске | Вызовите `start` после того, как пользователь даст согласие на предоставление данных при первом запуске.  <br />Если пользователь не дает согласия на сбор данных, не вызывайте  <br />`start` вообще. |
| Отказ для сессии | В каждой сессии работы с приложением спрашивайте согласие и, соответственно, вызывайте или не вызывайте `start`. |
| Однократный отказ от предоставления данных (когда пользователь соглашается, а затем решает отказаться). | Вызовите `stop`, чтобы остановить отправку дальнейших событий из SDK. |

<div id="developer-reference" />

### Ссылки для разработчика

Справочная информация для разработчиков и документация по использованию методов start и stop:

<Tabs>
<Tab title="Android iOS">

[Используйте start, чтобы поделиться только событием установки.](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#use-start-to-share-only-the-install-event)

</Tab>

<Tab title="adjusted.png">

[Используйте start, чтобы поделиться только событием установки.](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#use-start-to-share-only-the-install-event)

</Tab>
</Tabs>

<div id="prevent-sharing-data-with-networks" />

## Предотвращение обмена данными с сетями

Во время интеграции с рекламной сетью или сетью с самостоятельной атрибуцией (SRN) вы можете выбрать, передавать или не передавать информацию уровня пользователя этому партнеру. В SDK вы можете дополнительно отфильтровать обмен данными со всеми или некоторыми партнерами в **соответствии с предпочтениями конечного пользователя** с помощью метода `setSharingFilterForPartners`.

При использовании этого метода AppsFlyer запретит передачу данных пользователей исключенному партнеру любыми способами, включая постбэки, API, отчеты по сырым данным и т. д.

<div id="impact-on-attribution-1" />

### Влияние на атрибуцию

* Установки **из исключенных рекламных сетей** **(не-SRN)** будут атрибутированы в AppsFlyer, но рекламные сети не будут уведомлены об этом в какой-либо форме или способом.
* **SRN** не атрибутируются, и их данные не передаются вашим интегрированным партнерам. Это не относится к **расширенным SRN**, где атрибуция по-прежнему возможна; однако установки, повторные вовлечения и события в приложении не будут передаваться обратно из-за фильтра передачи данных.

  > 📘 **Note**
  >
  > **Примечание**
  >
  > AppsFlyer не может атрибутировать данные о вовлечении для любых SRN, исключенных из получения ваших данных.


<div id="developer-reference-1" />

### Ссылки для разработчика

Ссылки для разработчиков и документация о том, как предотвратить передачу данных третьим лицам:

<Tabs>
<Tab title="Android iOS">

[Предотвращение передачи данных третьим лицам](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#prevent-sharing-data-with-third-parties)

</Tab>

<Tab title="/docs/set-up-multi-store-android-attribution">

[Предотвращение передачи данных третьим лицам](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#prevent-sharing-data-with-third-parties)

</Tab>
</Tabs>

<div id="anonymize-user-information" />

## Анонимизация пользовательской информации

В отличие от метода `anonymizeUser`, отключение определенных идентификаторов позволяет вам самим решить, какие идентификаторы вы хотите оставить. Вы можете запретить SDK собирать и отправлять определенные идентификаторы устройств в AppsFlyer.

* **Удаляются:** персональные идентификаторы (GAID, IDFA, IDFV и CUID)
* **Хешируется:** идентификатор AppsFlyer и IP-адрес

На следующем изображении показан пример строки сырых данных после анонимизации (удаление и хеширование).

![Пример строки сырых данных с удаленными и хешированными полями после анонимизации](https://files.readme.io/5cae15ee0e38c84b2f9876d0dca2145543e83e624933ca138017da5206e7a834-35847868223633.png)

<div id="impact-on-attribution-2" />

### Влияние на атрибуцию

Если вы вызовете `anonymizeUser` до вызова `start`, атрибуция не произойдет. В результате стандартные методы атрибуции, основанные на этих идентификаторах, не используются.

Однако атрибуция по-прежнему может выполняться следующими способами, которые не зависят от идентификаторов устройства:

* <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns#атрибуция">Атрибуция в сетях с самостоятельной отчетностью (SRN)</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#probabilistic-modeling">Вероятностное моделирование (PMOD)</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#install-referrer-android-only">Атрибуция на основе реферера</Anchor>

Чтобы атрибутировать событие установки, вызывайте функцию `anonymizeUser` только после того, как убедитесь, что SDK отправил событие установки в AppsFlyer.

Этот процесс гарантирует, что:

* Событие установки можно атрибутировать обычным образом.
* Все события в приложении, происходящие после вызова `anonymizeUser`, отправляются **без идентификаторов**.

В результате эти события в приложении либо учитываются как **органические**, либо **игнорируются** в зависимости от метода отчетности.

> 📘 **Note**
>
> **Примечание**
>
> В анонимизированном режиме поддерживаются <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns#атрибуция">SRN</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#probabilistic-modeling">PMOD (probabilistic)</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#install-referrer-android-only">атрибуция на основе реферера</Anchor>. Сюда входят <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#реферал-установки-в-google-play">Google Play Install Referrer</Anchor>, рефереры других магазинов (например, <Anchor target="_blank" href="/marketers/ru/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">Xiaomi, Huawei,</Anchor> <Anchor target="_blank" href="/marketers/ru/docs/set-up-appsflyer-preload-referrer-attribution#реферер-предзагрузки-samsung">и Samsung</Anchor>) и <Anchor target="_blank" href="/marketers/ru/docs/set-up-appsflyer-preload-referrer-attribution?utm_source=chatgpt.com">реферер предустановки AppsFlyer</Anchor>

<div id="developer-reference-2" />

### Ссылки для разработчика

Ссылки для разработчиков и документация о том, как анонимизировать информацию о пользователях:

<Tabs>
<Tab title="В">

[Анонимизация пользовательской информации](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#anonymize-user-information)

</Tab>

<Tab title="Задача">

[Анонимизация пользовательской информации](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#anonymize-user-information)

</Tab>
</Tabs>

<div id="remove-specific-device-identifiers" />

## Удаление определенных идентификаторов устройств

Вы можете запретить SDK собирать и отправлять определенные идентификаторы устройств в AppsFlyer. В отличие от метода `anonymizeUser`, отключение определенных идентификаторов позволяет вам самим решить, какие идентификаторы вы хотите оставить.

API SDK включает следующие методы отключения идентификаторов.

<div id="android-identifiers" />

### Идентификаторы Android

| Метод | Идентификаторы отключены |
| --- | --- |
| [`Установки из исключенных`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) | <ul><li>Рекламный идентификатор Google (GAID)</li><li>Открытый анонимный идентификатор устройства (OAID)</li><li>Рекламный идентификатор Amazon (AAID)</li></ul> |
| [`setcollectoaid`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid) | Открытый анонимный идентификатор устройства (OAID) |

<div id="ios-identifiers" />

### Идентификаторы iOS

| Метод | Идентификатор отключен |
| --- | --- |
| [`Согласие на сбор данных или отказ от него при запуске`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) | IDFA (iOS 13 и ниже) |
| [`disableIDFVCollection`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableidfvcollection) | IDFV |

<div id="developer-reference-3" />

### Ссылки для разработчика

Ссылки для разработчика и документация по удалению определенных идентификаторов устройств:

<Tabs>
<Tab title="Android iOS">

[Отключить идентификаторы](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#disable-ids)

</Tab>

<Tab title="Задача">

[Отключить идентификаторы](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#disable-ids)

</Tab>
</Tabs>

> 📘 **Note**
>
> **Вопросы о конфиденциальности в AppsFlyer?**
>
> Уровень конфиденциальности ваших данных в AppsFlyer определяется [Положением AppsFlyer об обработке данных](https://www.appsflyer.com/legal/processing-customer-data/). По вопросам по поводу этого положения или для связи с нашим сотрудником по защите данных отправьте письмо на адрес [dpo@appsflyer.com.](mailto:dpo@appsflyer.com)

<div data-zendesk-anchors="use-start-and-stop-methods=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%BE%D0%B2-start-%D0%B8-stop h_01HKD1N2C8V0SP1NG8W2EJPRQZ=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%BE%D0%B2-start-%D0%B8-stop impact-on-attribution=%D0%B2%D0%BB%D0%B8%D1%8F%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E h_01HKD1N2C80QAJSNE83SD45DJA=%D0%B2%D0%BB%D0%B8%D1%8F%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E common-use-cases=%D1%80%D0%B0%D1%81%D0%BF%D1%80%D0%BE%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82%D1%8B-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F h_01HKD1N2C8YHWYARRAGX1TD6DM=%D1%80%D0%B0%D1%81%D0%BF%D1%80%D0%BE%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82%D1%8B-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F developer-reference=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0 h_01HKM6VNJFCW77F2268XXDF65Q=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0 prevent-sharing-data-with-networks=%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%82%D0%B2%D1%80%D0%B0%D1%89%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BE%D0%B1%D0%BC%D0%B5%D0%BD%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 h_01HKD1N2C8ASV10XWY33R972MC=%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%82%D0%B2%D1%80%D0%B0%D1%89%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BE%D0%B1%D0%BC%D0%B5%D0%BD%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8 impact-on-attribution::aa0a9f9e=%D0%B2%D0%BB%D0%B8%D1%8F%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-1 h_01HKD1N2C8RA34M4TSWYCW3A9F=%D0%B2%D0%BB%D0%B8%D1%8F%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-1 developer-reference::f2007ab7=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-1 h_01HKM6VNJFP8C7KCFSV1046H0B=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-1 anonymize-user-information=%D0%B0%D0%BD%D0%BE%D0%BD%D0%B8%D0%BC%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%BE%D0%B9-%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D0%B8 h_01HKD1N2C8CWSWK0VSXZ39MQ3D=%D0%B0%D0%BD%D0%BE%D0%BD%D0%B8%D0%BC%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%BE%D0%B9-%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D0%B8 anonymize-impact=%D0%B2%D0%BB%D0%B8%D1%8F%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-2 h_01KK93D18X4QYG87CFMZWNHSBA=%D0%B2%D0%BB%D0%B8%D1%8F%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-2 developer-reference::e4cacf1f=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-2 h_01HKM6VNJF7XPZ9ME61JG4KM9Z=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-2 remove-specific-device-identifiers=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%BE%D0%B2-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2 h_01HKD1N2C8S3Y73AZ9J7JFDKQE=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%BE%D0%B2-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2 android-identifiers=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-android h_01HKD1N2C8HZ61XHMBC0JNTK7S=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-android ios-identifiers=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-ios h_01HKD1N2C8AHK4EYANG6N6ST06=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-ios developer-reference::4e0971d1=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-3 h_01HKM6VNJFV0YJWV8KT23VTKKH=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-3" />

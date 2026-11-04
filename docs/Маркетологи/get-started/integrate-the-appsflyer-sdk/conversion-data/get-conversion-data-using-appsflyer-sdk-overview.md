---
title: Получение данных о конверсиях с помощью SDK AppsFlyer — обзор
metadata:
  keywords:
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
  created_at: '2021-11-09T10:06:52Z'
  edited_at: '2026-08-18T00:13:51Z'
  id: 4410481069969
  locale: ru
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/ru/articles/4410481069969
---
> **Краткий обзор.** Используйте данные о конверсии для определения различных сценариев конверсии, настройки пользовательского опыта и многого другого.

Используйте данные о конверсии в следующих целях:

* Направление пользователей к определенным активностям
* Предоставление индивидуального контента

<div id="important" />

> 🚧 **Двоеточие (:)**
>
> **Ограничения данных конверсии SDK**
>
> При использовании callback `onConversionDataSuccess` в SDK AppsFlyer обратите внимание, что он может сработать до завершения процесса атрибуции. В результате данные, возвращаемые SDK, могут не совпадать с данными в отчетах или API AppsFlyer.
>
> **Рекомендация:**
> Не используйте метод Get Conversion Data (GCD) для сбора или проверки данных атрибуции.
> Чтобы получить точные и полные результаты атрибуции, используйте дэшборды, отчеты или API AppsFlyer.

<div id="get-conversion-data" />

## Получите данные о конверсиях

SDK AppsFlyer возвращает данные о конверсиях, используя следующее:

* * `onConversionDataSuccess`: Конверсии по привлечению пользователей (UA) и повторной атрибуции
    * Android: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerconversionlistener#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * iOS: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * Unity: loadConversionData
  * `onAppOpenAttribution`: Для конверсий при повторном вовлечении

<div data-zendesk-anchors="h_01K9KSQQDVDEACFRXS0M4JNW9M=%D0%B4%D0%B2%D0%BE%D0%B5%D1%82%D0%BE%D1%87%D0%B8%D0%B5- get-conversion-data=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B8%D1%82%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85 h_01HTZ6M409RPZAQM66R0H5HA16=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B8%D1%82%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F%D1%85" />

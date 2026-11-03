---
title: Идентификаторы устройств
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2021-10-12T14:16:09Z'
  edited_at: '2026-08-18T00:09:16Z'
  id: 4408847686161
  locale: ru
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ru/articles/4408847686161
---
> **Краткий обзор.** Узнайте, какие идентификаторы устройств поддерживаются в SDK AppsFlyer.

## Обзор

SDK AppsFlyer собирает идентификаторы устройств для <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#атрибуция">целей атрибуции</Anchor>.

SDK автоматически собирает такие идентификаторы, как AppsFlyer ID и Google Advertising ID (GAID). Сбор других идентификаторов для вашего приложения зависит от ваших потребностей (например, сбор информации о сторонних магазинах приложений для Android или о приложениях, продаваемых в Китае).

## Идентификаторы устройств Android

SDK поддерживает следующие идентификаторы устройств для всех платформ:

#### Приложения, опубликованные в Google Play

| Идентификатор устройства | Цель |
| --- | --- |
| <span id="gaid"></span>ГАИД | **Сбрасываемый пользователем** идентификатор Google Play для устройств Android.<br /><br />Начиная с SDK 4.8.0, AppsFlyer автоматически собирает этот идентификатор устройства. |

#### Приложения, опубликованные в сторонних магазинах приложений

| Идентификатор устройства | Цель |
| --- | --- |
| <span id="amazon-advertising-id"></span>Рекламный идентификатор Amazon | **Сбрасываемый пользователем** уникальный идентификатор, используемый в Amazon Fire TV. <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">См. обзор CTV</Anchor> |
| <span id="oaid"></span>OAID | **Сбрасываемый пользователем** идентификатор в некоторых магазинах для приложений Android.  Подробную информацию см. в <Anchor target="_blank" href="/marketers/ru/docs/android-oaid-implementation-in-the-sdk">руководстве по внедрению OAID</Anchor>. |
| <span id="android-id"></span>Время совершения события, полученное из первой вспомогательной атрибуции. | Уникальный **несбрасываемый** идентификатор мобильного устройства, используемый в сторонних магазинах приложений. SDK не собирает автоматически Android ID. Однако, если есть необходимость в сборе этих идентификаторов, ваш разработчик может реализовать сбор.<br /><br />IMEI не может использоваться в сочетании с GAID. |

## Идентификаторы устройств Apple

SDK поддерживает следующие идентификаторы устройств для платформ Android:

| Идентификатор устройства | Цель |
| --- | --- |
| <span id="idfa"></span>IDFA | Уникальный **сбрасываемый пользователем** идентификатор для пользователей Apple iOS или tvOS (Apple TV). Начиная с версии iOS 14.5, IDFA доступен только при согласии пользователя на сбор данных через <Anchor target="_blank" href="/marketers/ru/docs/about-att-and-skan#att-principles">запрос на ATT</Anchor>. |
| <span id="idfv"></span>IDFV | Идентификатор устройства, общий для всех приложений одного **производителя**, установленных на устройстве. После установки первого приложения ему присваивается идентификатор, и другим приложениям того же производителя присваивается тот же IDFV. Приложениям других производителей присваивается другой IDFV.<br /><br />Кроме того, при удалении всех приложений определенного производителя удаляется IDFV этого производителя, а при новой установке назначается новый IDFV. |

## Идентификаторы устройств CTV

SDK поддерживает следующие идентификаторы устройств для платформ iOS:

| Окно повторного вовлечения | Идентификатор устройства |
| --- | --- |
| Android TV | рекламный\_идентификатор |
| tvOS (Apple TV) | IDFA |
| Amazon Fire ТВ | amazon\_fire\_id |
| Chromecast | рекламный\_идентификатор |
| Roku | rida |
| Vizio | VIDA |
| Samsung | TIFA |
| LGUDID | IMEI |
| Xbox | custom |
| RIDA | vidaaid |
| Steam | steamid |
| Meta Quest (Oculus) | custom |
| Эпические игры | epicid |
| PlayStation | psid |
| Нативный ПК | custom |
| Google Play Games для ПК | См. [идентификаторы Android](/docs/about-device-identifiers#идентификаторы-устройств-android) |

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01H9YXEYC3PA271B3G3Y3GM9PS=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 android-device-identifiers=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2-android h_01H9YXEYC3D95A6G70EGNR8ENK=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2-android apps-published-on-google-play=%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BE%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2-google-play h_01H9YXEYC3RG2XCVVW8MJ5VZSC=%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BE%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2-google-play apps-published-in-thirdparty-app-stores=%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BE%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%BD%D0%B8%D1%85-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0%D1%85-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01H9YXEYC3JA3DPN6P43J1ZXR9=%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BE%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%BD%D0%B8%D1%85-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0%D1%85-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 apple-device-identifiers=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2-apple h_01H9YXEYC3733B1A85TEF35EAY=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2-apple ctv-device-identifiers=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2-ctv h_01H9YXEYC3DFPWVXA5Y3XANQ3P=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2-ctv" />

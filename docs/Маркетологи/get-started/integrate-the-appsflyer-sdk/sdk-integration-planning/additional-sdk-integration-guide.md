---
title: Интеграция дополнительных средств SDK
metadata:
  keywords:
    - iOS
    - Android
    - Integration
    - Advertisers
    - firetv
    - Advertiser
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2021-10-10T11:54:14Z'
  edited_at: '2026-08-19T00:15:04Z'
  id: 4408735106193
  locale: ru
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ru/articles/4408735106193
---
> **At a glance:** **Краткий обзор:** Рассмотрите дополнительные возможности SDK и совместно с разработчиком реализуйте API, например, для измерения удалений, атрибуции приглашений пользователей, push-уведомлений и настройки конфиденциальности.

<div id="additional-attribution-methods" />

## Дополнительные методы атрибуции

Рассмотрите дополнительные методы атрибуции, если планируете измерять показатели ТВ-рекламы, удалений или предустановленных приложений.

**Все платформы**

<Accordion title="Атрибуция CTV">

Атрибутируйте <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">пользователей мобильных устройств к ТВ-рекламе</Anchor>, транслируемой в определенных местоположениях в определенное время.

</Accordion>

<Accordion title="Измерение количества удалений приложений">

Измеряйте количество удалений приложения пользователями, привлеченными из различных источников. Измерение количества удалений дает возможность проанализировать и оптимизировать свои кампании для достижения нужных значений значимых KPI.

<Anchor target="_blank" href="/marketers/ru/docs/measure-uninstalls">Как настроить измерение удалений</Anchor>.

</Accordion>

**Только для Android**

<Accordion title="Предустановленные приложения">

В ходе <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-factory-preinstall-using-manifest-android">предустановочных кампаний</Anchor> изготовители устройств по просьбе владельцев приложений устанавливают эти приложения на устройства.

AppsFlyer позволяет легко атрибутировать установки предустановленных приложений. Когда пользователь в первый раз запускает приложение, AppsFlyer атрибутирует эту установку партнеру по предварительной загрузке как медиа-источнику.

</Accordion>

<div id="sessions" />

## Сессии

Измеряйте взаимодействие пользователей с приложением, подсчитывая количество пользовательских сессий за определенный период.

**Все платформы**

<Accordion title="Настройка временного интервала между сеансами">

По умолчанию две сессии учитываются как отдельные, если между запусками приложения прошло не менее 5 секунд. Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/measure-sessions#session-reporting-by-the-app-sdk">подсчете сессий</Anchor>.

Установка **большого интервала между запусками может отрицательно сказаться на работе API**, использующих данные сессий, например, для диплинкинга.

</Accordion>

**Только для Android**

<Accordion title="Фоновые сеансы для служебных приложений">

Регистрировать сессии пользователей можно <Anchor target="_blank" href="/marketers/ru/docs/measure-sessions#session-reporting-by-the-app-sdk">вручную</Anchor>. Это может оказаться полезным для служебных приложений, которые работают в фоновом режиме.

</Accordion>

<div id="owned-media" />

## Собственные медиа

Для атрибуции собственных медиа-источников, таких как сайты, аккаунты в соцсетях и приглашения пользователей, используйте OneLink.

**Все платформы**

<Accordion title="Разрешение упакованных URL-адресов глубинных ссылок">

Некоторые сторонние службы, такие как <Anchor target="_blank" href="/marketers/ru/docs/email-service-provider-esp-integration-guide">службы электронной почты</Anchor> упаковывают ссылки в электронных письмах в свои собственные домены регистрации кликов. Некоторые даже разрешают вам устанавливать свои собственные домены регистрации кликов. Упаковка ссылки OneLink в такие домены может привести к ограничению ее функциональных возможностей.

Чтобы решить эту проблему, разработчику нужно настроить приложение, используя следующие API:

<Tabs>
<Tab title="Нативный Android Нативный iOS Unity">

См. [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setresolvedeeplinkurls) в справочнике по Android SDK

</Tab>

<Tab title="iOS Native">

См. [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#resolvedeeplinkurls) в справочнике по SDK для iOS

</Tab>

<Tab title="Unity">

См. [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/api#setresolvedeeplinkurls) в справочнике по Unity SDK

</Tab>
</Tabs>

</Accordion>

<Accordion title="Регистрация push-уведомлений">

AppsFlyer поддерживает измерение кампаний с push-уведомлениями всех поставщиков, включая Google Cloud Messaging и службу push-уведомлений Apple.

<Anchor target="_blank" href="/marketers/ru/docs/measuring-push-notification-re-engagement-campaigns">Подробнее об измерении push-уведомлений</Anchor>.

</Accordion>

<Accordion title="Атрибуция приглашений пользователей">

С их помощью уже имеющиеся пользователи могут приглашать своих друзей и знакомых в качестве новых пользователей вашего приложения, что может существенно способствовать его продвижению. С помощью AppsFlyer можно атрибутировать и регистрировать установки, источником которых являются приглашения, отправленные пользователями из вашего приложения.

<Anchor target="_blank" href="/marketers/ru/docs/user-invite-attribution">Подробнее об атрибуции приглашений пользователей</Anchor>.

</Accordion>

<Accordion title="Атрибуция кампаний перекрестной рекламы">

Перекрестная реклама помогает значительно увеличить количество установок ваших приложений. AppsFlyer позволяет атрибутировать и регистрировать установки, источником которых является перекрестная реклама одного из ваших приложений в другом приложении, которое уже есть у пользователя.

<Anchor target="_blank" href="/marketers/ru/docs/cross-promotion-attribution-for-marketers">Подробнее об атрибуции перекрестной рекламы</Anchor>.

</Accordion>

<Accordion title="Атрибуция сессий приложения, инициированных с собственных сайтов (доменов)">

Владельцы приложений, которые используют для диплинкинга App Links или универсальные ссылки (без OneLink), могут настроить в SDK атрибуцию сессий, инициированных через домен, связанный с их приложением (<Anchor target="_blank" href="https://developer.android.com/studio/write/app-link-indexing#associatesite">Android</Anchor>/<Anchor target="_blank" href="https://developer.apple.com/documentation/xcode/supporting-associated-domains?preferredLanguage=occ">iOS</Anchor>).

Например:

* Пользователь ищет что-то в Google и кликает по ссылке на ваш домен **www.example.com**.
* Если у пользователя не установлено приложение, он перенаправляется на веб-сайт (www.example.com).
* Если приложение уже установлено на устройстве этого пользователя, диплинк приведет его в приложение, связанное с доменом www.example.com. Эта сессия атрибутируется медиа-источнику (параметр `pid`), настроенному в SDK.

Доступна следующая документация для разработчиков:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Справочник по Android SDK</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Справочник по SDK для iOS</Anchor>

**Совет!** <Anchor target="_blank" href="/marketers/ru/docs/convert-your-mobile-web-visitors-to-app-users#решения-для-атрибуции">OneLink Smart Script</Anchor> помогает конвертировать посетителей сайта в пользователей мобильного приложения.

</Accordion>

<div id="user-privacy" />

## Конфиденциальность данных пользователей

Ознакомьтесь с такими нормативными актами, как GDPR и CCPA, учтите свои бизнес-требования и решите, какие политики согласия на сбор данных или отказа от него требуется реализовать.

**Все платформы**

<Accordion title="Политика отказа от сбора данных">

В некоторых случаях потребуется попросить разработчика настроить в SDK AppsFlyer прекращение или ограничение сбора данных (например, в соответствии с требованиями GDPR и CCPA). Существуют различные методы для сохранения конфиденциальности пользователей в SDK. Для получения дополнительной информации о различных методах см. статью <Anchor target="_blank" href="/marketers/ru/docs/apply-privacy-preserving-sdk-methods">Методы сохранения конфиденциальности в SDK</Anchor>.

</Accordion>

<Accordion title="Прекращение предоставления данных партнерам">

В некоторых случаях рекламодатели должны прекратить передачу рекламным сетям / партнерам данных по определенным пользователям. Причины могут быть следующие:

* Политики конфиденциальности, такие как CCPA или GDPR.
* Отказ пользователей от предоставления данных
* Конкуренция с некоторыми партнерами (рекламными сетями, третьими сторонами)

Обмен данными с партнерами контролируется с помощью метода `setSharingFilterForPartners`:

<Tabs>
<Tab title="Android iOS">

См. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> в справочнике по Android SDK.

</Tab>

<Tab title="Android native iOS native Unity React Native">

См. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">`resolveDeepLinkURLs`</Anchor> в справочнике по SDK для iOS.

</Tab>

<Tab title="Unity / React Native">

См. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> в справочнике по Unity SDK.

См. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> в справочнике по SDK React Native.

</Tab>
</Tabs>

</Accordion>

<Accordion title="Отправление согласия для соблюдения DMA">

В рамках закона ЕС «[О цифровых рынках](https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en)» (DMA) крупные технологические компании должны получать от конечных пользователей в Европе согласие прежде чем использовать личные данные из сторонних сервисов для рекламы.

Для соблюдения законодательства Google требует от клиентов AppsFlyer включать конкретные поля согласия при отправке в Google событий, связанных с конечными пользователями из ЕС. AppsFlyer SDK (Android: v6.13.0+, iOS: v6.13.1+) может отправлять необходимые данные о согласии с каждым событием, чтобы соответствовать этому требованию.

Для SDK возможны два альтернативных метода для сбора данных о согласии:

* **Через платформу для запросов согласия (CMP):** Если приложение использует CMP, соответствующую [спецификации Transparency and Consent Framework (TCF) v2.2](https://iabeurope.eu/tcf-supporting-resources/), SDK может автоматически извлекать детали согласия.

  ИЛИ
* **Через специальный API SDK**: Разработчики могут передавать необходимые данные согласия Google напрямую в SDK, используя специальный API, разработанный для этой цели.

Чтобы реализовать сбор данных согласия пользователей для соблюдения DMA, смотрите наши руководства в разделе для разработчиков:

<Tabs>
<Tab title="Нативный Android Нативный iOS">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-send-consent-for-dma-compliance">Отправление согласия для соблюдения DMA</Anchor>

</Tab>

<Tab title="iOS Native">

[Отправление согласия для соблюдения DMA](https://dev.appsflyer.com/hc/docs/ios-send-consent-for-dma-compliance)

</Tab>
</Tabs>

</Accordion>

**Только для iOS**

<Accordion title="Строгий режим в SDK">

Используйте строгий режим в SDK, чтобы полностью удалить функции сбора IDFA и зависимости инфраструктуры AdSupport (например, при разработке <Anchor target="_blank" href="https://developer.apple.com/app-store/review/guidelines/#kids-category">приложений для детей</Anchor>).

Если вы предлагаете приложения для детей, вместо обычного SDK вашему разработчику потребуется установить <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK со строгим режимом</Anchor>. **Примечание:** Данные IDFV остаются доступны.

</Accordion>

<Accordion title="Отключение фреймворков для рекламы">

Для отключения фреймворков AdSupport и iAd в SDK предусмотрены следующие схемы настройки:

<Tabs>
<Tab title="Android native iOS native Unity React Native">

* [`disableCollectASA`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disablecollectasa) для отказа от атрибуции Apple Search Ads.
* [`disableAdvertisingIdentifier`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) для того, чтобы не собирать в Apple `advertisingIdentifier` (рекламный идентификатор).

</Tab>

<Tab title="Unity">

* [`setDisableCollectIAd`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectiad) для отказа от атрибуции Apple Search Ads.
* [`setDisableCollectAppleAdSupport`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectappleadsupport) для того, чтобы не собирать в Apple `advertisingIdentifier` (рекламный идентификатор).

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="additional-attribution-methods=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D1%8B-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01H8W01DRHQHJKNMJA24PR5S2T=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D1%8B-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 sessions=%D1%81%D0%B5%D1%81%D1%81%D0%B8%D0%B8 01H8W01DRHD3EZBQT0ZKDMM1QB=%D1%81%D0%B5%D1%81%D1%81%D0%B8%D0%B8 owned-media=%D1%81%D0%BE%D0%B1%D1%81%D1%82%D0%B2%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0 01H8W01DRHV8H3QFJX5QKABK5E=%D1%81%D0%BE%D0%B1%D1%81%D1%82%D0%B2%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0 user-privacy=%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 01H8W01DRHJFB71DVJ64QWJME4=%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9" />

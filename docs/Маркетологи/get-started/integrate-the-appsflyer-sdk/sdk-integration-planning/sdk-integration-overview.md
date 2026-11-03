---
title: Обзор интеграции SDK (пакет средств разработки ПО)
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Integration
    - Advertisers
    - firetv
    - fire tv
    - Advertiser
    - Developer
    - appuid
    - anonymous
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2012-12-26T14:34:58Z'
  edited_at: '2026-08-19T00:15:17Z'
  id: 207032126
  locale: ru
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ru/articles/207032126
---
> **At a glance:** **Краткий обзор:** Изучите функции SDK (пакет средств разработки ПО) AppsFlyer и определите, какие API вы хотите использовать в вашем Приложении для Android или iOS.

## О SDK (пакет средств разработки ПО)

Посмотрите это видео, чтобы получить общее представление об интеграции SDK.

<Embed title="Обзор интеграции SDK (пакет средств разработки ПО)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/4iybquc6q3" providerUrl="https://fast.wistia.com" />

SDK обеспечивает функциональность установки Приложений и записи событий. Вы можете записывать установленные, сессии и события в приложении. События в приложении включают, например, внутренние покупки или повышение уровня в игре. Запись этих событий может помочь вам оценить ROI (окупаемость инвестиций) и качество пользователей.

Эта статья описывает процесс интеграции SDK V6+ и помогает рекламодателям (владельцам приложений) и менеджерам по продуктам планировать интеграцию AppsFlyer SDK в свои Приложения для Android или iOS.

Дополнительная документация включает в себя следующее:

<Tabs>
<Tab title="Android iOS">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">Документация по установке SDK для разработчиков</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-android-sdk-release-notes">Примечания к релизу</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference">Справочная документация SDK для разработчиков</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/fill-out-google-safety-section-form">Раздел о безопасности данных в Google Play</Anchor>

</Tab>

<Tab title="Android native iOS native Unity React Native">

* <Anchor target="_blank" href="/marketers/ru/docs/updating-to-ios-sdk-v6-and-plugins">Обновление до iOS SDK V6</Anchor>. Обратите внимание, что iOS SDK V5.4.4 полностью совместим с iOS 14. Однако мы рекомендуем использовать SDK V6.X для обеспечения совместимости с будущими версиями iOS.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">Документация по установке SDK для разработчиков</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes">Примечания к релизу</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference">Справочная документация SDK для разработчиков</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/preparing-for-the-app-store-review-nutrition-labels">Подготовка к проверке в магазине приложений — этикетки с данными</Anchor>

</Tab>

<Tab title="Unity">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Документация по установке SDK для разработчиков</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api">Справочная документация SDK для разработчиков</Anchor>

</Tab>

<Tab title="iOS native UnityReact Native">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Документация по установке SDK для разработчиков</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api">Справочная документация SDK для разработчиков</Anchor>

</Tab>
</Tabs>

## Совместимость SDK

AppsFlyer SDK совместим со следующими платформами:

<Tabs>
<Tab title="Android iOS">

* Начиная с Android V4.0
* Немобильные платформы на базе Android, такие как Smart TV (включая Amazon Fire TV). <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">См. обзор CTV</Anchor>
* Маркетплейсы вне магазина для Android приложений, такие как Amazon и Baidu

</Tab>

<Tab title="/docs/set-up-multi-store-android-attribution">

* iOS 9+ (iPhone, iPod, iPad)
* tvOS 9+ (Apple TV)
* Соответствует сетям Apple <Anchor target="_blank" href="https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1">IPv6 DNS64\/NAT64</Anchor>

SDK поддерживает <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model">разнообразные методы Атрибуции</Anchor>. Методы Атрибуции, которые используются, зависят от следующих факторов:

* Версия iOS, установленная на устройстве пользователя
* Версия iOS SDK, установленная в приложении

<table><thead><tr><th>Поддерживаемые методы Атрибуции</th><th>Версия iOS</th><th>Поддержка iOS SDK (пакет средств разработки ПО)</th><th>Примечания</th></tr></thead><tbody><tr><td rowspan="2">Вероятностное моделирование</td><td>8–14.4</td><td>5.0.0+</td><td> </td></tr><tr><td>14.5+</td><td>6.0.3+</td><td>Вероятностное моделирование ограничено контекстом собственных медиа, меж-продвижения и согласованных потоков из веб-приложений в приложения.</td></tr><tr><td rowspan="2">Сопоставление идентификаторов<br/><br/> </td><td>8–13</td><td>5.0.0+</td><td>Пользователи могут отказаться от функции ограниченное отслеживание рекламы (Limit Ad Tracking, LAT).</td></tr><tr><td>14.5+</td><td>6.0.3+</td><td>Требуется App Tracking Transparency (ATT) и согласие пользователя. Для получения дополнительной информации см. <a href="./basic-sdk-integration-guide#configure-app-tracking-transparency-att-support" target="_blank">настройте iOS SDK (пакет средств разработки ПО) для поддержки ATT</a>.</td></tr><tr><td rowspan="2"><a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork</a></td><td>11.3 - 13</td><td rowspan="2">6.2.3<br/><br/> </td><td>Решение SKAdNetwork (SKAN) <span>ограничено атрибуцией установки в соответствии со спецификацией </span><a href="https://developer.apple.com/documentation/storekit/skadnetwork" target="_blank">SKAN</a> <span>, что означает отсутствие ценности, значения конверсии.</span> </td></tr><tr><td>14+</td><td><ul><li>SKAN всегда доступен на уровнях iOS и SDK, независимо от настроек ATT.</li><li>Маркетолог активирует SKAN в дэшборде AppsFlyer.</li></ul></td></tr></tbody></table>

Начиная с SDK версии 6.0.8 доступна <Anchor target="_blank" href="/marketers/ru/docs/apple-app-clips-integration-guide">атрибуция Apple App Clips</Anchor>. Вы также можете прочитать нашу <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips">статью в блоге</Anchor> об Apple App Clips.

</Tab>
</Tabs>

## Интеграция SDK

Процесс установки и интеграции SDK требует совместной работы менеджера продукта и мобильного разработчика. **Перед** интеграцией SDK с вашим приложением, ознакомьтесь со всеми задачами интеграции и определите, какие функции вы хотите использовать.

### Контрольный список планирования SDK

Мы подготовили <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx">чек-лист</Anchor>, который сориентирует вас в процессе планирования. Для каждой задачи есть ссылки на документацию для маркетологов и разработчиков.

### Задачи интеграции SDK

Базовая интеграция SDK включает следующие задачи. Оценки времени предоставляются только для общего руководства.

| Основные задачи интеграции SDK | Время на планирование |
| --- | --- |
| Получите <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#внедрение-ключа-разработчика-в-ваше-приложение">ключ разработчика AppsFlyer</Anchor> и отправьте ссылку вместе с инструкциями по установке и интеграции вашему разработчику. | 15 мин. |
| Ознакомьтесь с <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#атрибуция">вопросами атрибуции</Anchor> и определите, какие идентификаторы устройств следует собирать. | 30 мин. |
| Определите <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#регистрация-внутренних-событий-приложения">события в приложении</Anchor>, которые вы хотите измерить, и отправьте названия событий и параметры разработчику. | 1 час |
| Определите методы <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#диплинкинг-с-помощью-onelink">диплинкинга</Anchor> , которые следует использовать. | 30 мин. |
| Определите методы <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#доступ-к-данным-атрибуции-и-диплинкинга">доступа к данным атрибуции</Anchor>. | 30 мин. |
| После завершения базовой интеграции любой пользователь учетной записи, имеющий доступ к дэшборду AppsFlyer, может выполнить <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#тестирование-интеграции-sdk">базовое тестирование</Anchor>.<br /><br />Разработчики могут использовать журналы отладки в <Anchor target="_blank" href="/marketers/ru/docs/testing-the-sdk-integration-for-marketers#testing-in-the-development-environment">среде разработки</Anchor>. | 1 час |

Вы можете работать с разработчиками мобильных приложений, чтобы внедрить эти дополнительные API в SDK (пакет средств разработки ПО).

| Дополнительные задачи интеграции SDK (пакет средств разработки ПО) | Время на планирование |
| --- | --- |
| Определите, нужна ли вашему приложению <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#дополнительные-методы-атрибуции">дополнительная настройка атрибуции</Anchor> (например, измерение удаления или атрибуция установок для сторонних магазинов приложений). | 30 минут |
| Определите <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#сессии">отчетность по сессиям пользователей</Anchor>. | 30 мин. |
| Определите методы атрибуции для использования с <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#собственные-медиа">собственными медиа-источниками</Anchor>. | 1 час |
| Управляйте политиками <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#конфиденциальность-данных-пользователей">конфиденциальности пользователей</Anchor>, чтобы ваше приложение соответствовало правилам конфиденциальности (GDPR, CCPA). | 1 час |

> 📘 **Note**
>
> **См. также**
>
> * Обзор платформ CTV, ПК и консолей

<div data-zendesk-anchors="about-the-sdk=%D0%BE-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE h_01H9FHRVKE6BHGW05G6YMKF737=%D0%BE-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE sdk-compatibility=%D1%81%D0%BE%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%B8%D0%BC%D0%BE%D1%81%D1%82%D1%8C-sdk h_01H9FHRVKEQ837Q0GFECNPPAN2=%D1%81%D0%BE%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%B8%D0%BC%D0%BE%D1%81%D1%82%D1%8C-sdk sdk-integration=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-sdk h_01H9FHRVKEN0MMGTSD362FTWPS=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-sdk sdk-planning-checklist=%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-%D1%81%D0%BF%D0%B8%D1%81%D0%BE%D0%BA-%D0%BF%D0%BB%D0%B0%D0%BD%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-sdk h_01H9FHRVKE468M1RTMF7VTYV1R=%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-%D1%81%D0%BF%D0%B8%D1%81%D0%BE%D0%BA-%D0%BF%D0%BB%D0%B0%D0%BD%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-sdk sdk-integration-tasks=%D0%B7%D0%B0%D0%B4%D0%B0%D1%87%D0%B8-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-sdk h_01H9FHRVKERHXY19R97EN86EGP=%D0%B7%D0%B0%D0%B4%D0%B0%D1%87%D0%B8-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-sdk" />

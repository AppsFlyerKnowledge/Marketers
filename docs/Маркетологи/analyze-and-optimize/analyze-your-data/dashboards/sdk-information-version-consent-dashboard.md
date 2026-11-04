---
title: Дэшборд информации об SDK (версия и согласие)
metadata:
  keywords:
    - SDK Information
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
  created_at: '2017-02-15T09:32:15Z'
  edited_at: '2026-10-19T14:01:18Z'
  id: 115000805366
  locale: ru
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ru/articles/115000805366
---
> **Кратко:** дэшборд с показателями внедрения SDK, долями использования операционных систем (iOS, Android) и метриками согласия ATT в iOS.

<div id="version-adoption-and-att-consent-dashboard" />

## Дэшборд внедрения версий и согласия ATT

Данные в дэшборде основаны на событии af\_open (сессия) и не связаны с событиями установки. Дэшборд содержит следующие основные разделы: 

* Информация о версии SDK; доступно для всех платформ (Android и  iOS)
* Метрики согласия ATT и внедрение iOS 16.1+ (что обеспечивает потенциальную доступность данных SKAN 4)

**Чтобы просмотреть дэшборд с информацией о SDK**:

1. В AppsFlyer в боковом меню выберите **Настройки** > **Информация об SDK**.
2. Выберите диапазон дат активности.   
   Показанные метрики описаны в следующих разделах.

<div id="sdk-information-ios-and-android" />

<Accordion title="Информация об SDK (iOS и Android)">

Ниже показаны метрики версий, доступные для приложений iOS и Android, на основе самой последней даты открытия приложения (запуска)

| Пользователи по | Например |
| --- | --- |
| Характеристика | Обратите внимание на выпуск версии приложения V1.4.28 20 мая 2021 г.<br /><br />[![UsersByAppVersion__1_.png](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png)](https://files.readme.io/87bbf8aba8295e44430098c7c6fe4dc290cafca229e271a4185c763c609e9833-4402595560337.png) |
| Параметр запроса | Обратите внимание на выпуск SDK V6.1.4 20 мая 2021 г.<br /><br />[![UsersBySDKVersion.png](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png)](https://files.readme.io/df7b4a1f380cd10162b3a13efc5da1ccc4b96e47d994e4c42b2674bfd4930bb6-4402589094033.png) |
| Версия операционной системы. | [![UsersByOsVersion.png](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png)](https://files.readme.io/d56f8b43155bb226adaa1a276e00634fe721a01b74b5114d273ae66e74034dd9-4402589093521.png) |
| Тип устройства | [![UsersByDevice.png](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png)](https://files.readme.io/2f320f91d6a5a9f4bca0e3715cd33dfff2ac971af29e961592b4494bafe721f0-4402595560977.png) |

</Accordion>

<div id="att-metrics-ios-14" />

<Accordion title="iOS и метрики ATT">

Используемая вашими пользователями версия iOS может повлиять на то, какие данные будут доступны. Например, если у пользователей iOS 16.1+, данные SKAN 4 потенциально доступны.

Статус <Anchor target="_blank" href="/marketers/ru/docs/att-implications-ios-14-and-deprecation-of-lat">ATT</Anchor> задается в iOS и передается в AppsFlyer вашим приложением. Возможные значения статуса ATT:

* **Разрешено**: пользователь явно согласился на отслеживание
* **Запрещено**: пользователь явно не согласился на отслеживание или LAT был включен до того, как пользователь обновился до iOS 14+
* **Не определено**: запрос ATT не отображался или пользователь не ответил
* **Ограничено**: Apple не разрешает отслеживать пользователя

**Учтите:**

* Метрики диаграммы рассчитываются на основе уникальных событий открытия приложения пользователями в указанную дату. Это означает, что если пользователь не открыл приложение в указанную дату, он не учитывается в метриках за эту дату.
* Метрики iOS и ATT включают только <Anchor target="_blank" href="/marketers/ru/docs/att-implications-ios-14-and-deprecation-of-lat#значения-att-определенные-apple">значения ATT, определенные Apple</Anchor>; не дополнительные значения, определенные AppsFlyer.
* Метрики коэффициента согласия рассчитываются по формуле: Authorized / (Authorized + Denied) x 100

<div id="att-and-ios-adoption-metrics-for-ios-apps" />

#### Метрики ATT и внедрения iOS для приложений iOS

| Диаграмма | Пример и примечания |
| --- | --- |
| Статус ATT при открытии приложения | [![AttStatusByDate.png](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)](https://files.readme.io/8e41e1602125903267e91a71b49305d43ca018aec77a2a991d0af08cb396825a-4402691807377.png)<br /><br />Относится к пользователям с iOS 14+, которые открывают приложение в указанную дату. Это означает, что метрики показывают статус ATT пользователя на указанную дату. |
| Согласие на ATT по версии приложения | [![ATTAppVersion.png](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png)](https://files.readme.io/1f19917998f142180d0fdfb5448c90b280b2d6536844c63ce630d3656719f656-4402589092113.png) |
| Тренд согласия на ATT | [![ConsentTrend.png](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png)](https://files.readme.io/bae0c55c603e83b87fa50ba6d16c628443d565417c1aceee4536a5b96dd9435e-4402589093265.png) |
| Процент использования iOS 16.1 | [![iso_user_adoption_rate.png](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png)](https://files.readme.io/2a29749fd968354f9836595cf20f07954be1aedce97df140d1d14452eb7306b3-15478514320529.png) |

</Accordion>

<div data-zendesk-anchors="version-adoption-and-att-consent-dashboard=%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4-%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B9-%D0%B8-%D1%81%D0%BE%D0%B3%D0%BB%D0%B0%D1%81%D0%B8%D1%8F-att h_01HGX98Q4FRVS2B35BVT683D5W=%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4-%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B9-%D0%B8-%D1%81%D0%BE%D0%B3%D0%BB%D0%B0%D1%81%D0%B8%D1%8F-att h_01HGX98Q4F8PQYRSC0J2WE4RQX=sdk-information-ios-and-android h_01HGX98Q4FKWD5496P446FB31B=att-metrics-ios-14 att-and-ios-adoption-metrics-for-ios-apps=%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D0%BA%D0%B8-att-%D0%B8-%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-ios-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-ios h_01HGX98Q4G0C4XTC1DSVP96M19=%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D0%BA%D0%B8-att-%D0%B8-%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-ios-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-ios" />

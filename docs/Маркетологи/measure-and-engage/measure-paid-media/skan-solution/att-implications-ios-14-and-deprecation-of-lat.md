---
title: Последствия ввода ATT (iOS 14+) и прекращение поддержки LAT
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-10-07T17:33:35Z'
  edited_at: '2026-08-19T00:30:49Z'
  id: 360014090597
  locale: ru
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ru/articles/360014090597
---
> **Краткий обзор**: Начиная с iOS 14, iOS использует ATT для определения предпочтений пользователей в области конфиденциальности, и ограниченное отслеживание рекламы (LAT) устарело.

<div id="att-values" />

### Значения ATT

* Начиная с iOS 14: Apple <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> (ATT) предоставляет значения статуса для авторизации отслеживания приложений.
* AppsFlyer получает ATT из следующих источников:
  * AppsFlyer SDK V6+ встроен в Приложение.
  * Через API от рекламодателей. Например, S2S API.
* ATT доступен в Отчеты о необработанных данных. Вам нужно явно запросить это следующим образом:
  * Возникает, если выполняется одно из следующих условий:
  * Страница экспорта данных: На вкладке полей Отчет явно выберите ATT.
  * Data Locker: На странице конфигурации Data Locker явно добавьте ATT в список полей.
  * push: На странице доступ API явно добавьте ATT в список полей.
* В некоторых случаях ATT заполняется значениями, определенными AppsFlyer. Они обозначены префиксом *af* в таблица.
* Если IDFA недоступен, он заполняется нулями.

<div id="att-values-defined-by-apple" />

#### Значения ATT, определенные Apple

| Статус ATT | Наличие IDFA | Поведение |
| --- | --- | --- |
| не\_определено | В iOS 14-14.4: Доступно<br /><br />Начиная с iOS 14.5: Не доступно | Значение ATT по умолчанию |
| Ограничено | Не доступно | Это определяется Apple на основе учетной записи iTunes и не связано с поведением пользователь. Например, на основании возраста пользователь или для Устройства, контролируемых организациями. |
| Отклонено | Не доступно | Возникает, если выполняется одно из следующих условий:<ul><li>Устанавливается после отображения запроса</li><li>пользователь отключил функцию *Разрешить приложениям запрашивать отслеживание* (главный переключатель на уровне устройства)</li><li>Перед установкой iOS 14 на устройство LAT был включен</li></ul> |
| Авторизовано | Доступно | Пользователь явно дал согласие. |

<div id="additional-att-values-defined-by-appsflyer" />

#### Дополнительные значения ATT, определенные AppsFlyer

| Статус ATT | Замечание | Наличие IDFA |
| --- | --- | --- |
| af\_unknown | Значение ATT было сообщено рекламодатель, но оно не является известным значением согласно спецификации <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> | Зависит от версии iOS |
| af\_authorized | Использование IDFA разрешено по одной из следующих причин:<ul><li>Версия iOS устройства: до iOS 14.</li><li>Сообщенное событие содержало IDFA, но не ATT. Например, Приложение с SDK (пакет средств разработки ПО) V5.X на устройстве, работающем под управлением версии iOS до iOS 14.</li></ul> | Доступно |
| af\_unavailable | <ul><li>Рекламодатель не сообщил об ATT в данном событии, и IDFA недоступен.</li><li>SDK (пакет средств разработки ПО) AppsFlyer версии V5.X не поддерживает ATT и не получает IDFA.</li></ul> | Не доступно |

<div id="is-lat-in-iosconsiderations-and-how-lat-translates-to-att-in-ios-14" />

### LAT в iOS — соображения и как LAT преобразуется в ATT в iOS 14

| Версия iOS | Использование LAT |
| --- | --- |
| До iOS 13 | <Image alt="IsLatTrue_us-en.png" src="https://files.readme.io/28440075d9c3913a148228a85ede15048d76f24913b48799ec4de3952d8f33e7-360011938457.png" width="221px" /><br /><br />Если значение true, то включена функция ограниченного отслеживания рекламы, и IDFA недоступен. |
| Начиная с iOS 14 | <Anchor target="_blank" href="https://developer.apple.com/documentation/adsupport/asidentifiermanager/1614148-isadvertisingtrackingenabled">Apple прекратила поддержку *LAT*</Anchor>. Игнорируйте значение *LAT* и используйте ATT. |

**Как LAT преобразуется в ATT в iOS 14**

[<Image alt="LATtoiOS14.5.png" src="https://files.readme.io/872b3acdcd975337ff4de791a9fc98cd45eb50a487e80b3dfad6a1c7d9495739-360017977837.png" width="522px" />](https://files.readme.io/872b3acdcd975337ff4de791a9fc98cd45eb50a487e80b3dfad6a1c7d9495739-360017977837.png)

<div data-zendesk-anchors="att-values=%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-att h_01HGX9468F5YF0KSHB3S49CW2Y=%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-att att-values-defined-by-apple=%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-att-%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-apple h_01HGX9468F0TFTMKP1W2J6GEBV=%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-att-%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-apple additional-att-values-defined-by-appsflyer=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-att-%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-appsflyer h_01HGX96RG9NX9QM2WTX8789DDR=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-att-%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-appsflyer is-lat-in-ios%E2%80%94considerations-and-how-lat-translates-to-att-in-ios-14=lat-%D0%B2-ios--%D1%81%D0%BE%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D0%BA%D0%B0%D0%BA-lat-%D0%BF%D1%80%D0%B5%D0%BE%D0%B1%D1%80%D0%B0%D0%B7%D1%83%D0%B5%D1%82%D1%81%D1%8F-%D0%B2-att-%D0%B2-ios-14 h_01HGX9468F0VTYNXBJRSTNBCMB=lat-%D0%B2-ios--%D1%81%D0%BE%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D0%BA%D0%B0%D0%BA-lat-%D0%BF%D1%80%D0%B5%D0%BE%D0%B1%D1%80%D0%B0%D0%B7%D1%83%D0%B5%D1%82%D1%81%D1%8F-%D0%B2-att-%D0%B2-ios-14" />

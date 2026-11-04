---
title: Интеграция Amazon Vega OS с AppsFlyer
metadata:
  keywords:
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2026-01-19T07:36:38Z'
  edited_at: '2026-08-31T00:21:57Z'
  id: 42971481283601
  locale: ru
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ru/articles/42971481283601
---
> **Вкратце:** Интегрируйте свое приложение Amazon Vega OS Connected TV (CTV) с AppsFlyer, чтобы получать данные об атрибуции и событиях для ваших кампаний в Amazon Vega OS.

<div id="about-amazon-vega-os-ctv-attribution" />

## **Об атрибуции CTV Amazon Vega OS**

Amazon Vega OS для потоковой передачи работает на всех устройствах Amazon Vega OS.

Приложения CTV, транслируемые на Amazon Vega OS, можно интегрировать с AppsFlyer через API, чтобы получать данные атрибуции и измерения эффективности о том, какие источники (органические) и кампании приводят к открытию приложения и in-app событиям. Маркетологи полагаются на эти данные для измерения и оптимизации маркетинговой деятельности.

API-интеграция Amazon Vega OS поддерживает:

* Смарт-ТВ Amazon Vega OS.
* Атрибуция и регистрация событий между CTV-to-CTV. То есть атрибуцию и запись на устройстве Amazon Vega OS пользователя.

<div id="integration-procedures" />

## **Процедуры интеграции**

В таблице ниже перечислены задачи, необходимые для интеграции вашего приложения Amazon Vega OS CTV с AppsFlyer. Чтобы фиксировать прогресс, загрузите эту [электронную таблицу](https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx).

| **Выручка** | **Действия** | **Кто участвует** |
| --- | --- | --- |
| Настройка приложения | <ul><li>[Создание аккаунта](https://www.appsflyer.com/get-started/)</li><li><Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими разрешениями</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте свое приложение Amazon Vega OS CTV в AppsFlyer</Anchor> используя the <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer#amazon-vega-os">структуру идентификатора приложения Amazon Vega</Anchor>.</li></ul> | Маркетолог |
| Интеграция API с вашим приложением (через S2S) | [Интегрируйте AppsFlyer CTV API](https://dev.appsflyer.com/hc/reference/overview-4) в своё CTV-приложение с помощью команд для отправки в AppsFlyer следующих событий.<ul><li>Первое открытие</li><li>События в приложении</li><li>Sessions (Сеансы)</li></ul>**Внимание**<ul><li>Об установках необходимо сообщать до внутренних событий и сеансов.</li><li>Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправить. Убедитесь, что при настройке API вы задали и сопоставили события для отправки в AppsFlyer.</li><li>Для параметра `device_ids` выберите тип `vegaid`.</li><li>Чтобы сообщать о вовлеченности в собственных медиа, интегрируйте [API вовлеченности по показам.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id)</li></ul> | Разработчик приложения |
| Настройка ссылки | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Узнайте, как создавать прямые ссылки атрибуции</Anchor> | Маркетолог |
| Настройка отчета / просмотр данных | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#доступность-данных">Узнайте о доступности данных на дэшбордах и в отчетах</Anchor> | Маркетолог/инженер по обработке и анализу данных |

<div id="traits-and-limitations" />

## Спецификации и ограничения

| Специфика | Примечание |
| --- | --- |
| Неорганические источники | В разработке |
| Обязательный | В настоящее время не поддерживается |
| Данные о затратах | Данные о затратах должны быть отправлены через<Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">импорт данных</Anchor> о затратах методом загрузки файла по электронной почте. |

<div id="see-also" />

### **Смотрите также**

* <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Обзор платформ CTV, ПК и консолей</Anchor>

<div data-zendesk-anchors="about-amazon-vega-os-ctv-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-ctv-amazon-vega-os h_01KFAJYYX01B4E6CDMCH6REGY9=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-ctv-amazon-vega-os integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01KFAJYYX0WZY682B0SSWJM40V=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 traits-and-limitations=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KFAJYYX0E95XEYQCQPCTN700=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F see-also=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5 h_01KFAJYYX00K3RKMYB9QX6KXKN=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

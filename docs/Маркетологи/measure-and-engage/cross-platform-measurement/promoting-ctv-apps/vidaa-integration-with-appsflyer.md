---
title: Интеграция Vidaa с AppsFlyer
metadata:
  keywords:
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2022-11-06T08:13:09Z'
  edited_at: '2026-08-31T00:22:11Z'
  id: 10400222972433
  locale: ru
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ru/articles/10400222972433
---
> **Краткий обзор:** Интегрируйте свое приложение Vidaa Connected TV (CTV) с AppsFlyer, чтобы получать данные об атрибуции и событиях для ваших кампаний на Vidaa.

<div id="about-vidaa-ctv-attribution" />

## Об атрибуции Vidaa CTV

ОС Vidaa для потоковой передачи данных работает на всех телевизорах Vidaa.

Приложения CTV, транслирующие контент на Vidaa, могут интегрироваться с AppsFlyer через API, чтобы получать данные атрибуции и показатели эффективности о том, какие источники (органические) и кампании приводят к открытию приложения и событиям в приложении. Маркетологи полагаются на эти данные для измерения и оптимизации маркетинговой деятельности.

Интеграция Vidaa по API поддерживает:

* Смарт-ТВ Vidaa.
* Атрибуция и регистрация событий между CTV-to-CTV. То есть атрибуция и запись действий на устройстве Vidaa пользователя.

<div id="integration-procedures" />

## Процедуры интеграции

В следующей таблице перечислены задачи, необходимые для интеграции вашего приложения Vidaa CTV с AppsFlyer. Чтобы отслеживать прогресс, скачайте эту <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx">таблицу</Anchor>.

| Выручка | Действия | Кто участвует |
| --- | --- | --- |
| Настройка приложения | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Создание аккаунта</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими разрешениями</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте свое приложение Vidaa CTV в AppsFlyer</Anchor></li></ul> | Маркетолог |
| Интеграция API с вашим приложением (через S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Интегрируйте AppsFlyer API для CTV</Anchor> в свое приложение CTV с помощью команд, чтобы сообщать AppsFlyer о следующих событиях.<ul><li>Первое открытие</li><li>События в приложении</li><li>Sessions (Сеансы)</li></ul>**Внимание**:<ul><li>Об установках необходимо сообщать до внутренних событий и сеансов.</li><li>Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправить. Убедитесь, что при настройке API вы настроили и сопоставили события, которые нужно отправлять в AppsFlyer.</li><li>Для параметра `device_ids` выберите тип `vidaaid`.</li></ul>Чтобы сообщать о взаимодействиях с собственными каналами, интегрируйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API взаимодействия по показам.</Anchor> | Разработчик приложения |
| Настройка ссылки | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Узнайте, как создавать прямые ссылки атрибуции</Anchor> | Маркетолог |
| Настройка отчета / просмотр данных | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#доступность-данных">Узнайте о доступности данных на дэшбордах и в отчетах</Anchor> | Маркетолог/инженер по обработке и анализу данных |

<div id="traits-and-limitations" />

<Accordion title="Спецификации и ограничения">

| Специфика | Специфика |
| --- | --- |
| Неорганические источники | В разработке |
| Обязательный | В настоящее время не поддерживается |
| Данные о затратах | Данные о затратах должны быть отправлены через <Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">Cost Import</Anchor> с использованием метода загрузки файла по электронной почте. |

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Обзор платформ CTV, ПК и консолей</Anchor>

<div data-zendesk-anchors="about-vidaa-ctv-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-vidaa-ctv 01H7Z180QRR77E1GBQ0P0RHVN5=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-vidaa-ctv integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z180QR6HT4R3N9DYSM8WB9=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z180QR0QQ0HK3N5N1G4ENZ=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

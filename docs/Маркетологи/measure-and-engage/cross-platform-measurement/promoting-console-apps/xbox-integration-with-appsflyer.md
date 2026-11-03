---
title: Интеграция Xbox с AppsFlyer
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-04-13T08:28:00Z'
  edited_at: '2026-10-19T14:18:37Z'
  id: 14504812967057
  locale: ru
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/ru/articles/14504812967057
---
> **Краткий обзор:** Интегрируйте свое приложение Xbox с AppsFlyer, чтобы получать данные атрибуции и данные о событиях для своих кампаний на Xbox.

## Об атрибуции Xbox

ОС Xbox для консоли и приложения CTV работают на всех консолях Xbox.

Приложения, работающие на Xbox, могут интегрироваться с AppsFlyer через API S2S, чтобы получать данные атрибуции и измерения эффективности о том, какие источники (органические) и кампании приводят к открытию приложения и событиям в приложении. Маркетологи полагаются на эти данные для измерения и оптимизации маркетинговой деятельности.

Интеграция API Xbox поддерживает:

* Xbox’ы.
* Атрибуция и запись событий для приложений Xbox. То есть атрибуция и запись на устройстве Xbox пользователя.

## Процедуры интеграции

В следующей таблице перечислены задачи, необходимые для интеграции приложения Xbox с AppsFlyer.

| Выручка | Действия | Кто участвует |
| --- | --- | --- |
| Настройка приложения | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Создание аккаунта</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими разрешениями</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте приложение Xbox в AppsFlyer</Anchor></li></ul> | Маркетолог |
| Интеграция API с вашим приложением (через S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Интегрируйте API AppsFlyer</Anchor> в свое приложение с помощью команд, чтобы передавать в AppsFlyer отчеты о следующих событиях.<ul><li>Первое открытие</li><li>События в приложении</li><li>Sessions (Сеансы)</li></ul>**Внимание**:<ul><li>О первых открытиях приложения необходимо сообщать перед внутренними событиями и сеансами приложения.</li><li>Для параметра `device_ids` выберите тип `custom`.</li><li>Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправить. Убедитесь, что при настройке API вы задали и сопоставили события для отправки в AppsFlyer.</li></ul>Чтобы сообщать о взаимодействиях с собственными каналами, интегрируйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API взаимодействия по показам.</Anchor> | Разработчик приложения |
| Настройка отчетов | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#доступность-данных">Узнайте о доступности данных на дэшбордах и в отчетах</Anchor> | Маркетолог/инженер по обработке и анализу данных |

<div id="traits-and-limitations" />

<Accordion title="Спецификации и ограничения">

| Специфика | Специфика |
| --- | --- |
| Обязательный | В настоящее время не поддерживается |
| Данные о затратах | Данные о затратах должны быть отправлены через <Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">импорт данных о затратах</Anchor> методом загрузки файла по электронной почте. |

</Accordion>

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Обзор платформ CTV, ПК и консолей</Anchor>

<div data-zendesk-anchors="about-playstation-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-xbox 01H7Z1NEAJMRWKHS4K168V0753=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-xbox integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z1NEAJJY4ZRVKY74ACXAAR=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z1NEAJRA11P7NG05KRKR8Q=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

---
title: Интеграция Vizio с AppsFlyer
metadata:
  keywords:
    - Developers
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
  created_at: '2022-03-27T15:48:04Z'
  edited_at: '2026-10-19T14:18:55Z'
  id: 5045234293777
  locale: ru
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ru/articles/5045234293777
---
> **Краткий обзор:** Интегрируйте свое приложение Vizio Connected TV (CTV) (канал) с AppsFlyer, чтобы получать данные об атрибуции и событиях для ваших кампаний на Vizio.

<div id="about-vizio-ctv-attribution" />

## Об атрибуции Vizio CTV

Операционная система Vizio SmartCast для потоковой передачи работает на всех телевизорах Vizio.

Приложения CTV, транслируемые на Vizio, могут интегрироваться с AppsFlyer через API, чтобы получать данные атрибуции и измерения эффективности о том, какие источники (неорганические или органические) и платные кампании приводят к открытию приложения и событиям в приложении. Маркетологи полагаются на эти данные для измерения и оптимизации маркетинговой деятельности.

Интеграция Vizio API поддерживает следующее:

* Смарт-ТВ Vizio.
* Атрибуция и регистрация событий между CTV-to-CTV. Значение, атрибуция и запись первого открытия приложения Vizio (эквивалент установки) и событий, происходящих на пользовательском устройстве Vizio.

<div id="vizio-attribution-flow" />

### Порядок атрибуции Vizio

<Image align="center" alt="CTV_attribution_flow_-_Vizio__1_.png" src="https://files.readme.io/f4ab4b6c9e045fe00b537814fa9f10746b525a5512e5805e62eb0c2e4c9a8615-6318406872337.png" />

<div id="integration-procedures" />

## Процедуры интеграции

В таблице ниже перечислены задачи, необходимые для интеграции вашего приложения Vizio CTV с AppsFlyer.

| Выручка | Действия | Кто участвует |
| --- | --- | --- |
| Настройка приложения | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Создание аккаунта</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими разрешениями</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте приложение Vizio CTV в AppsFlyer</Anchor></li></ul> | Маркетолог |
| Интеграция API с вашим приложением (через S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Интегрируйте AppsFlyer API для CTV</Anchor> в свое приложение CTV с помощью команд, чтобы сообщать AppsFlyer о следующих событиях.<ul><li>Первое открытие</li><li>События в приложении</li><li>Sessions (Сеансы)</li></ul>**Внимание**:<ul><li>Об установках необходимо сообщать до внутренних событий и сеансов.</li><li>Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправить. Убедитесь, что при настройке API вы задали и сопоставили события для отправки в AppsFlyer.</li></ul>Чтобы сообщать о взаимодействиях с собственными каналами, интегрируйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API взаимодействия по показам.</Anchor> | Разработчик приложения |
| Интеграция партнера | Добавьте Vizio в качестве рекламной сети (интегрированного партнера) в AppsFlyer:<ol><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#a-activate-partner">Активация партнера</Anchor></li><li>[Необязательно] Включите **<Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#e-install-attribution">атрибуцию просмотров</Anchor>.**</li></ol> | Маркетолог |
| Настройка ссылки | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Узнайте, как создавать прямые ссылки атрибуции</Anchor> | Маркетолог |
| Настройка отчета / просмотр данных | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#доступность-данных">Узнайте о доступности данных на дэшбордах и в отчетах</Anchor> | Маркетолог/инженер по обработке и анализу данных |

<div id="traits-and-limitations" />

<Accordion title="Спецификации и ограничения">

| Специфика | Специфика |
| --- | --- |
| Обязательный | В настоящее время не поддерживается |
| Атрибуция по просмотрам | По умолчанию — 24 часа. |
| Данные о затратах | Данные о затратах должны быть отправлены через <Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">Cost Import</Anchor> методом загрузки файла по электронной почте. |

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Обзор платформ CTV, ПК и консолей</Anchor>

<div data-zendesk-anchors="about-vizio-ctv-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-vizio-ctv 01H7Z16QWWCPR309JDKV7H0469=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-vizio-ctv vizio-attribution-flow=%D0%BF%D0%BE%D1%80%D1%8F%D0%B4%D0%BE%D0%BA-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-vizio 01H7Z16QWW3GJEAGV0F3JHTKE1=%D0%BF%D0%BE%D1%80%D1%8F%D0%B4%D0%BE%D0%BA-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-vizio integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z16QWW1WX5F947WPH9HBQX=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z16QWX24K8QCEJVBX1SQEA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

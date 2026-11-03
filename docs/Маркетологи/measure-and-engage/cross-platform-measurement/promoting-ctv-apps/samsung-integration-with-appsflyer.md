---
title: Интеграция Samsung с AppsFlyer
metadata:
  keywords:
    - Advertisers
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
  created_at: '2022-05-03T09:19:48Z'
  edited_at: '2026-10-07T00:11:33Z'
  id: 5860544738065
  locale: ru
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ru/articles/5860544738065
---
> **At a glance:** Интегрируйте свое приложение Samsung Connected TV (CTV) с AppsFlyer, чтобы получать данные об атрибуции и событиях для ваших кампаний на Samsung.

## Об атрибуции Samsung CTV

Операционная система Samsung Tizen OS для потокового вещания работает на всех телевизорах Samsung.

Стриминговые CTV-приложения на Samsung могут интегрироваться с AppsFlyer через API, чтобы получать данные атрибуции и измерения эффективности о том, какие источники (органические и неорганические) и кампании приводят к открытию приложения и событиям в приложении. Маркетологи полагаются на эти данные для измерения и оптимизации маркетинговой деятельности.

Интеграция API Samsung поддерживает следующее:

* Телевизоры Samsung Smart TV.
* Атрибуция и регистрация событий CTV-to-CTV, то есть атрибуция и регистрация происходят на устройстве Samsung пользователя.

### Поток атрибуции Samsung

![[ПОДТВЕРДИТЬ: Схема процесса атрибуции Samsung CTV, показывающая передачу данных об установках, сеансах и событиях внутри приложения из приложения Samsung в AppsFlyer через S2S API или SDK]](https://files.readme.io/a1031878e8aced81da5762d06ae0163770cd73b9a7c91224ea7665aa142d2ce8-7215151128209.png)

## Процедуры интеграции

В таблице ниже перечислены задачи, необходимые для интеграции приложения Samsung CTV с AppsFlyer.

| Выручка | Действия | Кто задействован |
| --- | --- | --- |
| Настройка приложения | Чтобы интегрировать ваше CTV-приложение Samsung с AppsFlyer:<ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Создание аккаунта</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими правами</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте свое приложение Samsung CTV в AppsFlyer</Anchor></li></ul> | Маркетолог |
| Интеграция API с вашим приложением (через S2S или SDK) | Вы можете использовать два метода интеграции: server-to-server (S2S) и SDK.<br /><br />Для метода S2S <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">интегрируйте AppsFlyer API</Anchor> в ваше приложение с командами для сообщения в AppsFlyer о следующих событиях.<ul><li>Первое открытие</li><li>События в приложении</li><li>Sessions (Сеансы)</li></ul>**<span id="h_01M349521V96NRS5CJKXZKMA6P"></span>Примечание:**<ul><li>Передавайте данные об установках до событий в приложении и сессий.</li><li>Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправлять, и убедитесь, что вы настроили и сопоставили события для отправки в AppsFlyer.</li></ul><br /><br />Чтобы сообщать о вовлеченности в собственных медиа, интегрируйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API вовлеченности по показам</Anchor>.<br /><br />Для метода SDK смотрите документацию Samsung в хабе разработчика. | Разработчик приложений |
| Интеграция партнера | Добавьте Samsung в качестве рекламной сети (интегрированного партнера) в AppsFlyer.<ol><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#a-activate-partner">Активация партнера</Anchor></li><li>[Необязательно] Включите <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#e-install-attribution">**атрибуцию по показам**</Anchor>.</li></ol> | Маркетолог |
| Настройка ссылки | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Узнайте, как создавать прямые ссылки атрибуции</Anchor> | Маркетолог |
| Настройка отчета/просмотр данных | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#доступность-данных">Узнайте о доступности данных на дэшбордах и в отчетах</Anchor> | Маркетолог / инженер по обработке и анализу данных |

## Характеристики и ограничения

| Специфика | Замечания |
| --- | --- |
| Обязательный | В настоящее время не поддерживается |
| Данные о затратах | Импортируйте данные о расходах через <Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">Cost Import</Anchor>, используя метод загрузки файла **по электронной почте**. Вы также можете получать данные **через API** для Google, Meta или TikTok. |
| Поддерживаемые регионы | Поддержка CTV и preload-кампаний зависит от региона, а именно.<ul><li>AppsFlyer поддерживает кампании Connected TV (CTV) только в США, включая передачу постбэков Samsung через интеграцию с Samsung demand-side platform (DSP) (`samsungdsp_int`).</li><li>В регионе EMEA (Европа, Ближний Восток и Африка) AppsFlyer поддерживает CTV-кампании без передачи постбэков Samsung через интеграцию Samsung EMEA DSP (`samsungemea_int`).</li><li>В других регионах CTV-кампании не поддерживаются.</li><li>AppsFlyer поддерживает preload-кампании по всему миру.</li></ul> |

<div data-zendesk-anchors="about-samsung-ctv-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-samsung-ctv 01H7Z17A1QPJQH9R5MRBVTMG37=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-samsung-ctv samsung-attribution-flow=%D0%BF%D0%BE%D1%82%D0%BE%D0%BA-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-samsung 01H7Z17A1Q03CEJT848FRFHDPQ=%D0%BF%D0%BE%D1%82%D0%BE%D0%BA-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-samsung integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z17A1QQN4FYJXZFS5FP2NY=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F 01H7Z17A1QVW58B2FZE7SDJHHJ=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

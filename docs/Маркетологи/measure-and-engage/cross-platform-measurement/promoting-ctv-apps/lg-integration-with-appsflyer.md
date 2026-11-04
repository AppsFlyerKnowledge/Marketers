---
title: Интеграция LG с AppsFlyer
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
  created_at: '2022-07-03T10:31:42Z'
  edited_at: '2026-08-19T00:22:04Z'
  id: 7341725624081
  locale: ru
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ru/articles/7341725624081
---
> **Краткий обзор:** Интегрируйте свое приложение LG Connected TV (CTV) с AppsFlyer, чтобы получать данные об атрибуции и событиях для ваших кампаний на LG.

<div id="about-lg-ctv-attribution" />

## Об атрибуции LG CTV

ОС LG Webos для потоковой передачи данных работает на всех телевизорах LG.

Приложения CTV, транслирующие контент на LG, могут интегрироваться с AppsFlyer через API, чтобы получать данные об атрибуции и показатели эффективности: какие источники (органические и неорганические) и кампании способствуют открытию приложения и событиям в приложении. Маркетологи полагаются на эти данные для измерения и оптимизации маркетинговой деятельности.

Интеграция LG по API поддерживает:

* Смарт-телевизоры LG.
* Атрибуция с CTV на CTV и запись событий. То есть атрибуция и запись на LG-устройстве пользователя.

<div id="integration-procedures" />

## Процедуры интеграции

В следующей таблице перечислены задачи, необходимые для интеграции приложения LG CTV в AppsFlyer.

| Выручка | Действия | Кто задействован |
| --- | --- | --- |
| Настройка приложения | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Создайте аккаунт AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими разрешениями</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте ваше приложение LG CTV в AppsFlyer</Anchor></li></ul> | Маркетолог |
| Интеграция API с вашим приложением (через S2S или SDK) | Вы можете использовать два метода интеграции: S2S и SDK.<br /><br />Для метода S2S <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">интегрируйте AppsFlyer API</Anchor> в ваше приложение с командами для сообщения в AppsFlyer о следующих событиях.<ul><li>Первые открытия</li><li>Внутренние события приложений</li><li>Сессии</li></ul>**Примечание**:<ul><li>Об установках необходимо сообщать до событий и сессий в приложении.</li><li>Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправлять. Убедитесь, что при настройке API вы задали и сопоставили события для отправки в AppsFlyer.</li></ul>Для получения отчетов о вовлеченности в собственных СМИ подключите <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API вовлеченности по показам</Anchor>.<br /><br />Для метода SDK смотрите <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk">документацию LG</Anchor> в хабе разработчика. | Разработчик приложений |
| Интеграция партнера | Добавьте LG Ads в качестве рекламной сети (интегрированного партнера) в AppsFlyer:<ol><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#a-activate-partner">Активация партнера</Anchor></li><li>[Необязательно] Включите <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#e-install-attribution">**атрибуцию по просмотрам**</Anchor> .</li></ol> | Маркетолог |
| Настройка ссылки | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Узнайте, как создавать прямые ссылки атрибуции</Anchor> | Маркетолог |
| Настройка отчета/просмотр данных | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#доступность-данных">Узнайте о доступности данных на дэшбордах и в отчетах</Anchor> | Маркетолог/Инженер по обработке и анализу данных |

<div id="traits-and-limitations" />

<Accordion title="Характеристики и ограничения">

| Специфика | Замечания |
| --- | --- |
| Обязательный | В настоящее время не поддерживается |
| Данные о затратах | Данные о затратах должны быть отправлены через<Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">импорт данных</Anchor> о затратах методом загрузки файла по электронной почте. |
| Атрибуция | LG Ads использует вероятностное моделирование для атрибуции; сопоставление идентификаторов в настоящее время недоступно. |
| идентификатор клиента | В качестве значения этого параметра укажите идентификатор клиента LG (`cust_id`), полученный от LG Ads. |
| Детерминированная атрибуция | Есть возможность включить детерминированное сопоставление рекламного идентификатора ID для атрибуции. Для этого необходимо выполнить следующие требования:<ul><li>LG должна провести юридическую проверку, прежде чем в приложениях контент-партнеров можно будет включить отображение рекламного идентификатора ID.</li><li>В рамках этой юридической проверки контент-партнер напрямую работает с LG Electronics, и обе стороны должны подписать юридическое соглашение.</li><li>Приложения контент-партнеров должны интегрировать функцию сбора и передачи рекламного идентификатора ID LG, а также выпустить инициируемое пользователем обновление приложения, чтобы начать показывать рекламный идентификатор ID в AppsFlyer.</li><li>Для получения дополнительной информации обратитесь к вашему CSM в AppsFlyer и  [partnerships@lgads.tv](mailto:partnerships@lgads.tv)</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Обзор платформ CTV, ПК и консолей</Anchor>

<div data-zendesk-anchors="about-lg-ctv-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-lg-ctv 01H7Z17N0YAAGTDPMGZ89F7AVB=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-lg-ctv integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z17N0Y8RE5PS15N2JG5NRH=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z17N0YCX89SYYJ1AMPM6W4=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

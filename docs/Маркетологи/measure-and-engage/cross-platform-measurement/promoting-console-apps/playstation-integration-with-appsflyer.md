---
title: Интеграция PlayStation с AppsFlyer
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-11-03T15:12:14Z'
  edited_at: '2026-09-23T00:10:21Z'
  id: 10342860530961
  locale: ru
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/ru/articles/10342860530961
---
> **At a glance:** Узнайте, как интегрировать ваше приложение PlayStation с AppsFlyer и как измерять рекламу, которая работает на PlayStation.

В этой статье рассматриваются две связанные, но разные интеграции.

* [Интегрируйте ваше приложение PlayStation с AppsFlyer](#интегрируйте-ваше-приложение-playstation-с-appsflyer): получайте данные Атрибуции и событий для вашего приложения PlayStation независимо от того, откуда приходят ваши пользователи.
* [Измеряйте рекламу, которая работает на PlayStation](#измерение-рекламы-которая-запускается-на-playstation): активируйте интеграцию с PlayStation Ads, чтобы измерять рекламу, которая работает на консолях PlayStation и стимулирует установки вашего приложения.

## Интегрируйте ваше приложение PlayStation с AppsFlyer

ОС PlayStation для консольных приложений и приложений CTV (Connected TV) работает на всех устройствах PlayStation.

Приложения, работающие на PlayStation, могут интегрироваться с AppsFlyer через S2S (server-to-server) API, чтобы получать данные атрибуции и измерения эффективности о том, какие источники и кампании приводят к открытию приложения и событиям в приложении. Маркетологи полагаются на эти данные для измерения и оптимизации маркетинговой деятельности.

Интеграция PlayStation API поддерживает следующее:

* PlayStations.
* Атрибуцию и регистрацию событий для приложений PlayStation, то есть атрибуцию и регистрацию на устройстве пользователя PlayStation.

### Пример процесса атрибуции

Ниже приведен пример процесса, в котором описаны наиболее важные этапы пути пользователя от вовлечения по рекламе до атрибуции. В него входит рекомендованная AppsFlyer кроссплатформенная целевая страница. **Примечание:** Хотя мы рекомендуем использовать кроссплатформенную целевую страницу, вы также можете использовать прямые ссылки атрибуции.

<Image alt="Схема потока Атрибуции: от маркетинговой точки взаимодействия через кроссплатформенную целевую страницу до установки приложения PlayStation" src="https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg" width="3938px" />

1. <span id="marketing-touchpoint"></span>Маркетинговые точки взаимодействия: клиенты взаимодействуют с вашим брендом через онлайн- или офлайн-каналы. Это могут быть электронная почта и рассылки, социальные сети, мобильный веб и многое другое.
2. Целевая страница игры: Целевая страница игры направляет клиентов на страницу загрузки приложения. Этот шаг важен для сбора UTM (Urchin Tracking Module) и других параметров URL-адреса, чтобы выполнять атрибуцию клиентов от клика/установки к исходным медиаисточникам или вашим собственным медиа.  
   Целевая страница также полезна, потому что на ней есть ссылки на различные платформы, поддерживаемые вашей игрой. Например, на целевой странице также можно разместить ссылки на страницы Xbox, Microsoft Store и Steam.
3. Страница приложения: это URL-адрес страницы вашего приложения PlayStation, на которой ваше приложение размещено для загрузки клиентами.
4. Установка игры: Пользователь устанавливает игру, запуская атрибуцию и запись внутренних событий приложения и сессий.

### Процедуры интеграции

В следующей таблице перечислены задачи, необходимые для интеграции вашего приложения PlayStation с AppsFlyer.

| Выручка | Действия | Кто задействован |
| --- | --- | --- |
| Настройка приложения | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Создание аккаунта</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими разрешениями</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте свое приложение PlayStation в AppsFlyer</Anchor></li></ul> | Маркетолог |
| Интеграция API с вашим приложением (через S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">Интегрируйте API AppsFlyer</Anchor> в свое приложение с помощью команд, чтобы сообщать AppsFlyer о следующих событиях.<ul><li>Первое открытие</li><li>События в приложении</li><li>Sessions (Сеансы)</li></ul>**Внимание**:<ul><li>Сообщайте о событии первого открытия приложения до событий в приложении и сессий.</li><li>Для параметра `device_ids` выберите тип `custom`.<ul><li>Сгенерированный идентификатор `custom` для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">первых открытий</Anchor> должен совпадать с идентификатором, который вы используете для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">событий в приложении</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">сессий</Anchor>.</li></ul></li><li>Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправить. При настройке API убедитесь, что вы сопоставили события, которые хотите отправлять в AppsFlyer.</li><li>Тип идентификатора устройства `psid` предназначен для использования в качестве рекламного идентификатора. В настоящее время PlayStation не поддерживает сопоставление рекламных идентификаторов, поэтому нет необходимости использовать этот тип идентификатора устройства.</li><li>Мы рекомендуем передавать `psn_uid`, который является идентификатором учетной записи PlayStation, в поле `customer_user_id`. Перед отправкой обязательно анонимизируйте это значение.</li></ul>Чтобы сообщать о взаимодействиях с собственными каналами, интегрируйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API взаимодействия по показам.</Anchor> | Разработчик приложения |
| Настройка кросс-платформенной целевой страницы | **Рекомендуется:** Кроссплатформенная целевая страница, на которой запущен смарт-скрипт AppsFlyer, позволяет проводить атрибуцию из веба в приложение. Это рекомендуется, когда ваша кампания продвигает приложение, которое также доступно на других платформах, например Epic и Native PC.<br /><br /><Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Узнайте о кросс-платформенных целевых страницах</Anchor><br /><br /><Anchor target="_blank" href="/marketers/ru/docs/cross-platform-landing-pages-with-smart-script">Узнайте, как создать кросс-платформенную целевую страницу</Anchor><br /><br />**Внимание**:<br /><br />Для PlayStation необходимы следующие параметры:<ul><li>**платформа**: playstation</li><li>**app\_id**: идентификатор ID приложения</li><li>**медиа-источник**</li></ul>Следующие параметры не являются обязательными, но рекомендуются:<ul><li>**campaign (кампания)**</li><li>**ad (объявление)**</li><li>**ad\_set (группа объявлений)**</li></ul> | Маркетолог (может потребоваться помощь разработчика) |
| Настройка ссылки | Если вы не используете кроссплатформенную целевую страницу, вы можете создать прямые ссылки атрибуции для размещения за рекламой.<br /><br /><Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Узнайте, как создавать прямые ссылки атрибуции</Anchor> | Маркетолог |
| Настройка отчета / просмотр данных | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#доступность-данных">Узнайте о доступности данных на дэшбордах и в отчетах</Anchor> | Маркетолог/инженер по обработке и анализу данных |

## Измерение рекламы, которая запускается на PlayStation

AppsFlyer поддерживает измерение рекламы, которая запускается на консолях PlayStation и приводит к установкам вашего приложения PlayStation. Этот процесс отделен от общей интеграции в разделе [Процедуры интеграции](#процедуры-интеграции) выше. Он применяется только в том случае, если PlayStation также является одним из ваших рекламных источников, и доступен рекламодателям, у которых уже настроено активное приложение PlayStation в AppsFlyer.

Чтобы запускать и измерять рекламу PlayStation:

1. **Создайте ссылку атрибуции.** Следуйте инструкциям в статье <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Прямые ссылки атрибуции для CTV, ПК и консольных платформ</Anchor> и задайте для платформы значение `playstation`.
2. **Отправьте ссылку в PlayStation.** Попросите команду PlayStation, которая управляет рекламой, разместить ссылку атрибуции в вашей рекламе.
3. **Активируйте интеграцию PlayStation Ads в AppsFlyer.** Используйте идентификатор партнера `playstation_int`. Общие шаги активации см. в статье <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner">Настройка интегрированного партнера</Anchor>.
4. **Просматривайте результаты в AppsFlyer.** Данные об эффективности отображаются в стандартных дэшбордах и отчетах AppsFlyer с атрибуцией к медиаисточнику PlayStation.

> 🚧 **Важно!**
>
> На этом этапе вы не можете передавать обратно команде PlayStation, управляющей рекламой, сигналы, такие как конверсии, события или постбэки. Данные измерения остаются в AppsFlyer и не отправляются обратно в PlayStation для оптимизации.

### Примеры ссылок атрибуции

Ниже приведены примеры ссылок атрибуции кликов и показов для PlayStation.

**Клик**

```
https://engagements.appsflyer.com/v1.0/s2s/click/app/playstation/10000000
?af_media_source=playstation_int
&af_campaign_id={campaign_id}
&af_ip={USER_IP}
&af_campaign={campaign_name}
```

**Показ**

```
https://engagements.appsflyer.com/v1.0/s2s/impression/app/playstation/10000000
?af_media_source=playstation_int
&af_campaign_id={campaign_id}
&af_ip={USER_IP}
&af_campaign={campaign_name}
```

| Плейсхолдер | Тип | Значение |
| --- | --- | --- |
| 10000000 | Параметры пути | Идентификатор приложения PlayStation рекламодателя в AppsFlyer. Замените на реальный идентификатор приложения без префикса платформы. |
| s2s / c2s | Параметры пути | Указывает, отправляется ли запрос от сервера к серверу (s2s) или от клиента к серверу (c2s). Заменяет сегмент s2s, показанный в примерах URL-адресов выше. Команда PlayStation Ads определяет, какой из них применяется. |
| `{campaign_id}` | Параметр запроса | Идентификатор кампании, заполняется в PlayStation. |
| `{campaign_name}` | Параметр запроса | Название кампании, заполняется в PlayStation. |
| `{USER_IP}` | Параметр запроса | IP-адрес конечного пользователя, заполняется PlayStation. |

## Спецификации и ограничения

| Специфика | Description(Описание) |
| --- | --- |
| Данные о затратах | Отправляйте данные о расходах через <Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">Ad Spend Ingestion</Anchor>, используя метод загрузки файла по электронной почте. |

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Обзор платформ CTV, ПК и консолей</Anchor>

<div data-zendesk-anchors="integrate-your-playstation-app-with-appsflyer=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B8%D1%80%D1%83%D0%B9%D1%82%D0%B5-%D0%B2%D0%B0%D1%88%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-playstation-%D1%81-appsflyer 01H7Z1HPD0AB0VP6REMBF2HCR8=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B8%D1%80%D1%83%D0%B9%D1%82%D0%B5-%D0%B2%D0%B0%D1%88%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-playstation-%D1%81-appsflyer example-attribution-flow=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HP1Q8B11P0Q8F2Z2FRDSPNDE=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint 01H7Z1HPD0VAMPEHBPN8MAT3ST=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 run-and-measure-ads-on-playstation=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D0%B0%D1%8F-%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA%D0%B0%D0%B5%D1%82%D1%81%D1%8F-%D0%BD%D0%B0-playstation h_01M2FS60HDHKN7GZWFADVMAEKD=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D0%B0%D1%8F-%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA%D0%B0%D0%B5%D1%82%D1%81%D1%8F-%D0%BD%D0%B0-playstation h_01M2FS60HDVJVBNN2MGCA8CVXG=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE sample-attribution-links=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01M2FS60HDQGDT1KCSGCPJAFJC=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 traits-and-limitations=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F 01H7Z1HPD0CS7CTX2KS2RVD3VA=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HE0T79YSNWGB3W4S7WEBW1B5=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
